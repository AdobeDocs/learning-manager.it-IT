---
description: Scopri come utilizzare le impostazioni di iscrizione alla bacheca e le API dei sottoscrittori per configurare le e-mail di riepilogo e gestire i sottoscrittori delle bacheche
jcr-language: en_us
title: Modifiche alle API in novembre 2026
exl-id: 9b2d3856-810c-4352-bf18-667f698d4d70
source-git-commit: d1399781294a58f6ede8461878c979bd8b5edb34
workflow-type: tm+mt
source-wordcount: '5724'
ht-degree: 4%
---

# Modifiche alle API di dicembre 2026

## API per le notifiche degli istruttori dell&#39;area discussioni

Questo articolo descrive le nuove API che supportano le notifiche per gli istruttori nell’area discussioni. Utilizzali per iscrivere istruttori e manager di coorte alle aree discussioni e per controllare quale attività viene visualizzata nelle e-mail di riepilogo.

### Sequenza API {#api-sequence}

Le API sono suddivise in due gruppi. L&#39;API `boardSubscriptionSettings` funziona a livello di account. L’API per abbonati funziona a livello di bacheca. Utilizza le API in questa sequenza:

| Passaggio | API | Scopo | Ambito |
|---|---|---|---|
| 1 | [`POST /boardSubscriptionSettings`](#api-create-settings) | Configura le impostazioni a livello di account. | `admin:write` |
| 2 | [`PATCH /boardSubscriptionSettings`](#api-update-settings) | Aggiorna le impostazioni a livello di account. | `admin:write` |
| 3 | [`GET /boardSubscriptionSettings`](#api-get-settings) | Recupera le impostazioni a livello di account. | `admin:read` |
| 4 | [`GET /boards/{id}/subscribers`](#api-get-subscribers) | Ottieni l’elenco degli utenti iscritti a una bacheca. | `admin:read` |
| 5 | [`POST /boards/{id}/subscribers`](#api-subscribe-users) | Iscriviti gli utenti a una bacheca. | `admin:write` |
| 6 | [`DELETE /boards/{id}/subscribers/{userId}`](#api-unsubscribe-user) | Annulla l’iscrizione di un utente a una bacheca. | `admin:write` |

### Autenticazione e autorizzazioni

Chiunque esegua l’autenticazione con OAuth e disponga degli ambiti `admin:read` e `admin:write` può chiamare queste API. Le API utilizzano i seguenti ambiti OAuth:

* `admin:read`: elenca i sottoscrittori e legge le impostazioni di notifica (`GET` richieste).
* `admin:write`: creare o modificare le impostazioni di notifica e aggiungere o rimuovere sottoscrittori (`POST`, `PATCH` e `DELETE` richieste).

>[!NOTE]
>
>L’accesso alla bacheca viene controllato di nuovo quando viene inviata una notifica. Se un abbonato perde l&#39;accesso a una bacheca, la consegna viene ignorata per quella bacheca, ma l&#39;abbonamento viene mantenuto. Se l&#39;accesso viene restituito, il recapito viene ripreso.

### Limiti e considerazioni

* Il numero di sottoscrittori che è possibile aggiungere è limitato.
* Il digest viene inviato come un singolo messaggio e-mail senza impaginazione e il corpo del messaggio ha un limite di dimensione. Per le bacheche con attività elevata, scegli una frequenza di riepilogo che consenta di gestire ogni e-mail, ad esempio ogni 6 ore.
* I collegamenti di riepilogo aprono il post, il commento o la risposta solo per gli utenti che hanno effettuato l’accesso.

## API per creare impostazioni a livello di account {#api-create-settings}

### Scopo dell’API {#purpose-create-settings}

Utilizza questa API per configurare le impostazioni a livello di account per le notifiche di abbonamento alla bacheca per la prima volta. Le impostazioni consentono di controllare la modalità di generazione dei digest delle notifiche nell’account:

* Gli eventi dell&#39;area discussioni che generano le notifiche.
* Quante volte vengono inviate e-mail di riepilogo.
* Indica se sono inclusi post, commenti, risposte e voti.

Per modificare le impostazioni in seguito, utilizzare [`PATCH /boardSubscriptionSettings`](#api-update-settings).

### Endpoint {#endpoint-create-settings}

```http
POST /primeapi/v2/boardSubscriptionSettings
```

| Proprietà | Valore |
|---|---|
| Ambito | `admin:write` |
| Formato richiesta | `application/vnd.api+json;charset=UTF-8` |
| Formato di risposta | `application/vnd.api+json;charset=UTF-8` |

### Corpo della richiesta {#request-body-create-settings}

Invia le impostazioni come attributi di una risorsa `boardSubscriptionSettings`.

| Campo | Tipo | Descrizione |
|---|---|---|
| `notifyNewPost` | booleano | Indica se gli abbonati ricevono una notifica quando viene aggiunto un nuovo post a una bacheca. |
| `notifyComment` | booleano | Indica se i sottoscrittori ricevono una notifica quando viene aggiunto un commento a un post. |
| `notifyReply` | booleano | Indica se i sottoscrittori ricevono una notifica quando viene aggiunta una risposta a un commento. |
| `digestFrequencyHours` | numero intero | La frequenza, espressa in ore, con cui viene inviato il messaggio e-mail di riepilogo. I valori validi sono compresi tra 1 e 168 (una settimana). Ad esempio, 24 invia un riepilogo giornaliero e 168 invia un riepilogo settimanale. |

### Richiesta di esempio {#example-request-create-settings}

```bash
curl -X POST \
--header 'Content-Type: application/vnd.api+json;charset=UTF-8' \
--header 'Accept: application/vnd.api+json' \
--header 'Authorization: oauth <access-token>' \
-d '{
  "data": {
    "type": "boardSubscriptionSettings",
    "attributes": {
      "notifyNewPost": true,
      "notifyComment": true,
      "notifyReply": true,
      "digestFrequencyHours": 24
    }
  }
}' \
'https://learningmanager.adobe.com/primeapi/v2/boardSubscriptionSettings'
```

### Esempio di risposta - 201 creato {#example-response-create-settings}

```json
{
  "links": {
    "self": "https://learningmanager.adobe.com/primeapi/v2/boardSubscriptionSettings"
  },
  "data": {
    "id": "1010",
    "type": "boardSubscriptionSettings",
    "attributes": {
      "digestFrequencyHours": 24,
      "notifyComment": true,
      "notifyNewPost": true,
      "notifyReply": true
    }
  }
}
```

### Codici di risposta {#response-codes-create-settings}

| Stato | Significato |
|---|---|
| 201 | La richiesta è riuscita. Sono state create le impostazioni a livello di account. |
| 400 | Errore generico di richiesta non valida. |
| 401 | Nella richiesta mancano credenziali valide oppure l&#39;accesso è stato negato a causa di credenziali non valide. |

## API per aggiornare le impostazioni a livello di account {#api-update-settings}

### Scopo dell’API {#purpose-update-settings}

Utilizza questa API per aggiornare le impostazioni a livello di account create con [`POST /boardSubscriptionSettings`](#api-create-settings). Ad esempio, potete modificare la frequenza di digest o attivare o disattivare un tipo di evento.

### Endpoint {#endpoint-update-settings}

```http
PATCH /primeapi/v2/boardSubscriptionSettings
```

| Proprietà | Valore |
|---|---|
| Ambito | `admin:write` |
| Formato richiesta | `application/vnd.api+json;charset=UTF-8` |
| Formato di risposta | `application/vnd.api+json;charset=UTF-8` |

### Corpo della richiesta {#request-body-update-settings}

Invia gli attributi che desideri modificare nello stesso formato dell&#39;API di creazione: `notifyNewPost`, `notifyComment`, `notifyReply` e `digestFrequencyHours`. Gli attributi non inviati mantengono i valori correnti. Per la descrizione di ogni attributo, vedere [API per creare impostazioni a livello di account](#api-create-settings).

### Richiesta di esempio {#example-request-update-settings}

```bash
curl -X PATCH \
--header 'Content-Type: application/vnd.api+json;charset=UTF-8' \
--header 'Accept: application/vnd.api+json' \
--header 'Authorization: oauth <access-token>' \
-d '{
  "data": {
    "type": "boardSubscriptionSettings",
    "attributes": {
      "notifyReply": true,
      "digestFrequencyHours": 12
    }
  }
}' \
'https://learningmanager.adobe.com/primeapi/v2/boardSubscriptionSettings'
```

### Esempio di risposta - 200 OK {#example-response-update-settings}

```json
{
  "links": {
    "self": "https://learningmanager.adobe.com/primeapi/v2/boardSubscriptionSettings"
  },
  "data": {
    "id": "1010",
    "type": "boardSubscriptionSettings",
    "attributes": {
      "digestFrequencyHours": 12,
      "notifyComment": true,
      "notifyNewPost": true,
      "notifyReply": true
    }
  }
}
```

### Codici di risposta {#response-codes-update-settings}

| Stato | Significato |
|---|---|
| 200 | La richiesta è riuscita. Le impostazioni a livello di account sono state aggiornate e la risposta contiene le impostazioni correnti. |
| 400 | Errore generico di richiesta non valida. |
| 401 | Nella richiesta mancano credenziali valide oppure l&#39;accesso è stato negato a causa di credenziali non valide. |

## API per recuperare le impostazioni a livello di account {#api-get-settings}

### Scopo dell’API {#purpose-get-settings}

Quando gli utenti si iscrivono a una bacheca, Adobe Learning Manager può notificare loro l&#39;attività in quella bacheca tramite e-mail di riepilogo. Le impostazioni a livello di account determinano i tipi di attività che attivano una notifica e la frequenza con cui viene inviato il digest.

Questa API consente di recuperare tali impostazioni. Utilizzarlo per visualizzare la configurazione di notifica corrente nell&#39;applicazione o per verificare le impostazioni prima di creare le funzionalità che dipendono da esse.

### Endpoint {#endpoint-get-settings}

```http
GET /primeapi/v2/boardSubscriptionSettings
```

| Proprietà | Valore |
|---|---|
| Ambito | `admin:read` |
| Formato di risposta | `application/vnd.api+json;charset=UTF-8` |

### Richiesta di esempio {#example-request-get-settings}

```bash
curl -X GET \
--header 'Accept: application/vnd.api+json' \
--header 'Authorization: oauth <access-token>' \
'https://learningmanager.adobe.com/primeapi/v2/boardSubscriptionSettings'
```

### Esempio di risposta - 200 OK {#example-response-get-settings}

```json
{
  "links": {
    "self": "https://learningmanager.adobe.com/primeapi/v2/boardSubscriptionSettings"
  },
  "data": {
    "id": "1010",
    "type": "boardSubscriptionSettings",
    "attributes": {
      "digestFrequencyHours": 24,
      "notifyComment": true,
      "notifyNewPost": true,
      "notifyReply": true
    }
  }
}
```

### Schema risorsa {#resource-schema-get-settings}

**`boardSubscriptionSettings`attributi**

| Campo | Tipo | Descrizione |
|---|---|---|
| `notifyNewPost` | booleano | Indica se gli abbonati ricevono una notifica quando viene aggiunto un nuovo post a una bacheca. |
| `notifyComment` | booleano | Indica se i sottoscrittori ricevono una notifica quando viene aggiunto un commento a un post. |
| `notifyReply` | booleano | Indica se i sottoscrittori ricevono una notifica quando viene aggiunta una risposta a un commento. |
| `digestFrequencyHours` | numero intero | La frequenza, espressa in ore, con cui viene inviato il messaggio e-mail di riepilogo. I valori validi sono compresi tra 1 e 168 (una settimana). Utilizza questo valore per indicare agli utenti la frequenza con cui devono ricevere le e-mail di riepilogo. Ad esempio, mostra &quot;Daily&quot; quando il valore è 24 e &quot;Weekly&quot; quando è 168. |

### Codici di risposta {#response-codes-get-settings}

| Stato | Significato |
|---|---|
| 200 | La richiesta è riuscita. La risposta contiene le impostazioni di abbonamento alla bacheca a livello di account. |
| 400 | Errore generico di richiesta non valida. |
| 401 | Nella richiesta mancano credenziali valide oppure l&#39;accesso è stato negato a causa di credenziali non valide. |

### Utilizza questa API nell’integrazione {#integration-get-settings}

Un caso d&#39;uso comune è una schermata delle preferenze di notifica che mostra come le e-mail di iscrizione alla bacheca sono configurate per l&#39;account.

1. Quando viene caricata la schermata delle preferenze di notifica dell&#39;applicazione, chiama `GET /boardSubscriptionSettings`.
1. Mostra i tipi di attività che attivano una notifica e la frequenza con cui viene inviata l’e-mail di riepilogo, utilizzando i valori nella risposta.

## API per recuperare i sottoscrittori della bacheca {#api-get-subscribers}

### Scopo dell’API {#purpose-get-subscribers}

Recupera l’elenco degli utenti iscritti a una bacheca specifica. Gli utenti iscritti a una bacheca vengono informati delle nuove attività in essa svolte. Questa API restituisce gli utenti attualmente iscritti a una determinata bacheca, insieme ai dettagli su quando e da chi è stata creata ciascuna sottoscrizione.

Utilizza questa API per visualizzare un elenco di sottoscrittori nell’applicazione, per controllare chi riceve gli aggiornamenti per una bacheca o per sincronizzare i dati di abbonamento della bacheca con un sistema esterno.

La risposta viene impaginata. Utilizzare i parametri di query `page[offset]` e `page[limit]` per spostarsi tra elenchi di sottoscrittori di grandi dimensioni. I dati restituiti sono soggetti alle autorizzazioni dell’utente chiamante sulla bacheca richiesta.

### Endpoint {#endpoint-get-subscribers}

```http
GET /primeapi/v2/boards/{id}/subscribers
```

| Proprietà | Valore |
|---|---|
| Ambito | `admin:read` |
| Formato di risposta | `application/vnd.api+json;charset=UTF-8` |

### Parametri {#parameters-get-subscribers}

| Parametro | In | Necessario | Predefinito | Descrizione |
|---|---|---|---|---|
| `id` | percorso | Sì | N/D | ID della bacheca di cui si desidera recuperare i sottoscrittori. L&#39;accesso è soggetto alle autorizzazioni del chiamante sulla bacheca. |
| `page[offset]` | query | No | 0 | Posizione iniziale dei record da restituire. |
| `page[limit]` | query | No | 10 | Numero di sottoscrittori da restituire per pagina. Il valore massimo consentito è 200. |

### Richiesta di esempio {#example-request-get-subscribers}

```bash
curl -X GET \
--header 'Accept: application/vnd.api+json' \
--header 'Authorization: oauth <access-token>' \
'https://learningmanager.adobe.com/primeapi/v2/boards/1234/subscribers?page[offset]=0&page[limit]=50'
```

### Esempio di risposta - 200 OK {#example-response-get-subscribers}

```json
{
  "data": [
    {
      "id": "1234:5678",
      "type": "boardSubscriber",
      "attributes": {
        "boardId": 1234,
        "dateSubscribed": 1757000000000,
        "subscribedByUserId": 5678,
        "user": {
          "id": "5678",
          "name": "Jane Doe",
          "email": "jane.doe@example.com",
          "avatarUrl": "https://example.com/avatars/5678.png",
          "bio": "Learning enthusiast",
          "contentLocale": "en-US",
          "uiLocale": "en-US",
          "timeZoneCode": "PST",
          "userType": "INTERNAL",
          "state": "ACTIVE",
          "profile": "Learner",
          "roles": ["Learner"],
          "gamificationEnabled": true,
          "pointsEarned": 120,
          "pointsRedeemed": 20,
          "enrollOnClick": true,
          "preferredResolution": "720p",
          "lastLoginDate": "2026-09-23T18:12:04.000Z"
        }
      }
    }
  ]
}
```

### Schema risorsa {#resource-schema-get-subscribers}

La risposta include una nuova risorsa, `boardSubscriber`. Gli attributi includono `boardId`, `dateSubscribed`, `subscribedByUserId` e `user`. L’oggetto utente incorporato contiene informazioni sul sottoscrittore, come ID utente, nome, e-mail, profilo e ruoli e altri metadati utente.

**`boardSubscriber`attributi**

| Campo | Tipo | Descrizione |
|---|---|---|
| `id` | stringa | ID sottoscrizione opaco. |
| `type` | stringa | Tipo di risorsa. |
| `boardId` | numero | ID della bacheca a cui è iscritto l’utente. |
| `dateSubscribed` | numero | Data e ora dell’iscrizione dell’utente alla bacheca. |
| `subscribedByUserId` | numero | ID dell&#39;utente che ha creato la sottoscrizione. |
| `user` | oggetto | Dettagli dell’utente iscritto (incorporato, vedi di seguito). |

**`user`(incorporato, all&#39;interno di un sottoscrittore)**

| Campo | Tipo | Descrizione |
|---|---|---|
| `id` | stringa | ID utente opaco. |
| `name` | stringa | Nome visualizzato dell&#39;utente. |
| `email` | stringa | Indirizzo e-mail dell’utente. |
| `avatarUrl` | stringa | URL dell&#39;immagine del profilo utente. |
| `bio` | stringa | Breve biografia dell&#39;utente. |
| `binUserId` | stringa | Identificatore interno dell’utente. |
| `userUniqueId` | stringa | Identificatore univoco dell’utente nell’account. |
| `userType` | stringa | Tipo di utente, ad esempio interno o esterno. |
| `state` | stringa | Stato corrente dell&#39;account utente. |
| `profile` | stringa | Profilo assegnato all&#39;utente. |
| `roles` | matrice di stringhe | Ruoli mantenuti dall&#39;utente. |
| `contentLocale` | stringa | Impostazioni internazionali in cui l&#39;utente preferisce visualizzare il contenuto. |
| `uiLocale` | stringa | Impostazioni internazionali utilizzate per l&#39;interfaccia utente. |
| `timeZoneCode` | stringa | Fuso orario configurato per l&#39;utente. |
| `preferredResolution` | stringa | Risoluzione video preferita dall’utente. |
| `enrollOnClick` | booleano | Se l’utente viene iscritto automaticamente alla selezione di un oggetto di apprendimento. |
| `gamificationEnabled` | booleano | Se la gamification è abilitata per l’utente. |
| `pointsEarned` | numero | Punti di gamification totali guadagnati dall’utente. |
| `pointsRedeemed` | numero | Punti di gamification totali riscattati dall&#39;utente. |
| `lastLoginDate` | stringa | Data e ora dell&#39;ultimo accesso dell&#39;utente. |
| `fields` | oggetto | Campi utente personalizzati e relativi valori. |
| `metadata` | oggetto | Metadati aggiuntivi associati all’utente. |

### Codici di risposta {#response-codes-get-subscribers}

| Stato | Significato |
|---|---|
| 200 | La richiesta è riuscita. La risposta contiene gli abbonati della bacheca. |
| 400 | Errore generico di richiesta non valida. Ad esempio, l’ID della bacheca o un valore di paginazione non è valido. |
| 401 | Nella richiesta mancano credenziali valide oppure l&#39;accesso è stato negato a causa di credenziali non valide. |

### Utilizza questa API nell’integrazione {#integration-get-subscribers}

Un caso di utilizzo comune è una visualizzazione per amministratori o moderatori che mostra tutti coloro che ricevono aggiornamenti per una bacheca.

1. Quando la visualizzazione viene caricata, chiamare questo endpoint con l&#39;ID della bacheca e un valore `page[limit]` adatto al layout (fino a 200).
1. Visualizzare i valori `user.name`, `user.email` e `dateSubscribed` per ogni sottoscrittore.
1. Se il numero di record restituiti è uguale a `page[limit]`, è possibile che siano presenti più sottoscrittori. Chiamare nuovamente l&#39;endpoint, aumentando `page[offset]` in base alle dimensioni della pagina, fino a quando una pagina restituisce un numero di record inferiore a quello richiesto.

## API per iscrivere gli utenti a una bacheca {#api-subscribe-users}

### Scopo dell’API {#purpose-subscribe-users}

Sottoscrivere uno o più utenti a un&#39;area discussioni in modo che ricevano i relativi messaggi di posta elettronica di riepilogo. Identifica gli utenti tramite l&#39;ID utente, l&#39;indirizzo e-mail (risolto negli ID utente all&#39;interno dell&#39;account) o entrambi. Puoi aggiungere più utenti in una singola richiesta. Vedere [Sottoscrizioni in modalità collettiva](#bulk-subscriptions).

### Endpoint {#endpoint-subscribe-users}

```http
POST /primeapi/v2/boards/{id}/subscribers
```

| Proprietà | Valore |
|---|---|
| Ambito | `admin:write` |
| Formato richiesta | `application/vnd.api+json;charset=UTF-8` |
| Formato di risposta | `application/vnd.api+json;charset=UTF-8` |

### Parametri {#parameters-subscribe-users}

| Parametro | In | Necessario | Descrizione |
|---|---|---|---|
| `id` | percorso | Sì | ID della bacheca a cui sottoscrivere gli utenti. |

### Corpo della richiesta {#request-body-subscribe-users}

Inviare gli utenti come attributi di una risorsa `boardSubscriberBulkRequest`. È necessario almeno uno di `userIds` o `emails`.

| Campo | Tipo | Descrizione |
|---|---|---|
| `data.attributes.userIds` | matrice di numeri | ID degli utenti a cui effettuare la sottoscrizione. |
| `data.attributes.emails` | matrice di stringhe | Gli indirizzi e-mail degli utenti a cui si desidera effettuare la sottoscrizione. Ogni indirizzo viene risolto in un ID utente all’interno dell’account. |

### Richiesta di esempio {#example-request-subscribe-users}

```bash
curl -X POST \
--header 'Content-Type: application/vnd.api+json;charset=UTF-8' \
--header 'Accept: application/vnd.api+json' \
--header 'Authorization: oauth <access-token>' \
-d '{
  "data": {
    "type": "boardSubscriberBulkRequest",
    "attributes": {
      "userIds": [
        1234,
        5678
      ],
      "emails": [
        "abc@xyz.com"
      ]
    }
  }
}' \
'https://learningmanager.adobe.com/primeapi/v2/boards/1010/subscribers'
```

### Esempio di risposta: 207 Multi-Status {#example-response-subscribe-users}

```json
{
  "added": [
    {
      "userId": "12345",
      "status": "SUCCESS"
    }
  ],
  "failed": [
    {
      "userId": "78910",
      "errorCode": "NO_BOARD_ACCESS"
    }
  ]
}
```

**Attributi di risposta**

| Campo | Tipo | Descrizione |
|---|---|---|
| `added` | matrice | Utenti sottoscritti. Ogni voce ha un `userId` e un `status`. Gli utenti che erano già abbonati vengono segnalati qui come successi. |
| `failed` | matrice | Gli utenti che non hanno ricevuto la sottoscrizione. Ogni voce ha un `userId` e un `errorCode`, ad esempio `NO_BOARD_ACCESS`. |

### Codici di risposta {#response-codes-subscribe-users}

| Stato | Significato |
|---|---|
| 207 | Stato multiplo. La richiesta è stata elaborata e la risposta elenca il risultato per ogni utente in `added` e `failed`. |
| 400 | Errore generico di richiesta non valida. |
| 401 | Nella richiesta mancano credenziali valide oppure l&#39;accesso è stato negato a causa di credenziali non valide. |
| 404 | Impossibile trovare la risorsa richiesta, ad esempio la bacheca. |
| 409 | La bacheca è inattiva, eliminata o ritirata, quindi l’intera richiesta viene rifiutata. |

### Abbonamenti in blocco {#bulk-subscriptions}

Utilizza l’abbonamento in blocco per aggiungere più utenti a un’area discussioni in un’unica richiesta. L’abbonamento in blocco consente di ridurre il numero di chiamate API necessarie per gestire i sottoscrittori. È utile quando:

* Un istruttore gestisce più coorti.
* Un manager di coorte ha bisogno di accedere a molte aree discussioni.
* Un sistema esterno sincronizza le sottoscrizioni delle bacheche in batch.
* Durante la creazione della coorte è necessario che siano presenti più istruttori.

#### Comportamento di aggiunta in blocco

Una richiesta in blocco può contenere ID utente, indirizzi e-mail o una combinazione di entrambi. Ogni utente viene elaborato in modo indipendente.

#### Comportamento ipopotente

L’aggiunta in blocco è ideale. Se un utente è già iscritto alla bacheca, la richiesta ha esito positivo, non viene creato alcun abbonamento duplicato e l’abbonamento esistente rimane invariato. Ciò consente ai client di ritentare le richieste in modo sicuro.

#### Completamento parziale

Alcuni utenti possono essere sottoscritti mentre altri non riescono a convalidare. L&#39;operazione non ha esito negativo perché uno o più utenti non sono validi.

| Maiuscole/minuscole | Risultato |
|---|---|
| L’utente esiste e ha accesso alla bacheca | Operazione completata |
| L&#39;utente è già iscritto | Operazione completata |
| L’utente non ha accesso alla bacheca | Errore (`NO_BOARD_ACCESS`) |
| Utente inesistente | Errore |
| L&#39;utente è inattivo | Errore |
| L&#39;utente è stato eliminato | Errore |

#### Formato di risposta

La sottoscrizione bulk restituisce HTTP 207 Multi-Status con un risultato `added` e un risultato `failed` per ogni utente, come indicato nella [risposta di esempio](#example-response-subscribe-users).

#### Errori di convalida comuni

* **L&#39;utente non ha accesso alla bacheca.** Se un utente non ha visibilità sulla bacheca, `NO_BOARD_ACCESS` viene restituito per tale utente. Gli altri utenti continuano a essere elaborati normalmente.
* **La bacheca è inattiva, eliminata o ritirata.** Se la bacheca non è idonea per gli abbonamenti, la richiesta viene rifiutata con conflitto HTTP 409.
* **Utente non valido.** Se un account utente non esiste, è inattivo o è stato eliminato, l&#39;operazione restituisce una voce di errore per l&#39;utente.

## API per annullare l’iscrizione di un utente a una bacheca {#api-unsubscribe-user}

### Scopo dell’API {#purpose-unsubscribe-user}

Annullare l&#39;iscrizione di un utente a un&#39;area discussioni. Dopo la rimozione dell’abbonamento, l’utente non riceve più notifiche ed e-mail di riepilogo per quella bacheca.

### Endpoint {#endpoint-unsubscribe-user}

```http
DELETE /primeapi/v2/boards/{id}/subscribers/{userId}
```

| Proprietà | Valore |
|---|---|
| Ambito | `admin:write` |
| Formato di risposta | `application/vnd.api+json;charset=UTF-8` |

### Parametri {#parameters-unsubscribe-user}

| Parametro | In | Necessario | Descrizione |
|---|---|---|---|
| `id` | percorso | Sì | ID della bacheca. |
| `userId` | percorso | Sì | ID dell&#39;utente di cui annullare la sottoscrizione. |

### Richiesta di esempio {#example-request-unsubscribe-user}

```bash
curl -X DELETE \
--header 'Accept: application/vnd.api+json' \
--header 'Authorization: oauth <access-token>' \
'https://learningmanager.adobe.com/primeapi/v2/boards/1234/subscribers/5678'
```

### Esempio di risposta - 204 Nessun contenuto {#example-response-unsubscribe-user}

La risposta è priva di corpo.

### Codici di risposta {#response-codes-unsubscribe-user}

| Stato | Significato |
|---|---|
| 204 | La richiesta è riuscita. L’utente non è più iscritto alla bacheca. |
| 400 | Errore generico di richiesta non valida. |
| 401 | Nella richiesta mancano credenziali valide oppure l&#39;accesso è stato negato a causa di credenziali non valide. |
| 404 | Impossibile trovare la risorsa richiesta, ad esempio la bacheca o la sottoscrizione. |

## Ordinamento delle API dei segnalibri e gestione dei contenuti ritirati

### Scopo dell’API

Gli Allievi aggiungono un segnalibro ai corsi di formazione che desiderano rivisitare. Prima di questa modifica, le API dei segnalibri non restituivano segnalibri in un ordine particolare. Le integrazioni, in particolare le implementazioni headless, non sono riuscite a visualizzare prima gli ultimi segnalibri salvati. Gli allievi con molti segnalibri dovevano scorrere gli elementi più vecchi per trovare quelli più recenti.

I segnalibri relativi agli oggetti di apprendimento ritirati sono rimasti nell’elenco. Selezionandone una si verifica un errore di tipo &quot;Pagina non trovata&quot;.

Questa modifica migliora le API dei segnalibri in due modi:

* I segnalibri vengono restituiti in ordine cronologico, a partire dai più recenti.
* I segnalibri per gli oggetti di apprendimento ritirati non vengono più restituiti.

Non vengono introdotti nuovi endpoint, parametri o attributi di risposta. Le integrazioni esistenti continuano a funzionare senza modifiche.

### URL di base e convenzioni

Le API dei segnalibri utilizzano il percorso di base e le convenzioni seguenti:

| Elemento | Valore |
|---|---|
| Percorso di base | `/primeapi/v2` |
| Tipo di contenuto | `application/vnd.api+json` |
| Autenticazione | Token OAuth con accesso in lettura da parte dell’Allievo |
| Ordine predefinito | Prima il segnalibro più recente |
| Nuovi parametri | Nessuno |
| Struttura della risposta | Invariato |

### Endpoint

#### Endpoint che restituiscono segnalibri

I seguenti endpoint restituiscono segnalibri nel nuovo ordine:

| Endpoint | Restituisce |
|---|---|
| `GET /primeapi/v2/learningObjects?filter.bookmarks=true` | Oggetti di apprendimento contrassegnati con segnalibro per l’Allievo |
| `GET /primeapi/v2/bookmarks` | Segnalibri dell’Allievo |

#### Ordinare gli oggetti di apprendimento con segnalibro

`GET /primeapi/v2/learningObjects?filter.bookmarks=true`

<!-- Content Review by Claude: Please confirm the endpoint list. The dev-to-QE hand-off confirms ordering for GET /learningObjects?filter.bookmarks=true. The PRD (ALMER-442) also lists GET /primeapi/v2/bookmarks. Please also confirm the OAuth scope. -->

Restituisce gli oggetti di apprendimento contrassegnati dall’Allievo chiamante. L&#39;ultimo elemento contrassegnato con segnalibro è il primo e il meno recente è l&#39;ultimo.

**Ambito:** Accesso in lettura da parte dell’Allievo

L&#39;endpoint accetta il seguente parametro di query:

| Parametro | In | Necessario | Descrizione |
|---|---|---|---|
| `filter.bookmarks` | query | Sì | Imposta su `true` per restituire solo gli oggetti di apprendimento contrassegnati dall’Allievo |

**Richiesta di esempio**

```http
GET /primeapi/v2/learningObjects?filter.bookmarks=true
Accept: application/vnd.api+json
Authorization: oauth <access-token>
```

**Esempio di risposta 200 OK**

L’Allievo ha aggiunto un segnalibro al documento Getting Started with Adobe Analytics first, Building Workspace Projects second e Advanced Segmentation in Adobe Analytics last. La risposta elenca i dati da più recenti a meno recenti. Altri attributi vengono omessi per brevità.

```json
{
  "data": [
    {
      "id": "course:2400162",
      "type": "learningObject",
      "attributes": {
        "name": "Advanced Segmentation in Adobe Analytics"
      }
    },
    {
      "id": "course:2400160",
      "type": "learningObject",
      "attributes": {
        "name": "Building Workspace Projects"
      }
    },
    {
      "id": "course:2400159",
      "type": "learningObject",
      "attributes": {
        "name": "Getting Started with Adobe Analytics"
      }
    }
  ]
}
```

>[!NOTE]
>
>Il nuovo ordine è il comportamento predefinito e si applica a tutti gli account.

### Ordinamento segnalibri

#### Ordinamento dei segnalibri

I segnalibri vengono ordinati in base alla data in cui l’Allievo li ha salvati, dalla più recente alla meno recente. Ad esempio, se un Allievo appone un segnalibro al corso A, quindi al corso B e infine al corso C, la risposta elenca prima il corso C, poi il corso B e infine il corso A.

Se un LO contrassegnato con segnalibro che appare alla decima posizione, ad esempio, è &quot;non salvato&quot; e successivamente nuovamente contrassegnato con segnalibro, verrà visualizzato come segnalibro recente e all&#39;inizio nell&#39;elenco.

Le integrazioni che in precedenza ordinavano i segnalibri sul client possono rimuovere tale logica e visualizzare i risultati nell’ordine restituito.

### Gestione dei contenuti ritirati

#### Come vengono gestiti gli oggetti di apprendimento ritirati

I segnalibri relativi agli oggetti di apprendimento ritirati non vengono restituiti nella risposta, indipendentemente dal fatto che l’Allievo sia iscritto o meno all’oggetto di apprendimento.

Gli oggetti di apprendimento ritirati contrassegnati da segnalibro non verranno visualizzati a meno che l’Allievo non vi sia iscritto.

Gli allievi non visualizzano più i segnalibri che generano l’errore &quot;Pagina non trovata&quot;. Il segnalibro è nascosto dai risultati, non eliminato.

### Compatibilità

Questa modifica non interrompe i consumer API esistenti:

* I punti finali e i relativi parametri rimangono invariati.
* La struttura della risposta rimane invariata e non viene aggiunto né rimosso alcun attributo.
* Solo l’ordine dei risultati e l’esclusione degli oggetti di apprendimento ritirati differiscono dai comportamenti precedenti.

### Utilizza questa API nell’integrazione

Un caso di utilizzo comune è un elenco &quot;Salvato per versioni successive&quot; in un’esperienza di apprendimento headless. Si desidera che gli allievi vedano prima i segnalibri più recenti, senza collegamenti a contenuti ritirati.

1. Chiama `GET /primeapi/v2/learningObjects?filter.bookmarks=true` quando l’Allievo apre l’elenco.
2. Visualizza gli oggetti di apprendimento nell’ordine restituito. Il primo elemento è l&#39;ultimo segnalibro.
3. Rimuovi qualsiasi ordinamento sul lato client o filtro dei contenuti ritirati aggiunto come soluzione alternativa.
4. Mostra un conteggio dei segnalibri utilizzando il numero di elementi nella risposta. I segnalibri per gli oggetti di apprendimento ritirati non sono più inclusi.

### Supporto API per istanze con più iscrizioni nel widget Conformità allievi nell’app per allievi

L’API pubblica supporta questo comportamento tramite un parametro di query opzionale sull’endpoint di registrazione esistente. Se ometti il parametro, l’API restituisce gli stessi risultati di prima, in modo che le integrazioni esistenti, incluse le implementazioni headless, continuino a funzionare senza modifiche.

**Endpoint**

GET /primeapi/v2/enrollments

**Parametro query**

includeMultiInstanceEnrollments (facoltativo)

**Query**

https://learningmanagerstage1.adobe.com/primeapi/v2/enrollments?page\[limit\]=10&filter.loTypes=course&includeHierarchicalEnrollments=false&includeMultiInstanceEnrollments=true&sort=dateEnrolled

**Valore**

vero. Impostazione predefinita: False.

**Corpo della risposta**

&lbrace;

&quot;links&quot;: &lbrace;

&quot;self&quot;: &quot;[https://learningmanagerstage1.adobe.com/primeapi/v2/enrollments?page\[limit\]=10&amp;filter.loTypes=course&amp;sort=dateEnrolled&amp;includeHierarchicalEnrollments=false&amp;includeMultiInstanceEnrollments=true](https://learningmanagerstage1.adobe.com/primeapi/v2/enrollments?page%5blimit%5d=10&filter.loTypes=course&sort=dateEnrolled&includeHierarchicalEnrollments=false&includeMultiInstanceEnrollments=true)&quot;,

&quot;avanti&quot;: &quot;[https://learningmanagerstage1.adobe.com/primeapi/v2/enrollments?page\[limit\]=10&amp;filter.loTypes=course&amp;sort=dateEnrolled&amp;includeHierarchicalEnrollments=false&amp;includeMultiInstanceEnrollments=true&amp;page\[cursor\]=eyJjb3Vyc2VNdWx0aSI6MCwiam9iQWlkIjowLCJjb3Vyc2UiOjEwLCJsZWFybmluZ1Byb2ZdyYas0iYi&quot;](https://learningmanagerstage1.adobe.com/primeapi/v2/enrollments?page%5blimit%5d=10&filter.loTypes=course&sort=dateEnrolled&includeHierarchicalEnrollments=false&includeMultiInstanceEnrollments=true&page%5bcursor%5d=eyJjb3Vyc2VNdWx0aSI6MCwiam9iQWlkIjowLCJjb3Vyc2UiOjEwLCJsZWFybmluZ1Byb2dyYW0iOjAsImNlcnRpZmljYXRpb24iOjB9)

&rbrace;,

&quot;data&quot;: \&lbrack;

&lbrace;

&quot;id&quot;: &quot;course:15067_30122_3400468&quot;,

&quot;type&quot;: &quot;learningObjectInstanceEnrollment&quot;,

&quot;attributes&quot;: &lbrace;

&quot;completionDeadline&quot;: &quot;2026-02-24T10:50:45.000Z&quot;,

&quot;enrollmentSource&quot;: &quot;MGR_APPROVAL&quot;,

&quot;hasPassed&quot;: false,

&quot;progressPercent&quot;: 0,

&quot;score&quot;: 0,

&quot;state&quot;: &quot;PENDING_APPROVAL&quot;

&rbrace;,

&quot;relations&quot;: &lbrace;

&quot;Allievo&quot;: &lbrace;

&quot;data&quot;: &lbrace;

&quot;id&quot;: &quot;3400468&quot;,

&quot;type&quot;: &quot;user&quot;

&rbrace;

&rbrace;,

&quot;learningObject&quot;: &lbrace;

&quot;data&quot;: &lbrace;

&quot;id&quot;: &quot;course:15067&quot;,

&quot;type&quot;: &quot;learningObject&quot;

&rbrace;

&rbrace;,

&quot;loInstance&quot;: &lbrace;

&quot;data&quot;: &lbrace;

&quot;id&quot;: &quot;course:15067_30122&quot;,

&quot;type&quot;: &quot;learningObjectInstance&quot;

&rbrace;

&rbrace;,

&quot;loResourceGrades&quot;: &lbrace;

&quot;data&quot;: \&lbrack;

&lbrace;

&quot;id&quot;: &quot;course:15067_30122_41715_1_3400468&quot;,

&quot;type&quot;: &quot;learningObjectResourceGrade&quot;

&rbrace;

\&rbrack;

&rbrace;

&rbrace;

&rbrace;,

&lbrace;

&quot;id&quot;: &quot;course:1108800_1997400_3400468&quot;,

&quot;type&quot;: &quot;learningObjectInstanceEnrollment&quot;,

&quot;attributes&quot;: &lbrace;

&quot;enrollmentSource&quot;: &quot;SELF_ENROLL&quot;,

&quot;hasPassed&quot;: false,

&quot;progressPercent&quot;: 0,

&quot;score&quot;: 0,

&quot;state&quot;: &quot;PENDING_APPROVAL&quot;

&rbrace;,

&quot;relations&quot;: &lbrace;

&quot;Allievo&quot;: &lbrace;

&quot;data&quot;: &lbrace;

&quot;id&quot;: &quot;3400468&quot;,

&quot;type&quot;: &quot;user&quot;

&rbrace;

&rbrace;,

&quot;learningObject&quot;: &lbrace;

&quot;data&quot;: &lbrace;

&quot;id&quot;: &quot;course:1108800&quot;,

&quot;type&quot;: &quot;learningObject&quot;

&rbrace;

&rbrace;,

&quot;loInstance&quot;: &lbrace;

&quot;data&quot;: &lbrace;

&quot;id&quot;: &quot;course:1108800_1997400&quot;,

&quot;type&quot;: &quot;learningObjectInstance&quot;

&rbrace;

&rbrace;,

&quot;loResourceGrades&quot;: &lbrace;

&quot;data&quot;: \&lbrack;

&lbrace;

&quot;id&quot;: &quot;course:1108800_1997400_2174574_0_3400468&quot;,

&quot;type&quot;: &quot;learningObjectResourceGrade&quot;

&rbrace;

\&rbrack;

&rbrace;

&rbrace;

&rbrace;,

&lbrace;

&quot;id&quot;: &quot;course:2027668_3707328_3400468&quot;,

&quot;type&quot;: &quot;learningObjectInstanceEnrollment&quot;,

&quot;attributes&quot;: &lbrace;

&quot;enrollmentSource&quot;: &quot;MGR_APPROVAL&quot;,

&quot;hasPassed&quot;: false,

&quot;progressPercent&quot;: 0,

&quot;score&quot;: 0,

&quot;state&quot;: &quot;PENDING_APPROVAL&quot;

&rbrace;,

&quot;relations&quot;: &lbrace;

&quot;Allievo&quot;: &lbrace;

&quot;data&quot;: &lbrace;

&quot;id&quot;: &quot;3400468&quot;,

&quot;type&quot;: &quot;user&quot;

&rbrace;

&rbrace;,

&quot;learningObject&quot;: &lbrace;

&quot;data&quot;: &lbrace;

&quot;id&quot;: &quot;course:2027668&quot;,

&quot;type&quot;: &quot;learningObject&quot;

&rbrace;

&rbrace;,

&quot;loInstance&quot;: &lbrace;

&quot;data&quot;: &lbrace;

&quot;id&quot;: &quot;course:2027668_3707328&quot;,

&quot;type&quot;: &quot;learningObjectInstance&quot;

&rbrace;

&rbrace;,

&quot;loResourceGrades&quot;: &lbrace;

&quot;data&quot;: \&lbrack;

&lbrace;

&quot;id&quot;: &quot;course:2027668_3707328_2665897_0_3400468&quot;,

&quot;type&quot;: &quot;learningObjectResourceGrade&quot;

&rbrace;

\&rbrack;

&rbrace;

&rbrace;

&rbrace;,

&lbrace;

&quot;id&quot;: &quot;course:2030067_3709862_3400468&quot;,

&quot;type&quot;: &quot;learningObjectInstanceEnrollment&quot;,

&quot;attributes&quot;: &lbrace;

&quot;enrollmentSource&quot;: &quot;MGR_APPROVAL&quot;,

&quot;hasPassed&quot;: false,

&quot;progressPercent&quot;: 0,

&quot;score&quot;: 0,

&quot;state&quot;: &quot;PENDING_APPROVAL&quot;

&rbrace;,

&quot;relations&quot;: &lbrace;

&quot;Allievo&quot;: &lbrace;

&quot;data&quot;: &lbrace;

&quot;id&quot;: &quot;3400468&quot;,

&quot;type&quot;: &quot;user&quot;

&rbrace;

&rbrace;,

&quot;learningObject&quot;: &lbrace;

&quot;data&quot;: &lbrace;

&quot;id&quot;: &quot;course:2030067&quot;,

&quot;type&quot;: &quot;learningObject&quot;

&rbrace;

&rbrace;,

&quot;loInstance&quot;: &lbrace;

&quot;data&quot;: &lbrace;

&quot;id&quot;: &quot;course:2030067_3709862&quot;,

&quot;type&quot;: &quot;learningObjectInstance&quot;

&rbrace;

&rbrace;,

&quot;loResourceGrades&quot;: &lbrace;

&quot;data&quot;: \&lbrack;

&lbrace;

&quot;id&quot;: &quot;course:2030067_3709862_2668467_0_3400468&quot;,

&quot;type&quot;: &quot;learningObjectResourceGrade&quot;

&rbrace;

\&rbrack;

&rbrace;

&rbrace;

&rbrace;,

&lbrace;

&quot;id&quot;: &quot;course:3081896_5749155_3400468&quot;,

&quot;type&quot;: &quot;learningObjectInstanceEnrollment&quot;,

&quot;attributes&quot;: &lbrace;

&quot;enrollmentSource&quot;: &quot;MGR_APPROVAL&quot;,

&quot;hasPassed&quot;: false,

&quot;progressPercent&quot;: 0,

&quot;score&quot;: 0,

&quot;state&quot;: &quot;PENDING_APPROVAL&quot;

&rbrace;,

&quot;relations&quot;: &lbrace;

&quot;Allievo&quot;: &lbrace;

&quot;data&quot;: &lbrace;

&quot;id&quot;: &quot;3400468&quot;,

&quot;type&quot;: &quot;user&quot;

&rbrace;

&rbrace;,

&quot;learningObject&quot;: &lbrace;

&quot;data&quot;: &lbrace;

&quot;id&quot;: &quot;course:3081896&quot;,

&quot;type&quot;: &quot;learningObject&quot;

&rbrace;

&rbrace;,

&quot;loInstance&quot;: &lbrace;

&quot;data&quot;: &lbrace;

&quot;id&quot;: &quot;course:3081896_5749155&quot;,

&quot;type&quot;: &quot;learningObjectInstance&quot;

&rbrace;

&rbrace;,

&quot;loResourceGrades&quot;: &lbrace;

&quot;data&quot;: \&lbrack;

&lbrace;

&quot;id&quot;: &quot;course:3081896_5749155_3737554_0_3400468&quot;,

&quot;type&quot;: &quot;learningObjectResourceGrade&quot;

&rbrace;,

&lbrace;

&quot;id&quot;: &quot;course:3081896_5749155_3737555_0_3400468&quot;,

&quot;type&quot;: &quot;learningObjectResourceGrade&quot;

&rbrace;

\&rbrack;

&rbrace;

&rbrace;

&rbrace;,

&lbrace;

&quot;id&quot;: &quot;course:2037893_3717940_3400468&quot;,

&quot;type&quot;: &quot;learningObjectInstanceEnrollment&quot;,

&quot;attributes&quot;: &lbrace;

&quot;enrollmentSource&quot;: &quot;MGR_APPROVAL&quot;,

&quot;hasPassed&quot;: false,

&quot;progressPercent&quot;: 0,

&quot;score&quot;: 0,

&quot;state&quot;: &quot;PENDING_APPROVAL&quot;

&rbrace;,

&quot;relations&quot;: &lbrace;

&quot;Allievo&quot;: &lbrace;

&quot;data&quot;: &lbrace;

&quot;id&quot;: &quot;3400468&quot;,

&quot;type&quot;: &quot;user&quot;

&rbrace;

&rbrace;,

&quot;learningObject&quot;: &lbrace;

&quot;data&quot;: &lbrace;

&quot;id&quot;: &quot;course:2037893&quot;,

&quot;type&quot;: &quot;learningObject&quot;

&rbrace;

&rbrace;,

&quot;loInstance&quot;: &lbrace;

&quot;data&quot;: &lbrace;

&quot;id&quot;: &quot;course:2037893_3717940&quot;,

&quot;type&quot;: &quot;learningObjectInstance&quot;

&rbrace;

&rbrace;,

&quot;loResourceGrades&quot;: &lbrace;

&quot;data&quot;: \&lbrack;

&lbrace;

&quot;id&quot;: &quot;course:2037893_3717940_3676856_0_3400468&quot;,

&quot;type&quot;: &quot;learningObjectResourceGrade&quot;

&rbrace;

\&rbrack;

&rbrace;

&rbrace;

&rbrace;,

&lbrace;

&quot;id&quot;: &quot;course:3049434_5713130_3400468&quot;,

&quot;type&quot;: &quot;learningObjectInstanceEnrollment&quot;,

&quot;attributes&quot;: &lbrace;

&quot;completionDeadline&quot;: &quot;2020-05-05T18:29:59.000Z&quot;,

&quot;enrollmentSource&quot;: &quot;MGR_APPROVAL&quot;,

&quot;hasPassed&quot;: false,

&quot;progressPercent&quot;: 0,

&quot;score&quot;: 0,

&quot;state&quot;: &quot;PENDING_APPROVAL&quot;

&rbrace;,

&quot;relations&quot;: &lbrace;

&quot;Allievo&quot;: &lbrace;

&quot;data&quot;: &lbrace;

&quot;id&quot;: &quot;3400468&quot;,

&quot;type&quot;: &quot;user&quot;

&rbrace;

&rbrace;,

&quot;learningObject&quot;: &lbrace;

&quot;data&quot;: &lbrace;

&quot;id&quot;: &quot;course:3049434&quot;,

&quot;type&quot;: &quot;learningObject&quot;

&rbrace;

&rbrace;,

&quot;loInstance&quot;: &lbrace;

&quot;data&quot;: &lbrace;

&quot;id&quot;: &quot;course:3049434_5713130&quot;,

&quot;type&quot;: &quot;learningObjectInstance&quot;

&rbrace;

&rbrace;,

&quot;loResourceGrades&quot;: &lbrace;

&quot;data&quot;: \&lbrack;

&lbrace;

&quot;id&quot;: &quot;course:3049434_5713130_3693595_0_3400468&quot;,

&quot;type&quot;: &quot;learningObjectResourceGrade&quot;

&rbrace;

\&rbrack;

&rbrace;

&rbrace;

&rbrace;,

&lbrace;

&quot;id&quot;: &quot;course:2001397_3679403_3400468&quot;,

&quot;type&quot;: &quot;learningObjectInstanceEnrollment&quot;,

&quot;attributes&quot;: &lbrace;

&quot;enrollmentSource&quot;: &quot;MGR_APPROVAL&quot;,

&quot;hasPassed&quot;: false,

&quot;progressPercent&quot;: 0,

&quot;score&quot;: 0,

&quot;state&quot;: &quot;PENDING_APPROVAL&quot;

&rbrace;,

&quot;relations&quot;: &lbrace;

&quot;Allievo&quot;: &lbrace;

&quot;data&quot;: &lbrace;

&quot;id&quot;: &quot;3400468&quot;,

&quot;type&quot;: &quot;user&quot;

&rbrace;

&rbrace;,

&quot;learningObject&quot;: &lbrace;

&quot;data&quot;: &lbrace;

&quot;id&quot;: &quot;course:2001397&quot;,

&quot;type&quot;: &quot;learningObject&quot;

&rbrace;

&rbrace;,

&quot;loInstance&quot;: &lbrace;

&quot;data&quot;: &lbrace;

&quot;id&quot;: &quot;course:2001397_3679403&quot;,

&quot;type&quot;: &quot;learningObjectInstance&quot;

&rbrace;

&rbrace;,

&quot;loResourceGrades&quot;: &lbrace;

&quot;data&quot;: \&lbrack;

&lbrace;

&quot;id&quot;: &quot;course:2001397_3679403_2635974_0_3400468&quot;,

&quot;type&quot;: &quot;learningObjectResourceGrade&quot;

&rbrace;

\&rbrack;

&rbrace;

&rbrace;

&rbrace;,

&lbrace;

&quot;id&quot;: &quot;course:2037862_3717900_3400468&quot;,

&quot;type&quot;: &quot;learningObjectInstanceEnrollment&quot;,

&quot;attributes&quot;: &lbrace;

&quot;enrollmentSource&quot;: &quot;MGR_APPROVAL&quot;,

&quot;hasPassed&quot;: false,

&quot;progressPercent&quot;: 0,

&quot;score&quot;: 0,

&quot;state&quot;: &quot;PENDING_APPROVAL&quot;

&rbrace;,

&quot;relations&quot;: &lbrace;

&quot;Allievo&quot;: &lbrace;

&quot;data&quot;: &lbrace;

&quot;id&quot;: &quot;3400468&quot;,

&quot;type&quot;: &quot;user&quot;

&rbrace;

&rbrace;,

&quot;learningObject&quot;: &lbrace;

&quot;data&quot;: &lbrace;

&quot;id&quot;: &quot;course:2037862&quot;,

&quot;type&quot;: &quot;learningObject&quot;

&rbrace;

&rbrace;,

&quot;loInstance&quot;: &lbrace;

&quot;data&quot;: &lbrace;

&quot;id&quot;: &quot;course:2037862_3717900&quot;,

&quot;type&quot;: &quot;learningObjectInstance&quot;

&rbrace;

&rbrace;,

&quot;loResourceGrades&quot;: &lbrace;

&quot;data&quot;: \&lbrack;

&lbrace;

&quot;id&quot;: &quot;course:2037862_3717900_3676816_0_3400468&quot;,

&quot;type&quot;: &quot;learningObjectResourceGrade&quot;

&rbrace;

\&rbrack;

&rbrace;

&rbrace;

&rbrace;,

&lbrace;

&quot;id&quot;: &quot;course:2037837_3717863_3400468&quot;,

&quot;type&quot;: &quot;learningObjectInstanceEnrollment&quot;,

&quot;attributes&quot;: &lbrace;

&quot;completionDeadline&quot;: &quot;2020-02-29T18:29:59.000Z&quot;,

&quot;enrollmentSource&quot;: &quot;SELF_ENROLL&quot;,

&quot;hasPassed&quot;: false,

&quot;progressPercent&quot;: 0,

&quot;score&quot;: 0,

&quot;state&quot;: &quot;OTHER&quot;

&rbrace;,

&quot;relations&quot;: &lbrace;

&quot;Allievo&quot;: &lbrace;

&quot;data&quot;: &lbrace;

&quot;id&quot;: &quot;3400468&quot;,

&quot;type&quot;: &quot;user&quot;

&rbrace;

&rbrace;,

&quot;learningObject&quot;: &lbrace;

&quot;data&quot;: &lbrace;

&quot;id&quot;: &quot;course:2037837&quot;,

&quot;type&quot;: &quot;learningObject&quot;

&rbrace;

&rbrace;,

&quot;loInstance&quot;: &lbrace;

&quot;data&quot;: &lbrace;

&quot;id&quot;: &quot;course:2037837_3717863&quot;,

&quot;type&quot;: &quot;learningObjectInstance&quot;

&rbrace;

&rbrace;,

&quot;loResourceGrades&quot;: &lbrace;

&quot;data&quot;: \&lbrack;

&lbrace;

&quot;id&quot;: &quot;course:2037837_3717863_3597363_0_3400468&quot;,

&quot;type&quot;: &quot;learningObjectResourceGrade&quot;

&rbrace;

\&rbrack;

&rbrace;

&rbrace;

&rbrace;

\&rbrack;

&rbrace;

## Ultima data di accesso per l’iscrizione al percorso di apprendimento {#last-access-date-lp-enrollment}

Adobe Learning Manager consente di archiviare metadati personalizzati, ad esempio la data dell’ultimo accesso, in un’iscrizione a un percorso di apprendimento. I metadati vengono impostati e letti tramite l’API. Ciò consente di tenere traccia dell’accesso in base al tempo ai percorsi di apprendimento assegnati.

## Informazioni sui metadati di iscrizione al percorso di apprendimento

Puoi già impostare la data dell’ultimo accesso per l’iscrizione a un corso tramite API. Questa data controlla per quanto tempo un Allievo può accedere al corso. Le iscrizioni al percorso di apprendimento ora supportano un campo di metadati generico, in modo da poter memorizzare l’ultima data di accesso o qualsiasi altro valore di cui desideri tenere traccia.

Non è necessario attivare il campo o inviare un&#39;intestazione speciale. Il campo è vuoto finché non lo si imposta.

>[!NOTE]
>
>I metadati servono per il tracciamento. Adobe Learning Manager non la aggiorna quando gli Allievi aprono un percorso di apprendimento o i relativi corsi e non controlla l’accesso al percorso di apprendimento. Inoltre, non viene propagato ai corsi nel percorso. Ogni corso mantiene la propria data di ultimo accesso, in modo che i corsi nello stesso percorso possano avere date diverse. Continua a gestire separatamente la scadenza dell’accesso a livello di corso.

### Regole metadati {#metadata-rules}

* Il valore deve essere un oggetto JSON. Una stringa, un numero, un valore Boolean o una matrice restituisce un errore 400 con il messaggio `metadata must be a JSON object`.
* Puoi usare qualsiasi tasto. Adobe Learning Manager non convalida chiavi o valori e non applica un formato di data. Gli esempi in questo articolo utilizzano millisecondi, lo stesso formato delle date del corso.
* Una richiesta PATCH sostituisce l’intero oggetto metadati. Non si fonde con i valori esistenti, pertanto le chiavi escluse vengono rimosse.
* L&#39;impostazione di `"metadata": null` cancella tutti i metadati e restituisce 200.
* Una richiesta con un oggetto `attributes` vuoto o senza una chiave `metadata` lascia invariati i metadati archiviati.
* Quando non è impostato alcun metadati o dopo averlo cancellato, la chiave `metadata` non è presente nella risposta.

## Impostare i metadati su un&#39;iscrizione esistente

Utilizza un token di amministrazione.

Invia una richiesta PATCH all&#39;endpoint seguente, dove `{enrollmentId}` è l&#39;ID di iscrizione al percorso di apprendimento nel formato `learningProgram:<lpId><instanceId><userId>`:

```
PATCH /primeapi/v2/users/{userId}/enrollments/{enrollmentId}
```

Utilizza questo corpo della richiesta:

```json
{
  "data": {
    "id": "<enrollmentId>",
    "type": "learningObjectInstanceEnrollment",
    "attributes": {
      "metadata": {
        "lastAccessDate": 1745337600000
      }
    }
  }
}
```

### Impostare i metadati al momento dell’iscrizione di un Allievo

Utilizza un token di amministrazione.

Invia una richiesta POST con il percorso di apprendimento e gli ID istanza. Includere un oggetto `metadata` facoltativo nel corpo della richiesta.

```
POST /primeapi/v2/users/{userId}/enrollments?loId=<lpId>&loInstanceId=<instanceId>
```

* Se `metadata` non è un oggetto JSON, la richiesta restituisce 400 e l&#39;utente non è iscritto.
* Se l’utente è già iscritto, la richiesta restituisce 200 e non cambia nulla. Per modificare i metadati di una registrazione esistente, utilizzare la richiesta PATCH.
* La risposta non include i metadati. Invia una richiesta di GET per leggerla.

### Recuperare i metadati

È possibile recuperare i metadati con un amministratore o un token Allievo. Le richieste differiscono per tipo di token.

| Token | Ottieni un&#39;iscrizione | Elenca iscrizioni al percorso di apprendimento |
|---|---|---|
| Amministrazione | `GET /primeapi/v2/users/{userId}/enrollments/{enrollmentId}` | `GET /primeapi/v2/users/{userId}/enrollments?filter.loTypes=learningProgram` |
| Allievo | `GET /primeapi/v2/enrollments/{enrollmentId}`<br>`GET /primeapi/v2/learningObjects/{id}?include=enrollment` | `GET /primeapi/v2/enrollments?filter.loTypes=learningProgram` |

>[!NOTE]
>
>Il parametro `include=enrollment` funziona solo con un token Allievo. Non è supportato per il ruolo di amministratore.

La risposta restituisce l&#39;oggetto `metadata` con l&#39;iscrizione al percorso di apprendimento.

### Utilizzo dei metadati nei portali headless ed esterni

I portali e le integrazioni esterni utilizzano le stesse chiamate API. Utilizza la richiesta corrispondente al token utilizzato dal portale.

* **Mostra il valore nel portale:** Inviare la richiesta di GET per il tipo di token dalla tabella precedente e leggere l&#39;oggetto `metadata` dalla risposta.
* **Aggiornare il valore da un sistema esterno, ad esempio una piattaforma di e-commerce:** Inviare la richiesta PATCH con un token di amministrazione.

## API processo: esportazione di report di Report Builder con generateCustomReport

La versione di dicembre 2026 di Adobe Learning Manager aggiunge un nuovo tipo di processo, `generateCustomReport`, all&#39;API del processo. Usalo per esportare qualsiasi report creato nel Report Builder, in modo automatico, passando l’ID del report.

In combinazione con il nuovo set di dati del quiz L2 in Report Builder, ora puoi:

* Esporta i dati dei quiz a livello di domanda (L2) in più corsi e moduli in un unico report, invece di eseguire `generateQuizReport` una volta per ogni corso.
* Automatizza le esportazioni ricorrenti, ad esempio, un&#39;esportazione incrementale giornaliera nel tuo data warehouse o strumento BI.

I tipi di processo esistenti, inclusi `generateQuizReport`, rimangono invariati.

### Prima di iniziare

* Devi essere un Amministratore. Tipo di processo `generateCustomReport` non disponibile per altri ruoli.
* Crea e salva prima il report nel Report Builder. Per i dati dei quiz L2, crea il report dal set di dati del quiz L2 e includi i campi a livello di domanda necessari, come il testo della domanda, la risposta dell’Allievo, il punteggio, il numero del tentativo e la data di risposta.
* Prendere nota dell&#39;ID del report. Passalo nella richiesta come `reportId`.

### Crea un lavoro

**Endpoint**

```
POST /primeapi/v2/jobs
```

**Corpo della richiesta**

```json
{
  "data": {
    "type": "job",
    "attributes": {
      "description": "Daily L2 quiz export",
      "jobType": "generateCustomReport",
      "payload": {
        "reportId": "1478"
      }
    }
  }
}
```

**Attributi**

| Attributo | Necessario | Descrizione |
|---|---|---|
| `jobType` | Sì | Deve essere `generateCustomReport`. |
| `payload.reportId` | Sì | ID del report Report Builder salvato, sotto forma di stringa. Deve essere un numero intero positivo, passato come stringa, ad esempio `"1478"`. L’invio di un numero, 0, un valore negativo, un valore decimale o un valore vuoto restituisce un errore. |
| `description` | No | Una descrizione di tua scelta per il lavoro. |
| `callbackUrl` | No | URL da chiamare al completamento del processo. Funziona allo stesso modo degli altri tipi di job. |
| `payload.filters` | No | Consulta la sezione seguente. |

### Sostituisci il filtro data (facoltativo) {#override-date-filter}

```json
"payload": {
  "reportId": "1478",
  "filters": [
    { "columnName": "L2 Quiz - Response - Timestamp", "operator": "gte", "val": "2026-11-15T00:00:00.000Z" }
  ]
}
```

* Sostituisce il filtro data salvato del report solo per questa esecuzione. L&#39;esportazione copre `val` (incluso) fino al momento in cui viene eseguito il processo.
* `columnName` utilizza il formato `<Dataset name> - <Field name>`. Deve corrispondere a un filtro data già esistente nel report. Non fa distinzione tra maiuscole e minuscole, ma la spaziatura e i trattini devono corrispondere esattamente.
* `operator` è facoltativo e solo `gte` è consentito.
* `val` è un&#39;ora UTC ISO 8601 negli ultimi 7 giorni. I tempi vengono troncati al secondo.
* È possibile sostituire più colonne. Un elenco vuoto indica che vengono utilizzati i filtri salvati.
* Esempio di utilizzo: un’esportazione incrementale giornaliera che inizia nel punto in cui si è conclusa l’esportazione precedente.

### Errori restituiti durante la creazione di un processo

| Causa | Messaggio |
|---|---|
| `reportId` mancante | `reportId is required` |
| `reportId` non è una stringa intera positiva | `reportId must be a positive integer string` |
| Data non in formato ISO | `filters.val must be in ISO format, e.g. 2020-01-01T18:30:00.000Z` |
| Data anteriore a 7 giorni o futura | `filters.val must be within the last 7 days` |
| Operatore diverso da `gte` | `filters.operator must be gte` |
| Stessa colonna specificata due volte | `Duplicate filter column: <column>` |
| La colonna non è un filtro nel report | `Unsupported custom report filter column: <column>` |
| Un processo per lo stesso report è ancora in esecuzione | `There exists an similar job with id = <jobId> which has not finished yet` |

Durante l&#39;esecuzione del processo vengono rilevati solo i problemi relativi alla definizione di report salvata. In tal caso, lo stato del processo diventa `Failed` e non viene restituito alcun motivo.

### Requisiti per i report

Il processo non riesce con un messaggio di errore se il report non soddisfa le seguenti condizioni:

* La definizione del report include un filtro data relativa, ad esempio ultimi 7 giorni.
* Ogni filtro per data nel report deve coprire un massimo di 7 giorni, non solo uno.
* Gli intervalli di date fissi, con date di inizio e fine impostate, non sono supportati e il processo non riesce.
* Un report senza filtro per data non riesce. Sono inclusi i report basati su dataset privi di campo data.

>[!NOTE]
>
>La richiesta POST viene convalidata immediatamente. Richiesta non valida rifiutata con HTTP 400. Motivo in `source.info`.

### Verifica lo stato del processo e scarica il report

**Endpoint**

```
GET /primeapi/v2/jobs/{jobId}
```

La risposta utilizza la stessa struttura degli altri tipi di job. Al termine del processo, `status.code` è `Completed` e `status.data.s3Url` contiene il collegamento per il download.

```json
{
  "data": {
    "type": "job",
    "id": "12345",
    "attributes": {
      "jobType": "generateCustomReport",
      "payload": {
        "reportId": "1478"
      },
      "status": {
        "code": "Completed",
        "data": {
          "s3Url": "valid for 7 days"
        }
      }
    }
  }
}
```

L&#39;API restituisce `Submitted`, `Completed` e `Failed`. Il file è un singolo file CSV denominato `report.csv`.

>[!NOTE]
>
>L’URL di download è valido per sette giorni. Scarica il file non appena viene completato il processo.

>[!IMPORTANT]
>
>Chiunque disponga del collegamento può scaricare il file senza effettuare l’accesso. Gestire il collegamento come se si trattassero i dati in esso contenuti.

**Esempio di processo non riuscito**

```json
"status": { "code": "Failed" }
```

### Limiti

È possibile eseguire un solo processo `generateCustomReport` per un report alla volta. Una seconda richiesta viene rifiutata fino al termine della prima.

### Output report quiz L2

Quando crei un report dal set di dati del quiz L2 nel Report Builder ed esporti il report con `generateCustomReport`, l’output ha le seguenti caratteristiche:

* L&#39;output è un singolo file CSV denominato `report.csv`. Il modulo è una colonna nel file. Se selezioni un corso, il report restituisce solo i moduli del quiz.
* Ogni riga rappresenta la risposta di un Allievo a una domanda in un unico tentativo.
* I dati vengono aggiornati all&#39;intervallo di Report Builder standard (circa ogni 15 minuti).
* I valori di data e ora si trovano nel fuso orario dell’account. L&#39;intestazione di colonna mostra il fuso orario, ad esempio `L2 Quiz - Response - Timestamp (America/Argentina/Salta)`.

### Campi nel set di dati del quiz L2

| Categoria | Campi |
|---|---|
| Allievo | ID utente |
| Corso | ID corso, ID istanza corso, nome corso |
| Modulo | ID modulo, nome modulo, versione modulo |
| Domanda | ID domanda, testo domanda, risposta corretta, tipo di interazione |
| Risposta | Risposta, Punteggio Ottenuto, Punteggio Massimo Possibile, Corretta, Timestamp Risposta |
| Tentativo | Numero di tentativi |

>[!NOTE]
>
>Il set di dati del quiz L2 non è collegato ad altri set di dati di Report Builder. Il nome dell’Allievo, l’e-mail, il Manager e gli attributi personalizzati non sono disponibili in questo report. Per fare in modo che una riga corrisponda a un Allievo, utilizza l’ID utente.

È inoltre possibile esportare report creati su altri dataset di Report Builder con `generateCustomReport`. I campi disponibili nell’output dipendono dal set di dati.

## API per creare e gestire il connettore Zoom

Utilizza queste API per gestire le connessioni Zoom in Adobe Learning Manager. È possibile recuperare le connessioni esistenti, salvare le credenziali di Zoom, creare o aggiornare le connessioni, configurare le autorizzazioni di accesso per i gruppi di utenti e i ruoli personalizzati e attivare o disattivare una connessione.

### Configurazione delle API del connettore Zoom

La configurazione e la gestione di un connettore Zoom richiede quattro chiamate API. Effettua le seguenti operazioni:

| Passaggio | API | Che cosa fa |
|---|---|---|
| 1 | `POST /ctr/authcred/uuid/20012` | Salva le credenziali di Zoom. |
| 2 | `POST /ctr/app/esconnect` | Crea la connessione Zoom o ne aggiorna una esistente. |
| 3 | `PUT /ctr/xtsa/{connectionId}/access` | Imposta i gruppi di utenti e i ruoli personalizzati che possono utilizzare la connessione. |
| 4 | `POST /ctr/xtsas/{connectionId}/enable` | Attiva o disattiva la connessione. |

>[!NOTE]
>
>Queste API utilizzano la sessione di amministrazione dell’integrazione che ha effettuato l’accesso. Non utilizzano una chiave API o un token OAuth.

### URL di base e convenzioni

Le API del connettore Zoom utilizzano le seguenti convenzioni:

| Elemento | Valore |
|---|---|
| URL di base | `https://learningmanagerstage1.adobe.com` |
| Tipo di contenuto | `application/json` |
| Autenticazione | Sessione di un Amministratore dell’integrazione che ha effettuato l’accesso |
| Intestazioni obbligatorie | `content-type`, `accept`, `x-acap-caller-role: ROLE_INTEGRATIONADMIN`, `x-csrf-token` e `Cookie` |
| UUID del catalogo di integrazione per Zoom | `20012` |
| Limite connessioni | 50 Connessioni zoom |

Il valore `x-csrf-token` è incorporato nel HTML della pagina Amministratore dell’integrazione come `csrfToken`. L&#39;intestazione `Cookie` contiene i cookie di sessione dell&#39;amministratore che ha effettuato l&#39;accesso.

### Prima di iniziare

- Accedi come Amministratore dell’integrazione.
- Creare un’app Zoom Server-to-Server OAuth. Prendere nota dell’ID client, del segreto client e dell’ID account. È inoltre necessario l’indirizzo e-mail del super amministratore Zoom.
- Chiama `GET /ctr/xtsas/canCreateAccount/25`. Restituisce `true` se puoi creare un&#39;altra connessione Zoom.

### Passaggio 1: salvare le credenziali di Zoom {#save-credentials}

Chiama questa API prima di creare o aggiornare una connessione. Vengono memorizzate le credenziali utilizzate dal connettore per connettersi a Zoom.

```
POST /ctr/authcred/uuid/20012
```

Per aggiornare una connessione esistente, aggiungere il parametro di query `connectionId`:

```
POST /ctr/authcred/uuid/20012?connectionId={connectionId}
```

Il corpo della richiesta è costituito dalle credenziali come testo JSON. È una stringa JSON che contiene JSON, non un oggetto nidificato. Includi le virgolette esterne.

| Chiave | Descrizione |
|---|---|
| `clientId` | ID client dell’app Zoom. |
| `clientSecret` | Il segreto client dell’app Zoom. Questo valore è sensibile. |
| `accountId` | ID account Zoom. |
| `superAdmin` | L’indirizzo e-mail dell’amministratore privilegiato Zoom. |

Corpo della richiesta di esempio:

```
"{\"clientId\":\"<ZOOM_CLIENT_ID>\", \"clientSecret\":\"<ZOOM_CLIENT_SECRET>\", \"accountId\":\"<ZOOM_ACCOUNT_ID>\", \"superAdmin\":\"<ADMIN_EMAIL>\"}"
```

Esempio di risposta `200 OK`:

```json
{
  "code": 0,
  "description": "Success"
}
```

`code: 0` indica che le credenziali sono state salvate.

### Passaggio 2: crea o aggiorna la connessione Zoom {#create-connection}

Questa API crea una connessione Zoom. Lo stesso endpoint aggiorna anche una connessione esistente.

```
POST /ctr/app/esconnect
```

Il corpo della richiesta contiene i seguenti campi:

| Campo | Necessario | Descrizione |
|---|---|---|
| `UUID` | Sì | UUID del catalogo di integrazione. Usa `20012` per Zoom. |
| `listOfConnections` | Sì | Connessioni da creare. Invia un elemento. |
| `listOfConnections[].name` | Sì | Nome visualizzato del connettore, ad esempio `Zoom_Partner_X`. |
| `listOfConnections[].tag` | Sì | Invia una stringa vuota (`""`) quando crei un connettore. Omettetelo quando ne aggiornate una. |
| `listOfConnections[].credentialsJson` | Sì | Le credenziali come testo JSON. Utilizza la stessa stringa inviata al passaggio 1. |
| `listOfConnections[].schedules` | Sì | Pianificazione della sincronizzazione. Invia `objectUUID` 10002, `priority` 1 e `type` 1. |
| `listOfConnections[].id` | Aggiorna solo | ID della connessione da aggiornare, ad esempio `3474737`. |

Corpo della richiesta di esempio:

```json
{
  "UUID": 20012,
  "listOfConnections": [
    {
      "name": "Zoom_Example",
      "tag": "",
      "credentialsJson": "{\"clientId\":\"<ZOOM_CLIENT_ID>\", \"clientSecret\":\"<ZOOM_CLIENT_SECRET>\", \"accountId\":\"<ZOOM_ACCOUNT_ID>\", \"superAdmin\":\"<ADMIN_EMAIL>\"}",
      "schedules": [
        { "objectUUID": 10002, "priority": 1, "type": 1 }
      ]
    }
  ]
}
```

Esempio di risposta `200 OK`:

```json
[3474737]
```

La risposta è una matrice JSON che contiene l’ID della nuova connessione. Utilizza questo ID nei passaggi 3 e 4 e in qualsiasi chiamata di follow-up.

### Crea e aggiorna confrontati

| Differenza | Crea | Aggiornamento |
|---|---|---|
| `listOfConnections[].id` | Non inviato | ID connessione |
| `listOfConnections[].tag` | `""` | Non inviato |
| Chiamata credenziali nel passaggio 1 | `POST /ctr/authcred/uuid/20012` | `POST /ctr/authcred/uuid/20012?connectionId={id}` |

### Passaggio 3: impostare gli utenti autorizzati a utilizzare la connessione {#set-access}

Questa API definisce quali gruppi di utenti e ruoli personalizzati possono utilizzare la connessione.

```
PUT /ctr/xtsa/{connectionId}/access
```

Il percorso utilizza il singolare `xtsa` per una connessione. Il plurale `xtsas` è la raccolta di connessioni.

Il corpo della richiesta è una matrice JSON. Ogni elemento concede l&#39;accesso a un gruppo di utenti o a un ruolo personalizzato.

| Campo | Necessario | Descrizione |
|---|---|---|
| `accessType` | Sì | `USER_GROUP` o `CUSTOM_ROLE`. |
| `accessId` | Sì | ID del gruppo di utenti o del ruolo personalizzato, sotto forma di stringa. |

Corpo della richiesta di esempio:

```json
[
  { "accessType": "USER_GROUP", "accessId": "<groupId>" },
  { "accessType": "CUSTOM_ROLE", "accessId": "<roleId>" }
]
```

L&#39;API restituisce `204 No Content` senza corpo quando l&#39;elenco di accesso viene salvato.

>[!NOTE]
>
>La richiesta sostituisce l&#39;intero elenco di accesso. Non si accoda ad esso. Tutto ciò che non è nel corpo perde l&#39;accesso. Per rimuovere tutti gli accessi, inviare una matrice vuota (`[]`).

### Passaggio 4: attivare o disattivare la connessione {#enable-disable}

Questa API attiva o disattiva una connessione. Usalo dopo aver creato la connessione, ogni volta che devi cambiarne lo stato.

```
POST /ctr/xtsas/{connectionId}/enable
```

Il percorso utilizza il plurale `xtsas`, come l&#39;elenco e le chiamate di eliminazione. La chiamata di accesso nel passaggio 3 utilizza il singolare `xtsa`.

| Parametro Path | Tipo | Descrizione |
|---|---|---|
| `connectionId` | Numero | ID della connessione. `id` restituito da `GET /ctr/xtsas` e ID restituito al passaggio 2. |

Il corpo della richiesta contiene i seguenti campi:

| Campo | Tipo | Necessario | Descrizione |
|---|---|---|---|
| `objectUUID` | Numero | Sì | Oggetto di sincronizzazione della connessione. Utilizza `10002`, lo stesso valore che hai inviato in `schedules[].objectUUID` nel passaggio 2. |
| `operation` | Numero | Sì | Invia `1`. |
| `val` | Booleano | Sì | Nuovo stato della connessione. Invia `false` per disabilitare la connessione. Invia `true` per abilitarlo. |

Esempio di corpo della richiesta per disabilitare una connessione:

```json
{
  "objectUUID": 10002,
  "operation": 1,
  "val": false
}
```

Esempio di corpo della richiesta per abilitare una connessione:

```json
{
  "objectUUID": 10002,
  "operation": 1,
  "val": true
}
```

Richiesta di esempio per disabilitare una connessione:

```bash
curl -X POST 'https://learningmanagerstage1.adobe.com/ctr/xtsas/<connectionId>/enable' \
  -H 'accept: application/json' \
  -H 'content-type: application/json' \
  -H 'x-acap-caller-role: ROLE_INTEGRATIONADMIN' \
  -H 'x-csrf-token: <CSRF_TOKEN>' \
  -H 'Cookie: <SESSION_COOKIES>' \
  --data '{"objectUUID":10002,"operation":1,"val":false}'
```

Per confermare il nuovo stato, chiamare `GET /ctr/xtsas`, trovare la connessione entro `id` e controllare il relativo flag `enabled`.

>[!NOTE]
>
>L&#39;intestazione `x-acap-caller-role` deve corrispondere al ruolo del profilo attivo. Per queste API, utilizza `ROLE_INTEGRATIONADMIN`.

### Gestire la connessione dopo averla creata

È possibile utilizzare le chiamate seguenti con l&#39;ID di connessione:

| Scopo | Chiama |
|---|---|
| Attivare o disattivare una connessione | `POST /ctr/xtsas/{connectionId}/enable` |
| Leggi l&#39;elenco di accesso di una connessione | `GET /ctr/xtsa/{connectionId}/access` |
| Accesso in lettura per tutte le connessioni Zoom | `GET /ctr/xtsas/access?UUID=20012` |
| Elenca tutte le connessioni. Le connessioni zoom hanno `extsysRefId` 25. | `GET /ctr/xtsas` |
| Visualizzare una connessione | `GET /ctr/app/connection/{id}/object/10002` |
| Eliminare definitivamente una connessione | `DELETE /ctr/xtsas/{id}` |

>[!NOTE]
>
>La chiamata di visualizzazione restituisce il segreto client in testo non crittografato. Considera il segreto client come sensibile e ruotalo se è esposto. Non eseguire il commit o condividere cookie di sessione, token CSRF o credenziali, anche nei file HAR e nei comandi cURL copiati.

### Utilizza queste API nell’integrazione

Un caso d’uso comune è la configurazione automatica di un connettore Zoom per un nuovo account o partner.

1. Chiamare `GET /ctr/xtsas/canCreateAccount/25` per confermare la creazione di un&#39;altra connessione.
2. Chiama `POST /ctr/authcred/uuid/20012` con le credenziali Zoom.
3. Chiama `POST /ctr/app/esconnect` con il nome del connettore, la stessa stringa di credenziali e la pianificazione della sincronizzazione. Leggere l&#39;ID di connessione dalla risposta.
4. Chiama `PUT /ctr/xtsa/{connectionId}/access` con i gruppi di utenti e i ruoli personalizzati che possono utilizzare la connessione.
5. Chiamare `POST /ctr/xtsas/{connectionId}/enable` con `val` impostato su `true` o `false` per abilitare o disabilitare la connessione. Quindi chiamare `GET /ctr/xtsas` e controllare il flag `enabled` per confermare lo stato.
6. Per modificare le credenziali in seguito, ripetere i passaggi 2 e 3 con l&#39;ID di connessione.


