---
jcr-language: en_us
title: Assegnazione predefinita dei ruoli di istruttore nei gruppi di utenti in Learning Manager
description: Assegnazione predefinita dei ruoli di istruttore nei gruppi di utenti in Learning Manager
contentowner: nluke
preview: true
source-git-commit: 66dfaaaf723382eada39e2be29dfd49b795107a0
workflow-type: tm+mt
source-wordcount: '300'
ht-degree: 48%

---



# Assegnazione predefinita dei ruoli di istruttore nei gruppi di utenti in Learning Manager

## Problema

A tutti gli utenti che partecipano a una sessione viene assegnato il ruolo di istruttore.

## Descrizione

Esistono scenari in cui una sessione potrebbe richiedere più istruttori o altri in cui un Amministratore/Autore potrebbe assegnare un gruppo di utenti a una sessione. In questi casi, a tutti gli utenti del gruppo viene assegnato il ruolo di istruttore.

## Causa

Poiché i ruoli non possono essere suddivisi durante l’assegnazione in blocco degli utenti in un gruppo, il ruolo di istruttore viene assegnato a tutti gli utenti.

## Soluzione

Crea gruppi di utenti personalizzati per filtrare i ruoli utente assegnati a una sessione. Per rimuovere i ruoli di istruttore assegnati a un gruppo di utenti, effettua le seguenti operazioni:

1. Accedi come Amministratore. Nel pannello a sinistra, fai clic su **[!UICONTROL Modelli e-mail]**.
1. Per evitare che vengano attivati i messaggi e-mail per le modifiche da apportare, fai clic su **[!UICONTROL Disattiva tutto]**.

   ![](assets/instructor-disable-all.png)

1. Passa a **Utenti** > **Gruppo di utenti**. Fai clic su **[!UICONTROL Aggiungi]**.

   ![](assets/instructor-usergroups.png)

1. Crea un gruppo di utenti personalizzato nella finestra Aggiungi gruppo di utenti come indicato di seguito:

   * Immettere un nome per il gruppo personalizzato nel campo **[!UICONTROL Nome]**.
   * Nel campo **[!UICONTROL Includi Allievi]**, aggiungi il gruppo di utenti a cui non vuoi assegnare il ruolo di istruttore.
   * Nel campo **[!UICONTROL Escludi Allievi]**, aggiungi gli utenti per i quali desideri mantenere il ruolo di istruttore.

   ![](assets/instructor-add-ug.png)

   Con questi passaggi hai creato un elenco di utenti nel gruppo &quot;Includi&quot; e hai rimosso degli utenti specifici (che rimarranno istruttori) inserendoli nel gruppo &quot;Escludi&quot;.

1. Fai clic su **[!UICONTROL Salva]** le modifiche apportate.
1. Cerca il gruppo di utenti personalizzato creato andando su **[!UICONTROL Utenti]** > **[!UICONTROL Interni]**.

   ![](assets/instructor-custom-ug.png)

1. Fai clic sulla casella di controllo per selezionare tutti gli utenti del gruppo.

   ![](assets/instructor-bulk-ug.png)

1. Fai clic su **[!UICONTROL Azioni]** > **[!UICONTROL Rimuovi ruolo]** > **[!UICONTROL Rimuovi istruttore]**.

Assicurati che le eventuali e-mail disattivate nel passaggio 2 vengano riattivate a procedura completata.
