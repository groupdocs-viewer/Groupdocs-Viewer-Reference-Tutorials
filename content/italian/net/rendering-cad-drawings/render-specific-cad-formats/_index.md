---
"description": "Scopri come convertire formati CAD specifici come CF2 in HTML, JPG, PNG e PDF utilizzando Groupdocs.Viewer per .NET."
"linktitle": "Formati CAD specifici per il rendering (CF2)"
"second_title": "API .NET di GroupDocs.Viewer"
"title": "Formati CAD specifici per il rendering (CF2)"
"url": "/it/net/rendering-cad-drawings/render-specific-cad-formats/"
"weight": 12
---

# Formati CAD specifici per il rendering (CF2)

## Introduzione
In questo tutorial, esploreremo come eseguire il rendering di specifici formati CAD utilizzando Groupdocs.Viewer per .NET. Groupdocs.Viewer è una potente API per la visualizzazione di documenti che consente agli sviluppatori di visualizzare oltre 170 tipi di documenti nelle loro applicazioni senza richiedere l'installazione di software esterni. Nello specifico, ci concentreremo sul rendering di formati CAD come CF2 in vari formati di output come HTML, JPG, PNG e PDF.
## Prerequisiti
Prima di immergerci nel tutorial, assicurati di avere i seguenti prerequisiti:
- Visual Studio installato sul sistema.
- Groupdocs.Viewer per .NET SDK. Puoi scaricarlo da [Qui](https://releases.groupdocs.com/viewer/net/).
- Conoscenza di base del linguaggio di programmazione C#.
## Importa spazi dei nomi
Per prima cosa importiamo gli spazi dei nomi necessari per il rendering dei formati CAD.
```csharp
using GroupDocs.Viewer.Options;
using System;
using System.IO;
```
Ora, scomponiamo ogni esempio in più passaggi:
## Renderizza CF2 in HTML
### Passaggio 1: definire la directory di output in cui verrà salvato il codice HTML renderizzato.
```csharp
string outputDirectory = "Your Document Directory";
```
### Passaggio 2: definire il formato del percorso del file per l'output HTML.
```csharp
string pageFilePathFormat = Path.Combine(outputDirectory, "CF2_result.html");
```
### Passaggio 3: inizializzare l'oggetto Viewer e specificare il file CF2 di input.
```csharp
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_CF2))
{
    HtmlViewOptions options = HtmlViewOptions.ForEmbeddedResources(pageFilePathFormat);
    // Imposta opzioni di rendering aggiuntive se necessario
    // opzioni.CadOptions = CadOptions.ForRenderingByScaleFactor(0.7f);
    viewer.View(options);
}
```
## Rendi CF2 in JPG
### Passaggio 1: definire il formato del percorso del file per l'output JPG.
```csharp
pageFilePathFormat = Path.Combine(outputDirectory, "CF2_result.jpg");
```
### Passaggio 2: inizializzare l'oggetto Viewer e specificare il file CF2 di input.
```csharp
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_CF2))
{
    JpgViewOptions options = new JpgViewOptions(pageFilePathFormat);
    // Imposta opzioni di rendering aggiuntive se necessario
    // opzioni.CadOptions = CadOptions.ForRenderingByScaleFactor(0.7f);
    viewer.View(options);
}
```
## Rendi CF2 in PNG

### Passaggio 1: definire il formato del percorso del file per l'output PNG.
```csharp
pageFilePathFormat = Path.Combine(outputDirectory, "CF2_result.png");
```
### Passaggio 2: inizializzare l'oggetto Viewer e specificare il file CF2 di input.
```csharp
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_CF2))
{
    PngViewOptions options = new PngViewOptions(pageFilePathFormat);
    // Imposta opzioni di rendering aggiuntive se necessario
    // opzioni.CadOptions = CadOptions.ForRenderingByScaleFactor(0.7f);
    viewer.View(options);
}
```
## Renderizza CF2 in PDF
### Passaggio 1: definire il formato del percorso del file per l'output PDF.
```csharp
pageFilePathFormat = Path.Combine(outputDirectory, "CF2_result.pdf");
```
### Passaggio 2: inizializzare l'oggetto Viewer e specificare il file CF2 di input.
```csharp
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_CF2))
{
    PdfViewOptions options = new PdfViewOptions(pageFilePathFormat);
    // Imposta opzioni di rendering aggiuntive se necessario
    // opzioni.CadOptions = CadOptions.ForRenderingByScaleFactor(0.7f);
    viewer.View(options);
}
```

## Conclusione
In questo tutorial abbiamo imparato come eseguire il rendering di formati CAD specifici, come CF2, utilizzando Groupdocs.Viewer per .NET. Seguendo la guida passo passo, potrete integrare facilmente le funzionalità di rendering dei documenti nelle vostre applicazioni .NET.
## Domande frequenti
### Groupdocs.Viewer può eseguire il rendering di altri formati CAD oltre a CF2?
Sì, Groupdocs.Viewer supporta un'ampia gamma di formati CAD, tra cui DWG, DXF, DGN e altri.
### Groupdocs.Viewer è adatto per il rendering di documenti in applicazioni web?
Certamente, Groupdocs.Viewer può essere integrato perfettamente nelle applicazioni web per visualizzare i documenti direttamente nel browser.
### Groupdocs.Viewer richiede dipendenze esterne per il rendering?
No, Groupdocs.Viewer è un'API autonoma e non richiede dipendenze esterne o installazioni di software.
### Posso personalizzare le opzioni di rendering in base alle mie esigenze?
Sì, Groupdocs.Viewer offre varie opzioni di rendering che possono essere personalizzate per soddisfare le tue esigenze specifiche.
### Esiste una versione di prova disponibile per Groupdocs.Viewer?
Sì, puoi ottenere una versione di prova gratuita di Groupdocs.Viewer da [Qui](https://releases.groupdocs.com/).