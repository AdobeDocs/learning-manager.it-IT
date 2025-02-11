---
jcr-language: en_us
title: Documentazione API per l’interazione col lettore incorporato
description: Scopri le varie API per ascoltare eventi e attivare azioni nel lettore incorporato
contentowner: chandrum
exl-id: 4734ecc1-cc8a-40b0-8997-32a31ec661ec
source-git-commit: 3d183dc40e4d1962d25160b74d8cf6cfa26e3171
workflow-type: tm+mt
source-wordcount: '833'
ht-degree: 69%

---

# Documentazione API per l’interazione col lettore incorporato

Adobe Learning Manager offre una libreria che può essere integrata in un’app. Questa libreria fornisce varie API per ascoltare gli eventi e attivare le azioni nel lettore incorporato.

Utilizzando le API fornite puoi riprodurre, mettere in pausa ed eseguire altre azioni sul lettore.

## Caricamento della libreria

La libreria è disponibile [qui](https://cpcontents.adobe.com/public/publiccdn/playerInteractionLib.min.js).

Per caricare la libreria, effettua le seguenti operazioni:

1. Carica il file js nell’applicazione consumer.
2. Al caricamento della libreria, window.cpPlayerLib viene popolato.

>[!NOTE]
>
>Se non utilizzi prod US, imposta i parametri cpPlayerLib.env e cpPlayerLib.sourceOrigin in base alla tua env.

I valori predefiniti sono:

* window.cpPlayerLib.env = [https://learningmanager.adobe.com/app/player](https://learningmanager.adobe.com/app/player);
* window.cpPlayerLib.sourceOrigin = &quot;[https://cpcontents.adobe.com](https://cpcontents.adobe.com/)&quot;;

### Metodi disponibili

La libreria cpPlayerLib è composta dalle seguenti funzioni:

**startPlayer**

<table>
<tbody>
<tr>
<td>Nome metodo</td>
<td>startPlayer</td>
</tr>
<tr>
<td>Descrizione</td>
<td>Carica un lettore nell’app.</td>
</tr>
<tr>
<td>Parametri</td>
<td><li>loId: l’ID dell’oggetto di apprendimento.</li><li>accountId: l’ID account dell’account ALM.</li><li>userId: l’ID utente.</li><li>accessToken: il token di accesso.</li><li>domRefId: l’ID del contenitore div in cui deve essere eseguito il rendering del lettore.</li><li>onModuleLoaded: questa funzione viene richiamata quando vengono caricati i moduli con i dettagli seguenti.</li><br><li>contentType</li><li>loId</li><li>moduleId</li><li>completed</li><li>currentLanguage</li><li>availableLanguages</li><li>isCCAavailable</li><li>ccEnabled</li></br></td>
</tr>
<tr>
<td>Restituisce</td>
<td>Restituisce una promessa. Alla risoluzione della promessa, verrà passato un playerObj.</td>
</tr>
<tr>
<td>Eccezione</td>
<td>La promessa darà luogo a un'eccezione.</td>
</tr>
<tr>
<td>Codice di esempio</td>
<td>cpPlayerLib.startPlayer(loId, accountId, userId, accessToken, domRefId, onModuleLoaded).then((playerObj) =&gt; {//playerObj ha le api per interagire con il lettore}) &gt;</td>
</tr>
</tbody>
</table>

**getAllPlayers**

<table>
<tbody>
<tr>
<td>Nome del metodo</td>
<td>getAllPlayers</td>
</tr>
<tr>
<td>Descrizione</td>
<td>Restituisce tutti gli oggetti player nella pagina corrente.</td>
</tr>
<tr>
<td>Parametri</td>
<td>Nessuno</td>
</tr>
</tr>
<tr>
<td>Codice di esempio</td>
<td>cpPlayerLib.getAllPlayers()</td>
</tr>
</tbody>
</table>

**getPlayer**


<table>
<tbody>
<tr>
<td>Nome del metodo</td>
<td>getPlayer</td>
</tr>
<tr>
<td>Descrizione</td>
<td>Restituisce un oggetto player con l’ID dell’oggetto di apprendimento specificato.</td>
</tr>
<tr>
<td>Parametri</td>
<td><li>loId: l’ID dell’oggetto di apprendimento.</li></td>
</tr>
</tr>
<tr>
<td>Codice di esempio</td>
<td>cpPlayerLib.getPlayer(loId)</td>
</tr>
</tbody>
</table>

**navigateToModule**

<table>
<tbody>
<tr>
<td>Nome del metodo</td>
<td>navigateToModule</td>
</tr>
<tr>
<td>Descrizione</td>
<td>Passa al modulo successivo.</td>
</tr>
<tr>
<td>Parametri</td>
<td><li>moduleId: l’ID del modulo.</li></td>
</tr>
</tr>
<tr>
<td>Codice di esempio</td>
<td>playerObj.navigateToModule(moduleID)</td>
</tr>
</tbody>
</table>

**avanti**

<table>
<tbody>
<tr>
<td>Nome del metodo</td>
<td>next</td>
</tr>
<tr>
<td>Descrizione</td>
<td>Passa al modulo successivo.</td>
</tr>
<tr>
<td>Parametri</td>
<td><li>Nessuno</li></td>
</tr>
</tr>
<tr>
<td>Codice di esempio</td>
<td>playerObj.next()</td>
</tr>
</tbody>
</table>

**precedente**

<table>
<tbody>
<tr>
<td>Nome del metodo</td>
<td>previous</td>
</tr>
<tr>
<td>Descrizione</td>
<td>Passa al modulo precedente.</td>
</tr>
<tr>
<td>Parametri</td>
<td><li>Nessuno</li></td>
</tr>
</tr>
<tr>
<td>Codice di esempio</td>
<td>playerObj.previous()</td>
</tr>
</tbody>
</table>

**toggleTOC**

<table>
<tbody>
<tr>
<td>Nome del metodo</td>
<td>toggleTOC</td>
</tr>
<tr>
<td>Descrizione</td>
<td>Attiva/disattiva il pannello Sommario sul lettore.</td>
</tr>
<tr>
<td>Parametri</td>
<td><li>Nessuno</li></td>
</tr>
</tr>
<tr>
<td>Codice di esempio</td>
<td>playerObj.toggleTOC()</td>
</tr>
</tbody>
</table>

**toggleNotes**

<table>
<tbody>
<tr>
<td>Nome del metodo</td>
<td>toggleNotes</td>
</tr>
<tr>
<td>Descrizione</td>
<td>Attiva/disattiva il pannello Note sul lettore.</td>
</tr>
<tr>
<td>Parametri</td>
<td><li>Nessuno</li></td>
</tr>
</tr>
<tr>
<td>Codice di esempio</td>
<td>playerObj.toggleNotes()</td>
</tr>
</tbody>
</table>

**toggleClosedCaption**

<table>
<tbody>
<tr>
<td>Nome del metodo</td>
<td>toggleClosedCaption</td>
</tr>
<tr>
<td>Descrizione</td>
<td>Attiva/disattiva la visualizzazione dei sottotitoli codificati sul lettore.</td>
</tr>
<tr>
<td>Parametri</td>
<td><li>Nessuno</li></td>
</tr>
</tr>
<tr>
<td>Codice di esempio</td>
<td>playerObj.toggleClosedCaption()</td>
</tr>
</tbody>
</table>

**changeLanguage**

<table>
<tbody>
<tr>
<td>Nome del metodo</td>
<td>changeLanguage</td>
</tr>
<tr>
<td>Descrizione</td>
<td>Cambia la lingua del contenuto sul lettore.</td>
</tr>
<tr>
<td>Parametri</td>
<td><li>language: il codice della lingua da specificare.</li></td>
</tr>
</tr>
<tr>
<td>Codice di esempio</td>
<td>playerObj.changeLanguage("es")</td>
</tr>
</tbody>
</table>

**closePlayer**

<table>
<tbody>
<tr>
<td>Nome del metodo</td>
<td>closePlayer</td>
</tr>
<tr>
<td>Descrizione</td>
<td>Chiudere il lettore e rimuoverlo dalla pagina. </td>
</tr>
<tr>
<td>Parametri</td>
<td><li>Nessuno</li></td>
</tr>
</tr>
<tr>
<td>Codice di esempio</td>
<td>playerObj.closePlayer()</td>
</tr>
</tbody>
</table>

**togglePlayPause**

<table>
<tbody>
<tr>
<td>Nome del metodo</td>
<td>togglePlayPause</td>
</tr>
<tr>
<td>Descrizione</td>
<td>Alterna la riproduzione e la sospensione del contenuto sul lettore.</td>
</tr>
<tr>
<td>Parametri</td>
<td><li>Nessuno</li></td>
</tr>
</tr>
<tr>
<td>Codice di esempio</td>
<td>playerObj.togglePlayPause()</td>
</tr>
</tbody>
</table>

**setVolume**

<table>
<tbody>
<tr>
<td>Nome del metodo</td>
<td>setVolume</td>
</tr>
<tr>
<td>Descrizione</td>
<td>Imposta il volume del lettore. Il valore deve essere compreso tra 0 e 1.</td>
</tr>
<tr>
<td>Parametri</td>
<td><li>volume: il valore del volume. L'intervallo valido è 0-1. </li></td>
</tr>
</tr>
<tr>
<td>Codice di esempio</td>
<td>playerObj.setVolume(0.5)</td>
</tr>
</tbody>
</table>

**setPlayBackSpeed**

<table>
<tbody>
<tr>
<td>Nome del metodo</td>
<td>setPlayBackSpeed</td>
</tr>
<tr>
<td>Descrizione</td>
<td>Impostare la velocità di riproduzione nel lettore.</td>
</tr>
<tr>
<td>Parametri</td>
<td><li>speed: il valore della velocità da specificare. I valori validi sono .25, .5, .75, 1, 1.25, 1.5, 1.75, 2.</li></td>
</tr>
</tr>
<tr>
<td>Codice di esempio</td>
<td>playerObj.setPlayBackSpeed(1.25)</td>
</tr>
</tbody>
</table>

**cerca**

<table>
<tbody>
<tr>
<td>Nome del metodo</td>
<td>seek</td>
</tr>
<tr>
<td>Descrizione</td>
<td>Passa a qualsiasi punto del video.</td>
</tr>
<tr>
<td>Parametri</td>
<td><li>time: il punto a cui passare. Il punto è espresso in secondi.</li></td>
</tr>
</tr>
<tr>
<td>Codice di esempio</td>
<td>playerObj.seek(50)</td>
</tr>
</tbody>
</table>

**avanti**

<table>
<tbody>
<tr>
<td>Nome del metodo</td>
<td>forward</td>
</tr>
<tr>
<td>Descrizione</td>
<td>Va avanti di 10 secondi nel video.</td>
</tr>
<tr>
<td>Parametri</td>
<td><li>Nessuno</li></td>
</tr>
</tr>
<tr>
<td>Codice di esempio</td>
<td>playerObj.forward()</td>
</tr>
</tbody>
</table>

**indietro**

<table>
<tbody>
<tr>
<td>Nome del metodo</td>
<td>backward</td>
</tr>
<tr>
<td>Descrizione</td>
<td>Va indietro di 10 secondi nel video.</td>
</tr>
<tr>
<td>Parametri</td>
<td><li>Nessuno</li></td>
</tr>
</tr>
<tr>
<td>Codice di esempio</td>
<td>playerObj.backward()</td>
</tr>
</tbody>
</table>

**navigateToPage**

<table>
<tbody>
<tr>
<td>Nome del metodo</td>
<td>navigateToPage</td>
</tr>
<tr>
<td>Descrizione</td>
<td>Passa alla pagina specificata sul PPT/PDF.</td>
</tr>
<tr>
<td>Parametri</td>
<td><li>pageNumber: numero della pagina a cui passare.</li></td>
</tr>
</tr>
<tr>
<td>Codice di esempio</td>
<td>playerObj.navigateToPage (5)</td>
</tr>
</tbody>
</table>

**paginaSuccessiva**

<table>
<tbody>
<tr>
<td>Nome del metodo</td>
<td>nextPage</td>
</tr>
<tr>
<td>Descrizione</td>
<td>Passa alla pagina successiva sul PPT/PDF.</td>
</tr>
<tr>
<td>Parametri</td>
<td><li>Nessuno</li></td>
</tr>
</tr>
<tr>
<td>Codice di esempio</td>
<td>playerObj.nextPage()</td>
</tr>
</tbody>
</table>

**paginaPrecedente**

<table>
<tbody>
<tr>
<td>Nome del metodo</td>
<td>previousPage</td>
</tr>
<tr>
<td>Descrizione</td>
<td>Passa alla pagina precedente sul PPT/PDF.</td>
</tr>
<tr>
<td>Parametri</td>
<td><li>Nessuno</li></td>
</tr>
</tr>
<tr>
<td>Codice di esempio</td>
<td>playerObj.previousPage()</td>
</tr>
</tbody>
</table>

**zoomIn**

<table>
<tbody>
<tr>
<td>Nome del metodo</td>
<td>zoomIn</td>
</tr>
<tr>
<td>Descrizione</td>
<td>Ingrandisce i contenuti su un PPT/PDF.</td>
</tr>
<tr>
<td>Parametri</td>
<td><li>Nessuno</li></td>
</tr>
</tr>
<tr>
<td>Codice di esempio</td>
<td>playerObj.zoomIn()</td>
</tr>
</tbody>
</table>

**zoomOut**

<table>
<tbody>
<tr>
<td>Nome del metodo</td>
<td>zoomOut</td>
</tr>
<tr>
<td>Descrizione</td>
<td>Rimpicciolisce i contenuti su un PPT/PDF.</td>
</tr>
<tr>
<td>Parametri</td>
<td><li>Nessuno</li></td>
</tr>
</tr>
<tr>
<td>Codice di esempio</td>
<td>playerObj.zoomOut()</td>
</tr>
</tbody>
</table>

**downloadJobAid**

<table>
<tbody>
<tr>
<td>Nome del metodo</td>
<td>downloadJobAid</td>
</tr>
<tr>
<td>Descrizione</td>
<td>Scarica una risorsa formativa da un corso.</td>
</tr>
<tr>
<td>Parametri</td>
<td><li>Nessuno</li></td>
</tr>
</tr>
<tr>
<td>Codice di esempio</td>
<td>playerObj.downloadJobAid()</td>
</tr>
</tbody>
</table>

**toggleJobAidPullout**

<table>
<tbody>
<tr>
<td>Nome del metodo</td>
<td>toggleJobAidPullout</td>
</tr>
<tr>
<td>Descrizione</td>
<td>Se desideri o meno scaricare una risorsa formativa.</td>
</tr>
<tr>
<td>Parametri</td>
<td><li>Nessuno</li></td>
</tr>
</tr>
<tr>
<td>Codice di esempio</td>
<td>playerObj.toggleJobAidPullout()</td>
</tr>
</tbody>
</table>

**schermo intero**

<table>
<tbody>
<tr>
<td>Nome del metodo</td>
<td>fullScreen</td>
</tr>
<tr>
<td>Descrizione</td>
<td>Imposta il lettore sulla modalità a schermo intero.</td>
</tr>
<tr>
<td>Parametri</td>
<td><li>Nessuno</li></td>
</tr>
</tr>
<tr>
<td>Codice di esempio</td>
<td>playerObj.fullScreen()</td>
</tr>
</tbody>
</table>

## Elenco degli eventi

**onPlayerEvents(callBack)**

Al momento della registrazione, la funzione di callback viene richiamata in tutti gli eventi del lettore. I nomi degli eventi sono i seguenti:

* PLAY (video/audio/CP)
* PAUSE (video/audio/CP)
* TIMEUPDATE (video/audio/CP)
* PAGECHANGE (PPT/PDF)
* NOTEADDED (tutti i contenuti)
* LAUNCHED (tutti i contenuti)
* STARTED (tutti i contenuti)
* COMPLETED (tutti i contenuti)
* PASSED (tutti i contenuti)
* FAILED (tutti i contenuti)

**onStreamingEvents(callBack)**

Al momento della registrazione, la funzione di callback viene richiamata su tutte le istruzioni del lettore inviate per il monitoraggio dell’attività dell’utente.
