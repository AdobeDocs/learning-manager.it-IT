---
description: Note sulla versione di Adobe Learning Manager
jcr-language: en_us
title: Note sulla versione di Adobe Learning Manager
contentowner: jayakarr
exl-id: ae9251b6-5326-42c2-881e-2ab3393d9e17
source-git-commit: 96e875a2b2cd2866a624068b5e8e18aabb39d888
workflow-type: tm+mt
source-wordcount: '26470'
ht-degree: 72%

---

# Note sulla versione di Adobe Learning Manager

<!--<table>
 <tbody>
  <tr>
   <td><img src="assets/cp-prime-appicon-88x84.png"></td>
   <td>
    <p><a href="https://business.adobe.com/products/learning-manager/adobe-learning-manager.html">Adobe Learning Manager</a> was launched in August 2015. As part of our continuous improvement efforts to enhance the product, we have been rolling out regular updates. Read on to know the features enhanced/issues fixed in update releases.<br></p></td>
  </tr>
 </tbody>
</table>-->

+++Aggiornamento 99: versione di febbraio 2025 di Adobe Learning Manager

## Configurazione della lingua dell’interfaccia tramite SAML

Adobe Learning Manager (ALM) ora accetta un attributo SAML per la lingua. Questo attributo viene quindi mappato alle impostazioni dell&#39;interfaccia utente e del linguaggio dei contenuti, garantendo un&#39;interazione uniforme con l&#39;LMS nella lingua preferita. La configurazione di queste impostazioni della lingua viene gestita tramite la piattaforma Identity and Access Management (IAM), utilizzando SAML per Single Sign-On (SSO). Ciò supporta sia gli accessi avviati dal provider di servizi (SP) che quelli avviati dal provider di identità (IdP), consentendo agli utenti di visualizzare l&#39;interfaccia e il contenuto nella lingua scelta.

Per ulteriori informazioni, fai riferimento a questo [articolo](/help/migrated/administrators/feature-summary/set-up-interface-language-through-saml.md).

## Miglioramento delle API di migrazione

In precedenza, nei moduli di attività con collegamenti esterni migrati tramite API (`GET /bulkimport/cansync` e `POST /bulkimport/startrun`) non veniva visualizzata l’opzione **[!UICONTROL Contrassegna come completato]** per gli Allievi dopo aver effettuato l’accesso al collegamento. Questo problema è stato risolto. Ora i moduli di attività con collegamenti esterni migrati tramite API visualizzeranno correttamente l’opzione **[!UICONTROL Contrassegna come completato]** per gli Allievi.

## Funzionalità di ordinamento nell’app per Allievi

La funzione di ordinamento nell’app per Allievi fornisce raccomandazioni personalizzate per i corsi in base al contenuto e alla lingua dell’interfaccia. &#x200B; Questo miglioramento semplifica il processo per gli Allievi di trovare i corsi nella lingua preferita e utilizza opzioni di ordinamento più intelligenti.

Per ulteriori informazioni, fai riferimento a questo [articolo](/help/migrated/learners/feature-summary/catalogs.md#sorting-functionality-in-the-learner-app).

+++

+++Aggiornamento 98: versione di novembre 2024 di Adobe Learning Manager

**Data di pubblicazione**: 16 novembre 2024

## Novità di questa versione

Per ulteriori informazioni, fai riferimento alla pagina [Novità di Adobe Learning Manager](/help/migrated/whats-new.md).
+++

+++Aggiornamento 97: versione di luglio 2024 di Adobe Learning Manager

**Data di pubblicazione:** 13 luglio 2024

## Novità di questa versione

Per ulteriori informazioni, fai riferimento alla pagina [Novità di Adobe Learning Manager](/help/migrated/whats-new-july-2024.md).
+++

+++Aggiornamento 96: versione di marzo 2024 di Adobe Learning Manager

**Data di pubblicazione:** 7 marzo 2023

## Novità di questa versione

Per ulteriori informazioni, fai riferimento alla pagina [Novità di Adobe Learning Manager](/help/migrated/whats-new-march-2024.md).
+++

+++Aggiornamento 95: versione di novembre 2023 di Adobe Learning Manager

**Data di pubblicazione:** 18 novembre 2023

## Novità di questa versione

Per ulteriori informazioni, fai riferimento alla pagina [Novità di Adobe Learning Manager](/help/migrated/whats-new-november-2023.md).
+++

+++Aggiornamento 94

**Data di pubblicazione:** giovedì 23 agosto 2023

## Novità dell’aggiornamento

* Seleziona l’icona dell’ingranaggio del lettore per modificare la qualità del video.
* Modifica la qualità e la velocità di un video sui social.
+++

+++Aggiornamento 93: versione di luglio 2023 di Adobe Learning Manager

**Data di pubblicazione:** 10 luglio 2023

Novità di questa versione

### I suggerimenti sono stati migliorati

Adobe Learning Manager ha introdotto un sistema nuovo e rinnovato di suggerimenti per i corsi. Questa funzione di consigli utilizza algoritmi di intelligenza artificiale e gli interessi degli utenti come Prodotti, Ruoli e Livelli per fornire consigli sui contenuti personalizzati.

### Iscrizione multipla

In questa versione di Adobe Learning Manager, stiamo introducendo l’iscrizione multipla per gli Allievi, opzione che consente agli Allievi di iscriversi a più istanze di un corso in uno o più periodi.

### Rimozione Del Connettore Exavault

Questa versione di Adobe Learning Manager includerà un nuovo connettore, che utilizzerà il protocollo SFTP della famiglia di prodotti AWS Transfer.

Per ulteriori informazioni, consulta [Novità della versione di luglio 2023 di Adobe Learning Manager](/help/migrated/whats-new-2023-july.md).
+++

+++Aggiornamento: 92

**Data di pubblicazione:** 23 giugno 2023

**Bug corretti in questo aggiornamento**

* Dopo aver completato un modulo, l’API del livello non viene attivata automaticamente, pertanto il segno di spunta verde non viene visualizzato come previsto nell’interfaccia utente.
* Dopo aver completato alcuni moduli di un percorso di apprendimento o una certificazione, il segno di spunta verde che indica il corretto completamento non viene visualizzato come previsto.
* Adobe Learning Manager non si avvia come previsto dopo aver caricato un file CSV di un utente con campi errati.
* Il messaggio pop-up di avviso su come contattare l’Amministratore visualizza anche altri indirizzi e-mail.
* Tutti i distintivi ottenuti da un Allievo non vengono visualizzati nella risposta.
* Durante la registrazione dell’utente, è necessario accettare un nome utente con &quot; &quot;.

#### Lettore

* Aggiungi un menu per selezionare la risoluzione dello schermo durante la riproduzione di un video.
+++

+++Aggiornamento 91

**Data di pubblicazione:** venerdì 1 giugno 2023

### Connettori

* Il connettore Adobe Connect richiede le API per inviare i token CSRF. Per ulteriori informazioni, consulta Migliorare la sicurezza dell’account Adobe Connect.

### Modifica della stringa

* Abbiamo rinominato la stringa Valuta questo corso in Valuta questo corso, Valuta questo percorso di apprendimento o Valuta questa certificazione, in base al corso seguito da un Allievo. A seconda del tipo di corso di formazione, l’Allievo vede la stringa di conseguenza.

### Bug corretti in questo aggiornamento

* La descrizione dell’app mobile Adobe Learning Manager di Play Store riporta erroneamente che un Allievo può seguire un corso offline.
* Si sono verificati problemi durante la migrazione dei contenuti (module_version.csv e course_module.csv) da LinkedIn a Adobe Learning Manager.
* Se un account si trova in uno stato inattivo e viene creato più di tre anni fa, tutti gli utenti dell’account vengono eliminati tramite il RGPD, indipendentemente dallo stato degli utenti.
* Nell’app Istruttore, quando il limite della lista d’attesa per una sessione viene impostato su zero, e la sessione viene salvata, nell’interfaccia utente viene visualizzato erroneamente il messaggio “Non applicabile” anziché zero.
* Quando le trascrizioni degli allievi per il connettore Power BI vengono generate, nella colonna Durata del corso di formazione o del modulo (minuti) vengono visualizzati valori nulli per alcuni moduli classe o classe virtuale.
* Dopo aver contrassegnato un corso come completato per gli Allievi in una o più istanze, vengono contrassegnati come completi tutti gli Allievi del corso, non solo gli Allievi nell’istanza o nelle istanze correnti.
+++

+++Aggiornamento 90

**Data di pubblicazione:** 4 aprile 2023

### Bug Corretti In Questo Aggiornamento

L&#39;accesso SAML non riesce se l&#39;URL di accesso SSO contiene l&#39;entity_id.
+++

+++Aggiornamento 89: versione di marzo 2023 di Adobe Learning Manager

**Data di pubblicazione:** 4 aprile 2023

### Novità dell’aggiornamento

**Miglioramenti dell&#39;esperienza di formazione con istruttore (ILT)**

Sono stati apportati diversi miglioramenti all’esperienza di formazione con istruttore (ILT). I miglioramenti principali includono: la possibilità di filtrare le sessioni in aula in base alla posizione, la possibilità di cambiare istanza (VILT) senza perdere i progressi, un nuovo &quot;Assistente alla pianificazione&quot; per la gestione dei conflitti nella prenotazione di istruttori e classi, la possibilità di allegare &quot;Abilità&quot; agli istruttori e scegliere Istruttori in base alle abilità.

**Miglioramenti all&#39;elenco di controllo delle osservazioni**:

Gli Autori ora possono selezionare &quot;Manager&quot; e &quot;Store Manager&quot; come Observer per le liste di controllo. I manager possono visualizzare e completare gli elenchi di controllo nell’interfaccia Manager senza dover passare al ruolo di Istruttore. Quando a un manager viene assegnato un elenco di controllo, riceve una notifica.

**Usa qualsiasi app/fotocamera per smartphone per scansionare i codici QR di Learning Manager**

Gli Allievi ora potranno utilizzare qualsiasi app di scansione di codici QR o la fotocamera dello smartphone per acquisire i codici QR generati da Learning Manager per l’iscrizione al corso, il completamento e altro ancora.

**Miglioramenti alla creazione di rapporti**

Un nuovo rapporto Utilizzo istruttore, un rapporto Revisione corsi di formazione, un rapporto Risorse formative e altri miglioramenti a livello di creazione di rapporti.

**Supporto per sessioni &#39;ibride&#39;**

Adobe Learning Manager ora supporta la possibilità di creare sessioni di formazione con istruttore &quot;ibride&quot; (ILT). Le sessioni ILT virtuali possono essere create con informazioni sulla posizione facoltative in modo che gli Allievi possano partecipare alla sessione anche di persona se si trovano sul posto.

**Migliore monitoraggio dello stato di avanzamento per aula e ILT virtuale**

I moduli classe e ILT virtuali ora consentono di segnalare lo stato del quiz di un Allievo (superato o non superato) insieme allo stato di partecipazione. Quindi, è possibile prendere in considerazione sia la partecipazione che i risultati del quiz per decidere l’avanzamento dell’Allievo.

**App Adobe Learning Manager per Microsoft Teams**

La nuova app Adobe Learning Manager su Microsoft Teams è progettata per favorire l’apprendimento nel flusso di lavoro e rendere più efficiente l’apprendimento sociale. Gli Allievi potranno accedere ai contenuti di apprendimento all’interno della piattaforma Microsoft Teams senza dover passare a un browser. Contatta il CSAM per la versione beta dell’app Adobe Learning Manager su MS Teams.

### Bug corretti in questo aggiornamento

**Corso**

* Un Autore personalizzato non può visualizzare in anteprima un modulo quando il corso è nello stato “UNDER_CONSTRUCTION”. La risposta mostra l’errore 404.
* Il titolo del corso nella pagina di aggiunta o del corso di un’app Autore si espande quando supera un determinato limite di caratteri.

**Autore**

* Nell’app Autore, il titolo del corso (se lungo) supera i limiti della pagina durante la creazione di un corso.
* A volte viene aggiunto un corso anche se non è selezionato alcun Autore.

**Report dashboard**

* Le descrizioni comandi vengono visualizzate correttamente quando la lingua dell&#39;interfaccia è l&#39;inglese, ma genera un errore di console quando la lingua dell&#39;interfaccia è diversa.
* Rinomina &quot;Obbligatorio&quot; in &quot;Obbligatorio&quot; nel dashboard Allievo.

**App per istruttori**

* Il formato dell’ora nell’app per istruttori non è coerente con le altre app.

**Social**

* Per alcuni tipi di post, dopo la pubblicazione, la bacheca social non si apre come previsto.

**Amministrazione**

* Un utente con un ruolo personalizzato non riesce scaricare le risorse durante l’anteprima di un corso.

**Modelli e-mail**

* Quando un Allievo annulla l’iscrizione a un programma di apprendimento che contiene un corso virtuale/in aula, non riceve alcuna e-mail con la notifica dell’annullamento.

**Risorse formative**

* Non è possibile visualizzare il nome del corso nel widget Risorsa formativa.

**Pubblicazione**

* La descrizione del modulo aggiunta in Adobe Captivate non è visibile in Learning Manager quando il modulo viene pubblicato in ALM.

**Campi attivi**

* Quando un file CSV con un numero elevato di record è in fase di elaborazione, l’elaborazione richiede un periodo di tempo significativo durante il quale, se un utente accede e immette un valore per uno degli attributi, potrebbe creare un nuovo gruppo di utenti che potrebbe generare errori CSV. Per risolvere questo problema, quando è in corso l’importazione di CSV, il messaggio a comparsa dell’attributo Campi attivi è disabilitato e riabilitato una volta completato il caricamento di CSV.
* Se la colonna nel file CSV Utenti ha lo stesso nome del campo attivo utenti esterni, il caricamento del file CSV non riesce.

**Correzioni relative alle API**

* Nella risposta learningObjects, l’attributo del segnalibro non è presente.
* Viene creata una voce di accesso durante la generazione di token di aggiornamento oauth per gli utenti eliminati.
* L’API LO restituisce un formato lo errato, poiché per il calcolo del tipo di corso e del contenuto principale sono stati considerati moduli di preparazione.

**Problemi noti in questo aggiornamento**

* Il pulsante Condividi sul catalogo degli Allievi non funziona come previsto nel browser safari e nell’app MS Teams per dispositivi mobili e iPad.
* Le notifiche non vengono visualizzate nella scheda Attività dopo che l&#39;app è stata rimossa da altri computer.
Quando viene fatto clic sulle notifiche nella scheda Attività dell’app su iPhone 14 non avviene nulla.
* Nell’app MS Teams, le notifiche di Learning Manager (completato, iscritto, in scadenza e scaduto) non mostrano lo stato e il nome del corso nella scheda Attività.
* Viene visualizzata una finestra a comparsa con contenuti XML quando l’Amministratore di integrazione non approva l’app MS Teams.
* La lingua dell’interfaccia utente nell’app Adobe Learning Manager su MS Teams a volte non cambia come previsto quando viene modificata.
* Non è possibile interagire con la prima notifica quando l’elemento attivo è nell’Iframe (schede Home e Catalogo).

**Limitazioni dell&#39;app per dispositivi mobili Adobe Learning Manager**

* Visualizzazione dei contenuti offline.
* Vista Griglia/Elenco nella pagina Catalogo/Il mio apprendimento.
* Più tentativi di seguire un corso.
* Scadenza per l’iscrizione sulla scheda di un corso.
* Sui dispositivi iOS, le notifiche push non vengono visualizzate quando l&#39;app è in primo piano.
* I collegamenti diretti nelle notifiche push non reindirizzano alla pagina di destinazione prevista.
* Facendo clic sul pulsante Registra interessi si verrà reindirizzati al Web.
* Durante la risposta o l’inserimento di commenti in Apprendimento sociale, non potrai allegare un file.
* Non potrai accedere a LinkedIn Learning.
+++

+++Aggiornamento 88

**Data di pubblicazione:** 7 marzo 2023

### Miglioramenti Delle Prestazioni In Questa Versione

Quando viene eseguita un’iscrizione in blocco degli Allievi, non viene generato alcun file registro per ciascun Allievo.
È stata ottimizzata l’elaborazione dei piani di apprendimento per gli account di grandi dimensioni. In questo modo si evitano problemi di ricerca o ritardi.
+++

+++Aggiornamento 87

**Data di pubblicazione:** 1° marzo 2023

## Bug Corretti In Questo Aggiornamento

* Un Allievo non riceve l’e-mail di annullamento della sessione se il modulo CR/VC viene rimosso dal corso registrato.
* Cambia GetNotificationData da GET a POST. L&#39;implementazione originale ha generato l&#39;errore **IllegalArgumentException: l&#39;intestazione della richiesta è troppo grande** e ciò ha portato a notifiche non riuscite.
+++

+++Aggiornamento: 86

**Data di pubblicazione:** 17 febbraio 2023

### Bug Corretti In Questa Versione

Nell’app per Allievi, non è possibile cercare utenti e gruppi di utenti a causa di alcuni problemi relativi alle impostazioni locali.
+++

+++Aggiornamento 85

**Data di pubblicazione:** martedì 13 febbraio 2023

### Cosa è cambiato in questo aggiornamento

È stato aggiunto il supporto per il codice a quattro lettere della lingua durante il filtraggio delle lingue in GET managerapi/v2/learningObjects.

### Bug Corretti In Questo Aggiornamento

Per alcune lingue, la ricerca restituisce risultati errati.
I metadati del corso vengono sovrascritti quando il corso dispone di più varianti della stessa lingua.
+++

+++Aggiornamento 84

**Data di pubblicazione:** venerdì 2 febbraio 2023

### Cosa è cambiato in questo aggiornamento

**Report risorsa formativa**

Questo aggiornamento presenta un nuovo report Risorse formative che elenca tutte le risorse formative nell’account.

**Controllo versione**

È stato aggiunto il controllo delle versioni per le risorse quando si aggiungono risorse durante la creazione di un corso.

**Report per tentativi**

Puoi visualizzare un report di tutti i tentativi e le revisioni effettuate da un Allievo per ogni corso di formazione.

**API reimpostazione modulo**

Un amministratore può ora reimpostare un modulo utilizzando l’API di ripristino moduli. Per ulteriori informazioni, consulta il [Riferimento API di Adobe Learning Manager](https://captivateprime.adobe.com/docs/primeapi/v2/).

**Modello e-mail**

Per alcuni modelli e-mail, è ora possibile aggiungere un prerequisito al modello.

**Altre modifiche**

* Puoi aggiungere un corso approvato dal Manager come prerequisito.
* Miglioramento delle prestazioni durante l&#39;aggiornamento del dashboard di riepilogo dell’apprendimento.
* Gli ID e-mail e gli ID account vengono verificati prima dell’invio di un report di bounce.

### BUG CORRETTI IN QUESTO AGGIORNAMENTO

* I nomi degli autori duplicati vengono visualizzati nella pagina di panoramica del corso.
* Un collegamento ipertestuale nella pagina di creazione dell’account ha generato l’errore 404.
* La lingua ceca non appare come previsto nelle impostazioni del lettore.
* In alcuni casi, le abilità vengono visualizzate come indefinite per gli Allievi in corso e gli Allievi iniziali.
* Il tempo trascorso in più giorni mostra il tempo diverso impiegato nei report di trascrizione degli Allievi e di iscrizione.
* Il pulsante Indietro non risponde per i profili Amministratore e Manager in Corso > Punteggio quiz L2 > Per domanda, scheda Frequenza e punteggio rispettivamente.
* Per alcune lingue, in un modello e-mail manca del contenuto nel corpo del messaggio e-mail e la traduzione nella lingua nel modello non è coerente.
+++

+++Aggiornamento 83

**Data di pubblicazione:** 18 gennaio 2023

### Cosa è cambiato in questo aggiornamento

**Nuova colonna**

Una nuova colonna, **unenrollmentAllowed**, viene aggiunta a course.xlsx. Scarica il file da questo manuale.

**Connettore Linkedin Learning**

Per il connettore LinkedIn Learning, è disponibile una nuova casella di controllo per permetterei agli Allievi di annullare l’iscrizione nella pagina Filtri. Per ulteriori informazioni, consulta [Connettore LinkedIn Learning](/help/migrated/integration-admin/feature-summary/connectors.md).

### Bug Corretti In Questo Aggiornamento

* Quando si passa con il mouse sui grafici a barre, la descrizione del report del dashboard viene visualizzata come previsto.
* Nei report in Attività degli utenti, il report Tempo impiegato per l’apprendimento mostra dati errati per i dati giornalieri/mensili.
* In alcuni casi, il grafico del punteggio del quiz visualizza valori errati.
* In un corso con contenuti SCORM con più tentativi impostati, quando un Allievo tenta di seguire il corso, il pulsante Rivedi è disabilitato.
* In alcuni casi, dopo aver iscritto un Allievo a un corso e aver scaricato un registro di controllo delle e-mail, l’e-mail viene recapitata, ma non viene visualizzata nel registro.
* L’invito nel calendario di un Istruttore deve includere l’Istruttore di testo nell’oggetto.
* L’icona della scheda di formazione non si riflette sulla raccomandazione relativa ai corsi e sulle schede Percorso di apprendimento presenti nella pagina Panoramica del corso.
* Nelle impostazioni della pagina principale dell’Allievo, aggiungi la sezione Salvato da me.
* Per alcuni account, all’utente viene richiesto l’accesso SSO per un account in cui è necessario l’ID Adobe.
* Nei fusi orari con ora legale, il campo &#39;start_time&#39; viene calcolato in base alla differenza di orario corrente, non in base alla differenza di orario nella data e ora di inizio effettive. Ciò ha causato inviti con orari errati.
* Quando una certificazione è ricorrente, viene creata internamente nel database una copia dei corsi sottostanti. Questi corsi appaiono quindi in cerca, contrariamente al comportamento previsto.
* Quando il caricamento di un file CSV non riesce, non ricevi alcuna notifica e-mail.
* Se i nomi dei campi attivi sono lunghi, scompaiono quando vengono trascinati o rilasciati. Di conseguenza, anche il pulsante Salva non funziona come previsto.
* Un report di sessione non viene esportato tramite la pagina presenze e punteggio di un corso se il primo utente nel report dispone di un record nella tabella di valutazione delle attività con il commento null.
* Quando utilizzi l’account amministratore per recuperare i badge, puoi ordinare l’elenco come previsto. Tuttavia, quando si esegue la stessa operazione per un Allievo, i risultati non vengono ordinati.
* Se scegli un corso dai risultati della ricerca e poi tenti di tornare ai risultati della ricerca utilizzando il pulsante Indietro, i risultati della ricerca scompaiono.
* Non tutti gli utenti vengono aggiunti a un gruppo di utenti come istruttori in una sessione.
* Nei modelli che contengono più modelli utente, l’oggetto viene sostituito da alcuni valori.
+++

+++Aggiornamento 82

**Data di pubblicazione:** 15 dicembre 2022

* L’API GET LO ora include informazioni sui prezzi, se disponibili.
* Ai report LT viene aggiunta una nuova colonna, Completato da, Questo aiuta l’amministratore a identificare la fonte di completamento di un LO.
* Abbiamo aggiunto un nuovo modulo ILT in grado di registrare lo stato di superamento o meno dell’Allievo insieme alla partecipazione. Gli istruttori ora possono contrassegnare un Allievo con l’opzione di partecipante promosso o partecipante bocciato.
* Un Amministratore può ora richiedere agli Allievi il completamento e superamento di un modulo o corso prima di passare al successivo. Si applica a corsi propedeutici, corsi in sequenza e LP.

**Correzioni di bug**

* Problemi della lingua bahasa relativi all’esperienza mobile immersiva sulla barra laterale e sul piè di pagina.
* Correzioni di visualizzazione immersiva correlata all’anteprima del modulo.
* Una ricerca del corso in Amministratore e autore restituisce impostazioni internazionali diverse da quelle digitate.
* Le modifiche apportate ai modelli e-mail di benvenuto non venivano salvate dopo la modifica.
* Gli utenti con ID e-mail e ID Adobe diversi non riuscivano ad accedere all’app mobile.
* Gli utenti sono stati identificati in modo errato durante le sessioni di Zoom/BJ VC.
+++

+++Aggiornamento 81 - Versione di novembre 2022 di Adobe Learning Manager

**Data di pubblicazione:** 05 novembre 2022

**Nota:** con questa versione di Adobe Learning Manager, gli utenti con account inattivi non possono più accedere ai propri account utilizzando i sottodomini. È possibile accedere agli account utilizzando l’ID account o la pagina acapindex.html e inserendo l’ID e-mail.

### Novità di questa versione

La versione di Adobe Learning Manager di novembre 2022 è costituita dai seguenti elementi:

* Configurazione SSO multipla
* Supporto di funzioni senza accesso
* Miglioramenti della pagina Panoramica sulla formazione
* Personalizzazione del lettore
* Impersonificazione dell’Allievo e del Manager

**Nota:** Con la versione di novembre 2022 di Adobe Learning Manager, Zoom interromperà l&#39;autenticazione [JWT a partire da giugno 2023](https://marketplace.zoom.us/docs/guides/auth/jwt/). Di conseguenza, il connettore Zoom con JWT continuerà a funzionare alla suddetta data, ma suggeriamo agli utenti di creare un’app OAuth Server-to-Server per sostituire la funzionalità nel proprio account. Per impostazione predefinita, tutte le nuove connessioni dispongono dell’autenticazione Zoom OAuth.

### Bug corretti in questo aggiornamento

* In qualità di Allievo, quando tenti di accedere a un programma di apprendimento con più di 10 corsi su dispositivi mobili, viene visualizzato un messaggio di errore.
* Se un corso ha impostato un promemoria da inviare nei giorni successivi al mancato rispetto della scadenza, l’e-mail viene inviata dopo n giorni come previsto, ma il numero di giorni in cui la scadenza non viene rispettata corrisponde a n-1, non a n.
* Un video non viene caricato nel lettore se il feedback L1 è abilitato per il corso nell’app Allievo e l’utente ha solo il ruolo di Allievo.
* Nell’e-mail di promemoria di completamento non viene visualizzata l’ora nel fuso orario dell’utente come previsto.
* Le trascrizioni degli Allievi generate tramite i report del dashboard non rispettano i filtri e mostrano più informazioni del necessario.
* Non è possibile selezionare il contenuto per cui la lingua dell’interfaccia non è aggiunta come lingua del contenuto.
* Quando si effettua la registrazione autonoma per un secondo corso, l’URL che appare non è corretto.
* Quando un istruttore viene rimosso da una sessione VC, non riceve alcuna e-mail di notifica della cancellazione della sessione.
* Il testo “minuto” su un riquadro della pagina di formazione dei discenti non viene tradotto in bahasa indonesiano come previsto.
* Il dashboard Conformità visualizza dati errati per gli Allievi non conformi.
* Durante l’aggiunta di un report, non è possibile selezionare corsi o cataloghi in cui la lingua dell’interfaccia non è stata aggiunta alla lingua del contenuto.
* In questa versione sono state aggiunte le seguenti lingue dei contenuti:
   * Bulgaro
   * Fiammingo
   * Portoghese (Brasile)

### Problemi noti in questo aggiornamento

* In alcuni casi, il grafico del punteggio del quiz non viene visualizzato come previsto. Quando ridimensionate il grafico, all’inizio viene visualizzato uno spazio vuoto. Inoltre, non vengono visualizzate tutte le domande e i dati errati vengono visualizzati in modo intermittente.
+++

+++Aggiornamento 80

**Data di pubblicazione:** 20 settembre 2022

* I problemi di accesso nell’app mobile su iOS sono stati risolti.
* È stato risolto un problema relativo alle e-mail non recapitate.
* Gli Istruttori ricevevano erroneamente una notifica anche prima che gli Allievi inviassero le proprie attività.
* Un Istruttore riceve una notifica e-mail anche se un Allievo non ha inviato un’attività.
* Dopo aver creato una sessione VC in MS Teams o Adobe Connect, gli istruttori non ricevono gli inviti alla sessione.
* Stato non corretto in un percorso di apprendimento.
* Miglioramento delle prestazioni dell’app.
+++

+++Aggiornamento 79

**Data di pubblicazione:** venerdì 18 agosto 2022

* La conferma dell’invito sul calendario per le sessioni ILT/VILT ora funziona con Google Calendar.
* I manager dei punti vendita ora possono vedere le notifiche per gli utenti subordinati anche se vengono rimossi dal ruolo di manager del personale.
* In alcuni casi, l’iscrizione al corso non va a buon fine e viene mostrato l’errore 500.
* In alcuni casi, non è possibile modificare un’istanza di corso virtuale per Teams.
* Gli amministratori e gli istruttori possono aggiungere commenti per gli utenti che non hanno partecipato a sessioni ILT/VILT.
* Miglioramento delle prestazioni durante il download di report di grandi dimensioni.
* Quando l’e-mail diretta a un utente non viene consegnata, l’Amministratore riceve una notifica e-mail. L’e-mail contiene un link che consente di scaricare un file CSV con l’elenco degli utenti a cui non sono state consegnate le e-mail. L’Amministratore può quindi intraprendere le azioni necessarie.
   * L’e-mail viene attivata quando un messaggio di posta viene rimosso o non viene recapitato.
   * L’e-mail viene attivata una volta al giorno per tutti gli amministratori aggiunti all’elenco.
   * Il link scade tra sette giorni.
* Viene mostrato un messaggio di errore durante l’integrazione di un account Adobe Connect già integrato con un altro account Learning Manager.
+++

+++Aggiornamento 78

**Data di pubblicazione:** 4 agosto 2022

### Bug corretti in questo aggiornamento

* Se il tuo corso contiene un modulo con un’anteprima e utilizzi un’API per recuperare le risorse dal corso, la risposta non conterrà dati da location, contentZipUrl e contentStructureInfoUrl.
* Risposta errata dopo l’invio di una richiesta XAPI da un documento Swagger. Il nome del dominio è learningmanager.
* Nella risposta API /boards/{id}/post, la proprietà &quot;post.attributes.myPoll&quot; appare come oggetto vuoto.
* In alcuni casi, per un utente non connesso, il pulsante Aggiungi al carrello è disabilitato per alcuni corsi o percorsi di apprendimento.
* URL del sottodominio non corretto nella pagina di branding.
+++

+++Aggiornamento 77

**Data di pubblicazione:** 24 maggio 2022

**Problemi risolti in questo aggiornamento:**

* I nuovi corsi non rispettano la sequenza nell’app Salesforce. Se modifichi la sequenza, il corso non viene visualizzato nella sequenza desiderata.
* Dopo aver modificato e salvato le impostazioni nella pagina principale classica, le modifiche non vengono salvate come previsto. Questo si verifica a tratti.
* Il codice HTML viene visualizzato quando gli Allievi controllano le notifiche, il che influisce negativamente sull’esperienza.
* Nella dashboard, il tempo impiegato per l’apprendimento viene visualizzato in modo errato come zero ore.

## AGGIORNAMENTO: Adobe Learning Manager cambierà nome in Adobe Learning Manager

Questo è un aggiornamento per aiutarti a prepararti a una modifica imminente.

**Il prodotto Adobe Learning Manager cambierà nome in Adobe Learning Manager a luglio 2022**. Si tratta di un cambiamento strategico che riflette in modo più accurato l’allineamento del prodotto a determinate priorità aziendali.

Il team del prodotto sta adottando tutte le misure necessarie per garantire che non vi sia alcun impatto sull’utilizzo della piattaforma. Potrai continuare a utilizzare il prodotto come di consueto. A luglio, gli amministratori della piattaforma potrebbero notare il nuovo nome del prodotto in alcune schermate.

Come parte di questa modifica, gli URL di accesso per Learning Manager sono interessati.

Ad esempio, se l&#39;URL di accesso per il tuo account è `https://learningmanager.adobe.com/XYZ`, il nuovo URL sarà `https://learningmanager.adobe.com/XYZ`.

Tutti gli URL esistenti continueranno a funzionare.

Per completare questa azione, collabora con il reparto IT della tua organizzazione. Per ulteriori informazioni, contattaci all&#39;indirizzo `learningmanagersupport@adobe.com`.
+++

+++Aggiornamento 76

**Data di pubblicazione:** giovedì 20 aprile 2022

* Correzioni alla terminologia dei prodotti in alcuni report del dashboard.
* Una doppia barra (//) nell’URL di un endpoint generava errori di convalida.
* Dopo l’aggiornamento di una pagina, la percentuale di completamento e l’ultimo campo visitato contenevano informazioni errate.
* Abbiamo apportato alcune modifiche al modo in cui il valore Certificato o un Piano di apprendimento vengono calcolati.
* Un Amministratore personalizzato poteva aggiungere tutti gli utenti come istruttori, anche se aveva l’autorizzazione per aggiungere solo un utente.
* In un PDF badge veniva mostrata una data di completamento errata.
+++

+++Aggiornamento 75

**Data di pubblicazione:** mercoledì 29 marzo 2022

* In alcuni account, dopo aver copiato il file CSV raw nella posizione FTP, l’importazione dell’utente non avviene come previsto e appaiono varie notifiche di errore.
* Nelle versioni precedenti di Learning Manager, per configurare un connettore Zoom, era necessario configurare prima Exavault FTP per copiare il file CSV. In questa versione, il connettore FTP non verrà più utilizzato per il file CSV, quindi non è necessario configurare prima l’FTP.
+++

+++Aggiornamento 74: istanza AWS India di Learning Manager

**Data di pubblicazione:** mercoledì 15 febbraio 2022

### Panoramica

Una [istanza](https://learningmanagerapac.adobe.com/acapindex.html) di Learning Manager verrà ora ospitata su AWS a Mumbai (ap-south-1). Per i clienti che utilizzano questa istanza India, le informazioni personali e i record di apprendimento dell’utente verranno archiviati solo in India.

### Cosa è supportato

L’istanza Adobe Learning Manager India è allo stesso livello di altre istanze come le regioni UE e Stati Uniti in termini di funzionalità. Alcune funzioni non sono supportate in India. Queste sono:

* Pagamento con carta di credito per l’acquisto di postazioni
* Creative Cloud catalogo dei contenuti
* App Slack
* **&#42;** In attesa di certificazione per conformità SOC2

### Domande frequenti

**In che modo questa istanza di Mumbai è diversa da altri ambienti solo AWS?**

Non vi è alcuna differenza. L’istanza di Mumbai è uguale alle istanze [AWS US](http://learningmanager.adobe.com/) o [AWS EU](http://learningmanagereu.adobe.com/). Questa istanza è ospitata in India e tutti i record di apprendimento e i dati degli utenti rimangono in India. Le seguenti funzioni non sono supportate nell’istanza India:

* Pagamento con carta di credito per l’acquisto di postazioni
* Creative Cloud catalogo dei contenuti
* App Slack
* **&#42;** In attesa di certificazione per conformità SOC2

**Questo ambiente sarà conforme al Common Controls Framework (CCF)?**

Sì. La nuova istanza è conforme al Common Control Framework (CCF).
+++

+++Aggiornamento 73

Data di pubblicazione: 05 febbraio 2022

* Il supporto per i modelli e-mail è ora disponibile per le lingue dei contenuti, tra cui ungherese e finlandese.
+++

+++Aggiornamento 72 - Versione di gennaio 2022 di Learning Manager

Data di pubblicazione: 28 gennaio 2019

### Novità e modifiche

* Aggiungere aule
* Modifiche alla gamification
* Connettore Microsoft Teams
* Modifiche API
* Modifiche web coinvolgenti per dispositivi mobili

<!--
For more information, see What's new in the [**January 2022 release of Adobe Learning Manager**](../whats-new.md).
-->

### Bug corretti in questa release

**Libreria dei contenuti**

* La ricerca dei file di contenuto nelle cartelle di contenuto private non funzionava per gli utenti con privilegi di ruolo personalizzati. Questo problema è stato risolto.

**Corsi**

* L’eliminazione di un corso o di un percorso di apprendimento non era possibile se avevano un’associazione storica con un piano di apprendimento. Questo problema è stato risolto. Gli utenti ora possono eliminare un corso o un percorso di apprendimento se non sono attualmente associati a un piano di apprendimento.
* Quando si visualizza l’anteprima di un corso o di un percorso di apprendimento, se il file di risorse ha un nome lungo senza spazi, il nome del file non va a capo come previsto e viene inserito nella riga successiva. Questo problema è stato risolto.
* Nel caso di aula virtuale, in precedenza era possibile creare un modulo senza selezionare alcun sistema di videoconferenza VC; in una nuova istanza l’URL VC non disponeva delle informazioni richieste. Per evitare questo problema, nella fase di creazione del modulo viene visualizzato un messaggio di errore che richiede di specificare il sistema di videoconferenza VC prima di salvare il modulo.
* La pagina della lista d’attesa mostrava un messaggio fuorviante sugli utenti registrati, che è stato rimosso.
* In caso di annullamento in blocco dei corsi, la finestra a comparsa per l’immissione degli ID e-mail non veniva visualizzata. Queso problema è stato risolto.
* L’opzione per inviare e-mail agli Allievi dalla scheda Frequenza e punteggi nell’app Amministratore e Istruttore non escludeva gli Allievi non selezionati dopo aver eseguito l’operazione Seleziona tutto. Quindi Learning Manager inviava e-mail a tutti gli Allievi. Questo problema è stato risolto.
* Il report di iscrizione viene visualizzato come &quot;Non avviato&quot;, anche se un Allievo ha già completato il corso.

**SSO**

* Nella configurazione SSO, se l’ID entità disponeva di spazi iniziali o finali, la configurazione di accesso non funzionava; questo viene ora gestito come parte della correzione.

**Annunci**

* In qualità di amministratore, le date di inizio e fine per un annuncio non venivano salvate se la lingua dell’interfaccia e dei contenuti era impostata su Deutsch/Espanol. Questo problema è stato risolto.

**Modello e-mail**

* Gli inviti alla sessione che si estendevano su più giorni in cui gli inviti non riflettevano le informazioni corrette sui giorni sono bloccati in alcuni client e-mail. Questo problema è stato risolto.
* La variabile &quot;Nome sede&quot; non era presente nel modello e-mail &quot;Promemoria della prossima sessione&quot; per gli Allievi nelle impostazioni internazionali tedesche. Questo elemento è stato aggiunto.
* Il collegamento per creare l’account come parte dell’e-mail di benvenuto per l’utente non considerava le impostazioni internazionali dell’utente. Questo problema è stato risolto.

**Promemoria e-mail**

* Se gli Allievi venivano iscritti a un corso di formazione tramite un piano di apprendimento, le e-mail di promemoria di completamento venivano inviate più volte in base al numero di modifiche apportate alle date di completamento dello stesso piano di apprendimento. Questo problema è stato risolto.

**Utente**

* È stato migliorato il messaggio mostrato all’utente quando il suo account è inattivo/sospeso, indicando di contattare l’amministratore per richiedere nuovamente l’attivazione dei propri account.

**Attività**

* Un istruttore non era in grado di visualizzare gli invii dell’Allievo se il nome del file di invio conteneva un carattere speciale. Questo problema è stato risolto.

**Segnala**

* Un amministratore non era in grado di scaricare il report di iscrizione al corso se conteneva un Allievo che era iscritto indirettamente a questo corso tramite un percorso di apprendimento flessibile, ma che doveva ancora scegliere un’istanza per questo corso nel percorso di apprendimento. Questo problema è stato risolto.
* La ridisposizione dei report nel dashboard dei report per i ruoli di amministratore e manager non manteneva lo stato dell’ordine dei report. Questo problema è stato risolto.

**Contenuto**

* L’audio nei contenuti di formazione non veniva riprodotto automaticamente nell’anteprima in modalità Allievo a causa dei criteri di riproduzione automatica del browser. Questo problema è stato risolto per i browser supportati, ad eccezione di Safari.

**Gamification**

* Se un Allievo esterno veniva convertito come Allievo interno nello stesso account, non era in grado di accedere alla classifica di gamification nell’app per Allievi. Questo problema è stato risolto.

**Lettore**

* Il lettore non mostrava messaggi di avvertenza quando l’utente cercava di saltare moduli nel corso ordinato con il tipo di moduli AICC. Questo problema è stato risolto.
* Per alcuni corsi acquisiti con moduli video nel sistema LMS senza intestazione, la riproduzione non funzionava per determinati utenti. Questo problema è stato risolto.

**Dashboard per i Manager**

* Un manager non era in grado di esportare il report per il proprio team diretto dalla pagina delle abilità team di Dashboard per i Manager. Questo problema è stato risolto.

**Publish**

* Nell’istanza europea di Learning Manager, i contenuti pubblicati direttamente su Adobe Learning Manager da Adobe Captivate venivano pubblicati nelle impostazioni internazionali Deutsch per impostazione predefinita. Questo problema è stato risolto.

**API**

* Il campo Durata viene ora aggiunto al modello Risorsa formativa.
* Per le API dei suggerimenti, a volte una richiesta GET restituisce l’errore 500.
* Quando si eseguiva la migrazione dei corsi di formazione tramite Exavault e se il testo conteneva caratteri non inglesi, veniva aggiornato con i caratteri spazzatura nel testo. Questo problema è stato risolto.

**Localizzazione**

* `NormalTextRun  BCX0 SCXW38820519 For the`App per amministratori, autori e allievi, alcuni contenuti in tedesco non vengono visualizzati come previsto.

## Problemi noti in questa versione

* Nella pagina Apprendimento sociale, quando crei un post, non riesci a registrare un audio o a caricarlo dopo aver toccato il pulsante del microfono. Questa è una limitazione del browser.
* In iOS, i file audio H264 e WMA non sono supportati nel browser per dispositivi mobili.
* Gli Allievi che hanno un + nel loro indirizzo e-mail non vedono contrassegnato il loro avanzamento. Questo avviene dopo aver seguito un corso VC in Microsoft Teams.
* Nel browser per dispositivi mobili Safari, gli allievi non potranno caricare più di 200 mb di file in Apprendimento sociale. Questa è una limitazione del browser.
+++

+++Aggiornamento 71

Data di pubblicazione: 17 novembre 2021

### Condivisione di corsi di formazione con i Manager

Learning Manager offre un dashboard di conformità a tutti gli Amministratori e i Manager. I Manager trovano molto utile monitorare la conformità dei membri del proprio team per un determinato corso di formazione. Allo stesso tempo, gli Amministratori vorrebbero che tutti i Manager aggiungessero corsi di formazione sulla conformità al loro dashboard e li monitorassero.

In Learning Manager, il flusso di lavoro **Condividi con i Manager** consente agli Amministratori di condividere i corsi di formazione con i Manager, in modo che possano essere aggiunti al dashboard di conformità di un Manager. Pertanto, i Manager non devono intraprendere alcuna azione e possono iniziare immediatamente a monitorare la conformità.

Per ulteriori informazioni, consulta [**Condivisione dei corsi di formazione con i Manager**](../administrators/feature-summary/reports.md#share_training_managers).

### Bug corretti in questo aggiornamento

* Se sono presenti due account e la funzione Percorso di apprendimento avanzato è disabilitata ed è presente un catalogo condiviso dal primo account all’altro, il percorso di apprendimento nel secondo account contiene sezioni duplicate nella pagina del corso.
* Adesso, un FTP personalizzato supporta sftp:// oltre a http:// e https://
* Adesso il connettore Exavault utilizza le API V2.
* In alcuni casi, la qualità dei video non era ottimale. Adesso il problema è stato risolto.
* Anche dopo che un Allievo ha completato un corso obbligatorio ed è stato approvato dal Manager, lo stato della certificazione rimane su In attesa di approvazione.
* Se i nomi degli Autori contengono caratteri accentati, la migrazione del corso non va a buon fine.
* Se il campo attivo contiene valori in maiuscolo, non viene salvato come previsto.
* Impossibilità di filtrare i percorsi di apprendimento in base alle abilità.
* Quando un Amministratore crea un’istanza e aggiunge una nuova sessione, l’Istruttore non riceve l’e-mail di invito a quest’ultima. Questo problema si verifica nei corsi tenuti nelle aule virtuali di Zoom.
+++

+++Aggiornamento 70

Data di pubblicazione: 28 ottobre 2021

### Bug corretti in questo aggiornamento

* In alcuni casi, le informazioni su un percorso di apprendimento non vengono indicate in una Trascrizione Allievo.
* Il testo della finestra di dialogo **Contrassegna completamento** viene aggiornato per indicare che l’operazione è irreversibile.
* In alcuni casi, l’API Oggetti di apprendimento ha restituito un errore di metadati.
+++

+++Aggiornamento 69 - Versione di ottobre 2021 di Learning Manager

**Data di pubblicazione:** 09 ottobre 2021

### Percorso di apprendimento

La versione di **ottobre 2021 di Adobe Learning Manager** introduce il concetto di percorso di apprendimento.

>[!NOTE]
>
>La pagina **Impostazioni > Generale** contiene una nuova opzione per abilitare le funzionalità estese dei percorsi di apprendimento. Se attivi questa opzione, puoi aggiungere percorsi di apprendimento in un altro. Una volta abilitata, l’opzione non può essere modificata.

I percorsi di apprendimento sostituiscono la funzionalità esistente dei programmi di apprendimento. È come se i programmi di apprendimento siano stati migliorati senza perdere nessuna funzionalità esistente. Inoltre, il nome è stato cambiato in Percorso di apprendimento.

Per ulteriori informazioni, vedi [***Percorsi di apprendimento***](../administrators/feature-summary/learning-paths.md).

### Altre modifiche

* Nuova app Salesforce
* Hub dei contenuti
* Segnalazione delle modifiche
* Report di riepilogo della sessione
* Modifiche al sommario dei contenuti del lettore
* Modifiche API
* Modifiche relative al connettore

Per ulteriori informazioni, consulta [***Novità della versione di ottobre 2021 di Learning Manager***](../whats-new.md).

### Bug corretti in questo aggiornamento

* I modelli e-mail, ad esempio per l’annullamento dell’iscrizione al corso, l’annullamento dell’iscrizione al programma di apprendimento o l’annullamento dell’iscrizione alla certificazione, non riflettono le terminologie di prodotto più recenti definite nel csv. Ora il testo predefinito nei modelli e-mail supporterà i termini personalizzati.
* La lingua dell’utente in Learning Manager non è supportata nel flusso di lavoro Pubblica su Learning Manager. Se la lingua dell’utente è diversa, la procedura da Publish a Learning Manager è in inglese.
* Se si aggiungono molti cataloghi a un ruolo personalizzato, si verifica un errore quando si aggiorna il ruolo. Ora il numero massimo di cataloghi è aumentato a 50.
* In alcuni casi, i corsi di formazione cancellati sono ancora visibili in un catalogo. Il problema si è verificato solo nell’app per amministratori ed è stato risolto ora.
* Quando il ruolo di gestione passa da un utente all’altro, il ruolo di gestione dall’utente precedente viene ancora riflesso nell’interfaccia utente. Questo problema è stato risolto. Questo problema era presente solo per gli utenti esterni e non per gli utenti interni.
* In alcuni scenari specifici per un ampio gruppo di utenti che vengono importati tramite il csv dell’utente, l’importazione non è riuscita. Questo problema è stato risolto.
* Una trascrizione di apprendimento non visualizza la data di completamento di un certificato esterno se viene aggiunto un corso obbligatorio dopo la creazione di un certificato esterno e un utente vi viene iscritto. Questo problema è stato risolto.
* Un certificato non visualizza il nome localizzato dell’Allievo come previsto. Questo problema è stato risolto.
* In caso di sessioni in aule virtuali di Zoom, un istruttore non riceve sempre l’invito per la sessione. Questo problema è stato risolto. L’istruttore ora riceve la comunicazione richiesta.
* Un Allievo non riceve inviti per una sessione se i modelli a livello di corso sono abilitati, ma i modelli a livello di account sono disattivati. Questo problema è stato risolto.
* Per fusi orari specifici, i promemoria tramite posta elettronica sono stati recapitati il giorno successivo a quello previsto. Questo problema è stato risolto.
* Gli Allievi non ricevono messaggi di notifica della sessione se alcuni modelli di posta elettronica sono disattivati.
* Nel caso in cui una riunione BlueJeans venga aggiornata da Autori, Amministratori, l’URL della riunione BJ diventa inutilizzabile. Questo problema è stato risolto.
* Quando si esegue l’API GET/LO in alcuni casi, i corsi che fanno parte di un programma di apprendimento non vengono restituiti.
* Se l’Allievo tenta di caricare contenuto il cui nome ha uno spazio vuoto, l’Allievo riscontra un errore interno del server.
* I file PDF di badge generati per gli Allievi hanno avuto problemi di formattazione quando sono stati generati in lingue non inglesi. Tali questioni sono state ora risolte.
+++

+++Aggiornamento 68

Data di pubblicazione: 28 settembre 2021

### Bug corretti in questo aggiornamento

* Sul browser mobile, i collegamenti diretti sono stati abilitati per le funzioni seguenti:

   * Tutte le bacheche
   * Bacheca pubblica e post
   * Bacheca privata e post con accesso
   * Bacheca privata e post senza accesso
   * Bacheca limitata e post
   * Commento al post
   * Risposta al commento
   * Profilo utente social

* Per gli account che utilizzano un dominio personalizzato, l’app per gli Allievi non mostrerà la favicon.
* Su AEM, il componente Learning Manager elimina la configurazione di altri componenti.
* La pagina della guida per il componente AEM conduce a una posizione errata.
* Ottenimento e archiviazione esterna di e-mail utente/token in modo che gli utenti possano implementare il proprio back-end di archiviazione invece di utilizzare i nodi utente AEM.
* Quando una descrizione in testo semplice viene modificata in Corsi, Programmi di apprendimento, Certificati e Risorse formative, viene mostrato un messaggio di avviso.
* I report dalla Dashboard per i manager non vengono scaricati quando un utente ha sia un ruolo personalizzato che un ruolo manager.
* Un’e-mail di riepilogo mostra un valore errato per l’attività di formazione.
* In alcuni casi, Learning Manager ha un comportamento imprevisto quando si passa dal Marketplace dei contenuti alla Pagina dell’Allievo.
* Nell’app Social, i filtri della visualizzazione a elenco non funzionano come previsto.
* L’e-mail di benvenuto ricevuta dagli utenti interni viene ricevuta anche da utenti esterni.
* Aggiunta del widget Learning Manager nel modello di pagina in AEM.
* Impossibilità di pubblicare nuovamente un certificato dopo aver rimosso un corso.
* Gli allievi non ricevono messaggi con i dettagli di una sessione.
+++

+++Aggiornamento 67 - Aggiornamenti ad Azure

Questo aggiornamento introduce una nuova istanza di Azure.

>[!NOTE]
>
>I seguenti elementi non sono supportati:
>
>* [Dominio personalizzato](../custom-domain.md)
>* [Acquisto con carta di credito](../administrators/feature-summary/billing-management.md)
>* [Catalogo dei contenuti](../administrators/feature-summary/content-catalogs.md)

+++

+++Aggiornamento 66 - Versione di agosto 2021 di Learning Manager

La **versione di agosto 2021** di Adobe Learning Manager **è incentrata sul miglioramento dell’esperienza degli Allievi, sulla creazione di report e sui flussi di lavoro amministrativi.** Alcuni degli elementi principali includono:

* **Contenuti del marketplace:** Learning Manager offre ora più di 70000 corsi da diversi domini, ad esempio Tecnologia, Management, Leadership e così via.
* **Supporto dell&#39;accessibilità migliorato:** il supporto dell&#39;accessibilità per il ruolo di Allievo si rafforza grazie alla navigazione tramite tastiera avanzata, alla funzionalità screen reader e alla conformità al rapporto di contrasto.
* **Formattazione RTF:** Learning Manager offre ora la modifica di testo RTF per le descrizioni di corsi, programmi, certificati e risorse formative. Questo consente agli autori di specificare le descrizioni nel testo RTF, inclusi collegamenti ipertestuali, immagini e altre opzioni di formattazione del testo, in contrapposizione al testo normale.
* **Valutazione a stelle:** un Allievo può assegnare una valutazione a un corso su una scala di 5 punti. L’Amministratore può scegliere tra la valutazione dell’efficacia esistente o quella a 5 stelle.
* Integrazione con **Badgr:** gli Allievi possono ora autorizzare Learning Manager a inviare automaticamente i distintivi acquisiti in Learning Manager al proprio account Badgr, così da poterli condividere sui social network.
* **Esportazione degli eventi di apprendimento su Salesforce:** Learning Manager offre ora la possibilità di esportare alcuni eventi specifici in Learning Manager, come l’aggiunta di nuovi utenti, l’iscrizione e il completamento a un tenant Salesforce, consentendo di collegarli con l’oggetto utente o l’oggetto referente appropriato su Salesforce.

Per ulteriori informazioni, consulta [***Novità e modifiche nella versione di agosto 2021 di Learning Manager***](../whats-new.md).


**Data di pubblicazione:** 7 agosto 2021

### Bug corretti in questo aggiornamento

**Esperienza Allievo**

* Dopo aver aggiunto un allievo a due gruppi di utenti e aver aggiunto un piano di apprendimento, l’allievo è iscritto a un’istanza diversa dello stesso corso.
* In alcuni casi, dopo l’iscrizione e l’inizio del corso, il corso non viene riprodotto correttamente.
* Nella descrizione del corso sono presenti tag HTML. Questo problema ora è risolto.
* Se scrivi un commento che si estende su più righe a un post in una bacheca social, il commento appare su una singola riga. Questo problema è stato risolto.

**Authoring**

* In alcuni casi, con l’iscrizione automatica, gli allievi ricevono più e-mail di iscrizione.

**Report**

* Quando l’interfaccia è impostata su alcune lingue diverse dall’inglese, le Trascrizioni allievi non sono generate correttamente.
* Possibilità di reimpostare l’avanzamento di un corso all’interno di un programma di apprendimento e di una certificazione.
* Se un file CSV contiene campi attivi con lo stesso nome, ma con diverse maiuscole e minuscole, il file CSV produce un’eccezione.

**Altro**

* L’opzione di modifica punteggi e commenti deve essere disattivata quando non è selezionato alcun Allievo o se la presenza dell’Allievo selezionato non è contrassegnata.
* I valori nei campi attivi vengono visualizzati in minuscolo nella finestra di dialogo Modifica utente anche se un utente aveva aggiunto i valori in maiuscolo.
* Possibilità per amministratori e management di visualizzare le approvazioni in sospeso per i corsi. Ciò consente ai manager di tenere traccia dell’apprendimento e della formazione dei dipendenti e agli amministratori di Learning Manager di approvare l’iscrizione ai corsi in base alle esigenze.
* Un utente che dispone di un’autorizzazione di autore o Amministratore/autore personalizzato non può modificare una risorsa formativa creata da un altro utente.
* Dal ruolo Amministratore, quando l’utente andava su Corso > Istanza e selezionava l’opzione &quot;Allievi iscritti&quot; per qualsiasi istanza, il sistema mostrava gli allievi dell’&quot;Istanza predefinita&quot;. L’amministratore doveva modificare l’istanza manualmente dal menu a discesa. Ora Learning Manager consente di passare correttamente alla pagina Allievi con l’istanza corretta selezionata.

**App per dispositivi**

* Sui dispositivi Android e iPhone, gli Allievi non possono avviare i moduli dei corsi in modo casuale. In questi casi, viene mostrato l’errore “Error 401 unathorized”.
* Un Allievo non riesce ad acquisire più due codici QR e viene visualizzato un messaggio di errore.
* Su alcuni dispositivi Android e iOS, un file non si apre come previsto per alcuni corsi scaricati.
* Se si tenta di aprire una risorsa formativa, viene visualizzato un messaggio di errore.
* L’app per dispositivi si comporta in modo imprevisto quando un programma di apprendimento viene utilizzato offline.
* Quando un Allievo torna online e apre l’app, questa si blocca nella schermata di caricamento.
* A volte, quando un utente torna online, l’app passa alla visualizzazione classica.
* Qualche volta, quando un corso viene seguito offline, l’avanzamento non viene salvato.
* A volte, quando il nome di un corso è troppo lungo, questo non viene visualizzato come previsto sin dall’inizio.
* Nella pagina del catalogo, i corsi non vengono ordinati come previsto.
+++

+++Aggiornamento 65

Data di pubblicazione: luglio 2021

### Bug corretti in questo aggiornamento

* Problemi relativi all’accesso degli utenti.
* Il modello dell’e-mail relativa all’iscrizione al corso per Manager non visualizza la scadenza di completamento del corso se la variabile viene aggiunta al modello.
* TLS 1.0 e TLS 1.1 sono stati dichiarati obsoleti.
* Problemi relativi all’eliminazione dei dati GDPR di un utente.
+++

+++Aggiornamento 64

Data di pubblicazione: luglio 2021

### Bug corretti in questo aggiornamento

* La notifica dell’iscrizione viene inviata agli allievi già iscritti a un corso.
* Quando viene generato un certificato personalizzato come distintivo, il formato della data non è supportato in tedesco.
+++

+++Aggiornamento 63

Data di pubblicazione: giugno 2021

### Bug corretti in questo aggiornamento

* Puoi creare un utente con un nome vuoto in un file csv.
* Se nel campo attivo è presente un carattere ‘/’, dopo aver creato un processo per il download di user.csv, lo stato del processo non cambia da “Inviato” a “Completato”.
* I moduli ordinati non rispettano la sequenza.
* Quando un autore esterno viene eliminato, il corso creato dall’autore non è più disponibile.
* La ricerca di un oggetto di apprendimento con più competenze comporta risultati imprevisti.
+++

+++Aggiornamento 62

Data di pubblicazione: giugno 2021

### Bug corretti in questo aggiornamento

* Impossibile accedere all’app quando l’account effettua l’accesso a SP.
* I video non vengono visualizzati da Brightcove come previsto.
* L’API userGroupInfo non è visibile durante la visita al programma di apprendimento in nessuna delle app.
* Impossibile cercare un programma di apprendimento e una certificazione ritirati durante la creazione di un report del dashboard.
* Un autore non è in grado di modificare o aggiornare una risorsa formativa creata da un altro autore.
* L’API per l’invio dei file non funziona come previsto nel cluster UE.
+++

+++Aggiornamento 61

Data di pubblicazione: maggio 2021

### Bug corretti in questo aggiornamento

* Miglioramento delle prestazioni nelle chiamate userGroupInfo.
* Dopo aver attivato i nuovi profili Brightcove, Learning Manager supporta i contenuti con moduli video e audio.
* Le trascrizioni di apprendimento non consentono di acquisire i dati se è selezionato un intervallo di date ristretto.
* Gli allievi iscritti ricevono un invito alla sessione per tutte le altre anche quando ne viene aggiunta una nuova.
* I moduli audio non vengono caricati come previsto.
+++

+++Aggiornamento 60

Data di pubblicazione: aprile 2021

### Bug corretti in questo aggiornamento

**Segnala**

* Impossibile cercare un corso inattivo una volta creato un report.
* Gli errori di un report vengono propagati agli altri. Di conseguenza, tali rapporti hanno generato errori.

**Risorse formative**

* Impossibile eliminare una risorsa formativa dopo averla scaricata.

**Lettore**

* Le didascalie WebVTT non vengono visualizzate come previsto.

**App per gli Allievi**

* Nella pagina Panoramica certificazioni, la durata aggiunta da un autore non viene visualizzata nella certificazione esterna.
* Aggiungi l&#39;opzione **Tutti** nel filtro Abilità.
* Gli allievi ricevevano più e-mail di riepilogo.
* Il numero di righe selezionate non corrisponde a quello previsto in una pagina.

**Componente AEM**

* I widget non vengono aggiornati come previsto dopo l’aggiornamento della pagina.

**Localizzazione**

* Alcune stringhe in tedesco non sono localizzate come previsto.
* Se un Allievo non ha selezionato la lingua dell’interfaccia e del contenuto, la lingua predefinita per la traduzione delle stringhe è l’inglese.

**Certificazione**

* L’ordine del modulo può essere ignorato se i prerequisiti non vengono stabiliti.

**Browser**

* Le app per Autori, Manager o allievi non vengono visualizzate come previsto in IE 11.

**Gamification**

* I punti di Gamification non vengono riscattati come previsto.

**Libreria dei contenuti**

* I corsi per l’app di prova del contenuto non funzionano come previsto.

**Lettore**

* Il lettore viene caricato solo nello spazio in cui è presente il widget.
* I video all’interno di un modulo Captivate non vengono riprodotti come previsto.

**Connettore**

* In alcuni casi, i file vengono eliminati da un connettore FTP/Box.
* I file vengono eliminati da ftp se vengono aggiornati con gli stessi nomi.
* Un evento BlueJeans supporta la paginazione nel caso in cui il numero di eventi è maggiore di 100.

**Aggiornamento app per dispositivi mobili 3.3 - Marzo 2021**

Data di pubblicazione: 26 marzo 2021

### Novità e modifiche {#whatsnewandchanged}

L’aggiornamento 3.3 dell’app mobile Captivate Learning Manager introduce una nuovissima home page, che supporta i masthead e i consigli di formazione basati sull’intelligenza artificiale. Questa home page è disponibile per tutti gli account configurati per la nuova opzione Layout immersivo. Gli account configurati con Layout classico continuano a visualizzare la home page classica/precedente. senza alcun cambiamento.

Inoltre, questo aggiornamento consente agli Allievi di scaricare il proprio badge come PDF e un’immagine. L’aggiornamento introduce anche una finestra a comparsa dedicata al feedback, che consente agli Allievi di fornire un feedback sull’app in modo anonimo.

Per ulteriori informazioni, consulta [App per dispositivi Learning Manager](../learners/feature-summary/ipad-android-tablet-users.md).

Per saperne di più, continua a leggere.

#### Nuova home page

Per tutti gli account in cui è attivata l’opzione Layout immersivo, è disponibile una nuova home page in grado di supportare la configurazione di Layout immersivo.

#### Valutazione feedback

In questa versione, Learning Manager chiede all’utente di fornire un feedback sulla propria esperienza con l’app mobile.

#### Scarica badge

Questo aggiornamento consente agli Allievi di scaricare i propri badge in formato PDF e immagine.

<!--## Previous update releases {#previousupdatereleases}-->
+++

+++Aggiornamento 60 - Versione di febbraio 2021 di Learning Manager

Data di pubblicazione: 20 febbraio 2021

### Novità e modifiche {#Whatsnewandchanged-1}

* Visualizzazione della bacheca nel social.
* Personalizzazione del banner social.
* Filtri catalogo nell’app per allievi.
* Annullamento dell’iscrizione dal corso di formazione.
* Importazione degli utenti dai contatti Salesforce.
* ...e molto altro.

Per ulteriori informazioni, consulta Novità dell’[aggiornamento di febbraio 2021 di Learning Manager](../whats-new.md).

### Bug corretti in questo aggiornamento {#bug-fixes}

**Certificazione**

* In alcuni casi, gli Allievi non riuscivano a seguire di nuovo uno dei corsi previsti da una certificazione, anche se il numero massimo di tentativi era impostato su infinito. Questo problema è stato risolto.
* In alcuni casi, gli Allievi non riuscivano a iscriversi a una certificazione perché il pulsante **Iscrizione** non era visibile come previsto.

**Libreria dei contenuti**

* L’URL della Guida sulla pagina **Aggiungi nuovo contenuto** era errato ed è stato aggiornato con quello corretto.

**Corso**

* Un report relativo al punteggio di un quiz L2 scaricato per un modulo di contenuti AICC mostrava un punteggio errato nella colonna Totale punteggio utente/punteggio quiz. Questo problema è stato risolto.
* Se l’Allievo non aveva accesso al corso originale da cui poteva essere creato uno uguale, non poteva scaricare le risorse dal corso duplicato.
* Le immagini del banner non venivano eliminate quando l’autore le rimuoveva mentre il corso era in stato Bozza. Questo problema è stato risolto.

**AEM**

* Dopo aver inserito il componente Learning Manager in AEM, il caricamento della pagina richiedeva molto tempo impedendo l’accesso agli altri componenti. Questo problema è stato risolto.

**Amministrazione**

* I corsi ritirati non venivano visualizzati nei risultati della ricerca come previsto. Questo problema è stato risolto.
* L’Amministratore non è stato in grado di cercare i corsi ritirati in **App per amministratori** -> **Report personalizzati** -> **Report Excel** -> **Report corso**. Questo problema è stato risolto.

* Il download di un report relativo a un quiz in formato excel non funzionava se il file conteneva gli allievi che avevano seguito i corsi prima e dopo l’aggiornamento dei contenuti. Questo problema è stato risolto.
* Il caricamento di un file CSV non riesce se i campi attivi contengono caratteri speciali. Questo problema è stato risolto.
* In alcuni casi, quando gli allievi sostenevano un quiz creato in Captivate, le risposte non venivano acquisite nel modo previsto.
* Dopo aver creato un abbonamento e aver tentato di modificarlo, i pulsanti **Salva** e **Annulla** non vengono visualizzati come previsto. Questo problema è stato risolto.

**Lettore**

* Per un tipo specifico di contenuto SCORM-2004, lo scenario di ripresa non funzionava. Di conseguenza, gli Allievi dovevano procedere manualmente fino al punto in cui si erano fermati. Questo problema è stato risolto. Il contenuto ora può essere ripreso dal punto in cui viene bloccato.
* In alcuni casi, dopo l’iscrizione a un corso, il contenuto non veniva riprodotto come previsto. Questo problema è stato risolto.

**Annullamento iscrizione**

* Un report di iscrizione elencava solo 20 registrazioni annullate anche se il numero di allievi che avevano annullato l’iscrizione al corso o alla certificazione era maggiore. Questo problema è stato risolto.
* In alcuni casi, si verificava un problema durante l’esportazione dell’elenco di iscrizioni annullate nel relativo report. Questo problema è stato risolto.

**Programma di apprendimento**

* Per un piano di apprendimento flessibile, se un Allievo era iscritto a una sola istanza del corso e faceva clic sul link degli altri corsi di cui non aveva selezionato le istanze, visualizzava una pagina vuota.

**Allievo**

* Alcuni allievi, i cui nomi utente avevano caratteri speciali, non ricevevano notifiche e-mail come previsto.
* Nella vista immersiva, in alcuni casi il widget Calendario non visualizzava le sessioni in aula virtuale come previsto.
* Nell’app per Allievi, il filtro **Abilità** non funzionava come previsto. Questo problema è stato risolto.

**Cerca**

* In uno scenario specifico, il Manager non era in grado di cercare il gruppo di utenti di un Manager in precedenza. Questo problema è stato risolto per il ruolo Manager.

**Gruppo utenti**

* Durante l’esportazione di un report relativo a un gruppo con più di 500 utenti, i valori dei dati e le intestazioni delle colonne presenti in tale report non corrispondevano. Questo problema è stato risolto.
* Quando l’Amministratore modificava la firma in calce all’e-mail in Modelli e-mail e aggiungeva più righe, visualizzava i tag html solo nell’interfaccia Amministratore. Questo problema è stato risolto.
* Nell&#39;**App per amministratori > Catalogo > Cerca catalogo** non è possibile effettuare ricerche.

**Utenti**

* Alcuni utenti esterni attivi venivano eliminati. Sono state apportate alcune modifiche e il problema è stato risolto.

**Importa**

* L’importazione di un file CSV non andava a buon fine se la relativa intestazione conteneva spazi finali o l’e-mail di un utente conteneva accenti o caratteri diacritici.

**Invio attività**

* Nella pagina per inviare le attività dell’app per istruttori, la data di invio si sovrapponeva al nome del file se tale nome conteneva molti caratteri. Questo problema dell’interfaccia utente è stato risolto.

**Istruttore**

* Un Istruttore riceve inviti per tutte le sessioni anche se ne viene aggiunta solo una nuova. Questo problema è stato risolto.

**SCORM**

* Alcuni contenuti SCORM presentavano dei problemi relativi al browser e alla navigazione nel lettore, nonché delle incongruenze nella registrazione dei punteggi dei quiz. Questi problemi sono stati risolti.

**SAML e SSO**

* È stato aggiornato il messaggio di errore visualizzato alla scadenza delle credenziali SSO.

**API di Learning Manager**

* L’API getlearningObject restituiva dati di registrazione errati a causa di problemi di memorizzazione nella cache. Questo problema è stato risolto.
* Una sessione in aula virtuale ora visualizza l’URL della riunione nel campo Posizione dell’invito.
* Se erano state configurate più integrazioni per il provider di aule virtuali e se una di esse non funzionava come previsto, il menu a tendina di selezione del provider visualizzava un elenco vuoto. Questo problema è stato risolto. Le integrazioni rimanenti per aule virtuali ora vengono elencate correttamente.
* I modelli di aula virtuale Connect non venivano caricati come previsto quando un Istruttore entrava nella sessione.
* Una durata non corretta veniva visualizzata nell’interfaccia utente dopo la migrazione di moduli con durata nel file CSV versione_modulo.
* In alcuni account, l’aggiornamento di un utente non funzionava come previsto. Questo problema è stato risolto.

### Problemi noti in questo aggiornamento {#known-issues}

* Quando un Allievo utilizzava il filtro **Durata** nell’app per allievi, il contenuto e il filtro risultavano non sincronizzati se aveva attivato altre impostazioni locali per il contenuto e non faceva parte dell’istanza predefinita in termini di iscrizione.

>[!NOTE]
>
>I filtri &#39;**Durata**&#39; e &#39;**Formato**&#39; del corso di formazione sono identificati in base al contenuto del corso di formazione disponibile per l&#39;istanza predefinita e per le impostazioni locali preferite dell&#39;account.

+++

+++Aggiornamento 59

## Aggiornamento 59

Data di pubblicazione: 18 dicembre 2020

### Connettore evento BlueJeans {#bluejeanseventconnector}

Il connettore BlueJeans Events collega i sistemi Learning Manager e BlueJeans per automatizzare la sincronizzazione dei dati. Utilizzando questo connettore, è possibile:

* **Configurare le sessioni virtuali utilizzando BlueJeans Events:** Configurare un nuovo evento in BlueJeans e una sessione VC in Learning Manager selezionando l’evento BlueJeans più appropriato. I dettagli relativi a data e ora vengono selezionati automaticamente dagli eventi BlueJeans.
* **Sincronizzazione automatizzata completamento utente:** Un processo di sincronizzazione automatizzato di completamento dell’utente consente all’Amministratore Learning Manager di recuperare automaticamente i record di completamento per gli eventi BlueJeans.

Per configurare questo nuovo connettore sono necessarie delle credenziali diverse.

Per ulteriori informazioni, consulta [***connettore evento BlueJeans***](../integration-admin/feature-summary/connectors.md#bj-events).

+++

+++Aggiornamento 58 - Versione di dicembre 2020 di Learning Manager

## Aggiornamento 58 - Versione di dicembre 2020 di Learning Manager

Data di pubblicazione: 05 dicembre 2020

### Novità e modifiche {#Whatsnewandchanged-2}

Questa versione è incentrata sui seguenti aspetti:

* Nuovissima esperienza della pagina principale dell’Allievo
* Layout reattivo per il Web mobile del ruolo di Allievo
* Consiglio per gli Allievi basato sull’intelligenza artificiale
* E-mail di riepilogo settimanali
* Elenco di controllo
* Integrazione di Marketo Engage
* Dominio personalizzato
* Importazione dei punteggi dei quiz da Adobe Connect
* Deep link al catalogo per gli allievi
* Miglioramenti a LinkedIn Learning
* ...e molto altro

Per ulteriori informazioni, consulta [***Novità della versione di dicembre 2020 di Adobe Learning Manager***](../whats-new.md).

### Funzionalità non supportate nell’esperienza mobile immersiva {#unsupportedfeaturesinmobileimmersiveexperience}

Le seguenti funzionalità non sono supportate:

* App Social: un Allievo viene reindirizzato all’esperienza classica se fa clic sul widget Social nella pagina principale
* Impostazioni profilo/Modifica profilo
* Visualizza distintivo/competenze
* Classifica: un Allievo viene reindirizzato all’esperienza classica se fa clic sul widget Classifica nella pagina principale
* Download delle risorse formative in corso.
* Opzioni filtro in Cerca.

### Bug corretti in questo aggiornamento {#bug-fixes-1}

* Non è possibile eliminare una cartella dei contenuti se questa presenta contenuti eliminati.
* Il Piano di apprendimento consente agli Amministratori di impostare un corso con istanza automatica. Per un corso con modulo di invio delle attività, le informazioni dell’Istruttore non erano configurate correttamente in precedenza. Learning Manager ora assegna automaticamente l’Istruttore dall’istanza predefinita a questa istanza automatica.
* Un badge personalizzato con un’etichetta di catalogo con uno spazio non consente il download del PDF come previsto.
* Un report scaricato dal dashboard è diverso dall’e-mail di iscrizione ricevuta per il report del dashboard.
* Una Trascrizione Allievo non dispone di dati aggiornati per una certificazione ricorrente.
* Dopo aver avviato un corso, se lo si lascia scadere, il numero di tentativi non viene visualizzato come previsto. A volte, quando si tenta di accedere a un corso più volte, viene visualizzata una schermata vuota.
* Si è verificato l’Errore 5xx dopo il caricamento di un modulo.
* Una bacheca social privata non è visibile a tutti gli allievi.

### Problemi noti in questo aggiornamento {#known-issues-1}

Al termine di un corso o di una certificazione, non viene visualizzata immediatamente la finestra di feedback. Questo problema si verifica solo quando si segue il corso nell’interfaccia utente immersiva. Se si segue il corso nell’interfaccia utente classica, viene visualizzata la finestra di feedback come previsto.

+++

+++Aggiornamento 57

## Aggiornamento 57

Data di pubblicazione: 23 settembre 2020

**Libreria dei contenuti**

* Nella libreria dei contenuti, il ritiro di un contenuto non comporta la rimozione del contenuto nella scheda **Pubblicato**. Quando si aggiorna la pagina, il contenuto ritirato non viene più visualizzato.
* Quando si crea una cartella di contenuto, il campo **Nome** non è contrassegnato come obbligatorio, in realtà è obbligatorio.

**Richiesta del cliente**

* Per identificare tutti i corsi a cui è iscritto ciascun Allievo e se l’ha completato, includi i seguenti campi nel dashboard, Report di iscrizione:

   * UUID
   * Indirizzo e-mail

**Trascrizione Allievo**

* La generazione di una Trascrizione Allievo nelle impostazioni internazionali indonesiane ha generato errori.

**Cerca**

* Non è possibile cercare un corso specifico. Questo problema è stato risolto.

+++

+++Aggiornamento 56 - App mobile

Data di pubblicazione: 25 agosto 2020

### Segui corsi da LinkedIn Learning {#takecoursesfromlinkedinlearning}

Learning Manager supporta già i corsi di LinkedIn Learning all’interno della piattaforma di apprendimento. Ora gli Allievi possono seguire i corsi di LinkedIn Learning nell’app mobile Learning Manager. Nell’app per dispositivi, cerca un corso e poi avvialo.

Per ulteriori informazioni, vedi Segui corsi da [***LinkedIn Learning***](../learners/feature-summary/ipad-android-tablet-users.md#linkedin).

### Notifica push per le iscrizioni amministratore {#pushnotificationforadminenrollments}

Quando l’amministratore iscrive gli allievi ai corsi di formazione, gli allievi ricevono le notifiche relative alle iscrizioni.

La notifica push è ora supportata anche per gli annunci.

### Feedback L1 obbligatorio {#mandatoryl1feedback}

Nell’ultima versione di agosto 2020, Learning Manager consente agli amministratori di configurare il feedback L1 in modo che tutte le domande diventino obbligatorie. La stessa funzione è ora supportata per gli Allievi nell’app mobile.

### Miglioramenti all’interfaccia utente {#userinterfaceenhancements}

**Collegamenti a piè di pagina**

L’amministratore può impostare più collegamenti a piè di pagina nella vista Amministratore sul Web. Gli allievi possono ora accedere a questi collegamenti toccando le icone Hamburger e Aiuto.

Per impostazione predefinita, sono disponibili due collegamenti e l’amministratore ha la possibilità di aggiungerne altri tre (tramite la vista Amministratore sul Web) che saranno visualizzati nell’app.

**Vista a schede per gli oggetti di apprendimento**

Per impostazione predefinita, nelle sezioni dell’app Il mio apprendimento e Catalogo, i corsi di formazione sono visualizzati come schede anziché come elenchi. Si tratta di una modifica per gli Allievi, poiché in precedenza la visualizzazione predefinita era &quot;Visualizzazione elenco&quot;.

Gli allievi possono, tuttavia, alternare la visualizzazione tra quella a elenco e quella a schede.

+++

+++Aggiornamento 55 - Versione di agosto 2020 di Learning Manager

Data di pubblicazione: 23 agosto 2020

### Novità e modifiche {#Whatsnewandchanged-3}

Questa versione è incentrata sui seguenti aspetti:

* Miglioramenti ai report
* Cartelle dei contenuti private
* FTP personalizzato
* Supporto per sottotitoli per video
* Miglioramenti all’applicazione Power BI
* Ottimizzazione dei feedback
* API nuove e modificate
* Modifiche ai criteri di conservazione dei dati
* ...e molto altro

Per ulteriori informazioni, consulta [***Novità della versione di agosto 2020 di Adobe Learning Manager***](../whats-new.md).

### Note su questa versione {#notes}

* La generazione di una Trascrizione Allievo (~1 GB) richiede meno di 15 minuti.
* Nelle versioni precedenti di Learning Manager, le colonne Punteggio quiz e Punteggio quiz più alto della Trascrizione Allievo fornivano il punteggio e il punteggio massimo nel formato 25/100. Per migliorarne la leggibilità e l’analisi, il punteggio del quiz ora viene esportato anche nelle colonne separate **Punteggio_quiz, Punteggio_massimo_quiz, Punteggio_quiz_più_alto e Punteggio_massimo_quiz_più_alto**. Queste consentono agli Amministratori di effettuare rapidamente calcoli e analisi.

### Bug corretti in questo aggiornamento {#bug-fixes-2}

**Connettore**

* Lo studente non può partecipare contemporaneamente a due riunioni diverse create da autori diversi.
* Facendo clic sull’opzione Gestisci connessioni dalla scheda Adobe Connect si passa alla pagina della connessione FTP.
* Una sincronizzazione FTP pianificata viene chiusa con un’eccezione.
* Problemi relativi alla password durante la connessione a Exavault.

**Corso**

* È possibile creare un modulo di Classe virtuale senza selezionare alcun sistema per conferenze. Di conseguenza, il processo di creazione di un corso genera l’errore 500.
* Nonostante sia iscritto al corso, lo studente non è in grado di scaricare le risorse di un corso duplicato.
* Visualizzando l’anteprima di un corso come studente, un amministratore o autore non è in grado di scaricare risorse a meno che non sia iscritto al corso.

**App per dispositivi**

* In casi specifici di iscrizione, il diagramma a torta nella sezione Apprendimento in sospeso dell’app per allievi mostra valori diversi tra la visualizzazione su browser e quella su dispositivi mobili.

**Certificazione**

* Il filtro Stato non funziona come previsto quando si tenta di scaricare un report del dashboard per la certificazione.

**Cerca**

* Nella pagina Catalogo dell’Allievo, quando si tenta di cercare un corso in base alla relativa nota, non viene visualizzato alcun risultato di ricerca.

**SCORM**

* Per alcuni contenuti, il lettore SCORM mostra una schermata vuota.
* Un contenuto Storyline viene identificato come contenuto Captivate se il progetto Storyline pubblicato contiene un oggetto Web che punta all’output di Captivate pubblicato.
* Non è possibile avviare il contenuto SCORM a causa di un URL non corretto.

**Ruolo personalizzato**

* Per certi scenari, un amministratore personalizzato non è in grado di visualizzare l’elenco completo degli Oggetti di apprendimento.
* Un amministratore personalizzato non è in grado di cercare un Programma di apprendimento né una Certificazione nei report del dashboard.
* Un amministratore personalizzato non è in grado di cercare un manager in una dashboard.
* Le Trascrizioni allievi generate da un amministratore personalizzato non contengono i dati degli utenti eliminati.
* Un autore personalizzato o un amministratore personalizzato non è in grado di duplicare un Programma di apprendimento, un corso né una certificazione.

**Report**

* Se lo studente non è iscritto alla certificazione, la colonna Tipo in una Trascrizione Allievo mostra il valore come corso per quei corsi che sono parte di una certificazione.

**Abilità**

* Durante l’aggiunta di un’abilità per un corso, si presentano alcuni problemi nella ricerca di un’abilità.

**Gamification**

* Se molti utenti sono impostati come riservati, facendo clic sulla scheda dell’Allievo riservato su Edge e Internet Example, il browser risponde in modo imprevisto.
* Quando si modifica la frequenza di un criterio, i punti calcolati con la frequenza precedente vengono aggiunti al calcolo corrente.

**Amministratore**

* Se viene modificata l’istanza del corso mappata a un Programma di apprendimento, non è possibile contrassegnare lo stato Partecipazione avvenuta per gli allievi.

**Modelli e-mail**

* Per i Programmi di apprendimento e le Certificazioni, manca il pulsante di attivazione/disattivazione nel modello e-mail.

**Libreria dei contenuti**

* I contenuti SCORM non vengono avviati come previsto a causa di un URL errato.

**Trascrizioni allievi**

* Quando si generano le Trascrizioni allievi, se nella casella di immissione Seleziona allievi si aggiunge un allievo eliminato e si abilita l’opzione “Includi i dati degli allievi eliminati” in Avanzate, la pagina risponde in modo imprevisto.

**Cerca**

* Non è possibile cercare un corso utilizzando le relative note.

**Report Excel**

* Se il download di un report di prova di verifica dell’utente richiede più di un’ora a causa di una grande quantità di dati o per un’elaborazione lenta, la connessione si interrompe e il report non viene scaricato.
* Se lo studente non è iscritto alla certificazione, in una Trascrizione Allievo la colonna Tipo viene visualizzata come “Corso” anziché come “Certificazione” per quei corsi che sono parte della certificazione.

**App per gli Allievi**

* Un Allievo può seguire un corso ordinato in modo non ordinato accedendo ai corsi tramite un’e-mail o una notifica di annullamento dell’iscrizione.
* Lo studente non riceve le e-mail dei promemoria di sessione come previsto.
* Un corso non viene avviato come previsto se manca un determinato modulo.

**Annunci**

* Se un annuncio contiene il tag `<a>`, l&#39;annuncio non viene creato come previsto.

**Account**

* In alcuni casi, gli account vengono disattivati anche se dispongono di un ordine di acquisto valido.

**API**

* Facendo clic su Gestisci connessioni dalla scheda Adobe Connect, si viene reindirizzati alla pagina Connessione FTP.
* L’amministratore di Connect riceve avvisi sbagliati per alcuni scenari.
* La migrazione a LinkedIn Learning genera alcuni errori.

### Problemi noti in questo aggiornamento {#known-issues-2}

**Report dashboard**

* Quando si elimina un Programma di apprendimento o una Certificazione, nel report dei Corsi di formazione attivi vengono visualizzati i corsi presenti all’interno del Programma di apprendimento o della Certificazione nonostante non risulti alcuna iscrizione.

+++

+++Aggiornamento 54 - App mobile

## Aggiornamento 54 - App mobile

Data di pubblicazione: 16 aprile 2020

Per ottenere le funzionalità e gli aggiornamenti più recenti e un’esperienza migliore, si consiglia di aggiornare l’app per dispositivi alla versione più recente. L’aggiornamento è **obbligatorio**.

### Funzioni nuove e migliorate {#newandenhancedfeatures}

Un amministratore può comunicare informazioni importanti a tutti gli utenti dell’app. Gli annunci possono essere realizzati tramite un video, un’immagine o un semplice messaggio di testo. Questa versione dell’app per dispositivi supporta gli annunci nell’app. Un nuovo annuncio verrà visualizzato all’avvio dell’app, in modo che gli Allievi non perdano alcuna comunicazione importante inviata dagli Amministratori. Gli allievi potranno leggerli subito o successivamente nella scheda **Annunci**.

I nuovi annunci sono disponibili nella sezione **Annunci**.

Per visualizzare un annuncio, tocca **Annunci**. L’annuncio più recente viene visualizzato sullo schermo.

Per visualizzare l’annuncio successivo, tocca **Scorri a sinistra per visualizzare successivo**.

### Annunci {#announcements}

![](assets/read-later.png)

Se non desideri leggere subito l’annuncio puoi leggerlo in un secondo momento. Tocca **Leggi in seguito** sull’annuncio: lo stato dell’annuncio torna ad essere “non letto”.

### Bug corretti in questo aggiornamento {#bugsfixedinthisupdate}

* In iOS, la riproduzione di podcast si interrompe quando lo schermo viene bloccato. Il problema è stato risolto e l’audio viene riprodotto anche quando lo schermo è bloccato.
* Se segui un corso nell’app per dispositivi, la diapositiva dei risultati potrebbe apparire vuota. Questo problema è stato risolto in questo aggiornamento.

+++

+++Aggiornamento 53 - Versione di aprile 2020 di Learning Manager

Data di pubblicazione: 04 aprile 2020

La versione di aprile 2020 di Learning Manager si è concentrata sui seguenti punti:

* [Ottimizzazione delle prestazioni](../whats-new.md#performance)
* [Formazione in classe](../whats-new.md#classroom)
* [Flussi di lavoro Manager](../whats-new.md#manager)
* [Apprendimento sociale](../whats-new.md#social)
* [Report](../whats-new.md#reporting)
* [Esperienza di apprendimento](../whats-new.md#learner)
* [Modifiche a livello di API](../whats-new.md#api)

Per ulteriori informazioni, consulta [***Novità della versione di aprile 2020 di Learning Manager***](../whats-new.md).

+++

+++Aggiornamento 52 - App mobile

## Aggiornamento 52 - App mobile

Data di pubblicazione: 20 dicembre 2019

### Funzioni nuove e migliorate {#Newandenhancedfeatures-1}

#### Logo del marchio aziendale {#companybrandinglogo}

L’app ora è in grado di mostrare il nome del marchio, il logo del marchio o entrambi nell’app del dispositivo, a seconda delle impostazioni selezionate dall’Amministratore.

#### Collegamenti diretti {#deeplinks}

Learning Manager avvia l’app del dispositivo non appena fai clic su un collegamento/URL supportato da Learning Manager. Se l’app non è installata nel dispositivo, l’URL viene aperto nel browser.

Di seguito sono riportati alcuni esempi di utilizzo supportati in questo aggiornamento.

* Fai clic su un URL di formazione ricevuto tramite e-mail.
* URL di formazione predefiniti contenuti nei modelli di e-mail.
* URL dell’account contenuto nei modelli di e-mail.
* URL di accesso a Il mio apprendimento e Catalogo.

Inoltre, qualsiasi URL con dominio *learningmanager.adobe.com* viene aperto nell’app del dispositivo.

#### Carica le risorse nel certificato esterno come prova di completamento {#uploadassetsinexternalcertificateasproofofcompletion}

In questo aggiornamento, un Allievo può caricare risorse come prova di completamento per un certificato esterno.

Un Allievo può aprire un certificato esterno e caricare risorse quali file PDF, di testo o di immagine.

Per ulteriori informazioni, consulta [***Caricamento di risorse in un certificato esterno***](../learners/feature-summary/ipad-android-tablet-users.md#externalcert).**&#x200B;**

### Problemi risolti in questa versione {#issuesfixedinthisrelease}

* L’utente non è in grado di accedere all’app del dispositivo se l’e-mail contiene caratteri speciali.
* Durante lo scorrimento, l’icona dell’oggetto di apprendimento lampeggia quando si è in una visualizzazione a elenco.
* Ora puoi visualizzare tutte le notifiche push senza toccare il pulsante freccia giù e visualizzare i messaggi uno alla volta.
* Quando fai clic su una notifica per un post che è stato accettato o rifiutato in cura, viene aperta una pagina vuota nell’app. In questo aggiornamento viene aperta la pagina della bacheca.

+++

+++Aggiornamento 51

In questo aggiornamento, puoi anche modificare l’immagine del banner per un oggetto di apprendimento.

Puoi anche personalizzare il banner in una pagina di apprendimento per social network.

## Aggiornamento 51

Data di pubblicazione: 17 dicembre 2019

### Funzioni nuove e migliorate {#Newandenhancedfeatures-2}

### Piani di apprendimento con ambito di validità per ruoli configurabili {#learningplansscopedbyconfigurableroles}

È possibile creare ruoli personalizzati per piani di apprendimento che consentono di definire l’ambito degli utenti e degli oggetti di apprendimento. In altre parole, i piani di apprendimento possono essere creati con un ambito limitato derivato dall’ambito di un ruolo dell’Amministratore personalizzato.

A questo punto, un Amministratore può definire o limitare l’ambito, garantendo allo stesso tempo l’accesso alla gestione del piano di apprendimento.

Per ulteriori informazioni, consulta [***Piani di apprendimento con ambito di validità per ruoli configurabili***](../administrators/feature-summary/custom-role.md#scopeconfigure).

### Limitazione dei campi attivi nei report {#restrictactivefieldsinreports}

Per i campi attivi, sono state aggiunte due nuove opzioni: **Riportabile** ed **Esportabile**.

Per i campi CSV e i campi aggiunti manualmente, se un campo attivo è contrassegnato come **Riportabile**, esso diventa ricercabile in un filtro all’interno di un report del dashboard.

Per ulteriori informazioni, consulta [***Limitazione dei campi attivi nei report***](../administrators/feature-summary/add-users-user-groups.md#restrictactivefields)***.***

### Visualizzazione della descrizione del modulo dei contenuti {#viewdescriptionofcontentmodule}

In qualità di Autore, puoi visualizzare la descrizione dei moduli mentre li aggiungi a un corso.

Durante la creazione di un modulo, aggiungine la relativa descrizione. Per ulteriori informazioni sulla creazione di un corso, consulta [***Creazione di un corso***](../authors/feature-summary/courses.md).

### Visualizzazione dei nomi dei corsi e delle sessioni {#displaycourseandsessionnames}

In qualità di Istruttore, puoi visualizzare i nomi delle sessioni e dei corsi nella vista Partecipazione. Puoi tenere traccia delle sessioni in corso di modifica.

### Annuncio per gli allievi {#announcementforlearners}

Gli allievi ora possono visualizzare gli annunci in visualizzazione completa anziché in visualizzazione elenco. Questo accade quando l’Allievo ha un annuncio non letto. Questo migliora l’esperienza degli allievi nella visualizzazione dell’annuncio.

Adobe Learning Manager ora ti consente di personalizzare il tuo account per offrire un’esperienza più ricca ai tuoi utenti. Ecco un elenco di elementi che è possibile personalizzare. Per apportare queste modifiche, contatta l’[assistenza di Learning Manager](mailto:learningmanagersupport@adobe.com).

* Colori delle schede di formazione.
* Icona di avanzamento
* Immagine puntatore del mouse
* Font

Per ulteriori informazioni, consulta [***Personalizzazione dell’account***](../administrators/feature-summary/themes.md#customize).

### Caricamento di immagini banner {#uploadbannerimages}

In questo aggiornamento, puoi anche modificare l’immagine del banner per un oggetto di apprendimento.

Puoi anche personalizzare il banner in una pagina di apprendimento per social network.

### Supporto API {#apisupport}

Questo aggiornamento di Learning Manager include API per le seguenti operazioni:

**Scarica PDF badge**

Questo aggiornamento include l’API per Allievi che consente di scaricare un PDF di un badge.

**Scarica trascrizione Allievo**

Questo aggiornamento include l’API per Allievi che consente di scaricare le trascrizioni degli Allievi.

**Scarica report del quiz**

Questo aggiornamento include l’API per Amministratori che consente di scaricare i report dei quiz.

**Gamification impaginata**

L’API per Allievi ora consente di recuperare tutti gli Allievi e i punti di gamification nell’ambito dell’Allievo. In questo modo è possibile creare una classifica di gamification.

**API:** `GET /users`

**Richiesta:** `GET\\ users?page[offset]=0&page[limit]=10&sort=id&filter=gamification`

**Risposta:** *La risposta conterrà gli utenti ordinati in base ai punti di gamification.*

**Non disturbare**

Attualmente solo gli Amministratori possono aggiungere utenti a un elenco Non disturbare tramite l’interfaccia utente. Dopo questa versione, un Allievo sarà in grado di impostare autonomamente queste autorizzazioni tramite API, a condizione che questa API sia abilitata dall’Amministratore. L’abilitazione di questa API per un account richiede un’impostazione backend. Questa API consente all’Allievo di modificare le autorizzazioni riportate di seguito relative alle e-mail.

* Indirizzamento di e-mail agli allievi
* Escalation di e-mail ai Manager degli allievi
* Informazioni sui report diretti
* Informazioni sui report salta livello

Per ulteriori informazioni sulle API di Learning Manager, consulta la pagina seguente:

* [***Riferimento API***] (<https://learningmanager.adobe.com/docs/Learning> Managerapi/v2/)
* [***Guida per sviluppatori API***] (<https://helpx.adobe.com/captivate-Learning> Manager/integration-admin/feature-summary/developer-manual.html)

### Problemi risolti in questa versione {#Issuesfixedinthisrelease-1}

* Solo gli utenti appartenenti a un gruppo di utenti specifico devono ricevere annunci che sono destinati a loro. Gli altri utenti non devono ricevere gli annunci.
* Il lettore visualizza una rotellina di caricamento prima della visualizzazione del contenuto.
* I metadati utente nei report causano un’eccezione Puntatore Null.
* Dopo avere aggiunto un Istruttore per un’istanza predefinita per il corso di videoconferenza Connect, il messaggio *“Nessuna sessione per questo modulo”* viene visualizzato nella pagina Istanza del corso nell’app Amministratore.

* L’esportazione di una trascrizione dell’Allievo determina un comportamento imprevisto durante un trasferimento FTP.
* Il nome di un Autore non viene visualizzato correttamente nei corsi di un programma di apprendimento.
* Le modifiche apportate alla terminologia di prodotto delle risorse formative non sono conformi alle aspettative.
* Il nome di un modulo viene troncato se il nome è lungo e viene visualizzato in modalità verticale mobile.
* Impossibile creare un’istanza per un corso Connect precedente dopo avere aggiornato l’istanza predefinita con l’implementazione Connect precedente.
* Un Istruttore riceve un invito di calendario anche prima della pubblicazione del corso.

+++

+++Aggiornamento 50

## Aggiornamento 50

Data di pubblicazione: 24 ottobre 2019

### Funzioni nuove e migliorate {#Newandenhancedfeatures-3}

#### Creazione di un ruolo personalizzato con più ambiti di catalogo {#createcustomrolewithmultiplecatalogscopes}

In qualità di Amministratore, puoi limitare un ruolo personalizzato in base ai cataloghi e ai gruppi di utenti. Tutti gli utenti che appartengono a tali ruoli possono visualizzare solo gli oggetti di apprendimento dal catalogo nel loro ambito. Questi utenti possono eseguire solo azioni definite nell’ambito dei rispettivi gruppi di utenti.

Fino ad ora, in Learning Manager un ruolo personalizzato poteva essere assegnato a più cataloghi per un singolo gruppo di utenti con autorizzazioni complete.

In questo aggiornamento di Learning Manager puoi creare un ruolo personalizzato con un’area di validità di più cataloghi e fare in modo che vengano assegnate autorizzazioni diverse per ogni catalogo. Per ulteriori informazioni, consulta [***Assegnazione di un ruolo personalizzato a più cataloghi***](../administrators/feature-summary/custom-role.md#multi-scope).

### Miglioramenti alla ricerca {#enhancementstosearch}

**Piano di apprendimento**

Nella pagina Piani di apprendimento per Amministratori e Autori è ora disponibile una barra di ricerca che consente di cercare in qualsiasi piano di apprendimento.

![](assets/search-for-as-learningplan.png)

**App per Amministratori e Autori**

In questo aggiornamento di Learning Manager, in qualità di Amministratore o Autore, oltre a eseguire una ricerca con completamento automatico, puoi eseguire la ricerca libera in qualsiasi oggetto di apprendimento.

### Il filtro di ricerca viene mantenuto {#searchfilterispreserved}

Questo vale solo per un profilo Allievo.

Nelle pagine **Catalogo** e **Il mio apprendimento**, un Allievo può applicare un filtro nel pannello a sinistra, ad esempio **Corsi** o **Programmi di apprendimento**, quindi fare clic su un elemento Corso o Catalogo.

![](assets/choose-learning-objects.png)

Quando l’Allievo ritorna alle pagine **Catalogo** o **Il mio apprendimento** con il pulsante Indietro del browser, il filtro rimane inalterato. Il filtro applicato in precedenza dall’Allievo non viene più ripristinato.

### Controllo della visibilità dei filtri di ricerca {#controlvisibilityofsearchfilters}

Nelle versioni precedenti di Learning Manager, gli Amministratori non avevano il controllo sulle opzioni di visibilità di un filtro catalogo, pertanto gli allievi non vedono le abilità e i tag. In questa versione di Learning Manager, l’Amministratore può filtrare tipi, abilità e tag di un catalogo.

Nella pagina **Impostazioni**, per la categoria Mostra pannelli filtri, quando fai clic su **[!UICONTROL Modifica]**, sono disponibili le seguenti opzioni. Le opzioni determinano i pannelli di filtro visibili agli allievi, in modo che essi possano perfezionare i risultati della ricerca.

Per ulteriori informazioni, consulta [***Mostra pannelli filtri***](../administrators/feature-summary/settings.md#filter-panels).

### Scaricare il codice QR dall’app Amministratore {#downloadqrcodefromadministratorapp}

Negli aggiornamenti precedenti di Learning Manager, un Amministratore personalizzato riscontrava problemi durante il download di un codice QR. In questo aggiornamento, un Amministratore personalizzato che ha avuto accesso a **Tutti gli allievi** e ha l’autorizzazione per **l’iscrizione al corso** può scaricare il codice QR.

Il codice QR non è ancora disponibile per gli utenti di ruoli personalizzati nel caso in cui dispongano di autorizzazioni per ambiti limitati degli utenti.

### Aggiunta di commenti durante l’iscrizione degli allievi {#addcommentswhileenrollinglearners}

In qualità di Amministratore o Manager, puoi aggiungere commenti durante l’iscrizione di allievi a un corso. Puoi aggiungere ulteriori informazioni sulla coorte di utenti che vengono iscritti. Questi dati vengono esportati nei report sui corsi.

Per ulteriori informazioni, consulta [***Aggiunta di commenti durante l’iscrizione degli allievi***](../administrators/feature-summary/courses.md#enroll-comments).

### Supporto per la sala riunioni permanente di Adobe Connect {#supportforadobeconnectpersistentmeetingroom}

In Adobe Connect, i clienti utilizzano le sale riunioni esistenti che hanno già creato in Connect. Tutte le sale riunioni di Connect sono permanenti e i modelli delle sale riunioni vengono accuratamente impostati per offrire un’esperienza unificata per ogni sala permanente.

In questa versione di Learning Manager, l’integrazione con Adobe Connect è stata migliorata per supportare anche la sala permanente. Ciò significa che ora puoi creare una sessione di classe virtuale utilizzando una delle sale già create in Adobe Connect.

Learning Manager consente ora agli Allievi di accedere alla sala Connect per la sessione virtuale utilizzando l’autenticazione SSO.

Per ulteriori informazioni, consulta [***Supporto per sale permanenti in Adobe Connect***](../integration-admin/feature-summary/connectors.md#persistent).

### Avviso prima di contrassegnare la presenza se la durata della sessione è pari a zero {#warningbeforemarkingattendanceifthesessiondurationiszero}

Un Autore o un Amministratore può creare una sessione con durata uguale a 0. È possibile quando:

* la data di inizio e/o di fine sono vuote;
* l’ora di inizio e/o di fine sono vuote.

In questo aggiornamento all’Amministratore, al Manager o all’Istruttore viene mostrato un **messaggio di avviso, che indica che la durata di una sessione è zero**.

### Avviso se un modulo Classe viene creato senza aggiungere i dati della sessione {#warningifaclassroommoduleiscreatedwithoutaddingsessiondata}

Se un Autore crea un corso aggiungendo un modulo Classe o Classe virtuale, può scegliere di:

* non aggiungere una data di inizio/fine né un’ora di inizio/fine;
* aggiungere una data, ma non un’ora di inizio/fine;
* aggiungere una data e un’ora di inizio.

In tutti questi casi, quando un Amministratore, un Manager o un Istruttore contrassegna la partecipazione o il completamento, i valori della data di inizio e della data di fine della sessione diventano uguali, il che significa che in una Trascrizione Allievo il valore del tempo di apprendimento trascorso viene visualizzato come zero.

In questo aggiornamento, all’Autore viene mostrato un **messaggio di avviso che indica che i dati della sessione sono incompleti**.

### Problemi risolti in questa versione {#Issuesfixedinthisrelease-2}

**App per gli Allievi**

* Un Allievo non è in grado di visualizzare un corso in un programma di apprendimento se il corso è stato creato da un Autore esterno.
* Se un Amministratore aggiunge un post su una bacheca esterna, la richiesta di selezione va a un SME interno assegnato a tale competenza.
* Un Allievo non è in grado di visualizzare il pulsante Inizia o Continua dopo aver effettuato l’iscrizione ai corsi LinkedIn.

**E-mail**

* Quando un numero elevato di utenti era presente in un elenco DND e-mail, la pagina **Impostazioni** si caricava molto lentamente. In questo aggiornamento, l’impaginazione viene aggiunta a un elenco di DND e-mail.
* Un Istruttore riceveva aggiornamenti/e-mail per sessioni di cui non fa parte. In questo aggiornamento, questo problema è stato corretto.

**Abilità**

* In una Trascrizione Allievo, il tipo di valore di un’abilità viene visualizzato in modo errato come testo.

**App mobile**

* Nell’app mobile, un Allievo può visualizzare e iscriversi a un’istanza del piano di apprendimento, ma questo non era il comportamento desiderato. In questo aggiornamento, questo problema è stato corretto.

**Ruoli personalizzati**

* In qualità di Amministratore personalizzato, non è possibile cercare un Manager in un report del dashboard.

**Tentativi multipli**

* In alcuni scenari, alcuni moduli di corso non vengono visualizzati dagli Allievi.

**Iscrizione esterna**

* Non è possibile modificare il profilo esterno di un utente se sono state compilate postazioni per i profili principali.

### Problemi noti in questa versione {#knownissuesinthisrelease}

* Nei browser indicati di seguito, quando si passa il mouse sul riquadro sinistro, il testo viene visualizzato dopo un leggero ritardo.

   * Edge 42.17134.1.0
   * Edge 44.17763.1.0
   * Internet Explorer 11.1006
   * Internet Explorer 11.615

* Un Allievo può accedere a una sala riunioni Connect prima e dopo la sessione.

+++

+++Aggiornamento 49

## Aggiornamento 49

Data di pubblicazione: 26 agosto 2019

### Funzioni nuove e migliorate {#Newandenhancedfeatures-4}

**Ottimizzazione delle prestazioni**

* L’importazione degli utenti nel sistema è più rapida rispetto alle versioni precedenti. Vi è un miglioramento significativo durante l’importazione di dati utente di grandi dimensioni.
* Per i Manager e gli Amministratori, le opzioni nell’elenco a discesa Configurazione report sono state modificate per caricare i dati su richiesta.
* Le prestazioni delle API sono state migliorate. Molte API dovrebbero ora avere un tempo di risposta migliorato.
* Il tempo impiegato per generare la trascrizione degli allievi è stato migliorato.
* Non vi è alcun ritardo nelle pagine in cui sono elencati gli Allievi interni ed esterni, soprattutto quando ci sono molti utenti.

**Privilegi degli utenti speciali**

Un Amministratore può concedere privilegi speciali a un gruppo di utenti, selezionando i membri del gruppo che possono partecipare a tutte le bacheche. Qualsiasi restrizione imposta nella sezione Impostazioni ambito viene ignorata per il gruppo di utenti speciali. Per ulteriori informazioni, consulta [***Privilegi degli utenti speciali***](../administrators/feature-summary/social-learning-configurations-as-an-admin.md#privilege).

**Modifiche all’interfaccia utente**

* Nella finestra di dialogo **Aggiungi report**, i selettori **Intervallo di tempo** e **Filtri** vengono visualizzati come sezioni separate, compresse per impostazione predefinita. Per ulteriori informazioni, consulta [***Generazione di report***](../administrators/feature-summary/reports.md#report).

* Per un gruppo di utenti, è possibile utilizzare la ricerca con completamento automatico nella finestra di dialogo **Aggiungi report** per scegliere uno o più gruppi di utenti. Per ulteriori informazioni, consulta [***Report gruppo utenti***](../administrators/feature-summary/reports.md#user-group-reporting).

**Modifiche dei valori nelle colonne dell’ora**

Nelle colonne dell’ora delle trascrizioni Allievi, i minuti sono arrotondati al valore più vicino e il valore dei secondi è 00. Per ulteriori informazioni, consulta [***Colonne dell’ora***](../administrators/feature-summary/learner-transcripts.md#datetime).

### Problemi risolti in questa versione {#Issuesfixedinthisrelease-3}

**Dashboard Allievo**

* Un calendario di apprendimento mostrava lo stato **Sessione registrata** anche quando il Manager doveva ancora approvare l’iscrizione. Ora lo stato corretto **In sospeso** viene visualizzato dall’Allievo fino a quando il Manager non approva l’iscrizione.

* In un caso particolare, il calendario di apprendimento per una sessione mostrava lo stato **Iscritto** anche se l’Allievo aveva completato un corso.

**Dashboard per i Manager**

* I Manager non erano in grado di tracciare la conformità dei training del proprio team se i membri del team erano iscritti tramite i piani di apprendimento.

**Cerca**

* Nella vista Istruttore, non era possibile cercare un Allievo.

**Interfaccia utente**

* Per un account a cui sono applicate modifiche tassonomiche, tali modifiche non vengono rispecchiate come previsto nelle notifiche.

### Problemi noti in questa versione {#Knownissuesinthisrelease-1}

* Utilizzando la barra di ricerca, non è possibile cercare utenti eliminati nell’elenco Utenti esterni. Come soluzione alternativa, scorri verso il basso per visualizzare l’elenco di tutti gli utenti e individua manualmente l’utente richiesto.
* Se un utente speciale pubblica su una bacheca esterna, la richiesta di cura viene ricevuta dagli SME nel suo ambito.

+++

+++Aggiornamento 48

## Aggiornamento 48

Data di pubblicazione: 2 agosto 2019

### Funzioni nuove e migliorate {#Newandenhancedfeatures-5}

**Separazione dell’ambito in Apprendimento sociale per utenti interni ed esterni** Un Amministratore può definire ambiti separati per Allievi interni ed esterni. Esistono due nuove sezioni per utenti interni ed esterni. In entrambe è possibile definire gli ambiti per i gruppi di allievi. Per gli utenti interni, puoi definire i valori della Caratteristica utente. Per gli utenti esterni è possibile definire il profilo esterno, entro il quale gli allievi possono condividere lo stesso spazio sociale. Per ulteriori informazioni, vedere [***Impostazioni ambito***](../administrators/feature-summary/social-learning-configurations-as-an-admin.md#scopesettings).  **Restrizione sociale della creazione di bacheche sociali** Per limitare la creazione di bacheche da parte di tutti gli Allievi e moderarle in modo efficace, un Amministratore può concedere autorizzazioni per creare bacheche a un gruppo di utenti selezionati. L’Amministratore può limitare la creazione di una bacheca solo per un gruppo selezionato e non per tutti gli allievi che partecipano all’apprendimento sociale. Per ulteriori informazioni, consulta [***Autorizzazioni per la creazione di bacheche***](../administrators/feature-summary/social-learning-configurations-as-an-admin.md#permission).  **Consenti agli Allievi di visualizzare solo i campi Attivi vuoti** Un Amministratore può scegliere di visualizzare i campi Attivi o nascondere i campi una volta compilati i valori. Per ulteriori informazioni, vedere [***Visualizzazione utente***](../administrators/feature-summary/add-users-user-groups.md#activefields).  **Gli utenti interni vengono eliminati dopo un determinato periodo di inattività** Un Amministratore può impostare il periodo di tempo (in giorni) entro il quale un Allievo interno viene eliminato se rimane inattivo per il periodo specificato. Per ulteriori informazioni, consulta ***[Eliminazione automatica degli utenti](../administrators/feature-summary/settings.md#autodelete)***.  **Personalizzare i collegamenti nel piè di pagina** Un amministratore può aggiungere e personalizzare i collegamenti nel piè di pagina. I collegamenti possono anche essere personalizzati per le versioni in lingue diverse. Il metodo esistente per aggiungere il collegamento Contatta l’amministratore nel piè di pagina è disponibile anche nella sezione **Collegamenti a piè di pagina**. Per ulteriori informazioni, vedere [***Personalizzare i collegamenti a piè di pagina***](../administrators/feature-summary/settings.md#footer).

### Problemi noti in questa versione {#Knownissuesinthisrelease-2}

* I collegamenti a piè di pagina personalizzati non vengono visualizzati per i ruoli di Amministratore di integrazione.

+++

+++Aggiornamento 47 - App mobile

## Aggiornamento 47 - App mobile

Data di pubblicazione: 24 luglio 2019

Utenti Android:

Questo aggiornamento supporta anche le modifiche necessarie per aderire ai consigli rivisti di Google per l&#39;implementazione delle notifiche push. Quindi non riceverai più **notifiche** se utilizzi la versione 2.7.4 o versioni precedenti.

Per ricevere notifiche, ti consigliamo di effettuare l’aggiornamento alla versione 2.8.

### Funzioni nuove e migliorate {#Newandenhancedfeatures-6}

**Apprendimento sociale**

Condividi la tua esperienza con i colleghi sotto forma di contenuti generati dagli utenti pubblicati su forum di discussione per argomento. Altri allievi interessati a competenze simili possono seguire questi forum per apprendere e persino contribuire all’argomento, come su una piattaforma di social media.

Condividi idee e approfondimenti significativi in un ambiente informale. Metti Mi piace o Non mi piace su un post, caricare contenuti e commenta i post. Per ulteriori informazioni, consulta [***Apprendimento sociale nell’app mobile***](../learners/feature-summary/ipad-android-tablet-users.md#socialmobile).

**Condivisione di media su una bacheca**

Condividi immagini, documenti o file audio o video su qualsiasi bacheca, in modo che gli altri membri della bacheca possano visualizzare il tuo post e avviare un’interazione.  Per ulteriori informazioni, consulta [***Post di condivisione***](../learners/feature-summary/ipad-android-tablet-users.md#socialmobile).

**Invio di file per moduli classe e attività**

Invia al tuo istruttore file come prova del completamento del corso. L’istruttore può approvare o rifiutare l’invio, in base al contenuto del file. Per ulteriori informazioni, consulta [***Invio di file per l’approvazione***](../learners/feature-summary/ipad-android-tablet-users.md#submitfile).

**Supporto piattaforme aggiornato**

L’app mobile Learning Manager è ora supportata su dispositivi con Android 7 e versioni successive e iOS 10 e versioni successive. Per ulteriori informazioni, consulta [***Requisiti di sistema***](../system-requirements.md).

### Problemi noti in questa versione {#Knownissuesinthisrelease-3}

1. Su Android, non è possibile caricare un file GIF in un post, commento o durante la risposta a un commento.
1. Come moderatore di qualsiasi bacheca, non puoi eliminare post, commenti o risposte di un utente. Tuttavia puoi farlo dalla web app.
1. Nell’app non è possibile contrassegnare un tipo di domanda.
1. Dopo aver abilitato l’Apprendimento sociale sull’app, riavvia l’app per visualizzare la scheda **Apprendimento sociale**. Se non vedi Apprendimento sociale, chiudi l’app e riavviala. La scheda Apprendimento sociale sarebbe visibile.

+++

+++Aggiornamento 46

### Funzioni nuove e migliorate {#Newandenhancedfeatures-7}

## Aggiornamento 46

Data di pubblicazione: 20 giugno 2019

**Cura automatica di contenuti**

L’Apprendimento sociale consente ai contenuti pubblicati dagli Allievi di essere selezionati in due modi: **Nessuna cura** e **Cura manuale**. In questa versione, Adobe Learning Manager migliora l’apprendimento sociale fornendo funzionalità di cura automatica basate su intelligenza artificiale. Una volta pubblicato, il contenuto viene analizzato per identificare se appartiene all’abilità per cui è stato pubblicato. In base al punteggio di confidenza, il contenuto viene pubblicato in diretta o inviato per la cura manuale. Per ulteriori informazioni, consulta *[**&#x200B; Cura auto-assistita &#x200B;**](../administrators/feature-summary/social-learning-configurations-as-an-admin.md#autocuration)**.***

**Mappare abilità con domini di abilità**

Associa le abilità nel tuo account con i domini di abilità presenti nell’LMS di Learning Manager. Ciò aiuta a collegare le abilità del tuo account con i domini di abilità che Learning Manager supporta per la cura auto-assistita. Per ulteriori informazioni, consulta [***Mappare abilità con domini di abilità***](../administrators/feature-summary/curation-skills.md).

**Specifiche CSV e CSV di esempio**

Specifiche CSV aggiornate che puoi utilizzare per mappare i dati di migrazione LMS esistenti. Utilizza i file zip csv-specific e sample-csvs più recenti scaricabili per comprendere il formato prescritto dei dati da immettere. Per ulteriori informazioni, consulta [***Manuale di migrazione***.](../integration-admin/feature-summary/migration-manual.md)

### Problemi risolti in questa versione {#Issuesfixedinthisrelease-4}

**API di Learning Manager**

* Quando viene aggiunto un profilo esterno utilizzando il metodo POST dell’API *externalProfile*, l’e-mail di benvenuto non viene visualizzata.

**Dashboard per i Manager**

* Quando un Manager selezionava l’opzione **Questo trimestre**, i dettagli su iscrizione, progressi e completamento di un Oggetto di apprendimento non venivano visualizzati. In questa versione, questi dettagli vengono visualizzati come previsto.

**Allievi in lista di attesa**

* Nelle versioni precedenti di Learning Manager, dopo che un Manager aveva iscritto gli allievi, quando un Istruttore desiderava verificare gli allievi inseriti in lista d’attesa, veniva visualizzato un messaggio di errore. In questa versione, un Istruttore può sfogliare l’elenco degli allievi inseriti in lista d’attesa senza visualizzare alcun messaggio di errore.

**Panoramica certificazioni**

* Dopo che un autore aveva creato un corso e una certificazione che conteneva una descrizione e una panoramica, quando un Allievo apriva la pagina del corso, il contenuto della panoramica non veniva visualizzato come previsto. Il contenuto era tuttavia visibile nelle pagine di anteprima degli allievi nelle app di amministrazione e dell’autore. In questa versione, il contenuto della panoramica viene visualizzato come previsto nell’app dell’Allievo.

**Catalogo**

* Gli allievi possono visualizzare tutti gli Oggetti di apprendimento per ciascun catalogo. Nelle versioni precedenti, se un catalogo non conteneva un Oggetto di apprendimento, il catalogo veniva comunque mostrato all’inizio della lista dei cataloghi. In questa versione, tutti i cataloghi che non contengono di oggetti di apprendimento vengono visualizzati nella parte inferiore della lista dei cataloghi.

+++

+++Aggiornamento 45

Data di pubblicazione: 30 maggio 2019

**Funzioni nuove e migliorate**

* Ricerca consolidata in tutte le istanze per gli Allievi iscritti nella sezione Allievi dell’Oggetto di apprendimento. Cerca utenti iscritti nella sezione Allievo dell’Oggetto di apprendimento utilizzando la ricerca con completamento automatico. Per ulteriori informazioni, consulta [***Cerca utenti iscritti***](../administrators/feature-summary/courses.md#searchforusers).
* Completa le funzionalità di modifica degli oggetti di apprendimento acquisiti tramite catalogo condiviso. Per ulteriori informazioni, vedere [***Controllo catalogo condiviso***](../administrators/feature-summary/shared-catalog-full-control.md). Per abilitare la funzione, contatta l’assistenza di Learning Manager.
* Gli istruttori ora possono identificare facilmente sessioni e moduli con revisioni in sospeso. Per ulteriori informazioni, consulta [***Revisioni in sospeso***](../instructors/feature-summary/learners.md#pending).

* Le competenze ora supportano l’assegnazione di valori di credito in formato decimale. Ciò consente agli autori di assegnare un valore di credito di livello decimale a un determinato corso. Per ulteriori informazioni, consulta [***Supporto decimale***](../administrators/feature-summary/skills-levels.md#decimal).
* Creazione automatizzata di ruoli personalizzati. Per ulteriori informazioni, consulta [***Configurazione dei ruoli tramite file CSV***](../integration-admin/feature-summary/configure-role-csv-files.md).
* Gli invii di certificazioni esterne e moduli di attività sono ora facoltativi. Ciò consente a Manager e Istruttori di valutare senza dover inviare nulla. Per ulteriori informazioni, vedere [***Invio facoltativo***](../managers/feature-summary/learning-objects.md#optional).
* Download di trascrizioni allievi per utenti eliminati. Per ulteriori informazioni, consulta [***Trascrizioni allievi***](../administrators/feature-summary/learner-transcripts.md).
* Supporto per le seguenti lingue:

   * Coreano
   * Turco
   * Olandese
   * Polacco

**Problemi noti**

* L’aggiunta di cifre decimali nei crediti delle abilità è supportata solo per la lingua inglese.
* Per le lingue coreana, giapponese e russa, il valore del tempo di sessione non viene visualizzato come previsto.

**Problemi risolti in questa versione**

* I punteggi del questionario non vengono salvati per un programma di apprendimento o certificazione nelle schede Frequenza e Punteggio.
* Un amministratore o un manager non è in grado di contrassegnare una certificazione esterna come completata.
* Nella finestra di dialogo Trascrizioni allievo, un amministratore non è in grado di selezionare un intervallo di date personalizzato se la lingua è impostata su portoghese o spagnolo.
* Un amministratore non è in grado di creare un profilo esterno quando la lingua del profilo è il francese.
* I campi attivi non sono visibili nella finestra di dialogo Modifica utente se viene impostata una lingua diversa dall’inglese.

+++

+++Aggiornamento 44 - App mobile

Data di pubblicazione: 26 aprile 2019

* **Modifiche all&#39;interfaccia utente:** Nell&#39;app, le opzioni ![](assets/hamburger.jpg) e ![](assets/search-magnifying-glass-icon.png) sono ora visualizzate nella parte superiore.

![](assets/1.png)

* **Scansione del codice QR per l&#39;iscrizione:** le funzionalità del codice QR sono state migliorate. Oltre che per contrassegnare la partecipazione, ora il codice QR può essere utilizzato per l’iscrizione a un corso e il completamento di un corso.

  Per iscriverti a un corso e per completarlo, puoi eseguire la scansione di un codice QR fornito dall’amministratore. Per ulteriori informazioni sulla scansione dei codici QR nella versione Web di Learning Manager, consulta [***Leggi codice QR***] (<https://helpx.adobe.com/captivate-Learning> Manager/whats-new.html#QRcodetoenrollcompleteenrollcompleteacourse).

* **Tentativi multipli per un corso:** L’app Learning Manager consente all’Allievo di utilizzare corsi con più tentativi attivati. Per ulteriori informazioni sull&#39;impostazione di più tentativi, vedere [***Tentativi multipli***] (<https://helpx.adobe.com/captivate-Learning> Manager/authors/feature-summary/courses.html#Multiattempts).

+++

+++Aggiornamento 43

## Aggiornamento 43

Data di pubblicazione: 28 gennaio 2019

* Il tempo dedicato da un Allievo all’apprendimento di un modulo può venire conteggiato più volte quando la partecipazione viene contrassegnata più di una volta. Questo problema è stato risolto.
* Se si contrassegna la partecipazione a un oggetto di apprendimento in una sessione di più giorni, viene visualizzata la data di inizio sessione errata per un Allievo in una trascrizione di apprendimento. Questo problema è stato risolto.
* Quando un corso viene aggiunto a un programma di apprendimento completato o a una certificazione, gli utenti potrebbero non riuscire a visualizzarlo. Questo problema è stato risolto.
* L’iscrizione degli utenti potrebbe avvenire in modo errato quando vengono spostati da un gruppo di utenti. Questo problema è stato risolto.
* Allievo e istruttore non ricevono nessuna e-mail quando i dettagli della sessione vengono modificati nell’app dell’istruttore. Questo problema è stato risolto.
* L’URL di Adobe Connect non funziona correttamente in presenza di “/” alla fine dell’URL. Questo problema è stato risolto.
* Quando si seleziona almeno un modulo obbligatorio per un corso già pubblicato, viene visualizzato un messaggio di errore. Questo problema è stato risolto.
* Quando un Allievo completa un corso che in seguito viene contrassegnato come obbligatorio dall’Autore, il completamento del corso potrebbe non essere contrassegnato come completato. Questo problema è stato risolto.
* Il valore verificato di un modulo selezionato per un corso duplicato non viene visualizzato immediatamente. Viene visualizzato come corso duplicato solo quando la pagina viene aggiornata. Questo problema è stato risolto.
* Tutti i moduli vengono visualizzati come deselezionati in modalità di modifica dopo la pubblicazione di un corso. Per visualizzare le modifiche è necessario aggiornare la pagina. Questo problema è stato risolto.
* La selezione di un modulo obbligatorio viene resa disponibile per un corso progressivo anche quando non dovrebbe esserlo. Questo problema è stato risolto.
* Un modulo obbligatorio continua a essere visualizzato nella casella di controllo a discesa anche dopo essere stato rimosso durante la modifica del corso. Questo problema è stato risolto.
* I moduli di preparazione e verifica vengono contrassegnati come obbligatori per impostazione predefinita. Questo problema è stato risolto.
* Quando si fa clic sul collegamento di feedback L3 presente nell’e-mail, la finestra modale dei feedback non si apre. Questo problema è stato risolto.
* La certificazione non è presente nel menu a discesa del report del dashboard, sebbene sia visibile nell’app di gestione e nell’elenco API dei dati. Questo problema è stato risolto.
* Alcuni oggetti di apprendimento non possono essere ritirati dall’Amministratore per mancanza di autorizzazioni sebbene i cataloghi condivisi siano indipendenti dagli account Learning Manager. Questo problema è stato risolto.

+++

+++Aggiornamento 42

Aggiornamento 42

Data di pubblicazione: 11 gennaio 2019.

* L’inserimento delle notifiche utente potrebbe non riuscire in modo casuale, con conseguente mancata consegna delle e-mail associate. Questo problema è stato risolto.
* `If a Learner is enrolled in Learning Program 1 and a Course in Learning Program 2, when the Learning Transcript is downloaded for a user group or more than one individual, the Learning Transcript may have missing data. This issue is fixed.`

+++

+++Aggiornamento 41

Aggiornamento 41Data di pubblicazione: 1 dicembre 2018.

* Gli amministratori possono controllare l’autorizzazione concessa agli allievi per la visualizzazione dei punteggi di quiz nelle trascrizioni degli allievi. L’opzione può essere abilitata/disabilitata dalla pagina Impostazioni.
* L’inserimento delle notifiche utente potrebbe non riuscire in modo casuale, con conseguente mancata consegna delle e-mail associate. Questo problema è stato risolto.
* I dati relativi al tempo impiegato per l’apprendimento potrebbero non essere riportati nei report di trascrizione degli Allievi e del dashboard. Questo problema è stato risolto.
* Le informazioni su attività quali iscrizione/completamento potrebbero non essere presenti nelle trascrizioni degli Allievi scaricate da un Manager. Questo problema è stato risolto.
* I moduli che fanno parte di un corso ancora attivo possono apparire come completati nelle trascrizioni degli allievi. Questo problema è stato risolto.
* Nelle trascrizioni degli allievi potrebbero non essere visualizzati i dati scaricati in base all’intervallo di date selezionato. Questo problema è stato risolto.
* Gli utenti a cui è assegnato solo il ruolo di Autore potrebbero non visualizzare i Cataloghi. Questo problema è stato risolto.
* Quando un Amministratore del ruolo personalizzato scarica la Trascrizione Allievo, il report scaricato non conterrà informazioni sugli LO che facevano parte solo dei cataloghi predefiniti. Questo problema è stato risolto.
* Il numero totale degli utenti potrebbe non corrispondere all’elenco di utenti nella pagina Gruppo di utenti. Questo problema è stato risolto.
* La finestra a comparsa del programma di apprendimento potrebbe non essere visualizzata anche se abilitata e gli utenti potrebbero essere reindirizzati alla pagina degli oggetti di apprendimento. Questo problema è stato risolto.
* Quando la lista d’attesa viene cancellata e gli allievi vengono iscritti a un corso, l’Amministratore può ricevere una notifica e-mail nella quale è indicato il suo nome anziché il nome dell’Allievo. Questo problema è stato risolto.
* Il Cognome di un utente aggiunto tramite l’API utente POST potrebbe non essere visualizzato nell’interfaccia utente. Questo problema è stato risolto.

+++

+++Aggiornamento 40

Aggiornamento 40

Data di pubblicazione: settembre 2018.

Ottimizzazione delle prestazioni

* Gli utenti potrebbero riscontrare problemi di timeout durante il download di gruppi di trascrizioni allievi di grandi dimensioni. Questo problema è stato risolto.
* Gli utenti potrebbero riscontrare un ritardo durante lo scaricamento di un ampio set di report di iscrizione in cui è registrato il punteggio dei quiz degli allievi. Questo problema è stato risolto.
* Il download di un ampio set di report Punteggio quiz potrebbe richiedere più tempo del solito. Questo problema è stato risolto.
* Quando l’Allievo completa un programma di apprendimento, il modulo di feedback L1 potrebbe non essere visualizzato automaticamente anche se la finestra a comparsa automatica è abilitata dall’Amministratore. Questo problema è stato risolto.
* Nei report di prova di verifica dell’utente e del contenuto scaricati, le colonne modificate per nome utente e e-mail utente potrebbero non essere registrate. Il report mostra il Sistema in questi casi. È stato aggiornato per essere contrassegnato come Sconosciuto.

+++

+++Aggiornamento 39

Data di pubblicazione: 19 maggio 2018.

* Questa versione di Adobe Learning Manager propone nuove funzionalità e miglioramenti. Offre la possibilità di creare ruoli personalizzati, aggiungere etichette di catalogo, rimuovere utenti, gestire tag, rinominare oggetti di apprendimento, integrare Slack, nuove integrazioni di connessione, supporto di xAPI e molto altro. Per ulteriori informazioni sulle nuove funzioni e i miglioramenti, vedere [Riepilogo delle nuove funzioni](../whats-new.md#main-pars_text).

* Learning Manager è conforme al GDPR. Per ulteriori informazioni, consulta [Conformità di Learning Manager al GDPR](/help/migrated/kb/prime-gdpr.md).

## Problema noto {#knownissue}

* Il collegamento ipertestuale al numero di corsi e certificazioni all’interno delle etichette modali include corsi ombra e certificazioni ricorrenti. Quando si fa clic sul collegamento ipertestuale, questi corsi e certificazioni potrebbero non essere elencati causando una mancata corrispondenza nei numeri.

+++

+++Aggiornamento 38

* Gli allievi con stato In sospeso o In attesa di accettazione venivano contrassegnati come completati. Questo problema è stato risolto.
* Quando un Istruttore cerca e seleziona tutti gli Allievi, il numero di Allievi selezionati e il conteggio visualizzato presentano differenze. Questo problema è stato risolto.
* Quando cerchi e selezioni un Allievo e contrassegni la partecipazione, Learning Manager potrebbe contrassegnare la partecipazione per tutti gli Allievi. Questo problema è stato risolto.
* Learning Manager mostra l’ora nelle e-mail nel formato 24 ore. Questo problema è stato risolto. Ora viene visualizzato nel formato 12 ore.
* Quando un manager nomina un Allievo per un corso utilizzando il pulsante di nomina disponibile nella pagina delle notifiche, il modale di nomina non viene caricato. Questo problema è stato risolto.
* Nei report Excel esportati, la data di scadenza, che dovrebbe essere la data di iscrizione + i giorni per completare il valore impostato nell&#39;istanza automatica degli LO, verrebbe visualizzata in modo errato. Questo problema è stato risolto.

* I risultati della ricerca utente vengono visualizzati vuoti quando non sono presenti utenti nel gruppo cercato. Questo problema è stato risolto.
* I manager non possono essere eliminati anche se non ci sono report diretti. Questo problema è stato risolto. I manager ora possono essere eliminati.
* La funzionalità di avanzamento modulo di reimpostazione potrebbe non funzionare. Questo problema è stato risolto.
* La certificazione eliminata potrebbe essere visualizzata nel widget per gli Allievi. Questo problema è stato risolto.
* Il problema relativo al calcolo dell’efficacia del corso è stato risolto.

* Il problema di integrazione del nuovo account di connessione è stato risolto.
* La finestra a comparsa del feedback L1 potrebbe non apparire se è abilitata su istanze non predefinite. Il problema è stato risolto.
* L’Istruttore potrebbe non essere in grado di contrassegnare la partecipazione di tutti gli utenti in un’unica sessione per le sessioni che fanno parte del programma di apprendimento o della certificazione. Questo problema è stato risolto.

+++

+++Aggiornamento 37

Data di pubblicazione: 25 marzo 2018

La versione di marzo 2018 di Adobe Learning Manager propone incredibili nuove funzionalità e miglioramenti. Offre a te, generazione di report di prova di verifica degli utenti e report di accesso/accesso, offre agli Allievi la possibilità di scegliere le istanze del corso, miglioramenti alle aule e alle aule virtuali e molto altro. Questa versione contiene anche le correzioni ai bug e i miglioramenti alle prestazioni.

Per leggere tutte le novità di questa versione, consulta [Novità di Adobe Learning Manager](../whats-new.md).

### Problema noto {#KnownIssue-1}

**Problema:** l’accesso ad alcuni oggetti di apprendimento specifici tramite Internet Explorer v11.1478.10586.0 potrebbe provocare l’arresto anomalo di Learning Manager.

**Soluzione:** aggiorna il browser Internet Explorer 11 alla versione più recente contattando il team IT della tua organizzazione.

+++

+++Aggiornamento 36

Data di pubblicazione: 22 gennaio 2018.

### Problemi risolti {#issuesfixed}

* Qualsiasi modifica all’impostazione di personalizzazione e-mail può far scomparire il banner e-mail. Questo problema è stato risolto.
* In alcuni casi gli allievi non riescono ad aggiungere o avviare risorse formative personalizzate. Questo problema è stato risolto.
* In alcuni casi i gruppi di utenti personalizzati presenti in un account non vengono elencati sotto il campo del gruppo di utenti nella finestra di dialogo modale di aggiunta o modifica report. Questo problema è stato risolto.
* Se il nome di un’immagine del distintivo include spazio, è possibile che non venga visualizzata per l’Allievo nella home page.
* Quando un utente iscritto viene eliminato da un corso, in determinati casi il report del corso e il report del quiz non vengono generati per il corso specifico. Questo problema è stato risolto.
* Se l’Amministratore modifica il numero di posti assegnati per un Manager, il conteggio può apparire errato nella richiesta di assegnazione quando questa viene aperta da posizioni diverse. Questo problema è stato risolto.
* Quando si converte un utente esterno in utente interno è possibile che l’utente non venga aggiunto al gruppo Tutti gli allievi interni. Questo problema è stato risolto.
* Se cerchi un singolo Allievo, lo selezioni ed esegui l’azione di annullamento dell’iscrizione, potrebbe annullarsi l’iscrizione di tutti gli allievi nel gruppo anziché solo di quello selezionato. Questo problema è stato risolto.
* In qualità di Amministratore, potresti non essere in grado di utilizzare la casella di controllo per selezionare un Allievo all’interno delle certificazioni. Questo problema è stato risolto.
* La creazione e aggiornamento di gruppi di utenti con più di 600 singoli utenti potrebbe non riuscire. Questo problema è stato risolto. Ora puoi creare gruppi di utenti con più di 600 singoli utenti.
* Se elimini un gruppo di utenti personalizzato appartenente a un altro gruppo di utenti personalizzato, la regola di intersezione può trasferire il numero utente al gruppo di livello superiore. Questo problema è stato risolto.
* Quando il catalogo predefinito è disattivato e viene creato un nuovo catalogo, se il manager ha accesso a questo catalogo appena creato potrebbe non essere in grado di cercare corsi in tale catalogo. Questo problema è stato risolto.
* Gli utenti dell’applicazione per dispositivi mobili potrebbero non ricevere feedback L1 come notifiche push. Questi problemi sono stati risolti.

+++

+++Aggiornamento 35

Data di pubblicazione: 7 gennaio 2018.

Questa versione di Learning Manager offre ottimizzazioni delle prestazioni volte a migliorare la scalabilità, le prestazioni e la sicurezza.

### Miglioramenti {#enhancements}

* Utilizza Elasticsearch durante la ricerca di corsi e utenti in tutte le applicazioni. Ciò include la ricerca di corsi, utenti e gruppi di utenti.
* Supporta l’utilizzo del connettore Box per integrare Learning Manager con sistemi esterni per l’automazione della sincronizzazione dei dati. Per ulteriori informazioni, consulta [Connettore Box](../integration-admin/feature-summary/connectors.md#main-pars_header_302653946).
* Specifiche CSV aggiornate che puoi utilizzare per mappare i dati di migrazione LMS esistenti. Utilizza i file zip csv-specific e sample-csvs più recenti scaricabili per comprendere il formato prescritto dei dati da immettere. Per ulteriori informazioni, consulta il [manuale di migrazione.](../integration-admin/feature-summary/migration-manual.md)

+++

+++Aggiornamento 34

### Problemi risolti {#IssuesFixed-1}

* Gli annunci potrebbero non riuscire quando il numero di utenti è elevato. Questo problema è stato risolto.
* L’accesso all’account Learning Manager tramite l’URL del dominio secondario in UE potrebbe reindirizzare gli utenti a una pagina diversa. Questo problema è stato risolto.
* Quando un programma di apprendimento viene ordinato, l’Allievo deve essere in grado di utilizzarlo solo nell’ordine specificato. Gli allievi erano in grado di partecipare ai corsi non elencati per primi tramite i collegamenti ipertestuali del corso. Questo problema è stato risolto. Gli allievi non possono più avviare un corso fino a quando non termina quello precedente.

* Il messaggio di errore della versione del browser non supportata potrebbe non essere visualizzato nelle versioni non supportate di Internet Explorer (IE 7, IE 8, IE 9 e IE 10) e Safari (versione 7, 8 e 9). Questo problema è stato risolto.



+++

+++Aggiornamento 33

Data di pubblicazione: 5 ottobre 2017.

### Problemi risolti {#IssuesFixed-2}

* Le modifiche a un corso condiviso potrebbero non essere propagate all’account condiviso se l’Autore nell’account di origine salva automaticamente il corso. Questo problema è stato risolto.
* A volte, per progetti Learning Manager specifici, i contenuti venivano bloccati nel lettore Fluidic. Questo problema è stato risolto.

* L’elenco del calendario nel widget Calendario di apprendimento potrebbe essere visualizzato in ordine sparso. Questo problema è stato risolto. L’elenco verrà ora visualizzato in ordine corretto.
* Quando la partecipazione viene segnalata tramite l’opzione di selezione di tutti gli elementi, gli allievi vengono segnalati come partecipanti in tutti gli oggetti di apprendimento per la stessa sessione. Questo problema è stato risolto.
* Su determinati schermi ad alta risoluzione, l’e-mail ricevuta da Learning Manager presentava problemi di allineamento e troncamento per il testo e l’immagine del banner. Questi problemi sono stati risolti.
* Alcuni messaggi e-mail di Learning Manager come le e-mail senza dati di notifica non venivano inviati agli utenti. Esempio: e-mail ricevuta alla creazione e all’attivazione di un profilo esterno e e-mail ricevuta alla configurazione dell’account di connessione. Questo problema è stato risolto.
* Quando crei un programma di apprendimento, imposti un promemoria, registri gli utenti e quindi modifichi la scadenza dell’istanza, la scadenza modificata potrebbe non essere riportata per i promemoria. Questo problema è stato risolto. I promemoria avranno ora la scadenza modificata.
* In alcuni casi, per i contenuti creati utilizzando Adobe Presenter, il tempo totale e quello trascorso nel lettore Fluidic non erano sincronizzati con il contenuto. Questo problema è stato risolto.
* In alcuni casi, dopo l’aggiunta di un programma di apprendimento a un catalogo, l’opzione da aggiungere potrebbe comunque essere abilitata. Questo problema è stato risolto.
* L’apertura di Learning Manager in un browser per dispositivi visualizza un’opzione che consente di provare Learning Manager nell’app per dispositivi. Se l’app non è installata e fai clic su Sì, avvia Play Store (Android) o, se installata, avvia l’app (in Android e iOS). Questo flusso di lavoro presentava problemi ed è stato risolto.

+++

+++Aggiornamento 32

Data di pubblicazione: 17 agosto 2017

### Problemi risolti {#IssuesFixed-3}

**Se un corso includeva più versioni dei moduli, in caso di eliminazione veniva ripristinata la versione precedente.**

Quando un corso includeva più voci relative alle versioni per moduli specifici, in caso di eliminazione di un modulo veniva ripristinata la versione precedente dello stesso e il modulo non veniva eliminato completamente. Questo problema è stato risolto.

**Le modifiche apportate a un corso condiviso non venivano propagate in caso di salvataggio automatico quando si passava a un’altra scheda.**

Le modifiche apportate a un corso condiviso a volte non venivano propagate all’account tenant in caso di salvataggio automatico quando l’Autore nell’account principale passava alla scheda successiva. Questo problema è stato risolto.

**Gli utenti non potevano modificare la scadenza delle istanze per i corsi di sole attività.**

Gli utenti non potevano modificare la scadenza di un’istanza nei corsi di attività poiché veniva ripristinata la data di scadenza precedente. Questo problema è stato risolto.

**Impossibile utilizzare un ID univoco una volta rimosso da un oggetto di apprendimento.**

Quando a un corso veniva assegnato un ID univoco che in seguito veniva rimosso, non era possibile utilizzare nuovamente tale ID. Questo problema è stato risolto.

**Un programma di apprendimento già registrato nell’ambito di un evento per un piano di apprendimento poteva essere di nuovo visualizzato all’interno di un altro evento nell’app per Allievi.**

Se un programma di apprendimento era già registrato nell’ambito di un evento per un piano di apprendimento, poteva essere nuovamente visualizzato all’interno di un altro evento nell’app per Allievi. Questo problema è stato risolto.

**Gli Allievi ricevevano e-mail di promemoria in cui la data di scadenza o l’orario della sessione specificati non erano corretti.**

Gli Allievi spesso ricevevano e-mail con promemoria relativi a scadenze o orari di sessione errati a causa delle correzioni del fuso orario. Questo problema è stato risolto.

**La linea temporale della classifica di Gamification mostra gli Allievi esterni se si passa da Allievo esterno a interno.**

La linea temporale della classifica di gamification di un Allievo interno poteva mostrare un Allievo esterno quando veniva convertito da esterno a interno. Questo problema è stato risolto.

**Il campo UUID per un Allievo viene visualizzato in formato modificabile durante la creazione di utenti singoli e CSV in un account abilitato per UUID.**

Il campo UUID veniva visualizzato dall’Allievo durante il completamento del suo profilo anche se l’Amministratore aveva indicato gli UUID per utenti singoli e CSV. Questo problema è stato risolto.

**Il tempo impiegato per l’apprendimento non veniva registrato nei report in alcuni casi.**

I dati relativi al tempo impiegato per l’apprendimento non venivano indicati nei report per un Allievo nei seguenti casi:

* Se la sua partecipazione viene contrassegnata automaticamente dal sistema per i moduli di connessione.
* Quando viene eseguita la scansione di un codice QR per moduli classe o classe virtuale utilizzando l’applicazione per dispositivi Learning Manager.

**Questa versione di Learning Manager ha inoltre introdotto miglioramenti e correzioni di bug relativi al lettore per dispositivi.**

* Problemi relativi al completamento dei moduli di attività. Questi problemi sono stati risolti.
* Quando l’Allievo riproduceva un video in modalità verticale, i pulsanti +10 e -10 a volte non funzionavano. Questo problema è stato risolto
* È stata migliorata l’esperienza di riproduzione di alcuni progetti di esempio su dispositivi Android (cellulari e tablet) per i quali in precedenza si verificava uno sfarfallio.
* Quando si aggiunge una nuova nota, il pannello delle note dovrebbe chiudersi e nel lettore dovrebbe riprendere la riproduzione. Ciò non accadeva in alcuni casi. Questi problemi sono stati risolti.
* Quando si aprivano le note aggiunte a un modulo, il pulsante di chiusura a volte non veniva visualizzato. Questo problema è stato risolto.
* Quando l’Allievo apriva il pannello delle note utilizzando l’indicatore di nota, a volte doveva fare clic due volte sull’icona Note per chiudere il pannello.
* Facendo clic sul sommario, è possibile che il contenuto non venga compresso automaticamente e che sia necessario chiuderlo manualmente per visualizzarlo. Questo problema è stato risolto.
* Se un corso includeva un modulo con più lingue, a volte non erano visualizzate tutte le lingue disponibili poiché la barra di scorrimento non veniva ridimensionata adeguatamente. Questo problema è stato risolto.
* Quando si apriva un modulo per un corso di attività di terze parti in un lettore in modalità orizzontale, l’orientamento del testo a volte non veniva adeguato, rendendo difficile lo scorrimento. Questo problema è stato risolto.
* È stata incrementata l’area di tocco per il pulsante di chiusura del lettore sia in modalità online che in modalità offline.
* Il sommario non si chiude automaticamente quando si cambia l’orientamento del dispositivo. Questi problemi sono stati risolti.
* Sono stati risolti alcuni problemi secondari relativi all’interfaccia utente, come l’allineamento del pulsante di riproduzione, del pulsante di scelta e altre impostazioni in modalità orizzontale e verticale.

* È stato risolto il problema relativo alla visualizzazione della barra di ricerca anche quando l’opzione per mostrare il controllo della riproduzione è deselezionata nel contenuto.
* Il pulsante di chiusura del lettore non era visibile per alcuni progetti quando l’orientamento del dispositivo veniva cambiato. Questi problemi sono stati risolti.
* Il problema relativo al troncamento della sezione del sommario del modulo nella modalità orizzontale sul lettore per dispositivi è stato risolto. In alcuni casi, il sommario del contenuto non era visibile nel lettore per dispositivi. Anche questo problema è stato risolto.

**Questa versione di Learning Manager ha inoltre introdotto i miglioramenti e le correzioni relativi all’applicazione per dispositivi elencati di seguito**.

* La notifica push relativa alle scadenze di completamento non veniva visualizzata su alcuni dispositivi. Questo problema è stato risolto.
* Ora supportiamo il ciclo di vita degli oggetti di apprendimento anche sull’applicazione per dispositivi. Gli Allievi possono ora accedere ai contenuti più recenti negli oggetti di apprendimento se questi sono stati modificati dall’Autore.

* I problemi di orientamento dell’applicazione Learning Manager (incluso l’orientamento predefinito, ovvero la modalità verticale) sono stati risolti.
* È possibile che non sia disponibile un’opzione per aggiornare il contenuto quando l’utente passa dalla modalità offline a quella online.
* L’ordinamento dei moduli in modalità online è ora supportato per i corsi nell’applicazione per dispositivi.

* Se un utente non ha scaricato risorse formative, facendo clic sulla scheda Le mie risorse formative in modalità offline potrebbe verificarsi l’arresto anomalo dell’app in IOS e la visualizzazione di un messaggio di errore durante il caricamento dei dati in Android. Questo problema è stato risolto.
* L’applicazione Learning Manager si chiudeva o generava un errore se si accedeva a un corso subito dopo aver disattivato la connessione Internet, anche nel caso di un corso scaricato. Questo problema è stato risolto.
* A volte, in seguito alla scansione di un codice QR, veniva visualizzata l’immagine acquisita durante la scansione di un codice QR precedente. Questo problema è stato risolto.
* Se si tenta di rimuovere una risorsa formativa già aggiunta dalla scheda Le mie risorse formative, in alcuni casi viene visualizzato un messaggio di errore. Questo problema è stato risolto.

+++

+++Aggiornamento 31

Data di pubblicazione: 16 luglio 2017

### Miglioramenti {#Enhancements-1}

**Gamification**

In questa versione è stata migliorata l’area di validità della gamification. Gli utenti esterni possono ora prendere parte alla gamification. In qualità di amministratore, puoi definire l’area di validità della gamification modificando le impostazioni per l’area di validità. Puoi abilitare la gamification in modo selettivo tra utenti, gruppi o posizioni di profilo simili.

**Miglioramenti utente esterno**

Con questo miglioramento puoi impostare l’intervallo di tempo dopo il quale gli utenti vengono eliminati automaticamente dopo il periodo di inattività. Il miglioramento consente inoltre all’Amministratore di aggiungere nuovamente un utente come Allievo esterno in caso di Allievi eliminati sia automaticamente che manualmente.

**Risorsa formativa, annunci e report di annullamento dell’iscrizione**

Le risorse formative sono contenuti di formazione a cui un Allievo ha accesso senza bisogno di iscriversi a uno specifico oggetto di apprendimento come Corso o Programma di apprendimento. Grazie a questo miglioramento, gli amministratori possono estrarre e scaricare il report Risorse formative. In qualità di amministratore, puoi anche generare un report di tutti gli annunci che ti sono stati inviati. Amministratori e Manager possono inoltre estrarre un report degli allievi con iscrizione annullata.

**Connettori Learning Manager**

Puoi ora esportare le abilità utente in una posizione FTP per l’integrazione con qualsiasi sistema di terzi con l’opzione Esportazione dati. Puoi specificare il nome della connessione per l’integrazione e scegliere se importare gli utenti interni o esportare le abilità degli utenti configurandoli o recuperandoli a richiesta.

**Copia di istanze del corso**

Ora puoi copiare l’URL dell’istanza facendo clic sulla freccia a discesa nell’angolo superiore destro di un’istanza.

### Problemi risolti {#IssuesFixed-4}

**Gli utenti non ricevevano l’invito nel calendario al momento dell’iscrizione a un programma di apprendimento**

A volte gli utenti non ricevevano il file dell’invito nel calendario (.ics) quando si iscrivevano a programmi di apprendimento, classi con certificati e sessioni Connect. Questo problema è stato risolto. Ora gli utenti riceveranno i file .ics come allegati contenenti i dettagli della sessione e l’e-mail di iscrizione.

**La descrizione delle attività era visualizzata in inglese sebbene fosse disponibile in più lingue**

Per gli utenti la cui preferenza per la lingua dei contenuti era impostata su una lingua diversa dall’inglese veniva comunque visualizzata la descrizione dei moduli di attività in inglese. Questo problema è stato risolto.

+++

+++Aggiornamento 30

Data di pubblicazione: 30 giugno 2017

### Miglioramenti {#Enhancements-2}

**Supporto di varie attività nel piano per l’apprendimento** 

In quanto Amministratore o Autore, adesso puoi assegnare varie attività a un piano per l’apprendimento. Se una delle proprietà dell’istanza dell’Oggetto di apprendimento viene ritirata o scade, l’intero Piano di apprendimento viene disattivato automaticamente. Con questo miglioramento puoi inoltre eseguire ricerche nei campi **[!UICONTROL Apprendimento completato]** e **[!UICONTROL Assegna apprendimento]** mediante l’ID univoco degli Oggetti di apprendimento.

**Accessibilità**

Con questo aggiornamento, Learning Manager per gli allievi ora supporta lo standard di accessibilità Section 508. Inoltre, Learning Manager è compatibile con la versione più recente di **[!UICONTROL JAWS]**. Questa funzione è supportata solo per l’applicazione per allievi. Utilizza Internet Explorer 11, Windows Chrome o macOS Safari per accedere a questa funzione.

### Problemi risolti {#IssuesFixed-5}

**Informazioni non corrette in determinati fusi orari**

I promemoria delle scadenze indicavano erroneamente il numero di giorni rimanenti per gli allievi in determinati fusi orari. Questo problema è stato risolto.

**Problemi relativi al programma di apprendimento nel caso di un&#39;istanza del programma scaduta**

L’avvio di moduli dal Programma di apprendimento causava problemi se l’istanza del programma era scaduta. Ciò causava il mancato funzionamento dell’espansione del modulo e l’impossibilità per gli allievi di avviare il lettore ed esplorare il contenuto. Questo problema è stato risolto.

**Problemi di traduzione nell’applicazione per gli Allievi**

Gli utenti di Learning Manager riscontravano alcuni problemi di conversione nell’applicazione per gli allievi. Questi problemi sono stati risolti.

**Problemi relativi all’iscrizione a un’abilità**

In alcuni casi, gli Allievi non riuscivano a iscriversi a una nuova abilità. Questo problema è stato risolto.

+++

+++Aggiornamento 29

Data di pubblicazione: 9 aprile 2017

### Nuove funzioni {#newfeatures}

Per un elenco di nuove funzioni e miglioramenti nella versione di aprile di Learning Manager, fai riferimento alla sezione [Novità](../whats-new.md).

**App per Allievi basata su widget**

Utilizza i widget nella home page per gestire corsi, abilità e obiettivi. Utilizza la barra di ricerca per eseguire una ricerca nell’intero LMS per oggetti di apprendimento, cataloghi, abilità, note e discussioni

Per informazioni dettagliate sulla nuova home page, consulta [Home page Allievo in Learning Manager](../learners/feature-summary/getting-started-learner.md).

**Impostazioni Amministratore per il dashboard Allievo**

In qualità di Amministratore, puoi controllare la home page dell’Allievo attivando e disattivando diversi widget.

**App mobile Learning Manager per Allievi**

La nuova applicazione Learning Manager per dispositivi mobili consente agli allievi di utilizzare l’app per iscriversi ai corsi e seguirli. L’app può essere utilizzata anche per gestire i dashboard.

Per ulteriori informazioni sull’utilizzo di Learning Manager su dispositivi mobili, consulta [Applicazione di Learning Manager per allievi per dispositivi mobili](../learners/feature-summary/ipad-android-tablet-users.md#main-pars_header_1451175907).

**Contrassegno di partecipazione tramite codice QR**

Utilizza il codice di scansione QR per contrassegnare la tua partecipazione alle sessioni in aula mediante i tuoi dispositivi mobili.

**Ruolo Istruttore**

Learning Manager introduce ora gli Istruttori per moduli. Gli Istruttori possono gestire le sessioni del modulo, compresa la durata, il luogo e il limite di posti disponibili per i moduli loro assegnati.

Per visualizzare informazioni dettagliate sugli Istruttori, consulta [Istruttori in Learning Manager](../instructors/feature-summary/getting-started.md#main-pars_header).

**Account condivisi tra pari**

Se sei un Amministratore puoi creare Account condivisi tra pari con le persone con cui desideri condividere le postazioni acquistate.

Per sapere come creare e gestire gli account condivisi tra pari, consulta [Account condivisi tra pari](../administrators/feature-summary/peer-account.md#main-pars_text).

**Offerte di equivalenza del corso**

Utilizza l&#39;opzione **[!UICONTROL Aggiungi nuova lingua]** quando aggiungi un modulo o un corso per renderlo disponibile in più lingue e formati.

**Trascrizione Allievo**

Learning Manager offre ai Manager e agli Amministratori la possibilità di scaricare i dati di trascrizione per tracciare la cronologia di apprendimento dei singoli utenti, nonché dei team.

**Integrazione con altri fornitori di contenuto**

Learning Manager ha introdotto tre nuovi connettori in questa versione, in modo che gli Allievi possano accedere e utilizzare i corsi dei seguenti fornitori di contenuti: Lynda.com, getAbstract e Harvard ManageMentor.

Per sapere come configurare e utilizzare ciascuno di questi connettori, consulta [Connettori](../integration-admin/feature-summary/connectors.md#main-pars_header).

**ID univoco per gli oggetti di apprendimento**

Durante la creazione di oggetti di apprendimento, ora gli Autori e gli Amministratori possono specificare ID univoci per corsi, programmi di apprendimento o certificazioni. Se desideri attivare l’ID univoco durante la creazione di un oggetto di apprendimento, fai clic su Impostazioni > Generale. Seleziona la casella di controllo Abilita accanto all’opzione ID oggetto di apprendimento univoco.

**Bacheca di discussione per gli Allievi**

Utilizza la bacheca di discussione nei corsi per interagire con gli altri allievi e gli Istruttori. Come Allievo, puoi visualizzare tutti i post per i corsi. Tuttavia, puoi inoltre eliminare solo i post inseriti. Per ulteriori informazioni sulla bacheca di discussione, vedere [Visualizzazione e partecipazione alle discussioni](../learners/feature-summary/courses.md#main-pars_header_1772461149).

### Miglioramenti {#Enhancements-3}

**X di Y corsi**

I criteri di completamento per gli oggetti di apprendimento, come corsi, certificazioni e piani di apprendimento possono essere impostati in modo che gli Allievi debbano completare solo X di Y moduli o corsi. Gli Autori possono impostare in modo analogo i criteri di completamento per le certificazioni e i piani di apprendimento.

Per ulteriori informazioni su questa funzionalità, consulta [Criteri di completamento del corso](../learners/feature-summary/courses.md#main-pars_image_1164377098).

**Moderazione del corso**

Gli Amministratori ora ricevono notifiche ogni volta che un Autore modifica o aggiorna i moduli e ripubblica un corso.

**Impostazioni Amministratore per la reimpostazione dei moduli**

Ora gli Amministratori hanno la possibilità di configurare l’opzione Ripristina modulo per consentire agli Allievi di reimpostare un corso non completo o non riuscito.

**Catalogo report**

Quando crei report in Learning Manager, ora puoi generare report e grafici per i cataloghi.

**Miglioramenti al piano di apprendimento**

Gli Amministratori possono ora creare i piani di apprendimento dei tipi alla data. Con il piano di apprendimento alla data, un Amministratore può specificare il nome dell’evento, scegliere la data per l’evento e selezionare il gruppo di utenti a cui appartiene l’evento.

**Messaggi di iscrizione specifici per il corso**

Gli Amministratori possono ora configurare e inviare i messaggi di iscrizione specifici per il corso tramite e-mail, agli Allievi.

**Annunci Sticky**

In qualità di Amministratore, puoi ora attivare la funzionalità Sticky per gli annunci.

**Supporto per URL negli annunci** 

Puoi aggiungere URL come annunci inserendo l’URL in HTML.

**Aggiunta di nuovi tipi di distribuzione (corsi)**

Adobe Learning Manager ora consente di aggiungere i tipi di distribuzione per i tuoi corsi.

**Miglioramenti al ruolo di Autore**

Gli Autori precedenti potevano solo creare moduli e corsi. Ora, gli Autori hanno inoltre la possibilità di creare certificazioni e programmi di apprendimento per gli Allievi.

**Ruolo Autore a utenti esterni**

Come Amministratore, ora puoi assegnare ruoli Autore a utenti esterni.

**Più Autori**

Learning Manager ora consente a più Autori di modificare contemporaneamente lo stesso gruppo di contenuti.

**Miglioramenti Adobe Connect**

Ora puoi configurare un singolo URL Adobe Connect con più account Learning Manager.

**Supporto per nuove lingue**

Il supporto per il giapponese, portoghese brasiliano e italiano è disponibile da questa versione.



+++

+++Aggiornamento 28

Data di pubblicazione: 30 gennaio 2017

### Problemi risolti {#IssuesFixed-6}

#### Impostazioni account {#accountsettings}

Quando facevi clic come Amministratore su Profilo esterno e sceglievi Azioni > Modifica profilo, non venivano elencati tutti i profili. Questo problema è stato risolto.

#### Ciclo di vita del corso {#courselifecycle}

* Quando avvii un corso creato utilizzando lo strumento di e-learning della libreria Biz, l’azione &quot;Riprendi&quot; non funzionava. Questo problema è stato risolto.
* Alcuni utenti non riuscivano ad avviare un corso su iPad mediante il collegamento del corso in Annunci. Questo problema è stato risolto.
* Quando facevi clic sul pulsante Continua nel programma degli allievi, non riuscivi ad accedere ai corsi in ordine. Questo problema è stato risolto.
* L’etichetta di panoramica del corso per i corsi nel programma per allievi non era nella posizione corretta. Questo problema è stato risolto.

#### App per gli allievi {#learnerapp}

* Nel dispositivo, se aprivi un’immagine di annuncio nella modalità a schermo intero, non riuscivi a tornare all’applicazione. Questo problema è stato risolto.
* Il contenuto di Tincan caricato da Captivate non veniva riprodotto in modalità online nei sistemi operativi Android e iOS. Questo problema è stato risolto.

#### Report corso {#coursereports}

In Learning Manager venivano generati report di trascrizione degli allievi errati quando il corso disponeva di più versioni di moduli. Questo problema è stato risolto.

#### Livello API {#apilayer}

Ogni volta che tentavi di recuperare informazioni sulla versione del modulo utilizzando AP/corsi/{coursesid}, si verificava un errore. Questo problema è stato risolto.

+++

+++Aggiornamento 27

Data di pubblicazione: 23 dicembre 2016.

### Nuove funzioni {#Newfeatures-1}

Adobe consente alle aziende di migrare i dati e il contenuto di formazione dal sistema di gestione dell’apprendimento (LMS) esistente all’applicazione LMS di Learning Manager.

Learning Manager fornisce i modelli e gli strumenti necessari in modo che l’Amministratore di integrazione dell’organizzazione sia in grado di configurare ed eseguire le attività di migrazione.

Per ulteriori informazioni sulla funzionalità di migrazione, consulta il [manuale della migrazione](../integration-admin/feature-summary/migration-manual.md)

### Miglioramenti {#Enhancements-4}

**Registrazione utente**

In qualità di Amministratore, puoi ora aggiungere i nomi di dominio specifici durante l’aggiunta di utenti esterni. Quando gli allievi accedono all’account, possono inserire gli indirizzi e-mail solo con gli stessi nomi di dominio.

Puoi inoltre inviare i collegamenti di verifica e-mail all’e-mail degli utenti quando si registrano all’account. Per ulteriori informazioni su questo miglioramento, consulta [Aggiungere utenti/gruppi di utenti](../administrators/feature-summary/add-users-user-groups.md#main-pars_header_1217981931).

**Lettore Fluidic**

Il lettore Fluidic consente ora di modificare la velocità di riproduzione. Puoi scegliere tra cinque variabili di velocità disponibili. Il lettore Fluidic consente inoltre di controllare le impostazioni volume quando si segue un corso.

Come Allievo, puoi inoltre saltare avanti o indietro di 10 secondi grazie alle nuove icone su ogni lato del pulsante di riproduzione nel lettore Fluidic. Per ulteriori informazioni su questi miglioramenti, consulta [Lettore Fluidic](../learners/feature-summary/fluidic-player.md).

I miglioramenti del lettore Fluidic sono applicabili unicamente ai video.

+++

+++Aggiornamento 26

Data di pubblicazione: 06 dicembre 2016.

### Miglioramento {#enhancement}

Nell’ambito di questo aggiornamento, Learning Manager fornisce un endpoint [PATCH/users/{id}] (<https://learningmanager.adobe.com/docs/Learning> Managerapi/v1/#!/user/patch_users_id) per aggiornare gli utenti in un&#39;applicazione. Puoi accedere a questo endpoint API nel ruolo di Amministratore. Utilizzando&#x200B;**&#x200B;**&#x200B;questo endpoint puoi aggiornare le seguenti informazioni degli utenti di Learning Manager:

* Nome
* E-mail
* Profilo
* Ruolo
* Manager

### Problema risolto {#issuefixed}

**Lettore Fluidic**

Quando seguivi un corso sviluppato in Captivate utilizzando la variabile `code cpQuizInfoStudentName`, il nome dello studente non veniva visualizzato come previsto. Questo problema è stato risolto.

+++

+++Aggiornamento 25

Data di pubblicazione: 17 novembre 2016.

### Miglioramenti {#Enhancements-5}

**Cataloghi condivisi**

La funzionalità del catalogo condiviso consente agli Amministratori degli account di condividere o acquisire i cataloghi con gli oggetti di apprendimento. Come estensione di questo catalogo condiviso supportiamo la propagazione degli aggiornamenti agli oggetti di apprendimento come Distintivi, Abilità, Moduli, Corsi, Programmi di apprendimento, Certificazioni e Risorse formative.

Per ulteriori informazioni su questa funzionalità, consulta la [Guida ai cataloghi condivisi](../administrators/feature-summary/catalogs.md#propagation)

**Feedback L1 e L3**

* La finestra di dialogo di feedback L1 viene visualizzata appena un Allievo completa la frequenza di un corso. Inoltre, l’Allievo riceve una notifica in merito al completamento del feedback L1.
* È stata fornita un’opzione per aggiungere domande descrittive nella funzionalità di feedback L1 e L3. Gli Amministratori possono aggiungere queste domande descrittive agli allievi. Tutto questo viene aggiunto al set di domande predefinito fornito da Learning Manager. Puoi aggiungere due domande descrittive per feedback L1 e una domanda descrittiva per feedback L3.\
  Per ulteriori informazioni su questa funzionalità, consulta la [Guida alle domande descrittive per feedback L1 e L3](../administrators/feature-summary/courses.md#descriptive)

**Esportazione utenti**

* Sulla base di una richiesta di alcuni utenti enterprise di grandi dimensioni, è stata creata una nuova opzione che consente di scaricare l’elenco di tutti gli utenti dell’account principale di Learning Manager. Nell&#39;accesso come Amministratore, fai clic su **[!UICONTROL Utenti]** nel riquadro a sinistra e seleziona **[!UICONTROL Esporta dati utente]** per scaricare l&#39;elenco di utenti come foglio Excel.

### Problemi risolti {#Issuesfixed-1}

**Iscrizioni ai corsi**

* In alcuni casi, quando un Amministratore tentava di visualizzare le iscrizioni ai corsi utilizzando la scheda allievi, alcuni dei nomi degli allievi iscritti non venivano visualizzati. Questo problema è stato risolto.

**Aggiunta di corsi**

* Quando aggiungevi un’abilità al corso, se un Autore aggiungeva una funzionalità con uno spazio vuoto alla fine del nome, si verificava un errore e il corso non veniva salvato. Questo problema è stato risolto.

**Utilizzo dei corsi**

* In un corso ordinato, alcuni Allievi non erano in grado di passare da un modulo a un altro durante l’utilizzo del corso stesso poiché i moduli non venivano contrassegnati come completati. Questo problema è stato risolto.
* In un corso ordinato, gli allievi non potevano passare da un modulo all’altro all’interno del sommario in modalità Normale e Rivedi. Questo problema è stato risolto.

**Lettore Fluidic**

* In alcuni casi, quando un utente caricava il contenuto del modulo con fotogrammi/diapositive nascosti, il sommario nel riquadro a sinistra visualizzava i fotogrammi/diapositive nascosti. Questo problema è stato risolto.

**Report**

* Il tempo necessario per caricare i report è maggiore nell’aggiornamento più recente di Learning Manager. Questo problema è stato risolto.

+++

+++Aggiornamento 24

Data di pubblicazione: 12 ottobre 2016.

### Miglioramenti {#Enhancements-6}

**Report corso**

* Per gli account Learning Manager con identificatore unico universale (UUID) abilitato, l’UUID viene visualizzato nel report di iscrizione a un corso, nelle trascrizioni degli allievi e nei report Punteggio quiz.

### Problemi risolti {#Issuesfixed-2}

**Risorse formative**

* In alcuni casi, quando un Allievo cerca di passare dalla scheda Apprendimento > Risorse formative ad Apprendimento > Corsi, i corsi non venivano caricati correttamente nella scheda Apprendimento > Corsi. Questo problema è stato risolto.

**Aggiunta di utenti**

* In alcuni casi, quando veniva aggiunto un utente singolo all’applicazione Learning Manager, l’utente non riceveva la notifica e-mail. Questo problema è stato risolto.
* Gli Amministratori non riuscivano a scaricare il file CSV se il processo di caricamento dei file CSV non andava a buon fine. Questo problema è stato risolto: ora gli Amministratori possono scaricare il file CSV più recente, anche se il processo di caricamento non va a buon fine.
* Se un file CSV viene importato dopo la modifica delle informazioni di un utente che si è iscritto in modo autonomo, questi dati non venivano visualizzati nell’interfaccia utente dell’Amministratore. Questo problema è stato risolto.

**Report corso**

* In alcuni casi, i punteggi di quiz non venivano visualizzati per i corsi, anche se i punteggi comparivano nelle trascrizioni degli Allievi. Questo problema è stato risolto.

**Report di iscrizione**

* In alcuni casi, i report di Excel di iscrizione degli Allievi non venivano scaricati per gli oggetti di apprendimento. Questo problema si verificava ogni volta che venivano utilizzati caratteri speciali o non ASCII nel nome degli oggetti di apprendimento. Questo problema è stato risolto.

**Accesso utente**

* Durante l’impostazione di una password nella fase di registrazione o di ripristino, se la password non rispettava i criteri, non veniva visualizzato alcun messaggio di errore. Questo problema è stato risolto.

**Efficacia del corso**

* Nel ruolo di Allievo, l’efficacia del corso veniva visualizzata come una delle opzioni di filtro **Ordina per** anche quando un Amministratore aveva disattivato l’efficacia dei corsi per gli allievi. Questo problema è stato risolto.

**Certificazioni**

* Quando un Amministratore rimuove gli allievi da una certificazione ricorrente, si verificava un errore e l’applicazione di Learning Manager si bloccava. Questo problema è stato risolto.

**Report**

* Quando un Amministratore tentava di generare un report di certificazione con l’opzione **Fino alla data**, gli utenti inattivi non venivano visualizzati nel report. Questo problema è stato risolto.
* Quando un Amministratore faceva clic sul collegamento Report corso nella scheda Report > I miei report, veniva visualizzata una finestra a comparsa senza il pulsante Chiudi. Questo problema è stato risolto.

**Lettore Fluidic**

* Durante l’anteprima dei corsi come Amministratore o Autore, quando un utente sceglie la modalità a schermo intero nel lettore Fluidic, la schermata appare vuota. Questo problema è stato risolto.

**Supporto multilingue**

* Al posto dei caratteri cinesi venivano visualizzati dei punti interrogativi in risposta alle chiamate API degli utenti. Questo problema è stato risolto.

**Livello API**

* Ogni volta che un utente tentava di recuperare l’ID catalogo predefinito mediante l’API get/catalog/catalog Id, si verificava un errore. Un esempio di ID catalogo predefinito è “970_predefinito”. Questo problema è stato risolto.

**Interfaccia utente**

* Alcuni errori ortografici secondari sono stati corretti nell’interfaccia utente dell’applicazione di Learning Manager per il ruolo di Allievo.

+++

+++Aggiornamento 23

Data di pubblicazione: 19 settembre 2016.

### Problemi risolti {#Issuesfixed-3}

**Trascrizioni allievi**

* In alcuni casi, se erano presenti più di venti allievi inattivi/allievi eliminati in un account, gli allievi inattivi oltre i primi venti non venivano visualizzati nell’elenco a discesa della ricerca nella finestra di dialogo delle trascrizioni degli allievi. Questo problema è stato risolto.
* Se un account per utenti esterni era scaduto, gli utenti non venivano elencati nella trascrizione dell’Allievo generata. Questo problema è stato risolto.

**Cataloghi**

* Alcuni dei clienti riscontravano un problema relativo alla visualizzazione dei gruppi di utenti in un catalogo. Anche se erano presenti più di venti gruppi di utenti in un catalogo, ne venivano visualizzati solo 20. Il problema è stato risolto facendo in modo di poter visualizzare 200 gruppi di utenti in una pagina.

+++

+++Aggiornamento 22

Data di pubblicazione: 13 settembre 2016.

In questa versione dell’aggiornamento, sono stati risolti alcuni problemi di progettazione del prodotto backend per migliorare l’esperienza dei clienti.

### Problemi risolti {#Issuesfixed-4}

* Si verificava un problema relativo all’esportazione dei dati del modulo nelle trascrizioni degli allievi che causava un’esportazione non corretta dei dati stessi. Questo problema è stato risolto.
* Se un utente utilizzava un’estensione ID e-mail con più di quattro caratteri, essa non era supportata. Ad esempio, se un ID e-mail è <abcd@company.world>, non è supportato poiché l’estensione &quot;world&quot; contiene più di quattro caratteri. Abbiamo corretto il problema in modo da supportare le estensioni con più di quattro caratteri.

+++

+++Aggiornamento 21

Data di pubblicazione: 01 settembre 2016.

### Miglioramenti {#Enhancements-7}

**Efficacia del corso**

Adesso gli Amministratori possono personalizzare la funzione di efficacia del corso o del programma di apprendimento in modo da nascondere il punteggio di efficacia dalla vista degli Allievi.

**Aggiungi utenti esterni**

Learning Manager ha esteso il limite massimo delle registrazioni autonome esterne a 5 cifre.

**Report**

Tutti i report e gli elenchi di Allievi scaricati per tutti gli oggetti di apprendimento ora mostrano gli utenti eliminati con un’indicazione chiara.

### Problemi risolti {#Issuesfixed-5}

**Ciclo di vita del corso**

In alcuni casi, quando l’autore modificava un corso condiviso per aggiornare un’informazione del modulo modificata, veniva visualizzato un messaggio di avviso secondo il quale l’utente non poteva apportare modifiche durante l’elaborazione di modifiche precedenti. Questo problema è stato risolto.

**Supporto multilingue**

In alcune delle funzioni dell’interfaccia utente di Learning Manager, i messaggi non venivano tradotti o visualizzati all’utente nelle frasi localizzate corrette. Questo problema è stato risolto.

**Aggiunta di utenti**

* Quando un utente eliminato veniva aggiunto nuovamente come un singolo utente, non risultava aggiunto al gruppo “tutti gli utenti” per impostazione predefinita. Questo problema è stato risolto.
* Veniva visualizzato un numero limitato di profili nelle finestre di dialogo relative alla modifica dei profili di iscrizione esterna e iscrizione autonoma. Ora è stata implementata la paginazione.

**Risorse formative**

Ogni volta che un utente accedeva alla scheda Risorse formative nell’account di un Allievo, veniva visualizzato un messaggio di errore simile a “Questa risorsa formativa non esiste più nel tuo elenco” prima che il contenuto venisse caricato. Questo problema è stato risolto.

**Cataloghi**

Durante la creazione del catalogo, quando venivano aggiunti corsi come contenuto al catalogo, il filtro Ordina per non funzionava correttamente. Questo problema è stato risolto.

**Impostazioni**

In Impostazioni account, quando un Amministratore utilizzava un dominio secondario già utilizzato da un altro account, l’Amministratore non riceveva alcun messaggio di errore. Questo problema è stato risolto.

**Livello API**

* Quando la funzione di inclusione del manager veniva utilizzata durante il recupero degli utenti, veniva recuperata l’intera gerarchia dei manager invece del manager diretto dell’utente. Questo problema è stato risolto.
* Quando un utente con autorizzazione area di validità Allievo tentava di aggiungere utenti, veniva visualizzato un messaggio di errore generico. Questo problema è stato risolto; ora l’Allievo riceve il messaggio Accesso non autorizzato.
* Quando un utente tentava di eliminare l’ultimo utente esistente in un gruppo, veniva visualizzato un messaggio di errore 204. Questo problema ora è stato risolto; viene visualizzato un messaggio di errore che indica all’utente che il gruppo deve avere almeno un utente.
* Lo spazio, se presente all’inizio del nome, veniva eliminato quando il nome utente veniva visualizzato nell’API GET/users. Questo problema è stato risolto.
* Quando gli Amministratori tentavano di recuperare tutti i corsi, venivano restituiti anche i corsi bozza, che dovrebbero rimanere visibili solo all’autore. Questo problema è stato risolto; ora i corsi bozza non vengono restituiti.

**Integrazione Adobe Connect**

* In alcune istanze di Adobe Connect basate su sessioni in aula virtuale, la frequenza non veniva registrata automaticamente dopo la sessione. Questo problema si verificava solo quando un ID di login veniva utilizzato da un istruttore al posto dell’ID e-mail per l’accesso. Questo problema è stato risolto.
* In alcuni casi, il nome dell’istruttore veniva visualizzato più volte nell’elenco degli istruttori durante la creazione di un modulo aula virtuale basato su Adobe Connect. Questo problema è stato risolto.

+++

+++Aggiornamento 20

Data di pubblicazione: 22 agosto 2016.

### Miglioramenti {#Enhancements-8}

**Livello API**

Nell’ambito dell’aggiornamento sono state aggiunte le seguenti nuove API per soddisfare alcune delle richieste dei nostri clienti:

1. POST Users
1. DELETE Users
1. GET userGroups
1. GET userGroups /{id}
1. DELETE userGroups /{id}/Users
1. POST userGroups /{id}/Users
1. GET /users/userId/userGroups

Abbiamo inoltre migliorato il modello utente esistente con le seguenti aggiunte:

1. Il modello per i manager viene aggiunto come relazione con il modello Utente
1. userGroupId viene aggiunto come nuovo parametro a GetUsers

**Trascrizione Allievo**

Quando un utente generava la trascrizione dell’Allievo per un allievo, veniva visualizzata una finestra a comparsa per un periodo brevissimo, per poi sparire senza richiedere alcuna azione da parte dell’utente. È stata migliorata l’esperienza dell’utente grazie a una finestra a comparsa che mette in pausa e richiede all’utente di fare clic su OK.

**Integrazione Adobe Connect**

L’ID di login viene fornito come nuovo campo facoltativo nelle impostazioni di integrazione di Adobe Connect per gli utenti che non utilizzano il proprio ID e-mail per effettuare il login.

### Problemi risolti {#Issuesfixed-6}

**Report corso**

* Quando un modulo del corso era costituito da domande aperte o di tipo sondaggio, al momento dell’esportazione veniva visualizzato un report del punteggio del quiz vuoto. Questo problema è stato risolto.
* In alcuni casi, il report del punteggio del quiz non veniva caricato quando un utente utilizzava il collegamento Esporta punteggio quiz. Questo problema è stato risolto.

**Creazione di corsi**

La pagina delle impostazioni corso nel ruolo Autore non veniva visualizzata ogni volta che un’abilità associata a quel corso veniva ritirata dall’Amministratore. Questo problema è stato risolto.

**Iscrizione intelligente**

Il campo di ricerca non supportava i caratteri speciali come input; di conseguenza i risultati della ricerca non venivano visualizzati. Questo problema è stato risolto.

+++

+++Aggiornamento 19

Data di pubblicazione: 11 agosto 2016.

### Miglioramenti {#Enhancements-9}

**Iscrizione intelligente**

Le prestazioni del motore di ricerca sono state migliorate in modo da produrre risultati di ricerca più precisi.

**Integrazione Adobe Connect**

Il processo di richiesta di verifica/autenticazione dell’integrazione è stato migliorato nell’applicazione di Learning Manager.

### Problemi risolti {#Issuesfixed-7}

**Aggiunta di utenti**

* Quando era presente un numero elevato di utenti di Learning Manager, si verificava un ritardo nel caricamento degli utenti e delle pagine dei gruppi di utenti. Questo problema è stato risolto.
* Dopo che l’amministratore aveva completato il caricamento del file CSV con i nuovi utenti, l’elenco di utenti della pagina non veniva aggiornato con i nuovi utenti fino a quando la pagina non veniva aggiornata. Questo problema è stato risolto.
* A volte, dopo l’importazione degli utenti mediante CSV, il valore dell’ID utente nella pagina veniva sostituito con l’ID e-mail. Questo problema è stato risolto.

**Creazione di gruppi di utenti**

In alcuni casi, il numero degli utenti non veniva visualizzato nella pagina dei gruppi di utenti predefinita di Learning Manager. Questo problema è stato risolto.

**Trascrizione Allievo**

I valori degli attributi dei campi attivi non venivano visualizzati correttamente nelle trascrizioni dell’Allievo per le certificazioni. Questo problema è stato risolto.

**Condivisione di più account**

In uno scenario in cui un amministratore di account condivideva un catalogo corsi con il destinatario e aggiornava il modulo di verifica o quello precedente alla lavorazione in un momento successivo, il contenuto di tali moduli veniva riprodotto nel modulo dei contenuti per il destinatario. Questo problema è stato risolto.

**Temi e marchio**

Quando un Amministratore cambiava un tema nell’applicazione utilizzando il widget di anteprima Live e modificava il suo ruolo, il widget di anteprima Live non funzionava come previsto nel nuovo ruolo. Questo problema è stato risolto.

**Supporto multilingue**

Quando un Amministratore modificava le impostazioni internazionali dell’applicazione in cinese semplificato o spagnolo, parte del contenuto del menu nel riquadro a sinistra, le istruzioni e i messaggi a comparsa online non venivano visualizzati con parole o frasi di senso compiuto. Questo problema è stato risolto.

**Lettore Fluidic**

* Quando un Autore creava un corso con contenuto AICC o Tin Can e tentava di visualizzare in anteprima il contenuto, il contenuto non veniva riprodotto. Questo problema è stato risolto.
* L’anteprima del modulo non funzionava durante la creazione o la modifica di un corso da parte di un Autore. Questo problema è stato risolto.

**Cataloghi**

Quando un Allievo tentava di accedere a un URL di cataloghi/programmi di formazione direttamente nel browser, veniva reindirizzato ai corsi. Questo problema è stato risolto.

**Integrazione di Salesforce**

* Dopo aver stabilito una connessione Salesforce o FTP, nella pagina della mappa attributi, le frecce a discesa per i campi non venivano visualizzate nei browser IE, Edge e Safari. Inoltre, alcuni dei messaggi a comparsa non venivano visualizzati nei flussi di lavoro. Questo problema è stato risolto.
* In alcuni casi, quando un Amministratore tentava di sincronizzare i dati importati dal file .csv nel connettore FTP, per la sincronizzazione non andava a buon fine e si verificavano voci duplicate. Questo problema è stato risolto.

**Livello API**

* Quando un Amministratore autorizzava l’Allievo esterno tramite l’autenticazione con OAuth, a volte gli Allievi esterni non riuscivano ad accedere all’applicazione. Questo problema è stato risolto.
* Talvolta, quando veniva eseguita una chiamata API per le risorse formative dell’Allievo, veniva visualizzato un errore di accesso non autorizzato. Questo problema è stato risolto.

**Impostazioni**

Nella pagina delle origini dati, quando un orario di pianificazione automatica veniva impostato e salvato, a volte tornava allo stato precedente. Questo problema è stato risolto.

**Creazione report gruppo utenti**

I valori di un gruppo di utenti nel filtro non venivano popolati quando il tipo di report selezionato era Personalizzato. Questo problema è stato risolto.

**Integrazione Adobe Connect**

Per l’integrazione di Adobe Connect veniva visualizzato un titolo non appropriato una volta che la connessione veniva stabilita correttamente. Il testo dell’intestazione della pagina è stato corretto.

**Report**

A volte, anche se l’opzione &quot;mostra dati per valori correnti&quot; è selezionata, i dati più recenti non venivano visualizzati nei report. Questo problema è stato risolto.

+++

+++Aggiornamento 18

Data di pubblicazione: 31 luglio 2016.

## Nuove funzioni e miglioramenti {#newfeaturesandenhancements}

Per un elenco di nuove funzioni e dei miglioramenti nella versione di luglio di Learning Manager, fai riferimento alla sezione [Novità](../whats-new.md).

Alcune delle funzioni migliorate sono elencate di seguito per riferimento.

**Trascrizione Allievo**

Learning Manager fornisce una funzionalità per generare trascrizioni per gli allievi Learning Manager dell’organizzazione. Per ulteriori informazioni, consulta il [contenuto della guida della funzionalità Trascrizioni allievi](../administrators/feature-summary/learner-transcripts.md).

**Esporta distintivo come PDF**

Learning Manager consente di esportare i badge come file PDF. Per ulteriori informazioni, consulta il [contenuto della funzione dei distintivi](../administrators/feature-summary/badges.md).

**Punteggio quiz per i moduli**

Puoi aggiungere il punteggio quiz per l’aula, l’aula virtuale e i moduli di attività.

**Aggiunta di utenti**

* Puoi spostare gli Allievi da un gruppo di registrazione autonoma a un altro.
* Puoi spostare gli utenti da un gruppo esterno a un altro.
* Puoi fare in modo che un utente di un gruppo esterno diventi Manager dello stesso gruppo.
* Dopo l’aggiunta di un gruppo utenti esterni a Learning Manager, puoi inoltre mettere in pausa la procedura di registrazione degli utenti esterni. In qualsiasi momento, puoi sempre revocare il blocco (pausa) scegliendo un&#39;opzione Riprendi.
* Ora puoi modificare il nome e l’ID e-mail degli allievi.

**Iscrizione autonoma**

Gli utenti possono inoltre disiscriversi dagli oggetti di apprendimento, ad esempio corsi, programmi di apprendimento o certificazioni. Tuttavia, l’Allievo non può disiscriversi da un oggetto di apprendimento dopo averlo completato.

**Utilizzo degli oggetti di apprendimento**

Ora gli Amministratori possono contrassegnare un’attività di apprendimento degli Allievi come completata.

**Report**

* Puoi iscriverti a report relativi a corsi, programmi di apprendimento o certificati. Puoi anche iscriverti ai singoli report del corso per dati come il punteggio del quiz e lo stato dell’Allievo. Le iscrizioni verranno consegnate al tuo ID e-mail come registrate nell’account Learning Manager. Puoi anche modificare questo ID e-mail.
* Quando esporti il report di iscrizione alla certificazione, viene esportata anche una nuova colonna denominata **Scadenza**. I dati di questa colonna consentono agli Amministratori di sapere quali allievi non hanno rispettato la scadenza di utilizzo degli oggetti di apprendimento.

**Modelli e-mail**

Ora puoi modificare l’intestazione dei modelli e-mail.

+++

+++Aggiornamento 17

Data di pubblicazione: 15 giugno 2016.

### Problemi risolti {#Issuesfixed-8}

**Aggiunta di utenti**

Quando era presente un numero elevato di utenti di Learning Manager, si verificava un ritardo nel caricamento degli utenti e delle pagine dei gruppi di utenti. Questo problema è stato risolto.

**Creazione di gruppi di utenti**

In alcuni casi, il numero degli utenti non veniva visualizzato nella pagina dei gruppi di utenti predefinita di Learning Manager. Questo problema è stato risolto.

+++

+++Aggiornamento 16

Data di pubblicazione: 10 giugno 2016.

## Problema risolto {#Issuefixed-1}

Alcuni clienti riscontravano problemi quando utilizzavano la funzione Single Sign-On in Learning Manager. Questo problema è stato risolto puntando l’entityId di Learning Manager a un URL (<https://learningmanager.adobe.com>) invece che a una parola chiave. Learning Manager è conforme alla specifica SAML 2.0.

+++

+++Aggiornamento 15

Data di pubblicazione: 25 maggio 2016

### Miglioramenti {#Enhancements-10}

**Programmi di apprendimento/Certificazioni**

* Nell’elenco di iscrizione degli Allievi alle Certificazioni e ai Programmi di apprendimento, vengono visualizzati nome e cognome degli Allievi (nome e cognome). In precedenza veniva visualizzato solo il nome.
* Le abilità con i crediti di livello più alto sono tratte dall’elenco dei corsi nei programmi di apprendimento/certificazioni e visualizzati nelle schede come abilità dei programmi di apprendimento/certificazioni. Se sono presenti più corsi con lo stesso valore di crediti, vengono selezionati in ordine alfabetico. In precedenza, i nomi di abilità per programmi di apprendimento/certificazioni venivano selezionati casualmente da un elenco dei rispettivi corsi.

**Importazione di CSV**

Per la funzione di caricamento automatico dei CSV tramite FTP, gli Amministratori ricevono notifiche e-mail se si verifica un errore durante il caricamento dei file CSV.

**Aggiunta di partner esterni**

Quando gli Allievi esterni visitano la pagina di registrazione usando un URL di profilo esterno, il nome del profilo esterno viene visualizzato nella pagina di registrazione per una migliore identificazione.

### Problemi risolti {#Issuesfixed-9}

**Anteprima e pubblicazione di corsi**

* Nel ruolo Autore, quando esegui l’anteprima di un corso caricato da Captivate come contenuto SCORM+SWF con variabile `code $$cpQuizInfoStudentName$$`, viene visualizzato il valore null per la variabile. Questo problema è stato risolto.
* Quando un corso Relatore con un titolo che contiene l’apostrofo (’) veniva pubblicato e visualizzato in Learning Manager, venivano visualizzati punti interrogativi (???) nel sommario. Questo problema è stato risolto.

**Certificazioni**

* Se una certificazione è associata a un catalogo, quando la certificazione è ricorrente, viene visualizzata in tutti i cataloghi collegati. In precedenza, in alcuni casi gli utenti non visualizzavano le certificazioni ricorrenti nei rispettivi cataloghi.
* Durante la creazione delle certificazioni, se un amministratore immette un valore di **giorni per il completamento** maggiore o uguale al periodo di validità della certificazione, viene visualizzato un messaggio di avviso. In precedenza, il messaggio di avviso non veniva visualizzato agli amministratori.
* La **validità** della certificazione viene visualizzata agli utenti in termini di mesi. In precedenza, il valore base veniva visualizzato in termini di anni.

**Definizione dei programmi di apprendimento**

La scadenza non viene visualizzata per le istanze predefinite dei programmi di apprendimento. In precedenza veniva visualizzata una scadenza predefinita che poteva non essere rilevante per gli utenti.

**Creazione di corsi tramite i moduli**

* Quando un Autore aggiornava un modulo di un corso misto, la pagina di partecipazione non veniva visualizzata nel ruolo di Amministratore. Questo problema è stato risolto.
* Quando un nome di istanza del corso conteneva i due punti (:), l’azione di esportazione per l’elenco degli allievi non andava a buon fine. Questo problema è stato risolto.

+++

+++Aggiornamento 14

Data di pubblicazione: 04 maggio 2016

### Miglioramenti {#Enhancements-11}

**Cataloghi**

Quando un Allievo accede al catalogo, le schede si attivano in base alla disponibilità degli oggetti di apprendimento, nel seguente ordine: 1. Corsi 2. Programmi 3. Certificazioni e 4. Risorse formative. Ad esempio, se i corsi non sono disponibili nella scheda Corsi per tale Allievo, si attiva l’oggetto di apprendimento successivo, ovvero Programmi se sono disponibili programmi di formazione.

**Impostazioni account**

Un’opzione di commento viene fornita nella finestra di dialogo di conferma della disattivazione dell’account quando un Amministratore sceglieva di disattivare un account.

### Problemi risolti {#Issuesfixed-10}

**Esportazione di report**

* L’esportazione di un elenco di Allievi non andava a buon fine quando un gruppo di utenti di grandi dimensioni veniva iscritto a un programma di apprendimento. Questo problema è stato risolto.
* Quando un corso ha due istanze con lo stesso nome e il nome dell’istanza è lungo, due fogli di lavoro non venivano creati nel file Excel esportato. Questo problema è stato risolto.

**Iscrizione in serie**

Quando un elevato numero di Allievi veniva registrato negli oggetti di apprendimento quali programmi di apprendimento, corsi, certificazioni, risorse formative e piani di formazione, la registrazione non andava a buon fine. Questo problema è stato risolto.

+++

+++Aggiornamento 13

Data di pubblicazione: 20 aprile 2016

### Problemi risolti {#Issuesfixed-11}

**Creazione di corsi tramite i moduli**

Quando veniva caricato un contenuto del modulo con un nome file lungo, si verificavano problemi relativi all’aspetto dei pulsanti. Inoltre, il caricamento del modulo e le opzioni di eliminazione non funzionavano correttamente. Questo problema è stato risolto.

**Importazione di CSV**

A seconda delle richieste da parte di clienti degli Stati Uniti, il tempo di caricamento automatico di file FTP CSV è stato modificato da mezzanotte GMT a mezzanotte PST.

**Esportazione di report**

L’esportazione di dati di iscrizione non riusciva se uno degli Allievi iscritti veniva eliminato dopo avere frequentato il corso. Questo problema è stato risolto.

**Modelli e-mail**

* La parola **partner,** utilizzata per rappresentare gruppi esterni,**&#x200B;**&#x200B;è&#x200B;**&#x200B;** rimossa dal corpo e dal titolo dei modelli di posta elettronica. I gruppi esterni non vengono necessariamente chiamati partner.\
  **Nota:** questo modello aggiornato non viene visualizzato se il modello predefinito è già stato modificato. Per visualizzare il modello aggiornato, fare clic su **Torna all&#39;originale** nella finestra di dialogo **Anteprima modello**.

* L&#39;URL non è cliccabile nell&#39;e-mail ricevuta dagli Amministratori ogni volta che i modelli e-mail **Profilo creato (registrazione autonoma)** e **Profilo creato (Esterni/Partner)** vengono modificati. Questo problema è stato risolto.

+++

+++Aggiornamento 12

Data di pubblicazione: 07 aprile 2016

### Miglioramenti {#Enhancements-12}

**Risorse formative**

Creazione di risorse formative tramite un URL. È possibile citare solo un nome di URL nel flusso di lavoro di creazione di risorse formative e creare una risorsa formativa se desideri utilizzare un contenuto online esistente come Risorsa formativa.

**Aggiunta di Allievi**

La modifica dei dati di un singolo utente, ad esempio nome, indirizzo e-mail, profilo e nome del Manager è consentita. Tutti i gruppi utenti corrispondenti vengono aggiornati con i dati dell’utente più recenti.

**Esportazione di report**

Il nome del manager, il nome dell’oggetto di apprendimento e le colonne di valori non specifiche definite dall’utente provenienti dal file CSV vengono aggiunti all’elenco degli Allievi esportato per gli oggetti di apprendimento. In precedenza venivano visualizzati solo i dati di base degli allievi, ad esempio nome, data, e-mail e stato.

**Aggiunta di partner esterni**

L’applicazione di Learning Manager non consente agli utenti esterni di accedere all’applicazione dopo che l’account è scaduto. I partner esterni possono visualizzare il loro stato account nell’applicazione.

**Certificazioni**

Puoi rinnovare le certificazioni in termini di mesi indicando il valore desiderato nel campo **Validità**. In precedenza, il rinnovo della certificazione era consentito solo in termini di anni.

### Problemi risolti {#Issuesfixed-12}

**Annunci**

Nel login come Amministratore, la paginazione non funzionava correttamente in pagina Annunci. Questo problema è stato risolto.

**Programmi e piani di formazione**

* Quando un Allievo cerca di saltare un modulo del corso ordinato in un programma di apprendimento, non veniva visualizzato alcun messaggio di errore. Questo problema è stato risolto. Viene visualizzato il messaggio di errore **Impossibile saltare i moduli**.
* I corsi non venivano aggiunti ai programmi di apprendimento ogni volta che veniva utilizzata la paginazione nell’elenco dei corsi. Questo problema è stato risolto.
* La scheda **Ritirato** veniva visualizzata due volte in Programmi di apprendimento > Istanze. Questo problema è stato risolto.

**Risorse formative**

* Quando un Allievo rimuoveva le risorse formative dalla scheda **Apprendimento**, l’ordinamento **Nome** non funzionava più correttamente fino a quando la pagina non veniva aggiornata. Questo problema è stato risolto.

* Se una Risorsa formativa faceva parte di più corsi, questi ultimi non venivano visualizzati nell’elenco Risorse formative. Questo problema è stato risolto.
* Se un Allievo eseguiva lo zoom avanti o indietro nel browser, la paginazione per l’elenco Risorse formative non funzionava come previsto. Questo problema è stato risolto.

**Fruizione dei corsi**

* Se un Allievo eseguiva lo zoom avanti o indietro nel browser, la paginazione per i corsi non funzionava come previsto. Questo problema è stato risolto.

**Creazione di abilità**

Nel login per gli Allievi, la descrizione comando del nome dell’abilità in **Mappa abilità &#x200B;** non mostrava **&#x200B;**&#x200B;il nome e cognome&#x200B;**&#x200B;** dell’utente. Questo problema è stato risolto.

**Aggiunta di partner esterni**

* Nella pagina di registrazione degli utenti esterni è stato incluso un messaggio di testo simile al seguente: **Gli utenti devono prima registrarsi e creare una password per i login successivi**.

**Notifiche per l’utente**

* Quando un Allievo esterno faceva clic sul collegamento **Apri Note** nella notifica e-mail Rivedi corso, il lettore si apriva ma il pannello delle note non funzionava. Questo problema è stato risolto.
* Quando un Allievo esterno tentava di aprire il modulo di verifica o quello precedente alla lavorazione tramite il collegamento **Apri Note** nella notifica e-mail Rivedi corso, il contenuto delle note non era visibile. Questo problema è stato risolto.

**Creazione di corsi tramite i moduli**

Quando un Amministratore tentava di iscrivere gli utenti a un corso misto contenente un modulo aula scaduto, la finestra di dialogo di iscrizione non veniva visualizzata. Questo problema è stato risolto.

**Esportazione di report**

Se il testo di una domanda contiene più di 255 caratteri ed è abilitato per il formato SCORM 1.2, il report quiz per tali domande non funzionava. Questo problema è stato risolto.

+++

+++Aggiornamento 11

Data di pubblicazione: 15 marzo 2016

### Problemi risolti {#Issuesfixed-13}

**Creazione di corsi tramite i moduli**

* Nell’accesso come Amministratore, quando tentavi di creare una nuova istanza per i corsi dalla scheda **Ritirato**, si verificava un errore. Questo problema è stato risolto.
* Nel login di Amministratore del contenuto localizzato, durante l’iscrizione di allievi a un’istanza di corso, il layout delle schermate di azione e iscrizione risultavano distorte. Questo problema è stato risolto.
* Quando un Autore creava moduli Aula o Aula virtuale, il mese predefinito del calendario visualizzato era gennaio 2015. Questo problema è stato risolto in modo da riflettere la data corrente in modo predefinito.
* Quando un nome di istanza del corso è costituito da una barra o da una barra rovesciata, l’azione di esportazione dell’elenco allievi non andava a buon fine. Questo problema è stato risolto.

**Annunci**

Quando un Allievo passava il mouse su un annuncio video, il cursore veniva modificato in un dito puntato come previsto. Questo problema è stato risolto.

**Notifiche per l’utente**

Quando un Allievo esterno faceva clic sul collegamento **Apri Note** nella notifica e-mail Rivedi corso, il collegamento non funzionava. Questo problema è stato risolto. Questo collegamento consente di aprire il Lettore con note, anche quando l’utente non è connesso a Learning Manager.

**Supporto in francese e tedesco**

Gli URL della guida nella funzione di caricamento CSV puntavano alla guida in linea in inglese. Questo problema è stato risolto.

**Anteprima e pubblicazione di corsi**

Nel login di Autore, quando eseguivi l’anteprima di contenuti Presenter 10 e 11 TinCan API (SWF/HTML), il contenuto non funzionava. Questo problema è stato risolto.

**E-mail personalizzabili**

I nomi dei titoli nei modelli e-mail non erano appropriati. Il contenuto viene aggiornato in questi titoli dei modelli per renderli leggibili.

**Risorse formative**

Nel browser Internet Explorer 11, il nome e l’icona della Risorsa formativa venivano visualizzati in modo distorto nell’anteprima Autore e Amministratore. Questo problema è stato risolto.

+++

+++Aggiornamento 10

Data di pubblicazione: 28 febbraio 2016.

## Nuove funzioni {#Newfeatures-2}

### Risorse formative

Risorse formative è un archivio del contenuto di formazione accessibile agli Allievi senza alcun requisito di completamento o di iscrizione. Gli Allievi possono fare riferimento a queste risorse formative per ottenere assistenza relativa all’esecuzione di qualsiasi attività o attività in un’organizzazione. L’Amministratore può tenere traccia del numero di download per ciascuna risorsa formativa.

Per ulteriori informazioni su questa funzionalità, consulta la [Guida alle risorse formative](../learners/feature-summary/job-aids.md).

### Annunci

Un annuncio è un messaggio multimediale (testo, immagine o video) che un Amministratore può creare e trasmettere a un insieme di utenti definito. Utilizza gli Annunci per motivare gli Allievi a intraprendere una formazione e creare in questo modo una cultura dell’apprendimento.

Per ulteriori informazioni su questa funzionalità, consulta la [Guida agli annunci](../learners/feature-summary/announcements.md).

### Supporto API Tin Can

Adobe Learning Manager supporta la specifica API Tin Can (nota anche come API Experience o xAPI). Puoi caricare e tenere traccia del contenuto compatibile con l’API Tin Can in modo analogo a come si tiene traccia del contenuto SCORM e AICC.

Per ulteriori informazioni, contatta il Team di supporto di Adobe.

### Ordinamento dei corsi

Puoi creare un percorso di apprendimento assegnando un corso di follow-up o qualsiasi attività di apprendimento automaticamente.

Gli eventi per i piani di apprendimento sono stati aggiornati. Sono stati aggiunti un paio di nuovi eventi. Per ulteriori informazioni, fai riferimento alla sezione [Piani di apprendimento](../learners/feature-summary/learning-programs.md).

### Promemoria delle note

Se prendi delle note mentre segui un corso, dopo 15 giorni Learning Manager invia una notifica per ricordarti di rivedere le note prese.

### Gamification a livello di gruppo

Gli Amministratori possono definire l’area di validità della gamification modificando le impostazioni per l’area di validità. Puoi abilitare la gamification in modo selettivo tra utenti, gruppi o posizioni di profilo simili. Per ulteriori informazioni, fai riferimento alla funzionalità [Gamification](../learners/feature-summary/gamification.md).

### Supporto in francese e tedesco

L’applicazione di Learning Manager è disponibile in lingua francese e tedesca. È possibile personalizzare la lingua per feedback, istanze del corso e comunicazioni.

### Miglioramenti {#Enhancements-13}

Sono stati apportati miglioramenti importanti alle funzioni esistenti di Learning Manager. Ecco alcuni dei principali miglioramenti:

### Importazione di CSV

Se elimini gli utenti, non puoi aggiungerli nuovamente all’applicazione tramite l’aggiunta di utenti singoli. Tuttavia, puoi aggiungere nuovamente un utente eliminato tramite la procedura di caricamento dei file CSV. Sono state apportate modifiche importanti alla limitazione dei campi obbligatori nella funzione di caricamento dei file CSV. Per ulteriori informazioni, fai riferimento alle [domande frequenti su CSV](../administrators/add-users-in-bulk.md).

### Visualizzazione di elenchi di corsi

Per impostazione predefinita, è possibile visualizzare i corsi come schede. La visualizzazione in elenchi è stata introdotta in questa versione. Puoi modificare la visualizzazione anche facendo clic sull’icona a tre barre accanto al campo di ricerca.

### Eliminazione di corsi

Ora puoi eliminare i corsi nelle fasi Bozza e Ritirato. Per ulteriori informazioni, fai riferimento alla funzionalità [Corsi](../administrators/feature-summary/courses.md). Se un oggetto di apprendimento viene eliminato, vengono eliminati anche tutti i dati dei report relativi. Se un corso viene eliminato e faceva parte di qualsiasi altro oggetto di apprendimento, viene visualizzato un messaggio appropriato all’utente.

**Programmi e piani di formazione**

Puoi stabilire l’ordine in cui gli utenti possono seguire i corsi all’interno dei programmi di formazione. È possibile eliminare i programmi di apprendimento nelle fasi Bozza e Ritirato. Se un oggetto di apprendimento viene eliminato, vengono eliminati anche tutti i relativi dati di reporting.

**Certificazioni**

È possibile eliminare le certificazioni nelle fasi bozza e ritirata. Se un oggetto di apprendimento viene eliminato, vengono eliminati anche tutti i relativi dati di reporting.

**Valutazione dell’efficacia dei corsi**

Nel login di Amministratore, puoi esportare i dati di feedback L1 e L3 per qualsiasi corso.

**Creazione di corsi tramite i moduli**

Puoi rendere obbligatorio il completamento dei corsi propedeutici prima di poter seguire i corsi.

**Notifiche per l’utente**

Gli utenti ricevono notifiche ogni volta che si iscrivono autonomamente a un programma di apprendimento.

**Moduli classe (ILT)**

Puoi creare corsi in aula per una data già trascorsa. Questa funzione consente agli amministratori aziendali di inserire informazioni relative a corsi in aula anche in Learning Manager e di generare report.

**Esportazione di report**

I report relativi agli Allievi sono stati migliorati. Nei report puoi visualizzare nome, e-mail, stato dell’oggetto di apprendimento, criteri di iscrizione, data di completamento e data di inizio.

**Aggiunta di partner esterni**

Dopo aver iscritto allievi esterni all’account Learning Manager, puoi anche ridurre il numero di allievi, se necessario. Tuttavia, non è possibile ridurre il numero degli allievi oltre il numero di postazioni utilizzato. Come soluzione alternativa, puoi eliminare gli allievi che si sono registrati per primi, quindi iscriverli nuovamente con il numero di postazioni richiesto.

### Problemi risolti {#Issuesfixed-14}

**Partecipazione degli Allievi**

Il foglio delle presenze nella vista Amministratore mostra nome e cognome del dipendente, se disponibile. In precedenza veniva visualizzato solo il nome.

**Programmi e piani di formazione**

Tutti i corsi nei programmi di apprendimento vengono visualizzati nell’ordine desiderato. In precedenza si verificavano problemi relativi all’ordine dei corsi nei programmi di apprendimento. Questo problema è stato risolto.

**Aggiunta di allievi**

Se un utente che si è registrato autonomamente tenta di registrarsi nuovamente tramite la procedura di registrazione autonoma, viene visualizzato un messaggio appropriato. Il formato e il contenuto del messaggio sono fissi.

**Report**

Se si desidera che il contenuto identifichi il tempo impiegato dall&#39;utente per l&#39;utilizzo del contenuto, è possibile identificarlo utilizzando una variabile, `code cmi.core.session_time`. Questa variabile non era impostata in precedenza. Questo problema è stato risolto.

**Creazione di corsi tramite i moduli**

Ogni volta che un modulo di corso esistente viene sostituito da un altro modulo, viene generata una nuova versione. Se il quiz di questo nuovo modulo veniva esportato, si verificava un’eccezione e il report del quiz non veniva generato. Questo problema è stato risolto.

**Modelli e-mail**

Gli errori di ortografia nei modelli e-mail sono stati corretti.

+++

+++Aggiornamento 9

Data di pubblicazione: 09 febbraio 2016.

## Comportamento di uscita aggiornato {#signoutbehaviorupdated}

Quando gli utenti fanno clic su **[!UICONTROL Esci]** in Learning Manager, ora effettuano la disconnessione dall’applicazione di Learning Manager, oltre che dall’Adobe.

+++

+++Aggiornamento 8

Data di pubblicazione: 20 gennaio 2016.

### Miglioramenti {#Enhancements-14}

**E-mail personalizzabili**

* Gli utenti possono modificare la sezione piè di pagina dei modelli e-mail. Puoi personalizzare il piè di pagina in un modello e-mail con il testo desiderato. Il piè di pagina personalizzato viene automaticamente applicato a tutti i tipi di modelli e-mail.

**Fruizione dei corsi**

* Gli oggetti risorsa in modalità anteprima di un corso vengono elencati uno dopo l’altro in una nuova riga. In precedenza vi erano casi in cui le risorse di un corso venivano visualizzate una accanto all’altra su un’unica riga.

**Collegamento diretto agli oggetti di apprendimento**

* È possibile accedere agli oggetti di apprendimento (tranne le certificazioni) mediante un URL diretto. L’opzione **[!UICONTROL Copia URL]** viene visualizzata nei riquadri degli oggetti di apprendimento. Gli utenti possono fare clic su **[!UICONTROL Copia URL]** e incollare il collegamento in una pagina separata del browser per accedere direttamente all’oggetto di apprendimento.

**Creazione di corsi tramite i moduli**

* Durante la creazione di un corso, gli Autori possono organizzare i corsi propedeutici in qualsiasi ordine. In precedenza, questa opzione non era disponibile in Learning Manager.

* Gli Autori possono aggiungere o eliminare i corsi propedeutici nei corsi pubblicati. In precedenza, questa funzione era disponibile solo per i corsi nella fase Bozza.

**Registrazione utente**

* Gli utenti possono accedere a Learning Manager senza alcuna ulteriore verifica tramite URL se l’Adobe ID corrisponde all’ID e-mail di Learning Manager. Durante l’aggiunta degli utenti all’account, l’Amministratore di un’organizzazione fornisce l’ID e-mail di Learning Manager.

**Creazione di un catalogo**

* Nel ruolo Amministratore, mentre crei i cataloghi tramite la finestra di dialogo **Aggiungi oggetti di apprendimento**, i corsi ritirati non vengono visualizzati nell’elenco dei corsi.

**Altre correzioni**

* Nel ruolo Amministratore, nella scheda **Allievi** viene visualizzato nome e cognome degli Allievi. In precedenza veniva visualizzato solo il nome.

+++

+++Aggiornamento 7

Data di pubblicazione: 13 gennaio 2016.

### Problemi risolti {#Issuesfixed-15}

**Fruizione dei corsi**

* Durante l’accesso ai contenuti del corso, la barra di riproduzione del contenuto viene sempre visualizzata sullo schermo. In precedenza si verificava un problema con barra di riproduzione contenuto, che a tratti scompariva dallo schermo.
* Durante l’accesso al contenuto di un corso, se il contenuto prevede una finestra a comparsa che viene visualizzata e richiede agli utenti se desiderano uscire o rimanere nella pagina, scegliendo di rimanere l’utente viene riportato al contenuto. In alcuni scenari, facendo clic sul pulsante Rimani, l’utente usciva dal contenuto del corso.

**Altre correzioni**

* Alcuni problemi relativi alla riproduzione del contenuto sono stati risolti.

+++

+++Aggiornamento 6

Data di pubblicazione: 22 dicembre 2015

### Miglioramenti {#Enhancements-15}

**Dashboard personale**

* Quando si accedeva a corsi, cataloghi e programmi di apprendimento nei ruoli Autore e Amministratore, l’ordine delle schede veniva modificato in **Pubblicato - Bozza - Tutti - Ritirato**. La selezione predefinita è **Pubblicato.**

### Problemi risolti {#Issuesfixed-16}

**Fruizione dei corsi**

* Mentre segui un corso nel ruolo di Allievo, se il lettore viene chiuso tramite il pulsante Indietro del browser o il tasto indietro sulla tastiera, il tempo impiegato per il corso viene registrato nei report. In alcuni casi si verificava un problema per cui tale tempo non veniva registrato nei report.

**Registrazione utente**

* Se un utente immette l’account Learning Manager utilizzando la registrazione autonoma SSO, il nome utente nell’elenco utenti viene visualizzato in modo corretto in base ai record. In alcuni casi, il nome utente non veniva visualizzato correttamente.

**Creazione di corsi tramite i moduli**

* Quando un Autore duplica un corso, i file delle risorse del corso duplicato possono essere eliminati o aggiornati. In alcuni casi, gli utenti riscontravano problemi nell’eliminazione o nell’aggiornamento di risorse da corsi duplicati.

**Creazione di un catalogo personalizzato per un gruppo di utenti**

* Quando utilizzi la finestra di dialogo **Aggiungi oggetti di apprendimento** nel ruolo Amministratore, puoi filtrare i corsi, sceglierne uno e aggiungerlo tramite il pulsante **Aggiungi** nella parte inferiore della finestra di dialogo. In alcuni casi, il pulsante **Aggiungi** non veniva visualizzato per alcuni utenti.

+++

+++Aggiornamento 5

Data di pubblicazione: 11 dicembre 2015

### Problemi risolti {#Issuesfixed-17}

**Accesso utente**

* Quando un utente tenta di accedere all’applicazione Learning Manager senza utilizzare il collegamento di attivazione, il messaggio di errore veniva visualizzato nel formato sbagliato. Questo problema è stato risolto.

**App per tablet**

* Dopo avere installato Learning Manager su un tablet Android o iPhone, non vengono visualizzati messaggi di compatibilità del browser. In precedenza, gli utenti ricevevano un messaggio di compatibilità del browser. Questo problema è stato risolto.

+++

+++Aggiornamento 4

Data di pubblicazione: 09 dicembre 2015

### Miglioramenti {#Enhancements-16}

**Aggiunta di utenti**

* Nel ruolo Amministratore, quando l’Amministratore registra degli utenti o completa l’aggiunta di un singolo utente, viene visualizzato un messaggio che indica il corretto completamento del flusso di lavoro insieme ai passaggi successivi.
* Quando un utente tenta di accedere all’applicazione di Learning Manager direttamente senza utilizzare il collegamento di attivazione dell’utente, viene visualizzato un messaggio di errore che richiede agli utenti di utilizzare il collegamento di attivazione.

**Browser supportati**

* Se l’utente accede all’applicazione di Learning Manager in un browser non supportato, riceve un avviso con l’elenco dei browser compatibili.

### Problemi risolti {#Issuesfixed-18}

**Report**

* Nel ruolo di Amministratore o Manager, quando creavi un report con asse secondario come tempo di apprendimento trascorso, applicavi il filtro Manager e salvavi il report, l’utente non riusciva a scaricare tali report. Ora è possibile scaricare qualsiasi tipo di report.

**Aggiunta di utenti**

* Erano presenti alcuni errori ortografici nel messaggio di avviso visualizzato durante l’abilitazione di Allievi esterni nel ruolo Amministratore. Questo problema è stato risolto.
* Nel ruolo Amministratore, viene visualizzato un messaggio di errore appropriato quando il campo Manager non viene selezionato correttamente durante l’aggiunta di un singolo utente.

**Registrazione utente**

* Il messaggio e-mail di benvenuto ricevuto dai nuovi utenti evidenzia l’importanza di collegare l’Adobe ID con l’ID di Learning Manager per un login corretto.

**E-mail personalizzabili**

* Quando venivano aggiunti più Allievi ai corsi in aula che prevedono sessioni come allegati, alcuni Allievi non ricevevano le notifiche e-mail. Questo problema è stato risolto.
* I messaggi e-mail inviati agli allievi e relativi alle iscrizioni agli oggetti di apprendimento e ad altri eventi ora contengono il nome dell’oggetto di apprendimento specifico nell’oggetto dell’e-mail.

**Altre correzioni**

* I problemi relativi ai collegamenti URL nei modelli e-mail sono stati corretti.
* È ora disponibile il supporto per

   * Da Publish a Learning Manager
   * Supporto del caricamento di contenuto più veloce per la versione CP 8 (è richiesta la patch CP803)

+++

+++Aggiornamento 3

Data di pubblicazione: 26 ottobre 2015.

### Miglioramenti {#Enhancements-17}

**Aggiunta di utenti**

* È stato fornito un collegamento alla guida in linea nella finestra di dialogo Aggiungi utenti > Caricamento CSV, per consentire una migliore comprensione degli utenti durante il caricamento del file CSV.

**Lettore Fluidic**

* Quando veniva caricato il contenuto di un corso di Captivate con dimensioni superiori a 500 MB, tale contenuto non veniva riprodotto nel lettore Fluidic. Questa restrizione è stata rimossa. Al momento, il limite è stato impostato su 2 GB.

**Fatturazione**

* Nel ruolo Amministratore, quando un utente immette il numero di allievi e fa clic su **Effettua ordine**, viene visualizzata una finestra di dialogo che contiene le tariffe di abbonamento annuale e mensile per ciascun utente.

### Problemi risolti {#Issuesfixed-19}

**Creazione di corsi tramite i moduli**

* Durante la creazione di corsi con i moduli di attività, gli autori possono scegliere URL esterni validi anche se contengono percorsi di cartella all’interno dell’URL. In precedenza, gli URL con i percorsi di cartella non erano supportati. Questo problema è stato risolto.
* Se il contenuto del corso è un progetto che veniva caricato con un file zip in Learning Manager e tale file zip conteneva percorsi di cartella, ad esempio Zip > Cartella > Contenuto, questo tipo di contenuto non era supportato. Questo problema è stato risolto.

**App per tablet**

* Quando un utente tentava di scaricare i file delle risorse di un corso nell’app di Learning Manager per Android, i file delle risorse non venivano scaricati. Questo problema è stato risolto.
* Quando si seguiva un corso tramite il lettore Fluidic, se un utente registrava una nota e tentava di scaricarla dal corso in un secondo momento, tale nota non era scaricabile. Questo problema è stato risolto.

+++

+++Aggiornamento 2

Data di pubblicazione: 28 settembre 2015

### Miglioramenti {#Enhancements-18}

**Creazione di corsi tramite i moduli**

* L’applicazione di Learning Manager supporta il caricamento del contenuto SCORM anche se la versione non è presente nel file manifest.xml. Per impostazione predefinita, la versione è considerata 1.2.
* Quando veniva caricato il contenuto di un corso di Captivate con dimensioni superiori a 500 MB, tale contenuto non veniva riprodotto nel lettore Fluidic. Nell’ambito dell’aggiornamento 2, il limite è stato portato a 800 MB.

**Fatturazione**

* Nel ruolo Amministratore, mentre si acquista un’iscrizione tramite la carta di credito, l’utente può scegliere il primo ordine iniziando con 10 Allievi. Il numero minimo di allievi richiesti per il primo ordine è stato ridotto da 100 a 10.

**Registrazione utente**

* Un collegamento URL per creare l’Adobe ID è stato fornito nel messaggio e-mail di benvenuto ricevuto dall’Allievo dopo la registrazione.

**Aggiunta di utenti**

* Nel ruolo Amministratore, l’aggiunta di utenti tramite l’opzione di caricamento di file CSV diretto da un account Exavault non funzionava per alcuni clienti. Questo problema è stato risolto.

### Problemi risolti {#Issuesfixed-20}

**Programmi e piani di formazione**

* Gli Allievi possono iscriversi autonomamente allo stesso programma di apprendimento nell’ambito di più piani di apprendimento. In precedenza questo flusso di lavoro era soggetto ad alcune eccezioni. Questo problema è stato risolto.

**Visualizzazione di classifiche e distintivi**

* Nel ruolo Allievo, dopo avere seguito un corso che contiene un distintivo, l’immagine del distintivo non veniva visualizzata nella mappa dei distintivi della classifica degli Allievi e nel file scaricato. Questo problema è stato risolto.

**App per tablet**

* Viene visualizzata una finestra a comparsa per indicare la disponibilità di un’app Allievo quando l’URL dell’app Allievo viene aperta in un browser su un dispositivo Android.

**Altre correzioni**

* Un problema relativo alla creazione dell’account utente dovuto al supporto dell’archiviazione di rete Akamai è stato risolto.
* Un problema relativo al caricamento del contenuto SCORM 1.2 contenente un file zip con più cartelle è stato risolto.

+++
