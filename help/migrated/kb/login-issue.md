---
jcr-language: en_us
title: Problemi di accesso in Learning Manager
description: Problemi di accesso nell’Adobe di Learning Manager
contentowner: nluke
source-git-commit: ec79aa3dd6225cc424721afb50702963c1b125eb
workflow-type: tm+mt
source-wordcount: '236'
ht-degree: 0%

---



# Problemi di accesso in Learning Manager

## Problema

Impossibile accedere all’Adobe Learning Manager.

## Errore

Durante il tentativo di accesso all’Adobe Learning Manager, viene visualizzato il messaggio di errore riportato di seguito:

![](assets/cp-error.png)

*Messaggio di errore per una sessione scaduta*

## Motivo

Quando un utente accede tramite SSO, crea un cookie di sessione che viene archiviato nel browser. Consente inoltre all&#39;utente di accedere ad altre applicazioni. La maggior parte degli SSO è configurata per la disconnessione dopo 24 ore. L’utente deve autenticarsi di nuovo per una nuova sessione.

In alcuni casi, un utente non è in grado di accedere al sistema a causa di cookie SSO non aggiornati. Questi cookie vengono inoltrati ad Adobe Learning Manager per l’autenticazione. La sessione non termina se un utente non chiude il browser per molto tempo o non si è disconnesso.

Adobe Learning Manager rifiuta questi cookie non aggiornati, con conseguente errore.

## Risoluzione

Se un cookie non aggiornato viene rifiutato da un Adobe di Learning Manager, prova le opzioni seguenti:

1. Cancella i cookie e la cache del browser. Per ulteriori informazioni, consulta questo articolo [documento](unable-log-in-learning-manager.md).

   In alternativa, l’Amministratore IDP può definire una disconnessione forzata dopo un determinato periodo di tempo impostato. Questo passaggio consente di autenticare nuovamente l&#39;utente per iniziare una nuova sessione.

Ci sono altri motivi per cui si verifica questo errore, ma quello precedente è uno scenario comune.

## Collegamenti di riferimento:

[Microsoft: sessione di accesso condizionale nel corso della vita](https://docs.microsoft.com/en-us/azure/active-directory/conditional-access/howto-conditional-access-session-lifetime)
