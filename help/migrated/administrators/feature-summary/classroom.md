---
jcr-language: en_us
title: Aggiungere aule
description: Gli amministratori possono ora creare una libreria di aule. Per ogni aula, gli amministratori possono configurare i metadati che includono nome della posizione, limite di partecipanti e informazioni aggiuntive come l’URL. Autori e gli Amministratori possono quindi utilizzare questi percorsi preconfigurati per configurare di eventi di formazione guidati da istruttori (moduli aula).
contentowner: saghosh
exl-id: 51a1e38f-d4e2-4c19-bbf7-6696505c0dfd
source-git-commit: b882c22da029cdc4c8bcc4ab1b6d861f06f83f0f
workflow-type: tm+mt
source-wordcount: '1240'
ht-degree: 77%

---

# Aula

## Panoramica

Gli amministratori possono ora creare una libreria di aule. Per ogni aula, gli amministratori possono configurare i metadati che includono nome della posizione, limite di partecipanti e informazioni aggiuntive come l’URL. Autori e gli Amministratori possono quindi utilizzare questi percorsi preconfigurati per configurare di eventi di formazione guidati da istruttori (moduli aula).

È possibile aggiungere un’aula nei due modi riportati di seguito.

## Aggiungere un’aula a partire dall’interfaccia utente

È possibile aggiungere un’aula utilizzando l’interfaccia utente:

1. Nell’app di amministrazione (l’interfaccia utente per i ruoli di amministratore), fai clic su **[!UICONTROL Impostazioni]** > **[!UICONTROL Aule]**.

1. Fai clic **[!UICONTROL Aggiungi]** > **[!UICONTROL Nuova posizione]**.

1. Nella finestra di dialogo **[!UICONTROL Aula]**, inserisci le informazioni seguenti:

   * Digita il **[!UICONTROL Nome ubicazione]**. Usa un nome unico. In caso contrario, ti verrà mostrato un messaggio di errore in Learning Manager.
   * Inserisci la descrizione dell’aula nel campo **[!UICONTROL Informazioni aula]**. Questo campo è facoltativo.
   * Inserisci l’**[!UICONTROL URL dell’aula]**. Gli Allievi possono visualizzare queste informazioni nei dettagli dell’aula. L’URL può anche essere una posizione su una mappa, se necessario. Questo campo è opzionale.
   * Digita e seleziona il **[!UICONTROL Area Ubicazione]**. Questo campo è facoltativo.
   * Inserisci il numero di posti disponibili nel campo **[!UICONTROL Limite partecipanti]**. Quest’informazione si riferisce al numero di posti a sedere disponibili nell’aula. Quando si crea l’evento di formazione vero e proprio, questo valore può essere modificato.

   ![](assets/add-classroom-location.png)

   *Aggiungere un’aula*

Dopo aver aggiunto la posizione, il **[!UICONTROL Impostazioni]** > **[!UICONTROL Aule]** nella pagina sono elencate le sale riunioni:

![](assets/list-meeting-rooms.png)

*Visualizza tutte le sale riunioni*

L’elenco contiene i seguenti campi:

**[!UICONTROL Nome ubicazione]** - Nome dell’aula.

**[!UICONTROL Sessioni future]** - Numero di eventi che si verificheranno nel percorso corrispondente. Fai clic sul numero per visualizzare i dettagli in una finestra di dialogo.

![](assets/sessions-list.png)

*Visualizza sessioni future*

Nella finestra di dialogo vengono visualizzati i dettagli di ogni sessione, come il nome, il nome del corso di formazione che include la sessione e il programma. L’ora visualizzata si adatta al fuso orario di sistema dell’Allievo.

La **[!UICONTROL Sessioni future]** visualizzazioni dei campi **zero** quando l’aula non viene utilizzata per alcuna sessione o quando è associata a sessioni passate.

**[!UICONTROL Posti limitati]** - Visualizza la capacità dell’aula.

**URL percorso** - URL fornito durante la creazione dell’aula.

**Informazioni sulla posizione** - Le informazioni sull’aula che hai fornito durante la creazione dell’aula.

## Aggiungere un’aula con CSV

In alternativa, puoi aggiungere una o più aule importando un file CSV contenente le informazioni dell’aula.

Ingresso **[!UICONTROL App per amministratori]** > **[!UICONTROL Impostazioni]** > **[!UICONTROL Aule]** > **[!UICONTROL Aggiungi]**, fare clic sul pulsante **[!UICONTROL Percorsi di importazione in blocco]** pulsante. Individua il percorso contenente il file CSV e selezionalo.

Il file CSV utilizza questi campi per memorizzare i dettagli relativi a una o più aule:

* name
* info
* url
* seatLimit

I titoli possono essere personalizzati.

Il file CSV deve contenere obbligatoriamente tutte le colonne nello stesso ordine specificato qui.

Dopo l’importazione del file CSV da parte del sistema, le aule vengono aggiunte alla libreria.

## Cercare le aule

Gli Autori e gli Amministratori possono iniziare a digitare il nome dell’aula, e vedranno apparire i risultati pertinenti. Dai risultati elencati è quindi possibile selezionare un’aula. Se non ci sono risultati, l’utente può comunque aggiungere il nome della nuova aula. Tieni presente che l’aula che crei in questo modo, usando il flusso di creazione di una sessione, non viene aggiunta alla libreria di aule creata dall’Amministratore.

Quando aggiungi un’aula, la piattaforma di apprendimento ti fa sapere anche se l’aula è già stata prenotata nella fascia oraria selezionata. Fornisce anche dei suggerimenti con fasce orarie alternative. In questo modo, se decide di utilizzare la stessa aula, l’Autore può modificare l’orario della riunione.

![](assets/classroom-search.png)

*Cercare le classi*

## Limitare l’elenco di possibili istruttori

Al momento, gli utenti possono aggiungere qualsiasi utente registrato nel campo “Istruttore” durante la creazione di un’aula o di una sessione in aula virtuale. Questo è possibile anche su questa versione.

Tuttavia, gli amministratori dispongono ora di un’opzione aggiuntiva per limitare il numero di utenti che possono essere inseriti come istruttori sulla piattaforma. In questo modo, è possibile evitare che vengano aggiunti nuovi istruttori per errore durante la creazione di una sessione.

## Amministratore

Un Amministratore può selezionare **[!UICONTROL Gestione Istruttori]** opzione (disponibile in **[!UICONTROL App per amministratori]** > **[!UICONTROL Impostazioni]** > **[!UICONTROL Generale]**) per garantire che solo gli utenti con una formazione di istruttore predefinita possano essere aggiunti come istruttori per una sessione.

Per configurare un Istruttore, l’Amministratore può selezionare **[!UICONTROL GESTISCI]** > **[!UICONTROL Utenti]** per aprire la pagina Gestione utenti, seleziona un utente e assegna il ruolo di istruttore (utilizzando **[!UICONTROL Azioni]** > **[!UICONTROL Assegna ruolo]**).

## Autore

Se l’amministratore seleziona l’opzione **[!UICONTROL Gestione Istruttori]**, l’autore può cercare e aggiungere solo utenti con il ruolo di istruttore alle sessioni in aula, in aula virtuale, agli elenchi di controllo e ai moduli che richiedono l’invio di materiali.

Inoltre, l’autore può:

* Aggiungere e rimuovere istruttori dalle sessioni esistenti.
* Aggiungere istruttori alle sessioni esistenti che dispongono già di uno o più istruttori.

Quindi, se l’opzione **[!UICONTROL Gestione Istruttori]** è stata abilitata dall’Amministratore, è possibile aggiungere come tali solo gli utenti con il ruolo Istruttore.

>[!NOTE]
>
>Questo non si applica alla migrazione delle sessioni tramite il file CSV. In questo caso, anche un utente che non dispone del ruolo di Istruttore può essere aggiunto come tale.

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

## Amministratore

Sulla pagina **[!UICONTROL Istanza del corso]** l’Amministratore può annullare una o più sessioni. Quando l’Amministratore annulla una sessione, il sistema cancella tutti i dettagli della sessione ad eccezione del limite di partecipanti.

Inoltre, un Amministratore può:

* Visualizzare gli allievi iscritti e gli allievi nella lista d’attesa di una sessione.
* Annullare l’iscrizione degli allievi a un corso con una o più sessioni annullate.
* Prendere le presenze per le sessioni annullate.
* Contrassegnare come completato un corso con una o più sessioni annullate.
* Riprogrammare una sessione annullata.
* Aggiungere un istruttore a una sessione annullata durante la sua riprogrammazione.

Tieni presente che anche dopo l’annullamento, gli Allievi iscritti all’istanza di formazione continuano a rimanere iscritti. Lo stato delle loro iscrizioni, incluse le iscrizioni confermate, in lista d’attesa e in attesa di approvazione del manager, non cambia. Questo è utile perché l’Amministratore può configurare e riprogrammare la sessione annullata in futuro.

## Autore

Sulla pagina **[!UICONTROL Istanza del corso]**, l’Autore può annullare una o più sessioni. Quando l’Autore annulla una sessione, il sistema cancella tutti i dettagli della sessione, ad eccezione del limite di partecipanti.

Pertanto, un Autore può utilizzare il **[!UICONTROL Annulla sessione]** collegamenti per annullare una o più sessioni in aula o in aula virtuale disponibili nella stessa istanza del corso o in istanze diverse.
