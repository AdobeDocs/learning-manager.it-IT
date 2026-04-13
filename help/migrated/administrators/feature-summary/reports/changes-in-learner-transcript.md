---
description: Informazioni sulle Trascrizioni Allievi
jcr-language: en_us
title: Modifiche alle Trascrizioni Allievi
source-git-commit: cd0737061029e75953fa23cf3d12409b1407772a
workflow-type: tm+mt
source-wordcount: '677'
ht-degree: 0%

---


# Modifiche alle Trascrizioni Allievi nella versione di aprile

## Colonna Metodo di completamento

La colonna **Metodo di completamento** indica il modo in cui ogni record della Trascrizione Allievo dell’Amministratore è stato completato.

**Valori:**

1. **Diretta** (per i completamenti diretti)
2. **Alternativo** (per i completamenti ottenuti tramite relazioni alternative)
3. **Alternativa revocata** (quando tutti i completamenti alternativi sono revocati a causa di incompletamento retroattivo e rimozione della relazione)

>[!NOTE]
>
>Questa colonna non è visibile nel LT dell’Allievo; è disponibile solo in Admin LT a scopo di report e tracciamento.

**Impatto**: consente agli amministratori di disporre di audit trail, tracciamento della conformità e trasparenza chiari relativi al completamento di un corso.

## Tracciamento del completamento alternativo nelle Trascrizioni Allievi

I completamenti alternativi consentono agli Allievi di ricevere i crediti di completamento per un corso o percorso di apprendimento target quando hanno completato un corso o percorso di origine equivalente, in base alle relazioni stabilite.

Nella Trascrizione Allievo (LT), i completamenti alternativi influiscono su tre colonne esistenti: **Stato**, **Data di completamento** e **Origine completamento**.

- **Stato**: lo stato può essere **Completato** anche se l’Allievo non ha completato direttamente il corso o il percorso di destinazione a causa di un completamento alternativo. Gli altri stati (**Non avviato**, **In corso**, **Non registrato**) non sono interessati.
- **Data di completamento**: per il completamento alternativo, la data viene ereditata dal corso o percorso di origine. Se l’Allievo completa direttamente l’oggetto in un secondo momento, la data viene aggiornata di conseguenza.
- **Origine completamento**: acquisisce gli ID di formazione dei corsi o percorsi di origine che hanno fornito il completamento alternativo. Più origini attive sono elencate come ID separati da virgole. Se le origini vengono revocate, rimangono solo quelle attive. Se esistono più origini, viene utilizzata la prima data di completamento.

**Impatto**: i completamenti alternativi riducono la riconciliazione manuale, automatizzano il monitoraggio dei progressi nei percorsi di apprendimento e nelle certificazioni e supportano i requisiti di conformità.

>[!NOTE]
>
>Nelle Trascrizioni Allievi non viene visualizzata la colonna **Metodo di completamento**. Questa colonna è disponibile solo nella Trascrizione Allievo Amministratore.

## Logica della data di completamento per le alternative

La colonna **Data di completamento** nella Trascrizione Allievo viene utilizzata per i completamenti diretti e alternativi.

- Per i completamenti alternativi, la data si riferisce a quando l’Allievo ha completato il corso o il percorso di origine.
- Se l’Allievo completa direttamente l’obiettivo in un secondo momento, la data di completamento viene aggiornata alla data di completamento diretto.
- Non viene introdotta alcuna nuova colonna per le date di completamento alternative.
- Se più origini forniscono un completamento alternativo, viene utilizzata la prima data di completamento attiva.
- Se un&#39;origine viene revocata (con incompletamento retroattivo abilitato), la data viene aggiornata alla prima origine attiva successiva oppure viene cancellata se non vi sono altre origini attive.

**Impatto**: assicura un tracciamento cronologico accurato e report coerenti, anche quando le relazioni alternative cambiano nel tempo.

## Completamenti alternativi revocati

I completamenti alternativi revocati si verificano quando vengono rimosse tutte le relazioni di origine per un corso o percorso di apprendimento di destinazione, a condizione che l’incompletamento retroattivo sia abilitato.

### Condizioni di attivazione

- L’incompletamento retroattivo deve essere abilitato a livello di account.
- La revoca avviene solo quando vengono rimosse **tutte** relazioni di origine attive.
- Se rimane almeno un&#39;origine, il completamento alternativo persiste e la colonna origine completamento viene aggiornata di conseguenza.

### Impatto sulla trascrizione Allievo

- **Stato**: se tutti i completamenti alternativi sono stati revocati e non esiste un completamento diretto, lo stato viene aggiornato, ad esempio da **Completato** a **Non avviato** o **In corso**.
- **Data di completamento**: cancellata se non vi sono più origini attive e non vi è un completamento diretto.
- **Origine completamento**: aggiornata per rimuovere le origini revocate. Cancellata se tutte le origini sono revocate.

Se l’Allievo ha un completamento diretto, la revoca delle origini alternative non influisce sullo stato o sulla data di completamento.

>[!NOTE]
>
>Se più sorgenti hanno fornito un completamento alternativo e solo alcune sono state revocate, la trascrizione riflette le sorgenti attive rimanenti e la prima data di completamento. Se tutte le origini sono state revocate e non vi è completamento diretto, l’Allievo perde lo stato di completamento per la destinazione.

## Report migliorati per le osservazioni del revisore dell’elenco di controllo

I commenti dei revisori dei moduli dell’elenco di controllo sono ora inclusi nel report Trascrizione Allievo in una colonna rinominata, **Note del revisore**.

**Impatto**: consente agli Allievi e agli Amministratori di visualizzare il feedback consolidato, migliorando la trasparenza e supportando la valutazione delle prestazioni.

## Calcolo del tempo di apprendimento migliorato

Il report Trascrizione Allievo ora utilizza una logica perfezionata per distinguere tra tempo di apprendimento attivo e inattivo in base all’attività dell’utente e allo stato attivo della scheda del browser.

**Impatto**: fornisce una misurazione più accurata del coinvolgimento degli Allievi, supportando la creazione di report e l’analisi della conformità.
