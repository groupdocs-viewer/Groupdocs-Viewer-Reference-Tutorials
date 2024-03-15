---
title: Rendering di immagini SVG e SVGZ
linktitle: Rendering di immagini SVG e SVGZ
second_title: API GroupDocs.Viewer .NET
description: Scopri come eseguire il rendering di immagini SVG e SVGZ utilizzando GroupDocs.Viewer per .NET. Converti grafica vettoriale in HTML, JPG, PNG e PDF senza sforzo.
type: docs
weight: 16
url: /it/net/image-rendering/render-svg-svgz-images/
---
## introduzione
In questo tutorial ti guideremo attraverso il processo di rendering delle immagini SVG e SVGZ utilizzando GroupDocs.Viewer per .NET. GroupDocs.Viewer per .NET è una potente API per il rendering di documenti che consente agli sviluppatori di eseguire il rendering di vari formati di documenti nelle loro applicazioni .NET. SVG e SVGZ sono formati di immagine popolari utilizzati per la grafica vettoriale e con GroupDocs.Viewer per .NET puoi facilmente renderizzarli in diversi formati di output come HTML, JPG, PNG e PDF.
## Prerequisiti
Prima di iniziare, assicurati di avere i seguenti prerequisiti installati e configurati:
1.  GroupDocs.Viewer per .NET: scarica e installa GroupDocs.Viewer per .NET da[Qui](https://releases.groupdocs.com/viewer/net/).
2. Ambiente di sviluppo: assicurati di disporre di un ambiente di sviluppo funzionante per lo sviluppo .NET, come Visual Studio.
3. File SVGZ di esempio: tieni pronto un file SVGZ di esempio per il test.

## Importa spazi dei nomi
Prima di immergerci nel codice, importiamo gli spazi dei nomi necessari:
```csharp
using GroupDocs.Viewer.Options;
using System;
using System.IO;
```
## Passaggio 1: renderizza SVGZ in HTML
```csharp
string outputDirectory = "Your Document Directory";
string pageFilePathFormat = Path.Combine(outputDirectory, "svgz_result.html");
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_SVGZ))
{
    HtmlViewOptions options = HtmlViewOptions.ForEmbeddedResources(pageFilePathFormat);
    viewer.View(options);
}
```

## Passaggio 2: renderizza SVGZ in JPG
```csharp
pageFilePathFormat = Path.Combine(outputDirectory, "svgz_result.jpg");
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_SVGZ))
{
    JpgViewOptions options = new JpgViewOptions(pageFilePathFormat);
    
    viewer.View(options);
}
```

## Passaggio 3: renderizza SVGZ in PNG
```csharp
pageFilePathFormat = Path.Combine(outputDirectory, "svgz_result.png");
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_SVGZ))
{
    PngViewOptions options = new PngViewOptions(pageFilePathFormat);
   
    viewer.View(options);
}
```

## Passaggio 4: renderizza SVGZ in PDF
```csharp
pageFilePathFormat = Path.Combine(outputDirectory, "svgz_result.pdf");
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_SVGZ))
{
    PdfViewOptions options = new PdfViewOptions(pageFilePathFormat);
   
    viewer.View(options);
}
```

## Conclusione
In questo tutorial, abbiamo imparato come eseguire il rendering di immagini SVG e SVGZ utilizzando GroupDocs.Viewer per .NET. Con pochi semplici passaggi, puoi convertire le immagini SVGZ in vari formati di output come HTML, JPG, PNG e PDF, rendendole accessibili e visualizzabili in diversi ambienti.
## Domande frequenti
### GroupDocs.Viewer può eseguire il rendering di altri formati di immagine?
Sì, GroupDocs.Viewer supporta il rendering di vari formati di immagine tra cui PNG, JPEG, BMP, TIFF, GIF e altri.
### GroupDocs.Viewer è compatibile con .NET Core?
Sì, GroupDocs.Viewer è compatibile sia con .NET Framework che con .NET Core.
### Posso personalizzare le opzioni di rendering?
Sì, GroupDocs.Viewer fornisce ampie opzioni di rendering che ti consentono di personalizzare l'output in base alle tue esigenze.
### GroupDocs.Viewer richiede dipendenze di terze parti?
No, GroupDocs.Viewer è un'API autonoma e non richiede dipendenze di terze parti per il rendering dei documenti.
### È disponibile una versione di prova per i test?
Sì, puoi scaricare una versione di prova gratuita di GroupDocs.Viewer da[Qui](https://releases.groupdocs.com/) per valutarne le caratteristiche prima di effettuare l'acquisto.