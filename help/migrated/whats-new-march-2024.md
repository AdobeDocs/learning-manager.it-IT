---
description: Scopri le nuove funzioni e i miglioramenti introdotti nella versione di marzo 2024 di Adobe Learning Manager
jcr-language: en_us
title: Riepilogo delle nuove funzioni
contentowner: jayakarr
exl-id: 603f1f1c-bf8d-4807-b9f7-b10ded19a91e
source-git-commit: c833d92533b7fbf5a87c980d8b5e088185d02ef5
workflow-type: tm+mt
source-wordcount: '3903'
ht-degree: 1%

---

# Riepilogo delle nuove funzioni {#new-features-summary}

Scopri le nuove funzioni e i miglioramenti inclusi nella versione di marzo 2024 di Adobe Learning Manager.

Esplora alcune delle funzionalità più recenti di Adobe Learning Manager, ad esempio:

1. Importare abilità da fonti esterne
1. Supporto di più branding
1. Modulo di rivalutazione dell&#39;attività di rivalutazione della lista di controllo
1. App di apprendimento mobile con etichetta bianca

>[!NOTE]
>
>Dai un&#39;occhiata a questo [webinar](https://learningmanager.adobe.com/app/learner?accountId=98632#/course/9212121) per saperne di più sulle nuove funzionalità di questa versione.


## Novità di questa versione {#whatsnewandchanged}

### Importare abilità da fonti esterne

Importare le competenze dai fornitori di contenuti, ad esempio LinkedIn e Go1, utilizzando i rispettivi connettori. Questo miglioramento fa parte dell&#39;obiettivo verso la capacità del Learning Manager di integrarsi con Skills Cloud e Talent Management Systems esterni. Le abilità importate verranno aggiunte alle abilità definite dall&#39;amministratore in Learning Manager e saranno disponibili per gli Autori durante il flusso di lavoro di creazione del corso. Sono stati inoltre apportati miglioramenti alla funzionalità di ricerca delle abilità in tutta la piattaforma per fornire una migliore esperienza di ricerca quando l&#39;account ha un numero elevato di competenze.

Per saperne di più, consulta [le competenze](administrators/feature-summary/import-skills-external-sources.md) di importazione.

### Personalizzazione

Ora potrai personalizzare alcuni elementi dell&#39;interfaccia utente: il nome dell&#39;organizzazione, il logo e il tema dell&#39;interfaccia utente in base ai gruppi di utenti disponibili nell&#39;account. Ad esempio, un&#39;organizzazione con più divisioni può impostare un logo personalizzato e un tema dell&#39;interfaccia utente da visualizzare per ogni divisione.

>[!NOTE]
>
>Questa funzione di personalizzazione multipla non è applicabile alla vista Amministratore. Vedranno sempre il branding a livello di organizzazione nel loro account. Questo perché si tratta di una funzionalità rivolta agli Allievi e gli amministratori potrebbero non volerla nel loro account.

Per ulteriori informazioni, visualizza [Più personalizzazioni di branding](administrators/feature-summary/themes.md#multiple-branding) .


## Modifiche per gli account con un&#39;ampia base di utenti

### Admin- Pagine del corso o del percorso di apprendimento

Se un numero elevato di Allievi è iscritto al corso, ad esempio più di 50.000, l&#39;elenco degli Allievi non verrà visualizzato. Puoi cercare un Allievo nella *barra di ricerca Cerca Allievi* o selezionare il **** link Scarica nella parte superiore della barra di ricerca per scaricare l&#39;elenco degli Allievi.

### Amministratore - Pagina Allievi

Quando cerchi un utente, le **opzioni Scarica Allievo** ed **Esporta** scaricano lo stesso report. Nel frattempo, durante la ricerca di un gruppo di utenti, puoi scaricare gli utenti filtrati da quel gruppo di utenti. Durante la ricerca in un gruppo di utenti,
L&#39;elenco **Scarica allievi** diventa **Scarica elenco Allievi per gruppo di utenti** L&#39;opzione **Esporta** scarica nuovamente l&#39;intero elenco.

### Admin- Pagina utenti

#### Utenti interni

Se il numero di utenti supera, ad esempio, 50.000, verrà visualizzato un messaggio per scaricare i dati per un&#39;analisi più dettagliata in un secondo momento. La barra di ricerca è ora prominente e visualizza un utente nel formato *Nome, email | UUID*.

>[!NOTE]
>
>L&#39;UUID viene visualizzato solo se l&#39;UUID è abilitato per l&#39;account.

#### Utenti esterni

Per gli utenti esterni, si applica lo stesso comportamento. Se il numero di utenti è elevato, è possibile scaricare gli utenti e anche recuperare i dettagli di un utente dopo una ricerca nel formato *Nome, e-mail | UUID*.

#### Pagina di pulizia utente

Nella pagina Pulizia utente, per gli utenti eliminati, è stata rimossa la funzionalità di ordinamento in **Data eliminazione**. È possibile ordinare solo in base agli UUID.

### Admin - Pagine delle istanze

#### Corso o percorso di apprendimento

Se il numero di iscrizioni è elevato, Adobe Learning Manager non visualizzerà il numero di Allievi. Al contrario, ci sarà un&#39;icona che puoi selezionare e visualizzare il numero di Allievi e passare alla pagina Allievi.

Il numero di Allievi verrà visualizzato come valore approssimativo. Ad esempio, se il numero di Allievi è superiore a 50.000, il valore verrà visualizzato come 50K+.

### Admin- Pagine L1/L3

Nella pagina Feedback L1, se il numero di iscrizioni ai corsi è elevato, l&#39;elenco degli Allievi non viene visualizzato. È invece possibile esportare l&#39;elenco degli utenti per un&#39;analisi più dettagliata in un secondo momento.

La ricerca supporta il type-ahead e i risultati sono limitati all&#39;istanza selezionata.

#### Pagina Presenze e punteggi

Nella pagina, quando cerchi un utente, la ricerca viene eseguita in tutte le istanze disponibili. Tuttavia, il risultato è per l&#39;istanza selezionata.

Nella pagina Partecipazione, se cerchi un gruppo di utenti e il numero di utenti supera i 10.000 nel gruppo di utenti, indipendentemente dall&#39;iscrizione, puoi eseguire solo azioni a livello di gruppo. Non sarà possibile visualizzare l&#39;elenco degli utenti.

Se il numero di utenti nel gruppo di utenti è inferiore a 10.000, puoi eseguire singole azioni a livello di utente insieme ad azioni a livello di blocco. In questo caso, l&#39;elenco degli utenti non è disabilitato.

### Admin- Pagina Certificazioni

Nelle versioni correnti di Adobe Learning Manager, se è presente un numero elevato di utenti iscritti a una certificazione, non è possibile visualizzare gli Allievi non iscritti poiché il menu a **discesa Stato** è disattivato.

In questa versione di Adobe Learning Manager, se il numero di utenti iscritti è elevato, il **menu a discesa Stato** visualizza solo due opzioni: **Registrati** e **Non iscritti**. L&#39;opzione **Iscritto** è selezionata per impostazione predefinita. Se selezioni **Non iscritti**, viene visualizzato l&#39;elenco degli Allievi non iscritti.

#### Modifiche ai gruppi di utenti

Nel caso di un gruppo di utenti, se il numero di utenti nel gruppo di utenti è inferiore, ad esempio, a 50.000, il **menu a discesa Stato** visualizza tutte le opzioni: Certificato, Assegnato e In scadenza.

Se il numero di utenti in un gruppo di utenti è elevato, l&#39;elenco **a discesa Stato** visualizza solo due opzioni: **Registrati** e **Non registrati**, in base alla nuova progettazione.

### Tabella comparativa

<table>
    <tbody>
        <tr>
            <td><b>Pagina</b></td>
            <td><b>Prima della modifica della soglia</b></td>
            <td><b>Dopo la modifica della soglia</b></td>
        </tr>
        <tr>
            <td>Admin- Istanza del corso</td>
            <td>Le istanze vengono visualizzate come previsto:
            <ul>
                <li>Moduli</li>
                <li>Allievi iscritti</li>
                <li>Sessioni</li>
                <li>Distintivo</li>
                <li>Feedback L1 abilitato</li>
                <li>Avvisi di notifica</li>
                <li>Punti di gamification</li>
                <li>Codice QR</li>
                <li>Estensione del percorso di apprendimento</li>
            </ul>
            <td>
                <ul>
                    <li>Se il numero di iscrizioni supera la soglia predefinita, ALM non visualizzerà il conteggio; il conteggio verrà sostituito con un'icona che, se selezionata, visualizza il numero effettivo di Allievi e un collegamento che ti porterà alla pagina Allievi.</li>
                    <li>Il numero di iscrizioni sarà visualizzato in un formato approssimativo. Ad esempio, se il numero è superiore a 50.000, il conteggio verrà visualizzato come 50K+ a livello del corso.</li>
                </ul>
            </td>
        </tr>
        <tr>
            <td>Amministratore - Pagina Allievi</td>
            <td>
                    <ul>
                        <li>Per ogni istanza viene visualizzato l'elenco degli Allievi.</li>
                        <li>Puoi cercare un utente o un gruppo di utenti iscritto a un corso.</li>
                        <li>Il report esportato non include alcun filtro per gruppo di utenti.</li>
                    </ul>
            </td>
            <td>
                <ul>
                    <li>La selezione dell'istanza è disabilitata.</li>
                    <li>Anche l'elenco degli Allievi scaricato scarica gli stessi dati, ad eccezione di un caso. Se cerchi un gruppo di utenti e poi selezioni l'elenco Scarica allievi, verranno scaricati i dati del gruppo di utenti.</li>
                </ul>
            </td>
        </tr>
        <tr>
            <td>Admin- Pagina di feedback L1/L3</td>
            <td>
                <p>Nessun cambiamento nel comportamento esistente</p>
            </td>
            <td>
                <ul>
                    <li>La selezione dell'istanza è disabilitata.</li>
                    <li>Se l'iscrizione a un corso è superiore a 50K, ALM non elenca gli Allievi e visualizza solo la barra di ricerca. Se l'iscrizione è inferiore a 50K, ALM visualizza sia l'elenco degli Allievi che la barra di ricerca.</li>
                    <li>L'inserzione è disattivata per impostazione predefinita.</li>
                </ul>
            </td>
        </tr>
        <tr>
            <td>Admin - Pagina Presenze e punteggi</td>
            <td>
                <p>Nessun cambiamento nel comportamento esistente</p>
            </td>
            <td>
                <ul>
                    <li>La selezione dell'istanza è disabilitata durante la ricerca di un utente.</li>
                    <li>Se il numero di utenti supera, ad esempio, 50.000, verrà visualizzato un messaggio aggiuntivo per scaricare i dati per un'analisi più dettagliata in un secondo momento. La barra di ricerca è ora prominente e visualizza un utente nel formato Nome, email | UUID.</li>
                    <li>Se il numero di utenti nel gruppo di utenti è inferiore a 10.000, indipendentemente dall'iscrizione, puoi eseguire singole azioni a livello di utente insieme ad azioni a livello di blocco. In questo caso, l'elenco degli utenti non è disabilitato.</li>
                </ul>
            </td>
        </tr>
        <tr>
            <td>Admin- Pagina Punteggio quiz L2</td>
            <td>
                    <ul>
                        <li>Viene implementata anche la ricerca degli utenti.</li>
                    </ul>
            </td>
            <td>
                <ul>
                    <li>Viene implementata anche la ricerca degli utenti. Durante la ricerca typeahead a livello di LO, l'elenco viene filtrato in base all'istanza attualmente selezionata.</li>
                </ul>
            </td>
        </tr>
        <tr>
            <td>Pagina Admin - Utenti (Interna, Esterna)</td>
            <td>
                    <ul>
                        <li>L'ID e-mail viene visualizzato durante la ricerca di un utente.</li>
                    </ul>
            </td>
            <td>
                <ul>
                    <li>Se il numero di utenti supera, ad esempio, 50.000, verrà visualizzato un messaggio aggiuntivo per scaricare i dati per un'analisi più dettagliata in un secondo momento. La barra di ricerca è ora prominente e visualizza un utente nel formato Nome, email | UUID.</li>
                    <li>Nella pagina Pulizia utente, per gli utenti eliminati, è stata rimossa la funzionalità di ordinamento in **Data eliminazione**. È possibile ordinare solo in base agli UUID.</li>
                </ul>
            </td>
        </tr>
        <tr>
            <td>Istruttori - Inscrição</td>
            <td>
                    <ul>
                        <li>Impaginazione dei moduli da inviare.</li>
                        <li>In qualità di Istruttore, ora puoi filtrare gli invii di file dagli Allievi in base a stato, Revisione finale, Invio in sospeso, Superato e Non superato. </li>
                    </ul>
            </td>
            <td>
                <ul>
                    <li>In questo caso puoi cercare solo utenti, non gruppi di utenti.</li>
                </ul>
            </td>
        </tr>
        <tr>
            <td>Conta sull'anteprima come pagina Allievo</td>
            <td>
                    <ul>
                        <li>Il conteggio include i dati delle iscrizioni di ordine superiore.</li>
                    </ul>
            </td>
            <td>
                <ul>
                    <li>Il conteggio esclude i dati dalle iscrizioni di ordine superiore.</li>
                </ul>
            </td>
        </tr>
    </tbody>
</table>

## Funzionalità di ricerca avanzate

In questa versione è stata migliorata l&#39;esperienza di ricerca. I risultati della ricerca vengono recuperati in base non solo ai metadati, ma anche alla ricerca semantica e all&#39;interno del contenuto per ricavare risultati basati su precisione, attualità e contenuto pertinente.

Questa modifica si riflette su quanto segue:

* Catalogo e pagina Il mio apprendimento: l&#39;azione di passaggio del mouse su corso, percorso di apprendimento e certificazione è stata rimossa.
* Aspetto della barra di ricerca.
* Sono stati aggiunti tag di filtro nell&#39;app di apprendimento.

Per attivare le funzionalità di ricerca, contatta il team di CSAM di Adobe Learning Manager.

## Modifiche all’interfaccia utente {#ui-changes}

### Pagina di creazione del corso

Durante il mapping dei corsi a un livello di abilità, l&#39;elenco delle abilità è incentrato sulla ricerca. In altre parole, cerca abilità e vedrai un elenco di abilità corrispondenti al termine cercato.

### Gruppi utente

#### Amministratore: pagina Allievi

Quando cerchi un utente, le **opzioni Scarica Allievo** ed **Esporta** scaricano lo stesso report. Nel frattempo, durante la ricerca di un gruppo di utenti, puoi scaricare gli utenti filtrati da quel gruppo di utenti. Durante la ricerca in un gruppo di utenti, l&#39;elenco **** Scarica allievi diventa **Scarica elenco Allievi per gruppo di utenti** L&#39;opzione **Esporta** scarica nuovamente l&#39;intero elenco.

## Modifiche ai report

* Le colonne Tag e Abilità nel Report corsi di formazione vengono modificate in Tag e Abilità.
* Aggiunto il report [Gamification Audit Trail](administrators/feature-summary/reports.md#gamification-audit-trail).
* Se un account contiene più di 280000 Allievi assegnati a un&#39;abilità, il report Allievo viene scaricato come CSV compresso.
Se l&#39;account ha meno di 250000 Allievi, lo stesso report viene scaricato come CSV.
Nella pagina Amministratore, seleziona **Amministratore** > **Abilità** > **Abilità** > **Allievi**. Il rapporto viene scaricato come CSV.
* Il [rapporto](administrators/feature-summary/reports.md#session-summary-report) Riepilogo sessione ha due nuove colonne: Informazioni sulla posizione e Area sulla posizione.

## Modifiche alla creazione di classi

In base alle impostazioni dell&#39;Amministratore[, l&#39;autore può [creare, modificare ed eliminare percorsi](administrators/feature-summary/classroom.md#add-classroom-location).](administrators/feature-summary/classroom.md#classroom-settings)

>[!NOTE]
>
>Durante l&#39;aggiunta di etichette di località e catalogo, gli autori (nella pagina di creazione del corso) e gli amministratori (nella pagina di istanza) vedranno un elenco compilato automaticamente rispettivamente di sedi ed etichette del catalogo.

In qualità di Amministratore, puoi imporre restrizioni a un Autore per modificare o eliminare la sede di un&#39;aula. Per ulteriori informazioni, visualizza [le impostazioni](administrators/feature-summary/classroom.md#classroom-settings) di Classroom.

## Modifiche al percorso di apprendimento flessibile

Tutti gli account (vecchi e nuovi) inizieranno includendo Scadenza iscrizione, Scadenza annullamento iscrizione e Limite di posti nell&#39;applicazione Allievo per un percorso di apprendimento flessibile.
Gli Allievi ora potranno iscriversi al Percorso di apprendimento flessibile senza selezionare alcuna istanza del corso.

## Nuovo trigger per i piani di apprendimento

È stato aggiunto un nuovo trigger alla pagina di configurazione del piano di apprendimento. Gli Autori e gli Amministratori saranno ora in grado di attivare azioni quando un Allievo non supera un modulo di un corso.

Visualizza [i piani](administrators/feature-summary/learning-plans.md) di apprendimento per ulteriori informazioni.

## Nuovo stato di invio

In qualità di Istruttore, ora puoi filtrare gli invii di file dagli Allievi in base a stato, Revisione finale, Invio in sospeso, Superato e Non superato.

Visualizza [lo stato](instructors/feature-summary/learners.md#filter-file-submissions) dell&#39;invio per ulteriori informazioni.

## Miglioramenti all&#39;elenco di controllo

Nella versione di marzo 2024 di Adobe Learning Manager, i miglioramenti apportati al flusso di lavoro dell&#39;elenco di controllo sono i seguenti:

### Non consentire lo stato di avanzamento in caso di mancato rispetto di una lista di controllo

Quando si crea una lista di controllo, un Autore può selezionare **Abilita** nella sezione Elenco di controllo obbligatorio. In questo modo si impedisce a un Allievo di procedere nel modulo se non supera l&#39;elenco di controllo. Possono procedere solo se superano la lista di controllo.

I revisori della lista di controllo, cioè istruttori o manager, possono quindi controllare lo stato della lista di controllo. I revisori possono anche esaminare l&#39;elenco di controllo di un Allievo in ordine sparso.

### Rivalutazione di una lista di controllo

Quando si crea una lista di controllo, un Autore può selezionare **Abilita** nella sezione Rivalutazione. In questo modo, un Manager o un Istruttore può rivalutare un Allievo fino a quando non supera l&#39;elenco di controllo.

Se il modulo è obbligatorio, la casella di controllo Rivalutazione è selezionata per impostazione predefinita.

Un istruttore o un manager può inoltre modificare lo stato di una lista di controllo da Non riuscito a Superato quando è abilitata la rivalutazione.

Nella pagina Elenco di controllo, un istruttore può visualizzare il numero di Allievi nello stato In sospeso. Come istruttore, puoi valutare un Allievo e superarlo o fallirlo. Se un Allievo si trova in uno stato negativo, puoi visualizzare l&#39;elenco di controllo solo quando la rivalutazione non è abilitata.

Questo errore indica che la **casella di controllo Abilita** non è stata selezionata nella sezione Rivalutazione durante la creazione dell&#39;elenco di controllo. Se questa casella di controllo è selezionata, puoi visualizzare il pulsante Visualizza/Rivaluta nella pagina Elenco di controllo dell&#39;istruttore.

La selezione del pulsante ti consente di rivalutare un Allievo e di contrassegnarlo come superato o non superato.

>[!NOTE]
>
>Entrambe queste funzionalità - Rivalutazione e Rendere obbligatoria la lista di controllo - si applicano solo ai moduli appena creati. Una volta pubblicato un corso, questi non possono essere attivati/disattivati.


Visualizza [Creare un elenco](authors/feature-summary/courses.md#checklist-fail) di controllo per ulteriori informazioni.

## Altri miglioramenti

### Notifiche e-mail relative alla sessione

Nelle versioni precedenti di Adobe Learning Manager, un Allievo non riceveva e-mail relative alla sessione, Dettagli sessione aggiornati, Invito alla sessione e Promemoria sessione quando:

* Gli Allievi hanno completato un corso,
* Nuove sessioni vengono aggiunte a un corso oppure
* Sono state apportate modifiche alle sessioni esistenti.

Nella versione di marzo 2024 di Adobe Learning Manager, le seguenti sono le nuove modifiche:

* Dettagli della sessione aggiornati e invito alla sessione (per Allievo e Istruttore)
   * Per le sessioni future, le e-mail relative ai **Dettagli della sessione aggiornate**, **agli Invito** alla sessione per gli Allievi iscritti e gli Istruttori attuali saranno deprecate. Per le sessioni passate, le e-mail con i **Dettagli della sessione aggiornate** e **l&#39;Invito** alla sessione per gli Allievi iscritti e gli Istruttori attuali rimarranno invariate.
* E-mail di promemoria (per Amministratore e Allievo)
   * Per le sessioni future, verranno inviate solo **le e-mail di promemoria** della sessione.

>[!NOTE]
>
>Le e-mail non dipendono dal completamento della sessione e del corso.


### Modifiche al sito di riferimento di AEM

In un sito di riferimento di AEM, abbiamo aggiunto il supporto per aggiungere il token di aggiornamento dell&#39;amministratore al token di accesso degli Allievi.

### Nascondere gli invii agli istruttori

Dopo che gli Allievi hanno caricato i propri file utilizzando il flusso di lavoro di invio del file, se un istruttore non intraprende alcuna azione (approvazione o rifiuto) sull&#39;invio, l&#39;URL di invio viene nascosto alla vista dopo un numero predefinito di giorni. Contatta i team di CSAM di Adobe Learning Manager per impostare o modificare il numero di giorni.

### Modifiche alla terminologia del prodotto

Abbiamo aggiunto le *colonne Istanza* e *Allievo* al vocabolario terminologico del prodotto.

### Modifiche alle app per dispositivi mobili

In questa versione dell&#39;applicazione per dispositivi mobili, gli Allievi possono pianificare e gestire i promemoria dei corsi scaduti. Facendo clic su una notifica di promemoria scaduta è possibile accedere alle seguenti opzioni:

* Annulla
* Vai al corso
* Ricordamelo di nuovo tra 3 giorni
* Ricordamelo di nuovo tra una settimana

Su Android: facendo clic sulla notifica push verrai indirizzato alla pagina Panoramica **del**corso.
Su iOS: facendo clic sulla notifica push verrai indirizzato alla home page dell&#39;app. Si tratta di una limitazione nota in iOS.

### Modifiche all&#39;elenco di controllo nell&#39;app Allievo su Salesforce

Se un Allievo non supera una lista di controllo, non può passare al modulo o al corso successivo. Quando la casella di controllo Elenco di controllo obbligatorio è selezionata, l&#39;Allievo non è in grado di andare avanti in un corso se non supera l&#39;elenco di controllo.

Come per l&#39;app Web, se un Allievo non supera un elenco di controllo sull&#39;app Salesforce, vedrà un messaggio e non andrà avanti.

### Modifiche in Connect VC

Nelle versioni correnti di Adobe Learning Manager, un Allievo viene contrassegnato come **Non frequentato** quando viene iscritto a una sessione di Connect VC, ma non soddisfa i criteri di completamento.

In questa versione, lo stato cambia in **Ancora da contrassegnare**.

### Etichettatura bianca in Adobe Learning Manager

L&#39;app mobile Adobe Learning Manager ora supporta l&#39;etichettatura bianca, il che significa che ora puoi rilasciare l&#39;app con il tuo marchio.

Per ulteriori informazioni, consulta l&#39;etichettatura bianca nell&#39;app [](white-label.md) Adobe Learning Manager per dispositivi mobili.

### Nuova colonna nei CSV di migrazione

In questa versione, è presente una nuova colonna facoltativa, uniqueLoId, nei seguenti CSV di migrazione.

* certification.csv
* course.csv
* learning_program.csv

>[!NOTE]
>
>La **colonna uniqueLoId** è facoltativa.


Se esegui una migrazione per aggiornare un corso, un piano formativo o una certificazione esistente, il corso o il piano di apprendimento o la certificazione con i **LOId** univoci viene aggiunto all&#39;app Autore.

Durante la migrazione, devi aggiornare i **valori LOId** univoci nei CSV per il corso, il piano di apprendimento o la certificazione, anche se si tratta di una colonna facoltativa.

Se la **colonna uniqueLoId** non viene aggiunta prima di eseguire la migrazione durante l&#39;aggiornamento del corso o del piano formativo esistente o della certificazione con **LOId** univoci, dopo la migrazione i **valori uniqueLOId** verranno sostituiti con valori NULL.

>[!NOTE]
>
>La colonna, **uniqueLoId**, non è applicabile al CSV Risorsa formativa.


>[!IMPORTANT]
>
>I valori delle colonne devono essere univoci in tutto l&#39;account. Non è possibile utilizzare lo stesso valore con un corso o una certificazione.

Scarica i CSV dal manuale](integration-admin/feature-summary/migration-manual.md#csv-specifications-and-sample-csvs) di [migrazione.


### Valutazione dell&#39;app

Un Allievo può fornire il proprio feedback sull&#39;app Adobe Learning Manager per migliorare ulteriormente l&#39;esperienza dell&#39;app. Se l&#39;Allievo ottiene una valutazione di almeno quattro stelle, viene visualizzata una finestra a comparsa che richiede all&#39;Allievo di valutare l&#39;app sul Play Store o sull&#39;App Store.

### Bluejeans ha raggiunto il suo fine vita (EOL) nel febbraio 2024

Volevamo informarvi che Bluejeans ha raggiunto il suo fine vita (EOL) nel febbraio 2024. Dopo febbraio 2024, Bluejeans non riceverà più aggiornamenti o supporto. I nostri team di CSAM e supporto ti assisteranno per qualsiasi domanda o dubbio tu possa avere durante questo periodo di transizione.

Visualizza [Connettori in Adobe Learning Manager](integration-admin/feature-summary/connectors.md) per ulteriori informazioni sulla configurazione dei connettori.

### Modifiche al report Accesso

Il report Accesso sarà disponibile solo per gli ultimi cinque trimestri. Se un amministratore di integrazione richiede il download su richiesta dell&#39;esportazione unificata con **accesso all&#39;accesso** selezionato, Adobe Learning Manager visualizzerà un messaggio di errore. Tuttavia, non vi è alcun impatto su altri rapporti.

### Modifiche ADFS

I campi Tipo di dipendente e ID dipendente di ADFS sono ora disponibili in Adobe Learning Manager, in base alle mappature.

## Modifiche alle API introdotte da questa versione

### API per Allievi

In questa versione, abbiamo aggiunto il supporto API per consentire agli Allievi di visualizzare il logo del branding e i temi personalizzati a livello di gruppo di utenti.

Le API /account e /user?include=account restituiscono quattro campi, che vengono sostituiti in modo specifico per il campo attivo dell&#39;utente appartenente a logoUrl, logoStyling e themeData.

### Nuovi attributi

Un nuovo attributo, isExpiredSubmission, in learningObjectResource, che mostra se l&#39;invio nella risorsa è scaduto o meno.

* API GET /account: restituisce il nuovo attributo **expireSubmissionDuration** X, dove X è il numero di giorni impostato. Se non impostato, verrà restituito 0
* L&#39;API GET /LO con la risorsa include il nuovo attributo **isExpiredSubmission**&quot; True o False.
   * True, se l&#39;invio è scaduto e &quot;submissionUrl&quot; non viene visualizzato.
   * Se False, l&#39;invio non è scaduto e viene recuperato &quot;submissionUrl&quot;.

### Modifiche API nell&#39;elenco di controllo

Un corso può essere composto da diversi moduli di cui Checklist è un tipo di modulo. Questo modulo dell&#39;elenco di controllo viene valutato dall&#39;istruttore e può essere contrassegnato come Non superato o Riuscito in base alla valutazione.

Ma in entrambi i casi lo stato dell&#39;elenco di controllo è contrassegnato come Completato e in questo modo, il corso viene contrassegnato come Completato.

In questa versione, l&#39;API di LO include il parametro *isChecklistMandatory*. Se il valore è True, l&#39;elenco di controllo è obbligatorio.

### Supporto per più impostazioni locali

Un amministratore può ora scaricare il rapporto di feedback L1 nella lingua di sua scelta. Tuttavia, non è ancora possibile scaricare i report di feedback L1 per Power BI. Nella richiesta API, utilizza il parametro preferredLocale per specificare la lingua di tua scelta.

### Modifiche nel conteggio del riepilogo delle istanze

Questo è applicabile agli account in cui le iscrizioni a un corso in aula/VC sono più di 1000.

Se il numero è inferiore a 1000, le iscrizioni invalidano la cache e restituiscono i valori aggiornati in una chiamata API GET Summary, ad esempio number of enrollment, completion e seatLimit.

Se l&#39;account è abilitato per questa funzionalità e il numero di iscrizioni è superiore a 1000, i valori vengono recuperati dalla cache.

### Tracciati obsoleti

Al momento, le API di Learning Manager seguono una struttura di dati a grafico, che consente di recuperare i dati attraversando il modello API attraverso include. Anche se è possibile attraversare un&#39;API fino a sette livelli, recuperare i dati utilizzando una singola chiamata API è costoso dal punto di vista computazionale.

È consigliabile che tutti i clienti esistenti e nuovi effettuino chiamate di piccole dimensioni più volte anziché un&#39;unica chiamata di grandi dimensioni. Questo approccio impedirà il caricamento di dati indesiderati nella chiamata.

#### Quali tracciati sono deprecati

I seguenti percorsi sono obsoleti:

* /learningObjects
   * Tracciati obsoleti:
      * enrollment.loInstance.loResources.resources
      * instances.loResources.resources
   * Tracciati esistenti:
      * enrollment.loInstance
      * instances.loResources
* /learningObjects/{id}
   * Percorso obsoleto:
      * enrollment.instances.subLoInstances.learningObject
   * Percorso esistente:
      * enrollment.instances.subLoInstances
* /Iscrizioni
   * Percorso obsoleto:
      * loInstance.learningObject.enrollment
   * Nuovo tracciato:
      * loInstance.learningObject
* /learningObjects/{id}
   * Percorso obsoleto:
      * instance.subLoInstances.learningObject.enrollment.loResourceGrades
   * Nuovo tracciato:
      * instance.subLoInstances

### Accesso all&#39;accesso e Archiviazione del report di verifica utente per l&#39;API Job

Con questa versione, l&#39;API Job conserverà Login Access Report fino a cinque trimestri e User Audit Report per sei mesi. Se si desidera scaricare i dati più vecchi di questo periodo di tempo, è necessario passare il parametro archive, specificando trimestre e anno. Fare riferimento al payload di esempio.

```
{
    "data": {
        "type": "job",
        "attributes": {
            "description": "description of your choice",
            "jobType": "generateLoginAccessReport",
            "payload": {
                "fromDate": "2023-04-01T18:30:00.000Z",
                "toDate": "2023-04-30T18:30:00.000Z",
                "archive": {
                    "quarter": "4",
                    "year": "2021"
                }
            }
        }
    }
}
```

Se si tenta di scaricare il report Accesso che supera i **** cinque trimestri, verrà visualizzato un messaggio di errore. Un messaggio di errore simile viene visualizzato se si tenta di scaricare il **rapporto di controllo** utente che va oltre i sei mesi.

### API deprecate

Visualizza [le deprecazioni delle API in Adobe Learning Manager](api-deprecations-list.md) per un elenco cumulativo di tutte le API deprecate nel prodotto.

## Bug corretti in questo aggiornamento {#bug-fixes}

* Quando un Allievo viene iscritto a un corso e tenta di iscriversi a un altro corso, viene visualizzato un messaggio di avviso.
* Un gruppo di utenti, anche dopo essere stato eliminato, è visibile nella ricerca.
* Quando gli utenti attivano molte trascrizioni degli Allievi con una grande quantità di dati, la coda delle trascrizioni degli Allievi viene bloccata e impedisce una nuova richiesta.
* Se un account bambino richiede all&#39;account genitore di condividere un report, l&#39;account principale non è in grado di farlo.
* Gli URL di un corso e di un percorso di apprendimento reindirizzano a posizioni errate.
* Un Allievo visualizza in modo intermittente l&#39;istanza di un corso diverso facendo clic sul collegamento del corso nella pagina del catalogo.
* Il **pulsante Annulla iscrizione** non viene visualizzato come previsto dopo la prima registrazione, ma viene visualizzato dopo un aggiornamento.
* Non è possibile salvare il contenuto o un quiz il cui nome contiene uno spazio vuoto.
* Nei corsi approvati dal Manager, puoi iscrivere nuovamente gli Allievi a un gruppo di utenti.
* In alcuni casi, se si tenta di aggiungere un ulteriore campo attivo, viene visualizzato il messaggio di errore &quot;Impossibile salvare i campi attivi&quot;.
* Il testo trabocca nel nome di un corso all&#39;interno di una scheda del corso nella sezione Corsi correlati.
* Dopo il cambio di istanza e l&#39;iscrizione di un Allievo all&#39;istanza, le istanze precedenti esistono ancora nel calendario di Outlook.
* Quando un Allievo di un account tra pari tenta di selezionare la miniatura di un corso, viene visualizzato un messaggio di errore.
* Quando gli Allievi si iscrivono a un corso, ricevono più notifiche per l&#39;iscrizione.
* Se un utente modifica manualmente il nome dei cataloghi creati in un connettore, vengono creati nuovi cataloghi e i corsi vengono pubblicati nei cataloghi errati.
* Gli utenti appartenenti ad account inattivi continuano a ricevere e-mail di iscrizione.

### Correzioni di bug relativi alle API

* L&#39;API GET/USERS non recupera i dettagli di un Manager.
* In un account, gli utenti sono stati creati tramite un&#39;importazione utente FTP pianificata durante un periodo di inattività pianificato.
* Nell&#39;app per dispositivi mobili o in modalità immersiva, dopo aver eliminato o ritirato un&#39;istanza del corso e aver selezionato l&#39;istanza attiva successiva, viene visualizzato il **pulsante Registra interesse** invece di **Iscriviti**.
* Quando un Allievo di un account peer tenta di selezionare la miniatura di un corso utilizzando l&#39;API Learning Object, viene visualizzato l&#39;errore 403 Forbidden.

## Requisiti di sistema

Visualizza [i requisiti di sistema di](system-requirements.md) Adobe Learning Manager.

## Versioni precedenti di Adobe Learning Manager

* [Versione di novembre 2023](whats-new-november-2023.md)
* [Versione di luglio 2023](whats-new-2023-july.md)
