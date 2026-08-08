---
description: Trovate le risposte alle domande più comuni di Composizione contenuto, inclusi i motivi per cui Genera contorno è disattivato, come rinominare una lezione, perché le domande dei quiz non sono allineate e cosa fare quando Publish è disattivato.
jcr-language: en_us
title: Domande frequenti su Adobe Learning Manager Content Composer
source-git-commit: ea6d296fa99686136ab08d756a20570a4681d704
workflow-type: tm+mt
source-wordcount: '584'
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
