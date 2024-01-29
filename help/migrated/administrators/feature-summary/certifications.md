---
description: Scopri come creare certificazioni, iscrivere Allievi e modificare le certificazioni pubblicate.
jcr-language: en_us
title: Certificazioni
contentowner: manochan
source-git-commit: 0052ccb2f5a8f9617bca2c7bad91c0cd18338b66
workflow-type: tm+mt
source-wordcount: '991'
ht-degree: 0%

---



# Certificazioni

Scopri come creare certificazioni, iscrivere Allievi e modificare le certificazioni pubblicate.

Con questa funzione, puoi certificare gli Allievi una sola volta o in base a un periodo di tempo ricorrente. Solo gli Amministratori possono definire le certificazioni per gli Allievi.

In qualità di Amministratore, puoi creare un programma di certificazione ospitato internamente o condotto da terze parti. In caso di certificazione interna, definisci i corsi che un Allievo deve completare per essere certificato. Pubblica il programma e assegnalo agli Allievi.

## Creare una certificazione {#createacertification}

1. Fai clic **[!UICONTROL Certificazione]** nel riquadro sinistro.\
   Viene visualizzata una pagina con un elenco di tutte le bozze e lo stato delle certificazioni pubblicate.

1. Visualizza le certificazioni in varie modalità:

   1. Fai clic **[!UICONTROL Bozza]** per visualizzare tutte le certificazioni con lo stato di bozza. Devi completare la creazione.
   1. Fai clic **[!UICONTROL Pubblicato]** per vedere tutte le certificazioni pubblicate.
   1. Fai clic **[!UICONTROL Tutti]** per visualizzare le certificazioni in tutti gli stati.
   1. Ordina e visualizza l’elenco delle certificazioni in ordine crescente o decrescente oppure in base alla data di aggiornamento.

1. Fai clic **[!UICONTROL Aggiungi]**.

   Viene visualizzata una nuova pagina di certificazione.

![](assets/add-new-certification.png)

*Visualizza la pagina per aggiungere una certificazione*

1. Aggiungi nome e descrizione del certificato.

<table>
 <tbody>
  <tr>
   <th>Campo</th>
   <th>Descrizione</th>
  </tr>
  <tr>
   <td>Giorni per il completamento</td>
   <td>Scadenza per la certificazione. Immettere un valore numerico.</td>
  </tr>
  <tr>
   <td>Tipo</td>
   <td>
    <p>Tipo di certificazione:</p>
    <ul>
     <li><b>Ricorrente</b>- Scegli questa opzione se la certificazione deve essere rilasciata dopo ogni anno, due anni o tre anni.</li>
     <li><b>Perpetuo</b>- Scegli questa opzione se la certificazione deve essere un requisito una tantum.</li>
    </ul></td>
  </tr>
  <tr>
   <td>Riassegnazione</td>
   <td>Scegli se desideri che il certificato venga riassegnato in base alla data di completamento o in base alla data di iscrizione.<br></td>
  </tr>
  <tr>
   <td>Validità (in mesi) <br></td>
   <td>Specifica per quanto tempo la certificazione può rimanere valida.</td>
  </tr>
  <tr>
   <td>Ordinamento dei corsi<br></td>
   <td>Decidi se gli Allievi devono seguire i corsi in sequenza o meno.<br></td>
  </tr>
  <tr>
   <td>Annullamento dell’iscrizione<br></td>
   <td>Abilita o disabilita l’opzione per consentire agli Allievi di annullare l’iscrizione.</td>
  </tr>
  <tr>
   <td>Emittente certificazione<br></td>
   <td>
    <p>Scegli <b>Interno</b> se appartiene alla tua organizzazione o scegli <b>Esterno</b> per le certificazioni di organizzazioni esterne.</p>
    <p>Quando scegli <b>Certificazione esterna</b>, vengono visualizzate altre due opzioni:</p>
    <ul>
     <li>Uguale alla data di approvazione<br></li>
     <li>Inviato dall’Allievo<br></li>
    </ul>
    <p>Gli Allievi possono specificare la data di completamento corretta per le certificazioni esterne. Nelle versioni precedenti, la data di completamento era impostata per impostazione predefinita da Prime, in base alla data di approvazione del Manager. La data di completamento fornita dall’Allievo deve essere successiva alla data di creazione del certificato<span>.</span></p></td>
  </tr>
  <tr>
   <td>Durata</td>
   <td>Se hai scelto Certificazione esterna, specifica la durata in minuti.</td>
  </tr>
  <tr>
   <td>Tag</td>
   <td>Immettere i tag da associare al certificato. I tag sono utili quando si desidera cercare il certificato.</td>
  </tr>
  <tr>
   <td>Seleziona cataloghi<br></td>
   <td>Scegliere il catalogo di cui fa parte il certificato.</td>
  </tr>
 </tbody>
</table>

Scegli i corsi da aggiungere alla certificazione da **[!UICONTROL Corsi]** > **[!UICONTROL Catalogo]** scheda.

Passa il mouse su ogni riquadro del corso e fai clic su + per aggiungerli alla certificazione. Fai clic **[!UICONTROL Anteprima]** per visualizzare il corso come allievo prima di aggiungerlo.

1. Fai clic **[!UICONTROL Curriculum]** per visualizzare/verificare l’elenco dei corsi aggiunti.
1. Fai clic **[!UICONTROL Pubblica]**.

## Mappatura dell’istanza del corso per le certificazioni {#courseinstancemappingforcertifications}

Per mappare il corso e l’istanza per le certificazioni:

1. Fai clic su Certificazioni nel riquadro a sinistra.
1. Dall’elenco delle certificazioni, seleziona Visualizza certificazione della certificazione a cui desideri associare il corso e l’istanza.
1. Nel riquadro a sinistra, fai clic su Corsi. Vengono visualizzati i corsi per la certificazione. Fai clic su Modifica.
1. Passa con il mouse sul corso per cui desideri impostare la mappatura delle istanze, e seleziona Mappatura istanze del corso.
1. Nella finestra a comparsa visualizzata, seleziona l’istanza del corso da inviare per la certificazione scelta.
1. Fai clic su Salva.

Un amministratore può aggiungere corsi di tipo aula e aula virtuale a un programma di apprendimento. Qualunque sessione l’autore abbia impartito durante la creazione del corso diventa l’istanza predefinita. Quando l’Amministratore aggiunge corsi a un programma di apprendimento, per impostazione predefinita viene mappato all’istanza predefinita di tutti i corsi, ma l’Amministratore può modificare la mappatura delle istanze. Il numero di corsi aggiunti a un programma di apprendimento è visibile anche nella pagina delle istanze, come illustrato di seguito.

## Abilita controllo completo dei cataloghi {#catalog}

Come concedere pieno [controllo catalogo per corsi o moduli](shared-catalog-full-control.md), puoi anche abilitare il controllo completo dei cataloghi per le certificazioni.

## Iscrizione o annullamento dell’iscrizione degli allievi alla certificazione {#enrollorunenrolllearnerstothecertification}

Per ulteriori informazioni sull’iscrizione degli Allievi e sui passaggi da seguire, consulta [Iscrizione degli Allievi](courses.md#main-pars_header_1058138132).

## Annullamento dell’iscrizione per gli Allievi {#unenrollmentforlearners}

Durante la creazione delle certificazioni, l’Amministratore può selezionare se gli Allievi possono annullare l’iscrizione alla certificazione. Se l’Amministratore seleziona l’opzione, l’Allievo può annullare la propria iscrizione.

![](assets/unenrollment.png)

*Scegli di annullare l’iscrizione degli Allievi*

## Contrassegna completamento {#markcompletion}

Gli amministratori possono contrassegnare una certificazione come completata utilizzando l’opzione disponibile. Per contrassegnare il completamento di una certificazione, attieniti alla procedura riportata di seguito.

1. Apri **[!UICONTROL Certificazione]** > **[!UICONTROL Allievi]**.

   Si apre la pagina Allievi con l’elenco degli Allievi iscritti.

1. Seleziona uno/più/tutti gli Allievi per contrassegnare il completamento della certificazione utilizzando la casella di controllo disponibile per ogni Allievo.
1. Fai clic  **[!UICONTROL Azione]** > **[!UICONTROL Contrassegna completamento.]**

   Tieni presente che se una certificazione include più corsi, il completamento verrà contrassegnato per tutti i corsi.

## Corsi obbligatori per la certificazione esterna {#mandatory}

Nelle versioni precedenti di Learning Manager, il completamento del corso da parte di un Allievo in una certificazione esterna non era obbligatorio per completare un certificato.

Ora puoi rendere obbligatori i corsi attivando l’opzione **[!UICONTROL Imposta i corsi richiesti come obbligatori per il completamento del certificato]** nella scheda Curriculum durante la modifica della certificazione.

## Modifica di una certificazione pubblicata {#editingapublishedcertification}

Una certificazione può essere modificata da un Amministratore a uno stato pubblicato. A questo punto, l’Amministratore può modificare tutte le sezioni di una certificazione e ripubblicarle.

Per modificare una certificazione pubblicata, fai clic sulla scheda della certificazione e quindi su **[!UICONTROL Modifica]** nell’angolo in alto a destra della pagina.

Durante la modifica delle sezioni di una certificazione, se devi uscire dalla pagina, devi ripubblicare la certificazione. Viene visualizzata una finestra di dialogo che richiede di pubblicare nuovamente la certificazione.

## Abbonamento {#subscription}

Un amministratore può recuperare il punteggio del quiz e i report sullo stato degli allievi. Possono impostare la frequenza del report, l’oggetto e-mail e l’ID e-mail dei destinatari. A seconda della frequenza impostata, il destinatario riceverà un’e-mail con il report allegato.

![](assets/report-subscription.jpeg)

*Impostare la frequenza del report e altre proprietà*
