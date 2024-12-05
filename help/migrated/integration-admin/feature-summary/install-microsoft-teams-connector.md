---
description: Installazione del connettore Microsoft Teams su Adobe Learning Manager
jcr-language: en_us
title: Installazione del connettore Microsoft Teams su Adobe Learning Manager
contentowner: saghosh
exl-id: 68092187-ac69-4727-a3dc-f3047a1e164d
source-git-commit: 6192559436074c3270644850b202589961e7b81b
workflow-type: tm+mt
source-wordcount: '1138'
ht-degree: 17%

---

# Installazione del connettore Microsoft Teams su Adobe Learning Manager

## Panoramica

Microsoft Teams® è una piattaforma di collaborazione persistente basata su chat che supporta completamente la condivisione di documenti, riunioni online e altre funzionalità per le comunicazioni aziendali.

Adobe Learning Manager utilizza un connettore per aula virtuale che può essere utilizzato per integrare le riunioni di Microsoft Teams con Learning Manager.

Il connettore Microsoft Teams collega i sistemi Learning Manager e Microsoft Teams per consentire la sincronizzazione automatica delle riunioni virtuali. L’elenco riportato di seguito descrive le funzioni del connettore Microsoft Teams:

**Configurare sessioni virtuali utilizzando Microsoft Teams**

Questo connettore consente di integrare l’account Adobe Learning Manager con l’account Microsoft Teams. Una volta integrato, il connettore consente a un Autore in Learning Manager di utilizzare Microsoft Teams come fornitore di servizi tecnologici per i moduli aula virtuale creati in Learning Manager.

**Consenti ai Microsoft Teams di autenticare gli Allievi quando entrano in un’aula virtuale**

Questo connettore aiuta a configurare l’organizzatore della riunione dei Microsoft Teams da Learning Manager durante la creazione di una riunione. L’organizzatore della riunione può gestire la sala d’attesa in modo che l’accesso alla riunione sia limitato, ammettere partecipanti e controllare le altre opzioni della riunione fornite da Microsoft Teams.

**Utilizzare la sincronizzazione automatizzata di completamento degli utenti**

Il processo di sincronizzazione automatizzato di completamento degli utenti consente a un Amministratore Learning Manager di recuperare automaticamente i record di completamento e l’URL della registrazione della riunione di Microsoft Teams.

## Ruoli su Microsoft Teams

Se stai organizzando una riunione con più partecipanti, puoi assegnare ruoli a ciascuno di essi in modo che un partecipante possa sapere cosa può fare nella riunione.

Ci sono due ruoli tra cui scegliere: **relatore** e **partecipante**.

Per ulteriori informazioni, consulta [Ruoli in una riunione Teams- Microsoft](https://support.microsoft.com/en-us/office/roles-in-a-teams-meeting-c16fa7d0-1666-4dde-8686-0a0bfe16e019).

## Configurazione del connettore Microsoft Teams

>[!NOTE]
>
>Gli elementi contrassegnati con la dicitura &lt;Sviluppatori/Facoltativo> qui sotto sono facoltativi, e si riferiscono alla configurazione di tenant di sviluppo/di prova con Microsoft nel caso in cui l’utente non abbia un tenant di produzione. Queste operazioni sono facoltative poiché la maggior parte di esse sarebbe già stata eseguita dall&#39;amministratore del team.

## Creare un account Microsoft E5 per sviluppatori &lt;Sviluppatori/Facoltativo>

Puoi accedere al connettore Microsoft Teams se hai Office 365 E3 o Office 365 E5. L’opzione consigliata è Office 365 E5.

* Visita la [pagina dei piani Microsoft](https://www.microsoft.com/en-in/microsoft-365/enterprise/compare-office-365-plans?&amp;ef_id=CjwKCAjw8cCGBhB6EiwAgORey9Tjrae-dyAsBrzvXdVJ5WCcoQ55wySzUBMoo-EkPt7CoIqAtcWc0xoC9RcQAvD_BwE:G:s&amp;OCID=AID2100137_SEM_CjwKCAjw8cCGBhB6EiwAgORey9Tjrae-dyAsBrzvXdVJ5WCcoQ55wySzUBMoo-EkPt7CoIqAtcWc0xoC9RcQAvD_BwE:G:s&amp;lnkd=Google_O365SMB_Brand&amp;gclid=CjwKCAjw8cCGBhB6EiwAgORey9Tjrae-dyAsBrzvXdVJ5WCcoQ55wySzUBMoo-EkPt7CoIqAtcWc0xoC9RcQAvD_BwE). Sulla pagina Web, puoi acquistare un account E3 o E5 o fare clic su Prova gratuitamente.
* Inserisci le informazioni richieste e crea un account.

>[!NOTE]
>
>L&#39;account deve utilizzare il formato `<username>@<company name>.onmicrosoft.com`.

## Creazione applicazione per connettore Microsoft Teams

1. Visita il [portale Microsoft Azure®](https://portal.azure.com/).
1. Accedi con l’account Microsoft E5 che hai creato nella sezione precedente.
1. Cerca **Azure Active Directory**.
1. Fai clic su **[!UICONTROL Registrazioni app]**.
1. Fai clic su **[!UICONTROL Nuova registrazione]**, inserisci i seguenti dettagli e registra l’applicazione:

   1. **Nome**: un nome a tua scelta.
   1. **Tipi di account supportati** - Account in qualsiasi directory dell&#39;organizzazione (Qualsiasi Azure Active Directory - Multitenant)
   1. **URI di reindirizzamento (facoltativo)**: campo facoltativo che indica l&#39;URL di risposta.

1. Nella colonna **Essenziali**, prendi nota degli ID seguenti, che verranno utilizzati durante l&#39;integrazione:

   1. **ID applicazione (client)**
   1. **ID directory (tenant)**

1. Cerca le credenziali client e fai clic su **[!UICONTROL Aggiungi certificato o segreto]**.
1. Fai clic su **[!UICONTROL Nuovo segreto client]** e aggiungi i seguenti dettagli:

   1. **Descrizione** - Immettere un nome qualsiasi.
   1. **Scadenza**: impostare un valore qualsiasi (il valore consigliato è 24 mesi. Assicurati che al momento della scadenza vengano generate nuove credenziali).

Prendi nota del segreto client, che verrà utilizzato durante l’integrazione.

## Ottieni l’autorizzazione di accesso per il connettore Microsoft Teams

1. Visita il [portale di Microsoft Azure](https://portal.azure.com/).
1. Accedi con il Microsoft E5 che hai creato in precedenza.
1. Cerca **Azure Active Directory**.
1. Fai clic su **[!UICONTROL Registrazioni app]**.
1. Fai clic sull’app che hai creato nella sezione precedente.
1. Fai clic su **[!UICONTROL Autorizzazioni API]**.
1. Fai clic su **[!UICONTROL Aggiungi autorizzazione]**.
1. Seleziona **[!UICONTROL Microsoft Graph]** > **[!UICONTROL Autorizzazioni applicazione]** e aggiungi le seguenti autorizzazioni:

   1. Chat.Read.All
   1. Directory.Read.All
   1. OnlineMeetingArtifact.Read.All
   1. OnlineMeetings.Read.All
   1. OnlineMeetings.ReadWrite.All
   1. User.Read.All
   1. OnlineMeetingRecording.Read.All

1. Fai clic su **[!UICONTROL Concedi accesso amministratore per Adobe]**.
1. Fai clic su **[!UICONTROL Ruoli app]** > **[!UICONTROL Crea ruolo app]**.
1. Immetti i seguenti valori:

   1. **Nome visualizzato** - Nome dell&#39;API/dell&#39;autorizzazione (Esempio: Calendars.ReadWrite).

   1. **Tipi di membri consentiti** - Specificare sia gli utenti che le applicazioni (Utenti/gruppi + applicazioni).

   1. **Valore** - Nome dell&#39;API/dell&#39;autorizzazione (Esempio: Calendars.ReadWrite).

   1. **Descrizione** - Nome dell&#39;API/dell&#39;autorizzazione (Esempio: Calendars.ReadWrite).

   1. **Abilitare questo ruolo dell&#39;app?** - Selezionare questa casella di controllo.

1. Ripeti i passaggi precedenti per tutte le nove API/Autorizzazioni aggiunte.

## Configurare i criteri di accesso utilizzando gli script di PowerShell

Per configurare i criteri di accesso dell&#39;applicazione per il connettore Microsoft Teams eseguendo gli script PowerShell, seguire la procedura descritta in questo [documento](https://docs.microsoft.com/en-us/graph/cloud-communication-online-meeting-application-access-policy).

Questa azione consente al connettore di accedere alle riunioni online di Microsoft Teams.

>[!NOTE]
>
>Nel documento precedente, esegui anche il passaggio facoltativo numero 5 per assicurarti che ad ogni utente attivo possa essere assegnato il ruolo di organizzatore dall’interno dell’app per autori di Learning Manager. Se questo passaggio non viene eseguito, gli utenti non avranno le autorizzazioni di accesso necessarie per gli organizzatori e la creazione della riunione non andrà a buon fine (gli API Microsoft considerano l’organizzatore il creatore di una riunione Teams).

## Configurazione del connettore Microsoft Teams in Learning Manager

1. Accedi a Learning Manager come **Amministratore dell’integrazione**.

1. Nella pagina Connettori, seleziona il connettore Microsoft Teams e fai clic su **[!UICONTROL Connetti]**.

1. Immetti i seguenti valori:

   1. **Nome connessione**: immetti il nome che l’autore vedrà durante la creazione della sessione.

   1. **ID tenant Microsoft Teams**: immetti il valore indicato in precedenza.

   1. **Microsoft Teams ID client**: immetti il valore indicato in precedenza.

   1. **Segreto client Microsoft Teams**: immetti il valore indicato in precedenza.

   1. E-mail utente amministratore di **Microsoft Teams**: inserisci l’e-mail dell’organizzatore predefinito. Questo utente (di solito un utente del servizio) diventa il creatore della riunione nel caso in cui non venga selezionato alcun organizzatore dall’app per autori di Learning Manager.

## Allocare le licenze agli utenti &lt;Sviluppatori/Facoltativo>

1. Visita [https://admin.microsoft.com/#/homepage](https://admin.microsoft.com/#/homepage).
1. Fai clic su **[!UICONTROL Utenti]** > **[!UICONTROL Utenti attivi]**.
1. Fai clic su **[!UICONTROL Altre azioni per gli utenti]** per gli utenti a cui desideri fornire accesso ai Microsoft Teams.
1. Fai clic su **[!UICONTROL Gestisci licenze prodotto]**.
1. Abilita la licenza per Office 365 E5 senza audioconferenze.

<!--## Record a session

The API used for recording a session is a protected API. To access the API, you must request access from Microsoft. For more information, see this  [document](https://docs.microsoft.com/en-us/graph/teams-protected-apis).

In the document,

*"To request access to these protected APIs, complete the following  [request form](https://aka.ms/teamsgraph/requestaccess). We review access requests every Wednesday and deploy approvals every Friday, except during major holiday weeks in the U.S. Submissions during those weeks will be processed the following non-holiday week. To verify whether your request has been approved, test your application access on the next applicable Monday."*

For learners, the recording URL is displayed on the VC course overview page.

After 30 minutes of completing a course, the attendance for the learner gets marked. -->

## Domande frequenti

+++Chi sono gli organizzatori e i relatori?

Consulta la [documentazione](https://support.microsoft.com/en-us/office/roles-in-a-teams-meeting-c16fa7d0-1666-4dde-8686-0a0bfe16e019) di Microsoft per i ruoli e le funzionalità diverse supportate dai Microsoft Teams.

+++

+++È necessario che un organizzatore sia un utente registrato sia su Learning Manager che sui Microsoft Teams?

Sì, l’organizzatore deve far parte sia di Learning Manager che di Microsoft Teams. Inoltre, l’organizzatore deve far parte dello stesso tenant Microsoft, che è configurato nell’app dell’Amministratore di integrazione.

+++

+++È necessario che un relatore sia un utente registrato sia su Learning Manager che sui Microsoft Teams?

Sì, il relatore deve far parte sia di Learning Manager che di Microsoft Teams. Il relatore deve avere un ID Azure Active Directory (può far parte dello stesso tenant dell’organizzatore o di qualsiasi altro tenant). Inoltre, anche gli utenti anonimi (utenti che accedono solo con il nome utente e non fanno parte di Active Directory) possono ricevere il ruolo di relatori da parte dell’organizzatore o del relatore esistente durante una riunione.

+++

+++Microsoft Teams ha riunioni, webinar ed eventi dal vivo. Quale di questi è supportato dal connettore di Teams?

Al momento, il connettore Teams supporta solo le riunioni in Microsoft Teams. Per ulteriori informazioni, consulta questo [documento](https://docs.microsoft.com/en-us/microsoftteams/quick-start-meetings-live-events).

+++
