---
jcr-language: en_us
title: Guida alla distribuzione di Learning Manager - Sezione 2
contentowner: sanm
preview: true
source-git-commit: fba5e5ddc1964b485be473bf356806f234688cf4
workflow-type: tm+mt
source-wordcount: '2232'
ht-degree: 0%

---



# Guida alla distribuzione di Learning Manager - Sezione 2

## Configurazione tecnica {#technicalsetup}

La configurazione tecnica dell’account Learning Manager è richiesta principalmente per gli utenti aziendali. In questo documento viene illustrata la configurazione dell’accesso Single Sign On per l’organizzazione e l’integrazione di Learning Manager con connettori di terze parti.

### Configurazione Single Sign-On {#configuresinglesignon}

In qualità di amministratore di sistema nell&#39;Admin Console, una delle prime attività è definire e configurare un sistema di identità in base al quale gli utenti finali verranno autenticati. Poiché l’organizzazione acquista licenze per Learning Manager, dovrai fornire tali licenze agli utenti finali. E per questo, avrai bisogno di un modo per autenticare questi utenti. Per configurare l&#39;SSO per gli utenti, segui la procedura riportata di seguito.

1. Nella home page di Learning Manager, fai clic su **[!UICONTROL ** Impostazioni **>** Metodi di accesso **.]**

   ![](assets/configure-sso-step1.png)

1. A seconda del tipo di utente, seleziona **[!UICONTROL ** Utenti interni **oppure** Utenti esterni **.]**



1. Dal **[!UICONTROL **Accesso**]**campo a discesa, seleziona **[!UICONTROL ** Single Sign-On **.]**

   ![](assets/configure-sso-step3.png)

1. Per configurare le impostazioni Single Sign-On, fai clic su **[!UICONTROL ** Modifica **.]**

   ![](assets/configure-sso-step4.png)

1. Nella ****[!UICONTROL URL di autenticazione avviata da IDP]**** , immetti l’URL di autenticazione fornito dal provider di servizi.



   ![](assets/configure-sso-step5.png)

1. Fai clic su **[!UICONTROL **Carica **]**accanto a**[!UICONTROL  **File XML metadati IDP **]******e caricare il file XML.
1. Fai clic **[!UICONTROL ** Salva **.]**
1. L’autenticazione SSO è stata configurata correttamente per l’account. Dovresti essere in grado di accedere al tuo account Learning Manager utilizzando l’SSO.

   ***L’SSO configurato in Learning Manager deve supportare SAML 2.0.***

## Migrazione dei dati utente {#migrationofuserdata}

In qualità di amministratore, quando l’azienda acquista Learning Manager, uno dei passaggi fondamentali da eseguire è la migrazione. È fondamentale spostare i contenuti di formazione esistenti e i dati degli utenti in Learning Manager. Il seguente flusso di lavoro di migrazione consente di sfruttare i vantaggi di un LMS moderno e intuitivo senza perdere i dati legacy dell’organizzazione.

Learning Manager consente di eseguire la migrazione dal sistema LMS esistente tramite una procedura guidata dettagliata, in sprint iterativi. Ottieni una visibilità completa sullo stato di ogni sprint per garantire che gli Allievi non subiscano tempi di inattività durante la migrazione dei dati legacy ad Adobe Learning Manager.

Per eseguire il flusso di lavoro di migrazione, è necessario disporre dei privilegi di Amministratore dell’integrazione. In qualità di Amministratore, puoi assumere il ruolo di Amministratore dell’integrazione oppure assegnare questo ruolo a un altro utente.

**Qui possiamo usare l&#39;aiuto di Shaleen per creare un&#39;immagine.**

1. Prerequisito
1. Valutazione dei contenuti esistenti e dei dati degli utenti
1. Esportare e mappare i dati dal sistema LMS esistente
1. Configurazione delle cartelle FTP e BOX per la migrazione
1. Trasferimento degli Allievi in Learning Manager
1. Trasferimento dei contenuti di apprendimento in Learning Manager
1. Trasferimento dei dati rimanenti in Learning Manager



### Prerequisito {#prerequisite}

Prima di avviare il processo di migrazione, è necessario eseguire i seguenti prerequisiti:

* Estrazione di dati e contenuti dall’LMS in uso e trasformazione dei dati nei formati di file definiti da Learning Manager.
* Importazione di utenti che utilizzano connettori FTP e BOX. L’Amministratore dell’integrazione deve assicurarsi che i connettori siano configurati prima del processo di migrazione.



***Si consiglia che gli Amministratori eseguano una prova del processo di migrazione in un account di prova prima di migrare dati e contenuti nell’ambiente di produzione di Learning Manager. ***

### Valutazione ed esportazione dei dati {#evaluatingandexportingdata}

L’Amministratore dell’integrazione deve innanzitutto esaminare i dati disponibili nel sistema LMS corrente. In qualità di Amministratore dell’integrazione, puoi migrare solo i seguenti oggetti di apprendimento:

* Modulo
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
* Iscrizioni
* Iscrizione certificazione
* Iscrizione al programma di apprendimento
* Livelli corso utente



Dopo aver valutato i dati esistenti, devi mappare questi dati con le specifiche CSV standard in Learning Manager. Scarica il seguente esempio ***csv-specific.zip*** file contenente sette fogli Excel necessari per la migrazione. Questi fogli Excel contengono specifiche con descrizioni che consentono di capire come mappare i dati esistenti con i campi nei file .csv.

<!--
<Download link to the zip file>
-->

Assicurati che ogni file .csv contenga i dati per ogni campo nel formato prescritto:

<table> 
 <tbody> 
  <tr> 
   <th width="7%" valign="top"><p><strong>No.</strong></p></th> 
   <th width="29%" valign="top"><p><strong>Nome foglio Excel</strong></p></th> 
   <th width="31%" valign="top"><p><strong>Descrizione del contenuto</strong></p></th> 
   <th width="31%" valign="top"><p><strong>Note</strong></p></th> 
  </tr> 
  <tr> 
   <td><p>1</p></td> 
   <td><p>module.xlsx</p></td> 
   <td><p>metadati per module.csv;</p></td> 
   <td><p> </p></td> 
  </tr> 
  <tr> 
   <td><p>2</p></td> 
   <td><p>course.xlsx</p></td> 
   <td><p>Metadati per course.csv</p></td> 
   <td><p>Indica il nome di un autore per un determinato corso poiché a volte i nomi di più autori non vengono visualizzati in modo accurato nell’applicazione dopo la migrazione. </p></td> 
  </tr> 
  <tr> 
   <td><p>3</p></td> 
   <td><p>module_version.xlsx </p></td> 
   <td><p>Metadati per module_version.csv</p></td> 
   <td><p>Assicurati di fornire il percorso URL della cartella dell’account Box in cui hai caricato il contenuto. </p></td> 
  </tr> 
  <tr> 
   <td><p>4</p></td> 
   <td><p>course_instance.xlsx</p></td> 
   <td><p>metadati per course_instance.csv; </p></td> 
   <td> </td> 
  </tr> 
  <tr> 
   <td><p>5</p></td> 
   <td><p>course_module.xlsx</p></td> 
   <td><p>Metadati per course_module.csv</p></td> 
   <td> </td> 
  </tr> 
  <tr> 
   <td><p>6</p></td> 
   <td><p>skill.xlsx</p></td> 
   <td><p>metadati per skill.csv;</p></td> 
   <td> </td> 
  </tr> 
  <tr> 
   <td><p>7</p></td> 
   <td><p>skill_level.xlsx</p></td> 
   <td><p>Metadati per skill_level.csv</p></td> 
   <td> </td> 
  </tr> 
  <tr> 
   <td><p>8</p></td> 
   <td><p>skill_course.xlsx</p></td> 
   <td><p>metadati per skill_course.csv</p></td> 
   <td> </td> 
  </tr> 
  <tr> 
   <td><p>9</p></td> 
   <td><p>Certification.xlsx</p></td> 
   <td><p>Metadati per Certification.csv</p></td> 
   <td> </td> 
  </tr> 
  <tr> 
   <td><p>10</p></td> 
   <td><p>certification_course.xlsx</p></td> 
   <td><p>Metadati per certification_course.csv</p></td> 
   <td> </td> 
  </tr> 
  <tr> 
   <td><p>11</p></td> 
   <td><p>certification_commit.xlsx</p></td> 
   <td><p>Metadati per certification_commit.csv</p></td> 
   <td> </td> 
  </tr> 
  <tr> 
   <td><p>12</p></td> 
   <td><p>learning_program.xlsx</p></td> 
   <td><p>Metadati per learning_program.csv</p></td> 
   <td> </td> 
  </tr> 
  <tr> 
   <td><p>13</p></td> 
   <td><p>learning_program_course.xls </p></td> 
   <td><p>Metadati per learning_program_course.csv </p></td> 
   <td> </td> 
  </tr> 
  <tr> 
   <td><p>14</p></td> 
   <td><p>learning_program_instance.xlsx </p></td> 
   <td><p>Metadati per learning_program_instance.csv</p></td> 
   <td> </td> 
  </tr> 
  <tr> 
   <td><p>15</p></td> 
   <td><p>learning_program_instance_course_instance.xlsx </p></td> 
   <td><p>Metadati per learning_program_instance_course_instance.csv</p></td> 
   <td> </td> 
  </tr> 
  <tr> 
   <td><p>16</p></td> 
   <td><p>enrollments.xlsx</p></td> 
   <td><p>Metadati per enrollments.csv</p></td> 
   <td> </td> 
  </tr> 
  <tr> 
   <td><p>17</p></td> 
   <td><p>certification_enrollment.xlsx</p></td> 
   <td><p>Metadati per certification_enrollment.csv</p></td> 
   <td> </td> 
  </tr> 
  <tr> 
   <td><p>18</p></td> 
   <td><p>learning_program_enrollment.xlsx</p></td> 
   <td><p>Metadati per learning_program_enrollment.csv</p></td> 
   <td> </td> 
  </tr> 
  <tr> 
   <td><p>19</p></td> 
   <td><p>User_course_grade.xlsx</p></td> 
   <td><p>Metadati per User_course_grade.csv</p></td> 
   <td><p>Fornisci i dati dei record Allievo richiesti nel file .csv anche se non sono obbligatori. Senza queste informazioni, anche se il file .csv viene elaborato per la migrazione, l’applicazione Learning Manager potrebbe non riflettere alcun dato. </p></td> 
  </tr> 
 </tbody> 
</table>

***Learning Manager supporta solo i valori di data e ora in formato UTF a 8 e 32 bit. È possibile che si verifichino errori durante la migrazione se nei file CSV si specifica una data fuori intervallo, ad esempio 2038-07-17T08:53:21.000Z o 1980-04-17T08:13:25.322Z***

### Dipendenze durante l’importazione dei dati nei file CSV {#dependencieswhileimportingdatatocsvfiles}

Durante l’importazione dei dati esistenti nel formato csv standard, tieni presente le seguenti dipendenze:

* module_version.csv dipende da module.csv
* course_instance.csv dipende da course.csv
* course_module.csv dipende da course.csv, module.csv e module_version.csv
* course_instance.csv dipende da course.csv
* enrollment.csv dipende da course.csv
* user_course_grade.csv dipende da course.csv e module.csv
* skill_course.csv dipende da course.csv
* skill_level.csv dipende da skill.csv
* learning_program_instance.csv dipende dal programma di apprendimento e learning_program_course.csv
* learning_program_course.csv dipende da learning_program.csv
* learning_program_enrollment.csv dipende dal programma di apprendimento e learning_program_instance.csv
* learning_program_instance_course_instance.csv dipende da learning_program.csv, learning_program_instance.csv e course_instance.csv
* certification_course.csv dipende da certification.csv e course.csv
* certification_commit.csv dipende da certification.csv e certification_course.csv
* certification_enrollment.csv dipende da certification.csv, certification_course.csv e certification_enrollment.csv



Dopo aver esportato i dati, salva i file .csv nel computer locale. I file sono ora pronti per essere rilasciati nelle cartelle FTP o BOX.

## Configurazione delle cartelle FTP e BOX per la migrazione {#setupftpandboxfoldersforthemigration}

Prima di pianificare e avviare la migrazione effettiva di tutto il contenuto, è necessario configurare prima le cartelle FTP e BOX. Queste cartelle sono necessarie per rilasciare i file .csv in queste cartelle. Una volta che il contenuto legacy, sotto forma di file .csv, è disponibile nelle cartelle FTP e BOX, Learning Manager può utilizzare i dati.

### Configurare un account FTP {#setupanftpaccount}

Nella home page dell’Amministratore dell’integrazione, fai clic su **[!UICONTROL ** Richiesta di cartella FTP CSV **.]** Nella finestra a comparsa visualizzata, immetti l’ID e-mail. Segui la procedura guidata online per creare l’account FTP Exavault. Una volta creato l’account, puoi visualizzare le cartelle del progetto di migrazione e del progetto di sprint in FTP Exavault.

Consulta un’istantanea di esempio dei file di progetto e della cartella di ExaVault, come mostrato qui:

![](assets/set-up-an-ftp-account.png)

Una volta configurata correttamente la cartella FTP, il sistema visualizza il messaggio &quot;Impostazione cartella FTP completata&quot;.

## Configurazione di un account BOX {#setupaboxaccount}

Per creare un account BOX e impostare una cartella BOX, effettua le seguenti operazioni:

Nella home page dell’Amministratore dell’integrazione, seleziona Migrazione.

Nella sezione Configurazione, fai clic su Richiedi una cartella Box.

![](assets/set-up-a-box-account.png)

Nella ****[!UICONTROL Immetti e-mail]**** , immetti l’ID e-mail in cui desideri ricevere le istruzioni di accesso per la connessione a Box.

Fai clic **[!UICONTROL ** Connetti **.]**

Riceverai un’e-mail da Box con il collegamento alla cartella condivisa. Se non disponi di un account Box, fai clic su Registrati e crea un account. Le istruzioni di accesso vengono quindi inviate all’ID e-mail dell’Amministratore dell’integrazione.

Dopo aver salvato la connessione, nella pagina di migrazione viene visualizzato il messaggio: &quot;Impostazione cartella Box completata&quot;.

## Migrazione del contenuto a Learning Manager {#migratingthecontenttocaptivateprime}

Prima di avviare la migrazione, è importante tenere presente quanto segue:

* In un account può essere attivo un solo progetto di migrazione in qualsiasi momento. All’interno di un progetto, solo uno sprint può essere attivo in un dato momento.
* Non è possibile annullare un&#39;esecuzione già in corso. Tuttavia, puoi utilizzare l’opzione di eliminazione esistente all’interno di ciascuna funzionalità di Learning Manager per annullare qualsiasi migrazione di dati o contenuti.

Non appena viene avviato il progetto di migrazione, lo stato del progetto cambia in &quot;Migrazione in corso&quot;. In questo stato, nessun altro utente oltre all’Amministratore dell’integrazione può accedere a Learning Manager.

Caricamento dei contenuti di formazione nelle cartelle dei contenuti:

Nella home page dell’Amministratore dell’integrazione, fai clic su **[!UICONTROL Migrazione.]**

Nella home page della migrazione, vengono visualizzati i progetti di migrazione già creati nell’organizzazione.

Fai clic su **[!UICONTROL **Nuovo**]**in alto a destra nella pagina, per creare un progetto di migrazione.

***Se non hai già creato una cartella FTP, ti verrà chiesto di creare un account Exavault della cartella FTP. Si tratta di un passaggio obbligatorio prima di iniziare a creare un progetto di migrazione. ***

Nella ****[!UICONTROL Crea un nuovo progetto di migrazione]**** , specifica il nome del progetto.

![](assets/migrating-the-content-1.png)

Specifica un tag per il progetto, il catalogo del corso e fornisci una descrizione del progetto di migrazione. Gli elementi dei dati di migrazione vengono identificati utilizzando il tag del progetto di migrazione. Se non disponi di un catalogo dei corsi specifico, seleziona il catalogo predefinito dal menu a discesa, tutti i corsi che vengono migrati utilizzando un progetto di migrazione verranno inclusi nel catalogo scelto in questa fase. Se non scegli alcun catalogo, tutti i corsi migrati faranno parte del catalogo predefinito.

Fai clic **[!UICONTROL Crea.]**

Nella pagina Configurazione sprint, crea uno sprint per il progetto di migrazione. Nel processo di migrazione di Learning Manager, uno sprint definisce un set di elementi di migrazione che si desidera migrare dall’LMS esistente.

![](assets/migrating-the-content-2.png)

Specificate un nome per lo sprint e fornite una descrizione per lo sprint.

Selezionare il ****[!UICONTROL Casella di controllo Gli utenti sono stati aggiunti o modificati dopo l&#39;ultima esecuzione]****, per sincronizzare l’elenco degli utenti con l’applicazione Learning Manager. Se stai eseguendo la migrazione di contenuti e dati all’applicazione Learning Manager, questa operazione potrebbe non essere richiesta. Tuttavia, se è trascorso un certo intervallo di tempo tra la precedente migrazione sprint e l’ultima, è consigliabile sincronizzare l’elenco degli utenti. Questo passaggio consente la sincronizzazione del database Learning Manager con gli utenti dell’LMS.

***La sincronizzazione è consigliata durante la migrazione di enrollment.csv e user_course_grade.csv. Questo passaggio consente la sincronizzazione del database Learning Manager con il database di migrazione e garantisce che tutti gli utenti i cui record devono essere migrati nello sprint siano disponibili nel database di migrazione.***

Fai clic **[!UICONTROL ** Avanti **.]**

Fai clic su **[!UICONTROL **Inizia**]**per avviare la migrazione sprint con i dati e i contenuti caricati. Fai clic ****[!UICONTROL Aggiorna]**** prima di avviare l’esecuzione dello sprint per sincronizzare le cartelle FTP e dei contenuti con Learning Manager.

![](assets/migrating-the-content-3.png)

È possibile fare clic su ****[!UICONTROL Interrompi]****in qualsiasi momento durante il processo di migrazione sprint, per interrompere la migrazione.

Il sistema visualizza lo stato della migrazione per ciascuno dei contenuti e degli elementi dati dello sprint. Verifica il numero di elementi riusciti e non riusciti durante l’esecuzione dello sprint di migrazione.

Se stai caricando il contenuto di un modulo, assicurati che il percorso della cartella del contenuto sia specificato nel file *module_version.csv *. Se salti questo passaggio, potresti riscontrare errori durante la migrazione. Ad esempio, per caricare i contenuti di un modulo di autoformazione, come video, è necessario specificare il relativo percorso URL Box nel file *module_version.csv *.

Di seguito viene fornita un’istantanea dello stato di avanzamento della migrazione come riferimento. Come mostrato nell’istantanea, è possibile visualizzare il numero di record elaborati per ogni elemento dati di migrazione insieme allo stato degli elementi riusciti e non riusciti. Fai clic su Scarica record degli errori in base agli elementi non riusciti per scaricare e visualizzare i registri degli errori. Puoi correggere i problemi in CSV e caricarli di nuovo in FTP.

![](assets/migrating-the-content-4.png)

Per visualizzare l’elenco di tutti gli sprint di un progetto di migrazione, fai clic su **[!UICONTROL **Sprint**]**nel riquadro di navigazione a sinistra. Puoi visualizzare un elenco di tutti gli sprint, il numero di esecuzioni per ogni sprint, la data di inizio, la durata e lo stato di completamento, come mostrato nell’istantanea di esempio seguente.

![](assets/migrating-the-content-5.png)

Per visualizzare l’elenco di tutti gli sprint di un progetto di migrazione, fai clic su **[!UICONTROL **Sprint**]**nel riquadro di navigazione a sinistra. Puoi visualizzare un elenco di tutti gli sprint, il numero di esecuzioni per ogni sprint, la data di inizio, la durata e lo stato di completamento, come mostrato nell’istantanea di esempio seguente.

Per visualizzare l’elenco di tutti gli sprint di un progetto di migrazione, fai clic su **[!UICONTROL **Sprint**]**nel riquadro di navigazione a sinistra. Puoi visualizzare un elenco di tutti gli sprint, il numero di esecuzioni per ogni sprint, la data di inizio, la durata e lo stato di completamento, come mostrato nell’istantanea di esempio seguente.

***Prima di contrassegnare il progetto di migrazione come completato, assicurati che tutti gli sprint nel progetto siano completi. Una volta contrassegnato il progetto di migrazione come completato, non è possibile tornare indietro e creare eventuali sprint in tale progetto. Non è possibile apportare modifiche al progetto. Puoi solo creare un altro progetto di migrazione e aggiungervi sprint.***

Dopo aver eseguito la migrazione dei dati e dei contenuti di apprendimento dal sistema LMS legacy della tua organizzazione, verifica che i dati e i contenuti siano stati importati correttamente. Puoi eseguire la verifica accedendo come Amministratore e verificando la disponibilità dei dati e dei contenuti dei moduli e corsi importati

Per risorse utili sulla migrazione, consulta i seguenti riferimenti:

* Risoluzione dei problemi di migrazione
* Domande frequenti sul caricamento di CSV

