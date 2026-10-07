---
jcr-language: en_us
title: Il modulo risulta incompleto al termine del corso su Adobe Learning Manager
description: Il modulo risulta incompleto anche dopo che un Allievo ha completato un corso in Adobe Learning Manager.
contentowner: nluke
exl-id: c0f14f2e-733a-4b4f-a2c2-4c0b33a15fa1
product_v2:
  - id: ed12e5b7-96e3-45e7-a17f-de222065ebcb
    internal-label: Learning Manager
source-git-commit: c061ccbefe8d40154220587796062d335e35de77
workflow-type: tm+mt
source-wordcount: '191'
ht-degree: 65%
---
# Il modulo risulta incompleto al termine del corso su Adobe Learning Manager

## Il problema

Il modulo risulta incompleto anche dopo che un Allievo ha completato un corso in Adobe Learning Manager.

## Causa

SCORM 2004 definisce i criteri di successo e di completamento e invia i due riepiloghi separatamente.

Ad esempio, prendiamo il caso di un set di contenuti in cui **Criteri di completamento** sia impostato su 100% visualizzazioni diapositive e **Criteri di successo** su &quot;Quiz superato&quot;.

Un allievo completa il corso ma non supera il quiz. In questo caso, il progresso è del 100%, ma il modulo risulta incompleto perché l’allievo non soddisfa i **criteri di successo**.

## Soluzione

Il problema riguarda le **Preferenze** di reporting impostate per il progetto. L’autore deve verificare i criteri di completamento e di successo del corso.

Se sono necessarie modifiche, l’autore può effettuarle con uno strumento di authoring dei contenuti, ad esempio Adobe Captivate Classic. L’autore può quindi aggiornare il modulo di conseguenza.

![](assets/scorm.png)

*Visualizza Captivate preferenze report classiche*
