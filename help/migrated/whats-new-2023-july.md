---
title: Novità di questa versione (luglio 2023)
description: Scopri le nuove funzioni e i miglioramenti in Adobe Learning Manager
hidefromtoc: true
exl-id: c6f192b6-f377-47b2-9151-516ac8179543
source-git-commit: ebf4ea065ba799b957b8ce275fd1690f18b26556
workflow-type: tm+mt
source-wordcount: '2059'
ht-degree: 67%

---

# Novità di questa versione (luglio 2023)

## Consigli migliorati

Adobe Learning Manager ha introdotto un sistema nuovo e rinnovato di suggerimenti per i corsi. Questa funzione di consigli utilizza algoritmi di intelligenza artificiale e gli interessi degli utenti come Prodotti, Ruoli e Livelli per fornire consigli sui contenuti personalizzati.

Per ulteriori informazioni, consulta [Suggerimenti di Adobe Learning Manager](recommendations-adobe-learning-manager.md).

## Iscrizione multipla

In questa versione di Adobe Learning Manager, stiamo introducendo l’iscrizione multipla per gli Allievi, opzione che consente agli Allievi di iscriversi a più istanze di un corso in uno o più periodi.

Per ulteriori informazioni, consulta [Iscrizioni multiple](/help/migrated/authors/feature-summary/courses.md).

### Iscrizioni multiple nell’app per dispositivi mobili o in quella immersiva

Gli Allievi non possono iscriversi a più istanze da un’app per dispositivi mobili/immersiva. La registrazione multipla non è supportata nell’app per dispositivi mobili e nel Web coinvolgente per dispositivi mobili.

>[!NOTE]
>
>L’attivazione dell’iscrizione multipla determina l’aggiunta di più righe al report Trascrizione Allievo per ogni corso (una riga per ogni istanza).
>
>Se hai configurato l’automazione dei report che prevede una sola riga per corso, prima di abilitare la funzione Iscrizione multipla devi apportare le modifiche necessarie all’automazione dei report.

### Formato dei distintivi in un’istanza con iscrizioni multiple

Per supportare i distintivi in un’istanza con più iscrizioni, il formato del distintivo viene modificato in `userId_badgeId_COURSE_courseId_courseInstanceId`.

### Avviare il lettore nella funzione di iscrizione multipla utilizzando una modalità headless

In questa versione, è stata modificata la libreria utilizzata per la comunicazione con il lettore headless.

In caso di registrazione multipla, è necessario passare gli argomenti racchiusi in un oggetto.

```
{{startplayer(argument_object) ,
where
argument_object=
{ loId = <loId>, accountId = <accountId>, userId =<userId>, accessToken = <accessToken>, domId = <elementId>, onModuleLoaded = fn(), isMultiEnrolled=<boolean>, instanceId=<instanceId> }
}}
```

## Rimozione del connettore exavault

Questa versione di Adobe Learning Manager includerà un nuovo connettore, che utilizzerà il protocollo SFTP della famiglia di prodotti AWS Transfer.

Questa modifica sostituisce anche il connettore ExaVault, che non sarà più disponibile per i nuovi utenti. È possibile utilizzare qualsiasi client FTP open source in sostituzione di ExaVault. Per ulteriori informazioni, consulta [Transizione da FTP Manager di Adobe](transition-from-ftp-manager.md).

## Promemoria in Outlook per classi e sessioni virtuali

Le sessioni in aula e in aula virtuale create da Adobe Learning Manager che sono state aggiunte al calendario di Outlook dell’Allievo ora supporteranno i promemoria da Outlook in modo coerente (in modo simile ai promemoria delle riunioni in Outlook).

## Miglioramenti relativi all’assegnazione di abilità ai corsi

Abbiamo migliorato il flusso di lavoro di assegnazione delle abilità per gli Autori. L’elenco dei suggerimenti per le abilità nella pagina Impostazioni corso ora include una funzionalità di ricerca con completamento automatico. Gli autori ora possono cercare le abilità digitando i primi caratteri e i suggerimenti verranno visualizzati nell’elenco a discesa Abilità in base all’input. Con questo miglioramento, gli Autori non devono scorrere l’elenco completo per trovare e assegnare abilità ai corsi.

## Miglioramenti del flusso di lavoro dei corsi approvati dal Manager

I corsi approvati dal Manager ora forniscono informazioni di errore adatte sia ai Manager che agli Allievi.

![messaggi di errore](assets/error-messages.png)

I Manager possono ora visualizzare i messaggi di errore pertinenti con informazioni (ad esempio, la scadenza per l’iscrizione è passata) quando non possono approvare una richiesta di iscrizione al corso. Gli Allievi possono vedere l’errore e la correzione.

## Report nuovo piano di apprendimento

Gli amministratori/amministratori personalizzati possono ora esportare un elenco di tutti i piani di apprendimento nell’account e i metadati, ad esempio lo stato, i gruppi di utenti applicabili, le informazioni sull’attivazione, i corsi/percorsi di apprendimento inclusi nel piano di apprendimento e le informazioni sui promemoria.

## Report per tenere traccia delle istanze ritirate in arrivo

Il report dei corsi di formazione include una colonna aggiuntiva che visualizza la scadenza per il completamento delle istanze presenti nei corsi o nei percorsi di apprendimento in modo che gli amministratori e gli autori sappiano quali istanze verranno ritirate e possano intraprendere le azioni necessarie.

## Miglioramenti per acquisire le valutazioni dei corsi da parte degli Allievi

Non appena l’utente completa l’ultimo modulo del corso viene visualizzata una finestra a comparsa per acquisirne la valutazione a stelle.

![valutazioni](assets/ratings.png)

## Personalizzare i modelli e-mail

I modelli e-mail in Learning Manager ora includono sezioni completamente modificabili che offrono una maggiore flessibilità per personalizzare le comunicazioni e-mail in base alle preferenze di messaggistica e branding.

Per ulteriori informazioni, consulta [Personalizzare il modello e-mail](/help/migrated/administrators/feature-summary/email-templates.md#flexibility-in-customizing-the-templates).

## Miglioramenti apportati all&#39;assistente alla pianificazione

Perfeziona il processo di selezione di un istruttore per le sessioni in aula o virtuali. Un filtro Gruppo utenti è stato aggiunto al campo Istruttore nell&#39;Assistente alla pianificazione. Gli Autori ora possono filtrare gli Istruttori in base alle &quot;Abilità dell’Istruttore&quot; e a qualsiasi parametro aggiuntivo come posizione, lingua, qualifica e così via.

Per ulteriori informazioni, consulta [Filtro Gruppo utenti in Assistente pianificazione](/help/migrated/authors/feature-summary/courses.md#user-group-filter).

## Miglioramenti al flusso di lavoro di ritiro degli oggetti di apprendimento

Gli autori possono ora fornire una data di **Ritiro automatico** per un corso. Questo aiuta a prevenire l’inflazione del catalogo nel tempo e la necessità di tornare indietro e ritirare manualmente i corsi.

Gli amministratori possono inoltre decidere a livello di account la natura dell’accesso agli oggetti di apprendimento &quot;ritirati&quot;.

Il report sulla formazione include una nuova colonna, **Data ritiro automatico**, per visualizzare la data di ritiro per ogni oggetto di apprendimento (se impostata).

## Valori delle etichette del catalogo per autori

Durante la creazione o la modifica di un corso, gli Autori ora possono aggiungere i loro valori per le etichette del catalogo. Gli amministratori possono abilitare questa funzione a livello di account. Quando un autore aggiunge un nuovo valore di etichetta del catalogo, questo diventa parte della ricerca con completamento automatico.

![seleziona catalogo](assets/select-catalog.png)

## Miglioramenti nella ricerca di ruoli di amministratore, autore e manager nei corsi

Sono stati apportati miglioramenti alla ricerca per i ruoli di amministratore, autore e manager. Ora saranno in grado di effettuare ricerche con parole chiave per i titoli. Questo vale per corsi, percorsi di apprendimento e certificazioni.

## Notifiche per errori di migrazione

Gli amministratori di integrazione ricevono una notifica tramite e-mail se durante la migrazione o quando utilizzano connettori di dati quali PowerBI, FTP, Box e così via, eventuali operazioni di importazione o esportazione non vanno a buon fine.

## Configurazione di gestione multipla tramite API

È stata aggiunta una nuova API al set di API di Managed Office per supportare la configurazione multi-manager.

## Miglioramenti all’API di iscrizione

Sono stati apportati miglioramenti all’API di iscrizione per supportare e ottimizzare le iscrizioni in blocco su larga scala.

## App per dispositivi mobili - Visualizzazione di contenuti offline

Gli Allievi possono scaricare e visualizzare i contenuti in modalità offline. I percorsi di apprendimento nidificati e flessibili non sono supportati per la visualizzazione offline.

*In questa versione, la visualizzazione dei contenuti offline è supportata solo per i contenuti in lingua inglese.*

## Accessibilità

Sono stati implementati diversi miglioramenti per potenziare l’accessibilità, ad esempio l’ottimizzazione della leggibilità da parte degli screen reader.

## Supporto per app mobili

Con la prossima versione principale, l’app mobile Adobe Learning Manager supporterà solo le tre versioni più recenti del sistema operativo per dispositivi mobili.

## Contenuto su LinkedIn

Il contenuto di LinkedIn non viene caricato come previsto sull’app immersiva nel browser Safari. Per ovviare a questo problema, è possibile eseguire le operazioni seguenti:

1. Sul dispositivo, seleziona **[!UICONTROL Impostazioni]** > **[!UICONTROL Safari]**.
1. Disabilita **Impedisci il monitoraggio tra siti**.
1. Disabilita **Blocca tutti i cookie**.
1. Accedi all’app immersiva.
1. Riproduci il contenuto.
1. Consenti i pop-up.

## Altri miglioramenti

### Cambiare le istanze in MS Teams

Un Allievo può passare a un’istanza di corso diversa fino al completamento e mantenere l’avanzamento del corso.

### Supporto di più iscrizioni in MS Teams

Un Allievo può iscriversi a un’altra istanza del corso indipendentemente dallo stato di completamento di qualsiasi istanza precedente. In questo modo l’Allievo si iscrive a più istanze dello stesso corso.

### Le note del corso supportano più iscrizioni in MS Teams

Le note del corso sono disponibili a livello di istanza del corso per supportare l’iscrizione multipla.

## Modifiche API

Per ulteriori informazioni sulle modifiche API, vedere il [Riferimento API di Adobe Learning Manager](https://captivateprime.adobe.com/docs/primeapi/v2/).

### Supporto API per nuovi suggerimenti

**GET /account**

Restituisce se prlRecommendation è abilitato.

**Richiesta**

`https://learningmanagerstage1.adobe.com/primeapi/v2/account`

**GET /data?filter.recommendationCriteria=product**

Restituisce l’elenco di Prodotti/Argomenti. I risultati dipendono dalle impostazioni dell’account che confermano se tutti i prodotti saranno visibili all’Allievo o il catalogo visibile ai prodotti/argomenti.

**Richiesta**

`https://learningmanagerqe.adobe.com/primeapi/v2/data?filter.recommendationCriteria=product&filter.showAllRecommenda`

**`GET /data?filter.recommendationCriteria=role`**

Restituisce l’elenco dei ruoli consigliati.

**Richiesta**

`https://learningmanagerqe.adobe.com/primeapi/v2/data?filter.recommendationCriteria=role&filter.showAllRecommendationCriteria=false`

**`GET /data?filter.recommendationCriteria=level`**

Restituisce l’elenco dei ruoli consigliati.

**Richiesta**

`https://learningmanagerqe.adobe.com/primeapi/v2/data?filter.recommendationCriteria=level&filter.showAllRecommendationCriteria=false`

**POST /search/query**

La ricerca include anche i prodotti e i parametri dei ruoli nella query. Non ci sono modifiche nelle query e nel corpo. Verranno aggiunte nuove opzioni di ordinamento

**Richiesta**

`https://learningmanagerstage1.adobe.com/primeapi/v2/search/query?...`

**GET /learningObjects**

Il modello Oggetto di apprendimento restituisce suggerimenti con tag di autore se il suggerimento PRL è attivo.

**URL richiesta**

`https://learningmanagerstage1.adobe.com/primeapi/v2/learningObjects?sort=recommendationScore&filter.recommendationProducts=...&filter.recommendationRoles=...&filter.excludeIgnoredRecommendations=true`

POST /learningObjects/query

Nel corpo della chiamata di query sono supportati i seguenti attributi:

```javascript {line-numbers="true"}
{
  "filter.announcedGroups": [
    "string"
  ],
  "filter.bookmarks": true,
  "filter.catalogIds": [
    "string"
  ],
  "filter.cityName": [
    "string"
  ],
  "filter.duration.range": [
    "string"
  ],
  "filter.effectiveModifiedDate.fromDate": "string",
  "filter.effectiveModifiedDate.toDate": "string",
  "filter.excludeIgnoredRecommendations": true,
  "filter.ignoreEnhancedLP": true,
  "filter.ignoreHigherOrderLOEnrollment": true,
  "filter.lang.subLOs": true,
  "filter.lang.twoLetterCode": true,
  "filter.learnerState": [
    "string"
  ],
  "filter.loFormat": [
    "string"
  ],
  "filter.loTypes": [
    "string"
  ],
  "filter.price": "string",
  "filter.priceRange": [
    "string"
  ],
  "filter.recommendationLevels": [
    "string"
  ],
  "filter.skill.level": [
    "string"
  ],
  "filter.skillName": [
    "string"
  ],
  "filter.tagName": [
    "string"
  ],
  "language": [
    "string"
  ],
  "preferredSortPartitionOrder": [
    "string"
  ],
  "showLoContentSource": true,
  "useCache": true,
  "filter.recommendationProducts": [
    {
      "levels": [
        "string"
      ],
      "name": "string"
    }
  ],
  "filter.recommendationRoles": [
    {
      "levels": [
        "string"
      ],
      "name": "string"
    }
  ]
}
```

**GET /recommendationProducts**

Recupera il prodotto PRL in base all’ID RecommendationProduct.

**URL richiesta**

`https://learningmanagerstage1.adobe.com/primeapi/v2/recommendationProducts`

GET /recommendationRoles

Recupera il prodotto PRL in base all’ID RecommendationProduct. Verranno restituiti solo i ruoli visibili di (Oggetti di apprendimento).

**URL richiesta**

`https://learningmanagerstage1.adobe.com/primeapi/v2/prlRecommendations/roles`

`POST /users/{id}/recommendationPreferences`

Crea/Ricrea (Sostituisci) le preferenze di raccomandazione PRL. Esempio di carico utile:

```javascript {line-numbers="true"}
{
    "data": {
        "id": "userRecommendationPreferences:14755328",
        "type": "userRecommendationPreferences",
        "attributes": {
            "products": [
                {
                    "id": "recommendationProduct:1",
                    "dateCreated": "2023-05-07T20:00:00.000Z"
                },
                {
                    "id": "recommendationProduct:37",
                    "dateCreated": "2023-05-07T21:00:00.000Z"
                }
            ],
            "roles": [
                {
                    "id": "recommendationRole:23",
                    "dateCreated": "2023-05-07'T'21:00:00.000'Z'"
                },
                {
                    "id": "recommendationRole:1",
                    "dateCreated": "2023-05-07'T'20:01:00.000'Z'"
                },
                {
                    "id": "recommendationRole:2",
                    "dateCreated": "2023-05-07'T'19:02:00.000'Z'"
                },
                 {
                    "id": "recommendationRole:3",
                    "dateCreated": "2023-05-07'T'18:02:00.000'Z'"
                },
                {
                    "id": "recommendationRole:20",
                    "dateCreated": "2023-05-07'T'17:02:00.000'Z'",
                    "levels": [
                        "INTERMEDIATE"
                    ]
                }
            ]
        }
    }
}
```

**`GET /users/{id}/recommendationPreferences`**

**URL richiesta**

`https://learningmanagerstage1.adobe.com/primeapi/v2//users/123/recommendationPreferences`

**`DELETE /users/{id}/recommendationPreferences`**

Elimina le preferenze utente dei suggerimenti PRL per un prodotto o un ruolo.

**URL richiesta**

`https://learningmanagerstage1.adobe.com/primeapi/v2/users/123/recommendationPreferences?ids=recommendationRole:123,recommendationRole:234`

Params :

Id = elenco degli ID da eliminare

**PATCH /users/{id}/recommendationPreferences**

Addizione/Aggiornamento parziale. Esempio di carico utile:

```javascript {line-numbers="true"}
{
  "data": {
    "id": "userRecommendationPreferences:<USER_ID>",
    "type": "userRecommendationPreferences",
    "attributes": {
      "roles": [
        {
          "id": "recommendationRole:123",
          "type": "recommendationRole",
          "attributes": {
            "levels": [
              "INTERMEDIATE"
            ]
          }
        },
        {
          "id": "recommendationRole:123",
          "type": "recommendationRole",
          "attributes": {
            "levels": [
              "ADVANCED"
            ]
          }
        }
      ]
    }
  }
}
```

**POST/recommendationPreferences/learningObjects/{id}/ignore**

Aggiunge oggetti di apprendimento ai suggerimenti bloccati.

**URL richiesta**

`https://learningmanagerstage1.adobe.com/primeapi/v2/recommendationPreferences/learningObjects/{id}/ignored`

**`DELETE /recommendationPreferences/learningObjects/{id}/ignore`**

Elimina oggetti di apprendimento dai suggerimenti bloccati.

**URL richiesta**

`https://learningmanagerstage1.adobe.com/primeapi/v2/recommendationPreferences/learningObjects/{id}/ignored`

**`GET /users/{id}/recommendationStrips`**

Recupera tutte le strisce da utilizzare per mostrare i suggerimenti prl

### Supporto di più iscrizioni per API

**GET /primeapi/v2/account**

Vengono aggiunti due nuovi attributi :

* instanceSwitchEnabled
* multiEnrollmentEnabled

**GET /users/{userId}/userNotifications**

È stato aggiunto l’ID istanza del corso nelle notifiche nel nuovo attributo dei metadati.

**GET /learningObjects**

La relazione di iscrizione visualizza solo l’iscrizione principale, ovvero la prima iscrizione o il primo completamento.

**`GET /learningObjects/{id}`**

La relazione di iscrizione visualizza solo l’iscrizione principale, ovvero la prima iscrizione o il primo completamento.

**`GET /learningObjects/{loId}/instances/{loInstanceId}`**

Viene aggiunta una nuova relazione al modello di istanza dell’oggetto di apprendimento.

**`GET /enrollments/{id}`**

Recupera l’iscrizione ai corsi a iscrizione multipla.

**`DELETE /enrollments/{id}`**

Annulla l’iscrizione a una particolare istanza dell’oggetto di apprendimento.

**POST /enrollments**

Supporta l’iscrizione in diverse istanze.

**GET/iscrizioni**

Ottiene le iscrizioni solo per le iscrizioni primarie per l’oggetto di apprendimento.

**`GET /learningObjects/{id}/note`**

Recupera un elenco di note per un corso.

**`GET /learningObjects/{lo_id}/instances/{loi_id}/note`**

Recupera un elenco di note per un corso e l’istanza.

**`GET /learningObjects/{id}/resources/{loResourceId}/note`**

Recupera un elenco di note per una risorsa in un corso.

**`POST /learningObjects/{id}/resources/{loResourceId}/note`**

Aggiunge una nota in un modulo per un corso specifico.

**`DELETE /learningObjects/{id}/resources/{loResourceId}/note/{noteId}`**

Elimina note specifiche da un determinato modulo rispetto a un’istanza specifica (parte di loResource Id).

**`GET /learningObjects/{id}/resources/{loResourceId}/note/{noteId}`**

Recupera una nota specifica in un modulo di un corso per una determinata istanza (parte di loResourceId).

**`PATCH /learningObjects/{id}/resources/{loResourceId}/note/{noteId}`**

Aggiorna note specifiche di un determinato modulo rispetto a un’istanza specifica (parte di loResource Id).

**Modifiche API amministratore**

* GET /users/{id}/enrollments
* POST /users/{id}/enrollments
* DELETE /users/{id}/enrollments/{enrollmentId}
* PATCH /users/{id}/enrollments/{enrollmentId}

### Enforcedfields per gli endpoint

I prodotti e i ruoli vengono caricati solo se applicati.

Richiesta di esempio

* GET `https://learningmanagerstage1.adobe.com/primeapi/v2/learningObjects/course%3A7418798?enforcedFields[learningObject]=products`
* GET `https://learningmanagerstage1.adobe.com/primeapi/v2/users/11255638/userBadges?include=model&page[offset]=0&page[limit]=10&sort=dateAchieved&enforcedFields[learningObject]=products,roles`

### Modifiche API di ricerca nell’implementazione radice (lingua inglese)

Lo stemming consiste nel ridurre una parola alla sua radice. Questo assicura che le varianti di una parola corrispondano durante la ricerca. Ad esempio, camminare e camminare possono essere associati alla stessa parola radice: camminare. Una volta effettuata la ricerca, l&#39;occorrenza di una delle due parole corrisponderà all&#39;altra.

In questa versione è stato aggiunto lo stemming per le lingue inglesi, che include le seguenti varianti: en_US, en_AU, en_GB.

L’attributo stemmed indica se è necessario effettuare lo stemming nei risultati della ricerca. Per impostazione predefinita, questo valore è impostato su False.

Parametri query API:

* matchType=phrase_and_match
* stemmed=true

### Rimozione degli endpoint V1

Le API V1 smetteranno di funzionare in questa versione. Per ulteriori informazioni, consulta il [Manuale per sviluppatori](/help/migrated/integration-admin/feature-summary/developer-manual.md).

### Notifiche per l’iscrizione o la cancellazione del corso

Questa versione introduce il supporto per l’ID istanza del corso con le notifiche nel nuovo attributo dei metadati.

### Supporto feedback L1

Consente all’Allievo di fornire feedback a ogni livello di istanza della funzione Iscrizione multipla.

**API:** `POST /enrollments/{id}/l1Feedback`

### Elenco campi di applicazione LO

In questa versione è necessario inviare esplicitamente a learningObject sezioni, prequisiteConstraints, prerequisiteLO, subLO, additionalResources, additionalLO, instance e catalogLabels.

Ad esempio:

`enforcedFields[learningObject]=prerequisiteLOs,instances`

### Avviso di obsolescenza per la prossima versione

* Ignora flag per le API dell’Allievo.
* Modificheremo l’impostazione predefinita per highlightResults=false. Inoltre, modificheremo l’impostazione predefinita di snippetType=courseName.
* Verrà deprecato matchType=bool nell&#39;endpoint di ricerca.
* autoCompleteMode ha il tag [Deprecato] e per fornire la stessa funzionalità di autoCompleteMode =false, è stato aggiunto un matchType denominato Match.

### Formato ID badge con iscrizione multipla

Per supportare i distintivi delle istanze con iscrizione multipla, stiamo modificando il formato dei distintivi del corso da `userId_badgeId_COURSE_courseId to userId_badgeId_COURSE_courseId_courseInstanceId` per identificare in modo univoco i distintivi.

## Note sulla versione

Per informazioni sulle versioni correnti e precedenti dell’app Web e per dispositivi di Learning Manager, consulta le [Note sulla versione](/help/migrated/release-note/release-notes.md).

## Problemi noti o limitazioni in questa versione

Di seguito sono riportate le limitazioni di questa versione:

### Visualizzazione di contenuti offline nell’app per dispositivi mobili

I seguenti elementi non sono supportati durante la visualizzazione di contenuti offline nell’app:

* Corsi, piani di apprendimento o certificazioni Flex.
* Corsi avanzati, piani di apprendimento o certificazioni.
* Corsi con quiz a risposta multipla, piani di apprendimento o certificazioni.
* Harvard Manage Mentor, Content Marketplace, GetAbstract o Corsi LinkedIn, piani di apprendimento o certificazioni.
* Piani di apprendimento e certificati con i prerequisiti abilitati.
* Corsi, piani di apprendimento o certificazioni ritirati.
* Corsi, piani di apprendimento o certificazioni con scadenza scaduta.
* Certificati esterni.
* Corsi, piani di apprendimento o certificazioni abilitati per l’eCommerce.

I seguenti percorsi di apprendimento, corsi o certificazioni presentano alcuni problemi con la sincronizzazione offline:

* Tutti i percorsi di apprendimento.
* Tutti i certificati interni.
* Contenuto con chiamate POST.

### Suggerimenti

I seguenti elementi non sono supportati per Prodotto/Ruolo/Livello nel nuovo sistema di suggerimenti:

* Adobe Experience Manager, Teams, SFDC e Senza accesso.
* L’app per dispositivi mobili non supporta la modifica di Prodotti e ruoli nella pagina Suggerimenti.
* Impossibile eseguire la mappatura durante la migrazione.
* Applicazione automatica di tag a LinkedIn, marketplace dei contenuti e altri corsi, piani di apprendimento o certificazioni esterni.
* Ripristino basato su abilità o classico dopo l’attivazione.
* Il menu di ricerca per Prodotti e ruoli nell’app per gli Allievi.
* Mappatura in blocco di corsi, piani di apprendimento o certificazioni e utenti nell’app per Amministratori.

## Requisiti di sistema

[Requisiti di sistema di Learning Manager](/help/migrated/system-requirements.md)
