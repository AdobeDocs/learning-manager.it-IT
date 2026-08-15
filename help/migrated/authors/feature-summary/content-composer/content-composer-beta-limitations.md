---
description: 'Limitazioni della versione beta di Review Content Composer: modifica solo a livello di conversazione, quiz MCQ/True-False-only, profili fissi con soluzioni alternative per ciascuno di essi.'
jcr-language: en_us
title: Limitazioni di Content Composer beta
source-git-commit: 68d15fa96588b2569c9b1cdb480e2ba9f31a1cf6
workflow-type: tm+mt
source-wordcount: '495'
ht-degree: 0%

---


# Limitazioni di Adobe Learning Manager Content Composer beta

Elenco completo dei vincoli beta correnti di Content Composer, con descrizioni e soluzioni alternative, se disponibili.

## Limitazioni correnti

La tabella seguente illustra tutti i vincoli noti della versione beta corrente.

| **Limitazione** | **Descrizione** | **Soluzione alternativa** |
|---------------------------------------------------------------|-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|---------------------------------------------------------------------------------------------------------------------------------------------------------------|
| **La modifica del contorno è solo a livello di conversazione** | Non è possibile selezionare una lezione o un argomento nell&#39;area di lavoro per rinominarlo, riordinarlo o eliminarlo. Tutte le modifiche alla struttura devono essere apportate tramite il pannello Chat assistente. | Chiedere all&#39;assistente: &quot;Rinominare la lezione 2 in &#39;Igiene password&#39;&quot; o &quot;Spostare il tema 1.3 nella lezione 2.&quot; |
| **La gerarchia del profilo è fissa** | La struttura del corso è impostata su Lezioni > Argomenti. Non è possibile creare sottoargomenti, livelli di gerarchia aggiuntivi o strutture personalizzate. | Utilizzare i componenti disponibili per aggiungere profondità all&#39;interno di un argomento. |
| **Impossibile modificare il contorno direttamente dopo la generazione del corso** | Una volta generato un corso, i nomi degli argomenti e delle lezioni rimangono parte della struttura. Per modificarle, è necessario tornare alle conversazioni a livello di struttura. Non è possibile rinominarli selezionando un’intestazione nell’editor del corso. | Chiedi all’assistente nell’editor del corso: &quot;Rinomina la lezione 3 in &quot;Risposta all’incidente&quot;.&quot; |
| **Tipi di valutazione: solo MCQ e True/False** | La versione beta corrente supporta solo le domande a scelta multipla (**MCQ**) e le domande True/False. Non sono disponibili altri tipi di valutazione. | - |
| **Le banche domande non sono disponibili** | Non è possibile importare o gestire una serie di domande già create. | Create domande aggiuntive a livello di conversazione: &quot;Aggiungete altre due domande al quiz per la lezione 1.&quot; |
| **I controlli della conoscenza non sono classificati** | I controlli delle conoscenze incorporati nelle lezioni non vengono valutati. Solo le valutazioni dei quiz di fine lezione vengono valutate e registrate. | Utilizzare i quiz (non i controlli delle conoscenze) per qualsiasi valutazione che deve produrre un record di completamento o punteggio. |
| **Azioni di conversazione limitate alle funzionalità supportate** | L&#39;assistente può discutere e fare brainstorming liberamente, ma le modifiche effettive del corso sono limitate alle funzionalità supportate dal prodotto. Le richieste di generare strutture di contenuto o formati non supportati potrebbero non riuscire. | Se una richiesta non funziona, chiedi all&#39;assistente di spiegare cosa può fare. |
| **Generazione con restrizioni ai documenti** | Quando è abilitata l&#39;opzione **Limita output al contenuto nei file**, il modulo di composizione contenuto genera il contenuto solo dai documenti di origine caricati. Non introduce informazioni al di là di tali fonti. | Disattiva l&#39;interruttore per consentire all&#39;IA di integrare le conoscenze generali. |
| **Le funzionalità di collaborazione sono in evoluzione** | Condividi per la revisione e i commenti e Condividi per gli Allievi sono entrambi in fase di sviluppo attivo. I dettagli di implementazione potrebbero cambiare prima della disponibilità generale. | Utilizza **Copia collegamento** per condividere un collegamento di anteprima per la revisione informale. Per la modifica in comproprietà, coordina i giri con i collaboratori. Il co-editing simultaneo non è supportato. |
| **L&#39;assistente interno al prodotto non è un sistema di guida del prodotto** | L’assistente conversazionale è progettato per le attività di modifica dei corsi, come la generazione e la modifica di contenuti. Le risposte alle domande sull’utilizzo dei prodotti potrebbero non essere affidabili perché questo comportamento non è ancora stato progettato in modo esplicito. | Per domande sulle procedure, utilizza la documentazione della guida esistente anziché chiedere informazioni all’assistente interno al prodotto. |
