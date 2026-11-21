---
description: Scopri come attivare la registrazione multipla per i corsi adattivi, gestire i limiti di posti e le liste di attesa e comprendere le regole di iscrizione nei percorsi di apprendimento
jcr-language: en_us
title: Iscrizione multipla per corsi adattivi
exl-id: e2a52964-fe9d-4a71-a020-68201f75f9f0
hide: true
source-git-commit: e056f1a655efd7c999856e2b54b28e676e67afc6
workflow-type: tm+mt
source-wordcount: '1231'
ht-degree: 0%
---

# Iscrizione multipla per corsi adattivi

## Panoramica

L’iscrizione multipla consente a un Allievo di iscriversi contemporaneamente a più di un’istanza dello stesso corso. In Adobe Learning Manager, ora puoi attivare la registrazione multipla per i corsi adattivi.

## Informazioni sull’iscrizione multipla in un corso adattivo

Un corso adattivo mostra a ogni Allievo solo i moduli che corrispondono ai suoi gruppi di utenti. Quando l’iscrizione multipla è attivata, un Allievo può seguire diverse istanze di quel corso, ad esempio sessioni in mesi diversi.

I corsi adattivi tengono traccia delle liste di attesa a livello di modulo, non a livello di istanza. Un Allievo può essere in corso su alcuni moduli ed essere in lista d’attesa su altri allo stesso tempo. Ad esempio, un corso ha due istanze e ciascuna istanza ha un limite di partecipanti pari a una. Il primo Allievo si iscrive in entrambe le istanze e accetta entrambe le postazioni. Un secondo Allievo che si iscrive in entrambe le istanze viene inserito nella lista d’attesa in entrambe.

## Abilitare l’iscrizione multipla per un corso adattivo

1. Accedi a Adobe Learning Manager come autore.
2. Nella barra di navigazione a sinistra, seleziona **Corsi**. Apri un corso adattivo o creane uno.
3. Aggiungi i moduli. Per ogni modulo di contenuto, selezionare **Aggiungi regole** per impostare i gruppi di utenti che possono visualizzarlo e i gruppi di utenti per i quali è obbligatorio.
4. Seleziona **Salva**. L’opzione di iscrizione multipla diventa disponibile.
5. Attiva l&#39;interruttore **Registrazione multipla**.
6. Create le varianti necessarie. Per le sessioni in aula e in aula virtuale, imposta i limiti dei posti.
7. Seleziona **Publish**.

Gli Allievi ora possono iscriversi a più di un’istanza del corso.

## Comportamento Limite di posti e lista d’attesa

I corsi adattivi applicano i limiti di partecipanti per ogni classe o sessione aula virtuale. Un Allievo si iscrive immediatamente ed è in lista d’attesa solo per le sessioni piene. L’Allievo può avviare subito tutti gli altri moduli.

| Condizione | Risultato |
|------------------------------------------------------------------------------|--------------------------------------------------------------------------------------------------------------|
| Tutte le sessioni visibili hanno postazioni disponibili | L’Allievo è iscritto con accesso completo a tutti i moduli. |
| Una o più sessioni visibili sono piene | L’Allievo è iscritto e inserito in lista d’attesa solo per le sessioni complete. |
| Aggiungi una sessione obbligatoria senza postazioni a un corso a cui hanno partecipato gli Allievi | L’Allievo è in lista d’attesa per la nuova sessione. Lo stato di avanzamento e l’accesso esistenti non sono interessati. |
| Una modifica al gruppo di utenti rimuove una sessione dai moduli visibili dell’Allievo. | Adobe Learning Manager libera immediatamente il sedile. |
| Un Allievo passa a un’altra istanza | I moduli completati rimangono completati. Le postazioni vengono utilizzate solo per i moduli visibili che l’Allievo non ha completato. |

## Regole di iscrizione e completamento per i percorsi di apprendimento adattativi

Gli Autori ora possono aggiungere corsi adattativi ai percorsi di apprendimento adattativi in Adobe Learning Manager. L’iscrizione, le liste di attesa e il completamento seguono le regole che combinano le impostazioni della sezione e le impostazioni del corso configurate dagli autori.

### Valutazione di un Allievo da parte di un percorso di apprendimento adattivo

Adobe Learning Manager valuta la visibilità a livello di sezione e di corso. La regola di sezione determina se un Allievo vede una sezione e i relativi corsi adattivi. Le regole del modulo all’interno di ciascun corso adattivo decidono quindi se l’Allievo è iscritto al corso.

Gli Allievi verranno iscritti automaticamente ogni volta che si verificherà un cambiamento dell’UG in relazione al corso adattivo all’interno dell’LP adattivo. Allo stesso modo, gli Allievi riceveranno notifiche di iscrizione automatica e e-mail.

### Regole di valutazione dell&#39;iscrizione

Quando iscrivi un Allievo a un percorso di apprendimento adattivo, Adobe Learning Manager controlla il percorso nel seguente ordine:

| Ordine | Verifica | Risultato |
|-----------|----------------------------------|------------------------------------------------------------------------------------------------------------------------------------------------------------|
| 1 | Visibilità della sezione | Adobe Learning Manager controlla l’iscrizione di un corso solo se la relativa sezione è visibile all’Allievo. |
| 2 | Idoneità al corso | Se il corso non dispone di un modulo obbligatorio per l’Allievo, quest’ultimo non viene iscritto al corso. Il corso non conta per il completamento del percorso di apprendimento. |
| 3 | Sezioni senza corso idoneo | Se una sezione contiene solo corsi adattivi e l’Allievo non è idoneo per nessuno di essi, Adobe Learning Manager salta la sezione. |
| 4 | Iscrizione al percorso di apprendimento | Se nessuna delle sezioni obbligatorie si applica all’Allievo, quest’ultimo non viene iscritto al percorso di apprendimento. |

Se l’Allievo è già iscritto a un’istanza del corso che appartiene all’istanza del percorso di apprendimento, Adobe Learning Manager utilizza tale iscrizione.

Dopo l’iscrizione, si applicano le seguenti regole:

* Un Allievo che ha saltato un corso inizialmente per visibilità può essere iscritto automaticamente se il corso adattivo è visibile a causa della visibilità o delle modifiche alle regole obbligatorie in un secondo momento.
* Una modifica del gruppo di utenti o di un corso può annullare l’iscrizione di un Allievo a un corso adattivo. Se nel percorso non è presente alcun contenuto obbligatorio, l’iscrizione dell’Allievo viene annullata.
* Per le modifiche di sezione, l’Allievo non riceverà alcuna notifica o e-mail di iscrizione automatica. Semplicemente al momento del ricaricamento della pagina, l’Allievo può visualizzare le modifiche.

### Comportamento della lista d’attesa nei percorsi di apprendimento adattativi

La lista d&#39;attesa funziona a livello di sessione, non a livello di istanza. Ciò vale anche per i corsi adattativi nei percorsi di apprendimento.

| Scenario | Comportamento |
|----------------------------------------------------------------------------------|----------------------------------------------------------------------------------------------------------------------------------|
| Nessun corso adattivo nel percorso dispone di un modulo aula o aula virtuale | Non si applica nessuna lista d&#39;attesa. |
| Un corso adattivo dispone di un modulo aula o aula virtuale e non è selezionata alcuna istanza | Per impostazione predefinita, il corso è **Nessuna istanza**. L’Allievo può iscriversi a qualsiasi istanza ed è in lista d’attesa solo per le sessioni piene. |
| Un&#39;istanza viene selezionata prima dell&#39;iscrizione | L’Allievo è iscritto a quell’istanza ed è in lista d’attesa solo per le sessioni piene. |

Per gestire gli Allievi in lista d’attesa, apri il corso adattivo e seleziona la scheda **Allievi** > **Lista d’attesa**. Per un corso adattivo in un percorso di apprendimento flessibile e un percorso di apprendimento adattivo, gli Allievi in lista d’attesa vengono visualizzati solo nella scheda **Lista d’attesa** del corso e non nel percorso di apprendimento.

### Aggiornamento del comportamento di completamento e rollback

Adobe Learning Manager non revoca automaticamente il completamento quando vengono modificati i gruppi di utenti o le regole. Un Allievo completato rimane completato fino al completamento dell’aggiornamento.

* Esegui **Aggiorna completamento** sul percorso di apprendimento. Non puoi aggiornare un corso adattivo da solo per gli Allievi che lo seguono.

* Ogni corso adattivo viene ricalcolato per primo in base ai moduli obbligatori correnti dell’Allievo. Il percorso di apprendimento viene quindi ricalcolato in base alle sezioni obbligatorie correnti e agli stati del corso aggiornato.

* Se il corso o il percorso non è più completato, lo stato dell’Allievo diventa in corso. Il completamento originale rimane nella Trascrizione Allievo come record storico.

* Un rollback di completamento trova i corsi adattivi i cui moduli sono stati modificati a causa di una modifica del gruppo di utenti o di una ripubblicazione. Ricalcola i corsi e quindi il percorso di apprendimento. Lo stato del processo mostra **Operazione completata** al termine del rollback.

La lista d’attesa viene monitorata a livello di modulo. Un Allievo può essere messo in lista d’attesa in una sessione completa in più di un’istanza. Ad esempio, un corso ha due istanze con un limite di partecipanti pari a una per ciascuna. Il primo Allievo si iscrive in entrambe le istanze e accetta entrambe le postazioni. Un secondo Allievo che si iscrive a entrambe le istanze viene visualizzato nella scheda **Lista d’attesa** di ogni istanza.

### Assegnazione di posti agli Allievi in lista d’attesa

Quando un Allievo annulla l’iscrizione, un Autore aumenta il limite di partecipanti o un Allievo cambia istanza, Adobe Learning Manager cancella la lista d’attesa secondo l’ordine della data di iscrizione. È inoltre possibile allocare le postazioni manualmente.

1. Aprire il corso adattivo.
2. Seleziona la scheda **Allievi** > **Lista d’attesa**.
3. Seleziona la casella di controllo accanto a ciascun Allievo per il quale desideri assegnare postazioni.
4. Seleziona **Assegna Posti**.

Adobe Learning Manager cancella tutti gli Allievi selezionati dalla lista d’attesa in tutte le sessioni in lista d’attesa contemporaneamente, non solo quella che stai visualizzando. Il sistema presuppone che tu abbia organizzato la postazione per l’Allievo.
