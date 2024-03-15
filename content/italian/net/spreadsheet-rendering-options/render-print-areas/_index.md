---
title: Rendering di aree di stampa con GroupDocs.Viewer per .NET
linktitle: Rendering delle aree di stampa
second_title: API GroupDocs.Viewer .NET
description: Esplora GroupDocs.Viewer per .NET ed esegui il rendering senza sforzo di aree di stampa in vari formati di documenti. Prova subito la prova gratuita! #GroupDocs.Visualizzatore
type: docs
weight: 17
url: /it/net/spreadsheet-rendering-options/render-print-areas/
---
## introduzione
Benvenuti in questa guida completa su come sfruttare GroupDocs.Viewer per .NET per eseguire il rendering delle aree di stampa nei documenti. Se sei uno sviluppatore .NET alla ricerca di una soluzione solida per il rendering dei documenti, sei nel posto giusto. In questo tutorial ti guideremo attraverso il processo di rendering delle aree di stampa utilizzando GroupDocs.Viewer, garantendo un'esperienza senza interruzioni nelle tue applicazioni.
## Prerequisiti
Prima di immergerti nel tutorial, assicurati di disporre dei seguenti prerequisiti:
- Una conoscenza pratica dello sviluppo C# e .NET.
-  GroupDocs.Viewer per .NET installato. Puoi scaricarlo[Qui](https://releases.groupdocs.com/viewer/net/).
- Un documento di esempio (ad esempio, "SAMPLE.XLSX") nella directory dei documenti specificata.
## Importa spazi dei nomi
Assicurati di importare gli spazi dei nomi necessari nel codice C# per una corretta implementazione:
```csharp
using System;
using System.IO;
using GroupDocs.Viewer.Options;
```
## Passaggio 1: impostare la directory dei documenti
Inizia specificando la directory di output per le pagine HTML renderizzate:
```csharp
string outputDirectory = "Your Document Directory";
```
## Passaggio 2: definire il formato del percorso del file di paging
Crea un formato per i percorsi dei file di pagina, combinando la directory di output e un segnaposto per il numero di pagina:
```csharp
string pageFilePathFormat = Path.Combine(outputDirectory, "page_{0}.html");
```
## Passaggio 3: inizializzare GroupDocs.Viewer
Crea un'istanza della classe Viewer con il percorso del tuo documento di esempio:
```csharp
using (Viewer viewer = new Viewer("SAMPLE.XLSX"))
{
```
## Passaggio 4: configura le opzioni di visualizzazione HTML
Configura le opzioni di visualizzazione HTML, specificando il formato del percorso del file di pagina e abilitando le opzioni per il rendering delle aree di stampa:
```csharp
HtmlViewOptions options = HtmlViewOptions.ForEmbeddedResources(pageFilePathFormat);
options.SpreadsheetOptions = SpreadsheetOptions.ForRenderingPrintArea();
```
## Passaggio 5: rendering del documento
 Invocare il`View` metodo per eseguire il rendering del documento con le opzioni specificate:
```csharp
viewer.View(options);
```
## Passaggio 6: Visualizza il messaggio di successo
Stampa un messaggio di successo, indicando che il rendering del documento sorgente è stato eseguito correttamente:
```csharp
Console.WriteLine($"\nSource document rendered successfully.\nCheck output in {outputDirectory}.");
```
## Conclusione
Congratulazioni! Hai imparato con successo come utilizzare GroupDocs.Viewer per .NET per eseguire il rendering delle aree di stampa nei tuoi documenti. Questo potente strumento apre nuove possibilità per il rendering dei documenti nelle tue applicazioni .NET.
## Domande frequenti
### GroupDocs.Viewer è compatibile con diversi formati di documenti?
 Sì, GroupDocs.Viewer supporta un'ampia gamma di formati di documenti, inclusi PDF, DOCX, XLSX e altri. Fare riferimento al[documentazione](https://reference.groupdocs.com/viewer/net/) per un elenco completo.
### Posso provare GroupDocs.Viewer prima di effettuare un acquisto?
 Assolutamente! Puoi esplorare lo strumento con una prova gratuita disponibile[Qui](https://releases.groupdocs.com/).
### Dove posso trovare supporto o chiedere assistenza per eventuali problemi?
 Visitare il[Forum GroupDocs.Viewer](https://forum.groupdocs.com/c/viewer/9)per connettersi con la comunità e ottenere assistenza.
### È disponibile un'opzione di licenza temporanea?
 Sì, puoi ottenere una licenza temporanea[Qui](https://purchase.groupdocs.com/temporary-license/).
### Dove posso acquistare GroupDocs.Viewer per .NET?
 Puoi effettuare il tuo acquisto[Qui](https://purchase.groupdocs.com/buy).