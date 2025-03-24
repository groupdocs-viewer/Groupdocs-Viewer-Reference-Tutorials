---
title: Rendering di file CHM
linktitle: Rendering di file CHM
second_title: API GroupDocs.Viewer .NET
description: Scopri come eseguire il rendering dei file CHM in .NET utilizzando GroupDocs.Viewer. Converti i formati CHM in HTML, JPG, PNG e PDF senza sforzo.
weight: 10
url: /it/net/rendering-web-documents/render-chm/
---

# Rendering di file CHM

## introduzione
In questo tutorial esploreremo come eseguire il rendering dei file CHM (Compiled HTML Help) utilizzando GroupDocs.Viewer per .NET. GroupDocs.Viewer per .NET è una potente API per il rendering di documenti che consente agli sviluppatori di visualizzare oltre 170 tipi di documenti all'interno delle proprie applicazioni .NET senza richiedere installazioni di software esterno.

## Prerequisiti

Prima di immergerci nel rendering dei file CHM, assicurati di avere i seguenti prerequisiti:

### Installazione di GroupDocs.Viewer per .NET

 Per iniziare, è necessario installare GroupDocs.Viewer per .NET. È possibile scaricare la libreria da[Sito web di GroupDocs](https://releases.groupdocs.com/viewer/net/) oppure installarlo tramite NuGet Package Manager eseguendo il comando seguente nella console di Package Manager:

```bash
Install-Package GroupDocs.Viewer
```

## Importazione di spazi dei nomi

Assicurati di importare gli spazi dei nomi necessari nel tuo progetto:

```csharp
using System;
using System.Collections.Generic;
using System.Text;
using System.IO;
using GroupDocs.Viewer.Options;
```

Ora suddividiamo il processo di rendering in più passaggi:

## Passaggio 1: definire la directory di output

Definisci la directory in cui desideri salvare i file renderizzati:

```csharp
string outputDirectory = "Your Document Directory";
```

## Passaggio 2: rendering in HTML

Per eseguire il rendering dei file CHM in HTML, utilizzare il seguente snippet di codice:

```csharp
string pageFilePathFormat = Path.Combine(outputDirectory, "chm_result_{0}.html");

using (Viewer viewer = new Viewer("Your_CHM_File_Path"))
{
    HtmlViewOptions options = HtmlViewOptions.ForEmbeddedResources(pageFilePathFormat);
    options.RenderToSinglePage = true; // Imposta su true per convertire tutto il contenuto CHM in una singola pagina

    viewer.View(options); //Converti tutte le pagine
}
```

## Passaggio 3: rendering in JPG

Per eseguire il rendering dei file CHM in immagini JPG, utilizzare il seguente snippet di codice:

```csharp
string pageFilePathFormat = Path.Combine(outputDirectory, "chm_result_{0}.jpg");

using (Viewer viewer = new Viewer("Your_CHM_File_Path"))
{
    JpgViewOptions options = new JpgViewOptions(pageFilePathFormat);

    viewer.View(options, 1, 2, 3); // Converti solo le pagine 1, 2, 3
}
```

## Passaggio 4: rendering in PNG

Per eseguire il rendering dei file CHM in immagini PNG, utilizzare il seguente snippet di codice:

```csharp
string pageFilePathFormat = Path.Combine(outputDirectory, "chm_result_{0}.png");

using (Viewer viewer = new Viewer("Your_CHM_File_Path"))
{
    PngViewOptions options = new PngViewOptions(pageFilePathFormat);

    viewer.View(options, 1, 2, 3); // Converti solo le pagine 1, 2, 3
}
```

## Passaggio 5: rendering in PDF

Per eseguire il rendering dei file CHM in un documento PDF, utilizzare il seguente snippet di codice:

```csharp
string pageFilePathFormat = Path.Combine(outputDirectory, "chm_result.pdf");

using (Viewer viewer = new Viewer("Your_CHM_File_Path"))
{
    PdfViewOptions options = new PdfViewOptions(pageFilePathFormat);

    viewer.View(options); //Converti tutte le pagine
}
```

## Passaggio 6: controllare l'output

Una volta completato il processo di rendering, controlla la directory di output specificata per i file renderizzati:

```csharp
Console.WriteLine($"\nSource document rendered successfully.\nCheck output in {outputDirectory}.");
```

## Conclusione

Il rendering dei file CHM utilizzando GroupDocs.Viewer per .NET è un processo semplice. Seguendo i passaggi descritti in questo tutorial, puoi convertire in modo efficiente i documenti CHM in vari formati come HTML, immagini (JPG, PNG) e PDF all'interno delle tue applicazioni .NET.

## Domande frequenti

### Q1: GroupDocs.Viewer può eseguire il rendering di altri formati di documenti oltre a CHM?

R1: Sì, GroupDocs.Viewer supporta il rendering di oltre 170 formati di documenti tra cui PDF, DOCX, XLSX, PPTX e altri.

### Q2: GroupDocs.Viewer è compatibile con .NET Core?

R2: Sì, GroupDocs.Viewer supporta .NET Core oltre al tradizionale .NET Framework.

### Q3: Posso personalizzare le opzioni di rendering per diversi formati di output?

R3: Sì, GroupDocs.Viewer fornisce varie opzioni per personalizzare il processo di rendering, come specificare i numeri di pagina, impostare la qualità dell'immagine e configurare i percorsi di output.

### Q4: GroupDocs.Viewer richiede dipendenze esterne per il rendering dei documenti?

R4: No, GroupDocs.Viewer è una libreria autonoma e non richiede dipendenze esterne o installazioni di software di terze parti.

### Q5: È disponibile una prova gratuita per GroupDocs.Viewer?

 R5: Sì, puoi usufruire di una prova gratuita di GroupDocs.Viewer visitando il sito[sito web](https://releases.groupdocs.com/).