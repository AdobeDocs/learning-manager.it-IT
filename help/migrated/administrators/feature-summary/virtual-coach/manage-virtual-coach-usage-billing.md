---
description: Scopri come gli amministratori di Learning Manager attivano l’istruzione virtuale, monitorano l’utilizzo dei crediti MAU e scaricano i report sulle prestazioni degli Allievi
jcr-language: en_us
title: Gestire l’utilizzo e la fatturazione degli allenatori virtuali
exl-id: 1f8f6465-51c3-4670-a1c7-9a7dfb091452
product_v2:
  - id: ed12e5b7-96e3-45e7-a17f-de222065ebcb
    internal-label: Learning Manager
source-git-commit: c061ccbefe8d40154220587796062d335e35de77
workflow-type: tm+mt
source-wordcount: '584'
ht-degree: 0%
---

# Gestire l’utilizzo e la fatturazione degli allenatori virtuali

Attiva l’istruttore virtuale, monitora il consumo di crediti degli utenti attivi mensili (MAU) e scarica i report sulle prestazioni degli Allievi come amministratore Adobe Learning Manager.

## Attiva l’istruttore virtuale per il tuo account {#activatevirtualcoach}

Virtual Coach è disponibile come componente aggiuntivo di Adobe Learning Manager. Dopo l&#39;acquisto, il provisioning genera una chiave di attivazione che viene inviata tramite e-mail all&#39;amministratore dell&#39;account.

1. Accedi a Adobe Learning Manager come amministratore.
2. Passa alla pagina **Fatturazione** dal riquadro di navigazione a sinistra.
3. Nella sezione **Allenatore virtuale**, immetti la chiave di attivazione ricevuta tramite e-mail.

   ![](/help/migrated/administrators/feature-summary/assets/virtual_coach12.png)
   *Immettere la chiave di attivazione nella sezione Allenamento virtuale della pagina Fatturazione per attivare la funzionalità.*

4. Selezionare **Applica**. L’istruzione virtuale è abilitata per il tuo account.

Una volta attivata, riceverai una notifica in-app per confermare che la funzione è attiva. Alla **Libreria dei contenuti** vengono aggiunti automaticamente quattro scenari di esempio per l&#39;esecuzione dei ruoli, in modo che gli autori possano iniziare immediatamente.

>[!NOTE]
>
>La chiave di attivazione viene generata automaticamente durante il provisioning e condivisa tramite e-mail. Se non disponi della chiave di attivazione, contatta il tuo Customer Success Manager Adobe Learning Manager.

## Visualizza saldo credito MAU

I crediti MAU (Monthly Active User) contano il numero di Allievi univoci che utilizzano l’Allenatore virtuale ogni mese.

1. Passa alla pagina **Fatturazione**.
2. Nella sezione **Allenatore virtuale**, seleziona **Visualizza dettagli utilizzo**.

   ![](/help/migrated/administrators/feature-summary/assets/virtual-coach22.png)

3. Utilizza l&#39;elenco a discesa **Seleziona periodo** per scegliere l&#39;intervallo di date da rivedere.

   La tabella **Utilizzo complessivo** mostra:

   - **Disponibile**: totale crediti MAU acquistati.
   - **Utilizzato**: crediti utilizzati fino ad oggi.
   - **Rimanenti**: crediti disponibili per il resto del periodo del contratto.

   La tabella **Utilizzo mensile** mostra il numero di allievi attivi univoci per mese di calendario.

   ![](/help/migrated/administrators/feature-summary/assets/virtual-coach23.png)

4. Selezionare **Scarica report dettagliato** per esportare i dati di utilizzo completi.

   ![](/help/migrated/administrators/feature-summary/assets/virtual-coach-report-mau-billing-5.png)

## Come vengono utilizzati i crediti MAU

Un credito MAU viene utilizzato quando un Allievo avvia una sessione di coach virtuale in un mese di calendario. Le sessioni aggiuntive dello stesso Allievo nello stesso mese non richiedono crediti aggiuntivi. I crediti inutilizzati alla fine del periodo contrattuale scadono e non vengono riportati.

| Scenario | MAU utilizzate |
|---|---|
| Un Allievo completa 5 sessioni a gennaio | 1 |
| Lo stesso Allievo utilizza l’Allenatore virtuale sia in gennaio che in febbraio | 2 (1 al mese) |
| 100 Allievi completano 1 sessione a gennaio | 100 |

*I crediti MAU vengono conteggiati per Allievo univoco al mese, indipendentemente dal numero di sessioni avviate da ogni Allievo.*

**Esempio: Allievo singolo, più sessioni.** Sarah lancia cinque sessioni di Virtual Coach in gennaio. Viene contata come un singolo utente univoco per il mese, quindi 1 MAU viene consumato indipendentemente dal numero di volte che si esercita.

**Esempio: stesso Allievo, più mesi.** Sarah utilizza Virtual Coach sia in gennaio (3 sessioni) che in febbraio (2 sessioni). Ogni mese di calendario viene conteggiato separatamente, quindi vengono consumate 2 MAU: 1 per gennaio e 1 per febbraio.

**Esempio: più Allievi, stesso mese.** Ogni 100 agenti di vendita lancia una sessione Virtual Coach in gennaio. Ogni Allievo univoco conta come un MAU per quel mese, quindi vengono utilizzati 100 MAU.

**Esempio: esercitazione del team nel tempo.** Il tuo team di 50 persone utilizza Virtual Coach durante tutto l&#39;anno. In un mese in cui solo cinque delle 50 esercitazioni vengono seguite, per quel mese vengono utilizzate cinque MAU; in un mese in cui tutte le 50 esercitazioni vengono ripetute, vengono consumate altre 0 MAU oltre a quella già utilizzata per il rimpatrio degli Allievi in quel mese, poiché ogni Allievo viene conteggiato una sola volta al mese di calendario, indipendentemente dal numero di volte in cui si esercita al suo interno.

Per informazioni sui report degli allenatori virtuali, seleziona [Report degli allenatori virtuali](/help/migrated/administrators/feature-summary/virtual-coach/virtual-coach-reports.md).
