---
"description": "Scopri come visualizzare i PDF con le dimensioni di pagina originali utilizzando GroupDocs.Viewer per .NET. Segui la nostra guida passo passo e integra perfettamente questa funzionalità."
"linktitle": "Rendi PDF con dimensioni di pagina originali"
"second_title": "API .NET di GroupDocs.Viewer"
"title": "Rendi PDF con dimensioni di pagina originali"
"url": "/it/net/pdf-rendering-options/render-pdf-original-page-size/"
"weight": 17
type: docs
---
# Rendi PDF con dimensioni di pagina originali

## Introduzione
Nell'ambito dello sviluppo .NET, GroupDocs.Viewer si distingue come un potente strumento per il rendering di vari formati di documento, inclusi i PDF. Un requisito comune nella gestione dei documenti è il rendering dei PDF mantenendo le dimensioni di pagina originali. Per raggiungere questo obiettivo in modo ottimale, è necessaria una conoscenza approfondita di GroupDocs.Viewer per .NET e delle sue funzionalità.

![Rendi PDF con le dimensioni di pagina originali con GroupDocs.Viewer .NET](/viewer/pdf-rendering-options/render-pdf-with-original-page-size.png)

## Prerequisiti
Prima di iniziare a elaborare PDF con le dimensioni di pagina originali utilizzando GroupDocs.Viewer per .NET, assicurati di avere i seguenti prerequisiti:
### 1. Installa GroupDocs.Viewer per .NET
Inizia scaricando la libreria GroupDocs.Viewer dal sito web. Puoi ottenere la libreria dal sito web fornito. [collegamento per il download](https://releases.groupdocs.com/viewer/net/)Seguire le istruzioni di installazione fornite nella documentazione per integrarlo efficacemente nel progetto .NET.
### 2. Impostare l'ambiente di sviluppo
Assicuratevi di disporre di un ambiente di sviluppo configurato per lo sviluppo .NET. Questo include l'installazione di un IDE compatibile, come Visual Studio, e una conoscenza di base della programmazione C#.
### 3. Ottieni un documento PDF
Avrai bisogno di un documento PDF di esempio da visualizzare con GroupDocs.Viewer. Puoi utilizzare qualsiasi documento PDF a scopo di test. Se non ne hai uno, puoi scaricarne uno da diverse fonti online.

## Importa spazi dei nomi
Prima di procedere con il rendering dei PDF, è essenziale importare gli spazi dei nomi necessari nel progetto C#. Questo passaggio consente di accedere alle classi e ai metodi richiesti dalla libreria GroupDocs.Viewer.

```csharp
using System;
using System.IO;
using GroupDocs.Viewer.Options;
```

Ora che hai soddisfatto i prerequisiti e hai importato gli spazi dei nomi necessari, scomponiamo il processo di rendering dei PDF con le dimensioni di pagina originali utilizzando GroupDocs.Viewer per .NET in semplici passaggi:
## Passaggio 1: definire la directory di output
```csharp
string outputDirectory = "Your Document Directory";
```
Assicurati di specificare la directory in cui desideri salvare le pagine renderizzate. Sostituisci `"Your Document Directory"` con il percorso della directory desiderata.
## Passaggio 2: definire il formato del percorso del file di paging
```csharp
string pageFilePathFormat = Path.Combine(outputDirectory, "page_{0}.png");
```
Imposta il formato per la denominazione dei file di pagina renderizzati. In questo esempio, le pagine verranno salvate come immagini PNG con nomi file nel formato `"page_1.png"`, `"page_2.png"`, e così via.
## Passaggio 3: rendering del PDF con le dimensioni di pagina originali
```csharp
using (Viewer viewer = new Viewer("Path_to_Your_PDF_File.pdf"))
{
    PngViewOptions viewOptions = new PngViewOptions(pageFilePathFormat);
    viewOptions.PdfOptions.RenderOriginalPageSize = true;
    
    viewer.View(viewOptions);
}
```
Istanziare un `Viewer` oggetto con il percorso del file PDF. Quindi, crea `PngViewOptions` con il formato del percorso del file di paging specificato. Imposta `RenderOriginalPageSize` proprietà a `true` per preservare le dimensioni originali della pagina durante il rendering.
## Passaggio 4: visualizzare la posizione del documento renderizzato
```csharp
Console.WriteLine($"\nSource document rendered successfully.\nCheck output in {outputDirectory}.");
```
Visualizza un messaggio che indica l'avvenuto rendering e indica la directory in cui sono salvate le pagine renderizzate.

## Conclusione
Il rendering di PDF con le dimensioni di pagina originali utilizzando GroupDocs.Viewer per .NET è un processo semplice se si seguono i passaggi descritti in questo tutorial. Importando gli spazi dei nomi necessari e seguendo la guida dettagliata, è possibile integrare perfettamente questa funzionalità nelle applicazioni .NET.
## Domande frequenti
### GroupDocs.Viewer può riprodurre altri formati di documenti oltre al PDF?
Sì, GroupDocs.Viewer supporta il rendering di vari formati di documenti, tra cui Word, Excel, PowerPoint e altri.
### GroupDocs.Viewer è compatibile con .NET Core?
Sì, GroupDocs.Viewer è compatibile sia con gli ambienti .NET Framework che .NET Core.
### Posso personalizzare il formato di output delle pagine renderizzate?
Sì, puoi personalizzare il formato di output modificando le opzioni fornite da GroupDocs.Viewer, ad esempio impostando formati immagine diversi o specificando opzioni di rendering personalizzate.
### GroupDocs.Viewer supporta il rendering di documenti basato su cloud?
Sì, GroupDocs.Viewer fornisce API per il rendering di documenti basati su cloud, consentendo di eseguire il rendering di documenti direttamente dai provider di archiviazione cloud.
### È disponibile una versione di prova gratuita per GroupDocs.Viewer?
Sì, puoi esplorare GroupDocs.Viewer con una prova gratuita visitando il sito fornito [collegamento](https://releases.groupdocs.com/).