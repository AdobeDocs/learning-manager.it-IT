---
jcr-language: en_us
title: Ruoli personalizzati
description: La funzione Percorsi di apprendimento consente di definire ruoli personalizzati e di assegnare responsabilità specifiche a un gruppo di utenti. Questa funzione consente di assegnare responsabilità al di fuori dell'ambito del ruolo esistente della persona.
contentowner: dvenkate
exl-id: dcc84f91-4e51-4ae2-b7cb-9eb29b398bc1
source-git-commit: 890775dafffd3b9d717c39507490977f51f163d4
workflow-type: tm+mt
source-wordcount: '2223'
ht-degree: 63%

---

# Ruoli personalizzati

Questa funzione consente di definire ruoli personalizzati e di assegnare responsabilità specifiche a un gruppo di utenti. Questa funzione consente di assegnare responsabilità al di fuori dell&#39;ambito del ruolo esistente della persona.

È possibile creare un ruolo personalizzato per fornire funzionalità di creazione limitate a un determinato catalogo. Puoi anche creare un ruolo dedicato alla gestione dei rapporti. Tali ruoli possono quindi essere assegnati a singoli utenti che dovrebbero assumere queste responsabilità specifiche.

## Creazione di un ruolo personalizzato {#create-role}

1. Accedi come Amministratore. Apri **[!UICONTROL Utenti]** > **[!UICONTROL Ruolo personalizzato]**.
1. Seleziona **[!UICONTROL Crea ruolo]**. La **[!UICONTROL Crea nuovo ruolo]** viene aperta la scheda.

   ![](assets/create-new-role.png)

   *Creare un ruolo personalizzato*

1. Immetti il nome nella casella **[!UICONTROL Nome del ruolo]** campo.
1. **[!UICONTROL Privilegi dell’account]**: questi privilegi consentono ai proprietari dei ruoli di accedere ad aspetti specifici della configurazione del sistema e che agiscono sull&#39;intero account. Scegli le autorizzazioni di accesso. L’utente ottiene il pieno controllo sulle autorizzazioni assegnate.

>[!NOTE]
>
>   L&#39;ambito non è applicabile a questi privilegi.


![](assets/account-privileges.png)

*Imposta l’ambito*

1. **Privilegi di funzionalità - Funzionalità principali**: utilizzato per concedere l&#39;accesso a funzionalità specifiche per la gestione delle attività di apprendimento. tramite questa opzione possono essere concesse le autorizzazioni per le seguenti funzionalità.

   * Cataloghi
   * Rapporti
   * Tag

   ![](assets/core-features.png)

   *Imposta l’ambito per cataloghi, report e tag*

1. **Privilegi di funzionalità - Oggetti di apprendimento:**  Utilizzare questa opzione per consentire l&#39;accesso alle funzioni relative agli oggetti di apprendimento. Puoi fornire l’accesso ai seguenti LO.

   * Certificazioni
   * Corsi
   * Risorse formative
   * Programmi di apprendimento

   È inoltre possibile concedere un controllo operativo specifico per gli LO. L’autorizzazione può essere una delle seguenti:

   * Controllo completo
   * Modifica ed elimina
   * Iscrizione
   * Report

   ![](assets/learning-objects.png)

   *Concedere autorizzazioni specifiche*

1. **Ambito per i privilegi di funzionalità:** L’ambito dei privilegi di funzionalità assegnati a questo ruolo può essere limitato a un gruppo di utenti specifico o a uno o più cataloghi.

   Cataloghi: utilizza il pulsante di opzione per fornire controllo su **[!UICONTROL Tutti i cataloghi]** o utilizza l’opzione **[!UICONTROL Imposta accesso per catalogo]** per fornire l’accesso a cataloghi specifici. Puoi anche selezionare più cataloghi.

   Gruppi di utenti: fornisci l’accesso a **[!UICONTROL Tutti i gruppi di utenti]** o utilizza l’opzione **[!UICONTROL Imposta accesso per gruppo di utenti]** per fornire l’accesso a gruppi di utenti specifici. È possibile specificare un solo gruppo utenti.

   >[!NOTE]
   >
   >Se in Privilegi account hai selezionato Annuncio, Gamification, Modelli e-mail, Abilità e Utenti, l’accesso al gruppo di utenti viene fornito a tutti i gruppi di utenti per impostazione predefinita e questa opzione è disabilitata.

   Se hai selezionato Piani di apprendimento in Privilegi account, per impostazione predefinita è fornito l’accesso a tutti i cataloghi e gruppi di utenti e queste opzioni sono disabilitate in Ambito.

   ![](assets/define-scope-of-privileges.png)

   *Definire l&#39;ambito dei privilegi*

>[!NOTE]
>
>   In Learning Manager 27.6, puoi creare un ruolo personalizzato con un’area di validità di più cataloghi e fare in modo che vengano assegnate autorizzazioni diverse per ogni catalogo.


Per concedere varie autorizzazioni ai cataloghi, attieniti alla seguente procedura:

1. Fai clic sull’opzione **[!UICONTROL Imposta accesso per catalogo]**.
1. Scegli i cataloghi. Puoi vedere il livello di autorizzazione per ciascun catalogo. Le autorizzazioni sono le seguenti:

   <table>
        <tbody>
        <tr>
          <td>
          <p><b>Autorizzazione</b></p></td>
          <td>
          <p><b>Descrizione</b></p></td>
        </tr>
        <tr>
          <td>
          <p>Controllo completo</p></td>
          <td>
          <p>Garantisce il controllo completo su tutti gli oggetti di apprendimento. Le autorizzazioni includono Aggiungi, Modifica, Elimina, Lettura, Iscrivimi e Report.<br></p></td>
        </tr>
        <tr>
          <td>
          <p>Report</p></td>
          <td>
          <p>Concede solo l’accesso alla scheda Report dell’oggetto di apprendimento.</p></td>
        </tr>
        <tr>
          <td>
          <p>Iscrivimi</p></td>
          <td>
          <p>Concede solo l’autorizzazione a iscriversi per l’oggetto di apprendimento.</p></td>
        </tr>
        <tr>
          <td>
          <p>Sola lettura</p></td>
          <td>
          <p>Concede solo l’autorizzazione per visualizzare gli oggetti di apprendimento nel catalogo.</p></td>
        </tr>
        </tbody>
      </table>

1. Attiva o disattiva le autorizzazioni in base alle tue esigenze.
1. Per salvare le modifiche, fai clic su **[!UICONTROL OK]**. Quindi, per salvare le modifiche per il ruolo personalizzato, fai clic su **[!UICONTROL Salva]**.

Ad esempio, considera il seguente scenario.

L’autorizzazione risultante che un utente personalizzato avrebbe su un oggetto di apprendimento è un’intersezione tra l’autorizzazione dell’oggetto di apprendimento e l’autorizzazione del catalogo.

Un utente personalizzato ha l’autorizzazione completa sui corsi e l’accesso in sola lettura sul catalogo A ma l’autorizzazione completa sul catalogo B. I risultati sono un accesso in sola lettura sui corsi del catalogo A e il controllo completo sui corsi del catalogo B.

Un utente con un ruolo personalizzato può:

* visualizzare solo i contenuti dei cataloghi a cui ha accesso;
* accedere a qualsiasi oggetto di apprendimento in base alle autorizzazioni del catalogo di cui esso fa parte.

  Come Amministratore, puoi:

* scegliere più di un catalogo per un ruolo personalizzato;
* modificare le autorizzazioni di un catalogo in qualsiasi momento;
* rimuovere i cataloghi da un ambito a cui non desideri più concedere autorizzazioni;
* concedere implicitamente l’autorizzazione di sola lettura a un catalogo quando concedi le autorizzazioni al catalogo.

  La tabella seguente mostra come vengono concesse le autorizzazioni.

  <table>
    <tbody>
     <tr>
      <td>
       <p><strong> </strong></p></td>
      <td>
       <p><strong>Autorizzazione a livello di catalogo</strong></p></td>
     </tr>
     <tr>
      <td>
       <p><strong>Autorizzazione a livello di oggetto di apprendimento</strong></p>
       <p><strong>(Ad es.: corsi)</strong></p></td>
      <td>
       <p>Controllo completo</p></td>
      <td>
       <p>Iscrivimi</p></td>
      <td>
       <p>Report</p></td>
      <td>
       <p>Sola lettura</p></td>
     </tr>
     <tr>
      <td>
       <p>Controllo completo</p></td>
      <td>
       <p>Controllo completo</p></td>
      <td>
       <p>Iscrivimi</p></td>
      <td>
       <p>Report</p></td>
      <td>
       <p>Sola lettura</p></td>
     </tr>
     <tr>
      <td>
       <p>Iscrivimi</p></td>
      <td>
       <p>Iscrivimi</p></td>
      <td>
       <p>Iscrivimi</p></td>
      <td>
       <p>Sola lettura</p></td>
      <td>
       <p>Sola lettura</p></td>
     </tr>
     <tr>
      <td>
       <p>Modifica ed elimina</p></td>
      <td>
       <p>Modifica ed elimina</p></td>
      <td>
       <p>Sola lettura</p></td>
      <td>
       <p>Sola lettura</p></td>
      <td>
       <p>Sola lettura</p></td>
     </tr>
     <tr>
      <td>
       <p>Report</p></td>
      <td>
       <p>Report</p></td>
      <td>
       <p>Sola lettura</p></td>
      <td>
       <p>Report</p></td>
      <td>
       <p>Sola lettura</p></td>
     </tr>
    </tbody>
   </table>

1. **Utenti:** Utilizzare questa opzione per determinare a quali utenti è assegnato questo ruolo. Puoi scegliere uno o più utenti utilizzando la casella di ricerca.

   **Aggiungi utenti al caricamento CSV del ruolo personalizzato:** Per aggiungere utenti tramite l’aggiornamento CSV, aggiungi una colonna CustomRole al file .csv utilizzato dall’amministratore per importare gli utenti. Immettere il ruolo dell&#39;utente nella colonna CustomRole per gli utenti a cui si desidera assegnare un ruolo personalizzato. Per caricare il file CSV, fai clic su  **[!UICONTROL Aggiungi > Carica un file CSV]**.

   Colonna CustomRoleNota:

* Non è possibile cercare gruppi di utenti.
* Non è possibile cercare tra gli utenti a cui è già stato assegnato il ruolo di amministratore.
* L&#39;assegnazione di un nuovo ruolo personalizzato a un utente sostituisce il precedente ruolo personalizzato dell&#39;utente.

  <!--![](assets/users.png)-->

* Un amministratore personalizzato che dispone dell&#39;autorizzazione per Impostazioni potrà configurare la pianificazione per la sincronizzazione o la sincronizzazione degli utenti dall&#39;origine dati anche se non dispone dell&#39;autorizzazione per l&#39;entità Utenti.
* Se un Amministratore personalizzato dispone dell’autorizzazione per l’entità Utenti, può assegnare il ruolo di Amministratore a se stesso e diventare Amministratore standard.

## Limitare l’accesso alle cartelle per gli Autori personalizzati {#folder-custom-author}

Learning Manager supporta già la possibilità di concedere l’accesso alla libreria dei contenuti utilizzando ruoli personalizzati. Tutti gli autori personalizzati che hanno già accesso alla raccolta di contenuti continueranno ad avere accesso a tutti i file di contenuto anche dopo la configurazione delle cartelle dei contenuti. Ciò consente di mantenere il comportamento precedente. Gli amministratori non devono apportare modifiche nel caso in cui desiderano continuare a utilizzare il comportamento corrente.

Nel caso in cui desiderino limitare l’accesso a questi autori personalizzati, gli amministratori devono modificare il ruolo personalizzato esistente e configurarlo fornendo l’accesso solo a specifiche cartelle di contenuti.

![](assets/folder-access-forcustomauthors.png)

*Limitare l’accesso alle cartelle per autori personalizzati*

Durante la creazione di un Autore personalizzato, ora puoi assegnare all’Autore le cartelle dei contenuti. Scegli l’opzione **Cartelle selezionate**.

Dopo aver fatto clic su questa opzione, si apre una nuova finestra di dialogo in cui puoi assegnare le cartelle all’Autore personalizzato.

![](assets/choose-folder.png)

*Selezionare le cartelle per l&#39;autore personalizzato*

Scegli le cartelle e fai clic su **[!UICONTROL OK]**.

## Dashboard di riepilogo dell’apprendimento per l’Amministratore personalizzato {#custom-admin-dashboard}

Gli amministratori personalizzati possono visualizzare la stessa visualizzazione di un amministratore. Un amministratore personalizzato può accedere a dati che non rientrano nel suo ambito. Questo è applicabile solo se l’amministratore personalizzato ha un ambito completo. Per concedere pieno ambito, durante la creazione di un amministratore personalizzato, attiva l’opzione **[!UICONTROL Controllo completo]** nel rapporto Sintetico conto.

![](assets/create-custom-role.png)

*Creare un ruolo personalizzato*

Di conseguenza, le opzioni, **[!UICONTROL Tutti i cataloghi]** e **[!UICONTROL Tutti i gruppi di utenti]** verrà selezionato e il resto verrà disabilitato.

![](assets/scope-of-featureprivileges.png)

*Definire l&#39;ambito dei privilegi*

## Autorizzazioni implicite {#implicitpermissions}

Quando a un utente viene assegnato un ruolo con un&#39;entità specifica, potrebbero esserci casi in cui ha bisogno di accedere ad altre entità anche per poter eseguire compiti sull&#39;entità concessa. Ad esempio, se a un utente viene concesso l’accesso Crea all’entità Corso, deve accedere alle entità Abilità e Tag in modo da poterle associare al corso creato. In queste tabelle vengono fornite informazioni relative a tali autorizzazioni implicite.

<table>
 <tbody>
  <tr>
   <th>Tipo di accesso</th>
   <th>Autorizzazione dell’entità assegnata dall’Amministratore</th>
   <th>Autorizzazione entità implicita</th>
   <th>Accesso implicito</th>
  </tr>
  <tr>
   <td>Gestisci</td>
   <td>Utente</td>
   <td>Gruppo</td>
   <td>Crud</td>
  </tr>
  <tr>
   <td>Iscrivimi</td>
   <td>Tutti gli oggetti di apprendimento (corso, risorsa formativa, programma di apprendimento, certificazione)</td>
   <td>Utente<br>
     Piano di apprendimento</td>
   <td>Lettura</td>
  </tr>
  <tr>
   <td>Crea</td>
   <td>
    <p>Gruppo di contenuti<br>
      Risorsa formativa<br></p></td>
   <td>Tag</td>
   <td>Lettura</td>
  </tr>
  <tr>
   <td>Crea</td>
   <td>Corso</td>
   <td>Gruppo di contenuti<br>
     Tag<br>
     Abilità<br>
     Badge<br>
     Risorsa formativa</td>
   <td>Lettura su tutti</td>
  </tr>
  <tr>
   <td>Crea</td>
   <td>Programma di apprendimento<br>
     Certificazione<br></td>
   <td>Corso<br>
     Tag<br>
     Abilità<br>
     Badge</td>
   <td>Lettura</td>
  </tr>
  <tr>
   <td>Crea</td>
   <td>Piano di apprendimento</td>
   <td>Catalogo<br>
     Raggruppamento<br>
     Abilità<br>
     Tutti i persi (corso, risorsa formativa, programma di apprendimento, certificazione)</td>
   <td>Lettura</td>
  </tr>
  <tr>
   <td>Crea</td>
   <td>Annuncio</td>
   <td>Utente<br>
     Raggruppamento<br>
     Tutti i persi (corso, risorsa formativa, programma di apprendimento, certificazione)</td>
   <td>Lettura</td>
  </tr>
  <tr>
   <td>Crea</td>
   <td>Gamification</td>
   <td>Branding</td>
   <td>Scrittura</td>
  </tr>
  <tr>
   <td>*</td>
   <td>Utente</td>
   <td>Fatturazione</td>
   <td>Lettura</td>
  </tr>
  <tr>
   <td>*</td>
   <td>Catalogo</td>
   <td>Raggruppamento<br>
     Tutti i persi (corso, risorsa formativa, programma di apprendimento, certificazione)</td>
   <td>Lettura</td>
  </tr>
  <tr>
   <td>*</td>
   <td>Impostazione</td>
   <td>Branding<br>
     Utente</td>
   <td>Lettura</td>
  </tr>
  <tr>
   <td>*</td>
   <td>Branding</td>
   <td>Impostazione</td>
   <td>Lettura</td>
  </tr>
  <tr>
   <td>*</td>
   <td>Fatturazione<br>
     Gamification</td>
   <td>Utente</td>
   <td>Lettura</td>
  </tr>
 </tbody>
</table>

## Accedi a un ruolo personalizzato {#accessacustomrole}

Quando un Amministratore assegna un ruolo personalizzato, ricevi una notifica via e-mail.

Nota: se hai già effettuato l’accesso a Learning Manager con un ruolo personalizzato, dovrai accedere nuovamente a Learning Manager per assumere il nuovo ruolo.

Per passare da un ruolo all’altro, fai clic sull’icona del tuo profilo nell’angolo in alto a destra di Learning Manager e seleziona il ruolo.

## Piani di apprendimento con ambito di validità per ruoli configurabili {#scopeconfigure}

Nelle versioni precedenti di Learning Manager, qualsiasi ruolo personalizzato con l’autorizzazione per la creazione di piani di apprendimento poteva definire l’ambito del piano di apprendimento per tutti i tipi di gruppi di utenti e oggetti di apprendimento.

L’impostazione dell’ambito veniva disabilitata quando veniva concesso l’accesso al piano di apprendimento, consentendo all’utente di accedere per impostazione predefinita a Tutti i cataloghi e a Tutti i gruppi di utenti.

Per impostazione predefinita, tutti i piani di apprendimento creati da un Amministratore si applicano a tutti gli utenti. Gli utenti possono inoltre essere assegnati a qualsiasi oggetto di apprendimento. Per contro, gli utenti con ruoli personalizzati hanno accesso a tutti gli ambiti, ad esempio a tutti i cataloghi, gli oggetti di apprendimento o i gruppi di utenti. Ciò significa che gli Amministratori non potevano creare ruoli personalizzati come previsto per consentire l’accesso ai piani di apprendimento per gli utenti con ambito limitato.

In questo aggiornamento di Learning Manager è possibile creare ruoli personalizzati per piani di apprendimento che consentono di definire l’ambito degli utenti e degli oggetti di apprendimento. In altre parole, i piani di apprendimento possono essere creati con un ambito limitato derivato dall’ambito di un ruolo dell’Amministratore personalizzato.

A questo punto, un Amministratore può definire o limitare l’ambito, garantendo allo stesso tempo l’accesso alla gestione del piano di apprendimento.

Gli Amministratori personalizzati possono creare piani di apprendimento con un ambito limitato, determinato dall’ambito del ruolo configurabile dell’Amministratore personalizzato. Tali piani di apprendimento sono accessibili solo agli Amministratori personalizzati con lo stesso ruolo, oltre ad essere accessibili agli Amministratori normali. Inoltre, gli Amministratori personalizzati non possono visualizzare altri piani di apprendimento nell’account.

Gli Amministratori personalizzati esistenti, che hanno accesso ai piani di apprendimento, avranno sempre un ambito completo (per definizione). Avranno accesso a tutti i piani di apprendimento dell’account, proprio come gli Amministratori normali. I nuovi ruoli personalizzati creati con l’ambito completo e i nuovi Amministratori personalizzati aggiunti a tali ruoli continueranno ad avere accesso a tutti i piani di apprendimento.

I piani di apprendimento creati dagli Amministratori e dagli Amministratori personalizzati con ambito completo verranno creati come al solito e non saranno limitati dall’ambito.

Nella sezione **Ambito dei privilegi di funzionalità**, concedi l’accesso ai gruppi di utenti e/o al catalogo per il ruolo personalizzato.

![](assets/scope-for-featureprivileges.png)

*Concedere l’accesso a gruppi di utenti e/o cataloghi per il ruolo personalizzato*

Assegna un utente al ruolo personalizzato.

![](assets/assign-users-to-customrole.png)

*Assegnare un utente a un ruolo personalizzato*

L’utente ora accede a Learning Manager come Amministratore personalizzato e aggiunge un piano di apprendimento.

Quando viene aggiunto un nuovo Allievo, l’Amministratore personalizzato può selezionare un corso di formazione solo dai cataloghi con ambito del ruolo configurabile.

Questo piano di apprendimento ora è applicabile all’Allievo solo se l’utente è stato aggiunto anche al gruppo all’interno del gruppo di utenti con ambito del piano di apprendimento. Tutti gli altri Allievi sono esentati da questo piano di apprendimento.

## L’Allievo viene aggiunto al gruppo {#learnergetsaddedtothegroup}

<!--![](assets/add-learner-to-thegroup.png)-->

L’Amministratore personalizzato può selezionare qualsiasi gruppo di utenti che include utenti appartenenti al gruppo di utenti con ambito del ruolo.

Quando un utente viene aggiunto al gruppo specificato, all’oggetto di apprendimento vengono assegnati solo gli utenti che fanno già parte del gruppo di utenti con ambito del piano di apprendimento e che sono stati aggiunti al gruppo di utenti specificato.

## Modifica dell’ambito {#changeinscope}

Quando l’Amministratore modifica l’ambito del ruolo personalizzato, la modifica viene applicata anche all’Amministratore personalizzato. Quando l’Amministratore personalizzato sceglie un piano di apprendimento il cui ambito era già definito da un ruolo personalizzato precedente, viene visualizzato un messaggio, come illustrato di seguito:

![](assets/change-scope.png)

*Messaggio dopo le modifiche dell&#39;ambito*

L’Amministratore personalizzato deve ora aggiornare l’ambito precedente al nuovo ambito.

Facendo clic su **[!UICONTROL Aggiorna ambito]**, l’ambito viene aggiornato. Viene visualizzato un messaggio di avviso.

![](assets/refresh-scope-message.png)

*Messaggio di avviso dopo l&#39;aggiornamento di un ambito*

Facendo clic su **[!UICONTROL Sì]**, l’ambito viene aggiornato.

## Aggiunta di un report gamification a un ruolo personalizzato {#gamification-custom}

Un Amministratore può abilitare i report gamification per un utente personalizzato.

1. Nella pagina **[!UICONTROL Ruoli personalizzati]**, immetti il nome del ruolo personalizzato.
1. Nella **[!UICONTROL Privilegi di funzionalità: funzionalità principali]** , abilita l&#39;opzione **[!UICONTROL Controllo completo]** per la categoria **[!UICONTROL Report]**.

1. Nella sezione **[!UICONTROL Utenti]**, seleziona l’utente a cui verrà assegnato il ruolo personalizzato appena creato.
1. Fai clic su **[!UICONTROL Salva]**.

Quando un utente accede come Amministratore personalizzato e fa clic su **[!UICONTROL Report]** nel riquadro a sinistra, vengono visualizzate le trascrizioni, come illustrato di seguito:

![](assets/download-gamificationtranscripts.png)

*Scarica le trascrizioni della gamification*

Fai clic su **[!UICONTROL Trascrizioni gamification]**, scegli un utente e genera il report.

Se un amministratore modifica i punti del livello, i report mostrano i livelli in base ai punti correnti.

Il ripristino della gamification non ripristina la data di raggiungimento del livello.

## Domande frequenti {#frequentlyaskedquestions}

+++Come si crea un ruolo personalizzato?

Un ruolo personalizzato è simile a un sottoinsieme di un ruolo Autore o Amministratore. Consenti uno o più privilegi, definisci l’ambito e assegna il ruolo a un utente.

Fai clic **[!UICONTROL Utenti]** > **[!UICONTROL Ruoli personalizzati]**. Nella pagina Ruoli personalizzati fai clic su **[!UICONTROL Crea ruolo]**. Immetti il nome del ruolo personalizzato e imposta i privilegi per tale ruolo. Per ulteriori informazioni, consulta [Creazione di un ruolo personalizzato](custom-role.md#create-role).
+++

