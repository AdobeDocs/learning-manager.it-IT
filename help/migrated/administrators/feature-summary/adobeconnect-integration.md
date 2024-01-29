---
jcr-language: en_us
title: Integrazione con Adobe Connect
description: Gli Autori possono creare corsi in aula virtuale con Adobe Connect durante la creazione del corso. Per abilitare Adobe Connect per il tuo account Learning Manager, devi contattare l’amministratore della tua organizzazione.
contentowner: jayakarr
source-git-commit: 0052ccb2f5a8f9617bca2c7bad91c0cd18338b66
workflow-type: tm+mt
source-wordcount: '419'
ht-degree: 0%

---



# Integrazione con Adobe Connect

Gli Amministratori di un’organizzazione possono configurare le impostazioni dell’account Learning Manager per abilitare l’integrazione Adobe Connect.

## Configurazione di Adobe Connect {#configureadobeconnect}

1. Nell’accesso come Amministratore, fai clic su **[!UICONTROL Impostazioni]** nel riquadro di sinistra per visualizzare le informazioni di base sulla società. Fai clic **[!UICONTROL Adobe Connect]** nel riquadro sinistro.

   ![](assets/left-pane.png)

   *Seleziona Adobe Connect nel riquadro a sinistra*

1. Fai clic **[!UICONTROL Configura ora]** collegamento **[!UICONTROL Configurazione di Adobe Connect]** sezione.

   <!--![](assets/configure-now-connect.png)-->

1. Fornisci il nome di dominio Adobe Connect della tua azienda e le credenziali di accesso.

   ![](assets/adobeconnect-config.png)

   *Aggiungi nome di dominio e credenziali*

   URL di Adobe Connect di esempio: mycompany.adobeconnect.com\
   È necessario fornire l’ID e-mail dell’Amministratore dell’account di connessione di Adobe.

   In Learning Manager sono supportati solo gli account di connessione ospitati di Adobe. Esempio: &quot;.adobeconnect.com&quot;.

1. Fai clic **[!UICONTROL Integrazione].**

   Dopo l’autenticazione dell’ID e-mail, Learning Manager visualizza il messaggio quando Connect è integrato correttamente. Puoi iniziare a visualizzare i corsi in aula virtuale utilizzando Adobe Connect automaticamente.

   L’amministratore dell’account Adobe Connect deve accettare i Termini e le Condizioni d’uso di Adobe Connect. In caso contrario, l’autenticazione di accesso potrebbe non riuscire. Dopo aver creato l’account Adobe Connect, accedi all’account una volta. Al primo accesso, viene visualizzata una pagina di termini e condizioni.

   <!--![](assets/mail-confirmation.png)-->

## Aggiungere informazioni sulla sessione aula virtuale {#addvirtualclassroomsessioninformation}

Se l’Autore di un corso in aula virtuale non ha fornito le informazioni sulla sessione, l’Amministratore può includere i dettagli della sessione.

Nell’accesso come Amministratore, fai clic sul nome del corso aula virtuale. Fai clic **[!UICONTROL Istanze]** nel riquadro a sinistra e fare clic su **[!UICONTROL Dettagli della sessione]**.  Fai clic sull’icona Modifica nell’angolo destro della pagina Dettagli sessione per aggiungere le informazioni sulla sessione.

![](assets/session-creation-admin.png)

*Aggiungere informazioni sulla sessione aula virtuale*

Con l’integrazione di Adobe Learning Manager e Adobe Connect per la creazione di moduli o sessioni aula virtuale, il tuo account Connect dovrebbe supportare le sale riunioni con un numero di sale e utenti simultanei adeguato alle tue esigenze. Queste sale riunioni vengono utilizzate per ospitare i moduli aula virtuale di Learning Manager. Una nuova sala riunioni Connect viene creata dinamicamente da Learning Manager per ogni modulo o sessione aula virtuale all’interno di Learning Manager.

È necessario acquistare Adobe Connect separatamente, a parte l’Adobe Learning Manager.

## Partecipazione degli Allievi {#learnersattendance}

Se l’ospitante del corso in aula virtuale non partecipa alla sessione, la partecipazione non viene registrata automaticamente per gli Allievi che hanno partecipato alla sessione. In tali scenari, l’Amministratore può registrare manualmente la partecipazione.

Fai clic sul corso in aula virtuale, quindi su Partecipazione nel riquadro a sinistra della pagina seguente e registra la partecipazione.
