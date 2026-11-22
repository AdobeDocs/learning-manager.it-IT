---
description: Consenti agli Allievi di scoprire i corsi, monitorare i progressi e ottenere risposte dai contenuti di Adobe Learning Manager all’interno di Claude, ChatGPT Enterprise e agenti personalizzati.
jcr-language: en_us
title: Server Adobe Learning Manager Model Context Protocol
exl-id: 8d0a25a6-1301-4f68-8db7-e3b1d3ff6537
source-git-commit: f6dc1e97076edf812862b80a6ed5931989c660da
workflow-type: tm+mt
source-wordcount: '684'
ht-degree: 0%
---

# Server Adobe Learning Manager Model Context Protocol

## Panoramica

MCP (Model Context Protocol) è un metodo standard per la connessione di un client AI agli strumenti. Il server Adobe Learning Manager MCP consente agli Allievi di apprendere dove già lavorano. Gli strumenti per Allievi di Adobe Learning Manager vengono esposti a qualsiasi client AI che supporti MCP, ad esempio un agente aziendale personalizzato, Claude o ChatGPT. Gli Allievi possono quindi accedere ai corsi di formazione e avanzare dallo stesso client, mentre il contenuto rimane in Adobe Learning Manager.

## Funzionalità Allievo

Gli Allievi lavorano con il linguaggio naturale nel client AI che già utilizzano. Il client interpreta ogni richiesta, chiama lo strumento Allievo di Adobe Learning Manager appropriato e restituisce una risposta in base a ciò a cui l’Allievo può accedere. Gli Allievi possono:

* Scopri i corsi, le certificazioni e i percorsi di apprendimento disponibili.
* Tieni traccia di iscrizioni, progressi e scadenze, compreso l’apprendimento che sta per scadere.
* Ottieni risposte basate sui contenuti di apprendimento.
* Generare un percorso di apprendimento personalizzato dai propri obiettivi e salvarlo.
Per l’elenco completo, visualizza il **riferimento agli strumenti per allievi**.

Il client AI chiama il server MCP, che indirizza ogni richiesta allo strumento Allievo corrispondente.

Per l’elenco completo, visualizza il **riferimento agli strumenti per allievi**.

## Formazione per clienti e partner

La formazione dei clienti e dei partner è un utilizzo principale del server MCP. Le organizzazioni che creano i propri agenti di intelligenza artificiale aziendale possono connettere tali agenti agli strumenti per gli Allievi di Adobe Learning Manager. I clienti e i partner apprendono quindi tramite l&#39;assistente già utilizzato, senza passare a un assistente di apprendimento separato.

Ad esempio, Acme Inc. crea un proprio assistente di intelligenza artificiale aziendale. Un partner di Acme Inc. visita l&#39;ambiente di Tech Corp per conoscere i prodotti Tech Corp. L&#39;assistente di Acme si connette al proprio account Adobe Learning Manager tramite il server MCP e restituisce le risposte relative all&#39;apprendimento, pertanto il partner non lascia mai l&#39;esperienza Acme.

Questo approccio consente alle organizzazioni di:

* Offrite l&#39;apprendimento all&#39;interno dell&#39;esperienza di intelligenza artificiale esistente di un partner.
* Consenti agli agenti aziendali personalizzati di utilizzare gli strumenti di formazione di Adobe Learning Manager.
* Integrare l’apprendimento nei propri flussi di lavoro.
* Integrazione dell&#39;apprendimento con l&#39;ecosistema di intelligenza artificiale aziendale.

## Formazione dei dipendenti

I dipendenti che già utilizzano un client di intelligenza artificiale, come Claude, possono ottenere le loro informazioni di apprendimento lì. Ad esempio, un dipendente può controllare l’apprendimento assegnato, rivedere le iscrizioni, trovare corsi su un argomento o chiedere un percorso di apprendimento, senza passare a Adobe Learning Manager. Per le richieste di esempio, consulta [richieste di esempio per gli Allievi](https://word-edit.officeapps.live.com/docs/sample-prompts-adobe-learning-manager-learners).

Questo approccio consente ai dipendenti di:

* Rimani negli strumenti che già usano.
* Raggiungi il loro apprendimento ovunque lavorino.
* Utilizzate qualsiasi client AI che supporti MCP come punto di ingresso per Adobe Learning Manager.
* Ottieni informazioni sull’apprendimento senza modificare il contesto.

## Un server per entrambi i gruppi di destinatari

La formazione per clienti e partner e quella per dipendenti utilizzano gli stessi strumenti per gli Allievi e lo stesso server. Cambia solo il pubblico. Scegli l’approccio che si adatta a chi sono i tuoi Allievi.

| **Pubblico** | **Esempio** | **Dove lavorano gli Allievi** |
|----|----|----|
| Esterno | Clienti e partner | L&#39;agente di intelligenza artificiale aziendale della tua organizzazione |
| Interno | Dipendenti | Un client di intelligenza artificiale aziendale, ad esempio Claude o ChatGPT Enterprise |

## Ruoli di installazione

La configurazione è suddivisa in tre ruoli.

* **Amministratore:** crea un&#39;applicazione client MCP in Adobe Learning Manager e la gestisce. Vedere [configurare un server MCP](https://word-edit.officeapps.live.com/docs/configure-model-context-protocol-server-adobe-learning-manager).
* **Amministratore del client AI:** aggiunge il server al client di intelligenza artificiale dell&#39;organizzazione, ad esempio Claude o ChatGPT Enterprise.
* **Allievo:** seleziona **Connect** nel client AI, autentica la connessione e fornisce i dettagli del proprio account Adobe Learning Manager.

## Sicurezza delle richieste degli Allievi

Ogni Allievo autentica la connessione e fornisce i dettagli del proprio account Adobe Learning Manager. La richiesta viene eseguita come tale Allievo, quindi il client AI restituisce solo le informazioni a cui l’Allievo può accedere in Adobe Learning Manager. Il server non offre agli Allievi accesso aggiuntivo.

## Limitazioni di MCP in questo aggiornamento

* La disponibilità degli strumenti dipende da ciò che supporta il client AI.
* Ogni richiesta viene trattata come nuova. Le conversazioni a più turni funzionano solo se il client AI mantiene il contesto della conversazione.
