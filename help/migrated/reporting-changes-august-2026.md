---
description: Questo documento riassume le modifiche alla segnalazione di agosto 2026 in Adobe Learning Manager. Include colonne nuove e aggiornate in Trascrizione Allievo, Formazione, Iscrizione, Lista d’attesa, Partecipazione, Controllo del contenuto e Report utente. Spiega inoltre il comportamento adattivo dei corsi, il punteggio dei gradebook, i record di apprendimento esterni, i report sui crediti dell’intelligenza artificiale generale, il tracciamento della certificazione root, la standardizzazione delle marche temporali e gli aggiornamenti degli autori delle API.
jcr-language: en_us
title: Segnalazione delle modifiche nella versione di agosto 2026 di Adobe Learning Manager
source-git-commit: 2d60f665d2e00c95edfc96360ee65fdae013c0cd
workflow-type: tm+mt
source-wordcount: '1434'
ht-degree: 2%

---


# Segnalazione delle modifiche nella versione di agosto 2026 di Adobe Learning Manager

La versione di agosto 2026 di Adobe Learning Manager introduce miglioramenti nella creazione di report per corsi adattivi, libri di testo, apprendimento esterno, utilizzo dei crediti di intelligenza artificiale generale e altro ancora. Questo articolo riepiloga le nuove colonne, i report e le modifiche comportamentali disponibili per gli amministratori in questa versione.

## Cosa è cambiato

Gli aggiornamenti dei report si estendono su otto aree funzionali: comportamento del corso adattivo, lista d’attesa adattiva, punteggio dei gradebook, apprendimento esterno, esportazioni incrementali degli utenti, utilizzo dei crediti dell’intelligenza artificiale, tracciamento della certificazione root e allineamento della marca temporale del webhook. Le modifiche interessano in modo significativo i seguenti report:

- Trascrizione Allievo (LT)
- Report dei corsi di formazione
- Report di iscrizione
- Report lista d’attesa
- Report di audit del contenuto

La maggior parte degli aggiornamenti introduce nuove colonne. Alcuni hanno introdotto nuovi tipi di report. Alcuni hanno modificato il modo in cui i dati esistenti vengono modellati o formattati.

## Modifiche ai report dei corsi adattativi

### Report dei corsi di formazione

Tre nuove colonne del report del corso di formazione supportano il comportamento adattivo del corso.

| **Colonna** | **Descrizione** | **Valori supportati** |
|--------------------------|----------------------------------------------------------|------------------------------------------------------------------------|
| Oggetto di apprendimento adattivo | Identifica se un corso è adattivo | true (adattivo), false (non adattivo) |
| Gruppi di utenti visibilità | Elenca i gruppi di utenti che possono visualizzare ogni modulo | Uno o più nomi di gruppi di utenti (ad esempio, Tutti gli Allievi, UG-Australia) |
| Obbligatorio | Indica se un modulo è obbligatorio per un gruppo di utenti | Nomi dei gruppi di utenti per i quali il modulo è obbligatorio; vuoto = facoltativo |

È possibile combinare **gruppi di utenti di visibilità** e **obbligatori** per interpretare le regole di completamento adattive direttamente nel report. Ad esempio, un modulo potrebbe essere visibile a **Tutti gli Allievi** ma obbligatorio solo per il **gruppo Amministratore**.

### Trascrizione Allievo

Una nuova colonna **Completamenti precedenti** acquisisce i dati cronologici di completamento quando la logica adattiva attiva il completamento successivo.

| **Campo secondario** | **Descrizione** |
|-----------------------|-----------------------------------------|
| completedRefreshDate | Data e ora di reimpostazione del completamento |
| completedDate | Timestamp completamento precedente |
| progressAtRefresh | Avanzamento dell’Allievo prima del ripristino |
| gradeAtRefresh | Punteggio dell’Allievo al momento del ripristino |

La Trascrizione Allievo ora supporta più cicli di completamento. Quando si verifica un evento di completamento, ad esempio a causa di aggiornamenti del corso o di nuovi moduli obbligatori, il completamento precedente viene spostato nella colonna **Completamenti precedenti**. Il completamento corrente rimane nei campi trascrizione standard.

### Report di iscrizione

Una nuova colonna **In lista d’attesa** indica se un Allievo è in lista d’attesa in uno dei moduli di un corso.

| **Valore** | **Significato** |
|-----------|---------------------------------------------------------|
| vero | L’Allievo è in lista d’attesa in uno o più moduli |
| falso | L’Allievo ha confermato l’iscrizione a tutti i moduli visibili |

### Report lista d’attesa

Due nuove colonne e un modulo di supporto avanzato per i dettagli dello stato consentono il tracciamento della lista d’attesa a livello di modulo.

| **Colonna** | **Descrizione** |
|-----------------|----------------------------------------------------------------------------------------------------------------------------------------|
| **Modulo** | Nome del modulo (aula o sessione aula virtuale) in cui l’Allievo è in lista d’attesa. Viene visualizzato dopo la colonna Stato istanza (Instance Status). |
| **ID modulo** | Identificatore del modulo in cui l’Allievo è in lista d’attesa. Viene visualizzato dopo la colonna Modulo. |
| **Incorporato In** | Il nome e l’ID del percorso di apprendimento di qualsiasi percorso che contiene questo corso. Vuoto se il corso non fa parte di un percorso di apprendimento. |

Il report Lista d’attesa è passato da un modello a livello di corso a un modello a livello di sessione del modulo. Un Allievo può ora essere iscritto ad alcuni moduli e inserito in lista d’attesa in altri. Il report supporta anche il tracciamento delle liste di attesa nei percorsi di apprendimento Flex, in cui i limiti dei posti vengono applicati a livello di modulo.

### Report di iscrizione LP

Anche il report di iscrizione al percorso di apprendimento riceve una nuova colonna **Note**. Quando un Allievo si trova in lista d’attesa in un’aula o in un’aula virtuale all’interno dei corsi che costituiscono il percorso di apprendimento, la colonna Note mostra **In lista d’attesa**. Quando tutte le sessioni sono confermate, la colonna è vuota.

### Report di partecipazione

La colonna **Stato dell’Allievo** ora distingue tra Allievi confermati e in lista d’attesa.

| **Valore** | **Significato** |
|------------|----------------------------------------|
| Confermato | L’Allievo ha un posto assegnato |
| In lista di attesa | L’Allievo è in attesa di assegnazione del posto |

## Modifiche al report Gradebook

### Trascrizione Allievo

Una nuova colonna **Spessore** rappresenta il contributo di ogni modulo con punteggio ai fini del punteggio complessivo del corso.

| **Valore** | **Descrizione** |
|----------------------------------------------|------------------------------------------------------|
| Percentuale numerica (ad esempio, 20, 30, 50) | Contributo del modulo al punteggio del corso |
| Vuoto | Il modulo non ha un punteggio (ad esempio, PDF o video) |

### Report di audit del contenuto

Due nuovi eventi acquisiscono le modifiche alla configurazione dei gradebook.

| **Evento** | **Attivato quando** | **Dati acquisiti** |
|-----------------------|-----------------------------------------------------------------|----------------------------------------------------------|
| Gradebook aggiornato | Gradebook è abilitato, disabilitato o modificato a livello di corso | Modifica dello stato del grafico; aggiornamenti della configurazione delle scarpate |
| Peso del modulo aggiornato | La ponderazione assegnata a un modulo viene modificata | Identificatore del modulo; valore di ponderazione aggiornato |

La Trascrizione Allievo riflette il peso più recente. Il report di controllo del contenuto tiene traccia delle modifiche cronologiche. Insieme, danno un quadro completo della logica di punteggio corrente e di come si è evoluta.

## Modifiche ai report sull’apprendimento esterno

### Trascrizione Allievo

Vengono aggiunte tre nuove colonne per supportare i record di apprendimento esterni.

| **Colonna** | **Descrizione** |
|------------------------|-----------------------------------------------------------------------------------------------------|
| Nome dell&#39;apprendimento esterno | Nome dell’attività di apprendimento esterna inviata dall’Allievo |
| Campi personalizzati | Una colonna per campo personalizzato configurato per l’apprendimento esterno (testo, numerico, casella di controllo o menu a discesa) |
| Commento di completamento | Note del manager inserite durante l&#39;approvazione o il rifiuto |

**Nota:** nella Trascrizione Allievo (visualizzazione autonoma Allievo), la posizione delle colonne è diversa da quella della Trascrizione Allievo amministratore:

- **Nome apprendimento esterno** viene aggiunto immediatamente dopo la colonna **Modulo** esistente.

- Il **commento di completamento** viene aggiunto immediatamente dopo la colonna **Note del revisore** esistente.

- Le colonne dei campi personalizzati (una per ogni campo personalizzato configurato) vengono aggiunte alla fine della trascrizione.

Nella Trascrizione Allievo Amministratore, tutte le nuove colonne, compresi Nome apprendimento esterno e Commento di completamento, vengono aggiunte alla fine, seguite da colonne dei campi personalizzate.

### Colonna Tipo in Trascrizione Allievo

Le voci di apprendimento esterne ora vengono visualizzate accanto agli oggetti di apprendimento esistenti (corsi, percorsi di apprendimento, certificazioni) in Administrator LT. La colonna **Tipo** include una nuova classificazione di apprendimento esterna per semplificare i filtri.

I dati di apprendimento esterni vengono trasferiti sia in Trascrizione Allievo che in Admin LT. I campi principali, ad esempio la data di completamento, lo stato e il mapping dei punteggi, vengono associati alle colonne esistenti. I campi personalizzati vengono aggiunti come colonne aggiuntive.

## Modifiche incrementali al report utente

Un nuovo modello di esportazione incrementale consente di esportare solo gli utenti i cui dati sono stati modificati entro una specifica finestra temporale, anziché generare esportazioni di dati complete ogni volta.

| **Modalità di esportazione** | **Comportamento** |
|--------------------|-----------------------------------------------------------------|
| Esportazione completa | Restituisce tutti gli utenti dell’account. |
| Esportazione incrementale | Restituisce solo gli utenti con modifiche comprese nell&#39;intervallo di date specificato |

Per utilizzare l&#39;esportazione incrementale, filtrare in base a **data di inizio** e **data di fine** per definire la finestra di modifica. I report degli utenti vengono ora generati utilizzando una pipeline della piattaforma dati e l’output viene restituito in blocchi per supportare account di grandi dimensioni.

## Report di credito Gen AI

Un nuovo dashboard dei crediti e due report forniscono agli amministratori visibilità sul consumo dei crediti Gen AI.

### Dashboard crediti

Il dashboard mostra le seguenti metriche a livello di conto.

| **Metrica** | **Descrizione** |
|-------------------|---------------------------------------------------|
| Crediti acquistati | Totale crediti accantonati per l&#39;account |
| Crediti utilizzati | Crediti utilizzati per le funzioni basate sull&#39;intelligenza artificiale |
| Crediti rimanenti | Crediti disponibili dopo il consumo |
| Utilizzo per singola funzione | Consumo di credito diviso per singola funzione di intelligenza artificiale |

### Nuovi report

| **Segnala** | **Descrizione** |
|----------------------|---------------------------------------------------------------------------------------------|
| Report di utilizzo mensile | Riepiloga il consumo di credito per mese, funzione e crediti utilizzati |
| Report audit trail | Fornisce dettagli a livello di utente: identificatore utente, nome funzione, crediti utilizzati e timestamp |

## Altri cambiamenti comportamentali

### Certificazione radice: ID del corso di formazione radice

Alla fine della **Trascrizione Allievo amministratore** e della **Trascrizione Allievo** (visualizzazione autonoma dell’Allievo) viene aggiunta una nuova colonna **ID corso di formazione radice**. Consente di acquisire l’identificatore univoco che collega tutte le ricorrenze di una certificazione a una singola entità radice. Ciò consente di associare tutte le istanze ricorrenti di una certificazione a un unico ID radice per il tracciamento e il filtraggio.

### Standardizzazione timestamp Trascrizione webhook e Allievo

Le marche temporali dei webhook sono ora allineate alla formattazione Trascrizione Allievo. Ogni campo di data e ora all’interno dell’**oggetto dati** di un payload di webhook ha ora il valore secondi impostato su 00, fornendo una granularità a livello di minuti coerente con i report Trascrizione Allievo. Questo elimina la necessità di normalizzare i formati di marca temporale durante il confronto dei dati del webhook con i dati di Trascrizione Allievo.

### Informazioni sull’Autore nella risposta API per i corsi condivisi

Quando un corso viene condiviso da un account Adobe Learning Manager a un altro tramite la condivisione del catalogo, la risposta dell’oggetto di apprendimento (LO) API ora restituisce solo i dettagli dell’autore originale dall’account di origine. In precedenza, l’amministratore dell’account di accettazione era l’autore del corso nella risposta API per il proprio account.

Questa modifica riguarda solo gli account condivisi tra pari (in ricezione). Quando si esegue una query sull’endpoint di dettaglio LO per un corso condiviso in un account di ricezione, il campo authorNames ora riflette l’autore originale dall’account di origine, non l’amministratore dell’account di ricezione.

Non è stata modificata la modalità di visualizzazione dei dettagli dell’autore quando si esegue una query sull’LO nell’account di origine.

**Nota:** se l’integrazione si basa sul campo authorNames nella risposta API LO per i corsi condivisi, verifica che i dati dell’autore aggiornati non interrompano alcuna logica a valle che presupponeva che in questo campo venisse visualizzato il nome dell’amministratore dell’account ricevente.
