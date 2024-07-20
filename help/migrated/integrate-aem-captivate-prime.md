---
jcr-language: en_us
title: Integrazione di Adobe Learning Manager con AEM
description: Scopri come integrare Adobe Learning Manager con Adobe Experience Manager (AEM)
contentowner: saghosh
source-git-commit: 0052ccb2f5a8f9617bca2c7bad91c0cd18338b66
workflow-type: tm+mt
source-wordcount: '1025'
ht-degree: 44%

---



# Integrazione di Learning Manager con AEM

## Panoramica {#overview}

Learning Manager è un sistema di gestione dell’apprendimento con un sistema di gestione dei contenuti di apprendimento integrato. Gli utenti gestiscono i propri contenuti di apprendimento caricandoli su Learning Manager, in modo che Learning Manager esegua il controllo delle versioni, l’assegnazione ai corsi, la definizione della visibilità agli Allievi, il monitoraggio della frequenza e la segnalazione agli amministratori.

Tuttavia, alcuni utenti archiviano e gestiscono i propri contenuti su sistemi di gestione delle risorse. Il contenuto viene quindi convertito per altre funzioni.

Le varie strisce presenti nell’app per Allievi possono essere incorporate nei siti AEM. Tutti gli Allievi che accedono al sito AEM vedranno i propri dati di formazione specifici in queste strisce.

## Download del pacchetto dei contenuti {#downloadthecontentpackage}

Il programma di installazione viene fornito come pacchetto di contenuti AEM. [***Scarica il pacchetto***](https://github.com/adobe/captivate-prime-aem-components/releases).

Il pacchetto dei contenuti è disponibile come file zip ed è compatibile con AEM 6.4 e AEM 6.5.

## Installazione del pacchetto Learning Manager {#installcaptivateprimecomponent}

Installa il pacchetto dei contenuti Learning Manager utilizzando il gestore pacchetti AEM:

>[!NOTE]
>
>Per informazioni sull&#39;installazione dei pacchetti, vedere [***Come utilizzare i pacchetti***](https://experienceleague.adobe.com/docs/experience-manager-65/administering/contentmanagement/package-manager.html?lang=en#how-to-work-with-packages).

1. Come Autore AEM, apri il gestore pacchetti AEM.

1. Fai clic sul pulsante **Carica pacchetto**.

1. Fai clic su **[!UICONTROL Sfoglia]** e carica il pacchetto di contenuti.
1. Fai clic su **[!UICONTROL Carica]**.
1. Dopo aver caricato il pacchetto, installalo selezionandolo e facendo clic su **[!UICONTROL Installa]**.

   ![](assets/install-package.jpg)

## Generazione del token di aggiornamento {#generatetherefreshtoken}

L’Amministratore AEM richiede un token di aggiornamento dall’account Learning Manager. L’Amministratore dell’integrazione Learning Manager genererà il token di aggiornamento.

1. Approva l’app in primo piano AEM Sites.

   Fai clic su **[!UICONTROL Applicazioni]** > **[!UICONTROL App in primo piano]** > **[!UICONTROL Adobe Experience Manager - Sites]**.

   ![](assets/launch-aem.jpg)

1. Fai clic su **[!UICONTROL Applicazioni]** > **[!UICONTROL App in primo piano]** e apri l&#39;applicazione AEM Sites.

   Copia l’ID dell’applicazione e la descrizione.

1. Fai clic su **[!UICONTROL Risorse sviluppatore]** > **[!UICONTROL Token di accesso]**.

   ![](assets/click-tokens.jpg)

1. Immetti i seguenti dettagli:

   * ID client, ovvero l’ID dell’applicazione.
   * Segreto del client, presente nella descrizione.

1. Ottieni il codice OAuth. Devi usare API v2 nell’URI di reindirizzamento.
1. Fai clic su **[!UICONTROL Invia]** e ottieni il token di aggiornamento.

## Configurazione del widget in AEM {#configurethewidgetinaem}

Per la configurazione del widget, l’autore AEM richiede solo il token di aggiornamento fornito dall’Amministratore dell’integrazione Learning Manager.

Puoi anche impostare più configurazioni di account in più pagine.

1. Fai clic su **[!UICONTROL Strumenti]** > **[!UICONTROL Cloud Service]** > **[!UICONTROL Captivate configurazione widget Learning Manager]**.
1. Fai clic su **[!UICONTROL Crea]**.
1. Immetti qui il token di aggiornamento. Configura altre impostazioni.
1. Il nome host deve essere modificato in &quot;learningmanagereu&quot; per le regioni dell’UE.
1. Salva e chiudi la configurazione.
1. Seleziona una configurazione e pubblicala.

## Autore AEM {#aemauthor}

L’autore AEM deve prima aggiungere il componente nel modello AEM

L’autore AEM potrà quindi trascinare e rilasciare il componente Adobe Learning Manager e configurarlo di conseguenza.

Il componente Learning Manager richiede che la configurazione creata nel passaggio precedente venga mappata alla pagina.  L&#39;autore può mappare la configurazione modificando le proprietà della pagina in **[!UICONTROL Avanzate]** > **[!UICONTROL Configurazione]** > **[!UICONTROL Configurazione cloud]** e fornire il percorso di configurazione. In questo modo, l’Autore può creare configurazioni per più account Learning Manager e collegare ciascuna di esse a pagine diverse. Se una configurazione non è collegata alla pagina, il componente leggerà ricorrentemente la configurazione dalla pagina padre fino a quando non ne trova una.

## Allievo {#learner}

L’Allievo può seguire i corsi direttamente dalla pagina.

Per poter accedere al widget Learning Manager, l’Allievo deve effettuare il login come utente AEM. Inoltre, la proprietà **email** deve essere presente nel nodo &quot;/profile&quot; del nodo rep:User dell’Allievo. Questa e-mail deve essere esattamente uguale a quella presente nell’account Learning Manager.

L’Allievo può seguire i corsi direttamente dalla pagina.

Anche l’avanzamento del corso viene salvato.

Vengono forniti i seguenti widget:

1. Gamification
1. Calendario apprendimento
1. Widget social
1. Widget Catalogo
1. Il mio apprendimento
1. Consiglio basato sull’apprendimento tra utenti dello stesso livello
1. Consigli dell’Amministratore
1. Consiglio basato sugli interessi degli Allievi

In caso di mancanza di consigli, il widget sarà vuoto.

## Supporto per Skyline

Skyline è la versione cloud dell&#39;AEM. Devi prima installare Skyline dal gestore dei pacchetti. Per utilizzare il componente Skyline nell’AEM, un utente deve essere presente nell’account Learning Manager. In altre parole, l’indirizzo e-mail dell’utente deve esistere nell’account.

## Implementa Skyline

La procedura per configurare Skyline è indicata nel [repository GitHub](https://github.com/adobe/captivate-prime-aem-components).

## Widget Catalogo

Il widget Catalogo mostra i corsi di formazione da un catalogo specifico o da un set di cataloghi a un utente. Nella sezione Proprietà delle proprietà della pagina, seleziona Catalogo dalle opzioni elencate.

![](assets/catalog-widget.png)

Il widget Catalogo contiene le seguenti opzioni:

* **[!UICONTROL ID catalogo]:** ID catalogo separati da virgole per i quali è necessario visualizzare i corsi di formazione.
* **[!UICONTROL Ordinamento]:** Ordinamento per il corso di formazione. Le opzioni sono: name, date, dateCreated, dateEnrolled e così via.
* **[!UICONTROL Stato dell’Allievo]:** restituisce tutti i corsi di formazione che utilizzano i seguenti filtri: enrolled, started, completed, e notenrolled. I risultati della ricerca non verranno visualizzati se l&#39;opzione di ordinamento è dateEnrolled, dueDate o dateEnrolled.
* **[!UICONTROL Nome dell’abilità]:** Abilità utilizzata per filtrare il corso di formazione esatto.
* **[!UICONTROL Nome del tag]:** Il tag utilizzato per filtrare i risultati esatti.

Di seguito sono riportati alcuni componenti aggiuntivi che è possibile personalizzare:

**[!UICONTROL Tipi di oggetti di apprendimento]:** Filtrare in base al tipo di oggetto di apprendimento. I tipi supportati sono: corso, certificazione, risorsa formativa e programma di apprendimento.

Nell&#39;AEM, il titolo di una carta in una striscia sarà inizialmente vuoto. Nelle proprietà, digita il nome del titolo in widgets.html.

**Personalizzazione**

È possibile personalizzare l&#39;aspetto del layout utilizzando widgets.html. È possibile modificare l&#39;aspetto delle schede visualizzate e personalizzare il tema.

Nella sezione **[!UICONTROL Impostazioni generali]** è possibile scegliere i colori primari e secondari delle schede e specificare le proprietà per personalizzare il tema.

```
\{ 
 "globalCssText":"@import url('https://fonts.googleapis.com/css2?family=Grandstander:ital,wght@0,100;0,200;0,300;0,400;0,500;0,600;0,700;0,800;0,900;1,100;1,200;1,300;1,400;1,500;1,600;1,700;1,800;1,900&family=Montserrat:ital,wght@0,100;0,200;0,300;0,400;0,500;0,600;0,700;0,800;0,900;1,100;1,200;1,300;1,400;1,500;1,600;1,700;1,800;1,900&display=swap');", 
 "fontNames":"Grandstander", 
 "cardLayout":{ 
 "cardLayoutName":"compact", 
 "cardPrimaryColor":"#376BA4", 
 "cardSecondaryColor":"#F98EB0", 
 "startedStateTextColor":"#ffffff", 
 "continueStateTextColor":"#ffffff", 
 "revisitStateTextColor":"#ffffff", 
 "startedStateColor":"#a0a0a0", 
 "continueStateColor":"#f9a122", 
 "revisitedStateColor":"#7fbc64", 
 "textPrimaryColor":"#ffffff", 
 "textSecondaryColor":"#d93f3f", 
 "navIconColor":"#a0a0a0" 
 } 
}
```

### Ignora l’iscrizione agli oggetti di apprendimento di ordine superiore

Se la casella di controllo **[!UICONTROL Ignora l’iscrizione agli oggetti di apprendimento di ordine superiore]** è abilitata e un utente è iscritto direttamente a un programma di apprendimento o a una certificazione, nei widget verranno visualizzati i corsi per tale certificazione o programma di apprendimento.

Se la casella di controllo è disattivata, i corsi presenti nel programma di apprendimento o nella certificazione a cui l’utente non si è iscritto direttamente non verranno visualizzati.

![](assets/higher-order-lo.png)

L’impostazione viene quindi applicata al widget.

### Protezione

I campi ID client e Segreto del client vengono aggiunti. Inoltre, il token di aggiornamento viene nascosto. Dopo che un utente ha creato l&#39;intera configurazione, se l&#39;utente apre nuovamente la configurazione per modificarla o se un altro utente apre questa configurazione, il token di aggiornamento verrà mascherato.
