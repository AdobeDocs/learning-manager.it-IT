---
jcr-language: en_us
title: Interpretare il file CSV Trascrizione Allievo
description: Interpretare il file CSV Trascrizione Allievo
contentowner: saghosh
preview: true
source-git-commit: fba5e5ddc1964b485be473bf356806f234688cf4
workflow-type: tm+mt
source-wordcount: '2997'
ht-degree: 0%

---



# Interpretare il file CSV Trascrizione Allievo

La Trascrizione Allievo è uno dei report più diffusi utilizzati in Learning Manager di Adobe. Il report consente di ottenere quasi tutti i dettagli possibili in un unico report in formato CSV.

Oltre a essere un report che gli utenti possono recuperare per monitorare e analizzare i comportamenti di apprendimento, il report può anche essere visualizzato come il formato in cui Learning Manager può essere configurato per esportare i dati sui comportamenti di apprendimento in applicazioni/sistemi esterni.

Uno scenario aziendale tipico consiste nell’esportare periodicamente le trascrizioni degli Allievi per Learning Manager, analizzarle per estrarre gli Allievi che completano un importante programma di apprendimento e ordinare un buono regalo per riconoscere e premiare i completamenti puntuali.

Un altro caso di utilizzo consiste nell’aggiungere i dati relativi al comportamento di apprendimento a un data warehouse aziendale, in cui è possibile combinare i dati di apprendimento con altri dati aziendali per analizzare le correlazioni tra il comportamento di apprendimento e altri dati di processo.

Nel resto del documento viene descritto in breve come recuperare la Trascrizione Allievo da Learning Manager; quindi viene descritto in dettaglio come interpretare ogni riga e colonna del report.

Queste informazioni possono essere utili per qualsiasi sviluppatore che intenda integrare Learning Manager con altri sistemi mediante l’elaborazione dei dati di trascrizione dell’Allievo esportati.

## Recupero della trascrizione dell’Allievo dall’interfaccia utente {#fetchlearnertranscriptfromtheuserinterface}

Dalle Impostazioni profilo, un Allievo può scaricare la propria trascrizione. Per ulteriori informazioni, consulta *** [Scarica Trascrizione Allievo](../../administrators/feature-summary/learner-transcripts.md)***.

Gli Amministratori possono generare le Trascrizioni Allievi per l’intera organizzazione, un gruppo specifico di utenti o un gruppo specifico di oggetti di apprendimento oppure un gruppo specifico di utenti e oggetti di apprendimento. Possono anche ottenere tutti i record di apprendimento per una durata di intervallo di tempo e indicare se sono necessarie informazioni a livello di modulo (per impostazione predefinita, le informazioni a livello di modulo vengono omesse). Per ulteriori dettagli, consulta [***Scarica le Trascrizioni Allievi***](../../administrators/feature-summary/learner-transcripts.md).

<!--Update above link?-->

Gli Amministratori possono anche configurare il sistema per inviare periodicamente e-mail alla Trascrizione Allievo.

La Trascrizione Allievo generata tramite l’interfaccia utente sarà un file Excel, che contiene anche la &quot;Trascrizione abilità&quot;. In questo documento, ci riferiremo a ciò che viene generato nel formato CSV, un report contenente le attività di apprendimento relative all’iscrizione, all’avvio, all’avanzamento o al completamento di un oggetto di apprendimento.

## Esporta trascrizione Allievo {#exportlearnertranscript}

Quando la Trascrizione Allievo deve essere utilizzata da un sistema esterno, Learning Manager fornisce la funzione Esporta dati, in cui Trascrizione Allievo è uno dei tipi di dati che possono essere esportati. Come spiegato nel Preambolo, ciò è necessario per l’integrazione di Learning Manager con un sistema esterno che deve elaborare i dati relativi al comportamento di apprendimento o per popolare un data warehouse aziendale con i dati sul comportamento di apprendimento.

Per dettagli su come i connettori che supportano l’esportazione delle trascrizioni degli allievi, consulta la [Sezione Esporta dati](/help/migrated/integration-admin/feature-summary/connectors.md) nei connettori FTP, Box e Power BI.

Lo scopo di questi connettori è quello di esportare periodicamente i dati in un&#39;applicazione downstream (una volta in N giorni). Pertanto, questi connettori esportano in ogni sequenza solo i dati relativi al comportamento di apprendimento incrementale. Tieni presente che questi connettori non consentono di recuperare i record relativi a un sottoinsieme specifico di utenti o oggetti di apprendimento: si tratta sempre di dati su tutti gli utenti e su tutti gli oggetti di apprendimento in quell’account.

Nel caso di Power BI, il cliente deve fornire un’area di lavoro in cui Learning Manager possa continuare a esportare questi dati in modo incrementale in un set di dati creato dinamicamente. Questo connettore esporta semplicemente i dati e i clienti devono creare i propri report/dashboard in base a questo set di dati in base alle esigenze.

La sezione successiva fornisce i dettagli su come un sistema downstream deve interpretare i record nella trascrizione Allievo.

## Interpretare la Trascrizione Allievo {#interpretthelearnertranscript}

Ogni riga di una Trascrizione Allievo può essere considerata come un comportamento di apprendimento acquisito in Learning Manager in un periodo di tempo specifico. In genere, i connettori esportano &quot;dati incrementali&quot; e quindi le righe rappresentano le attività di apprendimento che si sono svolte tra l’ultima esecuzione del connettore e l’esecuzione corrente.

Naturalmente, i connettori consentono anche di recuperare la trascrizione dell’Allievo su richiesta; in questo caso, l’utente può specificare una data di inizio e si presume che la data di fine sia ora. Solitamente, una volta all’inizio si esegue questa operazione, quindi si configura il connettore per l’esportazione della trascrizione Allievo incrementale a un’ora specifica del giorno, una volta ogni N giorni (il valore predefinito è N, ovvero 1).

Definiamo ora cosa si intende per Trascrizione Allievo incrementale

Nella trascrizione Allievo, ogni riga rappresenta un’attività specifica che coinvolge un Allievo specifico e un oggetto di apprendimento specifico. Siamo interessati principalmente a quale stato si trova un Allievo in relazione all’oggetto di apprendimento: **Iscritto**, **Avviato**, **In corso** e **Completato**. Pertanto, la trascrizione Allievo acquisisce anche quattro date corrispondenti.

Ora esistono tre tipi di oggetti di apprendimento, in cui Learning Manager tiene traccia dell’avanzamento dell’Allievo, e i dati esportati contengono informazioni sull’avanzamento a livello di modulo, che è l’unità di contenuto più granulare che un Allievo può provare in Learning Manager.

* **Corso** - una composizione di uno o più moduli
* **Programma di apprendimento** - una composizione di uno o più corsi
* **Certificazione** - una composizione di uno o più corsi.

Ogni riga della Trascrizione Allievo riguarda il coinvolgimento di un utente specifico in un modulo, corso, programma di apprendimento o certificazione. Quando un utente è iscritto a un programma di apprendimento, la trascrizione indica che l’utente è

Le colonne della Trascrizione Allievo forniscono varie informazioni relative a ciascuna attività di apprendimento e le tabelle seguenti descrivono la semantica di ciascuna colonna.

## Trascrizione Allievo

<table> 
 <tbody> 
  <tr> 
   <th width="158" valign="bottom"><p><b>Nome colonna</b></p></th> 
   <th width="160" valign="bottom"><p><b>Tipo di valore</b></p></th> 
   <th width="306" valign="bottom"><p><b>Descrizione</b></p></th> 
  </tr> 
  <tr> 
   <td><p><b>Nome</b></p></td> 
   <td><p>Mai vuoto</p></td> 
   <td><p>Nome dell’Allievo</p></td> 
  </tr> 
  <tr> 
   <td><p><b>email</b></p></td> 
   <td><p>Mai vuoto</p></td> 
   <td><p>Indirizzo e-mail dell’Allievo</p></td> 
  </tr> 
  <tr> 
   <td valign="bottom"><b>Adobe ID</b></td> 
   <td valign="bottom">Può essere vuoto</td> 
   <td valign="bottom">Adobe ID dell’Allievo</td> 
  </tr> 
  <tr> 
   <td height="19" width="283"><b>ID univoco utente</b></td> 
   <td height="19" width="283">Può essere vuoto</td> 
   <td height="19" width="728">ID univoco utente dell’Allievo. Questa colonna si basa sull’impostazione back-end, abilitata o disabilitata a livello di account.</td> 
  </tr> 
  <tr> 
   <td valign="middle"><p><b>Nome del piano di apprendimento</b></p></td> 
   <td valign="middle"><p>Può essere vuoto</p></td> 
   <td valign="middle">Nome dell’eventuale piano di apprendimento, al quale l’utente è stato automaticamente assegnato.</td> 
  </tr> 
  <tr> 
   <td valign="middle"><p><b>LP/Certificazione/Corso</b></p></td> 
   <td valign="middle"><p>Mai vuoto</p></td> 
   <td valign="middle"><p>Nome del programma di apprendimento, certificazione o corso</p></td> 
  </tr> 
  <tr> 
   <td valign="middle"><p><b>Tipo</b></p></td> 
   <td valign="middle">Mai vuoto</td> 
   <td valign="middle"><p>Il tipo di oggetto di apprendimento a cui l’utente è stato iscritto.</p></td> 
  </tr> 
  <tr> 
   <td valign="middle"><p><b>Corso</b></p></td> 
   <td valign="middle"><p>Può essere vuoto</p></td> 
   <td valign="middle">Nome del corso a cui l’utente è iscritto. Quando è vuota, la riga rappresenta un programma di certificazione o di apprendimento. </td> 
  </tr> 
  <tr> 
   <td height="19" width="283"><b>ID univoco LO</b></td> 
   <td height="19" width="283">Può essere vuoto</td> 
   <td height="19" width="728">ID univoco dell’oggetto di apprendimento LO. Questa colonna si basa sull’impostazione, abilitata o disabilitata a livello di account.</td> 
  </tr> 
  <tr> 
   <td valign="middle"><p><b>Istanza  </b></p></td> 
   <td valign="middle">Mai vuoto</td> 
   <td valign="middle">Nome dell’istanza dell’oggetto di apprendimento a cui è iscritto l’utente. </td> 
  </tr> 
  <tr> 
   <td valign="middle"><p><b>Criteri di selezione</b></p></td> 
   <td valign="middle"><p>Mai vuoto</p></td> 
   <td valign="middle"><p>Base dell’iscrizione (come l’allievo è stato iscritto all’LO).</p></td> 
  </tr> 
  <tr> 
   <td valign="middle"><p><b>Modulo</b></p></td> 
   <td valign="middle"><p>Può essere vuoto</p></td> 
   <td valign="middle">Nome del modulo all’interno dei corsi. Se vuota, questa riga rappresenta un corso, un programma di apprendimento o una certificazione.</td> 
  </tr> 
  <tr> 
   <td height="19" width="283"><b>Versione</b></td> 
   <td height="19" width="283">Può essere vuoto</td> 
   <td height="19" width="728">Versione del modulo</td> 
  </tr> 
  <tr> 
   <td height="19" width="283"><b>Tipo di consegna</b></td> 
   <td height="19" width="283">Può essere vuoto</td> 
   <td height="19" width="728">Tipo di erogazione del modulo: eLearning, F2F, VC, Attività.</td> 
  </tr> 
  <tr> 
   <td height="19" width="283"><b>Lingua</b></td> 
   <td height="19" width="283">Può essere vuoto</td> 
   <td height="19" width="728">Lingua in cui il modulo viene utilizzato dall’Allievo. Questa colonna mostra il valore solo per i moduli di eLearning.</td> 
  </tr> 
  <tr> 
   <td height="19" width="283"><b>Commento</b></td> 
   <td height="19" width="283">Può essere vuoto</td> 
   <td height="19" width="728">Commenti aggiunti dall’Amministratore, istruttore dell’Allievo mentre segna la partecipazione dell’utente.</td> 
  </tr> 
  <tr> 
   <td height="19" width="283"><b>Data di iscrizione (fuso orario Asia/Calcutta)</b></td> 
   <td height="19" width="283">Mai vuoto</td> 
   <td height="19" width="728">Data di iscrizione dell’Allievo al tipo di LO.</td> 
  </tr> 
  <tr> 
   <td height="19" width="283"><b>Data di inizio (fuso orario Asia/Calcutta)</b></td> 
   <td><p>Può essere vuoto</p></td> 
   <td height="19" width="728">Data in cui l’Allievo ha avviato l’LO. Se il campo è vuoto significa che l’Allievo non ha ancora iniziato l’attività.</td> 
  </tr> 
  <tr> 
   <td height="19" width="283"><b>Data di completamento (fuso orario Asia/Calcutta)</b></td> 
   <td><p>Può essere vuoto</p></td> 
   <td><p>Data in cui l’Allievo ha completato l’attività. Se il campo è vuoto significa che l’Allievo non ha ancora completato l’attività.</p></td> 
  </tr> 
  <tr> 
   <td height="19" width="283"><b>Scadenza (fuso orario Asia/Calcutta)</b></td> 
   <td><p>Può essere vuoto</p></td> 
   <td height="19" width="728">Data entro la quale l’Allievo deve completare l’LO. Se il campo è vuoto significa che non esiste una scadenza per l'operazione.</td> 
  </tr> 
  <tr> 
   <td height="19" width="283"><b>Scaduto</b></td> 
   <td height="19" width="283">Sì/No</td> 
   <td height="19" width="728">Stato di ritardo corrente dell’Allievo iscritto all’LO. Sì/No</td> 
  </tr> 
  <tr> 
   <td valign="middle"><p><b>Stato</b></p></td> 
   <td valign="middle">Non avviato/Completato/In corso/Non registrato</td> 
   <td valign="middle">% avanzamento corrente dell’Allievo iscritto all’LO.</td> 
  </tr> 
  <tr> 
   <td valign="middle"><p><b>% avanzamento</b></p></td> 
   <td valign="middle">Può essere vuoto</td> 
   <td valign="middle"><p>Indica in che misura l’Allievo ha completato l’attività.</p></td> 
  </tr> 
  <tr> 
   <td height="38" width="283"><b>Tempo impiegato (minuti)</b></td> 
   <td height="38" width="283">Può essere vuoto</td> 
   <td height="38" width="728">Il tempo di apprendimento impiegato dall’Allievo nell’LO, le righe a livello di modulo mostrano il tempo di apprendimento dedicato al singolo modulo. Le righe a livello di corso/programma/certificato mostrano il tempo di apprendimento aggregato impiegato.</td> 
  </tr> 
  <tr> 
   <td valign="middle"><p><b>Grado</b></p></td> 
   <td valign="middle">Superata/Non superata</td> 
   <td valign="middle">Indica l’esito positivo dell’Allievo. "Superato", se l’utente ha soddisfatto i criteri di successo, altrimenti "Non superato".</td> 
  </tr> 
  <tr> 
   <td valign="middle"><p><b>Punteggio quiz</b></p></td> 
   <td valign="middle">Può essere vuoto</td> 
   <td valign="middle">L’ultimo punteggio del quiz ottenuto dall’Allievo. Può essere vuoto, se l’Allievo non ha tentato il quiz o se il contenuto non include quiz o se l’Amministratore/Istruttore non ha assegnato alcun punteggio.</td> 
  </tr> 
  <tr> 
   <td height="38" width="283"><b>Quiz_score_max</b></td> 
   <td height="38" width="283">Può essere vuoto</td> 
   <td height="38" width="728">L’ultimo punteggio massimo del quiz per il modulo. Può essere vuoto se l’Allievo non ha tentato il quiz o se il contenuto non include quiz.</td> 
  </tr> 
  <tr> 
   <td height="38" width="283"><b>Highest_Quiz_score</b></td> 
   <td height="38" width="283">Può essere vuoto</td> 
   <td height="38" width="728">Il punteggio più alto del quiz ottenuto dall’Allievo dopo più tentativi. Può essere vuoto, se l’Allievo non ha tentato il quiz o se il contenuto non include quiz o se l’Amministratore/Istruttore non ha assegnato alcun punteggio.</td> 
  </tr> 
  <tr> 
   <td height="38" width="283"><b>Highest_Quiz_score_max</b></td> 
   <td height="38" width="283">Può essere vuoto</td> 
   <td height="38" width="728">Il punteggio massimo del quiz per il modulo. Può essere vuoto se l’Allievo non ha tentato il quiz o se il contenuto non include quiz.</td> 
  </tr> 
  <tr> 
   <td height="19" width="283"><b>Tentativi effettuati</b></td> 
   <td height="19" width="283">Può essere vuoto</td> 
   <td height="19" width="728">Numero totale di tentativi compiuti dall’Allievo per questo modulo.</td> 
  </tr> 
  <tr> 
   <td height="19" width="283"><b>Numero massimo di tentativi consentiti</b></td> 
   <td height="19" width="283">Può essere vuoto</td> 
   <td height="19" width="728">Numero massimo di tentativi consentiti per l’Allievo per utilizzare il modulo.</td> 
  </tr> 
  <tr> 
   <td valign="middle"><p><b>userState</b></p></td> 
   <td valign="middle">Mai vuoto</td> 
   <td valign="middle">Stato utente dell’Allievo: attivo/eliminato/sospeso.</td> 
  </tr> 
  <tr> 
   <td height="38" width="283"><b>Campo attivo raggruppabile</b></td> 
   <td height="38" width="283">Può essere vuoto</td> 
   <td height="38" width="728">Per ogni campo attivo raggruppabile dell’account, sarà presente una colonna, con il nome Campo attivo, e il valore sarà il valore specifico dell’Allievo per quel campo.</td> 
  </tr> 
  <tr> 
   <td><p><b>Nome del manager</b></p></td> 
   <td><p><i>Può essere vuoto</i></p></td> 
   <td height="19" width="728">Nome del Manager dell’Allievo</td> 
  </tr> 
  <tr> 
   <td height="38" width="283"><b>Conteggio iscrizioni</b></td> 
   <td height="38" width="283">1 o 0</td> 
   <td height="38" width="728">Conteggio iscrizioni dell’Allievo per l’LO. La riga LO di livello più alto mostra un valore = "1". I corsi di formazione secondari mostrano un valore pari a 0.</td> 
  </tr> 
  <tr> 
   <td height="19" width="283"><b>Conteggio avviato</b></td> 
   <td height="19" width="283">1 o 0</td> 
   <td height="19" width="728">Conteggio avviato dell’Allievo per l’LO. La riga LO di livello più alto mostra un valore = "1". I corsi di formazione secondari mostrano un valore pari a 0.</td> 
  </tr> 
  <tr> 
   <td height="58" width="283"><b>Conteggio completamento</b></td> 
   <td height="58" width="283">1 o 0</td> 
   <td height="58" width="728">Conteggio completamenti dell’Allievo per l’LO. La riga LO di livello più alto mostra un valore = "1" se l’Allievo è in attesa di completare il corso di formazione. I corsi di formazione secondari mostrano un valore pari a 0 quando è in stato In sospeso. La riga LO di livello più alto mostra un valore = "0", se l’Allievo ha completato il corso di formazione.</td> 
  </tr> 
  <tr> 
   <td height="38" width="283"><b>Scadenza tra N giorni</b></td> 
   <td height="38" width="283">1 o 0</td> 
   <td height="38" width="728">In questo modo viene visualizzato un valore di "1" o "0" a seconda della scadenza dell’istanza a cui è iscritto l’Allievo che segue il corso di formazione. Dipende dal valore immesso nel campo "Data di scadenza prevista in" del foglio I del riepilogo di apprendimento.</td> 
  </tr> 
  <tr> 
   <td height="38" width="283"><b>Scadenza tra N giorni per l’utente</b></td> 
   <td height="38" width="283">1 o 0</td> 
   <td height="38" width="728">In questo modo viene visualizzato un valore di "1" o "0" a seconda della scadenza dell’istanza a cui è iscritto l’Allievo che segue il corso di formazione. Dipende dal valore immesso nel campo "Data di scadenza prevista in" del foglio II del riepilogo di apprendimento.</td> 
  </tr> 
  <tr> 
   <td height="38" width="283"><b>Conteggio di (avanzamento superiore al N%)</b></td> 
   <td height="38" width="283">1 o 0</td> 
   <td height="38" width="728">Viene visualizzato un valore di "1" o "0" a seconda dell’avanzamento dell’Allievo nel corso di formazione. Dipende dal valore immesso nel campo "Avanzamento superiore a" del foglio I del riepilogo di apprendimento.</td> 
  </tr> 
  <tr> 
   <td height="38" width="283"><b>Conteggio di (avanzamento superiore al N%) per l’utente</b></td> 
   <td height="38" width="283">1 o 0</td> 
   <td height="38" width="728">Viene visualizzato un valore di "1" o "0" a seconda dell’avanzamento dell’Allievo nel corso di formazione. Dipende dal valore immesso nel campo "Avanzamento superiore a" del foglio II del riepilogo di apprendimento.</td> 
  </tr> 
  <tr> 
   <td height="19" width="283">T<b>ID formazione</b></td> 
   <td height="19" width="283">Mai vuoto</td> 
   <td height="19" width="728">ID del corso di formazione.</td> 
  </tr> 
  <tr> 
   <td height="20" width="283"><b>Durata del corso di formazione o del modulo (minuti)</b></td> 
   <td height="20" width="283">Mai vuoto</td> 
   <td height="20" width="728">Durata totale del corso di formazione o del modulo (minuti) dell’istanza predefinita del corso di formazione.</td> 
  </tr> 
 </tbody> 
</table>

### Riepilogo apprendimento I

<table cellpadding="1" cellspacing="0" border="1"> 
 <tbody> 
  <tr> 
   <th>Nome colonna<br></th> 
   <th>Tipo di valore</th> 
   <th>Descrizione</th> 
  </tr> 
  <tr> 
   <td height="19" width="264">Tipo</td> 
   <td height="19" width="253">Tutto, Programma di apprendimento, Certificato, Corso.</td> 
   <td height="19" width="412">Tipo di LO per il quale la tabella Riepilogo apprendimento deve visualizzare i dati.</td> 
  </tr> 
  <tr> 
   <td height="19" width="264">Campo raggruppabile (profilo)</td> 
   <td height="19" width="253">Mai vuoto</td> 
   <td height="19" width="412">Profilo per il quale la tabella di riepilogo dell’apprendimento deve visualizzare i dati.</td> 
  </tr> 
  <tr> 
   <td height="38" width="264">Nome del manager</td> 
   <td height="38" width="253">Mai vuoto</td> 
   <td height="38" width="412">Il nome del manager dei subordinati i cui dati sul coinvolgimento nell’LO devono essere visualizzati sulla tabella di riepilogo dell’apprendimento.</td> 
  </tr> 
  <tr> 
   <td height="19" width="264">Etichette righe</td> 
   <td height="19" width="253">Mai vuoto</td> 
   <td height="19" width="412">Il nome LO con l’elenco degli Allievi iscritti all’LO.</td> 
  </tr> 
  <tr> 
   <td height="19" width="264">Numero di Allievi iscritti</td> 
   <td height="19" width="253">Mai vuoto</td> 
   <td height="19" width="412">Numero di Allievi iscritti all’LO.</td> 
  </tr> 
  <tr> 
   <td height="19" width="264">Numero di Allievi che hanno iniziato</td> 
   <td height="19" width="253">Mai vuoto</td> 
   <td height="19" width="412">Numero di Allievi che hanno avviato l’LO.</td> 
  </tr> 
  <tr> 
   <td height="19" width="264">Numero di Allievi che hanno completato</td> 
   <td height="19" width="253">Mai vuoto</td> 
   <td height="19" width="412">Numero di Allievi che hanno completato l’LO.</td> 
  </tr> 
  <tr> 
   <td height="38" width="264">Numero di Allievi con avanzamento &gt;= N%</td> 
   <td height="38" width="253">Mai vuoto</td> 
   <td height="38" width="412">Numero di Allievi con avanzamento &gt;= N% (valori).</td> 
  </tr> 
  <tr> 
   <td height="39" width="264">Numero di Allievi con data di scadenza tra N giorni</td> 
   <td height="39" width="253">Mai vuoto</td> 
   <td height="39" width="412">Numero di Allievi con data di scadenza tra N giorni (valori).</td> 
  </tr> 
 </tbody> 
</table>

### Riepilogo dell’apprendimento II

| Nome colonna | Tipo di valore | Descrizione |
|---|---|---|
| Tipo | Tutto, Programma di apprendimento, Certificato, Corso. | Tipo di LO per il quale la tabella Riepilogo apprendimento deve visualizzare i dati. |
| Campo raggruppabile (profilo) | Mai vuoto | Profilo per il quale la tabella di riepilogo dell’apprendimento deve visualizzare i dati. |
| Nome del manager | Mai vuoto | Il nome del manager dei subordinati i cui dati sul coinvolgimento nell’LO devono essere visualizzati sulla tabella di riepilogo dell’apprendimento. |
| Etichette righe | Mai vuoto | Il nome dell’Allievo con l’elenco degli LO a cui è iscritto l’Allievo. |
| Numero di oggetti di apprendimento iscritti | Mai vuoto | Numero di oggetti di apprendimento a cui è iscritto l’Allievo. |
| Numero di oggetti di apprendimento avviati | Mai vuoto | Numero di oggetti di apprendimento avviati. |
| Numero di oggetti di apprendimento completati | Mai vuoto | Numero di oggetti di apprendimento completati. |
| Numero di oggetti di apprendimento con avanzamento >= N% | Mai vuoto | Il numero di oggetti di apprendimento in cui l’Allievo ha fatto progressi >= N%. |
| Numero di oggetti di apprendimento con data di scadenza tra N giorni | Mai vuoto | Numero di oggetti di apprendimento con scadenza tra N giorni. |

### Riepilogo conformità

| Nome colonna | Tipo di valore | Descrizione |
|---|---|---|
| Tipo | Tutto, Programma di apprendimento, Certificato, Corso. | Tipo di LO per il quale la tabella Riepilogo apprendimento deve visualizzare i dati. |
| Etichette di riga (colonna laterale sinistra) | Mai vuoto | Il nome dell’Allievo con l’elenco degli LO a cui è iscritto l’Allievo. |
| Etichette di riga (colonna laterale sinistra) | Mai vuoto | Il nome dell’Allievo con l’elenco degli LO a cui è iscritto l’Allievo. |

### Trascrizione abilità

| .Nome colonna | Tipo di valore | Descrizione |
|---|---|---|
| Nome | Mai vuoto | Nome dell’Allievo |
| email | Mai vuoto | Indirizzo e-mail dell’Allievo |
| Adobe ID | Può essere vuoto | Adobe ID dell’Allievo |
| ID univoco utente | Può essere vuoto | ID univoco utente dell’Allievo. Questa colonna si basa sull’impostazione back-end, abilitata o disabilitata a livello di account. |
| Abilità | Mai vuoto | Nome dell’abilità assegnata all’Allievo. |
| Livello di competenza | Mai vuoto | Livello di abilità assegnato all’Allievo. |
| Crediti richiesti | Mai vuoto | Totale crediti richiesti dall’Allievo per ottenere la competenza. |
| Crediti guadagnati | Mai vuoto | Totale crediti guadagnati dall’Allievo per la competenza. |
| Percentuale completamento | Mai vuoto | Percentuale di avanzamento per raggiungere l’abilità. |
| Data assegnazione (fuso orario UTC) | Mai vuoto | Data in cui la competenza è stata assegnata all’Allievo. |
| Data acquisizione (fuso orario UTC) | Mai vuoto | Data in cui l’Allievo ha raggiunto la competenza. |
| userState | Mai vuoto | Stato utente dell’Allievo: attivo/eliminato/sospeso. |
| Campo attivo raggruppabile | Può essere vuoto | Per ogni campo attivo raggruppabile dell’account, sarà presente una colonna, con il nome Campo attivo, e il valore sarà il valore specifico dell’Allievo per quel campo. |
| Nome del manager | Può essere vuoto | Nome del Manager dell’Allievo. |

### Riepilogo competenze I

| Nome colonna | Tipo di valore | Descrizione |
|---|---|---|
| Dopo | Mai vuoto | Numero di Allievi che hanno acquisito l’abilità, prima del numero di giorni inserito (valore) che deve essere aggiornato. |
| Nome | Tutti o qualsiasi nome dell’Allievo | Nome dell’Allievo a cui è stata assegnata una competenza. |
| Nome del manager | Mai vuoto | Il nome del manager dei subordinati i cui dati sul coinvolgimento sono visualizzati nella tabella di riepilogo dell’abilità. |
| Etichette righe | Mai vuoto | Il nome della competenza con l’elenco degli Allievi assegnati alla competenza. |
| Numero di utenti che devono possedere questa abilità | Mai vuoto | Numero di Allievi assegnati alla competenza. |
| Numero di utenti che hanno acquisito questa competenza | Mai vuoto | Numero di Allievi che hanno acquisito la competenza. |
| Numero di Allievi la cui competenza deve essere aggiornata | Mai vuoto | Numero di Allievi la cui competenza deve essere aggiornata. |
| Percentuale di conformità (in base alle competenze acquisite) | Mai vuoto | Percentuale di avanzamento dell’abilità assegnata. |

### Riepilogo competenze II

| Nome colonna | Tipo di valore | Descrizione |
|---|---|---|
| Dopo | Mai vuoto | Numero di Allievi che hanno acquisito l’abilità prima del numero di giorni inserito (valore) che deve essere aggiornato. |
| Abilità | Tutti o qualsiasi nome dell’abilità | I nomi delle competenze assegnate agli Allievi. |
| Nome del manager | Mai vuoto | Il nome del manager dei subordinati i cui dati sul coinvolgimento sono visualizzati nella tabella di riepilogo dell’abilità. |
| Etichette righe | Mai vuoto | Il nome dell’Allievo con l’elenco di abilità assegnate. |
| Numero di abilità che ogni utente deve avere | Mai vuoto | Numero di abilità assegnate all’allievo. |
| Numero di abilità di ogni utente | Mai vuoto | Numero di abilità acquisite dall’Allievo. |
| Numero di abilità da aggiornare | Mai vuoto | Numero di Allievi la cui competenza deve essere aggiornata. |
| Percentuale di conformità | Mai vuoto | Percentuale di avanzamento dell’abilità assegnata. |

* A volte gli amministratori possono contrassegnare manualmente il completamento di un oggetto di apprendimento (in particolare per i corsi in aula) molto dopo la classe. In questo scenario, se l’opzione Esporta dati è impostata per esportare LT giornalmente, la data effettiva di completamento potrebbe essere già trascorsa e quindi l’esportazione non riceverà mai i record di completamento contrassegnati come completati molto tempo dopo che è avvenuta la classe. Quando questo viene rilevato, considera l’esportazione della trascrizione da una data di inizio specificata fino alla data (su richiesta) nell’interfaccia utente; quindi portala nell’applicazione a valle per &quot;elaborazione in ritardo&quot;. Durante questa operazione potresti dover ignorare i record che sono già stati elaborati.
* I tentativi multipli per un modulo dipendono dall’abilitazione o meno di tale LO. Quando questa opzione è attivata, ciò che ora viene visualizzato in una riga CSV relativa a un modulo è un tentativo. Non tutti i tentativi in un giorno possono essere segnalati, quindi è possibile visualizzare il numero totale di tentativi e vedere l’incremento di più di un tentativo. Anche un tentativo non necessariamente migliora un punteggio, e in qualsiasi momento si otterrà solo il punteggio migliore.
