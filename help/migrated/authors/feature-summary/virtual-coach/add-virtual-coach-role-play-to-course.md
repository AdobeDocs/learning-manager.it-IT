---
description: Scopri come pubblicare un ruolo di istruttore virtuale come risorsa formativa, quindi aggiungerlo a un corso come parte di un percorso di apprendimento strutturato
jcr-language: en_us
title: Aggiunta di un ruolo di istruttore virtuale a un corso
exl-id: c33ec5e4-0e96-4452-ada7-d48f9c71a123
product_v2:
  - id: ed12e5b7-96e3-45e7-a17f-de222065ebcb
    internal-label: Learning Manager
source-git-commit: c061ccbefe8d40154220587796062d335e35de77
workflow-type: tm+mt
source-wordcount: '926'
ht-degree: 0%
---

# Aggiunta di un ruolo di istruttore virtuale a un corso

Publish è un ruolo di istruttore virtuale come risorsa formativa da aggiungere a un corso in modo che gli Allievi possano accedervi come parte di un percorso di apprendimento strutturato.

I ruoli di istruttore virtuali non vengono aggiunti direttamente ai corsi. In questo caso, devi prima pubblicare il ruolo svolto come risorsa formativa, quindi aggiungere tale risorsa formativa a un corso come modulo. Questo processo in due fasi consente di riutilizzare lo stesso ruolo in più corsi senza duplicarlo. Sotto il cofano, un ruolo pubblicato viene aggiunto alla Libreria dei contenuti come modulo LTI, ovvero come può essere distribuito come risorsa formativa autonoma o come modulo del corso. Prima di iniziare, [crea e pubblica un ruolo di istruttore virtuale](/help/migrated/authors/feature-summary/virtual-coach/create-publish-virtual-coach-role-play.md), se non l&#39;hai già fatto.

## Aggiungere il ruolo di risorsa formativa

1. Nel riquadro di navigazione a sinistra della home page dell’Autore, seleziona **Risorse formative**.
2. Seleziona **Crea** > **Allenatore virtuale** nell&#39;angolo in alto a destra.
3. Immettere un nome e una descrizione per la risorsa formativa.
4. Seleziona il ruolo **Allenatore virtuale** che desideri utilizzare dal campo **Cerca e seleziona istruttore virtuale**.

   ![](/help/migrated/authors/feature-summary/assets/virtual_coach8.png)
   *Cercare e selezionare il ruolo pubblicato che si desidera trasformare in una risorsa formativa.*

5. Imposta visibilità:
   - Lasciare l&#39;impostazione predefinita **Condiviso** per consentire ad altri autori di assegnare questa risorsa formativa ai propri corsi.
   - Seleziona **Privato** per limitare l’accesso ai tuoi corsi.
6. Facoltativamente, immetti il tempo di completamento previsto in minuti nel campo **Durata**.
7. Nel campo **Tag**, immettere le parole chiave per rendere la risorsa formativa rilevabile nella ricerca e nel catalogo.
8. Facoltativamente, puoi assegnare abilità e livelli di abilità. Puoi utilizzare solo le abilità già esistenti nel tuo account Adobe Learning Manager; le abilità non possono essere create da questa schermata e l&#39;assegnazione non è obbligatoria.
9. Seleziona **Salva**. La risorsa formativa viene pubblicata e può essere aggiunta a un corso.

## Aggiungere il ruolo a un corso

Una volta pubblicata la risorsa formativa, aggiungila a qualsiasi corso come modulo. Il ruolo viene visualizzato dagli allievi nella sequenza del corso insieme ad altri contenuti, come video, documenti o quiz.

1. Nel riquadro di navigazione a sinistra della home page dell’Autore, seleziona **Corsi**.
2. Apri il corso a cui vuoi aggiungere il ruolo o seleziona **Crea** per iniziare un nuovo corso. Se stai aprendo un corso esistente, seleziona **Modifica** dopo averlo aperto.
3. Aggiungi il nome e la descrizione del corso.
4. Passa alla sezione **Moduli** dell’editor del corso.
5. Sono disponibili tre sezioni in cui è possibile aggiungere moduli. Per selezionare un coach virtuale, passa alla prima sezione denominata **Contenuti**, seleziona **Aggiungi modulo**, quindi seleziona **Allenatore virtuale**.

   ![](/help/migrated/authors/feature-summary/assets/virtual-coach18.png)

   ![](/help/migrated/authors/feature-summary/assets/virtual_coach9.png)
   *Scegli Allenatore virtuale come tipo di modulo per aggiungere il tuo ruolo di ruolo pubblicato a un corso.*

6. Cerca il ruolo Allenatore virtuale che hai creato e selezionalo.

   ![](/help/migrated/authors/feature-summary/assets/virtual_coach10.png)
   *Cerca la risorsa formativa per nome o tag, quindi seleziona la relativa casella di controllo per aggiungerla al corso.*

7. Seleziona **Aggiungi**.
8. Configura i criteri di completamento e successo del modulo in base alla progettazione del corso.
9. Seleziona **Ripubblica** se hai aggiornato un corso esistente. Se hai aggiornato un corso esistente, verrà visualizzato solo il pulsante **Ripubblica**. Seleziona **Salva** se hai creato nuovamente il corso. Se hai creato nuovamente il corso, verrà visualizzato solo il pulsante **Salva**. Facendo clic sul pulsante **Salva**, il corso viene salvato nella scheda **Bozza** della pagina Catalogo corsi. Per pubblicare lo stesso corso, accedi allo stesso corso nella pagina **Catalogo corsi**, seleziona i puntini di sospensione e seleziona **Corso Publish**.

   ![](/help/migrated/authors/feature-summary/assets/virtual-coach19.png)

>[!NOTE]
>
>Tutti gli aggiornamenti apportati alla risorsa formativa, comprese le modifiche ai contenuti di ruolo, sono riportati automaticamente in tutti i corsi a cui è stata aggiunta. Se il ruolo svolto fa parte di una valutazione formale, ripubblica la risorsa formativa dopo aver apportato le modifiche in modo che gli Allievi possano visualizzare la versione più recente.

## Creazione di un pacchetto di Virtual Coach come parte di un percorso di apprendimento

Virtual Coach è progettato per funzionare al meglio come &quot;ultimo miglio&quot; di formazione — il punto in cui gli Allievi dimostrano di poter applicare ciò che hanno appena imparato, piuttosto che un&#39;attività autonoma. Raccogli il ruolo svolto all’interno di un corso o di un percorso di apprendimento insieme ai relativi contenuti e distribuisci il collegamento al corso tramite e-mail o altre comunicazioni sulla gestione del cambiamento, in modo che gli Allievi sappiano esattamente quando e perché completarlo.

Questo approccio all&#39;imballaggio si applica bene a diversi aggregati comuni:

- **Onboarding e ampliamento del personale**, in cui il gioco di ruolo segue i contenuti di onboarding e conferma che un nuovo dipendente è pronto per la prima conversazione dal vivo.
- **Certificazione e rafforzamento delle vendite**, in cui il ruolo è il punto di controllo della certificazione al termine di un corso di abilitazione alle vendite.
- **Preparazione al lancio del prodotto**, in cui il gioco di ruolo segue la formazione al lancio e conferma che i rappresentanti possono posizionare il nuovo prodotto prima che venga commercializzato, ad esempio lo scenario di preparazione al lancio del prodotto descritto in [cos&#39;è Virtual Coach](/help/migrated/authors/feature-summary/virtual-coach/what-virtual-coach-is.md), in cui un rappresentante deve adattare il proprio tono in un comitato di acquisto multi-persona.
- **Allenamento per dirigenti e manager**, in cui il gioco di ruolo segue un corso di abilità gestionali e precede una conversazione reale sulle prestazioni.
- **Programmi di preparazione per i partner**, in cui il gioco di ruolo conferma che un partner esterno può rappresentare correttamente il prodotto prima che venga certificato.
- **Corso di formazione sulla gestione delle modifiche e la comunicazione**, in cui il ruolo-play rafforza un nuovo processo o un messaggio di riorganizzazione dopo che i dipendenti hanno completato i contenuti correlati.

Una volta che gli Allievi potranno trovare e avviare il gioco di ruolo, consulta [Esercitarsi con l’Allenatore virtuale](/help/migrated/learners/feature-summary/virtual-coach/practice-role-play-with-virtual-coach.md) per sapere cosa sperimenteranno.
