---
jcr-language: en_us
title: Non è possibile cercare un corso in Learning Manager
description: Un Allievo non riesce a cercare un corso in Learning Manager.
contentowner: nluke
source-git-commit: 8b29ac996962e7ce8fbda51f3421c9a5f248fcf6
workflow-type: tm+mt
source-wordcount: '307'
ht-degree: 55%

---



# Non è possibile cercare un corso in Learning Manager

## Il problema

Un Allievo non riesce a cercare un corso in Learning Manager.

## Scenario 1: l’iscrizione è effettuata tramite un oggetto di apprendimento superiore

### Riepilogo

Ci sono scenari in cui un allievo cerca un corso ma il corso non è nell’elenco. Tuttavia, se l’allievo si è iscritto a un programma di apprendimento o una certificazione, l’allievo può visualizzare il corso all’interno dell’oggetto di apprendimento.

### Perché si verifica il problema?

In Learning Manager, quando un Allievo si iscrive tramite un programma di apprendimento o una certificazione, l’iscrizione a tale corso avviene tramite il programma di apprendimento o la certificazione.

Pertanto, l’allievo non è in grado di cercare i corsi autonomi in **Il mio apprendimento**.

Tuttavia, l’Allievo non può visualizzare i corsi all’interno del programma di apprendimento o della certificazione.

## Scenario 2: l’Allievo non ha accesso al catalogo che contiene il corso.

### Riepilogo

Un allievo non è in grado di cercare corsi nel catalogo o nel dashboard di apprendimento.

### Perché si verifica il problema?

Questo problema si verifica se:

* L’allievo non fa parte del Catalogo che contiene il corso **OPPURE**
* Il corso non fa parte del Catalogo a cui l’allievo ha accesso.

### Risoluzione

1. Accedi come Amministratore.

1. Fai clic **[!UICONTROL Catalogo]** e sfoglia il catalogo che contiene il corso.
1. Fai clic **[!UICONTROL Condividi internamente]** oppure **[!UICONTROL Contenuto]** (a seconda dello scenario sopra menzionato).

   ![](assets/cp-share-internally.png)

   *Condivisione interna del catalogo*

1. Consulta gli scenari seguenti:

   * L’Allievo non fa parte del catalogo

     Per condividere il catalogo, fai clic su **[!UICONTROL Aggiungi]** e aggiungi il gruppo di cui fa parte l’utente. Fai clic su **[!UICONTROL Salva]**.

     ![](assets/cp-add-user-group.png)

     *Aggiungere il gruppo di utenti*

   * Il corso non fa parte del catalogo

     Nella sezione Contenuto, fai clic su **[!UICONTROL Aggiungi contenuto]** e seleziona il corso da aggiungere al catalogo.

     ![](assets/cp-add-content.png)

     *Aggiungere contenuti al corso*
