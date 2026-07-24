---
description: Modifiche API in ALM
jcr-language: en_us
title: Modifiche alle API nella versione di agosto 2026 di Adobe Learning Manager
source-git-commit: 0862e0d042fac74377b44c3387a72336ec625161
workflow-type: tm+mt
source-wordcount: '3369'
ht-degree: 3%

---


# Modifiche alle API nella versione di agosto 2026 di Adobe Learning Manager

## API di amministrazione gruppi di utenti in Adobe Learning Manager

Questa versione aggiunge tre nuovi endpoint API pubblici con ambito di amministrazione per la gestione di gruppi di utenti personalizzati a livello di programmazione. Puoi creare, rinominare ed eliminare gruppi di utenti personalizzati senza utilizzare l’app di amministrazione, consentendo di automatizzare la gestione dei gruppi come parte dei flussi di lavoro di identità o provisioning.

Questi endpoint funzionano solo con gruppi di utenti personalizzati. I gruppi gestiti dal sistema, ad esempio il gruppo Tutti gli utenti e i gruppi di utenti generati automaticamente, hanno il valore readOnly: true nella risposta API e non possono essere modificati o eliminati tramite questi endpoint.

Per i requisiti di autenticazione API, vedere [Autenticazione API Adobe Learning Manager](https://experienceleague.adobe.com/en/docs/learning-manager/using/integration/developer-manual#authentication-using-oauth-20).

### Endpoint API gruppi di utenti

Tutti e tre gli endpoint richiedono un token di accesso amministratore con autorizzazioni di scrittura (ROLE_ADMIN).

| **Metodo** | **Percorso** | **Operazione** | **Codice operazione riuscita** |
|---|---|---|---|
| POST | /primeapi/v2/userGroups | Creare un gruppo di utenti personalizzato | 201 Created |
| PUT | /primeapi/v2/userGroups/{id} | Aggiornare il nome o la descrizione di un gruppo | 200 OK |
| DELETE | /primeapi/v2/userGroups/{id} | Eliminare un gruppo di utenti personalizzato | 204 Nessun contenuto |

## **Intestazioni di richiesta comuni**

Tutti e tre gli endpoint richiedono le intestazioni seguenti.

```
Authorization: Bearer \<access-token\>
X-acap-user: \<user-id\>
X-acap-account: \<account-id\>
X-acap-caller-role: ROLE_ADMIN
Content-Type: application/vnd.api+json
Accept: application/vnd.api+json
```

### **Creare un gruppo di utenti**

```
POST /primeapi/v2/userGroups
```

Crea un nuovo gruppo di utenti personalizzato con un elenco iniziale di membri. Il gruppo è immediatamente disponibile per l&#39;uso nell&#39;app per amministratori.

#### **Corpo della richiesta**

```
{
  "name": "Marketing Team",
  "description": "Custom user group for marketing onboarding",
  "data": [
    { "type": "user", "id": "11282373" },
    { "type": "user", "id": "11282374" }
  ]
}
```

#### **Parametri richiesta**

| **Parametro** | **Obbligatorio** | **Tipo** | **Descrizione** |
|---------------|--------------|----------|-------------------------------------------------------------------------------------|
| nome | Sì | stringa | Nome visualizzato del gruppo. Non deve essere vuoto o contenere solo spazi. |
| descrizione | No | stringa | Descrizione facoltativa dello scopo del gruppo. |
| dati | Sì | matrice | Elenco dei membri iniziali. Minimo 1 oggetto, massimo 100 oggetti. |
| data[].type | Sì | stringa | Deve essere &quot;utente&quot;. Non sono accettati altri tipi di risorse. |
| data[].id | Sì | stringa | Stringa dell&#39;ID utente numerico. L’utente deve appartenere all’account e avere lo stato ATTIVO. |

> **Nota:** la matrice di dati viene utilizzata solo al momento della creazione per impostare l&#39;elenco di membri iniziale. Per aggiungere o rimuovere membri dopo la creazione, utilizzare gli endpoint di appartenenza al gruppo di utenti esistenti.

#### **Risposta 201 creata**

```
{
  "links": {
    "self": "https://<host>/primeapi/v2/userGroups"
  },
  "data": {
    "id": "2769204",
    "type": "userGroup",
    "attributes": {
      "dateCreated": "2026-06-04T14:19:53.000Z",
      "description": "Custom user group for marketing onboarding",
      "name": "Marketing Team",
      "readOnly": false,
      "userCount": 2
    }
  }
}
```

#### **POST delle regole di convalida**

| **#** | **Convalida** | **Codice di errore** | **Attivazione** |
|-------|-------------------------------------------------------|----------------------------------------------------------|------------------------------------------------|
| 1 | nome presente e non vuoto | USERGROUP_CREATE_NAME_REQUIRED | Nome omesso o solo spazio vuoto |
| 2 | i dati contengono almeno 1 utente | USERGROUP_CREATE_USERS_REQUIRED | dati assenti o matrice vuota |
| 3 | i dati contengono al massimo 100 utenti | USERGROUP_USERS_MAX_LIMIT_EXCEEDED | Più di 100 voci nei dati[] |
| 4 | Tutti gli ID utente sono stringhe numeriche | INVALID_USER_IDS | Stringa non numerica trovata in data[].id |
| 5 | Tutti gli utenti sono presenti nell’account e hanno lo stato ATTIVO. | INVALID_USER_IDS / USERGROUP_CREATE_USERS_NOT_IN_ACCOUNT | Utente non trovato o non attivo |
| 6 | L’account non ha raggiunto il limite di gruppi personalizzati | 400 | Superato il limite a livello di account per i gruppi personalizzati |

### **Aggiornare un gruppo di utenti**

```
PUT /primeapi/v2/userGroups/{id}
```

Aggiorna il nome e/o la descrizione di un gruppo di utenti personalizzato esistente. Questo endpoint non può aggiungere o rimuovere membri del gruppo.

Entrambi i campi possono essere omessi; se si omette un campo, il suo valore corrente rimane invariato. Se si passa il valore null per la descrizione, il valore viene cancellato. Il passaggio di una stringa vuota per il nome è rifiutato.

#### **Corpo della richiesta**

```json
{
  "name": "Updated Group Name",
  "description": "Updated description text"
}
```

#### **Parametri richiesta**

| **Parametro** | **Obbligatorio** | **Tipo** | **Descrizione** |
|---------------|--------------|----------|---------------------------------------------------------------------------|
| nome | No | stringa | Nuovo nome visualizzato. Se specificato, non deve essere vuoto. Ometti di lasciare invariato. |
| descrizione | No | stringa | Nuova descrizione. Passare null per cancellare. Ometti di lasciare invariato. |
| dati | — | null | Deve essere null o assente. Qualsiasi valore diverso da null restituisce un errore 400. |

#### **Risposta 200 OK**

```
{
  "data": {
    "type": "userGroup",
    "id": "2767870",
    "attributes": {
      "name": "Updated Group Name",
      "description": "Updated description text",
      "readOnly": false,
      "state": "Active",
      "userCount": 3
    }
  }
}
```

#### **PUT delle regole di convalida**

| **#** | **Convalida** | **Codice di errore** | **Attivazione** |
|-------|-------------------------------------|----------------------------------------|----------------------------------------------------------|
| 1 | dati nulli o assenti | USERGROUP_UPDATE_USERS_NOT_ALLOWED | Il chiamante ha superato il tentativo di modifica dell&#39;appartenenza ai dati non Null |
| 2 | il nome, se fornito, non è vuoto | USERGROUP_UPDATE_NAME_BLANK | nome inviato come stringa solo spazio vuoto |
| 3 | Il gruppo esiste in questo account | INVALID_USER_GROUP_ID | Parametro percorso {id} sconosciuto |
| 4 | Il gruppo non è già stato eliminato | DELETED_USERGROUP | Il gruppo è stato precedentemente eliminato |
| 5 | La proprietà Group ReadOnly è false | READ_ONLY_USERGROUP | Gruppo gestito dal sistema |
| 6 | Gruppo personalizzato (non di sistema) | USERGROUP_UPDATE_OPERATION_NOT_ALLOWED | Tipo di gruppo interno al sistema |

### **Eliminare un gruppo di utenti**

```
DELETE /primeapi/v2/userGroups/{id}
```

Contrassegna il gruppo di utenti personalizzato specificato come eliminato. Il record del gruppo non viene rimosso in modo permanente: il suo stato è impostato su ELIMINATO e questo lo rende invisibile nell’app per amministratori e non idoneo per l’uso in nuove configurazioni. Impossibile riutilizzare l&#39;ID gruppo.

#### **Esempio di richiesta**

```
DELETE /primeapi/v2/userGroups/2767870
Authorization: Bearer <access-token>
X-acap-user: <user-id>
X-acap-account: <account-id>
X-acap-caller-role: ROLE_ADMIN
```

#### **Risposta 204 senza contenuto**

Il corpo della risposta è vuoto.

> **Nota:** DELETE non è idempotente. L’invio di una seconda richiesta DELETE allo stesso ID gruppo restituisce un errore 400 con il codice DELETED_USERGROUP (non 204). Considera una risposta 400 DELETED_USERGROUP come conferma che il gruppo è già stato eliminato. L&#39;eliminazione in blocco non è supportata. Ogni gruppo richiede una richiesta DELETE separata.

#### **DELETE delle regole di convalida**

| **#** | **Convalida** | **Codice di errore** | **Attivazione** |
|-------|-------------------------------------|----------------------------------------|---------------------------------------------------|
| 1 | Il gruppo esiste in questo account | INVALID_USER_GROUP_ID | Parametro percorso {id} sconosciuto |
| 2 | Il gruppo non è già stato eliminato | DELETED_USERGROUP | Ripeti DELETE su un gruppo già nello stato ELIMINATO |
| 3 | La proprietà Group ReadOnly è false | READ_ONLY_USERGROUP | Gruppo gestito dal sistema |
| 4 | Gruppo personalizzato (non di sistema) | USERGROUP_UPDATE_OPERATION_NOT_ALLOWED | Tipo di gruppo interno al sistema |

## API di apprendimento esterno in Adobe Learning Manager

Questa versione aggiunge cinque nuovi endpoint API con ambito Allievo per la funzione di apprendimento esterno. Questi endpoint consentono agli Allievi di creare, recuperare e aggiornare gli invii di apprendimento esterni a livello di programmazione, ad esempio, da un’app per dispositivi mobili, un sistema HR integrato o un portale di apprendimento personalizzato.

Il flusso di lavoro di apprendimento esterno tramite API riflette il flusso di lavoro nell’app per allievi: un Allievo invia i dettagli del corso di formazione e un documento di prova opzionale, il suo Direct Manager riceve una notifica per esaminare l’invio e, all’approvazione, il record viene visualizzato nella trascrizione dell’Allievo.

Tutti e cinque gli endpoint hanno un ambito Allievo. Un Allievo può accedere solo ai propri invii: l’API restituisce un errore se un Allievo tenta di accedere ai dati di un altro Allievo.

Per i requisiti di autenticazione API, vedere [Autenticazione API Adobe Learning Manager](https://experienceleague.adobe.com/en/docs/learning-manager/using/integration/developer-manual#authentication-using-oauth-20).

### Endpoint API di apprendimento esterni

Tutti gli endpoint richiedono un token di accesso Allievo (ROLE_LEARNER).

| **Metodo** | **Percorso** | **Operazione** | **Codice operazione riuscita** |
|------------|---------------------------------------|----------------------------------|------------------|
| GET | /primeapi/v2/externalLearningSettings | Recupera configurazione modulo account | 200 OK |
| GET | /primeapi/v2/externalLearnings | Elenca gli invii del chiamante | 200 OK |
| GET | /primeapi/v2/externalLearnings/{id} | Recuperare un singolo inoltro | 200 OK |
| POST | /primeapi/v2/externalLearnings | Crea un nuovo inoltro | 201 Created |
| PUT | /primeapi/v2/externalLearnings/{id} | Aggiornare un inoltro in sospeso | 200 OK |

### Intestazioni di richiesta comuni

```
Authorization: Bearer <access-token>
X-acap-user: <user-id>
X-acap-account: <account-id>
X-acap-caller-role: ROLE_LEARNER
Accept: application/vnd.api+json
Content-Type: application/vnd.api+json (POST and PUT only)
```

### Ciclo di vita stato invio

| **Stato** | **Impostato da** | **Significato** | **L’Allievo può aggiornare?** |
|------------|------------------|-----------------------------------------|-----------------------------|
| IN SOSPESO | Sistema al momento della creazione | In attesa di revisione da parte del manager | Sì, tramite PUT |
| APPROVATO | Manager | Accettato; viene visualizzato nella trascrizione dell’Allievo | No - PUT restituisce 409 |
| RIFIUTATO | Manager | Rifiutato; commento di revisione allegato | No: crea un nuovo inoltro |

APPROVATI e RIFIUTATI sono stati terminali. Un inoltro rifiutato non può essere riaperto; l’Allievo deve creare un nuovo inoltro.

### Recupera configurazione modulo account

```
GET /primeapi/v2/externalLearningSettings
```

Restituisce la configurazione del modulo a livello di account. Chiamare questo endpoint prima di eseguire il rendering di un modulo di invio. La risposta definisce i campi da visualizzare, i campi obbligatori, i relativi tipi di dati e tutti i campi personalizzati configurati dall&#39;amministratore.

Verifica l’attributo abilitato di primo livello prima di procedere. Se è false, la funzione di apprendimento esterno non è attiva per questo account e gli endpoint di invio restituiranno errori.

#### Risposta 200 OK

```
{
  "data": {
    "id": "8627",
    "type": "externalLearningSettings",
    "attributes": {
      "enabled": true,
      "updatedAt": "2026-06-05T06:51:20.000Z",
      "coreFields": [
        { "id": "title", "type": "TEXT", "mandatory": true, "editable": false, "order": 0 },
        { "id": "description_notes", "type": "TEXT", "mandatory": false, "editable": true, "order": 1 },
        { "id": "date", "type": "TIMESTAMP", "mandatory": false, "editable": true, "order": 2 },
        { "id": "score", "type": "NUMBER", "mandatory": true, "editable": true, "order": 3 },
        { "id": "duration", "type": "TEXT", "mandatory": false, "editable": true, "order": 4 },
        { "id": "attachments", "type": "FILE_UPLOAD", "mandatory": true, "editable": true, "order": 5 }
      ],
      "customFields": [
        {
          "id": "960369b2-...",
          "type": "NUMBER",
          "mandatory": true,
          "order": 0,
          "label": { "en_US": "Employee Code" }
        },
        {
          "id": "3c6cc6d9-...",
          "type": "DROPDOWN",
          "mandatory": true,
          "order": 1,
          "label": { "en_US": "Department" },
          "options": [
            { "option_id": "opt_1", "label": { "en_US": "IT" } },
            { "option_id": "opt_2", "label": { "en_US": "HR" } },
            { "option_id": "opt_3", "label": { "en_US": "FIN" } }
          ]
        }
      ]
    }
  }
}
```

#### Riferimento campo core

| **ID campo** | **Tipo** | **Impostazione predefinita obbligatoria** | **Note** |
|-------------------|-------------|-----------------------|----------------------------------------------------------------------------------------------------------|
| titolo | TESTO | Sì | Nome del corso di formazione. Sempre presente. Non può essere disabilitato dall&#39;amministratore. |
| description_notes | TESTO | No | Descrizione o note in formato testo libero. |
| data | MARCA TEMPORALE | No | Intervallo di date. Forma valore: { &quot;start_date&quot;: &quot;<ISO-Z>&quot;, &quot;end_date&quot;: &quot;<ISO-Z>&quot; }. Entrambi i valori possono essere Null. |
| punteggio | NUMERO | Sì | Forma valore: { &quot;achievements_score&quot;: <number>, &quot;max_score&quot;: <number> }. Entrambi i valori devono essere numerici. |
| durata | TESTO | No | Stringa in formato libero, ad esempio &quot;40 ore&quot;. |
| allegati | FILE_UPLOAD | Sì | Prova di completamento. **Non** ha passato i campi[] — utilizza invece l&#39;attributo di primo livello submissionUrl. |

I campi personalizzati sono definiti dall&#39;amministratore e restituiti in customFields[]. Gli ID, i tipi, i contrassegni obbligatori, le etichette e le opzioni del menu a discesa variano a seconda della configurazione dell’account.

### Elenca invii

```
GET /primeapi/v2/externalLearnings
```

Restituisce un elenco impaginato degli invii dell’Allievo autenticato, ordinati in ordine decrescente in base all’ultima modifica.

#### **Parametri di query**

| **Parametro** | **Predefinito** | **Massimo** | **Descrizione** |
|---------------|-------------|-------------|-------------------------------------------------------------------------------------------------------|
| page[offset] | 0 | 5000 | Offset record basato su zero. |
| page[limit] | 10 | 100 | Record per pagina. I valori superiori a 100 vengono bloccati in modalità invisibile a 100. |
| ls_qp_status | — | — | Filtra per stato. Ometti per tutti i risultati. Valori validi: PENDING, APPROVED, REJECTED (senza distinzione tra maiuscole e minuscole). |

#### **Risposta 200 OK**

```
{
  "links": {
    "next": "/primeapi/v2/externalLearnings?page[offset]=10&page[limit]=10"
  },
  "data": [
    { "id": "1001", "type": "externalLearning", "attributes": { "status": "PENDING", ... } },
    { "id": "1002", "type": "externalLearning", "attributes": { "status": "APPROVED", ... } }
  ]
}
```

### Recuperare un inoltro

```
GET /primeapi/v2/externalLearnings/{id}
```

Restituisce il record completo di un singolo invio appartenente all’Allievo autenticato.

#### **Risposta 200 OK

```
{
  "data": {
    "id": "1001",
    "type": "externalLearning",
    "attributes": {
      "submissionUrl": "https://<cdn-url>/cert.pdf",
      "title": "Java Fundamentals Certification",
      "status": "PENDING",
      "creationSource": "LEARNER",
      "createdAt": "2026-04-14T08:30:00.000Z",
      "modifiedAt": "2026-04-16T11:45:00.000Z",
      "fields": [ "...resolved against live settings..." ]
    },
    "relationships": {
      "reviewerUser": { "data": null }
    }
  }
}
```

### Creare un inoltro

```
POST /primeapi/v2/externalLearnings
```

Crea un nuovo invio di apprendimento esterno in stato IN SOSPESO. Tutti i campi obbligatori definiti nelle impostazioni dell’account devono essere inclusi. Dopo un POST riuscito, il manager dell’Allievo riceve una notifica nella piattaforma per esaminare l’invio.

### **Caricamento file**

Il campo degli allegati viene gestito separatamente dagli altri campi. Non includerlo nei campi []. Invece:

&#x200B;1. Ottenere un URL di caricamento S3 pre-firmato dall&#39;endpoint di caricamento del file ALM.

&#x200B;2. Carica il file in tale URL.

&#x200B;3. Passa l’URL risultante come attributo submissionUrl di primo livello nella richiesta POST.

#### **Corpo della richiesta**

```
{
  "data": {
    "type": "externalLearning",
    "attributes": {
      "submissionUrl": "<pre-signed-upload-url>",
      "fields": [
        { "id": "title", "type": "TEXT", "value": "Java Fundamentals Certification" },
        { "id": "description_notes", "type": "TEXT", "value": "Completed via online course platform." },
        { "id": "date", "type": "TIMESTAMP", "value": { "start_date": "2026-05-01T00:00:00.000Z", "end_date": "2026-05-15T00:00:00.000Z" } },
        { "id": "score", "type": "NUMBER", "value": { "achieved_score": 88, "max_score": 100 } },
        { "id": "duration", "type": "TEXT", "value": "40 hours" },
        { "id": "960369b2-...", "type": "NUMBER", "value": "1225" },
        { "id": "3c6cc6d9-...", "type": "DROPDOWN", "value": "opt_3" }
      ]
    }
  }
}
```

#### Forme valore campo

| **Tipo di campo** | **Forma valore** | **Esempio** |
|----------------|---------------------------------------------------------|----------------------------------------------------------------|
| TESTO | Stringa | &quot;Nozioni di base su Java&quot; |
| NUMERO | Oggetto con achievements_score e max_score | { &quot;completed_score&quot;: 88, &quot;max_score&quot;: 100 } |
| MARCA TEMPORALE | Oggetto con start_date e end_date (ISO 8601 o null) | { &quot;start_date&quot;: &quot;2026-05-01T00:00:00.000Z&quot;, &quot;end_date&quot;: null } |
| MENU A DISCESA | stringa option_id da impostazioni account | &quot;opt_3&quot; |
| FILE_UPLOAD | Non consentito nei campi []: utilizzare submissionUrl | — |

#### POST delle regole di convalida

| **#** | **Convalida** | **Attivazione** |
|-------|-----------------------------------------------------------------|----------------------------------------------------------|
| 1 | L’apprendimento esterno è abilitato per l’account | Flag di funzionalità disattivato |
| 2 | Tutti i campi obbligatori sono presenti nei campi [] | Campo obbligatorio omesso |
| 3 | Ogni forma ID campo, tipo e valore corrisponde alle impostazioni dell’account | Tipo errato o oggetto con valore non valido |
| 4 | Tipo FILE_UPLOAD non presente nei campi[] | Allegato inviato all&#39;interno dei campi [] invece di submissionUrl |
| 5 | submissionUrl è un URL valido prefirmato S3 | URL CDN e URL non S3 rifiutati al momento della creazione |
| 6 | submissionUrl presente quando attachments.mandatory è true | Gli allegati sono obbligatori, ma l&#39;URL di invio è mancante |

### Aggiornare un inoltro

```
PUT /primeapi/v2/externalLearnings/{id}
```

Aggiorna un inoltro in SOSPESO esistente. È possibile aggiornare solo gli invii IN SOSPESO. Se si tenta di applicare il PUT a un inoltro APPROVATO o RIFIUTATO, viene restituito un errore 409.

**Questo endpoint utilizza la semantica di sostituzione completa.** Fornire la matrice completa dei campi [] in ogni richiesta PUT, non solo i campi che si stanno modificando. I campi omessi dalla matrice vengono cancellati.

#### Campi che l’Allievo può aggiornare

| **Campo / attributo** | **L’Allievo può aggiornare** | **Note** |
|-----------------------|------------------------|----------------------------------------------------------------------------|
| campi[] | Sì | Sostituzione completa: include tutti i campi, non solo quelli modificati |
| submissionUrl | Sì | Gli URL CDN vengono accettati in PUT; gli URL prefirmati S3 sono obbligatori solo in POST |
| reviewerUserId | No | Impostazione eseguita dal manager; sola lettura per l’Allievo |
| reviewedAt | No | Impostazione eseguita dal manager; sola lettura per l’Allievo |
| reviewerComment | No | Impostazione eseguita dal manager; sola lettura per l’Allievo |
| stato | No | Controllato dal manager: IN SOSPESO → APPROVATO o RIFIUTATO |
| creationSource | No | Allievo sempre per gli invii creati tramite API |
| createdAt | No | Impostato al momento della creazione; immutabile |

#### Corpo della richiesta

```
{
  "data": {
    "type": "externalLearning",
    "attributes": {
      "submissionUrl": "<cdn-url>/cert-v2.pdf",
      "fields": [
        { "id": "title", "type": "TEXT", "value": "Java Fundamentals — Updated" },
        { "id": "description_notes", "type": "TEXT", "value": "Updated notes." },
        { "id": "date", "type": "TIMESTAMP", "value": { "start_date": null, "end_date": null } },
        { "id": "score", "type": "NUMBER", "value": { "achieved_score": 92, "max_score": 100 } },
        { "id": "duration", "type": "TEXT", "value": "42 hours" },
        { "id": "960369b2-...", "type": "NUMBER", "value": "1227" },
        { "id": "3c6cc6d9-...", "type": "DROPDOWN", "value": "opt_2" }
      ]
    }
  }
}
```

## API per ID di certificazione e ID di certificazione principale pertinenti per gli Allievi in LT

Quando una certificazione ricorrente si rinnova, Adobe Learning Manager crea una nuova versione della certificazione e vi iscrive automaticamente gli Allievi attivi. Se l’integrazione richiede direttamente i dati di certificazione anziché basarsi sull’esperienza dell’Allievo in Adobe Learning Manager, è possibile utilizzare questa API per determinare con esattezza quale versione di una certificazione ricorrente è rilevante per uno specifico Allievo in qualsiasi momento.

### Scopo dell’API

Le certificazioni ricorrenti generano un nuovo ID di certificazione ogni volta che vengono rinnovate. Nell’esperienza nativa di un Allievo Adobe Learning Manager, viene visualizzata solo la versione relativa a ciascun Allievo. Le versioni precedenti venivano nascoste automaticamente quando un Allievo passava a una più recente.

Se l&#39;integrazione recupera i dati di certificazione in modo indipendente, ad esempio per visualizzare le informazioni di certificazione su un portale esterno, è possibile che non applichi automaticamente questo filtro. Senza tale certificazione, un Allievo poteva visualizzare tutte le versioni storiche di una certificazione ricorrente, comprese quelle che non lo riguardavano più, senza alcuna indicazione su cui agire.

Questa API ha risolto tale lacuna. Dato l’ID di certificazione principale, restituisce la versione della certificazione specifica che si applica a un determinato Allievo, tenendo conto della cronologia di iscrizione e di eventuali ricorrenze.

### Informazioni sulla ricorrenza della certificazione

Quando una certificazione è configurata per essere ricorrente, ogni rinnovo crea una nuova versione della certificazione con il proprio ID univoco. Tutte le versioni riconducono a un singolo **ID di certificazione radice** l&#39;ID della certificazione originale al momento della creazione.

Ad esempio, una certificazione che si ripete ogni mese può produrre una sequenza di versioni nel tempo, in cui ogni nuova versione viene generata automaticamente al raggiungimento dell&#39;intervallo di ricorrenza. Gli Allievi iscritti attivamente quando si verifica una ricorrenza vengono iscritti automaticamente alla nuova versione.

Poiché ogni versione ha un ID distinto, la versione pertinente di un Allievo dipende dalla propria tempistica di iscrizione individuale:

- Un Allievo che si è iscritto prima di una ricorrenza e ha completato la certificazione prima della ricorrenza successiva si sarà spostato con diverse versioni nel tempo.

- Un Allievo che si iscrive in modo parziale durante un ciclo di ricorrenza viene iscritto direttamente a qualsiasi versione corrente al momento dell’iscrizione.

### Determinare la versione di certificazione pertinente

Utilizza l’API della versione di certificazione per identificare la versione di una certificazione ricorrente rilevante per un Allievo specifico.

Fornire l&#39;**ID certificazione radice** come input. L’API valuta la cronologia di iscrizione dell’Allievo e restituisce la versione appropriata in base alle seguenti regole:

| **Stato Allievo** | **Elementi restituiti dall&#39;API** |
|--------------------------------------------------|----------------------------------------------------------------------------------------------------------------------------------------------|
| L’Allievo non è ancora iscritto alla certificazione | L’ultima versione disponibile della certificazione |
| L’Allievo è attualmente iscritto | La versione specifica a cui l’Allievo è attualmente iscritto, tenendo conto di eventuali ricorrenze verificatesi dopo la sua iscrizione originale. |

Ciò significa che due Allievi che eseguono contemporaneamente una query sullo stesso ID di certificazione principale possono ricevere risultati diversi, a seconda della cronologia di iscrizione individuale di ciascun Allievo.

**Nota**: durante la creazione della nuova versione e la migrazione delle iscrizioni potrebbe essere presente una breve finestra durante una ricorrenza in cui l&#39;API potrebbe restituire la versione che sta per essere sostituita anziché quella appena creata.

**Esempio**

Si consideri una certificazione che ricorre mensilmente, in cui sono state create quattro versioni nel tempo a causa di ricorrenze successive:

- Un Allievo che si è iscritto alla prima versione e ha compiuto ogni ricorrenza man mano che si verificava verrà restituito alla versione, in cui è attualmente attivo, che riflette la propria cronologia di completamento e ricorrenza, non necessariamente l’ultima versione esistente.

- Se un Allievo non si è ancora iscritto, verrà ripristinata la versione creata più di recente, in quanto questa è la versione a cui devono iscriversi le nuove iscrizioni.

Ciò consente all’integrazione di indirizzare sempre un Allievo alla versione di certificazione a lui pertinente, anziché mostrare ogni versione storica o indovinare quale sia applicabile.

### Riferimento API

**Ottenere la certificazione applicabile per una certificazione radice**

```
GET /primeapi/v2/learningObjects/{loId}/applicableCertification
```

Risolve la versione della certificazione che si applica all’Allievo corrente, dato l’ID di una certificazione radice. Per gli Allievi iscritti, restituisce la versione a cui sono attualmente iscritti. Per gli Allievi non iscritti, questa opzione restituisce la versione attiva più recente.

| **Proprietà** | **Valore** |
|----------------------------------------------------------|--------------------------|
| **Ambito** | Accesso in lettura da parte dell’Allievo |
| **Limite di frequenza (chiamate standard degli allievi)** | 70 richieste al minuto |
| **Limite di velocità (credenziali API elevate o a livello di amministratore)** | 500 richieste all&#39;ora |
| **Formato risposta** | application/vnd.api+json |

**Nota**: questa API restituisce informazioni sulla versione per un singolo Allievo alla volta. Non restituisce un elenco di tutte le versioni di una certificazione.

**Parametri del percorso**

| **Parametro** | **Obbligatorio** | **Tipo** | **Descrizione** |
|---------------|--------------|----------|---------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| loId | Sì | stringa | L’ID dell’oggetto di apprendimento, in particolare la certificazione principale, per la quale viene richiesta la versione applicabile. Questo è soggetto alle autorizzazioni di accesso standard. |

**Parametri di query**

| **Parametro** | **Obbligatorio** | **Tipo** | **Descrizione** |
|---------------|--------------|----------|---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| includere | No | stringa | Elenco separato da virgole di modelli correlati da includere nella risposta insieme alla certificazione risolta, ad esempio gli oggetti di apprendimento secondari o l&#39;iscrizione. Utilizza la stessa sintassi di inclusione degli altri endpoint degli oggetti di apprendimento Adobe Learning Manager. |

**Esempio di richiesta**

```
GET /primeapi/v2/learningObjects/certification%3A167658/applicableCertification?include=subLOs
Accept: application/vnd.api+json
Authorization: oauth <access-token>
```

```
curl -X GET --header 'Accept: application/vnd.api+json' \
--header 'Authorization: oauth <access-token>' \
'https://<host>/primeapi/v2/learningObjects/certification%3A167658/applicableCertification?include=subLOs'
```

**Nota**: il valore loId deve essere codificato con URL. I due punti in un ID di certificazione, ad esempio certificazione:167658, sono codificati come %3A.

**Esempio di risposta 200 OK**

La risposta utilizza la stessa struttura di una risposta standard all’oggetto di apprendimento e restituisce la certificazione risolta.

**Importante:** il campo ID nella risposta è l’ID della certificazione **risolta**, ovvero la versione specifica applicabile a questo Allievo. In genere sarà diverso dall’ID di certificazione principale che hai passato come loId, poiché lo scopo di questa API è quello di tradurre un ID principale nella versione corrente corretta.

```
{
  "data": {
    "id": "string",
    "type": "string",
    "attributes": {
      "authorNames": [
        "string"
      ],
      "bannerUrl": "string",
      "catalogs": [
        ...
      ]
    }
  }
}
```

**Codici di risposta**

| **Stato** | **Significato** |
|------------|---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| 200 | La certificazione applicabile è stata risolta e viene restituita in risposta. |
| 400 | L’loId fornito non è una certificazione o non è una certificazione radice. Passa l’ID della certificazione originale, non una versione di ricorrenza, come loId. |
| 401 / 403 | Nella richiesta mancano le credenziali dell’Allievo valide o le credenziali non dispongono dell’accesso richiesto. |
| 404 | Non è stato possibile risolvere alcuna certificazione attiva per questa certificazione radice. Ad esempio, perché ogni versione della catena è stata ritirata o eliminata oppure perché la certificazione non ha alcun riferimento di certificazione radice registrato. Può verificarsi anche un errore 404 se una versione viene risolta correttamente, ma l’Allievo chiamante non ha accesso al catalogo. |
| 500 | Errore imprevisto del server durante la risoluzione della certificazione. Riprovare a eseguire la richiesta. Se l&#39;errore persiste, contattare il supporto tecnico. |

**Esempio di risposta di errore**

```
{
  "meta": {
    "error": "string",
    "detail": "string"
  }
}
```

**Nota:** questa API risolve la versione per un Allievo per chiamata. Non restituisce un elenco di tutte le versioni esistenti per una certificazione radice.

**Punti importanti**

- **Certificazioni non ricorrenti: se** loId passato è una certificazione che non è configurata per la ricorrenza, l&#39;API restituisce la certificazione stessa.

- **Versioni intermedie ignorate: se** l’iscrizione attiva di un Allievo viene spostata direttamente da una versione precedente a una successiva senza un’iscrizione attiva tra, l’API si risolve ancora correttamente nella versione corrente effettiva dell’Allievo. La presenza di versioni intermedie che l’Allievo non utilizzava attivamente non influisce sulla risoluzione.

- **Certificazioni eliminate rispetto a quelle ritirate:** una versione della certificazione eliminata è completamente esclusa dalla risoluzione. Una certificazione ritirata può comunque essere considerata a seconda del suo stato; se si fa affidamento su una versione specifica che rimane risolvibile, confermare il suo stato corrente invece di assumere che il solo ritiro la rimuova dalla considerazione.

- **La risoluzione è deterministica:** se i dati di iscrizione di un Allievo sono in uno stato incoerente (ad esempio, più di un’iscrizione è contrassegnata come corrente), l’API si risolve nella versione creata più di recente, anziché restituire un risultato imprevedibile o un errore.

**Nota**: un equivalente con ambito amministratore di questa API non è attualmente disponibile ed è in fase di valutazione per una versione futura.

### Utilizza questa API nell’integrazione

Uno use case comune è una pagina o un portale esterno in cui sono elencate le certificazioni a cui un Allievo può accedere. Invece di collegarti direttamente a uno specifico ID di certificazione, che potrebbe diventare obsoleto dopo una ricorrenza. Esegui il collegamento utilizzando l’ID di certificazione principale e risolvi la versione corretta quando l’Allievo la seleziona.

1.Memorizzare o fare riferimento alle certificazioni nell&#39;integrazione utilizzando **l&#39;ID di certificazione radice** l&#39;ID della certificazione creato inizialmente, prima di qualsiasi ricorrenza.

&#x200B;2. Quando un Allievo seleziona una certificazione da visualizzare o su cui agire, chiama GET /primeapi/v2/learningObjects/{loId}/applicableCertification, passando l’ID della certificazione principale come loId.

&#x200B;3. Utilizza la versione di certificazione restituita nella risposta per indirizzare l’Allievo alla destinazione corretta, che si tratti di un’azione di iscrizione o di una visualizzazione dell’avanzamento corrente.

Ciò garantisce che gli Allievi ottengano sempre la versione della certificazione che corrisponde alla loro iscrizione e al loro avanzamento effettivi, anche se la certificazione si ripete nel tempo e genera nuove versioni.

## Report: ID del corso di formazione principale nella Trascrizione Allievo

Per impostazione predefinita, la colonna **ID del corso di formazione radice** è disponibile nella Trascrizione Allievo per tutti gli account.

| **Tipo di riga** | **Valore ID corso radice** |
|-----------------------------------------------------------------|--------------------------------------------------------------------------------|
| Certificazione configurata per la ricorrenza | ID di certificazione radice a cui viene ricondotta questa versione |
| Certificazione non configurata per la ricorrenza | Lo stesso valore dell’ID del corso di formazione per quella riga |
| Un corso incorporato in una certificazione | ID della certificazione principale, non ID del corso |
| Un corso o un percorso di apprendimento che non fa parte di alcuna certificazione | Lo stesso valore dell’ID del corso di formazione o dell’ID del corso incorporato per quella riga |

**Nota**: per gli account di grandi dimensioni con un volume elevato di certificazioni, i valori dell’ID del corso di formazione principale nelle trascrizioni degli Allievi vengono risolti in batch. Questo non modifica l&#39;accuratezza dei dati, ma la generazione di trascrizioni molto grandi potrebbe richiedere più tempo.

Questa colonna consente di raggruppare e generare report sulla cronologia completa di un Allievo in ogni versione di una certificazione ricorrente, anziché trattare ogni ricorrenza come un record indipendente e non correlato. Ogni ricorrenza viene comunque visualizzata come riga propria nella Trascrizione Allievo. La colonna ID del corso di formazione principale identifica semplicemente le righe appartenenti alla stessa certificazione sottostante.

**Nota:** utilizza la colonna ID del corso di formazione principale quando devi tracciare la cronologia completa delle partecipazioni di un Allievo in una certificazione ricorrente.

