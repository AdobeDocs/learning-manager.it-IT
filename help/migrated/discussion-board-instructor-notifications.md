---
description: Scopri come Istruttori e Manager di coorte ricevono i digest tramite e-mail delle attività dell’area discussioni e come gestire le impostazioni e gli abbonati con le API
jcr-language: en_us
title: Notifiche Istruttore bacheca di discussione
exl-id: 370c9add-5572-4555-8a95-ddb470c230f4
source-git-commit: 650ec8159a4291189dfc38b03701b7b96932233d
workflow-type: tm+mt
source-wordcount: '1231'
ht-degree: 0%
---

# Notifiche Istruttore bacheca di discussione

## Panoramica

Le notifiche per gli Istruttori nelle bacheche di discussione offrono a Istruttori, Manager di coorte e Amministratori un riepilogo tramite e-mail delle attività recenti nelle bacheche che monitorano. Ciò è utile per gli Istruttori che gestiscono più coorti e prendono parte a più bacheche contemporaneamente.

Un Manager di coorte è la persona che gestisce un gruppo di Allievi (una coorte) che seguono un corso o un programma insieme in base alla stessa pianificazione.

Invece di aprire ogni bacheca singolarmente, gli Istruttori ricevono avvisi in-app in tempo reale e un digest e-mail, alla frequenza configurata, per le bacheche a cui sono iscritti. È possibile gestire le sottoscrizioni delle bacheche e le impostazioni di notifica tramite l&#39;API [`boardSubscriptionSettings`](api-changes-dec-2026.md#api-sequence) e l&#39;API [sottoscrittori](api-changes-dec-2026.md#api-get-subscribers).

## Funzionalità principali

* È possibile sottoscrivere utenti Adobe Learning Manager attivi a aree discussioni selezionate utilizzando l&#39;API sottoscrittori ([`POST /boards/{id}/subscribers`](api-changes-dec-2026.md#api-subscribe-users), ambito `admin:write`). Un utente deve avere accesso alla bacheca quando vengono inviate le notifiche.
* Gli utenti ricevono notifiche in-app in tempo reale per i tipi di evento abilitati e un riepilogo e-mail raggruppato per bacheca. I tipi di evento sono controllati dalle impostazioni a livello di account (`notifyNewPost`, `notifyComment` e `notifyReply`) nell&#39;API [`boardSubscriptionSettings`](api-changes-dec-2026.md#api-sequence).
* La finestra di riepilogo è il periodo di tempo in cui l’attività viene raccolta in un’e-mail di riepilogo. È possibile impostarlo a livello di account con l&#39;attributo `digestFrequencyHours`, da 1 a 168 ore (ad esempio, 24 ore per un digest giornaliero). Si applica a tutti gli utenti dell’account.
* Puoi sottoscrivere gli utenti in base all&#39;ID utente o all&#39;indirizzo e-mail e aggiungere diversi utenti in una richiesta ([sottoscrizioni in blocco](api-changes-dec-2026.md#bulk-subscriptions)). Gli utenti vengono prima creati in Learning Manager nel modo usuale.
* L’e-mail di riepilogo elenca ogni nuovo post, commento e risposta per i tipi di evento abilitati, con il nome della bacheca, il nome e l’indirizzo e-mail dell’autore e un collegamento diretto. Mostra anche il conteggio degli aggiornamenti dall’inizio del periodo di riepilogo.
* L&#39;API `boardSubscriptionSettings` e l&#39;API dei sottoscrittori sono API pubbliche, pertanto è possibile gestire impostazioni e sottoscrizioni senza un&#39;interfaccia utente (integrazioni basate su API).

## Casi d’uso

I seguenti casi d’uso mostrano come le notifiche per gli Istruttori aiutano:

| Caso di utilizzo | Informazioni sulla notifica |
|---|---|
| Monitorare più coorti | Un Istruttore responsabile di diverse coorti può ricevere un’attività riassuntiva dalle bacheche associate a tali coorti. |
| Verifica del coinvolgimento dell’Allievo | Un gestore di coorte può monitorare i nuovi contributi e identificare le discussioni attive senza controllare separatamente ogni bacheca. |
| Traccia conversazioni di follow-up | I commenti e le risposte inclusi nel riepilogo aiutano gli istruttori a identificare le discussioni che possono richiedere una guida o moderazione. |

## Considerazioni importanti

* Un utente deve essere in grado di accedere a una bacheca quando viene inviata una notifica. L&#39;accesso viene controllato di nuovo al momento della consegna, non solo quando l&#39;utente è iscritto. Se un abbonato perde l’accesso a una bacheca, l’abbonamento viene mantenuto ma le notifiche per quella bacheca vengono ignorate.
* Il digest viene inviato come un&#39;e-mail, quindi una bacheca occupata può renderlo molto lungo. Ad esempio, una coorte di circa 40 allievi potrebbe pubblicare diverse centinaia di commenti in sei ore.
* Se le bacheche sono molto attive, utilizza una frequenza di riepilogo più breve, ad esempio ogni sei ore, in modo che ogni e-mail rimanga gestibile. Impostare la frequenza con `digestFrequencyHours` nell&#39;API [`boardSubscriptionSettings`](api-changes-dec-2026.md#api-create-settings).
* Il numero di post nel riepilogo e-mail è limitato a 20 per bacheca per digest. Lo stesso massimale si applica indipendentemente alle osservazioni (20) e alle risposte (20) per bacheca. Solo gli elenchi visualizzati vengono troncati; i conteggi di titoli/sottotitoli riflettono sempre l&#39;attività vera e non troncata della finestra.
* Il numero di abbonati è limitato a 200 per bacheca.
* Poiché il contenuto viene inviato direttamente nell’e-mail anziché come allegato, anche il corpo dell’e-mail ha un limite di dimensione.

## Modello di abbonamento, autorizzazioni e idoneità

* Un abbonato è un utente che riceve notifiche da una bacheca. Un abbonamento a una bacheca è indipendente dalla relazione di follow-up esistente con l’utente della bacheca.
* Chiunque esegua l’autenticazione con OAuth e disponga degli ambiti `admin:read` e `admin:write` può utilizzare le impostazioni di sottoscrizione e le API dei sottoscrittori. `admin:read` consente di elencare i sottoscrittori e di leggere le impostazioni. `admin:write` consente di aggiungere o rimuovere sottoscrittori e modificare le impostazioni.
* Puoi iscriverti a qualsiasi utente Learning Manager, ma l’utente deve esistere, essere attivo e disporre dell’accesso alla bacheca per ricevere notifiche. L&#39;accesso viene ricontrollato all&#39;invio di notifiche e digest.
* Se un utente perde l&#39;accesso, la consegna viene ignorata per quella bacheca e l&#39;abbonamento viene mantenuto. Se l&#39;accesso viene restituito, il recapito viene ripreso.
* Puoi aggiungere più utenti a una bacheca in una richiesta (abbonamenti in blocco). Se un utente è già iscritto, la richiesta riesce comunque e non viene creato alcun duplicato. Per il formato della richiesta, la risposta 207 con più stati e i casi di errore, vedere [Sottoscrizioni in blocco](api-changes-dec-2026.md#bulk-subscriptions).

## Contenuto digest

### Eventi inclusi

Il digest include nuovi post, commenti e risposte quando l&#39;impostazione corrispondente è `true` nell&#39;API [`boardSubscriptionSettings`](api-changes-dec-2026.md#api-create-settings): `notifyNewPost`, `notifyComment` e `notifyReply`. Impostali con `POST` o `PATCH /boardSubscriptionSettings`. Per impostazione predefinita, tutte le impostazioni sono `false`.

### Eventi esclusi

Il digest esclude gli eventi la cui impostazione corrispondente nell&#39;API [&#128279;](api-changes-dec-2026.md#api-create-settings) di `boardSubscriptionSettings` (ad esempio `notifyComment`) è `false`. Non viene inviato alcun digest quando non è presente alcuna attività idonea.

### Esempio di layout e-mail di riepilogo

Viene inviato un messaggio e-mail di riepilogo per ogni bacheca sottoscritta che aveva attività idonee. Esso è strutturato come segue:

* **Riga di riepilogo:** l&#39;e-mail si apre con il numero totale di aggiornamenti nella bacheca (ad esempio, sette aggiornamenti) e una suddivisione per tipo (ad esempio, nuovi post e commenti), insieme all&#39;ora a partire dalla quale viene conteggiata l&#39;attività.
* **Sezione della bacheca:** L&#39;attività è raggruppata sotto il nome della bacheca. Ogni post è elencato sotto di esso.
* **Dettagli elemento:** Ogni post, commento o risposta mostra il nome e l&#39;indirizzo e-mail dell&#39;utente che lo ha creato, oltre a un collegamento all&#39;elemento.
* **Collegamenti:** selezionando un collegamento si apre direttamente il post, il commento o la risposta. Per aprire il collegamento, il destinatario deve aver effettuato l’accesso.
* **Commenti e risposte:** questi vengono visualizzati nello stesso messaggio e-mail dei post, in modo che gli istruttori possano visualizzare le conversazioni di follow-up e i nuovi argomenti.

## Configurare le notifiche

### Configurare le impostazioni utilizzando le API

Le notifiche vengono gestite tramite due API pubbliche: l&#39;API [`boardSubscriptionSettings`](api-changes-dec-2026.md#api-sequence), che si applica a livello di account, e l&#39;API [per abbonati](api-changes-dec-2026.md#api-get-subscribers), che si applica per bacheca. Entrambi utilizzano gli ambiti OAuth `admin:read` e `admin:write`. Chiamali in questa sequenza:

1. Impostare le impostazioni a livello di account con [`POST /boardSubscriptionSettings`](api-changes-dec-2026.md#api-create-settings).
1. Modificare le impostazioni in seguito, se necessario, con [`PATCH /boardSubscriptionSettings`](api-changes-dec-2026.md#api-update-settings).
1. Recupera le impostazioni a livello di account con [`GET /boardSubscriptionSettings`](api-changes-dec-2026.md#api-get-settings).
1. Elenca gli utenti iscritti a una bacheca con [`GET /boards/{id}/subscribers`](api-changes-dec-2026.md#api-get-subscribers).
1. Abbonare gli utenti a una bacheca con [`POST /boards/{id}/subscribers`](api-changes-dec-2026.md#api-subscribe-users).
1. Annulla l&#39;iscrizione di un utente a una bacheca con [`DELETE /boards/{id}/subscribers/{userId}`](api-changes-dec-2026.md#api-unsubscribe-user).

Utilizza l&#39;API `boardSubscriptionSettings` per impostare la frequenza di digest in ore e per attivare o disattivare post, commenti e risposte per il digest. Ad esempio, un account con una frequenza di riepilogo di 1 ora riceve un&#39;e-mail di riepilogo ogni ora. Per impostazione predefinita, tutte le impostazioni degli eventi sono `false`.

### Gestione abbonati

Utilizza l’API per abbonati per scegliere a quali bacheche sono iscritti gli utenti attivi di Learning Manager. Un abbonamento è separato dalla relazione di follow della bacheca esistente. Un utente deve avere visibilità su una bacheca per ricevere le sue notifiche, il che significa che l&#39;utente deve essere registrato. La perdita di visibilità elimina il recapito ma non rimuove l’abbonamento.

### Attivare la funzione

Per abilitare le notifiche degli istruttori, crea le impostazioni a livello di account e quindi iscrivi gli utenti alle bacheche, come descritto in [Modifiche API in Nov 2026](api-changes-dec-2026.md). Successivamente, il sistema raccoglie nuovi post, commenti e risposte creati durante l&#39;intervallo configurato. Alla fine dell&#39;intervallo, gli abbonati ricevono una notifica riassuntiva che copre l&#39;attività ammissibile nelle bacheche sottoscritte.

Ulteriori informazioni sulle modifiche delle API in [Modifiche delle API in dicembre 2026](api-changes-dec-2026.md).
