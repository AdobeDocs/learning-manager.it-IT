---
description: Scopri come il report di prova di verifica dell’amministratore monitora le modifiche della configurazione, mostrando chi le ha apportate, quando e i valori prima e dopo.
jcr-language: en_us
title: Report di prova di verifica dell’amministratore
exl-id: 71b2ee42-ef1c-47fb-95ad-c339562e227d
source-git-commit: 500a467395fc8ada89cd6ea7e3783b73cc43045d
workflow-type: tm+mt
source-wordcount: '1085'
ht-degree: 0%
---

# Report di prova di verifica dell’amministratore {#adminaudittrailreport}

Genera un report delle modifiche di configurazione apportate alle impostazioni di base, avanzate e integrazione dell’account, inclusi gli utenti che hanno apportato ogni modifica, quando e il valore prima e dopo.

## Elementi acquisiti dal report

Il report Audit trail dell’amministratore fornisce un record cronologico delle modifiche di configurazione in modo da poter determinare:

- Chi ha apportato il cambiamento
- Quando è stata effettuata la modifica
- Che cosa era l’impostazione prima della modifica
- Che cosa è l’impostazione dopo la modifica

La relazione riguarda le modifiche apportate:

- Impostazioni **Nozioni di base**
- Impostazioni **avanzate**
- Impostazioni **Integrazioni**

Il report è di tipo additivo: i nuovi record di modifica vengono aggiunti nel tempo e le voci registrate in precedenza non vengono mai rimosse. In questo modo è possibile esaminare la cronologia completa di un&#39;impostazione tra più modifiche, non solo il suo valore corrente.

Il report è disponibile per tutti gli utenti con privilegi Report e accesso completo al gruppo di utenti. Sono inclusi gli amministratori completi e gli amministratori personalizzati a cui è stato concesso l&#39;accesso al report.

>[!NOTE]
>
>I record sono disponibili a partire dall’aggiornamento 112, settembre 2026. Le modifiche apportate prima di questo aggiornamento non vengono incluse nel report. Consulta [note sulla versione](/help/migrated/release-note/release-notes.md) aggiornamento 112.

## Perché questo report è importante per la conformità

Le organizzazioni che operano in settori regolamentati spesso devono dimostrare che le modifiche alla configurazione dei sistemi che gestiscono i record elettronici vengono rilevate, attribuibili e mantenute. Il report Audit trail dell’amministratore supporta questi requisiti identificando la persona, l’impostazione, l’ora e i valori prima e dopo ogni modifica.

>[!NOTE]
>
>Questo report supporta le attività di conformità della tua organizzazione. Esso non certifica di per sé la conformità ad alcun regolamento o norma specifico.

## Generare un report di prova di verifica dell’amministratore

1. Accedi a Adobe Learning Manager come Amministratore.
2. Nella barra di navigazione a sinistra, seleziona **Gestisci** > **Report** > **Report personalizzati**.

   ![](/help/migrated/administrators/feature-summary/assets/audit-trail-report1.png)

3. Scorri verso il basso e seleziona **Audit trail amministratore**.

   ![](/help/migrated/administrators/feature-summary/assets/audit-trail-report2.png)

4. **Seleziona intervallo**: scegli il periodo per il quale creare report: **Ultima settimana**, **Ultimo mese** o **Scegli date**. Se si seleziona **Scegli date**, immettere una data **Da** e una data **A**.
5. **Selezionare il tipo di impostazione**: scegliere **Seleziona tutto**, **Nozioni di base**, **Integrazioni** o **Avanzate**.

   Per visualizzare l&#39;elenco completo delle impostazioni rilevate da questo report in Nozioni di base, Integrazioni e Avanzate, selezionare **Scarica elenco delle impostazioni**.

   ![](/help/migrated/administrators/feature-summary/assets/audit-trail-report6.png)

   ![](/help/migrated/administrators/feature-summary/assets/audit-trail-report3.png)

6. Seleziona **Genera**.

   ![](/help/migrated/administrators/feature-summary/assets/audit-trail-report4.png)

   ![](/help/migrated/administrators/feature-summary/assets/audit-trail-report5.png)

Un file `.csv` contenente le modifiche viene scaricato nella cartella Download del browser. La generazione dei report può richiedere alcuni minuti: puoi continuare a utilizzare Adobe Learning Manager durante l’elaborazione. Se chiudi la finestra del browser prima che il report sia pronto, il download inizia al successivo accesso.

## Usi comuni per questo report

- **Esaminare una modifica imprevista delle impostazioni** — verificare quali modifiche sono state apportate, quando e chi, anziché basarsi su ipotesi.
- **Rivedere le modifiche apportate da più amministratori**: genera una visualizzazione consolidata di tutte le attività di configurazione che rientrano nell&#39;ambito del report per un determinato periodo, anziché contattare ogni amministratore singolarmente.
- **Confermare una modifica di configurazione approvata**: verificare che l&#39;amministratore previsto abbia apportato la modifica entro il periodo di tempo previsto e che il nuovo valore corrisponda a quello approvato.
- **Confrontare la cronologia di un&#39;impostazione con più modifiche**: utilizzare la colonna **Revisione** per verificare quante volte un&#39;impostazione specifica è stata modificata e verificare ogni valore registrato in sequenza, anche se una modifica successiva ha ripristinato un valore precedente.
- **Supportare una revisione della conformità**: generare il report per il periodo in esame come parte dei record amministrativi e di conformità.
- **Esaminare le impostazioni dopo una modifica dei criteri** — verificare che gli aggiornamenti di configurazione previsti siano stati applicati in modo coerente e identificare eventuali modifiche impreviste.
- **Gestione di un record amministrativo storico** — download e conservazione dei report in base alle pratiche di gestione dei record dell&#39;organizzazione.

## Riferimento colonna report

Il file `.csv` scaricato include le colonne seguenti.

| Colonna | Descrizione |
|---|---|
| **ID evento** | Identificatore univoco per il record di modifica specifico. |
| **Timestamp (UTC)** | La data e l&#39;ora in cui è stata apportata la modifica, in Ora universale coordinata. |
| **E-mail** | L&#39;indirizzo e-mail dell&#39;amministratore che ha apportato la modifica. |
| **UUID** | Identificatore univoco per l&#39;amministratore che ha apportato la modifica. Compilato solo se UUID è abilitato a livello di account. |
| **Nome amministratore** | Nome visualizzato dell&#39;amministratore che ha apportato la modifica. |
| **Tipo di evento** | Categoria dell&#39;evento registrato, ad esempio `Modify`, `Create` o `Delete`. |
| **Tipo di azione** | Tipo di azione eseguita sull&#39;impostazione, ad esempio `CREATE_SETTING`, `UPDATE_SETTING` o `DELETE_SETTING`. |
| **Tipo di oggetto** | Oggetto di configurazione o impostazione modificato. |
| **ID oggetto** | Identificatore univoco dell&#39;impostazione o dell&#39;oggetto di configurazione specifico che è stato modificato. |
| **Valore precedente** | Il valore dell&#39;impostazione prima della modifica. Per un&#39;impostazione eliminata, viene visualizzato il valore esistente prima dell&#39;eliminazione. |
| **Nuovo valore** | Il valore dell&#39;impostazione dopo la modifica. Per un&#39;impostazione eliminata, questa casella è vuota. |
| **Revisione** | Numero di volte in cui l&#39;ID oggetto specifico è stato modificato durante la registrazione dell&#39;evento. La prima modifica registrata per un oggetto inizia da 1. |

>[!TIP]
>
>Per trovare tutte le impostazioni eliminate durante un periodo, filtrare il file scaricato in cui **Tipo di azione** è `DELETE_SETTING`.

## Accedi a questo report a livello di programmazione

È possibile recuperare il report di prova di verifica dell’amministratore a livello di programmazione utilizzando l’API dei processi, anziché generarlo manualmente dall’app di amministrazione. Questa funzione è utile per pianificare esportazioni regolari o inserire il report in un sistema di monitoraggio a valle o di avviso. Vedere [Report di prova di verifica dell&#39;amministratore dell&#39;API dei processi](/help/migrated/api-changes-sep-2026.md#job-api-for-admin-audit-trail-report).

## Limitazioni

- **Localizzazione**: contenuto del report non localizzato. Il report viene generato nella lingua predefinita dell’account, indipendentemente dalle impostazioni internazionali configurate dell’account.
- **Motivo della modifica**: il report non rileva il motivo della modifica. Conserva separatamente qualsiasi richiesta di modifica, approvazione o giustificazione aziendale correlata.

## Procedure ottimali

- Selezionare un intervallo di date che copra la modifica sospetta o pianificata.
- Selezionare **Seleziona tutto** quando l&#39;area delle impostazioni interessate non è nota.
- Confrontare entrambe le colonne **Valore precedente** e **Nuovo valore** per ogni voce.
- Utilizza le colonne **Nome amministratore** e **Timestamp** per correlare una modifica con il lavoro approvato o i record interni.
- Conservare separatamente la richiesta di modifica, l&#39;approvazione o la giustificazione commerciale correlata quando l&#39;organizzazione richiede una spiegazione documentata per una modifica.

## Risoluzione dei problemi

**Nessun record visualizzato prima di una determinata data**
I record sono disponibili solo dall’aggiornamento 112 (settembre 2026) in poi. Le modifiche apportate prima di tale aggiornamento non vengono incluse nel report. Consulta [note sulla versione](/help/migrated/release-note/release-notes.md)

**La colonna UUID è vuota per alcuni o tutti i record**
La colonna UUID viene compilata solo se UUID è abilitato a livello di account. Se non è attivata, questa colonna non sarà presente.

**Ho un ruolo di amministratore personalizzato, ma non riesco a trovare questo report**
Conferma che al tuo ruolo personalizzato sono stati concessi i privilegi di Report e l&#39;accesso completo al gruppo di utenti. Se necessario, contatta il proprietario dell’account o un amministratore completo per richiedere l’accesso.
