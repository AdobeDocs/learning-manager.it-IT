---
jcr-language: en_us
title: Aggiungere e combinare i filtri in un report
description: Limitare i dati dei report nel Report Builder Adobe Learning Manager utilizzando filtri singoli, logica AND/OR e gruppi di filtri nidificati.
contentowner: mmanuel
source-git-commit: 8823a5481bc3b34266f7ec36a8f3c26cb923e1ce
workflow-type: tm+mt
source-wordcount: '620'
ht-degree: 0%

---


# Aggiungere e combinare i filtri in un report

## Panoramica

I filtri consentono di definire esattamente l’ambito del report in base ai record necessari. Potete applicare un singolo filtro, combinare più filtri con logica AND o OR e creare gruppi nidificati per condizioni complesse.

## Aggiungi un filtro

Utilizzare i filtri per limitare il report a un sottoinsieme di dati specifico invece di visualizzare tutto.

Ad esempio, potresti voler capire quanti Allievi si sono iscritti ai corsi negli ultimi 365 giorni. In questo caso, per includere solo l’attività recente, applicherai un filtro per data alla data di iscrizione.

1. Avvia Report Builder e seleziona **Crea report**.
2. Digitare il nome e la descrizione del report.
3. Selezionare le colonne seguenti: <dataset>:<column name>

   * Iscrizione - Data di iscrizione
   * Utente - Nome

   ![](assets/report-builder-0024.png)

4. Nella sezione Report, seleziona **Aggiungi filtro**.
5. Cercare o selezionare il campo in base al quale si desidera filtrare i dati. In questo esempio, seleziona **Iscrizione - Data iscrizione**.

   ![](assets/report-builder-0025.png)

6. Seleziona **Aggiungi**.
7. Selezionare un operatore. Gli operatori disponibili dipendono dal tipo di dati del campo:

   * Campi stringa - contiene, è uguale a, inizia con
   * Campi numerici - maggiore di, minore di, uguale a, tra
   * Campi data: uguale a, prima, dopo, tra, ultimi N giorni
   * Campi elenco (enum): è incluso, non è incluso

8. In questo caso, seleziona **rientra nell&#39;ultimo anno**.

   ![](assets/report-builder-0026.png)

9. Selezionate **Salva report** e selezionate **Azioni** > **Scarica** per scaricare il report.

Il report scaricato elenca tutti gli utenti iscritti a un oggetto di apprendimento negli ultimi 365 giorni.

## Aggiungere più filtri con logica AND/OR

Quando aggiungete un secondo filtro, la relazione predefinita tra i filtri è AND; affinché una riga venga visualizzata, entrambe le condizioni devono essere vere.

Ad esempio, potresti voler identificare gli Allievi iscritti ai corsi negli ultimi 365 giorni E fare rapporto a un Manager specifico. In questo caso, entrambe le condizioni devono essere vere, in modo che i filtri vengano combinati utilizzando la logica AND.

1. Avvia Report Builder e seleziona **Crea report**.
2. Digitare il nome e la descrizione del report.
3. Selezionare le colonne seguenti: <dataset>:<column name>

   * Utente - Nome
   * Utente - Nome Manager
   * <span class="mark">Iscrizione - Data di iscrizione</span>

4. Raggruppa in base alla colonna **User-Manager Name**.
5. Nella sezione Filtro, seleziona i seguenti filtri:

   * Iscrizione - Data di iscrizione i **s nell&#39;ultimo anno**
   * Utente - Nome manager **inizia con** N
   * Utente - Il nome del manager **non è vuoto**

     ![](assets/report-builder-0027.png)

6. Selezionate **Salva report** e selezionate **Azioni** > **Scarica** per scaricare il report.

Nel report scaricato sono elencati tutti gli utenti iscritti a un oggetto di apprendimento negli ultimi 365 giorni **e** che hanno inviato un report a un Manager il cui nome inizia con N.

## Creare gruppi di filtri nidificati

I gruppi nidificati consentono di creare condizioni con più livelli logici, equivalenti alle parentesi in una formula. Ad esempio: (Catalogo = Sicurezza O Catalogo = Igiene) AND La data di completamento è negli ultimi 90 giorni.

Utilizzare i gruppi di filtri nidificati quando la logica include una combinazione di condizioni AND e OR che devono essere valutate insieme.

Ad esempio, utilizza la logica del filtro nidificato per identificare iscrizioni incomplete per le quali gli Allievi hanno compiuto progressi al di sotto del 50% o hanno terminato un corso di formazione, dimostrando come funzionano insieme le condizioni AND e OR.

1. Avvia Report Builder e seleziona **Crea report**.
2. Digitare il nome e la descrizione del report.
3. Selezionare le colonne seguenti: <dataset>:<column name>

   * Iscrizione - Stato
   * Iscrizione - Percentuale avanzamento
   * Iscrizione scaduta

     ![](assets/report-builder-0028.png)

4. Nella sezione **Filtro**, seleziona i seguenti filtri:

   * Iscrizione: lo stato **non corrisponde a nessuno di** completato.
   * Seleziona +.
   * Cerca la percentuale di avanzamento dell’iscrizione.
   * Seleziona il filtro.
   * Seleziona **Aggiungi come gruppo**.

     ![](assets/report-builder-0029.png)

5. Aggiungi iscrizione - Percentuale avanzamento **inferiore a** 50.

   ![](assets/report-builder-0030.png)

6. Seleziona +.
7. Cerca **Iscrizione scaduta**.
8. Seleziona il filtro.
9. Seleziona **Aggiungi come gruppo**.

   ![](assets/report-builder-0031.png)

10. Aggiungi iscrizione scaduta è uguale a TRUE.
11. Modificate l&#39;AND nidificato in OR.

    ![](assets/report-builder-0032.png)

12. Selezionate **Salva report** e selezionate **Azioni** > **Scarica** per scaricare il report.

Il report scaricato elenca tutte le iscrizioni in corso o non avviate, con una percentuale di avanzamento inferiore al 50% o scadute.
