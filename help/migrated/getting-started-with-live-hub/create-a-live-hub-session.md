---
title: Creare una sessione di Hub live (Beta)
description: Scopri come creare un corso Hub dal vivo, aggiungere istanze del corso, assegnare Istruttori con Finder Istruttori, iscrivere Allievi e personalizzare il branding della sala.
source-git-commit: 055a04c6226146b1816241834a57ae4b1b8a1d2a
workflow-type: tm+mt
source-wordcount: '1084'
ht-degree: 0%

---


# Creare una sessione di Hub live (Beta)

Utilizza Live Hub per offrire corsi di formazione in diretta guidati da istruttori all’interno di un corso Adobe Learning Manager. Puoi combinare le sessioni Live Hub con contenuti autonomi per creare un&#39;esperienza di apprendimento mista.

Quando aggiungi un modulo Classe virtuale a un corso, seleziona lo strumento di formazione virtuale che ospiterà la sessione dal vivo. Puoi scegliere **Hub live**, la soluzione di formazione virtuale integrata di Adobe basata sull&#39;intelligenza artificiale o utilizzare un provider esterno come **Adobe Connect**.

>[!NOTE]
>
> Live Hub viene visualizzato come opzione Live Virtual Training Tool solo se l’Amministratore l’ha abilitato nelle impostazioni Live Hub. Se questa opzione non è abilitata, utilizza invece un provider esterno come Adobe Connect. Per ulteriori informazioni, visualizza [Abilita Hub dal vivo](../administrators/feature-summary/enable-live-hub.md).

Quando crei un corso Hub dal vivo, puoi:

* Aggiungi una o più sessioni Hub dal vivo a un corso.

* Seleziona manualmente gli Istruttori o utilizza i consigli degli Istruttori basati sull’intelligenza artificiale.

* Configura il corso con una singola istanza predefinita o crea più istanze per pianificazioni o gruppi di destinatari diversi.

Questo articolo spiega come creare un corso Hub dal vivo, assegnare Istruttori e configurare le istanze del corso.

## Creazione di un corso Hub dal vivo

Un’istanza predefinita viene creata automaticamente quando aggiungi un modulo Classe virtuale. Questa funzione è utile per offrire una singola sessione o una pianificazione standard per tutti gli Allievi.

Per creare un corso Hub dal vivo:

1. Accedi a Adobe Learning Manager come Autore.

1. Seleziona **Crea corsi**.

1. Nella pagina **Catalogo corsi**, seleziona **Aggiungi**, quindi immetti i seguenti dettagli:

   1. Nome del corso

   1. Breve descrizione

   ![Aggiungi descrizione nome corso](assets/add-course-name-description.png)
   *Immettere il nome del corso e la breve descrizione prima di aggiungere moduli al corso.*

1. Seleziona **Contenuto** > **Aggiungi moduli** nella sezione **Moduli**. <br> Viene visualizzata la finestra a comparsa **Seleziona tipo di modulo**.

1. Seleziona **Aula virtuale** e immetti i dettagli del corso, inclusi titolo, descrizione, fuso orario, data di inizio e di fine e ora di inizio e di fine.

1. Seleziona **Hub live** in **Strumenti di formazione virtuale live**.

   ![Seleziona strumento Hub dinamico](assets/select-live-hub-tool.png)
   *Seleziona Hub dal vivo per abilitare i suggerimenti degli istruttori basati sull&#39;intelligenza artificiale per la sessione.*

1. Aggiungi Istruttori utilizzando una delle seguenti opzioni:

   1. Immetti i nomi degli istruttori nel campo **Istruttori**.

   1. Seleziona **Trova istruttori che utilizzano l&#39;IA** per visualizzare gli istruttori consigliati dall&#39;IA. Per ulteriori informazioni, consulta [Aggiungere istruttori tramite il Finder istruttori](#add-instructors-using-instructor-finder).

1. Seleziona **Aggiungi** > **Salva**.

1. Seleziona le abilità richieste nella sezione **Abilità corso**.

1. Seleziona **Livello di abilità**, quindi rivedi o aggiorna i **crediti massimi**.

   ![Assegna livello di abilità del corso](assets/assign-course-skill-level.png)
   *Assegnare un’abilità e un livello di abilità per definire i crediti che gli Allievi guadagnano completando il corso.*

1. Seleziona **Salva** > **Publish**. Il corso viene creato correttamente in Adobe Learning Manager.

## Creazione di un’istanza di corso

Un Amministratore può creare una o più istanze di un corso per offrirlo a gruppi di destinatari, pianificazioni o sedi diversi. Ogni istanza ha i propri dettagli di sessione, in modo da poter assegnare diversi Istruttori, suggerimenti per il Finder dell’Istruttore e orari a ogni istanza dello stesso corso.

Per creare un’istanza di corso:

1. Accedi a Adobe Learning Manager come Autore.

1. Apri il corso, quindi seleziona **Istanze** dal pannello a sinistra.

   ![Pagina Istanza predefinita](assets/default-instance-page.png)
   *L’istanza predefinita viene creata automaticamente quando aggiungi un modulo Classe virtuale.*

1. Selezionare **Aggiungi nuova istanza**.

1. Immetti **Nome istanza**, **Data inizio** e **Scadenza completamento**. Selezionare **Mostra più opzioni** per configurare impostazioni aggiuntive.

   ![Aggiungi nuovo modulo istanza](assets/add-new-instance-form.png)
   *Immettere un nome di istanza, una data di inizio e una scadenza di completamento per creare una nuova istanza del corso.*

1. Seleziona **Salva**. <br> La nuova istanza viene aggiunta all&#39;elenco **Istanze**.

   ![Elenco delle istanze - Nuova istanza](assets/instances-list-new-instance.png)
   *La nuova istanza viene visualizzata accanto all&#39;istanza predefinita nell&#39;elenco delle istanze.*

1. Selezionare il numero in **Sessioni** per visualizzare i **Dettagli sessione**.

   ![Icona Modifica dettagli sessione](assets/session-details-edit-icon.png)
   *I dettagli della sessione mostrano quali campi relativi a orario, istruttore e posizione devono ancora essere configurati.*

1. Seleziona l’icona di modifica (matita) accanto ai dettagli della sessione per aprire il pannello di configurazione della sessione.

   ![Pannello di configurazione della sessione](assets/session-configuration-panel.png)
   *Configurare la pianificazione, l&#39;istruttore e il percorso per un&#39;istanza di sessione specifica.*

1. Nel campo **Istruttori**, immettete manualmente i nomi o selezionate **Trova istruttori utilizzando l&#39;intelligenza artificiale** per gli Istruttori consigliati dall&#39;intelligenza artificiale. Per ulteriori informazioni, consulta [Aggiungere istruttori tramite il Finder istruttori](#add-instructors-using-instructor-finder).

1. Immetti i dettagli della **Posizione**, quindi seleziona **Salva**. La sessione viene aggiornata con gli orari configurati, l’Istruttore e i dettagli sulla posizione.

## Aggiungere Istruttori mediante il Finder Istruttori

Invece di cercare e aggiungere manualmente gli Istruttori, utilizza **Instructor Finder** per ricevere consigli di Istruttore basati sull’intelligenza artificiale per la sessione. Il Finder degli Istruttori abbina gli Istruttori in base ai dettagli del corso e alle abilità richieste, considerando anche il calendario delle vacanze dell’organizzazione, la disponibilità degli Istruttori e il loro utilizzo per suggerire gli Istruttori più adatti. Per ulteriori informazioni, consulta [Aggiungere e gestire gli istruttori](./instructor-management.md).

>[!NOTE]
>
> Il Finder viene visualizzato solo se l’Amministratore ha abilitato l’Assistente Finder Istruttori nelle impostazioni Hub dinamico. Per ulteriori informazioni, visualizza [Abilita Hub dal vivo](../administrators/feature-summary/enable-live-hub.md).

Per aggiungere Istruttori tramite il Finder Istruttori:

1. Passa alla sezione **Istruttori** nel modulo **Aula virtuale**.

1. Seleziona **Trova istruttori utilizzando l&#39;intelligenza artificiale**. <br> Il pannello **Assistente AI** si apre sul lato destro.

   ![Recommendations Istruttore pannello Assistente intelligenza artificiale](assets/ai-assistant-panel-instructor-recommendations.png)
   *Utilizzare il pannello Assistente intelligenza artificiale per ottenere consigli sull&#39;istruttore e sulle fasce orarie in base ai dettagli della sessione.*

1. Consulta l’elenco degli Istruttori consigliati.

1. Passa all’Istruttore che desideri assegnare, quindi seleziona **Aggiungi**. <br> L’istruttore selezionato viene aggiunto al campo **Istruttori** come tag.

## Iscrizione degli Allievi al corso

Gli Allievi possono essere iscritti a un corso Hub dal vivo nei due modi seguenti:

1. Un **Amministratore** iscrive gli Allievi al corso in base ai requisiti dell’organizzazione. Per ulteriori informazioni, visualizza [Creare istanze del corso e percorsi di apprendimento](https://experienceleague.adobe.com/it/docs/learning-manager/using/admin/courses).

1. Gli Allievi possono iscriversi direttamente al corso dalla pagina **Catalogo**. Se il corso è configurato per l’iscrizione autonoma, gli Allievi vengono iscritti immediatamente e possono accedere al corso da **I miei Allievi**. Per ulteriori informazioni, consulta [I miei insegnamenti](https://experienceleague.adobe.com/it/docs/learning-manager/using/learner/courses).

Dopo l’iscrizione, gli Allievi vengono aggiunti al corso e ricevono una notifica nel proprio account Adobe Learning Manager. A seconda delle impostazioni di notifica e-mail dell’account, gli Allievi possono anche ricevere un invito a partecipare al corso tramite e-mail.

## Personalizzare il branding della stanza dell’Hub live

Gli amministratori possono personalizzare l&#39;aspetto delle stanze dell&#39;Hub dal vivo per allinearlo al marchio della tua organizzazione. Utilizza le impostazioni **Temi** in Adobe Learning Manager per applicare i colori del marchio, i loghi e lo stile visivo nelle sessioni dell&#39;Hub dal vivo.

Il branding personalizzato consente di creare un’esperienza di apprendimento uniforme e garantisce che le sessioni di formazione dal vivo riflettano l’identità dell’organizzazione.

Per ulteriori informazioni sulla configurazione dei temi, consulta l&#39;articolo [Temi colore](../administrators/feature-summary/themes.md#color-themes).
