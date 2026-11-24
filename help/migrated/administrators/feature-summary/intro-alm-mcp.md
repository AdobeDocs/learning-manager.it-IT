---
description: Estendi Adobe Learning Manager in Claude, ChatGPT Enterprise e agenti personalizzati in modo che gli Allievi possano trovare corsi, monitorare i progressi e ottenere risposte.
jcr-language: en_us
title: Server Adobe Learning Manager Model Context Protocol
exl-id: 8d0a25a6-1301-4f68-8db7-e3b1d3ff6537
source-git-commit: 89aa1b5ab02eed8a61507ab162fcbbd384e6c5fc
workflow-type: tm+mt
source-wordcount: '765'
ht-degree: 0%
---

# Server Adobe Learning Manager Model Context Protocol

Il Model Context Protocol (MCP) è uno standard aperto che consente a un client AI di individuare e richiamare strumenti esterni. Il server Adobe Learning Manager MCP espone gli strumenti per gli Allievi di Adobe Learning Manager a qualsiasi client compatibile con MCP, ad esempio un agente aziendale personalizzato, Claude o ChatGPT Enterprise. Gli Allievi ottengono la formazione e i progressi dal client che già utilizzano, mentre i contenuti e i record di apprendimento rimangono in Adobe Learning Manager.

## Come funziona

Un Allievo invia una richiesta in lingua naturale a un client AI. Il client seleziona lo strumento Allievo più pertinente e chiama il server MCP con il token di accesso OAuth dell’Allievo. Adobe Learning Manager esegue lo strumento come tale Allievo e restituisce il risultato, quindi il client compone la risposta finale.

Ogni chiamata riporta l’identità dell’Allievo. Un Allievo può quindi recuperare solo i contenuti e i record a cui è già autorizzato ad accedere.

Il client AI chiama il server MCP, che indirizza ogni richiesta allo strumento Allievo corrispondente.

## Funzionalità Allievo

Gli Allievi lavorano con il linguaggio naturale nel client AI che già utilizzano. Il client interpreta ogni richiesta, chiama lo strumento Allievo di Adobe Learning Manager appropriato e restituisce una risposta in base a ciò a cui l’Allievo può accedere. Gli Allievi possono:

* Scopri i corsi, le certificazioni e i percorsi di apprendimento disponibili.
* Tieni traccia di iscrizioni, progressi e scadenze, compreso l’apprendimento che sta per scadere.
* Ottieni risposte basate sui contenuti di apprendimento.
* Generare un percorso di apprendimento personalizzato dai propri obiettivi e salvarlo.

Per l’elenco completo, visualizza il **riferimento agli strumenti per allievi**.

## Formazione per clienti e partner

>[!IMPORTANT]
>
>Anche i clienti che creano i propri agenti aziendali possono connettersi al server. Ad esempio, un&#39;organizzazione partner può offrire ai propri clienti l&#39;accesso all&#39;apprendimento tramite il proprio agente.

La formazione dei clienti e dei partner è un utilizzo principale del server MCP. Le organizzazioni che creano i propri agenti di intelligenza artificiale aziendale possono connettere tali agenti agli strumenti per gli Allievi di Adobe Learning Manager. I clienti e i partner apprendono quindi tramite l&#39;assistente già utilizzato, senza passare a un assistente di apprendimento separato.

Ad esempio, Acme Inc. crea un proprio assistente di intelligenza artificiale aziendale. Un partner di Acme Inc. visita l&#39;assistente per informazioni sui prodotti Acme Inc. L’assistente si connette all’account Adobe Learning Manager di Acme Inc. tramite il server MCP e restituisce le risposte relative all’apprendimento. Il partner non lascia mai l&#39;esperienza Acme Inc.

Questo approccio consente alle organizzazioni di:

* Offre apprendimento all&#39;interno dell&#39;esperienza di intelligenza artificiale esistente di un partner.
* Estendi gli agenti aziendali personalizzati con gli strumenti per Allievi di Adobe Learning Manager.
* Incorporare l’apprendimento nei propri flussi di lavoro.
* Integrazione dell&#39;apprendimento con l&#39;ecosistema di intelligenza artificiale aziendale.

## Formazione dei dipendenti

I dipendenti che già utilizzano un client di intelligenza artificiale, come Claude, possono ottenere le loro informazioni di apprendimento lì. Ad esempio, un dipendente può controllare l’apprendimento assegnato, rivedere le iscrizioni, trovare corsi su un argomento o chiedere un percorso di apprendimento, senza passare a Adobe Learning Manager. Per le richieste di esempio, scopri di più su [richieste di esempio per gli Allievi](/help/migrated/learners/feature-summary/sample-prompts-for-learners.md).

Questo approccio consente ai dipendenti di:

* Rimani negli strumenti che già utilizza.
* Raggiungi il loro apprendimento ovunque lavorino.
* Utilizza qualsiasi client di intelligenza artificiale compatibile con MCP come punto di ingresso per Adobe Learning Manager.
* Recupero delle informazioni di apprendimento senza modificare il contesto.

## Un server per entrambi i gruppi di destinatari

La formazione per clienti e partner e quella per dipendenti utilizzano gli stessi strumenti per gli Allievi e lo stesso server. Cambia solo il pubblico. Scegli l’approccio che si adatta a chi sono i tuoi Allievi.

| **Pubblico** | **Esempio** | **Dove lavorano gli Allievi** |
|----|----|----|
| Esterno | Clienti e partner | L&#39;agente di intelligenza artificiale aziendale della tua organizzazione |
| Interno | Dipendenti | Un client di intelligenza artificiale aziendale, ad esempio Claude o ChatGPT Enterprise |

## Ruoli di installazione

La configurazione è suddivisa in tre ruoli.

* **Amministratore:** crea un&#39;applicazione client MCP in Adobe Learning Manager e la gestisce. Ulteriori informazioni sulla [configurazione di un server MCP](/help/migrated/administrators/feature-summary/configure-mcp-admin.md).
* **Amministratore del client AI:** aggiunge il server al client di intelligenza artificiale dell&#39;organizzazione, ad esempio Claude o ChatGPT Enterprise.
* **Allievo:** seleziona **Connect** nel client AI, autentica la connessione e fornisce i dettagli del proprio account Adobe Learning Manager.

## Sicurezza delle richieste degli Allievi

Ogni Allievo autentica la connessione e fornisce i dettagli del proprio account Adobe Learning Manager. Ogni richiesta viene eseguita come tale Allievo, pertanto il client AI restituisce solo le informazioni a cui l’Allievo può accedere in Adobe Learning Manager. Il server non concede agli Allievi l’accesso aggiuntivo.

## Limitazioni

* Il server MCP è disponibile solo per gli account di livello Adobe Learning Manager Ultimate.
* La disponibilità degli strumenti dipende da ciò che supporta il client AI.
* Ogni richiesta viene considerata come nuova dal server. Le conversazioni a più turni funzionano solo se il client AI mantiene il contesto di conversazione.
