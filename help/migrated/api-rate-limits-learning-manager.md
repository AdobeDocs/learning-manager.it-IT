---
jcr-language: en_us
title: Limiti di velocità delle API in Learning Manager
contentowner: saghosh
preview: true
source-git-commit: 544c695a77c21dd9162b9b943b6119d27aa373dc
workflow-type: tm+mt
source-wordcount: '1757'
ht-degree: 51%

---



# Limiti di velocità delle API in Learning Manager

## Introduzione alla limitazione delle tariffe {#introductiontoratelimiting}

Adobe Learning Manager espone una ricca suite di API REST che aiuta i clienti a creare applicazioni che si integrano con Learning Manager o persino esperienze utente ed estensioni personalizzate ai flussi di lavoro che aiutano la loro azienda.

Ogni volta che viene richiamata un’API, sono disponibili risorse computazionali condivise che vengono utilizzate nei server di Learning Manager. Pertanto, dobbiamo prestare attenzione e cautela per garantire che le applicazioni funzionino correttamente e non compromettano le caratteristiche di prestazioni e disponibilità della piattaforma. A tale scopo, vengono introdotti limiti alle modalità di esecuzione delle chiamate da parte dei client API (frequenza e velocità).

Ad esempio, un’applicazione potrebbe tentare di ottenere tutti gli utenti di tale account e potrebbe effettuare più chiamate API impaginate a una velocità elevata. E per errore, uno sviluppatore potrebbe chiamare questo in un ciclo stretto risultante in un carico enorme sul server e rendendo le applicazioni lente e persino mettendo in pericolo la piattaforma consumando più risorse di quello che è previsto o richiesto.

Per risolvere questo problema, stiamo introducendo limiti di tariffa per quante chiamate API possono essere effettuate da un singolo utente in una specifica applicazione client di un account specifico. Lo misuriamo in termini di richieste al minuto, abbreviate in RPM. Ad esempio, quando il limite per le chiamate API GET è 600 rpm, significa semplicemente che un singolo utente non può superare un massimo di 600 chiamate in un minuto e se l&#39;utente supera tale limite, l&#39;utente otterrà una velocità limitata. Le richieste vengono rilevate con granularità di millisecondi, pertanto questo limite corrisponde a 1 richiesta ogni 100 millisecondi (ms). C&#39;è un altro parametro, chiamato Burst, che è anche definito insieme al limite di velocità, che definisce quante richieste un utente può fare in eccesso rispetto alla velocità specificata (nel nostro caso, 600RPM). Ad esempio, se il parametro Burst è 10, significa che in una coda verranno allocati fino a 10 slot e quando una richiesta arriva &quot;troppo presto&quot; (nel nostro caso, prima di 100 ms), viene elaborata immediatamente se nella coda è disponibile uno slot per essa. Lo slot viene quindi contrassegnato come &quot;occupato&quot; e non viene liberato per l&#39;uso da un&#39;altra richiesta fino a quando non è trascorso il tempo appropriato (nel nostro caso, dopo 100 ms). Il traffico nel mondo reale è generalmente caratterizzato da burst, ed è qui che il parametro Burst è utile. Per la piattaforma Learning Manager, definiamo i limiti per una versione API specifica (ad esempio V2), il ruolo (Allievo/Amministratore) e un verbo (GET/PUT/POST/DELETE/PATCH). Nell&#39;esempio, descrivi sopra diremmo che il limite di tasso è (600, 10).

Sebbene abbiamo sempre avuto limiti di velocità per le API pubbliche in Learning Manager, finora siamo stati piuttosto liberali nel consentire un numero di giri molto elevato. Tuttavia, con la crescita della tua piattaforma di apprendimento preferita, abbiamo assistito a una rapida crescita nell’utilizzo delle nostre API e abbiamo deciso di documentare esplicitamente questi limiti di velocità a beneficio di tutti i nostri clienti e per una migliore gestione della piattaforma. In questo contesto, abbiamo aggiornato le nostre API per iniziare a restituire una nuova risposta API (codice di stato HTTP 429), che non è stata ancora visualizzata. Questa risposta viene fornita ai client API, quando il limite di velocità viene superato. Le applicazioni client dovranno ora gestire questo codice di risposta in modo che si adatti alla logica dell&#39;applicazione; questo documento è principalmente destinato ad aiutare gli sviluppatori a ottenere le informazioni necessarie per incorporare la logica corretta nel loro codice quando visualizzano una risposta di questo tipo.

## Come si confermano i limiti di tariffa applicati? {#howtoconfirmtheenforcedratelimits}

Per ogni richiesta, le intestazioni delle risposte contengono le seguenti informazioni:

```
x-rate-limit: 600r/m 
x-burst: 10
```

* x-rate-limit specifica la soglia della velocità di richiesta di base in termini di richieste al minuto.
* x-burst specifica il numero di richieste in eccesso rispetto alla frequenza di richieste di base accettate per l&#39;elaborazione immediata.

## Come rilevare gli errori causati dai limiti di velocità? {#howtocatcherrorscausedbyratelimits}

Per ogni richiesta, puoi controllare se hai raggiunto il limite di tariffa. Se ricevi un codice di risposta di 429, &quot;{&quot;message&quot;:&quot;429 Troppe richieste&quot;}&quot;, hai raggiunto il limite di velocità.

Si consiglia di includere nello script il codice che rileva le risposte 429. Se lo script ignora l&#39;errore &quot;Troppe richieste&quot; e continua a tentare di effettuare richieste, è possibile che si verifichino errori null. A questo punto, le informazioni sull&#39;errore non saranno utili per diagnosticare il problema.

Ad esempio, una richiesta curl che si scontra con il limite di velocità potrebbe restituire la seguente risposta:

```
< HTTP/2 429 
< date: Wed, 04 Nov 2020 06:53:04 GMT 
< content-type: application/json; charset=utf-8 
< server: openresty 
< x-rate-limit: 60r/m 
< x-burst: 10 
< retry-after: 10.752 
< access-control-allow-credentials: true 
< access-control-allow-methods: GET, POST, OPTIONS, PUT, HEAD, DELETE, PATCH 
< access-control-allow-headers: X-acap-all-roles, X-acap-account,X-acap-user,X-acap-caller-role,Keep-Alive,User-Agent,X-Requested-With,If-Modified-Since,Cache-Control,Content-Type, x-experience-api-version, Authorization, X-CSRF-TOKEN, X-HTTP-Method-Override 
< strict-transport-security: max-age=31536000; includeSubDomains 
< x-frame-options: SAMEORIGIN 
< x-xss-protection: 1 
< x-content-type-options: nosniff 
< x-request-id: gwBBFC9741-58A5-43B1-B1FE-7D14275961E7 
< strict-transport-security: max-age=31536000; includeSubDomains
```

La risposta contiene informazioni sulle seguenti chiavi:

```
status: 429 
retry-after: 10.752
```

Il codice di stato 429 indica &quot;troppe richieste&quot; e che la richiesta corrente non viene elaborata. L’intestazione retry-after specifica che è possibile riprovare la chiamata API in 10,752 secondi. Il codice dovrebbe smettere di effettuare richieste API aggiuntive finché non è trascorso un tempo sufficiente per riprovare.

Lo pseudo-codice seguente mostra un modo semplice per rilevare gli errori di limite di velocità:

```
response = request.get(url) 
if response.status equals 429: 
    alert('Rate limited. Waiting to retry…') 
    wait(response.retry-after) 
    retry(url)
```

In effetti, abbiamo persino creato un&#39;API fittizia Learning Manager che consente di giocare e familiarizzare con la gestione del codice di stato 429.

```
curl -X GET --header 'Accept: application/json' --header 'Authorization: oauth < 
<token>
  >' 'https://learningmanager.adobe.com/learningmanagerapi/v2/dummy 
</token>
```

Questa API fittizia ha un limite di:

```
x-rate-limit: 5r/m 
x-burst: 2
```

Il limite per l’API fittizia è intenzionalmente basso, quindi puoi superare i limiti di velocità molto rapidamente e concentrarti maggiormente sullo sviluppo del codice per rilevare e gestire gli errori relativi ai limiti di velocità.

## Test dell’API fittizia {#testingthedummyapi}

Abbiamo fornito un endpoint per verificare come funziona la limitazione della velocità. A tale scopo è stato creato un endpoint speciale denominato GET /dummy con ambito di lettura dell’Allievo. Questa API è stata intenzionalmente configurata per un limite di velocità molto rigoroso di 5 richieste al minuto, con limite di frammentazione = 2.

Puoi facilmente verificarlo colpendo questo endpoint con velocità inferiori a 5 RPM e superiori a 5 RPM. Scrivi il codice per gestire il codice di stato HTTPS di 429 e in base alle informazioni nelle intestazioni di risposta.

Per semplificare, è possibile consultare questo codice JavaScript di esempio che illustra questo aspetto. Fai clic su questo [violino](https://jsfiddle.net/ACAPJS/9yv8zcmL/) e vedere il codice in azione.

Questa applicazione richiede di fornire un token di applicazione del ruolo Allievo per l’account. Fare riferimento a [Manuale per sviluppatori di applicazioni](https://captivateLearning Manager.adobe.com/docs/Learning Managerapi/v2/) per informazioni sui token API e utilizza la funzionalità Helper token nella sezione delle risorse per sviluppatori dell’applicazione Amministratore di integrazione Learning Manager per generare i token.

Questa applicazione sta effettuando 10 chiamate all’API fittizia in un ciclo continuo. Poiché il limite di velocità è (5, 2) per l’API fittizia; il limite di velocità verrà superato dopo che le prime chiamate 5+2 ricevute da Learning Manager avranno esito positivo e verrà visualizzata una risposta corretta.

Tuttavia, tieni presente che questa applicazione sta cercando il codice di stato 429 in risposta e gestendolo. Quando l’applicazione riceve una risposta di questo tipo, stampa i dettagli nella risposta API, attende il tempo suggerito e tenta di eseguire nuovamente i tentativi non riusciti.

## Best practice per la gestione della limitazione delle tariffe {#bestpracticestohandleratelimiting}

Spesso, i dati di un account non cambiano così spesso. Ad esempio, i corsi di un account potrebbero non cambiare così spesso. Anziché cercare di ottenere tutti i dati ogni volta, è possibile verificare se è possibile ottenere i dati specifici quando sono necessari e valutare l&#39;utilizzo di un meccanismo di cache. In questo modo, quando l&#39;applicazione deve effettuare molte chiamate, si avrà una quota sufficiente entro i limiti di tariffa per effettuare queste chiamate importanti.

Alcuni dati possono cambiare più spesso e potrebbe essere necessario riceverli più spesso. Anche in questo caso, è necessario verificare se l&#39;applicazione può consentire la presenza di dati leggermente obsoleti (che potrebbero trovarsi nella cache, recuperata da N minuti), in quanto potrebbero non avere alcun impatto sul flusso di lavoro dell&#39;utente. Anche se è necessario ottenere nuovi dati dai server, si può essere di nuovo prudenti nel recuperare solo i dati specifici di cui si ha bisogno, invece di ottenere tutto.

Ci saranno anche momenti in cui non si ha scelta di ottenere molti dati perché l&#39;API potrebbe non essere abbastanza flessibile da fornire esattamente ciò che si desidera con una sola chiamata. Verifica se l’API fornisce filtri e criteri di ordinamento che possono essere utilizzati per ridurre al minimo il numero di chiamate; dovresti comunque considerare la memorizzazione nella cache, perché molti utenti nel tuo account potrebbero aver bisogno degli stessi dati.

Quando si ottengono troppi dati nel contesto di un&#39;applicazione interattiva con un&#39;interfaccia utente grafica, è probabile che l&#39;applicazione stia cercando di fare troppo e potrebbe sopraffare l&#39;utente con molte informazioni/funzionalità che influiscono sull&#39;esperienza utente dell&#39;applicazione.

Quando si crea un&#39;applicazione non interattiva (ad esempio un lavoro quotidiano), potrebbe essere necessario recuperare molti dati in blocco. In tali casi, considera l’utilizzo dell’API dei processi, che è progettata principalmente per restituire dati in blocco in formato CSV. Tieni presente che l’API dei processi avrà un vincolo di quota che puoi richiamare N volte al giorno.

Poiché Learning Manager ha implementato le specifiche JSONAPI, alcune API possono anche essere trasferite. In questo modo sarà possibile risparmiare effettuando chiamate API aggiuntive, ma sarà necessario risolvere il problema con un recupero troppo rapido dei dati. Poiché i dati caricati lateralmente a volte possono essere molto grandi, nelle chiamate API impaginate le dimensioni di pagina massime sono limitate a 10; tuttavia, per le chiamate API senza inclusione è possibile specificare dimensioni di pagina maggiori (fino a 100)

Alla fine, se effettui molte richieste API in un breve lasso di tempo, supererai il limite di velocità API per le richieste. Quando raggiungi il limite, Learning Manager interromperà l’elaborazione di qualsiasi altra richiesta fino a quando non sarà trascorso un determinato periodo di tempo.

I limiti di velocità sono descritti nell’ultima sezione di questo articolo. Ti consigliamo di familiarizzare con i limiti.

## Limiti di velocità per gli endpoint API V2 {#ratelimitsforv2apiendpoints}

Nella tabella seguente vengono indicati i limiti per i vari endpoint V2. Attualmente i limiti tariffari non sono imposti ai clienti, ma saranno applicati a partire dal GG/MM/AAAA. Pertanto, diventa importante che i clienti rivedano il codice delle loro applicazioni esistenti per vedere come possono regolare il loro codice per essere consapevoli di questi limiti di velocità e gestire le risposte API con codice di stato HTTP 429.

<table> 
 <tbody>
  <tr> 
   <td><p><b>Funzionamento</b></p></td> 
   <td><p><b>API amministratore</b></p></td> 
   <td><p><b>API Allievo</b></p></td> 
  </tr> 
  <tr> 
   <td><p>DELETE</p></td> 
   <td><p>25, 10 <br></p></td> 
   <td><p>20, 10<br></p></td> 
  </tr> 
  <tr> 
   <td><p>PATCH</p></td> 
   <td><p>(60, 20)</p></td> 
   <td><p>(15, 5) <br></p></td> 
  </tr> 
  <tr> 
   <td><p>POST</p></td> 
   <td><p>30, 10<br></p></td> 
   <td><p>30, 10<br></p></td> 
  </tr> 
  <tr> 
   <td><p>PUT</p></td> 
   <td><p>20, 10<br></p></td> 
   <td><p>20, 10<br></p></td> 
  </tr> 
  <tr> 
   <td><p>GET</p></td> 
   <td><p>(100, 100)<br></p></td> 
   <td><p>100, 30)<br></p></td> 
  </tr> 
 </tbody>
</table>

