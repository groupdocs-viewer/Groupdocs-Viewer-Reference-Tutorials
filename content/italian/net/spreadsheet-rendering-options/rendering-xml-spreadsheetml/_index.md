---
title: Rendering XML SpreadSheetML
linktitle: Rendering XML SpreadSheetML
second_title: API GroupDocs.Viewer .NET
description: Esplora il rendering senza interruzioni dei file XML SpreadSheetML in vari formati utilizzando GroupDocs.Viewer per .NET. Integra facilmente le tue applicazioni.
type: docs
weight: 16
url: /it/net/spreadsheet-rendering-options/rendering-xml-spreadsheetml/
---
## introduzione
Benvenuti nel mondo di GroupDocs.Viewer per .NET! In questo tutorial ti guideremo attraverso il rendering dei file XML SpreadSheetML con facilità utilizzando GroupDocs.Viewer, una potente libreria .NET. Che tu sia uno sviluppatore esperto o che tu abbia appena iniziato, questa guida passo passo ti aiuterà a integrare facilmente il rendering XML SpreadSheetML nelle tue applicazioni.
## Prerequisiti
Prima di immergerti nel tutorial, assicurati di aver impostato i seguenti prerequisiti:
- Un ambiente di sviluppo con supporto .NET.
-  GroupDocs.Viewer per la libreria .NET installata. Puoi scaricarlo[Qui](https://releases.groupdocs.com/viewer/net/).
- Una conoscenza di base della programmazione C#.
## Importa spazi dei nomi
Inizia importando gli spazi dei nomi necessari nel tuo progetto C#. Ciò garantisce l'accesso alle funzionalità fornite da GroupDocs.Viewer.
```csharp
using GroupDocs.Viewer.Options;
using System;
using System.IO;
```
## Passaggio 1: imposta la directory dei documenti
Definisci il percorso della directory dei documenti in cui verrà salvato l'output.
```csharp
string outputDirectory = "Your Document Directory";
```
## Passaggio 2: specificare i percorsi dei file di output
Imposta i percorsi completi per i file di output HTML, JPG, PNG e PDF.
```csharp
string pageFileFullPath = Path.Combine(outputDirectory, "Excel_2003_Xml_result.html");
```
## Passaggio 3: specificare le opzioni di caricamento
Specificare esplicitamente il tipo di file come Excel 2003 XML SpreadSheetML per visualizzarlo in modo accurato.
```csharp
LoadOptions loadOptions = new LoadOptions(FileType.Excel2003XML);
```
## Passaggio 4: rendering in HTML multipagina
Utilizza le opzioni di visualizzazione HTML per eseguire il rendering del file XML SpreadSheetML in un documento HTML multipagina.
```csharp
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_XML_SPREADSHEETML, loadOptions))
{
    HtmlViewOptions options = HtmlViewOptions.ForEmbeddedResources(pageFileFullPath);
    viewer.View(options);
}
```
## Passaggio 5: rendering in JPG
Esegui il rendering del file XML SpreadSheetML in un'immagine JPG utilizzando le opzioni specificate.
```csharp
pageFileFullPath = Path.Combine(outputDirectory, "Excel_2003_Xml_result.jpg");
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_XML_SPREADSHEETML, loadOptions))
{
    JpgViewOptions options = new JpgViewOptions(pageFileFullPath);
    viewer.View(options);
}
```
## Passaggio 6: rendering in PNG
Allo stesso modo, esegui il rendering del file in un'immagine PNG con le opzioni specificate.
```csharp
pageFileFullPath = Path.Combine(outputDirectory, "Excel_2003_Xml_result.png");
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_XML_SPREADSHEETML, loadOptions))
{
    PngViewOptions options = new PngViewOptions(pageFileFullPath);
    viewer.View(options);
}
```
## Passaggio 7: rendering in PDF
Infine, esegui il rendering del file XML SpreadSheetML in un documento PDF utilizzando le opzioni specificate.
```csharp
pageFileFullPath = Path.Combine(outputDirectory, "Excel_2003_Xml_result.pdf");
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_XML_SPREADSHEETML, loadOptions))
{
    PdfViewOptions options = new PdfViewOptions(pageFileFullPath);
    viewer.View(options);
}
```
## Conclusione
Congratulazioni! Hai imparato con successo come eseguire il rendering di file XML SpreadSheetML utilizzando GroupDocs.Viewer per .NET. Migliora le tue capacità di visualizzazione dei documenti esplorando più funzionalità e opzioni fornite da questa versatile libreria.
## Domande frequenti
### GroupDocs.Viewer è compatibile con altri formati di file?
Sì, GroupDocs.Viewer supporta un'ampia gamma di formati di documenti, inclusi PDF, Word, Excel e altri.
### Posso personalizzare l'aspetto dei documenti renderizzati?
Assolutamente! GroupDocs.Viewer offre varie opzioni di personalizzazione, consentendoti di adattare l'output alle tue esigenze specifiche.
### Dove posso trovare ulteriore supporto e risorse?
 Visitare il[Forum GroupDocs.Viewer](https://forum.groupdocs.com/c/viewer/9) per il supporto della comunità ed esplorare il[documentazione](https://reference.groupdocs.com/viewer/net/)per informazioni dettagliate.
### È disponibile una prova gratuita?
 Sì, puoi accedere alla prova gratuita[Qui](https://releases.groupdocs.com/).
### Come posso ottenere una licenza temporanea?
 Puoi ottenere una licenza temporanea[Qui](https://purchase.groupdocs.com/temporary-license/).