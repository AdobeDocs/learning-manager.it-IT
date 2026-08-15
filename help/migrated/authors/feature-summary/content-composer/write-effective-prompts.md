---
description: Il prompt è l’input più importante in Composizione contenuti. Un prompt specifico, ad esempio l’assegnazione di un nome al pubblico, 2-3 argomenti e un segnale di ambito, produce un breve risultato più preciso, un contorno più forte e meno editing a valle.
jcr-language: en_us
title: Scrivi messaggi efficaci in Composizione contenuti
source-git-commit: c58fff50e6ccf6ab45722a0aafb7f4cee73752b5
workflow-type: tm+mt
source-wordcount: '2339'
ht-degree: 0%

---


# Scrivi messaggi efficaci in Composizione contenuti

Scoprite come scrivere messaggi efficaci in ogni fase di Content Composer, dal prompt di apertura fino alla descrizione, al contorno e all’editor del corso, per produrre corsi accurati e ben strutturati generati dall’intelligenza artificiale con meno operazioni di editing.

Il modulo di composizione dei contenuti è interattivo. La qualità di ciò che produce in ogni fase dipende dalla qualità di ciò che gli viene dato. Questa guida descrive come comunicare con l&#39;intelligenza artificiale in modo efficace in ognuna delle quattro fasi: **Home**, **Breve**, **Struttura** e **Corso**.

## Fase 1: Home- Scrivi la richiesta di apertura

Il prompt di apertura è il punto di partenza. Non deve essere perfetto. Composizione contenuti legge il prompt e lo utilizza per aprire una conversazione. Anche un messaggio di prova mette in moto il processo; l&#39;assistente porrà domande di follow-up nella fase Breve per completare ciò che manca.

Detto questo, un messaggio più specifico significa che l&#39;IA precompila il Brief in modo più accurato, riducendo l&#39;avanzamento prima di generare il contorno. Se hai una chiara idea di pubblico, argomenti e obiettivo, mettilo nel messaggio.

Un messaggio vago genera un messaggio vago. Una descrizione vaga produce un contorno generico. Un profilo generico genera un corso che richiede modifiche significative. La specificità nella fase iniziale scorre in avanti in ogni fase successiva.

### Cosa ci si aspetta da Content Composer

In Content Composer sono previste le seguenti operazioni in una o due frasi:

- **Chi** sono gli Allievi? Assegna un nome al ruolo e al livello di esperienza.
  - **Che cosa** coprirà il corso? Descrivi 2-3 aree tematiche specifiche anziché un ambito ampio. Ad esempio, &quot;il riconoscimento del phishing, l&#39;igiene della password e la configurazione MFA&quot; è più utile della &quot;sicurezza IT&quot;.
- **Qual è l&#39;obiettivo di apprendimento?** Descrivi il risultato o il cambiamento comportamentale che desideri che gli allievi ottengano dopo aver completato il corso.

### Anatomia di un prompt effettivo

**[Livello di pubblico + esperienza]** + **[2-3 argomenti specifici]** + **[obiettivo di apprendimento]**

**Esempio**:

Desidero creare un corso per nuovi rappresentanti commerciali che copra i nostri livelli di prezzo enterprise e il flusso di lavoro di approvazione degli sconti. Alla fine, dovrebbero essere in grado di gestire con sicurezza le tre obiezioni più comuni dei clienti.

Suddivisione in base a:

- **Pubblico:** nuovi rappresentanti commerciali

- **Argomenti:** livelli di prezzo enterprise, flusso di lavoro di approvazione degli sconti, tre obiezioni comuni
  - **Obiettivo di apprendimento**: gestire con sicurezza le tre obiezioni più comuni dei clienti: un risultato comportamentale misurabile, non un argomento da trattare

Dopo aver selezionato **Introduzione**, Content Composer apre la fase **Breve**. Verifica i campi precompilati, il titolo, il profilo dell’Allievo e l’obiettivo che l’intelligenza artificiale ha generato dal tuo messaggio e perfeziona tutto ciò che non corrisponde alle tue intenzioni prima di generare la struttura.

### Proposte efficaci da fare e da non fare

| **Includi** | **Evitare** |
|--------------------------------------------------------------------------------------------------------|--------------------------------------------------------------------------------------------------|
| Un ruolo di pubblico specifico (&quot;nuovi rappresentanti commerciali&quot;, &quot;responsabili in prima linea&quot;) | Gruppi di destinatari vaghi (&quot;tutto il personale&quot;, &quot;tutti&quot;, &quot;utenti&quot;) |
| 2-3 aree tematiche concrete | Più di 6 argomenti in un unico messaggio: si ottengono contorni sovraccarichi; al loro posto, vengono suddivisi in corsi separati |
| Un segnale ambito: durata, profondità o risultato dell’Allievo | Obiettivi generici (&quot;insegnare loro tutto su X&quot;, &quot;coprire tutti gli aspetti di&quot;) |
| Contesto che forma il tono o la profondità (&quot;per conformità&quot;, &quot;per un pubblico non tecnico&quot;, &quot;basato su scenari&quot;) | Fare domande all&#39;intelligenza artificiale. Il messaggio è breve, non una conversazione |
| Cosa potranno fare gli Allievi dopo il corso | Contenuto del corso (lasciare la struttura alla fase di struttura) |

### Suggerimenti per il corso in base al tipo di corso

| **Tipo di corso** | **Messaggio per iniziare** |
|--------------------------------|----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| **Corso di formazione sulla conformità** | &quot;Desidero creare un corso per tutti i dipendenti sulla gestione dei dati GDPR, che copra ciò che è considerato come un dato personale, come archiviarlo e condividerlo correttamente e cosa fare in caso di violazione&quot;. |
| **Onboarding** | &quot;Creare un modulo di onboarding per il nuovo \[ruolo\] che copra \[argomento 1\], \[argomento 2\] e \[argomento 3\]. |
| **Abilità tecniche** | &quot;Voglio creare un corso per i tecnici informatici junior sulle pratiche di codifica sicura, come la prevenzione dell&#39;iniezione SQL, la convalida dell&#39;input e come leggere un report SAST&quot;. |
| **Capacità relazionali** | &quot;Voglio creare un corso per i responsabili della vendita al dettaglio in prima linea sul feedback costruttivo, ad esempio sul modello SBI, su come prepararsi a una conversazione sul feedback e su come dare seguito alle richieste&quot;. |
| **Criteri e procedura** | &quot;Voglio creare un corso per il personale del magazzino sulle procedure di movimentazione manuale, come la corretta tecnica di sollevamento, quando utilizzare le attrezzature e come segnalare un incidente.&quot; |
| **Formazione sul prodotto** | &quot;Desidero creare un corso per gli agenti dell&#39;assistenza clienti sulla nostra politica di restituzioni, ad esempio per illustrare i criteri di idoneità, come elaborare una restituzione in \[sistema\] e come gestire le escalation.&quot; |
| **Abilitazione alle vendite** | &quot;Voglio creare un corso per gli amministratori degli account di livello intermedio sulla negoziazione di accordi aziendali, ad esempio, che copra come identificare i responsabili delle decisioni, come gestire le obiezioni sui prezzi utilizzando la nostra struttura di valore e quando inoltrare la richiesta a un direttore vendite.&quot; |
| **Sviluppo della leadership** | &quot;Voglio creare un corso per i manager delle persone che per la prima volta trattano come gestire in modo efficace un rapporto 1:1 settimanale, come impostare un programma, dare riconoscimento e affrontare tempestivamente il problema delle prestazioni insoddisfacenti.&quot; |
| **Formazione su sistemi e strumenti** | &quot;Voglio creare un corso per i coordinatori delle risorse umane che non hanno mai lavorato in Workday, ad esempio per illustrare come creare una richiesta di lavoro, far passare un candidato in diverse fasi di assunzione e generare un report sull&#39;headcount&quot;. |
| **Salute e sicurezza** | &quot;Voglio creare un corso di aggiornamento per tutto il personale del sito sulle procedure di sicurezza antincendio, per esempio, coprendo la via di evacuazione per ogni zona dell&#39;edificio, come utilizzare un estintore e cosa fare se si scopre un incendio al di fuori dell&#39;orario di lavoro.&quot; |

## Fase 2: accentuare i suggerimenti dell&#39;IA

Dopo aver inviato il messaggio, Composizione contenuti apre la fase Breve e precompila tre campi: il titolo del corso, il profilo dell’Allievo e l’obiettivo di apprendimento. L&#39;intelligenza artificiale fa delle domande di follow-up per rendere più nitidi i campi prima di generare il contorno.

Questa è una fase di conversazione. La qualità delle vostre risposte alle domande dell&#39;intelligenza artificiale determina direttamente la qualità del profilo che produce.

### Titolo del corso

L&#39;intelligenza artificiale suggerisce due opzioni per i titoli. Selezionate quello adatto o digitatene uno personalizzato. Se nessuna delle due è corretta, descrivere la lacuna:

&quot;Nemmeno. Il corso tratta in modo specifico del flusso di lavoro di approvazione, non dei prezzi generali&quot;.

Un buon titolo è rivolto agli Allievi. Descrive ciò che l’Allievo sarà in grado di fare, non ciò che copre il corso.

### Profilo Allievo

L’IA chiede informazioni sul ruolo, sul livello di esperienza e su cosa devono affrontare attualmente gli Allievi. È importante essere specifici sia per ciò che conoscono che per ciò che non conoscono:

| Meno utile | Più utile |
|---|---|
| &quot;Tutti i dipendenti&quot; | &quot;Sviluppatori di software di fascia media che hanno familiarità con la tecnologia agile ma che non hanno esperienza di conformità alle normative di sicurezza aziendali&quot; |
| &quot;Novità dell&#39;argomento&quot; | &quot;Dirigenti a inizio carriera promossi da ruoli di contributore individuale senza alcuna formazione formale sulla gestione&quot; |
| &quot;Il nostro team di vendita&quot; | &quot;Nuovi responsabili account nei primi 90 giorni, a proprio agio con gli strumenti CRM ma poco esperti con le strutture di prezzo aziendali&quot; |

### Obiettivo di apprendimento

L’intelligenza artificiale chiede cosa potranno fare gli Allievi sul lavoro dopo aver completato il corso. Questo è il campo Brief più importante: controlla le priorità dell&#39;intelligenza artificiale nei file sorgente, il modo in cui è strutturato il profilo e i test del quiz.

Scrivere l&#39;obiettivo come comportamento che inizia con un verbo di azione:

| Obiettivo debole | Obiettivo forte |
|---|---|
| &quot;Comprendere la protezione dei dati&quot; | &quot;Identificare i dati personali, applicare pratiche corrette di archiviazione e condivisione e segnalare una sospetta violazione utilizzando il processo di segnalazione dell&#39;organizzazione&quot; |
| &quot;Informazioni sulla gestione delle obiezioni&quot; | &quot;Rispondere alle tre più comuni obiezioni dei clienti utilizzando il framework di messaggistica approvato, senza richiedere l&#39;intervento di un direttore vendite&quot; |
| &quot;Conoscere il processo di onboarding&quot; | &quot;Completare la checklist di onboarding della prima settimana, inviare i moduli di conformità richiesti e accedere agli strumenti necessari per il proprio ruolo senza assistenza IT&quot; |

>[!IMPORTANT]
>
>**Prima di generare la struttura:** La struttura viene creata interamente a partire dalla Breve, non dal prompt originale. Prima di selezionare **Genera struttura**, verifica che il titolo sia rivolto agli Allievi, che il profilo Allievo nomini un ruolo e un livello di esperienza specifici e che l’obiettivo di apprendimento descriva un comportamento misurabile sul lavoro. Un Brief ben definito produce un contorno ben strutturato. Se un campo risulta ancora generico, perfezionalo ora.  In seguito, si risparmierà una notevole quantità di modifiche.

### Segnala che il Brief richiede più lavoro

- Il profilo dell’Allievo afferma &quot;Dipendenti che desiderano conoscere X&quot; invece di assegnare un ruolo specifico e un livello di esperienza
- L’obiettivo di apprendimento descrive un’area tematica piuttosto che un comportamento misurabile sul lavoro
- Il titolo è un’etichetta per argomento (&quot;Sicurezza IT&quot;) piuttosto che un risultato rivolto all’Allievo (&quot;Identificare e rispondere ai tentativi di phishing&quot;)

## Fase 3: modifica del profilo attraverso la conversazione

Dopo aver confermato la descrizione, Composizione contenuti genera una struttura di lezioni e argomenti. Lo rivedi e richiedi modifiche tramite il pannello Chat prima di generare il corso completo.

La modifica dei contorni nella versione corrente è interamente a scopo di conversazione. Non è possibile selezionare una lezione o un argomento nell&#39;area di lavoro per rinominarlo o riordinarlo. Tutte le modifiche vengono apportate digitando richieste in linguaggio semplice.

Questa è anche la fase più efficiente per apportare modifiche strutturali. La modifica della struttura richiede alcuni secondi. La ristrutturazione di un corso generato richiede molto più tempo.

### Come formulare le richieste di modifica del profilo

Sii diretto e specifico. Assegnare un nome alla lezione o all&#39;argomento in base al titolo corrente, descrivere la modifica desiderata e, facoltativamente, spiegarne il motivo.

**Rinomina:**

- &quot;Rinominare la lezione 1 in &#39;Funzionamento degli attacchi di phishing&#39;.&quot;
- &quot;Rinominare l’argomento 2.3 in &quot;Tracciati e linee temporali di escalation&quot;.&quot;

**Aggiungi:**

- &quot;Aggiungere un nuovo argomento alla lezione 2 sul phishing del codice QR&quot;.
- &quot;Aggiungere una lezione sulla risposta all&#39;incidente dopo la lezione 4.&quot;

**Rimuovi:**

- &quot;Rimuovi argomento 1.3.&quot;
- &quot;Elimina lezione 5. Tali contenuti sono trattati in un corso separato.&quot;

**Riordina:**

- &quot;Spostare la lezione 3 per la seconda lezione.&quot;
- &quot;Spostare l&#39;argomento 2.1 alla fine della lezione 2.&quot;

**Divisione:**

- &quot;Dividere la lezione 3 in due lezioni, una sui filtri antispam e una sulla gestione delle patch&quot;.

**Unione:**

- &quot;Unire le lezioni 4 e 5 in un&#39;unica lezione denominata &#39;Risposta e ripristino in caso di incidente&#39;.&quot;

**Rigenera:**

- &quot;Rigenerare il contorno con una maggiore attenzione all&#39;igiene delle password e all&#39;autenticazione basata su conoscenza.&quot;
- &quot;Rigenerare il profilo: la struttura corrente è troppo tecnica per un pubblico non tecnico.&quot;

### Cosa non può fare la fase di struttura

- La gerarchia è fissa come Lezioni > Argomenti. Non è possibile creare sottoargomenti o strutture a tre livelli.
- In questa fase non è possibile impostare obiettivi individuali per le lezioni: l’obiettivo di apprendimento generale del Brief si applica a tutto il corso.
- In questa fase non è possibile aggiungere componenti o file multimediali. che vengono aggiunti nell’editor del corso.

### Quando rigenerare e quando modificare

| Usa modifica a livello di conversazione quando... | Rigenera quando... |
|---|---|
| La struttura complessiva è corretta, ma i singoli nomi o argomenti devono essere modificati | La struttura generale non corrisponde affatto alle tue intenzioni |
| Desideri aggiungere o rimuovere elementi specifici | Il Brief è stato rifinito in modo significativo dopo la generazione del primo contorno |
| È necessario dividere o unire una lezione | Il contorno sembra generico e manca del contesto specifico dell&#39;organizzazione |

## Fase 4: Corso - Perfezionamento dei contenuti tramite l&#39;assistente

Dopo aver approvato il profilo e generato il corso, il pannello **Crea con Content Composer** rimane aperto sul lato destro dello schermo. Puoi usarlo per perfezionare, espandere o regolare qualsiasi parte del corso generato attraverso la conversazione.

L’assistente nell’editor del corso è progettato per le attività di modifica dei contenuti. Per domande sulle procedure del prodotto, utilizzare questa documentazione della Guida anziché chiedere all&#39;assistente.

### Come formulare le richieste di modifica del corso

**Riscrivere o regolare una sezione specifica:**

- &quot;Riscrivere il paragrafo nella seconda sezione della lezione 1 per essere più concisi — mirare a tre frasi.&quot;
- &quot;Rendete il contenuto del tema 2.1 meno tecnico. Il pubblico non dispone di un background IT&quot;.
- &quot;Aggiungere un esempio del mondo reale all&#39;introduzione della lezione 1.&quot;

**Regola tono:**

- &quot;Riscrivi la lezione 2 in un tono più conversazionale.&quot;
- &quot;Rendi il contenuto dell&#39;argomento 3.2 più autorevole: questo è un corso sulla conformità.&quot;

**Espandere o aggiungere contenuto:**

- &quot;Aggiungere un esempio basato su scenari all&#39;argomento 1.3 che mostra l&#39;aspetto che potrebbe avere un&#39;e-mail di phishing.&quot;
- &quot;Espandere la sezione su MFA per includere le istruzioni per la configurazione su dispositivi mobili.&quot;

**Ridurre o semplificare:**

- &quot;Abbreviare il testo nella diapositiva 5 a tre punti elenco.&quot;
- &quot;Riassumere il secondo paragrafo del punto 2.2 in una frase.&quot;

**Regolare il quiz:**

- &quot;Rigenerate il quiz per la lezione 2 con domande più difficili&quot;.
- &quot;Sostituire la domanda 3 con una domanda basata su uno scenario per il riconoscimento di un tentativo di ingegneria sociale.&quot;
- &quot;Aggiungi altre due domande al quiz della lezione 1 incentrato sulla configurazione MFA&quot;.

**Regolare le immagini:**

- &quot;Sostituire l&#39;immagine del punto 2.2 con un&#39;immagine che illustri uno scenario di ingegneria sociale.&quot;
- &quot;Genera un’immagine per l’argomento 1.1 che illustri un’e-mail di phishing sullo schermo di un laptop.&quot;

**Aggiungere o modificare i componenti:**

- &quot;Aggiungere una flip card all&#39;argomento 3.1 con le definizioni dei tre livelli di prezzo.&quot;
- &quot;Aggiungere una fisarmonica al tema 2.3 con i passaggi di escalation: un pannello per passaggio.&quot;
- &quot;Convertire l’elenco puntato nell’argomento 1.2 in un componente della linea temporale.&quot;

### Cosa non può fare l’assistente

- Rinomina le lezioni o gli argomenti direttamente nell’area di lavoro. Utilizzare l&#39;assistente: &quot;Rinominare la lezione 2 in &#39;Igiene password&#39;.&quot;
- Creare tracciati diramati o adattati. La struttura del corso è lineare.
- Aggiungi nuove lezioni o ristruttura la struttura. Le modifiche strutturali richiedono il ritorno allo stadio Contorno.

## Procedure ottimali in tutte le fasi

- **Descrivere gli elementi che si desidera compilare prima di aprire Composizione contenuti.** Una frase scritta in anticipo tende ad essere più chiara di una digitata sotto la pressione del campo di input.
- **Investire tempo nell&#39;obiettivo di apprendimento.** L’obiettivo in Breve controlla la struttura, la priorità dei file di origine e l’allineamento dei quiz. Un obiettivo specifico, incentrato sul comportamento, riduce l’editing in ogni fase successiva.
- **Perfezionare il Brief prima di generare il profilo.** Il contorno viene creato dal Brief, non dal prompt originale. Un Brief ben definito con un profilo di Allievo specifico e un obiettivo di apprendimento produce un profilo strutturato e pertinente.
- **Modificare la struttura prima di generare il corso.** Le modifiche strutturali nella fase di struttura richiedono secondi. Le stesse modifiche dopo la generazione del corso richiedono molto più tempo.
- **Per i contenuti utilizzare l&#39;Assistente corso, non per la struttura.** Le modifiche strutturali, l’aggiunta di lezioni, il riordinamento degli argomenti fanno parte della fase Outline. Utilizza l’Assistente corso per perfezionare testo, toni, esempi e domande relative ai quiz.
- **Specificare in ogni richiesta.** Assegnare un nome alla lezione, all&#39;argomento, alla diapositiva o alla domanda che si desidera modificare. &quot;Miglioralo&quot; non dà all&#39;intelligenza artificiale nulla su cui agire. &quot;Rendete l’argomento 2.1 più conciso e aggiungete un esempio del mondo reale&quot;, vero.
