---
title: Numeri di rendering
linktitle: Numeri di rendering
second_title: API GroupDocs.Viewer .NET
description: Esplora la potenza di Groupdocs.Viewer per .NET nel rendering dei file Numbers senza problemi. Converti in HTML, JPG, PNG e PDF senza sforzo.
weight: 15
url: /it/net/spreadsheet-rendering-options/rendering-numbers/
---

# Numeri di rendering

## introduzione
Benvenuto in questo tutorial passo passo sul rendering dei file Numbers utilizzando Groupdocs.Viewer per .NET. Che tu sia uno sviluppatore esperto o un principiante, questa guida ti guiderà attraverso il processo di conversione dei documenti Numbers in vari formati. Groupdocs.Viewer per .NET è un potente strumento che ti consente di integrare perfettamente le funzionalità di visualizzazione dei documenti nelle tue applicazioni .NET.
## Prerequisiti
Prima di immergerti nel tutorial, assicurati di avere i seguenti prerequisiti:
- Una conoscenza pratica dello sviluppo C# e .NET.
-  Groupdocs.Viewer per la libreria .NET installata. Puoi scaricarlo[Qui](https://releases.groupdocs.com/viewer/net/).
- Il percorso della directory del documento in cui verranno salvati i file di output.
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
Prima di iniziare il rendering, definire la directory di output in cui verranno salvati i file convertiti. Sostituisci "La tua directory dei documenti" con il percorso effettivo:
```csharp
string outputDirectory = "Your Document Directory";
```
## Passaggio 2: rendering in HTML multipagina
Utilizza il codice seguente per convertire il file Numbers in HTML multipagina:
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
Congratulazioni! Hai eseguito con successo il rendering dei file Numbers in vari formati utilizzando Groupdocs.Viewer per .NET.
## Conclusione
In questo tutorial, abbiamo trattato le basi del rendering dei file Numbers utilizzando Groupdocs.Viewer per .NET. Questa potente libreria fornisce un'integrazione perfetta per la visualizzazione e la conversione di documenti nelle applicazioni .NET.
## Domande frequenti
### Posso utilizzare Groupdocs.Viewer for .NET con altri tipi di documenti?
Sì, Groupdocs.Viewer supporta un'ampia gamma di formati di documenti, inclusi Word, Excel, PDF e altri.
### È disponibile una licenza temporanea a scopo di test?
 Sì, puoi ottenere una licenza temporanea[Qui](https://purchase.groupdocs.com/temporary-license/) per i test.
### Dove posso trovare supporto per Groupdocs.Viewer per .NET?
 Visitare il[Forum di Groupdocs.Viewer](https://forum.groupdocs.com/c/viewer/9) per assistenza e discussioni.
### Come posso acquistare la versione completa di Groupdocs.Viewer per .NET?
 Puoi acquistare la versione completa[Qui](https://purchase.groupdocs.com/buy).
### È disponibile una versione di prova gratuita?
 Sì, puoi esplorare la versione di prova gratuita[Qui](https://releases.groupdocs.com/).