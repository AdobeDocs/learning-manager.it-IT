---
title: Equivalenti e alternative in Adobe Learning Manager
description: Offre un'esperienza di apprendimento senza problemi ed elimina i corsi di formazione ridondanti con Equivalenti e Alternative in ALM. Questa nuova funzionalità consente agli amministratori di configurare regole unidirezionali (alternative) o bidirezionali (equivalenti), in cui il completamento di un corso di formazione garantisce automaticamente il completamento alternativo per un altro
jcr-language: en-us
source-git-commit: e70a3b5a5d1080dc4b3a56aa726c717120c6bfa3
workflow-type: tm+mt
source-wordcount: '3457'
ht-degree: 0%

---


# Alternative ed equivalenti

## Introduzione

In molte organizzazioni, gli Allievi si trovano in situazioni di formazione in cui diversi corsi possono legittimamente soddisfare lo stesso requisito. Ad esempio, quando un nuovo corso deve sostituire uno precedente? Quando un corso più completo dovrebbe sostituirsi a uno più breve o quando dovrebbe essere offerto un corso sostitutivo speciale?

La funzione Corsi alternativi o Percorso di apprendimento offre ad ALM un modo formale per dire:

&quot;Se l’Allievo ha completato questo corso di formazione, considera che abbia soddisfatto il relativo requisito di formazione.&quot;

La funzione funziona per tutti i corsi e percorsi di apprendimento, garantisce il rispetto dei requisiti a valle quali prerequisiti e regole di conformità, e lo fa senza costringere gli Allievi a occuparsi dei contenuti ridondanti. Continua inoltre a riportare in modo accurato ciò che è stato completato direttamente rispetto a ciò che è stato soddisfatto tramite un&#39;alternativa.

Alla base, la funzione introduce il concetto di completamento alternativo: uno stato di completamento speciale creato automaticamente quando un Allievo completa un corso di formazione sorgente configurato che conta per un altro corso di formazione target.

## Relazioni alternative

Alcune relazioni di formazione sono bidirezionali, il che significa che ogni corso può soddisfare i requisiti dell’altro. Si tratta in effetti di uno scenario in cui due corsi di formazione sono trattati come intercambiabili. Al contrario, le relazioni unidirezionali consentono a un corso di formazione di soddisfare il requisito per un altro, ma non viceversa. ALM modella entrambi gli scenari utilizzando lo stesso meccanismo di completamento alternativo sottostante.

* **Relazione bidirezionale (equivalenti):** Il completamento di uno dei corsi di formazione soddisfa i requisiti dell&#39;altro.
* **Relazione unidirezionale:** il completamento del corso di formazione A soddisfa il corso di formazione B, ma il completamento del corso di formazione B non soddisfa il livello A. Ciò è comune quando una versione più recente o più completa deve essere conteggiata ai fini di un requisito precedente, ma non viceversa.

Ad esempio, quando un corso di superset più completo copre tutto in un corso di sottoinsieme più semplice. Il completamento del soprainsieme deve soddisfare il requisito per il sottoinsieme, ma non necessariamente il contrario.

Un corso più recente ed esteso che deve essere conteggiato ai fini di un requisito precedente.

Un corso progettato per un pubblico specifico (ad esempio, una variante regionale o adattata all’accessibilità) che soddisfa ancora lo stesso requisito del corso principale.

Una nuova versione avanzata di un corso che l’organizzazione desidera contare per un requisito precedente, ma la versione precedente non deve contare per il nuovo requisito.

In Alternative, la relazione è normalmente un modo. Se il corso A rappresenta un’alternativa al corso B, il completamento di A può soddisfare i requisiti di B, ma il completamento di B non soddisfa necessariamente A.

Quando un corso di formazione di origine configurato viene completato, ALM genera automaticamente un completamento alternativo per uno o più corsi di formazione di destinazione.

## Quali problemi risolve questo?

Senza alternative, amministratori e Allievi si trovano ad affrontare diversi problemi ricorrenti:

* Agli Allievi viene spesso richiesto di ripetere i corsi relativi ai contenuti già completati in una versione o in un formato diverso.
* L’aggiornamento dei programmi di conformità è più semplice perché gli amministratori possono sostituire o ristrutturare i corsi di formazione senza forzare gli Allievi che hanno completato versioni precedenti a riprendere contenuti alternativi o sostituiti.
* La logica dei prerequisiti è rigida. Se un percorso richiede come prerequisito un determinato corso, non c’è modo corretto di riconoscere che un altro corso di formazione è sufficiente.
* Le relazioni e gli audit sono più difficili. Non vi è alcun segnale formale che indichi che un requisito è stato soddisfatto tramite un completamento alternativo e nessun modo semplice per rintracciare la fonte del credito.

La funzione alternative risolve questi problemi come segue:

* Impedire agli Allievi di duplicare le attività quando le alternative sono valide.
* Consentire agli amministratori di modificare le strutture di formazione (ad esempio, scambiare un corso all’interno di un percorso) senza interrompere i completamenti per gli Allievi che hanno seguito la versione precedente.
* Consentire ai prerequisiti e ai controlli di conformità di rispettare sia i completamenti diretti sia quelli alternativi o equivalenti.
* Registrare chiaramente, nelle trascrizioni e nei rapporti, se un corso di formazione è stato completato direttamente o è stato soddisfatto tramite un rapporto alternativo, insieme al quale l’addestramento è servito come fonte.

## Funzionamento concettuale della funzione

La funzione si basa su tre idee principali: **relazioni**, **completamento alternativo** e **comportamento downstream**.

### Rapporti tra i corsi di formazione

Gli Amministratori definiscono le relazioni tra corsi e percorsi di apprendimento. Per ogni relazione, scelgono un&#39;origine e uno o più oggetti. Un singolo corso può avere fino a 30 obiettivi, a seconda del numero di corsi di formazione precedenti o correlati che deve soddisfare.

Per gli equivalenti, gli amministratori possono rendere la relazione bidirezionale se desiderano che entrambi i corsi di formazione si soddisfino a vicenda. Per le alternative, gli amministratori normalmente mantengono la direzione di un*senso per indicare che sono consentite solo alcune sostituzioni.

Queste relazioni vengono memorizzate a livello di formazione, non a livello di Allievo. Una volta configurati e abilitati, potrebbero applicare   a tutti i completamenti attuali e futuri del corso di formazione sorgente, in base alle impostazioni a livello di account*ad esempio se è abilitato il completamento retroattivo.

### Completamento alternativo

Quando un Allievo completa un corso di formazione di origine, ALM esamina tutte le relazioni alternative configurate e, per ogni corso di formazione di destinazione pertinente, crea un record di completamento alternativo. Questo record è diverso da un normale completamento:

* Segna il corso di formazione di destinazione per l’Allievo ma tiene traccia del completamento tramite alternative anziché direttamente.
* Registra quale addestramento sorgente è stato utilizzato per soddisfare la destinazione.
* È memorizzato in una struttura dedicata in modo che il reporting possa distinguere tra completamenti diretti e alternativi.

Gli Allievi vedranno il completamento alternativo anche se non sono iscritti. Il report Trascrizione Allievo (LT) include solo i record dei corsi di formazione a cui l’Allievo si è iscritto.

#### Esperienza dell’app per Allievi per completamenti alternativi e equivalenti

I completamenti alternativi vengono presentati in modo distinto nell’app per allievi, in modo che gli allievi possano capire chiaramente in che modo è stato soddisfatto un requisito di formazione, mantenendo la coerenza con le trascrizioni e i report.

#### Comportamento scheda LO

##### Stato di completamento alternativo

Quando un Allievo completa un corso di formazione tramite una relazione alternativa, nella scheda Oggetto di apprendimento (LO) viene visualizzato uno stato distinto **Completato tramite alternativo**. Questa distinzione visiva aiuta gli Allievi a distinguere tra completamenti diretti e completamenti concessi tramite relazioni configurate.

#### Indicatore del metodo di completamento

La scheda LO include un indicatore del metodo di completamento (ad esempio, un’etichetta o un’icona) per mostrare che il completamento è stato ottenuto tramite un’alternativa. Se un completamento alternativo viene successivamente revocato a causa di modifiche come il completamento retroattivo o l&#39;eliminazione del corso di formazione di origine, ALM annullerà tutte le aggiunte dell&#39;interfaccia utente effettuate per il completamento alternativo. L’Allievo non sarà comunque in grado di identificare l’LO in base al comportamento di accesso al catalogo corrente.

#### Dettagli sulla trasparenza e sull’audit

Gli Allievi possono aprire la scheda LO per visualizzare ulteriori dettagli, tra cui:

* Il corso o il percorso di apprendimento di origine che ha concesso il completamento alternativo

Ciò garantisce la trasparenza.

#### Filtraggio e visualizzazioni

##### Filtro metodo di completamento

L’app per Allievi fornisce un filtro che consente loro di distinguere tra:

* Completata
* Completato tramite alternativo (filtra gli oggetti di apprendimento che hanno solo completamenti alternativi. Se un LO ha un completamento alternativo e diretto, non verrà incluso.)
* Quando selezioni **Completato** e **Completato tramite alternativa**, potrai visualizzare tutti i completamenti

Ciò consente agli Allievi di comprendere rapidamente in che modo sono stati soddisfatti i loro requisiti di apprendimento.

##### Visualizzazioni Trascrizione e avanzamento

Il filtro del metodo di completamento è disponibile nelle visualizzazioni per allievi. Ad esempio:

* Sezioni di verifica avanzamento e completamento

Questi pareri indicano chiaramente quali corsi di formazione sono stati completati direttamente e quali sono stati soddisfatti mediante alternative.

<!--## Configure equivalent courses (complete each other)

Use this workflow to define courses that are **equal in value**, where completing either course should automatically complete the other.

1. Launch ALM and navigate to courses.
2. Select a course to configure.
3. Navigate to the **Alternates** section.
4. Search for and select one or more related courses.
5. For each selected course, enable **Completes each other**.
6. Save the configuration.

**Result**

- ALMm records a **bi-directional equivalence relationship**.
- Either course can act as a completion source for the other.

## Configure alternate courses (superset → subset)

Use this workflow when one course is a **superset** of another and should satisfy completion for the simpler or subset course.

1. Launch ALM and navigate to courses.
2. Select the **superset (primary)** course.
3. Go to the **Alternates** section.
4. Select one or more **alternate (subset)** courses.
5. Leave the relationship as **alternate** (do not enable completes each other).
6. Save the configuration.

**Result**

- Completion flows **one-way** from the source course to the alternate.
- Reverse completion is not applied.

## Apply completion logic after source course completion

Automatically evaluate and apply alternate or equivalent completion once a learner completes a configured source course. ALM:

1. Detects completion of a **source course**.
2. Evaluates configured relationships:
   - Equivalent relationships
   - Alternate relationships
3. For each related course:
   - Marks the course as completed if conditions are met
4. Creates a completion record with method **Alternate**.

**Key system rules**

- Alternate completion:
  - Satisfies prerequisites
  - Allows progress in learning paths and certifications
- Alternate completion does **not** award:
  - Skills
  - Badges
  - Gamification credits

## Record completion in Learning Transcript

Ensure alternate and equivalent completions are clearly distinguishable from direct completions for audit and reporting. ALM:

1. Updates the **Learner Transcript (LT)**.
2. Sets:
   - Completion status = Completed
   - Completion method = **Alternate**
3. Sets completion date equal to the **source course completion date**.

## Enable retroactive completion (optional)

Apply alternate or equivalent completion benefits to learners who completed source courses **before** the relationships were configured.

1. Open **Account-level settings** from Administrator home > Settings > General.
2. Enable **Retroactive completion**.
3. Save the configuration.

ALM:

1. Scans historical learner completions.
2. Applies alternate or equivalent completion where applicable.
3. Updates learner transcripts automatically.

## Enable retroactive incompletion (irreversible)

Revoke previously applied alternate or equivalent completions when relationships are removed or corrected.

1. Open **Account-level settings**.
2. Enable **Retroactive incompletion**.
3. Modify or remove alternate/equivalent relationships.

ALM:

1. Identifies impacted alternate completions.
2. Revokes previously applied alternate or equivalent completions.
3. Updates transcript entries to **Alternate (Revoked)**.-->

### Flusso end-to-end

**Per Allievi**

1. Passa a **Il mio apprendimento** o **Corsi completati** nell’app per Allievi.
2. Rivedi le schede LO per identificare i corsi di formazione contrassegnati come **Completati tramite Alternativo**.
3. Apri una scheda LO per visualizzare i dettagli (nella pagina Panoramica) sul corso di formazione di origine.
4. Utilizza il filtro per selezionare **Diretta**, **Alternativa** o **Tutto**.
5. Esamina l’elenco aggiornato in base al metodo di completamento selezionato.

**Per amministratori e autori**

* Configura relazioni alternative tra corsi o percorsi di apprendimento nell’interfaccia di amministrazione.

## Comportamento di completamento e incompletamento retroattivo

ALM supporta il completamento retroattivo e l&#39;incompletamento retroattivo per garantire che le relazioni alternative rimangano accurate nel tempo, anche quando le relazioni vengono modificate o rimosse dopo che gli Allievi hanno già completato il corso di formazione.

### Completamento retroattivo

#### Definizione

Quando il completamento retroattivo è abilitato, gli Allievi che hanno completato un corso di origine in passato ricevono automaticamente un completamento alternativo per il corso di destinazione se in seguito viene creata una relazione alternativa. Ciò garantisce che l’apprendimento storico venga rispettato senza richiedere agli Allievi di riprendere i corsi di formazione.

#### Come funziona

1. Un amministratore abilita il completamento retroattivo a livello di account.
2. L’Amministratore definisce una relazione alternativa tra un corso di formazione di origine e uno di destinazione.
3. Il sistema analizza i record di completamento cronologici per il corso di formazione di origine.
4. Agli Allievi idonei viene concesso un completamento alternativo per il corso di formazione di destinazione.
5. Questi record vengono visualizzati come **Completati tramite Alternativo** nelle trascrizioni e nei report degli Allievi.

>[!NOTE]
>
>Quando il completamento retroattivo è abilitato, si applica solo alle relazioni create successivamente. Non si applica alle relazioni che esistevano già prima dell’attivazione dell’impostazione retroattiva.

### Incompletamento retroattivo

#### Definizione

Quando l’opzione Incompletamento retroattivo è abilitata, i completamenti alternativi vengono revocati se la relazione alternativa sottostante viene rimossa o se il corso di formazione di origine viene eliminato.
Ciò garantisce che il sistema rifletta le relazioni di formazione correnti e valide.

#### Come funziona

1. Un amministratore abilita il completamento retroattivo a livello di account.
2. L’Amministratore rimuove una relazione alternativa o elimina il corso di formazione di origine.
3. Il sistema identifica gli Allievi che hanno ricevuto un completamento alternativo tramite la relazione interessata.
4. I record di completamento alternativi corrispondenti vengono revocati.
5. I record revocati sono contrassegnati come **Alternativi (revocati)** nelle trascrizioni e nei report per la visibilità del controllo.

#### Impatto sui prerequisiti

I completamenti alternativi, inclusi quelli concessi retroattivamente, vengono trattati come completamenti validi durante la valutazione dei prerequisiti. Se un Allievo ha completato **tramite Alternativa**, può continuare con i corsi che richiedono il corso di destinazione.

Se un completamento alternativo viene successivamente revocato tramite incompletamento retroattivo, l’Allievo può perdere l’idoneità ai corsi che dipendono da tale prerequisito. Se l’Allievo non ha avviato l’LO dipendente/successivo, l’idoneità gestita dall’LO di origine verrà annullata. Se l’Allievo ha già iniziato o completato l’LO dipendente/successivo, non ci sarà alcun impatto.

#### Impatto su percorsi di apprendimento e certificazioni

I completamenti alternativi contribuiscono al completamento dei percorsi di apprendimento e delle certificazioni perpetue. Gli Allievi possono avanzare o completare questi programmi quando i corsi di formazione richiesti vengono soddisfatti tramite relazioni alternative.

Se viene revocato un completamento alternativo, i percorsi di apprendimento o le certificazioni interessati possono perdere l’avanzamento fino a quando il requisito non viene soddisfatto mediante un completamento valido.

### Flusso di lavoro completo

#### Abilitazione del completamento o incompletamento retroattivo

1. Gli amministratori passano alle impostazioni account e abilitano il completamento retroattivo e/o l’incompletamento retroattivo.
2. Gli Amministratori creano, modificano o rimuovono relazioni alternative tra i corsi di formazione.

#### Azioni di sistema

* **Per il completamento retroattivo**:
Il sistema concede completamenti alternativi in base ai completamenti dell&#39;origine cronologica.
* **Per incompletamento retroattivo**:
Il sistema revoca i completamenti alternativi quando vengono rimosse le relazioni o vengono eliminati i corsi di formazione di origine.

#### Esperienza di apprendimento

Gli Allievi visualizzano gli stati di completamento aggiornati sulle schede LO e nelle trascrizioni, ad esempio:

* **Completato tramite alternativo**

Quando viene revocato un completamento alternativo, nell’interfaccia utente dell’Allievo non viene visualizzata alcuna etichetta. Nei report e nelle trascrizioni, i metodi di completamento sono visualizzati come segue:

* Alternativa
* Alternativa (revocata)
* Diretto

I controlli dei prerequisiti, l’avanzamento del percorso di apprendimento e lo stato della certificazione vengono aggiornati in modo dinamico in base allo stato di completamento corrente.

Gli LO ordinati si sbloccano in modo dinamico in base al completamento alternativo.

Abilità, distintivi, punti di gamification o feedback non verranno assegnati agli Allievi al completamento alternativo degli obiettivi.

#### Relazioni e audit

Tutte le modifiche retroattive sono riportate nel report Trascrizione Allievo (LT). Dopo l’eliminazione dell’origine, la Trascrizione Allievo può ancora mostrare un ID di formazione di origine accanto a **Alternativo revocato**. I report distinguono chiaramente tra completamenti diretti, completamenti alternativi e completamenti alternativi revocati per supportare conformità, indagini di supporto e audit.

Il report di iscrizione lascia vuoto il campo Origine completamento in caso di completamento diretto, mentre la Trascrizione Allievo mostra l’e-mail e digita per lo stesso.

Quando una destinazione viene rimossa dall’origine (o l’origine stessa viene eliminata), il report di iscrizione potrebbe non visualizzare lo stesso stato **Alternativo o Alternativo (Revocato)** come mostrato nella Trascrizione Allievo.

Anche quando   **Le alternative** sono disabilitate, le voci della cronologia nelle righe **Controllo contenuto** o **Iscrizione** potrebbero ancora visualizzare le attività relative alle alternative.

La data di completamento può precedere la data di iscrizione quando un LO viene completato tramite un percorso alternativo **prima** dell’iscrizione effettiva dell’Allievo. Poiché i completamenti alternativi possono verificarsi indipendentemente dallo stato dell’Allievo (**Iscritto**, **Non iscritto** o **In corso**), gli Allievi possono completare prima l’LO e solo in seguito iscriversi al corso di destinazione.

## Impatto del ritiro e dell’eliminazione dei corsi di formazione sorgente in alternanze

Lo stato del ciclo di vita di un corso di formazione di origine (ritirato o eliminato) influisce direttamente sul modo in cui i completamenti alternativi vengono mantenuti per gli Allievi. ALM gestisce questi scenari in modo diverso per mantenere l&#39;accuratezza storica, assicurando al contempo la validità delle relazioni correnti.

### Ritiro del corso di formazione di origine

#### Definizione

Se un corso viene ritirato, non è più disponibile per nuove iscrizioni, ma viene mantenuto nel sistema a scopo di riferimento storico, report e audit.

#### Impatto

* I completamenti alternativi esistenti concessi tramite il corso di origine ritirato restano validi.
* Gli Allievi che hanno completato in precedenza il corso di origine continuano a sostenere il completamento alternativo per il corso di destinazione.
* Il corso ritirato non genera nuovi completamenti alternativi, poiché non può essere completato da nuovi allievi.
* Le trascrizioni e i report degli Allievi continuano a visualizzare **Completato tramite alternativa** per gli Allievi interessati.

### Elimina corso di formazione di origine

#### Definizione

L’eliminazione di un corso lo rimuove completamente dal sistema, compresi i record di completamento e le relazioni configurate.

#### Impatto

* Se un corso di formazione di origine viene eliminato, lo stato potrebbe cambiare in **Alternativo (revocato)**. Il ritiro di un LO non attiva questo stato.
* Se l’opzione Incompletamento retroattivo è abilitata, tutti i completamenti alternativi concessi tramite il corso di origine eliminato vengono revocati.
* Le trascrizioni e i report degli Allievi vengono aggiornati per mostrare **Alternativo (revocato)** per il controllo e la visibilità della conformità.
* Il completamento dei percorsi di apprendimento e la disponibilità dei certificati non sono interessati.
* Non è possibile concedere ulteriori completamenti alternativi dal corso eliminato.

#### Flusso di lavoro

1. Un Amministratore ritira o elimina il corso di origine utilizzando l’interfaccia di amministrazione.
2. Il sistema valuta tutti i completamenti alternativi derivati dal corso di origine.
3. Lo stato di completamento viene aggiornato in base allo stato del corso:
   * **Ritirato:** i completamenti alternativi esistenti rimangono invariati.
   * **Eliminati:** completamenti alternativi revocati se l&#39;incompletamento retroattivo è abilitato.
4. Le trascrizioni e i report degli Allievi riflettono lo stato aggiornato per supportare i requisiti di conformità e audit.

## Nessun concatenamento delle relazioni

ALM non supporta il concatenamento di relazioni alternative. I completamenti alternativi vengono concessi solo per relazioni configurate direttamente e non si sovrappongono a più livelli di corsi.

### Concetto: nessun concatenamento delle relazioni

#### Definizione

Per concatenamento si intende la possibilità di consentire la propagazione di relazioni alternative tra più corsi. Ad esempio, se il Corso A è un’alternativa al Corso B e il Corso B è un’alternativa al Corso C, il concatenamento implicherebbe che il completamento del Corso A conceda il completamento del Corso C.

#### Policy

Concatenamento non supportato. Le relazioni alternative ed equivalenti vengono valutate solo a un singolo livello. Il completamento di un corso di origine consente il completamento alternativo solo al corso o ai corsi di destinazione immediati, non a qualsiasi destinazione a valle.

### Flusso di lavoro

#### Impostazione delle relazioni

Un amministratore definisce relazioni alternative tra i corsi, ad esempio:

* Corso A → Corso B
* Corso B → Corso C

#### Evento di completamento

Un Allievo completa direttamente il corso A.

#### Azione di sistema

* Se viene definita la relazione A → B, il sistema concede un completamento alternativo per il corso B.
* Il sistema non consente il completamento alternativo per il corso C, anche se esiste una relazione B → C.

#### Requisito di completamento diretto

Per ricevere un completamento alternativo per il corso C, l’Allievo deve:

* Completamento diretto del corso B oppure
* Completa un corso configurato in modo esplicito come alternativa diretta o equivalente per il corso C.

## Implicazioni

### Nessun vantaggio indiretto

Gli Allievi non possono ricevere i crediti di completamento per i corsi nelle fasi successive di una catena di relazioni a meno che ciascun corso (o il suo alternativo diretto) non venga completato. Ciò garantisce che i requisiti di apprendimento siano soddisfatti in modo esplicito e prevedibile.

### Audit e reporting semplificati

I report e le trascrizioni degli allievi visualizzano i completamenti alternativi solo per le relazioni dirette. In questo modo si evitano audit trail complessi e multi-hop e si garantisce chiarezza durante la revisione delle modalità di concessione di un completamento.

## Condivisione del catalogo con account condivisi tra pari: relazioni non condivise

La condivisione del catalogo consente la condivisione degli LO tra account condivisi tra pari, ma le relazioni alternative e equivalenti sono gestite in modo indipendente all’interno di ciascun account e non vengono condivise.

### Concetto: condivisione di cataloghi e relazioni

#### Condivisione catalogo

Gli account possono condividere cataloghi con account condivisi tra pari per fornire accesso a corsi, percorsi di apprendimento e altri oggetti di apprendimento tra account.

#### Relazione non condivisa

Le relazioni alternative, equivalenti e di completamento alternativo configurate nell’account di origine non vengono condivise o replicate quando un catalogo viene condiviso. Ogni account gestisce e valuta le proprie relazioni in modo indipendente.

### Flusso di lavoro

#### Condivisione catalogo

Un amministratore dell&#39;account **A** condivide un catalogo contenente oggetti di apprendimento con **Account B**.

#### Configurazione delle relazioni

L’account A può avere relazioni alternative definite tra gli LO nel catalogo condiviso.

#### Accesso all’account condiviso tra pari

L’account B riceve l’accesso agli oggetti di apprendimento condivisi ma non eredita alcuna relazione alternativa configurata nell’account A.

#### Gestione indipendente

Se l’account B richiede un comportamento alternativo simile, un amministratore dell’account B deve configurare manualmente le relazioni all’interno di tale account.

#### Implicazioni

##### Nessuna propagazione automatica delle relazioni

Le relazioni alternative non sono automaticamente disponibili negli account condivisi tra pari tramite condivisione del catalogo.

##### È richiesta la configurazione manuale

Ogni account condiviso tra pari è responsabile della definizione e della gestione delle proprie relazioni per gli oggetti di apprendimento condivisi.

##### Considerazioni sulla coerenza

Il comportamento di completamento, il soddisfacimento dei prerequisiti e la creazione di rapporti possono differire tra account a meno che le relazioni non siano intenzionalmente allineate tramite la configurazione manuale.

## Comportamento a valle

Una volta che esiste un completamento alternativo per un corso di formazione di destinazione, ALM lo utilizza nei controlli a valle:

* Se il corso di formazione di destinazione è un **prerequisito** per altri corsi di formazione, l’Allievo è idoneo per tali corsi di formazione come se avesse completato la destinazione.
* Se la destinazione è un **corso obbligatorio in un percorso di apprendimento**, la logica di completamento del percorso può considerare che l’Allievo abbia completato quella parte e procedere a contrassegnare il percorso come completato quando vengono soddisfatte altre condizioni.
* La conformità e altre dashboard come ad esempio Dashboard di successo del gruppo, che si basano sul rispetto di un requisito di formazione, possono includere Allievi che dispongono solo di completamenti alternativi.

Il sistema distingue tra completamento effettivo e completamento alternativo in modo che:

* Se l’Allievo in seguito segue direttamente il corso di formazione di destinazione e lo completa, questo completamento diretto può ignorare la necessità di un completamento alternativo.
* Se la relazione tra origine e destinazione viene rimossa o modificata, ALM può rimuovere i completamenti alternativi senza toccare quelli originali, a condizione che per l&#39;account siano abilitati i completamenti retroattivi.

I completamenti alternativi sono progettati per non interferire con l’effettiva attività dell’Allievo nel corso di formazione di destinazione. Agiscono come una sovrapposizione che può essere rivista se le relazioni cambiano.

## E-mail e notifiche

Non appena un Allievo completa un corso, riceve una notifica in-app e un’e-mail che indica lo stato del corso e il modo in cui è stato completato, indipendentemente dal fatto che sia stato completato tramite un corso alternativo.

>[!NOTE]
>
>Il completamento alternativo può comunque attivare notifiche per gli oggetti di apprendimento di destinazione nei cataloghi in cui l’Allievo non può vedere. Le notifiche alternative di completamento/incompletamento potrebbero non apparire nello stesso modo sull’app immersiva per dispositivi mobili come altrove.

## Aggiungi un corso alternativo

In qualità di Amministratore, puoi aggiungere corsi e percorsi alternativi in modo che gli Allievi abbiano più scelte per completare i propri corsi e percorsi.

1. Passa alla sezione **Apprendimento** > **Corsi**. Verrà visualizzato un elenco dei corsi disponibili.
   ![](assets/ALM-courses-main.png)
   *Elenco dei corsi*
2. Seleziona il corso a cui desideri aggiungere un corso alternativo.
   ![](assets/ALM-course-single.png)
   *Aggiungere un corso alternativo a un corso*
3. Passa alla sezione **Gestisci** > **Corsi/percorsi alternativi**.
   ![](assets/ALM-alt-train-paths.png)
   *Corsi di formazione/percorsi alternativi*
4. Seleziona **Aggiungi corsi/percorsi**. Verrà visualizzato un elenco dei corsi disponibili.
   ![](assets/ALM-alt-courses-list.png)
   *Elenco dei corsi disponibili*
5. Seleziona i corsi che desideri contrassegnare come **alternativi** selezionando la casella di controllo di ciascun corso in alto a sinistra nel riquadro.
   ![](assets/ALM-alt-courses-added.png)
   *Aggiungi corso alternativo*
6. Seleziona **Aggiungi**.

   >[!NOTE]
   >
   >A questo punto, se lo desideri, puoi rimuovere i corsi alternativi. Per rimuovere i corsi alternativi, seleziona **Rimuovi alternativi** accanto a ogni corso sulla destra.

7. Seleziona **Salva**. I corsi alternativi vengono ora salvati.

L&#39;avanzamento non è influenzato dal completamento alternativo. Quando un corso o un percorso di apprendimento viene completato tramite un completamento alternativo, l’Allievo può comunque accedervi e seguirlo direttamente per rafforzare l’apprendimento e ottenere vantaggi a valle (ad esempio, i punti di gamification). In questi casi, lo stato di avanzamento riflette i progressi effettivi dell’Allievo rispetto al consumo diretto, indipendentemente dallo stato di completamento alternativo. Riceverai anche una notifica in-app e una notifica e-mail sul completamento tramite un&#39;alternativa.

Di seguito sono elencati diversi vantaggi offerti da questo completamento:

* Questo viene conteggiato come completamento come parte del percorso di apprendimento in cui è presente.
* In questo modo si aprirà anche qualsiasi altro corso/percorso collegato.

## Impostazioni per gli utenti esperti

Le impostazioni seguenti consentono agli utenti esperti di utilizzare completamenti e incompletamenti retroattivi.

1. Passa alla sezione **Configura** > **Impostazioni** > **Nozioni di base** > **Generali** > **Sezione corsi/percorsi alternativi**.
2. Seleziona **Attiva completamenti retroattivi** e **Attiva incompletamenti retroattivi** o solo uno dei due in base alle tue esigenze.
   ![](assets/ALM-alt-train-paths-settings-powerusers.png)
   *Attiva completamento o incompletamento retroattivo*

## Report Trascrizione Allievo

Il modo in cui un Allievo completa un corso o un percorso viene acquisito nel report Trascrizione Allievo. Vengono acquisiti i seguenti scenari:

1. Quando un Allievo completa un corso direttamente senza optare per un corso alternativo, questo si riflette nel report Trascrizione Allievo
2. Quando un Allievo completa un corso alternativo, questo si riflette nel report Trascrizione Allievo
3. Quando tutti i completamenti alternativi vengono revocati a causa di incompletamento retroattivo e rimozione della relazione, questo si riflette nel report Trascrizione Allievo.
