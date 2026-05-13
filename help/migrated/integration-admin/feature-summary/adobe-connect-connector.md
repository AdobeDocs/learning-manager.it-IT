---
description: Scopri come integrare il connettore Adobe Connect con Adobe Learning Manager
jcr-language: en_us
title: Connettore Adobe Connect
contentowner: mmanuel
source-git-commit: 8a5212062c6b172b0e9d4f3faa2e66d26c5c2b56
workflow-type: tm+mt
source-wordcount: '655'
ht-degree: 2%

---


# Connettore Adobe Connect in Adobe Learning Manager

## Introduzione

Adobe Learning Manager si integra con Adobe Connect per aiutarti a fornire e gestire corsi di formazione in aula virtuale. Grazie a questa integrazione, è possibile pianificare le sessioni, utilizzare sale riunioni dinamiche o permanenti, acquisire la partecipazione, importare i risultati dei quiz e fornire agli Allievi le registrazioni delle sessioni.

## Configurazione di Adobe Connect

Per configurare Adobe Connect:

1. Accedi a Adobe Learning Manager come amministratore di integrazione.
2. Passa il mouse sul riquadro **Adobe Connect** e seleziona **Connetti**.

   ![](assets/adobe-connect-connector1.png)
   _Selezionare Connetti per configurare il connettore Adobe Connect_

3. Digita i seguenti dettagli:

   - **Nome connessione**
   - **URL Adobe Connect**
   - **E-mail amministratore connessione**
4. Digita l&#39;**ID di accesso amministratore di Connect** (obbligatorio se non viene utilizzato l&#39;accesso tramite e-mail per Adobe Connect).

   ![](assets/adobe-connect-connector2.png)
   _Digitare i dettagli richiesti per la configurazione di Adobe Connect_

5. Selezionare **Abilita autenticazione di Connect**.

   >[!NOTE]
   >
   >Sono supportati solo gli account Connect ospitati da Adobe. Il dominio deve terminare con .adobeconnect.com

6. Seleziona **Connetti**.

Dopo aver autenticato l’ID e-mail dell’amministratore:

- Adobe Learning Manager mostra un messaggio di conferma dell’integrazione di Connect.
- La richiesta viene inviata al team backend di Adobe Connect per l’approvazione. Questa operazione richiede solitamente uno o due giorni.

>[!IMPORTANT]
>
>L&#39;amministratore dell&#39;account Adobe Connect deve accettare Termini e condizioni quando accede per la prima volta. In caso contrario, l&#39;autenticazione di accesso potrebbe non riuscire.

## Aggiunta di informazioni alla sessione aula virtuale

Se un Autore non ha fornito i dettagli della sessione per un corso in aula virtuale, l’Amministratore può aggiungerli:

1. Accedi come Amministratore.
2. Seleziona il corso VC.
3. Seleziona **Istanze**, quindi seleziona **Dettagli sessione**.
4. Seleziona l&#39;icona **Modifica** per aggiungere o aggiornare le informazioni sulla sessione.

>[!NOTE]
>
>L’account Connect deve disporre di sale riunioni e capacità sufficienti per consentire agli utenti simultanei di eseguire classi virtuali. Ogni sessione aula virtuale di Adobe Learning Manager crea automaticamente una nuova sala riunioni Connect, a meno che non si utilizzi una sala permanente.

## Sale riunioni permanenti

Adobe Connect supporta le sale riunioni permanenti, che possono essere riutilizzate.

- È possibile creare una sessione aula virtuale utilizzando una sala permanente esistente in Connect.
- Potete anche scegliere di fare in modo che Adobe Learning Manager crei invece una stanza dinamica per ogni sessione.

Quando gli Allievi partecipano a una sessione utilizzando Adobe Connect, entrano nella room tramite Learning Manager utilizzando l’autenticazione sicura.

Al termine di una sessione, gli Allievi possono accedere alla registrazione della sessione e al codice di accesso nell’app Learning Manager.

## Importazione dei punteggi dei quiz da Adobe Connect

Adobe Learning Manager può importare i dati dei quiz dalle sessioni di Adobe Connect e combinarli con altri flussi di lavoro di reporting. Questo include punteggi dei quiz, risposte degli allievi e dati di completamento, ad esempio il funzionamento dei moduli a ritmo personalizzato.

### Flusso di lavoro per l’importazione dei quiz

#### Adobe Connect (host)

- L’ospitante di Connect crea un corso e carica contenuti che includono un quiz interattivo.
- L’ospitante imposta un corso Classe virtuale (VC) e collega il corso alla VC oppure utilizza l’opzione **Condividi corso** per condividerlo durante la sessione.

#### Adobe Learning Manager (autore)

- L’Autore crea un corso in Adobe Learning Manager con il tipo di modulo impostato su **Aula virtuale**.
- Dal menu a discesa **Sistema conferenze**, seleziona **Connect** come provider VC.
- Scegliere la **sala riunioni permanente** creata dall&#39;host in Connect.
- Assegna un Istruttore, salva e pubblica il corso.

#### Adobe Learning Manager (Allievo)

- L’Allievo si iscrive al corso e partecipa alla sessione Connect VC.
- L’host Connect consente all’Allievo di accedere alla sessione.

### Adobe Connect (ospitante e Allievo)

- L’ospitante condivide il quiz nella sessione.
- L’Allievo completa il quiz e esce dalla sessione.

### Adobe Learning Manager (Sincronizzazione e amministrazione)

- Al termine della sessione, Adobe Learning Manager sincronizza automaticamente i dati del quiz.
- Il flusso di lavoro di importazione del quiz inizia al termine della durata programmata.
- Per tenere traccia dell’avanzamento, l’Amministratore dell’integrazione può controllare lo **Stato di esecuzione** nel connettore Adobe Connect.
- Al termine dell&#39;importazione, lo stato viene aggiornato a **Completato**.

L’Amministratore può quindi esaminare i risultati importati:

- **Frequenza e punteggi:** Visualizzare i punteggi finali dei quiz e la partecipazione.
- **Punteggio quiz L2:**
   - **Per utente:** mostra i singoli punteggi in punti e percentuali.
   - **Per domanda:** mostra i risultati del quiz in un grafico.
