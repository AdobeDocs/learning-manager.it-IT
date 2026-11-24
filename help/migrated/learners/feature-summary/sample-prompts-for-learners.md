---
description: Trova suggerimenti di esempio a cui gli Allievi possono chiedere in Claude o ChatGPT Enterprise di cercare corsi, controllare le iscrizioni e creare percorsi di apprendimento
jcr-language: en_us
title: Suggerimenti di esempio per gli Allievi Adobe Learning Manager
exl-id: e5d64ac4-03e9-49bc-95d0-bb074d55987f
source-git-commit: 89aa1b5ab02eed8a61507ab162fcbbd384e6c5fc
workflow-type: tm+mt
source-wordcount: '181'
ht-degree: 1%
---

# Suggerimenti di esempio per gli Allievi Adobe Learning Manager

Utilizza questi suggerimenti in Claude o ChatGPT Enterprise per cercare corsi, controllare le iscrizioni e creare percorsi di apprendimento.

Collega prima il tuo client AI. Ulteriori informazioni sulla [connessione del client AI a Adobe Learning Manager](/help/migrated/learners/feature-summary/connect-ai-client-to-alm-learner.md). Ogni prompt viene mappato a uno strumento nel [riferimento agli strumenti per gli allievi](/help/migrated/learners/feature-summary/learner-tools-reference.md).

>[!TIP]
>
>Assegna un nome alle tue esigenze, ad esempio un argomento, lo stato di un corso o una scadenza. Richieste specifiche aiutano il client AI a selezionare lo strumento giusto.

## Iscrizioni

| **Richiedi** | **Strumento** |
|------------------------------------------|------------------------------|
| A quali corsi sono iscritto? | list_my_learning_enrollments |
| Quali dei miei corsi stanno per scadere? | list_my_learning_enrollments |

## Cerca

| **Richiedi** | **Strumento** |
|-----------------------------------------|-----------------------|
| Quali corsi di leadership sono disponibili? | search_learning_items |
| Mostra corsi di formazione sulla sicurezza disponibili. | search_learning_items |

## Conoscenza

| **Richiedi** | **Strumento** |
|----|----|
| Cosa significa gestione dei rischi della catena di approvvigionamento in FedRAMP? | response_learning_content_question |
| Spiegare i requisiti nel mio corso sulla conformità. | response_learning_content_question |

## Percorsi di apprendimento

| **Richiedi** | **Strumento** |
|----|----|
| Aiutami a trovare una serie di corsi per migliorare le competenze nella gestione dei progetti. | personalized_learning_path |
| Salva questo percorso di apprendimento. | personalized_learning_path |
