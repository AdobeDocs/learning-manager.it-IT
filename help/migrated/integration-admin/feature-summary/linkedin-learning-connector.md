---
description: Scopri come integrare il connettore LinkedIn Learning con Adobe Learning Manager
jcr-language: en_us
title: Connettore LinkedIn Learning
contentowner: mmanuel
source-git-commit: 8a5212062c6b172b0e9d4f3faa2e66d26c5c2b56
workflow-type: tm+mt
source-wordcount: '756'
ht-degree: 1%

---


# Connettore linkedIn Learning in Adobe Learning Manager

## Introduzione

Il connettore LinkedIn Learning consente di integrare perfettamente i contenuti di LinkedIn Learning con Adobe Learning Manager. Con questo connettore, le organizzazioni possono portare automaticamente i corsi di LinkedIn Learning in Adobe Learning Manager in modo che gli Allievi possano trovare, iscriversi e completare i corsi LinkedIn direttamente all’interno della piattaforma.

Durante la configurazione, l’avanzamento degli Allievi nei contenuti di LinkedIn Learning viene monitorato in Adobe Learning Manager, consentendo agli Amministratori di monitorare i completamenti e il tempo impiegato. Puoi pianificare la sincronizzazione automatica dei contenuti, eseguire le importazioni su richiesta e filtrare i corsi introdotti nel sistema in base alla lingua, alla libreria o ai tag personalizzati.

>[!NOTE]
>
>Quando importi i corsi da LinkedIn Learning, Adobe Learning Manager genera ID LO (Learning Object) univoci per ogni corso. Il tempo di apprendimento impiegato per i contenuti di LinkedIn Learning viene segnalato dalla piattaforma LinkedIn a Adobe Learning Manager. Se la piattaforma LinkedIn non invia questi dati, Adobe Learning Manager non può registrarli e il tempo impiegato verrà visualizzato come zero.

## Configurazione delle impostazioni del portale di LinkedIn Learning

Per configurare le impostazioni del portale di LinkedIn Learning:

1. Accedi a **LinkedIn Learning LMS** come amministratore.
2. Seleziona **Amministratore** dal pannello di navigazione superiore.
3. Fare clic sulla scheda **Impostazioni**.
4. Dalla barra di navigazione a sinistra, seleziona **Integrazione riproduzione**, quindi seleziona la scheda **Integrazione**.
5. Espandere **Impostazioni di avvio contenuto LMS**.
6. Aggiungi i seguenti nomi host:

   - learningmanager.adobe.com
   - learningmanagerlrs.adobe.com
   - cpcontents.adobe.com
7. Seleziona **Abilita integrazione AICC**.

   ![](assets/linkedin-connector1.png)
   _Selezionare Abilita integrazione AICC per configurare il connettore LinkedIn Learning_

## Connetti LinkedIn Learning in Adobe Learning Manager

Per configurare il connettore LinkedIn Learning:

1. Accedi a Adobe Learning Manager come amministratore di integrazione.
2. Passa il mouse sul riquadro **LinkedIn Learning** e seleziona **Connetti**.

   ![](assets/linkedin-connector2.png)
   _Selezionare Connetti per configurare il connettore LinkedIn Learning_

3. Nella pagina di impostazione della connessione:
   - Digitare un **nome connessione**.
   - Digitare **Chiave applicazione** e **Chiave segreta**.

   ![](assets/linkedin-connector3.png)
   _Digitare il nome della connessione, la chiave dell&#39;applicazione e la chiave segreta per configurare il connettore LinkedIn Learning_

   >[!NOTE]
   >
   >L’amministratore aziendale può generare queste chiavi creando un’applicazione nel portale di amministrazione di LinkedIn Learning.

4. Seleziona **Salva** per aggiungere la connessione.

Per modificare una connessione esistente, seleziona **Gestione connessioni** nel riquadro **LinkedIn Learning**.

>[!IMPORTANT]
>
>Per poter configurare il connettore, è necessario abilitare la funzionalità **Migrazione** per l&#39;account.


## Gestire la connessione e la sincronizzazione

Per gestire il connettore LinkedIn Learning:

1. Selezionare **Gestione connessioni** e selezionare la connessione.
2. Nel riquadro a sinistra, seleziona **Configura**.
3. Selezionare **Abilita connessione**.

   ![](assets/linkedin-connector4.png)
   _Selezionare Abilita connessione nella pagina Configura connettore LinkedIn Learning_

4. Selezionare **Modifica** per aggiornare le credenziali. Usa **Ripristina** per annullare le modifiche.
5. Per automatizzare la sincronizzazione, seleziona **Abilita pianificazione**.
6. Imposta la data, l’ora e la frequenza di inizio (ad esempio, ogni 3 giorni).
7. Seleziona **Salva**.

### Sincronizzazione su richiesta

Per eseguire la sincronizzazione su richiesta:

1. Seleziona **Esecuzione su richiesta** nel riquadro a sinistra.
2. Digitare una **Data di inizio**.
3. Selezionate una delle opzioni seguenti per **Abilitare** o **Disabilitare l&#39;accesso** a Adobe Learning Manager durante l&#39;esecuzione:
   - **Abilita accesso a Adobe Learning Manager durante l&#39;esecuzione**: nessun periodo di inattività per gli utenti.
   - **Disabilita accesso a Adobe Learning Manager durante l&#39;esecuzione**: l&#39;applicazione non è disponibile durante la sincronizzazione.

   ![](assets/linkedin-connector5.png)
   _Selezionare Esecuzione su richiesta per eseguire l&#39;importazione_

4. Seleziona **Esegui** per importare i feed degli utenti e i dati da LinkedIn Learning a partire da quella data in avanti.

Per monitorare tutte le esecuzioni della sincronizzazione:

Selezionare **Stato esecuzione** nel riquadro sinistro per visualizzare la cronologia di tutte le sincronizzazioni, la loro durata, il tipo (pianificato o su richiesta) e lo stato corrente (in corso, completato).

>[!NOTE]
>
>Se elimini e ricrei una connessione, le esecuzioni precedenti vengono mantenute e visualizzate in **Stato esecuzione**. Puoi eseguire nuovamente solo la sincronizzazione più recente.

## Filtrare i contenuti di LinkedIn Learning

Durante la configurazione del connettore, puoi filtrare i corsi di LinkedIn Learning da importare.

Per impostare il filtro:

1. Seleziona **Filtro** nel riquadro sinistro.
2. Seleziona l&#39;opzione richiesta in **Filtra i corsi di formazione utilizzando**.
   - **Nessun filtro** - Importa tutti i corsi.
   - **Lingua** - Filtra i corsi in base a lingue specifiche.
   - **Libreria** - Filtra i corsi in base alle librerie di LinkedIn Learning.
3. Se si applica un filtro in base a **Lingua**, selezionare le lingue desiderate. Ad esempio, **inglese** e **spagnolo**.
4. In **Importa corsi di formazione in**, seleziona il percorso di importazione dei corsi.
5. Scegli come organizzare i corsi importati.
6. Seleziona una delle opzioni seguenti per l&#39;opzione **Segrega corsi di formazione basati su**:

   - **Lingua** - Raggruppa per lingua.
   - **Libreria** - Raggruppa per libreria.
7. In **Importa tag**, seleziona i tipi di tag da applicare ai corsi importati.

   - **Lingua**
   - **Libreria**
   - **Soggetto**
   - **Argomento**
   - **Tag personalizzato**
8. Nel campo **Tag personalizzato**, digitare un tag personalizzato che si desidera assegnare. Separa più tag con virgole.

   ![](assets/linkedin-connector6.png)
   _Selezionare le opzioni di filtro per importare i dati dal connettore LinkedIn Learning_

9. Se desideri che gli Allievi possano annullare l’iscrizione a questi corsi, seleziona **Gli utenti possono annullare l’iscrizione**.
10. Seleziona **Salva** per applicare il filtro e importare le impostazioni.
