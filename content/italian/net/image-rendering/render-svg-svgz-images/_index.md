---
"description": "Scopri come renderizzare immagini SVG e SVGZ utilizzando GroupDocs.Viewer per .NET. Converti la grafica vettoriale in HTML, JPG, PNG e PDF senza sforzo."
"linktitle": "Rendering di immagini SVG e SVGZ"
"second_title": "API .NET di GroupDocs.Viewer"
"title": "Rendering di immagini SVG e SVGZ"
"url": "/it/net/image-rendering/render-svg-svgz-images/"
"weight": 16
---

# Rendering di immagini SVG e SVGZ

## Introduzione
In questo tutorial, ti guideremo attraverso il processo di rendering di immagini SVG e SVGZ utilizzando GroupDocs.Viewer per .NET. GroupDocs.Viewer per .NET è una potente API per il rendering di documenti che consente agli sviluppatori di visualizzare vari formati di documento nelle loro applicazioni .NET. SVG e SVGZ sono formati di immagine molto diffusi per la grafica vettoriale e, con GroupDocs.Viewer per .NET, puoi facilmente renderli in diversi formati di output come HTML, JPG, PNG e PDF.

![Rendering di immagini SVG e SVGZ con GroupDocs.Viewer per .NET](/viewer/image-rendering/render-svg-and-svgz-images.png)

## Prerequisiti
Prima di iniziare, assicurati di aver installato e configurato i seguenti prerequisiti:
1. GroupDocs.Viewer per .NET: Scarica e installa GroupDocs.Viewer per .NET da [Qui](https://releases.groupdocs.com/viewer/net/).
2. Ambiente di sviluppo: assicurati di disporre di un ambiente di sviluppo funzionante per lo sviluppo .NET, come Visual Studio.
3. File SVGZ di esempio: tieni pronto un file SVGZ di esempio per il test.

## Importa spazi dei nomi
Prima di immergerci nel codice, importiamo gli spazi dei nomi necessari:
```csharp
using GroupDocs.Viewer.Options;
using System;
using System.IO;
```
## Passaggio 1: rendering di SVGZ in HTML
```csharp
string outputDirectory = "Your Document Directory";
string pageFilePathFormat = Path.Combine(outputDirectory, "svgz_result.html");
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_SVGZ))
{
    HtmlViewOptions options = HtmlViewOptions.ForEmbeddedResources(pageFilePathFormat);
    viewer.View(options);
}
```

## Passaggio 2: rendering SVGZ in JPG
```csharp
pageFilePathFormat = Path.Combine(outputDirectory, "svgz_result.jpg");
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_SVGZ))
{
    JpgViewOptions options = new JpgViewOptions(pageFilePathFormat);
    
    viewer.View(options);
}
```

## Passaggio 3: convertire SVGZ in PNG
```csharp
pageFilePathFormat = Path.Combine(outputDirectory, "svgz_result.png");
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_SVGZ))
{
    PngViewOptions options = new PngViewOptions(pageFilePathFormat);
   
    viewer.View(options);
}
```

## Passaggio 4: convertire SVGZ in PDF
```csharp
pageFilePathFormat = Path.Combine(outputDirectory, "svgz_result.pdf");
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_SVGZ))
{
    PdfViewOptions options = new PdfViewOptions(pageFilePathFormat);
   
    viewer.View(options);
}
```

## Conclusione
In questo tutorial abbiamo imparato come visualizzare immagini SVG e SVGZ utilizzando GroupDocs.Viewer per .NET. Con pochi semplici passaggi, è possibile convertire le immagini SVGZ in diversi formati di output come HTML, JPG, PNG e PDF, rendendole accessibili e visualizzabili in diversi ambienti.
## Domande frequenti
### GroupDocs.Viewer può riprodurre altri formati di immagine?
Sì, GroupDocs.Viewer supporta il rendering di vari formati di immagine, tra cui PNG, JPEG, BMP, TIFF, GIF e altri.
### GroupDocs.Viewer è compatibile con .NET Core?
Sì, GroupDocs.Viewer è compatibile sia con .NET Framework che con .NET Core.
### Posso personalizzare le opzioni di rendering?
Sì, GroupDocs.Viewer offre ampie opzioni di rendering che consentono di personalizzare l'output in base alle proprie esigenze.
### GroupDocs.Viewer richiede dipendenze di terze parti?
No, GroupDocs.Viewer è un'API autonoma e non richiede dipendenze di terze parti per il rendering dei documenti.
### Esiste una versione di prova disponibile per effettuare dei test?
Sì, puoi scaricare una versione di prova gratuita di GroupDocs.Viewer da [Qui](https://releases.groupdocs.com/) per valutarne le caratteristiche prima di procedere all'acquisto.