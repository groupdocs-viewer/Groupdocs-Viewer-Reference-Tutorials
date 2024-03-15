---
title: Rendering di archivi su pagine HTML singole o multiple
linktitle: Rendering di archivi su pagine HTML singole o multiple
second_title: API GroupDocs.Viewer .NET
description: Scopri come eseguire il rendering degli archivi in pagine HTML utilizzando GroupDocs.Viewer per .NET. Integra facilmente le funzionalità di visualizzazione dei documenti nelle tue applicazioni .NET.
type: docs
weight: 12
url: /it/net/rendering-archive-files/render-archives-html/
---
## introduzione
GroupDocs.Viewer per .NET è una potente libreria di rendering di documenti che consente agli sviluppatori di integrare facilmente le funzionalità di visualizzazione dei documenti nelle loro applicazioni .NET. Se devi eseguire il rendering degli archivi su pagine HTML singole o multiple, questo tutorial ti guiderà passo dopo passo attraverso il processo.
## Prerequisiti
Prima di immergerti in questo tutorial, assicurati di possedere i seguenti prerequisiti:
1.  GroupDocs.Viewer per .NET: assicurati di avere la libreria installata nel tuo progetto. Puoi scaricarlo da[Qui](https://releases.groupdocs.com/viewer/net/).
2. Ambiente di sviluppo: disporre di un ambiente di sviluppo funzionante configurato per lo sviluppo .NET.
3. Directory dei documenti: prepara una directory in cui sono archiviati i tuoi documenti.
4. Comprensione di base di C#: acquisisci familiarità con le nozioni di base del linguaggio di programmazione C#.

## Importa spazi dei nomi
Nel codice C#, assicurati di importare gli spazi dei nomi necessari:
```csharp
using GroupDocs.Viewer.Options;
using System;
using System.IO;
```

Seguire questi passaggi per eseguire il rendering degli archivi su pagine HTML singole o multiple utilizzando GroupDocs.Viewer per .NET:
## Passaggio 1: imposta la directory di output
Definisci la directory in cui desideri salvare le pagine HTML renderizzate:
```csharp
string outputDirectory = "Your Document Directory";
```
## Passaggio 2: definire il formato del percorso del file
Specificare il formato del percorso file per le pagine HTML. Per il rendering di una sola pagina:
```csharp
string pageFilePathFormat = Path.Combine(outputDirectory, "RAR_result.html");
```
Per il rendering multipagina:
```csharp
pageFilePathFormat = Path.Combine(outputDirectory, "RAR_result_page_{0}.html");
```
## Passaggio 3: rendering in HTML a pagina singola
```csharp
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_RAR_WITH_FOLDERS))
{
    HtmlViewOptions options = HtmlViewOptions.ForEmbeddedResources(pageFilePathFormat);
    options.RenderToSinglePage = true; 
    viewer.View(options);
}
```
## Passaggio 4: rendering in più pagine HTML
```csharp
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_RAR_WITH_FOLDERS))
{
    HtmlViewOptions options = HtmlViewOptions.ForEmbeddedResources(pageFilePathFormat);
    options.ArchiveOptions.ItemsPerPage = 10; // Imposta gli elementi per pagina
    viewer.View(options);
}
```
## Passaggio 5: controllare l'output
```csharp
Console.WriteLine($"\nSource document rendered successfully.\nCheck output in {outputDirectory}.");
```

## Conclusione
Il rendering degli archivi in pagine HTML utilizzando GroupDocs.Viewer per .NET è un processo semplice. Seguendo i passaggi descritti in questa esercitazione, puoi integrare perfettamente le funzionalità di visualizzazione dei documenti nelle tue applicazioni .NET.
## Domande frequenti
### Posso eseguire il rendering di altri formati di documenti oltre agli archivi?
Sì, GroupDocs.Viewer supporta un'ampia gamma di formati di documenti tra cui PDF, DOCX, XLSX, PPTX e altri.
### GroupDocs.Viewer è adatto sia per applicazioni desktop che web?
Assolutamente sì, GroupDocs.Viewer può essere utilizzato senza problemi sia nelle applicazioni desktop che in quelle web.
### GroupDocs.Viewer offre opzioni di personalizzazione per l'interfaccia del visualizzatore?
Sì, puoi personalizzare l'interfaccia del visualizzatore in base alle tue esigenze.
### Posso eseguire il rendering dei documenti in modo asincrono con GroupDocs.Viewer?
Sì, GroupDocs.Viewer fornisce funzionalità di rendering asincrono per migliorare le prestazioni.
### GroupDocs.Viewer supporta le annotazioni dei documenti?
Sì, GroupDocs.Viewer consente agli utenti di visualizzare e gestire le annotazioni dei documenti in modo efficiente.