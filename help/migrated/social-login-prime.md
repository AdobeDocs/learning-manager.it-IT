---
jcr-language: en_us
title: Accesso social in Learning Manager
description: Accesso social in Learning Manager
contentowner: saghosh
preview: true
source-git-commit: ccdb222228f76fdae63ebb0a808824ad6ac1db7f
workflow-type: tm+mt
source-wordcount: '100'
ht-degree: 0%

---



# Accesso social in Learning Manager

Puoi utilizzare Facebook, LinkedIn o le credenziali di Twitter per accedere a Learning Manager.

## Configurazione dell’accesso social {#setupsociallogin}

1. Contatta il tuo Customer Success Manager per configurare l&#39;account.

   In caso contrario, segui i passaggi riportati di seguito.

1. Cerca l&#39;account in cui desideri configurare l&#39;accesso social.
1. Modifica l’accesso in SSO.
1. Fare clic su Avanzate. Specifica il seguente codice JSON.

   ```
   \{"linkedIn":true,"microsoft":true,"twitter":true,"facebook":true,"editingAllowed":true
   ```

   Se si tratta di un JSON errato, ci sarà un’eccezione.

   Questa funzione di accesso social viene utilizzata solo per gli utenti INTERNI.

