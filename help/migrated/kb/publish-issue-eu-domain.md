---
jcr-language: en_us
title: Non è possibile pubblicare sul dominio UE di Learning Manager
description: Impossibile pubblicare da Adobe Captivate sul dominio UE di Adobe Learning Manager in Adobe Learning Manager.
contentowner: nluke
source-git-commit: 69ac8f8ce5a0c077f31569571f9d9fbf16ecb943
workflow-type: tm+mt
source-wordcount: '246'
ht-degree: 83%

---



# Non è possibile pubblicare sul dominio UE di Learning Manager {#unable-to-publish-to-learning-manager-eu-domain}

## Il problema

Non è possibile pubblicare da Adobe Captivate sul dominio UE di Adobe Learning Manager.

## Errore

Nessun account trovato

## Descrizione

In alcuni casi, gli autori provano a pubblicare un corso da Adobe Captivate su Adobe Learning Manager. Tuttavia, non possono farlo poiché visualizzano il messaggio di errore &quot;Nessun account trovato&quot;.

## Causa

Questo problema si verifica quando, per impostazione predefinita, Adobe Captivate è configurato per la pubblicazione di contenuti sul dominio statunitense di Adobe Learning Manager.

## Risoluzione:

Da notare:

* Se aperta, chiudi l’applicazione Adobe Captivate.
* Per eseguire la procedura riportata di seguito, devi disporre dell’accesso come Amministratore sul tuo computer. Se non disponi dell’accesso come Amministratore, contatta il team IT per ricevere assistenza.

Esegui la procedura riportata di seguito:

1. Accedi alla directory di installazione di Adobe Captivate.

   Ad esempio,  `kbd C:\\Program Files\\Adobe\\Adobe Captivate 2019 x64` (2019 è la versione di Captivate. Questo cambia se si utilizza una versione diversa di Adobe Captivate).

1. Copia il file di configurazione **AdobeCaptivate.ini** sul desktop.

   ![](assets/cp-captivate.ini.png)
   *Visualizzare il file di configurazione*

1. Apri il file copiato dal desktop su un file di Blocco note.
1. Modifica il valore di LearningManagerBaseUrl = `https://learningmanager.adobe.com/inappstarter` to LearningManagerBaseUrl = `https://learningmanagereu.adobe.com/inappstarter`

   ![](assets/cp-primebaseurl.png)
   *Visualizza PrimeBaseURL*

1. Salva le modifiche apportate al file di Blocco note.
1. Copia il file modificato e salvato, quindi incollalo nuovamente nel percorso del file. Sostituisci il file originale in  `kbd C:\\Program Files\\Adobe\\Adobe Captivate 2019 x64`
1. Una volta completata la procedura, avvia Adobe Captivate e prova a pubblicare su Adobe Learning Manager.
