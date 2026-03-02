---
title: Ciclo di vita dell'account amministrativo Adobe Learning Manager
description: Questo documento fornisce una guida completa sulla gestione sicura degli account amministrativi di primo livello in Adobe Learning Manager (ALM) per soddisfare la conformità FedRAMP e le migliori procedure di sicurezza.
jcr-language: en-us
source-git-commit: db3ed4dc44da75b418e923999bdf3776bf81b11f
workflow-type: tm+mt
source-wordcount: '2122'
ht-degree: 0%

---


# Tipi di account amministrativi in Adobe Learning Manager

## Mapping ruoli ALM

In Adobe Learning Manager, l’account amministrativo di primo livello è il ruolo Amministratore. Questo è il ruolo a cui si fa riferimento ogni volta che questa guida utilizza il termine FedRAMP &#39;account amministrativo di primo livello&#39;. Gli Amministratori personalizzati e gli Amministratori di integrazione vengono trattati come account con privilegi (con ambito).

La tabella seguente mappa i livelli dell&#39;account FedRAMP ai ruoli specifici utilizzati in Adobe Learning Manager:

| Termine FedRAMP | Nome ruolo ALM | Descrizione |
|--------------------------------------|----------------------------|-------------|
| Account amministrativo di primo livello | L’Amministratore | Ruolo di massimo privilegio in ALM. Controllo completo su utenti, ruoli, contenuti di apprendimento, report, integrazioni e tutte le configurazioni di sistema. Mapping diretto alla definizione di account amministrativo di livello superiore FedRAMP. |
| Account con privilegi (ambito) | Amministratore personalizzato | Un sottoinsieme definito di autorizzazioni di amministratore con ambito di funzioni specifiche (ad esempio, creazione di report, gestione dei cataloghi). Non dispone del controllo completo a livello di account. |
| Account con privilegi (integrazione) | Amministratore di integrazione | Gestisce le integrazioni e l&#39;accesso basato su API tra ALM e sistemi esterni. Privilegi elevati con ambito solo per la gestione dell’integrazione. |


Per gestire l&#39;accesso amministrativo, Adobe Learning Manager utilizza un modello di controllo di accesso basato sui ruoli. I ruoli amministrativi vengono assegnati solo da amministratori autorizzati.

Per ulteriori informazioni, vedere [Ruoli personalizzati in Adobe Learning Manager](https://experienceleague.adobe.com/it/docs/learning-manager/using/admin/custom-role)

## Tipi di identità e autenticazione consigliata

Adobe Admin Console supporta tre tipi di identità per gli account amministratore. La scelta del tipo di identità ha implicazioni dirette sulla sicurezza:

| Tipo identità | Descrizione | Consiglio di sicurezza |
|---------------------------|-----------------------------------------------------------------------------|------------------------------------------------------------------------------------------|
| Adobe ID (ID personale) | Tipo predefinito; gestito da Adobe. Chiunque può crearne una. | NON CONSIGLIATO per gli amministratori. L&#39;organizzazione non ha alcun controllo su questo tipo di account. |
| Enterprise ID | Account di proprietà dell&#39;organizzazione gestito da un amministratore di sistema Admin Console. | Accettabile se Federated ID/SSO non è disponibile. Applicare 2FA. |
| Federated ID (SSO) | Di proprietà dell&#39;organizzazione; integrato con SAML 2.0 SSO. L&#39;organizzazione controlla completamente l&#39;autenticazione. | CONSIGLIATO. Autentica tramite l’IdP dell’organizzazione; supporta l’imposizione di MFA a livello di provider di identità. |

Per ulteriori informazioni, consultate i seguenti riferimenti:

* [Tipi di identità](https://helpx.adobe.com/it/enterprise/using/admin-console.html)
* [Autenticazione utente e password sicure](https://helpx.adobe.com/it/enterprise/using/authentication-settings.html)

## Assegnazione dei ruoli e controllo di accesso

L&#39;accesso agli account amministrativi in Adobe Learning Manager è controllato tramite l&#39;assegnazione esplicita del [ruolo](https://experienceleague.adobe.com/it/docs/learning-manager/using/admin/user-management/add-users-user-groups) da un amministratore esistente. Le caratteristiche principali di un accesso amministrativo sicuro includono:

* I ruoli amministrativi vengono assegnati solo da amministratori autorizzati.
* L&#39;accesso è basato sui ruoli e ha un ambito in base alle autorizzazioni assegnate.
* Le organizzazioni sono responsabili della limitazione dell&#39;accesso amministrativo agli utenti con esigenze aziendali legittime.

L&#39;Adobe consiglia ai clienti di verificare periodicamente l&#39;accesso amministrativo per garantire il rispetto del principio del privilegio minimo.

## Richiedi Multi-Factor Authentication (MFA)

Adobe consiglia vivamente agli amministratori di applicare la verifica in due passaggi (2FA) a livello di organizzazione. La funzione MFA si applica agli utenti di Enterprise ID e Adobe ID. Agli utenti del Federated ID deve essere applicata l&#39;autenticazione basata su conoscenza presso il provider di identità dell&#39;organizzazione.

Per applicare 2FA in Adobe Admin Console:

1. Accedi a Adobe Admin Console.
2. Passa a Impostazioni > Privacy e sicurezza > Impostazioni di autenticazione.
3. Attiva la verifica in due passaggi e seleziona l&#39;opzione Applica per impedire agli utenti di disabilitarla.
4. Facoltativamente, è possibile configurare le restrizioni di accesso basate su IP e le impostazioni di sessione avanzate (Durata massima della sessione / Tempo massimo di inattività).

>[!IMPORTANT]
>
>L’Adobe consiglia di applicare 2FA e di non lasciarla facoltativa agli utenti. L’applicazione di 2FA può richiedere fino a 24 ore. Per gli utenti di Federated ID, applica l&#39;autenticazione basata su conoscenza al provider di identità.

Per ulteriori informazioni, vedere [Autenticazione sicura dell&#39;utente](https://helpx.adobe.com/it/enterprise/using/authentication-settings.html).


## Accedi come amministratore

ALM [Gli amministratori](https://experienceleague.adobe.com/it/docs/learning-manager/using/get-started/getting-started-admin) accedono direttamente alla piattaforma ALM utilizzando le credenziali dell&#39;organizzazione gestite tramite l&#39;Admin Console.

### Assegnare un ruolo di amministratore

All&#39;interno della piattaforma ALM, gli amministratori configurano l&#39;accesso amministrativo creando e gestendo ruoli, assegnando autorizzazioni agli utenti e definendo l&#39;ambito delle autorizzazioni in base alle responsabilità operative.

Per assegnare il ruolo Amministratore in ALM:

1. Accedi a Adobe Learning Manager come amministratore esistente.
2. Seleziona Utenti > Interno.
3. Cerca o seleziona l’utente di destinazione.
4. Seleziona Azioni > Assegna ruolo > Crea amministratore.

I ruoli amministrativi personalizzati consentono ai clienti di delegare le attività amministrative mantenendo al contempo il controllo centralizzato sui privilegi a livello di account. Gli amministratori personalizzati possono essere assegnati a specifici gruppi di utenti o cataloghi.

Per ulteriori informazioni, vedere [Aggiungere utenti e gruppi di utenti](https://experienceleague.adobe.com/it/docs/learning-manager/using/admin/user-management/add-users-user-groups).

## Configurazione dei metodi di accesso e di SSO

Gli amministratori ALM controllano i metodi di accesso disponibili per tutti gli utenti tramite Impostazioni > Metodi di accesso, una configurazione critica che riguarda la sicurezza:

* **Utenti interni**: imposta la modalità di accesso su Adobe ID o Single Sign-On (SSO). SSO tramite SAML 2.0 è fortemente consigliato.
* **Utenti esterni**: imposta la modalità di accesso su Adobe ID, SSO o ID Learning Manager. Allineare il metodo selezionato ai criteri di sicurezza dell&#39;organizzazione.

L’Adobe consiglia di utilizzare Federated ID/SAML 2.0 SSO come metodo di accesso per tutti gli utenti interni. Ciò garantisce il pieno controllo dell&#39;autenticazione da parte del provider di identità dell&#39;organizzazione, consentendo l&#39;applicazione centralizzata di MFA e la revoca immediata dell&#39;account alla partenza dell&#39;utente.

Per ulteriori informazioni, vedere [Impostazioni](https://experienceleague.adobe.com/it/docs/learning-manager/using/admin/settings).

## Impostazioni predefinite sicure consigliate per il provisioning

Quando viene eseguito il primo provisioning di un account ALM, Adobe consiglia di verificare le seguenti impostazioni predefinite prima di concedere l&#39;accesso operativo a qualsiasi utente amministrativo:

| Impostazione | Impostazione predefinita protetta consigliata | Dove configurare |
|------------------------------|------------------------------------------------------------------|-------------------------------------------------|
| Metodo di accesso — utenti interni | Single Sign-On (SSO) / Federated ID | ALM > Impostazioni > Metodi di accesso |
| Verifica in due fasi (2FA) | Applicato (non facoltativo per nessun utente) | Admin Console > Impostazioni > Privacy e sicurezza |
| Durata massima della sessione | Criteri per 8 ore o per organizzazione | Admin Console > Impostazioni > Impostazioni avanzate |
| Tempo di inattività massimo | 30 minuti o per policy dell&#39;organizzazione | Admin Console > Impostazioni > Impostazioni avanzate |
| Ambito del ruolo di amministratore | Meno privilegio; utilizzare i ruoli di amministratore personalizzato, ove possibile | ALM > Utenti > Ruoli personalizzati |
| Scadenza utente esterno | Impostare una data di scadenza per ogni profilo utente esterno | ALM > Utenti > Esterno |

### Elenco di controllo per la configurazione iniziale di nuovi amministratori

Quando effettui il provisioning di un nuovo account amministratore di primo livello, completa quanto segue prima di concedere l&#39;accesso operativo:

* Verifica che il tipo di identità sia Enterprise ID o Federated ID, non Adobe ID personale.
* Imponi 2FA a livello di Admin Console (Impostazioni > Impostazioni di autenticazione).
* Se non è già abilitato, configura SSO/Federated ID.
* Imposta Durata massima della sessione e Tempo massimo di inattività in Admin Console > Impostazioni > Impostazioni avanzate.
* Limita ambito ruolo di amministratore: assegna solo le autorizzazioni necessarie per le responsabilità dell’utente.
* Verifica che l’account amministratore sia associato a un indirizzo e-mail dell’organizzazione controllato dal team IT.
* Documentare l&#39;account nel registro di accesso privilegiato dell&#39;organizzazione.

## Gestione della contabilità amministrativa

### Attività amministrative quotidiane

Gli account amministrativi vengono utilizzati per eseguire attività operative quotidiane, tra cui:

* **Gestione del ciclo di vita degli utenti**: creazione di utenti, aggiornamento dei profili e modifica dei ruoli.
* **Gestione dei contenuti di apprendimento**: gestione di corsi, programmi di apprendimento, certificazioni e cataloghi.
* **Creazione di report e analisi**: generazione e revisione di report sull&#39;avanzamento degli Allievi e sull&#39;utilizzo della piattaforma.
* **Integrazioni e configurazione del sistema**: gestione dei connettori, accesso basato su API e impostazioni a livello di sistema.

Gli amministratori devono seguire le politiche di controllo degli accessi interni e di gestione delle modifiche della propria organizzazione durante l&#39;esecuzione di azioni amministrative.

Consulta [Domande frequenti per gli amministratori di Adobe Learning Manager](https://experienceleague.adobe.com/it/docs/learning-manager/using/faq/frequently-asked-questions-for-administrators)


### Gerarchia e delega dei ruoli

Adobe Admin Console utilizza una struttura gerarchica di amministrazione. Gli amministratori di sistema possono delegare le responsabilità a ruoli con privilegi inferiori per ridurre la superficie di attacco dell&#39;account amministratore di livello superiore:

* Amministratore del prodotto: gestisce l&#39;accesso a prodotti di Adobe specifici (ad esempio, Adobe Learning Manager).
* Amministratore dei profili di prodotto: gestisce l&#39;iscrizione degli utenti a profili di prodotto specifici.
* Amministratore gruppo di utenti: gestisce l’iscrizione al gruppo di utenti.
* Amministratore personalizzato ALM: amministratore con ambito in ALM con autorizzazioni configurabili per catalogo e gruppo di utenti.

### Prassi di governance in corso

Le organizzazioni che gestiscono account di amministratore ALM devono seguire le seguenti procedure su base continuativa:

* **Revisione periodica dell&#39;accesso**: controlla regolarmente l&#39;elenco degli amministratori di sistema in Admin Console (Utenti > Amministratori) e degli amministratori ALM (Utenti > Interni) per garantire che solo il personale corrente e autorizzato ricopra questi ruoli.
* **Monitoraggio del registro di controllo**: l&#39;Admin Console Registro di controllo registra tutte le modifiche apportate dagli amministratori. Gli amministratori di sistema hanno piena visibilità. Esamina regolarmente il registro per verificare l’eventuale presenza di modifiche non autorizzate.
* **Accesso minimo in piedi**: evitare di utilizzare account di amministratore di primo livello per le attività di routine. Riserva l&#39;accesso completo come amministratore per le attività che lo richiedono.
* **Protezione della sessione**: configurare Durata massima della sessione e Tempo massimo di inattività in Admin Console > Impostazioni > Impostazioni avanzate per limitare l&#39;esposizione da sessioni automatiche.

Per ulteriori informazioni, vedere [Panoramica di Admin Console](https://helpx.adobe.com/it/enterprise/using/admin-console.html).

### Gestire gli account utente sotto il controllo dell’amministratore

Gli amministratori ALM gestiscono gli account utente interni ed esterni. Le operazioni relative alla sicurezza comprendono:

* Eliminazione automatica degli utenti: nelle impostazioni, gli amministratori possono configurare gli utenti interni inattivi in modo che vengano eliminati automaticamente dopo un numero specificato di giorni, riducendo il rischio di account inattivi.
* Scadenza utente esterno: gli amministratori impostano una data di scadenza durante la creazione dei profili utente esterni. Gli account scaduti vengono spostati automaticamente allo stato inattivo.
* Eliminazione degli utenti: gli amministratori possono eliminare manualmente gli utenti tramite Utenti > Interno > Azioni > Elimina utente.
* Rimozione degli utenti: dopo l’eliminazione, gli amministratori possono eliminare definitivamente i record degli utenti per rispettare i criteri di conservazione dei dati e impedire l’accesso non autorizzato a dati utente non aggiornati.

Per ulteriori informazioni, consultate i seguenti riferimenti:

* [Aggiungere utenti e gruppi di utenti](https://experienceleague.adobe.com/it/docs/learning-manager/using/admin/user-management/add-users-user-groups)
* [Rimuovere utenti](https://experienceleague.adobe.com/it/docs/learning-manager/using/admin/purge-users)

## Dismissione dei conti amministrativi

Quando non è più necessario, l’accesso amministrativo deve essere rimosso. I conti amministrativi delle operazioni di disattivazione possono comprendere:

* Revoca dei ruoli amministrativi agli utenti.
* Riduzione dei privilegi quando non è più necessario l&#39;accesso amministrativo completo.
* Rimozione degli utenti dal sistema quando appropriato.

La revisione regolare e la rimozione degli accessi amministrativi non necessari contribuiscono a mantenere l&#39;accesso meno privilegiato.

### Rimozione dei diritti di amministratore di sistema (Admin Console)

Quando un amministratore di sistema lascia l&#39;organizzazione o modifica i ruoli, i privilegi devono essere revocati immediatamente:

1. Accedi a Adobe Admin Console come amministratore di sistema.
2. Seleziona Utenti > Amministratori.
3. Seleziona l’amministratore da rimuovere.
4. Fai clic sull&#39;icona Altre opzioni (...) > Modifica amministratore, quindi rimuovi il ruolo di amministratore di sistema — OPPURE seleziona Rimuovi utente per rimuovere completamente l&#39;utente dall&#39;organizzazione.
5. Se l&#39;amministratore ricopriva altri ruoli (amministratore del prodotto, amministratore del supporto, ecc.), revoca anche questi.

>[!IMPORTANT]
>
>Se l&#39;amministratore uscente è il proprietario del contratto per l&#39;organizzazione, il ruolo Proprietario del contratto deve essere trasferito a un&#39;altra persona prima di poter essere rimosso. Se necessario, contatta il supporto di Adobe.

Per ulteriori informazioni, consultate i seguenti riferimenti:

* [Creazione, aggiornamento o rimozione di account utente nell&#39;Admin Console](https://helpx.adobe.com/it/enterprise/using/manage-users-individually.html)
* [Come lasciare l&#39;account di proprietà dell&#39;organizzazione](https://helpx.adobe.com/it/enterprise/using/leave-organization.html)

### Rimuovi il ruolo di amministratore ALM

Per revocare l&#39;accesso come Amministratore ALM senza eliminare l&#39;account dell&#39;utente (ad esempio, quando la persona rimane un Allievo):

1. Accedi a Adobe Learning Manager come Amministratore.
2. Seleziona Utenti > Interno.
3. Cerca e seleziona l’utente.
4. Seleziona Azioni > Rimuovi ruolo > Rimuovi amministratore.

L’utente torna al ruolo di Allievo. La cronologia di apprendimento e le iscrizioni ai corsi vengono mantenute.

Per ulteriori informazioni, vedere [Aggiungere utenti e gruppi di utenti](https://experienceleague.adobe.com/it/docs/learning-manager/using/admin/user-management/add-users-user-groups).

### Eliminare ed eliminare gli utenti

Quando un utente esce completamente dall&#39;organizzazione e il suo account deve essere rimosso dalla piattaforma:

* Elimina l’utente: Utenti > Interno > seleziona utente > Azioni > Elimina utente. Questo disattiva l’account e rimuove l’accesso attivo.
* Svuota l’utente: dopo l’eliminazione, accedi a Utenti > Pulizia utente, seleziona il mese di eliminazione, seleziona l’utente e scegli Azioni > Svuota utente. La rimozione definitiva rimuove tutti i record utente.

Per ulteriori informazioni, vedere [Rimuovi utenti](https://experienceleague.adobe.com/it/docs/learning-manager/using/admin/purge-users).


## Sicurezza e responsabilità condivisa

Adobe Learning Manager opera secondo un modello di responsabilità condivisa:

* Adobe è responsabile della protezione della piattaforma e dell&#39;infrastruttura ALM sottostante.
* I clienti sono responsabili della gestione dell&#39;accesso amministrativo, dell&#39;assegnazione dei ruoli e delle attività del ciclo di vita degli utenti all&#39;interno del proprio account ALM.

Ulteriori informazioni sulle procedure di sicurezza di Adobe Learning Manager sono disponibili in [Cenni preliminari sulla sicurezza di Adobe Learning Manager (PDF)](https://experienceleague.adobe.com/docs/learning-manager/assets/alm-security-whitepaper-2024.pdf?lang=it)

## Manutenzione dei documenti

Questo documento può essere aggiornato periodicamente per riflettere le modifiche alle funzionalità di Adobe Learning Manager o alle procedure consigliate di amministrazione. La versione e la data dell’ultimo aggiornamento vengono mantenute nei metadati del documento e nel pacchetto di autorizzazione FedRAMP. I clienti devono fare riferimento alla versione pubblicamente disponibile su Adobe Experience League per assicurarsi di utilizzare le indicazioni più aggiornate.

## Copertura avanzata delle funzionalità di sicurezza

### SCG-ENH-CMP

Adobe gestisce i processi documentati di inventario, proprietà e gestione del ciclo di vita dei componenti per garantire la conformità e la configurazione controllata dei componenti.

### SCG-ENH-API

Adobe applica controlli di sicurezza API standardizzati, tra cui autenticazione, autorizzazione e monitoraggio, supportati da governance documentata e protezioni per la piattaforma.

### SCG-ENH-MRG

Adobe applica processi formali di gestione delle modifiche e delle unioni, inclusi i controlli di revisione e approvazione, per mantenere l&#39;integrità del sistema e ridurre i rischi di distribuzione.

### SCG-ENH-VRH

Adobe segue un processo di gestione e risoluzione delle vulnerabilità definito che comprende l&#39;identificazione, la definizione delle priorità, il monitoraggio e la risoluzione tempestiva.
