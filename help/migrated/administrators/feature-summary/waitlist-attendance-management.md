---
jcr-language: en_us
title: Gestione delle liste di attesa e di frequenza
description: Gli Amministratori possono gestire le liste di attesa e di frequenza per i corsi degli Allievi.
contentowner: manochan
exl-id: 257ed196-d6a7-4d6c-bd90-33d658f6ba55
product_v2:
  - id: ed12e5b7-96e3-45e7-a17f-de222065ebcb
    internal-label: Learning Manager
source-git-commit: 38dba6765ff013e446ab1f6098e9f1df0c24d0f9
workflow-type: tm+mt
source-wordcount: '430'
ht-degree: 38%
---
# Gestione delle liste di attesa e di frequenza

Gli Amministratori possono gestire le liste di attesa e di frequenza per i corsi degli Allievi.

## Gestione delle liste di attesa {#waitlistmanagement}

Gli Allievi vengono inseriti in lista d’attesa per un corso in aula quando i posti sono limitati, in base all’ordine di iscrizione. Quando tutte le postazioni riservate a un gruppo di utenti vengono occupate, gli altri membri del gruppo vengono inseriti nella lista d’attesa del gruppo. Gli Allievi esterni ai gruppi di utenti vengono inseriti nella **lista d’attesa aperta**.

Gli Amministratori possono rivedere la lista d’attesa e gestire gli Allievi in lista d’attesa. Adobe Learning Manager può inoltre promuovere automaticamente gli Allievi inseriti in lista d’attesa quando diventa disponibile un posto.

Per gestire gli Allievi nella lista d’attesa:

1. Seleziona **Corsi** nel riquadro a sinistra.
1. Seleziona il nome di un corso in aula dai corsi disponibili.

   Viene visualizzata una nuova pagina contenente informazioni dettagliate sul corso.

1. Seleziona **Lista d’attesa** nel riquadro a sinistra della pagina dei dettagli del corso.

   Viene aperta la pagina della lista d&#39;attesa con il seguente **stato della lista d&#39;attesa**:

   * **Limite partecipanti:** Numero totale di partecipanti disponibili per la sessione.
   * **Pieno:** numero di posti attualmente occupati.
   * **In lista d’attesa:** numero di allievi in attesa di iscrizione.

1. Selezionare le schede seguenti nella pagina **Lista d&#39;attesa**:

   1. **Lista d’attesa per gruppo di utenti**: elenca gli Allievi in lista d’attesa in ciascun gruppo di utenti.

   >[!NOTE]
   >
   >Questa scheda viene visualizzata solo se l&#39;impostazione **Registrazione gruppo** è abilitata.

   1. **Apri lista d’attesa**: elenca gli Allievi in lista d’attesa non riservati ad alcun gruppo di utenti.

   ![Pagina della lista d&#39;attesa che mostra la scheda Lista d&#39;attesa per gruppo di utenti](assets/waitlist-by-user-group-tab.png "Pagina della lista d&#39;attesa che mostra la scheda Lista d&#39;attesa per gruppo di utenti")

1. Accanto a un Allievo, seleziona una delle seguenti azioni:

   | **Azione** | **Descrizione** |
   |---|---|
   | **Conferma** | Iscrive l’Allievo in lista d’attesa nella sessione e lo rimuove dalla lista d’attesa. |
   | **Annulla iscrizione** | Rimuove l’Allievo dalla lista d’attesa e aggiorna le posizioni degli Allievi rimanenti nella lista d’attesa. |

## Gestione della frequenza {#attendancemanagement}

Questa funzione è applicabile solo ai corsi in aula e in aula virtuale. Puoi registrare le presenze procedendo come segue:

1. Fai clic su Corsi nel riquadro a sinistra dopo avere effettuato l’accesso come Amministratore.
1. Dall’elenco dei corsi disponibili, fai clic sul nome di un corso/modulo in aula a tua scelta. Viene visualizzata una nuova pagina contenente informazioni dettagliate sul corso.
1. Fai clic sulla scheda Frequenza, seleziona gli Allievi e fai clic su Salva per contrassegnare la frequenza.

>[!NOTE]
>
>Se sono presenti più moduli in un corso e l’Allievo ne ha completato solo uno, puoi selezionare un singolo modulo e fare clic su Salva. Se l’Allievo completa tutti i moduli di un corso, puoi fare clic sull’opzione Seleziona tutti e poi su Salva.

La frequenza ad Adobe Connect basata su sessioni in aula virtuale viene contrassegnata automaticamente nelle 2-3 ore successive alla sessione. Il completamento del corso in aula virtuale dell’Allievo viene contrassegnato solo dopo aver rilevato la frequenza.
