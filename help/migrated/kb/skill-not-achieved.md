---
jcr-language: en_us
title: Impossibile raggiungere un’abilità dopo aver completato un corso
description: Un Allievo, anche dopo aver completato un corso, non ottiene un’abilità. Le abilità dell’Allievo assegnate a tale corso rimangono sullo stato In corso.
contentowner: nluke
source-git-commit: 6abc118c6ad7e66e3ded5bd26b9167c3a0b99e4b
workflow-type: tm+mt
source-wordcount: '258'
ht-degree: 0%

---



# Impossibile raggiungere un’abilità dopo aver completato un corso

## Problema

Un Allievo, anche dopo aver completato un corso, non ottiene un’abilità. Le abilità assegnate a tale corso rimangono **In corso** per l’allievo.

## Causa

Questo problema si verifica se **Crediti richiesti** per raggiungere questa abilità è maggiore del **Crediti guadagnati** dall’Allievo dopo aver completato il corso.

## Soluzione

Controlla la **Crediti abilità** e **Punto** informazioni necessarie per raggiungere l’abilità. Segui i passaggi riportati di seguito:

1. Per l’Allievo, genera un **Trascrizione Allievo** rapporto.
1. Durante la generazione della Trascrizione Allievo, fai clic su **[!UICONTROL Opzioni avanzate]** e seleziona l’opzione **[!UICONTROL Includi dati sulle abilità e fogli di riepilogo]**.

   ![](assets/advanced-options.png)

   *Seleziona l’opzione Includi dati sulle abilità e fogli di riepilogo*

1. Apri il report Trascrizione Allievo scaricato.
1. Passare alla **[!UICONTROL Trascrizione abilità]** lenzuola. Qui è possibile visualizzare **[!UICONTROL Crediti richiesti]** e **[!UICONTROL Crediti guadagnati]** dall’Allievo.

   Ad esempio, nell’esempio seguente, i crediti richiesti per raggiungere l’abilità per un corso sono 50. Tuttavia, l’Allievo ha ottenuto un solo credito.

   ![](assets/skill-transcript.png)

   *Visualizzare i crediti richiesti*

1. Per verificare i crediti assegnati a una determinata abilità, accedi come Amministratore e passa a **Abilità** come illustrato di seguito:

   ![](assets/skill.png)

   *Scheda Avvia abilità*

1. Per verificare il numero di crediti assegnati a un corso, accedi come Autore e apri il corso. Fai clic **[!UICONTROL Impostazioni]** > **Abilità del corso** come illustrato di seguito:

   ![](assets/course-skills.png)

   *Visualizza abilità corso*
