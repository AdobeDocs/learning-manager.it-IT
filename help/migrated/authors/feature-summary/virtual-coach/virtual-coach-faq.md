---
description: Trova le risposte alle domande frequenti su creazione di istruzioni virtuali, licenze, sicurezza, privacy dei dati, punteggi e l’esperienza degli Allievi
jcr-language: en_us
title: Domande frequenti su Virtual Coach
exl-id: b8955b04-4655-413a-b570-a05b1f76285c
source-git-commit: 449f25df93867bf4d5ec11af057f8da7c405a09f
workflow-type: tm+mt
source-wordcount: '1904'
ht-degree: 0%
---

# Domande frequenti su Virtual Coach

## Authoring

Risposte alle domande frequenti sulla creazione, la configurazione e la risoluzione dei problemi di un ruolo di istruttore virtuale.

1. **Perché il mio punteggio di gioco di ruolo è pari a zero anche se ho trattato la maggior parte degli argomenti?**
Verifica se per uno degli argomenti è abilitata l&#39;opzione **Crea o interrompi**. Se un Allievo non affronta alcun argomento &quot;Make&quot; o &quot;Break&quot; durante la conversazione, il punteggio finale della simulazione è 0, indipendentemente dal risultato ottenuto su tutto il resto. Riserva Make or Break per uno o due argomenti veramente non negoziabili per evitare che ciò accada in un tentativo ragionevole. Per la configurazione completa, vedere [creare e pubblicare un ruolo di istruttore virtuale](/help/migrated/authors/feature-summary/virtual-coach/create-publish-virtual-coach-role-play.md).

2. **Quanti personaggi può includere un gioco di ruolo multi-persona?**
Fino a quattro persone in uno scenario singolo, ognuna configurata singolarmente con il proprio **Ruolo**, **Personalità** e **Problemi personali**. Utilizza questa opzione quando un Allievo deve consultare più di uno stakeholder nella stessa conversazione, ad esempio un&#39;istanza del comitato per gli acquisti o una revisione del pannello esecutivo.

3. **Come posso scegliere tra voce, chat e video per un gioco di ruolo?**
Dipende dal tipo di persona selezionato. **Le persone di sistema** supportano solo **Voce e video** (un avatar animato con voce vocale) o **Voce**. **Personaggi personalizzati** supportano l&#39;interazione vocale ed è possibile abilitare **Avatar video** separatamente per i personaggi che supportano la modalità Voce e video. Scegli Voce e video per la simulazione più realistica o Voce solo per gli scenari in cui non è necessario un avatar visivo, ad esempio un corso di formazione telefonico.

4. **Come si scrive un messaggio valido per l&#39;Assistente alla creazione condivisa basata su intelligenza artificiale?**
Immettere una breve descrizione che descriva lo scenario, ad esempio `Handling price objections in enterprise sales` o `Pitching our new product to a buying committee`. L&#39;assistente AI pone quindi domande di follow-up per aiutarti a creare la panoramica, il personaggio AI e gli argomenti di valutazione. Fornisci il maggior contesto possibile sulla situazione, sul ruolo e sulle preoccupazioni del personaggio e su come vuoi misurare il successo — più dettagli nella tua descrizione iniziale significa meno avanti e indietro nella chat. Per un modello di messaggio più completo, consulta [raccolta di materiali per un ruolo di istruttore virtuale](/help/migrated/authors/feature-summary/virtual-coach/gather-materials-for-virtual-coach-role-play.md).

5. **È possibile modificare un ruolo dopo la pubblicazione?**
Sì. Le modifiche alle impostazioni del personaggio, agli argomenti e ad altre configurazioni hanno effetto immediato per qualsiasi gioco di ruolo non pubblicato. Se un ruolo è già pubblicato e assegnato agli allievi, ripubblicalo dopo aver apportato le modifiche affinché gli allievi possano vedere la versione più recente.

Per domande generali sul prodotto, sulle licenze e sugli amministratori, consulta le [domande frequenti su Adobe Learning Manager Virtual Coach](/help/migrated/authors/feature-summary/virtual-coach/virtual-coach-faq.md).

## Formazione e conformità

1. **In che modo Virtual Coach protegge i dati dei clienti e degli Allievi?**
I dati dei clienti vengono archiviati utilizzando la crittografia AES-256, protetti in transito utilizzando TLS 1.3+ e separati logicamente da identificatori univoci dei clienti per garantire l&#39;isolamento tra gli ambienti dei clienti. Questi controlli sono convalidati attraverso test di penetrazione annuali da parte di terzi.

2. **Dove vengono archiviati ed elaborati i dati dell&#39;istruzione virtuale?**
I dati dei clienti vengono archiviati nei centri dati dell&#39;UE, a supporto dell&#39;allineamento con i requisiti europei in materia di privacy.

3. **Per quanto tempo Virtual Coach conserva i dati dei clienti e degli Allievi ed è possibile eliminarli?**
I dati della sessione possono essere conservati per la durata del contratto di servizio e i clienti possono configurare i criteri di conservazione specifici dell&#39;azienda. I singoli utenti possono eliminare le proprie registrazioni, gli amministratori possono eseguire eliminazioni in blocco e i dati possono essere esportati prima dell’eliminazione. Sono supportati anche i meccanismi di eliminazione automatica e la registrazione dei controlli.

4. **I contenuti caricati dal cliente vengono utilizzati per scopi diversi dalla generazione del ruolo, ad esempio la formazione sull&#39;intelligenza artificiale o il miglioramento del prodotto?**
No, i dati dei clienti non vengono utilizzati per il training sull&#39;intelligenza artificiale.

5. **In che modo gli istruttori virtuali utilizzano l&#39;IA e quali sono le protezioni disponibili per le risposte generate dall&#39;IA?**
Virtual Coach utilizza l&#39;intelligenza artificiale generativa per creare esperienze di gioco di ruolo interattive. Sono disponibili diverse protezioni, tra cui filtri per i contenuti di Azure OpenAI per categorie come violenza, incitamento all&#39;odio, contenuti sessuali e autolesionismo; tutele di livello immediato e controlli contestuali che mantengono l&#39;intelligenza artificiale concentrata sull&#39;apprendimento e lo sviluppo dei casi d&#39;uso. Vengono anche condotti test di sicurezza dell&#39;intelligenza artificiale e per le richieste sensibili vengono utilizzate salvaguardie come la trasformazione rapida basata sulla sicurezza e il comportamento &quot;chiarisci e poi rifiuta&quot;. Inoltre, gli impegni contrattuali richiedono la divulgazione degli output generati dall&#39;IA e la conformità ai regolamenti applicabili in materia di IA.

6. **Quali standard di privacy e conformità sono supportati da Virtual Coach?**
Virtual Coach supporta le protezioni della privacy relative al GDPR, i controlli di conservazione configurabili, la registrazione dei controlli, le funzionalità di eliminazione degli utenti e l’hosting dei dati basato sull’UE. L&#39;accordo contrattuale richiede anche il rispetto delle leggi e dei regolamenti applicabili, tra cui l&#39;EU AI Act e il California AI Transparency Act (SB-942).

7. **Chi possiede i contenuti caricati su Virtual Coach e i contenuti generati durante una sessione?**
Il cliente possiede il contenuto caricato su Virtual Coach e il contenuto generato durante una sessione.

8. **Dove risiedono i dati di Virtual Coach, all&#39;interno di Adobe Learning Manager o con il provider di servizi Virtual Coach?**
I dati relativi al ruolo sono archiviati nell&#39;infrastruttura cloud del fornitore di servizi Virtual Coach e ospitati nei centri dati dell&#39;UE.

## Prodotto

1. **Come viene attivato Virtual Coach per un cliente Adobe Learning Manager esistente?**
Vedere [Attivazione dell&#39;istruzione virtuale](/help/migrated/administrators/feature-summary/virtual-coach/manage-virtual-coach-usage-billing.md#activatevirtualcoach)

2. **Per quanto tempo è valida l&#39;attivazione dell&#39;istruzione virtuale e come viene rinnovata?**
L’attivazione dell’istruttore virtuale in Adobe Learning Manager è valida per la durata del contratto di abbonamento per componenti aggiuntivi. Non è automaticamente perpetua. La validità viene allineata al periodo di abbonamento.

   **Rinnovo:** per continuare a utilizzare Virtual Coach al termine del periodo di validità del contratto, è necessario rinnovare l&#39;abbonamento. Al momento dell’acquisto, Adobe fornisce una chiave di attivazione che l’amministratore dell’account utilizza per abilitare l’istruzione virtuale nella sezione Fatturazione. Se rinnovi il contratto, riceverai istruzioni e una nuova chiave di attivazione se necessario per mantenere l&#39;accesso ininterrotto.

   Anche i crediti utente attivo mensile (MAU) vengono allocati per ciascun periodo del contratto. Eventuali crediti inutilizzati alla fine del contratto scadono. Non possono essere riportati in un periodo nuovo o rinnovato. L’attivazione dura finché è attivo l’abbonamento a pagamento Virtual Coach e si verifica il rinnovo estendendo l’abbonamento, come gestito tramite l’account Adobe.

3. **Cosa succede ai documenti di origine caricati e ai dati di sessione generati dopo la creazione o il completamento di un ruolo?**
I documenti di origine caricati possono essere utilizzati per creare e configurare scenari di ruolo, personaggi e criteri di valutazione. Una volta completato un ruolo da parte degli Allievi, l’Allenatore virtuale genera risultati di valutazione, punteggi, feedback sull’allenatore e informazioni di completamento a supporto delle attività di apprendimento e reporting. I dati associati ai ruoli sono disponibili in base alle regole di conservazione e al ciclo di vita dei contenuti applicabili.

4. **Gli Allievi possono ritentare un ruolo?**
Sì. Gli Allievi possono ripetere più volte una sessione di gioco dei ruoli per mettere in pratica le proprie abilità, applicare feedback di coaching e migliorare le proprie prestazioni. Dopo aver completato un ruolo, gli Allievi possono rivedere il loro feedback e iniziare un altro tentativo per continuare a sviluppare le proprie abilità.

## Generale

1. **Che cos&#39;è l&#39;istruzione virtuale?**
Virtual Coach è una funzione di coaching e gioco di ruolo basata sull&#39;intelligenza artificiale integrata in Adobe Learning Manager. Consente agli Allievi di praticare conversazioni reali con un personaggio di intelligenza artificiale che risponde in modo intelligente in tempo reale, quindi riceve un report immediato sulle prestazioni che copre ciò che hanno detto e come lo hanno detto. Per una spiegazione completa, vedere [cos&#39;è Virtual Coach](/help/migrated/authors/feature-summary/virtual-coach/what-virtual-coach-is.md).

2. **Chi utilizza l&#39;istruzione virtuale?**
Le organizzazioni utilizzano Virtual Coach per formare rappresentanti commerciali, team di assistenza clienti, agenti di call center, manager e leader, nuovi assunti, partner e dipendenti che apprendono nuovi prodotti o processi. Virtual Coach è disponibile per tutti gli Allievi, gli Autori e gli Amministratori in un account Adobe Learning Manager in cui è stato attivato. Gli Allievi possono accedere e completare le sessioni di gioco dei ruoli, gli Autori creano e pubblicano scenari di gioco dei ruoli e gli Amministratori gestiscono i crediti e visualizzano i report.

3. **Virtual Coach utilizza automaticamente i contenuti Adobe Learning Manager esistenti?**
N. Per ogni gioco di ruolo creato, gli autori devono fornire materiale di riferimento, ad esempio playbook, mazzi di vendita, trascrizioni e materiale per la valutazione, oppure un messaggio scritto. L’istruttore virtuale utilizza tali materiali caricati e le definizioni di persona per guidare la conversazione; non utilizza automaticamente i contenuti già presenti nella libreria dei contenuti o nei corsi. Per sapere cosa preparare, consulta [raccogliere materiali per un ruolo di istruttore virtuale](/help/migrated/authors/feature-summary/virtual-coach/gather-materials-for-virtual-coach-role-play.md).

4. **Quali tipi di ruoli sono disponibili?**
Virtual Coach supporta tre domini: abilitazione alle vendite, sviluppo della leadership e valutazione delle competenze. Gli autori possono scegliere tra modelli predefiniti che coprono scenari quali chiamate di individuazione B2B, chiamate senza preavviso, gestione delle obiezioni, invio di feedback difficili e riduzione dell&#39;escalation dei reclami dei clienti. Gli autori possono anche creare scenari personalizzati da zero utilizzando l’assistente AI. Vedere [creare e pubblicare un ruolo di istruttore virtuale](/help/migrated/authors/feature-summary/virtual-coach/create-publish-virtual-coach-role-play.md).

5. **Quali lingue supporta Virtual Coach?**
Virtual Coach è disponibile in nove lingue per l&#39;interfaccia e i contenuti di simulazione: tedesco (Germania), spagnolo (LATAM), spagnolo (Spagna), francese (Francia), italiano (Italia), portoghese (Portogallo), portoghese (Brasile), olandese (Paesi Bassi) e inglese.

6. **Come vengono concessi in licenza e fatturati gli allenatori virtuali?**
Virtual Coach è disponibile come abbonamento aggiuntivo a Adobe Learning Manager. L’utilizzo viene misurato in Utenti attivi mensili (MAU). Un credito MAU viene utilizzato quando un Allievo avvia un corso in un mese di calendario; le sessioni aggiuntive dello stesso Allievo in quel mese non richiedono crediti aggiuntivi. I crediti inutilizzati alla fine del contratto annuale scadono. Consulta [gestire l&#39;utilizzo e la fatturazione degli istruttori virtuali](/help/migrated/administrators/feature-summary/virtual-coach/manage-virtual-coach-usage-billing.md).

7. **Come viene calcolato il punteggio di un Allievo?**
Ogni sessione genera un punteggio della conoscenza e un punteggio dello stile. Il punteggio della Knowledge Base indica se l’Allievo ha affrontato gli argomenti richiesti e fornito informazioni accurate. Il punteggio di stile riflette il modo in cui l’Allievo comunica, inclusi ritmo, chiarezza, parole di riempimento, forza della frase ed energia vocale. Gli autori impostano il peso di ciascun componente durante la configurazione dello scenario; una configurazione comune è il 70% di conoscenza e il 30% di stile. Consulta [il rapporto sulle prestazioni dell&#39;istruttore virtuale](/help/migrated/learners/feature-summary/virtual-coach/understand-virtual-coach-performance-report.md).

8. **Gli Allievi possono scaricare il report sulle prestazioni?**
Sì. Oltre a visualizzare il report sullo schermo, gli Allievi possono scaricarlo come PDF da conservare per i propri record o da condividere con un Manager.

9. **Un Allievo può ritentare un ruolo?**
Sì. Gli Allievi possono tentare di eseguire un ruolo tutte le volte che lo desiderano. Ogni tentativo è una nuova sessione indipendente e genera un nuovo report sulle prestazioni. Solo la prima sessione di un mese di calendario utilizza un credito MAU.

10. **Gli Allievi possono inviare le proprie sessioni per la revisione da parte di un utente?**
N.

11. **Virtual Coach è disponibile sui dispositivi mobili?**
Virtual Coach è supportato su Adobe Learning Manager per desktop e dispositivi mobili Web e dalle API. Non è disponibile nell’app Adobe Learning Manager per dispositivi mobili (iOS/Android) nella versione corrente.

12. **I dati dell’Allievo vengono utilizzati per addestrare l’IA?**
N. Virtual Coach è ospitato su un’infrastruttura conforme al GDPR e non vengono utilizzati dati personali degli Allievi per addestrare i modelli di intelligenza artificiale.

13. **Qual è la differenza tra una risorsa formativa e un modulo del corso per l’istruttore virtuale?**
Una risorsa formativa è una risorsa autonoma su richiesta a cui gli Allievi possono accedere direttamente dal Catalogo in qualsiasi momento senza essere iscritti a un corso. È possibile accedere a un modulo del corso come parte di una sequenza di corsi strutturata con iscrizione, monitoraggio del completamento e valutazione formale. Lo stesso ruolo può essere pubblicato come risorsa formativa e aggiunto a più corsi contemporaneamente. Consulta [aggiungere un ruolo di istruttore virtuale a un corso](/help/migrated/authors/feature-summary/virtual-coach/add-virtual-coach-role-play-to-course.md).

14. **Come creare un pacchetto di Virtual Coach durante l&#39;implementazione di un nuovo processo o prodotto?**
Raccogli il ruolo svolto all’interno di un corso o percorso di apprendimento insieme ai relativi contenuti di formazione e distribuisci il collegamento al corso tramite e-mail o altre comunicazioni relative alla gestione del cambiamento. Virtual Coach si posiziona meglio come ultimo miglio del corso di formazione: il punto di controllo subito dopo che gli Allievi hanno completato i contenuti correlati, dove dimostrano di poterli applicare, piuttosto che come attività autonoma.

15. **Virtual Coach è supportato nelle implementazioni headless o API?**
Le API pubbliche per il recupero di corsi e risorse formative recuperano anche corsi di formazione virtuale e risorse formative. Il filtro `jobAidType` è disponibile per il recupero delle risorse formative di Virtual Coach. Il contenuto dell’istruttore virtuale è supportato nel lettore headless e i corsi e le risorse formative contenenti il lavoro dell’istruttore virtuale nel lettore Fluidic.

Per domande sulla creazione e la configurazione di un gioco di ruolo, consulta questa pagina con le domande frequenti.
