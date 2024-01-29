---
jcr-language: en_us
title: Il modulo risulta incompleto al termine del corso su Adobe Learning Manager
description: Il modulo risulta incompleto anche dopo che un Allievo ha completato un corso in Adobe Learning Manager.
contentowner: nluke
source-git-commit: ec79aa3dd6225cc424721afb50702963c1b125eb
workflow-type: tm+mt
source-wordcount: '191'
ht-degree: 0%

---



# Il modulo risulta incompleto al termine del corso su Adobe Learning Manager

## Problema

Il modulo risulta incompleto anche dopo che un Allievo ha completato un corso in Adobe Learning Manager.

## Causa

SCORM 2004 definisce i criteri di successo e di completamento e invia i due riepiloghi separatamente.

Ad esempio, prendiamo il caso di un set di contenuti **Criteri di completamento** di viste diapositiva 100% e **Criteri di successo** impostato come &quot;Quiz superato&quot;.

Un Allievo completa il corso ma non supera il quiz. In questo caso, il progresso è del 100%, ma il modulo risulta incompleto perché l’Allievo non soddisfa i requisiti **Criteri di successo**.

## Soluzione

Il problema riguarda la segnalazione **Preferenze** per il progetto. L’Autore deve verificare i criteri di completamento e di successo del corso.

Se sono necessarie modifiche, l’autore può effettuarle con uno strumento di authoring dei contenuti, ad esempio Adobe Captivate Classic. L’autore può quindi aggiornare il modulo di conseguenza.

![](assets/scorm.png)

*Visualizza Preferenze Di Report Captivate Classico*
