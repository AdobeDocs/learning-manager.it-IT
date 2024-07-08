---
description: Scopri come creare contenuti da allineare ai corsi come contenuti autonomi.
jcr-language: en_us
title: Libreria dei contenuti
exl-id: cc19eca6-6b47-44b2-ad23-2d7ad8975f65
source-git-commit: 76d84364ce037a81d77e3e2fa3f68fdef7ff411d
workflow-type: tm+mt
source-wordcount: '3542'
ht-degree: 50%

---

# Libreria dei contenuti

Scopri come creare contenuti da allineare ai corsi come contenuti autonomi.

## Libreria dei contenuti {#contentlibrary}

I contenuti sono gli elementi costitutivi di un corso. Gli Autori creano una libreria di moduli che può essere allineata ai corsi come contenuto autonomo. Solo gli Autori hanno accesso alla libreria di contenuti.

## Tipi di contenuto supportati {#supported}

Nella libreria puoi caricare sia contenuti interattivi che statici.

La tabella seguente mostra i tipi di file interattivi e statici che è possibile caricare nella libreria.

<table>
 <tbody>
  <tr>
   <td>
    <p><b>Contenuti interattivi</b></p></td>
   <td>
    <p><b>Tipo di contenuto</b></p></td>
   <td>
    <p><b>Estensioni</b></p></td>
  </tr>
  <tr>
   <td>
    <p> </p></td>
   <td>
    <p></p>
    <ul>
     <li>SCORM 1.2</li>
     <li>SCORM 2004</li>
     <li>AICC</li>
     <li>TinCan</li>
    </ul>
    <p></p></td>
   <td>
    <p>zip</p></td>
  </tr>
  <tr>
   <td>
    <p><b>Contenuti statici</b></p></td>
   <td>
    <p><b>Tipo di contenuto</b></p></td>
   <td>
    <p><b>Estensioni</b></p></td>
  </tr>
  <tr>
   <td>
    <p> </p></td>
   <td>
    <p>Video</p></td>
   <td>
    <p>mp4, wmv, 3gp, 3g2, 3gp2, asf, avi, f4v h264, mpe, mpeg, mpg, mpg2, m4v, mov, wmv</p></td>
  </tr>
  <tr>
   <td>
    <p> </p></td>
   <td>
    <p>Audio</p></td>
   <td>
    <p>mp3, wav, aac, m4a, wma, vorbis, pcm, eac3, amr, ac3</p></td>
  </tr>
  <tr>
   <td>
    <p> </p></td>
   <td>
    <p>PDF</p></td>
   <td>
    <p>pdf</p></td>
  </tr>
  <tr>
   <td>
    <p> </p></td>
   <td>
    <p>MS PowerPoint</p></td>
   <td>
    <p>pptx, ppt</p></td>
  </tr>
  <tr>
   <td>
    <p> </p></td>
   <td>
    <p>MS Word</p></td>
   <td>
    <p>docx, doc</p></td>
  </tr>
  <tr>
   <td>
    <p> </p></td>
   <td>
    <p>MS Excel</p></td>
   <td>
    <p>xlsx, xls</p></td>
  </tr>
  <tr>
   <td>
    <p> </p></td>
   <td>
    <p>HTML</p></td>
   <td>
    <p>html o htm</p></td>
  </tr>
 </tbody>
</table>

## Aggiunta di nuovi contenuti alla libreria {#addnewcontentinthelibrary}

**Gli autori** possono aggiungere contenuti in ALM. Ci sono due tipi di contenuti in ALM: **[!UICONTROL Contenuto]** e **[!UICONTROL Quiz]**. Per informazioni su come aggiungere contenuti, vedere [Aggiungere contenuto](content-library.md#addstaticcontent) statico e [Creare un quiz](content-library.md##createaquiz).

## Aggiunta di contenuti statici {#addstaticcontent}

1. Selezionare **[!UICONTROL Libreria contenuti nel riquadro sinistro dopo aver effettuato l&#39;accesso come** Autore e selezionare **[!UICONTROL Aggiungi]****.]**

   In alternativa, puoi selezionare **[!UICONTROL Crea contenuto]** dalla **[!UICONTROL pagina Guida introduttiva]** .

1. **[!UICONTROL Nel campo Nome]**, digitare un nome per il contenuto che si desidera caricare.
1. **[!UICONTROL Nel campo Descrizione]** digitare la descrizione del contenuto. Assicurati che la descrizione che vuoi inserire sia provvista di significato. Il limite di caratteri è pari a 400 caratteri.
1. Per aggiungere il contenuto, selezionare **[!UICONTROL Aggiungi file]** di contenuto e caricare il file di risorse. Quando si aggiungono contenuti per più lingue, non è possibile combinare contenuti statici e interattivi all’interno di un singolo gruppo. I contenuti di tutte le versioni locali devono essere o tutti statici o tutti interattivi.

   Se desideri sostituire il contenuto, poi sostituire un contenuto statico con un altro contenuto statico. Lo stesso vale per il contenuto interattivo.

1. **[!UICONTROL Nel campo Durata]**, puoi facoltativamente digitare il tempo previsto che un Allievo trascorrerebbe in questo modulo. La durata è espressa in minuti.

   Se l&#39;Allievo contrassegna un corso come completato, calcoliamo il tempo di apprendimento in base alla durata specificata. Se l&#39;Allievo utilizza il contenuto nel lettore, il tempo trascorso nel lettore viene aggiunto al tempo trascorso nell&#39;apprendimento. Se il tempo effettivo del contenuto è inferiore alla durata specificata, il lettore visualizza l&#39;ora del contenuto così com&#39;è. In questo caso non vengono apportate modifiche.

1. **[!UICONTROL Nel campo Tag]**, digita i tag per il contenuto caricato in modo che diventi individuabile.

   Un Autore può utilizzare questi tag per cercare il contenuto e aggiungerlo al corso.

### Aggiungere il tipo di file HTML5 nella libreria dei contenuti

Gli autori possono aggiungere contenuto HTML5 come file .zip al contenuto di autoapprendimento. La cartella .zip deve contenere un file HTML denominato `index.html`. Se ci sono più file HTML, devono essere tutti collegati, con il file principale chiamato `index.html`. Gli Allievi possono visualizzare il contenuto HTML5 nel lettore Fluidic. L&#39;Autore può aggiungere questo contenuto HTML5 al modulo di autoapprendimento di un corso e impostare i criteri di completamento. Gli Autori possono impostare i criteri per il completamento del corso HTML in uno dei due modi seguenti:

* L&#39;Allievo può contrassegnarlo come completato.
* Sarà contrassegnato come completato una volta avviato il corso.

Per aggiungere il tipo di file HTML .zip alla libreria contenuto, attenersi alla seguente procedura.

1. Nell&#39;app Autore, seleziona **[!UICONTROL Crea contenuto]** nella home page.
1. **[!UICONTROL Nella schermata Libreria]** contenuto, seleziona **[!UICONTROL Aggiungi]** > **[!UICONTROL contenuto]**.
1. Digitare il nome e la descrizione del contenuto.
1. Seleziona l&#39;opzione **[!UICONTROL Aggiungi file di contenuto]** , quindi sfoglia e seleziona i file HTML (compressi come una cartella).
1. Dopo aver aggiunto il contenuto, è possibile visualizzarlo nella **[!UICONTROL sezione Libreria]** contenuto.
1. Selezionare il contenuto HTML, quindi fare clic su **[!UICONTROL Modifica]**.
1. Selezionate una delle opzioni seguenti dall&#39;opzione **[!UICONTROL Criteri]** di completamento.
   * **[!UICONTROL All&#39;avvio del contenuto]**: il corso verrà contrassegnato come completato automaticamente quando l&#39;Allievo lo avvia.
   * **[!UICONTROL Voti dell&#39;Allievo completati]**: l&#39;Allievo ha la possibilità di contrassegnare il corso come completato nel lettore Fluidic.

   ![](assets/completion-criteria.png)
   _Criteri di completamento_

1. Seleziona **[!UICONTROL Salva]**.
1. Crea un corso aggiungendo questo contenuto.  Per ulteriori informazioni, consulta [Creare, modificare e pubblicare corsi](/help/migrated/authors/feature-summary/courses.md).

Nell&#39;applicazione per gli Allievi, se un Autore seleziona criteri di selezione come **[!UICONTROL All&#39;avvio del contenuto]**, il corso verrà contrassegnato come completato all&#39;avvio dell&#39;Allievo. Quando un Autore sceglie **[!UICONTROL L&#39;Allievo contrassegna come completato]**, avrà la possibilità di contrassegnare il corso come completato.

![](assets/completion-criteria-fluidic-player.png)

_Voti Allievo completati_

### Controllo delle versioni {#versioning}

La libreria dei contenuti registra anche il controllo delle versioni per i contenuti caricati. Se apporti modifiche al contenuto, ad esempio a una presentazione di PowerPoint, e carichi nuovamente il file PPT nella libreria, il numero di versione aumenta di un’unità. Questo ti aiuta a tenere traccia delle modifiche nel tuo contenuto.

## Aggiunta di contenuto interattivo {#addinteractivecontent}

1. Selezionare **[!UICONTROL Libreria contenuti nel riquadro sinistro dopo aver effettuato l&#39;accesso come** Autore e selezionare **[!UICONTROL Aggiungi]****.]**

   In alternativa, puoi selezionare **[!UICONTROL Crea contenuto]** dalla **[!UICONTROL pagina Guida introduttiva]** .

1. **[!UICONTROL Nel campo Nome]**, digitare un nome per il contenuto che si desidera caricare.
1. **[!UICONTROL Nel campo Descrizione]** digitare la descrizione del contenuto.

   >[!NOTE]
   >
   >Assicurati che la descrizione che vuoi inserire sia provvista di significato. Il limite di caratteri è pari a 245 caratteri.

1. Per aggiungere il contenuto, selezionare **[!UICONTROL Aggiungi file]** di contenuto e caricare il file di risorse. Quando si aggiungono contenuti per più lingue, non è possibile combinare contenuti statici e interattivi all’interno di un singolo gruppo. I contenuti di tutte le versioni locali devono essere o tutti statici o tutti interattivi.

* [Tipi di file supportati](content-library.md#supported)

  Il contenuto interattivo può essere un progetto pubblicato SCORM, AICC o Captivate. Il file deve essere un file zip.

  Puoi anche aggiungere contenuto HTML generato da Captivate, Presenter o Presenter Video Express.

1. Learning Manager supporta i sottotitoli per i contenuti video caricati in Learning Manager. Ora gli Autori possono caricare il file contenente i sottotitoli insieme al file video.

   Gli studenti possono quindi visualizzare le didascalie durante la riproduzione del modulo video.

   Il formato supportato è [Web Video Text Tracks (webVTT).](https://www.w3.org/TR/webvtt1/)

   Il supporto delle didascalie è disponibile per i contenuti video caricati in Libreria dei contenuti di Learning Manager.

   Come autore, quando carichi un contenuto video o audio, puoi anche caricare il file VTT che contiene le didascalie.

   I sottotitoli appaiono quindi nel lettore Fluidic. Le didascalie sono inoltre conformi agli [standard](https://www.w3.org/TR/WCAG20/) WCAG2.0.

   Quando aggiungi un contenuto video alla libreria, puoi anche aggiungere il file VTT, che **deve** essere un file valido.

   ![](assets/webvtt.png)

   *Aggiungere un file webvtt*

   Il file VTT caricato corrisponde alla versione esistente del contenuto. Pertanto, il file webVTT caricato non si collega alla versione precedente del contenuto.

   Se crei il contenuto in lingue diverse, puoi caricare un file webVTT diverso per ogni lingua. Gli studenti potranno visualizzare le didascalie corrispondenti alla lingua selezionata durante la riproduzione.

   >[!NOTE]
   >
   >   Un file VTT supporta una lingua. Per supportare più lingue, caricate più file video per ogni lingua del contenuto, quindi caricate il rispettivo file VTT per ogni file video.

   Come autore, ogni volta che modifichi il contenuto, il video o l&#39;audio, Learning Manager ti richiede un nuovo file vtt.

   Dopo aver aggiunto questo contenuto a un corso e quando visualizzi l&#39;anteprima del corso come Allievo, puoi visualizzare i sottotitoli nel video.

   Sul lettore, attiva o disattiva il pulsante CC del lettore Fluidic per visualizzare o nascondere le didascalie.

   La stessa visualizzazione è presente nell’**app per Allievi** e nell’**Anteprima come Allievo**.

   Quando si **aggiunge, si aggiorna o si elimina** il file VTT, si riceve una notifica.
Il supporto WebVTT non è disponibile per:

   1. Annunci video.
   1. Video riprodotto all&#39;interno del contenuto eLearning. Questo dipende dal contenuto.
   1. Video caricato in Apprendimento sociale.
   1. Video creato nell’app desktop Learning Manager.
   1. Contenuto video creato con il processo di migrazione.
   1. Riproduzione di video nell’app mobile in modalità offline.

1. **[!UICONTROL Nel campo Durata]**, puoi facoltativamente immettere il tempo previsto che un Allievo trascorrerebbe in questo modulo. La durata è espressa in minuti.
1. **[!UICONTROL Nel campo Tag]**, immetti i tag per il contenuto caricato in modo che diventi individuabile.

### Supporto per il catalogo condiviso

Se un Account venditore condivide un catalogo contenente i corsi e i corsi contengono moduli, audio o video con i sottotitoli, i corsi devono comportarsi allo stesso modo nell&#39;account acquirente.

La propagazione del modulo deve funzionare correttamente dall’account venditore all’account acquirente. Ciò può includere - modifica / eliminazione / aggiunta del file VTT nel modulo.

Una volta caricato il contenuto, puoi visualizzare una notifica facendo clic sull’icona raffigurante una campana nell’angolo in alto a destra della pagina. Ogni volta che modifichi un contenuto e lo carichi nuovamente, ricevi una notifica. Se apporti le modifiche, solo tu ricevi la notifica, e non gli altri autori.

## Crea un quiz {#createaquiz}

Crea valutazioni all’interno di Adobe Learning Manager con il nuovo strumento per la creazione di quiz nella pagina Libreria dei contenuti. Le valutazioni create diventano parte della Libreria contenuti e possono essere aggiunte a una cartella &quot;pubblica&quot; per la riusabilità del corso.

1. Seleziona Libreria contenuti nel pannello sinistro.
1. Nell&#39;angolo superiore destro dello schermo, seleziona **Aggiungi > quiz**.
1. Nella pagina Crea quiz, digita il nome e la descrizione del quiz.
1. Nella sezione Contenuto quiz, seleziona **Aggiungi domanda per il quiz**.
1. Nella finestra di dialogo della domanda del quiz, seleziona il tipo di domanda. Esistono Sono disponibili tre tipi di domande:
   * Domanda a scelta multipla
   * True o false
   * Compila lo spazio vuoto
1. Immetti la domanda e seleziona la risposta corretta.
1. Definisci i punti per il quiz.
1. Se desideri che alla domanda venga fornita una risposta corretta per superare il quiz, seleziona la casella di controllo **È obbligatorio rispondere correttamente per superare il quiz**.
1. Seleziona **Salva e chiudi**.
1. Inserisci i punti per superare il quiz nel campo Criteri **di** superamento.
1. Se desideri che un Allievo visualizzi una risposta corretta, attiva l&#39;opzione **Mostra risposte** corrette agli Allievi dopo il quiz.
1. Se desideri che le domande e le risposte vengano visualizzate in modo casuale, attiva le opzioni:
   * Ordine domande casuale
   * Ordine delle opzioni di risposta casuale
1. Specifica una cartella in cui aggiungere il quiz per renderlo disponibile a tutti gli autori.
1. **Nel campo Durata**, specifica il tempo che l&#39;Allievo deve dedicare al quiz.
1. Specifica un tag dall’elenco dei tag già creati.
1. Aggiungi un logo e uno sfondo al quiz.
1. Nell&#39;angolo in alto a destra della pagina, selezionare **Pubblica**.

Per aggiungere i quiz in una lingua diversa, segui i passaggi per favore:

1. Per aggiungere il quiz per lingue diverse, selezionare la **scheda Aggiungi nuova lingua** e scegliere le lingue desiderate. Utilizzando questo approccio, puoi aggiungere il supporto multilingue per il tuo contenuto.

   ![](assets/add-new-languagetab.png)

   *Aggiungere una nuova lingua per un contenuto*

1. Ripeti la procedura di caricamento del contenuto per le nuove lingue.
1. Se si desidera rimuovere una lingua, selezionare la **[!UICONTROL scheda Aggiungi nuova lingua]** e cancellare la selezione.

   Dopo aver apportato le modifiche, fai clic su **[!UICONTROL Salva]**. Nella libreria, il nuovo contenuto ora è disponibile per l’uso.

Il quiz viene aggiunto alla libreria ]**contenuto**[!UICONTROL . Come per qualsiasi contenuto nella Libreria dei contenuti, puoi ritirare un quiz e quindi eliminarlo.


## Aggiunta nella cartella {#add-folder}

Dopo che un Amministratore crea le cartelle dei contenuti, come autore puoi caricare un contenuto in una cartella di contenuti affinché il contenuto sia visibile solo a te o a un gruppo di autori selezionato nell’account. Puoi anche rendere il contenuto pubblico e visibile a tutti gli autori nell’account.

**Esempio di utilizzo**

Ad esempio, le agenzie vogliono mantenere il pieno controllo del contenuto e qualcuno che trascura il contenuto deve avere accesso a tutti i contenuti. Allo stesso tempo, i creatori di contenuti nelle agenzie devono avere accesso solo ai propri contenuti e, in alcuni casi, accedere ai contenuti di qualcun altro.

La libreria di contenuti con contenuto esistente (ovvero il contenuto caricato prima della configurazione delle cartelle di contenuto) viene definita come **cartella** pubblica. Questa cartella non può essere ritirata o eliminata. Il contenuto che fa parte della cartella pubblica è accessibile a tutti i tipi di autori. Una volta configurate le cartelle di contenuto, gli autori standard e gli autori personalizzati devono selezionare la cartella in cui inserire il contenuto durante il caricamento del nuovo contenuto.

>[!NOTE]
>
>Le cartelle pubbliche e private si escludono a vicenda. Ciò significa che il contenuto **non può** essere associato contemporaneamente alla cartella pubblica e alla cartella privata. Può essere associata a una cartella **pubblica oppure** a una o più cartelle private in qualsiasi momento.

Quando aggiungi un contenuto, puoi scegliere la cartella in cui risiederà il contenuto.

![](assets/add-to-content-folder.png)

*Aggiungere contenuti alla cartella*

Se scegli **Pubblico**, il contenuto sarà visibile a tutti gli autori. Tutto il contenuto presente nell&#39;account che non fa parte di alcuna cartella sarà nella cartella pubblica, per impostazione predefinita.

Tieni presente che le cartelle dei contenuti sono semplicemente dei comparti virtuali usati per collegare il contenuto. Nel caso in cui un contenuto venga inserito in due cartelle, significa che il file di contenuto è sempre un singolo file ma collegato a più cartelle. Pertanto, nel caso in cui il contenuto venga aggiornato da custom-author-1 che ha accesso a custom-folder-1, lo stesso contenuto aggiornato si rifletterà anche in custom-folder-2 a cui accede custom-author-2.

Nella Libreria dei contenuti sono disponibili due opzioni per la gestione delle cartelle di contenuti:

**Tutte le cartelle**

Si tratta di un elenco che visualizza tutte le cartelle create nell&#39;account.

![](assets/list-of-all-folders.png)

*Visualizza tutte le cartelle*

**Tutti gli autori**

Si tratta di un elenco che mostra gli autori che hanno creato contenuti e li hanno caricati nella libreria.

![](assets/list-of-all-authors.png)

*Vedi tutti gli autori*

Questa opzione è disponibile **solo** quando un amministratore crea una nuova cartella.

## Spostamento del contenuto nella cartella {#movecontenttofolder}

Per spostare il contenuto di una cartella pubblica in una cartella privata,

1. Selezionare **Cartella pubblica** dall&#39;elenco **a discesa Tutte le cartelle** .

   ![](assets/list-of-public-folders.png)

   *Visualizzare tutti i contenuti caricati*

1. Scegli il contenuto che desideri spostare in una cartella. Quindi fai clic su Azioni > Organizza contenuto ]**>**[!UICONTROL  Sposta contenuto nella cartella ]**.******[!UICONTROL 

   ![](assets/move-content-to-folder.png)

   *Spostare un contenuto selezionato nella cartella*

1. Scegli la cartella in cui desideri spostare il contenuto. Fai clic su **[!UICONTROL Sposta]**.

## Copia del contenuto nella cartella {#copycontenttofolder}

Copiare una cartella significa aggiungere un tag alla cartella. L&#39;operazione di copia non creerà copie del contenuto, ma aggiungerà solo un&#39;associazione con le cartelle specificate.

![](assets/copy-content-to-folder.png)

*Copiare una cartella*

## Scollegamento della cartella {#unlinkfolder}

Scollegamento significa rimuovere il contenuto dalla cartella selezionata.

Il contenuto può essere scollegato da una cartella **specificata SOLO** se è associato anche ad altre cartelle. Se il contenuto che viene scollegato è associato a una sola cartella, è consigliabile utilizzare invece l&#39;operazione SPOSTA.

>[!NOTE]
>
>Il menu Organizza, in Azioni, è inizialmente disattivato. Per utilizzarlo, devi prima selezionare una cartella nell’elenco a discesa delle cartelle.

![](assets/unlink-a-folder.png)

*Scollegare una cartella*

## Aggiunta di contenuto per lingue diverse {#addcontentfordifferentlanguages}

1. Per aggiungere contenuto per lingue diverse, fare clic sulla **scheda Aggiungi nuova lingua** e scegliere le lingue desiderate. Utilizzando questo approccio, puoi aggiungere il supporto multilingue per il tuo contenuto.

   ![](assets/add-new-languagetab.png)

   *Aggiungere una nuova lingua per un contenuto*

1. Ripeti la procedura di caricamento del contenuto per le nuove lingue.
1. Per rimuovere una lingua, fai clic sulla scheda Aggiungi una nuova lingua e annulla la selezione corrispondente.

   Dopo aver apportato le modifiche, fai clic su Salva. Nella libreria, il nuovo contenuto ora è disponibile per l’uso.

## Impostazione dei criteri di completamento {#setcompletioncriteria}

<table>
 <tbody>
  <tr>
   <td>
    <p><b>Contenuti statici</b></p></td>
   <td>
    <p><b>Contenuti interattivi</b></p></td>
  </tr>
  <tr>
   <td>
    <p>Puoi impostare solo i criteri <b>Completamento</b> per il contenuto relativo alle seguenti opzioni:</p>
    <ul>
     <li>All’avvio del contenuto</li>
     <li>In base alla percentuale minima richiesta</li>
    </ul></td>
   <td>
    <p>Puoi impostare sia i criteri <b>Completamento</b> sia i criteri <b>Operazione riuscita</b> per il contenuto per le opzioni seguenti:</p>
    <ul>
     <li>All’avvio del contenuto</li>
     <li>In base alla percentuale minima richiesta</li>
     <li>Opzioni Quiz superato o Tentativi nei quiz</li>
    </ul>
    <p><b>NOTA:</b> è possibile modificare solo il contenuto HTML di Captivate, Presenter Video Express o Presenter.</p></td>
  </tr>
 </tbody>
</table>

Dopo aver aggiunto il contenuto, puoi modificarne i criteri di completamento.

In Learning Manager, i distintivi e le abilità vengono assegnati in base al successo e al completamento. Se lo studente ha completato un corso ma non ha ottenuto il successo, non riceve il badge e l’abilità corrispondente all’oggetto di apprendimento.

Ad esempio, se hai utilizzato Adobe Captivate per creare il tuo corso e hai impostato i parametri di apprendimento nella finestra di dialogo Preferenze, le stesse impostazioni vengono migrate su Learning Manager nelle opzioni Criteri di completamento.

Nella sezione Criteri di completamento puoi impostare le opzioni indicate di seguito:

**All’avvio del contenuto:** se abiliti questa opzione definisci i criteri di completamento del contenuto quando uno studente apre il contenuto.

**In base alla percentuale minima richiesta:** imposta un valore come percentuale minima d’uso da parte del tuo allievo. Ad esempio, se imposti la percentuale su 50, lo studente può utilizzare solo il 50% del contenuto e soddisfare comunque i criteri di completamento.

**Quiz:** scegli uno dei seguenti criteri:

* **Quiz superato:** lo stato viene segnalato come Completo solo se uno studente supera il quiz.
* **Tentativi nei quiz:** lo stato viene segnalato come Completo se gli studenti tentano di superare il quiz, indipendentemente dal fatto che lo superino o meno.
* **Quiz superato o limite raggiunto:** lo stato viene segnalato come Completo se gli studenti superano il quiz o hanno effettuato tutti i tentativi consentiti. Ad esempio, se il numero di tentativi impostati nel corso è pari a due:

   * Se gli Allievi eseguono il primo tentativo e lo superano, lo stato viene segnalato come Completato e Superato.
   * Se gli Allievi eseguono il primo tentativo e falliscono, lo stato viene segnalato come Incompleto e Non riuscito poiché il limite di tentativi non è ancora stato raggiunto.
   * Se gli Allievi ripetono il quiz e falliscono, lo stato viene segnalato come Completato e Non superato.
   * Se gli Allievi tentano nuovamente il quiz e lo superano, lo stato viene segnalato come Completato e Superato.

## Impostazione dei criteri di successo {#setsuccesscriteria}

Allo stesso modo, puoi definire i criteri di successo per il corso. Un criterio di successo indica che le prestazioni di un Allievo sono Superate o Non superate. Se hai creato un corso in Captivate puoi impostare i criteri di successo per il corso nella finestra di dialogo Preferenze, come mostrato di seguito:

Ad esempio, hai caricato un modulo che contiene un quiz. Ora hai impostato i Criteri di completamento per quel modulo su All’avvio del contenuto e i Criteri di successo su Quiz superato.

Se lo studente ha avviato il corso e non ha superato il quiz, il corso viene contrassegnato come Completato, ma i Criteri di successo saranno soddisfatti solo quando lo studente supererà il test.

## Opzioni filtro contenuto {#contentfilteroptions}

### Ordina in base alla data {#sortaccordingtodate}

Organizza il contenuto in base a quando il contenuto è stato modificato per l’ultima volta. Puoi ordinare il contenuto in ordine crescente o decrescente.

![](assets/according-to-date.png)

*Ordinare i contenuti per data*

### Ordina in base all’utilizzo {#sortaccordingtousage}

Organizza il contenuto in base al suo utilizzo nei corsi. Nel menu a discesa Tipo, scegli In uso o Non utilizzato.

![](assets/according-to-usage.png)

*Ordinare i contenuti in base all&#39;utilizzo*

## Ricerca dei contenuti {#searchforcontent}

Nella Libreria dei contenuti puoi cercare un contenuto scegliendo il nome del contenuto o i tag associati al contenuto stesso.

Nella barra di ricerca, immetti il nome di un corso o un tag e visualizza i consigli corrispondenti.

<!--![](assets/search-bar.png)-->

## Ritiro di contenuti {#retirecontent}

Una volta pubblicato un contenuto, non puoi eliminarlo. Devi prima ritirare il contenuto. Quando contrassegni un contenuto come Ritirato, il contenuto non è più visibile agli studenti. Il contenuto viene inoltre spostato nella sezione Ritirato. In un secondo momento puoi anche spostare il contenuto allo stato Pubblicato.

Per ritirare un contenuto, attieniti alla seguente procedura:

* In Libreria dei contenuti, seleziona il contenuto che desideri ritirare.
* Seleziona Azione > Ritira.

I contenuti utilizzati negli oggetti di apprendimento non vengono modificati. Gli Allievi possono continuare ad accedere al contenuto.

>[!NOTE]
>
>Puoi anche aggiungere contenuto dalla sezione Ritirato ]**, passare a Libreria]** contenuti **[!UICONTROL >**[!UICONTROL  Ritirato ]**e selezionare**[!UICONTROL  Aggiungi contenuto ]**.**[!UICONTROL  Per ulteriori informazioni, consulta [Aggiungere contenuto statico](content-library.md#addstaticcontent).


## Ripubblicazione di contenuto ritirato {#republishretiredcontent}

Una volta che hai ritirato un contenuto, puoi decidere di ripubblicarlo e tornare a visualizzarlo nell’elenco Pubblicato. Ad esempio, se hai ritirato la versione 1 di un contenuto e desideri sostituirla con la versione 2, puoi spostare version1.pptx nell’elenco Pubblicato e aggiornare il file con version2.pptx. Il nuovo file diventa disponibile per l’utilizzo in vari corsi.

Per ripubblicare il contenuto ritirato,

1. Passa alla scheda **Ritirato** e seleziona il contenuto che desideri ripubblicare.
1. Seleziona **Azione** > **Ripubblica**.

Il contenuto ora appare nell’elenco Pubblicato.

## Elimina contenuto {#deletecontent}

Dopo che hai ritirato un contenuto, puoi eliminarlo.

* Passa alla scheda Ritirato e seleziona il contenuto che desideri eliminare.
* Seleziona Azione > Elimina.

Ricorda che i corsi esistenti che utilizzano il contenuto eliminato dalla libreria dei contenuti continueranno a utilizzare tale contenuto.

## Domande frequenti {#frequentlyaskedquestions}

+++ Come caricare un contenuto SCORM in Adobe Learning Manager?

Crea un corso di e-learning conforme allo standard SCORM in qualsiasi strumento, ad esempio Adobe Captivate, e pubblica il contenuto come file zip. Quindi, in Learning Manager, carica il file zip nel catalogo e imposta i criteri di completamento e successo.
+++

+++Come faccio a caricare una nuova versione dello stesso contenuto in Learning Manager?

In Learning Manager, la libreria di contenuti gestisce anche le versioni dei contenuti caricati. Se si apportano modifiche al contenuto, ad esempio una presentazione di PowerPoint, e si ricarica nuovamente la presentazione nella libreria, il numero di versione viene incrementato di uno. Questo ti aiuta a tenere traccia delle modifiche nel tuo contenuto. Una nuova versione del contenuto può essere applicata contemporaneamente a tutti gli oggetti di apprendimento oppure puoi applicare singoli aggiornamenti per ogni corso.
+++

+++Come modificare i dettagli di un corso in una lingua diversa?
Dopo aver aggiunto una o più lingue, come descritto nella sezione precedente, fai clic sulla scheda di ciascuna lingua e aggiungi/modifica le informazioni sul corso.

&lt;!--![](assets/edit-course-language.png)--->
+++
