---
description: Ulteriori informazioni sulla configurazione delle impostazioni avanzate in Adobe Learning Manager
jcr-language: en_us
title: Impostazioni avanzate in Adobe Learning Manager
source-git-commit: 03123dcd8d9066cdfcb0fe97e61acb3df625a23e
workflow-type: tm+mt
source-wordcount: '571'
ht-degree: 34%

---


# Impostazioni avanzate in Adobe Learning Manager

## Etichette del catalogo

Le etichette del catalogo in Adobe Learning Manager vengono utilizzate per contrassegnare gli oggetti di apprendimento (corsi, certificazioni, percorsi di apprendimento e così via) con campi e valori specifici. Queste etichette aiutano l&#39;utente e gli autori a classificare e organizzare i contenuti in modo efficace, consentendo un migliore filtraggio, tracciamento e reporting.

Per ulteriori informazioni, vedere [Etichette del catalogo in Adobe Learning Manager](/help/migrated/administrators/feature-summary/catalog-labels.md).


>[!NOTE]
>
>* Etichette obbligatorie: puoi scegliere di rendere le etichette del catalogo obbligatorie per gli autori durante la creazione del corso.
>* Flusso di lavoro dell’Autore: gli Autori devono aggiungere etichette di conformità durante la creazione o la modifica dei corsi per garantire una corretta categorizzazione.

## Cartella dei contenuti

Le cartelle dei contenuti consentono di organizzare e gestire i contenuti creando cartelle pubbliche o private. Questa funzionalità garantisce che i contenuti siano accessibili solo a specifici autori o gruppi, fornendo un migliore controllo sulla visibilità e la gestione dei contenuti.

**Punti chiave:**

Una cartella è un archivio di contenuti, un sottoinsieme dell’intera libreria dei contenuti disponibile in un account con le seguenti proprietà:

* Solo l&#39;utente (amministratore) può creare, modificare o eliminare una cartella.
* È possibile controllare l&#39;accesso alle cartelle come parte della definizione dei ruoli solo per gli amministratori personalizzati.
* Il contenuto deve sempre essere associato ad almeno una cartella. Per iniziare, tutto il contenuto sarà associato alla cartella pubblica, che potrà essere modificata in un secondo momento.
* Il contenuto può essere associato a più cartelle al momento della creazione e sarà possibile farlo anche mediante un’operazione di copia.
* Tutti i nomi delle cartelle devono essere univoci all’interno dell’account, altrimenti si verificherà un errore nell’assegnazione del nome a una cartella.

Le cartelle controllano solo la visibilità del contenuto e non ne creano delle copie. Pertanto, la modifica del contenuto si rifletterà in tutte le cartelle associate.

**Cartella pubblica**

Una cartella pubblica è sempre presente in un account e inizialmente tutti i contenuti saranno parte di questa cartella. Gli autori potranno poi spostarli da questa ad altre cartelle. Una cartella pubblica ha le seguenti proprietà:

* Per impostazione predefinita, ogni contenuto associato a questa cartella sarà accessibile a tutti i tipi di autore.
* Qualsiasi contenuto inserito in una cartella pubblica non può far parte di un’altra cartella, e viceversa.

Questa cartella non può far parte della definizione di ruoli configurabili. Di conseguenza, la mancanza di una cartella pubblica nella definizione di ruoli configurabili non limita l’accesso a una cartella pubblica.

**Cartella privata**

Qualsiasi cartella creata dall&#39;utente è una cartella privata.

**Aggiungere una cartella di contenuti**

Per aggiungere una cartella di contenuti, attieniti alla seguente procedura:

1. Selezionare **[!UICONTROL Impostazioni]** > **[!UICONTROL Cartella dei contenuti]**.
2. Seleziona **[!UICONTROL Aggiungi]** per creare una nuova cartella.
3. Digitare il nome e la descrizione della cartella da creare.

   ![testo alternativo](assets/advanced-settings-picture1.png)

4. Seleziona **[!UICONTROL Salva]** per creare la cartella.

**Operazioni con le cartelle**

* **[!UICONTROL Aggiungi cartella]**: per aggiungere una cartella, selezionala e scegli **[!UICONTROL Aggiungi]** nell&#39;angolo superiore destro dello schermo.
* **[!UICONTROL Eliminare una cartella]**: per eliminare una cartella, selezionare la cartella da eliminare, scegliere il menu **[!UICONTROL Azioni]**, quindi selezionare **[!UICONTROL Elimina cartella]**.

## Aule

Crea e gestisci una libreria di aule fisiche o virtuali. Questi percorsi possono essere utilizzati dagli Autori e dagli Amministratori per configurare eventi di formazione ILT (Instructor-Led Training). La funzione assicura che i dettagli dell&#39;aula, come i limiti dei posti e le informazioni sulla posizione, siano preconfigurati e facilmente accessibili.

Per ulteriori informazioni, vedere [Aggiungere aule in Adobe Learning Manager](/help/migrated/administrators/feature-summary/classroom.md).

## Report

Questa sezione consente di configurare i dashboard Conformità e Gruppi riusciti.

![testo alternativo](assets/advanced-settings-picture2.png)

Per ulteriori informazioni, consultate i seguenti riferimenti:

* [Dashboard di conformità](/help/migrated/administrators/feature-summary/reports.md#compliance-dashboard)
* [Dashboard di Group Success](/help/migrated/administrators/feature-summary/group-success-dashboard.md)


