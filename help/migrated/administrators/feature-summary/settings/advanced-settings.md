---
description: Ulteriori informazioni sulla configurazione delle impostazioni avanzate in Adobe Learning Manager
jcr-language: en_us
title: Impostazioni avanzate in Adobe Learning Manager
exl-id: 7047c89f-5f1c-4e0a-a908-20ef0eb9667d
source-git-commit: 0862e0d042fac74377b44c3387a72336ec625161
workflow-type: tm+mt
source-wordcount: '2357'
ht-degree: 1%

---

# Impostazioni avanzate in Adobe Learning Manager

## Etichette del catalogo

Le etichette del catalogo in Adobe Learning Manager vengono utilizzate per contrassegnare gli oggetti di apprendimento (corsi, certificazioni, percorsi di apprendimento e così via) con campi e valori specifici. Queste etichette aiutano l&#39;utente e gli autori a classificare e organizzare i contenuti in modo efficace, consentendo un migliore filtraggio, tracciamento e reporting.

Per ulteriori informazioni, vedere [Etichette del catalogo in Adobe Learning Manager](/help/migrated/administrators/feature-summary/catalog-labels.md).


>[!NOTE]
>
>* Etichette obbligatorie: puoi scegliere di rendere le etichette del catalogo obbligatorie per gli autori durante la creazione del corso.
>* Flusso di lavoro dell’Autore: gli Autori devono aggiungere etichette di conformità durante la creazione o la modifica dei corsi per garantire una corretta categorizzazione.

## Cartella dei contenuti

Le cartelle dei contenuti di Adobe Learning Manager consentono agli autori di visualizzare e accedere ai contenuti nella libreria dei contenuti. Grazie alle cartelle dei contenuti gerarchiche, gli amministratori possono organizzare librerie di contenuti di grandi dimensioni in un massimo di tre livelli di cartelle private nidificate, semplificando la ricerca, la gestione e il riutilizzo dei contenuti all&#39;interno dell&#39;organizzazione.

### Che cos&#39;è una cartella di contenuti

Una cartella di contenuti è un contenitore che raggruppa i contenuti correlati e determina chi può accedervi. Ogni file di contenuto in Adobe Learning Manager appartiene sempre ad almeno una cartella.

Esistono due tipi di cartelle dei contenuti:

**Cartella pubblica**- presente in ogni account per impostazione predefinita. La cartella pubblica dispone delle seguenti proprietà:

* Tutti gli autori dell’account possono accedere al contenuto della cartella pubblica.
* Il contenuto della cartella pubblica non può trovarsi in alcuna cartella privata. È vero anche il contrario. Il contenuto di una cartella privata non può trovarsi nella cartella pubblica.
* La cartella pubblica non fa parte della configurazione di accesso basata sui ruoli. La limitazione di un ruolo personalizzato a cartelle private specifiche non limita l&#39;accesso alla cartella pubblica.

**Cartelle private**- create dagli amministratori. Le cartelle private supportano una gerarchia a tre livelli e il loro accesso è controllato tramite la configurazione dei ruoli.

**Comprendere i livelli della gerarchia di cartelle**

Le cartelle dei contenuti privati supportano fino a tre livelli di nidificazione:

* **Cartelle di livello 1**: cartelle di livello superiore nella cartella principale della raccolta di contenuti

* **Cartelle di livello 2**- sottocartelle nidificate in una cartella di livello 1

* **Cartelle di livello 3**- sottocartelle nidificate in una cartella di livello 2

Questa struttura offre alle organizzazioni la flessibilità di rispecchiare l&#39;organizzazione dei contenuti reali, in base all&#39;area tematica, al tipo di distribuzione, al pubblico o al team, anziché gestire migliaia di file in un elenco semplice.

Solo gli amministratori possono creare, modificare o eliminare le cartelle a qualsiasi livello. Autori e utenti personalizzati interagiscono con la gerarchia ma non possono modificarla.

### Regole di denominazione delle cartelle

I nomi delle cartelle devono essere univoci all’interno dello stesso livello all’interno della stessa cartella principale. In particolare:

| **Scenario** | **Consentito?** |
|----------------------------------------------------------------------------------------------|--------------------------|
| Due cartelle di livello 1 con lo stesso nome | No |
| Due cartelle di livello 2 nella stessa cartella di livello 1 con lo stesso nome | No |
| Due cartelle di livello 2 in cartelle di livello 1 diverse con lo stesso nome | Sì |
| Una cartella Level 2 e una cartella Level 3 con lo stesso nome | Sì. I livelli sono distinti |
| Una cartella di livello 3 e un&#39;altra cartella di livello 3 nello stesso livello 2 con lo stesso nome | No |


### Come vengono visualizzati i percorsi delle cartelle

Nella Libreria dei contenuti viene visualizzato il percorso completo della cartella di ogni file di contenuto. Ad esempio, **Programmi di formazione** > **Onboarding** > **Risorse SCORM**. Questo percorso mostra la posizione completa del contenuto.

Se un file è presente in più cartelle, tutti i percorsi vengono visualizzati separati da virgole. Se un percorso è lungo, viene troncato dall&#39;inizio con un&#39;ellisse (...) e viene sempre visualizzato il nome della cartella più profonda.

### Accesso alle cartelle basato sui ruoli

L&#39;accesso alle cartelle private è assegnato solo al **livello 1**. Quando a un ruolo personalizzato viene concesso l&#39;accesso a una cartella di livello 1, tale accesso viene automaticamente esteso a tutte le sottocartelle di livello 2 e 3 al suo interno. Non è possibile concedere l&#39;accesso a livello di sottocartella in modo indipendente.

Nella tabella seguente vengono descritte le operazioni che ogni ruolo può eseguire con la gerarchia di cartelle.

| **Ruolo** | **Funzionamento** |
|-----------------|-----------------------------------------------------------------------------------------------------------------------------------------------------------|
| L’Amministratore | Creazione, ridenominazione ed eliminazione di cartelle private di livello 1, 2 e 3; configurazione dell&#39;accesso alle cartelle di livello 1 per i ruoli personalizzati |
| Amministratore personalizzato | Gestire le cartelle all&#39;interno delle filiali di livello 1 accessibili, in base ai privilegi assegnati |
| Autore | Sfoglia cartelle, filtra i contenuti per cartella, aggiungi contenuti alle cartelle, copia e sposta i contenuti tra le cartelle, seleziona i contenuti quando aggiungi moduli a un corso |
| Autore personalizzato | Come l’autore, ma limitato alle cartelle accessibili tramite i privilegi di livello 1 assegnati |

### Limiti della struttura delle cartelle

| **Limite** | **Valore** |
|---------------------------------------|-----------|
| Cartelle di livello 1 per account | Nessun limite |
| Sottocartelle di livello 2 per cartella di livello 1 | 25 |
| Sottocartelle di livello 3 per cartella di livello 2 | 25 |
| Profondità massima cartella | 3 livelli |


### Comportamento selezione cartella

Quando si seleziona una cartella, ad esempio, quando si filtra o si elimina una cartella, la selezione si sovrappone alla gerarchia nel modo seguente:

* Se si seleziona una cartella **di livello 1**, vengono selezionate automaticamente tutte le cartelle di livello 2 e 3 sottostanti.

* Se si seleziona una cartella **di livello 2**, vengono selezionate automaticamente tutte le cartelle di livello 3 sottostanti. Non sono selezionate altre cartelle di livello 2 nella stessa cartella di livello 1.

* Se si seleziona una cartella di **livello 3**, viene selezionata solo tale cartella. Non sono selezionate altre cartelle.

>[!NOTE]
>
>Quando si seleziona una sottocartella senza selezionarne la principale, nella cartella principale non viene visualizzato un indicatore di selezione parziale o misto. Questo è intenzionale. Perché una cartella principale può contenere contenuto, non solo sottocartelle. Selezionare una cartella principale significa &quot;includere tutto il contenuto in questa cartella e tutto ciò che si trova sotto di essa&quot;. Un indicatore parziale suggerisce che il contenuto della cartella principale è parzialmente incluso, il che sarebbe fuorviante. Se si desidera filtrare solo in base a una sottocartella specifica, selezionare direttamente tale sottocartella. Se desiderate che tutto il contenuto si trovi in una cartella principale e nelle relative sottocartelle, selezionate la cartella principale.

### Quando utilizzare una struttura di cartelle gerarchica

Le cartelle dei contenuti gerarchici sono particolarmente utili quando l&#39;organizzazione gestisce molti file di contenuto e necessita di un modo strutturato per spostarsi, riutilizzare e controllare l&#39;accesso ad essi.

Gli scenari più comuni includono:

* **Librerie di contenuti di grandi dimensioni**: quando sono disponibili migliaia di file di contenuto, una gerarchia a tre livelli consente agli autori di passare direttamente a ciò di cui hanno bisogno, anziché scorrere un elenco semplice.

* **Più team o progetti**: le cartelle di livello 1 possono separare team o aree di progetto; le cartelle di livello 2 possono essere organizzate in base al tipo di distribuzione; le cartelle di livello 3 possono contenere singole risorse.

* **Separazione dei contenuti basata sui ruoli**: quando diversi team di autori devono accedere solo ai contenuti pertinenti al proprio lavoro, l&#39;assegnazione dell&#39;accesso alla cartella di livello 1 mantiene privati i contenuti di ciascun team.

### Casi d&#39;uso reali di cartelle di contenuti gerarchici

**Caso di utilizzo 1- Corso di formazione sulla conformità con contenuti specifici per ogni giurisdizione**

Un&#39;organizzazione globale gestisce corsi di formazione sulla conformità obbligatori in più aree geografiche. Ogni area geografica dispone di moduli principali applicabili a tutti, oltre a moduli legali aggiuntivi specifici per ogni giurisdizione, come le normative sulla privacy dei dati, il diritto del lavoro locale, i requisiti di divulgazione finanziaria, che variano a seconda del paese o dell&#39;area geografica.

Senza cartelle gerarchiche, tutte le risorse di conformità si trovano in un elenco semplice, rendendo difficile per i team di contenuti regionali sapere a quali file appartengono ciascun programma o giurisdizione.

Con una struttura a tre livelli:

* Livello 1: formazione sulla conformità

* Livello 2: EMEA / APAC / Americhe (una sottocartella per area geografica)

* Livello 3: moduli o risorse specifici per area geografica (PDF delle normative sulla privacy, Policy deck locali, file di valutazione)

I team di autori regionali possono accedere solo alle filiali di livello 1 o 2. Possono trovare, aggiornare e riutilizzare solo le risorse pertinenti alla loro giurisdizione senza visualizzare o modificare accidentalmente il contenuto di un&#39;altra area geografica.

**Caso di utilizzo 2 - Programma di onboarding su larga scala con molti ruoli**

Un&#39;organizzazione impiega migliaia di dipendenti all&#39;anno in diversi ruoli distinti: singoli collaboratori, manager, appaltatori e specialisti tecnici. Ogni ruolo ha una propria traccia di onboarding con contenuti di base condivisi e moduli specifici per ogni ruolo.

Con una struttura a tre livelli:

* Livello 1: Onboarding

* Livello 2: ruolo (collaboratore individuale/manager/appaltatore/specialista tecnico)

* Livello 3: tipo di modulo (pacchetti SCORM / deck ILT / guide di attività / valutazioni)

Gli Autori che creano corsi per ogni ruolo possono passare direttamente al Livello 2 e trovare i file esatti per quella traccia. Quando un modulo viene riutilizzato in più ruoli, ad esempio in un video con valori aziendali, può essere copiato o collegato in più cartelle senza creare duplicati. Il contenuto rimane a origine singola ma viene visualizzato in tutte le sezioni pertinenti.

**Caso di utilizzo 3 - Libreria di competenze tecniche per volumi elevati con più team di contenuti**

Un&#39;azienda tecnologica gestisce una libreria interna di corsi di formazione con migliaia di file di contenuti su linee di prodotti, infrastrutture cloud, strumenti per sviluppatori, sicurezza e progettazione dei dati. Sono coinvolti più team di autori, ognuno responsabile di un&#39;area di prodotto. I moduli del corso possono eseguire da 40 a 60 file per corso.

Senza gerarchia, tutte le migliaia di file si trovano in una manciata di cartelle di primo livello e autori di team diversi spesso scelgono la versione errata del file o sovrascrivono accidentalmente le risorse condivise.

Con una struttura a tre livelli:

* Livello 1: Area del prodotto (Cloud / Strumenti di sviluppo / Sicurezza / Ingegneria dei dati)

* Livello 2: Nome del corso

* Livello 3: Tipo di risorsa (video / PDF / SCORM / quiz)

A ogni team di prodotto viene concesso l’accesso solo alla propria cartella di livello 1. Trovare un quiz specifico per un corso specifico significa navigare esattamente nella cartella di Livello 3 giusta, invece di cercare tra migliaia di file. Quando il team di sicurezza aggiorna un pacchetto SCORM, sa che vive in Sicurezza > [Nome corso] > SCORM e non può atterrare accidentalmente nella filiale di un altro team.

### Gestire le cartelle dei contenuti come amministratore

In qualità di amministratore di Adobe Learning Manager, puoi creare e gestire la gerarchia delle cartelle dei contenuti, controllare quali ruoli personalizzati hanno accesso a cartelle specifiche e gestire i nomi e le eliminazioni delle cartelle. Gli autori possono aggiungere contenuti alle cartelle e organizzarne i contenuti all’interno della gerarchia, ma solo gli amministratori possono creare, rinominare o eliminare le cartelle.

#### Creare una cartella di contenuti

>[!NOTE]
>
>Due cartelle dello stesso livello sotto lo stesso elemento padre non possono condividere un nome. Lo stesso nome è consentito in rami diversi o a livelli diversi.

1. Accedi a Adobe Learning Manager come amministratore.
2. Nella barra di navigazione a sinistra, seleziona **Configura** > **Impostazioni**.
3. Nella sezione **Avanzate**, seleziona **Cartella dei contenuti**.
4. Seleziona **Aggiungi** nell&#39;angolo superiore destro della pagina. Viene visualizzata la finestra di dialogo **Aggiungi nuova cartella**.
5. Immettere un nome e una descrizione facoltativa per la cartella.
6. Seleziona **Salva**. La cartella viene creata e visualizzata nell&#39;elenco delle cartelle.


#### Creare una sottocartella

1. Nella pagina **Cartella dei contenuti**, individua la cartella principale.
2. Selezionare l&#39;opzione **Crea sottocartella** accanto al nome della cartella.
3. Immettere un nome e una descrizione facoltativa per la sottocartella.
4. Seleziona **Salva**. La sottocartella viene visualizzata con rientro al di sotto della relativa cartella principale nell&#39;elenco delle cartelle.

>[!NOTE]
>
>Ogni cartella può contenere fino a 25 sottocartelle dirette. Il livello 3 corrisponde alla profondità massima. Non è possibile creare una sottocartella all&#39;interno di una cartella di livello 3.

#### Rinominare una cartella

1. Nella pagina **Cartella dei contenuti**, selezionare la cartella che si desidera rinominare. La cartella viene aperta in modalità di modifica.
2. Aggiornare il nome della cartella e, se necessario, la descrizione.
3. Seleziona **Salva**. La cartella viene salvata con il nuovo nome.

#### Eliminazione di una cartella

Prima di procedere con l’eliminazione, tieni presente le seguenti regole:

* È possibile eliminare una cartella vuota a qualsiasi livello.
* Non è possibile eliminare una cartella se contiene contenuto non collegato ad altre cartelle. Sposta prima il contenuto in un’altra cartella.
* Quando si elimina una cartella principale, vengono eliminate anche tutte le relative sottocartelle. Quando selezionate una cartella principale, vengono selezionati automaticamente tutti i relativi elementi secondari.

#### Eliminare la cartella principale

1. Nella pagina **Cartella dei contenuti** selezionare la casella di controllo accanto a ogni cartella che si desidera eliminare.
2. Seleziona **Azioni** > **Elimina cartella** nell&#39;angolo superiore destro della pagina.
3. Confermare l&#39;eliminazione quando richiesto. Vengono eliminate anche tutte le sottocartelle all’interno delle cartelle principali.

#### Eliminare una sottocartella

1. Nella pagina **Cartella dei contenuti** selezionare la casella di controllo accanto alla sottocartella che si desidera eliminare.
2. Seleziona **Azioni** > **Elimina cartella** nell&#39;angolo superiore destro della pagina.
3. Confermare l&#39;eliminazione quando richiesto. La sottocartella viene eliminata.

>[!CAUTION]
>
>L&#39;eliminazione di una cartella è permanente. Assicurati che tutto il contenuto all&#39;interno della cartella sia stato spostato in un&#39;altra posizione prima di confermare.


#### Configurare l&#39;accesso alle cartelle per i ruoli personalizzati

È possibile limitare i ruoli personalizzati a cartelle di livello 1 specifiche in modo che gli amministratori e gli autori personalizzati con tali ruoli visualizzino solo il contenuto ad essi relativo.

L&#39;accesso è impostato solo a livello di cartella **Livello 1**. Quando si concede a un ruolo personalizzato l&#39;accesso a una cartella di livello 1, tale ruolo ottiene automaticamente l&#39;accesso a tutte le sottocartelle di livello 2 e 3 al suo interno. Non è possibile assegnare l&#39;accesso a livello di sottocartella in modo indipendente.

1. Nella barra di navigazione a sinistra, seleziona **Utenti** > **Ruoli personalizzati**.
2. Aprire il ruolo personalizzato che si desidera configurare o crearne uno nuovo.
3. In **Privilegi account**, individua la sezione **Cartelle dei contenuti**.
4. Selezionare **Cartelle selezionate**.
5. Seleziona le cartelle di livello 1 a cui questo ruolo deve avere accesso.
6. Seleziona **OK**.

Gli utenti con questo ruolo visualizzano solo il contenuto delle cartelle di livello 1 selezionate e delle relative sottocartelle. Il contenuto in altre cartelle private e nella cartella pubblica rimane inaccessibile.

#### Procedure ottimali

Le seguenti procedure consentono di creare una struttura di cartelle che si adatta bene e rimane facile da esplorare.

1. **Pianificare la struttura prima di creare le cartelle.** Una volta organizzati i contenuti in una gerarchia, la ristrutturazione richiede lo spostamento di grandi volumi di contenuti. Decidi le categorie di livello 1, come linee di prodotti, reparti o programmi di formazione, prima di iniziare.

2. **Utilizzare tre livelli per raggruppamenti significativi.** Uno schema comune è: Livello 1 per un ampio dominio o programma, Livello 2 per il tipo di distribuzione o il team, Livello 3 per le singole risorse. Ad esempio:

   * Livello 1: Formazione alle vendite

   * Livello 2: moduli a ritmo personalizzato

   * Livello 3: Risorse PDF

3. **I nomi devono essere brevi, descrittivi e univoci all&#39;interno dell&#39;elemento padre.** Evita nomi generici come &quot;Modulo 1&quot; o &quot;Contenuto&quot;. Utilizza identificatori sensati per gli autori che esplorano la libreria.

4. **Assegna l&#39;accesso al ruolo personalizzato solo al livello 1.** Poiché l&#39;accesso si sovrappone automaticamente, l&#39;assegnazione al livello 1 è sufficiente e consente di gestire l&#39;accesso in modo semplice. Non è necessario aggiornare l&#39;accesso quando si aggiungono sottocartelle di livello 2 o 3.

5. **Spostare il contenuto prima di eliminare le cartelle.** Se una cartella contiene contenuto non collegato in altri punti, l&#39;eliminazione viene bloccata. Creare un&#39;abitudine di revisione del contenuto delle cartelle prima dell&#39;eliminazione.


<!--

**Key points:**

A folder is a repository of content, which is a subset of the entire content library available in an account with the following properties:

* Only you (administrator) can create, edit, or delete a folder.
* You can control access to folders as part of defining roles only for custom administrators.
* Content must at all times be associated with at least one folder. To start with, all content will be associated with the public folder, which can later be changed.
* Content can be associated with multiple folders at the time of creation, which will also be possible by a copy operation
* All folder names must be unique within the account, otherwise there will be an error in naming a folder.

Folders only control visibility of content and don't create copies of content. Therefore, editing content will reflect in all the associated folders.

**Public folder**

A public folder is always present in an account and initially, all content will be part of this folder. Later, authors can move content out of this folder into other folders. A public folder has the following properties:

* All content associated with this folder will be accessible to all types of authors, by default.
* Any content that is a part of a public folder, cannot be part of any other folder. The converse also holds true.

This folder cannot be part of configurable role definition. Consequently, not having a public folder in configurable role definition doesn't restrict access to a public folder.

**Private folder**

Any folder created by you is a private folder.

**Add a content folder**

To add a content folder, follow the steps:

1. Select **[!UICONTROL Settings]** > **[!UICONTROL Content Folder]**.
2. Select **[!UICONTROL Add]** to create a new folder.
3. Type the name and description of the folder to be created.
 
    ![alt text](assets/advanced-settings-picture1.png)

4. Select **[!UICONTROL Save]** to create the folder.

**Folder operations**

* **[!UICONTROL Add a folder]**: To add a folder, select the folder, and then select **[!UICONTROL Add]** on the upper-right corner of the screen.
* **[!UICONTROL Delete a folder]**: To delete a folder, select the folder to delete, select the **[!UICONTROL Actions]** menu, and then select **[!UICONTROL Delete Folder]**.
-->

## Aule

Crea e gestisci una libreria di aule fisiche o virtuali. Questi percorsi possono essere utilizzati dagli Autori e dagli Amministratori per configurare eventi di formazione ILT (Instructor-Led Training). La funzione assicura che i dettagli dell&#39;aula, come i limiti dei posti e le informazioni sulla posizione, siano preconfigurati e facilmente accessibili.

Per ulteriori informazioni, vedere [Aggiungere aule in Adobe Learning Manager](/help/migrated/administrators/feature-summary/classroom.md).

## Report

Questa sezione consente di configurare i dashboard Conformità e Gruppi riusciti.

![testo alternativo](assets/advanced-settings-picture2.png)

Per ulteriori informazioni, consultate i seguenti riferimenti:

* [Dashboard di conformità](/help/migrated/administrators/feature-summary/reports.md#compliance-dashboard)
* [Dashboard di Group Success](/help/migrated/administrators/feature-summary/group-success-dashboard.md)
