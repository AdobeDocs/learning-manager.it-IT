---
description: Gli amministratori possono avviare una sessione impersonata, vale a dire una sessione in cui possono accedere nel proprio account per conto di qualsiasi utente nei ruoli Allievo e Manager.
jcr-language: en_us
title: Impersonificazione dell’Allievo e del Manager
contentowner: saghosh
exl-id: 0306f255-283f-43b9-9494-11b3dc3765da
source-git-commit: ba0c87447755729cd98cea1d40083e05f2159f37
workflow-type: tm+mt
source-wordcount: '547'
ht-degree: 70%

---

# Impersonificazione dell’Allievo e del Manager {#impersonation-of-learner-and-manager}

Nelle grandi organizzazioni, il personale dell’assistenza clienti necessita della capacità di impersonificazione per risolvere i problemi riscontrati dagli Allievi.

Grazie a questa capacità di impersonare altri utenti, gli Amministratori e gli Amministratori personalizzati possono identificare ed eseguire tutte le attività svolte da Allievi e Manager della propria organizzazione.

## Come funziona

Gli Amministratori (e/o gli Amministratori personalizzati) possono cercare un utente (interno o esterno) e quindi impersonarlo. L’Amministratore viene quindi reindirizzato alla pagina dell’utente (se applicabile, app di gestione o altra app per Allievi) e disconnesso dalla propria sessione. L’Amministratore viene poi reindirizzato alla pagina Completa il tuo profilo, nel caso in cui questa sia impostata per l’utente che è stato impersonato dall’Amministratore.

Se un Amministratore personalizzato dispone dell’autorizzazione per accedere alla pagina di un utente, può cercare gli utenti che desidera rappresentare.

Ecco cosa devi tenere a mente quando impersoni un utente:

* Tutti gli amministratori visualizzano questa funzione per impostazione predefinita.
* Possono essere impersonati solo gli utenti attivi nell’account.
* Un Amministratore non può impersonare se stesso.
* Un Amministratore personalizzato che ha accesso alla pagina Utenti può impersonare gli utenti.
* Un Amministratore/Amministratore personalizzato può impersonare un altro utente solo per 60 minuti.
* Un amministratore personalizzato con accesso di sola lettura non può rappresentare gli utenti.

## Impersonare un utente

Per impersonare un utente, esegui le operazioni descritte di seguito:

1. Accedi all’app come amministratore.
1. Seleziona Profilo > Impersona utente.

   Puoi impersonare un solo utente alla volta.

1. Cerca un utente (interno/esterno) nella casella di ricerca presente nella finestra di dialogo modale. Puoi impersonare un solo utente alla volta. Seleziona Procedi.

   Puoi anche eseguire ricerche tramite e-mail utente, UUID e così via.

1. Viene visualizzato un messaggio con la conferma che impersonerai un utente.

   Seleziona Procedi.

   Un messaggio di conferma, &quot;Modalità di rappresentazione: Hai effettuato l’accesso come &quot;nome utente (e-mail utente)&quot;. Disconnetti&quot; viene visualizzato nell&#39;intestazione della pagina.

**Una sessione impersonata dura 60 minuti.**

Quando si passa a un ruolo di Allievo o Manager, viene visualizzato un messaggio che indica che l’Amministratore/Amministratore personalizzato è in modalità di impersonificazione dell’utente.

## Report di accesso

Gli accessi e gli accessi di un Amministratore vengono acquisiti in un report di accesso. Per ogni utente che viene impersonato dall’Amministratore viene creato un record nel report.

Le colonne che fanno parte di questa funzione sono:

* Impersonato tramite nome utente
* Impersonato tramite e-mail utente

Queste colonne vengono aggiunte alla fine del report.

Nel report, ogni accesso viene conteggiato separatamente.

## Cosa non è supportato

* Impersonificazione dei componenti AEM.
* Impersonificazione nell’app mobile.
* Impersonificazione in ambiente mobile immersivo.
* Impersonificazione di app immersive. È applicabile solo alle applicazioni ALM.

## Domande frequenti

+++È possibile accedere a Adobe Learning Manager anche durante la rappresentazione?

Sì, l’accesso di un utente è indipendente dall’impersonificazione.
+++

+++Gli eventi di rappresentazione vengono conteggiati in modo univoco?

Sì, ogni accesso/visita da parte dell’amministratore durante l’impersonificazione verrà conteggiato/a separatamente.
+++

+++Qual è il timeout dell’impersonificazione?

60 minuti. Se un utente che esegue l’impersonificazione chiude la finestra del browser e passa a un URL principale entro 60 minuti, l&#39;attività di impersonificazione continua e il messaggio del banner deve essere visualizzato.
+++
