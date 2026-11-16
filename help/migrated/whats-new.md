---
description: Scopri le nuove funzioni della versione di dicembre 2026 di Adobe Learning Manager, inclusi i grafici dei Report Builder e il Virtual Coach.
jcr-language: en_us
title: Novità della versione di dicembre 2026 di Adobe Learning Manager
exl-id: da46f186-3ff3-422a-af49-31c7405fd584
product_v2:
  - id: ed12e5b7-96e3-45e7-a17f-de222065ebcb
    internal-label: Learning Manager
source-git-commit: c01de295c4baa533ff15f4872df84ac197ffb3a7
workflow-type: tm+mt
source-wordcount: '4684'
ht-degree: 0%
---

# Novità della versione di dicembre 2026 di Adobe Learning Manager

Questa versione di Adobe Learning Manager introduce una serie di nuove funzioni e miglioramenti volti a semplificare la piattaforma e ad ampliarne le funzionalità. Questi aggiornamenti semplificano i flussi di lavoro quotidiani, migliorano l’organizzazione e la distribuzione dei contenuti di apprendimento e rendono l’esperienza complessiva più coerente e intuitiva.

## Grafici e dashboard dei Report Builder

Adobe Learning Manager ora supporta grafici e dashboard nel Report Builder, consentendo agli amministratori di visualizzare i dati dei report direttamente all’interno della piattaforma. Gli amministratori possono creare grafici dalle colonne dei report, con aggregazione e filtri disponibili in ogni grafico.

Report Builder supporta i seguenti tipi di grafico:

* Numero grande
* Grafico a linee
* Grafico a barre
* Grafico a torta
* Tabella pivot

Un dashboard di report contiene grafici creati da un report. Un dashboard personalizzato combina grafici provenienti da diversi report, ad esempio dati di iscrizione e dati utente, e supporta fino a 20 widget. I grafici che appartengono a un report vengono condivisi quando si condivide il report. In questo modo, gli amministratori possono mantenere i dati dei report correnti in un’unica visualizzazione anziché eseguire nuovamente i report. I grafici visualizzano fino a 10.000 punti dati e le tabelle pivot fino a 100 righe e 100 colonne. Se un grafico supera un limite, applicare filtri per restringere i risultati. I dashboard non possono ancora essere esportati.

## Report di Insights Agent nel Report Builder

Gli amministratori possono ora continuare a lavorare con le risposte dell&#39;agente Insights nel Report Builder. Quando Insights Agent risponde a una domanda, Report Builder mappa la stessa query ai propri campi in un passaggio parallelo. Gli amministratori possono aprire, rivedere, modificare e salvare il report. Da qui è possibile utilizzare le stesse funzionalità di Report Builder di qualsiasi altro report, ad esempio gli abbonamenti.

Se una parte di una domanda non può essere espressa con campi di Report Builder, il report elenca tale parte come spazio vuoto. Se la parte mancante è fondamentale per la domanda, il rapporto non viene offerto. Le query complesse possono produrre risultati ridotti, pertanto esaminare ogni report prima di fare affidamento su di esso.

## Integrazione con Adobe Experience Manager Assets

Adobe Learning Manager si integra ora con Adobe Experience Manager Assets, consentendo agli Autori di accedere e utilizzare i contenuti di apprendimento e le risorse di immagini approvati direttamente da un archivio centralizzato. Questo rimuove il passaggio di download e caricamento manuale tra il team che gestisce le risorse in Digital Asset Manager (DAM) e il team che crea i corsi in Adobe Learning Manager.

Cosa cambia:

* **Accedi alle risorse approvate:** gli autori sfogliano e selezionano le risorse da Experience Manager Assets senza uscire da Adobe Learning Manager, pertanto i corsi utilizzano file aggiornati e approvati, anziché copie locali che possono risultare obsolete.
* **Aggiornamento costante delle risorse del corso:** quando una risorsa cambia nel DAM, l’aggiornamento può fluire nei corsi utilizzandolo automaticamente, mantenendo i contenuti coerenti durante la revisione delle risorse.
* **Access segue le autorizzazioni esistenti:** gli autori visualizzano solo le risorse a cui hanno già accesso in Experience Manager Assets, pertanto la navigazione in Adobe Learning Manager rispetta le stesse autorizzazioni del sistema DAM.

Il risultato è un unico percorso regolamentato da risorsa a Allievo, con meno lavoro manuale e meno corrispondenze nelle versioni.

## Miglioramenti per l’invio di file

I moduli per l&#39;invio di file ora supportano l&#39;invio da parte del team e la valutazione basata su rubriche. Una nuova impostazione controlla anche se l’approvazione dell’Istruttore è necessaria per gli invii.

### Invii del team

Gli istruttori possono ora creare team per l’invio dei file. Ogni team invia un file per l&#39;intero team. L’Istruttore valuta l’invio una volta e il risultato si applica a ogni membro. I team si formano in due modi: gli istruttori li creano manualmente o un processo pianificato li crea prima della data di inizio dell’istanza, in base ai membri per team o al numero di team.

Gli istruttori gestiscono i team nella nuova pagina **Gestione team** e rivedono il lavoro nella pagina degli invii del team. Gli istruttori possono anche annullare l’invio di un file approvato per sbloccare il team quando sono necessarie modifiche, ad esempio quando un membro del team lascia il team. Un team può contare fino a 100 membri. Gli Allievi possono visualizzare il team, i membri e i risultati della valutazione. I moduli Team non possono essere aggiunti o eliminati dopo la pubblicazione di un corso.

### Valutazioni basate su Rubrica

Gli autori possono ora definire una rubrica, denominata piano di valutazione, per i moduli di invio dei file. Una rubrica supporta le domande oggettive con opzioni a punteggio e le domande soggettive con revisione scritta.

Gli Autori possono anche configurare le seguenti impostazioni:

* Se gli Allievi visualizzano le domande di valutazione basate su rubriche prima dell’invio
* Indica se il punteggio è un punteggio complessivo o un punteggio per ogni criterio

Ogni domanda può essere contrassegnata come necessaria e configurata per consentire commenti del revisore. Una valutazione basata su rubriche contiene fino a 100 domande e gli Autori immettono le domande separatamente per ciascuna lingua. Dopo la pubblicazione di un corso, solo il testo delle domande può essere modificato.

### Approvazione dell’istruttore o completamento automatico

Gli Autori possono ora scegliere se l’invio dei file richiede l’approvazione dell’Istruttore o se viene completato automaticamente. Questa impostazione è indipendente dal piano di valutazione.

## Server protocollo di contesto modello per l’Assistente Allievo

ALM consente agli Allievi di accedere alla formazione negli strumenti già utilizzati tramite un server MCP (Model Context Protocol). Gli Allievi possono accedere a Learning Manager da qualsiasi luogo, compresi ChatGPT, Claude e agenti personalizzati. Configura il server nell’app di amministrazione dell’integrazione per consentire agli Amministratori di accedere a sei strumenti di base per gli Allievi. Questi includono due strumenti dell’Assistente Allievo: Answer Agent e Percorso di apprendimento personalizzato.

Il server offre le seguenti funzionalità:

* Cerca
* Elenca iscrizioni
* Ottieni oggetto di apprendimento
* Ottieni profilo utente
* Rispondi alla domanda sui contenuti di apprendimento
* Ottieni percorso di apprendimento personalizzato

Gli amministratori possono modificare la descrizione di ogni strumento per aggiungere esempi specifici dell&#39;organizzazione. Poiché i client leggono i dettagli di autorizzazione dai metadati del server, il programma di installazione richiede solo un ID client e un segreto client.

## Modifica e branding del percorso di apprendimento personalizzato

Gli allievi ora possono rimuovere gli argomenti o i corsi suggeriti in un unico passaggio, oltre all’opzione esistente per perfezionare gli argomenti e gli elenchi dei corsi tramite chat.

Gli Amministratori ora possono riposizionare la striscia Percorsi di apprendimento personalizzati nella home page dell’Allievo tramite la pagina di branding.

## Esercitarsi con il ruolo di istruttore virtuale

Adobe Learning Manager ora offre Virtual Coach, una soluzione di gioco di ruolo e coaching basata sull’intelligenza artificiale che consente agli Allievi di praticare conversazioni realistiche sul posto di lavoro prima di affrontarle sul posto di lavoro. Gli esempi includono le obiezioni alle vendite, le escalation dei clienti e le revisioni delle prestazioni.

Gli autori creano scenari dai propri materiali di riferimento utilizzando modelli o un assistente AI e gli Allievi parlano con un personaggio AI che si adatta alle loro risposte in tempo reale. Dopo ogni sessione, gli Allievi ottengono punteggi istantanei e feedback di coaching sia sulla conoscenza che sullo stile di comunicazione, misurato rispetto ai criteri definiti dall’Autore.

Virtual Coach supporta nove lingue e può essere utilizzato come risorsa formativa autonoma o incorporato in un corso.

## Citazioni del percorso di apprendimento nell’Assistente Allievo

Le risposte dell’Allievo ora citano il percorso di apprendimento che contiene un corso di origine, insieme al corso stesso. Gli Allievi aprono la panoramica del corso o la pagina del percorso di apprendimento dalla citazione. Le risposte tratte da una risorsa formativa includono un collegamento per il download. Questo aiuta gli Allievi a trovare il corso di formazione che risponde alla loro domanda.

## Configurazioni Assistente AI

L&#39;Assistente Amministratore offre due agenti: Agente di Insights e Agente della conoscenza. Possono essere configurati singolarmente. L’Assistente Allievo offre tre agenti: Knowledge Agent, Answer Agent e Learning Path Agent. Possono essere configurati insieme alla configurazione del catalogo.

## Webhook per le modifiche dell’Istruttore alle istanze degli oggetti di apprendimento

Il webhook di modifica dell’istanza dell’oggetto di apprendimento ora si attiva quando un Istruttore modifica una sessione di un’aula virtuale, oltre alle modifiche per Amministratore e Autore. Modifiche quali gli orari delle sessioni, la sede e il limite di iscrizioni lo attivano. I clienti headless possono quindi recuperare i dettagli della sessione tramite l’API pubblica e trasmettere gli aggiornamenti agli Allievi.

## Corsi con iscrizione multipla nel widget di conformità

Il widget di conformità ora elenca tutte le istanze di un corso con più iscrizioni che un Allievo deve completare. Ogni voce visualizza il nome dell&#39;istanza. Se un’istanza ha una scadenza, qualsiasi istanza senza una scadenza viene nascosta. L’endpoint di iscrizione dell’API pubblica supporta lo stesso comportamento tramite un parametro opzionale.

## Inviare nuovamente gli inviti alla sessione aula virtuale

Gli Amministratori con autorizzazione di modifica del corso possono ora inviare nuovamente un invito alla sessione dalla pagina dell’istanza. Seleziona **Invia di nuovo**, cerca l’Allievo e invia. L’opzione è disponibile per le sessioni in aula virtuale correnti e future. Per gli Allievi in più istanze, l’invito va solo all’istanza selezionata. Gli Allievi non iscritti alla sessione vengono ignorati con un avviso.

## Partecipazione automatica dalle viste di registrazione di Adobe Connect

Adobe Learning Manager ora contrassegna la partecipazione quando un Allievo riproduce la registrazione di una sessione in aula virtuale persa. Un’integrazione pianificata estrae i dati del visualizzatore da Adobe Connect e confronta il tempo di riproduzione con i criteri di completamento impostati per l’account. Gli amministratori impostano la pianificazione nell’app di amministrazione dell’integrazione. Adobe Learning Manager considera solo il tempo di visualizzazione effettivo durante la determinazione della partecipazione, pertanto il passaggio a una registrazione non viene conteggiato ai fini dei criteri di completamento.

## Email Builder per corsi e istanze

Email Builder in Adobe Learning Manager consente agli Amministratori e agli Autori di creare modelli di comunicazione con il marchio degli Allievi. Nella versione di dicembre 2026 di Learning Manager, l’esperienza completa di Creazione e-mail è disponibile per e-mail a livello di corso e di istanza. Gli Autori possono personalizzare questi messaggi e-mail ereditando i layout e la formattazione definiti dagli Amministratori.

Con Email Builder, puoi:

* Crea layout e-mail riutilizzabili
* Applicare il branding dell’organizzazione
* Personalizzare banner e firme
* Definire font e colori predefiniti
* Standardizzazione della comunicazione tra corsi e programmi di apprendimento

Gli amministratori creano modelli e layout e-mail per l’intero account. Gli autori personalizzano le e-mail a livello di corso e di istanza senza ricostruire i modelli da zero.

Le impostazioni relative al banner e alla firma sono state spostate. In precedenza, queste impostazioni erano visualizzate in una scheda **Impostazioni** separata. Questa scheda è stata rimossa e **Banner** e **Firma** sono ora visualizzati in **Layout globale**.

### Gerarchia di Generatore e-mail

Generatore e-mail utilizza una gerarchia. Ogni livello eredita dal proprio livello principale e consente la personalizzazione locale.

| **Livello** | **Cosa fornisce** | **Chi lo personalizza** |
|-------------------|---------------------------------------------------------------------------------------------------------------------|-----------------------|
| Layout account | Branding, font, colori e struttura di intestazione e piè di pagina | Amministratori |
| Modello di account | Stile e-mail globale, componenti di messaggistica comuni e branding condiviso | Amministratori |
| Modello di corso | E-mail specifiche per il corso, come messaggi di iscrizione, promemoria del corso, e-mail di completamento e notifiche della sessione | Autori |
| Modello di istanza | Il massimo livello di personalizzazione, ad esempio messaggi specifici della coorte, della sessione o regionali | Autori |

Tutti i corsi possono ereditare dai modelli di account. Le e-mail dei corsi ereditano il layout dell’organizzazione e consentono la personalizzazione dei contenuti.

### Ereditarietà dei layout

Un modello si collega al layout disponibile più vicino. Un modello a livello di istanza viene collegato a un layout a livello di istanza, se presente. Se non ne esiste alcuno, il modello viene collegato al layout principale più vicino. Potete visualizzare il livello da cui proviene un layout.

Quando un modello è collegato a un layout:

* Il branding viene inserito automaticamente nel modello.
* Gli autori aggiornano solo il contenuto.
* Il layout riduce la duplicazione tra i messaggi.

Potete scollegare un modello dal suo layout. Dopo aver scollegato un modello:

* Il modello mantiene la struttura esistente.
* I futuri aggiornamenti del layout non influiranno sul modello.
* Il modello diventa modificabile in modo indipendente.

L’ereditarietà dei layout dipende dai layout principali disponibili. Quando sono presenti entrambi i livelli, le e-mail a livello di istanza hanno la precedenza sui modelli a livello di corso.

### Flusso di lavoro Amministratore e Autore

Gli amministratori utilizzano modelli a livello di account per mantenere i messaggi coerenti in tutto l’account, che gestiscono creando un layout e un modello, quindi pubblicando il branding.

Gli autori utilizzano modelli a livello di istanza quando le coorti necessitano di messaggi diversi, che gestiscono tramite le istanze del corso.

### Disponibilità di Email Builder per le e-mail relative a corsi e istanze

Se Email Builder è già abilitato per il tuo account, riceverai automaticamente le nuove modifiche e non dovrai intraprendere alcuna azione. Le funzionalità e-mail esistenti continuano a funzionare indipendentemente dalle attività di migrazione di Email Builder.

## Attributi personalizzati dell’Allievo in Interoperabilità degli Strumenti di apprendimento

Adobe Learning Manager ora legge gli attributi personalizzati degli Allievi tramite l’endpoint facoltativo Names and Role Provisioning Services di Interoperabilità degli Strumenti di apprendimento. Inoltre, le legge dalla richiesta di avvio. Attributi come paese o città vengono memorizzati in campi di profilo raggruppabili. I parametri di avvio richiedono un prefisso affinché Adobe Learning Manager li riconosca. Alcuni sistemi di apprendimento, come Moodle, non supportano questo endpoint.

## Notifiche Istruttore bacheca di discussione

I clienti headless possono ora inviare a Istruttori e responsabili della coorte un riepilogo delle attività dell’area discussioni. Utilizzando l’API, puoi aggiungere sottoscrittori a una bacheca. Ricevono nuovi post, commenti e risposte in un&#39;unica e-mail, a un intervallo impostato. I Mi piace e i non mi piace non sono inclusi. La funzione viene attivata tramite l’API.

## Classificazione della pertinenza nella ricerca del catalogo dell’amministratore

La ricerca nel catalogo nella visualizzazione per amministratori ora classifica i risultati per pertinenza, utilizzando lo stesso servizio di ricerca degli Allievi e della ricerca per amministratori in altri luoghi. Una corrispondenza esatta, ad esempio un nome di catalogo con una data specifica, viene visualizzata per prima, seguita da corrispondenze parziali. L&#39;elenco dei suggerimenti durante la digitazione segue lo stesso ordine.

## Sincronizzazione dell’annullamento di sessione da Adobe Workfront

Le sessioni annullate in Adobe Workfront vengono trasferite a Adobe Learning Manager durante la procedura di migrazione, senza passaggi manuali. La migrazione aggiunge una colonna facoltativa **Stato** che accetta **Attivo** o **Annullato**. Un valore vuoto lascia invariata la sessione. Una cancellazione effettuata tramite Migrazione si comporta come una effettuata nell’interfaccia di Learning Manager. Allievi, Istruttori, Amministratori, Autori e Manager ricevono le stesse e-mail di annullamento.

Alle sessioni annullate si applicano due comportamenti:

* La migrazione non applica modifiche di dettaglio a una sessione annullata e restituisce un errore di convalida per tali righe.
* L’impostazione dello stato su Attivo riattiva la sessione, che può quindi essere aggiornata o annullata di nuovo.

Gli aggiornamenti della sessione continuano a funzionare come prima.

## Limite caratteri per nomi

Adobe Learning Manager ora accetta nomi composti da un massimo di 255 caratteri (fino a 63). Ciò si applica agli utenti aggiunti nell&#39;interfaccia, tramite l&#39;importazione CSV e nella registrazione autonoma, in modo che le sincronizzazioni degli utenti da altri sistemi non abbiano più esito negativo sui nomi lunghi.

Ciò è particolarmente utile quando si esegue la migrazione degli utenti da un sistema esterno o si automatizza la creazione degli utenti.

A partire dalla versione di dicembre 2026, il campo del nome accetta fino a 255 caratteri. Le versioni precedenti accettavano un massimo di 63 caratteri.

>[!NOTE]
>
>Il limite si applica a tutti gli utenti del tuo account, indipendentemente dal loro ruolo. Gli utenti esistenti e i loro nomi non sono interessati da questa modifica.

È possibile immettere nomi lunghi quando si aggiungono o si modificano utenti nei modi seguenti:

* Aggiunta di un singolo utente nell’interfaccia di amministrazione
* Modificare un utente esistente
* Importare gli utenti con un file CSV
* Registra gli utenti tramite registrazione autonoma
* Aggiungi utenti esterni

I nomi lunghi possono essere più ampi dello spazio disponibile in alcune parti dell’interfaccia. Per mantenere il layout leggibile, Adobe Learning Manager accorcia i nomi lunghi nelle seguenti aree compatte:

* Celle di tabella
* Elementi elenco a discesa
* Risultati di ricerca

Per visualizzare il nome completo, passa il mouse sopra il nome abbreviato.

## Informazioni sui distintivi per corsi e percorsi di apprendimento

Quando gli Autori aggiungono un corso o un percorso di apprendimento, una finestra elenca i corsi e i percorsi di apprendimento esistenti con le informazioni sul badge. Nella finestra sono visualizzati il nome, il tipo (corso o percorso di apprendimento), lo stato della pubblicazione e il formato del corso, ad esempio autonomo, virtuale, in aula o misto.

## Miglioramenti senza accesso

Learning Manager ora consente l’accesso controllato ai contenuti di apprendimento senza richiedere agli utenti di accedere. Gli Amministratori possono specificare quali cataloghi sono pubblici, mentre gli Autori possono determinare quali corsi e moduli sono disponibili senza un account. I contenuti pubblici sono pubblicati come pagine crawlable e leggibili dall&#39;intelligenza artificiale, rendendo l&#39;accademia individuabile attraverso motori di ricerca e assistenti all&#39;intelligenza artificiale come Claude e ChatGPT. L’utilizzo anonimo viene monitorato per visitatore e riportato separatamente dall’utilizzo per l’accesso.

### Utilizzo dei contenuti senza accesso

I visitatori della tua accademia pubblica possono ora riprodurre i contenuti selezionati direttamente dalla pagina della panoramica del corso, senza dover ricorrere a account, e-mail o moduli.

* **Attivazione o disattivazione dell&#39;accesso non connesso:** gli amministratori possono attivare o disattivare l&#39;utilizzo di contenuti non connessi per l&#39;intero account.
* **Rendere disponibili corsi o moduli senza accedere:** gli autori possono rendere disponibile un intero corso senza accedere o aprire solo moduli specifici, ad esempio un modulo introduttivo gratuito prima dei contenuti avanzati gestiti.
* **Eredita impostazioni dai corsi:** I percorsi di apprendimento e le certificazioni seguono le impostazioni dei corsi al loro interno, senza ulteriori impostazioni.
* **Visualizza i contenuti senza accedere:** gli Allievi non autenticati possono visualizzare i contenuti disponibili non connessi senza accedere al proprio account.
* **Solo contenuti autonomi:** i contenuti con licenza di terze parti e i contenuti del catalogo acquisiti non possono essere resi disponibili senza accesso.
* **Report sul consumo anonimo:** è possibile generare un report sul consumo mensile non connesso.
* **Abilita l&#39;apprendimento senza accesso tra le piattaforme:** L&#39;utilizzo di contenuti senza accesso è supportato su Adobe Learning Manager nativo su Web e dispositivi mobili, su distribuzioni headless e su accademie basate su widget Adobe Experience Manager Sites.

### Scegliere i cataloghi pubblici

Gli amministratori ora possono scegliere i cataloghi specifici che appaiono nell&#39;accademia pubblica. Solo questi cataloghi possono essere sfogliati da visitatori anonimi e indicizzati da motori di ricerca e assistenti di intelligenza artificiale, quindi i corsi di prova o i contenuti interni rimangono privati.
 
### Trova in motori di ricerca e assistenti AI (Beta)

Adobe Learning Manager può ora rendere la tua accademia pubblica reperibile da motori di ricerca come Google e da assistenti AI come ChatGPT, Claude e Gemini. I tuoi corsi possono quindi essere visualizzati nei risultati della ricerca e nelle risposte generate dall&#39;intelligenza artificiale, attribuite alla tua accademia.

* I controlli a livello di account consentono agli amministratori di decidere se i crawler possono accedere all&#39;accademia pubblica e se il relativo contenuto può essere indicizzato.
* Ogni accademia ottiene la propria sitemap e robots.txt, generati automaticamente dai cataloghi che hai reso pubblici.
* Il rendering delle pagine viene eseguito per i crawler, in modo che gli assistenti AI che non eseguono JavaScript possano comunque leggerle.
* I crawler vedono solo ciò a cui un visitatore può accedere. I contenuti gestiti non vengono mai esposti.
* Meta title, description e dati strutturati: Adobe Learning Manager li genera automaticamente per ogni corso, percorso di apprendimento e certificazione, in base ai metadati di apprendimento.

>[!NOTE]
>
>L&#39;intelligenza artificiale e l&#39;individuazione delle ricerche in Adobe Learning Manager nativo richiedono un dominio personalizzato. Le installazioni headless dovranno implementare parti della configurazione nel proprio ambiente.

## Ritiro di un corso senza rendere inaccessibile un percorso di apprendimento

Un corso ritirato o un percorso di apprendimento nidificato viene rimosso dall’oggetto di apprendimento di livello superiore, che resta aperto per nuove iscrizioni. Se un corso viene ritirato, il percorso di apprendimento non sarà più accessibile.

## URL della pagina senza accesso per i profili di registrazione autonoma

I profili di registrazione autonoma consentono agli utenti esterni, come partner o membri di più organizzazioni, di creare i propri account Adobe Learning Manager. Ogni profilo ora può avere il proprio URL di menu condivisibile non connesso, incorporato in Experience Builder.

Quando gli utenti selezionano **Registrati** da una pagina raggiunta tramite tale URL, questi vengono aggiunti al profilo a cui appartiene l&#39;URL. In questo modo gli utenti di organizzazioni diverse, ad esempio agenzie o società partner separate, vengono mantenuti in profili separati.

## Archivia le date dell’ultimo accesso per le iscrizioni al percorso di apprendimento

Adobe Learning Manager consente ora di allegare metadati personalizzati, ad esempio la data dell’ultimo accesso, a un’iscrizione a un percorso di apprendimento. L’impostazione e la lettura avviene tramite l’API, che consente di tenere traccia dell’accesso in base al tempo ai percorsi di apprendimento assegnati.

Le iscrizioni ai corsi supportano già una data di ultimo accesso tramite l’API, che controlla la durata di accesso di un Allievo al corso. Le iscrizioni al percorso di apprendimento ora offrono un campo di metadati generico, che consente di memorizzare la data dell’ultimo accesso o qualsiasi altro valore di cui desideri tenere traccia.

## Esportare i report di Report Builder con l’API dei processi

Questa versione di Adobe Learning Manager aggiunge un nuovo tipo di processo API processo, `generateCustomReport`. Trasmetti un ID report per esportare automaticamente tutti i report creati nel Report Builder.

In combinazione con il nuovo set di dati del quiz L2 in Report Builder, ora puoi:

* Esporta i dati dei quiz a livello di domanda (L2) in più corsi e moduli in un unico report, anziché eseguire `generateQuizReport` una volta per corso.
* Automatizza le esportazioni ricorrenti, ad esempio un’esportazione incrementale giornaliera nel data warehouse o nello strumento di business intelligence.

I tipi di processo esistenti, inclusi `generateQuizReport`, rimangono invariati.

## Modifiche all’intestazione di colonna nei report scaricati

Il Report Builder ora include il nome del set di dati nelle intestazioni di colonna predefinite dei report scaricati, pertanto il nome del set di dati dell’oggetto di apprendimento viene visualizzato come **Oggetto di apprendimento - Nome** anziché come **Nome**. Per le colonne aggregate, l’intestazione include anche la funzione, ad esempio **Numero di oggetti di apprendimento - ID**. Se si immette un nome personalizzato nel campo **Alias** di una colonna, tale alias verrà utilizzato come intestazione e rimarrà invariato.

Dopo l’aggiornamento, i report esistenti senza alias personalizzati mostrano le intestazioni aggiornate, mentre i dati, i filtri e le pianificazioni dei report non sono interessati. Se gli script, i fogli di calcolo, i dashboard di business intelligence o le integrazioni fanno riferimento a colonne per intestazione, aggiornarli in base ai nuovi nomi o impostare un alias personalizzato per mantenere un&#39;intestazione specifica.

## Live Hub

Live Hub è ora generalmente disponibile per i clienti Ultimate e rimane in versione beta per i clienti Prime.

## Supporto multilingue per sottotitoli codificati nell’Hub live

I sottotitoli codificati nell’Hub live sono stati migliorati per supportare altre lingue. Gli istruttori possono ora selezionare la lingua dei sottotitoli in **Impostazioni sala** in base alla lingua parlata durante la sessione.

I sottotitoli vengono generati automaticamente nella lingua selezionata e visualizzati in un pannello dedicato che si aggiorna continuamente mentre l’Istruttore parla. Tutti i partecipanti visualizzano i sottotitoli nella lingua selezionata dall’Istruttore.

Questo miglioramento migliora l’accessibilità per i partecipanti in diverse lingue e li aiuta a seguire le sessioni dal vivo in modo più efficace.

## Interfaccia Live Hub localizzata e lettore di registrazione

L’interfaccia Hub live ora viene visualizzata nella lingua selezionata per l’interfaccia utente di Learning Manager. Le etichette e i titoli durante la sessione, incluse chat, partecipanti, sondaggi, breakout room e impostazioni, vengono visualizzati nella lingua scelta dall&#39;utente. L’Hub live supporta le stesse 18 lingue di interfaccia di Learning Manager, inglese incluso. Anche il lettore di registrazione è localizzato, quindi elementi come i sondaggi vengono visualizzati nella lingua del corso. Ad esempio, una registrazione di un corso di tedesco visualizza l’interfaccia del lettore in tedesco.

Questo offre ai partecipanti globali un’esperienza uniforme su tutta la piattaforma e nelle registrazioni delle sessioni.

## Sessioni Hub live fino a 5000 partecipanti

Live Hub ora supporta sessioni su larga scala con un massimo di 5000 partecipanti, consentendo alle organizzazioni di condurre sessioni di formazione di grandi dimensioni. Gli Autori possono scegliere una capacità di 5000 partecipanti quando aggiungono un modulo Classe virtuale a un corso. L’Hub live configura automaticamente la sala in base alle dimensioni del pubblico e applica specifiche restrizioni di interazione.

Nelle sessioni di grandi dimensioni, si applicano le funzionalità e i comportamenti seguenti:

* L’accesso alla videocamera, la condivisione dello schermo e la funzionalità della lavagna sono limitati agli istruttori.
* Le stanze di svago non sono disponibili.
* Grandi volumi di messaggi, reazioni e domande di chat simultanee vengono distribuiti in batch scaglionati.
* Altre interazioni e funzionalità, tra cui sondaggi, quiz, registrazione e monitoraggio delle presenze, funzionano come nelle sessioni regolari.

Ciò consente alle organizzazioni di eseguire sessioni di formazione di grandi dimensioni all&#39;interno della stessa piattaforma, con una sala che può essere impostata sulle dimensioni del pubblico previste.

## Canali

I canali sono ora generalmente disponibili per tutti i clienti.

## Prenotazione dell&#39;iscrizione al gruppo e gestione della lista d&#39;attesa

La prenotazione delle iscrizioni ai gruppi e la gestione della lista d’attesa offrono agli Autori un controllo più preciso su chi può iscriversi ai corsi in aula e in aula virtuale. Gli Autori possono assegnare postazioni a gruppi di utenti specifici e impostare date di apertura separate per l’iscrizione a tali gruppi e per tutti gli altri Allievi. Possono anche attivare la promozione automatica della lista d’attesa con una data limite, in modo che un posto disponibile vada al prossimo Allievo idoneo. La prenotazione di tutte le postazioni limita un corso ai gruppi selezionati.

## Supporto di più connessioni Zoom

Adobe Learning Manager ora supporta più connessioni Zoom all’interno di un singolo account, consentendo alle organizzazioni di gestire le sessioni in aula virtuale tra diversi account Zoom.

Gli Amministratori di integrazione possono configurare più connessioni Zoom e assegnarle a ruoli o gruppi di utenti specifici. Quando crei o modifichi una sessione del corso, gli Autori possono scegliere tra le connessioni Zoom disponibili, con ogni sessione che utilizza una connessione.

Questo miglioramento offre maggiore flessibilità alle organizzazioni che utilizzano più account Zoom, in particolare nei seguenti casi:

* **Formazione specifica per il reparto**: gestione di account Zoom separati per reparti o team diversi all’interno dello stesso account Learning Manager.
* **Formazione per partner ed esterni**: assegnazione di connessioni Zoom dedicate a partner o gruppi di utenti specifici per supportare le sessioni di formazione.
* **Accesso controllato**: limita la disponibilità delle connessioni Zoom in base ai ruoli o ai gruppi di utenti, garantendo che gli autori possano selezionare solo le connessioni assegnate.
* **Gestione semplificata delle connessioni**: consente agli amministratori dell’integrazione di gestire centralmente più connessioni Zoom senza influire sulle sessioni esistenti.

## Integrazione del browser per esami sicuri per i quiz

Adobe Learning Manager si integra ora con Safe Exam Browser per quiz nativi, fornendo un ambiente sicuro e controllato per lo svolgimento delle valutazioni. Gli amministratori possono abilitare l’integrazione a livello di account e caricare un file di configurazione Safe Exam Browser (.seb) per definire le restrizioni della valutazione. Gli Autori possono quindi scegliere quali singoli quiz richiedono il browser per esami sicuri.

Quando gli Allievi tentano un quiz che richiede un browser per esami sicuro, viene richiesto di avviare il browser. In questo modo viene bloccato l&#39;accesso ad altri browser e applicazioni per la durata della valutazione in base alle restrizioni definite dall&#39;amministratore. Agli Allievi che non lo hanno installato viene richiesto di scaricarlo.

**Dove è utile:**

* **Valutazioni della certificazione:** condurre quiz in cui è importante limitare l&#39;accesso a risorse esterne.
* **Corso di formazione sulla conformità:** supporto di valutazioni controllate per i requisiti normativi e di formazione obbligatori.
* **Valutazioni ad alto rischio:** ridurre le opportunità di accesso ad applicazioni o risorse non autorizzate durante valutazioni importanti.
* **Gestione flessibile della valutazione:** Consentire agli autori di richiedere il browser degli esami sicuro solo per i quiz che richiedono restrizioni aggiuntive.

## Correzioni relative all’accessibilità nell’Hub live

Le correzioni relative all’accessibilità nell’Hub live migliorano l’esperienza degli utenti che utilizzano tecnologie di supporto e la navigazione tramite tastiera.

* **Screen reader**: i controlli e i contenuti ora sono annunciati correttamente con NVDA, JAWS, VoiceOver e TalkBack.
* **Navigazione tramite tastiera**: ogni elemento interattivo è raggiungibile in un ordine di tabulazione logico con un indicatore di attivazione visibile, lo stato attivo non viene più bloccato e è disponibile un collegamento per ignorare la navigazione.
* **Sottotitoli codificati**: le sessioni dal vivo mostrano i sottotitoli in tempo reale, le registrazioni supportano il caricamento e la disattivazione dei sottotitoli e l&#39;interruttore per i sottotitoli può essere attivato dalla tastiera.
* **Contrasto colore**: i componenti di testo e interfaccia ora soddisfano le proporzioni di contrasto richieste ed è disponibile un tema ad alto contrasto.
* **Zoom e ridisposizione**: i contenuti e le funzionalità vengono mantenuti con uno zoom del browser del 200% e l&#39;Hub dinamico funziona con le lenti di ingrandimento dello schermo.

## Modifiche alle API nella versione di dicembre 2026 di Adobe Learning Manager

### Ordinamento delle API dei segnalibri e gestione dei contenuti ritirati

Gli Allievi possono aggiungere segnalibri ai corsi di formazione per riesaminarli in un secondo momento. In precedenza, le API dei segnalibri restituivano i corsi di formazione salvati senza un ordine specifico, impedendo alle integrazioni headless di visualizzare prima quelli salvati più di recente. Anche i segnalibri relativi agli oggetti di apprendimento ritirati sono rimasti nell’elenco e hanno causato errori di tipo &quot;Pagina non trovata&quot;.

Questo aggiornamento risolve entrambi i problemi:

* I segnalibri ora vengono restituiti innanzitutto come più recenti.
* I segnalibri per gli oggetti di apprendimento ritirati non vengono più restituiti.

Non vengono aggiunti nuovi endpoint, parametri o attributi di risposta, pertanto le integrazioni esistenti continuano a funzionare senza modifiche.

### API per notifiche Istruttore dell&#39;area discussioni

Questa versione include nuove API che supportano le notifiche per gli Istruttori nell’area discussioni. Utilizzali per iscrivere Istruttori e Manager di coorte alle aree discussioni e per controllare quale attività viene visualizzata nelle e-mail di riepilogo.

### Supporto API per istanze con iscrizione multipla nell’app per Allievi

L’API delle iscrizioni ora supporta le istanze con iscrizione multipla nell’app per Allievi. Aggiungere il parametro facoltativo `includeMultiInstanceEnrollments=true` a `GET /enrollments` per includerli. Il valore predefinito è `false`, pertanto le integrazioni esistenti, incluse le implementazioni headless, continuano a funzionare senza modifiche.

### Ultima data di accesso per l’iscrizione ai percorsi di apprendimento

Ora puoi archiviare i metadati personalizzati, ad esempio la data dell’ultimo accesso, in un’iscrizione al percorso di apprendimento e impostarli e leggerli tramite l’API. Ciò consente di tenere traccia dell’accesso in base al tempo ai percorsi di apprendimento assegnati.

* Imposta i metadati su un’iscrizione esistente o al momento dell’iscrizione di un Allievo, utilizzando un token di amministrazione.
* Leggilo con un token Amministratore o Allievo.

I metadati servono per il tracciamento. Non controlla l’accesso e non viene applicato ai corsi nel percorso.

### Tipo di processo API processo per esportazioni Report Builder

L&#39;API dei processi dispone di un nuovo tipo di processo, `generateCustomReport`, che esporta qualsiasi report di Report Builder salvato quando viene superato il relativo ID. Con il nuovo set di dati dei quiz L2, puoi esportare i dati dei quiz a livello di domanda tra più corsi in un unico report e automatizzare le esportazioni ricorrenti.

I tipi di processo esistenti, inclusi `generateQuizReport`, rimangono invariati.

### API per il connettore Zoom

Utilizza queste API per visualizzare e gestire i connettori Zoom in Adobe Learning Manager. Utilizzali per recuperare le connessioni Zoom esistenti, salvare le credenziali Zoom, creare o aggiornare le connessioni e gestire le autorizzazioni di accesso per i gruppi di utenti e i ruoli personalizzati.

**Sequenza API**

Utilizza le API in questa sequenza:

| **Passaggio** | **API** | **Scopo** | **Autenticazione** |
|------------------------------------|---------------------------------------------------------------|---------------------------------------------------------------------------------------------|-----------------------------------------------------|
| 1 | `POST /ctr/authcred/uuid/20012    ` | Salva le credenziali di Zoom. | Sessione di Amministratore dell’integrazione |
| 2 | `POST /ctr/app/esconnect  ` | Crea una connessione Zoom o aggiorna una esistente. | Sessione di Amministratore dell’integrazione |
| 3 | `PUT /ctr/xtsa/{connectionId}/access` | Imposta i gruppi di utenti e i ruoli personalizzati che possono utilizzare la connessione. | Sessione di Amministratore dell’integrazione |

**Autenticazione e autorizzazioni**

Queste API utilizzano l’autenticazione basata su sessione e richiedono all’utente di accedere come Amministratore dell’integrazione in Adobe Learning Manager.
