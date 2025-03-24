---
title: Rendering di figure di Visio
linktitle: Rendering di figure di Visio
second_title: API GroupDocs.Viewer .NET
description: Scopri come eseguire il rendering delle figure di Visio utilizzando GroupDocs.Viewer per .NET con questo programma completo. Migliora le funzionalità di visualizzazione dei documenti nelle tue applicazioni .NET.
weight: 10
url: /it/net/rendering-visio-documents/render-visio-figures/
---
## introduzione
Nell'era digitale di oggi, il rendering dei documenti gioca un ruolo cruciale in varie applicazioni. Che si tratti di visualizzare documenti su un sito Web o di convertirli in diversi formati, un rendering efficiente è essenziale. GroupDocs.Viewer per .NET fornisce una soluzione solida per visualizzare e manipolare documenti all'interno delle applicazioni .NET. In questo tutorial approfondiremo il rendering delle figure di Visio utilizzando GroupDocs.Viewer per .NET, suddividendo il processo in semplici passaggi.
## Prerequisiti
Prima di immergerti nel tutorial, assicurati di possedere i seguenti prerequisiti:
1. Configurazione dell'ambiente: assicurati di disporre di un ambiente di lavoro per lo sviluppo .NET.
2.  GroupDocs.Viewer per .NET: scaricare e installare GroupDocs.Viewer per .NET dal[Link per scaricare](https://releases.groupdocs.com/viewer/net/).
3. Comprensione di base di C#: acquisisci familiarità con i fondamenti del linguaggio di programmazione C#.
4. Documento Visio di esempio: disporre di un documento Visio di esempio pronto per il rendering.

## Importa spazi dei nomi
Nel tuo progetto C#, inizia importando gli spazi dei nomi necessari:
```csharp
using GroupDocs.Viewer.Options;
using System;
using System.IO;
```
## 1. Rendering in HTML
```csharp
string outputDirectory = "Your Document Directory";
string pageFilePathFormat = Path.Combine(outputDirectory, "result_page.html");
using (Viewer viewer = new Viewer("YourVisioDocumentPath"))
{
    HtmlViewOptions options = HtmlViewOptions.ForEmbeddedResources(pageFilePathFormat);
    options.VisioRenderingOptions.RenderFiguresOnly = true;
    options.VisioRenderingOptions.FigureWidth = 250;
    viewer.View(options);
}
```
- Directory di output: definire la directory in cui verrà salvato l'HTML renderizzato.
- Formato percorso file di pagina: specificare il formato del percorso per la pagina HTML.
- Inizializzazione visualizzatore: inizializza l'oggetto Visualizzatore con il percorso del documento Visio.
- Opzioni di visualizzazione HTML: configura le opzioni per il rendering dell'HTML.
- Opzioni di rendering di Visio: imposta opzioni specifiche per il rendering di Visio, ad esempio il rendering delle sole figure e la larghezza della figura.
## 2. Rendering in JPG
```csharp
string pageFilePathFormat = Path.Combine(outputDirectory, "visio_result.jpg");
using (Viewer viewer = new Viewer("YourVisioDocumentPath"))
{
    JpgViewOptions options = new JpgViewOptions(pageFilePathFormat);
    options.VisioRenderingOptions.RenderFiguresOnly = true;
    options.VisioRenderingOptions.FigureWidth = 250;
    viewer.View(options);
}
```
- Similmente al rendering in HTML, configura le opzioni per il rendering in formato JPG.
## 3. Rendering in PNG
```csharp
string pageFilePathFormat = Path.Combine(outputDirectory, "visio_result.png");
using (Viewer viewer = new Viewer("YourVisioDocumentPath"))
{
    PngViewOptions options = new PngViewOptions(pageFilePathFormat);
    options.VisioRenderingOptions.RenderFiguresOnly = true;
    options.VisioRenderingOptions.FigureWidth = 250;
    viewer.View(options);
}
```
- La configurazione per il rendering in formato PNG segue uno schema simile al rendering JPG.
## 4. Rendering in PDF
```csharp
string pageFilePathFormat = Path.Combine(outputDirectory, "visio_result.pdf");
using (Viewer viewer = new Viewer("YourVisioDocumentPath"))
{
    PdfViewOptions options = new PdfViewOptions(pageFilePathFormat);
    options.VisioRenderingOptions.RenderFiguresOnly = true;
    options.VisioRenderingOptions.FigureWidth = 250;
    viewer.View(options);
}
```
- Per il rendering in PDF, configurare le opzioni specifiche per il formato PDF.

## Conclusione
In questa esercitazione è stato esplorato come eseguire il rendering delle figure di Visio utilizzando GroupDocs.Viewer per .NET. Seguendo la guida passo passo, puoi integrare perfettamente le funzionalità di rendering dei documenti nelle tue applicazioni .NET, migliorando l'esperienza utente e la produttività.
## Domande frequenti
### Posso personalizzare le opzioni di rendering per le figure di Visio?
Sì, GroupDocs.Viewer per .NET fornisce ampie opzioni per personalizzare il rendering, inclusa la larghezza della figura, il rendering delle sole figure e altro ancora.
### GroupDocs.Viewer per .NET è adatto per il rendering di documenti su larga scala?
Assolutamente, GroupDocs.Viewer per .NET è ottimizzato per gestire in modo efficiente il rendering di documenti su larga scala.
### GroupDocs.Viewer supporta altri formati di documenti oltre a Visio?
Sì, GroupDocs.Viewer supporta un'ampia gamma di formati di documenti, tra cui PDF, Microsoft Office, AutoCAD e altri.
### Posso integrare GroupDocs.Viewer nelle applicazioni web?
Sì, GroupDocs.Viewer può essere perfettamente integrato nelle applicazioni Web per la visualizzazione e la manipolazione di documenti.
### È disponibile una versione di prova da provare prima dell'acquisto?
Sì, puoi usufruire di una prova gratuita da[sito web](https://releases.groupdocs.com/) per testare le funzionalità di GroupDocs.Viewer per .NET.