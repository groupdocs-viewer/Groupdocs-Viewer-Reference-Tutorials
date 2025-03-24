---
title: Escludi caratteri dall'HTML renderizzato
linktitle: Escludi caratteri dall'HTML renderizzato
second_title: API GroupDocs.Viewer .NET
description: Scopri come escludere i caratteri dall'HTML sottoposto a rendering utilizzando GroupDocs.Viewer per .NET. Segui questa guida passo passo per visualizzare i documenti senza problemi.
weight: 10
url: /it/net/rendering-documents-html/exclude-fonts-html/
---
## introduzione
GroupDocs.Viewer per .NET è una potente libreria di rendering di documenti che consente agli sviluppatori di visualizzare oltre 50 formati di documenti nelle loro applicazioni .NET senza la necessità di dipendenze esterne. In questo tutorial, ci concentreremo su una funzionalità specifica di GroupDocs.Viewer: esclusione dei caratteri dall'output HTML renderizzato. 
## Prerequisiti
Prima di iniziare, assicurati di avere quanto segue:
1. Conoscenza di base dello sviluppo C# e .NET.
2.  GroupDocs.Viewer per .NET installato. Puoi scaricarlo da[Qui](https://releases.groupdocs.com/viewer/net/).
3. Visual Studio o qualsiasi altro IDE per lo sviluppo C#.

## Importa spazi dei nomi
Nel codice C# assicurati di includere gli spazi dei nomi necessari:
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
Specificare il formato per i percorsi dei file delle singole pagine del documento sottoposto a rendering.
```csharp
string pageFilePathFormat = Path.Combine(outputDirectory, "page_{0}.html");
```
## Passaggio 3: inizializzare l'oggetto visualizzatore
Crea un'istanza dell'oggetto Viewer con il documento di cui desideri eseguire il rendering.
```csharp
using (Viewer viewer = new Viewer("YourDocumentPath"))
{
    // Il tuo codice va qui
}
```
## Passaggio 4: imposta le opzioni di visualizzazione HTML
Definire le opzioni per il rendering HTML, incluso il formato delle risorse incorporate e i caratteri da escludere.
```csharp
HtmlViewOptions options = HtmlViewOptions.ForEmbeddedResources(pageFilePathFormat);
options.FontsToExclude.Add("Arial");
```
## Passaggio 5: rendering del documento
Passa le opzioni di visualizzazione HTML all'oggetto Viewer per eseguire il rendering del documento.
```csharp
viewer.View(options);
```
## Passaggio 6: output della posizione del documento renderizzato
Informare l'utente sulla posizione in cui vengono salvati i file HTML sottoposti a rendering.
```csharp
Console.WriteLine($"\nSource document rendered successfully.\nCheck output in {outputDirectory}.");
```

## Conclusione
In questo tutorial abbiamo imparato come utilizzare GroupDocs.Viewer per .NET per escludere i caratteri dall'output HTML sottoposto a rendering. Seguendo i passaggi sopra descritti, è possibile personalizzare il processo di rendering per soddisfare le proprie esigenze specifiche, garantendo una visualizzazione ottimale dei documenti nelle proprie applicazioni.
## Domande frequenti
### Posso escludere più caratteri dall'HTML renderizzato?
 Sì, puoi aggiungere più nomi di caratteri al file`FontsToExclude` elenco nelle opzioni di visualizzazione HTML.
### GroupDocs.Viewer è compatibile con tutti i framework .NET?
Sì, GroupDocs.Viewer supporta .NET Framework 4.6.1 e versioni successive.
### Posso eseguire il rendering di documenti da posizioni di archiviazione remote?
Sì, GroupDocs.Viewer supporta il rendering di documenti dall'archiviazione locale nonché da posizioni e flussi di archiviazione remoti.
### GroupDocs.Viewer supporta il design reattivo per l'output HTML?
Sì, puoi abilitare il rendering reattivo regolando di conseguenza le opzioni di visualizzazione HTML.
### È disponibile supporto tecnico per GroupDocs.Viewer?
 Sì, puoi chiedere assistenza e partecipare alle discussioni su[Forum GroupDocs.Viewer](https://forum.groupdocs.com/c/viewer/9).