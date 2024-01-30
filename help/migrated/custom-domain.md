---
jcr-language: en_us
title: Supporto per il dominio personalizzato
description: I domini personalizzati non sono supportati in un’istanza Azure di Learning Manager.
contentowner: saghosh
source-git-commit: 8635072782253cbac3f913953797cae7c0bc5ef4
workflow-type: tm+mt
source-wordcount: '446'
ht-degree: 67%

---



# Supporto per il dominio personalizzato

I domini personalizzati non sono supportati in un’istanza Azure di Learning Manager.

## Panoramica {#overview}

Il supporto per il dominio personalizzato consente ai clienti di avere il controllo totale sul nome del dominio che possono usare per il loro account in Learning Manager. Un cliente deve acquistare il dominio personalizzato separatamente e collaborare con il team Adobe per configurarlo come URL di accesso per la piattaforma di apprendimento.

Questo consente al cliente di offrire un’esperienza di accesso “white label” in modo che gli utenti non notino la presenza di Adobe o Adobe Learning Manager.

Ad esempio, vorresti personalizzare il tuo dominio in modo che i tuoi utenti ottengano la stessa esperienza che se si trovassero nel dominio Adobe. Se ABC Inc vuole addestrare i propri clienti, vorrebbe che atterrassero su un dominio chiamato `abc.com/mylearning`, anziché `learningmanager.adobe.com/abc-inc/mylearning`.

>[!NOTE]
>
>Come prerequisito, è necessario registrare il dominio e quindi l’Adobe ti guiderà nella personalizzazione dell’URL.


La funzione di dominio personalizzato è disponibile a un costo aggiuntivo. Per saperne di più, contatta il tuo Customer Success Manager.

* Per il ruolo di Allievo, il dominio inizierà con `https://cdn.<customer_custom_domain>/` Ad esempio, `https://cdn.elearningstage1.cpdomaintest.in/`
* Per tutti gli altri ruoli, il dominio inizierà con `https://<customer_custom_domain>/`. Ad esempio: `https://elearningstage1.cpdomaintest.in/`

`<customer_custom_domain>` è la parte personalizzabile.

## Come configurare un dominio personalizzato in un account {#howtosetupacustomdomainonanaccount}

Come prerequisito, un cliente deve possedere un nome di dominio e acquistare il dominio da un provider.

Ad esempio, supponiamo che un cliente possieda un dominio fittizio, **acme.com**. Il cliente desidera che i contenuti di Learning Manager vengano forniti da **learning.acme.com**.

Applica i passaggi seguenti per configurare un dominio personalizzato.

1. Il cliente deve **aggiungere tre record CNAME** nel dominio:

   * **learning.acme.com:** Endpoint pubblico ALB di Learning Manager condiviso dall’Adobe
   * **lrs.learning.acme.com:** Endpoint pubblico ALB indicato da learning.acme.com
   * **cdn.learning.acme.com:** Endpoint CDN condiviso dall&#39;Adobe

1. Il cliente deve fornire certificati SSL per questi domini:

   * learning.acme.com
   * lrs.learning.acme.com
   * cdn.learning.acme.com

1. Adobe caricherà questi certificati SSL in AWS ALB per soddisfare le richieste per i domini.
1. Adobe aggiungerà learning.acme.com nel certificato SAN.
1. Adobe genererà i metadati SP per il cliente poiché i metadati conterranno gli URL del dominio personalizzato.

   * Se il cliente vuole avere accesso ai social, Adobe deve includere i modelli URL di reindirizzamento dei siti social nell’elenco di URL consentiti.
   * Se il cliente ha abilitato SSO, allora deve collaborare con il proprio IDP per includere i domini negli URL di reindirizzamento. Il cliente deve condividere il file XML dei metadati IDP con Adobe. Adobe deve quindi aggiornare le impostazioni SSO dell’account del cliente.

1. Adobe modificherà le regole S3 CORS per includere il dominio del cliente.
