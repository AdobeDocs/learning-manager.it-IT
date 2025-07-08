---
jcr-language: en_us
title: Manuale per sviluppatori di applicazioni
description: Scopri come integrare e personalizzare le applicazioni utilizzando le API RESTful, affrontando argomenti essenziali come l’autenticazione OAuth 2.0, gli scenari di utilizzo delle API e i modelli di dati. Migliora le tue applicazioni aziendali con funzionalità come la creazione di corsi, il tracciamento dei progressi degli Allievi, la mappatura delle abilità, la certificazione, la gamification e altro ancora. Questa guida fornisce istruzioni dettagliate ed esempi reali per aiutare gli sviluppatori a creare flussi di lavoro diretti ed efficienti. Ideale per gli sviluppatori che desiderano sfruttare le funzionalità di Adobe Learning Manager per la creazione di applicazioni incentrate sugli Allievi.
contentowner: jayakarr
exl-id: fa9313ac-67de-4467-9253-7eeabcf14204
source-git-commit: 334fb7dcc73e21679d3f95d36456da4e33226773
workflow-type: tm+mt
source-wordcount: '4520'
ht-degree: 5%

---


# Manuale per sviluppatori Adobe Learning Manager

## Panoramica

Adobe Learning Manager fornisce API RESTful che consentono agli sviluppatori di integrare e personalizzare efficacemente applicazioni o flussi di lavoro. Il Manuale per gli sviluppatori offre istruzioni su come utilizzare queste API, coprendo argomenti quali autenticazione, modelli di dati e integrazione con altre applicazioni. Inoltre, questa guida [documentazione di riferimento API](https://learningmanager.adobe.com/docs/primeapi/v2/) aiuta gli sviluppatori a creare applicazioni esterne o flussi di lavoro back-end che interagiscono con varie funzionalità di Adobe Learning Manager, tra cui la creazione di corsi, il monitoraggio dell’avanzamento degli allievi, la mappatura delle abilità, la certificazione, la gamification e le trascrizioni.

Il presente manuale tratta i seguenti argomenti:

* Autenticazione OAuth2.0
* Modelli di oggetti API
* Includi, campi e altri parametri
* Casi d&#39;uso reali

>[!IMPORTANT]
>
>Questo manuale per sviluppatori copre esclusivamente le API V2 di Adobe Learning Manager. Tutti gli esempi, le strutture di richiesta e i flussi di lavoro di autenticazione descritti in questa guida sono specifici degli endpoint /primeapi/v2/. Per informazioni sulle versioni precedenti o sulle API obsolete, consulta la [documentazione di riferimento sulle API](https://learningmanager.adobe.com/docs/primeapi/v2/).

## Scenari di utilizzo delle API

Gli sviluppatori possono utilizzare le API di Learning Manager per migliorare o integrare Learning Manager con altre applicazioni aziendali. Puoi creare app Web, desktop o per dispositivi mobili utilizzando qualsiasi tecnologia. Gli sviluppatori possono accedere ai dati di Learning Manager, ma puoi controllare dove e come viene utilizzata l’app.

## Autenticazione tramite OAuth 2.0

Per accedere in modo sicuro alle API di Adobe Learning Manager, è necessario autenticarsi utilizzando il meccanismo OAuth 2.0 di Adobe Learning Manager. Questo processo include la registrazione dell’applicazione, la generazione di un codice di autorizzazione, lo scambio con un token di aggiornamento e, infine, l’utilizzo del token di aggiornamento per ottenere un token di accesso.

### Registra un&#39;applicazione

Integrazione di Adobe Learning Manager con applicazioni esterne per una maggiore versatilità. I passaggi prevedono l’accesso all’interfaccia di Amministratore di integrazione, la registrazione dell’applicazione e l’ottenimento di ID client e Segreto. Genera token di autenticazione OAuth 2.0 da Adobe Learning Manager, inclusi token di autorizzazione, aggiornamento e accesso. Utilizza il flusso OAuth 2.0 per autenticare e autorizzare in modo sicuro l’app. Il token di accesso ha una validità di sette giorni.

1. Accedi a Adobe Learning Manager come amministratore di integrazione.
2. Seleziona **[!UICONTROL Applicazioni]** nel riquadro a sinistra.

   ![testo alternativo](assets/application.png)

3. Seleziona **[!UICONTROL Registra]** e aggiungi le seguenti informazioni:

   * **[!UICONTROL Nome applicazione]**: digita il nome dell&#39;applicazione (massimo 50 caratteri).
   * **[!UICONTROL URL]**: URL ufficiale dell&#39;azienda o dell&#39;applicazione. Utilizzato per l&#39;identificazione e il riferimento.
   * **[!UICONTROL Domini di reindirizzamento]**: specifica i domini (ad esempio, [http://learningmanager.adobe.com](http://learningmanager.adobe.com)) a cui Adobe Learning Manager può reindirizzare dopo l&#39;autorizzazione.  È possibile specificare più URL validi.
   * **[!UICONTROL Descrizione]**: breve descrizione delle operazioni eseguite dall&#39;applicazione.
   * **[!UICONTROL Ambiti]**: selezionare una delle sei opzioni disponibili per definire l&#39;ambito dell&#39;applicazione. In base alla scelta indicata qui, gli endpoint API di Learning Manager sono accessibili per l’applicazione. Ad esempio, se scegli l’accesso in lettura al ruolo di Allievo, tutti gli endpoint API da Allievo di Learning Manager sono accessibili all’applicazione in sola lettura.

      * Accesso in lettura/scrittura al ruolo di amministratore: consente all’applicazione di accedere o modificare i dati come amministratore.
      * Accesso in lettura/scrittura al ruolo Allievo: consente all’applicazione di accedere o modificare i dati per gli Allievi.
      * Accesso in lettura/scrittura xAPI: consente all’applicazione di accedere e inviare istruzioni Experience API (xAPI).

   * **[!UICONTROL Solo per questo account?]**

      * **[!UICONTROL Sì]**: se scegli Sì, l’applicazione non sarà visibile ad altri amministratori account.
      * **[!UICONTROL No]** - se scegli No, anche altri amministratori account potranno accedere a questa applicazione, ma dovranno usare l&#39;ID dell&#39;applicazione. L’ID applicazione viene generato e visualizzato nella modalità di modifica dell’applicazione di Learning Manager.

     ![testo alternativo](assets/register-an-app.png)

4. Selezionare **[!UICONTROL Salva]** per registrare l&#39;applicazione.

   * Dopo aver registrato l’applicazione, questa diventa disponibile nell’elenco delle applicazioni create nell’account. Seleziona l&#39;applicazione e oltre ai campi immessi in precedenza verranno visualizzati i seguenti elementi:
   * ID applicazione: ID client. Questo ID indica a Adobe Learning Manager l’applicazione che richiede l’accesso. È incluso nelle richieste API per identificare l’app.
   * Segreto dell’applicazione: viene utilizzato per autenticare l’app e verificarne l’identità durante i passaggi di scambio dei token (ad esempio, quando si richiede un token di aggiornamento o di accesso).

   ![](assets/application-id-and-secret.png)

## Ottenere un token di accesso

### Ottenere il codice di autorizzazione

Dopo aver ottenuto l’ID client e il segreto client, utilizzali per richiedere un token di accesso utilizzato per autenticare le chiamate API.

Per avviare il flusso del codice di autorizzazione, aggiungi il seguente URL in un browser:

```
GET https://learningmanager.adobe.com/oauth/o/authorize?client_id=<Enter your clientId>&redirect_uri=<Enter a url to redirect to>&state=<Any String data>&scope=<one or more comma separated scopes>&response_type=CODE 
```

Dopo che l&#39;utente ha autorizzato l&#39;applicazione, Adobe Learning Manager reindirizzerà all&#39;URI_reindirizzamento specificato con un parametro di query accodato:

[https://yourapp.com/callback?code=abc123xyz](https://yourapp.com/callback?code=abc123xyz)

Insieme all&#39;URI di reindirizzamento viene aggiunto un codice di parametro.

### Ottieni token di aggiornamento dal codice

Dopo aver ottenuto il codice, utilizza uno strumento API e aggiungi la seguente richiesta POST:

```https://learningmanager.adobe.com/oauth/token ```

**Corpo della richiesta (x-www-form-urlencoded)**:

```
grant_type=authorization_code  
&code=abc123xyz  
&client_id=<your_client_id>  
&client_secret=<your_client_secret>  
&redirect_uri=<your_redirect_url> 
```

**Risposta**

```
{ 

  "access_token": "eyJhbGciOiJIUzI1...", 
  "refresh_token": "xTjlfz0jCk6gF1...", 
  "expires_in": 604800, 
  "token_type": "Bearer" 

} 
```

Per effettuare richieste API autenticate, utilizza access_token nell’intestazione Autorizzazione.

### Utilizzare il token di accesso in una chiamata API

Verifica il token di accesso utilizzando quanto segue:

```
GET https://learningmanager.adobe.com/oauth/token/check?access_token=<access_token> 
```

Un token di accesso è valido per sette giorni. Dopo sette giorni, è necessario generare un nuovo token di accesso utilizzando il token di aggiornamento. Se generi un nuovo token di accesso dal token di aggiornamento mentre un token di accesso esistente è ancora valido, verrà restituito il token esistente.

### Ottieni token di accesso per test e sviluppo

Quando si utilizzano le API di Adobe Learning Manager, gli sviluppatori devono disporre di un token di accesso OAuth 2.0 valido per autenticare le richieste API. La generazione di questo token tramite il flusso OAuth standard può essere complessa e richiedere molto tempo, in particolare per test rapidi, apprendimento o sviluppo. Adobe Learning Manager fornisce uno strumento di generazione di token per semplificare questo processo.

Questo strumento è ideale durante:

* Build POC (Proof of concept)

* Sviluppo nelle fasi iniziali

* Risoluzione dei problemi di integrazione API

Questi token sono destinati esclusivamente all&#39;uso personale durante le fasi di sviluppo e debug. Tieni presente che i token di prova consentono l&#39;accesso ai dati Adobe Learning Manager, quindi è essenziale gestirli in modo sicuro. Non condividere mai i token di prova con altri utenti, non utilizzarli nelle applicazioni di produzione e non includerli in archivi di codice pubblici. Trattali come password per garantire la sicurezza dell’account e dei dati.

1. Accedi a Adobe Learning Manager come Amministratore dell’integrazione.
2. Selezionare **[!UICONTROL Risorse sviluppatore]**, quindi **[!UICONTROL Seleziona token di accesso per test e sviluppo]**.

   ![](assets/select-access-token.png)

3. Digita l&#39;**[!UICONTROL ID client]** ottenuto dopo aver creato un&#39;applicazione per ottenere il codice OAuth. Quindi seleziona **[!UICONTROL Invia]**.

   ![](assets/type-client-id.png)

4. Aggiungi **[!UICONTROL ID client]** e **[!UICONTROL Segreto client]** per ottenere il token di aggiornamento. Quindi seleziona **[!UICONTROL Invia]**. OAuth viene precompilato dal passaggio precedente.

   ![](assets/get-refresh-token.png)

5. Aggiungi l’ID client e il segreto client per ottenere il token di accesso. Quindi seleziona **[!UICONTROL Invia]**.

   ![](assets/get-access-token.png)

6. Aggiungi il token di accesso e seleziona Invia per ottenere i relativi dettagli.

   ![](assets/type-access-token.png)

Dopo aver selezionato **[!UICONTROL Invia]**, il token di accesso viene verificato e riceverai il seguente oggetto JSON:

```
{ 
  "access_token": "access token", 
  "refresh_token": "refresh token", 
  "user_role": "admin", 
  "account_id": "1234", 
  "user_id": "123456", 
  "expires_in": 604800 
} 
```

Come in precedenza, il token di accesso per il test scade tra sette giorni.

### Utilizza uno strumento API per testare gli endpoint

Sebbene sia possibile utilizzare qualsiasi strumento di testing API di terze parti, utilizzeremo Postman per testare gli endpoint. Negli esempi riportati in questo documento viene utilizzato Postman per il test degli endpoint.

1. Apri Postman e crea una nuova richiesta.
2. Seleziona la scheda Autorizzazione.
3. Imposta Tipo di autenticazione su Bearer Token.

   ![](assets/developer-manual-1.png)
4. Incolla nel campo Token il token di accesso ottenuto dalla sezione precedente.

   ![](assets/developer-manual-2.png)

5. Aggiungere quanto segue nella scheda Intestazioni.

   * Chiave: Accetta
   * Valore: application/json
6. Immetti l’endpoint API nel campo URL. Esempio: [https://learningmanager.adobe.com/learningManager/api/v2/users](https://learningmanager.adobe.com/learningManager/api/v2/users)
Per ulteriori informazioni, consulta la [Guida di riferimento all’API di Adobe Learning Manager](https://learningmanager.adobe.com/docs/primeapi/v2/).
7. Seleziona Invia per effettuare la richiesta API.

## Tipi di API

### API per amministratori

Le API di amministrazione di Adobe Learning Manager consentono agli amministratori di automatizzare e gestire le operazioni di apprendimento su larga scala.

Utilizzando le API di amministrazione, gli sviluppatori possono:

>[!NOTE]
>
>L&#39;elenco non è esaustivo.

* **Gestione di utenti e gruppi**: creazione, aggiornamento ed eliminazione di utenti o assegnazione di utenti a gruppi.
* **Iscrizione degli Allievi**: iscrizione automatica a corsi, percorsi di apprendimento o certificazioni.
* **Monitoraggio dell’avanzamento dell’Allievo**: recupero dello stato di avanzamento del corso/modulo, dei punteggi del quiz e dello stato di completamento.
* **Generazione di report**: accesso ai dati su attività, coinvolgimento e prestazioni degli Allievi.
* **Gestione contenuto**: creazione e organizzazione di corsi e oggetti di apprendimento.

Per ulteriori informazioni, vedere [Adobe Learning Manager API Reference](https://learningmanager.adobe.com/docs/primeapi/v2/).

### API Allievo

Le API per Allievi sono progettate per gli utenti autenticati (Allievi) e consentono di accedere a informazioni specifiche per gli Allievi. Queste API consentono attività quali:

* Accesso ai corsi e all’avanzamento di un Allievo
* Recupero di distintivi o certificazioni ottenuti
* Aggiornamento delle informazioni del profilo Allievo
* Visualizzazione delle abilità associate ai corsi completati

**Punti chiave:**

* Queste API richiedono un token utente autenticato, che garantisce la sicurezza e la privacy dei dati.
* Le API sono pensate per scenari in cui gli utenti sono completamente registrati e connessi, piuttosto che utenti anonimi o condivisi.

Per ulteriori informazioni, vedere [Adobe Learning Manager API Reference](https://learningmanager.adobe.com/docs/primeapi/v2/).

## Progettazione API e parametri comuni

Le API forniscono agli sviluppatori l’accesso alle risorse chiave di Learning Manager, come utenti, corsi, abilità, certificazioni e programmi di apprendimento. Seguono i principi REST, utilizzando i metodi HTTP (GET, POST, PUT, DELETE) per le operazioni sui dati.

| | |
|--|--|
| Metodi | GET, PUT, POST, DELETE |
| Formato | application/vnd.api+json, applicazione/json. [Ulteriori informazioni](https://developer.mozilla.org/en-US/docs/Web/HTTP/Guides/MIME_types/Common_types) sui tipi MIME comuni. |
| URL di base | [https://learningmanager.adobe.com/primeapi/v2/](https://learningmanager.adobe.com/primeapi/v2/) |

### Parametri comuni

| Parametri | Scopo |
|--|--|
| includere | Ottieni le risorse correlate in una chiamata. |
| campi | Seleziona attributi specifici per ridurre il payload. |
| filtro | Risultati stretti (ad esempio, per ID, nome) |
| ordinamento | Ordinare i risultati. |
| page[limit], page[offset] | Supporto di paginazione. |

Ecco una breve spiegazione di ciascuno:

### includere

Le API Adobe Learning Manager possono essere utilizzate per recuperare informazioni utili durante la creazione di un’applicazione personalizzata o di un LMS headless. Gli endpoint API possono inoltre essere inclusi con parametri aggiuntivi di tipo &quot;include&quot; per recuperare le informazioni aggiuntive correlate ai dati ricevuti per impostazione predefinita. Queste relazioni sono relazioni del modello di dati, ad esempio durante una chiamata per ottenere i dettagli dell&#39;utente, riceverai le informazioni sull&#39;utente e la relazione dell&#39;ID manager e dell&#39;ID account Adobe Learning Manager. Con il parametro include, puoi estrarre in modo dettagliato altri dettagli insieme a quelli dell’utente, come i dettagli del manager e dell’account Adobe Learning Manager.
In breve, il parametro **include** viene utilizzato nelle chiamate API per recuperare le risorse correlate (collegate) insieme alla risorsa primaria in un&#39;unica risposta. È utile quando desideri accedere a dati nidificati o dipendenti, come i moduli di un corso o le abilità mappate a un Allievo, senza effettuare chiamate API separate.

Vantaggi principali:

* Riduce più chiamate API: evita di richiedere manualmente ogni risorsa correlata.
* Maggiore efficienza: sviluppo più rapido, minore carico del server e rendering più rapido dei dati.
* Assicura la coerenza dei dati: recupera tutti i dati correlati in uno snapshot coerente.

**Come utilizzare il parametro include**

Aggiungi il parametro include all’URL API e specifica le entità correlate da includere.

**Percorsi di inclusione comuni**

| Includi valore | Descrizione |
|---|---|
| istanze | Restituisce tutte le istanze dell’oggetto di apprendimento |
| enrollment | Restituisce i dettagli dell&#39;iscrizione per l&#39;utente |
| instances.loResources.resources | Recupera moduli e risorse all’interno di un’istanza |
| risorsesupplementari | Restituisce risorse supplementari associate |
| skills.skillLevel.badge | Recupera i livelli di abilità e i badge associati |
| prerequisiteLOs | Include i prerequisiti per gli oggetti di apprendimento |
| subLO | Recupera oggetti di apprendimento secondario (utilizzati in LP o certificazioni) |
| subLOs.enrollment | Iscrizione a oggetti di apprendimento secondari |
| instances.badge | Badge assegnato per il completamento di un’istanza del corso |
| subLOs.subLOs.instances.loResources.resources | Risorse nidificate in profondità all&#39;interno di un&#39;istanza sub-LO |

**Esempio 1**

Recuperare i dettagli di un utente utilizzando il parametro userID nell&#39;endpoint.

```
https://learningmanager.adobe.com/primeapi/v2/users/<userID>
```

```
GET https://learningmanager.adobe.com/primeapi/v2/users/<userID>
```

Nella risposta, è possibile notare che l&#39;oggetto dati ha una relazione con l&#39;account e il manager dell&#39;utente.

```
"relationships": {
            "account": {
                "data": {
                    "id": "1010",
                    "type": "account"
                }
            },
            "manager": {
                "data": {
                    "id": "3400476",
                    "type": "user"
                }
            }
        }
```

Utilizzando il parametro include nella richiesta, è possibile recuperare informazioni dettagliate sul manager, come illustrato di seguito:

```
GET https://learningmanager.adobe.com/primeapi/v2/users/<userid>?include=manager
```

**Esempio 2**

Per recuperare i dettagli del corso, utilizza il parametro include nella chiamata all’endpoint. L’endpoint seguente ottiene le informazioni sul corso e le relative relazioni.

```
GET https://learningmanager.adobe.com/primeapi/v2/learningObjects/<courseID>
```

Le relazioni vengono visualizzate nella risposta nel modo seguente:

* istanze
* abilità
* autori

```
"relationships": {
            "authors": {
                "data": [
                    {
                        "id": "3400468",
                        "type": "user"
                    }
                ]
            },
            "instances": {
                "data": [
                    {
                        "id": "course:16444_31598",
                        "type": "learningObjectInstance"
                    }
                ]
            },
            "skills": {
                "data": [
                    {
                        "id": "course:16444_1796",
                        "type": "learningObjectSkill"
                    },
                    {
                        "id": "course:16444_3103",
                        "type": "learningObjectSkill"
                    }
                ]
            }
        }
```

Altre relazioni potrebbero includere (non presente nella risposta precedente):

* prerequisiteLOs
* oggetti di apprendimento supplementari
* risorsesupplementari

Per ottenere dati dettagliati sulle istanze e sulle abilità, includere &quot;instance,skills&quot; nel parametro include.

```
GET https://learningmanager.adobe.com/primeapi/v2/learningObjects/<courseID>?include=instances,skills
```

Ora, ad esempio, se desideri recuperare più dati associati all’istanza del corso, come loResources (informazioni sul modulo del corso), applica loResources come inclusione nidificata.

```
GET https://learningmanager.adobe.com/primeapi/v2/learningObjects/<courseID>?include=instances.loResources
```

Inoltre, combina abilità e istanze con un include nidificato.

```
GET https://learningmanager.adobe.com/primeapi/v2/learningObjects/<courseID>?include=instances,instances.loResources,skills
```

**Altri filtri di inclusione**

<table>
  <tbody>
  <tr>
   <td>
    <p style="text-align: left;"><b>Programmi di apprendimento</b></p></td>
   <td>
    <p style="text-align: left;"><b>Corso</b></p></td>
  </tr>
  <tr>
  <td><br>subLOs.prerequisiteLOs.enrollment</br><br>subLOs.subLOs.prerequisiteLOs.enrollment</br><br>subLOs.enrollment.loResourceGrades</br><br>subLOs.subLOs.enrollment.loResourceGrades</br><br>subLOs.subLOs.instances.loResources.resources.room</br><br>subLOs.instances.loResources.resources.room</br><br>subLOs.supplementaryResources</br><br>subLOs.enrollment</br><br>SubLOs.enrollment.loInstance.loResources.resources</br><br>subLOs.supplementaryLOs.instances.loResources.resources</br>
  </td>
  <td>
  <br>instance.enrollment.loResourceGrades</br><br>enrollment.loInstance.loResources.resources</br>prerequisiteLOs</br><br>authors</br><br>instance.loResources.resources</br><br>additionalLOs.instance.loResources.resources</br><br>additionalResources</br><br>instance.badge</br><br>skills.skillLevel.badge</br><br>skills.skillLevel.skill</br><br>instance.loResources.resources.room</br><br>prerequisiteLOs.enrollment</br><br>enrollment.loResourceGrades 3}</br>
  </td>
  </tr>
  </table>

#### campi

Gli attributi e le relazioni di un oggetto API sono denominati Campi. Utilizza Fields come parametro nelle chiamate API per recuperare attributi specifici dal modello. Senza il parametro Fields, la chiamata API recupera tutti gli attributi disponibili.

Ad esempio, nella seguente chiamata API, fields[skill]=name recupera solo l’attributo name del modello di abilità.

```
GET https://learningmanager.adobe.com/primeapi/v2/users/3400490/userSkills/3400490_1796_1?include=skillLevel.skill&fields[skill]=name
```

#### impaginazione

La paginazione API è una tecnica utilizzata nelle API per scomporre grandi insiemi di dati in blocchi più piccoli e gestibili, chiamati pagine, anziché restituire l’intero dato in un’unica risposta.

La paginazione riduce il carico del client e del server, limita le dimensioni della risposta per evitare colli di bottiglia del server o è utile per visualizzare i dati in tabelle o elenchi una pagina alla volta.

**Funzionamento della paginazione nelle API di Adobe Learning Manager**

Le API di Adobe Learning Manager supportano la paginazione tramite parametri quali:

* page[limit]: numero di record per pagina.
* page[offset]: numero di record da ignorare.
* page[cursor]: puntatore al set di risultati successivo. Invece di utilizzare la paginazione basata su offset (che ignora un certo numero di record), la paginazione basata su cursore utilizza un marcatore univoco restituito dall’API per recuperare la pagina successiva di risultati.

Di seguito è illustrato come utilizzare la paginazione nelle API:

**pagina[limite]**

Mentre [https://learningmanager.adobe.com/primeapi/v2/users](https://learningmanager.adobe.com/primeapi/v2/users) restituisce tutti gli utenti e le informazioni correlate in una singola chiamata, l&#39;utilizzo di page[limit] limita il numero di risultati al valore specificato.

Per restituire solo cinque record utente in una singola chiamata, utilizza la seguente API:

```
GET https://learningmanager.adobe.com/primeapi/v2/users?page[limit]=5
```

**pagina[offset]**

Utilizzare questa chiamata API per restituire tre record utente, ignorare i primi cinque utenti e iniziare dal sesto.

```
GET https://learningmanager.adobe.com/primeapi/v2/users?page[limit]=3&page[offset]=5 
```

**pagina[cursore]**

1. Inizia richiedendo la prima pagina con un limite di 5.

   ```
   GET https://learningmanager.adobe.com/primeapi/v2/users?page[limit]=5
   ```

2. Copiare il valore del cursore da links.next e utilizzarlo nella richiesta successiva:

   ```
   "links": {
       "self": "https://learningmanager.adobe.com/primeapi/v2/users?page[limit]=5",
       "next": "https://learningmanager.adobe.com/primeapi/v2/users?page[limit]=5&page[cursor]=3400482"
    }
   ```

3. Invia la seguente richiesta:

   ```
   GET https://learningmanager.adobe.com/primeapi/v2/users?page[limit]=5&page[cursor]=3400482
   ```

In questo modo viene restituito il set successivo di 10 record, a partire dall&#39;ultimo elemento della pagina precedente.

#### filtro

Il parametro filter consente di restringere i risultati API in base a uno o più valori di campo.

Le API Adobe Learning Manager forniscono diverse varianti del parametro di filtro per restringere le risposte.

Per ulteriori informazioni, vedere [Adobe Learning Manager API Reference](https://learningmanager.adobe.com/docs/primeapi/v2/).

In questo esempio viene illustrato come filtrare le risorse formative a cui un Allievo si è iscritto utilizzando l’endpoint con il parametro filter:

```
GET https://learningmanager.adobe.com/primeapi/v2/users/3400480/enrollments?filter.loTypes=jobAid
```

#### ordinamento

Il parametro sort viene utilizzato per ordinare i risultati API in ordine crescente o decrescente in base a uno o più campi.

Adobe Learning Manager fornisce varie opzioni di ordinamento per ordinare la risposta API. Per ulteriori informazioni, vedere [Adobe Learning Manager API Reference](https://learningmanager.adobe.com/docs/primeapi/v2/).

Estendendo l’esempio precedente, ora ordinerai l’iscrizione dell’utente ai programmi di apprendimento in base alla data di iscrizione in ordine crescente.

```
GET https://learningmanager.adobe.com/primeapi/v2/users/3400480/enrollments?filter.lotypes=learningProgram&sort=dateEnrolled
```

## Panoramica dei modelli API

Le API di Adobe Learning Manager consentono agli sviluppatori di accedere agli oggetti di Learning Manager come risorse RESTful. Ogni endpoint API rappresenta una risorsa, in genere un’istanza di oggetto come un Badge o una raccolta di tali oggetti. Gli sviluppatori quindi utilizzano verbi HTTP come PUT, GET, POST e DELETE per eseguire le operazioni CRUD su tali oggetti (insiemi).

![](assets/api-flow.png)

| Oggetto di Learning Manager | Descrizione |
|----|----|
| account | Incapsula i dettagli di un cliente Learning Manager. |
| badge | Un distintivo è un token che gli Allievi ottengono quando raggiungono traguardi specifici durante un corso. |
| catalogo | Catalogo è una raccolta di oggetti di apprendimento. |
| all’interfaccia  | Utente è il modello chiave di Learning Manager. Gli utenti sono in genere gli Allievi interni o esterni di un’organizzazione che utilizzano gli Oggetti di apprendimento. Tuttavia, possono svolgere altri ruoli, quali Autore e Manager, insieme al ruolo di Allievo. L’ID utente, il tipo e l’e-mail sono alcuni degli attributi incorporati. |
| risorsa | Rappresenta ogni risorsa contenuto all&#39;interno di un modulo. Tutte le risorse incapsulate in un &quot;loResource&quot; sono equivalenti in termini di obiettivo di apprendimento, ma differiscono l’una dall’altra in termini di tipo di erogazione o impostazioni locali del contenuto. |
| NotificheUtente | Questo modello contiene informazioni di notifica relative a un Allievo. |
| AbilitàUtente | L’AbilitàUtente indica quanto di un singolo livello di abilità viene raggiunto da un singolo utente. |
| BagdeUtente | UserBadge mette in relazione un singolo badge con un singolo utente. Contiene dettagli come quando è stato raggiunto, assertionUrl e così via. |
| abilità | Il modello di abilità è costituito da livelli e crediti. Le abilità possono essere acquisite dagli Allievi dopo il completamento del corso. |
| LivelloAbilità | Un livello di abilità comprende uno o più corsi da utilizzare per acquisire un livello e i relativi crediti associati. |
| learningObject | Un oggetto di apprendimento è un’astrazione per vari tipi di oggetti a cui gli utenti possono iscriversi e da cui possono imparare. Attualmente Learning Manager dispone dei quattro tipi di oggetti di apprendimento, Corso, Certificazione, Programma di apprendimento e Risorsa formativa. |
| IstanzaOggettoApprendimento | Un’istanza specifica di un oggetto di apprendimento. |
| RisorsaOggettoApprendimento | Ciò equivale al concetto di modulo . Un corso è composto da uno o più moduli. In Learning Manager, un modulo può essere distribuito in una serie di modi equivalenti tra loro. Pertanto loResource incapsula essenzialmente tutte le risorse equivalenti. |
| loResourceGrade | Contiene il risultato dell’utilizzo di una risorsa specifica da parte dell’utente nel contesto di un oggetto di apprendimento a cui è iscritto. Contiene informazioni come la durata spesa dall&#39;utente nella risorsa, la percentuale di avanzamento da parte dell&#39;utente, lo stato di superamento/fallimento e il punteggio ottenuto dall&#39;utente in qualsiasi quiz associato. |
| calendario | Un oggetto calendario è un elenco di corsi in aula o in aula virtuale a cui l’utente può iscriversi. |
| InformazioniFeedbackL1 | Il feedback L1 contiene le risposte fornite dall’Allievo alle domande di feedback associate agli oggetti di apprendimento. In genere viene raccolto dopo che l’utente ha completato un oggetto di apprendimento se è configurato per raccogliere tali feedback dagli Allievi. |
| iscrizione | Questa astrazione include i dettagli relativi alla transazione che rappresenta l’assegnazione di un utente specifico a un’istanza specifica dell’oggetto di apprendimento. |


## API ed endpoint degli Allievi

Di seguito sono riportati gli endpoint API chiave per l’utilizzo dei dati dell’Allievo. Queste API guidano gli sviluppatori nell’interazione con le informazioni degli Allievi, nel tracciamento dell’avanzamento, nella gestione delle iscrizioni e nel recupero dei contenuti del corso.

### Recuperare i dettagli di tutti gli Allievi

Recupero dei dettagli dell’Allievo (nome, e-mail, UUID, profilo utente e così via). Utilizza l’API per elencare tutti gli Allievi nell’account.

```
GET https://learningmanager.adobe.com/primeapi/v2/users
```

### Recuperare i dettagli di un Allievo specifico

Se desideri visualizzare il profilo di un Allievo in base all’ID, utilizza le API seguenti per effettuare una chiamata.

```
GET https://learningmanager.adobe.com/primeapi/v2/users/<userID>
```

### Elenca tutti i corsi, i programmi di apprendimento, le risorse formative e le certificazioni

Recupera i dettagli di tutti gli oggetti di apprendimento a cui l’Allievo è iscritto, ha completato o è stato abilitato dall’Amministratore.

```
GET https://learningmanager.adobe.com/primeapi/v2/learningObjects
```

### Ottieni i dettagli di un oggetto di apprendimento specifico

Ottieni informazioni dettagliate su un oggetto di apprendimento. Include la data di creazione, la data di pubblicazione, la data di aggiornamento e altre informazioni.

```
GET https://learningmanager.adobe.com/primeapi/v2/learningObjects/<LearningObjectID>
```

### Recuperare un elenco di abilità collegate ai corsi

Visualizza le abilità assegnate a tutti gli Allievi nell’account.

```
GET https://learningmanager.adobe.com/primeapi/v2/skills
```

### Ottieni informazioni su livelli di abilità e distintivi

Verifica i progressi degli Allievi nei percorsi di apprendimento basati sulle abilità.

```
GET https://learningmanager.adobe.com/primeapi/v2/skills/<skillID>?include=levels
```

### Elenco di tutti i distintivi creati per un account

Effettua una chiamata al seguente endpoint per recuperare un elenco di tutti i distintivi creati per un account in un&#39;organizzazione.

```
GET https://learningmanager.adobe.com/primeapi/v2/badges
```

### Recuperare le informazioni di un badge

Ottieni informazioni dettagliate su un badge, tra cui il nome del badge, l’URL dell’immagine del badge e lo stato del badge.

```
GET https://learningmanager.adobe.com/primeapi/v2/badges/<skillID>
```

Viene generata la seguente risposta:

```
{
    "links": {
        "self": "https://learningmanager.adobe.com/primeapi/v2/badges/499"
    },
    "data": {
        "id": "499",
        "type": "badge",
        "attributes": {
            "imageUrl": "https://cpcontentsdev.adobe.com/public/account/1010/accountassets/1010/badges/test_57a5ab00555a475a8fc6671562184dc9.png",
            "name": "penguins",
            "state": "Retired"
        }
    }
}
```

## Altri esempi di utilizzo delle API

### Creare un utente

1. Utilizzare l&#39;endpoint:

   ```
   POST https://learningmanager.adobe.com/primeapi/v2/users
   ```

   Elabora gli attributi dal corpo API o dal payload JSON per generare un utente e successivamente fornisce a un utente il rispettivo ID utente compilato.

2. Utilizza il seguente payload come corpo:

   ```
   { 
      "data": { 
        "type": "user", 
        "attributes": { 
         "email": "bob@example.com", 
          "name": "Bob", 
          "userType": "INTERNAL" 
        } 
      } 
    }
   ```

Sono disponibili tre attributi obbligatori:

* email: ID e-mail dell&#39;utente. Questo valore deve essere univoco per ogni utente.
* name: il nome dell’utente.
* userType: al momento, solo gli utenti interni possono essere aggiunti utilizzando questo endpoint. Il valore userType deve essere &quot;INTERNAL&quot;.

Riceverai il seguente oggetto JSON:

```
{
  "links": {
      "self": "https://learningmanager.adobe.com/primeapi/v2/users"
  },
  "data": {
      "id": "13386404",
      "type": "user",
      "attributes": {
          "avatarUrl": "https://cpcontents.adobe.com/public/images/default_user_avatar.svg",
          "email": "bob@example.com",
          "name": "Bob",
          "pointsEarned": 0,
          "pointsRedeemed": 0,
          "preferredResolution": "AUTO",
          "profile": "Employee",
          "roles": [
              "Learner"
          ],
          "state": "ACTIVE",
          "userType": "Internal",
          "userUniqueId": "bob@example.com"
      },
      "relationships": {
          "account": {
              "data": {
                  "id": "1010",
                  "type": "account"
              }
          },
          "manager": {
              "data": {
                  "id": "3400468",
                  "type": "user"
              }
          }
      }
  }
}
```

### Elimina un utente

1. Ottieni l’ID utente dell’utente da eliminare.

   ```
   GET https://learningmanager.adobe.com/primeapi/v2/users/<userID>
   ```

2. Quindi, utilizzando DELETE, effettua la seguente chiamata:

   ```
   DELETE https://learningmanager.adobe.com/primeapi/v2/users/<userID>
   ```

Viene visualizzata una risposta 204. Un codice di risposta 204 indica che l’operazione è riuscita senza alcun contenuto da restituire. Il server ha elaborato correttamente la richiesta ma non dispone di dati da fornire al client.

Lo stato dell&#39;utente è ora **[!UICONTROL ELIMINATO]** dopo aver recuperato i dettagli dell&#39;utente.

### Aggiorna dettagli utente

1. Aggiorna i dettagli utente dell’utente utilizzando l’API v2. L’Allievo può modificare bio, uiLocale, contentLocale, fuso orario. Per gli account di grandi dimensioni, si tratta di chiamate asincrone. Molti altri attributi utente possono essere aggiornati utilizzando questo endpoint API. Utilizzare l&#39;endpoint /users/{id}, dove id è l&#39;ID utente dell&#39;utente di cui si desidera aggiornare i dettagli.

```
PATCH https://learningmanager.adobe.com/primeapi/v2/users/<userID>
```

Aggiungi quanto segue nel payload della richiesta di aggiornamento dell&#39;utente con ID `<userID>`, dalla sezione precedente.

Modificare qualsiasi campo nel payload.

```
{
    "data": {
        "id": "3400468",
        "type": "user",
        "attributes": {
            "avatarUrl": "https://cpcontents.adobe.com/public/images/default_user_avatar.svg",
            "binUserId": "3e6d571f-3956-44db-be69-8e458bde649f",
            "bio": "Manager",
            "contentLocale": "de-DE",
            "email": "user@example.com",
            "enrollOnClick": true,
            "fields": {
                "Web": "Web",
                "newfororder": "newvalue",
                "location": "New",
                "test1": "b"
            },
            "gamificationEnabled": true,
            "lastLoginDate": "2025-04-30T09:30:51.000Z",
            "metadata": {
                "level": "5",
                "expertise": "java",
                "sport": "tennis"
            },
            "name": "John Adams",
            "pointsEarned": 8600,
            "pointsRedeemed": 0,
            "preferredResolution": "AUTO",
            "profile": "Employee",
            "roles": [
                "Learner",
                "Admin",
                "Author",
                "Instructor",
                "Integration Admin",
                "Manager"
            ],
            "state": "ACTIVE",
            "timeZoneCode": "213",
            "uiLocale": "en-US",
            "userType": "Internal",
            "userUniqueId": "user@example.com"
        },
        "relationships": {
            "account": {
                "data": {
                    "id": "1010",
                    "type": "account"
                }
            }
        }
    }
}
```

Dopo aver effettuato la chiamata, i dettagli dell&#39;utente vengono aggiornati.

### Creare un profilo esterno

Un profilo esterno si riferisce a un profilo utente creato per allievi esterni, in genere utenti che non fanno parte della base utenti interna dell’organizzazione. Tali Allievi possono includere clienti, partner, fornitori, affiliati o appaltatori temporanei che hanno bisogno di accedere ai programmi di formazione o certificazione offerti dall’organizzazione.

1. Utilizza il seguente endpoint:

   ```
   POST https://learningmanager.adobe.com/primeapi/v2/externalProfiles
   ```

2. Utilizza il seguente payload come corpo:

```
{
    "data": {
      "type": "externalProfile",
      "attributes": {
        "name": "Jonas Albertson",
        "expiry": "2027-12-31T18:29:59.000Z",
        "managerEmail": "jonas@acme.com",
        "seatLimit": 10
      }
    }
}
```

Il payload ha i seguenti attributi:

* name: il nome dell’utente esterno.
* scadenza: la data di scadenza (in formato ISO-8601) della registrazione dell&#39;utente in Adobe Learning Manager.
* managerEmail: l&#39;indirizzo e-mail del manager dell&#39;utente dell&#39;organizzazione partner.
* seatLimit: il numero di postazioni consentito per l’organizzazione partner.

Dopo aver effettuato la chiamata, viene visualizzata la seguente risposta:

```
{
    "links": {
        "self": "https://learningmanager.adobe.com/primeapi/v2/externalProfiles"
    },
    "data": {
        "id": "18805",
        "type": "externalProfile",
        "attributes": {
            "accessKey": "8gte2ne7f4r14",
            "enabled": true,
            "expiry": "2027-12-31T18:29:59.000Z",
            "managerEmail": "jonas@acme.com",
            "name": "Jonas Albertson",
            "seatLimit": 10,
            "url": "https://learningmanager.adobe.com/eplogin?groupid=18805&accesskey=8gte2ne7f4r14"
        }
    }
}
```

L’utente esterno è stato aggiunto a Adobe Learning Manager. Invia l’URL che si trova nella risposta all’utente, utilizzando il quale può registrarsi sulla piattaforma.

### Estrarre il report utente con ID utente e dettagli manager

È possibile scaricare un report utente direttamente dall&#39;interfaccia utente amministratore (**[!UICONTROL Amministratore]** > **[!UICONTROL Utenti]** > **[!UICONTROL Interno]**). Tuttavia, il report non restituisce l&#39;ID utente e i dettagli del manager associato.

Utilizza l’API dei processi per scaricare il report. L’API dei processi consente di generare report, operazioni in blocco (iscrizioni o assegnazioni di badge), completamenti di certificazioni o generazione di badge.

Ecco come puoi scaricare il report:

1. Aggiungi il seguente payload all’API dei processi.

   ```
   {
       "data": {
           "type": "job",
           "attributes": {
               "description": "description of your choice",
               "jobType": "generateUsers",
               "payload":{
                   "expandMetadata":true
               }
           }
      }
   }
   ```

2. Utilizzare il punto finale seguente.

   ```
   POST https://learningmanager.adobe.com/primeapi/v2/jobs
   ```

3. Copia l’ID processo dalla risposta.

   ```
   {
       "links": {
           "self": "https://learningmanager.adobe.com/primeapi/v2/jobs"
       },
       "data": {
           "id": "43118",
           "type": "job",
           "attributes": {
               "dateCreated": "2025-05-26T06:35:35.000Z",
               "description": "description of your choice",
               "jobType": "generateUsers",
               "payload": {
                   "expandMetadata": true
               },
             "status": {
                   "code": "Submitted"
               }
           }
       }
   }
   ```

   Nella risposta, l&#39;ID processo è 43118.
4. Dopo aver copiato l’ID, scarica il report utilizzando l’ID nell’API dei processi.

   ```
   GET https://learningmanager.adobe.com/primeapi/v2/jobs/43118
   ```

5. Copia l’URL S3 dalla risposta.
6. Incollate l’URL nel browser. Il browser richiede di salvare o aprire il file CSV. Salvate il file sul computer.
Il file scaricato contiene le seguenti colonne:

internalUserID, userEmail, customerDefinedUniqueUserId, name, managerEmail, userType, state, excludeFromGamification, pointsEarned, profile, roles, dateCreated, lastLoginDate, dateDeleted, uiLocale, contentLocale, timeZoneCode, userSource, group, campi attivi, metadati e lastSocialActivityDate.

### Generare un badge mediante l’API dei processi

1. Ottieni un elenco di distintivi per un utente dell&#39;organizzazione. Utilizza il seguente endpoint:

   ```
   GET https://learningmanager.adobe.com/primeapi/v2/users/3400476/userBadges
   ```

   Dove 3400476 è l’ID utente.
2. Copia l’ID badge dalla risposta. Ad esempio, 3400476_759_COMPETENCY_1796_1 è l’ID del badge.

   ```
   {
    "id": "3400476_759_COMPETENCY_1796_1",
    "type": "userBadge",
    "attributes": {
        "assertionUrl": "https://cpcontentsdev.adobe.com/public/accountassets/1010/badges/assertions/a99566b5aa8f4cfa92380581733c63a9_1626278856926.json",
        "dateAchieved": "2016-02-25T08:45:25.000Z",
        "modelType": "skillLevel"
    },
    "relationships": {
        "badge": {
            "data": {
                "id": "759",
                "type": "badge"
            }
        },
        "learner": {
            "data": {
                "id": "3400476",
                "type": "user"
            }
        },
        "model": {
            "data": {
                "id": "1796_1",
                "type": "skillLevel"
            }
        }
    }
   }
   ```

3. Crea un payload e specifica l’ID badge nel payload. Di seguito è riportato un esempio di payload:

   ```
   {
    "data": {
        "type": "job",
        "attributes": {
            "description": "Acme Corp Badge",
            "jobType": "generateUserBadge",
            "payload": {
                "userBadgeId": "3400476_759_COMPETENCY_1796_1"
            }
        }
    }
   }  
   ```

   Dopo aver effettuato una chiamata, riceverai l&#39;ID processo nella risposta.
4. Prendere l&#39;ID processo dalla risposta e utilizzare l&#39;ID processo nell&#39;endpoint seguente per effettuare la chiamata.

   ```
   GET https://learningmanager.adobe.com/primeapi/v2/jobs/<jobsID>
   ```

5. Copia l’URL del badge dalla risposta e aprilo in un browser. Il certificato verrà scaricato come PDF.

### Creazione di utenti in Adobe Learning Manager

L’endpoint POST /users consente di creare un utente utilizzando la modalità headless. Creazione di utenti con informazioni dettagliate, come la procedura di registrazione nell’interfaccia utente nativa in Adobe Learning Manager.

Ad esempio:

```
POST https://learningmanager.adobe.com/primeapi/v2/users
```

Aggiungi il seguente corpo alla richiesta:

```
{   
   "data":  
     {  
       "type": "user",  
       "attributes": {  
         "bio": "",  
         "contentLocale": "fr-FR",  
         "email": "user@work.com",  
         "enrollOnClick": true,  
         "fields": {  
           "Learning Categories": [  
             "Business"  
           ],  
           "Categories": "IT"  
         },  
         "gamificationEnabled": true,  
         "name": "Test User",  
         "profile": "Engineer",  
         "userType": "INTERNAL",  
         "userUniqueId": "user@work.com"  
       },  
       "relationships": {  
         "account": {  
           "data": {  
             "id": "108079",  
             "type": "account"  
           }  
         }
         }  
       }  
    } 
```

Dopo aver effettuato la chiamata, viene visualizzata la seguente risposta:

```
{
    "links": {
        "self": "https://learningmanager.adobe.com/primeapi/v2/users"
    },
    "data": {
        "id": "13385627",
        "type": "user",
        "attributes": {
            "avatarUrl": "https://cpcontents.adobe.com/public/images/default_user_avatar.svg",
            "email": "user@work.com",
            "name": "Test User",
            "pointsEarned": 0,
            "pointsRedeemed": 0,
            "preferredResolution": "AUTO",
            "profile": "Engineer",
            "roles": [
                "Learner"
            ],
            "state": "ACTIVE",
            "userType": "Internal",
            "userUniqueId": "user@work.com"
        },
        "relationships": {
            "account": {
                "data": {
                    "id": "1010",
                    "type": "account"
                }
            },
            "manager": {
                "data": {
                    "id": "3400468",
                    "type": "user"
                }
            }
        }
    }
}
```

Un nuovo utente verrà aggiunto a Adobe Learning Manager.

### Post feedback L1

1. Recupera i dati del corso, dell’istanza e dell’iscrizione dell’Allievo. Utilizza il seguente endpoint:

   ```
   GET /enrollments
   ```

2. Verifica se il feedback L1 è abilitato per l’istanza del corso.

   ```
   GET https://learningmanager.adobe.com/primeapi/v2/learningObjects/<loID>/instances/<loInstanceID>/l1Feedback
   ```

3. Invia il feedback L1.

   ```
   POST /enrollments/{id}/l1Feedback
   ```

Esempio di payload richiesto:

```
{
    "data": {
      "id": "course:7454218_10333537_11257863",
      "type": "feedback",
      "attributes": {
        "questions": [
          {
            "answer": "8",
            "questionId": "1",
            "mandatory": true,
            "questionType": "scaleTen"
          }
        ],
        "score": 80
      }
    }
  }
```

### Recupero delle informazioni a livello di modulo di un corso

1. Recupera i dettagli di un oggetto di apprendimento tramite ID.

   ```
   GET https://learningmanager.adobe.com/primeapi/v2/learningObjects/<loID>
   ```

   ```
   {
    "links": {
        "self": "https://learningmanager.adobe.com/primeapi/v2/learningObjects/course:1171899"
    },
    "data": {
        "id": "course:1171899",
        "type": "learningObject",
        "attributes": {
            "authorNames": [
                "James Adams"
            ],
            "dateCreated": "2017-11-01T15:28:09.000Z",
            "datePublished": "2017-11-01T15:28:20.000Z",
            "dateUpdated": "2017-11-01T15:28:20.000Z",
            "duration": 60,
            "effectiveModifiedDate": "2017-11-01T15:28:20.000Z",
            "effectivenessIndex": 0,
            "enrollmentType": "Self Enroll",
            "hasOptionalLoResources": false,
            "hasPreview": false,
            "isExternal": false,
            "isMqaEnabled": false,
            "isPrerequisiteEnforced": false,
            "isSubLoOrderEnforced": false,
            "loFormat": "Self Paced",
            "loResourceCompletionCount": 3,
            "loType": "course",
            "moduleResetEnabled": false,
            "state": "Published",
            "unenrollmentAllowed": true,
            "catalogLabels": [
                {
                    "catalogLabelValueIds": [
                        {
                            "name": "Sales",
                            "id": "catalogLabel:13_31"
                        }
                    ],
                    "description": "",
                    "mandatory": false,
                    "name": "Department",
                    "values": [
                        "Sales"
                    ]
                }
            ],
            "localizedMetadata": [
                {
                    "locale": "en-US",
                    "name": " Test course 2"
                }
            ],
            "rating": {
                "averageRating": 0,
                "ratingsCount": 0
            }
        },
        "relationships": {
            "authors": {
                "data": [
                    {
                        "id": "3400468",
                        "type": "user"
                    }
                ]
            },
            "instances": {
                "data": [
                    {
                        "id": "course:1171899_2067352",
                        "type": "learningObjectInstance"
                    }
                ]
            },
            "skills": {
                "data": [
                    {
                        "id": "course:1171899_1797",
                        "type": "learningObjectSkill"
                    }
                ]
            }
        }
    }
   }
   ```

2. Utilizzare il parametro include per recuperare quanto segue:

   a. Elenca tutti i moduli dell’oggetto di apprendimento.

   ```
   GET https://learningmanager.adobe.com/primeapi/v2/learningObjects/course:1171899?include=instances.loResources
   ```

   b. Elenca tutto il contenuto dei moduli.

   ```
   GET https://learningmanager.adobe.com/primeapi/v2/learningObjects/course:1171899?include=instances.loResources.resources
   ```

### Verifica avanzamento modulo

1. Recupera l’oggetto di apprendimento dal catalogo utilizzando l’ID corso.

   ```
   GET https://learningmanager.adobe.com/primeapi/v2/learningObjects?page[limit]=10&filter.loTypes=course&sort=name&filter.ignoreEnhancedLP=true&id=<courseID>
   ```

2. Ottieni i dettagli di iscrizione di un Allievo utilizzando l’ID di iscrizione.

   ```
   GET https://learningmanager.adobe.com/primeapi/v2/enrollments/<enrollmentID>
   ```

   Copia l’ID livello risorsa oggetto di apprendimento dalla risposta.
3. Utilizzare l&#39;ID nell&#39;endpoint seguente.

   ```
   GET https://learningmanager.adobe.com/primeapi/v2/loResourceGrades/<courseResourceGradeID>
   ```

Nella risposta verranno fornite informazioni sull&#39;avanzamento del modulo.

### Implementare la rappresentazione dell’Allievo

Quando si implementa un sistema LMS headless con Adobe Learning Manager come backend, le organizzazioni potrebbero richiedere allo staff di supporto di impersonare gli Allievi per la risoluzione dei problemi o l’assistenza. Il metodo di rappresentazione basato su API garantisce l’accesso sicuro mantenendo la riservatezza delle credenziali dell’Allievo e supporta transizioni senza problemi negli stati della sessione.

Adobe Learning Manager facilita la rappresentazione degli Allievi in ambienti LMS headless tramite un’API dedicata. Questa funzione consente al personale di supporto di assumere temporaneamente l’identità di un allievo, consentendo di diagnosticare problemi, testare funzionalità o fornire assistenza pratica simulando l’esperienza dell’allievo. La rappresentazione viene attivata utilizzando un token di accesso amministratore memorizzato nella cache, utilizzato per generare a livello di programmazione un token di accesso Allievo. Questo processo consente al sistema di funzionare come se fosse connesso come l’Allievo.

>[!IMPORTANT]
>
>Per utilizzare questa funzione, gli utenti devono richiedere un accesso API speciale e il sistema deve gestire il cambio di sessione, l’autorizzazione e altri indicatori per garantire trasparenza e responsabilità durante la rappresentazione.

**Dettagli endpoint API**

```
POST /oauth/learnerToken
```

**Esempio di URL completo**

```
https://learningmanager.adobe.com/oauth/o/learnerToken?learner_email=foo@acme.com&force=false
```

**Parametri query:**

* learner_email: (stringa) L’e-mail dell’Allievo da rappresentare.
* force: (booleano) Indica se generare forzatamente un nuovo token, se esistente.

**Corpo della richiesta:**

```
{
    "client_id": "your-client-id",
    "client_secret": "your-client-secret",
    "refresh_token": "your-admin-refresh-token"
}  
```

**Risposta di esempio:**

```
{
    "access_token": "generated-token",
    "refresh_token": "new-refresh-token",
    "user_role": "learner",
    "account_id": "123456",
    "user_id": "7891011",
    "expires_in": 604800
}  
```

**Esempio di cURL:**

```
curl --location --request POST 'https://learningmanager.adobe.com/oauth/o/learnerToken?learner_email=foo@acme.com&force=false' \
--header 'Content-Type: application/json' \
--data-raw '{
  "client_id": "xxxx",
  "client_secret": "xxxx",
  "refresh_token": "xxxx"
}'
```


### Codici di errore

Quando si utilizzano le API di Adobe Learning Manager (Adobe Learning Manager), gli sviluppatori potrebbero riscontrare vari codici di errore HTTP durante le richieste. Questi errori forniscono un feedback importante su cosa è andato storto e su come correggerlo. La comprensione di questi codici aiuta gli sviluppatori a risolvere rapidamente i problemi, migliorare l’affidabilità delle API e garantire integrazioni più fluide. La tabella seguente illustra i codici di errore HTTP più comuni restituiti dalle API di Adobe Learning Manager, oltre a spiegazioni e scenari tipici in cui si verificano. Questa sezione è essenziale per chiunque crei, esegua test o esegua il debug di applicazioni collegate a Adobe Learning Manager.

| Stato HTTP | Significato | Risoluzione dei problemi |
|---|---|---|
| 400 | Richiesta non valida | Verificare la presenza di parametri mancanti o non validi nella richiesta. Verifica i campi obbligatori e la formattazione corretta. Ad esempio, sintassi non valida per filtri, campi o parametri di inclusione. |
| 401 | Token non autorizzato non valido o mancante | Assicurati che il token di accesso sia corretto e incluso nell&#39;intestazione Autorizzazione. Verifica che il token sia attivo. Quando richiedi il token, utilizza anche l’ID client e il segreto client corretti. |
| 403 | Proibito. Nessun accesso | Non si dispone dell&#39;autorizzazione per accedere alla risorsa. Verifica che il token abbia gli ambiti corretti (admin:read, learner:write, ecc.). |
| 404 | Risorsa non trovata | L&#39;endpoint o l&#39;ID della risorsa non è corretto o non esiste. Verificare che la risorsa esista nell&#39;elenco dei parametri. |
| 406 | Non accettabile - Intestazione di accettazione errata | Aggiungi questa intestazione alla richiesta: Accetta: application/vnd.api+json <br>Le API Adobe Learning Manager richiedono rigorosamente questo tipo di contenuto.</br> |
| 500 | Errore interno del server | Si tratta di un problema sul lato server. Riprova più tardi o segnala il problema ai team di supporto Adobe Learning Manager se continua. |




<!--# Application developer manual

>[!NOTE]
>
>Learning Manager V1 API is now deprecated. We recommend that you use V2 APIs to interact with Learning Manager.


## Overview {#overview}

[Adobe Learning Manager](http://www.adobe.com/in/products/learningmanager.html) is a cloud-hosted, learner-centric, and self-service learning management solution. Customers can access Learning Manager resources programmatically using the Learning Manager API to integrate it with other enterprise applications. The API can also be used by Adobe partners to enhance the value proposition of Learning Manager, by extending its functionality or by integrating it with other applications or services.

### Usage scenario {#usagescenario}

Using Learning Manager API, developers can build self-contained applications that extend the functionality of Learning Manager or integrate Learning Manager with other enterprise applications workflows. You can develop a web application, desktop client or a mobile app using any technology of your choice. As a developer you can access your application data from within Learning Manager. The deployment of the application that you develop is external to the Learning Manager platform and you have full control over the software development lifecycle as the application evolves. Typically, applications are developed by a customer organization for use with their Learning Manager account, and these applications are private to that specific customer organization. Also, Adobe partners can build generic applications with Learning Manager API, that can be used by a large set of Learning Manager customers.

## Learning Manager API {#apidescription}

The Learning Manager API is based on principles of REST, and exposes key elements of the Learning Manager Object Model to application developers through HTTP. Before knowing the details of the API endpoints and the HTTP methods, developers can become familiar with the various Learning Manager objects, their attributes and inter-relationships. Once the models are understood, it will be useful to get a basic understanding of the structure of API requests and responses, and a few common programming terms that we use generically across the API.

For details of the various API endpoints and methods, refer to the  [Learning Manager API documentation](https://learningmanager.adobe.com/docs/primeapi/v2/).

## Learner APIs

Adobe Learning Manager - Learner APIs allow you to create a custom learning experience for your users. The usage of these APIs need a valid user token and are to be used only for the purpose of workflows where there is a fully licensed/registered Learner.
 
>[!IMPORTANT]
>
>They are not to be used, as is, for any sort of data retrieval to support any non-logged in user/shared users or any other such cases.
 
The non-logged in use cases require special handling. 

**Reach out to the Solution Architecture team, in case you have any questions on the appropriate use of these APIs and ensure that a Solution Architect has vetted a solution before you deploy it**.

## API authentication {#apiauthentication}

When writing an application that makes API calls to Learning Manager, you have to register your application using the Integration Admin app. 

Learning Manager APIs use OAuth 2.0 framework to authenticate and authorize your client applications. 

**Procedure**

**1. Set up your application**

You can set up your application with client id and client secret to use the proper end points. Once you register your application, you can get the clientId and clientSecret. Get URL should be used in browser as it authenticates the Learning Manager users using their pre-configured accounts such as SSO, Adobe ID, and so on. 

```
GET https://learningmanager.adobe.com/oauth/o/authorize?client_id=<Enter your clientId>&redirect_uri=<Enter a url to redirect to>&state=<Any String data>&scope=<one or more comma separated scopes>&response_type=CODE.
```

After successful authentication, your browser redirects to the redirect_uri mentioned in the above URL. A parameter **code** is appended along with the redirect uri.

**2. Get refresh token from code**

`POST https://learningmanager.adobe.com/oauth/token Content-Type: application/x-www-form-urlencoded`

Body of the post request:

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

**3.** **Obtain an access token from refresh token**

URL to obtain access token: 

POST [https://learningmanager.adobe.com/oauth/token/refresh](https://learningmanager.adobe.com/oauth/token/refresh) Content-Type: application/x-www-form-urlencoded

Body of the post request:

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

**URL to verify access token details**

`GET https://learningmanager.adobe.com/oauth/token/check?access_token=<access_token>`

**Usage limitation**

An access token is valid for seven days. After a day, you have to generate a new access token using refresh token. If you generate a new access token from refresh token while an existing access token is still valid, the existing token is returned. 

Some of the frequently used terms in Learning Manager API are explained below for your reference. 

**Includes**

Developers can access a single API object model and also multiple models associated with that model. To access the subsequent related models, you need to understand the relationship of each model with other models. **Includes** parameter enables developers to access the dependant models. You can use comma separator to access multiple models. For sample usage and more details on **includes**, refer to sample API model section in this page. 

**API request**

The API requests can be made by making a HTTP Request. Depending upon the end point and method developer may have a choice of various HTTP verbs such as GET, PUT, POST, DELETE, PATCH, etc. For some requests query parameters can be passed. When making a request for a specific data model, the user can also request for related models as described in the JSON API specifications. The structure of a typical API Request is described in [sample model usage](/help/migrated/integration-admin/feature-summary/developer-manual.md#api-usage-illustration).

**API response**

When an API request is made by a client, a SON document is obtained according to the JSON API specification. The response also contains the HTTP Status code, which the developer can verify to perform the appropriate next steps in his application logic. The structure of a typical API Response is described in  [sample model usage](/help/migrated/integration-admin/feature-summary/developer-manual.md#api-usage-illustration).

**Errors**

When an API request fails, an Error response is obtained. The HTTP Status code returned in the response indicates the nature of error. Error codes are represented with numbers for each model in the API reference. 200, 204, 400 and 404 are some of the common errors represented in APIs indicating HTTP access issues.  

**Fields**

API object's attributes and its relationships are collectively called Fields. Refer to [JSON API for more information.](http://jsonapi.org/format/#document-resource-object-fields) You can use Fields as a parameter while making API calls to fetch one or more specific attributes from the model. In absence of the Fields parameter, the API call fetches all the available attributes from the model. For example, in the following API call, fields[skill]=name fetches you the name attribute of the skill model alone. 

`https://learningmanager.adobe.com/primeapi/v2/users/{userId}/userSkills/{id}?include=skillLevel.skill&fields[skill]=name `

**Pagination**

Sometimes, an API request results in a long list of objects to be returned in the response. In such cases, the pagination attribute enables the developer to fetch the results sequentially in terms of multiple pages, where each page contains a range of records. For example, pagination attribute in Learning Manager enables you to set the maximum number of records to be displayed in a page. Also, you can define the range value of records to be displayed on page. 

**Sorting**

Sorting is allowed in API models. Based on the model, choose the type of sorting to be applied for the results. Sorting can be applied in ascending or descending order. For example, if you specify `code sort=name`, then it is ascending sort by name. If you specify `code sort=-name`, it is descending sort by name. Refer to [JSON API spec for more information](http://jsonapi.org/format/#fetching-sorting). 

## API usage illustration {#samplemodel}

Let us consider a scenario where a developer wants to get skill name, max points assigned for skill level and points earned by the learner for that skill.

A userSkill model in Learning Manager APIs consists of id, type, dateAchieved, dateCreated, pointsEarned as default attributes. So, when a developer uses GET method to acquire details of userSkill model, the current data pertaining to the default attributes is shown in the response output. 

But, in this scenario, the developer wants to get the skill name, and points of skill level for the user. Learning Manager API enables you to access this related information using relationship fields and include parameter. The associated models for userSkill are obtained in relatioships tag. You can get the details of each associated models by calling these models along with the userSkill. To get this information, use **`code include`** parameter with dot (period) separated values for each of the associated models. You can use comma as separator to request another model like user include=skillLevel.skill,course

**API Call**

`https://learningmanagerqe1.adobe.com/primeapi/v1/users/%7buserId%7d/userSkills/%7bid%7d?include=skillLevel.skill&fields%5bskill%5d=name&fields%5bskillLevel%5d=maxCredits&fields%5buserSkill%5d=pointsEarned`

For example userId can be 746783 and the userSkills id: 746783_4426_1. 

**Response of API call**

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

## Learning Manager models {#models}

The Learning Manager API allows developers to access Learning Manager objects as RESTful resources. Each API endpoint represents a resource, typically an object instance like Badge, or a collection of such objects. The developers then use the HTTP verbs such as PUT, GET, POST and DELETE to perform the CRUD operations on those objects (collections).

+++V1 API

The following diagram represents the various elements of the Learning Manager Object Model in V1 API.

![](assets/er-diag-primemodels.png)

The following table describes various elements of the Learning Manager V1 object model: 

<table border="1" cellspacing="0" cellpadding="0">
 <tbody>
  <tr>
   <td>
    <p><strong>Serial No</strong></p></td>
   <td>
    <p><strong>Learning Manager Object</strong></p></td>
   <td>
    <p><strong>Description</strong></p></td>
  </tr>
  <tr>
   <td>
    <p>1.      </p></td>
   <td>
    <p>user</p></td>
   <td>
    <p>User is the key model in Learning Manager. Users are typically the internal or external learners of an organization who consume Learning Objects. However they may play some other roles such as author and Manager along with learner role. User id, type, email are some of the inline attributes. </p></td>
  </tr>
  <tr>
   <td>
    <p>2.      </p></td>
   <td>
    <p>course</p></td>
   <td>
    <p>Course is one of the Learning Objects supported in Learning Manager, that consists of one or more modules. </p></td>
  </tr>
  <tr>
   <td>
    <p>3.      </p></td>
   <td>
    <p>module</p></td>
   <td>
    <p>Module is a building block to create Learning Objects in Learning Manager. Modules can be of four different types such as Class room, virtual class room, activity and self-paced. Use this module model to get the details of all modules in an account. </p></td>
  </tr>
  <tr>
   <td>
    <p>4.      </p></td>
   <td>
    <p>certification</p></td>
   <td>
    <p>Certification is awarded to learners based on successful completion of courses. Courses are required in the application before you use certifications. </p></td>
  </tr>
  <tr>
   <td>
    <p>5.      </p></td>
   <td>
    <p>learning program</p></td>
   <td>
    <p>Learning programs are uniquely designed courses meeting specific learning requirements of users. Typically, learning programs are used to drive learning goals spanning across individual courses. </p></td>
  </tr>
  <tr>
   <td>
    <p>6.      </p></td>
   <td>
    <p>badge</p></td>
   <td>
    <p>Badge is a token of accomplishment that learners get when they reach specific milestones as they progress within a course. </p></td>
  </tr>
  <tr>
   <td>
    <p>7.      </p></td>
   <td>
    <p>skill</p></td>
   <td>
    <p>Skills model consists of levels and credits. Skills can be acquired by learners after relevant course completion. </p></td>
  </tr>
  <tr>
   <td>
    <p>8.      </p></td>
   <td>
    <p>certificationEnrollment</p></td>
   <td>
    <p>This model provides details of an enrollment by a user to a single certification.</p></td>
  </tr>
  <tr>
   <td>
    <p>9.  </p></td>
   <td>
    <p>courseEnrollment</p></td>
   <td>
    <p>This model provides details of an enrollment by a user to a single course. </p></td>
  </tr>
  <tr>
   <td>
    <p>10.  </p></td>
   <td>
    <p>courseInstance</p></td>
   <td>
    <p>A course can have one or many instances associated with it. You can get Course instance </p></td>
  </tr>
  <tr>
   <td>
    <p>11.  </p></td>
   <td>
    <p>courseSkill</p></td>
   <td>
    <p>A courseSkill model specifies the progress of a single skill that is achieved by completing a course.</p></td>
  </tr>
  <tr>
   <td>
    <p>12.  </p></td>
   <td>
    <p>courseModule</p></td>
   <td>A courseModule model specifies how a module is included  in a course. For instance, whether the module is used for pretest or for content.</td>
  </tr>
  <tr>
   <td>
    <p>13.  </p></td>
   <td>learningProgramInstance</td>
   <td>
    <p>A learning program can consist of multiple instances imbibing similar properties of a learning program or customized instances. </p></td>
  </tr>
  <tr>
   <td>
    <p>14.  </p></td>
   <td>
    <p>job aid</p></td>
   <td>
    <p>Job aid is a learning content accessible to learners without any enrollment or completion criteria. You can fetch, updated date, state, id information along with its related models such as job aid version, authors and skill level. </p></td>
  </tr>
  <tr>
   <td>
    <p>15.  </p></td>
   <td>
    <p>jobAidVersion</p></td>
   <td>
    <p>Job aid can have one or many versions associated to it based on number revisions in content and number of uploads. This model provides details of a single job aid version. </p></td>
  </tr>
  <tr>
   <td>
    <p>16.  </p></td>
   <td>
    <p>learningProgramInstanceEnrollment</p></td>
   <td>
    <p>Learning program consists of one or many instances. Learners can enroll to a learning program instance by themselves or assigned by administrator. This model provides details of an enrollment by a user to a single learning program instance. </p></td>
  </tr>
  <tr>
   <td>
    <p>17.  </p></td>
   <td>
    <p>moduleVersion</p></td>
   <td>
    <p>A module can have one or many versions based on its revised content uploads. Use this model to obtain specific info about any single module version. </p></td>
  </tr>
  <tr>
   <td>
    <p>18.  </p></td>
   <td>
    <p>skillLevel</p></td>
   <td>
    <p>A skill level comprises of one or many courses to be consumed in order to acquire a level along with its associated credits. </p></td>
  </tr>
  <tr>
   <td>
    <p>19.  </p></td>
   <td>
    <p>userBadge</p></td>
   <td>
    <p>UserBadge relates a single badge with a single user. It contains details such as when was it achieved, assertionUrl and so on. </p></td>
  </tr>
  <tr>
   <td>
    <p>20.  </p></td>
   <td>
    <p>userSkill</p></td>
   <td>
    <p>UserSkill indicates how much of a single skill level is achieved by a single user.</p></td>
  </tr>
 </tbody>
</table>

+++

+++V2 API

Following are the various elements of the Learning Manager class diagram in V2 API.

![](assets/v2api-class-diagram.jpg)

<table>
 <tbody>
  <tr>
   <th><b>Learning Manager Object</b></th>
   <th><b>Description</b></th>
  </tr>
  <tr>
   <td>account</td>
   <td>Encapsulates the details of a Learning Manager customer.</td>
  </tr>
  <tr>
   <td><code>
     badge
    </code></td>
   <td>Badge is a token of accomplishment that learners get when they reach specific milestones as they progress within a course. <br></td>
  </tr>
  <tr>
   <td><code>
     catalog
    </code></td>
   <td>Catalog is a collection of Learning Objects.</td>
  </tr>
  <tr>
   <td><code>
     user
    </code></td>
   <td>User is the key model in Learning Manager. Users are typically the internal or external learners of an organization who consume Learning Objects. However, they may play some other roles such as author and Manager along with learner role. User id, type, email are some of the inline attributes. </td>
  </tr>
  <tr>
   <td>resource</td>
   <td>This is used to model each content resource that a module seeks to encapsulate. All resources encapsulated within <code>
     an
    </code> <code>
     loResource
    </code> are equivalent in terms of the learning objective, but they differ from each other in terms of delivery type or content locale.<br></td>
  </tr>
  <tr>
   <td>userNotification</td>
   <td>This model contains notification information pertaining to a learner.<br></td>
  </tr>
  <tr>
   <td>userSkill</td>
   <td>UserSkill indicates how much of a single skill level is achieved by a single user.<br></td>
  </tr>
  <tr>
   <td>userBadge</td>
   <td>UserBadge relates a single badge <code>
     with
    </code> a single user. It contains details such as when was it achieved, <code>
     assertionUrl
    </code> and so on. <br></td>
  </tr>
  <tr>
   <td>skill</td>
   <td>Skills model consists of levels and credits. Skills can be acquired by learners after relevant course completion. <br></td>
  </tr>
  <tr>
   <td>skillLevel</td>
   <td>A skill level comprises of one or many courses to be consumed in order to acquire a level along with its associated credits. <br></td>
  </tr>
  <tr>
   <td>learningObject</td>
   <td>A Learning Object is an abstraction for various kinds of objects which users can enroll into and learn from. Currently Learning Manager has the four types of Learning Objects – Course, Certification, Learning Program <code>
     and
    </code> Job Aid.<br></td>
  </tr>
  <tr>
   <td>learningObjectInstance<br></td>
   <td>A specific instance of a learning object.<br></td>
  </tr>
  <tr>
   <td>learningObjectResource</td>
   <td>This is equivalent to the concept of <code>
     module
    </code>. A course is composed of one <code>
     of
    </code> more modules. In Learning Manager, a module can be delivered in a variety of equivalent ways. Therefore the <code>
     loResource
    </code> essentially encapsulates all those equivalent resources.<br></td>
  </tr>
  <tr>
   <td>loResourceGrade<br></td>
   <td>This encapsulates the outcome of the user consuming a specific resource in the context of a learning object he is enrolled into. It has information such as the duration spent by <code>
     user
    </code> in the resource, percentage progress made by the user, pass/fail status and the score obtained by the user in any associated quiz.<br></td>
  </tr>
  <tr>
   <td>calendar<br></td>
   <td>A calendar object is a list of <code>
     upcoming classroom
    </code> or virtual classroom courses that the user can enroll into.<br></td>
  </tr>
  <tr>
   <td>l1FeedbackInfo<br></td>
   <td>L1 Feedback encapsulates the answers provided by a learner for the feedback questions associated with Learning Objects. Typically this is collected after the user completes a Learning Object if configured to collect such feedback from learners.<br></td>
  </tr>
  <tr>
   <td>enrollment<br></td>
   <td>This abstraction encapsulates the details pertaining to the transaction representing the assignment of a specific user to a specific learning object instance.<br></td>
  </tr>
 </tbody>
</table>

+++

List of object attributes and relationships.

+++account

**Attributes** 
dateCreated  
gamificationEnabled  
id  
locale  
loginUrl  
logoUrl  
name  
subdomain  
themeData  
timeZoneCode

**Relationships** 
contentLocales(localizationMetadata)  
gamificationLevels(gamificationLevel)  
timeZones(timeZone)  
uiLocales(localizationMetadata)

+++

+++badge

**Attributes** 
id  
imageUrl  
name  
state

+++

+++catalog

**Attributes** 
dateCreated  
dateUpdated  
description  
id  
isDefault  
isInternallySearchable  
isListable  
name  
state

+++

+++data

**Attributes** 
id  
names

+++

+++gamification

**Attributes** 
color  
name  
points

+++

+++learningObject

**Attributes** 
authorNames  
dateCreated  
datePublished  
dateUpdated  
effectivenessIndex  
enrollmentType  
id  
imageUrl  
isExternal  
isSubLoOrderEnforced  
loType  
state  
tags

**Relationships** 
authors(user)  
enrollment(learningObjectInstanceEnrollment)  
instances(learningObjectInstance)  
prerequisiteLOs(learningObject)  
skills(learningObjectSkill)  
subLOs(learningObject)  
supplementaryLOs(learningObject)  
supplementaryResources(resource)

+++

+++learningObjectInstance

**Attributes** 
completionDeadline  
dateCreated  
enrollmentCount  
id  
isDefault  
seatLimit  
state  
validity

**Relationships** 
badge(badge)  
l1FeedbackInfo(feedbackInfo)  
learningObject(learningObject)  
loResources(learningObjectResource)  
localizedMetadata(localizationMetadata)  
subLoInstances(learningObjectInstance)

+++

+++learningObjectInstanceEnrollment

**Attributes** 
dateCompleted  
dateEnrolled  
dateStarted  
hasPassed  
id  
progressPercent  
score  
state

**Relationships** 
learner(user)  
learnerBadge(userBadge)  
learningObject(learningObject)  
loInstance(learningObjectInstance)  
loResourceGrades(learningObjectResourceGrade)

+++

+++learningObjectResource

**Attributes** 
externalReporting  
id  
loResourceType  
resourceType  
version

**Relationships** 
learningObject(learningObject)  
loInstance(learningObjectInstance)  
localizedMetadata(localizationMetadata)  
resources(resource)

+++

+++learningObjectResourceGrade

**Attributes** 
dateCompleted  
dateStarted  
dateSuccess  
duration  
hasPassed  
id  
progressPercent  
score

**Relationships** 
loResource(learningObjectResource)

+++

+++learningObjectSkill

**Attributes** 
credits  
id  
**Relationships** 
learningObject(learningObject)  
skillLevel(skillLevel)

+++

+++recommendation

**Attributes** 
id  
reason

**Relationships** 
learningObject(learningObject)

+++

+++resource

**Attributes** 
authorDesiredDuration  
completionDeadline  
contentStructureInfoUrl  
contentType  
contentZipSize  
contentZipUrl  
dateCreated  
dateStart  
desiredDuration  
downloadUrl  
extraData  
hasQuiz  
hasToc  
id  
instructorNames  
isDefault  
locale  
location  
name  
onlyQuiz  
reportingInfo  
reportingType  
seatLimit

+++

+++skill

**Attributes** 
description  
id  
name  
state

**Relationships** 
levels(skillLevel)

+++

+++skillLevel

**Attributes** 
id  
level  
maxCredits  
name  
**Relationships** 
badge(badge)  
skill(skill)

+++

+++user

**Attributes** 
avatarUrl  
bio  
contentLocale  
email  
fields  
id  
name  
pointsEarned  
profile  
roles  
state  
timeZoneCode  
uiLocale

**Relationships** 
account(account)  
manager(user)

+++

+++userBadge

**Attributes** 
assertionUrl  
dateAchieved  
id  
modelType

**Relationships** 
badge(badge)  
learner(user)  
model(learningObject)

+++

+++userCalendar

**Attributes** 
course  
courseType  
dateStart  
enrolled  
id  
month  
quarter

**Relationships** 
containerLO(learningObject)  
course(learningObject)

+++

+++userNotification

**Attributes** 
actionTaken  
channel  
dateCreated  
id  
message  
modelIds  
modelNames  
modelTypes  
read  
role

+++

+++userSkill

**Attributes** 
dateAchieved  
dateCreated  
id  
pointsEarned

**Relationships** 
learnerBadge(userBadge)  
learningObject(learningObject)  
skillLevel(skillLevel)  
user(user)

+++

## Application development process {#registration}

## Pre-requisites {#prerequisites}

As a developer you have to create a trial account on Learning Manager, so that you can have full access to all the roles within that account. To be able to write an application, a developer has to create some users and courses and get the account to a reasonable state so that the application being developed can have access to some sample data.

## Create client id and secret {#createclientidandsecret}

1. In **Integration Admin** login, click **[!UICONTROL Applications]** on the left pane. 

   ![](assets/application-development-menu.png)

   *Select Applications on Integration Admin*

1. Click **[!UICONTROL Register]** at the upper-right corner of the page to register your application details. Registration page appears. 

   ![](assets/register-application.png)

   *Register the application*

   It is mandatory to fill up all the fields in this page. 

   **Application Name**: Enter your application name. It is not mandatory to use the same application name, it can be any valid name. 

   **URL**: If you know the exact URL where the application is hosted, you can mention it. If you are not aware, then you can mention your company URL. Valid URL name is mandatory in this field. 

   **Redirect Domains**: Enter the domain name of the application where you want the Learning Manager application to redirect after OAuth authentication. You can mention multiple URLs here but you have to use the valid URLs such as `http://google.com`, `http://yahoo.com` and so on. 

   **Description:** Enter the brief description for your application. 

   **Scopes:** Choose one of the four available options to define the scope of your application. Based on your choice mentioned here, Learning Manager API endpoint are accessible for your application. For example, If you chose **Learner role read access**, then all the Learning Manager learner API end points are read-only accessible to your application. 

   **For this account only?**   
   **Yes** - if you choose Yes, then the application is not visible to other account administrators.  
   **No** - if you choose No, other account admins can also access this application but they need to use the application id to access this application. Application id is generated and displayed in Learning Manager application Edit mode. 

   If you choose **Admin role read and write access** as scope while registering the application and choose **Admin role read access** while authoring the APIs, you can still have write access for the application as the app registration scope supersedes the authorization workflow. 

1. Click **[!UICONTROL Register]** at the upper-right corner after filling up the details in the registration page.

## Application development and testing {#applicationdevelopmentandtesting}

The Learning Manager API can be used by developers to build any application. Developers have to ensure that their accounts consist of some valid users and courses. They can create a few dummy users and courses and simulate activity in the trial account, so that they can test functionality of the application.

## Application deployment {#applicationdeployment}

We recommend that the Learning Manager Administrator or an Integration Administrator for the production account, to take ownership of making the application available to users within their organization. Once the application has been tested and is considered ready for production, inform the administrator of the production account. Ideally, the administrators want to generate a new client-id and client-secret for the application in the production account, and perform the necessary steps to incorporate them inside the application in a secure manner. The actual procedure for deploying applications varies from enterprise to enterprise, and the Learning Manager Administrator of your organization has to take support from the IT/IS department within your organization to complete the deployment.

## External application approval {#externalapplicationapproval}

You can add external applications by clicking **Approve** at the upper-right corner of the **Applications** page. Provide the external application id and click **Save.**

![](assets/add-external-application.png)

*Add and approve an external application*

## Frequently Asked Questions

+++Does Learning Manager have an E-commerce integration?

Adobe Learning Manager does not have an E-commerce integration. However, we provide APIs so that you can create your own headless LMS and implement E-commerce features.
+++
-->