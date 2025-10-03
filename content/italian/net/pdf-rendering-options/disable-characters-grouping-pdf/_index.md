---
"description": "Scopri come disattivare il raggruppamento dei caratteri nei PDF utilizzando GroupDocs.Viewer per .NET. Segui il nostro tutorial passo passo per un rendering impeccabile dei documenti."
"linktitle": "Disabilitare il raggruppamento dei caratteri in PDF"
"second_title": "API .NET di GroupDocs.Viewer"
"title": "Disabilitare il raggruppamento dei caratteri in PDF"
"url": "/it/net/pdf-rendering-options/disable-characters-grouping-pdf/"
"weight": 11
type: docs
---
# Disabilitare il raggruppamento dei caratteri in PDF

## Introduzione
Nel mondo dello sviluppo .NET, la gestione della visualizzazione dei documenti può a volte essere una sfida, soprattutto quando si lavora con formati come i PDF. Tuttavia, con gli strumenti e le competenze giuste, è possibile semplificare questo processo in modo efficiente. Uno strumento che viene in soccorso è GroupDocs.Viewer per .NET. Questa potente libreria consente agli sviluppatori di eseguire il rendering e la visualizzazione fluida di vari tipi di documenti all'interno delle loro applicazioni .NET.

![Disabilitare il raggruppamento dei caratteri in PDF con GroupDocs.Viewer .NET](/viewer/pdf-rendering-options/disable-characters-grouping-in-pdf.png)

## Prerequisiti
Prima di immergerti nel tutorial, assicurati di aver impostato i seguenti prerequisiti:
1. Visual Studio: assicurati che Visual Studio sia installato sul tuo sistema.
2. GroupDocs.Viewer per .NET: Scarica e installa GroupDocs.Viewer per .NET da [link ufficiale per il download](https://releases.groupdocs.com/viewer/net/).
3. Conoscenza di base del linguaggio C#: familiarizzare con i fondamenti del linguaggio di programmazione C#.
4. File di documenti: prepara i file di documenti che intendi elaborare, ad esempio PDF o immagini.

## Importa spazi dei nomi
Per prima cosa, importiamo gli spazi dei nomi necessari nel nostro progetto. Questi spazi dei nomi ci forniranno l'accesso alle funzionalità di GroupDocs.Viewer di cui abbiamo bisogno.

```csharp
using System;
using System.IO;
using GroupDocs.Viewer.Options;
```

Ora analizziamo l'esempio fornito in passaggi gestibili.
## Passaggio 1: definire la directory di output
```csharp
string outputDirectory = "Your Document Directory";
```
Qui impostiamo una variabile per memorizzare la directory in cui verranno salvate le pagine HTML renderizzate.
## Passaggio 2: definire il formato del percorso del file di paging
```csharp
string pageFilePathFormat = Path.Combine(outputDirectory, "page_{0}.html");
```
Questo passaggio stabilisce il formato per la denominazione dei file HTML generati per ogni pagina del documento.
## Passaggio 3: inizializzare l'oggetto Viewer
```csharp
using (Viewer viewer = new Viewer(TestFiles.HIEROGLYPHS_PDF))
```
Qui inizializziamo l'oggetto Viewer, passando il percorso al file PDF che vogliamo visualizzare.
## Passaggio 4: configurare le opzioni di visualizzazione HTML
```csharp
HtmlViewOptions options = HtmlViewOptions.ForEmbeddedResources(pageFilePathFormat);
options.PdfOptions.DisableCharsGrouping = true;
```
In questa fase, impostiamo le opzioni di visualizzazione HTML, specificando che il raggruppamento dei caratteri nel PDF deve essere disabilitato.
## Passaggio 5: rendering del documento
```csharp
viewer.View(options);
```
Infine, chiamiamo il `View` sull'oggetto Viewer, passando le opzioni configurate per il rendering del documento.
## Passaggio 6: visualizzare la directory di output
```csharp
Console.WriteLine($"\nSource document rendered successfully.\nCheck output in {outputDirectory}.");
```
Questo passaggio genera un messaggio che indica il corretto rendering del documento e indica la posizione in cui è possibile trovare l'output.

## Conclusione
In conclusione, seguendo i passaggi descritti in questo tutorial, è possibile disabilitare senza problemi il raggruppamento dei caratteri nei documenti PDF utilizzando GroupDocs.Viewer per .NET. Questa libreria semplifica il processo di visualizzazione e manipolazione dei documenti nelle applicazioni .NET, fornendo agli sviluppatori un potente set di strumenti per migliorare le loro capacità di gestione dei documenti.
## Domande frequenti
### GroupDocs.Viewer è compatibile con tutte le versioni di .NET?
Sì, GroupDocs.Viewer è compatibile con diverse versioni di .NET, garantendo flessibilità e facilità di integrazione.
### Posso visualizzare documenti diversi dai PDF utilizzando GroupDocs.Viewer?
Assolutamente sì! GroupDocs.Viewer supporta un'ampia gamma di formati di documenti, inclusi file di Microsoft Office, immagini e altro ancora.
### È disponibile una versione di prova gratuita di GroupDocs.Viewer per .NET?
Sì, puoi accedere a una prova gratuita di GroupDocs.Viewer per .NET dal sito ufficiale [pagina delle release](https://releases.groupdocs.com/).
### Come posso ottenere licenze temporanee per GroupDocs.Viewer?
Le licenze temporanee per GroupDocs.Viewer possono essere ottenute da [pagina della licenza temporanea](https://purchase.groupdocs.com/temporary-license/).
### Dove posso trovare supporto o assistenza per le domande relative a GroupDocs.Viewer?
Per qualsiasi supporto o assistenza riguardante GroupDocs.Viewer, puoi visitare il sito [forum ufficiale](https://forum.groupdocs.com/c/viewer/9).