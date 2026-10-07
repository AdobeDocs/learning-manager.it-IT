---
description: Questo documento consente di configurare l’autenticazione SSO per accedere all’account Learning Manager.
jcr-language: en_us
title: Accesso a Learning Manager tramite autenticazione SSO
contentowner: dvenkate
exl-id: ef5ab232-0a87-4f76-8dfd-b2497f360cbe
product_v2:
  - id: ed12e5b7-96e3-45e7-a17f-de222065ebcb
    internal-label: Learning Manager
source-git-commit: c061ccbefe8d40154220587796062d335e35de77
workflow-type: tm+mt
source-wordcount: '135'
ht-degree: 68%
---
# Accesso a Learning Manager tramite autenticazione SSO

Questo documento consente di configurare l’autenticazione SSO per accedere all’account Learning Manager.

Per configurare l’autenticazione SSO, esegui i passaggi seguenti:

1. Apri **[!UICONTROL Impostazioni]** > **[!UICONTROL Metodi di accesso.]**

   ![](assets/login-methods.png)

1. Scegli **[!UICONTROL Utenti interni]** o **[!UICONTROL Utenti esterni]** a seconda delle necessità.
1. Fai clic sul menu a discesa accanto all&#39;opzione **[!UICONTROL accesso]** e seleziona **[!UICONTROL Single Sign-On]**.

   ![](assets/single-sign-on.png)

1. Per modificare le impostazioni Single Sign-On (SSO), fai clic su **[!UICONTROL Modifica.]**

   ![](assets/change.png)

1. Immetti l&#39;**[!UICONTROL URL di autenticazione avviato da IDP]** fornito dal tuo provider di servizi e carica il file XML facendo clic sul **[!UICONTROL file XML dei metadati IDP.]**

   ![](assets/sso-configuration.png)

   L’SSO configurato in Learning Manager deve supportare SAML 2.0.

   Ora puoi accedere a Learning Manager tramite l’autenticazione SSO.
