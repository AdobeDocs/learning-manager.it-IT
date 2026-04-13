---
description: Impostare una finestra temporale durante la quale agli Allievi è consentito avviare un modulo.
jcr-language: en_us
title: Controllo del tempo di accesso al modulo
contentowner: mmanuel
source-git-commit: 6423fd5c0853705a28c6c67b6936d93e68cbca20
workflow-type: tm+mt
source-wordcount: '615'
ht-degree: 1%

---

# Controllo del tempo di accesso al modulo

## Panoramica

Il miglioramento consente agli Autori e agli Amministratori di Adobe Learning Manager di definire una finestra temporale durante la quale gli Allievi possono avviare un modulo. Al di fuori della finestra di inizio/fine configurata, il modulo rimane visibile nella struttura del corso, ma gli allievi non possono avviarlo.

Questa funzionalità è fondamentale per gli utenti che necessitano di un controllo più rigoroso per verificare quando determinati contenuti diventano disponibili o non devono più essere avviati, ad esempio in programmi a tempo determinato, corsi di formazione basati su coorte o esercizi che richiedono tempi lunghi.

## Novità

Gli Autori possono ora configurare, a livello di modulo all’interno di un corso, una data/ora di inizio e una data/ora di fine che determinano quando agli Allievi è consentito avviare tale modulo. All’interno di questa finestra, il modulo funziona come al solito; prima dell’ora di inizio o dopo l’ora di fine, l’Allievo vede il modulo nella struttura del corso ma non può avviarlo.
La configurazione viene visualizzata nell’interfaccia utente di creazione del corso come controlli di pianificazione aggiuntivi per tipi di modulo specifici, ad esempio contenuti autonomi, quiz o attività. Gli amministratori possono utilizzare questi controlli per creare moduli che si aprono in fasi o per evitare l&#39;avvio tardivo di programmi in cui il contenuto deve essere utilizzato entro un periodo di tempo definito.

## Vantaggi principali

Il vantaggio principale è la possibilità di controllare quando i moduli sono accessibili. I team di formazione possono sincronizzare la disponibilità dei moduli con eventi reali, quali il lancio di nuovi prodotti, le scadenze normative e i programmi interni. Ciò garantisce che gli Allievi completino i contenuti dei prerequisiti prima di poter accedere ai moduli successivi.
Ad esempio, la coorte 1 può accedere al modulo 2 solo nella settimana 2, mentre il modulo 3 rimarrà bloccato fino alla settimana 3, eliminando la necessità di nascondere e scoprire manualmente i contenuti o di creare versioni del corso separate.
Ciò migliora l’esperienza dell’Allievo: invece di affrontare moduli a cui è tecnicamente possibile accedere ma che non dovrebbero essere in quel momento (o che dovrebbero già essere completati), gli Allievi vedono una struttura del corso in cui i moduli a cui è consentito avviare sono chiaramente allineati alla pianificazione prevista.

## Casi d’uso

**Programma di abilitazione basato su coorte**: in questo programma, ogni settimana viene aperto un nuovo modulo. Il contenuto per la Settimana 1 è disponibile immediatamente, mentre la Settimana 2 è visibile ma non può essere avviata fino a una data specificata. La Settimana 3 segue lo stesso processo di controllo. Gli Allievi possono visualizzare l’intero percorso di apprendimento, ma il sistema controlla quando possono effettivamente iniziare ciascun passaggio.
**Corso di formazione su prodotti o campagne in scadenza**: i team di marketing o di prodotto possono creare un modulo di formazione a cui accedere solo quando è attiva una campagna o quando è ancora disponibile una versione specifica di un prodotto. Questa finestra iniziale assicura che gli allievi non inizino un modulo su una versione del prodotto fuori produzione dopo l’ora di fine specificata.
**Ambienti di valutazione o esame**: le organizzazioni possono aprire un modulo (ad esempio un test) per una breve finestra ben definita (ad esempio, &quot;è possibile avviare l&#39;esame in qualsiasi momento tra il 9:00 e il 12:00 in una data specifica&quot;). Gli Allievi non possono iniziare l’esame al di fuori di tale finestra, il che supporta una pianificazione equa per fusi orari e coorti.

## Impostazione del tempo di accesso del modulo

1. Accedi a Adobe Learning Manager come Autore.
2. Vai alla sezione **Apprendimento** > **Corsi**. ALM visualizza un elenco di corsi.![alt-text](/help/migrated/administrators/feature-summary/assets/module-access-time1.png)
3. Seleziona il corso per il quale desideri impostare la restrizione.
4. Seleziona **Istanze**. ALM visualizza un elenco di istanze.
5. Selezionare **Moduli** nella sezione dell&#39;istanza per cui si desidera impostare il limite di accesso. Viene visualizzato il pulsante **Modifica**.![alt-text](/help/migrated/administrators/feature-summary/assets/module-access-time2.png) ![alt-text](/help/migrated/administrators/feature-summary/assets/module-access-time3.png)
6. Seleziona **Modifica**. Le sezioni pertinenti relative al modulo si aprono verso la parte inferiore della pagina.![alt-text](/help/migrated/administrators/feature-summary/assets/module-access-time4.png)
7. Per ogni sezione, selezionare una data iniziale, un&#39;ora iniziale, una data finale e un&#39;ora finale.
8. Seleziona **Salva**. In ALM viene visualizzato il messaggio &quot;Mapping salvato correttamente&quot;.










