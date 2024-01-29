---
description: Leggi questo articolo per scoprire come configurare le impostazioni del profilo dell’Allievo e aggiungere una foto del profilo. Scopri come scaricare la trascrizione Allievo per il tuo profilo.
jcr-language: en_us
title: Impostazioni profilo
contentowner: manochan
source-git-commit: a495c86f8dff3ebc51e7700a3f3bcf7ce57d1311
workflow-type: tm+mt
source-wordcount: '783'
ht-degree: 0%

---



# Impostazioni profilo

Leggi questo articolo per scoprire come configurare le impostazioni del profilo dell’Allievo e aggiungere una foto del profilo. Scopri come scaricare la trascrizione Allievo per il tuo profilo.

## Configurazione delle impostazioni del profilo {#configuringprofilesettings}

1. Nell’angolo superiore destro della pagina, fai clic sulla freccia a discesa accanto al profilo o alla foto.
1. Seleziona Impostazioni profilo.
1. Dalla finestra a comparsa visualizzata, puoi effettuare le seguenti operazioni:

   * Aggiungi/aggiorna foto profilo: passa il mouse sulla foto. Fai clic su Carica e aggiungi una foto. Fate clic su Modifica per modificare la foto.
   * Elimina foto: passate il mouse sulla foto del profilo. Fai clic su Elimina.
   * Per aggiungere il contenuto Informazioni su di me, fai clic sull’area di testo sottostante.
   * Modificare il contenuto Informazioni personali facendo clic su Modifica accanto al campo.
   * Imposta le impostazioni internazionali per il tuo profilo. Dal menu a discesa Lingua, seleziona la lingua desiderata.
   * Imposta la lingua corrente per il tuo profilo.
   * Imposta il fuso orario per il tuo profilo.
   * Scarica la Trascrizione Allievi con i tuoi dati.

   ![](assets/learner-preferences.png)
   *Visualizzare le preferenze dell’Allievo*

   Quando fai clic sul collegamento Scarica la mia trascrizione di apprendimento XLS, nel tuo sistema viene scaricato un foglio Excel. Questo foglio Excel contiene i dettagli sugli oggetti di apprendimento utilizzati, lo stato di completamento di ciascun oggetto di apprendimento, le date di scadenza corrispondenti, le abilità acquisite e così via. Scarica questo foglio per ottenere rapidamente alcuni dati complessivi per il tuo profilo di apprendimento.

1. Se un amministratore ha abilitato l’e-mail di riepilogo e non sei nell’elenco DND, puoi iscriverti o annullare l’iscrizione alle e-mail di riepilogo. Abilita l’opzione seguente.

   ![](assets/digest-email-option-learner.png)
   *Iscriviti o annulla l’iscrizione alle e-mail di riepilogo*

   In base alla frequenza impostata dall’Amministratore, l’Allievo riceverà l’e-mail con cadenza bisettimanale o mensile.

## Annulla l’iscrizione alle e-mail di riepilogo {#unsubscribefromdigestemails}

Quando ricevi un messaggio e-mail, puoi annullare l’iscrizione all’e-mail di riepilogo facendo clic sul pulsante **Annulla abbonamento** link in fondo all’e-mail.

Dopo aver fatto clic su **[!UICONTROL Annulla abbonamento]**, verrai reindirizzato al **Impostazioni profilo** , in cui è possibile disattivare l’opzione per ricevere e-mail.

## Anatomia di un&#39;e-mail di riepilogo {#anatomyofadigestemail}

Un&#39;e-mail di riepilogo è composta dalle seguenti sezioni:

<table>
 <tbody>
  <tr>
   <td>
    <p><b>Sezione</b></p></td>
   <td>
    <p><b>Descrizione</b></p></td>
  </tr>
  <tr>
   <td>
    <p>Riepilogo dei corsi di formazione personali</p></td>
   <td>
    <p>Questa sezione personalizza le metriche di formazione di un Allievo indicando il numero di minuti dedicati ai corsi di formazione.</p>
    <p>In base al tempo impiegato dall’Allievo, il contenuto viene personalizzato in base alle regole definite di seguito:</p>
    <p>Se (time_spent) &gt;= 60 minuti, viene visualizzato il testo seguente:</p>
    <p><i>"Durante le ultime due settimane/l’ultimo mese, lei ha <b>(time_spent)</b> minuti di formazione per riqualificarsi. Di seguito sono elencati alcuni consigli per consentirti di ulteriori informazioni." </i></p>
    <p> Se (time_spent) &lt; 60 minuti, viene visualizzato il testo seguente:</p>
    <p><i>"Durante le ultime due settimane/l’ultimo mese, lei ha <b>(time_spent)</b> minuti di formazione per riqualificarsi. Di seguito sono elencati alcuni consigli che ci auguriamo possano esserti utili per iniziare e continuare."</i></p></td>
  </tr>
  <tr>
   <td>
    <p>Attività di formazione</p></td>
   <td>
    <p>Questa sezione visualizza il riepilogo a livello di organizzazione dell’attività di formazione per l’account.</p>
    <p>Il riepilogo dell'attività di formazione è costituito dai seguenti elementi: </p>
    <ul>
     <li>Numero di corsi di formazione disponibili nell’account.</li>
     <li>Numero di coallievi che hanno seguito attivamente le attività di formazione.</li>
     <li>Numero di ore di apprendimento dedicate dai colleghi.</li>
     <li>Tempo medio (in minuti) impiegato dai colleghi per migliorare le competenze nell’account.</li>
    </ul></td>
  </tr>
  <tr>
   <td>
    <p>Corsi consigliati</p></td>
   <td>
    <p>Questa è una sezione personalizzata che include i corsi di formazione consigliati per gli Allievi. In questa sezione, un Allievo può visualizzare tre corsi di formazione selezionati dal motore di raccomandazione.</p>
    <p>Ogni corso di formazione dispone di un pulsante Esplora che, quando viene selezionato, consente di reindirizzare alla home page dell’app per Allievi.  </p></td>
  </tr>
  <tr>
   <td>
    <p>Classifica</p></td>
   <td>
    <p>Visualizza un grafico a barre in cui ogni barra rappresenta un Allievo e i relativi punti di gamification (solo se l’Amministratore ha abilitato la gamification per tutti gli allievi).</p>
    <p>La classifica visualizza quanto segue:</p>
    <ul>
     <li>Punti guadagnati da un Allievo.</li>
     <li>Punti necessari per raggiungere il livello successivo.</li>
    </ul>
    <p>È inoltre disponibile una mini classifica che mostra il coordinatore e i due allievi più vicini all’allievo in tale ambito utente.</p>
    <p>Se la classifica è vuota, questa sezione non viene visualizzata nell'e-mail.</p></td>
  </tr>
  <tr>
   <td>
    <p><a>Post social</a></p></td>
   <td>
    <p>Questa sezione mostra i tre post social più recenti.</p>
    <p>Un Allievo può visualizzare la data di creazione, il nome della bacheca, l’eventuale titolo del post, il nome utente e l’icona del creatore. Il post può anche contenere un video, un documento, un PDF o qualsiasi altro file.</p>
    <p>Ogni post contiene collegamenti per reindirizzare l’Allievo alla pagina di apprendimento sociale nell’app per Allievi.</p>
    <p>Se non sono presenti post recenti, questa sezione dell’e-mail non sarà visibile all’Allievo.</p></td>
  </tr>
 </tbody>
</table>

## Domande frequenti {#frequentlyaskedquestions}

**1. Come si scarica una Trascrizione Allievo come Allievo?**

Nell’angolo in alto a destra, fai clic sul tuo **[!UICONTROL profilo utente]** > **[!UICONTROL Impostazioni profilo]**. Nella finestra di dialogo visualizzata, fai clic su **Scarica la mia trascrizione di apprendimento (XLS)**.

![](assets/dowload-lt.png)
*Scarica Trascrizione Allievo*
