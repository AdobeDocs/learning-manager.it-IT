---
description: Registra il server MCP di Adobe Learning Manager come connettore nel client di intelligenza artificiale aziendale, in modo che gli Allievi dell’organizzazione possano connettersi ed eseguire query sul loro apprendimento.
jcr-language: en_us
title: Aggiungere Adobe Learning Manager al client di intelligenza artificiale aziendale
exl-id: d893efb7-dc0d-4a3a-88d6-b315340e5daa
source-git-commit: 89aa1b5ab02eed8a61507ab162fcbbd384e6c5fc
workflow-type: tm+mt
source-wordcount: '215'
ht-degree: 0%
---

# Aggiungere Adobe Learning Manager al client di intelligenza artificiale aziendale

## Panoramica

Sono necessari privilegi di amministratore nel client AI. Prima di iniziare, ottenere l&#39;URL dell&#39;endpoint MCP, l&#39;ID client e la chiave privata dall&#39;amministratore di Adobe Learning Manager. Ulteriori informazioni sulla [configurazione di un server di protocollo di contesto del modello](/help/migrated/administrators/feature-summary/configure-mcp-admin.md).

## Aggiungere il connettore

1. Accedi al tuo client di intelligenza artificiale aziendale come Amministratore.
2. Apri le impostazioni Amministratore per i connettori.
3. Aggiungere un connettore personalizzato che utilizza il protocollo di contesto del modello.
4. Immettere l&#39;URL dell&#39;endpoint MCP di Adobe Learning Manager.
5. Immetti l’ID client e la chiave privata dell’amministratore Adobe Learning Manager.
6. Salva il connettore.
7. Rendi il connettore disponibile agli Allievi.

>[!NOTE]
>
>Le interfacce client basate su IA cambiano frequentemente. Se questi passaggi non corrispondono al tuo client, consulta la documentazione del fornitore del client AI per l&#39;aggiunta di un connettore remoto.

## Risoluzione dei problemi

**Gli Allievi non visualizzano il connettore.**
Verifica che il connettore sia abilitato per l’area di lavoro o il gruppo dell’Allievo.

**L’autorizzazione non riesce quando un Allievo seleziona Connetti.**
Verificare che l&#39;ID client e la chiave privata corrispondano ai valori nella pagina **Credenziali client** del server in Adobe Learning Manager.
