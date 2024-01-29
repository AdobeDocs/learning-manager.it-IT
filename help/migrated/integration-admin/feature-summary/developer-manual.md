---
jcr-language: en_us
title: Manuale per sviluppatori di applicazioni
description: L’API V1 di Learning Manager è ora obsoleta. Le API V1 smetteranno di funzionare dal 28 febbraio 2021. Si consiglia di utilizzare le API V2 per interagire con Learning Manager.
contentowner: jayakarr
source-git-commit: ab6737e8b43222a6538921b0628a504a5f15859d
workflow-type: tm+mt
source-wordcount: '3279'
ht-degree: 0%

---



# Manuale per sviluppatori di applicazioni

L’API V1 di Learning Manager è ora obsoleta. Le API V1 smetteranno di funzionare dal 28 febbraio 2021. Si consiglia di utilizzare le API V2 per interagire con Learning Manager.

## Panoramica {#overview}

[Adobe di Learning Manager](http://www.adobe.com/in/products/learningmanager.html) è una soluzione di gestione dell’apprendimento self-service ospitata nel cloud e incentrata sugli allievi. I clienti possono accedere alle risorse di Learning Manager a livello di programmazione utilizzando l’API di Learning Manager per integrarla con altre applicazioni aziendali. L’API può essere utilizzata anche dai partner Adobi per migliorare la proposta di valore di Learning Manager, estendendone le funzionalità o integrandola con altri servizi o applicazioni.

### Scenario di utilizzo {#usagescenario}

Tramite l’API di Learning Manager, gli sviluppatori possono creare applicazioni autonome che estendono le funzionalità di Learning Manager o integrino Learning Manager con i flussi di lavoro di altre applicazioni aziendali. Puoi sviluppare un&#39;applicazione Web, un client desktop o un&#39;app per dispositivi mobili utilizzando qualsiasi tecnologia a tua scelta. In qualità di sviluppatore, puoi accedere ai dati delle applicazioni da Learning Manager. La distribuzione dell’applicazione sviluppata è esterna alla piattaforma Learning Manager e avrai il pieno controllo sul ciclo di vita dello sviluppo del software man mano che l’applicazione si evolve. In genere, le applicazioni vengono sviluppate da un’organizzazione cliente per l’utilizzo con il proprio account Learning Manager e sono private per quella specifica organizzazione cliente. Inoltre, i partner di Adobe possono creare applicazioni generiche con l’API di Learning Manager, utilizzabili da un’ampia gamma di clienti di Learning Manager.

## API di Learning Manager {#apidescription}

L’API di Learning Manager si basa sui principi di REST ed espone gli elementi chiave del modello a oggetti di Learning Manager agli sviluppatori di applicazioni tramite HTTP. Prima di conoscere i dettagli degli endpoint API e dei metodi HTTP, gli sviluppatori possono acquisire familiarità con i vari oggetti di Learning Manager, i loro attributi e le interrelazioni. Una volta compresi i modelli, sarà utile comprendere la struttura delle richieste e delle risposte API e alcuni termini di programmazione comuni utilizzati genericamente nell’API.

Per informazioni dettagliate sui vari metodi ed endpoint API, consulta  [Documentazione delle API di Learning Manager](https://learningmanager.adobe.com/docs/primeapi/v2/).

## Autenticazione API {#apiauthentication}

Quando scrivi un’applicazione che effettua chiamate API a Learning Manager, devi registrare l’applicazione utilizzando l’app Amministratore di integrazione.

Le API di Learning Manager utilizzano il framework OAuth 2.0 per autenticare e autorizzare le applicazioni client.

**Procedura**

**1. Configurare l’applicazione**

Puoi configurare l’applicazione con ID client e segreto client per utilizzare gli endpoint corretti. Una volta registrata l’applicazione, puoi ottenere clientId e clientSecret. È necessario utilizzare GET URL nel browser in quanto autentica gli utenti di Learning Manager che utilizzano i loro account preconfigurati, ad esempio SSO, Adobe ID e così via.

```
GET https://learningmanager.adobe.com/oauth/o/authorize?client_id=<Enter your clientId>&redirect_uri=<Enter a url to redirect to>&state=<Any String data>&scope=<one or more comma separated scopes>&response_type=CODE.
```

Dopo aver eseguito correttamente l&#39;autenticazione, il browser reindirizza al redirect_uri indicato nell&#39;URL precedente. Un parametro **codice** insieme all&#39;uri di reindirizzamento.

**2. Ottieni token di aggiornamento dal codice**

`POST https://learningmanager.adobe.com/oauth/token Content-Type: application/x-www-form-urlencoded`

Corpo della richiesta post:

```
client_id: 
<enter your clientid>
 & 
 client_secret: 
 <enter your clientsecret>
  & 
  code: 
  <code from step 1></code>
 </enter>
</enter>
```

**3.** **Ottenere un token di accesso dal token di aggiornamento**

URL per ottenere il token di accesso:

POST [https://learningmanager.adobe.com/oauth/token/refresh](https://learningmanager.adobe.com/oauth/token/refresh) Content-Type: application/x-www-form-urlencoded

Corpo della richiesta post:

```
client_id: 
<enter your clientid>
 & 
 client_secret: 
 <enter your clientsecret>
  & 
  refresh_token: 
  <refresh token>
   
  </refresh>
 </enter>
</enter>
```

**URL per verificare i dettagli del token di accesso**

`GET https://learningmanager.adobe.com/oauth/token/check?access_token=<access_token>`

**Limitazione di utilizzo**

Un token di accesso è valido per sette giorni. Dopo un giorno, devi generare un nuovo token di accesso utilizzando il token di aggiornamento. Se generi un nuovo token di accesso da un token di aggiornamento mentre un token di accesso esistente è ancora valido, viene restituito il token esistente.

Alcuni dei termini utilizzati più di frequente nell’API di Learning Manager sono spiegati come riferimento qui di seguito.

**Include**

Gli sviluppatori possono accedere a un singolo modello a oggetti API e a più modelli associati a tale modello. Per accedere ai successivi modelli correlati, è necessario comprendere la relazione di ogni modello con gli altri. **Include** consente agli sviluppatori di accedere ai modelli dipendenti. È possibile utilizzare il separatore di virgole per accedere a più modelli. Per l&#39;utilizzo di esempio e ulteriori dettagli su **include**, fai riferimento alla sezione del modello API di esempio in questa pagina.

**Richiesta API**

Le richieste API possono essere effettuate effettuando una richiesta HTTP. A seconda del punto finale e del metodo, lo sviluppatore può scegliere tra vari verbi HTTP, ad esempio GET, PUT, POST, DELETE, PATCH e così via. Per alcune richieste è possibile passare parametri di query. Quando effettua una richiesta per un modello di dati specifico, l’utente può anche richiedere i modelli correlati come descritto nelle specifiche API JSON. La struttura di una tipica richiesta API è descritta in [esempio di utilizzo del modello](#main-pars_header_1415780624).

**Risposta API**

Quando una richiesta API viene effettuata da un client, viene ottenuto un documento SON in base alla specifica API JSON. La risposta contiene anche il codice di stato HTTP che lo sviluppatore può verificare per eseguire i passaggi successivi appropriati nella logica dell&#39;applicazione. La struttura di una tipica risposta API è descritta in  [esempio di utilizzo del modello](#main-pars_header_1415780624).

**Errori**

Quando una richiesta API ha esito negativo, viene restituita una risposta di errore. Il codice di stato HTTP restituito nella risposta indica la natura dell&#39;errore. I codici di errore sono rappresentati con numeri per ogni modello nel riferimento API. 200, 204, 400 e 404 sono alcuni degli errori più comuni rappresentati nelle API che indicano problemi di accesso HTTP.

**Campi**

Gli attributi dell’oggetto API e le relative relazioni sono denominati collettivamente Fields. Fare riferimento a [API JSON per ulteriori informazioni.](http://jsonapi.org/format/#document-resource-object-fields) Puoi utilizzare Fields come parametro durante le chiamate API per recuperare uno o più attributi specifici dal modello. In assenza del parametro Fields, la chiamata API recupera tutti gli attributi disponibili dal modello. Ad esempio, nella seguente chiamata API, i campi[abilità]=name recupera solo l’attributo name del modello di abilità.

https://learningmanager.adobe.com/primeapi/v2/users/{userId}/userSkills/{id}?include=skillLevel.skill&amp;fields[skill]=name

**Paginazione**

A volte, una richiesta API genera un lungo elenco di oggetti da restituire nella risposta. In tali casi, l’attributo di paginazione consente allo sviluppatore di recuperare i risultati in modo sequenziale in termini di più pagine, in cui ogni pagina contiene un intervallo di record. Ad esempio, l’attributo di paginazione in Learning Manager consente di impostare il numero massimo di record da visualizzare in una pagina. Inoltre, è possibile definire il valore di intervallo dei record da visualizzare nella pagina.

**Ordinamento**

L’ordinamento è consentito nei modelli API. In base al modello, scegliere il tipo di ordinamento da applicare ai risultati. L&#39;ordinamento può essere applicato in ordine crescente o decrescente. Ad esempio, se specificate `code sort=name`, quindi l&#39;ordinamento è crescente in base al nome. Se si specifica `code sort=-name`, è un ordinamento decrescente in base al nome. Fare riferimento a [Specifiche API JSON per ulteriori informazioni](http://jsonapi.org/format/#fetching-sorting).

## Illustrazione di utilizzo delle API {#samplemodel}

Consideriamo uno scenario in cui uno sviluppatore desidera ottenere il nome dell’abilità, il numero massimo di punti assegnati per il livello di abilità e i punti guadagnati dall’Allievo per tale abilità.

Un modello userSkill nelle API di Learning Manager è costituito da id, type, dateAchieved, dateCreated e pointsEarned come attributi predefiniti. Pertanto, quando uno sviluppatore utilizza il metodo GET per acquisire i dettagli del modello userSkill, i dati correnti relativi agli attributi predefiniti vengono visualizzati nell&#39;output della risposta.

Ma, in questo scenario, lo sviluppatore vuole ottenere il nome dell&#39;abilità e i punti di livello di abilità per l&#39;utente. L’API di Learning Manager ti consente di accedere a queste informazioni correlate utilizzando i campi delle relazioni e di includere i parametri. I modelli associati per userSkill si ottengono nel tag relatioships. È possibile ottenere i dettagli di ogni modello associato chiamando questi modelli insieme all&#39;utenteSkill. Per ottenere queste informazioni, utilizzare **`code include`** parametro con valori separati da punto (punto) per ciascuno dei modelli associati. Puoi usare la virgola come separatore per richiedere un altro modello come user include=skillLevel.skill,course

**Chiamata API**

`https://learningmanagerqe1.adobe.com/primeapi/v1/users/%7buserId%7d/userSkills/%7bid%7d?include=skillLevel.skill&fields%5bskill%5d=name&fields%5bskillLevel%5d=maxCredits&fields%5buserSkill%5d=pointsEarned`

Ad esempio, è possibile 746783 userId e userSkills id: 746783_4426_1.

**Risposta della chiamata API**

```
\{ 
 "links": {"self": "https://learningmanager.adobe.com/primeapi/v2/users/746783/userSkills/746783_4426_1?include=skillLevel.skill&fields[userSkill]=pointsEarned&fields[skillLevel]=maxCredits&fields[skill]=name"}, 
 "data": { 
 "id": "746783_4426_1", 
 "type": "userSkill", 
 "attributes": {"pointsEarned": 5}, 
 "links": {"self": "https://learningmanager.adobe.com/primeapi/v2/users/746783/userSkills/746783_4426_1"} 
 }, 
 "included": [ 
 { 
 "id": "4426", 
 "type": "skill", 
 "attributes": {"name": "Java"}, 
 "links": {"self": "https://learningmanager.adobe.com/primeapi/v2/skills/4426"} 
 }, 
 { 
 "id": "4426_1", 
 "type": "skillLevel", 
 "attributes": {"maxCredits": 10} 
 } 
 ] 
} 
```

## Modelli di Learning Manager {#models}

L’API di Learning Manager consente agli sviluppatori di accedere agli oggetti di Learning Manager come risorse RESTful. Ogni endpoint API rappresenta una risorsa, in genere un&#39;istanza di oggetto come Badge o una raccolta di tali oggetti. Gli sviluppatori quindi utilizzano i verbi HTTP come PUT, GET, POST e DELETE per eseguire le operazioni CRUD su tali oggetti (insiemi).

API +++V1

Il diagramma seguente rappresenta i vari elementi del modello a oggetti di Learning Manager nell’API V1.

![](assets/er-diag-primemodels.png)

La tabella seguente descrive vari elementi del modello a oggetti V1 di Learning Manager:

<table border="1" cellspacing="0" cellpadding="0">
 <tbody>
  <tr>
   <td>
    <p><strong>N. di serie</strong></p></td>
   <td>
    <p><strong>Oggetto Learning Manager</strong></p></td>
   <td>
    <p><strong>Descrizione</strong></p></td>
  </tr>
  <tr>
   <td>
    <p>1.      </p></td>
   <td>
    <p>utente</p></td>
   <td>
    <p>Utente è il modello chiave di Learning Manager. Gli utenti sono in genere gli Allievi interni o esterni di un’organizzazione che utilizzano gli oggetti di apprendimento. Tuttavia, possono svolgere altri ruoli, come Autore e Manager, insieme al ruolo di Allievo. L’ID utente, il tipo e l’e-mail sono alcuni degli attributi in linea. </p></td>
  </tr>
  <tr>
   <td>
    <p>2.      </p></td>
   <td>
    <p>corso</p></td>
   <td>
    <p>Il corso è uno degli oggetti di apprendimento supportati in Learning Manager, costituito da uno o più moduli. </p></td>
  </tr>
  <tr>
   <td>
    <p>3.      </p></td>
   <td>
    <p>modulo</p></td>
   <td>
    <p>Il modulo è un elemento fondamentale per creare oggetti di apprendimento in Learning Manager. I moduli possono essere di quattro tipi diversi, ad esempio aula, aula virtuale, attività e ritmo personalizzato. Utilizza questo modello di modulo per ottenere i dettagli di tutti i moduli di un account. </p></td>
  </tr>
  <tr>
   <td>
    <p>4.      </p></td>
   <td>
    <p>certificazione</p></td>
   <td>
    <p>La certificazione viene assegnata agli Allievi in base al completamento dei corsi. Prima di utilizzare le certificazioni, i corsi nell’applicazione sono obbligatori. </p></td>
  </tr>
  <tr>
   <td>
    <p>5.      </p></td>
   <td>
    <p>programma di apprendimento</p></td>
   <td>
    <p>I programmi di apprendimento sono corsi progettati specificatamente per soddisfare specifiche esigenze di apprendimento degli utenti. In genere, i programmi di apprendimento vengono utilizzati per indirizzare gli obiettivi di apprendimento su più corsi individuali. </p></td>
  </tr>
  <tr>
   <td>
    <p>6.      </p></td>
   <td>
    <p>badge</p></td>
   <td>
    <p>Un distintivo è un token che gli Allievi ottengono quando raggiungono dei traguardi specifici durante un corso. </p></td>
  </tr>
  <tr>
   <td>
    <p>7.      </p></td>
   <td>
    <p>abilità</p></td>
   <td>
    <p>Il modello di abilità è costituito da livelli e crediti. Le abilità possono essere acquisite dagli Allievi dopo il completamento del corso. </p></td>
  </tr>
  <tr>
   <td>
    <p>8.      </p></td>
   <td>
    <p>certificationEnrollment</p></td>
   <td>
    <p>Questo modello fornisce i dettagli dell’iscrizione di un utente a una singola certificazione.</p></td>
  </tr>
  <tr>
   <td>
    <p>9.  </p></td>
   <td>
    <p>courseEnrollment</p></td>
   <td>
    <p>Questo modello fornisce i dettagli dell’iscrizione di un utente a un singolo corso. </p></td>
  </tr>
  <tr>
   <td>
    <p>10.  </p></td>
   <td>
    <p>courseInstance</p></td>
   <td>
    <p>A un corso possono essere associate una o più istanze. Puoi ottenere l’istanza del corso </p></td>
  </tr>
  <tr>
   <td>
    <p>11  </p></td>
   <td>
    <p>courseSkill</p></td>
   <td>
    <p>Un modello AbilitàCorso specifica il progresso di una singola abilità ottenuta completando un corso.</p></td>
  </tr>
  <tr>
   <td>
    <p>12  </p></td>
   <td>
    <p>courseModule</p></td>
   <td>Un modello ModuloCorso specifica come viene incluso un modulo in un corso. Ad esempio, se il modulo viene utilizzato per la verifica preliminare o per il contenuto.</td>
  </tr>
  <tr>
   <td>
    <p>13  </p></td>
   <td>learningProgramInstance</td>
   <td>
    <p>Un programma di apprendimento può essere costituito da più istanze con proprietà simili a quelle di un programma di apprendimento o di istanze personalizzate. </p></td>
  </tr>
  <tr>
   <td>
    <p>14  </p></td>
   <td>
    <p>risorsa formativa</p></td>
   <td>
    <p>Le risorse formative sono contenuti didattici accessibili agli Allievi senza alcun requisito di completamento o di iscrizione. Puoi recuperare le informazioni relative a data, stato e ID aggiornate insieme ai modelli correlati, ad esempio la versione della risorsa formativa, gli autori e il livello di abilità. </p></td>
  </tr>
  <tr>
   <td>
    <p>15  </p></td>
   <td>
    <p>jobAidVersion</p></td>
   <td>
    <p>Alla risorsa formativa possono essere associate una o più versioni in base al numero di revisioni del contenuto e al numero di caricamenti. Questo modello fornisce i dettagli di una singola versione della risorsa formativa. </p></td>
  </tr>
  <tr>
   <td>
    <p>16  </p></td>
   <td>
    <p>learningProgramInstanceEnrollment</p></td>
   <td>
    <p>Il programma di apprendimento è costituito da una o più istanze. Gli Allievi possono iscriversi a un’istanza del programma di apprendimento da soli o tramite l’assegnazione dell’Amministratore. Questo modello fornisce i dettagli dell’iscrizione di un utente a una singola istanza del programma di apprendimento. </p></td>
  </tr>
  <tr>
   <td>
    <p>17  </p></td>
   <td>
    <p>moduleVersion</p></td>
   <td>
    <p>Un modulo può avere una o più versioni in base ai caricamenti del contenuto rivisto. Utilizzare questo modello per ottenere informazioni specifiche su qualsiasi versione di un singolo modulo. </p></td>
  </tr>
  <tr>
   <td>
    <p>18.  </p></td>
   <td>
    <p>skillLevel</p></td>
   <td>
    <p>Un livello di abilità comprende uno o più corsi da seguire per acquisire un livello con i relativi crediti associati. </p></td>
  </tr>
  <tr>
   <td>
    <p>19.  </p></td>
   <td>
    <p>userBadge</p></td>
   <td>
    <p>UserBadge mette in relazione un singolo badge con un singolo utente. Contiene dettagli come quando è stato raggiunto, assertionUrl e così via. </p></td>
  </tr>
  <tr>
   <td>
    <p>20.  </p></td>
   <td>
    <p>userSkill</p></td>
   <td>
    <p>L’AbilitàUtente indica quanto di un singolo livello di abilità viene raggiunto da un singolo utente.</p></td>
  </tr>
 </tbody>
</table>

+++

API +++V2

Di seguito sono riportati i vari elementi del diagramma della classe di Learning Manager nell’API V2.

![](assets/v2api-class-diagram.jpg)

<table>
 <tbody>
  <tr>
   <th><b>Oggetto Learning Manager</b></th>
   <th><b>Descrizione</b></th>
  </tr>
  <tr>
   <td>account</td>
   <td>Incapsula i dettagli di un cliente Learning Manager.</td>
  </tr>
  <tr>
   <td><code>
     badge
    </code></td>
   <td>Un distintivo è un token che gli Allievi ottengono quando raggiungono dei traguardi specifici durante un corso. <br></td>
  </tr>
  <tr>
   <td><code>
     catalog
    </code></td>
   <td>Catalogo è una raccolta di oggetti di apprendimento.</td>
  </tr>
  <tr>
   <td><code>
     user
    </code></td>
   <td>Utente è il modello chiave di Learning Manager. Gli utenti sono in genere gli Allievi interni o esterni di un’organizzazione che utilizzano gli oggetti di apprendimento. Tuttavia, possono svolgere altri ruoli, come Autore e Manager, insieme al ruolo di Allievo. L’ID utente, il tipo e l’e-mail sono alcuni degli attributi in linea. </td>
  </tr>
  <tr>
   <td>risorsa</td>
   <td>Questa opzione viene utilizzata per modellare ogni risorsa di contenuto che un modulo cerca di incapsulare. Tutte le risorse incapsulate in <code>
     an
    </code> <code>
     loResource
    </code> sono equivalenti in termini di obiettivo di apprendimento, ma differiscono l’uno dall’altro in termini di tipo di erogazione o impostazioni locali dei contenuti.<br></td>
  </tr>
  <tr>
   <td>userNotification</td>
   <td>Questo modello contiene informazioni di notifica relative a un Allievo.<br></td>
  </tr>
  <tr>
   <td>userSkill</td>
   <td>L’AbilitàUtente indica quanto di un singolo livello di abilità viene raggiunto da un singolo utente.<br></td>
  </tr>
  <tr>
   <td>userBadge</td>
   <td>BadgeUtente fa riferimento a un singolo badge <code>
     with
    </code> un singolo utente. Contiene dettagli come quando è stato raggiunto, <code>
     assertionUrl
    </code> e così via. <br></td>
  </tr>
  <tr>
   <td>abilità</td>
   <td>Il modello di abilità è costituito da livelli e crediti. Le abilità possono essere acquisite dagli Allievi dopo il completamento del corso. <br></td>
  </tr>
  <tr>
   <td>skillLevel</td>
   <td>Un livello di abilità comprende uno o più corsi da seguire per acquisire un livello con i relativi crediti associati. <br></td>
  </tr>
  <tr>
   <td>learningObject</td>
   <td>Un oggetto di apprendimento è un’astrazione per vari tipi di oggetti a cui gli utenti possono iscriversi e da cui possono imparare. Attualmente Learning Manager dispone di quattro tipi di oggetti di apprendimento: Corso, Certificazione, Programma di apprendimento <code>
     and
    </code> Risorsa formativa.<br></td>
  </tr>
  <tr>
   <td>learningObjectInstance<br></td>
   <td>Un’istanza specifica di un oggetto di apprendimento.<br></td>
  </tr>
  <tr>
   <td>learningObjectResource</td>
   <td>Ciò equivale al concetto di <code>
     module
    </code>. Un corso è composto da uno <code>
     of
    </code> altri moduli. In Learning Manager, è possibile distribuire un modulo in vari modi equivalenti. Pertanto, la <code>
     loResource
    </code> racchiude essenzialmente tutte le risorse equivalenti.<br></td>
  </tr>
  <tr>
   <td>loResourceGrade<br></td>
   <td>In questo modo viene incapsulato il risultato del consumo di una risorsa specifica nel contesto di un oggetto di apprendimento a cui è iscritto. Contiene informazioni quali la durata spesa da <code>
     user
    </code> nella risorsa, percentuale di avanzamento dell'utente, stato di superamento/fallimento e punteggio ottenuto dall'utente in qualsiasi quiz associato.<br></td>
  </tr>
  <tr>
   <td>calendario<br></td>
   <td>Un oggetto calendario è un elenco di <code>
     upcoming classroom
    </code> o corsi in aula virtuale a cui l’utente può iscriversi.<br></td>
  </tr>
  <tr>
   <td>l1FeedbackInfo<br></td>
   <td>Il feedback L1 contiene le risposte fornite da un Allievo alle domande di feedback associate agli oggetti di apprendimento. In genere viene raccolto dopo che l’utente ha completato un oggetto di apprendimento se è configurato per raccogliere tali feedback dagli Allievi.<br></td>
  </tr>
  <tr>
   <td>iscrizione<br></td>
   <td>Questa astrazione include i dettagli relativi alla transazione che rappresenta l’assegnazione di un utente specifico a un’istanza specifica dell’oggetto di apprendimento.<br></td>
  </tr>
 </tbody>
</table>

+++

Elenco degli attributi e delle relazioni degli oggetti.

+++account

**Attributi**
dateCreated\
gamificationEnabled\
id\
locale\
loginUrl\
logoUrl\
nome\
sottodominio\
themeData\
timeZoneCode

**Relazioni**
contentLocales(localizationMetadata)\
gamificationLevels(gamificationLevel)\
fusi orari(fuso orario)\
uiLocales(localizationMetadata)

+++

+++badge

**Attributi**
id\
imageUrl\
nome\
stato

+++

+++catalogo

**Attributi**
dateCreated\
dateUpdated\
descrizione\
id\
isDefault\
isInternallySearchable\
isListable\
nome\
stato

+++

+++data

**Attributi**
id\
nomi

+++

+++gamification

**Attributi**
colore\
nome\
punti

+++

+++learningObject

**Attributi**
authorNames\
dateCreated\
datePublished\
dateUpdated\
effectiveIndex\
enrollmentType\
id\
imageUrl\
isExternal\
isSubLoOrderEnforced\
loType\
stato\
tag

**Relazioni**
authors(user)\
enrollment(learningObjectInstanceEnrollment)\
instance(learningObjectInstance)\
prerequisiteLOs(learningObject)\
skill(learningObjectSkill)\
subLO(learningObject)\
additionalLO(learningObject)\
risorsesupplementari(risorsa)

+++

+++learningObjectInstance

**Attributi**
completedDeadline\
dateCreated\
enrollmentCount\
id\
isDefault\
seatLimit\
stato\
validità

**Relazioni**
badge (badge)\
l1FeedbackInfo(feedbackInfo)\
learningObject(learningObject)\
loResources(learningObjectResource)\
localizedMetadata(localizationMetadata)\
subLoInstances(learningObjectInstance)

+++

+++learningObjectInstanceEnrollment

**Attributi**
dateCompleted\
dateEnrolled\
dateStarted\
hasPassed\
id\
progressPercent\
punteggio\
stato

**Relazioni**
allievo(utente)\
learnerBadge(userBadge)\
learningObject(learningObject)\
loInstance(learningObjectInstance)\
loResourceGrades(learningObjectResourceGrade)

+++

+++learningObjectResource

**Attributi**
externalReporting\
id\
loResourceType\
resourceType\
versione

**Relazioni**
learningObject(learningObject)\
loInstance(learningObjectInstance)\
localizedMetadata(localizationMetadata)\
risorse(risorsa)

+++

+++learningObjectResourceGrade

**Attributi**
dateCompleted\
dateStarted\
dateSuccess\
durata\
hasPassed\
id\
progressPercent\
punteggio

**Relazioni**
loResource(learningObjectResource)

+++

+++learningObjectSkill

**Attributi**
crediti\
id\
**Relazioni**
learningObject(learningObject)\
skillLevel(skillLevel)

+++

+++consiglio

**Attributi**
id\
motivo

**Relazioni**
learningObject(learningObject)

+++

+++risorsa

**Attributi**
authorDesiredDuration\
completedDeadline\
contentStructureInfoUrl\
contentType\
contentZipSize\
contentZipUrl\
dateCreated\
dateStart\
wishDuration\
downloadUrl\
extraData\
hasQuiz\
hasToc\
id\
instructorNames\
isDefault\
locale\
posizione\
nome\
onlyQuiz\
reportingInfo\
reportingType\
seatLimit

+++

+++skill

**Attributi**
descrizione\
id\
nome\
stato

**Relazioni**
livelli(skillLevel)

+++

+++skillLevel

**Attributi**
id\
livello\
maxCredits\
nome\
**Relazioni**
badge (badge)\
skill(skill)

+++

+++user

**Attributi**
avatarUrl\
biografia\
contentLocale\
email\
campi\
id\
nome\
pointsEarned\
profilo\
ruoli\
stato\
timeZoneCode\
uiLocale

**Relazioni**
account(account)\
manager(utente)

+++

+++userBadge

**Attributi**
assertionUrl\
dateAchieved\
id\
modelType

**Relazioni**
badge (badge)\
allievo(utente)\
model(learningObject)

+++

+++userCalendar

**Attributi**
corso\
courseType\
dateStart\
iscritto\
id\
mese\
trimestre

**Relazioni**
containerLO(learningObject)\
course(learningObject)

+++

+++userNotification

**Attributi**
actionTaken\
canale\
dateCreated\
id\
messaggio\
modelIds\
modelNames\
modelTypes\
leggi\
ruolo

+++

+++userSkill

**Attributi**
dateAchieved\
dateCreated\
id\
pointsEarned

**Relazioni**
learnerBadge(userBadge)\
learningObject(learningObject)\
skillLevel(skillLevel)\
user(user)

+++

## Processo di sviluppo delle applicazioni {#registration}

## Prerequisiti {#prerequisites}

In qualità di sviluppatore, devi creare un account di prova in Learning Manager, in modo da avere accesso completo a tutti i ruoli all’interno di tale account. Per poter scrivere un’applicazione, uno sviluppatore deve creare alcuni utenti e corsi e portare l’account a uno stato ragionevole, in modo che l’applicazione in fase di sviluppo possa avere accesso ad alcuni dati di esempio.

## Crea ID client e segreto {#createclientidandsecret}

1. Ingresso **Amministratore dell’integrazione** , fare clic su **[!UICONTROL Applicazioni]** nel riquadro sinistro.

   ![](assets/application-development-menu.png)

   *Seleziona applicazioni sull’Amministratore dell’integrazione*

1. Fai clic **[!UICONTROL Registrati]** nell’angolo in alto a destra della pagina per registrare i dettagli dell’applicazione. Viene visualizzata la pagina di registrazione.

   ![](assets/register-application.png)

   *Registra l’applicazione*

   È obbligatorio compilare tutti i campi di questa pagina.

   **Nome applicazione**: immettere il nome dell&#39;applicazione. Non è obbligatorio utilizzare lo stesso nome di applicazione, ma può essere qualsiasi nome valido.

   **URL**: se conosci l’URL esatto in cui si trova l’applicazione, puoi menzionarlo. Se non ne sei a conoscenza, puoi citare l’URL della tua azienda. In questo campo il nome URL valido è obbligatorio.

   **Domini di reindirizzamento**: Immetti il nome di dominio dell’applicazione a cui desideri reindirizzare l’applicazione di Learning Manager dopo l’autenticazione OAuth. Puoi citare più URL qui, ma devi utilizzare URL validi, come `http://google.com`, `http://yahoo.com` e così via.

   **Descrizione:** Immetti una breve descrizione dell’applicazione.

   **Ambiti:** Scegliere una delle quattro opzioni disponibili per definire l&#39;ambito dell&#39;applicazione. In base alla scelta effettuata, gli endpoint API di Learning Manager sono accessibili per l’applicazione. Ad esempio, se hai scelto **Accesso in lettura al ruolo Allievo**, tutti gli endpoint API da Allievo di Learning Manager sono accessibili all’applicazione in sola lettura.

   **Solo per questo account?**\
   **Sì** - se scegli Sì, l’applicazione non sarà visibile ad altri amministratori account.\
   **No** - se scegli No, anche altri amministratori account potranno accedere a questa applicazione, ma dovranno usare l’id dell’applicazione. L’ID applicazione viene generato e visualizzato nella modalità di modifica dell’applicazione di Learning Manager.

   Se si sceglie **Accesso in lettura e scrittura del ruolo di amministratore** come ambito durante la registrazione dell’applicazione e scegliere **Accesso in lettura ruolo amministratore** durante la creazione delle API, puoi comunque disporre dell’accesso in scrittura per l’applicazione, poiché l’ambito di registrazione dell’app sostituisce il flusso di lavoro di autorizzazione.

1. Fai clic **[!UICONTROL Registrati]** nell&#39;angolo in alto a destra dopo aver compilato i dettagli nella pagina di registrazione.

## Sviluppo e test delle applicazioni {#applicationdevelopmentandtesting}

L’API di Learning Manager può essere utilizzata dagli sviluppatori per creare qualsiasi applicazione. Gli sviluppatori devono assicurarsi che i loro account siano composti da alcuni utenti e corsi validi. Possono creare alcuni utenti fittizi e corsi e simulare l’attività nell’account della versione di prova, in modo da testare le funzionalità dell’applicazione.

## Distribuzione dell&#39;applicazione {#applicationdeployment}

Si consiglia all’Amministratore Learning Manager o a un Amministratore di integrazione per l’account di produzione di renderlo disponibile agli utenti dell’organizzazione. Una volta che l’applicazione è stata testata ed è considerata pronta per la produzione, informa l’amministratore dell’account di produzione. Idealmente, gli amministratori desiderano generare un nuovo client-id e client-secret per l’applicazione nell’account di produzione ed eseguire i passaggi necessari per incorporarli nell’applicazione in modo sicuro. La procedura effettiva di distribuzione delle applicazioni varia da azienda a azienda e l’Amministratore Learning Manager della tua organizzazione deve ricevere il supporto del reparto IT/IS per completare la distribuzione.

## Approvazione applicazione esterna {#externalapplicationapproval}

Puoi aggiungere applicazioni esterne facendo clic su **Approva** nell&#39;angolo in alto a destra della **Applicazioni** pagina. Fornisci l’ID applicazione esterna e fai clic su **Risparmia.**

![](assets/add-external-application.png)

*Aggiunta e approvazione di un&#39;applicazione esterna*

## Domande frequenti

+++Learning Manager dispone di un e-commerce integrato?

Adobe Learning Manager non dispone di un e-commerce integrato. Tuttavia, sono disponibili API che consentono di creare un sistema LMS headless personalizzato e di implementare le funzionalità di e-commerce.
+++
