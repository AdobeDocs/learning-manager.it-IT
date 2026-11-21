---
description: Creazione di un server MCP in Adobe Learning Manager, connessione a Claude o ChatGPT e gestione di credenziali, strumenti, limiti e risoluzione dei problemi
jcr-language: en_us
title: Configurare il server Adobe Learning Manager MCP
exl-id: b5d2c08e-a11e-4f55-9ba5-a652a9575678
source-git-commit: 9d93dbeca8a0c6da5e75e935bbec1ff3476c0a6e
workflow-type: tm+mt
source-wordcount: '1908'
ht-degree: 1%
---

# Configurare il server Adobe Learning Manager MCP

Configurare il server MCP (Model Context Protocol) una volta per l&#39;organizzazione. La configurazione è composta da due parti: crea un server MCP in Learning Manager e collegalo all’assistente AI. Successivamente, gli Allievi accedono a Learning Manager dall’assistente AI e possono utilizzare gli strumenti MCP.

Prima di iniziare, assicurati che:

* Il server MCP è abilitato per l’account Learning Manager. Contatta il tuo Customer Success Manager Adobe o il supporto Adobe per abilitarlo. Fino ad allora, ogni richiesta restituisce 403 Vietato.
* L&#39;amministratore dell&#39;assistente AI dispone dell&#39;autorizzazione per aggiungere e configurare connettori in quella piattaforma.

**Prerequisito:** Il server Model Context Protocol è una funzionalità basata su flag back-end che funziona solo per gli account di livello Ultimate.

## Creazione di un server MCP in Learning Manager

La creazione di un server MCP comporta la configurazione di un&#39;applicazione OAuth e l&#39;assegnazione dell&#39;URL del server MCP, dell&#39;ID client e del segreto client.

1. Accedi a Learning Manager in qualità di Amministratore di integrazione.
2. Nel menu di navigazione, selezionare **Server MCP**.
3. Nell&#39;angolo superiore destro, seleziona **Crea**.

   ![](assets/integration-admin-mcp1.png)

4. Nella pagina **Dettagli applicazione**, immetti quanto segue, quindi seleziona **Avanti**:

   * **Nome applicazione:** Immetti un massimo di 50 caratteri, ad esempio ALM per Claude. Gli Allievi visualizzano questo nome quando autorizzano la connessione, quindi scegli un nome che riconoscono.
   * **Domini di reindirizzamento:** Immettere il dominio di richiamata di ogni assistente dell&#39;intelligenza artificiale, un dominio per riga. Iniziate ognuno con senza includere un tracciato. Questo campo è obbligatorio.
   * **Descrizione:** Inserisci un massimo di 150 caratteri, ad esempio, consente agli Allievi di utilizzare ALM di Claude.

5. Nella pagina **Configurazione strumento**, esamina gli strumenti e le descrizioni utilizzate dagli assistenti AI per decidere quando chiamare ogni strumento. Per modificare una descrizione, selezionare **Azioni** (**...**) \> **Modifica**. Per ripristinare il valore predefinito, selezionare **Ripristina**. Quindi seleziona **Avanti**.
6. Nella pagina **Credenziali client**, copiare l&#39;**URL server MCP**, l&#39;**ID client** e il **Segreto client**. Conservarli in modo sicuro. Servono per collegare il tuo assistente AI.

Il server MCP ha sempre un ambito Allievo, quindi non sono disponibili ambiti da selezionare.

Registra il dominio per ogni assistente AI che intendi connettere.

| **Assistente AI** | **Reindirizza il dominio alla registrazione** | **URL di richiamata completo (riferimento)** |
|----|----|----|
| Claude | [https://claude.ai](https://claude.ai/) e [https://claude.com](https://claude.com/) | <https://claude.ai/api/mcp/auth_callback> |
| ChatGPT | [https://chatgpt.com](https://chatgpt.com/) | <https://chatgpt.com/connector/oauth/&lt;id>\> (ChatGPT visualizza l&#39;ID durante l&#39;installazione) |

Registra domini esatti, ad esempio [https://chatgpt.com](https://chatgpt.com/). Non utilizzare caratteri jolly parziali, ad esempio [https://*chatgpt.com*](https://chatgpt.com)*, perché possono corrispondere a domini non correlati. Per consentire i sottodomini, utilizzare un carattere jolly di etichetta intera, ad esempio* [*https://*.example.com](https://.example.com).

Un server MCP può servire diversi assistenti AI se vengono elencati tutti i rispettivi domini di reindirizzamento. Per revocare l&#39;accesso a un assistente senza influire sugli altri, creare un server MCP separato per ciascuno di essi. Tutti i server utilizzano lo stesso URL del server MCP.

È necessario solo l&#39;URL del server MCP. Claude e ChatGPT scoprono automaticamente gli endpoint OAuth di Learning Manager. Per la configurazione manuale, visualizza **gli endpoint OAuth per il server MCP di Learning Manager**.

## Connetti Claude Pro o Max

Consultare la documentazione di Claude se questi passaggi non corrispondono più all&#39;interfaccia.

>[!NOTE]
>
>La dettaglio delle risposte alle domande poste cambia man mano che le risposte dallo strumento answer_learning_content_question vengono riinquadrate e formattate dai client.

1. In Claude, vai a **Personalizza** \> **Connettori**.
2. Seleziona **Aggiungi** (+), quindi seleziona **Aggiungi connettore personalizzato**.
3. Immetti i dettagli del connettore, quindi seleziona **Continua**:

   * **Nome:** Immetti un nome riconosciuto dagli Allievi, ad esempio Adobe Learning Manager.
   * **URL server MCP remoto:** Immettere l&#39;URL del server MCP dalla pagina Credenziali client, nel formato [https://\[alm-host\]/v1/mcp](https://[alm-host]/v1/mcp).

4. In **Autenticazione**, mantieni **Accedi ora**. Claude legge le impostazioni OAuth di Learning Manager e contrassegna le opzioni corrispondenti come *Rilevate*.
5. In **client OAuth**, seleziona **Usa il tuo client OAuth**. Incolla **ID client** e **Segreto client**.
6. Seleziona **Aggiungi**. Claude apre la pagina di accesso di Learning Manager. Dopo aver effettuato l’accesso, il connettore viene visualizzato come connesso.

>[!NOTE]
>
>Claude etichetta il campo Segreto cliente come facoltativo, ma Learning Manager lo richiede. Se lo lasci vuoto o immetti un valore errato, l’accesso non riesce e viene visualizzato il messaggio &quot;Autorizzazione non riuscita&quot;.

## Collega Claude Team o Enterprise

Solo il proprietario dell&#39;organizzazione o un membro con un ruolo che può gestire i connettori può aggiungere il connettore. I membri non visualizzano mai l’ID client o il segreto client.

>[!NOTE]
>
>La dettaglio delle risposte alle domande poste cambia man mano che le risposte dallo strumento answer_learning_content_question vengono riinquadrate e formattate dai client.

1. In Claude, accedi come proprietario dell&#39;organizzazione o come membro con l&#39;autorizzazione a gestire i connettori.
2. Vai a **Impostazioni organizzazione** \> **Connettori**.
3. Seleziona **Aggiungi**, passa il mouse sopra **Personalizzato**, quindi seleziona **Web**.
4. Immetti il nome e l’URL del server MCP, quindi imposta **Autenticazione** e **Client OAuth** come descritto nei passaggi 4 e 5 della procedura precedente.
5. Seleziona **Aggiungi**.

Il connettore è ora disponibile per la tua organizzazione. Ogni iscritto seleziona **Connetti** e accede a Learning Manager con il proprio account.

## Collega team ChatGPT o Enterprise

>[!NOTE]
>
>La dettaglio delle risposte alle domande poste cambia man mano che le risposte dallo strumento answer_learning_content_question vengono riinquadrate e formattate dai client.

1. Accedi a ChatGPT come proprietario o amministratore dell’area di lavoro.
2. Nella barra laterale sinistra, fai clic su **Plugin**.
3. Fai clic su **Aggiungi** nell&#39;angolo in alto a destra e seleziona **Crea app MCP**.
4. Nella finestra **Nuovo plug-in**, configura la connessione:

   * **Nome:** Adobe Learning Manager o il nome con cui gli Allievi conoscono la piattaforma di apprendimento.
   * **Connessione:** mantenere selezionato **URL server** e immettere [https://\[alm-host\]/v1/mcp](https://[alm-host]/v1/mcp)
   * **Autenticazione:** OAuth


     ![](assets/integration-administrator-mcp1.png)

5. Fai clic su **Impostazioni OAuth avanzate**. ChatGPT rileva automaticamente gli endpoint OAuth ALM.
6. In **Registrazione client**, mantieni il **metodo di registrazione** impostato su **Client OAuth definito dall&#39;utente**, quindi immetti il **ID client OAuth** e il **segreto client OAuth** dal passaggio 1.
7. Controlla l&#39;**URL di richiamata** visualizzato in questo pannello. Il dominio (<https://chatgpt.com>) deve trovarsi nei **domini di reindirizzamento** del server MCP dal passaggio 1.

   ![](/help/migrated/integration-admin/feature-summary/assets/integration-admin-mcp2.png)

**Gli endpoint vengono rilevati automaticamente**

In genere non è necessario modificare gli endpoint OAuth. Se richiesto da ChatGPT, utilizzare: URL di autenticazione [https://\[alm-host\]/oauth/o/authorization](https://[alm-host]/oauth/o/authorization), URL token [https://\[alm-host\]/oauth/token](https://[alm-host]/oauth/token), URL di registrazione vuoto, risorsa [https://\[alm-host\]/v1/mcp](https://[alm-host]/v1/mcp), Allievo ambito:write.

1. Seleziona **Confermo che desidero continuare**, quindi fai clic su **Crea**.
1. Nella finestra **Connetti**, fai clic su **Continua** e accedi ad ALM. La finestra dovrebbe mostrare *Approvato dall&#39;amministratore*.
1. Rendete il plug-in disponibile agli utenti di destinazione nell&#39;area di lavoro.

![](/help/migrated/integration-admin/feature-summary/assets/integration-admin-mcp3.png)

## Autenticazione dell&#39;utente finale

Una volta completata la configurazione del server MCP da parte dell’amministratore, gli allievi aggiungono il connettore ALM dall’elenco dei connettori dell’assistente AI e fanno clic su **Connetti**. Viene aperta la pagina di accesso ALM. Dopo aver effettuato l’accesso (con SSO, se l’account lo utilizza) e aver approvato l’accesso, l’assistente AI è collegato all’account ALM dell’Allievo.

## Ruota il segreto client o revoca l’accesso

Non è possibile rigenerare un segreto client. Per ruotarla:

1. Creare un nuovo server MCP, come descritto in precedenza in questo articolo.
2. Aggiorna il tuo assistente AI con il nuovo ID client e il Segreto client.
3. In **Amministratore dell&#39;integrazione** \> **Server MCP**, selezionare **Azioni** (**...**) \> **Elimina** per il server precedente.

Gli Allievi devono accedere nuovamente dopo il passaggio.

Per disconnettere un assistente AI per tutti gli Allievi, elimina il server MCP dalla stessa pagina.

## Strumenti disponibili

Il server MCP espone i seguenti strumenti. Tutte vengono eseguite con le autorizzazioni dell’Allievo che ha effettuato l’accesso.

<table style="width:100%;">
<colgroup>
<col style="width: 46%" />
<col style="width: 31%" />
<col style="width: 21%" />
</colgroup>
<thead>
<tr>
<th><strong>Strumento</strong></th>
<th><strong>Che cosa fa</strong></th>
<th><strong>Suggerimenti di esempio</strong></th>
</tr>
</thead>
<tbody>
<tr>
<td>search_learning_itemsread-only</td>
<td>Cerca nel catalogo corsi, percorsi di apprendimento, certificazioni, risorse formative, distintivi, abilità, cataloghi e tag. Filtri: tipo, stato dell’Allievo, abilità, tag, catalogo, formato di consegna, prezzo e lingua. Restituisce fino a 10 risultati per pagina.</td>
<td>"Corsi per principianti Python"<br />
"Corsi di formazione gratuiti in classe in francese"</td>
</tr>
<tr>
<td>list_my_learning_enrollssola lettura</td>
<td>Elenca l’apprendimento registrato, in corso e completato dell’Allievo, con stato, avanzamento e scadenza. L’ultima iscrizione è stata effettuata per impostazione predefinita.</td>
<td>"A cosa sono iscritto?"<br />
"Cosa sarà presto?"<br />
"I miei corsi di formazione completati"</td>
</tr>
<tr>
<td>get_learning_objectread-only</td>
<td>Ottiene i dettagli completi di un corso, un percorso di apprendimento, una certificazione o una risorsa formativa in base all'ID, incluse facoltativamente istanze, abilità ed elementi secondari.</td>
<td>"Ulteriori informazioni sul secondo corso"</td>
</tr>
<tr>
<td>get_my_learning_profileread-only</td>
<td>Ottiene il profilo ALM dell’Allievo, inclusi l’account e il Manager.</td>
<td>"Chi è il mio manager in ALM?"</td>
</tr>
<tr>
<td>response_learning_content_questionuses crediti IA</td>
<td>Risponde alle domande sull'argomento del corso utilizzando ALM Learning Assistant, basato sul contenuto del corso con le citazioni. Restituisce un ID di conversazione utilizzato dall'assistente per le domande di completamento.</td>
<td>"Descrizione di TCP e UDP come descritto nel corso sulla rete"</td>
</tr>
<tr>
<td>personalized_learning_path</td>
<td>Fornisce percorsi di apprendimento personalizzati in Adobe Learning Manager in base agli obiettivi, agli argomenti e alle esigenze di apprendimento di un Allievo. Supporta la generazione di consigli sui corsi, il salvataggio di un percorso di apprendimento selezionato nell’account dell’Allievo, l’elenco dei percorsi di apprendimento salvati dell’Allievo (elenco azioni) e l’acquisizione dei dettagli e dei corsi di un percorso di apprendimento salvato tramite il relativo ID (dettagli azione). Aiuta gli Allievi a identificare contenuti di apprendimento pertinenti per lo sviluppo di competenze e il raggiungimento di obiettivi di apprendimento.</td>
<td>"Salva il percorso di apprendimento selezionato nel mio account."</td>
</tr>
</tbody>
</table>

Le conversazioni avviate tramite answer_learning_content_question vengono visualizzate nel report Conversazione basata su IA dell’Allievo, come le conversazioni nell’Assistente all’Allievo.

## Limiti

| **Limite** | **Valore** |
|----|----|
| Risultati per pagina (ricerca e iscrizioni) | Fino a dieci. Usa il cursore restituito per altre pagine. |
| percentuale di risposte_learning_content_question | 10 richieste al minuto per Allievo (sequenza di 5), con un massimo di 2 in corso contemporaneamente |
| Versioni di protocollo MCP supportate | 2025-11-25, 2025-06-18, 2025-03-26 |
| Trasporti | HTTP semplificabile, senza stato (solo POST; nessun flusso di eventi inviato dal server) |

## **Riferimento agli endpoint OAuth**

Claude e ChatGPT li scoprono automaticamente. Sono elencati qui per i clienti o i proxy che li richiedono inseriti manualmente. Sostituire \[alm-host\] con l&#39;host nell&#39;URL del server MCP (host di zona o dominio personalizzato ALM).

| **Valore** | **URL** |
|----|----|
| URL server MCP | [https://\[alm-host\]/v1/mcp](https://[alm-host]/v1/mcp) |
| URL autorizzazione | [https://\[alm-host\]/oauth/o/authorization](https://[alm-host]/oauth/o/authorization) |
| URL token | [https://\[alm-host\]/oauth/token](https://[alm-host]/oauth/token) |
| Aggiorna URL | [https://\[alm-host\]/oauth/token/refresh](https://[alm-host]/oauth/token/refresh) |
| Base server di autorizzazione | &lbrack;https://\[alm-host](https://[alm-host)\] |
| Risorsa | [https://\[alm-host\]/v1/mcp](https://[alm-host]/v1/mcp) |
| Ambito | Allievo:write |

## Risoluzione dei problemi

| **Sintomo** | **Causa e correzione** |
|----|----|
| Reindirizzamento non registrato durante l’accesso | Il dominio di richiamata dell&#39;assistente AI non si trova nei **domini di reindirizzamento** dell&#39;applicazione. Aggiungilo (ad esempio, <https://claude.ai>) e riprova. |
| L’accesso riesce, quindi l’assistente segnala che l’autorizzazione non è riuscita (client non valido) | Il segreto client immesso nell&#39;assistente non corrisponde all&#39;applicazione. Copiarlo nuovamente da ALM, verificare la presenza di spazi aggiuntivi e riconnettersi. |
| Tutte le richieste restituiscono 403 Non consentito | Il server MCP non è abilitato per l&#39;account. Contatta l’assistenza tecnica di Adobe. |
| Connesso come utente ALM errato | Il browser aveva già una sessione ALM. Disconnetti, esci da ALM (o utilizza una finestra privata) e riconnettiti. |
| &quot;Limite di velocità superato&quot; dallo strumento Domande e Risposte | L’Allievo ha superato il limite del tasso di domande e risposte. Attendere un minuto e riprovare. |
| L&#39;assistente chiede di accedere di nuovo | Il token dell’Allievo è scaduto o è stato revocato. Fai di nuovo clic su **Connetti**. |

## Domande frequenti

### **Gli Allievi possono utilizzare il server MCP senza che un amministratore lo configuri?**

N. Un amministratore dell&#39;integrazione deve creare un server MCP in ALM (passaggio 1), perché il server MCP non supporta la registrazione dinamica dei client.

### **È possibile utilizzare un dominio personalizzato?**

Sì. Se l&#39;account ALM dispone di un dominio personalizzato, utilizzalo al posto di \[alm-host\] in tutti gli URL.

### **Quali ruoli ALM possono utilizzare il server MCP?**

Qualsiasi utente ALM può connettersi. Gli strumenti agiscono nel contesto dell’Allievo e i controlli delle autorizzazioni di ALM si applicano a ogni richiesta.
