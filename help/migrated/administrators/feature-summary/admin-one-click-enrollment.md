---
description: 'L’iscrizione con un solo clic consente agli Allievi di fare clic su un collegamento diretto a un modulo condiviso dagli Amministratori e di accedere immediatamente al contenuto, senza dover seguire più passaggi: fai clic su Iscriviti e quindi avvia il corso. Consente di risparmiare tempo e migliora l’accesso ai corsi.'
jcr-language: en_us
title: Configurazione dell’iscrizione con un solo clic in Adobe Learning Manager
contentowner: mmanuel
source-git-commit: 87971737d1d9838d8b29035b5b9bf718742da1eb
workflow-type: tm+mt
source-wordcount: '317'
ht-degree: 0%

---


# Configurazione dell’iscrizione con un solo clic in Adobe Learning Manager

## Funzionamento dell’iscrizione con un clic

L&#39;iscrizione con un solo clic si basa su due funzionalità Adobe Learning Manager (ALM) che funzionano insieme:
I collegamenti diretti forniscono un URL diretto a un corso o un oggetto di apprendimento specifico all&#39;interno di ALM. Puoi incorporare questi collegamenti (che sono URL diretti ai moduli) nelle e-mail, nei portali Intranet o nelle applicazioni di terze parti. Se un Allievo non ha ancora effettuato l’accesso quando fa clic sul collegamento, ALM chiede di autenticarsi e quindi lo reindirizza direttamente al corso.

In genere è utile quando gli Allievi sono nel bel mezzo del lavoro e utilizzano Slack o Team o quando devono seguire una veloce formazione di aggiornamento di due minuti prima di viaggiare o partecipare a una riunione o a una chiamata di vendita. Possono accedere immediatamente al contenuto e ricevere una formazione.
I servizi relativi all’iscrizione iscrivono automaticamente un Allievo a un corso prima che il collegamento profondo avvii il lettore del corso. In questo modo viene rimosso il passaggio di iscrizione manuale che altrimenti interromperebbe l’esperienza dell’Allievo.

Quando un Allievo seleziona un collegamento con un clic per l’iscrizione, ALM li iscrive tramite API in background, quindi li reindirizza al corso utilizzando il collegamento profondo. Il lettore del corso si apre immediatamente.

>[!NOTE]
>
>L’iscrizione si verifica solo a livello di corso e non a oggetti di apprendimento di livello superiore (percorsi di apprendimento o certificazioni).

## Generare un collegamento profondo per un modulo

1. Accedi a Adobe Learning Manager come amministratore.
2. Seleziona **Corsi** nel riquadro di navigazione a sinistra.
   ![](assets/one-click-enroll1.png)
3. Seleziona un corso
4. Seleziona **Istanze**.
   ![](assets/one-click-enroll2.png)
5. Selezionare la sezione **Modulo** dell&#39;istanza di cui si desidera copiare i collegamenti diretti dei moduli. I dettagli del modulo vengono visualizzati nella sezione espansa nella parte inferiore dell’istanza.
   ![](assets/one-click-enroll3.png)
6. Accedi al modulo di cui desideri copiare il collegamento.
   ![](assets/one-click-enroll4.png)
7. Seleziona **Copia collegamento**. Il collegamento profondo è ora copiato. Questo collegamento profondo consente di aprire il modulo specifico di un corso.

Ora puoi utilizzare questo collegamento profondo per inviarlo a un Allievo.
