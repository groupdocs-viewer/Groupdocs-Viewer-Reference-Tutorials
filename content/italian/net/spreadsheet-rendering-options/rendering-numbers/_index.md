---
"description": "Esplora la potenza di Groupdocs.Viewer per .NET nel rendering impeccabile dei file Numbers. Convertili in HTML, JPG, PNG e PDF senza sforzo."
"linktitle": "Numeri di rendering"
"second_title": "API .NET di GroupDocs.Viewer"
"title": "Numeri di rendering"
"url": "/it/net/spreadsheet-rendering-options/rendering-numbers/"
"weight": 15
type: docs
---
# Numeri di rendering

## Introduzione
Benvenuti a questo tutorial passo passo sul rendering di file Numbers utilizzando Groupdocs.Viewer per .NET. Che siate sviluppatori esperti o principianti, questa guida vi guiderà attraverso il processo di conversione di documenti Numbers in vari formati. Groupdocs.Viewer per .NET è un potente strumento che vi consente di integrare perfettamente le funzionalità di visualizzazione dei documenti nelle vostre applicazioni .NET.
## Prerequisiti
Prima di immergerti nel tutorial, assicurati di avere i seguenti prerequisiti:
- Conoscenza pratica dello sviluppo C# e .NET.
- Libreria Groupdocs.Viewer per .NET installata. Puoi scaricarla. [Qui](https://releases.groupdocs.com/viewer/net/).
- Percorso della directory dei documenti in cui verranno salvati i file di output.
## Importa spazi dei nomi
Nel tuo progetto C#, assicurati di importare gli spazi dei nomi necessari per utilizzare la libreria Groupdocs.Viewer:
```csharp
using System;
using System.Collections.Generic;
using System.Text;
using System.IO;
using GroupDocs.Viewer.Options;
```
## Passaggio 1: impostare la directory di output
Prima di iniziare il rendering, definisci la directory di output in cui verranno salvati i file convertiti. Sostituisci "Directory Documenti" con il percorso effettivo:
```csharp
string outputDirectory = "Your Document Directory";
```
## Passaggio 2: rendering in HTML multipagina
Utilizzare il seguente codice per convertire il file Numbers in HTML multipagina:
```csharp
string pageFileFullPath = Path.Combine(outputDirectory, "Numbers_result.html");
using (Viewer viewer = new Viewer("SAMPLE.NUMBERS"))
{
    HtmlViewOptions options = HtmlViewOptions.ForEmbeddedResources(pageFileFullPath);
    viewer.View(options);
}
```
## Passaggio 3: rendering in JPG
Converti il file Numbers in formato JPG con il seguente codice:
```csharp
pageFileFullPath = Path.Combine(outputDirectory, "Numbers_result.jpg");
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_NUMBERS))
{
    JpgViewOptions options = new JpgViewOptions(pageFileFullPath);
    viewer.View(options);
}
```
## Passaggio 4: rendering in PNG
Trasforma il file Numbers in formato PNG utilizzando il seguente codice:
```csharp
pageFileFullPath = Path.Combine(outputDirectory, "Numbers_result.png");
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_NUMBERS))
{
    PngViewOptions options = new PngViewOptions(pageFileFullPath);
    viewer.View(options);
}
```
## Passaggio 5: rendering in PDF
Infine, converti il file Numbers in formato PDF utilizzando il seguente codice:
```csharp
pageFileFullPath = Path.Combine(outputDirectory, "Numbers_result.pdf");
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_NUMBERS))
{
    PdfViewOptions options = new PdfViewOptions(pageFileFullPath);
    viewer.View(options);
}
```
Congratulazioni! Hai elaborato con successo i file Numbers in vari formati utilizzando Groupdocs.Viewer per .NET.
## Conclusione
In questo tutorial abbiamo trattato le basi del rendering di file Numbers utilizzando Groupdocs.Viewer per .NET. Questa potente libreria offre un'integrazione perfetta per la visualizzazione e la conversione di documenti nelle applicazioni .NET.
## Domande frequenti
### Posso utilizzare Groupdocs.Viewer per .NET con altri tipi di documenti?
Sì, Groupdocs.Viewer supporta un'ampia gamma di formati di documenti, tra cui Word, Excel, PDF e altri.
### È disponibile una licenza temporanea per scopi di prova?
Sì, puoi ottenere una licenza temporanea [Qui](https://purchase.groupdocs.com/temporary-license/) per effettuare i test.
### Dove posso trovare supporto per Groupdocs.Viewer per .NET?
Visita il [Forum di Groupdocs.Viewer](https://forum.groupdocs.com/c/viewer/9) per assistenza e discussioni.
### Come posso acquistare la versione completa di Groupdocs.Viewer per .NET?
Puoi acquistare la versione completa [Qui](https://purchase.groupdocs.com/buy).
### È disponibile una versione di prova gratuita?
Sì, puoi esplorare la versione di prova gratuita [Qui](https://releases.groupdocs.com/).