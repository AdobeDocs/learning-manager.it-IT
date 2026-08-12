---
title: Guida alla risoluzione dei problemi per Live Hub (Beta)
description: Messaggi di errore e notifiche comuni che potresti incontrare durante una sessione di Live Hub, loro cause e passaggi per risolverli.
source-git-commit: 43d4a9fb47d94ef541984a1c1fb9c70ba4e3f61d
workflow-type: tm+mt
source-wordcount: '1011'
ht-degree: 2%

---


# Guida alla risoluzione dei problemi per Live Hub (Beta)

Durante una sessione Hub dal vivo, gli Istruttori potrebbero ricevere messaggi di errore o notifiche che impediscono il completamento previsto di determinate azioni. Questo articolo descrive gli errori comuni relativi agli istruttori, le loro possibili cause e i passaggi da eseguire per risolverli.

## Problemi di connessione

| Messaggio di errore | Scenario | Suggerimenti per superare l&#39;errore |
|---|---|---|
| Si è verificato un errore. Riprova. | Si verifica un errore generale di connettività o relativo alla sessione, ad esempio, quando si partecipa o si interagisce con una sessione e la richiesta non riesce a causa di instabilità di rete, una sessione ALM scaduta o uno stato del browser in conflitto, ad esempio più schede aperte per la stessa riunione. | <ul><li>Controlla la connessione di rete e assicurati che la larghezza di banda sia stabile e che non vi siano interferenze VPN o proxy.</li><li>Conferma di aver effettuato l&#39;accesso ad ALM con una sessione valida: disconnettiti e accedi di nuovo se la sessione potrebbe essere scaduta.</li><li>Evitare di partecipare alla stessa riunione da più schede contemporaneamente.</li><li>Se il problema persiste, provate a utilizzare una finestra in incognito/privata o cancellate la cache del browser.</li><li>Aggiorna la pagina: la maggior parte degli errori temporanei si risolve dopo un ricaricamento; se si ripete, contatta il supporto tecnico.</li></ul> |

## Problemi della scheda del quiz

I messaggi seguenti possono essere visualizzati quando un Istruttore crea o avvia un quiz che, tuttavia, non soddisfa i requisiti necessari per avviarlo.

| Messaggio di errore | Scenario | Suggerimenti per superare l&#39;errore |
|---|---|---|
| Per continuare, immetti una domanda. | Un Istruttore tenta di avviare un quiz senza inserire il testo della domanda. | Inserisci la domanda, fornisci le opzioni di risposta, seleziona la risposta corretta e quindi avvia il quiz per i partecipanti. |
| Le opzioni di risposta non possono essere lasciate vuote. | L’Istruttore inserisce il testo della domanda ma non inserisce le opzioni di risposta o lascia vuote una o più opzioni di risposta. | Inserisci la domanda, fornisci le opzioni di risposta, seleziona la risposta corretta e quindi avvia il quiz per i partecipanti. |
| Contrassegna la risposta corretta. | L’Istruttore immette le opzioni di domanda e risposta ma non seleziona un’opzione di risposta corretta. | Inserisci la domanda, fornisci le opzioni di risposta, seleziona la risposta corretta e quindi avvia il quiz per i partecipanti. |

## Problemi della scheda sondaggio

I messaggi seguenti possono essere visualizzati quando un Istruttore duplica, elimina o reimposta un sondaggio.

| Messaggio di errore | Scenario | Suggerimenti per superare l&#39;errore |
|---|---|---|
| Impossibile duplicare il sondaggio. Riprova. | Un Istruttore duplica un sondaggio esistente e il duplicato non viene creato. | Chiudi il pannello Sondaggi e quiz e riprova a duplicare il sondaggio. |
| Impossibile eliminare tutti i sondaggi. Riprova. | Un Istruttore elimina tutti i polling contemporaneamente utilizzando Elimina tutto, e l’eliminazione in blocco non riesce o viene completata solo parzialmente. | Chiudi il pannello Poll e quiz e riprova ad eliminare i sondaggi utilizzando Elimina tutti i sondaggi. |
| Impossibile eliminare il sondaggio. Riprova. | Un Istruttore elimina un singolo sondaggio e l’eliminazione non viene completata. | Chiudi il pannello Sondaggi e quiz e riprova ad eliminare il sondaggio. |
| Impossibile reimpostare il sondaggio. Riprova. | Un Istruttore reimposta un sondaggio eseguito in precedenza in modo che possa essere riutilizzato e il ripristino non viene completato. | Chiudi il pannello Sondaggi e quiz e riprova a reimpostare il sondaggio. |

## Problemi di caricamento dei contenuti

Il messaggio seguente può essere visualizzato quando un Istruttore carica un file di riferimento utilizzato dall’assistente AI per rispondere a delle domande.

| Messaggio di errore | Scenario | Suggerimenti per superare l&#39;errore |
|---|---|---|
| Impossibile elaborare il file. Riprova. | Un Istruttore carica un file danneggiato, vuoto o protetto da password che non può essere elaborato. | Converti il file in un formato supportato (PDF o PPT) e caricalo di nuovo. |

## Problemi relativi al caricamento di avvisi popup di contenuto

I messaggi seguenti vengono visualizzati come notifiche di tipo avviso popup quando un Istruttore carica un file di riferimento che l’assistente AI utilizzerà e il file non supera un controllo di convalida specifico.

| Messaggio di errore | Scenario | Suggerimenti per superare l&#39;errore |
|---|---|---|
| Impossibile elaborare il file. Controllare il file e riprovare. | Un Istruttore carica un file danneggiato. | Verifica il formato del file e convertilo in un formato supportato (PDF o PPT), quindi ricarica. |
| Il file è protetto da password. Rimuovi la password e ricarica. | Un Istruttore carica un file protetto da password. | Rimuovi la protezione con password dal file, quindi ricaricalo. |
| Il file non ha contenuto da elaborare. Carica un file con contenuto testuale. | Un Istruttore carica un file che non ha contenuto per l’elaborazione da parte dell’assistente AI. | Carica un file contenente testo. |
| &quot;FileName.pdf&quot; supera il limite di 1 MB. | Un Istruttore carica un file PDF che supera il limite di 1 MB per le dimensioni del file. | Comprimi o riduci le dimensioni del file PDF a meno di 1 MB, quindi ricarica. |
| &quot;FileName.pptx&quot; supera il limite di 3 MB. | Un Istruttore carica un file PPT che supera il limite di 3 MB per le dimensioni del file. | Comprimi o riduci le dimensioni del file PPT a meno di 3 MB, quindi ricarica. |

## Problemi della sessione di analisi

I messaggi seguenti possono essere visualizzati quando un Istruttore tenta di avviare una sessione di breakout.

| Messaggio di errore | Scenario | Suggerimenti per superare l&#39;errore |
|---|---|---|
| Impossibile avviare l&#39;interruzione. Connessione interrotta. Riprova quando ti sarai riconnesso. | Un Istruttore tenta di avviare le breakout room mentre la connessione è attualmente interrotta o si riconnette. | Attendi che la connessione si stabilizzi (controlla un indicatore di riconnessione), quindi avvia di nuovo le sale d&#39;attesa. |
| Impossibile avviare l&#39;interruzione. Riprova. | Un Istruttore avvia le breakout room e la richiesta di avviarle non riesce. | Riprovate ad avviare le sale stampa. Se il problema persiste, chiudere il pannello Breakouts e riprovare. |
| Impossibile generare il riepilogo. | Ciò può verificarsi nelle seguenti situazioni: <ul><li>Nessun utente ha parlato durante la sessione, quindi non ci sono contenuti audio da riepilogare.</li><li>Discussione inferiore a 60 secondi.</li></ul> | Assicurati che i partecipanti parlino attivamente per almeno 60 secondi durante la sessione prima di generare il riepilogo. Se il problema persiste, attendi qualche istante e riprova. |

## Rispondere ai problemi relativi ai messaggi pubblicitari

Il messaggio seguente può essere visualizzato quando un Istruttore chiede all’assistente AI di generare una risposta alla domanda di un Partecipante nella chat.

| Messaggio di errore | Scenario | Suggerimenti per superare l&#39;errore |
|---|---|---|
| Questo argomento non è stato trattato durante la sessione. | Un Allievo pone una domanda che non è trattata nel riferimento al contenuto caricato. Questo è il comportamento previsto, non un errore. | Rispondi alla domanda manualmente. |
