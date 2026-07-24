---
description: L’API per l’elaborazione incrementale dei report sugli utenti consente agli amministratori di esportare solo gli utenti i cui dati sono stati modificati entro un determinato intervallo di date. In questo modo non è più necessario esportare tutti gli utenti e viene consentita una sincronizzazione più efficiente dei record utente nuovi o aggiornati.
jcr-language: en_us
title: Report utente incrementale (API dei processi)
source-git-commit: d61e81b0df6a6043b938c65adaabecb5699c2ce9
workflow-type: tm+mt
source-wordcount: '1602'
ht-degree: 1%

---


# Report utente incrementale (API dei processi)

## Panoramica

Il Report utente incrementale di Adobe Learning Manager è una nuova funzione API dei processi che consente agli amministratori e agli sviluppatori di integrazione di esportare solo gli utenti i cui dati sono stati modificati entro una determinata finestra di data e ora. Anziché trascinare l’elenco completo degli utenti ogni volta, potete richiedere una sezione di destinazione che copra solo gli utenti nuovi o modificati.

Il presente documento riguarda:

- Perché esistono report incrementali e quando utilizzarli
- Funzionamento della feature, incluso il modello di tracciamento delle modifiche
- La nuova API dei processi per i report utente incrementali (payload, parametri, paginazione)
- Come gestire gli account di grandi dimensioni (oltre 5.00.000 utenti)
- Campi tracciati e non tracciati
- Limitazioni e non obiettivi

## Perché utilizzare il reporting incrementale

Questa sezione spiega la motivazione della funzione e dovrebbe aiutarti a decidere se le esportazioni incrementali o complete si adattano meglio alla tua integrazione.

## Il problema con le esportazioni di utenti completi

L’esportazione completa corrente dell’utente (tipo di processo generateUsers) restituisce ogni utente in un account a ogni esecuzione. Per gli account enterprise di grandi dimensioni ciò crea due problemi significativi:

| Cliente | Volume utente |
|----------|-------------|
| Cliente A | 2,1 milioni di utenti |
| Cliente B | 7 milioni di utenti |
| Cliente C | Più di 1 milione di utenti |
| D cliente | 7,7 milioni di utenti (migrazione) |


* A questi livelli, la pipeline di esportazione viene eseguita con un utilizzo della CPU di circa il 90% durante il recupero, l’elaborazione e l’archiviazione dei dati.
* I dashboard a valle (Power BI, Salesforce, integrazioni personalizzate) acquisiscono nuovamente i record utente invariati a ogni esecuzione, sprecando larghezza di banda e tempo di elaborazione.
* Non è possibile chiedere &quot;quali utenti sono cambiati dall&#39;ultima esportazione?&quot; utilizzando l’API corrente.

## Quando utilizzare il reporting incrementale

Utilizza l’esportazione incrementale quando è necessario mantenere un sistema esterno sincronizzato con i dati utente di Adobe Learning Manager. Casi d’uso tipici:

* Mantenere aggiornato un dashboard aziendale (Power BI, Tableau, SFDC) con le modifiche apportate al profilo utente.
* Invio dei sistemi di gestione delle identità downstream con modifiche a ruoli, stati o metadati.
* Esecuzione di pipeline di sincronizzazione differenziale notturne o orarie invece di ricariche complete.
* Riduzione dei costi di caricamento e trasferimento dei dati delle API per gli account con milioni di utenti.

Utilizza l’esportazione completa (generateUsers) quando è necessaria una baseline autorevole, ad esempio alla prima configurazione o dopo un lungo intervallo tra le sincronizzazioni.

| Modalità di esportazione | Usa quando... |
|-------------|-----------|
| Esportazione completa (generateUsers) | Bootstrap iniziale; account con meno di 50.000 utenti; ripristino dopo una finestra di sincronizzazione mancante. |
| Esportazione incrementale (generateUserIncrementalReport) | Delta-sync regolare; account di grandi dimensioni; pipeline che richiedono solo record modificati |

## Report utente completo corrente

(generateUsers) In questa sezione viene documentato il report utente API dei processi esistente come riferimento. Se ne hai già familiarità, passa alla sezione successiva.

## Come funziona

Il report CSV dell’utente corrente viene inviato come processo tramite l’API dei processi. Una pipeline Snaplogic preleva l&#39;attività, esegue una query MySQL sul database CAPTIVATE (tabelle user, usergroup, usergroup_user) e genera un file CSV.

## Filtri disponibili

Il payload supporta tre filtri opzionali:

* `expandMetadata` - Passare true per esportare i metadati come colonna separata.
* `fetchActiveUsers` - Passare true per esportare solo gli utenti attivi.
* `peerAccountId` - Per generare il report utente per un account condiviso tra pari.

## Colonne CSV

Il file CSV esportato contiene le seguenti colonne:

```
internalUserID, userEmail, customerDefinedUniqueUserId, name, managerEmail,

userType, state, excludedFromGamification, pointsEarned, profile, roles,

dateCreated, lastLoginDate, dateDeleted, uiLocale, contentLocale,

timeZoneCode, userSource, group, AF_location, AF_login, AF_externalaf,

lastSocialActivityDate
```

## Payload richiesta

Tipo di processo: generateUsers. Solo ruolo di amministratore.

```
{

  "data": {

    "type": "job",

    "attributes": {

      "description": "<description of your choice>",

      "jobType": "generateUsers",

      "payload": {

        "expandMetadata": "<true to export metadata as separate column>",

        "fetchActiveUsers": "<true to export ACTIVE users only>",

        "peerAccountId": "<peerAccountId for peer account report>"

      }

    }

  }

}
```

## Limitazioni

* Nessun filtro basato su date: ogni esecuzione esporta tutti gli utenti.
* Non fattibile per gli account di grandi dimensioni: esaurimento delle risorse di pipeline superiore a ~1 milione di utenti.
* Nessuna funzionalità incrementale o differenziale.

## Report utente incrementale (generateUserIncrementalReport)

In questa sezione viene documentata la nuova funzione di report incrementale per gli utenti introdotta in M46. Questo è l&#39;oggetto principale di questo documento.

## Che cos’è un’esportazione incrementale?

Un’esportazione incrementale restituisce solo gli utenti i cui dati rilevati sono stati modificati entro una specifica finestra di data-ora di inizio e di fine. Il backend memorizza un indicatore orario dell’ultima modifica per i campi rilevati di ciascun utente. Quando si richiede un report per una determinata finestra, vengono inclusi solo gli utenti la cui modifica più recente rientra in tale finestra.

## Funzionamento del modello di rilevamento delle modifiche

Adobe Learning Manager mantiene un timestamp dell’ultima modifica che viene aggiornato ogni volta che cambia un campo tracciato per un utente.

Quando richiedi un report incrementale con start_date_time e end_date_time, il sistema restituisce gli utenti il cui timestamp dell&#39;ultima modifica rientra in [start_date_time, end_date_time]. Se un utente è stato modificato sia all&#39;interno che dopo la finestra (ad esempio, è stato modificato di nuovo dopo end_date_time), l&#39;utente non viene incluso nel report perché il timestamp dell&#39;ultima modifica è ora oltre la finestra.

>[!NOTE]
>
>Ciò significa che un’esportazione incrementale acquisisce gli utenti la cui modifica più recente si trova nella finestra specificata, non tutti gli utenti che sono stati toccati in qualsiasi momento durante la finestra.

## Campi rilevati per le modifiche

Un utente viene incluso in un report incrementale se uno qualsiasi dei seguenti campi viene modificato:

| Campo | Note |
|---|---|
| userEmail | Indirizzo e-mail dell’utente |
| nome | Nome dell&#39;utente |
| managerId | Nella tabella utente viene memorizzato l&#39;ID di gestione. Se l’ID del manager cambia, il campo viene segnalato come modificato. Se cambia solo l’indirizzo e-mail del manager (stesso managerId), questo campo NON viene considerato modificato. |
| testo | Classificazione utente interna o esterna |
| state | Attivo o eliminato |
| profilo | Assegnazione profilo utente |
| mansioni | Aggiunta o eliminazione di ruoli |
| uiLocale | Impostazioni locali interfaccia utente |
| contentLocale | Impostazioni locali del contenuto |
| timeZoneCode | Fuso orario utente |
| Campi attivi (AF_*) | Tutti i campi attivi configurati, ad esempio AF_location, AF_login |
| metadati | Tutti i campi di metadati configurati |

## Campi NON rilevati per le modifiche

I seguenti campi vengono visualizzati nell&#39;output CSV ma non attivano l&#39;inclusione in un&#39;esportazione incrementale quando vengono modificati:

* excludeFromGamification
* pointsEarned
* lastLoginDate
* dateDeleted
* dateCreated
* userSource
* lastSocialActivityDate

## Formato di output

Il report CSV incrementale ha le stesse colonne e lo stesso formato del report CSV utente completo. Tutte le colonne vengono visualizzate nello stesso ordine, compresi tutti i campi attivi e le colonne di metadati, indipendentemente dai campi modificati per gli utenti esportati.

>[!NOTE]
>
>Se viene aggiunto un nuovo campo attivo o ne viene rimosso uno esistente, tutti gli utenti interessati dalla modifica verranno visualizzati nella successiva esportazione incrementale. Le nuove colonne dei nuovi campi attivi vengono aggiunte alla fine del report in modo che le integrazioni esistenti basate sulla posizione delle colonne non vengano interrotte.

## Nuova API processo per report utente incrementale

Il report utente incrementale utilizza l’API dei processi per generare un file CSV contenente gli utenti i cui dati rilevati sono stati modificati entro la finestra di data e ora specificata. Per i set di risultati di grandi dimensioni, utilizzare lo stesso modello di impaginazione descritto più avanti in questo documento: inviare la stessa finestra di data in ogni richiesta e passare l&#39;ultimo ID utente ricevuto nella risposta precedente come fromUserId per recuperare il blocco successivo.

## Tipo di processo

Tipo di processo: generateUserIncrementalReport

## Payload richiesta

```
{

    "data": {

        "type": "job",

        "attributes": {

            "description": "description of your choice",

            "jobType": "generateUserIncrementalReport",

            "payload":{

                 "fullExport": <Pass true to export all users. If fullExport is true, fromDate and toDate are ignored>,

                 "expandMetadata": <Pass true to export metadata as separate columns>,

                 "fromDate": <Start of the change window in ISO format, for example 2020-01-01T18:30:00.000Z>,

                 "toDate": <End of the change window in ISO format, for example 2020-01-31T18:30:00.000Z>,

                 "fromUserId": <For paginated requests, pass the last userId received in the previous response>

            }

        }

   }

}
```

## Parametri payload

| Parametro | Tipo | Descrizione |
|---|---|---|
| fromDate | String (ISO 8601) | Richiesto per l’esportazione incrementale. Inizio della finestra di modifica. Utilizza il formato ISO 8601. |
| toDate | String (ISO 8601) | Richiesto per l’esportazione incrementale. Fine della finestra di modifica. Utilizza il formato ISO 8601. |
| fromUserId | Stringa | Facoltativo. Per le richieste impaginate, passa l’ultimo userId ricevuto nella risposta precedente come fromUserId. Ometti questo parametro per la prima richiesta. |
| expandMetadata | Booleano | Facoltativo. Se è true, i metadati vengono esportati come colonne separate. |

Per l&#39;esportazione incrementale, passare `fromDate` e `toDate` per definire la finestra di modifica. Se il set di risultati è più grande di un blocco, continuare la paginazione inviando gli stessi `fromDate` e `toDate` e passando gli ultimi `userId` dalla risposta precedente come `fromUserId`. Se fullExport è true, la finestra della data viene ignorata e l’API genera un’esportazione completa da parte dell’utente.

## Gestione di account di grandi dimensioni (oltre 500.000 utenti)

I report utente vengono generati utilizzando una pipeline della piattaforma dati e l&#39;output viene restituito in blocchi per supportare account di grandi dimensioni. Se un’esportazione incrementale copre più di 500.000 utenti, il report viene impaginato.

## Modello di paginazione

Per recuperare tutte le pagine per un’esportazione incrementale di grandi dimensioni, passa gli stessi valori di startDateTime e endDateTime in ogni richiesta e passa anche l’ID utente dell’ultimo utente ricevuto nel blocco precedente come fromUserId. L’API restituirà il successivo set di un massimo di 500.000 utenti con userId maggiore di quello passato da UserId.

## Flusso di lavoro di paginazione

Passaggio 1: invia la prima richiesta senza fromUserId.

```
// First request – no fromUserId

{

  "payload": {

    "startDateTime": "2026-05-01T00:00:00Z",

    "endDateTime": "2026-05-31T23:59:59Z"

  }

}
```

Passaggio 2: ricevere il primo blocco (fino a 500.000 utenti). Prendi nota dell’ultimo ID utente nella risposta.

Passaggio 3: sottometti la richiesta successiva, superando la stessa finestra di data e l’ultimo ID utente della risposta precedente come fromUserId.

```
// Subsequent request – pass last userId from previous response as fromUserId

{

  "payload": {

    "startDateTime": "2026-05-01T00:00:00Z",

    "endDateTime": "2026-05-31T23:59:59Z",

    "fromUserId": "<last userId from previous response>"

  }

}
```

Passaggio 4: ripeti l’operazione finché una risposta non restituisce meno di 500.000 record, indicando che hai raggiunto l’ultima pagina.

| Richiesta | Parametro fromUserId |
|---|---|
| Prima pagina | Ometti fromUserId |
| Seconda pagina | Passa l’ultimo ID utente dalla prima pagina come fromUserId |
| Terza pagina | Passa l’ultimo ID utente dalla seconda pagina come fromUserId |
| ... (continua) | ... |
| Ultima pagina | La risposta contiene meno di 500.000 record |

>[!NOTE]
>
>Assicurati che `startDateTime` e `endDateTime` rimangano identici in tutte le richieste impaginate per una singola esecuzione dell&#39;esportazione. La modifica della finestra della data a metà paginazione produrrà risultati incoerenti.

## Limitazioni

Il report incrementale dell&#39;utente è intenzionalmente incluso nell&#39;ambito. Le seguenti funzionalità non rientrano nell&#39;ambito:

* Non è un report di audit dell’utente: non elenca i campi specifici modificati.
* Nessun confronto tra valori vecchi e nuovi: nel report vengono visualizzati solo i valori dei campi correnti.
* Nessun timestamp per modifica: non viene rilevato il tempo delle singole modifiche dei campi.
* Nessuna indicazione del numero di modifiche: un utente modificato una volta e un utente modificato dieci volte vengono visualizzati identici nell’esportazione.
* Il formato del report esistente è invariato: la struttura delle colonne CSV è uguale a quella del report utente completo.

## Integrazione dei connettori

Il report utente incrementale è progettato per essere utilizzato nei connettori Adobe Learning Manager (Power BI, Salesforce e altri) come sostituzione a discesa del report utente completo nelle normali pipeline di sincronizzazione. Ciò consente ai connettori che utilizzano attualmente generateUsers di eseguire la migrazione al modello incrementale senza modifiche allo schema dei dati downstream.

* Il file CSV di output è compatibile con le colonne per il report completo dell’utente.
* I connettori possono utilizzare il report incrementale per la sincronizzazione differenziale e tornare al report completo per il bootstrap o il ripristino.
* Supporto per l’integrazione dei connettori (PowerBI, SFDC)
