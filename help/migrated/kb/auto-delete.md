---
jcr-language: en_us
title: L’utente viene eliminato automaticamente in Learning Manager
description: Un utente viene eliminato da Learning Manager anche se l’Amministratore non ha mai eseguito alcuna azione di questo tipo.
contentowner: nluke
source-git-commit: 3242a293fc4b2707044e11c342c984cbfb2fc434
workflow-type: tm+mt
source-wordcount: '234'
ht-degree: 55%

---



# L’utente viene eliminato automaticamente in Learning Manager {#user-gets-auto-deleted-in-learning-manager}

## Il problema

A **utente** viene eliminato da Learning Manager, tuttavia, l’Amministratore non ha mai eseguito alcuna azione di questo tipo.

## Causa

In Adobe Learning Manager è disponibile un’opzione che consente di eliminare un utente che non effettua l’accesso al sistema da un certo periodo di tempo.

## Come si modifica/applica l’impostazione?

### Per Allievi interni

1. Accedi come **Amministratore**.
1. Sotto **Configura**, fare clic su **Impostazioni** > **Generale**.
1. Nella pagina Impostazioni generali, visualizza l’opzione **Elimina automaticamente utenti interni**.
1. Fai clic **[!UICONTROL Modifica]** per immettere il numero di giorni nel campo, per eliminare automaticamente un Allievo che non ha effettuato l’accesso al sistema.

   ![](assets/cp-autodelete-internal.png)

   *Modifica il numero di giorni*

>[!NOTE]
>
>   Lascia vuoto il campo se non desideri eliminare automaticamente gli utenti.


1. Fai clic **[!UICONTROL Salva]** per mantenere le impostazioni configurate.

### Se sei un Allievo esterno:

1. Accedi come **Amministratore**.
1. Sotto **Gestisci**, fare clic su **[!UICONTROL Utenti]** > **[!UICONTROL Esterno]**.
1. Fai clic sul nome di un utente esterno per il quale occorre applicare l’impostazione.

   Viene aperta la finestra **Modifica profilo di registrazione esterno**.

1. Fai clic **[!UICONTROL Impostazioni avanzate]** nell’angolo in basso a sinistra.

   ![](assets/cp-autodelete-external.png)

   *Seleziona l’opzione Impostazioni avanzate*

1. Nella **Requisiti di accesso** immetti il numero di giorni per l’eliminazione automatica di un allievo che non ha effettuato l’accesso al sistema.
1. Fai clic **[!UICONTROL Salva]** per mantenere le impostazioni configurate.
