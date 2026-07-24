---
jcr-language: en_us
title: Domande frequenti (Report Builder)
description: Ottieni risposte alle domande frequenti sul Report Builder Adobe Learning Manager.
contentowner: mmanuel
source-git-commit: 8823a5481bc3b34266f7ec36a8f3c26cb923e1ce
workflow-type: tm+mt
source-wordcount: '443'
ht-degree: 0%

---


# Domande frequenti (Report Builder)

**Qual è la differenza tra un modello e un report?**

I modelli sono configurazioni di report predefinite fornite da Adobe Learning Manager. Sono progettati per i casi d&#39;uso più comuni, pronti per il download immediato e di sola lettura. Non puoi modificarli. I report sono le tue configurazioni salvate. Puoi crearli creando da zero o duplicando un modello e modificando la copia. I report vengono visualizzati nella scheda **Report**; i modelli vengono visualizzati nella scheda **Modelli**.

**È possibile modificare direttamente un modello?**

N. I modelli sono di sola lettura. Per personalizzare un modello, seleziona **Duplica** per creare una copia modificabile. Le modifiche vengono salvate come nuovo report nella scheda **Report** e non influiscono sul modello originale.

Le righe duplicate vengono visualizzate quando un campo nei dati ha una relazione uno-a-molti con il record principale. Le cause più comuni includono sessioni con più istruttori (una riga per istruttore per sessione) e oggetti di apprendimento con più autori. Per risolvere questo problema, aggiungi come colonna il campo con più valori, ad esempio **Nomi Istruttori** o **Nome Autore**.

**Perché le date vengono visualizzate in UTC?**

In questa versione, Report Builder restituisce i valori di data in UTC. Il fuso orario configurato del tuo account verrà applicato ai campi data in una versione futura. Quando analizzi i dati basati sulla data, considera lo scostamento UTC relativo al fuso orario principale del tuo account.

**Quanto tempo è necessario per visualizzare i nuovi dati di registrazione o completamento?**

Il Report Builder esegue il pull dal database di Adobe Learning Manager, che ha una latenza massima di circa 15 minuti a partire dal momento in cui si verifica un evento nel sistema. Se hai appena registrato un&#39;iscrizione o un completamento che non viene visualizzato nel report, attendi almeno 15 minuti e scarica di nuovo.

**Esiste un limite alle righe o alle colonne in un report?**

I report sono limitati a circa 1 milione di righe. Non esiste alcun limite al numero di colonne in questa versione. Se il report richiede più di 1 milione di righe, applicare filtri per restringere l’ambito.

**Esiste un limite alle dimensioni dei file durante l&#39;esportazione dei report dal Report Builder?**

Al momento, i file di report esportati di dimensioni superiori a 5 GB non sono supportati in Report Builder. Se si prevede che il report superi queste dimensioni, valuta l’applicazione di filtri aggiuntivi o la riduzione del numero di righe per mantenere l’esportazione al di sotto di 5 GB.

**È possibile estrarre i dati di Report Builder tramite un&#39;API o un&#39;automazione?**

L’accesso API automatico ai report di Report Builder è previsto per una versione futura. Nella versione corrente, i report vengono scaricati manualmente tramite l’interfaccia utente del Report Builder o ricevuti su base pianificata tramite la funzione di abbonamento.
