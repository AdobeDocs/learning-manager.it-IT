---
description: Individuare le operazioni che gli Allievi possono eseguire con il server Adobe Learning Manager Model Context Protocol e gli strumenti MCP che supportano ciascuna funzionalità
jcr-language: en_us
title: Strumenti per gli Allievi per il server Model Context Protocol
exl-id: 4509b984-d0ba-4b7e-a0bb-803aa235fd1e
source-git-commit: 05691364449234a4782e2de5d4752c7b277f5fd4
workflow-type: tm+mt
source-wordcount: '262'
ht-degree: 1%
---

# Strumenti per gli Allievi per il server Model Context Protocol

Ogni funzionalità viene eseguita come Allievo connesso, dopo la connessione. Una richiesta restituisce solo ciò a cui l’Allievo può accedere in Adobe Learning Manager. Per ulteriori informazioni, consulta [Collega il tuo client AI](/help/migrated/learners/feature-summary/connect-ai-client-to-alm-learner.md).

## Funzionalità Allievo

| **Funzionalità** | **Attività che gli Allievi possono svolgere** | **Esempio di richiesta** |
|----|----|----|
| Cerca nei contenuti di apprendimento | Trova corsi, certificazioni e percorsi di apprendimento | Quali corsi di leadership sono disponibili? |
| Visualizza iscrizioni | Verifica delle iscrizioni e della formazione | Quali dei miei corsi stanno per scadere? |
| Domande di apprendimento | Ottieni risposte dai contenuti di apprendimento | Cosa significa gestione dei rischi della catena di approvvigionamento in FedRAMP? |
| Genera percorsi di apprendimento | Creazione di percorsi di apprendimento personalizzati | Aiutami a trovare corsi per migliorare le competenze nella gestione dei progetti. |
| Salvare i percorsi di apprendimento | Salvare i percorsi di apprendimento generati | Salva questo percorso di apprendimento. |

## Strumenti MCP supportati

Il server MCP di Learner Assistant espone i seguenti strumenti rivolti agli Allievi.

| **Strumento MCP** | **Scopo** | **Supporta le funzionalità** |
|----|----|----|
| Cerca | Ricerca dei contenuti di apprendimento disponibili | Cerca nei contenuti di apprendimento |
| Ottieni iscrizione | Recuperare le informazioni di iscrizione degli Allievi | Visualizza iscrizioni |
| Agente di risposta | Rispondere alle domande utilizzando i contenuti di apprendimento | Domande di apprendimento |
| Ottieni utente | Identifica l’Allievo che ha effettuato l’accesso per ogni richiesta | Tutte le funzionalità |
| Ottieni oggetto di apprendimento | Recupero dei dettagli di un oggetto di apprendimento, come descrizione e durata | Cerca contenuti di apprendimento, Visualizza iscrizioni |
| Genera percorso di apprendimento | Creazione di percorsi di apprendimento consigliati | Genera percorsi di apprendimento |
| Salva percorso di apprendimento | Salvare i percorsi di apprendimento generati | Salvare i percorsi di apprendimento |

>[!IMPORTANT]
>
>I nomi degli strumenti vengono visualizzati come riferimento e possono variare a seconda dell&#39;implementazione client.

