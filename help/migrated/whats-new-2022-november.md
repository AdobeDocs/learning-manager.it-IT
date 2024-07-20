---
title: Novità di questa versione (novembre 2022)
description: Scopri le nuove funzioni e i miglioramenti in Adobe Learning Manager
hidefromtoc: true
exl-id: 2ccfb4e6-ba11-4657-8edb-3c527b4e5b9f
source-git-commit: a0c01c0d691429bd66a3a2ce4cfc175ad0703157
workflow-type: tm+mt
source-wordcount: '1994'
ht-degree: 77%

---

# Novità di questa versione (novembre 2022)

<!--
IN-PROGRESS

<https://helpx.adobe.com/learning-manager/whats-new-nov-2022.html>
-->

## Configurazione SSO multipla

Adobe Learning Manager supporta attualmente un metodo di accesso per utenti interni e uno per utenti esterni. Questo crea limitazioni nei casi in cui i clienti abbiano i propri dipendenti e i propri clienti e partner di canale sullo stesso account.

Con l’intento di supportare più tipi di gruppi di utenti che accedono alla piattaforma, Adobe Learning Manager ora supporta più metodi di accesso tramite più configurazioni SSO per utenti interni ed esterni.

Per ulteriori informazioni, consulta [Accessi SSO multipli](/help/migrated/administrators/feature-summary/multiple-sso-logins.md).

## Supporto di funzioni senza accesso

Il portale nativo di Adobe Learning Manager ora supporta la modalità di utilizzo del portale di formazione senza necessità di effettuare l’accesso.

Gli Allievi possono scoprire e accedere al sito di formazione, esplorare i vari contenuti disponibili e decidere di registrarsi per utilizzare i corsi.

Questa funzione semplifica la creazione di un portale di apprendimento rivolto ai clienti, in cui gli Allievi possono consultare vari corsi senza aver effettuato prima l’accesso.

Per ulteriori informazioni, consulta [Esperienza senza accesso per gli Allievi](/help/migrated/administrators/feature-summary/non-logged-in-experience-learners.md).

## Miglioramenti della pagina Panoramica sulla formazione

La pagina Panoramica sulla formazione presenta ora un’interfaccia utente aggiornata che consente agli Allievi di usufruire di un’esperienza migliorata mentre seguono un corso.

Altri miglioramenti includono:

* Aggiungi un corso di formazione ai segnalibri.
* Corsi correlati consigliati.
* Informazioni su corsi e percorsi di apprendimento.
* Nomi di autori cliccabili.
* Link di navigazione per maggiore facilità di utilizzo.

## Miglioramenti della pagina Panoramica sulla formazione

La pagina Panoramica sulla formazione presenta ora un’interfaccia utente aggiornata che consente agli Allievi di usufruire di un’esperienza migliorata mentre seguono un corso.

Altri miglioramenti includono:

* Aggiungi un corso di formazione ai segnalibri.
* Corsi correlati consigliati.
* Informazioni su corsi e percorsi di apprendimento.
* Nomi di autori cliccabili.
* Link di navigazione per maggiore facilità di utilizzo.

## Pagina Profilo autore

La pagina del profilo dell’autore mostra tutti i corsi di formazione creati da un determinato autore.

Gli Allievi possono trovare facilmente informazioni specifiche dell’autore e tutti i corsi di formazione creati dallo stesso.

## Corsi di formazione aggiunti ai segnalibri

Gli allievi possono salvare (con il pulsante Salva) o aggiungere ai segnalibri i corsi di formazione dal riquadro del corso o dalla pagina con la panoramica. Tutti i corsi contrassegnati sono disponibili nella pagina principale dell’Allievo.

## Personalizzazione del lettore

In questa versione, puoi personalizzare il lettore Fluidic in base ai requisiti di branding di un corso.

Puoi mostrare e nascondere diverse impostazioni e opzioni del lettore in base ai requisiti di contenuto e concedere il controllo agli Allievi in base al tipo di contenuto. Questa modifica può essere applicata sia a implementazioni native che headless.

Le varie opzioni che puoi modificare includono:

* Attivazione/disattivazione del sommario
* Note
* Lingua
* Velocità
* Didascalia
* Volume
* Controlli di riproduzione

## Impersonificazione dell’Allievo e del Manager

Gli amministratori possono avviare una sessione impersonata, vale a dire una sessione in cui possono accedere nel proprio account per conto di qualsiasi utente nei ruoli Allievo e Manager.

Per ulteriori informazioni, consulta [Impersonificazione dell’Allievo e del Manager](/help/migrated/administrators/feature-summary/impersonation-learner-manager.md).

## Altri miglioramenti

### Registro di controllo delle e-mail

Gli amministratori possono ora accedere a tutti i registri e-mail inviati dal sistema tramite un report di audit trail via e-mail.

Questo registro raccoglie tutti i dati relativi alle e-mail inviate negli ultimi 30 giorni e viene aggiornato a cadenza quotidiana. Il report contiene anche informazioni, come quelle sullo stato di consegna, sul mittente, sul destinatario, sull’oggetto e sui metadati del contenuto.

Scarica il report da Report > Report personalizzati > Report Excel > Report e-mail. Viene visualizzata una notifica che consente di scaricare il report.

Questo report comprende i seguenti campi:

* Orario di invio dell’email (fuso orario UTC)
* Ora dello stato dell’ultimo evento (fuso orario UTC)
* Stato di consegna
* E-mail destinatario
* ID utente mittente
* Oggetto dell’e-mail
* Tipo di entità
* Nome entità
* ID entità

### Notifica Allievo in lista d’attesa

Quando un autore aggiunge una nuova istanza, può attivare un’e-mail per informare gli Allievi in lista d’attesa delle altre istanze. Gli Allievi ricevono un’e-mail con la modifica.

### Modelli e-mail a livello di istanza

Puoi personalizzare le e-mail per ciascuna istanza di un corso di formazione.

Nei casi in cui l’Autore o l’Amministratore è autorizzato ad aggiungere una nuova istanza, il modello di una singola istanza può essere modificato.

Ad esempio, se un corso ha tipi di pubblico diversi, puoi modificare il modello e-mail di conseguenza.

![modelli e-mail](assets/email-template.png)

Di seguito è riportata la priorità del modello:

1. Modello a livello di istanza
2. Modello a livello di corso di formazione
3. Modello a livello di account

### Commenti dell’istruttore durante l’accettazione dei contenuti inviati

Gli istruttori ora possono aggiungere commenti quando accettano i contenuti inviati dagli Allievi. L’Allievo riceve una notifica e-mail e una notifica in-app (se ha attivato questo tipo di notifiche) dopo l’approvazione, da parte dell’istruttore, del contenuto inviato. I commenti relativi ai contenuti inviati sono presenti nelle Trascrizioni Allievi sia per gli Amministratori che per gli Allievi.

### Miglioramenti relativi alla ricerca

La cronologia delle ricerche recenti di un discente viene visualizzata in modo che possa vedere tutte le ricerche passate.

I risultati della ricerca sono ora coerenti in tutto l’apprendimento formale e informale (apprendimento sociale). I risultati includono la formazione, l’apprendimento sociale e le corrispondenze con il marketplace dei contenuti.

La ricerca è più focalizzata e mirata, in cui puoi visualizzare i risultati della ricerca in tre punti: apprendimento formale, apprendimento sociale e Content Marketplace.

![ricerca](assets/search-image.png)

#### Ricerca basata sulle frasi

In questa versione di Adobe Learning Manager, abbiamo sostituito la ricerca Typeahead con la ricerca basata su frase.

#### Ricerche recenti

Uno studente può visualizzare le ricerche recenti solo nella sessione corrente.

### Catalogo dei corsi gratuiti per il marketplace dei contenuti

Nel marketplace dei contenuti è ora disponibile per gli Allievi un set di 50 corsi selezionati, di alta qualità e gratuiti.

### Supporto per la lingua indonesiana

Il Bahasa Indonesia è stato aggiunto come lingua di interfaccia nelle app per Allievi e Manager.

### Campo Autore obbligatorio

Durante la creazione di un corso, il campo Autore è obbligatorio.

### Modifiche del marketplace dei contenuti

* Gli account di prova appena creati vedranno nel marketplace dei contenuti un nuovo catalogo di 50 corsi gratuiti e immediatamente disponibili per gli utenti.
* Un Allievo può ora vedere il numero di risultati della ricerca e collegare i collegamenti incorporati per il reindirizzamento al marketplace dei contenuti.

### Modifiche all’app immersiva per dispositivi mobili

In questa versione, gli utenti Web su dispositivi mobili possono eseguire le attività elencate di seguito:

* Creare - Post sondaggi
* Modificare post - tutti i tipi, RTE
* Flusso di lavoro per l’e-commerce.
* Anteprima di un modulo: gli Allievi avranno la funzione Anteprima modulo in Mobile Immersive. Questa modifica consentirà agli Allievi di visualizzare in anteprima il modulo prima dell’iscrizione a un corso.
* Copiare un URL.
* Eliminare una bacheca.

### Modifiche al connettore zoom

Il tipo di app JWT diventerà obsoleto a giugno 2023. Ti consigliamo di creare app OAuth o da server a server OAuth per sostituire le funzionalità di un’app JWT nel tuo account.

### Report per gamification

In questa versione, puoi accedere a un report che mostra i diversi corsi in cui era abilitata la gamification.

### Importa la lingua desiderata tramite CSV

Quando importi un file CSV, il file CSV contiene i campi Interface Language (lingua dell’interfaccia), Content Language (lingua del contenuto) e Time Zone (fuso orario).

L’Amministratore può anche esportare il report, che contiene gli stessi campi.

* Lingua dell’interfaccia
* Lingua del contenuto
* Fuso orario

Oltre agli amministratori, questo report può essere esportato anche da un amministratore personalizzato.

![report lingua](assets/language-report.png)

#### Impatto sulla localizzazione

* I nomi delle colonne non possono essere localizzati e devono rimanere come sono (Interface Language, Content Language, Timezone).
* I codici dei locali non fanno distinzione tra maiuscole e minuscole.
* Sebbene non vi siano restrizioni sull’inserimento del codice del paese, è possibile specificare solo il codice della lingua. Ad esempio, sono validi sia &quot;it_IT&quot; che &quot;it&quot;.
* In caso di discrepanza nel report a causa di un codice locale errato, l’elaborazione del file CSV prosegue come di consueto, e non influisce sugli altri record del file CSV. La preferenza del locale di un utente con un locale errato non viene aggiornata. Il resto dei dati viene aggiornato.

## Modifiche e miglioramenti delle API

### Connettori VC

Se per configurare il connettore VC viene utilizzato un ID e-mail dell’amministratore, tale amministratore deve disporre delle autorizzazioni necessarie per:

* Creare una riunione
* Aggiornare una riunione
* Recuperare il report di partecipazione

Durante la creazione o l’aggiornamento della riunione VC, gli istruttori devono TERMINARE la riunione entro 30 minuti dall’orario di fine previsto dell’incontro.

### Applicazione di segnalibri

Le API seguenti vengono aggiunte per contrassegnare un corso nella pagina Panoramica del corso di formazione:

* Ottieni tutti i segnalibri: `primeapi/v2/bookmarks`
* Crea segnalibro: `primeapi/v2/learningObjects/{id}/bookmark`
* Eliminare un segnalibro: `primeapi/v2/learningObjects/{id}/bookmark`

### Supporto per metadati e contenuti multiconali tramite migrazione

Per tutti i tipi di contenuti e corsi di formazione supportati dalla piattaforma (corsi, percorsi di apprendimento, moduli, certificazioni e risorse formative), può ora essere supportata la migrazione multilingue tramite file CSV con colonne aggiuntive per altre lingue.

#### Prerequisiti

Crea il progetto di migrazione come Amministratore dell’integrazione, quindi condividi migrationProjectId con il team di supporto ALM, in modo che il flag delle impostazioni internazionali multiple possa essere abilitato dal back-end.

#### Ambito degli oggetti di migrazione per più impostazioni locali

* Modulo
* Corso
* Versione modulo
* Certificazione
* Programma di apprendimento
* Risorsa formativa
* Versione risorsa formativa

#### Specifica CSV

Adobe Learning Manager offre una serie di specifiche CSV standard per la migrazione basata su impostazioni internazionali multiple. È consigliabile prendere visione delle specifiche CSV prima di avviare il processo di migrazione. L’amministratore dell’integrazione dell’organizzazione può analizzare i formati di dati esistenti e mapparli per farli coincidere con gli elementi del modello CSV forniti dal Learning Manager.

#### Modifiche con supporto per più impostazioni internazionali

* La colonna module_version non è supportata in module_version.csv e course_module.csv.
* Impossibile aggiornare il file module_version nella stessa esecuzione (nello stesso modulo non è possibile migrare due versioni con lo stesso modulo).
* L’aggiornamento di contenuto o metadati è considerato come aggiornamento della versione del modulo dal file csv module_version.
* Impossibile supportare l’aggiornamento Job_Aid_Version tramite job_aid_version.csv

### Revocare token di autenticazione e cookie

Un’applicazione LMS headless riceve il parametro refresh_token al primo accesso. Successivamente, refresh_token viene utilizzato per generare access_token per le applicazioni client per effettuare chiamate API. Analogamente, la riproduzione dei contenuti utilizza un endpoint oauth per generare i cookie e gestire la riproduzione che coinvolge più file di contenuti e chiamate API, richiamate da tali file utilizzando i cookie. Il cookie generato da oauth ha la stessa validità dell’access_token, ovvero sette giorni. Una volta generato il cookie, non c’è modo di cancellarlo a differenza del tipico logout dall’applicazione Web. I cookie Oauth e i cookie delle applicazioni Web sono due cookie diversi e non sono consapevoli l’uno dell’altro.

Quindi, per cancellare il cookie, abbiamo introdotto un nuovo endpoint, che revoca refresh_token, cookie e refresh token e cookie.

**Dettagli**

**Endpoint**

`POST oauth/o/revoke`

**Parametri di query**

* `cookie=true|false` - indica che il cookie deve essere revocato
* `refresh_token=true|false` - indica l&#39;aggiornamento

**Corpo della richiesta**

Corpo richiesto per revocare refresh_token o (refresh_token e cookie)

```
{
      "client_id": <>,
      "client_secret": <>,
      "refresh_token": <>
}
Body required for revoking oauth cookie only
{
      "access_token": <>
}
```

### API rese pubbliche

In questa versione, sono state rese pubbliche alcune API.

| API | Tipo | Descrizione |
|---|---|---|
| /social/search | GET | Cerca nei social. |
| /announcements | GET | Ottieni informazioni dettagliate sull’annuncio sul masthead assegnato all’Allievo. |
| /announcements/`{id}` | GET | Ottieni informazioni dettagliate sull’annuncio sul masthead assegnato all’Allievo. |
| /learningObjects/`{id}`/loResources/{loResourcesId} | GET | Carica l’URL del file per loResource di resourceType &#39;Activity&#39; in cui è richiesto l’invio del file. |
| /jobAid/`{jobAidId}`/jobAidDownloaded | GET | Imposta il report di download della risorsa formativa. |
| /bulkimport/startrun | POST | Esegui l’importazione in blocco. |
| /bulkimport/cansync | GET | Sincronizza importazione in blocco. |
| /ricerca | GET | DELETEMEBOB |
| /uploadInfo | GET | Ottieni informazioni relative all’aggiornamento dei contenuti. |
| /uploadSigner | GET | Ottieni la firma del contenuto to_sign. |
| /avatar | POST | Aggiorna l’avatar dell’Allievo con una nuova immagine. |
| /avatar | DELETE | Elimina l’avatar dell’Allievo. |

### App Salesforce

L’opzione **Ignora gli oggetti di apprendimento di ordine superiore** deve essere abilitata nell’app Salesforce in modo che tutti i corsi, i programmi di apprendimento e i certificati possano essere visualizzati contemporaneamente.

### API per la personalizzazione del lettore

In questa versione, sono disponibili API per personalizzare un lettore. È possibile:

* Avviare o caricare il lettore;
* Passare a un modulo particolare;
* Attiva/disattivare il sommario;
* Cambiare lingua;
* Chiudere il lettore;
* Riprodurre, mettere in pausa, andare avanti o indietro, cercare, regolare il volume o cambiare la velocità;
* Acquisire gli eventi emessi dal lettore.

### Visualizzazione della posizione nella lista di attesa di un Allievo

L’API GET /enrollments/{id}/waitlistPosition sotto l’API LO recupera la posizione in lista d’attesa di un utente per una specifica iscrizione.

### Invio della data di completamento in certificazioni esterne

L’API /primeapi/v2/learningObjects/certification:xxxxx con attributo “completionDateSameAsApprovalDate” indica che nel certificato l’opzione “Data di completamento della certificazione” è abilitata per l’Allievo o non corrisponde al flag true/false.

### Ottenimento dei dati di anteprima LO

L’API GET /preview/learningObjects/{id} viene aggiunta per ottenere informazioni di anteprima su un oggetto di apprendimento.

### Spostamento degli utenti esterni all’interno dei profili

La chiamata `PUT primeapi/v2/externalProfiles/{currentep}/users/{userid}?` consente di spostare un utente in un altro profilo esterno specificando un nuovo ID externalProfile.

### Aggiunta di utenti a profili esterni

`POST /externalProfiles/{id}/users` aggiunge utenti esterni al profilo esterno.

## Note sulla versione

Per informazioni sulle versioni correnti e precedenti dell’app Web e per dispositivi di Learning Manager, consulta le [Note sulla versione](/help/migrated/release-note/release-notes.md).

## Correzioni di bug

Per visualizzare i bug risolti in questo aggiornamento, consultare l&#39;[elenco Bug corretti](release-note/release-notes.md#bugs-fixed-in-this-release).

## Requisiti di sistema

[Requisiti di sistema di Learning Manager](/help/migrated/system-requirements.md)
