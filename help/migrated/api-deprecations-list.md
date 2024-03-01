---
jcr-language: en_us
title: Deprecazioni API in Adobe Learning Manager
description: Con l’evolversi delle API in Adobe Learning Manager, le API vengono periodicamente riorganizzate o aggiornate. Quando le API si evolvono, le API precedenti sono obsolete e alla fine rimosse. Questa pagina contiene le informazioni necessarie per eseguire la migrazione da versioni API obsolete a versioni API più recenti e stabili.
contentowner: saghosh
source-git-commit: 01cdcd816fe101af55adf0902f4e3660a1a098ce
workflow-type: tm+mt
source-wordcount: '847'
ht-degree: 21%

---


# Modifiche e deprecazioni delle API in Adobe Learning Manager

## Rimozione delle API nella versione di marzo 2024 di Adobe Learning Manager

<!-- ### Changes in Rate Limits

With the next release of Adobe Learning Manager, we're restructuring API rate limits for new accounts. For existing accounts, only the Admin APIs will be rate-limited. After 90 days (about 3 months), we will restructure rate limits for all APIs, but existing accounts will be whitelisted according to current usage. Existing accounts need to revisit their learner API usage. 

For new accounts, if they want to increase the rate limits, they must contact the Customer Success team of ALM. 

#### Which APIs will be rate limited 

For new accounts, all Admin, Learner, and Search APIs will have rate limits and burst enforced.  

The API burst rate or burst limit refers to the maximum number of requests allowed to be made to an API in a short burst within a limited timeframe. 

The following table lists the rate and burst limits for the APIs.

<table>
    <tr>
        <th>API</th>
        <th>Number of requests-RPM</th>
        <th>Number of requests-Burst</th>
    </tr>
    <tr>
        <td>Admin</td>
        <td>5</td>
        <td>5</td>
    </tr>
    <tr>
        <td>Learner</td>
        <td>20</td>
        <td>5</td>
    </tr>
    <tr>
        <td>Search</td>
        <td>50</td>
        <td>5</td>
    </tr>
</table>
-->

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

### Flag di esclusione

Nella versione di novembre 2023 di Adobe Learning Manager, abbiamo interrotto il contrassegno di esclusione dalle API. in quanto non fa parte delle specifiche dell’API pubblica ed è dunque destinato al test in back-end. Il flag non è più disponibile per le API degli Allievi, ma è ancora valido per le API degli Amministratori.

Il motivo per cui il flag per le API degli Allievi viene rimosso è perché il flag di esclusione recuperava una grande quantità di dati tramite le API degli Allievi.

D’ora in avanti, la seguente API per Allievi non funzionerà più perché contiene il flag di esclusione.

_/primeapi/v2/users?pagina[offset]=0&amp;pagina[limite]=10&amp;sort=id&amp;override=TRUE_

### Modifiche alle API per nuovi consigli basati sulle competenze

Adobe Learning Manager ha migliorato i suggerimenti per gli account di clienti e partner. L’ottimizzazione dell’algoritmo dei suggerimenti ha comportato la modifica dell’algoritmo di classificazione per corsi, percorsi di apprendimento e certificazioni, aiutando così gli utenti a trovare facilmente contenuti.

L’algoritmo non consentirà più suggerimenti in base alle attività dei colleghi. La modifica non interesserà gli utenti esistenti, ma l’opzione Allineato al settore resterà disponibile. Per l’opzione Personalizzato, Adobe Learning Manager non consentirà più la selezione personalizzata in base alle attività dei colleghi.

Il gruppo di colleghi diventerà un account e gli Allievi vedranno una stringa con gli argomenti di tendenza nel gruppo. Tutti i suggerimenti comprendono spiegazioni. Ad esempio, se si consulta un argomento, la scheda sulla striscia riporta la descrizione del corso.

### Modifiche Nel Report Annuncio Notifiche

Nelle versioni precedenti di Adobe Learning Manager, il report Annuncio notifica non disponeva di filtri. per cui venivano scaricate tutte le notifiche di un account.

Nella versione di novembre 2023, è stato aggiunto un filtro per data, con cui è possibile scaricare le notifiche entro un periodo specificato.  Tuttavia, puoi scaricare il report solo per gli ultimi sei mesi.