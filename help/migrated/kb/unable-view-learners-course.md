---
jcr-language: en_us
title: Impossibile visualizzare gli Allievi in un corso
description: Nella scheda Allievi di un corso non viene visualizzato alcun Allievo iscritto ad Adobe Learning Manager. Tuttavia, se si genera un report, è possibile visualizzare gli Allievi iscritti al report.
contentowner: saghosh
source-git-commit: 8b29ac996962e7ce8fbda51f3421c9a5f248fcf6
workflow-type: tm+mt
source-wordcount: '212'
ht-degree: 0%

---



# Impossibile visualizzare gli Allievi in un corso

## Problema

Non è possibile visualizzare gli Allievi iscritti a un corso.

## Descrizione

Nella scheda Allievi di un corso non viene visualizzato alcun Allievo iscritto. Tuttavia, se si genera un report, è possibile visualizzare gli Allievi iscritti al report.

![](assets/no-learners.png)

*Nessun Allievo visualizzato*

## Causa

Se un Allievo è iscritto tramite un oggetto di apprendimento superiore (programma di apprendimento o certificazione), sarà visibile nella scheda Allievo dell’oggetto di apprendimento superiore. La ricerca dell’Allievo non sarà possibile nella scheda Allievi del corso.

**Come si visualizza l’oggetto di apprendimento superiore a cui è iscritto l’Allievo?**

Puoi controllare queste informazioni nel report Trascrizione Allievo. Per generare una Trascrizione Allievo, segui i passaggi riportati di seguito:

1. Accedi come Amministratore.
1. Fai clic **[!UICONTROL Report]** > **[!UICONTROL Report personalizzati]** > **[!UICONTROL Report Excel]** > **[!UICONTROL Trascrizione Allievo]**.

1. Immetti il nome del **[!UICONTROL Allievo]** e specificare **[!UICONTROL Data]** intervallo.
1. Espandere la sezione **[!UICONTROL Opzioni avanzate]** e seleziona l’opzione **[!UICONTROL Abilita informazioni a livello di modulo]**.
1. Fai clic **[!UICONTROL Genera]**.

   Nella Trascrizione Allievo, puoi visualizzare l’oggetto di apprendimento superiore tramite il quale è iscritto l’Allievo.
