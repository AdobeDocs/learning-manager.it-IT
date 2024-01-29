---
description: Durante il caricamento di un file CSV, viene visualizzato un errore. Continua a leggere per risolvere il problema.
jcr-language: en_us
title: Impossibile caricare il file CSV
contentowner: saghosh
source-git-commit: 8b29ac996962e7ce8fbda51f3421c9a5f248fcf6
workflow-type: tm+mt
source-wordcount: '541'
ht-degree: 0%

---



# Impossibile caricare il file CSV

## Errore: dati troncati: dati troppo lunghi per la colonna

Quando tenti di caricare un file CSV in Adobe Learning Manager, visualizzi il seguente messaggio di errore.

![](assets/csv-upload-failed.png)

*Messaggio di errore che indica che l’elaborazione del file CSV non è riuscita*

## Causa

L&#39;errore si verifica se i dati presenti nella colonna specificata superano il limite di caratteri definito per la colonna.

## Risoluzione

* Apri il file CSV.
* Controlla i dati nella colonna indicata nell’errore.
* Se esiste un valore grande, ad esempio maggiore di 60 caratteri, modificalo per correggere i dati.

## Errore: nella prima colonna del file CSV viene visualizzato un carattere speciale

Impossibile caricare un file CSV perché nella prima colonna viene visualizzato un carattere speciale durante la mappatura delle colonne.

![](assets/csv-2.png)

*Carattere speciale nella colonna Nome*

## Causa

Il problema si verifica quando il file CSV viene salvato in formato UTF-8 in Excel. Quando salvi un file CSV in Excel come UTF-8, il file viene salvato in formato UTF-BOM. Puoi verificarlo utilizzando Blocco note++ o quando carichi un file CSV in Learning Manager, durante la mappatura delle colonne, nella prima colonna viene visualizzato un carattere speciale.

## Risoluzione

* **R:** Salvataggio tramite Excel:

   1. Apri il file CSV in Excel.
   1. Salva il file come file CSV normale.

* **B:** Salvataggio tramite Notepad o Notepad++:

   * Apri il file CSV in Notepad o Notepad++.
   * Salvate il file in formato UTF-8.

## Errore: indirizzo e-mail dell’utente già presente nel sistema

Impossibile caricare un file CSV perché l’elaborazione CSV non è riuscita. Viene visualizzato il messaggio di errore riportato di seguito:

![](assets/csv-3.png)

*Messaggio di errore per un utente dupliacet*

## Causa

Questo problema si verifica se un utente è già presente nel sistema con lo stesso indirizzo e-mail o UUID.

## Risoluzione

### Scenario 1

**Account per i quali l’UUID non è abilitato.**

In questo scenario, l&#39;errore può essere dovuto a due motivi:

1. L’utente che stai tentando di aggiungere è un Manager di un profilo esterno. Per risolvere questo problema, apri il profilo esterno di cui fa parte l’utente, selezionalo e fai clic su **[!UICONTROL Azioni]** > **[!UICONTROL Assegna ruolo]** > **[!UICONTROL Manager]** e modificare il Manager del profilo.
1. L’utente che stai tentando di aggiungere è stato eliminato. In questo scenario, non potrai aggiungere l’utente con lo stesso indirizzo e-mail fino al completamento del processo di rimozione. Come soluzione alternativa**, a**ggiungi all’utente un indirizzo e-mail secondario per fornire accesso alla piattaforma. Al termine del processo di rimozione, modifica l’utente e modifica l’indirizzo e-mail con l’indirizzo e-mail corretto.

### Scenario 2

**Account abilitati per UUID.**

Per gli account abilitati per UUID, questo problema può verificarsi se a un utente è stato assegnato un UUID già utilizzato da un altro utente nell’account o se l’utente ha un indirizzo e-mail diverso.

Ad esempio, consideriamo due utenti, A e B, con indirizzi e-mail,  <a@xyz.com> e <b@xyz.com> con UUID 1 e 2 rispettivamente.

A questo punto, se carichi un file CSV con l’UUID dell’utente A uguale a 3 e l’UUID dell’utente B uguale a 2, visualizzerai un errore.

>[!TIP]
>
>Per risolvere questo problema: **nel file CSV e nel sistema deve essere registrato lo stesso indirizzo e-mail e UUID per l’utente.**

