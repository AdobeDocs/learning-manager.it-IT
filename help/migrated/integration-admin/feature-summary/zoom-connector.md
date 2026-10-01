---
description: Scopri come integrare il connettore Zoom con Adobe Learning Manager
jcr-language: en_us
title: Connettore zoom
contentowner: mmanuel
source-git-commit: 289bd299abdf6ff25d6bbb7bc4dbcaaf057e591e
workflow-type: tm+mt
source-wordcount: '412'
ht-degree: 2%
---

# Connettore zoom in Adobe Learning Manager

## Introduzione

Il connettore Zoom in Adobe Learning Manager consente l’integrazione diretta con Zoom per realizzare sessioni in aula virtuale. Grazie a questa integrazione, gli istruttori possono ospitare riunioni con Zoom direttamente da Learning Manager, iscrivere gli Allievi e tenere traccia dei dati di partecipazione e completamento. Gli Allievi ricevono inviti automatici e possono partecipare alle sessioni tramite i loro account Adobe Learning Manager. Al termine della sessione, i dati su presenze e prestazioni vengono sincronizzati in Adobe Learning Manager per la creazione di report e il tracciamento.

## Configurazione del connettore Zoom

Per configurare il connettore Zoom:

1. Accedi a Adobe Learning Manager come amministratore di integrazione.
2. Passa il mouse sul riquadro **Zoom**.

   ![](assets/zoom-connector1.png)
   _Configurazione del connettore Zoom in Adobe Learning Manager_

3. Seleziona **Connetti**. Viene visualizzata la pagina di impostazione del connettore Zoom.
4. Digita i seguenti dettagli dell&#39;account nei rispettivi campi. Puoi ottenere queste credenziali dall’amministratore del tuo account Zoom:

   * Nome connessione
   * Zoom ID account
   * ID client
   * Segreto del client
   * Indirizzo e-mail amministratore privilegiato

   ![](assets/zoom-connector2.png)
   _Digitare i dettagli di configurazione per configurare il connettore Zoom_

5. Seleziona **Connetti** per stabilire l&#39;integrazione.

>[!NOTE]
>
>Quando si abilita il connettore, **gli Allievi devono utilizzare lo stesso indirizzo e-mail** sia per gli account Zoom che per quelli Adobe Learning Manager, in modo da garantire la corretta sincronizzazione dei dati utente.

## Creazione di corsi Zoom

Una volta stabilita la connessione:

1. Accedi come **Autore** e crea un nuovo corso Classe virtuale.
2. Seleziona **Zoom** come sistema di conferenza durante la creazione del corso.
3. Assegnare gli Allievi al corso tramite amministratori, manager o iscrizione autonoma.
4. Al momento dell’iscrizione, gli allievi ricevono un’e-mail con i dettagli del corso.
5. Gli Allievi possono accedere al proprio account Adobe Learning Manager per accedere al corso e partecipare alla sessione Zoom.

## Monitoraggio di partecipazione e completamento

Al termine della sessione virtuale:

* Adobe Learning Manager riceve automaticamente lo stato di completamento da Zoom.
* Gli Amministratori possono visualizzare i report su partecipazione e punteggio in Adobe Learning Manager per tenere traccia della partecipazione e delle prestazioni degli Allievi.

## Creare un’app Zoom server-to-server OAuth

Per utilizzare il connettore Zoom con Adobe Learning Manager, è necessario creare un’app OAuth Zoom Server-to-Server e configurare gli ambiti richiesti.

### Ambiti OAuth richiesti

Quando crei l’applicazione in Zoom, assicurati che siano selezionati i seguenti ambiti:

| Quello che vuoi | Cerca questa parola chiave | Quindi scegli |
|---|---|---|
| Visualizza tutte le riunioni utenti | riunione | `meeting:read:meeting:admin, meeting:read:list_meetings:admin` |
| Visualizza/gestisci tutte le riunioni utente | riunione | `meeting:update:meeting:admin, meeting:delete:meeting:admin, meeting:write:meeting:admin` |
| Visualizza dati report | riepilogo | `report:read:meeting:admin, report:read:user:admin` (scegliere quello corrispondente all&#39;endpoint). |
| Visualizza tutte le informazioni utente | utente | `user:read:user:admin, user:read:list_users:admin` |
| Gestisci utenti | utente | `user:update:user:admin, user:write:user:admin` |
| Aggiungere un iscritto alla riunione | registrante | `meeting:write:registrant:admin` |
| Elenca tutti i partecipanti alla riunione | registrante | `meeting:read:list_registrants:admin` |
| Riunioni di sub-account | riunione + cerca :master | `meeting:write:meeting:master` |
| Report dei partecipanti alla riunione | partecipante | `report:read:list_meeting_participants:admin` |

