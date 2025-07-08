---
jcr-language: en_us
title: Domande frequenti per gli Amministratori
description: Domande frequenti per gli amministratori Adobe Learning Manager
contentowner: manochan
exl-id: 8b113a4e-73f4-4cd5-982a-cefdf5388e91
source-git-commit: b128a2adb1d0655078d79b6d46c00612f4ddb996
workflow-type: tm+mt
source-wordcount: '2515'
ht-degree: 52%

---

# Domande frequenti per gli Amministratori

<table>
 <tbody>
  <tr>
   <td><img src="assets/administrator2.png"></td>
   <td>
    <p>Continua a leggere per scoprire le domande frequenti relative a Learning Manager associate al ruolo di Amministratore. </p></td>
  </tr>
 </tbody>
</table>

+++È possibile aggiungere utenti in blocco? Come?

Sì, è possibile aggiungere utenti in blocco utilizzando la funzione che consente di caricare un file CSV. Per ulteriori informazioni, fai clic [qui](/help/migrated/administrators/feature-summary/add-users-user-groups.md#bulk-upload-internal-users).

+++

+++Se si digita male l’ID e-mail durante la creazione del login per gli Allievi, come posso correggerlo?

Per correggere il login di un utente, è necessario importare un file CSV in Learning Manager. Nella parte inferiore della pagina trovi in allegato un file CSV di esempio da poter consultare. L’e-mail è considerata un identificatore univoco di una persona, pertanto non può essere modificata. Procedi come segue:

1. Aggiungi lo stesso utente con l’ID e-mail corretto nel file CSV e assicurati che rimanga come Manager degli altri utenti aggiungendo il suo ID e-mail alla colonna &quot;E-mail del Manager del dipendente&quot; nel file CSV di esempio.
1. Aggiungi altri utenti presenti nel tuo account al file CSV, incluso te stesso
1. Importa questo file nell’app Learning Manager per gli Amministratori->Utenti->Aggiungi->Importa CSV
1. Collega tutti i campi alle colonne CSV corrispondenti, come ti viene richiesto nella finestra di dialogo.
1. Fai clic su Salva.

Gli utenti dovrebbero essere stati aggiunti alla pagina Allievi.

[File CSV di esempio di Learning Manager.csv](https://helpx.adobe.com/content/dam/help/en/captivate_prime/learning-manager-sample-csv.zip)

+++

+++Come si configurano gli avvisi?

Adobe Learning Manager 1.0 consente di creare notifiche. Per ulteriori informazioni, fai riferimento alla [domanda relativa alle notifiche](/help/migrated/administrators/feature-summary/user-notifications.md).

+++

+++Come si aggiungono i certificati per i corsi?

Adobe Learning Manager non fornisce certificati per i corsi. Tuttavia, l’Amministratore può creare distintivi per ogni corso facendo clic sulla scheda Distintivi nel pannello a sinistra. Quando l’Amministratore iscrive gli Allievi a un corso, può anche associarvi un distintivo.

+++

+++Come si importano le firme per i certificati?

Adobe Learning Manager non offre funzioni che consentono di importare firme per la certificazione o il distintivo.

+++

+++È possibile configurare un calendario per i corsi? Come?

In Adobe Learning Manager 1.0, non è possibile configurare il calendario dei corsi.

+++

+++Come si iscrivono direttamente gli Allievi in lista d’attesa?

Gli Allievi vengono inseriti in liste di attesa per ogni corso in aula che prevede un numero chiuso, in base all’ordine di iscrizione. Gli Amministratori possono selezionare gli Allievi nella lista di attesa e assegnare i posti, ignorando il limite, per qualsiasi corso in aula. Gli Allievi verranno iscritti ai corsi man mano che l’Amministratore assegna un posto.

1. Fai clic su Corsi nel riquadro a sinistra dopo avere effettuato l’accesso come Amministratore.
1. Dall’elenco dei corsi disponibili, fai clic sul nome di un corso in aula a tua scelta. Viene visualizzata una nuova pagina contenente informazioni dettagliate sul corso.
1. Fare clic su Lista di attesa nel riquadro a sinistra della pagina dei dettagli del corso. Nella pagina viene visualizzato un elenco di Allievi in lista di attesa.
1. Seleziona gli Allievi, quindi fai clic su Assegna posti per iscriverli direttamente ai corsi, ignorando il limite.

Per ulteriori informazioni, fai riferimento alla funzionalità [lista d&#39;attesa e partecipazione](/help/migrated/administrators/feature-summary/waitlist-attendance-management.md).

+++

+++Come si registra la partecipazione degli Allievi al modulo in aula?

Sì, è possibile registrare le presenze procedendo come segue:

1. Fai clic su Corsi nel riquadro a sinistra dopo avere effettuato l’accesso come Amministratore.
1. Dall’elenco dei corsi disponibili, fai clic sul nome di un corso/modulo in aula a tua scelta. Viene visualizzata una nuova pagina contenente informazioni dettagliate sul corso.
1. Seleziona gli Allievi, quindi fai clic su Salva per registrare il completamento del corso.

Se esistono più moduli in un corso e l’Allievo ne ha completato solo uno, puoi selezionare un singolo modulo e fare clic su Salva per segnare il completamento per un Allievo. Se l’Allievo completa tutti i moduli di un corso, puoi fare clic sull’opzione Seleziona tutti e poi su Salva.

Per ulteriori informazioni, fai riferimento alla funzionalità [lista d&#39;attesa e partecipazione](/help/migrated/administrators/feature-summary/waitlist-attendance-management.md).

+++

+++Come si include l’opzione feedback L3?

È possibile aggiungere il feedback L3 durante la registrazione degli Allievi ai corsi. Per aggiungere una domanda al feedback L3, procedi come segue:

1. Fai clic su Corsi nel riquadro a sinistra dopo avere effettuato l’accesso come Amministratore. L’elenco di tutti i corsi viene visualizzato nella pagina a destra.
1. Fai clic sul riquadro del corso a cui desideri aggiungere il feedback L3.
1. Fai clic sull’istanza predefinita nel riquadro a sinistra.
1. Fai clic sul cerchio del pulsante di attivazione accanto a L3 - Modifica comportamento feedback per selezionarlo.
1. Aggiungi la domanda al feedback L3 nell’area di testo sotto Domanda L3.

+++

+++Come posso cercare la nomina del Manager per un corso nominato dal Manager?

In qualità di Amministratore, puoi cercare i corsi nominati dal Manager procedendo come segue:

1. Fai clic su Corsi nel riquadro a sinistra
1. Passa il mouse su un corso nominato dal Manager, quindi fai clic su **[!UICONTROL Cerca nomina Manager]**.

1. Nell&#39;elenco delle istanze, fai clic sul collegamento **[!UICONTROL Manager nominati]** seguito dal collegamento **[!UICONTROL Aggiungi Manager]**.

1. Aggiungi il nome del Manager, il numero di posti assegnati e poi fai clic sul segno di spunta per salvare le modifiche.

Durante la creazione dei corsi, l’Autore sceglie il tipo di corso come Nominato dal Manager.

+++

+++Come si iscrive un Allievo a un corso specifico?

Per registrare gli Allievi ai corsi, procedi come segue:

1. Fai clic su Corsi nel riquadro a sinistra dopo avere effettuato l’accesso come Amministratore. L’elenco di tutti i corsi viene visualizzato nella pagina a destra.
1. Scegli il corso a cui desideri aggiungere gli Allievi e passa il mouse sopra di esso.
1. Fai clic su Iscrivi Allievi e aggiungi il loro nome. **Nota:** puoi aggiungere uno o più Allievi alla volta.

+++

+++Come si assegna un’abilità a un Allievo?

Per assegnare le abilità agli Allievi, procedi come segue:

1. Dopo aver effettuato l’accesso come Amministratore, fai clic su **[!UICONTROL Abilità]** nel riquadro a sinistra.
1. Seleziona una o più abilità facendo clic sulle caselle di controllo corrispondenti a ciascuna di esse e fai clic su **[!UICONTROL Azioni]** nell&#39;angolo superiore destro della pagina.
1. Fai clic su Assegna a utenti.
1. Inizia a digitare il nome dell&#39;utente, scegli dall&#39;elenco a discesa e fai clic su **[!UICONTROL Salva]**.

   >[!NOTE]
   >
   >Per assegnare le abilità a più Allievi, fai clic su Aggiungi altri utenti e ripeti il quarto passaggio.

+++

+++Come si crea una sessione per un programma di apprendimento?

Per creare un programma di apprendimento, procedi come segue:

1. Fai clic su Programma di apprendimento nel riquadro a sinistra. Viene visualizzata la pagina Programmi di apprendimento con un elenco di programmi di apprendimento esistenti.
1. Fai clic su Aggiungi nell’angolo in alto a destra della pagina.\
   Immetti il nome, la panoramica e la descrizione del programma, quindi fai clic su Salva.
1. Fai clic su Corsi nel riquadro a sinistra.
1. Per aggiungere uno o più corsi, fai clic su + sul riquadro di ciascun corso.

   >[!NOTE]
   >
   >Prima di iscrivere gli Allievi o un’istanza, è necessario pubblicare il programma di apprendimento.

1. Fai clic su Istanze nel riquadro a sinistra e poi su **[!UICONTROL Aggiungi nuove istanze]** nell&#39;angolo a destra della pagina per includere i dettagli dell&#39;istanza.

Per ulteriori informazioni sui programmi di apprendimento, fai riferimento alla [funzionalità Programmi di apprendimento.](/help/migrated/administrators/feature-summary/learning-programs.md)

+++

+++Come si modificano o personalizzano i report per tutti i ruoli?

Per modificare i report, fai clic sulla freccia a discesa nell’angolo in alto a destra di ciascuno di essi. Dopo aver completato le modifiche e visualizzato il report modificato, fai clic su Salva.

+++

+++Come si modificano corsi, programmi di apprendimento e profilo aziendale?

È possibile modificare corsi o programmi di apprendimento anche dopo la pubblicazione. Per ulteriori informazioni, fai riferimento ai [corsi](/help/migrated/administrators/feature-summary/courses.md) e ai [programmi di apprendimento](/help/migrated/administrators/feature-summary/learning-programs.md) contenuti della Guida.

Per modificare il profilo aziendale, fai clic su **[!UICONTROL Impostazioni]** nel riquadro a sinistra e poi su **[!UICONTROL Modifica]** nell&#39;angolo superiore destro della pagina.

+++

+++Come si cercano i corsi?

Fai clic su Corsi nel riquadro a sinistra dopo avere effettuato l’accesso come Amministratore. Viene visualizzato un elenco di tutti i corsi disponibili.

Puoi cercare i corsi in due modi:

1. Fai clic sull’icona di ricerca visualizzata nell’angolo in alto a destra. Viene visualizzato un campo di ricerca. Per individuare i corsi, digita il nome del corso o una parola chiave associata ad esso.
1. Applicando un filtro all’elenco di corsi.

Puoi filtrare i corsi per stato come Tutti, Pubblicati e Ritirati facendo clic su una di queste opzioni. Puoi anche eseguire una ricerca in base alle competenze facendo clic su Competenze e poi scegliendole.

A seconda della scelta, puoi visualizzare l’elenco filtrato di corsi e selezionare quelli desiderati.

+++

+++È possibile modificare i temi dell’applicazione? Come?

Sì, puoi modificare i temi e il branding dell’applicazione Learning Manager in base alle esigenze dell’organizzazione. Viene fornito un set di cinque immagini rappresentative per visualizzare in anteprima le modifiche apportate al tema colore prima di applicarle all’applicazione. Sfoglia queste immagini facendo clic su &lt; e > a sinistra e a destra delle immagini per visualizzarle in anteprima.

Fai clic su **[!UICONTROL Branding]** nel riquadro a sinistra per aggiornare il nome dell’organizzazione e modificare il sottodominio, gli stili del registro e i temi. Fai clic su **[!UICONTROL Modifica]** accanto a ciascuno di questi argomenti per modificare il contenuto.

Per ulteriori informazioni, fai riferimento alla [Guida ai temi colore e al branding](/help/migrated/administrators/feature-summary/themes.md).

+++

+++Come si configurano i distintivi per i corsi?

1. Dopo aver effettuato l’accesso come Amministratore, fai clic su Distintivi nel riquadro a sinistra.
1. Fai clic su Aggiungi nell’angolo in alto a destra della pagina visualizzata.
1. Aggiungi il nome del distintivo.
1. Carica il badge facendo clic su Carica distintivo, quindi seleziona Salva.

+++

+++Come si configurano i punti Gamification per i corsi?

Per configurare punti Gamification per gli Allievi, procedi come segue:

1. Dopo aver effettuato l’accesso come Amministratore, fai clic su Gamification. Viene visualizzata una pagina con un elenco di livelli bronzo, argento, oro e platino e i punti necessari per raggiungere ognuno di essi. È disponibile un elenco di attività e punti corrispondenti.
1. Per configurare/impostare i punti, fai clic sull’icona Modifica accanto a ogni attività.

Per ulteriori informazioni, fai riferimento alla [funzionalità Gamification](/help/migrated/administrators/feature-summary/gamification.md).

+++

+++Come si creano i report per i Manager e gli Allievi?

Per creare report, procedi come segue:

1. Fai clic su Report nel riquadro a sinistra. Viene visualizzata la pagina di riepilogo del report.
1. Nella pagina Report, fai clic su **[!UICONTROL Aggiungi]** nell&#39;angolo in alto a destra.

   Viene visualizzata la finestra di dialogo **[!UICONTROL Aggiungi report]**.

1. Compila tutti i campi obbligatori e fai clic su Salva.

Solo gli Amministratori e i Manager possono creare o visualizzare report. Per ulteriori informazioni, fai riferimento alla [funzionalità report](/help/migrated/administrators/feature-summary/reports.md).

+++

+++Come si passa ai ruoli di Allievo, Manager e Autore?

È possibile effettuare l’accesso all’account con altri ruoli, come Allievo, Manager e Autore, senza dover eseguire il log out.

1. Fai clic sulla freccia a discesa accanto all’immagine del profilo nell’angolo in alto a destra della pagina.\
   Viene visualizzato un menu a comparsa.
1. Seleziona ogni ruolo disponibile per accedere ai rispettivi account.

+++

+++Come si includono le notifiche per gli utenti?

Manager, Autori e Allievi possono visualizzare le notifiche in base alle attività del corso. Per attivare/disattivare le notifiche per tutti gli utenti, l’Amministratore deve procedere come segue:

1. Fai clic su Modelli e-mail nel riquadro a sinistra e scegli le schede Generale, Iscrizioni utenti, Completamenti e Feedback.
1. Dagli eventi elencati di seguito, fare clic sui pulsanti di attivazione No/Sì accanto a **ogni evento &#x200B;** e scegliere Sì per attivare la notifica. Per disattivare l’invio di notifiche per un evento specifico, fare clic su No.

+++

+++Come posso consentire l’iscrizione esterna ai corsi?

Adobe Learning Manager consente di iscrivere all’applicazione membri esterni al reparto o dipendenti al di fuori dell’organizzazione.

1. Fai clic su **[!UICONTROL Utenti]** nel riquadro a sinistra.
1. Fai clic su **[!UICONTROL Esterni]** nel riquadro a sinistra.
1. Fai clic su **[!UICONTROL Aggiungi]** nell&#39;angolo superiore destro della pagina.

   Viene visualizzata la finestra di dialogo Aggiungi utente.

1. Aggiungi il nome del profilo, l’e-mail del Manager, i posti assegnati e le informazioni sulla scadenza. Puoi anche aggiungere un’immagine al profilo esterno.
1. Fai clic su **[!UICONTROL Salva]**.

L’Amministratore può copiare l’URL di registrazione e inviarlo al gruppo esterno da iscrivere. Gli utenti esterni possono effettuare la registrazione, accedere all’applicazione Learning Manager e ai corsi.

+++

+++Come si aggiunge il questionario per il feedback L1?

Crea un questionario per il feedback da far compilare agli Allievi dopo il completamento dei corsi. Per impostazione predefinita, sono disponibili tre domande di esempio. Per creare il questionario, procedi come segue.

1. Fai clic su Feedback nel riquadro a sinistra. Viene visualizzata una finestra con il questionario per il feedback.
1. Fai clic su **[!UICONTROL Modifica]** per aggiungere/modificare il questionario.

Puoi aggiungere una serie di questionari e scegliere di non renderli visibili se non sono necessari. Per attivare/disattivare una determinata domanda, fai clic sulla casella di controllo corrispondente.

+++

+++Come si configurano le abilità e i livelli?

1. Fai clic su Competenze nel riquadro a sinistra della finestra Amministratore.
1. Per aggiungere nuove competenze, fai clic su Aggiungi.
1. Aggiungi il nome, la descrizione e i crediti della competenza in base a ciascun livello.

   Per impostazione predefinita, per ciascuna competenza sarà disponibile un singolo livello con 0 crediti.

1. Fai clic su [!UICONTROL **Aggiungi livello**] per aggiungere un nuovo livello a ciascuna competenza, quindi fai clic su Salva. Puoi aggiungere fino a 5 livelli.

Una volta salvata la competenza, i relativi livelli non potranno essere rimossi. L’Amministratore può anche assegnare una competenza e un livello specifico agli Allievi.

+++

+++Come si imposta il sistema di fatturazione per i corsi della mia organizzazione?

1. Fai clic su [!UICONTROL **Fatturazione**] nel riquadro a sinistra.

   Le informazioni di fatturazione vengono visualizzate nella pagina.

1. Fare clic sulla scheda [!UICONTROL **Abbonati**].
1. Digita il numero di pacchetti che desideri ordinare nel campo Pacchetti Allievo, quindi fai clic su Effettua ordine nell’angolo in alto a destra della pagina.

   Scegli il numero di pacchetti in base al numero di Allievi nell’organizzazione ed effettua l’ordine. Per la procedura guidata all&#39;acquisto, scrivici all&#39;indirizzo [learningmanagersales@adobe.com](mailto:learningmanagersales@adobe.com).

1. Inserisci le tue informazioni di contatto, scegli il tipo di carta di credito, fornisci i relativi dettagli e fai clic su Completa ordine.

Per ulteriori informazioni, fai riferimento alla funzionalità [Gestione fatturazione](/help/migrated/administrators/feature-summary/billing-management.md).

+++

+++È possibile personalizzare la progettazione del certificato? Come?

In Adobe Learning Manager, puoi riconoscere gli Allievi emettendo distintivi. Per ulteriori informazioni, fai riferimento alla funzionalità Distintivi.  Inoltre, fai riferimento alla funzionalità Certificazione.

+++

+++Come si imposta il profilo aziendale?

1. Dopo aver effettuato l’accesso come Amministratore, fai clic su **[!UICONTROL Informazioni aziendali]** nel riquadro a sinistra.
1. Aggiungi il profilo, il sottodominio e il logo dell’azienda facendo clic su ognuna di queste opzioni nella pagina.

+++

+++Come posso aggiungere corsi?

Per aggiungere corsi, è necessario passare al ruolo Autore. Puoi visualizzare l’elenco dei corsi disponibili solo in base al relativo stato, cioè **[!UICONTROL Completati]**, **[!UICONTROL Pubblicati]** e **[!UICONTROL Ritirati]**.

Per visualizzare i corsi, fai clic su **[!UICONTROL Corsi]** nel riquadro a sinistra. Per ulteriori informazioni, fai riferimento alla sezione [Creazione di corsi](/help/migrated/administrators/feature-summary/courses.md)

+++

+++Come si aggiungono ruoli diversi all&#39;applicazione?

Per aggiungere nuovi utenti, procedi come segue:

1. Dopo aver effettuato l’accesso come Amministratore, fai clic su Utenti nel riquadro a sinistra. Puoi aggiungere gli utenti anche facendo clic su Guida introduttiva nel riquadro a sinistra della finestra e poi su Aggiungi utenti.
1. Per aggiungere nuovi utenti, fai clic su Aggiungi nell’angolo in alto a destra della pagina.

Per impostazione predefinita, a tutti i nuovi utenti viene assegnato il ruolo Allievo. Per assegnare i ruoli Amministratore o Autore agli Allievi, fai clic su **[!UICONTROL Azioni]** nell’angolo in alto a destra della pagina, quindi scegli **[!UICONTROL Assegna ruolo]** > **[!UICONTROL Crea autore]** o **[!UICONTROL Crea amministratore]**.

Per informazioni dettagliate sull&#39;aggiunta di Allievi, Autori e Amministratori, fai riferimento alla funzionalità [Aggiungi nuovi utenti](/help/migrated/administrators/feature-summary/add-users-user-groups.md).

+++

+++Come si modifica un’immagine di sfondo di un Allievo?

Contatta il team di supporto di Learning Manager.

+++

+++Dove trovo l’ID del mio account Learning Manager?

Puoi trovare l’ID account nel browser in cui è aperto Learning Manager.

*/app/admin?i_qp_user_id=12761637&amp;**accountId=6849***

+++

+++Esiste un report che è possibile richiamare o che può essere richiamato da altri utenti che mi mostrerà un elenco di tutti i corsi disponibili nel sistema LMS?

Sì, puoi estrarre un **[!UICONTROL report sulla formazione]** che contiene tutti i corsi, il programma di apprendimento e la certificazione nel sistema LMS. Per scaricare il report, procedi come segue:

1. Accedi come Amministratore.
2. Fai clic su **[!UICONTROL Report]** > **[!UICONTROL Report personalizzati]** > **[!UICONTROL Report Excel]** > **[!UICONTROL Report dei corsi di formazione]**.
3. Seleziona **[!UICONTROL Tutti i corsi di formazione]** dal menu a discesa.
4. Fai clic su **[!UICONTROL Scarica]**.

+++

+++Dove posso scaricare la versione desktop dell&#39;app?

Segui i passaggi riportati di seguito per scaricare la versione desktop:

1. Accedi come Amministratore.
2. Fai clic su **[!UICONTROL Apprendimento sociale]** > **[!UICONTROL Impostazioni]**.
3. In **[!UICONTROL Scarica configurazione]**, fai clic sul collegamento ipertestuale a seconda del sistema operativo.

+++
