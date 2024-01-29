---
description: Scopri come scaricare la trascrizione dell’Allievo basata su utenti, oggetti di apprendimento o abilità in Learning Manager.
jcr-language: en_us
title: Trascrizioni Allievi
source-git-commit: a495c86f8dff3ebc51e7700a3f3bcf7ce57d1311
workflow-type: tm+mt
source-wordcount: '917'
ht-degree: 0%

---



# Trascrizioni Allievi

Scopri come scaricare la trascrizione dell’Allievo basata su utenti, oggetti di apprendimento o abilità in Learning Manager.

Adobe Learning Manager consente ai Manager di un’organizzazione di generare le trascrizioni associate agli Allievi.

## Genera trascrizioni Allievi {#generatelearnertranscripts}

1. Per generare le trascrizioni Allievi, fai clic su **[!UICONTROL Report]** nel riquadro a sinistra nell’accesso Manager.
1. Fai clic **[!UICONTROL I miei report]** sulla pagina.
1. Fai clic **[!UICONTROL Trascrizioni Allievi]** link.

   ![](assets/learner-transcripts.png)

   *Creazione di report per le trascrizioni Allievi*

1. Viene visualizzata la finestra di dialogo Trascrizioni Allievi. Scegli l’intervallo di date per il quale desideri che venga generata la trascrizione.

   >[!NOTE]
   >
   >Per impostazione predefinita, la data di inizio corrisponde alla data di registrazione dell’Allievo e la data di fine è sempre la data corrente. È possibile modificare solo la data di inizio dal momento in cui sono necessari i dati.

1. Scegli i nomi degli Allievi dal campo Seleziona Allievi e fai clic su **[!UICONTROL Genera]**.

Puoi scegliere uno o più Allievi. Per aggiungere più Allievi, fai clic su Aggiungi altri Allievi.

Le trascrizioni vengono generate e scaricate nel computer come file .xls. Ogni file .xls excel ha sette fogli, i dettagli dei quali sono menzionati di seguito:

## Scarica la Trascrizione Allievo in base al fuso orario {#lt-timezone}

Come un Amministratore, anche un Manager può scegliere le colonne da esportare. Inoltre, un Manager può scaricare la Trascrizione Allievo in base al fuso orario selezionato nelle impostazioni del profilo.

Se il Manager abilita questa opzione, il fuso orario viene selezionato da quello impostato nella pagina delle impostazioni del profilo, come illustrato di seguito.

>[!NOTE]
>
>Per un nuovo Manager, la casella di controllo Fuso orario è disabilitata.

![](assets/image030.png)

*Scarica le trascrizioni Allievi per un fuso orario*

## Contenuto del file Trascrizione Allievo {#learnertranscriptfilecontent}

Un tipico file di trascrizione degli Allievi è costituito da sei fogli Excel in un singolo file. I fogli di trascrizione Allievo forniscono un’analisi complessiva dei dati, tra cui il numero di Allievi coinvolti per corso, le loro abilità, la percentuale di competizione in base al corso o all’Allievo e un dashboard di conformità. Di seguito sono riportati i dashboard disponibili nelle trascrizioni Allievi:

**Trascrizione Allievo**

Nel foglio Excel della trascrizione dell’Allievo, insieme ai dettagli del profilo sull’Allievo, vengono forniti dettagli di consumo per l’oggetto di apprendimento quali data di iscrizione, data di inizio, livello conseguito, punteggio del quiz ottenuto e così via. Se i corsi fanno parte di un programma di apprendimento, vengono elencati separatamente oltre ai dettagli sulla fruizione dei singoli corsi.

**1 - Dashboard di attività di apprendimento**

In questa dashboard specifica dell’LO, puoi visualizzare il numero di Allievi per ogni corso, programma di apprendimento o certificazione. È possibile visualizzare il foglio di avanzamento per gli Allievi per un determinato oggetto di apprendimento. Questo foglio mostra dati quali il numero di allievi che hanno completato il corso o il programma di apprendimento, gli allievi in corso e le date di scadenza degli allievi.

L’avanzamento degli utenti per il corso specifico viene calcolato in base ai campi di input in cui si specificano la data di scadenza e le soglie di percentuale di avanzamento. Ad esempio, se specifichi 7 giorni e 70% come valori nel campo di input, viene visualizzato l’avanzamento del corso per i corsi con scadenza tra 7 giorni e per quelli con avanzamento superiore al 70%. È inoltre possibile modificare il periodo di tempo in questo foglio, in cui i dati modificati vengono visualizzati automaticamente in questo dashboard.

**2 - Dashboard di attività di apprendimento**

Questo dashboard di apprendimento mostrerà i dati per un utente specifico. Da questa dashboard, puoi visualizzare i corsi, i programmi di apprendimento o le certificazioni a cui si è iscritto un determinato utente. La tabella mostra anche i dati sugli oggetti di apprendimento completati dall’utente, sugli oggetti di apprendimento in corso e sulle date di scadenza imminenti.

L’avanzamento di ogni corso viene calcolato in base agli input specificati. ovvero la data di scadenza e i valori percentuali di avanzamento. Ad esempio, se specifichi 7 giorni e 70% come valori nel campo di input, vengono visualizzati l’avanzamento dell’utente per i diversi corsi con scadenza tra 7 giorni e per i corsi con avanzamento superiore al 70%.

**Abilità**

Nel foglio delle abilità, vengono forniti il nome dell’abilità, il livello di abilità, i crediti richiesti, i crediti acquisiti, la percentuale di completamento e altri dettagli del profilo. Di seguito è fornita un’istantanea di esempio del foglio Excel delle abilità come riferimento.

**Dashboard delle abilità**

In questo dashboard, puoi vedere se la tua organizzazione è attrezzata per varie abilità. Per un’abilità specifica puoi controllare il numero di utenti di un’organizzazione che dovrebbero possedere questa abilità rispetto al numero di utenti che ne possiedono effettivamente una. Questo dashboard specifica anche gli utenti che potrebbero dover aggiornare le proprie abilità. Questo valore viene calcolato in base all&#39;input immesso nel campo Input. Ad esempio, se immetti 50 giorni come input, il dashboard fornisce dati sugli utenti che potrebbero dover aggiornare le proprie abilità dopo 50 giorni.

Questo dashboard delle abilità è più specifico dell’utente. Puoi filtrare uno o più utenti specifici e visualizzarne il livello di abilità come dashboard. Questo foglio consente ai manager e agli amministratori di tenere traccia delle competenze di ogni allievo rispetto a quelle previste. Il dashboard Abilità mette inoltre in luce gli Allievi che devono aggiornare le proprie abilità. L’elenco di aggiornamento degli Allievi viene calcolato in base al numero di giorni immessi nel campo di input.

**Dashboard di conformità**

Il dashboard di conformità è composto da due parti: report di conformità per utente e report di conformità per formazione. Per il report basato sull’utente, è possibile utilizzare il dashboard di conformità per tenere traccia degli utenti con date di scadenza imminenti per importanti iniziative di conformità. Per il report basato sulla formazione, puoi filtrare in base al programma di apprendimento o alla certificazione.

Per entrambi i rapporti di conformità, filtrare in base alla data di scadenza per visualizzare i dati appropriati.
