---
jcr-language: en_us
title: Integrazione Learning Manager con Slack
description: Integrazione Learning Manager con Slack
contentowner: dvenkate
source-git-commit: 864b1796f1ca99ae7b5643e8c58d1756ff2461a1
workflow-type: tm+mt
source-wordcount: '468'
ht-degree: 0%

---



# Integrazione Learning Manager con Slack

Abbiamo **rimosso** **Slack** come connettore in Learning Manager. Non sarà più possibile accedere al connettore di Slack.

Come utente di Slack, puoi installare l’app di Adobe Learning Manager dalla directory dell’app di Slack nei team di Slack ed esplorare il contenuto di Learning Manager da destra all’interno dello Slack. Puoi interagire con Primebot per cercare nuovi corsi, visualizzare i consigli e ricevere notifiche sulle scadenze imminenti in Learning Manager. Puoi anche iscriverti e passare direttamente all’apprendimento dall’interno di Slack.

L’app Learning Manager per lo Slack non è supportata in un’istanza Azure di Learning Manager.

## Installazione dell’app Adobe Learning Manager {#installingadobecaptivateprimeapp}

Come Allievo, puoi installare l’app CP Prime nel tuo account di Slack. Per installare l’app, apri la directory dell’app dal tuo account di Slack e cerca Learning Manager. Scarica e installa l’app. Se l’app non è approvata nel tuo account, contatta l’Amministratore dell’integrazione per l’approvazione. Se è già stato approvato, potrai accedere.

## Approvazione dell’accesso dell’Allievo come Amministratore dell’integrazione {#approvinglearnersigninasanintegrationadmin}

In qualità di Amministratore dell’integrazione, segui questi passaggi per approvare l’autorizzazione di un Allievo a utilizzare l’applicazione Prime durante lo Slack.

1. Seleziona **[!UICONTROL Applicazioni]** dal riquadro sinistro e fare clic sul pulsante **[!UICONTROL App in primo piano]** scheda.

   ![](assets/featuredapps.jpg)

1. Fare clic sul pulsante **[!UICONTROL Slack]** riquadro > viene visualizzata la pagina di integrazione slack. Fai clic **[!UICONTROL Approva]** nell’angolo in alto a destra per approvare l’applicazione.

   ![](assets/approval.png)

1. Torna al **[!UICONTROL Applicazioni]** pagina. Una volta approvato, lo Slack deve apparire nel **[!UICONTROL App esterne]** scheda.
1. Gli Allievi ora possono accedere al proprio account Prime utilizzando Slack.

## Funzionalità Primebot {#primebotfunctionalities}

Ora puoi iniziare a interagire con Primebot. Di seguito sono riportate le funzionalità del bot.

1 - Comando

&#42;/prime&#42; Può essere utilizzato per singole domande mirate relative all’account Learning Manager di Adobe.

I sottocomandi disponibili sono:

/prime find `<query>` - ricerca di corsi, certificazioni, ecc.

/prime recommend: mostra consigli

/prime deadlines: mostra scadenze passate e imminenti

/prime enrollments: mostra iscrizioni

/prime skills: mostra abilità

/prime notifications: mostra notifiche

/prime catalogs: mostra cataloghi

/prime invite: [Solo amministratore] invita gli utenti dello Slack nel team corrente a provare primebot

/prime profile: mostra profilo

/prime logout: esci dall’account Prime in questo team di Slack

/prime help: mostra messaggio della Guida

2 - Consigliato

Puoi provare una frase come `show my recommendations` per ottenere un elenco personalizzato di corsi, certificazioni e programmi di apprendimento consigliati dal tuo account Adobe Learning Manager.

3 - Ricerca

Puoi provare frasi come `search for machine learning` oppure `search for artificial intelligence`. Puoi specificare il tipo di oggetto di apprendimento utilizzando frasi come `search for machine learning certifications`, `search for artificial intelligence courses` oppure `search for adobe photoshop job aids`. Puoi anche eseguire ricerche all’interno di un catalogo utilizzando frasi come `search for machine learning in Lynda catalog`.

4 - Scadenze

Usare una frase come `show my deadlines` per ottenere un elenco di scadenze passate e imminenti dal tuo account Adobe Learning Manager. Puoi filtrare le scadenze passate o imminenti con frasi come `show my overdue deadlines` oppure `show my upcoming deadlines`.
