---
description: Le Trascrizioni allievi in Adobe Learning Manager (ALM) consentono agli Amministratori di monitorare i progressi degli allievi in corsi, moduli, percorsi di apprendimento e certificazioni. Supporta le valutazioni delle prestazioni, il monitoraggio della conformità, gli audit e le relazioni esterne. Il report offre un riepilogo completo del coinvolgimento e delle prestazioni di un Allievo.
jcr-language: en_us
title: Trascrizioni Allievi in Adobe Learning Manager
source-git-commit: 85799b32f3a24fc0e6beb34ae39a502ff8e7a7b4
workflow-type: tm+mt
source-wordcount: '4354'
ht-degree: 8%

---


# Trascrizioni Allievi in Adobe Learning Manager

## Panoramica

Le Trascrizioni Allievi in Adobe Learning Manager (ALM) consentono agli Amministratori di monitorare i progressi degli Allievi a livello granulare tra corsi, moduli, percorsi di apprendimento e certificazioni. I dati di trascrizione consentono di eseguire revisioni delle prestazioni, monitoraggio della conformità, verifiche e esigenze di reporting esterno.

>[!NOTE]
>
>Le Trascrizioni Allievi possono essere scaricate da Amministratori, Amministratori personalizzati, Manager o Allievi.

Nel caso degli Allievi, devono avviare le impostazioni del profilo e quindi scaricare le trascrizioni di apprendimento come file Excel. Questa trascrizione, generata per un singolo Allievo, descrive in dettaglio il suo percorso di apprendimento personale. Include i nomi di percorsi di apprendimento, corsi, istanze e moduli, oltre a date chiave quali iscrizione, completamento e scadenze. Inoltre, tiene traccia dei loro progressi attraverso lo stato, i voti, i punteggi dei quiz (inclusi i punteggi più alti e i massimi) e i tentativi compiuti. Inoltre, mostra gli ID del corso di formazione, le durate, le date di annullamento dell’iscrizione, i prezzi e qualsiasi commento inviato. Questo report fornisce una panoramica completa del coinvolgimento e delle prestazioni di un singolo Allievo.

Le organizzazioni possono utilizzare le Trascrizioni Allievi per aggiungere i dati relativi al comportamento di apprendimento a un data warehouse aziendale, in cui è possibile combinare i dati di apprendimento con altri dati aziendali per analizzare le correlazioni tra il comportamento di apprendimento e altri dati del processo.

## Scopo e vantaggi

* Crea record pronti per l&#39;esecuzione di audit per i requisiti normativi con data e ora di completamento.
* Collega le attività di apprendimento allo sviluppo dei dipendenti e all’acquisizione di competenze.
* Tiene traccia dello stato della certificazione per i ruoli che richiedono formazione obbligatoria.
* Supporta la misurazione quantitativa dell’efficacia dei programmi di apprendimento.

## Casi di utilizzo di Trascrizioni Allievi

Le Trascrizioni Allievi in Adobe Learning Manager tengono traccia dei corsi di formazione, della conformità e dello sviluppo delle competenze, consentendo ai reparti di verificare il completamento e di valutare l’efficacia dei programmi all’interno dell’organizzazione.  Di seguito sono riportati alcuni casi d’uso trattati nelle Trascrizioni Allievi:

* Un&#39;organizzazione di servizi finanziari deve fornire la prova che tutti i dipendenti rivolti al cliente hanno completato un corso di formazione obbligatorio sulla conformità prima della scadenza prevista dalla normativa.
* Il reparto IT deve valutare le attuali funzionalità di programmazione Java rispetto ai requisiti futuri del progetto.
* HR desidera valutare l&#39;efficacia del nuovo programma di inserimento dei dipendenti nei diversi reparti.
* Il team operativo deve assicurarsi che tutti i tecnici sul campo mantengano le certificazioni di sicurezza richieste.

## Controllo di accesso e autorizzazioni

**Amministratori**

* Può generare trascrizioni per tutti gli Allievi in tutti i cataloghi.
* Può accedere a tutte le funzioni di reporting, ma può avere restrizioni a livello di catalogo o gruppo di utenti.
* Amministratori personalizzati: accesso limitato dall&#39;ambito e dalle autorizzazioni assegnati.

**Restrizioni basate sull&#39;ambito**

* Gli Amministratori personalizzati possono visualizzare le trascrizioni solo per gli Allievi all’interno dei gruppi di utenti assegnati.
* I report includeranno solo gli oggetti di apprendimento dai cataloghi a cui l’amministratore ha l’autorizzazione di accesso.

## Come generare le Trascrizioni Allievi

1. Accedi a Adobe Learning Manager come amministratore.
2. Seleziona **[!UICONTROL Report]** dal menu di navigazione a sinistra.
3. Seleziona **[!UICONTROL Report personalizzati]** in Report, quindi seleziona **[!UICONTROL Report Excel]**.
4. Seleziona **[!UICONTROL Trascrizioni Allievi]**.
5. Selezionare **[!UICONTROL Genera nuovo]**.
6. Seleziona l’intervallo di date per il quale desideri che venga generata la trascrizione. Per impostazione predefinita, la data **[!UICONTROL Da]** è la data di registrazione dell’Allievo e la data **[!UICONTROL A]** è sempre la data corrente. Puoi modificare solo la data di inizio da quando hai bisogno dei dati.
7. Selezionate una delle seguenti opzioni:
a. Seleziona i nomi degli Allievi nella sezione **[!UICONTROL Seleziona Allievi]**. Puoi selezionare utenti o gruppi di utenti oppure copiare e incollare gli indirizzi e-mail degli Allievi per i quali desideri generare le trascrizioni. Per ulteriori informazioni, consulta la sezione [Generazione della trascrizione Allievo](#generate-learner-transcript-using-copy-paste) utilizzando il comando copia-incolla.
b.Selezionare cataloghi specifici dall&#39;elenco a discesa **[!UICONTROL Seleziona cataloghi]**. La trascrizione viene scaricata solo per i cataloghi specificati.\
   c. Selezionare **[!UICONTROL Stato iscrizione]**. Questo elenco a discesa contiene le seguenti opzioni:

       * Seleziona tutto
       * Completato
       * In Corso
       * Non Avviato
       * Annullata L&#39;Iscrizione
   8. Opzioni avanzate: seleziona **[!UICONTROL Opzioni avanzate]** per scaricare le trascrizioni e includere quanto segue:

   a. Scarica le trascrizioni per gli Allievi eliminati da un account selezionando la casella di controllo **[!UICONTROL Includi Allievi eliminati]**.
b. Scarica le informazioni a livello di modulo nella trascrizione dell’Allievo abilitando la casella di controllo **[!UICONTROL Abilita informazioni a livello di modulo]**. In questo caso, i nomi dei moduli e il tempo impiegato per ogni modulo vengono recuperati come parte della trascrizione, se questa opzione è abilitata.
c. Scarica i dati sulle abilità e i fogli di riepilogo abilitando la casella di controllo **[!UICONTROL Includi dati sulle abilità e fogli di riepilogo]**. Per ulteriori informazioni, vedere la sezione Report Excel.
9. È inoltre possibile selezionare i valori delle colonne da inserire nel report. In questo modo è possibile scaricare i report con valori di colonna specifici in base alle esigenze. Seleziona le colonne dal menu a discesa.
Le trascrizioni vengono generate e scaricate nel computer come file .zip quando i dati sulle abilità non sono inclusi. Se la casella di controllo Dati abilità è abilitata, le trascrizioni vengono generate e scaricate come . file xlsx.

### Genera trascrizione Allievo utilizzando copia-incolla

Per acquisire le trascrizioni degli Allievi può volerci molto tempo, perché queste possono essere ottenute solo per un allievo o un gruppo di utenti alla volta. In questo caso, con la funzione copia-incolla, puoi copiare la lista di ID e-mail degli Allievi e copiarla in un solo momento.

1. Seleziona la scheda **[!UICONTROL ID e-mail]** per immettere l’elenco copiato di ID e-mail univoci.
2. Incolla gli ID e-mail univoci degli Allievi che desideri aggiungere, separati da virgola, punto e virgola o interruzione di riga.
3. Selezionare **[!UICONTROL Convalida ID e-mail]** per verificare se l&#39;ID e-mail immesso è valido. Se l’ID e-mail inserito non è corretto, viene evidenziato in rosso con un messaggio di convalida.

   >[!NOTE]
   >
   >Il pulsante Genera rimarrà disabilitato a meno che tutti gli ID e-mail inseriti non siano corretti.

4. Seleziona **[!UICONTROL Genera]** per generare le Trascrizioni allievi per tutti gli ID e-mail menzionati.

   >[!NOTE]
   >
   >La generazione delle Trascrizioni allievi può combinare gli ID e-mail inseriti sia nella scheda Utenti che nella scheda ID e-mail.

### Cosa contiene il report Trascrizioni Allievi

Il report Trascrizione Allievo è una combinazione di informazioni relative all’utente, all’iscrizione e agli oggetti di apprendimento.
Le tabelle seguenti descrivono ciascun tipo:

**Informazioni relative all&#39;utente**

Le colonne seguenti identificano l’Allievo.

| Campo | Descrizione |
|---|---|
| Nome | Nome dell’Allievo. |
| E-mail | Indirizzo e-mail dell’Allievo. |
| Adobe ID | Questo campo viene compilato solo quando gli utenti accedono utilizzando il proprio Adobe ID. Se accedono a Adobe Learning Manager tramite un [Single Sign-On (SSO)](/help/migrated/administrators/feature-summary/multiple-sso-logins.md) definito dall&#39;organizzazione, il campo Adobe ID rimarrà vuoto. |
| ID univoco utente | L’ID univoco utente è un ID esterno generato dagli account, nel caso in cui non dispongano degli ID e-mail di tutti gli utenti o degli ID e-mail univoci di tutti gli utenti. <br>Il campo ID univoco utente è un campo facoltativo che può essere abilitato per un account. Lo scopo principale del campo è consentire agli account di assegnare un tag a ogni utente con un ID univoco per tenerne traccia, aggiornare i record utente tramite API, audit o sincronizzazione dei dati nei flussi di lavoro automatizzati. L’assegnazione di tag a ogni utente avviene tramite l’importazione CSV degli utenti.</br><br>Se un account ha scelto ID utente univoco, i report, ad esempio le Trascrizioni allievi, Adobe Learning Manager fornisce la colonna nei report.</br> |

**Informazioni relative all&#39;iscrizione**

Le colonne seguenti consentono di acquisire l&#39;attività, l&#39;avanzamento o i tentativi.

| Campo | Descrizione |
|---|---|
| Data di iscrizione (fuso orario UTC) | Data e ora dell’iscrizione dell’Allievo al tipo di oggetto di apprendimento (corso, certificazione o percorso di apprendimento). |
| Contrassegna data completamento (fuso orario UTC) | Indicazione di data e ora di quando un Istruttore contrassegna una sessione o un modulo come completato. Si noti che se non si è verificata una sessione, la colonna viene visualizzata vuota nel report. Inoltre, se si è verificata una sessione e l’istruttore non l’ha contrassegnata come completata, la colonna appare vuota nel report. |
| Data di avvio (fuso orario UTC) | Data e ora in cui l’Allievo ha iniziato l’oggetto di apprendimento. Se il campo è vuoto significa che l’allievo non ha ancora iniziato l’attività. |
| Data di completamento (fuso orario UTC) | Data e ora in cui l’Allievo ha completato l’attività. Se il campo è vuoto significa che l’Allievo non ha ancora completato l’attività. |
| Scadenza (fuso orario UTC) | Data e ora previste per il completamento di questo oggetto di apprendimento da parte dell’Allievo. Se il campo è vuoto significa che non esiste una scadenza per l’attività. |
| Scaduta | Stato di ritardo corrente dell’Allievo iscritto all’oggetto di apprendimento. Sì/No |
| Stato | Indica lo stato dell’Allievo durante il corso, la certificazione o il percorso di apprendimento.  Gli stati disponibili sono Non avviato, Annullato, In corso o Completato. |
| % di avanzamento | % di avanzamento corrente dell’Allievo che segue il corso, la certificazione o il percorso di apprendimento. |
| Tempo trascorso (minuti) | Il tempo di apprendimento impiegato dall’Allievo nell’LO, le righe a livello di modulo mostrano il tempo di apprendimento dedicato al singolo modulo. Le righe a livello di corso/percorso di apprendimento/certificato mostrano il tempo di apprendimento aggregato impiegato. |
| Valutazione | Indica l’esito dell’attività dell’Allievo. ‘Superata’ indica che l’utente ha soddisfatto i criteri di successo, altrimenti la valutazione è “Non superata”. |
| Punteggio_quiz | La colonna viene utilizzata per registrare il punteggio ottenuto dall’ultimo tentativo di quiz. Ad esempio, se un utente esegue più tentativi (ad esempio, ottiene un punteggio di 10, 50 e 30 in tre tentativi), nella colonna Punteggio_quiz verrà visualizzato il punteggio ottenuto nell’ultimo tentativo, ovvero 30. Supponiamo che un quiz abbia un punteggio massimo di 100 e che un utente tenti tre volte, segnando 30, 60 e 90. La colonna Punteggio_quiz mostrerà 90 (il punteggio più recente), mentre il punteggio_quiz_più_alto mostrerà 90 (il punteggio migliore tra tutti i tentativi) e il punteggio_massimo_quiz rimarrà 100 (il punteggio massimo possibile). |
| Quiz_score_max | La colonna Quiz_score_max rappresenta il punteggio massimo che può essere ottenuto per un quiz o modulo specifico. Poiché Quiz_score_max rimane costante, è utile nei report mostrare il punteggio totale ottenibile per un quiz o modulo, indipendentemente dalle prestazioni dell’utente. |
| Highest_Quiz_score | La colonna Highest_Quiz_score rappresenta il punteggio più alto ottenuto da un utente su tutti i tentativi relativi a un quiz specifico. Ad esempio, se un utente effettua tre tentativi con un punteggio di 10, 20 e 15, nel punteggio più alto del quiz verrà visualizzato 20, in quanto è il punteggio più alto ottenuto. |
| Highest_Quiz_score_max | Il punteggio massimo possibile associato al tentativo di quiz più elevato eseguito da un Allievo in più tentativi. Non è il punteggio più alto raggiunto dall’Allievo. Al contrario, acquisisce il punteggio massimo che era possibile nel tentativo in cui l’Allievo otteneva il punteggio più alto. |
| Tentativi effettuati | Numero totale di tentativi compiuti dall’Allievo per questo modulo. |
| Numero massimo di tentativi consentiti | Numero massimo di tentativi consentiti per l’Allievo per utilizzare il modulo. |
| Commenti sui contenuti inviati | Commenti del manager di un Allievo dopo il completamento di un oggetto di apprendimento.<br>I dati dei commenti di invio forniti dall&#39;istruttore sono inclusi nel modulo di invio dei file . Per ulteriori informazioni, vedere <a href="https://experienceleague.adobe.com/en/docs/learning-manager/using/instructor/modules#filesubmissionforactivitymodules">Modules-Adobe Learning Manager.</a></br> |
| Origine completamento | Si riferisce all’origine o al metodo con cui viene registrato il completamento di un corso, programma di apprendimento o certificazione da parte di un Allievo. Consente agli amministratori di comprendere in che modo il completamento è stato raggiunto o registrato nel sistema. La colonna indica se il completamento è stato segnalato, registrato automaticamente o agevolato da un ruolo o una configurazione specifica. <b>Nota:</b> per i flussi di lavoro di partecipazione al connettore VC, quando un Allievo viene contrassegnato come partecipante automatico, nell&#39;origine viene visualizzato &quot;SELF, (learner_email)&quot;. |
| Commento di completamento | I commenti aggiunti dall’Amministratore quando contrassegna un Allievo come completo dopo aver completato un corso, una certificazione o un percorso di apprendimento. L’Amministratore può aggiungere i commenti di completamento per uno o più Allievi. |

**Informazioni relative agli oggetti di apprendimento**

Questi si riferiscono a corsi, moduli, percorsi di apprendimento, certificazioni e così via.

| Campo | Descrizione |
|---|---|
| Nome del piano di apprendimento | Titolo del piano di apprendimento. |
| LP/Certificazione/Corso | Titolo dell’oggetto di apprendimento. |
| Tipo | Il tipo di oggetto di apprendimento a cui l’utente è stato iscritto. Ad esempio:<ul><li>Percorso di apprendimento</li><li>Certificazione</li><li>Corso</li></ul> |
| Percorso incorporato | Un percorso incorporato è un tipo di percorso di apprendimento incluso in un altro corso.     o un percorso di apprendimento. Il campo indica che un Allievo sta completando quel percorso di apprendimento come parte di un altro percorso di apprendimento piuttosto che come assegnazione autonoma. |
| Corso | Nome del corso a cui l’utente è iscritto. Quando è vuota, la riga rappresenta un percorso di certificazione o di apprendimento. <br><b>Nota:</b> sebbene percorsi di apprendimento e certificazioni    composti da singoli corsi o percorsi di apprendimento nidificati, ogni componente mantiene il proprio record indipendente. Ciò garantisce che i dati relativi all&#39;avanzamento, al completamento e alla creazione di rapporti vengano registrati separatamente per gli elementi padre e figlio.</br> |
| ID univoco LO | ID univoco dell’oggetto di apprendimento. È necessario se il cliente dispone dell’LO in un sistema esterno che dispone di un proprio ID. Ciò è utile se desideri mappare l’LO Id e l’LO di Adobe Learning Manager del sistema esterno.<br>Un amministratore può abilitare l’opzione ID univoci oggetto di apprendimento nella pagina Impostazioni. Quando questa opzione è attivata, Adobe Learning Manager assegna un ID univoco a un oggetto di apprendimento ogni volta che un Autore crea un corso, una certificazione o un percorso di apprendimento. </br> |
| Istanza | Il nome dell’istanza dell’utente dell’oggetto di apprendimento a cui è iscritto. |
| Criteri di selezione | Base dell’iscrizione (come l’Allievo è stato iscritto a questo oggetto di apprendimento).<br>In Adobe Learning Manager, gli Allievi possono iscriversi agli oggetti di apprendimento tramite diversi metodi: Iscrizione nominata dal Manager: i Manager nominano gli Allievi per corsi specifici. Gli Allievi non possono iscriversi autonomamente a questi corsi.</br><ul><li>Iscrizione approvata dal manager: gli allievi si iscrivono ai corsi, ma l’iscrizione richiede l’approvazione del manager.</li><li>Iscrizione autonoma: gli allievi si iscrivono direttamente ai corsi senza richiedere l’approvazione.</li><li>Iscrizione tramite l’Amministratore: gli Amministratori iscrivono manualmente gli allievi ai corsi.</li></ul> |
| Modulo | Nome del modulo all’interno dei corsi. Nel report vengono visualizzati solo i moduli con stato Completato o In corso. Se lo stato è Non avviato o Non registrato, la colonna Modulo rimane vuota.<br>Scarica le informazioni a livello di modulo nella trascrizione dell’Allievo selezionando la casella di controllo <b>Abilita informazioni a livello di modulo</b>. In questo caso, i nomi dei moduli e il tempo impiegato per ogni modulo vengono recuperati come parte della trascrizione, se questa opzione è abilitata.</br> |
| ID modulo | ID univoco del modulo.<br><b>Nota:</b> la colonna ID modulo viene visualizzata nel report solo se è stata selezionata la casella di controllo Includi informazioni modulo durante la generazione della trascrizione.</br> |
| Versione | La versione del modulo si riferisce alla versione specifica di un modulo con cui un Allievo ha interagito. Ciò è particolarmente utile quando un modulo è stato aggiornato o modificato, in quanto consente agli amministratori di tenere traccia della versione del modulo a cui l’Allievo ha avuto accesso.<br>Quando un autore carica una nuova versione di un modulo, Adobe Learning Manager la considera come una nuova versione del modulo esistente. Ciò consente di aggiornare i contenuti senza interrompere le attività di tutti gli Allievi.</br><br>La versione viene visualizzata se la casella di controllo <b>Abilita informazioni a livello di modulo</b> è stata selezionata durante la generazione del report.</br><br>Per ulteriori informazioni, vedere <a href="https://elearning.adobe.com/2023/03/updating-the-module-in-adobe-learning-manager-how-to-replace-a-content-module-in-a-course-without-disturbing-the-users-progress" />Aggiornamento di un modulo in Adobe Learning Manager</a>.</br> |
| Tipo di erogazione | Indica come viene fornito il modulo: misto, aula o aula virtuale. |
| Lingua | Lingua in cui il modulo viene utilizzato dall’Allievo. Questa colonna mostra il valore solo per i moduli di eLearning. |
| Scaduta | Stato di ritardo corrente dell’Allievo iscritto all’oggetto di apprendimento. Sì/No |
| Valutazione | Indica l’esito dell’attività dell’Allievo. ‘Superata’ indica che l’utente ha soddisfatto i criteri di successo, altrimenti la valutazione è “Non superata”. |

>[!INFO]
>
>Le seguenti colonne sono nascoste nelle Trascrizioni Allievi:
>
>* Conteggio delle iscrizioni
>* Conteggio avviato
>* Conteggio completamento
>* Scadenza tra N giorni
>* Scadenza tra N giorni per l’utente
>* Conteggio di (avanzamento superiore al N%)
>* Conteggio di (avanzamento superiore al N%) per l’utente
>
>Queste colonne vengono visualizzate solo se hai selezionato Includi dati sulle abilità e fogli di riepilogo durante la generazione della trascrizione. Queste colonne vengono utilizzate per calcolare i dettagli di riepilogo di un Allievo iscritto a un oggetto di apprendimento.

| Campi | Descrizione |
|---|---|
| ID del corso di formazione | Un identificatore univoco generato dal sistema assegnato all’iscrizione di ciascun Allievo a un corso, a una certificazione o a un percorso di apprendimento specifico. Se un Allievo si iscrive nuovamente allo stesso corso, verrà generato un nuovo ID di formazione. Un Allievo può avere più ID di formazione per lo stesso corso. |
| Durata del corso di formazione o del modulo (minuti) | Questa colonna mostra la durata prevista (in minuti) di un corso, modulo o attività di formazione come definito durante la creazione del corso. Non è il tempo effettivo trascorso da un Allievo, ma la durata configurata/assegnata a rappresentare la durata prevista del corso di formazione. <br>Questa colonna mostra la durata totale (in minuti) dell’elemento di apprendimento assegnato, che può essere un percorso di apprendimento o un singolo corso.</br><br><b>Durata del percorso di apprendimento:<b> se l’elemento di formazione è un percorso di apprendimento, la sua durata viene calcolata come la somma delle durate di tutti i corsi all’interno del percorso di apprendimento.</br><br>Esempio: se corso 1 = 50 minuti e corso 2 = 60 minuti, la durata del percorso di apprendimento è pari a 110 minuti.</br><br><b>Durata del corso individuale:</b>Se l&#39;elemento del corso di formazione è un corso individuale (non fa parte di un percorso di apprendimento), la durata riflette il tempo richiesto solo per quel corso.</br> |
| Embedded_Course_ID | ID del corso che fa parte di un percorso di apprendimento o di qualsiasi altro corso.<br>La colonna viene compilata quando la riga rappresenta un percorso di apprendimento o una certificazione. Mostra gli ID dei singoli corsi incorporati nel percorso di apprendimento o nella certificazione. Non viene popolata quando la riga stessa è un corso in ly, poiché non sono presenti elementi incorporati.</br> |
| ID percorso incorporato | ID del percorso in cui si trova il corso incorporato.<br>La colonna identifica l’ID univoco dei percorsi di apprendimento incorporati. Consente di tenere traccia dei corsi all&#39;interno dei percorsi di apprendimento e di visualizzare la struttura gerarchica dei percorsi di apprendimento.</br> |
| Data di annullamento iscrizione (fuso orario UTC) | Data di annullamento dell’iscrizione dell’Allievo al tipo di oggetto di apprendimento. |
| Prezzo($) | Il prezzo dell’oggetto di apprendimento per il quale viene acquistato dal catalogo dei corsi. Affinché questa colonna venga visualizzata nella Trascrizione Allievo, l’Amministratore deve abilitare la casella di controllo Abilita prezzo per corsi/percorsi di apprendimento/certificazioni dalle impostazioni dell’account. |

## Report Excel

La finestra di dialogo Trascrizioni Allievi consente inoltre di scaricare i dati sulle abilità e i fogli di riepilogo come file Excel. Seleziona la casella di controllo **[!UICONTROL Includi dati sulle abilità e fogli di riepilogo]**, quindi seleziona **[!UICONTROL Genera]** per scaricare un file Excel con i fogli seguenti:

* Riepilogo apprendimento I
* Riepilogo apprendimento II
* Riepilogo conformità
* Trascrizione competenza
* Riepilogo competenze I
* Riepilogo competenze II

### Cosa contiene il foglio I del Riepilogo dell’apprendimento

Tieni traccia di percorsi di apprendimento, corsi o certificazioni utilizzati attivamente. Tenere traccia dell’attività in corso e delle date di scadenza imminenti per i corsi di formazione.

* Numero di Allievi iscritti: indica quanti Allievi sono stati iscritti a un determinato oggetto di apprendimento (corso, percorso di apprendimento o certificazione), indipendentemente dal fatto che lo abbiano avviato.
* Numero di Allievi che hanno iniziato: mostra il numero di Allievi che hanno avviato o iniziato il corso, la certificazione o il percorso di apprendimento.
* Numero di Allievi che hanno completato: mostra quanti Allievi hanno completato correttamente il corso di formazione e hanno soddisfatto tutti i criteri di completamento.
* Numero di Allievi con avanzamento ≥ N%: riflette il numero di Allievi che hanno raggiunto almeno la soglia di avanzamento specificata (ad esempio, 70%) nel corso di formazione, anche se non l’hanno completato.
* Numero di Allievi con Scadenza tra N giorni: indica quanti Allievi hanno una formazione con scadenza entro i successivi &quot;N&quot; giorni (ad esempio, 7 giorni), utile per identificare le scadenze imminenti.

### Come interpretare i dati

Questo report Riepilogo apprendimento I tiene traccia dei due percorsi di apprendimento assegnati all’Allievo.

* L’utente è iscritto a due percorsi di apprendimento e ne ha avviati entrambi.
* Nessuno dei percorsi di apprendimento è stato ancora completato.
* L’Allievo non ha ancora superato la soglia del 70% in nessuno dei due percorsi.
* Nessuna data di scadenza rientra nei prossimi sette giorni per entrambi i corsi di formazione.

### Cosa contiene il foglio Learning Summary II

Tieni traccia dell’attività di apprendimento per Allievo. Tieni traccia delle iscrizioni, dell’attività in corso e delle date di scadenza per gli Allievi.

* Numero di oggetti di apprendimento registrati: numero totale di oggetti di apprendimento (LO) a cui è iscritto l’Allievo in ogni corso, certificazione o percorso di apprendimento. conta separatamente .
* Numero di oggetti di apprendimento avviati: indica quanti oggetti di apprendimento registrati l’Allievo ha avviato o iniziato.
* Numero di oggetti di apprendimento completati: mostra quanti oggetti di apprendimento avviati l’Allievo ha completato completamente.
* Numero di oggetti di apprendimento con avanzamento ≥ N%: riflette il numero di LO in cui l’Allievo ha raggiunto almeno la soglia di avanzamento specificata (in questo caso, 70%).
* Numero di oggetti di apprendimento con data di scadenza tra N giorni: identifica gli oggetti di apprendimento con scadenza entro il numero di giorni successivo (in questo caso, 7 giorni), consentendo di tenere traccia delle scadenze imminenti.

### Come interpretare i dati

* L’Allievo è iscritto a due oggetti di apprendimento e ha iniziato entrambi.
* Nessun oggetto di apprendimento completato.
* L’Allievo non ha ancora raggiunto il 70% di progressi in nessuno di essi.
* Nessuno degli oggetti di apprendimento deve essere completato entro i prossimi 7 giorni.

### Cosa contiene il Riepilogo conformità

Tieni traccia degli Allievi con date di scadenza imminenti per corsi chiave, percorsi di apprendimento o certificazioni.

| Colonna | Descrizione |
|---|---|
| Tipo | Tipo di LO per il quale la tabella Riepilogo apprendimento deve visualizzare i dati. |
| Etichette righe (colonna laterale sinistra) | Il nome dell’Allievo con l’elenco degli LO a cui è iscritto. |

### Cosa contiene il foglio Trascrizione abilità

| Colonna | Descrizione |
|---|---|
| Nome | Nome e cognome dell’Allievo associato alla trascrizione dell’abilità. |
| E-mail | Indirizzo e-mail dell’Allievo. |
| ID univoco utente | Identificatore univoco definito dall’organizzazione per l’Allievo. |
| Competenza | Il nome dell’abilità assegnata all’Allievo (ad esempio, Programmazione Java, Leadership). |
| Livello di abilità | Il livello di esperienza all’interno dell’abilità che l’Allievo deve raggiungere (ad esempio, Principiante, Intermedio, Avanzato). |
| Crediti richiesti | Numero di crediti di apprendimento necessari per raggiungere il livello di abilità assegnato. |
| Crediti guadagnati | Numero di crediti guadagnati dall’Allievo per il completamento del livello di abilità assegnato. |
| Percentuale completamento | Percentuale di crediti richiesti completati dall’Allievo. |
| Data di assegnazione (UTC) | Data in cui l’abilità è stata assegnata all’Allievo. |
| Data acquisizione (UTC) | Data in cui l’Allievo ha ottenuto i crediti richiesti e ha soddisfatto i criteri del livello di abilità. |
| Nome del manager | Nome del manager dell’Allievo che supervisiona i progressi dell’apprendimento. |

### Cosa contiene il foglio I del Riepilogo competenze

| Colonna | Descrizione |
|---|---|
| Dopo | Rappresenta il numero di Allievi che hanno acquisito un’abilità prima di un periodo definito (in giorni) oltre il quale l’abilità viene considerata obsoleta o richiede un aggiornamento. Utile per identificare gli Allievi con obiettivi di abilità prossimi o scaduti.<br>Per ulteriori informazioni, vedere <a href="https://experienceleague.adobe.com/en/docs/learning-manager/using/admin/skills-levels">livelli di abilità</a>. |
| Nome | Nome completo dell’Allievo a cui è assegnata l’abilità. |
| Nome del manager | Nome del manager dell’Allievo responsabile della segnalazione. |
| Titoli delle righe | Il nome dell’abilità specifica assegnata agli Allievi visualizzato in questa riga. Utilizzata come intestazione di raggruppamento per riepilogare i dati relativi alle abilità degli Allievi in ciascuna categoria di abilità. |
| Numero di utenti che dovrebbero possedere questa competenza | Numero totale di Allievi a cui è stata assegnata la competenza specifica. |
| Numero di utenti che hanno conseguito questa competenza | Numero di Allievi che hanno completato correttamente gli oggetti di apprendimento richiesti per raggiungere l’abilità. |
| Numero di Allievi la cui competenza deve essere aggiornata | Il numero di Allievi le cui date di conseguimento delle abilità superano la soglia di aggiornamento definita. |
| Percentuale di conformità (in base alle competenze acquisite) | Il tasso di conformità o adozione per l’abilità. |


### Cosa contiene il foglio Riepilogo competenze II

| Colonna | Descrizione |
|---|---|
| Dopo | Numero di abilità acquisite dall’Allievo prima della soglia di aggiornamento definita (in giorni). Questa opzione consente di identificare le abilità che potrebbero essere obsolete e che devono essere aggiornate. |
| Competenza | Nome delle abilità assegnate agli Allievi. Potrebbe essere collegato a uno o più oggetti di apprendimento, ad esempio corsi, certificazioni o percorsi di apprendimento. |
| Nome del manager | Il nome del Direct Manager dell’Allievo. |
| Titoli delle righe | Nome completo dell’Allievo. Per ogni Allievo, le abilità e l’avanzamento vengono visualizzati nelle colonne successive. |
| Numero di abilità che ogni utente dovrebbe avere | Numero totale di abilità assegnate all’Allievo. |
| Numero di abilità di ogni utente | Numero totale di abilità acquisite correttamente dall’Allievo tramite il completamento degli oggetti di apprendimento associati. |
| Numero di abilità che devono essere aggiornate | Numero di abilità acquisite che hanno superato la durata dell&#39;aggiornamento e che ora richiedono un rinnovo. Questo valore consente di tenere traccia delle esigenze di rinnovo dei corsi di formazione in termini di conformità o sviluppo continuo. |
| Percentuale di conformità | Indica il livello di conformità complessivo dell’Allievo in base al raggiungimento dell’abilità. |

## Cronologia dei download delle trascrizioni degli Allievi

La cronologia dei download delle trascrizioni degli Allievi consente agli Amministratori di tenere traccia di chi ha scaricato le trascrizioni di ogni Allievo e degli utenti a cui hanno effettuato l’accesso. Questa funzione è particolarmente utile nelle impostazioni aziendali e incentrate sulla conformità, in cui diversi stakeholder possono avere bisogno di visualizzare i record di apprendimento.

Dopo aver scaricato una Trascrizione Allievo, la pagina Trascrizioni allievi elenca tutte le trascrizioni generate da chiunque nella piattaforma.

L&#39;elenco mostra i seguenti attributi:

* Da e A: durata delle trascrizioni da scaricare.
* Generato da: l’indirizzo e-mail dell’utente che ha scaricato il report o richiesto il download.
* Allievi: gli Allievi o i gruppi di Allievi le cui trascrizioni devono essere scaricate.
* Filtri applicati: i filtri applicati per lo stato di iscrizione.
* Dati aggiuntivi inclusi: i dati aggiuntivi (allievi eliminati, informazioni sul modulo, dati sulle abilità e fogli di riepilogo) che l’amministratore aveva richiesto dall’opzione Avanzate nella finestra di dialogo modale Aggiungi trascrizione Allievo
* Stato: scaricato, in coda o in corso.
* Annulla: annulla la generazione del report in qualsiasi momento.

## Ulteriori considerazioni sulle Trascrizioni Allievi

Le Trascrizioni Allievi includono diversi comportamenti che gli Amministratori devono tenere in considerazione:

**Visualizzazione del percorso di apprendimento e dell’avanzamento del corso**

Tutti i corsi che fanno parte di un percorso di apprendimento (LP) verranno visualizzati nelle trascrizioni degli allievi, anche se questi hanno compiuto progressi in uno solo dei corsi. Ciò garantisce la visibilità completa di un percorso di apprendimento, anche quando l’avanzamento è parzialmente completato.

**Dati per gli Allievi eliminati**

Se un Allievo è stato eliminato dalla piattaforma, la sua trascrizione non mostrerà i suoi record in alcun report generato per il gruppo di utenti di cui faceva parte. Ciò significa che i record degli Allievi eliminati verranno esclusi da qualsiasi report filtrato creato utilizzando i filtri dei gruppi di utenti.

Tuttavia, puoi comunque scaricare i dati degli Allievi eliminati. Se hai selezionato l’opzione **[!UICONTROL Includi allievi eliminati]** durante l’impostazione dei filtri per la generazione del report, puoi scaricare il report per gli allievi eliminati.

**Comportamento per gli amministratori personalizzati**

Gli amministratori personalizzati con un ambito definito (ad esempio, limitato a cataloghi specifici o gruppi di utenti) vedranno i dati di trascrizione filtrati in base al loro ambito:

* Ambito del gruppo di utenti: nel report verranno inclusi solo gli Allievi nel gruppo di utenti con ambito Amministratore personalizzato.
* Ambito del catalogo: nel report verranno inclusi solo gli oggetti di apprendimento (corsi, certificazioni e percorsi di apprendimento) assegnati ai cataloghi con ambito.
* Colonne filtrate: le colonne restano invariate. Solo le righe avranno un ambito in base agli ambiti dei cataloghi e dei gruppi di utenti.

Ciò garantisce che gli amministratori personalizzati con ambito visualizzino solo i dati e i contenuti di apprendimento dell’Allievo che sono autorizzati a gestire.

**Supporto del connettore**

È possibile accedere al report Trascrizione Allievo tramite l’interfaccia utente amministratore, [FTP, Box, Job API o Power BI](/help/migrated/integration-admin/feature-summary/connectors.md). Non è incluso nei report unificati di Salesforce, Power BI e Marketi Engage.

I report unificati scaricati da Salesforce, Marketi Engage e Power BI contengono meno colonne delle Trascrizioni Allievo.






