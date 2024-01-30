---
jcr-language: en_us
title: Non è possibile visualizzare i file inviati su Adobe Learning Manager
description: Gli istruttori non sono in grado di visualizzare i file caricati dagli allievi nel Modulo attività di invio.
contentowner: nluke
source-git-commit: 8b29ac996962e7ce8fbda51f3421c9a5f248fcf6
workflow-type: tm+mt
source-wordcount: '205'
ht-degree: 50%

---



# Non è possibile visualizzare i file inviati su Adobe Learning Manager

## Problema

L’istruttore non è in grado di vedere i file inviati e caricati da un allievo.

## Descrizione

Gli istruttori non sono in grado di visualizzare i file caricati dagli allievi nel **Modulo attività di invio**.

Ad esempio, un Allievo si è iscritto a un’istanza denominata **Istanza di test** di un corso, come illustrato di seguito:

![](assets/test-instance.png)

*Visualizza istanza*

A questo punto, l’allievo apre il corso e carica un file nel modulo attività.

Quando l’istruttore tenta di approvare l&#39;invio, non è in grado di eseguire tale operazione.

![](assets/activity.png)

*Caricare un file nel modulo Attività*

## Causa

Il problema si verifica se nell’istanza del corso a cui l’Allievo è iscritto non è presente un Istruttore.

## Risoluzione

Per verificare la presenza di un istruttore nell’istanza del corso, procedi come indicato di seguito:

1. Vai alle impostazioni del corso.
1. Nella **Gestisci** , fare clic su **[!UICONTROL Istanze].**
1. Nell’istanza a cui è iscritto l’Allievo, fai clic su **[!UICONTROL Sessioni]**.

   ![](assets/check-instructor.png)

   *Selezionare Sessioni nell&#39;istanza*

   Nessun istruttore assegnato a questa sessione.

1. Fai clic **[!UICONTROL Modifica]**. Aggiungi l’istruttore che si occupa di approvare l’invio dei file.

   ![](assets/assign-instructor.png)

   *Aggiungere l’istruttore*
1. Salva le modifiche.

