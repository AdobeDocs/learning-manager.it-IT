---
jcr-language: en_us
title: Integrazione di Okta Active Directory con Adobe Learning Manager
description: Integrazione di Okta Active Directory con Adobe Learning Manager
contentowner: nluke
source-git-commit: 6abc118c6ad7e66e3ded5bd26b9167c3a0b99e4b
workflow-type: tm+mt
source-wordcount: '548'
ht-degree: 0%

---



# Integrazione di Okta Active Directory con Adobe Learning Manager {#okta-active-directory-integration-with-adobe-learning-manager}

Questo documento descrive come integrare Learning Manager per Adobi con Okta Active Directory (AD). L’integrazione di Learning Manager Adobe con Okta AD consente di:

* Verificare l’accesso dell’utente di Learning Manager a Okta AD.
* Consentire agli utenti di accedere automaticamente ad Adobe Learning Manager con i loro account Okta AD.
* Gestisci i tuoi account in una posizione centrale: il portale Okta.

Adobe Learning Manager supporta l’SSO avviato dal provider di identità (Identity Provider o IdP) e dal fornitore di servizi (Service Provider o SP).

## Creare un’applicazione in OKTA

1. Accedi come Amministratore a Okta AD.
1. Fai clic **[!UICONTROL Applicazioni]**. Viene aperto l’Application Store di Okta.

   ![](assets/cp-application-store.png)

   *Visualizza l&#39;Application Store a Okta*

1. Fai clic **[!UICONTROL Crea Integrazione App]**.

   ![](assets/cp-app-integrations.png)

   *Seleziona Crea integrazione app*

1. Seleziona **[!UICONTROL SAML 2.0]** dalla nuova finestra di integrazione dell’app.

   ![](assets/cp-saml2.0.png)

   *Seleziona l&#39;opzione SAML2.0*

1. Seleziona **[!UICONTROL Crea integrazione SAML]** > **[!UICONTROL Pagina Impostazioni generali]**. Immettere un nome applicazione.

   Può essere un nome qualsiasi per identificare in modo univoco l’applicazione. Al termine, fai clic su **[!UICONTROL Avanti]**.

   ![](assets/cp-saml-integration.png)

   *Immetti il nome dell’applicazione*

1. Esegui i passaggi seguenti nella pagina Configura impostazioni SAML:

   **Per la configurazione IDP:**

   1. Nel campo URL Single Sign-on, digita l’URL: [https://learningmanager.adobe.com/saml/SSO](https://learningmanager.adobe.com/saml/SSO)
   1. Nel campo URL pubblico, digita l’URL: [https://learningmanager.adobe.com](https://learningmanager.adobe.com/)
   1. Nella **Formato ID nome** casella a discesa, seleziona **Indirizzo e-mail**.
   1. Nella **Nome utente applicazione** seleziona il nome utente Okta.
   1. Se si desidera fornire attributi aggiuntivi, è possibile aggiungerli nella sezione **Istruzione Attributes** (Facoltativo)

   ![](assets/cp-saml-integration-step1.png)

   *Aggiungi attributi SAML*

   **Per la configurazione SP:**

   1. Nel campo URL Single Sign-on, digita l’URL: [https://learningmanager.adobe.com/saml/SSO](https://learningmanager.adobe.com/saml/SSO)
   1. Nel campo URL pubblico, digita l’URL: [https://learningmanager.adobe.com](https://learningmanager.adobe.com/)
   1. Nella casella a discesa Formato ID Nome, seleziona **Indirizzo e-mail**.
   1. Nel menu a discesa Nome utente applicazione, seleziona Nome utente Okta.
   1. Fai clic su **Mostra impostazioni avanzate**.
   1. Sotto **Algoritmo di firma**, selezionare RSA-SHA256
   1. Nella **Algoritmo di asserzione**, seleziona SHA256
   1. Nella **Crittografia delle asserzioni** selezionare **Crittografato**.

   1. Nella **Certificato di crittografia** , carica il file di certificato condiviso da Adobe.
   1. Se si desidera fornire attributi aggiuntivi, è possibile aggiungerli nella sezione **Istruzione Attributes** (Facoltativo).

   ![](assets/cp-saml-integration-step2.png)

   *Aggiungere attributi aggiuntivi*

   Al termine, fai clic su **[!UICONTROL Avanti]**.

1. La **Feedback**  è opzionale. Dopo aver selezionato le opzioni e fornito il tuo feedback, fai clic su **[!UICONTROL Fine]**.

   ![](assets/cp-saml-integration-step3.png)

   *Completare la configurazione SAML*

## Estrarre l’URL e il file di metadati avviati da IDP

Per visualizzare l’URL e il file di metadati avviati da IdP/SP, effettua le operazioni riportate di seguito:

1. Apri l’applicazione creata.
1. Sotto il **Single Sign-On** , fare clic su **[!UICONTROL Visualizza istruzioni]**.

   ![](assets/cp-prime-sso.png)

   *Seleziona la scheda SSO*

   **Per IDP:**

   1. L’URL Single Sign-On del provider di identità è l’URL avviato dall’IdP.
   1. Copia tutto il testo presente sotto **Facoltativo** campo.
   1. Aprite un nuovo documento di blocco note e incollate il testo copiato.
   1. Fai clic **[!UICONTROL File]** > **[!UICONTROL Salva con nome]** > &quot;nomefile.xml&quot;. Questo sarà il file di metadati.

   **Per SP:**

   1. L’URL Single Sign-On del provider di identità è l’URL avviato dall’IdP.
   1. L’emittente del provider di identità è l’ID entità.
   1. Copia tutto il testo presente sotto **Facoltativo** campo.
   1. Aprite un nuovo documento di blocco note e incollate il testo copiato.
   1. Fai clic **[!UICONTROL File]** > **[!UICONTROL Salva con nome]** > **[!UICONTROL nomefile.xml]**. Questo sarà il file di metadati.

   ![](assets/cp-saml-integration-step4.png)

   *Salva file XML SP*

   È necessario salvare il file in formato XML.

## Configurazione dell’SSO di Adobe Learning Manager

Per configurare l’Adobe SSO di Learning Manager, esegui i passaggi descritti nell’articolo seguente.

<!--

article not in TOC

[SSO Authentication](/help/migrated/kb/sso-authentication-for-learning-manager.md)
-->