---
jcr-language: en_us
title: Guida all’utilizzo dei webhook
description: Scopri l’utilizzo dei webhook, le best practice e le limitazioni
contentowner: chandrum
source-git-commit: d7f7652c38c3eb623be083fd2fdde36eec25c1e4
workflow-type: tm+mt
source-wordcount: '3377'
ht-degree: 1%

---

# Guida all’utilizzo dei webhook

I webhook sono un modo per le applicazioni Web di comunicare tra loro automaticamente e in tempo reale.

A differenza delle API tradizionali, che aspettano che un utente richieda informazioni, le API in tempo reale condividono i dati nel momento in cui si verificano. I webhook agiscono come API in tempo reale e aiutano a condividere i dati immediatamente ogni volta che si verifica l’evento specificato.

## Entità

Per comprendere gli eventi dei webhook, dobbiamo prima essere consapevoli delle entità coinvolte e delle condizioni di attivazione per questi eventi.

### Oggetti di apprendimento

Di seguito sono riportati gli eventi supportati per gli oggetti di apprendimento (Corso, Percorso di apprendimento o Certificazioni).

#### Bozze

Ogni volta che un oggetto di apprendimento viene creato dall’interfaccia utente, viene avviato in modalità **Bozza**. Ciò significa che l’oggetto di apprendimento non è ancora pubblicato e non è disponibile per gli Allievi. L’evento **LEARNING_OBJECT_DRAFT** viene attivato finché l’oggetto di apprendimento rimane una bozza. Questo evento viene attivato anche da eventuali aggiornamenti successivi della bozza.

#### Aggiornamento

Una volta pubblicato l’oggetto di apprendimento, il suo stato cambia da **Bozza** a **Pubblicato**. Durante questa transizione, Webhook genera l&#39;evento **LEARNING_OBJECT_MODIFICATION** perché l&#39;oggetto di apprendimento viene modificato da **Bozza** a **Pubblicato**. Tutte le modifiche e gli aggiornamenti successivi all’LO attiveranno anche un evento **LEARNING_OBJECT_MODIFICATION**.

L’evento **LEARNING_OBJECT_MODIFICATION** viene attivato anche quando l’oggetto di apprendimento viene ritirato. Questa operazione ritirata contrassegna le istanze sottostanti come aggiornate, poiché queste istanze vengono ritirate una volta che l’oggetto di apprendimento principale è nello stato ritirato.

#### Elimina

Dopo aver eliminato un oggetto di apprendimento, viene generato l’evento **LEARNING_OBJECT_DELETION**. Questo evento indica che l’oggetto di apprendimento è stato eliminato e non è più accessibile agli Allievi.

Oltre agli eventi in tempo reale, gli eventi degli oggetti di apprendimento hanno anche una controparte batch (non in tempo reale), che viene attivata come parte dell’evento **LEARNING_OBJECT_MODIFICATION_BATCH**. Questo evento si verifica durante la creazione o la modifica di un oggetto di apprendimento tramite il flusso di lavoro di migrazione. Poiché le operazioni di bozza ed eliminazione degli oggetti di apprendimento non sono supportate tramite migrazione, non esistono eventi di bozza o eliminazione corrispondenti per queste azioni.

### Istanze dell’oggetto di apprendimento

Di seguito sono riportati gli eventi supportati per le istanze degli oggetti di apprendimento.

#### Aggiornamento

Una volta creata un&#39;istanza, viene generato l&#39;evento **LEARNING_OBJECT_INSTANCE_MODIFICATION**. Le istanze dell’oggetto di apprendimento in Adobe Learning Manager non hanno uno stato **Bozza**, pertanto Adobe Learning Manager non supporta un **evento LEARNING_OBJECT_INSTANCE_DRAFT**. Questo evento viene generato ogni volta che un&#39;istanza viene creata, modificata o ritirata.

Oltre a essere generato al momento della creazione, dell’aggiornamento o del ritiro di un’istanza, questo evento viene generato automaticamente anche quando il relativo oggetto di apprendimento principale è contrassegnato come **Ritirato**. Questo perché quando un oggetto di apprendimento viene ritirato, anche le istanze sottostanti devono essere contrassegnate come **Ritirate**.

#### Elimina

Quando un’istanza viene eliminata, viene generato l’evento **LEARNING_OBJECT_INSTANCE_DELETION**. Questo evento si applica solo alle istanze del corso che contengono moduli a ritmo personalizzato, poiché Adobe Learning Manager consente agli amministratori di eliminare solo le istanze del corso in cui il tipo di modulo è a ritmo personalizzato. Adobe Learning Manager non supporta l’eliminazione esplicita per altri tipi di moduli di corso, non per le istanze del percorso di apprendimento o le istanze di certificazione.

L’istanza dell’oggetto di apprendimento ha anche una controparte non in tempo reale, esposta come parte dell’evento **LEARNING_OBJECT_INSTANCE_MODIFICATION_BATCH**. Questo evento viene attivato durante la creazione o la modifica di un’istanza dell’oggetto di apprendimento tramite il flusso di lavoro di migrazione. Poiché le operazioni di bozza o eliminazione per le istanze degli oggetti di apprendimento non sono supportate nella migrazione, gli eventi di bozza o eliminazione corrispondenti non sono disponibili.

### Iscrizione

Quando un Allievo esegue un’azione di iscrizione, viene attivato un evento di iscrizione in tempo reale. A seconda del tipo di oggetto di apprendimento, l’evento di iscrizione in tempo reale può rientrare in una delle seguenti categorie:

* COURSE_ENROLLMENT
* LEARNING_PATH_ENROLLMENT
* CERTIFICATION_ENROLLMENT

Oltre a questi eventi in tempo reale, gli eventi di iscrizione hanno controparti in batch. Ogni volta che un’iscrizione viene attivata da un amministratore, un manager o una piattaforma, vengono attivati eventi di iscrizione non in tempo reale. In base al tipo di oggetto di apprendimento, l’evento di iscrizione in batch può essere uno dei seguenti:

* COURSE_ENROLLMENT_BATCH
* LEARNING_PATH_ENROLLMENT_BATCH
* CERTIFICATION_ENROLLMENT_BATCH

### Annullamento iscrizione

Quando un Allievo esegue un’azione di annullamento dell’iscrizione, viene attivato un evento di annullamento dell’iscrizione in tempo reale. A seconda del tipo di oggetto di apprendimento, l’evento di annullamento dell’iscrizione in tempo reale può rientrare in una delle seguenti categorie:

* COURSE_UNENROLLMENT
* LEARNING_PATH_UNENROLLMENT
* CERTIFICATION_UNENROLLMENT

Oltre a questi eventi, ci sono anche eventi di annullamento dell&#39;iscrizione in batch. Ogni volta che un’iscrizione viene annullata da un amministratore, un manager o una piattaforma, vengono attivati eventi di annullamento dell’iscrizione non in tempo reale. In base al tipo di oggetto di apprendimento, l’evento di annullamento dell’iscrizione in batch può essere uno dei seguenti:

* COURSE_UNENROLLMENT_BATCH
* LEARNING_PATH_UNENROLLMENT_BATCH
* CERTIFICATION_UNENROLLMENT_BATCH

### Completamento

L’evento di completamento in tempo reale viene attivato ogni volta che un Allievo completa un oggetto di apprendimento. In base al tipo di oggetto di apprendimento, l’evento di completamento in tempo reale può rientrare in una delle seguenti categorie:

* COURSE_COMPLETED
* LEARNING_PATH_COMPLETED
* CERTIFICATION_COMPLETED

Oltre a questi eventi in tempo reale, ci sono anche eventi di completamento in batch. Ad esempio, quando un amministratore, un manager o una piattaforma contrassegna un oggetto di apprendimento come completato, vengono attivati gli eventi di completamento non in tempo reale. In base al tipo di oggetto di apprendimento, l’evento di completamento batch può rientrare in una delle seguenti categorie:

* COURSE_COMPLETED_BATCH
* LEARNING_PATH_COMPLETED_BATCH
* CERTIFICATION_COMPLETED_BATCH

### Avanzamento dell’Allievo

Ogni volta che un Allievo si iscrive a un oggetto di apprendimento e inizia il modulo, viene monitorato l’avanzamento. Questi dati sono inclusi nell&#39;evento **LEARNER_PROGRESS**. L&#39;evento può essere ritardato fino a 15 minuti, poiché il monitoraggio dell&#39;avanzamento si basa su una logica di aggregazione complessa, che non è in tempo reale.

### Statistiche CI

L&#39;evento in tempo reale **CI_STATS** viene attivato ogni volta che si verifica una modifica della disponibilità della postazione o della lista d&#39;attesa per un&#39;istanza del corso. Questi dati vengono acquisiti solo a livello di istanza. Inoltre, questo evento viene attivato per i corsi e non per altri percorsi di apprendimento o certificazioni, in quanto la disponibilità di posti e liste di attesa sono attributi specifici di un corso e della relativa istanza.

## Ordine degli eventi

Adobe Learning Manager garantisce che gli eventi siano ordinati per ogni account. Tuttavia, potrebbero esserci discrepanze quando si correlano i messaggi tra l’iscrizione o il completamento e gli eventi di avanzamento. Ciò accade perché l’evento di avanzamento dell’Allievo può essere ritardato di un massimo di 15 minuti, poiché il tracciamento dell’avanzamento si basa su una logica di aggregazione complessa, che non è in tempo reale. Inoltre, gli eventi di avanzamento provengono da origini dati diverse, pertanto il loro ordine non può essere garantito in relazione agli eventi di iscrizione e completamento. Pertanto, Adobe Learning Manager fornisce ai client procedure ottimali per l&#39;ascolto di questi eventi.

Se l’evento di completamento si verifica prima dell’evento di avanzamento dell’Allievo, il client può ignorare tale evento. Questo si verifica perché l’evento di avanzamento dell’Allievo può essere ritardato di un massimo di 15 minuti, mentre l’evento di completamento può essere attivato prima della ricezione dell’evento di avanzamento. Poiché la ricezione di un evento di completamento indica che l’oggetto di apprendimento è stato completato, significa che l’avanzamento ha raggiunto il 100%.

Nel raro caso in cui l’evento di iscrizione si verifichi dopo l’evento di avanzamento dell’Allievo, il client può ignorare l’evento di iscrizione. Questo perché l’avanzamento può essere monitorato solo dopo che l’Allievo si è iscritto all’oggetto di apprendimento. In altre parole, la ricezione di un evento di avanzamento indica che l’oggetto di apprendimento è stato avviato, il che si verifica solo dopo un’iscrizione riuscita.

## Eventi in tempo reale ed eventi in batch

Alcuni eventi hanno controparti in tempo reale e non in tempo reale, come indicato sopra. Potrebbero esserci domande su quando abbonarsi a eventi in tempo reale e su quando abbonarsi a eventi non in tempo reale. Di seguito sono riportate le linee guida che è possibile seguire in base alle entità descritte in precedenza.

### Eventi in tempo reale

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

### Eventi non in tempo reale

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

### Oggetti di apprendimento e relative istanze

* Abbonati a eventi in tempo reale ogni volta che desideri ascoltare le modifiche agli oggetti di apprendimento apportate tramite le azioni dell’interfaccia utente per ruoli come Amministratore, Autore, ecc.
* Abbonati a eventi in batch o non in tempo reale ogni volta che desideri ascoltare le modifiche apportate agli oggetti di apprendimento tramite i flussi di lavoro di migrazione.

### Iscrizione, annullamento dell’iscrizione e completamento

* Iscriviti a eventi in tempo reale ogni volta che desideri ascoltare iscrizioni, annullamenti di iscrizioni o completamenti eseguiti dagli Allievi.
* Abbonati a eventi in batch o non in tempo reale ogni volta che desideri ascoltare iscrizioni, annullamenti di iscrizioni o completamenti contrassegnati da Amministratore, Manager, Piattaforma, ecc.

### Avanzamento dell’Allievo

* Iscriviti all’evento ogni volta che desideri ascoltare le modifiche di avanzamento di un Allievo.

>[!NOTE]
>
>Negli scenari precedenti (iscrizione, annullamento dell’iscrizione, completamento e avanzamento), le composizioni di attributi consistenti in userId e loInstanceId possono identificare in modo univoco un record.

### Statistiche delle istanze del corso

* Abbonati all&#39;evento **CI_STATS** in tempo reale ogni volta che desideri ascoltare modifiche nella disponibilità di posti o liste di attesa.

## Payload evento webhook

Come parte del payload di risposta dei webhook, Adobe Learning Manager emetterà gli attributi richiesti per identificare in modo univoco un’entità. Questi saranno emessi nello stesso formato e secondo gli standard utilizzati dall’API pubblica, assicurando che i dati del webhook siano sincronizzati con i dati dell’API pubblica. Visualizza [payload di esempio](/help/migrated/integration-admin/feature-summary/webhooks-usage-guide.md#sample-payloads-for-the-events) per vedere i payload dei vari eventi.

## Utilizzo dei webhook per creare un database esterno o un servizio di notifica

Uno dei casi di utilizzo che abbiamo sentito in cui i webhook potrebbero essere utili è per la creazione di un database sul lato del cliente. Adobe Learning Manager dispone di un proprio database e schema, ma i clienti non vi hanno accesso.

La domanda è: in che modo i clienti possono creare un database utilizzando gli eventi dei webhook?

Poiché Adobe Learning Manager non esporrà direttamente i record e lo schema della tabella, i clienti possono fare affidamento sulla soluzione Webhooks per creare un database esterno utilizzando gli eventi per compilarlo. In questa versione, vengono forniti eventi per gli oggetti di apprendimento, le istanze degli oggetti di apprendimento, l’iscrizione, l’annullamento dell’iscrizione, il completamento, l’avanzamento e le statistiche delle istanze del corso.

### Creazione di un database dagli eventi dell’oggetto di apprendimento

Gli eventi oggetto di apprendimento espongono `loId` e `loType` per identificare un&#39;entità. Tuttavia, questi attributi da soli non sono sufficienti per creare un database esterno di oggetti di apprendimento. I clienti avranno bisogno di campi aggiuntivi per descrivere ulteriormente l’oggetto di apprendimento.
Esistono due metodi per recuperare i dati aggiuntivi:

#### Genera un report dei dati di formazione per recuperare tutti i dati

Questo approccio deve essere utilizzato quando gli oggetti di apprendimento vengono creati in blocco tramite flussi di lavoro come la migrazione. L&#39;obiettivo qui è generare il report **[!UICONTROL Dati di formazione]** con tutti gli oggetti di apprendimento acquisiti come parte del flusso di lavoro di migrazione. Per ottimizzare il processo di importazione, si consiglia di impostare l’ora di inizio dell’esportazione sull’ora in cui è stata attivata la migrazione. In questo modo, nel report verranno esportati solo gli oggetti di apprendimento importati tramite la migrazione, poiché i dati cronologici saranno già disponibili nel database del cliente.

#### Eseguire una query sulle informazioni dall’API pubblica GET /learningObjects - Ambito di amministrazione

Questo approccio deve essere utilizzato quando gli oggetti di apprendimento vengono creati tramite flussi di lavoro in tempo reale. Il cliente deve disporre di un proprio livello di memorizzazione nella cache per creare in batch gli oggetti di apprendimento emessi tramite gli eventi, quindi eseguire una query sull&#39;API `GET /learningObjects` passando questi ID degli oggetti di apprendimento. Il motivo per cui disponi di un livello di memorizzazione nella cache è assicurare che i limiti di frequenza delle API pubbliche non vengano superati. Attualmente, i limiti di velocità per gli amministratori sono impostati su 500 richieste all&#39;ora per le API ` GET /learningObject`. Se questo limite viene superato, il servizio API pubblico risponderà con un **messaggio HTTP 429 Troppe richieste**.

### Creazione di un database dall’istanza dell’oggetto di apprendimento e dagli eventi CI_STATS

L’evento Istanza dell’oggetto di apprendimento emette gli attributi `loInstanceId`, `loId` e `loType` per i corsi e i percorsi di apprendimento. Analogamente, l’evento **CI_STATS** è applicabile solo ai corsi poiché `seatLimit`, `seatAvailability`, `waitListLimit`, `waitlistAvailability` e così via sono applicabili solo ai corsi.

In alcuni casi, sono necessari dati di istanza aggiuntivi come il nome, lo stato e così via. Per recuperare ulteriori dati di variante, è necessario seguire il seguente approccio:

#### Eseguire una query sulle informazioni da public-api GET /learningobjects - Ambito amministratore

I clienti possono utilizzare l&#39;API `GET /learningObjects` come indicato in precedenza, insieme alle istanze incluse per recuperare le informazioni sulle istanze. Dovrebbero continuare a seguire l&#39;approccio indicato nella [sezione](/help/migrated/integration-admin/feature-summary/webhooks-usage-guide.md#query-the-information-from-the-public-api-get-learningobjects-admin-scope) per garantire che i limiti delle tariffe non vengano violati.


>[!NOTE]
>
>1. Le certificazioni non hanno il concetto di istanze in ALM.
>2. Non è necessario recuperare dati aggiuntivi per CI_STATS poiché le stesse informazioni sarebbero già state recuperate nell’ambito degli eventi Istanza dell’oggetto di apprendimento.

### Creazione di un database dagli eventi di iscrizione, annullamento dell&#39;iscrizione, completamento e avanzamento

L’iscrizione, l’annullamento dell’iscrizione, il completamento e l’avanzamento degli Allievi vengono emessi come eventi separati in Adobe Learning Manager. L’Allievo è identificato dall’attributo `userId`. Tuttavia, in alcuni casi potrebbero essere necessarie ulteriori informazioni per gli Allievi, ad esempio nome, e-mail e così via, per i flussi di lavoro a valle sul lato cliente. Per recuperare questi dati, i clienti possono seguire l’approccio descritto di seguito:

#### Esportare il report utente dall’amministratore o dai connettori

Questo approccio deve essere seguito ogni volta che sono coinvolti flussi di lavoro in blocco, come l’iscrizione in blocco, l’annullamento in blocco e così via. Il Report utente di Adobe Learning Manager contiene tutte le informazioni relative a un utente. Correlando `userId` ottenuto dall&#39;evento webhook, i clienti possono cercare questo report (che può essere esposto sul lato cliente come database, cache o endpoint API) per recuperare ulteriori dettagli come Nome, E-mail, UUID e così via. Questo approccio può essere utilizzato per sincronizzare gli utenti su base settimanale o giornaliera.

#### Query di informazioni da API pubbliche GET /users - Ambito amministratore

Questo approccio può essere seguito quando gli utenti non sono disponibili nel report precedente. La combinazione degli approcci 1 e 2 garantisce che tutti gli utenti esistenti che sono stati creati in passato possano essere coperti dal **[!UICONTROL Report utente]**, mentre gli utenti appena creati possono ancora essere recuperati dall&#39;API. Se il **[!UICONTROL report utente]** non dispone dei dati, il cliente può inviare gli userId come argomenti di input all&#39;API `GET /users` per recuperare le informazioni utente. Queste informazioni devono essere memorizzate nella cache dal lato del cliente per evitare ripetute chiamate all’API pubblica per lo stesso insieme di utenti. Al momento, i limiti di tariffa per l’Amministratore sono impostati su 500 richieste all’ora per le API GET /users. Qualsiasi richiesta oltre questo limite produrrà una risposta **HTTP 429 Troppe richieste**.

## Tolleranza di errore

La tolleranza agli errori del sistema webhook ALM fornisce raccomandazioni agli abbonati per la gestione di potenziali problemi, come perdita di eventi, eventi duplicati e recapito fuori ordine.

ALM ha un timeout di connessione configurato su 10 secondi e un timeout del socket configurato su 5 secondi. Ci si aspetta che il client riconosca il messaggio non appena lo riceve. In questo modo, il client non subirà ritardi durante l&#39;elaborazione dei messaggi. Nel caso in cui si verifichi un&#39;elaborazione a valle che richiede tempo, il client deve comunque riconoscere immediatamente l&#39;evento e quindi gestire l&#39;elaborazione a valle alla loro fine.

### Conservazione dei dati

Gli eventi sono conservati per 7 giorni. Se non vengono elaborati entro questo periodo di tempo, vengono persi definitivamente. Se il ripristino avviene nell&#39;ultimo giorno e occorre più tempo, il sistema non estenderà il periodo di conservazione.
Se gli eventi vengono prodotti più velocemente di quanto vengono utilizzati, alcuni eventi potrebbero andare perduti. Sebbene ciò sia raro, gli abbonati devono monitorare per evitare che diventi un problema a lungo termine.

### Webhook disabilitati

Quando un abbonato non risponde agli eventi webhook, il sistema ALM tenta di utilizzare i webhook con un backoff esponenziale per evitare di sopraffare il sottoscrittore.

Il processo di nuovo tentativo inizia con un intervallo iniziale di 5 secondi. Se l&#39;abbonato non risponde, il tempo di attesa raddoppia a 10, 20, 40 e 80 secondi, aumentando fino a un massimo di 5 minuti. Una volta raggiunti i 5 minuti, il sistema continuerà a riprovare ogni 5 minuti fino al termine del periodo di conservazione di 7 giorni. Se il sottoscrittore continua a non rispondere per tutto questo periodo, il webhook verrà disabilitato automaticamente. Un’e-mail di promemoria verrà inviata all’abbonato a intervalli regolari.

### Eventi duplicati

Se un sottoscrittore impiega più di 5 secondi per rispondere dopo aver elaborato un evento, il sistema potrebbe tentare di elaborare nuovamente lo stesso evento. Si consiglia di utilizzare gli ID evento per tenere traccia degli eventi che sono già stati elaborati. Inoltre, se il webhook si arresta in modo anomalo dopo l’invio dell’evento ma prima del salvataggio che è stato elaborato, è possibile che venga eseguito un nuovo tentativo per lo stesso gruppo di eventi. Si consiglia di utilizzare ID batch o singoli ID evento per riconoscere e ignorare eventuali duplicati.

### Eventi non ordinati

ALM tenta di mantenere gli eventi nell&#39;ordine corretto, ma a volte gli eventi possono essere consegnati in modo non corretto, specialmente tra eventi in tempo reale e non in tempo reale.

Se un amministratore iscrive più allievi a un corso contemporaneamente, gli eventi di iscrizione sono contrassegnati come non in tempo reale. Tuttavia, se un Allievo completa rapidamente il corso, l’evento di completamento viene contrassegnato come in tempo reale e potrebbe essere inviato prima degli eventi di iscrizione.

### Raccomandazione per la tolleranza agli errori

Per evitare questi errori, gli abbonati devono monitorare attivamente gli eventi webhook e configurare avvisi per problemi come eventi mancati, consegne duplicate o sequenze di guasti.

## Linee guida specifiche per gli eventi webhook

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

## Webhook Procedure consigliate per il consumo di eventi

* La soluzione webhook viene utilizzata per gestire sistemi ad alto throughput in cui velocità e bassa latenza sono essenziali. Pertanto, il cliente deve assicurarsi che l&#39;evento venga confermato non appena ricevuto. Anche se è necessaria un&#39;elaborazione aggiuntiva da parte del cliente (ad esempio il recupero di dati da report, API o l&#39;esecuzione di altre azioni), la conferma deve essere inviata non appena viene ricevuto l&#39;evento e spetta al client elaborare l&#39;evento in un secondo momento.
* Il mancato riconoscimento dell’evento il prima possibile potrebbe incidere sulla natura in tempo reale degli eventi, poiché gli eventi successivi saranno emessi solo una volta ricevuto il precedente riconoscimento.
* I client possono rispondere con un codice di stato HTTP 202 Accettato per confermare che l&#39;evento è stato accettato.

## Limitazioni

* Le risorse formative non vengono considerate per gli eventi Webhook nella categoria degli LO perché vengono in genere utilizzate per aiutare gli Allievi a completare altri oggetti di apprendimento.
* Il ritiro di un’istanza di un oggetto di apprendimento viene considerato un evento di aggiornamento. Non ci sarebbe un evento di eliminazione per un&#39;istanza poiché può essere solo ritirata, non eliminata.
* Le modifiche alla sessione verranno acquisite come parte dell&#39;evento di aggiornamento dell&#39;istanza. Questo vale solo per i corsi. Non ci sarà alcuna propagazione verso l&#39;alto da entità di livello inferiore per le istanze del percorso di apprendimento o le istanze di certificazione.
* Se un percorso di apprendimento contiene un corso e un Allievo lo completa tramite, verranno generati due eventi **LearnerProgress**: uno per il corso e uno per il percorso di apprendimento.
* Alcuni flussi di lavoro calcolano gli attributi degli oggetti di apprendimento, come la durata e il tipo di distribuzione, in modo asincrono. Pertanto, gli eventi per questi oggetti di apprendimento verranno generati una volta che il processo cron avrà terminato l’elaborazione.

## Payload di esempio per gli eventi

+++CI_STATS

```
{
  "accountId": 1234,
  "events": [
    {
      "eventId": "12345-0458-4450-b5dd-6bc1ef4f8b50",
      "eventName": "CI_STATS",
      "timestamp": "2024-11-08T03:49:52.000Z",
      "eventInfo": "123456785-LoSt",
      "data": {
        "loInstanceId": "course:12345678_14448475",
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
      "eventId": "12345c1-4576-4ec5-a057-3a6f078cc9d6",
      "eventName": "COURSE_ENROLLMENT",
      "timestamp": "2024-11-08T03:49:52.000Z",
      "eventInfo": "123424713000-040366-10488-0",
      "data": {
        "userId": 12345678,
        "loId": "course:12345678",
        "loInstanceId": "course:12345678_14450088",
        "loType": "course",
        "enrollmentSource": "SELF_ENROLL",
        "dateEnrolled": "2024-11-08T03:49:52.000Z"
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
      "eventId": "1234ec1-4576-4ec5-a057-3a6f078cc9d6",
      "eventName": "COURSE_ENROLLMENT_BATCH",
      "timestamp": "2024-11-08T03:49:52.000Z",
      "eventInfo": "123424713000-040366-10488-0",
      "data": {
        "userId": 12345678,
        "loId": "course:12345678",
        "loInstanceId": "course:12345678_14450088",
        "loType": "course",
        "enrollmentSource": "ADMIN_ENROLL",
        "dateEnrolled": "2024-11-08T03:49:52.000Z"
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
      "eventId": "c2345c-6c98-4ed3-b0b0-ba3da5087c1c",
      "eventName": "COURSE_COMPLETED",
      "timestamp": "2024-11-08T03:49:52.000Z",
      "eventInfo": "12345823000-040363-12018-0",
      "data": {
        "userId": 11080928,
        "loId": "course:12345678",
        "loInstanceId": "course:12345678_14448484",
        "loType": "course",
        "enrollmentSource": "SELF_ENROLL",
        "dateCompleted": "2024-11-08T03:49:52.000Z",
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
      "eventId": "c23458c-6c98-4ed3-b0b0-ba3da5087c1c",
      "eventName": "COURSE_COMPLETED_BATCH",
      "timestamp": "2024-11-08T03:49:52.000Z",
      "eventInfo": "123456823000-040363-12018-0",
      "data": {
        "userId": 12345678,
        "loId": "course:12345678",
        "loInstanceId": "course:12345678_14448484",
        "loType": "course",
        "enrollmentSource": "ADMIN_ENROLL",
        "dateCompleted": "2024-11-08T03:49:52.000Z",
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
      "eventId": "1234791-338f-4c4c-83bc-9f73ea794965",
      "eventName": "LEARNING_PATH_ENROLLMENT",
      "timestamp": "2024-11-08T03:49:52.000Z",
      "eventInfo": "123404248000-040653-71396-0",
      "data": {
        "userId": 12345678,
        "loId": "learningProgram:1234567",
        "loInstanceId": "learningProgram:1234567_109139",
        "loType": "learningProgram",
        "enrollmentSource": "SELF_ENROLL",
        "dateEnrolled": "2024-11-08T03:49:52.000Z"
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
      "eventId": "12340791-338f-4c4c-83bc-9f73ea794965",
      "eventName": "LEARNING_PATH_ENROLLMENT_BATCH",
      "timestamp": "2024-11-08T03:49:52.000Z",
      "eventInfo": "123404248000-040653-71396-0",
      "data": {
        "userId": 12345678,
        "loId": "learningProgram:1234557",
        "loInstanceId": "learningProgram:1234557_109139",
        "loType": "learningProgram",
        "enrollmentSource": "ADMIN_ENROLL",
        "dateEnrolled": "2024-11-08T03:49:52.000Z"
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
      "eventId": "123404e-d554-4027-944b-086debefdddf",
      "eventName": "LEARNING_PATH_COMPLETED",
      "timestamp": "2024-11-08T03:49:52.000Z",
      "eventInfo": "1234604391000-040653-314618-0",
      "data": {
        "userId": 12345678,
        "loId": "learningProgram:92348",
        "loInstanceId": "learningProgram:92348_95662",
        "loType": "learningProgram",
        "enrollmentSource": "SELF_ENROLL",
        "dateCompleted": "2024-11-08T03:49:52.000Z",
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
      "eventId": "12344e-d554-4027-944b-086debefdddf",
      "eventName": "LEARNING_PATH_COMPLETED_BATCH",
      "timestamp": "2024-11-08T03:49:52.000Z",
      "eventInfo": "123404391000-040653-314618-0",
      "data": {
        "userId": 12345678,
        "loId": "learningProgram:92348",
        "loInstanceId": "learningProgram:92348_95662",
        "loType": "learningProgram",
        "enrollmentSource": "ADMIN_ENROLL",
        "dateCompleted": "2024-11-08T03:49:52.000Z",
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
      "eventId": "1234e776-148e-4128-80e9-b896a460b655",
      "eventName": "CERTIFICATION_ENROLLMENT",
      "timestamp": "2024-11-08T03:49:52.000Z",
      "eventInfo": "12344672000-040654-559128-0",
      "data": {
        "userId": 12345678,
        "loId": "certification:123418",
        "loInstanceId": "certification:123418_160299",
        "loType": "certification",
        "enrollmentSource": "SELF_ENROLL",
        "dateEnrolled": "2024-11-08T03:49:52.000Z"
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
      "eventId": "123472ec1-4576-4ec5-a057-3a6f078cc9d6",
      "eventName": "COURSE_ENROLLMENT_BATCH",
      "timestamp": "2024-11-08T03:49:52.000Z",
      "eventInfo": "1234524713000-040366-10488-0",
      "data": {
        "userId": 12345678,
        "loId": "course:123456798",
        "loInstanceId": "course:12345678_14450088",
        "loType": "course",
        "enrollmentSource": "ADMIN_ENROLL",
        "dateEnrolled": "2024-11-08T03:49:52.000Z"
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
      "eventId": "1234bf8-7521-4bc0-bc51-7f951ff63ea9",
      "eventName": "CERTIFICATION_COMPLETED",
      "timestamp": "2024-11-08T03:49:52.000Z",
      "eventInfo": "123454768000-040654-756257-0",
      "data": {
        "userId": 123456728,
        "loId": "certification:123418",
        "loInstanceId": "certification:134518_160299",
        "loType": "certification",
        "enrollmentSource": "SELF_ENROLL",
        "dateCompleted": "2024-11-08T03:49:52.000Z"
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
      "eventId": "123453bf8-7521-4bc0-bc51-7f951ff63ea9",
      "eventName": "CERTIFICATION_COMPLETED_BATCH",
      "timestamp": "2024-11-08T03:49:52.000Z",
      "eventInfo": "1234604768000-040654-756257-0",
      "data": {
        "userId": 12345678,
        "loId": "certification:123418",
        "loInstanceId": "certification:123418_160299",
        "loType": "certification",
        "enrollmentSource": "ADMIN_ENROLL",
        "dateCompleted": "2024-11-08T03:49:52.000Z"
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
      "eventId": "d1234d3a4-c3df-44fa-a1cf-7edd6e3d2075",
      "eventName": "LEARNER_PROGRESS",
      "timestamp": "2024-11-08T03:49:52.000Z",
      "eventInfo": "1235604551000-297002-5823-0",
      "data": {
        "loId": "course:7542090",
        "loType": "course",
        "userId": 12380928,
        "loInstanceId": "course:7232090_10423047",
        "dateStarted": "2024-11-08T03:49:52.000Z",
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
      "eventId": "f3237817-8cb8-40ea-a441-813bec1c7724",
      "eventName": "COURSE_UNENROLLMENT",
      "timestamp": "2024-11-08T03:49:52.000Z",
      "eventInfo": "1345506253000-040298-24078-0",
      "data": {
        "userId": 12311591,
        "loId": "course:12324298",
        "loInstanceId": "course:12324298_14450088",
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
      "eventId": "f2317817-8cb8-40ea-a441-813bec1c7724",
      "eventName": "COURSE_UNENROLLMENT_BATCH",
      "timestamp": "2024-11-08T03:49:52.000Z",
      "eventInfo": "17235506253000-040298-24078-0",
      "data": {
        "userId": 12311591,
        "loId": "course:12324298",
        "loInstanceId": "course:12324298_14450088",
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
      "eventId": "823df878-1dfd-47ac-9bfe-7d4952e3edd1",
      "eventName": "LEARNING_PATH_UNENROLLMENT",
      "timestamp": "2024-11-08T03:49:52.000Z",
      "eventInfo": "1235506667000-040299-28209-0",
      "data": {
        "userId": 12311591,
        "loId": "learning_program:123157",
        "loInstanceId": "learning_program:123157_109139",
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
      "eventId": "8e23f878-1dfd-47ac-9bfe-7d4952e3edd1",
      "eventName": "LEARNING_PATH_UNENROLLMENT_BATCH",
      "timestamp": "2024-11-08T03:49:52.000Z",
      "eventInfo": "1235506667000-040299-28209-0",
      "data": {
        "userId": 12311591,
        "loId": "learning_program:123157",
        "loInstanceId": "learning_program:123157_109139",
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
      "eventId": "7232766b-54d8-472d-b933-7e89d1b75ef8",
      "eventName": "CERTIFICATION_UNENROLLMENT",
      "timestamp": "2024-11-08T03:49:52.000Z",
      "eventInfo": "1235507900000-040304-1065-0",
      "data": {
        "userId": 12311591,
        "loId": "certification:123199",
        "loInstanceId": "certification:123199_162078",
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
      "eventId": "7202766b-54d8-472d-b933-7e89d1b75ef8",
      "eventName": "CERTIFICATION_UNENROLLMENT_BATCH",
      "timestamp": "2024-11-08T03:49:52.000Z",
      "eventInfo": "1735507900000-040304-1065-0",
      "data": {
        "userId": 12511591,
        "loId": "certification:139199",
        "loInstanceId": "certification:139199_162078",
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
      "eventId": "12345da9f-26ec-453c-b56a-cdf18a841948",
      "eventName": "LEARNING_OBJECT_DRAFT",
      "timestamp": "2024-11-08T03:49:52.000Z",
      "eventInfo": "1234519188000-040344-48604-0",
      "data": {
        "loId": "course:1234091",
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
      "eventId": "1234a690-5517-4c09-9cde-d953cdd8582c",
      "eventName": "LEARNING_OBJECT_DELETION",
      "timestamp": "2024-11-08T03:49:52.000Z",
      "eventInfo": "1235605296000-040656-662792-0",
      "data": {
        "loId": "course:12319716",
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
  "accountId": 8308,
  "events": [
    {
      "eventId": "223e068-af3e-4dd3-a515-ce19d7234873",
      "eventName": "LEARNING_OBJECT_MODIFICATION",
      "timestamp": "2024-11-08T03:49:52.000Z",
      "eventInfo": "123350842000-039736-54153-0",
      "data": {
        "loId": "learningProgram:123836",
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
  "accountId": 8308,
  "events": [
    {
      "eventId": "1234e068-af3e-4dd3-a515-ce19d7234873",
      "eventName": "LEARNING_OBJECT_MODIFICATION_BATCH",
      "timestamp": "2024-11-08T03:49:52.000Z",
      "eventInfo": "1235350842000-039736-54153-0",
      "data": {
        "loId": "learningProgram:123836",
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

+++

+++LEARNING_OBJECT_INSTANCE_MODIFICATION_BATCH

```
{
  "accountId": 1234,
  "events": [
    {
      "eventId": "1231da98-ab8d-43e9-b671-e79131cd69dc",
      "eventName": "LEARNING_OBJECT_INSTANCE_MODIFICATION_BATCH",
      "timestamp": "2024-11-08T03:49:52.000Z",
      "eventInfo": "123603297000-040649-741781-0",
      "data": {
        "loInstanceId": "course:12324298_14453691",
        "loId": "course:12324298",
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
      "eventId": "12d16e90-d73a-457b-83f3-666ba9654edb",
      "eventName": "LEARNING_OBJECT_INSTANCE_DELETION",
      "timestamp": "2024-11-08T03:49:52.000Z",
      "eventInfo": "1235605491000-040657-236307-0",
      "data": {
        "loInstanceId": "course:12319674_14453849",
        "loId": "course:12319674",
        "loType": "course"
      }
    }
  ]
}
```

+++
