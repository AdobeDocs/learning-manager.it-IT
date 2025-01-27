---
jcr-language: en_us
title: Credendo
description: Informazioni sull'integrazione Creded con ALM per gestire e condividere distintivi esterni dalla piattaforma su vari canali di social media
contentowner: chandrum
exl-id: 168f7ff8-51f5-4962-bf76-af909fc5565b
source-git-commit: f3a0ec693e1a2e75cdad24f91f22a0290d62740d
workflow-type: tm+mt
source-wordcount: '360'
ht-degree: 0%

---

# Credendo

[Creded](https://info.credly.com/) è una piattaforma di credenziale digitale che consente agli Allievi e alle organizzazioni di ottenere, condividere e verificare i risultati professionali, ad esempio distintivi o certificazioni. Gli Allievi possono gestire e condividere i distintivi tramite il proprio profilo Crely sui social media e in altri luoghi.

## Prerequisiti

Configura un account Creded per la tua organizzazione. Aggiungi gli Allievi a Crely utilizzando i loro ID e-mail in Adobe Learning Manager. Ciò consentirà agli Allievi di visualizzare i distintivi su Creded e Adobe Learning Manager.

## Aggiungere il connettore Creded a Adobe Learning Manager

Segui questi passaggi per aggiungere il connettore Creded a Adobe Learning Manager:

1. Accedi come **[!UICONTROL Amministratore dell’integrazione]**.
2. Seleziona **[!UICONTROL In modo credibile]** > **Connetti** per aggiungere il connettore **[!UICONTROL In modo credibile]** a Adobe Learning Manager.

   ![](assets/connector-credly.png)
   _Aggiungi connettore Credly_

3. Digitare **[!UICONTROL Nome connessione]**.
4. Digitare **[!UICONTROL ID organizzazione]** e **[!UICONTROL token di autorizzazione]**.

   >[!NOTE]
   >
   >Ogni badge in Creded è fornito con un ID organizzazione e un token di autorizzazione. Copiate questi valori da Credendo.

5. Digita **[!UICONTROL Nome host]** e seleziona **[!UICONTROL Connetti]**.

## Migrazione dei distintivi da Creded

Il file badge.csv di Adobe Learning Manager consente di migrare i distintivi dai sistemi LMS o dai sistemi esterni esistenti. Il file badge.csv è stato aggiornato con due nuove colonne:

* externalBadgeId
* externalBadgeProvider

L’ID del badge esterno si riferisce all’ID del modello di badge nella piattaforma Creded e il provider del badge esterno è Creded. Aggiungi questi valori in badge.csv e segui i passaggi indicati nel [Manuale di migrazione](https://experienceleague.adobe.com/en/docs/learning-manager/using/integration/migration-manual#migrationprocedure) per migrare il file csv.

## Creare un’abilità - Amministratore

Una volta importato in Adobe Learning Manager, l’amministratore può creare questi distintivi come un’abilità. Per informazioni su come creare un’abilità, consulta [Creare e modificare abilità](https://experienceleague.adobe.com/en/docs/learning-manager/using/admin/skills-levels).

### Assegnare l’abilità/badge all’oggetto di apprendimento: Autore

L’Autore/Amministratore può assegnare questi distintivi ALM importati da Creded a un corso, un percorso di apprendimento o una certificazione (non solo abilità) e sull’utilizzo di questi oggetti di apprendimento, il distintivo verrà ottenuto e può essere visualizzato sull’app Creded e ALM.

Gli Allievi possono accedere a Creded e visualizzare i distintivi nella piattaforma Creded. Da Crely, possono condividere i distintivi su piattaforme esterne come LinkedIn e altri social media.
