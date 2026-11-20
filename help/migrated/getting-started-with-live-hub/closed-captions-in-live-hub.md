---
title: Sottotitoli codificati nelle sessioni Live Hub
description: Scopri come i sottotitoli codificati visualizzano il contenuto vocale in tempo reale, in modo che Istruttori e Allievi possano seguire durante le sessioni dell’Hub dal vivo.
product_v2:
  - id: ed12e5b7-96e3-45e7-a17f-de222065ebcb
    internal-label: Learning Manager
source-git-commit: 574ba5fd9ac9dc02130a39006574c9ca1ce6c1d1
workflow-type: tm+mt
source-wordcount: '384'
ht-degree: 4%
---

# Comprendere i sottotitoli codificati

I sottotitoli codificati vengono generati automaticamente durante una sessione dell’Hub dal vivo e vengono aggiornati continuamente man mano che i partecipanti parlano. I sottotitoli vengono visualizzati in un&#39;area di visualizzazione dedicata e nella lingua selezionata dall&#39;Istruttore nelle **Impostazioni sala**.

Sia gli Istruttori che i partecipanti possono visualizzare i sottotitoli. Ogni partecipante può mostrare o nascondere i sottotitoli in modo indipendente, senza influire sulle impostazioni dei sottotitoli degli altri partecipanti.

Solo gli Istruttori possono modificare la lingua dei sottotitoli. I partecipanti possono visualizzare i sottotitoli solo nella lingua scelta dagli istruttori. I partecipanti non possono modificare la lingua dei sottotitoli.

## Come Live Hub determina la lingua dei sottotitoli

Live Hub seleziona automaticamente la lingua dei sottotitoli in base al seguente ordine di priorità:

1. **Lingua del corso:** l&#39;hub live utilizza la lingua del corso se è supportata per i sottotitoli. Per un corso multilingue, se l’istanza del corso corrente utilizza una lingua che non supporta i sottotitoli codificati, l’Hub live seleziona la lingua della prima istanza del corso che supporta i sottotitoli codificati. Per ulteriori informazioni, visualizzare [Lingue supportate in ALM](../../migrated/languages-supported.md).
1. **Lingua account:** Se la lingua del corso non è supportata, Live Hub controlla la lingua dell&#39;account e la utilizza se supportata.

>[!NOTE]
>
>Se non è supportata né la lingua del corso né la lingua dell’account, Live Hub seleziona Inglese come lingua dei sottotitoli. Inoltre, i sottotitoli vengono disattivati per impostazione predefinita e devono essere attivati manualmente.

## Lingue supportate per i sottotitoli codificati

Live Hub supporta i sottotitoli codificati nelle seguenti lingue:

* Inglese
* Francese
* Tedesco
* Cinese
* Spagnolo
* Italiano
* Giapponese
* Portoghese
* Danese
* Olandese
* Finlandese
* Turco
* Coreano
* Norvegese
* Svedese
* Russo

## Come funzionano i sottotitoli codificati

In una sessione Hub dal vivo, i sottotitoli codificati vengono generati automaticamente. I sottotitoli vengono visualizzati in un pannello dedicato e aggiornati continuamente man mano che i partecipanti parlano. Sia gli Istruttori che gli Allievi possono visualizzare i sottotitoli.

Ogni partecipante può mostrare o nascondere i sottotitoli a seconda delle proprie preferenze. La modifica di questa impostazione non influisce sugli altri partecipanti.

![](assets/closed-captions-overview.png)
*Interfaccia Hub dal vivo che mostra i sottotitoli codificati nella sessione*

## Ruoli e autorizzazioni

La funzione **sottotitoli codificati** è disponibile sia per gli Istruttori che per gli Allievi in una sessione di Hub dal vivo. Le azioni disponibili variano in base al ruolo utente.

| **Istruttori** | **Allievi** |
|---|---|
| [Visualizza sottotitoli codificati](../getting-started-with-live-hub/manage-closed-captions-as-an-instructor.md#display-closed-captions) | [Visualizza sottotitoli codificati](../getting-started-with-live-hub/manage-closed-captions-as-a-learner.md#display-closed-captions) |
| [Modificare l&#39;aspetto dei sottotitoli codificati](../getting-started-with-live-hub/manage-closed-captions-as-an-instructor.md#change-the-appearance-of-closed-captions) | [Modificare l&#39;aspetto dei sottotitoli codificati](../getting-started-with-live-hub/manage-closed-captions-as-a-learner.md#change-the-appearance-of-closed-captions) |
| [Seleziona lingua sottotitoli](../getting-started-with-live-hub/manage-closed-captions-as-an-instructor.md#select-the-caption-language) | |