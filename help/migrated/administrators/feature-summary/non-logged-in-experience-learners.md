---
title: Esperienza senza accesso per gli Allievi
description: Il portale nativo di Adobe Learning Manager supporterà la modalità di accesso al sito di formazione senza necessità di effettuare l’accesso. Abilitando questa modalità, gli Allievi possono scoprire e accedere al sito di formazione e consultare i vari corsi e contenuti disponibili. L’esperienza senza accesso consente agli Allievi di esplorare i corsi senza accedere a un portale.
exl-id: 12260cca-d2d2-4e7c-991d-9b09690d4c0a
source-git-commit: 70d516a262180fd5a2a9390c9813058f0fa5e1c9
workflow-type: tm+mt
source-wordcount: '601'
ht-degree: 40%

---

# Esperienza senza accesso per gli Allievi

Il portale nativo di Adobe Learning Manager supporterà la modalità di accesso al sito di formazione senza necessità di effettuare l’accesso. Abilitando questa modalità, gli Allievi possono scoprire e accedere al sito di formazione e consultare i vari corsi e contenuti disponibili.

L’esperienza senza accesso consente agli Allievi di esplorare i corsi senza accedere a un portale.

Affinché la pagina principale senza accesso sia abilitata, l’Amministratore dell’integrazione deve abilitare e configurare il [Connettore dati di formazione](/help/migrated/integration-admin/feature-summary/connectors.md#training-data-access).

Il corso di formazione può quindi essere esportato dal connettore.

>[!NOTE]
>
>Assicurati che l’opzione Learning Manager nativo sia selezionata.

L’Amministratore può modificare e configurare la pagina principale, che è destinata agli utenti che non effettuano l’accesso.

## API Allievo

Adobe Learning Manager: le API degli Allievi consentono di creare un’esperienza di apprendimento personalizzata per gli utenti. L’utilizzo di queste API richiede un token utente valido e deve essere utilizzato solo per lo scopo dei flussi di lavoro in cui è presente un Allievo con licenza o registrazione completa.

>[!IMPORTANT]
>
>Non devono essere utilizzati, così come sono, per qualsiasi tipo di recupero di dati per supportare qualsiasi utente non registrato/utenti condivisi o qualsiasi altro caso simile. Per creare un’esperienza headless o basata su AEM senza accesso, contattaci. Suggeriremo l&#39;approccio giusto in base alle vostre esigenze.

I casi d’uso senza registrazione richiedono una gestione speciale.

**Rivolgersi al team dell&#39;architettura della soluzione per eventuali domande sull&#39;utilizzo appropriato di queste API e verificare che un architetto della soluzione abbia verificato una soluzione prima di distribuirla**.

## Avvia le opzioni della pagina principale

Nella pagina principale di Adobe Learning Manager, seleziona **Branding**. Quindi, nel riquadro a sinistra, seleziona Pagina principale senza accesso.

![opzioni della pagina principale](assets/non-logged-in-homepage.png)

*Seleziona la pagina principale senza accesso*

## Aggiungi un banner

Aggiungi un banner per qualsiasi annuncio di marketing o presenta l’argomento di tendenza del giorno. Seleziona **Aggiungi banner**.

![banner](assets/add-banner-image.png)

*Aggiungi un banner*

Individua la posizione dell’immagine da utilizzare come banner. Fornisci quindi un collegamento come pulsante di azione sull’immagine del banner.

## Aggiungi categorie

Questo componente può essere utilizzato per filtrare il catalogo in base a tag, abilità e catalogo. Questa sezione contiene un’intestazione e una descrizione per ciascuna categoria. Facendo clic, l’utente viene reindirizzato alla pagina del catalogo con i filtri applicati.

Selezionare **[!UICONTROL Aggiungi categoria]**. Quindi inserisci i dettagli per la categoria.

![aggiungi categoria](assets/add-category.png)

*Aggiungere le categorie*

Salva la categoria. La categoria viene aggiunta alla sezione.

## Aggiungi un catalogo

Aggiungi un catalogo per gli utenti che non hanno effettuato l’accesso in modo che possano sfogliare tutti i corsi di formazione sulla piattaforma.

![aggiungi catalogo](assets/add-catalog.png)

*Aggiungere un catalogo*

Saranno presenti tutti i corsi di formazione esportati.

## Funzioni non supportate

* Le risorse formative non verranno esportate. Tuttavia, gli Allievi possono visualizzarle dopo l’accesso.
* Ordina per nel componente del catalogo.
* Impostazione di visualizzazione predefinita utilizzata nell’app di amministrazione (Impostazioni > Generale > Visualizzazione elenco).
* Valutazione a stelle/efficacia.
* Impostazione dell’icona della scheda.
* Impostazioni di abilità e tag pertinenti.
* Vista dell’app dell’Allievo visualizzata a livello di catalogo.
* Pagine della panoramica del corso di formazione - Facendo clic sulla scheda si verrà reindirizzati a Registrazione, quindi alla pagina della panoramica del corso di formazione/pagina dell’istanza.
* Saranno presenti tutti i cataloghi abilitati. Gli Allievi che non hanno accesso a un catalogo non possono visualizzare il catalogo e i corsi di formazione in esso contenuti dopo l’accesso.
* Per l’opzione nativa, le modifiche a un corso o a un percorso di apprendimento verranno applicate dopo 24 ore, non in tempo reale.
