---
description: Connettore Box in Adobe Learning Manager
jcr-language: en_us
title: Connettore Box
contentowner: mmanuel
source-git-commit: 8a5212062c6b172b0e9d4f3faa2e66d26c5c2b56
workflow-type: tm+mt
source-wordcount: '894'
ht-degree: 1%

---


# Connettore Box in Adobe Learning Manager

## Introduzione

Il **connettore Box** in Adobe Learning Manager consente l’integrazione diretta con i sistemi esterni automatizzando l’importazione e l’esportazione di dati relativi agli utenti e all’apprendimento tramite file CSV. I sistemi esterni possono inserire file CSV in cartelle designate nell’account Box gestito da Adobe Learning Manager, dove vengono elaborati automaticamente in base a una pianificazione definita.

Con questo connettore, gli amministratori possono:

- Importa utenti interni da file CSV.
- Esporta in sistemi esterni i dati sulle abilità degli utenti e le trascrizioni degli Allievi.
- Importa istruzioni di attività xAPI da sistemi di terze parti supportati.

Il connettore supporta la mappatura degli attributi, la sincronizzazione pianificata e l’esecuzione su richiesta, aiutando le organizzazioni a mantenere aggiornati i dati degli utenti e dell’apprendimento su tutte le piattaforme.

## Configurazione del connettore Box

Per configurare il connettore Box in Adobe Learning Manager:

1. Accedi a Adobe Learning Manager come amministratore di integrazione.
2. Passa il mouse sul riquadro **Box**.
3. Seleziona **Connetti**.

   ![](assets/box-connector1.png)
   _Selezionare Connetti per configurare il connettore BoxSelezionare Connetti per configurare il connettore Box_

4. Digita l’indirizzo e-mail della persona che gestirà l’account Adobe Learning Manager Box per la tua organizzazione.
5. Seleziona **Connetti**.



### Attivare l’account

1. Adobe Learning Manager invia un collegamento per la reimpostazione della password all’ID e-mail fornito.
2. L’utente deve reimpostare la password prima di accedere all’account Box per la prima volta.

>[!NOTE]
>
>È possibile configurare un solo account Box per account Adobe Learning Manager.

Nella pagina **Panoramica**, selezionare una delle azioni seguenti:

- **Importa uso interno**
- **Importa report attività xAPI**
- **Esporta abilità utente**
- **Esporta trascrizione Allievo**
- **Esporta report di attività xAPI**

Una volta connesso, il connettore Box sarà pronto per sincronizzare i dati tra Adobe Learning Manager e i sistemi esterni.

## Importazione di utenti interni

La funzionalità di importazione degli utenti consente la sincronizzazione automatica dei dati dei dipendenti dai sistemi HR e da altre fonti esterne in Adobe Learning Manager.

### Mapping attributi

La mappatura degli attributi crea la connessione tra i dati esterni e la struttura di dati supportata di Adobe Learning Manager, garantendo che i dati vengano inseriti nei campi corretti. Questo passaggio è obbligatorio.

Per mappare gli attributi:

1. Seleziona **Utenti interni** nella pagina del connettore Box.
2. Selezionare **Mappatura colonne**.
3. Nella pagina **Mappa attributi**:
   - Il lato sinistro mostra i campi obbligatori in Adobe Learning Manager.
   - Sul lato destro sono riportati i nomi delle colonne CSV. Inizialmente, questo lato contiene menu a discesa vuoti.
   - Seleziona **Scegli CSV** per caricare un file CSV di esempio. In questo modo viene compilato il menu a discesa di destra con i nomi delle colonne del file CSV. Per ottenere file CSV di esempio, consulta [questo articolo](https://experienceleague.adobe.com/it/docs/learning-manager/using/integration/migration-manual#csv).
   - Associa ciascun campo Adobe Learning Manager alla colonna CSV corrispondente.

   ![](assets/box-connector2.png)
   _Interfaccia di mappatura degli attributi che mostra i campi Adobe Learning Manager a sinistra e gli elenchi a discesa delle colonne CSV a destra_

4. Seleziona **Salva** per completare il mapping.

Dopo il salvataggio, l’account configurato viene visualizzato come origine dati nell’app Amministratore. Gli amministratori possono quindi pianificare un’importazione o attivare una sincronizzazione manuale.

### Importare istruzioni xAPI

L’importazione di istruzioni xAPI consente il tracciamento dettagliato delle attività di apprendimento tramite l’inserimento di dati di apprendimento esterni in Adobe Learning Manager.

_Configura origine_

La configurazione sorgente xAPI stabilisce la connessione tra i sistemi di apprendimento esterni e il tracciamento delle attività di Adobe Learning Manager.

Per configurare un&#39;origine:

1. Passa alla sezione di configurazione xAPI.
2. Selezionare **Aggiungi nuova configurazione** nell&#39;elenco di configurazione.
3. Digitare **Nome** e **Nome file di origine**.
   - Nome: identificatore descrittivo per questa origine xAPI (ad esempio, Integrazione LMS o Sistema di formazione esterno).
   - Nome file di origine: nome esatto del file che verrà caricato nella cartella Box (deve corrispondere esattamente, compresa l’estensione del file).

   ![](assets/box-connector3.png)
   _Modulo di configurazione che mostra il campo del nome e il campo del nome del file di origine_

4. Seleziona **Salva** per creare la configurazione di base.

_Aggiungi filtri (facoltativo)_

I filtri consentono di importare selettivamente istruzioni xAPI in base a criteri specifici.

Per aggiungere un filtro per l&#39;origine:

1. Seleziona **Filtro** nel riquadro sinistro.
2. Selezionare **Aggiungi nuovo filtro**.
3. Configura quanto segue:
   - **Nome:** Nome descrittivo della regola di filtro.
   - **Condizione:** Operatore di confronto (uguale a, contiene, maggiore di e così via).

   ![](assets/box-connector4.png)
   _Finestra di dialogo per la creazione di filtri con campi Nome e Condizioni_

4. Selezionare **Aggiungi nuovo filtro** per aggiungere altri filtri.
5. Selezionare **Salva** o **Elimina** in base alle esigenze nella colonna **Azioni**.
6. Dopo aver aggiunto i filtri, seleziona **Salva**.

## Pianificare l’importazione

La pianificazione automatizzata garantisce una sincronizzazione dei dati coerente senza interventi manuali, mantenendo i record delle attività di apprendimento correnti.

Per pianificare l&#39;importazione:

1. Selezionare **Configura pianificazione** nel riquadro sinistro.

   ![](assets/box-connector5.png)
   _Pagina di configurazione della pianificazione che mostra le opzioni di attivazione e i controlli temporali_

2. Seleziona **Abilita importazione istruzioni xAPI utilizzando questa connessione**.
3. Selezionare **Abilita pianificazione** per impostare le importazioni automatiche.
4. Imposta i seguenti parametri di pianificazione:

   - **Data inizio:** Data in cui devono iniziare le importazioni pianificate.
   - **Ora:** ora del giorno per l&#39;esecuzione dell&#39;importazione.
   - **Ripetere dopo:** La frequenza di esecuzione delle importazioni (intervalli giornalieri, settimanali e personalizzati).
5. Seleziona **Salva**.

## Esecuzione su richiesta (opzionale)

L&#39;esecuzione su richiesta fornisce l&#39;importazione immediata dei dati al di fuori delle normali operazioni programmate.

Quando utilizzare le importazioni su richiesta:

- Verifica delle nuove configurazioni prima della pianificazione.
- Elaborazione di aggiornamenti di dati urgenti o sensibili al tempo.
- Gestione di migrazioni o correzioni di dati unici.
- Risoluzione dei problemi di importazione.

Per importare manualmente istruzioni xAPI:

1. Seleziona **Su richiesta** nel riquadro a sinistra.
2. Selezionare **Esegui**.

## Visualizza stato esecuzione

Il monitoraggio dello stato consente la gestione proattiva delle operazioni di importazione e la rapida identificazione dei problemi.

Per visualizzare lo stato di esecuzione:

1. Selezionare **Stato esecuzione** per visualizzare un elenco di tutte le esecuzioni di importazione.
2. La pagina di stato mostra:

   - **Data inizio:** All&#39;inizio dell&#39;operazione di importazione
   - **Durata:** Tempo totale richiesto per l&#39;elaborazione
   - **Tipo di importazione:** Indica se l&#39;importazione è stata pianificata o su richiesta
   - **Stato corrente:** informazioni sullo stato in tempo reale
      - **In corso:** importazione attualmente in esecuzione
      - **Completato:** Completato con conteggi record
      - **Errore:** errore con informazioni di diagnostica
