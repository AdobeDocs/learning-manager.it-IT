---
jcr-language: en_us
title: Problemi relativi al ritiro di un programma di apprendimento
description: Problemi relativi al ritiro di un programma di apprendimento in Adobe Learning Manager
contentowner: nluke
exl-id: 706cafe3-2650-4837-9dee-e381a4a711f9
source-git-commit: a0c01c0d691429bd66a3a2ce4cfc175ad0703157
workflow-type: tm+mt
source-wordcount: '231'
ht-degree: 55%

---

# Problemi relativi al ritiro di un programma di apprendimento

## Problema

Un programma di apprendimento viene automaticamente ritirato.

## Causa

In alcuni casi un programma di apprendimento è stato ritirato senza che un amministratore/autore abbia esplicitamente ritirato il programma.

Questo problema si verifica perché un programma di apprendimento è una raccolta di corsi. I corsi di formazione di ordine superiore vengono ritirati se uno dei corsi in essi contenuti include un&#39;istanza ritirata o se l&#39;istanza del corso viene ritirata.

## Risoluzione

Per controllare il corso che include un&#39;istanza ritirata, procedi come segue:

1. Accedi come amministratore e avvia il programma di apprendimento pertinente.

1. Fai clic su **[!UICONTROL Istanze]** > **Ccorsi**. Nella pagina sono elencati tutti i corsi inclusi in questo programma di apprendimento. Potrai visualizzare il corso che contiene un’istanza ritirata.

   ![](assets/retired-instance.png)

   *Visualizza elenco di tutti i corsi*

1. Dopo aver individuato l’istanza del corso che è stata ritirata, fai clic su **[!UICONTROL Corsi]** > **[!UICONTROL Apri il corso]**.

1. Fai clic su **[!UICONTROL Istanze]**. Nell&#39;istanza ritirata, fai clic su **[!UICONTROL Modifica]** e quindi imposta la data di completamento su una data futura in cui desideri che l&#39;istanza venga ritirata.

   ![](assets/completion-date.png)

   *Modificare la data di completamento di un corso*

1. Al termine, fai clic sul menu a discesa come illustrato nell&#39;immagine seguente. Fai quindi clic su **[!UICONTROL Riapri istanza]**.

   ![](assets/re-open-instance.png)

   *Riaprire l&#39;istanza di un corso*

1. Visita il programma di apprendimento pertinente. Fai clic su **[!UICONTROL Istanze]** ed esegui il passaggio precedente per riaprire l’istanza del programma di apprendimento.
