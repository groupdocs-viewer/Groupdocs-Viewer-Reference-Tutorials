---
"description": "Scopri come abilitare il rendering a livelli nei documenti PDF utilizzando GroupDocs.Viewer per .NET. Migliora l'esperienza di visualizzazione dei documenti senza sforzo."
"linktitle": "Abilita il rendering a strati in PDF"
"second_title": "API .NET di GroupDocs.Viewer"
"title": "Abilita il rendering a strati in PDF"
"url": "/it/net/pdf-rendering-options/enable-layered-rendering-pdf/"
"weight": 15
---

# Abilita il rendering a strati in PDF

## Introduzione
In questo tutorial, approfondiremo il processo di abilitazione del rendering a livelli nei documenti PDF utilizzando GroupDocs.Viewer per .NET. Il rendering a livelli consente una visualizzazione e una manipolazione ottimizzate dei documenti, offrendo agli utenti un'esperienza di visualizzazione più interattiva.

![Abilita il rendering a strati in PDF con GroupDocs.Viewer .NET](/viewer/pdf-rendering-options/enable-layered-rendering-in-pdf.png)

## Prerequisiti
Prima di iniziare, assicurati di avere i seguenti prerequisiti:
1. GroupDocs.Viewer per .NET: assicurati di aver installato il pacchetto o la libreria necessari per utilizzare GroupDocs.Viewer per .NET nel tuo progetto.
2. Visual Studio: per scrivere il codice ed eseguire gli esempi forniti, è necessario che Visual Studio sia installato sul sistema.
3. Nozioni di base di C#: questo tutorial presuppone la familiarità con la sintassi e i concetti del linguaggio di programmazione C#.

## Importa spazi dei nomi
Inizia importando gli spazi dei nomi richiesti nel tuo progetto:
```csharp
using System;
using System.IO;
using GroupDocs.Viewer.Options;
```
## Passaggio 1: definire la directory di output
```csharp
string outputDirectory = "Your Document Directory";
```
Assicurati di specificare il percorso della directory in cui desideri salvare l'output renderizzato.
## Passaggio 2: definire il formato del percorso del file di paging
```csharp
string pageFilePathFormat = Path.Combine(outputDirectory, "page_{0}.html");
```
Questo passaggio imposta il formato per i percorsi dei file delle singole pagine nell'output renderizzato. `{0}` è un segnaposto per il numero di pagina.
## Passaggio 3: abilitare il rendering a strati
```csharp
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_PDF))
{
    HtmlViewOptions options = HtmlViewOptions.ForEmbeddedResources(pageFilePathFormat);
    options.PdfOptions.EnableLayeredRendering = true;
    viewer.View(options, 1);
}
```
Qui creiamo un `Viewer` oggetto e specificare il documento PDF da elaborare. Quindi configuriamo `HtmlViewOptions` con il formato del percorso del file di paging definito. Impostando `EnableLayeredRendering` proprietà a `true` In `PdfOptions`, abilitiamo il rendering a livelli per il documento PDF.
## Passaggio 4: visualizzare la directory di output
```csharp
Console.WriteLine($"\nSource document rendered successfully.\nCheck output in {outputDirectory}.");
```
Infine, stampiamo un messaggio che indica l'avvenuto rendering del documento sorgente e chiediamo all'utente di controllare l'output nella directory specificata.

## Conclusione
Abilitare il rendering a livelli nei documenti PDF utilizzando GroupDocs.Viewer per .NET migliora le capacità di visualizzazione dei documenti, offrendo agli utenti un'esperienza più ricca e interattiva. Seguendo i passaggi descritti in questo tutorial, è possibile integrare perfettamente questa funzionalità nelle applicazioni .NET.
## Domande frequenti
### Cos'è il rendering a livelli nei documenti PDF?
Il rendering a strati consente la separazione e la manipolazione di diversi componenti all'interno di un documento PDF, consentendo una visualizzazione interattiva e un'esperienza utente migliorata.
### Posso personalizzare la directory di output per i documenti renderizzati?
Sì, puoi specificare qualsiasi percorso di directory per l'output in base alle tue esigenze.
### GroupDocs.Viewer supporta altri formati di file oltre al PDF?
Sì, GroupDocs.Viewer supporta un'ampia gamma di formati di documenti, tra cui Word, Excel, PowerPoint e altri.
### GroupDocs.Viewer è compatibile con .NET Core?
Sì, GroupDocs.Viewer è compatibile sia con gli ambienti .NET Framework che .NET Core.
### Dove posso trovare ulteriore supporto o assistenza?
Per qualsiasi domanda o assistenza riguardante la libreria del visualizzatore, puoi visitare il forum di GroupDocs.Viewer.