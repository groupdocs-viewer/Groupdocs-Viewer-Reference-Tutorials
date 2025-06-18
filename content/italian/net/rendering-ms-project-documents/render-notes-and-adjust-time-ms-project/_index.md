---
"description": "Padroneggia il rendering dei documenti di MS Project con GroupDocs.Viewer per .NET. Crea note, modifica le unità di tempo ed esplora diversi formati di output senza sforzo."
"linktitle": "Note di rendering e regolazione delle unità di tempo (MS Project)"
"second_title": "API .NET di GroupDocs.Viewer"
"title": "Note di rendering e regolazione delle unità di tempo (MS Project)"
"url": "/it/net/rendering-ms-project-documents/render-notes-and-adjust-time-ms-project/"
"weight": 11
---

# Note di rendering e regolazione delle unità di tempo (MS Project)

## Introduzione
GroupDocs.Viewer per .NET è una potente API per il rendering di documenti che consente agli sviluppatori di visualizzare e manipolare vari formati di documento all'interno delle loro applicazioni .NET. In questo tutorial, ci concentreremo sul rendering delle note e sulla regolazione delle unità di tempo specificamente per i documenti di MS Project.
## Prerequisiti
Prima di iniziare, assicurati di avere i seguenti prerequisiti:
1. GroupDocs.Viewer per .NET: assicurati di aver scaricato e installato la libreria GroupDocs.Viewer per .NET. Puoi scaricarla da [Qui](https://releases.groupdocs.com/viewer/net/).
2. Ambiente di sviluppo: configura il tuo ambiente di sviluppo preferito con supporto .NET.
3. Documento MS Project: tieni pronto un documento MS Project di esempio da testare.
## Importa spazi dei nomi
Per prima cosa, importiamo gli spazi dei nomi necessari per iniziare a eseguire il rendering dei documenti MS Project:
## Passaggio 1: importare gli spazi dei nomi
```csharp
using GroupDocs.Viewer.Options;
using System;
using System.IO;
```
Ora che abbiamo importato gli spazi dei nomi richiesti, scomponiamo ogni esempio in più passaggi per una comprensione più completa.
## Rendering del documento MS Project in HTML
Per convertire un documento MS Project in formato HTML con note incluse, seguire questi passaggi:
### Passaggio 2: impostare la directory di output e il formato del file
```csharp
string outputDirectory = "Your Document Directory";
string pageFilePathFormat = Path.Combine(outputDirectory, "mpp_result.html");
```
### Passaggio 3: inizializzare l'oggetto Viewer e impostare le opzioni
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
È anche possibile convertire i documenti di MS Project in formati immagine come JPG e PNG. Ecco come:
### Passaggio 5: imposta la directory di output e il formato file per JPG
```csharp
pageFilePathFormat = Path.Combine(outputDirectory, "mpp_{0}_result.jpg");
```
### Passaggio 6: inizializzare l'oggetto Viewer e impostare le opzioni JPG
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
Ripetere passaggi simili per il rendering in PNG e altri formati immagine.
## Rendering di un documento MS Project in PDF
Per convertire un documento MS Project in formato PDF, procedere come segue:
### Passaggio 8: impostare la directory di output e il formato file per PDF
```csharp
pageFilePathFormat = Path.Combine(outputDirectory, "mpp_result.pdf");
```
### Passaggio 9: inizializzare l'oggetto Viewer e impostare le opzioni PDF
```csharp
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_MPP))
{
    PdfViewOptions options = new PdfViewOptions(pageFilePathFormat);
    options.RenderNotes = true;
```
### Passaggio 10: Trasforma il documento in PDF
```csharp
viewer.View(options);
```

## Conclusione
Congratulazioni! Hai imparato con successo come visualizzare i documenti di MS Project e modificare le unità di tempo utilizzando GroupDocs.Viewer per .NET. Integra queste conoscenze nei tuoi progetti per migliorare le funzionalità di visualizzazione dei documenti.
## Domande frequenti
### Posso convertire i documenti MS Project in formati diversi da HTML, immagini e PDF?
Sì, GroupDocs.Viewer per .NET supporta il rendering in vari formati, quali DOCX, XLSX, PPTX e altri.
### Esiste una versione di prova disponibile per GroupDocs.Viewer per .NET?
Sì, puoi ottenere una prova gratuita da [Qui](https://releases.groupdocs.com/).
### Come posso ottenere una licenza temporanea per GroupDocs.Viewer per .NET?
Visita [questo collegamento](https://purchase.groupdocs.com/temporary-license/) per ottenere una licenza temporanea.
### Dove posso trovare la documentazione per GroupDocs.Viewer per .NET?
Fare riferimento alla documentazione [Qui](https://tutorials.groupdocs.com/viewer/net/).
### Dove posso cercare supporto o porre domande relative a GroupDocs.Viewer per .NET?
Puoi visitare il forum di supporto [Qui](https://forum.groupdocs.com/c/viewer/9).