---
description: Scopri come Adobe Learning Manager contrassegna gli Allievi come partecipanti quando guardano una registrazione di sessione Adobe Connect, senza aggiornamenti manuali
jcr-language: en_us
title: Tenere traccia della partecipazione tramite le visualizzazioni di registrazione di Adobe Connect
exl-id: f4cb951e-3cb1-4caf-b6b8-aec86b32f782
source-git-commit: 90b45cb128b74ecb33a89bf42ef4d6e960101ff0
workflow-type: tm+mt
source-wordcount: '1654'
ht-degree: 1%
---

# Tenere traccia della partecipazione tramite le visualizzazioni di registrazione di Adobe Connect

## Panoramica

Adobe Learning Manager può tenere traccia della partecipazione alle sessioni in aula virtuale di Adobe Connect tramite le visualizzazioni di registrazione. Quando un Allievo salta una sessione dal vivo ma osserva la registrazione su Adobe Connect abbastanza a lungo, Learning Manager contrassegna l’Allievo come partecipante alla sessione. L’Allievo completa quindi il modulo della sessione e può procedere verso il completamento dell’oggetto di apprendimento a cui appartiene la sessione.

Prima di questa funzione, Learning Manager non aveva modo di registrare le presenze degli Allievi che guardavano una registrazione di Connect. Un Allievo che non ha potuto completare una sessione dal vivo non è riuscito a farlo e un Istruttore ha dovuto intervenire e contrassegnare manualmente la partecipazione. Questa funzione rimuove tale passaggio manuale. Adobe Connect segnala chi ha guardato quale registrazione e per quanto tempo e Learning Manager confronta l’ora di orologio con i criteri di completamento impostati per l’account.

Una volta che l’Allievo soddisfa i criteri di completamento per la sessione registrata, gli Allievi vengono contrassegnati nell’app Amministratore.

L’ID e-mail dell’Allievo deve essere lo stesso in Adobe Learning Manager e Adobe Connect, poiché Adobe Learning Manager reindirizza l’Allievo ad Adobe Connect utilizzando lo stesso ID e-mail.
La frequenza di sincronizzazione predefinita e l’intervallo più breve che l’Amministratore dell’integrazione può impostare sono un’ora.


## Chi fa cosa

| Ruolo | Cosa fanno |
|----------------------------|-----------------------------------------------------------------------------------------------------------------------|
| Allievo | Apre la registrazione della sessione e la osserva dopo aver saltato la sessione dal vivo. |
| Istruttore | Avvia la registrazione durante la sessione dal vivo, quindi esistono una registrazione e una trascrizione. |
| Amministratore dell’integrazione | Configura l’account Adobe Connect utilizzato dalla sincronizzazione delle presenze e imposta la pianificazione della sincronizzazione oppure la attiva o disattiva. |
| Autore o responsabile consegna | Pianifica le sessioni in aula virtuale e, per i programmi con più giorni, riutilizza una sala permanente per giorni. |
| Adobe Connect | Acquisisce l’e-mail e la registrazione dell’ora di controllo di ogni Allievo ed espone l’elenco dei visualizzatori di registrazione tramite un’API. |

Ogni ruolo ha una parte separata nel fare in modo che la partecipazione sia basata sulla registrazione.

## Glossario

| Durata | Significato |
|---------------------------------|--------------------------------------------------------------------------------------------------------|
| Sessione aula virtuale | Una sessione aula virtuale ospitata in Adobe Connect. |
| Formazione con istruttore virtuale | I corsi di formazione erogati da un Istruttore attraverso sessioni in aula virtuale. |
| Oggetto di apprendimento | Ad esempio, un corso che contiene il modulo della sessione. |
| Stanza permanente | Una stanza Adobe Connect che può essere riutilizzata per diverse sessioni, ad esempio il giorno 1, il giorno 2 e il giorno 3. |
| Criteri di completamento | Percentuale di registrazione che un Allievo deve guardare per contrassegnare come completata per il modulo. |

## Casi d’uso

### Un Allievo non partecipa a una sessione dal vivo

Un Allievo non può partecipare alla sessione in aula virtuale in tempo reale. Successivamente, l’Allievo apre la sessione in Learning Manager e osserva la registrazione. Una volta che il tempo di osservazione soddisfa i criteri di completamento, Learning Manager contrassegna l’Allievo come partecipante e lo completa senza chiedere aiuto all’Istruttore.

### Allievo che osserva solo parzialmente

Un Allievo apre la registrazione ma osserva meno della condivisione richiesta. I criteri di completamento non sono soddisfatti, quindi Learning Manager non contrassegna l’Allievo come partecipante.

### Sessioni di più giorni su una stanza permanente

Un autore o un manager di consegna pianifica le sessioni per il giorno 1, il giorno 2 e il giorno 3 nella stessa sala Connect permanente. Possono visualizzare e riutilizzare il nome della stanza senza accedere ad Adobe Connect.

## Funzioni principali

| Funzionalità | Che cosa fa |
|-------------------------------|-------------------------------------------------------------------------------------------------------------------------------|
| Partecipazione automatica | Contrassegna un Allievo come partecipante a una sessione aula virtuale basata su Connect quando osserva la registrazione per un periodo di tempo sufficiente a rispettare il limite di soglia prescritto. |
| Guarda il tempo da Connect | Utilizza l’e-mail dell’Allievo e la registrazione dell’ora di controllo acquisita da Adobe Connect. |
| Soglia criteri di completamento | Contrassegna l’Allievo come completato per il modulo quando il tempo di controllo raggiunge la percentuale impostata nei criteri di completamento. |
| Solo ora di controllo effettiva | Conta il tempo che un Allievo ha seguito davvero. Se si trascina la barra di ricerca, il tempo di osservazione non viene aggiunto. |
| Sincronizzazione pianificata | Esegue una pipeline back-end in base a una pianificazione controllata dall’Amministratore dell’integrazione e può essere attivata o disattivata. |
| Visibilità della sala permanente | Mostra il nome della sala Connect a livello di istanza in modo che gli autori possano riutilizzare una stanza permanente nei giorni successivi. |

## Funzionamento del tracciamento della frequenza

*Da un Allievo che apre la registrazione in Learning Manager, il modulo viene contrassegnato come completato.*

### Flusso end-to-end

1. L’istruttore ospita la sessione live in aula virtuale su Adobe Connect e avvia la registrazione. La registrazione e la trascrizione diventano disponibili dopo la sessione.

1. Un Allievo che non ha partecipato alla sessione seleziona la registrazione per visualizzarla. Adobe Connect tiene automaticamente traccia della vista.

1. Adobe Connect acquisisce l’e-mail dell’Allievo e il tempo che l’Allievo ha effettivamente trascorso a guardare.

1. In base alla pianificazione configurata, una pipeline SnapLogic back-end chiama l&#39;API Adobe Connect ed estrae l&#39;elenco dei visualizzatori di registrazione per un determinato fotogramma di tempo. La pipeline utilizza l’account Adobe Connect configurato nell’Amministratore dell’integrazione.

1. Learning Manager mappa ogni visualizzatore sul corso e sul modulo corrispondenti.

1. Learning Manager confronta il tempo di controllo totale dell’Allievo con i criteri di completamento.

1. Se il tempo di osservazione soddisfa i criteri, Learning Manager contrassegna l’Allievo come completato per il modulo. Nel back-end, Learning Manager registra questa situazione compilando il file CSV di livello del corso utente.

>[!NOTE]
>
>Adobe Connect non invia dati a Learning Manager. Learning Manager esegue il pull a livello di istanza di Adobe Connect, ad esempio &quot;questi cinque utenti hanno guardato queste sei registrazioni nelle ultime 24 ore&quot;. La frequenza viene quindi aggiornata dopo l’esecuzione della pipeline successiva, non nel momento in cui l’Allievo termina la visualizzazione.

### Criteri di completamento e ora di controllo

L’Allievo deve controllare almeno la percentuale di registrazione definita dai criteri di completamento. Tenete presenti le seguenti regole:

* La percentuale si applica alla durata della registrazione, non alla durata programmata della sessione. Se una sessione di 15 minuti viene registrata solo per 5 minuti, il tempo richiesto si basa sui 5 minuti. Adobe Connect specifica la durata della registrazione.

* La percentuale viene impostata sul lato Learning Manager. Si tratta di un’impostazione comune a tutto l’account, non di un’impostazione per ogni istanza. Lo stesso tipo di impostazione è già stata applicata alle sessioni dal vivo, ad esempio con una partecipazione dell’80%.

* Adobe Connect registra per quanto tempo l’Allievo ha potuto osservarlo. Il passaggio avanti con la barra di ricerca non conta e Learning Manager elabora il tempo di osservazione trascorso da Connect.

| Criteri di completamento | Lunghezza di registrazione | Tempo di controllo necessario | Risultato |
|-------------------------|------------------------------------|-----------------------|-------------------------------------------------------------|
| 50% | 5 minuti | 2,5 minuti | Contrassegnato come completato dopo 2,5 minuti di osservazione. |
| 50% | 5 minuti (sessione di 15 minuti) | 2,5 minuti | Basato sulla registrazione di 5 minuti, non sulla sessione di 15 minuti. |
| 0% | Qualsiasi | Nessuna dopo l&#39;apertura | È sufficiente aprire la registrazione. |

### Finestra Idoneità

Learning Manager applica la partecipazione basata sulla registrazione solo fino alla data di completamento dell’oggetto di apprendimento. Se l’oggetto di apprendimento non ha una data di completamento, Learning Manager utilizza la data di completamento dell’oggetto di apprendimento principale.

### Pianificare la sincronizzazione

L’Amministratore dell’integrazione controlla la frequenza di esecuzione della pipeline. La pianificazione può essere oraria o settimanale, tra altri intervalli, e l’Amministratore dell’integrazione può attivarla o disattivarla. Per ogni esecuzione viene utilizzato lo stesso account Adobe Connect.

### Cosa cambia

* Quando un utente aggiunge la sala permanente creata per il giorno 1, Learning Manager consente l’accesso a tale stanza. Potranno quindi aggiungere la stessa stanza alle sessioni negli altri giorni.
* Learning Manager mostra il nome della sala Connect a livello di istanza, nei dettagli della sessione accanto all&#39;**URL aula virtuale**.
* Per l’istanza predefinita, Learning Manager mostra la sala configurata durante la creazione del corso.

### Limitazioni e considerazioni

* La partecipazione non è in tempo reale, perché Learning Manager estrae i dati in base a una pianificazione.
* La funzione copre solo le sessioni in aula virtuale basate su Connect.
* Deve esistere una registrazione, quindi l’istruttore deve avviare la registrazione durante la sessione dal vivo.
* Gli Allievi vengono associati tramite l’indirizzo e-mail acquisito da Adobe Connect.
* Se si trascina la barra di ricerca, il tempo di osservazione non viene aggiunto.
* La partecipazione basata sulla registrazione si interrompe alla data di completamento dell’oggetto di apprendimento o dell’oggetto di apprendimento principale.

### Punti da ricordare

* Il tempo di osservazione deve essere maggiore o uguale alla percentuale prescritta (ad esempio, 50% di 5 minuti è 2,5 minuti). Il tempo di visione non aumenta se l’Allievo guarda ripetutamente la sessione ma è ancora al di sotto del tempo di visione prescritto. Tuttavia, il tempo di controllo risulta sommato anche se l’Allievo guarda la sessione in diversi momenti di tempo in più parti e soddisfa i criteri di soglia. Ad esempio, se un Allievo osserva un minuto della sessione il giorno 1 e poi guarda altri 1,5 minuti della sessione il giorno successivo dal punto in cui era partito, il tempo di osservazione si somma. Ciò accade sul lato Adobe Connect.

* I criteri di completamento possono essere configurati a livello di corso e di account. L’effetto è lo stesso della partecipazione alla sessione dal vivo.

* La frequenza di sincronizzazione predefinita e l’intervallo più breve che l’Amministratore dell’integrazione può impostare sono un’ora.

* L’ID e-mail dell’Allievo deve essere lo stesso in Adobe Learning Manager e Adobe Connect, poiché Adobe Learning Manager reindirizza l’Allievo ad Adobe Connect utilizzando lo stesso ID e-mail.

### Domande frequenti

**Q. L’Allievo deve partecipare alla sessione dal vivo?**
**A.** No. Un Allievo che non segue la sessione dal vivo può comunque essere contrassegnato come partecipante guardando la registrazione abbastanza a lungo.

**Q. Quanto della registrazione deve guardare l’Allievo?**
**A.** La percentuale nei criteri di completamento applicata alla durata della registrazione. Ad esempio, al 50% una registrazione di 5 minuti richiede almeno 2,5 minuti di tempo di visione.

**Q. Salta in avanti nel conteggio delle registrazioni?**
**A.** No. Adobe Connect registra l’ora in cui l’allievo ha effettivamente guardato, quindi il trascinamento della barra di ricerca non conta.

**Q. La partecipazione viene segnalata appena l’Allievo termina di guardare?**
**A.** No. Learning Manager estrae i dati del visualizzatore da Adobe Connect in base a una pianificazione, in modo che la partecipazione si aggiorni dopo l’esecuzione della pipeline successiva.

**Q. Adobe Connect invia i dati a Learning Manager?**
**A.** No. Learning Manager esegue il pull. È un meccanismo di pull a livello di istanza di Adobe Connect, non di push.

**Q. In che modo Learning Manager sa quale Allievo ha seguito?**
**A.** Adobe Connect acquisisce l’e-mail dell’Allievo e l’ora di controllo della registrazione. Learning Manager associa questa impostazione al corso e al modulo.

**Q. Chi controlla la frequenza di esecuzione della sincronizzazione?**
**A.** L’Amministratore dell’integrazione imposta la pianificazione e può attivarla o disattivarla.

**Q. La percentuale di completamento è impostata per ogni istanza?**
**A.** No. È un’impostazione comune in tutto l’account.

**Q. Le sessioni con più giorni possono condividere una stanza Connect?**
**A.** Sì. Gli Autori possono riutilizzare la sala permanente creata per il giorno 1 sulle sessioni per gli altri giorni e il nome della stanza viene visualizzato a livello di istanza in Learning Manager.
