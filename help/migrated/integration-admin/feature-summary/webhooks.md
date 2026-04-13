---
jcr-language: en_us
title: Webhook
description: Informazioni sui webhook per inviare informazioni in tempo reale, come iscrizioni a corsi, creazione di corsi e altre informazioni, a un URL specifico
contentowner: chandrum
exl-id: 472aaf2b-9c2f-4f43-a791-2b2d81e69471
source-git-commit: 3b35c16d74c83329cee24ee9ad007a53ccbd8cf3
workflow-type: tm+mt
source-wordcount: '1633'
ht-degree: 0%

---

# Webhook

Un webhook consente a un’entità di inviare automaticamente dati o notifiche in tempo reale a un’altra entità quando si verifica un evento specifico. Ciò consentirà a un&#39;applicazione di fornire informazioni ad altre applicazioni senza richiederle costantemente. Ad esempio, se un utente completa un corso LMS (Learning Management System), un webhook può inviare automaticamente tali informazioni a un’altra piattaforma, ad esempio un CRM o uno strumento di reporting. I webhook sono spesso utilizzati nelle integrazioni per automatizzare i processi e ridurre la necessità di aggiornamenti manuali tra i sistemi. Configura i webhook fornendo un URL di richiamata a cui invieresti i dati.

## Webhook e API

I webhook e le API aiutano i sistemi a comunicare tra loro, ma funzionano in modi diversi. Con le API, le informazioni vengono condivise solo quando l’utente le richiede. Ad esempio, se un Allievo richiede i dati di avanzamento del corso, invia una richiesta all’API, che fornisce le informazioni. D’altra parte, i webhook inviano automaticamente i dati immediatamente quando si verifica un evento. Ad esempio, se un Allievo completa un corso, invierà immediatamente i dati all’URL del listener senza alcuna richiesta manuale.

## Cosa sono le API in tempo reale?

Le API in tempo reale consentono alle applicazioni di scambiarsi istantaneamente i dati quando si verifica un evento. A differenza delle API tradizionali, che aspettano che un utente richieda informazioni, le API in tempo reale condividono i dati nel momento in cui si verificano. I webhook agiscono come API in tempo reale e aiutano a condividere i dati immediatamente ogni volta che si verifica l’evento specificato. L&#39;API in tempo reale garantisce che il trasferimento dei dati avvenga immediatamente senza necessità di alcuna richiesta manuale, consentendo ai sistemi di rimanere aggiornati all&#39;istante.

## Eventi webhook

Gli eventi webhook sono azioni specifiche che si verificano in un sistema che invia automaticamente i dati a un URL del listener. Ad esempio, quando un Allievo si iscrive a un corso, viene attivato un evento webhook che invia i dettagli dell’iscrizione all’URL del listener.

Gli eventi webhook sono classificati in due categorie:

* **Eventi in tempo reale**: gli eventi vengono elaborati e inviati in tempo reale a un URL di destinazione
* **Eventi non in tempo reale**: gli eventi vengono elaborati in batch e inviati in orari specifici anziché in tempo reale

## URL listener

Un URL del listener è un endpoint o una destinazione che riceve informazioni sui dati quando si verifica un evento. Ogni volta che si verifica un evento specifico, ad esempio l’iscrizione di un utente a un corso, il sistema invia automaticamente i dettagli a questo URL senza alcuna richiesta manuale. L’URL del listener è l’indirizzo a cui vengono inviati tutti questi aggiornamenti.
Webhook invia le informazioni pertinenti in formato JSON. Ecco un payload di esempio per un evento attivato in Adobe Learning Manager:

```
{
  "accountId": 1010,
  "events": [
    {
      "eventId": "d5fb7071-10a9-46b2-9f9e-79dde346c052",
      "eventName": "COURSE_ENROLLMENT_BATCH",
      "timestamp": 1727414643000,
      "eventInfo": "1727414643000-047210-84242-0",
      "data": {
        "userId": 4279332,
        "loId": "course:7374992",
        "loInstanceId": "course:7376092_10250977",
        "loType": "course",
        "enrollmentSource": "ADMIN_ENROLL",
        "dateEnrolled": 1727414643
      }
    }
  ]
}
```

## Creazione e gestione dei webhook - Amministratore dell’integrazione

Segui i passaggi seguenti per creare l’integrazione Webhook in Adobe Learning Manager:

1. Accedi come **[!UICONTROL Amministratore dell’integrazione]**.
2. Nella pagina principale, seleziona **[!UICONTROL Webhook]** > **[!UICONTROL Aggiungi webhook]**.

   ![](assets/create-webhook.png)
   _Aggiungi un webhook_

3. Digita **[!UICONTROL Nome]** e **[!UICONTROL Descrizione]** del webhook.
4. Digitare l&#39;URL del listener come **[!UICONTROL URL di destinazione]** in cui si desidera passare i dati dell&#39;evento.
5. Seleziona uno dei metodi di autenticazione:
L’autenticazione nei webhook è un metodo di sicurezza per garantire che i dati inviati a un URL listener provengano da una fonte attendibile.
   * **[!UICONTROL Nessuno]**: nessuna autenticazione richiesta.
   * **[!UICONTROL Base]**: autenticazione basata su credenziali. Immetti il nome utente e la password.
   * **[!UICONTROL Firma]**: il sistema crea una firma speciale e la aggiunge ai dati del webhook. Il server ricevente controlla il codice per verificare che i dati siano reali e che non siano stati modificati. Genera una firma da utilizzare per l’autenticazione. Scarica la firma come JSON.
6. Seleziona gli eventi Webhook dal menu a discesa **[!UICONTROL Eventi trigger]**.

   >[!NOTE]
   >
   >Puoi anche testare i webhook selezionando l’opzione Verifica webhook dalla pagina Aggiungi webhook.

7. Seleziona l&#39;interruttore **[!UICONTROL Stato attivazione]** per abilitare il webhook. Una volta abilitata, i dati verranno passati ogni volta che si verificano gli eventi selezionati.

>[!NOTE]
>
>Puoi creare e gestire fino a 5 webhook.

### Modifica webhook - Amministratore dell’integrazione

Segui questi passaggi per modificare i webhook da Adobe Learning Manager:

1. Accedi come **[!UICONTROL Amministratore dell’integrazione.]**
2. Seleziona **[!UICONTROL Webhook]** nella pagina principale.
3. Seleziona il webhook da modificare.

   ![](assets/edit-webhook.png)
   _Modificare il webhook_
4. Seleziona **[!UICONTROL Modifica]** per modificare i dettagli del webhook e seleziona **[!UICONTROL Salva]**.

### Rimuovere I Webhook - Amministratore Dell’Integrazione

Segui questi passaggi per modificare i webhook da Adobe Learning Manager:

1. Accedi come **[!UICONTROL Amministratore dell’integrazione]**.
2. Seleziona **[!UICONTROL Webhook]** nella pagina principale.
3. Seleziona il webhook da eliminare.
4. Seleziona **[!UICONTROL Elimina]** per rimuovere i webhook.

![](assets/delete-webhooks.png)
_Rimuovi il webhook_

### Rimozione dei webhook - Amministratore dell’integrazione

Segui questi passaggi per ritirare i webhook:

1. Accedi come **[!UICONTROL Amministratore dell’integrazione]**.
2. Seleziona **[!UICONTROL Webhook]** nella pagina principale.
3. Seleziona il webhook da modificare.
4. Seleziona **[!UICONTROL Modifica]** e disabilita **[!UICONTROL Stato attivazione]** per ritirare il webhook.

![](assets/retire-webhook.png)
_Rimozione del webhook_

## Webhook per alternative {#webhooks-for-alternates}

ALM fornisce eventi webhook dedicati per completamenti alternativi per supportare automazione, integrazioni e sincronizzazione con sistemi esterni.

Questi eventi consentono ai consumatori esterni di distinguere in modo affidabile tra completamenti diretti e completamenti concessi attraverso relazioni alternative.

### Panoramica

Quando un Allievo completa un corso tramite un’alternativa o una relazione, ALM attiva un evento webhook separato dal webhook di completamento del corso standard. Ciò garantisce che le integrazioni possano rispondere in modo diverso a completamenti alternativi, se necessario.

Gli eventi webhook vengono attivati anche quando si verifica un completamento retroattivo o un incompletamento retroattivo, che copre gli aggiornamenti storici e le modifiche delle relazioni.

### Comportamento evento webhook

* Un evento webhook distinto viene attivato quando un Allievo riceve lo stato Completato tramite Alternativa per un corso di destinazione.
* L’evento viene generato quando l’Allievo completa un corso di origine configurato che soddisfa la destinazione tramite una relazione alternativa.
* Questo webhook non viene attivato per il completamento diretto del corso.
* Quando l’opzione completamento retroattivo o incompletamento retroattivo è abilitata, gli eventi webhook vengono emessi per ogni Allievo interessato e corso di destinazione.

### Dettagli payload webhook

Il payload del webhook di completamento alternativo include i seguenti attributi chiave:

* **ID Allievo**
Identifica l’Allievo che ha ricevuto il completamento alternativo.
* **Corso di origine**
Il corso o il percorso di apprendimento completato direttamente dall’Allievo.
* **Corso di destinazione**
Il corso contrassegnato come completato tramite la relazione alternativa.
* **Metodo di completamento**
Indica che il metodo di completamento è alternativo.
* **Data di completamento**
Derivato dalla data di completamento del corso di origine.
* **Tipo di relazione**
Specifica se la relazione è alternativa.

Per gli scenari di incompletamento retroattivo, gli eventi webhook indicano che un completamento alternativo esistente è stato revocato.

### Considerazioni sull&#39;integrazione

I sistemi esterni possono utilizzare questi eventi webhook per:

* Aggiorna record Allievo
* Sincronizzare lo stato di completamento
* Attivare notifiche o flussi di lavoro a valle
* Gestisci audit trail per scopi di conformità

I consumatori di webhook devono distinguere esplicitamente tra completamenti diretti e alternativi.

I completamenti alternativi non assegnano premi per abilità, distintivi e gamification. Il feedback dovrebbe essere gestito di conseguenza nei sistemi a valle.

## Webhook per percorsi di apprendimento adattativi

### Introduzione

Adobe Learning Manager fornisce **eventi webhook** che avvisano i sistemi esterni ogni volta che lo stato di completamento di un **percorso di apprendimento (programma di apprendimento)** viene aggiornato. Ciò consente di sincronizzare i sistemi a valle (come le piattaforme HR, di reporting o di analisi) ogni volta che il record di completamento di un Allievo viene ripristinato o ricalcolato.

Sono disponibili due nuovi tipi di evento webhook:

**LEARNING_PATH_COMPLETION_ROLLBACK** - Viene attivato quando un **Allievo** aggiorna lo stato di completamento di un percorso di apprendimento.

**LEARNING_PATH_COMPLETION_ROLLBACK_BATCH** - Viene attivato quando un **amministratore** aggiorna lo stato di completamento di un percorso di apprendimento per **uno o più Allievi** (ad esempio, tramite operazioni in blocco).

Questi eventi utilizzano una **struttura di payload comune** e possono essere utilizzati dall&#39;endpoint del webhook per aggiornare o rielaborare i dati di completamento sul tuo lato.

### Struttura comune del payload

Ogni richiesta webhook contiene la seguente struttura a livelli:

```
{
  "accountId": 69735,
  "events": [
    {
      "eventId": "757b9d58-048c-4ae2-9fff-35f9def7ef29",
      "eventName": "LEARNING_PATH_COMPLETION_ROLLBACK",
      "timestamp": "2026-01-20T05:48:10.000Z",
      "eventInfo": "1768888090000-197513-137581-0",
      "data": {
        "userId": 13446697,
        "loId": "learningProgram:157165",
        "loInstanceId": "learningProgram:157165_148769",
        "loType": "learningProgram",
        "enrollmentSource": "SELF_ENROLL",
        "dateEnrolled": "2026-01-20T05:44:05.000Z"
      }
    }
  ]
}
```

La **stessa struttura** è utilizzata per entrambi i tipi di evento; solo eventName e i valori all&#39;interno dei dati (ad esempio, userId, loId, enrollmentSource) sono diversi.

#### Esempio: aggiornamento avviato dall’Allievo

Quando un Allievo aggiorna lo stato di completamento del proprio percorso di apprendimento, il webhook invia un evento LEARNING_PATH_COMPLETION_ROLLBACK:

```
{
  "accountId": 69735,
  "events": [
    {
      "eventId": "757b9d58-048c-4ae2-9fff-35f9def7ef29",
      "eventName": "LEARNING_PATH_COMPLETION_ROLLBACK",
      "timestamp": "2026-01-20T05:48:10.000Z",
      "eventInfo": "1768888090000-197513-137581-0",
      "data": {
        "userId": 13446697,
        "loId": "learningProgram:157165",
        "loInstanceId": "learningProgram:157165_148769",
        "loType": "learningProgram",
        "enrollmentSource": "SELF_ENROLL",
        "dateEnrolled": "2026-01-20T05:44:05.000Z"
      }
    }
  ]
}
```

Utilizza questo evento per **ricalcolare o ripristinare i dati di completamento dell’Allievo** nei sistemi esterni quando l’Allievo richiede esplicitamente un aggiornamento.

#### Esempio: aggiornamento batch avviato dall&#39;amministratore

Quando un Amministratore esegue un aggiornamento di completamento per uno o più Allievi (ad esempio, la correzione dei completamenti storici per un gruppo), il webhook genera un evento LEARNING_PATH_COMPLETION_ROLLBACK_BATCH:

```
{
  "accountId": 69735,
  "events": [
    {
      "eventId": "757b9d58-048c-4ae2-9fff-35f9def7ef29",
      "eventName": "LEARNING_PATH_COMPLETION_ROLLBACK_BATCH",
      "timestamp": "2026-01-20T05:48:10.000Z",
      "eventInfo": "1768888090000-197513-137581-0",
      "data": {
        "userId": 13446698,
        "loId": "learningProgram:157166",
        "loInstanceId": "learningProgram:157166_148770",
        "loType": "learningProgram",
        "enrollmentSource": "ADMIN_ENROLL",
        "dateEnrolled": "2026-01-21T05:44:05.000Z"
      }
    }
  ]
}
```

Nelle operazioni in batch, l’endpoint del webhook può ricevere **più oggetti evento in un’unica richiesta**, uno per Allievo il cui completamento è stato aggiornato. L’integrazione deve scorrere l’array degli eventi ed elaborare ogni evento in modo indipendente.

### Come utilizzare questi eventi nelle integrazioni

Puoi utilizzare questi eventi webhook per:

**Sincronizzare i record di completamento** con LMS/LRS, HR o sistemi di reporting esterni quando un completamento viene ripristinato o ricalcolato.

**Attiva flussi di lavoro a valle** quali riassegnazioni, notifiche o ricalcolo di certificazioni e distintivi.

**Gestisci audit trail** registrando eventId, timestamp ed eventInfo insieme agli identificatori dell’Allievo e del percorso di apprendimento.

Come minimo, il gestore del webhook deve:

Convalida gli eventi payload e parse[].
Utilizzare eventName per determinare se la modifica è stata **learnerstarted** o **admin/batchstarted**.

Utilizza userId, loId e loInstanceId per individuare e aggiornare il record corrispondente nel sistema.
Utilizzo di eventId per impedire elaborazioni duplicate se lo stesso evento viene recapitato più di una volta.

## Webhook per l’aggiunta e la rimozione dell’iscrizione al gruppo di utenti

Due nuovi tipi di evento webhook hanno gli stati finali:

* RISPOSTA:ASYNCAPI_USERGROUP_USER_ADDED
* RISPOSTA:ASYNCAPI_USERGROUP_USER_REMOVED

### Payload di esempio

```
{
  "accountId": 69735,
  "events": [
    {
      "eventId": "cd2972c8-cb15-47a0-a23f-e4a16cb720f5",
      "eventName": "RESPONSE:ASYNCAPI_USERGROUP_USER_REMOVED",
      "timestamp": "2026-03-18T13:38:12.000Z",
      "eventInfo": "cd2972c8-cb15-47a0-a23f-e4a16cb720f5",
      "data": {
        "status": "SUCCESS",
        "request": {
          "metadata": { "event_id": "cd2972c8-cb15-47a0-a23f-e4a16cb720f5" },
          "data": [ { "type": "user", "id": "13446641" } ]
        }
      }
    }
  ]
}
```

### Elementi chiave

* `accountId` identifica l&#39;account ALM.
* `events` è una matrice di oggetti evento.
* `eventId` corrisponde all&#39;identificatore della richiesta asincrona originale.
* `eventName` indica un&#39;operazione di aggiunta o rimozione.
* `timestamp` indica l&#39;ora di completamento.
* `data.status` attualmente segnala &quot;OPERAZIONE COMPLETATA&quot; per i batch completati.
* `data.request` contiene la richiesta esatta che hai inviato.

La tua integrazione deve principalmente escludere `eventId` (o `metadata.event_id`) e `status`.

### Esempi

#### Aggiunta asincrona di utenti

**Passaggio 1. Effettua la chiamata asincrona**

POST /primeapi/v2/async/userGroups/12345/users

```
{
  "metadata": {
    "event_id": "sync-2026-03-30T10:15:00Z-ug-12345",
    "sourceSystem": "HRIS",
    "batchId": "hr_2026_03_30_0001"
  },
  "data": [
    { "type": "user", "id": "11101219" },
    { "type": "user", "id": "11101220" }
  ]
}
```

**Passaggio 2. Leggi la risposta immediata**

```
{ "event_id": "sync-2026-03-30T10:15:00Z-ug-12345" }
```

Ora puoi contrassegnare questo processo come inviato nel tuo sistema.

**Passaggio 3. Gestire il webhook**

Esempio di callback webhook:

```
{
  "accountId": 69735,
  "events": [
    {
      "eventId": "sync-2026-03-30T10:15:00Z-ug-12345",
      "eventName": "RESPONSE:ASYNCAPI_USERGROUP_USER_ADDED",
      "timestamp": "2026-03-30T10:15:43.000Z",
      "data": {
        "status": "SUCCESS",
        "request": {
          "metadata": {
            "event_id": "sync-2026-03-30T10:15:00Z-ug-12345",
            "sourceSystem": "HRIS",
            "batchId": "hr_2026_03_30_0001"
          },
          "data": [
            { "type": "user", "id": "11101219" },
            { "type": "user", "id": "11101220" }
          ]
        }
      }
    }
  ]
}
```

Un consumatore tipico:

* Individuare il processo interno.
* È possibile verificare l&#39;appartenenza utilizzando GET /userGroups/{id}/users.
* Contrassegna il processo come completato.

#### Rimozione asincrona degli utenti

La rimozione è simmetrica, utilizzando DELETE con la stessa struttura del corpo.

```
{
  "metadata": {
    "event_id": "sync-2026-03-30T11:00:00Z-ug-12345",
    "sourceSystem": "HRIS",
    "batchId": "hr_2026_03_30_0002"
  },
  "data": [ { "type": "user", "id": "11101219" } ]
}
```

Risposta immediata:

```
{ "event_id": "sync-2026-03-30T11:00:00Z-ug-12345" }
```

Più tardi, arriva un webhook RESPONSE:ASYNCAPI_USERGROUP_USER_REMOVED con lo stesso eventId.

Per ulteriori informazioni, visualizzare l&#39;[API pubblica asincrona per l&#39;appartenenza al gruppo di utenti](/help/migrated/api-changes-alm.md#asynchronous-public-apis-for-user-group-membership).
