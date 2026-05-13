---
description: Scopri come integrare il connettore Adobe Commerce
jcr-language: en_us
title: Connettore Adobe Commerce
contentowner: mmanuel
source-git-commit: 8a5212062c6b172b0e9d4f3faa2e66d26c5c2b56
workflow-type: tm+mt
source-wordcount: '696'
ht-degree: 4%

---


# Connettore Adobe Commerce in Adobe Learning Manager

## Connettore Adobe Commerce

>[!NOTE]
>
>Questa funzione è disponibile solo se Adobe Learning Manager viene venduto come **componente aggiuntivo** a Adobe Experience Manager. Il connettore può essere abilitato anche per gli account **versione di prova**.

Adobe Learning Manager si integra con Adobe Commerce, una soluzione di e-commerce estensibile e scalabile che consente di offrire esperienze di e-commerce multicanale per i clienti B2B e B2C. Utilizza il connettore Adobe Commerce per collegare Adobe Learning Manager ad Adobe Commerce e abilitare le funzionalità di formazione a pagamento e e-commerce all&#39;interno della piattaforma di apprendimento.

Quando il connettore è abilitato, Learning Manager invia i dati di formazione ad Adobe Commerce in modo che gli Allievi possano acquistare corsi, percorsi di apprendimento o certificazioni. Il connettore raccoglie inoltre informazioni sull’acquisto per convalidare le transazioni e concedere agli Allievi l’accesso ai propri corsi di formazione.

## Prerequisiti

Prima di configurare il connettore Adobe Commerce, verifica quanto segue:

- Abilita [RabbitMQ](https://experienceleague.adobe.com/it/docs/commerce-cloud-service/start/overview) o qualsiasi altro broker di messaggi.
- Abilita [processi CRON](https://experienceleague.adobe.com/it/docs/commerce-cloud-service/start/overview#cron_consumers_runner).

Per attivarle, modifica i seguenti file:

- .magento.app.yaml
- .magento/services.yaml
- .magento.env.yaml

Altri requisiti di configurazione:

- Sostituisci il limite di opzioni utilizzando un modulo personalizzato. Questo passaggio è facoltativo ma consigliato per set di dati di grandi dimensioni.
- Abilita tutte le **API asincrone**. I dataset di formazione di grandi dimensioni vengono esportati in modo asincrono. Quando Learning Manager chiama le API Adobe Commerce, le richieste vengono accodate ed elaborate da un consumatore che crea prodotti sul lato commerciale. L’elaborazione asincrona deve essere abilitata perché non è disponibile per impostazione predefinita in Adobe Commerce.
- Aggiungi un **collegamento restituito** a Learning Manager nella pagina di completamento del pagamento in Adobe Commerce.
   - Utilizza questo [URL restituito](https://learningmanager.adobe.com/app/learner#/postPayment):
- Modifica **indicizzazione** da **Al salvataggio** a **Pianificato**. Per ulteriori informazioni, vedere la [Knowledge Base](https://experienceleague.adobe.com/it/support?support-tab=home#home).
- Applicare le **patch** richieste. Per istruzioni, consultare la [documentazione sull&#39;applicazione delle patch](https://experienceleague.adobe.com/it/docs/commerce-cloud-service/start/overview).
- Configura **Fastly** per Adobe Commerce sull&#39;infrastruttura cloud (gestione temporanea e produzione). Per ulteriori informazioni, vedere [Configurazione di Fastly](https://devdocs.magento.com/cloud/cdn/configure-fastly.html).

## Configurazione del connettore

Per configurare il connettore Adobe Commerce:

1. Accedi a Adobe Learning Manager come amministratore di integrazione.
2. Passa il mouse sul riquadro del connettore **Adobe Commerce** e seleziona **Connetti**.

   ![](assets/adobe-commerce-connector1.png)
   _Selezionare Connetti per configurare il connettore Adobe Commerce_

3. Digita i seguenti dettagli:

   - Nome connessione
   - Token di accesso
   - URL ADOBE COMMERCE
   - Codice punto vendita
4. Selezionate il tipo di interfaccia tra i seguenti:

   - Learning Manager nativo
   - Personalizzazione tramite AEM Sites

   ![](assets/adobe-commerce-connector2.png)
   _Digitare i dettagli richiesti per la configurazione di Adobe Commerce_

5. Seleziona **Connetti**.

## Imposta i prezzi per il corso di formazione

Una volta attivata la connessione:

- Gli Autori possono impostare i prezzi per corsi, percorsi di apprendimento o certificazioni.
- Dopo la pubblicazione, gli Allievi possono acquistare i corsi di formazione tramite Adobe Learning Manager o un sito AEM personalizzato.

## Flusso di acquisto

### Adobe Learning Manager nativo

- Gli Allievi accedono a Adobe Learning Manager per acquistare un corso, un percorso di apprendimento o un certificato.
- Quando gli Allievi fanno clic su Acquista ora, vengono reindirizzati ad Adobe Commerce per completare il pagamento.
- Dopo il pagamento, agli Allievi viene richiesto di tornare a Adobe Learning Manager per avviare il corso di formazione.
- Per completare l’acquisto, gli Allievi devono accedere separatamente ad Adobe Commerce.
- Gli Allievi ricevono e-mail di conferma dell’acquisto da Learning Manager e Adobe Commerce. Le e-mail Adobe Commerce possono essere attivate o disattivate in base alle esigenze.

### AEM Sites personalizzato

Quando si utilizzano siti AEM personalizzati:

- Gli Allievi possono consultare e acquistare corsi tramite il sito AEM.
- Il sito AEM utilizza metadati sincronizzati da Adobe Learning Manager per la ricerca e la visualizzazione.
- Sia gli utenti connessi che gli utenti guest possono sfogliare. Tuttavia, solo gli utenti che hanno effettuato l’accesso possono effettuare l’acquisto.
- Dopo l’accesso, gli Allievi possono aggiungere corsi al carrello, visualizzare in anteprima i dettagli e completare l’acquisto.

## Esportazione dei corsi in Adobe Commerce

### Pianifica esportazione

Per pianificare l’esportazione:

1. Selezionare **Esporta metadati del corso di formazione**, quindi selezionare **Configura pianificazione**.
2. Seleziona **Abilita esportazione dei metadati di formazione utilizzando questa connessione**.
3. Seleziona **Abilita pianificazione** e imposta **data di inizio**, **ora** e **intervallo**.

   ![](assets/adobe-commerce-connector3.png)
   _Abilita esportazione pianificata_

4. Seleziona **Salva**.

### Esportazione su richiesta

Dopo che gli Autori hanno impostato i prezzi per il corso di formazione, l’Amministratore di integrazione deve esportare i dati del corso di formazione:

1. Selezionare **Esporta metadati corso**, quindi selezionare **Su richiesta**.
2. Seleziona l’intervallo di date.
3. Selezionare **Esegui** per esportare.

   ![](assets/adobe-commerce-connector4.png)
   _Crea esportazione su richiesta_

4. Al termine dell’operazione, i corsi e i percorsi di apprendimento con prezzo verranno spostati in Adobe Commerce per l’acquisto.
