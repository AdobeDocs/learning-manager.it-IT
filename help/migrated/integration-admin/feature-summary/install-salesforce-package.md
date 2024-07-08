---
jcr-language: en_us
title: Installazione del pacchetto Salesforce
description: Learning Manager offre un pacchetto di app Salesforce. Una volta installato e configurato in SFDC, gli addetti alle vendite possono svolgere le proprie attività di formazione all’interno del portale SFDC. Questa app consente agli utenti di SFDC di esplorare nuovi corsi di formazione, visualizzare i consigli e consultarli direttamente all’interno del portale SFDC. Gli utenti ricevono anche gli annunci inviati dagli amministratori sotto forma di masthead direttamente all'interno dell'app all'interno del portale SFDC.
contentowner: saghosh
exl-id: 2b1c32e7-81af-4c13-a2bd-66684cde084e
source-git-commit: fb946ae98dce45156e2f4c1cf992319405403ea9
workflow-type: tm+mt
source-wordcount: '1055'
ht-degree: 47%

---

# Installazione del pacchetto Salesforce

## Panoramica

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

![](assets/uninstall-package.png)

*Installare il pacchetto di Learning Manager*

>[!NOTE]
>
>L&#39;app Adobe Learning Manager è supportata solo nella visualizzazione Salesforce Lightning.

1. Avvia l&#39;URL](https://test.salesforce.com/packaging/installPackage.apexp?p0=04tDb000000LRvP) del [pacchetto di Learning Manager.
1. **Nella pagina Login**, fai clic su **[!UICONTROL Usa dominio]** personalizzato.

1. Immetti l&#39;URL del pacchetto e fai clic su **[!UICONTROL Continua]**. Nella pagina di installazione deve essere selezionata l&#39;opzione Installa solo per amministratori. Non cambiare questa opzione.
1. Fai clic su **Insalto**. Una volta installato il pacchetto, fai clic su **[!UICONTROL Fine]**. Si apre la pagina Pacchetti installati in cui puoi visualizzare il pacchetto Adobe Learning Manager installato.

1. Vai all’App Launcher (accanto a Configurazione) e cerca Adobe Learning Manager.
1. Per configurare l&#39;app, fai clic su **[!UICONTROL Configura]**.
1. Fai clic su **[!UICONTROL Nuovo]** e aggiungi i seguenti dettagli:

   * **Configurazione:** immetti il nome che preferisci.
   * **ClientID**: immetti il valore ottenuto dalla prima sezione.
   * **ClientSecret:** immettere il valore ottenuto dalla prima sezione.
   * **RefreshToken:** immetti il valore ottenuto dalla prima sezione.
   * **LearningManagerBaseURL:** l&#39;URL del sito in cui è ospitato Learning Manager.
   * **Disattivazione del reindirizzamento:** disabilita il reindirizzamento alla home page dell’Allievo in Learning Manager.

>[!NOTE]
>
>È possibile creare una singola configurazione. Se provi ad aggiungere un’altra configurazione, visualizzerai un messaggio di errore. La configurazione mappa l’account Salesforce con l’account Allievo.

### Aggiunta delle impostazioni del sito remoto

1. Nell&#39;angolo superiore destro della pagina, fai clic su **[!UICONTROL Imposta]**.
1. In **Ricerca** rapida, cercare Impostazioni sito remoto.
1. Fare clic su **[!UICONTROL Nuovo sito]** remoto.
1. Immetti i seguenti dettagli:

   1. **Nome del sito remoto:** immetti il nome che preferisci.
   1. **URL del sito remoto:** l’URL del sito in cui è ospitato Learning Manager.

1. Avvia Learning Manager.

### Aggiungi il dominio Adobe agli URL attendibili di Salesforce

Per aggiungere il dominio Adobe agli URL attendibili, effettua le seguenti operazioni:

1. Nella console di Salesforce, vai a Configura **** > **[!UICONTROL Ricerca]** rapida.
1. **[!UICONTROL Cerca URL]** attendibili e seleziona **[!UICONTROL Nuovo URL]** attendibile.
1. Digita un nome nel **[!UICONTROL campo Nome]** API.
1. Digita `*.adobe.com` nel campo URL.
1. Selezionare tutte le caselle di controllo nelle **direttive CSP** e salvare le modifiche.
1. Modifica il token di aggiornamento dell&#39;app Salesforce e salvalo.
1. Riavvia l&#39;app Salesforce.

### Abilitazione delle notifiche per l’app Learning Manager

1. Nell&#39;angolo superiore destro, fai clic su **Imposta**.
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

### Profilo

Come amministratore Salesforce, puoi assegnare i profili agli utenti oppure creare un profilo personalizzato.

>[!NOTE]
>
>Gli utenti devono essere presenti sia in Salesforce che in Learning Manager.

![](assets/create-profile.png)

*Assegnare un profilo a un Allievo*

Quando aggiungi un Allievo, devi assegnare un profilo specifico all&#39;Allievo. Quindi vai a quel profilo e concedi l&#39;accesso richiesto.

Per consentire agli Allievi di visualizzare l&#39;app Learning Manager, è necessario abilitare l&#39;app per tutti gli Allievi.

Il passo successivo consiste nel fornire l’autorizzazione per accedere all’app Learning Manager.

![](assets/permission-set.png)

*Aggiungere autorizzazioni per accedere all&#39;app Learning Manager*

Quando installi il pacchetto, viene creato un nuovo set di autorizzazioni, **Adobe Learning Manager User**. Vai al set di autorizzazioni e aggiungi gli utenti.

Seleziona gli utenti e assegna le autorizzazioni di conseguenza. Gli Allievi ora possono accedere all’app Learning Manager.

Adesso, seleziona un profilo, ad esempio Profilo standard di un utente, quindi fai clic sul profilo. Fai clic su **[!UICONTROL Modifica e nella** sezione Impostazioni **app personalizzate seleziona la casella** di controllo Adobe Learning Manager **]**. In questo modo l’utente può accedere all’app.

Nella sezione **Impostazioni schede personalizzate**, nell’elenco a discesa **Home Allievo** seleziona l’opzione **[!UICONTROL Predefinito su]**.

È necessario rendere l’app visibile a tutti i profili.

Fai clic su **[!UICONTROL Salva]** e gli Allievi appartenenti a tutti i profili accederanno all&#39;app Learning Manager.
