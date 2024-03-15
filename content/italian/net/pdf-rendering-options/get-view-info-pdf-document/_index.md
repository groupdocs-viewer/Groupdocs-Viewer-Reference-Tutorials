---
title: Ottieni informazioni sulla visualizzazione per il documento PDF
linktitle: Ottieni informazioni sulla visualizzazione per il documento PDF
second_title: API GroupDocs.Viewer .NET
description: Scopri come estrarre informazioni sulla visualizzazione da documenti PDF utilizzando GroupDocs.Viewer per .NET in questo tutorial completo.
type: docs
weight: 16
url: /it/net/pdf-rendering-options/get-view-info-pdf-document/
---
## introduzione
GroupDocs.Viewer per .NET è un potente strumento progettato per semplificare la visualizzazione dei documenti all'interno delle applicazioni .NET. Che tu abbia a che fare con PDF, documenti Word, fogli di calcolo Excel o presentazioni PowerPoint, questa libreria semplifica il processo di rendering e interazione con vari formati di file. In questo tutorial, ci concentreremo sullo sfruttamento delle funzionalità di GroupDocs.Viewer specificamente per estrarre informazioni sulla visualizzazione da documenti PDF.
## Prerequisiti
Prima di immergerti nel tutorial, assicurati di possedere i seguenti prerequisiti:
1.  Installazione di GroupDocs.Viewer per .NET: assicurati di aver scaricato e installato la libreria GroupDocs.Viewer. Puoi ottenerlo da[Link per scaricare](https://releases.groupdocs.com/viewer/net/).   
2. Conoscenza di base di C#: la familiarità con il linguaggio di programmazione C# è essenziale per comprendere e implementare gli esempi di codice forniti.
3. Accesso a un documento PDF: tieni pronto un documento PDF che utilizzerai per estrarre le informazioni sulla visualizzazione.

## Importa spazi dei nomi
Nel tuo progetto C#, importa gli spazi dei nomi necessari per utilizzare le funzionalità GroupDocs.Viewer.

```csharp
using System;
using GroupDocs.Viewer.Options;
using GroupDocs.Viewer.Results;
```


Analizziamo ora il processo di recupero delle informazioni sulla visualizzazione da un documento PDF utilizzando GroupDocs.Viewer per .NET.
## Passaggio 1: inizializza l'oggetto visualizzatore
Crea un oggetto Visualizzatore e fornisci il percorso del documento PDF come parametro.
```csharp
using (Viewer viewer = new Viewer("path/to/your/sample.pdf"))
{
```
## Passaggio 2: definire ViewInfoOptions
Specificare le opzioni di visualizzazione, come la visualizzazione HTML, per recuperare le informazioni sulla visualizzazione.
```csharp
	ViewInfoOptions options = ViewInfoOptions.ForHtmlView();
```
## Passaggio 3: ottieni informazioni sulla visualizzazione
Richiamare il metodo GetViewInfo per estrarre le informazioni sulla visualizzazione dal documento PDF.
```csharp
	PdfViewInfo info = viewer.GetViewInfo(options) as PdfViewInfo;
```
## Passaggio 4: informazioni sulla visualizzazione dell'output
Visualizza le informazioni sulla visualizzazione estratta, come tipo di documento, conteggio pagine e autorizzazioni di stampa.
```csharp
	Console.WriteLine("Document type is: " + info.FileType);
	Console.WriteLine("Pages count: " + info.Pages.Count);
	Console.WriteLine("Printing allowed: " + info.PrintingAllowed);
}
```

## Conclusione
In questo tutorial, abbiamo esplorato come utilizzare GroupDocs.Viewer per .NET per estrarre informazioni sulla visualizzazione da documenti PDF. Seguendo i passaggi forniti, puoi integrare perfettamente questa funzionalità nelle tue applicazioni .NET, migliorando la gestione dei documenti e le capacità di visualizzazione.
## Domande frequenti
### GroupDocs.Viewer è compatibile con altri formati di file oltre al PDF?
Sì, GroupDocs.Viewer supporta un'ampia gamma di formati di documenti, inclusi Word, Excel, PowerPoint e altri.
### Posso personalizzare le opzioni di visualizzazione in base ai requisiti della mia applicazione?
Assolutamente sì, GroupDocs.Viewer offre varie opzioni per personalizzare l'esperienza di visualizzazione in base alle tue esigenze specifiche.
### GroupDocs.Viewer è adatto sia per applicazioni desktop che web?
Sì, GroupDocs.Viewer è versatile e può essere integrato perfettamente in applicazioni .NET desktop e basate sul Web.
### GroupDocs.Viewer fornisce supporto e assistenza in caso di problemi durante l'implementazione?
Certamente, puoi chiedere assistenza al forum della community GroupDocs.Viewer o accedere a servizi di supporto professionale per una rapida risoluzione di eventuali problemi.
### Posso provare GroupDocs.Viewer prima di effettuare un acquisto?
 Sì, puoi esplorare le funzionalità di GroupDocs.Viewer accedendo alla versione di prova gratuita disponibile su[sito web](https://purchase.groupdocs.com/buy).