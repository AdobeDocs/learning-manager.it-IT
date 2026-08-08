---
description: Scopri come importare un file JSON con tema personalizzato in Composizione contenuti e come salvarlo come nuovo tema personalizzato disponibile nel pannello Temi del corso.
jcr-language: en_us
title: Importare un tema
source-git-commit: f8687710f5b73e8b7cf8d56057cac25483f38cdc
workflow-type: tm+mt
source-wordcount: '209'
ht-degree: 0%

---


# Importare un tema

Importa un file JSON personalizzato per applicare le modifiche come nuovo tema in Composizione contenuti.

1. Seleziona **Temi** dalla barra degli strumenti.

2. Seleziona **Importa** dalle opzioni **Tema del corso**.
   ![](../assets/48_course_themes_import_button_updated.png)

3. Scegli il file JSON personalizzato dal tuo computer.

4. Seleziona **Salva come nuovo** per creare un nuovo tema personalizzato.

## Panoramica della struttura JSON del tema

Un file JSON tema ha cinque aree principali:

| Sezione | Controlli |
|----------------------------------------------------------------------|-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Metadati (id, name, version, description, author, source, isDefault) | Identità del tema e informazioni di visualizzazione |
| foundation.palette | I 7 token di colore principali (primo piano, sfondo, accento, sfondoLeggero, secondario, textPrimary, textInverse) a cui si fa riferimento in tutto il tema tramite var(—tokenName) |
| foundation.fonts | Stack di font per intestazione e corpo |
| foundation.spacing e foundation.radius | Scala di spaziatura orizzontale/verticale e token di raggio angolo |
| elementi | Composizione tipografica e stile strutturale per ogni ruolo di testo (lessonTitle, topicTitle, blockHeading, subheading, question, caption, paragraph, buttonLabel) e ogni componente (paragraphBlock, imageBlock, videoBlock, imageGrid, accordion, carosello, flipCard, tabulazioni, timeline, assessment) |

Poiché la maggior parte dei valori fa riferimento ai token della tavolozza utilizzando var(—tokenName), l&#39;aggiornamento di un singolo token, ad esempio accent, comporta automaticamente la modifica in cascata di ogni elemento che vi fa riferimento. Non è necessario cercare singoli valori di colore.

