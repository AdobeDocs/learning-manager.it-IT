---
description: Il prompt è l’input più importante in Composizione contenuti. Un prompt specifico, ad esempio l’assegnazione di un nome al pubblico, 2-3 argomenti e un segnale di ambito, produce un breve risultato più preciso, un contorno più forte e meno editing a valle.
jcr-language: en_us
title: Scrivi messaggi efficaci in Composizione contenuti
hide: true
source-git-commit: 229e407621281978f94783c3e9320c237c314fc3
workflow-type: tm+mt
source-wordcount: '1078'
ht-degree: 0%

---


# Scrivi prompt validi

Scrivi messaggi che producano resoconti accurati del corso, contorni migliori e contenuti più efficaci generati dall’intelligenza artificiale in Content Composer.

Il prompt è il primo input fornito da Composizione contenuti e il più importante. Un messaggio chiaro e specifico indica che l&#39;intelligenza artificiale precompila il documento in modo più accurato, genera un contorno che corrisponde alle tue intenzioni e produce contenuti del corso che richiedono meno modifiche.

## Cosa fa funzionare un messaggio?

Composizione contenuti legge il messaggio e lo utilizza per precompilare tre brevi campi: il titolo del corso, il profilo dell’Allievo e l’obiettivo di apprendimento. Più il suggerimento riflette queste tre dimensioni, minore è la correzione richiesta dal suggerimento e più accurato sarà il risultato di un contorno più pertinente.

Un messaggio che dice &quot;Crea un corso sulla sicurezza&quot; non fornisce quasi nulla con cui lavorare all&#39;intelligenza artificiale. Un messaggio che indica il nome del pubblico, specifica gli argomenti e segnala che l&#39;ambito fornisce all&#39;IA abbastanza da generare un breve messaggio che puoi accettare con modifiche minime.

I campi brevi amplificano anche tutto ciò che è presente nel messaggio. Se il tuo messaggio è vago, l&#39;IA genera un breve messaggio vago. Una breve descrizione generica genera un contorno generico.

## Strutturare un messaggio forte

Un forte messaggio risponde a tre domande in una o due frasi:

- **Chi** sono gli Allievi? Assegna un nome al ruolo e al livello di esperienza.

- **Che cosa** coprirà il corso? Assegna un nome a argomenti specifici 2-3, non un’ampia area tematica.

- **Specificare l&#39;ambito o il risultato**. Durata del segnale, profondità o attività che gli Allievi possono svolgere.

## Anatomia di un prompt effettivo

**[Pubblico + livello di esperienza]** + **[2-3 argomenti specifici]** + **[Segnale di ambito o di risultato]**

**Esempio**:

Desidero creare un corso per nuovi rappresentanti commerciali che copra i nostri livelli di prezzo enterprise, il flusso di lavoro di approvazione degli sconti e come gestire le tre obiezioni più comuni dei clienti.

Suddivisione in base a:

- **Pubblico:** nuovi rappresentanti commerciali

- **Argomenti:** livelli di prezzo enterprise, flusso di lavoro di approvazione degli sconti, tre obiezioni comuni

Dopo aver selezionato **Introduzione**, Content Composer apre la fase **Breve**. Verifica i campi precompilati, il titolo, il profilo dell’Allievo e l’obiettivo che l’intelligenza artificiale ha generato dal tuo messaggio e perfeziona tutto ciò che non corrisponde alle tue intenzioni prima di generare la struttura.

## Proposte efficaci da fare e da non fare

| **Includi** | **Evitare** |
|--------------------------------------------------------------------------------------------------------|--------------------------------------------------------------------------------------------------|
| Un ruolo di pubblico specifico (&quot;nuovi rappresentanti commerciali&quot;, &quot;responsabili in prima linea&quot;) | Gruppi di destinatari vaghi (&quot;tutto il personale&quot;, &quot;tutti&quot;, &quot;utenti&quot;) |
| 2-3 aree tematiche concrete | Più di 6 argomenti in un unico messaggio: si ottengono contorni sovraccarichi; al loro posto, vengono suddivisi in corsi separati |
| Un segnale ambito: durata, profondità o risultato dell’Allievo | Obiettivi generici (&quot;insegnare loro tutto su X&quot;, &quot;coprire tutti gli aspetti di&quot;) |
| Contesto che forma il tono o la profondità (&quot;per conformità&quot;, &quot;per un pubblico non tecnico&quot;, &quot;basato su scenari&quot;) | Fare domande all&#39;intelligenza artificiale. Il messaggio è breve, non una conversazione |
| Cosa potranno fare gli Allievi dopo il corso | Contenuto del corso (lasciare la struttura alla fase di struttura) |

## Suggerimenti per il corso in base al tipo di corso

| **Tipo di corso** | **Messaggio per iniziare** |
|--------------------------------|----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| **Corso di formazione sulla conformità** | &quot;Voglio creare un corso di 20 minuti per tutti i dipendenti che si occupano della gestione dei dati GDPR, che copra ciò che è considerato come un dato personale, come archiviarlo e condividerlo correttamente e cosa fare in caso di violazione.&quot; |
| **Onboarding** | &quot;Creare un modulo di onboarding per il nuovo \[ruolo\] che copra \[argomento 1\], \[argomento 2\] e \[argomento 3\]. |
| **Abilità tecniche** | &quot;Voglio creare un corso per i tecnici informatici junior sulle pratiche di codifica sicura, come la prevenzione dell&#39;iniezione SQL, la convalida dell&#39;input e come leggere un report SAST&quot;. |
| **Capacità relazionali** | &quot;Voglio creare un corso di 30 minuti per i responsabili della vendita al dettaglio in prima linea sul fornire feedback costruttivi, ad esempio sul modello SBI, su come prepararsi per una conversazione sul feedback e su come dare seguito alle decisioni prese.&quot; |
| **Criteri e procedura** | &quot;Voglio creare un corso per il personale del magazzino sulle procedure di movimentazione manuale, come la corretta tecnica di sollevamento, quando utilizzare le attrezzature e come segnalare un incidente.&quot; |
| **Formazione sul prodotto** | &quot;Desidero creare un corso per gli agenti dell&#39;assistenza clienti sulla nostra politica di restituzioni, ad esempio per illustrare i criteri di idoneità, come elaborare una restituzione in \[sistema\] e come gestire le escalation.&quot; |
| **Abilitazione alle vendite** | &quot;Voglio creare un corso per gli amministratori degli account di livello intermedio sulla negoziazione di accordi aziendali, ad esempio, che copra come identificare i responsabili delle decisioni, come gestire le obiezioni sui prezzi utilizzando la nostra struttura di valore e quando inoltrare la richiesta a un direttore vendite.&quot; |
| **Sviluppo della leadership** | &quot;Voglio creare un corso di 45 minuti per i manager delle persone che per la prima volta affrontano come gestire in modo efficace un rapporto 1:1 settimanale, ad esempio definendo un programma, riconoscendo e affrontando tempestivamente il problema delle prestazioni insoddisfacenti.&quot; |
| **Formazione su sistemi e strumenti** | &quot;Voglio creare un corso per i coordinatori delle risorse umane che non hanno mai lavorato in Workday, ad esempio per illustrare come creare una richiesta di lavoro, far passare un candidato in diverse fasi di assunzione e generare un report sull&#39;headcount&quot;. |
| **Salute e sicurezza** | &quot;Voglio creare un corso di aggiornamento per tutto il personale del sito sulle procedure di sicurezza antincendio, per esempio, coprendo la via di evacuazione per ogni zona dell&#39;edificio, come utilizzare un estintore e cosa fare se si scopre un incendio al di fuori dell&#39;orario di lavoro.&quot; |

## Cosa succede quando un messaggio è troppo vago?

Se il suggerimento è ampio, l&#39;intelligenza artificiale genera un breve schema generico. Il contorno può coprire l&#39;area del soggetto corretta, ma manca della struttura specifica di cui ha bisogno il tuo corso. La modifica della struttura richiede più tempo a livello di conversazione di quanto non sia stato necessario per scrivere un messaggio migliore.

I segni più comuni indicano che un suggerimento è troppo vago:

- Il profilo Allievo della descrizione è generico (&quot;dipendenti che desiderano conoscere X&quot;) anziché specifico per un ruolo

- Lo schema include titoli di lezioni che potrebbero essere applicabili a qualsiasi corso sull&#39;argomento (&quot;Introduzione&quot;, &quot;Concetti chiave&quot;, &quot;Riepilogo&quot;)

- L&#39;obiettivo non definisce un comportamento misurabile. Descrive invece l’argomento del corso

## Procedure ottimali

- Scrivere la richiesta prima di aprire Composizione contenuti. Una frase scritta in anticipo tende ad essere più chiara di una digitata sotto la pressione del campo di input.

- Assegnare un nome al gruppo di destinatari in base al ruolo e non in base alle dimensioni. &quot;Nuovi rappresentanti&quot; è più utile di &quot;un grande team di dipendenti&quot;.

- Limita il prompt a 2-3 argomenti. Altri argomenti generano contorni sovraccarichi. Se il soggetto richiede più di tre lezioni, crea corsi separati.

- Considera il prompt come punto di partenza. I campi brevi sono modificabili. Se il suggerimento dell&#39;IA è vicino ma non corretto, perfeziona il campo direttamente invece di riscrivere il messaggio da zero.
