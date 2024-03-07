---
jcr-language: en_us
title: Mappare abilità con domini di abilità
description: Per fare in modo che il motore di cura basato su intelligenza artificiale esegua la cura automatica di un post pubblicato da un utente per un particolare dominio di abilità, l’azienda dell’utente deve disporre delle proprie abilità personalizzate da mappare ai domini di abilità supportati presenti in LMS di Learning Manager.
contentowner: kuppan
source-git-commit: b24771ced8788a906af021b45204925fe43eb7e7
workflow-type: tm+mt
source-wordcount: '373'
ht-degree: 90%

---



# Mappare abilità con domini di abilità

Per fare in modo che il motore di cura basato su intelligenza artificiale esegua la cura automatica di un post pubblicato da un utente per un particolare dominio di abilità, l’azienda dell’utente deve disporre delle proprie abilità personalizzate da mappare ai domini di abilità supportati presenti in LMS di Learning Manager.

Durante la creazione di un’abilità, un Amministratore può mapparla ai domini di abilità più rilevanti supportati da Learning Manager. Ciò verrà ulteriormente considerato durante il processo di cura automatica. LMS di Learning Manager elenca le seguenti abilità:

* Gestione della catena di distribuzione
* Contabilità
* Ricerca scientifica e progettazione
* Sicurezza del computer
* Gestione strategica
* Social media
* Medicina
* Finanza
* Sicurezza sul lavoro
* Abilità soft
* Diritto aziendale
* Management
* Gestione delle risorse umane
* Comunicazione tecnica
* Etica aziendale
* Gestione delle relazioni con i clienti
* Tecnologia dell’informazione
* Produzione
* Marketing
* Gestione della qualità
* Processi aziendali
* Apprendimento
* Design
* Analisi
* Vendite

>[!NOTE]
>
>Secondo l&#39;algoritmo, se il punteggio di confidenza è inferiore al 50%, il contenuto è contrassegnato per la cura manuale.


Per aggiungere un dominio di abilità, procedi nel modo seguente:

1. Nel riquadro sinistro dell’app di amministrazione, fai clic su **[!UICONTROL Abilità]**.
1. Per aggiungere un’abilità, fai clic su **[!UICONTROL Aggiungi]** nell’angolo superiore destro della pagina.
1. Nella finestra di dialogo **[!UICONTROL Aggiungi abilità]**, aggiungi un’abilità e una descrizione dell’abilità.
1. Nella sezione **[!UICONTROL Dominio abilità]**, aggiungi i domini di abilità. I domini vengono aggiunti quando li inserisci. Questi domini sono popolati dalla lista sopramenzionata.

   ![](assets/skill-domain-mapping.png)

   *Aggiungere i domini di abilità nella sezione Dominio di abilità*

1. Per salvare le modifiche, fai clic su **[!UICONTROL Salva]**.

Quando un utente pubblica un contenuto su una bacheca, il contenuto viene sottoposto a cura e viene approvato o rifiutato a seconda del suo punteggio di confidenza rispetto all’abilità mappata alla bacheca.

<!--![](assets/content-uploaded.png)-->

Se il contenuto da caricare ha un punteggio di confidenza superiore al 50%, il contenuto viene caricato sulla bacheca. Se i tuoi contenuti soddisfano i criteri, vedrai una notifica che conferma che la cura del contenuto è avvenuta correttamente e che esso è disponibile sulla bacheca.

![](assets/curation-notification.png)

*Visualizza le notifiche in base al punteggio di confidenza*

