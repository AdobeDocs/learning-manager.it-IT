---
description: Scopri come integrare il connettore Workday con Adobe Learning Manager
jcr-language: en_us
title: Connettore Workday
contentowner: mmanuel
source-git-commit: 8a5212062c6b172b0e9d4f3faa2e66d26c5c2b56
workflow-type: tm+mt
source-wordcount: '812'
ht-degree: 1%

---


# Connettore Workday in Adobe Learning Manager

## Introduzione

**Workday** è un sistema basato su cloud che aiuta le organizzazioni a gestire i dipendenti e i dati finanziari. Viene utilizzato principalmente per attività HR come l&#39;assunzione, il ciclo paghe e il monitoraggio delle prestazioni. Quando è collegato a Adobe Learning Manager, consente la sincronizzazione automatica dei dati degli utenti e delle abilità tra le due piattaforme.

Il connettore Workday consente di integrare perfettamente Adobe Learning Manager con il tenant Workday dell’organizzazione. Questa integrazione consente la sincronizzazione automatica dei dati utente e delle competenze tra i due sistemi, migliorando la precisione dei dati e riducendo le operazioni manuali.

## Vantaggi principali

- Importa gli utenti da Workday a Adobe Learning Manager.
- Mappatura degli attributi tra Workday e Adobe Learning Manager.
- Esporta le abilità utente da Adobe Learning Manager a Workday.
- Pianifica l&#39;esecuzione automatica delle attività di sincronizzazione dei dati.

## Prerequisiti

Prima di configurare il connettore Workday, richiedi i seguenti dettagli all’amministratore di Workday:

- URL host
- ID tenant
- Nome utente
- Password

## Configurazione del connettore Workday

Puoi configurare il connettore Workday in Adobe Learning Manager per importare i dati degli utenti da Workday, esportare le abilità degli utenti in Workday e pianificare sincronizzazioni automatizzate per mantenere entrambi i sistemi aggiornati.

Per configurare il connettore Workday:

1. Accedi a Adobe Learning Manager come amministratore di integrazione.
2. Passa il mouse sul riquadro **Workday** e seleziona **Connetti**.

   ![](assets/workday-connector1.png)
   _Configurare il connettore Workday per l&#39;importazione e l&#39;esportazione dei dati_

3. Digitare i seguenti dettagli di connessione:
   - **Nome connessione**: un nome a tua scelta per la connessione.
   - **URL host**: fornito dall&#39;amministratore di Workday.
   - **Tenant**: identificatore interno dell’amministratore di Workday.
   - **Nome utente e password**: l&#39;amministratore di Workday crea un utente di sistema integrato (ISU) con i privilegi di sicurezza richiesti e lo condivide con l&#39;amministratore di integrazione.

   ![](assets/workday-connector2.png)
   _Aggiungere i dettagli necessari per configurare il connettore Workday_

4. Seleziona **Connetti** per completare l&#39;installazione.

>[!NOTE]
>
>Puoi configurare più connessioni Workday nel tuo account.

## Importazione di utenti da Workday

### Mapping attributi

Puoi utilizzare il connettore Workday per importare gli utenti attivi dal tenant Workday in Adobe Learning Manager. Questa integrazione semplifica la gestione degli utenti mantenendo sincronizzati i record dei dipendenti. Oltre a Workday, Adobe Learning Manager supporta anche le importazioni degli utenti da altre fonti di dati come FTP e Salesforce.

Prima di importare gli utenti, è necessario mappare gli attributi utente tra Workday e Learning Manager.

1. Passa alla pagina **Panoramica** nel connettore Workday.
2. Seleziona **Utenti interni** nella sezione **Importa**.

   ![](assets/workday-connector3.png)
   _Selezionare gli utenti interni a cui mappare gli attributi utente_

3. Utilizza l&#39;opzione **Mapping attributi** per collegare i campi tra i due sistemi:
   - Nella colonna **Adobe Learning Manager**, selezionate l&#39;attributo Adobe Learning Manager corrispondente.
   - Nella colonna **Workday**, utilizza il menu a discesa per selezionare l&#39;attributo Workday corrispondente.

   ![](assets/workday-connector4.png)
   _Mappatura degli attributi di Workday con i campi di Adobe Learning Manager_

   >[!NOTE]
   >
   >Adobe Learning Manager supporta attualmente l&#39;importazione di un massimo di **69 attributi utente** da Workday. Puoi abilitare campi aggiuntivi utilizzando la funzione **Campi attivi** in Adobe Learning Manager. Per aggiungere attributi Workday personalizzati, contatta il tuo Customer Success Account Manager (CSAM).

4. Selezionare la casella di controllo **Escludi lavoratori temporanei** per evitare di importare lavoratori temporanei.
5. Se necessario, applica i filtri, ad esempio per importare gli utenti in manager specifici.

>[!IMPORTANT]
>
>Assicurati che UUID, indirizzo e-mail e nome del dipendente siano univoci. Valori errati o duplicati possono causare errori di integrazione.

## Attributi Workday supportati

Elenco degli attributi Workday supportati:

```
wd:User_ID wd:Worker_ID manager wd:Personal_Data.wd:Name_Data.wd:Preferred_Name_Data.wd:Name_Detail_Data.@wd:Formatted_Name wd:Personal_Data.wd:Name_Data.wd:Legal_Name_Data.wd:Name_Detail_Data.@wd:Formatted_Name wd:Personal_Data.wd:Name_Data.wd:Legal_Name_Data.wd:Name_Detail_Data.wd:Prefix_Data.wd:Title_Descriptor wd:Personal_Data.wd:Name_Data.wd:Preferred_Name_Data.wd:Name_Detail_Data.wd:Prefix_Data.wd:Title_Descriptor wd:Personal_Data.wd:Name_Data.wd:Preferred_Name_Data.wd:Name_Detail_Data.wd:First_Name wd:Personal_Data.wd:Name_Data.wd:Preferred_Name_Data.wd:Name_Detail_Data.wd:Last_Name wd:Personal_Data.wd:Name_Data.wd:Legal_Name_Data.wd:Name_Detail_Data.wd:First_Name wd:Personal_Data.wd:Name_Data.wd:Legal_Name_Data.wd:Name_Detail_Data.wd:Last_Name wd:Personal_Data.wd:Contact_Data.wd:Address_Data.0.@wd:Formatted_Address wd:Personal_Data.wd:Contact_Data.wd:Address_Data.0.wd:Postal_Code wd:Personal_Data.wd:Contact_Data.wd:Email_Address_Data.0.wd:Email_Address wd:Personal_Data.wd:Contact_Data.wd:Address_Data.0.wd:Country_Region_Descriptor wd:Personal_Data.wd:Contact_Data.wd:Phone_Data.0.@wd:Formatted_Phone wd:Personal_Data.wd:Contact_Data.wd:Phone_Data.0.wd:Country_ISO_Code wd:Personal_Data.wd:Contact_Data.wd:Phone_Data.0.wd:International_Phone_Code wd:Personal_Data.wd:Contact_Data.wd:Phone_Data.0.wd:Phone_Number wd:Personal_Data.wd:Primary_Nationality_Reference.wd:ID.1.$ wd:Personal_Data.wd:Gender_Reference.wd:ID.1.$ wd:Personal_Data.wd:Identification_Data.wd:National_ID.0.wd:National_ID_Data.wd:ID wd:Personal_Data.wd:Identification_Data.wd:Custom_ID.0.wd:Custom_ID_Data.wd:ID wd:User_Account_Data.wd:Default_Display_Language_Reference.wd:ID.1.$ wd:Role_Data.wd:Organization_Role_Data.wd:Organization_Role.0.wd:Organization_Role_Reference.wd:ID.1.$ wd:Employment_Data.wd:Worker_Job_Data.0.wd:Position_Data.wd:Position_Title wd:Employment_Data.wd:Worker_Job_Data.0.wd:Position_Data.wd:Business_Title wd:Employment_Data.wd:Worker_Job_Data.0.wd:Position_Data.wd:Business_Site_Summary_Data.wd:Name wd:Employment_Data.wd:Worker_Job_Data.0.wd:Position_Data.wd:Business_Site_Summary_Data.wd:Address_Data.@wd:Formatted_Address
wd:Employment_Data.wd:Worker_Job_Data.0.wd:Position_Data.wd:Job_Classification_Summary_Data.0.wd:Job_Classification_Reference.wd:ID.1.$ wd:Employment_Data.wd:Worker_Job_Data.0.wd:Position_Data.wd:Job_Classification_Summary_Data.0.wd:Job_Group_Reference.wd:ID.1.$ wd:Employment_Data.wd:Worker_Job_Data.0.wd:Position_Data.wd:Work_Space__Reference.wd:ID.1.$ wd:Employment_Data.wd:Worker_Job_Data.0.wd:Position_Data.wd:Job_Profile_Summary_Data.wd:Job_Family_Reference.0.wd:ID.1.$ wd:Employment_Data.wd:Worker_Job_Data.0.wd:Position_Data.wd:Job_Profile_Summary_Data.wd:Job_Profile_Name wd:Employment_Data.wd:Worker_Job_Data.0.wd:Position_Data.wd:Job_Profile_Summary_Data.wd:Job_Profile_Reference.wd:ID.1.$ wd:Employment_Data.wd:Worker_Job_Data.0.wd:Position_Data.wd:Business_Site_Summary_Data.wd:Address_Data.0.wd:Country_Reference.wd:ID.2.$ wd:Employment_Data.wd:Worker_Job_Data.0.wd:Position_Data.wd:Worker_Type_Reference.wd:ID.1.$ wd:Employment_Data.wd:Worker_Job_Data.0.wd:Position_Data.wd:Business_Site_Summary_Data.wd:Address_Data.0.@wd:Formatted_Address wd:Employment_Data.wd:Worker_Job_Data.0.wd:Position_Data.wd:Job_Profile_Summary_Data.wd:Management_Level_Reference.wd:ID.1.$ wd:Employment_Data.wd:Worker_Status_Data.wd:Active wd:Employment_Data.wd:Worker_Status_Data.wd:Active_Status_Date wd:Employment_Data.wd:Worker_Status_Data.wd:Hire_Date wd:Employment_Data.wd:Worker_Status_Data.wd:Original_Hire_Date wd:Employment_Data.wd:Worker_Status_Data.wd:Retired wd:Employment_Data.wd:Worker_Status_Data.wd:Retirement_Date wd:Employment_Data.wd:Worker_Status_Data.wd:Terminated wd:Employment_Data.wd:Worker_Status_Data.wd:Termination_Date wd:Employment_Data.wd:Worker_Status_Data.wd:Termination_Last_Day_of_Work wd:Organization_Data.wd:Worker_Organization_Data.0.wd:Organization_Data.wd:Organization_Code wd:Organization_Data.wd:Worker_Organization_Data.0.wd:Organization_Data.wd:Organization_Name wd:Organization_Data.wd:Worker_Organization_Data.0.wd:Organization_Data.wd:Organization_Type_Reference.wd:ID.1.$ wd:Organization_Data.wd:Worker_Organization_Data.0.wd:Organization_Data.wd:Organization_Subtype_Reference.wd:ID.1.$ wd:Qualification_Data.wd:Education.0.wd:School_Name wd:Qualification_Data.wd:External_Job_History.0.wd:Job_History_Data.wd:Job_Title wd:Qualification_Data.wd:External_Job_History.0.wd:Job_History_Data.wd:Company wd:Management_Chain_Data.wd:Worker_Supervisory_Management_Chain_Data.wd:Management_Chain_Data.0.wd:Manager.Employee_ID Primary Work Email wd:Organization_Type_Reference_Cost_Center_ID wd:Organization_Type_Reference_Cost_Center_Name wd:Organization_Type_Reference_Company wd:Organization_Subtype_Reference_Department
wd:Organization_Subtype_Reference_Division wd:Universal_ID wd:Employment_Data.wd:Worker_Job_Data.0.wd:Position_Data.wd:Business_Site_Summary_Data.wd:Address_Data.0.wd:Country_Region_Descriptor wd:Employment_Data.wd:Worker_Job_Data.0.wd:Position_Data.wd:Business_Site_Summary_Data.wd:Address_Data.0.wd:Country_Region_Reference.wd:ID.2.$ wd:Personal_Data.wd:Contact_Data.wd:Address_Data.0.wd:Municipality
```

## Esportare le abilità utente in Workday

Puoi esportare tutte le abilità utente attive da Adobe Learning Manager a Workday. Le abilità ritirate non vengono esportate.

>[!IMPORTANT]
>
>- Non cercare di esportare contemporaneamente abilità da più account Adobe Learning Manager allo stesso account Workday.
>- Se più account Adobe Learning Manager utilizzano lo stesso account Workday, assicurati che i nomi delle abilità siano coerenti tra gli account per evitare conflitti.

### Configurare un’esportazione pianificata

Per configurare le esportazioni pianificate:

1. Seleziona **Abilità utente**, quindi seleziona **Configura pianificazione** nella pagina **Panoramica di Workday**.

   ![](assets/workday-connector5.png)
   _Selezionare le abilità utente per pianificare l&#39;esportazione_

2. Seleziona la casella di controllo **Abilita esportazione abilità utente utilizzando questa connessione**.
3. Seleziona **Abilita pianificazione**.
4. Impostare la data di inizio, l&#39;ora e l&#39;intervallo di ricorrenza.

   ![](assets/workday-connector6.png)
   _Configurare l&#39;esportazione della pianificazione nel connettore Workday_

5. Seleziona **Salva** per applicare la pianificazione.

### Esportazione su richiesta

Per creare esportazioni su richiesta:

1. Seleziona **Su richiesta** nella pagina **Panoramica di Workday**.
2. Digitare la data di inizio del report.
3. Selezionare **Esegui** per eseguire il report.

### Visualizza stato esecuzione

1. Vai a **Stato esecuzione**.
2. Visualizza lo stato di tutte le attività e scarica i report degli errori in base alle esigenze.

## Pianificazione delle attività di sincronizzazione

È possibile configurare il connettore per eseguire automaticamente le attività di sincronizzazione dei dati:

- Pianifica le importazioni giornaliere degli utenti da Workday a Learning Manager.
- Pianifica esportazioni periodiche di abilità utente in Workday.

>[!NOTE]
>
>La pianificazione garantisce che i record utente e i dati sulle abilità siano sempre aggiornati in entrambi i sistemi.

## Punti da ricordare

- Il campo UUID compilato da Workday non può essere eliminato dagli amministratori LMS rivolti al client.
- La funzione **Rimozione utente** supporta solo un massimo di 50 utenti per esecuzione. Presta attenzione quando importi gli utenti con UUID.
- Le abilità vengono mappate a livello di elemento di abilità in Workday, utilizzando il nome e il livello di abilità di Adobe Learning Manager.
