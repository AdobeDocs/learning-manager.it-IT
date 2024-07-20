---
jcr-language: en_us
title: L’utente viene eliminato automaticamente in Learning Manager
description: Un utente viene eliminato da Learning Manager anche se l’Amministratore non ha mai eseguito alcuna azione di questo tipo.
contentowner: nluke
exl-id: 9e293da3-bcbf-4798-b391-aef53ef8d946
source-git-commit: a0c01c0d691429bd66a3a2ce4cfc175ad0703157
workflow-type: tm+mt
source-wordcount: '234'
ht-degree: 61%

---

# L’utente viene eliminato automaticamente in Learning Manager {#user-gets-auto-deleted-in-learning-manager}

## Il problema

Un utente viene eliminato da Learning Manager anche se l’Amministratore non ha mai eseguito alcuna azione di questo tipo.

## Causa

In Adobe Learning Manager è disponibile un’opzione che consente di eliminare un utente che non effettua l’accesso al sistema da un certo periodo di tempo.

## Come si modifica/applica l’impostazione?

### Per Allievi interni

1. Accedi come **Amministratore**.
1. In **Configura**, fai clic su **Impostazioni** > **Generali**.
1. Nella pagina Impostazioni generali, visualizza l’opzione **Elimina automaticamente utenti interni**.
1. Fai clic su **[!UICONTROL Modifica]** per immettere il numero di giorni nel campo e per eliminare automaticamente un Allievo che non ha effettuato l’accesso al sistema.

   ![](assets/cp-autodelete-internal.png)

   *Modifica il numero di giorni*

>[!NOTE]
>
>   Lascia vuoto il campo se non desideri eliminare automaticamente gli utenti.


1. Fai clic su **[!UICONTROL Salva]** per mantenere le impostazioni configurate.

### Se sei un Allievo esterno:

1. Accedi come **Amministratore**.
1. In **Gestisci**, fai clic su **[!UICONTROL Utenti]** > **[!UICONTROL Esterni]**.
1. Fai clic sul nome di un utente esterno per il quale occorre applicare l’impostazione.

   Viene aperta la finestra **Modifica profilo di registrazione esterno**.

1. Fai clic su **[!UICONTROL Impostazioni avanzate]** nell&#39;angolo in basso a sinistra.

   ![](assets/cp-autodelete-external.png)

   *Selezionare l&#39;opzione Impostazioni avanzate*

1. Nel campo **Requisiti di accesso**, immetti il numero di giorni per l’eliminazione automatica di un Allievo che non ha effettuato l’accesso al sistema.
1. Fai clic su **[!UICONTROL Salva]** per mantenere le impostazioni configurate.
