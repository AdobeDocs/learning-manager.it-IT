---
jcr-language: en_us
title: L’utente viene eliminato automaticamente in Learning Manager
description: Un utente viene eliminato da Learning Manager, ma l’Amministratore non ha mai eseguito alcuna azione di questo tipo.
contentowner: nluke
source-git-commit: 66dfaaaf723382eada39e2be29dfd49b795107a0
workflow-type: tm+mt
source-wordcount: '234'
ht-degree: 0%

---



# L’utente viene eliminato automaticamente in Learning Manager {#user-gets-auto-deleted-in-learning-manager}

## Problema

Un utente viene eliminato da Learning Manager, ma l’Amministratore non ha mai eseguito alcuna azione di questo tipo.

## Causa

Nell’Adobe di Learning Manager, è disponibile un’opzione che consente di eliminare un utente che non effettua l’accesso al sistema da un certo periodo di tempo.

## Come si modifica/applica l’impostazione?

### Per Allievi interni

1. Accedi come **Amministratore**.
1. Sotto **Configura**, fare clic su **Impostazioni** > **Generale**.
1. Nella pagina Impostazioni generali, consulta le opzioni disponibili. **Elimina automaticamente utenti interni**.
1. Fai clic **[!UICONTROL Modifica]** per immettere il numero di giorni nel campo, per eliminare automaticamente un Allievo che non ha effettuato l’accesso al sistema.

   ![](assets/cp-autodelete-internal.png)

   *Modifica il numero di giorni*

>[!NOTE]
>
>   Lascia il campo vuoto se non desideri eliminare automaticamente gli utenti.


1. Fai clic **[!UICONTROL Salva]** per mantenere le impostazioni configurate.

### Per Allievi esterni:

1. Accedi come **Amministratore**.
1. Sotto **Gestisci**, fare clic su **[!UICONTROL Utenti]** > **[!UICONTROL Esterno]**.
1. Fai clic sul nome di un utente esterno per il quale è necessario applicare l’impostazione.

   Viene aperto il **Modifica profilo di registrazione esterno** finestra.

1. Fai clic **[!UICONTROL Impostazioni avanzate]** nell’angolo in basso a sinistra.

   ![](assets/cp-autodelete-external.png)

   *Seleziona l’opzione Impostazioni avanzate*

1. Nella **Requisiti di accesso** immetti il numero di giorni per l’eliminazione automatica di un allievo che non ha effettuato l’accesso al sistema.
1. Fai clic **[!UICONTROL Salva]** per mantenere le impostazioni configurate.
