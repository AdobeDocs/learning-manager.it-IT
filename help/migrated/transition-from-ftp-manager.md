---
title: Transizione da Gestione FTP di Adobe
description: Adobe Learning Manager supporta un nuovo connettore utilizzando il protocollo SFTP della famiglia AWS Transfer. Potete sostituire qualsiasi client FTP open source con FTP Manager di Adobe.
source-git-commit: aa8030e7e1d0ad72b76fb48a34e7b15ddf178a0b
workflow-type: tm+mt
source-wordcount: '1041'
ht-degree: 0%

---


# Transizione da Gestione FTP di Adobe

Adobe Learning Manager supporta un nuovo connettore utilizzando il protocollo SFTP della famiglia AWS Transfer.

Potete sostituire qualsiasi client FTP open source con FTP Manager di Adobe.

Sono elencati alcuni client FTP consigliati da AWS [qui](https://docs.aws.amazon.com/transfer/latest/userguide/transfer-file.html):

* FileZilla (Windows, macOS e Linux)
* OpenSSH (macOS e Linux) - Nota: questo client funziona solo con server abilitati per il protocollo SFTP (Secure Shell).
* WinSCP (solo Microsoft)
* Cyberduck (Windows, macOS e Linux)

## Configurazione del connettore FTP basato su AWS

È necessario configurare il nuovo connettore FTP basato su AWS nell’Amministratore dell’integrazione.

![immagine connettori](assets/alm-ftp.png)
*Seleziona l’opzione FTP*

Una volta effettuata la connessione, viene visualizzata la pagina Dettagli connessione.

![pagina dettagli connessione](assets/connection-name.png)
*Visualizza la pagina dei dettagli della connessione*

Sono disponibili tre opzioni di autenticazione:

### Crea autenticazione generando nuove chiavi SSH

Se desideri generare la chiave SSH nel tuo sistema, puoi farlo. Fai clic su Genera chiave SSH.

La chiave privata viene scaricata nel computer e la chiave pubblica viene salvata nei nostri servizi. Dopo aver fatto clic su Connetti, l’utente FTP viene creato con le chiavi pubbliche e private come autenticazione.

Hai creato una connessione FTP.

### Creazione dell&#39;autenticazione mediante le chiavi SSH esistenti

Se disponi già di una chiave SSH, incolla la chiave pubblica nel **[!UICONTROL Chiave pubblica FTP]** e quindi fare clic su Connetti.

![Tasti SSH](assets/ssh-keys.png)
*Incollare i tasti*

### Creare l’autenticazione di base utilizzando una password

Questo è il meccanismo di autenticazione di base. Selezionate la prima opzione, **[!UICONTROL Creare l’autenticazione di base utilizzando una password]**. Immettere la password e fare clic su **[!UICONTROL Connetti]**.

Viene creata una connessione.

## Passaggi successivi

### Configurazione del client FTP

Configurare la connessione su un client FTP (scelta consigliata nella sezione precedente) con le chiavi scaricate o le chiavi o la password esistenti.

### Esportazione test di esempio

* Nel client FTP, modificate la posizione dell’FTP ExaVault con la nuova posizione FTP. Il nuovo dominio è `http://almftp.adobelearningmanager.com/`.
* È inoltre necessario autorizzare l&#39;IP, `18.195.107.67`.
* Dopo l’autenticazione è necessario caricare e scaricare alcuni file di esempio da e verso il nuovo percorso FTP utilizzando client FTP esterni o script di automazione.
* È necessario trasferire i dati dalla posizione precedente a quella nuova.
* I criteri di conservazione dei dati per il connettore rimangono invariati. ExaVault ha inoltre supportato alcune policy di conservazione dei dati oltre alla policy ufficiale. Tali criteri di conservazione dei dati non saranno disponibili per il nuovo connettore. Verifica se il connettore utilizza qualsiasi tipo di conservazione dei dati oltre alle policy ufficialmente supportate.

### Cosa succede ai progetti di migrazione

| Stato | Consiglio |
|---|---|
| Nuova migrazione | Non è possibile avviare nuove migrazioni dal vecchio FTP. Per le nuove migrazioni è necessario utilizzare il nuovo FTP. Per ulteriore supporto, contatta il team Customer Success. |
| Migrazione in corso | Creazione di uno sprint: puoi continuare a utilizzare il vecchio FTP, ma ti consigliamo di utilizzare il nuovo FTP. Contatta il team Customer Success per qualsiasi sprint esistente che non possa essere spostato. |
| Migrazione chiusa | Nessuna azione. |

## Connettersi all’Adobe di Learning Manager tramite il client FTP Filezilla

1. Collega al nuovo connettore FTP ALM. Fai clic su Connetti.

   ![connetti immagine](assets/connect-client.png)
   *Collegamento al nuovo connettore FTP ALM*

1. Per connettersi tramite autenticazione di base tramite password, immetti il nome di dominio e il nome utente FTP e imposta la password che soddisfa i criteri di convalida della password. Fai clic su Connetti. La nuova connessione FTP verrà creata e sarà accessibile tramite qualsiasi client SFTP.

   ![impostazioni ftp](assets/connect-settings.png)
   *tramite autenticazione di base tramite password*

1. Installa qualsiasi client SFTP, ad esempio File Zilla. Avvia File Zilla e fai clic su Apri Gestione siti nell&#39;angolo in alto a sinistra.

   ![Client SFTP](assets/sftp-client-install.png)
   *Connessione tramite client SFTP*

1. Fai clic **[!UICONTROL Nuovo sito]** per creare un nuovo sito. Rinomina il sito in base alle esigenze.

   ![nuovo sito](assets/new-site.png)
   *Creare un sito*

1. Mappatura dei dettagli dalla pagina delle credenziali del connettore.

   * Selezionare il protocollo come &#39;SFTP - SSH File Transfer Protocol&#39;
   * Host come dominio FTP
   * Tipo di accesso: &#39;Richiedi password&#39;
   * Nome utente FTP

1. Fai clic su Connetti.

   ![credenziali](assets/connector-credentials.png)
   *Immettere le credenziali*

   >[!NOTE]
   >
   >Esegui questo passaggio nel client File Zilla.

1. Immettere la password.

   (Facoltativo) Selezionare la casella di controllo Memorizza password per memorizzare la password.

   ![password](assets/password.png)
   *Immetti la password*

   (Facoltativo) Selezionate **[!UICONTROL Considera sempre attendibile l&#39;host]** casella di controllo per considerare attendibile l&#39;host.

1. Fai clic su OK.

   ![chiave host sconosciuta](assets/unknown-host-key.png)
   *Chiave host*

1. Controllare lo stato e l&#39;avanzamento della connessione nella parte superiore.

   La metà sinistra è il sito locale, mentre la metà destra è il sito remoto.

   Per spostare i file da locale a remoto e viceversa:

   * Puoi trascinare i file.
   * Fare doppio clic sul file.

   ![stato della connessione](assets/connection-status-progress.png)
   *Controllare lo stato della connessione*

In qualsiasi momento puoi modificare e aggiornare il tipo di autenticazione.

Altre modalità di autenticazione sono tramite le chiavi SSH:

Incolla la chiave pubblica nella casella di testo per utilizzare le chiavi SSH esistenti. Fai clic su Connetti/Salva.

Per generare nuove chiavi SSH, fare clic sul pulsante &#39;**[!UICONTROL Genera chiave SSH]**&#39;. La chiave privata verrà scaricata. Fai clic **[!UICONTROL Connetti/Salva]**.

![genera chiave ssh](assets/ssh-key.png)
*Genera chiave SSH*

Mappate i dettagli. Selezionare il tipo di accesso come file di chiave. Selezionare il file della chiave privata.

Fai clic **[!UICONTROL Connetti]**.

## Cosa succede dopo la rimozione di ExaVault

Una volta che ExaVault è stato dichiarato obsoleto, tutti i progetti di migrazione esistenti in corso verranno trasferiti al nuovo FTP come percorso di origine. È quindi necessario configurare il nuovo connettore FTP e continuare il processo di migrazione.

## Recommendations per migrare gli sprint

Durante la creazione di un progetto di migrazione, l’Adobe consiglia di crearlo utilizzando il nuovo connettore SFTP di AWS per evitare la migrazione sprint da Exavault ad AWS in una fase successiva.

Se è in corso una migrazione, chiudere lo sprint corrente che utilizza Exavault come origine dati. Crea la connessione SFTP AWS, verifica la configurazione e contatta il team Customer Success per passare alla nuova origine dati SFTP AWS. Dopo il passaggio, crea un nuovo sprint nello stesso progetto di migrazione. Le cartelle sprint vengono create nel nuovo percorso e puoi caricare i file CSV di migrazione per continuare l’attività.

**Casi in cui non è possibile chiudere un progetto di migrazione**

* La mappatura dell’ID corso viene eseguita nel progetto corrente per i corsi migrati da sistemi legacy esterni ad Adobe Learning Manager. Puoi farlo solo se desideri aggiornare gli stessi corsi nello stesso progetto. Una volta chiuso il progetto, non è possibile modificarne i dettagli.
* Per i progetti di migrazione basati su API, in cui non è necessario chiudere un progetto.
