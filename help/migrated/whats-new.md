---
title: Novità di questa versione
description: Scopri le nuove funzioni e i miglioramenti in Adobe Learning Manager
source-git-commit: 655c94f0faaa6c025e07b11d3d9bfac4f221f899
workflow-type: tm+mt
source-wordcount: '2372'
ht-degree: 70%

---

# Novità di questa versione

## Interfaccia utente rinnovata

L’interfaccia utente di Learning Manager di Adobe è stata aggiornata per offrire un’esperienza più moderna e pulita. Le landing page sono state rinnovate per i ruoli Amministratore e Autore, mentre il tema dell’interfaccia utente è stato modificato per tutti i ruoli. Tuttavia, non è stata apportata alcuna modifica alla posizione di menu, pulsanti o collegamenti e potrai trovarli esattamente nella posizione in cui si trovavano prima.

Le modifiche del tema verranno applicate automaticamente agli account che utilizzano quello predefinito; invece, gli aggiornamenti del tema dell’interfaccia utente non interesseranno gli account che ne utilizzano uno personalizzato. Ciò significa che, per accedere ai nuovi aggiornamenti del tema, tali account dovranno ripristinare quello predefinito.

![Immagine dell&#39;interfaccia utente](assets/refreshed-ui.png)

*Interfaccia utente rinnovata di Adobe Learning Manager*

### Informazioni sulle modifiche

**Modifiche introdotte da questa release**

L’intestazione contiene un nuovo modello che reimposta automaticamente dimensioni e posizione fisse per i loghi mantenendone le proporzioni. Questa modifica mira a migliorare la grafica dell’esperienza degli Allievi.

Le dimensioni del nome dell’organizzazione nell’intestazione vengono reimpostate automaticamente anche a 336 (minimo) x 680 (massimo) px per gli Allievi.

**Qual è la dimensione consigliata del logo?**

La larghezza massima è 210 px. I loghi con larghezza superiore a 210 px o altezza superiore a 42 px vengono ridimensionati a 42 x 210 px.

Se le dimensioni di un logo sono inferiori a quelle consigliate, viene caricato senza modifiche e allineato al centro.

**Qual è l&#39;impatto?**

I nomi molto lunghi vengono abbreviati con un punto.

**Cosa consigliamo?**

* Occorre ridimensionare l’immagine mantenendo intatte le proporzioni. La dimensione massima consigliata per i loghi è 42 px (verticale) x 210 px (orizzontale).
* Questa opzione viene attivata automaticamente su molti account, pertanto non è richiesta alcuna modifica.

## Estendibilità nativa

La configurazione di esperienze personalizzate nella versione nativa di Adobe Learning Manager consente di evitare di usare l’approccio headless per i casi meno complicati. È possibile anche creare app personalizzate e inserirle in vari punti all’interno della versione nativa dei flussi di lavoro Allievo, Manager, Amministratore, Autore o Istruttore.

Un Allievo può utilizzare un’app personalizzata o un’estensione creata da un Amministratore.

Per ulteriori informazioni, consultare [Estendibilità nativa](/help/migrated/administrators/feature-summary/native-extensibility.md).

## Strumento per la creazione di quiz

Ora sarai in grado di creare valutazioni in Learning Manager con il nuovo strumento di creazione dei quiz nella pagina Libreria dei contenuti. Le valutazioni create diventano parte della Libreria dei contenuti e possono essere aggiunte a una cartella &quot;pubblica&quot; per consentire il riutilizzo del corso.

Visualizza [Creare un quiz](/help/migrated/authors/feature-summary/content-library.md) per ulteriori informazioni.

## Modifiche ai report introdotte da questa release

### Modifiche nel report di iscrizione alle risorse formative

Le versioni precedenti di Adobe Learning Manager non prevedevano filtri per il report Iscrizione risorsa formativa, per cui venivano scaricati tutti i dati di un account.

In questa versione, è stato aggiunto un menu a discesa nella finestra di dialogo Report risorse formative.

### Modifiche nel report di annuncio delle notifiche

Nelle versioni precedenti di Adobe Learning Manager, il report Annuncio notifica non disponeva di filtri. per cui venivano scaricate tutte le notifiche di un account.

In questa versione è stato aggiunto un filtro per data, con cui è possibile scaricare le notifiche entro un periodo di tempo specificato.  Tuttavia, puoi scaricare il report solo per gli ultimi sei mesi.

### Modifiche nei dati di rivisita del corso nel report di iscrizione

Questa versione consente di scaricare i dati sulla revisione dei corsi contenuti nel report Iscrizione specificando un arco di tempo. Il periodo di download è limitato a 6 mesi per gli account con più di cinque milioni di iscrizioni e a 15 mesi per tutti gli altri account.

Puoi scaricare il report da **[!UICONTROL Report]** > **[!UICONTROL Report personalizzati]** > **[!UICONTROL Report cronologici]** > **[!UICONTROL Report di accesso al corso]**.

### Modifiche della trascrizione Allievo

Nelle versioni precedenti di Adobe Learning Manager, se l’ambito di un Amministratore personalizzato era impostato su Utente, la Trascrizione Allievo conteneva gli utenti eliminati. In questa versione, la Trascrizione Allievo contiene gli utenti eliminati sia se l’ambito di un Amministratore personalizzato è impostato su Utente, sia se ha accesso a tutti i gruppi di utenti.

### Modifiche del report di partecipazione

Il report Partecipazione disponibile in Partecipazione ai corsi (app per Amministratori) e in Allievi della sessione (app per Istruttori) veniva scaricato in modo sincrono. Questa versione consente di scaricare il report in modo asincrono tramite una notifica.

Per ulteriori informazioni sui report, vedere [Report](/help/migrated/administrators/feature-summary/reports.md) nell’Adobe Learning Manager.

## Ritiro marketplace dei contenuti

I corsi presenti nel catalogo all’interno del marketplace dei contenuti importati (corsi di formazione Enterprise) verranno eliminati automaticamente una volta scaduti. L’eliminazione dei corsi avverrà nel momento in cui i contenuti saranno contrassegnati per il ritiro. Gli Allievi già iscritti avranno tempo fino a un periodo limitato per seguirli, dopodiché verranno eliminati. Ciò consentirà di tenere aggiornato il catalogo ed eviterà agli utenti di visualizzare corsi scaduti.

## Nuovi suggerimenti basati sulle competenze

Adobe Learning Manager ha migliorato i suggerimenti per gli account di clienti e partner. L’ottimizzazione dell’algoritmo dei suggerimenti ha comportato la modifica dell’algoritmo di classificazione per corsi, percorsi di apprendimento e certificazioni, aiutando così gli utenti a trovare facilmente contenuti.

L’algoritmo non consentirà più suggerimenti in base alle attività dei colleghi. La modifica non interesserà gli utenti esistenti, ma l’opzione Allineato al settore resterà disponibile. Per l’opzione Personalizzato, Adobe Learning Manager non consentirà più la selezione personalizzata in base alle attività dei colleghi.

Il gruppo di colleghi diventerà un account e gli Allievi vedranno una stringa con gli argomenti di tendenza nel gruppo. Tutti i suggerimenti comprendono spiegazioni. Ad esempio, se si consulta un argomento, la scheda sulla striscia riporta la descrizione del corso.

## Miglioramenti al flusso di lavoro Amministratore personalizzato

Ora gli Amministratori personalizzati possono accedere ai report allo stesso modo degli Amministratori. Gli Amministratori controllano meglio la configurazione dell’accesso ai report.

In Adobe Learning Manager, prima gli Amministratori personalizzati potevano accedere solo a Trascrizione Allievo e Trascrizione gamification. In questa versione, invece, possono accedere a tutti i report personalizzati, ad eccezione di quelli xAPI e tramite e-mail, i quali sono ancora disponibili solo per gli Amministratori. L’accesso a tutti i report è soggetto al catalogo e all’ambito utente assegnato agli Amministratori personalizzati. Di seguito sono indicati i report accessibili solo con ambito completo :

<table>
    <tbody>
        <tr>
            <td>
    <p style="text-align: left;"><b>Report</b></p></td>
   <td>
    <p style="text-align: left;"><b>Disponibilità</b></p></td>
   <td>
    <p style="text-align: left;"><b>Ambito</b></p></td>
        </tr>
    <tr>
   <td>
    <p>Prova di verifica del contenuto</p></td>
   <td>
    <p>Sì</p></td>
   <td>
    <p>Catalogo completo</p></td>
  </tr>
  <tr>
   <td>
    <p>Prova di verifica dell’utente</p></td>
   <td>
    <p>Sì</p></td>
   <td>
    <p>Utente completo</p></td>
  </tr>
  <tr>
   <td>
    <p>Accesso al login</p></td>
   <td>
    <p>Sì</p></td>
   <td>
    <p>Utente completo</p></td>
  </tr>
    </tbody>
</table>

**Nuovi controlli di sola lettura**

Nella pagina Ruoli personalizzati, sono state aggiunte le seguenti opzioni di Sola lettura per consentire agli amministratori di fornire opzioni più flessibili all’Amministratore personalizzato: L’Amministratore personalizzato avrà ora un’autorizzazione aggiuntiva di Sola lettura per Utenti, Modelli e-mail e Piani di apprendimento.

**Utenti**

Selezionando Sola lettura, gli Amministratori personalizzati possono visualizzare tutti gli utenti, ma non modificare i relativi dati, e creare un portale di autoregistrazione per loro.

**Piani di apprendimento**:

Selezionando Sola lettura, gli Amministratori personalizzati non possono aggiungere o modificare Piani di apprendimento. Possono, invece, scaricare report dei piani di apprendimento e visualizzarne i dettagli, ma non modificarli.

>[!NOTE]
>
>I piani di apprendimento saranno aggiuntivi di sola lettura con controllo completo.

**Modelli e-mail**

Selezionando Sola lettura, gli Amministratori personalizzati possono visualizzare i modelli e-mail, ma non abilitare o disabilitare le relative impostazioni. Possono, invece, scaricare i report di accesso alle e-mail.

### Trascrizioni Allievi

Se è selezionata l’opzione Autorizzazione utente o Tutto il gruppo di utenti e l’Amministratore personalizzato tenta di scaricare le Trascrizioni allievi, l’opzione Includi allievi eliminati restituirà nel report tutti gli allievi eliminati.

### Rapporti

Gli Amministratori personalizzati possono accedere ai seguenti report in base all’ambito definito:

<table>
    <tbody>
        <tr>
            <td>
    <p style="text-align: left;"><b>Report</b></p></td>
   <td>
    <p style="text-align: left;"><b>Disponibilità</b></p></td>
   <td>
    <p style="text-align: left;"><b>Ambito</b></p></td>
        </tr>
    <tr>
   <td>
    <p>Prova di verifica del contenuto</p></td>
   <td>
    <p>Sì</p></td>
   <td>
    <p>Catalogo completo</p></td>
  </tr>
  <tr>
   <td>
    <p>Prova di verifica dell’utente</p></td>
   <td>
    <p>Sì</p></td>
   <td>
    <p>Utente completo</p></td>
  </tr>
  <tr>
   <td>
    <p>Accesso al login</p></td>
   <td>
    <p>Sì</p></td>
   <td>
    <p>Utente completo</p></td>
  </tr>
    </tbody>
</table>

<!--| Report | Available | Scope |
|--- |--- |
| Content Audit Trail | Yes | Full Catalog |
| User Audit Trail | Yes | Full User |
|Login Access | Yes | Full User |-->

## Integrazione avanzata di Connect

Gli istruttori possono personalizzare le proprie sessioni selezionando stanze specifiche per loro. In questa versione, sono stati apportati i seguenti miglioramenti:

### Importa trascrizioni

Potrai importare le trascrizioni di sessione da Connect e analizzare le trascrizioni. Gli Allievi ricevono le trascrizioni dopo la registrazione e possono scaricarle in un secondo momento.

### Modifica video

Gli istruttori possono modificare il video e migliorare l’esperienza di visualizzazione degli Allievi. Utilizzando il link in Panoramica sessione, possono collegarsi alla pagina di accesso di Adobe Connect. Dopo l’accesso, visualizzano il link della registrazione su cui possono fare clic per accedere al video e modificarlo.

## Limitazione dei report del dashboard agli utenti con ruolo di Manager

Gli amministratori possono cercare solo i manager nei report del dashboard.

## Limitazione elaborazione report del dashboard precedenti

Quando un Amministratore tenta di tracciare un report del dashboard e il tracciamento del report richiede troppo tempo (più di 2,5 min), in un Adobe di Learning Manager viene visualizzato il seguente messaggio:

![immagine report legacy](assets/error-message.png)
*Messaggio di errore quando il report richiede troppo tempo*

I report di questa entità non possono essere visualizzati sull’interfaccia utente, ma l’Amministratore può scaricarli.

## Supporto per la migrazione delle etichette del catalogo

Ora il flusso di lavoro Migrazione supporta le etichette del catalogo. I file CSV per la migrazione possono essere utilizzati per importare le chiavi e i valori delle etichette del catalogo e associarli a corsi, percorsi di apprendimento, certificazioni e risorse formative. Il flusso di lavoro può anche essere utilizzato per eliminare valori e chiavi errati, se necessario.

## Miglioramenti alle API per applicare filtri avanzati ai corsi

Sarà ora possibile filtrare in modo avanzato i corsi per tag e etichette del catalogo (utilizzando una combinazione di condizioni &quot;AND&quot; e &quot;OR&quot;) tramite le API di Learning Manager.

## Modifiche alle API introdotte da questa versione

### Convalida nell’API dei processi

In questa versione, se il report Risorsa formativa supera i 10 milioni generati utilizzando l’API del processo, la risposta conterrà il messaggio: &quot;Nel report richiesto sono presenti troppi dati da generare, provare ad applicare i filtri della risorsa formativa!&quot;.

### Notifiche di contenuti eliminati

Nelle versioni precedenti di Adobe Learning Manager, se un corso, una certificazione o un piano di apprendimento veniva eliminato e compariva una notifica, era comunque possibile accedere al contenuto cliccando sulla notifica.

In questa versione, ci assicureremo che un post eliminato non sia più accessibile. Se si specifica l&#39;ID in /posts/{id} e l’ID del post non è più disponibile, viene visualizzato il messaggio &quot;Post non trovato per la risorsa specificata&quot;.

### Scadenza per il completamento del corso con le API degli Allievi

Le versioni precedenti di Adobe Learning Manager recuperavano la scadenza dalla tabella di iscrizione. Questa versione, invece, la ottiene dalla tabella delle istanze del corso. Se la scadenza non è disponibile, viene recuperata dalla tabella di iscrizione.

### Flag di esclusione

La versione di novembre 2023 di Adobe Learning Manager disattiva il flag di esclusione nelle API, in quanto non fa parte delle specifiche dell’API pubblica ed è dunque destinato al test in back-end. Il flag non è più disponibile per le API degli Allievi, ma è ancora valido per le API degli Amministratori.

Il motivo per cui il flag per le API degli Allievi viene rimosso è perché il flag di esclusione recuperava una grande quantità di dati tramite le API degli Allievi.

D’ora in avanti, la seguente API per Allievi non funzionerà più perché contiene il flag di esclusione.

`https://captivateprime.adobe.com/primeapi/v2/users?page[offset]=0&page[limit]=10&sort=id&override=TRUE`

### Modifica impostazione predefinita per highlightResults

Nella prossima versione di Adobe di Learning Manager, ad esempio, nell’API /search, l’impostazione predefinita per highlightResults viene modificata in false.

Inoltre, modificheremo l’impostazione predefinita di snippetTypes in courseName. In questo modo i nomi dei corsi verranno evidenziati nella ricerca solo se highlightResults è True.

### Nuovo tipo di risorsa per i quiz

La `instances.loResources.resources` l&#39;endpoint restituirà `ResourceContentType` con quiz.

## Avviso di disattivazione

Il 30 novembre 2023 LinkedIn GET Learning disattiverà il metodo HTTP per ottenere un token OAuth. Dopo la rimozione, sarai in grado di generare un token OAuth solo utilizzando il metodo HTTP POST.
Adobe Learning Manager disattiverà BlueJeans a febbraio 2024. Tutti i nuovi account aperti dopo febbraio 2024 non includeranno il connettore BlueJeans.

## Note sulla versione

Per informazioni sulle versioni correnti e precedenti dell’app Web e per dispositivi di Learning Manager, consulta la [Note sulla versione](release-note/release-notes.md).

## Bug corretti in questa release

* La miniatura di un corso, ossia il prerequisito di un percorso di apprendimento o un altro corso, non veniva visualizzata quando un Allievo apriva la pagina di anteprima del percorso di apprendimento o del corso.
* Se le opzioni Calendario, Gamification e Apprendimento sociale non erano selezionate, l’impostazione della dashboard per Allievi non salvava l’impostazione successiva. Le opzioni come Consigliato nelle tue aree di interesse e Sfoglia per catalogo venivano visualizzate non come selezionate, ma nell’anteprima.
* Gli Allievi ricevevano un promemoria via e-mail per completare il corso anche se lo avevano terminato.
* Non era possibile scaricare i report del dashboard per gli account condivisi tra pari.
* L’eliminazione e l’aggiunta di un modulo per una checklist in un corso generava un errore interno.
* Nel caso dei modelli Invito alla sessione, l’ID relativo all’e-mail del mittente conteneva il testo captivatePrime invece di AdobeLearningManager.
* Se si utilizzava Efficacia corso come asse Y secondario, il download del report non andava a buon fine con l’eccezione Puntatore Null.
* Se a un Allievo veniva assegnato il ruolo di Amministratore personalizzato, passava al profilo di Amministratore personalizzato per impostazione predefinita. Tuttavia, se nell’account era impostato un URL di reindirizzamento per Allievi, l’Amministratore personalizzato accedeva a una pagina diversa, non al profilo di Amministratore personalizzato.
* L’ambito Gamification non funzionava come previsto se disabled_sub_groups era impostato su un numero molto alto.
* In alcuni casi, gli utenti eliminati attivavano una migrazione.
* Gli Allievi non riuscivano a riprodurre i corsi LinkedIn nell’app MS Teams.
* L’API Enrollment non restituiva le iscrizioni a un piano di apprendimento Flex o incorporato come previsto.
* Nell’app mobile, i nomi di un corso, una certificazione o un piano di apprendimento venivano visualizzati in minuscolo.
* Nelle versioni precedenti di Adobe Learning Manager, se un corso, una certificazione o un piano di apprendimento veniva eliminato e compariva una notifica, era comunque possibile accedere al contenuto cliccando sulla notifica. In questa versione, ci assicureremo che un post eliminato non sia più accessibile. Se si specifica l&#39;ID in /posts/{id} e l’ID del post non è più disponibile, viene visualizzato il messaggio &quot;Post non trovato per la risorsa specificata&quot;.
* Nell’API per Allievi, il campo relativo alla scadenza per il completamento non veniva visualizzato nella risposta dell’API Enrollment.
* Nell’API Get Enrollment, i dettagli dell’iscrizione venivano visualizzati anche dopo aver specificato un ID istanza errato.

## Problemi noti in questa versione

* Una nuova iscrizione o l’aggiornamento di una esistente non va a buon fine quando un piano di apprendimento Flex si trova in un altro piano di apprendimento Flex.
* L’URL della trascrizione non visualizza le registrazioni nelle sessioni di Adobe Connect.
* Gli Allievi possono ripetere un quiz offline nell’app per dispositivi mobili anche se non lo superano.

## Requisiti di sistema

[Requisiti di sistema di Learning Manager](system-requirements.md)

## Versioni precedenti di Adobe Learning Manager

<!--* [November 2023 release](whats-new-november-2023.md)-->
* [Versione di luglio 2023](whats-new-2023-july.md)
* [Versione di aprile 2023](whats-new-2023-april.md)
