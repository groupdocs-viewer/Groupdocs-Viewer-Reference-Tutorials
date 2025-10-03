---
"description": "Scopri come estrarre le informazioni di visualizzazione dai documenti PDF utilizzando GroupDocs.Viewer per .NET in questo tutorial completo."
"linktitle": "Ottieni informazioni di visualizzazione per il documento PDF"
"second_title": "API .NET di GroupDocs.Viewer"
"title": "Ottieni informazioni di visualizzazione per il documento PDF"
"url": "/it/net/pdf-rendering-options/get-view-info-pdf-document/"
"weight": 16
type: docs
---
# Ottieni informazioni di visualizzazione per il documento PDF

## Introduzione
GroupDocs.Viewer per .NET è un potente strumento progettato per semplificare la visualizzazione dei documenti nelle applicazioni .NET. Che si tratti di PDF, documenti Word, fogli di calcolo Excel o presentazioni PowerPoint, questa libreria semplifica il processo di rendering e interazione con diversi formati di file. In questo tutorial, ci concentreremo sullo sfruttamento delle funzionalità di GroupDocs.Viewer specificamente per l'estrazione di informazioni di visualizzazione dai documenti PDF.

![Ottieni informazioni di visualizzazione per il documento PDF con GroupDocs.Viewer .NET](/viewer/pdf-rendering-options/get-view-iInfo-for-pdf-document.png)

## Prerequisiti
Prima di immergerti nel tutorial, assicurati di avere i seguenti prerequisiti:
1. Installazione di GroupDocs.Viewer per .NET: assicurati di aver scaricato e installato la libreria GroupDocs.Viewer. Puoi scaricarla da [collegamento per il download](https://releases.groupdocs.com/viewer/net/).   
2. Conoscenza di base di C#: la familiarità con il linguaggio di programmazione C# è essenziale per comprendere e implementare gli esempi di codice forniti.
3. Accesso a un documento PDF: tieni pronto un documento PDF che utilizzerai per estrarre le informazioni di visualizzazione.

## Importa spazi dei nomi
Nel progetto C#, importa gli spazi dei nomi necessari per utilizzare le funzionalità di GroupDocs.Viewer.

```csharp
using System;
using GroupDocs.Viewer.Options;
using GroupDocs.Viewer.Results;
```


Analizziamo ora il processo di recupero delle informazioni di visualizzazione da un documento PDF utilizzando GroupDocs.Viewer per .NET.
## Passaggio 1: inizializzare l'oggetto Viewer
Creare un oggetto Viewer e fornire il percorso al documento PDF come parametro.
```csharp
using (Viewer viewer = new Viewer("path/to/your/sample.pdf"))
{
```
## Passaggio 2: definire ViewInfoOptions
Specificare le opzioni di visualizzazione, ad esempio la visualizzazione HTML, per recuperare le informazioni di visualizzazione.
```csharp
	ViewInfoOptions options = ViewInfoOptions.ForHtmlView();
```
## Passaggio 3: Ottieni informazioni sulla visualizzazione
Richiamare il metodo GetViewInfo per estrarre le informazioni di visualizzazione dal documento PDF.
```csharp
	PdfViewInfo info = viewer.GetViewInfo(options) as PdfViewInfo;
```
## Passaggio 4: Visualizzare le informazioni di output
Visualizza le informazioni di visualizzazione estratte, come tipo di documento, numero di pagine e autorizzazioni di stampa.
```csharp
	Console.WriteLine("Document type is: " + info.FileType);
	Console.WriteLine("Pages count: " + info.Pages.Count);
	Console.WriteLine("Printing allowed: " + info.PrintingAllowed);
}
```

## Conclusione
In questo tutorial, abbiamo esplorato come utilizzare GroupDocs.Viewer per .NET per estrarre informazioni di visualizzazione dai documenti PDF. Seguendo i passaggi indicati, è possibile integrare perfettamente questa funzionalità nelle applicazioni .NET, migliorando la gestione e la visualizzazione dei documenti.
## Domande frequenti
### GroupDocs.Viewer è compatibile con altri formati di file oltre al PDF?
Sì, GroupDocs.Viewer supporta un'ampia gamma di formati di documenti, tra cui Word, Excel, PowerPoint e altri.
### Posso personalizzare le opzioni di visualizzazione in base ai requisiti della mia applicazione?
Certamente, GroupDocs.Viewer offre diverse opzioni per personalizzare l'esperienza di visualizzazione in base alle tue esigenze specifiche.
### GroupDocs.Viewer è adatto sia per le applicazioni desktop che per quelle web?
Sì, GroupDocs.Viewer è versatile e può essere integrato senza problemi sia nelle applicazioni desktop che in quelle basate sul Web .NET.
### GroupDocs.Viewer fornisce supporto e assistenza se riscontro problemi durante l'implementazione?
Certamente, puoi cercare assistenza nel forum della community GroupDocs.Viewer o accedere ai servizi di supporto professionale per una rapida risoluzione di qualsiasi problema.
### Posso provare GroupDocs.Viewer prima di effettuare un acquisto?
Sì, puoi esplorare le funzionalità di GroupDocs.Viewer accedendo alla versione di prova gratuita disponibile su [sito web](https://purchase.groupdocs.com/buy).