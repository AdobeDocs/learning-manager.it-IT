---
title: Creare un corso con un browser per esami sicuro
description: Creare un quiz con la modalità Browser esami sicuro e aggiungerlo a un corso come modulo di autoapprendimento in Adobe Learning Manager per fornire un ambiente di valutazione limitato.
source-git-commit: 8f23f95cd81e5b64932281c990d27be0c390850b
workflow-type: tm+mt
source-wordcount: '551'
ht-degree: 0%
---

# Creare un corso con un browser per esami sicuro

Gli Autori possono aggiungere quiz ai corsi che richiedono un browser per esami sicuro per fornire un ambiente di valutazione protetto e limitato. Il browser per esami sicuri si applica solo a singoli quiz Adobe Learning Manager nativi e non limita l’accesso ad altri moduli del corso.

Prima di aggiungere il quiz a un corso, assicurati che il browser degli esami sicuri sia abilitato per il quiz. Se il corso include altri tipi di distribuzione, come i moduli aula virtuale, tali moduli continuano a funzionare indipendentemente dal requisito del browser per esami sicuri.

Questo articolo spiega come aggiungere un quiz con il browser per esami sicuri a un corso e configurarne le impostazioni per il corso.

## Creare un quiz con la modalità Browser per esami sicuri

La modalità Browser esami sicuro determina se gli Allievi devono utilizzare il Browser esami sicuro per sostenere il quiz. L’opzione viene visualizzata solo dopo che un Amministratore ha abilitato l’integrazione del browser per esami sicuri per l’account. Per ulteriori informazioni, visualizzare **Abilita browser per esami sicuri**.

Per creare un quiz con la modalità Browser per esami sicuri:

1. Accedi ad ALM come Autore.
1. Selezionare **Crea contenuto**.

   Viene visualizzata la pagina **Libreria dei contenuti**.

1. Seleziona **Aggiungi** > **Quiz**.

   Viene aperta la pagina **Crea quiz**.

1. Immetti un nome per il quiz nel campo **Nome**.
1. (Facoltativo) Inserite una descrizione per il quiz nel campo Descrizione.
1. Seleziona **Aggiungi domanda per quiz** e aggiungi i **criteri di superamento**.
1. Abilita **modalità Browser esami sicuri**. Viene visualizzata l’opzione **Consenti all’autore di personalizzare durante la creazione del corso**.

   ![Impostazione della modalità Browser esami sicuro nella pagina Crea quiz](assets/quiz-safe-exam-browser-mode-setting.png "Impostazione della modalità Browser esami sicuro nella pagina Crea quiz")

1. (Facoltativo) Abilita **Consenti all&#39;autore di personalizzare durante la creazione del corso**.

   L’opzione Browser esami sicuri viene visualizzata quando configuri il codice del corso.

   >[!NOTE]
   >
   > Se l’Amministratore abilita questa opzione, puoi abilitare o disabilitare il requisito del browser per esami sicuri (SEB) per un modulo del quiz sul corso. Se l’Amministratore disattiva questa opzione, SEB diventa obbligatorio per il quiz e non è possibile modificare questo requisito. Per ulteriori informazioni, vedere [Abilitare l&#39;integrazione del browser per esami sicuri](../../administrators/feature-summary/safe-exam-browser.md#enable-safe-exam-browser-integration).

1. Seleziona **Publish**.

## Aggiunta di un quiz con il browser per esami sicuri a un corso

Aggiungere il quiz come modulo autonomo per richiedere un browser per esami sicuro per tale valutazione. Prima di iniziare, assicurati che il quiz sia pubblicato con l’opzione Browser esami sicuro abilitata. Per ulteriori informazioni, consulta Abilitare un browser per esami sicuro.

Per aggiungere il quiz a un corso:

1. Seleziona **Crea corso** e immetti il nome e la descrizione del corso.
1. Selezionare **Aggiungi moduli** dalla pagina **Moduli**.

   Viene visualizzata la finestra a comparsa Moduli.

1. Seleziona **Apprendimento autonomo**. Viene visualizzata la finestra di dialogo **Modulo autonomo**.

   ![Finestra di dialogo Modulo a ritmo personalizzato che elenca i moduli quiz disponibili](assets/self-paced-module-dialog-quiz-selection.png "Finestra di dialogo Modulo a ritmo personalizzato che elenca i moduli quiz disponibili")

1. Seleziona la casella di controllo accanto al quiz del browser per esami sicuri che hai creato.
1. Seleziona **Aggiungi**. Il quiz viene aggiunto al corso come modulo di autoapprendimento.
1. (Facoltativo) Per aggiungere un altro tipo di recapito al corso, selezionare **Aggiungi altri tipi di recapito** e configurare il modulo richiesto.
1. Seleziona **Salva** > **Publish**.

   Il corso ora include una valutazione che richiede agli Allievi di utilizzare il browser degli esami sicuro.

Visualizza [Avvia un quiz nel browser per esami sicuri](../../learners/feature-summary/launch-safe-exam-browser.md) per scoprire come gli Allievi possono accedere e rispondere ai quiz utilizzando il browser per esami sicuri.
