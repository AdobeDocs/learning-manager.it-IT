---
description: Scopri come condividere un URL di menu non connesso per ogni profilo di registrazione autonoma in modo che gli utenti esterni si uniscano al profilo corretto in Adobe Learning Manager
jcr-language: en_us
title: Utilizza un URL di menu non connesso per la registrazione autonoma
exl-id: c4b3f1f5-a785-45ab-b820-621dae16526d
source-git-commit: 8cf3817fc740f8a0219ca6b4f3fe6c637633c955
workflow-type: tm+mt
source-wordcount: '591'
ht-degree: 0%
---

# Utilizza un URL di menu non connesso per la registrazione autonoma

I profili di registrazione autonoma consentono agli utenti esterni, come partner o membri di più organizzazioni, di creare i propri account in Adobe Learning Manager. Ora puoi condividere un URL del menu per ciascun profilo di registrazione autonoma, senza aver effettuato l’accesso. Il menu è integrato in Experience Builder.

Quando gli utenti selezionano **Registrati** da una pagina raggiunta tramite tale URL, Adobe Learning Manager li aggiunge al profilo a cui appartiene l&#39;URL. Ciò consente di mantenere gli utenti di organizzazioni diverse, ad esempio agenzie o società partner diverse, in profili separati.

In precedenza, un URL di pagina non connesso aggiungeva sempre nuovi utenti al profilo selezionato in **Branding**. L’URL del menu senza accesso rimuove questa limitazione: ogni profilo ha un proprio URL e tutti gli URL aprono la stessa pagina di destinazione.

## Prima di iniziare

1. Crea il menu senza accesso in Experience Builder e seleziona la pagina di destinazione in **Branding**. Tutti gli URL del profilo aprono questa pagina di destinazione.

1. Crea il profilo di registrazione autonoma in **Utenti** > **Esterni**. Ogni profilo ha il proprio ID gruppo e la propria chiave di accesso, che gli utenti devono registrare.

## Copia l’URL di registrazione per un profilo

1. Seleziona **Utenti** > **Esterni**, quindi seleziona **Registrazione autonoma**.

1. Nella colonna **URL della pagina di destinazione da copiare**, selezionare **Non connesso** per un profilo.

   ![URL della pagina di destinazione da copiare nella colonna per un profilo di registrazione autonoma](assets/Use-a-non-logged-in-menu-URL-for-self-registration-image1.png "URL della pagina di destinazione da copiare")

1. Copia l&#39;URL e condividilo con gli utenti che desideri invitare.

L&#39;elenco **URL della pagina di destinazione da copiare** include le seguenti opzioni:

* **Registrazione**: URL di registrazione standard
* **Pagina principale senza accesso (legacy)**: URL della pagina principale senza accesso legacy
* **Menu senza accesso**: URL del menu senza accesso in Experience Builder

## Cosa vedono gli utenti

1. L&#39;utente apre l&#39;URL e raggiunge la pagina di destinazione senza accesso selezionata in **Branding**.

1. L&#39;utente seleziona **Registrati** e immette l&#39;ID gruppo e la chiave di accesso per il profilo.

1. L’utente immette il suo nome, indirizzo e-mail e password, quindi completa la registrazione.

Adobe Learning Manager aggiunge l’utente al profilo a cui appartiene l’URL. Il nuovo utente verrà visualizzato in tale profilo in **Utenti** > **Esterni**.

>[!NOTE]
>
>Ogni URL del profilo mostra la stessa pagina di destinazione. Differisce solo il profilo a cui vengono aggiunti gli utenti.

## Invia un messaggio e-mail di benvenuto con l’URL

1. Seleziona **Utenti** > **Esterni** e seleziona il profilo di registrazione autonoma.

1. Nell&#39;elenco **URL della pagina di destinazione da copiare** selezionare l&#39;URL che si desidera includere nell&#39;e-mail.

   ![Elenco URL della pagina di destinazione con le icone di posta elettronica e copia](assets/Use-a-non-logged-in-menu-URL-for-self-registration-image2.png "Elenco URL della pagina di destinazione")

1. Seleziona l’icona e-mail per inviare l’e-mail. In alternativa, selezionate l&#39;icona di copia per copiare l&#39;URL.

Adobe Learning Manager invia l’e-mail utilizzando il modello **Profilo creato (Esterni/Partner)**. L’e-mail contiene l’URL univoco selezionato, il limite di partecipanti per il profilo e la data di scadenza dell’URL. Condividi l&#39;URL con gli utenti che desideri invitare.

## Spostarsi dalla pagina principale precedente senza accesso

Nelle versioni precedenti di questo elenco era visualizzata l&#39;opzione **Accesso non effettuato**. Ora si chiama **Pagina principale senza accesso (legacy)**.

La pagina principale precedente senza accesso diventerà obsoleta in una versione futura. Se lo utilizzi, passa al menu senza accesso in Experience Builder per mantenere la stessa funzionalità.
