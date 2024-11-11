---
description: Scopri le nuove funzioni e i miglioramenti nella versione di novembre 2024 di Adobe Learning Manager
jcr-language: en_us
title: Riepilogo delle nuove funzioni
source-git-commit: bfe77d838340f94e072f9d7346576e3034a66a66
workflow-type: tm+mt
source-wordcount: '3133'
ht-degree: 2%

---

# Riepilogo delle nuove funzioni {#new-features-summary}

Scopri le nuove funzioni e i miglioramenti nella versione di novembre 2024 di Adobe Learning Manager.

* **Ricerca basata sull&#39;intelligenza artificiale:** combina ricerca lessicale e semantica per risultati più intelligenti e sensibili al contesto.
* **Webhook**: si integra con i webhook per inviare informazioni in tempo reale a URL specifici.
* **Interoperabilità degli strumenti di apprendimento (LTI)**: supporta LTI per l&#39;interoperabilità con altre piattaforme LMS.
* **Integrazione sicura**: gestione e condivisione di distintivi esterni tramite Creded.
* **Miglioramenti della dashboard di conformità**: condividi i dashboard con altri amministratori e imposta i widget di conformità predefiniti nelle home page degli Allievi.
* **Supporto multilingue**: crea istanze specifiche della lingua per i moduli Aula e Aula virtuale.
* **Ruoli personalizzati**: controllo avanzato sui ruoli utente e sulle autorizzazioni.
* **Commenti di completamento**: aggiungi commenti quando contrassegni gli Allievi come completati.
* **Report gruppo utenti**: gestisci i gruppi di utenti con report dettagliati.
* **Report lista d’attesa**: scarica l’elenco degli allievi in lista d’attesa per le istanze del corso.
* **Miglioramenti a livello di accessibilità**: supporto per testo alternativo nei masthead e nei loghi aziendali.
* **Supporto per Hindi**: supporto della lingua di interfaccia per l&#39;hindi.
* **Controllo della propaganda**: blocca i post social contenenti parole vietate.
* **Ottimizzazione dei modelli e-mail**: modelli e-mail combinati e ottimizzati per assegnazioni di istruttori e annullamenti di sessioni.
* **Criteri di completamento MS Teams**: imposta il tempo minimo di partecipazione alle sessioni VILT.
* **Nuovi flussi di lavoro di migrazione**: le modifiche alla migrazione includono i criteri di completamento per corsi e moduli e la migrazione dei moduli nelle cartelle.

## Ricerca basata sull&#39;intelligenza artificiale in Adobe Learning Manager

Adobe Learning Manager sta rinnovando il modo in cui gli Allievi cercano corsi o corsi di formazione. Introduce una funzionalità di ricerca basata sull&#39;intelligenza artificiale che combina ricerca lessicale e semantica. La ricerca è ora più intelligente, in quanto cerca termini specifici e comprende il contesto e l’intento che li sottendono. La ricerca avanzata comprende il significato della query e fornisce risultati rilevanti. Identifica l&#39;obiettivo principale della ricerca per fornire la serie di risultati più completa.

Per ulteriori informazioni, consultare questo articolo [Ricerca avanzata](/help/migrated/learners/feature-summary/advanced-search.md).

## Webhook

Adobe Learning Manager consente l’integrazione con i webhook per inviare informazioni in tempo reale, come iscrizioni a corsi, creazione di corsi e altre informazioni, a un URL specifico.

Un webhook in ALM consente a un&#39;entità di inviare automaticamente i dati a un&#39;altra applicazione tramite HTTP. Ciò consentirà a un&#39;applicazione di fornire informazioni ad altre applicazioni senza richiederle costantemente. Ad esempio, se un utente completa un corso LMS (Learning Management System), un webhook può inviare automaticamente tali informazioni a un’altra piattaforma, ad esempio un CRM o uno strumento di reporting. I webhook sono spesso utilizzati nelle integrazioni per automatizzare i processi e ridurre la necessità di aggiornamenti manuali tra i sistemi. Configura i webhook fornendo un URL di richiamata a cui invieresti i dati.

Per ulteriori informazioni, fai riferimento a questo articolo [Webhook](/help/migrated/integration-admin/feature-summary/webhooks.md).

## Interoperabilità degli strumenti di apprendimento

Adobe Learning Manager ora supporta l’LTI per migliorare l’interoperabilità tra Adobe Learning Manager e altri sistemi di gestione dell’apprendimento (LMS).

### Che cos&#39;è l&#39;LTI?

L’LTI (Learning Tools Interoperability) è uno standard che consente a strumenti e fornitori di contenuti di terze parti di connettersi con un sistema di gestione dell’apprendimento (LMS). Gli utenti possono accedere a contenuti di apprendimento esterni da fornitori di contenuti esterni direttamente all’interno del proprio LMS senza accedere o passare a un LMS diverso.

LTI come fornitore di strumenti: LTI come fornitore di strumenti consente ai sistemi esterni di integrarsi con un LMS. Adobe Learning Manager funge da provider di strumenti LTI, consentendo ad altre piattaforme LMS di accedere a corsi, certificati o percorsi di apprendimento da Adobe Learning Manager direttamente all’interno dell’LMS.

LTI come utente di strumenti: LTI come utente di strumenti consente a LMS di integrare strumenti esterni tramite l’interoperabilità degli strumenti di apprendimento (LTI). In questo scenario, LMS è un consumatore di servizi forniti da strumenti esterni. Adobe Learning Manager funge da utente di strumenti LTI e consente di integrare strumenti di apprendimento di terze parti. Ciò consente agli Allievi Adobe Learning Manager di utilizzare i corsi, i certificati o i percorsi di apprendimento degli strumenti di terze parti all’interno di Adobe Learning Manager.

Per ulteriori informazioni, fai riferimento a questo articolo [Interoperabilità dello strumento di apprendimento](/help/migrated/integration-admin/feature-summary/learning-tools-interoperability.md).

## Credendo

Tramite l’utilizzo di Creded, un amministratore in ALM consente agli allievi di gestire e condividere distintivi esterni dalla piattaforma su vari canali di social media.

### Cos&#39;è Creded?

Creded è una piattaforma di credenziale digitale che consente agli Allievi e alle organizzazioni di ottenere, condividere e verificare i risultati professionali, ad esempio distintivi o certificazioni. Gli Allievi possono gestire e condividere i distintivi tramite il proprio profilo Crely sui social media e in altri luoghi.

### Integrazione di Creded con Adobe Learning Manager

Per prima cosa, aggiungi il connettore Creded in Adobe Learning Manager (ALM). Quindi, migra i distintivi esistenti da Creded per garantire la continuità dei risultati degli Allievi. Infine, crea un’abilità in Adobe Learning Manager per il percorso di apprendimento appropriato per migliorare lo sviluppo e il riconoscimento degli Allievi.

Per ulteriori informazioni, fai riferimento a questo articolo [In modo creativo](/help/migrated/integration-admin/feature-summary/credly-integration.md)

## Dashboard di conformità

In questa versione, gli amministratori possono ora condividere la dashboard con altri amministratori, amministratori personalizzati e manager dei punti vendita, fornendo loro l’accesso immediato ai dashboard di conformità. Ora possono impostare il widget di conformità predefinito sulla pagina principale dell’Allievo, consentendo agli Allievi di monitorare i propri requisiti di conformità. Per ulteriori informazioni, consultare questo articolo [Dashboard di conformità](/help/migrated/administrators/feature-summary/reports.md#share-compliance-dashboard-with-admins-and-custom-admins).

## Supporto multilingue

Adobe Learning Manager (ALM) ora consente agli Autori di creare istanze specifiche della lingua utilizzando i tag della lingua per i moduli Aula e Aula virtuale. Gli Allievi possono accedere ai moduli di videoconferenza/videoconferenza nella lingua preferita. Ad esempio, un autore può creare un modulo CR/VC con due istanze: una in inglese e una in francese. Gli Allievi possono selezionare le istanze nella lingua preferita.

Per ulteriori informazioni, fai riferimento a questo articolo [Aggiungere oggetti di apprendimento in lingue diverse](/help/migrated/authors/feature-summary/add-new-language-learning-objects.md#multi-language-support-for-crvc-instances-with-language-tagging).

## Ruoli personalizzati

I ruoli personalizzati consentono agli amministratori di definire ruoli e responsabilità specifiche per diversi gruppi di utenti, garantendo una migliore gestione e un migliore controllo. Con questa versione, ALM migliora i ruoli personalizzati fornendo un controllo più dettagliato sulle sezioni seguenti.

* Utenti
* Corsi
* Percorsi di apprendimento
* Certificazioni
* Risorse formative
* Cataloghi

Gli amministratori possono assegnare autorizzazioni precise in base alle responsabilità degli utenti, garantendo che ogni gruppo abbia accesso solo alle funzionalità e ai contenuti pertinenti. Questi controlli avanzati consentono una gestione più granulare delle sezioni principali.

Accedi come amministratore e passa a **[!UICONTROL Utenti]** > **[!UICONTROL Ruoli personalizzati]** per creare e gestire i ruoli personalizzati.

Per ulteriori informazioni, consultare questo articolo [Ruoli personalizzati](/help/migrated/administrators/feature-summary/custom-role.md).

## Commenti di completamento

Gli amministratori ora possono aggiungere commenti quando contrassegnano gli Allievi come completi in corsi, percorsi di apprendimento o certificazioni. Gli amministratori possono aggiungere commenti per uno o più Allievi contemporaneamente e i commenti vengono visualizzati nel report [Trascrizioni Allievi](/help/migrated/administrators/feature-summary/reports.md#learner-transcripts).

Per ulteriori informazioni, consultare questo articolo [Commenti di completamento](/help/migrated/administrators/feature-summary/courses.md#completion-comments).

## Report gruppo utenti

Il nuovo **[!UICONTROL Report gruppo utenti]** di Adobe Learning Manager consente di gestire i gruppi di utenti fornendo visibilità sui gruppi non gestiti quando gli amministratori se ne sono andati. Gli amministratori possono accedere ai report nella sezione **[!UICONTROL Utenti]** > **[!UICONTROL Gruppo di utenti]**. Fornisce informazioni dettagliate su ciascun gruppo, tra cui:

* Tipo di gruppo di utenti
* Nome gruppo
* Descrizione
* Creato da (nome)
* Creato da (e-mail)
* Creato il (fuso orario UTC)
* Numero di utenti

Per ulteriori informazioni, fai riferimento a questo articolo [Report gruppo utenti](/help/migrated/administrators/feature-summary/add-users-user-groups.md#user-group-report).

## Report lista d’attesa

Il nuovo **[!UICONTROL Report della lista d’attesa]** di Adobe Learning Manager consente agli amministratori di scaricare l’elenco degli allievi in lista d’attesa per tutte le istanze di un corso. Gli amministratori e gli istruttori possono accedere a questo report dalla sezione **[!UICONTROL Lista d&#39;attesa]** del **[!UICONTROL corso]** o dalla pagina della **[!UICONTROL panoramica della sessione]**. Il rapporto sulla lista d’attesa può essere scaricato dalle sezioni Amministratore e Istruttore.

Seguire le colonne disponibili nel report Lista d&#39;attesa:

* Nome del corso
* Nome istanza
* ID istanza
* Stato istanza
* Nome utente
* E-mail
* ID univoco utente
* Data di iscrizione (fuso orario UTC)
* Stato
* Numero di lista d’attesa
* Limite per la lista d’attesa
* Posti limitati

Per scaricare il report dalla sezione Amministratore e istruttore, fai riferimento a questi articoli [Report della lista d’attesa](/help/migrated/administrators/feature-summary/courses.md#waitlist-report) e [Report della lista d’attesa](/help/migrated/instructors/feature-summary/learners.md#waitlist-report).

## Accessibilità nella pagina principale dell’Allievo

Adobe Learning Manager ora supporta il testo alternativo per tutti i masthead per migliorare l’accessibilità per gli Allievi. Ciò consente agli Allievi con esigenze particolari di utilizzare gli assistenti vocali per leggere il testo alternativo e comprendere l’immagine. Potete selezionare più lingue e fornire testo alternativo per ogni lingua. Assicurati di aggiungere il testo alternativo nelle rispettive lingue. Assicurati che il logo aziendale nel tuo account includa anche testo alternativo con il nome dell’azienda.
Per ulteriori informazioni, fai riferimento a questo articolo [Annuncio](/help/migrated/administrators/feature-summary/announcements.md#masthead).

## Supporto per hindi

Adobe Learning Manager ora introduce l&#39;hindi come una delle lingue di interfaccia della piattaforma e supporta la crescita della piattaforma in India. Il supporto per le lingue hindi native garantisce che tutte le funzioni, i report e l’esperienza utente complessiva siano completamente accessibili agli utenti.

Per cambiare la lingua dell’interfaccia, effettua le seguenti operazioni:

1. Accedi come **[!UICONTROL Amministratore]**.
2. Vai a **[!UICONTROL Impostazioni profilo]** > **[!UICONTROL Lingua interfaccia]**.
3. Selezionare **[!UICONTROL Hindi]** come lingua dell&#39;interfaccia.


## Verifica della fanità per i post social

Adobe Learning Manager ora blocca i post social nell’app per Allievi che contengono parole vietate. Questo aiuta a mantenere le cose professionali e conformi, soprattutto in settori sensibili come la sanità.

## Ottimizzazione dei modelli e-mail

### Inviare e-mail agli Allievi quando viene assegnato un Istruttore

Le e-mail esistenti **[!UICONTROL Ti hanno aggiunto come Istruttore]** e **[!UICONTROL Dettagli della sessione VCProvider]** sono stati combinati in un&#39;unica e-mail **[!UICONTROL Ti hanno aggiunto come UserType]**. **[!UICONTROL UserType]** sarà **[!UICONTROL Instructor]** o **[!UICONTROL Organizer]**, in base al ruolo dell&#39;utente. Queste e-mail non erano disponibili nell&#39;interfaccia utente prima. Sono stati combinati in un unico messaggio e-mail e aggiunti all’interfaccia utente. Gli amministratori possono accedere a questo modello nella sezione **[!UICONTROL Modello e-mail]**. Verrà abilitato per impostazione predefinita per tutti gli account nuovi ed esistenti, ma gli amministratori possono disabilitarlo o abilitarlo dalla stessa sezione. Questo messaggio e-mail verrà inviato ogni volta che viene creata una sessione e viene assegnato un istruttore, che si tratti di sessioni come Zoom, Teams, Connect o altri servizi.

### Inviare e-mail agli Allievi quando una sessione viene annullata

Gli istruttori rimossi da una sessione riceveranno ora solo un’e-mail di annullamento della sessione. In precedenza, hanno ricevuto sia un&#39;e-mail di annullamento che un&#39;e-mail di aggiornamento. Gli istruttori che rimangono in una sessione riceveranno un’e-mail di aggiornamento della sessione con un nuovo invito.

## Criteri di completamento MS Teams

Attualmente, gli Allievi risultano partecipanti anche se partecipano a una sessione di formazione virtuale con istruttore (VILT) per pochi secondi. Con questa versione, abbiamo introdotto i criteri di completamento per i moduli Teams per garantire una partecipazione più accurata. Gli Autori possono ora impostare il tempo minimo che gli Allievi devono trascorrere in una sessione VILT affinché la loro partecipazione venga conteggiata.

Si tratta di una funzione di back-end disattivata per impostazione predefinita. Per attivarla, contatta il CSM.

## Modifiche alla migrazione

Nel flusso di lavoro di migrazione vengono apportate le seguenti modifiche:

* Migra i moduli in cartelle specifiche.
* Sono stati aggiunti i criteri di completamento per i moduli.
* Sono stati aggiunti criteri di completamento per i corsi

### Modifiche alla migrazione dei moduli

Quando esegui la migrazione dei moduli in ALM, questi verranno salvati nella cartella pubblica per impostazione predefinita. In questa versione è stata aggiunta una nuova colonna denominata `folder` nel file [module_version.csv](assets/module_version.csv). Gli amministratori possono utilizzare questa colonna per specificare il nome della cartella in cui i moduli devono andare dopo la migrazione. Gli amministratori possono anche inserire un singolo modulo in più cartelle elencando i nomi delle cartelle separati da virgole.

La colonna della cartella utilizza il tipo di dati stringa ed è facoltativa. Di seguito sono riportate le condizioni per la colonna della cartella:

* Il nome della cartella che aggiungi deve essere una cartella di contenuti esistente nell&#39;account ALM.
* I valori devono essere una stringa separata da virgole.
* Se aggiungi un nuovo nome di cartella per un modulo già presente in un’altra cartella, il nuovo valore non sovrascriverà né sostituirà la cartella assegnata. Il modulo verrà aggiunto alla nuova cartella e rimarrà disponibile anche nella cartella esistente.
* Se il valore è vuoto, per impostazione predefinita la cartella sarà **[!UICONTROL Pubblica]**.

Per ulteriori informazioni, fai riferimento al file della specifica ](assets/4-module_version.xlsx) di [module_version_csv.

### Modifiche alla migrazione dei moduli - Criteri di completamento

Gli amministratori possono specificare i criteri di completamento dei moduli durante la migrazione. In questa versione sono state aggiunte nuove colonne `completionCriteria`, `viewPercent` e `quizData` in [module_version.csv](assets/module_version.csv).

Di seguito sono riportate le condizioni per le nuove colonne:

1. `completionCriteria`:

   * Il tipo di dati deve essere una stringa e i valori supportati sono:
      * `LAUNCH_CONTENT`
      * `VIEW_PERCENT`
      * `QUIZ`
      * `MARK_COMPLETE`
   * Aggiungi i criteri di completamento a livello di modulo solo per i tipi di modulo a ritmo personalizzato.
   * I valori supportati per il contenuto statico sono `LAUNCH_CONTENT` e `VIEW_PERCENT`.
   * I valori supportati per il contenuto interattivo sono `LAUNCH_CONTENT`, `VIEW_PERCENT` e `QUIZ`.
   * I valori supportati per il contenuto di HTML5 sono `LAUNCH_CONTENT` e `MARK_COMPLETE`.

2. `viewPercent`:

   * Il tipo di dati per questa colonna deve essere un numero intero e il valore deve essere compreso tra 0 e 100.
   * Quando completedCriteria è impostato su `VIEW_PERCENT`, immettere la percentuale di visualizzazione richiesta in questa colonna o lasciarla vuota.

3. `quizData`:

   * Il tipo di dati deve essere una stringa e i valori supportati sono `QUIZ_ATTEMPTED`, `QUIZ_PASSED` e `QUIZPASSED_OR_LIMITREACHED`.
   * Quando `completionCriteria` è impostato su `QUIZ`, immetti il valore del quiz appropriato nella colonna `quizData`.

Per ulteriori informazioni, fai riferimento al file della specifica ](assets/4-module_version.xlsx) di [module_version_csv.

### Modifiche nella migrazione del corso - Criteri di completamento

Gli amministratori possono specificare i criteri di completamento per i corsi durante la migrazione. In questa versione è stata aggiunta una nuova colonna denominata `completionCriteria` in [course.csv](assets/course.csv).

Di seguito sono riportate le condizioni per la colonna `completionCriteria`:

* Il tipo di dati deve essere stringa o numero ed è un campo facoltativo.
* I valori devono essere `ALL`, `X` e `SELECTEDMODULES`.
* X è un valore intero che deve essere maggiore di 0 e minore del numero totale di moduli.
* Se imposti `completionCriteria` su `SELECTEDMODULES`, devi contrassegnare i moduli obbligatori nel file [course_module.csv](assets/course_module.csv).
* Nella colonna `optionalCriteria`, immettere `TRUE` o `FALSE`. Se imposti il valore come `TRUE`, il modulo sarà obbligatorio.

Per ulteriori informazioni, fai riferimento alle [specifiche csv del corso](assets/3-course.xlsx) e al file delle [specifiche csv del modulo_corso](assets/6-course_module.xlsx).

## Modifiche API

Di seguito sono riportate le modifiche apportate alle API:

* **API di ricerca**:
   * Nuovo filtro modalità con opzioni: classicSearch e advanceSearch.
   * Nuova opzione loMetadata per snippetTypes.
* **API annuncio**:
   * Include l&#39;attributo altText per le descrizioni masthead.
* **API istanza**:
   * Nuovo attributo locale per recuperare i dettagli delle impostazioni locali.
* **Controllo di propagazione**:
   * Aggiornamento delle API per verificare la presenza di parole vietate nei commenti e nelle risposte ai post social:
* **Limitazione RPM e burst**:
   * Sono stati aggiunti i limiti RPM (Richieste al minuto) e burst per tutte le API.
* **API badge**:
   * Nuovo attributo externalProvider per recuperare informazioni sui distintivi esterni.
* **API processo**:
   * Scarica il report Gruppo utenti e il report di audit dei ruoli personalizzati utilizzando l’API dei processi.

### Modifiche all’API di ricerca

L&#39;API di ricerca dispone ora di un nuovo filtro in modalità con due opzioni: `classicSearch` e `advanceSearch`. Esiste anche una nuova opzione `loMetadata` per `snippetTypes`. Per ottenere risultati ottimali, includere `loMetadata` in `snippetTypes` quando si utilizza la modalità `advanceSearch`.

### Modifiche all’API dell’annuncio

`GET /announcements API` ora include l&#39;attributo `altText` per fornire la descrizione masthead.

#### Esempio di richiesta tramite cURL:

```
curl -X GET --header 'Accept: application/vnd.api+json' --header 'Authorization: oauth 12345678' 'https://abcd.adobe.com/primeapi/v2/announcements/123456'
```

#### Risposta di esempio:

```
{
  "links": {
    "self": "https://abcd.adobe.com/primeapi/v2/announcements/123456"
  },
  "data": {
    "id": "12345",
    "type": "adminAnnouncement",
    "attributes": {
      "actionUrl": "google.com",
      "announcementType": "MASTHEAD",
      "expiryDate": "2038-01-19T03:14:07.000Z",
      "liveDate": "2024-07-31T11:11:30.000Z",
      "contentMetaData": [
        {
          "contentType": "IMAGE",
          "contentUrl": "https://abcd.adobe.com",
          "locale": "en-US",
          "altText": "Moonlight - english changed new",
          "thumbnailUrl": "https://abcd.adobe.com/"
        },      ]
    }
  }
}
```

### Modifiche delle API delle istanze

Il nuovo attributo `locale` è stato aggiunto alle API seguenti per recuperare i dettagli delle impostazioni internazionali.

* `GET /learningObjects/{loId}/instances/{loInstanceId}`
* `GET /learningObjects/{id}?include=instances,enrollment.loInstance`
* `GET /learningObjects?include=instances,enrollment.loInstance`
* `GET /learningObjects/{id}/relatedLOs?include=instances,enrollment.loInstance`
* `POST /learningObjects/query?include=instances,enrollment.loInstance`
* `POST /search/query?include=model.instances`
* `GET /search?include=model.instances`

#### Esempio di richiesta tramite cURL:

```
curl --location 'http://abcd.com/primeapi/v2/learningObjects/course:1234567/instances/course:1234567_1234567' \
```

#### Richiesta di esempio:

```
{
    "links": {
        "self": "http://abcd.com/primeapi/v2/learningObjects/course:1234567/instances/course:1234567_1234567"
    },
    "data": {
        "id": "course:1234567_1234567",
        "type": "learningObjectInstance",
        "attributes": {
            "dateCreated": "2024-02-27T09:21:25.000Z",
            "isAET": false,
            "isDefault": true,
            "isFlexible": false,
            "locale": "en-US",
            "state": "Active",
            "localizedMetadata": [
                {
                    "locale": "en-US",
                    "name": "Default instance"
                }
            ]
        },
        "relationships": {
            "learningObject": {
                "data": {
                    "id": "course:1234567",
                    "type": "learningObject"
                }
            },
            "loResources": {
                "data": [
                    {
                        "id": "course:123456_1234567_1234567_1",
                        "type": "learningObjectResource"
                    }
                ]
            }
        }
    }
}
```

### Modifiche API pubbliche per controllo di profanità

Le API seguenti sono state aggiornate per eseguire controlli di blasfemia per commenti e risposte ai post sui social.

* `POST /boards/{id}/posts `
* `PATCH /posts/{id}`
* `POST /posts/{id}/comments`
* `PATCH /comments/{id}`
* `POST /comments/{id}/replies`
* `PATCH /replies/{id}`

Se nel post viene trovata una parola con restrizioni, verrà inviata la seguente risposta.

#### Risposta di esempio:

```
{
  "status": "FORBIDDEN",
  "title": "BAD_WORD_FOUND",
  "source": {
    "info": "Unacceptable word found in post"
  }
}
```

### Modifiche del numero di giri/min e limitazione della frammentazione

In questa versione sono stati aggiunti i limiti di RPM (Richieste al minuto) e burst per tutte le API. Il numero massimo di RPM per ogni API può essere controllato nella pagina Swagger.

RPM indica il numero di richieste che è possibile inviare al server API in un minuto. Il limite di burst consente un numero più elevato di richieste per un breve periodo di tempo, superando il normale limite di velocità. Ad esempio, l&#39;API `learningObject` consente un massimo di 15 richieste al minuto. Se questo limite viene superato, l’API restituirà un messaggio di errore.

### Modifiche delle API dei badge

Il nuovo attributo `externalProvider` è stato aggiunto alle API seguenti per recuperare informazioni sui distintivi esterni, tra cui l&#39;ID del distintivo e il nome del provider.

* `GET /badges `
* `GET /badges/{id}`
* `GET /skills?include=levels.badge`
* `GET /skills/{id}?include=levels.badge`
* `GET /learningObjects/{loId}/instances/{loInstanceId}?include=badge`
* `GET /users/{userId}/userBadges`
* `GET /users/{userId}/userBadges/{id}`

#### Esempio di richiesta tramite cURL:

```
curl -X GET --header 'Accept: application/vnd.api+json' --header 'Authorization: oauth 123456789' 'https://abcd.adobe.com/primeapi/v2/badges/44'
```

#### Risposta di esempio:

```
{
  "links": {
    "self": "https://abcd.adobe.com/primeapi/v2/badges/44"
  },
  "data": {
    "id": "44",
    "type": "badge",
    "attributes": {
      "imageUrl": "https://abcd.com/accountassets/1/badges/download.png",
      "name": "external badge",
      "state": "Active",
      "externalProvider": {
        "id": "1234sjd-b272-4de1-9b60-1234567",
        "provider": "credly"
      }
    }
  }
}
```

### Scaricare i report di audit dei gruppi di utenti e dei ruoli personalizzati tramite l’API dei processi

L&#39;utente può scaricare **[!UICONTROL Report gruppo utenti]** e **[!UICONTROL Report di audit ruolo personalizzato]** utilizzando `Job API`.

#### Esempio di richiesta per il download del report del gruppo di utenti:

```
curl -X POST --header 'Content-Type: application/vnd.api+json;charset=UTF-8' --header 'Accept: application/vnd.api+json' --header 'Authorization: oauth 12345678' -d '{ \ 
     "data": { \ 
         "type": "job", \ 
         "attributes": { \ 
             "jobType": "generateUserGroupReport" \ 
         } \ 
    } \ 
 }' 'https://abcd.adobe.com/primeapi/v2/jobs'
```

#### Esempio di richiesta per il download del report di audit del ruolo personalizzato:

```
curl -X POST --header 'Content-Type: application/vnd.api+json;charset=UTF-8' --header 'Accept: application/vnd.api+json' --header 'Authorization: oauth 1234567' -d '{
    "data": {
        "type": "job",
        "attributes": {
            "description": "description of your choice",
            "jobType": "generateCustomRoleAuditReport",
            "payload":{
                 "fromDate": "2020-01-01T18:30:00.000Z",
                 "toDate": "2024-09-31T18:30:00.000Z",
                 "locale":  "en-US"
            }
        }
   }
}
```

### Messaggi di errore per nessun corpo della richiesta

Abbiamo introdotto messaggi di errore specifici per i casi in cui il corpo della richiesta è obbligatorio ma non fornito nell’API.

#### Messaggio di errore di esempio:

```
{
    "status": "BAD_REQUEST",
    "title": "Generic Error"
}
```

## Miglioramenti ai report

Gli amministratori possono trovare queste modifiche ai report nella sezione **Amministratore** > **Report**.

### Report Trascrizioni apprendimento

Il report **[!UICONTROL Trascrizioni apprendimento]** conterrà due nuove colonne:

* **[!UICONTROL ID modulo]**: visualizza l&#39;identificatore univoco per ogni modulo. Questa nuova colonna è stata aggiunta dopo la colonna **[!UICONTROL Modulo]** esistente.
* **[!UICONTROL ID istanza corso]**: visualizza l’identificatore univoco per ogni istanza del corso. Questa nuova colonna è stata aggiunta dopo la colonna **[!UICONTROL Istanza]** esistente.
* **[!UICONTROL Commento di completamento]**: questa colonna acquisisce i commenti immessi dall&#39;amministratore quando contrassegna il completamento dell&#39;utente. Questa nuova colonna è stata aggiunta alla fine del report.


### Report di riepilogo della sessione

Il report **[!UICONTROL Riepilogo sessione]** conterrà tre nuove colonne:

* La colonna **[!UICONTROL ID modulo]** è stata aggiunta prima della colonna **[!UICONTROL Nome sessione]**.
* La colonna **[!UICONTROL ID sessione]** è stata aggiunta prima della colonna **[!UICONTROL Nome sessione]**.
* La colonna **[!UICONTROL ID istanza corso]** è stata aggiunta dopo la colonna **[!UICONTROL Nome istanza]**.
* La colonna **[!UICONTROL Totale completamenti]** è stata aggiunta dopo la colonna **[!UICONTROL Totale iscrizioni]**.

## Bug corretti in questo aggiornamento

* È stato corretto l’errore che si verificava durante il caricamento di video dal modulo di attività durante l’invio di file su dispositivi Android e iOS.
* È stato risolto il problema relativo all’apertura dei corsi nell’app per dispositivi mobili; la versione Web funziona correttamente.
* È stato risolto il problema relativo alla visualizzazione delle risorse formative e di altre risorse in Safari.
* È stato risolto il problema che impediva agli utenti di scaricare le risorse formative nell’app per dispositivi mobili.
* È stato corretto l’errore nella documentazione dell’API utente della patch.
* È stato risolto il problema a causa del quale gli organizzatori non ricevevano notifiche e-mail quando una sessione veniva eliminata dal corso.
* È stato risolto il problema a causa del quale gli organizzatori non ricevevano e-mail di annullamento della sessione quando un modulo veniva rimosso dal corso e ripubblicato.
* È stato aggiunto il supporto per l’inclusione di caratteri speciali &quot;+&quot; e &quot;-&quot; negli indirizzi e-mail durante la creazione di utenti esterni.
* È stato risolto il problema a causa del quale la sincronizzazione del report unificato del connettore Marketo non andava a buon fine se il report sulle abilità dell’utente conteneva virgolette doppie nel valore del record CSV.
* È stato risolto il problema a causa del quale l’endpoint `/skills` restituiva lo stato corretto per l’API di amministrazione, ma l’API dell’Allievo mostrava sempre dati errati o memorizzati nella cache.
* È stato risolto il problema relativo all’onboarding Go1 per i corsi freemium che non andavano a buon fine quando l’account non disponeva del connettore Go1 configurato.
* È stato risolto il problema a causa del quale i corsi nel percorso di apprendimento (LP) non erano accessibili tramite migrazione se l’Allievo aveva già completato il LP.
* È stato risolto il problema a causa del quale il file CSV dell’utente incrementale non funzionava se il manager dell’utente e il manager di salto livello erano impostati come SU (Utente privilegiato) anziché come amministratore e non erano inclusi nel file CSV.
* Sono stati risolti i problemi relativi agli ambiti per i manager dei punti vendita nei report del dashboard.
* È stato risolto il problema a causa del quale xapi_iri non veniva rimosso quando veniva eliminata una bozza di corso.
* È stato risolto il problema che impediva l’aggiunta di un ID LO univoco in alcuni scenari.
* È stato risolto il problema a causa del quale la proprietà IsEmbeddable nel piano di apprendimento non veniva aggiornata correttamente nei piani di apprendimento condivisi.
* È stato risolto il problema che influiva sulla visualizzazione della durata totale dei percorsi di apprendimento nella vista Allievo.
* È stato risolto il problema che consentiva agli Allievi di registrarsi o registrarsi tramite i collegamenti di registrazione autonoma anche dopo l’eliminazione dei propri account.
* È stato risolto il problema a causa del quale `www` veniva rimosso durante l’aggiunta di collegamenti nella descrizione del corso durante la creazione.
* È stato risolto il problema a causa del quale le informazioni nascoste e le risorse formative scaricate non funzionavano correttamente.
* È stato risolto il problema a causa del quale SSO (Single Sign-On) non funzionava per i nuovi utenti aggiunti tramite il collegamento di registrazione autonoma con un ID IP.
* È stato risolto il problema a causa del quale i dati del messaggio di notifica non venivano recuperati dopo l’eliminazione di un annuncio.
* È stato risolto il problema relativo all’insufficienza dei risultati di ricerca durante la ricerca di utenti tramite e-mail.

## Requisiti di sistema

Visualizza [requisiti di sistema di Adobe Learning Manager](/help/migrated/system-requirements.md).

## Versioni precedenti di Adobe Learning Manager

* [Versione di luglio 2024](/help/migrated/whats-new-july-2024.md)
* [Versione di marzo 2024](/help/migrated/whats-new-march-2024.md)
