---
description: Questo documento contiene suggerimenti di base per risolvere alcuni dei problemi tipici che si verificano durante l’installazione e l’utilizzo dell’applicazione desktop Adobe Learning Manager.
jcr-language: en_us
title: Risoluzione dei problemi con l’app desktop Adobe Learning Manager
contentowner: kuppan
source-git-commit: 6abc118c6ad7e66e3ded5bd26b9167c3a0b99e4b
workflow-type: tm+mt
source-wordcount: '1447'
ht-degree: 0%

---



# Risoluzione dei problemi con l’app desktop Adobe Learning Manager

Questo documento contiene suggerimenti di base per risolvere alcuni dei problemi tipici che si verificano durante l’installazione e l’utilizzo dell’applicazione desktop Adobe Learning Manager.

## Non riesco a effettuare le seguenti operazioni {#iamunabletodothefollowing}

+++Non riesco a scaricare l’applicazione desktop Adobe Learning Manager

1. Controlla la connessione Internet e le impostazioni del firewall.
1. In Apprendimento sociale, fai clic su **[!UICONTROL Nuovo post]** per creare un post. Se non disponi di una bacheca, creane una.
1. Fai clic su una delle seguenti opzioni del pulsante di pubblicazione visualizzate per creare contenuti, come Schermata, Registra audio, Registra video, Galleria Learning Manager. Verrai reindirizzato alla pagina dell’applicazione desktop Adobe Learning Manager da cui potrai scaricare l’applicazione desktop Adobe Learning Manager.
1. È necessario un account Learning Manager di Adobe valido con Apprendimento sociale abilitato dall’amministratore. L&#39;amministratore potrebbe aver disabilitato anche i download tramite il browser Web. Per ulteriori informazioni sul download dell’app desktop Learning Manager, contatta l’Adobe Adobe Amministratore di Learning Manager.

+++

+++Impossibile installare l’applicazione desktop Adobe Learning Manager

1. Assicurati che il tuo sistema soddisfi i requisiti minimi di sistema. Vedere [Requisiti di sistema per l’Adobe dell’app Learning Manager per desktop](../learners/adobe-learning-manager-app-for-desktop/adobe-learning-manager-desktop-app-system-requirements.md).
1. Pulisci qualsiasi installazione precedente dell’applicazione desktop Adobe Learning Manager. Per ulteriori informazioni, consulta  [Come pulire le installazioni precedenti](#howtocleanuppreviousinstallationsofadobelearningmanagerdesktopapp) per ulteriori informazioni.
1. Per gli errori durante il processo di installazione, vedere [Come trovare i registri delle applicazioni](#howtofindapplicationlogs). Per ulteriore assistenza, contatta l’amministratore dell’applicazione desktop Learning Manager, Adobe.

+++

+++Non riesco ad avviare l’applicazione desktop Adobe Learning Manager

1. Assicurati che l’applicazione desktop Adobe Learning Manager sia stata scaricata e installata.
1. In Apprendimento sociale, fai clic su **[!UICONTROL Nuovo post]** (se non disponi di una bacheca, creane una). Fai clic su una delle seguenti opzioni del pulsante di pubblicazione visualizzate: Scatta una schermata, Registrazione audio, Registrazione video e Galleria di Learning Manager di Adobe. Verrai reindirizzato a una pagina da cui potrai avviare l’applicazione desktop Adobe Learning Manager.
1. Nel caso in cui l&#39;app non si avvia, è possibile avviarla anche dal menu Start su Windows o da Launchpad su Mac OS X.

+++

+++Non riesco ad accedere al mio account nell’applicazione desktop Adobe Learning Manager

1. Assicurati di essere connesso a Internet e che le impostazioni del firewall non blocchino l’applicazione desktop Adobe Learning Manager.
1. Assicurati di avere un account Allievo di Adobe Learning Manager valido con Apprendimento sociale abilitato.
1. Se non riesci ancora ad accedere, esci e riavvia l’applicazione desktop Adobe Learning Manager, quindi riprova.
1. Per ulteriore assistenza, contatta l’amministratore Adobe di Learning Manager.

+++

+++Non riesco a visualizzare la webcam/il microfono elencato nell’applicazione desktop Learning Manager di Adobe

1. Assicurati che la webcam/il microfono sia correttamente collegato al sistema e funzioni correttamente.
1. Assicurati di aver installato i driver più recenti della webcam/microfono. Alcuni dispositivi non funzionano correttamente senza driver dedicati.
1. Ripristina le preferenze dell’applicazione, quindi riavvia l’applicazione desktop Adobe Learning Manager e riprova. Per ulteriori informazioni, consulta [Come ripristinare le preferenze dell’applicazione](#howtoresetapplicationpreferences).
1. Se utilizzi Mac OS X Mojave 10.14, consenti all’applicazione desktop Adobe Learning Manager di accedere alla webcam/al microfono. Per ulteriori informazioni, consulta [Come impostare le autorizzazioni per webcam/microfono su OSX Mojave](#howtosetwebcammicrophonepermissionsonMacOSXMojave).

+++

+++Non riesco a pubblicare i miei post dall’applicazione desktop Adobe Learning Manager

1. Assicurati di avere un account Allievo di Adobe Learning Manager valido con Apprendimento sociale abilitato da parte dell’Amministratore di Adobe Learning Manager.
1. Ripristina le preferenze dell’applicazione, quindi riavvia l’applicazione desktop Adobe Learning Manager e riprova. Per ulteriori informazioni, consulta [Come ripristinare le preferenze dell’applicazione](#howtoresetapplicationpreferences).
1. Per gli errori durante la pubblicazione, abilita la registrazione avanzata. Per ulteriori informazioni, consulta [Come abilitare la registrazione avanzata](#howtoenableadvancedlogging), riavvia l’applicazione desktop Adobe Learning Manager e ripeti i passaggi precedenti che causano l’errore. Per richiedere assistenza, invia i registri delle applicazioni più recenti all’amministratore di Learning Manager Adobe. Per ulteriori informazioni, consulta [Come trovare i registri delle applicazioni](#howtofindapplicationlogs).

+++

+++Non riesco a visualizzare o aprire i miei progetti precedenti

1. Puoi visualizzare solo i progetti creati con il tuo account Adobe Learning Manager, sullo stesso computer su cui sono stati creati.
1. Ripristina le preferenze dell’applicazione, quindi riavvia l’applicazione desktop Adobe Learning Manager e riprova. Per informazioni, consultate [Come ripristinare le preferenze dell’applicazione](#howtoresetapplicationpreferences).
1. Per gli errori durante l&#39;apertura dei progetti, abilita la registrazione avanzata. Per ulteriori informazioni, consulta [Come abilitare la registrazione avanzata](#howtoenableadvancedlogging). Riavvia l’applicazione desktop Adobe Learning Manager e ripeti i passaggi che causano l’errore. Per richiedere assistenza, invia i registri delle applicazioni più recenti all’amministratore di Learning Manager Adobe. Per ulteriori informazioni, consulta [Come trovare i registri delle applicazioni](#howtofindapplicationlogs).

+++

## Come si ripristinano le preferenze dell’applicazione? {#howtoresetapplicationpreferences}

### Windows {#windows}

1. Per aprire la finestra di dialogo Esegui, premere il tasto **Windows + R** tasti.
1. Tipo `**%APPDATA%\\..\\Local\\Adobe\\Learning Manager 1.0**` e premi Invio.
1. Elimina i file denominati **preferences.json** e **preferences.xml**.

### MAC OS X {#macosx}

1. Apri il Finder.
1. Per aprire il **Vai a** cartella, premere **Cmd+Maiusc+G** tasti.
1. Tipo `**~/Library/Application Support/Adobe/Learning Manager 1.0**` e premi Invio.
1. Elimina i file denominati **preferences.json** e **preferences.xml**.

## Come trovare i registri delle applicazioni? {#howtofindapplicationlogs}

### Windows {#application-logs}

1. Per aprire la finestra di dialogo Esegui, premere **Windows + R** tasti.
1. Tipo `**%TEMP%\\elthor**` e premi Invio.
1. Ordinare le cartelle in base al **Data modifica** e aprire la cartella più recente. Questa cartella contiene i registri dell&#39;applicazione più recenti.

### MAC OS X {#MacOSX-1}

1. Apri **Finder**.
1. Per aprire il **Vai alla cartella** finestra di dialogo, premere **Cmd+Maiusc+G** tasti.
1. Digita &quot;**/var/folders**&quot; (senza virgolette) e premi Invio.
1. Cerca &quot;**elthor**&quot; nella barra di ricerca e apri la cartella.
1. Ordinare le cartelle in base alla ** **Data di modificae aprire la cartella più recente. Questa cartella contiene i registri dell&#39;applicazione più recenti.

## Come abilitare la registrazione avanzata? {#howtoenableadvancedlogging}

### Windows {#Windows-1}

1. Per aprire la finestra di dialogo Esegui, premere **Tasto Windows + R**.****
1. Digita &quot;**%APPDATA%\\.\\Local\\Adobe\\Learning Manager 1.0**&quot; (senza virgolette) e premi Invio.****
1. Esegui backup del file **preferences.json** e quindi aprirlo in un editor di testo.****
1. Cerca la chiave **debugMode** e modifica la proprietà value di questa chiave in &quot;**vero**&quot; (senza virgolette).

### MAC OS X {#MacOSX-2}

1. Apri il Finder.
1. Per aprire il **Vai alla cartella** finestra di dialogo, premere **Cmd+Maiusc+G**.
1. Digita &quot;**~/Libreria/Application Support/Adobe/Learning Manager 1.0**&quot; (senza virgolette) e premi Invio.
1. Esegui backup del file **preferences.json** e quindi aprirlo in un editor di testo.
1. Cerca la chiave **debugMode** e modifica la proprietà value di questa chiave in &quot;**vero**&quot; (senza virgolette)

## Come impostare le autorizzazioni per webcam/microfono in Mac OS X Mojave? {#howtosetwebcammicrophonepermissionsonmacosxmojave}

1. Fai clic **[!UICONTROL Preferenze di sistema]** icona nel Dock.
1. Fai clic **[!UICONTROL Sicurezza e privacy]** > **[!UICONTROL Privacy].**
1. Fai clic **[!UICONTROL Opzioni webcam e microfono]** e assicurati che la casella di controllo Adobe Learning Manager sia selezionata. Se l’Adobe Learning Manager non è elencato, prima installa e avvia l’applicazione desktop Adobe Learning Manager.

## Come ripulire la cache degli aggiornamenti di Adobe di Learning Manager per desktop? {#howtocleanupadobecaptivateprimefordesktopupdatescache}

### Windows {#clean-previous-installation}

1. Per aprire la finestra di dialogo Esegui, premere **Tasto Windows + R**.
1. Tipo `**%APPDATA%\\..\\Local\\Adobe\\Learning Manager 1.0**` e premi Invio.
1. Elimina la cartella denominata **aggiornamenti**.

### MAC OS X {#MacOSX-3}

1. Apri il Finder.
1. Per aprire il **Vai alla cartella** finestra di dialogo, premere **Cmd+Maiusc+G**.
1. Tipo `**~/Library/Application Support/Adobe/Learning Manager 1.0**` e premi Invio.
1. Elimina la cartella denominata **aggiornamenti**.

## Come rimuovere la cartella temporanea di Adobe Learning Manager per desktop? {#howtocleanupadobecaptivateprimefordesktoptempfolder}

### Windows {#clean-previous-installation-1}

1. Per aprire la finestra di dialogo Esegui, premere **Tasto Windows + R**.
1. Digita &quot;**%TEMP%**&quot; (senza virgolette) e premi Invio.
1. Elimina la cartella &quot;**elthor**&quot;.

### MAC OS X {#MacOSX-4}

1. Apri il Finder.
1. Per aprire il **Vai alla cartella** finestra di dialogo, premere **Cmd+Maiusc+G** tasti.
1. Digita &quot;**/var/folders**&quot; (senza virgolette) e premi Invio.
1. Cerca &quot;**elthor**&quot; nella barra di ricerca.
1. Elimina la cartella &quot;**elthor**&quot;.

## Come individuare un Adobe di Learning Manager per i progetti desktop? {#howtolocateadobecaptivateprimefordesktopprojects}

### Windows {#Windows-2}

1. Per aprire la finestra di dialogo Esegui, premere **Tasto Windows + R**.
1. Digita &quot;**~/Documenti/Il mio Adobe di progetti Learning Manager**&quot; (senza virgolette) e premi Invio.
1. Tu o l’Adobe Amministratore di Learning Manager potreste aver modificato il percorso predefinito della cartella dei progetti. Contatta l&#39;amministratore per ulteriore assistenza per individuare e rimuovere i progetti.

### MAC OS X {#MacOSX-5}

1. Apri il Finder.
1. Per aprire il **Vai alla cartella** finestra di dialogo, premere **Cmd+Maiusc+G** tasti.
1. Digita &quot;**~/Documenti/Il mio Adobe di progetti Learning Manager**&quot; (senza virgolette) e premi Invio.

   Tu o l’Adobe Amministratore di Learning Manager potreste aver modificato il percorso predefinito della cartella dei progetti. Contatta l&#39;amministratore per ulteriore assistenza per individuare e rimuovere i progetti.

## Come rimuovere le installazioni precedenti dell’app desktop Adobe Learning Manager? {#howtocleanuppreviousinstallationsofadobelearningmanagerdesktopapp}

### Windows {#Windows-3}

1. Per aprire il **Finestra di dialogo Esegui,** premere **Tasti Windows + R**.
1. Digita regedit e cerca &quot;**HKEY_LOCAL_MACHINE \\SOFTWARE\\Classes\\Installer\\**&quot; (senza virgolette) o &quot;**HKEY_LOCAL_MACHINE\\SOFTWARE\\Microsoft\\Windows\\CurrentVersion\\Installer\\UserData\\S-1-5-18\\Products\\**&quot; (senza virgolette) e premi Invio.
1. Trova la cartella denominata Adobe Learning Manager e individua l’installazione precedente. Elimina la voce del Registro di sistema.  Per individuare il tasto, premere F3.

### MAC OS X {#MacOSX-6}

Sposta i file dal seguente percorso &quot;**/Applicazioni/Adobe Learning Manager/Utenti/Condiviso/Adobe/Risorse Learning Manager/1.0**&quot; per scaricare il cestino e poi svuotarlo.
