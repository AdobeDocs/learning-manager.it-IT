---
jcr-language: en_us
title: Importa abilità da origini esterne
description: Importa le abilità dai provider di contenuti, come LinkedIn e Go1, utilizzando i rispettivi connettori.  Le abilità importate verranno aggiunte alle abilità definite dall’amministratore in Learning Manager e saranno disponibili per gli Autori durante il flusso di lavoro di creazione del corso.
contentowner: saghosh
exl-id: 3bcd8fc6-16e4-4f66-a5c6-15b3d606f0c2
source-git-commit: fb2d642c90fa36d3db15d7da99fe9c97908ce0e8
workflow-type: tm+mt
source-wordcount: '445'
ht-degree: 0%

---

# Importa abilità da origini esterne

Importa le abilità dai provider di contenuti, come LinkedIn e Go1, utilizzando i rispettivi connettori. Questo miglioramento fa parte dell’obiettivo verso la capacità di Learning Manager di integrarsi con cloud di abilità e sistemi di gestione dei talenti esterni. Le abilità importate verranno aggiunte alle abilità definite dall’amministratore in Learning Manager e saranno disponibili per gli Autori durante il flusso di lavoro di creazione del corso. Sono stati apportati miglioramenti anche alla funzionalità di ricerca delle abilità su tutta la piattaforma, per offrire un’esperienza di ricerca migliore quando l’account dispone di un numero elevato di abilità.

## Configura importazione abilità

Segui i passaggi nella procedura per abilitare l’importazione di abilità nell’account.

1. Nell’app di amministrazione, seleziona **Impostazioni** nel riquadro sinistro.
1. Seleziona **Generale**.
1. Nella **Importazione di abilità** , seleziona **Abilita**. Se questa opzione è attivata, puoi scegliere un’origine esterna da importare. **Abilità**. Le abilità per le risorse di apprendimento esistenti verranno importate nel repository delle abilità una volta durante l’esecuzione iniziale. Per tutte le successive importazioni di risorse di apprendimento, le abilità verranno importate nel repository delle abilità solo per gli elementi appena importati.
1. Seleziona un provider di contenuti dal menu a discesa.

In qualità di Amministratore, puoi importare una sola Abilità come Origine.

### Livello di abilità predefinito

Il livello di abilità predefinito è uno e Credito è 10 dopo la migrazione delle abilità. L’amministratore successivo può modificare il credito.

Non è possibile modificare il nome dell’abilità, la descrizione e aggiungere livelli alle abilità esterne. Tuttavia, puoi aggiungere domini, distintivi e modificare i crediti.

#### Report

Colonna **Sorgente** con valori: Interno, LinkedIn Learning, Go1, che indica l’origine dell’importazione delle abilità.

Le abilità aggiunte di recente saranno al primo posto.

Nella pagina delle impostazioni del corso, la colonna **Assegnato da** contenente valori, Interno e Provider di contenuti.


## Flusso di lavoro Amministratore dell’integrazione

L’Amministratore dell’integrazione carica i CSV (abilità, livello di abilità e corso) e quindi migra i corsi nell’account. Ad esempio, dopo che l’Amministratore ha selezionato LinkedIn Learning, l’Amministratore dell’integrazione può pianificare un’attività in cui vengono importati sia abilità che livelli in Adobe Learning Manager.

## Esportare le abilità

In qualità di Amministratore,

1. Seleziona **Abilità** nel riquadro sinistro.
1. Seleziona la fonte per qualsiasi abilità. Puoi visualizzare corsi, risorse formative, Allievi iscritti e Istruttori del corso.

### Modifica di un’abilità

Seleziona un’abilità. Nella **Modificare un’abilità** pop-up, non è possibile modificare il nome e la descrizione dell’abilità. Tuttavia, puoi aggiungere domini di abilità e un distintivo per l’abilità.
