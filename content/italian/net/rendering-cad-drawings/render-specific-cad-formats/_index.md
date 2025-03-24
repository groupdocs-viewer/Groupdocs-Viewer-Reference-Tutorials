---
title: Rendering di formati CAD specifici (CF2)
linktitle: Rendering di formati CAD specifici (CF2)
second_title: API GroupDocs.Viewer .NET
description: Scopri come eseguire il rendering di formati CAD specifici come CF2 in HTML, JPG, PNG e PDF utilizzando Groupdocs.Viewer per .NET.
weight: 12
url: /it/net/rendering-cad-drawings/render-specific-cad-formats/
---

# Rendering di formati CAD specifici (CF2)

## introduzione
In questo tutorial esploreremo come eseguire il rendering di formati CAD specifici utilizzando Groupdocs.Viewer per .NET. Groupdocs.Viewer è una potente API per la visualizzazione di documenti che consente agli sviluppatori di visualizzare oltre 170 tipi di documenti nelle loro applicazioni senza richiedere installazioni di software esterno. Nello specifico, ci concentreremo sul rendering di formati CAD come CF2 in vari formati di output come HTML, JPG, PNG e PDF.
## Prerequisiti
Prima di immergerci nel tutorial, assicurati di possedere i seguenti prerequisiti:
- Visual Studio installato nel sistema.
-  Groupdocs.Viewer per .NET SDK. Puoi scaricarlo da[Qui](https://releases.groupdocs.com/viewer/net/).
- Conoscenza base del linguaggio di programmazione C#.
## Importa spazi dei nomi
Innanzitutto, importiamo gli spazi dei nomi necessari per il rendering dei formati CAD.
```csharp
using GroupDocs.Viewer.Options;
using System;
using System.IO;
```
Ora suddividiamo ciascun esempio in più passaggi:
## Rendere CF2 in HTML
### Passaggio 1: definire la directory di output in cui verrà salvato l'HTML renderizzato.
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
    // Imposta opzioni di rendering aggiuntive, se necessario
    // opzioni.CadOptions = CadOptions.ForRenderingByScaleFactor(0.7f);
    viewer.View(options);
}
```
## Renderizza CF2 in JPG
### Passaggio 1: definire il formato del percorso del file per l'output JPG.
```csharp
pageFilePathFormat = Path.Combine(outputDirectory, "CF2_result.jpg");
```
### Passaggio 2: inizializzare l'oggetto Viewer e specificare il file CF2 di input.
```csharp
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_CF2))
{
    JpgViewOptions options = new JpgViewOptions(pageFilePathFormat);
    // Imposta opzioni di rendering aggiuntive, se necessario
    // opzioni.CadOptions = CadOptions.ForRenderingByScaleFactor(0.7f);
    viewer.View(options);
}
```
## Renderizza CF2 in PNG

### Passaggio 1: definire il formato del percorso del file per l'output PNG.
```csharp
pageFilePathFormat = Path.Combine(outputDirectory, "CF2_result.png");
```
### Passaggio 2: inizializzare l'oggetto Viewer e specificare il file CF2 di input.
```csharp
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_CF2))
{
    PngViewOptions options = new PngViewOptions(pageFilePathFormat);
    // Imposta opzioni di rendering aggiuntive, se necessario
    // opzioni.CadOptions = CadOptions.ForRenderingByScaleFactor(0.7f);
    viewer.View(options);
}
```
## Trasforma CF2 in PDF
### Passaggio 1: definire il formato del percorso del file per l'output PDF.
```csharp
pageFilePathFormat = Path.Combine(outputDirectory, "CF2_result.pdf");
```
### Passaggio 2: inizializzare l'oggetto Viewer e specificare il file CF2 di input.
```csharp
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_CF2))
{
    PdfViewOptions options = new PdfViewOptions(pageFilePathFormat);
    // Imposta opzioni di rendering aggiuntive, se necessario
    // opzioni.CadOptions = CadOptions.ForRenderingByScaleFactor(0.7f);
    viewer.View(options);
}
```

## Conclusione
In questo tutorial abbiamo imparato come eseguire il rendering di formati CAD specifici come CF2 utilizzando Groupdocs.Viewer per .NET. Seguendo la guida passo passo, puoi integrare facilmente le funzionalità di rendering dei documenti nelle tue applicazioni .NET.
## Domande frequenti
### Groupdocs.Viewer può eseguire il rendering di altri formati CAD oltre a CF2?
Sì, Groupdocs.Viewer supporta un'ampia gamma di formati CAD, inclusi DWG, DXF, DGN e altri.
### Groupdocs.Viewer è adatto per il rendering di documenti in applicazioni web?
Assolutamente sì, Groupdocs.Viewer può essere perfettamente integrato nelle applicazioni web per il rendering dei documenti direttamente nel browser.
### Groupdocs.Viewer richiede dipendenze esterne per il rendering?
No, Groupdocs.Viewer è un'API autonoma e non richiede dipendenze esterne o installazioni software.
### Posso personalizzare le opzioni di rendering in base alle mie esigenze?
Sì, Groupdocs.Viewer fornisce varie opzioni di rendering che possono essere personalizzate per soddisfare le tue esigenze specifiche.
### È disponibile una versione di prova per Groupdocs.Viewer?
 Sì, puoi ottenere una versione di prova gratuita di Groupdocs.Viewer da[Qui](https://releases.groupdocs.com/).