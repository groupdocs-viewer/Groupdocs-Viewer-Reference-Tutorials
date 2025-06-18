---
"description": "Integra GroupDocs.Viewer per .NET in modo semplice e intuitivo nelle tue applicazioni per ottenere potenti funzionalità di visualizzazione dei documenti. Migliora l'esperienza utente con opzioni personalizzabili."
"linktitle": "Imposta il formato data/ora e l'offset del fuso orario (e-mail)"
"second_title": "API .NET di GroupDocs.Viewer"
"title": "Imposta il formato data/ora e l'offset del fuso orario (e-mail)"
"url": "/it/net/rendering-email-messages/set-date-time-format-offset-email/"
"weight": 11
---

# Imposta il formato data/ora e l'offset del fuso orario (e-mail)


## Introduzione
GroupDocs.Viewer per .NET è un potente strumento che consente agli sviluppatori di integrare perfettamente le funzionalità di visualizzazione dei documenti nelle loro applicazioni .NET. Con GroupDocs.Viewer, è possibile visualizzare un'ampia gamma di formati di documento, inclusi PDF, documenti di Microsoft Office, immagini e altro ancora, direttamente all'interno dell'applicazione, senza la necessità di plugin o visualizzatori esterni. In questo tutorial completo, vi guideremo attraverso il processo di configurazione di GroupDocs.Viewer per .NET, esplorandone le funzionalità e mostrandovi come utilizzarlo efficacemente per migliorare le funzionalità di visualizzazione dei documenti della vostra applicazione.
## Prerequisiti
Prima di immergerti in questo tutorial, assicurati di aver impostato i seguenti prerequisiti:
1. Visual Studio: assicurati di avere Visual Studio installato sul tuo sistema. GroupDocs.Viewer per .NET è pienamente compatibile con Visual Studio, consentendo una perfetta integrazione nei tuoi progetti .NET.
2. GroupDocs.Viewer per .NET: Scarica e installa GroupDocs.Viewer per .NET da [collegamento per il download](https://releases.groupdocs.com/viewer/net/)Seguire le istruzioni di installazione fornite per configurare la libreria nel proprio ambiente di sviluppo.
3. .NET Framework: assicurarsi di aver installato la versione appropriata di .NET Framework. GroupDocs.Viewer per .NET supporta diverse versioni di .NET Framework, tra cui .NET Core e .NET Standard.

## Importa spazi dei nomi
Per utilizzare GroupDocs.Viewer per .NET in modo efficace, è necessario importare gli spazi dei nomi necessari nel progetto. Seguire questi passaggi per importare gli spazi dei nomi richiesti:

```csharp
using System;
using System.IO;
using GroupDocs.Viewer.Options;
```


Per comprendere meglio ciascun componente e le sue funzionalità, scomponiamo l'esempio fornito in più passaggi.
## Passaggio 1: impostare la directory di output e il percorso del file
```csharp
string outputDirectory = "Your Document Directory";
string filePath = Path.Combine(outputDirectory, "output.html");
```
In questo passaggio definiamo la directory di output in cui verrà salvato il documento renderizzato e specifichiamo il percorso del file HTML di output.
## Passaggio 2: creare un'istanza dell'oggetto Viewer
```csharp
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_EML))
```
Qui creiamo una nuova istanza di `Viewer` classe, passando come parametro il percorso del documento da visualizzare (in questo caso, un file EML di esempio).
## Passaggio 3: definire le opzioni di visualizzazione HTML
```csharp
HtmlViewOptions options = HtmlViewOptions.ForEmbeddedResources(filePath);
```
In questa fase configuriamo le opzioni di visualizzazione HTML per il rendering del documento, specificando il percorso del file di output per il documento HTML renderizzato.
## Passaggio 4: impostare il formato data/ora e l'offset del fuso orario
```csharp
options.EmailOptions.DateTimeFormat = "MM d yyyy HH:mm tt zzz";
options.EmailOptions.TimeZoneOffset = new TimeSpan(1, 0, 0);
```
Qui personalizziamo il formato di data e ora per i messaggi di posta elettronica e impostiamo la differenza di fuso orario in base al fuso orario desiderato.
## Passaggio 5: rendering del documento
```csharp
viewer.View(options);
```
Infine, chiamiamo il `View` metodo del `Viewer` oggetto, passando le opzioni di visualizzazione HTML configurate per rendere il documento in formato HTML.
## Passaggio 6: visualizzare la directory di output
```csharp
Console.WriteLine($"\nSource document rendered successfully.\nCheck output in {outputDirectory}.");
```
Questo passaggio visualizza semplicemente un messaggio che indica l'avvenuto rendering del documento e fornisce il percorso alla directory di output in cui si trova il documento HTML renderizzato.

## Conclusione
GroupDocs.Viewer per .NET offre una soluzione affidabile per integrare le funzionalità di visualizzazione dei documenti nelle applicazioni .NET. Seguendo i passaggi descritti in questo tutorial, è possibile configurare facilmente GroupDocs.Viewer, importare gli spazi dei nomi necessari e utilizzare le sue funzionalità per visualizzare i documenti con opzioni personalizzabili. Che si lavori con PDF, documenti di Microsoft Office o altri formati, GroupDocs.Viewer semplifica il processo di visualizzazione dei documenti, migliorando l'esperienza utente delle applicazioni.
## Domande frequenti
### GroupDocs.Viewer è compatibile con .NET Core?
Sì, GroupDocs.Viewer per .NET supporta .NET Core, consentendo la compatibilità multipiattaforma per le tue applicazioni.
### Posso personalizzare l'aspetto dei documenti renderizzati?
Assolutamente sì! GroupDocs.Viewer offre diverse opzioni di personalizzazione, tra cui livelli di zoom, rotazione delle pagine e altro ancora, per personalizzare l'esperienza di visualizzazione in base alle tue esigenze.
### Esiste una versione di prova disponibile per scopi di test?
Sì, puoi scaricare una versione di prova gratuita di GroupDocs.Viewer per .NET da [collegamento al sito web](https://releases.groupdocs.com/viewer/net/) per valutarne le caratteristiche prima di procedere all'acquisto.
### GroupDocs.Viewer supporta il rendering di documenti protetti da password?
Sì, GroupDocs.Viewer supporta in modo integrato la visualizzazione di documenti protetti da password, garantendone la visualizzazione sicura all'interno delle applicazioni.
### Dove posso trovare ulteriore supporto o assistenza per GroupDocs.Viewer?
Per qualsiasi domanda tecnica o assistenza, puoi visitare GroupDocs.Viewer [foro](https://forum.groupdocs.com/c/viewer/9) oppure contatta il loro team di supporto per ricevere assistenza e indicazioni immediate.