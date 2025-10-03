---
"description": "Scopri come visualizzare le figure di Visio utilizzando GroupDocs.Viewer per .NET con questa guida completa. Migliora le funzionalità di visualizzazione dei documenti nelle tue applicazioni .NET."
"linktitle": "Rendering di figure Visio"
"second_title": "API .NET di GroupDocs.Viewer"
"title": "Rendering di figure Visio"
"url": "/it/net/rendering-visio-documents/render-visio-figures/"
"weight": 10
type: docs
---
# Rendering di figure Visio

## Introduzione
Nell'era digitale odierna, il rendering dei documenti gioca un ruolo cruciale in diverse applicazioni. Che si tratti di visualizzare documenti su un sito web o di convertirli in diversi formati, un rendering efficiente è essenziale. GroupDocs.Viewer per .NET offre una soluzione affidabile per la visualizzazione e la manipolazione di documenti all'interno di applicazioni .NET. In questo tutorial, approfondiremo il rendering di figure Visio utilizzando GroupDocs.Viewer per .NET, suddividendo il processo in semplici passaggi.
## Prerequisiti
Prima di immergerti nel tutorial, assicurati di avere i seguenti prerequisiti:
1. Configurazione dell'ambiente: assicurati di disporre di un ambiente funzionante per lo sviluppo .NET.
2. GroupDocs.Viewer per .NET: Scarica e installa GroupDocs.Viewer per .NET da [collegamento per il download](https://releases.groupdocs.com/viewer/net/).
3. Nozioni di base di C#: familiarizzare con i fondamenti del linguaggio di programmazione C#.
4. Esempio di documento Visio: tieni pronto un esempio di documento Visio per il rendering.

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
- Directory di output: definisce la directory in cui verrà salvato il codice HTML renderizzato.
- Formato percorso file di paging: specifica il formato del percorso per la pagina HTML.
- Inizializzazione Viewer: inizializza l'oggetto Viewer con il percorso al documento Visio.
- Opzioni di visualizzazione HTML: configura le opzioni per il rendering HTML.
- Opzioni di rendering di Visio: imposta le opzioni specifiche per il rendering di Visio, ad esempio il rendering solo delle figure e della larghezza delle figure.
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
- Simile al rendering in HTML, configura le opzioni per il rendering in formato JPG.
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
- La configurazione per il rendering nel formato PNG segue uno schema simile al rendering JPG.
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
- Per il rendering in PDF, configurare le opzioni specifiche del formato PDF.

## Conclusione
In questo tutorial abbiamo illustrato come eseguire il rendering di figure Visio utilizzando GroupDocs.Viewer per .NET. Seguendo la guida passo passo, è possibile integrare perfettamente le funzionalità di rendering dei documenti nelle applicazioni .NET, migliorando l'esperienza utente e la produttività.
## Domande frequenti
### Posso personalizzare le opzioni di rendering per le figure di Visio?
Sì, GroupDocs.Viewer per .NET offre ampie opzioni per la personalizzazione del rendering, tra cui la larghezza delle figure, il rendering solo delle figure e altro ancora.
### GroupDocs.Viewer per .NET è adatto al rendering di documenti su larga scala?
Certamente, GroupDocs.Viewer per .NET è ottimizzato per gestire in modo efficiente il rendering di documenti su larga scala.
### GroupDocs.Viewer supporta altri formati di documenti oltre a Visio?
Sì, GroupDocs.Viewer supporta un'ampia gamma di formati di documenti, tra cui PDF, Microsoft Office, AutoCAD e altri.
### Posso integrare GroupDocs.Viewer nelle applicazioni web?
Sì, GroupDocs.Viewer può essere integrato perfettamente nelle applicazioni web per la visualizzazione e la manipolazione dei documenti.
### Esiste una versione di prova disponibile per testarla prima dell'acquisto?
Sì, puoi usufruire di una prova gratuita da [sito web](https://releases.groupdocs.com/) per testare le funzionalità di GroupDocs.Viewer per .NET.