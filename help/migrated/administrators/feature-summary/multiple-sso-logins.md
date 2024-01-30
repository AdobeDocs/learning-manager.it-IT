---
description: Adobe Learning Manager supporta più metodi di accesso tramite più configurazioni SSO per utenti interni ed esterni.
title: Accessi SSO multipli
contentowner: saghosh
source-git-commit: d59e748472c77527c22b286aea5412f776f6441b
workflow-type: tm+mt
source-wordcount: '782'
ht-degree: 39%

---


# Accessi SSO multipli {#multiple-sso-logins}

Un Amministratore può configurare più metodi di accesso per utenti interni ed esterni. Adobe Learning Manager supporta accessi SSO multipli per aiutare gli amministratori a configurare il metodo di accesso più adatto in base alle proprie esigenze e ai casi di utilizzo.

L’intento è consentire agli amministratori di configurare SSO diversi per i diversi gruppi di utenti in base a posizione, organizzazione e altri parametri.

È possibile aggiungere fino a 20 configurazioni SSO a un account. Queste possono essere utilizzate per configurare SSO per utenti interni ed esterni.

>[!NOTE]
>
>Quando attivi Multi-SSO, puoi scegliere i valori o i gruppi di utenti nel profilo di registrazione autonoma. Quando si sceglie un valore, viene creato un gruppo di utenti con zero utenti. Un gruppo di utenti di questo tipo non dispone di alcun utente. Quando il prossimo file CSV verrà importato, questo gruppo di utenti verrà rimosso.

## Abilita SSO multipli

Per abilitare SSO multipli, seleziona **Impostazioni** > **Metodi di accesso**.

Nella pagina di configurazione, seleziona la casella di controllo &quot;Abilita SSO multipli&quot; per gli utenti interni o esterni.

Quando Multi-SSO è abilitato, il metodo di accesso selezionato per &quot;Metodo di accesso predefinito&quot; diventa il tipo di accesso predefinito per gruppi di utenti/profili che non sono collegati a nessuna configurazione SSO. L’accesso predefinito può essere ID Adobe, SSO o ID ALM (utenti esterni).

Per configurare un SSO, segui i passaggi riportati di seguito:

1. Fai clic su Configura SSO.
1. Fai clic su Aggiungi nuova configurazione SSO.
1. Nella finestra di dialogo Configurazione SSO, aggiungi quanto riportato di seguito:

   * Inserisci il nome dell’SSO.
   * Seleziona il tipo di SSO: avviato da IDP o avviato da SP.

      * Se hai selezionato avviato IDP, immetti l&#39;URL IDP. Si tratta dell&#39;URL che sarà l&#39;identificatore univoco dell&#39;applicazione e delle informazioni fornite dal provider di servizi IDP. Questo è l’URL a cui verranno reindirizzati tutti gli utenti di Learning Manager Adobi dopo l’accesso.
      * Carica il file XML dei metadati IDP dal provider IDP. Questo file contiene informazioni sull’IdP che consente ad Adobe Learning Manager di accettare le asserzioni SAML da esso
      * Se hai selezionato avviato SP, immetti l&#39;ID entità. L’ID entità è un URL fornito dal provider di servizi (SP).
      * Immetti l&#39;URL di accesso dell’SP. Questo URL viene utilizzato dagli utenti per accedere all&#39;applicazione.

1. La configurazione SSO viene aggiunta all&#39;elenco.

## Configurazione di SSO per utenti interni

### Utenti da un file CSV

Effettua le seguenti operazioni:

1. Importa il file CSV contenente i campi attivi e i relativi valori.
1. Fai clic su Impostazioni > Metodi di accesso.
1. Seleziona la casella di controllo Abilita SSO multipli per l’accesso.
1. Associa le configurazioni SSO ai valori del campo attivo.
1. Salva le impostazioni. Importa nuovamente il file CSV.

### Singolo utente

Effettua le seguenti operazioni:

1. Fai clic su Impostazioni > Metodi di accesso.
1. Seleziona la casella di controllo Abilita SSO multipli per l’accesso.
1. Seleziona un campo attivo per un SSO.
1. Collega le configurazioni SSO ai valori del campo.
1. Salva le impostazioni. Aggiungi un singolo utente e assegna un valore al campo attivo.

### Utenti registrati autonomamente

Effettua le seguenti operazioni:

1. Fai clic su Impostazioni > Metodi di accesso.
1. Seleziona la casella di controllo Abilita SSO multipli per l’accesso.
1. Collega le configurazioni SSO ai valori del campo.
1. Salva le impostazioni. Aggiungi un singolo utente e assegna un valore al campo attivo.
1. Aggiungi un profilo di registrazione autonoma.
1. Seleziona un valore per il campo SSO configurato.

Dopo aver salvato le impostazioni del profilo, l’URL copiato reindirizza gli utenti all’SSO collegato al valore scelto per il profilo.

### Configurazione di SSO per utenti esterni

Effettua le seguenti operazioni:

1. Crea un profilo esterno.
1. Fai clic su Impostazioni > Metodi di accesso.
1. Seleziona la casella di controllo Abilita SSO multipli per l’accesso.
1. Collega la configurazione SSO al profilo esterno creato.
1. Salva le impostazioni.

Una volta salvate le impostazioni del profilo, l’URL del profilo esterno copiato reindirizzerà gli utenti all’SSO collegato al profilo.

## Domande frequenti

+++ Chi può abilitare più SSO per gli utenti?

Sia l’Amministratore che l’Amministratore personalizzato possono abilitare più SSO.
+++

+++È possibile utilizzare un campo attivo a valore singolo nuovo o esistente?

Sì, puoi utilizzare un campo attivo a valore singolo nuovo o esistente per configurare più SSO.
+++

+++Se in un file CSV sono presenti campi disattivati, la configurazione di più SSO avrà esito negativo?

No, questo non influirà sulla configurazione degli SSO. Gli utenti verranno reindirizzati a un SSO già configurato.
+++

+++Un amministratore può aggiungere nuovi valori al campo attivo della pagina durante la configurazione di Multi-SSO?

Sì, un amministratore può aggiungere nuovi valori ai campi attivi.
+++

+++Posso disattivare o eliminare i campi collegati a SSO?

Sì, puoi disabilitare o eliminare i campi collegati a SSO fino a quando non scolleghi i campi dalla pagina di configurazione SSO.
+++
