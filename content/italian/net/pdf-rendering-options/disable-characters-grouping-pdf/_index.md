---
title: Disabilita il raggruppamento dei caratteri nel PDF
linktitle: Disabilita il raggruppamento dei caratteri nel PDF
second_title: API GroupDocs.Viewer .NET
description: Scopri come disabilitare il raggruppamento di caratteri nei PDF utilizzando GroupDocs.Viewer per .NET. Segui il nostro tutorial passo passo per un rendering fluido dei documenti.
weight: 11
url: /it/net/pdf-rendering-options/disable-characters-grouping-pdf/
---
## introduzione
Nel mondo dello sviluppo .NET, la gestione della visualizzazione dei documenti a volte può rappresentare una sfida, soprattutto quando si ha a che fare con formati come i PDF. Tuttavia, con gli strumenti e le conoscenze giuste, è possibile semplificare questo processo in modo efficiente. Uno di questi strumenti che viene in soccorso è GroupDocs.Viewer per .NET. Questa potente libreria consente agli sviluppatori di eseguire il rendering e visualizzare senza problemi vari tipi di documenti all'interno delle loro applicazioni .NET.
## Prerequisiti
Prima di immergerti nel tutorial, assicurati di aver impostato i seguenti prerequisiti:
1. Visual Studio: assicurati di avere Visual Studio installato sul tuo sistema.
2.  GroupDocs.Viewer per .NET: scaricare e installare GroupDocs.Viewer per .NET dal[collegamento ufficiale per il download](https://releases.groupdocs.com/viewer/net/).
3. Conoscenza di base di C#: acquisisci familiarità con i fondamenti del linguaggio di programmazione C#.
4. File di documenti: prepara i file di documenti che intendi sottoporre a rendering, come PDF o immagini.

## Importa spazi dei nomi
Innanzitutto, importiamo gli spazi dei nomi necessari nel nostro progetto. Questi spazi dei nomi forniranno l'accesso alle funzionalità di cui abbiamo bisogno da GroupDocs.Viewer.

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
Questo passaggio stabilisce il formato per denominare i file HTML generati per ciascuna pagina del documento.
## Passaggio 3: inizializzare l'oggetto visualizzatore
```csharp
using (Viewer viewer = new Viewer(TestFiles.HIEROGLYPHS_PDF))
```
Qui inizializziamo l'oggetto Viewer, passando il percorso al file PDF che vogliamo renderizzare.
## Passaggio 4: configura le opzioni di visualizzazione HTML
```csharp
HtmlViewOptions options = HtmlViewOptions.ForEmbeddedResources(pageFilePathFormat);
options.PdfOptions.DisableCharsGrouping = true;
```
In questo passaggio, configuriamo le opzioni di visualizzazione HTML, specificando che il raggruppamento dei caratteri nel PDF deve essere disabilitato.
## Passaggio 5: rendering del documento
```csharp
viewer.View(options);
```
 Infine, chiamiamo il`View` metodo sull'oggetto Viewer, passando le opzioni configurate per eseguire il rendering del documento.
## Passaggio 6: Visualizza la directory di output
```csharp
Console.WriteLine($"\nSource document rendered successfully.\nCheck output in {outputDirectory}.");
```
Questo passaggio genera un messaggio che indica il rendering corretto del documento e fornisce la posizione in cui è possibile trovare l'output.

## Conclusione
In conclusione, seguendo i passaggi delineati in questo tutorial, puoi disattivare facilmente il raggruppamento dei caratteri nei documenti PDF utilizzando GroupDocs.Viewer per .NET. Questa libreria semplifica il processo di visualizzazione e manipolazione dei documenti all'interno delle applicazioni .NET, fornendo agli sviluppatori un potente set di strumenti per migliorare le loro capacità di gestione dei documenti.
## Domande frequenti
### GroupDocs.Viewer è compatibile con tutte le versioni di .NET?
Sì, GroupDocs.Viewer è compatibile con varie versioni di .NET, garantendo flessibilità e facilità di integrazione.
### Posso eseguire il rendering di documenti diversi dai PDF utilizzando GroupDocs.Viewer?
Assolutamente! GroupDocs.Viewer supporta un'ampia gamma di formati di documenti, inclusi file di Microsoft Office, immagini e altro ancora.
### È disponibile una prova gratuita per GroupDocs.Viewer per .NET?
 Sì, puoi accedere a una prova gratuita di GroupDocs.Viewer per .NET dal sito ufficiale[pagina delle uscite](https://releases.groupdocs.com/).
### Come posso ottenere licenze temporanee per GroupDocs.Viewer?
Le licenze temporanee per GroupDocs.Viewer possono essere ottenute da[pagina della licenza temporanea](https://purchase.groupdocs.com/temporary-license/).
### Dove posso trovare supporto o assistenza per le domande relative a GroupDocs.Viewer?
 Per qualsiasi supporto o assistenza riguardante GroupDocs.Viewer, è possibile visitare il[foro ufficiale](https://forum.groupdocs.com/c/viewer/9).