---
title: Rinominare i campi email durante il rendering
linktitle: Rinominare i campi email durante il rendering
second_title: API GroupDocs.Viewer .NET
description: Migliora l'esperienza di visualizzazione dei documenti con GroupDocs.Viewer per .NET. Visualizza e personalizza le email senza problemi.
type: docs
weight: 12
url: /it/net/rendering-email-messages/rename-email-fields/
---
## introduzione

Nell'era digitale di oggi, gestire e visualizzare i documenti in modo efficiente è fondamentale sia per le aziende che per i privati. Che si tratti di contratti, report o e-mail, avere la possibilità di navigare tra questi documenti senza problemi può migliorare notevolmente la produttività. È qui che entra in gioco GroupDocs.Viewer per .NET. Questa potente libreria consente agli sviluppatori di integrare funzionalità di visualizzazione dei documenti direttamente nelle loro applicazioni .NET, offrendo un'ampia gamma di funzionalità per il rendering di vari formati di documenti.

## Prerequisiti

Prima di immergerti nel tutorial sulla ridenominazione dei campi email durante il rendering utilizzando GroupDocs.Viewer per .NET, assicurati di avere i seguenti prerequisiti:

1.  Libreria GroupDocs.Viewer per .NET: scaricare e installare la libreria GroupDocs.Viewer per .NET da[Qui](https://releases.groupdocs.com/viewer/net/).

2. Ambiente di sviluppo: assicurati di disporre di un ambiente di sviluppo adatto configurato per lo sviluppo .NET, come Visual Studio.

3. Comprensione di base di C#: acquisisci familiarità con le basi del linguaggio di programmazione C# poiché il tutorial coinvolgerà frammenti di codice C#.

4. Directory dei documenti: preparare una directory in cui sono archiviati i documenti da sottoporre a rendering.

## Importa spazi dei nomi

Per utilizzare le funzionalità GroupDocs.Viewer nella tua applicazione .NET, devi importare gli spazi dei nomi necessari.

```csharp
using System;
using System.IO;
using GroupDocs.Viewer.Options;
```

Ora suddividiamo il processo di ridenominazione dei campi email durante il rendering utilizzando GroupDocs.Viewer for .NET in più passaggi:

## Passaggio 1: definire la directory di output

Innanzitutto, specifica la directory in cui verranno salvate le pagine HTML renderizzate.

```csharp
string outputDirectory = "Your Document Directory";
```

## Passaggio 2: definire il formato del percorso del file di paging

Definire il formato per i percorsi dei file delle pagine HTML renderizzate. Ogni pagina verrà salvata come file HTML separato.

```csharp
string pageFilePathFormat = Path.Combine(outputDirectory, "page_{0}.html");
```

## Passaggio 3: inizializzare l'oggetto visualizzatore

Crea un'istanza della classe Viewer e passa come parametro il percorso del documento da visualizzare.

```csharp
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_MSG))
{
```

## Passaggio 4: configura le opzioni di visualizzazione HTML

Configura le opzioni per la visualizzazione HTML, inclusa la specifica del formato del file di output e l'impostazione delle mappature dei campi e-mail.

```csharp
HtmlViewOptions options = HtmlViewOptions.ForEmbeddedResources(pageFilePathFormat);
options.EmailOptions.FieldTextMap[Field.From] = "Sender";
options.EmailOptions.FieldTextMap[Field.To] = "Receiver";
options.EmailOptions.FieldTextMap[Field.Sent] = "Date";
options.EmailOptions.FieldTextMap[Field.Subject] = "Topic";
```

## Passaggio 5: rendering del documento

Richiamare il metodo View dell'oggetto Viewer, passando le opzioni di visualizzazione HTML configurate.

```csharp
viewer.View(options);
```

## Passaggio 6: Visualizza il messaggio di successo

Informare l'utente che il rendering del documento è stato eseguito correttamente.

```csharp
Console.WriteLine($"\nSource document rendered successfully.\nCheck output in {outputDirectory}.");
```

## Conclusione

In conclusione, GroupDocs.Viewer per .NET fornisce una soluzione perfetta per il rendering di documenti all'interno delle applicazioni .NET. Seguendo i passaggi delineati in questo tutorial, puoi facilmente rinominare i campi email durante il rendering, migliorando la leggibilità e l'usabilità dei documenti email. Con la sua API intuitiva e funzionalità complete, GroupDocs.Viewer consente agli sviluppatori di semplificare i processi di visualizzazione dei documenti in modo efficace.

## Domande frequenti

### D: Posso eseguire il rendering di documenti diversi dai messaggi di posta elettronica utilizzando GroupDocs.Viewer per .NET?

R: Sì, GroupDocs.Viewer supporta il rendering di vari formati di documenti tra cui PDF, documenti di Microsoft Office, immagini e altro.

### D: GroupDocs.Viewer è compatibile con .NET Core?

R: Sì, GroupDocs.Viewer supporta .NET Core insieme al tradizionale .NET Framework.

### D: Posso personalizzare l'aspetto dei documenti sottoposti a rendering?

R: Assolutamente sì, GroupDocs.Viewer offre ampie opzioni di personalizzazione per controllare l'aspetto e il comportamento dei documenti renderizzati.

### D: GroupDocs.Viewer supporta lo streaming di documenti?

R: Sì, GroupDocs.Viewer consente lo streaming di documenti direttamente nel browser del client senza la necessità di archiviarli sul server.

### D: GroupDocs.Viewer è adatto per applicazioni di livello aziendale?

R: Certamente, GroupDocs.Viewer è progettato per soddisfare le esigenze delle applicazioni di livello aziendale con la sua scalabilità, affidabilità e un solido set di funzionalità.
