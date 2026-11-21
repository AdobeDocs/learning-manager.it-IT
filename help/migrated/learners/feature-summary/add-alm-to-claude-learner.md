---
description: Aggiungi il server Adobe Learning Manager al tuo account Claude come connettore personalizzato, accedi e chiedi informazioni sul tuo apprendimento
jcr-language: en_us
title: Aggiungi Adobe Learning Manager a Claude come Allievo
exl-id: 31c00b29-4919-48b7-9993-ed3ac358ba5e
source-git-commit: 05691364449234a4782e2de5d4752c7b277f5fd4
workflow-type: tm+mt
source-wordcount: '399'
ht-degree: 0%
---

# Aggiungi Adobe Learning Manager a Claude come Allievo

Utilizza questi passaggi solo se la tua organizzazione non ha già aggiunto il connettore per te. Se in Claude viene visualizzato un connettore Adobe Learning Manager, seleziona invece **Connetti**.

## Aggiungere il connettore in Claude

1. In Claude, vai a **Personalizza** \> **Connettori**.
2. Seleziona **Aggiungi** (**+**), quindi seleziona **Aggiungi connettore personalizzato**.
3. Immetti un **Nome**, ad esempio Adobe Learning Manager.
4. Immettere l&#39;URL dell&#39;endpoint MCP in **URL server MCP remoto**.
5. Selezionare **Continua**.
6. In **Autenticazione**, mantieni **Accedi ora**.
7. In **client OAuth**, seleziona **Usa il tuo client OAuth**.
8. Immettere l&#39;ID client in **ID client**.
9. Immetti la chiave segreta in **Segreto client**.
10. Seleziona **Aggiungi**.
11. Accedi a Adobe Learning Manager quando viene aperta la pagina di accesso.

Dopo aver effettuato l’accesso, il connettore viene visualizzato come connesso. Fai una domanda sul tuo apprendimento. Per le idee, visualizza **suggerimenti di esempio per gli Allievi**.

>[!IMPORTANT]
>
>Claude etichetta il campo Segreto client come facoltativo, ma Adobe Learning Manager lo richiede. Se lo lasci vuoto o immetti un valore errato, l’accesso non riesce e viene visualizzato il messaggio &quot;Autorizzazione non riuscita&quot;.

>[!NOTE]
>
>Le tue richieste vengono eseguite con le tue autorizzazioni. Claude riesce a vedere solo ciò che puoi vedere in Adobe Learning Manager.

## Usa un account Adobe Learning Manager diverso

Se il tuo browser ha già una sessione Adobe Learning Manager attiva, Claude si connette a quell&#39;account senza chiedere le credenziali. Per connetterti come un altro utente, esci prima da Adobe Learning Manager o usa una finestra privata del browser.

## Altri clienti IA

Per ChatGPT o un altro client, i passaggi sono diversi. Consulta la documentazione del client AI per aggiungere un connettore personalizzato e utilizza gli stessi tre valori del tuo amministratore.

## Risoluzione dei problemi

**L&#39;accesso mostra un messaggio di reindirizzamento non registrato.** L&#39;amministratore deve aggiungere il dominio Claude a **Domini di reindirizzamento** per il server. Chiedi all&#39;amministratore di aggiungere <https://claude.ai> e riprova.

**Claude indica che l&#39;autorizzazione non è riuscita.** Controlla la chiave segreta per verificare la presenza di spazi aggiuntivi o un valore errato. Copialo di nuovo dall&#39;amministratore, rimuovi il connettore e aggiungilo di nuovo.

**Connessione come utente errato.** Scollega il connettore, esci da Adobe Learning Manager e riconnettiti in una finestra privata del browser.

**Claude ti chiede di accedere nuovamente.** Sessione scaduta o accesso revocato. Seleziona **Connetti** per accedere di nuovo.
