---
"description": "Scopri come aggiungere filigrane ai documenti in modo semplice utilizzando GroupDocs.Viewer per .NET. Migliora la sicurezza e il branding dei documenti con questo tutorial semplice da seguire."
"linktitle": "Aggiungi filigrana nel documento"
"second_title": "API .NET di GroupDocs.Viewer"
"title": "Aggiungi filigrana nel documento"
"url": "/it/net/rendering-options/add-watermark/"
"weight": 10
type: docs
---
# Aggiungi filigrana nel documento

## Introduzione
Nell'era digitale odierna, gestire e visualizzare senza problemi diversi formati di documenti è una necessità per molte aziende e privati. Fortunatamente, con strumenti come GroupDocs.Viewer per .NET, la gestione dei documenti diventa un gioco da ragazzi. Questa potente libreria .NET consente agli sviluppatori di integrare facilmente la funzionalità di visualizzazione dei documenti nelle loro applicazioni, consentendo agli utenti di visualizzare i documenti senza dover utilizzare il software originale con cui sono stati creati.
## Prerequisiti
Prima di iniziare a utilizzare GroupDocs.Viewer per .NET per aggiungere filigrane ai documenti, assicurati di disporre di quanto segue:
1. Configurazione dell'ambiente: disporre di un ambiente di sviluppo configurato con .NET Framework o .NET Core installato.
2. GroupDocs.Viewer per .NET: Scarica e installa la libreria GroupDocs.Viewer per .NET da [pagina di download](https://releases.groupdocs.com/viewer/net/).
3. File di documenti: prepara i file di documenti con cui vuoi lavorare, ad esempio DOCX, PDF o altri.
4. Conoscenza di base di C#: è necessaria familiarità con il linguaggio di programmazione C# per implementare gli esempi di codice.

## Importa spazi dei nomi
Prima di iniziare ad aggiungere filigrane ai documenti utilizzando GroupDocs.Viewer per .NET, assicuratevi di importare gli spazi dei nomi necessari nel codice C#. Questo passaggio vi permetterà di accedere senza problemi alle classi e ai metodi forniti dalla libreria.

```csharp
using System;
using System.IO;
using GroupDocs.Viewer.Options;
```

Ora, vediamo come aggiungere una filigrana a un documento utilizzando GroupDocs.Viewer per .NET. Segui questi passaggi per integrare perfettamente la funzionalità di filigrana nella tua applicazione.
## Passaggio 1: impostare la directory di output
```csharp
string outputDirectory = "Your Document Directory";
```
Specificare la directory in cui si desidera salvare i file di output dopo l'applicazione della filigrana.
## Passaggio 2: definire il formato del percorso del file di paging
```csharp
string pageFilePathFormat = Path.Combine(outputDirectory, "page_{0}.html");
```
Imposta il formato per i percorsi dei file delle pagine renderizzate. In questo esempio, verranno generati file HTML con i numeri di pagina.
## Passaggio 3: creare un'istanza dell'oggetto Viewer
```csharp
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_DOCX))
{
    // Il codice continua nel passaggio successivo...
}
```
Crea un'istanza della classe Viewer, passando il percorso del file del documento come parametro. In questo esempio, utilizziamo un file DOCX di esempio.
## Passaggio 4: configurare le opzioni di visualizzazione HTML
```csharp
HtmlViewOptions options = HtmlViewOptions.ForEmbeddedResources(pageFilePathFormat);
options.Watermark = new Watermark("This is a watermark");
```
Configura le opzioni di visualizzazione HTML, incluso il testo della filigrana che desideri aggiungere al documento.
## Passaggio 5: Visualizza il documento con filigrana
```csharp
viewer.View(options);
```
Invoca il metodo View dell'oggetto Viewer, passando le opzioni configurate. Questo renderà il documento con la filigrana specificata.
## Passaggio 6: visualizzare il percorso della directory di output
```csharp
Console.WriteLine($"\nSource document rendered successfully.\nCheck output in {outputDirectory}.");
```
Informare l'utente dell'avvenuto rendering del documento e indicare la directory in cui sono salvati i file di output.

## Conclusione
GroupDocs.Viewer per .NET offre un modo pratico per aggiungere filigrane ai documenti tramite codice. Seguendo i passaggi descritti in questo tutorial, è possibile integrare perfettamente la funzionalità di filigrana nelle applicazioni .NET, migliorando la sicurezza e il branding dei documenti.
## Domande frequenti
### Posso personalizzare l'aspetto della filigrana?
Sì, puoi personalizzare varie proprietà della filigrana, come testo, carattere, colore, dimensione e posizione.
### GroupDocs.Viewer supporta la visualizzazione di documenti da fonti remote?
Sì, GroupDocs.Viewer supporta la visualizzazione di documenti da archivi locali e da URL remoti.
### Esiste una versione di prova disponibile per GroupDocs.Viewer per .NET?
Sì, puoi scaricare una versione di prova gratuita da [Qui](https://releases.groupdocs.com/).
### Posso aggiungere filigrane a più pagine di un documento?
Certamente, GroupDocs.Viewer consente di aggiungere filigrane a singole pagine o a tutte le pagine di un documento.
### Come posso ottenere supporto o assistenza se riscontro qualche problema?
Puoi cercare aiuto e supporto nei forum della community di GroupDocs [Qui](https://forum.groupdocs.com/c/viewer/9).