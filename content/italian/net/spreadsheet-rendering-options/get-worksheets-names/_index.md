---
"description": "Scopri la magia di GroupDocs.Viewer per .NET&#58; integra perfettamente la visualizzazione dei documenti nelle tue applicazioni. Prova subito la versione di prova gratuita!"
"linktitle": "Ottieni i nomi dei fogli di lavoro"
"second_title": "API .NET di GroupDocs.Viewer"
"title": "Ottieni i nomi dei fogli di lavoro"
"url": "/it/net/spreadsheet-rendering-options/get-worksheets-names/"
"weight": 11
type: docs
---
# Ottieni i nomi dei fogli di lavoro

## Introduzione
Benvenuti nell'affascinante mondo di GroupDocs.Viewer per .NET! Se siete sviluppatori o appassionati desiderosi di esplorare le potenti funzionalità di visualizzazione dei documenti nelle vostre applicazioni .NET, vi aspetta una vera sorpresa. In questa guida completa, approfondiremo le complessità del recupero dei nomi dei fogli di lavoro utilizzando GroupDocs.Viewer. Quindi, allacciate le cinture e iniziamo questo entusiasmante viaggio!
## Prerequisiti
Prima di immergerci nella magia della codifica, assicuriamoci di aver impostato tutto:
1. Installa GroupDocs.Viewer per .NET: vai su [collegamento per il download](https://releases.groupdocs.com/viewer/net/) per scaricare l'ultima versione di GroupDocs.Viewer per .NET. Segui le istruzioni di installazione per integrarlo perfettamente nel tuo ambiente di sviluppo.
2. Prepara il documento: assicurati di avere un documento di destinazione, ad esempio un file Excel denominato "file.xlsx", nella directory dei documenti designata.
## Importa spazi dei nomi
Ora che hai soddisfatto i prerequisiti, iniziamo importando gli spazi dei nomi necessari. Questo garantirà che l'applicazione riconosca e possa utilizzare le funzionalità fornite da GroupDocs.Viewer per .NET.
```csharp
using System;
using System.IO;
using GroupDocs.Viewer.Options;
using GroupDocs.Viewer.Results;
```
## 1. Impostazione della directory dei documenti
```csharp
string outputDirectory = "Your Document Directory";
```
Sostituisci "Directory dei documenti" con il percorso della directory in cui si trova il documento di destinazione.
## 2. Inizializzazione del visualizzatore
```csharp
using (Viewer viewer = new Viewer(Path.Combine(outputDirectory, "file.xlsx")))
```
In questo passaggio creiamo un'istanza della classe Viewer, fornendo il percorso al file Excel.
## 3. Configurazione delle opzioni di visualizzazione delle informazioni
```csharp
ViewInfoOptions viewInfoOptions = ViewInfoOptions.ForHtmlView();
viewInfoOptions.SpreadsheetOptions = SpreadsheetOptions.ForOnePagePerSheet();
```
Qui configuriamo ViewInfoOptions per generare visualizzazioni HTML e impostiamo opzioni aggiuntive per il rendering del foglio di calcolo.
## 4. Recupero delle informazioni di visualizzazione
```csharp
ViewInfo viewInfo = viewer.GetViewInfo(viewInfoOptions);
```
Utilizzare l'istanza Viewer per recuperare le informazioni di visualizzazione in base alle opzioni configurate.
## 5. Visualizzazione dei nomi dei fogli di lavoro
```csharp
Console.WriteLine("Worksheets:");
foreach (Page page in viewInfo.Pages)
{
    Console.WriteLine($" - Worksheet {page.Number} name '{page.Name}'");
}
```
Scorrere le pagine recuperate e stampare il nome di ciascun foglio di lavoro sulla console.
## Conclusione
Congratulazioni! Hai completato con successo il processo di recupero dei nomi dei fogli di lavoro utilizzando GroupDocs.Viewer per .NET. Questo apre una miriade di possibilità per migliorare le funzionalità di visualizzazione dei documenti nelle tue applicazioni.
## Domande frequenti
### Posso utilizzare GroupDocs.Viewer per .NET con altri formati di documenti?
Assolutamente sì! GroupDocs.Viewer supporta un'ampia gamma di formati di documento, tra cui PDF, Microsoft Office e altri.
### È disponibile una prova gratuita?
Sì, puoi esplorare GroupDocs.Viewer per .NET con il nostro [prova gratuita](https://releases.groupdocs.com/).
### Dove posso trovare ulteriore supporto?
Dirigetevi verso il [Forum di GroupDocs.Viewer](https://forum.groupdocs.com/c/viewer/9) per il supporto e le discussioni della comunità.
### Posso ottenere una licenza temporanea?
Certamente! Visita [questo collegamento](https://purchase.groupdocs.com/temporary-license/) per ottenere la patente temporanea.
### Sono disponibili risorse di documentazione dettagliate?
Assolutamente! Dai un'occhiata al [documentazione ufficiale](https://tutorials.groupdocs.com/viewer/net/) per informazioni approfondite e guide.