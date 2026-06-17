---
jcr-language: en_us
title: Applica raggruppamento e aggregazioni nel Report Builder
description: Riepiloga i dati dei report di Adobe Learning Manager in base a un campo selezionato e calcola i conteggi, i totali e le percentuali in righe raggruppate.
contentowner: mmanuel
source-git-commit: 14970e9119077860dba6b4e60b3299b63f7db74c
workflow-type: tm+mt
source-wordcount: '519'
ht-degree: 0%

---


# Applica raggruppamento e aggregazioni nel Report Builder

Raggruppamento e aggregazione consentono di produrre report di riepilogo, ad esempio il numero totale di completamenti per istruttore, il numero di iscrizioni per catalogo o la percentuale di conformità per area.

## Quando utilizzare Raggruppa per

Utilizzare Raggruppa per quando si desidera una riga per categoria anziché una riga per record. Ad esempio:

* Una riga per istruttore, mostrando quante sessioni hanno insegnato
* Una riga per catalogo, con il totale delle iscrizioni
* Una riga per gruppo di utenti, con percentuale di conformità

Se desideri visualizzare i singoli record degli Allievi o le singole righe di iscrizione, non applicare Raggruppa per.

Quando si applica GroupBy a una colonna, a ogni colonna del report deve essere applicata una funzione di aggregazione. Non è possibile visualizzare un valore di campo non elaborato insieme a una colonna raggruppata, ma solo un valore calcolato (conteggio, somma, media e così via).

Ad esempio, se esegui il raggruppamento in base a **Nome istruttore**, non puoi visualizzare i singoli valori di **Nome sessione** accanto a esso. Al contrario, applicheresti **Count** al campo **ID sessione** per mostrare quante sessioni ha insegnato ciascun istruttore.

## Applica raggruppamento e aggregazioni

In questo esempio, confronterai l’avanzamento dell’iscrizione tra gli Allievi. Utilizzare questo report per comprendere le prestazioni dei diversi Manager in termini di avanzamento e completamento dell’iscrizione.

### Seleziona colonne

1. Avvia **Report Builder** e seleziona **Crea report**.
2. Digitare il nome e la descrizione del report:
a. **Nome:** Confronta l&#39;avanzamento della registrazione tra gli utenti
b. **Descrizione:** questo report raggruppa gli Allievi in base al Manager e calcola le metriche di riepilogo, ad esempio il totale degli Allievi, l’avanzamento medio e i conteggi di completamento per stato iscrizione=COMPLETATO
3. Selezionare le colonne seguenti: `<dataset>:<column name>`
a. Nome utente\manager
b. Utente\Nome
c. Iscrizione\Stato
d. Iscrizione\Percentuale avanzamento
e. Oggetto di apprendimento\Conteggio completamento

### Selezionare Raggruppa per colonne

1. Selezionare le colonne seguenti nella sezione **Raggruppa per**:
a. Iscrizione\Stato
b. Nome utente\manager
   ![](assets/image020.jpg)
2. Selezionare **Applica**.

### Selezionare le colonne da aggregare

Le funzioni di aggregazione riepilogano le prestazioni di iscrizione degli allievi per manager e lo stato di iscrizione, mostrando conteggi degli allievi distinti, percentuali medie di avanzamento dei corsi e conteggi medi di completamento degli oggetti di apprendimento tra record di formazione raggruppati.

1. Selezionare **Count Distinct** per User\Name.
2. Selezionare **Media** per Iscrizione\Percentuale avanzamento.
3. Seleziona **Media** per Oggetto di apprendimento\Conteggio completamento.
   ![](assets/image021.png)

### Applica filtri

Applica i filtri per includere solo le iscrizioni completate ed escludere i record con nomi di manager mancanti, assicurandoti che il report analizzi dati validi degli Allievi per analizzare in modo accurato lo stato di avanzamento della formazione per i Manager e le informazioni sul completamento.

1. Applica un filtro in cui _Stato-registrazione_ è uguale a _Completato_.
2. Applica un secondo filtro in cui _Nome utente-manager_ non è vuoto.
3. Combina entrambi i filtri utilizzando la condizione AND per includere solo i record dell’Allievo completato validi.

### Salvare e scaricare il report

Selezionate **Salva report** e selezionate **Azioni** > **Scarica** per scaricare il report. Riceverai una notifica per scaricare il report in formato .csv quando sarà pronto.

Il file CSV contiene un riepilogo per il manager delle iscrizioni completate e dell’avanzamento del corso di formazione. Ogni riga rappresenta un manager e include i conteggi degli allievi, lo stato dell’iscrizione, la percentuale di avanzamento media e i conteggi di completamento medi.

Nel complesso, il report confronta il completamento della formazione e l’attività di apprendimento tra i Manager, evidenziando le differenze nel coinvolgimento degli Allievi e il numero di oggetti di apprendimento completati.
