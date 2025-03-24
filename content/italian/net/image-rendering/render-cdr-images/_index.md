---
title: Rendering di immagini CDR
linktitle: Rendering di immagini CDR
second_title: API GroupDocs.Viewer .NET
description: Scopri come eseguire il rendering delle immagini CDR in HTML, JPG, PNG e PDF utilizzando GroupDocs.Viewer per .NET. Converti facilmente i file CorelDRAW con questo tutorial.
weight: 12
url: /it/net/image-rendering/render-cdr-images/
---
## introduzione
In questo tutorial ti guideremo attraverso il processo di rendering delle immagini CDR (CorelDRAW) utilizzando GroupDocs.Viewer per .NET. CDR è un formato di file associato principalmente a CorelDRAW, un editor di grafica vettoriale. Con GroupDocs.Viewer puoi convertire facilmente file CDR in vari formati come HTML, JPG, PNG e PDF.
## Prerequisiti
Prima di iniziare, assicurati di possedere i seguenti prerequisiti:
1.  GroupDocs.Viewer per .NET: assicurati di aver installato GroupDocs.Viewer per .NET. Puoi scaricarlo da[Qui](https://releases.groupdocs.com/viewer/net/).
2. Directory dei documenti: prepara una directory in cui desideri salvare le immagini renderizzate.
3. Conoscenza di base di C#: la familiarità con il linguaggio di programmazione C# è necessaria per comprendere gli esempi di codice.
## Importa spazi dei nomi
Prima di immergerti negli esempi di codice, importa gli spazi dei nomi necessari nel tuo file C#:
```csharp
using GroupDocs.Viewer.Options;
using System;
using System.IO;
```
Ora suddividiamo ciascun esempio in più passaggi:
## Rendering in HTML
1. Definisci la directory di output in cui desideri salvare i file HTML renderizzati:
```csharp
string outputDirectory = "Your Document Directory";
```
2. Specificare il formato del percorso file per i file HTML:
```csharp
string pageFilePathFormat = Path.Combine(outputDirectory, "cdr_result_{0}.html");
```
3. Utilizza la classe Viewer per eseguire il rendering del file CDR in HTML:
```csharp
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_CDR))
{
    HtmlViewOptions options = HtmlViewOptions.ForEmbeddedResources(pageFilePathFormat);
    
    viewer.View(options);
}
```
## Rendering in JPG
1. Definire il formato del percorso file per i file JPG:
```csharp
pageFilePathFormat = Path.Combine(outputDirectory, "cdr_result_{0}.jpg");
```
2. Utilizza la classe Viewer per eseguire il rendering del file CDR in JPG:
```csharp
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_CDR))
{
    JpgViewOptions options = new JpgViewOptions(pageFilePathFormat);
    
    viewer.View(options);
}
```
## Rendering in PNG
1. Definire il formato del percorso file per i file PNG:
```csharp
pageFilePathFormat = Path.Combine(outputDirectory, "cdr_result_{0}.png");
```
2. Utilizza la classe Viewer per eseguire il rendering del file CDR in PNG:
```csharp
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_CDR))
{
    PngViewOptions options = new PngViewOptions(pageFilePathFormat);
    
    viewer.View(options);
}
```
## Rendering in PDF
1. Definire il formato del percorso file per PDF:
```csharp
pageFilePathFormat = Path.Combine(outputDirectory, "cdr_result.pdf");
```
2. Utilizza la classe Viewer per eseguire il rendering del file CDR in PDF:
```csharp
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_CDR))
{
    PdfViewOptions options = new PdfViewOptions(pageFilePathFormat);
    
    viewer.View(options);
}
```
3.  Facoltativamente, è possibile specificare le opzioni di rendering o eseguire il rendering di pagine specifiche passando parametri aggiuntivi al file`viewer.View()` metodo.
## Conclusione
Il rendering delle immagini CDR in vari formati come HTML, JPG, PNG e PDF utilizzando GroupDocs.Viewer per .NET è un processo semplice. Seguendo i passaggi delineati in questo tutorial, puoi convertire in modo efficiente i file CDR in diversi formati in base alle tue esigenze.
## Domande frequenti
### GroupDocs.Viewer per .NET è compatibile con tutte le versioni dei file CDR?
GroupDocs.Viewer per .NET supporta il rendering di file CDR creati da diverse versioni di CorelDRAW.
### Posso personalizzare l'output dei file renderizzati?
Sì, GroupDocs.Viewer per .NET fornisce varie opzioni per personalizzare l'output, come la regolazione della qualità dell'immagine, l'impostazione della filigrana, ecc.
### GroupDocs.Viewer per .NET richiede dipendenze esterne?
No, GroupDocs.Viewer per .NET è una libreria autonoma e non richiede dipendenze esterne per il rendering dei documenti.
### È disponibile una versione di prova per GroupDocs.Viewer per .NET?
 Sì, puoi scaricare una versione di prova gratuita di GroupDocs.Viewer per .NET da[Qui](https://releases.groupdocs.com/).
### Dove posso ottenere supporto per GroupDocs.Viewer per .NET?
 Puoi ottenere supporto dal forum della community GroupDocs.Viewer[Qui](https://forum.groupdocs.com/c/viewer/9).