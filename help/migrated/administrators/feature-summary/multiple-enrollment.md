---
title: Iscrizione multipla in Adobe Learning Manager
description: In qualità di Amministratore dell’account, uno dei tuoi compiti principali è creare istanze diverse di sessioni VILT in diversi fusi orari ed eventualmente creare sessioni per gruppi di utenti specifici.
exl-id: c430545d-b48e-432d-a278-658c9281818f
source-git-commit: 22cfa30d22a45afd3e0a65d8c088c2dda4d93072
workflow-type: tm+mt
source-wordcount: '604'
ht-degree: 63%

---

# Iscrizione multipla in Adobe Learning Manager

In Adobe Learning Manager, ogni corso può avere istanze diverse. In qualità di Amministratore dell’account, uno dei tuoi compiti principali è creare istanze diverse di sessioni VILT in diversi fusi orari ed eventualmente creare sessioni per gruppi di utenti specifici.

Prima della versione di luglio 2023, un Amministratore poteva iscrivere un Allievo a una sola istanza. Se un Allievo desiderava seguire un corso in istanze diverse, l’Amministratore creava molti corsi, uno per ogni istanza.

La funzione di iscrizione multipla di Adobe Learning Manager aiuta un Amministratore a evitare tali scenari.

## Gestire le istanze

>[!INFO]
>
>In questo corso imparerai come modificare i dettagli e le proprietà delle istanze.<br><br>[![pulsante](assets/launch-training-button.png)](https://content.adobelearningmanageracademy.com/app/learner?accountId=98632#/course/8318912)</br></br>

Se non è possibile avviare il corso di formazione, scrivere a <almacademy@adobe.com>.

## Che cos’è l’iscrizione multipla

L’iscrizione multipla consente di iscrivere un Allievo più volte in un corso tramite varie istanze disponibili.  Un Allievo può iscriversi a più istanze del corso indipendentemente dallo stato al quale è iscritto, ha completato o deve ancora iniziare. Se l’Autore abilita l’opzione [!UICONTROL Iscrizione multipla], un Allievo può iscriversi a più istanze del corso.

![immagine a iscrizione multipla](assets/multi-enrollment-author.png)
*Avvia più iscrizioni dalle impostazioni*

È possibile monitorare singolarmente l’avanzamento di ogni istanza ed esportare il relativo report.

## Aspetti importanti

* L’iscrizione multipla è applicabile solo quando un corso ha più istanze.
* Una volta attivata l’opzione di iscrizione multipla ed effettuata l’iscrizione degli utenti a più istanze, vengono create nuove righe per ogni corso nel report Trascrizione Allievo (una riga per ogni istanza e ogni Allievo).
* Se è impostata l’automazione dei report che prevede una sola riga per corso, devi apportare le modifiche necessarie all’automazione dei report prima di abilitare la funzione Iscrizione multipla.
* Le API dell’amministratore non supportano scenari di iscrizione multipla. Se hai esigenze particolari, contatta il CSM.

## Come abilitare l’Iscrizione multipla

1. Accedi al tuo account Adobe Learning Manager come autore.
1. Seleziona il corso a cui vuoi che gli Allievi si iscrivano più volte.
1. Nel pannello a sinistra, seleziona **[!UICONTROL Impostazioni]** > **[!UICONTROL Modifica]** > **[!UICONTROL Configurazione istanza]** > **[!UICONTROL Abilita iscrizione multipla]**.

![immagine a iscrizione multipla](assets/multi-enrollment-author.png)
*Abilita iscrizione multipla*

>[!NOTE]
>
>In qualità di Autore, non è possibile attivare Contemporaneamente il parametro di istanza e la registrazione multipla.

## Vista Allievo

Le iscrizioni multiple sono utili quando un Allievo desidera iscriversi a un corso in aula o in aula virtuale o desidera completare di nuovo un corso prima di passare a un altro.

Gli Allievi non iscritti, quando selezionano un corso, visualizzano la schermata sotto il corso con più istanze. Quindi, possono selezionare ogni istanza e iscriversi.

![immagine di visualizzazione Allievo](assets/learner-view.png)
*Visualizzare le istanze*

Dopo l’iscrizione a un’istanza, è possibile effettuare l’iscrizione ad altre istanze selezionando l’opzione Visualizza tutte le istanze nel riquadro a destra.

![immagine del corso a più iscrizioni](assets/enroll-instance.png)
*Iscriversi a un&#39;istanza*

L’avanzamento in ciascuna istanza può essere monitorato come segue:

![monitoraggio dell&#39;avanzamento](assets/check-progress.png)
*Monitoraggio dell&#39;avanzamento di ogni istanza*

## Modifiche alle iscrizioni multiple in Amministratore

**Iscrizione:**

Durante l’iscrizione degli Allievi, puoi abilitare la seguente casella di controllo:

*&quot;Gli Allievi selezionati potrebbero essere già iscritti ad altre istanze di questo corso. Consenti l’iscrizione di questi Allievi anche all’istanza...&quot;*

![modifiche dell&#39;amministratore](assets/admin-changes.png)
*Opzione di iscrizione per gli amministratori*

Se l’Allievo è già iscritto a un’istanza e tu, in qualità di Amministratore, stai tentando di iscriverlo a un’istanza di corso diversa, seleziona Sì.

## Report

Per un Allievo iscritto a due istanze dello stesso corso, vengono create due righe per ogni istanza del corso. Il report mostra anche lo stato di avanzamento delle istanze.
