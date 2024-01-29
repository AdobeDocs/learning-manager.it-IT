---
title: Novità di questa versione (luglio 2023)
description: Scopri le nuove funzioni e i miglioramenti in Adobe Learning Manager
hidefromtoc: true
source-git-commit: c55f9448082c9971c065eec95b59992db95e53dc
workflow-type: tm+mt
source-wordcount: '2052'
ht-degree: 0%

---

# Novità di questa versione (luglio 2023)

## Consigli migliorati

Adobe Learning Manager ha introdotto un nuovo sistema di raccomandazione per i corsi. Questa funzione di consigli utilizza algoritmi di intelligenza artificiale e gli interessi degli utenti come Prodotti, Ruoli e Livelli per fornire consigli sui contenuti personalizzati.

Per ulteriori informazioni, consulta [Recommendations nell’Adobe di Learning Manager](recommendations-adobe-learning-manager.md).

## Iscrizione multipla

In questa versione di Adobe di Learning Manager, stiamo introducendo l’iscrizione multipla per gli Allievi che consente loro di iscriversi a più di un’istanza di un corso in uno o diversi periodi di tempo.

Per ulteriori informazioni, consulta [Iscrizioni multiple](/help/migrated/authors/feature-summary/courses.md).

### Iscrizioni multiple nell’app per dispositivi mobili o immersive

Gli Allievi non possono effettuare l’iscrizione a più istanze da un’app per dispositivi mobili/immersiva. La registrazione multipla non è supportata nell’app per dispositivi mobili e nel Web coinvolgente per dispositivi mobili.

>[!NOTE]
>
>L’abilitazione della registrazione multipla comporta l’aggiunta di più righe al report Trascrizione Allievo per ogni corso (una riga per ogni istanza).
>
>Se hai configurato l’automazione dei report che prevede una sola riga per corso, prima di abilitare la funzione Iscrizione multipla devi apportare le modifiche necessarie all’automazione dei report.

### Formato dei distintivi in un’istanza con più iscrizioni

Per supportare i distintivi in un’istanza con più iscrizioni, il formato del distintivo viene modificato in `userId_badgeId_COURSE_courseId_courseInstanceId`.

### Avvia il lettore in registrazione multipla utilizzando una modalità headless

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

Questa versione di Adobe Learning Manager includerà un nuovo connettore, che utilizzerà il protocollo SFTP della famiglia AWS Transfer.

Questa modifica sostituirà anche il connettore ExaVault, che non sarà più disponibile per i nuovi utenti. Puoi utilizzare qualsiasi client FTP open source in sostituzione di ExaVault. Per ulteriori informazioni, consulta [Transizione da Gestione FTP di Adobe](transition-from-ftp-manager.md).

## Promemoria in Outlook per classi e sessioni virtuali

Le sessioni in aula e in aula virtuale create da Adobe Learning Manager che sono state aggiunte al calendario di Outlook dell’Allievo ora supporteranno i promemoria da Outlook in modo coerente (in modo simile ai promemoria delle riunioni in Outlook).

## Miglioramenti relativi all’assegnazione di abilità ai corsi

Abbiamo apportato miglioramenti al flusso di lavoro di assegnazione delle abilità per gli Autori. L’elenco Suggerimenti per le abilità nella pagina Impostazioni corso ora include una funzionalità di ricerca con completamento automatico. Gli Autori possono ora cercare le abilità digitando i primi caratteri e i suggerimenti verranno visualizzati nell’elenco a discesa Abilità in base all’input. Con questo miglioramento, gli Autori non devono scorrere l’elenco completo per trovare e assegnare abilità ai corsi.

## Miglioramenti del flusso di lavoro dei corsi approvati dal Manager

I corsi approvati dal Manager ora forniscono informazioni appropriate sugli errori sia ai Manager che agli Allievi.

![messaggi di errore](assets/error-messages.png)

I Manager ora possono visualizzare i messaggi di errore pertinenti con informazioni (ad esempio, se la scadenza dell’iscrizione è passata) quando non possono approvare una richiesta di iscrizione a un corso. Agli Allievi vengono mostrati l’errore e l’azione correttiva.

## Report nuovo piano di apprendimento

Amministratori/Amministratori personalizzati possono ora esportare un elenco di tutti i piani di apprendimento dell’account e metadati quali stato, gruppi di utenti applicabili, informazioni sui trigger, corsi/percorsi di apprendimento inclusi nel piano di apprendimento e informazioni sui promemoria.

## Report per tenere traccia delle istanze ritirate in arrivo

Il report dei corsi di formazione include una colonna aggiuntiva per visualizzare la scadenza di completamento delle istanze presenti nei corsi o nei percorsi di apprendimento, in modo che amministratori e autori sappiano quali istanze verranno ritirate e possano intraprendere le azioni necessarie.

## Miglioramenti per acquisire le valutazioni dei corsi da parte degli Allievi

Una finestra a comparsa per acquisire la valutazione a stelle di un corso viene visualizzata non appena l’utente completa l’ultimo modulo del corso.

![valutazioni](assets/ratings.png)

## Personalizzare i modelli e-mail

I modelli e-mail in Learning Manager ora includono sezioni completamente modificabili, offrendo maggiore flessibilità per personalizzare le comunicazioni e-mail in base alle preferenze di messaggistica e branding.

Per ulteriori informazioni, consulta [Personalizza modello e-mail](/help/migrated/administrators/feature-summary/email-templates.md#flexibility-in-customizing-the-templates).

## Miglioramenti apportati all&#39;assistente alla pianificazione

Perfeziona il processo di selezione di un istruttore per le sessioni in aula o virtuali. Un filtro Gruppo utenti è stato aggiunto al campo Istruttore nell&#39;Assistente alla pianificazione. Gli Autori ora possono filtrare gli Istruttori in base alle &quot;Abilità dell’Istruttore&quot; e a qualsiasi parametro aggiuntivo come posizione, lingua, qualifica e così via.

Per ulteriori informazioni, consulta [Filtro Gruppo utenti in Assistente alla pianificazione](/help/migrated/authors/feature-summary/courses.md#user-group-filter).

## Miglioramenti al flusso di lavoro di ritiro degli oggetti di apprendimento

Gli autori possono ora fornire un **Ritiro automatico** data di un corso. In questo modo si evita che il catalogo si gonfii nel tempo e che sia necessario tornare indietro e ritirare manualmente i corsi.

Gli amministratori possono inoltre decidere a livello di account la natura dell’accesso agli oggetti di apprendimento &quot;ritirati&quot;.

Il report sulla formazione include una nuova colonna, **Data smobilizzo automatico**, per visualizzare la data di ritiro per ogni oggetto di apprendimento (se impostata).

## Valori delle etichette del catalogo per autori

Gli Autori ora possono aggiungere i propri valori per le etichette del catalogo durante la creazione o la modifica di un corso. Gli amministratori possono abilitare questa funzione a livello di account. Dopo che un autore ha aggiunto un nuovo valore di etichetta del catalogo, questo diventa parte della ricerca con completamento automatico.

![seleziona catalogo](assets/select-catalog.png)

## Miglioramenti nella ricerca di ruoli di amministratore, autore e manager nei corsi

Sono stati apportati miglioramenti alla ricerca per i ruoli di amministratore, autore e manager. Ora saranno in grado di cercare con parole chiave i titoli. Ciò si applica a corsi, percorsi di apprendimento e certificazioni.

## Notifiche per errori di migrazione

Gli Amministratori di integrazione ricevono una notifica tramite e-mail se durante la migrazione o l’utilizzo di connettori di dati come Power BI, FTP, Box o altri si verificano errori nelle operazioni di importazione o esportazione.

## Configurazione di gestione multipla tramite API

È stata aggiunta una nuova API al set di API di Managed Office per supportare la configurazione con più manager.

## Miglioramenti all’API di iscrizione

Sono stati apportati miglioramenti all’API di iscrizione per supportare e ottimizzare le iscrizioni in blocco su larga scala.

## App per dispositivi mobili - Visualizzazione di contenuti offline

Gli Allievi possono scaricare e utilizzare i contenuti in modalità offline. I percorsi di apprendimento nidificati e flessibili non sono supportati per la visualizzazione offline.

*In questa versione, la visualizzazione dei contenuti offline è supportata solo per i contenuti in lingua inglese.*

## Accessibilità

Sono stati implementati diversi miglioramenti per migliorare l’accessibilità, tra cui i miglioramenti per ottimizzare la leggibilità da parte degli screen reader.

## Supporto per app mobili

Con la prossima versione principale, l’app mobile Adobe Learning Manager supporterà solo le tre versioni più recenti del sistema operativo per dispositivi mobili.

## Contenuto su LinkedIn

Il contenuto di linkedIn non viene caricato come previsto sull’app immersiva nel browser Safari. Per ovviare a questo problema, è possibile eseguire le operazioni seguenti:

1. Sul dispositivo, seleziona **[!UICONTROL Impostazioni]** > **[!UICONTROL Safari]**.
1. Disabilita **Impedisci tracciamento tra siti**.
1. Disabilita **Blocca tutti i cookie**.
1. Accedi all’app immersiva.
1. Riproduci il contenuto.
1. Consenti i pop-up.

## Altri miglioramenti

### Cambiare le istanze in MS Teams

Un Allievo può passare a un’istanza di corso diversa fino al completamento e mantenere l’avanzamento del corso.

### Supporto di più iscrizioni in MS Teams

Un Allievo può iscriversi a un’altra istanza del corso indipendentemente dallo stato di completamento delle istanze precedenti. In questo modo, l’Allievo si iscrive a più istanze dello stesso corso.

### Le note del corso supportano l’iscrizione multipla in MS Teams

Le note del corso sono disponibili a livello di istanza del corso per supportare l’iscrizione multipla.

## Modifiche API

Per ulteriori informazioni sulle modifiche alle API, consulta la [Adobe di riferimento per l’API di Learning Manager](https://captivateprime.adobe.com/docs/primeapi/v2/).

### Supporto API per nuovi suggerimenti

**GET /account**

Restituisce il valore se prlRecommendations è abilitato.

**Richiesta**

`https://learningmanagerstage1.adobe.com/primeapi/v2/account`

**GET /data?filter.recommendationCriteria=product**

Restituisce un elenco di prodotti/argomenti. I risultati dipendono dalle impostazioni dell’account che confermano se tutti i prodotti saranno visibili all’Allievo o al catalogo visibile ai prodotti o agli argomenti.

**Richiesta**

`https://learningmanagerqe.adobe.com/primeapi/v2/data?filter.recommendationCriteria=product&filter.showAllRecommenda`

**`GET /data?filter.recommendationCriteria=role`**

Restituisce l&#39;elenco dei ruoli consigliati.

**Richiesta**

`https://learningmanagerqe.adobe.com/primeapi/v2/data?filter.recommendationCriteria=role&filter.showAllRecommendationCriteria=false`

**`GET /data?filter.recommendationCriteria=level`**

Restituisce l&#39;elenco dei ruoli consigliati.

**Richiesta**

`https://learningmanagerqe.adobe.com/primeapi/v2/data?filter.recommendationCriteria=level&filter.showAllRecommendationCriteria=false`

**POST /search/query**

La ricerca include anche i prodotti e i parametri di ruolo nella query. Nessuna modifica apportata alla query e al corpo. Verranno aggiunte nuove opzioni di ordinamento

**Richiesta**

`https://learningmanagerstage1.adobe.com/primeapi/v2/search/query?...`

**GET /learningObjects**

Il modello di oggetti di apprendimento restituisce i suggerimenti con tag di autore se il consiglio PRL è attivo.

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

Recupera il prodotto PRL per suggerimentoID prodotto.

**URL richiesta**

`https://learningmanagerstage1.adobe.com/primeapi/v2/recommendationProducts`

GET /recommendationRoles

Recupera il prodotto PRL per suggerimentoID prodotto. Verranno restituiti solo i ruoli visibili di (Oggetti di apprendimento).

**URL richiesta**

`https://learningmanagerstage1.adobe.com/primeapi/v2/prlRecommendations/roles`

`POST /users/{id}/recommendationPreferences`

Crea/ricrea (sovrascrive) le preferenze dei consigli PRL. Payload di esempio:

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

Parametri:

ID = Elenco di ID da eliminare

**PATCH /users/{id}/recommendationPreferences**

Aggiunta/aggiornamento parziale. Payload di esempio:

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

**POST /recommendationPreferences/learningObjects/{id}/ignore**

Aggiungi LO ai consigli bloccati.

**URL richiesta**

`https://learningmanagerstage1.adobe.com/primeapi/v2/recommendationPreferences/learningObjects/{id}/ignored`

**`DELETE /recommendationPreferences/learningObjects/{id}/ignore`**

Elimina LO dai suggerimenti bloccati.

**URL richiesta**

`https://learningmanagerstage1.adobe.com/primeapi/v2/recommendationPreferences/learningObjects/{id}/ignored`

**`GET /users/{id}/recommendationStrips`**

Recupera tutte le strisce da utilizzare per visualizzare i suggerimenti prl

### Supporto di più iscrizioni per API

**GET /primeapi/v2/account**

Vengono aggiunti due nuovi attributi:

* instanceSwitchEnabled
* multiEnrollmentEnabled

**GET /users/{userId}/userNotifications**

ID istanza del corso aggiunto nelle notifiche nel nuovo attributo dei metadati.

**GET /learningObjects**

La relazione di iscrizione visualizza solo l’iscrizione primaria, ovvero la prima iscrizione o il primo completamento.

**`GET /learningObjects/{id}`**

La relazione di iscrizione visualizza solo l’iscrizione primaria, ovvero la prima iscrizione o il primo completamento.

**`GET /learningObjects/{loId}/instances/{loInstanceId}`**

Al modello di variante LO viene aggiunta una nuova relazione.

**`GET /enrollments/{id}`**

Recuperare l’iscrizione a corsi con più iscrizioni.

**`DELETE /enrollments/{id}`**

Annulla l’iscrizione a una determinata istanza dell’oggetto di apprendimento.

**POST /enrollments**

Supporta l’iscrizione in istanze diverse.

**GET /enrollments**

Ottiene le iscrizioni solo per le iscrizioni primarie per l’oggetto di apprendimento.

**`GET /learningObjects/{id}/note`**

Recupera un elenco di note per un corso.

**`GET /learningObjects/{lo_id}/instances/{loi_id}/note`**

Recupera un elenco di note per un corso e l’istanza.

**`GET /learningObjects/{id}/resources/{loResourceId}/note`**

Recupera un elenco di note per una risorsa in un corso.

**`POST /learningObjects/{id}/resources/{loResourceId}/note`**

Aggiunge una nota in un modulo per un corso per un determinato corso.

**`DELETE /learningObjects/{id}/resources/{loResourceId}/note/{noteId}`**

Elimina note specifiche da un determinato modulo rispetto a un&#39;istanza specifica (parte di loResource Id).

**`GET /learningObjects/{id}/resources/{loResourceId}/note/{noteId}`**

Recupera una nota specifica in un modulo di un corso per una determinata istanza (parte di loResourceId).

**`PATCH /learningObjects/{id}/resources/{loResourceId}/note/{noteId}`**

Aggiorna le note specifiche di un determinato modulo in base a un&#39;istanza specifica (parte di loResource Id).

**Modifiche alle API degli amministratori**

* GET /users/{id}/enrollments
* POST /users/{id}/enrollments
* DELETE /users/{id}/enrollments/{enrollmentId}
* PATCH /users/{id}/enrollments/{enrollmentId}

### Enforcedfields per gli endpoint

Prodotti e ruoli vengono caricati solo se applicati.

Esempio di richiesta

* GET `https://learningmanagerstage1.adobe.com/primeapi/v2/learningObjects/course%3A7418798?enforcedFields[learningObject]=products`
* GET `https://learningmanagerstage1.adobe.com/primeapi/v2/users/11255638/userBadges?include=model&page[offset]=0&page[limit]=10&sort=dateAchieved&enforcedFields[learningObject]=products,roles`

### Modifiche API di ricerca nell’implementazione radice (lingua inglese)

Lo stemming consiste nel ridurre una parola alla sua radice. In questo modo viene garantita la corrispondenza delle varianti di una parola durante una ricerca. Ad esempio, camminare e camminare possono essere associati alla stessa parola radice: camminare. Una volta effettuata la ricerca, l&#39;occorrenza di una delle due parole corrisponderà all&#39;altra.

In questa versione è stato aggiunto lo stemming per le lingue inglesi, che include le seguenti varianti: en_US, en_AU, en_GB.

L&#39;attributo stemmed indica se nei risultati della ricerca è richiesto lo stemming. Per impostazione predefinita, questo valore è impostato su False.

### Rimozione degli endpoint V1

Le API V1 smetteranno di funzionare in questa versione. Per ulteriori informazioni, consultate [Manuale per sviluppatori](/help/migrated/integration-admin/feature-summary/developer-manual.md).

### Notifiche per l’iscrizione o l’annullamento dell’iscrizione al corso

Questa versione introduce il supporto per l’ID istanza del corso con le notifiche nel nuovo attributo dei metadati.

### Supporto feedback L1

Consente all’Allievo di fornire feedback a ogni livello di istanza della funzione Iscrizione multipla.

**API:** `POST /enrollments/{id}/l1Feedback`

### Elenco campi applicati LO

In questa versione è necessario inviare esplicitamente a learningObject sezioni, prequisiteConstraints, prerequisiteLO, subLO, additionalResources, additionalLO, instance e catalogLabels.

Ad esempio,

`enforcedFields[learningObject]=prerequisiteLOs,instances`

### Avviso di annullamento per la prossima versione

* Ignora flag per le API degli Allievi.
* Modificheremo l’impostazione predefinita per highlightResults=false. Inoltre, modificheremo l’impostazione predefinita di snippetType=courseName.
* Verrà deprecato matchType=bool nell&#39;endpoint di ricerca.
* autoCompleteMode presenta [Obsoleto] e per fornire la stessa funzionalità di autoCompleteMode =false, è stato aggiunto un matchType denominato Match.

### Formato ID badge con iscrizione multipla

Per supportare i distintivi delle istanze con iscrizione multipla, stiamo modificando il formato dei distintivi del corso da `userId_badgeId_COURSE_courseId to userId_badgeId_COURSE_courseId_courseInstanceId` per identificare in modo univoco i distintivi.

## Note sulla versione

Per informazioni sulle versioni correnti e precedenti dell’app Web e per dispositivi di Learning Manager, consulta la [Note sulla versione](/help/migrated/release-note/release-notes.md).

## Problemi noti o limitazioni in questa versione

Di seguito sono riportate le limitazioni di questa versione:

### Visualizzazione di contenuti offline nell&#39;app per dispositivi mobili

I seguenti elementi non sono supportati durante la visualizzazione di contenuto offline nell&#39;app:

* Corsi Flex, piani di apprendimento o certificazioni.
* Corsi avanzati, piani di apprendimento o certificazioni.
* Corsi abilitati per più quiz, piani di apprendimento o certificazioni.
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

### Recommendations

I seguenti elementi non sono supportati per Prodotto/Ruolo/Livello nel nuovo sistema di raccomandazione:

* Adobe Experience Manager, Teams, SFDC e Accesso non effettuato.
* L’app per dispositivi mobili non supporta la modifica di Prodotti e ruoli nella pagina Suggerimenti.
* Impossibile eseguire la mappatura durante la migrazione.
* Applicazione automatica di tag a LinkedIn, marketplace dei contenuti e altri corsi, piani di apprendimento o certificazioni esterni.
* Ripristino basato su abilità o classico dopo l’attivazione.
* Il menu di ricerca Prodotti e ruoli nell’app per Allievi.
* Mappatura in blocco di corsi, piani di apprendimento o certificazioni e utenti nell’app per Amministratori.

## Requisiti di sistema

[Requisiti di sistema di Learning Manager](/help/migrated/system-requirements.md)
