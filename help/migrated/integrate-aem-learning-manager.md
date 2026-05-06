---
jcr-language: en_us
title: Integrazione di Adobe Learning Manager con AEM
description: Learning Manager è un sistema di gestione dell’apprendimento con un sistema di gestione dei contenuti di apprendimento integrato. Gli utenti gestiscono i propri contenuti di apprendimento caricandoli su Learning Manager, in modo che Learning Manager esegua il controllo delle versioni, l’assegnazione ai corsi, la definizione della visibilità agli Allievi, il monitoraggio della frequenza e la segnalazione agli amministratori.
contentowner: saghosh
exl-id: 61fae7bd-1703-4ed1-9bd9-07387d67a91c
source-git-commit: e4fbde07314dcb99ee2d16aa4977308b8ab5b990
workflow-type: tm+mt
source-wordcount: '3817'
ht-degree: 45%

---


# Integrazione di Adobe Learning Manager con AEM

Adobe Learning Manager (ALM) viene integrato con Adobe Experience Manager (AEM) Sites. In questo modo, potrai creare il tuo sito Web e interfacce per dispositivi mobili reattive per Adobe Learning Manager con il minimo sforzo di codifica. Grazie a questa integrazione, puoi creare esperienze di apprendimento personalizzate per i tuoi utenti.

Per creare un&#39;esperienza di questo tipo, ALM fornisce un pacchetto per il sito di riferimento di Adobe Learning Manager (pacchetto per il sito di riferimento ALM) per AEM Sites sotto forma di file ZIP, che è possibile installare nell&#39;istanza di AEM Sites.

Il pacchetto include i modelli di pagine Web e i componenti dei siti Web di AEM Sites, nonché i widget incorporabili. Ad esempio, Catalogo di apprendimento, Calendario, Conformità, Categorie, Corsi e Percorsi e così via.

Dopo aver installato il pacchetto per il sito di riferimento ALM, puoi iniziare a creare un sito Web per Adobe Learning Manager che puoi ospitare sulla tua istanza di AEM Sites. Gli utenti possono quindi trascinare e rilasciare i componenti sul sito Web.

>[!IMPORTANT]
>
>I pacchetti Adobe Learning Manager (ALM) per AEM Sites forniscono un blocco di codice di avvio rapido per l&#39;implementazione. Questo pacchetto è progettato per le distribuzioni headless. All&#39;atto dell&#39;attuazione del codebase fornito, la manutenzione e l&#39;ulteriore sviluppo continui sono di competenza della parte attuatrice, come avviene di norma con le applicazioni headless basate su Adobe Learning Manager.

## Installazione del pacchetto per il sito di riferimento ALM

### Prerequisiti

* Licenze per AEM Sites e Adobe Commerce.
* AEM locale 6.5 o Adobe Experience Manager - Cloud Service
* Adobe Commerce 2.4.3

Dopo aver protetto l&#39;ambiente di AEM Sites, è necessario installare il pacchetto per il sito di riferimento ALM. Questo pacchetto include pagine Web e componenti dei siti Web AEM che consentono di creare la piattaforma di apprendimento.

Il pacchetto del sito di riferimento è ospitato nel [**repository GitHub**](https://github.com/adobe/adobe-learning-manager-reference-site/releases).

Per ulteriori informazioni, consulta il README.

## Download del pacchetto dei contenuti {#downloadthecontentpackage}

Il programma di installazione viene fornito come pacchetto di contenuti AEM. [***Scarica il pacchetto***](https://github.com/adobe/adobe-learning-manager-reference-site).

Il pacchetto dei contenuti è disponibile come file zip ed è compatibile con AEM 6.4 e AEM 6.5.

## Installazione del pacchetto Learning Manager {#installcaptivateprimecomponent}

Installa il pacchetto dei contenuti Learning Manager utilizzando il gestore pacchetti AEM:

>[!NOTE]
>
>Per informazioni sull&#39;installazione dei pacchetti, vedere [***Come utilizzare i pacchetti***](https://experienceleague.adobe.com/docs/experience-manager-65/administering/contentmanagement/package-manager.html?lang=en#how-to-work-with-packages).

1. Come Autore AEM, apri il gestore pacchetti AEM.
1. Fai clic sul pulsante **[!UICONTROL Carica pacchetto]**.
1. Fai clic su **[!UICONTROL Sfoglia]** e carica il pacchetto di contenuti.
1. Fai clic su **[!UICONTROL Carica]**.
1. Dopo aver caricato il pacchetto, installalo selezionandolo e facendo clic su **[!UICONTROL Installa]**.

   ![](assets/install-package.jpg)

   *Installare il pacchetto dei contenuti*

## Crea un&#39;applicazione in [!DNL Adobe Learning Manager]

Dopo aver installato il pacchetto per il sito di riferimento AEM, è necessario configurare un’applicazione ALM per connettere il portale di apprendimento con il sito AEM.

Questo scenario è applicabile quando l&#39;AEM viene utilizzato con [!DNL Adobe Learning Manager].

Effettua le seguenti operazioni:

1. Come Amministratore di integrazione, fai clic su **[!UICONTROL Applicazioni]**.
1. Per creare una nuova applicazione, fai clic su **[!UICONTROL Registra]** nell’angolo superiore destro della pagina.
1. Nella finestra Registra una nuova applicazione, inserisci i seguenti dettagli:

   1. **Nome applicazione:** Il nome dell&#39;applicazione che si sta creando.
   1. **URL:** URL dell&#39;organizzazione.
   1. **Domini di reindirizzamento:** I domini di hosting del sito Web dell&#39;AEM. Puoi anche specificare i caratteri jolly.
   1. **Descrizione:** Descrizione dell&#39;applicazione.
   1. **Ambiti:** Selezionare l&#39;accesso in lettura al ruolo Allievo e l&#39;accesso in scrittura al ruolo Allievo.
   1. **Solo per questo account?:** Selezionare Sì se si desidera utilizzare l&#39;applicazione per l&#39;account ALM esistente.

1. Dopo aver apportato le modifiche, fai clic su **Salva**.

Annota le credenziali dell&#39;applicazione dalla schermata.

![](assets/application-credentials.png)
*Credenziali dell&#39;applicazione*

Per approvare l’applicazione, fai clic su **[!UICONTROL Approva]**.

## Ottenere i token

1. Nella scheda Risorse sviluppatore, fai clic su **[!UICONTROL Token di accesso per test e sviluppo]**.

   ![](assets/access-tokens.png)

   *Selezionare token di accesso per test e sviluppo*

1. Immetti i seguenti dettagli:

   ![](assets/access-token-details.png)
   *Immettere i dettagli del token*

   1. **Ottieni codice OAuth:** Immetti l&#39;ID client della sezione precedente e modifica l&#39;ambito. Fai clic su Invia per ottenere il codice Oauth.
   1. **Ottieni token di aggiornamento:** Immetti l&#39;ID client e il segreto della sezione precedente. Immetti inoltre il codice OAuth ottenuto dal passaggio precedente. Fai clic su **Invia**.
   1. **Ottieni token di accesso:** Immetti l&#39;ID client e il segreto della sezione precedente. Immetti inoltre il token di aggiornamento ottenuto dal passaggio precedente. Fai clic su **Invia**.
   1. **Ottieni dettagli token di accesso:** Immetti il token di accesso ottenuto dal passaggio precedente. Fai clic su **Invia**.

1. Puoi ottenere i dettagli dalla risposta JSON che segue. La risposta include token di accesso, token di aggiornamento, ruolo dell’utente, ID account, ID utente e tempo rimanente prima della scadenza. Prendi nota del token di aggiornamento, perché verrà riutilizzato.

## Configurazione dell’account ALM in AEM

1. Avvia l’istanza AEM.
1. Fai clic su **Impostazioni** > **Cloud Service**.
1. Fai clic su **Configurazione di Adobe Learning Manager**.

   ![](assets/alm-configuration.png)
   *Selezionare la configurazione di Adobe Learning Manager*

1. Fai clic su **Crea** > **Cartella di configurazione**. Assegna un nome alla cartella.

   ![](assets/create-folder.png)
   *Crea configurazione*

1. Nel progetto di apprendimento, seleziona la configurazione creata.

1. Immetti i dettagli della configurazione.

   ![](assets/account-congiguration.png)
   *Crea cartella di configurazione*

   1. **Modalità Adobe Learning Manager:** scegli come vuoi che sia l’esperienza di apprendimento per gli Allievi che hanno effettuato l’accesso e per quelli che non l’hanno fatto.
   2. **URL Adobe Learning Manager:** Immettere l&#39;URL dell&#39;istanza ALM in cui sono ospitati i servizi di apprendimento.
   3. **ID account:** ID dell&#39;account ALM.
   4. **ID client, segreto client e token di aggiornamento autore:** Immettere le credenziali ottenute durante la creazione dell&#39;applicazione in ALM.
   5. **Personalizzazione del widget:** Per ulteriori informazioni, vedere [Integrazione con AEM](/help/migrated/integrate-aem-learning-manager.md) `.`

1. Salva e chiudi la configurazione.

### AEM + Adobe Learning Manager (utenti connessi/non connessi)

Adobe Learning Manager ora ti consente di presentare i tuoi prodotti e corsi di formazione ai clienti e ai partner esistenti e potenziali senza dover creare account o effettuare l’accesso. Questa funzionalità ti aiuterà a promuovere l’adozione di prodotti e corsi di formazione fornendo agli Allievi un’anteprima rapida e semplice dei corsi di formazione, che consente di evidenziare e promuovere le funzionalità del prodotto. Potrai quindi presentare i tuoi prodotti e le tue offerte con efficacia, in particolare ai potenziali clienti e partner, aumentando la consapevolezza del prodotto. La facilità di accesso e una migliore raggiungibilità producono un maggiore interesse, che contribuisce a stimolare le iscrizioni ai corsi di formazione e l’adozione della soluzione di apprendimento.

Utilizzando questo flusso di lavoro, un Allievo può visualizzare in anteprima un corso di formazione, accedere alle informazioni del corso o cercare un corso di formazione senza accedere ad Adobe Learning Manager. Questo flusso di lavoro non è applicabile all’interfaccia di Learning Manager nativa (applicabile SOLO per AEM Sites e altre interfacce headless).

**Configurare e attivare il connettore della piattaforma di apprendimento**

Questa sezione sottolinea i passaggi necessari per configurare e attivare il seguente connettore:

**Accesso ai dati di formazione**

Questo connettore consente all’interfaccia utente basata su AEM Sites o a un’altra interfaccia utente headless personalizzata di recuperare ed eseguire il rendering delle informazioni sul corso di formazione per gli Allievi e realizzare una ricerca uniforme delle informazioni del corso prima o dopo l’accesso di un Allievo.

Questo connettore è richiesto solo se si utilizzano interfacce basate su AEM Sites o altre interfacce headless.

Il connettore esporta i metadati del corso di formazione in una soluzione di archiviazione e recupero dati, oltre a un sistema di ricerca. Di conseguenza, puoi configurare la tua interfaccia utente basata su AEM Sites o un’altra interfaccia headless personalizzata per utilizzare questi due servizi per recuperare i dati del corso di formazione, eseguire il rendering delle pagine Web e fornire agli Allievi funzionalità di ricerca ottimizzate per la formazione. Ad esempio, un’interfaccia basata su AEM Sites non registrata può utilizzare i metadati esportati per consentire agli Allievi di cercare, sfogliare e accedere alle pagine del corso di formazione che mostrano informazioni sul corso di formazione.

Abilita questo connettore per creare ed eseguire il rendering delle pagine Web basate su AEM Sites e distribuire esperienze personalizzate agli Allievi sia prima che dopo l’accesso. Abilita questo connettore per creare ed eseguire il rendering delle pagine Web basate su AEM Sites e distribuire esperienze personalizzate agli Allievi sia prima che dopo l’accesso.

* **URL di base CDN di Adobe Learning Manager:** Immettere l&#39;URL di base del percorso del servizio CDN per il recupero dei dati dalla pagina di connessione Accesso ai dati della formazione.
* **Token di aggiornamento amministratore:** Immettere il token di aggiornamento determinato nella sezione precedente.
* **URL di base metadati di formazione:** Immettere l&#39;URL di base del percorso del servizio di ricerca e recupero dati dalla pagina di connessione Accesso ai dati di formazione.
* **URL registro Adobe Learning Manager:** Immettere l&#39;URL di registrazione automatica generato dall&#39;amministratore di integrazione per l&#39;account, utilizzato dagli Allievi per iscriversi al corso di formazione.

### AEM + Adobe Learning Manager + Adobe Commerce (utenti connessi/non connessi)

Adobe Learning Manager ora offre soluzioni che consentono di integrare perfettamente la piattaforma di apprendimento con Adobe Commerce. Questa versione ti consentirà di collegare facilmente ad Adobe Commerce le tue interfacce di Learning Manager native, basate su AEM Sites o altre interfacce headless. Questa integrazione ti consente di sfruttare le funzionalità di e-commerce all&#39;interno della piattaforma di apprendimento. Ora puoi offrire corsi di formazione a pagamento ai tuoi clienti e partner commerciali e agevolare gli acquisti di corsi di formazione su interfacce di Learning Manager native e non. Un Allievo può anche visualizzare in anteprima un corso di formazione, accedere alle informazioni del corso o cercare un corso di formazione senza accedere ad Adobe Learning Manager.

Invece di crearne una, l’utente può utilizzare l’applicazione AEM esistente e approvarla.

* **URL di base CDN di Adobe Learning Manager:** Immettere l&#39;URL di base del percorso del servizio CDN per il recupero dei dati dalla pagina di connessione Adobe Commerce.
* **URL Adobe Commerce:** Immettere l&#39;URL dell&#39;istanza Adobe Commerce in uso.
* **Percorso proxy GraphQL:** i componenti di Learning Manager lato client accedono direttamente all&#39;endpoint Adobe Commerce GraphQL e, pertanto, potrebbe verificarsi un errore CORS. Per evitare questo errore, tutte le chiamate devono essere effettuate dallo stesso endpoint dell’AEM o tramite un proxy che aggiunge le intestazioni CORS.
* **Nome archivio Adobe Commerce:** Immettere il nome dell&#39;archivio Adobe Commerce determinato nella sezione precedente.
* **Durata del token cliente Adobe Commerce (in sec):** Immettere la durata del token cliente che indica il periodo predeterminato per una sessione di accesso.
* **Token di aggiornamento amministratore:** Immettere il token di aggiornamento determinato nella sezione precedente.

## Personalizzazione delle pagine Web

Personalizza le tue pagine Web utilizzando il sito di riferimento AEM e i widget disponibili.

1. Avvia l’istanza AEM.
1. Fai clic su **Siti** e apri la pagina di configurazione.
1. Fai clic su **[!UICONTROL Sito di apprendimento]** > **[!UICONTROL Lingua principale]** > **[!UICONTROL Inglese]**. Tutte le pagine Web del progetto sono incluse nella cartella.

   ![](assets/list-webpages.png)
   *Visualizza tutte le pagine Web*

1. Seleziona un modello e fai clic su **[!UICONTROL Modifica]**.

1. Nella pagina, fai clic sul pulsante delle impostazioni relative al componente e modifica le proprietà del componente.

   ![](assets/settings-button.png)
   *Pulsante Seleziona impostazioni*

1. Puoi visualizzare in anteprima le modifiche o pubblicare la pagina.

## Creazione delle pagine Web

Oltre ai modelli che puoi utilizzare forniti dal pacchetto per il sito di riferimento, puoi anche creare pagine Web basate sui modelli in AEM.

1. Nella pagina principale AEM, fai clic su **Crea** > **Pagina**.

2. Scegli il modello da personalizzare. Fai clic su **Avanti**.

3. Immettere le proprietà della pagina.

   ![](assets/page-properties.png)
   *Proprietà pagina*

4. Per creare la pagina, fai clic su **[!UICONTROL Crea]**.

5. Seleziona la nuova pagina e fai clic su **[!UICONTROL Modifica]**.

6. Aggiungi un componente alla pagina. Ad esempio, **Widget Adobe Learning Manager**.

   ![](assets/learning-content.png)
   *Filtra per sito*

7. Trascina il **widget Adobe Learning Manager** nella pagina in cui desideri che risieda.
8. Selezionate l&#39;icona delle impostazioni. Viene visualizzata la finestra a comparsa **Proprietà**.
9. Seleziona un widget dal menu a discesa, immetti un titolo e una descrizione, quindi seleziona **Fine**. Il widget selezionato viene quindi aggiunto alla pagina.

## Widget di Adobe Learning Manager

Il widget Adobe Learning Manager è disponibile nella versione 2.0.0 e successive nel gruppo di componenti **Apprendimento - Contenuti**. Un singolo componente ospita tutti i widget della pagina principale di ALM, selezionabili da un menu a discesa nella finestra di dialogo di creazione.

Con l’aggiunta del nuovo **widget Adobe Learning Manager**, puoi creare esperienze su AEM Sites che sono in parità con le pagine Adobe Learning Manager native: Home, Catalogo, Panoramica oggetto di apprendimento e pagine personalizzate create con widget come Categorie e Corsi e Percorsi.

**Widget disponibili:**

* **Il mio apprendimento** — Allievi attualmente iscritti
* **Classifica** — classifica dei punti di gamification
* **Calendario**: sessioni imminenti e completate, organizzate per mese
* **Conformità**: corsi con scadenze passate o imminenti
* **Apprendimento sociale** — post in Apprendimento sociale
* **Categorie**: schede per cataloghi, prodotti o ruoli
* **Corsi e percorsi**: elenchi selezionati, basati sull&#39;origine o selezionati personalmente
* **Segnalibri**: corsi salvati dell’Allievo
* **Admin Recommendations**: contenuto impostato dagli amministratori
* **Aree di interesse, tendenza e individuazione Recommendations**, in base alle impostazioni consigliate a livello di account

### Funzionalità di authoring

* Cataloghi, prodotti, ruoli e corsi sono selezionabili dai menu a discesa ricercabili all’interno della finestra di dialogo.
* I campi di selezione multipla supportano fino a 25 elementi con visualizzazione basata su tag e trascinamento per riordinarli.
* La terminologia a livello di account (ad esempio, nomi personalizzati per **Catalogo** o **Ruolo**) viene riflessa automaticamente nelle etichette delle finestre di dialogo.

### Personalizzazione del riquadro del corso

Le personalizzazioni dei riquadri del corso apportate nell’app di amministrazione ALM, in **Amministratore** > **Branding** > **Riquadro del corso**, si applicano a ogni widget che esegue il rendering dei riquadri per corsi, percorsi di apprendimento, certificazioni e risorse formative. Utilizza questa opzione per controllare quali dettagli (formato, durata, abilità, valutazione, nome dell’autore, descrizione, stato di completamento e altro ancora) vengono mostrati agli Allievi nei nuovi widget con un’unica configurazione che si propaga ovunque nella tua Accademia di apprendimento basata su AEM Sites.

Per personalizzare il widget Adobe Learning Manager, vedere [Integrazione con AEM](/help/migrated/integrate-aem-learning-manager.md).


## Creazione di un sito da Blueprint

Il pacchetto per il sito di riferimento ALM fornisce un &quot;Learning Site Blueprint&quot;, che consente di creare un sito Web per la piattaforma di apprendimento. I blueprint di AEM consentono di creare pagine Web direttamente dai componenti di AEM Sites. Non è necessario utilizzare alcun modello.

1. Nella pagina iniziale AEM, fai clic su **[!UICONTROL Siti]**.

1. Fai clic su **[!UICONTROL Crea]** > **[!UICONTROL Sito]**.

1. Fai clic su **Learning Site Blueprint**.

   ![](assets/learning-site-blueprint.png)

   *Crea sito dal modello*

1. Fai clic su **Avanti**.

1. Nella pagina delle proprietà, inserisci i metadati della pagina. Fai clic su **Crea**.

   ![](assets/blueprint-properties.png)
   *Seleziona progetto del sito di apprendimento*

1. Fai clic sul collegamento ipertestuale **Home** per accedere alla home page del sito creato. In questa pagina puoi personalizzare i widget e i componenti del catalogo.

## Codifica del sito Web

Oltre a utilizzare i modelli incorporati e creare il sito Web da zero tramite i componenti WYSIWYG, puoi anche scrivere codice e creare il sito.

Il codice si trova nel [Repository GitHub del sito di riferimento](https://github.com/adobe/adobe-learning-manager-reference-site).

Le parti principali del modello sono:

* Pacchetto Java `core:` contenente tutte le funzionalità di base quali servizi OSGi, listener o scheduler, nonché codice Java relativo ai componenti come servlet o filtri di richiesta.
* `ui.apps:` contiene le parti /apps (e /etc) del progetto, ad esempio clientlib JS&amp;CSS, componenti e modelli.
* `ui.content:` contiene contenuto di esempio utilizzando i componenti di ui.apps
* `ui.frontend:` contiene componenti React.

### Personalizzazione dei widget Adobe Learning Manager mediante il codice

Il componente **Adobe Learning Manager Widget** esegue il rendering direttamente nel DOM della pagina utilizzando i componenti React.

**Quali sono le implicazioni per il tuo progetto?**

* Il markup del widget, gli stili e l’origine React fanno parte del pacchetto AEM e sono accessibili al progetto
* Sostituisci CSS utilizzando la tua libreria client senza toccare il pacchetto
* Per le modifiche comportamentali, i pulsanti di rietichettatura, la logica condizionale e la personalizzazione dell&#39;output del componente, modifica l&#39;origine React nel modulo ui.frontend e rigenera

### Classi CSS predefinite per i widget

Le seguenti classi CSS predefinite sono disponibili come destinazioni per lo stile a livello di widget:

| Nome widget | CSS contenitore |
|------------|---------------|
| Calendario | `alm-calendar-widget-container` |
| Categoria | `alm-category-widget-container` |
| Schede categoria | `alm-category-card-container` |
| Conformità | `alm-compliance-container` |
| Corso e percorsi | `alm-course-path-widget-container` |
| Schede LO per corsi e percorsi | `alm-training-card-v2-card` |
| Recommendations (tutto) | `alm-course-path-widget-container` |
| Gamification | `alm-leaderboard-container` |
| Apprendimento sociale | `alm-social-learning-container` |

Tutto il codice è a tua disposizione nel repository.

## Importazione e aggiunta di componenti di Learning Manager in pagine Web o modelli esistenti

L’installazione del pacchetto per il sito di riferimento AEM aggiunge i componenti di Learning Manager all’istanza di AEM Sites. Per impostazione predefinita, puoi aggiungere questi componenti al sito di apprendimento del progetto Web (sito Web) fornito da Adobe. Questi componenti sono disponibili anche nel sito Web che hai creato da Learning Site Blueprint.

Tuttavia, se desideri utilizzare questi componenti di Learning Manager appena aggiunti al tuo progetto Web o sito Web esistente, devi importarli utilizzando la procedura seguente.

1. Installa il pacchetto per il sito di riferimento ALM.

1. Apri il progetto Web e accedi al file HTML (per la pagina Web o il modello Web in cui desideri aggiungere i componenti di Learning Manager).
1. Apri il file HTML e aggiungi al componente di pagina i seguenti frammenti di codice in modo che il codice venga eseguito prima dei componenti di apprendimento presenti nel rendering della pagina.

   *`<sly data-sly-use.configModel="com.adobe.learning.core.models.GlobalConfigurationModel"/>`*
   *`<meta name="cp-config" content="${configModel.config}" />`*

   Il codice precedente aggiunge la configurazione mappata nel meta tag della pagina, necessaria per il rendering dei componenti di apprendimento. Per ulteriori dettagli, consulta [Sito di riferimento di Adobe Learning Manager](https://github.com/adobe/adobe-learning-manager-reference-site/blob/master/ui.apps/src/main/content/jcr_root/apps/learning/components/page/customheaderlibs.html).

1. Assicurati di aver mappato la configurazione con il progetto Web.
1. Apri il modello **AEM Sites** in cui desideri importare i componenti di Learning Manager.
1. Nell&#39;editor della pagina del modello, accedi al contenitore **Componenti consentiti** e seleziona **Criteri**.
1. Nella pagina **Criteri**, seleziona **Proprietà** > **Componenti consentiti** e seleziona i seguenti componenti: &quot;**Apprendimento - Contenuto,**&quot; &quot;**Apprendimento - Modulo**&quot; e &quot;**Apprendimento - Struttura**&quot;

La procedura seguente consente al modello di soddisfare le dipendenze della libreria client dei componenti Learning Manager importati.

Le pagine Web che includono questi componenti devono caricare queste librerie per eseguire correttamente il rendering e utilizzare i componenti.

1. Nell&#39;editor della pagina del modello fare clic su **Informazioni pagina** e quindi su **Criteri pagina**.
1. Nella pagina **Criteri**, seleziona **Proprietà** > **Librerie client** e aggiungi questi elementi alla pagina del modello:

   1. learning.site
   1. learning.ui
   1. learning.commerce

Dopo aver salvato questo modello, puoi aggiungere i componenti di Learning Manager in tutte le pagine Web derivate da questo modello.

## Configurazione del widget in AEM {#configurethewidgetinaem}

Per la configurazione del widget, l’autore AEM richiede solo il token di aggiornamento fornito dall’Amministratore dell’integrazione Learning Manager.

Puoi anche impostare più configurazioni di account in più pagine.

1. Fai clic su **[!UICONTROL Strumenti]** > **[!UICONTROL Cloud Service]** > **[!UICONTROL Configurazione widget Learning Manager]**.
1. Fai clic su **[!UICONTROL Crea]**.
1. Immetti qui il token di aggiornamento. Configura altre impostazioni.
1. Il nome host deve essere modificato in **learningmanagereu** per le aree dell’UE.
1. Salva e chiudi la configurazione.
1. Seleziona una configurazione e pubblicala.

## Autore AEM {#aemauthor}

L’autore AEM deve prima aggiungere il componente nel modello AEM

L’autore AEM potrà quindi trascinare e rilasciare il componente Adobe Learning Manager e configurarlo di conseguenza.

Il componente Learning Manager richiede il mapping della configurazione creata nel passaggio precedente alla **pagina**.  L&#39;autore può mappare la configurazione modificando le proprietà della pagina in **[!UICONTROL Avanzate]** > **[!UICONTROL Configurazione]** > **[!UICONTROL Configurazione cloud]** e fornire il percorso di configurazione. In questo modo, l’Autore può creare configurazioni per più account Learning Manager e mappare ciascuna di esse su diverse pagine del sito. Se una configurazione non è collegata alla pagina, il componente leggerà ricorrentemente la configurazione dalla pagina padre fino a quando non ne trova una.

## Allievo {#learner}

L’Allievo può seguire i corsi direttamente dalla pagina.

Per poter accedere al widget Learning Manager, l’Allievo deve effettuare il login come utente AEM. Inoltre, la proprietà **email** deve essere presente nel nodo &quot;/profile&quot; del nodo rep:User dell’Allievo. Questa e-mail deve essere esattamente uguale a quella presente nell’account Learning Manager.

L’Allievo può seguire i corsi direttamente dalla pagina.

Anche l’avanzamento del corso viene salvato.

Vengono forniti i seguenti widget:

1. Gamification
1. Calendario apprendimento
1. Widget social
1. Widget Catalogo
1. Il mio apprendimento
1. Consiglio basato sull’apprendimento tra utenti dello stesso livello
1. Consigli dell’Amministratore
1. Consiglio basato sugli interessi degli Allievi

In caso di mancanza di consigli, il widget sarà vuoto.

## Supporto per Skyline

Skyline è la versione cloud di AEM. È necessario prima installare Skyline dal gestore pacchetti. Per utilizzare il componente Skyline in AEM, un utente deve essere presente nell’account Learning Manager. In altre parole, l’indirizzo e-mail dell’utente deve esistere nell’account.

### Implementa Skyline

La procedura per configurare Skyline è indicata nel [repository GitHub](https://github.com/adobe/captivate-prime-aem-components).

## Il mio widget di apprendimento

Il widget **[!UICONTROL Il mio apprendimento]** consente di visualizzare i corsi di formazione da un catalogo specifico o da un set di cataloghi a un utente.

Nella sezione **[!UICONTROL Proprietà]** delle proprietà della pagina, seleziona **[!UICONTROL Catalogo]** dalle opzioni elencate.

<!--![](assets/catalog-widget.png)-->

Le opzioni del catalogo contengono le seguenti opzioni:

* **[!UICONTROL ID catalogo]:** ID catalogo separati da virgole per i quali è necessario visualizzare i corsi di formazione.
* **[!UICONTROL Ordinamento]:** Ordinamento per il corso di formazione. Di seguito sono riportate le opzioni di ordinamento:
   * name: ordina gli oggetti di apprendimento in ordine alfabetico dalla A alla Z.
   * -name: ordina gli oggetti di apprendimento alfabeticamente da Z ad A.
   * data: ordina per data in ordine crescente.
   * -date: ordina per data in ordine decrescente (la prima più recente).
   * dateCreated: ordina in base alla data di creazione dell’oggetto di apprendimento (prima il meno recente).
   * -dateCreated: ordina in base alla data di creazione (prima la più recente).
   * dateEnrolled: ordina in base alla data di iscrizione dell’Allievo (prima).
   * -dateEnrolled: ordina in base alla data di iscrizione (la prima più recente).
   * valutazione: ordina in base alle valutazioni dell’Allievo (dalla più bassa alla più alta).
   * -rating: ordina in base alle valutazioni (dal più alto al più basso).
   * dueDate: ordina in base alla data di scadenza del corso (prima scadenza).
   * efficacia: ordina in base ai punteggi di efficacia in base al feedback degli allievi.
   * avanzamento: ordina in base all’avanzamento dell’Allievo (avanzamento minimo fino alla maggior parte).
* **[!UICONTROL Stato dell’Allievo]:** restituisce tutti i corsi di formazione che utilizzano i seguenti filtri: enrolled, started, completed, and not enrolled. I risultati della ricerca non verranno visualizzati se l’ opzione di ordinamento è dateEnrolled, dueDate o dateEnrolled.
* **[!UICONTROL Nome dell’abilità]:** Abilità utilizzata per filtrare il corso di formazione esatto.
* **[!UICONTROL Nome del tag]:** Il tag utilizzato per filtrare i risultati esatti.

Di seguito sono riportati alcuni componenti aggiuntivi che è possibile personalizzare:

**[!UICONTROL Tipi di oggetti di apprendimento]:** Filtrare in base al tipo di oggetto di apprendimento. I tipi supportati sono: corso, certificazione, risorsa formativa e programma di apprendimento.

In AEM, il titolo di una scheda all’interno di una striscia sarà inizialmente vuoto. Nelle proprietà, digita il nome del titolo su widgets.html.

**Personalizzazione**

È possibile personalizzare il layout utilizzando widgets.html. È possibile modificare l’aspetto delle schede che vengono visualizzate e personalizzare il tema.

Nella sezione **[!UICONTROL Impostazioni generali]** è possibile scegliere i colori primari e secondari delle schede e specificare le proprietà per personalizzare il tema.

```
{ 
 "globalCssText":"@import url('https://fonts.googleapis.com/css2?family=Grandstander:ital,wght@0,100;0,200;0,300;0,400;0,500;0,600;0,700;0,800;0,900;1,100;1,200;1,300;1,400;1,500;1,600;1,700;1,800;1,900&family=Montserrat:ital,wght@0,100;0,200;0,300;0,400;0,500;0,600;0,700;0,800;0,900;1,100;1,200;1,300;1,400;1,500;1,600;1,700;1,800;1,900&display=swap');", 
 "fontNames":"Grandstander", 
 "cardLayout":{ 
 "cardLayoutName":"compact", 
 "cardPrimaryColor":"#376BA4", 
 "cardSecondaryColor":"#F98EB0", 
 "startedStateTextColor":"#ffffff", 
 "continueStateTextColor":"#ffffff", 
 "revisitStateTextColor":"#ffffff", 
 "startedStateColor":"#a0a0a0", 
 "continueStateColor":"#f9a122", 
 "revisitedStateColor":"#7fbc64", 
 "textPrimaryColor":"#ffffff", 
 "textSecondaryColor":"#d93f3f", 
 "navIconColor":"#a0a0a0" 
 } 
}
```

### Configurare i widget dei corsi salvati nei siti AEM

Il widget Corsi salvati consente agli Allievi di visualizzare i corsi contrassegnati o salvati direttamente sulle pagine di apprendimento, fornendo un facile accesso ai corsi che desiderano rivisitare o completare in un secondo momento.

Per configurare il widget **Corsi salvati** in AEM Sites:

1. Avvia **AEM Sites**.
2. Apri la pagina in modalità **[!UICONTROL Modifica]**.
3. Passa al **[!UICONTROL Browser dei componenti]** e aggiungi **[!UICONTROL Il mio widget di apprendimento]** alla pagina.
4. Seleziona il componente, quindi seleziona **[!UICONTROL Configura]**.
5. Seleziona **[!UICONTROL Corsi salvati]** dal menu a discesa nelle **[!UICONTROL Proprietà]**.
6. Seleziona **[!UICONTROL Fine]** e aggiorna la pagina in modalità **[!UICONTROL Anteprima]** o **[!UICONTROL Publish]**.

Gli Allievi possono visualizzare i corsi salvati nella striscia **[!UICONTROL Salvato da me]** nella pagina principale dell’Allievo. Se si seleziona la striscia **[!UICONTROL Salvato da me]**, gli allievi vengono indirizzati alla pagina del catalogo e viene visualizzato il numero esatto di corsi con segnalibro.

Quando si applica un altro filtro nel **Catalogo**, vengono visualizzati solo i risultati corrispondenti a tale filtro. Gli oggetti con segnalibro non vengono inclusi automaticamente.

### Ignora l’iscrizione agli oggetti di apprendimento di ordine superiore

Se la casella di controllo **Ignora l’iscrizione agli oggetti di apprendimento di ordine superiore** è abilitata e un utente è iscritto direttamente al programma di apprendimento o alla certificazione, nei widget verranno visualizzati i corsi per tale certificazione o programma di apprendimento.

Se la casella di controllo è disattivata, l’utente non visualizzerà i corsi presenti nel programma di apprendimento o nella certificazione a cui non si è registrato direttamente.

![](assets/higher-order-lo.png)

*Selezionare la casella di controllo Ignora l&#39;iscrizione agli oggetti di apprendimento di ordine superiore.

L’impostazione viene quindi applicata al widget.

### Protezione

Sono stati aggiunti i campi **ID client** e **Segreto client**. Inoltre, il token di aggiornamento viene nascosto. Una volta creata l’intera configurazione, se l’utente apre di nuovo la configurazione per modificarla, o se qualcun altro apre tale configurazione, il token di aggiornamento verrà nascosto.
