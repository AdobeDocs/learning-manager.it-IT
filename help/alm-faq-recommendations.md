---
title: Ciclo di vita dell'account amministrativo Adobe Learning Manager
description: Questo documento fornisce un riepilogo completo delle funzionalità di gestione, configurazione e conformità dell'account di sicurezza ALM (Adobe Learning Manager) in linea con i consigli FedRAMP.
jcr-language: en-us
source-git-commit: 06051e44c0a6bc8ae60e44272ba088f2f6ff281f
workflow-type: tm+mt
source-wordcount: '1706'
ht-degree: 0%

---


# Consigli sulla sicurezza di Adobe Learning Manager

## Quali impostazioni relative alla sicurezza possono essere utilizzate solo da Amministratori personalizzati o Amministratori di integrazione in Adobe Learning Manager e quali sono le implicazioni per la sicurezza?

I due tipi di account privilegiati di Adobe Learning Manager, Amministratore personalizzato e Amministratore di integrazione, dispongono ciascuno di un insieme definito di impostazioni relative alla sicurezza con implicazioni documentate.

### Amministratore personalizzato: cosa può fare:

* I ruoli personalizzati sono configurati dall&#39;amministratore completo in Amministratore ALM > Utenti > Ruoli personalizzati. A un amministratore personalizzato può essere concesso l’accesso a una o più delle seguenti categorie di autorizzazione: Privilegi di account (annunci, gamification, abilità, gestione utenti), Privilegi di funzionalità (cataloghi, report, tag) e Privilegi dell’oggetto di apprendimento (corsi, certificazioni, percorsi di apprendimento).
* L’impostazione relativa all’ambito è la più sensibile alla sicurezza: un ruolo personalizzato può essere limitato a gruppi di utenti e/o cataloghi specifici. Senza limitazioni di ambito, un ruolo personalizzato ha di fatto un accesso a livello di piattaforma alle funzionalità concesse, avvicinandosi all’impronta di un Amministratore completo.
* Se a un ruolo personalizzato viene concesso l&#39;accesso a Impostazioni in Privilegi account, l&#39;amministratore personalizzato può modificare i metodi di accesso, le impostazioni di notifica e le configurazioni a livello di account, un privilegio ad alto impatto che deve essere concesso solo con una giustificazione aziendale esplicita.
* Un amministratore personalizzato con accesso alle impostazioni che dispone anche dell’accesso all’entità Utenti può assegnare a se stesso il ruolo di amministratore completo, passando a un controllo amministrativo completo.

### Amministratore dell’integrazione: cosa possono fare:

* Gli Amministratori di integrazione gestiscono le registrazioni delle applicazioni OAuth 2.0 in Amministratore di integrazione > Applicazioni > Registra. Selezionano uno dei sei ambiti OAuth, che vanno dall’accesso in lettura agli allievi all’accesso in lettura/scrittura al ruolo di amministratore. L’ambito di lettura/scrittura amministratore concede all’applicazione registrata gli stessi privilegi di un amministratore completo tramite API.
* Gli Amministratori di integrazione configurano i connettori FTP, SFTP, Salesforce, Workday e altri connettori che importano i record degli utenti, le assegnazioni dei ruoli, i completamenti dei corsi ed esportano i dati della piattaforma in sistemi esterni.
* Ambito OAuth per le applicazioni registrate: ambito minimo richiesto. Non concedere mai al ruolo di amministratore l&#39;accesso in lettura/scrittura a meno che non sia strettamente necessario.
* Gli Amministratori di integrazione configurano i webhook che inviano i dati degli eventi ALM in tempo reale (iscrizioni, completamenti, modifiche al ruolo) agli URL esterni. Un endpoint del webhook compromesso o non configurato correttamente è un rischio di exfiltrazione dei dati.
* Gli Amministratori di integrazione possono configurare le integrazioni LTI. Una volta attivato, l’LTI non può essere disattivato. Le credenziali LTI esposte consentono l’accesso non autorizzato al contenuto del corso da piattaforme LMS esterne.


## Quali sono le impostazioni predefinite sicure consigliate per gli account di livello superiore con privilegi e amministratore in Adobe Learning Manager e dove sono configurate?

### Impostazioni predefinite account amministratore di primo livello (configurate al primo provisioning):

* Metodo di accesso per utenti interni: Single Sign-On (SSO) tramite SAML 2.0: configurato in Amministratore ALM > Impostazioni > Metodi di accesso. Non utilizzare Adobe ID per dipendenti o amministratori.
* Verifica in due fasi (2FA): applicata per tutti gli utenti: configurata in Adobe Admin Console > Impostazioni > Privacy e sicurezza > Impostazioni di autenticazione.
* Durata massima della sessione: 8 ore (o secondo la policy dell’organizzazione): configurato in Adobe Admin Console > Impostazioni > Privacy e sicurezza > Impostazioni avanzate.
* Tempo massimo di inattività: 30 minuti (o per policy dell&#39;organizzazione): stesso percorso come sopra.
* Eliminazione automatica degli utenti inattivi: attivata con un periodo di conservazione definito dall&#39;organizzazione (ad esempio, 90 giorni di inattività): Amministratore ALM > Impostazioni > Generale.
* Scadenza profilo utente esterno: impostato su ogni profilo esterno al momento della creazione: Amministratore ALM > Utenti > Esterno. Nessun profilo esterno indefinito.
* Limitazioni di accesso IP: limita agli intervalli IP approvati, ove possibile- Admin Console > Impostazioni > Impostazioni avanzate.

### Impostazioni predefinite ruolo Amministratore personalizzato (configurate durante la creazione di ogni ruolo):

* Ambito OAuth per le applicazioni registrate: ambito minimo richiesto. Non concedere mai al ruolo di amministratore l&#39;accesso in lettura/scrittura a meno che non sia strettamente necessario.
* Ambito del ruolo personalizzato: limita a gruppi di utenti e cataloghi specifici. Non creare ruoli personalizzati con ambito Tutti gli utenti e Tutti i cataloghi a meno che la funzione non lo richieda realmente.
* Accesso alle impostazioni nei ruoli personalizzati: non concedere a meno che la funzione specifica non lo richieda, dato il rischio di acquisizione illecita di privilegi.

### Impostazioni predefinite Amministratore di integrazione:

* Ambito OAuth API: seleziona l’ambito più restrittivo che soddisfa i requisiti dell’integrazione. Non concedere autorizzazioni di lettura/scrittura da parte dell’Amministratore ad applicazioni che richiedono solo l’accesso in lettura da parte degli Allievi.
* Credenziali del connettore, credenziali LTI e URL del webhook: considera segreti riservati; non condividerli mai tramite e-mail o confermare il controllo del codice sorgente.

## Adobe Learning Manager offre agli amministratori un modo per confrontare le impostazioni dell’account corrente con le impostazioni predefinite di sicurezza consigliate?

Adobe Learning Manager non dispone di una dashboard di confronto dedicata che mostra automaticamente le impostazioni correnti insieme alle impostazioni di sicurezza consigliate. Tuttavia, le funzionalità di tre piattaforme consentono agli amministratori di controllare e confrontare le configurazioni correnti manualmente o a livello di programmazione.

### Report ruolo personalizzato - Assegnazioni di ruoli con privilegi correnti:

In ALM, seleziona Amministratore > Utenti > Ruoli personalizzati e fai clic su Scarica (in alto a destra) per esportare un file CSV di tutti i ruoli personalizzati, i relativi set di autorizzazioni e le assegnazioni di ambito.

### API REST ALM - Recupero della configurazione a livello di codice:

* L’endpoint GET /account restituisce i dati di configurazione a livello di account in formato JSON, accessibili tramite l’ambito OAuth del ruolo di amministratore. I clienti possono chiamare questo endpoint a livello di programmazione.
* L&#39;endpoint GET /users (con filtro include=role) restituisce le assegnazioni di ruolo correnti per tutti gli utenti, consentendo il rilevamento automatico di assegnazioni di ruolo impreviste. Utilizza l’API dei processi per le esportazioni degli utenti in blocco.

## Gli amministratori possono esportare le impostazioni e le configurazioni correnti relative alla sicurezza da Adobe Learning Manager in un formato leggibile da un computer?

Adobe Learning Manager supporta l&#39;esportazione di dati di configurazione relativi alla sicurezza attraverso diversi meccanismi. Nessuna esportazione singola genera un’istantanea completa di tutte le impostazioni di sicurezza contemporaneamente, ma le esportazioni seguenti coprono collettivamente l’intero ambito dei dati relativi alla sicurezza.

### Registro di controllo di Admin Console — Esportazione CSV di tutte le modifiche di autenticazione e ruolo:

* In Adobe Admin Console, seleziona **Insights > Registri > Registro di controllo**, applica i filtri secondo necessità e fai clic su **Esporta CSV**
* Il file CSV esportato registra ogni azione amministrativa, tra cui: modifiche dell&#39;imposizione 2FA, modifiche dei limiti di sessione, assegnazioni e rimozioni del ruolo di amministratore, eliminazioni di utenti e modifiche delle autorizzazioni del prodotto, il tutto con marche temporali e identità dell&#39;attore.
* I dati vengono conservati per 90 giorni. Gli utenti del Global Admin Console possono esportare i registri in tutte le organizzazioni.

### API REST ALM: esportazione JSON delle assegnazioni dei ruoli e della configurazione dell’account correnti:

* `GET /account`: restituisce le impostazioni a livello di account in JSON, inclusi i dati di configurazione di accesso attivi e i metadati dell&#39;account.
* `GET /users?include=role` — restituisce tutti gli utenti con i ruoli attualmente assegnati in JSON.
* `GET /userGroups`: restituisce tutti i gruppi di utenti e la relativa appartenenza, rilevanti per il controllo dell&#39;ambito del ruolo personalizzato.
* Tutte le risposte API sono JSON (`vnd.api+json`). L’autenticazione utilizza OAuth 2.0 con ambito di lettura/scrittura del ruolo di amministratore.

### Esportazione CSV ruolo personalizzato — definizioni di ruolo privilegiate correnti:

* Amministratore ALM > Utenti > Ruoli personalizzati > Scarica esporta un file CSV con tutte le definizioni di ruolo personalizzate, le categorie di autorizzazioni e le assegnazioni di ambito.
* Questa esportazione può essere utilizzata come snapshot leggibile dal computer della configurazione corrente dell&#39;account con privilegi.

### API dei processi: dati utente e ruolo in blocco:

* L’API dei processi ALM supporta la generazione su richiesta di report utente (incluse le assegnazioni di ruoli) in formato CSV. Questi possono essere pianificati e utilizzati da strumenti di conformità esterni o SIEM.

Per ulteriori informazioni, vedere [Manuale per sviluppatori di applicazioni di Adobe Learning Manager](https://experienceleague.adobe.com/en/docs/learning-manager/using/integration/developer-manual).

## Adobe Learning Manager fornisce un’API tramite la quale è possibile visualizzare e regolare a livello di programmazione le impostazioni relative alla sicurezza?

Adobe Learning Manager fornisce un’API REST v2 completa che consente la visualizzazione a livello di programmazione e la regolazione delle impostazioni relative alla sicurezza utilizzando l’autenticazione OAuth 2.0. Di seguito sono riportate le funzionalità API specifiche relative alle impostazioni di sicurezza:

### Autenticazione e ambito

* Le applicazioni vengono registrate dall’Amministratore di integrazione in **Amministratore di integrazione > Applicazioni > Registra**. ID client e segreto OAuth 2.0 vengono rilasciati per applicazione.
* Sono disponibili sei ambiti. Per la gestione delle impostazioni di sicurezza, è necessario l&#39;accesso in lettura/scrittura **del ruolo di amministratore.** In questo modo, all’applicazione viene concesso lo stesso accesso di un amministratore completo tramite API.
* I token di accesso vengono ottenuti tramite il codice di autorizzazione OAuth standard o il flusso di credenziali client.\
  **URL di base:**\
  `https://learningmanager.adobe.com/primeapi/v2/`

### Gestione di utenti e ruoli tramite API

* `GET /users` — recupero di tutti gli utenti e dei relativi ruoli correnti
* `POST /users`: provisioning di nuovi utenti a livello di programmazione
* `PATCH /users/{id}` — aggiornare gli attributi utente, incluse le assegnazioni dei ruoli
* `DELETE /users/{id}` — disabilita un account utente
* `POST /users/{id}/purge` - Rimozione definitiva di un utente e di tutti i record associati

### Recupero configurazione account

* `GET /account`: restituisce la configurazione a livello di account, inclusi i dati delle impostazioni dell&#39;account in formato JSON, inclusi i seguenti campi:
   * `complianceLabelDefaultID`
   * `showComplianceLabel`
   * `custom_injections`

### API di gestione utenti Adobe (livello Admin Console)

* L&#39;API UMAPI (User Management API) di Adobe consente l&#39;accesso a livello di codice alle operazioni di Admin Console:
   * Provisioning utente
   * Assegnazione autorizzazione prodotto
   * Assegnazione del ruolo di amministratore di sistema a livello di organizzazione
* UMAPI è separata dall’API REST ALM e opera a livello di organizzazione dell’Adobe. Utilizzalo per automatizzare le assegnazioni dei ruoli di Admin Console e il provisioning degli utenti.

## Adobe Learning Manager pubblica la propria guida alla configurazione sicura, ovvero le impostazioni predefinite consigliate, in un formato leggibile da un computer come OSCAL, JSON o YAML?

Al momento Adobe Learning Manager non pubblica la Guida alla configurazione sicura in un formato leggibile dal computer.

## La Guida alla configurazione sicura di Adobe Learning Manager è disponibile pubblicamente senza richiedere un accesso o un accesso speciale?

Sì. La Guida alla configurazione sicura di Adobe Learning Manager è disponibile pubblicamente su Adobe Experience League. Non è richiesto alcun account, login o licenza per accedervi.

Cosa è disponibile al pubblico:

* FRR-RSC-01: Guida all&#39;amministrazione sicura: guida completa al ciclo di vita per gli account amministrativi di livello toplel.
* FRR-RSC-02: Impostazioni e implicazioni per la sicurezza amministrativa: tutte le impostazioni rilevanti per la sicurezza, le relative implicazioni e le impostazioni predefinite consigliate.

## Adobe Learning Manager fornisce il controllo delle versioni e una cronologia delle versioni che consente alle agenzie di tenere traccia delle modifiche apportate nel tempo alle impostazioni relative alla sicurezza e alle impostazioni predefinite consigliate?

Per ogni aggiornamento del prodotto, Adobe Learning Manager mantiene a disposizione del pubblico una cronologia dettagliata delle versioni. In ogni versione sono documentate le modifiche relative alla sicurezza delle impostazioni amministrative, delle funzionalità di autenticazione, degli endpoint API e delle funzionalità di gestione dei ruoli.

### Note sulla versione di ALM - Cronologia delle modifiche numerate e cumulative

* Adobe pubblica le note sulla versione numerate per ogni aggiornamento di Adobe Learning Manager (ad esempio, *Aggiornamento 100*, *Aggiornamento 99*).
* Questi sono pubblicati nell&#39;**Experience League** e nel documento:
   * Nuove funzioni
   * Modifiche alle impostazioni esistenti
   * Aggiunte e rimozioni API
   * Modifiche al connettore
   * Funzionalità obsolete
* Ogni nota sulla versione include una sezione dedicata per **modifiche API**, che elenca:
   * Nuovi endpoint
   * Campi di risposta modificati
   * Obsoleti
   * Queste sono direttamente rilevanti per le capacità di configurazione relative alla sicurezza.

### Pagine &quot;Novità&quot;: riepiloghi delle funzioni per ogni versione

* Ogni versione principale dispone di una pagina **&quot;Novità&quot;** dedicata che documenta le nuove funzionalità relative alla sicurezza con il contesto.
* Esempi di aggiornamenti documentati relativi alla sicurezza includono:
   * Modifiche alla gestione delle autorizzazioni dei ruoli personalizzati
   * Aggiunta della visibilità delle autorizzazioni create con CSV per i ruoli personalizzati
   * Modifiche per la limitazione della velocità API

### Elenco deprecazioni API: record autorevole delle funzionalità API rimosse

* Adobe gestisce una pagina dedicata **API obsolete** che elenca tutti gli endpoint API ALM obsoleti e rimossi, inclusa la versione di rilascio in cui si è verificata ciascuna interruzione.
* Esempi di deprecazioni relative alla sicurezza includono:
   * Modifiche al comportamento di ordinamento e sostituzione dell&#39;endpoint `GET /users`
   * Requisiti di notifica, filtro data report

