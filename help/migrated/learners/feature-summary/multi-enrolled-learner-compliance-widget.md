---
description: Scopri come il widget Conformità Allievo elenca tutte le istanze di un corso a iscrizione multipla con una scadenza e come l’API la supporta
jcr-language: en_us
title: Corsi a iscrizione multipla da visualizzare nel widget Conformità Allievo
exl-id: 6484c815-ecae-4a75-ba10-ef42e4ff50a6
source-git-commit: d762bc8f199b703169878acbb52d0d7e3e0d6973
workflow-type: tm+mt
source-wordcount: '351'
ht-degree: 1%
---

# Corsi con iscrizione multipla nel widget Conformità Allievo

In Adobe Learning Manager, un Allievo può essere iscritto a più di un’istanza dello stesso corso. Il widget Conformità Allievo ora elenca tutte le istanze registrate con una scadenza, in modo che gli Allievi vedano ogni data di scadenza anziché solo l’istanza principale.

## Cosa cambia per i corsi a iscrizione multipla

Prima di questa modifica, il widget Conformità mostrava solo l’istanza principale di un corso a più iscrizioni. Un Allievo che era iscritto in diverse istanze non riusciva a visualizzare le scadenze per gli altri utenti nel widget.

Ora, il widget Conformità mostra ogni istanza che soddisfa tutte queste condizioni:

* L’Allievo è iscritto all’istanza.
* L’istanza ha una scadenza.
* L’Allievo non ha completato l’istanza.

Ogni voce mostra il nome dell’istanza, in modo che gli allievi possano distinguere le istanze dello stesso corso. Quando un Allievo seleziona una voce, Adobe Learning Manager apre direttamente l’istanza.

Ad esempio, un Allievo completa un corso di formazione iniziale. Un amministratore successivamente iscrive l’Allievo nelle edizioni di settembre, ottobre e novembre dello stesso corso, ciascuna con una scadenza. Il widget Conformità elenca tutte e tre le edizioni.

Il widget conta ciascuna istanza separatamente in ciascuna categoria di conformità: **Scaduto**, **Scadenza imminente entro i prossimi 30 giorni** e **In linea**.

## Istanze visualizzate nel widget Conformità

Nella tabella seguente viene descritto come il widget gestisce ogni situazione di iscrizione.

| Situazione di iscrizione | Viene visualizzato nel widget | Note |
|--------------------------------------------------|-----------------------------------|---------------------------------------|
| Iscritto, l’istanza ha una scadenza, non è stata completata | Sì | Visualizzato con il nome dell&#39;istanza |
| Iscritto, istanza senza scadenza | No | Vengono visualizzate solo le istanze con una scadenza |
| Istanza completata | No | Un&#39;istanza completata non è elencata |
| Completato in tutte le istanze registrate | No | Il corso non viene più visualizzato |
| Un&#39;istanza con una scadenza e una senza | Solo l’istanza con una scadenza |                                       |
| Solo un&#39;istanza registrata | Sì | Il widget mostra tale istanza |

Per informazioni sulle API, consulta [Supporto API per istanze con iscrizione multipla nell&#39;app per Allievi](/help/migrated/api-changes-dec-2026.md#multi-enrolled-compliance-widget).
