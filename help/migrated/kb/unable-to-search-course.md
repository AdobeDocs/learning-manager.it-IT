---
jcr-language: en_us
title: Non è possibile cercare un corso in Learning Manager
description: Un Allievo non riesce a cercare un corso in Learning Manager.
contentowner: nluke
exl-id: 702aacb7-a0b9-48fb-8a3d-425bfea63f65
source-git-commit: a0c01c0d691429bd66a3a2ce4cfc175ad0703157
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

1. Fai clic su **[!UICONTROL Catalogo]** e individua il catalogo che contiene il corso.
1. Fai clic su **[!UICONTROL Condividi internamente]** o **[!UICONTROL Contenuto]** (a seconda dello scenario sopra menzionato).

   ![](assets/cp-share-internally.png)

   *Condivisione interna del catalogo*

1. Consulta gli scenari seguenti:

   * L’Allievo non fa parte del catalogo

     Per condividere il catalogo, fai clic su **[!UICONTROL Aggiungi]** e aggiungi il gruppo di cui fa parte l&#39;utente. Fai clic su **[!UICONTROL Salva]**.

     ![](assets/cp-add-user-group.png)

     *Aggiungere il gruppo di utenti*

   * Il corso non fa parte del catalogo

     Nella sezione Contenuto, fai clic su **[!UICONTROL Aggiungi contenuto]** e seleziona il corso da aggiungere al catalogo.

     ![](assets/cp-add-content.png)

     *Aggiungi contenuto al corso*
