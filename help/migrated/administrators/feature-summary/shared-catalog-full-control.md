---
jcr-language: en_us
title: Abilita il controllo completo del catalogo condiviso
description: Abilita il controllo completo del catalogo condiviso in Adobe Learning Manager
contentowner: saghosh
source-git-commit: 46afb6603456ced9d7e2aaf98d07ec92fee30c0b
workflow-type: tm+mt
source-wordcount: '791'
ht-degree: 0%

---



# Abilita il controllo completo del catalogo condiviso

## Crea catalogo {#createcatalog}

In qualità di Amministratore, puoi creare un catalogo di corsi, programmi di apprendimento, risorse formative e certificazioni.

Per ulteriori informazioni, consulta [Cataloghi](/help/migrated/administrators/feature-summary/catalogs.md).

## Condividi catalogo {#sharecatalog}

Puoi condividere i cataloghi con gli utenti interni di un’organizzazione o con qualsiasi utente esterno. Tuttavia, la condivisione è esclusiva. In altre parole, un catalogo condiviso internamente non può essere condiviso con gruppi esterni e viceversa.

Corsi, programmi di apprendimento, risorse formative e certificazioni sono gli oggetti di apprendimento supportati per il catalogo condiviso.

Per ulteriori informazioni, consulta [Condividere i cataloghi](/help/migrated/administrators/feature-summary/catalogs.md).

## Abilita il controllo completo del catalogo condiviso {#fullcontrol}

Puoi concedere l’accesso completo al catalogo ad account esterni. L’Amministratore dell’account può quindi accettare il catalogo e aggiungere o eliminare eventuali corsi di formazione o moduli.

Per concedere il pieno controllo a un account esterno,

1. Dopo aver aggiunto uno o più corsi di formazione a un catalogo, è necessario condividerlo con utenti esterni.
1. Nella finestra di dialogo Account esterno, aggiungi il sottodominio e l&#39;ID e-mail dell&#39;amministratore dell&#39;organizzazione esterna.
1. Nell’opzione Controllo catalogo, attiva/disattiva il pulsante per consentire agli utenti esterni il controllo completo del catalogo.

   ![](assets/catalog-control.png)

   *Consenti il controllo completo del catalogo condiviso*

   Quando si consente il controllo completo del catalogo, l&#39;amministratore dell&#39;organizzazione esterna accetta la richiesta di consentire le modifiche al catalogo. L’Autore dell’organizzazione esterna può quindi modificare i corsi o aggiungere moduli.

   Per ulteriori informazioni, consulta le sezioni seguenti.

## Amministratore dell’organizzazione esterna {#administratorofexternalorganization}

Una volta che l’Amministratore dell’organizzazione precedente abilita il controllo completo del catalogo, l’Amministratore dell’organizzazione esterna accetta la richiesta e la visualizza.

1. Fate clic sull’icona di notifica per visualizzare la notifica di accettazione del catalogo.

   <!--![](assets/notification-to-acceptcatalog.png)-->

1. Per accettare l’invito per il catalogo, fai clic su Accetta.
1. Nell’elenco dei cataloghi, se avvii il catalogo condiviso, viene visualizzato un messaggio che indica che il catalogo ha ora il controllo completo.

   ![](assets/catalog-details.png)

   *Visualizzare i dettagli del catalogo*

1. Potete modificare il nome del catalogo e la descrizione.

## Condividere il catalogo per il programma di apprendimento, la certificazione e le risorse formative {#sharecatalogforlearningprogramcertificationandjobaids}

Allo stesso modo della concessione del controllo completo del catalogo per i corsi, l’Amministratore può anche concedere il controllo completo del catalogo per:

* Programmi di apprendimento
* Certificazioni
* Risorse formative

## Ripristina corso {#resetcourse}

1. Nella scheda del catalogo con un collegamento interrotto, fate clic su **[!UICONTROL Ripristina corso]**.

<!-- ![](assets/reset-course.png)-->

1. Dopo aver fatto clic sul pulsante Ripristina, viene visualizzato un messaggio di avviso. Reimpostazione del corso:

   * Rimuove tutto il contenuto appena aggiunto dal catalogo.
   * Aggiorna il catalogo sincronizzato con il catalogo condiviso originale.
   * Ripristina la relazione con l’oggetto di apprendimento principale.

   Il ripristino del catalogo è irreversibile. Non è possibile annullare le modifiche apportate al catalogo.

1. Per accettare le modifiche, fare clic su Sì.
1. Nel catalogo del corso, noterai che non è presente il messaggio *Collegamento interrotto* più.

   Quando visualizzi i dettagli del catalogo, puoi notare che ora è stato ripristinato lo stato originale del catalogo.

## Aggiungere di nuovo un oggetto di apprendimento {#readdalearningobject}

Se hai rimosso inavvertitamente un corso, un programma di apprendimento, una certificazione o una risorsa formativa, puoi ripristinarlo.

Per ripristinare un oggetto di apprendimento eliminato, fai clic su Aggiungi di nuovo.

Questa azione annulla l’azione e ripristina l’oggetto di apprendimento nella vista catalogo.

![](assets/re-add-button.png)

*Aggiungi nuovamente un oggetto di apprendimento*

Dopo aver fatto clic sul pulsante Aggiungi di nuovo, viene visualizzato un messaggio di conferma che l’oggetto di apprendimento è stato aggiunto correttamente al catalogo.

## Organizzazione esterna {#externalorganization}

Una volta che l’Amministratore dell’account esterno ha accettato il catalogo, l’Autore può ora aggiungere corsi e programmi di apprendimento.

1. Come utente, riceverai una notifica che avvisa che il catalogo è ora disponibile nel tuo account.
1. Per visualizzare l’elenco dei corsi, fai clic su **[!UICONTROL Corsi]** nel riquadro di navigazione sinistro. Puoi visualizzare tutti i corsi creati da te e condivisi con te.
1. Per visualizzare i dettagli del corso, fai clic su **[!UICONTROL Visualizza corso]** sulla scheda del corso.

   <!--![](assets/view-course.png)-->

1. Nella pagina dei dettagli del corso, puoi visualizzare le informazioni sul corso e sui moduli condivisi. Per aggiungere un modulo, fai clic su Aggiungi moduli. Quando aggiungi moduli ai moduli esistenti, i nuovi moduli vengono visualizzati alla fine dei moduli esistenti. Puoi sempre riorganizzare i moduli.
1. Dopo aver aggiunto i moduli, fai clic su Ripubblica.

   Dopo aver ripubblicato i moduli, nella scheda del catalogo viene visualizzato un messaggio *Collegamento interrotto*.

   Poiché hai aggiornato il catalogo originale con nuovi moduli, la relazione esistente con il corso acquisito non esiste più.

   L’oggetto di apprendimento non sarà sincronizzato con l’account di origine poiché il contenuto dell’oggetto di apprendimento è stato modificato.

   <!--![](assets/link-broken.png)-->

Dopo aver aggiunto e ripubblicato il modulo, se ritieni di aver aggiunto o eliminato inavvertitamente un corso nel catalogo in precedenza, puoi ripristinare il modulo e ripristinarne lo stato originale quando è stato condiviso per la prima volta con il controllo completo.
