---
"description": "Scopri come convertire immagini FODG e ODG in HTML, JPG, PNG e PDF utilizzando GroupDocs.Viewer per .NET. Migliora la gestione dei tuoi documenti."
"linktitle": "Rendering di immagini FODG e ODG"
"second_title": "API .NET di GroupDocs.Viewer"
"title": "Rendering di immagini FODG e ODG"
"url": "/it/net/image-rendering/render-fodg-odg-images/"
"weight": 15
---

# Rendering di immagini FODG e ODG

## Introduzione
Nel mondo dello sviluppo software, la gestione efficiente dei formati di documento è fondamentale. GroupDocs.Viewer per .NET è un potente strumento progettato per semplificare il processo di rendering di immagini FODG e ODG nelle applicazioni .NET. Questo tutorial vi guiderà attraverso i passaggi necessari per il rendering di queste immagini in vari formati, come HTML, JPG, PNG e PDF, utilizzando GroupDocs.Viewer per .NET.

![Rendering di immagini FODG e ODG con GroupDocs.Viewer per .NET](/viewer/image-rendering/render-fodg-and--odg-images.png)

## Prerequisiti
Prima di immergerti nel tutorial, assicurati di avere i seguenti prerequisiti:
1. GroupDocs.Viewer per .NET: Scarica e installa GroupDocs.Viewer per .NET da [Qui](https://releases.groupdocs.com/viewer/net/).
2. .NET Framework: assicurati che .NET Framework sia installato sul tuo sistema.
3. Conoscenza di base di C#: sarà utile avere familiarità con il linguaggio di programmazione C#.

## Importa spazi dei nomi
Prima di iniziare l'implementazione, importare gli spazi dei nomi necessari:
```csharp
using GroupDocs.Viewer.Options;
using System;
using System.IO;
```
## Passaggio 1: impostare la directory di output
```csharp
string outputDirectory = "Your Document Directory";
```
Sostituire `"Your Document Directory"` con il percorso della directory in cui si desidera salvare le immagini renderizzate.
## Passaggio 2: rendering in HTML
```csharp
string pageFilePathFormat = Path.Combine(outputDirectory, "fodg_result.html");
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_FODG))
{
    HtmlViewOptions options = HtmlViewOptions.ForEmbeddedResources(pageFilePathFormat);
    viewer.View(options);
}
```
Questo passaggio converte l'immagine FODG in formato HTML.
## Passaggio 3: rendering in JPG
```csharp
pageFilePathFormat = Path.Combine(outputDirectory, "fodg_result.jpg");
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_FODG))
{
    JpgViewOptions options = new JpgViewOptions(pageFilePathFormat);
    viewer.View(options);
}
```
Qui, l'immagine FODG è renderizzata in formato JPG.
## Passaggio 4: rendering in PNG
```csharp
pageFilePathFormat = Path.Combine(outputDirectory, "fodg_result.png");
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_FODG))
{
    PngViewOptions options = new PngViewOptions(pageFilePathFormat);
    viewer.View(options);
}
```
Questo passaggio converte l'immagine FODG in formato PNG.
## Passaggio 5: rendering in PDF
```csharp
pageFilePathFormat = Path.Combine(outputDirectory, "fodg_result.pdf");
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_FODG))
{
    PdfViewOptions options = new PdfViewOptions(pageFilePathFormat);
    viewer.View(options);
}
```
Infine, l'immagine FODG viene renderizzata in formato PDF.

## Conclusione
In questo tutorial abbiamo illustrato come eseguire il rendering di immagini FODG e ODG in vari formati utilizzando GroupDocs.Viewer per .NET. Seguendo questi passaggi, è possibile integrare perfettamente le funzionalità di rendering dei documenti nelle applicazioni .NET.
## Domande frequenti
### GroupDocs.Viewer per .NET è compatibile con tutte le versioni di .NET Framework?
GroupDocs.Viewer per .NET è compatibile con un'ampia gamma di versioni di .NET Framework, comprese quelle più recenti.
### Posso eseguire il rendering dei documenti in modo asincrono con GroupDocs.Viewer per .NET?
Sì, GroupDocs.Viewer per .NET offre funzionalità di rendering asincrono per prestazioni migliorate.
### GroupDocs.Viewer per .NET supporta il rendering di documenti crittografati?
Sì, GroupDocs.Viewer per .NET supporta il rendering di documenti crittografati con chiavi di decrittazione appropriate.
### È possibile personalizzare l'output di rendering con GroupDocs.Viewer per .NET?
Certamente, GroupDocs.Viewer per .NET offre diverse opzioni di personalizzazione per adattare l'output di rendering alle tue esigenze.
### Posso eseguire il rendering di documenti da posizioni di archiviazione remote utilizzando GroupDocs.Viewer per .NET?
Sì, GroupDocs.Viewer per .NET supporta il rendering di documenti da posizioni di archiviazione sia locali che remote.