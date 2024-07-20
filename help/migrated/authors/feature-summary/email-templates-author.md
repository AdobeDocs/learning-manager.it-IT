---
description: Leggi questo articolo per scoprire come configurare i modelli e-mail per gli eventi correlati a tutti gli oggetti di apprendimento.
jcr-language: en_us
title: Modelli e-mail
exl-id: 3b17f889-52be-4073-ab91-7c76dd79f1d2
source-git-commit: 6862dc1958a34a369f0e0e7218f28151a47beb3b
workflow-type: tm+mt
source-wordcount: '475'
ht-degree: 72%

---

# Modelli e-mail

Leggi questo articolo per scoprire come configurare i modelli e-mail per gli eventi correlati a tutti gli oggetti di apprendimento.

L’applicazione Learning Manager invia notifiche via e-mail a più ruoli di utenti in base agli eventi.

In qualità di Autore puoi personalizzare i modelli e-mail aggiungendo o modificando il contenuto e inviando notifiche agli utenti per vari eventi attivati da Allievi, Manager e Autori. Ad esempio, puoi inviare un’e-mail personalizzata ogni volta che un Allievo si iscrive al corso. Al momento dell’iscrizione, l’Allievo riceve automaticamente l’e-mail specifica del corso.

Puoi anche scegliere di non inviare notifiche e-mail per determinati eventi disattivando l’opzione Modello e-mail.

## Configurare le notifiche e-mail {#settingemailnotifications}

1. Dall’app Autore, seleziona l’oggetto di apprendimento per il quale vuoi configurare il modello e-mail. Ad esempio, Corsi.

1. Nella pagina Oggetto di apprendimento, fai clic sul corso, la certificazione o il programma di apprendimento per cui desideri configurare le impostazioni e-mail.

1. Dalla pagina dei dettagli dell’oggetto di apprendimento, seleziona **Modelli e-mail** > **Tutti i modelli**. I modelli e-mail sono disponibili per **Istanza predefinita** e **Corso corrente**. Puoi passare da una all’altra utilizzando il menu a discesa nell’angolo in alto a destra.

   Puoi vedere l’elenco dei modelli disponibili per l’oggetto di apprendimento selezionato.

   ![](assets/email-templates-forlearningprograms.png)
   *Elenco dei modelli*

1. Fai clic sul nome dell’evento per visualizzare il modello in modalità anteprima.

   ![](assets/preview-the-emailtemplateforyourlearningobject.png)

   *Visualizza anteprima modello*

   Puoi personalizzare ogni modello facendo clic sul testo nel corpo del modello. Puoi inserire variabili nel testo facendo clic sulle icone appropriate, come illustrato nell’immagine. Passa il mouse su ogni icona per visualizzare i nomi.

   ![](assets/insert-variable.png)
   *Inserire una variabile*

   Sono disponibili le seguenti variabili:

   * NomeProgrammaFormativo
   * ScadenzaCompletamentoProgrammaFormativo
   * NomeAllievo
   * E-mailAllievo
   * NomeCorso
   * DescrizioneCorso
   * ScadenzaCompletamentoCorso
   * DettagliAbilitàCorso
   * DistintivoCorso

   Puoi ripristinare il contenuto predefinito del messaggio facendo clic sul collegamento Torna all’originale sopra il modello.

   Come vedi nella parte superiore del modello, puoi personalizzare il modello per più ruoli (Manager, Allievo ecc.) a seconda del tipo di notifica e-mail.

1. Fai clic su Salva in fondo alla pagina dei modelli.
1. Nella pagina Modelli e-mail, fai clic sul pulsante circolare Sì/No per inviare o disabilitare la notifica.

![](assets/email-notification-e1437624109719.png)
*Attivare o disattivare la notifica e-mail*

Se il cerchio nel pulsante di notifica relativo a ciascun nome di evento si trova accanto a Sì (sfondo blu), la notifica è attivata. Se il cerchio è grigio e si trova accanto a No, la notifica è disattivata.

Ogni volta che configuri un modello e-mail a livello di corso, esso acquista la precedenza sulle impostazioni a livello di Amministratore per quel determinato corso.

## Impostazioni dei modelli e-mail

L’autore può impostare quanto segue nelle impostazioni del modello e-mail:

* **Banner e-mail**: consente di modificare il banner e-mail.

* **Firma e-mail**: consente di aggiungere o modificare la firma e-mail.
