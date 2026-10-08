---
description: Scopri come creare, configurare e pubblicare un ruolo di istruttore virtuale, dalla configurazione di persone e argomenti alle impostazioni avanzate e di punteggio
jcr-language: en_us
title: Creazione e pubblicazione di un ruolo di istruttore virtuale
exl-id: f37e93ef-6d76-4b7c-b4c3-f3f8c57b143c
product_v2:
  - id: ed12e5b7-96e3-45e7-a17f-de222065ebcb
    internal-label: Learning Manager
source-git-commit: c061ccbefe8d40154220587796062d335e35de77
workflow-type: tm+mt
source-wordcount: '4850'
ht-degree: 0%
---

# Creazione e pubblicazione di un ruolo di istruttore virtuale

Crea uno scenario di gioco di ruolo dell’intelligenza artificiale in Adobe Learning Manager Virtual Coach in modo che gli Allievi possano praticare conversazioni reali come parte di un corso o di una risorsa formativa. Questo articolo descrive l’intero processo per creare un ruolo di istruttore virtuale: dalla scelta di un modello alla pubblicazione nella libreria dei contenuti.

Prima di iniziare, verifica che Adobe Learning Manager Virtual Coach sia abilitato per il tuo account e di aver effettuato l&#39;accesso come autore. L’istruttore virtuale crea ogni ruolo dai materiali e dai dettagli tempestivi forniti, non inserendo automaticamente i contenuti dei corsi esistenti dell’organizzazione. Se non lo hai già fatto, [raccogli i materiali per un ruolo di istruttore virtuale](/help/migrated/authors/feature-summary/virtual-coach/gather-materials-for-virtual-coach-role-play.md) prima di iniziare.

Per creare uno scenario di gioco di ruolo dell&#39;intelligenza artificiale in Virtual Coach:
1. Nel pannello di navigazione a sinistra, seleziona **Allenatore virtuale** e quindi **Crea ora**.

   ![](/help/migrated/authors/feature-summary/assets/virtual_coach1.png)

2. Nella sezione **In primo piano**, scegli un modello **Single-Persona** o **Multi-Persona**. In questo esempio, si presume che questo gioco di ruolo sia basato su un singolo personaggio. Per i passaggi che coinvolgono più persone, consulta [gioco di ruolo multi-persona](#configure-a-multi-persona-role-play)

   ![](/help/migrated/authors/feature-summary/assets/virtual_coach2.png)

   Viene visualizzata la finestra **Crea ruolo**.

   ![](/help/migrated/authors/feature-summary/assets/virtual_coach14.png)

3. Carica materiale sorgente facoltativamente, quindi seleziona **Crea in comproprietà con AI**.
4. Configura il personaggio, l’apertura della conversazione e gli argomenti di valutazione.
5. Seleziona **Modifica** nella sezione **Argomenti da trattare**. Impostare gli spessori di punteggio e gli argomenti **Crea o Interrompi**.
6. Ognuna delle sezioni può essere modificata in questo modo.
7. Se si è soddisfatti del contenuto, selezionare **Approva contenuto e continuare**.

   ![](/help/migrated/authors/feature-summary/assets/virtual-coach16.png)

8. Visualizza in anteprima il ruolo e quindi **Publish**.

   ![](/help/migrated/authors/feature-summary/assets/virtual_coach17.png)

## Apri Virtual Coach e inizia un gioco di ruolo

Esistono due modi per creare un ruolo di istruttore virtuale: iniziare da un modello o crearne uno da zero con l’Assistente alla creazione congiunta dell’intelligenza artificiale. Questa sezione descrive gli edifici da zero.

1. Accedi a Adobe Learning Manager come autore.
2. Seleziona **Allenatore virtuale** nel riquadro di navigazione a sinistra.

   ![](/help/migrated/authors/feature-summary/assets/virtual_coach1.png)
   *Per iniziare a creare un gioco di ruolo, seleziona Istruzione virtuale nella sezione Crea del riquadro di navigazione a sinistra.*

3. Nella pagina **Allenatore virtuale**, seleziona **Crea ora**.
4. Selezionate un modello dalla sezione **In evidenza** o **Modelli disponibili**. I modelli in primo piano includono due opzioni per creare da zero:
   - **Single-Persona Role-Play (AI Assistant)**: l’Allievo interagisce con un personaggio AI. Utilizzalo per una conversazione con un cliente, una discussione sulla leadership, una chiamata di individuazione o una conversazione di coaching.
   - **Programma di ruolo per più persone (beta)**: l’Allievo interagisce con un massimo di quattro membri dell’intelligenza artificiale nella stessa conversazione. Utilizzare questa opzione per la revisione di un comitato esecutivo, un gruppo di esperti di approvvigionamento, finanze e legale o una negoziazione con i clienti che coinvolge diversi stakeholder, ad esempio uno scenario di preparazione per il lancio di un prodotto in cui un rappresentante deve presentare una nuova offerta a un responsabile finanziario, un responsabile acquisti, un Director IT e un promotore dell&#39;utente finale in una sessione.

   ![](/help/migrated/authors/feature-summary/assets/virtual_coach2.png)
   *Per creare uno scenario da zero, scegli Single-Persona Role-Play o Multi-Persona Role-Play dalla sezione In primo piano oppure seleziona un modello predefinito di seguito.*

   Per questo esempio, seleziona **Single-Persona Role-Play (AI Assistant)** dalla sezione **In primo piano**. Per iniziare da uno scenario già pronto, consulta [Creare un ruolo utilizzando un modello Allenatore virtuale](/help/migrated/authors/feature-summary/virtual-coach/create-role-play-using-virtual-coach-template.md).
5. Facoltativamente, seleziona **Carica file** per aggiungere documenti di supporto, ad esempio un foglio dati del prodotto, una playbook o una registrazione di chiamata. L’Assistente alla creazione congiunta dell’intelligenza artificiale le utilizza per creare uno scenario più accurato. Ignora questo passaggio se non hai file pertinenti.
6. Seleziona **Co-Crea Con IA**. Quando viene visualizzato il messaggio di conferma, seleziona **Genera**.
7. Immetti una descrizione per il tuo ruolo. Utilizzare una descrizione che descriva lo scenario, ad esempio `Handling price objections in enterprise sales` o `Pitching our new product to a buying committee`.
8. Continua la conversazione con l&#39;assistente AI, aggiungendo più contesto sullo scenario. L’assistente spiega che un ruolo ha tre componenti principali: **Panoramica** (titolo e contesto di conversazione), **Persona IA** (nome, organizzazione, ruolo, sfondo, dubbi e così via) e **Argomenti di valutazione** (i criteri utilizzati per assegnare un punteggio agli Allievi) e chiede se desideri creare questi passaggi o generarli tutti contemporaneamente.
9. Continua ad aggiungere informazioni o seleziona **Approva contenuto e continua** quando sei soddisfatto.

## Configurare le impostazioni di gioco dei ruoli

Dopo aver creato un ruolo di istruttore virtuale utilizzando l&#39;Assistente alla creazione condivisa IA, si apre la schermata **Modifica ruolo**. L&#39;avanzamento viene salvato automaticamente, come mostrato dall&#39;indicatore **Salvato** nell&#39;angolo in alto a destra. Puoi uscire e tornare a questa schermata in qualsiasi momento senza perdere il lavoro.

In questa schermata sono disponibili tre opzioni:

- **Anteprima** esegue una sessione di test dal vivo in modo che tu possa sperimentare il ruolo di Allievo prima di chiunque altro. Verifica che il personaggio abbia un aspetto naturale e che gli argomenti siano trattati correttamente.
- **Salva** salva lo stato corrente senza pubblicare. Il ruolo viene aggiunto alla sezione **Modelli disponibili** della libreria dell&#39;istruttore virtuale, in cui sarà possibile tornare a modificarla in un secondo momento.
- **Publish** aggiunge il ruolo alla **Libreria dei contenuti** in modo che possa essere assegnato a un corso o a una risorsa formativa.

Per apportare modifiche ai contenuti generati senza modificare manualmente i campi, seleziona **Modifica con AI** a destra. Viene aperta l&#39;interfaccia chat basata su IA e puoi descrivere le modifiche che desideri in un linguaggio semplice, ad esempio `make the persona more formal` o `add a topic about pricing objections`.

>[!NOTE]
>
>Questo comportamento è diverso dalla modifica per sezione. L’opzione di modifica per sezione consente di accedere contemporaneamente a tutte le sezioni. L&#39;interfaccia di chat dell&#39;intelligenza artificiale, d&#39;altra parte, offre un&#39;opzione per descrivere liberamente ciò che si desidera modificare.

Seleziona **Modifica** accanto a **Titolo di gioco dei ruoli** per modificare il titolo.

## Personalizza la simulazione dell’allenatore virtuale

Definisci il contesto della conversazione, lo sfondo del personaggio e le preoccupazioni del personaggio per rendere il tuo scenario di gioco di ruolo realistico e stimolante. Più dettagli fornisci in ogni campo, più il personaggio dell&#39;IA si comporta in modo accurato e coerente durante la simulazione.

Se hai utilizzato **Crea in comproprietà con IA** o **Genera automaticamente gioco ruolo**, questi campi sono precompilati in base ai tuoi input. Esaminali e perfezionali prima di pubblicarli.

### Contesto conversazione

Il campo **Contesto conversazione** imposta lo stadio per l’Allievo. Indica al personaggio dell&#39;intelligenza artificiale lo sfondo e lo scopo del gioco di ruolo, in modo che il personaggio comprenda perché la conversazione sta avvenendo e quale dovrebbe essere l&#39;obiettivo principale.

>[!NOTE]
>
>Questo campo è scritto per il personaggio dell’IA, non per l’Allievo. Non includere qui istruzioni o linee guida destinate all’Allievo. Utilizza il campo **Modulo di apertura istruttore AI**, descritto più avanti in questo articolo, per il contesto rivolto agli Allievi.

Durante la scrittura del contesto di conversazione:

- **Spiegare la situazione.** Descrivere il tipo di conversazione, ad esempio una chiamata di rilevamento vendite, una chiamata a freddo o un campo di ascensore, e chi ha avviato la conversazione.
- **Descrivi la posizione del personaggio dell&#39;intelligenza artificiale.** Spiega chi è il personaggio in relazione all’Allievo. Ad esempio, un cliente che valuta un prodotto, un responsabile finanziario che esamina una proposta di budget o un dipendente che riceve feedback.
- **Utilizza &quot;l’Allievo&quot; in modo uniforme.** Quando ci si riferisce alla persona con cui sta parlando, scrivere sempre &quot;l’Allievo&quot;. Evita etichette come &quot;l&#39;agente&quot;, &quot;il venditore&quot; o &quot;il rappresentante&quot;, che possono causare un comportamento incoerente della persona.
- **Tienilo conciso.** Includi solo le informazioni relative alla configurazione della conversazione. Salva dettagli specifici dell&#39;utente per **Informazioni di sfondo utente**.

**Esempio:** &quot;Chiamata di individuazione vendite. L’Allievo ha pianificato una chiamata introduttiva con Karen Mitchell, la Director per gli affari medici di una rete ospedaliera di medie dimensioni. Karen ha accettato una chiamata di 15 minuti per saperne di più sulla piattaforma di apprendimento. Prima di coinvolgere il suo team, la sua azienda ha dei limiti di tempo e valuta se la piattaforma soddisfa gli standard di qualità dei contenuti clinici&quot;.

### Informazioni di base sulle persone

Il campo **Informazioni di sfondo persona** conferisce al personaggio dell&#39;intelligenza artificiale una personalità. Più dettagli inserisci, più precise e coerenti sono le risposte del personaggio durante la simulazione.

Includi:

- **Dettagli di base**: nome, età, ruolo e situazione corrente dell&#39;utente in relazione all&#39;argomento e allo scopo del ruolo.
- **Motivazioni e obiettivi**: ciò che interessa al personaggio, ciò che vuole ottenere, ciò che vuole cambiare e i suoi punti critici.
- **Credenze e atteggiamenti**: come si sente il personaggio riguardo l’argomento della conversazione e l’organizzazione dell’Allievo.
- **Comportamenti e abitudini**: tendenze che modellano la Prospettiva del personaggio, come un processo decisionale cauto o la voglia di adottare nuovi strumenti.
- **Criteri decisionali**: elementi che convincono l&#39;utente a procedere e a eventuali vincoli entro i quali deve lavorare, ad esempio tempo, budget o processi di approvazione.

>[!TIP]
>
>Dettagli specifici aiutano il personaggio a rispondere in modo naturale e credibile. Gli sfondi generici generano un comportamento generico.

### Preoccupazioni personali

**Problemi personali** definiscono i problemi specifici, le preoccupazioni o le domande che l&#39;utente solleva durante la conversazione. Queste preoccupazioni guidano il flusso del ruolo e assicurano che l’Allievo debba rispondere a sfide realistiche.

- **Elencare da tre a cinque problemi.** Frase ciascuno come un problema o una domanda, rendendolo specifico e attuabile. Evitare preoccupazioni vaghe come &quot;preoccupato per i costi&quot;; scrivere &quot;preoccupato che il costo annuale della licenza supererà il budget discrezionale del dipartimento senza l&#39;approvazione del direttore finanziario.&quot;
- **Concentrare ogni problema su un singolo argomento.** Un problema per ogni problema mantiene la conversazione gestibile e garantisce che ogni sfida sia valutata chiaramente.
- **Specificare quando si verifica il problema.** Indica il punto della conversazione in cui il personaggio la solleva.
- **Definire gli elementi sufficienti per continuare.** Descrivi cosa consentirebbe alla conversazione di andare avanti. Ad esempio, l’Allievo rassicura l’utente, fornisce un riferimento o offre documentazione.

Scrivere ogni problema utilizzando questa struttura: **problema → quando si tratta → informazioni sufficienti per procedere.**

**Esempio:** &quot;Preoccupazione — accuratezza dei contenuti clinici: viene visualizzata quando l’Allievo descrive il processo di creazione dei contenuti. Abbastanza buono: l’Allievo dichiara esplicitamente che i contenuti sono scritti da professionisti medici, sono valutati da colleghi e sono collegati alla letteratura primaria o a linee guida cliniche riconosciute.&quot;

Una volta compilate le informazioni pertinenti, seleziona **Salva**.

>[!TIP]
>
>Timing dei problemi di test con **Anteprima**. Un problema che appare troppo presto o troppo tardi interrompe il flusso della conversazione.

>[!NOTE]
>
>Le modifiche alle impostazioni del personaggio hanno effetto immediato per qualsiasi gioco di ruolo non pubblicato. Se modifichi un ruolo già pubblicato e assegnato agli allievi, ripubblicalo per applicare il personaggio aggiornato alle sessioni future.

## Configurare una presentazione per la simulazione

Utilizza la sezione **Impostazioni presentazione** per allegare una presentazione alla simulazione di gioco di ruolo. Quando una presentazione è allegata, gli allievi possono visualizzarla durante la sessione come riferimento o supporto vocale. Ad esempio, un deck con una panoramica del prodotto utilizzato durante una simulazione del passo di vendita.

1. Seleziona **Carica PDF o PPTX** in **Dettagli presentazione**.
2. Seleziona il file. Sono supportati entrambi i formati PDF e PPTX, con una dimensione massima del file di 100 MB.
3. Una volta caricato, il nome del file viene visualizzato sotto il pulsante, confermando l’allegato.

   ![](/help/migrated/authors/feature-summary/assets/virtual_coach3.png)
   *Allega una presentazione in modo che gli Allievi possano farvi riferimento come supporto vocale durante la simulazione.*

4. Seleziona **Fine** per salvare l&#39;impostazione e tornare alla configurazione di gioco dei ruoli.

Una volta caricata una presentazione, l’opzione **Consenti agli Allievi di caricare la propria presentazione** si attiva automaticamente. Puoi anche scaricare o eliminare il file allegato utilizzando i pulsanti a destra.

Seleziona **Consenti agli Allievi di caricare la propria presentazione** se desideri che ogni Allievo si eserciti con la propria versione di un videoregistratore anziché con una condivisa. Ciò è utile quando gli Allievi vengono valutati in merito a una presentazione che hanno preparato personalmente, come una recensione aziendale o un discorso di vendita personalizzato. Questo interruttore è disabilitato per impostazione predefinita; quando è abilitato, gli allievi visualizzano un prompt di caricamento all’inizio della sessione.

>[!NOTE]
>
>Assicurati che qualsiasi presentazione che carichi sia accessibile. Usa un contrasto di colore sufficiente, includi testo alternativo per le immagini ed evita contenuti che si basano solo sul colore per trasmettere il significato.

## Configurare il personaggio dell&#39;intelligenza artificiale

La sezione **Impostazione dell’IA Persona** controlla con chi parla l’Allievo durante la simulazione, oltre ad aspetto, voce, ruolo e personalità comportamentale. Correggere questa sezione è una delle parti più importanti di come si crea uno scenario di gioco di ruolo dell&#39;intelligenza artificiale, poiché un personaggio di avatar dell&#39;intelligenza artificiale ben configurato rende il gioco di ruolo realistico e garantisce che l&#39;intelligenza artificiale si comporti in modo coerente con lo scenario che hai progettato.

### Scegli un personaggio

Sono disponibili due schede: **Personale di sistema** e **Personale personalizzato**.

**I System Personas** sono caratteri predefiniti forniti da Adobe. Ognuno di essi dispone di un nome, di una foto e di una o due modalità di interazione supportate: **Voce e video** (il personaggio appare come un avatar animato con una voce parlata) o **Voce** (solo voce parlata, senza avatar video). Seleziona una persona di sistema selezionandone la porzione.

**Personaggi personalizzati** sono personaggi creati in precedenza. Seleziona questa scheda per riutilizzare un personaggio dell&#39;avatar AI da un gioco di ruolo precedente invece di crearne uno da zero.

![](/help/migrated/authors/feature-summary/assets/virtual_coach4.png)
*Riutilizzare un personaggio personalizzato da un ruolo precedente invece di crearne uno nuovo da zero.*

Puoi riutilizzare un utente in due modi: modificarne i dettagli direttamente per trasformarlo in un altro utente, oppure selezionare **Duplica** per creare una copia e modificare i dettagli della copia. Per visualizzare entrambe le opzioni, seleziona l&#39;icona con i puntini di sospensione verticali (**⋮**) visualizzata nell&#39;angolo superiore destro dell&#39;immagine di un utente quando passi il puntatore del mouse su di essa o la selezioni.

### Configurazione dei dettagli e della personalità del personaggio

Dopo aver selezionato un utente, completa i campi **Dettagli persona AI**:

1. Immetti il **Ruolo** dell&#39;utente, ovvero il titolo che dovrebbe apparire nella simulazione, ad esempio Director per gli affari medici.
2. Immetti l&#39;**organizzazione** dell&#39;utente, ovvero l&#39;azienda o l&#39;istituto per cui lavora. Ad esempio, Northgate Health.
3. Seleziona una **personalità** che corrisponda al livello di sfida e al contesto dello scenario:

   | Personalità | Comportamento |
   |---|---|
   | Scettico | Mette in discussione tutto e richiede prove |
   | Indifferente | Disinnestato e difficile da eccitare |
   | Entusiasta | Entusiasta della soluzione e pronta all&#39;uso |
   | Orientamento alle relazioni | Valori di fiducia e connessione personale soprattutto |
   | Neutro | Bilanciamento e valutazione delle opzioni senza distorsioni |
   | Assertivo | Blunt, veloce, e tende a sfidare gli altri |

4. Facoltativamente, abilita **Consenti agli Allievi di selezionare questa opzione prima che inizi il gioco dei ruoli** per consentire agli Allievi di scegliere la personalità del personaggio prima di avviare la sessione. Ciò è utile per gli scenari in modalità pratica in cui gli Allievi desiderano controllare la difficoltà.
5. Seleziona **Fine** per salvare la configurazione dell&#39;utente.

>[!TIP]
>
>Associa la personalità alla sfida dello scenario. Uno scenario &quot;cold call&quot; trae vantaggio da un **scettico** o da un **indifferente** personaggio per simulare un potenziale cliente difficile. Uno scenario di feedback sulla leadership funziona bene con **Assertive** o **Relationship Oriented** per riflettere dinamiche realistiche manager-dipendente.

### Creare un personaggio personalizzato

Se i personaggi di sistema non si adattano al tuo scenario, creane uno nuovo dalla scheda **Personaggi personalizzati**.

1. Seleziona **Personaggi personalizzati**, quindi seleziona **Crea nuovo utente**.
2. Carica una foto per il personaggio. L’immagine deve essere di almeno 640 x 360 pixel e non superare 1 MB.
3. Immetti il **Nome** del tuo account.
4. Selezionate una **voce** dal menu a discesa per impostare la voce vocale dell&#39;IA.
5. Regolate il cursore **Frequenza vocale** per controllare la velocità della voce, da -100 (più lento) a +100 (più veloce). Il valore predefinito è 0 (spazio neutro). Seleziona **Verifica voce** per visualizzare in anteprima l&#39;audio della voce prima del salvataggio.
6. Seleziona **Crea persona**. Il nuovo utente viene salvato nella scheda **Personaggi personalizzati** ed è disponibile per l&#39;uso in qualsiasi gioco di ruolo futuro.

>[!NOTE]
>
>Personaggi personalizzati supportano l’interazione vocale. Conferma i suoni con frequenza vocale naturale per lo scenario prima della pubblicazione: una frequenza molto veloce o molto lenta può rendere la simulazione innaturale e influire sul punteggio di ritmo dell’Allievo.

L&#39;abilitazione di **Avatar video** aggiunge un avatar video dell&#39;intelligenza artificiale fotorealistico al gioco di ruolo. Gli avatar video sono disponibili per gli utenti che supportano la modalità **Voce e video**. Ogni Allievo ha a disposizione 300 minuti di gioco di ruolo video al mese; una volta raggiunto questo limite, l’esperienza diventa un avatar statico.

### Configurare un ruolo multi-persona

Utilizza un ruolo multi-persona quando l’Allievo deve seguire una conversazione che coinvolge più di uno stakeholder nella stessa sessione. Ad esempio, sottoporre un nuovo prodotto a un comitato di acquisto composto da un direttore finanziario, un responsabile acquisti, un Director IT e un promotore dell&#39;utente finale. I giochi di ruolo per più persone supportano **fino a quattro persone** in un singolo scenario.

1. Seleziona **Multi-Persona Role-Play** come modello quando avvii il gioco di ruolo.
2. Aggiungi ogni persona e assegnale un ruolo distinto. Ad esempio, CFO, Procurement Manager, IT Director e Champion.
3. Configura una personalità separata per ogni persona, seguendo gli stessi passaggi di **Dettagli persona IA** descritti in precedenza.
4. Definisci dubbi univoci per ogni persona, utilizzando la stessa struttura di dubbi descritta in **Problemi di persona.** Ogni persona pone domande e solleva obiezioni dalla propria Prospettiva, quindi l’Allievo deve adattare il proprio messaggio per ogni stakeholder a turno, piuttosto che dare un tono generico.

## Configura l’apertura della conversazione

La sezione **Apertura conversazione** controlla le prime due cose che un Allievo sente quando inizia una simulazione: una breve dichiarazione di contesto dal preparatore AI, seguita dalla riga di apertura del personaggio AI.

![](/help/migrated/authors/feature-summary/assets/virtual_coach5.png)
*L&#39;istruttore di intelligenza artificiale imposta prima lo stage, quindi il personaggio dell&#39;intelligenza artificiale apre la conversazione in carattere.*

**L&#39;utente che ha aperto l&#39;istruttore basato su intelligenza artificiale** è un breve messaggio pronunciato dall&#39;istruttore, non dall&#39;utente, prima dell&#39;inizio della conversazione. Indica all&#39;Allievo con chi sta per parlare, qual è l&#39;obiettivo e in quale contesto pertinente deve intervenire. Seleziona **Modifica** per aggiornare il testo. Breve e diretto. Per scenari più impegnativi, includi esplicitamente l&#39;obiettivo, ad esempio: &quot;Stai per fare una telefonata a un responsabile acquisti senior. Il tuo obiettivo è quello di garantire una riunione di follow-up.&quot;

**Apertura persona basata su IA** è la prima riga che il personaggio basato su IA invia all’Allievo, iniziando la conversazione. Dovrebbe riflettere la personalità del personaggio e mettere l&#39;Allievo sul posto dal primo scambio. Seleziona **Modifica** per aggiornare il testo.

| Scenario | Esempio di apertura |
|---|---|
| Chiamata a freddo | &quot;Pronto? Chi è questo?&quot; |
| Chiamata di individuazione pianificata | &quot;Ciao, grazie per avermi contattato. Cosa volevi coprire oggi?&quot; |
| Conversazione di feedback | &quot;Hai un minuto? Volevo parlarne la settimana scorsa.&quot; |
| Tono esecutivo | &quot;Ho solo dieci minuti. Cosa hai per me?&quot; |

Seleziona **Anteprima** per ascoltare entrambi gli apripista riprodotti in sequenza, esattamente come gli allievi li vedranno all’inizio di una sessione.

>[!TIP]
>
>Se i toni di apertura dell&#39;istruttore AI e dell&#39;apripista AI Persona sono troppo simili, la transizione tra di essi può creare confusione. Mantenete l&#39;istruttore aperto neutro e istruttivo; lasciate che l&#39;apripista persona abbia la personalità.

## Configurare argomenti e criteri di valutazione

La sezione **Argomenti da trattare** definisce ciò che l’Allievo deve affrontare durante la simulazione e il modo in cui l’IA valuta le sue prestazioni su ciascun argomento. Questa è la rubrica per il punteggio del roleplay dell’IA. Ogni argomento che aggiungi diventa un componente con punteggio nel report informativo dell’Allievo.

**Prima di iniziare:** Completare prima la sezione **Personalizza la simulazione**. L&#39;intelligenza artificiale utilizza il contesto di conversazione e il background del personaggio per generare linee guida di valutazione accurate per ogni argomento.

Ogni riga della tabella topics rappresenta un&#39;area di conversazione obbligatoria:

| Colonna | Scopo |
|---|---|
| Argomento | Il nome dell’area di conversazione che l’Allievo deve coprire |
| Linee guida per la valutazione | I criteri utilizzati dall’intelligenza artificiale per valutare se l’argomento è stato affrontato in modo adeguato; queste linee guida vengono visualizzate anche come feedback nella pagina di analisi dell’Allievo |
| Spessore | Percentuale del punteggio della conoscenza fornito da questo argomento; il peso totale di tutti gli argomenti deve essere 100% |
| Video di esempio | Un video opzionale che l’Allievo può guardare nella propria pagina di analisi per vedere come deve essere gestito l’argomento |
| Collegamento utile | Un URL facoltativo visualizzato nella pagina di analisi dell’Allievo insieme ai criteri di valutazione |
| Crea o interrompi | Se questa opzione è attivata, se l’Allievo non risolve affatto questo argomento, il punteggio finale della simulazione è 0, indipendentemente dalle prestazioni su altri argomenti |

![](/help/migrated/authors/feature-summary/assets/virtual_coach6.png)
*Ogni riga di argomento definisce cosa valutare, quanto vale e se è necessario passare.*

### Aggiungi un argomento

1. Selezionate **Modifica** nella sezione **Argomenti da trattare** per aprire la tabella degli argomenti.
2. Selezionare **Aggiungi argomento**. Viene visualizzata una nuova riga con campi vuoti.
3. Immettere il nome dell&#39;argomento nel campo **Argomento**. Utilizzare un&#39;etichetta breve e descrittiva che rifletta l&#39;area di conversazione, ad esempio `Opening and Rapport`, `Handling Objections` o `Agreeing Next Steps`.
4. Immettere le linee guida di valutazione nel campo **Linee guida di valutazione**. Scrivi queste informazioni come istruzione di completamento partendo da &quot;Per trattare correttamente questo argomento, l’Allievo deve...&quot;
5. Immetti una percentuale nel campo **Spessore**. Distribuisci i pesi in tutti gli argomenti in modo che il totale sia uguale al 100%.
6. Facoltativamente, selezionare **Fare clic per aggiungere un video** per allegare un video di esempio oppure **Fare clic per aggiungere l&#39;URL** per allegare un collegamento utile, ad esempio un articolo della knowledge base o un cercapersone del prodotto.
7. Facoltativamente, abilitare **Crea o interrompi** per gli argomenti non negoziabili.
8. Ripetere l&#39;operazione per ogni argomento da includere, quindi selezionare **Fine**.

### Modificare o rimuovere un argomento

- Per modificare un campo di una riga di argomento esistente, selezionare direttamente il campo e aggiornare il testo o il valore.
- Per rigenerare le linee guida di valutazione utilizzando l&#39;intelligenza artificiale in base al proprio personaggio e contesto, selezionare l&#39;icona di aggiornamento (**↻**) nella cella **Linee guida di valutazione**.
- Per rimuovere un argomento, selezionare il menu delle opzioni (**⋮**) alla fine della riga e selezionare **Elimina argomento**.
- Per duplicare un argomento e utilizzarlo come base per uno simile, selezionate **Duplica argomento** dallo stesso menu.

### Linee guida per la scrittura di argomenti efficaci

Un roleplay di intelligenza artificiale forte a punteggi fa la differenza tra un gioco di ruolo che sembra equo e uno che sembra arbitrario. Tenete presenti le seguenti indicazioni:

- **Assegna un nome agli argomenti dopo le fasi della conversazione, non alle funzionalità del prodotto.** Argomenti come `Opening and Rapport`, `Needs Discovery` e `Agreeing Next Steps` riflettono la struttura di una conversazione reale.
- **Scrivi linee guida per la valutazione come azioni osservabili.** L&#39;intelligenza artificiale valuta ciò che ha detto l&#39;allievo, quindi le linee guida devono descrivere comportamenti specifici e udibili, non intenzioni. Confrontate &quot;l’Allievo deve capire le preoccupazioni del singolo&quot; (debole) con &quot;l’Allievo deve chiedere al singolo di dare un nome alla sua preoccupazione principale e confermare di averla sentita prima di rispondere&quot; (forte).
- **Usare Crea o Interrompi con moderazione.** Riservatelo a uno o due argomenti in cui l&#39;omissione totale renderebbe la conversazione un chiaro fallimento, come non presentarsi a una chiamata fredda. La sua applicazione a troppi argomenti rende difficile per gli Allievi superare anche un tentativo ragionevole.
- **Bilanciare gli spessori in base all&#39;importanza della conversazione.** Un argomento che occupa la maggior parte di una conversazione tipica, ad esempio richiede la scoperta in una chiamata di vendita, dovrebbe avere un peso maggiore rispetto a una breve apertura o chiusura.
- **Aggiungi collegamenti utili agli argomenti con punteggio basso.** Se gli Allievi ottengono sempre punteggi bassi per un particolare argomento in più sessioni, allega un collegamento alla risorsa in modo da avere qualcosa da studiare tra i tentativi.

## Configurare le impostazioni della lingua

La sezione **Impostazioni lingua** controlla se gli Allievi possono scegliere la lingua nella quale esercitarsi quando avviano la simulazione. Abilita **Consenti agli Allievi di scegliere la propria lingua per l&#39;esercitazione** per consentire a ogni Allievo di selezionare la propria lingua preferita all&#39;inizio della sessione. Lasciare questa opzione disattivata se si desidera che tutti gli allievi si esercitino nella lingua in cui è stato creato il ruolo: l’impostazione consigliata per le valutazioni formali in cui la coerenza della lingua fa parte dei criteri di valutazione.

>[!NOTE]
>
>Virtual Coach supporta contenuti di simulazione in nove lingue. La selezione della lingua dell’Allievo è significativa solo se il contenuto dello scenario e il personaggio sono scritti per supportare l’uso multilingue; se le linee guida di valutazione e il background del personale sono scritti in una singola lingua, l’attivazione di questa impostazione può produrre risposte di intelligenza artificiale incoerenti per gli Allievi che selezionano una lingua diversa.

## Configura l’analisi delle azioni su schermo

La sezione **Analisi delle azioni sullo schermo** consente di caricare un video di best practice che mostra all’IA come assegnare un punteggio alle azioni intraprese da un Allievo durante il gioco di ruolo. Ciò è particolarmente utile per le simulazioni in cui l’Allievo deve mostrare sullo schermo in modo visibile azioni specifiche, come navigare in un’interfaccia software, completare un modulo o seguire un processo definito passo dopo passo.

>[!NOTE]
>
>Questa opzione è disabilitata se nella sezione **Impostazioni di presentazione** sono stati caricati solo file di PowerPoint o PDF.

1. Selezionare **Seleziona file** per aprire l&#39;elenco dei file.
2. Seleziona il file video e conferma il caricamento.
3. Una volta caricato, il nome del file viene visualizzato nella riga di riepilogo **Analisi azioni su schermo**.

Il video deve soddisfare i seguenti requisiti:

| Requisito | Specifiche |
|---|---|
| Formato file | WEBM, MP4, WMV o MPEG |
| Dimensione massima del file | 200 MB |
| Risoluzione minima | 1280 x 720 pixel |
| Frequenza fotogrammi minima | 5 FPS |
| Proporzioni | Tra 4:3 e 21:9 |

Durante la registrazione di un video, descrivere tutte le azioni contemporaneamente nell&#39;audio e sullo schermo. Ad esempio, pronunciate &quot;Ora sto selezionando il pulsante Invia&quot; mentre lo faccio, poiché l&#39;intelligenza artificiale si basa sia sulla narrazione che sull&#39;azione visiva. Mantenere la registrazione concentrata sull&#39;attività, rimuovere notifiche e contenuti non correlati e abbinare il video alle linee guida di valutazione in modo che dimostri ogni azione richiesta nel punto del flusso di lavoro in cui si prevede che si verifichi.

## Configurare le impostazioni del punteggio

**Il punteggio minimo** è il punteggio complessivo minimo che un Allievo deve ottenere per contrassegnare la simulazione come superata, applicata alla combinazione ponderata di punteggio di conoscenza e punteggio di stile. Immetti un numero compreso tra 1 e 100 nel campo **Punteggio minimo** (il valore predefinito è 80) e seleziona **Fine**.

>[!TIP]
>
>Per le valutazioni formali, è tipico un punteggio di passaggio da 75 a 80. Per i giochi di ruolo in modalità pratica in cui l&#39;obiettivo è lo sviluppo di abilità piuttosto che la certificazione, considerare una soglia inferiore o abilitare **Modalità pratica**.

**I pesi del punteggio IA** consentono di stabilire in che misura la componente Conoscenza (se l’Allievo ha trattato argomenti obbligatori e fornito informazioni accurate) e la componente Stile (ritmo, chiarezza, parole di riempimento, lunghezza della frase, energia) contribuiscono ciascuna al punteggio complessivo. Trascina il cursore per regolare il bilanciamento; i due valori sono sempre totali al 100% e l’impostazione predefinita è Conoscenza 70% / Stile 30%. Per indicazioni su come gli Allievi interpretano questi punteggi, consulta [il report sulle prestazioni degli istruttori virtuali](/help/migrated/learners/feature-summary/virtual-coach/understand-virtual-coach-performance-report.md).

| Tipo di scenario | Rapporto consigliato | Causa |
|---|---|---|
| Valutazione delle competenze o certificazione | 80% di conoscenza/20% di stile | La precisione del contenuto è la misura principale |
| Abilitazione alle vendite | 60% di conoscenza/40% di stile | Il recapito è importante quanto il messaggio nelle conversazioni con i clienti |
| Sviluppo della leadership | Conoscenza 70% / Stile 30% | Equilibrato: sia il contenuto che il tono sono fondamentali nelle conversazioni tra persone |
| Coaching della comunicazione | 40% di conoscenza/60% di stile | Lo stile è l’obiettivo di apprendimento principale |

**Abilita modalità pratica per gli Allievi** consente agli Allievi di richiedere suggerimenti durante la simulazione per tenerli sotto controllo, utile per l’apprendimento nella fase iniziale. Quando questa opzione è attivata, potete impostare **Numero massimo di suggerimenti per sessione** (valore predefinito 5, regolabile da 1 a 10) e la durata della visibilità dei suggerimenti (valore predefinito 30 secondi).

>[!NOTE]
>
>I suggerimenti non sono disponibili durante le valutazioni formali. Se utilizzi questo ruolo come valutazione graduata, disattiva Modalità pratica in modo che tutti gli Allievi vengano valutati nelle stesse condizioni.

**Nascondi punteggio** impedisce agli Allievi di visualizzare il punteggio numerico dopo la sessione; continuano a ricevere feedback qualitativi e analisi a livello di argomento. Usa questa opzione quando il gioco di ruolo è solo per pratica, quando solo un valutatore manager deve visualizzare il risultato o quando desideri ridurre l’ansia da punteggio nelle prime fasi di apprendimento.

## Configurare le impostazioni avanzate di gioco dei ruoli

Queste impostazioni opzionali controllano come e quando termina la simulazione e come viene configurato l’ambiente della sessione.

**Consenti all&#39;intelligenza artificiale di terminare l&#39;esecuzione dei ruoli.** Per impostazione predefinita, solo l’Allievo può terminare una simulazione selezionando **Termina simulazione**. Abilita questa opzione e descrivi la condizione in base alla quale l’utente deve chiudere la conversazione in modo naturale, ad esempio: &quot;Quando l’Allievo programma con successo una riunione di follow-up o l’utente rifiuta tre volte, l’utente deve terminare la chiamata in modo educato.&quot; Utilizzare questa opzione per scenari avanzati in cui l&#39;endpoint naturale della conversazione, non un timer, deve determinare la chiusura della sessione.

**Limite di tempo per la simulazione.** Immettere un numero compreso tra 1 e 59 minuti per impostare la durata massima della sessione; una volta raggiunta la durata, la simulazione termina automaticamente e l&#39;Allievo viene indirizzato alla pagina di analisi.

| Tipo di scenario | Limite consigliato |
|---|---|
| Chiamata a freddo o breve pratica di apertura | 3-5 minuti |
| Chiamata di individuazione o valutazione delle esigenze | 10-15 minuti |
| Colloquio completo sulle vendite o sulla leadership | 15-20 minuti |
| Valutazione formale con più argomenti | Corrispondenza della lunghezza prevista per una conversazione in tempo reale |

**Penalità sessione breve** scoraggia gli allievi dal terminare le sessioni troppo rapidamente applicando una riduzione del punteggio se la durata della sessione scende al di sotto della durata minima impostata. Utilizzalo quando la durata della sessione è significativa per l’obiettivo di apprendimento. Ad esempio, in una chiamata di individuazione in cui l’Allievo deve dedicare tempo a scoprire le esigenze prima di proporre una soluzione.

>[!NOTE]
>
>Non utilizzare l’opzione Penalità sessione breve nei giochi di ruolo in modalità pratica dove gli Allievi creano ancora fiducia, poiché penalizzare le uscite anticipate può aumentare l’ansia e scoraggiare i tentativi ripetuti.

**Abilita condivisione dello schermo** consente agli Allievi di condividere lo schermo durante la simulazione. Questo è rilevante per gli scenari che includono un componente **Analisi azioni su schermo**. È disattivato per impostazione predefinita se sono stati caricati solo documenti di PowerPoint o PDF in **Impostazioni presentazione**.

**Abilita sottotitoli persona AI** visualizza il testo su schermo del messaggio del personaggio AI in tempo reale. Abilita questa opzione per gli Allievi con difficoltà di udito o che esercitano in una seconda lingua, per ambienti rumorosi o per scenari in cui la lettura delle parole esatte dell’utente è importante per comprendere le obiezioni sfumate.

## Il ruolo di Virtual Coach in Publish

Dopo aver configurato tutte le sezioni, seleziona **Publish**.

![](/help/migrated/authors/feature-summary/assets/virtual_coach7.png)
*Completare i dettagli di pubblicazione e selezionare Salva per aggiungere il proprio ruolo alla libreria dei contenuti.*

1. Immetti il titolo di ruolo.
2. Seleziona la cartella in cui desideri aggiungere il ruolo.
3. Facoltativamente, aggiungi tag e una data di scadenza.
4. Seleziona **Salva**. Il ruolo è stato aggiunto alla **Libreria dei contenuti**.

Ora hai creato un ruolo di istruttore virtuale dall’inizio alla fine in Adobe Learning Manager Virtual Coach. Continua per [aggiungere un ruolo di istruttore virtuale a un corso](/help/migrated/authors/feature-summary/virtual-coach/add-virtual-coach-role-play-to-course.md) per renderlo disponibile agli Allievi. Per le risposte alle domande frequenti sulla creazione, ad esempio perché un gioco di ruolo potrebbe ottenere un punteggio pari a zero, quante persone supporta un gioco di ruolo multi-persona e come scrivere un messaggio valido per l&#39;Assistente alla creazione condivisa basata su intelligenza artificiale, consulta le [Domande frequenti sull&#39;istruttore virtuale](/help/migrated/authors/feature-summary/virtual-coach/virtual-coach-faq.md).
