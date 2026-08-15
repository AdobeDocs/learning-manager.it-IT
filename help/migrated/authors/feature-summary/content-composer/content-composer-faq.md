---
description: Trovate le risposte alle domande frequenti di Composizione contenuti sulla modifica dei profili, sul comportamento dei quiz, sulla compatibilità delle Captivate, sulla pubblicazione e su Condividi per revisione.
jcr-language: en_us
title: Domande frequenti su Adobe Learning Manager Content Composer
source-git-commit: 68d15fa96588b2569c9b1cdb480e2ba9f31a1cf6
workflow-type: tm+mt
source-wordcount: '1438'
ht-degree: 0%

---


# Domande frequenti su Adobe Learning Manager Content Composer

Risposte alle domande frequenti sull’utilizzo di Composizione contenuti.

**Il pulsante Genera struttura è disattivato. Cosa devo fare?**

Tutti e tre i campi **Breve**, **Titolo**, **Allievi** e **Obiettivo** devono contenere contenuto prima dell&#39;attivazione di **Genera struttura**. Controlla l’area di lavoro per verificare se sono ancora presenti campi contenenti testo segnaposto in corsivo, ad esempio *Immetti qui il profilo Allievi* o *Immetti l’obiettivo di questo corso*. Compila il campo vuoto e il pulsante si attiva immediatamente.

**Impossibile selezionare la struttura per rinominare una lezione. Perché?**

Nella versione beta corrente, la modifica dei contorni ha un effetto a livello di conversazione. Non è possibile selezionare una lezione o un argomento nell&#39;area di lavoro per rinominarlo o riordinarlo. Digita la modifica in linguaggio semplice nel pannello Chat assistente.

Esempi:

- &quot;Rinominare la lezione 1 in &#39;Funzionamento del phishing&#39;&quot;

- &quot;Spostare il tema 1.3 come primo argomento della lezione 2&quot;

- &quot;Eliminare la lezione 4 e distribuire gli argomenti nella lezione 3&quot;

**La struttura generata non corrisponde a quella desiderata. Si è verificato un errore?**

Lo schema riflette la richiesta e la breve. Se la struttura risulta disattivata, le cause più comuni sono un messaggio che tratta troppi argomenti contemporaneamente o un obiettivo di apprendimento che non indica le competenze o i comportamenti specifici che il corso deve sviluppare.

**L&#39;intelligenza artificiale ha ignorato una sezione importante del file caricato. Come posso risolvere questo problema?**

In Composizione contenuti vengono assegnate priorità alle sezioni del file sorgente più rilevanti per l’obiettivo di apprendimento. Se una sezione viene ignorata, è probabile che non venga riflessa nell&#39;obiettivo.

Per risolvere il problema:

1. Tornate al pannello **Breve** e aggiornate l&#39;obiettivo per assegnare un nome esplicito all&#39;argomento mancante.

2. Chiedere all&#39;assistente di rigenerare il profilo: &quot;Rigenerare il profilo, assicurandosi di includere la sezione relativa ai criteri di conservazione dei dati.&quot;

È inoltre possibile aggiungere manualmente il contenuto mancante come nuovo argomento nella conversazione della struttura: &quot;Aggiungere un nuovo argomento alla lezione 2 denominato &#39;Criteri di conservazione dei dati&#39;.&quot;

**È possibile utilizzare Composizione contenuti con Adobe Captivate?**

N. Composizione contenuti e Adobe Captivate non condividono un flusso di lavoro completo. Non è possibile aprire progetti di Composizione contenuto in Captivate né progetti di Captivate in Composizione contenuto.

Un file MP4 esportato dalla Captivate può essere inserito come componente **Video** in Content Composer.

**Posso utilizzare Content Composer per corsi di formazione sulla conformità o regolamentati?**

Sì. Questo è uno dei casi più forti. Carica i documenti di policy o procedure in Gestisci file sorgente e seleziona Limita l&#39;output al contenuto nei file in modo che l&#39;intelligenza artificiale venga generata solo da ciò che hai fornito, anziché completare con le informazioni generali.

**Perché i controlli della conoscenza non vengono valutati?**

I controlli della conoscenza in Composizione contenuto sono progettati per l’apprendimento del rinforzo durante una lezione, non per il punteggio. Forniscono un feedback immediato all’Allievo, ma non producono un record di livello o completamento.

Solo le valutazioni dei quiz di fine lezione vengono valutate. Se è necessaria una valutazione che contribuisca al punteggio di un Allievo, utilizza il quiz e non un componente di verifica della conoscenza.

**Le domande del quiz non corrispondono a ciò che insegna il corso. Come posso risolvere questo problema?**

Content Composer utilizza l’IA per generare le domande dei quiz e l’output dell’IA non è deterministico. Le domande potrebbero non riflettere sempre esattamente ciò che ti aspetti. Dopo aver generato il corso, esamina tutte le domande sul quiz, modifica eventuali domande che richiedono modifiche direttamente nell’editor del corso e verifica che il contenuto sia accurato prima della pubblicazione.

## Informazioni su Condividi per revisione

**Che cos&#39;è Condividi per revisione in Composizione contenuti?**

Condividi per la revisione consente di distribuire un corso ai revisori per ricevere feedback prima della pubblicazione. I revisori aprono il corso in un browser, aggiungono commenti su qualsiasi componente e provano a eseguire il quiz, senza installare Content Composer o avere bisogno di un abbonamento.

**I revisori devono disporre di una licenza di Content Composer?**

N. I revisori non hanno bisogno di un abbonamento o di un&#39;installazione di Content Composer. Chiunque disponga del collegamento alla revisione può aprire il corso nel proprio browser.

**Per partecipare i revisori è necessario un Adobe ID?**

Sì. La revisione di un corso richiede l’accesso, quindi per partecipare è richiesto un Adobe ID. Una volta effettuato l’accesso, i revisori possono aprire il corso, aggiungere commenti, provare a svolgere il quiz e utilizzare @mentions per assegnare tag all’autore o ad altri revisori.

**I revisori possono modificare il contenuto del corso?**

N. L’accesso alla revisione è di solo commento. I revisori possono aggiungere, rispondere, risolvere e filtrare i commenti, ma non possono modificare il testo, le immagini o la struttura del corso.

Dove vengono archiviati i file di revisione? I file di revisione sono ospitati nel cloud di Adobe. Gli Autori non devono gestire l’archiviazione dei file né inviare direttamente i file dei corsi ai revisori.

### Condivisione e accesso

**Chi può accedere a un collegamento per la revisione?**

Per impostazione predefinita, solo le persone invitate per nome o e-mail possono accedere al progetto. Prima di inviare il collegamento, verificatelo nella sezione Chi ha accesso del pannello Condividi progetto.

**Posso invitare stakeholder esterni che non sono utenti Adobe?**

Sì, puoi invitare chiunque tramite indirizzo e-mail. Tuttavia, per accedere e rivedere il corso, è necessario disporre di un account di Adobe.

**È possibile aggiungere revisori dopo l&#39;avvio della revisione?**

Sì. Aprite il pannello Condividi progetto in qualsiasi momento, aggiungete nomi o indirizzi e-mail e selezionate Invita a commentare. I nuovi revisori ricevono immediatamente un invito.

**È possibile rimuovere un revisore dopo la condivisione?**

Sì. Nel pannello Condividi progetto, individua il revisore in Chi ha accesso e rimuovilo. Se tenta di aprire il corso utilizzando un collegamento condiviso in precedenza, viene visualizzato un messaggio di accesso negato.

**Cosa succede se un revisore perde l&#39;accesso?**

Possono selezionare Richiedi accesso nella schermata Accesso negato. Il proprietario del corso riceve una notifica per il ripristino dell’accesso.

### Commenti e feedback

I revisori possono commentare una parte specifica del corso?

Sì. I revisori selezionano un componente del corso, ovvero un blocco di testo, un’immagine o una domanda a quiz, e aggiungono un commento direttamente su tale elemento. I commenti rimangono contestualmente collegati al componente su cui sono stati aggiunti.

**Più revisori possono commentare contemporaneamente?**

Sì. Tutti i revisori possono visualizzare i commenti degli altri nel pannello Commenti e possono rispondere, risolvere o @mention.

**È possibile filtrare i commenti per trovare feedback non risolti?**

Sì. Utilizzate il filtro Risolto nel pannello Commenti per visualizzare solo i commenti non risolti. È inoltre possibile filtrare in base ai revisori per visualizzare il feedback di una persona specifica oppure in base all&#39;ora per trovare i commenti più recenti.

**Come si assegna un tag a un altro revisore in un commento?**

Digita @ seguito dal nome o dall&#39;indirizzo e-mail e selezionalo dal menu a discesa. Gli utenti con tag ricevono una notifica. Ciò richiede che il revisore acceda con un Adobe ID.

#### Quiz e accesso Allievo

**I revisori possono tentare il quiz?**

Sì. I revisori possono tentare il quiz fino al numero specificato di tentativi. I loro punteggi non vengono registrati e non influiscono sul corso né sui report LMS.

**Qual è la differenza tra la condivisione per la revisione e la condivisione per gli Allievi?**

Condividi per la revisione consente di accedere al corso con il pannello dei commenti abilitato, pensato per colleghi e stakeholder che forniscono feedback. Condividi per gli Allievi consente di accedere al corso senza commenti, rivolto agli Allievi che non sono iscritti tramite un LMS. Inoltre, i punteggi degli Allievi non vengono registrati tramite un collegamento diretto.

### Aggiornamento e chiusura di una revisione

**È necessario creare una nuova revisione dopo aver apportato le modifiche?**

N. L’URL di revisione resta invariato dopo l’aggiornamento del corso. Selezionare **Condividi** per notificare ai revisori che è disponibile una versione aggiornata.

**I revisori riceveranno una notifica quando aggiorno il corso?**
I revisori visualizzano un banner di notifica quando aprono il collegamento alla revisione dopo un aggiornamento. Possono selezionare Ricarica per visualizzare la versione più recente.

**I commenti precedenti rimangono dopo un aggiornamento del corso?**

Sì. I commenti esistenti persistono negli aggiornamenti. I revisori e gli autori possono continuare a risolvere i commenti sulla versione aggiornata.

**Cosa succede a un collegamento Allievo dopo aver aggiornato il corso?**

Il collegamento Allievo esistente continua a mostrare la versione precedente. Genera un nuovo collegamento dopo ogni aggiornamento e condividilo con gli Allievi per garantire che accedano ai contenuti più recenti.

**Come si visualizzano gli aggiornamenti del progetto?**

Se l’Autore aggiorna il corso mentre lo stai esaminando, viene visualizzata una notifica.

![](../assets/68_newer_version_available_reload_notification.png)

- Seleziona **Ricarica** per caricare la versione più recente o annulla la notifica per continuare la revisione della versione corrente. Il ricaricamento è sicuro: i commenti esistenti persistono anche dopo gli aggiornamenti del progetto, quindi non perderai i feedback che hai già aggiunto.

## Provate a eseguire il quiz come revisore

In qualità di revisore, puoi tentare di rispondere al quiz fino al numero di volte specificato, ma i tuoi punteggi non vengono registrati.

- Selezionare **AVVIA QUIZ** per tentare il quiz.

  ![](../assets/66_final_quiz_start_screen_attempts_info.png)

- Al termine vengono visualizzati i risultati. Da qui, è possibile selezionare Rivedi le risposte per vedere quali domande sono state corrette o sbagliate, oppure Ripeti il quiz per riprovare.

  ![](../assets/67_quiz_results_attempts_remaining_reviewer.png)




