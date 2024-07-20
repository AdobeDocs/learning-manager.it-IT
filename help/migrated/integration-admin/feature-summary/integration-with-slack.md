---
jcr-language: en_us
title: Integrazione Learning Manager con Slack
description: Integrazione Learning Manager con Slack
contentowner: dvenkate
source-git-commit: 864b1796f1ca99ae7b5643e8c58d1756ff2461a1
workflow-type: tm+mt
source-wordcount: '468'
ht-degree: 44%

---



# Integrazione Learning Manager con Slack

Abbiamo **rimosso** **Slack** come connettore in Learning Manager. Non sarà più possibile accedere al connettore di Slack.

Come utente Slack, puoi installare l’app Adobe Learning Manager dalla directory dell’app Slack nei team Slack ed esplorare il contenuto di Learning Manager direttamente da Slack. Puoi interagire con Primebot per cercare nuovi corsi, visualizzare i consigli e ricevere notifiche sulle scadenze imminenti in Learning Manager. Puoi anche iscriverti e passare direttamente all’apprendimento dall’interno di Slack.

L’app Learning Manager per lo Slack non è supportata in un’istanza Azure di Learning Manager.

## Installazione dell’app Adobe Learning Manager {#installingadobecaptivateprimeapp}

Come Allievo, puoi installare l’app CP Prime nel tuo account di Slack. Per installare l’app, apri la directory dell’app dal tuo account Slack e cerca Learning Manager. Scarica e installa l’app. Se l’app non è approvata nel tuo account, contatta l’Amministratore dell’integrazione per l’approvazione. Se è già stata approvata, potrai accedere.

## Come approvare l’accesso dell’Allievo se sei un Amministratore dell’integrazione {#approvinglearnersigninasanintegrationadmin}

In qualità di Amministratore dell’integrazione, segui questi passaggi per approvare l’autorizzazione di un Allievo a utilizzare l’applicazione Prime durante lo Slack.

1. Seleziona **[!UICONTROL Applicazioni]** dal riquadro sinistro e fai clic sulla scheda **[!UICONTROL App in primo piano]**.

   ![](assets/featuredapps.jpg)

1. Fai clic sul riquadro **[!UICONTROL Slack]**. Si aprirà la pagina di integrazione Slack. Fai clic su **[!UICONTROL Approva]** nell&#39;angolo in alto a destra per approvare l&#39;applicazione.

   ![](assets/approval.png)

1. Torna alla pagina **[!UICONTROL Applicazioni]**. Una volta approvato, lo Slack dovrebbe essere visualizzato nella scheda **[!UICONTROL App esterne]**.
1. Ora gli Allievi possono accedere al proprio account Prime utilizzando Slack.

## Funzionalità di Primebot {#primebotfunctionalities}

Ora puoi iniziare a interagire con Primebot. Di seguito vengono riportate le funzionalità del bot.

1 - Comando

&#42;/prime&#42; può essere utilizzato per singole domande mirate relative al tuo account Adobe Learning Manager.

I sottocomandi disponibili sono:

/prime find `<query>`: cerca corsi, certificazioni, ecc.

/prime recommend: mostra consigli

/prime deadlines: mostra scadenze passate e imminenti

/prime enrollments: mostra iscrizioni

/prime skills: mostra abilità

/prime notifications: mostra notifiche

/prime catalogs: mostra cataloghi

/prime invite: [Solo amministratore] invita gli utenti Slack nel team corrente a provare primebot

/prime profile: mostra profilo

/primo logout: esci dall’account Prime di questo team Slack

/prime help: mostra messaggio di aiuto

2 - Consigliato

Puoi provare una frase come `show my recommendations` per ottenere un elenco personalizzato di corsi, certificazioni e programmi di apprendimento consigliati dal tuo account Adobe Learning Manager.

3 - Ricerca

Puoi provare frasi come `search for machine learning` o `search for artificial intelligence`. Puoi specificare il tipo di oggetto di apprendimento utilizzando frasi come `search for machine learning certifications`, `search for artificial intelligence courses` o `search for adobe photoshop job aids`. Puoi anche eseguire ricerche in un catalogo utilizzando frasi come `search for machine learning in Lynda catalog`.

4 - Scadenze

Usa una frase come `show my deadlines` per ottenere un elenco di scadenze passate e imminenti dal tuo account Adobe Learning Manager. Puoi filtrare le scadenze passate o imminenti con frasi come `show my overdue deadlines` o `show my upcoming deadlines`.
