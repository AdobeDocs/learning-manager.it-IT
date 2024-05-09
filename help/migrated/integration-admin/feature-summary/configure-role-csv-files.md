---
jcr-language: en_us
title: Gestisci ruoli personalizzati tramite file CSV
description: L’Amministratore di integrazione può aggiungere vari ruoli personalizzati al proprio account in un’unica soluzione tramite CSV e può assegnare lo stesso ruolo a vari utenti. Questo approccio automatizza il processo di creazione dei ruoli personalizzati.
contentowner: saghosh
exl-id: fce2f457-2834-491a-8331-64086f5a51b5
source-git-commit: 0d318715e120b20b27f4876ad47868bef47bdb7c
workflow-type: tm+mt
source-wordcount: '907'
ht-degree: 83%

---

# Gestisci ruoli personalizzati tramite file CSV

L’Amministratore di integrazione può aggiungere vari ruoli personalizzati al proprio account in un’unica soluzione tramite CSV e può assegnare lo stesso ruolo a vari utenti. Questo approccio automatizza il processo di creazione dei ruoli personalizzati.

Puoi configurare i ruoli tramite i connettori Learning Manager FTP e Box.

Dopo aver effettuato l’accesso all’account di archiviazione Box, l’Amministratore dell’integrazione può aggiungere i seguenti file CSV all’account:

* role.csv
* user_role.csv

Per iniziare, scarica i csv e modifica i valori in base alle tue esigenze.

**role.csv**
* File di esempio: [role.csv](assets/role.csv)
* File di esempio: [user_role.csv](assets/user_role.csv)

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
    <p>Name</p></td>
   <td>
    <p>Identifica il ruolo all'interno del CSV da assegnare agli utenti.</p></td>
   <td>
    <p>Autore vendita</p></td>
  </tr>
  <tr>
   <td>
    <p>&lt;Entity&gt;</p></td>
   <td>
    <p>Identifica il tipo di accesso (FULL, WRITE, ENROLL, REPORT, NONE) per ogni tipo di entità come Corso, Catalogo e così via.</p></td>
   <td>
    <p>COMPLETO</p>
    <p>NESSUNO</p>
    <p>SCRITTURA | REPORT</p>
    <p>I nomi delle colonne corrispondono ai nomi dei tipi di entità come Catalogo, Corso, Piano di apprendimento ecc.</p>
    <p>Nel CSV è presente una colonna per ogni tipo di entità. Le entità per le quali non è richiesto il permesso devono essere incluse con il valore NESSUNO</p></td>
  </tr>
  <tr>
   <td>
    <p>Identificatore area validità catalogo</p></td>
   <td>
    <p>Nome singolo catalogo o elenco separato da caratteri barra verticale (|) di nomi di catalogo che determinano l’ambito di questo ruolo.</p></td>
   <td>
    <p>Catalogo vendite | Catalogo generale</p></td>
  </tr>
  <tr>
   <td>
    <p>Specificatore ambito gruppo utenti</p></td>
   <td>
    <p>Nome e valore dell’attributo Gruppo utenti che determina l’ambito degli utenti di questo ruolo.</p>
    <p>Per gli ambiti, consulta le sezioni seguenti.</p></td>
   <td>
    <p>location=London</p></td>
  </tr>
  <tr>
   <td>
    <p>Descrizione</p></td>
   <td>
    <p>Descrizione intuitiva che facilita la comprensione dello scopo del ruolo e la successiva consultazione.</p></td>
   <td>
    <p>Accesso completo di tipo autore agli oggetti di apprendimento nel catalogo vendite</p></td>
  </tr>
 </tbody>
</table>

Tutte le colonne tranne la Descrizione sono obbligatorie.

## Definizione dell&#39;ambito dei gruppi di utenti {#definescopeofusergroups}

È possibile specificare ambiti per diversi tipi di gruppi di utenti come segue:

* Nome del gruppo di utenti così com&#39;è (ad esempio Tutti gli autori, Il mio gruppo personalizzato)
* Attributo e valore foglia (ad esempio Department=HR)
* Gruppi di profili di registrazione automatica (self_registration=nomeprofilo)
* Gruppi di profili di registrazione esterna (ext_registration=nome profilo)
* Un team di subordinati (manager_direct=`<emailid>`)
* Organizzazione completa di un Manager (manager_org=`<emailid>`)

**user_role.csv**

<table>
 <tbody>
  <tr>
   <td>
    <p><b>Nome Colonna</b></p></td>
   <td>
    <p><b>Descrizione</b></p></td>
   <td>
    <p><b>Commento</b></p></td>
  </tr>
  <tr>
   <td>
    <p>Id</p></td>
   <td>
    <p>ID e-mail dell'utente al quale si assegna un ruolo configurabile.</p></td>
   <td>
    <p>Se all'utente è già assegnato un ruolo configurabile, il ruolo viene sostituito con un nuovo ruolo specificato nel CSV. Non viene restituito alcun errore.</p></td>
  </tr>
  <tr>
   <td>
    <p>CustomRole (Ruolo personalizzato)</p></td>
   <td>
    <p>Nome del ruolo configurabile da assegnare all'utente</p></td>
   <td>
    <p>Il nome del ruolo deve essere un ruolo esistente, come specificato nel file CSV. I ruoli creati dall'amministratore tramite l'interfaccia utente possono essere utilizzati qui.</p></td>
  </tr>
 </tbody>
</table>

**Funzioni Ambito completo**

Ogni volta che viene assegnata l’autorizzazione completa per una qualsiasi delle seguenti funzionalità (caratteristiche a livello di account), l’ambito Gruppo utenti e l’ambito Catalogo vengono automaticamente considerati come COMPLETI in quanto l’utente non può avere accesso limitato a queste funzionalità.

Se nel CSV sono presenti nomi di catalogo o nomi di gruppi di utenti, questi vengono sovrascritti con autorizzazione COMPLETO.

* Annunci
* Abilità
* Gamification
* Utenti
* Piani di apprendimento
* Modelli e-mail

## Aggiungi i file CSV del ruolo nell’account {#addtherolecsvsintheaccount}

Nell’account Box, seleziona **Import > user > internal** (Importa > Utente > Interno) e carica i file role.csv e user_role.csv.

* I file CSV del ruolo personalizzato devono essere copiati nella cartella &quot;import->user->internal->user_role&quot;
* Il file CSV degli utenti deve essere copiato nella cartella &quot;import->user->internal&quot;

Entrambi i CSV devono essere caricati solo tramite Box o FTP e non possono essere caricati tramite l’interfaccia utente.

>[!NOTE]
>
>Il file CSV per gli utenti è obbligatorio, ma i file CSV per i ruoli personalizzati sono facoltativi. Tutti i file presenti vengono elaborati e altri vengono saltati.

I ruoli personalizzati creati utilizzando il file CSV non sono visibili agli amministratori nell’interfaccia utente. Questi ruoli non saranno correlati a o influenzati da ruoli già creati (o creati in seguito) dall’interfaccia utente.

I ruoli personalizzati creati da un file CSV possono essere gestiti interamente tramite il file CSV stesso. Ciò include l&#39;aggiunta, la modifica e l&#39;eliminazione di ruoli.

I ruoli assegnati possono essere revocati rimuovendo le voci di assegnazione dal csv user_role. Ma le assegnazione eseguite tramite l’interfaccia utente di amministrazione non sono influenzate.

Per assegnare e revocare un ruolo di configurazione, aggiorna i file CSV.

## Sincronizzazione di ruoli personalizzati {#synchronizationofcustomroles}

Una volta che l’Amministratore di integrazione ha caricato i file CSV basati sui ruoli nella memoria del connettore, può abilitare la sincronizzazione con i CSV. Ogni volta che un ruolo personalizzato viene aggiornato, aggiunto o eliminato nei CSV, l’amministratore può sincronizzare le informazioni nei file e aggiornare l’elenco dei ruoli.

Nella pagina della Guida introduttiva del pannello Amministratore, fai clic su **[!UICONTROL Impostazioni]** > **[!UICONTROL Origini dati]**.

Nella sezione Sincronizza impostazioni, abilitare l&#39;opzione **[!UICONTROL Attiva sincronizzazione automatica]**.

![](assets/sync-settings.png)

*Seleziona l’opzione Abilita sincronizzazione automatica*

Quando si sceglie questa opzione, è possibile pianificare l’orario della sincronizzazione sull&#39;ora esatta specificata nel campo dell’ora della sincronizzazione. Se si specifica l’ora di sincronizzazione come 12:00, i ruoli personalizzati vengono aggiornati esattamente all’ora specificata per ogni giorno.

Se si desidera sincronizzare i dati on-demand, fare clic su **[!UICONTROL Sync Now]** (Sincronizza adesso).

## Vincoli durante la configurazione dei ruoli {#constraintswhileconfiguringroles}

In qualsiasi account il nome di un ruolo deve essere univoco. Pertanto, un ruolo creato tramite interfaccia utente o CSV non deve avere lo stesso nome di un altro ruolo già creato tramite interfaccia utente o CSV.

Analogamente, nell’interfaccia utente di amministrazione non è possibile assegnare a un utente un ruolo configurabile creato tramite CSV, perché questi ruoli non saranno disponibili.

Tuttavia il CSV di assegnazione utenti può essere utilizzato per assegnare ruoli creati dall&#39;interfaccia utente.
