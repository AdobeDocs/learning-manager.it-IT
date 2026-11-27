---
title: Tenere traccia del coinvolgimento dei partecipanti
description: Scopri come gli Istruttori utilizzano l’indicatore del coinvolgimento dei partecipanti in tempo reale nell’Hub dal vivo per monitorare l’attività del browser, la chat e la partecipazione al sondaggio.
product_v2:
  - id: ed12e5b7-96e3-45e7-a17f-de222065ebcb
    internal-label: Learning Manager
source-git-commit: 5d89078fff50bbd3be1a2d01085efd568b8e0130
workflow-type: tm+mt
source-wordcount: '1408'
ht-degree: 0%
---

# Tenere traccia del coinvolgimento dei partecipanti

Il coinvolgimento dei partecipanti nell’hub live offre agli istruttori una vista in tempo reale del coinvolgimento degli allievi o dei partecipanti durante una sessione dal vivo. Combina l’attenzione del browser, l’attività della chat e la partecipazione al sondaggio in un singolo livello di coinvolgimento, mostrato come indicatore verde, giallo o rosso. Usalo per individuare i tuffi nell’attenzione e regolare la consegna in tempo reale.

Il coinvolgimento dei partecipanti mostra il livello medio di coinvolgimento di tutti gli Allievi nella sala principale in un determinato momento. Il livello si aggiorna appena un Allievo si unisce alla sessione.

Il coinvolgimento del partecipante viene calcolato e visualizzato solo durante una sessione dal vivo.

>[!NOTE]
>
> Solo gli Istruttori possono visualizzare il coinvolgimento dei partecipanti. Gli Allievi non vi hanno accesso.

## Comprendere i calcoli del livello di coinvolgimento

Il punteggio di coinvolgimento dei partecipanti ti aiuta a monitorare l’attenzione degli Allievi in tempo reale durante una sessione dal vivo. Questo badge di coinvolgimento nella parte superiore dello schermo mostra il livello di coinvolgimento complessivo come **Basso**, **Medio** o **Alto**, consentendoti di regolare la consegna della sessione e incoraggiare la partecipazione secondo necessità.

L’indicatore è visibile solo agli Istruttori nella stanza principale.

![Indicatore livello coinvolgimento](assets/engagement-level-indicator.png)
*Interfaccia Hub live che mostra il coinvolgimento dei partecipanti nell&#39;angolo superiore destro.*

## Come viene calcolato il punteggio di coinvolgimento

Ogni Allievo o partecipante ha un punteggio di coinvolgimento compreso tra 0 e 100, in base ai seguenti fattori:

- **Attenzione alla sessione**: quando un Allievo o un partecipante mantiene attiva la finestra della sessione, il livello di coinvolgimento è alto per impostazione predefinita. Se passano a un’altra finestra o scheda del browser, il livello di coinvolgimento scende a Basso a meno che non continuino a partecipare alle attività della sessione.
- **Partecipazione alla sessione**: attività come parlare, condividere uno schermo, inviare messaggi di chat, rispondere a sondaggi o quiz, disegnare sulla lavagna, alzare la mano, inviare reazioni e fare clic all&#39;interno della sessione aumentano il punteggio di coinvolgimento.

### Come cambiano i punteggi di coinvolgimento

Il punteggio di coinvolgimento degli Allievi cambia durante una sessione dal vivo in base alla loro attenzione e partecipazione. Le seguenti condizioni influenzano il modo in cui viene calcolato il punteggio dell&#39;accordo:

- **Durata dell&#39;attività**: la maggior parte delle attività di partecipazione aumenta temporaneamente il punteggio di coinvolgimento e il loro contributo diminuisce gradualmente nell&#39;arco di circa cinque minuti. Ad esempio, se un Allievo parla durante una sessione e poi passa a un’altra finestra, il suo punteggio di coinvolgimento si riduce gradualmente anziché immediatamente
- **Condivisione dello schermo**: il punteggio di coinvolgimento rimane su 100 mentre un Allievo o un partecipante condivide lo schermo.
- **Attività simultanee**: quando un Allievo o un partecipante esegue più attività contemporaneamente, viene considerata solo l’attività con il valore di coinvolgimento più elevato. I punteggi delle singole attività non sono combinati, assicurando che il punteggio dell’impegno non superi il 100.
- **Più dispositivi**: se un Allievo o un partecipante partecipa alla sessione da più dispositivi, viene considerato il punteggio di coinvolgimento più alto tra tali dispositivi.

## Punteggio complessivo di coinvolgimento

Il badge coinvolgimento partecipante mostra il livello di coinvolgimento complessivo in base al punteggio medio di coinvolgimento di tutti gli Allievi nella stanza principale, arrotondato al numero intero più vicino.

Le seguenti condizioni si applicano quando si calcola il punteggio complessivo dell’ingaggio:
- **Istruttori e bot di registrazione**: gli istruttori e i bot di registrazione sono esclusi dal calcolo complessivo del punteggio di coinvolgimento. I bot di registrazione non vengono visualizzati nell&#39;elenco dei partecipanti.
- **Sale per le attività**: gli allievi o i partecipanti alle sale per le attività non sono inclusi nel punteggio complessivo di coinvolgimento. Quando gli Allievi si spostano tra la stanza principale e una breakout room, i loro punteggi di coinvolgimento individuale vengono ripristinati e ricalcolati entro uno o due minuti.
- **Nuovi Allievi**: il punteggio di coinvolgimento dei partecipanti diventa disponibile circa un minuto dopo l’adesione alla sessione. Finché il punteggio non sarà disponibile, l’allievo o il partecipante verrà escluso dal calcolo del punteggio complessivo dell’accordo.
- **Stanza principale vuota**: quando nessun Allievo o partecipante è presente nella stanza principale, il badge mostra il coinvolgimento del partecipante senza un livello di coinvolgimento.

## Identificazione dei livelli di coinvolgimento e degli indicatori

Il badge di coinvolgimento del partecipante mostra uno dei seguenti livelli di coinvolgimento in base al punteggio complessivo di coinvolgimento. Puoi utilizzare questi livelli per monitorare l’attenzione degli Allievi e regolare l’erogazione della sessione in base alle esigenze.  Ecco cosa significa ogni livello:

| **Livello di coinvolgimento** | **Punteggio** | **Descrizione** |
|----|----|----|
| Alto | da 61 a 100 | Gli Allievi partecipano attivamente alla sessione. |
| Media | da 31 a 60 | Gli Allievi mostrano interazioni occasionali con una partecipazione moderata. |
| Basso | Da 0 a 30 | Gli Allievi mostrano un’interazione minima o nulla o una riduzione dell’attenzione durante la sessione. |

>[!NOTE]
>
> - Il punteggio di coinvolgimento indica l’attenzione del partecipante durante una sessione. Non misura né i risultati né le prestazioni dell’apprendimento.
> 
> - I punteggi di coinvolgimento vengono calcolati ogni minuto. La visualizzazione delle modifiche nel badge di coinvolgimento può richiedere fino a due minuti.

## Domande frequenti

+++ Il punteggio di coinvolgimento rileva se un partecipante sta guardando attivamente la sessione?

N. Il punteggio di coinvolgimento viene calcolato in base al fatto che la finestra della sessione sia attiva e alle attività del partecipante, ad esempio la conversazione, l’invio di messaggi di chat e la risposta ai sondaggi. Per misurare il coinvolgimento, non usa lo stato di disattivazione dell’audio della videocamera, del tracciamento degli occhi o del microfono.

+++

+++ Cosa succede quando un partecipante si allontana dalla finestra della sessione?

Quando un partecipante passa a un’altra scheda del browser, finestra o applicazione, la finestra della sessione non è più considerata attiva. Anche se la finestra della sessione rimane visibile, viene considerata inattiva quando un&#39;altra finestra è attiva.

+++

+++ Tutte le attività di partecipazione contribuiscono in egual misura al punteggio di coinvolgimento?

Parlare, condividere lo schermo, inviare messaggi in chat, rispondere a sondaggi o quiz, attingere alla lavagna, alzare la mano e inviare reazioni contribuiscono in egual misura al punteggio di coinvolgimento. Facendo clic all&#39;interno della sessione il contributo è leggermente inferiore.

+++

+++ Come cambia il punteggio di coinvolgimento dopo un&#39;attività di partecipazione?

Il contributo della maggior parte delle attività di partecipazione diminuisce gradualmente nell’arco di circa cinque minuti. Ad esempio, se un partecipante passa a un’altra finestra e poi parla, il suo punteggio di coinvolgimento aumenta a 100 al successivo aggiornamento. Nei minuti successivi, il punteggio scende gradualmente a 80, 60, 40 e 20, dove rimane fino a quando il partecipante torna alla finestra della sessione o partecipa di nuovo.

Un partecipante che mantiene attiva la finestra della sessione mantiene un livello di coinvolgimento elevato.

+++

+++ I partecipanti alle breakout room sono inclusi nel punteggio di coinvolgimento complessivo?

N. Solo i partecipanti nella sala principale sono inclusi nel calcolo del punteggio complessivo dell’impegno. Il badge di coinvolgimento non viene visualizzato quando un istruttore si trova in una sala conferenze.

+++

+++ Perché il punteggio di coinvolgimento complessivo diminuisce al termine delle breakout room?

Quando i partecipanti si spostano dalle sale d&#39;attesa alla stanza principale, i loro punteggi di coinvolgimento individuale vengono reimpostati e ricalcolati entro uno o due minuti. Ciò può ridurre temporaneamente il punteggio complessivo di coinvolgimento.

+++

+++ Come viene calcolato il punteggio di coinvolgimento quando un partecipante si unisce da più dispositivi?

Se un partecipante partecipa alla sessione da più dispositivi, viene considerato il punteggio di coinvolgimento più alto tra tali dispositivi. Una sessione inattiva su un dispositivo non riduce il punteggio di coinvolgimento registrato su un altro dispositivo attivo.

+++

+++ Perché l’aggiornamento del badge di coinvolgimento richiede fino a due minuti?

Il punteggio di coinvolgimento di ogni partecipante viene calcolato una volta al minuto. Il punteggio di coinvolgimento complessivo viene quindi aggiornato una volta al minuto, in modo che le modifiche possano richiedere fino a due minuti per essere visualizzate nel badge di coinvolgimento.

+++

+++ Cosa possono fare gli istruttori quando il badge di coinvolgimento viene visualizzato Basso?

Un livello di coinvolgimento basso indica che la maggior parte dei partecipanti si è allontanata dalla finestra della sessione e non partecipa attivamente. Gli istruttori possono utilizzare sondaggi, quiz, chat o domande di discussione per incoraggiare la partecipazione e riportare l’attenzione dei partecipanti sulla sessione.

+++

+++ Gli Istruttori possono utilizzare i punteggi di coinvolgimento per monitorare la partecipazione o valutare gli Allievi?

I punteggi di coinvolgimento forniscono un’indicazione generale dell’attenzione e dell’attività del partecipante durante una sessione. Un partecipante può mantenere un livello di coinvolgimento elevato mantenendo attiva la finestra della sessione, anche senza partecipare attivamente o dimostrare di saper apprendere. Pertanto, i punteggi di coinvolgimento potrebbero non essere adatti per la valutazione delle prestazioni degli Allievi o il tracciamento della frequenza.

+++

+++ I partecipanti possono visualizzare i loro punteggi di coinvolgimento?

N. Il badge di coinvolgimento è visibile solo agli istruttori.

+++

+++ Gli istruttori possono visualizzare i punteggi di coinvolgimento dei singoli partecipanti?

N. Il badge di coinvolgimento mostra solo il punteggio di coinvolgimento complessivo per la stanza principale. I punteggi dei singoli partecipanti non sono disponibili.

+++

+++ Gli istruttori possono disabilitare il tracciamento del coinvolgimento?

N. La registrazione del coinvolgimento è sempre abilitata e non può essere disabilitata.

+++

+++ I punteggi di coinvolgimento sono disponibili nei report o nella cronologia delle sessioni?

N. Il badge di coinvolgimento mostra solo il punteggio di coinvolgimento complessivo corrente. I punteggi di coinvolgimento non vengono salvati o inclusi nei report o nella cronologia delle sessioni.

+++

+++ I co-istruttori possono visualizzare il badge di coinvolgimento?

Sì. I coistruttori possono anche visualizzare il badge di coinvolgimento durante una sessione.

+++

+++ Come vengono calcolati i punteggi di coinvolgimento sui dispositivi mobili?

I partecipanti possono accedere alle sessioni dell’Hub dal vivo tramite i browser per dispositivi mobili. I punteggi di coinvolgimento vengono calcolati utilizzando gli stessi criteri dei browser desktop.

+++
