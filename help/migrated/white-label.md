---
jcr-language: en_us
title: Etichettatura bianca nell’app mobile Adobe Learning Manager
description: L'etichettatura bianca è una pratica per rinominare un'app o un servizio con il proprio marchio e personalizzarlo come se fossi il creatore originale. In Adobe Learning Manager, puoi applicare l'etichettatura bianca all'app per dispositivi mobili, in modo da rinominare l'app e renderla disponibile agli utenti con il tuo marchio.
contentowner: saghosh
exl-id: f37c86e6-d4e3-4095-9e9d-7a5cd0d45e43
source-git-commit: b9809314014fcd8c80f337983c0b0367c060e348
workflow-type: tm+mt
source-wordcount: '0'
ht-degree: 0%

---

# Etichettatura bianca nell’app mobile Adobe Learning Manager

L’app per dispositivi mobili Adobe Learning Manager ora supporta l’etichettatura bianca, il che significa che ora puoi rilasciare l’app con il tuo marchio.

## Come iniziare a preparare l’avvio dell’app con etichetta bianca

Per distribuire e gestire la tua app con etichetta bianca, segui i passaggi:

1. Prepara le risorse (come l&#39;immagine della schermata iniziale) e il testo in modo che entrambi possano essere utilizzati nell&#39;app e la descrizione nell&#39;app/play store.

1. Assegnare una risorsa tecnica in grado di:

   * Generazione dei file del certificato di notifica push.
   * Firma dei file binari dell&#39;app forniti dal team ALM.
   * Caricamento e gestione del processo di pubblicazione. Il processo di pubblicazione richiede la comunicazione tra il gestore dell&#39;app e i team dell&#39;app/play store che l&#39;app è conforme a tutte le linee guida sulla pubblicazione. Da ALM, riceverai un file binario dell&#39;app completamente conforme.

## Panoramica

L&#39;etichettatura bianca è una pratica per rinominare un&#39;app o un servizio con il proprio marchio e personalizzarlo come se fossi il creatore originale. In Adobe Learning Manager, puoi applicare l&#39;etichettatura bianca all&#39;app per dispositivi mobili, in modo da rinominare l&#39;app e renderla disponibile agli utenti con il tuo marchio.

## Cosa è possibile personalizzare

È possibile personalizzare quanto segue:

### Campi

<table>

 <tbody>

  <tr>

   <td>

    <p>ID account</p>

   </td>

   <td>

    <p>ID del tuo account. Tieni presente che l’app con etichetta bianca non sarà accessibile agli Allievi che appartengono a nessun altro account.</p>

   </td>

  </tr>

  <tr>

   <td>

    <p>ID account aggiuntivi</p>

   </td>

   <td>

    <p>Se lo desideri, aggiungi più account (sottodomini). Aggiungi i sottodomini come separati da virgole senza spazi. Ad esempio, acc01,acc02,acc03 e così via.<br> <b>Nota:</b> è necessario aggiungere l'ID account quando si specificano i sottodomini.</br> </p>

   </td>

  </tr>

  <tr>

   <td>

    <p>Nome app</p></td>

   <td>

    <p>Il nome che si desidera utilizzare per l'app.</p>

   </td>

  </tr>

  <tr>

   <td>

    <p>Nome breve dell’app</p>

   </td>

   <td>

    <p>Nei casi in cui il nome dell'app è lungo, assegna all'app un nome breve che appare sul dispositivo.</p>

   </td>

  </tr>

  <tr>

   <td>

    <p>Nome app interna</p></td>

   <td>

    <p>Il nome con cui il sistema operativo identifica l'app. Il formato solitamente utilizzato è: com.company-name.product-name.</p>

   </td>

  </tr>

  <tr>

   <td>

    <p>Nome app interna - iOS</p>

   </td>

   <td>

    <p>Assegna un nome diverso all’app se gli utenti si trovano in iOS. Si consiglia di utilizzare lo stesso nome sia per iOS che per Android.</p>

   </td>

  </tr>

  <tr>

   <td>

    <p>Icona app</p>

   </td>

   <td>

    <p>L'icona dell'app come png. Questa icona viene visualizzata nell'app. Il formato da assegnare al nome è account-id_appIcon.png. Le dimensioni dell'icona dell'app sono di 512 × 512 pixel.<div>Tieni presente che Apple non consente il canale di Alpha nelle icone delle app. Assicurati quindi di rimuovere il canale di Alpha dalla risorsa prima di inviarla.</div></p>

   </td>

  </tr>

  <tr>

   <td>

    <p>Schermata iniziale dell’app</p></td>

   <td>

    <p>Per la schermata iniziale dell'app, fornisci un'immagine (png) che viene visualizzata quando gli utenti avviano l'app. Il formato del nome è account-id_splashIcon.png. Le dimensioni delle schermate iniziali basate su quadrati sono di 1052 × 1052 pixel, quelle basate su cerchi di 768 x 768 pixel.</p>

   </td>

  </tr>

  <tr>

   <td>

    <p>ID client e segreto client</p>

   </td>

   <td>

    <p>L’Amministratore dell’integrazione del tuo account fornisce i dettagli durante la registrazione dell’app. L’Amministratore dell’integrazione deve utilizzare quanto segue:<ul><li>Allievo:lettura,allievo:scrittura come ruolo</li><li>app interna name://redirect come URL di reindirizzamento</li></ul></p>

   </td>

  </tr>

  <tr>

   <td>

    <p>Logo account</p>

   </td>

   <td>

    <p>URL che ospita il logo dell'organizzazione. Fornisci un collegamento al contenuto come logo dell’account. L’URL deve essere codificato per il Web.</p>

   </td>

  </tr>

  <tr>

   <td>

    <p>ID App Store per l’app (iOS)</p>

   </td>

   <td>

    <p>ID richiesto per implementare l’aggiornamento forzato. L’app deve sapere che l’Allievo deve essere reindirizzato all’App Store per aggiornare l’app.</p>

   </td>

  </tr>

  <tr>

   <td>

    <p>ID Play Store per Google per l’app (Android)</p>

   </td>

   <td>

    <p>ID richiesto per implementare l’aggiornamento forzato.</p>

   </td>

  </tr>

  <tr>

   <td>

    <p>Nome host per collegamento profondo</p>

   </td>

   <td>

    <p>Per ospitare i collegamenti diretti, utilizza Learning Manager. Se si desidera utilizzare un altro URL nome host come collegamento profondo, fornire l'URL dell'host. Ad esempio, learningmanager.adobe.com.</p>

   </td>

  </tr>

 </tbody>

</table>

>[!NOTE]
>
>Fornisci i dati ai tuoi CSAM in modo che possano aggiungerli nel tuo file binario personalizzato dell&#39;app.


#### Aggiornare l&#39;associazione del sito per gestire i collegamenti personalizzati

Se utilizzi un dominio personalizzato o learningmanager\*.adobe.com come host, non è necessario intraprendere alcuna azione. Tuttavia, se utilizzate una soluzione personalizzata o un nome host specifico per gli URL, aggiungete i file di associazione del sito.

>[!CAUTION]
>
>Se i file non sono presenti, i collegamenti non funzioneranno. Assicurati che i file siano presenti.


Per ulteriori informazioni, fai riferimento ai seguenti collegamenti:

* [Android](https://learningmanager.adobe.com/.well-known/assetlinks.json)
* [iOS](https://learningmanager.adobe.com/.well-known/apple-app-site-association)

## Genera notifiche push

L’invio di notifiche push alle app Android e iOS richiede due meccanismi diversi.

* Per iOS, genera i certificati di notifica push.
* Per Android, fornisci una chiave server generata dal progetto Firebase.

Segui le istruzioni riportate di seguito per configurare i progetti in Firebase:

### Notifiche push su iOS

Nello sviluppo di app iOS, un certificato di notifica push è una credenziale crittografica rilasciata da Apple che consente a un server di inviare notifiche push in modo sicuro a un dispositivo iOS tramite il servizio di notifica push (APN) di Apple.

Il certificato garantisce una comunicazione sicura tra il server (o il provider) e i numeri API di Apple quando si inviano notifiche push ai dispositivi iOS.

Sia Android che iOS utilizzano Firebase Cloud Messaging (FCM) come servizio per l’invio di notifiche push ai dispositivi.

### Come generare il certificato su iOS

Seguire la procedura descritta di seguito.

1. Genera o scarica il **certificato di notifica push** e la chiave privata (.p12). Per ulteriori informazioni, consulta il [documento per sviluppatori Apple](https://developer.apple.com/documentation/usernotifications/setting_up_a_remote_notification_server/establishing_a_certificate-based_connection_to_apns).

1. Installa il file p12 dopo averlo scaricato. Utilizza la password per eseguire l’installazione in **Accesso Portachiavi**.

1. Passa a **Certificati personali** ed esporta il certificato. Assicurati di selezionare il tipo MIME .CER.

1. Una volta che hai il file p12 e il file cer sono disponibili, esegui i seguenti comandi:

```
- openssl pkcs12 -in privatekey.p12 -out myapnappkey.pem -nodes –clcerts

- openssl x509 -in privatekey.cer -inform DER -out myapnsappcert.pem 

- openssl s_client -connect gateway.sandbox.push.apple.com:2195 -cert myapnsappcert.pem -key myapnappkey.pem 
```

Se è possibile connettersi al server, il certificato creato è valido. Dal file myapnappkey.pem, copiare i valori del certificato e della chiave privata.

### Notifiche push su Android

Per Android, l’utente deve fornire il file services.json dal progetto Firebase per aggiungere la voce nel servizio SNS.

Crea un progetto in Firebase e condividi il file services.json con il team CSM. Questo file è necessario per la voce basata su token nell&#39;SNS. Si noti che la chiave del server non è più utilizzata. Vedere [Creare un progetto in Firebase](#create-project-in-firebase).

Per scaricare il file services.json, effettua le seguenti operazioni:

1. Accedi alla console **Firebase**.
1. Passa a **Impostazioni progetto** e seleziona **Messaggistica cloud**.
1. Trova **l&#39;API di messaggistica cloud di Firebase** e seleziona **Gestisci account servizio**.
1. Nella pagina **Account del servizio**, seleziona **Account del servizio** nel pannello a sinistra.
1. Trova la voce del progetto e seleziona **Gestisci dettagli** in azioni.

   >[!NOTE]
   >
   >   Il formato di immissione del progetto sarà &lt;-accountname->@appspot.gserviceaccount.com.

1. Passa alla scheda **Tasti** e seleziona **Aggiungi chiave**.
1. Se non è presente alcuna chiave, selezionare **Crea nuova chiave** e selezionare **JSON** come tipo di chiave. Questo genererà e scaricherà il file JSON.
1. Se è già presente una chiave, seleziona **Carica chiave esistente**, incolla la chiave e caricala. Questo genererà e scaricherà il file JSON.

<!-- Set up a project in Firebase and share the server key with the CSAM.-->

Contatta il team CSM e condividi il file JSON per aggiungere la voce ai servizi SNS in AWS. Gli utenti dovranno registrare la voce nel servizio SNS per la notifica push, che richiederà loro di condividere i certificati generati sopra per la convalida.

## Crea progetto in Firebase {#create-project-in-firebase}

### Android

Riutilizza lo stesso progetto creato nei passaggi precedenti per le notifiche push.

[Aggiungi il progetto](https://learn.microsoft.com/en-us/xamarin/android/data-cloud/google-messaging/firebase-cloud-messaging) in Firebase e recupera il file ***google-services.json***.

### iOS

[Aggiungere il progetto](https://firebase.google.com/docs/ios/setup) a Firebase e recuperare il file ***GoogleService-Info.plist***.

>[!IMPORTANT]
>
>Invia i file al team CSAM di Adobe Learning Manager per includerli nella build del file binario dell’app.


## Genera i file binari firmati

### iOS

<!--```
sh""" xcodebuild -exportArchive -archivePath Runner.xcarchive -exportPath "ipa_path/" -exportOptionsPlist {ExportFile} 

mv ipa_path/*.ipa "${env.AppName}_signed.ipa" """ 
```-->

La cartella `<root>` contiene il file **Runner.xcarchive.zip**. Esegui i comandi seguenti per generare il file binario firmato:

1. Esegui il comando seguente per decomprimere l&#39;archivio:

   ```
   unzip Runner.xcarchive.zip
   ```

2. Accedi alla directory dell&#39;app:

   ```
   cd Runner.xcarchive/Products/Applications/Runner.app
   ```

3. Copia il file di provisioning per dispositivi mobili:

   ```
   cp <path>/<mobile-provisioningfile>.mobileprovision embedded.mobileprovision
   ```

4. Torna alla cartella `<root>` (in cui si trova Runner.xcarchive.zip):

   ```
   cd <root>
   ```

5. Esportare l&#39;archivio utilizzando xcodebuild:

   ```
   xcodebuild -exportArchive -archivePath Runner.xcarchive -exportPath ipa_path/ -exportOptionsPlist <path>/<ExportOptions-file>.plist
   ```

6. Individuate il file .ipa nella cartella ipa_path.
7. Carica il file .ipa nel sito Web `Diawi`.
8. Una volta completato il caricamento, seleziona il pulsante **[!UICONTROL Invia]**.
9. Al termine, riceverai un codice QR e un collegamento.
10. Apri il codice QR o il collegamento direttamente in Safari.

Se il dispositivo è incluso nel profilo di provisioning, l&#39;installazione deve procedere sul dispositivo.

>[!NOTE]
>
>Per creare i file binari firmati è necessario XCode 15.2 o versione successiva.


### Android

**Per il file apk**

```
sh""" <path>/apksigner sign --ks $storeFile --ks-pass "pass:$store_password" --ks-key-alias $key_alias --key-pass "pass:$key_password" --out app-release-signed.apk -v app-release.apk """
```

**Per il file aab**

>[!NOTE]
>
>Per creare i file binari firmati, saranno necessari gli strumenti di compilazione SDK Android.

Play Store richiede file binari Android in formato aab per la pubblicazione. Pertanto, forniremo il file .aab non firmato.

>[!NOTE]
>
>Quando crei un file keystore, devi generare una password keystore, un alias chiave di firma e una password alias chiave di firma.

Segui i passaggi riportati di seguito per firmare il file .aab:

Esegui il comando seguente:

```
<path>/jarsigner -verbose -sigalg SHA256withRSA -digestalg SHA-256 -keystore <keystore-file> app-release.aab <signingKeyAlias>
```

>[!NOTE]
>
>**[!UICONTROL jarsigner]** è incluso in Java. Assicurati di utilizzare Java 21.

Quando richiesto, immetti le seguenti password:

* Password Keystore
* password per l’alias della chiave di firma

È possibile utilizzare l&#39;apk fornito. Tuttavia, se devi generare un&#39;app da un file aab, segui questi passaggi:

>[!NOTE]
>
>Sarà necessario installare **[!UICONTROL bundletool]** per generare APK.


Esegui il comando seguente per creare il file apk:

```
java -jar <path>/bundletool-all.jar  build-apks --bundle=app-release.aab --output=my_app.apks --mode=universal
```

Per decomprimere il file, esegui il comando seguente:

```
unzip my_app.apks -d output_dir
```

Riceverai il file apk dalla cartella **[!UICONTROL output_dir]**.

**Novità**

Dopo aver generato i file binari, inviali a Play Store o App Store.

## Come si applicano le modifiche

Invia le risorse e i file necessari al team CSM. Il team CSM quindi compila il [modulo](https://forms.office.com/r/bJRRaRBvSh) con le modifiche richieste e allega le risorse richieste. Il team rivedrà e informerà i team tecnici delle modifiche. Il team tecnico genererà quindi una build e la condividerà con il team CSM.

Il team CSM condividerà la build con il cliente.

## Cosa non può essere personalizzato

* Schermata Aggiorna password
* Creazione di una schermata dell&#39;account
