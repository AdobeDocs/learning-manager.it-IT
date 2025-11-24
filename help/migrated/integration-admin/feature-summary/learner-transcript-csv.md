---
jcr-language: en_us
title: Interpretazione del CSV Trascrizione Allievo
description: Interpretazione del CSV Trascrizione Allievo
contentowner: saghosh
preview: true
source-git-commit: fcc50e80f94bdcbc8de2cddac92f1a12b55e1e18
workflow-type: tm+mt
source-wordcount: '2997'
ht-degree: 88%

---



# Interpretazione del CSV Trascrizione Allievo

Trascrizione Allievo è uno dei report più diffusi utilizzati in Adobe Learning Manager. Il report consente di ottenere quasi tutti i dettagli possibili in un unico report in formato CSV.

Il report, oltre a essere utilizzato dagli utenti per recuperare, monitorare e analizzare i comportamenti di apprendimento, può anche essere visualizzato nel formato impostato da Learning Manager per esportare i dati sui comportamenti di apprendimento in applicazioni/sistemi esterni.

Uno scenario aziendale tipico consiste nell’esportare periodicamente la trascrizione degli allievi per Learning Manager, analizzarla per estrarre gli allievi che completano un importante programma di apprendimento e ordinare un buono come premio per le attività completate per tempo.

Un altro caso di utilizzo consiste nell’aggiungere i dati sul comportamento dell’apprendimento a un data warehouse aziendale, dove è possibile combinare i dati di apprendimento con altri dati aziendali per analizzare le correlazioni tra il comportamento dell’apprendimento e altri dati di processo.

Nel resto del documento, descriviamo brevemente in che modo è possibile recuperare la Trascrizione Allievo da Learning Manager. Passeremo quindi a fornire i dettagli su come interpretare ogni riga e colonna del report.

Queste informazioni possono essere utili per qualsiasi sviluppatore che intenda integrare Learning Manager con altri sistemi elaborando i dati di Trascrizione Allievo esportati.

## Recupero di Trascrizione Allievo dall’interfaccia utente {#fetchlearnertranscriptfromtheuserinterface}

L’allievo può scaricare la propria trascrizione da Impostazioni profilo. Per ulteriori informazioni, consulta ***[Download della trascrizione Allievo](/help/migrated/administrators/feature-summary/reports/learner-transcripts.md)***.

Gli amministratori possono generare Trascrizioni Allievi per l’intera organizzazione, un set specifico di utenti o un set specifico di oggetti di apprendimento oppure un set specifico di utenti e oggetti di apprendimento. Possono inoltre ottenere tutti i record di apprendimento relativi a un intervallo di tempo e indicare se sono necessarie informazioni a livello di modulo (per impostazione predefinita, le informazioni a livello di modulo vengono omesse). Per ulteriori dettagli, consultare [***Scarica Trascrizioni Allievi***](/help/migrated/administrators/feature-summary/reports/learner-transcripts.md).

<!--Update above link?-->

Gli amministratori possono inoltre impostare il sistema in modo che invii periodicamente un messaggio e-mail contenente Trascrizione Allievo.

La Trascrizione Allievo generata tramite l’interfaccia utente sarà un file Excel, che contiene anche la &quot;Trascrizione abilità&quot;. In questo documento, ci riferiremo a ciò che viene generato nel formato CSV, un report contenente le attività di apprendimento relative all’iscrizione, all’avvio, all’avanzamento o al completamento di un oggetto di apprendimento.

## Esportazione di Trascrizione Allievo {#exportlearnertranscript}

Quando la Trascrizione Allievo deve essere utilizzata da un sistema esterno, Learning Manager fornisce una funzione denominata Esporta dati, in cui Trascrizione Allievo è uno dei tipi di dati che è possibile esportare. Come spiegato nel Preambolo, ciò è necessario per l’integrazione di Learning Manager con un sistema esterno che deve elaborare i dati relativi al comportamento di apprendimento o per popolare un data warehouse aziendale con i dati sul comportamento di apprendimento.

Per informazioni dettagliate sui connettori che supportano l’esportazione della Trascrizione Allievo, consultare la sezione [Esportazione di dati](/help/migrated/integration-admin/feature-summary/connectors.md) in connettori FTP, Box e PowerBI.

Lo scopo di questi connettori è quello di esportare periodicamente i dati in un’applicazione downstream (una volta in N giorni). Quindi, questi connettori esportano solo i dati del comportamento di apprendimento incrementale in ogni fase. Tieni presente che questi connettori non consentono di recuperare i record relativi a un sottoinsieme specifico di utenti o oggetti di apprendimento: si tratta sempre di dati su tutti gli utenti e su tutti gli oggetti di apprendimento in quell’account.

Nel caso di Power BI, il cliente deve fornire un’area di lavoro in cui Learning Manager possa continuare a esportare questi dati in modo incrementale in un set di dati creato dinamicamente. Questo connettore esporta solo i dati e i clienti devono creare i propri report/dashboard in base a questo set di dati.

La sezione seguente fornisce i dettagli su come un sistema downstream deve interpretare i record della Trascrizione Allievo.

## Interpretazione della Trascrizione Allievo {#interpretthelearnertranscript}

Ogni riga di una Trascrizione Allievo può essere considerata come un comportamento di apprendimento acquisito in Learning Manager in un periodo di tempo specifico. In genere, i connettori esportano &quot;dati incrementali&quot; e quindi le righe rappresentano le attività di apprendimento che si sono svolte tra l’ultima esecuzione del connettore e l’esecuzione corrente.

Naturalmente, i connettori consentono anche di recuperare la trascrizione allievo su richiesta e, in questo caso, l’utente può specificare una data di avvio mentre la data di fine si presume sia quella corrente. Di solito si esegue questa operazione solo inizialmente, quindi si imposta il connettore per l’esportazione della trascrizione allievo incrementale a un’ora specifica del giorno, una volta in N giorni (il valore predefinito N è 1).

Definiamo ora cosa si intende per trascrizione allievo incrementale

Nella Trascrizione Allievo, ogni riga rappresenta un’attività specifica che coinvolge un allievo specifico e un oggetto di apprendimento specifico. Siamo interessati principalmente allo stato di un Allievo in relazione all’oggetto di apprendimento: **Iscritto**, **Avviato**, **In corso** e **Completato**. Pertanto, la Trascrizione Allievo cattura anche quattro date corrispondenti.

Ora esistono tre tipi di oggetti di apprendimento, in cui Learning Manager tiene traccia dell’avanzamento dell’Allievo, e i dati esportati contengono informazioni sull’avanzamento a livello di modulo, che è l’unità di contenuto più granulare che un Allievo può provare in Learning Manager.

* **Corso** - una composizione di uno o più moduli
* **Programma di apprendimento** - una composizione di uno o più corsi
* **Certificazione**: una composizione di uno o più corsi.

Ogni riga della Trascrizione Allievo riguarda il coinvolgimento di un utente specifico in un modulo, corso, programma di apprendimento o certificazione. Quando un utente è iscritto a un programma di apprendimento, la trascrizione indica che l’utente è

Le colonne della Trascrizione Allievo forniscono varie informazioni relative a ciascuna attività di apprendimento e le tabelle seguenti descrivono la semantica di ogni colonna.

## Trascrizione Allievo

<table> 
 <tbody> 
  <tr> 
   <th width="158" valign="bottom"><p><b>Nome Colonna</b></p></th> 
   <th width="160" valign="bottom"><p><b>Tipo di valore</b></p></th> 
   <th width="306" valign="bottom"><p><b>Descrizione</b></p></th> 
  </tr> 
  <tr> 
   <td><p><b>Nome</b></p></td> 
   <td><p>Mai vuoto</p></td> 
   <td><p>Nome dell’Allievo</p></td> 
  </tr> 
  <tr> 
   <td><p><b>e-mail</b></p></td> 
   <td><p>Mai vuoto</p></td> 
   <td><p>Indirizzo e-mail dell’allievo</p></td> 
  </tr> 
  <tr> 
   <td valign="bottom"><b>Adobe ID</b></td> 
   <td valign="bottom">Può essere vuoto</td> 
   <td valign="bottom">ID Adobe dell’Allievo</td> 
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
   <td valign="middle"><p>Il tipo di oggetto di apprendimento cui l’utente iscritto.</p></td> 
  </tr> 
  <tr> 
   <td valign="middle"><p><b>Corso</b></p></td> 
   <td valign="middle"><p>Può essere vuoto</p></td> 
   <td valign="middle">Nome del corso in cui l’utente è iscritto. Quando è vuoto, la riga rappresenta un programma di certificazione o di apprendimento. </td> 
  </tr> 
  <tr> 
   <td height="19" width="283"><b>ID univoco LO</b></td> 
   <td height="19" width="283">Può essere vuoto</td> 
   <td height="19" width="728">ID univoco dell’oggetto di apprendimento LO Questa colonna si basa sull’impostazione, abilitata/disabilitata a livello di account</td> 
  </tr> 
  <tr> 
   <td valign="middle"><p><b>Istanza  </b></p></td> 
   <td valign="middle">Mai vuoto</td> 
   <td valign="middle">Il nome dell’istanza dell’oggetto di apprendimento cui l’utente è iscritto. </td> 
  </tr> 
  <tr> 
   <td valign="middle"><p><b>Criteri di selezione</b></p></td> 
   <td valign="middle"><p>Mai vuoto</p></td> 
   <td valign="middle"><p>Base dell’iscrizione (come l’allievo è stato iscritto all’oggetto di apprendimento).</p></td> 
  </tr> 
  <tr> 
   <td valign="middle"><p><b>Modulo</b></p></td> 
   <td valign="middle"><p>Può essere vuoto</p></td> 
   <td valign="middle">Nome del modulo all’interno dei Corsi. Quando questa riga è vuota rappresenta un corso, un programma di apprendimento o una certificazione.</td> 
  </tr> 
  <tr> 
   <td height="19" width="283"><b>Versione</b></td> 
   <td height="19" width="283">Può essere vuoto</td> 
   <td height="19" width="728">Versione del modulo</td> 
  </tr> 
  <tr> 
   <td height="19" width="283"><b>Tipo di erogazione</b></td> 
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
   <td height="19" width="728">Commenti aggiunti dall’Amministratore, istruttore dell’Allievo mentre segna la presenza dell’utente.</td> 
  </tr> 
  <tr> 
   <td height="19" width="283"><b>Data iscrizione (fuso orario Asia/Calcutta)</b></td> 
   <td height="19" width="283">Mai vuoto</td> 
   <td height="19" width="728">Data di iscrizione dell’Allievo al tipo di LO.</td> 
  </tr> 
  <tr> 
   <td height="19" width="283"><b>Data di inizio (fuso orario Asia/Calcutta)</b></td> 
   <td><p>Può essere vuoto</p></td> 
   <td height="19" width="728">Data in cui lo studente ha avviato l’LO. Se il campo è vuoto significa che l’allievo non ha ancora iniziato l’attività.</td> 
  </tr> 
  <tr> 
   <td height="19" width="283"><b>Data di completamento (fuso orario Asia/Calcutta)</b></td> 
   <td><p>Può essere vuoto</p></td> 
   <td><p>Data di completamento dell’allievo. Se il campo è vuoto significa che l’Allievo non ha ancora completato l’attività.</p></td> 
  </tr> 
  <tr> 
   <td height="19" width="283"><b>Scadenza (fuso orario Asia/Calcutta)</b></td> 
   <td><p>Può essere vuoto</p></td> 
   <td height="19" width="728">Data entro la quale l’Allievo deve completare l’LO. Se il campo è vuoto significa che non esiste una scadenza per l’attività.</td> 
  </tr> 
  <tr> 
   <td height="19" width="283"><b>Scaduta</b></td> 
   <td height="19" width="283">Sì/No</td> 
   <td height="19" width="728">Stato di ritardo corrente dell’Allievo iscritto all’LO. Sì/No</td> 
  </tr> 
  <tr> 
   <td valign="middle"><p><b>Stato</b></p></td> 
   <td valign="middle">Non avviato/Completato/In corso/Non registrato</td> 
   <td valign="middle">% avanzamento corrente dell’Allievo iscritto all’LO.</td> 
  </tr> 
  <tr> 
   <td valign="middle"><p><b>% di avanzamento</b></p></td> 
   <td valign="middle">Può essere vuoto</td> 
   <td valign="middle"><p>Indica in che misura l’Allievo ha completato l’attività.</p></td> 
  </tr> 
  <tr> 
   <td height="38" width="283"><b>Tempo trascorso (minuti)</b></td> 
   <td height="38" width="283">Può essere vuoto</td> 
   <td height="38" width="728">Il tempo di apprendimento impiegato dall’Allievo nell’LO, le righe a livello di modulo mostrano il tempo di apprendimento dedicato al singolo modulo. Le righe a livello di corso/programma/certificato mostrano il tempo di apprendimento aggregato impiegato.</td> 
  </tr> 
  <tr> 
   <td valign="middle"><p><b>Valutazione</b></p></td> 
   <td valign="middle">Superata/Non superata</td> 
   <td valign="middle">Indica l’esito dell’attività dell’Allievo. ‘Superata’ indica che l’utente ha soddisfatto i criteri di successo, altrimenti la valutazione è “Non superata”.</td> 
  </tr> 
  <tr> 
   <td valign="middle"><p><b>Punteggio quiz</b></p></td> 
   <td valign="middle">Può essere vuoto</td> 
   <td valign="middle">L’ultimo punteggio al quiz ottenuto dall’Allievo. Può essere vuoto, se l’Allievo non ha tentato il quiz o se il contenuto non include quiz o se l’Amministratore/Istruttore non ha assegnato alcun punteggio.</td> 
  </tr> 
  <tr> 
   <td height="38" width="283"><b>Quiz_score_max</b></td> 
   <td height="38" width="283">Può essere vuoto</td> 
   <td height="38" width="728">L’ultimo punteggio massimo del quiz per il modulo. Può essere vuoto se lo studente non ha tentato il quiz o se il contenuto non contiene alcun quiz.</td> 
  </tr> 
  <tr> 
   <td height="38" width="283"><b>Highest_Quiz_score</b></td> 
   <td height="38" width="283">Può essere vuoto</td> 
   <td height="38" width="728">Il punteggio più alto del quiz ottenuto dall’Allievo dopo vari tentativi. Può essere vuoto, se l’Allievo non ha tentato il quiz o se il contenuto non include quiz o se l’Amministratore/Istruttore non ha assegnato alcun punteggio.</td> 
  </tr> 
  <tr> 
   <td height="38" width="283"><b>Highest_Quiz_score_max</b></td> 
   <td height="38" width="283">Può essere vuoto</td> 
   <td height="38" width="728">Il punteggio più alto possibile del quiz per il modulo. Può essere vuoto se lo studente non ha tentato il quiz o se il contenuto non contiene alcun quiz.</td> 
  </tr> 
  <tr> 
   <td height="19" width="283"><b>Tentativi effettuati</b></td> 
   <td height="19" width="283">Può essere vuoto</td> 
   <td height="19" width="728">Numero totale di tentativi compiuti dall’Allievo per questo modulo.</td> 
  </tr> 
  <tr> 
   <td height="19" width="283"><b>Numero massimo di tentativi consentiti</b></td> 
   <td height="19" width="283">Può essere vuoto</td> 
   <td height="19" width="728">Numero massimo di tentativi consentiti per l’Allievo per poter utilizzare il modulo.</td> 
  </tr> 
  <tr> 
   <td valign="middle"><p><b>userState</b></p></td> 
   <td valign="middle">Mai vuoto</td> 
   <td valign="middle">Stato utente dell’Allievo: Attivo/Eliminato/Sospeso.</td> 
  </tr> 
  <tr> 
   <td height="38" width="283"><b>Campo attivo raggruppabile</b></td> 
   <td height="38" width="283">Può essere vuoto</td> 
   <td height="38" width="728">Per ogni campo attivo raggruppabile dell’account, sarà presente una colonna, con il nome Campo attivo, e il valore sarà il valore specifico dell’allievo per quel campo.</td> 
  </tr> 
  <tr> 
   <td><p><b>Nome del manager</b></p></td> 
   <td><p><i>Può essere vuoto</i></p></td> 
   <td height="19" width="728">Nome del manager dell’Allievo</td> 
  </tr> 
  <tr> 
   <td height="38" width="283"><b>Conteggio delle iscrizioni</b></td> 
   <td height="38" width="283">1 o 0</td> 
   <td height="38" width="728">Conteggio iscrizioni dell’Allievo per l’LO. La riga LO di livello più alto mostra un valore = “1”. I corsi di formazione secondari mostrano un valore pari a 0.</td> 
  </tr> 
  <tr> 
   <td height="19" width="283"><b>Conteggio avviato</b></td> 
   <td height="19" width="283">1 o 0</td> 
   <td height="19" width="728">Conteggio avviato dell’Allievo per l’LO. La riga LO di livello più alto mostra un valore = “1”. I corsi di formazione secondari mostrano un valore pari a 0.</td> 
  </tr> 
  <tr> 
   <td height="58" width="283"><b>Conteggio completamento</b></td> 
   <td height="58" width="283">1 o 0</td> 
   <td height="58" width="728">Conteggio completamento dell’Allievo per l’LO. La riga LO di livello più alto mostra un valore = “1” se l’Allievo è in attesa di completare il corso di formazione. I corsi di formazione secondari mostrano un valore pari a 0 se lo stato è In sospeso. La riga LO di livello più alto mostra un valore = “0”, se l’Allievo ha completato il corso di formazione.</td> 
  </tr> 
  <tr> 
   <td height="38" width="283"><b>Scadenza tra N giorni</b></td> 
   <td height="38" width="283">1 o 0</td> 
   <td height="38" width="728">In questo modo viene visualizzato un valore di “1” o “0” a seconda della scadenza del corso di formazione al quale è iscritto l’Allievo. Dipende dal valore immesso nel campo “Data di scadenza prevista in” del foglio I del riepilogo di apprendimento.</td> 
  </tr> 
  <tr> 
   <td height="38" width="283"><b>Scadenza tra N giorni per l’utente</b></td> 
   <td height="38" width="283">1 o 0</td> 
   <td height="38" width="728">In questo modo viene visualizzato un valore di “1” o “0” a seconda della scadenza del corso di formazione al quale è iscritto l’Allievo. Dipende dal valore immesso nel campo “Data di scadenza prevista in” del foglio II del riepilogo di apprendimento.</td> 
  </tr> 
  <tr> 
   <td height="38" width="283"><b>Conteggio di (avanzamento superiore al N%)</b></td> 
   <td height="38" width="283">1 o 0</td> 
   <td height="38" width="728">In questo modo viene visualizzato un valore di “1” o “0” a seconda dell’avanzamento dell’Allievo nel corso di formazione. Dipende dal valore immesso nel campo “Avanzamento superiore a” del foglio I del riepilogo di apprendimento.</td> 
  </tr> 
  <tr> 
   <td height="38" width="283"><b>Conteggio di (avanzamento superiore al N%) per l’utente</b></td> 
   <td height="38" width="283">1 o 0</td> 
   <td height="38" width="728">In questo modo viene visualizzato un valore di “1” o “0” a seconda dell’avanzamento dell’Allievo nel corso di formazione. Dipende dal valore immesso nel campo “Avanzamento superiore a” del foglio II del riepilogo di apprendimento.</td> 
  </tr> 
  <tr> 
   <td height="19" width="283">ID f<b>ormazione</b></td> 
   <td height="19" width="283">Mai vuoto</td> 
   <td height="19" width="728">ID formazione del corso di formazione.</td> 
  </tr> 
  <tr> 
   <td height="20" width="283"><b>Durata del corso di formazione o del modulo (minuti)</b></td> 
   <td height="20" width="283">Mai vuoto</td> 
   <td height="20" width="728">Durata del corso di formazione o del modulo totale (minuti) dell’istanza predefinita del corso di formazione.</td> 
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
   <td height="38" width="412">Il nome del manager dei subordinati i cui dati sul coinvolgimento nell’LO sono mostrati sulla tabella di riepilogo dell’apprendimento.</td> 
  </tr> 
  <tr> 
   <td height="19" width="264">Titoli delle righe</td> 
   <td height="19" width="253">Mai vuoto</td> 
   <td height="19" width="412">Nome LO con l’elenco degli Allievi iscritti all’LO.</td> 
  </tr> 
  <tr> 
   <td height="19" width="264">Numero di studenti iscritti</td> 
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
| Nome del manager | Mai vuoto | Il nome del manager dei subordinati i cui dati sul coinvolgimento nell’LO sono mostrati sulla tabella di riepilogo dell’apprendimento. |
| Titoli delle righe | Mai vuoto | Il nome dell’Allievo con l’elenco degli LO a cui è iscritto l’Allievo. |
| Numero di oggetti di apprendimento a cui è iscritto | Mai vuoto | Numero di oggetti di apprendimento a cui è iscritto. |
| Numero di oggetti di apprendimento avviati | Mai vuoto | Numero di oggetti di apprendimento avviati. |
| Numero di oggetti di apprendimento completati | Mai vuoto | Numero di oggetti di apprendimento completati. |
| Numero di oggetti di apprendimento con avanzamento >= N% | Mai vuoto | Il numero di oggetti di apprendimento in cui l’Allievo ha fatto progressi >= N%. |
| Numero di oggetti di apprendimento con data di scadenza tra N giorni | Mai vuoto | Numero di oggetti di apprendimento con data di scadenza tra N giorni. |

### Riepilogo conformità

| Nome colonna | Tipo di valore | Descrizione |
|---|---|---|
| Tipo | Tutto, Programma di apprendimento, Certificato, Corso. | Tipo di LO per il quale la tabella Riepilogo apprendimento deve visualizzare i dati. |
| Etichette righe (colonna laterale sinistra) | Mai vuoto | Il nome dell’Allievo con l’elenco degli LO a cui è iscritto l’Allievo. |
| Etichette righe (colonna laterale sinistra) | Mai vuoto | Il nome dell’Allievo con l’elenco degli LO a cui è iscritto l’Allievo. |

### Trascrizione competenza

| .Nome colonna | Tipo di valore | Descrizione |
|---|---|---|
| Nome | Mai vuoto | Nome dell’Allievo |
| e-mail | Mai vuoto | Indirizzo e-mail dell’allievo |
| Adobe ID | Può essere vuoto | ID Adobe dell’Allievo |
| ID univoco utente | Può essere vuoto | ID univoco utente dell’Allievo. Questa colonna si basa sull’impostazione back-end, abilitata o disabilitata a livello di account. |
| Competenza | Mai vuoto | Nome competenza assegnata all’Allievo. |
| Livello di abilità | Mai vuoto | Livello di abilità assegnato all’Allievo. |
| Crediti richiesti | Mai vuoto | Totale crediti richiesti dall’Allievo per ottenere la competenza. |
| Crediti guadagnati | Mai vuoto | Totale crediti guadagnati dall’Allievo per la competenza. |
| Percentuale completamento | Mai vuoto | Percentuale di avanzamento per raggiungere la competenza. |
| Data di assegnazione (fuso orario UTC) | Mai vuoto | Data in cui la competenza è stata assegnata all’Allievo. |
| Data di conseguimento (fuso orario UTC) | Mai vuoto | Data in cui l’Allievo ha raggiunto la competenza. |
| userState | Mai vuoto | Stato utente dell’Allievo: Attivo/Eliminato/Sospeso. |
| Campo attivo raggruppabile | Può essere vuoto | Per ogni campo attivo raggruppabile dell’account, sarà presente una colonna, con il nome Campo attivo, e il valore sarà il valore specifico dell’allievo per quel campo. |
| Nome del manager | Può essere vuoto | Nome dell’Allievo del manager |

### Riepilogo competenze I

| Nome colonna | Tipo di valore | Descrizione |
|---|---|---|
| Dopo | Mai vuoto | Numero di allievi che hanno acquisito la competenza prima del numero di giorni inserito (valore) che deve essere aggiornato. |
| Nome | Tutti o qualsiasi nome degli Allievi | Nome dell’Allievo a cui è stata assegnata una competenza. |
| Nome del manager | Mai vuoto | Il nome del manager dei subordinati i cui dati sul coinvolgimento sono mostrati sulla tabella di riepilogo dell’abilità. |
| Titoli delle righe | Mai vuoto | Il nome della competenza con l’elenco degli Allievi assegnati alla competenza. |
| Numero di utenti che dovrebbero possedere questa competenza | Mai vuoto | Numero di Allievi assegnati alla competenza. |
| Numero di utenti che hanno conseguito questa competenza | Mai vuoto | Numero di Allievi che hanno conseguito la competenza. |
| Numero di Allievi la cui competenza deve essere aggiornata | Mai vuoto | Numero di Allievi la cui competenza deve essere aggiornata. |
| Percentuale di conformità (in base alle competenze acquisite) | Mai vuoto | Percentuale di avanzamento dell’abilità assegnata. |

### Riepilogo competenze II

| Nome colonna | Tipo di valore | Descrizione |
|---|---|---|
| Dopo | Mai vuoto | Numero di Allievi che hanno acquisito l’abilità prima del numero di giorni inserito (valore) che deve essere aggiornato. |
| Competenza | Tutti o qualsiasi nome delle competenze | I nomi delle competenze assegnate agli Allievi. |
| Nome del manager | Mai vuoto | Il nome del manager dei subordinati i cui dati sul coinvolgimento sono mostrati sulla tabella di riepilogo dell’abilità. |
| Titoli delle righe | Mai vuoto | Il nome dell’allievo con l’elenco di abilità assegnate. |
| Numero di abilità che ogni utente dovrebbe avere | Mai vuoto | Numero di abilità assegnate all’allievo. |
| Numero di abilità di ogni utente | Mai vuoto | Numero di abilità acquisite dall’allievo. |
| Numero di abilità che devono essere aggiornate | Mai vuoto | Numero di Allievi la cui competenza deve essere aggiornata. |
| Percentuale di conformità | Mai vuoto | Percentuale di avanzamento dell’abilità assegnata. |

* A volte gli amministratori possono contrassegnare manualmente il completamento di un oggetto di apprendimento (in particolare per i corsi della classe) molto dopo la lezione. In questo scenario, se l’opzione Esporta dati è impostata per l’esportazione di dati LT giornalieri, la data effettiva di completamento potrebbe essere già passata, quindi l’esportazione non otterrà mai record di completamento contrassegnati come completati molto dopo la lezione. Quando questo viene rilevato, considera l’esportazione della trascrizione da una data di inizio specificata fino alla data (su richiesta) nell’interfaccia utente; quindi portala nell’applicazione a valle per &quot;elaborazione in ritardo&quot;. Durante questa operazione potresti dover ignorare i record che sono già stati elaborati.
* L’opzione Tentativi multipli è possibile se il modulo è abilitato per l’oggetto di apprendimento. Quando questa opzione è attivata, ciò che viene visualizzato in una riga CSV relativa a un modulo è un tentativo. Non tutti i tentativi di un giorno possono essere segnalati, pertanto è possibile che il numero totale di tentativi venga visualizzato in incrementi di più di uno. Inoltre, i tentativi non necessariamente migliorano il punteggio, quindi in un dato punto si otterrà solo il punteggio migliore.
