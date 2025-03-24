---
title: Ottieni nomi di fogli di lavoro
linktitle: Ottieni nomi di fogli di lavoro
second_title: API GroupDocs.Viewer .NET
description: Esplora la magia di GroupDocs.Viewer per .NET integra perfettamente la visualizzazione dei documenti nelle tue applicazioni. Prova subito la prova gratuita!
weight: 11
url: /it/net/spreadsheet-rendering-options/get-worksheets-names/
---
## introduzione
Benvenuti nell'affascinante mondo di GroupDocs.Viewer per .NET! Se sei uno sviluppatore o un appassionato desideroso di esplorare potenti funzionalità di visualizzazione di documenti all'interno delle tue applicazioni .NET, sei pronto per una sorpresa. In questa guida completa, approfondiremo le complessità del recupero dei nomi dei fogli di lavoro utilizzando GroupDocs.Viewer. Quindi, allacciate la cintura di sicurezza e intraprendiamo questo emozionante viaggio!
## Prerequisiti
Prima di immergerci nella magia della codifica, assicuriamoci di aver impostato tutto:
1.  Installa GroupDocs.Viewer per .NET: vai al file[Link per scaricare](https://releases.groupdocs.com/viewer/net/)per prendere l'ultima versione di GroupDocs.Viewer per .NET. Segui le istruzioni di installazione per integrarlo perfettamente nel tuo ambiente di sviluppo.
2. Prepara il tuo documento: assicurati di avere un documento di destinazione, diciamo un file Excel denominato "file.xlsx", nella directory dei documenti designata.
## Importa spazi dei nomi
Ora che hai i prerequisiti, iniziamo importando gli spazi dei nomi necessari. Ciò garantisce che l'applicazione riconosca e possa utilizzare le funzionalità fornite da GroupDocs.Viewer per .NET.
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
In questo passaggio creiamo un'istanza della classe Viewer, fornendo il percorso del tuo file Excel.
## 3. Configurazione delle opzioni di visualizzazione delle informazioni
```csharp
ViewInfoOptions viewInfoOptions = ViewInfoOptions.ForHtmlView();
viewInfoOptions.SpreadsheetOptions = SpreadsheetOptions.ForOnePagePerSheet();
```
Qui configuriamo ViewInfoOptions per generare visualizzazioni HTML e impostare opzioni aggiuntive per il rendering del foglio di calcolo.
## 4. Recupero delle informazioni sulla vista
```csharp
ViewInfo viewInfo = viewer.GetViewInfo(viewInfoOptions);
```
Utilizza l'istanza del visualizzatore per recuperare le informazioni sulla visualizzazione in base alle opzioni configurate.
## 5. Visualizzazione dei nomi dei fogli di lavoro
```csharp
Console.WriteLine("Worksheets:");
foreach (Page page in viewInfo.Pages)
{
    Console.WriteLine($" - Worksheet {page.Number} name '{page.Name}'");
}
```
Sfoglia le pagine recuperate e stampa il nome di ciascun foglio di lavoro sulla console.
## Conclusione
Congratulazioni! Hai completato con successo il processo di recupero dei nomi dei fogli di lavoro utilizzando GroupDocs.Viewer per .NET. Ciò apre una miriade di possibilità per migliorare le funzionalità di visualizzazione dei documenti all'interno delle tue applicazioni.
## Domande frequenti
### Posso utilizzare GroupDocs.Viewer for .NET con altri formati di documenti?
Assolutamente! GroupDocs.Viewer supporta un'ampia gamma di formati di documenti, tra cui PDF, Microsoft Office e altri.
### È disponibile una prova gratuita?
 Sì, puoi esplorare GroupDocs.Viewer per .NET con il nostro[prova gratuita](https://releases.groupdocs.com/).
### Dove posso trovare ulteriore supporto?
 Dirigiti al[Forum GroupDocs.Viewer](https://forum.groupdocs.com/c/viewer/9) per il supporto e le discussioni della comunità.
### Posso ottenere una licenza temporanea?
 Certamente! Visita[questo link](https://purchase.groupdocs.com/temporary-license/) per ottenere la tua licenza temporanea.
### Sono disponibili risorse di documentazione dettagliate?
 Assolutamente! Dai un'occhiata a[documentazione ufficiale](https://tutorials.groupdocs.com/viewer/net/) per approfondimenti e guide.