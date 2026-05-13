---
description: Connettore FTP personalizzato in Adobe Learning Manager
jcr-language: en_us
title: Connettore FTP personalizzato
contentowner: mmanuel
source-git-commit: 8a5212062c6b172b0e9d4f3faa2e66d26c5c2b56
workflow-type: tm+mt
source-wordcount: '526'
ht-degree: 0%

---


# Connettore FTP personalizzato in Adobe Learning Manager

## Introduzione

Il connettore FTP personalizzato in Adobe Learning Manager consente lo scambio sicuro e automatizzato di dati tra Adobe Learning Manager e il server FTP (SFTP) dell&#39;organizzazione. Grazie a questa integrazione, gli amministratori possono importare i dati degli utenti da sistemi esterni ed esportare le trascrizioni degli allievi o i dati sulle abilità in base a una pianificazione. Questa configurazione semplifica la sincronizzazione dei dati, riduce il lavoro manuale e supporta l’integrazione con sistemi HR o di reporting di terze parti. La configurazione richiede il coordinamento con il team IT e l&#39;assistenza del Customer Success Manager (CSM) di Adobe.

>[!NOTE]
>
>Per configurare una connessione FTP personalizzata, contatta il Customer Success Manager (CSM). Il processo di configurazione può richiedere l&#39;assistenza del team IT per la creazione di elenchi di indirizzi IP consentiti, l&#39;apertura delle porte necessarie e la creazione di cartelle con le autorizzazioni di accesso necessarie.

## Funzionalità supportate

Il connettore FTP personalizzato supporta le seguenti azioni:

### Importazione di dati

Il processo di importazione degli utenti recupera automaticamente i dati dei dipendenti dal server FTP e li importa in Adobe Learning Manager. Questa funzione è utile quando si integrano più sistemi che generano file CSV contenenti dati utente.

- Inserisci i file CSV nella cartella **import** designata sul server FTP.
- Adobe Learning Manager rileva i file, li unisce se necessario e importa i dati utente in base alla pianificazione definita.

Consulta la sezione [Pianificazione](/help/migrated/integration-admin/feature-summary/custom-ftp-connector.md#scheduling-reports) per scoprire come automatizzare questo processo.

### Mappatura degli attributi

In qualità di amministratore di integrazione, puoi mappare le colonne nel file CSV agli attributi raggruppabili in Adobe Learning Manager.

- La mappatura è una configurazione singola.
- La stessa mappatura viene utilizzata per le importazioni successive.
- È possibile riconfigurare i mapping se la struttura dei dati cambia.

### Esportazione dati

Adobe Learning Manager consente di esportare:

- Abilità utente
- Trascrizioni Allievi

Questi file di report vengono inseriti nella cartella di esportazione sull’FTP e possono essere utilizzati da sistemi di terze parti per la creazione di report, l’analisi o altri processi a valle.

### Pianificazione dei report

Gli amministratori dell’integrazione possono pianificare entrambi gli aspetti:

- Importazioni utente
- Esportazioni trascrizioni Allievo

La pianificazione garantisce che l&#39;ambiente Adobe Learning Manager sia sempre aggiornato con i sistemi di origine. È possibile configurare sincronizzazioni giornaliere o intervalli personalizzati in base alle esigenze.

## Configurazione del connettore FTP personalizzato

Per configurare il connettore FTP personalizzato:

1. Accedi a Adobe Learning Manager come amministratore di integrazione.
2. Passa il mouse sul riquadro **FTP personalizzato** e seleziona **Connetti**.

   ![](assets/custom-ftp-connector1.png)
   _Selezionare Connetti per configurare il connettore FTP personalizzato_

### Scegli metodo di autenticazione

Puoi configurare la connessione FTP personalizzata utilizzando uno dei due tipi di autenticazione seguenti:

#### Account di autenticazione di base

1. Digita i seguenti dettagli:

   - **Il tuo dominio FTP**
   - **Nome utente FTP**
   - **Password FTP**

   ![](assets/custom-ftp-connector2.png)
   _Digitare il dominio FTP, il nome utente e la password per la configurazione._

2. Seleziona **Connetti**.

#### Autenticazione certificato

Se il server FTP supporta l&#39;autenticazione con chiave SSH:

1. Selezionare **Genera chiave SSH**.

   ![](assets/custom-ftp-connector3.png)
   _Selezionare Genera chiave SSH per scaricare la chiave_

2. La chiave pubblica verrà scaricata nel computer.
3. Aggiungere la chiave all&#39;elenco delle chiavi autorizzate del server FTP.
4. Digita i seguenti dettagli:

   - **Il tuo dominio FTP**
   - **Nome utente FTP**
5. Seleziona **Connetti**.

>[!NOTE]
>
>Per la configurazione FTP personalizzata sono supportati solo i server **SFTP**.

## Configurazione dopo la connessione

Una volta stabilita la connessione:

- Adobe Learning Manager crea automaticamente cartelle per **import** e **export** sul server FTP.
- Puoi iniziare a importare ed esportare i dati in base alla pianificazione e alle impostazioni di mappatura.
