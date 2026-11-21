---
description: Scopri come gli amministratori inviano nuovamente gli inviti alla sessione agli Allievi iscritti a una sessione aula virtuale in Adobe Learning Manager
jcr-language: en_us
title: Invia di nuovo l’invito alla sessione
exl-id: 12ee20a8-4521-4235-8120-596812da7809
source-git-commit: 90b45cb128b74ecb33a89bf42ef4d6e960101ff0
workflow-type: tm+mt
source-wordcount: '1527'
ht-degree: 2%
---

# Invia nuovamente gli inviti alla sessione

## Panoramica

>[!NOTE]
>
>Il riavvio è disponibile solo per le sessioni in aula virtuale. Altri tipi di modulo, come i moduli in aula e i moduli di apprendimento autonomo (e-learning) non sono supportati.

Gli Allievi possono non ricevere un invito per diversi motivi. Con l’opzione **Invia di nuovo**, in qualità di amministratore che dispone dell’autorizzazione per modificare i corsi, puoi aprire una sessione in aula virtuale nella pagina dell’istanza, cercare gli Allievi e inviare un’e-mail di invito alla sessione. Learning Manager invia l’e-mail su richiesta, all’esterno del flusso di eventi di iscrizione. L’Allievo riceve i dettagli della sessione e un invito del calendario e lo stato dell’iscrizione resta invariato.

## Casi d’uso

Di seguito sono riportati i casi di utilizzo in cui invieresti nuovamente un invito alla sessione.

* **Recupera un invito mancante.** Invia nuovamente l’invito a un Allievo la cui cassetta postale era piena, il cui indirizzo e-mail è stato inviato tramite spam o il cui indirizzo e-mail originale non è stato recapitato.
* **Riduci no-show.** Invia di nuovo i dettagli della sessione e l&#39;invito del calendario immediatamente prima della sessione o nel giorno della sessione.
* **Evitare soluzioni alternative per l&#39;iscrizione.** Invia nuovamente un invito senza annullare l’iscrizione e iscrivere nuovamente l’Allievo, in modo che lo stato di iscrizione e la registrazione della sessione rimangano intatti.
* **Ridurre i ticket di supporto.** Gli amministratori risolvono autonomamente le richieste di &quot;inviti mancanti&quot;, senza coinvolgere il team di supporto.

## Prerequisiti

* La sessione è una sessione VC.
* L’Allievo è iscritto alla sessione di destinazione. Learning Manager invia l’invito solo agli Allievi iscritti alla sessione.
* Sessione già esistente. Questa funzione non crea né modifica sessioni.
* Viene utilizzato il modello e-mail di invito alla sessione esistente. Questa funzione non introduce un nuovo modello e-mail.

## Configurazioni supportati

| Elemento | Supporto |
|--------------------|-----------------------------------------------------------------------------------------------------------|
| Ruoli | Amministratori autorizzati a modificare il corso. Istruttori per le sessioni a cui sono assegnati. |
| Tipi di elementi del catalogo | Corsi e percorsi di apprendimento |
| Tipo di modulo | Sessioni in aula virtuale |
| Sessioni | Sessioni correnti e future. Le sessioni passate non sono supportate. |
| Fornitori VC | Tutti i provider configurati per la sessione, ad esempio Zoom, Teams e Adobe Connect |
| Modelli e-mail | I modelli configurati per l’oggetto di apprendimento: un’e-mail con i dettagli della sessione e un invito al calendario |
| Destinatari | Singoli Allievi iscritti alla sessione. I gruppi di utenti non sono supportati. |
| Attivazione | Manuale, dall’azione Invia di nuovo invito alla sessione |

Il ruolo Manager non ha accesso a questa funzione in questa versione. L’opzione è nascosta agli Allievi e ai Manager.

## Accedere all’azione di invito Invia di nuovo alla sessione

La posizione dell’azione dipende dal tuo ruolo.

| Ruolo | Dove trovare l’azione |
|---------------|-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| L’Amministratore | Apri il corso o il percorso di apprendimento nel catalogo, seleziona Istanze e apri l’istanza. Nella sezione Sessioni, individua la sessione VC e seleziona Invia nuovamente l’invito alla sessione. È necessaria l’autorizzazione per modificare il corso. |

## Finestra di dialogo Invia di nuovo

La finestra di dialogo Invia di nuovo invito alla sessione contiene gli elementi seguenti.

| Elemento | Descrizione |
|-----------------|---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Seleziona Allievi | Un campo di ricerca. Immetti il nome o l’indirizzo e-mail di un Allievo per trovarlo, quindi seleziona l’Allievo. Puoi selezionare più Allievi. Una nota spiega che ogni Allievo selezionato riceve due e-mail: un’e-mail con i dettagli della sessione e un invito al calendario, in base ai modelli configurati per l’oggetto di apprendimento. |
| Annulla | Chiude la finestra di dialogo senza inviare alcuna e-mail. |
| Invia di nuovo | Invia le e-mail agli Allievi selezionati. Il pulsante è disattivato fino a quando non selezioni almeno un Allievo. |

>[!NOTE]
>
>La ricerca rileva solo i singoli Allievi. Non puoi cercare o selezionare gruppi di utenti.

## Inviare nuovamente un invito alla sessione

Completa i passaggi seguenti come amministratore.

1. Accedi come Amministratore che dispone dell’autorizzazione per modificare il corso.
2. Seleziona **Apprendimento** > **Corsi**.

   ![](assets/resend-session-invite1.png)

3. Apri il corso di cui desideri accedere alle istanze.

   ![](assets/resend-session-invite2.png)

4. Passare all&#39;istanza alla quale si desidera accedere alla sessione.
5. Nella sezione **Dettagli della sessione** riportata di seguito, seleziona **Invia nuovamente invito alla sessione**.

   ![](assets/resend-session-invite3.png)

6. Viene visualizzata la finestra a comparsa **Invia nuovamente invito sessione**.

   ![](assets/resend-session-invite4.png)

7. Cerca l’Allievo o gli allievi a cui desideri inviare nuovamente l’invito.

   ![](assets/resend-session-invite5.png)

   ![](assets/resend-session-invite6.png)

8. Seleziona **Invia di nuovo**. Verrà visualizzato il messaggio &quot;Invito alla sessione inviato agli Allievi &quot;x&quot;.&quot;

   ![](assets/resend-session-invite7.png)

9. Nel caso in cui uno degli Allievi selezionati provenga da un’altra sessione, verrà visualizzato un messaggio di tipo &quot;X Allievo selezionato non è iscritto a questa sessione ed è stato ignorato&quot;.

   ![](assets/resend-session-invite8.png)

10. Dopo alcuni minuti, gli Allievi riceveranno un messaggio e-mail con i dettagli della sessione, incluso un collegamento per accedere alla sessione.

![](assets/resend-session-invite9.png)

Learning Manager verifica che ogni Allievo selezionato sia iscritto alla sessione di destinazione, quindi invia l’invito alla sessione esistente agli Allievi idonei.

Quando Learning Manager accetta la richiesta, la finestra di dialogo si chiude e viene visualizzato un messaggio di conferma: &quot;Le e-mail di invito vengono inviate agli Allievi per la sessione. Il completamento di questa operazione potrebbe richiedere del tempo.&quot; Le e-mail di solito arrivano in pochi minuti.

## Contenuto e-mail

Ogni Allievo selezionato riceve l’e-mail con i dettagli della sessione e l’invito del calendario per la sessione. Il contenuto include il collegamento di partecipazione alla sessione VC, la data e l&#39;ora e i dettagli della sessione. L’e-mail è uguale all’invito alla sessione originale, perché Learning Manager utilizza lo stesso modello.

## Comportamento di iscrizione multipla

Il reinvio è specifico di un&#39;istanza. Se un Allievo è iscritto a più di un’istanza, il rinvio da un’istanza invia l’invito solo per quell’istanza. Non riattiva gli inviti per le altre istanze dell’Allievo.

| Iscrizione degli Allievi | Azione | Risultato |
|------------------------------------------------|------------------------------------------------|----------------------------------------------------------------------------------|
| Istanza A e Istanza B | Invia di nuovo dall&#39;istanza A | Viene inviato di nuovo solo l’invito Istanza A. |
| Solo istanza A | Invia di nuovo dall&#39;istanza A | L’invito per l’istanza A è stato inviato di nuovo. |
| Un&#39;istanza diversa dalla sessione selezionata | L’Allievo viene visualizzato nella ricerca a livello di corso | Learning Manager ignora l’Allievo per la sessione selezionata e visualizza un avviso. |

## Comportamento in scenari specifici

| Scenario | Comportamento |
|--------------------------------------------------------|------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| L’istanza non ha sessioni in aula virtuale | L&#39;azione Invia di nuovo invito alla sessione non è disponibile. |
| Sessione già eseguita | Azione non disponibile. Learning Manager supporta solo le sessioni correnti e future. |
| Seleziona un Allievo non iscritto alla sessione | La ricerca degli Allievi copre l’intero corso, in modo da poter trovare gli Allievi di altre istanze. Learning Manager ignora gli Allievi non iscritti alla sessione selezionata, invia l’invito agli altri utenti e visualizza un avviso. |
| Un Allievo è iscritto a più istanze | Learning Manager invia l’invito solo per l’istanza da cui lo invii. Non invia inviti per le altre istanze. |
| È selezionata un’istanza del percorso di apprendimento | L’azione funziona come per un’istanza del corso. |

## Gestione degli errori

Se un errore impedisce a Learning Manager di inviare le e-mail, la finestra di dialogo mostra uno dei seguenti messaggi.

| Condizione | Messaggio |
|---------------------------------------|------------------------------------------------------------------------|
| Il modello e-mail di invito è disabilitato | Impossibile inviare l’e-mail: il modello di e-mail di invito è attualmente disattivato. |
| Qualsiasi altro errore | Si è verificato un errore durante l&#39;invio dell&#39;e-mail. Riprova più tardi. |

Se selezioni gli Allievi che non sono iscritti alla sessione, Learning Manager mostra un avviso che segnala che l’invito è stato ignorato per questi Allievi. Invia comunque l’invito agli Allievi iscritti.

>[!NOTE]
>
>Il servizio e-mail segnala lo stato di recapito a Learning Manager in modo asincrono, dopo la chiusura della finestra di dialogo.

## Limitazioni

* Puoi inviare nuovamente gli inviti solo per le sessioni correnti e future.
* Vengono utilizzati solo i modelli configurati per l’oggetto di apprendimento. Non è possibile selezionare un modello diverso.
* Puoi inviare nuovamente gli inviti per una sessione alla volta. Il rinvio tra più istanze contemporaneamente non è supportato.
* Non puoi selezionare gruppi di utenti. Puoi selezionare solo singoli Allievi.
* Learning Manager invia inviti solo agli Allievi iscritti alla sessione selezionata.
* La finestra di dialogo non mostra lo stato di recapito delle e-mail e non offre un nuovo tentativo per i singoli Allievi.
* Non puoi pianificare nuove sessioni o modificare i dettagli delle sessioni esistenti dalla finestra di dialogo.

## Risoluzione dei problemi

| Sintomo | Probabile causa | Azione |
|---------------------------------------------------------------------|-------------------------------------------------------------------------------------------------------------------|---------------------------------------------------------------------------------------------------------------------|
| L’azione Invia di nuovo invito alla sessione non è visibile | Il modulo non è una sessione VC, la sessione si è già verificata o non disponi delle autorizzazioni necessarie per modificare il corso. | Conferma che la sessione è una sessione VC corrente o futura. Chiedi a un amministratore di verificare le autorizzazioni del corso. |
| Una volta inviate le e-mail, viene visualizzato un avviso. | Uno o più Allievi selezionati non sono iscritti alla sessione selezionata. | Verifica quali Allievi sono iscritti alla sessione e invia nuovamente l’invito dalla sessione o dall’istanza corretta. |
| L’invito è stato inviato per l’istanza errata | L’Allievo è iscritto a più istanze e l’invito viene inviato di nuovo da un’istanza diversa. | Apri l’istanza necessaria per l’Allievo e invia nuovamente l’invito da lì. |
| Viene visualizzato l’errore &quot;Il modello e-mail di invito è attualmente disattivato&quot; | Il modello e-mail di invito è disattivato per l’oggetto di apprendimento. | Chiedi a un amministratore di abilitare il modello, quindi invia nuovamente l&#39;invito. |
| L’e-mail inviata di recente ha lo stesso aspetto dell’invito originale | Questo è previsto. Learning Manager riutilizza il modello di invito alla sessione esistente. | Non è richiesto alcun intervento. |
| È necessario inviare nuovamente gli inviti tra più istanze contemporaneamente | Questo non è supportato. | Invia nuovamente gli inviti separatamente da ogni istanza. |
| È necessario inviare nuovamente un invito per una classe o un modulo di e-learning | Questo non è supportato. Il riavvio è disponibile solo per le sessioni in aula virtuale. | Nessuna azione disponibile per questi tipi di modulo. |
| Un Allievo afferma che l’e-mail non è arrivata | L’e-mail è ancora in fase di elaborazione, la cassetta postale dell’Allievo è piena o l’e-mail è stata filtrata come spam. | Attendi alcuni minuti, chiedi all’Allievo di controllare la cartella della posta indesiderata e liberare spazio nella cassetta postale, quindi invia nuovamente l’invito. |
