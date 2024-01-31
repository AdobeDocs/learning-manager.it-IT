---
jcr-language: en_us
title: Abilitare il controllo completo del catalogo condiviso
description: Abilita il controllo completo del catalogo condiviso in Adobe Learning Manager
contentowner: saghosh
source-git-commit: 46afb6603456ced9d7e2aaf98d07ec92fee30c0b
workflow-type: tm+mt
source-wordcount: '791'
ht-degree: 89%

---



# Abilitare il controllo completo del catalogo condiviso

## Crea catalogo {#createcatalog}

In qualità di amministratore, puoi creare un catalogo di corsi, programmi di apprendimento, risorse formative e certificazioni.

Per ulteriori informazioni, consulta [Cataloghi](/help/migrated/administrators/feature-summary/catalogs.md).

## Condividi catalogo {#sharecatalog}

Puoi condividere i cataloghi con gli utenti interni di un’organizzazione o con utenti esterni. Tuttavia, la condivisione è esclusiva. In altre parole, un catalogo condiviso internamente non può essere condiviso con gruppi esterni e viceversa.

Corsi, programmi di apprendimento, risorse formative e certificazioni sono gli oggetti di apprendimento supportati per il catalogo condiviso.

Per ulteriori informazioni, consulta [Cataloghi condivisi](/help/migrated/administrators/feature-summary/catalogs.md).

## Abilitare il controllo completo del catalogo condiviso {#fullcontrol}

Puoi concedere l’accesso completo al catalogo ad account esterni. L’amministratore dell’account può quindi accettare il catalogo e aggiungere o eliminare apprendimenti o moduli di conseguenza.

Per concedere il controllo completo a un account esterno,

1. dopo aver aggiunto apprendimenti a un catalogo, devi condividere il catalogo con utenti esterni.
1. Nella finestra di dialogo Account esterno, aggiungi il sottodominio e l’ID e-mail dell’amministratore dell’organizzazione esterna.
1. Nell’opzione Controllo catalogo, attiva il pulsante per consentire a utenti esterni di controllare completamente il catalogo.

   ![](assets/catalog-control.png)

   *Consenti il controllo completo del catalogo condiviso*

   Quando consenti il controllo completo del catalogo, l’amministratore dell’organizzazione esterna accetta la richiesta di consentire modifiche al catalogo. L’autore dell’organizzazione esterna può quindi modificare i corsi o aggiungere moduli.

   Per ulteriori informazioni consulta le sezioni seguenti.

## Amministratore di organizzazione esterna {#administratorofexternalorganization}

Quando l’amministratore dell’organizzazione precedente abilita il controllo completo del catalogo, l’amministratore dell’organizzazione esterna accetta la richiesta, quindi accetta il catalogo e lo visualizza.

1. Fai clic sull’icona di notifica per visualizzare la notifica per accettare il catalogo.

   <!--![](assets/notification-to-acceptcatalog.png)-->

1. Per accettare l’invito per il catalogo, fai clic su Accetta.
1. Nell’elenco dei cataloghi, se avvii il catalogo che è stato condiviso con te, viene visualizzato un messaggio che indica che il catalogo ora ha il controllo completo.

   ![](assets/catalog-details.png)

   *Visualizzare i dettagli del catalogo*

1. Puoi modificare il nome del catalogo e la descrizione.

## Condividi un catalogo per programmi di apprendimento, certificazioni e risorse formative {#sharecatalogforlearningprogramcertificationandjobaids}

Così come può concedere il controllo completo del catalogo per i corsi, l’amministratore può anche concedere il controllo completo del catalogo per quanto indicato di seguito:

* Programmi di apprendimento
* Certificazioni
* Risorse formative

## Ripristina corso {#resetcourse}

1. Nella scheda del catalogo con un collegamento interrotto, fate clic su **[!UICONTROL Ripristina corso]**.

<!-- ![](assets/reset-course.png)-->

1. Dopo aver fatto clic sul pulsante Ripristina, viene visualizzato un messaggio di avviso. Ripristino del corso:

   * Rimuove tutti i nuovi contenuti aggiunti dal catalogo.
   * Aggiorna il catalogo sincronizzato con il catalogo condiviso originale.
   * Ripristina la relazione con l’oggetto di apprendimento superiore.

   Il ripristino del catalogo è un processo irreversibile. Non è possibile annullare le modifiche apportate al catalogo.

1. Per accettare le modifiche, fai clic su Sì.
1. Nel catalogo del corso, noterai che non è più presente il messaggio *Collegamento interrotto*.

   Nei dettagli del catalogo, risulterà che il catalogo è stato ripristinato allo stato originale.

## Aggiungere nuovamente un oggetto di apprendimento {#readdalearningobject}

Se hai rimosso un corso, un programma di apprendimento, una certificazione o una risorsa formativa inavvertitamente, puoi eseguire un ripristino.

Per ripristinare un oggetto di apprendimento eliminato, fai clic su Riaggiungi.

Questo comando inverte l’azione e ripristina l’oggetto di apprendimento nella vista catalogo.

![](assets/re-add-button.png)

*Aggiungi nuovamente un oggetto di apprendimento*

Dopo aver fatto clic sul pulsante Riaggiungi, viene confermato che l’oggetto di apprendimento è stato aggiunto correttamente al catalogo.

## Organizzazione esterna {#externalorganization}

Dopo che l’amministratore dell’account esterno ha accettato il catalogo, l’autore può aggiungere corsi e programmi di apprendimento.

1. In qualità di utente, riceverai una notifica che avvisa che il catalogo è ora disponibile nel tuo account.
1. Per visualizzare l’elenco dei corsi, fai clic su **[!UICONTROL Corsi]** nel riquadro di navigazione sinistro. Puoi vedere tutti i corsi creati da te e condivisi con te.
1. Per visualizzare i dettagli del corso, fai clic su **[!UICONTROL Visualizza corso]** nella scheda del corso.

   <!--![](assets/view-course.png)-->

1. Nella pagina di dettagli del corso puoi vedere informazioni sul corso e sui moduli condivisi. Per aggiungere un modulo, fai clic su Aggiungi moduli. Quando aggiungi moduli a quelli esistenti, i nuovi moduli vengono visualizzati alla fine dei moduli esistenti. È sempre possibile riordinare i moduli.
1. Dopo aver aggiunto i moduli, fai clic su Ripubblica.

   Una volta ripubblicati i moduli, sulla scheda del catalogo viene visualizzato un messaggio di *Collegamento interrotto*.

   Poiché hai aggiornato il catalogo originale con nuovi moduli, la relazione esistente con il corso acquisito non esiste più.

   L’oggetto di apprendimento non sarà sincronizzato con l’account di origine perché il contenuto dell’oggetto di apprendimento è stato modificato.

   <!--![](assets/link-broken.png)-->

Dopo aver aggiunto e ripubblicato il modulo, se ritieni di aver aggiunto o eliminato inavvertitamente un corso nel catalogo in precedenza, puoi ripristinare il modulo e ripristinarne lo stato originale quando è stato condiviso per la prima volta con il controllo completo.
