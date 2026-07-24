---
jcr-language: en_us
title: Set di dati disponibili nel Report Builder
description: Guida di riferimento ai set di dati, ai campi e ai campi derivati disponibili in Adobe Learning Manager Report Builder.
contentowner: mmanuel
source-git-commit: 8823a5481bc3b34266f7ec36a8f3c26cb923e1ce
workflow-type: tm+mt
source-wordcount: '1410'
ht-degree: 12%

---


# Set di dati disponibili nel Report Builder

## Panoramica

Il Report Builder organizza tutte le colonne disponibili in set di dati, denominati gruppi di campi correlati. In questo articolo vengono elencati tutti i set di dati, vengono descritti i relativi contenuti e vengono indicate le serie di dati che è possibile combinare in un unico report.

## **Set di dati disponibili**

Le informazioni nella tabella non sono esaustive. Per un elenco completo di tutte le colonne nei dataset, vedere la sezione **Elenco di colonne nei dataset**.

| **Set Di Dati** | **Cosa contiene** | **Campi chiave** |
|----------------------------------------------------------|--------------------------------------------------------------------------|---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| **Utente** | Dati del profilo Allievo per gli Allievi attivi ed eliminati | Nome, e-mail, ID utente, Manager, campi attivi, stato |
| **Trascrizione (oggetto di apprendimento) e trascrizione (modulo)** | Record di iscrizione e completamento | Data di iscrizione, data di completamento, percentuale di avanzamento, stato |
| **Oggetto di apprendimento** | Metadati di corsi, percorsi di apprendimento e certificazioni | Nome dell’oggetto di apprendimento, ID dell’oggetto di apprendimento, tipo, catalogo, etichetta del catalogo, stato |
| **Istanza oggetto di apprendimento** | Dettagli a livello di istanza per i corsi con più istanze | Nome dell’istanza, ID dell’istanza, limite di iscrizione, scadenza |
| **Catalogo** | Coppie chiave-valore per metadati del catalogo ed etichetta del catalogo | Nomi degli autori, data di creazione, durata, formato. **Le colonne dell&#39;etichetta del catalogo sono configurate dal cliente**. Vengono visualizzate solo se nel tuo account sono impostate etichette del catalogo. I nomi e i valori delle etichette che vedi rifletteranno la tua configurazione. |
| **Gruppo utenti** | Appartenenza al gruppo di utenti e gerarchia | Data di creazione, conteggio membri, nome, stato |
| **Modulo** | Dettagli della sessione per aula, aula virtuale e moduli di e-learning | ID modulo, nome/i istruttore, ora di inizio, ora di fine, posizione |


>[!NOTE]
>
>Per i corsi acquisiti da un altro account tramite la condivisione del catalogo, la colonna **Nomi autori** nel set di dati dell’oggetto di apprendimento restituisce il nome dell’autore originale dall’account di origine. Questo si differenzia dall&#39;interfaccia di amministrazione ALM standard e dai report fissi, in cui i corsi acquisiti visualizzano invece &quot;Autore esterno&quot;. Questo comportamento è specifico del Report Builder e si applica solo agli account condivisi tra pari (in ricezione).

## Elenco delle colonne nei dataset

### Widget

* Data creazione
* ID

* Nome

### Etichetta del catalogo

* ID
* Nome
* Valore

### Campo personalizzato (oggetto di apprendimento)

* % completamento oggetto di apprendimento
* % conformità oggetto di apprendimento

### Campo personalizzato (utente)

* % completamento utente
* % conformità utente

### Oggetto di apprendimento

* Nomi degli autori
* Data smobilizzo automatico
* Conteggio completamento
* Data creazione
* Durata (minuti)
* Conteggio delle iscrizioni
* Tipo di iscrizione
* Formato
* ID
* Opzione istanza abilitata
* Data ultimo completamento
* Data ultima pubblicazione
* Iscrizione multipla abilitata
* Nome
* Prerequisiti applicati
* Prezzo
* Credito abilità
* Livello di abilità
* Nome abilità
* Media valutazione a stelle
* Conteggio valutazioni a stelle
* Conteggio avviato
* Stato
* Tag
* Tipo
* ID univoco

### Istanza dell’oggetto di apprendimento

* Scadenza completamento
* Data creazione
* Scadenza iscrizione
* ID
* Data ultimo completamento
* ID oggetto di apprendimento
* Nome
* Stato
* Tipo
* Scadenza annullamento iscrizione

### Modulo

* Ora di fine accesso
* Ora di inizio accesso
* ID corso
* ID istanza del corso
* Durata (minuti)
* Ora di fine
* Conteggio delle iscrizioni
* ID
* Nomi degli istruttori
* Posizione
* Informazioni sulla posizione
* Regione della posizione
* URL posizione
* ID modulo
* Nome
* Posti limitati
* Ora di inizio
* Tipo
* Limite per la lista d’attesa

### Trascrizione (oggetto di apprendimento)

* Data di completamento
* Scadenza completamento
* Origine completamento
* Origine completamento * ID utente
* Origine completamento * Nome utente
* Data di iscrizione
* Origine iscrizione
* Stato iscrizione
* ID oggetto di apprendimento
* Nome dell’oggetto di apprendimento
* ID istanza oggetto di apprendimento
* Scaduta
* ID oggetto di apprendimento principale
* Data di superamento
* Percentuale avanzamento
* ID certificazione radice
* Data di inizio
* Stato
* Tempo impiegato (minuti)
* Punteggio più alto utente
* ID utente
* Punteggio più recente utente

### Trascrizione (Modulo)

* Data di completamento
* ID corso
* ID modulo
* Nome del modulo
* Data di superamento
* Percentuale avanzamento
* Punteggio totale del modulo del quiz
* Data di inizio
* Stato
* Tempo impiegato (minuti)
* E-mail utente
* Punteggio più alto utente
* ID utente
* Punteggio più recente utente
* Nome utente

### Utente

* Adobe ID
* Lingua del contenuto
* Data creazione
* Data di eliminazione
* Conteggio membri team diretti
* E-mail
* ID
* Lingua dell’interfaccia
* Amministratore
* Autore
* Ruolo personalizzato
* Istruttore
* Amministratore dell’integrazione
* Allievo
* Manager
* Utente radice
* Data ultimo accesso
* E-mail del manager
* ID manager
* Nome del manager
* ID univoco manager
* Nome
* Ruoli
* Origine
* Stato
* Conteggio membri del team
* Fuso orario
* Tipo
* ID univoco

### Gruppo utenti

* Data creazione
* ID
* Conteggio membri
* Nome
* Stato

### Gruppo di utenti (campo attivo)

* Data creazione
* ID
* Conteggio membri
* Nome
* Stato

### Gruppo di utenti (personalizzato)

* Data creazione
* ID
* Conteggio membri
* Nome
* Stato

### Gruppo di utenti (team diretto)

* Data creazione
* ID
* Conteggio membri
* Nome
* E-mail proprietario
* ID proprietario
* Nome proprietario
* ID univoco proprietario
* Stato

### Gruppo di utenti (incorporato)

* Data creazione
* ID
* Conteggio membri
* Nome
* Stato

### Gruppo utenti (team)

* Data creazione
* ID
* Conteggio membri
* Descrizione
* Nome
* E-mail proprietario
* ID proprietario
* Nome proprietario
* Stato proprietario
* ID univoco proprietario
* Stato

## Come unire i set di dati

Non è possibile combinare ogni coppia di dataset in un unico report. Per poter essere uniti, i set di dati devono condividere una relazione logica nel modello di dati di Adobe Learning Manager. Quando si aggiunge la prima colonna, Report Builder filtra i set di dati rimanenti per visualizzare solo quelli compatibili. Se un set di dati viene visualizzato in grigio, non può essere unito direttamente alle colonne già selezionate.

Questo significa che il set di dati non può essere unito alle colonne già selezionate. Si tratta di un vincolo rigido nel modello di dati. I due dataset non condividono un percorso di join compatibile.

Un esempio comune è il campo derivato **Conformità %**. Quando è selezionata l&#39;opzione % conformità, i set di dati **Trascrizione**, **Trascrizione modulo** e **Istanza LO** sono disabilitati. La % di conformità viene calcolata a livello di utente o di gruppo di utenti in base agli oggetti di apprendimento e ai cataloghi. Deve essere utilizzato solo insieme alle colonne e ai filtri **Utente**, **Gruppo utenti**, **Oggetto di apprendimento** e **Catalogo**.

Per utilizzare un set di dati disattivato, deselezionare le colonne che causano il conflitto, quindi aggiungere il set di dati necessario.

>[!NOTE]
>
>Se un report generato contiene i dati del corso ma non i dati del percorso di apprendimento, controlla se hai aggiunto il set di dati dell’oggetto di apprendimento al set di dati del modulo. I moduli sono direttamente collegati ai corsi, ma non direttamente ai percorsi di apprendimento. Di conseguenza, quando i campi Modulo sono inclusi, il Report Builder può restituire solo i record del corso e filtrare i percorsi di apprendimento. Per generare report sui percorsi di apprendimento, evita di aggiungere campi modulo a meno che il report non sia progettato specificamente per analizzare i dati del modulo a livello di corso.

Le relazioni di join riportate di seguito sono tratte dal modello di dati del Report Builder. È possibile pianificare le serie di dati da combinare prima di creare un report.

### Set di dati hub

Due set di dati fungono da hub centrali. La maggior parte degli altri set di dati si connette tramite di essi:

* **Registrazione** (set di dati di registrazione), la tabella dei fatti primaria. Si connette direttamente a **Utente** (l’Allievo che si è iscritto), **Oggetto di apprendimento** (l’oggetto a cui si è iscritti) e, tramite l’oggetto di apprendimento, a **Modulo**, **Catalogo**, **Etichetta catalogo** e **Istanza LO**.
* **Trascrizione modulo** (set di dati moduleTranscript): tabella dei fatti relativi all&#39;avanzamento a livello di modulo. Si connette a **Utente** e a **Modulo**, che a sua volta si collega a **Oggetto di apprendimento**.

La maggior parte dei report che combinano i dati di Allievo, corso e completamento sono creati tramite uno di questi due hub.

### Relazioni con alias

Alcuni campi del modello di dati si uniscono all&#39;entità **Utente** tramite un ruolo denominato anziché un ID Allievo diretto. Si tratta di chiavi esterne con alias. I ruoli puntano alla stessa tabella utente ma rappresentano un ruolo diverso:

* **Istruttore**: il modulo si aggiunge all’utente come istruttore della sessione
* **Autore**: l’Autore dell’oggetto di apprendimento si unisce all’Utente come autore dell’oggetto di apprendimento
* **Manager**: l’utente si unisce a se stesso per rappresentare il manager dell’Allievo
* **Completato da**: iscrizione e trascrizione del modulo contengono ciascuno un riferimento utente separato &quot;Completato da&quot;

Ecco perché un singolo report può mostrare sia il nome di un Allievo che il nome del suo istruttore. Entrambi provengono dall’entità Utente tramite diversi percorsi di join.

### Tipi di set di dati del gruppo di utenti

La categoria **Gruppo utenti** contiene diverse visualizzazioni di set di dati distinte, ognuna delle quali copre un tipo diverso di gruppo:

| **Set di dati** | **Tipo di gruppo** |
|---------------------------------------------------------|---------------------------------------------------------------|
| **Gruppo utenti** (gruppo utenti) | Tutti i gruppi di utenti. Utilizza come set di dati del gruppo di utenti principale |
| **Gruppo di utenti (campo attivo)** (campo_attivo_gruppo_utente) | Gruppi basati su valori di campo attivi (ad esempio area geografica, reparto) |
| **Gruppo utenti (team)** (team_user_group) | Gruppi basati sulla gerarchia dei manager |
| **Gruppo di utenti (personalizzato)** (gruppo_utente_personalizzato) | Gruppi personalizzati configurati manualmente |
| **Gruppo utenti (incorporato)** (inbuilt_user_group) | Gruppi definiti dal sistema |

I set di dati del gruppo di utenti basati sulla visualizzazione (**Campo attivo**, **Team**, **Personalizzato**, **Incorporato**) non dispongono di relazioni di chiave esterna dirette nello schema, ma sono viste SQL. Questo significa che hanno vincoli di join più ampi rispetto al set di dati **Gruppo utenti** principale. Per risultati più affidabili, utilizza il set di dati di base **Gruppo utenti** quando unisci i dati del gruppo di utenti con i dati di registrazione o trascrizione.

## Campi derivati

I campi derivati sono colonne precalcolate calcolate per Report Builder. Sono elencati separatamente dalle colonne standard nel selettore di colonne.

| **Campo derivato** | **Elementi calcolati** | **Set di dati richiesti** |
|-------------------------|-------------------------------------------------------------------------|-----------------------------------------|
| **Conformità %** | Percentuale di Allievi obbligati che hanno completato corsi con tag di conformità | Gruppo di utenti, Oggetto di apprendimento, Trascrizione |
| **Completamento %** | Completamenti divisi per iscrizioni x 100 | Trascrizione o Oggetto di apprendimento |
| **Numero utenti iscritti** | Totale degli Allievi iscritti per un oggetto di apprendimento | Oggetto di apprendimento |
| **Conteggio completamenti** | Totale completamenti per un oggetto di apprendimento | Oggetto di apprendimento |
| **Conteggio iniziale** | Allievi che hanno iniziato ma non completato | Oggetto di apprendimento |
| **Conteggio membri** | Numero di utenti in un gruppo di utenti | Gruppo utenti |
