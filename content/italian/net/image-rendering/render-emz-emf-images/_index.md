---
title: Rendering di immagini EMZ e EMF
linktitle: Rendering di immagini EMZ e EMF
second_title: API GroupDocs.Viewer .NET
description: Scopri come eseguire il rendering di immagini EMZ ed EMF in vari formati utilizzando GroupDocs.Viewer per .NET. Tutorial facile da seguire per gli sviluppatori.
type: docs
weight: 14
url: /it/net/image-rendering/render-emz-emf-images/
---
## introduzione

GroupDocs.Viewer per .NET è una potente API per il rendering di documenti che consente agli sviluppatori di visualizzare vari tipi di documenti, tra cui immagini EMZ (Enhanced Windows Metafile) ed EMF (Enhanced Metafile), nelle loro applicazioni .NET. In questo tutorial esploreremo come eseguire il rendering di immagini EMZ ed EMF in diversi formati come HTML, JPG, PNG e PDF utilizzando GroupDocs.Viewer per .NET.

## Prerequisiti

Prima di iniziare, assicurati di avere i seguenti prerequisiti:

1.  GroupDocs.Viewer per .NET: è possibile scaricare la libreria da[Qui](https://releases.groupdocs.com/viewer/net/).
2. Ambiente di sviluppo: assicurati di disporre di un ambiente di sviluppo compatibile configurato per lo sviluppo .NET.
3. Immagini EMZ/EMF campione: avere a disposizione immagini EMZ ed EMF campione per il rendering.

## Importa spazi dei nomi

Prima di immergerci nel codice, importiamo gli spazi dei nomi necessari:

```csharp
using GroupDocs.Viewer.Options;
using System;
using System.IO;
```

Ora suddividiamo ciascun esempio in più passaggi in un formato di guida passo passo:

## Rendering di immagini EMZ/EMF in HTML

### Passaggio 1: imposta la directory di output:
```csharp
string outputDirectory = "Your Document Directory";
```
 Sostituire`"Your Document Directory"`con il percorso in cui desideri salvare il file HTML renderizzato.

### Passaggio 2: definire il formato del percorso del file di paging:
```csharp
string pageFilePathFormat = Path.Combine(outputDirectory, "emz_result.html");
```
Ciò specificherà il formato del percorso del file per il file HTML sottoposto a rendering.

### Passaggio 3: rendering in HTML:
```csharp
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_EMZ))
{
    HtmlViewOptions options = HtmlViewOptions.ForEmbeddedResources(pageFilePathFormat);
    
    viewer.View(options);
}
```
 Questo codice inizializza il file`Viewer` oggetto con l'immagine EMZ di esempio e ne esegue il rendering in formato HTML utilizzando le opzioni specificate.

## Rendering di immagini EMZ/EMF in JPG, PNG e PDF

Ripetere i seguenti passaggi per il rendering nei formati JPG, PNG e PDF:

### Passaggio 1: definire il formato del percorso del file di paging:
```csharp
pageFilePathFormat = Path.Combine(outputDirectory, "emz_result.jpg");
```
Modificare il nome e l'estensione del file in base al formato di output desiderato (`jpg`, `png` , O`pdf`).

### Passaggio 2: rendering nel rispettivo formato:
```csharp
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_EMZ))
{
    // Regola le opzioni in base al formato di output (Jpg, Png, Pdf)
    JpgViewOptions options = new JpgViewOptions(pageFilePathFormat);
    
    viewer.View(options);
}
```
 Sostituire`JpgViewOptions` con`PngViewOptions` O`PdfViewOptions` in base al formato di output desiderato.

## Conclusione

In conclusione, GroupDocs.Viewer per .NET fornisce una soluzione perfetta per il rendering di immagini EMZ ed EMF in vari formati nelle applicazioni .NET. Seguendo i passaggi descritti in questo tutorial, gli sviluppatori possono integrare facilmente le funzionalità di rendering dei documenti nelle loro applicazioni.

## Domande frequenti

### D: GroupDocs.Viewer può eseguire il rendering di altri formati di documenti oltre alle immagini EMZ ed EMF?
R: Sì, GroupDocs.Viewer supporta un'ampia gamma di formati di documenti tra cui PDF, DOCX, PPTX, XLSX e altri.

### D: È disponibile una prova gratuita per GroupDocs.Viewer per .NET?
 R: Sì, puoi accedere alla prova gratuita[Qui](https://releases.groupdocs.com/).

### D: GroupDocs.Viewer offre supporto agli sviluppatori?
 R: Sì, GroupDocs fornisce supporto tramite il suo[Forum](https://forum.groupdocs.com/c/viewer/9) dove gli sviluppatori possono porre domande e chiedere assistenza.

### D: Posso acquistare una licenza temporanea per GroupDocs.Viewer per .NET?
 R: Sì, è possibile acquistare licenze temporanee[Qui](https://purchase.groupdocs.com/temporary-license/).

### D: Dove posso trovare la documentazione dettagliata per GroupDocs.Viewer per .NET?
 R: Puoi fare riferimento alla documentazione[Qui](https://reference.groupdocs.com/viewer/net/)per una guida completa sull'utilizzo dell'API.