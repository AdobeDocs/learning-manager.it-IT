---
description: Manuale di riferimento per gli Amministratori di integrazione che desiderano eseguire la migrazione di un LMS esistente a Adobe Learning Manager LMS.
jcr-language: en_us
title: Manuale di migrazione
exl-id: bfdd5cd8-dc5c-4de3-8970-6524fed042a8
source-git-commit: 0ae0dee3a43108b707e13778edbc7367c67d63e3
workflow-type: tm+mt
source-wordcount: '5322'
ht-degree: 61%

---

# Manuale di migrazione

Manuale di riferimento per gli Amministratori di integrazione che desiderano eseguire la migrazione di un LMS esistente all’LMS di Learning Manager

<!-- ## Overview {#overview} -->

## Scenario di utilizzo {#usagescenario}

In generale, le aziende di grandi dimensioni dispongono di un proprio LMS interno o di un sistema di gestione dell’apprendimento legacy fornito da un qualsiasi rivenditore. Un LMS è costituito dai contenuti e dai dati di formazione dell’azienda. Quando un’azienda acquista Learning Manager, potrebbe essere nel suo interesse trasferire i contenuti e i dati LMS esistenti a Learning Manager in modo da sfruttare i vantaggi offerti da un LMS moderno e intuitivo senza perdere i propri dati legacy.

Learning Manager fornisce le specifiche e gli strumenti necessari in modo che l’Amministratore di integrazione dell’organizzazione sia in grado di configurare ed eseguire le attività di migrazione.

A partire da oggi, gli Amministratori di un’organizzazione possono accedere alla funzionalità di migrazione in Learning Manager contattando il team di supporto di Adobe. Per abilitare la funzionalità di migrazione nel tuo account, puoi rivolgerti al team di supporto di Adobe Learning Manager.

## Processo di migrazione {#apidescription}

I prerequisiti per la migrazione, i passaggi chiave del processo di migrazione, gli sprint di migrazione, le specifiche, i passaggi per la migrazione dei dati e dei contenuti sono spiegati in questa sezione come esposto di seguito:

### Importante avviso sulla migrazione

Tenere presente che le tempistiche della migrazione dipendono in larga misura dalla qualità e dalle dimensioni dei dati. Se hai bisogno di migrazione durante l&#39;onboarding, pianifica questa attività con largo anticipo e collabora strettamente con il team di onboarding di Adobe Learning Manager per evitare ritardi.

### Prerequisiti {#prerequisites}

Il team di Adobe Learning Manager prevede che gli Amministratori di integrazione dell’organizzazione effettuino le seguenti operazioni prima di intraprendere il processo di migrazione:

* L’Amministratore di integrazione estrae dati e contenuti dall’LMS in uso e trasforma i dati nei formati di file definiti da Learning Manager.
* Learning Manager non supporta l’importazione di utenti nell’ambito del processo di migrazione e prevede che l’importazione di utenti venga eseguita dall’organizzazione mediante connettori. Adobe Systems prevede che i connettori vengano configurati prima del processo di migrazione. Per ulteriori informazioni, fai riferimento alla funzione [Guida ai connettori di Learning Manager](connectors.md).

Learning Manager consiglia agli Amministratori di provare a eseguire il processo di migrazione in un account di prova prima di migrare dati e contenuti all’ambiente di produzione di Learning Manager.

### Passaggi chiave del processo di migrazione {#keystepsofmigrationprocess}

I passaggi chiave del processo di migrazione di contenuti e dati da un LMS esistente a Learning Manager sono i seguenti:

1. Il partner o l’Amministratore di integrazione valuta i dati e i contenuti LMS esistenti di cui deve essere eseguita la migrazione.
1. L’Amministratore di integrazione valuta gli strumenti e le specifiche forniti da Learning Manager per l’inserimento di dati e contenuti.
1. L’Amministratore di integrazione scrive il codice o esporta manualmente dati e contenuti di formazione dall’LMS precedente sulla base delle funzionalità fornite dall’LMS precedente.
1. Una volta che i dati e i contenuti di formazione sono disponibili, l’Amministratore di integrazione analizza e mappa dati e contenuti in modo che siano in linea con le specifiche di migrazione di Learning Manager.
1. L’Amministratore di integrazione utilizza gli strumenti forniti da Learning Manager per eseguire la migrazione nel seguente ordine:

   1. Trasferimento degli Allievi a Learning Manager
   1. Trasferimento dei contenuti di formazione in Learning Manager e
   1. Infine, trasferimento dei dati di formazione a Learning Manager.

L’organizzazione può iniziare a utilizzare l’LMS di Learning Manager insieme ai contenuti legacy.

### Area di validità degli oggetti di migrazione {#scopeofmigrationobjects}

È possibile migrare i contenuti solo per i seguenti oggetti di apprendimento:

* Modulo
* Distintivi
* Corso
* Versione modulo
* Istanza del corso
* Modulo del corso
* Abilità
* Livello di abilità
* Corso abilità
* Certificazione
* Corso per la certificazione
* Commit certificazione
* Programma di apprendimento
* Corso del programma di apprendimento
* Istanza del programma di apprendimento
* Istanza del corso del programma di apprendimento
* Risorsa formativa
* Versione risorsa formativa
* Corso risorsa formativa
* Abilità risorsa formativa
* Iscrizione
* Iscrizione certificazione
* Iscrizione programma di apprendimento
* Iscrizione risorsa formativa
* Valutazioni dei corsi degli utenti

### Concetti chiave della migrazione {#keyconceptsofmigration}

Di seguito sono illustrati brevemente alcuni dei concetti chiave del processo di migrazione di Learning Manager, per un riferimento rapido:

**Progetto di migrazione**

In Learning Manager, un progetto di migrazione è costituito da uno o più sprint. Puoi avviare anche più progetti di migrazione per il tuo account. Il processo di migrazione in Learning Manager inizia con la creazione di un progetto di migrazione.

**Sprint**

Nel processo di migrazione di Learning Manager, uno sprint definisce un insieme di elementi di migrazione che si desidera migrare dall’LMS esistente. Un elemento di migrazione può essere un modulo del corso, il record di un Allievo o un insieme di corsi. In uno sprint possono essere presenti anche più elementi dati di apprendimento. È possibile eseguire processi di migrazione in ciascuno sprint.

**Esecuzioni script**

Esecuzione script è il processo di avvio di un processo di migrazione sprint. È possibile interrompere l’esecuzione dello sprint in qualsiasi momento.

**Riesecuzioni script**

È possibile rieseguire uno sprint di migrazione in seguito al completamento dello stesso in qualsiasi momento. Questa situazione di riesecuzione di uno sprint si verifica quando si desidera aggiungere i dati a una voce sprint ed eseguirne nuovamente la migrazione all’applicazione o correggere gli errori nei CSV.

**Specifica CSV**

Learning Manager offre un set di [specifiche CSV standard](migration-manual.md#main-pars_header_140933605). È consigliabile prendere visione delle specifiche CSV prima di avviare il processo di migrazione. L’Amministratore di integrazione della tua organizzazione può analizzare i formati di dati esistenti e mapparli in modo che corrispondano agli elementi del modello CSV forniti da Learning Manager.

**Tag progetto di migrazione**

Adobe Systems consiglia di utilizzare una serie di parole chiave come tag per identificare facilmente i progetti di migrazione all’interno dell’applicazione Learning Manager. Questi tag consentono di identificare i progetti all’interno dell’applicazione Learning Manager in qualsiasi momento.

**Modulo senza contenuto**

Learning Manager consente di caricare un modulo senza contenuto. Adobe Systems lo considera come modulo senza contenuto in Learning Manager. Per eseguire la migrazione di alcuni dati legacy dall’LMS esistente senza la necessità di alcun contenuto, è possibile caricare il file module_version.csv senza riferimento URL.

## Specifiche CSV e CSV di esempio {#csv}

Di seguito sono riportate le specifiche CSV aggiornate che puoi utilizzare per mappare i dati di migrazione LMS esistenti. Fai clic su csv-specifications e sample-csvs per scaricare i file zip. Il file csv-specific.zip scaricato contiene sette fogli Excel. I file Excel contengono specifiche accompagnate da descrizioni che illustrano come compilare i file .csv. I file .csv corrispondenti devono contenere i dati per ciascun campo nel formato prestabilito, come spiegato in questi file .xlsx.

<table border="1" cellspacing="0" cellpadding="0" width="100%">
 <tbody>
  <tr>
   <th>
    <p><b>Sl.no</b></p></th>
   <th>
    <p><b>Nome file</b></p></th>
   <th>
    <p><b>Descrizione dei contenuti</b></p></th>
   <th>
    <p>Note</p></th>
  </tr>
  <tr>
   <td>
    <p>1</p></td>
   <td>
    <p>module.xlsx</p></td>
   <td>
    <p>Metadati per module.csv</p></td>
   <td> </td>
  </tr>
  <tr>
   <td>
    <p>2</p></td>
   <td>
    <p>badge.xlsx</p></td>
   <td>
    <p>Metadati per badge.xlsx</p></td>
   <td> </td>
  </tr>
  <tr>
   <td>
    <p>3</p></td>
   <td>
    <p>course.xlsx</p></td>
   <td>
    <p>Metadati per course.csv</p></td>
   <td>
    <p>Indica il nome di un Autore per un determinato corso poiché a volte i nomi di più Autori non vengono visualizzati correttamente nell’applicazione in seguito alla migrazione. </p></td>
  </tr>
  <tr>
   <td>
    <p>4</p></td>
   <td>
    <p>module_version.xlsx </p></td>
   <td>
    <p>Metadati per module_version.csv</p></td>
   <td>
    <p>Assicurati di specificare il percorso URL della cartella dell’account Box in cui hai caricato il contenuto. </p></td>
  </tr>
  <tr>
   <td>
    <p>5</p></td>
   <td>
    <p>course_instance.xlsx</p></td>
   <td>
    <p>Metadati per course_instance.csv </p></td>
   <td> </td>
  </tr>
  <tr>
   <td>
    <p>6</p></td>
   <td>
    <p>session.xlsx</p></td>
   <td>
    <p>Metadati per session.csv</p></td>
   <td>
    <p>Assicurati che ogni voce nel documento session.csv sia associata ad almeno un modulo Classe/Classe virtuale</p></td>
  </tr>
  <tr>
   <td>
    <p>7</p></td>
   <td>
    <p>course_module.xlsx</p></td>
   <td>
    <p>Metadati per course_module.csv</p></td>
   <td> </td>
  </tr>
  <tr>
   <td>
    <p>8</p></td>
   <td>
    <p>skill.xlsx</p></td>
   <td>
    <p>Metadati per skill.csv</p></td>
   <td> </td>
  </tr>
  <tr>
   <td>
    <p>9</p></td>
   <td>
    <p>skill_level.xlsx</p></td>
   <td>
    <p>Metadati per skill_level.csv</p></td>
   <td> </td>
  </tr>
  <tr>
   <td>
    <p>10</p></td>
   <td>
    <p>skill_course.xlsx</p></td>
   <td>
    <p>Metadati per skill_course.csv</p></td>
   <td> </td>
  </tr>
  <tr>
   <td>
    <p>11</p></td>
   <td>
    <p>certification.xlsx</p></td>
   <td>
    <p>Metadati per Certification.csv</p></td>
   <td> </td>
  </tr>
  <tr>
   <td>
    <p>12</p></td>
   <td>
    <p>certification_course.xlsx</p></td>
   <td>
    <p>Metadati per certification_course.csv</p></td>
   <td> </td>
  </tr>
  <tr>
   <td>
    <p>13</p></td>
   <td>
    <p>certification_commit.xlsx</p></td>
   <td>
    <p>Metadati per certification_commit.csv</p></td>
   <td> </td>
  </tr>
  <tr>
   <td>
    <p>14</p></td>
   <td>
    <p>learning_program.xlsx</p></td>
   <td>
    <p>Metadati per learning_program.csv</p></td>
   <td> </td>
  </tr>
  <tr>
   <td>
    <p>15</p></td>
   <td>
    <p>learning_program_course.xls </p></td>
   <td>
    <p>Metadati per learning_program_course.csv </p></td>
   <td> </td>
  </tr>
  <tr>
   <td>
    <p>16</p></td>
   <td>
    <p>learning_program_instance.xlsx </p></td>
   <td>
    <p>Metadati per learning_program_instance.csv</p></td>
   <td> </td>
  </tr>
  <tr>
   <td>
    <p>17</p></td>
   <td>
    <p>learning_program_instance_course_instance.xlsx </p></td>
   <td>
    <p>Metadati per learning_program_instance_course_instance.csv</p></td>
   <td> </td>
  </tr>
  <tr>
   <td>
    <p>18</p></td>
   <td>
    <p>job_aid.xlsx</p></td>
   <td>
    <p>Metadati per job_aid.csv</p></td>
   <td>
    <p>Ogni file job_aid migrato richiede la disponibilità di una o più versioni di job_aid.</p></td>
  </tr>
  <tr>
   <td>
    <p>19</p></td>
   <td>
    <p>Job_aid_version.xlsx</p></td>
   <td>
    <p>Metadati per job_aid_version.csv</p></td>
   <td> </td>
  </tr>
  <tr>
   <td>
    <p>20</p></td>
   <td>
    <p>job_aid_course.xlsx</p></td>
   <td>
    <p>Metadati per job_aid_course.csv</p></td>
   <td> </td>
  </tr>
  <tr>
   <td>
    <p>21</p></td>
   <td>
    <p>job_aid_skills.xlsx</p></td>
   <td>
    <p>Metadati per job_aid_skills.csv</p></td>
   <td> </td>
  </tr>
  <tr>
   <td>
    <p>22</p></td>
   <td>
    <p>iscrizioni</p></td>
   <td>
    <p>Metadati per enrollments.csv</p></td>
   <td> </td>
  </tr>
  <tr>
   <td>
    <p>23</p></td>
   <td>
    <p>certification_enrollement.xlsx</p></td>
   <td>
    <p>Metadati per certification_enrollement.csv</p></td>
   <td> </td>
  </tr>
  <tr>
   <td>
    <p>24</p></td>
   <td>
    <p>learning_program_enrollment.xlsx</p></td>
   <td>
    <p>Metadati per learning_program_enrollment.csv<br><br></p></td>
   <td> </td>
  </tr>
  <tr>
   <td>
    <p>25</p></td>
   <td>
    <p>job_aid_enrollment.xlsx</p></td>
   <td>
    <p>Metadati per job_aid_enrollment.csv</p></td>
   <td> </td>
  </tr>
  <tr>
   <td>
    <p>26</p></td>
   <td>
    <p>user_course_grade.xlsx</p></td>
   <td>
    <p><br>
      Metadati per user_course_grade.csv</p></td>
   <td>
    <p>Specifica i dati dei record Allievi richiesti nel file .csv anche se non sono obbligatori. Senza queste informazioni, anche se il file .csv viene elaborato per la migrazione, l’applicazione Learning Manager potrebbe non riflettere alcun dato. Il file sample-csvs.zip contiene sette file .csv con convenzione di denominazione simile a quanto riportato sopra.</p></td>
  </tr>
  <tr>
   <td>
    <p>27</p></td>
   <td>
    <p>user_skill.xlsx</p></td>
   <td>
    <p><br>
      metadati per user_skill.csv;</p></td>
   <td>
    <p> </p></td>
  </tr>
 </tbody>
</table>

Learning Manager supporta solo i valori di data e ora in formato UTF a 8 e 32 bit. È possibile che si verifichino errori durante la migrazione se nei file CSV viene indicata una data fuori intervallo come 2038-07-17T08:53:21.000Z o 1980-04-17T08:13:25.322Z.

* [sample-csvs.zip](assets/sample-csvs.zip)
* [csv_specific.zip](assets/csv-specifications.zip)

È necessario essere consapevoli delle seguenti dipendenze dai file CSV durante l’importazione:

* module_version.csv dipende da module.csv
* course_instance.csv dipende da course.csv
* course_module.csv dipende da course.csv, module.csv e module_version.csv
* course_instance.csv dipende da course.csv
* session.csv dipende da course.csv e module.csv
* enrollment.csv dipende da course.csv
* user_course_grade.csv dipende da course.csv e module.csv
* skill_course.csv dipende da course.csv
* skill_level.csv dipende da skill.csv
* learning_program_instance.csv dipende da learning_program e learning_program_course.csv
* learning_program_course.csv dipende da learning_program.csv
* learning_program_enrollment.csv dipende da learning_program e learning_program_instance.csv
* learning_program_instance_course_instance.csv dipende da learning_program.csv, learning_program_instance.csv e course_instance.csv
* certification_course.csv dipende da certification.csv e course.csv
* certification_commit.csv dipende da certification.csv e certification_course.csv
* certification_enrollment.csv dipende da certification.csv, certification_course.csv e certification_enrollment.csv

### Ordine dei corsi del programma di apprendimento nei file CSV per la migrazione

Nelle versioni precedenti delle specifiche di migrazione, il file learning_program_course.csv includeva una colonna relativa all’ordine, a indicare che era possibile controllare la sequenza dei corsi all’interno di un programma di apprendimento durante la migrazione.

Adobe Learning Manager non utilizza più questa colonna. L’ordine dei corsi in un programma di apprendimento non può essere controllato tramite CSV di migrazione e il sistema ignora eventuali valori forniti nella colonna dell’ordine, anche se **orderEnforced** è stato impostato su true.

Per evitare confusione, la colonna dell’ordine è stata rimossa dalle specifiche CSV ufficiali. Se disponi di script o strumenti esistenti che generano ancora questa colonna, puoi eliminarla in modo sicuro; ciò non ha alcun impatto sulla creazione o la visualizzazione dei programmi di apprendimento.

## Procedura di migrazione {#migrationprocedure}

Prima di avviare la procedura di migrazione, è importante tenere conto dei seguenti aspetti:

* Solo un progetto di migrazione può essere attivo in un account in qualsiasi momento. All’interno di un progetto, solo uno sprint può essere attivo in un dato momento.
* Non è possibile annullare un’Esecuzione già in corso nel processo di migrazione. Tuttavia, è possibile utilizzare l’opzione di eliminazione esistente all’interno di ciascuna funzionalità di Learning Manager per annullare qualsiasi migrazione di dati o contenuti.
* Non appena viene avviato, il progetto di migrazione passa allo stato &quot;Migrazione in corso&quot;. Durante la migrazione, nessun altro ruolo diverso dal ruolo di Amministratore di integrazione può accedere a Learning Manager.

### Creazione di account FTP e Box {#creatingftpandboxaccounts}

Pianificare il progetto di migrazione è molto importante. È consigliabile suddividere i progetti in più sprint e identificare chiaramente i dati di cui si desidera effettuare la migrazione in ciascuno sprint. Potrebbe inoltre essere una buona idea eseguire una convalida dopo ogni sprint per essere sicuri di aver eseguito la migrazione dei dati corretti nello sprint in questione, anziché limitarsi a un’unica convalida al termine del progetto. Prima di avviare lo sprint come parte del progetto di migrazione, è necessario caricare i file CSV di dati e contenuti nei server FTP e Box rispettivamente. Se non disponi di account per FTP personalizzato e Box, puoi crearli.

<!--**Create FTP account**-->

<!--
Click **[!UICONTROL Request for CSV FTP folder]**. A pop-up dialog appears prompting you to enter your e-mail id. Go through online instructions and create an FTP account. As soon as you create your account, you can view your migration project and sprint project folders in FTP. 

A sample snapshot of project files and folder of FTP is shown below for your reference. 
-->

<!--![](assets/exavault-migration-upload-folders.png)-->

**Creazione di un account Box**

Crea la cartella di caricamento dei contenuti seguendo un procedimento analogo a quello seguito per la creazione della cartella FTP. Fai clic su Migrazione nel riquadro di sinistra e seleziona Richiedi cartella di caricamento contenuti nella parte inferiore della pagina visualizzata.

Riceverai un’e-mail da Box con il link alla cartella condivisa. Se non disponi di un account Box, fai clic su Iscrizione e creane uno. Le istruzioni di accesso vengono inviate all’ID e-mail dell’Amministratore di integrazione.

**Caricamento di dati (file .csv) in cartelle FTP o Box**

La creazione di un account FTP o Box costituisce un prerequisito ai fini dello sviluppo di un progetto di migrazione. In questa fase puoi creare un progetto di migrazione e uno sprint nell’applicazione Learning Manager.  Fai riferimento alla sezione relativa alla **Procedura di migrazione di dati e contenuti** in questa pagina per creare un progetto di migrazione.

Nell’account FTP o Box, fai clic sul nome della cartella dei progetti e quindi sul nome dello sprint. All’interno della cartella degli sprint, puoi caricare i file di dati .csv di cui desideri eseguire la migrazione. Per caricare, fai clic sul pulsante Carica file in alto nel server FTP o Box e rilascia i file .csv. Di seguito è riportata un’istantanea di esempio dopo il caricamento su FTP come riferimento.

<!--![](assets/exavault-upload.png)-->

Puoi tornare al progetto di migrazione di Learning Manager, fare clic su **[!UICONTROL Aggiorna]** e visualizzare tutti i tipi di dati .csv elencati nello sprint di migrazione.

**Caricamento dei contenuti di formazione nelle cartelle di contenuto**

Carica i contenuti di formazione dell’LMS esistente nel tuo account Box. Se hai già creato lo sprint e il progetto di migrazione, l’account Box popolerà il campo relativo al nome di sprint e progetto di migrazione. Puoi caricare i contenuti nello stesso percorso. Fai riferimento alla sezione relativa alla **Procedura di migrazione di dati e contenuti** in questa pagina per creare un progetto di migrazione.

È possibile trascinare e rilasciare i file di contenuto oppure fare clic su **[!UICONTROL Carica]** e selezionare i file dal desktop. Se le dimensioni del file dei contenuti sono troppo grandi, si potrebbe verificare un ritardo nel caricamento dei file. Il tempo necessario per caricare i file nel tuo account Box varia a seconda delle dimensioni del file.

Di seguito viene mostrata, come riferimento, un’istantanea di esempio dell’account Box in seguito al caricamento dei contenuti:

![](assets/box-account.png)

*File nell&#39;account Box*

Una volta caricati i file nel tuo account Box, assicurati di specificare il percorso relativo di questo file di contenuto Box nel file module_version.csv. Indicare il percorso dei contenuti del modulo è un passaggio obbligatorio.

Una volta effettuato l’accesso ai server FTP e Box e caricato il contenuto, i percorsi CSV vengono visualizzati come mostrato nell’istantanea riportata di seguito in Learning Manager.

![](assets/after-setup.jpg)

*Percorsi CSV nell’account Box*

## Migrazione per alternative ed equivalenti

### Panoramica

Questo argomento descrive il modello di dati basato su CSV e il comportamento di migrazione per l’introduzione dell’equivalenza degli oggetti di apprendimento (LO) nel sistema.

### File CSV esistenti (contesto)

Questi file CSV esistono già nella piattaforma e forniscono l’oggetto di apprendimento principale, il modulo e il contesto di completamento (elenco non esaustivo):

* user_course_grade.csv
* moduleversione
* module.csv
* course.csv
* course_module.csv

Questi file continuano a essere utilizzati così come sono e non vengono modificati dalla nuova funzione di equivalenza, ma formano i dati sottostanti su cui opererà l’equivalenza.

### Nuovi file CSV per alternative

Sono stati introdotti due nuovi CSV per supportare le relazioni alternative GLI e i relativi completamenti da parte degli utenti.

#### &#x200B;1. equivalence_relations.csv

Definisce le mappature di equivalenza tra gli oggetti di apprendimento (LO) di origine e di destinazione, che possono essere corsi o percorsi di apprendimento (LP).

**Schema:**

* sourceId
* sourceloType (corso/programma di apprendimento)
* targetId
* targetLotype (corso/programma di apprendimento)
* dateCreated
* relationshipStatus (ACTIVE/DELETE)
* dateModified

**Scopo:**

* Rappresenta una relazione di equivalenza tra due LO.
* relationshipStatus controlla se la relazione è attualmente attiva o eliminata.
* dateCreated e dateModified supportano il controllo.

#### equivalence_user_completion.csv

Acquisisce informazioni di completamento a livello di utente per oggetti di apprendimento equivalenti, in linea con le relazioni definite in equivalence_relations.csv.

**Schema:**

* userID
* sourceId
* sourceloType (corso/programma di apprendimento)
* targetId
* targetLotype (corso/programma di apprendimento)
* dateCompleted

**Scopo:**

* Registra in modo esplicito quali **completamenti degli oggetti di apprendimento di destinazione** devono essere dedotti per un utente in base alla relazione di equivalenza e al completamento degli oggetti di apprendimento di origine esistenti.
* Funge da **origine autorevole** per i completamenti dell&#39;utente associati ai dati equivalenti migrati.

### Regole di migrazione e semantica comportamentale

#### &#x200B;1. Nessun supporto Retrofit per i nuovi file CSV equivalenti

* Tutti i dati relativi all’equivalenza devono essere inseriti tramite migrazione.
* Il sistema non supporta scenari in cui:
   * I dati LO (corsi/LP) sono stati creati tramite l’interfaccia utente e
   * Le relazioni di equivalenza vengono successivamente importate solo tramite file CSV.

Ciò significa che:

* Il modello supportato è: le definizioni degli LO e le loro relazioni di equivalenza sono gestite come parte di un flusso di migrazione coerente.
* I flussi ibridi in cui gli LO creati dall&#39;interfaccia utente vengono modificati con l&#39;equivalenza solo CSV non sono supportati.

#### &#x200B;2. Nessun completamento/incompletamento retroattivo da relazioni migrate

Quando viene introdotta una relazione di equivalenza tramite migrazione (ovvero tramite equivalence_relations.csv):

* Il sistema non eseguirà calcoli retroattivi di completamento o incompletamento basati esclusivamente su tale relazione.
* Al contrario, tutti i dati di completamento dell’utente richiesti devono essere forniti esplicitamente tramite equivalence_user_completion.csv.

**Implicazione:**

* equivalence_user_completion.csv è l&#39;unica fonte di verità per tutti i completamenti che devono essere riconosciuti al momento della migrazione come risultato dell&#39;equivalenza.
* La piattaforma non tenterà di dedurre o riempire nuovamente tali completamenti dall’avanzamento del corso esistente.

#### &#x200B;3. Comportamento per i nuovi completamenti dopo la migrazione

Se:

* Una relazione di equivalenza è stata creata tramite migrazione e
* Un Allievo completa successivamente l’LO di origine (post-migrazione),

quindi:

* Il sistema attiverà completamenti alternativi per l’LO di destinazione, vale a dire che l’equivalenza si comporta normalmente in futuro per i completamenti di nuove sorgenti.

**Distinzione chiave:**

* **Al momento della migrazione:** i completamenti devono pervenire tramite equivalence_user_completion.csv.
* **Dopo la migrazione:** la logica di runtime nativa gestirà i completamenti alternativi quando un oggetto di apprendimento di origine viene completato di recente.

#### &#x200B;4. Impatto sugli oggetti di apprendimento di ordine superiore

I completamenti alternativi in arrivo tramite CSV (ad esempio, tramite equivalence_user_completion.csv) attiveranno la ricalcolo degli LO di ordine superiore.

Gli LO di ordine superiore possono includere:

* Percorsi di apprendimento

**Implicazioni tecniche:**

* L&#39;assimilazione di equivalence_user_completion.csv non è un&#39;operazione &quot;invisibile&quot;: avvia la stessa logica di ricalcolo/rollup che verrebbe attivata dai normali completamenti in fase di runtime.
* I sistemi che integrano o pianificano questa migrazione devono pianificare il carico e i tempi dei ricalcoli.

## Webhook per alternative

Quando un Allievo completa un corso tramite un’iscrizione alternativa o una relazione, Adobe Learning Manager genera un evento webhook dedicato distinto dal webhook di completamento del corso standard, che consente alle integrazioni di applicare una logica di gestione diversa per i completamenti alternativi. Gli eventi webhook vengono generati anche per il completamento retroattivo e l’incompletamento retroattivo, che coprono le modifiche storiche allo stato del corso, comprese quelle guidate dagli aggiornamenti delle relazioni, in modo che i sistemi esterni rimangano sincronizzati con lo stato di completamento corrente dell’Allievo.

Per informazioni sui webhook per Alternative, visualizza [Webhook per Alternative](/help/migrated/integration-admin/feature-summary/webhooks.md#webhooks-for-alternates)

## Procedura di migrazione di dati e contenuti {#dataandcontentmigrationprocedure}

La procedura per migrare i contenuti e i dati LMS dell’azienda a Learning Manager viene illustrata di seguito:

Prendi visione dei prerequisiti del processo di migrazione prima di avviare la migrazione. Fai riferimento alla sezione [Specifiche CSV e CSV di esempio](migration-manual.md#main-pars_header_140933605) in questa pagina e preparare i CSV per la migrazione dei dati e dei contenuti.

1. Accedi all’applicazione Learning Manager come Amministratore di integrazione e fai clic su **[!UICONTROL Migrazione]** nel riquadro a sinistra.

   Viene visualizzata la home page dei progetti di migrazione. Se la tua organizzazione ha già creato progetti di migrazione, puoi visualizzare l’elenco di tutti i progetti in questa pagina.

1. Fai clic su **[!UICONTROL Nuovo]** nell’angolo in alto a destra della pagina per creare un progetto di migrazione. In alternativa, è possibile fare clic sul collegamento **[!UICONTROL Creazione di un progetto di migrazione]** nella pagina per creare un progetto di migrazione. Viene visualizzata la pagina Creazione di un progetto di migrazione.

   Se non hai ancora creato una cartella FTP, ti verrà chiesto di creare una cartella FTP nell’account. Si tratta di un passaggio obbligatorio prima di iniziare a creare un progetto di migrazione.

   ![](assets/create-project.png)
   *Crea cartella FTP*

   Specifica il nome del progetto, il tag del progetto, il catalogo dei corsi e la descrizione del progetto di migrazione. Fai clic su **[!UICONTROL Crea]**.

   Gli elementi dati di migrazione vengono identificati utilizzando il tag del progetto di migrazione. Se non disponi di un catalogo dei corsi specifico, seleziona il catalogo predefinito dal menu a discesa. Tutti i corsi che vengono migrati utilizzando un progetto di migrazione saranno inclusi nel catalogo selezionato in questa fase. Se non viene selezionato nessun catalogo, tutti i corsi migrati faranno parte del catalogo predefinito.

1. La pagina di configurazione degli sprint viene visualizzata come mostrato nell’istantanea riportata di seguito. È necessario creare uno sprint nell’ambito del progetto di migrazione. Scegli un nome per lo sprint e fornisci una breve descrizione. Puoi scegliere Sì se desideri migrare il contenuto come parte di questo sprint. Fai clic su **[!UICONTROL Avanti]**.

   ![](assets/users-modified-sprint.png)
   *Migrazione sprint*

   Seleziona la casella di controllo denominata **Sono stati aggiunti o modificati utenti dall’ultima esecuzione** per sincronizzare l’elenco degli utenti con l’applicazione Learning Manager. Se stai effettuando la migrazione di contenuti e dati all’applicazione Learning Manager, questa operazione potrebbe non essere richiesta. Tuttavia, qualora sia trascorso un certo intervallo di tempo tra la precedente migrazione sprint e l’ultima, è consigliabile effettuare la sincronizzazione dell’elenco degli utenti. Questo passaggio consente la sincronizzazione del database Learning Manager con gli utenti dell’LMS.

   La sincronizzazione è consigliata durante la migrazione di enrollment.csv e user_course_grade.csv. Questo passaggio consente la sincronizzazione del database Learning Manager con il database di migrazione e assicura che tutti gli utenti i cui record devono essere migrati nello sprint siano disponibili nel database di migrazione.

1. È possibile avviare la migrazione sprint con i dati e i contenuti caricati. Fai clic sul collegamento **[!UICONTROL Aggiorna]** prima di avviare l’esecuzione dello sprint per sincronizzare l’FTP e le cartelle dei contenuti con l’applicazione Learning Manager.

   ![](assets/sprint1-filesupload.png)
   *Avvia migrazione sprint*

   Fai clic su **[!UICONTROL Inizio]** nell&#39;angolo superiore destro della pagina. Puoi fare clic su **[!UICONTROL Arresta]** in qualsiasi momento durante il processo di migrazione sprint per interrompere la migrazione.

   Lo stato della migrazione viene visualizzato per ciascuno dei contenuti e degli elementi dati dello sprint. Verifica il numero di elementi riusciti e non riusciti nell’ambito dell’esecuzione di uno sprint di migrazione.

   Se stai caricando il contenuto di un modulo, assicurati che il percorso della cartella del contenuto sia specificato in module_version.csv. Se dimentichi questo passaggio, potrebbero verificarsi errori durante la migrazione. Ad esempio, per caricare i contenuti di un modulo di autoformazione, come video, è necessario specificare il relativo percorso URL Box in module_version.csv. Per il contenuto del modulo Attività, è possibile specificare il nome dell’URL.

   Come riferimento, viene di seguito fornita un’istantanea della finestra di dialogo di stato. Come mostrato nell’istantanea, è possibile visualizzare il numero dei record elaborati per ciascun elemento dati di migrazione insieme allo stato degli elementi riusciti e non riusciti. Fai clic su Scarica record degli errori confrontandoli con gli elementi non riusciti per scaricare e visualizzare i registri degli errori. È possibile correggere i problemi in CSV e ricaricare su FTP.

   ![](assets/sample-sprint-progress-status.png)
   *Visualizza avanzamento sprint*

   Fai clic sull’elenco Sprint nel riquadro di sinistra per visualizzare l’elenco di tutti gli sprint di un progetto di migrazione. Puoi visualizzare un elenco di tutti gli sprint, il numero di esecuzioni per ogni sprint, la data di inizio, la durata e lo stato di completamento, come mostrato nell’istantanea di esempio seguente.

   ![](assets/sprint-list.png)
   *Visualizza elenco di sprint*

1. Dopo aver caricato i CSV aggiornati più di recente, puoi fare clic su Riesegui nell’angolo in alto a destra della pagina. Riesegui elabora nuovamente tutti gli elementi di dati, ignorando quelli che non presentano modifiche. Una volta che sei soddisfatto della migrazione degli elementi di dati in uno sprint, puoi contrassegnare la migrazione dello sprint come completata facendo clic sull’apposito pulsante nella parte superiore della pagina. Potrai avviare un nuovo sprint con più elementi di dati in un secondo momento. Una volta che uno Sprint è stato contrassegnato come completato, non è possibile rieseguirlo. Allo stesso modo, in un progetto di migrazione è possibile avere un numero qualsiasi di sprint. Una volta che sei soddisfatto dello stato di migrazione di tutti gli sprint, puoi contrassegnare il progetto di migrazione come completato facendo clic sul collegamento **Contrassegna progetto come completato** nella pagina dell’elenco di sprint.

   Prima di contrassegnare il progetto di migrazione come completato, è necessario assicurarsi che tutti gli sprint del progetto siano completi. Dopo aver contrassegnato il progetto di migrazione come completato, non è possibile tornare indietro e creare eventuali sprint in tale progetto o apportare modifiche al progetto stesso. È necessario creare un altro progetto di migrazione e aggiungere sprint a esso.

## Verifica migrazione {#registration}

Dopo aver eseguito la migrazione dei dati e dei contenuti di formazione dall’LMS legacy della tua organizzazione, verifica i dati e i contenuti importati utilizzando le varie funzionalità degli oggetti di apprendimento. Ad esempio, è possibile accedere all’applicazione Learning Manager come Amministratore e verificare la disponibilità dei dati e dei contenuti relativi ai moduli e ai corsi importati.

## Migrazione tramite API

Adobe Learning Manager (ALM) fornisce una funzione di migrazione per il caricamento di dati o contenuti da sistemi esterni, utilizzata principalmente per la migrazione da piattaforme LMS legacy.

Tuttavia, alcune organizzazioni potrebbero richiedere che questo processo venga eseguito regolarmente (ad esempio, di notte o settimanalmente), anziché come importazione singola.

Ad esempio, puoi vedere come un cliente fittizio (NovaFX) si integra con un fornitore esterno fittizio (SquareCorp) e automatizza le migrazioni pianificate. L’integrazione consente di:

* I corsi SquareCorp vengono visualizzati come oggetti di apprendimento all’interno di ALM per gli Allievi NovaFX.
* NovaFX monitora i progressi degli Allievi per i corsi ospitati da SquareCorp direttamente in ALM.

### Requisiti di integrazione

SquareCorp deve fornire:

* Informazioni sui metadati del corso: API per condividere i metadati del corso a cui NovaFX ha accesso.
* Informazioni sui dati di avanzamento: un’API per condividere periodicamente informazioni sull’avanzamento e sul completamento dell’Allievo.

### Definizioni chiave

* **Progetto attivo:** Un progetto è attivo se è &quot;In corso&quot; o &quot;Inizializzato&quot;.
* **Sprint attivo:** Uno sprint è attivo se è &quot;In corso&quot; o &quot;Inizializzato&quot;.

### Automatizzare l’esecuzione dello sprint

Crea un&#39;app o uno script che esegue quanto segue secondo una pianificazione:

1. Recupero dei metadati del corso, delle iscrizioni degli utenti e dei voti degli Allievi da SquareCorp.
2. Genera i file CSV.
3. Carica i file su Box o FTP.
4. Attiva lo sprint utilizzando le API di migrazione.

### Dettagli API

#### Avviare un&#39;esecuzione della migrazione

**Endpoint:** POST /primeapi/v2/bulkimport/startrun

Parametri:

* **lockaccount (booleano):** Il parametro determina se bloccare l&#39;account all&#39;inizio dell&#39;esecuzione. Per impostazione predefinita, è impostato su false. Si consiglia di evitare di utilizzare questo parametro a meno che non vi sia un motivo valido per bloccare l&#39;account.
* **catalogid (Integer):** Questo parametro consente di selezionare il catalogo di destinazione durante la migrazione. In genere viene impostato durante la creazione del progetto di migrazione, ma può essere regolato per singole esecuzioni. Quando il catalogo viene modificato, gli oggetti di apprendimento aggiunti nelle esecuzioni future verranno inseriti nel catalogo scelto più di recente. Se è necessario tornare al catalogo selezionato durante la creazione del progetto di migrazione, è necessario specificarlo esplicitamente.
* **migrationProjectId (Integer):** Il parametro è necessario per attivare un progetto di migrazione specifico quando nell&#39;account sono abilitate più esecuzioni basate su API.

#### Verifica se la sincronizzazione può iniziare

Assicurati che il contenuto possa essere sincronizzato con la cartella sprint. Non copiare i file di contenuto o metadati nella cartella FTP a meno che questa API non restituisca un oggetto risposta corretto.

**Endpoint:** GET /primeapi/v2/bulkimport/cansync

Parametri:

* **migrationProjectId (Integer)** Il parametro è necessario per attivare un progetto di migrazione specifico quando nell&#39;account sono abilitate più esecuzioni basate su API.

<b>Risposta riuscita</b>

```
{  
    "status": "OK",  
    "title": "BULKIMPORT_CAN_SYNC_NOW",  
    "source": {  
        "info": "Yes"  
    }  
} 
```

<b>Risposta riuscita</b>

```
{ 
    "status": "BAD_REQUEST", 
    "title": "BULKIMPORT_ERROR_CANNOT_SYNC", 
    "source": { 
        "info": "Error, No active projects" 
    } 
} 
```

<b>Possibili risposte API</b>

| Azione | Tipo | Messaggio |
| ------------------------------------- | ------- | ------------------------------------------------------------------------------------- |
| BULKIMPORT_RUN_INITIATED_SUCCESSFULLY | Operazione completata | Esecuzione iniziata correttamente |
| BULKIMPORT_ERROR_CANNOT_INITATE_RUN | Errore | Esecuzione in corso |
| BULKIMPORT_ERROR_CANNOT_INITATE_RUN | Errore | Sono presenti più progetti attivi |
| BULKIMPORT_ERROR_CANNOT_INITATE_RUN | Errore | Sono presenti più sprint |
| BULKIMPORT_ERROR_CANNOT_INITATE_RUN | Errore | Nessun progetto attivo |
| BULKIMPORT_ERROR_CANNOT_INITATE_RUN | Errore | Nessun sprint attivo |
| BULKIMPORT_ERROR_CANNOT_INITATE_RUN | Errore | Il catalogo fornito non è un ID valido o non appartiene all’account Prime |
| BULKIMPORT_CAN_SYNC_NOW | Informazioni | Può sincronizzarsi ora |
| BULKIMPORT_ERROR_CANNOT_SYNC | Errore | Esecuzione in corso |
| BULKIMPORT_ERROR_CANNOT_SYNC | Errore | Sono presenti più progetti attivi |
| BULKIMPORT_ERROR_CANNOT_SYNC | Errore | Sono presenti più sprint |
| BULKIMPORT_ERROR_CANNOT_SYNC | Errore | Nessun progetto attivo |
| BULKIMPORT_ERROR_CANNOT_SYNC | Errore | Nessun sprint attivo |
| BULKIMPORT_ERROR_CANNOT_SYNC | Errore | Nessun file valido presente nella cartella |

### Esempio di flusso di integrazione

1. Verifica l’API cansync.
2. Genera e carica file CSV.
3. Attiva lo sprint utilizzando l’API startrun.
4. Monitora la risposta e gestisci gli errori.

### Limitazioni

Le API di migrazione non forniscono funzionalità per controllare gli errori relativi alla migrazione direttamente nel file CSV di output dopo l’esecuzione dello sprint. Tuttavia, questi errori possono essere esaminati come righe all’interno del file CSV accedendo all’interfaccia utente dell’Amministratore di integrazione dopo un’esecuzione sprint.

### Verifica della migrazione tramite API

L&#39;API di migrazione, `runStatus`, consente agli amministratori di integrazione di tenere traccia dell&#39;avanzamento delle esecuzioni di migrazione attivate tramite l&#39;API.

L&#39;API `runStatus` fornisce inoltre un collegamento diretto per scaricare i registri degli errori in formato CSV per le esecuzioni completate. Il collegamento per il download rimane attivo per sette giorni e i registri vengono conservati per un mese.

**Curva di esempio**

**Endpoint**

```
GET /bulkimport/runStatus
```

**Parametri**

* **migrationProjectId**: (obbligatorio). Identificatore univoco di un progetto di migrazione. Un progetto di migrazione viene utilizzato per trasferire dati e contenuti da un sistema di gestione dell’apprendimento (LMS) esistente a Adobe Learning Manager. Ogni progetto di migrazione può essere costituito da più sprint, ovvero unità più piccole delle attività di migrazione.

* **sprintId**: (obbligatorio). Identificatore univoco di uno sprint all&#39;interno di un progetto di migrazione. Uno sprint è un sottoinsieme delle attività di migrazione che include elementi di apprendimento specifici (ad esempio, corsi, moduli, record dell’Allievo) da migrare da un LMS esistente a Adobe Learning Manager. Ogni sprint può essere eseguito in modo indipendente, consentendo una migrazione graduale.

* **sprintRunId**: (obbligatorio). Identificatore univoco utilizzato per tenere traccia dell&#39;esecuzione di uno sprint specifico in un progetto di migrazione. È associato al processo di migrazione effettivo per gli elementi definiti in uno sprint. Lo sprintRunId consente di monitorare, risolvere e gestire il processo di migrazione.

**Risposta**

```
{
  "sprintId": 2510080,
  "sprintRunId": 2740845,
  "migrationProjectId": 2509173,
  "startTime": 1746524711052,
  "endTime": 1746524711052,
  [
    {
      "id": 2609923,
      "lastHeartbeatTime": 1746524711052,
      "objectName": "content",
      "jobState": "COMPLETED",
      "errorCsvLink": "",
      "errorLogLink": "migration/5830/2509173/2510080/2740845/content_err.csv",
      "sequenceNumber": 1
    },
    {
      "id": 2609922,
      "lastHeartbeatTime": 1746524713577,
      "objectName": "course",
      "jobState": "WAITING_IN_QUEUE",
      "errorCsvLink": "",
      "errorLogLink": null,
      "sequenceNumber": 2
    }
  ]
}
```

Inoltre, la risposta API `startRun` ora include l&#39;ID del progetto di migrazione, l&#39;ID dello sprint e l&#39;ID dell&#39;esecuzione dello sprint, necessari per eseguire una query sul nuovo endpoint di stato.

```
curl -X GET --header 'Accept: text/html' 'https://learningmanager.adobe.com/primeapi/v2/bulkimport/runStatus?migrationProjectId=001&sprintId=10001&sprintRunId=7'
```

Fornisce la seguente risposta. La risposta contiene:

* `migrationId`
* `sprintId`
* `sprintRunId`

**Risposta**

```
{
  "status": "OK",
  "title": "BULKIMPORT_RUN_INITIATED_SUCCESSFULLY",
  "source": {
    "info": "Success",
    "migrationInfo": {
      "migrationProjectId": "001",
      "sprintId": "10001",
      "sprintRunId": "7"
    }
  }
}
```

## Aggiornamento nella migrazione {#retrofittinginmigration}

Questa funzionalità di integrazione consente di trasformare i dati storici di un oggetto di apprendimento da un sistema di gestione dell’apprendimento legacy a un corso attivo creato in Learning Manager.

Di seguito sono riportate le specifiche CSV aggiornate che puoi utilizzare per mappare i dati di migrazione LMS esistenti. Fai clic su csv-specifications e sample-csvs per scaricare i file zip. Il file csv-specifications.zip scaricato contiene quattro file Excel. I file Excel contengono specifiche accompagnate da descrizioni che illustrano come compilare i file .csv. I file .csv corrispondenti devono contenere i dati per ciascun campo nel formato prestabilito, come spiegato in questi file .xlsx.

1-enrollment.xlsx contiene le descrizioni dei metadati richiesti per il file retrofit_enrollment.csv.

2-certification_enrollment.xlsx contiene le descrizioni dei metadati richiesti per il file retrofit_certification_enrollment.csv.

3-learning_program_enrollment.xlsx contiene le descrizioni dei metadati richiesti per il file retrofit_learning_program_enrollment.csv.

4-user_course_grades.xlsx contiene le descrizioni dei metadati richiesti per il file retrofit_user_course_grades.csv.
[csv-specific.zip](assets/csv-specifications.zip)

>[!NOTE]
>
>UUID (Univerally Unique Id) è anche una colonna nel file CSV di migrazione.


## Risoluzione dei problemi di migrazione {#troubleshootingmigrationissues}

Consulta questo [articolo](../../kb/troubleshooting-migration.md) per conoscere la soluzione ai problemi affrontati dagli Amministratori di integrazione durante la migrazione di dati e contenuti dall’LMS esistente all’applicazione Learning Manager.

## Suggerimenti per la gestione degli utenti {#usermanagement}

In questo argomento vengono forniti alcuni suggerimenti utili per capire in che modo vengono considerati e gestiti gli utenti in Learning Manager. Questi concetti ti aiuteranno a gestire meglio gli utenti durante l’utilizzo dell’importazione CSV, dei connettori e delle funzionalità di migrazione di Learning Manager.

## ID Learning Manager {#captivateprimeids}

Learning Manager fornisce due tipi di ID univoci per gli utenti:

* ID e-mail
* UUID (ID universalmente univoco)

Learning Manager supporta UUID per fornire flessibilità alle organizzazioni nel controllo degli account utente. Come amministratore, se disponi di un UUID degli utenti in un account, puoi modificare gli ID e-mail degli utenti per quell’account.

**Scenario di utilizzo dell’UUID in un’organizzazione**

Consideriamo uno scenario in cui un dipendente A entra a far parte di un’azienda denominata Learning Manager, come appaltatore. Durante il periodo del contratto, l’azienda di Learning Manager potrebbe non fornire l’ID e-mail dell’azienda come ```A@example.com```, ma considerare solo l’account e-mail personale del dipendente, ad esempio ```A@gmail.com```. Dopo aver completato 6 mesi di periodo di contratto, se lo stesso dipendente A si aggiunge a Learning Manager come dipendente a tempo pieno, Learning Manager potrebbe voler modificare il suo ID e-mail con l’ID e-mail dell’azienda: ```A@example.com```.

L’accesso UUID all’account utente rappresenta un vantaggio per Learning Manager nello scenario sopra citato. Learning Manager può facilmente sostituire l’ID e-mail personale del dipendente A con un ID e-mail ufficiale. I record del dipendente rilevanti per questo account non sono interessati da questa modifica.

## Identificazione utente singolo {#singleuseridentification}

Learning Manager identifica e ricorda la modalità con cui viene aggiunto un utente singolo, ad esempio mediante registrazione automatica, tramite caricamento CSV, oppure utilizzando l’interfaccia utente o tramite API.

* Se un utente singolo viene aggiunto utilizzando l’interfaccia utente o tramite API, è possibile eliminare tale tipo di utente tramite interfaccia utente o API.
* È possibile aggiornare gli utenti singoli utilizzando il processo di caricamento CSV, ma tieni presente che questi utenti vengono trattati come utenti CSV e che vengono loro applicati i flussi di lavoro CSV.

## Assegnazione del ruolo di Manager {#assigningmanagerrole}

Non è possibile assegnare direttamente un ruolo di Manager a un qualsiasi utente in Learning Manager. Un utente X può diventare Manager Learning Manager solo se viene impostato un attributo Manager di qualsiasi utente (ad esempio, Y) in quell’account come X.

In uno scenario in cui X è Manager degli utenti, ad esempio, A, B e C, se X lascia l’organizzazione, è necessario assicurarsi che l’attributo Manager di A, B e C sia impostato sul nuovo Manager. In alternativa, è possibile impostare temporaneamente l’attributo Manager di questi utenti come ROOT e assegnare il nuovo nome Manager in un secondo momento.

Per ulteriori informazioni su questo argomento, consulta il seguente contenuto della Guida:

* [Domande frequenti sul caricamento di CSV](/help/migrated/administrators/feature-summary/add-users-user-groups.md#bulk-upload-internal-users/)
* [Guida all’aggiunta di utenti](/help/migrated/administrators/feature-summary/add-users-user-groups.md)

## Modifiche API

La versione di aprile 2026 di Adobe Learning Manager offre miglioramenti mirati all’API pubblica nelle aree delle alternative e degli equivalenti, dell’accesso ai contenuti con finestra di tempo, dei tentativi di quiz basati sui contenuti, delle esperienze degli Allievi non registrate e della gestione delle risorse formative. Questi aggiornamenti sono progettati per rimanere ampiamente compatibili con le versioni precedenti, consentendo al contempo modelli di integrazione più precisi ed estensibili.

Per le modifiche API, visualizza [Modifiche API](/help/migrated/api-changes-alm.md).
