---
jcr-language: en_us
title: Etichettatura bianca nell’app mobile Adobe Learning Manager
description: L'etichettatura bianca è una pratica per rinominare un'app o un servizio con il proprio marchio e personalizzarlo come se fossi il creatore originale. Nell’Adobe di Learning Manager, puoi applicare l’etichettatura bianca all’app per dispositivi mobili, in modo da rinominare l’app e renderla disponibile agli utenti con il tuo marchio.
contentowner: saghosh
exl-id: f37c86e6-d4e3-4095-9e9d-7a5cd0d45e43
source-git-commit: b649255ce7b3f3e0676f785003d3af60c50520a0
workflow-type: tm+mt
source-wordcount: '1177'
ht-degree: 0%

---

# Etichettatura bianca nell’app mobile Adobe Learning Manager

L’app mobile Learning Manager di Adobe ora supporta l’etichettatura bianca, il che significa che ora puoi rilasciare l’app con il tuo marchio.

## Come iniziare a preparare l’avvio dell’app con etichetta bianca

Per distribuire e gestire la tua app con etichetta bianca, segui i passaggi:

1. Prepara le risorse (come l&#39;immagine della schermata iniziale) e il testo in modo che entrambi possano essere utilizzati nell&#39;app e la descrizione nell&#39;app/play store.

1. Assegnare una risorsa tecnica in grado di:

* Generazione dei file del certificato di notifica push.
* Firma dei file binari dell&#39;app forniti dal team ALM.
* Caricamento e gestione del processo di pubblicazione. Il processo di pubblicazione richiede la comunicazione tra il gestore dell&#39;app e i team dell&#39;app/play store che l&#39;app è conforme a tutte le linee guida sulla pubblicazione. Da ALM, riceverai un file binario dell&#39;app completamente conforme.

## Panoramica

L&#39;etichettatura bianca è una pratica per rinominare un&#39;app o un servizio con il proprio marchio e personalizzarlo come se fossi il creatore originale. Nell’Adobe di Learning Manager, puoi applicare l’etichettatura bianca all’app per dispositivi mobili, in modo da rinominare l’app e renderla disponibile agli utenti con il tuo marchio.

## Cosa è possibile personalizzare

È possibile personalizzare quanto segue:

### Campi

<table>

    <tbody>

    <tr>

   <td>

    <p>ID account</p></td>

   <td>

    <p>ID del tuo account. Tieni presente che l’app con etichetta bianca non sarà accessibile agli Allievi che appartengono a nessun altro account.</p></td>

  </tr>

  <tr>

   <td>

    <p>ID account aggiuntivi</p></td>

   <td>

    <p>Se lo desideri, aggiungi più account (sottodomini). Aggiungi i sottodomini come separati da virgole senza spazi. Ad esempio, acc01,acc02,acc03 e così via.<br> <b>Nota:</b> È necessario aggiungere l’ID account quando si specificano i sottodomini.</br> </p></td>

  </tr>

  <tr>

  <td>

  <p>Nome app</p></td>

  <td>

  <p>Il nome che si desidera utilizzare per l'app.</p></td>

  </tr>

  <tr>

  <td>

  <p>Nome breve dell’app</p></td>

  <td>

  <p>Nei casi in cui il nome dell'app è lungo, assegna all'app un nome breve che appare sul dispositivo.</p></td>

  </tr>

   <tr>

  <td>

  <p>Nome app interna</p></td>

  <td>

  <p>Il nome con cui il sistema operativo identifica l'app. Il formato solitamente utilizzato è: com.company-name.product-name.</p></td>

  </tr>

  <tr>

  <td>

  <p>Nome app interna - iOS</p></td>

  <td>

  <p>Assegna un nome diverso all’app se gli utenti si trovano in iOS. Si consiglia di utilizzare lo stesso nome sia per iOS che per Android.</p></td>

  </tr>

  <tr>

  <td>

  <p>Icona app</p></td>

  <td>

  <p>L'icona dell'app come png. Questa icona viene visualizzata nell'app. Il formato da assegnare al nome è account-id_appIcon.png.</p></td>

  </tr>

  <tr>

  <td>

  <p>Schermata iniziale dell’app</p></td>

  <td>

  <p>Per la schermata iniziale dell'app, fornisci un'immagine (png) che viene visualizzata quando gli utenti avviano l'app. Il formato del nome è account-id_splashIcon.png.</p></td>

  </tr>

  <tr>

  <td>

  <p>ID client e segreto client</p></td>

  <td>

  <p>L’Amministratore dell’integrazione del tuo account fornisce i dettagli durante la registrazione dell’app. L’Amministratore dell’integrazione deve utilizzare quanto segue:<ul><li>Allievo:lettura,allievo:scrittura come ruolo</li><li>app interna name://redirect come URL di reindirizzamento</li></ul></p></td>

  </tr>

  <tr>

  <td>

  <p>Logo account</p></td>

  <td>

  <p>URL che ospita il logo dell'organizzazione. Fornisci un collegamento al contenuto come logo dell’account. L’URL deve essere codificato per il Web.</p></td>

  </tr>

  <tr>

  <td>

  <p>ID App Store per l’app (iOS)</p></td>

  <td>

  <p>ID richiesto per implementare l’aggiornamento forzato. L’app deve sapere che l’Allievo deve essere reindirizzato all’App Store per aggiornare l’app.</p></td>

  </tr>

   <tr>

  <td>

  <p>ID Play Store per Google per l’app (Android)</p></td>

  <td>

  <p>ID richiesto per implementare l’aggiornamento forzato.</p></td>

  </tr>

  <tr>

  <td>

  <p>Nome host per collegamento profondo</p></td>

  <td>

  <p>Per ospitare i collegamenti diretti, utilizza Learning Manager. Se si desidera utilizzare un altro URL nome host come collegamento profondo, fornire l'URL dell'host. Ad esempio, learningmanager.adobe.com.</p></td>

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

1. Generare o scaricare **Certificato di notifica push** e chiave privata (.p12). Per ulteriori informazioni, consultate [Documento per sviluppatori Apple](https://developer.apple.com/documentation/usernotifications/setting_up_a_remote_notification_server/establishing_a_certificate-based_connection_to_apns).

1. Installa il file p12 dopo averlo scaricato. Utilizza la password per eseguire l’installazione **Accesso Portachiavi**.

1. Passa a **Certificati personali** ed esportare il certificato. Assicurati di selezionare il tipo MIME .CER.

1. Una volta che hai il file p12 e il file cer sono disponibili, esegui i seguenti comandi:

```
- openssl pkcs12 -in privatekey.p12 -out myapnappkey.pem -nodes –clcerts

- openssl x509 -in privatekey.cer -inform DER -out myapnsappcert.pem 

- openssl s_client -connect gateway.sandbox.push.apple.com:2195 -cert myapnsappcert.pem -key myapnappkey.pem 
```

Se è possibile connettersi al server, il certificato creato è valido. Dal file myapnappkey.pem, copiare i valori del certificato e della chiave privata.

### Notifiche push su Android

Configurare un progetto in Firebase e condividere la chiave del server con il CSAM.

Contatta il team CSM e ottieni i file aggiunti ai servizi SNS in AWS. Gli utenti dovranno registrare la voce nel servizio SNS per la notifica push, che richiederà loro di condividere i certificati generati sopra per la convalida.

>[!NOTE]
>
>Per Android, l’utente deve fornire la chiave del server dal progetto Firebase che crea per Android per aggiungere la voce nel servizio SNS.


## Crea progetto in Firebase

### Android

Riutilizza lo stesso progetto creato nei passaggi precedenti per le notifiche push.

[Aggiungere il progetto](https://learn.microsoft.com/en-us/xamarin/android/data-cloud/google-messaging/firebase-cloud-messaging) in Firebase e recuperare ***google-services.json*** file.

### iOS

[Aggiungere il progetto](https://firebase.google.com/docs/ios/setup) in Firebase e recuperare ***GoogleService-Info.plist*** file.

>[!IMPORTANT]
>
>Invia i file all’Adobe del team CSAM di Learning Manager per includerli nella build del file binario dell’app.


## Genera i file binari firmati

### iOS

```
sh""" xcodebuild -exportArchive -archivePath Runner.xcarchive -exportPath "ipa_path/" -exportOptionsPlist {ExportFile} 

mv ipa_path/*.ipa "${env.AppName}_signed.ipa" """ 
```

>[!NOTE]
>
>Per creare i file binari firmati è necessario XCode 15.2 o versione successiva.


## Android

```
sh""" ~/Library/Android/sdk/build-tools/30.0.3/apksigner sign --ks $storeFile --ks-pass "pass:$store\_password" --ks-key-alias $key\_alias --key-pass "pass:$key\_password" --out app-release-signed.apk -v app-release.apk """
```

>[!NOTE]
>
>Per creare i file binari firmati, saranno necessari gli strumenti di compilazione SDK Android.

**Passaggi successivi**

Dopo aver generato i file binari, inviali a Play Store o App Store.

## Come si applicano le modifiche

Invia le risorse e i file necessari al team CSM. Il team CSM compila quindi il [form](https://forms.office.com/r/bJRRaRBvSh) con le modifiche necessarie e allega le risorse richieste. Il team rivedrà e informerà i team tecnici delle modifiche. Il team tecnico genererà quindi una build e la condividerà con il team CSM.

Il team CSM condividerà la build con il cliente.

## Cosa non può essere personalizzato

* Schermata Aggiorna password
* Creazione di una schermata dell&#39;account
