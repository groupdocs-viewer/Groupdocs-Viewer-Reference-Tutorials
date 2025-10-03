---
"description": "Scopri come regolare la qualità delle immagini nei documenti PDF utilizzando GroupDocs.Viewer per .NET. Segui il nostro tutorial passo passo per un'integrazione perfetta."
"linktitle": "Regola la qualità dell'immagine in PDF"
"second_title": "API .NET di GroupDocs.Viewer"
"title": "Regola la qualità dell'immagine in PDF"
"url": "/it/net/pdf-rendering-options/adjust-image-quality-pdf/"
"weight": 10
type: docs
---
# Regola la qualità dell'immagine in PDF

## Introduzione
GroupDocs.Viewer per .NET è una potente libreria che consente agli sviluppatori di integrare facilmente le funzionalità di rendering dei documenti nelle loro applicazioni .NET. Una delle funzionalità principali di questa libreria è la possibilità di regolare la qualità delle immagini durante il rendering dei documenti PDF. In questo tutorial, vi guideremo passo dopo passo attraverso il processo di regolazione della qualità delle immagini utilizzando GroupDocs.Viewer per .NET.

![Regola la qualità dell'immagine in PDF con GroupDocs.Viewer .NET](/viewer/pdf-rendering-options/adjust-image-quality-in-pdf.png)

## Prerequisiti
Prima di iniziare, assicurati di avere i seguenti prerequisiti:
1. Conoscenza di base della programmazione C#.
2. Visual Studio installato sul sistema.
3. Scaricato e installato GroupDocs.Viewer per la libreria .NET. Puoi scaricarlo da [Qui](https://releases.groupdocs.com/viewer/net/).

## Importa spazi dei nomi
Per prima cosa, è necessario importare gli spazi dei nomi necessari per lavorare con GroupDocs.Viewer per .NET:
```csharp
using System;
using System.IO;
using GroupDocs.Viewer.Options;
```
## Passaggio 1: definire la directory di output
```csharp
string outputDirectory = "Your Document Directory";
```
Sostituire `"Your Document Directory"` con il percorso in cui si desidera salvare le pagine HTML renderizzate.
## Passaggio 2: definire il formato del percorso del file di paging
```csharp
string pageFilePathFormat = Path.Combine(outputDirectory, "page_{0}.html");
```
Questa riga definisce il formato del percorso del file di ogni pagina HTML renderizzata. `{0}` è un segnaposto per il numero di pagina.
## Passaggio 3: regola la qualità dell'immagine
```csharp
using (Viewer viewer = new Viewer("Your PDF File Path"))
{
    HtmlViewOptions options = HtmlViewOptions.ForEmbeddedResources(pageFilePathFormat);
    options.PdfOptions.ImageQuality = ImageQuality.Medium;
    viewer.View(options);
}
```
Sostituire `"Your PDF File Path"` con il percorso al tuo documento PDF.
## Passaggio 4: visualizzare il percorso di output
```csharp
Console.WriteLine($"\nSource document rendered successfully.\nCheck output in {outputDirectory}.");
```
Questa riga visualizza il percorso in cui vengono salvate le pagine HTML renderizzate.

## Conclusione
In questo tutorial abbiamo imparato come regolare la qualità delle immagini durante il rendering di documenti PDF utilizzando GroupDocs.Viewer per .NET. Seguendo i semplici passaggi descritti sopra, è possibile personalizzare facilmente la qualità delle immagini in base alle proprie esigenze.
## Domande frequenti
### Posso regolare la qualità dell'immagine per formati di documenti diversi dal PDF?
Sì, GroupDocs.Viewer per .NET supporta vari formati di documenti ed è possibile regolare la qualità dell'immagine per la maggior parte di essi.
### Quali sono le opzioni disponibili per la qualità dell'immagine?
GroupDocs.Viewer per .NET offre opzioni per la qualità delle immagini Bassa, Media e Alta.
### Esiste un modo per visualizzare in anteprima il documento prima di elaborarlo con la qualità dell'immagine regolata?
Sì, puoi utilizzare GroupDocs.Viewer per .NET per generare anteprime di documenti con diverse impostazioni di qualità delle immagini.
### GroupDocs.Viewer per .NET richiede una licenza per uso commerciale?
Sì, è necessario ottenere una licenza per l'uso commerciale. È possibile acquistare una licenza da [Qui](https://purchase.groupdocs.com/buy).
### Dove posso ottenere supporto per GroupDocs.Viewer per .NET?
Puoi ottenere supporto dal forum GroupDocs.Viewer [Qui](https://forum.groupdocs.com/c/viewer/9).