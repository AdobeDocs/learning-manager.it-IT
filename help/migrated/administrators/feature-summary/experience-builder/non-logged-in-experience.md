---
description: Illustra come Experience Builder può pubblicare pagine di apprendimento e cataloghi rivolti al pubblico per i visitatori anonimi, tra cui funzionalità chiave, widget supportati, prerequisiti (Connettore di accesso ai dati di formazione), limitazioni e indicazioni per la configurazione, la scalabilità e la migrazione dalla home page legacy senza accesso.
jcr-language: en_us
title: Configurare e gestire le pagine senza accesso in Experience Builder
exl-id: e4685cab-08ca-4b6b-93f4-a9eecf382dc4
source-git-commit: 2f9e931523da6e3e1ed2cf60f1ad05f5caf3cc1b
workflow-type: tm+mt
source-wordcount: '6058'
ht-degree: 1%

---


# Esperienza senza accesso in Experience Builder

## Introduzione

L’esperienza senza accesso in Experience Builder consente alle organizzazioni di visualizzare i contenuti di apprendimento e le pagine del portale a tutti i visitatori, inclusi quelli che non hanno effettuato l’accesso. Questa funzione è progettata per attirare, informare e coinvolgere i potenziali Allievi offrendo un’anteprima fluida e con marchio delle offerte di formazione prima di richiedere l’accesso o l’iscrizione.

Questa funzione consente di creare e personalizzare pagine pubbliche utilizzando la stessa intuitiva interfaccia di trascinamento disponibile in Generatore di esperienza standard. È possibile mostrare cataloghi di corsi, categorie, percorsi e contenuti statici avanzati, tra cui immagini, testo, HTML e immagini incorporate, per chiunque visiti il portale. In questo modo è possibile evidenziare i programmi di apprendimento, promuovere nuovi corsi e fornire informazioni essenziali a un pubblico più ampio.

I visitatori possono sfogliare il catalogo, visualizzare i dettagli su corsi e istanze e utilizzare la ricerca globale per esplorare le opportunità di formazione disponibili. Tuttavia, per le azioni che richiedono l’identità di un utente, ad esempio l’iscrizione a un corso, l’accesso a funzioni personalizzate (come Calendario, Conformità, Classifica o Apprendimento sociale) o la partecipazione a corsi di formazione, il visitatore dovrà effettuare l’accesso. Questo approccio garantisce che le informazioni sensibili e personalizzate rimangano al sicuro, pur consentendo un&#39;esperienza di anteprima completa.

Gli amministratori possono configurare le pagine e i widget visibili agli utenti che non hanno effettuato l’accesso, in modo da visualizzare solo il contenuto appropriato. Le pagine possono essere impostate in modo da essere accessibili sia agli utenti che hanno effettuato l’accesso che a quelli che non l’hanno fatto, oppure in modo esclusivo per uno di questi gruppi. Experience Builder offre una modalità di anteprima che consente di vedere esattamente come appariranno le pagine ai visitatori prima della pubblicazione.

Per abilitare questa funzione, l&#39;amministratore dell&#39;integrazione ALM deve attivare il connettore di accesso ai dati di formazione. Questo connettore garantisce che i metadati del corso siano accessibili al pubblico.

Il branding e la localizzazione sono completamente supportati e consentono di personalizzare i titoli delle pagine, i favicon e le impostazioni della lingua in modo che siano in linea con l&#39;identità dell&#39;organizzazione e soddisfino le esigenze del pubblico. Come parte della transizione a questa esperienza avanzata, la funzionalità della pagina principale precedente per gli utenti non connessi sarà dichiarata obsoleta. Pertanto, tutti i nuovi contenuti pubblici devono essere creati utilizzando Experience Builder.

## Scopo della funzione

L’esperienza senza accesso in Experience Builder consente alle organizzazioni di mostrare pubblicamente i contenuti di apprendimento e le pagine del portale a chiunque, senza richiedere agli utenti di accedere. Questo consente di attirare, informare e coinvolgere i potenziali Allievi fornendo un’anteprima dei corsi di formazione e delle risorse disponibili prima che sia necessaria l’iscrizione o l’autenticazione.

## Casi d&#39;uso reali di esperienza senza accesso

- **Marketing e sensibilizzazione**: le organizzazioni possono promuovere i propri programmi di formazione a un pubblico esterno, ad esempio potenziali clienti, partner o candidati, rendendo pubblicamente accessibili i cataloghi dei corsi e i dettagli dei programmi.
- **Esplorazione pre-iscrizione**: gli Allievi possono sfogliare i corsi disponibili, visualizzare le panoramiche ed esplorare le categorie prima di decidere di iscriversi o accedere, aiutandoli a prendere decisioni consapevoli in merito all’iscrizione.
- **Portali di formazione aziendali**: le aziende possono fornire un portale pubblico per informazioni sulla conformità o sull&#39;onboarding, consentendo ai nuovi assunti o appaltatori di vedere quale formazione è disponibile prima di ricevere le credenziali.
- **Pagine di destinazione evento o campagna**: le organizzazioni che eseguono campagne di apprendimento o eventi possono creare pagine pubbliche dedicate per evidenziare corsi, pianificazioni o risorse in primo piano, aumentando la visibilità e il coinvolgimento.
- **SEO e individuabilità**: rendendo pubbliche pagine e cataloghi selezionati, le organizzazioni migliorano la visibilità dei motori di ricerca, rendendo più facile per le persone scoprire le offerte di apprendimento online.

## Concetti chiave dell’esperienza senza accesso

L’esperienza non registrata di Experience Builder ti consente di mostrare pubblicamente contenuti di apprendimento e pagine di portali, consentendo ai visitatori di sfogliare senza accedere.

- **Creare pagine e menu pubblici**: è possibile impostare pagine e un menu singolo a cui tutti possono accedere, indipendentemente dallo stato di accesso.
- **Aggiungere solo i widget supportati**: sono inclusi i widget che non richiedono contesto utente (categorie, corsi e percorsi di apprendimento, casella di contenuto, HTML, iframe), mentre i widget specifici dell&#39;utente vengono nascosti.
- **Configura il comportamento adattivo della pagina**: decidi se visualizzare una pagina sia per gli utenti che hanno effettuato l’accesso che per quelli che non l’hanno fatto, e il sistema adatta i widget visibili e il contenuto in base allo stato di accesso.
- **Anteprima di entrambe le esperienze**: le opzioni di anteprima consentono di visualizzare le pagine con gli utenti che hanno effettuato l’accesso e quelli che non l’hanno fatto, con differenze a livello di visibilità e contenuto del widget.
- **Abilita ricerca globale**: i visitatori cercano corsi e contenuti, ma ottengono solo funzionalità di ricerca di base senza integrazione avanzata di intelligenza artificiale.
- **Consenti ai visitatori di sfogliare il catalogo e le panoramiche del corso**: i visitatori possono esplorare pagine del catalogo, dettagli del corso e istanze, ma devono accedere per iscriversi o accedere a funzioni personalizzate.
- **Personalizzare il branding e la localizzazione**: hai impostato le icone preferite e le impostazioni della lingua in modo che corrispondano alle esigenze di branding e accessibilità della tua organizzazione.
- **Abilita il connettore di accesso ai dati di formazione**: attiva questo connettore per esportare i metadati del corso per la visualizzazione pubblica, mantenendo aggiornate le pagine senza accesso.
- **Gestire un traffico elevato con un&#39;infrastruttura condivisa**: il sistema gestisce grandi volumi di visitatori anonimi utilizzando risorse condivise e limitando la velocità.
- **Ottimizza per SEO**: la piattaforma prepara le pagine pubbliche per l’indicizzazione dei motori di ricerca, semplificando la ricerca dei contenuti di apprendimento.

## Prerequisiti per l’esperienza senza accesso

- Prima di poter utilizzare l’esperienza senza accesso, è necessario abilitare il Connettore di accesso ai dati di formazione nell’Amministratore dell’integrazione.
- Il connettore esporta i metadati del corso in un repository pubblico, che mantiene aggiornate le pagine senza accesso.

### Inizializzazione del connettore TDA

Il connettore TDA (Training Data Access) è un prerequisito critico per l&#39;attivazione della nuova funzione di creazione di esperienze senza accesso in ALM. Questo connettore facilita l’esportazione dei metadati di formazione, consentendo al portale di visualizzare le informazioni sul corso agli utenti che non hanno effettuato l’accesso.

- **Attivazione del connettore**: è necessario abilitare il connettore TDA dal pannello di amministrazione dell’integrazione. Questo passaggio sblocca la funzionalità del generatore di esperienze senza accesso e rende visibili le opzioni dell&#39;interfaccia utente pertinenti nell&#39;interfaccia di amministrazione.
- **Esportazione di metadati**: una volta attivato, il connettore esporta i metadati di formazione essenziali (ad esempio nome del corso, descrizione, panoramica, valutazione, durata e abilità) da ALM a un repository pubblico. Questi dati vengono utilizzati per popolare pagine e widget che non hanno effettuato l’accesso.
- **Pianificazione e sincronizzazione**: il processo di esportazione può essere pianificato (ad esempio, ogni giorno) per garantire che nel portale vengano visualizzati gli aggiornamenti più recenti del corso. Le modifiche apportate in ALM verranno visualizzate nelle pagine non connesse dopo il successivo ciclo di esportazione, in base alla frequenza di memorizzazione nella cache e di esportazione.
- **Disponibilità funzionalità**: le funzionalità del generatore di esperienze senza accesso, tra cui creazione di menu, supporto del widget e visibilità del catalogo, sono accessibili solo dopo l&#39;inizializzazione del connettore TDA. Se il connettore non è abilitato, Experience Builder rimarrà limitato agli scenari utente connessi.
- **Migrazione e supporto**: per gli account che passano da funzioni precedenti della pagina principale senza accesso, l’inizializzazione del connettore TDA è il primo passo verso la migrazione. Garantisce la possibilità di sfruttare la flessibilità del nuovo Experience Builder e le funzionalità avanzate.

## Cosa possono fare i visitatori senza effettuare l’accesso

In un sito Experience Builder non connesso, i visitatori possono sfogliare il catalogo dei corsi di formazione aprendo la pagina del catalogo per i cataloghi pubblici. Possono utilizzare filtri quali catalogo, prodotto, ruolo, tipo, abilità e tag, a seconda della configurazione del sito. I visitatori possono anche cercare i corsi di formazione utilizzando la barra di ricerca globale nell’intestazione (se abilitata) e visualizzare i risultati della ricerca direttamente nella pagina del catalogo.

I visitatori possono visualizzare i dettagli del corso di formazione aprendo le pagine di panoramica per corsi, percorsi di apprendimento e certificazioni. In queste pagine sono visualizzati i metadati principali, inclusi titolo, descrizione, autore, durata, formato, tag e abilità.

Inoltre, i visitatori possono esplorare contenuti statici e promozionali. Possono leggere blocchi di testo e di contenuto RTF, visualizzare banner e porzioni di immagine e interagire con i frame incorporati come micrositi, video o strumenti esterni.

Se un visitatore fa clic su Iscriviti o tenta di avviare un corso di formazione, il sistema richiede di effettuare l&#39;accesso o di registrarsi. Dopo aver eseguito correttamente l’accesso, il visitatore viene reindirizzato alla pagina appropriata, che si tratti della home page, di una pagina personalizzata o del corso di formazione specifico selezionato.

## Cosa non è disponibile senza effettuare l’accesso

In un sito Experience Builder non connesso, i visitatori non possono accedere a funzionalità o contenuti che richiedono l&#39;autenticazione dell&#39;utente. Non sono in grado di iscriversi ai corsi di formazione, avviare o seguire corsi o accedere a widget personalizzati come Il mio apprendimento, Calendario, Conformità, Classifica o Apprendimento sociale. Questi widget dipendono dai dati specifici dell&#39;utente e sono disponibili solo dopo l&#39;accesso.

Inoltre, i visitatori non possono eseguire azioni quali l’iscrizione a un corso o l’accesso a contenuti che richiedono il tracciamento dell’avanzamento o del contesto dell’utente. Se si tenta di iscriversi o di avviare un corso di formazione, viene richiesto al visitatore di effettuare l’accesso o di registrarsi prima di procedere.

## Widget supportati in modalità senza accesso

In modalità senza accesso, sono supportati solo i widget che non richiedono dati specifici dell’utente. Queste comprendono:

- Widget Categorie, che visualizza le categorie di formazione disponibili.
- Widget di corsi e percorsi, che mostra corsi e percorsi di apprendimento dal catalogo pubblico. 1
- Casella dei contenuti per l&#39;aggiunta di testo statico, immagini o contenuto promozionale.
- widget HTML, per incorporare contenuti HTML personalizzati.
- Widget Iframe, per visualizzare siti, video o strumenti esterni all’interno della pagina.
- I widget che richiedono un contesto utente, ad esempio Il mio apprendimento, Calendario, Conformità, Classifica e Apprendimento sociale, non sono disponibili in modalità di accesso non effettuato.

I widget che richiedono il contesto dell’utente, ad esempio Il mio apprendimento, Calendario, Conformità, Classifica e Apprendimento sociale, non sono disponibili in modalità di accesso non effettuato

## Pagine e menu nell’esperienza senza accesso

- È supportato un solo menu senza accesso, visibile a tutti i visitatori senza autenticazione.
- Le pagine possono essere aggiunte sia ai menu di accesso che a quelli senza accesso; se una pagina è presente in entrambi, i widget e il contenuto vengono adattati in base allo stato di accesso dell’utente.
- I menu che non hanno effettuato l’accesso non dispongono di personalizzazione o definizione dei destinatari. Tutti vedono lo stesso set di pagine.
- I widget che non sono supportati in modalità senza accesso vengono nascosti automaticamente; il layout di pagina viene regolato per riempire gli spazi.
- La gestione di menu e pagine (aggiunta, anteprima, eliminazione) è simile alla modalità di accesso, ma con adeguamenti per i vincoli non di accesso.

## Comportamento di ricerca e catalogo

In modalità senza accesso, gli utenti possono accedere alla pagina del catalogo e utilizzare la ricerca per sfogliare i corsi e i percorsi di apprendimento disponibili. La pagina del catalogo mostra tutti i corsi pubblici, insieme ai filtri e alle funzionalità di ricerca, seguendo le stesse impostazioni dell’account della modalità di accesso. Quando un utente esegue la ricerca, i risultati vengono visualizzati nella pagina del catalogo e gli utenti possono visualizzare le pagine di panoramica del corso e dell’istanza senza effettuare l’accesso. Tuttavia, azioni come l&#39;iscrizione richiedono l&#39;accesso.

Se un utente tenta di effettuare l&#39;iscrizione, il sistema richiede che prima acceda. La ricerca di utenti non connessi è più semplice di quella per gli utenti connessi e non include funzionalità avanzate come l&#39;integrazione di Assistente AI.

## Implementazione tecnica

### Configurazione del connettore di accesso ai dati di formazione

Prima di poter utilizzare la funzione experience builder senza accesso, devi abilitare il connettore di accesso ai dati di formazione nel pannello di amministrazione dell’integrazione. Questo connettore esporta i metadati del corso di formazione da ALM a un repository pubblico, rendendolo accessibile tramite API per le pagine non connesse. La configurazione del connettore è un prerequisito per l&#39;attivazione della funzionalità e garantisce che il portale visualizzi informazioni aggiornate sul corso di formazione.

Esportazione e sincronizzazione dei metadati\
Il connettore esporta i campi di metadati chiave quali nome del corso, panoramica, descrizione, valutazione, durata e abilità. È possibile pianificare le esportazioni (ad esempio, giornalmente) per mantenere il portale sincronizzato con ALM. È possibile che non tutti i campi di metadati siano inclusi. Per un elenco completo, consultare il reparto tecnico. I dati esportati vengono utilizzati per popolare le pagine senza accesso e le modifiche in ALM verranno visualizzate dopo il successivo ciclo di esportazione.

Frequenza di memorizzazione nella cache e di esportazione\
Per gestire gli aggiornamenti dei dati, il sistema utilizza la frequenza di esportazione back-end e la cache front-end. Le modifiche apportate in ALM si riflettono sul portale dopo l&#39;esportazione pianificata e l&#39;aggiornamento della cache. A causa di questi meccanismi, alcuni aggiornamenti potrebbero non essere visualizzati immediatamente. Se hai bisogno di aggiornamenti più rapidi, modifica la pianificazione dell&#39;esportazione o cancella la cache in base alle esigenze.

Supporto della personalizzazione CSS/JS\
È possibile applicare CSS e JavaScript personalizzati sia alle pagine che hanno effettuato l’accesso che a quelle che non l’hanno fatto, utilizzando la scheda personalizzazione. Ciò consente di mantenere un branding coerente, aggiungere elementi dell&#39;interfaccia utente personalizzati e migliorare l&#39;esperienza utente nel portale. Tutte le personalizzazioni vengono applicate a livello globale, garantendo un aspetto unificato.

Differenze e branding degli URL (favicon, titolo pagina)\
Le pagine che non hanno effettuato l’accesso e che vi hanno effettuato l’accesso possono avere URL diversi per distinguere gli stati degli utenti. Puoi personalizzare la favicon e il titolo della pagina per il tuo portale, contribuendo a rafforzare l&#39;identità del tuo marchio. Queste funzioni sono disponibili in Experience Builder; verifica con il team tecnico lo stato più recente del supporto per i dispositivi che non hanno effettuato l&#39;accesso.

## Prestazioni e scalabilità

### Stack condiviso e stack premium

Lo stack condiviso consente a più clienti di utilizzare il generatore di esperienze senza accesso su un&#39;infrastruttura comune, che supporta livelli di traffico standard. Lo stack premium è un&#39;opzione a pagamento che fornisce risorse dedicate, funzionalità in tempo reale e limiti di posti più elevati per i clienti con esigenze avanzate. Scegli lo stack in base ai requisiti di traffico e business previsti.

### Limiti di traffico e limiti di velocità

Lo stack condiviso impone limiti di traffico per garantire un utilizzo corretto tra i clienti. I tecnici implementeranno la limitazione delle tariffe per evitare che un singolo cliente utilizzi tutte le risorse. Se si pianificano campagne di marketing o si prevede un traffico elevato, coordinarsi con la progettazione per comprendere i limiti ed evitare interruzioni del servizio. La limitazione della velocità consente di mantenere la stabilità del sistema e le prestazioni per tutti gli utenti.

Considerazioni su multi-tenancy e SEO\
La piattaforma supporta il multi-tenancy, consentendo a più clienti di ospitare i propri portali su un&#39;infrastruttura condivisa. Le pagine senza accesso sono compatibili con SEO, insieme a sitemap.xml e robots.txt per ottimizzare la visibilità dei motori di ricerca. Ciò garantisce che il portale sia individuabile e indicizzato correttamente dai motori di ricerca.

## Migrazione e rimozione

### Transizione dalla pagina principale esistente senza accesso

La funzione della pagina principale precedente senza accesso sarà obsoleta. I nuovi account non visualizzeranno questa opzione e gli account esistenti che la utilizzano riceveranno una notifica per la migrazione alla soluzione basata su Experience Builder. Dovresti ricreare la tua home page utilizzando il nuovo Experience Builder per una maggiore flessibilità, il supporto del widget e una migliore esperienza utente. Il piano di transizione assicura interruzioni minime e supporto continuo.

Piano di comunicazione\
I clienti che utilizzano la pagina principale precedente riceveranno una comunicazione chiara sulla tempistica della rimozione e sui passaggi di migrazione. Verrà fornito il supporto per consentire di spostare la pagina principale nella nuova piattaforma Experience Builder, in modo da trarre vantaggio dalle nuove funzioni e dagli aggiornamenti in corso.

### Supporto per localizzazione e accesso

Logica di fallback locale\
Il sistema visualizza le pagine nelle impostazioni locali in cui sono state create. Se la lingua di un utente non è disponibile, il sistema utilizza una logica di fallback per selezionare la successiva lingua migliore disponibile. Ciò garantisce agli utenti di visualizzare sempre i contenuti in una lingua supportata, migliorando l&#39;accessibilità e la soddisfazione degli utenti.

Tipi di accesso supportati\
L&#39;esperienza senza accesso supporta tutti i tipi di accesso disponibili in ALM, inclusi SSO e accesso standard. Gli utenti possono sfogliare i contenuti senza accedere e verrà richiesto di accedere quando necessario, ad esempio per iscriversi a un corso o accedere a funzioni personalizzate. Ciò garantisce una transizione fluida dalla navigazione al coinvolgimento.

## API senza accesso

### API oggetto di apprendimento Amministratore

Le pagine Experience Builder e i portali headless non connessi spesso organizzano o filtrano i corsi in base al prodotto e al ruolo. L’API di Admin LO è stata migliorata per garantire che queste associazioni siano sempre accessibili per le integrazioni back-end e headless, nonché per il connettore TDA.

**Endpoint e comportamento**

Continuerai a utilizzare l’endpoint LO di amministrazione esistente:

GET /primeapi/v2/learningObjects/{loId}?enforcedFields[learningObject]=products,roles


Dove:

- loId è l’ID dell’oggetto di apprendimento (ad esempio corso:12345).
- enforcedFields[learningObject] indica all&#39;API di includere in modo esplicito i prodotti e i ruoli per l&#39;oggetto di apprendimento.

A tale scopo, assicurati che le associazioni di prodotto e ruolo degli LO siano presenti nella risposta quando richiesto tramite enforcedFields. La risposta contiene quindi, in attributi, i metadati del prodotto e del ruolo necessari per calcolare o esporre i prodotti (rec_products) e i ruoli (rec_roles) consigliati per Experience Builder e altri consumer.

Una chiamata tipica di un amministratore o di un&#39;integrazione ha un aspetto simile al seguente:

curl -X GET \
  &quot;https://{your-domain}/primeapi/v2/learningObjects/course:12345?enforcedFields[learningObject]=products,roles&quot; \
  -H &quot;Autorizzazione: Portatore {admin_token}&quot; \
  -H &quot;Accetta: application/vnd.api+json&quot;

Il JSON LO restituito ha la stessa struttura di base di prima, ma ora puoi fare affidamento sui campi prodotto/ruolo presenti quando li richiedi con enforcedFields. Le integrazioni che non utilizzano enforcedFields continuano a comportarsi come prima.

### Elenco Oggetti di apprendimento - Supporto JobAid nel filtro effectiveModifiedDate

**Scopo**

Il connettore Accesso ai dati di formazione (TDA) e le implementazioni headless devono spesso eseguire una sincronizzazione incrementale, in base alla **data effettiva di modifica** degli oggetti di apprendimento. Fino a questa versione, le risorse formative (jobAid di tipo LO) non venivano gestite correttamente se combinate con i filtri effectiveModifiedDate. Questa versione corregge questo problema in modo che le risorse formative possano essere sincronizzate in modo incrementale proprio come i corsi e i percorsi di apprendimento.

**Endpoint e comportamento**

L&#39;endpoint dell&#39;elenco di oggetti di apprendimento esistente viene utilizzato con i filtri di data e il tipo di oggetto di apprendimento:

GET /primeapi/v2/learningObjects\
?filter.effectiveModifiedDate.fromDate=2025-03-15T13:14:56.000Z\
&amp;filter.effectiveModifiedDate.toDate=2025-03-20T13:14:56.000Z\
&amp;filter.loTypes=risorsa formativa


In precedenza, quando filter.loTypes=jobAid veniva combinato con un intervallo effectiveModifiedDate, il filtro escludeva effettivamente le risorse formative e la chiamata si comportava come se le risorse formative non fossero supportate.

A partire da questo aggiornamento, la chiamata restituisce solo oggetti di apprendimento JobAid il cui effectiveModifiedDate rientra nella finestra specificata.

```
{  
  "links": {  
    "self": "https://acapapiserver/primeapi/v2/learningObjects?page[limit]=10&filter.effectiveModifiedDate.fromDate=2026-01-19T13:14:56.000Z&filter.effectiveModifiedDate.toDate=2026-01-21T13:14:56.000Z&filter.loTypes=jobAid"  
  },  
  "data": [  
    {  
      "id": "jobAid:144968",  
      "type": "learningObject",  
      "attributes": {  
        "authorNames": ["Sid"],  
        "dateCreated": "2026-01-20T08:48:55.000Z",  
        "datePublished": "2026-01-20T08:48:55.000Z",  
        "dateUpdated": "2026-01-20T08:48:55.000Z",  
        "effectiveModifiedDate": "2026-01-05T07:31:18.000Z",  
        "loType": "jobAid",  
        "loFormat": "Content",  
        "loResourceType": "Content",  
        "localizedMetadata": [  
          {  
            "description": "Link jobAid new",  
            "locale": "en-US",  
            "name": "Link jobAid new"  
          },  
          {  
            "description": "Link jobAid new fre",  
            "locale": "fr-FR",  
            "name": "Link jobAid new fre"  
          }  
        ],  
        "relationships": {  
          "authors": {  
            "data": [  
              { "id": "13385176", "type": "user" }  
            ]  
          },  
          "instances": {  
            "data": [  
              { "id": "jobAid:144891_-1", "type": "learningObjectInstance" }  
            ]  
          }  
        }  
      }  
    }  
  ]  
}
```

Ciò significa che ora è possibile implementare in modo sicuro le sincronizzazioni incrementali delle risorse formative basate su effectiveModifiedDate, come già avviene per altri tipi.

Se si omette filter.loTypes=jobAid, il comportamento degli altri tipi di LO rimane invariato; la modifica interessa solo la combinazione di JobAid con tale filtro.

### **API Menu: filtro menu non connesso**

**Scopo**

Experience Builder e headless front-end necessitano di un modo semplice per recuperare il **menu senza accesso** , quello che definisce la navigazione per i visitatori pubblici. Prima di questa versione, dovevi recuperare tutti i menu e quindi applicare una logica personalizzata per identificare quale rappresentava la navigazione senza accesso. Questa versione aggiunge un semplice filtro lato server.

**Endpoint e comportamento**

Utilizzare l&#39;endpoint di elenco Menu esistente con un nuovo parametro di query:

GET /primeapi/v2/templates/menus?include=pages,subMenus.pages&amp;isNonLoggedIn=true


I punti chiave:

- include=pages,subMenus.pages è facoltativo ma consigliato quando si desidera visualizzare i dettagli della pagina e del sottomenu nella stessa risposta.
- isNonLoggedIn=true è una novità di questa release e indica al server di restituire solo i menu contrassegnati come non connessi.

Senza il parametro isNonLoggedIn, l&#39;endpoint si comporta esattamente come prima e restituisce i menu in base al comportamento predefinito esistente. Con isNonLoggedIn=true, in genere restituisce il singolo menu utilizzato dall&#39;esperienza senza accesso per l&#39;account (poiché normalmente esiste un solo menu senza accesso per account).

In pratica, un cliente può ora emettere:

curl -X GET \
  &quot;https://{your-domain}/primeapi/v2/templates/menus?include=pages,subMenus.pages&amp;isNonLoggedIn=true&quot; \
  -H &quot;Autorizzazione: Portatore {admin_token}&quot; \
  -H &quot;Accetta: application/vnd.api+json&quot;


e ripristina la struttura di navigazione senza accesso con una sola chiamata, con tutte le pagine che dovrebbero essere visibili ai visitatori anonimi.

Ciò è particolarmente utile quando si crea un sito senza intestazione per cui non è stato effettuato l&#39;accesso e si desidera eseguire il mirroring della stessa navigazione utilizzata da Experience Builder o quando si esegue il debug per verificare se il menu senza accesso è stato configurato correttamente.

## Consenti elenco di domini personalizzati

Lo stack non connesso è costituito da:

- Un dominio CDN pubblico (ad esempio cpcontents.adobe.com o yourdomain.example.com) che fornisce layout, codice JSON di configurazione e risorse statiche.
- Endpoint di Elasticsearch pubblico (ES) che serve i dati del catalogo e della ricerca, ma solo se la richiesta proviene da un **dominio elencato consentito** per l&#39;account ALM.

Quando introduci un dominio personalizzato, funziona senza problemi, seguendo il processo esistente per l’aggiunta di un dominio personalizzato.

### Prerequisiti

Prima di autorizzare un dominio personalizzato per gli utenti che non effettuano l’accesso:

1. Il dominio personalizzato è configurato per l&#39;account ALM (ad esempio, DNS per academy.yourcompany.com punta ad Adobe / Akamai e viene eseguito il provisioning dei certificati).
2. Il connettore **Accesso ai dati di formazione** è abilitato per l&#39;account.
3. La funzionalità **Experience Builder** non connesso è abilitata (lato Adobe).

Queste fasi garantiscono che:

- L&#39;account dispone di un **account JSON** non connesso (spesso indicato come accountConfig / experienceBuilderConfig), che include campi come cpDomain, almDomain, almCdnBaseUrl, esBaseUrl e i domini consentiti elencati.
- Lo stack non connesso sa dove fornire i dati e da quali domini deve accettare le richieste.

### Funzionamento di Consenti elenchi

L’elenco degli indirizzi consentiti viene archiviato nella configurazione esportata da TDA e nello stack non connesso. Tale configurazione include:

- I domini ALM (cpDomain, almDomain).
- **URL di base CDN** per il contenuto non connesso (almCdnBaseUrl).
- **URL di base per la ricerca pubblica** (esBaseUrl).
- L’elenco dei domini che possono effettuare chiamate pubbliche senza accesso per quell’account.

Per utilizzare Experience Builder senza accesso in un dominio personalizzato:

- Il browser deve caricare il HTML non connesso da quel dominio personalizzato (o dal dominio CDN ALM non connesso, a seconda della configurazione).
- Le chiamate da tale dominio agli endpoint pubblici ES e CDN devono essere accettate. Ciò accade solo se il dominio è presente nell&#39;elenco degli indirizzi consentiti.

Questa versione aggiunge un nuovo dominio CDN non connesso, cpcontents.adobe.com, e specifica che deve essere inserito nei **domini consentiti** nel connettore TDA. Per gli utenti nativi esistenti non connessi, questo richiede un aggiornamento.

### Elenco Consentiti di un dominio personalizzato

**Configurare il dominio personalizzato in ALM**

Utilizza Adobe per registrare il tuo dominio, ad esempio academy.yourcompany.com, come dominio personalizzato per il tuo account ALM. Aggiornare DNS per puntare ad Adobe Akamai come indicato e attendere il completamento di SSL e routing.

A questo punto, sia il traffico connesso che quello non connesso possono raggiungere ALM attraverso quel dominio, ma le chiamate di ricerca e catalogo non effettuate possono ancora essere bloccate se il dominio non è consentito.

**Abilita TDA e Experience Builder senza accesso**

Assicurati che:

- **Connettore Accesso ai dati di formazione** abilitato.
- La funzionalità **Experience Builder** non connesso è attivata per l&#39;account.

L’abilitazione di TDA crea o aggiorna il codice JSON dell’account non connesso. Per i nuovi account, per impostazione predefinita il processo consente anche l’elenco dei nuovi domini CDN non connessi (cpcontent.adobe.com), pertanto l’endpoint pubblico ES prevede chiamate da tale dominio.

Per gli account che utilizzavano già lo stack precedente non connesso, la specifica M45 richiama l’attenzione sul fatto che i connettori esistenti devono essere eliminati e ricreati per acquisire il nuovo dominio.

**Aggiungere il dominio personalizzato all&#39;elenco degli indirizzi consentiti**

La parte critica sta dicendo allo stack ES non connesso che academy.yourcompany.com è un&#39;origine approvata. Esistono due percorsi comuni.

1. **Riattivare il connettore TDA (semplice, self-service)**

Il wiki Experience Builder M45 spiega che gli utenti nativi esistenti non connessi dovranno eliminare e riattivare la connessione TDA in modo che il nuovo dominio venga automaticamente inserito nell’elenco dei domini consentiti. In questo modo si ottengono due risultati:
1. Il JSON dell’account non connesso viene rigenerato.
2. I domini consentiti vengono aggiornati per includere il nuovo dominio CDN non connesso e il dominio personalizzato.

Questa opzione è consigliata quando si dispone di un numero limitato di account e si può tollerare la disattivazione temporanea e la riattivazione del connettore.

1. **Verificare che il dominio sia effettivamente consentito**

Dopo aver consentito l&#39;inserimento nell&#39;elenco, apri il sito non connesso nel dominio personalizzato e analizza le chiamate di rete del browser.

Desideri visualizzare:

- Richieste a almCdnBaseUrl (ad esempio [https://cpcontent.adobe.com/](https://cpcontent.adobe.com/)...) con 200/304.
- Richieste a esBaseUrl (API di ricerca pubblica, ad esempio [https://primeapps.adobe.com/almsearch/api/v1/](https://primeapps.adobe.com/almsearch/api/v1/)) operazione riuscita, restituzione di JSON con dati di ricerca/catalogo.

Se queste chiamate restituiscono 4xx o errori espliciti che suggeriscono &quot;dominio non attendibile&quot; o &quot;origine non consentita&quot;, l&#39;elenco degli indirizzi consentiti è incompleto o non configurato correttamente e il supporto deve modificarlo.

L’LLD non connesso rileva inoltre che la configurazione dell’account può contenere un valore di dominio previsto. In fase di runtime, il sito verifica che il dominio nell&#39;URL corrisponda a quanto impostato nella configurazione; in caso contrario, l&#39;utente può essere reindirizzato a una pagina di errore. In questo modo è possibile evitare che la configurazione di un cliente sia accessibile tramite il dominio di un altro cliente.

## Utilizzo dei consigli in Experience Builder senza accesso

Experience Builder non connesso consente di creare pagine di apprendimento pubbliche in cui i visitatori possono sfogliare il catalogo e visualizzare i contenuti evidenziati prima di accedere. Anche se questi visitatori sono anonimi, puoi comunque presentare i corsi di formazione consigliati utilizzando metadati e widget.

Nell’app per Allievi che ha effettuato l’accesso, i consigli possono essere personalizzati in base al profilo, alla cronologia, alle abilità e ai progressi dell’Allievo. Nell&#39;esperienza **senza accesso**, l&#39;identità dell&#39;Allievo non è ancora presente, pertanto la piattaforma non può essere personalizzata per utente.

Recommendations in modalità senza accesso:

- **Selezionato o basato su regole**: basato su catalogo, prodotto, ruolo, etichette, tag e altri metadati.
- **Orientamento ai segmenti**: &quot;consigliato agli sviluppatori&quot;, &quot;consigliato ai partner&quot;, &quot;in primo piano per i principianti&quot;.
- **Orientamento al marketing**: utilizzato per attirare e guidare i visitatori a iscriversi una volta effettuato l’accesso.

### Metadati e API che supportano i suggerimenti

Dietro le quinte, le pagine non connesse utilizzano:

- **Connettore TDA** per esportare i metadati degli oggetti di apprendimento (corsi, percorsi, certificazioni, risorse formative) in un indice di ricerca pubblico.
- **stack di ricerca pubblico** per rispondere alle query dei widget non connessi (catalogo, ricerca, corsi e percorsi, categorie).
- L&#39;API **Admin Learning Objects** per esporre i metadati di prodotto e ruolo che possono essere utilizzati per le regole dei suggerimenti.

In questa versione, l’API degli oggetti di apprendimento (API) di amministrazione è stata estesa in modo che le associazioni di prodotti e ruoli siano disponibili in modo affidabile:

GET /primeapi/v2/learningObjects/{loId}?enforcedFields[learningObject]=products,roles

Ciò consente ai widget e alle integrazioni headless di creare consigli basati su regole utilizzando prodotti, ruoli, etichette di catalogo, tag e altri campi in modo coerente.

### Progettazione delle sezioni dei suggerimenti con i widget di Experience Builder

Puoi creare sezioni di suggerimenti su pagine non connesse combinando **widget Experience Builder** con filtri per metadati.

#### **Widget Corsi e percorsi**

Utilizza il widget **Corsi e percorsi** per visualizzare una riga o una griglia di elementi consigliati. Nella configurazione è possibile scegliere:

- Cataloghi da cui estrarre.
- Etichette di catalogo, prodotti, ruoli o tag da utilizzare come filtri.
- Indica se visualizzare corsi, percorsi, certificazioni, risorse formative o una combinazione.
- Ordinamento e numero massimo di elementi.

Ad esempio, potete creare:

- &quot;Consigliato agli sviluppatori&quot;: filtra in base a un prodotto o ruolo utilizzato per il contenuto degli sviluppatori.
- &quot;Inizia qui&quot;: filtra in base a un&#39;etichetta come &quot;Starter&quot; o &quot;Onboarding&quot;.
- &quot;In evidenza questo trimestre&quot;: filtro basato su un&#39;etichetta con limiti di tempo come featureq3-2026.

Il widget non impara dal comportamento, ma mostra tutto ciò che corrisponde alle regole di metadati definite. Dal punto di vista di un visitatore, tuttavia, sembra una striscia di consigli.

#### **Widget Categorie**

Utilizza il widget **Categorie** per consentire ai visitatori di accedere ai set di contenuti &quot;consigliati&quot;, anche se non conoscono i nomi dei prodotti.

Potete configurare porzioni che rappresentano ciascuna un segmento, ad esempio:

- &quot;Per gli amministratori&quot;
- &quot;Per i team di vendita&quot;
- &quot;Per i partner&quot;
- &quot;Per linea di prodotto&quot;

Ogni riquadro può collegarsi a:

- Pagina di un catalogo filtrato, ad esempio il catalogo filtrato in base a determinati prodotti o etichette.
- Una pagina dedicata senza accesso che utilizza corsi e percorsi preconfigurati per quel segmento.

In questo modo si ottiene un&#39;esperienza &quot;percorsi consigliati per segmento&quot; senza personalizzazione.

### Creazione di consigli basati sui segmenti

Poiché i visitatori non connessi non dispongono ancora di un profilo ALM, è utile progettare i suggerimenti **per segmento** e consentire ai visitatori di effettuare la selezione autonomamente.

1. Utilizza una **home page non registrata** che spiega brevemente a chi si rivolge l&#39;Accademia e mostra un piccolo numero di punti di ingresso del segmento (ad esempio, &quot;Sviluppatori&quot;, &quot;Commercianti&quot;, &quot;Partner&quot;, &quot;Nuovi dipendenti&quot;). Questa operazione può essere eseguita con un widget Categorie, una semplice casella Contenuto o una sezione HTML con pulsanti.
2. Per ogni segmento, crea una **pagina dedicata non connessa** in Experience Builder. In questa pagina utilizza uno o più widget di corsi e percorsi configurati con filtri che rappresentano i &quot;suggerimenti&quot; per il gruppo. Ad esempio, per &quot;Sviluppatori&quot; potete filtrare su:
   1. Catalogo = &quot;Formazione pubblica&quot;
   2. Prodotto = &quot;Adobe Experience Manager&quot;
   3. Tags = &quot;Fondamenti per sviluppatori&quot;
3. Utilizzare queste pagine di segmenti come destinazione delle campagne di marketing e come destinazione dei riquadri nella home page del sito non connesso.

I visitatori percepiscono che stanno visualizzando consigli su misura per la loro situazione, anche se la logica è definita in fase di progettazione tramite i metadati.

### Transizione da consigli non connessi a consigli personalizzati

I suggerimenti non connessi riguardano principalmente la **individuabilità** e la **conversione**. Quando i visitatori decidono di iscriversi o iniziare un corso di formazione, accedono e diventano Allievi a tempo pieno con un profilo e una cronologia.

Il flusso abituale è:

1. Un visitatore individua i contenuti attraverso le sezioni dei suggerimenti non registrate (consigli di casa, pagine di destinazione dei segmenti, righe in evidenza).
2. Fai clic su una panoramica del corso o del percorso e scegli di iscriverti o iniziare.
3. ALM richiede di registrarsi o accedere.
4. Dopo l’accesso, l’esperienza Allievo standard che ha effettuato l’accesso subentra, tra cui:
   1. &quot;Il mio apprendimento&quot;
   2. Catalogo connesso con avanzamento personale
   3. Tutti i sistemi di raccomandazione interni utilizzati per gli Allievi esistenti.

In altre parole, i consigli di accesso li aiutano a decidere cosa fare dopo e continuare.

## Come utilizzare le risorse formative nel nuovo Experience Builder non connesso

Nell&#39;**interfaccia utente**, le risorse formative partecipano a esperienze senza accesso principalmente tramite i widget che possono mostrare gli oggetti di apprendimento:

1. **Widget di corsi e percorsi**\
   Questo widget può mostrare più tipi di LO, incluse le risorse formative. Nelle pagine senza accesso, è possibile configurarlo per:
   1. Includere o escludere esplicitamente le risorse formative.
   2. Filtra le risorse formative per catalogo, prodotto, ruolo, etichette, tag e altri metadati.
   3. Presentali insieme a corsi e percorsi o come una striscia &quot;Risorse&quot; separata.

Ad esempio, in una pagina di destinazione pubblica è possibile configurare una striscia denominata &quot;Risorse utili&quot; che mostra solo risorse formative e un’altra striscia denominata &quot;Corsi consigliati&quot; che mostra corsi e percorsi.

1. **Pagina del catalogo e ricerca**\
   Le superfici **catalogo** e **ricerca** non registrate utilizzano l&#39;indice di ricerca pubblico (alimentato dal connettore Accesso ai dati della formazione). L&#39;indice ora supporta correttamente le risorse formative, pertanto:
   1. I risultati della ricerca senza accesso possono includere risorse formative.
   2. Filtri catalogo non registrati (per tipo, prodotto, tag, ecc.) possono includere risorse formative, a condizione che la configurazione dell’account e i widget siano impostati per visualizzarli.
2. **Pagine di panoramica LO**\
   Quando un visitatore fa clic su una risorsa formativa da un qualsiasi widget o dal catalogo, viene visualizzata una **pagina di panoramica dell&#39;LO** per tale risorsa formativa in modalità senza accesso. Da lì, possono leggere la sua descrizione e i metadati. Il download o l’utilizzo effettivo in genere richiede ancora l’accesso, ma la presenza e l’individuazione della risorsa formativa stessa vengono gestite dall’esperienza senza accesso.

### Come visualizzare le risorse formative tramite le API senza accesso

Sul **lato API**, le risorse formative sono supportate da:

1. **Connettore Accesso ai dati di formazione e ricerca pubblica**\
   TDA esporta i metadati della risorsa formativa insieme ad altri tipi di LO nell’indice di ricerca pubblico che serve le query di ricerca e catalogo non registrate. Questo è ciò su cui si basano Experience Builder e i front-end headless.
2. Elenco **Oggetti di apprendimento con effectiveModifiedDate**\
   In questa versione, l’endpoint dell’elenco di oggetti di apprendimento è stato corretto in modo che le risorse formative funzionino correttamente con il filtro effectiveModifiedDate. Ora puoi chiamare:

GET /primeapi/v2/learningObjects\
?filter.effectiveModifiedDate.fromDate=2026-01-19T13:14:56.000Z\
&amp;filter.effectiveModifiedDate.toDate=2026-01-21T13:14:56.000Z\
&amp;filter.loTypes=risorsa formativa


Prima di questa modifica, la combinazione di effectiveModifiedDate con loTypes=jobAid non restituiva le risorse formative in modo affidabile. Ora sì, come documentato nel wiki *M45 Public API Changes*. Ciò significa che:

1. I tuoi lavori TDA o ETL possono **sincronizzare in modo incrementale le risorse formative** per esperienze senza accesso, allo stesso modo dei corsi e dei percorsi.
2. Qualsiasi implementazione headless che crea una directory pubblica della risorsa formativa può eseguire query sulle modifiche in base a effectiveModifiedDate e loType=jobAid.

La risposta di esempio nel documento M45 mostra un learningObject con loType: &quot;jobAid&quot; e loFormat: &quot;Content&quot; restituito quando si utilizza questo pattern.

1. L&#39;**API LO amministratore**\
   Sebbene non specifico per gli oggetti senza accesso, M45 aggiorna anche l’API degli oggetti di apprendimento (LO) di amministrazione per esporre in modo coerente i metadati di prodotto e ruolo per tutti i tipi di oggetti di apprendimento tramite:

GET /primeapi/v2/learningObjects/{loId}?enforcedFields[learningObject]=products,roles


Per le risorse formative, questo significa che puoi gestire centralmente i prodotti, i ruoli, le etichette e i tag e basarti sui metadati in esperienze pubbliche non registrate, ad esempio nelle sezioni &quot;Risorse per gli addetti al marketing&quot; o nelle pagine di destinazione specifiche del prodotto.

**Nota**:

Nello stato senza accesso:

- Le risorse formative sono principalmente **individuabili**: i visitatori possono vedere che esistono, leggere le descrizioni e comprendere come supportano argomenti o corsi.
- Il **consumo** effettivo (download o apertura del contenuto della risorsa formativa) in genere richiede ancora l&#39;accesso, soprattutto se le risorse formative sono considerate parte di contenuto interno o con licenza.

## Modifiche alla &quot;breve descrizione&quot; nella ricerca LO (senza accesso)

Nello stack non connesso, la ricerca e l’elenco degli oggetti di apprendimento (LO) sono basati sul connettore Accesso ai dati di formazione (TDA) e su un indice di Elasticsearch pubblico. In passato, questo stack utilizzava un singolo campo di panoramica/descrizione per ogni LO. I clienti che creavano portali headless senza accesso desideravano mostrare la stessa breve descrizione sui riquadri LO visualizzata nell’interfaccia utente dell’Allievo che aveva effettuato l’accesso, anziché la sola panoramica lunga.

La modifica introduce il supporto per l&#39;LO **breve descrizione** nelle API di ricerca ed elenco non registrate:

- Per **corsi**, la semantica dell&#39;interfaccia utente esistente è:
   - Le schede per l’accesso mostrano una &quot;Breve descrizione&quot; (campo di 140 caratteri), se presente, altrimenti tornano alla lunga &quot;Panoramica dettagliata&quot;.
- Per i **percorsi di apprendimento**, l’interfaccia utente che ha effettuato l’accesso utilizza il campo &quot;Benefici&quot; come descrizione breve, se definita, e torna alla panoramica in caso contrario.
- Per le **certificazioni** viene utilizzata una breve &quot;Descrizione&quot;, con una &quot;Panoramica certificazioni&quot; più lunga come fallback.
- Per **risorse formative**, viene utilizzato il campo di descrizione principale.

## Altre modifiche

### Limitazione per cui due account non possono condividere lo stesso dominio personalizzato

Nelle architetture di Adobe Learning Manager senza accesso e con accesso, un **dominio personalizzato** (ad esempio, academy.example.com) viene considerato come una chiave univoca globale che deve essere mappata esattamente a un account ALM, pertanto la piattaforma applica una restrizione rigida in base alla quale **due account non possono condividere lo stesso dominio personalizzato**. Questo è richiesto per sicurezza, routing e SEO: il livello di routing e lo stack non connesso utilizzano il dominio per cercare la configurazione corretta dell’account (inclusi il relativo account non connesso JSON, i menu Experience Builder, il branding e gli endpoint TDA/di ricerca),

Consentendo lo stesso dominio personalizzato su due account, non sarebbe possibile garantire quali dati dell&#39;account vengono restituiti, potrebbe causare una perdita tra tenant e danneggiare gli artefatti generati come sitemap.xml e robots.txt prodotti per account ma rilevati dai motori di ricerca per host. Dal punto di vista operativo, ciò significa che quando si assegna o si sposta un dominio personalizzato, è necessario prima assicurarsi che non sia associato a nessun altro account (o cancellarlo) e gli strumenti interni di Adobe rifiuteranno i tentativi di associare lo stesso dominio a più account.

### Cache del browser delle risorse nell’esperienza senza accesso

Nell’esperienza senza accesso di Adobe Learning Manager, la memorizzazione delle risorse nella cache dei browser è una parte fondamentale della strategia di prestazioni e scalabilità, poiché le pagine pubbliche devono gestire un traffico di marketing ampio, a volte piccante, con bassa latenza e carico di origine minimo. Risorse statiche e semistatiche come la shell di HTML senza accesso (ad esempio, index.html/guest.html), la configurazione a livello di account JSON (account.json o config.json), il layout di pagina JSON di Experience Builder (menu, layout di widget, impostazioni delle schede), CSS, JS, immagini e favicon vengono forniti da un CDN Akamai (cpcontents.adobe.com / cpcontent.adobe.com) con intestazioni di cache che incoraggiano il riutilizzo sia lato CDN che lato browser, in modo che dopo il caricamento della prima pagina il browser possa eseguire il rendering delle pagine successive senza accesso in gran parte dalla propria cache, riconvalidando solo quando necessario tramite ETag o Ultima modifica.

## Avvia le opzioni della pagina principale

Nella pagina principale di Adobe Learning Manager, seleziona **Branding**. Quindi, nel riquadro a sinistra, seleziona Pagina principale senza accesso.

![opzioni della pagina principale](/help/migrated/administrators/feature-summary/assets/non-logged-in-homepage.png)

*Seleziona la pagina principale senza accesso*

## Aggiungi un banner

Aggiungi un banner per qualsiasi annuncio di marketing o presenta l’argomento di tendenza del giorno. Seleziona **Aggiungi banner**.

![banner](/help/migrated/administrators/feature-summary/assets/add-banner-image.png)

*Aggiungi un banner*

Individua la posizione dell’immagine da utilizzare come banner. Fornisci quindi un collegamento come pulsante di azione sull’immagine del banner.

## Aggiungi categorie

Questo componente può essere utilizzato per filtrare il catalogo in base a tag, abilità e catalogo. Questa sezione contiene un’intestazione e una descrizione per ciascuna categoria. Facendo clic, l’utente viene reindirizzato alla pagina del catalogo con i filtri applicati.

Selezionare **[!UICONTROL Aggiungi categoria]**. Quindi inserisci i dettagli per la categoria.

![aggiungi categoria](/help/migrated/administrators/feature-summary/assets//add-category.png)

*Aggiungere le categorie*

Salva la categoria. La categoria viene aggiunta alla sezione.

## Aggiungi un catalogo

Aggiungi un catalogo per gli utenti che non hanno effettuato l’accesso in modo che possano sfogliare tutti i corsi di formazione sulla piattaforma.

![aggiungi catalogo](/help/migrated/administrators/feature-summary/assets//add-catalog.png)

*Aggiungere un catalogo*

Saranno presenti tutti i corsi di formazione esportati.
