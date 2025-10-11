---
title: Ruolo personalizzato con autorizzazioni di annuncio con ambito
jcr-language: en_us
description: Scopri come creare un ruolo personalizzato in Adobe Learning Manager che consenta gli annunci solo per cataloghi e gruppi di utenti selezionati.
source-git-commit: 85eeebb33a67bf5528c88b26941345e00e98e0d3
workflow-type: tm+mt
source-wordcount: '820'
ht-degree: 0%

---


# Ruolo personalizzato con autorizzazioni di annuncio con ambito

Gli amministratori possono creare ruoli personalizzati con autorizzazioni di annuncio limitate a cataloghi e gruppi di utenti specifici. In questo modo, gli annunci sono mirati, pertinenti e visibili solo agli Allievi interessati. Gli annunci con ambito garantiscono che gli utenti corretti ricevano annunci pertinenti senza inviare dettagli ad altri.

## Creare un ruolo personalizzato con un ambito specifico

L’amministratore può creare un ruolo personalizzato con autorizzazioni di annuncio limitate a un catalogo e a un gruppo di utenti specifici.

Per creare un ruolo personalizzato con un ambito specifico:

1. Accedi a Adobe Learning Manager come amministratore.
2. Seleziona **[!UICONTROL Utenti]** nel riquadro di navigazione a sinistra.

   ![](assets/select-uses-admin.png)
   _Assegnazione di ruoli personalizzati agli utenti per autorizzazioni e responsabilità di destinazione in Adobe Learning Manager_

3. Seleziona Ruoli personalizzati.
4. Seleziona Crea ruolo personalizzato.

   ![](assets/create-custom-roles.png)
   _Assegnare ruoli personalizzati agli utenti per personalizzare le autorizzazioni e semplificare il controllo amministrativo per gruppi di utenti o cataloghi specifici_

5. Digitare il nome e la descrizione del ruolo personalizzato.
6. Seleziona Annuncio in Privilegi account.

   ![](assets/select-announcement.png)
   _Abilitare le autorizzazioni di annuncio in Privilegi account per consentire agli amministratori personalizzati di gestire le comunicazioni di destinazione nell&#39;ambito_

7. Seleziona Imposta accesso per catalogo in Ambito per Privilegi di funzionalità e seleziona il catalogo.
8. Nella stessa sezione, scegli Imposta accesso per gruppo di utenti e seleziona il
gruppo di utenti.

   ![](assets/select-scope-announcement.png)
   _Impostare il gruppo di utenti e gli ambiti del catalogo per garantire che gli amministratori personalizzati possano gestire le autorizzazioni e l&#39;accesso solo all&#39;interno degli ambiti assegnati_

9. Selezionare e aggiungere l&#39;utente a cui si desidera assegnare questo ruolo personalizzato. Gli utenti assegnati possono creare un annuncio per il proprio ambito.

Un amministratore personalizzato può creare annunci limitati ai gruppi di utenti e ai cataloghi assegnati, garantendo che i messaggi raggiungano il pubblico corretto e impedendo notifiche non necessarie. Per gli annunci tramite notifica e e-mail, gli amministratori possono aggiungere ulteriori gruppi di utenti, ma solo gli utenti all’interno dell’ambito definito li riceveranno. Per gli annunci di tipo Consiglio e Titolo, è possibile selezionare solo gruppi di utenti all’interno dell’ambito assegnato.

## Crea annuncio per l&#39;ambito assegnato

Un amministratore personalizzato può creare annunci limitati ai gruppi di utenti e ai cataloghi assegnati, garantendo che i messaggi raggiungano il pubblico corretto e impedendo notifiche non necessarie.

Per creare un annuncio per l&#39;ambito assegnato:

1. Accedi a Adobe Learning Manager come amministratore personalizzato.
2. Seleziona **[!UICONTROL Annuncio]** nel riquadro di navigazione a sinistra.
3. Seleziona **[!UICONTROL Aggiungi]**.

   ![](/help/migrated/assets/create-add-announcement.png)
   _Pagina Annunci in Adobe Learning Manager, in cui gli amministratori possono creare e gestire gli annunci per i gruppi di utenti di destinazione_

4. Seleziona **[!UICONTROL Tipo di annuncio]** dal menu a discesa.
a. **[!UICONTROL Come notifica]**
b. **[!UICONTROL Come masthead]**
c. **[!UICONTROL Come consiglio]**
d. **[!UICONTROL Come e-mail]**
5. Seleziona **[!UICONTROL Come Masthead]**.
6. Seleziona la lingua e carica un&#39;immagine per il masthead.
7. Facoltativamente, puoi aggiungere un URL per il pulsante di azione.

   ![](/help/migrated/assets/announcement-screen.png)
   _Creare una schermata di annuncio che consente agli amministratori di impostare il tipo di annuncio, caricare allegati e aggiungere pulsanti di azione_

   L&#39;ambito assegnato è preselezionato nella sezione **[!UICONTROL Ambito]** e non può essere modificato dagli amministratori personalizzati.

   >[!NOTE]
   >
   >**[!UICONTROL Per gli annunci]** e **[!UICONTROL Email]** di Notification, possono includere ulteriori gruppi di utenti e cataloghi se questi si sovrappongono all&#39;ambito assegnato.

8. Seleziona **[!UICONTROL Salva]**.

Solo gli Allievi nell’ambito dell’Amministratore personalizzato potranno visualizzare l’annuncio. Per informazioni sulla creazione di più tipi di annunci, consulta questo [articolo](/help/migrated/administrators/feature-summary/announcements.md).

## Reimpostazione dell&#39;ambito da parte degli amministratori personalizzati

Gli amministratori personalizzati possono reimpostare l’ambito degli annunci pubblicati se un amministratore ne ha modificato l’ambito. Una volta reimpostato l’ambito, l’ambito aggiornato verrà applicato all’annuncio e solo gli Allievi che rientrano nel nuovo ambito potranno visualizzare l’annuncio.

Per reimpostare l&#39;ambito:

1. Accedi a Adobe Learning Manager come amministratore personalizzato.
2. Seleziona **[!UICONTROL Annuncio]** nel riquadro di navigazione a sinistra.
3. Seleziona la scheda **[!UICONTROL Pubblicato]**.
4. Seleziona un annuncio, quindi seleziona l’icona delle impostazioni.
5. Seleziona **[!UICONTROL Modifica]**.

   ![](/help/migrated/assets/select-edit-published-announcement.png)
   _Schermata dell&#39;annuncio che mostra gli annunci pubblicati con opzioni di modifica, pubblicazione e altre opzioni_

6. Selezionare **Ripristina**.

   ![](/help/migrated/assets/reset-the-scope.png)
   _Annuncio che mostra una notifica di modifica dell&#39;ambito, con un&#39;opzione che consente agli amministratori personalizzati di reimpostare e aggiornare la selezione dell&#39;ambito in base alle nuove autorizzazioni di accesso_

L’ambito verrà aggiornato e solo gli utenti all’interno dell’ambito aggiornato potranno visualizzare l’annuncio.

## Modifica l’annuncio tramite l’interfaccia utente dell’amministratore

Gli amministratori possono modificare e gestire tutti gli annunci creati dagli amministratori personalizzati. Se un amministratore tenta di modificare un annuncio creato da un amministratore personalizzato con un ambito specifico, nell&#39;annuncio verrà visualizzato un messaggio di avviso che indica **[!UICONTROL Rimuovi]** ambito. L’amministratore può rimuovere l’ambito per rendere l’annuncio disponibile a tutti. In questo caso, l’amministratore personalizzato riceverà un avviso di modifica dell’ambito dell’annuncio.

Per modificare l’annuncio tramite l’interfaccia utente dell’amministratore:

1. Accedi a Adobe Learning Manager come amministratore.
2. Seleziona **[!UICONTROL Annuncio]** nel riquadro di navigazione a sinistra.
3. Seleziona la scheda **[!UICONTROL Pubblicato]**.
4. Seleziona un annuncio, quindi seleziona l’icona delle impostazioni.
5. Seleziona **[!UICONTROL Modifica]**.

   ![](/help/migrated/assets/select-edit-published-announcement.png)
   _Schermata dell&#39;annuncio che mostra gli annunci pubblicati con opzioni di modifica, pubblicazione e altre opzioni_

6. Selezionare **[!UICONTROL Rimuovi]**.

   ![](/help/migrated/assets/remove-the-scope.png)
   _Schermata dell&#39;annuncio che indica che è necessario rimuovere l&#39;ambito per consentire agli amministratori di modificare gli annunci creati per gruppi di utenti con ambito_

L’Amministratore può modificare l’annuncio dopo aver rimosso l’ambito.
