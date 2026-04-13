---
description: Scopri le nuove funzioni e i miglioramenti nella versione di aprile 2026 di Adobe Learning Manager, comprese le modifiche a livello di API e webhook
jcr-language: en_us
title: Novità della versione di aprile 2026 di Adobe Learning Manager
source-git-commit: f4ff53bf053b2c8c756961af990505d23ab22db3
workflow-type: tm+mt
source-wordcount: '1768'
ht-degree: 0%

---


# Novità della versione di aprile 2026 di Adobe Learning Manager

**Per gli Allievi:** il lettore Fluidic ora mostra il nome del modulo successivo e un pulsante Esci chiaro. La lingua del lettore può essere impostata tramite LTI per un’esperienza uniforme su più piattaforme. Il nome del parametro personalizzato è &#39;locale&#39; e accetta il codice delle impostazioni internazionali. Ad esempio, locale=fr-FR. Il contenuto di Captivate include un sommario unificato, i segni di graduazione di completamento a livello di diapositiva e le esportazioni di note affidabili. Il supporto multilingue è disponibile per risorse formative, domande sull’elenco di controllo e tracce di testo video (VTT). L’Assistente all’intelligenza artificiale consente agli Allievi di ottenere risposte all’interno dell’esperienza di apprendimento.

**Per amministratori e autori:** il connettore Zoom supporta più sessioni VILT simultanee. I corsi condivisi negli account condivisi tra pari visualizzano l’autore reale invece di &quot;Autore esterno&quot;. Gli amministratori possono limitare l’avvio dei moduli. Le date di scadenza degli oggetti di apprendimento sono esposte nelle API degli Allievi. I moduli dell’elenco di controllo supportano il punteggio ponderato, il testo multilingue delle domande e i commenti facoltativi dei revisori. I certificati personalizzati offrono un editor drag-and-drop con campi dinamici e sfondi generati dall’intelligenza artificiale. Experience Builder non connesso consente di creare pagine di apprendimento pubbliche senza richiedere l’accesso.

**Per gli istruttori:** genera codici QR per l&#39;iscrizione e la partecipazione alla sessione dell&#39;istanza. Aggiungi commenti o feedback durante la valutazione dell’elenco di controllo.

**Report e analisi:** il contenuto SCORM può ora segnalare più tentativi di quiz nel report L2. Il calcolo del tempo impiegato per l’apprendimento è stato migliorato nelle Trascrizioni allievi. I report Trascrizione Allievo per gli Amministratori sono stati aggiornati. Sono disponibili miglioramenti della ricerca avanzata.

**Metodo di accesso:** Scopri come funziona l’accesso OpenID Connect in Adobe Learning Manager per Allievi, Autori e Amministratori. OpenID Connect (OIDC) è un metodo di accesso comune basato su standard Web. Molte organizzazioni utilizzano
un provider di identità (ad esempio, Okta, Google Workspace o Microsoft Entra ID) per dipendenti e partner.

Per ulteriori informazioni, visualizzare [accedere con OIDC](/help/migrated/oidc.md).

## Webhook e migrazione in alternative ed equivalenti

### Webhook

Quando un Allievo completa un corso tramite un’alternativa o una relazione, ALM attiva un evento webhook separato dal webhook di completamento del corso standard. Ciò garantisce che le integrazioni possano rispondere in modo diverso a completamenti alternativi, se necessario. Gli eventi webhook vengono attivati anche quando si verifica un completamento retroattivo o un incompletamento retroattivo, che copre gli aggiornamenti storici e le modifiche delle relazioni.

Per ulteriori informazioni, visualizza [Webhook](/help/migrated/integration-admin/feature-summary/webhooks.md#webhooks-for-alternates).

### Migrazione

Il modello di dati basato su CSV e il comportamento di migrazione per l’introduzione dell’equivalenza degli oggetti di apprendimento (LO) nel sistema sono descritti in [Webhook](/help/migrated/integration-admin/feature-summary/migration-manual.md#migration-for-alternates-and-equivalents).

## Rimozione automatica degli utenti eliminati

La rimozione automatica degli utenti eliminati è una funzione che rimuove i dati per gli utenti che sono già stati eliminati in ALM. La rimozione avviene dopo un periodo di conservazione configurabile, concentrandosi sulle operazioni in blocco in modo che gli account dei clienti di grandi dimensioni possano essere gestiti in modo efficiente senza compromettere le prestazioni.

Per ulteriori informazioni, visualizza [Rimozione automatica degli utenti eliminati](/help/migrated/administrators/feature-summary/purge-users.md#auto-purge-of-deleted-users).

## Imposta il controllo del tempo di accesso del modulo

Il miglioramento consente agli Autori e agli Amministratori di Adobe Learning Manager di definire una finestra temporale durante la quale gli Allievi possono avviare un modulo. Al di fuori della finestra di inizio/fine configurata, il modulo rimane visibile nella struttura del corso, ma gli allievi non possono avviarlo.

Per ulteriori informazioni, vedere [Impostare il controllo del tempo di accesso del modulo](/help/migrated/administrators/feature-summary/module-access-time-control.md).

## Modifiche alle Trascrizioni Allievi

Questa versione migliora il report Trascrizioni apprendimento (LT) con un supporto più chiaro per la conformità e la verifica.

* Una nuova colonna Metodo di completamento in Admin LT mostra se i completamenti sono diretti, alternativi o revocati, mentre i completamenti alternativi influenzano ora lo stato, la data di completamento e l’origine di completamento utilizzando le date ereditate dai corsi di formazione sorgente e aggiornando quando le origini vengono revocate o si verificano completamenti diretti.
* Le alternative revocate adeguano automaticamente lo stato, la data di completamento e l&#39;origine di completamento quando tutte le relazioni idonee vengono rimosse con l&#39;opzione di incompletamento retroattivo abilitata.
* Il feedback dei revisori dai moduli dell’elenco di controllo è standardizzato nella colonna delle osservazioni del revisore rinominata tra i LT degli Amministratori e degli Allievi e tutti i canali di esportazione.
* Infine, i calcoli del tempo di apprendimento consentono di distinguere meglio il tempo di attività da quello di inattività, migliorando l&#39;accuratezza dei report relativi al coinvolgimento e alla conformità.

Per ulteriori informazioni, visualizza [Modifiche nel report Trascrizione Allievo](/help/migrated/administrators/feature-summary/reports/changes-in-learner-transcript.md).

## Elenco di controllo con funzionalità di creazione dei commenti per il revisore

Questa funzione consente ai revisori di aggiungere commenti o feedback durante la valutazione dell’elenco di controllo. Puoi fornire un feedback personalizzato e actionable per ogni Allievo. Puoi anche scegliere di visualizzare il tuo nome con i tuoi commenti per la trasparenza. Tutti i commenti vengono salvati nella trascrizione dell’Allievo e inclusi nei report dell’elenco di controllo.

Per ulteriori informazioni, visualizzare [Configurare l&#39;elenco di controllo con commenti](/help/migrated/authors/feature-summary/courses.md#checklist-with-commenting).

## Supporto multilingue per elenco di controllo

Questa funzione consente di creare e gestire moduli di elenchi di controllo in più lingue. Ogni domanda, istruzione e criterio dell’elenco di controllo può essere tradotto, in modo che revisori e allievi interagiscano con l’elenco di controllo nella lingua che preferiscono. Il sistema visualizza l’elenco di controllo nella lingua dei contenuti selezionata dall’utente, migliorando l’accessibilità e la conformità per i team globali.

Visualizza [Crea elenco di controllo multilingue nei moduli](/help/migrated/authors/feature-summary/courses.md#create-a-multi-language-checklist)

## Ponderazione delle domande nell’elenco di controllo per le valutazioni dell’istruttore

Questa funzione consente di assegnare punteggi massimi (ponderazione) diversi a ciascuna domanda dell’elenco di controllo. È possibile riflettere la diversa importanza o difficoltà di ciascuna domanda, il che supporta valutazioni più accurate e significative. Il sistema calcola il punteggio totale in base ai dati immessi e determina se l’Allievo supera o non supera i criteri impostati.

Visualizza [Domande sull&#39;elenco di controllo ponderato](/help/migrated/authors/feature-summary/courses.md#how-to-create-a-weighted-checklist)

## Certificati personalizzati

I certificati personalizzati in Adobe Learning Manager (ALM) consentono ad amministratori e autori di progettare, gestire ed emettere certificati personalizzati per gli Allievi.

La funzione include un editor drag-and-drop, campi dinamici, supporto multilingue e sfondi generati dall&#39;intelligenza artificiale, consentendo alle organizzazioni di creare certificati con marchio senza competenze tecniche.

Visualizza [Certificati personalizzati di progettazione](/help/migrated/administrators/feature-summary/create-customize-certificate.md)

## Esperienza senza accesso in Experience Builder

L’esperienza senza accesso in Experience Builder consente alle organizzazioni di visualizzare i contenuti di apprendimento e le pagine del portale a tutti i visitatori, inclusi quelli che non hanno effettuato l’accesso. Questa funzione è progettata per attirare, informare e coinvolgere i potenziali Allievi offrendo un’anteprima fluida e con marchio delle offerte di formazione prima di richiedere l’accesso o l’iscrizione.

Visualizza [Esperienza senza accesso in Experience Builder](/help/migrated/administrators/feature-summary/experience-builder/non-logged-in-experience.md)

## Miglioramenti della ricerca avanzata

I risultati della ricerca in Ricerca avanzata sono ora più accurati e pertinenti. Le corrispondenze esatte delle parole chiave vengono classificate di livello superiore sia nella ricerca di contenuti che nei metadati, rendendo più facile per gli Allievi trovare con precisione ciò che stanno cercando.

Gli Allievi possono ora vedere nei risultati di ricerca anche gli Oggetti di apprendimento a cui sono stati iscritti, anche se non fanno parte di un catalogo accessibile, garantendo che non vadano persi contenuti pertinenti. Inoltre, la classificazione delle risorse formative è stata migliorata sia nella ricerca avanzata che nella ricerca all’interno dei contenuti, superando più rapidamente le risorse più rilevanti.

## Risorse formative multilingue

Le risorse formative multilingue in Adobe Learning Manager (ALM) consentono agli autori e agli amministratori di fornire documenti di supporto, guide o risorse in più lingue all&#39;interno di una singola voce della risorsa formativa. Gli Allievi di diverse aree geografiche possono accedere ai materiali pertinenti nella lingua preferita, migliorando la comprensione, la conformità e l’esperienza dell’utente.

Per ulteriori informazioni, vedere [Aggiungere risorse formative multilingue](/help/migrated/authors/feature-summary/job-aids.md#create-a-multilingual-job-aid).

## Supporto di tracce di testo video (VTT) multilingue (per autori)

Il supporto delle tracce di testo video (VTT) multilingue in Adobe Learning Manager consente agli autori di fornire sottotitoli e didascalie per contenuti video e audio in più lingue. Questa funzione semplifica la localizzazione, rendendo i corsi di formazione accessibili a un pubblico globale e garantendo la conformità agli standard di accessibilità. Gli autori possono generare, tradurre, rivedere e modificare automaticamente i file VTT direttamente all’interno della piattaforma.

Per ulteriori informazioni, consulta [Supporto multilingue per il VTT](/help/migrated/authors/feature-summary/content-library.md#multi-lingual-vtt-support).

## Mostrare l’autore originale per i corsi condivisi negli account condivisi tra pari

Quando un corso viene condiviso tramite il catalogo con un account condiviso tra pari, Adobe Learning Manager attualmente etichetta l’autore come &quot;Autore esterno&quot; nelle viste Allievo, Amministratore e Autore dell’account di ricezione. Ciò può creare difficoltà per gli Allievi e gli Amministratori, in particolare nelle grandi aziende, poiché diventa difficile identificare e contattare il proprietario dei contenuti appropriato quando si verificano problemi o domande.

Questo miglioramento garantisce che le informazioni dell’Autore vengano conservate e rese disponibili per i corsi condivisi negli account condivisi tra pari, anziché essere sostituite da un segnaposto generico.

### Novità

Mostra il nome dell’autore effettivo per i corsi condivisi negli account condivisi tra pari

Per i corsi condivisi tramite cataloghi esterni o condivisi tra pari, il nome dell’autore originale dall’account di origine viene ora visualizzato nell’account di destinazione anziché come &quot;Autore esterno&quot;.

Questo vale per:

* App Allievo (scheda del corso o dettagli del corso).
* Visualizzazioni Amministratore e Autore durante l’anteprima come Allievo.

Per ulteriori informazioni, visualizza la visualizzazione del nome dell’autore [per i corsi condivisi](/help/migrated/administrators/feature-summary/peer-account.md#author-name-display-for-shared-courses-including-previously-acquired-courses).

## Equivalenti e alternative

Offre un&#39;esperienza di apprendimento senza problemi ed elimina i corsi di formazione ridondanti con Equivalenti e Alternative in ALM. Questa nuova funzionalità consente agli amministratori di configurare regole unidirezionali (alternative) o bidirezionali (equivalenti), in cui il completamento di un corso di formazione garantisce automaticamente il completamento alternativo per un altro corso. Progettata per semplificare ampi ecosistemi di apprendimento, questa funzione garantisce agli Allievi di ignorare i contenuti già acquisiti e alle organizzazioni di ridurre drasticamente i ticket di supporto per gli Amministratori, eliminare le modifiche manuali e mantenere un record degli Allievi più preciso e pulito.

Per ulteriori informazioni, vedere [Equivalenti e alternative](/help/migrated/administrators/feature-summary/alternates-equivalence.md).

## Codici QR dell’Istruttore per iscrizione e partecipazione a sessioni di esempio

Gli istruttori possono generare essi stessi codici QR per:

* Iscrizione istanza del corso,
* la partecipazione alla sessione, o
* Iscrizione e partecipazione insieme

a livello di sessione. È progettato per le situazioni in cui gli Allievi entrano in un’aula fisica o ibrida e richiedono un’opzione rapida e autonoma per iscriversi e registrare la partecipazione utilizzando un codice QR.

Per ulteriori informazioni, visualizza [Scarica codici QR per l’iscrizione e la partecipazione degli Allievi](/help/migrated/instructors/feature-summary/learners.md#download-qr-codes-for-learner-enrollment-and-attendance).

## Inviti del calendario (ICS) con collegamenti sessione

Adobe Learning Manager include il collegamento di partecipazione alla **sessione direttamente negli inviti del calendario (file ICS)** inviati ad allievi e istruttori. Ciò consente ai partecipanti di partecipare alle sessioni direttamente dal proprio calendario senza cercare l’e-mail della sessione.

Questo miglioramento migliora l&#39;esperienza per i client di calendario come **Gmail** e **Outlook**.

Per ulteriori informazioni, visualizzare [Inviti del calendario con collegamenti di sessione](/help/migrated/instructors/feature-summary/learners.md#joining-a-session-from-gmail).

## Assistente AI per gli Allievi

L’Assistente AI (Beta) per gli Allievi consente loro di trovare rapidamente le risposte dai contenuti di apprendimento assegnati senza sfogliare l’intero corso. Puoi porre domande in un linguaggio semplice e ricevere risposte accurate e mirate con collegamenti sorgente al contenuto del corso pertinente.

Le funzionalità, gli scenari supportati e le limitazioni possono cambiare con l&#39;evolversi della funzionalità. L&#39;Assistente all&#39;intelligenza artificiale è un compagno di chat generativo in Adobe Learning Manager basato sull&#39;intelligenza artificiale che fornisce risposte rapide e precise utilizzando i contenuti di apprendimento affidabili. Include citazioni in modo da conoscere sempre la fonte delle informazioni.

Visualizza [Assistente IA per gli Allievi](/help/migrated/learners/feature-summary/learner-ai-assistant.md)


## Modifiche API nella versione

La versione di aprile 2026 di Adobe Learning Manager introduce miglioramenti mirati all’API pubblica per alternative ed equivalenti, accesso con finestra di tempo ai contenuti, tentativi di quiz basati sui contenuti, esperienze senza accesso e gestione delle risorse formative. Le modifiche sono state progettate per essere ampiamente compatibili con le versioni precedenti, consentendo al contempo integrazioni più precise.

Visualizza [Modifiche API nella versione di aprile](/help/migrated/api-changes-alm.md)

## Requisiti di sistema

Visualizza [requisiti di sistema di Adobe Learning Manager](/help/migrated/system-requirements.md).

## Note sulla versione

Consulta le [note sulla versione](/help/migrated/release-note/release-notes.md) per gli aggiornamenti più recenti.

## Versioni precedenti di Adobe Learning Manager

* [Adobe Learning Manager versione di ottobre 2025](/help/migrated/whats-new-october-2025.md)
* [Versione di maggio 2025 di Adobe Learning Manager](/help/migrated/whats-new-may-2025.md)
