---
jcr-language: en_us
title: I collegamenti e-mail attivati da modelli modificati generano un errore in Learning Manager
description: I collegamenti e-mail attivati da modelli modificati generano un errore nell’Adobe Learning Manager
contentowner: nluke
preview: true
source-git-commit: 6abc118c6ad7e66e3ded5bd26b9167c3a0b99e4b
workflow-type: tm+mt
source-wordcount: '219'
ht-degree: 0%

---



# I collegamenti e-mail attivati da modelli modificati generano un errore in Learning Manager

## Problema

Si verifica un errore quando si fa clic su un collegamento per un’e-mail automatica, un’e-mail di benvenuto o un’e-mail di iscrizione.

**Errore**

HTTP Status 400 - Bad request

![](assets/email-404.png)

## Causa

Ciò si verifica in genere quando i modelli e-mail non sono personalizzati correttamente.

**Soluzione**

Per evitare errori relativi a collegamenti interrotti, che potrebbero verificarsi a causa della personalizzazione, segui i passaggi riportati di seguito:

1. Accedi come Amministratore.
1. Nel pannello a sinistra, fai clic su **[!UICONTROL Modelli e-mail]**.

1. Individuate il modello desiderato e fate clic su per modificarlo.

   Viene aperto il **Anteprima modello** finestra.

   ![](assets/email-template.png)

   Quando modifichi un modello e-mail, tieni presente quanto segue:

   * Ti consigliamo di modificare un modello e-mail dall’interfaccia di Learning Manager.
   * Copia e incolla il modello modificato su un file di Blocco note o Word per memorizzare una copia delle modifiche apportate.
   * Evitate di sostituire il testo dinamico evidenziato in blu all’interno del modello. Ad esempio, &quot;**NomeOrganizzazione**&quot;, &quot;**Allievo**&quot;, &quot;**fai clic qui**&quot;, &quot;**NomeCertificato**&quot;, e così via.

1. Fai clic **[!UICONTROL Salva]** per confermare le modifiche applicate al modello.
1. Attiva l’e-mail per verificare che i collegamenti funzionino come previsto.
1. Ripristina le impostazioni originali facendo clic sull’opzione **Ripristina originale** per il modello modificato.
