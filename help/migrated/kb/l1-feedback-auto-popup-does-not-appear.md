---
jcr-language: en_us
title: Il popup automatico del feedback L1 non viene visualizzato
description: Come risolvere l’errore "Il popup automatico del feedback L1 non viene visualizzato"
contentowner: saghosh
exl-id: 47edcd7f-e332-4a75-a025-fd07737d0b70
product_v2:
  - id: ed12e5b7-96e3-45e7-a17f-de222065ebcb
    internal-label: Learning Manager
source-git-commit: c061ccbefe8d40154220587796062d335e35de77
workflow-type: tm+mt
source-wordcount: '205'
ht-degree: 77%
---
# Il popup automatico del feedback L1 non viene visualizzato

## Problema

Il popup automatico del feedback L1 non viene visualizzato per un Allievo al termine del corso.

## Causa

A volte può accadere che un Allievo non riceva il feedback L1 dopo aver completato un determinato corso o che riceva un messaggio analogo al seguente:

![](assets/l1-feedback.png)

*Impossibile ricevere feedback L1*

Questo accade per i seguenti motivi:

1. Il feedback non è impostato per essere visualizzato dopo il completamento del corso.
1. I promemoria sono disattivati.
1. Il promemoria è programmato per essere visualizzato dopo un determinato periodo di tempo.

## Risoluzione

1. Assicurati che l’opzione &quot;Mostra questionario immediatamente dopo il completamento del corso&quot; sia abilitata in **Corso** > **Istanze** > **Feedback L1**.
   <!--![](assets/l1-feedback.png)-->
1. Come Amministratore, seleziona **Impostazioni > Feedback**. Verifica per quando è programmato il promemoria. Se è programmato per **Dopo il completamento del corso**, modifica l’opzione in **Al completamento del corso**.
1. Abilita i seguenti modelli e-mail: **Modelli e-mail > Promemoria e aggiornamenti > Richiedi feedback dell’Allievo per il corso**. Se l’opzione è disattivata, attivala e prova.
1. Se seguendo i passaggi precedenti non risolvi il problema, elimina il promemoria presente in **Amministratore > Impostazioni > Feedback**. Creane uno per &quot;Al completamento del corso&quot; e imposta la ricorrenza in base alle esigenze.
