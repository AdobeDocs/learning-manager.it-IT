---
description: Carica documenti, policy o videoregistratori esistenti per consolidare l'intelligenza artificiale nei contenuti dell'organizzazione. Scegliete se limitare la generazione solo a quei file o consentire all'intelligenza artificiale di integrarsi con le sue conoscenze generali.
jcr-language: en_us
title: Gestire i file sorgente
source-git-commit: 9ef7ede817f226004430b4104ff78a2ebc45aec2
workflow-type: tm+mt
source-wordcount: '456'
ht-degree: 0%

---


# Gestire i file sorgente

**Gestire le origini** consente di controllare il contenuto utilizzato da Content Composer per generare il corso. Aggiungi i tuoi documenti a un corso, quindi scegli se limitare l&#39;IA solo a quel contenuto o consentire che integri il tuo materiale con le proprie conoscenze. Se non aggiungi documenti, Content Composer genera il corso utilizzando le conoscenze esistenti del modello di intelligenza artificiale.

## Generare un corso utilizzando il materiale di origine

1. Seleziona **Gestisci origini** o **Aggiungi file** nel pannello Chat o nella barra degli strumenti.
   ![](../assets/5_brief_manage_sources_prompt_updated.png)

2. Trascina un file nella finestra di dialogo o seleziona **+ Aggiungi file di origine** per sfogliarli. Puoi aggiungere più file sorgente.
   ![](../assets/6_manage_sources_no_files_added_updated.png)

3. Selezionare **Limita output al contenuto nei file**. In questo modo, Content Composer può utilizzare solo il contenuto sorgente per generare il corso. Se questa opzione non è selezionata, Content Composer utilizza anche il Web per creare un corso.
   ![](../assets/7_manage_sources_file_uploading_restrict_output_updated.png)

Formati supportati:

| **Formato** | **Dimensioni massime** |
|-------------------------|--------------|
| PDF | 100 MB |
| Markdown (.md) | 100 MB |
| PowerPoint (.ppt/.pptx) | 100 MB |
| MS Word (.doc/.docx) | 100 MB |
| File di testo (.txt) | 100 MB |

Seleziona **Continua** per generare la struttura del corso.

### Genera senza materiale di origine

Se non disponi di un file di origine come documento di riferimento, effettua le operazioni riportate di seguito per generare la struttura del corso.

1. Selezionare **Gestisci origini**. Si apre la finestra di dialogo **Gestisci origini**.

2. Seleziona **Non dispongo di materiale di origine: genera il corso senza file di origine** per consentire all&#39;IA di generare contenuti sulla base delle sue conoscenze generali. Quando questa opzione non è selezionata e i file vengono caricati, l&#39;intelligenza artificiale limita i contenuti generati solo ai documenti caricati.![](../assets/8_manage_sources_no_source_material_option_updated.png)

3. Seleziona **Continua** per generare la struttura del corso.

### Aggiornare un corso quando cambia il materiale sorgente

I documenti sorgente possono non essere più aggiornati dopo che un corso è già stato generato: una policy viene rivista, un SOP ottiene una nuova versione o un pitch deck viene aggiornato. Utilizza questo flusso di lavoro per riallineare il corso al materiale corrente.

1. Seleziona **Gestisci origini** dal pannello Chat o dalla barra degli strumenti per riaprire la finestra di dialogo.

2. Aggiungi i file nuovi o modificati utilizzando **+ Aggiungi file di origine**.

3. Rimuovete o sostituite i file obsoleti in modo che l&#39;elenco di origine rifletta solo il materiale corrente.

4. Seleziona Continua per salvare l’elenco dei file sorgente aggiornato.

5. Rigenera le lezioni interessate in Composizione contenuto, rivedi le modifiche, quindi ripubblica il corso. La ripubblicazione invia l&#39;aggiornamento a Adobe Learning Manager come nuova versione del modulo. Consulta Controllo delle versioni dei moduli in ALM.

### Conferma il caricamento del file

![](../assets/9_manage_sources_file_ingested_confirmation_updated.png)

Una volta allegato un file, l’icona del file nella barra degli strumenti mostra un numero di badge. L&#39;assistente conferma il caricamento e offre una scelta rapida **Genera struttura**. Selezionalo o seleziona **Genera struttura** nella barra degli strumenti superiore.
