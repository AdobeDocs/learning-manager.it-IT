---
title: Novità della versione di aprile 2026 di Adobe Learning Manager
description: Scopri le nuove funzioni, i miglioramenti e gli aggiornamenti importanti nella versione di aprile 2026 di Adobe Learning Manager.
exl-id: 4d2129c4-42d8-446f-8837-879b5c2f42bf
source-git-commit: 47d49f4bbb81db88635b2c115768e15a3818e153
workflow-type: tm+mt
source-wordcount: '20175'
ht-degree: 0%

---

# Aggiornamenti in Adobe Learning Manager

>[!IMPORTANT]
>
>Le funzioni di questa versione sono disponibili in versione beta. Le funzionalità e il comportamento possono cambiare prima della disponibilità generale. Condividi feedback tramite i tuoi usuali canali di supporto Adobe.


Questo documento riassume le nuove funzioni, i miglioramenti e gli aggiornamenti nella versione di aprile 2026 di Adobe Learning Manager. Usalo per pianificare le modifiche per la tua organizzazione e capire cosa è disponibile per Allievi, Amministratori e Autori.

**Per gli Allievi:** il lettore Fluidic ora mostra il nome del modulo successivo e un pulsante Esci chiaro. La lingua del lettore può essere impostata tramite LTI per un’esperienza uniforme su più piattaforme. Il contenuto di Captivate include un sommario unificato, i segni di graduazione di completamento a livello di diapositiva e le esportazioni di note affidabili. Il supporto multilingue è disponibile per risorse formative, domande sull’elenco di controllo e tracce di testo video (VTT). L’Assistente all’intelligenza artificiale consente agli Allievi di ottenere risposte all’interno dell’esperienza di apprendimento.

**Per amministratori e autori:** il connettore Zoom supporta più sessioni VILT simultanee. I corsi condivisi negli account condivisi tra pari visualizzano l’autore reale invece di &quot;Autore esterno&quot;. Gli amministratori possono limitare l’avvio dei moduli. Le date di scadenza degli oggetti di apprendimento sono esposte nelle API degli Allievi. I moduli dell’elenco di controllo supportano il punteggio ponderato, il testo multilingue delle domande e i commenti facoltativi dei revisori. I certificati personalizzati offrono un editor drag-and-drop con campi dinamici e sfondi generati dall’intelligenza artificiale. Experience Builder non connesso consente di creare pagine di apprendimento pubbliche senza richiedere l’accesso.

**Per gli istruttori:** genera codici QR per l&#39;iscrizione e la partecipazione alla sessione dell&#39;istanza. Aggiungi commenti o feedback durante la valutazione dell’elenco di controllo.

**Report e analisi:** il contenuto SCORM può ora segnalare più tentativi di quiz nel report L2. Il calcolo del tempo impiegato per l’apprendimento è stato migliorato nelle Trascrizioni allievi. I report Trascrizione Allievo per gli Amministratori sono stati aggiornati. Sono disponibili miglioramenti della ricerca avanzata.

## Navigazione lettore Fluidic: mostra il nome del modulo successivo

### Panoramica

Questo miglioramento era già incluso nella versione di novembre 2025 di Adobe Learning Manager.

L’azione &quot;Avanti&quot; nel lettore indica cosa succede quando si fa clic visualizzando il nome del modulo o corso successivo e segnalando esplicitamente quando l’Allievo sta per uscire dal lettore.

### Novità

**&quot;Modulo successivo: etichetta {ModuleName}&quot; nel lettore**

L’icona Avanti nel lettore Fluidic ora mostra il nome del modulo successivo nel corso. Ad esempio, Modulo successivo: Lezione 2- Guida introduttiva.

Ciò si applica a tutti i casi in cui l’Allievo si sposta da un modulo all’altro all’interno dello stesso corso.

**Cancella azione uscita nell&#39;ultimo modulo**

Quando l’Allievo si trova sull’ultimo modulo di un corso, viene visualizzato un nuovo pulsante di azione Esci, che indica che facendo clic su di esso il lettore verrà chiuso e tornerà al contesto del corso.

**Comportamento reattivo per contenuti per dispositivi mobili e PDF**

Nelle finestre di visualizzazione più piccole (ad esempio, larghezza ~320 px), l’etichetta Avanti può essere abbreviata o nascosta, mostrando solo l’icona, per evitare la sovrapposizione con i controlli PDF.

Per i moduli PDF, il lettore regola i controlli su una riga separata, in modo che le etichette di navigazione e i controlli PDF non interferiscano tra loro.

**Aggiornamento amministratore > Branding > Anteprima lettore**

L’anteprima del lettore in Admin > Branding ora riflette la nuova etichetta, ad esempio Modulo successivo: Lezione 2. Ciò consente agli amministratori di visualizzare il comportamento di navigazione aggiornato.

### Vantaggi principali

**Navigazione più chiara per gli Allievi**

Gli Allievi non devono più indovinare cosa accadrà quando selezioneranno &quot;Avanti&quot;. L’etichetta specifica chiaramente cosa viene dopo, che si tratti di un modulo o di un corso. Questa riduzione dell’ambiguità aiuta ad attenuare l’esitazione e la confusione, in particolare nel grande pubblico di formazione del cliente in cui molti allievi potrebbero non avere familiarità con le interfacce LMS.

**Percentuali di completamento del corso più elevate**

Il passaggio successivo (modulo successivo: {ModuleName}) e l’aggiunta di un’azione di uscita distinta per il modulo finale riducono la probabilità che gli Allievi abbandonino il corso o trascurino l’ultimo passaggio di completamento.

**Esperienza utente più prevedibile sui vari dispositivi**

Le etichette aggiornate si allineano al comportamento e alle icone Successivo o Precedente su desktop, tablet e dispositivi mobili. I vincoli di layout vengono rispettati nei dispositivi e nei flussi di PDF in modo che i controlli rimangano utilizzabili e accessibili.

Ciò è particolarmente importante per le implementazioni headless in cui il lettore Fluidic è incorporato in un&#39;esperienza di apprendimento personalizzata.

### Casi d’uso

**Portali didattici per clienti e partner (headless o AEM integrato)**

Account che utilizzano Adobe Learning Manager in una configurazione headless, indirizzando gli Allievi da canali di marketing esterni. Questi Allievi:

* Utilizzano spesso contenuti video in sequenze lunghe.

* Ci si aspetta un’esperienza in stile curriculum in cui il sistema indichi chiaramente l’episodio o il modulo successivo.

In questi ambienti, l&#39;etichetta **Modulo successivo:{ModuleName}**:

* Rafforza la natura guidata del viaggio.

* Riduce al minimo il drop-off tra i moduli.

**Corsi di conformità e certificazione con i moduli ordinati**

In scenari regolamentati o con requisiti elevati:

* Gli Allievi devono completare una rigida sequenza di moduli.

* Gli autori spesso disattivano il sommario per evitare di saltarlo.

Qui, viene visualizzato **Modulo successivo:{ModuleName}**:

* Conferma agli Allievi che stanno seguendo la sequenza corretta.

* Rende meno probabile che interpretino in modo errato l&#39;azione successiva e che escano presto.

**Percorsi di apprendimento in cui i corsi si susseguono**

Dove percorsi di apprendimento o equivalenti concatenano più corsi. Questo è utile quando si creano sequenze in stile curriculum per un pubblico numeroso.

**Primo utilizzo per dispositivi mobili**

Per gli Allievi che utilizzano principalmente telefoni o tablet:

* Le etichette aggiornate e il comportamento reattivo garantiscono che la navigazione rimanga comprensibile senza dipendere da icone di chiusura o controlli nascosti.

* Questo è importante per la formazione dei clienti, gli addetti ai lavori o gli Allievi in prima linea che possono accedere ai contenuti in sessioni brevi su dispositivi mobili.

## Connettore Zoom - Creare più sessioni Zoom simultanee

### Panoramica

L’aggiornamento del connettore Zoom migliora il modo in cui Adobe Learning Manager gestisce il corso di formazione VILT (Virtual Instructor-Led Training). In precedenza, gli utenti potevano creare una sola sessione di Zoom alla volta. Con il nuovo aggiornamento, amministratori e autori possono pianificare più sessioni di Zoom contemporaneamente utilizzando l’integrazione standard.

### Novità

#### Supporto per più sessioni Zoom simultanee tramite il connettore

* Il connettore Zoom ora consente di creare più sessioni VILT alla stessa data/ora da ALM.

* La logica di pianificazione non applica più un vincolo di tipo &quot;uno zoom alla volta&quot; a livello di account/connettore.

* Amministratori e autori possono configurare sessioni VILT sovrapposte (ad esempio, aule regionali, tracce parallele o sessioni ripetute per diversi gruppi di partner) senza soluzioni alternative.

#### Le riunioni vengono create utilizzando l’identità Zoom dell’istruttore (non il super amministratore Zoom).

Per supportare in modo sicuro le riunioni simultanee, il connettore è stato aggiornato in modo che:

* Le riunioni con Zoom vengono ora create utilizzando l’indirizzo e-mail dell’istruttore, invece dell’e-mail dell’amministratore con privilegi di Zoom.

* L’account Zoom di ogni istruttore può ospitare le proprie riunioni in parallelo con gli altri istruttori, fatti salvi i limiti del piano Zoom esistente.

**Nota**:

* È ancora supportato un solo istruttore per riunione.

* Se l’indirizzo e-mail di un istruttore viene successivamente aggiornato in Adobe Learning Manager, le riunioni esistenti restano associate all’indirizzo e-mail originale utilizzato al momento della creazione.

#### Non dovrai più incollare manualmente l’URL di Zoom per le sessioni simultanee

In precedenza, quando doveva essere eseguita una seconda o una terza sessione di Zoom contemporaneamente:

* Gli Autori dovevano creare manualmente le riunioni Zoom al di fuori di ALM e quindi incollare l’URL di Zoom join nella configurazione dell’istanza del corso.

* Si tratta di un comportamento soggetto a errori che non ha tratto vantaggio da funzioni di connessione come il tracciamento della frequenza.

Con il connettore aggiornato:

* Tutte le sessioni possono essere create direttamente dall’interfaccia utente di ALM utilizzando il connettore Zoom, anche se si sovrappongono nel tempo.

* Il ciclo di vita delle sessioni (creazione/annullamento) continua a essere gestito centralmente tramite l&#39;integrazione.

### Vantaggi principali

#### Migliore pianificazione VILT su larga scala

Le organizzazioni possono ora:

* Esecuzione simultanea di più aule virtuali basate su Zoom (ad esempio, percorsi paralleli in un vertice virtuale, coorti regionali o sessioni di formazione separate per i partner).

* Evita i colli di bottiglia che in precedenza forzavano gli amministratori a serializzare le sessioni o che si affidavano alla gestione manuale dello zoom.

#### Riduzione del sovraccarico di lavoro per amministratori e autori

Il miglioramento elimina:

* Creazione manuale di riunioni con Zoom esterne a Adobe Learning Manager.

* Copia e incolla gli URL di Zoom in ogni istanza del corso per le sessioni sovrapposte.

* Rischio di collegamenti non configurati correttamente, riunioni errate o monitoraggio di presenze mancate.

Amministratori e Autori possono gestire tutte le sessioni di Zoom da Adobe Learning Manager, utilizzando flussi di lavoro familiari.

#### Migliore allineamento con il provisioning di Zoom e i ruoli di istruttore

Legando le riunioni ai singoli account Zoom del docente:

* Ogni istruttore può operare entro i propri limiti di licenza Zoom.

* Le organizzazioni possono utilizzare il modello di provisioning Zoom esistente (un account per istruttore, per BU, ecc.) continuando a integrarsi completamente con Adobe Learning Manager.

* Evita il collo di bottiglia a punto singolo che comporta l’utilizzo di un utente Zoom condiviso con amministratore privilegiato per tutte le sessioni.

### Casi d’uso

#### Eventi e vertici virtuali a più tracce

I team di formazione dei clienti che eseguono eventi di grandi dimensioni (ad esempio, bootcamp di prodotti, vertici con i partner o settimane di certificazione) possono:

* Configurare più sessioni basate su Zoom nello stesso intervallo di tempo (per tracce o argomenti diversi).

* Puoi gestirli tutti come moduli VILT nei corsi e percorsi di apprendimento Adobe Learning Manager.

* Offre agli Allievi un’esperienza unificata, mentre il connettore gestisce tutta la creazione della riunione Zoom sottostante.

#### Formazione globale per partner e clienti

Le organizzazioni che formano clienti e partner in diverse aree geografiche possono:

* Eseguire sessioni di Zoom separate per EMEA, APAC e Americhe a orari sovrapposti in modo che corrispondano agli orari di lavoro locali.

* Evitate di forzare una singola fascia oraria globale o la configurazione manuale dello zoom per altre coorti.

#### Abilitazione interna

I team di abilitazione interni (vendite, supporto e così via) possono:

* Pianifica sessioni di onboarding parallele o breakout basati sui ruoli (ad esempio, sale Zoom separate per sviluppatori, amministratori e stakeholder aziendali) in ALM.

* Mantenere tutte le sessioni all&#39;interno del modello VILT di ALM per scopi di reporting e conformità, piuttosto che passare parzialmente a riunioni Zoom non gestite.

## Mostrare l’autore originale per i corsi condivisi negli account condivisi tra pari

### Panoramica

Quando un corso viene condiviso tramite il catalogo con un account condiviso tra pari, Adobe Learning Manager attualmente etichetta l’autore come &quot;Autore esterno&quot; nelle viste Allievo, Amministratore e Autore dell’account di ricezione. Ciò può creare difficoltà per gli Allievi e gli Amministratori, in particolare nelle grandi aziende, poiché diventa difficile identificare e contattare il proprietario dei contenuti appropriato quando si verificano problemi o domande.

Questo miglioramento garantisce che le informazioni dell’Autore vengano conservate e rese disponibili per i corsi condivisi negli account condivisi tra pari, anziché essere sostituite da un segnaposto generico.

### Novità

Mostra il nome dell’autore effettivo per i corsi condivisi negli account condivisi tra pari

Per i corsi condivisi tramite cataloghi esterni o condivisi tra pari, il nome dell’autore originale dall’account di origine viene ora visualizzato nell’account di destinazione anziché come &quot;Autore esterno&quot;.

Questo vale per:

* App Allievo (scheda del corso o dettagli del corso).

* Visualizzazioni Amministratore e Autore durante l’anteprima come Allievo.

### Vantaggi principali

#### Visibilità diretta del proprietario per il contenuto condiviso

Gli Allievi e gli Amministratori degli account condivisi tra pari ora possono:

* Scopri chi ha creato il corso, anche quando viene acquisito tramite un catalogo condiviso.

* Evitate l’etichetta generica e inutile &quot;Autore esterno&quot;.

#### Esperienza più coerente con più tenant e account condivisi tra pari

Per i clienti che eseguono scenari multi-tenant o extended-enterprise:

* Lo stesso corso viene visualizzato con un branding autore coerente tra gli account.

* L’esperienza dell’Allievo è allineata alle aspettative dell’account principale (ad esempio, se si visualizza il nome dell’autore dell’account di origine anziché &quot;Autore esterno&quot;).

### Casi d’uso

#### Grande azienda con account condivisi tra pari

L&#39;azienda utilizza ALM con:

* Un account principale a cui appartengono i corsi canonici e

* Account condivisi tra pari che acquisiscono contenuti tramite cataloghi condivisi.

Gli Allievi negli account condivisi tra pari devono sapere quale team aziendale ha creato un corso per indirizzare correttamente domande o suggerimenti di miglioramento.

Con questo miglioramento:

* I corsi condivisi ora visualizzano il nome dell’autore enterprise corretto negli account condivisi tra pari.

* Il carico di supporto interno dell’azienda viene ridotto perché gli Allievi e gli Amministratori locali sanno a chi rivolgersi.

#### Condivisione interna multi-BU

Dove una Business Unit cura l&#39;apprendimento per gli altri:

* Il BU proprietario può essere identificato nel campo Autore in tutti gli account di consumo.

* Gli amministratori L&amp;D locali possono vedere rapidamente se un corso viene gestito localmente o da un altro BU e collaborare di conseguenza.

## Esponi la data di scadenza (ritiro automatico) degli Oggetti di apprendimento nelle API degli Allievi

### Panoramica

Questo miglioramento rende disponibile la data di ritiro automatico di un oggetto di apprendimento (LO) direttamente tramite le API rivolte agli Allievi di Adobe Learning Manager. Quando un corso, un percorso di apprendimento o una certificazione sono configurati con una data di scadenza o ritiro automatico, tali informazioni fanno ora parte dei dati LO restituiti dagli endpoint principali dell’Allievo.

### Novità

#### Nuovo campo per scadenza/ritiro automatico nelle API degli oggetti di apprendimento degli Allievi

* Le API degli LO degli Allievi (ad esempio, gli endpoint che restituiscono gli oggetti di apprendimento all’esperienza dell’Allievo e a piattaforme esterne) ora includono la data di scadenza dell’LO (data di ritiro automatico configurata per tale oggetto di apprendimento).

* Questo campo viene restituito come parte dell&#39;entità LO in risposte quali:

   * Ottieni oggetto di apprendimento (dettagli LO).

   * Dati LO utilizzati per popolare la pagina principale dell’Allievo, il catalogo e i risultati della ricerca.

* Il campo integra l’attuale completamentoScadenza già esistente a livello di istanza; il nuovo campo è specificamente la data di smobilizzo automatico a livello di LO.

#### Disponibilità in esperienze di apprendimento basate su ricerca

Poiché la data di scadenza è esposta come parte della rappresentazione LO basata su ricerca, è ora disponibile ovunque ALM o una piattaforma esterna utilizzi:

* API di ricerca o

* cataloghi e suggerimenti basati sulla ricerca per creare visualizzazioni per gli allievi.

**Ambito ed esclusioni**

Il miglioramento si applica solo alle API degli Allievi.

### Vantaggi principali

#### Esperienza in base alla scadenza degli Allievi in LXP personalizzati

Per le grandi e medie imprese, il LXP personalizzato può ora ottenere informazioni sulla scadenza degli oggetti di apprendimento direttamente da ALM, consentendo loro di:

* Mostra le etichette &quot;In scadenza il {date}&quot; o &quot;In scadenza a breve&quot; sulle schede dei corsi e sulle pagine dei dettagli.

* Comunicare con urgenza in modo più chiaro, così gli Allievi danno priorità ai corsi di formazione che stanno per essere ritirati.

Ciò è particolarmente importante per la conformità o per la formazione sul prodotto vincolata nel tempo, in cui gli oggetti di apprendimento vengono regolarmente aggiornati e le versioni precedenti vengono ritirate.

#### Migliore orientamento per gli Allievi sui corsi di formazione da seguire ora

Rendendo visibile la scadenza dell’LO, l’esperienza dell’Allievo può:

* Evidenzia i corsi ancora validi rispetto a quelli che stanno per essere ritirati.

* Aiuta gli Allievi a evitare di iscriversi a corsi di formazione che non saranno più disponibili o validi nel prossimo futuro.

#### Coerenza con i dati di scadenza di completamento esistenti

In precedenza, le API degli Allievi esponevano già il completamento a livello di istanzaScadenza, ma non la data di ritiro automatico a livello di LO. Con questa modifica:

Sono disponibili i seguenti aspetti della formazione:

* &quot;Entro quando devo completare questa istanza?&quot; (scadenza per il completamento).

* &quot;Fino a quando sarà offerto questo corso di formazione?&quot; (ritiro automatico/data di scadenza).

### Casi d’uso

#### Un&#39;azienda globale con una rigorosa gestione del ciclo di vita dei corsi

Le aziende che ritirano e sostituiscono regolarmente i corsi (ad esempio, aggiornamenti normativi, di prodotto o metodologici) possono:

* Evitare di confondere gli Allievi circa la graduale eliminazione di un corso di formazione.

* Indirizzare gli Allievi verso le offerte più recenti e di lunga durata.

I portali personalizzati e gli strumenti interni possono ora leggere la data di scadenza direttamente da ALM tramite le API degli Allievi.

#### Accademie esterne di clienti o partner

Per la formazione dei clienti e dei partner, le pagine di marketing e i portali spesso enfatizzano la formazione aggiornata.

L’aggiunta di date di scadenza nell’API LO consente ai creatori di esperienze di:

* Nascondere o attenuare i contenuti prossimi al pensionamento.

* Costruisci campagne &quot;Ultima occasione per completare&quot;.

## Supporto multilingue per risorse formative

### Panoramica

Questo miglioramento estende il modello di localizzazione di Adobe Learning Manager alle risorse formative, consentendo agli autori di allegare file di contenuto diversi per lingua a una singola risorsa formativa. Invece di creare risorse formative separate per ogni lingua, gli autori possono ora gestire tutte le versioni localizzate come una risorsa formativa logica.

### Novità

#### Caricamento di contenuti specifici per ogni lingua per le risorse formative

Gli autori possono allegare file diversi per lingua supportata a una singola risorsa formativa, come corsi e altri LO.

L’esperienza di creazione/modifica della risorsa formativa ora supporta:

* Selezione di una lingua.

* Caricamento del file specifico della lingua per la stessa lingua nella stessa entità Risorsa formativa.

#### Gestione coerente della lingua nell’interfaccia utente del lettore e dell’Allievo

Il lettore Fluidic è stato aggiornato in modo che quando un Allievo apre una risorsa formativa, viene visualizzata la variante di contenuto corrispondente alla lingua dell’Allievo (se disponibile).

Gli Amministratori e gli Autori possono visualizzare le risorse formative come singoli oggetti con varianti di lingua, anziché come elementi separati per lingua.

### Vantaggi principali

#### Risorsa formativa unica per tutte le lingue

Gli autori possono evitare di creare risorse formative separate per lingua.

Tutte le varianti della lingua della stessa risorsa formativa (ad esempio, una procedura, un SOP, un PDF dell’elenco di controllo o una guida di riferimento) possono essere gestite in un’unica posizione.

#### Migliore esperienza per gli Allievi globali

Gli Allievi visualizzano automaticamente la risorsa formativa nella lingua preferita, ovvero:

* Meno confusione sulla versione da aprire.

* Riduzione del rischio di accesso a copie fuori dalle impostazioni locali o obsolete.

Ciò è particolarmente utile nelle organizzazioni multilingue in cui la stessa documentazione relativa a processi o prodotti deve essere disponibile in più lingue.

### Casi d’uso

#### Implementazione globale del contenuto di riferimento

Un’azienda deve fornire risorse formative in diverse lingue agli Allievi in tutto il mondo, ad esempio:

* Schede di riferimento del prodotto.

* Elabora elenchi di controllo.

* Supporta i playbook

Invece di creare risorse formative separate come &quot;Product Quick Start - EN&quot;, &quot;Product Quick Start - DE&quot;, &quot;Product Quick Start - JP&quot;, ecc., possono creare una risorsa formativa, allegare file localizzati per ogni lingua e consentire ad ALM di fornire la versione corretta a ciascun Allievo in base alle impostazioni della lingua.

#### Documentazione rivolta ai clienti o ai partner per più mercati

Per le accademie di clienti e partner, le risorse formative possono includere:

* Schede di imbroglio di prodotti

* Guide di integrazione

* Flussi di lavoro di supporto

Con risorse formative multilingue:

* Ogni partner vede la versione localizzata senza essere costretto a scegliere tra voci specifiche della lingua.

* I team di marketing e abilitazione possono gestire una risorsa formativa per argomento in tutte le lingue.

## Imposta la restrizione sull&#39;ora di inizio del modulo

### Panoramica

Il miglioramento consente agli Autori e agli Amministratori di Adobe Learning Manager di definire una finestra temporale durante la quale gli Allievi possono avviare un modulo. Al di fuori della finestra di inizio/fine configurata, il modulo rimane visibile nella struttura del corso, ma gli allievi non possono avviarlo.

Questa funzionalità è fondamentale per gli utenti che necessitano di un controllo più rigoroso per verificare quando determinati contenuti diventano disponibili o non devono più essere avviati, ad esempio in programmi a tempo determinato, corsi di formazione basati su coorti o esercizi sensibili al fattore tempo.

### Novità

Gli Autori possono ora configurare, a livello di modulo all’interno di un corso, una data/ora di inizio e una data/ora di fine che determinano quando agli Allievi è consentito avviare tale modulo. All’interno di questa finestra, il modulo funziona come al solito; prima dell’ora di inizio o dopo l’ora di fine, l’Allievo vede il modulo nella struttura del corso ma non può avviarlo.

La configurazione viene visualizzata nell’interfaccia utente di creazione del corso come controlli di pianificazione aggiuntivi per tipi di modulo specifici, ad esempio contenuti autonomi, quiz o attività. Gli amministratori possono utilizzare questi controlli per creare moduli che si aprono in fasi o per evitare l&#39;avvio tardivo di programmi in cui il contenuto deve essere utilizzato entro un periodo di tempo definito.

#### Vantaggi principali

Il vantaggio principale è la possibilità di controllare quando i moduli sono accessibili. I team di formazione possono sincronizzare la disponibilità dei moduli con eventi reali, quali il lancio di nuovi prodotti, le scadenze normative e i programmi interni. Ciò garantisce che gli Allievi completino i contenuti dei prerequisiti prima di poter accedere ai moduli successivi.

Ad esempio, la coorte 1 può accedere al modulo 2 solo nella settimana 2, mentre il modulo 3 rimarrà bloccato fino alla settimana 3, eliminando la necessità di nascondere e scoprire manualmente i contenuti o di creare versioni del corso separate.

Ciò migliora l’esperienza dell’Allievo: invece di affrontare moduli a cui è tecnicamente possibile accedere ma che non dovrebbero essere in quel momento (o che dovrebbero già essere completati), gli Allievi vedono una struttura del corso in cui i moduli a cui è consentito avviare sono chiaramente allineati alla pianificazione prevista.

#### Casi d’uso

* **Programma di abilitazione basato su coorte**: in questo programma, ogni settimana viene aperto un nuovo modulo. Il contenuto per la Settimana 1 è disponibile immediatamente, mentre la Settimana 2 è visibile ma non può essere avviata fino a una data specificata. La Settimana 3 segue lo stesso processo di controllo. Gli Allievi possono visualizzare l’intero percorso di apprendimento, ma il sistema controlla quando possono effettivamente iniziare ciascun passaggio.

* **Corso di formazione su prodotti o campagne con scadenze precise**: i team di marketing o di prodotto possono creare un modulo di formazione a cui accedere solo quando è attiva una campagna o quando è ancora disponibile una versione specifica di un prodotto. Questa finestra iniziale assicura che gli allievi non inizino un modulo su una versione del prodotto fuori produzione dopo l’ora di fine specificata.

* **Ambienti di valutazione o esame**: le organizzazioni possono aprire un modulo (ad esempio un test) per una breve finestra ben definita (ad esempio, &quot;è possibile avviare l&#39;esame in qualsiasi momento tra il 9:00 e il 12:00 in una data specifica&quot;). Gli Allievi non possono iniziare l’esame al di fuori di tale finestra, il che supporta una pianificazione equa per fusi orari e coorti.

## Controllare la lingua del lettore tramite il parametro LTI personalizzato

### Panoramica

Il miglioramento consente alle piattaforme esterne che utilizzano LTI (Learning Tools Interoperability) di specificare la lingua per i contenuti Adobe Learning Manager al momento del lancio. Invece di dipendere dall’Allievo che deve modificare la lingua nel lettore Fluidic, il consumatore di LTI può inviare un codice della lingua tramite un parametro LTI personalizzato. Adobe Learning Manager utilizzerà quindi questo codice per selezionare la variante della lingua appropriata.

### Novità

Le piattaforme esterne che fungono da consumer LTI possono ora passare un parametro di lingua personalizzato (e le relative impostazioni del lettore) quando avviano il contenuto ALM. ALM legge questo parametro e:

* Imposta la lingua del lettore di conseguenza.

* Avvia la variante della lingua corrispondente del modulo, quando è configurato un contenuto multilingue.

Ciò significa che un Allievo alla prima volta, che seleziona il francese sulla piattaforma esterna, vedrà il lettore e il modulo ALM lanciarsi direttamente in francese, senza dover regolare nulla all&#39;interno di ALM.

Il miglioramento consente inoltre di gestire scenari in cui la piattaforma esterna considera ALM come un lettore di contenuti headless. Ad esempio, consente di nascondere gli elementi di navigazione e il sommario inviando parametri personalizzati aggiuntivi per regolare alcune impostazioni dell&#39;interfaccia utente. Queste impostazioni funzionano in combinazione con il parametro del linguaggio, consentendo alla piattaforma esterna di fornire un&#39;esperienza uniforme e personalizzata mentre si utilizza ancora ALM per la riproduzione e il tracciamento.

### Vantaggi principali

* **Esperienza linguistica coerente nei sistemi**: quando un Allievo seleziona una lingua nel portale esterno, tale scelta viene immediatamente riflessa in ALM. In questo modo, gli allievi non riscontreranno alcuna discrepanza tra la lingua del portale e il corso. Di conseguenza, non dovranno cercare un cambio di lingua all&#39;interno del lettore.

* **Report specifici per la lingua**: nella piattaforma, la selezione della lingua è coerente con ALM, che migliora la precisione delle analisi e il tracciamento degli allievi. Questo allineamento supporta anche le configurazioni in cui i controlli della lingua di ALM sono intenzionalmente disabilitati o nascosti nel lettore Fluidic per corsi specifici. In questi casi, la piattaforma esterna serve come unica fonte di verità per il linguaggio.

### Casi d’uso

* Un caso di utilizzo significativo coinvolge le grandi aziende che utilizzano integrazioni basate su LTI. Gli Allievi si iscrivono prima e selezionano una lingua sulla piattaforma. Quindi avviano le sessioni di formazione ALM tramite LTI. Con questo miglioramento, quando un Allievo seleziona lo spagnolo, il modulo ALM si apre automaticamente in spagnolo. Ciò significa che gli Allievi non devono regolare le impostazioni della lingua in ALM. Inoltre, il reporting basato sulla lingua rimane coerente con ciò che gli Allievi vedono e hanno esperienza in ALM.

* Un&#39;altra applicazione è la distribuzione di esperienze di corso headless all&#39;interno di un portale per clienti o partner. In questa configurazione, il portale può incorporare il contenuto ALM utilizzando un iframe, mentre tutta la navigazione e l&#39;esperienza utente della lingua (UX) sono gestite al di fuori di ALM. Utilizzando i parametri LTI personalizzati, il portale può garantire che il lettore ALM sia visualizzato nella lingua corretta e che eventuali elementi dell&#39;interfaccia utente non necessari (ad esempio il sommario e i pulsanti di navigazione) siano nascosti. Ciò consente agli Allievi di percepire un’unica applicazione coerente anziché una raccolta disgiunta di strumenti.

* Questo è utile per le organizzazioni che conducono corsi di formazione su larga scala in più lingue utilizzando un altro LMS o piattaforma di apprendimento. Possono standardizzare l’utilizzo di tale piattaforma per la gestione dei profili degli Allievi, la selezione delle lingue e la presentazione dei cataloghi. Nel frattempo, ALM funge da motore di contenuti e tracciamento affidabile, rispettando le preferenze della lingua e le interazioni degli utenti specificate dal sistema esterno durante ogni avvio di LTI.

## Ponderazione delle domande nell’elenco di controllo per le valutazioni dell’istruttore

### Panoramica

Il miglioramento introduce liste di controllo ponderate, consentendo a istruttori e manager di valutare gli Allievi utilizzando scale graduate e punteggi totali, invece di trattare ogni domanda dell’elenco di controllo come uguale. L’obiettivo è facilitare la creazione di liste di controllo mediante l’attuazione di valutazioni ponderate delle domande, che consentano di riflettere l’importanza relativa delle diverse azioni o competenze all’interno di una singola lista di controllo.

### Novità

Gli elenchi di controllo supportano i seguenti tipi:

1. Sì/No
Il comportamento rimane lo stesso di oggi: ogni domanda è Sì/No e i criteri di superamento sono basati sul numero di risposte &quot;Sì&quot;.

2. Domande dello stesso peso

   * Le domande vengono valutate su una scala numerica (0-10 per impostazione predefinita), dove:

      * I valori max/min nella scala sono personalizzabili a livello di elenco di controllo.

      * La scala può ora iniziare da 0 (il punteggio minimo precedente era 1).

   * Tutte le domande hanno lo stesso punteggio massimo, quindi l’elenco di controllo si comporta come una scala graduata uniforme per ogni domanda.

3. Domande a peso diverso

   * Ogni domanda ha il proprio punteggio massimo (peso).

   * I criteri di superamento dipendono dalla percentuale del punteggio totale possibile che l’Allievo ottiene nell’elenco di controllo (ad esempio, &quot;supera se l’Allievo ottiene ≥ 70% del punteggio totale disponibile&quot;).

Per tutti i tipi di elenco di controllo:

* **Il revisore** (istruttore o manager) valuta l’allievo in base al tipo di elenco di controllo configurato:

   * Selezionare Sì/No.

   * Selezionare i punteggi nella scala definita.

* Il report **Elenco di controllo** è stato aggiornato per includere, per domande con peso diverso:

   * Punteggio massimo per ogni domanda.

   * Il punteggio ottenuto da ciascun Allievo per tale domanda.

Ciò consente l&#39;analisi delle prestazioni complessive e delle prestazioni specifiche delle domande in base agli spessori previsti.

### Vantaggi principali

* **Valutazioni più complete e realistiche**: gli istruttori possono riflettere le priorità reali fornendo più punti ai comportamenti critici e meno a quelli minori, pur utilizzando un flusso di lavoro di elenco di controllo adatto alle attività osservate o pratiche.

* **Passaggio/fallimento basato sul punteggio totale**: le valutazioni possono essere basate sul punteggio percentuale complessivo, non solo sul numero di domande che superano una soglia, ma anche su un maggiore allineamento con le competenze o gli schemi di valutazione tipici.

* **Migliore reporting**: i report dell&#39;elenco di controllo aggiornati espongono il punteggio massimo e il punteggio raggiunto per domanda, consentendo ai proprietari dei programmi e ai team di qualità di identificare punti deboli specifici e perfezionare la formazione o la guida alla valutazione.

### Casi d’uso

* **Valutazioni delle competenze aziendali**: gli ingegneri vengono valutati mediante elenchi di controllo pratici basati su scenari in cui determinate fasi diagnostiche o di comunicazione devono avere un peso maggiore rispetto alle fasi cosmetiche o a basso rischio. Le domande ponderate e i criteri di superamento del punteggio totale rendono queste valutazioni più credibili e predittive delle prestazioni reali.

* **Osservazioni sulla sicurezza e sulla conformità**: nel settore sanitario, manifatturiero o dell&#39;assistenza sul campo, è possibile assegnare punteggi massimi più elevati alle fasi di sicurezza critiche, in modo da garantire che l&#39;assenza di un&#39;azione critica per la sicurezza abbia un impatto maggiore sul punteggio totale rispetto all&#39;assenza di una fase procedurale minore.

* **Coaching e calibrazione**: con il numero massimo di punteggi per domanda raggiunti, i manager possono vedere esattamente dove gli Allievi hanno ottenuto risultati insoddisfacenti e calibrare gli Istruttori su come ottenere punteggi uniformi.

## Supporto multilingue per domande dell&#39;elenco di controllo

### Panoramica

Il miglioramento introduce il supporto multilingue per le domande sugli elenchi di controllo, consentendo ai revisori di valutare e assegnare un punteggio agli elenchi di controllo nella lingua preferita. Questa funzione è particolarmente utile nelle aree multilingue e nelle distribuzioni globali, in quanto consente agli autori di creare domande di elenchi di controllo localizzate per ogni lingua di contenuto supportata, mantenendo un singolo modulo di elenchi di controllo e un processo di valutazione coerente.

In Adobe Learning Manager oggi:

* Tutti i moduli rivolti agli Allievi (SCORM, PDF, HTML, ecc.) possono essere disponibili in più lingue dei contenuti, consentendo agli allievi di scegliere la lingua preferita.

* In un modulo di elenco di controllo, i revisori (istruttori/manager) valutano gli allievi in base alle domande definite in tale elenco di controllo.

### Novità

**Authoring**

* Gli Autori ora possono aggiungere domande dell’elenco di controllo in tutte le lingue selezionate a livello di corso.

* Per ogni elenco di controllo:

   * L’Autore deve fornire un testo di domanda equivalente in ogni lingua di contenuto in cui si trova il corso.

   * Gli autori hanno la responsabilità di garantire che il significato di ogni domanda sia coerente in tutte le lingue.

**Esperienza di revisione**

* I revisori visualizzeranno le domande dell’elenco di controllo e l’interfaccia utente di valutazione nella lingua del contenuto selezionato.

* Quando una domanda viene valutata in una lingua:

   * La valutazione (punteggio, Sì/No, stato) è logicamente la stessa in tutte le lingue. Si tratta di un elenco di controllo singolo con visualizzazioni in più lingue, non di elenchi di controllo separati per lingua.

**Report**

Il report Elenco di controllo visualizzerà il testo della domanda nella lingua del contenuto dell&#39;utente:

* Un amministratore o un revisore che esegue il report in ciascuna lingua visualizza i nomi delle domande localizzate per tale lingua.

* Le risposte e i punteggi sottostanti rimangono invariati; vengono tradotte solo le etichette delle domande.

### Vantaggi principali

* **Migliore esperienza di revisione**: i revisori possono lavorare interamente nella propria lingua, leggendo domande e registrando valutazioni senza barriere linguistiche.

* **Allineamento normativo e delle policy**: nelle aree con requisiti di uguaglianza linguistica (ad esempio, olandese/francese in Belgio), le liste di controllo ora possono soddisfare gli stessi standard di altri materiali di apprendimento, riducendo i rischi di conformità.

* **Logica di valutazione coerente**: mentre il testo è localizzato, la valutazione e il punteggio vengono condivisi in tutte le lingue, assicurando che i risultati siano confrontabili e gestiti a livello centrale.

### Casi d’uso

* I franchising di più paesi che operano in più lingue possono distribuire un singolo corso e una checklist fornendo al contempo esperienze di revisione localizzate in ogni territorio.

* Qualsiasi azienda globale con istruttori locali (ad esempio, EMEA, LATAM, APAC) può fare in modo che i revisori lavorino nella propria lingua locale condividendo la stessa progettazione e creazione di report dell&#39;elenco di controllo globale.

## Elenco di controllo con funzionalità di creazione dei commenti per il revisore

### Panoramica

Il miglioramento introduce una funzione di inserimento dei commenti per le valutazioni degli elenchi di controllo, che consente ai revisori, come istruttori e manager, di fornire un feedback qualitativo insieme ai punteggi numerici. Questo feedback può essere reso visibile agli Allievi quando necessario.

L&#39;obiettivo è quello di supportare valutazioni basate su liste di controllo in cui il feedback del mentore è cruciale quanto il risultato numerico. Ciò include evidenziare punti di forza specifici, aree di miglioramento o fornire il contesto per il punteggio fornito.

Oggi i revisori possono:

* Valuta un elenco di controllo per ogni Allievo, domanda per domanda.

* Visualizzare i risultati e rivalutare gli Allievi con esito negativo.

In scenari reali, come l&#39;aviazione, i formatori sul campo valutano gli agenti del reparto produttivo e il personale aeroportuale. Analogamente, gli istruttori e i tutori delle piccole e medie imprese (PMI) utilizzano spesso liste di controllo per valutare le prestazioni lavorative. Tuttavia, questi elenchi di controllo in genere non includono una sezione strutturata per acquisire il feedback narrativo correlato alla valutazione.

### Novità

#### Opzioni di authoring

Gli Autori possono configurare ogni elenco di controllo per:

* Attivare o disattivare la funzionalità Commenti per i revisori.

* Decidi se il nome del revisore deve essere mostrato agli Allievi insieme ai commenti.

Ciò consente alle organizzazioni di personalizzare la visibilità dei commenti in base ai requisiti di cultura e privacy.

#### Esperienza del revisore

Quando è attivata l’opzione di aggiunta di commenti:

* I revisori (istruttori/manager) possono aggiungere commenti facoltativi durante la valutazione di un elenco di controllo.

* In base alle impostazioni dell’elenco di controllo, gli Allievi possono scegliere se visualizzare o meno i commenti.

Se rivalutano un Allievo, può aggiornarlo o modificarlo per riflettere la valutazione più recente.

#### Relazioni e notifiche

* Il report Elenco di controllo acquisisce una nuova colonna per le osservazioni del revisore, acquisendo il commento fornito durante la valutazione.

* Gli Allievi ricevono notifiche (tramite piattaforma e e-mail) ogni volta che viene eseguita una valutazione dell’elenco di controllo. Queste notifiche includono:

   * Il commento e

   * Il nome del revisore, se configurato per essere visibile.

In questo modo, il feedback non viene solo archiviato, ma viene trasmesso attivamente agli Allievi.

### Vantaggi principali

* **Feedback più ricco e simile a un coach**: i punteggi numerici sono integrati da osservazioni contestuali, rendendo le liste di controllo uno strumento più efficace per l&#39;allenamento, non solo la conformità.

* **Tracciabilità e verificabilità**: le organizzazioni ottengono un record persistente di chi ha valutato chi, quando e cosa hanno detto, che è importante in ambienti regolamentati e ruoli ad alto rischio.

* **Migliore coinvolgimento degli Allievi**: gli Allievi ricevono indicazioni chiare collegate a valutazioni specifiche, che migliorano la comprensione delle aspettative e dei passaggi successivi.

### Casi d’uso

* Le organizzazioni con ambienti regolamentati possono utilizzare i commenti per documentare il giudizio clinico o il feedback procedurale per il personale che viene osservato sul campo.

* Le organizzazioni del settore dell&#39;aviazione e dell&#39;assistenza a terra possono allegare note dettagliate sulle prestazioni operative, sulle pratiche di sicurezza e sul comportamento dei clienti, trasformando una lista di controllo in uno strumento strutturato di debrief.

* Nel tutoraggio e nella valutazione di PMI, gli istruttori possono acquisire osservazioni sfumate che non si adattano a un punteggio da soli, ad esempio, &quot;l’escalation gestita bene ma deve migliorare la gestione del tempo&quot; o &quot;un flusso di risoluzione dei problemi eccellente; non è stato completato un passaggio della documentazione&quot;.

## Creazione di report dei quiz e tentativi multipli a livello di contenuto

### Panoramica

>[!IMPORTANT]
>
>Tieni presente che la funzione sarà disponibile solo dopo averla abilitata nell’account. Contatta il supporto di ALM.


Attualmente, ALM supporta tentativi multipli a livello di LMS tramite la funzione MQA (Multiple Quiz Attempt):

* Gli Autori possono configurare i tentativi a livello di corso (applicato a tutti i moduli quiz del corso) o a livello di modulo (per modulo quiz).

* I tentativi possono essere:

   * Un numero specifico (ad esempio, 3 tentativi) oppure

   * Tentativi infiniti, controllati a livello LMS.

* Quando un Allievo utilizza un modulo tramite il lettore Fluidic e quindi lo chiude o lo completa, la sessione viene trattata come un singolo tentativo di LMS.

* Ogni tentativo di LMS viene acquisito nel report del quiz L2 come nuova riga.

Tuttavia, se il file di contenuti stesso (ad esempio, un quiz Articola SCORM) implementa la propria logica dei tentativi multipli, il report del quiz L2 di ALM al momento non distingue o traccia correttamente tali tentativi interni.

Questo miglioramento introduce il monitoraggio a livello di contenuto di più tentativi per i quiz, consentendo a Adobe Learning Manager di acquisire con precisione ogni tentativo all’interno del contenuto stesso nel report del quiz L2. È progettato per situazioni in cui lo strumento di authoring dei contenuti (come Articola SCORM) gestisce i tentativi di quiz in modo indipendente. Con questa funzione, i tentativi vengono riportati correttamente nel report ALM senza dipendere dalle impostazioni MQA (Multiple Quiz Attempt) di livello LMS.

### Novità

#### Flag Autore per i tentativi a livello di contenuto

* Quando si carica del contenuto nella libreria dei contenuti, gli autori possono ora indicare che un file di contenuto specifico contiene più tentativi incorporati.

* Si tratta di un&#39;impostazione per contenuto che indica ad ALM di trattare i tentativi definiti all&#39;interno del contenuto come la fonte di verità.

#### Comportamento del corso/modulo

Quando tali contenuti vengono utilizzati in un corso:

* I tentativi del modulo verranno ricavati dal contenuto e non da LMS MQA.

* Gli Allievi vedranno un solo tentativo a livello di LMS:

   * La panoramica del corso e la vista del modulo non espongono un pulsante LMS &quot;re-attempt&quot; (ritenta) per tale modulo.

   * La gestione dei tentativi (ad esempio, i tentativi all’interno del quiz) è regolata dal contenuto stesso.

#### Report

Il report del quiz L2 considera ogni tentativo a livello di contenuto come una riga di tentativo separata:

* Ogni tentativo di quiz interno configurato nel contenuto viene visualizzato come propria riga nel report del quiz L2, ad esempio come sono rappresentati oggi i tentativi a livello di LMS.

* Il formato di ogni riga rimane lo stesso delle righe a tentativi multipli esistenti nei report L2 (stesse colonne, struttura e semantica).

* In questo modo si ottiene un&#39;esperienza di reporting coerente:

   * Sia che i tentativi siano controllati da LMS MQA o dal contenuto, il report del quiz L2 mostra una riga per tentativo.

#### Vantaggi principali

* Cronologia accurata dei tentativi per i quiz SCORM in cui i tentativi sono controllati internamente da strumenti come Articola, senza forzare la configurazione MQA di livello LMS in primo piano.

* Esperienza di apprendimento più pulita: per i tentativi controllati dal contenuto, gli Allievi vedono un singolo spazio a livello LMS e non devono interagire con i controlli dei tentativi LMS; tutti i tentativi vengono gestiti all’interno dell’interfaccia utente del quiz che già conoscono.

* Architettura flessibile: gli utenti possono scegliere se ALM MQA o i tentativi a livello di contenuto debbano guidare il comportamento per modulo, a seconda di come è stato creato il loro contenuto e di come preferiscono gestire i tentativi.

* Modello di reporting coerente: i consumatori a valle del report quiz L2 possono trattare ogni riga come &quot;un tentativo&quot;, indipendentemente da dove ha origine la logica del tentativo.

#### Casi d’uso

* Le organizzazioni che utilizzano Articulate SCORM possono mantenere la logica dei quiz indipendente all&#39;interno del pacchetto SCORM, ottenendo al contempo report accurati a livello di tentativo in ALM senza ulteriori configurazioni LMS.

* Le organizzazioni che utilizzano contenuti SCORM forniti dal fornitore possono evitare la necessità di modificare o implementare la logica dei tentativi e tentativi aggiuntivi con MQA a livello LMS.

## Codici QR dell’Istruttore per iscrizione e partecipazione a sessioni di esempio

### Panoramica

Questo miglioramento consente agli istruttori di generare essi stessi codici QR per:

* Iscrizione istanza del corso,

* la partecipazione alla sessione, o

* Iscrizione e partecipazione insieme

a livello di sessione. È progettato per le situazioni in cui gli Allievi entrano in un’aula fisica o ibrida e richiedono un’opzione rapida e autonoma per iscriversi e registrare la partecipazione utilizzando un codice QR.

### Novità

#### Codici QR generati dall’istruttore

* Gli istruttori possono generare codici QR a livello di sessione per:

   * Iscriviti all’istanza: gli Allievi eseguono la scansione per iscriversi all’istanza che include la sessione corrente.

   * Contrassegna partecipazione alla sessione: gli Allievi eseguono la scansione durante/dopo la sessione per registrare la partecipazione a una sessione specifica.

   * Iscriviti alla sessione di istanza + contrassegna la partecipazione : Un QR combinato per i walk-in che non sono ancora iscritti e la cui partecipazione deve essere contrassegnata in un unico passaggio.

* Gli istruttori possono esportare i codici QR necessari in base allo scenario (iscrizione, partecipazione o entrambi).

#### Confezionamento di codici QR

Il PDF del codice QR esportato include:

* Nome del corso

* Nome dell’istanza

* Nome sessione

Ciò consente agli istruttori e ai coordinatori di identificare e stampare il codice QR corretto per ogni sessione.

### Vantaggi principali

* **Autonomia degli istruttori**: gli istruttori non devono più attendere che gli amministratori creino codici QR. Possono generarli direttamente per ogni sessione, migliorando l&#39;agilità e riducendo il sovraccarico di coordinamento.

* **Migliore logistica delle aule**: per gli assistenti vocali o in loco (come gli operatori sul campo, il personale del negozio o i partecipanti esterni), gli istruttori possono gestire le iscrizioni e la frequenza sul posto utilizzando i codici QR.

* **Carico di lavoro amministrativo ridotto**: i team di amministrazione possono concentrarsi sulla configurazione e sulla governance invece di gestire le richieste di generazione di codici QR di routine per ogni sessione.

### Casi d’uso

* Le organizzazioni che eseguono grandi quantità di sessioni in loco (ad esempio, formazione sul prodotto per professionisti) possono consentire agli istruttori di stampare codici QR specifici per sessione che registrano e contrassegnano la partecipazione con una scansione.

* Nei corsi di formazione per la vendita al dettaglio, la produzione industriale e l’assistenza sanitaria, in cui gli Allievi spesso partecipano alle sessioni direttamente dal pavimento o senza pre-iscrizione, è possibile inserire un codice QR &quot;Iscrizione + Partecipazione&quot; sulla porta. Ciò consente agli Allievi di provvedere autonomamente all’iscrizione e alla partecipazione tramite telefono.

* Gli eventi di formazione per partner o clienti consentono al formatore on-site di adattarsi facilmente alle modifiche della stanza, a sessioni aggiuntive o a partecipanti aggiuntivi senza dover consultare l&#39;amministratore per nuovi codici QR.

## Miglioramenti a Captivate e al lettore ALM

### Panoramica

Questo miglioramento migliora l’esperienza di riproduzione dei contenuti Adobe Captivate all’interno del lettore Adobe Learning Manager (ALM), in particolare in seguito alle recenti modifiche apportate all’architettura di Captivate. L&#39;obiettivo è consentire agli Allievi di interagire con i moduli Captivate in modalità nativa in ALM, garantendo al contempo che la navigazione, il tracciamento del completamento e la creazione di note siano chiari, coerenti e affidabili.

### Novità

#### Esperienza sommario unificata

* Sul lato sinistro del lettore viene visualizzato solo il sommario ALM.

* Il sommario della Captivate è nascosto quando il modulo viene riprodotto all&#39;interno di ALM.

* In questo modo si eliminano le duplicazioni, si garantisce un&#39;unica fonte di verità per la navigazione e si libera spazio su schermo.

#### Feedback sul completamento visivo

* Il sommario ALM mostra segni di graduazione verdi (o indicatori visivi equivalenti) che indicano il completamento a livello di diapositiva.

* Man mano che gli Allievi avanzano nelle diapositive Captivate, il sommario ALM riflette le diapositive completate, in linea con le aspettative degli Allievi per i lettori del corso moderni.

#### Controlli di avanzamento contestuali

* I controlli del lettore verranno adattati in base al tipo di diapositiva:

   * Per le diapositive video:

      * Mostra una barra di avanzamento temporale che riflette la riproduzione del video.

* Per diapositive non video:

   * Visualizza i controlli di spostamento tra le diapositive (diapositiva successiva/precedente, ecc.) anziché una barra temporale non funzionale.

      * In questo modo si evita di mostrare controlli irrilevanti o non funzionanti su alcuni tipi di diapositive.

#### Navigazione semplificata

* La barra di navigazione separata del modulo (ALM) e la barra di navigazione del corso vengono unite in un&#39;unica barra intuitiva.

* Questa navigazione unificata:

   * Distingue chiaramente lo spostamento all’interno del modulo Captivate rispetto al ritorno al livello del corso o del modulo.

   * Riduce la confusione causata da più barre con scopi sovrapposti.

#### Collegamento note affidabile

* Le note sono collegate ai numeri delle diapositive anziché alle marche temporali.

* Questa modifica:

   * Corregge gli errori di esportazione causati da timestamp mancanti o errati.

   * Assicura che le note possano essere esportate in modo coerente come PDF, con una mappatura affidabile tra le note e il contesto della diapositiva a cui appartengono.

### Vantaggi principali

* Esperienza più pulita per un singolo giocatore: gli allievi interagiscono con un sommario e un modello di navigazione, riducendo la confusione e il carico cognitivo.

* Indicazioni precise di completamento e avanzamento: le tacche a livello di diapositiva e i controlli contestuali aiutano gli allievi a capire dove si trovano e cosa resta.

* Creazione ed esportazione di note più affidabili: legando le note alle diapositive invece di timestamp fragili, gli utenti riacquistano un flusso di lavoro affidabile da note a PDF, anche con il contenuto di Captivate basato su diapositive.

* Flusso di lavoro dell’autore mantenuto: gli autori mantengono la semplicità della pubblicazione diretta su ALM di Captivate, mentre gli Allievi ottengono un’esperienza di riproduzione moderna e integrata senza costi di authoring aggiuntivi.

### Casi d’uso

* I programmi di abilitazione che si basano su Captivate per le simulazioni interattive possono distribuire i contenuti in ALM, garantendo che la navigazione, il tracciamento del completamento e le note funzionino in modo coerente per gli Allievi.

* Le organizzazioni che utilizzano Captivate come strumento principale di authoring dei contenuti possono gestire la pubblicazione con un clic ed evitare di confondere i doppi sommari e i controlli non funzionali per gli Allievi.

* Le organizzazioni che si basano sulle note esportate dal contenuto Captivate in ALM (per coaching, conformità o record) possono accedere a quanto segue:

   * Le note sono collegate correttamente alle diapositive.

   * I PDF vengono generati come previsto.

## Miglioramento del tempo di apprendimento impiegato per il calcolo nelle Trascrizioni Allievi

### Panoramica

Con la versione di aprile 2026 di Adobe Learning Manager è stato aggiornato il modo in cui vengono calcolati i tempi di apprendimento nelle Trascrizioni allievi. In precedenza, la logica di reporting poteva portare a tempi imprecisi se gli Allievi lasciavano il lettore aperto senza interagire con il contenuto, causando discrepanze. Il nuovo metodo ora tiene traccia del tempo attivo in base al coinvolgimento dell’utente, in particolare quando la scheda è attiva e quando c’è attività dell’utente. Questa modifica consente di ottenere dati più accurati.

Questo aggiornamento migliora i report e i dashboard, aiutando gli amministratori a garantire una migliore conformità e a tenere traccia dei progressi degli Allievi. Dopo l’aggiornamento, rivedi le Trascrizioni Allievi per vedere questi miglioramenti.

Il metodo di calcolo aggiornato si concentra sul coinvolgimento effettivo, ad esempio l&#39;attivazione della scheda attiva e le recenti interazioni degli utenti, migliorando in tal modo la precisione dei report temporali nelle seguenti aree:

* Trascrizioni Allievi (interfaccia utente)
* Metriche Admin Dashboard
* Report di iscrizione al corso
* API e connettori

### Cosa è cambiato

La colonna **Tempo impiegato per l’apprendimento** nelle trascrizioni degli allievi ora utilizza una logica migliorata per calcolare il tempo in modo più accurato. Invece di tenere traccia degli orari di apertura e chiusura del lettore, il sistema ora distingue tra periodi di inattività e di attività in base al coinvolgimento dell&#39;utente.

* **Tempo di attività**: tempo in cui l’Allievo è attivamente coinvolto (ad esempio, nella scheda corretta, eseguendo azioni come scorrere o guardare video).
* **Tempo di inattività**: tempo in cui l’allievo non è impegnato (ad esempio, tabulazione attivata, nessuna attività da oltre 10 minuti), che viene escluso dal totale.

Ciò si applica alla maggior parte dei tipi di modulo, con eccezioni per i moduli SCORM, Captivate e XAPI, che mantengono la logica originale.

### Come funziona

Il nuovo calcolo varia in base al tipo di modulo:

* **Moduli video e audio**: attivo durante la riproduzione del contenuto, anche se l’Allievo passa a un’altra scheda. L&#39;attivazione tramite tabulazione non è richiesta per tenere traccia del tempo di riproduzione.
* **Moduli statici (PDF, PPT, Excel e così via)**: attivi se nella scheda ed eseguono attività (movimento del mouse, scorrimento, clic, input da tastiera) negli ultimi 10 minuti. Se non viene rilevata alcuna attività per 10 minuti, il sistema passa al modo inattivo.
* **SCORM e Captivate** mantengono la logica di apertura/chiusura originale.
* **xAPI** ora utilizza il rilevamento del tempo attivo basato su schede, in cui il tempo viene conteggiato solo quando la scheda è attiva. Il contenuto AICC **non è supportato**.
* **HTML, LTI e altro contenuto**: può variare; verifica l’accuratezza delle Trascrizioni Allievi.

Il tempo di inattività viene sottratto, in modo da registrare solo il tempo di coinvolgimento effettivo.

>[!NOTE]
>
>Se il notebook entra in modalità di sospensione, il tempo di apprendimento potrebbe non essere monitorato correttamente. Ciò è dovuto al fatto che il tracciamento delle attività si interrompe durante il sonno e riprende solo alla riattivazione del notebook.


### Tabella riassuntiva

| **Tipo modulo** | **Ora di attivazione (contata)** | **Tempo di inattività (escluso)** |
| --- | --- | --- |
| **Video/Audio** | Tempo di riproduzione | Non avviato; terminato; sospeso **\>10 min** |
| **Statico (PDF/PPT/DOC)** | Attività **e** della scheda attiva negli ultimi **10 min** | Nessuna attività **\>10 min**; scheda inattiva |
| **SCORM** | Tempo segnalato per runtime di contenuto | Impossibile rilevare lo stato inattivo |
| **Captivate** | Intervallo basato su diapositive | Impossibile rilevare lo stato inattivo |
| **nell’istruzione xAPI** | Scheda attiva | Tabulazione inattiva |
| **HTML** | Tempo di apertura del lettore con scheda attiva | Tabulazione inattiva |
| **Produttore/consumatore LTI** | Se il contenuto LTI viene riprodotto all&#39;interno del lettore di ALM (ovvero, ALM utilizza contenuto LTI ospitato su un altro LMS che funge da produttore), viene applicata questa logica relativa al tempo impiegato.<br><br>Tuttavia, se il contenuto viene riprodotto al di fuori dell&#39;LMS (ovvero, il contenuto è ospitato in ALM, ALM è il produttore, ma la riproduzione avviene in un lettore esterno), questa parte della logica di calcolo del tempo non si applica.  <br>**Nota**: consumer LTI non supportato in Adobe Learning Manager. | Tabulazione inattiva |

**Nota**:

* **Revisioni e sessioni parallele**: conta come attive quando vengono soddisfatte le condizioni sopra riportate.
* **Tutti i dispositivi, i browser e le lingue**: incluso; l&#39;utilizzo offline dei dispositivi mobili viene aggiunto dopo la sincronizzazione.

### Vantaggi del nuovo calcolo

* **Report accurati**: elimina i tempi di apprendimento eccessivi dovuti ai giocatori incustoditi, fornendo durate di apprendimento realistiche.
* **Migliore conformità**: supporta il monitoraggio accurato per la formazione obbligatoria (ad esempio, il requisito mensile di 5 ore di un&#39;azienda).
* **Dashboard migliorati**: i grafici delle attività degli utenti e i report sul tempo impiegato ora riflettono il coinvolgimento effettivo.
* **Insight sugli Allievi**: consente agli Amministratori di identificare i progressi effettivi e di indirizzare gli Allievi disimpegnati.

### Impatto su report e analisi

* **Trascrizioni Allievi:** &quot;Tempo impiegato per l’apprendimento&quot; riflette ora il **coinvolgimento effettivo**.
* **Admin Dashboard:** le metriche che includono il tempo (ad esempio, riquadri &quot;tempo impiegato&quot; e tendenze) mostreranno valori **più bassi ma più realistici** in scenari in cui il tempo di inattività ha gonfiato i risultati in precedenza.
* **Report di iscrizione al corso:** i campi relativi al tempo adottano il **nuovo calcolo** dopo l’avvio.
* **Nota sulla comparabilità:** poiché i dati cronologici non vengono ricalcolati, le analisi delle serie temporali che si estendono oltre la data di rilascio potrebbero mostrare un **cambiamento di passaggio**. Considerare l&#39;annotazione o la segmentazione per data negli strumenti di analisi.

### API e connettori

* **Nessuna modifica dello schema** in endpoint/campi esistenti che segnalano il tempo impiegato.
* **La semantica dei campi** è stata aggiornata per riflettere il _calcolo del tempo attivo_ per le sessioni **successive** all&#39;avvio della funzione.
* **I connettori e le esportazioni** che utilizzano campi lunghi riceveranno automaticamente i valori aggiornati in futuro.

### Compatibilità con le versioni precedenti e migrazione dei dati

* **Sessioni cronologiche:** non ricalcolate.
* **Nuove sessioni:** Utilizzare il calcolo del tempo attivo **nuovo**.
* **Periodi misti:** per gli audit o i report longitudinali, suddividere per **pre-/post-lancio** per evitare errori di interpretazione.

### Limitazioni note

* **I contenuti interattivi** (SCORM/Captivate) continuano a dipendere dalla tempistica fornita dal contenuto; il rilevamento di inattività all&#39;interno del contenuto non è disponibile.
* **I contenuti basati su Iframe** (HTML/xAPI) limitano il rilevamento di interazioni granulari; in alternativa, viene utilizzato lo stato attivo della scheda.

### Domande frequenti

**Questo aggiornamento modifica i record cronologici?**

N. La modifica si applica solo alle sessioni successive all’avvio della funzione.

**Come verificare le modifiche?**

Controlla le Trascrizioni Allievi per i moduli recenti; confronta i tempi con le durate previste.

**Questa operazione influisce su tutti gli account?**

Sì, è un aggiornamento globale per tutti gli account Adobe Learning Manager.

**Gli Allievi devono intraprendere un’azione?**

N. La modifica è automatica e trasparente per gli Allievi.

**Cosa succede se gli Allievi lasciano aperto il contenuto?**

Il tempo di inattività è stato escluso, impedendo la creazione di rapporti eccessivi.

**Le sessioni video/audio vengono messe in pausa automaticamente quando la scheda è inattiva?**

N. Il comportamento di riproduzione è invariato. Il tempo viene escluso quando si è in pausa per più di 10 minuti o quando non si sta riproducendo attivamente.

**Verrà riflessa l&#39;attività mobile offline?**

Sì. Quando il dispositivo viene sincronizzato, viene incluso l&#39;utilizzo offline.

**Come devo procedere se i dashboard ora mostrano medie inferiori?**

Ciò è previsto nei casi in cui il tempo di inattività ha avuto risultati gonfiati in precedenza. Annota i dashboard e regola le destinazioni in base alle esigenze.

**Sono presenti prerequisiti?**

Nessuno; la modifica è automatica.

## Aggiornamento ai report Trascrizione Allievo per gli Amministratori

Stiamo aggiornando i report Trascrizione Allievo (LT) per gli Amministratori al fine di supportare meglio le valutazioni basate su elenchi di controllo e il feedback dei revisori.

## Cosa cambia?

### &#x200B;1. Rinomina colonna in Trascrizione apprendimento Amministratore

Colonna **Commento invio** esistente in Admin Learning
Trascrizione:

1. **Rinominato in:** `Reviewer's remarks`

### Dati visualizzati in questa colonna:

* **Per i moduli di invio:**
La colonna continua a visualizzare il commento di invio (nessuna modifica del comportamento).

* **Per i moduli dell&#39;elenco di controllo:**
La colonna ora visualizza il commento di valutazione (le note del revisore dell&#39;elenco di controllo).

Questa modifica si applica a tutte le origini Admin LT:

* LT scaricato dall’interfaccia utente di amministrazione
* LT ottenuto tramite l’API dei processi
* LT generati tramite connettori

Dopo questa modifica, la stessa colonna riporta: - Commenti di invio per i moduli di invio

* Commenti di valutazione per i moduli dell’elenco di controllo

Sotto il nuovo nome di intestazione **Note del revisore**.

### &#x200B;2. Nuova colonna nelle esportazioni delle trascrizioni di apprendimento basate sul connettore

Per le trascrizioni di apprendimento esportate dal connettore:

* Alla fine del report viene aggiunta una nuova colonna denominata **Note del revisore**.
* Questa colonna contiene i commenti del revisore, in linea con il comportamento descritto in precedenza:
   * Commenti di invio per i moduli di invio
   * Commenti di valutazione per i moduli dell’elenco di controllo

## Impatto su integrazioni e automazioni esistenti

Se utilizzi i report Trascrizione Allievo in integrazioni personalizzate, automazioni o strumenti di reporting esterni, verifica i seguenti scenari:

| Scenario | Impatto | Azione richiesta |
|----------|--------|----------------|
| I campi in Admin LT vengono identificati in base al nome della colonna (ad esempio, &quot;Commento di invio&quot;) | L&#39;intestazione di colonna viene modificata in Note del revisore. | Sì. Aggiornare le mappature o la logica che fanno riferimento al commento Invio per utilizzare le osservazioni del revisore. |
| I campi in Admin LT vengono identificati solo in base alla posizione delle colonne (basata su indice) | La posizione di questa colonna rimane la stessa in Admin LT. | Di solito nessuna azione. Se la logica non dipende dal testo dell&#39;intestazione, non è necessaria alcuna modifica per Admin LT, è sufficiente modificare il nome della colonna se attualmente viene utilizzata la colonna &quot;Commenti di invio&quot;. |
| Si utilizza LT esportato dal connettore e si basa su un numero di colonne fisso o su una posizione specifica dell&#39;ultima colonna | Alla fine del report viene aggiunta una nuova colonna. | Sì. Regolare la logica di analisi o convalida in modo da tenere conto di una colonna aggiuntiva alla fine del file. |
| Usa LT esportato dal connettore e mappa per nome colonna | È disponibile una nuova colonna Commenti del revisore. | Facoltativo. Non è richiesta alcuna modifica a meno che non si desideri utilizzare i nuovi dati dei commenti del revisore/elenco di controllo. |

**Operazioni da eseguire**

* Esamina gli script, i processi ETL, i dashboard o le integrazioni che utilizzano i report Trascrizione Allievo.
* Se si fa riferimento al vecchio nome di colonna _Commento invio_, aggiornare la configurazione o il codice in modo da utilizzare il nuovo nome di colonna Commenti del revisore.
* Se si utilizzano esportazioni LT basate su connettore e si presuppone un numero fisso di colonne o un&#39;ultima colonna fissa, aggiornare la logica per gestire una colonna aggiuntiva alla fine dell&#39;esportazione.

Se l&#39;implementazione corrente si basa esclusivamente sulle posizioni delle colonne in Admin LT e non convalida o dipende dal testo dell&#39;intestazione di colonna, non è richiesta alcuna modifica per Admin LT stessa. Solo le esportazioni di connettori richiedono attenzione quando si utilizza un layout fisso.


## Esperienza senza accesso in Experience Builder

L’esperienza senza accesso in Experience Builder consente alle organizzazioni di visualizzare i contenuti di apprendimento e le pagine del portale a tutti i visitatori, inclusi quelli che non hanno effettuato l’accesso. Questa funzione è progettata per attirare, informare e coinvolgere i potenziali Allievi offrendo un’anteprima fluida e con marchio delle offerte di formazione prima di richiedere l’accesso o l’iscrizione.

Questa funzione consente di creare e personalizzare pagine pubbliche utilizzando la stessa intuitiva interfaccia di trascinamento disponibile in Generatore di esperienza standard. È possibile mostrare cataloghi di corsi, categorie, percorsi e contenuti statici avanzati, tra cui immagini, testo, HTML e immagini incorporate, per chiunque visiti il portale. In questo modo è più semplice evidenziare i programmi di apprendimento, promuovere nuovi corsi e fornire informazioni essenziali a un pubblico più ampio.

I visitatori possono sfogliare il catalogo, visualizzare i dettagli su corsi e istanze e utilizzare la ricerca globale per esplorare le opportunità di formazione disponibili. Tuttavia, per le azioni che richiedono l’identità di un utente, ad esempio l’iscrizione a un corso, l’accesso a funzioni personalizzate (come Calendario, Conformità, Classifica o Apprendimento sociale) o la partecipazione a corsi di formazione, il visitatore dovrà effettuare l’accesso. Questo approccio garantisce che le informazioni sensibili e personalizzate rimangano al sicuro, pur consentendo un&#39;esperienza di anteprima completa.

Gli amministratori possono configurare le pagine e i widget visibili agli utenti che non hanno effettuato l’accesso, in modo da visualizzare solo il contenuto appropriato. Le pagine possono essere impostate in modo da essere accessibili sia agli utenti che hanno effettuato l’accesso che a quelli che non l’hanno fatto, oppure in modo esclusivo per uno di questi gruppi. Experience Builder offre una modalità di anteprima che consente di vedere esattamente come appariranno le pagine ai visitatori prima della pubblicazione.

Per abilitare questa funzione, l&#39;amministratore dell&#39;integrazione ALM deve attivare il connettore di accesso ai dati di formazione. Questo connettore garantisce che i metadati del corso siano accessibili al pubblico.

Il branding e la localizzazione sono completamente supportati e consentono di personalizzare i titoli delle pagine, i favicon e le impostazioni della lingua in modo che siano in linea con l&#39;identità dell&#39;organizzazione e soddisfino le esigenze del pubblico. Come parte della transizione a questa esperienza avanzata, la funzionalità della pagina principale precedente per gli utenti non connessi sarà dichiarata obsoleta. Pertanto, tutti i nuovi contenuti pubblici devono essere creati utilizzando Experience Builder.

### Scopo della funzione

L’esperienza senza accesso in Experience Builder consente alle organizzazioni di mostrare pubblicamente i contenuti di apprendimento e le pagine del portale a chiunque, senza richiedere agli utenti di accedere. Questo consente di attirare, informare e coinvolgere i potenziali Allievi fornendo un’anteprima dei corsi di formazione e delle risorse disponibili prima che sia necessaria l’iscrizione o l’autenticazione.

### Casi d&#39;uso reali su esperienze senza accesso

* **Marketing e sensibilizzazione**: le organizzazioni possono promuovere i propri programmi di formazione a un pubblico esterno, ad esempio potenziali clienti, partner o candidati, rendendo pubblicamente accessibili i cataloghi dei corsi e i dettagli dei programmi.
* **Esplorazione pre-iscrizione**: gli Allievi possono sfogliare i corsi disponibili, visualizzare le panoramiche ed esplorare le categorie prima di decidere di iscriversi o accedere, aiutandoli a prendere decisioni consapevoli in merito all’iscrizione.
* **Portali di formazione aziendali**: le aziende possono fornire un portale pubblico per informazioni sulla conformità o sull&#39;onboarding, consentendo ai nuovi assunti o appaltatori di vedere quale formazione è disponibile prima di ricevere le credenziali.
* **Pagine di destinazione evento o campagna**: le organizzazioni che eseguono campagne di apprendimento o eventi possono creare pagine pubbliche dedicate per evidenziare corsi, pianificazioni o risorse in primo piano, aumentando la visibilità e il coinvolgimento.
* **SEO e individuabilità**: rendendo pubbliche pagine e cataloghi selezionati, le organizzazioni migliorano la visibilità dei motori di ricerca, aiutando le persone a scoprire le offerte di apprendimento online.

### Concetti chiave dell’esperienza senza accesso

L’esperienza non registrata di Experience Builder ti consente di mostrare pubblicamente contenuti di apprendimento e pagine di portali, consentendo ai visitatori di sfogliare senza accedere.

* **Creare pagine e menu pubblici**: è possibile impostare pagine e un menu singolo a cui tutti possono accedere, indipendentemente dallo stato di accesso.
* **Aggiungere solo i widget supportati**: sono inclusi i widget che non richiedono contesto utente (categorie, corsi e percorsi di apprendimento, casella di contenuto, HTML, iframe), mentre i widget specifici dell&#39;utente vengono nascosti.
* **Configura il comportamento adattivo della pagina**: decidi se visualizzare una pagina sia per gli utenti che hanno effettuato l’accesso che per quelli che non l’hanno fatto, e il sistema adatta i widget visibili e il contenuto in base allo stato di accesso.
* **Anteprima di entrambe le esperienze**: le opzioni di anteprima consentono di visualizzare le pagine con gli utenti che hanno effettuato l’accesso e quelli che non l’hanno fatto, con differenze a livello di visibilità e contenuto del widget.
* **Abilita ricerca globale**: i visitatori cercano corsi e contenuti, ma ottengono solo funzionalità di ricerca di base senza integrazione avanzata di intelligenza artificiale.
* **Consenti ai visitatori di sfogliare il catalogo e le panoramiche del corso**: i visitatori possono esplorare pagine del catalogo, dettagli del corso e istanze, ma devono accedere per iscriversi o accedere a funzioni personalizzate.
* **Personalizzare il branding e la localizzazione**: hai impostato le icone preferite e le impostazioni della lingua in modo che corrispondano alle esigenze di branding e accessibilità della tua organizzazione.
* **Abilita il connettore di accesso ai dati di formazione**: attiva questo connettore per esportare i metadati del corso per la visualizzazione pubblica, mantenendo aggiornate le pagine senza accesso.
* **Gestire un traffico elevato con un&#39;infrastruttura condivisa**: il sistema gestisce grandi volumi di visitatori anonimi utilizzando risorse condivise e limitando la velocità.
* **Ottimizza per SEO**: la piattaforma prepara le pagine pubbliche per l’indicizzazione dei motori di ricerca, semplificando la ricerca dei contenuti di apprendimento.

### Prerequisiti per l’esperienza senza accesso

* Prima di poter utilizzare l’esperienza senza accesso, è necessario abilitare il Connettore di accesso ai dati di formazione nell’Amministratore dell’integrazione.
* Il connettore esporta i metadati del corso in un repository pubblico, che mantiene aggiornate le pagine senza accesso.

#### Inizializzazione del connettore Accesso ai dati di formazione

Il connettore TDA (Training Data Access) è un prerequisito critico per l&#39;attivazione della nuova funzione di creazione di esperienze senza accesso in ALM. Questo connettore facilita l’esportazione dei metadati di formazione, consentendo al portale di visualizzare le informazioni sul corso agli utenti che non hanno effettuato l’accesso.

* **Attivazione del connettore**: è necessario abilitare il connettore TDA dal pannello di amministrazione dell’integrazione. Questo passaggio abilita la funzionalità di Experience Builder senza accesso e rende visibili le opzioni dell&#39;interfaccia utente pertinenti nell&#39;interfaccia di amministrazione.
* **Esportazione di metadati**: una volta attivato, il connettore esporta i metadati di formazione essenziali (ad esempio nome del corso, descrizione, panoramica, valutazione, durata e abilità) da ALM a un repository pubblico. Questi dati vengono utilizzati per popolare pagine e widget che non hanno effettuato l’accesso.
* **Pianificazione e sincronizzazione**: il processo di esportazione può essere pianificato (ad esempio, ogni giorno) per garantire che nel portale vengano visualizzati gli aggiornamenti più recenti del corso. Le modifiche apportate in ALM verranno visualizzate nelle pagine non connesse dopo il successivo ciclo di esportazione, in base alla frequenza di memorizzazione nella cache e di esportazione.
* **Disponibilità funzionalità**: le funzionalità del generatore di esperienze senza accesso, tra cui creazione di menu, supporto del widget e visibilità del catalogo, sono accessibili solo dopo l&#39;inizializzazione del connettore TDA. Se il connettore non è abilitato, Experience Builder rimarrà limitato agli scenari utente connessi.
* **Migrazione e supporto**: per gli account che passano da funzioni precedenti della pagina principale senza accesso, l’inizializzazione del connettore TDA è il primo passo verso la migrazione. Garantisce la possibilità di utilizzare la flessibilità del nuovo Experience Builder e funzionalità avanzate.


### Cosa possono fare i visitatori senza effettuare l’accesso

In un sito Experience Builder non connesso, i visitatori possono sfogliare il catalogo dei corsi di formazione aprendo la pagina del catalogo per i cataloghi pubblici. Possono utilizzare filtri quali catalogo, prodotto, ruolo, tipo, abilità e tag, a seconda della configurazione del sito. I visitatori possono anche cercare i corsi di formazione utilizzando la barra di ricerca globale nell’intestazione (se abilitata) e visualizzare i risultati della ricerca direttamente nella pagina del catalogo.

I visitatori possono visualizzare i dettagli del corso di formazione aprendo le pagine di panoramica per corsi, percorsi di apprendimento e certificazioni. In queste pagine sono visualizzati i metadati principali, inclusi titolo, descrizione, autore, durata, formato, tag e abilità.

Inoltre, i visitatori possono esplorare contenuti statici e promozionali. Possono leggere blocchi di testo e di contenuto RTF, visualizzare banner e porzioni di immagine e interagire con i frame incorporati come micrositi, video o strumenti esterni.

Se un visitatore fa clic su Iscriviti o tenta di avviare un corso di formazione, il sistema richiede di effettuare l&#39;accesso o di registrarsi. Dopo aver eseguito correttamente l’accesso, il visitatore viene reindirizzato alla pagina appropriata, che si tratti della home page, di una pagina personalizzata o del corso di formazione specifico selezionato.

### Cosa non è disponibile senza effettuare l’accesso

In un sito Experience Builder non connesso, i visitatori non possono accedere a funzionalità o contenuti che richiedono l&#39;autenticazione dell&#39;utente. Non sono in grado di iscriversi ai corsi di formazione, avviare o seguire corsi o accedere a widget personalizzati come Il mio apprendimento, Calendario, Conformità, Classifica o Apprendimento sociale. Questi widget dipendono dai dati specifici dell&#39;utente e sono disponibili solo dopo l&#39;accesso.

Inoltre, i visitatori non possono eseguire azioni quali l’iscrizione a un corso o l’accesso a contenuti che richiedono il tracciamento dell’avanzamento o del contesto dell’utente. Se si tenta di iscriversi o di avviare un corso di formazione, viene richiesto al visitatore di effettuare l’accesso o di registrarsi prima di procedere.

### Widget supportati in modalità senza accesso

In modalità senza accesso, sono supportati solo i widget che non richiedono dati specifici dell’utente. Queste comprendono:

* Widget Categorie, che visualizza le categorie di formazione disponibili.
* Widget di corsi e percorsi, che mostra corsi e percorsi di apprendimento dal catalogo pubblico.
* Casella dei contenuti per l&#39;aggiunta di testo statico, immagini o contenuto promozionale.
* widget HTML, per incorporare contenuti HTML personalizzati.
* Widget Iframe, per visualizzare siti, video o strumenti esterni all’interno della pagina.
* I widget che richiedono un contesto utente, ad esempio Il mio apprendimento, Calendario, Conformità, Classifica e Apprendimento sociale, non sono disponibili in modalità di accesso non effettuato.

### Pagine e menu nell’esperienza senza accesso

* È supportato un solo menu senza accesso, visibile a tutti i visitatori senza autenticazione.
* Le pagine possono essere aggiunte sia ai menu di accesso che a quelli senza accesso; se una pagina è presente in entrambi, i widget e il contenuto vengono adattati in base allo stato di accesso dell’utente.
* I menu che non hanno effettuato l’accesso non dispongono di personalizzazione o definizione dei destinatari. Tutti vedono lo stesso set di pagine.
* I widget che non sono supportati in modalità senza accesso vengono nascosti automaticamente; il layout di pagina viene regolato per riempire gli spazi.
* La gestione di menu e pagine (aggiunta, anteprima, eliminazione) è simile alla modalità di accesso, ma con adeguamenti per i vincoli non di accesso.

### Comportamento di ricerca e catalogo

In modalità senza accesso, gli utenti possono accedere alla pagina del catalogo e utilizzare la ricerca per sfogliare i corsi e i percorsi di apprendimento disponibili. La pagina del catalogo mostra tutti i corsi pubblici, insieme ai filtri e alle funzionalità di ricerca, seguendo le stesse impostazioni dell’account della modalità di accesso. Quando un utente esegue la ricerca, i risultati vengono visualizzati nella pagina del catalogo e gli utenti possono visualizzare le pagine di panoramica del corso e dell’istanza senza effettuare l’accesso. Tuttavia, azioni come l&#39;iscrizione richiedono l&#39;accesso.

Se un utente tenta di effettuare l&#39;iscrizione, il sistema richiede che prima acceda. La ricerca di utenti non connessi è più semplice di quella per gli utenti connessi e non include funzionalità avanzate come l&#39;integrazione di Assistente AI.

### Implementazione tecnica

#### Configurazione del connettore di accesso ai dati di formazione

Prima di poter utilizzare la funzione experience builder senza accesso, devi abilitare il connettore di accesso ai dati di formazione nel pannello di amministrazione dell’integrazione. Questo connettore esporta i metadati del corso di formazione da ALM a un repository pubblico, rendendolo accessibile tramite API per le pagine non connesse. La configurazione del connettore è un prerequisito per l&#39;attivazione della funzionalità e garantisce che il portale visualizzi informazioni aggiornate sul corso di formazione.

#### Esportazione e sincronizzazione dei metadati

Il connettore esporta i campi di metadati chiave quali nome del corso, panoramica, descrizione, valutazione, durata e abilità. È possibile pianificare le esportazioni (ad esempio, giornalmente) per mantenere il portale sincronizzato con ALM. È possibile che non tutti i campi di metadati siano inclusi. Per un elenco completo, consultare il reparto tecnico. I dati esportati vengono utilizzati per popolare le pagine senza accesso e le modifiche in ALM verranno visualizzate dopo il successivo ciclo di esportazione.

#### Frequenza di memorizzazione nella cache e di esportazione

Per gestire gli aggiornamenti dei dati, il sistema utilizza la frequenza di esportazione back-end e la cache front-end. Le modifiche apportate in ALM si riflettono sul portale dopo l&#39;esportazione pianificata e l&#39;aggiornamento della cache. A causa di questi meccanismi, alcuni aggiornamenti potrebbero non essere visualizzati immediatamente. Se hai bisogno di aggiornamenti più rapidi, modifica la pianificazione dell&#39;esportazione o cancella la cache in base alle esigenze.

#### Supporto della personalizzazione CSS/JS

È possibile applicare CSS e JavaScript personalizzati sia alle pagine che hanno effettuato l’accesso che a quelle che non l’hanno fatto, utilizzando la scheda personalizzazione. Ciò consente di mantenere un branding coerente, aggiungere elementi dell&#39;interfaccia utente personalizzati e migliorare l&#39;esperienza utente nel portale. Tutte le personalizzazioni vengono applicate a livello globale, garantendo un aspetto unificato.

#### Differenze e branding degli URL (favicon, titolo pagina)

Le pagine che non hanno effettuato l’accesso e che vi hanno effettuato l’accesso possono avere URL diversi per distinguere gli stati degli utenti. Puoi personalizzare la favicon e il titolo della pagina per il tuo portale, contribuendo a rafforzare l&#39;identità del tuo marchio. Queste funzioni sono disponibili in Experience Builder; verifica con il team tecnico lo stato più recente del supporto per i dispositivi che non hanno effettuato l&#39;accesso.

### Prestazioni e scalabilità

#### Stack condiviso e stack premium

Lo stack condiviso consente a più clienti di utilizzare il generatore di esperienze senza accesso su un&#39;infrastruttura comune, che supporta livelli di traffico standard. Lo stack premium è un&#39;opzione a pagamento che fornisce risorse dedicate, funzionalità in tempo reale e limiti di posti più elevati per i clienti con esigenze avanzate. Seleziona lo stack in base ai requisiti di traffico e business previsti.

#### Limiti di traffico e limiti di velocità

Lo stack condiviso impone limiti di traffico per garantire un utilizzo corretto tra i clienti. I tecnici implementeranno la limitazione delle tariffe per evitare che un singolo cliente utilizzi tutte le risorse. Se si pianificano campagne di marketing o si prevede un traffico elevato, coordinarsi con la progettazione per comprendere i limiti ed evitare interruzioni del servizio. La limitazione della velocità consente di mantenere la stabilità del sistema e le prestazioni per tutti gli utenti.

#### Considerazioni su multi-tenancy e SEO

La piattaforma supporta il multi-tenancy, consentendo a più clienti di ospitare i propri portali su un&#39;infrastruttura condivisa. Le pagine senza accesso sono compatibili con SEO, insieme a sitemap.xml e robots.txt per ottimizzare la visibilità dei motori di ricerca. Ciò garantisce che il portale sia individuabile e indicizzato correttamente dai motori di ricerca.

### Migrazione e rimozione

#### Transizione dalla pagina principale esistente senza accesso

Dovresti ricreare la tua home page utilizzando il nuovo Experience Builder per una maggiore flessibilità, il supporto del widget e una migliore esperienza utente. Il piano di transizione assicura interruzioni minime e supporto continuo.

#### Piano di comunicazione

I clienti che utilizzano la pagina principale precedente riceveranno una comunicazione chiara sulla tempistica della rimozione e sui passaggi di migrazione. Verrà fornito il supporto per consentire di spostare la pagina principale nella nuova piattaforma Experience Builder, in modo da trarre vantaggio dalle nuove funzioni e dagli aggiornamenti in corso.

### Supporto per localizzazione e accesso

#### Logica di fallback locale

Il sistema visualizza le pagine nelle impostazioni locali in cui sono state create. Se la lingua di un utente non è disponibile, il sistema utilizza una logica di fallback per selezionare la successiva lingua migliore disponibile. Ciò garantisce agli utenti di visualizzare sempre i contenuti in una lingua supportata, migliorando l&#39;accessibilità e la soddisfazione degli utenti.

#### Tipi di accesso supportati

L&#39;esperienza senza accesso supporta tutti i tipi di accesso disponibili in ALM, inclusi SSO e accesso standard. Gli utenti possono sfogliare i contenuti senza accedere e verrà richiesto di accedere quando necessario, ad esempio per iscriversi a un corso o accedere a funzioni personalizzate. Ciò garantisce una transizione fluida dalla navigazione al coinvolgimento.


### API senza accesso

#### API oggetto di apprendimento Amministratore

Le pagine Experience Builder e i portali headless non connessi spesso organizzano o filtrano i corsi in base al prodotto e al ruolo. L’API di Admin LO è stata migliorata per garantire che queste associazioni siano sempre accessibili per le integrazioni back-end e headless, nonché per il connettore TDA.

**Endpoint e comportamento**

Continuerai a utilizzare l’endpoint LO di amministrazione esistente:

```
GET /primeapi/v2/learningObjects/{loId}?enforcedFields[learningObject]=products,roles
```

Dove:

* loId è l’ID dell’oggetto di apprendimento (ad esempio corso:12345).
* enforcedFields[learningObject] indica all&#39;API di includere in modo esplicito i prodotti e i ruoli per l&#39;oggetto di apprendimento.

A tale scopo, assicurati che le associazioni di prodotto e ruolo degli LO siano presenti nella risposta quando richiesto tramite enforcedFields. La risposta contiene quindi, in attributi, i metadati del prodotto e del ruolo necessari per calcolare o esporre i prodotti (rec\_products) e i ruoli (rec\_roles) consigliati per Experience Builder e altri consumer.

Una chiamata tipica di un amministratore o di un&#39;integrazione ha un aspetto simile al seguente:

```
url -X GET \
 "https://{your-domain}/primeapi/v2/learningObjects/course:12345?enforcedFields[learningObject]=products,roles" \
 -H "Authorization: Bearer {admin\_token}" \
 -H "Accept: application/vnd.api+json
```

Il JSON LO restituito ha la stessa struttura di base di prima, ma ora puoi fare affidamento sui campi prodotto/ruolo presenti quando li richiedi con enforcedFields. Le integrazioni che non utilizzano enforcedFields continuano a comportarsi come prima.

#### Elenco Oggetti di apprendimento - Supporto JobAid nel filtro effectiveModifiedDate

**Scopo**

Il connettore Accesso ai dati di formazione (TDA) e le implementazioni headless devono spesso eseguire una sincronizzazione incrementale, in base alla **data effettiva di modifica** degli oggetti di apprendimento. Fino a questa versione, le risorse formative (jobAid di tipo LO) non venivano gestite correttamente se combinate con i filtri effectiveModifiedDate. Questa versione corregge questo problema in modo che le risorse formative possano essere sincronizzate in modo incrementale come corsi e percorsi di apprendimento.

**Endpoint e comportamento**

L&#39;endpoint dell&#39;elenco di oggetti di apprendimento esistente viene utilizzato con i filtri di data e il tipo di oggetto di apprendimento:

```
GET /primeapi/v2/learningObjects
 ?filter.effectiveModifiedDate.fromDate=2025-03-15T13:14:56.000Z
 &filter.effectiveModifiedDate.toDate=2025-03-20T13:14:56.000Z
 &filter.loTypes=jobAid
```

In precedenza, quando filter.loTypes=jobAid veniva combinato con un intervallo effectiveModifiedDate, il filtro escludeva effettivamente le risorse formative e la chiamata si comportava come se le risorse formative non fossero supportate.

A partire da questo aggiornamento, la chiamata restituisce solo oggetti di apprendimento JobAid il cui effectiveModifiedDate rientra nella finestra specificata.

```
{
 "links": {
 "self": "https://acapapiserver/primeapi/v2/learningObjects?page[limit]=10&filter.effectiveModifiedDate.fromDate=2026-01-19T13:14:56.000Z&filter.effectiveModifiedDate.toDate=2026-01-21T13:14:56.000Z&filter.loTypes=jobAid"
 },
 "data": [
 {
 "id": "jobAid:144968",
 "type": "learningObject",
 "attributes": {
 "authorNames": ["Author"],
 "dateCreated": "2026-01-20T08:48:55.000Z",
 "datePublished": "2026-01-20T08:48:55.000Z",
 "dateUpdated": "2026-01-20T08:48:55.000Z",
 "effectiveModifiedDate": "2026-01-05T07:31:18.000Z",
 "loType": "jobAid",
 "loFormat": "Content",
 "loResourceType": "Content",
 "localizedMetadata": [
 {
 "description": "Link jobAid new",
 "locale": "en-US",
 "name": "Link jobAid new"
 },
 {
 "description": "Link jobAid new fre",
 "locale": "fr-FR",
 "name": "Link jobAid new fre"
 }
 ],
 "relationships": {
 "authors": {
 "data": [
 { "id": "13385176", "type": "user" }
 ]
 },
 "instances": {
 "data": [
 { "id": "jobAid:144891\_-1", "type": "learningObjectInstance" }
 ]
 }
 }
 }
 }
 ]
}
```

Ciò significa che ora è possibile implementare in modo sicuro le sincronizzazioni incrementali delle risorse formative basate su effectiveModifiedDate, come già avviene per altri tipi.

Se si omette filter.loTypes=jobAid, il comportamento degli altri tipi di LO rimane invariato; la modifica interessa solo la combinazione di JobAid con tale filtro.

#### **API menu: filtro menu non connesso**

**Scopo**

Experience Builder e headless front-end necessitano di un modo semplice per recuperare il **menu senza accesso** , quello che definisce la navigazione per i visitatori pubblici. Prima di questa versione, dovevi recuperare tutti i menu e quindi applicare una logica personalizzata per identificare quale rappresentava la navigazione senza accesso. Questa versione aggiunge un semplice filtro lato server.

**Endpoint e comportamento**

Utilizzare l&#39;endpoint di elenco Menu esistente con un nuovo parametro di query:

```
GET /primeapi/v2/templates/menus?include=pages,subMenus.pages&isNonLoggedIn=true
```

I punti chiave:

* include=pages,subMenus.pages è facoltativo ma consigliato quando si desidera visualizzare i dettagli della pagina e del sottomenu nella stessa risposta.
* isNonLoggedIn=true è una novità di questa release e indica al server di restituire solo i menu contrassegnati come non connessi.

Senza il parametro isNonLoggedIn, l&#39;endpoint si comporta esattamente come prima e restituisce i menu in base al comportamento predefinito esistente. Con isNonLoggedIn=true, in genere restituisce il singolo menu utilizzato dall&#39;esperienza senza accesso per l&#39;account (poiché normalmente esiste un menu senza accesso per account).

In pratica, un cliente può ora emettere:

```
curl -X GET \
 "https://{your-domain}/primeapi/v2/templates/menus?include=pages,subMenus.pages&isNonLoggedIn=true" \
 -H "Authorization: Bearer {admin\_token}" \
 -H "Accept: application/vnd.api+json"
```

e ripristina la struttura di navigazione senza accesso con una sola chiamata, con tutte le pagine che dovrebbero essere visibili ai visitatori anonimi.

Ciò è particolarmente utile quando si crea un sito senza intestazione per cui non è stato effettuato l&#39;accesso e si desidera eseguire il mirroring della stessa navigazione utilizzata da Experience Builder o quando si esegue il debug per verificare se il menu senza accesso è stato configurato correttamente.

### Consenti elenco di domini personalizzati

Lo stack non connesso è costituito da:

* Un dominio CDN pubblico (ad esempio cpcontents.adobe.com o yourdomain.example.com) che fornisce layout, codice JSON di configurazione e risorse statiche.
* Endpoint di Elasticsearch pubblico (ES) che serve i dati del catalogo e della ricerca, ma solo se la richiesta proviene da un **dominio elencato consentito** per l&#39;account ALM.

Quando introduci un dominio personalizzato, funziona senza problemi, seguendo il processo esistente per l’aggiunta di un dominio personalizzato.

#### Prerequisiti

Prima di autorizzare un dominio personalizzato per gli utenti che non effettuano l’accesso:

1. Il dominio personalizzato è configurato per l&#39;account ALM (ad esempio, DNS per academy.yourcompany.com punta ad Adobe / Akamai e viene eseguito il provisioning dei certificati).
2. Il connettore **Accesso ai dati di formazione** è abilitato per l&#39;account.
3. La funzionalità **Experience Builder** non connesso è abilitata (lato Adobe).

Queste fasi garantiscono che:

* L&#39;account dispone di un **account JSON** non connesso (spesso indicato come accountConfig / experienceBuilderConfig), che include campi come cpDomain, almDomain, almCdnBaseUrl, esBaseUrl e i domini consentiti elencati.
* Lo stack non connesso sa dove fornire i dati e da quali domini deve accettare le richieste.

#### Funzionamento di Consenti elenchi

L’elenco degli indirizzi consentiti viene archiviato nella configurazione esportata da TDA e nello stack non connesso. Tale configurazione include:

* I domini ALM (cpDomain, almDomain).
* **URL di base CDN** per il contenuto non connesso (almCdnBaseUrl).
* **URL di base per la ricerca pubblica** (esBaseUrl).
* L’elenco dei domini che possono effettuare chiamate pubbliche senza accesso per quell’account.

Per utilizzare Experience Builder senza accesso in un dominio personalizzato:

* Il browser deve caricare il HTML non connesso da quel dominio personalizzato (o dal dominio CDN ALM non connesso, a seconda della configurazione).
* Le chiamate da tale dominio agli endpoint pubblici ES e CDN devono essere accettate. Ciò accade solo se il dominio è presente nell&#39;elenco degli indirizzi consentiti.

Questa versione aggiunge un nuovo dominio CDN non connesso, cpcontents.adobe.com, e specifica che deve essere inserito nei **domini consentiti** nel connettore TDA. Per gli utenti nativi esistenti non connessi, questo richiede un aggiornamento.

#### Elenco Consentiti di un dominio personalizzato

**Configurare il dominio personalizzato in ALM**

Utilizza Adobe per registrare il tuo dominio, ad esempio academy.yourcompany.com, come dominio personalizzato per il tuo account ALM. Aggiornare DNS per puntare ad Adobe Akamai come indicato e attendere il completamento di SSL e routing.

A questo punto, sia il traffico connesso che quello non connesso possono raggiungere ALM attraverso quel dominio, ma le chiamate di ricerca e catalogo non effettuate possono ancora essere bloccate se il dominio non è consentito.

**Abilita TDA e Experience Builder senza accesso**

Assicurati che:

* **Connettore Accesso ai dati di formazione** abilitato.
* La funzionalità **Experience Builder** non connesso è attivata per l&#39;account.

L’abilitazione di TDA crea o aggiorna il codice JSON dell’account non connesso. Per i nuovi account, per impostazione predefinita il processo consente anche l’elenco dei nuovi domini CDN non connessi (cpcontent.adobe.com), pertanto l’endpoint pubblico ES prevede chiamate da tale dominio.

Per gli account che utilizzavano già lo stack precedente non connesso, i connettori esistenti devono essere eliminati e ricreati per selezionare il nuovo dominio.

**Aggiungere il dominio personalizzato all&#39;elenco degli indirizzi consentiti**

La parte critica sta dicendo allo stack ES non connesso che academy.yourcompany.com è un&#39;origine approvata. Esistono due percorsi comuni.

1. **Riattivare il connettore TDA (semplice, self-service)**

Gli attuali utenti nativi non connessi dovranno eliminare e riattivare la connessione TDA in modo che il nuovo dominio venga automaticamente inserito nell’elenco dei domini consentiti. In questo modo si ottengono due risultati:

1. Il JSON dell’account non connesso viene rigenerato.
2. I domini consentiti vengono aggiornati per includere il nuovo dominio CDN non connesso e il dominio personalizzato.

Questa opzione è consigliata quando si dispone di un numero limitato di account e si può tollerare la disattivazione temporanea e la riattivazione del connettore.

1. **Verificare che il dominio sia effettivamente consentito**

Dopo aver consentito l&#39;inserimento nell&#39;elenco, apri il sito non connesso nel dominio personalizzato e analizza le chiamate di rete del browser.

Desideri visualizzare:

* Richieste a almCdnBaseUrl (ad esempio <https://cpcontent.adobe.com/>...) con 200/304.
* Richieste a esBaseUrl (API di ricerca pubblica, ad esempio <https://primeapps.adobe.com/almsearch/api/v1/>...) operazione riuscita, restituzione di JSON con dati di ricerca/catalogo.

Se queste chiamate restituiscono 4xx o errori espliciti che suggeriscono &quot;dominio non attendibile&quot; o &quot;origine non consentita&quot;, l&#39;elenco degli indirizzi consentiti è incompleto o non configurato correttamente e il supporto deve modificarlo.

L’LLD non connesso rileva inoltre che la configurazione dell’account può contenere un valore di dominio previsto. In fase di runtime, il sito verifica che il dominio nell&#39;URL corrisponda a quanto impostato nella configurazione; in caso contrario, l&#39;utente può essere reindirizzato a una pagina di errore. In questo modo è possibile evitare che la configurazione di un cliente sia accessibile tramite il dominio di un altro cliente.

### Utilizzo dei consigli in Experience Builder senza accesso

Experience Builder non connesso consente di creare pagine di apprendimento pubbliche in cui i visitatori possono sfogliare il catalogo e visualizzare i contenuti evidenziati prima di accedere. Anche se questi visitatori sono anonimi, puoi comunque presentare i corsi di formazione consigliati utilizzando metadati e widget.

Nell’app per Allievi che ha effettuato l’accesso, i consigli possono essere personalizzati in base al profilo, alla cronologia, alle abilità e ai progressi dell’Allievo. Nell&#39;esperienza **senza accesso**, l&#39;identità dell&#39;Allievo non è ancora presente, pertanto la piattaforma non può essere personalizzata per utente.

Recommendations in modalità senza accesso:

* **Selezionato o basato su regole**: basato su catalogo, prodotto, ruolo, etichette, tag e altri metadati.
* **Orientamento ai segmenti**: &quot;consigliato agli sviluppatori&quot;, &quot;consigliato ai partner&quot;, &quot;in primo piano per i principianti&quot;.
* **Orientamento al marketing**: utilizzato per attirare e guidare i visitatori a iscriversi una volta effettuato l’accesso.

### Metadati e API che supportano i suggerimenti

Dietro le quinte, le pagine non connesse utilizzano:

* **Connettore TDA** per esportare i metadati degli oggetti di apprendimento (corsi, percorsi, certificazioni, risorse formative) in un indice di ricerca pubblico.
* **stack di ricerca pubblico** per rispondere alle query dei widget non connessi (catalogo, ricerca, corsi e percorsi, categorie).
* L&#39;API **Admin Learning Objects** per esporre i metadati di prodotto e ruolo che possono essere utilizzati per le regole dei suggerimenti.

In questa versione, l’API degli oggetti di apprendimento (API) di amministrazione è stata estesa in modo che le associazioni di prodotti e ruoli siano disponibili in modo affidabile:

```
GET /primeapi/v2/learningObjects/{loId}?enforcedFields[learningObject]=products,roles
```

Ciò consente ai widget e alle integrazioni headless di creare consigli basati su regole utilizzando prodotti, ruoli, etichette di catalogo, tag e altri campi in modo coerente.

### Progettazione delle sezioni dei suggerimenti con i widget di Experience Builder

Puoi creare sezioni di suggerimenti su pagine non connesse combinando **widget Experience Builder** con filtri per metadati.

#### **Widget Corsi e percorsi**

Utilizza il widget **Corsi e percorsi** per visualizzare una riga o una griglia di elementi consigliati. Nella configurazione è possibile scegliere:

* Cataloghi da cui estrarre.
* Etichette di catalogo, prodotti, ruoli o tag da utilizzare come filtri.
* Indica se visualizzare corsi, percorsi, certificazioni, risorse formative o una combinazione.
* Ordinamento e numero massimo di elementi.

Ad esempio, potete creare:

* &quot;Consigliato agli sviluppatori&quot;: filtra in base a un prodotto o ruolo utilizzato per il contenuto degli sviluppatori.
* &quot;Inizia qui&quot;: filtra in base a un&#39;etichetta come &quot;Starter&quot; o &quot;Onboarding&quot;.
* &quot;In evidenza questo trimestre&quot;: filtro basato su un&#39;etichetta con limiti di tempo come featureq3-2026.

Il widget non impara dal comportamento, ma mostra tutto ciò che corrisponde alle regole di metadati definite. Dal punto di vista di un visitatore, tuttavia, sembra una striscia di consigli.

#### **Widget Categorie**

Utilizza il widget **Categorie** per consentire ai visitatori di accedere ai set di contenuti &quot;consigliati&quot;, anche se non conoscono i nomi dei prodotti.

Potete configurare porzioni che rappresentano ciascuna un segmento, ad esempio:

* &quot;Per gli amministratori&quot;
* &quot;Per i team di vendita&quot;
* &quot;Per i partner&quot;
* &quot;Per linea di prodotto&quot;

Ogni riquadro può collegarsi a:

* Pagina di un catalogo filtrato, ad esempio il catalogo filtrato in base a determinati prodotti o etichette.
* Una pagina dedicata senza accesso che utilizza corsi e percorsi preconfigurati per quel segmento.

In questo modo si ottiene un&#39;esperienza &quot;percorsi consigliati per segmento&quot; senza personalizzazione.

### Creazione di consigli basati sui segmenti

Poiché i visitatori non connessi non dispongono ancora di un profilo ALM, è utile progettare i suggerimenti **per segmento** e consentire ai visitatori di effettuare la selezione autonomamente.

1. Utilizza una **home page non registrata** che spiega brevemente a chi si rivolge l&#39;Accademia e mostra un piccolo numero di punti di ingresso del segmento (ad esempio, &quot;Sviluppatori&quot;, &quot;Commercianti&quot;, &quot;Partner&quot;, &quot;Nuovi dipendenti&quot;). Questa operazione può essere eseguita con un widget Categorie, una semplice casella Contenuto o una sezione HTML con pulsanti.
2. Per ogni segmento, crea una **pagina dedicata non connessa** in Experience Builder. In questa pagina utilizza uno o più widget di corsi e percorsi configurati con filtri che rappresentano i &quot;suggerimenti&quot; per il gruppo. Ad esempio, per &quot;Sviluppatori&quot; potete filtrare su:
   1. Catalogo = &quot;Formazione pubblica&quot;
   2. Prodotto = &quot;Adobe Experience Manager&quot;
   3. Tags = &quot;Fondamenti per sviluppatori&quot;
3. Utilizzare queste pagine di segmenti come destinazione delle campagne di marketing e come destinazione dei riquadri nella home page del sito non connesso.

I visitatori percepiscono che stanno visualizzando consigli su misura per la loro situazione, anche se la logica è definita in fase di progettazione tramite i metadati.

### Transizione da consigli non connessi a consigli personalizzati

I suggerimenti non connessi riguardano principalmente la **individuabilità** e la **conversione**. Quando i visitatori decidono di iscriversi o iniziare un corso di formazione, accedono e diventano Allievi a tempo pieno con un profilo e una cronologia.

Il flusso abituale è:

1. Un visitatore individua i contenuti attraverso le sezioni dei suggerimenti non registrate (consigli di casa, pagine di destinazione dei segmenti, righe in evidenza).
2. Fai clic su una panoramica del corso o del percorso e scegli di iscriverti o iniziare.
3. ALM richiede di registrarsi o accedere.
4. Dopo l’accesso, l’esperienza Allievo standard che ha effettuato l’accesso subentra, tra cui:
   1. &quot;Il mio apprendimento&quot;
   2. Catalogo connesso con avanzamento personale
   3. Tutti i sistemi di raccomandazione interni utilizzati per gli Allievi esistenti.

In altre parole, i consigli di accesso li aiutano a decidere cosa fare dopo e continuare.

### Come utilizzare le risorse formative nel nuovo Experience Builder non connesso

Nell&#39;**interfaccia utente**, le risorse formative partecipano a esperienze senza accesso principalmente tramite i widget che possono mostrare gli oggetti di apprendimento:

1. **Widget di corsi e percorsi**
Questo widget può mostrare più tipi di LO, incluse le risorse formative. Nelle pagine senza accesso, è possibile configurarlo per:
   1. Includere o escludere esplicitamente le risorse formative.
   2. Filtra le risorse formative per catalogo, prodotto, ruolo, etichette, tag e altri metadati.
   3. Presentali insieme a corsi e percorsi o come una striscia &quot;Risorse&quot; separata.

Ad esempio, in una pagina di destinazione pubblica è possibile configurare una striscia denominata &quot;Risorse utili&quot; che mostra solo risorse formative e un’altra striscia denominata &quot;Corsi consigliati&quot; che mostra corsi e percorsi.

1. **Pagina del catalogo e ricerca**
Le superfici **catalogo** e **ricerca** non registrate utilizzano l&#39;indice di ricerca pubblico (alimentato dal connettore Accesso ai dati della formazione). L&#39;indice ora supporta correttamente le risorse formative, pertanto:
   1. I risultati della ricerca senza accesso possono includere risorse formative.
   2. Filtri catalogo non registrati (per tipo, prodotto, tag, ecc.) possono includere risorse formative, a condizione che la configurazione dell’account e i widget siano impostati per visualizzarli.
2. **Pagine di panoramica LO**
Quando un visitatore fa clic su una risorsa formativa da un qualsiasi widget o dal catalogo, viene visualizzata una **pagina di panoramica dell&#39;LO** per tale risorsa formativa in modalità senza accesso. Da lì, possono leggere la sua descrizione e i metadati. Il download o l’utilizzo effettivo in genere richiede ancora l’accesso, ma la presenza e l’individuazione della risorsa formativa stessa vengono gestite dall’esperienza senza accesso.

### Come visualizzare le risorse formative tramite le API senza accesso

Sul **lato API**, le risorse formative sono supportate da:

1. **Connettore Accesso ai dati di formazione e ricerca pubblica**
TDA esporta i metadati della risorsa formativa insieme ad altri tipi di LO nell’indice di ricerca pubblico che serve le query di ricerca e catalogo non registrate. Questo è ciò su cui si basano Experience Builder e i front-end headless.
2. Elenco **Oggetti di apprendimento con effectiveModifiedDate**
In questa versione, l’endpoint dell’elenco di oggetti di apprendimento è stato corretto in modo che le risorse formative funzionino correttamente con il filtro effectiveModifiedDate. Ora puoi chiamare:

```
GET /primeapi/v2/learningObjects
 ?filter.effectiveModifiedDate.fromDate=2026-01-19T13:14:56.000Z
 &filter.effectiveModifiedDate.toDate=2026-01-21T13:14:56.000Z
 &filter.loTypes=jobAid
```

Prima di questa modifica, la combinazione di effectiveModifiedDate con loTypes=jobAid non restituiva le risorse formative in modo affidabile. Ciò significa che:

1. I tuoi lavori TDA o ETL possono **sincronizzare in modo incrementale le risorse formative** per esperienze senza accesso, allo stesso modo dei corsi e dei percorsi.
2. Qualsiasi implementazione headless che crea una directory pubblica della risorsa formativa può eseguire query sulle modifiche in base a effectiveModifiedDate e loType=jobAid.

**Nota**:

Nello stato senza accesso:

* Le risorse formative sono principalmente **individuabili**: i visitatori possono vedere che esistono, leggere le descrizioni e comprendere come supportano argomenti o corsi.
* Il **consumo** effettivo (download o apertura del contenuto della risorsa formativa) in genere richiede ancora l&#39;accesso, soprattutto se le risorse formative sono considerate parte di contenuto interno o con licenza.

### Modifiche nella breve descrizione nella ricerca LO (senza accesso)

Nello stack non connesso, la ricerca e l’elenco degli oggetti di apprendimento (LO) sono basati sul connettore Accesso ai dati di formazione (TDA) e su un indice di Elasticsearch pubblico. In passato, questo stack utilizzava un singolo campo di panoramica/descrizione per ogni LO. I clienti che creavano portali headless senza accesso desideravano mostrare la stessa breve descrizione sui riquadri LO visualizzata nell’interfaccia utente dell’Allievo che aveva effettuato l’accesso, anziché la sola panoramica lunga.

La modifica introduce il supporto per l&#39;LO **breve descrizione** nelle API di ricerca ed elenco non registrate:

* Per **corsi**, la semantica dell&#39;interfaccia utente esistente è:
* Le schede per l’accesso mostrano una breve descrizione (campo di 140 caratteri), se presente, altrimenti tornano alla lunga panoramica dettagliata.
* Per i **percorsi di apprendimento**, l’interfaccia utente che ha effettuato l’accesso utilizza il campo Benefit come descrizione breve, se definita, e torna alla panoramica in caso contrario.
* Per le **certificazioni** viene utilizzata una breve descrizione, con una panoramica della certificazione più lunga come fallback.
* Per **risorse formative**, viene utilizzato il campo di descrizione principale.

### Altre modifiche

#### Limitazione per cui due account non possono condividere lo stesso dominio personalizzato

Nelle architetture di Adobe Learning Manager senza accesso e con accesso, un **dominio personalizzato** (ad esempio, academy.example.com) viene considerato come una chiave univoca globale che deve essere mappata esattamente a un account ALM, pertanto la piattaforma applica una restrizione rigida in base alla quale **due account non possono condividere lo stesso dominio personalizzato**. Questo è richiesto per sicurezza, routing e SEO: il livello di routing e lo stack non connesso utilizzano il dominio per cercare la configurazione corretta dell’account (inclusi il relativo account non connesso JSON, i menu Experience Builder, il branding e gli endpoint TDA/di ricerca),

Consentendo lo stesso dominio personalizzato su due account, non sarebbe possibile garantire quali dati dell&#39;account vengono restituiti, potrebbe causare una perdita tra tenant e danneggiare gli artefatti generati come sitemap.xml e robots.txt prodotti per account ma rilevati dai motori di ricerca per host. Dal punto di vista operativo, ciò significa che quando si assegna o si sposta un dominio personalizzato, è necessario prima assicurarsi che non sia associato a nessun altro account (o cancellarlo) e gli strumenti interni di Adobe rifiuteranno i tentativi di associare lo stesso dominio a più account.

#### Cache del browser delle risorse nell’esperienza senza accesso

Nell’esperienza senza accesso di Adobe Learning Manager, la memorizzazione delle risorse nella cache dei browser è una parte fondamentale della strategia di prestazioni e scalabilità, poiché le pagine pubbliche devono gestire un traffico di marketing ampio, a volte piccante, con bassa latenza e carico di origine minimo. Risorse statiche e semistatiche come la shell di HTML senza accesso (ad esempio, index.html/guest.html), la configurazione a livello di account JSON (account.json o config.json), il layout di pagina JSON di Experience Builder (menu, layout di widget, impostazioni delle schede), CSS, JS, immagini e favicon vengono forniti da un CDN Akamai (cpcontents.adobe.com / cpcontent.adobe.com) con intestazioni di cache che incoraggiano il riutilizzo sia lato CDN che lato browser, in modo che dopo il caricamento della prima pagina il browser possa eseguire il rendering delle pagine successive senza accesso in gran parte dalla propria cache, riconvalidando solo quando necessario tramite ETag o Ultima modifica.

## Risorse formative multilingue

### Introduzione

Le risorse formative multilingue in Adobe Learning Manager (ALM) consentono agli autori e agli amministratori di fornire documenti di supporto, guide o risorse in più lingue all&#39;interno di una singola voce della risorsa formativa. Gli Allievi di diverse aree geografiche possono accedere ai materiali pertinenti nella lingua preferita, migliorando la comprensione, la conformità e l’esperienza dell’utente.

### Comportamento precedente

In precedenza, le risorse formative in ALM supportavano solo un singolo file di contenuto per risorsa formativa, anche quando il nome e la descrizione potevano essere localizzati. Per fornire la stessa risorsa in più lingue, gli autori dovevano creare risorse formative separate per ogni lingua. Ciò ha portato a duplicazioni, confusione e aumento del sovraccarico amministrativo. Non esisteva un modo unificato per gestire le risorse multilingue, il che rendeva difficile garantire la coerenza e tenere traccia dell&#39;utilizzo.

### Casi d’uso

* **Abilitazione della forza lavoro globale**: consegna di manuali di sicurezza, guide di processo o documenti di riferimento in più lingue a una forza lavoro diversificata.
* **Conformità alle normative**: assicurati che tutti i dipendenti ricevano la stessa documentazione sulla conformità nella loro lingua nativa.
* **Onboarding coerente**: fornisci elenchi di controllo di onboarding o domande frequenti nelle lingue locali per i nuovi assunti in tutto il mondo.
* **Duplicazione ridotta**: gestisci tutte le versioni linguistiche di una risorsa formativa in un&#39;unica voce, semplificando gli aggiornamenti e la creazione di report.

### Funzioni principali

* **Supporto di più lingue**: allega un file o un URL univoco per ogni lingua supportata all&#39;interno di una singola risorsa formativa.
* **Nome e descrizione localizzati**: immettere il nome e la descrizione della risorsa formativa in ogni lingua.
* **Gestione unificata**: modifica, aggiornamento e creazione di report per tutte le versioni linguistiche da un&#39;unica posizione.
* **Compatibilità con le versioni precedenti**: le risorse formative monolingua esistenti vengono replicate automaticamente in tutte le lingue aggiunte fino al caricamento di nuovi file.

### Creare una risorsa formativa multilingue

1. Accedi al ruolo Autore e seleziona **Risorse formative**.
2. Seleziona **Crea risorsa formativa**.
3. Immetti il nome e la descrizione della risorsa formativa nella lingua predefinita.
4. Aggiungi il file di contenuto principale o l’URL per la lingua predefinita.
5. Salva la risorsa formativa.

### Aggiungere altre lingue

1. Nell&#39;editor della risorsa formativa, seleziona **Aggiungi lingua**.
2. Selezionare la lingua o le lingue desiderate dall&#39;elenco.
3. Per ogni lingua aggiunta:
   * Immetti il nome e la descrizione localizzati.
   * Carica il file di contenuto corrispondente o fornisci un URL specifico per la lingua.
4. Ripetete questa operazione per tutte le lingue richieste.

### Modificare e gestire le lingue

1. Per aggiornare un file o una descrizione per una lingua specifica, selezionare la scheda Lingua e apportare le modifiche necessarie.
2. Se dopo la pubblicazione della risorsa formativa viene aggiunta una lingua, il file originale viene assegnato automaticamente alla nuova lingua fino a quando non viene caricato un file univoco.
3. Rimuovi o sostituisci i file per qualsiasi lingua in base alle esigenze.

### Publish e l’esperienza degli allievi

1. Dopo aver aggiunto tutte le lingue e tutti i file, pubblica la risorsa formativa.
2. Gli Allievi visualizzano la risorsa formativa nella lingua dei contenuti selezionati, con il file o l’URL appropriato.
3. Se la lingua di un Allievo non è disponibile, viene visualizzato il file della lingua predefinita.

### Report

1. Scarica i report delle risorse formative per visualizzare i dettagli di tutti i file e le lingue associati a ciascuna risorsa formativa.
2. I report includono la lingua, il nome file e i dati di utilizzo per il tracciamento.

### Procedure ottimali

* Traduzione accurata di nomi, descrizioni e file di contenuto.
* Rivedi e aggiorna regolarmente i file per garantire coerenza tra le lingue.
* Utilizzare chiare convenzioni di denominazione per distinguere i file in base alla lingua.
* Prova l’esperienza dell’Allievo cambiando le lingue dei contenuti per verificare la corretta distribuzione dei file.

### Risoluzione dei problemi

* **File mancante per una lingua**: viene visualizzato il file predefinito. Assicurati che in tutte le lingue sia caricato il file corretto.
* **Risorse formative precedenti**: aggiungi nuovi file di lingua per sostituire gli originali replicati automaticamente.
* **Lingua errata visualizzata**: controlla le impostazioni della lingua del contenuto dell’Allievo e la configurazione della lingua della risorsa formativa.

Le risorse formative multilingue consentono di fornire risorse di supporto a un pubblico globale in una singola voce, ridurre la duplicazione e garantire che ogni Allievo riceva le informazioni corrette nella lingua preferita. Questa funzione migliora l’accessibilità, la conformità e l’efficienza amministrativa in Adobe Learning Manager.

## Ottieni risposte con l’Assistente all’intelligenza artificiale per gli Allievi

L’Assistente all’intelligenza artificiale per gli Allievi è un assistente conversazionale basato sull’intelligenza artificiale in Adobe Learning Manager progettato per aiutarti a trovare più rapidamente le informazioni di cui hai bisogno. Ponendo domande in linguaggio naturale, è possibile ottenere spiegazioni contestuali, corsi pertinenti e recuperare informazioni dai contenuti di apprendimento, senza sfogliare manualmente i cataloghi.

### Funzionalità

* **Risposta intelligente alle domande:** gestisce le conversazioni sia a turno singolo che a turno multiplo, consentendo di porre domande in modo naturale. Le risposte derivano da corsi, percorsi di apprendimento, certificazioni e risorse formative.
* **Risposte basate sul contenuto con citazioni:** estrae informazioni direttamente dai materiali di apprendimento e include citazioni che rimandano al corso, al modulo o alla risorsa originale.
* **Ampia compatibilità dei contenuti:** supporta un&#39;ampia gamma di formati, inclusi documenti, presentazioni, video, file audio, contenuti HTML e moduli SCORM (Sharable Content Object Reference Model).
* **Esperienza utente uniforme:** disponibile come pannello laterale nelle pagine degli Allievi, mantenendo la cronologia della chat basata sulla sessione per la continuità.
* **Controlli di amministratore affidabili:** gli amministratori possono abilitare o disabilitare l&#39;assistente, limitare l&#39;accesso da parte dei gruppi di utenti e scegliere i cataloghi interni utilizzati come origine per le risposte generate dall&#39;intelligenza artificiale.

### Vantaggi

* **Accesso più rapido alle conoscenze:** ricevi risposte immediate alle tue domande, eliminando la necessità di navigare in più corsi o documenti.
* **Maggiore coinvolgimento:** le interazioni conversazionali rendono l&#39;esperienza di apprendimento più naturale, intuitiva e accessibile.
* **Migliore comprensione:** puoi porre domande di follow-up per chiarire i concetti ed esplorare gli argomenti in modo più approfondito.
* **Supporto scalabile per l&#39;apprendimento:** risposte automatizzate basate sull&#39;intelligenza artificiale che riducono al minimo la dipendenza da esperti e team di supporto specializzati.

Ulteriori informazioni su [Assistente AI per gli Allievi](/help/migrated/learners/feature-summary/learner-ai-assistant.md).

## Supporto di tracce di testo video (VTT) multilingue

Il supporto delle tracce di testo video (VTT) multilingue in Adobe Learning Manager consente agli autori di fornire sottotitoli e didascalie per contenuti video e audio in più lingue. Questa funzione semplifica la localizzazione, rendendo i corsi di formazione accessibili a un pubblico globale e garantendo la conformità agli standard di accessibilità. Gli autori possono generare, tradurre, rivedere e modificare automaticamente i file VTT direttamente all’interno della piattaforma.

### Casi di utilizzo

* **Formazione globale:** distribuisci contenuti video con sottotitoli in più lingue per raggiungere gli Allievi internazionali.
* **Conformità all&#39;accessibilità:** fornite sottotitoli agli utenti audiolesi nella lingua preferita.
* **Localizzazione più rapida:** ridurre l&#39;impegno manuale e accelerare l&#39;implementazione dei contenuti generando e traducendo automaticamente i file VTT.
* **Esperienza coerente:** assicurati che tutti gli allievi ricevano le stesse informazioni, indipendentemente dalla lingua.

### Funzioni principali

* **Generazione automatica VTT:** carica un file video o audio e genera automaticamente i sottotitoli VTT nella lingua originale.
* **Traduzione multilingue:** traduci i sottotitoli in una delle 39 lingue non inglesi supportate.
* **Revisione e modifica in-app:** rivedere, modificare e scaricare i file VTT prima della pubblicazione.
* **Notifiche:** ricezione di notifiche in-app al termine della generazione e della traduzione VTT.
* **Pubblicazione fluida:** sottotitoli finalizzati da Publish a cui gli Allievi possono accedere nella lingua scelta.

### Caricare contenuti e generare VTT

1. Accedi alla Libreria dei contenuti e seleziona **Aggiungi contenuto**.
2. Carica il file MP3 o MP4.
3. Nella finestra di dialogo di caricamento, seleziona l&#39;opzione per **Generare la traduzione**.
4. Selezionare la lingua del contenuto originale (l&#39;impostazione predefinita è la lingua del file).
5. Seleziona altre lingue di destinazione per la traduzione (fino a 39 supportate).
6. Seleziona **Salva**. Il sistema inizia a generare e a tradurre i file VTT.

### Monitorare l’avanzamento

1. Dopo il salvataggio, la nuova voce di contenuto viene visualizzata nella libreria dei contenuti.
2. Un indicatore di avanzamento mostra lo stato della generazione e della traduzione VTT.
3. Una volta completato il processo, riceverai una notifica in-app.

### Rivedere e modificare i file VTT

1. Nella Libreria dei contenuti, apri il contenuto in modalità **Modifica**.
2. Per ogni lingua, selezionate il collegamento **Revisione** accanto al file VTT.
3. In un pop-up vengono visualizzati i sottotitoli per quella lingua.
4. Modifica i sottotitoli direttamente nella finestra a comparsa o scarica il file VTT per la modifica offline.
5. Dopo aver apportato le modifiche, carica o incolla di nuovo i sottotitoli revisionati nella finestra a comparsa.
6. Salvate le modifiche.

### Sottotitoli Publish

1. Quando sei soddisfatto/a dei sottotitoli in tutte le lingue, pubblica il contenuto.
2. Durante la visualizzazione del video, gli Allievi visualizzano le opzioni per i sottotitoli in tutte le lingue pubblicate.

### Informazioni aggiuntive

* **Lingue supportate:** Tutte le 39 lingue non inglesi supportate da Adobe Learning Manager.
* **Notifiche:** gli autori ricevono una notifica al termine della generazione e della traduzione VTT.
* **Flessibilità di modifica:** i sottotitoli possono essere modificati in-app o offline e ricaricati.
* **Scalabilità:** progettata per esigenze di localizzazione e accessibilità su scala aziendale.
* **Nessuna necessità di caricamento manuale VTT:** il sistema può generare file VTT da zero utilizzando il video/audio caricato.

### Procedure consigliate

* Prima della pubblicazione, verifica sempre l’accuratezza dei sottotitoli generati automaticamente.
* Fornire traduzioni per tutti i principali gruppi di Allievi per massimizzare l’accessibilità.
* Utilizza il sistema di notifica per restare aggiornato sullo stato dell’elaborazione.
* Aggiorna regolarmente i sottotitoli se il contenuto video cambia.

### Risoluzione dei problemi

* Se la generazione VTT non riesce, assicurati che il file sia in un formato supportato (MP3/MP4).
* Per le lingue mancanti, verifica che siano supportate e selezionate durante il caricamento.
* Se i sottotitoli non sono sincronizzati, utilizza l’editor in-app per regolare i tempi.

Il supporto multilingue per il VTT consente di offrire esperienze di apprendimento video accessibili e localizzate in modo efficiente. Utilizzando la generazione automatica, la traduzione e la modifica in-app, puoi assicurarti che i tuoi contenuti raggiungano e supportino tutti gli Allievi, indipendentemente dalla lingua.

## Progettare certificati personalizzati

I certificati personalizzati in Adobe Learning Manager (ALM) consentono ad amministratori e autori di progettare, gestire ed emettere certificati personalizzati per gli Allievi. La funzione include un editor drag-and-drop, campi dinamici, supporto multilingue e sfondi generati dall&#39;intelligenza artificiale, in modo che le organizzazioni possano creare certificati con marchio senza competenze tecniche.

### Comportamento precedente

In precedenza, la creazione di certificati in ALM era limitata dalla rigidità dei modelli, dalla mancanza di personalizzazione e dalle barriere tecniche (come la modifica dei HTML). I clienti richiedevano modi più semplici per progettare certificati, aggiungere campi dinamici (come il nome dell’Allievo o dell’Istruttore) e supportare più lingue, il tutto mantenendo la coerenza del marchio e l’attrattiva visiva.

### Casi d’uso

* **Riconoscimento con marchio**: rilascia certificati con loghi, colori e font aziendali per conformità, formazione o realizzazione.
* **Personalizzazione dinamica**: compila automaticamente i nomi degli Allievi, degli Istruttori e di altri campi attivi.
* **Distribuzione multilingue**: fornisci certificati in più lingue per gli Allievi globali.
* **Design flessibile**: crea certificati orizzontali o verticali, utilizza sfondi generati dall&#39;intelligenza artificiale e visualizza l&#39;anteprima prima della pubblicazione.

### Accedere a certificati personalizzati

1. Vai alla sezione **Risultati raggiunti** nella home page dell&#39;amministratore (precedentemente denominati **Distintivi**).
2. Selezionare **Certificati** per visualizzare, creare o gestire i modelli di certificato.

### Creare un certificato

1. Selezionare **Crea certificato**.
2. Selezionate l’orientamento verticale o orizzontale.
3. Seleziona un modello esistente o inizia da un&#39;area di lavoro vuota.
4. Immettere un nome di certificato e la lingua predefinita.
5. Utilizza l’editor di trascinamento della selezione per aggiungere:
   * Campi di testo (con font, colore e opzioni di posizionamento)
   * Immagini (loghi, icone, ecc.)
   * Campi dinamici (nome dell’Allievo, nome dell’Istruttore, ecc.)
   * Sfondi di certificati (tinta unita, immagine caricata o immagine generata dall&#39;intelligenza artificiale)
6. Per sfondi generati dall&#39;intelligenza artificiale: immetti un messaggio (ad esempio, &quot;studenti in una classe&quot;) per generare sfondi utilizzando l&#39;intelligenza artificiale.

### Aggiungi campi dinamici

I campi dinamici nei certificati personalizzati di Adobe Learning Manager sono segnaposto che vengono compilati automaticamente con le informazioni pertinenti, ad esempio il nome dell’Allievo, del istruttore o altri dati specifici dell’account, al momento della generazione del certificato, consentendo di creare certificati personalizzati e sensibili al contesto senza modifiche manuali.

1. Inserisci variabili dinamiche, ad esempio il nome dell’Allievo, dell’Istruttore o di altri campi attivi.
2. I campi vengono compilati automaticamente quando viene rilasciato il certificato.

### Supporto multilingue

1. Aggiungi nuove lingue (ad esempio, francese e tedesco) al certificato.
2. Immetti il testo tradotto per ogni lingua.
3. Gestire le traduzioni e visualizzare in anteprima i certificati in ogni lingua.

### Anteprima e pubblicazione

1. Utilizza la funzione di anteprima per vedere come apparirà il certificato agli Allievi.
2. Scaricate o stampate l’anteprima per la revisione.
3. Salva come bozza per continuare a modificare in seguito o pubblica quando è pronto.

### Applicare i certificati

1. Gli amministratori possono impostare i certificati predefiniti per l’account.
2. Gli Autori possono allegare certificati a istanze specifiche degli oggetti di apprendimento (corsi, percorsi, ecc.).
3. Selezionare certificati diversi a livello di istanza in base alle esigenze.

### Gestire i certificati

1. Visualizzare i certificati pubblicati e bozze nella libreria.
2. Modifica, aggiorna o elimina i modelli in base alle esigenze.
3. I certificati possono essere riutilizzati in più istanze.

I certificati personalizzati in ALM forniscono un modo flessibile per progettare e rilasciare certificati personalizzati, con marchio e multilingue. La funzione semplifica la gestione dei certificati, migliora il riconoscimento degli Allievi e supporta le esigenze di conformità globale e branding.

## Risorse formative multilingue

Le risorse formative multilingue in Adobe Learning Manager (ALM) consentono agli autori e agli amministratori di fornire documenti di supporto, guide o risorse in più lingue all&#39;interno di una singola voce della risorsa formativa. Gli Allievi di diverse aree geografiche possono accedere ai materiali pertinenti nella lingua preferita, il che migliora l’accessibilità, la conformità e l’esperienza utente.

### Comportamento precedente

In precedenza, ALM consentiva un solo file di contenuto per risorsa formativa, anche se il nome e la descrizione potevano essere localizzati. Per fornire la stessa risorsa in più lingue, gli autori dovevano creare risorse formative separate per ogni lingua. Ciò ha portato a duplicazioni, confusione e un maggiore sforzo amministrativo. Non esisteva un modo unificato per gestire le risorse multilingue, il che rendeva difficile garantire la coerenza e tenere traccia dell&#39;utilizzo.

### Casi d’uso

* **Abilitazione della forza lavoro globale**: consegna di manuali di sicurezza, guide di processo o documenti di riferimento in più lingue a una forza lavoro diversificata.
* **Conformità alle normative**: assicurati che tutti i dipendenti ricevano la stessa documentazione sulla conformità nella loro lingua nativa.
* **Onboarding coerente**: fornisci elenchi di controllo di onboarding o domande frequenti nelle lingue locali per i nuovi assunti in tutto il mondo.
* **Duplicazione ridotta**: gestisci tutte le versioni linguistiche di una risorsa formativa in un&#39;unica voce, semplificando gli aggiornamenti e la creazione di report.

### Creare una risorsa formativa multilingue

1. Accedi al ruolo Autore e seleziona **Risorse formative**.
2. Seleziona **Crea risorsa formativa**.
3. Immetti il nome e la descrizione della risorsa formativa nella lingua predefinita.
4. Carica il file di contenuto principale o fornisci un URL per la lingua predefinita.
5. Salva la risorsa formativa.

### Aggiungere altre lingue

1. Nell&#39;editor della risorsa formativa, seleziona **Aggiungi lingua**.
2. Selezionare la lingua o le lingue desiderate dall&#39;elenco.
3. Per ogni lingua aggiunta:
   * Immetti il nome e la descrizione localizzati.
   * Carica il file di contenuto corrispondente o fornisci un URL specifico per la lingua.
4. Ripetete questa operazione per tutte le lingue richieste.

### Modificare e gestire le lingue

1. Per aggiornare un file o una descrizione per una lingua specifica, selezionare la scheda Lingua e apportare le modifiche necessarie.
2. Se dopo la pubblicazione della risorsa formativa viene aggiunta una lingua, il file originale viene assegnato automaticamente alla nuova lingua fino a quando non viene caricato un file univoco.
3. Rimuovi o sostituisci i file per qualsiasi lingua in base alle esigenze.

### Publish e l’esperienza degli allievi

1. Dopo aver aggiunto tutte le lingue e tutti i file, pubblica la risorsa formativa.
2. Gli Allievi visualizzano la risorsa formativa nella lingua dei contenuti selezionati, con il file o l’URL appropriato.
3. Se la lingua di un Allievo non è disponibile, viene visualizzato il file della lingua predefinita.

### Report

1. Scarica i report delle risorse formative per visualizzare i dettagli di tutti i file e le lingue associati a ciascuna risorsa formativa.
2. I report includono la lingua, il nome file e i dati di utilizzo per il tracciamento.

Le risorse formative multilingue in ALM consentono di fornire risorse di supporto a un pubblico globale in un&#39;unica voce, ridurre la duplicazione e garantire che ogni Allievo riceva le informazioni corrette nella lingua preferita. Questa funzione migliora l’accessibilità, la conformità e l’efficienza amministrativa in Adobe Learning Manager.

## Miglioramenti della riproduzione per i corsi generati da Captivate

L&#39;aggiornamento migliora notevolmente l&#39;esperienza di riproduzione per i contenuti Adobe Captivate all&#39;interno di ALM introducendo un&#39;interfaccia unificata e semplificata.

Il lettore ALM ora visualizza un singolo sommario consolidato, nascondendo il sommario della Captivate e fornisce indicatori di completamento chiari a livello di diapositiva, comprese tacche verdi per il tracciamento dell&#39;avanzamento visivo.

Il sistema semplifica la navigazione unendo i controlli di moduli e corsi in un’unica barra intuitiva, riducendo la possibilità di confusione per gli Allievi.

I controlli di avanzamento con riconoscimento del contesto consentono di migliorare l&#39;usabilità visualizzando le barre di avanzamento video solo sulle diapositive video e i controlli di spostamento tra diapositive solo sulle diapositive non video.

Inoltre, le note vengono ora collegate ai numeri delle diapositive anziché alle marche temporali, in modo da garantire l&#39;affidabilità delle esportazioni dei PDF e risolvere le incongruenze di formato precedenti.

## Miglioramenti all’elenco di controllo

### Supporto multilingue per elenco di controllo

Questa funzione consente di creare e gestire moduli di elenchi di controllo in più lingue. Ogni domanda, istruzione e criterio dell’elenco di controllo può essere tradotto, in modo che revisori e allievi interagiscano con l’elenco di controllo nella lingua che preferiscono. Il sistema visualizza l’elenco di controllo nella lingua dei contenuti selezionata dall’utente, migliorando l’accessibilità e la conformità per i team globali.

1. Aggiungi o modifica un modulo di un elenco di controllo nel corso.
2. Seleziona tutte le lingue che desideri supportare dalle opzioni della lingua.
3. Per ogni lingua, inserire le traduzioni per ogni domanda dell&#39;elenco di controllo, istruzione e criterio di valutazione.
4. Salva le modifiche. L’elenco di controllo viene visualizzato nella lingua del contenuto selezionato del revisore o dell’Allievo.
5. Se in seguito si aggiunge una nuova lingua, fornire le traduzioni per tutte le domande e i criteri prima della pubblicazione.
6. Quando scarichi i report dell’elenco di controllo, seleziona la lingua preferita per visualizzare il report in quella lingua.

### Ponderazione delle domande nell’elenco di controllo per le valutazioni dell’istruttore

Questa funzione consente di assegnare punteggi massimi (ponderazione) diversi a ciascuna domanda dell’elenco di controllo. È possibile riflettere la diversa importanza o difficoltà di ciascuna domanda, il che supporta valutazioni più accurate e significative. Il sistema calcola il punteggio totale in base ai dati immessi e determina se l’Allievo supera o non supera i criteri impostati.

1. Quando si aggiunge un modulo elenco di controllo, selezionare **Punteggio personalizzato**.
2. Per ogni domanda dell’elenco di controllo, imposta un punteggio massimo univoco che ne rifletta l’importanza.
3. Definisci il punteggio di superamento complessivo per l’elenco di controllo.
4. Salva e pubblica l’elenco di controllo.
5. In qualità di Istruttore o Revisore, valuta ciascun Allievo assegnando un punteggio per ogni domanda (fino al massimo impostato).
6. Il sistema calcola il punteggio totale e determina lo stato di superamento/non superamento.
7. Scarica i report dell&#39;elenco di controllo per visualizzare sia i punteggi raggiunti che i punteggi massimi per ogni domanda e il punteggio totale.

### Elenco di controllo con funzionalità di creazione dei commenti per il revisore

Questa funzione consente ai revisori di aggiungere commenti o feedback durante la valutazione dell’elenco di controllo. Puoi fornire un feedback personalizzato e actionable per ogni Allievo. Puoi anche scegliere di visualizzare il tuo nome con i tuoi commenti per la trasparenza. Tutti i commenti vengono salvati nella trascrizione dell’Allievo e inclusi nei report dell’elenco di controllo.

1. Durante l&#39;impostazione dell&#39;elenco di controllo, abilitare **Note del revisore**.
2. Facoltativamente, abilita **Mostra il nome del revisore all’Allievo** se desideri che il tuo nome venga visualizzato con i tuoi commenti.
3. Durante la valutazione, immetti commenti o feedback per l’Allievo nel campo Commenti fornito.
4. Seleziona se i commenti devono essere visibili all’Allievo.
5. Inviare la valutazione. Se questa opzione è attivata, l’Allievo vede le tue osservazioni e il tuo nome insieme ai relativi risultati.
6. Tutti i commenti vengono salvati nella trascrizione dell’Allievo e inclusi nei report dell’elenco di controllo per riferimento futuro.

## Miglioramenti della ricerca avanzata

Questa versione include il miglioramento nella ricerca nel contenuto mostrando i corsi con il contenuto corrispondente alla query di livello più alto. Inoltre, le risorse formative sono ora incluse nella classifica di ricerca avanzata.

## Equivalenti e alternative

### Panoramica

In molte organizzazioni, gli Allievi si trovano in situazioni di formazione in cui diversi corsi possono legittimamente soddisfare lo stesso requisito?ad esempio, quando un nuovo corso sostituisce uno più vecchio, quando un corso più completo può sostituirlo con uno più breve o quando è necessario offrire un corso sostitutivo speciale.

La funzione Corsi alternativi o Percorso di apprendimento offre ad ALM un modo formale per dire:

&quot;Se l’Allievo ha completato questo corso di formazione, considera che abbia soddisfatto il relativo requisito di formazione.&quot;

La funzione funziona per tutti i corsi e percorsi di apprendimento, garantisce il rispetto dei requisiti a valle quali prerequisiti e regole di conformità, e lo fa senza costringere gli Allievi a occuparsi dei contenuti ridondanti. Continua inoltre a riportare in modo accurato ciò che è stato completato direttamente rispetto a ciò che è stato soddisfatto tramite un&#39;alternativa.

Alla base, la funzione introduce il concetto di completamento alternativo: uno stato di completamento speciale creato automaticamente quando un Allievo completa un corso di formazione sorgente configurato che conta per un altro corso di formazione target.

### Equivalenza e alternative

Alcune relazioni di formazione sono bidirezionali, il che significa che ogni corso può soddisfare i requisiti dell’altro. Si tratta in effetti di uno scenario in cui due corsi di formazione sono trattati come intercambiabili. Al contrario, le relazioni unidirezionali consentono a un corso di formazione di soddisfare il requisito per un altro, ma non viceversa. ALM modella entrambi gli scenari utilizzando lo stesso meccanismo di completamento*alternativo sottostante.

* **Relazione bidirezionale:** il completamento di uno dei corsi di formazione soddisfa i requisiti dell&#39;altro.
* **Relazione unidirezionale:** il completamento del corso di formazione A soddisfa il corso di formazione B, ma il completamento del corso di formazione B non soddisfa il livello A. Ciò è comune quando una versione più recente o più completa deve essere conteggiata ai fini di un requisito precedente, ma non viceversa.

Le alternative sono più spesso utilizzate negli scenari **unidirezionali**?ad esempio, quando un corso di superset più completo copre tutto in un corso di sottoinsieme più semplice. Il completamento del soprainsieme deve soddisfare il requisito per il sottoinsieme, ma non necessariamente il contrario.

* Un corso più recente ed esteso che deve essere conteggiato ai fini di un requisito precedente.
* Un corso progettato per un pubblico specifico (ad esempio, una variante regionale o adattata all’accessibilità*e) che soddisfa ancora lo stesso requisito del corso principale.
* Una nuova versione avanzata di un corso che l’organizzazione desidera contare per un requisito precedente, ma la versione precedente non deve contare per il nuovo requisito.

In Alternative, la relazione è normalmente **unidirezionale**. Se il Corso A è un’alternativa al Corso B, il completamento di A può soddisfare i requisiti di B, ma il completamento di B non soddisfa necessariamente A.

Sia l&#39;equivalenza che l&#39;alternativa condividono lo stesso meccanismo sottostante in ALM: quando un corso di formazione di origine configurato viene completato, ALM genera automaticamente un completamento alternativo per uno o più corsi di formazione di destinazione.

### Quali problemi risolve questo?

Senza alternative ed equivalenza, amministratori e allievi si trovano ad affrontare diversi problemi ricorrenti:

* Agli Allievi viene spesso richiesto di ripetere i corsi relativi ai contenuti già completati in una versione o in un formato diverso.
* L’aggiornamento dei programmi di conformità è più semplice perché gli amministratori possono sostituire o ristrutturare i corsi di formazione senza forzare gli Allievi che hanno completato versioni precedenti a riprendere contenuti equivalenti o sostituiti.
* La logica dei prerequisiti è rigida. Se un percorso richiede come prerequisito un determinato corso, non c’è modo corretto di riconoscere che un altro corso di formazione è sufficiente.
* Le relazioni e gli audit sono più difficili. Non vi è alcun segnale formale che indichi che un requisito è stato soddisfatto tramite un completamento alternativo e nessun modo semplice per rintracciare la fonte del credito.

Le funzioni Alternative ed Equivalenza risolvono questi problemi mediante:

* Impedire agli Allievi di duplicare le attività quando le alternative sono valide.
* Consentire agli amministratori di modificare le strutture di formazione (ad esempio, scambiare un corso all’interno di un percorso) senza interrompere i completamenti per gli Allievi che hanno seguito la versione precedente.
* Consentire ai prerequisiti e ai controlli di conformità di rispettare sia i completamenti diretti sia quelli alternativi o equivalenti.
* Registrare chiaramente, nelle trascrizioni e nei rapporti, se un corso di formazione è stato completato direttamente o è stato soddisfatto tramite un rapporto alternativo, insieme al quale l’addestramento è servito come fonte.

### Funzionamento concettuale della funzione

La funzione si basa su tre idee principali: **relazioni**, **completamento alternativo** e **comportamento downstream**.

#### Rapporti tra i corsi di formazione

Gli Amministratori definiscono le relazioni tra corsi e percorsi di apprendimento. Per ogni relazione, è possibile scegliere una **origine** e una o più **destinazioni**. Un singolo corso può avere fino a 30 obiettivi, a seconda del numero di corsi di formazione precedenti o correlati che deve soddisfare.

Per Equivalenza, gli amministratori possono rendere la relazione **bidirezionale** se desiderano che entrambi i corsi di formazione si soddisfino a vicenda. Per le alternative, gli amministratori normalmente mantengono la direzione di un*senso per indicare che sono consentite solo alcune sostituzioni.

Queste relazioni vengono memorizzate a livello di formazione, non a livello di Allievo. Una volta configurati e abilitati, si applicano a tutti i completamenti attuali e futuri del corso di formazione di origine, in base alle impostazioni a livello di account*ad esempio se il completamento retroattivo è abilitato o meno.

### Completamento alternativo

Quando un Allievo completa un corso di formazione di origine, ALM esamina tutte le relazioni alternative o equivalenti configurate e, per ogni corso di formazione di destinazione pertinente, crea un **record di completamento alternativo**. Questo record è diverso da un normale completamento:

* Contrassegna il corso di formazione di destinazione per l’Allievo ma tiene traccia del completamento tramite alternanza o equivalenza piuttosto che direttamente.
* Registra quale addestramento sorgente è stato utilizzato per soddisfare la destinazione.
* È memorizzato in una struttura dedicata in modo che il reporting possa distinguere tra completamenti diretti e alternativi.

Gli Allievi vedranno il completamento alternativo anche se non sono iscritti. Il report Trascrizione Allievo (LT) include solo i record dei corsi di formazione a cui l’Allievo si è iscritto.

### Esperienza dell’app per Allievi per completamenti alternativi e equivalenti

I completamenti alternativi ed equivalenti vengono presentati in modo distinto nell’app per allievi, in modo che gli allievi possano capire chiaramente in che modo è stato soddisfatto un requisito di formazione, mantenendo la coerenza con le trascrizioni e i report.

#### Comportamento scheda LO

#### Stato di completamento alternativo

Quando un Allievo completa un corso di formazione tramite una relazione alternativa o equivalente, la scheda Oggetto di apprendimento (LO) mostra uno stato distinto come **Completato tramite alternativo**.\
Questa distinzione visiva aiuta gli Allievi a distinguere tra completamenti diretti e completamenti concessi tramite relazioni configurate.

#### Indicatore del metodo di completamento

La scheda LO include un indicatore del metodo di completamento (ad esempio, un&#39;etichetta o un&#39;icona) per mostrare che il completamento è stato raggiunto tramite un **alternativo**.\
Se un completamento alternativo viene successivamente revocato a causa di modifiche quali il completamento retroattivo o l&#39;eliminazione del corso di formazione di origine, la scheda LO viene aggiornata in modo da riflettere **Alternativo (revocato)**.

#### Dettagli sulla trasparenza e sull’audit

Gli Allievi possono aprire la scheda LO per visualizzare ulteriori dettagli, tra cui:

* Il corso o il percorso di apprendimento di origine che ha concesso il completamento alternativo
* Data di completamento associata al corso di formazione di origine

Ciò garantisce la trasparenza e supporta le verifiche di audit e conformità.

#### Filtraggio e visualizzazioni

#### Filtro metodo di completamento

L’app per Allievi fornisce un filtro che consente loro di distinguere tra:

* Completamenti **diretti**
* **Completamenti alternativi**
* **Tutti** i completamenti

Ciò consente agli Allievi di comprendere rapidamente in che modo sono stati soddisfatti i loro requisiti di apprendimento.

#### Visualizzazioni Trascrizione e avanzamento

Il filtro per il metodo di completamento è disponibile nelle visualizzazioni Allievo*rivolto verso il volto, ad esempio:

* Trascrizioni dell’apprendimento
* Sezioni di verifica avanzamento e completamento

Questi pareri indicano chiaramente quali corsi di formazione sono stati completati direttamente e quali sono stati soddisfatti mediante alternative o equivalenza.

#### Allineamento report

La logica di filtro nell’app per Allievi è allineata alla colonna **Metodo di completamento** utilizzata nei report.\
Ciò garantisce coerenza tra ciò che gli Allievi vedono nell’interfaccia utente e ciò che gli Amministratori vedono nelle esportazioni e nei report di conformità.

#### Termina *a* flusso finale

#### Per gli Allievi

1. Passa a **Il mio apprendimento** o **Corsi completati** nell’app per Allievi.
2. Rivedi le schede LO per identificare i corsi di formazione contrassegnati come **Completati tramite Alternativo**.
3. Apri una scheda LO per visualizzare i dettagli sul corso di formazione di origine e la data di completamento.
4. Utilizza il menu dei filtri nelle visualizzazioni Trascrizione o Elenco corsi per selezionare **Diretto**, **Alternativo** o **Tutto**.
5. Esamina l’elenco aggiornato in base al metodo di completamento selezionato.

#### Per amministratori e autori

1. Configura relazioni equivalenti o alternative tra corsi o percorsi di apprendimento nell’interfaccia di amministrazione.
2. Verifica che i completamenti alternativi si riflettano correttamente sulle schede LO e nei filtri rivolti all’Allievo*.
3. Utilizza le visualizzazioni e i report degli Allievi per confermare la coerenza tra l’interfaccia utente e i dati esportati.
4. Se un corso di formazione di origine viene ritirato o eliminato, verifica che le schede LO interessate vengano aggiornate di conseguenza (ad esempio, visualizzando **Alternativo (revocato)** quando applicabile).

## Comportamento di completamento e incompletamento retroattivo

ALM supporta il completamento retroattivo e l&#39;incompletamento retroattivo per garantire che le relazioni alternative ed equivalenti rimangano accurate nel tempo, anche quando le relazioni vengono create, modificate o rimosse dopo che gli Allievi hanno già completato il corso di formazione.

### Completamento retroattivo

#### Definizione

Quando il completamento retroattivo è abilitato, gli Allievi che hanno completato un corso di origine in passato ricevono automaticamente un completamento alternativo per il corso di destinazione se in seguito viene creata una relazione equivalente o alternativa.\
Ciò garantisce che l’apprendimento storico venga rispettato senza richiedere agli Allievi di riprendere i corsi di formazione.

#### Come funziona

1. Un amministratore abilita il completamento retroattivo a livello di account.
2. L’Amministratore definisce una relazione equivalente o alternativa tra un corso di formazione di origine e uno di destinazione.
3. Il sistema analizza i record di completamento cronologici per il corso di formazione di origine.
4. Agli Allievi idonei viene concesso un completamento alternativo per il corso di formazione di destinazione.
5. Questi record vengono visualizzati come **Completati tramite Alternativo** nelle trascrizioni e nei report degli Allievi.

### Incompletamento retroattivo

#### Definizione

Quando l’opzione Incompletamento retroattivo è abilitata, i completamenti alternativi vengono revocati se la relazione equivalente o alternativa sottostante viene rimossa o se il corso di formazione di origine viene eliminato.\
Ciò garantisce che il sistema rifletta le relazioni di formazione correnti e valide.

#### Come funziona

1. Un amministratore abilita il completamento retroattivo a livello di account.
2. L’Amministratore rimuove una relazione alternativa o equivalente oppure elimina il corso di formazione di origine.
3. Il sistema identifica gli Allievi che hanno ricevuto un completamento alternativo tramite la relazione interessata.
4. I record di completamento alternativi corrispondenti vengono revocati.
5. I record revocati sono contrassegnati come **Alternativi (revocati)** nelle trascrizioni e nei report per la visibilità del controllo.

### Impatto sui prerequisiti

I completamenti alternativi, inclusi quelli concessi retroattivamente, vengono trattati come completamenti validi durante la valutazione dei prerequisiti.\
Se un Allievo ha completato **tramite Alternativa**, può continuare con i corsi che richiedono il corso di destinazione.

Se un completamento alternativo viene successivamente revocato tramite incompletamento retroattivo, l’Allievo può perdere l’idoneità ai corsi che dipendevano da tale prerequisito.

### Impatto su percorsi di apprendimento e certificazioni

I completamenti alternativi contribuiscono al progresso e al completamento dei percorsi di apprendimento e delle certificazioni.\
Gli Allievi possono avanzare o completare questi programmi quando i corsi di formazione richiesti vengono soddisfatti tramite relazioni alternative o equivalenti.

Se un completamento alternativo viene revocato, i percorsi di apprendimento o le certificazioni interessati possono perdere lo stato di avanzamento o completamento fino a quando il requisito non viene soddisfatto tramite un completamento valido.

### Fine *al* fine del flusso di lavoro

#### Abilitazione del completamento o incompletamento retroattivo

1. Gli amministratori passano alle impostazioni account e abilitano il completamento retroattivo e/o l’incompletamento retroattivo.
2. Gli Amministratori creano, modificano o rimuovono relazioni equivalenti o alternative tra i corsi di formazione.

#### Azioni di sistema

* **Per il completamento retroattivo:**\
  Il sistema concede completamenti alternativi in base ai completamenti dell&#39;origine cronologica.
* **Per incompletamento retroattivo:**\
  Il sistema revoca i completamenti alternativi quando vengono rimosse le relazioni o vengono eliminati i corsi di formazione di origine.

#### Esperienza di apprendimento

Gli Allievi visualizzano gli stati di completamento aggiornati sulle schede LO e nelle trascrizioni, ad esempio:

* **Completato tramite alternativo**
* **Alternativo (Revocato)**

I controlli dei prerequisiti, l’avanzamento del percorso di apprendimento e lo stato della certificazione vengono aggiornati in modo dinamico in base allo stato di completamento corrente.

#### Relazioni e audit

Tutte le modifiche retroattive sono riportate nel report Trascrizione Allievo (LT).\
I report distinguono chiaramente tra completamenti diretti, completamenti alternativi e completamenti alternativi revocati per supportare conformità, indagini di supporto e audit.

### Comportamento di completamento e incompletamento retroattivo

ALM supporta il completamento retroattivo e l&#39;incompletamento retroattivo per garantire che le relazioni alternative ed equivalenti rimangano accurate nel tempo, anche quando le relazioni vengono create, modificate o rimosse dopo che gli Allievi hanno già completato il corso di formazione.

#### Completamento retroattivo

#### Definizione

Quando il completamento retroattivo è abilitato, gli Allievi che hanno completato un corso di origine in passato ricevono automaticamente un completamento alternativo per il corso di destinazione se in seguito viene creata una relazione equivalente o alternativa.\
Ciò garantisce che l’apprendimento storico venga rispettato senza richiedere agli Allievi di riprendere i corsi di formazione.

#### Come funziona

1. Un amministratore abilita il completamento retroattivo a livello di account.
2. L’Amministratore definisce una relazione equivalente o alternativa tra un corso di formazione di origine e uno di destinazione.
3. Il sistema analizza i record di completamento cronologici per il corso di formazione di origine.
4. Agli Allievi idonei viene concesso un completamento alternativo per il corso di formazione di destinazione.
5. Questi record vengono visualizzati come **Completati tramite Alternativo** nelle trascrizioni e nei report degli Allievi.

#### Incompletamento retroattivo

#### Definizione

Quando l’opzione Incompletamento retroattivo è abilitata, i completamenti alternativi vengono revocati se la relazione equivalente o alternativa sottostante viene rimossa o se il corso di formazione di origine viene eliminato.\
Ciò garantisce che il sistema rifletta le relazioni di formazione correnti e valide.

#### Come funziona

1. Un amministratore abilita il completamento retroattivo a livello di account.
2. L’Amministratore rimuove una relazione alternativa o equivalente oppure elimina il corso di formazione di origine.
3. Il sistema identifica gli Allievi che hanno ricevuto un completamento alternativo tramite la relazione interessata.
4. I record di completamento alternativi corrispondenti vengono revocati.
5. I record revocati sono contrassegnati come **Alternativi (revocati)** nelle trascrizioni e nei report per la visibilità del controllo.

#### Impatto sui prerequisiti

I completamenti alternativi, inclusi quelli concessi retroattivamente, vengono trattati come completamenti validi durante la valutazione dei prerequisiti.\
Se un Allievo ha completato **tramite Alternativa**, può continuare con i corsi che richiedono il corso di destinazione.

Se un completamento alternativo viene successivamente revocato tramite incompletamento retroattivo, l’Allievo può perdere l’idoneità ai corsi che dipendevano da tale prerequisito.

#### Impatto su percorsi di apprendimento e certificazioni

I completamenti alternativi contribuiscono al progresso e al completamento dei percorsi di apprendimento e delle certificazioni.\
Gli Allievi possono avanzare o completare questi programmi quando i corsi di formazione richiesti vengono soddisfatti tramite relazioni alternative o equivalenti.

Se un completamento alternativo viene revocato, i percorsi di apprendimento o le certificazioni interessati possono perdere lo stato di avanzamento o completamento fino a quando il requisito non viene soddisfatto tramite un completamento valido.

#### Fine *al* fine del flusso di lavoro

#### Abilitazione del completamento o incompletamento retroattivo

1. Gli amministratori passano alle impostazioni account e abilitano il completamento retroattivo e/o l’incompletamento retroattivo.
2. Gli Amministratori creano, modificano o rimuovono relazioni equivalenti o alternative tra i corsi di formazione.

#### Azioni di sistema

* **Per il completamento retroattivo:**\
  Il sistema concede completamenti alternativi in base ai completamenti dell&#39;origine cronologica.
* **Per incompletamento retroattivo:**\
  Il sistema revoca i completamenti alternativi quando vengono rimosse le relazioni o vengono eliminati i corsi di formazione di origine.

#### Esperienza di apprendimento

Gli Allievi visualizzano gli stati di completamento aggiornati sulle schede LO e nelle trascrizioni, ad esempio:

* **Completato tramite alternativo**
* **Alternativo (Revocato)**

I controlli dei prerequisiti, l’avanzamento del percorso di apprendimento e lo stato della certificazione vengono aggiornati in modo dinamico in base allo stato di completamento corrente.

#### Relazioni e audit

Tutte le modifiche retroattive sono riportate nel report Trascrizione Allievo (LT).\
I report distinguono chiaramente tra completamenti diretti, completamenti alternativi e completamenti alternativi revocati per supportare conformità, indagini di supporto e audit.

### Webhook per equivalenti e alternative

ALM fornisce eventi webhook dedicati per completamenti equivalenti e alternativi per supportare automazione, integrazioni e sincronizzazione con sistemi esterni.

Questi eventi consentono ai consumatori esterni di distinguere in modo affidabile tra completamenti diretti e completamenti concessi attraverso relazioni alternative o equivalenti.

#### Panoramica

Quando un Allievo completa un corso tramite una relazione alternativa o equivalente, ALM attiva un evento webhook separato dal webhook di completamento del corso standard.\
Ciò garantisce che le integrazioni possano rispondere in modo diverso a completamenti alternativi, se necessario.

Gli eventi webhook vengono attivati anche quando si verifica un completamento retroattivo o un incompletamento retroattivo, che copre gli aggiornamenti storici e le modifiche delle relazioni.

#### Comportamento evento webhook

* Un evento webhook distinto viene attivato quando un Allievo riceve lo stato **Completato tramite Alternativa** per un corso di destinazione.
* L’evento viene generato quando l’Allievo completa un corso di origine configurato che soddisfa la destinazione tramite una relazione equivalente o alternativa.
* Questo webhook non viene attivato per il completamento diretto del corso.
* Quando l’opzione completamento retroattivo o incompletamento retroattivo è abilitata, gli eventi webhook vengono emessi per ogni Allievo interessato e corso di destinazione.

#### Dettagli payload webhook

Il payload del webhook di completamento alternativo include i seguenti attributi chiave:

* **ID Allievo**\
  Identifica l’Allievo che ha ricevuto il completamento alternativo.

* **Corso di origine**\
  Il corso o il percorso di apprendimento completato direttamente dall’Allievo.

* **Corso di destinazione**\
  Il corso contrassegnato come completato tramite la relazione alternativa o equivalente.

* **Metodo di completamento**\
  Indica che il metodo di completamento è **alternativo**.

* **Data di completamento**\
  Derivato dalla data di completamento del corso di origine.

* **Tipo di relazione**\
  Specifica se la relazione è **equivalente** o **alternativa**.

Per gli scenari di incompletamento retroattivo, gli eventi webhook indicano che un completamento alternativo esistente è stato revocato.

#### Considerazioni sull&#39;integrazione

I sistemi esterni possono utilizzare questi eventi webhook per:

* Aggiorna record Allievo
* Sincronizzare lo stato di completamento
* Attivare notifiche o flussi di lavoro a valle
* Gestisci audit trail per scopi di conformità

I consumer di webhook devono distinguere esplicitamente tra i completamenti **diretti** e **alternativi**.\
I completamenti alternativi non concedono premi di abilità, distintivi o gamification e devono essere gestiti di conseguenza nei sistemi a valle.

### Impatto del ritiro e dell’eliminazione dei corsi di formazione sorgente in equivalenti e alternative

Lo stato del ciclo di vita di un corso di formazione di origine (ritirato o eliminato) influisce direttamente sul modo in cui i completamenti alternativi ed equivalenti vengono mantenuti per gli Allievi. ALM gestisce questi scenari in modo diverso per mantenere l&#39;accuratezza storica, assicurando al contempo la validità delle relazioni correnti.

#### Ritiro del corso di formazione di origine

##### Definizione

Se un corso viene ritirato, non è più disponibile per nuove iscrizioni, ma viene mantenuto nel sistema a scopo di riferimento storico, report e audit.

##### Impatto

* I completamenti alternativi esistenti concessi tramite il corso di origine ritirato restano validi.
* Gli Allievi che hanno completato in precedenza il corso di origine continuano a sostenere il completamento alternativo per il corso di destinazione.
* Il corso ritirato non genera nuovi completamenti alternativi, poiché non può essere completato da nuovi allievi.
* Le trascrizioni e i report degli Allievi continuano a visualizzare **Completato tramite Alternativo** per gli Allievi interessati.

#### Eliminazione dei corsi di formazione di origine

#### Definizione

L’eliminazione di un corso lo rimuove completamente dal sistema, compresi i record di completamento e le relazioni configurate.

#### Impatto

* Se l’opzione Incompletamento retroattivo è abilitata, tutti i completamenti alternativi concessi tramite il corso di origine eliminato vengono revocati.
* Le trascrizioni e i report degli Allievi vengono aggiornati per mostrare **Alternativo (revocato)** per il controllo e la visibilità della conformità.
* Gli Allievi potrebbero perdere lo stato di avanzamento o completamento nei percorsi di apprendimento, nelle certificazioni o nei prerequisiti che dipendevano dal completamento alternativo revocato.
* Non è possibile concedere ulteriori completamenti alternativi dal corso eliminato.

#### Flusso di lavoro

1. Un Amministratore ritira o elimina il corso di origine utilizzando l’interfaccia di amministrazione.
2. Il sistema valuta tutti i completamenti alternativi ed equivalenti derivati dal corso di origine.
3. Lo stato di completamento viene aggiornato in base allo stato del corso:
   * **Ritirato:** i completamenti alternativi esistenti rimangono invariati.
   * **Eliminati:** completamenti alternativi revocati se l&#39;incompletamento retroattivo è abilitato.
4. Le trascrizioni e i report degli Allievi riflettono lo stato aggiornato per supportare i requisiti di conformità e audit.

### Nessun concatenamento delle relazioni

ALM non supporta il concatenamento di relazioni alternative o equivalenti. I completamenti alternativi vengono concessi solo per relazioni configurate direttamente e non si sovrappongono a più livelli di corsi.

#### Concetto: nessun concatenamento delle relazioni

#### Definizione

Per concatenamento si intende la possibilità di consentire la propagazione di relazioni alternative o equivalenti tra più corsi.\
Ad esempio, se il Corso A è un’alternativa al Corso B e il Corso B è un’alternativa al Corso C, il concatenamento implicherebbe che il completamento del Corso A conceda il completamento del Corso C.

#### Policy

Concatenamento non supportato.\
Le relazioni alternative ed equivalenti vengono valutate solo a un singolo livello. Il completamento di un corso di origine consente il completamento alternativo solo al corso o ai corsi di destinazione immediati, non a qualsiasi destinazione a valle.

#### Flusso di lavoro

#### Impostazione delle relazioni

Un amministratore definisce relazioni alternative o equivalenti tra i corsi, ad esempio:

* Corso A → Corso B
* Corso B → Corso C

#### Evento di completamento

Un Allievo completa direttamente il corso A.

#### Azione di sistema

* Se viene definita la relazione A → B, il sistema concede un completamento alternativo per il corso B.
* Il sistema non consente il completamento alternativo per il corso C, anche se esiste una relazione B → C.

#### Requisito di completamento diretto

Per ricevere un completamento alternativo per il corso C, l’Allievo deve:

* Completamento diretto del corso B oppure
* Completa un corso configurato in modo esplicito come alternativa diretta o equivalente per il corso C.

### Implicazioni

#### Nessun vantaggio indiretto

Gli Allievi non possono ricevere i crediti di completamento per i corsi nelle fasi successive di una catena di relazioni a meno che ciascun corso (o il suo alternativo diretto) non venga completato.\
Ciò garantisce che i requisiti di apprendimento siano soddisfatti in modo esplicito e prevedibile.

#### Audit e reporting semplificati

I report e le trascrizioni degli allievi visualizzano i completamenti alternativi solo per le relazioni dirette.\
In questo modo si evitano audit trail complessi e multi-hop e si garantisce chiarezza durante la revisione delle modalità di concessione di un completamento.

### Condivisione del catalogo con account condivisi tra pari: relazioni non condivise

La condivisione del catalogo consente la condivisione degli oggetti di apprendimento (LO) tra account condivisi tra pari, ma le relazioni alternative e equivalenti vengono gestite in modo indipendente all’interno di ciascun account e non vengono condivise.

#### Concetto: condivisione di cataloghi e relazioni

#### Condivisione catalogo

Gli account possono condividere cataloghi con account condivisi tra pari per fornire accesso a corsi, percorsi di apprendimento e altri oggetti di apprendimento negli account.

#### Relazione non condivisa

Le relazioni alternative, equivalenti e di completamento alternativo configurate nell’account di origine non vengono condivise o replicate quando un catalogo viene condiviso.\
Ogni account gestisce e valuta le proprie relazioni in modo indipendente.

### Flusso di lavoro

#### Condivisione catalogo

Un amministratore dell&#39;account **A** condivide un catalogo contenente oggetti di apprendimento con **Account B**.

#### Configurazione delle relazioni

Per l’account A possono essere definite relazioni alternative o equivalenti tra gli oggetti di apprendimento nel catalogo condiviso.

#### Accesso all’account condiviso tra pari

L’account B riceve l’accesso agli oggetti di apprendimento condivisi ma non eredita alcuna relazione alternativa o equivalente configurata nell’account A.

#### Gestione indipendente

Se l’account B richiede un comportamento alternativo o equivalente, l’amministratore dell’account B deve configurare manualmente le relazioni all’interno dell’account.

#### Implicazioni

#### Nessuna propagazione automatica delle relazioni

Le relazioni alternative ed equivalenti non sono automaticamente disponibili negli account condivisi tra pari tramite condivisione del catalogo.

#### È richiesta la configurazione manuale

Ogni account condiviso tra pari è responsabile della definizione e della gestione delle proprie relazioni per gli oggetti di apprendimento condivisi.

#### Considerazioni sulla coerenza

Il comportamento di completamento, il soddisfacimento dei prerequisiti e la creazione di rapporti possono differire tra account a meno che le relazioni non siano intenzionalmente allineate tramite la configurazione manuale.


### Comportamento a valle

Una volta che esiste un completamento alternativo per un corso di formazione di destinazione, ALM lo utilizza nei controlli a valle:

* Se il corso di formazione di destinazione è un **prerequisito** per altri corsi di formazione, l’Allievo è idoneo per tali corsi di formazione come se avesse completato la destinazione.
* Se la destinazione è un **corso obbligatorio in un percorso di apprendimento**, la logica di completamento del percorso può considerare che l’Allievo abbia completato quella parte e procedere a contrassegnare il percorso come completato quando vengono soddisfatte altre condizioni.
* La conformità e altre dashboard come ad esempio Dashboard di successo del gruppo, che si basano sul rispetto di un requisito di formazione, possono includere Allievi che dispongono solo di completamenti alternativi.

Il sistema distingue tra completamento effettivo e completamento alternativo in modo che:

* Se l’Allievo in seguito segue direttamente il corso di formazione di destinazione e lo completa, questo completamento diretto può ignorare la necessità di un completamento alternativo.
* Se la relazione tra origine e destinazione viene rimossa o modificata, ALM può rimuovere o regolare i completamenti alternativi senza toccare i completamenti originali, a condizione che gli incompletamenti retroattivi siano abilitati per l&#39;account.

I completamenti alternativi sono progettati per non interferire con l’effettiva attività dell’Allievo nel corso di formazione di destinazione. Agiscono come una sovrapposizione che può essere rivista se le relazioni cambiano.