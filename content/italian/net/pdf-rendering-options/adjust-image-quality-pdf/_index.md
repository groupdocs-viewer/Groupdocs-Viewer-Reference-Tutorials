---
title: Regola la qualità dell'immagine nel PDF
linktitle: Regola la qualità dell'immagine nel PDF
second_title: API GroupDocs.Viewer .NET
description: Scopri come regolare la qualità dell'immagine nei documenti PDF utilizzando GroupDocs.Viewer per .NET. Segui il nostro tutorial passo passo per un'integrazione perfetta.
weight: 10
url: /it/net/pdf-rendering-options/adjust-image-quality-pdf/
---
## introduzione
GroupDocs.Viewer per .NET è una potente libreria che consente agli sviluppatori di integrare facilmente funzionalità di rendering dei documenti nelle proprie applicazioni .NET. Una delle caratteristiche principali di questa libreria è la capacità di regolare la qualità dell'immagine durante il rendering di documenti PDF. In questo tutorial ti guideremo attraverso il processo di regolazione della qualità dell'immagine passo dopo passo utilizzando GroupDocs.Viewer per .NET.
## Prerequisiti
Prima di iniziare, assicurati di possedere i seguenti prerequisiti:
1. Conoscenza base della programmazione C#.
2. Visual Studio installato nel sistema.
3. Libreria GroupDocs.Viewer per .NET scaricata e installata. Puoi scaricarlo da[Qui](https://releases.groupdocs.com/viewer/net/).

## Importa spazi dei nomi
Innanzitutto, devi importare gli spazi dei nomi necessari per lavorare con GroupDocs.Viewer per .NET:
```csharp
using System;
using System.IO;
using GroupDocs.Viewer.Options;
```
## Passaggio 1: definire la directory di output
```csharp
string outputDirectory = "Your Document Directory";
```
 Sostituire`"Your Document Directory"` con il percorso in cui desideri salvare le pagine HTML renderizzate.
## Passaggio 2: definire il formato del percorso del file di paging
```csharp
string pageFilePathFormat = Path.Combine(outputDirectory, "page_{0}.html");
```
 Questa riga definisce il formato per il percorso del file di ciascuna pagina HTML renderizzata.`{0}` è un segnaposto per il numero di pagina.
## Passaggio 3: regola la qualità dell'immagine
```csharp
using (Viewer viewer = new Viewer("Your PDF File Path"))
{
    HtmlViewOptions options = HtmlViewOptions.ForEmbeddedResources(pageFilePathFormat);
    options.PdfOptions.ImageQuality = ImageQuality.Medium;
    viewer.View(options);
}
```
 Sostituire`"Your PDF File Path"` con il percorso del documento PDF.
## Passaggio 4: Visualizza il percorso di output
```csharp
Console.WriteLine($"\nSource document rendered successfully.\nCheck output in {outputDirectory}.");
```
Questa riga visualizza il percorso in cui vengono salvate le pagine HTML renderizzate.

## Conclusione
In questo tutorial, abbiamo imparato come regolare la qualità dell'immagine durante il rendering di documenti PDF utilizzando GroupDocs.Viewer per .NET. Seguendo i semplici passaggi sopra descritti, puoi personalizzare facilmente la qualità dell'immagine in base alle tue esigenze.
## Domande frequenti
### Posso regolare la qualità dell'immagine per altri formati di documento oltre al PDF?
Sì, GroupDocs.Viewer per .NET supporta vari formati di documenti e puoi regolare la qualità dell'immagine per la maggior parte di essi.
### Quali sono le opzioni di qualità dell'immagine disponibili?
GroupDocs.Viewer per .NET fornisce opzioni per la qualità dell'immagine Bassa, Media e Alta.
### C'è un modo per visualizzare in anteprima il documento prima di eseguirne il rendering con la qualità dell'immagine modificata?
Sì, puoi utilizzare GroupDocs.Viewer for .NET per generare anteprime di documenti con diverse impostazioni di qualità dell'immagine.
### GroupDocs.Viewer per .NET richiede una licenza per uso commerciale?
 Sì, è necessario ottenere una licenza per uso commerciale. È possibile acquistare una licenza da[Qui](https://purchase.groupdocs.com/buy).
### Dove posso ottenere supporto per GroupDocs.Viewer per .NET?
 Puoi ottenere supporto dal forum GroupDocs.Viewer[Qui](https://forum.groupdocs.com/c/viewer/9).