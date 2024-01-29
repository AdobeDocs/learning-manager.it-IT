---
jcr-language: en_us
title: Deprecazioni API in Adobe Learning Manager
description: Con l’evolversi delle API in Adobe Learning Manager, le API vengono periodicamente riorganizzate o aggiornate. Quando le API si evolvono, le API precedenti sono obsolete e alla fine rimosse. Questa pagina contiene le informazioni necessarie per eseguire la migrazione da versioni API obsolete a versioni API più recenti e stabili.
contentowner: saghosh
source-git-commit: 83fdd06aed823a50458d50c8ac240d56af873a6d
workflow-type: tm+mt
source-wordcount: '1005'
ht-degree: 0%

---


# Deprecazioni API in Adobe Learning Manager

## Rimozione delle API nella versione di marzo 2024 di Adobe Learning Manager

### Modifiche dei limiti di velocità

Con la prossima versione di Adobe di Learning Manager, stiamo ristrutturando i limiti di velocità delle API per i nuovi account. Per gli account esistenti, solo le API di amministrazione avranno una tariffa limitata. Dopo 90 giorni (circa 3 mesi), ristruttureremo i limiti di tariffa per tutte le API, ma gli account esistenti verranno inseriti in un elenco Consentiti in base all’utilizzo corrente. Gli account esistenti devono rivedere l’utilizzo delle API degli Allievi.

Per i nuovi account, se desiderano aumentare i limiti delle tariffe, devono contattare il team Customer Success di ALM.

#### Quali API saranno con tariffa limitata

Per i nuovi account, tutte le API per Amministratori, Allievi e Ricerca avranno limiti di tariffa e verranno applicate burst.

La velocità burst o il limite burst dell’API si riferisce al numero massimo di richieste che possono essere effettuate a un’API in un breve burst entro un periodo di tempo limitato.

Nella tabella seguente sono elencati i limiti di velocità e velocità di frammentazione per le API.

<table>
    <tr>
        <th>API</th>
        <th>Numero di richieste-RPM</th>
        <th>Numero di richieste - Burst</th>
    </tr>
    <tr>
        <td>Amministratore</td>
        <td>5</td>
        <td>5</td>
    </tr>
    <tr>
        <td>Allievo</td>
        <td>20</td>
        <td>5</td>
    </tr>
    <tr>
        <td>Cerca</td>
        <td>50</td>
        <td>5</td>
    </tr>
</table>

### Modifiche ai limiti di offset

A causa dell&#39;elevato numero di record recuperati dal valore di offset e del rallentamento delle prestazioni complessive, viene applicato un limite di **500** record. Nella prossima versione, sia per gli Amministratori che per gli Allievi, le **Utenti GET** L’API restituirà un massimo di **500** record.

Per recuperare altri record, utilizzare il pulsante **Processi GET** API.

La modifica dei limiti di offset si applica a tutti i nuovi clienti. Per i clienti esistenti, viene applicata la regola dei 90 giorni.

### Escludi tracciati

Al momento, le API di Learning Manager seguono una struttura di dati del grafico, che consente di recuperare i dati attraversando il modello API tramite include. Sebbene sia possibile attraversare un’API fino a sette livelli, recuperare i dati utilizzando una singola chiamata API è computazionalmente costoso.

Si consiglia a tutti i clienti nuovi ed esistenti di effettuare chiamate di piccole dimensioni più volte anziché una chiamata di grandi dimensioni. Questo approccio impedisce il caricamento di dati indesiderati nella chiamata.

Vogliamo applicare queste restrizioni ai nuovi account e mantenere una lista bianca degli account esistenti.

#### Percorsi obsoleti

I percorsi seguenti sono obsoleti:

* /learningObjects
   * Percorsi obsoleti:
      * enrollment.loInstance.loResources.resources
      * instances.loResources.resources
   * Nuovi tracciati:
      * enrollment.loInstance.loResources
      * instances.loResources

* /learningObjects/{id}
   * Percorso obsoleto:
      * enrollment.instances.subLoInstances.learningObject
   * Nuovo percorso:
      * enrollment.instances.subLoInstances

* /enrollments
   * Percorso obsoleto:
      * loInstance.learningObject.enrollment
   * Nuovo percorso:
      * loInstance.learningObject

* /learningObjects/{id}
   * Percorso obsoleto:
      * instance.subLoInstances.learningObject.enrollment.loResourceGrades
   * Nuovo percorso:
      * instance.subLoInstances

### Modifiche al conteggio riepilogativo dell’istanza

Attualmente, nell’endpoint di riepilogo LO, recuperate il numero di tutte le possibili varianti. Ad esempio, per un corso, puoi visualizzare il numero di iscrizioni e liste di attesa nella risposta per **GET /learningObjects/{loId}/instance/{loInstanceId}/summary**. È quindi possibile visualizzare i valori completionCount e enrollmentCount nella risposta. Se il corso è in aula virtuale o secondaria, puoi anche visualizzarne il limite di partecipanti e la lista d’attesa.

Il processo di recupero dei conteggi di completamento e di iscrizione è dispendioso dal punto di vista del calcolo, pertanto il calcolo viene eseguito su richiesta. Se i dati non sono presenti nella cache, i dati vengono ricaricati, il che richiede un uso intensivo di calcoli. Se sono presenti molti utenti che si iscrivono a un corso, i conteggi saranno elevati e influiranno in modo efficace sulle prestazioni della CPU.

Nella versione successiva di Adobe di Learning Manager, nell’endpoint di riepilogo dell’istanza LO, vengono memorizzati nella cache i valori completionCount, enrollmentCount, seatLimit e waitlistCount. Le informazioni memorizzate nella cache persistono finché non vengono apportate modifiche alle iscrizioni o annullate. Per i conteggi che superano le 1000 iscrizioni, supporremo i conteggi stimati e invalideremo i risultati per tutti i conti nuovi ed esistenti.

>[!NOTE]
>
>Per i conteggi, ad esempio completedCount, enrollmentCount, seatLimit e waitlistCount che superano i 1000, è consigliabile interpretarli come stime anziché come cifre precise, poiché verranno recuperati dalla cache.

### Ordina per nome

Nella versione successiva di Adobe di Learning Manager, nome e nome diventano obsoleti nel campo di ordinamento delle API seguenti:

* GET /userGroups/{userGroupId}/users
* GET /users

>[!NOTE]
>
>Per tutti gli account nuovi ed esistenti, l&#39;ordinamento in base al nome e al nome sarà deprecato.


## Rimozione delle API nella versione di novembre 2023 di Adobe Learning Manager

### Flag Sostituisci

Nella versione di novembre 2023 di Adobe Learning Manager, abbiamo interrotto il contrassegno di esclusione dalle API. Il flag di esclusione non fa parte della specifica API pubblica ed è destinato al test back-end. Il flag per le API degli Allievi ora non è più disponibile. Tuttavia, il flag è ancora valido per le API degli amministratori.

Il motivo per cui il flag per le API degli Allievi viene rimosso è perché il flag di esclusione recuperava una grande quantità di dati tramite le API degli Allievi.

In futuro, la seguente API Allievo non funzionerà più perché ha il flag di esclusione.

<code>https://captivateprime.adobe.com/primeapi/v2/users?page[offset]=0&amp;pagina[limite]=10&amp;sort=id&amp;override=TRUE</code>

### Modifiche alle API per nuovi consigli basati sulle competenze

L’Adobe di Learning Manager migliora i consigli per gli account abilitati per i clienti e i partner. Questo miglioramento dell’algoritmo di raccomandazione con la modifica dell’algoritmo di classificazione per corsi, percorsi di apprendimento e certificazioni offre una migliore esperienza utente nell’individuazione dei contenuti.

L’algoritmo non consentirà più raccomandazioni basate su peer. La modifica non interesserà gli utenti esistenti, ma l’opzione Allineato al settore continuerà a esistere. Per l’opzione Personalizzato, l’Adobe Learning Manager non consentirà più la selezione personalizzata basata su peer.

Il gruppo di colleghi diventa ora un account e gli allievi vedranno una stringa che mostra gli argomenti di tendenza nel gruppo. Tutti i consigli sono spiegabili. Ad esempio, se stai visualizzando qualcosa su un soggetto, la scheda sulla striscia mostrerà il motivo del corso.

### Modifiche Nel Report Annuncio Notifiche

Nelle versioni precedenti di Adobe Learning Manager, il report Annuncio notifica non disponeva di filtri. Adobe Learning Manager ha scaricato tutte le notifiche dell’account.

Nella versione di novembre 2023, è stato aggiunto un filtro per data, con cui è possibile scaricare le notifiche entro un periodo specificato.  Tuttavia, puoi scaricare il report solo per gli ultimi sei mesi.