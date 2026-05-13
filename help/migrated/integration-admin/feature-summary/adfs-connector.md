---
description: Scopri come integrare il connettore ADFS con Adobe Learning Manager
jcr-language: en_us
title: Connettore ADFS
contentowner: mmanuel
source-git-commit: 8a5212062c6b172b0e9d4f3faa2e66d26c5c2b56
workflow-type: tm+mt
source-wordcount: '460'
ht-degree: 3%

---


# Connettore ADFS in Adobe Learning Manager

## Introduzione

Il connettore ADFS in Adobe Learning Manager consente l&#39;integrazione con Microsoft Azure Active Directory tramite Active Directory Federation Services (ADFS). Questa integrazione consente la sincronizzazione automatica dei dati utente da Azure AD a Learning Manager. Con funzioni quali la mappatura degli attributi, il filtro degli utenti e le importazioni pianificate, il connettore consente di semplificare la gestione degli utenti e garantisce che i dati degli allievi rimangano accurati e aggiornati. È particolarmente utile per le organizzazioni che si affidano ad ADFS per la gestione centralizzata di identità e accessi.

## Prerequisiti

Prima di configurare il connettore ADFS in Adobe Learning Manager, completa i passaggi seguenti nel portale di Azure:

- Registra un&#39;applicazione
- Generare un segreto client
- Imposta autorizzazioni API

### Registra un&#39;applicazione in Azure

Per registrare un&#39;applicazione in Azure:

1. Accedi al [portale di Azure](https://portal.azure.com/).
2. Passa ad **Azure Active Directory**.
3. Seleziona **Aggiungi**, quindi seleziona **Registrazione app**.
4. Digita un nome per l&#39;applicazione e seleziona **Registra**.

### Generare un segreto client

Per creare un segreto client:

1. Nell&#39;app appena registrata, accedi a **Certificati e segreti**.
2. Selezionare **Nuovo segreto client**.
3. Aggiungi una descrizione e imposta la scadenza su **24 mesi**.
4. Salvare il **valore segreto client** in un percorso sicuro.

### Imposta autorizzazioni API

Per aggiungere l’autorizzazione API:

1. Seleziona **Autorizzazioni API**, quindi seleziona **Aggiungi autorizzazione**.
2. Seleziona **Microsoft Graph**, quindi seleziona **Autorizzazioni applicazione**.
3. Cerca e seleziona le seguenti autorizzazioni:

   - **Directory.Read.All** - Lettura dei dati della directory
   - **Utente.Leggi.Tutti** - Leggi tutti i profili completi degli utenti
4. Seleziona **Aggiungi autorizzazioni**.
5. Concedere **il consenso dell&#39;amministratore** per le autorizzazioni.

## Configurazione del connettore ADFS in Learning Manager

Puoi configurare il connettore ADFS in Adobe Learning Manager per importare i dati degli utenti da ADFS, esportare le abilità degli utenti in ADFS e pianificare sincronizzazioni automatizzate per mantenere entrambi i sistemi aggiornati.

Per configurare il connettore ADFS:

1. Accedi a Adobe Learning Manager come amministratore di integrazione.
2. Passa il mouse sul riquadro del connettore **ADFS**.
3. Seleziona **Connetti**.

   ![](assets/adfs-connector1.png)
   _Selezionare Connetti per configurare il connettore ADFS_

### Immetti i dettagli della connessione

Nella pagina di configurazione ADFS:

1. Digita i seguenti dettagli:

   - Nome connessione
   - ID client
   - Segreto del client

   ![](assets/adfs-connector2.png)
   _Digitare i dettagli di configurazione per connettere ADFS_

2. Seleziona **Connetti**.
3. Adobe Learning Manager recupererà e popolerà automaticamente il **ID tenant** e il **dominio primario** dal portale di Azure.

## Importazione di utenti da ADFS

### Mapping attributi

- Gli Amministratori di integrazione possono mappare gli attributi ADFS agli attributi raggruppabili corrispondenti in Adobe Learning Manager.
- Questa mappatura è una configurazione singola e viene riutilizzata per tutte le successive importazioni di utenti.
- Se necessario, puoi modificare la mappatura degli attributi in qualsiasi momento.

### Importazione automatica degli utenti

- Adobe Learning Manager estrae automaticamente i dati utente da ADFS a intervalli pianificati.
- Ciò consente di mantenere sincronizzati i record utente tra i sistemi.

### Filtraggio degli utenti

- Gli amministratori possono applicare filtri per limitare gli utenti importati.
- Ad esempio, puoi importare solo gli utenti di specifici manager o reparti.
