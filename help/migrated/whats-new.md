---
description: Scopri le nuove funzioni e i miglioramenti della versione di marzo 2024 di Adobe Learning Manager
jcr-language: en_us
title: Riepilogo delle nuove funzioni
contentowner: jayakarr
exl-id: 603f1f1c-bf8d-4807-b9f7-b10ded19a91e
source-git-commit: 898103cd6cda48bf4303c660b6c635d3208deca5
workflow-type: tm+mt
source-wordcount: '3666'
ht-degree: 1%

---

# Riepilogo delle nuove funzioni {#new-features-summary}

Scopri le nuove funzioni e i miglioramenti nella versione di marzo 2024 di Adobe Learning Manager.

## Novità di questa versione {#whatsnewandchanged}

### Importa abilità da origini esterne

Importa le abilità dai provider di contenuti, come LinkedIn e Go1, utilizzando i rispettivi connettori. Questo miglioramento fa parte dell’obiettivo verso la capacità di Learning Manager di integrarsi con cloud di abilità e sistemi di gestione dei talenti esterni. Le abilità importate verranno aggiunte alle abilità definite dall’amministratore in Learning Manager e saranno disponibili per gli Autori durante il flusso di lavoro di creazione del corso. Sono stati apportati miglioramenti anche alla funzionalità di ricerca delle abilità su tutta la piattaforma, per offrire un’esperienza di ricerca migliore quando l’account dispone di un numero elevato di abilità.

Visualizza [Importa abilità](administrators/feature-summary/import-skills-external-sources.md) per saperne di più.

### Personalizzazione del branding

Ora sarai in grado di personalizzare alcuni elementi dell&#39;interfaccia utente: il nome dell&#39;organizzazione, il logo e il tema dell&#39;interfaccia in base ai gruppi di utenti disponibili nell&#39;account. Ad esempio, un’organizzazione con più divisioni può impostare un logo personalizzato e un tema dell’interfaccia utente da visualizzare per ciascuna divisione.

>[!NOTE]
>
>Questa funzione di branding multipla non si applica alla vista dell’Amministratore. Vedranno sempre il branding a livello di organizzazione nel loro account. Questo perché si tratta di una funzione rivolta agli Allievi e gli Amministratori potrebbero non volerla nel loro account.

Visualizza [Più elementi di branding personalizzati](administrators/feature-summary/themes.md#multiple-branding) per ulteriori informazioni.


## Modifiche per gli account con una base di utenti di grandi dimensioni

### Amministratore: pagine del corso o del percorso di apprendimento

Se un numero elevato di Allievi è iscritto al corso, ad esempio, più di 50.000, l’elenco degli Allievi non verrà visualizzato. Puoi cercare un Allievo nel *Cerca Allievi* barra di ricerca o selezionare **Scarica** nella parte superiore della barra di ricerca, scarica l’elenco degli allievi.

### Pagina Amministratore: Allievi

Durante la ricerca di un utente, **Scarica Allievo** e **Esporta** opzioni scarica lo stesso report. Nel frattempo, durante la ricerca di un gruppo di utenti, ora puoi scaricare gli utenti filtrati da quel gruppo di utenti. Durante la ricerca in un gruppo di utenti, **Scarica elenco Allievi** modifiche a **Scarica l’elenco degli Allievi per il gruppo di utenti** La **Esporta** viene scaricato nuovamente l&#39;intero elenco.

### Pagina Amministratore: Utenti

#### Utenti interni

Se il numero di utenti supera, ad esempio, 50.000, verrà visualizzato un messaggio che richiede di scaricare i dati per un&#39;analisi più dettagliata in un secondo momento. La barra di ricerca è ora in primo piano e visualizza un utente nel formato *Nome, e-mail | UUID*.

>[!NOTE]
>
>L’UUID viene visualizzato solo se è abilitato per l’account.

#### Utenti esterni

Per gli utenti esterni, si applica lo stesso comportamento. Se il numero di utenti è elevato, puoi scaricare gli utenti e anche recuperare i dettagli di un utente dopo una ricerca nel formato *Nome, e-mail | UUID*.

#### Pagina Pulizia utente

Nella pagina Pulizia utente, per gli utenti eliminati è stata rimossa la funzionalità di ordinamento su **Data di eliminazione**. Puoi ordinare solo in base agli UUID.

### Pagine Amministrazione - Istanza

#### Corso o percorso di apprendimento

Se il numero di iscrizioni è elevato, Learning Manager di Adobe non visualizzerà il numero di Allievi. Verrà invece visualizzata un’icona, selezionabile, che consente di visualizzare il numero di Allievi e passare alla pagina Allievi.

Il numero di Allievi verrà visualizzato come valore approssimativo. Ad esempio, se il numero di Allievi è superiore a 50.000, il valore verrà visualizzato come 50K+.

### Amministratore: pagine L1/L3

Nella pagina Feedback L1, se il numero di iscrizioni ai corsi è elevato, l’elenco degli allievi non viene visualizzato. Puoi invece esportare l’elenco degli utenti per un’analisi più dettagliata in un secondo momento.

La ricerca supporta il completamento automatico e i risultati sono limitati all&#39;istanza selezionata.

#### Pagina Presenze e punteggio

Nella pagina, quando si esegue una ricerca in un utente, la ricerca viene eseguita in tutte le istanze disponibili. Tuttavia, il risultato è per l&#39;istanza selezionata.

Nella pagina Frequenza, se cerchi un gruppo di utenti e il numero di utenti supera i 10.000 nel gruppo di utenti indipendentemente dall’iscrizione, puoi eseguire solo azioni di livello collettivo. Non potrai visualizzare l’elenco degli utenti.

Se il numero di utenti nel gruppo di utenti è inferiore a 10.000, puoi eseguire azioni a livello di singolo utente e azioni a livello di blocco. In questo caso, l’elenco degli utenti non viene disattivato.

### Pagina Amministratore: Certificazioni

Nelle versioni correnti di Learning Manager di Adobe, se è presente un numero elevato di utenti iscritti a una certificazione, non potrai visualizzare gli Allievi con iscrizione annullata dal **Stato** Menu a discesa disattivato.

In questa versione di Adobe di Learning Manager, se il numero di utenti iscritti è elevato, il **Stato** nel menu a discesa vengono visualizzate solo due opzioni: **Iscritto** e **Annullata iscrizione**. Opzione **Iscritto** è selezionato per impostazione predefinita. Se si seleziona **Annullata iscrizione**, viene visualizzato l’elenco degli allievi non iscritti.

#### Modifiche al gruppo di utenti

Nel caso di un gruppo di utenti, se il numero di utenti nel gruppo è inferiore, ad esempio, a 50.000, il **Stato** Nel menu a discesa vengono visualizzate tutte le opzioni Certified, Assigned e Expiring.

Se il numero di utenti in un gruppo di utenti è elevato, il **Stato** nel menu a discesa vengono visualizzate solo due opzioni: **Iscritto** e **Annullata iscrizione**, in base al nuovo design.

### Tabella di confronto

<table>
    <tbody>
        <tr>
            <td><b>Pagina</b></td>
            <td><b>Prima della modifica della soglia</b></td>
            <td><b>Dopo la modifica della soglia</b></td>
        </tr>
        <tr>
            <td>Amministratore: istanza del corso</td>
            <td>Le istanze vengono visualizzate come progettate con:
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
                    <li>Se il numero di iscrizioni supera la soglia predefinita, ALM non visualizzerà il conteggio; sostituirà il conteggio con un’icona, che quando viene selezionata visualizza il numero effettivo di allievi e un collegamento per passare alla pagina Allievi.</li>
                    <li>Il numero di iscrizioni verrà visualizzato in un formato approssimativo. Ad esempio, se il numero è maggiore di 50.000, il conteggio verrà visualizzato come 50K+ a livello di corso.</li>
                </ul>
            </td>
        </tr>
        <tr>
            <td>Pagina Amministratore: Allievi</td>
            <td>
                    <ul>
                        <li>Per ogni istanza viene visualizzato l’elenco degli Allievi.</li>
                        <li>Puoi cercare un utente o un gruppo di utenti iscritto a un corso.</li>
                        <li>Il report esportato non è costituito da alcun filtro per Gruppo utenti.</li>
                    </ul>
            </td>
            <td>
                <ul>
                    <li>La selezione dell'istanza è disabilitata.</li>
                    <li>Scarica elenco Allievi scarica anche gli stessi dati ad eccezione di un caso. Se cerchi un gruppo di utenti e quindi selezioni Scarica elenco allievi, verranno scaricati i dati di quel gruppo di utenti.</li>
                </ul>
            </td>
        </tr>
        <tr>
            <td>Pagina di feedback L1/L3 dell’amministratore</td>
            <td>
                <p>Nessun cambiamento nel comportamento esistente</p>
            </td>
            <td>
                <ul>
                    <li>La selezione dell'istanza è disabilitata.</li>
                    <li>Se l’iscrizione a un corso supera i 50.000, ALM non elenca gli Allievi e visualizza solo la barra di ricerca. Se l’iscrizione è inferiore a 50.000, ALM visualizza sia l’elenco degli Allievi che la barra di ricerca.</li>
                    <li>L'inserzione è disabilitata per impostazione predefinita.</li>
                </ul>
            </td>
        </tr>
        <tr>
            <td>Pagina Amministratore: Presenze e punteggio</td>
            <td>
                <p>Nessun cambiamento nel comportamento esistente</p>
            </td>
            <td>
                <ul>
                    <li>La selezione dell’istanza è disattivata durante la ricerca di un utente.</li>
                    <li>Se il numero di utenti supera, ad esempio, 50.000, verrà visualizzato un messaggio aggiuntivo per scaricare i dati per un'analisi più dettagliata in un secondo momento. La barra di ricerca è ora in evidenza e visualizza un utente nel formato Nome, e-mail | UUID.</li>
                    <li>Se il numero di utenti nel gruppo di utenti è inferiore a 10.000, indipendentemente dall’iscrizione, è possibile eseguire azioni a livello di singolo utente e azioni di massa. In questo caso, l’elenco degli utenti non viene disattivato.</li>
                </ul>
            </td>
        </tr>
        <tr>
            <td>Pagina Punteggio quiz L2 per Amministratore</td>
            <td>
                    <ul>
                        <li>Viene implementata anche la ricerca utente.</li>
                    </ul>
            </td>
            <td>
                <ul>
                    <li>Viene implementata anche la ricerca utente. Mentre la ricerca con typeahead viene eseguita a livello di LO, l’elenco viene filtrato in base all’istanza attualmente selezionata.</li>
                </ul>
            </td>
        </tr>
        <tr>
            <td>Pagina Amministratore: Utenti (Interni, Esterni)</td>
            <td>
                    <ul>
                        <li>L’ID e-mail viene visualizzato durante la ricerca di un utente.</li>
                    </ul>
            </td>
            <td>
                <ul>
                    <li>Se il numero di utenti supera, ad esempio, 50.000, verrà visualizzato un messaggio aggiuntivo per scaricare i dati per un'analisi più dettagliata in un secondo momento. La barra di ricerca è ora in evidenza e visualizza un utente nel formato Nome, e-mail | UUID.</li>
                    <li>Nella pagina Pulizia utente, per gli utenti eliminati, è stata rimossa la funzionalità di ordinamento in data **Data eliminazione**. Puoi ordinare solo in base agli UUID.</li>
                </ul>
            </td>
        </tr>
        <tr>
            <td>Istruttori - Invio</td>
            <td>
                    <ul>
                        <li>Paginazione dei moduli da inviare.</li>
                        <li>In qualità di Istruttore, ora puoi filtrare i file inviati dagli Allievi in base a stato, revisione finale, invio in sospeso, esito positivo e non riuscito. </li>
                    </ul>
            </td>
            <td>
                <ul>
                    <li>È possibile cercare solo utenti e non gruppi di utenti in tale istanza.</li>
                </ul>
            </td>
        </tr>
        <tr>
            <td>Conta sull’anteprima come pagina Allievo</td>
            <td>
                    <ul>
                        <li>Il conteggio include i dati dell'iscrizione di ordine superiore.</li>
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

In questa versione, è stata migliorata l’esperienza di ricerca. I risultati della ricerca vengono recuperati in base non solo ai metadati, ma anche alla ricerca semantica e nel contenuto per derivare i risultati in base alla precisione, all’attualità e al contenuto pertinente.

Questa modifica si riflette su quanto segue:
* Catalogo e pagina Il mio apprendimento: l’azione al passaggio del mouse su corso, percorso di apprendimento e certificazione è stata rimossa.
* Aspetto della barra di ricerca.
* Sono stati aggiunti tag di filtro nell’app di apprendimento.

Per abilitare le funzionalità di ricerca, contatta il team CSAM di Learning Manager Adobe.

## Modifiche ai report

* Le colonne Tag e Abilità nel report dei corsi di formazione vengono modificate in Tag e Abilità.
* Ha aggiunto il report [Prova di verifica della gamification](administrators/feature-summary/reports.md#gamification-audit-trail).
* Se un account contiene più di 280000 Allievi assegnati a un’abilità, il report Allievo dell’abilità viene scaricato come un file CSV compresso.
Se l’account contiene meno di 250000 Allievi, lo stesso report viene scaricato come file CSV.
Nella pagina Amministrazione, seleziona **Amministratore** > **Abilità** > **Abilità** > **Allievi**. Il report viene scaricato come CSV.
* La [Report di riepilogo della sessione](administrators/feature-summary/reports.md#session-summary-report) ha due nuove colonne: Informazioni sulla posizione e Area geografica.

## Modifiche alla creazione di classi

In base a [Impostazioni amministratore](administrators/feature-summary/classroom.md#classroom-settings), in qualità di Autore, puoi [creare, modificare ed eliminare posizioni](administrators/feature-summary/classroom.md#add-classroom-location).
>[!NOTE]
>
>Durante l’aggiunta di etichette per località e cataloghi, gli Autori (nella pagina di creazione del corso) e gli Amministratori (nella pagina delle istanze) visualizzeranno rispettivamente un elenco di località e di etichette del catalogo compilato automaticamente.

In qualità di Amministratore, puoi applicare restrizioni a un Autore per modificare o eliminare un’aula. Visualizza [Impostazioni classe](administrators/feature-summary/classroom.md#classroom-settings) per ulteriori informazioni.

## Modifiche a un percorso di apprendimento flessibile

Tutti gli account (vecchi e nuovi) in inizieranno a includere Scadenza iscrizione, Scadenza annullamento iscrizione e Limite di posti nell’app per Allievi per un percorso di apprendimento flessibile.
Gli Allievi ora potranno iscriversi a un percorso di apprendimento flessibile senza selezionare alcuna istanza del corso.

## Nuovo attivatore per i piani di apprendimento

Un nuovo attivatore è stato aggiunto alla pagina di configurazione del piano di apprendimento. Autori e Amministratori ora potranno attivare azioni quando un Allievo non supera un modulo di un corso.

Visualizza [Piani di apprendimento](administrators/feature-summary/learning-plans.md) per ulteriori informazioni.

## Nuovo stato di invio

In qualità di Istruttore, ora puoi filtrare i file inviati dagli Allievi in base a stato, revisione finale, invio in sospeso, esito positivo e non riuscito.

Visualizza [Stato di invio](instructors/feature-summary/learners.md#filter-file-submissions) per ulteriori informazioni.

## Miglioramenti all’elenco di controllo

Nella versione di marzo 2024 di Adobe Learning Manager, i miglioramenti apportati al flusso di lavoro dell’elenco di controllo sono i seguenti:

### Non consentire l’avanzamento in caso di mancato superamento di un elenco di controllo

Quando si crea un elenco di controllo, un Autore può selezionare **Abilita** nella sezione Elenco di controllo obbligatorio. In questo modo si impedisce agli Allievi di continuare nel modulo se non rientrano nell’elenco di controllo. Possono procedere solo se superano l&#39;elenco di controllo.

I revisori dell’elenco di controllo, ad esempio istruttori o manager, possono quindi controllare lo stato dell’elenco di controllo. I revisori possono inoltre rivedere l’elenco di controllo di un Allievo in modo non corretto.

### Nuova valutazione di un elenco di controllo

Quando si crea un elenco di controllo, un Autore può selezionare **Abilita** nella sezione Rivalutazione. In questo modo, un manager o un istruttore può rivalutare un allievo fino a quando non supera l’elenco di controllo.

Se il modulo è obbligatorio, la casella di controllo per la rivalutazione è selezionata per impostazione predefinita.

Un istruttore o un manager può anche modificare lo stato di un elenco di controllo da Non riuscito a Superato quando è abilitata la rivalutazione.

Nella pagina Elenco di controllo, un Istruttore può visualizzare il numero di allievi con stato In sospeso. In qualità di Istruttore, puoi valutare un Allievo e superarlo o non superarlo. Se un Allievo si trova in uno stato di errore, è possibile visualizzare l’elenco di controllo solo quando la rivalutazione non è abilitata.

Ciò significa che il **Abilita** la casella di controllo non è stata selezionata nella sezione Rivalutazione durante la creazione dell&#39;elenco di controllo. Se questa casella di controllo è selezionata, nella pagina Elenco di controllo Istruttore sarà disponibile il pulsante Visualizza/Rivaluta.

Selezionando il pulsante puoi rivalutare un Allievo e contrassegnarlo come superato o non riuscito.

>[!NOTE]
>
>Entrambe queste funzionalità, Nuova valutazione e Impostazione dell’elenco di controllo come obbligatorio, si applicano solo ai moduli appena creati. Una volta pubblicato un corso, non è possibile attivarlo/disattivarlo.


Visualizza [Creare un elenco di controllo](authors/feature-summary/courses.md#checklist-fail) per ulteriori informazioni.

## Altri miglioramenti

### Notifiche e-mail relative alla sessione

Nelle versioni precedenti dell’Adobe di Learning Manager, un Allievo non inviava e-mail relative alla sessione, Dettagli della sessione aggiornati, Invito alla sessione e Promemoria della sessione nei seguenti casi:

* Gli Allievi hanno completato un corso,
* Le nuove sessioni vengono aggiunte a un corso, oppure
* Sono state apportate modifiche alle sessioni esistenti.

Nella versione di marzo 2024 di Adobe Learning Manager, sono state introdotte le seguenti nuove modifiche:

* Dettagli della sessione aggiornati e Invito alla sessione (per Allievo e Istruttore)
   * Per le sessioni future, invia e-mail per **Dettagli della sessione aggiornati**, **Invito alla sessione** per gli Allievi iscritti e gli Istruttori correnti diventeranno obsoleti. Per le sessioni passate, e-mail per **Dettagli della sessione aggiornati** e **Invito alla sessione** per gli Allievi iscritti e gli Istruttori correnti rimarranno invariati.
* E-mail di promemoria (per Amministratore e Allievo)
   * Solo per le sessioni future **Promemoria sessione** verranno inviate le e-mail.

>[!NOTE]
>
>Le e-mail non dipendono dalla sessione e dal completamento del corso.


### Modifiche al sito di riferimento dell’AEM

In un sito di riferimento AEM, è stato aggiunto il supporto per aggiungere il token di aggiornamento amministratore al token di accesso degli allievi.

### Nascondere gli invii degli istruttori

Dopo che gli Allievi hanno caricato i file tramite il flusso di lavoro per l’invio, se un Istruttore non intraprende alcuna azione (approvazione o rifiuto) sull’invio, l’URL di invio viene nascosto dalla visualizzazione dopo un numero predefinito di giorni. Per impostare o modificare il numero di Adobi, contatta i team CSAM di Learning Manager.

### Modifiche della terminologia del prodotto

Abbiamo aggiunto le colonne *Istanza* e *Allievo* al vocabolario della terminologia del prodotto.

### Modifiche all’app per dispositivi mobili

In questa versione dell’app per dispositivi mobili, gli Allievi possono pianificare e gestire i promemoria del corso scaduti. Facendo clic su una notifica di promemoria scaduta è possibile accedere alle seguenti opzioni:

* Annulla
* Vai al corso
* Ricordamelo tra 3 giorni
* Ricordamelo tra una settimana

Su Android: facendo clic sulla notifica push verrai indirizzato al **Panoramica del corso** pagina.
Su iOS: facendo clic sulla notifica push verrai indirizzato alla pagina Home dell’app. Si tratta di una limitazione nota in iOS.

### Modifiche all’elenco di controllo nell’app per Allievi in Salesforce

Se un Allievo non supera un elenco di controllo, non può passare al modulo o al corso successivo. Quando la casella di controllo Elenco di controllo obbligatorio è selezionata, l’Allievo non è in grado di proseguire in un corso se non supera l’elenco di controllo.

Come per la web app, se un Allievo non supera un elenco di controllo nell’app Salesforce, visualizzerà un messaggio e non procederà.

### Modifiche in Connect VC

Nelle versioni correnti di Learning Manager di Adobe, un Allievo viene contrassegnato **Non partecipato** quando sono iscritti a una sessione Connect VC, ma non soddisfano i criteri di completamento.

In questa versione, lo stato diventa **Ancora da segnare**.

### Etichettatura bianca in Adobe Learning Manager

L’app mobile Learning Manager di Adobe ora supporta l’etichettatura bianca, il che significa che ora puoi rilasciare l’app con il tuo marchio.

Visualizza etichettatura bianca in [Adobe dell’app mobile Learning Manager](white-label.md) per ulteriori informazioni.

### Nuova colonna nei CSV di migrazione

In questa versione, è presente una nuova colonna facoltativa, uniqueLoId, nei seguenti CSV di migrazione.

* certification.csv
* course.csv
* learning_program.csv

La colonna uniqueLoId non è applicabile al file CSV delle risorse formative.

>[!IMPORTANT]
>
>I valori delle colonne devono essere univoci in tutto l’account. Non è possibile utilizzare lo stesso valore con un corso o una certificazione.

Scarica i file CSV da [Manuale di migrazione](integration-admin/feature-summary/migration-manual.md#csv-specifications-and-sample-csvs).


### Valutazione app

Un Allievo può fornire il proprio feedback sull’app Adobe Learning Manager per migliorare ulteriormente l’esperienza dell’app. Se l’Allievo valuta l’app a quattro stelle o più, viene visualizzata una finestra a comparsa in cui richiede di valutare l’app su Play Store o App Store.

### Bluejeans ha raggiunto la fine del suo ciclo di vita (EOL) nel febbraio 2024

Volevamo informarti che Bluejeans ha raggiunto la fine del suo ciclo di vita (EOL) a febbraio 2024. Dopo febbraio 2024, Bluejeans non riceverà più aggiornamenti o supporto. Il nostro CSAM e i team di supporto ti assisteranno in caso di domande o dubbi durante questo periodo di transizione.

Visualizza [Connettori in Adobe Learning Manager](integration-admin/feature-summary/connectors.md) per ulteriori informazioni sulla configurazione dei connettori.

### Modifiche al report Accesso

Il report Accesso sarà disponibile solo per gli ultimi cinque trimestri. Se un Amministratore dell’integrazione richiede il download su richiesta di Unified Export con **Accesso** Se questa opzione è selezionata, nell’Adobe Learning Manager viene visualizzato un messaggio di errore. Tuttavia, non vi è alcun impatto sulle altre relazioni.

### Modifiche ADFS

I campi Tipo di dipendente e ID dipendente da ADFS sono ora disponibili su Adobe Learning Manager, in base alle mappature.

## Modifiche alle API introdotte da questa versione

### API Allievo

In questa versione, è stato aggiunto il supporto API per consentire agli Allievi di visualizzare il logo di branding e i temi personalizzati a livello di gruppo di utenti.

Le API /account e /user?include=account restituiscono quattro campi, che vengono sostituiti in base al campo attivo dell’utente e appartengono a logoUrl, logoStyling e themeData.

### Nuovi attributi

Un nuovo attributo, isExpiredSubmission, in learningObjectResource, che indica se l&#39;invio nella risorsa è scaduto o meno.

* API GET /account: restituisce un nuovo attributo **expireSubmissionDuration** X, dove X è il numero di giorni impostati. Se non impostato, verrà restituito 0
* L’API GET/LO con risorsa include un nuovo attributo **isExpiredSubmission**&quot; True o False.
   * True se l&#39;inoltro è scaduto e &quot;submissionUrl&quot; non viene visualizzato.
   * Se è False, l&#39;invio non è scaduto e &quot;submissionUrl&quot; viene recuperato.

### Modifiche API nell’elenco di controllo

Un corso può essere costituito da diversi moduli, di cui Checklist è un tipo di modulo. Questo modulo dell’elenco di controllo viene valutato dall’istruttore e, in base alla valutazione, può essere contrassegnato come Non riuscito o Riuscito.

Ma in entrambi i casi lo stato dell’elenco di controllo è contrassegnato come Completato e in questo modo, il corso viene contrassegnato come Completato.

In questa versione, l’API LO include il parametro *isChecklistMandatory*. Se il valore è True, l&#39;elenco di controllo è obbligatorio.

### Supporto per più lingue

Un Amministratore può ora scaricare il report del feedback L1 nella lingua che preferisce. Tuttavia, non è ancora possibile scaricare i report di feedback L1 per Power BI. Nella richiesta API, utilizza il parametro preferredLocale per specificare le impostazioni locali desiderate.

### Modifiche nel riepilogo del conteggio delle istanze

Questo è applicabile agli account in cui le iscrizioni a un corso in aula/aula virtuale sono superiori a 1000.

Se il numero è inferiore a 1000, le iscrizioni invalidano la cache e restituiscono i valori aggiornati in una chiamata API Summary di GET, ad esempio il numero di iscrizioni, il completamento e il limite di partecipanti.

Se l’account è abilitato per questa funzione e il numero di iscrizioni è superiore a 1000, i valori vengono recuperati dalla cache.

### Percorsi obsoleti

Al momento, le API di Learning Manager seguono una struttura di dati del grafico, che consente di recuperare i dati attraversando il modello API tramite include. Sebbene sia possibile attraversare un’API fino a sette livelli, recuperare i dati utilizzando una singola chiamata API è computazionalmente costoso.

Si consiglia a tutti i clienti nuovi ed esistenti di effettuare chiamate di piccole dimensioni più volte anziché una chiamata di grandi dimensioni. Questo approccio impedisce il caricamento di dati indesiderati nella chiamata.

#### Percorsi obsoleti

I percorsi seguenti sono obsoleti:

* /learningObjects
   * Percorsi obsoleti:
      * enrollment.loInstance.loResources.resources
      * instances.loResources.resources
   * Percorsi esistenti:
      * enrollment.loInstance
      * instances.loResources
* /learningObjects/{id}
   * Percorso obsoleto:
      * enrollment.instances.subLoInstances.learningObject
   * Percorso esistente:
      * enrollment.instances.subLoInstances
* /enrollments
   * Percorso obsoleto:
      * loInstance.learningObject.enrollment
   * Nuovo percorso:
      * loInstance.learningObject
* /learningObjects/{id}
   * Percorso obsoleto:
      * instance.subLoInstances.learningObject.enrollment.loResourceGrades
   * Nuovo percorso:
      * instance.subLoInstances

### Modifiche relative all’archiviazione dei report di accesso e di audit degli utenti per l’API dei processi

Con questa versione, l’API dei processi conserverà il Report di accesso fino a cinque trimestri e il Report di audit utente per sei mesi. Se si desidera scaricare i dati precedenti a questo periodo di tempo, è necessario passare il parametro di archivio, specificando trimestre e anno. Fate riferimento al payload di esempio.

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

Se si tenta di scaricare **Accesso** report oltre i cinque trimestri, viene visualizzato un messaggio di errore. Un messaggio di errore simile viene visualizzato se si tenta di scaricare **Controllo utente** che va oltre i sei mesi.

### API obsolete

Visualizza [Rimozione delle API in Adobe Learning Manager](api-deprecations-list.md) per un elenco cumulativo di tutte le API obsolete nel prodotto.

## Bug corretti in questo aggiornamento {#bug-fixes}

* Quando un Allievo si iscrive a un corso e tenta quindi di iscriversi a un altro corso, viene visualizzato un messaggio di avviso.
* Un gruppo di utenti, anche dopo essere stato eliminato, è visibile in Cerca.
* Quando gli utenti attivano molte Trascrizioni Allievi con una grande quantità di dati, la coda Trascrizioni Allievi viene bloccata e impedisce una nuova richiesta.
* Se un account secondario richiede al proprio account principale di condividere un report, l’account principale non è in grado di farlo.
* Gli URL di un corso e di un percorso di apprendimento vengono reindirizzati a posizioni errate.
* Un Allievo visualizza a intermittenza l’istanza di un altro corso facendo clic sul collegamento del corso nella pagina del catalogo.
* La **Annulla iscrizione** il pulsante non viene visualizzato come previsto dopo la prima iscrizione, ma viene visualizzato dopo un aggiornamento.
* Non è possibile salvare il Contenuto o un Quiz il cui nome contiene uno spazio vuoto.
* Nei corsi approvati dal manager, puoi iscrivere nuovamente gli allievi a un gruppo di utenti.
* In alcuni casi, se si tenta di aggiungere un campo attivo aggiuntivo, viene visualizzato il messaggio di errore &quot;Impossibile salvare i campi attivi&quot;.
* Il testo scorre in eccesso nel nome di un corso all’interno di una scheda del corso nella sezione Corsi correlati.
* Dopo il passaggio a un’istanza e l’iscrizione di un Allievo all’istanza, le istanze precedenti sono ancora presenti nel calendario di Outlook.
* Quando un Allievo di un account condiviso tra pari tentava di selezionare la miniatura di un corso, veniva visualizzato un messaggio di errore.
* Quando gli Allievi si registrano a un corso, ricevono più notifiche per l’iscrizione.
* Se un utente modifica manualmente il nome dei cataloghi creati in un connettore, vengono creati nuovi cataloghi e i corsi vengono pubblicati nei cataloghi errati.
* Gli utenti appartenenti ad account inattivi ricevono ancora le e-mail di abbonamento.

### Correzioni di bug relativi alle API

* Gli utenti/GET API non recuperano i dettagli di un Manager.
* In un account, gli utenti venivano creati tramite un’importazione pianificata di utenti FTP durante un periodo di inattività pianificato.
* Nell’app per dispositivi mobili o nella modalità immersiva, dopo aver eliminato o ritirato un’istanza del corso e aver selezionato la successiva istanza attiva, la **Registra interesse** viene visualizzato un pulsante anziché **Iscrizione**.
* Quando un Allievo da un account condiviso tra pari tenta di selezionare la miniatura di un corso utilizzando l’API dell’oggetto di apprendimento, viene visualizzato l’errore 403 Forbidden (Non consentito).

## Requisiti di sistema

Visualizza [Adobe dei requisiti di sistema di Learning Manager](system-requirements.md).

## Versioni precedenti di Adobe Learning Manager

* [Versione di novembre 2023](whats-new-november-2023.md)
* [Versione di luglio 2023](whats-new-2023-july.md)
