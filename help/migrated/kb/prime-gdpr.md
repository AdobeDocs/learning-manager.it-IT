---
jcr-language: en_us
title: Conformità di Learning Manager al GDPR
description: Conformità di Adobe Learning Manager al GDPR
contentowner: dvenkate
exl-id: 8ea31464-b4ce-49e8-b471-5630f0216aa4
source-git-commit: a01ec6117ad49a1f9af0b31d48ad19ddc8443dde
workflow-type: tm+mt
source-wordcount: '678'
ht-degree: 39%

---

# Conformità di Learning Manager al GDPR

>[!IMPORTANT]
>
>Il contenuto di questo documento non è un parere legale e non è inteso a sostituirlo con un parere legale. Consultare il dipartimento legale della propria azienda per consigli riguardanti il Regolamento generale sulla protezione dei dati.

Adobe Learning Manager si impegna a garantire la conformità al GDPR, garantendo che i dati degli utenti siano gestiti in modo sicuro e trasparente. Fornisce funzionalità GDPR essenziali, come la possibilità di rimuovere gli utenti (eliminare definitivamente tutti i dati personali) e consente agli amministratori di generare le trascrizioni degli Allievi per condividere informazioni con gli utenti su richiesta.

Tutti i dati degli utenti sono protetti con una forte crittografia durante il trasferimento e l&#39;archiviazione, utilizzando standard come SHA-256. Per alcune integrazioni, gli Allievi devono autenticarsi, verificando di aver ottenuto il consenso prima di condividere qualsiasi dato. Questi controlli sulla privacy e la sicurezza aiutano le organizzazioni che utilizzano Adobe Learning Manager a rispettare i requisiti GDPR e a proteggere le informazioni degli Allievi.

+++Cosa si intende con GDPR?

Il GDPR è un nuovo regolamento dell’Unione europea che entrerà in vigore il 25 maggio 2018. Offre un intenso controllo della riservatezza dei dati e consente agli utenti finali di prendere in carico i propri dati personali.

+++

+++Come o perché vale per te in quanto cliente di Adobe Learning Manager?

Sebbene il GDPR sia un regolamento dell’UE, è applicabile alle entità aziendali di tutto il mondo, che raccoglie informazioni personali per qualsiasi utente che può essere residente nell’UE.  In qualità di cliente Learning Manager, valuta se il GDPR è applicabile alla tua organizzazione.

+++

+++Che ruolo riveste Adobe in qualità di fornitore di Learning Manager?

In conformità con il GDPR, se l&#39;azienda fornisce un prodotto o un servizio ai residenti dell&#39;UE e determina modalità e motivazione di raccolta, tracciamento e monitoraggio dei dati, l&#39;utente è considerato un [data controller](https://gdpr-info.eu/art-24-gdpr/). Se sei cliente Adobe Learning Manager ed esegui una di queste attività, sei anche responsabile del trattamento dei dati.

Le aziende che elaborano i dati per conto di controller sono considerate [processori dati](https://gdpr-info.eu/art-28-gdpr/). In qualità di fornitore di Adobe Learning Manager LMS ospitato nel cloud, Adobe svolge il ruolo di responsabile del trattamento dei dati. Di seguito sono riportati ulteriori dettagli su [GDPR e azienda](https://www.adobe.com/privacy/general-data-protection-regulation.html).

+++

+++In che modo Learning Manager ti garantisce la conformità al GDPR?

Learning Manager dispone dei seguenti processi e strumenti integrati per semplificare il rispetto della conformità al GDPR. Per supportare la piena conformità al regolamento di qualsiasi processo che vada oltre il prodotto, potrebbe essere necessario valutare il problema con il team di conformità.

**Diritto all&#39;oblio - Per raggiungere il titolare del trattamento:** il GDPR richiede ai titolari del trattamento di supportare una funzionalità di Diritto all&#39;oblio per gli utenti. Ciò significa che ogni utente ha il diritto di richiedere al titolare del trattamento di eliminare definitivamente qualsiasi dato personale memorizzato per quell&#39;utente. Se ricevi tale richiesta e ne confermi la validità, questa funzionalità viene fornita in Learning Manager tramite la funzione di [rimozione degli utenti](../administrators/feature-summary/purge-users.md). Questa funzione consente all’amministratore di avviare una cancellazione permanente di tutti i dati relativi a una persona specifica, in base alla richiesta dei singoli individui. Nello stesso momento, Learning Manager cancella immediatamente i dati dal database e viene eseguita automaticamente la rimozione dei registri di backup (destinati al recupero del sistema).

**Diritto all’oblio - Dedicato al responsabile del trattamento dei dati:** l’utente finale può inoltre contattare Adobe in modo autonomo per eliminare i dati identificativi. In questo caso, Learning Manager rileva automaticamente gli account contenenti i dati identificativi di tale utente e Adobe notifica immediatamente l’amministratore di tale richiesta. L’Amministratore può quindi valutare la validità della richiesta e rispondere alla stessa tramite la funzione di rimozione degli utenti.

**Diritto di accesso:** GDPR consente all&#39;utente finale di richiedere i dati archiviati da un controller per tale utente finale. Per supportare questa richiesta, Learning Manager consente all’Amministratore di generare automaticamente la Trascrizione Allievo che può essere condivisa con l’utente.

**Privacy by Design, crittografia dei dati:** Il trattamento dei dati, sia in transito che non, viene eseguito utilizzando i migliori standard di crittografia per garantire la sicurezza dei dati. Gli algoritmi di crittografia utilizzati sono SHA-256. Ciò garantisce che tutti i dati archiviati siano adeguatamente protetti, in modo che non cadano nelle mani sbagliate.

+++
