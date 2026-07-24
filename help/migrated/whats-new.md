---
description: Scopri le nuove funzioni e i miglioramenti nella versione di aprile 2026 di Adobe Learning Manager, comprese le modifiche a livello di API e webhook
jcr-language: en_us
title: Novità della versione di agosto 2026 di Adobe Learning Manager
exl-id: da46f186-3ff3-422a-af49-31c7405fd584
source-git-commit: e476ca4736098ced4e21d0d713628b9682aab3da
workflow-type: tm+mt
source-wordcount: '2839'
ht-degree: 0%

---

# Novità della versione di agosto 2026 di Adobe Learning Manager

>[!IMPORTANT]
>
>Le funzioni descritte in questo articolo sono disponibili come parte della versione beta. Le funzioni beta di Adobe Learning Manager sono fornite a scopo di valutazione e possono essere modificate, limitate o rimosse prima del rilascio di disponibilità generale. I nomi delle funzioni, il comportamento e le opzioni di configurazione sono soggetti a modifiche senza preavviso.


## Corsi adattativi

I corsi adattivi consentono di erogare corsi di formazione personalizzati controllando i moduli visualizzati da ciascun Allievo e quelli richiesti in base ai gruppi di utenti a cui appartiene. Un singolo corso presenta in modo dinamico il contenuto corretto alla persona giusta.

Gli autori configurano ogni modulo con **Facoltativo** e **Obbligatorio** per le regole del gruppo di utenti. Gli Allievi appartenenti a gruppi di utenti diversi possono completare set di moduli completamente diversi, pur continuando a completare lo stesso corso. I limiti di posti per le sessioni in aula e in aula virtuale sono ora applicati a livello di modulo, in modo che un Allievo possa essere iscritto a un corso mentre è in lista d’attesa solo per una sessione specifica. Per ulteriori informazioni, consulta [Corsi adattativi - Autore](/help/migrated/authors/feature-summary/adaptive-course-author.md)

Funzionalità principali:

* Regole di visibilità e completamento a livello di modulo per gruppo di utenti
* Logica di unione OR: se un gruppo rende obbligatorio un modulo, questo è obbligatorio per quell’Allievo
* Liste di attesa a livello di modulo per le sessioni in aula e in aula virtuale
* Aggiornamento del completamento attivato quando cambia il profilo di un Allievo
* Supportato nei percorsi di apprendimento e nelle certificazioni con limitazioni documentate per le certificazioni ricorrenti

Ulteriori informazioni sui corsi adattivi.

## Gradebook

Un gradebook in Adobe Learning Manager aggiunge un punteggio ponderato ai corsi, consentendo agli autori di assegnare una percentuale di contributo a ciascun modulo con punteggio e di impostare un punteggio minimo aggregato per il completamento del corso. Gli Allievi possono monitorare i propri punteggi nel corso e gli Amministratori possono visualizzare i punteggi finali e scaricare le trascrizioni pertinenti.

### Che cosa fa Gradebook

Un corso abilitato per i gradebook calcola il punteggio finale di ogni Allievo combinando i singoli punteggi del modulo in base alla percentuale di ponderazione assegnata a ciascun modulo. Ciò fornisce una misura precisa e ponderata delle prestazioni, piuttosto che una semplice somma di punteggi o un marcatore di superamento/fallimento basato solo sul completamento.

Gradebook supporta due modelli di completamento:

* **Solo moduli obbligatori**: il corso viene completato al termine di tutti i moduli obbligatori. I punteggi dei Gradebook sono ancora calcolati e visibili, ma il punteggio aggregato non contribuisce al superamento dei criteri.

* **Moduli richiesti più punteggio aggregato**: l’Allievo deve completare tutti i moduli richiesti e ottenere un punteggio aggregato pari o superiore alla soglia minima di superamento. Per ottenere un voto favorevole devono essere soddisfatte entrambe le condizioni.

### Come vengono calcolati i punteggi dei corsi

Per ogni modulo con punteggio, il contributo al punteggio aggregato del corso è:

(Punteggio ottenuto ÷ Punteggio massimo) × % ponderazione = Contributo modulo

Il punteggio del corso aggregato è la somma di tutti i contributi al modulo. Le percentuali di ponderazione in tutti i moduli con punteggio devono sommarsi esattamente a 100. Impossibile salvare la configurazione del file Gradebook finché non viene soddisfatta questa condizione.

Il punteggio del corso aggregato è la somma di tutti i contributi al modulo. Le percentuali di ponderazione in tutti i moduli con punteggio devono sommarsi esattamente a 100. Impossibile salvare la configurazione del file Gradebook finché non viene soddisfatta questa condizione.

Non è necessario che la scala di punteggio sia coerente tra i moduli. Una sessione in aula ha ottenuto un punteggio di 100 e un modulo SCORM ha ottenuto un punteggio di 10 può coesistere nello stesso grafico. La formula normalizza ciascun contributo prima di applicare la ponderazione.

**Moduli con punteggio e senza punteggio**

Solo i moduli che producono un punteggio possono essere ponderati. I tipi di modulo con punteggio includono:

* Contenuto SCORM, AICC e xAPI con punteggio abilitato
* Captivate pacchetti di contenuti
* Quizzi nativi in Adobe Learning Manager
* Sessioni in aula e in aula virtuale in cui l’istruttore o l’amministratore inserisce un punteggio
* Moduli attività valutati da un Istruttore o Amministratore

Ai tipi di modulo non classificabili, ai file PDF, ai file video, ai file audio, alle presentazioni PowerPoint, ai documenti Word, ai file Excel e al contenuto HTML non può essere assegnata una percentuale di ponderazione e non contribuiscono al punteggio aggregato. Questi moduli potrebbero essere ancora necessari per il completamento del corso. Quando l’opzione Includi moduli che non contribuiscono al livello finale è abilitata, questi vengono visualizzati nel grafico senza un valore di ponderazione.

Per ulteriori informazioni, consulta [Gradebook per autori](/help/migrated/authors/feature-summary/alm-author-gradebook.md)

## Cartelle dei contenuti gerarchici

La Libreria dei contenuti ora supporta fino a tre livelli di gerarchia di cartelle private. Gli amministratori creano la struttura delle cartelle e controllano quali ruoli personalizzati possono accedere alle cartelle di livello 1. L&#39;accesso a cascata viene eseguito automaticamente a tutte le sottocartelle all&#39;interno di una cartella di livello 1.

Gli Autori possono copiare e spostare il contenuto tra le cartelle, filtrare la Libreria dei contenuti per cartella e sfogliare la gerarchia quando aggiungono moduli a un corso.

Funzionalità principali:

* Fino a tre livelli di nidificazione (massimo 25 sottocartelle per principale)
* Accesso basato su ruoli assegnato solo al livello 1
* Il contenuto può essere visualizzato in più cartelle senza duplicazioni
* La struttura delle cartelle pubbliche e private si esclude a vicenda
* Esplora le cartelle durante la selezione dei moduli durante la creazione del corso

Per ulteriori informazioni sulle funzionalità a livello di amministratore, vedere [Cartelle dei contenuti gerarchici](/help/migrated/administrators/feature-summary/settings/advanced-settings.md#content-folder). Per ulteriori informazioni sulle funzionalità a livello di autore, vedere [Cartelle dei contenuti gerarchici](/help/migrated/authors/feature-summary/content-library.md#add-content-to-a-folder).

## Live Hub

Live Hub è un&#39;esperienza di formazione virtuale basata sull&#39;intelligenza artificiale in Adobe Learning Manager che aiuta le organizzazioni a offrire un apprendimento dal vivo coinvolgente e di grande impatto. Con funzionalità intelligenti come sondaggi basati sull&#39;intelligenza artificiale, breakout room orchestration, spazi di apprendimento persistenti e assistenza basata sull&#39;intelligenza artificiale, Live Hub potenzia la produttività degli istruttori riducendo la complessità della distribuzione delle sessioni.

Punti salienti:

* Migliora l’apprendimento dal vivo con un’esperienza Adobe Learning Manager nativa che migliora la qualità dell’istruzione e i risultati degli Allievi.
* Dai ai tuoi Istruttori un co-facilitatore basato sull&#39;intelligenza artificiale che guida il coinvolgimento attraverso sondaggi intelligenti, supporto di domande e risposte e approfondimenti della sala d&#39;intervento.
* Aiuta i tuoi Allievi a ottenere di più da ogni sessione con riepiloghi generati dall&#39;intelligenza artificiale e registrazioni di sessione ricercabili per argomento.
* Misura ciò che conta con le analisi di coinvolgimento che vanno oltre la partecipazione per rivelare una reale partecipazione all&#39;apprendimento.
* Aiuta gli Autori a utilizzare il Finder di istruttori basato sull’intelligenza artificiale per abbinare l’Istruttore giusto in base a competenze, disponibilità, orari preferiti, fuso orario e utilizzo corrente.

>[!NOTE]
>
>Live Hub è attualmente disponibile in versione beta e sarà disponibile con la prossima versione di agosto di Adobe Learning Manager. La documentazione di Live Hub sarà disponibile una volta rilasciata la funzione.


## Generatore di modelli e-mail basati su componenti

Le organizzazioni possono ora creare notifiche e-mail con marchio di livello Enterprise in Adobe Learning Manager utilizzando un editor di componenti WYSIWYG moderno. Gli amministratori possono creare un layout globale una volta, con un’intestazione, un piè di pagina e gli elementi del marchio riutilizzabili, e applicarlo a tutti i modelli e-mail a livello di account. I singoli modelli possono quindi essere personalizzati a livello di corso o di istanza, ereditando il layout principale per impostazione predefinita e sostituendolo solo quando necessario.

Funzionalità principali:

* Editor WYSIWYG con una libreria di componenti riutilizzabili (testo, immagine, pulsante, divisore, intestazione, piè di pagina)
* Supporto delle variabili: consente di inserire campi dinamici quali nome dell’Allievo, nome del corso e data di scadenza
* Gerarchia di modelli collegati e non collegati: le modifiche apportate a un modello collegato vengono propagate a tutti i modelli secondari; i modelli non collegati possono essere modificati in modo indipendente
* Supporto per modelli multilingue
* Anteprima e verifica invio prima della pubblicazione
* Compatibilità con le versioni precedenti: i modelli e-mail esistenti continuano a funzionare

Per ulteriori informazioni, consulta [Generatore di e-mail basato su componenti](/help/migrated/administrators/feature-summary/email-builder.md)

## Supporto per l’apprendimento esterno

Gli Allievi possono ora inviare corsi di formazione off-platform, come certificazioni, workshop, conferenze e corsi esterni, per l’approvazione del Manager direttamente dal dashboard degli Allievi. Gli invii approvati vengono visualizzati nella Trascrizione Allievo.

Funzionalità principali:

* Modulo di invio configurabile con campi standard e personalizzati
* Flusso di lavoro di revisione e approvazione del Manager con supporto dei commenti
* Gli invii approvati vengono visualizzati in Trascrizione Allievo con metadati completi
* L’Amministratore può configurare i campi obbligatori, inclusi quelli personalizzati
* Nuove colonne nelle Trascrizioni Amministratore e Allievo: Nome apprendimento esterno, Commento di completamento, Colonne dei campi personalizzati
* Supporto API: cinque nuovi endpoint con ambito Allievo per la creazione, il recupero e l’aggiornamento degli invii

Per ulteriori informazioni a livello di amministratore, consulta [Supporto per l’apprendimento esterno](/help/migrated/administrators/feature-summary/settings/basic-settings.md). Per ulteriori informazioni a livello di manager, consulta [Supporto per l’apprendimento esterno](/help/migrated/managers/feature-summary/review-external-learning-requests.md). Per ulteriori informazioni a livello di Allievo, consulta [Supporto per l’apprendimento esterno](/help/migrated/learners/feature-summary/submit-external-learning.md).

## Funzioni basate su IA

### Assistente AI per gli Allievi

L’Assistente all’intelligenza artificiale per gli Allievi ora supporta quattro nuove funzionalità oltre a rispondere alle domande dei contenuti di apprendimento assegnati:

* **Riepilogo del corso**: utilizza il comando / per selezionare un elemento del catalogo e generare un riepilogo senza aprire il corso
* **Confronto tra oggetti di apprendimento**: seleziona fino a due oggetti di apprendimento utilizzando il comando / e chiedi all’assistente di confrontarli
* **Risposte di Adobe Experience League**: l&#39;assistente ora trova le risposte alle domande sulle procedure dalla documentazione della guida di Adobe Learning Manager
* **Query sui contenuti di terze parti**: è possibile eseguire query sui contenuti del catalogo Go1 e LinkedIn Learning (solo metadati; solo inglese; l’assimilazione richiede 1-2 ore dopo l’aggiunta del catalogo)

Per ulteriori informazioni, consulta [Assistente AI per gli Allievi](/help/migrated/learners/feature-summary/learner-ai-assistant.md).

### Agente del percorso di apprendimento

Gli Allievi possono ora intrattenere una conversazione guidata con l’Assistente all’intelligenza artificiale per generare un percorso di apprendimento personalizzato e in sequenza in base ai loro obiettivi, allo sfondo e al tempo disponibile. Il percorso di apprendimento viene creato automaticamente e l’Allievo viene iscritto.

Funzionalità principali:

* La conversazione a più turni guida l’Allievo attraverso la selezione dell’argomento, la revisione del corso e la conferma del percorso
* Fino a cinque argomenti di apprendimento suggeriti per conversazione
* Selezione del corso dai cataloghi assegnati
* Massimo 10 percorsi di apprendimento personalizzati visibili nella home page dell’Allievo
* I percorsi completati possono essere condivisi con i colleghi

Per ulteriori informazioni, consulta [Assistente AI per gli Allievi](/help/migrated/learners/feature-summary/learning-path-agent.md).

### Agente Insights

Insights Agent aiuta gli amministratori ad analizzare i dati di apprendimento attraverso query in linguaggio naturale. Porre domande sulle tendenze di iscrizione, sui tassi di completamento, sul coinvolgimento degli Allievi e sulle lacune nelle competenze. L&#39;agente genera report e visualizzazioni in risposta.

Per ulteriori informazioni, vedere [Agente Insights](/help/migrated/administrators/feature-summary/insights-agent.md)

### Crediti di intelligenza artificiale

Adobe Learning Manager integra funzionalità basate sull&#39;intelligenza artificiale gestite tramite un sistema basato sul credito collegato alle licenze di Agent Orchestrator. Questo sistema richiede agli amministratori di attivare le funzioni, impostare i limiti di credito e monitorare l’utilizzo tramite la pagina Fatturazione. Il collegamento dell&#39;account Adobe Learning Manager a un&#39;organizzazione Adobe Admin Console con una licenza di Agent Orchestrator attiva è essenziale per abilitare le funzionalità di intelligenza artificiale generale.

Per ulteriori informazioni, consulta [Crediti AI di generazione](/help/migrated/administrators/feature-summary/billing-management.md#genaicredits)

## Canali

I canali forniscono un modo centralizzato per organizzare, pubblicare e scoprire contenuti video da pagine Web e Confluence. Gli amministratori possono creare e gestire i canali collegando le pagine Web supportate o le pagine di Confluence, configurando le impostazioni dei canali, controllando la visibilità e sincronizzando il contenuto dall’origine. Gli Allievi possono sfogliare i canali disponibili, abbonarsi ai canali di interesse e guardare contenuti video selezionati da un’unica posizione.

Per ulteriori informazioni, consulta [Creazione di canali](/help/migrated/administrators/feature-summary/create-channels.md)

## Report Builder

Report Builder offre agli amministratori uno strumento di reporting self-service flessibile che va oltre i tipi di report fissi disponibili altrove in Adobe Learning Manager. Anziché limitarsi a strutture di report predefinite, gli amministratori possono unire campi di più set di dati, come Utente, Gruppi di utenti, Corsi e Percorsi di apprendimento, Moduli, Trascrizione, Cataloghi e altro ancora, in un unico report personalizzato in base alle esigenze specifiche dell’organizzazione.

I report vengono creati una sola volta e salvati per un uso ripetuto. Non è necessario ricreare i filtri, riapplicare i raggruppamenti o ricollegare i set di dati a ogni download. I report salvati possono essere scaricati su richiesta, condivisi con altri amministratori o configurati con una sottoscrizione in modo che i destinatari ricevano automaticamente i report aggiornati a intervalli regolari.

Per ulteriori informazioni, consulta [Report Builder](/help/migrated/administrators/feature-summary/alm-report-builder.md).

## Modifiche al ruolo personalizzato

Agli amministratori personalizzati possono ora essere concesse funzionalità estese di gestione degli utenti tramite il livello di autorizzazione Avanzate in Utenti in una definizione di ruolo personalizzata.

Sono disponibili due livelli di accesso:

| Livello di accesso | Funzionalità dell&#39;amministratore personalizzato |
|---|---|
| **Sola lettura** | Visualizza tutti i ruoli personalizzati, i registri di importazione e gli utenti eliminati; scarica il report dei ruoli personalizzati |
| **Controllo completo** | Tutte le funzionalità di sola lettura più: creazione, modifica, eliminazione e assegnazione di ruoli personalizzati; importazione di utenti tramite CSV; rimozione di utenti eliminati |

Ulteriori informazioni sulle modifiche ai ruoli personalizzati. Per ulteriori informazioni, vedere [Sblocco dell&#39;autorizzazione utente avanzata](/help/migrated/administrators/feature-summary/custom-role.md#whatadvanceduserpermissionunlocks)

## Collegamento profondo LTI

Gli Amministratori di integrazione possono ora abilitare il collegamento profondo LTI per le configurazioni degli strumenti LTI, consentendo agli Autori del corso di sfogliare e integrare i corsi Adobe Learning Manager direttamente da un LMS esterno senza copiare manualmente gli URL del corso.

Una volta attivato, gli autori visualizzano un pulsante **Seleziona contenuto** nella configurazione dell&#39;attività LMS esterna. Possono sfogliare i cataloghi approvati, selezionare corsi e confermare la selezione, con tutti i campi compilati automaticamente.

Per ulteriori informazioni, vedere [Collegamenti diretti LTI](/help/migrated/integration-admin/feature-summary/lti-deep-links.md).

## Aule

Le aule ora supportano un formato strutturato di **posizioni in quattro campi**, tra cui Paese, Stato/Provincia/Area geografica, Città e Nome aula, semplificando la gestione e l’organizzazione delle aule di formazione tra aree geografiche diverse. L’aggiornamento include una migrazione una tantum dal precedente formato per campo singolo e aggiunge il supporto multilingue per i campi **Nome località** e **Informazioni stanza**, consentendo di localizzare i dettagli dell’aula per gli Allievi.

Per ulteriori informazioni, consulta [Aule](/help/migrated/administrators/feature-summary/classroom.md)

## Disponibile a breve: Adobe Learning Manager Content Composer

Adobe Learning Manager Content Composer è uno strumento di authoring per corsi di intelligenza artificiale in arrivo in Adobe Learning Manager che consente di creare rapidamente un corso pronto per la pubblicazione.

Un assistente di intelligenza artificiale conversazionale ti guiderà attraverso l&#39;intero processo: Chiedi conferma, Breve, Contorno e Corso, in modo da mantenere il controllo in ogni fase, rivedendo e perfezionando prima di procedere. Potrai creare contenuti per la messa a terra nei tuoi documenti sorgente, applicare il tema istantaneo dei corsi e condividere o esportare i corsi completati tramite SCORM o la pubblicazione diretta su Adobe Learning Manager.

## Segnalazione delle modifiche nella versione

Ulteriori informazioni sui [report delle modifiche nella versione di agosto 2026 di Adobe Learning Manager](/help/migrated/reporting-changes-august-2026.md).

## Modifiche API nella versione

Ulteriori informazioni sulle [modifiche API nella versione di agosto 2026 di Adobe Learning Manager](/help/migrated/api-changes-august-2026.md).

## Altri miglioramenti nella versione

| Miglioramento | Descrizione |
|---|---|
| **MQA: punteggio più recente rispetto a quello più alto** | Per i moduli con più tentativi, gli Autori possono ora scegliere se il punteggio dei tentativi più recente o più elevato debba essere registrato nella Trascrizione Allievo e utilizzato nei calcoli della cartella degli studi. Latest era l&#39;impostazione predefinita esistente e rimane tale anche quando l&#39;impostazione non è configurata. Per ulteriori informazioni, consulta [Gradebook per autori](/help/migrated/authors/feature-summary/alm-author-gradebook.md#configurescoresettingsmultipleattempts). |
| **Anteprima del contenuto nella libreria dei contenuti** | Gli Autori ora possono visualizzare in anteprima i file di contenuti caricati direttamente nella Libreria dei contenuti prima di aggiungerli ai corsi. Per ulteriori informazioni, vedere [Anteprima libreria dei contenuti](/help/migrated/authors/feature-summary/content-library.md#previewcontentlibrary). |
| **Report utente incrementale** | Un nuovo report utente basato su API restituisce solo gli utenti creati o modificati dall’ultima richiesta, riducendo il trasferimento di dati per account di grandi dimensioni utilizzando flussi di lavoro di sincronizzazione automatica degli utenti. Per ulteriori informazioni, vedere [Report utente incrementale](/help/migrated/incremental-user-report.md). |
| **11 nuove lingue nel lettore Fluidic** | Il lettore Fluidic ora supporta 11 lingue aggiuntive, incluso il supporto per script da destra a sinistra (RTL). Per ulteriori informazioni, consulta [Lettore Fluidic](/help/migrated/learners/feature-summary/fluidic-player.md). |
| **Migrazione del modulo LTI** | I moduli LTI 1.1 esistenti possono ora essere migrati a LTI 1.3 utilizzando lo strumento di migrazione. Per ulteriori informazioni, consulta [Migrazione LTI dei moduli](/help/migrated/integration-admin/feature-summary/migration-manual.md#migrationofltimodules). |
| **Generatore di e-mail: supporto per editor di testo RTF** | I modelli e-mail in Adobe Learning Manager ora supportano la formattazione RTF, gli allegati e le automatizzazioni personalizzate. Per ulteriori informazioni, vedere [Generatore di e-mail](/help/migrated/administrators/feature-summary/email-builder.md). |
| **Generatore di e-mail: funzione di anteprima** | Puoi controllare l’e-mail composta per vedere come apparirebbe alla fine del destinatario utilizzando l’opzione Anteprima. Per ulteriori informazioni, vedere [Generatore di e-mail](/help/migrated/administrators/feature-summary/email-builder.md). |
| **Standardizzazione timestamp webhook** | Tutti i campi di data e ora nell’oggetto `data` dei payload del webhook ora hanno secondi impostati su `00`, fornendo precisione a livello di minuti coerente con i report di Trascrizione Allievo. |
| **Miglioramenti della connessione** | Aggiornamenti del connettore Azure Data Lake Storage (ADLS); supporto del nome della sala permanente per le sessioni ricorrenti dell&#39;aula virtuale; monitoraggio della frequenza basato sulla visualizzazione della registrazione. |
| **Miglioramenti delle prestazioni del lettore** | Il lettore per corsi fluidic è stato ottimizzato per tempi di caricamento più rapidi e transizioni più fluide tra i moduli. |
| **Avviso di impatto prima di ritirare corsi/programmi di apprendimento** | Gli Amministratori ora visualizzano un avviso che elenca tutte le iscrizioni attive e i percorsi di apprendimento dipendenti prima che un corso o un percorso di apprendimento possa essere ritirato. |
| **Modulo CR/VC: durata prevista** | Gli Autori possono ora impostare una durata prevista per i moduli aula e aula virtuale, separata dall’orario pianificato della sessione. Questo valore viene visualizzato nei report e nelle informazioni sui corsi rivolti agli Allievi. |
| **Conferma prima di modificare i corsi acquisiti** | Gli amministratori degli account condivisi tra pari ora visualizzano una finestra di dialogo di conferma prima di modificare un corso acquisito tramite la condivisione del catalogo, impedendo modifiche involontarie ai contenuti condivisi. |
| **URL della sessione con ID istanza** | Gli URL di avvio della sessione per le sessioni Microsoft Teams, Adobe Connect e Zoom ora includono l’ID istanza, garantendo che gli Allievi vengano indirizzati alla sessione corretta quando sono presenti più istanze. |
| **Avviso per annunci di pubblico numeroso** | Quando si invia un messaggio e-mail di annuncio ad-hoc a più di una soglia configurabile di destinatari, gli amministratori ora visualizzano un avviso di volume prima dell’invio. |
| **Modelli e-mail: URL account per Allievi esterni** | I modelli di notifica e-mail ora possono includere un URL account separato specifico per gli Allievi esterni, indirizzandoli alla corretta esperienza di accesso. |
| **AEM Sites** | Nella sezione **Il tuo profilo** > Le tue aree di interesse è ora disponibile un solo pulsante **Modifica** per modificare le preferenze per prodotti e ruoli e competenze. Anche questo fa parte di native Learning Manager. |
| **AEM Sites** | In precedenza esistevano due pulsanti **Modifica**, ma ora il pulsante **Modifica** è un pulsante consolidato per modificare le preferenze per Prodotti e ruoli e competenze. |
| **Fuso orario** | Una nuova casella di ricerca è stata aggiunta appena sotto il campo Fuso orario nelle Impostazioni profilo dell’utente che ha effettuato l’accesso. La casella di ricerca può essere utilizzata per cercare direttamente un fuso orario invece di scorrere l’intero elenco dei fusi orari disponibili. Se desideri modificare il fuso orario esistente, seleziona un nuovo fuso orario e fai clic su Salva. Il nuovo fuso orario viene salvato. Il pulsante Salva viene visualizzato solo quando si seleziona un fuso orario. |

## Requisiti di sistema

Visualizza [requisiti di sistema di Adobe Learning Manager](/help/migrated/system-requirements.md).

## Note sulla versione

Consulta le [note sulla versione](/help/migrated/release-note/release-notes.md) per gli aggiornamenti più recenti.

## Versioni precedenti di Adobe Learning Manager

* [Adobe Learning Manager - Versione di aprile 2026](/help/migrated/whats-new-april-2026.md)
* [Adobe Learning Manager versione di ottobre 2025](/help/migrated/whats-new-october-2025.md)
