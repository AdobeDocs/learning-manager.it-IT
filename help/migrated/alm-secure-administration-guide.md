---
title: Adobe Learning Manager - guida all'amministrazione sicura
description: Questa guida descrive le impostazioni di protezione, i ruoli e le procedure consigliate per la gestione della sicurezza amministrativa e del controllo degli accessi in Adobe Learning Manager al fine di garantire la conformità e la sicurezza.
jcr-language: en-us
exl-id: 67dd9334-9718-4b2a-841e-5d8bd5c42714
source-git-commit: 5682c45a4e5789a3eede53faf7cb257cd9685759
workflow-type: tm+mt
source-wordcount: '2354'
ht-degree: 0%

---

# Impostazioni di protezione amministrativa e implicazioni per la protezione

## Ruoli amministrativi con impatto sulla sicurezza

Adobe Learning Manager utilizza un modello di controllo di accesso basato sui ruoli. La tabella seguente mappa i livelli dei conti FedRAMP ai ruoli ALM a cui si fa riferimento in tutto il documento:

| Termine FedRAMP | Ruolo ALM | Rilevanza per la sicurezza |
|-------------|---------|------------------|
| Account amministrativo di primo livello | L’Amministratore | Controllo completo a livello di account. Accesso esclusivo a tutte le impostazioni relative alla protezione descritte nel presente documento. Questo è il ruolo a cui si fa riferimento in tutta la presente guida quando si utilizza il termine &quot;account amministrativo di primo livello&quot;. |
| Account con privilegi (ambito) | Amministratore personalizzato | Accesso amministrativo delegato con ambito a funzioni, gruppi di utenti o cataloghi specifici. Impossibile accedere alle impostazioni di protezione a livello di account se non esplicitamente consentito. |
| Account con privilegi (integrazione) | Amministratore di integrazione | Gestisce integrazioni, registrazioni API e configurazioni dei connettori. Privilegi elevati con ambito di gestione dell&#39;integrazione. Impossibile modificare altre impostazioni di protezione a livello di account. |

>[!NOTE]
>
>Solo gli utenti a cui sono stati assegnati esplicitamente questi ruoli possono modificare le impostazioni amministrative o relative alla sicurezza. Salvo diversa indicazione, le impostazioni documentate nelle Sezioni 3-7 sono accessibili esclusivamente al ruolo Amministratore.

## Impostazioni di accesso e autenticazione

Le impostazioni di accesso e autenticazione controllano il modo in cui tutti gli utenti, inclusi gli amministratori, accedono alla piattaforma ALM. Queste impostazioni sono configurate esclusivamente in base al ruolo di Amministratore e hanno un impatto diretto e significativo sulla posizione di sicurezza dell’intero account.

### Configurazione del metodo di accesso

**Posizione:** Amministratore ALM > Impostazioni > Metodi di accesso

L’Amministratore controlla il metodo di autenticazione utilizzato per tutti gli utenti interni ed esterni. Le opzioni disponibili includono:

- **Adobe ID:** Gli utenti eseguono l&#39;autenticazione tramite il proprio account di Adobe personale. Gestito da Adobe, non dall&#39;organizzazione.
- **Single Sign-On (SSO) tramite SAML 2.0:** Gli utenti si autenticano tramite il provider di identità (IdP) dell&#39;organizzazione. L&#39;organizzazione controlla completamente i criteri di autenticazione, MFA e sessione.
- **ID Learning Manager:** disponibile solo per utenti esterni. Gli utenti creano un nome utente e una password specifici della piattaforma.
- **Più configurazioni SSO:** è possibile aggiungere fino a 20 configurazioni SSO per supportare gruppi di utenti, posizioni o divisioni organizzative diverse

| Metodo di accesso | Implicazione sulla sicurezza | Consiglio |
|-------------|---------------------|----------------|
| **Adobe ID** | L&#39;organizzazione non ha alcun controllo sui criteri password, MFA o sul recupero dell&#39;account. Un account di Adobe personale compromesso consente l&#39;accesso alla piattaforma ALM. | **NON CONSIGLIATO** per utenti interni o amministrativi. Utilizzare solo quando SSO non è disponibile. |
| **SSO (SAML 2.0 / Federated ID)** | L’autenticazione è completamente controllata dall’IdP dell’organizzazione. MFA, timeout di sessione e criteri di accesso condizionale vengono applicati a livello IdP. Revoca immediata alla partenza dell&#39;utente. | **CONSIGLIATO** per tutti gli utenti e gli amministratori interni. Fornisce il massimo livello di controllo dell&#39;organizzazione. |
| **ID Learning Manager** | Gli utenti gestiscono autonomamente le password al di fuori dell&#39;infrastruttura di identità dell&#39;organizzazione. Impossibile applicare MFA tramite ALM. La robustezza della password dipende dal comportamento dell’utente. | Accettabile solo per utenti esterni. Non adatto a dipendenti o amministratori. |

>[!CAUTION]
>
>Se il metodo di accesso è impostato su Adobe ID per gli utenti interni, l&#39;organizzazione perde la possibilità di applicare l&#39;autenticazione a più fattori, controllare la complessità della password o revocare immediatamente l&#39;accesso quando un utente lascia l&#39;organizzazione. Ciò aumenta in modo significativo il rischio di accesso non autorizzato.

Per ulteriori informazioni, vedere [Ruoli personalizzati](https://experienceleague.adobe.com/en/docs/learning-manager/using/admin/custom-role).

### Autenticazione a più fattori (MFA)

**Posizione:** Adobe Admin Console > Impostazioni > Privacy e sicurezza > Impostazioni autenticazione

L&#39;imposizione MFA per gli utenti **Adobe ID** e **Enterprise ID** è configurata dall&#39;**amministratore di sistema** in Adobe Admin Console, non all&#39;interno dell&#39;applicazione ALM stessa.  Per gli utenti di **Federated ID/SSO**, l&#39;autenticazione a più fattori viene applicata al provider di identità dell&#39;organizzazione.

- **Imposizione di 2FA:** Gli utenti non possono disabilitare la verifica in due passaggi. Offre una protezione efficace contro il furto delle credenziali e il phishing.
- **2FA facoltativo:** gli utenti scelgono se abilitare la verifica in due passaggi. Posizione di sicurezza significativamente più debole.
- **MFA non configurato:** password proteggono l&#39;accesso da sole. Rischi elevati, in particolare per i conti amministrativi.

>[!IMPORTANT]
>
>I conti amministrativi senza AMF forzata sono esposti a un rischio significativamente più elevato di accesso non autorizzato. Una credenziale di amministratore compromessa senza MFA garantisce il controllo completo dell’account, inclusa la possibilità di modificare tutte le impostazioni di sicurezza.

### Durata della sessione e timeout di inattività

**Posizione:** Adobe Admin Console > Impostazioni > Privacy e sicurezza > Impostazioni avanzate

L&#39;**amministratore di sistema** configura la durata massima della sessione attiva e il timeout della sessione inattiva per l&#39;organizzazione. Queste impostazioni sono valide per tutti gli utenti, inclusi gli amministratori.

- **Durata massima della sessione:** impone la riautenticazione dopo un periodo definito indipendentemente dall&#39;attività. Limita la finestra di opportunità se una sessione è compromessa.
- **Tempo massimo di inattività:** Termina le sessioni inattive per un periodo definito. Protegge da sessioni autenticate automatiche su dispositivi condivisi o sbloccati.

## Impostazioni di ambito assegnazione ruoli e privilegi

Le impostazioni relative all&#39;assegnazione dei ruoli e all&#39;ambito dei privilegi determinano gli utenti che dispongono dell&#39;accesso amministrativo in ALM e le operazioni che possono eseguire. Queste sono tra le impostazioni di sicurezza con il maggiore impatto nella piattaforma. Solo il ruolo Amministratore può creare, assegnare, modificare o revocare ruoli amministrativi.

### Assegnazione ruolo amministrativo

**Posizione:** Amministratore ALM > Utenti > Interno > Azioni > Assegna ruolo / Rimuovi ruolo

L&#39;**Amministratore** può concedere o revocare i seguenti ruoli:

- **Amministratore:** accesso completo a livello di account
- **Autore:** accesso alla creazione di contenuti
- **Amministratore personalizzato:** Accesso amministrativo con ambito (vedere sezione 4.2)
- **Amministratore di integrazione:** integrazione e accesso API (vedere la sezione 7)

| Impostazione/Azione | Implicazione sulla sicurezza | Esercitazione consigliata |
|---|---|---|
| **Concessione del ruolo di amministratore** | Controllo completo dell&#39;account. Un utente con questo ruolo può modificare tutte le impostazioni in questo documento, inclusa la riconfigurazione dell&#39;autenticazione e la revoca dell&#39;accesso di altri amministratori. | Assegna l&#39;assegnazione solo a un numero minimo di utenti con esigenze aziendali verificate. Gestisce un elenco documentato di tutti i titolari del ruolo di amministratore. |
| **Impossibile revocare i ruoli alla partenza** | Gli utenti che non hanno accesso alle funzioni amministrative. Rischio di accesso non autorizzato, di exfiltrazione dei dati o di sabotaggio. | Rimuovere immediatamente i ruoli quando le responsabilità di un utente relative a un impiego o a un&#39;amministrazione cambiano. Eseguire revisioni periodiche degli accessi. |
| **Sovra-assegnazione ruoli ampi** | Un ampio accesso amministrativo aumenta il potenziale impatto di un account compromesso e riduce la responsabilità per le azioni amministrative. | Applicare il principio del minimo privilegio. Se possibile, preferisci ruoli con ambito (ad esempio, Amministratore personalizzato). |

### Configurazione personalizzata del ruolo amministrativo

**Posizione:** Amministratore ALM > Utenti > Ruoli personalizzati > Crea ruolo

Applicare il principio di **privilegio minimo**. Utilizzare i ruoli **Amministratore personalizzato** per delegare funzioni specifiche (vedere la sezione 4.2).

L&#39;**amministratore** può creare ruoli personalizzati che concedono un sottoinsieme definito di autorizzazioni amministrative. I ruoli personalizzati possono essere assegnati a gruppi di utenti, cataloghi o set di funzioni specifici, limitando la portata dell’accesso amministrativo delegato.

**Le categorie di autorizzazioni disponibili includono:**

- **Privilegi dell&#39;account:** accesso a configurazioni a livello di sistema come annunci, gamification, abilità e gestione degli utenti.
- **Privilegi di funzionalità (core):** Accesso a cataloghi, report e tag.
- **Privilegi delle funzioni (oggetti di apprendimento):** Accesso a corsi, certificazioni, percorsi di apprendimento e risorse formative.
- **Ambito:** Limita il ruolo a gruppi di utenti e/o cataloghi specifici.

| Decisione di configurazione | Implicazione sulla sicurezza | Esercitazione consigliata |
|---|---|---|
| **Creazione di un ruolo personalizzato troppo ampio** | Un ruolo personalizzato con privilegi eccessivi offre pochi vantaggi in termini di sicurezza rispetto al ruolo Amministratore completo e aumenta il raggio di esplosione di un account compromesso. | Assegnare l&#39;ambito dei ruoli personalizzati al set minimo di autorizzazioni necessarie per la funzione specifica. Preferisci ruoli con ambito catalogo e ambito gruppo utente. |
| **Concessione dell&#39;accesso alle impostazioni a un amministratore personalizzato** | Gli amministratori personalizzati con accesso alle impostazioni possono modificare i metodi di accesso, le impostazioni di notifica e altre configurazioni a livello di account. | Concedi l’accesso alle Impostazioni solo ai ruoli personalizzati quando esplicitamente richiesto. Controllare regolarmente i ruoli personalizzati che dispongono di questo privilegio. |
| **Impossibile controllare le assegnazioni di ruoli personalizzate** | I ruoli personalizzati non documentati o non revisionati possono accumularsi nel tempo, determinando lo slittamento dei privilegi. | Scarica periodicamente il report del ruolo personalizzato (**Utenti > Ruoli personalizzati > Scarica**) ed esamina tutte le assegnazioni di ruolo personalizzate attive. |

## Impostazioni di provisioning degli utenti e gestione degli accessi

Le impostazioni di provisioning degli utenti controllano il modo in cui gli utenti vengono aggiunti alla piattaforma, la durata della loro attività e la rimozione dei dati. Queste impostazioni sono configurate esclusivamente dal ruolo Amministratore e hanno implicazioni dirette sulla sicurezza per l’esposizione dei dati e il controllo degli accessi.

| Impostazione | Posizione | Implicazione sulla sicurezza | Valore predefinito consigliato |
|---|---|---|---|
| **Eliminazione automatica utente non attivo** | Amministratore ALM > Impostazioni > Generale | Senza eliminazione automatica, gli account inattivi si accumulano. Gli account inattivi sono una destinazione comune per l’accesso non autorizzato perché potrebbero non essere monitorati. | Abilita. Impostare un periodo di conservazione allineato ai criteri dell&#39;organizzazione, ad esempio 90 giorni di inattività. |
| **Scadenza profilo utente esterno** | Amministratore ALM > Utenti > Esterno > Aggiungi profilo | I profili utente esterni senza data di scadenza rimangono accessibili a tempo indeterminato. I partner o i fornitori che non richiedono più l&#39;accesso mantengono un punto di accesso attivo. | Imposta una data di scadenza su ogni profilo utente esterno al momento della creazione. |
| **Controlli del collegamento per registrazione autonoma** | Amministratore ALM > Utenti > Interno > Aggiungi > Registrazione autonoma | Un collegamento di registrazione autonoma consente a qualsiasi utente che dispone dell’URL di creare un account Allievo. Se non gestita, questa operazione può causare l&#39;accesso alla piattaforma da parte di utenti non autorizzati o imprevisti. | Genera collegamenti di registrazione autonoma solo quando necessario. Disattiva o revoca immediatamente i collegamenti inutilizzati. |
| **Pausa/Riprendi profilo esterno** | Amministratore ALM > Utenti > Esterni > Azioni > Pausa | La sospensione di un profilo esterno impedisce la registrazione ai nuovi utenti, ma non influisce su quelli già registrati. La mancata sospensione dei profili esterni inattivi può consentire registrazioni non intenzionali. | Metti in pausa i profili esterni quando la registrazione non è più necessaria. Elimina i profili inattivi in modo permanente. |
| **Eliminazione ed eliminazione degli utenti** | Amministratore ALM > Utenti > Interno > Azioni > Elimina / Pulizia utente > Rimuovi | Gli utenti eliminati sono disattivati ma i loro dati vengono mantenuti. La rimozione definitiva rimuove tutti i dati utente. La mancata rimozione degli utenti rimossi può mantenere i record di apprendimento sensibili e i dati identificativi oltre il periodo di conservazione richiesto. | Rimozione dei record utente in linea con le politiche aziendali sulla privacy e sulla conservazione dei dati. La rimozione è irreversibile. |

>[!IMPORTANT]
>
>La rimozione è permanente e irreversibile. Tutti i record della formazione, i dati di iscrizione e le informazioni utente vengono eliminati. Se nelle configurazioni dei connettori viene fatto riferimento a un utente rimosso, tali connettori verranno disattivati. Confermare attentamente la selezione prima di eseguire una rimozione.

## Impostazioni di reporting e accesso ai dati

Le impostazioni di reporting e accesso ai dati determinano quali utenti possono visualizzare, generare ed esportare i dati della piattaforma. Una configurazione errata di queste impostazioni può comportare l&#39;esposizione di informazioni riservate personali, dell&#39;organizzazione o relative alla conformità.

| Impostazione | Posizione | Implicazione sulla sicurezza | Valore predefinito consigliato |
|---|---|---|---|
| **Concessione dell&#39;accesso al report ai ruoli personalizzati** | Amministratore ALM > Utenti > Ruoli personalizzati > Privilegi di funzionalità > Report | I report possono contenere informazioni personali, dati di completamento del corso, punteggi di valutazione e progressi dell’Allievo. L’accesso alle funzionalità di reporting deve essere limitato agli utenti con esigenze aziendali verificate. | Concedere l&#39;accesso ai report solo ai ruoli con esigenze specifiche e documentate. Utilizzare l&#39;accesso in sola lettura in cui non è richiesto l&#39;accesso in scrittura. |
| **Controllo completo e ambito del report di sola lettura** | Amministratore ALM > Utenti > Ruoli personalizzati > Report di riepilogo account | Il report di riepilogo Controllo completo sull’account garantisce la visibilità di amministratore personalizzato a tutti i gruppi di utenti e i cataloghi, indipendentemente dal loro ambito di ruolo. Ciò può esporre dati al di fuori dell’ambito previsto di un ruolo di amministratore con ambito. | Concedere il controllo completo sul report di riepilogo dell&#39;account solo ai ruoli che effettivamente richiedono visibilità di reporting a livello di organizzazione. |
| **Accesso a xAPI e report e-mail** | Amministratore ALM > Utenti > Ruoli personalizzati | I report xAPI e i report e-mail sono disponibili solo per il ruolo di amministratore completo. Questi report possono contenere dati comportamentali e di comunicazione dettagliati. L&#39;accesso è limitato dalla progettazione. | Non tentare di delegare l’accesso al report xAPI o e-mail tramite ruoli personalizzati. Si tratta di una soluzione progettata solo per gli Amministratori. |
| **Dati utente esportati** | Amministratore ALM > Utenti > Interno > Esporta dati utente | La funzione Esporta dati utente genera un file scaricabile contenente tutti i record utente interni. Questi dati devono essere gestiti in conformità con le politiche di sicurezza e privacy dell&#39;organizzazione. | Limitare la capacità di esportazione al personale autorizzato. Considera i dati esportati come sensibili. Non archiviarlo o trasmetterlo al di fuori dei sistemi approvati. |

## Impostazioni di integrazione e accesso API

Le impostazioni di integrazione e accesso API controllano la modalità di connessione dei sistemi esterni a Adobe Learning Manager. Queste impostazioni estendono l&#39;accesso oltre l&#39;interfaccia utente ALM e, se non configurate correttamente, possono esporre i dati e le funzionalità della piattaforma a sistemi non autorizzati.  Le impostazioni di integrazione sono gestite dal ruolo Amministratore di integrazione. Il ruolo di amministratore completo conserva la possibilità di rivedere, approvare e revocare le applicazioni registrate.

| Impostazione | Posizione | Implicazione sulla sicurezza | Valore predefinito consigliato |
|---|---|---|---|
| **Registrazione applicazione API** | Amministratore dell’integrazione > Applicazioni > Registrazione | La registrazione di un&#39;applicazione crea credenziali OAuth 2.0 (ID client e segreto) che possono essere utilizzate per accedere ai dati e alle funzioni ALM a livello di programmazione. Gli ambiti OAuth troppo ampi (ad esempio, ruolo di amministratore in lettura/scrittura) concedono l’accesso completo all’API amministrativa. | Concedere il numero minimo di ambiti OAuth richiesti. Rivedere e revocare periodicamente le registrazioni di applicazioni inutilizzate o legacy. Considera le credenziali client come segreti riservati. |
| **Ambito applicazione OAuth** | Amministratore dell’integrazione > Applicazioni > Registra > Ambiti | Gli ambiti OAuth disponibili variano dall’accesso in lettura dell’Allievo all’accesso in lettura/scrittura dell’Amministratore. La lettura/scrittura del ruolo di amministratore consente a un&#39;applicazione di modificare tutti i dati che un amministratore può modificare, inclusi i ruoli utente e le impostazioni di protezione. | Utilizza l’ambito OAuth più restrittivo che soddisfi i requisiti dell’integrazione. Non concedere mai al ruolo di amministratore l&#39;accesso in lettura/scrittura a meno che non sia strettamente necessario. |
| **Configurazione del connettore (FTP, Salesforce, HRIS, ecc.)** | Amministratore dell’integrazione > Connettori | I connettori consentono l’importazione e l’esportazione automatizzate di dati utente, abilità e completamenti del corso. Connettori non configurati correttamente possono importare dati utente errati, assegnare ruoli indesiderati o esportare dati sensibili a destinazioni non autorizzate. | Rivedi periodicamente tutte le configurazioni attive del connettore. Assicurarsi che le origini dati e le destinazioni siano autorizzate. Disattiva i connettori non più in uso. |
| **Configurazione webhook** | Amministratore dell’integrazione > Webhook | I webhook inviano dati di eventi ALM in tempo reale (iscrizioni, completamenti, modifiche dell&#39;utente) a un URL esterno specificato. Un endpoint del webhook non configurato o compromesso può comportare l’exfiltrazione di dati o l’esposizione di eventi sensibili dell’Allievo. | Registra solo URL webhook verificati e approvati dall’organizzazione. Verifica regolarmente le configurazioni attive del webhook. Rimuovi immediatamente i webhook inattivi o non riconosciuti. |
| **Configurazione integrazione LTI** | Amministratore dell’integrazione > Integrazioni LTI | L’integrazione LTI consente ad ALM di agire come fornitore o consumatore di LTI, consentendo alle piattaforme LMS esterne di accedere ai corsi ALM. Una volta attivato, l’LTI non può essere disattivato. Le credenziali LTI esposte possono consentire l’accesso non autorizzato al contenuto del corso. | Abilita LTI solo se esiste un requisito di integrazione verificato. Considera le credenziali LTI come riservate. Condividere le credenziali solo con amministratori LMS autorizzati. |

## Responsabilità di configurazione amministrativa e responsabilità condivisa

Le impostazioni amministrative di Adobe Learning Manager sono configurabili dai clienti e fanno parte dei controlli di sicurezza gestiti dal cliente secondo il modello di responsabilità condivisa di Adobe.

| Responsabilità dell&#39;Adobe | Responsabilità del cliente |
|---|---|
| Funzionamento sicuro della piattaforma ALM e dell&#39;infrastruttura sottostante. | Configurazione di tutti i ruoli amministrativi e delle autorizzazioni. |
| Applicazione del modello di controllo di accesso basato sui ruoli. | Selezione e applicazione dei metodi di accesso appropriati e dell&#39;MFA. |

Ulteriori informazioni sulle procedure di sicurezza di Adobe Learning Manager sono disponibili in:

**Riferimento:** [Panoramica sulla sicurezza di Adobe Learning Manager (PDF)](https://experienceleague.adobe.com/docs/learning-manager/assets/alm-security-whitepaper-2024.pdf)

## Manutenzione documento

Questo documento può essere aggiornato periodicamente per riflettere le modifiche apportate alle funzionalità di Adobe Learning Manager o alle linee guida sulla sicurezza. La versione e la data dell’ultimo aggiornamento vengono mantenute nei metadati del documento e nel pacchetto di autorizzazione FedRAMP. I clienti devono fare riferimento alla versione pubblicamente disponibile su Adobe Experience League per assicurarsi di utilizzare le indicazioni più aggiornate.
