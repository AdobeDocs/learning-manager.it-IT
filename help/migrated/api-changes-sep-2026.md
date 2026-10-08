---
description: Endpoint API pubblici rivolti agli Allievi per elencare, recuperare, iscrivere ed eliminare percorsi di apprendimento personalizzati in Adobe Learning Manager ed endpoint API per verificare se uno o più oggetti di apprendimento sono direttamente accessibili a un determinato Allievo tramite un catalogo ad essi assegnato.
jcr-language: en_us
title: Modifiche alle API di settembre 2026
product_v2:
  - id: ed12e5b7-96e3-45e7-a17f-de222065ebcb
    internal-label: Learning Manager
source-git-commit: c061ccbefe8d40154220587796062d335e35de77
workflow-type: tm+mt
source-wordcount: '1374'
ht-degree: 3%
---

# Modifiche alle API nella versione di settembre 2026 di Adobe Learning Manager

## API per la verifica dell’accesso al catalogo per gli oggetti di apprendimento

Determina se l’Allievo corrente ha accesso diretto al catalogo a uno o più oggetti di apprendimento, indipendentemente dal fatto che abbia raggiunto tale contenuto tramite un percorso di apprendimento o una certificazione.

### Scopo dell’API

Quando un Allievo apre un percorso di apprendimento o una certificazione, può sfogliare i singoli corsi al suo interno, anche se un corso specifico non gli viene assegnato direttamente tramite un catalogo. Questo supporta l’individuazione dei contenuti: gli Allievi possono esplorare il contenuto di un percorso di apprendimento prima di decidere se proseguirlo o meno.

Tuttavia, la possibilità di visualizzare un corso in questo modo non dovrebbe implicare automaticamente che l’Allievo possa iscriverlo. L’iscrizione deve dipendere dal fatto che l’Allievo abbia o meno accesso diretto al catalogo per il corso specifico, non solo accesso indiretto tramite un percorso di apprendimento che lo contiene.

Questa API consente di verificare, per un determinato Allievo, se uno o più oggetti di apprendimento sono direttamente accessibili tramite un catalogo loro assegnato. Utilizza il risultato per controllare l’interfaccia utente relativa all’iscrizione, ad esempio, mostrando un’opzione Iscrizione solo quando l’accesso diretto al catalogo è confermato, mantenendo la pagina del corso visualizzabile in entrambi i casi.

### Endpoint

`GET /primeapi/v2/learningObjects/isMemberOfVisibleCatalogs`

| Proprietà | Valore |
|---|---|
| **Ambito** | Accesso in lettura da parte dell’Allievo |
| **Formato risposta** | application/vnd.api+json |

### Parametri di query

| Parametro | Necessario | Tipo | Descrizione |
|---|---|---|---|
| id | Sì | stringa o matrice | Uno o più ID dell’oggetto di apprendimento da controllare. Accetta un singolo ID o un elenco separato da virgole. Massimo 10 ID per richiesta. |

### Richiesta di esempio

```
GET /primeapi/v2/learningObjects/isMemberOfVisibleCatalogs?ids=course%3A2400159%2Ccourse%3A2400160%2Ccourse%3A2400161%2Ccourse%3A2400162
Accept: application/vnd.api+json
Authorization: oauth <access-token>
```

>[!NOTE]
>
>Gli ID dell’oggetto di apprendimento devono essere codificati con URL. I due punti in un ID come course:2400159 sono codificati come %3A e la virgola che separa più ID è codificata come %2C.

### Esempio di risposta - 200 OK

```json
{
  "course:2400162": false,
  "course:2400161": false,
  "course:2400160": true,
  "course:2400159": true
}
```

| Valore | Significato |
|---|---|
| vero | L’Allievo chiamante ha accesso diretto al catalogo a questo oggetto di apprendimento. |
| falso | L’oggetto di apprendimento non è direttamente disponibile per l’Allievo chiamante tramite un catalogo. L’Allievo potrebbe comunque essere in grado di visualizzarla se è raggiungibile tramite un percorso di apprendimento o una certificazione a cui ha accesso. |

### Codici di risposta

| Stato | Significato |
|---|---|
| 200 | La richiesta è riuscita. La risposta contiene un risultato per ogni ID richiesto. |
| 400 | Errore generico di richiesta non valida. Ad esempio, sono stati forniti più di 10 ID o il formato di un ID non è valido. |
| 401 | Nella richiesta mancano credenziali Allievo valide oppure l’accesso è stato negato a causa di credenziali non valide. |

### Esempio di risposta di errore

```json
{
  "status": "BAD_REQUEST",
  "title": "Bad request. Check url, params and headers",
  "source": {
    "info": "Either LO id is blank or not as per public api specification"
  }
}
```

### Utilizza questa API nell’integrazione

Un caso d’uso comune è una pagina del corso che un Allievo raggiunge navigando da un percorso di apprendimento. Desideri che la pagina del corso rimanga accessibile per l’individuazione, mostrando l’azione **Iscrizione** solo se l’Allievo ha accesso diretto al catalogo per quel corso.

1. Quando viene caricata la pagina del corso, chiama questo endpoint con l’ID dell’oggetto di apprendimento del corso.
2. Se la risposta restituisce true per l&#39;ID, visualizzare l&#39;opzione **Iscrizione**.
3. Se la risposta restituisce false, mantieni visibile la pagina del corso, il titolo, la descrizione e i dettagli del corso, ma nascondi l&#39;opzione **Iscrizione**.

## API dei processi per il report di prova di verifica dell’amministratore {#apiaudittrailreport}

### Scopo dell’API

Il report Audit trail dell’amministratore elenca le modifiche di configurazione apportate a un
Account Adobe Learning Manager. Ad esempio, modifiche a Nozioni di base, Integrazioni o
Impostazioni avanzate dell’account in un determinato intervallo di date. La generazione del report Audit trail richiede l&#39;esecuzione di query e l&#39;aggregazione dei record di modifica della configurazione nell&#39;intervallo di date richiesto e nei tipi di impostazione. A seconda delle dimensioni dell&#39;intervallo e del volume delle modifiche, questo valore può superare i limiti di tempo di una richiesta HTTP sincrona, con conseguente rischio di timeout del client o del gateway.

Per evitare ciò, il report viene generato in modo asincrono tramite l’API generica dei processi:

1. **Crea un processo.** L’amministratore invia una richiesta specificando il tipo di report, l’intervallo di date e i tipi di impostazione. L’API restituisce immediatamente un ID processo, senza attendere la compilazione del report.

2. **Sondaggio del processo.** L&#39;amministratore recupera periodicamente il processo in base al suo ID per verificarne lo stato. Al termine del processo, la risposta contiene il risultato o un riferimento al risultato.

### URL di base e convenzioni

| Elemento | Valore |
|---|---|
| Percorso di base | `/primeapi/v2` |
| Tipo di contenuto | `application/vnd.api+json;charset=UTF-8` (JSON:API) |
| Autenticazione | Token OAuth di Bearer, con ambito di amministrazione di un account |
| Contesto account | Intestazione `x-acap-account` che identifica l&#39;account dell&#39;amministratore chiamante |
| Polling | Nessun intervallo fisso applicato. Eseguire il polling dell&#39;endpoint Ottieni stato processo fino a quando `status` non è più `QUEUED` o `IN_PROGRESS` |

### ID

Il processo `id` restituito durante la creazione di un processo è una stringa opaca, ad esempio
`4593`). Restituisci sempre il valore `id` esatto ricevuto dalla creazione
risposta durante il polling per lo stato. Non costruirlo o analizzarlo mai.

### Ambiti di autenticazione

Ogni endpoint richiede un token OAuth con l’ambito seguente e
l’utente che effettua la chiamata deve avere il ruolo di amministratore dell’account:

- `admin:write` crea un processo di report (`ROLE_ADMIN` richiesto)
- `admin:read` ha letto lo stato e il risultato di un processo (`ROLE_ADMIN` richiesto)

Le richieste effettuate da un chiamante che non detiene `ROLE_ADMIN` sull&#39;account sono
rifiutato. Vedere [Gestione errori](/help/migrated/api-changes-sep-2026.md#error-handling)

### Endpoint

#### Creare un processo di report di audit trail

`POST /primeapi/v2/jobs`

Crea un processo asincrono che genera un report di traccia di revisione della modifica della configurazione
per l&#39;intervallo di date e i tipi di impostazione specificati. La risposta viene restituita immediatamente
con una risorsa processo nello stato `QUEUED`. Il report stesso viene prodotto nel
sfondo.

Ambito: `admin:write`

| Parametro | In | Necessario | Descrizione |
|---|---|---|---|
| `jobType` | corpo | Sì | Deve essere `generateConfigChangeAuditReport` per questo report |
| `payload.fromDate` | corpo | Sì | Inizio della finestra di reporting, ISO-8601 con offset, ad esempio `2026-09-15T00:00:00.000+05:30` |
| `payload.toDate` | corpo | Sì | Fine della finestra di reporting, ISO-8601 con offset, ad esempio `2026-09-23T23:59:59.000+05:30` |
| `payload.settingTypes` | corpo | Sì | Matrice di una o più categorie di impostazioni da includere. I valori supportati sono `Basics`, `Integrations` e `Advanced` |

Corpo della richiesta di esempio

```json
{
  "data": {
    "type": "job",
    "attributes": {
      "jobType": "generateConfigChangeAuditReport",
      "payload": {
        "fromDate": "2026-09-15T00:00:00.000+05:30",
        "toDate": "2026-09-23T23:59:59.000+05:30",
        "settingTypes": ["Basics", "Integrations", "Advanced"]
      }
    }
  }
}
```

Risposta: `202 Created`. Il corpo della risposta è la risorsa del processo nella relativa posizione iniziale
Stato `QUEUED`.

```json
{
  "data": {
    "id": "4593",
    "type": "job",
    "attributes": {
      "jobType": "generateConfigChangeAuditReport",
      "status": "QUEUED",
      "dateCreated": "2026-09-23T18:12:04.000+05:30"
    }
  }
}
```

>[!NOTE]
>
>Una finestra `fromDate`/`toDate` che si estende su un intervallo di date molto ampio o che
>richiede tutti i tipi di impostazione per un account con una lunga cronologia modifiche.
>l’elaborazione richiede più tempo. Eseguire il polling dell&#39;endpoint Ottieni stato processo anziché
>presupponendo che il report sia pronto dopo un determinato ritardo.

#### Ottenere lo stato di un processo di report di audit trail

`GET /primeapi/v2/jobs/{id}`

Restituisce lo stato corrente di un processo creato in precedenza. Durante l&#39;esecuzione del processo
ancora in esecuzione, `attributes.status` è `QUEUED` o `IN_PROGRESS` e
`attributes.result` è assente. Al termine del processo, `attributes.status` è
`COMPLETED`, con il percorso del report in `attributes.result`, oppure
`FAILED`, con dettagli errore in `attributes.error`.

Ambito: `admin:read`

| Parametro | In | Necessario | Descrizione |
|---|---|---|---|
| `id` | percorso | Sì | ID processo restituito al momento della creazione del processo |

Risposta di esempio mentre il processo è ancora in esecuzione

```json
{
  "data": {
    "id": "4593",
    "type": "job",
    "attributes": {
      "jobType": "generateConfigChangeAuditReport",
      "status": "IN_PROGRESS",
      "dateCreated": "2026-09-23T18:12:04.000+05:30"
    }
  }
}
```

Risposta di esempio al completamento del processo

```json
{
  "data": {
    "id": "4593",
    "type": "job",
    "attributes": {
      "jobType": "generateConfigChangeAuditReport",
      "status": "COMPLETED",
      "dateCreated": "2026-09-23T18:12:04.000+05:30",
      "dateCompleted": "2026-09-23T18:12:41.000+05:30",
      "result": {
        "downloadUrl": "https://learningmanager.adobe.com/primeapi/v2/jobs/4593/download",
        "expiresAt": "2026-09-24T18:12:41.000+05:30"
      }
    }
  }
}
```

### Schema risorsa

#### Attributi processo

| Campo | Tipo | Descrizione |
|---|---|---|
| `id` | stringa | ID processo opaco |
| `jobType` | stringa | `generateConfigChangeAuditReport` per questo report |
| `status` | stringa | `QUEUED`, `IN_PROGRESS`, `COMPLETED` o `FAILED` |
| `dateCreated` | string (ISO-8601) | Al momento della creazione del processo |
| `dateCompleted` | string (ISO-8601) | Al termine del processo; presente una volta `status`: `COMPLETED` o `FAILED` |
| `payload` | oggetto | Parametri di richiesta con cui è stato creato il job (incorporati - vedere di seguito) |
| `result` | oggetto | Dove scaricare il report finito; presente solo quando `status` è `COMPLETED` (incorporato - vedere di seguito) |
| `error` | oggetto | Dettagli errore; presente solo quando `status` è `FAILED` |

#### Payload (incorporato, nella richiesta di creazione)

| Campo | Descrizione |
|---|---|
| `fromDate` | Inizio della finestra di reporting |
| `toDate` | Fine della finestra di reporting |
| `settingTypes` | Impostazione delle categorie incluse nel report: `Basics`, `Integrations`, `Advanced` |

#### Risultato (incorporato, all&#39;interno di un processo completato)

| Campo | Descrizione |
|---|---|
| `downloadUrl` | URL firmato da cui è possibile scaricare il report generato |
| `expiresAt` | Quando `downloadUrl` smette di essere valido. Richiedere un nuovo controllo dello stato per ottenere un nuovo collegamento in seguito |

### Gestione degli errori {#audit-trail-report-error-handling}

I seguenti codici si applicano a questi endpoint:

| Stato HTTP | Codice di errore | Quando si verifica |
|---|---|---|
| 400 | `BAD_REQUEST` | `toDate` è precedente a `fromDate`, `settingTypes` è vuoto o contiene un valore non supportato o una data non valida ISO-8601 - crea solo endpoint |
| 401 | `UNAUTHORIZED_ACCESS` | Token mancante, non valido o scaduto |
| 403 | `FORBIDDEN` | Il chiamante non detiene `ROLE_ADMIN` nell&#39;account |
| 400 | `OBJECT_DOESNT_EXIST` | Ottieni per ID: il processo non esiste o l&#39;ID non è valido. Entrambi i casi vengono compressi nella stessa risposta |

Esempio di risposta di errore

```json
{
  "status": "BAD_REQUEST",
  "title": "Bad request. Check url, params and headers",
  "source": {
    "info": "toDate must be on or after fromDate"
  }
}
```

### Utilizza questa API nell’integrazione

Un caso d’uso comune è un’azione &quot;Scarica prova di verifica&quot; rivolta all’amministratore nella
schermata delle impostazioni dell’account.

1. Quando l’amministratore seleziona un intervallo di date e uno o più tipi di impostazione e
conferma, chiamare l&#39;endpoint create-job con tali valori.
2. Archivia il processo restituito `id` ed esegui il polling dell&#39;endpoint Ottieni stato processo in un
intervallo ragionevole (ad esempio, ogni pochi secondi).
3. Mentre `status` è `QUEUED` o `IN_PROGRESS`, continua a visualizzare uno stato di avanzamento
nell&#39;interfaccia utente.
4. Quando `status` diventa `COMPLETED`, utilizzare `result.downloadUrl` per consentire a
l&#39;amministratore scarica il report prima che `expiresAt` passi.
5. Quando `status` diventa `FAILED`, rivolgi `error` all&#39;amministratore e concedigli di
riprova.
