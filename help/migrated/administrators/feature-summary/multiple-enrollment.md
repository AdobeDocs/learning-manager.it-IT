---
title: Iscrizione multipla ad Adobe Learning Manager
description: In qualità di amministratore dell’account, uno dei tuoi compiti principali è creare istanze diverse di sessioni VILT in diversi fusi orari ed eventualmente creare sessioni per gruppi di utenti specifici.
source-git-commit: fc5b5afd8dd42ac3aa0e5190d6f421035df41a89
workflow-type: tm+mt
source-wordcount: '559'
ht-degree: 0%

---

# Iscrizione multipla ad Adobe Learning Manager

Nell’Adobe di Learning Manager, ogni corso può avere istanze diverse. In qualità di amministratore dell’account, uno dei tuoi compiti principali è creare istanze diverse di sessioni VILT in diversi fusi orari ed eventualmente creare sessioni per gruppi di utenti specifici.

Prima della versione di luglio 2023, quando un Amministratore iscriveva un Allievo, poteva iscriversi a una sola istanza. Se un Allievo desiderava seguire un corso in istanze diverse, l’Amministratore creava molti corsi, uno per ogni istanza.

Adobe La funzione di iscrizione multipla di Learning Manager aiuta un Amministratore a evitare tali scenari.

## Che cos’è la registrazione multipla

L’iscrizione multipla iscrive un Allievo più volte in un corso tramite varie istanze disponibili.  Un Allievo può iscriversi a più istanze del corso indipendentemente dallo stato al quale è iscritto, ha completato o deve ancora iniziare. Quando l’Autore abilita [!UICONTROL Iscrizione multipla] alternanza, un allievo può quindi iscriversi a più istanze del corso.

![immagine di iscrizione multipla](assets/multi-enrollment-author.png)
*Avvia iscrizione multipla da Impostazioni*

L’avanzamento di ogni istanza può essere monitorato singolarmente e un report può essere esportato per monitorare l’avanzamento di ogni istanza.

## Aspetti importanti

* L’iscrizione multipla è applicabile solo quando un corso ha più istanze.
* Una volta attivata l’opzione di iscrizione multipla e effettuata l’iscrizione degli utenti a più istanze, vengono create nuove righe per ogni corso nel report Trascrizione Allievo (una riga per ogni istanza e ogni Allievo).
* Se è stata impostata l’automazione dei report che prevede una sola riga per corso, è necessario apportare le modifiche necessarie all’automazione dei report prima di abilitare la funzione Iscrizione multipla.

## Come abilitare la registrazione multipla

1. Accedi all’account di Adobe Learning Manager come Autore.
1. Seleziona il corso a cui vuoi che gli Allievi si iscrivano più volte.
1. Nel pannello a sinistra, seleziona **[!UICONTROL Impostazioni]** > **[!UICONTROL Modifica]** > **[!UICONTROL Configurazione dell&#39;istanza]** > **[!UICONTROL Abilita iscrizione multipla]**.

![immagine di iscrizione multipla](assets/multi-enrollment-author.png)
*Abilita iscrizione multipla*

>[!NOTE]
>
>In qualità di Autore, non è possibile attivare Contemporaneamente il parametro di istanza e la registrazione multipla.

## Vista Allievo

Le iscrizioni multiple sono utili quando un Allievo desidera iscriversi a un corso in aula o in aula virtuale o desidera completare di nuovo un corso prima di passare a un altro corso.

Per gli Allievi che non si sono iscritti, quando selezionano un corso, visualizzeranno la schermata sotto il corso con più istanze. Quindi, possono selezionare ogni istanza e iscriversi.

![immagine visualizzazione Allievo](assets/learner-view.png)
*Visualizzare le istanze*

Dopo l’iscrizione a un’istanza, è possibile effettuare l’iscrizione ad altre istanze selezionando l’opzione Visualizza tutte le istanze nel riquadro a destra.

![immagine del corso con più iscrizioni](assets/enroll-instance.png)
*Iscriversi a un’istanza*

L’avanzamento in ciascuna istanza può essere monitorato come segue:

![traccia avanzamento](assets/check-progress.png)
*Tenere traccia dell&#39;avanzamento di ogni istanza*

## Modifiche a più iscrizioni nell’amministratore

**Registrazione:**

Durante l’iscrizione degli Allievi, puoi abilitare la seguente casella di controllo:

*&quot;Gli Allievi selezionati potrebbero essere già iscritti ad altre istanze di questo corso. Consenti l’iscrizione di questi Allievi anche all’istanza ...&quot;*

![modifiche dell’amministratore](assets/admin-changes.png)
*Opzione di iscrizione per gli Amministratori*

Se l’Allievo è già iscritto a un’istanza e tu, in qualità di Amministratore, stai tentando di iscriverlo a un’istanza di corso diversa, seleziona Sì.

## Report

Per un Allievo iscritto a due istanze dello stesso corso, vengono create due righe per ogni istanza del corso. Il report mostra anche lo stato di avanzamento delle istanze.
