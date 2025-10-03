---
"description": "Scopri come escludere i font dal codice HTML renderizzato utilizzando GroupDocs.Viewer per .NET. Segui questa guida passo passo per una visualizzazione impeccabile dei documenti."
"linktitle": "Escludi i font dall'HTML renderizzato"
"second_title": "API .NET di GroupDocs.Viewer"
"title": "Escludi i font dall'HTML renderizzato"
"url": "/it/net/rendering-documents-html/exclude-fonts-html/"
"weight": 10
type: docs
---
# Escludi i font dall'HTML renderizzato

## Introduzione
GroupDocs.Viewer per .NET è una potente libreria di rendering di documenti che consente agli sviluppatori di visualizzare oltre 50 formati di documento nelle loro applicazioni .NET senza la necessità di dipendenze esterne. In questo tutorial, ci concentreremo su una funzionalità specifica di GroupDocs.Viewer: l'esclusione dei font dall'output HTML renderizzato. 
## Prerequisiti
Prima di iniziare, assicurati di avere quanto segue:
1. Conoscenza di base dello sviluppo C# e .NET.
2. GroupDocs.Viewer per .NET installato. Puoi scaricarlo da [Qui](https://releases.groupdocs.com/viewer/net/).
3. Visual Studio o qualsiasi altro IDE per lo sviluppo C#.

## Importa spazi dei nomi
Nel codice C#, assicurati di includere gli spazi dei nomi necessari:
```csharp
using System;
using System.IO;
using GroupDocs.Viewer.Options;
```

## Passaggio 1: definire la directory di output
Imposta la directory in cui desideri salvare i file HTML renderizzati.
```csharp
string outputDirectory = "Your Document Directory";
```
## Passaggio 2: definire il formato del percorso del file di paging
Specificare il formato per i percorsi dei file delle singole pagine del documento renderizzato.
```csharp
string pageFilePathFormat = Path.Combine(outputDirectory, "page_{0}.html");
```
## Passaggio 3: inizializzare l'oggetto Viewer
Crea un'istanza dell'oggetto Viewer con il documento che vuoi visualizzare.
```csharp
using (Viewer viewer = new Viewer("YourDocumentPath"))
{
    // Il tuo codice va qui
}
```
## Passaggio 4: imposta le opzioni di visualizzazione HTML
Definisci le opzioni per il rendering HTML, incluso il formato delle risorse incorporate e i font da escludere.
```csharp
HtmlViewOptions options = HtmlViewOptions.ForEmbeddedResources(pageFilePathFormat);
options.FontsToExclude.Add("Arial");
```
## Passaggio 5: rendering del documento
Passare le opzioni di visualizzazione HTML all'oggetto Viewer per visualizzare il documento.
```csharp
viewer.View(options);
```
## Passaggio 6: posizione del documento renderizzato in output
Informa l'utente sulla posizione in cui vengono salvati i file HTML renderizzati.
```csharp
Console.WriteLine($"\nSource document rendered successfully.\nCheck output in {outputDirectory}.");
```

## Conclusione
In questo tutorial, abbiamo imparato come utilizzare GroupDocs.Viewer per .NET per escludere i font dall'output HTML renderizzato. Seguendo i passaggi descritti sopra, è possibile personalizzare il processo di rendering in base alle proprie esigenze specifiche, garantendo una visualizzazione ottimale dei documenti nelle applicazioni.
## Domande frequenti
### Posso escludere più font dall'HTML renderizzato?
Sì, puoi aggiungere più nomi di font al `FontsToExclude` elenco nelle opzioni di visualizzazione HTML.
### GroupDocs.Viewer è compatibile con tutti i framework .NET?
Sì, GroupDocs.Viewer supporta .NET Framework 4.6.1 e versioni successive.
### Posso eseguire il rendering di documenti da posizioni di archiviazione remote?
Sì, GroupDocs.Viewer supporta il rendering di documenti da archivi locali, nonché da posizioni di archiviazione remote e flussi.
### GroupDocs.Viewer supporta il design responsivo per l'output HTML?
Sì, puoi abilitare il rendering reattivo modificando di conseguenza le opzioni di visualizzazione HTML.
### È disponibile supporto tecnico per GroupDocs.Viewer?
Sì, puoi richiedere assistenza e partecipare alle discussioni su [Forum di GroupDocs.Viewer](https://forum.groupdocs.com/c/viewer/9).