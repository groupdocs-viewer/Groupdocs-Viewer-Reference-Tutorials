---
title: Disabilita la selezione del testo nel PDF
linktitle: Disabilita la selezione del testo nel PDF
second_title: API GroupDocs.Viewer .NET
description: Scopri come disabilitare la selezione del testo nel PDF utilizzando GroupDocs.Viewer per .NET. Segui la nostra guida passo passo per un'integrazione perfetta.
type: docs
weight: 13
url: /it/net/pdf-rendering-options/disable-text-selection-pdf/
---
## introduzione
GroupDocs.Viewer per .NET è una potente API per il rendering di documenti che consente agli sviluppatori di integrare facilmente le funzionalità di visualizzazione dei documenti nelle loro applicazioni .NET. Una delle funzionalità chiave fornite da GroupDocs.Viewer è la possibilità di disabilitare la selezione del testo nei documenti PDF. Questa funzionalità è particolarmente utile negli scenari in cui è necessario impedire agli utenti di copiare testo da documenti sensibili, garantendo la sicurezza e l'integrità dei documenti.
## Prerequisiti
Prima di immergerci nella guida passo passo su come disabilitare la selezione del testo nel PDF utilizzando GroupDocs.Viewer per .NET, assicurati di avere i seguenti prerequisiti:
1.  Installazione di GroupDocs.Viewer per .NET: assicurati di aver scaricato e installato GroupDocs.Viewer per .NET dal[Link per scaricare](https://releases.groupdocs.com/viewer/net/).
2. Directory dei documenti: prepara una directory in cui verranno archiviati i tuoi documenti. Dovrai specificare questa directory nello snippet di codice per eseguire il rendering del documento PDF.

## Importa spazi dei nomi
Innanzitutto, è necessario importare gli spazi dei nomi necessari per accedere alle funzionalità fornite da GroupDocs.Viewer per .NET. Ecco come puoi farlo:

```csharp
using System;
using System.IO;
using GroupDocs.Viewer.Options;
```

Ora, suddividiamo il processo di disabilitazione della selezione del testo in un documento PDF utilizzando GroupDocs.Viewer per .NET in più passaggi:
## Passaggio 1: specificare la directory di output
```csharp
string outputDirectory = "Your Document Directory";
```
 In questo passaggio, sostituisci`"Your Document Directory"` con il percorso della directory in cui si trova il documento PDF.
## Passaggio 2: definire il formato del percorso del file di paging
```csharp
string pageFilePathFormat = Path.Combine(outputDirectory, "page_{0}.html");
```
Questo passaggio definisce il formato per i percorsi dei file delle pagine HTML sottoposte a rendering. Ogni pagina del documento PDF verrà convertita in un file HTML con un numero di pagina sequenziale.
## Passaggio 3: rendering del documento PDF con la selezione del testo disabilitata
```csharp
using (Viewer viewer = new Viewer("Path to Your PDF Document"))
{
    HtmlViewOptions options = HtmlViewOptions.ForEmbeddedResources(pageFilePathFormat);
    options.PdfOptions.RenderTextAsImage = true;
    viewer.View(options);
}
```
 Sostituire`"Path to Your PDF Document"` con il percorso effettivo del file PDF. Questo frammento di codice inizializza a`Viewer` oggetto, configura le opzioni di visualizzazione HTML per incorporare risorse e disabilita la selezione del testo tramite l'impostazione`RenderTextAsImage` proprietà a`true`.
## Passaggio 4: Visualizza il messaggio di successo
```csharp
Console.WriteLine($"\nSource document rendered successfully.\nCheck output in {outputDirectory}.");
```
Dopo aver eseguito il rendering del documento PDF, questo passaggio visualizza un messaggio di successo insieme alla directory in cui sono archiviate le pagine HTML renderizzate.

## Conclusione
In questo tutorial, abbiamo imparato come disabilitare la selezione del testo nei documenti PDF utilizzando GroupDocs.Viewer per .NET. Seguendo la guida passo passo, puoi integrare perfettamente questa funzionalità nelle tue applicazioni .NET, garantendo la sicurezza dei documenti e migliorando l'esperienza dell'utente.
## Domande frequenti
### Posso personalizzare la directory di output per le pagine HTML renderizzate?
Sì, puoi specificare qualsiasi percorso di directory in cui desideri archiviare le pagine HTML renderizzate.
### GroupDocs.Viewer per .NET è compatibile con diverse versioni di .NET framework?
Sì, GroupDocs.Viewer per .NET è compatibile con varie versioni di .NET Framework, inclusi .NET Core e .NET Framework.
### La disabilitazione della selezione del testo influisce su altre funzionalità del documento PDF?
No, la disabilitazione della selezione del testo impedisce solo agli utenti di selezionare e copiare testo dal documento. Altre funzionalità rimangono intatte.
### Posso abilitare nuovamente la selezione del testo dopo aver eseguito il rendering del documento?
 Sì, puoi abilitare la selezione del testo semplicemente impostando il file`RenderTextAsImage` proprietà a`false` nelle opzioni di visualizzazione HTML.
### È disponibile una versione di prova per GroupDocs.Viewer per .NET?
 Sì, puoi accedere a una prova gratuita di GroupDocs.Viewer per .NET da[sito web](https://releases.groupdocs.com/).