---
title: Rendering di immagini FODG e ODG
linktitle: Rendering di immagini FODG e ODG
second_title: API GroupDocs.Viewer .NET
description: Scopri come eseguire il rendering di immagini FODG e ODG in HTML, JPG, PNG e PDF utilizzando GroupDocs.Viewer per .NET. Migliora la gestione dei tuoi documenti.
type: docs
weight: 15
url: /it/net/image-rendering/render-fodg-odg-images/
---
## introduzione
Nel mondo dello sviluppo software, la gestione efficiente dei formati dei documenti è fondamentale. GroupDocs.Viewer per .NET è un potente strumento progettato per semplificare il processo di rendering di immagini FODG e ODG all'interno delle applicazioni .NET. Questo tutorial ti guiderà attraverso i passaggi necessari per eseguire il rendering di queste immagini in vari formati, come HTML, JPG, PNG e PDF, utilizzando GroupDocs.Viewer per .NET.
## Prerequisiti
Prima di immergerti nel tutorial, assicurati di possedere i seguenti prerequisiti:
1.  GroupDocs.Viewer per .NET: scarica e installa GroupDocs.Viewer per .NET da[Qui](https://releases.groupdocs.com/viewer/net/).
2. .NET Framework: assicurati di avere .NET Framework installato sul tuo sistema.
3. Conoscenza di base di C#: sarà utile la familiarità con il linguaggio di programmazione C#.

## Importa spazi dei nomi
Prima di iniziare con l'implementazione, importa gli spazi dei nomi necessari:
```csharp
using GroupDocs.Viewer.Options;
using System;
using System.IO;
```
## Passaggio 1: imposta la directory di output
```csharp
string outputDirectory = "Your Document Directory";
```
 Sostituire`"Your Document Directory"`con il percorso della directory in cui desideri salvare le immagini renderizzate.
## Passaggio 2: rendering in HTML
```csharp
string pageFilePathFormat = Path.Combine(outputDirectory, "fodg_result.html");
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_FODG))
{
    HtmlViewOptions options = HtmlViewOptions.ForEmbeddedResources(pageFilePathFormat);
    viewer.View(options);
}
```
Questo passaggio esegue il rendering dell'immagine FODG in formato HTML.
## Passaggio 3: rendering in JPG
```csharp
pageFilePathFormat = Path.Combine(outputDirectory, "fodg_result.jpg");
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_FODG))
{
    JpgViewOptions options = new JpgViewOptions(pageFilePathFormat);
    viewer.View(options);
}
```
Qui, l'immagine FODG viene renderizzata in formato JPG.
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
In questo tutorial abbiamo esplorato come eseguire il rendering di immagini FODG e ODG in vari formati utilizzando GroupDocs.Viewer per .NET. Seguendo questi passaggi è possibile integrare perfettamente le funzionalità di rendering dei documenti nelle applicazioni .NET.
## Domande frequenti
### GroupDocs.Viewer per .NET è compatibile con tutte le versioni di .NET Framework?
GroupDocs.Viewer per .NET è compatibile con un'ampia gamma di versioni di .NET Framework, comprese quelle più recenti.
### Posso eseguire il rendering dei documenti in modo asincrono con GroupDocs.Viewer per .NET?
Sì, GroupDocs.Viewer per .NET fornisce funzionalità di rendering asincrono per migliorare le prestazioni.
### GroupDocs.Viewer per .NET supporta il rendering di documenti crittografati?
Sì, GroupDocs.Viewer per .NET supporta il rendering di documenti crittografati con chiavi di decrittografia appropriate.
### È possibile personalizzare l'output del rendering con GroupDocs.Viewer per .NET?
Assolutamente sì, GroupDocs.Viewer per .NET offre varie opzioni di personalizzazione per adattare l'output di rendering in base alle vostre esigenze.
### Posso eseguire il rendering di documenti da posizioni di archiviazione remote utilizzando GroupDocs.Viewer per .NET?
Sì, GroupDocs.Viewer per .NET supporta il rendering di documenti da posizioni di archiviazione sia locali che remote.