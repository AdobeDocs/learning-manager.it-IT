---
description: Modifiche API in ALM
jcr-language: en_us
title: Modifiche alle API nella versione patch di maggio 2026
product_v2:
  - id: ed12e5b7-96e3-45e7-a17f-de222065ebcb
    internal-label: Learning Manager
source-git-commit: c061ccbefe8d40154220587796062d335e35de77
workflow-type: tm+mt
source-wordcount: '114'
ht-degree: 0%
---

# Modifiche alle API nella versione patch di maggio 2026

## Miglioramento dell’API GET /learningObjects

L’API GET /learningObjects ora include un nuovo attributo startDate nella risorsa learningObjectInstance quando viene inclusa la relazione tra le istanze.

**Endpoint**
GET /learningObjects/{id}?include=instance

**Modifica**
È stato aggiunto un nuovo campo, startDate, in:
incluso[].attributes.startDate

**Descrizione**
startDate rappresenta la data e l’ora di inizio pianificate di un’istanza dell’oggetto di apprendimento.

**Esempio**
https://learningmanagerstage1.adobe.com/primeapi/v2/learningObjects/course:13209797?include=instances
Risposta del campione (troncata)

```
{
  "id": "course:13209797_16226533",
  "type": "learningObjectInstance",
  "attributes": {
    "dateCreated": "2026-05-20T04:35:46.000Z",
    "isAET": false,
    "isDefault": true,
    "isFlexible": false,
    "startDate": "2026-10-06T18:29:59.000Z",
    "state": "Active",
    "timeZoneCode": "IST"
  }
}
```

**Note**

* Il campo viene restituito solo per le istanze dell’oggetto di apprendimento applicabili.
* Il valore viene restituito nel formato data-ora UTC secondo la norma ISO 8601.
* Le integrazioni esistenti restano compatibili con le versioni precedenti.
