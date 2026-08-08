---
description: 'Scopri come Content Composer gestisce gli aggiornamenti dei corsi in Adobe Learning Manager: come la ripubblicazione crea una nuova versione del modulo e come gli autori di ALM aggiornano i corsi esistenti per utilizzare la versione più recente.'
jcr-language: en_us
title: Controllo delle versioni dei moduli in Adobe Learning Manager
source-git-commit: ea6d296fa99686136ab08d756a20570a4681d704
workflow-type: tm+mt
source-wordcount: '245'
ht-degree: 0%

---


# Controllo delle versioni dei moduli in Adobe Learning Manager

Il materiale sorgente cambia nel tempo: una policy viene rivista, un SOP ottiene una nuova versione, un pitch deck viene aggiornato. In Content Composer e ALM l’aggiornamento viene gestito come una modifica della versione, non come una modifica sul posto. Pertanto i corsi pubblicati in precedenza continuano a funzionare durante l’aggiornamento del modulo sottostante.

Quando ripubblichi, Adobe Learning Manager carica il modulo esistente come nuova versione nella Libreria dei contenuti, incrementando di una unità il numero di versione del modulo.

1. In Composizione contenuto, aggiorna i file di origine e rigenera le lezioni interessate (consulta Aggiornare un corso quando il materiale di origine cambia), quindi ripubblica.

2. La pubblicazione dell&#39;aggiornamento non sovrascrive il modulo esistente: aggiunge una nuova versione accanto all&#39;aggiornamento nella libreria dei contenuti ALM.

3. Un Autore ALM deve aggiornare esplicitamente ogni corso ALM che utilizza il modulo per puntare alla nuova versione; i corsi esistenti continuano a fare riferimento alla versione con cui sono stati creati fino a quando un Autore ALM non apporta quella modifica.

4. Gli Allievi che hanno già completato il corso nella versione precedente conservano il record di completamento esistente. La nuova versione si applica agli Allievi iscritti dopo l’aggiornamento del corso ALM.

Esaminate le lezioni rigenerate in Composizione contenuti prima di ripubblicarle. La rigenerazione può regolare testo, immagini o domande quiz precedentemente modificati nelle lezioni interessate.
