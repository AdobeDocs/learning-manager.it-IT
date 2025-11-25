---
description: Scopri come accedere, scaricare e interpretare il Report di feedback in Adobe Learning Manager. Informazioni sulle colonne dei report, sui tipi di domande, sulle risposte dei manager e degli allievi e su come le informazioni sul feedback supportano la valutazione dei corsi di formazione e il miglioramento continuo.
jcr-language: en_us
title: Report di feedback in Adobe Learning Manager
source-git-commit: e0553621dd67338d2433bb1f82af43cacc2d8b8c
workflow-type: tm+mt
source-wordcount: '856'
ht-degree: 8%

---


# Report di feedback

## Panoramica

Il report Feedback in Adobe Learning Manager raccoglie sia il Livello 1 (feedback dell’Allievo) che il Livello 3 (feedback del Manager) dopo che gli Allievi hanno completato gli oggetti di apprendimento. Questo report presenta una panoramica strutturata delle risposte soggettive e oggettive degli Allievi e dei loro Manager.

Il report tiene traccia dei dettagli dell’Allievo come nome, e-mail, nome del modulo di feedback, versione e lingua e acquisisce le risposte alle domande definite dall’Amministratore. Viene inoltre registrata la selezione dell’Allievo per ogni domanda (ad esempio, Accetto pienamente, Accetto o Non accetto).

## Scopo e vantaggi

* Fornisce informazioni utili per migliorare la qualità del corso e l’efficacia complessiva dell’apprendimento.
* Perfeziona i metodi di navigazione, ritmo e consegna in base al feedback diretto degli utenti.

## Casi d’uso

* **Identificazione rapida dei problemi relativi ai contenuti**: gli amministratori possono individuare punteggi bassi o commenti negativi ripetuti e aggiornare gli oggetti di apprendimento senza attendere i ticket di supporto o le escalation.
* **Misurazione dell’efficacia del corso di formazione**: i team possono confrontare i feedback degli Allievi in più corsi o versioni per capire quali oggetti di apprendimento funzionano correttamente e quali potrebbero dover essere rielaborati.
* **Tenere traccia del coinvolgimento degli Allievi con i moduli di feedback**: gli Amministratori possono vedere quanti Allievi rispondono o ignorano le domande, aiutandoli a perfezionare i moduli di feedback per migliorare la qualità della risposta e i tassi di completamento.

## Come scaricare il report Feedback

1. Accedi a Adobe Learning Manager come amministratore.
2. Seleziona **[!UICONTROL Report]** dal menu di navigazione a sinistra.
   ![](assets/select-report.png)
   _La pagina principale dell&#39;amministratore mostra l&#39;opzione Report evidenziata per il download dei report_

3. Seleziona **[!UICONTROL Report personalizzati]** in Report, quindi seleziona **[!UICONTROL Report Excel]**.
4. Seleziona **[!UICONTROL Report Feedback]**.
   ![](assets/select-feedback-report.png)
   _La sezione Report personalizzati mostra l’opzione per selezionare Report di feedback per accedere ai dati di feedback di Allievi e Manager_

5. Seleziona **[!UICONTROL Tutti i corsi di formazione]** o **[!UICONTROL I corsi di formazione selezionati]** e l’intervallo di date. Se selezioni la seconda opzione, puoi aggiungere fino a un massimo di 10 corsi o percorsi di apprendimento e generare il relativo report di feedback. Inoltre, puoi generare il report fino a un anno.
   ![](assets/feedback-report.png)
   _Configurare il report sul feedback selezionando l’ambito del corso di formazione, impostando l’intervallo di date e scegliendo l’opzione di traduzione prima del download_

6. Seleziona la lingua in cui tradurre il feedback L1. Le domande oggettive e le relative risposte vengono tradotte nella lingua selezionata quando tale versione della lingua è definita in modo esplicito. Nel report vengono visualizzate solo le domande soggettive definite in modo esplicito nella lingua selezionata.  Le risposte alle domande soggettive sono redatte nella lingua originale.
7. Seleziona **[!UICONTROL Scarica]** per scaricare il report.

## Cosa contiene il report Feedback

Di seguito sono riportate le colonne predefinite del report a livello di account:

| Colonna | Descrizione |
|----|----|
| Tipo di feedback | Indica se il feedback proviene dall’Allievo (L1) o dal Manager (L3) |
| Nome utente | Nome dell’Allievo che ha completato il corso di formazione |
| E-mail utente | Indirizzo e-mail dell’allievo |
| ID del corso di formazione | Un identificatore univoco generato dal sistema assegnato a ciascun oggetto di apprendimento (corso, certificazione o percorso di apprendimento) |
| Nome formazione | Nome dell’elemento di apprendimento per il quale viene inviato il feedback |
| Istanza del corso di formazione | Nome dell’istanza del corso di formazione (per corsi a più istanze) |
| Tipo di formazione | Tipo di corso di formazione (corso, certificazione, percorso di apprendimento) |
| Tipo di modulo di feedback | Tipo/categoria del modulo di feedback utilizzato (ad esempio, Corsi misti, Corsi a ritmo personalizzato e Corsi in aula) |
| Nome modulo di feedback | Nome del modulo di feedback |
| Versione feedback | Numero di versione del modulo di feedback |
| Manager attuale | Nome del manager dell’allievo |
| E-mail del manager attuale | Indirizzo e-mail del manager dell’Allievo |
| Data di completamento | Data in cui l’Allievo ha completato il corso di formazione |
| Data del feedback | Data in cui l’Allievo ha inviato il feedback |
| Lingua originale del feedback L1 | Lingua in cui l’Allievo ha inviato originariamente il feedback L1 |
| Domanda 1 della scala Likert L3 | Misura le prestazioni dell’Allievo dopo il corso di formazione utilizzando una scala di valutazione |
| Risposta 1 scala Likert L3 | Risposta del manager a questa domanda su scala Likert |
| Domanda 1 del testo libero L3 | Domanda in formato testo libero aggiunta al modulo di feedback L3 per i Manager; può essere configurata come facoltativa o obbligatoria |
| Risposta testo libero L3 1 | Risposta del manager alla domanda in formato testo libero |

Le seguenti colonne vengono visualizzate nel report a livello di account in base ai quattro tipi di domande aggiunte al modulo di feedback:

| Colonna | Descrizione |
|---|---|
| Efficacia del corso | La domanda predefinita sull’efficacia del corso visualizzata nel modulo |
| Risposta sull&#39;efficacia del corso | Risposta dell’Allievo alla domanda sull’efficacia del corso |
| Domanda 1 del Server dei criteri di rete | Prima domanda sul punteggio Net Promoter |
| Intervallo 1 Server dei criteri di rete | Scala di rating utilizzata (ad esempio, da 0 a 10) |
| Risposta Server dei criteri di rete 1 | Valutazione dell’Allievo per Server dei criteri di rete Domanda 1 |
| Domanda Likert 1 | Prima domanda su una scala di Likert |
| Risposta Likert 1 | Risposta alla domanda Likert 1 |
| Testo domanda 1 | Prima domanda con testo aperto nel modulo |
| Risposta testuale 1 | Risposta dell’Allievo alla domanda testuale 1 |


>[!NOTE]
>
>Il report a livello di account include anche eventuali campi attivi configurati per gli Allievi.

Nel report a livello di oggetto di apprendimento vengono visualizzate le seguenti colonne:

| Colonna | Descrizione |
|---|---|
| Allievo | Nome dell’Allievo |
| E-mail | Indirizzo e-mail dell’Allievo |
| Nome modulo di feedback | Nome del modulo di feedback |
| Versione feedback | Numero di versione del modulo di feedback |
| Lingua Allievo | Lingua selezionata dall’Allievo |

>[!NOTE]
>
>Il report a livello di oggetto di apprendimento include anche le domande aggiunte al modulo di feedback. Ogni domanda viene visualizzata come intestazione di colonna e le risposte dell’Allievo alle domande vengono visualizzate nelle righe corrispondenti di seguito.
