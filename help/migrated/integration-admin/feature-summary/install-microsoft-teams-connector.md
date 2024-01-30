---
description: Installazione del connettore Microsoft Teams su Adobe Learning Manager
jcr-language: en_us
title: Installazione del connettore Microsoft Teams su Adobe Learning Manager
contentowner: saghosh
source-git-commit: ab6737e8b43222a6538921b0628a504a5f15859d
workflow-type: tm+mt
source-wordcount: '1258'
ht-degree: 24%

---



# Installazione del connettore Microsoft Teams su Adobe Learning Manager

## Panoramica

Microsoft® Teams® è una piattaforma di collaborazione persistente basata su chat che supporta in modo completo la condivisione di documenti, riunioni online e altre funzioni utili per le comunicazioni aziendali.

Adobe Learning Manager utilizza un connettore per aula virtuale che può essere utilizzato per integrare le riunioni di Microsoft Teams con Learning Manager.

Il connettore Microsoft Teams collega i sistemi Learning Manager e Microsoft Teams per consentire la sincronizzazione automatica delle riunioni virtuali. L’elenco riportato di seguito descrive le funzioni del connettore Microsoft Teams:

**Configurazione di sessioni virtuali tramite Microsoft Teams**

Questo connettore consente di integrare l’account Adobe Learning Manager con l’account Microsoft Teams. Una volta integrato, il connettore consente a un Autore in Learning Manager di utilizzare Microsoft Teams come fornitore di servizi tecnologici per i moduli aula virtuale creati in Learning Manager.

**Consenti ai Microsoft Teams di autenticare gli Allievi quando entrano in un’aula virtuale**

Questo connettore aiuta a configurare l’organizzatore della riunione dei Microsoft Teams da Learning Manager durante la creazione di una riunione. L’organizzatore della riunione può gestire la sala d’attesa in modo che l’accesso alla riunione sia limitato, ammettere partecipanti e controllare le altre opzioni della riunione fornite da Microsoft Teams.

**Utilizzare la sincronizzazione automatizzata di completamento degli utenti**

Il processo di sincronizzazione automatizzato di completamento degli utenti consente a un Amministratore Learning Manager di recuperare automaticamente i record di completamento e l’URL della registrazione della riunione di Microsoft Teams.

## Ruoli su Microsoft Teams

Se stai organizzando una riunione con più partecipanti, puoi assegnare ruoli a ciascuno di essi in modo che un partecipante possa sapere cosa può fare nella riunione.

È possibile scegliere tra due ruoli: **relatore** e **partecipante**.

Per ulteriori informazioni, consulta  [Ruoli in una riunione Teams - Microsoft](https://support.microsoft.com/en-us/office/roles-in-a-teams-meeting-c16fa7d0-1666-4dde-8686-0a0bfe16e019).

## Configurazione del connettore Microsoft Teams

>[!NOTE]
>
>Elementi contrassegnati &lt;developer optional=&quot;&quot;> di seguito sono riportati i tenant facoltativi e la maggior parte per la configurazione di tenant di sviluppo/di prova con Microsoft nel caso in cui l’utente non abbia un tenant di produzione. Queste operazioni sono facoltative poiché la maggior parte di esse sarebbe già stata eseguita dall&#39;amministratore del team.

## Creazione di un account Microsoft E5 per sviluppatori &lt;developer optional=&quot;&quot;>

Puoi accedere al connettore Microsoft Teams se hai Office 365 E3 o Office 365 E5. L’opzione consigliata è Office 365 E5.

* Visita il sito [Pagina dei piani Microsoft](https://www.microsoft.com/en-in/microsoft-365/enterprise/compare-office-365-plans?&amp;ef_id=CjwKCAjw8cCGBhB6EiwAgORey9Tjrae-dyAsBrzvXdVJ5WCcoQ55wySzUBMoo-EkPt7CoIqAtcWc0xoC9RcQAvD_BwE:G:s&amp;OCID=AID2100137_SEM_CjwKCAjw8cCGBhB6EiwAgORey9Tjrae-dyAsBrzvXdVJ5WCcoQ55wySzUBMoo-EkPt7CoIqAtcWc0xoC9RcQAvD_BwE:G:s&amp;lnkd=Google_O365SMB_Brand&amp;gclid=CjwKCAjw8cCGBhB6EiwAgORey9Tjrae-dyAsBrzvXdVJ5WCcoQ55wySzUBMoo-EkPt7CoIqAtcWc0xoC9RcQAvD_BwE) . Sulla pagina Web, puoi acquistare un account E3 o E5 o fare clic su Prova gratuitamente.

* Inserisci le informazioni richieste e crea un account.

>[!NOTE]
>
>L’account deve utilizzare il formato `<username>@<company name>.onmicrosoft.com`.

## Creazione applicazione per connettore Microsoft Teams

1. Visita il sito  [Portale Microsoft Azure®](https://portal.azure.com/).
1. Accedi con l’account Microsoft E5 che hai creato nella sezione precedente.
1. Cerca **Azure Active Directory**.
1. Fai clic **[!UICONTROL Registrazioni app]**.
1. Fai clic **[!UICONTROL Nuova registrazione]**, inserisci i seguenti dettagli e registra l’applicazione:

   1. **Nome** - Qualsiasi nome a tua scelta.
   1. **Tipi di account supportati** - Account in qualsiasi directory dell’organizzazione (Qualsiasi Azure Active Directory - Multitenant)
   1. **URI di reindirizzamento (facoltativo)** - Campo facoltativo con l’URL di risposta.

1. Nella **Essenziali** tieni presente i seguenti ID, che saranno utilizzati durante l’integrazione:

   1. **ID applicazione (client)**
   1. **ID directory (tenant)**

1. Cerca le credenziali del client e fai clic su **[!UICONTROL Aggiungi certificato o segreto]**.
1. Fai clic **[!UICONTROL Nuovo segreto client]** e aggiungi i seguenti dettagli:

   1. **Descrizione** - Immettere un nome qualsiasi.
   1. **Scadenza** - Impostato su un valore qualsiasi (il valore consigliato è 24 mesi. Assicurati che al momento della scadenza vengano generate nuove credenziali).

Prendi nota del segreto client, che verrà utilizzato durante l’integrazione.

## Ottieni l’autorizzazione di accesso per il connettore Microsoft Teams

1. Visita il sito  [Portale Microsoft Azure](https://portal.azure.com/).
1. Accedi con il Microsoft E5 che hai creato in precedenza.
1. Cerca **Azure Active Directory**.
1. Fai clic **[!UICONTROL Registrazioni app]**.
1. Fai clic sull’app che hai creato nella sezione precedente.
1. Fai clic **[!UICONTROL Autorizzazioni API]**.
1. Fai clic **[!UICONTROL Aggiungi un&#39;autorizzazione]**.
1. Seleziona **[!UICONTROL Microsoft Graph]** > **[!UICONTROL Autorizzazioni applicazione]** e aggiungi le seguenti autorizzazioni:

   1. Chat.Read.All
   1. Directory.Read.All
   1. OnlineMeetingArtifact.Read.All
   1. OnlineMeetings.Read.All
   1. OnlineMeetings.ReadWrite.All
   1. User.Read.All

1. Fai clic **[!UICONTROL Concedere l&#39;accesso come amministratore, ad Adobe]**.
1. Fai clic **[!UICONTROL Ruoli app]** > **[!UICONTROL Crea ruolo dell’app]**.
1. Immetti i seguenti valori:

   1. **Nome visualizzato** - Nome dell’API/dell’autorizzazione (Esempio: Calendars.ReadWrite).

   1. **Tipi di membri consentiti** - Specificare sia gli utenti che le applicazioni (Utenti/gruppi + applicazioni).

   1. **Valore** - Nome dell’API/dell’autorizzazione (Esempio: Calendars.ReadWrite).

   1. **Descrizione** - Nome dell’API/dell’autorizzazione (Esempio: Calendars.ReadWrite).

   1. **Abilitare questo ruolo dell&#39;app?** - Selezionare questa casella di controllo.

1. Ripeti i passaggi precedenti per tutte le nove API/Autorizzazioni aggiunte.

## Configurare i criteri di accesso utilizzando gli script di PowerShell

Per configurare i criteri di accesso dell&#39;applicazione per il connettore Microsoft Teams eseguendo gli script PowerShell, seguire la procedura descritta in questa sezione  [documento](https://docs.microsoft.com/en-us/graph/cloud-communication-online-meeting-application-access-policy).

Questa azione consente al connettore di accedere alle riunioni online di Microsoft Teams.

>[!NOTE]
>
>Nel documento precedente, esegui anche il passaggio facoltativo numero 5 per assicurarti che ad ogni utente attivo possa essere assegnato il ruolo di organizzatore dall’interno dell’app per autori di Learning Manager. Se questo passaggio non viene eseguito, gli utenti non avranno le autorizzazioni di accesso necessarie per gli organizzatori e la creazione della riunione non andrà a buon fine (gli API Microsoft considerano l’organizzatore il creatore di una riunione Teams).

## Configurazione del connettore Microsoft Teams in Learning Manager

1. Accedi a Learning Manager in qualità di Amministratore di integrazione.

1. Nella pagina Connettori, seleziona il connettore Microsoft Teams e fai clic su **[!UICONTROL Connetti]**.

1. Immetti i seguenti valori:

   1. **Nome connessione** - Specifica il nome che l’autore vedrà durante la creazione della sessione.

   1. **ID tenant Microsoft Teams** - Immettere il valore indicato in precedenza.

   1. **ID client Microsoft Teams** - Immettere il valore indicato in precedenza.

   1. **Segreto client Microsoft Teams** - Immettere il valore indicato in precedenza.

   1. **E-mail utente amministratore Microsoft Teams** - Immetti l’e-mail dell’organizzatore predefinito. Questo utente (di solito un utente del servizio) diventa il creatore della riunione nel caso in cui non venga selezionato alcun organizzatore dall’app per autori di Learning Manager.

## Allocare le licenze agli utenti &lt;developer optional=&quot;&quot;>

1. Visita [https://admin.microsoft.com/#/homepage](https://admin.microsoft.com/#/homepage).
1. Fai clic **[!UICONTROL Utenti]** > **[!UICONTROL Utenti attivi]**.
1. Fai clic **[!UICONTROL Altre azioni per gli utenti]** per gli utenti a cui desideri concedere l’accesso ai Microsoft Teams.
1. Fai clic **[!UICONTROL Gestione delle licenze dei prodotti]**.
1. Abilita la licenza per Office 365 E5 senza audioconferenze.

## Registrare una sessione

L’API utilizzato per la registrazione della sessione è un API protetto. Per accedere all’API, è necessario richiedere l’accesso a Microsoft. Per ulteriori informazioni, consulta questo articolo  [documento](https://docs.microsoft.com/en-us/graph/teams-protected-apis).

Nel documento,

*&quot;Per richiedere l’accesso a queste API protette, completa quanto segue  [modulo di richiesta](https://aka.ms/teamsgraph/requestaccess). Lavoriamo sulle richieste di accesso ogni mercoledì e inviamo le approvazioni ogni venerdì, a eccezione delle settimane dei principali giorni festivi degli USA. Le richieste ricevute durante queste settimane saranno elaborate durante la settimana successiva (senza giorni festivi). Per verificare se la tua richiesta è stata approvata, testa l&#39;accesso dell&#39;applicazione il prossimo lunedì applicabile.&quot;*

Per gli allievi, l’URL della registrazione è mostrato sulla pagina con la panoramica del corso in aula virtuale.

Dopo 30 minuti dal completamento di un corso, la presenza dell’allievo viene registrata.

## Domande frequenti

+++Chi sono gli organizzatori e i relatori?

Visualizza la  [documentazione](https://support.microsoft.com/en-us/office/roles-in-a-teams-meeting-c16fa7d0-1666-4dde-8686-0a0bfe16e019) da Microsoft per ruoli e funzionalità diverse supportate dai Microsoft Teams.

+++

+++È necessario che un organizzatore sia un utente registrato sia su Learning Manager che sui Microsoft Teams?

Sì, l’organizzatore deve far parte sia di Learning Manager che di Microsoft Teams. Inoltre, l’organizzatore deve far parte dello stesso tenant Microsoft, che è configurato nell’app dell’Amministratore di integrazione.

+++

+++È necessario che un relatore sia un utente registrato sia su Learning Manager che sui Microsoft Teams?

Sì, il relatore deve far parte sia di Learning Manager che di Microsoft Teams. Il relatore deve avere un ID Azure Active Directory (può far parte dello stesso tenant dell’organizzatore o di qualsiasi altro tenant). Inoltre, anche gli utenti anonimi (utenti che accedono solo con il nome utente e non fanno parte di Active Directory) possono ricevere il ruolo di relatori da parte dell’organizzatore o del relatore esistente durante una riunione.

+++

+++Microsoft Teams ha riunioni, webinar ed eventi dal vivo. Quale di questi è supportato dal connettore di Teams?

Al momento, il connettore Teams supporta solo le riunioni in Microsoft Teams. Per ulteriori informazioni, consulta questo articolo  [documento](https://docs.microsoft.com/en-us/microsoftteams/quick-start-meetings-live-events).

+++
