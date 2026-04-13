---
description: Modifiche API in ALM
jcr-language: en_us
title: Modifiche alle API nella versione di aprile
source-git-commit: 3b35c16d74c83329cee24ee9ad007a53ccbd8cf3
workflow-type: tm+mt
source-wordcount: '4093'
ht-degree: 0%

---


# Modifiche alle API nella versione di aprile 2026

La versione di aprile 2026 di Adobe Learning Manager introduce miglioramenti mirati all’API pubblica per alternative ed equivalenti, accesso con finestra di tempo ai contenuti, tentativi di quiz basati sui contenuti, esperienze senza accesso e gestione delle risorse formative. Le modifiche sono state progettate per essere ampiamente compatibili con le versioni precedenti, consentendo al contempo integrazioni più precise.

## Apprendimento adattivo per i percorsi di apprendimento

Questa versione aggiunge il supporto API pubblico completo per i percorsi di apprendimento adattativi. I percorsi di apprendimento (LP) possono ora definire regole adattive che controllano quali sezioni e oggetti di apprendimento secondario (LO secondari) sono visibili a diversi gruppi di Allievi e l’API pubblica riflette questo comportamento.

Sono interessati i seguenti endpoint:

- GET /primeapi/v2/learningObjects?filter.loTypes=learningPath
- GET /primeapi/v2/learningObjects/{loId}

Un nuovo attributo booleano, attributes.isAdaptive, indica che un programma di apprendimento utilizza regole adattive. Quando questo flag è true, l&#39;attributo sections viene interpretato in modo adattivo.

Per le chiamate degli Allievi, vengono restituite solo le sezioni visibili per l’Allievo corrente. Ogni sezione include l’elenco degli ID degli oggetti di apprendimento (loId), un flag obbligatorio e un valore requiredLOCount calcolati in base alla configurazione adattiva per l’Allievo, nonché l’ID della sezione. Anche la relazione relations.subLOs è stata filtrata, quindi contiene solo gli oggetti di apprendimento secondario visibili all’Allievo.

Per le chiamate di amministratore, le sezioni possono esporre anche un array adaptiveConfig. Vengono descritte le regole adattive per ogni gruppo di utenti, inclusi userGroupId e userGroupName e se la sezione è obbligatoria per quel gruppo. Gli strumenti rivolti all’amministratore possono utilizzarli per visualizzare e gestire le regole adattive.

Ripristino del completamento dei programmi di apprendimento

La versione introduce un’API per __aggiornare (ripristinare) il completamento__ degli oggetti di apprendimento, inclusi i programmi di apprendimento adattativi. Ciò supporta scenari come corsi di formazione, aggiornamenti periodici della conformità o riavvii del programma.

È disponibile un nuovo endpoint:

```
POST /primeapi/v2/learningObjects/{loId}/instances/{loInstanceId}/refreshCompletion
```

Questa operazione richiede autorizzazioni di scrittura appropriate e reimposta lo stato di completamento per l’istanza dell’oggetto di apprendimento specificato nel contesto utente specificato. È destinato all’uso da parte di automazioni lato amministratore o strumenti allievi con ambito accurato.

Una versione in blocco di questa funzionalità è pianificata tramite un’API dei processi. La forma Richiesta è progettata per gli utenti di destinazione tramite e-mail, ID utente o ID gruppo utente, ad esempio:

```
{  
  "emails": ["[user1@example.com](mailto:user1@example.com)", "[user2@example.com](mailto:user2@example.com)"],  
  "userIds": ["12345", "67890"],  
  "userGroupIds": ["ug1", "ug2"]  
}  
```

Le integrazioni devono utilizzare questa API quando è necessario riavviare gli Allievi in ogni programma o corso. I client devono gestire correttamente le risposte agli errori: l’API potrebbe rifiutare le richieste di aggiornamento, laddove una reimpostazione non sia applicabile (ad esempio, in assenza di completamento o tipi di oggetti di apprendimento non supportati).

## Equivalenti e completamenti alternativi

Per supportare implementazioni in cui più oggetti di apprendimento possono soddisfare lo stesso requisito, la versione introduce completamenti equivalenti e alternativi come API pubbliche.

Gli endpoint dell’oggetto di apprendimento ora contengono queste informazioni:

```
- GET /primeapi/v2/learningObjects
- GET /primeapi/v2/learningObjects/{loId}
```

Un nuovo attributo booleano attributes.isAlternateComplete indica se il completamento dell’Allievo per un determinato oggetto di apprendimento è il risultato di un oggetto di apprendimento alternativo o equivalente anziché l’oggetto stesso. Quando questo è vero, la relazione relations.alternateCompletions elenca gli oggetti di apprendimento che hanno agito come alternative. Ciò consente la creazione di report a valle e i dashboard di distinguere tra completamenti diretti e alternativi e di mostrare quale alternativa soddisfaceva il requisito.

Inoltre, una visualizzazione correlata degli oggetti di apprendimento consente l’individuazione di potenziali alternative in grado di soddisfare un oggetto di apprendimento. Questo è esposto tramite:

```
GET /primeapi/v2/learningObjects/{loId}/relatedLOs?type=sourceAlternateLOs&limit={n}
```

La risposta restituisce oggetti di apprendimento che possono agire come alternative e include un campo meta.count che indica il numero totale di tali alternative, indipendentemente dal limite corrente. Le integrazioni possono utilizzare questa funzionalità per presentare gli equivalenti consigliati o per creare visualizzazioni amministrative di mapping alternativi.

## Report e casi d&#39;uso analitici

Gli utenti che generano report o analisi devono aggiornare la propria logica per aggiungere isAlternateComplete e alternateCompletions nei propri flussi di lavoro di reporting.

Le integrazioni di reporting che utilizzano dati di completamento (ad esempio, esportazione LT, feed data warehouse personalizzati o dashboard BI) devono estendere la logica per leggere e mantenere entrambi gli attributi.isAlternateComplete e relations.alternateCompletions dalle API LO:

- Quando isAlternateComplete == false:\
  Considera il record come un __completamento diretto__ dell&#39;LO, come avviene oggi.
- Quando isAlternateComplete == true:
   - Contrassegna il record come __completamento alternativo__ nel report (ad esempio, una colonna &quot;Metodo di completamento&quot; con valori DIRECT e ALTERNATE).
   - Utilizza relations.alternateCompletions.data[*].id per acquisire __gli LO/i di origine__ a cui è stato concesso questo completamento (ad esempio, &quot;Corso B completato tramite il corso alternativo A&quot;).

Casi d’uso tipici:

- _Report di conformità_: mostra che un corso di conformità è stato completato tramite un equivalente approvato ed elenca il corso di origine che ha soddisfatto il requisito.
- _Dashboard sull&#39;avanzamento del programma_: per visualizzare informazioni più precise sull&#39;avanzamento e i miglioramenti, distinguere gli Allievi che hanno completato _direttamente_ da quelli che l&#39;hanno soddisfatto tramite alternative.
- _Audit trail_: per qualsiasi LO contrassegnato come isAlternateComplete=true, gli auditor possono visualizzare esattamente i corsi di formazione alternativi utilizzati per concedere tale completamento.

Senza incorporare questi due campi, i report a valle considereranno i completamenti alternativi come completamenti regolari e _non saranno in grado di spiegare_ *perché* un Allievo mostra come completato un corso di formazione che non ha mai seguito direttamente.

## Comportamento API per Allievi e Amministratori di oggetti di apprendimento

La struttura della risorsa formativa multilingue è identica sia nelle API per gli oggetti di apprendimento per Allievi che per Amministratori. L’ambito Allievo restituisce solo le risorse formative visibili all’Allievo, ma per ogni risorsa formativa visibile espone tutte le impostazioni locali configurate tramite più entità risorsa (una per lingua) e più impostazioni locali localizzate Metadati. L’ambito Amministratore restituisce tutte le risorse formative che l’Amministratore può gestire, con lo stesso modello LO e gli stessi ID di risorse specifici per le impostazioni internazionali. I client con ambito Allievo devono scegliere la risorsa i cui attributi.locale corrispondono meglio alla lingua del contenuto dell’Allievo, mentre gli strumenti di amministrazione possono enumerare tutte le lingue per la creazione di report e la gestione.

## Elenco di controllo con funzionalità per commenti

Per supportare i flussi di lavoro in cui i revisori possono condividere feedback strutturati sulle attività basate su elenchi di controllo, questa versione genera *commenti all’elenco di controllo* e controlli di visibilità dei revisori tramite l’API delle risorse dell’oggetto di apprendimento.

I metadati relativi all’elenco di controllo vengono esposti nelle entità learningObjectResource (JApiLOResource, &quot;type&quot;: &quot;learningObjectResource&quot;) che rappresentano le risorse dell’elenco di controllo all’interno di un corso o di un altro oggetto di apprendimento.

Le informazioni sono disponibili tramite:

```
GET /primeapi/v2/learningObjects/{loId}?include=instances.loResources
```

Quando l’istanza dell’oggetto di apprendimento contiene risorse di tipo elenco di controllo, le voci learningObjectResource corrispondenti nell’array incluso espongono gli attributi di commento e visibilità del revisore in attributi e l’identità del revisore in relazioni.

### Nuovi attributi per i commenti dell’elenco di controllo

Per le risorse dell’elenco di controllo, in learningObjectResource possono essere presenti i seguenti attributi:

- attributes.checklistComment\
  Commento di testo libero lasciato dal revisore per l’Allievo, ad esempio:\
  &quot;checklistComment&quot;: &quot;Prestazioni eccellenti! Tutti i protocolli di sicurezza sono stati seguiti correttamente.&quot;\
  Questo attributo viene compilato _solo se_:
   - showChecklistComment è true e
   - nella configurazione dell&#39;elenco di controllo enable_reviewer_remarks è abilitato.
- attributes.showChecklistComment\
  Flag booleano che indica se le note del revisore devono essere visualizzate all’Allievo:\
  &quot;showChecklistComment&quot;: true\
  Questo attributo è presente _solo quando_ enable_reviewer_remarks è abilitato nella configurazione dell&#39;elenco di controllo.\
  I client devono utilizzare questo flag per decidere se eseguire il rendering dell’elenco di controllo Comment nelle esperienze degli Allievi.
- attributes.showReviewerNameToLearner\
  Flag booleano che controlla se l’Allievo deve visualizzare l’identità del revisore:\
  &quot;showReviewerNameToLearner&quot;: true\
  Se è true, i client possono utilizzare la relazione checklistReviewedBy (vedere di seguito) per risolvere e visualizzare il nome del revisore (ad esempio, tramite un&#39;API di ricerca utente).

Un altro contesto specifico dell’elenco di controllo, ad esempio checklistEvaluationStatus, isChecklistMandatory, resourceSubType: &quot;CHECKLIST&quot; e submissionDate, è disponibile anche sulla stessa risorsa learningObjectResource per supportare interfacce utente e report più completi.

### Relazione identità revisore

Quando i nomi dei revisori devono essere visibili, learningObjectResource include una relazione che punta all’utente revisore:

```
"relationships": {
  "checklistReviewedBy": {
    "data": {
      "id": "user_id",
      "type": "user"
    }
  }
}
```

Questa relazione viene popolata _solo se_:

- showReviewerNameToLearner è true e
- checklistReviewedBy non è null (ovvero l&#39;elenco di controllo è stato rivisto).

Le applicazioni client devono:

1. Selezionare attributes.showReviewerNameToLearner.
2. Se è presente true e relations.checklistReviewedBy.data, chiama l’API utente appropriata per risolvere &quot;id&quot;: &quot;user_id&quot; in un nome visualizzato.
3. Esegui il rendering del nome del revisore accanto al commento dell’elenco di controllo o allo stato, a seconda dei casi.

### Accesso alle risorse dell&#39;elenco di controllo e ai commenti

Per recuperare le risorse dell’elenco di controllo e i relativi commenti per un determinato oggetto di apprendimento, i client devono:

- Chiama

```
GET /primeapi/v2/learningObjects/{loId}?include=instances.loResources
```

- Nella comparsa di risposta:
   - Utilizza relations.instance dell’oggetto di apprendimento principale per individuare le voci learningObjectInstance pertinenti in incluse.
   - Da ogni learningObjectInstance, seguire relations.loResources per trovare le voci learningObjectResource.
   - Filtra le voci learningObjectResource in cui:
      - attributes.resourceSubType == &quot;CHECKLIST&quot; (per le risorse dell&#39;elenco di controllo) e
      - facoltativamente attributes.showChecklistComment == true per trovare gli elenchi di controllo con commenti visibili agli allievi.

- Per ogni elenco di controllo learningObjectResource, utilizzare:
   - attributes.checklistComment (se presente e showChecklistComment è true)
   - attributes.checklistEvaluationStatus (ad esempio, &quot;PASSED&quot;)
   - attributes.showReviewerNameToLearner
   - relations.checklistReviewedBy (se presente) per identificare il revisore.

Questo modello consente ai client headless o personalizzati di eseguire il rendering di un’esperienza completa dell’elenco di controllo, inclusi lo stato, i flag obbligatori/opzionali e il feedback dei revisori, direttamente dalle API Prime.

### Report e considerazioni UX

- _Creazione di rapporti e analisi_
Le integrazioni che tengono traccia delle prestazioni degli Allievi negli elenchi di controllo possono includere:
   - checklistEvaluationStatus per gli indicatori di stato pass/fail o di altro tipo.
   - isChecklistObbligatorio per distinguere le attività dell&#39;elenco di controllo obbligatorie da quelle facoltative.
   - Presenza o assenza di checklistComment e showChecklistComment per gli audit sulla copertura del feedback.
- _Esperienze degli Allievi_
Le implementazioni dell&#39;interfaccia utente devono:
   - Rispettare showChecklistComment prima di visualizzare le note.
   - Utilizzare showReviewerNameToLearner e checklistReviewedBy per decidere se visualizzare il nome del revisore o mantenere anonima la revisione.
   - Ripiegamento corretto quando i commenti sono disattivati o non presenti, continuando a mostrare lo stato di valutazione e le informazioni di invio.

## Supporto multilingue per risorsa formativa

Per supportare implementazioni in cui le risorse formative devono essere fornite in più lingue sia agli Allievi che agli Amministratori, questa versione estende la gestione delle risorse formative in modo da restituire *una risorsa per lingua* anziché una singola risorsa en-US hardcoded.

Le risorse formative multilingue continuano a utilizzare la gerarchia esistente:

_oggetto di apprendimento_ (lo) → _learningObjectResource_ (loResource) → _risorsa_

Non sono richieste modifiche al contratto API. Qualsiasi risorsa formativa localizzata si adatta naturalmente a questa struttura, con entità risorsa separate per lingua e metadati localizzati condivisi ai livelli learningObject/learningObjectResource.

I dati della risorsa formativa sono esposti tramite:

```
GET /primeapi/v2/learningObjects/jobAid:{jobAidId}?include=instances.loResources.resources
```

Quando una risorsa formativa dispone di più varianti di lingua, l’array incluso contiene più voci &quot;type&quot;: &quot;resource&quot;, una per ogni lingua (ad esempio, en-US, fr-FR, es-ES), tutte collegate da un singolo learningObjectResource.

### Struttura delle risorse formative multilingue

Le risorse formative multilingue utilizzano:

- _learningObject (tipo: learningObject)_
   - Contiene localizedMetadata con più voci (ad esempio, en-US, fr-FR) in modo che i clienti possano presentare il titolo/la descrizione della risorsa formativa nella lingua appropriata.
- _learningObjectInstance (tipo: learningObjectInstance)_
   - Fa riferimento a una o più voci learningObjectResource tramite relations.loResources.
- _learningObjectResource (tipo: learningObjectResource)_
   - Contiene la configurazione comune (tipo di contenuto, versione, ecc.) e multi-locale localizedMetadata.
   - Collegamento a una o più entità risorsa tramite relations.resources.
- _risorsa (tipo: risorsa)_
   - *Uno per ogni lingua*, ciascuno con il proprio ID, lingua, nome e URL (location / downloadUrl).

Per una risorsa formativa multilingue, un modello tipico è:

- learningObjectResource con localizedMetadata per en-US e fr-FR
- relations.resources.data che punta a:
   - risorsa con impostazioni internazionali: &quot;en-US&quot;
   - risorsa con impostazioni internazionali: &quot;fr-FR&quot;

I client possono selezionare la risorsa appropriata facendo corrispondere le impostazioni internazionali dell’Allievo al campo resource.attributes.locale.

### Nuovo formato ID risorsa per risorse formative

Per distinguere correttamente più varianti localizzate di una risorsa risorsa risorsa formativa, il formato _dell&#39;ID risorsa è cambiato_.

_Vecchio formato ID risorsa (legacy)_

In precedenza, le risorse risorsa formativa utilizzavano un formato ID opaco come:

risorsa formativa:131032_-1_-1_2_resource

Questo formato non codificava le impostazioni locali e le API esponevano di fatto solo una singola risorsa (in genere en-US).

_Nuovo formato ID risorsa (compatibile con più lingue)_

Il nuovo formato è:

```
jobAid:<jobAidId>_<version>_<localeCode>
```

Esempi:

- risorsa formativa:131032_2_en-US
- risorsa formativa:131032_2_fr_FR
- risorsa formativa:131032_2_es_ES

Ripartizione visiva:

```
jobAid:131032_2_fr_FR

        │      │ │ │

        │      │ │ └──► Locale Code (fr_FR, en_US, es_ES, etc.)

        │      │ └────► Version (2)

        │      └──────► JobAid ID (131032)

        └─────────────► Resource Type Prefix ("jobAid:")
```

Questa struttura consente ai client:

- Identificare rapidamente la risorsa formativa e la versione a cui appartiene una risorsa.
- Deduci direttamente la lingua dall&#39;ID della risorsa quando necessario.

### Compatibilità con le versioni precedenti: 

```/resources/{resourceId}```

L&#39;endpoint della risorsa legacy rimane disponibile:

```GET /primeapi/v2/resources/{resourceId}

```

Ora è _compatibile con le versioni precedenti_ con entrambi i formati ID precedente e nuovo:

- _Formato ID precedente_ (ad esempio, risorsa formativa:131032_-1_-1_2_resource)
   - Continua a lavorare.
   - Restituisce la _prima risorsa creata_ associata all&#39;identificatore legacy, in genere la risorsa en-US originale.
- _Nuovo formato ID_ (ad esempio, risorsa formativa:131032_2_fr_FR)
   - Restituisce la _risorsa specifica per le impostazioni internazionali_ corrispondente a tale ID.
   - Ciò consente di recuperare e modificare con precisione le varianti localizzate delle risorse formative.

Le integrazioni che attualmente memorizzano o fanno riferimento ai vecchi ID di risorsa possono continuare a funzionare senza modifiche, mentre le implementazioni più recenti sono incoraggiate ad adottare il nuovo formato di ID per le operazioni specifiche delle impostazioni internazionali.

### Considerazioni su integrazione ed esperienza utente

- _Interfaccia utente Allievo/Amministratore_
   - Utilizza learningObject.localizedMetadata e learningObjectResource.localizedMetadata per presentare titoli e descrizioni nella lingua appropriata.
   - Utilizza resource.attributes.locale per selezionare l’URL corretto (location / downloadUrl) per la lingua dell’Allievo.
   - Implementa il comportamento di fallback (ad esempio, fallback a en-US) se la lingua esatta di un Allievo non è disponibile.
- _API e archiviazione_
   - Per le nuove integrazioni, memorizza gli _ID di risorsa in nuovo formato_ (```jobAid:<jobAidId>_<version>_<localeCode>```) per abilitare il recupero univoco specifico per le impostazioni internazionali.
   - Gli ID legacy possono ancora essere utilizzati con /resources/{resourceId}, ma non distinguono tra le impostazioni internazionali.

## Vincoli relativi alle fasce orarie per l&#39;avvio dei moduli

Alcune esperienze di apprendimento devono essere disponibili solo entro una finestra temporale definita. La versione mostra le informazioni sugli intervalli di tempo nelle risorse degli oggetti di apprendimento e introduce un endpoint di convalida che controlla se un Allievo può avviare una risorsa al momento corrente.

I metadati delle fasce orarie sono disponibili attraverso il punto finale:

```GET /primeapi/v2/learningObjects/{loId}?include=instances.loResources```

A livello di risorsa dell’oggetto di apprendimento, un oggetto timeSlot potrebbe ora essere presente negli attributi, con i valori startTime e endTime in UTC. Specifica la finestra durante la quale è possibile avviare la risorsa.

Prima di avviare un modulo, le integrazioni possono chiamare un nuovo endpoint di convalida:

```GET /primeapi/v2/learningObjects/{loId}/instances/{loInstanceId}/loResources/{loResourceId}/canStart```

Questo endpoint, destinato agli scenari di lettura da parte dell’Allievo, indica se l’Allievo è attualmente autorizzato ad avviare la risorsa, tenendo conto della fascia oraria configurata, del tipo di recapito e di altre regole di back-end.

I lettori personalizzati e le applicazioni client devono utilizzare canStart per applicare l&#39;accesso basato sul tempo e utilizzare i metadati timeSlot per visualizzare messaggi chiari su quando il contenuto diventa disponibile o scade. Le risposte negative di canStart devono essere gestite in modo esplicito per informare gli Allievi del motivo per cui il contenuto non può essere ancora avviato o non può più essere avviato.

## Query basate sui contenuti e tentativi multipli

Alcuni pacchetti di contenuti implementano il proprio tentativo di tracciamento piuttosto che affidarsi esclusivamente a Adobe Learning Manager. La versione introduce un flag che indica quando i tentativi sono guidati dal contenuto stesso.

Attraverso:

```GET /primeapi/v2/learningObjects/{loId}?include=instances.loResources```

le risorse dell’oggetto di apprendimento possono ora esporre un attributo booleano hasContentDrivenAttemptTracking. In questo caso, il quiz o il modulo gestisce i tentativi internamente (ad esempio, tramite logica SCORM o xAPI) e i contatori dei tentativi standard della piattaforma potrebbero non riflettere completamente l’esperienza dell’Allievo.

Questo flag deve essere controllato dalle integrazioni che visualizzano il conteggio dei tentativi o controllano il comportamento dei tentativi. Quando questa opzione è attivata, non devono dedurre i limiti dei tentativi solo dai metadati della piattaforma e devono essere preparati a basarsi su report lato contenuto (ad esempio, tramite istruzioni xAPI) o su regole aziendali specifiche.

## Modifica comportamentale nel formato ID risorsa Risorsa risorsa formativa

Questa versione introduce un&#39;importante __modifica comportamentale__ nel formato degli ID delle risorse risorsa formativa. Sebbene non sia coinvolto alcun nuovo endpoint, questo ha un impatto diretto sui sistemi che memorizzano o analizzano questi ID.

In precedenza, gli ID delle risorse Risorsa formativa utilizzavano un formato come:

```jobAid:<jobAidId>_-1_-1_2_resource```

Nella versione di aprile 2026, questo è sostituito da un formato semplificato e più esplicito:

```jobAid:<jobAidId>_<version>_<localeCode>```

Ad esempio:

risorsa formativa:131032_2_fr_FR

I componenti sono:

- ```<jobAidId>```: ID risorsa formativa numerico (ad esempio, 131032),
- ```<version>```: numero di versione della risorsa formativa (ad esempio, 2),
- ```<localeCode>```: il codice delle impostazioni internazionali (ad esempio, en_US, fr_FR, es_ES).

Qualsiasi integrazione che indicizzi risorse o persista negli ID risorse risorsa formativa deve aggiornare la logica di analisi e archiviazione per riconoscere il nuovo formato. Poiché gli identificatori stessi cambiano, è consigliabile ricostruire tutti gli indici locali digitati dagli ID delle risorse della risorsa formativa dopo l’aggiornamento alla versione di aprile 2026.

## Impostazione delle immagini del banner del corso tramite migrazione

Ora puoi impostare o aggiornare le immagini del banner del corso in Adobe Learning Manager come parte del flusso di lavoro di migrazione standard. Questo consente di avviare o pulire cataloghi di grandi dimensioni mantenendo le pagine dei corsi coerenti visivamente, senza modifiche manuali

### Dove vengono definite le immagini dei banner

Le immagini del banner sono configurate nel file di migrazione _course.csv_, che già utilizzi per fornire i metadati del corso, ad esempio:

- id
- courseName
- courseCreationDate
- state
- autore
- thumbnailUrl

Con questo miglioramento, la specifica course.csv include una _colonna facoltativa_ aggiuntiva per l’immagine del banner del corso. Il nome esatto dell’intestazione è definito nella specifica CSV che scarichi dall’account Learning Manager (ad esempio, può essere visualizzato come bannerUrl o bannerImageUrl).

La colonna del banner:

- Indica il file di immagine da utilizzare come _banner del corso_.
- Funziona come thumbnailUrl, utilizzando le immagini disponibili nel repository dei contenuti configurato (Box/FTP).

### Preparazione delle immagini del banner per la migrazione

1. Carica immagini banner: inserisci i file delle immagini del banner nella stessa posizione Box o FTP utilizzata per altre risorse di migrazione, seguendo la struttura di directory esistente.
2. Controllare il formato del file:
Utilizza uno dei formati di immagine supportati (ad esempio, png, jpg, jpeg, gif), come descritto nei requisiti di sistema:
   1. [*Requisiti di sistema*](/help/migrated/system-requirements.md)
3. Aggiornamento course.csv: nella nuova colonna del banner, fai riferimento al percorso relativo o all’identificatore dell’immagine del banner. Esempio concettuale:

```
id,courseName,courseCreationDate,state,author,thumbnailUrl,bannerUrl  
12345,DEMO1,2018-05-05T08:56:21.000Z,Published,Sudheer,pic1.png,banners/banner1.png  
45678,DEMO2,2018-05-05T08:56:21.000Z,Published,Sudheer,pic2.png,banners/banner2.png  
```

### Applicare banner durante un&#39;esecuzione della migrazione

Una volta aggiornato il file course.csv, il flusso è uguale a qualsiasi altra migrazione:

1. _Carica CSV_
Carica il file course.csv aggiornato (e qualsiasi altro file pertinente) nella cartella Box/FTP configurata per la migrazione. I nomi dei file devono corrispondere esattamente ai nomi specificati in csv_specific.zip (con distinzione tra maiuscole e minuscole).
2. _Avvia esecuzione sprint_
In Adobe Learning Manager, in qualità di Amministratore dell’integrazione, avvia una migrazione _esecuzione dello sprint_ che include course.csv.\
   Il motore di migrazione legge la colonna del banner e applica l’immagine del banner a ciascun corso.
3. _Esaminare i risultati e i registri errori_
Dopo lo sprint:
   1. Verifica i banner nelle app _Autore_ e _Allievo_.
   2. Se alcune righe hanno esito negativo (ad esempio, a causa di un percorso di file non valido o di un formato non supportato), scarica il file CSV di errore dall’esecuzione della migrazione e correggi i dati.

### Nuovi corsi rispetto a quelli esistenti

Il campo banner funziona in entrambi gli scenari:

- _Nuovi corsi creati tramite la migrazione_
Quando un corso viene creato per la prima volta da course.csv e la colonna del banner viene compilata, tale banner viene impostato immediatamente.
- _Corsi esistenti (adeguamento/correzioni)_
Se esegui nuovamente la migrazione con lo stesso ID corso e un nuovo valore banner:
   - Learning Manager individua il corso esistente.
   - L&#39;immagine del banner è _aggiornata_ alla nuova immagine specificata nel file CSV.

I nomi e i percorsi effettivi delle colonne devono corrispondere alla _specifica CSV scaricata_ e al layout del repository dei contenuti.

## Rimuovere la colonna dell’ordine in LearningProgramCourse

Adobe Learning Manager ora supporta un modello semplificato per l&#39;ordinamento di _corsi all&#39;interno dei percorsi di apprendimento (programmi di apprendimento)_ durante la migrazione. Come parte di questa modifica, la colonna _ordine è stata rimossa_ dal file di migrazione learning_program_course.csv.

In precedenza, il file learning_program_course.csv includeva una colonna (spesso chiamata ordine o simile) utilizzata per:

- Imposta in modo esplicito la _posizione_ di ogni corso all’interno di un programma di apprendimento, in base al valore numerico in quella colonna.
- Richiedere agli amministratori o agli script di mantenere questa sequenza numerica manualmente, soprattutto durante l’inserimento o il riordinamento dei corsi.

Ora Adobe Learning Manager non utilizza più la colonna dell’ordine in learning_program_course.csv per determinare l’ordine dei corsi. Il file CSV di migrazione si concentra invece su _quali corsi appartengono a quale programma di apprendimento_, piuttosto che sul modo in cui sono ordinati numericamente.

## Impatto sui CSV di migrazione

### learning_program_course.csv

La colonna dell’ordine precedente deve essere considerata come rimossa o ignorata:

- Durante la migrazione, non basarti sull’ordine per controllare la sequenza dei corsi in un programma di apprendimento.
- Se disponi ancora di una colonna dell’ordine da modelli precedenti:
   - Learning Manager lo ignorerà per gli ordini.
   - Puoi rimuoverlo in modo sicuro dal tuo file CSV nel tempo per semplificare i file di migrazione.
- La mappatura richiesta principale rimane:
   - ID programma di apprendimento ↔ ID corso (e qualsiasi altra colonna ancora documentata come ID, learningProgramId, courseId e date).

Fai sempre riferimento alle [_specifiche CSV_](https://experienceleague.adobe.com/en/docs/learning-manager/using/integration/migration-manual) più recenti dal tuo account Learning Manager (tramite csv_specific.zip) per confermare il set di intestazioni e i requisiti correnti.

## TimeZoneCode sulle istanze del corso

A partire da questa versione, il modello Istanza del corso (learningObjectInstance) espone un nuovo attributo:

timeZoneCode: campo stringa che collega esplicitamente un’istanza del corso a uno dei fusi orari configurati dell’account.

Ciò consente ai client di:

- Risolvere il fuso orario di un’istanza di corso in modo coerente e basato su API.
- Interpreta e visualizza correttamente tutte le date/ore a livello di istanza per quell’istanza, indipendentemente dal fuso orario dell’utente.

### Dove viene visualizzato timeZoneCode

Il campo viene aggiunto negli attributi del modello learningObjectInstance.
solo per le istanze del corso.

Esempio:

```
{
  "id": "course:1262748_1359228",
  "type": "learningObjectInstance",
  "attributes": {
    "dateCreated": "2019-08-06T13:50:39.000Z",
    "isAET": false,
    "isDefault": true,
    "timeZoneCode": "356",
    "isFlexible": false,
    "state": "Active",
    "localizedMetadata": [
      {
        "locale": "en-US",
        "name": "Default instance"
      }
    ]
  }
}
```

### Come risolvere TimeZoneCode

Il codice numerico del fuso orario è una chiave di ricerca nel catalogo del fuso orario dell’account, che viene visualizzata tramite l’API Account:

```http
GET /primeapi/v2/account
Authorization: Bearer <access_token>
```

All’interno della risposta, i fusi orari sono elencati in:

```
"data": {
  "attributes": {
    "timeZones": [
      {
        "name": "Etc/GMT+12",
        "timeZoneCode": "356",
        "utcOffset": -720,
        "utcOffsetCode": "UTC-12:00(Etc/GMT+12)",
        "zoneId": "Etc/GMT+12"
      },
      "..."
    ]
  }
}
```

### Flusso client consigliato:

1. Chiama GET /account una volta, memorizza nella cache gli attributi.timeZones per il tenant.
2. Per ogni istanza di corso:
   - Leggere attributes.timeZoneCode.
   - Trovare la voce corrispondente in fusi orari in cui timeZoneCode corrisponde.
   - Utilizzare il valore zoneId, utcOffset e utcOffsetCode di tale voce per la logica di visualizzazione e pianificazione.

## API pubbliche asincrone per l’iscrizione a un gruppo di utenti

### Introduzione

Adobe Learning Manager espone due _API asincrone per l’amministratore_ per gestire l’iscrizione al gruppo di utenti:

- POST /async/userGroups/{userGroupId}/users: aggiunta asincrona di utenti a un gruppo di utenti
- DELETE /async/userGroups/{userGroupId}/users: rimozione asincrona degli utenti da un gruppo di utenti

Anziché aggiornare l&#39;appartenenza nella stessa richiesta, queste API accettano il batch e restituiscono un _ID evento_. Il risultato effettivo viene fornito in seguito tramite i webhook.

Usalo quando:

- Si gestiscono gruppi di grandi dimensioni o frequenti aggiornamenti in batch.
- La latenza è meno importante dell&#39;affidabilità e del throughput.
- Stai creando integrazioni (HR, CRM, LXP) anziché clic sull&#39;interfaccia utente.

Per piccole azioni di amministrazione interattive, puoi continuare a utilizzare le API `/userGroups/{id}/users` sincrone.

### Autenticazione e URL di base

Queste API fanno parte dell&#39;interfaccia standard __v2 Admin API__.

- [URL di base (prod)](https://learningmanager.adobe.com/docs/primeapi/v2/)
- Autenticazione: token di accesso OAuth 2.0 con ambito `admin:write`
- Intestazioni obbligatorie:
   - Autorizzazione: Bearer &lt;token_di_accesso>
   - Content-Type: applicazione/json
   - Accetta: applicazione/json

Per il comportamento e gli ambiti generali dell’API di amministrazione, consulta:

- [Manuale per sviluppatori](/help/migrated/integration-admin/feature-summary/developer-manual.md)
- [Guida di riferimento alle API](https://learningmanager.adobe.com/docs/primeapi/v2/)

### Formato richiesta

Sia __add__ che __remove__ utilizzano esattamente la stessa forma del corpo.

#### Corpo

```
{
  "metadata": {
    "event_id": "my-optional-correlation-id",
    "sourceSystem": "HRIS",
    "batchId": "hr_2026_03_30_0001"
  },
  "data": [
    { "type": "user", "id": "11101219" },
    { "type": "user", "id": "11101220" }
  ]
}
```

#### dati (obbligatorio)

dati è l&#39;elenco degli identificatori di risorsa utente per questo batch.

- `type` deve essere &quot;utente&quot;.
- `id` è l&#39;_ID utente numerico_ in ALM (non e-mail, non UUID).

#### Vincoli

- `data` deve essere presente e non vuoto.
- È richiesto almeno un utente.
- La dimensione massima del payload è di 20 utenti per richiesta.
- Tutti gli ID devono essere numerici e fare riferimento a utenti validi.

Se una di queste condizioni non riesce, l’API restituisce un errore e non viene messo in coda nulla.

#### metadati (facoltativi)

`metadata` è qualsiasi dato di correlazione aggiuntivo di cui desideri creare eco nel webhook.

Utilizzo tipico:

- `event_id` - ID correlazione generato.
- `sourceSystem` - nome del sistema upstream.
- `batchId` - identificatori batch o processo.

Il servizio restituisce questo oggetto invariato nella risposta Webhook, in modo che sia possibile associare il callback al processo interno.

Vincoli:

- Facoltativo; può essere omesso completamente.
- La lunghezza combinata di tutte le chiavi e i valori non deve superare i 1000 caratteri.

### Formato di risposta

Entrambi gli endpoint rispondono in modo sincrono con un ID evento:

```
{ "event_id": "cd2972c8-cb15-47a0-a23f-e4a16cb720f5" }
```

Comportamento:

- Se `metadata.event_id` viene passato, verrà utilizzato tale valore.
- In caso contrario, il servizio genera un UUID.

Devi sempre:

- Archivia `event_id` come identificatore primario per il batch.
- Previsto di ricevere lo stesso valore nel callback Webhook.

Per ulteriori informazioni, visualizza i [webhook per aggiungere e rimuovere l&#39;appartenenza al gruppo di utenti](/help/migrated/integration-admin/feature-summary/webhooks.md#webhooks-for-adding-and-removing-user-group-membership).

## Domande frequenti

_In che modo la versione di aprile 2026 modifica l’API di learningObjects per i programmi di apprendimento adattivo?_

Questa versione aggiunge un flag isAdaptive ai programmi di apprendimento e rende le sezioni e i subLO consapevoli degli Allievi. Nei programmi adattivi, gli allievi visualizzano solo le sezioni e gli oggetti di apprendimento secondario visibili in base alle regole adattive, mentre gli amministratori possono visualizzare la configurazione adattiva sottostante per un gruppo di utenti.

_È necessario aggiornare la mia integrazione se presuppone che tutte le sezioni e gli oggetti di apprendimento secondari vengano sempre restituiti?_

Sì. Per i programmi di apprendimento adattivo, l’API ora restituisce solo le sezioni e i sub LO visibili all’Allievo corrente. Il codice client deve considerare la risposta come una vista autorevole, eventualmente filtrata, invece di assumere un elenco completo.

_Come posso reimpostare a livello di programmazione il completamento di un Allievo per un corso o un programma di apprendimento?_

Usa il nuovo endpoint:

```POST /primeapi/v2/learningObjects/{loId}/instances/{loInstanceId}/refreshCompletion```
Questa operazione reimposta il completamento per l&#39;istanza di destinazione quando le autorizzazioni e lo stato lo consentono.

_Come si verifica se un Allievo ha completato un corso tramite un oggetto di apprendimento alternativo o equivalente?_

Verifica l’attributo isAlternateComplete nell’oggetto di apprendimento. Se è vero, la relazione alternateCompletions elenca gli oggetti di apprendimento che hanno agito da alternative per il completamento dell’Allievo.

_Come posso trovare tutte le alternative che soddisfano un determinato oggetto di apprendimento?_

Utilizza il seguente endpoint:

```GET /primeapi/v2/learningObjects/{loId}/relatedLOs?type=sourceAlternateLOs&limit={n}```

e utilizzare la matrice di dati (per le alternative) e meta.count (per il numero totale di alternative).

_Come faccio a sapere se un Allievo è autorizzato ad avviare un modulo in questo momento?_

Innanzitutto, recuperare il timeSlot della risorsa da:

```GET /primeapi/v2/learningObjects/{loId}?include=instances.loResources```
e quindi utilizzare:

```GET /primeapi/v2/learningObjects/{loId}/instances/{loInstanceId}/loResources/{loResourceId}/canStart```

_Cosa significa hasContentDrivenAttemptTracking in una risorsa?_

Indica che il tracciamento dei tentativi è controllato dal contenuto stesso (ad esempio, tramite logica SCORM/xAPI) anziché solo dai contatori della piattaforma. Quando è vero, non affidarti esclusivamente ai conteggi o ai limiti dei tentativi di piattaforma per l&#39;esperienza utente e la creazione di report.

_Come posso ottenere menu appropriati per gli utenti non connessi (esperienze pubbliche)?_

Usa:

```GET /primeapi/v2/templates/menus?include=pages,subMenus.pages&isNonLoggedIn=true```

Restituisce strutture di menu e pagine filtrate per utenti anonimi, adatte a Experience Builder o ad altri siti headless.

_Cosa è cambiato nel filtro delle risorse formative con effectiveModifiedDate?_

Le richieste che combinano filter.effectiveModifiedDate con filter.loTypes=jobAid ora restituiscono correttamente solo risorse formative nella finestra di data specificata.

_Cosa è cambiato nel formato dell&#39;ID della risorsa formativa e come devo gestirlo?_

Il formato ID è cambiato da valori quali:

```jobAid:<jobAidId>_-1_-1_2_resource```

a:

```jobAid:<jobAidId>_<version>_<localeCode>```

ad esempio jobAid:131032_2_fr_FR. Qualsiasi sistema che memorizzi o analizzi gli ID delle risorse risorsa formativa deve essere aggiornato e dovresti pianificare la ricostruzione degli indici locali basati su questi ID dopo l&#39;aggiornamento alla versione di aprile 2026.
