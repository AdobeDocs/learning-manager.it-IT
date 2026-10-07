---
jcr-language: en_us
title: Modello CSS per Editor di testo RTF
description: Modello CSS per Editor di testo RTF
contentowner: saghosh
preview: true
product_v2:
  - id: ed12e5b7-96e3-45e7-a17f-de222065ebcb
    internal-label: Learning Manager
source-git-commit: c061ccbefe8d40154220587796062d335e35de77
workflow-type: tm+mt
source-wordcount: '231'
ht-degree: 72%
---


# Modello CSS per Editor di testo RTF

## Perché è necessario CSS?

Il testo RTF è composto da markup HTML. Senza CSS, il rendering del markup causerebbe l’applicazione di uno stile predefinito da parte del browser. Questo spesso non è adatto alle linee guida di stile dell’azienda. Per rispettare le linee guida è necessario un CSS.

## Stile predefinito

Il foglio di stile CSS allegato contiene lo stile applicato da Learning Manager. Lo stile è adattato in base alla maggioranza dei casi d’uso. Scarica il file CSS allegato e importalo nell’app web in base alle tue convenzioni e al tuo sistema di compilazione. Le classi CSS definite utilizzano lo spazio dei nomi ql-editor e non interferiscono con i tuoi stili esistenti.

## Personalizzare gli stili

Lo stile predefinito potrebbe non soddisfare le esigenze di tutti. Le personalizzazioni possono essere eseguite sovrascrivendo il CSS fornito. Tutti i parametri di stile sono contenuti all’interno di ql-editor come selettori di discendenti. Vengono utilizzate le seguenti classi:

* **Rientro**: li.ql-indent-$number. $number varia da 1 a 9
* **dimensioni**: ql-size-small, ql-size-large, ql-size-large
* **alignment**: ql-align-center, ql-align-justify, ql-align-right
* **colore**: ql-color-$color. $color = white, red, orange, yellow, green, blue, purple
* **sfondo**: ql-bg-$color. $color = black, red, orange, yellow, green, blue, purple
* **tag html**: p, ol, ul, pre, blockquote, h1, h2, h3, h4, h5, h6

[File CSS da utilizzare per la personalizzazione.](assets/ql-headless.css)
