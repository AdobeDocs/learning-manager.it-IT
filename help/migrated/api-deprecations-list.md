---
jcr-language: en_us
title: Rimozione delle API da Adobe Learning Manager
description: Con l’evoluzione delle API in Adobe Learning Manager, le API vengono periodicamente riorganizzate o aggiornate. Quando le API si evolvono, le API precedenti sono obsolete e alla fine rimosse. Questa pagina contiene le informazioni necessarie per eseguire la migrazione da versioni API obsolete a versioni API più recenti e stabili.
contentowner: saghosh
exl-id: 0fe9a3cb-9114-42d6-81ae-1a4f28c984fa
source-git-commit: 670d0477b246af2a0257e41eca799817e391b348
workflow-type: tm+mt
source-wordcount: '577'
ht-degree: 32%

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

A causa dell&#39;elevato numero di record recuperati dal valore di offset e del rallentamento delle prestazioni complessive, viene applicato un limite di **500** record. Nella prossima versione, sia per l’Amministratore che per l’Allievo, l’API **Utenti GET** restituirà un massimo di **500** record.

Per recuperare altri record, utilizza l&#39;API **Processi di GET**.

<!--### Exclude paths 

At present, Learning Manager APIs follow a graph data structure, which allows you to fetch data by traversing the API model through includes. Even though you could traverse an API up to seven levels, fetching the data using a single API call is computationally expensive. 

We recommend that all existing and new customers make small calls multiple times instead of one large call. This approach will prevent unwanted data from being loaded in the call. 

We want to enforce these restrictions on new accounts and maintain a whitelist of existing accounts.-->

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

<!--### Instance summary count changes 

Currently, in the LO summary endpoint, you fetch the number of all possible instances. For example, for a course, you can view the number of enrollments and waitlists in the response for **GET /learningObjects/{loId}/instances/{loInstanceId}/summary**. You can then view the completionCount and enrollmentCount in the response. If the course is a VC or classroom, you can also view its seat limit and waitlist limit. 

The process of retrieving the completion and enrollment counts is computationally expensive, therefore the calculation is done on a request basis. If the data is not present in the cache, the data is reloaded, which is computationally intensive. If there are many users enrolling in a course, the counts will be large, and effectively impacts CPU performance. 

In the next release of Adobe Learning Manager, in the LO Instance summary endpoint, the completionCount, enrollmentCount, seatLimit, and waitlistCount are cached. The cached information persists till there are changes in enrollments or unenrollments. For counts exceeding 1000 enrollments, we'll assume the estimated counts, and invalidate the results for all existing and new accounts.

>[!NOTE]
>
>For counts, such as, completionCount, enrollmentCount, seatLimit, and waitlistCount exceeding1000, it's advisable to interpret them as estimates rather than precise figures, as these will be retrieved from cache.-->

### Ordina per nome

Nella prossima versione di Adobe Learning Manager, name e -name sono deprecati nel campo di ordinamento delle seguenti API:

* GET /userGroups/{userGroupId}/users
* GET /users

>[!NOTE]
>
>Per tutti gli account nuovi ed esistenti, l&#39;ordinamento in base al nome e al nome sarà deprecato.


## Rimozione delle API nella versione di novembre 2023 di Adobe Learning Manager

### Flag di esclusione

Nella versione di novembre 2023 di Adobe Learning Manager, il flag di esclusione dalle API è stato interrotto. in quanto non fa parte delle specifiche dell’API pubblica ed è dunque destinato al test in back-end. Il flag non è più disponibile per le API degli Allievi, ma è ancora valido per le API degli Amministratori.

Il motivo per cui il flag per le API degli Allievi viene rimosso è perché il flag di esclusione recuperava una grande quantità di dati tramite le API degli Allievi.

D’ora in avanti, la seguente API per Allievi non funzionerà più perché contiene il flag di esclusione.

_/primeapi/v2/users?page[offset]=0&amp;page[limit]=10&amp;sort=id&amp;override=TRUE_

### Modifiche alle API per nuovi consigli basati sulle competenze

Adobe Learning Manager ha migliorato i suggerimenti per gli account di clienti e partner. L’ottimizzazione dell’algoritmo dei suggerimenti ha comportato la modifica dell’algoritmo di classificazione per corsi, percorsi di apprendimento e certificazioni, aiutando così gli utenti a trovare facilmente contenuti.

L’algoritmo non consentirà più suggerimenti in base alle attività dei colleghi. La modifica non interesserà gli utenti esistenti, ma l’opzione Allineato al settore resterà disponibile. Per l’opzione Personalizzato, Adobe Learning Manager non consentirà più la selezione personalizzata in base alle attività dei colleghi.

Il gruppo di colleghi diventerà un account e gli Allievi vedranno una stringa con gli argomenti di tendenza nel gruppo. Tutti i suggerimenti comprendono spiegazioni. Ad esempio, se si consulta un argomento, la scheda sulla striscia riporta la descrizione del corso.

### Modifiche Nel Report Annuncio Notifiche

Nelle versioni precedenti di Adobe Learning Manager, il report Annuncio notifica non disponeva di filtri. per cui venivano scaricate tutte le notifiche di un account.

Nella versione di novembre 2023, è stato aggiunto un filtro per data, con cui è possibile scaricare le notifiche entro un periodo specificato.  Tuttavia, puoi scaricare il report solo per gli ultimi sei mesi.

### Rimozione dei valori di offset elevati nell&#39;endpoint GET /users

Per migliorare le prestazioni del sistema e gestire in modo più efficace l&#39;utilizzo delle risorse, Adobe ha deprecato valori di offset elevati nell&#39;endpoint GET /users per gli ambiti **ADMIN** e **LEARNER**. Si consiglia di utilizzare l&#39;API **Processi** per recuperare i record con un valore di offset.

