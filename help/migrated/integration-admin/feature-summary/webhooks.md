---
jcr-language: en_us
title: Webhook
description: Informazioni sui webhook per inviare informazioni in tempo reale, come iscrizioni a corsi, creazione di corsi e altre informazioni, a un URL specifico
contentowner: chandrum
source-git-commit: e4b0526e11083d116bf4ca4b0816892e0e8f0f9d
workflow-type: tm+mt
source-wordcount: '1695'
ht-degree: 1%

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

## Eventi in tempo reale

| S.No | Eventi webhook | Descrizione |
|---|---|---|
| 1 | CI_STATS | Viene attivato quando si verifica una modifica nella disponibilità di posti o liste di attesa per un’istanza di corso. |
| 2 | COURSE_ENROLLMENT | Attivato quando un Allievo si iscrive a un corso. |
| 3 | COURSE_COMPLETED | Viene attivato quando un Allievo completa un corso. |
| 4 | LEARNING_PATH_ENROLLMENT | Attivato quando un Allievo si iscrive a un percorso di apprendimento. |
| 5 | LEARNING_PATH_COMPLETED | Viene attivato quando un Allievo completa un percorso di apprendimento. |
| 6 | CERTIFICATION_ENROLLMENT | Attivato quando un Allievo si iscrive a una certificazione. |
| 7 | CERTIFICATION_COMPLETED | Viene attivato quando un Allievo completa una certificazione. |
| 8 | COURSE_UNENROLLMENT | Attivato quando un Allievo si disiscrive da un corso. |
| 9 | LEARNING_PATH_UNENROLLMENT | Attivato quando un Allievo si annulla l’iscrizione a un percorso di apprendimento. |
| 10 | CERTIFICATION_UNENROLLMENT | Generato quando un Allievo si annulla l’iscrizione a una certificazione. |
| 11 | LEARNING_OBJECT_DRAFT | Attivato durante la creazione di un oggetto di apprendimento in stato Bozza. |
| 12 | LEARNING_OBJECT_DELETION | Attivato durante l’eliminazione di un oggetto di apprendimento. |
| 13 | LEARNING_OBJECT_MODIFICATION | Attivato durante la modifica di un oggetto di apprendimento. |
| 14 | LEARNING_OBJECT_INSTANCE_MODIFICATION | Attivato durante la creazione o la modifica di un’istanza dell’oggetto di apprendimento.<div><b>Nota:</b> si consiglia di utilizzare le istanze del corso solo dopo la pubblicazione del corso.</div> |
| 15 | LEARNING_OBJECT_INSTANCE_DELETION | Attivato durante l’eliminazione di un’istanza dell’oggetto di apprendimento. |

## Eventi non in tempo reale

| S.No | Eventi webhook | Descrizione |
|---|---|---|
| 1 | COURSE_ENROLLMENT_BATCH | Attivato quando un Amministratore/Manager/piattaforma iscrive gli Allievi a un corso. |
| 2 | COURSE_COMPLETED_BATCH | Viene attivato quando un amministratore/manager/piattaforma contrassegna un corso come completato. |
| 3 | LEARNING_PATH_ENROLLMENT_BATCH | Attivato quando un Amministratore/Manager/piattaforma iscrive gli Allievi a un percorso di apprendimento. |
| 4 | LEARNING_PATH_COMPLETED_BATCH | Viene attivato quando un Amministratore/Manager contrassegna un percorso di apprendimento come completato. |
| 5 | CERTIFICATION_ENROLLMENT_BATCH | Attivato quando un Amministratore/Manager/piattaforma iscrive gli Allievi a una certificazione. |
| 6 | CERTIFICATION_COMPLETED_BATCH | Viene attivato quando un amministratore/manager/piattaforma contrassegna una certificazione come completata. |
| 7 | LEARNER_PROGRESS | Consente di tenere traccia dell’avanzamento di un Allievo al completamento di un modulo. |
| 8 | COURSE_UNENROLLMENT_BATCH | Viene attivato quando un Amministratore/Manager/piattaforma annulla l’iscrizione di allievi a un corso. |
| 9 | LEARNING_PATH_UNENROLLMENT_BATCH | Viene attivato quando un Amministratore/Manager/piattaforma annulla l’iscrizione degli Allievi a un percorso di apprendimento. |
| 10 | CERTIFICATION_UNENROLLMENT_BATCH | Viene attivato quando un Amministratore/Manager/piattaforma annulla l’iscrizione degli Allievi a una certificazione. |
| 11 | LEARNING_OBJECT_MODIFICATION_BATCH | Attivato durante la modifica di un oggetto di apprendimento tramite il flusso di lavoro di migrazione. |
| 12 | LEARNING_OBJECT_INSTANCE_MODIFICATION_BATCH | Attivato durante la creazione o la modifica di un’istanza dell’oggetto di apprendimento tramite il flusso di lavoro di migrazione. |

## Procedure consigliate per i webhook

I webhook consentono la comunicazione in tempo reale basata sugli eventi tra i servizi. Tuttavia, un&#39;implementazione non corretta può causare perdita di eventi, rallentamento delle prestazioni del sistema o rischi per la sicurezza. Di seguito sono riportate le best practice per l’implementazione dei webhook, con particolare attenzione alla fault tolerance, all’affidabilità e alla sicurezza.

### Tolleranza di errore

La tolleranza agli errori del sistema webhook ALM fornisce raccomandazioni agli abbonati per la gestione di potenziali problemi, come perdita di eventi, eventi duplicati e recapito fuori ordine.

ALM ha un timeout di connessione configurato su 10 secondi e un timeout del socket configurato su 5 secondi. Ci si aspetta che il client riconosca il messaggio non appena lo riceve. In questo modo, il client non subirà ritardi durante l&#39;elaborazione dei messaggi. Nel caso in cui si verifichi un&#39;elaborazione a valle che richiede tempo, il client deve comunque riconoscere immediatamente l&#39;evento e quindi gestire l&#39;elaborazione a valle alla loro fine.

#### Conservazione dei dati

Gli eventi sono conservati per 7 giorni. Se non vengono elaborati entro questo periodo di tempo, vengono persi definitivamente. Se il ripristino avviene nell&#39;ultimo giorno e occorre più tempo, il sistema non estenderà il periodo di conservazione.
Se gli eventi vengono prodotti più velocemente di quanto vengono utilizzati, alcuni eventi potrebbero andare perduti. Sebbene ciò sia raro, gli abbonati devono monitorare per evitare che diventi un problema a lungo termine.

#### Webhook disabilitati

Quando un abbonato non risponde agli eventi webhook, il sistema ALM tenta di utilizzare i webhook con un backoff esponenziale per evitare di sopraffare il sottoscrittore.

Il processo di nuovo tentativo inizia con un intervallo iniziale di 5 secondi. Se l&#39;abbonato non risponde, il tempo di attesa raddoppia a 10, 20, 40 e 80 secondi, aumentando fino a un massimo di 5 minuti. Una volta raggiunti i 5 minuti, il sistema continuerà a riprovare ogni 5 minuti fino al termine del periodo di conservazione di 7 giorni. Se il sottoscrittore continua a non rispondere per tutto questo periodo, il webhook verrà disabilitato automaticamente. Un’e-mail di promemoria verrà inviata all’abbonato a intervalli regolari.

#### Eventi duplicati

Se un sottoscrittore impiega più di 5 secondi per rispondere dopo aver elaborato un evento, il sistema potrebbe tentare di elaborare nuovamente lo stesso evento. Si consiglia di utilizzare gli ID evento per tenere traccia degli eventi che sono già stati elaborati. Inoltre, se il webhook si arresta in modo anomalo dopo l’invio dell’evento ma prima del salvataggio che è stato elaborato, è possibile che venga eseguito un nuovo tentativo per lo stesso gruppo di eventi. Si consiglia di utilizzare ID batch o singoli ID evento per riconoscere e ignorare eventuali duplicati.

#### Eventi non ordinati

ALM tenta di mantenere gli eventi nell&#39;ordine corretto, ma a volte gli eventi possono essere consegnati in modo non corretto, specialmente tra eventi in tempo reale e non in tempo reale.

Se un amministratore iscrive più allievi a un corso contemporaneamente, gli eventi di iscrizione sono contrassegnati come non in tempo reale. Tuttavia, se un Allievo completa rapidamente il corso, l’evento di completamento viene contrassegnato come in tempo reale e potrebbe essere inviato prima degli eventi di iscrizione.

#### Raccomandazione per la tolleranza agli errori

Per evitare questi errori, gli abbonati devono monitorare attivamente gli eventi webhook e configurare avvisi per problemi come eventi mancati, consegne duplicate o sequenze di guasti.

## Linee guida specifiche per gli eventi Webhook

1. Se ricevi prima un evento LEARNER_PROGRESS, ignora gli eventi elencati di seguito:

   * COURSE_ENROLLMENT
   * COURSE_ENROLLMENT_BATCH
   * LEARNING_PATH_ENROLLMENT
   * LEARNING_PATH_ENROLLMENT_BATCH
   * CERTIFICATION_ENROLLMENT
   * CERTIFICATION_ENROLLMENT_BATCH

2. Ignora l’evento LEARNER_PROGRESS se si verifica dopo i seguenti eventi:

   * COURSE_COMPLETED
   * COURSE_COMPLETED_BATCH
   * LEARNING_PATH_COMPLETED
   * LEARNING_PATH_COMPLETED_BATCH
   * CERTIFICATION_COMPLETED
   * CERTIFICATION_COMPLETED_BATCH

3. Utilizzare il campo indicatore orario per determinare se ignorare o elaborare l&#39;evento, ad eccezione dell&#39;evento LEARNER_PROGRESS.


## Payload di esempio per gli eventi

+++CI_STATS

```
{
  "accountId": 1234,
  "events": [
    {
      "eventId": "01234567-0458-4450-b5dd-6bc1edr4560",
      "eventName": "CI_STATS",
      "timestamp": 1725604147,
      "eventInfo": "1725604145-LoSt",
      "data": {
        "loInstanceId": "course:1234567_123456775",
        "waitlistCount": 0,
        "enrollmentCount": 10,
        "seatLimit": 30
      }
    }
  ]
}
```

+++

+++COURSE_ENROLLMENT

```
{
  "accountId": 1234,
  "events": [
    {
      "eventId": "29123ec1-4576-4ec5-a057-3a6dr45t9d6",
      "eventName": "COURSE_ENROLLMENT",
      "timestamp": 1725524713,
      "eventInfo": "1725524713000-040366-10488-0",
      "data": {
        "userId": 1234567,
        "loId": "course:1234567",
        "loInstanceId": "course:1234567_1234567",
        "loType": "course",
        "enrollmentSource": "SELF_ENROLL",
        "dateEnrolled": 1725524713
      }
    }
  ]
  }
```

+++

+++COURSE_ENROLLMENT_BATCH

```
{
  "accountId": 1234,
  "events": [
    {
      "eventId": "29572ec1-4576-4ec5-a057-3wsd43r59d6",
      "eventName": "COURSE_ENROLLMENT_BATCH",
      "timestamp": 1725524713,
      "eventInfo": "1725524713000-040366-10488-0",
      "data": {
        "userId": 1234567,
        "loId": "course:1234567",
        "loInstanceId": "course:12345678_123456788",
        "loType": "course",
        "enrollmentSource": "ADMIN_ENROLL",
        "dateEnrolled": 1725524713
      }
    }
  ]
  }
```

+++

+++COURSE_COMPLETED

```
{
  "accountId": 1234,
  "events": [
    {
      "eventId": "c1a3168c-6c98-4ed3-b0b0-ba3da5087c1c",
      "eventName": "COURSE_COMPLETED",
      "timestamp": 1725523823,
      "eventInfo": "1725523823000-040363-12018-0",
      "data": {
        "userId": 12345678,
        "loId": "course:12345671",
        "loInstanceId": "course:1234567_12345674",
        "loType": "course",
        "enrollmentSource": "SELF_ENROLL",
        "dateCompleted": 1725523818,
        "hasPassed": true
      }
    }
  ]
}
```

+++

+++COURSE_COMPLETED_BATCH

```
{
  "accountId": 1234,
  "events": [
    {
      "eventId": "c1a3168c-6c98-4ed3-b0b0-ba3da5087c1c",
      "eventName": "COURSE_COMPLETED_BATCH",
      "timestamp": 1725523823,
      "eventInfo": "1725523823000-040363-12018-0",
      "data": {
        "userId": 112345678,
        "loId": "course:12345678",
        "loInstanceId": "course:1234567_12345678",
        "loType": "course",
        "enrollmentSource": "ADMIN_ENROLL",
        "dateCompleted": 1725523818,
        "hasPassed": true
      }
    }
  ]
}
```

+++

+++LEARNING_PATH_ENROLLMENT

```
{
  "accountId": 1234,
  "events": [
    {
      "eventId": "96ed0791-338f-4c4c-83bc-9fwfr4564965",
      "eventName": "LEARNING_PATH_ENROLLMENT",
      "timestamp": 1725604249,
      "eventInfo": "1725604248000-040653-71396-0",
      "data": {
        "userId": 11234567,
        "loId": "learningProgram:123456",
        "loInstanceId": "learningProgram:12345_134567",
        "loType": "learningProgram",
        "enrollmentSource": "SELF_ENROLL",
        "dateEnrolled": 1725604248
      }
    }
  ]
}
```

+++

+++LEARNING_PATH_ENROLLMENT_BATCH

```
{
  "accountId": 1234,
  "events": [
    {
      "eventId": "96edft791-338f-4c4c-83bc-9f7erf94965",
      "eventName": "LEARNING_PATH_ENROLLMENT",
      "timestamp": 1725604249,
      "eventInfo": "1725604248000-040653-71396-0",
      "data": {
        "userId": 12345678,
        "loId": "learningProgram:12347",
        "loInstanceId": "learningProgram:12345_12345",
        "loType": "learningProgram",
        "enrollmentSource": "ADMIN_ENROLL",
        "dateEnrolled": 1725604248
      }
    }
  ]
  }
```

+++

+++LEARNING_PATH_COMPLETED

```
{
  "accountId": 1234,
  "events": [
    {
      "eventId": "e207104e-d554-4027-944b-08fty6fdddf",
      "eventName": "LEARNING_PATH_COMPLETED",
      "timestamp": 1725604392,
      "eventInfo": "1725604391000-040653-314618-0",
      "data": {
        "userId": 11080928,
        "loId": "learningProgram:12345",
        "loInstanceId": "learningProgram:12345_95662",
        "loType": "learningProgram",
        "enrollmentSource": "SELF_ENROLL",
        "dateCompleted": 1725604380,
        "hasPassed": true
      }
    }
  ]
  }
```

+++

+++LEARNING_PATH_COMPLETED_BATCH

```
{
  "accountId": 1234,
  "events": [
    {
      "eventId": "e207104e-d554-4027-944b-086debefdddf",
      "eventName": "LEARNING_PATH_COMPLETED",
      "timestamp": 1725604392,
      "eventInfo": "1725604391000-040653-314618-0",
      "data": {
        "userId": 12345678,
        "loId": "learningProgram:12345",
        "loInstanceId": "learningProgram:12345_95662",
        "loType": "learningProgram",
        "enrollmentSource": "ADMIN_ENROLL",
        "dateCompleted": 1725604380,
        "hasPassed": true
      }
    } 
    ]
    }
```

+++

+++CERTIFICATION_ENROLLMENT

```
{
  "accountId": 1234,
  "events": [
    {
      "eventId": "8bdfr76-148e-4128-80e9-b89123456755",
      "eventName": "CERTIFICATION_ENROLLMENT",
      "timestamp": 1725604672,
      "eventInfo": "1725604672000-040654-559128-0",
      "data": {
        "userId": 12345678,
        "loId": "certification:1234567",
        "loInstanceId": "certification:123456_160299",
        "loType": "certification",
        "enrollmentSource": "SELF_ENROLL",
        "dateEnrolled": 1725604672
      }
    }
  ]
}
```

+++

+++CERTIFICATION_ENROLLMENT_BATCH

```
{
  "accountId": 1234,
  "events": [
    {
      "eventId": "8b2ee776-148e-4128-80e9-12345678",
      "eventName": "CERTIFICATION_ENROLLMENT_BATCH",
      "timestamp": 1725604672,
      "eventInfo": "1725604672000-040654-559128-0",
      "data": {
        "userId": 123456788,
        "loId": "certification:1234567",
        "loInstanceId": "certification:12345678_160299",
        "loType": "certification",
        "enrollmentSource": "ADMIN_ENROLL",
        "dateEnrolled": 1725604672
      }
    }
  ]
  }
```

+++

+++CERTIFICATION_COMPLETED

```
{
  "accountId": 1234,
  "events": [
    {
      "eventId": "b8b63bf8-7521-4bc0-bc51-7f951ff63ea9",
      "eventName": "CERTIFICATION_COMPLETED",
      "timestamp": 1725604769,
      "eventInfo": "1725604768000-040654-756257-0",
      "data": {
        "userId": 12345678,
        "loId": "certification:1245678",
        "loInstanceId": "certification:1234567_160299",
        "loType": "certification",
        "enrollmentSource": "SELF_ENROLL",
        "dateCompleted": 1725604740
      }
    }
  ]
  }
```

+++

+++CERTIFICATION_COMPLETED_BATCH

```
{
  "accountId": 1234,
  "events": [
    {
      "eventId": "b8b63bf8-7521-4bc0-bc51-7f951ff63ea9",
      "eventName": "CERTIFICATION_COMPLETED_BATCH",
      "timestamp": 1725604769,
      "eventInfo": "1725604768000-040654-756257-0",
      "data": {
        "userId": 12345678,
        "loId": "certification:134567",
        "loInstanceId": "certification:1234567_160299",
        "loType": "certification",
        "enrollmentSource": "ADMIN_ENROLL",
        "dateCompleted": 1725604740
      }
    }
  ]
  }
```

+++

+++LEARNER_PROGRESS

```
{
  "accountId": 1234,
  "events": [
    {
      "eventId": "dd04d3a4-c3df-44fa-a1cf-7edd6e3d2075",
      "eventName": "LEARNER_PROGRESS",
      "timestamp": 1725604552,
      "eventInfo": "1725604551000-297002-5823-0",
      "data": {
        "loId": "course:7542090",
        "loType": "course",
        "userId": 12345678,
        "loInstanceId": "course:1234567_11234567",
        "dateStarted": 1725604380,
        "progressPercent": 50
      }
}
]
}
```

+++

+++COURSE_UNENROLLMENT

```
{
  "accountId": 1234,
  "events": [
    {
      "eventId": "f3417817-8cb8-40ea-a441-813bec1c7724",
      "eventName": "COURSE_UNENROLLMENT",
      "timestamp": 1725515824,
      "eventInfo": "1725506253000-040298-24078-0",
      "data": {
        "userId": 12345671,
        "loId": "course:12345678",
        "loInstanceId": "course:12345678_14450088",
        "loType": "course",
        "enrollmentSource": "ADMIN_ENROLL",
      }
    }
  ]
}
```

+++

+++COURSE_UNENROLLMENT_BATCH

```
{
  "accountId": 1234,
  "events": [
    {
      "eventId": "f3417817-8cb8-40ea-a441-8123e45724",
      "eventName": "COURSE_UNENROLLMENT_BATCH",
      "timestamp": 1725515824,
      "eventInfo": "1725506253000-040298-24078-0",
      "data": {
        "userId": 123456781,
        "loId": "course:12345678",
        "loInstanceId": "course:12345678_14450088",
        "loType": "course",
        "enrollmentSource": "SELF_ENROLL"
    }
   }
  ]
}
```

+++

+++LEARNING_PATH_UNENROLLMENT

```
{
  "accountId": 1234,
  "events": [
    {
      "eventId": "8e5df878-1dfd-47ac-9bfe-7d123456d1",
      "eventName": "LEARNING_PATH_UNENROLLMENT",
      "timestamp": 1725516573,
      "eventInfo": "1725506667000-040299-28209-0",
      "data": {
        "userId": 12345678,
        "loId": "learning_program:1234567",
        "loInstanceId": "learning_program:1234567_109139",
        "loType": "learning_program",
        "enrollmentSource": "SELF_ENROLL",
       
      }
    }
]
}
```

+++

+++LEARNING_PATH_UNENROLLMENT_BATCH

```
{
  "accountId": 1234,
  "events": [
    {
      "eventId": "8e5df878-1dfd-47ac-9bfe-7d4952e3edd1",
      "eventName": "LEARNING_PATH_UNENROLLMENT",
      "timestamp": 1725516573,
      "eventInfo": "1725506667000-040299-28209-0",
      "data": {
        "userId": 1234567,
        "loId": "learning_program:1234567",
        "loInstanceId": "learning_program:1234567_109139",
        "loType": "learning_program",
        "enrollmentSource": "ADMIN_ENROLL"
      }
    }
]
}
```

+++

+++CERTIFICATION_UNENROLLMENT

```
{
  "accountId": 1234,
  "events": [
    {
      "eventId": "7902766b-54d8-472d-b933-7e89d1b75ef8",
      "eventName": "CERTIFICATION_UNENROLLMENT",
      "timestamp": 1725517341,
      "eventInfo": "1725507900000-040304-1065-0",
      "data": {
        "userId": 12345678,
        "loId": "certification:1234567",
        "loInstanceId": "certification:12345678_162078",
        "loType": "certification",
        "enrollmentSource": "SELF_ENROLL"
      }
    }
  ]
}
```

+++

+++CERTIFICATION_UNENROLLMENT_BATCH

```
{
  "accountId": 1234,
  "events": [
    {
      "eventId": "7902766b-54d8-472d-b933-7e89d1b75ef8",
      "eventName": "CERTIFICATION_UNENROLLMENT_BATCH",
      "timestamp": 1725517341,
      "eventInfo": "1725507900000-040304-1065-0",
      "data": {
        "userId": 12345678,
        "loId": "certification:1234567",
        "loInstanceId": "certification:1234567_162078",
        "loType": "certification",
        "enrollmentSource": "SELF_ENROLL"
      }
    }
  ]
}
```

+++

+++LEARNING_OBJECT_DRAFT

```
{
  "accountId": 1234,
  "events": [
    {
      "eventId": "1712349f-26ec-453c-b56a-cdf18a841948",
      "eventName": "LEARNING_OBJECT_DRAFT",
      "timestamp": 1725519188,
      "eventInfo": "1725519188000-040344-48604-0",
      "data": {
        "loId": "course:12345671",
        "loType": "course"
      }
    }
  ]
}
```

+++

+++LEARNING_OBJECT_DELETION

```
{
  "accountId": 1234,
  "events": [
    {
      "eventId": "023456-5517-4c09-9cde-d953cdd8582c",
      "eventName": "LEARNING_OBJECT_DELETION",
      "timestamp": 1725605296,
      "eventInfo": "1234567800-040656-662792-0",
      "data": {
        "loId": "course:1234567",
        "loType": "course"
      }
    }
   ]
}
```

+++

+++LEARNING_OBJECT_MODIFICATION

```
{
  "accountId": 1234,
  "events": [
    {
      "eventId": "22345668-af3e-4dd3-a515-ce19d7234873",
      "eventName": "LEARNING_OBJECT_MODIFICATION_BATCH",
      "timestamp": 1725523081,
      "eventInfo": "123456000-039736-54153-0",
      "data": {
        "loId": "learningProgram:1234567",
        "loType": "learningProgram"

      }
    }
  ]
}
```

+++

+++LEARNING_OBJECT_MODIFICATION_BATCH

```
{
  "accountId": 1234,
  "events": [
    {
      "eventId": "2234567068-af3e-4dd3-a515-ce19d7234873",
      "eventName": "LEARNING_OBJECT_MODIFICATION_BATCH",
      "timestamp": 1725523081,
      "eventInfo": "123456700-039736-54153-0",
      "data": {
        "loId": "learningProgram:1234567",
        "loType": "learningProgram"

      }
    }
  ]
}
```

+++

+++LEARNING_OBJECT_INSTANCE_MODIFICATION

```
{
  "accountId": 1234,
  "events": [
    {
      "eventId": "b131da98-ab8d-43e9-b671-e79131cd69dc",
      "eventName": "LEARNING_OBJECT_INSTANCE_MODIFICATION",
      "timestamp": 1725603298,
      "eventInfo": "1723456000-040649-741781-0",
      "data": {
        "loInstanceId": "course:12345678_14453691",
        "loId": "course:12345678",
        "loType": "course"
        
      }
    }
  ]
}
```

+++

+++LEARNING_OBJECT_INSTANCE_MODIFICATION_BATCH

```
{
  "accountId": 1234,
  "events": [
    {
      "eventId": "b23458-ab8d-43e9-b671-e79131cd69dc",
      "eventName": "LEARNING_OBJECT_INSTANCE_MODIFICATION_BATCH",
      "timestamp": 1725603298,
      "eventInfo": "112345000-040649-741781-0",
      "data": {
        "loInstanceId": "course:12345678_14453691",
        "loId": "course:1234568",
        "loType": "course"

      }
    }
  ]
}
```

+++

+++LEARNING_OBJECT_INSTANCE_DELETION

```
{
  "accountId": 1234,
  "events": [
    {
      "eventId": "1234560-d73a-457b-83f3-666ba9654edb",
      "eventName": "LEARNING_OBJECT_INSTANCE_DELETION",
      "timestamp": 1725605491,
      "eventInfo": "17223456700-040657-236307-0",
      "data": {
        "loInstanceId": "course:1234567_14453849",
        "loId": "course:1234567",
        "loType": "course"

      }
    }
  ]
}
```

+++

