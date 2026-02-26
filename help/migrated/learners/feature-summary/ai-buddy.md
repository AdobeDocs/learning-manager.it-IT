---
description: L’Assistente AI (Beta) per gli Allievi è un compagno di chat basato su GenAI in Adobe Learning Manager che aiuta gli Allievi a ottenere risposte rapide e precise dai contenuti di apprendimento assegnati. Tramite le query in linguaggio naturale, gli Allievi possono recuperare immediatamente risposte mirate con citazioni chiare, semplificando la ricerca delle informazioni corrette, la verifica delle fonti e l’apprendimento in modo efficiente senza dover cercare nell’intero corso.
jcr-language: en_us
title: Assistente all’intelligenza artificiale per gli Allievi in Adobe Learning Manager
exl-id: 8203488d-74a6-4463-9383-76d16cabccfa
source-git-commit: 64765bdd9f364267f7c7f5d23a03cc576b875be3
workflow-type: tm+mt
source-wordcount: '2008'
ht-degree: 0%

---

# Assistente AI per gli Allievi

L’Assistente AI (Beta) per gli Allievi consente loro di trovare rapidamente le risposte dai contenuti di apprendimento assegnati senza sfogliare l’intero corso. Puoi porre domande in un linguaggio semplice e ricevere risposte accurate e mirate con collegamenti sorgente al contenuto del corso pertinente.

>[!IMPORTANT]
>
>L’Assistente AI per gli Allievi è attualmente disponibile come funzione beta. Le funzionalità, gli scenari supportati e le limitazioni possono cambiare con l&#39;evolversi della funzionalità.


## Che cos’è l’Assistente all’intelligenza artificiale per gli Allievi

L’Assistente AI è un compagno di chat basato su GenAI in Adobe Learning Manager che fornisce risposte rapide e precise alle domande degli Allievi utilizzando i contenuti di apprendimento affidabili disponibili in Adobe Learning Manager. Include anche le citazioni, in modo che gli Allievi conoscano sempre la fonte delle informazioni.

### Funzionalità principali di AI Assistant

1. Risposta intelligente alle domande
   * Conversazioni a turno singolo e a turni multipli
   * Conoscenza della lingua naturale in inglese
   * Risposte derivate da corsi, certificazioni, percorsi di apprendimento e risorse formative
   * Chiarire le domande quando le query sono ambigue
   * Basato sulle funzionalità LLM dell&#39;intelligenza artificiale aperta di Azure per generare risposte
2. Fonti di contenuto e citazioni
   * Recupera le risposte dalle risorse disponibili presenti nei cataloghi supportati.
   * Fornisce citazioni con collegamenti diretti ai materiali di origine
   * Supporta tutti i formati di contenuto ALM statici e interattivi: PDF, DOCX, PPTX, XLSX, Audio (mp3, wav, m4a), Video (mp4, mov, wmv), HTML, SCORM 2004, SCORM 1.2
3. Esperienza utente
   * Interfaccia del pannello laterale accessibile da tutte le pagine dell’Allievo
   * Design reattivo che si adatta all&#39;area dei contenuti
   * Cronologia chat gestita nella sessione del browser
   * Pulisci la lavagna al nuovo accesso o all&#39;aggiornamento della pagina
   * Tono insegnante o tutor: amichevole, chiaro e pedagogicamente sonoro
4. Controlli amministratore
   * Attivare o disattivare la funzione a livello di account
   * Controllare l&#39;accesso per gruppi di utenti
   * Seleziona i cataloghi inclusi per le risposte basate su IA
   * Requisito di accettazione delle Condizioni d’uso per seguire le linee guida dell’intelligenza artificiale di Adobe

## Quali tipi di contenuti sono supportati da AI Assistant

L’Assistente AI recupera informazioni dai contenuti di apprendimento assegnati all’utente, tra cui:

* **Documenti:** PDF, Word, PowerPoint, Excel, HTML
* **File multimediali:** audio (mp3, wav, m4a), video (mp4, mov, wmv)
* **Contenuto interattivo:** SCORM 1.2, SCORM 2004
* **Tipi di oggetti di apprendimento:** corsi, percorsi di apprendimento, certificazioni, risorse formative

Adobe trascrive in modo sicuro i contenuti di apprendimento utilizzando servizi di elaborazione di terze parti affidabili ospitati nell’ambiente VPC privato di Adobe.

### Limitazioni del catalogo e dell&#39;origine dei contenuti

L’Assistente all’intelligenza artificiale dell’Allievo utilizza solo i contenuti dei **cataloghi interni** configurati in modo esplicito dagli Amministratori.

Le seguenti origini di contenuto non sono **supportate** nella versione corrente:

* Cataloghi condivisi
* Cataloghi acquisiti
* Cataloghi esterni
* Cataloghi predefiniti
* Librerie di contenuti di terze parti (ad esempio, LinkedIn Learning o Go1)

Se un Allievo non ha accesso a un corso o a una risorsa formativa, l’Assistente AI non presenterà informazioni da tale contenuto e i collegamenti delle citazioni non saranno accessibili.

## Casi di utilizzo di AI Assistant

### Allievo tecnico

Sarah è un tecnico di vendita che sta imparando a usare le schede grafiche. Deve comprendere rapidamente le specifiche tecniche e i vantaggi per rispondere con sicurezza alle domande dei clienti.

L&#39;Assistente AI aiuta Sarah con:

* Spiegazione tecnica chiara della complessa architettura GPU
* Approfondisci la comprensione delle varie schede grafiche e delle loro differenze
* Spiegazione degli esempi in modo che Sarah possa mettere in relazione le funzionalità con casi d&#39;uso reali

### Assistenza clienti

Marcus è uno specialista di supporto in un&#39;azienda partner. Ha bisogno di risposte rapide sulle funzionalità del prodotto per aiutare i clienti senza rivolgersi ai team tecnici.

L&#39;Assistente AI aiuta Marcus con:

* Trovare contenuti di supporto pertinenti per le domande frequenti dei clienti
* Chiedere chiarimenti quando la risposta iniziale non è abbastanza specifica
* Trovare consigli per i relativi corsi di risoluzione dei problemi per migliorare le sue competenze

### Inserimento di nuovi dipendenti

Jennifer è appena entrata a far parte dell&#39;azienda ed è sopraffatta dalla quantità di materiale formativo. Ha bisogno di un modo per trovare informazioni specifiche senza rivedere interi corsi.

L&#39;assistente AI aiuta Jennifer con:

* Informazioni dettagliate sull&#39;invio delle note spese
* Individuazione di corsi sulle policy aziendali senza consultare l’intero catalogo
* Guidarla fino alla sezione appropriata di un corso senza farle guardare ore di video

## In che modo l&#39;Assistente AI utilizza i contenuti

L&#39;Assistente AI ti aiuta a trovare rapidamente risposte accurate mentre impari. Per utilizzarlo in modo efficace, è necessario comprendere quale contenuto viene utilizzato dall&#39;assistente, quali elementi non vengono utilizzati e come vengono generate le risposte.

### Quali contenuti utilizza l&#39;Assistente AI

L’Assistente AI risponde alle domande utilizzando solo i contenuti di apprendimento abilitati dall’amministratore dell’account. Il contenuto del catalogo è indicizzato.

L’Assistente all’intelligenza artificiale analizza i contenuti di apprendimento assegnati per generare risposte mirate e contestuali.

* Ogni risposta include citazioni che fanno riferimento al contenuto sorgente originale.
* Puoi selezionare una citazione per passare direttamente al corso, al modulo o al documento pertinente.
* Le citazioni consentono di verificare le informazioni ed esplorare ulteriori contesti quando necessario.

### Risposte in streaming

Una risposta in streaming indica che l&#39;Assistente AI fornisce la risposta progressivamente man mano che viene generata, in modo che gli utenti possano iniziare a leggere immediatamente la risposta senza attendere che l&#39;intera risposta finisca il caricamento.

### Citazioni e trasparenza sorgente

Ogni risposta all’Assistente AI include citazioni che si collegano direttamente al corso, al modulo o all’oggetto di apprendimento originale. Le citazioni consentono di:

* Selezionare un numero di citazione agganciato per passare alla sezione con riferimento esatto
* Aprire l&#39;elenco completo delle origini selezionando Mostra origini nella parte inferiore della risposta
* Verifica le informazioni ed esplora il contesto aggiuntivo dalla fonte autorevole

>[!IMPORTANT]
>
>L&#39;Assistente AI fornisce le risposte in base al contenuto abilitato dall&#39;amministratore, ma se un utente non dispone dell&#39;accesso a un elemento di riferimento, visualizzerà un messaggio &quot;non supportato&quot; all&#39;apertura.


## Suggerimenti incorporati

L’Assistente all’intelligenza artificiale include prompt incorporati per aiutare gli Allievi a iniziare rapidamente con domande e scenari comuni. Queste istruzioni guidano gli allievi su come interagire con l’assistente e mostrano i tipi di domande che possono porre.

![Suggerimenti incorporati forniti dall’Assistente Allievo](assets/built-in-prompt-new.png)

Le richieste predefinite sono personalizzabili per account. Le organizzazioni possono personalizzarle in base ai loro obiettivi di apprendimento, ai ruoli degli Allievi, alla terminologia o a casi d’uso specifici. Gli amministratori possono collaborare con il proprio Customer Success Manager (CSM) per configurare o aggiornare le richieste incorporate.

La personalizzazione dei prompt viene gestita a livello di account e non è configurabile direttamente nell’interfaccia utente di Adobe Learning Manager nella versione corrente.

## Configurazione Amministratore: attivazione dell’Assistente all’intelligenza artificiale per gli Allievi

![Assistente Allievo abilitato all’intelligenza artificiale](assets/learner-ai-assistant-new.png)

Gli amministratori selezionano i gruppi di utenti e i cataloghi interni che possono accedere alla funzione Assistente intelligenza artificiale. Devono assicurarsi che i cataloghi assegnati includano solo i contenuti di apprendimento che è appropriato far emergere attraverso le risposte e le citazioni dell&#39;intelligenza artificiale e che tali cataloghi siano Predefiniti, Interni, non Condivisi, Acquisiti o Esterni.

Prima di configurare l&#39;Assistente all&#39;intelligenza artificiale, verifica di disporre delle credenziali di amministratore e di aver identificato i gruppi di utenti e i cataloghi a cui deve essere consentito l&#39;accesso alla funzione.

### Configurare l&#39;accesso Assistente intelligenza artificiale

Per abilitare l’Assistente all’intelligenza artificiale dell’Allievo:

1. Accedi a Adobe Learning Manager come amministratore.

2. Selezionare **Impostazioni** dalla home page.
   ![Console di amministrazione con opzione Impostazioni nel riquadro sinistro](assets/settings-menu.png)

3. Seleziona **Assistente AI Allievo (Beta)** dal menu **Impostazioni**.
   ![La console dell’amministratore visualizza l’opzione Assistente intelligenza artificiale Allievo nel riquadro a sinistra](assets/learner-assistant-ai-beta.png)

4. Seleziona l’interruttore per attivare **Assistente AI Allievo (Beta)**.
   ![Nella console Amministratori viene visualizzato l’interruttore abilitato per l’Assistente AI Allievo](assets/learner-assistant-toggle.png)

5. Seleziona uno o più gruppi di utenti dall&#39;opzione **Gruppi di utenti idonei**.

6. Seleziona **Salva** per applicare le impostazioni del gruppo di utenti.

7. Seleziona uno o più cataloghi dall&#39;opzione **Cataloghi idonei**.

8. Seleziona **Salva** per applicare le impostazioni del catalogo.

>[!IMPORTANT]
>
>Solo i cataloghi interni sono supportati da AI Assistant. Se viene selezionato un catalogo condiviso, acquisito, esterno o un altro catalogo non interno, il relativo contenuto non verrà visualizzato dall&#39;Assistente all&#39;intelligenza artificiale, anche se il catalogo viene visualizzato nell&#39;elenco Cataloghi idonei.

## Guida per gli Allievi: avvia l’Assistente all’intelligenza artificiale

### Avvia l&#39;Assistente AI

Per avviare l&#39;Assistente all&#39;intelligenza artificiale:

1. Accedi a Adobe Learning Manager come Allievo.

2. Seleziona **Chiedi Assistente AI** nella home page.
   ![La home page dell’Allievo visualizza Chiedi all’Assistente AI di selezionare e aprire il pannello dell’Assistente AI dell’Allievo](assets/ask-ai-assistant.png)

3. Quando viene visualizzata la schermata **Assistente AI Allievo**, seleziona **Introduzione**.
   ![Selezionare Introduzione per avviare l’Assistente Allievo](assets/get-started-learner-assistant.png)

>[!NOTE]
>
>Quando avvii l&#39;Assistente all&#39;intelligenza artificiale per la prima volta, devi fornire il tuo consenso prima di utilizzarlo. La finestra di dialogo di consenso verrà visualizzata solo durante questo avvio iniziale. Per tutti gli avvii successivi, verrai indirizzato direttamente all&#39;Assistente AI per inserire le tue richieste.

&#x200B;4. Digita il messaggio nel campo di testo.

![Digitare il prompt nell&#39;Assistente Allievo](assets/type-prompt-new.png)

&#x200B;5. Premi **Invio** per ricevere una risposta. Rivedi la tua risposta, le tue fonti e i tuoi consigli.

È possibile:

* Selezionare il numero di citazione in linea per passare alla sezione di riferimento esatta
* Aprire l&#39;elenco completo delle origini selezionando **Mostra origini** nella parte inferiore della risposta

![Visualizza origini nella risposta](assets/show-sources-latest.png)

L&#39;Assistente AI include citazioni con ogni risposta per mostrare da dove provengono le informazioni. Ogni citazione si collega direttamente al corso, modulo o oggetto di apprendimento originale utilizzato per generare la risposta.

Puoi selezionare qualsiasi citazione per aprire la pagina del corso effettivo in Adobe Learning Manager e rivedere l’intero contenuto nel contesto. Le citazioni consentono di verificare le informazioni, esplorare ulteriori dettagli e continuare ad apprendere dalla fonte autorevole.

## Accedere all&#39;Assistente AI tramite la ricerca

Potete anche avviare l&#39;Assistente AI direttamente dalla barra di ricerca. Digita la domanda nel campo di ricerca, quindi seleziona **Chiedi assistente AI** dalle opzioni visualizzate per ottenere le risposte dai contenuti di apprendimento assegnati.Ha assegnato i contenuti di apprendimento.

![Accedere all’Assistente Allievo dalla barra di ricerca](assets/learner-assistant-search-new.png)


## Fornisci feedback sulle risposte dell’assistente di intelligenza artificiale dell’Allievo

Il tuo feedback sulle risposte generate dall’Assistente all’intelligenza artificiale degli allievi (Beta) aiuta a migliorarne l’accuratezza, la pertinenza e le prestazioni complessive.

### Mettere Mi piace o Non mi piace a una risposta

* Seleziona **Pollice in alto**, scegli gli elementi che hai trovato utili nella risposta, aggiungi facoltativamente commenti, quindi seleziona **Invia**.

![Selezionare Pollice in alto per votare una risposta](assets/la-feedback.png)

* Seleziona **Pollice giù**, scegli il motivo per cui la risposta non è stata utile, aggiungi eventuali commenti, quindi seleziona **Invia**.

## Avvia una nuova chat in Assistente AI

L’avvio di una nuova chat consente all’utente di iniziare una nuova conversazione, cancellando il contesto precedente in modo che l’assistente possa concentrarsi sul nuovo argomento senza fare riferimento alle interazioni precedenti. Questo è importante quando si cambia argomento o si cercano risposte non correlate a domande precedenti.

Cancella la conversazione corrente e avvia una nuova chat in qualsiasi momento.

Seleziona **Nuova chat** nella schermata dell&#39;Assistente AI, quindi seleziona **Sì**.

![Avvia una nuova chat in Assistente Allievo](assets/start-new-chat.png)

L’Assistente AI fornisce agli Allievi risposte rapide e contestuali, supporta più tipi di contenuto e offre citazioni inline per la trasparenza. Gli amministratori possono controllare l’accesso, verificando che l’Assistente all’intelligenza artificiale sia personalizzato in base alle esigenze dell’organizzazione e migliori l’esperienza di apprendimento.


## Risoluzione dei problemi

>[!NOTE]
>
>Dopo aver configurato un nuovo catalogo, attendi 4-5 ore prima che i contenuti vengano indicizzati e siano disponibili per le risposte dell&#39;Assistente AI.

### Scenario 1: nessun accesso ai contenuti

Problema: l’Allievo ha accesso all’Assistente Allievo ma riceve risposte &quot;Non ho una risposta a questa domanda&quot;.

**Cause possibili**

* I cataloghi dell’Allievo non sono inclusi durante la configurazione di AI Assistant
* Il contenuto correlato alla domanda non si trova nei cataloghi selezionati o i cataloghi sono vuoti
* L’Allievo non ha visibilità sui contenuti pertinenti

**Soluzione**

* Verifica dell’accesso al catalogo dell’Allievo
* Verifica quali cataloghi sono abilitati nelle impostazioni di Assistente Allievo
* Assicurati che i contenuti pertinenti esistano in tali cataloghi
* attendere alcune ore dall&#39;aggiunta di nuovo contenuto per l&#39;indicizzazione

### Scenario 2: risposte irrilevanti o di scarsa qualità

**Problema**: l&#39;Assistente AI fornisce risposte che non corrispondono alla domanda o di qualità inferiore.

**Cause possibili**

* Domanda troppo ampia o ambigua
* I metadati del contenuto rilevante sono scarsi (descrizioni, tag)
* La struttura del contenuto rende difficile l&#39;estrazione delle informazioni

**Soluzione**

* Incoraggiare gli Allievi a porre domande più specifiche
* Revisione e miglioramento delle descrizioni dei corsi e dei metadati
* Assicurati che i contenuti abbiano intestazioni e struttura chiare
* Esaminare il rapporto dettagliato sull&#39;utilizzo per identificare i modelli
* Considera la possibilità di creare risorse formative per le domande frequenti

### Scenario 3: domande non comprese nell’ambito

**Problema**: l’Allievo pone domande non correlate al contenuto della formazione.

**Esempi**:

* Domande generali sulle conoscenze (&quot;Chi è il presidente?&quot;)
* Opinioni personali (&#39;Cosa ne pensi di X?&#39;)
* Contenuto non appropriato
