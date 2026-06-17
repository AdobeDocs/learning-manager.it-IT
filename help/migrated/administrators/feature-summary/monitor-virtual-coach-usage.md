---
jcr-language: en_us
title: Monitoraggio dell’utilizzo della Virtual Coach
description: Monitora l’utilizzo dell’istruttore virtuale da parte dell’account.
contentowner: mmanuel
source-git-commit: 87971737d1d9838d8b29035b5b9bf718742da1eb
workflow-type: tm+mt
source-wordcount: '726'
ht-degree: 2%

---


# Monitoraggio dell’utilizzo della Virtual Coach

Visualizza i dati sull’utilizzo degli istruttori virtuali, tieni traccia del consumo di crediti degli utenti attivi mensili (MAU) e accedi ai report sulle prestazioni degli Allievi in Adobe Learning Manager.

## Attiva l’istruttore virtuale per il tuo account

Virtual Coach è disponibile come componente aggiuntivo di Adobe Learning Manager. Dopo l’acquisto, il provisioning genera una chiave di attivazione che viene inviata tramite e-mail all’amministratore dell’account.

1. Accedi a Adobe Learning Manager come amministratore.
2. Passa alla pagina **Fatturazione** dal riquadro di navigazione a sinistra.
3. Nella sezione **Allenatore virtuale**, immetti la chiave di attivazione ricevuta tramite e-mail.
4. Selezionare **Applica**. L’istruzione virtuale è abilitata per il tuo account.
   ![](assets/virtual-coach-037.png)

Una volta attivata, riceverai una notifica in-app per confermare che la funzione è attiva. Quattro scenari di esempio vengono aggiunti automaticamente alla libreria dei contenuti in modo che gli autori possano iniziare immediatamente.

>[!NOTE]
>
>La chiave di attivazione viene generata automaticamente durante il provisioning e condivisa tramite e-mail. Se non disponi della chiave di attivazione, contatta il Customer Success Manager (CSM) di Adobe Learning Manager.

## Visualizzazione del saldo del credito MAU

I crediti MAU (Monthly Active User) contano il numero di Allievi univoci che utilizzano l’Allenatore virtuale ogni mese.

1. Passa alla pagina **Fatturazione**.
2. Nella sezione **Allenatore virtuale**, seleziona **Visualizza dettagli utilizzo**.
3. Utilizza l&#39;elenco a discesa **Seleziona periodo** per scegliere l&#39;intervallo di date da rivedere.
   ![](assets/virtual-coach-038.png)

   La tabella **Utilizzo complessivo** mostra:

   a. **Disponibile:** Totale crediti MAU acquistati\
   b. **Utilizzato:** crediti utilizzati fino alla data corrente\
   c. **Rimanenti:** crediti disponibili per il resto del periodo del contratto

   La tabella **Utilizzo mensile** mostra il numero di allievi attivi univoci per mese di calendario.

4. Selezionare **Scarica report dettagliato** per esportare i dati di utilizzo completi.

## Come vengono utilizzati i crediti MAU

Un credito MAU viene utilizzato quando un Allievo completa una sessione di coach virtuale in un mese di calendario. Le sessioni aggiuntive dello stesso Allievo nello stesso mese non richiedono crediti aggiuntivi.

| Scenario | MAU utilizzate |
|----------|--------------|
| Un Allievo completa 5 sessioni a gennaio | 1 |
| Lo stesso Allievo utilizza l’istruttore virtuale sia a gennaio che a febbraio | 2 (1 al mese) |
| 100 Allievi completano 1 sessione a gennaio | 100 |

_I crediti MAU vengono conteggiati per Allievo univoco al mese, indipendentemente dal numero di sessioni completate da ogni Allievo._

I crediti non utilizzati alla fine del periodo contrattuale scadono e non sono riportati.

### Esempio 1: Allievo singolo, più sessioni

Scenario: Sarah completa cinque sessioni di Virtual Coach in gennaio.

* Sessioni di gennaio: 5
* MAU utilizzate: 1
* Perché: Sarah viene contata come singolo utente univoco per il mese di gennaio, indipendentemente dal numero di volte in cui si esercita.

### Esempio 2: stesso Allievo, più mesi

Scenario: Sarah utilizza Virtual Coach sia gennaio che febbraio.

* Sessioni di gennaio: 3
* Sessioni di febbraio: 2
* MAU consumate: 2 (1 per gennaio + 1 per febbraio)
* Perché: ogni mese di calendario viene conteggiato separatamente.

### Esempio 3: più Allievi, stesso mese

Scenario: 100 agenti di vendita completano ciascuna sessione di Virtual Coach in gennaio.

* Totale sessioni: 100
* MAU utilizzati: 100
* Perché: ogni Allievo univoco conta come un MAU per quel mese.

### Esempio 4: esercitazione del team nel tempo

Scenario: il tuo team di 50 persone utilizza Virtual Coach durante tutto l&#39;anno.

| Mese | Allievi attivi | MAU utilizzate questo mese | MAU cumulative |
|------|----------------|--------------------------|-----------------|
| gennaio | 0 | 0 | 0 |
| ebruary | 5 (5 persone non hanno praticato) | 5 | 5 |
| Marzo | 0 (tutti i 50 guadagni praticati) | 0 | 45 |
| Aprile | 0 | 0 | 75 |

## Visualizza report istruzioni virtuali

La sezione **Gestisci** > **Sezione Report** > **Pagina Report IA** fornisce dati sull&#39;utilizzo e sulle prestazioni per tutte le attività degli istruttori virtuali nell&#39;organizzazione. Due report sono disponibili sotto l&#39;intestazione **Allenatore virtuale**.

Tutti i report vengono esportati in formato CSV. La generazione dei report può richiedere diversi minuti, a seconda delle dimensioni dei dati.

### Riepilogo utilizzo Allievo

Contiene dati di utilizzo mensili per tutti gli Allievi. Utilizza questo report per tenere traccia del numero di Allievi che utilizzano Allenatore virtuale ogni mese, monitorare il consumo di crediti MAU e identificare le tendenze del coinvolgimento nel tempo.

### Dettagli della sessione

Contiene dati a livello di sessione per tutti gli Allievi negli ultimi 90 giorni. Utilizza questo report per esaminare i punteggi delle singole sessioni, la copertura degli argomenti e le metriche dello stile nella popolazione di allievi e per identificare le lacune nelle abilità che potrebbero richiedere formazione o contenuti aggiuntivi.

## Accedere a un report e scaricarlo

1. Accedi a Adobe Learning Manager come amministratore.
2. Seleziona **Report** nel riquadro di navigazione a sinistra.
3. Seleziona **Report IA**.
4. Nella sezione **Allenatore virtuale**, seleziona il report da scaricare, **Riepilogo dell’utilizzo degli Allievi** o **Dettagli della sessione**.
   ![](assets/virtual-coach-039.png)
5. Seleziona l&#39;intervallo di date quando richiesto, quindi seleziona **Procedi**.
6. Il report viene scaricato automaticamente come file CSV.
