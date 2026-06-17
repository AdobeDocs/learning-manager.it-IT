---
jcr-language: en_us
title: Personalizzare un modello di Report Builder duplicato
description: Modifica una copia di un modello di Report Builder di Adobe Learning Manager in base alle tue specifiche esigenze di colonne, filtri e ordinamento.
contentowner: mmanuel
source-git-commit: 14970e9119077860dba6b4e60b3299b63f7db74c
workflow-type: tm+mt
source-wordcount: '372'
ht-degree: 0%

---


# Personalizzare un modello di Report Builder duplicato

Dopo aver duplicato un modello, potete aggiungere o rimuovere colonne, aggiornare i filtri, rinominare le colonne e regolare l’ordinamento prima di salvare e scaricare\. Questo articolo descrive ogni fase di personalizzazione\.

Prima di iniziare, duplica un modello dalla scheda **Modelli**.

## Aggiungere e rimuovere colonne

1. Nella visualizzazione di modifica individuare il set di dati contenente la colonna che si desidera aggiungere.
2. Seleziona **+** accanto al nome della colonna. La colonna viene visualizzata nell&#39;area di lavoro del report.
3. Per aggiungere la stessa colonna più di una volta, ad esempio per contare due valori di stato diversi. Selezionare nuovamente **+** per la colonna.
4. Per rimuovere una colonna, selezionala nell’area di lavoro, quindi seleziona l’icona Rimuovi.

## Riordinare e rinominare le colonne

1. Trascina una colonna nella posizione desiderata nell’area di lavoro. L&#39;ordine nell&#39;area di lavoro corrisponde all&#39;ordine delle colonne nel file scaricato.
2. Per rinominare una colonna, selezionarne il campo alias e immettere il nome che si desidera venga visualizzato come intestazione di colonna nel report.

## Aggiorna filtri

1. Per modificare un valore di filtro esistente, selezionare la riga di filtro, modificare il valore, quindi confermare.
2. Per aggiungere un nuovo filtro, selezionare **Aggiungi filtro**.
3. Scegli il campo in base al quale applicare il filtro.
4. Selezionare un operatore. Gli operatori disponibili dipendono dal tipo di dati del campo.
5. Immettere o selezionare un valore:
   * Per i campi stringa, digita per cercare e selezionare dai suggerimenti.
   * Per i campi elenco, selezionare uno o più valori dal selettore.
   * Per i campi data, immettere una data o scegliere un intervallo relativo, ad esempio gli ultimi 90 giorni.
6. Per rimuovere un filtro, seleziona l’icona Elimina sulla riga del filtro.

## Aggiorna ordinamento

1. Selezionare l&#39;icona di ordinamento nella colonna in base alla quale si desidera eseguire l&#39;ordinamento.
2. Selezionare **Crescente** o **Decrescente**.
3. Per ordinare in base a colonne aggiuntive, ripetere l&#39;operazione per ogni colonna. La prima colonna ordinata è primaria; ulteriori ordinamenti vengono applicati entro i limiti.

>[!TIP]
>
>Applicare sempre almeno un ordinamento. Senza ordinamento, l&#39;ordine delle righe può differire tra i download dello stesso report.

## Salva e scarica

1. Seleziona Salva per salvare le modifiche nella scheda **Report**.
2. Seleziona **Scarica** per generare il report. Riceverai una notifica in-app quando il file sarà pronto.
