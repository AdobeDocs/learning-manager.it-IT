---
jcr-language: en_us
title: Aggiungere utenti in blocco
description: Scopri come aggiungere più utenti alla volta.
contentowner: saghosh
source-git-commit: 46afb6603456ced9d7e2aaf98d07ec92fee30c0b
workflow-type: tm+mt
source-wordcount: '286'
ht-degree: 0%

---



# Aggiungere utenti in blocco

Sì, puoi aggiungere più utenti alla volta procedendo come segue:

1. Fai clic **[!UICONTROL Utenti]** nel riquadro a sinistra nell’accesso come Amministratore, quindi fai clic su **[!UICONTROL Aggiungi]** > **[!UICONTROL Carica un file CSV]**. Viene visualizzata una finestra a comparsa.

1. Puoi aggiungere più utenti utilizzando un file .CSV. Fai clic **[!UICONTROL Importa]** e seleziona/apri il file .csv dal computer.

1. Dopo aver importato il file, mappa il contenuto del file .csv con le etichette dell’applicazione quando carichi per la prima volta il file .csv.

   Per tutti i caricamenti successivi, vengono considerate le impostazioni precedenti per le etichette. Fai clic **[!UICONTROL Salva]** dopo aver completato la mappatura dei dati e fare clic su **[!UICONTROL Aggiungi]** per caricare il file .csv mappato.

1. Fai clic **[!UICONTROL Salva]** dopo aver completato la mappatura dei dati e fare clic su **[!UICONTROL Aggiungi]** per caricare il file .csv mappato.

## Caricamento di file CSV con campi obbligatori {#csvuploadwithmandatoryfields}

Non è obbligatorio aggiungere il profilo utente e l’ID e-mail del Manager nel file CSV. Gli unici campi obbligatori sono il nome utente e l’ID e-mail dell’utente.

In questo caso, per impostazione predefinita, l’Amministratore dell’azienda viene considerato il Manager degli utenti. Per impostazione predefinita, il dipendente è considerato il profilo dell&#39;utente.

**CSV di esempio**

Di seguito è disponibile un file CSV di esempio per Learning Manager con campi obbligatori.
[Sample-CSV-name-email.zip](assets/sample-csv-name-email.zip)

## Caricamento di file CSV con tutti i campi {#csvuploadwithallthefields}

Prima di includere l’ID e-mail del Manager per qualsiasi dipendente, assicurati che il Manager sia stato aggiunto come dipendente nel file CSV. Ad esempio, fai riferimento al nome del dipendente, Howard Walters, nell’immagine seguente:

![](assets/csv-example.png)

*Modello CSV da caricare*

Inoltre, gli Amministratori di un’organizzazione possono aggiungersi come dipendenti e menzionare l’ID e-mail del proprio Manager come root.

**CSV di esempio**

Di seguito è disponibile un file CSV di esempio per Learning Manager con tutti i campi.
[learning-manager-sample-csv.zip](assets/learning-manager-sample-csv.zip).

Fare riferimento a  [Utilizzo del caricamento di file CSV](/help/migrated/administrators/feature-summary/add-users-user-groups.md) per ulteriori informazioni, consultare la guida alle funzionalità.
