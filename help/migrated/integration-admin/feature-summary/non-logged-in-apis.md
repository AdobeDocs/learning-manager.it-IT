---
description: Scopri le API che non hanno effettuato l'accesso per sviluppare l'interfaccia headless.
jcr-language: en_us
title: API senza accesso
source-git-commit: 21e2a4a5e73fcbddb64e0afec0a896b315e38688
workflow-type: tm+mt
source-wordcount: '574'
ht-degree: 0%

---

# API senza accesso

Scopri di più sulle API di Adobe Learning Manager, che forniscono dati per l&#39;esperienza headless o senza accesso in questo articolo.
API di ricerca pubblica

## API di ricerca pubblica

### Filtrare i dati utilizzando Public ES

L&#39;API Public Search consente di ottenere i dati del filtro che possono essere utilizzati con l&#39;API di ricerca di base per filtrare i corsi. Questa API fornisce tutti i filtri che possono essere utilizzati nell&#39;API di ricerca.

**Esempio di ricciolo**

Utilizzare il metodo GET per effettuare la richiesta seguente. Sostituisci &lt;Base_URL> con l&#39;URL di base nel comando curl riportato di seguito. &lt;/Base_URL> Puoi trovare &lt;Base_URL> la pagina del connettore di accesso ai dati di formazione.&lt;/Base_URL>

```
curl --location '<Base_URL>/filterableData'
```

**Risposta di esempio**

```
{
    "terms": {
        "loSkillLevels": [
            "1"
        ],
        "catalogNames": [
            "Default Catalog"
        ],
"catalogLabelIds": [
            "0000_1111"
        ],
        "loType": [
            "course"
        ],
        "availability": [
            "waitlistAvailable",
            "seatAvailable"
        ],
        "loSkillNames": [
            "General"
        ],
        "tags": [
            "course_tag"
        ],
        "authors": [
            "author_1"        
]
    },
    "range": {
        "duration": [
            "0"
        ],
        "dateCreated": [
            "2024-06-13T04:32:17.000Z"
        ],
        "price": [
            "0.0"
        ],
        "sessionEndTime": [
            "2024-06-18T20:30:00.000Z"
        ],
        "averageRating": [
            "0.0"
        ],
        "sessionStartTime": [
            "2024-06-18T19:30:00.000Z"
        ],
        "publishDate": [
            "2024-06-13T04:32:51.000Z"
        ],
        "ratingsCount": [
            "0"
        ]
    },
    "term": {}
}
```

**Opzioni del filtro**

| Opzioni | Descrizione |
| --- | --- |
| `loSkillLevels` | Il livello di competenza richiesto per l&#39;iscrizione al corso. |
| `catalogNames` | Elenco dei nomi di catalogo disponibili. |
| `loType` | Tipi di oggetti di apprendimento disponibili. |
| `availability` | La disponibilità dei posti e la disponibilità delle liste d&#39;attesa. |
| `loSkillNames` | I nomi delle abilità aggiunti agli oggetti di apprendimento. |
| `tags` | I tag associati agli oggetti di apprendimento. |
| `authors` | Il nome dell&#39;autore degli oggetti di apprendimento |
| `duration` | La durata degli oggetti di apprendimento. |
| `dateCreated` | Data di creazione dell&#39;oggetto di apprendimento. |
| `sessionEndTime` | Ora di fine della sessione. |
| `averageRating` | La valutazione media a stelle degli oggetti di apprendimento. |
| `sessionStartTime` | Ora di inizio della sessione. |
| `publishDate` | Data di pubblicazione dell&#39;oggetto di apprendimento. |
| `ratingsCount` | Il numero di conteggi di valutazione per l&#39;oggetto di apprendimento. |

### API di ricerca

L&#39;API di ricerca pubblica consente di ottenere dati di ricerca di base utilizzando i dati forniti.

**Esempio di ricciolo**

Utilizzare il metodo POST per effettuare la richiesta seguente. Sostituisci &lt;Base_URL> con l&#39;URL di base nel comando curl riportato di seguito. &lt;/Base_URL> Puoi trovare &lt;Base_URL> la pagina del connettore di accesso ai dati di formazione.&lt;/Base_URL>

```
curl --location '<Base_URL>/search?size=1000' \
--header 'content-type: application/json' 

--data '{
   "query": "",
   
    "sort": {
        "name": "publishDate",
        "order": "desc"
    },
    "lang": [
        "en-US"
    ],
    "filters": {
        "terms": {
            "loType": [
                "course",
                "learningProgram",
                "certification"
            ],
            "availability": [
                "seatAvailable",
                "waitlistAvailable"
            ]
        },
        "term": {
            "enrollmentDeadlinePassed": "true"
        },
        "range": {
                "dateCreated": [
                    {
                        "gte": "2024-05-02T02:48:51.000Z"
                    }
                ],
            "sessionStartTime": [
                {
                   "gte": "2024-06-18T19:30:00.000Z"
                }
            ],
            "sessionEndTime": [
                {
                   "lte": "2024-06-20T09:30:00.000Z"     
                }
            ]
        }
    }
}'
```

**Risposta di esempio della chiamata API**

```
{
    "results": [
        {
            "loId": "course:11332313",
            "loType": "course",
            "tags": [
                "course_tag"
            ],
            "authors": [
                "author1",
                "author2"
            ],
            "status": "Published",
            "duration": 0,
            "publishDate": "2024-06-13T04:32:51.000Z",
            "dateCreated": "2024-06-13T04:32:17.000Z",
            "name": "vc coursse to check ",
            "averageRating": 0.0,
            "ratingsCount": 0,
            "loSkillNames": [
                "General"
            ],
            "loSkillLevels": [
                "1"
            ],
            "loInstances": [
                {
                    "id": "14346696",
                    "name": "Default Instance",
                    "status": "Active",
                    "price": 0.0
                }
            ],
            "catalogInfo": [
                {
                    "id": "37779",
                    "name": "Default Catalog"
                }
            ]
        }
    ],
    "request": {
        "query": "",
        "filters": {
            "terms": {
                "loType": [
                    "course",
                    "learningProgram",
                    "certification"
                ],
                "loSkillNames": [
                    "General"
                ],
                "deliveryType": [],
                "availability": [
                    "seatAvailable",
                    "waitlistAvailable"
                ]
            },
            "term": {
                "enrollmentDeadlinePassed": "true"
            },
            "range": {
                "dateCreated": [
                    {
                        "gte": "2024-05-02T02:48:51.000Z"
                    }
                ],
                "sessionStartTime": [
                    {
                        "gte": "2024-06-18T19:30:00.000Z"
                    }
                ],
                "sessionEndTime": [
                    {
                        "lte": "2024-06-20T09:30:00.000Z"
                    }
                ]
            }
        },
        "sort": {
            "name": "publishDate",
            "order": "desc"
        },
        "lang": [
            "en-US"
        ]
    },
    "self": "<Base_URL>/search?page=0&size=1000",
    "count": 1
}
```

**Opzioni di ordinamento nell&#39;API di ricerca**

È possibile selezionare le seguenti opzioni di ordinamento da applicare ai risultati.

| Opzioni | Descrizione |
| --- | --- |
| `duration` | La durata dell&#39;oggetto di apprendimento. |
| `publishDate` | Data di pubblicazione dell&#39;oggetto di apprendimento. |
| `dateCreated` | Data di creazione dell&#39;oggetto di apprendimento. |
| `name_en` | Il nome dell&#39;oggetto di apprendimento. |
| `averageRating` | Valutazione media in stelle fornita dagli Allievi. |
| `ratingsCount` | Il numero di conteggi di valutazione per l&#39;oggetto di apprendimento. |
| `relevance(default)` | I dati rilevanti si basano sulle parole chiave di ricerca. |

### Ottenere dati sugli oggetti di apprendimento tramite l&#39;API di ricerca pubblica

L&#39;API Public ES Learning Object consente di ottenere l&#39;elenco dei tipi e degli ID degli oggetti di apprendimento disponibili sull&#39;interfaccia headless.

**Esempio di ricciolo**

Utilizzare il metodo GET per effettuare la richiesta seguente. Sostituisci &lt;Base_URL> con l&#39;URL di base nel comando curl riportato di seguito. &lt;/Base_URL> Puoi trovare &lt;Base_URL> la pagina del connettore di accesso ai dati di formazione.&lt;/Base_URL>

```
curl --location '<Base_URL>/learningObjectIds'
```

**Risposta di esempio per la chiamata API**

```
{
    "loIds": [
        "course:1132800",
"certification:126009",
"learningProgram:104433"
    ]
}
```

## API di riepilogo del corso

L&#39;API di riepilogo del corso consente di recuperare informazioni dettagliate su un corso specifico.

**Esempio di ricciolo**

Utilizzare il metodo GET per effettuare la richiesta seguente. Sostituisci &lt;Base_URL> con l&#39;URL di base nel comando curl riportato di seguito. &lt;/Base_URL> Puoi trovare &lt;Base_URL> la pagina del connettore di accesso ai dati di formazione. &lt;/Base_URL> Sostituisci &lt;Course_ID> con l&#39;ID corso specifico.&lt;/Course_ID>

```
curl --location '<Base_URL>/loSummary?loId=course%3A<Course_ID>'
```

**Risposta di esempio della chiamata API**

```
{
    "results": [
        {
            "instanceId": "14336686",
            "courseId": "11312313",
            "accountId": "44355",
            "seatConsumed": 1,
            "seatLimit": 1,
            "waitlistLimit":1,
            "waitlistCount": 1,
            "seatAvailable": false,
            "waitlistAvailable": false
        }
    ],
    "count": 1
}
```

>[!NOTE]
>
>Se un corso ha più istanze, otterrai i dettagli per tutte le istanze.

## CDN JSON API per i dettagli del corso

L&#39;API JSON CDN consente di recuperare le informazioni complete sul corso di un corso specifico.

**Esempio di ricciolo per il corso**

Utilizzare il metodo GET per effettuare la richiesta seguente. Sostituisci &lt;CDN_path> con l&#39;URL di base nel comando curl riportato di seguito. &lt;/CDN_path> Puoi trovare &lt;CDN_path> la pagina del connettore di accesso ai dati di formazione. &lt;/CDN_path> Sostituisci &lt;Course_ID> con l&#39;ID corso specifico.&lt;/Course_ID>

```
curl --location '<CDN_path_URL>/course/<Course_ID>.json'
```

**Ricciolo di esempio per il percorso di apprendimento e la certificazione**

```
curl --location '<CDN_path_URL>/learningProgram/<LearningProgram_ID>.json'
```

```
curl --location '<CDN_path_URL>/ certification /<Certification_ID>.json'
```

**Risposta di esempio della chiamata API**

```
{
    "data": {
        "id": "course:11342313",
        "type": "learningObject",
        "attributes": {
            "authorNames": [
                "author1",
                "author2"
            ],
            "dateCreated": "2024-06-13T04:32:17.000Z",
            "datePublished": "2024-06-13T04:32:51.000Z",
            "dateUpdated": "2024-06-13T04:32:51.000Z",
            "duration": 0,
            "effectiveModifiedDate": "2024-06-13T04:32:51.000Z",
            "effectivenessIndex": 0,
            "enrollmentType": "Self Enroll",
            "hasOptionalLoResources": false,
            "hasPreview": false,
            "isExternal": false,
            "isMqaEnabled": false,
            "isPrerequisiteEnforced": false,
            "isSubLoOrderEnforced": false,
            "loResourceCompletionCount": 1,
            "loType": "course",
            "moduleResetEnabled": false,
            "state": "Published",
            "tags": [
                "course_tag"
            ],
            "unenrollmentAllowed": true,
            "localizedMetadata": [
                {
                    "description": "",
                    "locale": "en-US",
                    "name": "vc coursse to check "
                }
            ],
            "rating": {
                "averageRating": 0,
                "ratingsCount": 0
            }
        },
        "relationships": {
            "authors": {
                "data": [
                    {
                        "id": "13138897",
                        "type": "user"
                    }
                ]
            },
            "instances": {
                "data": [
                    {
                        "id": "course:11332313_14336696",
                        "type": "learningObjectInstance"
                    }
                ]
            },
            "skills": {
                "data": [
                    {
                        "id": "course:11332313_237719",
                        "type": "learningObjectSkill"
                    }
                ]
            }
        }
    },
    "included": [
        {
            "id": "237719",
            "type": "skill",
            "attributes": {
                "name": "General",
                "state": "Active"
            },
            "relationships": {
                "levels": {
                    "data": [
                        {
                            "id": "237719_1",
                            "type": "skillLevel"
                        }
                    ]
                }
            }
        },
        {
            "id": "course:11312313",
            "type": "learningObject",
            "attributes": {
                "authorNames": [
                    "m 41",
                    "rae"
                ],
                "dateCreated": "2024-06-13T04:32:17.000Z",
                "datePublished": "2024-06-13T04:32:51.000Z",
                "dateUpdated": "2024-06-13T04:32:51.000Z",
                "duration": 0,
                "effectiveModifiedDate": "2024-06-13T04:32:51.000Z",
                "effectivenessIndex": 0,
                "enrollmentType": "Self Enroll",
                "hasOptionalLoResources": false,
                "hasPreview": false,
                "isExternal": false,
                "isMqaEnabled": false,
                "isPrerequisiteEnforced": false,
                "isSubLoOrderEnforced": false,
                "loResourceCompletionCount": 1,
                "loType": "course",
                "moduleResetEnabled": false,
                "state": "Published",
                "tags": [
                    "course_tag"
                ],
                "unenrollmentAllowed": true,
                "localizedMetadata": [
                    {
                        "description": "",
                        "locale": "en-US",
                        "name": "course name "
                    }
                ],
                "rating": {
                    "averageRating": 0,
                    "ratingsCount": 0
                }
            },
            "relationships": {
                "authors": {
                    "data": [
                        {
                            "id": "13128897",
                            "type": "user"
                        }
                    ]
                },
                "instances": {
                    "data": [
                        {
                            "id": "course:11312313_14336696",
                            "type": "learningObjectInstance"
                        }
                    ]
                },
                "skills": {
                    "data": [
                        {
                            "id": "course:11312313_237719",
                            "type": "learningObjectSkill"
                        }
                    ]
                }
            }
        },
        {
            "id": "course:11312313_14336696_12034506_0",
            "type": "learningObjectResource",
            "attributes": {
                "externalReporting": false,
                "isExpiredSubmission": false,
                "loResourceType": "Content",
                "multipleAttemptEnabled": false,
                "previewEnabled": false,
                "resourceType": "Virtual Classroom",
                "submissionEnabled": false,
                "localizedMetadata": [
                    {
                        "description": "",
                        "locale": "en-US",
                        "name": "vc session"
                    }
                ]
            },
            "relationships": {
                "learningObject": {
                    "data": {
                        "id": "course:11312313",
                        "type": "learningObject"
                    }
                },
                "resources": {
                    "data": [
                        {
                            "id": "course:11312313_14336696_12034506_0_resource",
                            "type": "resource"
                        }
                    ]
                }
            }
        },
        {
            "id": "course:11312313_237719",
            "type": "learningObjectSkill",
            "attributes": {
                "credits": 1,
                "learningObjectId": "course:11312313"
            },
            "relationships": {
                "skillLevel": {
                    "data": {
                        "id": "237719_1",
                        "type": "skillLevel"
                    }
                }
            }
        },
        {
            "id": "13128897",
            "type": "user",
            "attributes": {
                "avatarUrl": "https://abccontents.adobe.com/public/images/default_user_avatar.svg",
                "binUserId": "1f8c01aa-7f58-42e9-bc40-11537eb6498d",
                "email": "manjusha+41re@adobetest.com",
                "enrollOnClick": false,
                "gamificationEnabled": true,
                "lastLoginDate": "2024-06-13T04:23:45.000Z",
                "name": "m 41",
                "pointsEarned": 0,
                "pointsRedeemed": 0,
                "preferredResolution": "AUTO",
                "profile": "admin",
                "roles": [
                    "Learner",
                    "Admin",
                    "Author",
                    "Instructor",
                    "Integration Admin"
                ],
                "state": "ACTIVE",
                "userType": "Internal"
            },
            "relationships": {
                "account": {
                    "data": {
                        "id": "44355",
                        "type": "account"
                    }
                }
            }
        },
        {
            "id": "course:11312313_14336696_12034506_0_resource",
            "type": "resource",
            "attributes": {
                "avatarUrls": [
                    "https://abccontents.adobe.com/public/images/default_user_avatar.svg"
                ],
                "completionDeadline": "2024-06-18T20:30:00.000Z",
                "contentType": "Virtual Classroom",
                "dateStart": "2024-06-18T19:30:00.000Z",
                "desiredDuration": 3600,
                "hasQuiz": false,
                "hasToc": false,
                "instructorNames": [
                    "instructor1"
                ],
                "isDefault": true,
                "locale": "en-US",
                "location": "http://google.com",
                "name": "vc session",
                "onlyQuiz": false,
                "reportingType": "NONE"
            }
        },
        {
            "id": "course:11312313_14336696",
            "type": "learningObjectInstance",
            "attributes": {
                "dateCreated": "2024-06-13T04:32:18.000Z",
                "isDefault": true,
                "isFlexible": false,
                "state": "Active",
                "localizedMetadata": [
                    {
                        "locale": "en-US",
                        "name": "Default Instance"
                    }
                ],
                "seatConsumed": 0,
                "waitlistCount": 0
            },
            "relationships": {
                "learningObject": {
                    "data": {
                        "id": "course:11312313",
                        "type": "learningObject"
                    }
                },
                "loResources": {
                    "data": [
                        {
                            "id": "course:11312313_14336696_12034506_0",
                            "type": "learningObjectResource"
                        }
                    ]
                }
            }
        },
        {
            "id": "237719_1",
            "type": "skillLevel",
            "attributes": {
                "level": "1",
                "maxCredits": 1,
                "name": "Level 1"
            },
            "relationships": {
                "skill": {
                    "data": {
                        "id": "237719",
                        "type": "skill"
                    }
                }
            }
        }
    ]
}
```
