---
description: Scopri come importare un File JSON di temi personalizzato in Composizione contenuti e come salvarlo come nuovo tema personalizzato disponibile nel pannello Temi del corso.
jcr-language: en_us
title: Importare un tema
product_v2:
  - id: ed12e5b7-96e3-45e7-a17f-de222065ebcb
    internal-label: Learning Manager
source-git-commit: c061ccbefe8d40154220587796062d335e35de77
workflow-type: tm+mt
source-wordcount: '209'
ht-degree: 0%
---

# Importare un tema

Importate un File JSON personalizzato per applicare le modifiche come nuovo tema in Composizione contenuto.

1. Seleziona **Temi** dalla barra degli strumenti.

2. Seleziona **Importa** dalle opzioni **Tema del corso**.
   ![](../assets/48_course_themes_import_button_updated.png)

3. Scegliete il File JSON personalizzato dal computer.

4. Seleziona **Salva come nuovo** per creare un nuovo tema personalizzato.

## Panoramica della struttura JSON del tema

Un File JSON tematico si articola in cinque aree principali:

| Sezione | Controlli |
|----------------------------------------------------------------------|-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Metadati (id, name, version, description, author, source, isDefault) | Identità del tema e informazioni di visualizzazione |
| foundation.palette | I 7 token di colore principali (primo piano, sfondo, accento, sfondoLeggero, secondario, textPrimary, textInverse) a cui si fa riferimento in tutto il tema tramite var(—tokenName) |
| foundation.fonts | Stack di font per intestazione e corpo |
| foundation.spacing e foundation.radius | Scala di spaziatura orizzontale/verticale e token di raggio angolo |
| elementi | Composizione tipografica e stile strutturale per ogni ruolo di testo (lessonTitle, topicTitle, blockHeading, subheading, question, caption, paragraph, buttonLabel) e ogni componente (paragraphBlock, imageBlock, videoBlock, imageGrid, accordion, carosello, flipCard, tabulazioni, timeline, assessment) |

Poiché la maggior parte dei valori fa riferimento ai token della tavolozza utilizzando var(—tokenName), l&#39;aggiornamento di un singolo token, ad esempio accent, comporta automaticamente la modifica in cascata di ogni elemento che vi fa riferimento. Non è necessario cercare singoli valori di colore.

