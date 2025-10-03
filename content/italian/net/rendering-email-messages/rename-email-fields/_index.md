---
"description": "Migliora l'esperienza di visualizzazione dei documenti con GroupDocs.Viewer per .NET. Visualizza e personalizza le email in modo impeccabile."
"linktitle": "Rinomina i campi e-mail durante il rendering"
"second_title": "API .NET di GroupDocs.Viewer"
"title": "Rinomina i campi e-mail durante il rendering"
"url": "/it/net/rendering-email-messages/rename-email-fields/"
"weight": 12
type: docs
---
# Rinomina i campi e-mail durante il rendering

## Introduzione

Nell'era digitale odierna, gestire e visualizzare i documenti in modo efficiente è fondamentale sia per le aziende che per i privati. Che si tratti di contratti, report o email, la possibilità di navigare agevolmente tra questi documenti può migliorare notevolmente la produttività. È qui che entra in gioco GroupDocs.Viewer per .NET. Questa potente libreria consente agli sviluppatori di integrare le funzionalità di visualizzazione dei documenti direttamente nelle loro applicazioni .NET, offrendo un'ampia gamma di funzionalità per il rendering di vari formati di documento.

## Prerequisiti

Prima di immergerti nel tutorial sulla ridenominazione dei campi email durante il rendering utilizzando GroupDocs.Viewer per .NET, assicurati di disporre dei seguenti prerequisiti:

1. Libreria GroupDocs.Viewer per .NET: Scarica e installa la libreria GroupDocs.Viewer per .NET da [Qui](https://releases.groupdocs.com/viewer/net/).

2. Ambiente di sviluppo: assicurati di avere configurato un ambiente di sviluppo adatto per lo sviluppo .NET, come Visual Studio.

3. Nozioni di base di C#: familiarizzare con le basi del linguaggio di programmazione C# poiché il tutorial utilizzerà frammenti di codice C#.

4. Directory dei documenti: preparare una directory in cui archiviare i documenti da riprodurre.

## Importa spazi dei nomi

Per utilizzare le funzionalità di GroupDocs.Viewer nella tua applicazione .NET, devi importare gli spazi dei nomi necessari.

```csharp
using System;
using System.IO;
using GroupDocs.Viewer.Options;
```

Ora scomponiamo il processo di ridenominazione dei campi email durante il rendering utilizzando GroupDocs.Viewer per .NET in più passaggi:

## Passaggio 1: definire la directory di output

Per prima cosa, specifica la directory in cui verranno salvate le pagine HTML renderizzate.

```csharp
string outputDirectory = "Your Document Directory";
```

## Passaggio 2: definire il formato del percorso del file di paging

Definisci il formato per i percorsi dei file delle pagine HTML renderizzate. Ogni pagina verrà salvata come file HTML separato.

```csharp
string pageFilePathFormat = Path.Combine(outputDirectory, "page_{0}.html");
```

## Passaggio 3: inizializzare l'oggetto Viewer

Creare un'istanza della classe Viewer e passare come parametro il percorso del documento da visualizzare.

```csharp
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_MSG))
{
```

## Passaggio 4: configurare le opzioni di visualizzazione HTML

Configura le opzioni per la visualizzazione HTML, inclusa la specifica del formato del file di output e l'impostazione delle mappature dei campi e-mail.

```csharp
HtmlViewOptions options = HtmlViewOptions.ForEmbeddedResources(pageFilePathFormat);
options.EmailOptions.FieldTextMap[Field.From] = "Sender";
options.EmailOptions.FieldTextMap[Field.To] = "Receiver";
options.EmailOptions.FieldTextMap[Field.Sent] = "Date";
options.EmailOptions.FieldTextMap[Field.Subject] = "Topic";
```

## Passaggio 5: rendering del documento

Richiama il metodo View dell'oggetto Viewer, passando le opzioni di visualizzazione HTML configurate.

```csharp
viewer.View(options);
```

## Passaggio 6: visualizzare il messaggio di successo

Informare l'utente che il documento è stato renderizzato correttamente.

```csharp
Console.WriteLine($"\nSource document rendered successfully.\nCheck output in {outputDirectory}.");
```

## Conclusione

In conclusione, GroupDocs.Viewer per .NET offre una soluzione completa per il rendering dei documenti all'interno delle applicazioni .NET. Seguendo i passaggi descritti in questo tutorial, è possibile rinominare facilmente i campi email durante il rendering, migliorando la leggibilità e l'usabilità dei documenti email. Grazie alla sua API intuitiva e alle sue funzionalità complete, GroupDocs.Viewer consente agli sviluppatori di semplificare efficacemente i processi di visualizzazione dei documenti.

## Domande frequenti

### D: Posso visualizzare documenti diversi dalle e-mail utilizzando GroupDocs.Viewer per .NET?

R: Sì, GroupDocs.Viewer supporta il rendering di vari formati di documenti, tra cui PDF, documenti Microsoft Office, immagini e altro ancora.

### D: GroupDocs.Viewer è compatibile con .NET Core?

R: Sì, GroupDocs.Viewer supporta .NET Core oltre al tradizionale .NET Framework.

### D: Posso personalizzare l'aspetto dei documenti renderizzati?

R: Assolutamente sì, GroupDocs.Viewer offre ampie possibilità di personalizzazione per controllare l'aspetto e il comportamento dei documenti renderizzati.

### D: GroupDocs.Viewer supporta lo streaming di documenti?

R: Sì, GroupDocs.Viewer consente lo streaming di documenti direttamente sul browser del cliente senza la necessità di memorizzarli sul server.

### D: GroupDocs.Viewer è adatto alle applicazioni di livello aziendale?

R: Certamente, GroupDocs.Viewer è progettato per soddisfare le esigenze delle applicazioni di livello aziendale grazie alla sua scalabilità, affidabilità e al suo robusto set di funzionalità.