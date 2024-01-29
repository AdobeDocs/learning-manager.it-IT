---
description: Scopri come rimuovere i dati degli utenti in Learning Manager.
jcr-language: en_us
title: Rimuovi utenti
contentowner: dvenkate
source-git-commit: 53c1a5283295b56424d697bc26c5db31c2edca0f
workflow-type: tm+mt
source-wordcount: '849'
ht-degree: 0%

---



# Rimuovi utenti

Scopri come rimuovere i dati degli utenti in Learning Manager.

## Panoramica {#overview}

Utilizza la funzione di rimozione degli utenti per rimuovere da Learning Manager le informazioni di identificazione personale e i record di apprendimento dell’utente. Le funzioni Elimina e Rimuovi utente sono due funzioni diverse. Un utente eliminato può essere ripristinato, mentre non è possibile ripristinare tutti i dati utente e i record di apprendimento associati a un utente rimosso.

L’azione di rimozione dell’utente può avere i seguenti risultati:

* Se un utente viene rimosso, i collegamenti nei registri di importazione non funzionano per evitare il download dei vecchi file CSV e il ripristino dei dati utente nel sistema.
* Se un Autore viene rimosso, il suo nome viene sostituito dal nome dell’Amministratore che ha rimosso quell’utente.
* Se gli Istruttori vengono rimossi, vengono rimossi dalle sessioni. L’Amministratore deve sostituire/aggiungere istruttori per tali sessioni.
* La rimozione di un utente in Learning Manager non rimuove l’utente in alcuna applicazione esterna (sistemi di terze parti o altre applicazioni scritte dall’utente). Contatta i proprietari delle applicazioni esterne per rimuovere gli utenti da tali applicazioni.
* Se nelle impostazioni di configurazione di un connettore viene fatto riferimento a un utente rimosso, il connettore viene disattivato. Per riprenderlo, il connettore deve essere riconfigurato dall’amministratore.

Per rimuovere gli utenti, effettua le seguenti operazioni:

1. In qualità di Amministratore, seleziona **[!UICONTROL Utenti]** dal riquadro sinistro. La **[!UICONTROL Utenti interni]** pagina.
1. Elimina gli utenti da rimuovere. Per eliminarli, seleziona uno o più utenti utilizzando la casella di controllo. Apri il pannello **[!UICONTROL Azione]** a discesa e seleziona **[!UICONTROL Elimina utente.]**
1. Nel riquadro a sinistra, seleziona **[!UICONTROL Pulizia utente]**. La **[!UICONTROL Pulizia utente]** viene visualizzata una pagina con l’elenco degli utenti eliminati. Utilizza i pulsanti di scelta per selezionare l’utente da rimuovere. Puoi rimuovere un solo utente alla volta.

   ![](assets/purge-1.png)

   *Seleziona un utente da rimuovere*

1. Apri il pannello **[!UICONTROL Azioni]** menu a discesa e selezionare **[!UICONTROL Rimuovi utente]**.

   ![](assets/purge-2.png)

   *Seleziona l’opzione Rimuovi utente.*

1. Viene visualizzata una finestra di dialogo che richiede conferma. Una volta rimossi, tutti i dati utente e i record di apprendimento associati all’utente selezionato vengono eliminati definitivamente. Una volta rimossa, l’azione non può essere annullata. Per confermare, fare clic su **[!UICONTROL Rimuovi]**.

   ![](assets/purge-3.png)

   *Messaggio di conferma dopo l’eliminazione di un utente*

1. Dopo aver confermato e fatto clic su Rimuovi, la richiesta di rimozione viene accettata. Una volta completata l’azione, riceverai una notifica. Viene inoltre fornito un ID di richiesta di rimozione. È possibile fornire questo ID al CSM per tenere traccia della richiesta.

## Rimozione in blocco degli utenti

Puoi selezionare i primi 50 utenti ed eliminarli in una sola volta. Ciò consente agli amministratori di selezionare 50 utenti contemporaneamente ed eliminarli insieme. Questo consente agli amministratori di rimuovere gli utenti in blocco. È sempre consigliabile controllare gli utenti selezionati per la rimozione. Questo è importante per garantire che solo il set corretto di utenti venga eliminato.

![](assets/bulk-purge-users.png)

*Rimuovere gli utenti in blocco*

+++Informazioni sui risultati dell’azione Rimuovi utente

<table>
 <tbody>
  <tr>
   <th><strong>Rimozione tramite l’interfaccia utente di Learning Manager - Enterprise</strong></th>
   <th> </th>
  </tr>
  <tr>
   <td>Elimina l’utente selezionato dall’account enterprise richiedente.<br></td>
   <td>Sì</td>
  </tr>
  <tr>
   <td>Elimina tutti gli utenti da tutti gli account di prova il cui indirizzo e-mail, adobe_id corrisponde a quello degli utenti selezionati.</td>
   <td>Sì</td>
  </tr>
  <tr>
   <td>Elimina tutti gli utenti da tutti gli account di prova il cui indirizzo e-mail, adobe_id corrisponde a quello degli utenti selezionati, che sono gli autori dell’account di prova.</td>
   <td>No</td>
  </tr>
  <tr>
   <td>Elimina l’e-mail dell’utente da tutti gli altri campi dell’account Enterprise richiedente e da tutti gli account di prova.</td>
   <td>Sì</td>
  </tr>
  <tr>
   <td>Notifica all’iniziatore la conferma dell’eliminazione.</td>
   <td>Sì</td>
  </tr>
  <tr>
   <td><strong>Rimozione tramite l’interfaccia utente di Learning Manager - Non Enterprise</strong></td>
   <td> </td>
  </tr>
  <tr>
   <td>Elimina l’utente selezionato dall’account di prova richiedente.</td>
   <td>Sì</td>
  </tr>
  <tr>
   <td>Elimina tutti gli utenti da tutti gli account di prova il cui indirizzo e-mail, adobe_id corrisponde a quello degli utenti selezionati.</td>
   <td>Sì</td>
  </tr>
  <tr>
   <td>Elimina tutti gli utenti da tutti gli account di prova il cui indirizzo e-mail, adobe_id corrisponde a quello degli utenti selezionati, che sono gli autori dell’account di prova.</td>
   <td>No</td>
  </tr>
  <tr>
   <td>Elimina l’e-mail dell’utente da tutti gli altri campi dell’elenco Tutti gli account di prova.</td>
   <td>Sì</td>
  </tr>
  <tr>
   <td>Notifica all’iniziatore la conferma dell’eliminazione.</td>
   <td>Sì</td>
  </tr>
  <tr>
   <td><strong>Rimozione di altri utenti Enterprise (utenti privati che non sono utenti interni o esterni di Learning Manager)</strong></td>
   <td> </td>
  </tr>
  <tr>
   <td>Elimina l’utente selezionato da tutti gli altri campi dell’account Enterprise richiedente e da tutti gli account di prova.</td>
   <td>Sì</td>
  </tr>
  <tr>
   <td>Eliminazione degli utenti dagli account.</td>
   <td>No</td>
  </tr>
  <tr>
   <td>Notifica all’iniziatore la conferma dell’eliminazione. </td>
   <td>Sì</td>
  </tr>
  <tr>
   <td><strong>Rimuovi</strong> <strong>altri utenti - Non Enterprise (utenti privati che non sono utenti interni o esterni di Learning Manager)</strong></td>
   <td> </td>
  </tr>
  <tr>
   <td>Elimina l’utente selezionato da tutti gli altri campi dell’elenco Tutti gli account di prova.</td>
   <td>Sì</td>
  </tr>
  <tr>
   <td>Eliminazione degli utenti dagli account.</td>
   <td>No</td>
  </tr>
  <tr>
   <td>Notifica all’iniziatore la conferma dell’eliminazione.</td>
   <td>Sì</td>
  </tr>
  <tr>
   <td><strong>Rimozione tramite Adobe IMS - Enterprise</strong></td>
   <td> </td>
  </tr>
  <tr>
   <td>Informa l'amministratore Enterprise della richiesta.</td>
   <td>Sì</td>
  </tr>
  <tr>
   <td>Controlla i campi E-mail per l’invio delle notifiche.</td>
   <td>No</td>
  </tr>
  <tr>
   <td><strong>Rimozione tramite Adobe IMS - Non Enterprise</strong></td>
   <td> </td>
  </tr>
  <tr>
   <td>Elimina tutti gli utenti che dispongono dell’Adobe ID o dell’e-mail forniti da Tutti gli account di prova.</td>
   <td>Sì</td>
  </tr>
  <tr>
   <td>Elimina tutti gli utenti di un account di prova se l’E-mail/AdobeId fornito era del creatore dell’account.</td>
   <td>Sì</td>
  </tr>
  <tr>
   <td>Elimina l’ID e-mail selezionato da tutti gli altri campi di tutti gli account di prova.</td>
   <td>Sì</td>
  </tr>
 </tbody>
</table>

+++

Learning Manager è ora conforme al GDPR. Per ulteriori informazioni sulla conformità al GDPR, consulta  [Conformità di Learning Manager al GDPR](../../kb/prime-gdpr.md).

## Domande frequenti {#frequentlyaskedquestions}

+++Quanti giorni sono necessari per completare una richiesta di rimozione?

Il completamento di una richiesta di rimozione degli utenti richiede un massimo di 30 giorni.
+++

+++È possibile eseguire una rimozione in blocco in Learning Manager?

Sì, puoi eseguire una rimozione in blocco. Tuttavia, è possibile eseguire solo una rimozione in blocco di 50 utenti.
+++
