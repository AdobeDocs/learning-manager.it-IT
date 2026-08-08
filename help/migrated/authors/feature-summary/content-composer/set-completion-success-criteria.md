---
description: Scoprite la differenza tra i criteri di completamento e i criteri di successo in Composizione contenuti, come configurarli ciascuno e perché la distinzione è importante per il tracciamento e il reporting accurati degli Allievi in Adobe Learning Manager.
jcr-language: en_us
title: Impostare i criteri di completamento e di successo
source-git-commit: f8687710f5b73e8b7cf8d56057cac25483f38cdc
workflow-type: tm+mt
source-wordcount: '547'
ht-degree: 0%

---


# Imposta criteri di completamento e successo

## Criteri di completamento

**Criteri di completamento**: seleziona il menu a discesa e scegli quando il corso verrà contrassegnato per essere completato.

- **Avvia:** contrassegna il corso come completato non appena un Allievo lo apre, indipendentemente dalla quantità visualizzata.
  ![](../assets/21_completion_criteria_dropdown_launch_minview_quiz_updated.png)

- **Visualizzazione minima %:** contrassegna il corso come completato quando un Allievo visualizza la percentuale specificata del contenuto del corso.
  ![](../assets/22_completion_criteria_minview_percent_field_updated.png)

- **Quiz: contrassegna il corso come completato in base all’attività quiz dell’Allievo. Seleziona una condizione del quiz:**

  - **Al tentativo:** contrassegna il completamento non appena l’Allievo tenta di rispondere al quiz, indipendentemente dal risultato.

  - **Al passaggio:** contrassegna il completamento solo quando l’Allievo supera il quiz.

  - **Al superamento o al raggiungimento del limite:** contrassegni completati quando l’Allievo supera o raggiunge il numero massimo di tentativi consentiti, a seconda di quale evento si verifica per primo.
    ![](../assets/23_completion_criteria_quiz_condition_dropdown_updated.png)

## Criteri di successo

**I criteri di successo** determinano se un Allievo ha superato o meno il corso. A differenza dei criteri di completamento, i criteri di successo sono basati sul punteggio.

>[!NOTE]
>
>Le opzioni disponibili dipendono dalla versione SCORM selezionata in **Impostazioni di esportazione**. Se si seleziona **SCORM 1.2**, i criteri di completamento e di successo vengono combinati in un&#39;unica impostazione. Se si seleziona **SCORM 2004**, i criteri di completamento e di successo vengono visualizzati come impostazioni separate, come descritto di seguito.*

- **Criteri di successo**: seleziona il menu a discesa e scegli in che modo il corso misura il successo.

- **Avvio:** contrassegna l&#39;Allievo come passato semplicemente avviando il corso.
  ![](../assets/24_success_criteria_dropdown_launch_minview_quiz_updated.png)

- **Visualizzazione minima %**: contrassegna l’Allievo come superato quando visualizza la percentuale di contenuto specificata. Ad esempio, inserisci 80 per richiedere agli Allievi di visualizzare almeno l’80% del corso.
  ![](../assets/25_success_criteria_minview_percent_field_updated.png)

- **Quiz:** contrassegna l’Allievo come superato o non riuscito a seconda che il punteggio del quiz soddisfi o meno la soglia di punteggio superata. Seleziona una condizione del quiz:

  - **Al tentativo: segna l’esito positivo non appena l’Allievo tenta di rispondere al quiz.**

  - **Al passaggio: segna l’esito positivo solo quando l’Allievo supera il quiz.**

  - **Al superamento o al raggiungimento del limite: indica che l’Allievo ha superato o raggiunto il numero massimo di tentativi consentiti.**

  ![](../assets/26_success_criteria_quiz_condition_dropdown_updated.png)

>[!NOTE]
>
>Un Allievo può completare un corso ma non completarlo comunque, ad esempio, se completa tutti i contenuti ma non ottiene un punteggio sufficiente nel quiz. I criteri di completamento e successo sono indipendenti; è possibile impostarli entrambi con attenzione in base a come si desidera che vengano tenuti traccia dell’avanzamento e delle prestazioni dell’Allievo. Quando selezioni il quiz per uno dei criteri, configura i tentativi del quiz e il punteggio nella scheda **Impostazioni quiz**.


## Perché i criteri di completamento e successo sono importanti per la creazione dei report

- I criteri di completamento controllano quando lo stato di un Allievo diventa Completato nelle trascrizioni ALM, nei dashboard di completamento e in qualsiasi esportazione di conformità o audit estratta dal sistema LMS: misurano l’avanzamento, non le prestazioni.

- I criteri di successo controllano il valore di esito positivo/negativo registrato insieme allo stato di completamento, ovvero il valore su cui si basa la maggior parte dei report di conformità e certificazione.

- Se i criteri di completamento e di successo sono configurati anche nella libreria di contenuti **Adobe Learning Manager** per lo stesso modulo, tali impostazioni hanno la precedenza su quelle impostate in Composizione contenuto. Decidi in anticipo quale prodotto deve possedere queste regole ed evita di impostare valori in conflitto in entrambe le posizioni.

- Corrispondenza dei criteri con ciò che è necessario dimostrare: Avvia o Min view % è sufficiente per il contenuto di consapevolezza, mentre i criteri basati su quiz forniscono una documentazione comprovabile che un Allievo ha dimostrato di sapere, non solo di aver aperto il corso.
