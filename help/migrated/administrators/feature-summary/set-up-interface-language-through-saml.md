---
description: Scopri come configurare la lingua dell’interfaccia con SAML
jcr-language: en_us
title: Configurazione della lingua dell’interfaccia tramite SAML
contentowner: chandrum
exl-id: 726cb45e-1c37-42b1-924a-565c84c82852
source-git-commit: 7b84a4565ccf109ed4789f4963d6e250f5d0a852
workflow-type: tm+mt
source-wordcount: '765'
ht-degree: 0%

---

# Configurazione della lingua dell’interfaccia tramite SAML

Adobe Learning Manager (ALM) ora accetta un attributo SAML per la lingua. Questo attributo viene quindi mappato alle impostazioni dell&#39;interfaccia utente e del linguaggio dei contenuti, garantendo un&#39;interazione uniforme con l&#39;LMS nella lingua preferita. La configurazione di queste impostazioni della lingua viene gestita tramite la piattaforma Identity and Access Management (IAM), utilizzando SAML per Single Sign-On (SSO). Ciò supporta sia gli accessi avviati dal provider di servizi (SP) che quelli avviati dal provider di identità (IdP), consentendo agli utenti di visualizzare l&#39;interfaccia e il contenuto nella lingua scelta. Il flusso di lavoro è il seguente:

1. Creare l’applicazione a Okta
2. Aggiungere un utente a Okta
3. Configurazione di SSO in ALM

## Creare l’applicazione a Okta

Per creare un’applicazione a Okta, effettua le seguenti operazioni:

1. Crea un account sviluppatore a Okta utilizzando l&#39;e-mail della tua azienda e accedi al tuo account.
2. Seleziona **[!UICONTROL Applicazioni]** > **[!UICONTROL Crea Integrazione App]**.
3. Seleziona **[!UICONTROL SAML 2.0]** e quindi **[!UICONTROL Next]**.
4. Digita un nome per l’applicazione e seleziona Avanti.
5. Configura i seguenti campi:

   * **[!UICONTROL URL Single Sign-On]**: digita l&#39;URL di dominio specifico a cui vuoi collegare l&#39;applicazione (ad esempio, [https://learningmanagerstage.adobe.com/saml/SSO](https://learningmanagerstage.adobe.com/saml/SSO)). Se necessario, modifica l&#39;URL dell&#39;ambiente.
   * **[!UICONTROL URI pubblico (ID entità SP)]**: utilizzare lo stesso URL di ambiente precedente.
   * **[!UICONTROL Formato ID nome]**: seleziona l&#39;indirizzo e-mail.
   * **[!UICONTROL Nome utente applicazione]**: selezionare il nome utente Okta.

6. In Istruzioni attributo, aggiungi i seguenti campi (o campi aggiuntivi in base alle esigenze):
   * **Nome**: lingua
   * **Formato Nome**: Non Definito
   * **Valore**: user.locale

7. Seleziona Avanti e quindi seleziona Fine.
8. Al termine, scorri verso il basso fino a Certificati di firma SAML:

   * Trovare la riga in cui lo stato è **[!UICONTROL Attivo]**.
   * Selezionare **[!UICONTROL Azioni]** > **[!UICONTROL Visualizza metadati IdP]**.
   * Verrà aperto un file XML in una nuova scheda. Copiate il codice XML e salvatelo come file .xml localmente.

## Aggiungere un utente a Okta

Per creare un utente a Okta, effettua le seguenti operazioni:

1. Seleziona **[!UICONTROL Directory]** > **[!UICONTROL Persone]**, quindi seleziona **[!UICONTROL Aggiungi persona]**.
2. Digitare i dettagli necessari per l&#39;utente e selezionare **[!UICONTROL Salva]**.
3. Cerca e seleziona il nome utente del nuovo utente.
4. Selezionare **[!UICONTROL Assegna applicazione]**.
5. Seleziona l&#39;applicazione creata in precedenza, quindi seleziona **[!UICONTROL Salva]**.
6. Individua il profilo dell&#39;utente e seleziona **[!UICONTROL Modifica]**.
7. Nel campo delle impostazioni internazionali, digita il valore richiesto (ad esempio, fr_FR, en_US) e seleziona **[!UICONTROL Salva]**.

## Configurazione di SSO in ALM

Per configurare l&#39;SSO in ALM, segui questi passaggi:

1. Accedi come Amministratore.
2. Selezionare **[!UICONTROL Impostazioni]** > **[!UICONTROL Metodi Di Accesso]**.
3. Vai alla scheda **[!UICONTROL Configurazione Single Sign-On (SSO)]**.
4. Seleziona **[!UICONTROL Aggiungi nuova configurazione SSO]**.

   ![](assets/sso-add.PNG)
   _Aggiungi SSO in ALM_

5. Configura i seguenti dettagli e seleziona Salva.
   * Digitare un nome per la configurazione.
   * Seleziona **[!UICONTROL IDP avviato]** dal menu a discesa **[!UICONTROL Impostazioni Single Sign-On (SSO)]**.
   * Per **[!UICONTROL URL di autenticazione avviata da IDP]**:

      * Aprite il file XML dei metadati scaricato in precedenza.
      * Cercate il valore della posizione e copiatelo.
      * Incolla questo valore nel campo URL di autenticazione avviata da IDP.

   * Per **[!UICONTROL File XML dei metadati]**: carica il file .xml scaricato in precedenza.

6. Torna alla scheda **[!UICONTROL Configurazione]**.
7. Dal menu a discesa, seleziona **[!UICONTROL Configurazione Single Sign-On]**.
8. Nel menu a discesa **[!UICONTROL Installazione SSO]**, seleziona il nome della configurazione creata in precedenza.
9. Seleziona **[!UICONTROL Salva]**.

## Accesso utente e impostazione della lingua

Quando un utente accede utilizzando le credenziali tramite SSO, l&#39;attributo della lingua passato dall&#39;IDP viene mappato all&#39;interfaccia utente e ai campi della lingua del contenuto in ALM. Le impostazioni della lingua vengono applicate immediatamente nell’interfaccia utente e nel contenuto, senza che sia necessario memorizzare i dati nella cache.

Gli utenti possono aggiornare manualmente le impostazioni della lingua nella sezione profilo utente. Queste preferenze della lingua aggiornate manualmente rimarranno attive e non verranno sostituite dalle impostazioni dell&#39;IDP durante i futuri accessi.

Se un utente viene eliminato tramite software da ALM, le impostazioni della lingua verranno mantenute nel database. Quando lo stesso utente viene aggiunto di nuovo, verrà ripristinata la lingua impostata in precedenza.

Gli amministratori possono controllare i report Attività utente, Riepilogo apprendimento e Dashboard di conformità per dettagli specifici della lingua.

## Aggiornamento delle preferenze della lingua utente all&#39;accesso tramite SAML

Adobe Learning Manager è una piattaforma multilingue che supporta le preferenze linguistiche degli Allievi in diversi modi, tramite l’interfaccia, i contenuti e i moduli del corso, tutti disponibili in più lingue.

Con questo miglioramento, Adobe Learning Manager migliora il provisioning just-in-time degli utenti della piattaforma nativa. Quando i nuovi utenti creano account e accedono per la prima volta, le loro preferenze di lingua vengono acquisite e applicate correttamente automaticamente.

### Vantaggi principali

* Aggiorna automaticamente le preferenze della lingua degli utenti durante l&#39;accesso.
* Fornisce un&#39;esperienza personalizzata visualizzando l&#39;interfaccia e il contenuto nella lingua preferita dell&#39;utente.
* Si integra perfettamente con il processo di autenticazione SAML.

Quando gli utenti accedono tramite SAML, la preferenza della lingua (Interface and Content Language) viene controllata e aggiornata in base alle informazioni fornite durante il processo di accesso.

La funzione si integra con il processo di accesso SAML per acquisire e aggiornare senza problemi la preferenza della lingua dell&#39;utente.
