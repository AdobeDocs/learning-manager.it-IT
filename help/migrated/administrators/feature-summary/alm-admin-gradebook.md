---
description: Tutte le informazioni necessarie per abilitare il Gradebook e renderlo visibile ad autori e allievi
jcr-language: en_us
title: Gradebook per l'amministratore
source-git-commit: 971576b95ab0f75b9d28a7f3d1d62440927925f7
workflow-type: tm+mt
source-wordcount: '395'
ht-degree: 1%

---


# Abilita visibilità Gradebook per l&#39;account

## Panoramica

Prima che gli Autori possano mostrare il libro di schemi agli Allievi in un corso, un Amministratore deve abilitare l’impostazione Visibilità libro di schemi a livello di account. Questa impostazione funge da interruttore principale: quando è disattivata, gli allievi non possono visualizzare il Gradebook in alcun corso, indipendentemente dalla configurazione dei singoli corsi.

## Controlli di questa impostazione

L’impostazione **Visibilità gradebook** in **Impostazioni** > **Generali** determina se agli autori è consentito esporre il gradebook agli allievi a livello di corso.

| Stato impostazione | Effetto |
| --- | --- |
| Abilitato | Gli autori possono controllare la visibilità dei gradebook per corso utilizzando l’opzione **Mostra gradebook agli allievi** nell’editor del corso. Gli Allievi visualizzano la scheda **Gradebook** nei corsi in cui è stata abilitata dall’Autore. |
| Disattivata | Gli allievi non possono visualizzare il Gradebook in alcun corso. Se è disattivata, la configurazione del corso non avrà l’impostazione per mostrare il libro paga agli Allievi. |


Ciò significa che l’impostazione a livello di account e l’impostazione a livello di corso funzionano insieme. Entrambi devono essere abilitati affinché un Allievo possa visualizzare il libro di testo.

## Attivare la visibilità dei gradebook

1. Accedi a Adobe Learning Manager come amministratore.
2. Nella barra di navigazione a sinistra, seleziona **Impostazioni**.
3. Selezionare **Generale**.
4. Scorrete fino alla sezione **Visibilità gradebook**.
5. Seleziona la casella di controllo **Abilita visualizzazione Gradebook per gli Allievi**.

   ![](assets/gradebook-admin-1.png)

Gli Autori possono ora configurare la visibilità dei gradebook per corso.

## Impatto sui flussi di lavoro degli autori

Quando questa impostazione a livello di account è abilitata, nell’editor del corso diventa disponibile l’interruttore **Mostra gradebook agli Allievi**. Gli Autori utilizzano questo interruttore per decidere, in base al corso, se gli Allievi possono visualizzare la scheda **Gradebook**.

Quando questa impostazione a livello di account è disattivata:

* L’interruttore **Mostra gradebook agli allievi** nell’editor del corso potrebbe ancora essere visualizzato, ma qualsiasi configurazione a livello di corso viene ignorata. Gli Allievi non visualizzeranno il libro dei voti.
* I punteggi dei gradebook e i calcoli ponderati continuano a essere eseguiti in background per scopi di reporting da parte dell&#39;amministratore.
* Gli Amministratori e gli Amministratori personalizzati possono ancora scaricare le Trascrizioni Allievi con i dati dei gradebook.

>[!NOTE]
>
>Se si disabilita questa impostazione a livello di account, non viene eliminata alcuna configurazione o punteggio del registro di livello. Se la riattivi, vengono ripristinate immediatamente tutte le impostazioni della cartella di lavoro a livello di corso configurate in precedenza.

## Modalità di interazione delle due impostazioni

| Impostazione a livello di account | Impostazione a livello di corso | Cosa vede l’Allievo |
| --- | --- | --- |
| Abilitato | Mostra gradebook agli Allievi: **In data** | Scheda **Gradebook** visibile nel lettore del corso |
| Abilitato | Mostrare la cartella di lavoro agli Allievi: **Disattivato** | Nessuna scheda Gradebook; solo i punteggi calcolati internamente |
