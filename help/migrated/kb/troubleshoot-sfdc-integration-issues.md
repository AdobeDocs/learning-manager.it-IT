---
jcr-language: en_us
title: Risoluzione dei problemi di integrazione di Salesforce (SFDC) con Adobe Learning Manager
description: risoluzione dei problemi comuni di integrazione di Salesforce (SFDC) con Adobe Learning Manager (ALM), tra cui esportazioni non riuscite, problemi di autorizzazione dei campi negli oggetti personalizzati SFDC e note importanti sulla compatibilità SFDC-ALM.
contentowner: saghosh
source-git-commit: cedb4acc89e7d972a4752e10c4fb6930c4633f6a
workflow-type: tm+mt
source-wordcount: '596'
ht-degree: 0%

---


# Risoluzione dei problemi di integrazione di Salesforce (SFDC) con Adobe Learning Manager

## Risoluzione dei problemi relativi agli errori di esportazione di SFDC (nessuna esportazione per più di 2-3 ore)

Se l&#39;esportazione SFDC non è stata completata correttamente per più di **2-3 ore**, utilizza i passaggi seguenti per identificare e comprendere il problema.

1. Passa alla pagina **Home di Salesforce**.
2. Nella casella di ricerca **Ricerca rapida**, digita **`Bulk Data Load Jobs`** e aprilo.
3. La pagina visualizza i processi di caricamento dati in blocco per **ultimi 7 giorni**.
4. Cerca processi correlati a **oggetti Adobe Learning Manager (ALM)**.
5. Fare clic sul job specifico che si desidera analizzare.
6. Scorri fino alla **fine** della pagina dei dettagli del processo per visualizzare il **messaggio di errore** e ulteriori dettagli.

In molti casi, la causa principale è **autorizzazioni a livello di campo insufficienti in SFDC**. Il nome del campo che non riesce può essere simile al seguente:

- `cp_Module_ID`
- o altri campi `cp_...` correlati a oggetti personalizzati ALM.

Se nell’errore sono presenti tali campi, passa alla sezione successiva.

## Concedere le autorizzazioni per i campi oggetto personalizzato ALM in SFDC

Utilizza la funzionalità **Accessibilità dei campi** per risolvere i problemi di autorizzazione in campi specifici (ad esempio, `cp_Module_ID`).

### Passaggi

1. Passa alla pagina **Home di Salesforce**.
2. Nella casella di ricerca **Ricerca rapida**, digita **`Field Accessibility`** e aprilo.
3. Dall&#39;elenco degli oggetti, selezionare il **tipo di report/oggetto** pertinente.
   - Esempio: `cp_LearnerTranscript_xxxx_xxxx` per il report Trascrizione Allievo (LT).
4. Nella pagina successiva, scegli **&quot;Visualizza per campi&quot;**.
5. Nel menu a discesa **del campo**, seleziona il campo visualizzato nell&#39;errore di esportazione
   - Esempio: `cp_Module_ID`.
6. Nella matrice di accesso, fare clic sulla voce **&quot;Nascosto&quot;** per il profilo **Amministratore di sistema** (e altri profili pertinenti, se necessario).
7. Nella pagina successiva:
   - Abilitare **&quot;Visible&quot;** se necessario.
   - Fai clic su **Salva** nella parte inferiore della pagina.
8. Dopo il salvataggio, tornate alla vista di accessibilità dei campi. Il campo dovrebbe ora essere visualizzato come **&quot;Modificabile&quot;** per **Amministratore di sistema** (e qualsiasi altro profilo aggiornato).

## Ripeti l’operazione per tutti i campi interessati e riprova l’esportazione.

1. **Ripetere** i passaggi relativi all&#39;accessibilità dei campi nella sezione 2 per **ogni campo** ha segnalato problemi di autorizzazione in **processi di caricamento dati in blocco**.
2. Una volta che tutti i campi problematici hanno la corretta visibilità e le autorizzazioni di modifica:
   - Torna a **Adobe Learning Manager**.
   - Nella configurazione **del connettore SFDC**, **riprova l&#39;esportazione**.


## Note importanti e limitazioni

Tenete presenti queste specifiche SFDC-ALM durante la progettazione o la risoluzione dei problemi di integrazione.

### Nessuna creazione automatica di oggetti/campi in SFDC

- Il connettore **SFDC non crea nuovi oggetti o campi in Salesforce**.
- Se in ALM **viene aggiunto un** nuovo campo e si desidera che venga visualizzato in SFDC:
   - **Creare manualmente il campo personalizzato corrispondente** in SFDC.
   - **Associare** il campo personalizzato SFDC al **campo ALM appropriato** nella configurazione del connettore.
   - Assicurati che il nuovo campo disponga di **autorizzazioni a livello di campo corrette** (utilizza la sezione 2).

### URL di richiamata per gli account ALM con domini personalizzati

- Se l&#39;account ALM utilizza un **dominio personalizzato**, il team tecnico deve **aggiungere tale dominio personalizzato** all&#39;**elenco degli URL consentiti per il callback** per l&#39;app di produzione OAuth del connettore SFDC.
- Questa operazione viene eseguita tramite una **richiesta Jira** al reparto tecnico.
- In caso contrario, il flusso OAuth del connettore potrebbe non riuscire.

### Limitazione del fuso orario (solo UTC)

- Se l&#39;organizzazione SFDC utilizza un **fuso orario diverso da UTC**, i **dati di completamento e di iscrizione possono non essere visualizzati** durante la sincronizzazione.
- Motivo: ALM **attualmente supporta solo il fuso orario UTC** per l&#39;integrazione SFDC.
- Riferimento interno: PAPI-24525 viene sollevato per supportare fusi orari aggiuntivi.

### Limitazione del tipo di dati del filtro (elenco di selezione o elenco di controllo)

- ALM supporta l&#39;importazione di **filtri SFDC creati con campi di elenco di selezione**.
- ALM **non supporta** filtri basati su campi di elenco di controllo/selezione multipla.
- Motivo: ALM **supporta solo tipi di dati stringa** per i filtri SFDC.
