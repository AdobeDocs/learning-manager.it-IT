---
description: Scarica la trascrizione Allievo e gestisci i report utilizzando Learning Manager.
jcr-language: en_us
title: Trascrizioni Allievi
contentowner: jayakarr
source-git-commit: 0052ccb2f5a8f9617bca2c7bad91c0cd18338b66
workflow-type: tm+mt
source-wordcount: '1910'
ht-degree: 0%

---



# Trascrizioni Allievi

Scarica la trascrizione Allievo e gestisci i report utilizzando Learning Manager.

Adobe Learning Manager consente agli Amministratori di un’organizzazione di generare le trascrizioni associate agli Allievi.

## Genera trascrizioni Allievo {#generatelearnertranscripts}

1. Per generare le trascrizioni Allievi, fai clic su **[!UICONTROL Report]** nel riquadro a sinistra nell’accesso come Amministratore.

   L’Amministratore passa alla scheda Report Excel all’interno della **[!UICONTROL Report]** pagina.

1. Fai clic sul collegamento **[!UICONTROL Trascrizioni Allievi]**.

   La **[!UICONTROL Trascrizione Allievo]** viene visualizzata la pagina della cronologia con il messaggio **Non è ancora stata generata alcuna Trascrizione Allievo** oppure un elenco dei download attivati dopo l’implementazione della pagina Cronologia trascrizioni apprendimento.

   <!--[](assets/learner-transcripts.png)-->

   Viene visualizzata la finestra di dialogo Trascrizioni Allievi. Scegli l’intervallo di date per il quale desideri che venga generata la trascrizione.

   >[!NOTE]
   >
   >Per impostazione predefinita, la data di inizio corrisponde alla data di registrazione dell’Allievo e la data di fine è sempre la data corrente. È possibile modificare solo la data di inizio dal momento in cui sono necessari i dati.

1. Scegli i nomi degli Allievi dal menu **[!UICONTROL Seleziona Allievi]** e fare clic su **[!UICONTROL Genera].**
1. Puoi scegliere uno o più Allievi. Per aggiungere più Allievi, fai clic su **[!UICONTROL Aggiungi altri Allievi]**.

   ![](assets/add-learners-lt.png)

   *Aggiungi altri Allievi*

1. Per scegliere cataloghi specifici, attiva la casella di controllo. La trascrizione viene scaricata solo per i cataloghi specificati. Potete scegliere cataloghi specifici selezionando il catalogo dal menu **[!UICONTROL Seleziona cataloghi]** elenco a discesa.

   ![](assets/select-catalogs-lt.png)

1. Quando esporti le Trascrizioni Allievi, è disponibile un’opzione: **[!UICONTROL Stato iscrizione]**. Questo menu a discesa contiene le seguenti opzioni:

   * Seleziona tutto
   * Completato
   * In corso
   * Non avviato
   * Annullata iscrizione

   ![](assets/add-enrollment-status-lt.png)

   *Selezionare il catalogo*

1. Puoi anche scaricare le trascrizioni per gli Allievi eliminati da un account.

   Per scaricare le Trascrizioni Allievi degli utenti eliminati, fai clic sul pulsante **[!UICONTROL Opzioni avanzate]** e attivare la casella di controllo **[!UICONTROL Includi i dati degli Allievi eliminati]**.

   ![](assets/data-deleted-learners.png)

   *Scarica le Trascrizioni Allievi degli Allievi eliminati*

1. Puoi scegliere di scaricare le informazioni a livello di modulo nella trascrizione Allievo abilitando la proprietà &quot;**[!UICONTROL Abilita informazioni a livello di modulo]**&quot;. In questo caso, i nomi dei moduli e il tempo impiegato per ciascun modulo vengono recuperati come parte della trascrizione, se questa opzione è abilitata.
1. Puoi scegliere di scaricare i dati sulle abilità e i fogli di riepilogo abilitando l’opzione &quot;**[!UICONTROL Includi dati sulle abilità e fogli di riepilogo]**&quot;.

   Le trascrizioni vengono generate e scaricate nel computer come file .csv quando i dati sulle abilità non sono inclusi. Se la casella di controllo Dati abilità è abilitata, le trascrizioni vengono generate e scaricate nei file .xls.

## Genera trascrizione Allievo utilizzando copia-incolla

Il recupero delle trascrizioni degli Allievi diventa un processo noioso in quanto può essere ottenuto solo per un Allievo o un gruppo di utenti alla volta. In questo caso, con la funzione copia-incolla, puoi copiare l’elenco di ID e-mail degli Allievi e incollarlo contemporaneamente.

1. Accedi come **[!UICONTROL Amministratore]** oppure **[!UICONTROL Manager]**.
1. Vai a **[!UICONTROL Report]** sotto **[!UICONTROL Gestisci]**, viene caricato il **[!UICONTROL Attività utente]** pagina.
1. Fai clic **[!UICONTROL Report personalizzati]** nel riquadro a sinistra e seleziona **[!UICONTROL Trascrizioni Allievi]** dall&#39;elenco.
1. Nella **[!UICONTROL Trascrizioni Allievi]** pagina, fare clic su **[!UICONTROL Genera nuovo]** nell&#39;angolo superiore sinistro.
1. Selezionare le date preferite facendo clic su **[!UICONTROL Seleziona intervallo di date]** a discesa. Fai clic **[!UICONTROL ID e-mail]** per inserire l’elenco copiato di id e-mail univoci.

   ![](assets/cp-copy-paste-feature.png)

   *Copia e incolla ID e-mail*

1. Utilizzo **[!UICONTROL Convalida ID e-mail]** per verificare che l’id inserito sia corretto.

   ![](assets/cp-learnertran-gdpr.png)

   *Convalida gli ID e-mail*

   Se l’ID e-mail inserito non è corretto, viene evidenziato in rosso con un messaggio di convalida come sopra.

   **[!UICONTROL Genera]** Il pulsante sarà disponibile solo se tutti gli ID e-mail inseriti sono corretti.

   ![](assets/cp-copy-paste-generate.png)

   *Genera le Trascrizioni Allievi*

1. Fai clic **[!UICONTROL Genera]** per generare le Trascrizioni Allievi per tutti gli ID e-mail menzionati. Riceverai un messaggio di conferma come indicato di seguito, con la conferma della generazione del report.

   ![](assets/cp-copy-paste-gmessage.png)

   *Messaggio di conferma della generazione del report*

   La generazione delle Trascrizioni Allievi può combinare gli ID e-mail inseriti in entrambi **[!UICONTROL Utenti]** e **[!UICONTROL ID e-mail]** scheda.

## Cronologia dei download delle Trascrizioni Allievi {#ltdownload}

Nella **[!UICONTROL Trascrizione Allievo]** pagina di download, per generare un report, quando si fa clic sul pulsante **[!UICONTROL Genera nuovo]** , viene visualizzata la finestra di dialogo Trascrizioni Allievi.

![](assets/history-lt.png)

*Genera un report di tutte le Trascrizioni Allievi*

Fai clic **[!UICONTROL Opzioni avanzate]** ed espandete il pannello.

Scegli gli utenti e il catalogo a cui appartengono. Dopo aver fatto clic sul pulsante **[!UICONTROL Genera]** , viene visualizzata una finestra di dialogo che indica il tempo approssimativo necessario per scaricare il report. Per generare il report, fai clic su **[!UICONTROL Genera]**.

![](assets/download-learnertranscripts.png)

*Seleziona il pulsante Genera.*

La trascrizione viene generata in background e puoi continuare con le tue attività in Learning Manager. Una volta generata la trascrizione, puoi scaricarla dall’elenco.

In qualità di Amministratore, puoi visualizzare tutte le trascrizioni generate da chiunque nel sistema.

![](assets/download-history.png)

*Visualizzazione della cronologia dei download*

L&#39;elenco di download visualizza i seguenti attributi:

* **Allievi:** Gli Allievi/gruppi di Allievi le cui trascrizioni devono essere scaricate.
* **Dati aggiuntivi inclusi:** Dipende dai dati aggiuntivi che l’Amministratore desidera scaricare dall’opzione Avanzate nella finestra di dialogo modale Aggiungi trascrizione Allievo
* **Stato:** Scaricato, in coda o in corso.
* **Da** e **A**: durata delle trascrizioni da scaricare.
* **Filtri applicati:** Se sono stati applicati i filtri per Stato iscrizione.
* **Generato da:** ID utente dell’utente Learning Manager che ha richiesto il download.
* **Stato:** Scaricato, in coda o in corso.

Puoi annullare il download in qualsiasi momento. Se un processo viene annullato dall’Amministratore, Learning Manager invia una notifica in-app all’utente che ha attivato la trascrizione dell’Allievo.

![](assets/queued-status.png)

*Coda di download della Trascrizione Allievo*

È possibile **annulla** il download in qualsiasi momento. Se un processo viene annullato, Learning Manager invia una notifica in-app all’utente che ha annullato il processo.

## Dati degli Allievi eliminati {#dataofdeletedlearners}

È possibile includere i dati degli Allievi eliminati nell’elenco Trascrizione Allievo. Nella finestra di dialogo Trascrizioni Allievi, attiva l’opzione **[!UICONTROL Includi i dati degli Allievi eliminati]**.

Dopo aver attivato l’opzione e fatto clic su **[!UICONTROL Genera]**, le funzioni relative ai dati degli Allievi eliminati nella pagina di download delle trascrizioni degli Allievi, come illustrato di seguito:

![](assets/deleted-learnersondownloadpage.png)

*Visualizzare i dati degli Allievi eliminati*

## Personalizza colonne {#customize-columns-lt}

Un Amministratore può personalizzare le colonne esportate in un report Trascrizione Allievo. Amministratori, Amministratori personalizzati e Manager possono configurare le colonne prima di esportare il report.

Nella **[!UICONTROL Trascrizioni Allievi]** , fare clic su **[!UICONTROL Opzioni avanzate]**. Nella **[!UICONTROL Configura formato esportazione]** scegliere le colonne da esportare.

![](assets/image024.png)

*Personalizzare le colonne da esportare*

La personalizzazione è consentita solo quando un utente scarica la Trascrizione Allievo in formato .CSV. Quando viene scaricato in formato .XLSX, la selezione delle preferenze delle colonne non verrà rispettata e tutte le colonne predefinite verranno esportate.

## Contenuto del file di trascrizione Allievo {#learnertranscriptfilecontent}

Un tipico file di trascrizione degli Allievi è costituito da sei fogli Excel in un singolo file. I fogli di trascrizione Allievo forniscono un’analisi complessiva dei dati, tra cui il numero di Allievi coinvolti per corso, le loro abilità, la percentuale di completamento in base al corso o all’Allievo e un dashboard di conformità. Di seguito sono riportati i dashboard disponibili nelle trascrizioni Allievi:

**Trascrizione Allievo**

Nel foglio Excel della trascrizione dell’Allievo, insieme ai dettagli del profilo sull’Allievo, viene fornito un dettaglio di utilizzo in base all’oggetto di apprendimento come data di iscrizione, data di inizio, livello raggiunto, punteggio del quiz ottenuto. Se i corsi fanno parte di un programma di apprendimento, vengono elencati separatamente oltre ai dettagli sulla fruizione dei singoli corsi.

**1 - Dashboard di attività di apprendimento**

In questa dashboard specifica dell’LO, puoi visualizzare il numero di Allievi per ogni corso, programma di apprendimento o certificazione. È possibile visualizzare il foglio di avanzamento per gli Allievi per un determinato oggetto di apprendimento. Questo foglio mostra dati quali il numero di allievi che hanno completato il corso o il programma di apprendimento, gli allievi in corso e le date di scadenza degli allievi.

L’avanzamento degli utenti per il corso specifico viene calcolato in base ai campi di input in cui si specificano la data di scadenza e le soglie di percentuale di avanzamento. Ad esempio, se specifichi 7 giorni e 70% come valori nel campo di input, viene visualizzato l’avanzamento del corso per i corsi con scadenza tra 7 giorni e per quelli con avanzamento superiore al 70%. È inoltre possibile modificare il periodo di tempo in questo foglio, in cui i dati modificati vengono visualizzati automaticamente in questo dashboard.

**2 - Dashboard di attività di apprendimento**

Questa dashboard di apprendimento visualizza i dati per un utente specifico. Da questa dashboard, puoi visualizzare i corsi, i programmi di apprendimento o le certificazioni a cui si è iscritto un determinato utente. La tabella mostra anche i dati sugli oggetti di apprendimento completati dall’utente, sugli oggetti di apprendimento in corso e sulle date di scadenza imminenti.

L’avanzamento di ogni corso viene calcolato in base agli input specificati. ovvero la data di scadenza e i valori percentuali di avanzamento. Ad esempio, se specifichi 7 giorni e 70% come valori nel campo di input, vengono visualizzati l’avanzamento dell’utente per i diversi corsi con scadenza tra 7 giorni e per i corsi con avanzamento superiore al 70%.

**Abilità**

Nel foglio delle abilità, vengono forniti il nome dell’abilità, il livello di abilità, i crediti richiesti, i crediti acquisiti, la percentuale di completamento e altri dettagli del profilo. Di seguito è fornita un’istantanea di esempio del foglio Excel delle abilità come riferimento.

![](assets/skills-learner-transcript.png)

*Esempio di foglio Excel delle abilità*

**1 - Dashboard delle abilità**

In questo dashboard, puoi vedere se la tua organizzazione è attrezzata per varie abilità. Per un’abilità specifica, puoi controllare il numero di utenti di un’organizzazione che dovrebbero possedere questa abilità rispetto al numero di utenti che la possiedono effettivamente. Questo dashboard specifica anche gli utenti che devono aggiornare le proprie abilità. Questo valore viene calcolato in base all&#39;input immesso nel campo Input. Ad esempio, se immetti 50 giorni come input, il dashboard fornisce i dati sugli utenti che devono aggiornare le loro abilità dopo 50 giorni.

**2 - Dashboard delle abilità**

Questo dashboard delle abilità è più specifico dell’utente. Puoi filtrare uno o più utenti specifici e visualizzarne il livello di abilità come dashboard. Questo foglio consente ai manager e agli amministratori di tenere traccia delle competenze di ogni allievo rispetto a quelle previste. Il dashboard Abilità mette inoltre in luce gli Allievi che devono aggiornare le proprie abilità. L’elenco di aggiornamento degli Allievi viene calcolato in base al numero di giorni immessi nel campo di input.

**Dashboard di conformità**

Il dashboard di conformità è composto da due parti: report di conformità per utente e report di conformità per formazione. Per il report basato sull’utente, è possibile utilizzare il dashboard di conformità per tenere traccia degli utenti con date di scadenza imminenti per importanti iniziative di conformità. Per il report basato sulla formazione, puoi filtrare in base al programma di apprendimento o alla certificazione.

Per entrambi i rapporti di conformità, filtrare in base alla data di scadenza per visualizzare i dati appropriati.

### Colonne di data e ora nella trascrizione {#datetime}

I valori nelle colonne seguenti hanno minuti arrotondati al minuto più vicino e secondi a 00:

* Data di iscrizione (fuso orario UTC)
* Data di inizio (fuso orario UTC)
* Data di completamento (fuso orario UTC)

![](assets/time-columns-in-thetranscript.png)

*Colonne di data e ora nel foglio di Excel*

### Durata del modulo e colonne ID nella trascrizione {#moduledurationandidcolumnsinthetranscript}

La Trascrizione Allievo mostra anche le colonne: **[!UICONTROL Durata del modulo]** e **[!UICONTROL ID]**.

![](assets/lt-id-duration.png)

*Durata del modulo e colonne ID nella trascrizione*

### ALTRE colonne nella trascrizione {#ModuledurationandIDcolumnsinthetranscript-1}

| **Colonna** | **Descrizione** |
|---|---|
| Dopo | Numero di Allievi che hanno acquisito l’abilità prima del numero di giorni inserito (valore) che deve essere aggiornato |
| Abilità | I nomi delle competenze assegnate agli Allievi |
| Nome del manager | Il nome del manager dei subordinati i cui dati sul coinvolgimento sono visualizzati nella tabella di riepilogo dell’abilità |
| Etichette righe | Il nome dell’Allievo con l’elenco di abilità assegnate |
| Numero di abilità che ogni utente deve avere | Numero di abilità assegnate all’allievo |
| Numero di abilità di ogni utente | Numero di abilità acquisite dall’Allievo |
| Numero di abilità da aggiornare | Numero di Allievi la cui competenza deve essere aggiornata |
| Percentuale di conformità | Percentuale di avanzamento dell’abilità assegnata |
| Percorso incorporato | In queste righe sarà mostrato il nome del programma di apprendimento incorporato. |
| ID percorso incorporato | In queste righe saranno mostrati gli ID del programma di apprendimento incorporato. |
| Lingua percorso incorporato | In queste righe sarà mostrata la lingua di creazione del programma di apprendimento. |
