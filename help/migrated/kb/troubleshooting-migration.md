---
description: Questo documento contiene suggerimenti per la risoluzione di alcuni dei problemi tipici che possono verificarsi durante la migrazione di dati e contenuti da un sistema LMS esistente a Learning Manager.
jcr-language: en_us
title: Risoluzione dei problemi di migrazione
contentowner: jayakarr
source-git-commit: 6abc118c6ad7e66e3ded5bd26b9167c3a0b99e4b
workflow-type: tm+mt
source-wordcount: '854'
ht-degree: 0%

---



# Risoluzione dei problemi di migrazione

Questo documento contiene suggerimenti per la risoluzione di alcuni dei problemi tipici che possono verificarsi durante la migrazione di dati e contenuti da un sistema LMS esistente a Learning Manager.

## Problemi di migrazione generici {#genericmigrationissues}

### Impossibile accedere alla cartella FTP o alla cartella dei contenuti {#unabletologintoftpfolderorcontentfolder}

Assicurati che gli account siano stati creati nei servizi FTP e Box. Quando crei un progetto di migrazione, richiedi di configurare questi due servizi. Non appena si creano i servizi, si ricevono e-mail da Exavault e Box per reimpostare o configurare le password. Se non ricordi le password, puoi reimpostarle visitando i siti Web di Exavault e Box.

### I processi non vengono visualizzati anche dopo aver fatto clic sul pulsante Aggiorna {#jobsarenotreflectedevenafterclickingrefreshbutton}

* Assicurati che i file CSV siano caricati nella cartella corretta in FTP Exavault. La struttura del percorso deve essere la seguente:

`code Account>Project>Sprint location`

* Assicurati che i nomi dei file CSV siano conformi ai nomi delle specifiche CSV:

   * course.csv
   * course_instance.csv
   * course_module.csv
   * enrollment.csv
   * module.csv
   * module_version.csv
   * user_course_grade.csv

### Gli errori vengono visualizzati per i processi con record degli errori {#failuresareshownforjobswitherrorrecords}

1. Scarica i registri degli errori facendo clic su **Scaricare i record degli errori** collegare
1. Correggi i file CSV originali in base agli errori segnalati e
1. Esegui nuovamente lo sprint con i file CSV modificati.

È consigliabile eseguire i file CSV modificati in un nuovo sprint quando il numero di modifiche è inferiore al numero totale di record.

### Impossibile accedere all’applicazione Learning Manager anche dopo l’interruzione della migrazione sprint {#unabletologintocaptivateprimeapplicationevenafterstoppingthesprintmigration}

Potrebbero essere necessari 10-15 minuti per sbloccare un account una volta interrotta o completata l’esecuzione dello sprint. Prova ad accedere all’applicazione dopo 15 minuti.

### Alcuni processi di migrazione visualizzano lo stato &quot;In corso&quot; anche dopo aver attivato &quot;Interrompi&quot;. {#someofthemigrationjobsdisplayinprogressstatusevenafterstopistriggered}

Potrebbero essere necessari 10-15 minuti per interrompere l&#39;esecuzione di tutti i processi quando è in stato &quot;In corso&quot;. Controlla di nuovo lo stato dopo 10 minuti.

### Impossibile creare uno sprint perché il pulsante è disattivato {#unabletocreateasprintasthebuttonisdisabled}

Prima di creare uno sprint, assicurati che lo sprint corrente sia contrassegnato come completato. Fai clic **[!UICONTROL Contrassegna sprint come completato]** nella parte superiore della pagina per completare la migrazione sprint.

### Impossibile contrassegnare un progetto di migrazione come completato perché il pulsante è disattivato {#unabletomarkamigrationprojectascompleteasthebuttonisdisabled}

Assicurati che lo sprint corrente sia contrassegnato come completato prima di contrassegnare il completamento del progetto di migrazione. Fai clic **[!UICONTROL Contrassegna sprint come completato]** nella parte superiore della pagina per completare la migrazione sprint.

## Problemi con CSV {#csvissues}

### la migrazione del file module_version.csv non va a buon fine e la migrazione dei contenuti non è ancora avvenuta. {#moduleversioncsvfilemigrationisfailingandcontentisnotmigratedyet}

Assicurati che il contenuto sia disponibile nella cartella Contenuto (account Box nel progetto di migrazione specificato, percorso sprint). Assicurati inoltre di aver selezionato l’opzione **Sì** per **Vuoi migrare contenuti per questo sprint?** nella pagina di creazione dello sprint.

Se dimentica di selezionare **Sì**, e procedi con lo sprint, poi devi aspettare fino al completamento dello sprint. Crea un altro sprint e assicurati di fare clic su **[!UICONTROL Sì]**.

### I record enrollment.csv o user_course_grade.csv non vanno a buon fine e restituiscono il messaggio di errore &quot;ID Learning Manager non valido&quot; {#enrollmentcsvorusercoursegradecsvrecordsfailwithanerrormessagenotavalidprimeid}

Assicurati che l’ID e-mail fornito nei campi userId, assignedByUserID appartenga a utenti validi di Learning Manager. In caso contrario, aggiungi l’utente e crea un nuovo sprint con **Sincronizza utenti** opzione selezionata. Nel caso in cui l’utente non faccia parte dell’organizzazione, aggiungilo come utente eliminato in Learning Manager utilizzando la specifica CSV Aggiungi utenti. Di seguito è fornita una specifica CSV di esempio per aggiungere utenti eliminati come riferimento.

[Users.csv](assets/users.zip) Fare riferimento a **Specifiche CSV e CSV di esempio** sezione in [Manuale di migrazione](../integration-admin/feature-summary/migration-manual.md) per scaricare un set completo di specifiche CSV e file CSV di esempio.

### Corsi vuoti o riproduzione di moduli errati per un corso migrato {#coursesappearblankorincorrectmodulesplayforamigratedcourse}

Assicurati che **moduleOrderInCourse** valore chiave per un corso inizia con **0** ed è in ordine continuo. L’ordine in termini di courseModuleType deve essere PRETEST, TESTOUT, CONTENT

Inoltre, assicurati che due versioni di Attività, Aula e Aula virtuale non siano collegate al corso esistente.

### Ricezione del messaggio &quot;Il modulo è già collegato a un corso esistente&quot; {#receivingamessageasmoduleisalreadylinkedwithanexistingcourse}

Learning Manager non consente di collegare il modulo Attività/Aula virtuale/Aula a più di un corso. Assicurati che il modulo non sia collegato ad altri corsi.

### Tutti i corsi mostrano la versione più recente dei moduli Attività/Aula virtuale/Aula anche se i corsi sono collegati con diverse versioni del modulo {#allthecoursesshowthelatestversionofactivityvcclassroommoduleseventhoughthecoursesarelinkedwithdifferentmoduleversions}

Il controllo delle versioni dei moduli Attività, Aula e Aula virtuale non è supportato in Learning Manager. Se fornisci le versioni tramite il file moduleVersion.csv, il file esistente viene aggiornato anziché crearne una nuova.

### La durata desiderata non viene visualizzata per un modulo Attività/Aula virtuale/Aula migrato {#desireddurationdoesnotappearforamigratedactivityvcclassroommodule}

La durata desiderata non è una voce valida per il modulo Attività/Aula virtuale/Aula.

### L’URL del collegamento ipertestuale non si apre in Learning Manager {#hyperlinkurldoesntopenupincaptivateprime}

Assicurati che i collegamenti forniti siano pre-impostati con &quot;http://&#39;&quot; o &quot;https://&#39;&quot;

### La migrazione di moduleVersion non va a buon fine e restituisce errori di tipo &quot;File non trovato&quot; {#moduleversionmigrationfailswithfilenotfounderrors}

Assicurati che il file di riferimento sia presente nella cartella dei contenuti e che la migrazione sia stata completata correttamente.

### La migrazione di moduleVersion non va a buon fine e restituisce il messaggio di errore &quot;Si è verificato un errore interno - per Module : x e moduleVersion : y&quot; {#moduleversionmigrationfailswithanerrormessageasaninternalerrorhasoccurredformodulexandmoduleversiony}

Esegui nuovamente lo sprint per risolvere il problema.
