---
jcr-language: en_us
title: Invio di corsi di formazione esterni in Adobe Learning Manager
description: I Manager possono esaminare le richieste di apprendimento esterno inviate dai membri del team, verificare i dettagli e qualsiasi prova di completamento e approvare o rifiutare ogni richiesta con un commento facoltativo. Gli invii approvati vengono aggiunti alla Trascrizione Allievo.
contentowner: saghosh
source-git-commit: 2495d33fc1595bd962ba07988123e3563d4c69a0
workflow-type: tm+mt
source-wordcount: '761'
ht-degree: 1%

---


# Rivedi le richieste di apprendimento esterne come Manager

Quando un Allievo del team invia una richiesta di apprendimento esterna in Adobe Learning Manager, riceverai una notifica nella piattaforma. Puoi esaminare i dettagli dell’invio, approvare o rifiutare la richiesta e aggiungere un commento per l’Allievo.

## Funzionamento del flusso di lavoro di revisione del manager

Quando un Allievo invia una richiesta di apprendimento esterna, si verifica quanto segue:

1. Riceverai una **notifica in-app** che ti chiederà di rivedere l&#39;invio. L’invio viene visualizzato nella scheda **Apprendimento esterno** nel dashboard di gestione.
2. Apri un inoltro, esamina tutti i campi e qualsiasi documento caricato come prova e seleziona **Approva** o **Rifiuta**.
3. Puoi aggiungere un **commento di revisione** che l’Allievo vede quando riceve la notifica.
4. L’Allievo riceve una **notifica nella piattaforma** con la tua decisione.

Se approvi un invio, l’attività di apprendimento esterna viene aggiunta alla **Trascrizione Allievo Amministratore** e visualizzata nel record della trascrizione dell’Allievo.

<!--You can also change a previously **Rejected** submission to **Approved** if the circumstances change.-->

## Rivedere e approvare o rifiutare un inoltro

1. Accedi a Adobe Learning Manager come Manager.

2. Seleziona **Apprendimento esterno** nel riquadro di navigazione a sinistra.

3. Nell&#39;elenco di invio selezionare la richiesta che si desidera esaminare. Gli invii vengono ordinati in base alla data di invio, con il più recente nella parte superiore.

4. Rivedi l&#39;intero invio:

   - Titolo, descrizione, date, durata e punteggio

   - Eventuali campi personalizzati configurati dall&#39;amministratore

   - Documento di prova allegato, se disponibile. Selezionare l&#39;allegato per visualizzarlo o scaricarlo

5. Seleziona **Approva** o **Rifiuta**.

6. Nel campo **Commento revisione**, immetti eventuali note per l’Allievo. Questa opzione è facoltativa ma consigliata quando si rifiuta una richiesta, in modo che l’Allievo sappia cosa correggere.

7. Seleziona **Invia**.

L’Allievo riceve una notifica in-app della tua decisione. Se l’hai approvato, l’invio viene ora visualizzato nella Trascrizione Allievo.

## Gestire la coda di invio

La coda di apprendimento esterna mostra tutti gli invii in sospeso e passati dai report diretti.

**Filtra per stato**

Utilizzare il filtro **Stato** per restringere l&#39;elenco:

- **Tutti**- mostra ogni invio indipendentemente dallo stato

- **In attesa di revisione-** mostra solo gli invii in attesa di revisione

- **Approvato-** mostra gli invii già approvati

- **Rifiutato-** mostra gli invii che hai rifiutato

**Cerca e ordina**

- Utilizza il campo **Ricerca** per trovare gli invii in base al nome dell’Allievo.

- Per impostazione predefinita, gli invii vengono ordinati in base alla data di invio, a partire dal più recente.

### Regole di instradamento approvazione

Per impostazione predefinita, gli invii esterni per la formazione vengono indirizzati al manager diretto di un Allievo. Quando a un Allievo non è assegnato un Direct Manager, si applicano le regole seguenti:

| **L’Allievo ha un Manager** | **L’Allievo è anch’egli un Manager** | **Invio instradato a** |
|---------------------------|-------------------------------------|---------------------------------------------------------------------------------------------------------------------|
| Sì | No | Direct manager (caso predefinito) |
| Sì | Sì | Direct manager (caso predefinito) |
| No | No | Utente dell’account principale, se ha un ruolo di manager; in caso contrario, l’invio viene approvato automaticamente. |
| No | Sì | Utente dell’account principale, se ha un ruolo di manager; in caso contrario, l’invio viene indirizzato all’Allievo. |

In caso di domande sull’assegnazione del manager per uno specifico Allievo, contatta l’amministratore del tuo account.

## Report sull’apprendimento esterno e modifiche alla trascrizione

Quando l’invio di apprendimento esterno di un Allievo viene approvato in Adobe Learning Manager, l’attività viene aggiunta al sistema di reporting e visualizzata sia nella Trascrizione Allievo Amministratore che nella Trascrizione Allievo.

### Aspetto dell’apprendimento esterno nelle Trascrizioni Allievi

**Nota:** l’abilitazione dell’apprendimento esterno aggiunge le seguenti nuove colonne alla Trascrizione Allievo amministratore: **Nome apprendimento esterno**, **Commento di completamento** e una colonna dinamica per ogni campo personalizzato. Le colonne dei campi personalizzati vengono sempre visualizzate alla fine dell’esportazione. Se i dati Trascrizione Allievo confluiscono in strumenti di reporting automatico o BI, assicurati che tali pipeline siano aggiornate per gestire le colonne aggiuntive.

Nelle trascrizioni vengono visualizzati solo **gli invii di apprendimento esterni approvati**. Gli invii con stato **In attesa di approvazione** o **Rifiutato** non sono inclusi nelle esportazioni delle trascrizioni.

L’Amministratore Trascrizione Allievo e la Trascrizione Allievo gestiscono il titolo di apprendimento esterno in modo diverso:

- Nella **Trascrizione Allievo amministratore**, il titolo dell’apprendimento esterno viene inserito nella colonna **LP/Certificazione/Corso** esistente, mantenendo la struttura delle colonne coerente con altri tipi di attività di apprendimento.

- Nella **Trascrizione Allievo** (generata dall’Allievo), subito dopo la colonna **Modulo** viene aggiunta una nuova colonna denominata **Nome apprendimento esterno**.

I campi personalizzati configurati dall’amministratore vengono visualizzati come colonne dinamiche alla fine di entrambe le esportazioni di trascrizioni, una volta approvato un invio.

Il filtro basato sulla data nella Trascrizione Allievo Amministratore per le righe di apprendimento esterne si basa sulla **data di completamento**, che corrisponde alla data di approvazione.