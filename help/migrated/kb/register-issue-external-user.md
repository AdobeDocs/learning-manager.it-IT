---
jcr-language: en_us
title: Impossibile effettuare la registrazione come utente esterno
description: Gli Allievi esterni non possono effettuare la registrazione a un profilo in Adobe Learning Manager.
contentowner: nluke
exl-id: b1a9ecb6-75a8-44f7-b169-f77d7a4f6c2c
source-git-commit: a0c01c0d691429bd66a3a2ce4cfc175ad0703157
workflow-type: tm+mt
source-wordcount: '328'
ht-degree: 50%

---

# Impossibile effettuare la registrazione come utente esterno

## Problema

Gli Allievi esterni non possono effettuare la registrazione con un profilo.

## Errore

L’ID e-mail è già registrato. Utilizza un indirizzo e-mail diverso.

![](assets/cp-register-profile.png)

*Messaggio di errore di un messaggio di posta elettronica già registrato*

## Descrizione

Ci sono scenari in cui un utente non può registrarsi con un profilo esterno. Durante la registrazione, l’utente riceve il messaggio d’errore di cui sopra.

## Causa

Questo problema si verifica in uno dei seguenti scenari:

* L’utente è già registrato con un altro profilo esterno.
* L’utente è già un Allievo interno.
* All’utente è attribuito lo stato Eliminato.

## Risoluzione:

**Scenario 1:** L&#39;utente è già registrato con un altro profilo esterno.

1. Accedi come Amministratore.
1. In **Gestisci**, fai clic su **[!UICONTROL Utenti]** > **[!UICONTROL Esterni]**.
1. Apri il profilo di cui l’utente fa già parte facendo clic su Postazioni utilizzate

   ![](assets/cp-seats-used.png)

   *Apri profilo utente*

1. Selezionare l&#39;utente, fare clic su **[!UICONTROL Azioni]** > **[!UICONTROL Modifica profilo]**.

   ![](assets/cp-change-profile.png)

   *Modifica profilo utente*

   Viene visualizzata una finestra per selezionare un nuovo profilo come indicato di seguito.

   ![](assets/cp-select-profiles.png)

   *Selezionare il profilo utente*

1. Una volta selezionato, fai clic su **[!UICONTROL Modifica]**.

**Scenario 2:** L’utente è presente come Allievo interno.

1. Accedi come Amministratore.
1. In **Gestisci**, fai clic su **[!UICONTROL Utenti]** > **[!UICONTROL Interni]**.
1. Fai clic per aprire un profilo Allievo e fai clic sull&#39;icona Modifica.

   ![](assets/cp-internal-learner.png)

   *Aprire un profilo Allievo interno*

1. Modifica l’indirizzo e-mail dell’Allievo o aggiungi *_old* all’indirizzo e-mail esistente. In questo modo l’indirizzo e-mail sarà gratuito.

   Ad esempio, se l’indirizzo e-mail dell’Allievo è *<abc@adobe.com>,* modificalo in *<abc_old@adobe.com>*

1. Fai clic su **Salva** per mantenere le modifiche apportate.

**Scenario 3**: all’utente è attribuito lo stato Eliminato.

1. Accedi come Amministratore.
1. In **Gestisci**, fai clic su **[!UICONTROL Utenti]** > **[!UICONTROL Pulizia utente]**.
1. Seleziona l’Allievo e fai clic sull’icona Modifica.

   ![](assets/cp-deleted-learner.png)

   *Modifica indirizzo e-mail utente*

1. Modifica l’indirizzo e-mail dell’Allievo o aggiungi *_old* all’indirizzo e-mail esistente. In questo modo l’indirizzo e-mail sarà gratuito.

   Ad esempio, se l’indirizzo e-mail dell’Allievo è **<abc@adobe.com>**, modificalo in **<abc_old@adobe.com>**.
