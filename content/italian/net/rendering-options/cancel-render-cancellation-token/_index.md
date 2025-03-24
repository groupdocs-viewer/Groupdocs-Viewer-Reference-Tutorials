---
title: Annulla il rendering con il token di annullamento
linktitle: Annulla il rendering con il token di annullamento
second_title: API GroupDocs.Viewer .NET
description: Integra Groupdocs.Viewer for .NET perfettamente nei tuoi progetti .NET per una visualizzazione efficiente dei documenti.
weight: 11
url: /it/net/rendering-options/cancel-render-cancellation-token/
---
## introduzione
Groupdocs.Viewer per .NET è un potente strumento progettato per semplificare la visualizzazione e l'elaborazione dei documenti all'interno delle applicazioni .NET. Che tu abbia a che fare con PDF, documenti Microsoft Office o altri formati comuni, questa libreria offre funzionalità affidabili per integrare perfettamente le funzionalità di visualizzazione dei documenti nei tuoi progetti .NET.
## Prerequisiti
Prima di immergerti nell'integrazione di Groupdocs.Viewer per .NET, assicurati di disporre dei seguenti prerequisiti:
1.  Installazione: scaricare e installare la libreria Groupdocs.Viewer per .NET dalla libreria fornita[Link per scaricare](https://releases.groupdocs.com/viewer/net/).
   
2.  Licenza: ottieni una licenza da[Documenti di gruppo](https://purchase.groupdocs.com/buy) per sfruttare appieno il potenziale della biblioteca. In alternativa, puoi iniziare con una prova gratuita utilizzando il[licenza temporanea](https://purchase.groupdocs.com/temporary-license/).
   
3. Ambiente di sviluppo: assicurati di disporre di un ambiente di sviluppo compatibile, incluso Visual Studio o qualsiasi altro IDE .NET di tua scelta.

## Importa spazi dei nomi
Per utilizzare Groupdocs.Viewer for .NET in modo efficace, è necessario importare gli spazi dei nomi necessari nel progetto. Segui questi passi:

```csharp
using System;
using System.IO;
using GroupDocs.Viewer.Options;
using System.Threading.Tasks;
using System.Threading;
```

Ora suddividiamo l'esempio fornito in più passaggi per una migliore comprensione e implementazione:
## Passaggio 1: definire la directory di output
```csharp
string outputDirectory = "Your Document Directory";
```
Questo passaggio imposta la directory in cui verranno archiviate le pagine del documento sottoposto a rendering.
## Passaggio 2: definire il formato del percorso del file di paging
```csharp
string pageFilePathFormat = Path.Combine(outputDirectory, "page_{0}.html");
```
Qui definiamo il formato per i percorsi dei file delle singole pagine del documento.
## Passaggio 3: inizializza CancellationTokenSource
```csharp
CancellationTokenSource cancellationTokenSource = new CancellationTokenSource();
```
CancellationTokenSource viene utilizzato per generare istanze CancellationToken che possono essere utilizzate per annullare operazioni asincrone.
## Passaggio 4: ottieni CancellationToken
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
Qui, avviamo il rendering delle pagine del documento in modo asincrono utilizzando Task.Run(). L'istanza del visualizzatore viene creata con il file di documento specificato (SAMPLE_DOCX) e le opzioni di rendering vengono configurate. Il processo di rendering viene quindi avviato utilizzando il metodo View della classe Viewer.
## Passaggio 6: impostare il timeout del rendering
```csharp
cancellationTokenSource.CancelAfter(10);
```
Questo passaggio imposta un timeout di 10 millisecondi per l'operazione di rendering. Se l'operazione supera questo timeout, verrà automaticamente annullata.
## Passaggio 7: Visualizza il messaggio di successo
```csharp
Console.WriteLine($"\nSource document rendered successfully.\nCheck output in {outputDirectory}.");
```
Infine, viene visualizzato un messaggio di successo che indica che il rendering del documento è stato eseguito correttamente.

## Conclusione
In questo tutorial abbiamo trattato le nozioni di base per l'integrazione di Groupdocs.Viewer per .NET nei tuoi progetti. Seguendo i passaggi sopra descritti, puoi incorporare perfettamente funzionalità di visualizzazione dei documenti nelle tue applicazioni .NET, migliorando l'esperienza utente e la produttività.
## Domande frequenti
### Groupdocs.Viewer per .NET è compatibile con tutti i formati di documenti?
Groupdocs.Viewer per .NET supporta un'ampia gamma di formati di documenti, inclusi PDF, documenti di Microsoft Office, immagini e altro ancora.
### Posso personalizzare l'aspetto delle pagine del documento sottoposto a rendering?
Sì, puoi personalizzare vari aspetti del processo di rendering, tra cui dimensioni della pagina, qualità, filigrana e altro.
### Groupdocs.Viewer per .NET richiede la connettività Internet?
No, Groupdocs.Viewer per .NET funziona localmente all'interno del tuo ambiente .NET e non richiede connettività Internet per la visualizzazione dei documenti.
### È disponibile il supporto tecnico per Groupdocs.Viewer per .NET?
 Sì, il supporto tecnico è disponibile tramite[Forum dei documenti di gruppo](https://forum.groupdocs.com/c/viewer/9), dove puoi porre domande, segnalare problemi e interagire con la community.
### Posso provare Groupdocs.Viewer per .NET prima dell'acquisto?
 Sì, puoi iniziare con una prova gratuita utilizzando il servizio fornito[versione di prova](https://releases.groupdocs.com/).