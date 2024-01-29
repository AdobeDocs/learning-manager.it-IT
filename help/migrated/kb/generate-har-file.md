---
description: Continua a leggere per scoprire come generare file HAR su Google Chrome.
jcr-language: en_us
title: Generare un file HAR
contentowner: dvenkate
source-git-commit: ec79aa3dd6225cc424721afb50702963c1b125eb
workflow-type: tm+mt
source-wordcount: '158'
ht-degree: 0%

---



# Generare un file HAR

Continua a leggere per scoprire come generare file HAR su Google Chrome.

Per generare un file HAR, effettua le seguenti operazioni:

1. Apri una finestra di Google Chrome e apri una nuova scheda.
1. Apri gli strumenti per sviluppatori per la pagina, quindi fai clic con il pulsante destro del mouse su > Inspect.
1. Apri il pannello **[!UICONTROL Rete]** scheda. Assicurati che il pulsante di registrazione rosso sia attivo. Abilita **[!UICONTROL Mantieni registro]** casella di controllo.

   ![](assets/preserve-log-checkbox.png)

   *Seleziona la casella di controllo Mantieni registro nella scheda Rete.*

1. Accedi a [Learning Manager](https://learningmanager.adobe.com/acapindex.html) utilizzando le tue credenziali e seguire il corso. Esegui tutte le operazioni che provocheranno il problema.
1. Negli strumenti per sviluppatori, fai clic con il pulsante destro del mouse e seleziona **Salva tutto come HAR con contenuto**.

   In alcune versioni di Google Chrome, potrebbe essere necessario selezionare **[!UICONTROL Copia]** > **[!UICONTROL Copia tutto come HAR]**.

   ![](assets/copy-hra.png)

   *Copia tutti i file HAR*

1. Incollate il contenuto copiato in un file di blocco note. Salva sul desktop con nome **logs.har** e invialo tramite e-mail all&#39;Adobe.
