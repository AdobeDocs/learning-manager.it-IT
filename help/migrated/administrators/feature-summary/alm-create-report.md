---
jcr-language: en_us
title: Introduzione a un modello di Report Builder
description: Crea rapidamente un report in Adobe Learning Manager Report Builder partendo da un modello predefinito per i casi d'uso più comuni.
contentowner: mmanuel
source-git-commit: b4540c4c23ad496c8fff01095be6715d18aa0512
workflow-type: tm+mt
source-wordcount: '818'
ht-degree: 0%

---


# Introduzione a un modello di Report Builder

I modelli sono configurazioni di report pronte all’uso fornite da Adobe Learning Manager. Ogni modello è progettato per uno specifico caso di utilizzo, come la registrazione e il tracciamento del completamento, la segnalazione della conformità o le prestazioni dell’istruttore. Puoi scaricare direttamente un modello o duplicarlo per crearne una copia modificabile.

1. Accedi a Adobe Learning Manager come amministratore.
2. Seleziona **Report** nel riquadro a sinistra, quindi seleziona **Report Builder**.
3. Selezionare la scheda **Modelli**.
4. Sfoglia i modelli disponibili. A ogni modello viene assegnato un nome specifico.
   ![](assets/image007.png)
5. Seleziona il nome di un modello per aprirne l’anteprima di sola lettura. Per questo esempio, seleziona Duplica accanto al modello MoM Catalogo Wise - Conteggio corsi. Esaminate le colonne, i filtri applicati e l’ordinamento. Quando si duplica un modello, Report Builder apre una copia modificabile con la configurazione esistente del modello precaricata. Il nome, la descrizione, le colonne, i filtri e l’ordinamento del report sono tutti modificabili prima del salvataggio.

## Assegnare un nome al report e descriverlo

1. Nel campo **Nome**, sostituisci il nome predefinito (ad esempio, _copia del catalogo Wise_ - _MoM conteggio corsi_) con un nome univoco per il report. È necessario specificare un nome.
2. Nel campo **Descrizione**, immettere un breve riepilogo del contenuto del report. Questo aiuta gli altri amministratori a comprendere lo scopo del report quando lo visualizzano o lo modificano.

## Aggiungere e configurare le colonne

La sezione **Colonne** dispone di due pannelli: **Seleziona colonne** a sinistra e **Colonne selezionate** a destra.

### Aggiungere una colonna

1. Nel pannello **Seleziona colonne**, espandere un set di dati selezionandone il nome. Ad esempio, **Catalogo** o **Gruppo di utenti attivi**.
2. Selezionare l&#39;icona **+** accanto alla colonna che si desidera aggiungere. La colonna viene visualizzata nel pannello **Colonne selezionate** a destra.
   ![](assets/image009.png)
3. Per aggiungere più volte la stessa colonna. Ad esempio, per applicare due aggregazioni diverse allo stesso campo. Selezionare nuovamente **+** per la colonna.

### Riordina colonne

Trascinate la maniglia a sinistra di qualsiasi riga di colonna nel pannello **Colonne selezionate** per spostarla in una posizione diversa. L’ordine delle colonne nel pannello corrisponde a quello nel report scaricato.

### Rinominare una colonna

1. Seleziona l&#39;icona **modifica** (matita) su una riga di colonna.
   ![](assets/image011.png)
2. Immettere un alias. L’alias viene visualizzato come intestazione di colonna nel report scaricato anziché come nome di campo predefinito.
   ![](assets/image013.png)

### Rimuovere una colonna

Selezionare l&#39;icona **×** in una riga di colonna per rimuoverla dal report.

## Applica gruppo per

Il controllo **Raggruppa per** viene visualizzato nella parte superiore del pannello **Colonne selezionate**.

1. Seleziona **Raggruppa per: Seleziona**.
   ![](assets/image015.png)
2. Selezionare le colonne in base alle quali eseguire il raggruppamento. Potete selezionare più opzioni. Nella schermata, il report è raggruppato per _catalogo_ e _mese di creazione_.
3. Ogni colonna selezionata viene visualizzata sotto il controllo Raggruppa per come tag. Per rimuovere una colonna raggruppata, selezionare **×** nel relativo tag.

>[!NOTE]
>
>Quando si applica GroupBy, a ogni colonna che non è una colonna group-by deve essere applicata una funzione di aggregazione. Una colonna senza un&#39;aggregazione genererà un errore.

## Applicare un&#39;aggregazione a una colonna

1. In qualsiasi colonna non raggruppata nel pannello **Colonne selezionate**, selezionare **Aggrega per**.
2. Scegli una funzione dal menu a discesa. Nello screenshot, **Oggetto di apprendimento** - **ID oggetto di apprendimento** utilizza **Count Distinct**, con alias ount_of_course.

Funzioni di aggregazione disponibili:

| Funzione | Elementi restituiti |
|----------|-----------------|
| Conteggio | Numero totale di righe nel gruppo |
| Distinto conteggio | Numero di valori univoci nel gruppo |
| Conteggio se | Numero di righe corrispondenti a un valore specificato |
| Somma | Totale di un campo numerico nel gruppo |
| Min | Valore più basso nel gruppo |
| Massimo | Valore massimo nel gruppo |
| Valutazione | Valore medio nel gruppo |

## Applica filtri

La sezione **Filtri** si trova sotto la sezione **Colonne**. I filtri limitano le righe visualizzate nel report.

1. Per aggiungere un filtro, seleziona l&#39;icona **+** a destra della sezione Filtri.
2. Scegli il campo su cui filtrare.
   ![](assets/image017.png)
3. Selezionare un operatore e immettere o scegliere un valore.

Per modificare un filtro esistente, selezionare l&#39;icona **matita** nella riga del filtro. Per aggiungere un gruppo di filtri nidificato, seleziona l’icona + con parentesi quadre a destra di una riga di filtro.

## Configura ordinamento

La sezione Ordinamento si trova sotto la sezione Filtri.

1. Selezionare **+ Aggiungi ordinamento** per aggiungere un ordinamento.
2. Scegli la colonna in base alla quale eseguire l&#39;ordinamento e seleziona **Crescente** o **Decrescente**.
   ![](assets/image020.png)
3. Ripetete per aggiungere ordinamenti secondari. Trascinare la maniglia a sinistra di ogni riga di ordinamento per modificare la priorità.

>[!TIP]
>
>Applicare sempre almeno un ordinamento. Senza ordinamento, l&#39;ordine delle righe può differire tra i download dello stesso report.

## Salvare il report

Seleziona **Salva report** nell’angolo in alto a destra. Il report è stato salvato nella scheda **Report** ed è pronto per il download.

## Procedure ottimali

* Utilizza gli alias in ogni colonna in modo che il report scaricato contenga intestazioni significative anziché nomi di campi come _Oggetto di apprendimento_ - _ID oggetto di apprendimento_.
* Utilizza Distinto conteggio invece di Conteggio quando desideri record univoci, ad esempio corsi distinti per catalogo anziché righe totali.
* Applica l’ordinamento prima del salvataggio, in particolare per i report che condividerai o a cui ti iscrivi.
* Mantenete la descrizione aggiornata. Altri amministratori si basano su di esso per comprendere l’ambito del report senza aprirlo.
