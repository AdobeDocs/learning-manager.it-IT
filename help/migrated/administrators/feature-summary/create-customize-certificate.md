---
title: Creare e personalizzare un certificato
description: I certificati personalizzati in Adobe Learning Manager (ALM) consentono ad amministratori e autori di progettare, gestire ed emettere certificati personalizzati per gli Allievi.
jcr-language: en-us
source-git-commit: c012fdc19d3695add97661e290db19a90771748f
workflow-type: tm+mt
source-wordcount: '2630'
ht-degree: 0%

---


# Certificati personalizzati in Adobe Learning Manager

## Introduzione

I certificati personalizzati in Adobe Learning Manager cambiano il modo in cui gli amministratori progettano, gestiscono e rilasciano i certificati di completamento.

Gli amministratori possono:

- Progettare i certificati in un editor visivo in stile area di lavoro anziché scrivere codice.
- Allega certificati a corsi, percorsi di apprendimento e certificazioni con impostazioni predefinite flessibili.
- Utilizza sfondi generativi basati sull&#39;Adobe Firefly tenendo conto delle esigenze di marchio e conformità.
- Effettua la migrazione dai modelli di HTML esistenti e mantieni la compatibilità con i record storici degli Allievi.

Il processo di certificazione segue il modello di distintivo e di risultato esistente in Learning Manager, in modo che il comportamento degli Allievi rimanga familiare, mentre gli Amministratori e i team di supporto dedicano meno tempo alle operazioni relative ai certificati.

**Nota:** le funzionalità dei certificati che utilizzano l&#39;intelligenza artificiale generativa sono soggette a quota. Il limite è di 10.000 richieste per utente.

## Funzionalità chiave della certificazione personalizzata

### Progettazione certificati (editor in stile area di lavoro)

Un progettista di certificati con trascinamento fornisce un’area di lavoro ciò che vedi è ciò che ottieni (WYSIWYG) in cui gli amministratori possono creare e gestire progetti senza competenze HTML o CSS.

**Modifica visiva**

- Trascina, posiziona, ridimensiona, capovolgi e ruota testo e immagini.
- Allinea gli elementi (in alto, in basso, a sinistra, a destra), porta in secondo piano o porta in primo piano.
- Duplica o clona gli elementi per un lavoro di layout più veloce.

**Elementi supportati**

- Campi di testo con controlli per font, colore, dimensioni e allineamento.
- Segnaposto dinamici (ad esempio, nome dell’Allievo, nome del corso o della certificazione, data, campi account e campi utente attivi in cui sono consentiti solo attributi a valore singolo).
- Le immagini, compresi logo e distintivi, con ridimensionamento manuale preferito rispetto all&#39;adattamento automatico per un layout prevedibile.

**Sfondo e layout**

- Orientamento verticale o orizzontale (fisso dopo la creazione).
- Gli sfondi come colori a tinta unita o immagini con trasparenza regolabile.
- Galleria di immagini con immagini predefinite e sfondi condivisi.
- Controlli zoom (50%-150%) e allineamento a griglia o a scatto.

**Localizzazione**

- Supporto per più impostazioni locali, in cui ciascuna di esse dispone di un proprio file di layout.
- Quando aggiungete una lingua, il suo layout viene copiato dalla lingua predefinita e può quindi essere personalizzato.
- Menu a discesa Lingua con anteprima per lingua in fase di progettazione.

**Ciclo di vita Bozza e pubblicazione**

- Salva progetti come bozze. Le bozze non possono essere utilizzate per il rilascio.
- Dopo la pubblicazione, la struttura del progetto è bloccata; alcune modifiche potrebbero richiedere la duplicazione del progetto.
- Anteprima di Real-time PDF per controllare il layout prima del rilascio.

### Catalogo modelli ed elenchi

La pagina con l&#39;elenco **Progettazione certificati** consente agli amministratori di gestire i modelli di certificato su larga scala:

- Catalogo basato su piastrelle con schede **Pubblicato** e **Bozza**.
- Cerca per titolo del certificato; filtra per **Orientamento**.
- Azioni su ciascun progetto:
   - Duplicato (per varianti).
   - Imposta come predefinito al livello **Account**, **Corso**, **Percorso di apprendimento** o **Certificazione**.
   - Rimuovere o disattivare i modelli non più in uso.
- Supporto per modelli di terze parti che possono essere incorporati e riutilizzati.

### Configurazione flessibile ed ereditarietà

Gli amministratori possono configurare i certificati a diversi livelli:

**Impostazioni predefinite a livello di account**

- Imposta una struttura di certificati predefinita per tutti i nuovi oggetti di apprendimento (LO).
- L’impostazione predefinita funge da punto di partenza; gli oggetti di apprendimento esistenti non vengono modificati automaticamente quando cambia l’impostazione predefinita dell’account.

**Override a livello di istanza**

- Configurazione a livello di istanza per corsi, certificazioni e percorsi di apprendimento, tra cui:
   - Branding per coorte (ad esempio, per aree geografiche o account partner diversi).
   - Progettazioni di certificati diverse per i cicli di certificazione ricorrenti.

**Risoluzione e fallback del certificato**

Quando un Allievo completa il corso di formazione, Learning Manager sceglie un progetto nel seguente ordine:

- Configurazione istanza LO
- Configurazione LO
- Modello predefinito LO
- Modello predefinito account

### Sfondi generativi basati sull&#39;Adobe Firefly

Per aiutare i clienti a produrre certificati on-brand coerenti su larga scala, il designer si integra con l’Adobe Firefly:

- Gli amministratori generano sfondi dai prompt delle parole chiave e da una combinazione di colori (ad esempio, &quot;minimalista, sanitario, tavolozza verde acqua&quot;).
- Una libreria di parole chiave selezionata supporta i settori più comuni (trasporto, assistenza sanitaria e altro) per gli utenti che non sono progettisti.
- Le immagini generate vengono aggiunte alla galleria di sfondo e possono essere riutilizzate in tutti i modelli.
- I crediti e i livelli per l’utilizzo del Firefly in Learning Manager sono definiti dalla politica del prodotto.

### Migrazione dei certificati legacy HTML

I modelli di certificato HTML o ZIP esistenti vengono mantenuti ma non possono essere modificati nella nuova finestra di progettazione:

- I modelli precedenti vengono migrati con flag come `isLegacy` / `is_active`.
- Vengono visualizzate come voci non modificabili (nessuna anteprima WYSIWYG) e rimangono valide per l&#39;utilizzo storico.
- Quando i distintivi erano associati ai modelli precedenti, la migrazione mantiene i certificati scaricabili; laddove la configurazione non può essere mantenuta, vengono applicate le impostazioni predefinite globali.

### Generazione di PDF e pre-cottura

Per migliorare le prestazioni in fase di runtime e l’esperienza dell’Allievo:

- I certificati vengono pre-preparati al momento del completamento (quando l’LO viene completato), quindi memorizzati nella cache in modo che gli Allievi possano scaricarli rapidamente.
- I flussi di Allievi esistenti per scaricare i certificati tramite **Distintivi** e **Risultati** rimangono invariati.

## La sfida

Oggi, la gestione dei certificati in Learning Manager dipende da un modello complesso in termini di codice e supporto:

**Elevata dipendenza da CSM e team di supporto**: gli amministratori forniscono file HTML o ZIP caricati da CSM o team di progettazione tramite strumenti interni. Ogni cambiamento (branding, logo, testo normativo, firme) richiede un ticket interno e un ciclo di distribuzione.

**Agilità limitata per i team aziendali**: i team di marketing, conformità o HR spesso necessitano di aggiornamenti frequenti e localizzati dei certificati (lingue, campagne, regole specifiche del paese). Il flusso di lavoro corrente rallenta tali aggiornamenti e ritarda i programmi di conformità.

**Configurazione frammentata ed ereditarietà poco chiara**: i modelli precedenti di HTML possono essere impostati a livello di account, di oggetto di apprendimento predefinito e di oggetto di apprendimento con regole di fallback complesse. Senza una chiara configurazione personalizzata a più livelli, può essere difficile vedere quale modello viene applicato.

**I vincoli di collegamento dei distintivi** I certificati sono strettamente associati a **distintivi**:

- Un certificato deve essere associato a un badge; non è previsto il rilascio di soli certificati.
Tale associazione può complicare le modifiche di progettazione quando gli amministratori desiderano certificati senza elementi di gamification.

**Creazione non visiva e incoerenza del marchio**: i certificati basati su HTML sono flessibili ma richiedono competenze front-end di cui molti amministratori non dispongono. Alcuni clienti si affidano a certificati predefiniti generici, il che indebolisce la coerenza del marchio.

**Distanza competitiva**: alcuni sistemi di gestione dell’apprendimento includono progettisti di certificati personalizzati nativi (ad esempio, Docebo). La progettazione di certificati self-service in quest&#39;area rappresenta una lacuna nota per Adobe Learning Manager.

Il risultato è una modifica lenta, un costo di supporto elevato e un’esperienza di creazione che non corrisponde alle aspettative dell’amministratore per i certificati e le credenziali.

## In che modo le certificazioni personalizzate risolvono questi problemi

### Flussi di lavoro autonomi e intuitivi per gli amministratori

Di seguito sono riportati i flussi di lavoro:

- Progettazione ed elenco di certificati sostituiscono gli script di caricamento dei HTML e il provisioning interno con un&#39;esperienza guidata dall&#39;amministratore:
- Gli Amministratori creano, pubblicano e ritirano le progettazioni dei certificati all’interno di Learning Manager senza dover ricorrere a codice o CSM.
- Gli aggiornamenti della progettazione (ad esempio, il branding stagionale o specifico del partner) richiedono minuti nell&#39;interfaccia utente anziché biglietti e cicli di progettazione.
- Le impostazioni predefinite a livello di account e di oggetto di apprendimento riducono la configurazione ripetitiva per ogni oggetto.

### Riduzione dei costi generali di supporto e dei rischi operativi

Consolidando la gestione dei certificati in **Raggiungimenti** con un&#39;esperienza utente chiara:

- I carichi di lavoro per le richieste di &quot;caricamento o modifica del certificato&quot; vengono eliminati per i team tecnici e CSM.
- Il prodotto applica vincoli di sicurezza (ad esempio, orientamento bloccato, modelli legacy non modificabili) per ridurre i rischi per le distribuzioni esistenti.
- I modelli legacy migrati mantengono i certificati cronologici disponibili senza ulteriori interventi di supporto.

### Governance, coerenza e controllo del marchio

Impostazioni predefinite, Firefly e raccolte consentono ai clienti di:

- I modelli per il marchio possono essere spediti una sola volta a livello di account e possono essere sostituiti solo se necessario.
- Utilizza sfondi di Firefly all&#39;interno dei tutorial aziendali invece di risorse esterne ad hoc.
- Regola i certificati tramite gli stati di pubblicazione e ritiro, con bozze visualizzabili in anteprima prima del rollout.

### Allineamento ai flussi di badge e certificati esistenti

La progettazione mantiene il percorso dell’Allievo corrente: i certificati sono ancora scaricati dai **Distintivi** e dai **Risultati**, il che limita la riqualificazione.

### Prestazioni e scalabilità

Prestazioni della destinazione di rendering basata su JSON e certificati predefiniti:

- I certificati vengono generati al momento del completamento e vengono archiviati, pertanto il download è in realtà un recupero statico.
- I progetti basati su JSON rimangono leggeri per l’editor e il rendering in fase di runtime su larga scala.

## Casi d&#39;uso reali

### Formazione per clienti e partner: credenziali con marchio su larga scala

**Scenario:** una società di software gestisce accademie di clienti e partner con centinaia di programmi in diverse aree geografiche e marchi.

- Utilizza modelli predefiniti a livello di account con sfondi generati dal Firefly allineati a ciascuna linea di prodotto.
- È possibile aggiungere layout specifici della lingua per titoli di certificazione localizzati, esclusioni di responsabilità e firme.
- Per i partner premium, duplica i modelli di base e aggiungi il co-branding del partner (logo e testo legale) a livello di istanza.
- I PDF precotti consentono ai partner di scaricare i certificati subito dopo aver completato le certificazioni dei partner, con un carico minimo su Learning Manager.

Questo modello si adatta agli ecosistemi di franchising o multi-brand in cui i certificati rafforzano il valore del marchio e del partner (ad esempio, le reti di partner di grandi dimensioni come RealPage).

### Corsi di formazione sulla conformità e sulle normative: ambienti multi-locale ad alta evoluzione

**Scenario:** Un&#39;azienda regolamentata deve aggiornare spesso la formulazione del certificato di conformità in base al paese e alla lingua.

- **La modifica guidata dall&#39;amministratore** consente ai team di conformità e legale di modificare la formulazione e i campi dinamici senza dover richiedere l&#39;intervento dell&#39;ingegnere.
- I layout specifici per le impostazioni internazionali supportano **esclusioni di responsabilità specifiche per paese o area geografica** e firme su una struttura di base condivisa.
- **La logica di fallback** garantisce che, se manca un modello di istanza LO specifico, il sistema utilizzi comunque valori predefiniti sicuri ed eviti errori di emissione.

Questo vale per la sanità, la finanza, la pubblica amministrazione e altri settori in cui il testo del certificato cambia spesso ed è sottoposto a revisione.

### Certificazioni ricorrenti con contenuto di cataloghi condivisi o condivisi tra pari

**Scenario:** un account Learning Manager principale condivide contenuti su più **account condivisi tra pari** (ad esempio, molti account cliente), ciascuno con certificazioni ricorrenti e propri certificati.

- Gli account condivisi tra pari possono **aggiungere corsi acquisiti alle certificazioni ricorrenti** e configurare **modelli di certificato locali** a livello di istanza.
- Gli aggiornamenti del corso dal flusso dell&#39;account principale alle ricorrenze come previsto, mentre le progettazioni dei certificati possono rimanere **per cliente**.

### Programmi interni di abilitazione e leadership

**Scenario:** I programmi interni (ad esempio, gli acceleratori di gestione o le accademie di prodotti) richiedono **certificati visivamente distinti** che gli amministratori possono aggiornare senza il lavoro di HTML.

- I proprietari dei programmi possono progettare **modelli con marchio a livello di programma** (ad esempio, elementi visivi interni in stile accademia o MAP) senza competenze di HTML.
- Le esclusioni a livello di istanza consentono a diverse coorti o aree geografiche di utilizzare varianti (ad esempio, il branding specifico della coorte o regionale).
- Gli sfondi di Firefly supportano elementi visivi **specifici per eventi o coorti** con una minore dipendenza dai team di progettazione.

### Transizione dai certificati HTML legacy

**Scenario:** i clienti esistenti utilizzano certificati personalizzati HTML5 gestiti tramite CSM.

- I modelli legacy HTML o ZIP vengono migrati e contrassegnati come legacy, preservando l’utilizzo e i download precedenti.
- Gli amministratori possono passare a modelli basati su progettazioni nel tempo, a partire da programmi ad alta priorità.
- Se la migrazione non può mantenere una mappatura (ad esempio, i distintivi disattivati a metà percorso), il sistema torna al modello predefinito globale in modo che gli allievi non vengano bloccati.

## Creare un certificato personalizzato

**Prerequisito**

Per utilizzare le immagini di Firefly, l&#39;istanza di Adobe Learning Manager deve essere integrata con Firefly.

1. Accedi a Adobe Learning Manager come **Amministratore**.
2. Nella sezione **Configura**, seleziona **Risultati raggiunti**. Viene aperta la pagina **Distintivi**.
   ![Creazione di un certificato personalizzato](/help/migrated/administrators/feature-summary/assets/custom-cert-alm_images/create-custom-certificate1.png)
   *Passa a Risultati nel pannello di navigazione a sinistra*

3. Nel pannello di navigazione a sinistra, seleziona **Certificati**. Viene visualizzata la pagina **Certificati**.
   ![Creazione di un certificato personalizzato](/help/migrated/administrators/feature-summary/assets/custom-cert-alm_images/create-custom-certificate2.png)
   *Pagina del certificato*

4. Nell&#39;area superiore destra della pagina, selezionare **Nuovo certificato**. Viene visualizzata la finestra di dialogo **Crea nuovo certificato**.
5. Selezionare **Orizzontale** o **Verticale**, a seconda dell&#39;aspetto desiderato per il certificato. Dopo aver selezionato un orientamento, viene visualizzato un modello vuoto e modelli già pronti per tale orientamento.
   ![Creazione di un certificato personalizzato](/help/migrated/administrators/feature-summary/assets/custom-cert-alm_images/create-custom-certificate3.png)
   *Opzione Orizzontale o Verticale*

6. Seleziona un modello vuoto o esistente.
7. Immettere un nome per il certificato.
8. Nel menu a discesa, seleziona una lingua predefinita.
9. Selezionare **Crea**. Se si sceglie il modello vuoto, sotto il nome del certificato verrà visualizzata un&#39;area di lavoro vuota.
10. Aggiungi elementi: **Testo**, **Immagine**, **Valore dinamico** e **Sfondo certificato**.
    ![Creazione di un certificato personalizzato](/help/migrated/administrators/feature-summary/assets/custom-cert-alm_images/create-custom-certificate4.png)
    *Aggiungere elementi al certificato*

11. Per **Testo**, aggiungi contenuto sotto **Testo preformattato** o **Modelli di testo** oppure testo personalizzato. Il testo viene visualizzato nell&#39;area di lavoro. Quando il testo è selezionato, le opzioni di formattazione vengono visualizzate sopra l&#39;area di lavoro. Per rimuovere i contenuti non desiderati, seleziona l&#39;icona **Elimina** nell&#39;angolo superiore destro dell&#39;area di lavoro.
12. Per aggiungere le immagini, seleziona **Immagine** accanto a **Aggiungi elementi**. Carica immagini dal computer o seleziona immagini dagli elenchi delle categorie.
13. Seleziona **Valore dinamico** per aggiungere dettagli di base, etichette del catalogo e campi attivi.
14. Seleziona **Sfondo certificato** per applicare colori o immagini. Per creare immagini con Adobe Firefly, selezionare **Genera immagine**.
15. Nel campo Prompt, descrivi ciò che desideri (fino a 100 caratteri) e seleziona **Genera**. In base al messaggio, vengono visualizzate quattro opzioni per l’immagine.
16. Selezionare l&#39;immagine desiderata. Viene applicato come sfondo del certificato.
    ![Creazione di un certificato personalizzato](/help/migrated/administrators/feature-summary/assets/custom-cert-alm_images/create-custom-certificate5.png)
    *Aggiungi immagine al certificato*

17. Seleziona **Anteprima** per rivedere il certificato prima della pubblicazione. In questo modo è possibile comprendere l’aspetto del certificato.
    ![Creazione di un certificato personalizzato](/help/migrated/administrators/feature-summary/assets/custom-cert-alm_images/create-custom-certificate6.png)
    *Anteprima del certificato*

18. Nell’anteprima, puoi salvare su Google Drive, scaricare, stampare o utilizzare altre opzioni, come le proprietà di annotazione o del documento.
19. Seleziona **Salva come bozza** per continuare in un secondo momento oppure seleziona **Publish** per pubblicare il certificato. Dopo la pubblicazione, gli Allievi possono scaricare il certificato quando soddisfano l’obiettivo intermedio configurato.

Dopo aver salvato un certificato in **Pubblicato** o **Bozze**, è possibile modificarlo, clonarlo, rinominarlo o eliminarlo.

## Modificare un certificato personalizzato

1. Nella sezione **Configura**, seleziona **Risultati raggiunti**. Viene aperta la pagina **Distintivi**.
2. Nel pannello di navigazione a sinistra, seleziona **Certificati**. Viene visualizzata la pagina **Certificati**.
3. Selezionare la scheda **Pubblicato** o **Bozze** per il certificato desiderato.
4. Apri il menu delle azioni (**...**) per il certificato e seleziona **Modifica**.
   ![Modifica certificato dal menu Azioni](/help/migrated/administrators/feature-summary/assets/custom-cert-alm_images/image_0001.png)
   *Opzione Modifica nel menu a discesa*

5. Apportare le modifiche desiderate.
6. Seleziona **Publish** o **Salva come bozza**.

## Clonare un certificato personalizzato

Utilizzare **Clona** se si desidera una copia di un certificato per un nuovo nome o un caso d&#39;uso simile. Dopo la clonazione, rinominare il certificato in modo che abbia un nome distinto; in caso contrario, il nome può corrispondere all’origine anche se la progettazione è stata modificata.

>[!NOTE]
>
>Non potete impostare un nuovo nome mentre salvate immediatamente dopo la clonazione. Rinominare il certificato dopo averlo salvato come bozza o dopo averlo pubblicato.

1. Nella sezione **Configura**, seleziona **Risultati raggiunti**. Viene aperta la pagina **Distintivi**.
2. Nel pannello di navigazione a sinistra, seleziona **Certificati**. Viene visualizzata la pagina **Certificati**.
3. Selezionare la scheda **Pubblicato** o **Bozze** per il certificato desiderato.
4. Apri il menu delle azioni (**...**) per il certificato e seleziona **Clona**.
   ![Clona certificato dal menu Azioni](/help/migrated/administrators/feature-summary/assets/custom-cert-alm_images/image_0002.png)
   *Opzione Clona nel menu a discesa*

5. Apportare le modifiche desiderate.

6. Seleziona **Publish** o **Salva come bozza**.

7. Rinominare il certificato clonato utilizzando i passaggi descritti in [Rinominare un certificato personalizzato](#rename-a-custom-certificate).

## Rinominare un certificato personalizzato

È possibile rinominare un certificato senza clonarlo.

1. Nella sezione **Configura**, seleziona **Risultati raggiunti**. Viene aperta la pagina **Distintivi**.
2. Nel pannello di navigazione a sinistra, seleziona **Certificati**. Viene visualizzata la pagina **Certificati**.
3. Selezionare la scheda **Pubblicato** o **Bozze** per il certificato desiderato.

4. Apri il menu Azioni (**...**) per il certificato e seleziona **Rinomina**.
   ![Rinominare il certificato dal menu Azioni](/help/migrated/administrators/feature-summary/assets/custom-cert-alm_images/image_0003.png)
   *Opzione Rinomina nel menu a discesa*

5. Nella finestra di dialogo **Rinomina certificato**, immettere il nuovo nome.
   ![Finestra di dialogo Rinomina certificato](/help/migrated/administrators/feature-summary/assets/custom-cert-alm_images/image_0004.png)
   *Immettere un nuovo nome*

6. Seleziona **Salva**. Learning Manager mostra un messaggio di conferma.

## Eliminare un certificato personalizzato

Impossibile annullare l&#39;eliminazione di un certificato. Procedere solo se si è sicuri.

**Nota:** non è possibile eliminare un certificato associato a un oggetto di apprendimento o a un&#39;istanza.

1. Nella sezione **Configura**, seleziona **Risultati raggiunti**. Viene aperta la pagina **Distintivi**.
2. Nel pannello di navigazione a sinistra, seleziona **Certificati**. Viene visualizzata la pagina **Certificati**.
3. Selezionare la scheda **Pubblicato** o **Bozze** per il certificato desiderato.
4. Apri il menu delle azioni (**...**) per il certificato e seleziona **Elimina**. Adobe Learning Manager mostra un messaggio di conferma.
   ![Eliminare il certificato dal menu Azioni](/help/migrated/administrators/feature-summary/assets/custom-cert-alm_images/image_0005.png)
   *Opzione Elimina nel menu a discesa*
   ![Conferma dell&#39;eliminazione del certificato](/help/migrated/administrators/feature-summary/assets/custom-cert-alm_images/image_0006.png)
   *Messaggio di conferma*

5. Selezionare **Sì**. Se il certificato non è allegato a un oggetto di apprendimento o a un’istanza, Learning Manager completa l’eliminazione e potrebbe mostrare un’altra conferma.

## Impostare un certificato personalizzato come certificato predefinito

È possibile impostare un certificato come predefinito per:

- Corsi di formazione
- Percorsi di apprendimento
- Certificazioni
- Tutti

![Opzioni di certificato predefinite](/help/migrated/administrators/feature-summary/assets/custom-cert-alm_images/image_0007.png)
*Imposta come certificato predefinito*

1. Nella sezione **Configura**, seleziona **Risultati raggiunti**. Viene aperta la pagina **Distintivi**.
2. Nel pannello di navigazione a sinistra, seleziona **Certificati**. Viene visualizzata la pagina **Certificati**.
3. Selezionare la scheda **Pubblicato** o **Bozze** per il certificato desiderato.
4. Apri il menu delle azioni (**...**) per il certificato, seleziona **Imposta come predefinito**, quindi seleziona una delle quattro opzioni. Learning Manager mostra un messaggio di conferma.
5. Selezionare **Sì**. Learning Manager mostra un’altra conferma. Il certificato mostra un&#39;etichetta **Predefinita per** con la categoria selezionata (ad esempio, **Predefinita per i corsi di formazione**).
   ![Impostazione predefinita per l&#39;etichetta di categoria nel certificato](/help/migrated/administrators/feature-summary/assets/custom-cert-alm_images/image_0008.png)
   *Dopo che è diventato il certificato predefinito*
