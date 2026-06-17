---
jcr-language: en_us
title: Report Builder - concetti e terminologia
description: Prima di creare il primo report, è necessario comprendere i concetti chiave di Report Builder, inclusi dataset, colonne, raggruppamenti, filtri e aggregazioni.
contentowner: mmanuel
source-git-commit: b4540c4c23ad496c8fff01095be6715d18aa0512
workflow-type: tm+mt
source-wordcount: '816'
ht-degree: 0%

---


# Report Builder: concetti e terminologia

## Modelli e report

**I modelli** sono configurazioni di report predefinite fornite da Adobe Learning Manager. Sono progettati per casi d&#39;uso comuni, registrazione e monitoraggio del completamento, report di conformità, prestazioni degli istruttori e sono pronti per il download immediato. I modelli sono di sola lettura e non possono essere modificati né sovrascritti.
![](assets/image003.png)

**I report** sono configurazioni salvate dall&#39;utente. Puoi creare un report da zero o duplicando un modello e modificandone la copia. Quando duplichi un modello, la copia diventa un report nella scheda Report.

Sia i modelli che i report vengono visualizzati in Report Builder, ma in schede separate.

## Set di dati

Un set di dati è un gruppo denominato di colonne correlate in un Report Builder. Quando si aggiungono colonne a un report, è possibile scegliere tra questi set di dati. Ogni set di dati può essere considerato come una tabella di informazioni su un aspetto dei dati di apprendimento.

Di seguito è riportato un esempio di set di dati disponibili in Report Builder:

* **Utente:** dati del profilo dell’Allievo, inclusi i campi attivi
* **Trascrizione:** record di iscrizione e completamento
* **Oggetto di apprendimento:** corso, percorso di apprendimento e dati di certificazione
* **Istanza dell’oggetto di apprendimento:** dettagli a livello di istanza
* **Catalogo:** dati catalogo ed etichetta catalogo
* **Gruppo di utenti:** appartenenza al gruppo di utenti e gerarchia
* **Sessione modulo:** dati di aula e sessione virtuale, inclusi i dettagli del modulo di e-learning

>[!NOTE]
>
>I set di dati sono collegabili in modo selettivo. Non tutte le combinazioni sono disponibili in un unico report.

## Colonne e pulsante Aggiungi

Ogni colonna aggiunta viene visualizzata come riga nell&#39;area di lavoro del report e diventa una colonna nel file scaricato. È possibile aggiungere la stessa colonna più volte. Questa funzione è utile per misurare due valori diversi dello stesso campo. Ad esempio, è possibile aggiungere la colonna Stato due volte: una volta per contare le iscrizioni e una volta per contare gli Allievi in corso utilizzando il conteggio se aggregato.
![](assets/image005.png)

È inoltre possibile rinominare qualsiasi colonna immettendo un alias. L’alias viene visualizzato come intestazione di colonna nel report scaricato.

## Raggruppa per e aggregazione

Raggruppa per riepiloga i dati in base a un campo selezionato anziché in base a singole righe. Ad esempio, il raggruppamento in base al nome dell’istruttore fornisce una riga per istruttore anziché una riga per iscrizione.

Raggruppa in base al comportamento del database standard: dopo aver applicato Raggruppa in base a una colonna, a ogni colonna del report deve essere applicata una funzione di aggregazione. Non è possibile combinare i singoli dati di riga con i dati raggruppati. Le **funzioni** aggregate disponibili sono:

* **Conteggio:** Numero totale di righe
* **Conteggio se:** Numero di righe in cui il campo corrisponde a un valore specificato
* **Somma:** totale di un **campo** numerico
* **Min:** valore minimo in un campo numerico
* **Massimo:** il valore più alto in un campo numerico
* **Media:** valore medio di un campo numerico

Se sono state utilizzate tabelle pivot in Excel, il comando raggruppa per funziona allo stesso modo a livello di colonna.

## Filtri

I filtri limitano le righe visualizzate nel report. Potete applicare più filtri e combinarli con la logica AND o OR.

Gli operatori filtro dipendono dal tipo di dati della colonna:

* **Campi stringa:** contiene, è uguale a, inizia con (ricerca con completamento automatico disponibile per i valori riconosciuti)
* **Campi numerici:** maggiore di, minore di, uguale a, tra
* **Campi data:** uguale, prima, dopo, tra e relativi intervalli, ad esempio ultimi 90 giorni
* **Campi Enum (elenco):** è incluso, non è incluso (selezione di più valori)

## Logica AND/OR e gruppi di filtri nidificati

Per impostazione predefinita, più filtri utilizzano la logica AND. Affinché venga visualizzata una riga, tutte le condizioni devono essere vere. L&#39;operatore può passare da un filtro all&#39;altro su OR. Potete anche raggruppare i filtri utilizzando Aggiungi come gruppo, per creare una parentesi quadra. I filtri all’interno del gruppo vengono valutati insieme prima di essere combinati con i filtri esterni.

In questo modo è possibile creare condizioni quali:

(catalogo = Sicurezza OPPURE catalogo = Igiene) E la data di completamento è negli ultimi 90 giorni.

Potete nidificare i gruppi all’interno di altri gruppi per supportare una logica complessa a più livelli.

## Ordinamento

È possibile ordinare in base a una o più colonne. La prima colonna su cui si esegue l&#39;ordinamento è quella principale. Altri ordinamenti vengono applicati entro i limiti nella colonna principale.

Applica sempre almeno un ordinamento quando è necessario un output coerente. Poiché la generazione dei report viene eseguita in un sistema distribuito, l&#39;ordine delle righe non è garantito tra due download dello stesso report, a meno che non venga applicato l&#39;ordinamento.

## Confronto tra i dati sulle tendenze e quelli sulle copie istantanee

Qualsiasi report che utilizza un aggregatore di tendenze, ad esempio mese per mese o settimana per settimana, riflette i dati snapshot correnti raggruppati per data. Non riflette lo stato storico dei dati a ciascuna data passata.

Ad esempio, un andamento delle iscrizioni raggruppato per mese mostra quante iscrizioni esistono oggi, distribuite nei mesi in cui sono state create. Non tiene conto degli Allievi che in seguito hanno annullato l’iscrizione o modificato i gruppi di utenti. Questi cambiamenti non sono applicati retroattivamente ai mesi passati.

## Allievi eliminati e campi attivi

Il Report Builder supporta l’inclusione degli allievi eliminati nei report e il recupero dei valori dei campi attivi. Per creare il report, utilizzare la colonna **Data eliminazione** nel set di dati **Utente**.

## Procedure ottimali

* Prima di creare un report da zero, leggere il riferimento alle serie di dati disponibili. Sapere quale set di dati contiene i campi necessari consente di risparmiare tempo di configurazione significativo.
* Applica l&#39;ordinamento prima della sottoscrizione a un report pianificato. Ciò garantisce un ordine di riga coerente in ogni consegna.
* Se vengono visualizzate righe duplicate impreviste, controlla se il report include un campo che può avere più valori per riga, ad esempio il nome di un istruttore per una sessione con più istruttori.
