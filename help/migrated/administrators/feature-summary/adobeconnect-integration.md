---
jcr-language: en_us
title: Integrazione Adobe Connect
description: Gli autori possono creare corsi in classe virtuale con Adobe Connect durante la creazione del corso. Per abilitare Adobe Connect per il tuo account Learning Manager, devi contattare l’amministratore della tua organizzazione.
contentowner: jayakarr
exl-id: 13458f93-9ea7-4aab-8b33-3c4f4dd5886d
source-git-commit: a0c01c0d691429bd66a3a2ce4cfc175ad0703157
workflow-type: tm+mt
source-wordcount: '419'
ht-degree: 70%

---

# Integrazione Adobe Connect

Gli Amministratori di un’organizzazione possono configurare le impostazioni dell’account Learning Manager per consentire l’integrazione Adobe Connect.

## Configurazione di Adobe Connect {#configureadobeconnect}

1. Nell’accesso come Amministratore, fai clic su **[!UICONTROL Impostazioni]** nel riquadro a sinistra per visualizzare le informazioni di base sulla tua azienda. Fai clic su **[!UICONTROL Adobe Connect]** nel riquadro a sinistra.

   ![](assets/left-pane.png)

   *Seleziona Adobe Connect nel riquadro sinistro*

1. Fai clic sul collegamento **[!UICONTROL Configura ora]** nella sezione **[!UICONTROL Configurazione di Adobe Connect]**.

   <!--![](assets/configure-now-connect.png)-->

1. Fornisci il nome di dominio Adobe Connect della tua azienda e le credenziali di accesso.

   ![](assets/adobeconnect-config.png)

   *Aggiungi nome di dominio e credenziali*

   URL di Adobe Connect di esempio: mycompany.adobeconnect.com\
   È necessario fornire l’ID e-mail dell’Amministratore dell’account di connessione di Adobe.

   In Learning Manager sono supportati solo gli account Adobe Connect ospitati (hosted). Esempio: “.adobeconnect.com”.

1. Fai clic su **[!UICONTROL Integra].**

   Dopo l’autenticazione dell’ID e-mail, Learning Manager visualizza il messaggio quando Connect è integrato correttamente. Puoi iniziare a visualizzare i corsi in aula virtuale utilizzando Adobe Connect.

   L’Amministratore dell’account Adobe Connect deve accettare i termini e condizioni d’uso di Adobe Connect. In caso di mancata accettazione, l’autenticazione di accesso potrebbe non riuscire. Dopo averlo creato, accedi all’account Adobe Connect una volta. Al primo accesso, viene visualizzata una pagina di termini e condizioni.

   <!--![](assets/mail-confirmation.png)-->

## Aggiunta di informazioni alla sessione aula virtuale {#addvirtualclassroomsessioninformation}

Se l’Autore di un corso in aula virtuale non ha fornito le informazioni sulla sessione, l’Amministratore può includere dettagli sulla sessione.

Nell’accesso come Amministratore, fai clic sul nome del corso aula virtuale. Fai clic su **[!UICONTROL Istanze]** nel riquadro a sinistra e seleziona **[!UICONTROL Dettagli della sessione]**.  Fai clic sull’icona Modifica nell’angolo destro della pagina Dettagli sessione per aggiungere le informazioni sulla sessione.

![](assets/session-creation-admin.png)

*Aggiungi informazioni sessione aula virtuale*

Con l’integrazione di Adobe Learning Manager e Adobe Connect per la creazione di moduli o sessioni aula virtuale, il tuo account Connect dovrebbe supportare le sale riunioni con un numero di sale e utenti simultanei adeguato alle tue esigenze. Queste sale riunioni vengono utilizzate per ospitare i moduli aula virtuale di Learning Manager. Una nuova sala riunioni Connect viene creata in modo dinamico da Learning Manager per ciascun modulo o sessione aula virtuale all’interno di Learning Manager.

È necessario acquistare Adobe Connect e Adobe Learning Manager separatamente.

## Partecipazione degli allievi {#learnersattendance}

Se l’ospitante del corso in aula virtuale non partecipa alla sessione, la partecipazione non viene registrata automaticamente per gli Allievi che hanno partecipato alla sessione. In tali scenari, l’Amministratore può registrare manualmente la partecipazione.

Fai clic sul corso in aula virtuale, quindi su Partecipazione nel riquadro a sinistra della pagina seguente e registra la partecipazione.
