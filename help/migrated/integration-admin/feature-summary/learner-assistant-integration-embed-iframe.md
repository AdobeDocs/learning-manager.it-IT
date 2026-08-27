---
description: Scopri come incorporare l’Assistente Allievo nell’app utilizzando un iFrame, tra cui configurazione e gestione degli eventi
jcr-language: en_us
title: Integrazione di Assistente Allievo incorporando iFrame
source-git-commit: 1549a4592b7a930631dcff6b2e75ec3a3d4f5592
workflow-type: tm+mt
source-wordcount: '719'
ht-degree: 1%

---


# Assistente Allievo che incorpora utilizzando un iFrame

## Panoramica

Gli utenti Adobe Learning Manager (ALM) possono incorporare **Learner Assistant** direttamente nelle proprie applicazioni rivolte agli Allievi (ad esempio, portali personalizzati, front-end LMS, hub di apprendimento e così via). utilizzo di un HTML standard `<iframe>`.

Quando viene incorporato tramite iFrame, l’Assistente Allievo fornisce accesso a tutte le sue funzionalità, tra cui:

* Orchestrator
* Agente di risposta
* Agente conoscenza
* Agente percorso di apprendimento

>[!IMPORTANT]
>
>L’incorporamento iFrame consente all’applicazione di accedere agli agenti sottostanti dell’Assistente Allievo. Tuttavia, l’applicazione (l’&quot;app principale&quot;) è responsabile della gestione di tutti gli eventi generati dall’assistente. Ad esempio, quando un Allievo fa clic su una citazione o su un collegamento del corso all’interno della risposta dell’Assistente, quest’ultimo genera un evento che l’applicazione principale deve gestire ed eseguire di conseguenza. L’Assistente Allievo non naviga per conto dell’applicazione.

## Prerequisiti

Prima di iniziare, si assicuri di avere:

* Un tenant ALM con l’Assistente Allievo abilitato. Configura i cataloghi richiesti dalla pagina delle impostazioni dell’amministratore.
* Un accessToken valido per l’autenticazione della sessione dell’Allievo (o dell’Amministratore). Per generare un token di accesso, segui le istruzioni riportate nella pagina [Autenticazione tramite OAuth 2.0](https://experienceleague.adobe.com/en/docs/learning-manager/using/integration/developer-manual#authentication-using-oauth-20). La pagina include i passaggi necessari per autenticarsi e generare il token di accesso necessario per procedere.
* Possibilità di incorporare un `<iframe>` nell&#39;applicazione e comunicare con esso tramite l&#39;API postMessage del browser.
* Proprietà del codice front-end dell&#39;applicazione padre, poiché l&#39;applicazione deve ascoltare e rispondere ai messaggi dall&#39;iFrame incorporato.

## Parametri di configurazione di Learning Assistant

| Nome parametro | Valore | Descrizione |
|---|---|---|
| hostName | learningmanager.adobe.com | Specifica il dominio host per l&#39;applicazione. |
| accessToken | token123 (token di accesso effettivo) | Token utilizzato per autenticare e autorizzare la sessione utente. |

## Inizializza iFrame

Trasferisci la configurazione all’Assistente Allievo tramite l’API postMessage, utilizzando un handshake di configurazione iFrame incorporato.

1. L’applicazione principale incorpora Learning Assistant come `<iframe>`.
2. Se non viene trovata alcuna configurazione basata su URL, Learning Assistant invia un evento ALM_CHAT_REQUEST_CONFIG all&#39;applicazione principale.
3. L&#39;applicazione padre risponde con un evento ALM_CHAT_CONFIG contenente il payload di configurazione. Ad esempio:

   ```json
   {
     "hostName": "learningmanager.adobe.com",
     "accessToken": "token123",
     "openByDefault": false,
     "isAdmin": false
   }
   ```

4. Dopo l’inizializzazione, l’Assistente Allievo effettua il rendering ed è pronto per l’uso.

## Riepilogo eventi iFrame

L’Assistente Allievo e l’applicazione principale comunicano tramite eventi post-messaggio in entrambe le direzioni.

### Eventi in uscita (da iFrame dell’Assistente Allievo a app principale)

| Nome evento | Descrizione | Parametri passati |
|---|---|---|
| ALM_CHAT_OPEN | Generato all&#39;apertura della chat. | -- |
| ALM_CHAT_CLOSED | Generato alla chiusura della chat. | -- |
| ALM_CHAT_LO_REDIRECT | Passa alla pagina di panoramica del percorso di apprendimento personalizzato. | loId, loType, instanceId |
| ALM_CHAT_URL_REDIRECT | Generato quando si fa clic su un collegamento esterno nel messaggio della chat. | url |
| ALM_CHAT_REQUEST_CONFIG | Richiede la configurazione all&#39;applicazione padre. | -- |
| ALM_CHAT_WAITING_FOR_REPLY | Indica che l&#39;assistente sta elaborando una richiesta o è in attesa di una risposta. | isWaitingForReply |
| ALM_CHAT_PERSONALIZED_PATH_CREATED | Viene attivato quando viene salvato un percorso di apprendimento. | -- |

### Eventi in arrivo (app principale per Assistente Allievo)

| Nome evento | Descrizione | Carico utile |
|---|---|---|
| ALM_CHAT_CONFIG | Invia il payload di configurazione necessario per inizializzare l&#39;assistente. | Oggetto di configurazione |
| ALM_CHAT_OPEN | Apre l’Assistente Allievo. | Nessuno |
| ALM_CHAT_CLOSE | Chiude l’Assistente Allievo. | Nessuno |
| ASK_AI_ASSISTANT_QUERY | Apre la finestra della chat e invia una query all&#39;assistente. | { query: &quot;Testo domanda&quot; } |

## Requisiti per la gestione degli eventi nell&#39;applicazione principale

L’incorporamento dell’Assistente Allievo tramite iFrame non lo rende un widget completamente autonomo. L&#39;applicazione principale deve ascoltare attivamente gli eventi in uscita e intraprendere le azioni appropriate. L’applicazione deve almeno:

* Ascoltare ALM_CHAT_REQUEST_CONFIG e rispondere con ALM_CHAT_CONFIG in modo che l&#39;assistente possa inizializzare.
* Gestisci ALM_CHAT_LO_REDIRECT: quando un Allievo fa clic su una citazione o un’origine nella risposta dell’Assistente, l’applicazione riceve loId, loType e instanceId ed è responsabile della navigazione dell’Allievo nel corso o nell’oggetto di apprendimento corretto.
* Gestisci ALM_CHAT_URL_REDIRECT: quando un Allievo fa clic su un collegamento esterno in un messaggio di chat, l’applicazione riceve l’URL ed è responsabile dell’apertura o della navigazione (ad esempio, in una nuova scheda).
* È possibile tenere traccia di ALM_CHAT_OPEN / ALM_CHAT_CLOSED / ALM_CHAT_WAITING_FOR_REPLY per riflettere lo stato dell&#39;assistente nella propria interfaccia utente (ad esempio, se si visualizza un indicatore di caricamento mentre isWaitingForReply è true).
* È possibile utilizzare ALM_CHAT_OPEN / ALM_CHAT_CLOSE / ASK_AI_ASSISTANT_QUERY per controllare l&#39;assistente a livello di programmazione. Ad esempio, aprendo l&#39;assistente e precompilando una query da un pulsante **Guida** in un&#39;altra posizione dell&#39;applicazione.

## Serve aiuto?

Contatta il tuo Customer Success Manager Adobe per configurare una procedura dettagliata dal punto di vista tecnico.
