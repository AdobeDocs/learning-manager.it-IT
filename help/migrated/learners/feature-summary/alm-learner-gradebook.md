---
description: Tutte le informazioni sulla Gradiva dal punto di vista dell’Allievo
jcr-language: en_us
title: Gradebook per gli Allievi
source-git-commit: 40c3bcb1b23ad87a502692007f97b3df27b3a7b9
workflow-type: tm+mt
source-wordcount: '624'
ht-degree: 0%

---


# Gradebook per gli Allievi

## Inizia un corso con Gradebook

Quando il blocco appunti è abilitato e visibile per un corso in Adobe Learning Manager, nella pagina della panoramica del corso viene visualizzata la scheda **Registro appunti**. Puoi utilizzarlo per visualizzare il punteggio ponderato di ogni modulo, il punteggio aggregato corrente e se hai superato o se devi ancora completare una parte maggiore del corso.

![](assets/image_0008.png)

## Quando è disponibile il Gradebook

La scheda **Gradebook** viene visualizzata accanto a **Moduli**, **Note** e **Discussioni** nel lettore del corso quando l&#39;autore o l&#39;amministratore ha abilitato la visibilità dei gradebook per il corso. Se la scheda non è visibile, la funzionalità Gradebook non è stata abilitata per questo corso o l’amministratore ha disattivato la visibilità dell’Allievo. I punteggi potrebbero essere ancora registrati e visibili all&#39;amministratore.

Puoi aprire la scheda **Gradebook** in qualsiasi momento durante l&#39;iscrizione:

![](assets/image_0009.png)

* **Prima di iniziare:** Dopo l&#39;iscrizione, viene visualizzato l&#39;elenco completo dei moduli con punteggio con le relative percentuali di peso, i punteggi massimi per ciascuno e i criteri di superamento impostati dall&#39;autore. Questo mostra esattamente come viene valutato il corso prima di iniziare.
* **Durante l&#39;esecuzione:** mentre si completano moduli e punteggi, il grafico viene aggiornato in modo da mostrare i punteggi ottenuti insieme ai moduli non ancora tentati o in attesa di valutazione.
* **Dopo aver completato:** il grafico mostra tutti i punteggi finali del modulo, il punteggio aggregato del corso calcolato e un risultato **Superato** nell&#39;intestazione.

## Visualizzare il grafico

* Da **Il mio apprendimento**, seleziona il tuo corso.
* Seleziona la scheda **Gradebook** dalla pagina del corso.

  L’intestazione del grafico mostra:

  ![](assets/image_0010a.png)

* **Criteri di superamento:** Punteggio aggregato minimo e numero di moduli richiesti
* Numero di moduli obbligatori completati rispetto al totale
* **Punteggio aggregato** corrente come percentuale
* Stato corrente del corso: **Non avviato**, **Completamento in sospeso**, **Superato** o **Non riuscito**

La tabella dei moduli sotto l’intestazione mostra le seguenti colonne per ogni modulo:

| **Colonna** | **Elementi visualizzati** |
|------------|-------------------|
| **Modulo** | Nome e tipo del modulo |
| **Stato** | Stato di completamento o punteggio per questo modulo (vedi il riferimento allo stato di seguito) |
| **Peso** | Percentuale di contributo del modulo al punteggio aggregato |
| **Punteggio** | Il tuo punteggio per questo modulo (ad esempio, 40/100) |
| **Contributo** | Punti percentuali effettivi aggiunti finora dal modulo al punteggio aggregato |

## Visualizzare la ponderazione del modulo dalla scheda Moduli

Puoi anche visualizzare il peso di ogni modulo dalla scheda **Moduli** senza aprire il grafico.

Dalla pagina del corso, seleziona la scheda **Moduli**.

![](assets/image_0011.png)

Nella scheda **Moduli** vengono visualizzati la percentuale di ponderazione per ogni modulo e il numero di moduli necessari per completare il corso.

## Punteggi del modulo con più tentativi

Se un modulo consente più tentativi, il punteggio mostrato nel grafico dipende da come l’autore del corso lo ha configurato:

* **Massimo:** viene visualizzato il punteggio migliore di qualsiasi tentativo. Un punteggio inferiore in un tentativo successivo non riduce il punteggio registrato.
* **Ultime novità:** il punteggio ottenuto dal tentativo più recente viene sempre visualizzato. Un punteggio inferiore in un tentativo successivo sostituisce quello precedente.

## Comprendere lo stato del modulo

Ogni modulo nel blocco appunti mostra uno dei seguenti stati:

![](assets/image_0012.png)

| **Stato** | **Interpretazione** |
| ------------ | ------------------- |
| **Superato** | Modulo completato e punteggio registrato |
| **In corso** | Modulo avviato ma non ancora completato |
| **Non avviato** | Modulo non ancora aperto |
| **Non riuscito** | Il modulo ha ottenuto un punteggio e non ha raggiunto la soglia di superamento del modulo |

## Come viene calcolato il punteggio aggregato

Il punteggio aggregato è la somma del contributo ponderato di ciascun modulo con punteggio:

(Punteggio ottenuto ÷ Punteggio massimo) × % ponderazione = Contributo modulo

La colonna **Contributo** nel diagramma mostra il contributo di ogni modulo all&#39;aggregazione corrente. I moduli contrassegnati con **Nessuna ponderazione** sono esclusi da questo calcolo.

Non è necessario che la scala di punteggio sia la stessa per tutti i moduli. Un modulo ha ottenuto un punteggio di 100 e un modulo ha ottenuto un punteggio di 10. Entrambi contribuiscono correttamente. La formula normalizza ciascuna di esse prima di applicare la ponderazione.
