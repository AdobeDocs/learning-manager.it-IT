---
description: Scopri come Adobe Learning Manager utilizza NRPS per sincronizzare gli attributi personalizzati degli Allievi da una piattaforma LTI 1.3 nei profili degli Allievi come campi attivi
jcr-language: en_us
title: Supporto LTI per NRPS
exl-id: 4c972319-b8ce-4f2d-9ccb-1b93c6cc6ac0
source-git-commit: 92be9eb8ece6d083efe595894a492540cd96eead
workflow-type: tm+mt
source-wordcount: '1845'
ht-degree: 0%
---

# Supporto LTI per NRPS

## Panoramica

Adobe Learning Manager supporta la specifica NRPS (Names and Role Provisioning Services) quando funge da strumento LTI (Learning Tools Interoperability) 1.3. Quando un Allievo avvia Learning Manager da un sistema di gestione dell’apprendimento esterno (la piattaforma), Learning Manager recupera il record di iscrizione dell’Allievo dalla piattaforma. Copia quindi gli attributi personalizzati del record, ad esempio l’ID reparto o dipendente, nel profilo dell’Allievo come campi attivi.

## Casi d’uso

* **Arricchisci automaticamente i profili degli Allievi.** Inserisci attributi quali reparto, ID dipendente o metadati personalizzati dalla tua piattaforma in Learning Manager senza immissione manuale dei dati o importazioni separate.
* **Analizza da dove provengono gli Allievi.** Acquisisci gli attributi della posizione, ad esempio paese e città, per creare un’immagine delle aree geografiche di origine degli Allievi. Utilizza i campi del profilo risultanti per l’analisi in Learning Manager.
* **Mantenere i dati del profilo allineati alla piattaforma di origine.** La piattaforma rimane la fonte della verità. Learning Manager aggiorna i valori ogni volta che un Allievo si avvia.
* **Supporto di più piattaforme in un unico account.** I prefissi dello spazio dei nomi mantengono gli attributi di piattaforme diverse separati, anche quando le piattaforme utilizzano lo stesso nome di attributo.

Con la sincronizzazione dei campi personalizzati NRPS, Learning Manager effettua le seguenti operazioni all’avvio:

1. Rileva che la piattaforma supporta NRPS.
2. Richiede alla piattaforma di avviare il record di iscrizione dell’Allievo.
3. Estrae gli attributi personalizzati da tale record.
4. Scrive gli attributi nel profilo dell’Allievo come campi attivi. Ogni nome di campo contiene un prefisso `<namespace>`, in modo che gli attributi delle diverse piattaforme non si scontrino.
5. Learning Manager riutilizza il token delle credenziali client OAuth 2.0 già utilizzato per i servizi di assegnazione e valutazione (AGS). Non è necessario configurare un nuovo endpoint del token.

>[!NOTE]
>
>NRPS è una specifica opzionale di LTI Advantage. Il supporto per Server dei criteri di rete e per gli attributi personalizzati varia in base alla piattaforma. Assicurati che la piattaforma esponga NRPS 2.0 prima di pianificare l’utilizzo di questa funzione.

## Funzioni principali

* **Supporto per attestazioni NRPS:** Learning Manager controlla ogni avvio di LTI 1.3 per l’attestazione NRPS. Se l’attestazione è assente, l’avvio prosegue normalmente senza errori e senza alcun impatto sull’Allievo.
  * Questa richiesta fornisce le seguenti informazioni:
    * **L&#39;endpoint di appartenenza:** `context_memberships_url `identifica l&#39;URL del servizio per il corso o il contesto di apprendimento da cui l&#39;Allievo ha avviato ALM.
    * **Versioni supportate:** `service_versions` elenca le versioni di Server dei criteri di rete disponibili in tale endpoint.
      Questa funzione supporta NRPS 2.0.
  * **Infrastruttura token condiviso:** Learning Manager aggiunge l’ambito NRPS alla richiesta di token AGS esistente e riutilizza la cache dei token per registrazione esistente.
* **Sincronizzazione dei parametri personalizzati con i profili degli Allievi**
  * **Campi attivi con prefisso spazio dei nomi:** Ogni attributo personalizzato viene mappato a un campo attivo denominato `<namespace>_<field_name>`.
  * **Creazione automatica dei campi:** Se non esiste alcun campo attivo corrispondente, Learning Manager ne crea uno con il tipo **Testo** e lo stato **Attivo**.
  * **Piattaforma come fonte di verità:** Learning Manager sovrascrive i valori di profilo esistenti con i valori più recenti della piattaforma. Gli Allievi e gli Amministratori non possono modificare questi campi.
  * **Comportamento non bloccante:** errori NRPS non impediscono agli Allievi di avviare contenuti di apprendimento.
  * **Più origini per gli attributi personalizzati:** Learning Manager può leggere gli attributi personalizzati dall’endpoint NRPS e dai parametri personalizzati nel token di avvio dell’LTI. Ulteriori informazioni sugli [attributi personalizzati nel token di avvio](#custom-attributes-in-the-launch-token).

## Configurazioni supportati

| Elemento | Supporto |
|----------------------------------------------------------------|--------------------------------------------------------------------------|
| Ruolo Learning Manager | Strumento LTI 1.3 |
| Versione LTI | LTI 1,3 |
| Versione servizio Server dei criteri di rete | 2.0 |
| Piattaforme (formato di campo personalizzato conforme alle specifiche) | Moodle, D2L Brightspace, Lavagna (Antologia), Sakai |
| Tipo di campo personalizzato | Testo |
| Attivazione | Ogni avvio LTI 1.3 |

Il supporto della piattaforma dipende dal modello di serializzazione dei campi personalizzati utilizzato nel record del membro Server dei criteri di rete. Possono coesistere più pattern, ma Learning Manager elabora solo i pattern supportati nella versione attiva.

## Come funziona

### Flusso di avvio

1. Un Allievo avvia Learning Manager dalla piattaforma.
2. Learning Manager legge l’attestazione NRPS nel token di avvio LTI 1.3. Se l’attestazione elenca il servizio Server dei criteri di rete versione 2.0, Learning Manager memorizza `context_memberships_url` per la sessione e per il contesto LTI (corso).
3. Learning Manager richiede un token di accesso che include l’ambito Server dei criteri di rete `https://purl.imsglobal.org/spec/lti-nrps/scope/contextmembership.readonly`.
4. Learning Manager chiama `context_memberships_url?rlid=<lti_user_id>` con il token al portatore per recuperare il record di avvio dell’Allievo. Se la piattaforma ignora il filtro `rlid` e restituisce l’elenco completo, Learning Manager trova l’Allievo entro `user_id`.
5. Learning Manager estrae i campi personalizzati dal record.
6. Learning Manager mappa ogni campo personalizzato su un campo attivo e scrive i valori nel profilo dell’Allievo.
7. In alternativa, ALM supporta anche l’estrazione di parametri personalizzati da sincronizzare con il profilo dell’Allievo durante l’avvio dello strumento, se i parametri personalizzati sono preimpostati con il campo identificabile ALM `ALMfield`.

### Formato campo personalizzato

La specifica NRPS 2.0 definisce i dati personalizzati come matrice `message` nel record membro. Learning Manager legge i dati personalizzati dall’attestazione personalizzata LTI all’interno dell’array. Per questa versione, Learning Manager supporta la rappresentazione conforme allo schema S.

```json
{
  "user_id": "abc123",
  "message": [
    {
      "https://purl.imsglobal.org/spec/lti/claim/custom": {
        "department": "Engineering",
        "employee_id": "E4567"
      }
    }
  ]
}
```

### Attributi personalizzati nel token di avvio

Le piattaforme possono anche inviare attributi personalizzati come parametri personalizzati nel token di avvio LTI. Learning Manager raccoglie gli attributi sia dal token di avvio che dall’endpoint NRPS e li memorizza nel profilo dell’Allievo.

Per gli attributi nel token di avvio, il nome del parametro deve iniziare con il prefisso `almfield-` richiesto da Learning Manager. Senza il prefisso, Learning Manager non è in grado di distinguere questi parametri dagli altri personalizzati e non li importa. Gli attributi recuperati dall&#39;endpoint Server dei criteri di rete non necessitano di questo prefisso. Questo prefisso è obbligatorio solo se nel token di avvio vengono importati parametri personalizzati per ALM per identificare il campo che deve sincronizzare con i campi attivi dell’Allievo.

>[!NOTE]
>
>Prima di configurare i parametri personalizzati sulla piattaforma, verifica l’esatto prefisso richiesto con il rappresentante Learning Manager.

### Denominazione e mappatura dei campi attive

Learning Manager crea il nome di campo attivo come `<namespace>_<field_name>`. Ad esempio, il campo `department` nello spazio dei nomi `https://purl.imsglobal.org/spec/lti/claim/custom` diventa `https://purl.imsglobal.org/spec/lti/claim/custom_department`.

Learning Manager applica le seguenti regole:

* **Lunghezza nome:** se il nome supera il limite di caratteri del nome campo attivo, Learning Manager riduce prima la porzione dello spazio dei nomi e mantiene il nome del campo.
* **Conflitti di nomi:** dopo la riduzione, Learning Manager verifica la presenza di conflitti con campi attivi esistenti da un’altra origine. In caso di conflitto, regola la lunghezza della riduzione fino a trovare un nome univoco. Se non riesce a trovare un nome univoco, ignora il campo e registra un errore.
* **Corrispondenza:** La corrispondenza dei nomi dei campi non fa distinzione tra maiuscole e minuscole.
* **Campo esistente e abilitato:** Learning Manager scrive il valore nel profilo dell’Allievo.
* **Campo esistente e disabilitato:** Learning Manager ignora il campo senza registrare un errore.
* **Nessun campo esistente:** Learning Manager crea un campo **Testo** con stato **Attivo**.

### Scrittura dei valori nel profilo

* A ogni avvio in cui Learning Manager recupera i dati NRPS, scrive tutti i valori dei campi personalizzati risolti nel profilo di avvio dell’Allievo. Nessun altro profilo Allievo viene modificato.
* Se un campo contiene già un valore, Learning Manager lo sovrascrive con il valore più recente della piattaforma.
* Se il valore della piattaforma è vuoto o nullo, Learning Manager mantiene il valore del profilo esistente.
* Un errore di scrittura in un campo non blocca l’avvio o la scrittura in altri campi.
* Learning Manager applica gli aggiornamenti dei campi nella stessa transazione di avvio, ove possibile.
* Gli Allievi non possono modificare i campi di origine NRPS nella pagina del profilo e gli Amministratori non possono modificare questi valori per conto di un Allievo.

## Configurare la sincronizzazione dei campi personalizzati di Server dei criteri di rete

### Prerequisiti

* La piattaforma è registrata con Learning Manager come strumento LTI 1.3. Questa funzione non supporta LTI 1.1 o LTI 1.2.
* La piattaforma supporta il servizio Server dei criteri di rete versione 2.0 ed espone attributi personalizzati nel formato `message` conforme alle specifiche.
* Il token di avvio LTI contiene l&#39;attestazione `namesroleservice`.
* L&#39;attestazione fornisce `context_memberships_url`, che identifica l&#39;endpoint NRPS specifico del corso.
* Il valore `service_versions` nell&#39;attestazione include `2.0`.
* Disponi dell’accesso come Amministratore alla registrazione degli strumenti della piattaforma.

### Concedere l’ambito NRPS a Learning Manager

Le nuove registrazioni che includono l’ambito NRPS non richiedono alcuna configurazione aggiuntiva in Learning Manager.

Le nuove registrazioni che includono l’ambito NRPS funzionano senza ulteriori modifiche in Learning Manager. Per una registrazione esistente, l&#39;amministratore della piattaforma deve aggiornare la registrazione dello strumento sul lato piattaforma.

>[!NOTE]
>
>Non è necessario modificare l’endpoint del token, l’ID client o la chiave privata in Learning Manager. Viene riutilizzata la configurazione AGS esistente. Se la piattaforma non concede l’ambito NRPS, Learning Manager ignora NRPS senza influire su AGS o sull’avvio.

### Esposizione degli attributi dell’Allievo sulla piattaforma

La piattaforma controlla quali attributi dell’Allievo condivide. I passaggi esatti dipendono dalla piattaforma. Ad esempio, in Moodle:

1. Aggiungi Learning Manager come strumento esterno utilizzando LTI 1.3.
2. Abilita le impostazioni sulla privacy che consentono alla piattaforma di condividere le informazioni dell’Allievo con lo strumento.
3. Definire gli attributi personalizzati da inviare. È possibile utilizzare variabili di piattaforma o valori predefiniti.
4. Se nel token di avvio invii anche attributi come parametri personalizzati, aggiungi il prefisso richiesto da Learning Manager a ciascun nome di parametro.

>[!NOTE]
>
>Esponi solo gli attributi necessari per il caso d’uso di apprendimento. Learning Manager tratta la piattaforma come la fonte del vero e in questa versione non offre controlli separati per il consenso o la privacy.

### Verificare la sincronizzazione

1. Avvia Learning Manager dalla piattaforma come Allievo di prova.
2. Conferma che l’avvio è stato completato normalmente.
3. Nell’app di amministrazione Learning Manager, apri la pagina dei campi attivi.
4. Confermare che i campi vengano visualizzati con il prefisso dello spazio dei nomi, con il tipo **Testo** e lo stato **Attivo**.
5. Apri il profilo dell’Allievo di prova e verifica che i valori corrispondano alla piattaforma.
6. Confermare che i campi di origine NRPS siano di sola lettura. Né l’Allievo né un Amministratore possono modificare manualmente i valori sincronizzati.
7. Riavvia dopo aver modificato un valore di origine non vuoto e verifica che Learning Manager sovrascriva il valore del profilo esistente con il valore NRPS più recente.

>[!TIP]
>
>Se un campo esiste ma è disabilitato, Learning Manager non vi scrive. Abilitare il campo se si desidera compilarlo.

## Gestione e registrazione degli errori

Learning Manager non blocca mai un Allievo a causa di un problema relativo a Server dei criteri di rete. Non riprova. Registra l&#39;errore e ignora la sincronizzazione di Server dei criteri di rete per l&#39;avvio. L&#39;avvio successivo riprova.

| Condizione | Risultato |
|------------------------------------------------------------------|-------------------------------------------------------|
| Attestazione NRPS assente dal token di avvio | Server dei criteri di rete ignorato. Il lancio continua. |
| È presente solo il servizio Server dei criteri di rete versione 1.0 | Server dei criteri di rete ignorato. Il lancio continua. |
| La richiesta di token non riesce o la piattaforma non concede l&#39;ambito NRPS | Server dei criteri di rete ignorato. AGS e il lancio non sono interessati. |
| Chiamata NRPS non riuscita (timeout, 4xx o 5xx) | L&#39;errore viene registrato. Il lancio continua. |
| L’Allievo non viene trovato nella risposta Server dei criteri di rete | Sincronizzazione dei campi ignorata. Il lancio continua. |
| Nessun campo personalizzato nella risposta NRPS | La sincronizzazione dei campi viene ignorata senza errori. |
| Impossibile risolvere un conflitto di nomi di campo | Il campo viene ignorato e viene registrato un errore. |
| Scrittura di un singolo campo non riuscita | Altri campi sono ancora scritti. Il lancio continua. |

Ogni voce di registro include la marca temporale, l’ID di registrazione della piattaforma, l’ID dell’Allievo e il motivo dell’errore. Gli amministratori di sistema di Learning Manager possono accedere ai registri.

## Note

* Viene sincronizzato solo il record dell’Allievo che si avvia. Learning Manager non sincronizza l’elenco completo dei corsi.
* È supportata solo la versione 2.0 del servizio Server dei criteri di rete.
* Tutti i campi sincronizzati sono di tipo **Testo**. Learning Manager non deduce i tipi dai valori. I tipi di campo Numerico, Data e Booleano non sono supportati.
* Learning Manager funge da strumento LTI. Non funge da piattaforma NRPS e non fornisce un endpoint di elenco ad altri strumenti.
* La sincronizzazione dei campi personalizzati viene eseguita durante l’avvio dell’LTI.
