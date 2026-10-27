---
description: Scopri come i webhook di completamento Go1 aiutano Adobe Learning Manager a acquisire i completamenti del corso, anche quando gli Allievi chiudono anticipatamente il browser
jcr-language: en_us
title: Monitoraggio del completamento Go1 con i webhook
exl-id: 25c9c401-905f-4408-89ac-ac630a45a0c7
source-git-commit: aaea92d190b8ab22ce9f08c309faf5caa0b58a69
workflow-type: tm+mt
source-wordcount: '324'
ht-degree: 0%
---

# Monitoraggio del completamento Go1 con i webhook

## Panoramica

Adobe Learning Manager ora supporta il tracciamento del completamento basato su webhook per il contenuto Go1. Questo miglioramento migliora l’affidabilità della sincronizzazione di completamento del corso tra Go1 e Learning Manager. Gli eventi di completamento vengono acquisiti anche quando gli Allievi escono dal lettore del corso subito dopo aver terminato un corso.

Go1 utilizza i webhook per inviare notifiche di completamento del corso a Learning Manager ogni volta che un Allievo completa un corso Go1. Learning Manager riceve ed elabora questi eventi di completamento indipendentemente dalla sessione del browser dell’Allievo.

Inoltre, Go1 ritenta la consegna del webhook fino a quando Learning Manager non conferma la ricezione dell’evento di completamento. Ciò consente di evitare la perdita o l’incompletezza dei record di apprendimento.

## Problema risolto da questo miglioramento

In precedenza, il tracciamento del completamento si basava sulla comunicazione tra il lettore Go1 e Learning Manager, mentre la sessione del browser dell’Allievo rimaneva attiva. Se un Allievo chiudeva la finestra del browser o si allontanava prima che lo stato di completamento fosse stato completamente elaborato, il record di completamento poteva andare perso.

Di conseguenza:

* I completamenti del corso potrebbero non essere visualizzati nelle trascrizioni degli allievi.
* Gli amministratori possono rilevare discrepanze tra i completamenti effettivi e quelli registrati.
* Non è stato possibile recuperare automaticamente gli eventi di completamento mancanti.

## Flusso di lavoro eventi

1. Un Allievo avvia e completa un corso Go1.
1. Go1 registra il completamento.
1. Go1 invia un webhook di completamento a Learning Manager.
1. Learning Manager convalida e accetta l’evento di completamento.
1. Learning Manager aggiorna lo stato di completamento dell’Allievo.
1. Se Learning Manager non riconosce l’evento, Go1 riprova automaticamente il recapito.

## Domande frequenti

**Questa modifica richiede la configurazione dell&#39;amministratore**

No, questa modifica non richiede alcuna configurazione amministratore.

**Corsi Go1 esistenti interessati**

No, i corsi Go1 esistenti non sono interessati. Questo miglioramento migliora la sincronizzazione del completamento per il contenuto Go1.

**Cosa succede se un Allievo chiude anticipatamente il browser**

Go1 invia il webhook di completamento indipendentemente dalla sessione del browser dell’Allievo. Anche se l’Allievo esce dal lettore del corso, Go1 continua a ritentare il recapito fino a quando Learning Manager non riconosce l’evento di completamento.
