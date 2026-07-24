---
jcr-language: en_us
title: Creare un report personalizzato nel Report Builder
description: Per creare un report completamente personalizzato in un Report Builder di Adobe Learning Manager, selezionare colonne, filtri, impostazioni per raggruppamento e ordinamento personalizzati da un'area di lavoro vuota.
contentowner: mmanuel
source-git-commit: 8823a5481bc3b34266f7ec36a8f3c26cb923e1ce
workflow-type: tm+mt
source-wordcount: '521'
ht-degree: 1%

---


# Creare un report personalizzato nel Report Builder

## Panoramica

La creazione da zero funziona meglio se disponi di un’immagine chiara delle colonne e dell’output necessari e se nessun modello esistente corrisponde al tuo caso d’uso. Se non conosci Report Builder, inizia con un modello.

## Creare un report personalizzato

In questo esempio, identificherai gli Allievi a rischio di corsi sulla conformità alla guida di ciascun Manager.

1. Accedi a Adobe Learning Manager come amministratore.
2. Seleziona **Report**, quindi seleziona **Report Builder**.
3. Seleziona la scheda **Report**, quindi seleziona **Crea report**.
4. Inserire un nome per il rapporto. È necessario specificare un nome. Se necessario, inserire una descrizione.

   ![](assets/report-builder-0013.png)

5. Nel pannello colonna, selezionate i seguenti set di dati ed espandeteli:

   * Utente
   * Oggetto di apprendimento
   * Stato conformità utente

6. Selezionare **+** accanto alle colonne da includere. Le colonne selezionate vengono visualizzate nell&#39;area di lavoro del report.

   * Utente - Nome
   * Nome utente - Manager
   * Oggetto di apprendimento: nome dell’oggetto di apprendimento
   * Stato conformità utente - % completamento
   * Stato conformità utente - % conformità

   ![](assets/report-builder-0014.png)

7. Riordinate le colonne trascinandole nell&#39;area di lavoro.
8. Per rinominare una colonna, immettere un nome nel campo alias della colonna. L&#39;alias viene visualizzato come intestazione di colonna nel file scaricato.
9. Seleziona **Salva report**.

## Scarica il report

1. Seleziona **Azioni** nell&#39;angolo superiore destro.

   ![](assets/report-builder-0015.png)

2. Seleziona **Scarica**. Puoi scaricare il report dall&#39;icona delle notifiche quando è pronto.

Il report scaricato (csv) contiene le seguenti colonne:

* nome
* managerName
* nome
* completedPct
* compliancePct

## Applicare raggruppamento, filtri e ordinamento

### Filtro

Ora che hai scaricato il report, applica un filtro in cui completionPct O compliancePct è uguale a 100.

1. Apri il report e seleziona **Modifica** nell&#39;angolo superiore destro.
2. Selezionare **Aggiungi filtro** ed eseguire la ricerca nelle colonne in cui si desidera applicare i filtri.

   ![](assets/report-builder-0016.png)

3. Seleziona **Aggiungi**.
4. Combinate i filtri con logica AND/OR; selezionate l&#39;operatore per passare da una riga all&#39;altra.

   ![](assets/report-builder-0017.png)

5. Seleziona **Salva report** e scarica il report.

Il report scaricato contiene record in cui completionPct O compliancePct è uguale a 100.

### Raggruppa per

Raggruppa i record per responsabile in modo da:

* Aggregazione dei dati degli Allievi per Manager
* Calcola medie a livello di manager
* Conteggio degli Allievi in ciascun Manager

1. Apri il report e seleziona **Modifica** nell&#39;angolo superiore destro.
2. Seleziona **Raggruppa per:Select** e seleziona la colonna **Nome utente-manager**.

   ![](assets/report-builder-0018.png)

3. Aggregare le seguenti colonne:

   * User-Name
   * Oggetto di apprendimento - Nome dell’oggetto di apprendimento

4. Selezionare **Count** come funzione di aggregazione per le colonne.

   ![](assets/report-builder-0019.png)

5. Ripeti per Oggetto di apprendimento - Nome oggetto di apprendimento.

   ![](assets/report-builder-0020.png)

6. Seleziona **Salva report** e scarica il report.

Il report scaricato contiene un riepilogo delle prestazioni di formazione degli Allievi per i Manager. Mostra i tassi medi di completamento, i punteggi medi di conformità e i conteggi totali degli Allievi per ogni Manager. I dati indicano il completamento della formazione universale in tutti i gruppi, mentre le prestazioni di conformità variano in modo significativo tra i manager.

### Ordina

Ordina il report in ordine decrescente in base al numero di Allievi per ogni Manager.

1. Apri il report e seleziona **Modifica** nell&#39;angolo superiore destro.
2. Selezionare **Aggiungi ordinamento**.
3. Cerca il nome utente e seleziona **Nome-utente**.
4. Selezionare **Decrescente**.

   ![](assets/report-builder-0021.png)

5. Seleziona **Aggiungi**.
6. Seleziona **Salva report** e scarica il report.

Il report scaricato contiene il numero di Allievi per Manager in ordine decrescente.
