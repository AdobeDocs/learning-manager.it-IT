---
jcr-language: en_us
title: Aggiunta di utenti in blocco
description: Scopri come aggiungere più utenti alla volta.
contentowner: saghosh
exl-id: c3309ce5-8764-452e-82d5-5637c23c661b
source-git-commit: 96602899dd76eae14a6b7e1808d529756657e7b8
workflow-type: tm+mt
source-wordcount: '341'
ht-degree: 22%

---

# Aggiunta di utenti in blocco

>[!INFO]
>
>In questo corso imparerai come aggiungere utenti in blocco tramite un file CSV.<br><br>[![pulsante](feature-summary/assets/launch-training-button.png)](https://content.adobelearningmanageracademy.com/app/learner?accountId=98632#/course/7555555)</br></br>

Se non è possibile avviare il corso di formazione, scrivere a <almacademy@adobe.com>.

## Come aggiungere più utenti

Puoi aggiungere più utenti alla volta procedendo come segue:

1. Fai clic su **[!UICONTROL Utenti]** nel riquadro a sinistra nell’accesso come Amministratore, quindi fai clic su **[!UICONTROL Aggiungi]** > **[!UICONTROL Carica un file CSV]**. Viene visualizzata una finestra a comparsa.

1. Puoi aggiungere più utenti utilizzando un file .CSV. Fai clic su **[!UICONTROL Importa]** e seleziona/apri il file .csv dal computer.

1. Dopo aver importato il file, mappa il contenuto del file .csv con le etichette dell’applicazione quando carichi per la prima volta il suddetto file.

   Per tutti i caricamenti successivi, vengono considerate le impostazioni precedenti per le etichette. Dopo aver completato la mappatura dei dati, fai clic su **[!UICONTROL Salva]**, quindi su **[!UICONTROL Aggiungi]** per caricare il file .csv mappato.

1. Dopo aver completato la mappatura dei dati, fai clic su **[!UICONTROL Salva]**, quindi su **[!UICONTROL Aggiungi]** per caricare il file .csv mappato.

## Caricamento di file CSV con campi obbligatori {#csvuploadwithmandatoryfields}

Non è obbligatorio aggiungere il profilo utente e l’ID e-mail del Manager nel file CSV. Gli unici campi obbligatori sono il nome utente e l’ID e-mail dell’utente.

In questo caso, per impostazione predefinita, l’Amministratore dell’azienda viene considerato il Manager degli utenti. Per impostazione predefinita, il dipendente è considerato il profilo dell&#39;utente.

>[!NOTE]
>
>Per aggiungere nuovi utenti, crea un nuovo file CSV con i relativi dettagli e caricalo. L&#39;aggiornamento e il nuovo caricamento di un file CSV esistente non è supportato.

**File CSV di esempio**

Di seguito è disponibile un file CSV di esempio per Learning Manager con campi obbligatori.
[Nome-CSV-campione-email.zip](assets/sample-csv-name-email.zip)

## Caricamento di file CSV con tutti i campi {#csvuploadwithallthefields}

Prima di includere l’ID e-mail del Manager per qualsiasi dipendente, assicurati che il Manager sia stato aggiunto come dipendente nel file CSV. Ad esempio, fai riferimento al nome del dipendente, Howard Walters, nell’immagine seguente:

![](assets/csv-example.png)

*Modello CSV per il caricamento*

Inoltre, gli amministratori di un&#39;organizzazione possono aggiungere **se stessi** come dipendenti e menzionare l&#39;ID e-mail del proprio Manager come root.

**File CSV di esempio**

Di seguito è disponibile un file CSV di esempio per Learning Manager con tutti i campi.
[learning-manager-sample-csv.zip](assets/learning-manager-sample-csv.zip).

Per ulteriori informazioni, fai riferimento al contenuto della guida della funzionalità [Utilizzo del caricamento CSV](/help/migrated/administrators/feature-summary/add-users-user-groups.md).
