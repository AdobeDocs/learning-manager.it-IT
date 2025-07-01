---
title: Prossime modifiche in Adobe Learning Manager
description: Scopri le nuove funzioni, i miglioramenti e gli aggiornamenti importanti in arrivo per Adobe Learning Manager. Ricevi informazioni sulle novità per pianificare in anticipo e sfruttare al meglio le ultime novità.
source-git-commit: 97c52c188612b7ad7233a13bd90bcb174fdc60bc
workflow-type: tm+mt
source-wordcount: '652'
ht-degree: 2%

---


# Prossime modifiche in Adobe Learning Manager

Siamo entusiasti di condividere diversi importanti aggiornamenti in arrivo su Adobe Learning Manager con le prossime versioni. Questi miglioramenti mirano a semplificare i flussi di lavoro dell’amministratore, migliorare l’accuratezza del reporting dei dati e rafforzare i controlli basati sui ruoli.

Queste modifiche sono progettate per ridurre le operazioni manuali, supportare l&#39;automazione e migliorare la governance nelle operazioni di formazione.

## Acquisire i completamenti contrassegnati come istruttore in Trascrizione Allievo (M44)

### Pubblico

Amministratori e proprietari dell&#39;automazione

### Panoramica

In Adobe Learning Manager, quando si utilizzano le Trascrizioni Allievi incrementali (LT) per i flussi di lavoro di automazione, i completamenti contrassegnati da istruttore effettuati dopo la data della sessione non vengono acquisiti. La marca temporale di completamento riflette l’ora di fine sessione originale (non l’ora in cui l’istruttore ha contrassegnato il completamento). Poiché questi aggiornamenti non rientrano nella finestra di modifica di un giorno utilizzata per la generazione LT incrementale, di conseguenza, i dati di partecipazione e completamento degli Allievi vengono esclusi dai report, causando report a valle inaccurati o incompleti e potenziali carenze di conformità.

### Cosa è cambiato

I report Trascrizione Allievo (LT) includono i completamenti contrassegnati dagli istruttori dopo la data della sessione. In questo modo, ogni indicazione di partecipazione ritardata viene riportata correttamente nell’esportazione della trascrizione.

Gli stati di partecipazione come &quot;Partecipato con esito positivo/negativo&quot; verranno visualizzati automaticamente nelle esportazioni LT incrementali.

### Novità

* Nuova colonna: Contrassegna data completamento (fuso orario UTC).
* L’origine del completamento è disponibile a livello di modulo.
* Compatibile con report LT basati su connettore o generati da API per processi.

![](assets/capture-instructor.png)

**Azione richiesta**

* Se l&#39;automazione dipende dalle posizioni delle colonne, assicurati che i conti logici per la nuova colonna siano corretti.
* Se si utilizzano i nomi di colonna, non è necessario apportare modifiche.
* Non sono inclusi i completamenti modificati (importazioni manuali).

## Download dei collegamenti nel rapporto Risorse formative (M44)

### Pubblico

Amministratore, amministratore personalizzato e proprietari dell&#39;automazione

### Panoramica

Il report Risorse formative include un collegamento di download diretto per ciascuna risorsa formativa, che consente di accedervi rapidamente dal report stesso.

### Novità

Alla terza posizione del report è stata aggiunta una nuova colonna, **[!UICONTROL Collegamento risorsa formativa]**. Si collega direttamente alla risorsa formativa se si tratta di un file o mostra l’URL esterno fornito dall’autore.

Gli utenti con accesso (amministratore/autori e ruoli personalizzati) possono scaricare la risorsa formativa utilizzando questo collegamento.

![](assets/download-links-for-job-aid.png)

### Azione richiesta

* Verifica dei flussi di lavoro automatizzati mediante i report Risorse formative (mediante l’API dei processi).
* Se lo script è basato sulla posizione della colonna, aggiornare gli script di conseguenza.
* Non è necessaria alcuna azione se si utilizzano i nomi di colonna.

## Colonne ID utente interno ed e-mail del Manager aggiunte al Report utente (M44)

### Pubblico

Amministratori (e amministratori personalizzati) che utilizzano il **[!UICONTROL Report utente]** (**[!UICONTROL Amministratore]** > **[!UICONTROL Utenti]** > **[!UICONTROL Interno]** > **[!UICONTROL Esporta dati utente]**) scaricato dall&#39;interfaccia utente dell&#39;amministratore.

### Panoramica

Per semplificare i flussi di lavoro di identificazione e integrazione degli utenti, nel report utente esportato tramite l’interfaccia utente sono state aggiunte due colonne, **[!UICONTROL ID utente interno]** e **[!UICONTROL E-mail manager]**.

### Novità

Il report Utente include l’ID utente interno di un utente e l’indirizzo e-mail del manager, per mapparli in modo univoco su diversi strumenti o endpoint API.

### Azione richiesta

* Se utilizzi questo report in flussi automatizzati, questa colonna appena aggiunta deve essere gestita in automazione.
* Se i flussi di lavoro non sono interessati, non sono necessarie modifiche.

## Autorizzazioni di annuncio con ambito per amministratori personalizzati (M44)

### Pubblico

Amministratori personalizzati

### Panoramica

Gli amministratori personalizzati possono creare annunci solo per i gruppi di utenti o i cataloghi che rientrano nel loro ambito definito.

### Novità

* Le regole di ambito consentono agli amministratori personalizzati di creare annunci solo per gruppi di utenti o cataloghi specifici.
* Durante la definizione di un ruolo personalizzato, gli amministratori possono assegnare autorizzazioni di annuncio con ambito a gruppi di utenti o cataloghi.
* Gli amministratori personalizzati si limitano a creare annunci all’interno dell’ambito specificato.
* Il report dell’annuncio di notifica per gli amministratori personalizzati mostrerà gli Allievi solo nell’ambito assegnato.

### Azione richiesta

* Il formato del rapporto rimarrà invariato. Se gli amministratori personalizzati scaricano il report dall’interfaccia utente, il contenuto del report sarà soggetto al relativo ambito.
* Non sono necessarie modifiche se questo report non viene utilizzato in alcun flusso di lavoro automatico o a valle.
