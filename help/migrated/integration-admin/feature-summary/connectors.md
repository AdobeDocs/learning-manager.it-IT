---
description: Scopri come integrare vari connettori in Learning Manager
jcr-language: en_us
title: Connettori Learning Manager
contentowner: jayakarr
exl-id: 1f44934b-6a2b-484d-bc7f-d0f23e3008ca
source-git-commit: 7be69e68f3b8970e090c8eccd25771cd2e5e99f1
workflow-type: tm+mt
source-wordcount: '15924'
ht-degree: 60%

---

# Connettori Learning Manager

Le aziende usano altre applicazioni e altri sistemi che devono essere integrati con Learning Manager. I connettori sono utility che consentono di eseguire integrazioni basate sui dati, ad esempio l&#39;importazione di dati in Learning Manager da sistemi esterni.  Esegue inoltre l&#39;esportazione dei dati in sistemi esterni da Learning Manager.

Learning Manager fornisce connettori Salesforce e FTP. Tramite il connettore Salesforce, gli Amministratori di integrazione di un’organizzazione possono integrare l’applicazione Salesforce con Learning Manager. Come integratore, puoi utilizzare il connettore FTP per importare automaticamente un set di utenti nell’applicazione aziendale.

Learning Manager offre inoltre connettori Lynda, getAbstract e Harvard Management System. Questi connettori consentono agli allievi di accedere e seguire i corsi messi a disposizione da Lynda.com, getAbstract e Harvard ManageMentor.

Continua a leggere per scoprire come configurare e utilizzare ciascuno di questi connettori in Learning Manager.

<!--
>[!NOTE]
>
>**Update:** December 2020 update of Learning Manager
>
>For **FTP**, **Box**, and **Custom FTP** connectors, while exporting Learner Transcript or xAPI, you can also export the data as a **zip** file, for:
>
>* Learner Transcripts
>* xAPI
-->

>[!NOTE]
>
>Con la versione di novembre 2022 di Adobe Learning Manager, Zoom ha dichiarato obsoleto [l&#39;autenticazione JWT entro giugno 2023](https://marketplace.zoom.us/docs/guides/auth/jwt/). Di conseguenza, il connettore Zoom con JWT continuerà a funzionare alla suddetta data, ma suggeriamo agli utenti di creare un’app OAuth Server-to-Server per sostituire la funzionalità nel proprio account. Per impostazione predefinita, tutte le nuove connessioni dispongono dell’autenticazione Zoom OAuth.

## Connettore Salesforce {#sfconnector}

Il connettore Salesforce collega gli account Learning Manager e Salesforce per automatizzare la sincronizzazione dei dati. Le funzionalità del connettore Salesforce sono le seguenti:

### Mapping attributi

L’Amministratore di integrazione può scegliere le colonne Salesforce e mapparle agli attributi raggruppabili di Learning Manager corrispondenti. Una volta completata, la mappatura viene utilizzata nelle successive importazioni di utenti. Può essere riconfigurata qualora l’Amministratore desiderasse una mappatura diversa per l’importazione degli utenti.

### Importazione automatica degli utenti

Il processo di importazione degli utenti consente all’Amministratore di Learning Manager di recuperare i dettagli dei dipendenti da Salesforce e importarli automaticamente in Learning Manager. Grazie all’automatizzazione, le operazioni di creazione di CSV e caricamento in Learning Manager non richiedono alcun intervento manuale.

### Pianificazione automatica

L’utilizzo della funzione di pianificazione automatica insieme alla funzione di importazione automatica degli utenti può rivelarsi efficace. L’Amministratore Learning Manager può impostare la pianificazione in base alle esigenze dell’organizzazione. Gli utenti nell&#39;applicazione Learning Manager possono essere aggiornati in base alla pianificazione.  La sincronizzazione può essere eseguita su base giornaliera nell’applicazione Learning Manager.

### Filtraggio degli utenti

L’Amministratore Learning Manager può applicare filtri agli utenti prima di importarli. Ad esempio, può scegliere di importare tutti gli utenti della gerarchia sotto uno o più Manager specifici.

### Configurazione del connettore Salesforce {#configuresalesforceconnector}

Scopri il processo da seguire per integrare Salesforce con Learning Manager

#### Prerequisiti {#prerequisites}

Assicurati di avere a portata di mano l’URL dell’organizzazione Salesforce. Ad esempio, se il nome della tua organizzazione è **myorg**, l&#39;URL di Salesforce potrebbe essere `https://myorg.salesforce.com`. È l’unica informazione richiesta per connettere l’account Salesforce a Learning Manager.

Accertati inoltre di disporre delle credenziali appropriate per effettuare l’accesso all’account.

#### Creazione di una connessione {#createaconnection}

1. Nella home page di Learning Manager, passa il mouse sulla scheda/sull’anteprima di Salesforce. Viene visualizzato un menu. Fai clic sulla voce **[!UICONTROL Connetti]** nel menu.

   ![](assets/mouserover-salesforce.png)

   *Opzione di connessione*

1. Viene visualizzata una finestra di dialogo che richiede di inserire l’URL dell’organizzazione. Fai clic su **[!UICONTROL Connetti]** dopo aver fornito l&#39;URL.
1. Una volta effettuata la connessione, viene visualizzata la pagina di panoramica.

### Mapping attributi {#mapattributes}

Una volta stabilita la connessione, puoi mappare le colonne di Salesforce agli attributi corrispondenti di Learning Manager. Questo passaggio è obbligatorio.

1. Nella pagina di mappatura, sul lato sinistro puoi vedere le colonne di Learning Manager e sul lato destro puoi vedere le colonne di Salesforce. Seleziona il nome appropriato per la colonna, mappato al nome della colonna del responsabile dell&#39;apprendimento.

   ![](assets/sfdc-map-columns.png)
   *Mapping attributi*

   >[!NOTE]
   >
   >I dati della colonna di Learning Manager mostrati sul lato sinistro vengono recuperati dai campi attivi. Il **campo manager** deve essere mappato a un campo di tipo indirizzo e-mail. Prima di poter utilizzare il connettore è necessario mappare tutte le colonne.

1. Fai clic su **[!UICONTROL Salva]** dopo aver completato la mappatura.
1. Il connettore è ora pronto per l’uso. L’account è stato configurato e viene visualizzato come origine dati nell’app Amministratore. L’Amministratore può pianificare l’importazione o la sincronizzazione su richiesta.

## Utilizzo del connettore Salesforce {#usingsalesforceconnector}

Il connettore Salesforce si collega a Salesforce.com per recuperare gli utenti in base alla configurazione e aggiungerli a Learning Manager.

### Importazione degli utenti dai contatti Salesforce {#import-salesforce-contacts}

Learning Manager migliora il connettore Salesforce per recuperare i contatti e gli utenti Salesforce e importarli automaticamente in Learning Manager.

Nella pagina del connettore Salesforce, inserisci l&#39;URL di Salesforce e completa l&#39;autenticazione. Dopo aver effettuato l&#39;autenticazione, puoi procedere all&#39;importazione di utenti o contatti. Se scegli l&#39;opzione Contatti, specifica il sottoinsieme di contatti da importare.

Scegli le colonne di Salesforce e mappale agli attributi raggruppabili di Learning Manager corrispondenti. Una volta completata, la mappatura viene utilizzata nelle successive importazioni di utenti.

1. Accedi a Salesforce.
1. Nella pagina di connessione, fai clic su **[!UICONTROL Importa utenti]** interni.

   ![](assets/image048.png)
   *Importare utenti interni*

1. **Nella pagina Importa utenti** è disponibile una nuova opzione, Contatti. Fai clic sul pulsante **di opzione Contatti** e vedrai le seguenti opzioni.

   ![](assets/image050.png)
   *Mappare gli attributi di contatto*

1. Se si fa clic su **[!UICONTROL Sì]**, è possibile effettuare le seguenti operazioni:

   * **Scegli colonna Contatti:** seleziona il campo da importare in Learning Manager.
   * **Specificare valori:** scegliere i valori che rappresentano il campo selezionato.

   ![](assets/image053.png)
   *Specificare i valori*

   * Mappare le colonne di Salesforce con quelle di Learning Manager.
   * Per iniziare l&#39;importazione, fate clic su **[!UICONTROL Salva]**.

1. Se si fa clic su **[!UICONTROL No. Importa tutti i contatti]**, puoi mappare direttamente i campi senza filtrare i contatti. Qui, dovresti importare tutti i contatti da Salesforce.
1. Per iniziare l&#39;importazione, fate clic su **[!UICONTROL Salva]**.

## Esportazione dei record della formazione

Learning Manager offre la possibilità di esportare record di apprendimento come trascrizione, report utente, report abilità in Salesforce. È possibile determinare se i dati esportati devono essere collegati alla tabella &quot;Utente&quot; o alla tabella &quot;Contatti&quot; in Salesforce.

![](assets/export-events-new.png)
*Esportazione dei record di apprendimento*

### Oggetti personalizzati in Salesforce

Prima di esportare i record di apprendimento da Learning Manager, devi creare oggetti personalizzati in Salesforce. Gli oggetti personalizzati sono oggetti creati per archiviare informazioni specifiche dell&#39;azienda o del settore. Per ulteriori informazioni, consulta [Oggetti personalizzati di Salesforce](https://trailhead.salesforce.com/en/content/learn/modules/data_modeling/objects_intro).

Di seguito viene descritto come creare gli oggetti:

1. Scaricare e installare i pacchetti per creare gli oggetti personalizzati.

   * [Pacchetto 1](https://test.salesforce.com/packaging/installPackage.apexp?p0=04t1k0000008WPJ)
   * [Pacchetto 2](https://test.salesforce.com/packaging/installPackage.apexp?p0=04t1k0000008WPT)
   * [Pacchetto 3](https://test.salesforce.com/packaging/installPackage.apexp?p0=04t1k0000008WPi)

1. Rinomina gli oggetti personalizzati in Salesforce.
1. Seleziona gli eventi e fai clic su **[!UICONTROL Salva]**.

>[!NOTE]
>
>Assicurati che l&#39;accesso come amministratore di sistema sia stato concesso a tutti i campi attivi aggiunti dopo l&#39;installazione del pacchetto.

**Collega gli eventi con:** scegli la sezione che desideri esportare: Utente o Contatto. Se scegli Oggetto Contact, gli utenti presenti in Learning Manager ma non in Salesforce verranno creati in Salesforce.

![](assets/link-events.png)
*Opzione Collega eventi*

>[!NOTE]
>
>È possibile creare più collegamenti in un account. Una singola connessione può servire fino a tre oggetti personalizzati in Salesforce. Se desideri creare più connessioni per lo stesso account Salesforce, devi installare i tre pacchetti. Sono supportati fino a tre pacchetti.
>
>Per tutte le connessioni che si desidera creare, è necessario installare i relativi pacchetti.

>[!NOTE]
>
>Nella pagina Stato esecuzione di Salesforce, il numero di record elaborati può essere controllato solo da Salesforce. Learning Manager visualizza lo stato come completato anche in caso di esportazione parziale o errore in tutti i record elaborati.

## Installazione del pacchetto Salesforce

Learning Manager offre un pacchetto di app Salesforce. Una volta installato e configurato in SFDC, gli addetti alle vendite possono svolgere le proprie attività di formazione all’interno del portale SFDC. Questa app consente agli utenti di SFDC di esplorare nuovi corsi di formazione, visualizzare i consigli e consultarli direttamente all’interno del portale SFDC. Gli utenti ricevono anche gli annunci inviati dagli amministratori sotto forma di masthead direttamente all&#39;interno dell&#39;app all&#39;interno del portale SFDC.

### Configurazione nell’app Learning Manager

1. Accedi al tuo account Amministratore Learning Manager come Amministratore dell’integrazione.
1. Fai clic su **[!UICONTROL Applicazioni]** > **[!UICONTROL App]** in primo piano.
1. Fai clic su **[!UICONTROL Salesforce]**.
1. Nella pagina dell&#39;app Salesforce, annota l&#39;ID applicazione (noto anche come ID client) e il segreto client menzionati nella descrizione.
1. Fai clic su **[!UICONTROL Approva]** e l&#39;app deve essere approvata correttamente.
1. Fai clic su **[!UICONTROL Risorse]** sviluppatore > **[!UICONTROL token di accesso per test e sviluppo]**.
1. Nella sezione Ottieni codice OAuth, l&#39;ID client e l&#39;ambito devono essere impostati su - admin:read,admin:write. Fai clic su **[!UICONTROL Invia]**.
1. In Richiedi Token di Aggiornamento, immetti l’ID client e il segreto client. Fai clic su **[!UICONTROL Invia]** e annota il token di aggiornamento.

### Creazione dell’account nell’app Salesforce

1. Crea un account nella pagina di registrazione di Salesforce. Devi creare un account Salesforce nell&#39;edizione Developer o Enterprise.  [URL di registrazione sviluppatore](https://developer.salesforce.com/signup). Assicurati di utilizzare l&#39;ID e-mail per registrarti a Salesforce utilizzato per Learning Manager.
1. Verifica il tuo account tramite l’e-mail di verifica.
1. Crea una password e accedi a Salesforce.
1. Nota l&#39;URL di Salesforce dopo l&#39;accesso (ad esempio, site.lightning.force.com)

### Installazione del pacchetto Learning Manager

Se desideri installare il pacchetto, devi innanzitutto eliminare il pacchetto esistente in Salesforce. Prima della disinstallazione, attiva le impostazioni, come illustrato di seguito. L’attivazione è obbligatoria, altrimenti non sarà possibile installare il pacchetto.

>[!NOTE]
>
>L&#39;app Adobe Learning Manager è supportata solo nella visualizzazione Salesforce Lightning.

1. Avvia l&#39;URL](https://login.salesforce.com/packaging/installPackage.apexp?p0=04t1k0000008WOQ) del [pacchetto di Learning Manager.
1. **Nella pagina Login**, fai clic su **[!UICONTROL Usa dominio]** personalizzato.
1. Immetti l&#39;URL del pacchetto e fai clic su **[!UICONTROL Continua]**. Nella pagina di installazione deve essere selezionata l&#39;opzione Installa solo per amministratori. Non cambiare questa opzione.
1. Fai clic su **[!UICONTROL Installa]**. Una volta installato il pacchetto, fai clic su **[!UICONTROL Fine]**. Si apre la pagina Pacchetti installati in cui puoi visualizzare il pacchetto Adobe Learning Manager installato.
1. Vai all’App Launcher (accanto a Configurazione) e cerca Adobe Learning Manager.
1. Per configurare l&#39;app, fai clic su **[!UICONTROL Configura]**.
1. Fai clic su **[!UICONTROL Nuovo]** e aggiungi i seguenti dettagli:

   * **Configurazione:** immetti il nome che preferisci.
   * **ClientID**: immetti il valore ottenuto dalla prima sezione.
   * **ClientSecret:** immettere il valore ottenuto dalla prima sezione.
   * **RefreshToken:** immetti il valore ottenuto dalla prima sezione.
   * **LearningManagerBaseURL:** l&#39;URL del sito in cui è ospitato Learning Manager.

### Aggiunta delle impostazioni del sito remoto

1. Nell&#39;angolo superiore destro della pagina, fai clic su **[!UICONTROL Imposta]**.
1. In **[!UICONTROL Ricerca]** rapida, cercare Impostazioni sito remoto.
1. Fare clic su **[!UICONTROL Nuovo sito]** remoto.
1. Immetti i seguenti dettagli:

   * **Nome del sito remoto:** immetti il nome che preferisci.
   * **URL del sito remoto:** l’URL del sito in cui è ospitato Learning Manager.

1. Avvia Learning Manager.

### Attivare le notifiche per l&#39;app Learning Manager

1. Nell&#39;angolo superiore destro, fai clic su **[!UICONTROL Imposta]**.
1. Cerca le notifiche personalizzate.
1. Fare clic su **[!UICONTROL Nuovo]**.
1. Immetti i seguenti dettagli:

   1. **Nome notifica personalizzato:** LearningManagerNotification
   1. **Nome API:** LearningManagerNotification

1. Seleziona sia Desktop **che****Mobile** come canali supportati.

1. Fai clic su **[!UICONTROL Salva]**.
1. Per abilitare le notifiche push per i dispositivi mobili, esegui le operazioni descritte di seguito:

   1. Installa l’app mobile Salesforce sul tuo cellulare.
   1. Accedi all’app utilizzando le tue credenziali.
   1. Vai a **Impostazioni di configurazione** > **recapito** delle notifiche.
   1. Aggiungi Salesforce per iOS e Android.

### Disinstallazione di Learning Manager da Salesforce

1. Nell&#39;app Salesforce, vai a Pacchetti installati.
1. Fai clic su **[!UICONTROL Disinstalla]**.

## Configurazione di Learning Manager per gli utenti Salesforce

L’app Learning Manager è disponibile anche per gli utenti presenti in qualsiasi account Salesforce. L’amministratore Salesforce può aggiungere utenti in base ai profili. I profili Salesforce sono simili a quelli di Learning Manager. Ad esempio, Amministratore, Amministratore dell’integrazione, Istruttore e così via. L’amministratore Salesforce può inoltre creare un profilo personalizzato.

Come amministratore Salesforce, puoi assegnare i profili agli utenti oppure creare un profilo personalizzato.

![](assets/create-profile.png)

Durante l’installazione del pacchetto, puoi assegnare il profilo Salesforce agli Allievi.

Dopo aver installato il pacchetto, è necessario configurare il profilo.

Fare clic su **[!UICONTROL Configura]** > **[!UICONTROL Nuovo]** e quindi aggiungere quanto segue:

* Nome configurazione
* ID client
* Segreto client
* LearningManagerBaseURL
* Disattivazione del reindirizzamento

>[!NOTE]
>
>Per consentire agli Allievi di visualizzare l&#39;app Learning Manager, è necessario abilitare l&#39;app per tutti gli Allievi.

Il passo successivo consiste nel fornire l’autorizzazione per accedere all’app Learning Manager.

![](assets/permission-set.png)

*Impostare le autorizzazioni per accedere all&#39;app Learning Manager*

Seleziona gli utenti e assegna le autorizzazioni di conseguenza. Gli Allievi ora possono accedere all’app Learning Manager.

Adesso, seleziona un profilo, ad esempio Profilo standard di un utente, quindi fai clic sul profilo. Fai clic su **[!UICONTROL Modifica e nella** sezione Impostazioni **app personalizzate seleziona la casella** di controllo Adobe Learning Manager **]**. In questo modo l’utente può accedere all’app.

Nella sezione **Impostazioni schede personalizzate**, nell’elenco a discesa **Home Allievo** seleziona l’opzione **Predefinito su**.

È necessario rendere l’app visibile a tutti i profili.

Fai clic su **[!UICONTROL Salva]** e gli Allievi appartenenti a tutti i profili accederanno all&#39;app Learning Manager.

### Modifiche relative al percorso di apprendimento

#### Connessioni esistenti

Se l&#39;opzione Percorso di apprendimento è disabilitata nell&#39;account Amministratore, nel report non vengono aggiunte righe e colonne.

Se l&#39;opzione Percorso di apprendimento è abilitata nell&#39;account Amministratore, la colonna &quot;Tipo&quot; verrà popolata con il Percorso di apprendimento nel caso in cui gli Allievi vi siano iscritti.

>[!NOTE]
>
>Se il flag è abilitato e si utilizza una connessione esistente, alcuni record potrebbero non essere aggiunti.

#### Nuove connessioni

Se l&#39;opzione Percorso di apprendimento è disabilitata nell&#39;account Amministratore, il rapporto di formazione sarà composto dalle seguenti colonne, ma non conterrà alcun dato.

* **Percorso incorporato:** mostra il nome del programma di apprendimento.
* **ID percorso incorporato:** mostra gli ID del programma di apprendimento.
* **ID corso incorporato:** visualizza gli ID dei corsi che si trovano all&#39;interno di un percorso di apprendimento.

Anche per le nuove connessioni negli account in cui è attivato il percorso di apprendimento verranno visualizzate le tre nuove colonne e verranno inviati tutti i dati.

Inoltre, il report conterrà il tipo di colonna Percorso di apprendimento (livello superiore) per tutti gli Allievi iscritti a un percorso di apprendimento.

Nella colonna Tipo, il programma di apprendimento verrà rinominato Percorso di apprendimento. Per le connessioni esistenti, non è prevista alcuna modifica.

## Connettore FTP Learning Manager {#ftpconnector}

Usando il connettore FTP, puoi integrare Learning Manager con sistemi esterni arbitrari per l’automazione della sincronizzazione dei dati. I sistemi esterni dovrebbero esportare i dati in formato CSV e inserirli nella cartella appropriata dell’account FTP di Learning Manager. Le funzionalità del connettore FTP sono le seguenti:

È inoltre possibile utilizzare il connettore Box per la migrazione, l&#39;importazione e l&#39;esportazione dei dati. Per ulteriori informazioni, vedere Connettore Box.

### Importazione di dati {#dataimport}

Il processo di importazione degli utenti consente all’Amministratore Learning Manager di recuperare i dettagli dei dipendenti dal servizio FTP di Learning Manager e importarli automaticamente in Learning Manager. Utilizzando questa funzione, è possibile integrare più sistemi inserendo il file CSV generato da tali sistemi nelle apposite cartelle degli account FTP. Learning Manager preleva i file CSV, li unisce e importa i dati in base alla pianificazione Fai riferimento alla funzione di pianificazione per ulteriori informazioni.

**Mapping attributi**

L’Amministratore di integrazione può scegliere le colonne di CSV e mapparle agli attributi raggruppabili di Learning Manager. L’operazione di mappatura viene eseguita una sola volta. Una volta completata, la mappatura viene utilizzata nelle successive importazioni di utenti. Può essere riconfigurata qualora l’Amministratore desiderasse una mappatura diversa per l’importazione degli utenti.

#### Esportazione di dati {#exportdata}

La funzione di esportazione dei dati consente di esportare le abilità degli utenti e le trascrizioni degli allievi in un percorso FTP per l’integrazione con qualsiasi sistema di terze parti.

#### Pianificazione {#scheduling}

L’Amministratore può impostare le attività di pianificazione secondo i requisiti dell’organizzazione e gli utenti nell’applicazione Learning Manager vengono aggiornati in base alla pianificazione. Allo stesso modo, l’Amministratore di integrazione può pianificare l’esportazione delle abilità in modo tempestivo per consentire l’integrazione con un sistema esterno.  La sincronizzazione può essere eseguita su base giornaliera nell’applicazione Learning Manager.

### Configurazione del connettore FTP Learning Manager {#configurecaptivateprimeftpconnector}

Scopri il processo da seguire per integrare il connettore FTP con Learning Manager.

#### Creazione di una connessione {#Createaconnection-1}

1. Nella home page di Learning Manager, passa il mouse sopra la scheda/l’anteprima FTP. Viene visualizzato un menu. Fai clic sulla voce **[!UICONTROL Connetti]** nel menu.

   ![](assets/mouseover-ftpconnector.png)

   *Opzione di connessione*

1. Viene visualizzata una finestra di dialogo che richiede di inserire l’id e-mail. Fornisci l&#39;ID e-mail del responsabile della gestione dell&#39;account FTP di Learning Manager per l&#39;organizzazione. Fai clic su **[!UICONTROL Connetti]** dopo aver fornito l&#39;id e-mail.
1. Learning Manager invia all’utente un’e-mail con la richiesta di reimpostare la password prima di accedere all’FTP per la prima volta. L’utente deve reimpostare la password e utilizzarla per accedere all’account FTP Learning Manager.

   >[!NOTE]
   >
   >È possibile creare un solo account FTP Learning Manager per un determinato account Learning Manager.

   Nella pagina di panoramica, è possibile specificare il nome della connessione per l&#39;integrazione. Scegli l&#39;azione da eseguire tra le seguenti opzioni:

   * Importazione di utenti interni
   * Importa xAPI
   * Esporta abilità utente - Configura una pianificazione
   * Esporta abilità utente - Su richiesta
   * Esporta trascrizioni allievi - Configura una pianificazione
   * Esportazione delle trascrizioni degli allievi - Su richiesta

   ![](assets/ftp-connector-dashboard.png)
   *Opzioni di esportazione*

### Importa

+++Utente interno

L&#39;opzione di importazione utente interno consente di importare gli utenti da un file CSV in un Learning Manager su richiesta o in base alla pianificazione.

+++

Attributi +++Map

Una volta stabilita la connessione, è possibile mappare le colonne dei file CSV presenti nella cartella FTP agli attributi corrispondenti di Learning Manager. Questo passaggio è obbligatorio.

1. Nella pagina Mapping attributi, sul lato sinistro puoi visualizzare le colonne previste da Learning Manager e sul lato destro puoi vedere i nomi delle colonne CSV. Inizialmente, sul lato destro viene visualizzata una casella di selezione vuota. Importa un qualsiasi modello CSV facendo clic su **Scegli file**.
1. Il passaggio precedente consente di compilare l’elenco a discesa di selezione sulla destra con tutti i nomi delle colonne CSV. Seleziona il nome appropriato per la colonna, mappato al nome della colonna del responsabile dell&#39;apprendimento.

   >[!NOTE]
   >
   >Il campo Manager deve essere mappato a un campo di tipo indirizzo e-mail. Prima di poter utilizzare il connettore è necessario mappare tutte le colonne.

1. Fai clic su **[!UICONTROL Salva]** dopo aver completato la mappatura.

   Il connettore è ora pronto per l’uso. L’account configurato viene visualizzato come origine dati nell’app Amministratore per consentire all’Amministratore di pianificare l’importazione o per la sincronizzazione su richiesta.



+++

+++Utilizzo del connettore FTP di Learning Manager

1. I file CSV provenienti da sistemi esterni devono essere posizionati nel seguente percorso:

   `code $OPERATION$/$OBJECT_TYPE$/$SUB_OBJECT_TYPE$/data.csv`

   >[!NOTE]
   >
   >Nella versione di luglio 2016, è consentita solo l&#39;importazione di utenti. Pertanto, per utilizzare il connettore FTP è necessario assicurarsi che i file CSV si trovino nella seguente cartella:

   `code Home/import/user/internal/*.csv`

1. Il connettore FTP prende tutte le righe dai file CSV. È importante che la riga corrispondente a un utente in un file CSV non appaia in nessun altro file CSV.
1. Tutti i CSV devono contenere le colonne specificate nella mappatura.
1. Tutti i CSV richiesti devono essere presenti nella cartella prima dell&#39;inizio del processo.

>[!NOTE]
>
>Durante l’importazione degli utenti in Learning Manager, l’Amministratore deve sapere anche in che modo gli utenti vengono gestiti in Learning Manager. Per ulteriori informazioni, consulta la Guida](migration-manual.md#usermanagement) alla [gestione utenti.

+++

+++Importa xAPI

Le opzioni di importazione xAPI consentono di pianificare l’importazione di istruzioni xAPI da servizi di terze parti a Learning Manager su richiesta.

+++

+++Configurazioni necessarie per importare xAPI

1. Dalla pagina di configurazione, seleziona una configurazione esistente disponibile nell&#39;elenco delle configurazioni per importare le istruzioni xAPI dal file CSV. Fare clic su modifica o **aggiungere un nuovo collegamento di configurazione** per passare alla pagina Configura origini di importazione.

   **Configurazione**

   * Nella pagina Configurazione importazione-Origini, compila i campi Nome e Nome file di origine. Il nome del file di origine deve corrispondere al nome del file fornito nel percorso FTP della cartella.
   * Fai clic su **[!UICONTROL Salva]** per salvare le modifiche.

   ![](assets/configurations.png)
   *Configurare*

   **Filtro**

   * Nel riquadro a sinistra, fai clic su **[!UICONTROL Filtro]**.
   * Nella pagina Configurazione importazione-Filtro, compila i campi Nome e Condizioni per filtrare i record. Fai clic su **[!UICONTROL Aggiungi nuovo filtro]** per aggiungere un altro filtro. È possibile salvare o eliminare un filtro facendo clic sull’opzione **Salva** o **Elimina** nella colonna Azioni.

   ![](assets/filter.png)
   *Filtro*

   **Mappatura**

   * Nel riquadro a sinistra, fai clic su **[!UICONTROL Mappatura]**.
   * Nella parte sinistra della pagina Importa istruzioni xAPI-Configurazione-Mappatura, sono visualizzati i nomi dei percorsi JSON xAPI che devono essere mappati ai nomi delle colonne CSV.
   * Per impostazione predefinita, i tre nomi dei percorsi JSON che devono essere mappati ai nomi delle colonne CSV sono **actor.mbox**, **verb.id** e **object.id**. È possibile aggiungere altri campi da mappare facendo clic su **Aggiungi nuova mappatura**.

   * Seleziona il tipo di nome colonna che stai mappando al nome del percorso JSON (che si tratti di una stringa, di un numero, di un valore booleano o del tipo di data).
   * Una volta completata la mappatura, fai clic su Salva. L’importazione di xAPI può ora essere eseguita in base a una pianificazione o su richiesta.

   ![](assets/mapping.png)
   *Mappatura*

1. Nel riquadro a sinistra, fai clic su **[!UICONTROL Configura pianificazione]**. Fai clic su **[!UICONTROL Abilita pianificazione]** per pianificare l’importazione di istruzioni xAPI.

   Inserisci l’ora e la data di inizio e specifica la frequenza della pianificazione di importazione xAPI in giorni. Ad esempio, pianificando l’importazione xAPI in modo che venga eseguita ogni 3 giorni.

   ![](assets/configure-schedule2x.png)
   *Importa istruzioni xAPI - Configura pianificazione*

1. Nel riquadro a sinistra, fai clic su **[!UICONTROL Esecuzione]** su richiesta.

   ![](assets/on-demand.png)
   *Importazione di istruzioni xAPI - Su richiesta*

1. Nel riquadro a sinistra, fai clic su **[!UICONTROL Stato esecuzione]** per visualizzare il riepilogo di tutte le esecuzioni per questo connettore, in ordine cronologico. È possibile visualizzare la data di inizio e la durata dell’importazione xAPI, il tipo di importazione (su richiesta o pianificata) e lo stato dell’importazione (se l’importazione xAPI è in corso, è completata o non è riuscita).

   ![](assets/execution-status2x.png)
   *Importa istruzioni xAPI - Stato esecuzione*

+++

### Esporta

+++Competenze

Sono disponibili due opzioni per esportare i report sulle abilità degli utenti.

**[!UICONTROL Abilità utente - Su richiesta]**: è possibile specificare la data di inizio ed esportare il report utilizzando questa opzione. Il report viene estratto a partire dalla data inserita fino a oggi.

![](assets/export-on-demand2x.png)
*Opzione di esportazione su richiesta*

**[!UICONTROL Abilità utente - Configura]**: questa opzione consente di pianificare l’estrazione del report. Seleziona la casella di controllo Abilita pianificazione e specifica la data e l’ora di inizio. Puoi anche specificare l’intervallo desiderato per la generazione e l’invio del report.

![](assets/user-skills-configure.png)
*Configurazione dell&#39;esportazione del report*

+++

Per aprire la cartella di esportazione in cui si trovano i file esportati, apri il collegamento alla cartella FTP fornito nella pagina Abilità utente, come mostrato di seguito.

![](assets/ftp-folder.png)
*Cartella FTP per visualizzare i file*

I file esportati automaticamente si trovano nel percorso **Home/export/&#42;FTP_location&#42;**

I file esportati automaticamente sono disponibili con il titolo **skill_achievements_&#42;date from &#42;_to_&#42;date to&#42;.csv**

![](assets/exported-csvs.png)
*File .csv esportato*

+++Trascrizione Allievo

![](assets/on-demand-report.png)

**Configura**: questa opzione consente di pianificare l&#39;estrazione del report. Seleziona la casella di controllo Abilita pianificazione e specifica la data e l’ora di inizio. Puoi anche specificare l’intervallo desiderato per la generazione e l’invio del report.

![](assets/configure-report.png)

+++

Per aprire la cartella di esportazione in cui si trovano i file esportati nella posizione FTP, apri il collegamento alla cartella FTP fornito nella pagina Trascrizione Allievo, come mostrato di seguito

I file esportati automaticamente si trovano nel percorso **Home/export/&#42;FTP_location&#42;**

I file esportati automaticamente sono disponibili con il titolo **learner_transcript_&#42;date from &#42;_to_&#42;date to&#42;.csv**

![](assets/exported-file.png)

### Supporto per campi CSV manuali {#supportformanualcsvfields}

Durante l’importazione di dati utente tramite FTP, un Amministratore deve mappare tutti i campi attivi presenti nel sistema sul campo corrispondente nel csv.

Questo è obbligatorio per tutti i campi csv. attivi. Per i campi attivi manuali, l’Amministratore dell’integrazione può selezionare l’opzione **DontImportFromSource**.

Selezionando questa opzione, i valori dei campi attivi manuali non vengono riempiti mediante l’importazione di csv. I valori forniti dall’Allievo restano intatti.

>[!NOTE]
>
>Durante la mappatura, se l&#39;opzione **DontImportFromSource** è selezionata per il campo attivo csv, questo campo verrà eliminato dal sistema.

![](assets/ftp-conector-foractivefields.png)
*Connettore FTP per i campi attivi*

## Connettore Lynda {#lyndaconnector}

Il connettore Lynda è utilizzato dai clienti enterprise di Lynda.com che desiderano far seguire i corsi Lynda ai loro allievi da Learning Manager. È possibile configurare il connettore per recuperare periodicamente corsi da Lynda.com con la tua chiave API. Quando un corso viene creato in Learning Manager, gli utenti possono ricercarlo e seguirlo. Sarà quindi possibile seguire i progressi dell’Allievo in Learning Manager.

### Configurazione del connettore Lynda {#configurethelyndaconnector}

1. Nel dashboard di amministrazione integrato, fai clic su Lynda.

   Viene visualizzato il riquadro con tre opzioni: Guida introduttiva, Connetti e Gestione connessioni.

1. Se devi configurare il connettore Lynda per la prima volta, fai clic su Connetti.

   <!--Configure the Exavault FTP account before you configure this connector.-->

1. Nella pagina di connessione, specifica un nome per il connettore. Inserisci appkey e chiave privata per la connessione.

   >[!NOTE]
   >
   >Chiedi al tuo fornitore l’appkey e la chiave privata.

1. Fai clic su Salva.

   La configurazione viene salvata e viene aggiunta la connessione Lynda per l’account. È ora possibile fare clic su Gestione connessioni nella home page e modificare la configurazione in qualsiasi momento.

1. Se disponi già di una connessione configurata, fai clic su Gestione connessioni per visualizzare tutte le connessioni.

   >[!NOTE]
   >
   >Prima di configurare il connettore è necessario abilitare la funzione di migrazione per l’account.

1. Fai clic sulla connessione da modificare.
1. Nel riquadro a sinistra, fai clic su **[!UICONTROL Configura]**. Effettua una delle seguenti operazioni:

   * Visualizza o modifica i dettagli del tuo account e la pianificazione della sincronizzazione da questa finestra. Seleziona la casella di controllo Abilita connessione se desideri abilitare questo account.
   * Fai clic su Modifica e modifica le tue credenziali. Per annullare gli aggiornamenti a questo campo, fai clic su Ripristina.
   * Fai clic su Abilita pianificazione per pianificare la sincronizzazione. Inserisci l’ora e la data di inizio e specifica la frequenza della pianificazione di sincronizzazione in giorni. Ad esempio, puoi abilitare la sincronizzazione ogni tre giorni.

   Fai clic su **[!UICONTROL Salva]** per salvare le modifiche.

   ![](assets/lynda.png)

   *Configurare il connettore Lynda per Learning Manager*

1. Nel riquadro a sinistra, fai clic su Esecuzione su richiesta. Questa opzione consente di importare i feed degli utenti e altri dati rilevanti da Lynda. Immetti la data di inizio per l’esecuzione su richiesta e fai clic su Esegui per eseguire la sincronizzazione. Vengono importati tutti i dati dalla data di inizio fino a oggi.

   * È possibile fare clic su Disabilita accesso a Learning Manager durante un’esecuzione in cui l’applicazione presenta un periodo di inattività durante la sincronizzazione.
   * Se fai clic su Abilita accesso a Learning Manager durante l’esecuzione, non si verificano interruzioni del servizio durante la sincronizzazione.

   ![](assets/lynda-ondemand.png)

   *Esecuzione su richiesta per il connettore Lynda*

1. È anche possibile fare clic su Stato esecuzione nel riquadro sinistro in qualsiasi momento per visualizzare il riepilogo di tutte le esecuzioni per questo connettore, in ordine cronologico. Puoi visualizzare la data di inizio e la durata della sincronizzazione, il tipo di sincronizzazione (se si tratta di una sincronizzazione su richiesta) e lo stato della sincronizzazione (se la sincronizzazione è in corso o è completa).

   >[!NOTE]
   >
   >Quando elimini e ricrei una connessione, le precedenti esecuzioni del connettore vengono visualizzate nuovamente. È possibile visualizzare tutte le esecuzioni effettuate prima di eliminare la connessione.

   Solo la sincronizzazione più recente può essere eseguita di nuovo.

   ![](assets/lynda-ondemand.png)

   *Visualizzare il riepilogo di tutte le esecuzioni, fare clic su Stato esecuzione*

## Connettore getAbstract {#getabstractconnector}

Il connettore getAbstract viene utilizzato dai clienti enterprise di getAbstract.com, che desiderano che i loro Allievi utilizzino i riepiloghi di getAbstract. È possibile configurare il connettore in modo da ricavare periodicamente dei dati di utilizzo, in base ai quali i record di completamento dello studente vengono creati all’interno di Learning Manager. Continua a leggere per scoprire come configurare il connettore in Learning Manager.

### Configurazione del connettore getAbstract {#configurethegetabstractconnector}

1. Nel dashboard di amministrazione integrato, fai clic su getAbstract.

   Nel riquadro sono disponibili tre opzioni: Guida introduttiva, Connetti e Gestione connessioni.

1. Se devi configurare il connettore getAbstract per la prima volta, fai clic su Connetti.

   <!--Configure the Exavault FTP account before you configure this connector.

   Ensure that you share this FTP credentials with your content provider to access the feeds.-->

1. Immetti un nome per la connessione nel campo Nome connessione.

   Immetti le chiavi appropriate nei campi id client e chiave privata client. Chiedi al tuo fornitore le chiavi appropriate per questo connettore.

   Le chiavi sono necessarie per ottenere i metadati relativi ai corsi seguiti dal client.

1. Se disponi già di una connessione configurata, nella home page fai clic su getAbstract > Gestione connessioni per visualizzare e modificare la configurazione esistente.

   >[!NOTE]
   >
   >Prima di configurare il connettore è necessario abilitare la funzione di migrazione per l’account.

1. Fai clic sulla connessione di cui desideri visualizzare o modificare la configurazione.

   ![](assets/getabstractschedulepage.png)

   *Configurazione del connettore getAbstract per Learning Manager*

1. Nel riquadro a sinistra, fai clic su Configura. Effettua una delle seguenti operazioni:

   * Visualizza o modifica i dettagli del tuo account e la pianificazione della sincronizzazione da questa finestra. Seleziona la casella di controllo Abilita connessione se desideri abilitare questo account.
   * Fai clic su Modifica e modifica le tue credenziali. Per annullare gli aggiornamenti a questo campo, fai clic su Ripristina.
   * Fai clic su Abilita pianificazione per pianificare la sincronizzazione. Inserisci l’ora e la data di inizio e specifica la frequenza della pianificazione di sincronizzazione in giorni. Ad esempio, puoi abilitare la sincronizzazione ogni tre giorni.

1. Fai clic su **[!UICONTROL Salva]**.

   La configurazione viene salvata e viene aggiunta la connessione getAbstract per l’account.

1. Nel riquadro a sinistra, fai clic su Esecuzione su richiesta. Questa opzione consente di importare i feed degli utenti e altri dati rilevanti da getAbstract. Immetti la data di inizio per l’esecuzione su richiesta e fai clic su Esegui per eseguire la sincronizzazione. Vengono importati tutti i dati dalla data di inizio fino a oggi.

   * È possibile fare clic su Disabilita accesso a Learning Manager durante un’esecuzione in cui l’applicazione presenta un periodo di inattività durante la sincronizzazione.
   * Se fai clic su Abilita accesso a Learning Manager durante l’esecuzione, non si verificano interruzioni del servizio durante la sincronizzazione.

1. È anche possibile fare clic su Stato esecuzione nel riquadro sinistro in qualsiasi momento per visualizzare il riepilogo di tutte le esecuzioni per questo connettore, in ordine cronologico. Puoi visualizzare la data di inizio e la durata della sincronizzazione, il tipo di sincronizzazione (se si tratta di una sincronizzazione su richiesta) e lo stato della sincronizzazione (se la sincronizzazione è in corso o è completa).

   >[!NOTE]
   >
   >Quando elimini e ricrei una connessione, le precedenti esecuzioni del connettore vengono visualizzate nuovamente. È possibile visualizzare tutte le esecuzioni effettuate prima di eliminare la connessione.

   Solo la sincronizzazione più recente può essere eseguita di nuovo.

   Per consentire la corretta esecuzione di qualsiasi tipo di sincronizzazione, assicurati che nella cartella FTP getAbstract sia presente il feed dell’utente per le date specificate nella sincronizzazione.

   Consulta il foglio di calcolo Excel riportato di seguito, che è un file di esempio di un feed utente di getAbstract. Il nome del file deve rispettare il formato: **report_export_yyyy_MM_dd_HHmmss.xlsx** o **report_export_yyyy_MM_dd.xlsx**.
   [Esempio di feed utente di getAbstract Foglio Excel](assets/report-export-20170401175342.xlsx)

## Connettore Harvard ManageMentor {#hmmconnector}

Il connettore Harvard ManageMentor viene utilizzato dai clienti enterprise di Harvard ManageMentor che desiderano che i loro Allievi utilizzino i corsi Harvard ManageMentor. Il connettore consente di creare corsi all’interno di Learning Manager e può essere configurato in modo da recuperare periodicamente dati sull’avanzamento dell’Allievo. Per configurare il connettore, segui la seguente procedura:

### Configurazione del connettore Harvard ManagerMentor {#configuretheharvardmanagermentorconnector}

1. Nel dashboard di amministrazione integrato, fai clic su Harvard ManageMentor.

   Nel riquadro sono disponibili tre opzioni: Guida introduttiva, Connetti e Gestione connessioni.

1. Se devi configurare il connettore Harvard ManageMentor per la prima volta, fai clic su Connetti.

   <!--Configure the Exavault FTP account before you configure this connector.

   Ensure that you share this FTP credentials with your content provider to access the feeds.-->

1. Immetti un nome per la connessione nel campo Nome connessione. Fai clic su Connetti per salvare la connessione.
1. Se disponi già di una connessione configurata, nella home page fai clic su Harvard ManageMentor > Gestione connessioni. Fai clic sulla connessione di cui desideri modificare la connessione esistente.

   >[!NOTE]
   >
   >Prima di configurare il connettore è necessario abilitare la funzione di migrazione per l’account.

   ![](assets/hmm.png)

   *Configurare il connettore HarvardManage Mentor per Learning Manager*

1. Nel riquadro a sinistra, fai clic su Configura. Effettua una delle seguenti operazioni:

   * Visualizza o modifica i dettagli del tuo account e la pianificazione della sincronizzazione da questa finestra. Seleziona la casella di controllo Abilita connessione se desideri abilitare questo account.
   * Fai clic su Abilita pianificazione per pianificare la sincronizzazione. Inserisci l’ora e la data di inizio e specifica la frequenza della pianificazione di sincronizzazione in giorni. Ad esempio, puoi abilitare la sincronizzazione ogni tre giorni.

1. Nel riquadro a sinistra, fai clic su Esecuzione su richiesta. Questa opzione consente di importare i feed degli utenti e altri dati rilevanti da Harvard ManageMentor. Immetti la data di inizio per l’esecuzione su richiesta e fai clic su Esegui per eseguire la sincronizzazione. Per questa connessione vengono importati tutti i dati dalla data di inizio fino a oggi.

   * È possibile fare clic su Disabilita accesso a Learning Manager durante un’esecuzione in cui l’applicazione presenta un periodo di inattività durante la sincronizzazione.
   * Se fai clic su Abilita accesso a Learning Manager durante l’esecuzione, non si verificano interruzioni del servizio durante la sincronizzazione.

   Per automatizzare la sincronizzazione in modo che venga eseguita a intervalli di alcuni giorni, specifica il numero di giorni nel campo Ripeti n. giorni. La sincronizzazione assicura l’aggiornamento dell’account con la versione più recente dei resoconti e dei riepiloghi di Harvard ManageMentor.

1. È anche possibile fare clic su Stato esecuzione nel riquadro sinistro in qualsiasi momento per visualizzare il riepilogo di tutte le esecuzioni per questo connettore, in ordine cronologico. Puoi visualizzare la data di inizio e la durata della sincronizzazione, il tipo di sincronizzazione (se si tratta di una sincronizzazione su richiesta) e lo stato della sincronizzazione (se la sincronizzazione è in corso o è completa).

   >[!NOTE]
   >
   >Quando elimini e ricrei una connessione, le precedenti esecuzioni del connettore vengono visualizzate nuovamente. È possibile visualizzare tutte le esecuzioni effettuate prima di eliminare la connessione.

   Solo la sincronizzazione più recente può essere eseguita di nuovo.

   Affinché la sincronizzazione abbia esito positivo, assicurati che almeno uno dei seguenti file sia presente nella cartella FTP di Harvard ManageMentor:

   hmm12_metadata.xlsx: questo file fornisce i metadati del corso per il connettore Harvard ManageMentor. Attieniti alla convenzione di denominazione quando carichi il file.

   client_hmm12_20150125.xlsx: il feed utente per il connettore Harvard ManageMentor. Segue la convenzione di denominazione dei file **client_hmm12_yyyyMMdd.xlsx.**

   Consulta i due file di esempio feed utente e feed del corso per questo connettore:

   * [File dei metadati del corso per il connettore Harvard ManageMentor](assets/hmm12-metadata.xlsx)
   * [Feed utente per il connettore Harvard ManageMentor](assets/client-hmm12-20170304.xlsx)

## Connettore Workday {#workdayconnector}

Utilizzando il connettore Workday, è possibile integrare Learning Manager con il tenant Workday per automatizzare la sincronizzazione dei dati.

### Importa

#### Mapping attributi

L&#39;Amministratore di integrazione può scegliere le colonne Workday e mapparle agli attributi raggruppabili del Learning Manager corrispondente. Una volta completata, la mappatura viene utilizzata nelle successive importazioni di utenti. Può essere riconfigurata qualora l’Amministratore desiderasse una mappatura diversa per l’importazione degli utenti.

#### Importazione automatica degli utenti

Il processo di importazione degli utenti consente all’Amministratore Learning Manager di recuperare i dettagli dei dipendenti da Workday e importarli automaticamente in Learning Manager.

#### Filtraggio degli utenti

L’Amministratore Learning Manager può applicare filtri agli utenti prima di importarli. Ad esempio, può scegliere di importare tutti gli utenti della gerarchia sotto uno o più Manager specifici.

### Esporta

La funzione di esportazione delle abilità degli utenti consente di esportare automaticamente le abilità degli utenti in workday.

>[!NOTE]
>
>Non è possibile esportare le abilità di più account Learning Manager contemporaneamente utilizzando lo stesso account Workday.

#### Punti da notare

* Verifica che UUID, indirizzo e-mail e nome del dipendente siano univoci in più integrazioni Workday. Valori errati determineranno un errore di connessione.
* Il campo UUID, una volta compilato tramite Workday il attivo, non può essere eliminato da nessun client rivolto ad amministratore LMS. Se desideri modificare il valore, contatta il team di supporto o di onboarding di Adobe Learning Manager.
* L&#39;opzione User Purge potrebbe anche non funzionare poiché User Purge supporta solo 50 utenti da eliminare per esecuzione. Prestare estrema attenzione durante il caricamento degli utenti tramite gli UUID.

### Pianificazione {#Scheduling-1}

L’Amministratore può impostare le attività di pianificazione secondo i requisiti dell’organizzazione e gli utenti nell’applicazione Learning Manager vengono aggiornati in base alla pianificazione. Allo stesso modo, l’Amministratore di integrazione può pianificare l’esportazione delle abilità in modo tempestivo per consentire l’integrazione con un sistema esterno.  La sincronizzazione può essere eseguita su base giornaliera nell’applicazione Learning Manager.

### Configurazione del connettore Workday {#configureworkdayconnector}

>[!PREREQUISITES]
>
>Richiedi all&#39;amministratore Workday della tua organizzazione di creare un utente del sistema di integrazione (ISU) con le autorizzazioni definite nel documento di ISU_Permissions. Scarica una copia dal collegamento riportato di seguito.

[Scarica una copia della sicurezza dell&#39;utente del sistema di integrazione (ISU).](assets/isu-permissions-v1.pdf) Scopri il processo da seguire per integrare il connettore Workday con Learning Manager.

1. Nella home page di Learning Manager, posiziona il mouse sul riquadro di Workday. Viene visualizzato un menu. Fai clic sulla voce **[!UICONTROL Connetti]** nel menu.

   ![](assets/workday-tile.png)

   *Riquadro Workday*

1. Viene visualizzata una finestra di dialogo che richiede di inserire le credenziali per la nuova connessione. Prima di effettuare la connessione, compila i seguenti campi.

   * Nome connessione: assegna un nome alla connessione in base alle tue preferenze.
   * URL dell’host: l’Amministratore di integrazione può ottenere i dettagli relativi all’URL dell’host dall’Amministratore Workday corrispondente.
   * Tenant: il tenant è interno all&#39;azienda. L’Amministratore Workday fornisce i dettagli del tenant.
   * Nome utente e password: l&#39;amministratore Workday crea un utente di sistema integrato (ISU) con i privilegi di sicurezza richiesti e lo condivide con l&#39;amministratore di integrazione.

>[!NOTE]
>
>   Learning Manager utilizza la versione 40.1 dell&#39;API Workday.


![](assets/configure-connector.png)
*Configurazione del connettore Workday*

1. Fai clic su Connetti dopo avere inserito le informazioni in tutti i campi pertinenti.

   >[!NOTE]
   >
   >Puoi anche sincronizzare più connessioni Workday con il tuo account Learning Manager.

Nella pagina di panoramica, è possibile specificare il nome della connessione per l&#39;integrazione. Scegli l’azione da eseguire tra le seguenti opzioni:

* Importazione di utenti interni
* Esporta abilità utente - Configura una pianificazione
* Esporta abilità utente - Su richiesta

![](assets/overview.png)
*Panoramica di Workday*

### Importa

#### Mapping attributi {#MapAttributes-1}

È possibile utilizzare il connettore Workday per integrare Learning Manager e Workday e automatizzare la sincronizzazione dei dati. Puoi importare tutti gli utenti attivi di Workday in Learning Manager. Gli utenti possono essere importati da varie origini dati, tra cui FTP e Salesforce.

Prima di importare gli utenti, è necessario mappare gli attributi utente di Learning Manager e Workday. Nella pagina di panoramica, utilizza l’opzione Utenti interni in Importa per fornire il mapping degli attributi.

Inserisci le credenziali di Adobe Learning Manager nella colonna Adobe Learning Manager. Utilizza i menu a discesa per selezionare le credenziali corrette per le colonne in Workday.

>[!NOTE]
>
>Attualmente, Learning Manager supporta l’importazione di 69 attributi utente da Workday. Aggiungi altri attributi usando i campi attivi in Learning Manager.

![](assets/workday.png)
*Mapping attributi*

Seleziona la **casella di controllo Escludi lavoratori** contingenti per impedire l&#39;importazione dei lavoratori temporanei disponibili sotto un manager.

Workday presenta quattro livelli di gerarchia, mentre Learning Manager ne ha due. I quattro livelli in Workday sono: categoria profilo abilità, profilo abilità, categoria elemento abilità e elemento abilità. Il nome della tua abilità e il livello di Learning Manager sono mappati in Workday sotto l&#39;elemento competenza.

>[!NOTE]
>
>Puoi aggiungere altri attributi Workday. Contatta il CSAM per aggiungere gli attributi.

+++Elenco degli attributi Workday supportati

wd:User_ID
wd:Worker_ID
direttore
wd:Personal_Data.wd:Name_Data.wd:Preferred_Name_Data.wd:Name_Detail_Data.@wd:Formatted_Name
wd:Personal_Data.wd:Name_Data.wd:Legal_Name_Data.wd:Name_Detail_Data.@wd:Formatted_Name
wd:Personal_Data.wd:Name_Data.wd:Legal_Name_Data.wd:Name_Detail_Data.wd:Prefix_Data.wd:Title_Descriptor
wd:Personal_Data.wd:Name_Data.wd:Preferred_Name_Data.wd:Name_Detail_Data.wd:Prefix_Data.wd:Title_Descriptor
wd:Personal_Data.wd:Name_Data.wd:Preferred_Name_Data.wd:Name_Detail_Data.wd:First_Name
wd:Personal_Data.wd:Name_Data.wd:Preferred_Name_Data.wd:Name_Detail_Data.wd:Last_Name
wd:Personal_Data.wd:Name_Data.wd:Legal_Name_Data.wd:Name_Detail_Data.wd:First_Name
wd:Personal_Data.wd:Name_Data.wd:Legal_Name_Data.wd:Name_Detail_Data.wd:Last_Name
wd:Personal_Data.wd:Contact_Data.wd:Address_Data.0.@wd:Formatted_Address
wd:Personal_Data.wd:Contact_Data.wd:Address_Data.0.wd:Postal_Code
wd:Personal_Data.wd:Contact_Data.wd:Email_Address_Data.0.wd:Email_Address
wd:Personal_Data.wd:Contact_Data.wd:Address_Data.0.wd:Country_Region_Descriptor
wd:Personal_Data.wd:Contact_Data.wd:Phone_Data.0.@wd:Formatted_Phone
wd:Personal_Data.wd:Contact_Data.wd:Phone_Data.0.wd:Country_ISO_Code
wd:Personal_Data.wd:Contact_Data.wd:Phone_Data.0.wd:International_Phone_Code
wd:Personal_Data.wd:Contact_Data.wd:Phone_Data.0.wd:Phone_Number
wd:Personal_Data.wd:Primary_Nationality_Reference.wd:ID.1.$
wd:Personal_Data.wd:Gender_Reference.wd:ID.1.$
wd:Personal_Data.wd:Identification_Data.wd:National_ID.0.wd:National_ID_Data.wd:ID
wd:Personal_Data.wd:Identification_Data.wd:Custom_ID.0.wd:Custom_ID_Data.wd:ID
wd:User_Account_Data.wd:Default_Display_Language_Reference.wd:ID.1.$
wd:Role_Data.wd:Organization_Role_Data.wd:Organization_Role.0.wd:Organization_Role_Reference.wd:ID.1.$
wd:Employment_Data.wd:Worker_Job_Data.0.wd:Position_Data.wd:Position_Title
wd:Employment_Data.wd:Worker_Job_Data.0.wd:Position_Data.wd:Business_Title
wd:Employment_Data.wd:Worker_Job_Data.0.wd:Position_Data.wd:Business_Site_Summary_Data.wd:Name
wd:Employment_Data.wd:Worker_Job_Data.0.wd:Position_Data.wd:Business_Site_Summary_Data.wd:Address_Data.@wd:Formatted_Address
wd:Employment_Data.wd:Worker_Job_Data.0.wd:Position_Data.wd:Job_Classification_Summary_Data.0.wd:Job_Classification_Reference.wd:ID.1.$
wd:Employment_Data.wd:Worker_Job_Data.0.wd:Position_Data.wd:Job_Classification_Summary_Data.0.wd:Job_Group_Reference.wd:ID.1.$
wd:Employment_Data.wd:Worker_Job_Data.0.wd:Position_Data.wd:Work_Space__Reference.wd:ID.1.$
wd:Employment_Data.wd:Worker_Job_Data.0.wd:Position_Data.wd:Job_Profile_Summary_Data.wd:Job_Family_Reference.0.wd:ID.1.$
wd:Employment_Data.wd:Worker_Job_Data.0.wd:Position_Data.wd:Job_Profile_Summary_Data.wd:Job_Profile_Name
wd:Employment_Data.wd:Worker_Job_Data.0.wd:Position_Data.wd:Job_Profile_Summary_Data.wd:Job_Profile_Reference.wd:ID.1.$
wd:Employment_Data.wd:Worker_Job_Data.0.wd:Position_Data.wd:Business_Site_Summary_Data.wd:Address_Data.0.wd:Country_Reference.wd:ID.2.$
wd:Employment_Data.wd:Worker_Job_Data.0.wd:Position_Data.wd:Worker_Type_Reference.wd:ID.1.$
wd:Employment_Data.wd:Worker_Job_Data.0.wd:Position_Data.wd:Business_Site_Summary_Data.wd:Address_Data.0.@wd:Formatted_Address
wd:Employment_Data.wd:Worker_Job_Data.0.wd:Position_Data.wd:Job_Profile_Summary_Data.wd:Management_Level_Reference.wd:ID.1.$
wd:Employment_Data.wd:Worker_Status_Data.wd:Active
wd:Employment_Data.wd:Worker_Status_Data.wd:Active_Status_Date
wd:Employment_Data.wd:Worker_Status_Data.wd:Hire_Date
wd:Employment_Data.wd:Worker_Status_Data.wd:Original_Hire_Date
wd:Employment_Data.wd:Worker_Status_Data.wd:Ritirato
wd:Employment_Data.wd:Worker_Status_Data.wd:Retirement_Date
wd:Employment_Data.wd:Worker_Status_Data.wd:Terminated
wd:Employment_Data.wd:Worker_Status_Data.wd:Termination_Date
wd:Employment_Data.wd:Worker_Status_Data.wd:Termination_Last_Day_of_Work
wd:Organization_Data.wd:Worker_Organization_Data.0.wd:Organization_Data.wd:Organization_Code
wd:Organization_Data.wd:Worker_Organization_Data.0.wd:Organization_Data.wd:Organization_Name
wd:Organization_Data.wd:Worker_Organization_Data.0.wd:Organization_Data.wd:Organization_Type_Reference.wd:ID.1.$
wd:Organization_Data.wd:Worker_Organization_Data.0.wd:Organization_Data.wd:Organization_Subtype_Reference.wd:ID.1.$
wd:Qualification_Data.wd:Education.0.wd:School_Name
wd:Qualification_Data.wd:External_Job_History.0.wd:Job_History_Data.wd:Job_Title
wd:Qualification_Data.wd:External_Job_History.0.wd:Job_History_Data.wd:Company
wd:Management_Chain_Data.wd:Worker_Supervisory_Management_Chain_Data.wd:Management_Chain_Data.0.wd:Manager.Employee_ID
E-mail di lavoro principale
wd:Organization_Type_Reference_Cost_Center_ID
wd:Organization_Type_Reference_Cost_Center_Name
wd:Organization_Type_Reference_Company
wd:Organization_Subtype_Reference_Department
wd:Organization_Subtype_Reference_Division
wd:Universal_ID
wd:Integration_Field_Override_Data.3.wd:Valore
wd:Employment_Data.wd:Worker_Job_Data.0.wd:Position_Data.wd:Business_Site_Summary_Data.wd:Address_Data.0.wd:Country_Region_Descriptor
wd:Employment_Data.wd:Worker_Job_Data.0.wd:Position_Data.wd:Business_Site_Summary_Data.wd:Address_Data.0.wd:Country_Region_Reference.wd:ID.2.$
wd:Personal_Data.wd:Contact_Data.wd:Address_Data.0.wd:Comune

+++

### Esporta

Puoi esportare tutte le abilità utilizzate da un utente da Learning Manager in Workday. Vengono esportate solo tutte le abilità utente attive e Learning Manager non esporta le abilità ritirate. Puoi anche connettere più Learning Manager\
sullo stesso connettore Workday. Se i nomi delle abilità sono gli stessi in due account Learning Manager, vengono mappati alla stessa abilità in Workday. Prima di aggiornare l&#39;abilità in Workday, nel caso in cui due account Learning Manager utilizzino lo stesso account Workday, è consigliabile aggiornare i nomi delle abilità in tutti gli account Learning Manager.

+++Abilità utente - Configura

Questa opzione consente di pianificare l’estrazione del report. Assicurati che la casella di controllo Esporta abilità utente usando questa connessione sia attiva. Seleziona la casella di controllo Abilita pianificazione e specifica la data e l’ora di inizio. Puoi anche specificare l’intervallo desiderato per la generazione e l’invio del report. Seleziona la casella di controllo Abilita pianificazione e inserisci Data di inizio, Ora e Ripeti dopo “n” numero di giorni. Una volta completata l’operazione, fai clic su Salva.

![](assets/configure-schedule.png)
*Configurazione del report sulle abilità degli utenti*

+++

+++Abilità utente - Su richiesta

È possibile specificare la data di inizio ed esportare il report utilizzando questa opzione. Il report viene estratto a partire dalla data inserita fino a oggi. Immetti la data da cui desideri iniziare a generare il report e fai clic su Esegui.

![](assets/on-demand-report.png)
*Report sulle abilità degli utenti su richiesta*

+++

+++Abilità utente - Stato esecuzione

Qui puoi visualizzare il riepilogo di tutte le attività e ottenere il report sullo stato. È possibile scaricare i report degli errori facendo clic sul collegamento al report degli errori.

![](assets/execution-status.png)
*Report di esecuzione abilità utente*

+++

## Connettore miniOrange {#miniorangeconnector}

Utilizzando il connettore miniOrange, è possibile integrare Learning Manager con il tenant miniOrange per automatizzare la sincronizzazione dei dati.

### Importa

#### Mapping attributi

L&#39;Amministratore di integrazione può scegliere gli attributi miniOrange e mapparli agli attributi raggruppabili del corrispondente Learning Manager. Una volta completata, la mappatura viene utilizzata nelle successive importazioni di utenti. Può essere riconfigurata qualora l’Amministratore desiderasse una mappatura diversa per l’importazione degli utenti.

#### Importazione automatica degli utenti

Il processo di importazione degli utenti consente all&#39;amministratore di Learning Manager di recuperare i dettagli dei dipendenti da miniOrange e importarli automaticamente in Learning Manager.

#### Filtraggio degli utenti

L’Amministratore Learning Manager può applicare filtri agli utenti prima di importarli. Ad esempio, può scegliere di importare tutti gli utenti della gerarchia sotto uno o più Manager specifici.

Per configurare il connettore miniOrange, contatta il team CSM di Learning Manager.

### Configurazione del connettore miniOrange {#configureminiorangeconnector}

1. Nella home page di Learning Manager, passa il mouse sopra la scheda/anteprima miniOrange. Viene visualizzato un menu. Fai clic sull&#39;opzione  **[!UICONTROL Connetti]** nel menu.

   ![](assets/miniorange-tile.png)

   *Riquadro connettore miniOrange*

1. Fai clic su **[!UICONTROL Connetti]** per stabilire una nuova connessione. Viene visualizzata la pagina del connettore miniOrange. Inserisci i dettagli dell’account che desideri mappare.

   ![](assets/establish-connection.png)

   *Creare una connessione*

1. Se desideri importare l&#39;utente miniOrange direttamente come utente interno di Learning Manager, utilizza l&#39;opzione **[!UICONTROL Importa utenti]** interni.

   ![](assets/import-users.png)

   *Importare utenti interni*

1. Nella pagina di mappatura, sul lato sinistro puoi vedere le colonne di Learning Manager e sul lato destro puoi vedere le colonne miniOrnage. Seleziona il nome appropriato per la colonna, mappato al nome della colonna del responsabile dell&#39;apprendimento.

   ![](assets/map-attributes.png)

   *Mapping attributi*

1. Per visualizzare e modificare l’origine dati, fai clic, come Amministratore, su **[!UICONTROL Impostazioni > Origine dati]**.

   La fonte miniOrange stabilita verrebbe elencata. Per modificare il filtro, fai clic su **[!UICONTROL Modifica]**.

   ![](assets/data-source.png)

   *Visualizzare e modificare un&#39;origine dati*

1. Riceverai una notifica al completamento dell’importazione. Per visualizzare o modificare il registro di importazione, fai clic su **[!UICONTROL Utenti > Registro importazione.]**

<!-- #### Delete a connection {#deleteaconnection}

To delete an established  miniOrange  connection, follow these steps. -->

## Connettore Zoom {#zoom-connector}

Puoi integrare Learning Manager con i connettori Zoom e usarli per tenere corsi.  Il connettore consente di organizzare riunioni/lezioni in videoconferenza con gli Allievi.

Per configurare e utilizzare il connettore, attieniti alla seguente procedura.

1. Nella home page di Learning Manager , passa il mouse sopra la miniatura di Zoom. Viene visualizzato un menu. Fai clic sull&#39;opzione  **[!UICONTROL Connetti]** dal menu.

   <!-- ![](assets/connectors.png)

   *Zoom connector tile* -->

1. Si apre la pagina del connettore Zoom. Inserisci i dettagli del tuo account nei rispettivi campi per integrare e sincronizzare il feed utente. Per i dettagli, rivolgiti all’Amministratore dell’account del connettore.

   <!-- ![](assets/bluejeans-connecotrpage.png)
   *Connect to BlueJeans/ Zoom* -->

   >[!NOTE]
   >
   >Come studente, mentre abiliti il connettore, utilizza lo stesso id e-mail utilizzato per l’account Learning Manager per abilitare i feed utente in Learning Manager.

1. Una volta stabilita la connessione, crea come autore un corso VC con Zoom come sistema di conferenza.

   <!-- ![](assets/vc.jpg)
   
   *Create a VC course* -->

1. Amministratori, Manager e Allievi possono iscrivere gli Allievi al corso creato. Al momento dell’iscrizione, l’Allievo riceve un’e-mail. L’Allievo può accedere al proprio account Learning Manager per visualizzare i dettagli del programma e seguire il corso.
1. Al termine del corso, il rapporto sul completamento viene inviato a Learning Manager. L’Amministratore può visualizzare il report sul completamento per controllare la partecipazione e il punteggio degli Allievi.

   ![](assets/attendence-and-scoringreport.png)
   *Report su presenza e punteggio*

### Creare un&#39;app OAuth da server a server di zoom

Quando crei un&#39;app OAuth Zoom da server a server da utilizzare in Adobe Learning Manager, devi aggiungere gli ambiti richiesti da Adobe Learning Manager durante la creazione della connessione.

Adobe Learning Manager richiede gli ambiti sottostanti e gli ambiti devono essere selezionati nell’app OAuth.

* Visualizza tutte le riunioni degli utenti `/meeting:read:admin`
* Visualizza e gestisci tutte le riunioni degli utenti `/meeting:write:admin`
* Visualizzare i dati del report `/report:read:admin`
* Visualizza tutte le informazioni utente `/user:read:admin`
* Visualizzare le informazioni degli utenti e gestirli `/user:write:admin`

## Connettore Box {#boxconnector}

Usando il connettore Box, è possibile integrare Learning Manager con sistemi esterni arbitrari per l’automazione della sincronizzazione dei dati. I sistemi esterni dovrebbero esportare i dati in formato CSV e inserirli nella cartella appropriata dell&#39;account Box di Learning Manager. Le funzionalità del connettore Box sono le seguenti:

È inoltre possibile utilizzare il connettore FTP per la migrazione, l&#39;importazione e l&#39;esportazione dei dati. Per ulteriori informazioni, consulta [Connettore FTP Learning Manager.](connectors.md#main-pars_header_1427405935)

### Importazione di dati {#DataImport-1}

Il processo di importazione degli utenti consente all’Amministratore Learning Manager di recuperare i dettagli dei dipendenti dal servizio Box di Learning Manager e importarli automaticamente in Learning Manager. Utilizzando questa funzione, è possibile integrare più sistemi inserendo il file CSV generato da tali sistemi nelle apposite cartelle degli account Box. Learning Manager preleva i file CSV, li unisce e importa i dati in base alla pianificazione Fai riferimento alla funzione di pianificazione per ulteriori informazioni.

**Mapping attributi**

L’Amministratore di integrazione può scegliere le colonne di CSV e mapparle agli attributi raggruppabili di Learning Manager. L&#39;operazione di mappatura viene eseguita una sola volta. Una volta completata, la mappatura viene utilizzata nelle successive importazioni di utenti. Può essere riconfigurata qualora l’Amministratore desiderasse una mappatura diversa per l’importazione degli utenti.

## Esportazione dati {#dataexport}

La funzione di esportazione dei dati consente di esportare le abilità degli utenti e le trascrizioni degli allievi in un percorso Box per l’integrazione con qualsiasi sistema di terze parti.

## Report di pianificazione {#schedulereports}

L’Amministratore può impostare le attività di pianificazione secondo i requisiti dell’organizzazione e gli utenti nell’applicazione Learning Manager vengono aggiornati in base alla pianificazione. Allo stesso modo, l’Amministratore di integrazione può pianificare l’esportazione delle abilità in modo tempestivo per consentire l’integrazione con un sistema esterno.  La sincronizzazione può essere eseguita su base giornaliera nell’applicazione Learning Manager.

## Configurazione del connettore Box {#configureboxconnector}

Scopri il processo da seguire per integrare il connettore Box con Learning Manager.

1. Nella home page di Learning Manager, passa il mouse sopra la scheda/l&#39;anteprima di Box. Viene visualizzato un menu. Fai clic sulla voce Connetti nel menu.

   ![](assets/screen-shot-2017-10-25at54426pm.png)

   *Connetti a Box*

1. Viene visualizzata una finestra di dialogo che richiede di inserire l’id e-mail. Fornisci l&#39;ID e-mail del responsabile della gestione dell&#39;account Learning Manager Box per l&#39;organizzazione. Fai clic su Connetti dopo aver fornito l&#39;id e-mail.
1. Learning Manager invia all’utente un’e-mail con la richiesta di reimpostare la password prima di accedere a Box per la prima volta. L&#39;utente deve reimpostare la password e utilizzarla per accedere all&#39;account Box per Learning Manager.

   >[!NOTE]
   >
   >È possibile creare un solo account Box Learning Manager per un determinato account Learning Manager.

   Nella pagina di panoramica, è possibile specificare il nome della connessione per l&#39;integrazione. Scegli l&#39;azione da eseguire tra le seguenti opzioni:

   * Importazione di utenti interni
   * Importa report di attività xAPI
   * Esporta abilità utente - Configura una pianificazione
   * Esporta abilità utente - Su richiesta
   * Esporta trascrizione Allievo - Configura una pianificazione
   * Esporta trascrizione Allievo - Su richiesta

## Importa

+++Utente interno

L’opzione di importazione utente interno consente di pianificare automaticamente la generazione del report relativo all’importazione dell’utente. I report generati vengono inviati come file .CSV.

+++

Attributi +++Map

Una volta stabilita la connessione, puoi mappare le colonne di file CSV inserite nella cartella Box agli attributi corrispondenti di Learning Manager. Questo passaggio è obbligatorio.

1. Nella pagina Mapping attributi, sul lato sinistro puoi visualizzare le colonne previste da Learning Manager e sul lato destro puoi vedere i nomi delle colonne CSV. Inizialmente, sul lato destro viene visualizzata una casella di selezione vuota. Importa un qualsiasi modello CSV facendo clic su Scegli file.
1. Il passaggio precedente consente di compilare l’elenco a discesa di selezione sulla destra con tutti i nomi delle colonne CSV. Seleziona il nome appropriato per la colonna, mappato al nome della colonna del responsabile dell&#39;apprendimento.

   *Il campo Manager deve essere mappato a un campo di tipo indirizzo e-mail. Prima di poter utilizzare il connettore è necessario mappare tutte le colonne.*

1. Fai clic su Salva dopo aver completato la mappatura.

   Il connettore è ora pronto per l’uso. L’account configurato viene visualizzato come origine dati nell’app Amministratore per consentire all’Amministratore di pianificare l’importazione o per la sincronizzazione su richiesta.

+++

Report attività +++xAPI

L’opzione Report di attività xAPI consente di generare l’importazione di istruzioni xAPI dai servizi di terze parti. I file vengono salvati come file .CSV e poi convertiti in istruzioni xAPI durante l’importazione in Learning Manager.

+++

+++Configurazioni necessarie per importare xAPI

1. Dalla pagina di configurazione, seleziona una configurazione esistente disponibile nell&#39;elenco delle configurazioni per importare le istruzioni xAPI dal file CSV. Fare clic su modifica o su un **collegamento a una nuova configurazione** per passare alla pagina Importa istruzioni xAPI-Configurazione-File di origine.

   ![](assets/artboard-11-2x.png)

   *Modificare o aggiungere una nuova configurazione*

   **Configurazione**

   * Nella pagina Configurazione importazione-Origini, compila i campi Nome e Nome file di origine. Il nome del file di origine deve corrispondere al nome del file fornito nel percorso FTP della cartella.
   * Fai clic su **[!UICONTROL Salva]** per salvare le modifiche.

   ![](assets/configurations-main2x.png)

   *Configurare*

   **Filtro**

   * Nel riquadro a sinistra, fai clic su Filtro
   * Nella pagina Configurazione importazione-Filtro, compila il campo Nome e condizioni per filtrare i record. Fai clic su Aggiungi nuovo filtro per aggiungere un altro filtro. È possibile salvare o eliminare un filtro facendo clic sull’opzione Salva o Elimina nella colonna Azioni.

   ![](assets/box-filter-2x.png)

   *Filtro*

   **Mappatura**

   * Nel riquadro a sinistra, fai clic su Mappatura.
   * Nella parte sinistra della pagina Configurazione importazione-Mappatura, sono visualizzati i nomi dei percorsi JSON xAPI che devono essere mappati ai nomi delle colonne CSV.
   * Per impostazione predefinita, i tre nomi dei percorsi JSON che devono essere mappati ai nomi delle colonne CSV sono **actor.mbox**, **verb.id** e **object.id**. È possibile aggiungere altri campi da mappare facendo clic su Aggiungi nuova mappatura.
   * Seleziona il tipo di nome colonna che stai mappando al nome del percorso JSON (che si tratti di una stringa, di un numero, di un valore booleano o del tipo di data).
   * Una volta completata la mappatura, fai clic su Salva. L’importazione di xAPI può ora essere eseguita in base a una pianificazione o su richiesta.

   ![](assets/box-mapping-2x.png)
   *Mappatura*

1. Nel riquadro a sinistra, fai clic su **[!UICONTROL Configura pianificazione]**. Fai clic su Abilita pianificazione per pianificare l’importazione di istruzioni xAPI. Inserisci l’ora e la data di inizio e specifica la frequenza della pianificazione di importazione xAPI in giorni. Ad esempio, pianificando l’importazione xAPI in modo che venga eseguita ogni 3 giorni.

   ![](assets/configure-schedulebox2x.png)
   *Importa istruzioni xAPI - Configura pianificazione*

1. Nel riquadro a sinistra, fai clic su **[!UICONTROL Esecuzione]** su richiesta.

   ![](assets/box-on-demand-2x.png)
   *Importare istruzioni xAPI - Su richiesta*

1. Nel riquadro a sinistra, fai clic su **[!UICONTROL Stato esecuzione]** per visualizzare il riepilogo di tutte le esecuzioni per questo connettore, in ordine cronologico. È possibile visualizzare la data di inizio e la durata dell’importazione xAPI, il tipo di importazione (su richiesta o pianificata) e lo stato dell’importazione (se l’importazione xAPI è in corso, è completata o non è riuscita).

   ![](assets/box-execution-status2x.png)
   *Importa istruzioni xAPI - Stato esecuzione*

+++

+++Utilizzo del connettore Box di Learning Manager

1. I file CSV provenienti da sistemi esterni devono essere posizionati nel seguente percorso:

   `code $OPERATION$/$OBJECT_TYPE$/$SUB_OBJECT_TYPE$/data.csv`

   >[!NOTE]
   >
   >Nella versione di luglio 2016, è consentita solo l&#39;importazione di utenti. Pertanto, per utilizzare il connettore Box, assicurati che i file CSV si trovino nella seguente cartella:

   `code Home/import/user/internal/*.csv`

1. Il connettore Box prende tutte le righe dai file CSV. È importante che la riga corrispondente a un utente in un file CSV non appaia in nessun altro file CSV.
1. Tutti i CSV devono contenere le colonne specificate nella mappatura.
1. Tutti i CSV richiesti devono essere presenti nella cartella prima dell&#39;inizio del processo.

Durante l’importazione degli utenti in Learning Manager, l’Amministratore deve sapere anche in che modo gli utenti vengono gestiti in Learning Manager. Per ulteriori informazioni, consulta la Guida](migration-manual.md#usermanagement) alla [gestione utenti.

+++

## Esporta

+++Competenze

Sono disponibili due opzioni per esportare i report sulle abilità degli utenti.

Abilità utente - Su richiesta: questa opzione consente di specificare la data di inizio ed esportare il report. Il report viene estratto dalla data inserita fino a oggi

**[!UICONTROL Abilità utente - Configura]**: questa opzione consente di pianificare l’estrazione del report. Seleziona la casella di controllo Abilita pianificazione e specifica la data e l’ora di inizio. Puoi anche specificare l’intervallo desiderato per la generazione e l’invio del report.

+++

Per aprire la cartella di esportazione in cui si trovano i file esportati nel percorso di Box, apri il collegamento alla cartella di Box fornito nella pagina delle abilità utente, come mostrato di seguito.

I file esportati automaticamente si trovano nel percorso **Home/export/&#42;Box_location&#42;**

I file esportati automaticamente sono disponibili con il titolo **skill_achievements_&#42;date from &#42;_to_&#42;date to&#42;.csv**

>[!NOTE]
>
>Il cliente gestisce le autorizzazioni di accesso e il contenuto nella cartella Box condivisa dal team di Learning Manager.  Anche il contenuto della cartella sarebbe fisicamente memorizzato nella regione di Francoforte.

### Supporto per campi CSV manuali {#Supportformanualcsvfields-1}

Durante l’importazione dei dati utente tramite Box, un Amministratore deve mappare tutti i campi attivi presenti nel sistema sul campo corrispondente nel csv.

Questo è obbligatorio per tutti i campi csv. attivi. Per i campi attivi manuali, l’Amministratore dell’integrazione può selezionare l’opzione **DontImportFromSource**.

Selezionando questa opzione, i valori dei campi attivi manuali non vengono riempiti mediante l’importazione di csv. I valori forniti dall’Allievo restano intatti.

>[!NOTE]
>
>Durante la mappatura, se l&#39;opzione **DontImportFromSource** è selezionata per il campo attivo csv, questo campo verrà eliminato dal sistema.

![](assets/box-connector-foractivefields.png)
*Connettore Box per i campi attivi*

>[!NOTE]
>
>Tutti i file CSV elaborati verranno eliminati per qualsiasi connettore o migrazione che utilizza FTP/Box come origine dati.
>
>Il file CSV per i connettori di contenuto, ad esempio LinkedIn, verrà eliminato dopo sette giorni, mentre il file CSV per gli utenti di importazione verrà eliminato immediatamente.

## Connettore LinkedIn Learning {#linkedinlearningconnector}

Il connettore LinkedIn Learning è utilizzato dai clienti enterprise di LinkedIn.com che desiderano far seguire i corsi ai loro allievi da Learning Manager. È possibile configurare il connettore per recuperare periodicamente corsi con la tua chiave API. Quando un corso viene creato in Learning Manager, gli utenti possono ricercarlo e seguirlo. Sarà quindi possibile seguire i progressi dell’Allievo in Learning Manager.

>[!NOTE]
>
>Riceverai gli ID LO univoci per tutti i corsi importati dal connettore LinkedIn Learning ad Adobe Learning Manager.

>[!NOTE]
>
>Il tempo di apprendimento impiegato per i corsi di LinkedIn Learning viene comunicato dalla piattaforma LinkedIn content/LinkedIn alla piattaforma di apprendimento Learning Manager. Se LinkedIn Learning non invia il tempo di apprendimento impiegato, non sarà possibile registrarlo sulla nostra piattaforma di apprendimento. In tal caso, il tempo impiegato per l&#39;apprendimento visualizzato da Learning Manager è pari a zero.

### Configurazione delle impostazioni nel portale di Linkedln Learning {#configuresettingsinlinkedlnlearningportal}

1. Accedi al sistema LMS di Linkedln Learning come Amministratore.
1. Fai clic su **[!UICONTROL Amministratore]** nella parte superiore del pannello di navigazione.
1. Fai clic sulla scheda **[!UICONTROL Impostazioni]** nella finestra successiva.
1. Seleziona **[!UICONTROL Integrazione]** riproduzione dal pannello di navigazione sinistro, quindi fai clic sulla **scheda Integrazione** .
1. Fai clic su **[!UICONTROL Impostazioni]** di avvio dei contenuti LMS per espanderne le impostazioni.
1. Aggiungi i tre nomi host riportati di seguito: **learningmanager.adobe.com**, **learningmanagerlrs.adobe.com**, **cpcontents.adobe.com**
1. Seleziona **[!UICONTROL Abilita integrazione AICC]**.

   ![](assets/linkedin-learning.png)

   *Configurazione LinkedIn Learning*

### Configurazione del connettore LinkedIn Learning {#configurelinkedinlearningconnector}

1. Nel dashboard dell&#39;Amministratore di integrazione, fai clic su [!UICONTROL LinkedIn Learning]. Vengono visualizzate le opzioni Guida introduttiva, Connetti e Gestione connessioni.
1. Se devi configurare il connettore LinkedIn Learning per la prima volta, fai clic su [!UICONTROL Connetti].

   <!--Configure the Exavault FTP account before you configure this connector.

   ![](assets/configure.jpg)
   *Configure connection*-->

1. Nella pagina di connessione, specifica un nome per il connettore. Inserisci appkey e chiave privata per la connessione.

   >[!NOTE]
   >
   >L&#39;amministratore aziendale può generare una nuova applicazione dal portale di amministrazione di LinkedIn Learning per ottenere l&#39;appkey e la chiave segreta.

1. Fai clic su **[!UICONTROL Salva]**.

   La configurazione viene salvata e viene aggiunta la connessione LinkedIn Learning per l’account. È ora possibile fare clic su **[!UICONTROL Gestione connessioni]** nella home page e modificare la configurazione in qualsiasi momento.

1. Se disponi già di una connessione configurata, fai clic su **[!UICONTROL Gestione connessioni]** per visualizzare tutte le connessioni.

   >[!NOTE]
   >
   >Prima di configurare il connettore è necessario abilitare la funzione di migrazione per l’account.

1. Fai clic sulla connessione da modificare.
1. Nel riquadro a sinistra, fai clic su Configura. Effettua una delle seguenti operazioni:

   * Visualizza o modifica i dettagli del tuo account e la pianificazione della sincronizzazione da questa finestra. Seleziona la **[!UICONTROL casella di controllo Abilita connessione]** se desideri abilitare questo account.
   * Fai clic su **[!UICONTROL Modifica]** e modifica le tue credenziali. Per annullare gli aggiornamenti a questo campo, fai clic su Ripristina.
   * Fai clic su **[!UICONTROL Abilita pianificazione]** per pianificare la sincronizzazione. Inserisci l’ora e la data di inizio e specifica la frequenza della pianificazione di sincronizzazione in giorni. Ad esempio, puoi abilitare la sincronizzazione ogni tre giorni.

   Fai clic su **[!UICONTROL Salva]** per salvare le modifiche.

1. Nel riquadro a sinistra, fai clic su **[!UICONTROL Esecuzione]** su richiesta. Questa opzione consente di importare i feed degli utenti e altri dati rilevanti da LinkedIn. Immetti la data di inizio per l&#39;esecuzione su richiesta e fai clic su Esegui per eseguire la sincronizzazione. Vengono importati tutti i dati dalla data di inizio fino a oggi.

   * Puoi fare clic su **[!UICONTROL Disabilita accesso]** a Learning Manager durante un&#39;esecuzione in cui l&#39;applicazione presenta un periodo di inattività durante la sincronizzazione.
   * Se si fa clic su **[!UICONTROL Abilita accesso]** a Learning Manager durante l&#39;esecuzione, non si verificano interruzioni del servizio durante la sincronizzazione.

   ![](assets/ondemandexecution.jpg)

   *Esecuzione su richiesta del report*

1. È anche possibile fare clic su Stato esecuzione nel riquadro sinistro in qualsiasi momento per visualizzare il riepilogo di tutte le esecuzioni per questo connettore, in ordine cronologico. Puoi visualizzare la data di inizio e la durata della sincronizzazione, il tipo di sincronizzazione (se si tratta di una sincronizzazione su richiesta) e lo stato della sincronizzazione (se la sincronizzazione è in corso o è completa).

   ![](assets/executionstatus.jpg)

   *Stato di esecuzione del report*

   >[!NOTE]
   >
   >Quando elimini e ricrei una connessione, le precedenti esecuzioni del connettore vengono visualizzate nuovamente. È possibile visualizzare tutte le esecuzioni effettuate prima di eliminare la connessione.

   Solo la sincronizzazione più recente può essere eseguita di nuovo.

### Filtrare i contenuti di LinkedIn Learning {#filter-linkedin}

Esistono filtri nei connettori di LinkedIn che consentono di separare i contenuti in base alle librerie di LinkedIn Learning. Inoltre, puoi filtrare i contenuti in base alla lingua e alla libreria e importare solo i corsi nelle lingue richieste. Una volta importato, il contenuto viene separato in più cataloghi in base alla configurazione di importazione.

I filtri sono i seguenti:

**Filtra il corso usando:** consente di filtrare un sottoinsieme di corsi da LinkedIn in Learning Manager.

* **In base alla lingua**

![](assets/filter-language.png)

*Filtra per lingua*

* **Basato sulla libreria di LinkedIn Learning**

![](assets/filter-catalog.png)

*Filtra per catalogo*

**Importa i corsi in**

![](assets/iport-training.png)
*Importare la formazione nei cataloghi*

**Importa tag**

**Tag personalizzato** è un tipo di tag che puoi usare per aggiungere tag personalizzati ai corsi di LinkedIn Learning. Puoi aggiungere tutti i tag che desideri, separati da virgole.

![](assets/add-custom-tags.png)

*Aggiungere tag personalizzati*

Il contenuto viene salvato solo dopo la migrazione. I contenuti verranno salvati nei rispettivi cataloghi.

## Connettore Power BI {#powerbiconnector}

>[!NOTE]
>
>Learning Manager supporta l’integrazione solo con la licenza commerciale di Microsoft Power BI. Non si integra con Microsoft Power BI nel cloud standard.

Puoi usare l&#39;integrazione con questo connettore per sfruttare gli account Power BI esistenti per analizzare e visualizzare i dati di apprendimento da Learning Manager in Power BI. Durante la configurazione, l’Amministratore dell’integrazione può configurare il proprio spazio di lavoro di Power BI affinché sia popolato in modo incrementale con due serie di dati live: trascrizione dell’Allievo e report sulle abilità dell’utente. È quindi possibile utilizzare tutte le funzionalità e il potenziale di Power BI per sviluppare e distribuire dashboard personalizzati come desiderato nelle proprie organizzazioni.

### Configurazione del connettore {#configuringtheconnector}

Per configurare il connettore, nella **[!UICONTROL pagina Connettori]** passa il mouse sopra il riquadro Power **[!UICONTROL BI]** e fai clic su **[!UICONTROL Connetti]**. Si apre la pagina Power BI. Per stabilire una connessione, specifica id client dell’app, segreto del client dell’app, nome del tenant e id dell’area di lavoro (opzionale). Per ottenere le credenziali, attieniti alla seguente procedura.

![](assets/power-bi-configurepage.png)

*Configurare il connettore Power BI*

1. Avvia <https://app.powerbi.com/embedsetup>.
1. Fai clic su **[!UICONTROL Incorpora per la tua organizzazione]** e accedi al tuo account Microsoft.
1. Immetti il nome dell&#39;app.
1. Nella sezione Tipo di app seleziona l&#39;opzione App Web lato server.
1. Nella sezione URL di **[!UICONTROL reindirizzamento]** , seleziona l&#39;opzione **Usa un URL** personalizzato (scegli questa opzione se conosci l&#39;URL dell&#39;applicazione di destinazione). Immetti il seguente URL:

   `https://learningmanager.adobe.com/ctr/app/azure/_callback` (aggiornare il dominio in base all&#39;ambiente)

1. Nel campo URL personale, inserisci il seguente URL: `https://learningmanager.adobe.com/`
1. Nella sezione delle autorizzazioni, seleziona **Leggi tutti i set** di dati e **Leggi e scrivi tutti i set** di dati.

   Acquisizione del tenant: contatta l’Amministratore di Power BI per fornire il nome del tenant.

   Acquisizione dell’Id dell’area di lavoro: la creazione dell’area di lavoro è consentita solo agli utenti di Power BI Pro. È possibile creare un’area di lavoro in Power BI e ottenere l’Id dall’URL.

1. Fai clic su **[!UICONTROL Registra app]** e memorizza id client e chiave privata client.

>[!NOTE]
>
>Se vuoi autorizzare nuovamente la connessione, devi creare un&#39;altra Power App e specificare l&#39;URL di reindirizzamento con il nuovo marchio.

Puoi esportare le trascrizioni degli Allievi, le abilità degli utenti e il report di attività xAPI usando lo stesso metodo. Seleziona le trascrizioni degli allievi/le abilità degli utenti nel pannello di sinistra. Si apre la pagina di esportazione.

Seleziona la casella di controllo che consente di **[!UICONTROL abilitare l’esportazione di abilità utente/trascrizioni allievi usando questa connessione]**. Salva le modifiche.

**Configura pianificazione**: se desideri pianificare l’estrazione del report. Seleziona la casella di **[!UICONTROL controllo Abilita pianificazione]** e specifica la data e l&#39;ora di inizio. Puoi anche specificare l’intervallo desiderato per la generazione e l’invio del report.

![](assets/power-bi-configureuserskillpage.png)

*Configurazione dell&#39;esportazione per pianificare il report*

**Esportazione su richiesta:** è possibile specificare la data di inizio ed esportare il report utilizzando l&#39;opzione . Il report viene estratto a partire dalla data inserita fino a oggi.

![](assets/power-bi-userskillondemandpage.png)

*Esportazione su richiesta*

I dati esportati possono essere visualizzati effettuando l’accesso all’account Power BI. I dati esportati sono elencati nell’opzione set di dati.

### Esportazione dei report di attività xAPI in Learning Manager {#exportxapiactivityreportsincaptivateprime}

Nella pagina delle funzionalità di PowerBI-xAPI fare clic su **[!UICONTROL Esporta report]** attività xAPI.

![](assets/powerbi-dashboard.png)
*PowerBI - Esporta report attività xAPI*

Nel riquadro a sinistra, seleziona **Configurazione** e procedi come indicato di seguito:

* Compila il campo percorso JSON corrispondente al nome della colonna e al tipo di stringa.
* Per aggiungere ulteriori percorsi JSON, fai clic su **[!UICONTROL Aggiungi]**.
* È possibile modificare le voci nei campi percorso JSON facendo clic su **[!UICONTROL Modifica]**.
* Fai clic su **[!UICONTROL Salva]** per salvare le modifiche.

**Configura pianificazione**

Nel riquadro a sinistra, fai clic su **[!UICONTROL Configura pianificazione]** e procedi come indicato di seguito:

* Fai clic su Abilita esportazione di istruzioni xAPI utilizzando questa connessione.
* Seleziona la casella di controllo **[!UICONTROL Abilita pianificazione]** e specifica la data e l’ora di inizio. Puoi anche specificare l’intervallo di giorni desiderato per la ripetizione e l’invio dell’esportazione.
* Fai clic sul pulsante **[!UICONTROL Salva]** per salvare le impostazioni di pianificazione della configurazione.

![](assets/configure-schedule.png)
*Esportazione xAPI Configura pianificazione*

**Su richiesta**

Nel riquadro a sinistra, fai clic su **[!UICONTROL Su richiesta]** e specifica la data di inizio nella pagina Esporta istruzioni xAPI-Su richiesta.

![](assets/on-demand-2.png)
*Esportazione xAPI su richiesta*

Tutti i dati esportati verranno inseriti in un set di dati creato da Adobe nel tuo account Power BI.

L’esportazione xAPI in Power BI non riesce se alcune delle istruzioni xAPI in LRS non hanno un percorso JSON configurato per l’esportazione. Per le istruzioni xAPI in cui il percorso json non è disponibile, il valore della costante N/D deve essere aggiunto e visualizzato in Power BI.

**Stato di esecuzione**

Seleziona **Stato esecuzione** per visualizzare il riepilogo di tutte le attività in ordine cronologico. Il segnale di avvertimento indica guasti durante l’esecuzione. Puoi scaricare i rapporti degli errori come **CSV** facendo clic sul collegamento al rapporto degli errori.

![](assets/execution-status.png)
*Stato di esecuzione dell&#39;esportazione xAPI*

### Report unificati {#unified-reports}

Learning Manager offre un modo per creare l&#39;esportazione con combinazioni di report come Dati utente, Trascrizione Allievo, Gamification, Report feedback e altro ancora, come un unico set di dati per Power BI.

Questo consente agli utenti di Power BI di unire i dati di più report per creare analisi e visualizzazioni di forte impatto in Power BI.

![](assets/unified-power-bireports.png)
*Report Power BI unificati*

**Esportazione su richiesta**

Specificare la data di inizio e di fine ed esportare il report utilizzando questa opzione. Il report viene estratto per l’intervallo di date specificato.

![](assets/on-demand-export.png)
*Esportazione su richiesta*

**Esportazione pianificata**

Se desideri pianificare l’estrazione del report, seleziona la casella di controllo **Abilita pianificazione** e specifica la data e l’ora di inizio. Puoi anche specificare l’intervallo desiderato per la generazione e l’invio del report.

![](assets/configure-schedule.png)
*Configurare la pianificazione*

Puoi inoltre esportare i report sulla formazione in Power BI.

Puoi esportare i report sulla formazione in Power BI come parte della funzione Report unificati.

Il report sulla formazione presenta due campi aggiuntivi:

* Numero di utenti che hanno condiviso feedback su un corso
* Valutazione a stelle media per un corso

### Filtrare lo stato delle Trascrizioni Allievi {#lt-status}

Nella sezione Report unificati di una connessione Power BI, è presente un’opzione che consente di esportare le Trascrizioni Allievi in base allo stato degli oggetti di apprendimento.

* **Seleziona tutto:** consente di esportare tutti i record o le attività a livello di modulo nell’intervallo di date specificato.
* **Completati:** consente di esportare tutti i record che risultano completati nell’intervallo di date.
* **In corso:** consente di esportare tutti i record con lo stato In corso.
* **Non avviato:** escludi i record registrati nell&#39;intervallo di date specificato, ma che non sono stati avviati al momento della generazione del report.

* **Annullati:** consente di includere tutti i record annullati nell’intervallo di date.

![](assets/lt-filters.png)
*Stato del filtro delle trascrizioni di apprendimento*

Puoi esportare l’elenco necessario e quindi utilizzare Power BI per analizzare il report in un secondo momento.

### Download dei modelli di Power BI {#template}

Learning Manager fornisce anche modelli di Power BI già pronti. Questi modelli offrono migliori funzionalità di analisi agli amministratori degli account di Adobe Learning Manager.

È possibile scaricare i modelli, esportare i report pertinenti e tracciare facilmente i report utilizzando questi modelli disponibili.

![](assets/download-power-bi-template.png)
*Scaricare i modelli di Power BI*

Ciò consente agli utenti di scaricare questi modelli e usarli nell&#39;applicazione Power BI e di personalizzarli ulteriormente e di raccontare ai report una storia avvincente.

[**Scarica i modelli**](https://documentcloud.adobe.com/link/track?uri=urn:aaid:scds:US:842bb6a2-cd7d-4c3d-b968-da38bc1cc18a)

<!--<table> 
 <tbody>
  <tr> 
   <td><img src="assets/download.png"></td> 
   <td><p> </p> <p><a disablelinktracking="false" href="https://documentcloud.adobe.com/link/track?uri=urn:aaid:scds:US:842bb6a2-cd7d-4c3d-b968-da38bc1cc18a"><strong><em>Download the templates</em></strong></a></p></td> 
  </tr> 
 </tbody>
</table>-->

Puoi anche scaricare manualmente i modelli dal collegamento riportato sopra. Utilizza i modelli e personalizza i report.

### Esportare il report della formazione

I report di formazione possono essere esportati in Power BI come parte della funzione Report unificati.

Il report sulla formazione contiene i seguenti campi aggiuntivi:

* Numero di utenti che hanno condiviso feedback su un corso
* Valutazione a stelle media per un corso

![](assets/export-training-report.png)
*Report di formazione sull&#39;esportazione*

### Modifiche relative al percorso di apprendimento

#### Amministratore: Trascrizioni di apprendimento e report unificato

**Connessioni esistenti**

Se l&#39;opzione Percorso di apprendimento è disabilitata nell&#39;account Amministratore, nei report non vengono aggiunte righe e colonne.

Se l&#39;opzione Percorso di apprendimento è abilitata nell&#39;account Amministratore, il report conterrà il tipo di colonna Percorso di apprendimento (livello superiore) per tutti gli Allievi iscritti a un percorso di apprendimento.

**Nuove connessioni**

Se l&#39;opzione Percorso di apprendimento è disabilitata nell&#39;account Amministratore, il rapporto di formazione sarà composto dalle seguenti colonne:

* Percorso incorporato: mostra il nome del programma di apprendimento.
* ID percorso incorporato: mostra gli ID del programma di apprendimento.
* ID corso incorporato: mostra gli ID dei corsi che si trovano all’interno di un percorso di apprendimento.

Inoltre, il report conterrà il tipo di colonna “Percorso di apprendimento (livello superiore)” per tutti gli Allievi iscritti a un percorso di apprendimento.

Nella colonna Tipo, il programma di apprendimento verrà rinominato Percorso di apprendimento. Per le connessioni esistenti, non è prevista alcuna modifica. Tuttavia, per le nuove connessioni, le modifiche verranno applicate dopo 30 giorni.

#### Report di formazione: report unificato

**Connessioni esistenti**

Se l&#39;opzione Percorso di apprendimento è disabilitata nell&#39;account Amministratore, nei report non vengono aggiunte righe e colonne.

Se l&#39;opzione Percorso di apprendimento è abilitata nell&#39;account Amministratore, il report conterrà la colonna &quot;Tipo&quot;. La colonna contiene il nuovo valore &quot;Percorso di apprendimento (livello superiore), ove applicabile&quot;.

**Nuove connessioni**

Se l&#39;opzione Percorso di apprendimento è disabilitata nell&#39;account Amministratore, il rapporto di formazione sarà composto dalle seguenti colonne:

* **Percorso incorporato:** mostra il nome del programma di apprendimento.
* **ID percorso incorporato:** mostra gli ID del programma di apprendimento.
* **ID corso incorporato:** visualizza gli ID dei corsi che si trovano all&#39;interno di un percorso di apprendimento.

Inoltre, il report conterrà il tipo di colonna “Percorso di apprendimento (livello superiore)” per tutti gli Allievi iscritti a un percorso di apprendimento.

Nella colonna Tipo, il programma di apprendimento verrà rinominato Percorso di apprendimento. Per le connessioni esistenti, non è prevista alcuna modifica. Tuttavia, per le nuove connessioni, le modifiche verranno applicate dopo 30 giorni.

## FTP personalizzato {#custom-ftp}

**Pre-requisiti**

>[!NOTE]
>
>Per configurare l’FTP personalizzato, contatta il CSM. Il CSM fornirà i dettagli necessari per l’impostazione dell’FTP.
>
>La configurazione dell&#39;FTP comporta un tempo di consegna e richiede il supporto IT per consentire l&#39;elenco di IP e porte e creare anche determinate cartelle con autorizzazioni specifiche sul server FTP.

Learning Manager offre la possibilità di collegarsi alla propria posizione FTP personalizzata.

L’FTP supporterà:

### Importazione di dati

Il processo di importazione degli utenti consente all’Amministratore Learning Manager di recuperare i dettagli dei dipendenti dal servizio FTP di Learning Manager e importarli automaticamente in Learning Manager. Utilizzando questa funzione, è possibile integrare più sistemi inserendo il file CSV generato da tali sistemi nelle apposite cartelle degli account FTP. Learning Manager preleva i file CSV, li unisce e importa i dati in base alla pianificazione Fai riferimento alla funzione di pianificazione per ulteriori informazioni.

**Mapping attributi**

L’Amministratore di integrazione può scegliere le colonne di CSV e mapparle agli attributi raggruppabili di Learning Manager. L’operazione di mappatura viene eseguita una sola volta. Una volta completata, la mappatura viene utilizzata nelle successive importazioni di utenti. Può essere riconfigurata qualora l’Amministratore desiderasse una mappatura diversa per l’importazione degli utenti.

### Esportazione dati

La funzione di esportazione dei dati consente di esportare le abilità degli utenti e le trascrizioni degli allievi in una posizione FTP per l’integrazione con qualsiasi sistema di terzi.

### Report di pianificazione

L’Amministratore può impostare le attività di pianificazione secondo i requisiti dell’organizzazione e gli utenti nell’applicazione Learning Manager vengono aggiornati in base alla pianificazione. Allo stesso modo, l’Amministratore di integrazione può pianificare l’esportazione delle abilità in modo tempestivo per consentire l’integrazione con un sistema esterno.  La sincronizzazione può essere eseguita su base giornaliera nell’applicazione Learning Manager.

Per configurare il proprio FTP, accedere come amministratore di integrazione e fare clic su **[!UICONTROL FTP personalizzato >**[!UICONTROL  Connetti ]**]**.

Esistono due tipi di autenticazione:

![](assets/custom-ftp-authenticationoptions.png)
*Opzioni di autenticazione FTP personalizzate*

* **Base:** nell&#39;autenticazione di base, dovrai solo fornire l&#39;url, il nome utente e la password del dominio FTP. Dopo aver fornito i dettagli, fai clic su Connetti.
* **Certificazione:** se l&#39;FTP del cliente supporta l&#39;autenticazione tramite certificato, può scegliere questa opzione. Dopo aver fatto clic su Genera chiave SSH, la chiave SSH viene scaricata nel computer locale. Quando apri il file, la chiave è simile alla seguente

![](assets/ssh-public-key.png)
*Chiave pubblica SSH*

È necessario inserire questa chiave pubblica nel server FTP prima di aggiungere i seguenti dettagli. Una volta impostata la chiave indicata come chiave pubblica del tuo FTP, fornisci l&#39;URL del dominio FTP e il nome utente e fai clic sul **pulsante Connetti** per configurare la connessione.

Una volta impostata la connessione, vengono create automaticamente le cartelle per l&#39;importazione e l&#39;esportazione nella posizione ftp. Successivamente, la funzionalità di importazione/esportazione viene fornita da FTP personalizzato.

>[!NOTE]
>
>Un connettore FTP personalizzato può essere configurato solo con i server SFTP.

## Connettore ADFS {#adfsconnector}

Prerequisiti per stabilire una connessione ADFS:

* Accedi al portale Azure usando questo URL:  [https://portal.azure.com/](https://portal.azure.com/) prima di registrare l&#39;app.
* Aprire Azure Active Directory.

## Procedura di registrazione dell’applicazione {#stepstoregisteryourapplication}

* Fai clic su Azure Active Directory. Fai clic su **[!UICONTROL Aggiungi]** > **[!UICONTROL registrazione]** app.

  <!--![](assets/add-app-registration.png)-->
  <!-- *Add app registration*-->

* Inserisci il nome dell’applicazione.

  <!--![](assets/register-app.png)-->
  <!--*Enter the name of the application*-->

  Fai clic su **[!UICONTROL Registra]**.

* Nel riquadro a destra, seleziona **[!UICONTROL Certificati e segreti]**.

  <!--![](assets/add-client-secret.png)-->

  <!--*Select Certificates and Secrets*-->

* Aggiungi un segreto client.

  <!--![](assets/add-description.png)-->

  <!--*Add a client secret*-->

* Aggiungi una descrizione al segreto e impostane la scadenza a 24 mesi.

  <!-- ![](assets/copy-values.png)-->

  <!--*Add description*-->

* Copia il valore e il segreto, ad esempio, nel blocco note.

  <!-- ![](assets/copy-secret.png)-->

  <!--*Copy value and secret key*-->

* Seleziona **Autorizzazioni API**.

  <!--![](assets/click-api-permission.png)-->

  <!-- *Left pane containing API Permissions*-->

* Seleziona **Aggiungi autorizzazioni** e abilita l’opzione **Concedi consenso Amministratore**.

  ![](assets/add-permission.png)

  *Aggiungere autorizzazioni*

* Seleziona **Microsoft Graph**.

  <!--![](assets/ms-graph.png)-->

  <!--*Select Microsoft Graph*-->

* Seleziona **Autorizzazioni applicazione**.

  ![](assets/request-api-permission.png)

  *Seleziona le autorizzazioni dell&#39;applicazione*

* Cerca *directory* e seleziona **Lettura dei dati della directory**.

  ![](assets/read-directory-data.png)

  *Seleziona Leggi dati directory*

* Inserisci *utente* come termine di ricerca.

  ![](assets/search-user.png)

  *Immettere il termine di ricerca*

* Seleziona **Lettura completa dei profili di tutti gli utenti**.

  ![](assets/select-read-all.png)

  *Seleziona Leggi i profili completi di tutti gli utenti*

* Seleziona **Aggiungi autorizzazioni**.

  <!--![](assets/select-add-permission.png)-->

  <!-- *Select Add Permissions*-->

### Pagina di configurazione di ADFS

1. Nella pagina di configurazione ADFS in Adobe Learning Manager, inserisci l’ID client e il segreto client ottenuti in precedenza.

   Fai clic su **[!UICONTROL Connetti]**.

1. Accedi a **portal.azure.com**. I valori verranno inseriti nei campi ID tenant e Dominio primario.

### Importa

#### Mapping attributi

L&#39;Amministratore dell&#39;integrazione può scegliere gli attributi ADFS e mapparli agli attributi raggruppabili del relativo Learning Manager. Una volta completata, la mappatura viene utilizzata nelle successive importazioni di utenti. Può essere riconfigurata qualora l&#39;amministratore desiderasse una mappatura diversa per l&#39;importazione degli utenti.

#### Importazione automatica degli utenti

Il processo di importazione degli utenti consente all&#39;amministratore di Learning Manager di recuperare i dettagli dei dipendenti da ADFS e importarli automaticamente in Learning Manager.

#### Filtraggio degli utenti

L&#39;amministratore di Learning Manager può applicare filtri agli utenti prima di importarli. Ad esempio, può scegliere di importare tutti gli utenti della gerarchia sotto uno o più Manager specifici.

Per configurare il connettore ADFS, contatta il team CSM di Learning Manager.

## Configurazione del connettore ADFS {#configureadfsconnector}

1. Nella home page di Learning Manager passa il mouse sopra la scheda/l&#39;anteprima di ADFS. Viene visualizzato un menu. Fai clic sull&#39;opzione Connetti nel menu.

   ![](assets/adfs1.jpg)

   *Anteprima ADFS*

1. Fai clic su Connetti per stabilire una nuova connessione. Viene visualizzata la pagina del connettore ADFS. Inserisci i dettagli dell’account che desideri mappare.

   ![](assets/adfs2.jpg)

   *Stabilire la connessione*

1. Se desideri importare l&#39;utente ADFS direttamente come utente interno di Learning Manager, utilizza l&#39;opzione Importa utenti interni.

   ![](assets/adfs3.jpg)

   *Importare utenti in Learning Manager*

1. Nella pagina di mappatura, sul lato sinistro puoi vedere le colonne di Learning Manager e sul lato destro puoi vedere le colonne di ADFS. Seleziona il nome appropriato per la colonna, mappato al nome della colonna del responsabile dell&#39;apprendimento.

   ![](assets/adfs4.jpg)

   *Mapping attributi*

1. Per visualizzare e modificare l&#39;origine dati, fai clic come amministratore su **[!UICONTROL Impostazioni]** > **[!UICONTROL origine dati]**.

   L&#39;origine ADFS stabilita viene elencata. Per modificare il filtro, fai clic su **[!UICONTROL Modifica]**.

   ![](assets/datasource.jpg)
   *Impostazione origine dati*

1. Riceverai una notifica al completamento dell’importazione. Per visualizzare o modificare il registro di importazione, fai clic su **[!UICONTROL Utenti]** > **[!UICONTROL registro]** di importazione.

### Eliminare una connessione {#Deleteaconnection-1}

Per eliminare una connessione miniOrange stabilita, attenersi alla seguente procedura.

## Adobe Connect {#connect}

1. In Adobe Connect, fai clic sull’icona dei tre punti sulla scheda e scegli **Connetti**.
1. Fai clic sul **collegamento Configura ora** nella sezione Configurazione di Adobe Connect.
1. Fornisci il nome di dominio Adobe Connect della tua azienda e le credenziali di accesso.

   URL di Adobe Connect di esempio: ***mycompany.adobeconnect.com***

   È necessario fornire l’Id e-mail dell’Amministratore dell’account Adobe Connect.

   >[!NOTE]
   >
   >In Learning Manager sono supportati solo gli account Adobe Connect ospitati (hosted). Esempio: “.adobeconnect.com”.

1. Fate clic su **[!UICONTROL Integra.]**

   Dopo aver autenticato l&#39;ID e-mail, Learning Manager visualizza il messaggio quando Connect è stata integrata correttamente. Puoi iniziare a visualizzare i corsi in aula virtuale utilizzando Adobe Connect.

   **Una volta che l’Amministratore dell’account di Connect ha autenticato l’ID e-mail dell’utente, la richiesta viene inoltrata per ottenere l’approvazione del team di back-end Adobe Connect. In genere sono necessari uno o due giorni per l’approvazione e la configurazione dell’integrazione.**

   >[!NOTE]
   >
   >L’Amministratore dell’account Adobe Connect deve accettare i termini e condizioni d’uso di Adobe Connect. In caso di mancata accettazione, l’autenticazione di accesso potrebbe non riuscire. Dopo averlo creato, accedi all’account Adobe Connect una volta. Al primo accesso, viene visualizzata una pagina di termini e condizioni.

### Aggiunta di informazioni alla sessione aula virtuale {#addvirtualclassroomsessioninformation}

Se l’Autore di un corso in aula virtuale non ha fornito le informazioni sulla sessione, l’Amministratore può includere dettagli sulla sessione.

Nell’accesso come Amministratore, fai clic sul nome del corso aula virtuale. Fai clic su Istanze nel riquadro sinistro e su Dettagli sessione.  Fai clic sull&#39;icona Modifica nell&#39;angolo destro della pagina Dettagli sessione per aggiungere le informazioni sulla sessione.

Con l’integrazione di Adobe Learning Manager e Adobe Connect per la creazione di moduli o sessioni aula virtuale, il tuo account Connect dovrebbe supportare le sale riunioni con un numero di sale e utenti simultanei adeguato alle tue esigenze. Queste sale riunioni vengono utilizzate per ospitare i moduli aula virtuale di Learning Manager. Una nuova sala riunioni Connect viene creata in modo dinamico da Learning Manager per ciascun modulo o sessione aula virtuale all’interno di Learning Manager.

>[!NOTE]
>
>È necessario acquistare Adobe Connect e Adobe Learning Manager separatamente.

### Sala riunioni permanente di Adobe Connect {#persistent}

In Adobe Connect, i clienti utilizzano le sale riunioni esistenti che hanno già creato in Connect. Tutte le sale riunioni di Connect sono permanenti e i modelli delle sale riunioni vengono accuratamente impostati per offrire un’esperienza unificata per ogni sala permanente.

Puoi creare una sessione aula virtuale utilizzando una delle sale già create in Adobe Connect.

Learning Manager consente agli Allievi di accedere alla sala Connect per la sessione virtuale utilizzando un metodo di autenticazione.

![](assets/adobe-connect-authentication.png)
*Autenticazione Adobe Connect*

Quando si crea un modulo aula virtuale utilizzando Adobe Connect, è possibile selezionare una sala permanente. Se si seleziona **No** viene creata una sala riunioni dinamica, come in precedenza.

![](assets/persistent-room-selection.png)
*Selezione persistente della stanza*

Una volta completato un corso da parte di un Allievo tramite Adobe Connect, la registrazione della sessione e il codice di accesso verranno visualizzati nell’app per Allievi.

![](assets/connect-recording.png)
*Collega la registrazione*

### Importazione dei punteggi dei quiz da Adobe Connect {#quiz-adobe-connect}

Importa i dati dei quiz di Connect in Learning Manager e integrali con il flusso di lavoro di reporting esistente in modo che gli utenti di Learning Manager possano ottenere i dati dei quiz, le risposte degli utenti e i punteggi dalle sessioni di Adobe Connect all&#39;interno del report, ad esempio il modo in cui è disponibile per i moduli di autoapprendimento che contengono quiz.

Nella sezione Connect, se un Allievo segue un corso con quiz o eventuali interazioni che supporta la creazione di report per i quiz, tutte le interazioni degli allievi vengono monitorate in aggiunta al completamento. Deve trattarsi di un corso VC di Connect.

Ecco un breve flusso di lavoro del processo.

**Adobe Connect - Ospitante**

* L’ospitante in Connect crea un corso e carica i contenuti che includono quiz e sono interattivi.
* L’ospitante crea un corso **Classe virtuale** e salva il corso VC. L’ospitante può collegare il corso creato alla VC oppure può usare l’opzione **Condividi corso** nell’app Connect durante la sessione per condividere il corso.

**Learning Manager - Autore**

* L&#39;Autore crea un corso in Learning Manager con il tipo di modulo come **Aula virtuale.**
* Dall’elenco a discesa **Sistema di conferenza**, scegli Connect come fornitore VC.
* Scegli il corso Riunioni permanenti e seleziona la Classe virtuale (VC) creata dall’ospitante in Connect. Scegli l’Istruttore. Salva e pubblica il corso.

**Learning Manager - Allievo**

* Dopo la pubblicazione del corso, l’Allievo si iscrive al corso.
* L’Allievo viene reindirizzato alla sessione Connect VC in cui è autorizzato ad accedere alla sessione VC dall’ospitante di Connect.

**Adobe Connect - Ospitante**

* All’interno della sessione VC, l’ospitante di Connect condivide il quiz condiviso in precedenza.

**Adobe Connect - Allievo**

* L’Allievo effettua il quiz e, una volta completato, chiude la sessione.

**Learning Manager - Allievo**

* L’Allievo chiude la sessione, che si sincronizza automaticamente.

**Learning Manager - Amministratore**

* Una volta scaduta la sessione, il flusso di lavoro di importazione del quiz viene attivato dopo la durata programmata.
* Attendi fino all’attivazione del programma e al completamento dell’elaborazione. Per verificare lo stato dell’elaborazione come Amministratore dell’integrazione, puoi visualizzare lo **Stato di esecuzione** all’interno del connettore Adobe Connect. Una volta completata l&#39;esecuzione, lo stato cambierà in **Completato**.

* L&#39;amministratore sceglie quindi il corso per Manager dell&#39;apprendimento creato in precedenza. Ecco cosa vede l’Amministratore:

   * **Frequenza e punteggi**: mostra il punteggio del quiz finale e lo stato della frequenza.
   * **Punteggio quiz L2**

      * **Per utente** - Visualizza il punteggio finale del quiz visualizzato come **punti** e **percentuale**.
      * **Per domanda**: mostra le informazioni sul quiz come un grafico.

## Connettore Marketo Engage {#marketo}

Learning Manager si integra con Marketo Engage, un software di automazione del marketing che aiuta a eseguire campagne di marketing.

Marketo Engage Connector è progettato per aggiungere (o aggiornare) lead nel database Marketo Engage, quando un nuovo utente viene aggiunto all&#39;account Learning Manager. Associa inoltre i comportamenti di apprendimento dell&#39;utente in Learning Manager (iscrizione al corso, completamento del corso, assegnazione delle abilità e completamento delle abilità) come oggetti personalizzati con i lead corrispondenti in Marketo Engage. Ciò consente a un marketer di utilizzare queste informazioni per indirizzare il pubblico in base ai loro comportamenti di apprendimento acquisiti da Learning Manager e utilizzare funzionalità di Marketo Engage come &quot;Smart List&quot;.

Come Amministratore di integrazione, puoi integrare Learning Manager con un’istanza di Marketo Engage per automatizzare la sincronizzazione dei dati. Puoi esportare gli utenti interni, le iscrizioni ai corsi e gli eventi di completamento delle abilità. Le operazioni possono essere eseguite seguendo un programma e possono essere configurate, su richiesta.

Affinché Learning Manager si integri con il tuo account Marketo, il tuo account Marketo deve avere la possibilità di creare schemi tramite API.

Dall’app Marketo, puoi scaricare questi tre report:

* Report utente
* Trascrizione Allievo
* Report Abilità utente

Quando crei una connessione Marketo Engage, devi fornire i seguenti dettagli:

* Nome della connessione
* ID client
* Segreto del client
* Marketo Engage Domain

![](assets/marketo-creds.png)

*Immetti le credenziali per Marketo*

>[!NOTE]
>
>Puoi ottenere Id e segreto del client dall’app Marketo Engage. Nell&#39;app Marketo, puoi ottenere l&#39;ID client e il segreto dalla **sezione LaunchPoint** e il dominio Marketo dalla **sezione WebServices** .

**Nella sezione Report unificati della connessione Markeo Engage nell&#39;app Learning Manager**, puoi creare campagne basate sui seguenti elementi:

* Un nuovo utente viene aggiunto a Learning Manager
* Un nuovo utente si è iscritto a un corso
* Un nuovo utente ha completato un corso
* Un Allievo si è iscritto a un’abilità
* Un Allievo ha realizzato un’abilità

Come per qualunque altro connettore, puoi programmare ed esportare i dati su richiesta.

### Mappatura delle colonne in Marketo Engage {#columnmappinginmarketoengage}

In Marketo, sono presenti due tipi di database:

* Database di lead
* Database di oggetti personalizzati

La mappatura delle colonne viene utilizzata per creare il database dei lead. I lead sono utenti che hai esportato dal rapporto utente.

I campi del Report utente sono elencati sotto la colonna Adobe Learning Manager. I campi sotto la colonna Marketo sono ciò che fornisce Marketo. Utilizzando entrambe le colonne, puoi mappare qualsiasi campo di Learning Manager a quello di Marketo. Da una colonna di Learning Manager ti unisci a una colonna correlata di Marketo. Dopo aver unito le colonne, viene creato un database di lead.

Puoi quindi visualizzare tutti gli utenti esportati in Marketo.

Nella sezione **Oggetti personalizzati Marketo** nell’app Marketo, puoi notare che i tre report (Trascrizione Allievo, Abilità utente e Report utente) sono presenti. Per questi report è preceduta la stringa **&quot;cp_&quot;.** Ogni nuovo utente che viene esportato in Marketo è considerato come lead.

### Eventi

Esporta i dati dagli eventi di Learning Manager a un&#39;istanza di Marketo Engagement. Seleziona gli eventi da esportare nel database di Marketo Engage su richiesta o seguendo un programma.

* Aggiunta di nuovi utenti
* Aggiornamento dei metadati utente
* Aggiornamento dell’attività dell’utente
* Iscrizione alla formazione
* Iscrizione autonoma
* Completamento delle abilità

<!--## BlueJeans Events {#bj-events}

BlueJeans Events connector connects Learning Manager and BlueJeans systems to automate data synchronization. Using this connector, you can:

* **Set up virtual sessions using BlueJeans Events:** Configure a new event in BlueJeans and setup a VC session in Learning Manager by selecting the appropriate BlueJeans event. Date and time details are picked automatically from the BlueJeans events.
* **Automated User Completion Syncing:** An Automated user completion syncing process allows the Learning Manager Administrator to fetch completion records for BlueJeans events automatically.

This new connector requires a separate set of credentials to configure the connector. The credentials of the existing BlueJeans Meetings connector will not work for BlueJeans Events connector.

![](assets/bj-event-connector.png) 
*Credentials for BlueJeans Event Connector*

### Workflow {#workflow}

1. The BlueJeans Event moderator creates an event from within BlueJeans.
1. The author creates BlueJeans event course using the BlueJeans event url, which is created in future dates.
1. Since BlueJeans events have a similar title for multiple events, the author must append the event attendee url to the room name, so that he/she can choose the appropriate event.

   The format to enter event url: ***event name--event attendee url***

   For Dynamic rooms, the behavior is similar to that of Adobe Connect.

   ![](assets/bj-eventname.png)
   *BlueJeans Events configuration*

1. Once the author enters the BlueJeans event url, the date and time will be auto populated.
1. Add an instructor to the event. The instructor will now have elevated privileges as a Presenter in a BlueJeans event.

Administrators, managers, and learners can enroll learners to the created course. Upon enrollment, the learner receives an email. The learner can sign in to their Learning Manager account to view the program details and take the course.

When the course is complete, the completion report gets triggered after a scheduled duration. The administrator can see the completion report to check the attendance and score of the learners.

If the BlueJeans Event moderator enables the recording during the session, after session ends, the recording is available in the learner app.

![](assets/bluejeans-event-configure.png)
*BlueJeans Events configuration*

When you enable the check-box **Fetch Events created by the other users**, you can then add the list of BlueJeans event creators in the **Additional Event Creators** field. In the Author app, only events created by these users are searchable via the type-ahead field.

If the **Additional Event Creators** field is left blank, all events created in BlueJeans will be available for searching in the Author App.

The Author, in the Author app, then selects an event from the list of available events. In addition, the Author can add instructors to the event. These instructors in Learning Manager would become the presenters within BlueJeans events.

>[!NOTE]
>
>All users must belong to the same enterprise in BlueJeans Events App.

>[!NOTE]
>
>We've added a caching mechanism that improves the overall user experience. It is applicable when you select additional event creators. In this mode, the events are fetched the first time when an author searches for an event. The cache persists for 30 mins so that authors know how long they must wait to fetch the new events.-->

## Connettore Microsoft Teams

Microsoft® Teams® è una piattaforma di collaborazione persistente basata su chat che supporta la condivisione di documenti, riunioni online e altre funzioni utili per le comunicazioni aziendali.

Adobe Learning Manager utilizza un connettore per aula virtuale che può essere utilizzato per integrare le riunioni di Microsoft Teams con Learning Manager.

Il connettore Microsoft Teams collega i sistemi Learning Manager e Microsoft Teams per consentire la sincronizzazione automatica dei dati. L’elenco riportato di seguito descrive le funzioni del connettore Microsoft Teams:

**Configurare sessioni virtuali con Microsoft Teams**

Questo connettore consente di integrare l’account Adobe Learning Manager con l’account Microsoft Teams. Una volta integrato, il connettore consente a un Autore in Learning Manager di utilizzare Microsoft Teams come fornitore di servizi tecnologici per i moduli aula virtuale creati in Learning Manager.

**Consenti a Microsoft Teams di autenticare gli Allievi quando accedono all&#39;aula virtuale**

L’organizzatore della riunione può configurare la sala d’attesa in modo da limitare l’ingresso alla riunione e controllare le altre opzioni della riunione disponibili su Microsoft Teams.

**Utilizzare la sincronizzazione automatica del completamento utente**

Il processo di sincronizzazione automatizzato di completamento degli utenti consente a un Amministratore Learning Manager di recuperare automaticamente i record di completamento e l’URL della registrazione della riunione su Teams.

Per ulteriori informazioni, consulta  [**Installare il connettore Microsoft Teams in Adobe Learning Manager**](install-microsoft-teams-connector.md).

## Esperienza senza accesso

L&#39;esperienza di non accesso consente di creare un&#39;esperienza in tempo reale per gli utenti che non hanno effettuato l&#39;accesso. Ad esempio, un&#39;esperienza senza accesso funge da pagina di destinazione per le campagne di marketing volte a incoraggiare le iscrizioni.

L&#39;esperienza di accesso non connesso in Adobe Learning Manager può essere configurata utilizzando il **[!UICONTROL connettore Training Data Access]** . Il connettore offre le seguenti offerte:

* Offerta standard
* Offerta Premium

**Offerta standard**

L&#39;offerta standard prevede la creazione della versione nativa di Adobe Learning Manager. Gli utenti possono creare un&#39;esperienza headless di sola dimostrazione, senza accesso. L&#39;esperienza headless dimostrativa non è scalabile e non deve essere utilizzata in un ambiente di produzione.

**Offerta Premium**

L&#39;offerta premium aiuta gli utenti a creare un&#39;interfaccia **[!UICONTROL headless, configurata dal connettore Training Data Access]** . Ciò consente agli utenti di ottenere dati in tempo reale sui dettagli del corso e del percorso di apprendimento come nome, descrizione, autore, abilità, durata, ecc. Per gli scenari di apprendimento misto, ottieni anche limiti di posti in tempo reale, posti occupati, limiti delle liste d&#39;attesa e conteggi delle liste d&#39;attesa. I clienti possono utilizzare queste API per creare funzionalità di ricerca e filtro e un riepilogo completo del corso per gli Allievi che non hanno effettuato l&#39;accesso.

I clienti possono acquistare un piano premium per creare questa esperienza altamente scalabile senza accesso.

>[!NOTE]
>
>Contatta il team di supporto o CSM per acquistare il piano premium.

Dopo che un utente ha acquistato un piano, il team CSM attiverà il piano premium per lui. Utilizzando il connettore Training Data Access, gli utenti possono configurare un&#39;esperienza senza accesso con le funzionalità menzionate in precedenza.

### Connettore di accesso ai dati di formazione

>[!IMPORTANT]
>
>Questa funzionalità specifica è disponibile solo se Adobe Learning Manager viene venduto come componente aggiuntivo di Adobe Experience Manager. I dati del corso sarebbero obsoleti in 24 ore.

>[!NOTE]
>
>La sezione evidenzia il funzionamento dell&#39;infrastruttura, ma per creare un&#39;esperienza headless o basata su AEM senza accesso, contattaci. Ti suggeriremo il giusto approccio basato sul tuo caso d&#39;uso. Questa funzionalità non è attualmente disponibile come self-service.

Il **[!UICONTROL connettore Training Data Access]** ti consente di creare un&#39;esperienza senza testa. Questa esperienza può essere autonoma o un&#39;interfaccia utente personalizzata basata su AEM Sites. Aiuta a recuperare e visualizzare le informazioni di formazione agli Allievi e consente la ricerca e il filtraggio. Una volta abilitato il connettore dati, sarà disponibile un set di API pubbliche per creare l&#39;interfaccia, in cui le informazioni sul corso/percorso di apprendimento verranno visualizzate agli Allievi.

#### Configurazione del connettore

Utilizza il **[!UICONTROL connettore Training Data Access]** per integrare il tuo account Adobe Learning Manager con i sistemi di ricerca e archiviazione dei dati. Ciò consente all&#39;interfaccia basata su AEM Sites di ottenere dati di formazione, visualizzare pagine Web e offrire migliori opzioni di ricerca per gli Allievi.

Esporta i metadati di formazione da Adobe Learning Manager ai servizi di recupero dati e abilitazione della ricerca utilizzando le API. Inoltre, puoi creare una pianificazione per automatizzare queste esportazioni.

Per configurare il connettore di accesso ai dati di training, attenersi alla seguente procedura:

1. Nell&#39;app Amministratore di integrazione, seleziona **[!UICONTROL Accesso ai dati]** di formazione > **[!UICONTROL Guida introduttiva]**.
1. Seleziona **[!UICONTROL Avanti]** nella **[!UICONTROL pagina Guida introduttiva]** .
1. Digitare il nome della connessione e i domini elencati in modo consentito.

   ![](assets/connection-name-and-domain-name.png)Digitare il nome della connessione e il nome del dominio

1. Selezionare il **[!UICONTROL Tipo di interfaccia]** tra le seguenti opzioni:

   * **[!UICONTROL Native Learning Manager]**: questa è l&#39;offerta standard, disponibile solo per l&#39;interfaccia nativa.
***[!UICONTROL Interfacce]** headless: questa è l&#39;offerta premium che espone le API per creare un&#39;esperienza senza accesso.

   ![](assets/types-of-interface.png)Tipi di interfaccia

1. Seleziona **[!UICONTROL Connetti]**. L&#39;URL di base e l&#39;URL della rete CDN verranno generati automaticamente.
Puoi utilizzare questi URL per recuperare i dati utilizzando le API.

   >[!NOTE]
   >
   >I clienti che utilizzano l&#39;offerta premium riceveranno un URL diverso da quelli che utilizzano l&#39;offerta standard.


1. Seleziona **[!UICONTROL Esporta metadati]** di formazione nella pagina del connettore.
1. Seleziona **[!UICONTROL Abilita esportazione]** metadati di addestramento utilizzando questa connessione per esportare i dati di addestramento.
1. Una volta abilitata la connessione, le immagini di tutti i corsi, i percorsi di apprendimento e i certificati vengono migrate nella rete CDN.
1. Esporta i metadati dei corsi, dei percorsi di apprendimento e dei certificati nel servizio di ricerca e recupero.
1. È possibile pianificare l&#39;esportazione dei metadati selezionando l&#39;opzione Abilita pianificazione. Il programma avverrà automaticamente ogni 3 ore per il piano premium.
1. Per un report su richiesta, passare a **[!UICONTROL Su richiesta]**, selezionare la data ]**di**[!UICONTROL  inizio e quindi **[!UICONTROL fare clic su]** Esegui.
È possibile controllare lo stato di esecuzione del report nella **[!UICONTROL pagina Stato esecuzione]** .

### Crea il sito Web in AEM

**Prerequisito:** installa il pacchetto AEM dal  [**repository**](https://github.com/adobe/adobe-learning-manager-reference-site/releases/tag/1.0.0) GitHub.

1. Utilizza gli URL di base e recupero, l’ID client, il segreto client e il token di aggiornamento amministratore, quindi crea una configurazione in AEM.
1. Crea il sito Web utilizzando i componenti AEM.
1. Pubblica il sito Web.

Per ulteriori informazioni, consulta questo  [**documento**](../../adobe-learning-manager-integration-aem.md).

### Allievi

Nel sito Web pubblicato viene visualizzato un elenco di tutti i corsi, i certificati e i percorsi di apprendimento migrati che vengono recuperati dal servizio di ricerca per gli Allievi non registrati.

Quando un Allievo fa clic su Corso, Certificato o Percorso di apprendimento, viene avviata la pagina Panoramica. Nella pagina, al momento dell’iscrizione, l’Allievo deve prima effettuare l’accesso e poi seguire il corso.

## Connettore Adobe Commerce

>[!NOTE]
>
>Questa funzionalità specifica è disponibile solo se Adobe Learning Manager viene venduto come componente aggiuntivo di Adobe Experience Manager.

>[!NOTE]
>
>Questo connettore può essere abilitato anche per gli account di prova.

Adobe Learning Manager ora offre l’integrazione con Adobe Commerce, una piattaforma per la creazione di esperienze di e-commerce per i clienti B2B e B2C.

Adobe Commerce è una soluzione di abilitazione all’e-commerce estensibile e scalabile che consente di creare esperienze di e-commerce multicanale per clienti B2B e B2C su un’unica piattaforma. Utilizza il connettore Adobe Commerce per collegare il tuo account Adobe Learning Manager ad Adobe Commerce e realizzare funzionalità di e-commerce sulla piattaforma di apprendimento.

Abilita questo connettore e utilizza le funzioni di Adobe Commerce per fornire le offerte di apprendimento come corsi di formazione a pagamento. Tieni presente che è necessario acquistare Adobe Commerce separatamente prima di poterlo integrare con Adobe Learning Manager utilizzando questo connettore.

Il connettore si integra con Adobe Commerce inviando i dati di formazione alla piattaforma di e-commerce, il che consente agli Allievi di effettuare un pagamento e acquistare un corso di formazione.

Oltre ad avviare un acquisto, il connettore ne raccoglie anche i dettagli da Adobe Commerce, utilizzato da Adobe Learning Manager per convalidare l’acquisto e sbloccare l’accesso al corso di formazione.

**Pre-requisiti**

1. Abilita  [RabbitMq](https://devdocs.magento.com/cloud/project/services-rabbit.html) o qualsiasi altro broker di messaggistica.
1. Abilita [CRON.](https://devdocs.magento.com/cloud/env/variables-deploy.html#cron_consumers_runner)
1. Per i passaggi 1 e 2, modifica i seguenti file:

   1. .magento.app.yaml
   1. .magento/services.yaml
   1. .magento.env.yaml

1. Sostituisci il limite di opzioni tramite un modulo personalizzato. Si tratta di un passaggio facoltativo, ma altamente consigliato per set di dati di grandi dimensioni.
1. Abilita tutte le API asincrone della pagina. Poiché potrebbero esserci molti dati, l’esportazione avviene in modo asincrono: Le API di Adobe Commerce sono chiamate payload della richiesta inviato. La richiesta spinge i messaggi in una coda e c&#39;è un consumatore in questa coda, che elabora questi messaggi e crea prodotti sul lato commerciale. Adobe Commerce non fornisce questa elaborazione asincrona per impostazione predefinita. Ecco perché è necessario abilitare questa opzione.
1. Aggiungi un collegamento per tornare ad ALM nella pagina di completamento del pagamento. Tale URL di ritorno deve essere configurato in Adobe Commerce. URL da utilizzare per il collegamento. -  `https://learningmanager.adobe.com/app/learner#/postPayment`
1. Modifica l&#39;indicizzazione da &quot;Al salvataggio&quot; a &quot;Pianificato&quot;.  Per ulteriori informazioni, vedere questa  [KB](https://support.magento.com/hc/en-us/articles/360040227191).
1. Applica le seguenti patch. Per ulteriori informazioni, vedere  [Applicare le](https://devdocs.magento.com/cloud/project/project-patch.html) patch.
1. Configura rapidamente.  Fastly è necessario per Adobe Commerce sull&#39;infrastruttura cloud ed è utilizzato negli ambienti di gestione temporanea e produzione. Per ulteriori informazioni, consulta [Configurazione di Fastly](https://devdocs.magento.com/cloud/cdn/configure-fastly.html).

### Configurazione del connettore

In qualità di Amministratore di integrazione, nel connettore Adobe Commerce, fai clic su **[!UICONTROL Connetti]**.

Nella pagina di configurazione, inserisci i seguenti dettagli. Tali dettagli, ovvero le chiavi di autorizzazione, sono disponibili in Adobe Commerce. Una volta creata un&#39;integrazione in Adobe Commerce, le credenziali saranno disponibili lì.

![](assets/adobe-commerce-configuration.png)
*Configurazione di Adobe Commerce Connector*

Una volta attivata la connessione al connettore Adobe Commerce, l’Autore può stabilire il prezzo per un corso, un percorso di apprendimento o un certificato.

Dopo la pubblicazione del corso, del percorso di apprendimento o del certificato, un Allievo può acquistare i corsi nell’app per gli Allievi.

* **Learning Manager nativo:** l’Allievo può acquistare un corso, un piano di apprendimento o un certificato da Learning Manager. Ciò è possibile solo se l’autore ha aggiunto un prezzo.
* **Personalizzazione tramite AEM Sites:** l’Allievo può acquistare un corso da un sito AEM.

### Flusso di lavoro

L’Amministratore Adobe Commerce configura Learning Manager come integrazione.

L’Autore contrassegna i corsi, i percorsi di apprendimento o i certificati come premium e assegna i prezzi. Questa opzione è disponibile solo se l’e-commerce è abilitato per l’account. Per ulteriori informazioni, consulta [Creazione di corsi](../../authors/feature-summary/courses.md).

Il corso o il percorso di apprendimento non sarà disponibile per l’acquisto fino a quando i dati non saranno sincronizzati in Adobe Commerce.

### Esportazione dei corsi in Adobe Commerce

Dopo che un Autore ha impostato i prezzi per vari corsi, percorsi di apprendimento o certificazioni, l’Amministratore di integrazione esporta corsi, percorsi di apprendimento o certificazioni in Adobe Commerce.

>[!NOTE]
>
>Nella versione di marzo 2024 di Adobe Learning Manager è stato introdotto il supporto per [Adobe Commerce 2.4.6](https://experienceleague.adobe.com/docs/commerce-operations/release/notes/adobe-commerce/2-4-6.html?lang=en).


1. Fai clic su **[!UICONTROL Esporta metadati]** di formazione > **[!UICONTROL su richiesta]**.

1. Seleziona le date.

1. Fai clic su **[!UICONTROL Esegui]**. Al termine dell’esecuzione, tutti i corsi o percorsi di apprendimento a pagamento verranno spostati in Adobe Commerce. L&#39;Allievo può quindi acquistare il corso da Learning Manager.

### Manager dell&#39;apprendimento nativo con Adobe Commerce

#### Allievo

In qualità di Allievo, per acquistare un corso, un certificato o un percorso di apprendimento, devi essere registrato.

Per acquistare il corso, fai clic su Acquista ora. Verrai reindirizzato ad Adobe Commerce per completare l’acquisto. Una volta che il pagamento è andato a buon fine, viene visualizzato un messaggio che richiede di tornare a Learning Manager e iniziare il corso. Per completare l&#39;acquisto, devi anche accedere ad Adobe Commerce separatamente.

Quando acquisti un corso, un certificato o un percorso di apprendimento da ALM nativo o AEM, ricevi e-mail da ALM e da Adobe Commerce.

Inoltre, puoi attivare/disattivare i messaggi e-mail da Adobe Commerce.

### Siti AEM con Adobe Commerce

Quando l’opzione “Personalizzazione tramite AEM Sites” è attivata, in quanto Allievo puoi acquistare i corsi da un sito AEM personalizzato.

Il sito AEM conterrà tutti i metadati di Learning Manager per consentire la ricerca tramite Adobe Commerce. In caso di mancata registrazione, i corsi vengono recuperati da Adobe Commerce.

È possibile effettuare l’accesso con e senza registrazione. Gli utenti non registrati possono cercare e sfogliare il catalogo dei corsi, il piano di apprendimento e i certificati. Tuttavia, se desideri acquistare un corso, devi accedere al sito AEM.

Come con Learning Manager nativo, dopo aver effettuato l’accesso, puoi aggiungere un corso al carrello e quindi visualizzare l’anteprima o acquistare il corso.

### Configurazione del connettore Adobe Commerce

#### Prerequisiti

L&#39;amministratore attiva la casella di controllo Attiva **prezzi per i corsi di** formazione in **Impostazioni > Generali** dell&#39;app Amministratore. Se l&#39;opzione è abilitata, gli Autori possono specificare i prezzi per i corsi di formazione. Quando aggiungi una connessione ad Adobe Commerce, questa casella di controllo viene selezionata e applicata automaticamente.

Adobe Learning Manager supporta l’e-commerce per acquistare e vendere corsi di formazione. Qui gli utenti possono vendere corsi di formazione per promuovere l’upselling e il cross selling dei loro prodotti.

Grazie all’integrazione di Adobe Commerce, Adobe Learning Manager supporta l’acquisto e la vendita di corsi di formazione per offrire un’esperienza cliente più completa negli scenari di formazione dei partner.

Ecco gli obiettivi principali di questa integrazione:

* Gli utenti possono generare entrate vendendo corsi su Adobe Learning Manager o su un&#39;interfaccia di apprendimento Headless.
* Abilita l&#39;integrazione di Adobe Commerce nella piattaforma per vendere corsi utilizzando l&#39;app nativa di Learning Manager e AEM.
* Consenti ai clienti di Learning Manager di offrire un apprendimento formale sotto forma di corsi a pagamento.
* Consenti agli Allievi di visualizzare in anteprima i corsi prima di decidere di acquistare la formazione.

#### Adobe Learning Manager nativo

**Amministratore dell&#39;integrazione**

1. Nella pagina Amministratore di integrazione, aggiungi il connettore Adobe Commerce. Ottieni le autenticazioni dall’applicazione creata in Adobe Commerce.
1. Una volta abilitato Adobe Commerce, l’e-commerce è abilitato in Adobe Learning Manager. I dati da Learning Manager ad Adobe Commerce vengono sincronizzati in base a una pianificazione. Questi includono l’intero corso di formazione (a pagamento) e i metadati (utenti, abilità, nome dell’Autore, prezzo, ecc.).

>[!NOTE]
>
>Adobe Learning Manager e Adobe Commerce hanno login diversi.

### AEM

In questa modalità, un Allievo segue il corso su un sito basato su AEM, realizzato con modelli e componenti basati su AEM.

Nel sito di AEM, l&#39;Allievo supporta il carrello, il pulsante Aggiungi al carrello, l&#39;eliminazione di corsi dal carrello e così via.

Se l’utente non è registrato, può comunque cercare i cataloghi dei corsi e visualizzare i dettagli del corso, ma non può acquistare un corso. In qualità di Allievo, per acquistare un corso, devi essere registrato.

Dopo che l’Allievo ha acquistato il corso, viene reindirizzato alla pagina della panoramica del corso nello stato Iscritto, da cui può seguire il corso acquistato.

#### Headless - Accesso non effettuato

Un Allievo può:

* Cercare qualsiasi corso di formazione dalla barra di ricerca.
* Filtrare i corsi in base al prezzo.

Un Allievo non può:

* Acquistare un corso dalla pagina Panoramica.
* Visualizzare in anteprima i contenuti a pagamento.

#### Headless - Accesso effettuato

Un Allievo può:

* Esplorare, visualizzare, cercare e filtrare i corsi di formazione gratuiti o a pagamento.

* Aggiungere un corso al carrello e quindi effettuare il checkout per l’acquisto.
* Aggiungere, aggiornare o eliminare i corsi di formazione presenti nel carrello.
* Pagare contemporaneamente più corsi di formazione.
* Visualizzare in anteprima un corso a pagamento nel lettore.
* Vedere i messaggi in caso di errore di pagamento.

* Dopo aver acquistato il corso, consultare la fattura inviata come allegato tramite e-mail.

#### Sincronizzazione su richiesta

La sincronizzazione tra Learning Manager e Adobe Commerce avviene due volte al giorno. Dopo che l&#39;Amministratore ha abilitato un account per l&#39;e-commerce, l&#39;opzione **Abilita esportazione metadati formazione tramite questa connessione** , quando abilitata, archivia le immagini del corso, del percorso di apprendimento e dei certificati in un CDN pubblico.

Se i dati rimangono non sincronizzati, le informazioni sui prezzi non vengono visualizzate per un Allievo.

Per Learning Manager nativo, se l&#39;e-commerce è attivato e la sincronizzazione tra Learning Manager e Adobe Commerce è completata, gli Allievi possono visualizzare o cercare corsi di formazione gratuiti o a pagamento.

Per AEM, non è disponibile alcun pulsante Acquista ora, ma solo un **pulsante Aggiungi al carrello** . Questo pulsante rimane disabilitato anche se la sincronizzazione non viene eseguita.

#### Domande frequenti

+++Quali corsi non possono essere acquistati?

Un Allievo non può acquistare corsi quali certificazioni ricorrenti, corsi per i contenuti del marketplace, corsi acquisiti, corsi di formazione da parte di connettori, risorse formative e corsi approvati/nominati dal Manager.
+++

+++C&#39;è qualche cambiamento nella trascrizione degli allievi e nel rapporto sulla formazione?

Questi report mostrano il prezzo e la data di acquisto per tutti i corsi di formazione acquistati nell’account.
+++

+++Un Allievo può iscriversi a un corso di formazione gratuito?

Sì, un Allievo può iscriversi a corsi di formazione gratuiti. Il corso di formazione gratuito mostra il pulsante Anteprima e Iscrizione nella pagina Panoramica del corso di formazione.
+++
