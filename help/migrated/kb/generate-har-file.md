---
description: Continua a scoprire come generare file HAR in Google Chrome.
jcr-language: en_us
title: Generazione di un file HAR
contentowner: dvenkate
source-git-commit: ec79aa3dd6225cc424721afb50702963c1b125eb
workflow-type: tm+mt
source-wordcount: '158'
ht-degree: 57%

---



# Generazione di un file HAR

Continua a scoprire come generare file HAR in Google Chrome.

Per generare un file HAR, attieniti alla seguente procedura:

1. Apri una finestra di Google Chrome e apri una nuova scheda.
1. Apri gli strumenti per sviluppatori per la pagina e fai clic con il tasto destro del mouse su Ispeziona Elemento.
1. Apri la scheda **[!UICONTROL Rete]**. Assicurati che il pulsante di registrazione rosso sia attivo. Abilita **[!UICONTROL Mantieni registro]** casella di controllo.

   ![](assets/preserve-log-checkbox.png)

   *Seleziona la casella di controllo Mantieni registro nella scheda Rete.*

1. Accedi a [Learning Manager](https://learningmanager.adobe.com/acapindex.html) usando le tue credenziali e segui il corso. Esegui tutte le operazioni che provocheranno il problema.
1. Negli strumenti per sviluppatori, fai clic con il pulsante destro del mouse e seleziona **Salva tutto come HAR con contenuto**.

   In alcune versioni di Google Chrome, potrebbe essere necessario selezionare **[!UICONTROL Copia]** > **[!UICONTROL Copia tutto come HAR]**.

   ![](assets/copy-hra.png)

   *Copia tutti i file HAR*

1. Incolla il contenuto copiato in un file di blocco note. Salva sul desktop con nome **logs.har** e invialo tramite e-mail all&#39;Adobe.
