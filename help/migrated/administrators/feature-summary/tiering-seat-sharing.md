---
description: In che modo i piani di fatturazione determinano se gli account possono condividere postazioni con licenza e cosa accade alle relazioni di condivisione quando un piano cambia
jcr-language: en_us
title: Livelli - Condivisione dei posti
exl-id: 42b4cba4-1e44-40d8-aa57-ce2a855be258
source-git-commit: 34d4e6fb6583eed0dd3a46126c28284c58210078
workflow-type: tm+mt
source-wordcount: '547'
ht-degree: 0%
---

# Condivisione di postazioni e piani dell’account in Adobe Learning Manager

La condivisione di postazioni consente a un account di condividere una parte delle postazioni con licenza con un altro account, in modo che gli Allievi nell’account di ricezione possano accedere a Adobe Learning Manager utilizzando le postazioni dall’account di condivisione. Quali account possono condividere postazioni e con chi dipende dal piano di fatturazione di ciascun account.

## Quali piani supportano la condivisione delle postazioni?

La condivisione di postazioni è disponibile per gli account nel piano **Ultimate**. Gli account del piano **Prime** non possono condividere postazioni con un altro account e non possono ricevere postazioni condivise da un altro account.

Gli account fatturati con carta di credito sono inclusi nel piano Prime per impostazione predefinita e non possono quindi partecipare alla condivisione dei posti.

Gli account di prova sono un’eccezione: un account di prova può ricevere postazioni condivise da un account Ultimate. Quando esiste una relazione di condivisione attiva, l’account di prova può accedere alle funzioni di livello Ultimate.

## Account condivisi tra pari che impostano la visibilità

L’impostazione dell’account condiviso tra pari sarà visibile nell’app per amministratori dell’account che condivide questa funzione.

>[!NOTE]
>
>Se il tuo account condivide postazioni con account aggiuntivi oltre a quello da cui ricevi postazioni, ad esempio, se il tuo account passa l&#39;accesso condiviso a un terzo account, ogni account in quella catena deve essere nel piano Ultimate per la condivisione per continuare a lavorare end-to-end.

## Combinazioni di account che supportano la condivisione di postazioni

La tabella seguente mostra se la condivisione delle postazioni è possibile tra diverse combinazioni di piani account.

| Condivisione dell’account (principale) | Conto di ricezione (secondario) | Condivisione supportata? |
|---|---|---|
| Prime (qualsiasi) | Qualsiasi | No, la condivisione della sede è limitata agli account del piano Ultimate |
| Ultimate | Ultimate | Sì |
| Ultimate | l’applicazione Prime | No, piano non corrispondente |
| Ultimate | Un account fatturato con carta di credito | No, piano non corrispondente, poiché gli account fatturati con carta di credito fanno parte del piano Prime |
| Ultimate | Versione di prova | Sì, l’account di prova ottiene l’accesso di livello Ultimate mentre la relazione è attiva |

>[!NOTE]
>
>Alcune restrizioni aggiuntive sulla condivisione delle postazioni tra specifiche configurazioni dell’account possono essere applicate indipendentemente dal tipo di piano, ad esempio, in base a come è stato originariamente configurato l’abbonamento di un account. Se non riesci a stabilire una relazione di condivisione tra due account Ultimate, contatta il supporto di Adobe per confermare la configurazione dell’account.

## Cosa succede alla condivisione delle postazioni quando cambia un piano

L&#39;idoneità alla condivisione dei posti viene valutata al momento del rinnovo. Se il piano di un account cambia in modo che influisce su una relazione di condivisione esistente, si verifica quanto segue:

* Se il piano di un account (principale) che condivide il progetto cambia da Ultimate a Prime al momento del rinnovo, le relazioni esistenti per la condivisione del posto terminano.
* Se l’account ricevente ha un proprio abbonamento indipendente, tale abbonamento non è interessato; termina solo la relazione di condivisione.
* Se l’account ricevente era un account di prova che si basa sull’accesso Ultimate dell’account principale, tornerà all’accesso di livello Prime una volta terminata la relazione di condivisione.

Queste modifiche hanno effetto al prossimo rinnovo dell&#39;account per gli account ALM esistenti, non immediatamente durante una durata contrattuale attiva. Tuttavia, non sono applicabili ai nuovi account creati dopo l’attivazione della funzionalità di suddivisione in livelli.

>[!NOTE]
>
>Gli account fatturati tramite carta di credito che attualmente dispongono di accesso di livello Ultimate verranno spostati nel piano Prime a partire dal loro prossimo rinnovo. Se a quel punto un account di questo tipo ha relazioni attive con la condivisione del posto, tali relazioni terminano come parte della stessa transizione.
