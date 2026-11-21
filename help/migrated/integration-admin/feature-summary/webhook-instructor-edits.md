---
description: Ottieni eventi webhook in Adobe Learning Manager quando gli istruttori modificano i dettagli della sessione e mantengono aggiornate le notifiche degli Allievi e i sistemi connessi.
jcr-language: en_us
title: Ricezione di eventi webhook per modifiche alla sessione di istruttori
exl-id: 6fa4b71b-a8f4-40a2-ab57-bb7f3016542c
source-git-commit: 90b45cb128b74ecb33a89bf42ef4d6e960101ff0
workflow-type: tm+mt
source-wordcount: '514'
ht-degree: 0%
---

# Eventi webhook per modifiche di istanze LO da parte di istruttori

Adobe Learning Manager fornisce eventi webhook che avvisano i sistemi esterni quando viene modificata un’istanza di oggetto di apprendimento (LO), come una sessione di un corso con istruttore. In precedenza, questi eventi venivano attivati solo quando un amministratore o un autore modificava un’istanza LO. Gli eventi webhook vengono ora attivati anche quando un Istruttore modifica i dettagli di una sessione.

Puoi utilizzare questi eventi per mantenere aggiornati i sistemi esterni, ad esempio i servizi e-mail, i calendari, gli strumenti di reporting o le piattaforme di analisi con le modifiche apportate all’istruttore. Ad esempio, è possibile notificare agli Allievi le modifiche dell’orario di una sessione.

Le modifiche dell’Istruttore utilizzano l’evento esistente di modifica dell’istanza dell’oggetto di apprendimento, pertanto non viene introdotto alcun nuovo tipo di evento.

>[!NOTE]
>
>Le modifiche dell’Istruttore attivano un webhook solo se un webhook attivo si iscrive all’evento di modifica dell’istanza dell’oggetto di apprendimento. Scopri come [creare e gestire i webhook come Amministratore dell’integrazione](/help/migrated/integration-admin/feature-summary/webhooks.md#create-manage-webhooks).

## Modifiche supportate dall’istruttore

L’evento webhook viene attivato quando un Istruttore modifica uno dei seguenti dettagli della sessione:

* Tempistiche della sessione

* Crediti

* Fuso orario

* Luogo

* Limite di iscrizione

* Limite della lista d’attesa

* Consenti invii

## Struttura del payload del webhook

Ogni richiesta webhook contiene la seguente struttura di primo livello:

```json
{
  "accountId": 1234,
  "events": [
    {
      "eventId": "121da98-ab8d-43e9-b671-e79131cd69dc",
      "eventName": "LEARNING_OBJECT_INSTANCE_MODIFICATION",
      "timestamp": "2024-11-08T03:49:52.000Z",
      "eventInfo": "1235603297000-040649-741781-0",
      "data": {
        "loInstanceId": "course:12324298_14453691",
        "loId": "course:12324298",
        "loType": "course"
      }
    }
  ]
}
```

La stessa struttura viene utilizzata indipendentemente da chi modifica l’istanza LO. Il payload non indica se la modifica è stata apportata da un istruttore, un amministratore o un autore.

Quando un istruttore modifica i dettagli di una sessione, come il fuso orario, il limite di iscrizione o il limite della lista d’attesa, il webhook invia questo evento all’URL del listener. Utilizza l’evento per recuperare i dettagli della sessione più recente e avvisare gli Allievi o aggiornare i sistemi esterni.

## Recupera i dettagli della sessione aggiornata

L’evento webhook identifica l’istanza LO modificata. Per ottenere i dettagli della sessione aggiornata, chiama l’API pubblica (API Prime) di Learning Manager utilizzando `loId` dall’evento:

```http
GET /primeapi/v2/learningObjects/{loId}
```

Individuare l&#39;istanza corrispondente a `loInstanceId` nella risposta, quindi confrontarla con i dati memorizzati nel sistema.

## Creare integrazioni con gli eventi webhook

Puoi utilizzare questi eventi webhook per:

* Invia notifiche all’Allievo tramite un servizio e-mail o di messaggistica esterno quando vengono modificati dettagli della sessione come data, ora, fuso orario o luogo.

* Sincronizzare i dati della sessione con calendari esterni, sistemi di reporting o di analisi.

* Tenere traccia delle modifiche della capacità quando viene modificato il limite di iscrizioni o di liste di attesa di una sessione.

* Gestire gli audit trail registrando `eventId`, `timestamp` e `eventInfo` insieme agli identificatori di LO e di istanza.

Come minimo, il gestore del webhook deve:

* Convalida il payload e analizza `events[]`.

* Utilizza `eventName` per identificare l’evento di modifica dell’istanza dell’oggetto di apprendimento.

* Utilizza `loId` e `loInstanceId` per individuare il record corrispondente nel sistema e chiama l&#39;API pubblica per recuperare i dettagli della sessione corrente.

* Utilizzare `eventId` per impedire l&#39;elaborazione duplicata se lo stesso evento viene recapitato più di una volta.

Lo stesso evento viene inviato per le modifiche apportate da istruttori, amministratori e autori, pertanto l’integrazione potrebbe riceverlo più spesso di prima. Prima di inviare una notifica, confrontare i dettagli della sessione recuperata con i dati presenti nel sistema. Gli Allievi ricevono quindi una notifica solo quando cambiano i dettagli pertinenti.
