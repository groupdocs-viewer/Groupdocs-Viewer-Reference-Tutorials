---
"description": "Scopri come ottimizzare le dimensioni e la qualità delle immagini in formato JPEG utilizzando Groupdocs.Viewer per .NET. Migliora la tua esperienza di visualizzazione dei documenti."
"linktitle": "Regola le dimensioni e la qualità dell'immagine (JPG)"
"second_title": "API .NET di GroupDocs.Viewer"
"title": "Regola le dimensioni e la qualità dell'immagine (JPG)"
"url": "/it/net/rendering-documents-images/adjust-image-size-and-quality-jpg/"
"weight": 11
---

# Regola le dimensioni e la qualità dell'immagine (JPG)

## Introduzione
Groupdocs.Viewer per .NET è una potente libreria che consente agli sviluppatori di integrare perfettamente le funzionalità di visualizzazione dei documenti nelle loro applicazioni .NET. Un requisito comune nelle applicazioni di visualizzazione dei documenti è la possibilità di regolare le dimensioni e la qualità delle immagini, in particolare quando si tratta di immagini JPEG (JPG). In questo tutorial, vi guideremo attraverso il processo di regolazione delle dimensioni e della qualità delle immagini utilizzando Groupdocs.Viewer per .NET.
## Prerequisiti
Prima di iniziare, assicurati di avere quanto segue:
1. Conoscenza di base del linguaggio di programmazione C#.
2. Visual Studio installato sul sistema.
3. Libreria Groupdocs.Viewer per .NET installata. Puoi scaricarla da [Qui](https://releases.groupdocs.com/viewer/net/).

## Importa spazi dei nomi
Per prima cosa, devi importare gli spazi dei nomi necessari nel codice C#. Questi spazi dei nomi forniscono l'accesso alle classi e ai metodi necessari per lavorare con Groupdocs.Viewer.
## Passaggio 1: importare gli spazi dei nomi
```csharp
using System;
using System.IO;
using GroupDocs.Viewer.Options;
```

Ora, per una migliore comprensione, scomponiamo il codice di esempio fornito in più passaggi.
## Passaggio 2: impostare la directory di output e il formato del percorso del file di paging
```csharp
string outputDirectory = "Your Document Directory";
string pageFilePathFormat = Path.Combine(outputDirectory, "page_{0}.jpg");
```
In questo passaggio specifichiamo la directory di output in cui verranno salvate le immagini renderizzate e definiamo il formato per il percorso del file di ciascuna immagine di pagina.
## Passaggio 3: inizializzare il visualizzatore e configurare le opzioni di visualizzazione JPG
```csharp
using (Viewer viewer = new Viewer("Your Document Path"))
{
    JpgViewOptions options = new JpgViewOptions(pageFilePathFormat);
    options.Width = 600;
    options.Height = 800;
    viewer.View(options);
}
```
Qui, inizializziamo l'oggetto Viewer con il percorso del documento da visualizzare. Quindi, creiamo un'istanza di JpgViewOptions e impostiamo la larghezza e l'altezza desiderate per le immagini JPEG.
## Passaggio 4: rendering del documento sorgente
```csharp
Console.WriteLine($"\nSource document rendered successfully.\nCheck output in {outputDirectory}.");
```
Infine, stampiamo un messaggio che indica l'avvenuto rendering del documento sorgente e la posizione in cui sono state salvate le immagini di output.

## Conclusione
In questo tutorial abbiamo imparato come regolare le dimensioni e la qualità delle immagini JPEG utilizzando Groupdocs.Viewer per .NET. Seguendo i passaggi descritti sopra, è possibile integrare facilmente questa funzionalità nelle applicazioni .NET, offrendo agli utenti un'esperienza di visualizzazione delle immagini ottimizzata.
## Domande frequenti
### Posso regolare anche la qualità dell'immagine?
Sì, puoi regolare la qualità dell'immagine impostando la proprietà Qualità in JpgViewOptions.
### Quali formati di documento sono supportati da Groupdocs.Viewer per .NET?
Groupdocs.Viewer per .NET supporta un'ampia gamma di formati di documenti, tra cui DOCX, PDF, PPTX, XLSX e altri.
### Groupdocs.Viewer per .NET è compatibile con .NET Core?
Sì, Groupdocs.Viewer per .NET è compatibile con .NET Core e con il tradizionale .NET Framework.
### Posso personalizzare il formato di denominazione del file di output?
Sì, puoi personalizzare il formato di denominazione del file di output modificando la variabile pageFilePathFormat nel codice.
### Groupdocs.Viewer per .NET supporta le annotazioni nei documenti?
Sì, Groupdocs.Viewer per .NET fornisce un supporto completo per le annotazioni dei documenti, tra cui evidenziazione del testo, sottolineatura e commenti.