---
"description": "Scopri come eseguire il rendering di immagini EMZ ed EMF in vari formati utilizzando GroupDocs.Viewer per .NET. Tutorial semplice da seguire per sviluppatori."
"linktitle": "Rendering di immagini EMZ ed EMF"
"second_title": "API .NET di GroupDocs.Viewer"
"title": "Rendering di immagini EMZ ed EMF"
"url": "/it/net/image-rendering/render-emz-emf-images/"
"weight": 14
type: docs
---
# Rendering di immagini EMZ ed EMF

## Introduzione

GroupDocs.Viewer per .NET è una potente API per il rendering di documenti che consente agli sviluppatori di visualizzare vari tipi di documenti, tra cui immagini EMZ (Enhanced Windows Metafile) ed EMF (Enhanced Metafile), nelle loro applicazioni .NET. In questo tutorial, esploreremo come eseguire il rendering di immagini EMZ ed EMF in diversi formati come HTML, JPG, PNG e PDF utilizzando GroupDocs.Viewer per .NET.

![Rendering di immagini EMZ ed EMF con GroupDocs.Viewer per .NET](/viewer/image-rendering/render-emz-and-emf-images.png)

## Prerequisiti

Prima di iniziare, assicurati di avere i seguenti prerequisiti:

1. GroupDocs.Viewer per .NET: puoi scaricare la libreria da [Qui](https://releases.groupdocs.com/viewer/net/).
2. Ambiente di sviluppo: assicurati di avere impostato un ambiente di sviluppo compatibile per lo sviluppo .NET.
3. Immagini campione EMZ/EMF: avere a disposizione immagini campione EMZ ed EMF per il rendering.

## Importa spazi dei nomi

Prima di immergerci nel codice, importiamo gli spazi dei nomi necessari:

```csharp
using GroupDocs.Viewer.Options;
using System;
using System.IO;
```

Ora, scomponiamo ogni esempio in più passaggi in un formato guida passo passo:

## Rendering di immagini EMZ/EMF in HTML

### Passaggio 1: impostare la directory di output:
```csharp
string outputDirectory = "Your Document Directory";
```
Sostituire `"Your Document Directory"` con il percorso in cui si desidera salvare il file HTML renderizzato.

### Passaggio 2: definire il formato del percorso del file di paging:
```csharp
string pageFilePathFormat = Path.Combine(outputDirectory, "emz_result.html");
```
In questo modo verrà specificato il formato del percorso del file HTML renderizzato.

### Passaggio 3: rendering in HTML:
```csharp
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_EMZ))
{
    HtmlViewOptions options = HtmlViewOptions.ForEmbeddedResources(pageFilePathFormat);
    
    viewer.View(options);
}
```
Questo codice inizializza il `Viewer` oggetto con l'immagine EMZ di esempio e lo trasforma in formato HTML utilizzando le opzioni specificate.

## Rendering di immagini EMZ/EMF in JPG, PNG e PDF

Ripetere i seguenti passaggi per il rendering nei formati JPG, PNG e PDF:

### Passaggio 1: definire il formato del percorso del file di paging:
```csharp
pageFilePathFormat = Path.Combine(outputDirectory, "emz_result.jpg");
```
Regola il nome e l'estensione del file in base al formato di output desiderato (`jpg`, `png`, O `pdf`).

### Fase 2: Rendering nel formato rispettivo:
```csharp
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_EMZ))
{
    // Regola le opzioni in base al formato di output (JPG, PNG, PDF)
    JpgViewOptions options = new JpgViewOptions(pageFilePathFormat);
    
    viewer.View(options);
}
```
Sostituire `JpgViewOptions` con `PngViewOptions` O `PdfViewOptions` in base al formato di output desiderato.

## Conclusione

In conclusione, GroupDocs.Viewer per .NET offre una soluzione completa per il rendering di immagini EMZ ed EMF in vari formati nelle applicazioni .NET. Seguendo i passaggi descritti in questo tutorial, gli sviluppatori possono integrare senza problemi le funzionalità di rendering dei documenti nelle loro applicazioni.

## Domande frequenti

### D: GroupDocs.Viewer può riprodurre altri formati di documenti oltre alle immagini EMZ ed EMF?
R: Sì, GroupDocs.Viewer supporta un'ampia gamma di formati di documenti, tra cui PDF, DOCX, PPTX, XLSX e altri.

### D: È disponibile una versione di prova gratuita di GroupDocs.Viewer per .NET?
A: Sì, puoi accedere alla prova gratuita [Qui](https://releases.groupdocs.com/).

### D: GroupDocs.Viewer offre supporto agli sviluppatori?
A: Sì, GroupDocs fornisce supporto tramite il suo [foro](https://forum.groupdocs.com/c/viewer/9) dove gli sviluppatori possono porre domande e chiedere assistenza.

### D: Posso acquistare una licenza temporanea per GroupDocs.Viewer per .NET?
A: Sì, le licenze temporanee sono disponibili per l'acquisto [Qui](https://purchase.groupdocs.com/temporary-license/).

### D: Dove posso trovare la documentazione dettagliata per GroupDocs.Viewer per .NET?
A: Puoi fare riferimento alla documentazione [Qui](https://tutorials.groupdocs.com/viewer/net/) per una guida completa sull'utilizzo dell'API.