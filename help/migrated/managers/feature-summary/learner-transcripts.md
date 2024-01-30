---
description: Scopri come scaricare la trascrizione dell’Allievo basata su utenti, oggetti di apprendimento o abilità in Learning Manager.
jcr-language: en_us
title: Trascrizioni Allievi
source-git-commit: a495c86f8dff3ebc51e7700a3f3bcf7ce57d1311
workflow-type: tm+mt
source-wordcount: '917'
ht-degree: 85%

---



# Trascrizioni Allievi

Scopri come scaricare la trascrizione dell’Allievo basata su utenti, oggetti di apprendimento o abilità in Learning Manager.

Adobe Learning Manager consente ai Manager di un’organizzazione di generare le trascrizioni associate agli Allievi.

## Generazione delle trascrizioni dell’Allievo {#generatelearnertranscripts}

1. Per generare le trascrizioni Allievi, fai clic su **[!UICONTROL Report]** nel riquadro a sinistra nell’accesso Manager.
1. Fai clic **[!UICONTROL I miei report]** sulla pagina.
1. Fai clic **[!UICONTROL Trascrizioni Allievi]** link.

   ![](assets/learner-transcripts.png)

   *Creazione di report per le trascrizioni Allievi*

1. Viene visualizzata una finestra di dialogo relativa alle trascrizioni Allievo. Scegli l’intervallo di date per il quale generare la trascrizione.

   >[!NOTE]
   >
   >Per impostazione predefinita, la data di inizio corrisponde alla data di registrazione dell’Allievo e la data di fine è sempre la data corrente. Puoi modificare solo la data di inizio da quando hai bisogno dei dati.

1. Scegli i nomi degli Allievi dal campo Seleziona Allievi e fai clic su **[!UICONTROL Genera]**.

Puoi scegliere un singolo Allievo o gruppi di Allievi. Per aggiungere più di un Allievo, fai clic su Aggiungi altri Allievi.

Le trascrizioni sono generate e scaricate nel computer come file .xls. Ogni file .xls excel ha sette fogli, i dettagli dei quali sono menzionati di seguito:

## Download della trascrizione degli Allievi in base al fuso orario {#lt-timezone}

Allo stesso modo di un Amministratore, anche un Manager può scegliere le colonne da esportare. Inoltre, un Manager può scaricare la Trascrizione Allievo in base al fuso orario selezionato nelle impostazioni del profilo.

Se il Manager abilita questa opzione, il fuso orario viene selezionato da quello impostato nella pagina delle impostazioni del profilo, come illustrato di seguito.

>[!NOTE]
>
>Per un nuovo Manager, la casella di controllo Fuso orario è disabilitata.

![](assets/image030.png)

*Scarica le trascrizioni Allievi per un fuso orario*

## Contenuto del file di trascrizione Allievo {#learnertranscriptfilecontent}

Un file tipico di trascrizione Allievo consiste in sei fogli in un singolo file. I fogli di trascrizione Allievo offrono una panoramica completa sui dati, compreso il numero di Allievi coinvolti per corso, le loro abilità, la percentuale di completamento basata su corso o Allievo e un dashboard di conformità. Di seguito sono riportati i dashboard disponibili nelle trascrizioni Allievo:

**Trascrizione Allievo**

Nel file Excel di trascrizione Allievo, insieme ai dettagli di profilo dell’Allievo, vengono forniti dettagli di consumo relativi all’oggetto di apprendimento, come data di iscrizione, di avvio, valutazione raggiunta, punteggio quiz ottenuto e così via. Se i corsi fanno parte di un programma di apprendimento, sono elencati separatamente dai singoli dettagli di completamento corso.

**1 - Dashboard di attività di apprendimento**

In questo dashboard specifico per LO, puoi visualizzare il numero di Allievi per ogni corso, programma di apprendimento o certificazione. Puoi visualizzare il foglio di avanzamento per gli Allievi per uno specifico oggetto di apprendimento. In questo foglio sono visualizzati i dati come il numero di Allievi che hanno completato il corso o il programma di apprendimento, gli Allievi in corso e le date di scadenza per gli Allievi.

L’avanzamento degli utenti per il corso specifico è calcolato in base ai campi di input dove viene specificata la data di scadenza e le soglie di percentuale dell’avanzamento. Ad esempio, se specifichi 7 giorni e 70% come valori nel campo di input, viene visualizzato l’avanzamento per i corsi con scadenza tra 7 giorni e per i corsi con oltre il 70% di avanzamento. Puoi inoltre modificare il periodo di tempo in questo foglio, dove la data modificata viene visualizzata automaticamente in questo dashboard.

**2 - Dashboard di attività di apprendimento**

Questo dashboard di apprendimento visualizzerà i dati per un utente specifico. Da questo dashboard, puoi visualizzare i corsi, i programmi di apprendimento o la certificazione a cui è iscritto un particolare utente. La tabella mostra inoltre dati degli oggetti di apprendimento completati dall’utente, gli oggetti di apprendimento in corso e le prossime date di scadenza per l’utente.

L’avanzamento degli utenti per ciascun corso è calcolato in base agli input specificati. Ovvero, i valori di percentuale avanzamento e la data di scadenza. Ad esempio, se specifichi 7 giorni e 70% come valori nel campo di input, viene visualizzato l’avanzamento per i corsi con scadenza tra 7 giorni e per i corsi con oltre il 70% di avanzamento.

**Abilità**

Nel foglio delle abilità, sono forniti il nome dell’abilità, il livello dell’abilità, i crediti necessari, quelli ottenuti, la percentuale di completamento e altri dettagli di profilo. Come riferimento, viene di seguito fornita un’istantanea del foglio Excel delle abilità.

**Dashboard delle abilità**

In questo dashboard, puoi verificare se l’organizzazione possiede determinate abilità. Per una specifica abilità puoi verificare il numero di utenti in un’organizzazione che dovrebbe possedere questa abilità rispetto al numero che effettivamente la possiede. Questo dashboard indica inoltre gli utenti che potrebbero dover rinfrescare le loro abilità. Questo valore viene calcolato in base all’input immesso nel campo. Ad esempio, se immetti 50 giorni come input, il dashboard fornisce dati sugli utenti che potrebbero dover rinfrescare le abilità dopo 50 giorni.

Questo dashboard delle abilità è specifico per l’utente. Puoi filtrare un elenco specifico o diversi utenti e visualizzare il relativo livello di abilità come dashboard. Questo foglio può aiutare i Manager e gli Amministratori a valutare le abilità ottenute da ogni Allievo rispetto al livello di raggiungimento previsto. Il dashboard delle abilità indica inoltre gli Allievi che devono rinfrescare le abilità. L’elenco di tali Allievi è calcolato in base al numero di giorni immessi nel campo di input.

**Dashboard di conformità**

Il dashboard di conformità è composto da due parti: report di compatibilità per utente e report di compatibilità per formazione. Per il report basato sull’utente, puoi utilizzare il dashboard di conformità per valutare gli utenti con le date di scadenza programmate per importanti iniziative di conformità. Per il report basato sulla formazione, puoi applicare il filtro per certificazione o programma di apprendimento.

Per entrambi i report di conformità, applica il filtro in base alla data di scadenza per visualizzare i dati appropriati.
