---
title: Rendering di note e regolazione di unità di tempo (MS Project)
linktitle: Rendering di note e regolazione di unità di tempo (MS Project)
second_title: API GroupDocs.Viewer .NET
description: Masterizza il rendering dei documenti MS Project con GroupDocs.Viewer per .NET. Visualizza note, regola unità di tempo ed esplora vari formati di output senza sforzo.
weight: 11
url: /it/net/rendering-ms-project-documents/render-notes-and-adjust-time-ms-project/
---

# Rendering di note e regolazione di unità di tempo (MS Project)

## introduzione
GroupDocs.Viewer per .NET è una potente API per il rendering di documenti che consente agli sviluppatori di visualizzare e manipolare vari formati di documenti all'interno delle loro applicazioni .NET. In questo tutorial, ci concentreremo sul rendering delle note e sulla regolazione delle unità di tempo specifiche per i documenti MS Project.
## Prerequisiti
Prima di iniziare, assicurati di avere i seguenti prerequisiti:
1. GroupDocs.Viewer per .NET: assicurati di aver scaricato e installato la libreria GroupDocs.Viewer per .NET. Puoi scaricarlo da[Qui](https://releases.groupdocs.com/viewer/net/).
2. Ambiente di sviluppo: configura il tuo ambiente di sviluppo preferito con il supporto .NET.
3. Documento MS Project: tieni pronto un documento MS Project di esempio per il test.
## Importa spazi dei nomi
Innanzitutto, importiamo gli spazi dei nomi necessari per iniziare con il rendering dei documenti MS Project:
## Passaggio 1: importa gli spazi dei nomi
```csharp
using GroupDocs.Viewer.Options;
using System;
using System.IO;
```
Ora che abbiamo importato gli spazi dei nomi richiesti, suddividiamo ogni esempio in più passaggi per una comprensione completa.
## Rendering del documento MS Project in HTML
Per eseguire il rendering di un documento MS Project in formato HTML con note incluse, attenersi alla seguente procedura:
### Passaggio 2: imposta la directory di output e il formato file
```csharp
string outputDirectory = "Your Document Directory";
string pageFilePathFormat = Path.Combine(outputDirectory, "mpp_result.html");
```
### Passaggio 3: inizializzare l'oggetto visualizzatore e impostare le opzioni
```csharp
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_MPP))
{
    HtmlViewOptions options = HtmlViewOptions.ForEmbeddedResources(pageFilePathFormat);
    options.RenderNotes = true;
```
### Passaggio 4: rendering del documento in HTML
```csharp
viewer.View(options);
```
## Rendering di documenti MS Project in formati immagine
Puoi anche eseguire il rendering dei documenti MS Project in formati immagine come JPG e PNG. Ecco come:
### Passaggio 5: imposta la directory di output e il formato file per JPG
```csharp
pageFilePathFormat = Path.Combine(outputDirectory, "mpp_{0}_result.jpg");
```
### Passaggio 6: inizializza l'oggetto visualizzatore e imposta le opzioni JPG
```csharp
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_MPP))
{
    JpgViewOptions options = new JpgViewOptions(pageFilePathFormat);
    options.RenderNotes = true;
```
### Passaggio 7: rendering del documento in JPG
```csharp
viewer.View(options);
```
Ripeti passaggi simili per il rendering in PNG e altri formati di immagine.
## Rendering del documento MS Project in PDF
Per eseguire il rendering di un documento MS Project in formato PDF, procedere come segue:
### Passaggio 8: imposta la directory di output e il formato file per PDF
```csharp
pageFilePathFormat = Path.Combine(outputDirectory, "mpp_result.pdf");
```
### Passaggio 9: inizializza l'oggetto visualizzatore e imposta le opzioni PDF
```csharp
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_MPP))
{
    PdfViewOptions options = new PdfViewOptions(pageFilePathFormat);
    options.RenderNotes = true;
```
### Passaggio 10: rendering del documento in PDF
```csharp
viewer.View(options);
```

## Conclusione
Congratulazioni! Hai imparato con successo come eseguire il rendering dei documenti MS Project e regolare le unità di tempo utilizzando GroupDocs.Viewer per .NET. Incorpora queste conoscenze nei tuoi progetti per migliorare le capacità di visualizzazione dei documenti.
## Domande frequenti
### Posso eseguire il rendering dei documenti MS Project in altri formati oltre a HTML, immagini e PDF?
Sì, GroupDocs.Viewer per .NET supporta il rendering in vari formati come DOCX, XLSX, PPTX e altri.
### È disponibile una versione di prova per GroupDocs.Viewer per .NET?
 Sì, puoi ottenere una prova gratuita da[Qui](https://releases.groupdocs.com/).
### Come posso ottenere una licenza temporanea per GroupDocs.Viewer per .NET?
 Visita[questo link](https://purchase.groupdocs.com/temporary-license/) per ottenere una licenza temporanea.
### Dove posso trovare la documentazione per GroupDocs.Viewer per .NET?
 Fare riferimento alla documentazione[Qui](https://tutorials.groupdocs.com/viewer/net/).
### Dove posso chiedere supporto o porre domande relative a GroupDocs.Viewer per .NET?
 Puoi visitare il forum di supporto[Qui](https://forum.groupdocs.com/c/viewer/9).