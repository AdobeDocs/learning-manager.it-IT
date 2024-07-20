---
jcr-language: en_us
title: Non è possibile ottenere un’abilità dopo aver completato un corso
description: Un Allievo, anche dopo aver completato un corso, non ottiene un’abilità. Le abilità dell’Allievo assegnate a tale corso rimangono sullo stato In corso.
contentowner: nluke
exl-id: d9c1e2a2-351d-4d6f-b2e6-f9e9278e6523
source-git-commit: a0c01c0d691429bd66a3a2ce4cfc175ad0703157
workflow-type: tm+mt
source-wordcount: '258'
ht-degree: 52%

---

# Non è possibile ottenere un’abilità dopo aver completato un corso

## Il problema

Un Allievo, anche dopo aver completato un corso, non ottiene un’abilità. Le abilità dell’Allievo assegnate a tale corso rimangono **In corso**.

## Causa

Questo problema si verifica se i **crediti richiesti** per raggiungere questa abilità sono maggiori dei **crediti guadagnati** dall&#39;Allievo dopo aver completato il corso.

## Soluzione

Controlla le **credenziali delle abilità** e le **informazioni richieste** per ottenere l&#39;abilità. Effettua le seguenti operazioni:

1. Per l’Allievo, genera un report riguardante la **Trascrizione Allievo**.
1. Durante la generazione della Trascrizione Allievo, fai clic su **[!UICONTROL Opzioni avanzate]** e seleziona l’opzione **[!UICONTROL Includi dati sulle abilità e fogli di riepilogo]**.

   ![](assets/advanced-options.png)

   *Selezionare l&#39;opzione Includi dati sulle abilità e fogli di riepilogo*

1. Apri il report Trascrizione Allievo scaricato.
1. Vai al foglio **[!UICONTROL Trascrizione abilità]**. Qui puoi visualizzare i **[!UICONTROL crediti richiesti]** e i **[!UICONTROL crediti guadagnati]** dall’Allievo.

   Nell’esempio seguente, i crediti richiesti per guadagnare l’abilità per un corso sono 50, ma l’Allievo ha ottenuto un solo credito.

   ![](assets/skill-transcript.png)

   *Visualizza i crediti richiesti*

1. Per verificare i crediti assegnati a una determinata abilità, accedi come amministratore e vai alla scheda **Abilità**, come illustrato di seguito:

   ![](assets/skill.png)

   *Scheda Avvia abilità*

1. Per verificare il numero di crediti assegnati a un corso, accedi come autore e apri il corso. Fai clic su **[!UICONTROL Impostazioni]** > **Abilità corso** come illustrato di seguito:

   ![](assets/course-skills.png)

   *Visualizza Abilità Corso*
