---
description: Individuare le operazioni che gli Allievi possono eseguire con il server Adobe Learning Manager Model Context Protocol e gli strumenti che supportano ciascuna funzionalità.
jcr-language: en_us
title: Strumenti per gli Allievi per il server Model Context Protocol
exl-id: 4509b984-d0ba-4b7e-a0bb-803aa235fd1e
source-git-commit: 89aa1b5ab02eed8a61507ab162fcbbd384e6c5fc
workflow-type: tm+mt
source-wordcount: '394'
ht-degree: 0%
---

# Strumenti per gli Allievi per il server Model Context Protocol

## Panoramica

Ogni funzionalità viene eseguita come Allievo connesso, dopo la connessione. Una richiesta restituisce solo ciò a cui l’Allievo può accedere in Adobe Learning Manager. Ulteriori informazioni sulla [connessione del client AI](/help/migrated/learners/feature-summary/connect-ai-client-to-alm-learner.md).

## Funzionalità Allievo

| **Funzionalità** | **Attività che gli Allievi possono svolgere** | **Esempio di richiesta** |
|----|----|----|
| Cerca nei contenuti di apprendimento | Trova corsi, certificazioni e percorsi di apprendimento | Quali corsi di leadership sono disponibili? |
| Visualizza iscrizioni | Verifica delle iscrizioni e della formazione | Quali dei miei corsi stanno per scadere? |
| Domande di apprendimento | Ottieni risposte dai contenuti di apprendimento | Cosa significa gestione dei rischi della catena di approvvigionamento in FedRAMP? |
| Genera percorsi di apprendimento | Creazione di percorsi di apprendimento personalizzati | Aiutami a trovare corsi per migliorare le competenze nella gestione dei progetti. |
| Salvare i percorsi di apprendimento | Salvare i percorsi di apprendimento generati | Salva questo percorso di apprendimento. |

## Strumenti MCP supportati

Il server Adobe Learning Manager MCP espone i seguenti strumenti per gli Allievi.

| **Nome strumento** | **Descrizione** |
|----|----|
| search_learning_items | Cerca nel catalogo corsi, percorsi di apprendimento, certificazioni, risorse formative, distintivi, abilità, cataloghi e tag. Filtra per stato dell’Allievo, abilità, tag, catalogo, formato di consegna, prezzo e lingua. Per domande sull’argomento, utilizza response_learning_content_question. Esempio: &quot;corsi per principianti su Python&quot;. |
| list_my_learning_enrollments | Elenca i corsi dell’Allievo registrati, in corso e completati, i percorsi di apprendimento, le certificazioni e le risorse formative, con stato, avanzamento e scadenza. Filtra in base al tipo di oggetto di apprendimento o allo stato di completamento. I risultati mostrano prima le iscrizioni più recenti. Esempio: &quot;Cosa è previsto a breve?&quot; |
| get_learning_object | Ottieni i dettagli completi di un corso, un percorso di apprendimento, una certificazione o una risorsa formativa tramite ID, facoltativamente con istanze, abilità e oggetti di apprendimento secondario. Ottieni l’ID da search_learning_items o list_my_learning_enrollments. |
| get_my_learning_profile | Ottieni il profilo dell’Allievo, inclusi i dettagli dell’account e del manager. Per le iscrizioni e l’avanzamento, utilizza list_my_learning_enrollments. |
| response_learning_content_question | Rispondere alle domande sui contenuti di apprendimento, basate sul materiale di apprendimento e citate per gli oggetti di apprendimento di origine. Riepiloga un oggetto di apprendimento o confronta due elementi affiancati per copertura, profondità, prerequisiti e pubblico. Per trovare o elencare i contenuti, utilizza search_learning_items o list_my_learning_enrollments. Esempio: &quot;Descrizione di TCP rispetto a UDP come illustrato nel corso relativo alla rete&quot;. |
| personalized_learning_path | Corsi consigliati che corrispondono agli obiettivi, agli argomenti e alle esigenze di un Allievo. Salva un percorso approvato per l’account dell’Allievo. Elenca i percorsi salvati o ottieni i dettagli e i corsi di un percorso in base all&#39;ID. |

>[!IMPORTANT]
>
>I nomi degli strumenti vengono visualizzati come riferimento e possono variare a seconda dell&#39;implementazione client.
