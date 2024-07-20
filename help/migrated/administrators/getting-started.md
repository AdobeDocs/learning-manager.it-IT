---
description: Questo documento fornisce informazioni sull’approccio consigliato per configurare Adobe Learning Manager. Il team Learning Manager suggerisce un approccio graduale per iniziare a utilizzare l’applicazione. Non è obbligatorio seguire tutte le fasi in base a una sequenza specifica.
jcr-language: en_us
title: La guida con le migliori procedure per la configurazione di Learning Manager
contentowner: jayakarr
preview: true
source-git-commit: 46afb6603456ced9d7e2aaf98d07ec92fee30c0b
workflow-type: tm+mt
source-wordcount: '3387'
ht-degree: 71%

---



# La guida con le migliori procedure per la configurazione di Learning Manager

Questo documento fornisce informazioni sull’approccio consigliato per configurare Adobe Learning Manager. Il team Learning Manager suggerisce un approccio graduale per iniziare a utilizzare l’applicazione. Non è obbligatorio seguire tutte le fasi in base a una sequenza specifica.

Queste fasi possono essere eseguite da tre ruoli diversi, da uno o più utenti in base alla configurazione dell&#39;organizzazione. I tre ruoli sono i seguenti:

1. **Amministratore IT** - L’Amministratore IT esegue attività relative all’attivazione o all’integrazione associate all’applicazione Learning Manager in un’organizzazione. Inoltre, l’Amministratore IT può aggiungere uno o più utenti e svolgere il ruolo di Amministratore dell’integrazione.
1. **Autore** - L’Autore crea i contenuti di apprendimento necessari per le esigenze dell’organizzazione. L’Autore dei contenuti di formazione o apprendimento dell’organizzazione può iniziare a creare i contenuti di base necessari per l’applicazione Learning Manager.
1. **Amministratore Learning Manager** - L’Amministratore dell’applicazione Learning Manager esegue le attività di configurazione. In alcune aziende, l’Amministratore IT può anche svolgere il ruolo di Amministratore dell’applicazione Learning Manager.

Puoi esaminare l’infografica fornita di seguito per ottenere una panoramica delle fasi e delle attività corrispondenti.

![](assets/learning-manager-getting-started.jpg)

In questa fase, partiamo dal presupposto che la tua organizzazione abbia già ricevuto il codice di licenza e che tu abbia attivato l’account Learning Manager. Come indicato nell’infografica, le tre fasi vengono illustrate come segue:

## Fase 1 - Configurazione tecnica (Amministratore IT) {#phase1technicalsetupitadministrator}

Nel percorso 1, l’Amministratore IT della tua organizzazione può passare al ruolo di Amministratore dell’integrazione nell’applicazione Learning Manager ed eseguire alcune attivazioni e integrazioni nel modo seguente:

### Abilita/Aggiungi campi attivi (Amministratore di Learning Manager) {#enableaddactivefieldscaptivateprimeadministrator}

Oltre ai campi attivi forniti dagli utenti durante la registrazione, l’Amministratore può aggiungere altri campi attivi. Inoltre, l’Amministratore può attivare/disattivare i campi utente. I valori per questi campi attivi vengono generati dai metadati provenienti da varie origini dati associate agli account utente. Per ulteriori informazioni, fai riferimento alla [Guida ai campi attivi](feature-summary/add-users-user-groups.md#active-fields).

### Accesso unico (Single Sign-On, SSO) {#singlesignonsso}

È possibile accedere all’applicazione Learning Manager utilizzando l’Adobe ID o l’accesso unico. L’accesso unico è un meccanismo che consente a un utente di autenticarsi una volta sola e di accedere a più applicazioni molte volte. Questa configurazione non è obbligatoria per l’organizzazione. Se l’organizzazione dispone di un provider SSO basato su SAML 2.0, è possibile utilizzarlo per configurare l’applicazione Learning Manager. La configurazione è richiesta a livello di organizzazione e per l’applicazione Learning Manager. Se decidi di utilizzare SSO, contatta l’assistenza Adobe per ricevere le istruzioni di configurazione. Per ulteriori informazioni, fai riferimento alla [Guida alle impostazioni](feature-summary/settings.md).

### Importazione degli utenti in blocco {#bulkimportofusers}

Quando disponi di un elevato numero di utenti nell’organizzazione, è possibile importare tutti gli utenti in blocco nell’applicazione Learning Manager, utilizzando un file .CSV. Prima di eseguire questa operazione, ti consigliamo di esportare l’elenco degli utenti dall’applicazione HR dell’organizzazione in formato .CSV. Anche se in questa fase gli utenti non vengono importati in blocco, è possibile familiarizzare con il formato CSV. Per iniziare con il processo di importazione in Learning Manager, carichi il file .CSV e mappa i campi dei dati dell’applicazione con le colonne CSV dell’organizzazione. Per ulteriori informazioni, fai riferimento alla [Guida all&#39;importazione in blocco](add-users-in-bulk.md).

### Integrazione del connettore FTP {#ftpconnectorintegration}

Se all’interno della tua organizzazione si verifica una continua aggiunta o rimozione dei dipendenti, puoi scegliere di automatizzare l’importazione in blocco degli utenti utilizzando il connettore FTP. Una volta stabilita una connessione, carica un CSV e mappa gli attributi del CSV con i corrispondenti campi di Learning Manager. È possibile pianificare il processo di importazione automatica e sincronizzarlo a seconda delle esigenze. Per ulteriori informazioni, fai riferimento alla [Guida al connettore FTP](../integration-admin/feature-summary/connectors.md#ftpconnector).

### Integrazione del connettore Salesforce {#salesforceconnectorintegration}

Se disponi di un account Salesforce nell’organizzazione, è possibile automatizzare il processo di importazione di tutti gli utenti da Salesforce all’applicazione Learning Manager. Se desideri utilizzare questa funzione, è possibile utilizzare il connettore Salesforce per integrare Learning Manager con l’account Salesforce e automatizzare la sincronizzazione dei dati. Utilizza la funzione di pianificazione automatica per eseguire regolarmente l’importazione automatica degli utenti. Inoltre, è possibile eseguire la sincronizzazione su base giornaliera. Per ulteriori informazioni, fai riferimento alla [Guida al connettore Salesforce](../integration-admin/feature-summary/connectors.md#sfconnector).

### Integrazione Adobe Connect {#adobeconnectintegration}

Se utilizzi Adobe Connect nella tua organizzazione, è possibile integrarlo con l’applicazione Adobe Learning Manager per offrire agli Allievi un’esperienza utente ottimale. L’integrazione consente agli Allievi di accedere alle classi virtuali all’interno dell’applicazione Learning Manager con un semplice clic, senza dover accedere nuovamente ad Adobe Connect. Tramite questa funzione, gli Allievi possono anche seguire le sessioni di classe virtuale registrate all’interno dell’applicazione Learning Manager. Prima di procedere, integra le impostazioni. Vai a **Impostazioni > Adobe Connect > Configura ora** per fornire l’URL di Connect e le credenziali di accesso e procedere con l’integrazione. Per ulteriori informazioni, fai riferimento alla [Guida all’integrazione Adobe Connect](feature-summary/adobeconnect-integration.md).

### Registrazione all’app Salesforce {#salesforceappregistration}

Gli Allievi della tua azienda possono godere di un’esperienza ottimale nell’accedere all’app Learning Manager all’interno dei loro account Salesforce. Gli Allievi possono accedere ai contenuti di apprendimento assegnati come ad esempio corsi, programmi di apprendimento e risorse formative provenienti dall’applicazione Salesforce. Inoltre, gli utenti possono accedere alle notifiche e agli annunci dell’app Learning Manager all’interno di Salesforce. Per utilizzare questa funzionalità, è necessario registrare l’app in primo piano Salesforce nell’applicazione Learning Manager. Per ulteriori informazioni relative alle istruzioni per l’installazione e l’uso, fai riferimento alla [Guida all’app Salesforce](../integration-admin/feature-summary/sfdc-app.md).

## Fase 2 - Configurazione del sito (Amministratore di Learning Manager) {#phase2siteconfigurationcaptivateprimeadministrator}

L’Amministratore dell’applicazione Learning Manager dell’organizzazione deve configurare alcune funzioni prima di iniziare a renderle accessibili agli Allievi.

### Branding {#branding}

Un’organizzazione potrebbe voler visualizzare il logo aziendale nell’applicazione Learning Manager, avere un proprio dominio nell’URL, visualizzare il nome dell’organizzazione e visualizzare combinazioni di colori che corrispondano al marchio di un’organizzazione. Learning Manager consente alle organizzazioni di usufruire di tutte queste funzioni. Per personalizzare le impostazioni e utilizzare il proprio marchio, fai clic sulla sezione Branding nel riquadro di sinistra. Fai clic su Modifica accanto a tutte queste opzioni e personalizza in base alle esigenze. Per ulteriori informazioni, fai riferimento alla [Guida al branding e ai temi](feature-summary/themes.md).

### Aggiunta di utenti/gruppi di utenti {#addusersusergroups}

Dal momento che gli Allievi sono gli utenti principali dei contenuti di apprendimento, l’aggiunta di utenti nel sistema di gestione dell’apprendimento rappresenta il passaggio principale. Aggiungi gli utenti all’applicazione Learning Manager e assegna loro dei ruoli. È possibile aggiungere utenti nei modi seguenti:

#### Aggiunta di utenti (interni) {#addusersinternal}

* **Come singolo utente**: l’aggiunta di singoli utenti nell’applicazione Learning Manager consente di effettuare una prova con alcuni utenti prima di aggiungerli in blocco. Inoltre, questa opzione è utile quando si desidera aggiungere più utenti singoli in base alle esigenze, dopo l’importazione in blocco degli utenti.
* **Registrazione autonoma**: questa opzione consente agli amministratori di consentire ai dipendenti di registrarsi a Learning Manager.
* **Importazione in blocco** (tramite caricamento CSV): utilizzando questa opzione è possibile importare gli utenti in blocco nell’applicazione Learning Manager. Come prerequisito, è necessario preparare l’elenco degli utenti in formato CSV prima di utilizzare questa funzione.

#### Aggiunta di utenti (profili esterni) {#addusersexternalprofiles}

* Tramite l’iscrizione esterna: utilizzando questa opzione, è possibile iscrivere all’applicazione i membri esterni del reparto o i dipendenti esterni dell’organizzazione.

#### Aggiunta di gruppi di utenti {#addusergroups}

L’applicazione Learning Manager genera gruppi predefiniti di utenti in base ad attributi simili. Oltre ai gruppi predefiniti, è possibile generare gruppi di utenti personalizzati in base a parametri quali ad esempio il titolo e la posizione in modo da poter utilizzare questi gruppi nella gamification, nei report e così via. Per ulteriori informazioni, fai riferimento alla [Guida all’aggiunta di utenti](feature-summary/add-users-user-groups.md).

### Assegnazione dei ruoli {#assignroles}

Una volta aggiunti gli utenti a Learning Manager, l’Amministratore può iniziare ad assegnare agli utenti i ruoli Autore, Amministratore o Amministratore dell’integrazione in base ai requisiti dell’organizzazione. Per assegnare ruoli agli utenti, nell&#39;accesso come Amministratore fai clic su **[!UICONTROL Utenti]** nel riquadro a sinistra, seleziona la casella di controllo relativa a ciascun nome utente e fai clic su **[!UICONTROL Azioni]** nell&#39;elenco a discesa per scegliere il ruolo che desideri assegnare. I ruoli Manager vengono assegnati agli utenti da Adobe Learning Manager in base ai ruoli/privilegi indicati dalla tua organizzazione nel file CSV. Puoi anche modificare i ruoli di Manager assegnati agli utenti utilizzando il flusso di lavoro Modifica utenti. Per ulteriori informazioni, fai riferimento alla [Guida all’aggiunta di utenti](feature-summary/add-users-user-groups.md).

### Modelli di notifica {#notificationtemplates}

Le notifiche possono essere utili per gli utenti di un sistema di gestione dell’apprendimento per conoscere il proprio stato o per rimanere aggiornati sugli eventi/attività. Gli Allievi, i Manager, gli Amministratori o gli Autori ricevono notifiche relative alle varie attività svolte dagli utenti durante la creazione dei corsi, la configurazione delle funzioni o la fruizione dei corsi. L’applicazione Learning Manager fornisce diversi modelli e-mail di notifica. In qualità di Amministratore, è possibile personalizzarli in base alle esigenze dell’organizzazione. Seleziona **Modelli e-mail** nel riquadro di sinistra e fai clic sul nome del modello per creare notifiche e-mail. Per ulteriori informazioni, fai riferimento alla [Guida ai modelli e-mail](feature-summary/email-templates.md).

**Disattiva le notifiche e-mail (consigliato)**

Per impostazione predefinita, le notifiche sono attive nell’applicazione Learning Manager. Se non si desidera inviare una notifica ai dipendenti dell’organizzazione, è possibile disattivare le notifiche in questa fase.

### Distintivi {#badges}

I distintivi sono unità di misura dei risultati raggiunti che gli allievi ottengono al completamento di un corso. I professionisti di tutto il mondo utilizzano questi distintivi per rappresentare un’abilità particolare o un risultato di apprendimento. È possibile creare una raccolta di distintivi in modo da poterli assegnare agli Allievi al termine dei contenuti di apprendimento. Fai clic sulla funzione **[!UICONTROL Distintivi]** nel riquadro di sinistra, per iniziare a creare i distintivi. Per ulteriori informazioni, fai riferimento alla [Guida ai distintivi](feature-summary/badges.md).

### Feedback {#feedback}

Il feedback è uno dei principali fattori di un LMS per valutare i progressi nell’apprendimento degli Allievi e garantire la qualità dei contenuti dell’apprendimento. Learning Manager offre agli utenti due tipi di opzioni di feedback.

* Il feedback L1 è il feedback ricevuto dagli Allievi dopo aver completato il corso.
* Il feedback L3 è il feedback fornito dagli Allievi agli Allievi in base all’impatto del corso sul comportamento degli Allievi e sulle attività quotidiane.

Questa funzione è facoltativa. Gli Amministratori possono personalizzare i modelli di feedback in base alle esigenze dell’organizzazione. Per utilizzare questa funzione, l’Amministratore deve abilitare le opzioni di feedback L1 e L3 a livello di istanza del corso. Per configurare il feedback, seleziona un corso qualsiasi, fai clic su Impostazioni predefinite istanza nel riquadro di sinistra e abilita l’opzione di feedback. Per ulteriori informazioni, fai riferimento alla [Guida ai feedback](feature-summary/courses.md).

### Gamification {#gamification}

Coinvolgere gli Allievi mentre fruiscono dei contenuti è una delle sfide affrontate dalle organizzazioni. La gamification aumenta la percentuale di completamento del corso coinvolgendo e motivando gli Allievi a raggiungere i propri obiettivi, tramite tecniche di gioco. Gli Allievi possono competere con i colleghi per guadagnare punti per diverse attività di apprendimento e raggiungere livelli bronzo, argento, oro e platino. Gli Amministratori possono attivare/disattivare ogni attività di gamification e modificare l’assegnazione dei punti alle attività. Learning Manager fornisce la funzionalità Gamification con alcune impostazioni predefinite. Per un certo periodo di tempo, è possibile iniziare a utilizzare la funzione con le impostazioni predefinite, le quali possono essere personalizzate in seguito. È possibile configurare o modificare le impostazioni per questa funzione. Se disponi di un esperto in materia nell’organizzazione, si consiglia di configurare le impostazioni prima di utilizzarla. Per ulteriori informazioni, fai riferimento alla [Guida alla gamification](feature-summary/gamification.md).

### Creazione di oggetti di apprendimento {#createlearningobjects}

Questa è la fase logica in cui tutte e tre le fasi (fase 1, fase 2 e fase 3) convergono per consentirti di intraprendere le procedure successive.

A questo punto, una volta creati i moduli e i corsi, è possibile iniziare a creare oggetti di apprendimento di livello superiore, quali certificazioni, programmi di apprendimento o risorse formative per continuare. Prima di iniziare a creare oggetti di apprendimento, assicurati di aver già aggiunto alcuni utenti all’applicazione Learning Manager e di aver creato alcuni moduli e corsi.

#### Creazione di certificazioni {#createcertifications}

La certificazione è una prova del completamento di un contenuto di apprendimento o un attestato di profitto per gli Allievi su base ricorrente o una tantum. Fornendo agli Allievi una certificazione a seguito del completamento del corso, è possibile ottenere un aumento delle iscrizioni ai contenuti di apprendimento. In qualità di Amministratore è possibile creare un programma di certificazione ospitato internamente o condotto da terze parti. Nella certificazione interna, definisci i corsi che un Allievo deve completare per essere certificato. Prima di creare la certificazione, assicurati di disporre di alcuni corsi nell’account. Per ulteriori informazioni relative alla creazione delle certificazioni, fai riferimento alla [Guida alla certificazione](feature-summary/certifications.md).

#### Creazione di risorse formative {#createjobaids}

Risorse formative è un archivio del contenuto di formazione accessibile agli Allievi senza alcun requisito di completamento o di iscrizione. Gli Allievi possono fare riferimento a queste risorse formative per ottenere assistenza relativa all’esecuzione di qualsiasi operazione o attività in un’organizzazione. Sebbene non sia obbligatorio utilizzare le risorse formative come parte della creazione del corso, il team Learning Manager consiglia, come buona prassi, di crearle. Per informazioni sulla creazione delle risorse formative, consultare la [Guida alle risorse formative](../authors/feature-summary/job-aids.md).

#### Creazione di programmi di apprendimento {#createlearningprograms}

I programmi di apprendimento sono un set di corsi progettati specificatamente per soddisfare specifici obiettivi di apprendimento. Prima di creare programmi di apprendimento, assicurati di aver già creato alcuni corsi o di disporre di corsi esistenti nel tuo account.  Sebbene questa funzione sia facoltativa, il team di Learning Manager consiglia di utilizzarla per favorire un apprendimento mirato da parte dei dipendenti. Per iniziare a utilizzare i programmi di apprendimento, fai clic su Programmi di apprendimento nel riquadro di sinistra, seleziona un insieme di corsi dal catalogo e procedi con la pubblicazione. Per istruzioni specifiche, fai riferimento alla [Guida ai programmi di apprendimento](feature-summary/learning-programs.md).

### Creazione di cataloghi {#createcatalogs}

È possibile utilizzare i cataloghi in un’organizzazione per creare contenuti mirati o classificare i contenuti per un insieme definito di Allievi. In Learning Manager, un catalogo è una raccolta di oggetti di apprendimento quali corsi, certificazioni o programmi di apprendimento. Durante la creazione di cataloghi, puoi scegliere gli oggetti di apprendimento che desideri. Prima di creare i cataloghi, assicurati di aver già creato una serie di corsi, certificazioni o programmi di apprendimento. Puoi creare cataloghi personalizzati con un insieme di oggetti di apprendimento, qualora desiderassi assegnarli a gruppi di utenti interni o esterni. Per ulteriori informazioni sui cataloghi, fai riferimento alla [Guida ai cataloghi](feature-summary/catalogs.md).

### Attivazione notifiche e-mail/accesso agli utenti {#turnonemailnotificationsuseraccess}

In questa fase, puoi attivare le notifiche e-mail per gli utenti delle tue applicazioni e anche abilitare l&#39;accesso degli utenti.

## Fase 3 - Creazione dei corsi (Autore) {#phase3authoringcoursesauthor}

Gli sviluppatori di contenuti o gli autori dell’organizzazione possono iniziare a creare i contenuti di apprendimento. La creazione di moduli e corsi come base per tutti i contenuti di apprendimento nell’applicazione Learning Manager è obbligatoria.

### Creazione di moduli {#createmodules}

I moduli sono gli elementi fondamentali dell’applicazione Learning Manager. In qualità di Autore, inizia a creare i moduli per organizzare i contenuti di apprendimento. Learning Manager consente di scegliere uno qualsiasi dei quattro tipi di moduli del corso, ovvero classe, personalizzato, attività e classe virtuale. Per informazioni sul modulo del corso più adatto alle esigenze della tua organizzazione, fai riferimento alla [Guida ai moduli](../authors/how-to-choose-modules.md).

### Creazione di corsi {#createcourses}

Nell’applicazione Learning Manager, gli Amministratori possono assumere il ruolo di Autore e creare corsi. Nell’applicazione Learning Manager, un corso è un elemento fondamentale costituito da una serie di moduli che possono essere assegnati agli Allievi. Gli Allievi frequentano i corsi. Puoi iniziare a creare corsi scegliendo i moduli creati in precedenza, associando le competenze che desideri che gli Allievi acquisiscano durante il corso, associando livelli, crediti e distintivi a un corso, selezionando risorse formative, prerequisiti e risorse a tua scelta e pubblicando il corso. Inoltre, è possibile creare più istanze di un corso in modo da poterle assegnare a più Allievi in diversi fusi orari, pianificazioni e così via. Per ulteriori informazioni relative alla creazione di un corso, fai riferimento alla [Guida ai corsi](../authors/feature-summary/courses.md).

### Creazione di oggetti di apprendimento {#Createlearningobjects-1}

Questa è la fase logica in cui tutte e tre le fasi (fase 1, fase 2 e fase 3) convergono per consentirti di intraprendere le procedure successive.

A questo punto, una volta creati i moduli e i corsi, è possibile iniziare a creare oggetti di apprendimento di livello superiore, quali certificazioni, programmi di apprendimento o risorse formative per continuare. Prima di iniziare a creare oggetti di apprendimento, assicurati di aver già aggiunto alcuni utenti all’applicazione Learning Manager e di aver creato alcuni moduli e corsi.

#### Creazione di certificazioni {#Createcertifications-1}

La certificazione è una prova del completamento di un contenuto di apprendimento o un attestato di profitto per gli Allievi su base ricorrente o una tantum. Fornendo agli Allievi una certificazione a seguito del completamento del corso, è possibile ottenere un aumento delle iscrizioni ai contenuti di apprendimento. In qualità di Amministratore è possibile creare un programma di certificazione ospitato internamente o condotto da terze parti. Nella certificazione interna, definisci i corsi che un Allievo deve completare per essere certificato. Prima di creare la certificazione, assicurati di disporre di alcuni corsi nell’account. Per ulteriori informazioni relative alla creazione delle certificazioni, fai riferimento alla [Guida alla certificazione](feature-summary/certifications.md).

#### Creazione di risorse formative {#CreateJobaids-1}

Risorse formative è un archivio del contenuto di formazione accessibile agli Allievi senza alcun requisito di completamento o di iscrizione. Gli Allievi possono fare riferimento a queste risorse formative per ottenere assistenza relativa all’esecuzione di qualsiasi operazione o attività in un’organizzazione. Sebbene non sia obbligatorio utilizzare le risorse formative come parte della creazione del corso, il team Learning Manager consiglia, come buona prassi, di crearle. Per informazioni sulla creazione delle risorse formative, consultare la [Guida alle risorse formative](../authors/feature-summary/job-aids.md).

#### Creazione di programmi di apprendimento {#Createlearningprograms-1}

I programmi di apprendimento sono un set di corsi progettati specificatamente per soddisfare specifici obiettivi di apprendimento. Prima di creare programmi di apprendimento, assicurati di aver già creato alcuni corsi o di disporre di corsi esistenti nel tuo account.  Sebbene questa funzione sia facoltativa, il team di Learning Manager consiglia di utilizzarla per favorire un apprendimento mirato da parte dei dipendenti. Per iniziare a utilizzare i programmi di apprendimento, fai clic su Programmi di apprendimento nel riquadro di sinistra, seleziona un insieme di corsi dal catalogo e procedi con la pubblicazione. Per istruzioni specifiche, fai riferimento alla [Guida ai programmi di apprendimento](feature-summary/learning-programs.md).

## Fase 4 - Gestione del sistema LMS (Amministratore di Learning Manager) {#phase4managingyourlmscaptivateprimeadministrator}

### Annunci {#announcements}

Gli annunci sono utili all’organizzazione per divulgare in una sola volta tutte le informazioni importanti agli Allievi di un account. Nell’applicazione Learning Manager, un annuncio è un messaggio multimediale (testo, immagine o video) che un Amministratore può creare e trasmettere a un insieme definito di gruppi di utenti e oggetti di apprendimento. Puoi inviare annunci istantaneamente o pianificarli per attivarli automaticamente in una data specifica. Se desideri utilizzare questa funzione nell’applicazione Learning Manager, seleziona Annunci dal riquadro di sinistra e fai clic su Aggiungi per creare annunci. Per ulteriori informazioni, fai riferimento alla [Guida agli annunci](feature-summary/announcements.md).

### Iscrizione degli utenti {#userenrollment}

L’iscrizione degli utenti rappresenta un punto fondamentale per un’applicazione LMS. In questa fase, è possibile iniziare ad iscrivere gli Allievi a vari oggetti di apprendimento dell’applicazione Learning Manager. È possibile iscrivere gli Allievi manualmente o automaticamente utilizzando piani di apprendimento.

#### Iscrizione manuale {#manualenrollment}

* **Iscrizione autonoma -** Se attivi questa opzione durante la creazione di un oggetto di apprendimento, gli Allievi possono iscriversi direttamente agli oggetti di apprendimento.
* **Approvazione del Manager** - Se selezioni questa opzione nel tipo di iscrizione durante la creazione di un corso, gli Allievi risultano iscritti ai corsi solo in seguito all’approvazione dei Manager.
* **Nominato dal Manager** - Se scegli questo tipo di iscrizione durante la creazione di un corso, quest’ultimo deve essere nominato dai Manager.
* **Iscrizione tramite l’Amministratore**: in questo caso, l’Amministratore può iscrivere alcuni Allievi in base alle esigenze dell’organizzazione.

Per ulteriori informazioni, fai riferimento alla [Guida all’iscrizione degli utenti](feature-summary/courses.md).

Iscrivi manualmente gli Allievi agli oggetti di apprendimento utilizzando i quattro metodi indicati di seguito:

### Iscrizione automatizzata {#automatedenrollment}

Automatizza l’iscrizione degli Allievi agli oggetti di apprendimento, utilizzando piani di apprendimento.

#### Piani di apprendimento (in base alle attivazioni) {#learningplansbasedontriggers}

Puoi utilizzare piani di apprendimento per assegnare automaticamente corsi, programmi di apprendimento o certificazioni agli Allievi, in base all’occorrenza di determinati eventi. Ad esempio:

* Viene aggiunto un nuovo utente
* Un utente cambia il gruppo di utenti
* L’Allievo completa un oggetto di apprendimento
* L’utente completa un’abilità

Per ulteriori informazioni, fai riferimento alla [Guida ai piani di apprendimento](feature-summary/learning-plans.md).

### Creazione di report {#createreports}

In questa fase è possibile iniziare a creare e gestire diversi tipi di report.

Adobe Learning Manager consente di creare vari report per tracciare, monitorare e controllare le attività degli Allievi. Per generare i report, è possibile utilizzare i tre tipi di funzionalità di reporting seguenti:

* **Report dashboard**: crea report di riepilogo per ottenere informazioni utili sulla fruizione dei contenuti di apprendimento da parte degli Allievi in base a varie categorie, ad esempio gruppi di utenti, efficacia, tempo degli Allievi dedicato ai corsi e così via.
* **Trascrizioni Allievi** - Crea report incentrati sugli Allievi con la loro cronologia completa dal giorno della registrazione fino alla data.
* **Report corso** - Crea le statistiche di fruizione dei corsi da parte degli Allievi, a partire dai singoli corsi. Puoi anche creare report dei quiz a livello di corso.

Per ulteriori informazioni sul processo di generazione dei report, fai riferimento alla [Guida ai report](feature-summary/reports.md).

Per ulteriori informazioni in merito all’utilizzo delle funzionalità dell’applicazione Learning Manager, fai riferimento alla [Guida di Learning Manager](../topics.md) in base a ciascun ruolo.
