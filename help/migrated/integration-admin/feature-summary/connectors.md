---
description: Panoramica di ciascun connettore supportato ALM
jcr-language: en_us
title: Panoramica dei connettori supportati da ALM
contentowner: mmanuel
source-git-commit: bd80ca31ff633e21ec81e717772e43989f0d9aae
workflow-type: tm+mt
source-wordcount: '1424'
ht-degree: 6%

---


# Connettori Adobe Learning Manager

## Introduzione

Adobe Learning Manager (ALM) fornisce una suite completa di connettori che consentono l&#39;integrazione completa con applicazioni di terze parti e sistemi aziendali. Questi connettori fungono da ponte tra il sistema di gestione dell’apprendimento e le piattaforme esterne, facilitando la sincronizzazione automatizzata dei dati, la gestione degli utenti, l’importazione dei contenuti e le esportazioni dei record di apprendimento.

Questo documento funge da guida di riferimento completa per comprendere e selezionare i connettori appropriati per l’ecosistema di apprendimento dell’organizzazione. Che si tratti di integrazione con sistemi HR, piattaforme di e-commerce, strumenti per riunioni virtuali o soluzioni di business intelligence.

Per un elenco completo dei connettori supportati da Adobe Learning Manager, consulta gli articoli sui connettori nidificati a destra sotto questo articolo nel Sommario a sinistra.

>[!NOTE]
>
>Questa funzione è parzialmente disponibile negli ambienti autorizzati da FedRAMP. Per informazioni dettagliate, consulta [Disponibilità delle funzioni negli ambienti FedRAMP](/help/migrated/feature-availability-in-fedramp-authorized-environment.md).

>[!NOTE]
>
>Con la versione di novembre 2022 di Adobe Learning Manager, Zoom ha dichiarato obsoleta l&#39;autenticazione [JWT a giugno 2023](https://developers.zoom.us/docs/internal-apps/s2s-oauth/). Di conseguenza, il connettore Zoom con JWT continuerà a funzionare alla suddetta data, ma suggeriamo agli utenti di creare un’app OAuth Server-to-Server per sostituire la funzionalità nel proprio account. Per impostazione predefinita, tutte le nuove connessioni dispongono dell’autenticazione Zoom OAuth.

## Categorie di connettori

I connettori Adobe Learning Manager possono essere organizzati in diverse categorie funzionali in base allo scopo principale e alle funzionalità di integrazione:

| Categoria | Scopo | Connettori di esempio |
|---------|--------|-------------------|
| Trasferimento dati | Scambio di dati basato su file e operazioni in blocco | FTP, FTP personalizzato, Box |
| Classe virtuale | Formazione dal vivo e integrazione con riunioni | Microsoft Teams, Zoom, Adobe Connect |
| Sistemi aziendali | Integrazione dei sistemi aziendali e delle risorse umane | Workday, Salesforce, ADFS |
| Piattaforme dei contenuti | Integrazione di contenuti di apprendimento esterni | LinkedIn Learning, Harvard ManageMentor, getAbstract |
| Analytics e BI | Creazione di report e visualizzazione dei dati | Power BI, Accesso ai dati di formazione |
| Autenticazione | Gestione e sicurezza dell’identità | ADFS (funzionalità SSO) |
| e-commerce e marketing | Integrazione di vendite e marketing | Adobe Commerce, Marketo Engage |

## Connettori per il trasferimento dei dati e la gestione dei file

Questi connettori facilitano lo scambio automatizzato dei dati attraverso protocolli di trasferimento dei file, consentendo operazioni in blocco e comunicazioni tra sistemi.

### Connettore FTP Adobe Learning Manager

Il connettore FTP consente alle organizzazioni di automatizzare la sincronizzazione dei dati tra Adobe Learning Manager e i sistemi esterni utilizzando il protocollo File Transfer Protocol, ampiamente adottato. Questo connettore supporta varianti sicure, tra cui SFTP (SSH File Transfer Protocol) e FTPS (FTP Secure) per una maggiore sicurezza.

#### Funzionalità principali:

- Carica e scarica file tra Adobe Learning Manager e server remoti.
- Scambio automatizzato di dati per le informazioni sugli utenti e i record di formazione.
- Supporto per protocolli di trasferimento file protetti (SFTP, FTPS).
- Elaborazione in batch di set di dati di grandi dimensioni.

Per ulteriori informazioni, consulta [Connettore FTP](/help/migrated/integration-admin/feature-summary/ftp-connector.md).

### Connettore FTP personalizzato

Il connettore FTP personalizzato fornisce funzionalità di trasferimento file più sofisticate, supportando formati di dati strutturati e scambi di istruzioni xAPI. Questo connettore è progettato per le organizzazioni che richiedono un controllo più granulare sui processi di scambio dei dati.

#### Funzionalità principali:

- Importa ed esporta i dati utente tramite file CSV strutturati.
- Gestire i record di apprendimento e le istruzioni xAPI.
- Elaborazione automatizzata dei file da cartelle FTP designate.
- Funzioni di sicurezza avanzate per il trasferimento di dati riservati.

Per ulteriori informazioni, consulta [Connettore FTP personalizzato](/help/migrated/integration-admin/feature-summary/custom-ftp-connector.md).

### Connettore Box

Il connettore Box sfrutta la piattaforma di archiviazione cloud di Box per facilitare la sincronizzazione dei dati tra sistemi esterni e Adobe Learning Manager. Questo connettore è particolarmente utile per le organizzazioni che già utilizzano Box per la gestione dei file.

#### Funzionalità principali:

- Archiviazione e sincronizzazione dei file basate su cloud.
- Elaborazione automatizzata dei dati CSV.
- Integrazione con flussi di lavoro Box esistenti.
- Aggiornamenti dei dati in tempo reale da cartelle designate.

Per ulteriori informazioni, consulta [Connettore Box](/help/migrated/integration-admin/feature-summary/box-connector.md).

## Connettori per aula virtuale e riunioni

Questi connettori integrano Adobe Learning Manager con le più diffuse piattaforme di videoconferenza e riunioni virtuali, consentendo l&#39;esecuzione diretta delle sessioni di formazione.

### Connettore Microsoft Teams

Il connettore Microsoft Teams trasforma Adobe Learning Manager in una soluzione completa per aula virtuale integrandosi direttamente con le funzionalità di riunione di Teams. Questo connettore è essenziale per le organizzazioni che utilizzano l’ecosistema Microsoft 365.

#### Funzionalità principali:

- Pianificare sessioni in aula virtuale direttamente da Adobe Learning Manager.
- Creazione e gestione automatica delle riunioni Teams.
- Accesso diretto degli Allievi senza collegamenti alle riunioni separati.

Per ulteriori informazioni, consulta [Connettore MS Teams](/help/migrated/integration-admin/feature-summary/install-microsoft-teams-connector.md).

### Connettore zoom

Il connettore Zoom consente alle organizzazioni di sfruttare le potenti funzionalità di videoconferenza di Zoom direttamente nell’ambiente Adobe Learning Manager, fornendo un’esperienza uniforme sia agli istruttori che agli Allievi.

#### Funzionalità principali:

- Programmazione delle riunioni con Zoom diretto da Adobe Learning Manager.
- Generazione e distribuzione automatizzate dei collegamenti delle riunioni.
- Monitoraggio della frequenza in tempo reale.
- Gestione della registrazione e integrazione della riproduzione.
- Supporto per la sala d&#39;attesa per le sessioni interattive.

Per ulteriori informazioni, consulta [Connettore zoom](/help/migrated/integration-admin/feature-summary/zoom-connector.md).

### Connettore Adobe Connect

Il connettore Adobe Connect offre una profonda integrazione con la piattaforma per aula virtuale di Adobe, offrendo funzionalità avanzate per esperienze di apprendimento online interattive.

#### Funzionalità principali:

- Funzioni interattive avanzate (sondaggi, quiz, breakout).
- Condivisione dello schermo e strumenti di presentazione di alta qualità.
- Registrazione e riproduzione complete delle sessioni.
- Esperienza in aula virtuale ottimizzata per dispositivi mobili.

Per ulteriori informazioni, consulta [Connettore Adobe Connect](/help/migrated/integration-admin/feature-summary/adobe-connect-connector.md).

## Connettori di integrazione di sistema enterprise

Questi connettori consentono a Adobe Learning Manager di integrarsi con i principali sistemi aziendali, facilitando la gestione automatizzata degli utenti e la sincronizzazione dei dati dell&#39;organizzazione.

### Connettore Workday

Il connettore Workday crea un collegamento diretto tra il sistema HR e la piattaforma di gestione dell’apprendimento, assicurando la sincronizzazione tra i record dei dipendenti, le strutture organizzative e le assegnazioni dei ruoli in entrambi i sistemi.

#### Funzionalità principali:

- Provisioning automatico degli utenti da Workday.
- Sincronizzazione dei dati dei dipendenti in tempo reale.
- Mapping gerarchia organizzativa.
- Automazione dell’assegnazione dell’apprendimento basata sui ruoli.

Per ulteriori informazioni, consulta [Connettore Workday](/help/migrated/integration-admin/feature-summary/workday-connector.md).

### Connettore Salesforce

Il connettore Salesforce consente alle organizzazioni di integrare il proprio sistema di gestione delle relazioni con i clienti con iniziative di apprendimento, creando opportunità di formazione alle vendite, formazione per i clienti e monitoraggio delle prestazioni.

#### Funzionalità principali:

- Importazione automatica degli utenti da Salesforce.
- Mappatura dei campi dati personalizzati.
- Esportazione dei record di apprendimento in Salesforce.
- Prestazioni di vendita correlate al completamento della formazione.
- Gestione del programma di formazione per i clienti.

Per ulteriori informazioni, consulta [Connettore Salesforce](/help/migrated/integration-admin/feature-summary/salesforce-connector.md).

### Connettore ADFS (Active Directory Federation Services)

Il connettore ADFS consente alle organizzazioni di implementare l&#39;autenticazione e l&#39;autorizzazione di livello Enterprise, consentendo agli utenti di accedere a Adobe Learning Manager utilizzando le credenziali Active Directory esistenti.

#### Funzionalità principali:

- Implementazione Single Sign-On (SSO)
- Conformità alle normative di sicurezza aziendali
- Autenticazione completa degli utenti
- Importazione automatica degli utenti
- Possibilità di pianificare
- Possibilità di filtrare

Per ulteriori informazioni, consulta [Connettore ADFS](/help/migrated/integration-admin/feature-summary/adfs-connector.md).

## Connettori per piattaforme di contenuti e apprendimento

Questi connettori ampliano il catalogo di apprendimento integrando librerie di contenuti esterne e piattaforme di apprendimento specializzate.

### Connettore LinkedIn Learning

Il connettore LinkedIn Learning consente di accedere all’ampia libreria di corsi di sviluppo professionale di LinkedIn, che consente alle organizzazioni di integrare la formazione interna con contenuti esterni all’avanguardia.

#### Funzionalità principali:

- Accesso al catalogo completo dei corsi di LinkedIn Learning.
- Rilevamento e importazione automatizzati dei corsi.
- Verifica dello stato di avanzamento dell’Allievo in Adobe Learning Manager.

Per ulteriori informazioni, consulta [Connettore LinkedIn](/help/migrated/integration-admin/feature-summary/linkedin-learning-connector.md).

### Connettore Harvard ManageMentor

Il connettore Harvard ManageMentor fornisce contenuti di formazione di livello superiore per la leadership e la gestione direttamente nell&#39;ambiente Adobe Learning Manager, fornendo accesso alle rinomate risorse didattiche della Harvard Business School.

#### Funzionalità principali:

- Accesso premium ai contenuti della Harvard Business School.
- Moduli di sviluppo della gestione e della leadership.
- Importazione e organizzazione dei contenuti.

Per ulteriori informazioni, consulta [Connettore Harvard ManageMentor](/help/migrated/integration-admin/feature-summary/harvard-managementor-connector.md).

### Connettore getAbstract

Il connettore getAbstract consente di accedere a riepiloghi concisi dei libri aziendali e a approfondimenti professionali, consentendo alle organizzazioni di offrire un apprendimento continuo attraverso formati di contenuti digeribili.

#### Funzionalità principali:

- Accesso a riepiloghi e approfondimenti dei libri aziendali.
- Rilevamento e creazione di rapporti sui dati di utilizzo.
- Creazione automatizzata dei record di completamento.

Per ulteriori informazioni, consulta [connettore getAbstract](/help/migrated/integration-admin/feature-summary/getabstract-connector.md).

## Connettori di business intelligence e analisi

Questi connettori consentono funzionalità avanzate di reporting, visualizzazione dei dati e business intelligence integrando i dati di apprendimento con piattaforme di analisi esterne.

### Connettore Power BI

Il connettore Power BI trasforma i dati di apprendimento in informazioni aziendali attuabili sincronizzando automaticamente le metriche di apprendimento con la potente piattaforma di business intelligence di Microsoft.

#### Funzionalità principali:

- Sincronizzazione dei dati di apprendimento in tempo reale.
- Creazione e gestione di dashboard personalizzati.
- Visualizzazione e reporting avanzati dei dati.
- Trascrizione Allievo e integrazione dei report sulle abilità.

Per ulteriori informazioni, consulta [Connettore Power BI](/help/migrated/integration-admin/feature-summary/power-bi-connector.md).

### Connettore Accesso ai dati di formazione

Il connettore Accesso ai dati di formazione consente alle organizzazioni di creare interfacce di apprendimento personalizzate ed esperienze di apprendimento headless fornendo l’accesso API ai dati di formazione e alle informazioni sul corso.

**Funzionalità chiave:**

- Accesso API pubblica ai dati di corsi e percorsi di apprendimento.
- Supporto per lo sviluppo di interfacce utente personalizzate.
- Creazione di esperienze di apprendimento headless.
- Funzionalità avanzate di ricerca e filtraggio.

Per ulteriori informazioni, vedere [Connettore Accesso ai dati di formazione](/help/migrated/integration-admin/feature-summary/training-data-access-connector.md).

## Connettori di e-commerce e marketing

Questi connettori consentono la monetizzazione dei contenuti di apprendimento e l’integrazione con le piattaforme di automazione del marketing.

### Connettore Adobe Commerce

Il connettore Adobe Commerce trasforma Adobe Learning Manager in una piattaforma di e-commerce di apprendimento completa, consentendo alle organizzazioni di vendere corsi, certificazioni e programmi di formazione attraverso un&#39;esperienza di e-commerce completamente integrata.

**Funzionalità chiave:**

- Integrazione perfetta delle piattaforme di e-commerce.
- Gestione del catalogo dei corsi e dei prezzi.
- Elaborazione e iscrizione automatizzate dei pagamenti.

Per ulteriori informazioni, consulta [Connettore Adobe Commerce](/help/migrated/integration-admin/feature-summary/adobe-commerce-connector.md).

### Connettore Marketo Engage

Il connettore di Marketo Engage crea potenti sinergie tra le attività di apprendimento e le campagne di marketing, consentendo alle organizzazioni di sfruttare l&#39;impegno educativo per la formazione dei lead e lo sviluppo dei clienti.

#### Funzionalità principali:

- Creazione e aggiornamenti automatici dei lead.
- Monitoraggio delle attività di apprendimento per gli approfondimenti di marketing.
- Trigger eventi di completamento e iscrizione al corso.

Per ulteriori informazioni, consulta [Connettore Marketo Engage](/help/migrated/integration-admin/feature-summary/marketo-engage-connector.md).
