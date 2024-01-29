---
description: Manuale di riferimento per gli Amministratori di integrazione che desiderano eseguire la migrazione di un LMS esistente all’LMS di Learning Manager
jcr-language: en_us
title: Manuale di migrazione
source-git-commit: 66dfaaaf723382eada39e2be29dfd49b795107a0
workflow-type: tm+mt
source-wordcount: '3705'
ht-degree: 0%

---



# Manuale di migrazione

Manuale di riferimento per gli Amministratori di integrazione che desiderano eseguire la migrazione di un LMS esistente all’LMS di Learning Manager

## Panoramica {#overview}

<table>
 <tbody>
  <tr>
   <td><img src="assets/migration.jpg"></td>
   <td>
    <p><a href="https://business.adobe.com/products/learning-manager/adobe-learning-manager.html">Adobe di Learning Manager</a> è una soluzione di gestione dell’apprendimento self-service ospitata nel cloud e incentrata sugli allievi. L’Adobe consente alle aziende con i sistemi di gestione dell’apprendimento (LMS) esistenti di migrare i dati e i contenuti di formazione dell’organizzazione all’applicazione LMS di Learning Manager. </p></td>
  </tr>
 </tbody>
</table>

### Scenario di utilizzo {#usagescenario}

In generale, le grandi aziende dispongono di un sistema LMS interno o di sistemi di gestione dell&#39;apprendimento legacy forniti dal fornitore. LMS è costituito dai contenuti di formazione aziendale e dai dati di formazione. Quando un’azienda acquista Learning Manager, potrebbe essere utile spostare i contenuti e i dati LMS esistenti in Learning Manager per sfruttare i vantaggi di un LMS moderno e intuitivo senza perdere i dati legacy dell’organizzazione.

Learning Manager fornisce gli strumenti e le specifiche necessari in modo che l’Amministratore di integrazione dell’organizzazione sia in grado di configurare ed eseguire le attività di migrazione.

A partire da oggi, gli Amministratori di un’organizzazione possono accedere alla funzione di migrazione in Learning Manager contattando il team di supporto degli Adobi. Per abilitare la funzione di migrazione nel tuo account, puoi rivolgerti al team di supporto dell’Adobe Learning Manager.

## Processo di migrazione {#apidescription}

In questa sezione vengono illustrati i prerequisiti per la migrazione, le fasi principali del processo di migrazione, gli sprint di migrazione, le specifiche, i passaggi relativi alla migrazione di dati e contenuti:

### Prerequisiti {#prerequisites}

Il team di Learning Manager prevede che gli Amministratori di integrazione dell’organizzazione eseguano le seguenti attività prima di intraprendere il processo di migrazione:

* L’Amministratore di integrazione estrae dati e contenuti dall’LMS in uso e trasforma i dati nei formati di file definiti da Learning Manager.
* Learning Manager non supporta l’importazione di utenti nell’ambito del processo di migrazione e prevede che l’importazione di utenti venga eseguita dall’organizzazione mediante connettori. Adobe Systems prevede che questi connettori siano configurati prima del processo di migrazione. Fare riferimento a [Guida ai connettori di Learning Manager](connectors.md) per ulteriori informazioni.

Learning Manager consiglia agli Amministratori di provare il processo di migrazione in un account di prova prima di migrare dati e contenuti nell’ambiente di produzione di Learning Manager.

### Fasi principali del processo di migrazione {#keystepsofmigrationprocess}

I passaggi principali coinvolti nella migrazione di contenuti e dati da un LMS esistente a Learning Manager sono i seguenti:

1. L’Amministratore di integrazione o il partner valuta i dati e i contenuti LMS esistenti di cui deve essere eseguita la migrazione.
1. L’Amministratore di integrazione valuta gli strumenti e le specifiche forniti da Learning Manager per l’acquisizione di dati e contenuti.
1. L’Amministratore di integrazione scrive il codice o esegue operazioni manuali per esportare i dati e i contenuti della formazione dal sistema LMS precedente in base alla funzionalità fornita dal sistema LMS precedente.
1. Una volta che i dati e i contenuti di formazione sono disponibili, l’Amministratore di integrazione analizza e mappa dati e contenuti in modo che corrispondano alle specifiche di migrazione di Learning Manager.
1. L’Amministratore di integrazione utilizza gli strumenti forniti da Learning Manager per eseguire la migrazione nel seguente ordine:

   1. Trasferimento degli Allievi a Learning Manager
   1. Trasferimento dei contenuti di formazione in Learning Manager e
   1. Infine, trasferisci i dati di formazione a Learning Manager.

L’organizzazione può iniziare a utilizzare l’LMS di Learning Manager insieme ai contenuti legacy.

### Ambito degli oggetti di migrazione {#scopeofmigrationobjects}

Puoi migrare i contenuti solo per i seguenti oggetti di apprendimento:

* Modulo
* Distintivi
* Corso
* Versione modulo
* Istanza del corso
* Modulo del corso
* Abilità
* Livello di competenza
* Corso sulle abilità
* Certificazione
* Corso per la certificazione
* Commit certificazione
* Programma di apprendimento
* Corso del programma di apprendimento
* Istanza del programma di apprendimento
* Istanza del corso del programma di apprendimento
* Risorsa formativa
* Versione risorsa formativa
* Corso risorse formative
* Competenze risorsa formativa
* Iscrizione
* Iscrizione certificazione
* Iscrizione al programma di apprendimento
* Iscrizione risorsa formativa
* Livelli corso utente



### Concetti chiave della migrazione {#keyconceptsofmigration}

Di seguito sono illustrati brevemente alcuni dei concetti chiave del processo di migrazione di Learning Manager, per un riferimento rapido:

**Progetto di migrazione**

In Learning Manager, un progetto di migrazione è composto da uno o più sprint. Puoi anche avere più progetti di migrazione per il tuo account. Il processo di migrazione in Learning Manager inizia con la creazione di un progetto di migrazione.

**Sprint**

Nel processo di migrazione di Learning Manager, uno sprint definisce un set di elementi di migrazione che si desidera migrare dall’LMS esistente. Un elemento di migrazione può essere un modulo del corso, record dell’Allievo o un set di corsi. Puoi avere più elementi di dati di apprendimento in uno sprint. Puoi eseguire i processi di migrazione in ogni sprint.

**Esecuzioni sprint**

Esecuzione sprint indica il processo di avvio di un processo di migrazione sprint. Potete interrompere l’esecuzione dello sprint in qualsiasi momento di un’esecuzione.

**Ripetizioni sprint**

Puoi rieseguire uno sprint di migrazione dopo il suo completamento in qualsiasi momento. Questa situazione di riesecuzione o riesecuzione di uno sprint si verifica quando si desidera accodare i dati in un elemento sprint e migrarli di nuovo nell&#39;applicazione o correggere gli errori nei file CSV.

**Specifica CSV**

Learning Manager offre una serie di [specifiche CSV standard](migration-manual.md#main-pars_header_140933605). È consigliabile prendere visione delle specifiche CSV prima di avviare il processo di migrazione. L’Amministratore di integrazione dell’organizzazione può analizzare i formati di dati esistenti e mapparli per farli coincidere con gli elementi del modello CSV forniti da Learning Manager.

**Tag del progetto di migrazione**

Adobe Systems consiglia di utilizzare una serie di parole chiave come tag per identificare facilmente i progetti di migrazione all’interno dell’applicazione Learning Manager. Questi tag consentono di identificare i progetti internamente nell’applicazione Learning Manager in qualsiasi momento.

**Modulo senza contenuto**

Learning Manager consente di caricare un modulo senza contenuto. Adobe Systems lo considera come modulo senza contenuto in Learning Manager. In uno scenario in cui si desidera migrare alcuni dei dati legacy dal proprio LMS esistente senza la necessità di alcun contenuto, è possibile caricare il file module_version.csv senza riferimento URL.

## Specifiche CSV e CSV di esempio {#csv}

Di seguito sono riportate le specifiche CSV standard che è possibile utilizzare per eseguire il mapping con i dati di migrazione LMS esistenti. Fai clic su specifiche csv e csv di esempio per scaricare i file zip. Il file csv-specific.zip scaricato contiene sette fogli Excel. Questi fogli Excel sono specifiche con descrizioni per aiutarti a capire come riempire i file .csv. I file .csv corrispondenti devono contenere i dati per ogni campo nel formato prescritto, come spiegato in questi file .xlsx.

<table border="1" cellspacing="0" cellpadding="0" width="100%">
 <tbody>
  <tr>
   <th>
    <p><b>Sl.no</b></p></th>
   <th>
    <p><b>Nome file</b></p></th>
   <th>
    <p><b>Descrizione del contenuto</b></p></th>
   <th>
    <p>Note</p></th>
  </tr>
  <tr>
   <td>
    <p>1</p></td>
   <td>
    <p>module.xlsx</p></td>
   <td>
    <p>metadati per module.csv;</p></td>
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
    <p>Indica il nome di un autore per un determinato corso poiché a volte i nomi di più autori non vengono visualizzati in modo accurato nell’applicazione dopo la migrazione. </p></td>
  </tr>
  <tr>
   <td>
    <p>4</p></td>
   <td>
    <p>module_version.xlsx </p></td>
   <td>
    <p>Metadati per module_version.csv</p></td>
   <td>
    <p>Assicurati di fornire il percorso URL della cartella dell’account Box in cui hai caricato il contenuto. </p></td>
  </tr>
  <tr>
   <td>
    <p>5</p></td>
   <td>
    <p>course_instance.xlsx</p></td>
   <td>
    <p>metadati per course_instance.csv; </p></td>
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
    <p>Assicurati che ogni voce nel file CSV della sessione sia associata ad almeno un modulo Aula/Aula virtuale</p></td>
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
    <p>metadati per skill.csv;</p></td>
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
    <p>metadati per skill_course.csv</p></td>
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
    <p>risorsa formativa.xlsx</p></td>
   <td>
    <p>Metadati per job_aid.csv</p></td>
   <td>
    <p>Ogni risorsa formativa migrata richiede una o più versioni della risorsa formativa.</p></td>
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
    <p>metadati per job_aid_course.csv</p></td>
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
    <p>enrollments.xlsx</p></td>
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
    <p>metadati per job_aid_enrollment.csv</p></td>
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
    <p>Fornisci i dati dei record Allievo richiesti nel file .csv anche se non sono obbligatori. Senza queste informazioni, anche se il file .csv viene elaborato per la migrazione, l’applicazione Learning Manager potrebbe non riflettere alcun dato. il file sample-csvs.zip contiene sette file .csv con convenzione di denominazione simile a quella riportata sopra.</p></td>
  </tr>
 </tbody>
</table>

Learning Manager supporta solo i valori di data e ora in formato UTF a 8 e 32 bit. Se citi la data nei file CSV con una data non compresa nell’intervallo consentito, è possibile che si verifichino errori durante la migrazione: 2038-07-17T08:53:21.000Z o 1980-04-17T08:13:25.322Z
[sample-csvs.zip](assets/sample-csvs.zip) [csv_specific.zip](assets/csv-specifications.zip)Durante l’importazione, devi tenere presente le seguenti dipendenze dai file CSV:

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

## Procedura di migrazione {#migrationprocedure}

Prima di iniziare la procedura di migrazione, è importante tenere presente quanto segue:

* In un account può essere attivo un solo progetto di migrazione in qualsiasi momento. All’interno di un progetto, solo uno sprint può essere attivo in un dato momento.
* Non è possibile annullare un&#39;esecuzione già in corso di migrazione. Tuttavia, puoi utilizzare l’opzione di eliminazione esistente all’interno di ciascuna funzionalità di Learning Manager per annullare qualsiasi migrazione di dati o contenuti.
* Non appena viene avviato, il progetto di migrazione passa allo stato &quot;Migrazione in corso&quot;. Durante la migrazione, nessun altro ruolo diverso dal ruolo di Amministratore di integrazione può accedere a Learning Manager.

### Creazione di account FTP e Box {#creatingftpandboxaccounts}

Pianificare il progetto di migrazione è molto importante. Si consiglia di suddividere i progetti in più sprint e di identificare chiaramente ciò che si desidera migrare in ogni sprint. Può anche essere una buona idea fare qualche convalida dopo ogni sprint per sentirsi sicuri dei dati migrati in quello sprint, invece di una grande fase di convalida alla fine del progetto. Prima di avviare lo sprint come parte del progetto di migrazione, è necessario caricare dati e contenuti nei file CSV rispettivamente nei server FTP e Box. Se non disponi di account per FTP personalizzato e Box, puoi crearli.

**Crea account FTP**

Fai clic **[!UICONTROL Richiesta di cartella FTP CSV]**. Viene visualizzata una finestra a comparsa in cui viene richiesto di immettere l’ID e-mail. Consulta le istruzioni online e crea un account FTP. Una volta creato l’account, puoi visualizzare le cartelle del progetto di migrazione e del progetto di sprint in FTP.

Di seguito è riportata un’istantanea di esempio dei file di progetto e della cartella FTP come riferimento.

<!--![](assets/exavault-migration-upload-folders.png)-->

**Crea account Box**

Crea la cartella di caricamento del contenuto in un processo simile a quello seguito per la creazione della cartella FTP. Fai clic su Migrazione nel riquadro a sinistra e poi su Richiedi cartella per il caricamento dei contenuti nella parte inferiore della pagina visualizzata.

Riceverai un’e-mail da Box con il collegamento alla cartella condivisa. Se non disponi di un account Box, fai clic su Registrati e crea un account. Le istruzioni di accesso vengono inviate all’ID e-mail dell’Amministratore dell’integrazione.

**Caricamento di dati (file .csv) in cartelle FTP o Box**

La creazione di un account FTP o Box è un prerequisito per la creazione di un progetto di migrazione. In questa fase puoi creare un progetto di migrazione e uno sprint nell’applicazione Learning Manager.  Fare riferimento a **Procedura di migrazione di dati e contenuti** in questa pagina per creare un progetto di migrazione.

Nell’account FTP o Box, fai clic sul nome della cartella del progetto e quindi sul nome dello sprint. All&#39;interno della cartella sprint, puoi caricare i file di dati .csv che desideri migrare. Per caricare, fai clic sul pulsante Carica file in alto nel server FTP o Box e rilascia i file .csv. Di seguito è riportata un’istantanea di esempio dopo il caricamento su FTP come riferimento.

<!--![](assets/exavault-upload.png)-->

Puoi tornare al progetto di migrazione di Learning Manager, fare clic su **[!UICONTROL Aggiorna]** e visualizzare tutti i tipi di dati .csv elencati nello sprint di migrazione.

**Caricamento dei contenuti di formazione nelle cartelle dei contenuti**

Carica il contenuto di formazione del tuo LMS esistente nell’account Box. Se hai già creato il progetto di migrazione e lo sprint, l’account Box popolerà il progetto di migrazione e il nome dello sprint. Puoi caricare il contenuto nello stesso percorso. Fare riferimento a **Procedura di migrazione di dati e contenuti** in questa pagina per creare un progetto di migrazione.

Puoi trascinare e rilasciare i file di contenuto o fare clic su **[!UICONTROL Carica]** e seleziona i file dal desktop. Se i file sono di grandi dimensioni, potresti notare dei ritardi nel caricamento dei file. A seconda delle dimensioni del file, il tempo necessario per caricarli nell’account Box varia.

Di seguito è riportata un’istantanea dell’account Box di esempio dopo il caricamento dei contenuti, come riferimento:

![](assets/box-account.png)

*File nell’account Box*

Dopo aver caricato i file nell’account Box, assicurati di indicare il percorso relativo del file di contenuti Box nel file module_version.csv. Questo passaggio è obbligatorio per indicare il percorso del contenuto del modulo.

Una volta effettuato l’accesso ai server FTP e Box e caricato il contenuto, i percorsi CSV vengono visualizzati come mostrato nell’istantanea seguente in Learning Manager.

![](assets/after-setup.jpg)

*Percorsi CSV nell’account Box*

## Procedura di migrazione di dati e contenuti {#dataandcontentmigrationprocedure}

La procedura per migrare i dati e i contenuti dell’LMS aziendale a Learning Manager viene descritta di seguito:

Verifica i prerequisiti del processo di migrazione prima di iniziare la migrazione. Fare riferimento a [Specifiche CSV e CSV di esempio](migration-manual.md#main-pars_header_140933605) in questa pagina e preparare i file CSV per la migrazione di dati e contenuti.

1. Accedi all’applicazione Learning Manager come Amministratore di integrazione e fai clic su **[!UICONTROL Migrazione]** nel riquadro sinistro.

   Viene visualizzata la home page dei progetti di migrazione. Se la tua organizzazione ha già creato progetti di migrazione, puoi visualizzare l&#39;elenco di tutti i progetti di migrazione in questa pagina.

1. Fai clic **[!UICONTROL Nuovo]** nell’angolo in alto a destra della pagina, per creare un progetto di migrazione. In alternativa, potete fare clic su **[!UICONTROL Creare un progetto di migrazione]** nella pagina per creare un progetto di migrazione. Viene visualizzata la pagina Crea un progetto di migrazione.

   Se non hai ancora creato una cartella FTP, ti verrà chiesto di creare una cartella FTP nell’account. Si tratta di un passaggio obbligatorio prima di iniziare a creare un progetto di migrazione.

   ![](assets/create-project.png)
   *Crea cartella FTP*

   Fornisci il nome del progetto, il tag del progetto, il catalogo del corso e la descrizione del progetto di migrazione. Fai clic **[!UICONTROL Crea]**.

   Gli elementi dei dati di migrazione vengono identificati utilizzando questo tag del progetto di migrazione. Se non disponi di un catalogo dei corsi specifico, seleziona il catalogo predefinito dal menu a discesa. Tutti i corsi migrati utilizzando un progetto di migrazione verranno inclusi nel catalogo scelto in questa fase. Se non scegli alcun catalogo, tutti i corsi migrati faranno parte del catalogo predefinito.

1. Viene visualizzata la pagina di configurazione dello sprint come illustrato nell&#39;istantanea seguente. È necessario creare uno sprint come parte del progetto di migrazione. Scegli Nome sprint e fornisci una breve descrizione dello sprint. Puoi scegliere Sì se desideri migrare il contenuto come parte di questo sprint. Fai clic **[!UICONTROL Avanti]**.

   ![](assets/users-modified-sprint.png)
   *Migrazione sprint*

   Seleziona la casella di controllo con il titolo **Gli utenti sono stati aggiunti o modificati dall&#39;ultima esecuzione**, per sincronizzare l’elenco degli utenti con l’applicazione Learning Manager. Se stai eseguendo la migrazione di contenuti e dati all’applicazione Learning Manager, questa operazione potrebbe non essere richiesta. Tuttavia, se è trascorso un certo intervallo di tempo tra la precedente migrazione sprint e l’ultima, è consigliabile sincronizzare l’elenco degli utenti. Questo passaggio consente la sincronizzazione del database Learning Manager con gli utenti dell’LMS.

   Questo passaggio di sincronizzazione è consigliato durante la migrazione di enrollment.csv e user_course_grade.csv. Questo passaggio consente la sincronizzazione del database Learning Manager con il database di migrazione e garantisce che tutti gli utenti i cui record devono essere migrati nello sprint siano disponibili nel database di migrazione.

1. Puoi avviare la migrazione sprint con i dati e i contenuti caricati. Fai clic **[!UICONTROL Aggiorna]** prima di avviare l’esecuzione dello sprint per sincronizzare le cartelle FTP e dei contenuti con l’applicazione Learning Manager.

   ![](assets/sprint1-filesupload.png)
   *Avvia migrazione sprint*

   Fai clic **[!UICONTROL Inizia]** nell’angolo in alto a destra della pagina. È possibile fare clic su **[!UICONTROL Interrompi]** in qualsiasi momento durante il processo di migrazione sprint, per interrompere la migrazione.

   Lo stato della migrazione viene visualizzato su ciascuno degli elementi dati e del contenuto dello sprint. Verifica il numero di elementi riusciti e non riusciti durante l’esecuzione dello sprint di migrazione.

   Se stai caricando il contenuto di un modulo, assicurati che il percorso della cartella del contenuto sia specificato in module_version.csv. Se salti questo passaggio, potresti riscontrare errori durante la migrazione. Ad esempio, per caricare i contenuti di un modulo di autoformazione, come video, è necessario specificare il relativo percorso URL Box in module_version.csv. Per il contenuto del modulo Attività, puoi specificare il nome dell’URL.

   Di seguito viene fornita un’istantanea di esempio della finestra di dialogo di avanzamento, come riferimento. Come mostrato nell’istantanea, è possibile visualizzare il numero di record elaborati per ogni elemento dati di migrazione insieme allo stato degli elementi riusciti e non riusciti. Fai clic su Scarica record degli errori in base agli elementi non riusciti per scaricare e visualizzare i registri degli errori. Puoi correggere i problemi in CSV e caricarli di nuovo in FTP.

   ![](assets/sample-sprint-progress-status.png)
   *Visualizza avanzamento sprint*

   Per visualizzare l’elenco di tutti gli sprint di un progetto di migrazione, fai clic su Elenco sprint nel riquadro a sinistra. Puoi visualizzare un elenco di tutti gli sprint, il numero di esecuzioni per ogni sprint, la data di inizio, la durata e lo stato di completamento, come mostrato nell’istantanea di esempio seguente.

   ![](assets/sprint-list.png)
   *Visualizza elenco di sprint*

1. Dopo aver caricato i file CSV aggiornati più di recente, fai clic su Esegui di nuovo nell’angolo in alto a destra della pagina. Riesegui elabora nuovamente tutti gli elementi dati, ignorando quelli che non hanno alcuna modifica. Una volta completata la migrazione degli elementi dati in uno sprint, puoi contrassegnare la migrazione primaverile come completata facendo clic sul pulsante nella parte superiore della pagina. Puoi avviare un nuovo sprint con altri elementi dati in un secondo momento. Una volta contrassegnato lo sprint come completato, non è possibile rieseguirlo. Allo stesso modo, in un progetto di migrazione puoi avere un numero qualsiasi di sprint. Una volta ottenuto lo stato di migrazione di tutti gli sprint, puoi contrassegnare il progetto di migrazione come Completato facendo clic su **Contrassegna progetto come completato** nella pagina Elenco sprint.

   Prima di contrassegnare il progetto di migrazione come completato, devi assicurarti che tutti gli sprint del progetto siano completi. Una volta contrassegnato il progetto di migrazione come completato, non è possibile tornare indietro e creare eventuali sprint in tale progetto o apportare modifiche a tale progetto. Devi creare un altro progetto di migrazione e aggiungervi sprint.

## Verifica della migrazione {#registration}

Dopo la migrazione dei dati e dei contenuti di apprendimento dal sistema LMS legacy dell’organizzazione, puoi verificare i dati e i contenuti importati utilizzando varie funzionalità degli oggetti di apprendimento. Ad esempio, puoi accedere all’applicazione Learning Manager come Amministratore e verificare la disponibilità dei dati e dei contenuti dei moduli e corsi importati.

## Adattamento retroattivo nella migrazione {#retrofittinginmigration}

Questa funzione di integrazione consente di trasformare i dati storici di un oggetto di apprendimento da un sistema di gestione dell’apprendimento legacy a un corso attivo creato in Learning Manager.

Di seguito sono riportate le specifiche CSV standard che è possibile utilizzare per eseguire il mapping con i dati di migrazione LMS esistenti. Fai clic su specifiche csv e csv di esempio per scaricare i file zip. Il file csv-specific.zip scaricato contiene quattro fogli Excel. Questi fogli Excel sono specifiche con descrizioni per aiutarti a capire come riempire i file .csv. I file .csv corrispondenti devono contenere i dati per ogni campo nel formato prescritto, come spiegato in questi file .xlsx.

1-enrollment.xlsx-contiene le descrizioni dei metadati richiesti per il file retrofit_enrollment.csv.

2-certification_enrollment.xlsx-contiene le descrizioni dei metadati richiesti per il file retrofit_certification_enrollment.csv.

3-learning_program_enrollment.xlsx-contiene le descrizioni dei metadati richiesti per il file retrofit_learning_program_enrollment.csv.

4-user_course_grades.xlsx-contiene le descrizioni dei metadati richiesti per il file retrofit_user_course_grades.csv.
[csv-specific.zip](assets/csv-specifications.zip)

## Risoluzione dei problemi di migrazione {#troubleshootingmigrationissues}

[Fai clic qui](../../kb/troubleshooting-migration.md) per conoscere la soluzione ai problemi affrontati dagli Amministratori di integrazione durante la migrazione di dati e contenuti dall’LMS esistente all’applicazione Learning Manager.

## Suggerimenti per la gestione degli utenti {#usermanagement}

In questo argomento vengono forniti alcuni suggerimenti utili per comprendere come vengono considerati e gestiti gli utenti in Learning Manager. Questi concetti ti aiuteranno a gestire meglio gli utenti durante l’utilizzo dell’importazione CSV, dei connettori e delle funzioni di migrazione di Learning Manager.

## ID Learning Manager {#captivateprimeids}

Learning Manager offre due tipi di ID univoci per gli utenti:

* ID e-mail
* UUID (Univerally Unique Id)

Learning Manager supporta UUID per fornire flessibilità alle organizzazioni nel controllo degli account utente. In qualità di Amministratore, se disponi di UUID degli utenti in un account, puoi modificare gli ID e-mail degli utenti per tale account.

**Scenario di utilizzo dell’UUID in un’organizzazione**

Consideriamo uno scenario in cui un dipendente A entra a far parte di un’azienda denominata Learning Manager, come appaltatore. Durante il periodo del contratto, l’azienda di Learning Manager potrebbe non fornire l’ID e-mail dell’azienda come A@example.com, ma considerare solo l’account e-mail personale del dipendente, ad esempio A@gmail.com. Dopo aver completato 6 mesi di periodo di contratto, se lo stesso dipendente A si aggiunge a Learning Manager come dipendente a tempo pieno, Learning Manager potrebbe voler modificare il suo ID e-mail con l’ID e-mail dell’azienda: A@example.com.

L’accesso UUID all’account utente sarà vantaggioso per Learning Manager nello scenario sopra menzionato. L’azienda Learning Manager può facilmente sostituire l’ID e-mail personale del dipendente A con un ID e-mail ufficiale. Le registrazioni del dipendente relative a questo account non sono interessate da questa modifica.

## Identificazione utente singolo {#singleuseridentification}

Learning Manager identifica e ricorda la modalità di aggiunta di un singolo utente, ad esempio mediante registrazione automatica, tramite caricamento CSV, oppure utilizzando l’interfaccia utente o tramite API.

* Se viene aggiunto un singolo utente tramite l’interfaccia utente o l’API, puoi eliminare questo tipo di singoli utenti tramite l’interfaccia utente o l’API.
* Puoi aggiornare singoli utenti utilizzando la procedura di caricamento dei file CSV, ma devi ricordare che questi singoli utenti vengono trattati come utenti CSV e i flussi di lavoro CSV sono applicabili a tali utenti.

## Assegnazione del ruolo di Manager {#assigningmanagerrole}

Non è possibile assegnare direttamente un ruolo di Manager a nessun utente in Learning Manager. Un utente X può diventare Manager Learning Manager solo quando si imposta un attributo Manager di qualsiasi utente (ad esempio, Y) in quell’account come X.

In uno scenario in cui X è il Manager degli utenti, ad esempio, A, B e C, se X lascia l&#39;organizzazione, è necessario assicurarsi che l&#39;attributo Manager di A, B e C sia impostato sul nuovo Manager. In alternativa, puoi anche impostare temporaneamente l’attributo Manager di questi utenti come ROOT e assegnarlo successivamente con il nuovo nome Manager.

Per ulteriori informazioni su questo argomento, fare riferimento ai seguenti contenuti della Guida:

* [Domande frequenti sul caricamento di CSV](/help/migrated/administrators/add-users-in-bulk.md)
* [Guida all’aggiunta di utenti](/help/migrated/administrators/feature-summary/add-users-user-groups.md)

