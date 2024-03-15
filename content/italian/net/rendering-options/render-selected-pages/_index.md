---
title: Rendering delle pagine selezionate
linktitle: Rendering delle pagine selezionate
second_title: API GroupDocs.Viewer .NET
description: Scopri come eseguire il rendering delle pagine selezionate dai documenti utilizzando Groupdocs.Viewer per .NET. Tutorial passo passo con esempi di codice inclusi.
type: docs
weight: 17
url: /it/net/rendering-options/render-selected-pages/
---
## introduzione

In questo tutorial, approfondiremo come utilizzare Groupdocs.Viewer per .NET per eseguire il rendering delle pagine selezionate da un documento. Che tu sia uno sviluppatore esperto o che tu abbia appena iniziato, questa guida passo passo ti guiderà attraverso il processo con facilità.

## Prerequisiti

Prima di iniziare, assicurati di disporre dei seguenti prerequisiti:

### 1. Installazione

 Assicurati di avere Groupdocs.Viewer for .NET installato nel tuo ambiente di sviluppo. In caso contrario, puoi scaricarlo da[Link per scaricare](https://releases.groupdocs.com/viewer/net/).

## Importazione di spazi dei nomi

Nel file di codice C# importa gli spazi dei nomi necessari per accedere alle classi e ai metodi richiesti. Puoi farlo usando il file`using` direttiva:

```csharp
using System;
using System.IO;
using GroupDocs.Viewer.Options;
```

Ora suddividiamo il codice di esempio fornito in più passaggi:

## Passaggio 1: imposta la directory di output

 Definire la directory in cui si desidera salvare le pagine renderizzate. Sostituire`"Your Document Directory"` con il percorso della directory desiderato.

```csharp
string outputDirectory = "Your Document Directory";
```

## Passaggio 2: definire il formato del percorso del file di paging

Specificare il formato per i percorsi dei file delle pagine sottoposte a rendering. Questo verrà utilizzato per salvare ogni pagina come file HTML nella directory di output.

```csharp
string pageFilePathFormat = Path.Combine(outputDirectory, "page_{0}.html");
```

## Passaggio 3: istanziare l'oggetto visualizzatore

Crea un'istanza della classe Viewer, passando come argomento il percorso del documento di cui vuoi eseguire il rendering.

```csharp
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_DOCX))
```

## Passaggio 4: configura le opzioni di visualizzazione HTML

Configura le opzioni di visualizzazione HTML per il rendering. In questo esempio stiamo configurando le opzioni per incorporare risorse nell'output HTML.

```csharp
HtmlViewOptions options = HtmlViewOptions.ForEmbeddedResources(pageFilePathFormat);
```

## Passaggio 5: rendering delle pagine selezionate

Specifica i numeri di pagina di cui desideri eseguire il rendering. In questo caso, stiamo eseguendo il rendering delle pagine da 1 a 3. Quindi, chiamiamo il metodo View sull'oggetto Viewer, passando le opzioni e i numeri di pagina come argomenti.

```csharp
viewer.View(options, 1, 3);
```

## Passaggio 6: risultato dell'output

Infine, visualizza un messaggio che indica il rendering riuscito del documento e la posizione in cui vengono salvati i file di output.

```csharp
Console.WriteLine($"\nSource document rendered successfully.\nCheck output in {outputDirectory}.");
```

## Conclusione

Congratulazioni! Hai imparato con successo come eseguire il rendering delle pagine selezionate da un documento utilizzando Groupdocs.Viewer per .NET. Con queste conoscenze, ora puoi integrare facilmente le funzionalità di rendering dei documenti nelle tue applicazioni .NET.

## Domande frequenti

### D: Posso eseguire il rendering di pagine di diversi tipi di documenti, come PDF o immagini?

R: Sì, Groupdocs.Viewer per .NET supporta il rendering di pagine da vari formati di documenti, inclusi PDF, documenti di Microsoft Office e file di immagine.

### D: È disponibile una versione di prova da provare prima dell'acquisto?

 R: Sì, puoi accedere a una versione di prova gratuita di Groupdocs.Viewer per .NET da[sito web](https://releases.groupdocs.com/).

### D: Posso personalizzare il formato di output diverso da HTML?

R: Assolutamente, Groupdocs.Viewer per .NET fornisce opzioni per visualizzare le pagine come immagini, PDF e altro, oltre all'HTML.

### D: Come posso ottenere licenze temporanee a scopo di test?

R: Le licenze temporanee possono essere acquistate da[pagina della licenza temporanea](https://purchase.groupdocs.com/temporary-license/) sul sito web di Groupdocs.

### D: Dove posso chiedere assistenza o ottenere aiuto per eventuali problemi che riscontro?

 R: Puoi visitare il[Forum di Groupdocs.Viewer](https://forum.groupdocs.com/c/viewer/9) per il supporto e la guida della comunità e degli sviluppatori.