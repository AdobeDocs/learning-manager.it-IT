---
description: Ulteriori informazioni su come le impostazioni di integrazione collegano Adobe Learning Manager a soluzioni di terze parti
jcr-language: en_us
title: Impostazioni di integrazione in Adobe Learning Manager
source-git-commit: 03123dcd8d9066cdfcb0fe97e61acb3df625a23e
workflow-type: tm+mt
source-wordcount: '616'
ht-degree: 2%

---


# Impostazioni di integrazione in Adobe Learning Manager

## Metodi di accesso

Adobe Learning Manager offre diversi metodi di accesso per garantire un accesso sicuro e flessibile per utenti interni ed esterni. Gli amministratori possono configurare questi metodi di accesso in base ai requisiti dell’organizzazione.

I metodi di accesso disponibili sono:

* ID ADOBE LEARNING MANAGER
* Adobe ID
* Single Sign-On

### Utenti interni

La sezione Utenti interni consente di configurare le opzioni di accesso specifiche per gli utenti interni. Gli utenti interni possono accedere all’account utilizzando Adobe ID o Single Sign-On (SSO).

**Adobe ID:**

* Gli utenti interni possono accedere utilizzando le proprie credenziali Adobe ID.
* Ideale per le organizzazioni che già utilizzano i servizi Adobe.

**Single Sign-On (SSO):**

* Consente agli utenti interni di utilizzare il provider di identità (IdP) dell’organizzazione.
* Supporta l’autenticazione basata su SAML 2.0 per un’esperienza di accesso uniforme.

Per consentire gli accessi SSO per gli utenti interni, seleziona Abilita SSO multipli per l’accesso e inizia a configurare SSO.

Il **[!UICONTROL campo attivo SSO]** in Adobe Learning Manager viene utilizzato per mappare le configurazioni Single Sign-On (SSO) a attributi o gruppi di utenti specifici. Puoi configurare questo campo per abilitare più configurazioni SSO per gli utenti interni in base alla loro organizzazione, posizione o altri criteri.

### Utenti esterni

La sezione Utenti esterni di Adobe Learning Manager consente di gestire gli Allievi esterni, come partner o agenzie, che richiedono un accesso limitato all’account Adobe Learning Manager. Questa sezione fornisce strumenti per creare profili di registrazione, gestire gruppi di utenti esterni e configurare impostazioni specifiche per gli Allievi esterni.

Gli utenti esterni possono accedere come segue:

* Adobe ID: gli utenti esterni possono accedere utilizzando le proprie credenziali Adobe ID.
* Single Sign-On (SSO): gli utenti esterni possono accedere tramite SSO se configurato dall&#39;amministratore.
* ID Adobe Learning Manager: gli utenti esterni possono creare un nome utente e una password di Learning Manager per accedere alla piattaforma.

**Punti chiave:**

* Puoi abilitare uno o più metodi di accesso per gli utenti esterni.
* Se si seleziona Adobe Learning Manager ID, gli utenti esterni devono creare le proprie credenziali.
* SSO può essere configurato per utenti esterni in base alle esigenze dell&#39;organizzazione.

### Configurazione SSO in Adobe Learning Manager

Adobe Learning Manager supporta Single Sign-On (SSO) per consentire agli utenti di autenticarsi una volta sola e di accedere a più applicazioni. Gli amministratori possono configurare SSO per utenti interni ed esterni utilizzando provider basati su SAML 2.0.

Per ulteriori informazioni, vedere [Accessi SSO in Adobe Learning Manager](/help/migrated/administrators/feature-summary/multiple-sso-logins.md).

>[!NOTE]
>
>* È possibile aggiungere fino a 20 configurazioni SSO a un account.
>* Contatta il supporto di Adobe per assistenza con i provider SSO basati su SAML 2.0.

## Origini dati

Le origini dati consentono agli utenti o agli amministratori di integrazione di integrare sistemi esterni per l’importazione e la sincronizzazione di dati di utenti e apprendimento. Questa funzione garantisce una gestione e una sincronizzazione dei dati senza interruzioni con sistemi quali HRMS, Salesforce, FTP e altri.

**Esempi di tipi di origini dati**

* **Connettori FTP**: le origini dati basate su FTP consentono alle organizzazioni di caricare file di dati utente direttamente in Adobe Learning Manager tramite protocolli di trasferimento file protetti. Queste connessioni sono particolarmente utili per l’importazione in batch di informazioni utente, iscrizioni ai corsi e altre operazioni relative ai dati in blocco.
* **Integrazioni di terze parti**: Adobe Learning Manager supporta l’integrazione con vari sistemi aziendali tramite connettori predefiniti. Queste integrazioni possono includere sistemi di gestione delle risorse umane, piattaforme di gestione delle relazioni con i clienti e altri sistemi di gestione dell’apprendimento.
*** Integrazione Salesforce**: il connettore Salesforce consente la sincronizzazione diretta tra Salesforce e Adobe Learning Manager dei dati utente, delle informazioni sui corsi e dei record di apprendimento.

Per ulteriori informazioni, vedere [Connettori in Adobe Learning Manager](/help/migrated/integration-admin/feature-summary/connectors.md).

## Account condivisi tra pari

Gli account condivisi tra pari in Adobe Learning Manager consentono di condividere le postazioni acquistate e visualizzare i report tra gli account associati. Questa funzione è utile per le organizzazioni che devono collaborare o condividere risorse tra account diversi.

Per ulteriori informazioni, consulta [Account condivisi tra pari](/help/migrated/administrators/feature-summary/peer-account.md) in Adobe Learning Manager.





