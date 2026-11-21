---
description: Scopri come integrare il connettore Zoom con Adobe Learning Manager
jcr-language: en_us
title: Connettore zoom
contentowner: mmanuel
product_v2:
  - id: ed12e5b7-96e3-45e7-a17f-de222065ebcb
    internal-label: Learning Manager
source-git-commit: 3628dd3701949da127b138e0e1ffc2db8e84eab1
workflow-type: tm+mt
source-wordcount: '914'
ht-degree: 2%
---

# Connettore zoom in Adobe Learning Manager

## Introduzione

Il connettore Zoom in Adobe Learning Manager consente alle organizzazioni di offrire sessioni in aula virtuale in diretta, gestire l’iscrizione degli Allievi e tenere traccia della partecipazione e del completamento. Supporta anche più connessioni Zoom all’interno di un singolo account, consentendo agli Amministratori dell’integrazione di gestire l’accesso in base ai ruoli o ai gruppi di utenti e agli Autori di selezionare le connessioni disponibili per le sessioni del corso. Al termine della sessione, i dati su presenze e prestazioni vengono sincronizzati in Adobe Learning Manager per la creazione di report e il tracciamento.

## Configurazione del connettore Zoom

Per configurare il connettore Zoom:

1. Accedi a Adobe Learning Manager come Amministratore di integrazione.
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
   * Ruoli o gruppi che possono utilizzare questo connettore (facoltativo)

   ![](assets/zoom-connector2.png)
   _Digitare i dettagli di configurazione per configurare il connettore Zoom_

5. Seleziona **Connetti** per stabilire l&#39;integrazione.

>[!NOTE]
>
>Quando si abilita il connettore, **gli Allievi devono utilizzare lo stesso indirizzo e-mail** sia per gli account Zoom che per quelli Adobe Learning Manager, in modo da garantire la corretta sincronizzazione dei dati utente.

## Aggiungere più connessioni Zoom

Puoi aggiungere più connessioni Zoom a Adobe Learning Manager, con ogni connessione collegata a un account Zoom diverso. Ad esempio, è possibile creare connessioni separate per diversi partner o team e specificare quali ruoli o gruppi di utenti possono utilizzare ciascuna connessione.

Il numero di connessioni che è possibile aggiungere dipende dal livello dell&#39;account Adobe Learning Manager:

| **Account di livello** | **Numero massimo di connessioni Zoom** |
|---|---|
| l’applicazione Prime | 6 |
| Ultimate | 50 |

## Creazione di corsi Zoom

Una volta stabilita la connessione:

1. Accedi come **Autore** e crea un nuovo corso Classe virtuale.
2. Selezionare **Zoom** come sistema di conferenza, quindi selezionare la connessione Zoom che si desidera utilizzare dall&#39;elenco.
   >[!NOTE]
   >
   >Nell&#39;elenco vengono visualizzate solo le connessioni disponibili per il ruolo o il gruppo di utenti e una sessione utilizza una connessione alla volta.
3. Assegnare gli Allievi al corso tramite amministratori, manager o iscrizione autonoma.
4. Al momento dell’iscrizione, gli allievi ricevono un’e-mail con i dettagli del corso.
5. Gli Allievi possono accedere al proprio account Adobe Learning Manager per accedere al corso e partecipare alla sessione Zoom.

## Connessioni di zoom disponibili per gli Autori

Quando crei o modifichi una sessione del corso, puoi scegliere tra le connessioni Zoom disponibili per il tuo ruolo o gruppo di utenti. L’Amministratore dell’integrazione definisce i ruoli o i gruppi di utenti che possono accedere a ciascuna connessione Zoom.

Si supponga, ad esempio, che un Amministratore dell’integrazione configuri due connessioni Zoom, **Zoom partner A** e **Zoom partner B**, e assegni ciascuna connessione a un gruppo di utenti diverso:

* Se si appartiene a entrambi i gruppi Partner A e Partner B, è possibile selezionare una delle due connessioni.
* Se si appartiene solo al gruppo Partner A, è possibile selezionare **Partner A Zoom**.
* Se non appartieni a nessuno dei gruppi, queste connessioni non sono disponibili per la selezione.

>[!NOTE]
>
>È possibile utilizzare una sola connessione Zoom per una sessione. Se sono disponibili più connessioni, selezionare la connessione che si desidera utilizzare per la sessione.

## Gestire le connessioni Zoom

Nella pagina **Gestisci connessioni** sono visualizzate le connessioni Zoom configurate per l&#39;account. La colonna **Visibile a** indica i ruoli o i gruppi di utenti che possono utilizzare ogni connessione. Da questa pagina è possibile modificare, attivare o disattivare ed eliminare le connessioni Zoom esistenti.

![Connessione zoom Pagina Configura con Abilita impostazioni connessione, Credenziali e Ruoli o gruppi](assets/zoom-connection-configure-page.png "Connessione zoom Pagina Configura con Abilita impostazioni connessione, Credenziali e Ruoli o gruppi")

### Modificare una connessione Zoom

Per modificare una connessione Zoom esistente:

1. Nella pagina **Gestisci connessioni** selezionare la connessione che si desidera modificare.
1. Nella scheda Configura, aggiorna una delle seguenti opzioni:

   1. Per aggiornare le credenziali dell&#39;account Zoom, seleziona **Modifica** accanto a **Credenziali** e aggiorna i dettagli richiesti.
   1. Per modificare gli utenti autorizzati a utilizzare la connessione, aggiornare **Ruoli o gruppi** che possono utilizzare questo connettore.

1. Seleziona **Salva**.

### Attivare o disattivare una connessione Zoom

Le nuove connessioni Zoom sono attivate per impostazione predefinita. È possibile disattivare una connessione per impedire agli autori di utilizzarla senza eliminare la connessione.

Per disattivare una connessione:

1. Nella pagina **Gestisci connessioni**, selezionare la connessione che si desidera disabilitare.
1. Attiva **Abilita connessione**.
1. Seleziona **Salva**.

   La connessione disabilitata non è più disponibile per gli utenti nei ruoli o gruppi associati.

Per abilitare nuovamente la connessione, seleziona **Abilita connessione**, quindi seleziona **Salva**.

### Eliminare una connessione Zoom

Per eliminare una connessione Zoom:

1. Nella pagina **Gestisci connessioni**, seleziona la connessione che desideri eliminare.
1. Seleziona l&#39;icona **Elimina** accanto alla connessione.
1. Selezionare **Elimina**.

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

