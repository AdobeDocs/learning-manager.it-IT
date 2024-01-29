---
description: Questo documento fornisce un approccio consigliato per le organizzazioni per configurare Adobe Learning Manager. Il team di Learning Manager suggerisce un approccio graduale per iniziare a utilizzare l’applicazione. Non è obbligatorio seguire tutte le fasi in una sequenza specifica.
jcr-language: en_us
title: Guida con le migliori procedure per configurare Learning Manager
contentowner: jayakarr
preview: true
source-git-commit: 46afb6603456ced9d7e2aaf98d07ec92fee30c0b
workflow-type: tm+mt
source-wordcount: '3387'
ht-degree: 0%

---



# Guida con le migliori procedure per configurare Learning Manager

Questo documento fornisce un approccio consigliato per le organizzazioni per configurare Adobe Learning Manager. Il team di Learning Manager suggerisce un approccio graduale per iniziare a utilizzare l’applicazione. Non è obbligatorio seguire tutte le fasi in una sequenza specifica.

Queste fasi possono essere eseguite da tre ruoli diversi, da uno o più utenti in base alla configurazione dell&#39;organizzazione. I tre ruoli sono i seguenti:

1. **Amministratore IT** - L’Amministratore IT svolge attività relative all’attivazione o all’integrazione associate all’applicazione Learning Manager all’interno di un’organizzazione. L’Amministratore IT può inoltre aggiungere uno o più utenti ed eseguire il ruolo di Amministratore di integrazione.
1. **Autore** - L’Autore crea i contenuti di apprendimento necessari per le esigenze dell’organizzazione. L’Autore dei contenuti di formazione o apprendimento dell’organizzazione può iniziare a creare i contenuti di base necessari per l’applicazione Learning Manager.
1. **Amministratore Learning Manager** - L’Amministratore dell’applicazione Learning Manager esegue le attività di configurazione. In alcune aziende, l’Amministratore IT può anche svolgere un ruolo di Amministratore dell’applicazione Learning Manager.

Puoi esaminare l’infografica fornita di seguito per ottenere una panoramica delle fasi e delle attività corrispondenti.

![](assets/learning-manager-getting-started.jpg)

In questa fase, partiamo dal presupposto che la tua organizzazione abbia già ricevuto il codice di licenza e che tu abbia attivato l’account Learning Manager. Come indicato nell’infografica, le tre tracce sono spiegate come segue:

## Fase 1 - Configurazione tecnica (Amministratore IT) {#phase1technicalsetupitadministrator}

Nel percorso 1, l’Amministratore IT della tua organizzazione può passare al ruolo di Amministratore dell’integrazione nell’applicazione Learning Manager ed eseguire alcune attivazioni e integrazioni nel modo seguente:

### Abilita/Aggiungi campi attivi (Amministratore Learning Manager) {#enableaddactivefieldscaptivateprimeadministrator}

Oltre ai campi attivi forniti dagli utenti durante la registrazione, l’Amministratore può aggiungere altri campi attivi. L’Amministratore può anche abilitare/disabilitare i campi utente. I valori per questi campi attivi vengono generati dai metadati di varie origini dati associate agli account utente. Fare riferimento a [Guida in linea dei campi attivi](feature-summary/add-users-user-groups.md#active-fields) per ulteriori informazioni.

### Single Sign-On (SSO) {#singlesignonsso}

Puoi accedere all’applicazione Learning Manager utilizzando Adobe ID o l’accesso unico. L’accesso unico è un meccanismo che consente a un utente di autenticarsi una volta sola e di accedere a più applicazioni più volte. Questa configurazione non è obbligatoria per l&#39;organizzazione. Se l’organizzazione dispone di un provider SSO basato su SAML 2.0, è possibile utilizzarlo per configurare l’applicazione Learning Manager. La configurazione è richiesta a livello di organizzazione e per l’applicazione Learning Manager. Se scegli di utilizzare SSO, contatta il supporto di Adobi per ricevere le istruzioni di configurazione. Fare riferimento a [Guida alle impostazioni](feature-summary/settings.md) per ulteriori informazioni.

### Importazione in blocco degli utenti {#bulkimportofusers}

Quando disponi di un elevato volume di utenti nell’organizzazione, puoi importare tutti gli utenti in blocco nell’applicazione Learning Manager utilizzando un file .CSV. Prima di eseguire questa operazione, ti consigliamo di esportare l’elenco degli utenti dall’applicazione HR dell’organizzazione in formato .CSV. Anche se in questa fase gli utenti non vengono importati in blocco, è possibile familiarizzare con il formato CSV. Per iniziare con il processo di importazione in Learning Manager, carichi il file .CSV e mappa i campi dei dati dell’applicazione con le colonne CSV dell’organizzazione. Fare riferimento a [Guida all’importazione in blocco](add-users-in-bulk.md) per ulteriori informazioni.

### Integrazione del connettore FTP {#ftpconnectorintegration}

In caso di aggiunta o rimozione continua dei dipendenti dell’organizzazione, puoi scegliere di automatizzare l’importazione in blocco degli utenti utilizzando il connettore FTP. Prima di stabilire una connessione, carica un CSV e mappa gli attributi del CSV con i campi Learning Manager corrispondenti. Puoi pianificare il processo di importazione automatica e sincronizzarlo quando e quando necessario. Fare riferimento a [Aiuto per il connettore FTP](../integration-admin/feature-summary/connectors.md#ftpconnector) per ulteriori informazioni.

### Integrazione del connettore Salesforce {#salesforceconnectorintegration}

Se disponi di un account Salesforce nella tua organizzazione, puoi automatizzare il processo di importazione di tutti gli utenti da Salesforce all’applicazione Learning Manager. Se desideri utilizzare questa funzione, puoi utilizzare il connettore Salesforce per integrare Learning Manager con l’account Salesforce e automatizzare la sincronizzazione dei dati. Utilizza la funzione di pianificazione automatica per eseguire regolarmente l’importazione automatica degli utenti. Puoi anche eseguire la sincronizzazione su base giornaliera. Fare riferimento a [Aiuto per il connettore Salesforce](../integration-admin/feature-summary/connectors.md#sfconnector) per ulteriori informazioni.

### Integrazione con Adobe Connect {#adobeconnectintegration}

Se utilizzi Adobe Connect nella tua organizzazione, puoi integrarlo con l’applicazione Adobe Learning Manager per offrire agli Allievi un’esperienza utente ottimale. L’integrazione consente agli Allievi di accedere alle classi virtuali direttamente nell’applicazione Learning Manager con un solo clic, senza dover accedere nuovamente ad Adobe Connect. Utilizzando questa funzione, gli Allievi possono anche seguire le sessioni di aula virtuale registrate all’interno dell’applicazione Learning Manager. Per integrare, integrare prima le impostazioni. Utilizzo **Impostazioni > Adobe Connect > Configura ora** per fornire l’URL di Connect e le credenziali di accesso e procedere con l’integrazione. Fare riferimento a [Guida all’integrazione Adobe Connect](feature-summary/adobeconnect-integration.md) per ulteriori informazioni.

### Registrazione all’app Salesforce {#salesforceappregistration}

I tuoi Allievi aziendali possono avere un’esperienza diretta di accesso all’app Learning Manager direttamente nei loro account Salesforce. Gli Allievi possono accedere ai contenuti di apprendimento assegnati come corsi, programmi di apprendimento e risorse formative dall’applicazione Salesforce. Gli utenti possono anche accedere alle notifiche e agli annunci dall’app Learning Manager all’interno di Salesforce. Per utilizzare questa funzionalità, è necessario registrare l’app in primo piano Salesforce nell’applicazione Learning Manager. Fare riferimento a [Guida dell’app Salesforce](../integration-admin/feature-summary/sfdc-app.md) per ulteriori informazioni sulle istruzioni di installazione e utilizzo.

## Fase 2 - Configurazione del sito (Amministratore Learning Manager) {#phase2siteconfigurationcaptivateprimeadministrator}

L’Amministratore dell’applicazione Learning Manager dell’organizzazione deve configurare alcune funzionalità prima di iniziare a implementarle per gli Allievi.

### Branding {#branding}

Un’organizzazione potrebbe voler visualizzare il logo aziendale nell’applicazione Learning Manager, avere un proprio dominio nell’URL, visualizzare il nome dell’organizzazione e visualizzare combinazioni di colori che corrispondano al marchio di un’organizzazione. Learning Manager consente alle organizzazioni di utilizzare tutte queste funzionalità. Per personalizzare le impostazioni e utilizzare il proprio marchio, fai clic sulla sezione Branding nel riquadro a sinistra. Fai clic su Modifica accanto a tutte queste opzioni e personalizza in base alle tue esigenze. Fare riferimento a [Guida al branding e ai temi](feature-summary/themes.md) per ulteriori informazioni.

### Aggiunta di utenti/gruppi di utenti {#addusersusergroups}

Poiché gli Allievi sono gli utenti principali dei contenuti di apprendimento, l’aggiunta di utenti nel sistema di gestione dell’apprendimento rappresenta il passaggio principale. Aggiungi gli utenti all’applicazione Learning Manager e assegna loro dei ruoli. È possibile aggiungere utenti nei modi seguenti:

#### Aggiunta di utenti (interni) {#addusersinternal}

* **Come singolo utente** - L’aggiunta di singoli utenti nell’applicazione Learning Manager consente di effettuare una prova con alcuni utenti prima di aggiungerli in blocco. Inoltre, questa opzione è utile quando si desidera aggiungere più utenti singoli in base alle esigenze, dopo l’importazione in blocco degli utenti.
* **Registrazione autonoma** - Questa opzione consente agli Amministratori di consentire ai dipendenti di registrarsi a Learning Manager.
* **Importazione in blocco** (mediante caricamento di file CSV): utilizzando questa opzione è possibile importare gli utenti in blocco nell’applicazione Learning Manager. Come prerequisito, è necessario preparare l’elenco degli utenti in formato CSV prima di utilizzare questa funzione.

#### Aggiunta di utenti (profili esterni) {#addusersexternalprofiles}

* Tramite l’iscrizione esterna: utilizzando questa opzione, è possibile iscrivere all’applicazione i membri esterni del reparto o i dipendenti esterni dell’organizzazione.

#### Aggiungere gruppi di utenti {#addusergroups}

L’applicazione Learning Manager genera gruppi di utenti predefiniti in base ad attributi simili. Oltre ai gruppi predefiniti, è possibile generare gruppi di utenti personalizzati in base a parametri quali il titolo e la posizione, in modo da poter utilizzare tali gruppi nella gamification e nei report, tra gli altri. Fare riferimento a [Guida all’aggiunta di utenti](feature-summary/add-users-user-groups.md) per ulteriori informazioni.

### Assegna ruoli {#assignroles}

Una volta aggiunti gli utenti a Learning Manager, l’Amministratore può iniziare ad assegnare agli utenti i ruoli Autore, Amministratore o Amministratore di integrazione in base ai requisiti dell’organizzazione. Per assegnare ruoli agli utenti, nell’accesso come Amministratore fai clic su **[!UICONTROL Utenti]**  nel riquadro a sinistra, seleziona la casella di controllo relativa a ciascun nome utente e fai clic su **[!UICONTROL Azioni]** per scegliere il ruolo che si desidera assegnare. I ruoli Manager vengono assegnati agli utenti dall’Adobe di Learning Manager in base ai ruoli/privilegi menzionati dall’organizzazione nel file CSV. Puoi anche modificare i ruoli di Manager assegnati agli utenti utilizzando il flusso di lavoro Modifica utenti. Fare riferimento a [Guida all’aggiunta di utenti](feature-summary/add-users-user-groups.md) per ulteriori informazioni.

### Modelli di notifica {#notificationtemplates}

Le notifiche possono essere utili per gli utenti di un sistema di gestione dell’apprendimento per conoscere il loro stato o per essere informati sugli eventi/attività. Durante la creazione dei corsi, la configurazione delle funzioni o l’utilizzo dei corsi, gli utenti affrontano diversi eventi che attivano le notifiche agli Allievi, ai loro Manager, Amministratori o Autori. Learning Manager fornisce vari modelli di notifica e-mail nell’applicazione. In qualità di Amministratore, puoi personalizzarli in base alle esigenze dell’organizzazione. Per creare notifiche e-mail, scegli **Modelli e-mail** nel riquadro a sinistra e fai clic sul nome del modello. Fare riferimento a [Guida ai modelli e-mail](feature-summary/email-templates.md) per ulteriori informazioni

**Disattiva le notifiche e-mail (consigliato)**

Per impostazione predefinita, le notifiche sono abilitate nell’applicazione Learning Manager. Se non desideri inviare una notifica ai dipendenti dell’organizzazione, puoi disattivare le notifiche in questa fase.

### Distintivi {#badges}

I distintivi sono unità di misura dei risultati raggiunti che gli allievi ottengono al completamento di un corso. I professionisti di tutto il mondo utilizzano questi distintivi per rappresentare un’abilità particolare o un risultato di apprendimento. È possibile creare una raccolta di distintivi in modo da poterli assegnare agli Allievi al termine dei contenuti di apprendimento. Per iniziare a creare i distintivi, fai clic **[!UICONTROL Distintivi]** nel riquadro sinistro. Fare riferimento a  [Aiuto per i distintivi](feature-summary/badges.md) per ulteriori informazioni.

### Feedback {#feedback}

Il feedback è uno dei fattori importanti di un LMS per misurare i progressi nell’apprendimento degli Allievi e garantire la qualità dei contenuti di apprendimento. Learning Manager offre agli utenti due tipi di opzioni di feedback.

* Il feedback L1 è il feedback fornito dagli Allievi dopo aver completato il corso.
* Il feedback L3 è il feedback fornito dagli Allievi agli Allievi in base all’impatto del corso sul comportamento degli Allievi e sulle attività quotidiane.

Questa funzione è facoltativa. Gli Amministratori possono personalizzare i modelli di feedback in base alle esigenze dell’organizzazione. Per utilizzare questa funzione, l’Amministratore deve abilitare le opzioni di feedback L1 e L3 a livello di istanza del corso. Per configurare il feedback, scegli un corso qualsiasi, fai clic su Impostazioni predefinite istanza nel riquadro a sinistra e abilita l’opzione di feedback. Fare riferimento a [Aiuto per il feedback](feature-summary/courses.md) per ulteriori informazioni.

### Gamification {#gamification}

Coinvolgere gli Allievi mentre fruiscono dei contenuti è una delle sfide affrontate dalle organizzazioni. La gamification aumenta la percentuale di completamento del corso coinvolgendo e motivando gli Allievi a raggiungere i propri obiettivi, con tecniche di gioco. Gli Allievi possono competere con i colleghi per guadagnare punti per varie attività di apprendimento e raggiungere livelli bronzo, argento, oro e platino. Gli amministratori possono abilitare/disabilitare ogni attività di gamification e modificare l’assegnazione dei punti alle attività. Learning Manager fornisce la funzionalità Gamification con alcune impostazioni predefinite. È possibile iniziare a utilizzare la funzione con le impostazioni predefinite per un certo periodo di tempo, quindi è possibile scegliere di personalizzarla. È possibile configurare o modificare le impostazioni per questa funzione. Se disponi di un esperto in materia nell’organizzazione, ti consigliamo di configurare le impostazioni prima di utilizzarla. Fare riferimento a [Guida alla gamification](feature-summary/gamification.md) per ulteriori informazioni.

### Creazione di oggetti di apprendimento {#createlearningobjects}

Questa è la fase logica in cui tutte e tre le tracce (traccia 1, traccia 2 e traccia 3) convergono per consentirti di intraprendere la prossima azione.

A questo punto, dopo aver creato moduli e corsi, puoi iniziare a creare oggetti di apprendimento di livello superiore, come certificazioni, programmi di apprendimento o risorse formative per continuare. Prima di iniziare a creare oggetti di apprendimento, assicurati di aver già aggiunto alcuni utenti all’applicazione Learning Manager e di aver creato alcuni moduli e corsi.

#### Creazione di certificazioni {#createcertifications}

La certificazione è la prova del completamento di un contenuto di apprendimento o un attestato di successo per gli Allievi su base ricorrente o una tantum. L’iscrizione degli Allievi ai contenuti di apprendimento può essere aumentata fornendo una certificazione agli Allievi dopo il completamento del corso. In qualità di Amministratore, puoi creare un programma di certificazione ospitato internamente o condotto da terzi. Nella certificazione interna, definisci i corsi che un Allievo deve completare per essere certificato. Prima di creare la certificazione, assicurati di disporre di alcuni corsi nell’account. Fare riferimento a  [Guida alla certificazione](feature-summary/certifications.md) per ulteriori informazioni su come creare certificazioni.

#### Creazione di risorse formative {#createjobaids}

Risorse formative è un archivio del contenuto di formazione accessibile agli Allievi senza alcun requisito di completamento o di iscrizione. Gli Allievi possono fare riferimento a queste risorse formative per ottenere assistenza relativa all’esecuzione di qualsiasi attività o attività in un’organizzazione. Anche se non è obbligatorio utilizzare le risorse formative come parte della creazione del corso, il team di Learning Manager consiglia di creare tali risorse come procedura consigliata per la tua organizzazione. Consultare la  [Guida alle risorse formative](../authors/feature-summary/job-aids.md) per informazioni su come creare risorse formative.

#### Creazione di programmi di apprendimento {#createlearningprograms}

I programmi di apprendimento sono un set di corsi progettati specificatamente per soddisfare specifici obiettivi di apprendimento. Prima di creare programmi di apprendimento, assicurati di aver già creato alcuni corsi o di disporre di corsi esistenti nel tuo account.  Sebbene questa funzione sia facoltativa, il team di Learning Manager consiglia di utilizzarla per favorire un apprendimento mirato da parte dei dipendenti. Per iniziare a utilizzare i programmi di apprendimento, fai clic su Programmi di apprendimento nel riquadro a sinistra, scegli un set di corsi dal catalogo e pubblicali. Consultare la [Guida ai programmi di apprendimento](feature-summary/learning-programs.md) per istruzioni specifiche.

### Creazione di cataloghi {#createcatalogs}

È possibile utilizzare i cataloghi in un’organizzazione per creare contenuti mirati o classificare i contenuti per un insieme definito di Allievi. In Learning Manager, un catalogo è una raccolta di oggetti di apprendimento quali corsi, certificazioni o programmi di apprendimento. Durante la creazione dei cataloghi, puoi scegliere gli oggetti di apprendimento che desideri. Prima di creare i cataloghi, assicurati di aver già creato un set di corsi, certificazioni o programmi di apprendimento. Puoi creare cataloghi personalizzati con un set di oggetti di apprendimento, se desideri assegnarli a gruppi di utenti interni o esterni. Consultare la  [Guida ai cataloghi](feature-summary/catalogs.md) per ulteriori informazioni sui cataloghi.

### Attiva notifiche e-mail/accesso utente {#turnonemailnotificationsuseraccess}

In questa fase, puoi attivare le notifiche e-mail per gli utenti delle tue applicazioni e anche abilitare l&#39;accesso degli utenti.

## Fase 3 - Creazione di corsi (Autore) {#phase3authoringcoursesauthor}

Gli sviluppatori di contenuti o gli autori dell’organizzazione possono iniziare a creare i contenuti di apprendimento. La creazione di moduli e corsi come base per tutti i contenuti di apprendimento nell’applicazione Learning Manager è obbligatoria.

### Creazione di moduli {#createmodules}

I moduli sono gli elementi fondamentali dell’applicazione Learning Manager. Per organizzare i contenuti di apprendimento, inizia a creare moduli come Autore. Learning Manager consente di scegliere uno qualsiasi dei quattro tipi di moduli del corso, ad esempio classe, ritmo personalizzato, attività e aula virtuale. Fare riferimento a  [Guida ai moduli](../authors/how-to-choose-modules.md) per conoscere il tipo di modulo del corso più adatto alle esigenze della tua organizzazione.

### Creazione di corsi {#createcourses}

Nell’applicazione Learning Manager gli Amministratori possono assumere il ruolo di Autore e creare corsi. Nell’applicazione Learning Manager, un corso è un’unità di base con una serie di moduli che possono essere assegnati all’Allievo. Gli Allievi frequentano i corsi. Puoi iniziare a creare corsi scegliendo i moduli creati in precedenza, associando le abilità che desideri che gli Allievi acquisiscano nel corso, associando livelli, crediti e distintivi a un corso, selezionando risorse formative, prerequisiti e risorse a tua scelta e pubblicando il corso. È inoltre possibile creare più istanze di un corso in modo da poterle assegnare a più Allievi in diversi fusi orari, pianificazioni e così via. Consultare la  [Guida ai corsi](../authors/feature-summary/courses.md)per ulteriori informazioni su come creare un corso.

### Creazione di oggetti di apprendimento {#Createlearningobjects-1}

Questa è la fase logica in cui tutte e tre le tracce (traccia 1, traccia 2 e traccia 3) convergono per consentirti di intraprendere la prossima azione.

A questo punto, dopo aver creato moduli e corsi, puoi iniziare a creare oggetti di apprendimento di livello superiore, come certificazioni, programmi di apprendimento o risorse formative per continuare. Prima di iniziare a creare oggetti di apprendimento, assicurati di aver già aggiunto alcuni utenti all’applicazione Learning Manager e di aver creato alcuni moduli e corsi.

#### Creazione di certificazioni {#Createcertifications-1}

La certificazione è la prova del completamento di un contenuto di apprendimento o un attestato di successo per gli Allievi su base ricorrente o una tantum. L’iscrizione degli Allievi ai contenuti di apprendimento può essere aumentata fornendo una certificazione agli Allievi dopo il completamento del corso. In qualità di Amministratore, puoi creare un programma di certificazione ospitato internamente o condotto da terzi. Nella certificazione interna, definisci i corsi che un Allievo deve completare per essere certificato. Prima di creare la certificazione, assicurati di disporre di alcuni corsi nell’account. Fare riferimento a  [Guida alla certificazione](feature-summary/certifications.md) per ulteriori informazioni su come creare certificazioni.

#### Creazione di risorse formative {#CreateJobaids-1}

Risorse formative è un archivio del contenuto di formazione accessibile agli Allievi senza alcun requisito di completamento o di iscrizione. Gli Allievi possono fare riferimento a queste risorse formative per ottenere assistenza relativa all’esecuzione di qualsiasi attività o attività in un’organizzazione. Anche se non è obbligatorio utilizzare le risorse formative come parte della creazione del corso, il team di Learning Manager consiglia di creare tali risorse come procedura consigliata per la tua organizzazione. Consultare la  [Guida alle risorse formative](../authors/feature-summary/job-aids.md) per informazioni su come creare risorse formative.

#### Creazione di programmi di apprendimento {#Createlearningprograms-1}

I programmi di apprendimento sono un set di corsi progettati specificatamente per soddisfare specifici obiettivi di apprendimento. Prima di creare programmi di apprendimento, assicurati di aver già creato alcuni corsi o di disporre di corsi esistenti nel tuo account.  Sebbene questa funzione sia facoltativa, il team di Learning Manager consiglia di utilizzarla per favorire un apprendimento mirato da parte dei dipendenti. Per iniziare a utilizzare i programmi di apprendimento, fai clic su Programmi di apprendimento nel riquadro a sinistra, scegli un set di corsi dal catalogo e pubblicali. Consultare la [Guida ai programmi di apprendimento](feature-summary/learning-programs.md) per istruzioni specifiche.

## Fase 4 - Gestione dell’LMS (Amministratore Learning Manager) {#phase4managingyourlmscaptivateprimeadministrator}

### Annunci {#announcements}

Gli annunci sono utili all’organizzazione per divulgare contemporaneamente tutte le informazioni importanti a tutti gli Allievi di un account. Nell’applicazione Learning Manager, un annuncio è un messaggio multimediale (testo, immagine o video) che un Amministratore può creare e trasmettere a un insieme definito di gruppi di utenti e oggetti di apprendimento. Puoi inviare annunci istantaneamente o pianificarli in modo che vengano attivati automaticamente in una data specifica. Se desideri utilizzare questa funzione nell’applicazione Learning Manager, scegli Annunci dal riquadro a sinistra e fai clic su Aggiungi per creare annunci. Fare riferimento a [Guida agli annunci](feature-summary/announcements.md) per ulteriori informazioni.

### Iscrizione utente {#userenrollment}

L’iscrizione degli utenti è un passaggio importante per un’applicazione LMS. In questa fase, puoi iniziare a iscrivere gli Allievi a vari oggetti di apprendimento dell’applicazione Learning Manager. È possibile iscrivere gli Allievi manualmente o automaticamente utilizzando piani di apprendimento.

#### Iscrizione manuale {#manualenrollment}

* **Iscrizione autonoma -** Se attivi questa opzione durante la creazione di un oggetto di apprendimento, gli allievi possono iscriversi direttamente agli oggetti di apprendimento.
* **Approvazione del manager** - Se selezioni questa opzione nel tipo di iscrizione durante la creazione di un corso, i Manager devono approvare l’iscrizione degli Allievi.
* **Nomina Manager** - Se scegli questo tipo di iscrizione durante la creazione di un corso, quest’ultimo deve essere nominato dai Manager.
* **Iscrizione amministratore** - In questo caso, l’Amministratore può iscrivere alcuni Allievi in base alle esigenze dell’organizzazione.

Fare riferimento a [Guida all’iscrizione degli utenti](feature-summary/courses.md)contenuti per ulteriori informazioni.

Iscrivi manualmente gli Allievi agli oggetti di apprendimento utilizzando i quattro modi seguenti:

### Iscrizione automatica {#automatedenrollment}

Automatizza l’iscrizione degli Allievi agli oggetti di apprendimento, utilizzando piani di apprendimento.

#### Piani di apprendimento (in base alle attivazioni) {#learningplansbasedontriggers}

Puoi utilizzare i piani di apprendimento per assegnare automaticamente corsi, programmi di apprendimento o certificazioni agli Allievi, in base all’occorrenza di determinati eventi. Ad esempio,

* Nuovo utente aggiunto
* L’utente cambia il gruppo di utenti
* L’Allievo completa un oggetto di apprendimento
* L’utente completa un’abilità

Fare riferimento a [Guida ai piani di apprendimento](feature-summary/learning-plans.md)  contenuti per ulteriori informazioni.

### Creazione di report {#createreports}

In questa fase è possibile iniziare a creare e gestire diversi tipi di report.

Adobe Learning Manager consente di creare vari report per tracciare, monitorare e controllare le attività degli Allievi. Per generare i report, è possibile utilizzare i tre tipi di funzionalità di reporting seguenti:

* **Dashboard dei report** - Creazione di report di riepilogo per ottenere informazioni utili sulla fruizione dei contenuti di apprendimento da parte degli Allievi in base a varie categorie, ad esempio gruppi di utenti, efficacia, tempo degli Allievi dedicato ai corsi e così via.
* **Trascrizioni Allievi** - Creazione di report incentrati sugli Allievi con la loro cronologia completa dal giorno della registrazione fino alla data.
* **Report corso** - Creare le statistiche di fruizione dei corsi da parte degli Allievi, a partire dai singoli corsi. Puoi anche creare report dei quiz a livello di corso.

Fare riferimento a  [Guida ai report](feature-summary/reports.md) per ulteriori informazioni sul processo di generazione dei report.

Per ulteriori informazioni in merito all’utilizzo delle funzionalità dell’applicazione Learning Manager, consulta [Guida di Learning Manager](../topics.md) in base a ciascun ruolo.
