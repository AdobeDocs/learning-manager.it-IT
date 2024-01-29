---
description: Leggi questo articolo per scoprire come configurare i modelli e-mail per gli eventi correlati a tutti gli oggetti di apprendimento.
jcr-language: en_us
title: Modelli e-mail
source-git-commit: fda58bc18bee6d21ee904a442884e4759587d053
workflow-type: tm+mt
source-wordcount: '415'
ht-degree: 0%

---



# Modelli e-mail

Leggi questo articolo per scoprire come configurare i modelli e-mail per gli eventi correlati a tutti gli oggetti di apprendimento.

L’applicazione Learning Manager invia notifiche e-mail a più ruoli di utenti in base agli eventi.

In qualità di Autore, puoi personalizzare i modelli e-mail aggiungendo o modificando contenuti e inviando notifiche agli utenti per vari eventi attivati da Allievi, Manager e attività di Autore. Ad esempio, puoi inviare un’e-mail personalizzata ogni volta che un Allievo si iscrive a un corso. Al momento dell’iscrizione, l’Allievo riceverà automaticamente l’e-mail relativa al corso.

Puoi anche scegliere di non inviare notifiche e-mail per determinati eventi disabilitando l&#39;opzione del modello e-mail.

## Impostazione delle notifiche e-mail {#settingemailnotifications}

1. Dall’app Autore, fai clic sull’oggetto di apprendimento per il quale desideri configurare il modello e-mail. Ad esempio, Corsi.
1. Dalla pagina Oggetto di apprendimento, fai clic sul corso, sulla certificazione o sul programma di apprendimento che desideri configurare le impostazioni e-mail.
1. Nella pagina dei dettagli dell’oggetto di apprendimento, fai clic su Modelli e-mail.

   È possibile visualizzare l’elenco dei modelli disponibili per l’oggetto di apprendimento scelto.

   ![](assets/email-templates-forlearningprograms.png)
   *Elenco dei modelli*

1. Fate clic sul nome dell’evento per visualizzare il modello in modalità di anteprima.

   ![](assets/preview-the-emailtemplateforyourlearningobject.png)

   *Visualizza anteprima modello*

   È possibile personalizzare ogni modello facendo clic sul testo nel corpo del modello. È possibile inserire variabili nel testo facendo clic sulle icone appropriate come mostrato nell&#39;istantanea. Passate il mouse sopra ogni icona per visualizzarne i nomi.

   ![](assets/insert-variable.png)
   *Inserire una variabile*

   Sono disponibili le seguenti variabili:

   * LPName
   * LPCompletionDeadline
   * LearnerName
   * LearnerEmail
   * CourseName
   * DescrizioneCorso
   * ScadenzaCompletamentoCorso
   * DettagliAbilitàCorso
   * BadgeCorso

   È possibile ripristinare il contenuto predefinito del messaggio facendo clic sul collegamento Ripristina originale sopra il modello.

   Come vedi nella parte superiore del modello, puoi personalizzare il modello per più ruoli (Manager, Allievo ecc.) a seconda del tipo di notifica e-mail.

1. Fai clic su Salva nella parte inferiore della pagina dei modelli.
1. Dalla pagina Modelli e-mail, fai clic sul pulsante di attivazione circolare Sì/No per inviare o disattivare la notifica.

![](assets/email-notification-e1437624109719.png)
*Attivare o disattivare la notifica e-mail*

Se il cerchio del pulsante di notifica accanto al nome di ogni evento è adiacente a Sì (con sfondo blu), la notifica è attivata. Se è in tonalità grigia e il cerchio è adiacente a No, la notifica è disattivata.

Ogni volta che configuri un modello e-mail a livello di corso, ha la precedenza sulle impostazioni a livello di amministratore per quel determinato corso.
