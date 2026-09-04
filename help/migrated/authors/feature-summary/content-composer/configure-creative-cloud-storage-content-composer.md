---
jcr-language: en_us
title: Configurazione dello spazio di archiviazione Creative Cloud per Adobe Learning Manager Content Composer
description: Scopri come configurare l’archiviazione Creative Cloud per Adobe Learning Manager Content Composer. Questa guida spiega perché è richiesto lo spazio di archiviazione di Creative Cloud, come gli amministratori possono assegnare l'offerta di iscrizione gratuita in Adobe Admin Console e come risolvere i problemi di accesso relativi allo spazio di archiviazione.
contentowner: saghosh
source-git-commit: 42512cc4cab0d0cdb1e9796610d6fc2f7b5c51d6
workflow-type: tm+mt
source-wordcount: '718'
ht-degree: 0%

---


>[!IMPORTANT]
>
>A chi serve questo documento: amministratori che devono abilitare l’archiviazione Creative Cloud per gli utenti Adobe Learning Manager, in modo da poter accedere e utilizzare Composizione contenuti. È particolarmente utile per gli amministratori che devono risolvere errori di accesso o relativi allo spazio di archiviazione e assegnare l’offerta di iscrizione gratuita tramite Adobe Admin Console.


Adobe Learning Manager (ALM) Content Composer richiede che gli utenti dispongano di spazio di archiviazione Creative Cloud associato al proprio account di Adobe. Gli utenti che non dispongono di spazio di archiviazione Creative Cloud potrebbero non essere in grado di accedere a Content Composer e potrebbero riscontrare errori di accesso o di accesso.

Per aiutare le organizzazioni a fornire spazio di archiviazione per gli utenti interessati, Adobe fornisce un&#39;offerta di iscrizione gratuita che gli amministratori possono assegnare tramite Adobe Admin Console. Questa offerta include lo spazio di archiviazione di Creative Cloud e può essere utilizzata quando un utente non dispone già di un piano che fornisce autorizzazioni di archiviazione.

## Prima di iniziare

Assicurati che:

* Disponi dell&#39;accesso come amministratore di Adobe Admin Console.
* Viene identificato l’utente che richiede l’accesso a Content Composer.
* Hai verificato se l&#39;utente dispone già di un piano che include lo spazio di archiviazione di Creative Cloud.

## Perché gli utenti hanno bisogno dello spazio di archiviazione Creative Cloud

Content Composer utilizza l’archiviazione Creative Cloud per archiviare i corsi. Gli utenti a cui non è stato assegnato spazio di archiviazione al profilo di Adobe possono ricevere un errore quando tentano di utilizzare Composizione contenuto.

![Errore di archiviazione di Content Composer](../assets/coco-storage1.png)

Molti clienti Adobe dispongono già di spazio di archiviazione Creative Cloud tramite i prodotti Adobe esistenti e non ne sono interessati. Tuttavia, alcuni clienti Adobe Learning Manager potrebbero non disporre di spazio di archiviazione fornito per impostazione predefinita e potrebbe essere necessario un amministratore per abilitarlo.

## Abilita archiviazione Creative Cloud gratuita per gli utenti

Se un utente non dispone di spazio di archiviazione Creative Cloud, assegna l&#39;offerta di iscrizione gratuita da Adobe Admin Console.

1. Accedi a [Adobe Admin Console](https://adminconsole.adobe.com/) utilizzando un account con privilegi di amministratore. Solo gli amministratori possono assegnare prodotti e offerte agli utenti.
2. Dall&#39;Admin Console, seleziona Prodotti > Versioni di prova e offerte speciali.

   ![Versioni di prova e offerte speciali nell&#39;Admin Console](../assets/coco-storage2.png)

3. Trova l&#39;offerta di iscrizione gratuita disponibile in Versioni di prova e Offerte speciali. Questa offerta viene discussa come metodo consigliato per abilitare lo spazio di archiviazione di Creative Cloud per gli utenti che non dispongono già di autorizzazioni di archiviazione.

   ![Offerta di iscrizione gratuita](../assets/coco-storage3.png)

4. Assegna l’offerta di iscrizione gratuita agli utenti richiesti. L’assegnazione può essere completata solo da un amministratore che dispone delle autorizzazioni di Admin Console appropriate.
5. Dopo l’assegnazione, verifica che l’utente disponga di spazio di archiviazione Creative Cloud e chiedi all’utente di accedere nuovamente a Composizione contenuti.

## Archiviazione fornita tramite iscrizione gratuita

Gli utenti con iscrizione gratuita ricevono circa 2 GB di spazio di archiviazione Creative Cloud, che consente di utilizzare Content Composer.

## Risoluzione dei problemi

**L&#39;utente riceve un errore durante l&#39;accesso a Composizione contenuto**

Verifica se l&#39;utente dispone di spazio di archiviazione Creative Cloud disponibile nel profilo di Adobe.

**L&#39;utente non può visualizzare l&#39;offerta di iscrizione gratuita**

Confermare che:

* Hai effettuato l’accesso come amministratore.
* Stai visualizzando l&#39;area Prodotti di Adobe Admin Console.
* L&#39;organizzazione è idonea ad accedere all&#39;offerta.

## Domande frequenti

**Tutti gli utenti di Adobe Learning Manager ricevono automaticamente lo spazio di archiviazione di Creative Cloud?**

N. Alcuni utenti ALM potrebbero non disporre di spazio di archiviazione fornito per impostazione predefinita e potrebbero richiedere autorizzazioni aggiuntive tramite l&#39;offerta di iscrizione gratuita.

**Gli utenti possono abilitare autonomamente lo spazio di archiviazione?**

N. L&#39;autorizzazione allo spazio di archiviazione deve essere assegnata da un amministratore di Adobe tramite l&#39;Admin Console.

**È richiesto spazio di archiviazione Creative Cloud per Composizione contenuto?**

Sì. Content Composer dipende dal fatto che gli utenti dispongano di spazio di archiviazione Creative Cloud associato al proprio account di Adobe.

**Cosa devono fare gli amministratori se un utente riscontra un errore relativo allo spazio di archiviazione?**

Verifica che l&#39;utente disponga dell&#39;autorizzazione all&#39;archiviazione di Creative Cloud. In caso contrario, assegna l’offerta di iscrizione gratuita tramite Adobe Admin Console e chiedi all’utente di riprovare.

**Cosa devono fare gli amministratori se hanno ancora problemi di accesso o di autorizzazione?**

Se l&#39;amministratore di Adobe Admin Console riscontra un problema durante l&#39;assegnazione dello spazio di archiviazione Creative Cloud o il debug di problemi relativi all&#39;accesso, il problema potrebbe richiedere il supporto a livello di account aziendale. In questi casi, contatta il supporto Adobe Enterprise tramite le opzioni di supporto disponibili in Admin Console.

Per ulteriori informazioni, consulta [Opzioni di supporto Enterprise](https://helpx.adobe.com/business/enterprise/get-help/support-options/support-for-enterprise.html)
