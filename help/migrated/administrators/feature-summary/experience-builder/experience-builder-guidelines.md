---
title: Linee guida e limitazioni di Experience Builder in Adobe Learning Manager
description: Le linee guida e le limitazioni di Experience Builder forniscono suggerimenti personalizzati su contenuti e corsi agli Allievi utilizzando algoritmi basati sull’intelligenza artificiale.
jcr-language: en-us
source-git-commit: b3124c47d56a50437cb284fe809828bcd4c4008d
workflow-type: tm+mt
source-wordcount: '796'
ht-degree: 0%

---


# Linee guida e limitazioni di Experience Builder

Experience Builder è un potente strumento progettato per aiutare gli utenti a creare facilmente pagine Web dinamiche e coinvolgenti. Per garantire prestazioni, usabilità e sicurezza ottimali, è essenziale seguire determinate linee guida e raccomandazioni durante la configurazione delle pagine, l’utilizzo dei widget e la personalizzazione dei layout. Questo documento fornisce una panoramica dettagliata di note e punti importanti che gli utenti devono considerare quando utilizzano Experience Builder.

Le informazioni qui descritte riguardano aspetti chiave quali le configurazioni di pagine e widget, le opzioni di personalizzazione, la gestione del codice personalizzato e considerazioni sulla sicurezza. Aderendo a questi consigli, gli utenti possono ottimizzare l’efficienza dei progetti Experience Builder, evitare insidie comuni e adattarsi senza problemi ad aggiornamenti e modifiche.

## Configurazione di pagine e widget

### Numero massimo di pagine

In Experience Builder puoi creare fino a 1000 pagine. Questo è il limite massimo, ma si consiglia di pianificare le pagine strategicamente per evitare inutili complessità.

### Widget per pagina

* **Limite rigido**: è possibile aggiungere un massimo di 25 widget a una singola pagina.
* **Limite consigliato**: per prestazioni migliori, si consiglia di utilizzare non più di 10 widget per pagina.
* **Widget basati su API**: i widget che dipendono dalle API ALM (ad esempio, corsi e percorsi, categoria, il mio apprendimento, apprendimento sociale, calendario, conformità, classifica) devono essere limitati a 10 per pagina.
* **Widget indipendenti**: i widget come HTML e Content Box, che non si basano sulle API ALM, possono essere utilizzati fino al limite massimo di 25 widget.

### Widget monouso

Alcuni widget, come Calendario, Apprendimento sociale, Conformità e Classifica, devono essere utilizzati solo una volta a pagina. L’utilizzo ripetuto di tali controlli può causare problemi di prestazioni, in particolare per i widget come il calendario, che richiedono risorse significative per caricare le sessioni.

### Linee guida per il dimensionamento del widget

I widget come Calendario, Classifica, Social e Conformità devono essere inseriti in layout con una larghezza minima di un terzo della pagina. I widget a scheda singola sono più adatti a questa larghezza per garantire una visualizzazione ottimale. I widget come Calendario e Conformità (vista espansa) sono progettati per layout a mezza larghezza per offrire una migliore esperienza utente. Per altre dimensioni di layout, i widget si adattano in modo dinamico per adattarsi allo spazio disponibile e mantenere la usabilità.

L’utilizzo di widget all’interno di queste linee guida sulle dimensioni consigliate migliora l’interazione complessiva con l’utente.

## Linee guida per la personalizzazione

### Distanze in pixel predefinite

**Distanza verticale**: la distanza verticale predefinita tra i widget è di 80 pixel.
**Distanza orizzontale**: la distanza orizzontale predefinita tra i widget è di 20 pixel.

### CSS personalizzato

Gli utenti possono sostituire le distanze predefinite e altre proprietà visive utilizzando CSS personalizzato.

Passaggi per la personalizzazione:

* Inspect gli elementi della pagina per identificare le classi CSS.
* Applicare le modifiche a livello globale, widget o pagina.

Ad esempio, per ridurre la distanza verticale tra i widget, modificate la proprietà CSS per la classe pertinente.

## Posizionamento menu

I menu possono essere posizionati nella parte superiore o sinistra della pagina. È possibile apportare ulteriori regolazioni mediante CSS personalizzato.

## Consigli specifici per le funzioni

### Widget Apprendimento sociale e Gamification

* Se queste funzioni sono disattivate, gli amministratori devono rimuovere manualmente i widget corrispondenti dalle pagine.
* Le pagine devono essere riprogettate in modo da rimanere funzionali e visivamente intatte dopo la disattivazione di queste funzioni.

## Gestione del codice personalizzato

### Impatto degli aggiornamenti

* Il codice personalizzato esistente (HTML, CSS, JS) inserito nel back-end potrebbe non funzionare come previsto dopo gli aggiornamenti a Experience Builder.
* Gli utenti devono riscrivere il codice per allinearlo alle nuove modifiche dell&#39;interfaccia utente, ad esempio i nomi di classe aggiornati.

### Supporto front-end

* Aggiungi codice personalizzato direttamente nel portale di amministrazione utilizzando widget HTML o blocchi CSS/JS a livello di account.

### Dichiarazione di non responsabilità

* Il codice personalizzato potrebbe non funzionare come previsto con le versioni future, che richiedono regolazioni. Preparati ad aggiornare il codice dopo ogni versione.

## Raccomandazioni generali

### Considerazioni sulle prestazioni

* Evitare di superare i limiti consigliati del widget per evitare il degrado delle prestazioni.
* L’utilizzo ripetuto di widget che richiedono molte risorse (ad esempio, un calendario) su una pagina può influire in modo significativo sui tempi di caricamento della pagina.

### Considerazioni sulla sicurezza

* **Widget HTML**: è necessario assicurarsi che il codice gestisca problemi di sicurezza come gli attacchi XSS (Cross-Site Script), poiché non rientrano nell&#39;ambito del controllo di Experience Builder.
* **Piè di pagina personalizzato**: durante la personalizzazione del piè di pagina tramite HTML o CSS, assicurati che il codice rispetti le procedure consigliate per la sicurezza.

### Modifiche interrotte

Gli aggiornamenti di Experience Builder possono introdurre modifiche rivoluzionarie per le personalizzazioni. L’Utente deve:

* Regola il codice in modo che corrisponda ai nuovi elementi dell&#39;interfaccia utente.
* Verificare le personalizzazioni dopo ogni aggiornamento.

## Note aggiuntive

### Implementazione CSS personalizzata

* Potete ispezionare gli elementi della pagina, copiare le classi CSS e applicare le proprietà desiderate per personalizzare i layout a livello globale, a livello di widget o a livello di pagina.

### ID widget e ID pagina

Ogni widget e pagina ha ID univoci che possono essere utilizzati per modifiche CSS di destinazione. Ciò consente la personalizzazione a diversi livelli:

* Livello globale: applicate le modifiche CSS a tutte le pagine.
* Livello widget: consente di applicare le modifiche CSS a widget specifici.
* A livello di pagina: consente di applicare le modifiche CSS a tutti i widget di una determinata pagina.










