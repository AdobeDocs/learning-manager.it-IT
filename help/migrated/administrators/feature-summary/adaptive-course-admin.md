---
description: Consegna di un corso a più gruppi di destinatari controllando i moduli visualizzati da ciascun Allievo e quelli richiesti in base ai gruppi di utenti a cui appartiene.
jcr-language: en_us
title: Corsi adattivi in Adobe Learning Manager
contentowner: mmanuel
source-git-commit: ffaf107e8077b6a6270fa2f8afc76e721d393702
workflow-type: tm+mt
source-wordcount: '1532'
ht-degree: 0%

---


# Corsi di adattamento in Adobe Learning Manager

I corsi adattivi in Adobe Learning Manager consentono di fornire un corso a più gruppi di destinatari controllando quali moduli vede ciascun Allievo e quali sono richiesti, in base ai gruppi di utenti a cui appartiene.

Anziché creare corsi separati per ogni ruolo, area geografica o profilo di conformità, un singolo corso adattivo presenta dinamicamente il contenuto corretto all’Allievo giusto.

## Quali problemi possono risolvere i corsi adattivi

Le organizzazioni che formano dipendenti di grandi dimensioni e diversificati devono affrontare una sfida comune: la privacy dei dati, l’etica del posto di lavoro e la sicurezza devono raggiungere gli Allievi con ruoli, sedi o obblighi di conformità diversi.

Questo crea duplicazioni: gli autori mantengono più corsi quasi identici, i report sono frammentati e, quando il contenuto principale cambia, ogni copia deve essere aggiornata.

Un corso adattivo risolve questo problema consentendo agli Autori di configurare le regole di visibilità e completamento a livello di modulo, associate ai gruppi di utenti. Un corso serve ogni pubblico contemporaneamente.

### Scenari comuni

- Un corso sulla conformità ha un modulo principale per tutti i dipendenti più moduli aggiuntivi specifici per ogni giurisdizione. Ogni Allievo vede solo le aggiunte che si applicano alla sua posizione.
- Un corso per neoassunti mostra moduli diversi a dipendenti, manager e appaltatori. Ogni ruolo vede solo ciò che gli interessa.
- Un corso sulla sicurezza aggiunge un nuovo modulo obbligatorio a metà anno. Gli amministratori attivano un aggiornamento del completamento in modo che tutti gli Allievi completati in precedenza debbano eseguire il nuovo modulo per rimanere conformi.

### Esempio del mondo reale

Un&#39;organizzazione mette in atto un corso di conformità obbligatorio per tutta la forza lavoro. Il corso contiene sette moduli:

- Due moduli si applicano a tutti i dipendenti.
- Due moduli si applicano solo ai manager delle persone.
- Due moduli si applicano solo ai singoli collaboratori con ruoli tecnici.
- Un modulo si applica solo agli amministratori senior e superiori.

## Funzionamento della visibilità e del completamento dei moduli

Ogni modulo di contenuto di un corso adattivo dispone di due impostazioni:

**Visibile a:** gruppi di utenti che possono visualizzare il modulo. Gli Allievi in questi gruppi visualizzano il modulo nel corso e possono accedervi, ma il suo completamento viene conteggiato solo se sono anche in **Obbligatorio per**.

**Obbligatorio per:** gruppi di utenti per i quali il modulo è richiesto per completare il corso. Un modulo elencato in **Obbligatorio per** è automaticamente visibile a tali gruppi; non è necessario aggiungere gli stessi gruppi a entrambe le impostazioni.

Un modulo è in uno dei tre stati per ogni determinato Allievo in un qualsiasi momento:

| Stato | Come viene determinato | Conta per il completamento? |
|---|---|---|
| Obbligatorio | L’Allievo appartiene a un gruppo di utenti elencato in **Obbligatorio per** | Sì - deve essere completato |
| Facoltativo | L’Allievo è in un gruppo con **Visibile a** ma non **Obbligatorio per** | No - visibile e accessibile ma non richiesto |
| Nascosto | L’Allievo non è in alcun gruppo in nessuna delle due impostazioni | Non visibile all’Allievo |

## Caratteristiche di un corso di adattamento

La caratteristica fondamentale dei corsi adattativi è che il corso valuta il profilo dell’Allievo in modo continuo, non solo al momento dell’iscrizione.

Quando il gruppo di utenti di un Allievo cambia durante l’iscrizione:

- I moduli non più visibili nel nuovo gruppo di utenti scompaiono immediatamente.
- Se un modulo appena visibile è obbligatorio per il nuovo gruppo di utenti, viene aggiunto al requisito di completamento.
- Se un modulo precedentemente obbligatorio non è più obbligatorio, viene rimosso dal suo requisito di completamento.
- I moduli completati in precedenza restano completati. Una modifica del profilo non reimposta il lavoro già eseguito.

### Annullamento automatico dell’iscrizione

Se una modifica del gruppo di utenti rimuove tutti i moduli obbligatori di un Allievo, l’Allievo viene automaticamente annullato dall’iscrizione al corso.

### Completamento automatico

Se una modifica del gruppo di utenti rimuove tutti i moduli obbligatori incompleti rimanenti da un Allievo in corso, il corso viene completato automaticamente per tale Allievo.

Se una modifica del profilo determina nuovi moduli obbligatori che l’Allievo non ha completato, un Amministratore può attivare un completamento di aggiornamento per ripristinare il completamento esistente e richiedere all’Allievo di completare i nuovi moduli.

## Cosa si adatta e cosa rimane lo stesso

Le regole adattive si applicano solo ai **moduli di contenuto**. Quanto segue si applica a tutti gli Allievi iscritti, indipendentemente dal gruppo di utenti:

- **Moduli di preparazione:** visualizzati da tutti gli allievi prima dell’inizio del contenuto principale.
- **Moduli di verifica:** disponibili per tutti gli Allievi. Il completamento di un test comporta il completamento del corso indipendentemente dallo stato del modulo del contenuto.
- **Risorse formative e risorse:** visibili a tutti gli Allievi iscritti in qualsiasi momento.

## Disponibilità funzionalità

La funzione del corso adattivo è controllata da un flag a due livelli a livello di account. Per abilitare questa funzione per il tuo account, contatta il tuo team per gli account Adobe.

Una volta attivato il flag dell’account:

- Durante la creazione o la modifica di un corso diventa disponibile un interruttore **Regole di completamento e visibilità**.
- L’attivazione dell’interruttore attiva il pannello di configurazione adattiva.

**Attenzione:** l&#39;abilitazione del flag di funzionalità adattiva è **irreversibile**. Una volta attivata a livello di account, non può essere disattivata.

## Condivisione catalogo

I corsi adattivi possono essere aggiunti ai cataloghi all’interno del tuo account. Quando un catalogo viene condiviso esternamente con un account condiviso tra pari, i corsi adattivi vengono automaticamente esclusi dal contenuto condiviso.

>[!NOTE]
>
>Quando un percorso di apprendimento o una certificazione contenente un corso adattivo viene condiviso esternamente, l’account ricevente vede il percorso di apprendimento o la certificazione nel proprio catalogo, ma il corso adattivo al suo interno non viene visualizzato. L’oggetto di apprendimento non viene escluso completamente; solo il componente del corso adattivo viene rimosso dalla versione condivisa. Gli autori nell’account di destinazione devono tenere presente che l’oggetto di apprendimento condiviso può avere meno moduli rispetto alla versione di origine.

## Configurazioni supportati

| Configurazione | Supportato? |
|---|---|
| Corso adattivo in un percorso di apprendimento regolare | Sì (vedi nota sotto) |
| Corso adattivo in un percorso di apprendimento flessibile | Sì |
| Corso adattivo in un percorso di apprendimento adattivo | No |
| Corso adattivo in una certificazione | Sì (non consigliato per certificazioni ricorrenti) |
| Iscrizione multipla | No |
| Passaggio di istanza | Sì |
| Condivisione di cataloghi (tra account) | No |
| Regole di visibilità sui moduli di verifica o di preparazione alla lavorazione | No |
| Regole di visibilità sui moduli di contenuto di base | Sì |

>[!NOTE]
>
>Quando un corso adattivo viene incluso in un percorso di apprendimento **ordinato**, gli allievi che non dispongono di moduli visibili nel corso adattivo, in quanto il gruppo di utenti non corrisponde alle regole di visibilità di alcun modulo, non possono completare tale corso. In un percorso di apprendimento ordinato, questo impedisce a tutti gli elementi successivi di diventare accessibili. Per evitare ciò, assicurati che ogni Allievo iscritto al percorso di apprendimento appartenga ad almeno un gruppo di utenti che abbia visibilità su almeno un modulo in qualsiasi corso adattivo nel percorso.

Inoltre, non incorporare un percorso di apprendimento che contiene un corso adattivo all’interno di un percorso di apprendimento di ordine superiore (nidificato). In questa configurazione, se un Allievo non ha moduli visibili o obbligatori nel corso adattivo, il lettore incorporato potrebbe non rispondere, impedendo la navigazione attraverso il contenuto rimanente. Questo comportamento verrà affrontato in una versione futura.

>[!NOTE]
>
>Quando un Allievo viene rimosso automaticamente da un corso adattivo all’interno di un percorso di apprendimento **normale**, in quanto una modifica del gruppo di utenti ha rimosso tutti i moduli visibili, il percorso di apprendimento principale rimane nello stato di iscrizione. L’iscrizione al percorso di apprendimento non viene annullata automaticamente. L’Allievo vedrà il percorso di apprendimento come iscritto nella trascrizione anche se il corso adattivo al suo interno non è più accessibile. Se i casi di utilizzo richiedono che l’iscrizione al percorso di apprendimento principale venga annullata anche quando il corso adattivo è annullato, valuta la possibilità di utilizzare un **percorso di apprendimento adattivo** anziché un percorso di apprendimento regolare per contenere il corso adattivo.

## Abilitare i corsi adattivi per l’account

Attiva l’apprendimento adattivo in modo che gli Autori possano creare corsi che mostrano moduli diversi a diversi Allievi in base all’iscrizione al gruppo di utenti.

## Prima di attivare

- **Permanente:** una volta attivato, l’apprendimento adattivo non può essere disattivato per l’account.
- **Influenza simultanea su corsi e percorsi di apprendimento:** Lo stesso flag che abilita i corsi adattivi consente anche i percorsi di apprendimento adattivi.
- **I corsi esistenti non vengono modificati:** solo i corsi appena creati possono essere resi adattativi. Nessun corso regolare esistente viene convertito automaticamente.
- **Gli autori visualizzano immediatamente l&#39;opzione:** non appena si esegue il salvataggio, il tipo di corso adattivo viene visualizzato nel flusso di lavoro di creazione.
- **Provisioning a due livelli:** se per l&#39;account è stato eseguito il provisioning per l&#39;apprendimento adattivo, l&#39;opzione risulterà abilitata e bloccata. Non può essere modificato dall&#39;interfaccia utente. Se l’account non è stato abilitato, l’impostazione non è visibile. Contatta l&#39;Adobe per richiedere il provisioning.

## Abilita corsi adattivi

1. Accedi a Adobe Learning Manager come amministratore.
2. Seleziona **Impostazioni** nel riquadro di navigazione a sinistra.
3. Selezionare **Generale**.
4. Passa alla sezione **Regole di visibilità e completamento**. Se l’apprendimento adattivo è stato abilitato per la tua organizzazione, l’opzione apparirà bloccata, come mostrato:

![](assets/image_0001.png)

Apprendimento adattivo è ora attivo per il tuo account. Gli Autori possono creare immediatamente corsi adattativi e percorsi di apprendimento adattativi.

## Cosa cambia dopo l’attivazione

Dopo aver attivato l’apprendimento adattivo:

- Durante la creazione di un corso, oltre al tipo di corso normale esistente, gli autori visualizzano un’opzione **Regole di visibilità dei contenuti e di completamento**.
- Ogni modulo di contenuto in un corso adattivo può essere configurato con **regole facoltative** e **regole obbligatorie** per i gruppi di utenti.
- Gli Allievi iscritti a un corso adattivo visualizzano solo i moduli che i loro gruppi di utenti rendono visibili.
- Tutti i corsi regolari esistenti rimangono invariati.

## Risoluzione dei problemi

- **La sezione delle regole di visibilità e completamento non è visibile in Impostazioni:** È necessario eseguire il provisioning della funzionalità nel backend prima che venga visualizzato l&#39;interruttore. Contatta il rappresentante del tuo account Adobe o il supporto Adobe per richiedere l&#39;accesso.
- **L&#39;interruttore è già abilitato e appare bloccato:** Apprendimento adattivo è stato abilitato al momento del provisioning dell&#39;account. Non è necessaria alcuna azione. Gli Autori possono già creare corsi adattivi.
