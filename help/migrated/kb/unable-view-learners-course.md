---
jcr-language: en_us
title: Impossibile visualizzare gli Allievi in un corso
description: Nella scheda Allievi di un corso non viene visualizzato alcun Allievo iscritto a Adobe Learning Manager. Tuttavia, se si genera un report, è possibile visualizzare correttamente gli Allievi iscritti.
contentowner: saghosh
exl-id: 2ea54347-fa6b-493e-b73c-d350efb2aaaf
product_v2:
  - id: ed12e5b7-96e3-45e7-a17f-de222065ebcb
    internal-label: Learning Manager
source-git-commit: c061ccbefe8d40154220587796062d335e35de77
workflow-type: tm+mt
source-wordcount: '212'
ht-degree: 58%
---
# Impossibile visualizzare gli Allievi in un corso

## Problema

Non è possibile visualizzare gli Allievi iscritti a un corso.

## Descrizione

Nella scheda Allievi di un corso non risulta nessun Allievo iscritto. Tuttavia, se si genera un report, è possibile visualizzare correttamente gli Allievi iscritti.

![](assets/no-learners.png)

*Nessun Allievo visualizzato*

## Causa

Se un Allievo è iscritto tramite un oggetto di apprendimento superiore (programma di apprendimento o certificazione), sarà visibile nella scheda Allievo dell’oggetto di apprendimento superiore. La ricerca dell’Allievo non sarà possibile nella scheda Allievi del corso.

**Come visualizzare l’oggetto di apprendimento superiore a cui è iscritto l’Allievo?**

È possibile verificare queste informazioni nel report Trascrizione Allievo. Per generare un report Trascrizione Allievo, effettua le seguenti operazioni:

1. Accedi come Amministratore.
1. Fai clic su **[!UICONTROL Report]** > **[!UICONTROL Report personalizzati]** > **[!UICONTROL Report Excel]** > **[!UICONTROL Trascrizione Allievo]**.

1. Immetti il nome dell&#39;**[!UICONTROL Allievo]** e specifica l&#39;intervallo di **[!UICONTROL Date]**.
1. Espandi la sezione **[!UICONTROL Opzioni avanzate]** e seleziona l’opzione **[!UICONTROL Abilita informazioni sul livello di modulo]**.
1. Fai clic su **[!UICONTROL Genera]**.

   Nella Trascrizione Allievo è possibile visualizzare l’oggetto di apprendimento superiore tramite il quale è iscritto l’Allievo.
