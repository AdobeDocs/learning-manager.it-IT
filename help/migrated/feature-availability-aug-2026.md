---
description: Scopri quali superfici delle app supportano le nuove funzioni di Adobe Learning Manager per la versione di agosto 2026, tra cui API, dispositivi mobili e widget AEM
jcr-language: en_us
title: Disponibilità delle funzioni nella versione di agosto 2026 di Adobe Learning Manager
exl-id: e134937c-630d-4285-9181-2eca114717f6
source-git-commit: bb95f74b775d279e94fad319380d451446256636
workflow-type: tm+mt
source-wordcount: '628'
ht-degree: 0%

---


# Disponibilità delle funzioni nella versione di agosto 2026 di Adobe Learning Manager

## Scopo

I clienti aziendali che sviluppano o estendono la piattaforma attraverso il proprio front-end (un’implementazione &quot;headless&quot;) si chiedono regolarmente se una funzione nuova o modificata possa essere effettivamente utilizzata al di fuori dell’interfaccia utente Web standard, tramite l’API degli Allievi, l’API Admin, il widget AEM o un’altra superficie di integrazione.

Questo documento fornisce una risposta rapida e di tipo narrativo per ogni funzione fornita in questa versione. Per ogni funzionalità, questo documento identifica le superfici delle applicazioni supportate, la disponibilità dell’integrazione, il supporto della migrazione e qualsiasi comportamento di notifica applicabile.

## Disponibilità funzione per funzione

### Generatore e-mail basato su componenti

Si tratterà di un’abilitazione per fasi per account diversi che si registrano dopo il rilascio della funzione, per migrare tali account da un editor e-mail esistente a un nuovo editor. Una volta attivato, il cliente non può utilizzare il vecchio editor e-mail. (Per l’abilitazione delle funzioni, contatta il CSM/supporto).

* **Disponibile in:** app amministratore. Amministratori e autori configurano layout e modelli e-mail qui.
* **Non applicabile:** interfaccia utente rivolta agli Allievi, API headless e widget AEM, in quanto gli Allievi ricevono semplicemente le e-mail risultanti tramite il proprio client di posta.
* **Notifiche:**
  * Le notifiche e-mail continuano a essere inviate agli Allievi tra i client e-mail supportati.
  * Questa funzione non introduce alcun nuovo comportamento di notifica nella piattaforma.

### Apprendimento esterno

* **Disponibile su:** Web nativo, API headless (Allievo), Web mobile nativo e app Amministratore.
* **Non ancora disponibile nell&#39;app nativa per dispositivi mobili:**.
* **API processo:** non applicabile.
* **Migrazione:** Non ancora supportata.
* **Notifiche:**
  * Gli Allievi e i Manager possono ricevere notifiche sulla piattaforma quando vengono inviate richieste di approvazione dell’apprendimento esterno e quando le richieste vengono approvate o rifiutate.
  * Le notifiche e-mail non sono attualmente disponibili per questo flusso di lavoro.

### Report utente incrementale

* **Disponibile solo per:** API processo. Fornisce un&#39;esportazione incrementale (delta) dei dati utente per la creazione di report.
* **Non applicabile:** interfaccia utente, altre superfici API e strumenti di migrazione.

### Report Builder

* **Disponibile in:** app amministratore.
* **Non ancora disponibile per l&#39;API processo**. Per una versione futura è prevista un’esportazione basata su API di processo.
* **Migrazione:** non applicabile.
* **Notifiche:**
  * Gli utenti ricevono notifiche nella piattaforma quando i download dei report sono pronti o quando la generazione dei report non riesce.
  * Le notifiche e-mail non sono applicabili.

### Cartelle dei contenuti gerarchici

* **Disponibile in:** app per amministratori e autori.
* **Migrazione:** Supportata.
* **API processo:** non applicabile. Nessuna superficie API dedicata al momento.

>[!NOTE]
>
>I privilegi del ruolo personalizzato si applicano solo a livello di cartella principale/principale e non a tutte le cartelle della gerarchia.

### Agente Insights

* **Disponibile in:** app amministratore. Attualmente limitato solo agli amministratori completi (non ai ruoli personalizzati).
* **API amministratore:** non disponibile.
* **API processo/Migrazione:** non applicabile.

### Agente percorso di apprendimento

* **Disponibile su:** Web nativo e API headless (Allievo).
* **Non ancora disponibile su:** Web nativo per dispositivi mobili, app nativa per dispositivi mobili e widget AEM.
* **API processo/Migrazione:** non applicabile.

### Assistente AI (Allievo)

* **Disponibile su:** Web nativo, API headless (Allievo) e Web mobile nativo.
* **Non ancora disponibile su:** App mobile nativa e widget AEM.
* **API processo/Migrazione:** non applicabile.

>[!NOTE]
>
>Prima che questa funzione appaia agli Allievi, deve essere esplicitamente abilitata.

### Live Hub

* **Disponibile su:** Web nativo, API headless (Allievo), Web mobile nativo e app Amministratore.
* **API processo:** non applicabile.
* **Migrazione:** non supportata.

### Amministratori Personalizzati: Lettura/Gestione Di Altri Ruoli Personalizzati

* **Disponibile in:** app amministratore. Consente agli amministratori personalizzati di visualizzare e gestire altri ruoli di amministratore personalizzati.
* **API processo/Migrazione:** non applicabile. Ancora nessuna API dedicata per questo.

### Gradebook

* **Disponibile su:** Web nativo, API headless (Allievo), Web nativo per dispositivi mobili, App nativa per dispositivi mobili e app Amministratore.
* **Non ancora disponibile nel widget AEM:**.
* **Migrazione:** non supportata.
* **Notifiche:**
  * Nessuna notifica e-mail.
  * Nessuna notifica sulla piattaforma.

### Canali

* **Disponibile su:** Web nativo e app amministratore. Attualmente in versione beta.
* **Non ancora disponibile per:** API headless (Allievo), Web mobile, app per dispositivi mobili, widget AEM e API di amministrazione.
* **API processo/Migrazione:** non applicabile.
