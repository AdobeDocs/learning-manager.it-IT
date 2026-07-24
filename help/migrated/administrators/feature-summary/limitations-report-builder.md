---
jcr-language: en_us
title: Limitazioni del Report Builder in Adobe Learning Manager
description: Comprendere quali elementi non sono supportati dal Report Builder in questa versione, in modo da poter pianificare di conseguenza l’approccio alla creazione di report.
contentowner: mmanuel
source-git-commit: 8823a5481bc3b34266f7ec36a8f3c26cb923e1ce
workflow-type: tm+mt
source-wordcount: '411'
ht-degree: 0%

---


# Limitazioni del Report Builder in Adobe Learning Manager

## Panoramica

Report Builder copre un&#39;ampia gamma di esigenze di reporting personalizzate, ma alcuni tipi di report, set di dati e configurazioni non sono supportati in questa versione. In questa sezione sono elencate le limitazioni note e vengono suggerite soluzioni alternative, ove disponibili.

## Certificazioni ricorrenti

Alcune query relative a certificazioni ricorrenti non funzionano correttamente in Report Builder in questa versione. Se il report prevede cicli di certificazione ricorrenti, ad esempio la registrazione della nuova registrazione o il completamento di più periodi di certificazione, utilizzare i report di certificazione esistenti in Adobe Learning Manager.

## Set di dati e tipi di report non supportati

I seguenti elementi non sono disponibili in Report Builder in questa versione:

* **Dati sui risultati aziendali**: il Report Builder non supporta le integrazioni Bring Your Own Data (BYOD). I report che combinano dati aziendali esterni con dati LMS non sono supportati.
* **Report di audit**: gli audit trail del sistema e i log delle attività dell&#39;amministratore non possono essere incorporati nel Report Builder. Utilizza i report di audit esistenti nella visualizzazione per amministratori per questi dati.
* **Report incrementali**: ogni volta il Report Builder genera report snapshot completi. I report incrementali che restituiscono solo i record modificati dall&#39;ultimo download non sono supportati. Per i dati incrementali, utilizza l’API dei processi.

## Limitazioni del report di andamento

### Una sola colonna di date per report di tendenza

Un singolo report di andamento può essere raggruppato in base a una sola colonna basata su date. Non è possibile combinare due tendenze diverse basate sulla data nello stesso report.

Ad esempio, è possibile creare:

* Report che mostra **iscrizioni per mese** (raggruppate per data di iscrizione)
* Un report separato che mostra **completamenti per mese** (raggruppati per data di completamento)

Non è possibile creare un singolo report che mostra sia il mese di iscrizione che il mese di completamento come colonne di andamento separate. Per ottenere entrambi, creare due report separati e analizzarli uno accanto all&#39;altro.

### Le tendenze riflettono i dati correnti, non le snapshot cronologiche

I report sulle tendenze nel Report Builder si basano sui dati temporali correnti, non su snapshot cronologici. Il report riflette lo stato dei record esistenti, distribuiti nei relativi campi di data.

Ciò significa che:

* Un Allievo che si è iscritto a gennaio ma che successivamente ha annullato l’iscrizione potrebbe non essere visualizzato nella tendenza di iscrizione di gennaio
* Un gruppo di utenti che è stato riorganizzato non riflette la sua iscrizione storica negli ultimi mesi
* I record eliminati potrebbero non essere visualizzati nella tendenza per il periodo in cui erano attivi

Utilizzare i rapporti sulle tendenze per l&#39;analisi direzionale. Per record cronologici precisi o scopi di audit, utilizza i report fissi esistenti o le esportazioni API dei processi.
