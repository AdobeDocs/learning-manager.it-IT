---
jcr-language: en_us
title: Gestire ruoli personalizzati tramite file CSV
description: L’Amministratore dell’integrazione può aggiungere più ruoli personalizzati al proprio account in blocco tramite file CSV e può assegnare lo stesso ruolo a vari utenti. Questo approccio automatizza il processo di creazione di ruoli personalizzati.
contentowner: saghosh
source-git-commit: ab6737e8b43222a6538921b0628a504a5f15859d
workflow-type: tm+mt
source-wordcount: '908'
ht-degree: 0%

---



# Gestire ruoli personalizzati tramite file CSV

L’Amministratore dell’integrazione può aggiungere più ruoli personalizzati al proprio account in blocco tramite file CSV e può assegnare lo stesso ruolo a vari utenti. Questo approccio automatizza il processo di creazione di ruoli personalizzati.

Puoi configurare i ruoli tramite i connettori Learning Manager FTP e Box.

Dopo aver effettuato l’accesso all’account di archiviazione Box o ExaVault, l’Amministratore dell’integrazione può aggiungere i seguenti file CSV all’account:

* role.csv
* user_role.csv

Per iniziare, scarica i file CSV e modifica i valori in base alle tue esigenze.

**role.csv**
[File di esempio: role.csv](assets/role.csv) [File di esempio: user_role.csv](assets/user-role.csv)

<table>
 <tbody>
  <tr>
   <td>
    <p><b>Nome colonna</b></p></td>
   <td>
    <p><b>Descrizione</b></p></td>
   <td>
    <p><b>Valori di esempio</b></p></td>
  </tr>
  <tr>
   <td>
    <p>Nome</p></td>
   <td>
    <p>Identifica il ruolo nel CSV da assegnare agli utenti.</p></td>
   <td>
    <p>Autore vendite</p></td>
  </tr>
  <tr>
   <td>
    <p>&lt;Entity&gt;</p></td>
   <td>
    <p>Identifica il tipo di accesso (FULL, WRITE, ENROLL, REPORT, NONE) per ogni tipo di entità come Corso, Catalogo e così via.</p></td>
   <td>
    <p>COMPLETO</p>
    <p>NESSUNO</p>
    <p>SCRIVI | REPORT</p>
    <p>I nomi delle colonne corrisponderanno ai nomi dei tipi di entità come Catalogo, Corso, Piano di apprendimento ecc.</p>
    <p>Nel file CSV sarà presente una colonna per ogni tipo di entità. Le entità per le quali non deve essere concessa alcuna autorizzazione devono essere incluse con il valore NONE</p></td>
  </tr>
  <tr>
   <td>
    <p>Specificatore ambito catalogo</p></td>
   <td>
    <p>Nome di catalogo singolo o elenco di nomi di catalogo separati da PIPE (|) che determinano l'ambito di questo ruolo.</p></td>
   <td>
    <p>Catalogo vendite | Catalogo generale</p></td>
  </tr>
  <tr>
   <td>
    <p>Specificatore ambito gruppo utenti</p></td>
   <td>
    <p>Nome e valore dell'attributo del gruppo di utenti che determinano l'ambito degli utenti di questo ruolo.</p>
    <p>Consulta la sezione seguente per gli oscilloscopi.</p></td>
   <td>
    <p>location=Londra</p></td>
  </tr>
  <tr>
   <td>
    <p>Descrizione</p></td>
   <td>
    <p>Descrizione facoltativa di facile utilizzo per comprendere lo scopo del ruolo e il riferimento successivo.</p></td>
   <td>
    <p>Accesso completo dell’autore agli LO nel catalogo di vendita</p></td>
  </tr>
 </tbody>
</table>

Tutte le colonne, ad eccezione di Descrizione, sono obbligatorie.

## Definire l’ambito dei gruppi di utenti {#definescopeofusergroups}

È possibile specificare gli ambiti per i gruppi di utenti per vari tipi di gruppi nei modi seguenti:

* Nome del gruppo di utenti così com’è (ad esempio, Tutti gli autori, Il mio gruppo personalizzato)
* Attributo foglia e valore (ad esempio, Department=HR)
* Gruppi di profili di registrazione autonoma (self_registration=profilename)
* Gruppi di profili di registrazione esterni (ext_registration=profilename)
* Un team di subordinati (manager_direct=`<emailid>`)
* Organizzazione completa di un Manager (manager_org=`<emailid>`)

**user_role.csv**

<table>
 <tbody>
  <tr>
   <td>
    <p><b>Nome colonna</b></p></td>
   <td>
    <p><b>Descrizione</b></p></td>
   <td>
    <p><b>Commento</b></p></td>
  </tr>
  <tr>
   <td>
    <p>ID</p></td>
   <td>
    <p>ID e-mail dell’utente a cui assegnare un ruolo configurabile.</p></td>
   <td>
    <p>Se all’utente è già stato assegnato un ruolo configurabile, questo viene sostituito con un nuovo ruolo specificato nel file CSV. Nessun errore segnalato.</p></td>
  </tr>
  <tr>
   <td>
    <p>CustomRole</p></td>
   <td>
    <p>Nome del ruolo configurabile da assegnare all'utente</p></td>
   <td>
    <p>Il nome del ruolo deve essere un ruolo esistente come specificato nel file CSV. Qui è possibile utilizzare i ruoli creati dall’amministratore tramite l’interfaccia utente.</p></td>
  </tr>
 </tbody>
</table>

**Funzioni Ambito completo**

Ogni volta che viene assegnata l’autorizzazione completa per una delle seguenti funzionalità (funzionalità a livello di account), l’ambito del gruppo di utenti e l’ambito del catalogo vengono automaticamente considerati come PIENI in quanto l’utente non può avere accesso limitato a queste funzionalità.

Se nel file CSV vengono forniti nomi di cataloghi o gruppi di utenti, questi verranno sostituiti con l’autorizzazione COMPLETA.

* Annunci
* Abilità
* Gamification
* Utenti
* Piani di apprendimento
* Modelli e-mail

## Aggiungi i file CSV dei ruoli all’account {#addtherolecsvsintheaccount}

Nell’account Box, scegli **Importa > utente > interno** e carica i file: role.csv e user_role.csv.

* I file CSV del ruolo personalizzato devono essere copiati nella cartella &quot;import->user->internal->user_role&quot;
* Il file CSV degli utenti deve essere copiato nella cartella &quot;import->user->internal&quot;

Entrambi i file CSV devono essere caricati solo tramite Box o FTP e non possono essere caricati tramite l’interfaccia utente.

>[!NOTE]
>
>Il file CSV per gli utenti è obbligatorio, ma i file CSV per i ruoli personalizzati sono facoltativi. Tutti i file presenti vengono elaborati e gli altri vengono ignorati.

I ruoli personalizzati creati utilizzando il file csv non sono visibili agli amministratori nell’interfaccia utente. Questi ruoli non saranno correlati o influenzati da ruoli creati (o da creare in seguito) dall&#39;interfaccia utente.

I ruoli personalizzati creati da un file CSV possono essere gestiti interamente tramite il file CSV stesso. Ciò include l&#39;aggiunta, la modifica e l&#39;eliminazione di ruoli.

I ruoli assegnati possono essere revocati rimuovendo le voci di assegnazione dal csv user_role. Tuttavia, questo non influisce sulle assegnazioni eseguite tramite l’interfaccia utente dell’amministratore.

Per assegnare e revocare un ruolo personalizzato, aggiorna i file CSV.

## Sincronizzazione dei ruoli personalizzati {#synchronizationofcustomroles}

Una volta che l’Amministratore dell’integrazione carica i CSV basati su ruoli nell’archiviazione del connettore, l’Amministratore può abilitare la sincronizzazione con i CSV. Ogni volta che un ruolo personalizzato viene aggiornato, aggiunto o eliminato nei file CSV, l’Amministratore può sincronizzare le informazioni nei file e rendere corrente l’elenco dei ruoli.

Nella pagina della Guida introduttiva del pannello Amministratore, fai clic su **[!UICONTROL Impostazioni]** > **[!UICONTROL Origini dati]**.

Nella sezione Sincronizza impostazioni, attiva l’opzione **[!UICONTROL Attiva sincronizzazione automatica]**.

![](assets/sync-settings.png)

*Seleziona l’opzione Abilita sincronizzazione automatica*

Quando si sceglie questa opzione, è possibile pianificare l&#39;ora della sincronizzazione all&#39;ora esatta specificata nel campo Ora di sincronizzazione. Se si specifica l&#39;ora di sincronizzazione alle 12.00, i ruoli personalizzati vengono aggiornati esattamente all&#39;ora specificata ogni giorno.

Per sincronizzare i dati su richiesta, fare clic su **[!UICONTROL Sincronizza]**.

## Vincoli durante la configurazione dei ruoli {#constraintswhileconfiguringroles}

In qualsiasi account, il nome di un ruolo deve essere univoco. Di conseguenza, un ruolo creato tramite interfaccia utente o CSV non deve avere lo stesso nome di un altro ruolo già creato tramite interfaccia utente o CSV.

Analogamente, dall’interfaccia di amministrazione, non è possibile assegnare a un utente un ruolo configurabile creato tramite CSV, poiché tali ruoli non saranno disponibili.

Tuttavia, il file CSV di assegnazione utente può essere utilizzato per assegnare ruoli creati dall’interfaccia utente.
