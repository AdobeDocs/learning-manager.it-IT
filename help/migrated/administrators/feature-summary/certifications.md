---
description: Scopri come creare certificazioni, iscrivere Allievi e modificare le certificazioni pubblicate.
jcr-language: en_us
title: Certificazioni
contentowner: manochan
exl-id: 406d1c33-aac3-47e1-9b32-83874976ce54
source-git-commit: 69ef7d1e27fac3db49cbb4b9f9403f74e146efb5
workflow-type: tm+mt
source-wordcount: '1024'
ht-degree: 67%

---

# Certificazioni

Scopri come creare certificazioni, iscrivere Allievi e modificare le certificazioni pubblicate.

Certifica gli Allievi una sola volta oppure su base ricorrente tramite questa funzionalità. Solo gli Amministratori possono definire le certificazioni per gli Allievi.

In qualità di Amministratore è possibile creare un Programma di certificazione ospitato internamente o condotto da terze parti. In caso di certificazione interna, definisci i corsi che un Allievo deve completare per essere certificato. Pubblica il programma, quindi assegnalo agli Allievi.

## Creazione una certificazione {#createacertification}

1. Fai clic su **[!UICONTROL Certificazione]** nel riquadro a sinistra.\
   Viene visualizzata una pagina con un elenco di tutte le bozze e lo stato delle certificazioni pubblicate.

1. Visualizza le certificazioni in varie modalità:

   1. Fai clic sulla scheda **[!UICONTROL Bozza]** per visualizzare tutte le certificazioni con lo stato di bozza. Devi completarne la creazione.
   1. Fai clic su **[!UICONTROL Pubblicato]** per visualizzare tutte le certificazioni pubblicate.
   1. Fai clic su **[!UICONTROL Tutti]** per visualizzare le certificazioni in tutti gli stati.
   1. Ordina e visualizza l’elenco delle certificazioni in ordine crescente o decrescente oppure in base alla data di aggiornamento.

1. Fai clic su **[!UICONTROL Aggiungi]**.

   Viene visualizzata una nuova pagina di certificazione.

![](assets/add-new-certification.png)

*Visualizzare la pagina per aggiungere una certificazione*

1. Aggiungi nome e descrizione del certificato.

<table>
 <tbody>
  <tr>
   <th>Campo</th>
   <th>Descrizione</th>
  </tr>
  <tr>
   <td>Giorni per il completamento</td>
   <td>La scadenza per completare la certificazione. Immetti un valore numerico.</td>
  </tr>
  <tr>
   <td>Tipo</td>
   <td>
    <p>Tipo di certificazione:</p>
    <ul>
     <li><b>Ricorrente</b> - Scegli questa opzione se la certificazione deve avvenire ogni anno, due anni o tre anni.</li>
     <li><b>Permanente</b> - Scegli questa opzione se la certificazione è richiesta una sola volta.</li>
    </ul></td>
  </tr>
  <tr>
   <td>Riassegnazione</td>
   <td>Scegli se desideri che il certificato venga riassegnato in base alla data di completamento o in base alla data di iscrizione.<br></td>
  </tr>
  <tr>
   <td>Validità (in mesi) <br></td>
   <td>Specifica per quanto tempo rimane valida la certificazione.</td>
  </tr>
  <tr>
   <td>Ordinamento dei corsi<br></td>
   <td>Decidi se gli Allievi devono seguire i corsi in sequenza oppure no.<br></td>
  </tr>
  <tr>
   <td>Annullamento iscrizione<br></td>
   <td>Attiva o disattiva l’opzione per consentire agli Allievi di annullare l’iscrizione.</td>
  </tr>
  <tr>
   <td>Soggetto emittente certificazione<br></td>
   <td>
    <p>Scegli <b>Interno</b> se appartiene alla tua organizzazione o <b>Esterno</b> per le certificazioni esterne dell’organizzazione.</p>
    <p>Se scegli <b>Certificazione esterna</b> vedrai altre due opzioni:</p>
    <ul>
     <li>Uguale alla data di approvazione<br></li>
     <li>Inviato dall’Allievo<br></li>
    </ul>
    <p>Gli allievi possono specificare la corretta data di completamento delle certificazioni esterne. Nelle versioni precedenti, la data di completamento era impostata per impostazione predefinita da Prime, in base alla data di approvazione del Manager. La data di completamento fornita dall’Allievo deve essere successiva alla data di creazione del certificato<span>.</span></p></td>
  </tr>
  <tr>
   <td>Durata</td>
   <td>Se hai scelto Certificazione esterna, specifica la durata in minuti.</td>
  </tr>
  <tr>
   <td>Tag</td>
   <td>Immetti i tag da associare al certificato. I tag sono utili per cercare il certificato.</td>
  </tr>
  <tr>
   <td>Seleziona cataloghi<br></td>
   <td>Scegli il catalogo di cui fa parte il certificato.</td>
  </tr>
 </tbody>
</table>

Seleziona il livello di prodotti, ruoli e ruoli dalla sezione **[!UICONTROL Suggerimenti per]** per suggerire questo percorso di apprendimento agli utenti che hanno espresso interesse per tali prodotti e ruoli.

![](assets/recommend-for.png)

*Consiglio*

Scegli i corsi da aggiungere alla certificazione dalla scheda **[!UICONTROL Corsi]** > **[!UICONTROL Catalogo]**.

Passa il mouse su ogni riquadro del corso e fai clic su + per aggiungerli alla certificazione. Fai clic su **[!UICONTROL Anteprima]** per visualizzare il corso come Allievo prima di aggiungerlo.

1. Fai clic sulla scheda **[!UICONTROL Curriculum]** per visualizzare/verificare l’elenco dei corsi aggiunti.
1. Fai clic su **[!UICONTROL Publish]**.

## Mappatura delle istanze del corso per le certificazioni {#courseinstancemappingforcertifications}

Per mappare il corso e l’istanza per le certificazioni:

1. Fai clic su Certificazioni nel riquadro a sinistra.
1. Dall’elenco delle certificazioni, seleziona Visualizza certificazione in corrispondenza della certificazione a cui vuoi mappare il corso e l’istanza.
1. Nel riquadro a sinistra, fai clic su Corsi. Vengono visualizzati i corsi per la certificazione. Fai clic su Modifica.
1. Passa il cursore del mouse sul corso in cui vuoi impostare la mappatura dell’istanza e seleziona Mappatura istanze corso.
1. Dalla finestra a comparsa visualizzata, seleziona l’istanza del corso da consegnare per la certificazione scelta.
1. Fai clic su Salva.

Un amministratore può aggiungere corsi di tipo aula e aula virtuale a un programma di apprendimento. La sessione assegnata dall’Autore durante la creazione del corso diventa l’istanza predefinita. Quando l’Amministratore aggiunge corsi a un programma di apprendimento, esso viene mappato all’istanza predefinita di tutti i corsi per impostazione predefinita. L’Amministratore può tuttavia modificare la mappatura delle istanze. Il numero di corsi aggiunti in un programma di apprendimento è visibile anche nella pagina delle istanze, come illustrato di seguito.

## Abilitazione del controllo completo del catalogo {#catalog}

Oltre che per gli [apprendimenti o i moduli](shared-catalog-full-control.md), è anche possibile abilitare il controllo completo dei cataloghi per le certificazioni.

## Iscrizione o annullamento dell’iscrizione degli Allievi alla certificazione {#enrollorunenrolllearnerstothecertification}

Per ulteriori informazioni sull’iscrizione degli Allievi e sui passaggi da seguire, vedi [Iscrizione degli Allievi](courses.md#main-pars_header_1058138132).

## Annullamento dell’iscrizione degli Allievi {#unenrollmentforlearners}

Durante la creazione delle certificazioni, l’Amministratore dispone di un’opzione per selezionare se gli Allievi possono annullare l’iscrizione alla certificazione. Se l’Amministratore seleziona l’apposita opzione, l’Allievo può annullare l’iscrizione.

![](assets/unenrollment.png)

*Scegli di annullare l’iscrizione degli Allievi*

## Contrassegnare il completamento {#markcompletion}

Gli Amministratori possono contrassegnare una certificazione come completa utilizzando l’opzione apposita. Per contrassegnare il completamento della certificazione, procedi come segue.

1. Apri **[!UICONTROL Certificazione]** > **[!UICONTROL Allievi]**.

   Si apre la pagina Allievi con l’elenco degli Allievi iscritti.

1. Seleziona uno/più/tutti gli Allievi per contrassegnare il completamento della certificazione utilizzando la casella di controllo disponibile per ogni Allievo.
1. Fai clic su **[!UICONTROL Azione]** > **[!UICONTROL Contrassegna completamento.]**

   Tieni presente che se una certificazione contiene più corsi, il completamento verrà contrassegnato per tutti i corsi.

## Corsi obbligatori per la certificazione esterna {#mandatory}

Nelle versioni precedenti di Learning Manager, il completamento del corso da parte di un Allievo in una certificazione esterna non era obbligatorio per completare un certificato.

Ora puoi rendere obbligatori i corsi attivando l’opzione **[!UICONTROL Imposta i corsi richiesti come obbligatori per il completamento del certificato]** nella scheda Curriculum mentre modifichi la certificazione.

## Modifica di una certificazione pubblicata {#editingapublishedcertification}

L’Amministratore può modificare una certificazione dopo la pubblicazione. Quando lo stato del programma di apprendimento è Pubblicato, l’Amministratore può modificare tutte le sezioni della certificazione, quindi ripubblicarla.

Per modificare una certificazione pubblicata, fai clic sulla scheda della certificazione e quindi su **[!UICONTROL Modifica]** nell&#39;angolo superiore destro della pagina.

Se esci dalla pagina durante la modifica delle sezioni di una certificazione, dovrai pubblicare nuovamente la certificazione. Viene visualizzata una finestra di dialogo di conferma che ti invita a ripubblicare la certificazione.

![](assets/edit-a-certificate.png)

*Modificare un certificato*

## Abbonamento {#subscription}

Un Amministratore può recuperare il punteggio dei quiz e i report sullo stato degli Allievi. Può inoltre impostare la frequenza dei report, l’oggetto e-mail e l’ID e-mail dei destinatari. Il destinatario riceverà un’e-mail con il report in allegato in base alla frequenza impostata.

![](assets/report-subscription.jpeg)

*Impostare la frequenza del report e altre proprietà*
