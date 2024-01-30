---
description: Questo documento contiene suggerimenti di base per risolvere alcuni dei problemi tipici che si presentano durante l’installazione e l’uso dell’applicazione desktop Adobe Learning Manager
jcr-language: en_us
title: Risoluzione dei problemi con l’app desktop Adobe Learning Manager
contentowner: kuppan
source-git-commit: 6abc118c6ad7e66e3ded5bd26b9167c3a0b99e4b
workflow-type: tm+mt
source-wordcount: '1447'
ht-degree: 54%

---



# Risoluzione dei problemi con l’app desktop Adobe Learning Manager

Questo documento contiene suggerimenti di base per risolvere alcuni dei problemi tipici che si presentano durante l’installazione e l’uso dell’applicazione desktop Adobe Learning Manager

## Non riesco a effettuare le seguenti operazioni {#iamunabletodothefollowing}

+++Non riesco a scaricare l’applicazione desktop Adobe Learning Manager

1. Controlla le impostazioni di connessione Internet e di firewall.
1. In Apprendimento social, fai clic su **[!UICONTROL Nuovo post]** per creare un post. Se non disponi di una bacheca, creane una.
1. Fai clic su una delle seguenti opzioni del pulsante di pubblicazione visualizzate per creare contenuti, ad esempio Schermata, Registra audio, Registra video, Galleria Learning Manager. Viene eseguito il reindirizzamento alla pagina dell’applicazione desktop Adobe Learning Manager da cui puoi scaricare l’applicazione Adobe Learning Manager per desktop.
1. Occorre avere un account Adobe Learning Manager valido con apprendimento social abilitato dall’amministratore. L’amministratore potrebbe aver disabilitato anche i download tramite il browser web. Per ulteriori informazioni sul download dell’app desktop Adobe Learning Manager, contatta l’amministratore di Adobe Learning Manager.

+++

+++Impossibile installare l’applicazione desktop Adobe Learning Manager

1. Verifica che il sistema in uso soddisfi i requisiti minimi di sistema. Vedi [Requisiti di sistema per l’app Adobe Learning Manager per desktop](../learners/adobe-learning-manager-app-for-desktop/adobe-learning-manager-desktop-app-system-requirements.md).
1. Rimuovi tutte le precedenti installazioni dell’applicazione desktop Adobe Learning Manager. Per ulteriori informazioni, consulta  [Come pulire le installazioni precedenti](#howtocleanuppreviousinstallationsofadobelearningmanagerdesktopapp) per ulteriori informazioni.
1. Per gli errori durante il processo di installazione, vedere [Come trovare i registri delle applicazioni](#howtofindapplicationlogs). Per ulteriore assistenza, contatta l’amministratore dell’applicazione desktop Adobe Learning Manager.

+++

+++Non riesco ad avviare l’applicazione desktop Adobe Learning Manager

1. Assicurati che l’applicazione desktop Adobe Learning Manager sia stata scaricata e installata.
1. In Apprendimento social, fai clic su **[!UICONTROL Nuovo Post]** (se non disponi di una bacheca, creane una). Fai clic su una delle seguenti opzioni del pulsante di pubblicazione visualizzate: Scatta una schermata, Registrazione audio, Registrazione video e Galleria di Learning Manager di Adobe. Viene eseguito il reindirizzamento a una pagina da cui puoi avviare l’applicazione desktop Adobe Learning Manager.
1. Se l’app non si apre, avviala dal menu Start su Windows o da Launchpad su Mac OS X.

+++

+++Non riesco ad accedere al mio account nell’applicazione desktop Adobe Learning Manager

1. Verifica che la connessione a Internet sia attiva e che le impostazioni del firewall non blocchino l’applicazione desktop Adobe Learning Manager.
1. Assicurati di avere un account valido Allievo in formazione di Adobe Learning Manager con Apprendimento social abilitato.
1. Se non riesci ancora ad accedere, esci e riavvia l’applicazione desktop Adobe Learning Manager, quindi riprova.
1. Per ulteriore assistenza, contatta l’amministratore di Adobe Learning Manager.

+++

+++Non riesco a visualizzare la webcam/il microfono elencato nell’applicazione desktop Learning Manager di Adobe

1. Assicurati che la tua webcam/microfono sia correttamente inserita nel sistema e funzioni correttamente.
1. Assicurati di aver installato i driver più recenti della webcam/microfono. Alcuni dispositivi non funzionano correttamente senza driver dedicati.
1. Ripristina le preferenze dell’applicazione, quindi riavvia l’applicazione desktop Adobe Learning Manager e riprova. Per ulteriori informazioni, consulta [Come ripristinare le preferenze dell’applicazione](#howtoresetapplicationpreferences).
1. Se utilizzi Mac OS X Mojave 10.14, concedi le autorizzazioni di accesso alla webcam/al microfono all’applicazione desktop Adobe Learning Manager. Per ulteriori informazioni, consulta [Come impostare le autorizzazioni per webcam/microfono in OSX Mojave](#howtosetwebcammicrophonepermissionsonMacOSXMojave).

+++

+++Non riesco a pubblicare i miei post dall’applicazione desktop Adobe Learning Manager

1. Assicurati di avere un account valido Allievo in formazione di Adobe Learning Manager con Apprendimento social abilitato da parte dell’amministratore di Adobe Learning Manager.
1. Ripristina le preferenze dell’applicazione, quindi riavvia l’applicazione desktop Adobe Learning Manager e riprova. Per ulteriori informazioni, consulta [Come ripristinare le preferenze dell’applicazione](#howtoresetapplicationpreferences).
1. Per gli errori durante la pubblicazione, abilita la registrazione avanzata. Per ulteriori informazioni, vedi [Come abilitare la registrazione avanzata](#howtoenableadvancedlogging), riavvia l’applicazione desktop Adobe Learning Manager e ripeti i passaggi sopra riportati che causano l’errore. Per richiedere assistenza, invia gli ultimi registri delle applicazioni all’amministratore di Adobe Learning Manager. Per ulteriori informazioni, consulta [Come trovare i registri delle applicazioni](#howtofindapplicationlogs).

+++

+++Non riesco a visualizzare o aprire i miei progetti precedenti

1. Puoi vedere solo i progetti creati con il tuo account Adobe Learning Manager sullo stesso computer su cui li hai realizzati.
1. Ripristina le preferenze dell’applicazione, quindi riavvia l’applicazione desktop Adobe Learning Manager e riprova. Per informazioni, consultate [Come ripristinare le preferenze dell’applicazione](#howtoresetapplicationpreferences).
1. Per gli errori durante l&#39;apertura dei progetti, abilita la registrazione avanzata. Per ulteriori informazioni, consulta [Come abilitare la registrazione avanzata](#howtoenableadvancedlogging). Riavvia l’applicazione desktop Adobe Learning Manager e ripeti i passaggi che causano l’errore. Per richiedere assistenza, invia gli ultimi registri delle applicazioni all’amministratore di Adobe Learning Manager. Per ulteriori informazioni, consulta [Come trovare i registri delle applicazioni](#howtofindapplicationlogs).

+++

## Come si ripristinano le preferenze dell’applicazione? {#howtoresetapplicationpreferences}

### Windows {#windows}

1. Per aprire la finestra di dialogo Esegui, premere il tasto **Windows + R** tasti.
1. Tipo `**%APPDATA%\\..\\Local\\Adobe\\Learning Manager 1.0**` e premi Invio.
1. Elimina i file denominati **preferences.json** e **preferences.xml**.

### Mac OS X {#macosx}

1. Apri il Finder.
1. Per aprire il **Vai a** cartella, premere **Cmd+Maiusc+G** tasti.
1. Tipo `**~/Library/Application Support/Adobe/Learning Manager 1.0**` e premi Invio.
1. Elimina i file denominati **preferences.json** e **preferences.xml**.

## Come trovare i registri delle applicazioni {#howtofindapplicationlogs}

### Windows {#application-logs}

1. Per aprire la finestra di dialogo Esegui, premere **Windows + R** tasti.
1. Tipo `**%TEMP%\\elthor**` e premi Invio.
1. Ordinare le cartelle in base al **Data modifica** e aprire la cartella più recente. Questa cartella contiene i registri dell&#39;applicazione più recenti.

### Mac OS X {#MacOSX-1}

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

### Mac OS X {#MacOSX-2}

1. Apri il Finder.
1. Per aprire il **Vai alla cartella** finestra di dialogo, premere **Cmd+Maiusc+G**.
1. Digita &quot;**~/Libreria/Application Support/Adobe/Learning Manager 1.0**&quot; (senza virgolette) e premi Invio.
1. Esegui un backup del file **preferences.json** e aprilo in un editor di testo.
1. Cerca la chiave **debugMode** e modifica la proprietà value di questa chiave in &quot;**vero**&quot; (senza virgolette)

## Come impostare le autorizzazioni per webcam/microfono in Mac OS X Mojave? {#howtosetwebcammicrophonepermissionsonmacosxmojave}

1. Fai clic **[!UICONTROL Preferenze di sistema]** icona nel Dock.
1. Fai clic **[!UICONTROL Sicurezza e privacy]** > **[!UICONTROL Privacy].**
1. Fai clic su **[!UICONTROL Opzioni webcam e microfono]** e assicurati che la casella di controllo di Adobe Learning Manager sia selezionata. Se Adobe Learning Manager non è elencato, prima installa e avvia l’applicazione desktop Adobe Learning Manager.

## Come ripulire la cache degli aggiornamenti di Adobe Learning Manager per desktop? {#howtocleanupadobecaptivateprimefordesktopupdatescache}

### Windows {#clean-previous-installation}

1. Per aprire la finestra di dialogo Esegui, premere **Tasto Windows + R**.
1. Tipo `**%APPDATA%\\..\\Local\\Adobe\\Learning Manager 1.0**` e premi Invio.
1. Elimina la cartella **updates**.

### Mac OS X {#MacOSX-3}

1. Apri il Finder.
1. Per aprire il **Vai alla cartella** finestra di dialogo, premere **Cmd+Maiusc+G**.
1. Tipo `**~/Library/Application Support/Adobe/Learning Manager 1.0**` e premi Invio.
1. Elimina la cartella **updates**.

## Come ripulire la cartella temporanea di Adobe Learning Manager per desktop? {#howtocleanupadobecaptivateprimefordesktoptempfolder}

### Windows {#clean-previous-installation-1}

1. Per aprire la finestra di dialogo Esegui, premere **Tasto Windows + R**.
1. Digita &quot;**%TEMP%**&quot; (senza virgolette) e premi Invio.
1. Elimina la cartella &quot;**elthor**&quot;.

### Mac OS X {#MacOSX-4}

1. Apri il Finder.
1. Per aprire il **Vai alla cartella** finestra di dialogo, premere **Cmd+Maiusc+G** tasti.
1. Digita &quot;**/var/folders**&quot; (senza virgolette) e premi Invio.
1. Cerca &quot;**elthor**&quot; nella barra di ricerca.
1. Elimina la cartella &quot;**elthor**&quot;.

## Come individuare i progetti Adobe Learning Manager per i desktop? {#howtolocateadobecaptivateprimefordesktopprojects}

### Windows {#Windows-2}

1. Per aprire la finestra di dialogo Esegui, premere **Tasto Windows + R**.
1. Digita &quot;**~/Documenti/Il mio Adobe di progetti Learning Manager**&quot; (senza virgolette) e premi Invio.
1. Tu o l’amministratore di Adobe Learning Manager potreste aver cambiato il percorso predefinito della cartella dei progetti. Contatta l&#39;amministratore per ulteriore assistenza per individuare e rimuovere i progetti.

### Mac OS X {#MacOSX-5}

1. Apri il Finder.
1. Per aprire il **Vai alla cartella** finestra di dialogo, premere **Cmd+Maiusc+G** tasti.
1. Digita &quot;**~/Documenti/Il mio Adobe di progetti Learning Manager**&quot; (senza virgolette) e premi Invio.

   Tu o l’amministratore di Adobe Learning Manager potreste aver cambiato il percorso predefinito della cartella dei progetti. Per ulteriore assistenza per l’individuazione e la pulizia dei progetti, contatta l’amministratore.

## Come rimuovere tutte le precedenti installazioni dell’applicazione desktop Adobe Learning Manager? {#howtocleanuppreviousinstallationsofadobelearningmanagerdesktopapp}

### Windows {#Windows-3}

1. Per aprire il **Finestra di dialogo Esegui,** premere **Tasti Windows + R**.
1. Digita regedit e cerca &quot;**HKEY_LOCAL_MACHINE \\SOFTWARE\\Classes\\Installer\\**&quot; (senza virgolette) o &quot;**HKEY_LOCAL_MACHINE\\SOFTWARE\\Microsoft\\Windows\\CurrentVersion\\Installer\\UserData\\S-1-5-18\\Products\\**&quot; (senza virgolette) e premi Invio.
1. Trova la cartella denominata Adobe Learning Manager e individua l’installazione precedente. Elimina la voce del Registro di sistema.  Per individuare il tasto, premere F3.

### Mac OS X {#MacOSX-6}

Sposta i file dal seguente percorso &quot;**/Applicazioni/Adobe Learning Manager/Utenti/Condiviso/Adobe/Risorse Learning Manager/1.0**&quot; per scaricare il cestino e poi svuotarlo.
