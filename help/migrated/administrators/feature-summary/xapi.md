---
jcr-language: en_us
title: xAPI in Learning Manager
description: L’API Experience (xAPI) è una specifica del software di e-learning che consente ai contenuti di apprendimento e ai sistemi di apprendimento di comunicare tra loro in modo da registrare e tenere traccia di tutti i tipi di esperienze di apprendimento. Le esperienze di apprendimento sono registrate in un Learning Record Store (LRS). I Learning Record Store possono essere autonomi o esistere all’interno di sistemi LMS (Learning Management System) tradizionali.
contentowner: dvenkate
preview: true
source-git-commit: 53c1a5283295b56424d697bc26c5db31c2edca0f
workflow-type: tm+mt
source-wordcount: '801'
ht-degree: 48%

---



# xAPI in Learning Manager

## Cosa si intende per xAPI? {#whatisxapi}

L’API Experience (xAPI) è una specifica del software di e-learning che consente ai contenuti di apprendimento e ai sistemi di apprendimento di comunicare tra loro in modo da registrare e tenere traccia di tutti i tipi di esperienze di apprendimento. Le esperienze di apprendimento sono registrate in un Learning Record Store (LRS). I Learning Record Store possono essere autonomi o esistere all’interno di sistemi LMS (Learning Management System) tradizionali.

Per ulteriori informazioni su xAPI, consulta [Specifiche xAPIc](https://github.com/adlnet/xAPI-Spec).

## In che modo Learning Manager supporta xAPI? {#howdoeslearningmanagersupportxapi}

Learning Manager dispone di un Learning Record Store integrato. Questo LRS è perfettamente compatibile con le istruzioni xAPI provenienti da contenuti ospitati all’interno di Learning Manager. Accetta anche istruzioni xAPI create da terze parti. Queste istruzioni xAPI vengono memorizzate in Learning Manager e possono quindi essere esportate al di fuori di Learning Manager per essere visualizzate in qualsiasi sistema di data warehouse di terze parti.

## Quando si usa xAPI? {#whendoyouusexapi}

È sempre più diffusa la necessità di acquisire le esperienze di apprendimento dell&#39;utente finale che si svolgono su più sistemi.  È inoltre necessario tenere traccia dell’esatto coinvolgimento dell’Allievo nei contenuti di formazione. Non si tratta solo di Inizio, In corso e Completamento (che sono gli unici attributi acquisiti da SCORM).

## Utilizzo di xAPI in Learning Manager {#usingxapiinprime}

### Configurare l’applicazione {#setupyourapplication}

1. Accedi come amministratore dell’integrazione. Seleziona **[!UICONTROL Applicazioni > Registra]**.

   ![](assets/appregistration.png)

   *Pagina di avvio per la registrazione di un&#39;applicazione*

1. Registra una nuova applicazione.

   ![](assets/appregistration.png)

   *Registra una nuova applicazione*

1. Definire l&#39;ambito dell&#39;applicazione.

   * Se l’opzione **[!UICONTROL Accesso in lettura e scrittura xAPI del ruolo amministratore]** è abilitata, l’amministratore può pubblicare e ottenere documenti e istruzioni xAPI.
   * Se l’opzione **[!UICONTROL Accesso in lettura e scrittura xAPI del ruolo utente in formazione]** è abilitata, l’amministratore può pubblicare e ottenere documenti e istruzioni xAPI.

1. Salva le modifiche. Ottieni segreto e ID sviluppatore.

**End point**:

Fai clic sul collegamento di seguito per visualizzare il documento swagger xAPI:

[Documento Swagger xAPI](https://learningmanagereu.adobe.com/docs/primeapi/xapi/)

>[!NOTE]
>
>La versione xAPI supportata in Learning Manager è 1.0.3.


## Autenticazione API {#apiauthentication}

Le xAPI di Learning Manager utilizzano il framework OAuth 2.0 per autenticare e autorizzare le applicazioni client. Una volta registrata l’applicazione, puoi ottenere clientId e clientSecret. Get URL viene utilizzato nel browser in quanto autentica gli utenti di Learning Manager che utilizzano i loro account preconfigurati, ad esempio SSO, Adobe ID.

```
GET https://learningmanager.adobe.com/oauth/o/authorize?client_id=<Enter your clientId>&redirect_uri=<Enter a url to redirect to>&state=<Any String data>&scope=<admin:xapi or learner:xapi>&response_type=CODE.
```

## Tracciamento delle istruzioni xAPI come oggetto di apprendimento Learning Manager {#trackingxapistatementsasprimelo}

Come autore, ora puoi scegliere il modulo xAPI durante la creazione di corsi per monitorare l’esperienza degli utenti al di fuori di Learning Manager. Ad esempio, è possibile utilizzare questa funzione per valutare le attività degli utenti su una piattaforma di terze parti utilizzata per usufruire del corso.

1. Durante la creazione di un **[!UICONTROL modulo attività]**, nell&#39;opzione **[!UICONTROL Tipo]**&#x200B;utilizzare il menu a comparsa per selezionare **[!UICONTROL modulo basato su xAPI.]**

   ![](assets/xapimodulecreation.png)

   *Selezionare l&#39;opzione Modulo basato su xAPI*

1. Devi fornire un IRI. Se non viene fornito, Learning Manager ne genera uno automaticamente.

   L’IRI per un’attività è univoco in un account. Ciò significa che due moduli in Learning Manager non possono avere lo stesso IRI. Viene creato un nuovo IRI nei seguenti casi:

   * Quando un corso con modulo xAPI viene condiviso tra account.
   * Quando una certificazione con un modulo xAPI si ripete



   Qualsiasi istruzione xAPI con l’IRI menzionato viene monitorata nel modulo precedente e riflessa nei report di Learning Manager.

1. Per copiare l’IRI creato automaticamente, rivisita la pagina Modulo attività.
1. Pubblica il modulo.

**Punti da tenere presenti:**

* Learning Manager al momento supporta solo   mbox come identificatore. Gli altri identificatori, inclusi mboz_sha1, openid e account non sono supportati.

* L’ID stato e l’ID profilo sono UUID se utilizzati con Learning Manager.
* La richiesta PUT non sovrascrive il documento per agenti/profilo, attività/profilo e attività/stato di xAPI
* Il gruppo non identificato non è supportato in Actor.
* Il parametro &quot;related_activities&quot; non è supportato nell&#39;istruzione GET.
* I parametri “format=ids” e “format=canonical” non sono supportati nelle istruzioni GET.
* L’annullamento dell’istruzione xAPI non annulla le azioni che si sono verificate in Learning Manager quando l’istruzione è stata pubblicata.

## Creazione di rapporti {#generatereports}

I report xAPI possono essere generati come report Excel. Come amministratore, apri **[!UICONTROL Rapporti > Report Excel > Report di attività xAPI]**.

Il report scaricato recupera tutte le informazioni pubblicate dall’Allievo e dall’Amministratore per qualsiasi istruzione.

Gli stessi report possono essere generati/pianificati utilizzando connettori FTP e Box per qualsiasi integrazione di terze parti. Procedi come segue:

Accedi come **Amministratore dell’integrazione > Apri il connettore FTP/Box > Seleziona il report di attività xAPI** dal pannello a sinistra. Scegli di pianificare/generare un report.

![](assets/xapischedule.png)

*Pianificare o generare un report*

* Quando viene inviato solo il punteggio raw nell’istruzione xAPI senza il punteggio massimo, il punteggio del quiz non viene visualizzato in LT.

* Per ottenere il punteggio percentuale in Learning Manager, i punteggi ridimensionati vengono inviati tramite xAPI.

## Report di esempio {#samplereport}

[Report xAPI di esempio.](assets/xapireport8842560559890766717csv.zip)
