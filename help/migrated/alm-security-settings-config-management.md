---
title: Adobe Learning Manager - Impostazioni di sicurezza e gestione della configurazione
description: Questo documento descrive i tipi di account amministrativi di Adobe Learning Manager, le impostazioni relative alla protezione, le impostazioni predefinite protette consigliate, le funzionalità API, le funzionalità di esportazione, i metodi di confronto della configurazione, le procedure di pubblicazione e la cronologia delle versioni. Fornisce indicazioni dettagliate sul funzionamento degli account privilegiati, sulle relative implicazioni per la sicurezza e sul supporto della gestione della configurazione su tutta la piattaforma.
jcr-language: en-us
source-git-commit: 579573cbc1baaea2ac8e6ebf17f32c46624ea798
workflow-type: tm+mt
source-wordcount: '1940'
ht-degree: 0%

---


# Introduzione

Questa guida fornisce risposte dettagliate alle raccomandazioni FedRAMP (da FRR-RSC-03 a FRR-RSC-08) per Adobe Learning Manager (ALM). Descrive le procedure consigliate per la sicurezza, le impostazioni predefinite di protezione consigliate e gli strumenti per il controllo, l’esportazione e la gestione delle impostazioni degli account con privilegi. Il documento è progettato per gli amministratori e i team di conformità per garantire la configurazione e la gestione sicure degli account ALM.

Vengono inoltre evidenziate le aree in cui ALM soddisfa o soddisfa parzialmente gli standard FedRAMP, con riferimenti alla documentazione di supporto e alle risorse disponibili su Adobe Experience League.

+++Quali impostazioni relative alla sicurezza possono essere utilizzate solo da Amministratori personalizzati o Amministratori di integrazione in Adobe Learning Manager e quali sono le implicazioni per la sicurezza?

I due tipi di account privilegiati di Adobe Learning Manager: Amministratore personalizzato e Amministratore di integrazione. Ciascuna presenta un insieme definito di impostazioni relative alla sicurezza con implicazioni documentate.

**Amministratore personalizzato: funzionalità**:

* I ruoli personalizzati sono configurati dall&#39;amministratore completo in Amministratore ALM > Utenti > Ruoli personalizzati. A un amministratore personalizzato può essere concesso l’accesso a una o più delle seguenti categorie di autorizzazione: Privilegi di account (annunci, gamification, abilità, gestione utenti), Privilegi di funzionalità (cataloghi, report, tag) e Privilegi dell’oggetto di apprendimento (corsi, certificazioni, percorsi di apprendimento).
* L’impostazione relativa all’ambito è la più sensibile alla sicurezza: un ruolo personalizzato può essere limitato a gruppi di utenti e/o cataloghi specifici. Senza limitazioni di ambito, un ruolo personalizzato ha di fatto un accesso a livello di piattaforma alle funzionalità concesse, avvicinandosi all’impronta di un Amministratore completo.
* Se a un ruolo personalizzato viene concesso l&#39;accesso a Impostazioni in Privilegi account, l&#39;amministratore personalizzato può modificare i metodi di accesso, le impostazioni di notifica e le configurazioni a livello di account, un privilegio ad alto impatto che deve essere concesso solo con una giustificazione aziendale esplicita.

**Amministratore dell’integrazione - funzionalità**:

* Gli Amministratori di integrazione gestiscono le registrazioni delle applicazioni OAuth 2.0 in Amministratore di integrazione > Applicazioni > Registra. Selezionano uno dei sei ambiti OAuth, che vanno dall’accesso in lettura agli allievi all’accesso in lettura/scrittura al ruolo di amministratore. L’ambito di lettura/scrittura amministratore concede all’applicazione registrata gli stessi privilegi di un amministratore completo tramite API.
* Gli Amministratori di integrazione configurano i connettori FTP, SFTP, Salesforce, Workday e altri connettori che importano i record degli utenti, le assegnazioni dei ruoli e i completamenti dei corsi ed esportano i dati della piattaforma in sistemi esterni.
* Gli Amministratori di integrazione configurano i webhook che inviano i dati degli eventi ALM in tempo reale (iscrizioni, completamenti, modifiche al ruolo) agli URL esterni. Un endpoint del webhook compromesso o non configurato correttamente è un rischio di exfiltrazione dei dati.
* Gli Amministratori di integrazione possono configurare le integrazioni LTI. Una volta attivato, l’LTI non può essere disattivato.

**Riferimento**:

* [Ruoli personalizzati | Adobe Learning Manager](https://experienceleague.adobe.com/en/docs/learning-manager/using/admin/custom-role)
* [Gestione di ruoli personalizzati tramite CSV | Adobe Learning Manager](https://experienceleague.adobe.com/en/docs/learning-manager/using/integration/configure-role-csv-files)
* [Manuale per sviluppatori di applicazioni | Adobe Learning Manager][https://experienceleague.adobe.com/en/docs/learning-manager/using/integration/developer-manual]
* [Connettori Adobe Learning Manager](https://experienceleague.adobe.com/en/docs/learning-manager/using/integration/connectors)

+++

+++Quali sono le impostazioni predefinite sicure consigliate per gli account di livello superiore con privilegi e amministratore in Adobe Learning Manager e dove sono configurate?

Adobe Learning Manager documenta le impostazioni predefinite sicure consigliate per il ruolo di amministratore e per i tipi di account con privilegi.

* **Impostazioni predefinite account amministratore di primo livello (configurate al primo provisioning)**:

* Metodo di accesso per utenti interni: Single Sign-On (SSO) tramite SAML 2.0: configurato in Amministratore ALM > Impostazioni > Metodi di accesso. Non utilizzare Adobe ID per dipendenti o amministratori.
* Verifica in due fasi (2FA): applicata per tutti gli utenti: configurata in Adobe Admin Console > Impostazioni > Privacy e sicurezza > Impostazioni di autenticazione.
* Durata massima della sessione: 8 ore (o secondo la policy dell’organizzazione): configurato in Adobe Admin Console > Impostazioni > Privacy e sicurezza > Impostazioni avanzate.
* Tempo massimo di inattività: 30 minuti (o per policy dell&#39;organizzazione): stesso percorso come sopra.
* Eliminazione automatica degli utenti inattivi: attivata con un periodo di conservazione definito dall&#39;organizzazione (ad esempio, 90 giorni di inattività): Amministratore ALM > Impostazioni > Generale.
* Scadenza profilo utente esterno: impostata su ogni profilo esterno al momento della creazione: Amministratore ALM > Utenti > Esterno. Nessun profilo esterno indefinito.
* Limitazioni di accesso IP: limita agli intervalli IP approvati, ove possibile: Admin Console > Impostazioni > Impostazioni avanzate.

**Impostazioni predefinite ruolo Amministratore personalizzato (configurate durante la creazione di ogni ruolo)**:

* Ambito OAuth per le applicazioni registrate: ambito minimo richiesto. Non concedere mai al ruolo di amministratore l&#39;accesso in lettura/scrittura a meno che non sia strettamente necessario.
* Ambito del ruolo personalizzato: limita a gruppi di utenti e cataloghi specifici. Non creare ruoli personalizzati con ambito Tutti gli utenti e Tutti i cataloghi a meno che la funzione non lo richieda realmente.
* Accesso alle impostazioni nei ruoli personalizzati: non concedere a meno che la funzione specifica non lo richieda, dato il rischio di acquisizione illecita di privilegi.

**Impostazioni predefinite dell&#39;Amministratore di integrazione**:

* Ambito OAuth API: seleziona l’ambito più restrittivo che soddisfa i requisiti dell’integrazione. Non concedere autorizzazioni di lettura/scrittura da parte dell’Amministratore ad applicazioni che richiedono solo l’accesso in lettura da parte degli Allievi.
* Credenziali del connettore, credenziali LTI e URL del webhook: considera segreti riservati; non condividerli mai tramite e-mail o confermare il controllo del codice sorgente.

**Riferimento**:

* [Impostazioni | Adobe Learning Manager](https://experienceleague.adobe.com/en/docs/learning-manager/using/admin/custom-role)
* [Autenticazione utente e password sicure | Adobe Admin Console](https://helpx.adobe.com/enterprise/using/authentication-settings.html)
* [Ruoli personalizzati | Adobe Learning Manager](https://experienceleague.adobe.com/en/docs/learning-manager/using/admin/custom-role)

+++

+++Adobe Learning Manager offre agli amministratori un modo per confrontare le impostazioni dell’account corrente con le impostazioni predefinite di sicurezza consigliate?

Adobe Learning Manager non dispone di una dashboard di confronto dedicata che mostra automaticamente le impostazioni correnti insieme alle impostazioni di sicurezza consigliate.

**Report ruolo personalizzato: assegnazioni di ruolo con privilegi correnti**:

* In ALM, seleziona Amministratore > Utenti > Ruoli personalizzati e fai clic su Scarica (in alto a destra) per esportare un file CSV di tutti i ruoli personalizzati, i relativi set di autorizzazioni e le assegnazioni di ambito.
* Confrontate questa esportazione con le impostazioni predefinite consigliate nella sezione 8 di FRR-RSC-02: verificate in particolare se un ruolo personalizzato ha l&#39;accesso alle impostazioni, l&#39;ambito Tutti gli utenti o Tutti i cataloghi senza una giustificazione documentata.

**API REST ALM: recupero della configurazione a livello di codice**:

* L’endpoint GET /account restituisce i dati di configurazione a livello di account in formato JSON, accessibili tramite l’ambito OAuth del ruolo di amministratore. I clienti possono chiamare questo endpoint a livello di programmazione e modificare la risposta rispetto a una baseline derivata dai valori predefiniti consigliati nella sezione 8 di FRR-RSC-02.
* L&#39;endpoint GET /users (con filtro include=role) restituisce le assegnazioni di ruolo correnti per tutti gli utenti, consentendo il rilevamento automatico di assegnazioni di ruolo impreviste.

>[!NOTE]
>
>Adobe Learning Manager non offre un’interfaccia utente nativa di confronto affiancata. I clienti che richiedono il controllo automatico della conformità alla configurazione devono integrare l&#39;API REST ALM con gli strumenti esistenti.

**Riferimento**

* [Manuale per sviluppatori di applicazioni | Adobe Learning Manager](https://experienceleague.adobe.com/en/docs/learning-manager/using/integration/developer-manual)

+++

+++Gli amministratori possono esportare le impostazioni e le configurazioni correnti relative alla sicurezza da Adobe Learning Manager in un formato leggibile da un computer?

Adobe Learning Manager supporta l&#39;esportazione di dati di configurazione relativi alla sicurezza attraverso diversi meccanismi. Nessuna esportazione singola genera un’istantanea completa di tutte le impostazioni di sicurezza contemporaneamente, ma le esportazioni seguenti coprono collettivamente l’intero ambito dei dati relativi alla sicurezza.

**API REST ALM: esportazione JSON delle assegnazioni dei ruoli e della configurazione dell&#39;account correnti**:

* GET /account: restituisce le impostazioni a livello di account in JSON, inclusi i dati di configurazione di accesso attivi e i metadati dell’account.
* GET /users?include=role: restituisce tutti gli utenti con i ruoli attualmente assegnati in formato JSON.
* GET /userGroups: restituisce tutti i gruppi di utenti e la relativa appartenenza, rilevanti per il controllo dell&#39;ambito del ruolo personalizzato.
* Tutte le risposte API sono JSON (vnd.api+json). L’autenticazione utilizza OAuth 2.0 con ambito di lettura/scrittura del ruolo di amministratore.

**Esportazione CSV ruolo personalizzato: definizioni ruolo privilegiato corrente**:

* Amministratore ALM > Utenti > Ruoli personalizzati > Scarica esporta un file CSV con tutte le definizioni di ruolo personalizzate, le categorie di autorizzazioni e le assegnazioni di ambito.
* Questa esportazione può essere utilizzata come snapshot leggibile dal computer della configurazione corrente dell&#39;account con privilegi.
**

**API dei processi: dati utente e ruolo in blocco**:

* L’API dei processi ALM supporta la generazione su richiesta di report utente (incluse le assegnazioni di ruoli) in formato CSV. Questi possono essere pianificati e utilizzati da strumenti di conformità esterni o SIEM.

**Riferimento**

* [Manuale per sviluppatori di applicazioni | Adobe Learning Manager](https://experienceleague.adobe.com/en/docs/learning-manager/using/integration/developer-manual)

+++

+++Adobe Learning Manager fornisce un’API tramite la quale è possibile visualizzare e regolare a livello di programmazione le impostazioni relative alla sicurezza?

Adobe Learning Manager fornisce un’API REST v2 completa che consente la visualizzazione a livello di programmazione e la regolazione delle impostazioni relative alla sicurezza utilizzando l’autenticazione OAuth 2.0. Di seguito sono riportate le funzionalità API specifiche relative alle impostazioni di sicurezza:

**Autenticazione e ambito**:

* Le applicazioni vengono registrate dall’Amministratore di integrazione in Amministratore di integrazione > Applicazioni > Registra. ID client e segreto OAuth 2.0 vengono rilasciati per applicazione.
* Sono disponibili sei ambiti. Per la gestione delle impostazioni di sicurezza, è necessario l’accesso in lettura/scrittura al ruolo di amministratore. In questo modo, all’applicazione viene concesso lo stesso accesso di un amministratore completo tramite API.
* I token di accesso vengono ottenuti tramite il codice di autorizzazione OAuth standard o il flusso di credenziali client. URL di base: https://learningmanager.adobe.com/primeapi/v2/

**Gestione di utenti e ruoli tramite API**:

* GET /users: recupera tutti gli utenti e i relativi ruoli correnti
* POST /users: assegnazione di ruoli a livello di programmazione ai nuovi utenti
* PATCH /users/{id}: aggiornamento degli attributi utente, incluse le assegnazioni dei ruoli
* DELETE /users/{id}: disabilitare un account utente
* POST /users/{id}/purge: rimuovi definitivamente un utente e tutti i record associati

Recupero configurazione account:

* GET /account: restituisce la configurazione a livello di account, inclusi i dati delle impostazioni dell’account in formato JSON, inclusi campi come complianceLabelDefaultID, showComplianceLabel e custom_injections.

+++

+++Adobe Learning Manager pubblica la propria guida alla configurazione sicura in un formato leggibile da un computer come OSCAL, JSON o YAML?

Al momento Adobe Learning Manager non pubblica la Guida alla configurazione sicura in un formato leggibile dal computer. Le istruzioni in [FRR-RSC-01](/help/migrated/alm-administrative-lifecycle.md) e [FRR-RSC-02](/help/migrated/alm-secure-administration-guide.md) sono pubblicate come documentazione leggibile da persone in Adobe Experience League in formato HTML e documenti scaricabili.

Non esistono definizioni di componenti OSCAL, baseline YAML o file di criteri JSON pubblicamente disponibili che codificano i valori predefiniti di protezione consigliati per Adobe Learning Manager.

I clienti che necessitano di un confronto automatico delle impostazioni correnti rispetto alle baseline consigliate devono utilizzare l&#39;[API REST ALM](https://experienceleague.adobe.com/en/docs/learning-manager/using/integration/developer-manual) per recuperare i dati di configurazione correnti in formato JSON.

+++

+++La Guida alla configurazione sicura di Adobe Learning Manager è disponibile pubblicamente senza richiedere un accesso o un accesso speciale?

**Informazioni disponibili pubblicamente**:

* [FRR-RSC-01: Guida all&#39;amministrazione sicura](/help/migrated/alm-administrative-lifecycle.md): guida completa al ciclo di vita per gli account amministrativi di primo livello.
* [FRR-RSC-02: Impostazioni e implicazioni per la protezione amministrativa](/help/migrated/alm-secure-administration-guide.md): tutte le impostazioni relative alla protezione, le relative implicazioni e le impostazioni predefinite consigliate.
* FRR-RSC-03-10 (questo documento) — Risposte di domande e risposte a tutte e otto le raccomandazioni della FedRAMP.

+++

+++Adobe Learning Manager fornisce il controllo delle versioni e una cronologia delle versioni che consente alle agenzie di tenere traccia delle modifiche apportate nel tempo alle impostazioni relative alla sicurezza e alle impostazioni predefinite consigliate?

Per ogni aggiornamento del prodotto, Adobe Learning Manager mantiene a disposizione del pubblico una cronologia dettagliata delle versioni. In ogni versione sono documentate le modifiche relative alla sicurezza delle impostazioni amministrative, delle funzionalità di autenticazione, degli endpoint API e delle funzionalità di gestione dei ruoli.

**Note sulla versione di ALM: numerate, cronologia modifiche cumulative**:

* Adobe pubblica le note sulla versione numerate per ogni aggiornamento di Adobe Learning Manager (ad esempio, Aggiornamento 100, Aggiornamento 99). Questi sono pubblicati nell’Experience League e documentano tutte le nuove funzioni, le modifiche alle impostazioni esistenti, le aggiunte e le rimozioni API, le modifiche ai connettori e le funzionalità obsolete.
* Ogni nota sulla versione include una sezione dedicata alle modifiche API, che elenca nuovi endpoint, campi di risposta modificati e obsoleti, direttamente correlati alle funzionalità di configurazione relative alla sicurezza.

**Novità delle pagine: riepiloghi delle funzioni per ogni versione**:

* Ogni versione principale è dotata di una pagina dedicata denominata &quot;Novità&quot; che documenta le nuove funzioni relative alla sicurezza con il relativo contesto. Ad esempio, le note sulla versione includono le modifiche alla gestione delle autorizzazioni dei ruoli personalizzati, l’aggiunta della visibilità delle autorizzazioni create con CSV per i ruoli personalizzati e le modifiche relative alla limitazione della frequenza delle API.

**Elenco deprecazioni API: record autorevole delle funzionalità API rimosse** s:

* Adobe gestisce una pagina dedicata dedicata alle API obsolete che elenca tutti gli endpoint API ALM obsoleti e rimossi con la versione di rilascio in cui si è verificata ciascuna interruzione.

**Riferimento**:

* [Note sulla versione di Adobe Learning Manager](https://experienceleague.adobe.com/en/docs/learning-manager/using/introduction/release-notes)
* [Novità di Adobe Learning Manager](https://experienceleague.adobe.com/en/docs/learning-manager/using/introduction/whats-new-july-2024)
* [Rimozione delle API da Adobe Learning Manager](https://experienceleague.adobe.com/en/docs/learning-manager/using/introduction/api-deprecations-list)

+++

