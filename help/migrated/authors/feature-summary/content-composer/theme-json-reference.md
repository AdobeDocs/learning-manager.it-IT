---
description: Riferimento completo per ogni proprietà nello schema JSON del tema di Content Composer, tra cui token di tavolozza, pile di font, token di raggio e spaziatura, valori del ruolo del testo, proprietà dei componenti e stile di valutazione.
jcr-language: en_us
title: Riferimento della proprietà JSON del tema di Adobe Learning Manager Content Composer
source-git-commit: ea6d296fa99686136ab08d756a20570a4681d704
workflow-type: tm+mt
source-wordcount: '1899'
ht-degree: 5%

---


# Riferimento della proprietà JSON del tema di Adobe Learning Manager Content Composer

Riferimento completo per ogni proprietà in un file JSON tema di Content Composer, con descrizioni e valori di esempio.

Campi di livello superiore che identificano e descrivono il tema.

## **Metadati**

| **Proprietà** | **Tipo** | **Descrizione** | **Valore ardesia** |
|--------------|----------|----------------------------------------------------------------------------------------------------------------------------|------------------------------------------------------------------------------------------------------------------|
| id | stringa | Identificatore univoco del tema. Solo caratteri minuscoli e trattini, senza spazi o caratteri speciali. Utilizzato internamente per fare riferimento al tema. | &quot;ardesia&quot; |
| nome | stringa | Nome visualizzato nel pannello Temi del corso. | &quot;Ardesia&quot; |
| versione | stringa | Numero di versione semantica. Utilizzare &quot;1.0.0&quot; per i nuovi temi. | &quot;1.0.0&quot; |
| descrizione | stringa | Breve descrizione del carattere visivo del tema. | &quot;Un tema caldo e autorevole con sfondo crema, accenti Adobe e il sistema di tipo Roboto Slab + Roboto&quot; |
| autore | stringa | Nome del creatore o del team del tema. | &quot;Composizione contenuti&quot; |
| sorgente | stringa | Origine tema. &quot;spedito&quot; per i temi incorporati. &quot;personalizzato&quot; per i temi creati dall&#39;utente. | &quot;personalizzato&quot; |
| isDefault | booleano | Se questo tema viene applicato automaticamente ai nuovi corsi. Nella maggior parte dei casi, imposta su false. | falso |

## **foundation.palette**

I sette token di colore principali che formano la base del colore del tema. Tutti i valori degli elementi fanno riferimento a questi token utilizzando var(—tokenName) anziché valori esadecimali hardcoded.

| **Proprietà** | **Tipo** | **Descrizione** | **Valore ardesia** |
|------------------|------------|---------------------------------------------------------------------------------------------------------------------------|-----------------|
| primo piano | colore esadecimale | Colore di primo piano principale per testo, icone ed elementi dell’interfaccia utente posizionati sullo sfondo. | #1A1A1A |
| sfondo | colore esadecimale | Colore di sfondo dell&#39;area di lavoro del corso principale e delle diapositive. | #FAF7F2 |
| accento | colore esadecimale | Colore dell&#39;accento del marchio applicato ai pulsanti, agli stati selezionati, agli indicatori di avanzamento, alle intestazioni delle lezioni e alle evidenziazioni interattive. | #E8001C |
| backgroundLieve | colore esadecimale | Colore di sfondo secondario per schede, pannelli, navigazione e riempimenti dei componenti. | #F0EBE1 |
| secondario | colore esadecimale | Colore elemento interfaccia utente inattivo, bordo, divisore e bordo. | #D9D3C9 |
| textPrimary | colore esadecimale | Colore del testo principale per tutti i contenuti del titolo e del corpo. | #1A1A1A |
| textInverse | colore esadecimale | Colore del testo per i contenuti inseriti su sfondi scuri o colorati, come le etichette dei pulsanti sul colore principale. | #FFFFFF |

## **foundation.fonts**

Due pile di font applicate a tutti i ruoli di testo nel tema. Riferimento nei valori degli elementi utilizzando var(—font-heading) o var(—font-body).

| **Proprietà** | **Tipo** | **Descrizione** | **Valore ardesia** |
|--------------|-------------------|------------------------------------------------------------------------------------------------------|---------------------------------------------------------------------|
| intestazione | stringa stack di font | Famiglia di font per titoli di lezioni, argomenti e intestazioni di visualizzazione. Includere i fallback sicuri per il Web. | &quot;Roboto Slab, Georgia, &#39;Times New Roman&#39;, serif&quot; |
| corpo | stringa stack di font | Famiglia di font per testo paragrafo, sottotitoli, domande sui quiz ed etichette per l’interfaccia utente. Includere i fallback sicuri per il Web. | &quot;Roboto, -apple-system, BlinkMacSystemFont, &#39;Segoe UI&#39;, sans-serif&quot; |

## **foundation.spacing**

I token di spaziatura orizzontale e verticale utilizzati come linea di base. I componenti vengono ridimensionati a partire da questi utilizzando i moltiplicatori horizontalSpacingScale e verticalSpacingScale.

| **Percorso** | **Tipo** | **Descrizione** | **Valore ardesia** |
|---------------|----------|-------------------------------------|-----------------|
| horizontal.xs | valore px | Unità di spaziatura orizzontale minima | 4px |
| orizzontale.s | valore px | Unità di spaziatura orizzontale piccola | 8px |
| orizzontale.m | valore px | Unità di spaziatura orizzontale media | 12px |
| orizzontale.l | valore px | Unità di spaziatura orizzontale grande | 16px |
| orizzontale.xl | valore px | Unità di spaziatura orizzontale molto grande | 24px |
| verticale.xs | valore px | Unità di spaziatura verticale minima | 4px |
| verticale.s | valore px | Piccola unità di spaziatura verticale | 8px |
| verticale.m | valore px | Unità di spaziatura verticale media | 16px |
| verticale.l | valore px | Unità di spaziatura verticale grande | 24px |
| verticale.xl | valore px | Unità di spaziatura verticale molto grande | 32px |

## **fondazione.raggio**

Token del raggio del bordo che controllano l’arrotondamento degli angoli per componenti e schede.

| **Proprietà** | **Tipo** | **Descrizione** | **Valore ardesia** |
|--------------|----------|---------------------------------------------------------|-----------------|
| nessuno | valore px | Nessun arrotondamento: angoli acuti. Sempre &quot;0px&quot;. | 0px |
| s | valore px | Raggio ridotto per arrotondare gli angoli in modo discreto. | 4px |
| m | valore px | Raggio medio per l&#39;arrotondamento della scheda standard e dei componenti. | 8px |
| l | valore px | Raggio grande per arrotondamenti prominenti. | 16px |
| completo | valore px | Forma a riempimento o a cerchio. Sempre &quot;9999px&quot;. | 9999px |

## **foundation.logo**

| **Proprietà** | **Tipo** | **Descrizione** | **Valore ardesia** |
|--------------|----------------|----------------------------------------------------------------------------------------------|-----------------|
| logo | stringa o null | URL o percorso di file dell’immagine del logo visualizzata nell’intestazione del corso. Imposta su null per nessun logo. | null |

## **elements.text**

Proprietà di composizione tipografica per ogni ruolo di testo con nome nel corso. Tutti i ruoli condividono lo stesso insieme di proprietà.

### **Ruoli di testo**

| **Ruolo** | **Applicato a** |
|--------------|------------------------------------------------------------------------------|
| lessonTitle | Titolo principale di una diapositiva di apertura della lezione |
| topicTitle | Intestazione nella parte superiore di ogni diapositiva di argomento |
| blockHeading | Intestazioni all&#39;interno di componenti di contenuto come intestazioni a fisarmonica e titoli di schede |
| sottotitolo | Intestazioni secondarie all&#39;interno di una diapositiva argomento |
| domanda | Testo della domanda per quiz e verifica della conoscenza |
| didascalia | Sottotitoli sotto immagini e blocchi multimediali |
| paragrafo | Corpo del testo nelle diapositive del contenuto |
| buttonLabel | Testo su pulsanti ed elementi di invito all&#39;azione |

### **Proprietà testo condiviso**

Le seguenti proprietà si applicano a ogni ruolo di testo sopra elencato.

| **Proprietà** | **Tipo** | **Valori accettati** | **Descrizione** |
|--------------------|-----------------------|--------------------------------------------------------------------|---------------------------------------------------------|
| fontFamily | CSS var o stack di font | var(—font-heading), var(—font-body) o una stringa di stack di font completa | Famiglia di font per questo ruolo di testo. |
| fontSize | valore px | Qualsiasi valore in pixel | Dimensione font. |
| fontWeight | stringa | Solo &quot;bold&quot; o &quot;normal&quot;: i valori numerici non sono supportati | Spessore font. |
| fontStyle | stringa | &quot;normale&quot; o &quot;corsivo&quot; | Stile font. |
| colore | CSS var o hex | Qualsiasi token palette tramite var(—tokenName) o un valore esadecimale diretto | Colore testo. |
| textAlign | stringa | &quot;left&quot;, &quot;center&quot; o &quot;right&quot; | Allineamento orizzontale del testo. |
| letterSpacing | stringa | &quot;normal&quot;, un valore px o un valore em | Spazio tra i caratteri. |
| lineHeight | stringa | Un valore percentuale o senza unità | Height linea. |
| textDecoration | stringa | &quot;none&quot;, &quot;underline&quot; o &quot;line-through&quot; | Decorazione testo. |
| textTransform | stringa | &quot;none&quot;, &quot;uppercase&quot;, &quot;lowercase&quot; o &quot;capitalize&quot; | Trasformazione di maiuscole e minuscole. |
| paddingInlineStart | valore px | Qualsiasi valore in pixel | Spaziatura sinistra applicata al blocco di testo. |
| paragraphSpacing | valore px | Qualsiasi valore in pixel | Spazio aggiunto sotto ciascun paragrafo all’interno del blocco di testo. |

### **Valori ruolo testo - Tema Slate**

| **Ruolo** | **fontFamily** | **fontSize** | **fontWeight** | **fontStyle** | **colore** | **textAlign** | **letterSpacing** | **lineHeight** | **textTransform** |
|--------------|---------------------|--------------|----------------|---------------|--------------------|---------------|-------------------|----------------|-------------------|
| lessonTitle | var(—font-heading) | 48px | grassetto | normale | var(—textPrimary) | centro | -0,01em | 130% | nessuno |
| topicTitle | var(—font-heading) | 40px | normale | normale | var(—textPrimary) | lato | 0 | 135% | nessuno |
| blockHeading | var(—font-heading) | 24px | grassetto | normale | var(—textPrimary) | lato | 0 | 140% | nessuno |
| sottotitolo | var(—font-body) | 20px | grassetto | normale | var(—textPrimary) | lato | 0,01em | 150% | nessuno |
| domanda | var(—font-heading) | 24px | normale | normale | var(—textPrimary) | lato | 0 | 150% | nessuno |
| didascalia | var(—font-body) | 13px | normale | normale | var(—textPrimary) | lato | 0,02 em | 170% | nessuno |
| paragrafo | var(—font-body) | 16px | normale | normale | var(—textPrimary) | lato | 0,01em | 190% | nessuno |
| buttonLabel | var(—font-body) | 14px | grassetto | normale | var(—textInverse) | centro | 0,06 em | 125% | maiuscolo |

## **elementi - superfici strutturali**

Proprietà che controllano lo sfondo e il bordo delle superfici con layout fisso del corso.

| **Elemento** | **Proprietà** | **Tipo** | **Descrizione** | **Valore ardesia** |
|--------------|--------------|-------------------|---------------------------------------------------|----------------------------|
| area di lavoro | sfondo | CSS var | Colore di sfondo area di lavoro corso principale | var(—background) |
| intestazione | sfondo | CSS var | Colore di sfondo della barra dell’intestazione del corso | var(—background) |
| intestazione | bordo | Stringa bordo CSS | Bordo inferiore della barra dell’intestazione del corso | 1px solid var(—secondary) |
| piè di pagina | sfondo | CSS var | Colore di sfondo barra piè di pagina del corso | var(—background) |
| piè di pagina | bordo | Stringa bordo CSS | Bordo superiore della barra del piè di pagina del corso | 1px solid var(—secondary) |
| lessonHeader | sfondo | CSS var | Colore di sfondo dell&#39;area dell&#39;intestazione del titolo della lezione | var(—accent) |
| argomento | sfondo | CSS var | Colore di sfondo di ogni diapositiva di argomento | var(—background) |
| argomento | bordo | Stringa bordo CSS | Bordo attorno al contenitore di diapositive degli argomenti | 1px solid var(—secondary) |
| navigazione | sfondo | CSS var | Colore di sfondo del pannello di navigazione della lezione | var(—backgroundLieve) |
| navigazione | bordo | Stringa bordo CSS | Bordo nel pannello di navigazione della lezione | 1px solid var(—secondary) |
| pulsante | sfondo | CSS var | Colore di sfondo dei pulsanti di azione principale | var(—accent) |
| impaginazione | sfondo | CSS var | Colore di sfondo del controllo di impaginazione | var(—backgroundLieve) |

## **elementi - proprietà del componente condiviso**

Queste proprietà vengono visualizzate in tutti i componenti del blocco di contenuto: paragraphBlock, videoBlock, imageGrid, accordion, carosello, flipCard e timeline.

| **Proprietà** | **Tipo** | **Descrizione** |
|------------------------|-------------------|---------------------------------------------------------------------------------------------------|
| sfondo | CSS var o color | Sfondo esterno del blocco componente. In genere è &quot;trasparente&quot;. |
| cardBackgroundColor | CSS var o color | Riempimento dello sfondo di singole schede all’interno del componente. |
| cardBorder | Stringa bordo CSS | Bordo applicato a ogni carta. Stenografia CSS completa, ad esempio &quot;1px solid var(—secondary)&quot;. |
| cardShadowOffset | stringa | Offset X e Y dell&#39;ombra esterna della scheda, ad esempio &quot;0px 2px 6px&quot;. |
| cardShadowColor | CSS var o color | Colore dell&#39;ombra esterna della scheda. |
| cardShadowOpacity | stringa percentuale | Opacità dell’ombra esterna della scheda. Impostare su &quot;0%&quot; per rimuovere l&#39;ombra. |
| horizontalSpacingScale | stringa numerica | Moltiplicatore applicato ai token di spaziatura orizzontale per questo componente. &quot;1&quot; usa la spaziatura predefinita. |
| verticalSpacingScale | stringa numerica | Moltiplicatore applicato ai token di spaziatura verticale per questo componente. &quot;1&quot; usa la spaziatura predefinita. |
| radiusScale | stringa numerica | Moltiplicatore applicato ai token di raggio per questo componente. &quot;1&quot; usa il raggio di default. |
| nestedAccentColor | CSS var o color | Colore dei dettagli per gli elementi nidificati all&#39;interno del componente. Si applica solo a paragraphBlock. |

### **Valori dei componenti condivisi - Tema dello slate**

| **Componente** | **cardBackgroundColor** | **cardBorder** | **cardShadowOpacity** |
|----------------|-----------------------------|----------------------------|---------------------------|
| paragraphBlock | var(—backgroundLieve) | 1px solid var(—secondary) | 8% |
| videoBlock | var(—backgroundLieve) | 1px solid var(—secondary) | 8% |
| imageGrid | var(—backgroundLieve) | 1 px solid var(—accent) | 8% |
| fisarmonica | var(—backgroundLieve) | 1px solid var(—secondary) | 8% |
| carosello | var(—backgroundLieve) | 1px solid var(—secondary) | 8% |
| flipCard | var(—backgroundLieve) | 1px solid var(—secondary) | 8% |
| timeline | var(—backgroundLieve) | 1px solid var(—secondary) | 8% |

## **elementi - proprietà specifiche dei componenti**

Proprietà univoche per i singoli tipi di componenti.

| **Componente** | **Proprietà** | **Tipo** | **Descrizione** | **Valore ardesia** |
|----------------|--------------------------|----------|------------------------------------------------------------------|-------------------------|
| paragraphBlock | nestedAccentColor | CSS var | Colore dei dettagli per gli elementi nidificati all&#39;interno del blocco di paragrafo | var(—accent) |
| flipCard | cardFrontBackgroundColor | CSS var | Colore di sfondo del lato anteriore della flip card | var(—backgroundLieve) |
| flipCard | cardBackBackgroundColor | CSS var | Colore di sfondo del lato posteriore della flip card: il colore di visualizzazione | var(—accent) |
| flipCard | arrowColor | CSS var | Colore dell&#39;icona della freccia dell&#39;indicatore di capovolgimento | var(—textInverse) |
| schede | activeBg | CSS var | Colore di sfondo della scheda selezionata | var(—accent) |
| schede | inactiveBg | CSS var | Colore di sfondo delle schede non selezionate | var(—backgroundLieve) |
| schede | containerBg | CSS var | Colore di sfondo del contenitore della barra delle schede | var(—backgroundLieve) |
| timeline | trackColor | CSS var | Colore della linea di connessione tra i nodi della linea temporale | var(—secondario) |
| timeline | progressCompletedBg | CSS var | Colore di riempimento degli indicatori di avanzamento della timeline completati | var(—accent) |
| timeline | progressCurrentBorder | CSS var | Colore del bordo dell’indicatore di avanzamento della timeline corrente | var(—accent) |
| timeline | progressUnreachBg | CSS var | Colore di riempimento dei marcatori della timeline non ancora raggiunto | var(—secondario) |
| timeline | progressUnreachBorder | CSS var | Il colore del bordo dei marcatori della timeline non è ancora stato raggiunto | var(—backgroundLieve) |

## **elementi.valutazione**

Proprietà dei componenti quiz e verifica conoscenza.

| **Proprietà** | **Tipo** | **Descrizione** | **Valore ardesia** |
|----------------------------|----------------|------------------------------------------------------------------------------|-------------------------|
| sfondo | CSS var | Contesto esterno del blocco di valutazione | trasparente |
| optionTextColor | CSS var | Colore del testo delle etichette delle opzioni di risposta | var(—textPrimary) |
| optionIndicatorColor | CSS var | Colore del pulsante di scelta o dell&#39;indicatore della casella di controllo | var(—accent) |
| optionSelectedColor | CSS var | Colore applicato all’indicatore di opzioni selezionato | var(—accent) |
| optionCheckmarkColor | CSS var | Colore dell&#39;icona del segno di spunta visualizzato su un&#39;opzione selezionata | var(—textInverse) |
| optionBackgroundColor | CSS var | Colore di sfondo di ogni opzione di risposta | var(—background) |
| optionHoverBackgroundColor | CSS var | Colore di sfondo di un&#39;opzione di risposta al passaggio del mouse | var(—backgroundLieve) |
| buttonBackgroundColor | CSS var | Colore di sfondo del pulsante Invia o Controlla risposta | var(—accent) |
| buttonTextColor | CSS var | Colore del testo dell&#39;etichetta del pulsante Invia o Controlla risposta | var(—textInverse) |
| buttonHoverBackgroundColor | CSS var | Colore di sfondo del pulsante al passaggio del mouse | var(—accent) |
| feedbackCorrectColor | colore esadecimale | Colore di sfondo del pannello di feedback risposte corretto | #D7F7E1 |
| feedbackIncorrectColor | colore esadecimale | Colore di sfondo del pannello feedback risposte errato | #FFEBE8 |
| feedbackTextColor | colore esadecimale | Colore del testo nel pannello feedback | #111111 |
| optionBorderCorrectColor | colore esadecimale | Colore del bordo nell&#39;opzione di risposta corretta dopo la visualizzazione della risposta | #079355 |
| optionBorderIncorrectColor | colore esadecimale | Colore del bordo su un’opzione selezionata in modo errato dopo la visualizzazione della risposta | #D73220 |
| horizontalSpacingScale | stringa numerica | Moltiplicatore per la spaziatura orizzontale all&#39;interno della componente di valutazione | &quot;1&quot; |
| verticalSpacingScale | stringa numerica | Moltiplicatore per la spaziatura verticale all&#39;interno della componente di valutazione | &quot;1&quot; |
| radiusScale | stringa numerica | Moltiplicatore per il raggio del bordo all&#39;interno della componente di valutazione | &quot;1&quot; |

## **Riferimento var() token tavolozza**

Utilizza queste espressioni var() nei valori degli elementi per fare riferimento ai token della tavolozza. Quando si aggiorna un token di tavolozza, vengono aggiornati automaticamente tutti gli elementi che lo utilizzano.

| **Espressione** | **Riferimenti** |
|-------------------------|-------------------------------------|
| var(—primo piano) | foundation.palette.foreground |
| var(—background) | foundation.palette.background |
| var(—accent) | foundation.palette.accent |
| var(—backgroundLieve) | foundation.palette.backgroundSubtle |
| var(—secondario) | foundation.palette.secondary |
| var(—textPrimary) | foundation.palette.textPrimary |
| var(—textInverse) | foundation.palette.textInverse |
| var(—font-heading) | foundation.fonts.heading |
| var(—font-body) | foundation.fonts.body |

## Esempio di json tema

```
{
  "id": "slate",
  "name": "Slate",
  "version": "1.0.0",
  "description": "A warm, authoritative theme with cream background, Adobe red accents, and the Roboto Slab + Roboto type system",
  "author": "Content Composer",
  "source": "custom",
  "isDefault": false,
  "foundation": {
    "palette": {
      "foreground": "#1A1A1A",
      "background": "#FAF7F2",
      "accent": "#E8001C",
      "backgroundSubtle": "#F0EBE1",
      "secondary": "#D9D3C9",
      "textPrimary": "#1A1A1A",
      "textInverse": "#FFFFFF"
    },
    "fonts": {
      "heading": "Roboto Slab, Georgia, 'Times New Roman', serif",
      "body": "Roboto, -apple-system, BlinkMacSystemFont, 'Segoe UI', sans-serif"
    },
    "spacing": {
      "horizontal": {
        "xs": "4px",
        "s": "8px",
        "m": "12px",
        "l": "16px",
        "xl": "24px"
      },
      "vertical": {
        "xs": "4px",
        "s": "8px",
        "m": "16px",
        "l": "24px",
        "xl": "32px"
      }
    },
    "radius": {
      "none": "0px",
      "s": "4px",
      "m": "8px",
      "l": "16px",
      "full": "9999px"
    },
    "logo": null
  },
  "elements": {
    "text": {
      "lessonTitle": {
        "fontFamily": "var(--font-heading)",
        "fontSize": "48px",
        "fontWeight": "bold",
        "fontStyle": "normal",
        "color": "var(--textPrimary)",
        "textAlign": "center",
        "letterSpacing": "-0.01em",
        "lineHeight": "130%",
        "textDecoration": "none",
        "textTransform": "none",
        "paddingInlineStart": "0px",
        "paragraphSpacing": "0px"
      },
      "topicTitle": {
        "fontFamily": "var(--font-heading)",
        "fontSize": "40px",
        "fontWeight": "normal",
        "fontStyle": "normal",
        "color": "var(--textPrimary)",
        "textAlign": "left",
        "letterSpacing": "0",
        "lineHeight": "135%",
        "textDecoration": "none",
        "textTransform": "none",
        "paddingInlineStart": "0px",
        "paragraphSpacing": "0px"
      },
      "blockHeading": {
        "fontFamily": "var(--font-heading)",
        "fontSize": "24px",
        "fontWeight": "bold",
        "fontStyle": "normal",
        "color": "var(--textPrimary)",
        "textAlign": "left",
        "letterSpacing": "0",
        "lineHeight": "140%",
        "textDecoration": "none",
        "textTransform": "none",
        "paddingInlineStart": "0px",
        "paragraphSpacing": "0px"
      },
      "subheading": {
        "fontFamily": "var(--font-body)",
        "fontSize": "20px",
        "fontWeight": "bold",
        "fontStyle": "normal",
        "color": "var(--textPrimary)",
        "textAlign": "left",
        "letterSpacing": "0.01em",
        "lineHeight": "150%",
        "textDecoration": "none",
        "textTransform": "none",
        "paddingInlineStart": "0px",
        "paragraphSpacing": "0px"
      },
      "question": {
        "fontFamily": "var(--font-heading)",
        "fontSize": "24px",
        "fontWeight": "normal",
        "fontStyle": "normal",
        "color": "var(--textPrimary)",
        "textAlign": "left",
        "letterSpacing": "0",
        "lineHeight": "150%",
        "textDecoration": "none",
        "textTransform": "none",
        "paddingInlineStart": "0px",
        "paragraphSpacing": "0px"
      },
      "caption": {
        "fontFamily": "var(--font-body)",
        "fontSize": "13px",
        "fontWeight": "normal",
        "fontStyle": "normal",
        "color": "var(--textPrimary)",
        "textAlign": "left",
        "letterSpacing": "0.02em",
        "lineHeight": "170%",
        "textDecoration": "none",
        "textTransform": "none",
        "paddingInlineStart": "0px",
        "paragraphSpacing": "0px"
      },
      "paragraph": {
        "fontFamily": "var(--font-body)",
        "fontSize": "16px",
        "fontWeight": "normal",
        "fontStyle": "normal",
        "color": "var(--textPrimary)",
        "textAlign": "left",
        "letterSpacing": "0.01em",
        "lineHeight": "190%",
        "textDecoration": "none",
        "textTransform": "none",
        "paddingInlineStart": "0px",
        "paragraphSpacing": "0px"
      },
      "buttonLabel": {
        "fontFamily": "var(--font-body)",
        "fontSize": "14px",
        "fontWeight": "bold",
        "fontStyle": "normal",
        "color": "var(--textInverse)",
        "textAlign": "center",
        "letterSpacing": "0.06em",
        "lineHeight": "125%",
        "textDecoration": "none",
        "textTransform": "uppercase",
        "paddingInlineStart": "0px",
        "paragraphSpacing": "0px"
      }
    },
    "canvas": {
      "background": "var(--background)"
    },
    "header": {
      "background": "var(--background)",
      "border": "1px solid var(--secondary)"
    },
    "footer": {
      "background": "var(--background)",
      "border": "1px solid var(--secondary)"
    },
    "lessonHeader": {
      "background": "var(--accent)"
    },
    "topic": {
      "background": "var(--background)",
      "border": "1px solid var(--secondary)"
    },
    "navigation": {
      "background": "var(--backgroundSubtle)",
      "border": "1px solid var(--secondary)"
    },
    "button": {
      "background": "var(--accent)"
    },
    "pagination": {
      "background": "var(--backgroundSubtle)",
      "horizontalSpacingScale": "1",
      "verticalSpacingScale": "1",
      "radiusScale": "1"
    },
    "paragraphBlock": {
      "background": "transparent",
      "cardBackgroundColor": "var(--backgroundSubtle)",
      "cardBorder": "1px solid var(--secondary)",
      "cardShadowOffset": "0px 2px 6px",
      "cardShadowColor": "var(--foreground)",
      "cardShadowOpacity": "8%",
      "nestedAccentColor": "var(--accent)",
      "horizontalSpacingScale": "1",
      "verticalSpacingScale": "1",
      "radiusScale": "1"
    },
    "imageBlock": {
      "background": "transparent",
      "horizontalSpacingScale": "1",
      "verticalSpacingScale": "1",
      "radiusScale": "1"
    },
    "videoBlock": {
      "background": "transparent",
      "cardBackgroundColor": "var(--backgroundSubtle)",
      "cardBorder": "1px solid var(--secondary)",
      "cardShadowOffset": "0px 2px 6px",
      "cardShadowColor": "var(--foreground)",
      "cardShadowOpacity": "8%",
      "horizontalSpacingScale": "1",
      "verticalSpacingScale": "1",
      "radiusScale": "1"
    },
    "imageGrid": {
      "background": "transparent",
      "cardBackgroundColor": "var(--backgroundSubtle)",
      "cardBorder": "1px solid var(--accent)",
      "cardShadowOffset": "0px 2px 8px",
      "cardShadowColor": "var(--foreground)",
      "cardShadowOpacity": "8%",
      "horizontalSpacingScale": "1",
      "verticalSpacingScale": "1",
      "radiusScale": "1"
    },
    "accordion": {
      "background": "transparent",
      "cardBackgroundColor": "var(--backgroundSubtle)",
      "cardBorder": "1px solid var(--secondary)",
      "cardShadowOffset": "0px 2px 6px",
      "cardShadowColor": "var(--foreground)",
      "cardShadowOpacity": "8%",
      "horizontalSpacingScale": "1",
      "verticalSpacingScale": "1",
      "radiusScale": "1"
    },
    "carousel": {
      "background": "transparent",
      "cardBackgroundColor": "var(--backgroundSubtle)",
      "cardBorder": "1px solid var(--secondary)",
      "cardShadowOffset": "0px 2px 6px",
      "cardShadowColor": "var(--foreground)",
      "cardShadowOpacity": "8%",
      "horizontalSpacingScale": "1",
      "verticalSpacingScale": "1",
      "radiusScale": "1"
    },
    "flipCard": {
      "background": "transparent",
      "cardFrontBackgroundColor": "var(--backgroundSubtle)",
      "cardBackBackgroundColor": "var(--accent)",
      "arrowColor": "var(--textInverse)",
      "cardBorder": "1px solid var(--secondary)",
      "cardShadowOffset": "0px 2px 6px",
      "cardShadowColor": "var(--foreground)",
      "cardShadowOpacity": "8%",
      "horizontalSpacingScale": "1",
      "verticalSpacingScale": "1",
      "radiusScale": "1"
    },
    "tabs": {
      "background": "transparent",
      "activeBg": "var(--accent)",
      "inactiveBg": "var(--backgroundSubtle)",
      "containerBg": "var(--backgroundSubtle)",
      "horizontalSpacingScale": "1",
      "verticalSpacingScale": "1",
      "radiusScale": "1"
    },
    "timeline": {
      "background": "transparent",
      "cardBackgroundColor": "var(--backgroundSubtle)",
      "cardBorder": "1px solid var(--secondary)",
      "cardShadowOffset": "0px 2px 6px",
      "cardShadowColor": "var(--foreground)",
      "cardShadowOpacity": "8%",
      "trackColor": "var(--secondary)",
      "progressCompletedBg": "var(--accent)",
      "progressCurrentBorder": "var(--accent)",
      "progressUnreachedBg": "var(--secondary)",
      "progressUnreachedBorder": "var(--backgroundSubtle)",
      "horizontalSpacingScale": "1",
      "verticalSpacingScale": "1",
      "radiusScale": "1"
    },
    "assessment": {
      "background": "transparent",
      "optionTextColor": "var(--textPrimary)",
      "optionIndicatorColor": "var(--accent)",
      "optionSelectedColor": "var(--accent)",
      "optionCheckmarkColor": "var(--textInverse)",
      "optionBackgroundColor": "var(--background)",
      "optionHoverBackgroundColor": "var(--backgroundSubtle)",
      "buttonBackgroundColor": "var(--accent)",
      "buttonTextColor": "var(--textInverse)",
      "buttonHoverBackgroundColor": "var(--accent)",
      "feedbackCorrectColor": "#D7F7E1",
      "feedbackIncorrectColor": "#FFEBE8",
      "feedbackTextColor": "#111111",
      "optionBorderCorrectColor": "#079355",
      "optionBorderIncorrectColor": "#D73220",
      "horizontalSpacingScale": "1",
      "verticalSpacingScale": "1",
      "radiusScale": "1"
    }
  }
}
```
