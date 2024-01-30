---
jcr-language: en_us
title: Installazione del pacchetto Salesforce
description: Learning Manager offre un pacchetto dell’app Salesforce. Una volta installato e configurato in SFDC, gli addetti alle vendite possono svolgere le proprie attività di formazione all’interno del portale SFDC. Questa app consente agli utenti di SFDC di esplorare nuovi corsi di formazione, visualizzare i consigli e consultarli direttamente all’interno del portale SFDC. Gli utenti ricevono anche gli annunci inviati dagli Amministratori sotto forma di masthead direttamente nell’app all’interno del portale SFDC.
contentowner: saghosh
source-git-commit: ab6737e8b43222a6538921b0628a504a5f15859d
workflow-type: tm+mt
source-wordcount: '979'
ht-degree: 51%

---



# Installazione del pacchetto Salesforce

## Panoramica

Learning Manager offre un pacchetto dell’app Salesforce. Una volta installato e configurato in SFDC, gli addetti alle vendite possono svolgere le proprie attività di formazione all’interno del portale SFDC. Questa app consente agli utenti di SFDC di esplorare nuovi corsi di formazione, visualizzare i consigli e consultarli direttamente all’interno del portale SFDC. Gli utenti ricevono anche gli annunci inviati dagli Amministratori sotto forma di masthead direttamente nell’app all’interno del portale SFDC.

### Configurazione nell’app Learning Manager

1. Accedi al tuo account Amministratore Learning Manager come Amministratore dell’integrazione.
1. Fai clic **[!UICONTROL Applicazioni]** > **[!UICONTROL App in primo piano]**.
1. Fai clic **[!UICONTROL Salesforce]**.
1. Nella pagina dell’app Salesforce, annota l’ID dell’applicazione (noto anche come ID client) e il segreto client indicato nella descrizione.
1. Fai clic **[!UICONTROL Approva]** e l&#39;app deve essere approvata correttamente.
1. Fai clic **[!UICONTROL Risorse per sviluppatori]** > **[!UICONTROL Token di accesso per test e sviluppo]**.
1. Nella sezione Ottieni codice OAuth, l’ID client e l’ambito devono essere impostati su - admin:read,admin:write. Fai clic **[!UICONTROL Invia]**.
1. In Richiedi Token di Aggiornamento, immetti l’ID client e il segreto client. Fai clic **[!UICONTROL Invia]** e annota il token di aggiornamento.

### Creazione dell’account nell’app Salesforce

1. Crea un account nella pagina di registrazione di Salesforce. È necessario creare un account Salesforce nella versione per sviluppatori o enterprise.  [URL di iscrizione sviluppatore](https://developer.salesforce.com/signup). Per registrarti a Salesforce, assicurati di utilizzare l’ID e-mail che hai utilizzato per Learning Manager.
1. Verifica il tuo account tramite l’e-mail di verifica.
1. Crea una password e accedi a Salesforce.
1. Annota l’URL di Salesforce dopo l’accesso (ad esempio, site.lightning.force.com)

### Installazione del pacchetto Learning Manager

Se desideri installare il pacchetto, devi innanzitutto eliminare il pacchetto esistente in Salesforce. Prima della disinstallazione, attiva le impostazioni, come illustrato di seguito. L’attivazione è obbligatoria, altrimenti non sarà possibile installare il pacchetto.

![](assets/uninstall-package.png)

*Installazione del pacchetto Learning Manager*

>[!NOTE]
>
>L’app di Adobe Learning Manager è supportata solo nella visualizzazione Salesforce Lightning.

1. Avvia il  [URL del pacchetto Learning Manager](https://nam04.safelinks.protection.outlook.com/?url=https%3A%2F%2Ftest.salesforce.com%2Fpackaging%2FinstallPackage.apexp%3Fp0%3D04t1k0000008YWn&amp;data=04%7C01%7Ckillamse%40adobe.com%7Cf588f553fc694d2edee108d9a5c74711%7Cfa7b1b5a7b34438794aed2c178decee1%7C0%7C0%7C637723097572585825%7CUnknown%7CTWFpbGZsb3d8eyJWIjoiMC4wLjAwMDAiLCJQIjoiV2luMzIiLCJBTiI6Ik1haWwiLCJXVCI6Mn0%3D%7C1000&amp;sdata=mhYKVdwvS4F7WPruy0Kvw%2FsqgWxzTQpaZJyEACu8CNw%3D&amp;reserved=0).
1. Nella **Accesso** pagina, fare clic su **[!UICONTROL Usa dominio personalizzato]**.

1. Immetti l’URL del pacchetto e fai clic su **[!UICONTROL Continua]**. Nella pagina di installazione deve essere selezionata l’opzione Installa solo per gli amministratori. Non cambiare questa opzione.
1. Fai clic **Insalto**. Una volta installato il pacchetto, fai clic su **[!UICONTROL Fine]**. Si apre la pagina Pacchetti installati in cui puoi visualizzare il pacchetto Adobe Learning Manager installato.

1. Vai all’App Launcher (accanto a Configurazione) e cerca Adobe Learning Manager.
1. Per configurare l’app, fai clic su **[!UICONTROL Configura]**.
1. Fai clic **[!UICONTROL Nuovo]** e aggiungi i seguenti dettagli:

   * **Configurazione:** immetti il nome che preferisci.
   * **ID client**: immettere il valore ottenuto nella prima sezione.
   * **Segreto client:** Immetti il valore ottenuto nella prima sezione.
   * **Token di aggiornamento:** Immetti il valore ottenuto nella prima sezione.
   * **LearningManagerBaseURL:** URL del sito in cui è ospitato Learning Manager.
   * **Disattivazione del reindirizzamento:** disabilita il reindirizzamento alla home page dell’Allievo in Learning Manager.

>[!NOTE]
>
>È possibile creare una sola configurazione. Se provi ad aggiungere un’altra configurazione, visualizzerai un messaggio di errore. La configurazione mappa l’account Salesforce con l’account Allievo.

### Aggiunta delle impostazioni del sito remoto

1. Nell’angolo superiore destro della pagina, fai clic su **[!UICONTROL Configurazione]**.
1. Ingresso **Ricerca rapida**, cerca Impostazioni sito remoto.
1. Fai clic **[!UICONTROL Nuovo sito remoto]**.
1. Immetti i seguenti dettagli:

   1. **Nome del sito remoto:** immetti il nome che preferisci.
   1. **URL del sito remoto:** l’URL del sito in cui è ospitato Learning Manager.

1. Avvia Learning Manager.

### Abilitazione delle notifiche per l’app Learning Manager

1. Nell’angolo in alto a destra, fai clic su **Configurazione**.
1. Cerca le notifiche personalizzate.
1. Fai clic **[!UICONTROL Nuovo]**.
1. Immetti i seguenti dettagli:

   1. **Nome notifica personalizzata:** LearningManagerNotification
   1. **Nome API:** LearningManagerNotification

1. Seleziona entrambi **Desktop** e **Dispositivi mobili** come canali supportati.

1. Fai clic su **[!UICONTROL Salva]**.
1. Per abilitare le notifiche push per i dispositivi mobili, esegui le operazioni descritte di seguito:

   1. Installa l’app mobile Salesforce sul tuo cellulare.
   1. Accedi all’app utilizzando le tue credenziali.
   1. Vai a **Configurazione** > **Impostazioni di recapito delle notifiche**.
   1. Aggiungi Salesforce per iOS e Android.

### Disinstallazione di Learning Manager da Salesforce

1. Nell’app Salesforce, passa a Pacchetti installati.
1. Fai clic **[!UICONTROL Disinstalla]**.

## Configurazione di Learning Manager per gli utenti Salesforce

L’app Learning Manager è disponibile anche per gli utenti presenti in qualsiasi account Salesforce. L’amministratore Salesforce può aggiungere utenti in base ai profili. I profili Salesforce sono simili a quelli di Learning Manager. Ad esempio, Amministratore, Amministratore dell’integrazione, Istruttore e così via. L’amministratore Salesforce può inoltre creare un profilo personalizzato.

### Profilo

Come amministratore Salesforce, puoi assegnare i profili agli utenti oppure creare un profilo personalizzato.

>[!NOTE]
>
>Gli utenti devono essere presenti sia in Salesforce che in Learning Manager.

![](assets/create-profile.png)

*Assegnare un profilo a un Allievo*

Quando aggiungi un Allievo, devi assegnargli un profilo specifico. Accedi a tale profilo e concedi l&#39;accesso richiesto.

È necessario abilitare l’app Learning Manager per tutti gli Allievi, affinché questi possano visualizzarla.

Il passo successivo consiste nel fornire l’autorizzazione per accedere all’app Learning Manager.

![](assets/permission-set.png)

*Aggiungi le autorizzazioni per accedere all’app Learning Manager*

Quando installi il pacchetto, viene creato un nuovo set di autorizzazioni: **Adobe Utente Learning Manager**. Accedi al set di autorizzazioni e aggiungi gli utenti.

Seleziona gli utenti e assegna le autorizzazioni di conseguenza. Gli Allievi ora possono accedere all’app Learning Manager.

Adesso, seleziona un profilo, ad esempio Profilo standard di un utente, quindi fai clic sul profilo. Fai clic **[!UICONTROL Modifica]** e nel **Impostazioni app personalizzate** , attiva la casella di controllo **Adobe di Learning Manager**. In questo modo l’utente può accedere all’app.

Nella sezione **Impostazioni schede personalizzate**, nell’elenco a discesa **Home Allievo** seleziona l’opzione **[!UICONTROL Predefinito su]**.

È necessario rendere l’app visibile a tutti i profili.

Fai clic **[!UICONTROL Salva]** e gli allievi appartenenti a tutti i profili accederanno all’app Learning Manager.
