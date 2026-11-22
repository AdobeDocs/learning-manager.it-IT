---
description: Personalizza le e-mail a livello di corso e di istanza in Adobe Learning Manager con Email Builder e un layout fornito dall’amministratore.
jcr-language: en_us
title: Personalizzazione delle e-mail relative a corsi e istanze in Email Builder
exl-id: 06499e3f-0610-4983-83f2-3e8b578fc8bf
source-git-commit: 172889a4ff67e54c8e7b9a39ef5f393af0a1d703
workflow-type: tm+mt
source-wordcount: '466'
ht-degree: 0%
---

# Personalizzazione delle e-mail relative a corsi e istanze in Email Builder

In qualità di Autore, puoi personalizzare le e-mail per un corso o per un’istanza specifica di un corso. Entrambe le procedure iniziano da un layout fornito dall&#39;amministratore.

## Personalizzazione dell’e-mail a livello di corso

1. Apri il corso.
2. Seleziona **Modelli e-mail**.
3. Seleziona **Layout e-mail del corso**.
4. Personalizza il contenuto dell’e-mail. Per impostare font, colori, righe e pulsanti.
5. Salva il modello.
6. Publish il corso.

## Personalizzazione di un’e-mail a livello di istanza

Utilizza un&#39;e-mail a livello di istanza quando diverse coorti richiedono messaggi diversi. Puoi gestire queste coorti tramite le istanze del corso.

1. Apri l’istanza del corso.
2. Apri **Generatore e-mail**.
3. Selezionate un layout disponibile o ereditate il layout già utilizzato dall’istanza.
4. Aggiorna il contenuto del messaggio.
5. Salva il modello.

>[!NOTE]
>
>Quando entrambe esistono, le e-mail a livello di istanza hanno la precedenza sui modelli a livello di corso.

## Usare la variabile Title e un’immagine per le intestazioni e-mail

Utilizzare la variabile Title con un componente Image per creare l&#39;intestazione e-mail anziché il componente Banner. L&#39;immagine del componente Banner non viene visualizzata in alcuni client di posta elettronica, ad esempio Outlook.

La variabile Title, EmailTitle, funziona come la variabile ChannelName esistente. Ogni e-mail ha il proprio valore di titolo predefinito.

Per aggiungere un&#39;intestazione del titolo:

1. Aggiungi un componente Immagine per l’immagine dell’intestazione.
2. Aggiungi un componente di testo e inserisci la variabile del titolo dal menu a discesa delle variabili nel riquadro di configurazione del componente.
3. Allinea al centro il componente Testo. Nel layout globale, posizionalo nell&#39;intestazione superiore.

   Per impostazione predefinita, le singole e-mail utilizzano l’intestazione del layout globale. In un singolo messaggio e-mail, puoi modificare il componente Testo in:

4. Sostituire la variabile con testo personalizzato
5. Aggiungi il testo prima o dopo la variabile e mantieni `EmailTitle`

Se aggiungi un&#39;immagine al componente Banner, Email Builder visualizza un avviso che l&#39;immagine potrebbe non essere visualizzata correttamente in alcuni client e-mail. L&#39;avviso suggerisce invece di utilizzare un componente Immagine e la variabile titolo.

## Risoluzione dei problemi

**Impossibile selezionare un layout.**
L’ereditarietà dei layout dipende dai layout principali disponibili. Chiedi all’amministratore di creare un layout dell’account.

**Nel messaggio di posta elettronica non vengono visualizzate le ultime modifiche apportate al layout.**
Il modello potrebbe essere scollegato dal relativo layout. I modelli non collegati non ricevono più aggiornamenti del layout.

**Gli Allievi di un’istanza ricevono un messaggio e-mail diverso da quello del corso.**
Le e-mail a livello di istanza hanno la precedenza sui modelli a livello di corso. Esamina il modello a livello di istanza.

**Email Builder non viene visualizzato per le e-mail relative al corso o all&#39;istanza.**
Adobe abilita Email Builder in fasi. Chiedi all’amministratore di confermare che Generatore di e-mail sia abilitato per il tuo account.

**L&#39;immagine del banner non viene visualizzata nell&#39;e-mail.**
Alcuni client di posta elettronica, ad esempio Outlook, non visualizzano l&#39;immagine del componente Banner. Rimuovi il componente Banner, aggiungi un componente Immagine e aggiungi un componente Testo che utilizza la variabile titolo.
