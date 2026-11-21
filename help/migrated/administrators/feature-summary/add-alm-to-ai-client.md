---
description: Aggiungi il server MCP di Adobe Learning Manager al client di intelligenza artificiale aziendale, ad esempio Claude o ChatGPT Enterprise, in modo che gli Allievi possano connettersi
jcr-language: en_us
title: Aggiungere Adobe Learning Manager al client di intelligenza artificiale aziendale
exl-id: d893efb7-dc0d-4a3a-88d6-b315340e5daa
source-git-commit: 05691364449234a4782e2de5d4752c7b277f5fd4
workflow-type: tm+mt
source-wordcount: '209'
ht-degree: 0%
---

# Aggiungere Adobe Learning Manager al client di intelligenza artificiale aziendale

Sono necessari privilegi di amministratore nel client AI. Ottieni prima l&#39;URL dell&#39;endpoint MCP, l&#39;ID client e la chiave segreta dall&#39;amministratore di Adobe Learning Manager. Per ulteriori informazioni, vedere **Configurare un server Model Context Protocol**.

## Aggiungere il connettore

1. Accedi al tuo client di intelligenza artificiale aziendale come amministratore.
2. Apri le impostazioni di amministratore per i connettori.
3. Aggiungere un connettore personalizzato che utilizza il protocollo di contesto del modello.
4. Immettere l&#39;URL dell&#39;endpoint MCP di Adobe Learning Manager.
5. Immetti l’ID client e la chiave privata dell’amministratore di Adobe Learning Manager.
6. Salva il connettore.
7. Rendi il connettore disponibile agli Allievi.

>[!NOTE]
>
>Le interfacce client basate su IA cambiano spesso. Se questi passaggi non corrispondono al tuo client, consulta la documentazione del fornitore del client AI per l&#39;aggiunta di un connettore remoto.

## Risoluzione dei problemi

**Gli Allievi non vedono il connettore.** Verifica che il connettore sia abilitato per l’area di lavoro o il gruppo dell’Allievo.

**L’autorizzazione non riesce quando un Allievo seleziona Connect.** Verificare che l&#39;ID client e la chiave privata corrispondano ai valori nella pagina **Credenziali client** del server in Adobe Learning Manager.
