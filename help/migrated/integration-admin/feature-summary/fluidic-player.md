---
description: Leggi questo articolo per scoprire come incorporare il lettore Fluidic in un’applicazione personalizzata.
jcr-language: en_us
title: Lettore Fluidic incorporato
contentowner: dvenkate
preview: true
source-git-commit: fba5e5ddc1964b485be473bf356806f234688cf4
workflow-type: tm+mt
source-wordcount: '1626'
ht-degree: 24%

---



# Lettore Fluidic incorporato

Leggi questo articolo per scoprire come incorporare il lettore Fluidic in un’applicazione personalizzata.

In quanto azienda, è ora possibile offrire un’esperienza personalizzata agli Allievi anche al di fuori di Learning Manager. Utilizzando l’API pubblica, è possibile recuperare tutte le informazioni relative agli oggetti di apprendimento, alle iscrizioni degli Allievi e all’avanzamento dell’apprendimento e visualizzarle sul sito Web. E cosa ancora più importante, è possibile incorporare il lettore Fluidic di Learning Manager nel sito Web, in modo che l’utente possa utilizzare il contenuto direttamente nel sito Web. Il lettore Fluidic consente di riprodurre qualsiasi contenuto supportato da Learning Manager. Quando viene incorporato nel tuo sito Web, ha le stesse funzionalità di quando viene utilizzato in Learning Manager.

**Riproduci qualsiasi contenuto di eLearning[](../../learners/feature-summary/fluidic-player.md#main-pars_text_779047019)**

Il lettore Fluidic riproduce praticamente qualsiasi tipo di contenuto di eLearning in modo coerente e intuitivo senza richiedere plug-in o download. L’Allievo può avviare il contenuto e, indipendentemente dal tipo di file contenuto, inizia la riproduzione.

**Note e segnalibri**

È possibile prendere appunti e contrassegnare qualsiasi contenuto indipendentemente dal relativo tipo di file. Se desideri effettuare una selezione da un file o video lungo, puoi aggiungere un segnalibro ai punti effettivi in cui hai trovato le informazioni pertinenti alle tue esigenze. Le note e i segnalibri possono essere cercati o inviati come e-mail. Facendovi clic vieni reindirizzato al lettore Fluidic esattamente al punto del video o della pagina del documento.

Per ulteriori informazioni sul lettore Fluidic, consulta [Lettore Fluidic](../../learners/feature-summary/fluidic-player.md).

Ecco alcuni esempi di come è possibile utilizzare il lettore Fluidic incorporabile.

* Puoi utilizzare il lettore Fluidic incorporabile nel tuo sito Web** **per elencare i corsi a cui sono iscritti i dipendenti e fornire anche un collegamento per avviare una formazione nella stessa pagina. Ciò significa che gli Allievi possono seguire i corsi di formazione sul sito Web Intranet.

* Se sei impegnato nel settore della formazione, potresti avere un sito Web in cui i clienti possono acquistare corsi. È possibile integrare il lettore incorporabile con lo stesso sito Web in modo che i clienti possano utilizzare i contenuti acquistati all’interno del sito Web.

## Procedura per incorporare il lettore Fluidic nel sito Web {#stepstoembedfluidicplayerinyourwebsite}

La creazione di un’applicazione personalizzata per incorporare un lettore Fluidic nel sito Web prevede tre passaggi fondamentali:

1. Creare un’applicazione nell’app Amministratore dell’integrazione di Learning Manager.
1. Recuperare il token di accesso.
1. Utilizza il token di accesso per recuperare le risorse da Learning Manager utilizzando l’API pubblica.

### 1. Creare un’applicazione nell’Amministratore dell’integrazione {#1createanapplicationinintegrationadmin}

Questo passaggio è necessario per creare un ID applicazione/client e un segreto applicazione/client utilizzato per recuperare il token di aggiornamento e il token di accesso. Per ulteriori informazioni sulla creazione di un&#39;applicazione, vedere [Processo di sviluppo dell&#39;applicazione.](developer-manual.md#main-pars_header_994876235)

1. Passa all’app **[!UICONTROL IntegrationAdmin]** e aprire **[!UICONTROL Applicazioni]**.

1. Seleziona **[!UICONTROL Registra]** dall’angolo in alto a destra nella pagina.
1. Viene visualizzata la finestra **[!UICONTROL Registra una nuova applicazione]**. Compila i campi obbligatori.
1. Se l&#39;applicazione personalizzata deve essere condivisa tra più account, selezionare **[!UICONTROL No]** nel campo delle opzioni **[!UICONTROL Solo per questo account?]**
1. Per salvare l’applicazione e generare l’ID e il segreto dell’applicazione, fai clic su **[!UICONTROL Salva]**.

### 2. Recuperare il token di accesso {#2retrievingaccesstoken}

Poiché Learning Manager utilizza OAUTH2.0, il token di accesso è necessario per recuperare le risorse utilizzando l’API pubblica. È possibile recuperare il token di accesso utilizzando il token di aggiornamento, l’ID client o il segreto del client.

**2.1 Token di aggiornamento**

* Recuperare il codice OAuth

Il codice OAuth è necessario per recuperare il token di aggiornamento. Learning Manager reindirizza l’utente all’URL di reindirizzamento con il codice OAuth quando viene eseguito l’accesso utilizzando l’URL seguente (l’estrazione del codice OAuth è esemplificata nel file &quot;oauthredirect.html&quot; nell’applicazione di esempio):

```
code https://learningmanager.adobe.com/oauth/o/authorize  
client_id= <application_id>  
&redirect_uri=<redirect_uri>  
&state=<dummy_data>  
&scope=learner:read,learner:write  
&response_type=CODE  
&account=<account_id>  
&email=<email_id>
```

Qui **[!UICONTROL ID client]** è l&#39;ID applicazione ottenuto al passaggio 1.
**[!UICONTROL redirect_url]** è il redirect_url impostato nel passaggio 1.
**[!UICONTROL state]** è qualsiasi dato fittizio in base al quale dobbiamo filtrare l&#39;URL di reindirizzamento per ottenere il codice OAuth. L’ambito è l’ambito Allievo impostato nel passaggio 1.
**[!UICONTROL response_typ]**e è sempre &quot;CODE&quot;.\
**[!UICONTROL account]**è un campo facoltativo\
**[!UICONTROL email]** è un campo facoltativo\
&#42; Se vengono forniti sia l&#39;ID sia l&#39;indirizzo e-mail, l&#39;URL precedente consentirà all&#39;utente di accedere allo stesso account. Questo esempio di endpoint è rappresentato nel file &quot;index.html&quot; nell’applicazione di esempio.

* Recuperare il token di aggiornamento

Una volta ricevuto il codice OAuth, è possibile recuperare il token di aggiornamento utilizzando il codice OAuth ricevuto, l’ID client e il segreto client dall’endpoint seguente:

**https://learningmanager.adobe.com/oauth/token**

Come risposta alla tua richiesta post, riceverai quanto segue:

i. refresh_token\
2. access_token\
3. user_id\
iv. expres_in\
v. user_role\
vi. account_id

**2.2 Recupero del token di accesso dal token di aggiornamento**

Per recuperare il token di accesso, invia un’altra richiesta con refresh_token, client_id e client_secret come corpo del post all’URL seguente:

**https://learningmanager.adobe.com/oauth/token/refresh**

Come risposta alla tua richiesta post, riceverai quanto segue:\
i. refresh_token\
2. access_token\
3. user_id\
iv. expres_in\
v. user_role\
vi. account_id

### 3. Recuperare risorse utilizzando AP pubbliche {#3retrieveresourcesusingpublicapi}

Come terzo passaggio, devi utilizzare il token di accesso per recuperare le risorse da Learning Manager utilizzando un’API pubblica .  Il token di accesso è necessario per effettuare qualsiasi chiamata API pubblica ed è necessario aggiungerlo nell’intestazione come esemplificato nell’applicazione di esempio.

## Lettore incorporabile {#embeddableplayer}

Le applicazioni di terze parti possono utilizzare un lettore incorporabile per riprodurre il contenuto di un oggetto di apprendimento.

**Aprire un corso in un lettore incorporabile**

1. Creare un URL incorporabile

   Per aprire un corso utilizzando un lettore incorporabile, devi creare un URL incorporabile come illustrato di seguito:

   `https://learningmanager.adobe.com/app/player?lo_id=<v2-api course id>&access_token=<access_token>`

   In questo caso, lo_id deve essere conforme al formato ID corso API V2.

   Esempio: `https://learningmanager.adobe.com/app/player?lo_id=course:123456&access_token=45b269b75ac65d6696d53617f512450f`

   Nel lettore incorporabile è possibile riprodurre anche certificazioni, programmi di apprendimento e risorse formative.

   Esempi: `https://learningmanager.adobe.com/app/player?lo_id=certification:12345&access_token=c1a4847dfbf4007826a027d481b93c1e`

   `https://learningmanager.adobe.com/app/player?lo_id=learningProgram:12345&access_token=c1a4847dfbf4007826a027d481b93c1e`

   `https://learningmanager.adobe.com/app/player?lo_id=jobAid:1234&access_token=c1a4847dfbf4007826a027d481b93c1e`

1. Impostare questo URL nell’attributo &quot;src&quot; di iframe.

**Chiusura del lettore incorporabile**

```
code window.addEventListener("message", function closePlayer(){  
   if(event.data === "status:close"){  
     //handle closing event  
   }  
});
```

## Esercitazione applicazione di esempio {#sampleapplicationtutorial}

Il documento PDF allegato contiene un’esercitazione dell’applicazione di esempio.
[Esempio di esercitazione e fonte di esercitazione per incorporare il lettore Fluidic.](assets/sample-applicationtutorial.zip) Contenuto alternativo

Se sei un amministratore, puoi configurare il materiale del corso in modo da offrire contenuti alternativi agli Allievi all’interno del lettore Fluidic. Ad esempio, se sono presenti Allievi in diverse aree geografiche che desiderano utilizzare più lingue, è possibile creare lo stesso contenuto in più lingue. Il lettore Fluidic offrirà all’Allievo la lingua per la quale potrebbe essere configurato, ma l’Allievo ha anche la possibilità di passare a una lingua alternativa direttamente dal lettore.

Controlli specifici del video

La tecnologia di streaming utilizzata dal lettore Fluidic Learning Manager offre un’esperienza di riproduzione video ai suoi Allievi senza ritardi nell’avvio del video e senza requisiti di spazio su disco su nessun dispositivo. Il lettore Fluidic offre anche controlli intelligenti, come la velocità di riproduzione (1x, 1,5X) e ignora +-10 secondi, progettati per fornire all’Allievo il livello esatto di controllo di cui ha bisogno per abbinare la velocità di apprendimento.

Si tratta di un&#39;operazione che deve essere eseguita da un team IT o da un consulente esterno in grado di creare un&#39;applicazione che viene poi ospitata sul sito.

1. Modifica l’URL del lettore incorporato di Learning Manager con i parametri che puntano all’oggetto di apprendimento esatto che deve essere acquisito.

   URL: [https://learningmanager.adobe.com/app/player](https://cpcontents.adobe.com/public/embedplayer/index22fa615ec2baa034a22090c8cd4289fa.html)

1. Utilizza uno di questi parametri per avviare un corso:

   * course_id : ID del corso da avviare
   * learning_program_id : ID del programma di apprendimento da avviare
   * certification_id : ID della certificazione da avviare
   * lo_id : ID dell’oggetto di apprendimento (corso/programma di apprendimento/certificazione/risorsa formativa) da riprodurre


1. Utilizza il token di accesso come parametro obbligatorio.

   * access_token : Parametro di sicurezza. Utilizzare l&#39;API oauth pubblica.   token di accesso

   Puoi ottenere il token configurando il lettore Fluidic incorporabile nell’amministratore dell’integrazione. Puoi ottenere il token di autenticazione che puoi utilizzare come token di accesso.

   Esempio di URL creato: https://learningmanager.adobe.com/app/player?lo_id=&quot;+lo_id+&quot;&amp;access_token=&quot;+accToken

   Qui lo_id sarà l’ID del corso, del programma di apprendimento, della certificazione e della risorsa formativa.

   Esempi di lo_id - corso:21324, learningProgram:2143, certificazione:23432, jobAid:237

1. Effettua chiamate API di Learning Manager per recuperare i parametri sopra indicati.

   Queste chiamate API devono essere effettuate dall&#39;applicazione che il team IT/consulente scriverà e ospiterà sul sito.

   Ulteriori dettagli sull’utilizzo dell’API sono disponibili qui:

   API V1 di Learning Manager - [https://learningmanager.adobe.com/docs/primeapi/v1/](https://learningmanager.adobe.com/docs/primeapi/v1/)



   API di Learning Manager V2 - [https://learningmanager.adobe.com/docs/primeapi/v2/](https://learningmanager.adobe.com/docs/primeapi/v2/)

   Gli ID degli oggetti differiscono dall’API V1 e V2. Il lettore incorporabile prevede ID nel formato v2. Utilizza l’API di mappatura degli ID nella versione 2 per convertire gli ID V1 in ID V2.

   Dopo aver costruito l’URL, un modo in cui l’applicazione lo utilizzerebbe per visualizzarlo all’Allievo è inserirlo in un iFrame. Cliccando su questo link, il lettore Fluidic viene lanciato con il corso specifico nel contesto.

   ![](assets/salesforce-player.png)

   Per verificare i report di avanzamento e completamento, accedi a Learning Manager.

   Quando l’Allievo chiude il lettore, quest’ultimo invia un messaggio di &quot;chiusura&quot; all’elemento principale mediante html5 postMessage. Il controller di caricamento deve gestire questo messaggio e continuare.

Modifica l’URL del lettore incorporato di Learning Manager con i parametri che puntano all’oggetto di apprendimento esatto che deve essere acquisito.

URL: [https://learningmanager.adobe.com/app/player](https://learningmanager.adobe.com/app/player)

Uno qualsiasi di questi parametri può essere utilizzato per avviare un corso:

* course_id : ID del corso da avviare
* learning_program_id : ID del programma di apprendimento da avviare
* certification_id : ID della certificazione da avviare
* lo_id : ID dell’oggetto di apprendimento (corso/programma di apprendimento/certificazione/risorsa formativa) da riprodurre

Parametro obbligatorio:

* access_token : Parametro di sicurezza. Utilizzare l&#39;API oauth pubblica.   token di accesso

Effettua chiamate API di Learning Manager per recuperare i parametri sopra indicati. Queste chiamate API devono essere effettuate dall&#39;applicazione che il team IT/consulente scriverà e ospiterà sul sito.

Ulteriori dettagli sull’utilizzo dell’API sono disponibili qui:

API V1 di Learning Manager - [https://learningmanager.adobe.com/docs/primeapi/v1/](https://learningmanager.adobe.com/docs/primeapi/v1/)



API di Learning Manager V2 - [https://learningmanager.adobe.com/docs/primeapi/v2/](https://learningmanager.adobe.com/docs/primeapi/v2/)


