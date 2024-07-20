---
jcr-language: en_us
title: Aggiungere aule
description: Gli amministratori possono ora creare una libreria di aule. Per ogni aula, gli amministratori possono configurare i metadati che includono nome della posizione, limite di partecipanti e informazioni aggiuntive come l’URL. Autori e gli Amministratori possono quindi utilizzare questi percorsi preconfigurati per configurare di eventi di formazione guidati da istruttori (moduli aula).
contentowner: saghosh
exl-id: 51a1e38f-d4e2-4c19-bbf7-6696505c0dfd
source-git-commit: 8cb8a95812c97b0b59a2ae5188500cfafe09bd27
workflow-type: tm+mt
source-wordcount: '1315'
ht-degree: 54%

---

# Aula

## Panoramica

Gli amministratori possono ora creare una libreria di aule. Per ogni aula, gli amministratori possono configurare i metadati che includono nome della posizione, limite di partecipanti e informazioni aggiuntive come l’URL. Autori e gli Amministratori possono quindi utilizzare questi percorsi preconfigurati per configurare di eventi di formazione guidati da istruttori (moduli aula).

È possibile aggiungere un’aula nei due modi riportati di seguito.

## Aggiungere un’aula a partire dall’interfaccia utente

È possibile aggiungere un’aula utilizzando l’interfaccia utente:

1. Nell’app Amministratore (l’interfaccia utente per i ruoli di amministratore), fai clic su **[!UICONTROL Impostazioni]** > **[!UICONTROL Aule]**.

1. Fai clic su **[!UICONTROL Aggiungi]** > **[!UICONTROL Nuova posizione]**.

1. Nella finestra di dialogo **[!UICONTROL Aula]**, inserisci le informazioni seguenti:

   * Digitare il **[!UICONTROL nome del percorso]**. Usa un nome unico. In caso contrario, ti verrà mostrato un messaggio di errore in Learning Manager.
   * Inserisci la descrizione dell’aula nel campo **[!UICONTROL Informazioni aula]**. Questo campo è facoltativo.
   * Inserisci l’**[!UICONTROL URL dell’aula]**. Gli Allievi possono visualizzare queste informazioni nei dettagli dell’aula. L’URL può anche essere una posizione su una mappa, se necessario. Questo campo è opzionale.
   * Digitare e selezionare l&#39;**[!UICONTROL area geografica]**. Questo campo è facoltativo.
   * Inserisci il numero di posti disponibili nel campo **[!UICONTROL Limite partecipanti]**. Quest’informazione si riferisce al numero di posti a sedere disponibili nell’aula. Quando si crea l’evento di formazione vero e proprio, questo valore può essere modificato.

   ![](assets/add-classroom-location.png)

   *Aggiungi aula*

Dopo aver aggiunto l’aula, la pagina **[!UICONTROL Impostazioni]** > **[!UICONTROL Aule]** elenca le sale riunioni:

![](assets/list-meeting-rooms.png)

*Visualizza tutte le sale riunioni*

L’elenco contiene i seguenti campi:

**[!UICONTROL Nome aula]**: nome dell’aula.

**[!UICONTROL Sessioni future]**: numero di eventi che si verificheranno nel percorso corrispondente. Fai clic sul numero per visualizzare i dettagli in una finestra di dialogo.

![](assets/sessions-list.png)

*Visualizza sessioni future*

Nella finestra di dialogo vengono visualizzati i dettagli di ogni sessione, come il nome, il nome del corso di formazione che include la sessione e il programma. L’ora visualizzata si adatta al fuso orario di sistema dell’Allievo.

Il campo **[!UICONTROL Sessioni future]** visualizza **zero** quando l&#39;aula non è utilizzata per alcuna sessione o quando l&#39;aula è associata a sessioni passate.

**[!UICONTROL Limite partecipanti]** - Visualizza la capacità dell&#39;aula.

**URL aula** - URL fornito durante la creazione dell’aula.

**Informazioni sulla posizione**: le informazioni sull’aula che hai fornito durante la creazione.

### Modificare le aule

Per modificare l’aula, procedi come segue:

1. Nell’app Amministratore (l’interfaccia utente per i ruoli di amministratore), seleziona **[!UICONTROL Impostazioni]** > **[!UICONTROL Aule]**.

1. Passa il mouse sulla posizione dell’aula che desideri modificare.

1. Seleziona l’icona **[!UICONTROL Modifica aula]**.

1. Modifica la posizione dell&#39;aula e seleziona **[!UICONTROL Salva]**.

## Aggiungere un’aula con CSV

In alternativa, puoi aggiungere una o più aule importando un file CSV contenente le informazioni dell’aula.

In **[!UICONTROL App per amministratori]** > **[!UICONTROL Impostazioni]** > **[!UICONTROL Aule]** > **[!UICONTROL Aggiungi]**, fai clic sul pulsante **[!UICONTROL Percorsi importazione in blocco]**. Individua il percorso contenente il file CSV e selezionalo.

Il file CSV utilizza questi campi per memorizzare i dettagli relativi a una o più aule:

* name
* info
* url
* Regione di 
* seatLimit

I titoli possono essere personalizzati.

Il file CSV deve contenere obbligatoriamente tutte le colonne nello stesso ordine specificato qui.

Dopo l’importazione del file CSV da parte del sistema, le aule vengono aggiunte alla libreria.

## Cercare le aule

Per cercare le classi, seleziona il corso in aula virtuale, quindi vai a **[!UICONTROL Istanze]** > **[!UICONTROL Sessioni]**. Gli Autori e gli Amministratori possono iniziare a digitare il nome dell’aula, e vedranno apparire i risultati pertinenti. In seguito possono selezionare una posizione dai risultati visualizzati. Se nei risultati del tipo successivo non viene visualizzata alcuna aula, l’utente può comunque aggiungere il nome della nuova aula. Tieni presente che l’aula che crei in questo modo, usando il flusso di creazione di una sessione, non viene aggiunta alla libreria di aule creata dall’Amministratore.

Quando aggiungi un’aula, la piattaforma di apprendimento ti fa sapere anche se l’aula è già stata prenotata nella fascia oraria selezionata. Fornisce anche dei suggerimenti con fasce orarie alternative. In questo modo, se decide di utilizzare la stessa aula, l’Autore può modificare l’orario della riunione.

![](assets/classroom-search.png)

*Cerca classi*

## L’Amministratore

In qualità di Amministratore, puoi gestire gli Istruttori e le istanze del corso.

### Configurazione degli istruttori:

Nell&#39;app per amministratori, in **[!UICONTROL Impostazioni]** > **[!UICONTROL Generali]**, gli amministratori possono trovare l&#39;opzione **[!UICONTROL Gestione Istruttori]**. Questa funzione garantisce che solo gli utenti approvati in precedenza assegnati come istruttori possano essere aggiunti per condurre sessioni.

Per assegnare un Istruttore, effettua le seguenti operazioni:

1. Passa alla pagina **[!UICONTROL Guida introduttiva]** e seleziona **[!UICONTROL Utenti]** nel riquadro a sinistra.

1. Selezionare l&#39;utente desiderato.

1. Assegna all&#39;utente il ruolo di istruttore selezionando **[!UICONTROL Azioni]** > **[!UICONTROL Assegna ruolo]**.

### Annullamento delle sessioni:

Nella pagina **[!UICONTROL Istanza del corso]**, gli amministratori possono annullare una o più sessioni. Quando le sessioni vengono annullate, il sistema rimuove tutti i dettagli della sessione ma mantiene il limite di partecipanti.

Inoltre, gli amministratori possono:

* **[!UICONTROL Visualizza iscrizione]**: ottieni informazioni sugli Allievi iscritti e in lista d’attesa per ogni sessione.
* **[!UICONTROL Annullamento dell’iscrizione degli Allievi]**: rimozione degli Allievi da un corso con sessioni annullate senza modifica dello stato di iscrizione.
* **[!UICONTROL Gestione delle presenze]**: contrassegna la partecipazione per le sessioni, anche se queste vengono annullate.
* **[!UICONTROL Completamento del corso]**: gli amministratori possono contrassegnare un corso come completato anche se le sessioni sono state annullate.
* **[!UICONTROL Riprogrammazione]**: pianifica le sessioni annullate per le date successive e aggiungi un istruttore durante la riprogrammazione.

Tieni presente che, dopo l’annullamento, gli Allievi rimangono iscritti all’istanza di formazione. Il loro stato di iscrizione (ad esempio iscrizione confermata, in lista d’attesa e in attesa di approvazione del manager) rimane invariato. Questa funzione è utile in quanto l’amministratore può impostare e riprogrammare la sessione annullata in futuro.

## Autore

Se l’amministratore seleziona l’opzione **[!UICONTROL Gestione Istruttori]**, l’autore può cercare e aggiungere solo utenti con il ruolo di istruttore alle sessioni in aula, in aula virtuale, agli elenchi di controllo e ai moduli che richiedono l’invio di file.

Inoltre, l’autore può:

* Aggiungere e rimuovere istruttori dalle sessioni esistenti.
* Aggiungere istruttori alle sessioni esistenti che dispongono già di uno o più istruttori.

Pertanto, dopo che un amministratore ha abilitato l&#39;opzione **[!UICONTROL Gestione Istruttori]**, solo gli utenti con il ruolo di istruttore possono essere aggiunti come tali.

>[!NOTE]
>
>Questo non si applica alla migrazione delle sessioni tramite il file CSV. In questo caso, anche un utente che non dispone del ruolo di Istruttore può essere aggiunto come tale.

Nella pagina **[!UICONTROL Istanza del corso]**, un autore può annullare una o più sessioni. Quando le sessioni vengono annullate, il sistema rimuove tutti i dettagli della sessione ma mantiene il limite di partecipanti.

Pertanto, un autore può utilizzare i collegamenti **[!UICONTROL Annulla sessione]** per annullare una o più sessioni in aula o in aula virtuale disponibili nella stessa istanza del corso o in istanze diverse.

## Limitare l’elenco di possibili istruttori

Al momento, gli utenti possono aggiungere qualsiasi utente registrato nel campo “Istruttore” durante la creazione di un’aula o di una sessione in aula virtuale. Questo è possibile anche su questa versione.

Tuttavia, gli amministratori dispongono ora di un’opzione aggiuntiva per limitare il numero di utenti che possono essere inseriti come istruttori sulla piattaforma. In questo modo, è possibile evitare che vengano aggiunti nuovi istruttori per errore durante la creazione di una sessione.

## Annullare una sessione esistente

Gli Autori e gli Amministratori possono annullare una sessione e riprogrammarla, se necessario.

Quando una sessione viene annullata, il sistema invia un’e-mail con la notifica dell’annullamento della riunione a tutti gli Allievi e gli Istruttori iscritti. L’e-mail include i dettagli della sessione aggiornata.

Il modello **[!UICONTROL Annullamento della sessione]** ti aiuta ad annullare una sessione.

Sulla pagina **[!UICONTROL Istanza del corso]**, ogni sessione elencata in un’istanza di corso include un’opzione per annullare la sessione.

![](assets/cancel-session.png)

*Annullare una sessione esistente*

Cliccando sul link **[!UICONTROL Annulla sessione]**, visualizzerai un avviso.

Nella finestra di dialogo dell’avviso, cliccando sul pulsante **[!UICONTROL Procedi]**, il sistema annullerà la sessione.

Il sistema annulla anche i seguenti dettagli dopo l’annullamento di una sessione:

* Data di inizio della sessione
* Data finale della sessione
* Orario di inizio della sessione
* Orario finale della sessione
* Istruttori aggiunti alla sessione
* URL aula virtuale
* Posizione/luogo aggiunti alla sessione
* Limite della lista d’attesa aggiunto dall’istruttore
