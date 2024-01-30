---
description: Leggi questo articolo per scoprire come impostare le impostazioni profilo Allievo e aggiungere una foto profilo. Scopri come scaricare la trascrizione Allievo per il profilo.
jcr-language: en_us
title: Impostazioni profilo
contentowner: manochan
source-git-commit: a495c86f8dff3ebc51e7700a3f3bcf7ce57d1311
workflow-type: tm+mt
source-wordcount: '783'
ht-degree: 75%

---



# Impostazioni profilo

Leggi questo articolo per scoprire come impostare le impostazioni profilo Allievo e aggiungere una foto profilo. Scopri come scaricare la trascrizione Allievo per il profilo.

## Configurazione delle impostazioni profilo {#configuringprofilesettings}

1. Nell’angolo superiore destro della pagina, fai clic sulla freccia a discesa accanto al profilo o alla foto.
1. Seleziona Impostazioni profilo.
1. Nella finestra di dialogo a comparsa visualizzata, puoi effettuare le seguenti azioni:

   * Aggiungi/aggiorna la foto profilo: passa sopra la foto. Fai clic su Carica e aggiungi una foto. Fai clic su Modifica per modificare la foto.
   * Elimina foto: passa sopra la foto profilo. Fai clic su Elimina.
   * Aggiungi il contenuto Informazioni su di me facendo clic sull’area del testo sottostante.
   * Modifica il contenuto Informazioni su di me facendo clic su Modifica accanto al campo.
   * Configura le impostazioni locali per il profilo. Dal menu a discesa delle impostazioni locali seleziona la lingua di tua scelta.
   * Configura le impostazioni locali correnti per il profilo.
   * Imposta il fuso orario per il profilo.
   * Scarica la trascrizione Allievo con i tuoi dati.

   ![](assets/learner-preferences.png)
   *Visualizzare le preferenze dell’Allievo*

   Quando fai clic sul collegamento Scarica le trascrizioni di apprendimento (XLS), nel sistema viene scaricato un Excel. Tale documento contiene i dettagli degli oggetti di apprendimento utilizzati, lo stato di completamento di ogni oggetto di apprendimento, le corrispondenti date di scadenza, le abilità ottenute e così via. Scarica questo documento per ottenere rapidamente alcuni dati completi per il profilo di apprendimento.

1. Se un amministratore ha abilitato l’e-mail di riepilogo e non sei nell’elenco DND, puoi iscriverti o annullare l’iscrizione alle e-mail di riepilogo. Abilita l’opzione seguente.

   ![](assets/digest-email-option-learner.png)
   *Iscriviti o annulla l’iscrizione alle e-mail di riepilogo*

   In base alla frequenza impostata dall’Amministratore, come allievo puoi ricevere l’e-mail una volta ogni due settimane o una volta al mese.

## Annullare l’iscrizione alle e-mail di riepilogo {#unsubscribefromdigestemails}

Quando ricevi un messaggio e-mail, puoi annullare l’iscrizione all’e-mail di riepilogo facendo clic sul pulsante **Annulla abbonamento** link in fondo all’e-mail.

Dopo aver fatto clic su **[!UICONTROL Annulla abbonamento]**, verrai reindirizzato al **Impostazioni profilo** , in cui è possibile disattivare l’opzione per ricevere e-mail.

## Struttura di un’e-mail di riepilogo {#anatomyofadigestemail}

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
    <p>Riepilogo di formazione personale</p></td>
   <td>
    <p>Questa sezione personalizza le metriche di formazione di un Allievo indicando il numero di minuti dedicati ai corsi di formazione.</p>
    <p>In base al tempo impiegato dall’allievo, il contenuto viene personalizzato secondo le regole definite di seguito:</p>
    <p>Se (time_spent) &gt;= 60 minuti, viene visualizzato il testo seguente:</p>
    <p><i>"Durante le ultime due settimane/l’ultimo mese, lei ha <b>(time_spent)</b> minuti di formazione per riqualificarsi. Di seguito sono elencati alcuni consigli per consentirti di ulteriori informazioni." </i></p>
    <p> Se (time_spent) &lt; 60 minuti, viene visualizzato il testo seguente:</p>
    <p><i>"Durante le ultime due settimane/l’ultimo mese, lei ha <b>(time_spent)</b> minuti di formazione per riqualificarsi. Di seguito sono elencati alcuni consigli che ci auguriamo possano esserti utili per iniziare e continuare."</i></p></td>
  </tr>
  <tr>
   <td>
    <p>Attività di formazione</p></td>
   <td>
    <p>Questa sezione mostra il riepilogo a livello di organizzazione delle attività di formazione per l’account in questione.</p>
    <p>Il riepilogo dell'attività di formazione è costituito dai seguenti elementi: </p>
    <ul>
     <li>Numero di corsi disponibili nell’account.</li>
     <li>Numero di co-allievi che hanno effettuato le attività di formazione.</li>
     <li>Numero di ore di formazione impiegate dai colleghi.</li>
     <li>Media di tempo (in minuti) impiegato dai colleghi nel riqualificarsi nell’account.</li>
    </ul></td>
  </tr>
  <tr>
   <td>
    <p>Corsi consigliati</p></td>
   <td>
    <p>Questa è una sezione personalizzata che include i corsi consigliati per gli allievi. In questa sezione, un allievo può vedere tre corsi selezionati dal motore di Consiglio.</p>
    <p>Ogni corso presenta un pulsante Esplora che, una volta selezionato, reindirizza alla pagina principale dell’app per gli Allievi.  </p></td>
  </tr>
  <tr>
   <td>
    <p>La classifica</p></td>
   <td>
    <p>Mostra un istogramma in cui ogni barra rappresenta un allievo e i punti di gamification di ciascun allievo (solo se l’Amministratore ha abilitato Gamification per tutti gli allievi).</p>
    <p>La classifica mostra quanto segue:</p>
    <ul>
     <li>Punti guadagnati da un allievo.</li>
     <li>Punti necessari per raggiungere il livello successivo.</li>
    </ul>
    <p>È presente anche una mini classifica che mostra il leader e i due allievi più vicini all’allievo nell’ambito dell’utente in questione.</p>
    <p>Se la classifica è vuota, questa sezione non viene mostrata nell’e-mail.</p></td>
  </tr>
  <tr>
   <td>
    <p><a>Post social</a></p></td>
   <td>
    <p>Questa sezione mostra i tre post social più recenti.</p>
    <p>Un allievo può vedere la data di creazione, il nome della bacheca, il titolo del post (se presente), il nome utente e l’icona dell’autore. Il post può anche contenere un video, un documento, un .pdf o qualsiasi altro file.</p>
    <p>Ogni post presenta collegamenti per reindirizzare l’allievo alla pagina di apprendimento per social network dell’app per gli Allievi.</p>
    <p>Se non ci sono post recenti, questa sezione dell'e-mail non sarà visibile all’allievo.</p></td>
  </tr>
 </tbody>
</table>

## Domande frequenti {#frequentlyaskedquestions}

**1. Come si scarica una Trascrizione Allievo come Allievo?**

Nell’angolo in alto a destra, fai clic sul tuo **[!UICONTROL profilo utente]** > **[!UICONTROL Impostazioni profilo]**. Nella finestra di dialogo visualizzata, fai clic su **Scarica la mia trascrizione di apprendimento (XLS)**.

![](assets/dowload-lt.png)
*Scarica Trascrizione Allievo*
