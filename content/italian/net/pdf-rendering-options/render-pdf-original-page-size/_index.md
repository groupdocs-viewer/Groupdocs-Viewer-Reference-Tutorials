---
title: Visualizza il PDF con la dimensione della pagina originale
linktitle: Visualizza il PDF con la dimensione della pagina originale
second_title: API GroupDocs.Viewer .NET
description: Scopri come eseguire il rendering dei PDF con le dimensioni di pagina originali utilizzando GroupDocs.Viewer per .NET. Segui la nostra guida passo passo e integra perfettamente questa funzionalità.
weight: 17
url: /it/net/pdf-rendering-options/render-pdf-original-page-size/
---

# Visualizza il PDF con la dimensione della pagina originale

## introduzione
Nell'ambito dello sviluppo .NET, GroupDocs.Viewer si distingue come un potente strumento per il rendering di vari formati di documenti, inclusi i PDF. Un requisito comune nella gestione dei documenti è eseguire il rendering dei PDF preservando le dimensioni della pagina originale. Il raggiungimento di questo compito senza problemi richiede una conoscenza approfondita di GroupDocs.Viewer per .NET e delle sue funzionalità.
## Prerequisiti
Prima di immergerti nel rendering di PDF con dimensioni di pagina originali utilizzando GroupDocs.Viewer per .NET, assicurati di disporre dei seguenti prerequisiti:
### 1. Installa GroupDocs.Viewer per .NET
 Inizia scaricando la libreria GroupDocs.Viewer dal sito Web. È possibile ottenere la libreria dal file fornito[Link per scaricare](https://releases.groupdocs.com/viewer/net/). Segui le istruzioni di installazione fornite nella documentazione per integrarlo in modo efficace nel tuo progetto .NET.
### 2. Configurare l'ambiente di sviluppo
Assicurati di avere un ambiente di sviluppo configurato per lo sviluppo .NET. Ciò include l'installazione di un IDE compatibile, come Visual Studio, e una conoscenza di base della programmazione C#.
### 3. Ottieni un documento PDF
Avrai bisogno di un documento PDF di esempio da visualizzare con GroupDocs.Viewer. È possibile utilizzare qualsiasi documento PDF a scopo di test. Se non ne hai uno, puoi scaricare un PDF di esempio da varie fonti online.

## Importa spazi dei nomi
Prima di procedere con il rendering dei PDF, è essenziale importare gli spazi dei nomi necessari nel progetto C#. Questo passaggio consente di accedere alle classi e ai metodi richiesti dalla libreria GroupDocs.Viewer.

```csharp
using System;
using System.IO;
using GroupDocs.Viewer.Options;
```

Ora che disponi dei prerequisiti e degli spazi dei nomi necessari importati, analizziamo il processo di rendering dei PDF con le dimensioni di pagina originali utilizzando GroupDocs.Viewer per .NET in semplici passaggi:
## Passaggio 1: definire la directory di output
```csharp
string outputDirectory = "Your Document Directory";
```
 Assicurati di specificare la directory in cui desideri salvare le pagine renderizzate. Sostituire`"Your Document Directory"` con il percorso della directory desiderata.
## Passaggio 2: definire il formato del percorso del file di paging
```csharp
string pageFilePathFormat = Path.Combine(outputDirectory, "page_{0}.png");
```
Imposta il formato per denominare i file di pagina sottoposti a rendering. In questo esempio, le pagine verranno salvate come immagini PNG con nomi di file nel formato`"page_1.png"`, `"page_2.png"`, e così via.
## Passaggio 3: esegui il rendering del PDF con le dimensioni della pagina originale
```csharp
using (Viewer viewer = new Viewer("Path_to_Your_PDF_File.pdf"))
{
    PngViewOptions viewOptions = new PngViewOptions(pageFilePathFormat);
    viewOptions.PdfOptions.RenderOriginalPageSize = true;
    
    viewer.View(viewOptions);
}
```
 Istanziare a`Viewer` oggetto con il percorso del file PDF. Quindi, crea`PngViewOptions` con il formato del percorso del file di paging specificato. Impostato`RenderOriginalPageSize` proprietà a`true` per preservare le dimensioni della pagina originale durante il rendering.
## Passaggio 4: Visualizza la posizione del documento sottoposto a rendering
```csharp
Console.WriteLine($"\nSource document rendered successfully.\nCheck output in {outputDirectory}.");
```
Stampa un messaggio che indica il rendering riuscito e fornisce la directory in cui vengono salvate le pagine renderizzate.

## Conclusione
Il rendering di PDF con dimensioni di pagina originali utilizzando GroupDocs.Viewer per .NET è un processo semplice quando si seguono i passaggi descritti in questo tutorial. Importando gli spazi dei nomi necessari e seguendo la guida passo passo, puoi integrare perfettamente questa funzionalità nelle tue applicazioni .NET.
## Domande frequenti
### GroupDocs.Viewer può eseguire il rendering di altri formati di documenti oltre al PDF?
Sì, GroupDocs.Viewer supporta il rendering di vari formati di documenti, tra cui Word, Excel, PowerPoint e altri.
### GroupDocs.Viewer è compatibile con .NET Core?
Sì, GroupDocs.Viewer è compatibile sia con gli ambienti .NET Framework che .NET Core.
### Posso personalizzare il formato di output delle pagine renderizzate?
Sì, puoi personalizzare il formato di output modificando le opzioni fornite da GroupDocs.Viewer, come l'impostazione di diversi formati di immagine o la specifica di opzioni di rendering personalizzate.
### GroupDocs.Viewer offre supporto per il rendering di documenti basato su cloud?
Sì, GroupDocs.Viewer fornisce API per il rendering di documenti basato su cloud, consentendoti di eseguire il rendering di documenti direttamente dai fornitori di archiviazione cloud.
### È disponibile una prova gratuita per GroupDocs.Viewer?
 Sì, puoi esplorare GroupDocs.Viewer con una prova gratuita visitando il sito fornito[collegamento](https://releases.groupdocs.com/).