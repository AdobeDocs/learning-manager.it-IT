---
description: Informazioni sul metodo di accesso OIDC
jcr-language: en_us
title: Accedi a Adobe Learning Manager con OpenID Connect
source-git-commit: 7c430e3fbb2716455310f2130d73af10ce2e56c7
workflow-type: tm+mt
source-wordcount: '1402'
ht-degree: 0%

---


# Accedi a Adobe Learning Manager con OpenID Connect (OIDC)

Scopri come funziona l’accesso a OpenID Connect in Adobe Learning Manager per Allievi, Autori e Amministratori. Questo articolo riguarda l&#39;esperienza, non l&#39;attuazione.

## Informazioni sull’accesso a OpenID Connect

OpenID Connect (OIDC) è un metodo di accesso comune basato su standard Web. Molte organizzazioni utilizzano un provider di identità (ad esempio, Okta, Google Workspace o Microsoft Entra ID) per dipendenti e partner.

Quando la tua organizzazione abilita OIDC per Adobe Learning Manager:

* Accedi utilizzando la pagina di accesso abituale della tua organizzazione, non una password che si applica solo a Adobe Learning Manager, a meno che la tua organizzazione non scelga diversamente.
* Dopo l’autenticazione, Adobe Learning Manager riceve le informazioni consentite dalla tua organizzazione (come l’indirizzo e-mail e gli attributi del profilo) e apre l’esperienza giusta per te: Allievo, Autore, Amministratore o altri ruoli supportati dal tuo account.

OIDC è un&#39;alternativa ad altre opzioni di accesso che il tuo account può offrire, come Adobe ID o SSO basato su SAML. L&#39;amministratore decide i metodi disponibili.

## Perché le organizzazioni scelgono OpenID Connect

Le organizzazioni spesso scelgono OIDC per i seguenti motivi:

* Gli utenti visualizzano la stessa esperienza di identità aziendale o cloud che utilizzano per altre applicazioni.
* Le policy per le password, l&#39;autenticazione a più fattori e il ciclo di vita dell&#39;account sono gestiti nel provider di identità, in modo coerente con le altre app aziendali.
* OIDC segue pattern simili ad altri flussi di accesso moderni da una prospettiva utente e IT, senza lo scambio di documenti più pesante associato ad alcune configurazioni solo SAML.

La tua esperienza è ancora: accedi a Learning Manager, accedi dove ti dice la tua organizzazione e accedi all’app.

## Cosa vedi quando accedi

### Apri Adobe Learning Manager

È possibile utilizzare:

* URL principale di Adobe Learning Manager per l&#39;ambiente in uso
* Un dominio personalizzato configurato dall’organizzazione, se applicabile
* Un collegamento da una pagina di e-mail, invito o registrazione autonoma
* Un segnalibro o un collegamento diretto a un corso, a una pagina di catalogo o a una risorsa specifici

Se il tuo account utilizza OIDC, l&#39;avvio dell&#39;accesso in genere reindirizza il browser al provider di identità dell&#39;organizzazione.

### Accedi con la tua organizzazione

Nella pagina del provider di identità, immetti le tue credenziali e completa tutti i passaggi aggiuntivi richiesti dalla tua organizzazione, ad esempio l&#39;autenticazione a più fattori. Questo passaggio si verifica all&#39;esterno del modulo di accesso di Adobe Learning Manager quando OIDC è il metodo in uso. Dal tuo punto di vista, ti sembra di accedere al tuo account aziendale o scolastico. Durante questo passaggio potresti non visualizzare termini tecnici come *OIDC* o *OAuth*.

### Torna a Adobe Learning Manager

Dopo aver effettuato correttamente l’accesso, il browser torna a Adobe Learning Manager. Il prodotto:

* Riconosce l&#39;utente utilizzando le informazioni sull&#39;indirizzo e-mail e sul profilo condivise dal provider di identità, in base alle impostazioni dell&#39;organizzazione
* Applica le autorizzazioni in Adobe Learning Manager (Allievo, Autore, Amministratore, Amministratore di integrazione e così via).
* Apre l’app o l’area appropriata (ad esempio, l’esperienza dell’Allievo rispetto all’esperienza dell’Amministratore o dell’Autore), in linea con il modo in cui Adobe Learning Manager assegna i ruoli all’account

Se si verifica un errore (ad esempio, se il provisioning dell&#39;account non viene eseguito o l&#39;organizzazione blocca l&#39;accesso), potresti riscontrare un errore o non essere in grado di procedere. Contatta il tuo team IT interno o l&#39;amministratore Adobe Learning Manager.

## Usa altre opzioni di accesso con OpenID Connect

Adobe Learning Manager può supportare più di un metodo di accesso per un account (più opzioni SSO). Ad esempio:

* Alcuni utenti accedono con Adobe ID
* Altri utilizzano SAML SSO
* Altri utilizzano OIDC

Le opzioni visualizzate dipendono dalla configurazione dell’account. L&#39;abilitazione di OIDC per l&#39;organizzazione non rimuove di per sé altri metodi, a meno che gli amministratori non modifichino tale configurazione.

## Funzioni e scenari supportati

I seguenti comportamenti sono supportati quando la tua organizzazione utilizza OIDC con Adobe Learning Manager, in linea con il funzionamento previsto di altri metodi di accesso enterprise.

### Tabella 1. Supporto OIDC in scenari comuni

| Area | Cosa significa per te |
| --- | --- |
| Utenti interni ed esterni | I dipendenti e gli utenti esterni invitati (ad esempio, i partner) possono utilizzare OIDC dove è abilitato dall’amministratore, inclusi i flussi che partono dai collegamenti di registrazione autonoma quando l’account è configurato per tale scopo. |
| Primo accesso | Se sei autorizzato dalla policy, il tuo primo accesso OIDC riuscito può creare o collegare il tuo utente in Adobe Learning Manager in base alle regole della tua organizzazione, in modo simile ad altre opzioni SSO. |
| Profilo e attributi | Informazioni quali e-mail e altri attributi possono essere aggiornate dal provider di identità nel tempo, in modo che il profilo Adobe Learning Manager rimanga allineato con la directory dell&#39;organizzazione, all&#39;interno di quanto configurato dall&#39;amministratore. |
| Collegamenti diretti | Sono supportati i collegamenti che puntano a una pagina o risorsa specifica in Learning Manager (non solo alla home page). Puoi accedere ai contenuti desiderati dopo l&#39;accesso, quando la configurazione dell&#39;organizzazione lo consente. |
| Percorso di ritorno | Dopo l’autenticazione, puoi tornare al punto in cui stavi tentando di raggiungere (ad esempio, lo stesso corso o URL del catalogo da cui hai iniziato), anziché atterrare sempre su una home page generica. |
| Dominio personalizzato | Se la tua azienda utilizza un nome host personalizzato per Adobe Learning Manager, l&#39;accesso OIDC è supportato anche in tale contesto. |
| Dispositivi mobili | È possibile accedere su telefoni e tablet tramite i browser o le esperienze supportati. |
| Da Publish a Adobe Learning Manager (Prime) | I flussi di lavoro che comportano la pubblicazione di contenuti in Learning Manager da strumenti connessi restano supportati quando l’account utilizza OIDC, in modo coerente con la configurazione dell’integrazione. |
| Accesso basato su identificatori | Se il tuo account si basa su identificatori stabili (oltre alla sola e-mail) per gli account corrispondenti, quei flussi sono supportati per OIDC in base alla configurazione dell&#39;amministratore. |

Se un flusso di lavoro specifico non funziona, la causa potrebbe essere dovuta alle impostazioni del provider di identità, al provisioning dell&#39;account o all&#39;assegnazione del ruolo Adobe Learning Manager. L&#39;amministratore può verificare.

## Funzionamento dei ruoli dopo l&#39;accesso

Adobe Learning Manager determina le operazioni che puoi eseguire dai ruoli e dalle autorizzazioni del tuo account, non dal protocollo OIDC stesso. OIDC stabilisce solo chi sei in grado di soddisfare il tuo provider di identità e cosa la tua organizzazione condivide con Adobe Learning Manager.

* Gli Allievi visualizzano in genere corsi di formazione, cataloghi e piani di apprendimento.
* Gli Autori possono creare o curare contenuti.
* Gli amministratori gestiscono gli utenti, la configurazione e i report.

Se ti trovi in un&#39;area sbagliata o non riesci ad accedere, chiedi al tuo amministratore Adobe Learning Manager di controllare il tuo profilo e l&#39;iscrizione al gruppo.

## Risoluzione dei problemi comuni

### Tabella 2. Risoluzione dei problemi di accesso OIDC

| Problema | Cosa provare |
| --- | --- |
| Ripetizione del reindirizzamento o pagina vuota | Cancella i cookie per l’URL e il provider di identità di Learning Manager, prova con un altro browser o prova una finestra privata. Se il problema persiste, contatta l’IT. I proxy aziendali o le policy delle sessioni del provider di identità a volte interferiscono. |
| &quot;Accesso negato&quot; o simile dopo l&#39;accesso al provider di identità | Il tuo provider di identità ti ha accettato, ma Adobe Learning Manager potrebbe non avere un utente corrispondente o il tuo account potrebbe non disporre di una licenza o di un ruolo. Contatta il tuo amministratore Adobe Learning Manager. |
| Lingua o dettagli del profilo errati | La mappatura degli attributi è controllata dalla tua organizzazione. Chiedere all&#39;amministratore se gli attributi della directory devono guidare i campi delle impostazioni internazionali o dei profili. |
| Deep link ha aperto la home page invece della risorsa | Il comportamento di Return-path e deep-link può dipendere da come è stato condiviso il collegamento e dalla sessione. Riprova il collegamento dopo un accesso completo o chiedi al tuo amministratore se il formato del collegamento è supportato per gli utenti esterni. |

## Cosa devono sapere gli amministratori

Se configuri Adobe Learning Manager per la tua organizzazione, OIDC viene configurato con la registrazione dell&#39;applicazione del provider di identità: identificativi dei client, endpoint per l&#39;autorizzazione, token, informazioni sull&#39;utente e URL di reindirizzamento utilizzato da Adobe Learning Manager per completare l&#39;accesso. Tali valori provengono dalla documentazione del provider di identità. Le impostazioni devono corrispondere tra il provider di identità e Learning Manager in modo che gli utenti vedano un reindirizzamento e un ritorno fluidi.

Gli utenti finali non devono gestire tali valori. Hanno bisogno solo dell’URL di Learning Manager (o dominio personalizzato) corretto e, se applicabile, dei collegamenti di invito o registrazione autonoma del team.

## Riepilogo

* OIDC consente agli utenti di accedere a Adobe Learning Manager tramite il provider di identità standard della propria organizzazione, con un flusso familiare di reindirizzamento e restituzione.
* Dopo l’accesso, Adobe Learning Manager utilizza l’e-mail e gli attributi condivisi per identificare l’utente e applicare i ruoli (Allievo, Autore, Amministratore e così via).
* In base alla configurazione dell’account, sono supportati la registrazione autonoma, più opzioni SSO, aggiornamenti degli attributi, provisioning degli utenti per la prima volta, collegamenti diretti, percorso di ritorno, domini personalizzati, dispositivi mobili, da Publish a Adobe Learning Manager e corrispondenza basata su identificatori.
* Altri metodi di accesso (ad esempio Adobe ID o SAML) rimangono disponibili quando gli amministratori li mantengono abilitati.
