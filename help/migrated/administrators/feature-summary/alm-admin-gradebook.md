---
description: Tutte le informazioni necessarie per abilitare il Gradebook e renderlo visibile ad autori e allievi
jcr-language: en_us
title: Gradebook per l'amministratore
source-git-commit: c6ad5527fa5156d1a681fa0f21fb259ac3ebf782
workflow-type: tm+mt
source-wordcount: '1128'
ht-degree: 0%

---


# Abilita visibilità Gradebook per l&#39;account

## Panoramica

Prima che gli Autori possano mostrare il libro di schemi agli Allievi in un corso, un Amministratore deve abilitare l’impostazione Visibilità libro di schemi a livello di account. Questa impostazione funge da interruttore principale: quando è disattivata, gli allievi non possono visualizzare il Gradebook in alcun corso, indipendentemente dalla configurazione dei singoli corsi.

## Controlli di questa impostazione

L’impostazione **Visibilità gradebook** in **Impostazioni** > **Generali** determina se agli autori è consentito esporre il gradebook agli allievi a livello di corso.

| Stato impostazione | Effetto |
| --- | --- |
| Abilitato | Gli autori possono controllare la visibilità dei gradebook per corso utilizzando l’opzione **Mostra gradebook agli allievi** nell’editor del corso. Gli Allievi visualizzano la scheda **Gradebook** nei corsi in cui è stata abilitata dall’Autore. |
| Disattivata | Gli allievi non possono visualizzare il Gradebook in alcun corso. Se è disattivata, la configurazione del corso non avrà l’impostazione per mostrare il libro paga agli Allievi. |


Ciò significa che l’impostazione a livello di account e l’impostazione a livello di corso funzionano insieme. Entrambi devono essere abilitati affinché un Allievo possa visualizzare il libro di testo.

## Attivare la visibilità dei gradebook

1. Accedi a Adobe Learning Manager come amministratore.
2. Nella barra di navigazione a sinistra, seleziona **Impostazioni**.
3. Selezionare **Generale**.
4. Scorrete fino alla sezione **Visibilità gradebook**.
5. Seleziona la casella di controllo **Abilita visualizzazione Gradebook per gli Allievi**.

   ![](assets/gradebook-admin-1.png)

Gli Autori possono ora configurare la visibilità dei gradebook per corso.

## Impatto sui flussi di lavoro degli autori

Quando questa impostazione a livello di account è abilitata, nell’editor del corso diventa disponibile l’interruttore **Mostra gradebook agli Allievi**. Gli Autori utilizzano questo interruttore per decidere, in base al corso, se gli Allievi possono visualizzare la scheda **Gradebook**.

Quando questa impostazione a livello di account è disattivata:

* L’interruttore **Mostra gradebook agli allievi** nell’editor del corso potrebbe ancora essere visualizzato, ma qualsiasi configurazione a livello di corso viene ignorata. Gli Allievi non visualizzeranno il libro dei voti.
* I punteggi dei gradebook e i calcoli ponderati continuano a essere eseguiti in background per scopi di reporting da parte dell&#39;amministratore.
* Gli Amministratori e gli Amministratori personalizzati possono ancora scaricare le Trascrizioni Allievi con i dati dei gradebook.

>[!NOTE]
>
>Se si disabilita questa impostazione a livello di account, non viene eliminata alcuna configurazione o punteggio del registro di livello. Se la riattivi, vengono ripristinate immediatamente tutte le impostazioni della cartella di lavoro a livello di corso configurate in precedenza.

## Modalità di interazione delle due impostazioni

| Impostazione a livello di account | Impostazione a livello di corso | Cosa vede l’Allievo |
| --- | --- | --- |
| Abilitato | Mostra gradebook agli Allievi: **In data** | Scheda **Gradebook** visibile nel lettore del corso |
| Abilitato | Mostrare la cartella di lavoro agli Allievi: **Disattivato** | Nessuna scheda Gradebook; solo i punteggi calcolati internamente |

## Visualizzare e creare report sui punteggi dei gradebook

Gli Amministratori di Adobe Learning Manager possono visualizzare i punteggi ponderati dei gradienti per tutti gli Allievi iscritti a un corso, analizzare le prestazioni dei singoli Allievi per modulo, scaricare una Trascrizione Allievo filtrata e tenere traccia delle modifiche alla configurazione dei gradienti nel report di prova di verifica del contenuto.

## Visualizzare il blocco appunti per un corso

Quando il blocco appunti è abilitato per un corso, quando apri il corso viene visualizzata una nuova sezione **Feedback L2 - Gradebook** nel riquadro di navigazione a sinistra in **Report**.

* Accedi a Adobe Learning Manager come amministratore.
* Nella barra di navigazione a sinistra, seleziona **Corsi** e apri il corso che desideri rivedere.
* Nel riquadro di navigazione del corso in **Report**, seleziona **Feedback L2 - Gradebook**. Viene aperta la pagina **Active Feedback Gradebook**.

  ![](assets/image_0013.png)

Viene visualizzato quanto segue:

1. Criteri di superamento del corso (moduli minimi richiesti e punteggio minimo aggregato)
2. Una riga di filtro per visualizzare gli Allievi per livello: **Superato**, **Non riuscito** o **In attesa di completamento**
3. La formula del punteggio aggregato: Punteggio aggregato = (Punteggio ottenuto ÷ Punteggio massimo) × Ponderazione, per ogni modulo
4. Un elenco di Allievi che mostra il **punteggio aggregato** di ciascun Allievo e il relativo punteggio per ogni modulo con punteggio
5. Menu a discesa di un’istanza per passare da un’istanza all’altra quando un corso ha più istanze

Gli Allievi che non hanno ancora tentato alcun modulo con punteggio mostrano trattini nelle colonne di punteggio. I moduli che non supportano punteggi, PDF, video, audio e simili non vengono visualizzati come colonne di punteggio.

## Visualizzare i punteggi di un singolo Allievo

In **Active Feedback Gradebook**, seleziona il nome di un Allievo.

![](assets/image_0014.png)

La vista del singolo Allievo mostra:

1. Nome, e-mail e stato dell’Allievo (**Completamento in sospeso**, **Superato** o **Non riuscito**)
2. Punteggio aggregato e numero di moduli obbligatori completati dall’Allievo
3. Tabella dei moduli che mostra: nome del modulo, tipo, se richiesto, stato, peso, punteggio ottenuto e contributo all&#39;aggregazione

La tabella dei moduli include tutti i moduli con punteggio e quelli senza punteggio. I moduli con punteggi mostrano il loro punteggio e il loro contributo. I moduli senza punteggio mostrano trattini nelle colonne Punteggio e Contribuzione.

## Moduli punteggio

Il comportamento relativo al punteggio per amministratori e istruttori rimane invariato rispetto al flusso di lavoro corrente:

* **I moduli dei quiz SCORM, AICC, xAPI e nativi** vengono conteggiati automaticamente quando il contenuto sottostante riporta un punteggio.
* **Le sessioni in aula, le sessioni in aula virtuale e i moduli di attività** sono valutati da istruttori o amministratori nella pagina **Presenze e punteggi**.

## Scarica la Trascrizione Allievo per un corso

Puoi scaricare una Trascrizione Allievo filtrata per questo corso direttamente dalla pagina Gradebook in uno dei due modi:

* Nell’**Active Feedback Gradebook**, seleziona **Scarica trascrizione Allievo** nell’angolo superiore destro della pagina.
* Nella home page dell&#39;amministratore, seleziona **Report**, quindi seleziona **Report personalizzati**. Seleziona **Trascrizioni Allievi** dall’elenco dei report disponibili.

Per ulteriori informazioni, consulta Segnalazione delle modifiche nella versione.

## Eventi di prova di verifica del contenuto

L’audit trail del contenuto acquisisce due eventi di configurazione specifici del grafico:

| **Evento** | **Quando viene visualizzato** |
|-----------|---------------------|
| **Gradebook aggiornato** | Quando un Autore abilita o disabilita un libro di testo per un corso |
| **Peso del modulo aggiornato** | Quando un Autore modifica la percentuale di ponderazione per un modulo |

Per ulteriori informazioni, consulta Segnalazione delle modifiche nella versione.

Utilizzare queste voci per tenere traccia di chi ha modificato la configurazione e di quando dei gradebook, in particolare in ambienti in cui più autori collaborano allo stesso corso.

## Risoluzione dei problemi

**La sezione Feedback L2 - Gradebook non viene visualizzata nella navigazione del corso**

Durante la creazione del corso, l’autore del corso deve abilitare la funzione Gradebook. Conferma che l’Autore ha abilitato il libro di testo per la creazione di un corso. Se il corso è stato creato prima che fosse disponibile, non può essere aggiunto retroattivamente. È necessaria una nuova versione del corso.

**Il punteggio aggregato di un Allievo è 0 nonostante i moduli completati**

Conferma che al corso è assegnato almeno un modulo con punteggio. Se tutti i moduli completati dall’Allievo non hanno un punteggio (PDF, video, audio), non viene calcolato alcun punteggio aggregato. Inoltre, verificare che i moduli con punteggio non siano ancora in stato **Revisione in sospeso**. I moduli non valutati vengono esclusi dall’aggregato fino a quando un Istruttore non immette un punteggio.

**La colonna Peso non è presente nella Trascrizione Allievo scaricata**

Questa colonna viene visualizzata solo quando il file Gradebook è abilitato e almeno un modulo ha un valore di ponderazione salvato. Conferma che l’autore ha abilitato il file Gradebook e salvato un totale di 100% di valori di ponderazione.

**Un Allievo ha completato tutti i moduli richiesti ma mostra il completamento in sospeso**

Uno o più moduli potrebbero essere ancora in attesa di un punteggio da parte di un Istruttore o di un Amministratore (**In attesa di revisione**). Il corso non può essere completato finché tutti i moduli richiesti non hanno registrato il completamento e un punteggio. Immetti il punteggio in sospeso da **Frequenza e punteggio** per cancellare lo stato in sospeso.
