---
"description": "Integra Groupdocs.Viewer per .NET in modo semplice nei tuoi progetti .NET per una visualizzazione efficiente dei documenti."
"linktitle": "Annulla rendering con token di annullamento"
"second_title": "API .NET di GroupDocs.Viewer"
"title": "Annulla rendering con token di annullamento"
"url": "/it/net/rendering-options/cancel-render-cancellation-token/"
"weight": 11
type: docs
---
# Annulla rendering con token di annullamento

## Introduzione
Groupdocs.Viewer per .NET è un potente strumento progettato per semplificare la visualizzazione e l'elaborazione dei documenti nelle applicazioni .NET. Che si tratti di PDF, documenti di Microsoft Office o altri formati comuni, questa libreria offre funzionalità affidabili per integrare perfettamente la visualizzazione dei documenti nei progetti .NET.
## Prerequisiti
Prima di immergerti nell'integrazione di Groupdocs.Viewer per .NET, assicurati di avere i seguenti prerequisiti:
1. Installazione: Scarica e installa la libreria Groupdocs.Viewer per .NET dal sito fornito [collegamento per il download](https://releases.groupdocs.com/viewer/net/).
   
2. Licenza: Ottieni una licenza da [Documenti di gruppo](https://purchase.groupdocs.com/buy) per sbloccare il pieno potenziale della libreria. In alternativa, puoi iniziare con una prova gratuita utilizzando [licenza temporanea](https://purchase.groupdocs.com/temporary-license/).
   
3. Ambiente di sviluppo: assicurati di aver configurato un ambiente di sviluppo compatibile, tra cui Visual Studio o qualsiasi altro IDE .NET di tua scelta.

## Importa spazi dei nomi
Per utilizzare Groupdocs.Viewer per .NET in modo efficace, è necessario importare gli spazi dei nomi necessari nel progetto. Seguire questi passaggi:

```csharp
using System;
using System.IO;
using GroupDocs.Viewer.Options;
using System.Threading.Tasks;
using System.Threading;
```

Ora, scomponiamo l'esempio fornito in più passaggi per una migliore comprensione e implementazione:
## Passaggio 1: definire la directory di output
```csharp
string outputDirectory = "Your Document Directory";
```
Questo passaggio imposta la directory in cui verranno archiviate le pagine del documento renderizzate.
## Passaggio 2: definire il formato del percorso del file di paging
```csharp
string pageFilePathFormat = Path.Combine(outputDirectory, "page_{0}.html");
```
Qui definiamo il formato per i percorsi dei file delle singole pagine del documento.
## Passaggio 3: inizializzare CancellationTokenSource
```csharp
CancellationTokenSource cancellationTokenSource = new CancellationTokenSource();
```
CancellationTokenSource viene utilizzato per generare istanze di CancellationToken che possono essere utilizzate per annullare operazioni asincrone.
## Passaggio 4: Ottieni CancellationToken
```csharp
CancellationToken cancellationToken = cancellationTokenSource.Token;
```
Questo passaggio recupera il token da CancellationTokenSource, che verrà utilizzato per annullare l'operazione di rendering.
## Passaggio 5: rendering delle pagine del documento
```csharp
Task.Run(() =>
{
    using (Viewer viewer = new Viewer(TestFiles.SAMPLE_DOCX, new ViewerSettings(new GroupDocs.Viewer.Logging.ConsoleLogger())))
    {
        HtmlViewOptions options = HtmlViewOptions.ForEmbeddedResources(pageFilePathFormat);
        options.RenderComments = true;
        viewer.View(options, cancellationToken);
    }
}, cancellationToken);
```
Qui, avviamo il rendering delle pagine del documento in modo asincrono utilizzando Task.Run(). L'istanza di Viewer viene creata con il file di documento specificato (SAMPLE_DOCX) e vengono configurate le opzioni di rendering. Il processo di rendering viene quindi avviato utilizzando il metodo View della classe Viewer.
## Passaggio 6: imposta il timeout di rendering
```csharp
cancellationTokenSource.CancelAfter(10);
```
Questo passaggio imposta un timeout di 10 millisecondi per l'operazione di rendering. Se l'operazione supera questo timeout, verrà automaticamente annullata.
## Passaggio 7: visualizzare il messaggio di successo
```csharp
Console.WriteLine($"\nSource document rendered successfully.\nCheck output in {outputDirectory}.");
```
Infine, viene visualizzato un messaggio di successo che indica che il documento è stato renderizzato correttamente.

## Conclusione
In questo tutorial abbiamo illustrato le basi dell'integrazione di Groupdocs.Viewer per .NET nei vostri progetti. Seguendo i passaggi descritti sopra, potrete integrare perfettamente le funzionalità di visualizzazione dei documenti nelle vostre applicazioni .NET, migliorando l'esperienza utente e la produttività.
## Domande frequenti
### Groupdocs.Viewer per .NET è compatibile con tutti i formati di documento?
Groupdocs.Viewer per .NET supporta un'ampia gamma di formati di documenti, tra cui PDF, documenti Microsoft Office, immagini e altro ancora.
### Posso personalizzare l'aspetto delle pagine del documento renderizzate?
Sì, puoi personalizzare vari aspetti del processo di rendering, tra cui le dimensioni della pagina, la qualità, la filigrana e altro ancora.
### Groupdocs.Viewer per .NET richiede la connettività Internet?
No, Groupdocs.Viewer per .NET funziona localmente all'interno del tuo ambiente .NET e non richiede connettività Internet per la visualizzazione dei documenti.
### È disponibile supporto tecnico per Groupdocs.Viewer per .NET?
Sì, il supporto tecnico è disponibile tramite [Forum di Groupdocs](https://forum.groupdocs.com/c/viewer/9), dove puoi porre domande, segnalare problemi e interagire con la community.
### Posso provare Groupdocs.Viewer per .NET prima di acquistarlo?
Sì, puoi iniziare con una prova gratuita utilizzando il servizio fornito [versione di prova](https://releases.groupdocs.com/).