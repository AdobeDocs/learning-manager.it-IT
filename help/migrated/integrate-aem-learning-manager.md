---
jcr-language: en_us
title: Integrazione di Learning Manager con AEM
description: Learning Manager è un sistema di gestione dell’apprendimento con un sistema di gestione dei contenuti di apprendimento integrato. Gli utenti gestiscono i contenuti di apprendimento caricandoli su Learning Manager, in modo che Learning Manager esegua il controllo delle versioni, l’assegnazione ai corsi, la definizione della visibilità per gli Allievi, il monitoraggio dell’utilizzo e la creazione di report per gli Amministratori.
contentowner: saghosh
source-git-commit: 46afb6603456ced9d7e2aaf98d07ec92fee30c0b
workflow-type: tm+mt
source-wordcount: '1077'
ht-degree: 0%

---



# Integrazione di Learning Manager con AEM

Learning Manager è un sistema di gestione dell’apprendimento con un sistema di gestione dei contenuti di apprendimento integrato. Gli utenti gestiscono i contenuti di apprendimento caricandoli su Learning Manager, in modo che Learning Manager esegua il controllo delle versioni, l’assegnazione ai corsi, la definizione della visibilità per gli Allievi, il monitoraggio dell’utilizzo e la creazione di report per gli Amministratori.

Tuttavia, ci sono utenti che archiviano e gestiscono i propri contenuti su sistemi di gestione delle risorse. Il contenuto viene quindi ridestinato a varie altre funzioni.

Le varie strisce presenti nell’app per Allievi possono essere incorporate nei siti AEM. Tutti gli Allievi che accedono al sito dell’AEM vedranno su queste strisce i propri dati di formazione specifica.

## Scaricare il pacchetto dei contenuti {#downloadthecontentpackage}

Il programma di installazione viene fornito come pacchetto di contenuti AEM. [***Scaricare il pacchetto***](https://github.com/adobe/adobe-learning-manager-reference-site).

Il pacchetto dei contenuti è disponibile come file zip ed è compatibile con AEM 6.4 e AEM 6.5.

## Installazione del componente Learning Manager {#installcaptivateprimecomponent}

Installa il pacchetto di contenuti di Learning Manager utilizzando il gestore pacchetti AEM:

>[!NOTE]
>
>Per informazioni sull&#39;installazione dei pacchetti, consulta  [***Come utilizzare i pacchetti***](https://experienceleague.adobe.com/docs/experience-manager-65/administering/contentmanagement/package-manager.html?lang=en#how-to-work-with-packages).

1. In qualità di Autore AEM, apri il Gestore pacchetti AEM.
1. Fare clic sul pulsante **[!UICONTROL Carica pacchetto]**.
1. Fai clic **[!UICONTROL Sfoglia]** e caricare il pacchetto di contenuti.
1. Fai clic **[!UICONTROL Carica]**.
1. Dopo il caricamento del pacchetto, installa il pacchetto di contenuti selezionandolo e facendo clic su **[!UICONTROL Installa]**.

   ![](assets/install-package.jpg)

   *Installare il pacchetto dei contenuti*

## Generare il token di aggiornamento {#generatetherefreshtoken}

L’Amministratore AEM richiede un token di aggiornamento dall’account Learning Manager. L’Amministratore dell’integrazione Learning Manager genererà il token di aggiornamento.

1. Approva l’app in primo piano AEM Sites.

   Fai clic **[!UICONTROL Applicazioni]** > **[!UICONTROL App in primo piano]** > **[!UICONTROL Adobe Experience Manager - Sites]**.

   ![](assets/launch-aem.jpg)

   *Approva l’app*

1. Fai clic **[!UICONTROL Applicazioni]** > **[!UICONTROL App in primo piano]** e aprire l’applicazione AEM Sites.

   Copia l’ID applicazione e la descrizione.

1. Fai clic **[!UICONTROL Risorse per sviluppatori]** > **[!UICONTROL Token di accesso]**.

   ![](assets/click-tokens.jpg)

   *Generare i token di accesso*

1. Immetti i seguenti dettagli:

   * ID client, ovvero l&#39;ID applicazione.
   * Segreto client, presente in Descrizione.

1. Ottieni il codice OAuth. È necessario utilizzare API v2 nell&#39;URI di reindirizzamento.
1. Fai clic **[!UICONTROL Invia]** e ottenere il token di aggiornamento.

## Configurare il widget in AEM {#configurethewidgetinaem}

Per la configurazione del widget, l’autore AEM richiede solo il token di aggiornamento fornito dall’Amministratore dell’integrazione Learning Manager.

Puoi anche impostare più configurazioni di account in più pagine.

1. Fai clic **[!UICONTROL Strumenti]** > **[!UICONTROL Cloud Service]** > **[!UICONTROL Configurazione del widget Learning Manager]**.
1. Fai clic **[!UICONTROL Crea]**.
1. Immetti qui il token di aggiornamento. Configura le altre impostazioni.
1. Il nome host deve essere modificato in &quot;learningmanagereu&quot; per le regioni dell’UE.
1. Salva e chiudi la configurazione.
1. Seleziona una configurazione e pubblicala.

## Autore AEM {#aemauthor}

L’autore dell’AEM deve prima aggiungere il componente nel modello AEM

L’Autore dell’AEM potrà quindi trascinare e rilasciare il componente Adobe di Learning Manager e configurarlo di conseguenza.

Il componente Learning Manager richiede che la configurazione creata nel passaggio precedente venga mappata alla pagina.  L’Autore può mappare la configurazione modificando le proprietà della pagina in **[!UICONTROL Avanzate]** > **[!UICONTROL Configurazione]** > **[!UICONTROL Configurazione cloud]** e fornisci il percorso di configurazione. In questo modo, l’Autore può creare configurazioni per più account Learning Manager e mappare ciascuna di esse su diverse pagine del sito. Se una configurazione non è mappata alla pagina, il componente leggerà la configurazione dalla pagina padre in modo ricorsivo fino a quando non ne trova una.

## Allievo {#learner}

L’Allievo può seguire i corsi all’interno della pagina.

Per poter accedere al widget Learning Manager, l’Allievo deve aver effettuato l’accesso con un utente AEM. Inoltre, proprietà **email** deve essere presente nel nodo &quot;/profile&quot; del nodo rep:User dell’Allievo. Questo indirizzo e-mail deve essere esattamente uguale a quello presente nell’account Learning Manager.

L’Allievo può seguire i corsi all’interno della pagina.

Viene salvato anche l’avanzamento del corso.

Sono disponibili i seguenti widget:

1. Gamification
1. Calendario di apprendimento
1. Widget social
1. Widget Catalogo
1. Il mio apprendimento
1. Consiglio basato sull’apprendimento tra pari
1. Recommendations dell&#39;amministratore
1. Consiglio basato sugli interessi degli Allievi

Se non sono presenti suggerimenti, il widget viene visualizzato vuoto.

## Supporto per Skyline

Skyline è la versione cloud dell&#39;AEM. Devi prima installare Skyline dal gestore dei pacchetti. Per utilizzare il componente Skyline nell’AEM, un utente deve essere presente nell’account Learning Manager. In altre parole, l’indirizzo e-mail dell’utente deve esistere nell’account.

### Distribuisci Skyline

La procedura per configurare Skyline è indicata nella  [Repo GitHub](https://github.com/adobe/captivate-prime-aem-components).

## Widget Catalogo

Il widget Catalogo mostra i corsi di formazione da un catalogo specifico o da un set di cataloghi a un utente. Nella sezione Proprietà delle proprietà della pagina, seleziona Catalogo dalle opzioni elencate.

<!--![](assets/catalog-widget.png)-->

Il widget Catalogo contiene le seguenti opzioni:

* **[!UICONTROL ID catalogo]:** ID catalogo separati da virgole per i quali è necessario visualizzare i corsi di formazione.
* **[!UICONTROL Ordina]:** Ordinamento dei corsi di formazione. Le opzioni sono: name, date, dateCreated, dateEnrolled e così via.
* **[!UICONTROL Stato Allievo]:** Restituisce tutti i corsi di formazione che utilizzano i seguenti filtri: enrolled, started, completed, e notenrolled. I risultati della ricerca non verranno visualizzati se l&#39;opzione di ordinamento è dateEnrolled, dueDate o dateEnrolled.
* **[!UICONTROL Nome dell’abilità]:** Abilità utilizzata per filtrare il corso di formazione esatto.
* **[!UICONTROL Nome tag]:** Tag utilizzato per filtrare i risultati esatti.

Di seguito sono riportati alcuni componenti aggiuntivi che è possibile personalizzare:

**[!UICONTROL Tipi di oggetti di apprendimento]:** Filtra in base al tipo di oggetto di apprendimento. I tipi supportati sono: corso, certificazione, risorsa formativa e programma di apprendimento.

Nell&#39;AEM, il titolo di una carta in una striscia sarà inizialmente vuoto. Nelle proprietà, digita il nome del titolo in widgets.html.

**Personalizzazione**

È possibile personalizzare l&#39;aspetto del layout utilizzando widgets.html. È possibile modificare l&#39;aspetto delle schede visualizzate e personalizzare il tema.

Nella **[!UICONTROL Impostazioni generali]** sezione, è possibile scegliere i colori primari e secondari delle schede e specificare le proprietà per personalizzare il tema.

```
{ 
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

Se il **Ignora l’iscrizione agli oggetti di apprendimento di ordine superiore** la casella di controllo è abilitata e un utente è iscritto direttamente a un programma di apprendimento o a una certificazione; i corsi per tale certificazione o programma di apprendimento verranno visualizzati per l’utente nei widget.

Se la casella di controllo è disattivata, i corsi presenti nel programma di apprendimento o nella certificazione a cui l’utente non si è iscritto direttamente non verranno visualizzati.

![](assets/higher-order-lo.png)

*Selezionare la casella di controllo Ignora l&#39;iscrizione agli oggetti di apprendimento di ordine superiore.

L’impostazione viene quindi applicata al widget.

### Sicurezza

Vengono aggiunti i campi ID client e Segreto client. Inoltre, il token di aggiornamento viene nascosto. Dopo che un utente ha creato l&#39;intera configurazione, se l&#39;utente apre nuovamente la configurazione per modificarla o se un altro utente apre questa configurazione, il token di aggiornamento verrà mascherato.
