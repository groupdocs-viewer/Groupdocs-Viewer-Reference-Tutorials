---
"description": "Scopri come disattivare la selezione del testo nei PDF utilizzando GroupDocs.Viewer per .NET. Segui la nostra guida passo passo per un'integrazione perfetta."
"linktitle": "Disabilita la selezione del testo in PDF"
"second_title": "API .NET di GroupDocs.Viewer"
"title": "Disabilita la selezione del testo in PDF"
"url": "/it/net/pdf-rendering-options/disable-text-selection-pdf/"
"weight": 13
type: docs
---
# Disabilita la selezione del testo in PDF

## Introduzione
GroupDocs.Viewer per .NET è una potente API per il rendering di documenti che consente agli sviluppatori di integrare facilmente le funzionalità di visualizzazione dei documenti nelle loro applicazioni .NET. Una delle funzionalità chiave di GroupDocs.Viewer è la possibilità di disabilitare la selezione del testo nei documenti PDF. Questa funzionalità è particolarmente utile negli scenari in cui è necessario impedire agli utenti di copiare testo da documenti sensibili, garantendone la sicurezza e l'integrità.

![Disabilitare la selezione del testo in PDF con GroupDocs.Viewer .NET](/viewer/pdf-rendering-options/disable-text-selection-in-pdf.png)

## Prerequisiti
Prima di addentrarci nella guida dettagliata su come disattivare la selezione del testo in un PDF utilizzando GroupDocs.Viewer per .NET, assicurati di avere i seguenti prerequisiti:
1. Installazione di GroupDocs.Viewer per .NET: assicurarsi di aver scaricato e installato GroupDocs.Viewer per .NET da [collegamento per il download](https://releases.groupdocs.com/viewer/net/).
2. Directory dei documenti: prepara una directory in cui archiviare i tuoi documenti. Dovrai specificare questa directory nel frammento di codice per il rendering del documento PDF.

## Importa spazi dei nomi
Per prima cosa, è necessario importare gli spazi dei nomi necessari per accedere alle funzionalità fornite da GroupDocs.Viewer per .NET. Ecco come fare:

```csharp
using System;
using System.IO;
using GroupDocs.Viewer.Options;
```

Ora, scomponiamo il processo di disattivazione della selezione del testo in un documento PDF utilizzando GroupDocs.Viewer per .NET in più passaggi:
## Passaggio 1: specificare la directory di output
```csharp
string outputDirectory = "Your Document Directory";
```
In questo passaggio, sostituisci `"Your Document Directory"` con il percorso della directory in cui si trova il documento PDF.
## Passaggio 2: definire il formato del percorso del file di paging
```csharp
string pageFilePathFormat = Path.Combine(outputDirectory, "page_{0}.html");
```
Questo passaggio definisce il formato per i percorsi dei file delle pagine HTML renderizzate. Ogni pagina del documento PDF verrà convertita in un file HTML con un numero di pagina sequenziale.
## Passaggio 3: rendering del documento PDF con la selezione del testo disabilitata
```csharp
using (Viewer viewer = new Viewer("Path to Your PDF Document"))
{
    HtmlViewOptions options = HtmlViewOptions.ForEmbeddedResources(pageFilePathFormat);
    options.PdfOptions.RenderTextAsImage = true;
    viewer.View(options);
}
```
Sostituire `"Path to Your PDF Document"` con il percorso effettivo del file PDF. Questo frammento di codice inizializza un `Viewer` oggetto, configura le opzioni di visualizzazione HTML per incorporare risorse e disabilita la selezione del testo impostando `RenderTextAsImage` proprietà a `true`.
## Passaggio 4: visualizzare il messaggio di successo
```csharp
Console.WriteLine($"\nSource document rendered successfully.\nCheck output in {outputDirectory}.");
```
Dopo aver renderizzato il documento PDF, questo passaggio visualizza un messaggio di successo insieme alla directory in cui sono archiviate le pagine HTML renderizzate.

## Conclusione
In questo tutorial abbiamo imparato come disattivare la selezione del testo nei documenti PDF utilizzando GroupDocs.Viewer per .NET. Seguendo la guida passo passo, potrete integrare perfettamente questa funzionalità nelle vostre applicazioni .NET, garantendo la sicurezza dei documenti e migliorando l'esperienza utente.
## Domande frequenti
### Posso personalizzare la directory di output per le pagine HTML renderizzate?
Sì, puoi specificare qualsiasi percorso di directory in cui desideri che vengano archiviate le pagine HTML renderizzate.
### GroupDocs.Viewer per .NET è compatibile con le diverse versioni di .NET Framework?
Sì, GroupDocs.Viewer per .NET è compatibile con varie versioni del framework .NET, tra cui .NET Core e .NET Framework.
### La disattivazione della selezione del testo influisce sulle altre funzionalità del documento PDF?
No, disabilitando la selezione del testo si impedisce solo agli utenti di selezionare e copiare testo dal documento. Le altre funzionalità rimangono invariate.
### Posso abilitare nuovamente la selezione del testo dopo aver renderizzato il documento?
Sì, puoi abilitare la selezione del testo semplicemente impostando `RenderTextAsImage` proprietà a `false` nelle opzioni di visualizzazione HTML.
### Esiste una versione di prova disponibile per GroupDocs.Viewer per .NET?
Sì, puoi accedere a una prova gratuita di GroupDocs.Viewer per .NET da [sito web](https://releases.groupdocs.com/).