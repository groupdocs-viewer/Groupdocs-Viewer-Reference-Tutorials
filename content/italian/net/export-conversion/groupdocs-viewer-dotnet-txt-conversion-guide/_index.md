---
"date": "2025-04-25"
"description": "Scopri come convertire i file TXT in diversi formati, come HTML, JPG, PNG e PDF, utilizzando GroupDocs.Viewer per .NET con questa guida completa."
"title": "Convertire TXT in HTML, JPG, PNG, PDF utilizzando GroupDocs.Viewer .NET - Una guida completa"
"url": "/it/net/export-conversion/groupdocs-viewer-dotnet-txt-conversion-guide/"
"weight": 1
---

# Converti TXT in più formati con GroupDocs.Viewer .NET

## Introduzione

Vuoi convertire documenti di testo in diversi formati come HTML, JPG, PNG o PDF senza sforzo? Gestire le conversioni dei documenti può essere complicato, soprattutto quando si tratta di più pagine o di formati specifici. **GroupDocs.Viewer per .NET** semplifica il processo di rendering dei file TXT in diversi formati di output, garantendo che i dati siano accessibili e visivamente accattivanti.

![Converti TXT in HTML, JPG, PNG, PDF con GroupDocs.Viewer per .NET](/viewer/export-conversion/convert-txt-to-html-jpg-png-pdf.png)

In questa guida, esploreremo come utilizzare GroupDocs.Viewer per .NET per trasformare documenti TXT in HTML multipagina, HTML a pagina singola, JPG, PNG e PDF. Al termine, padroneggerai:
- Conversione di file TXT tramite C# con GroupDocs.Viewer
- Implementazione di diverse opzioni di rendering per le tue esigenze
- Ottimizzazione delle prestazioni durante le conversioni

Andiamo a scoprire come risolvere le tue sfide di conversione dei documenti.

## Prerequisiti

Prima di iniziare, assicurati di avere pronto quanto segue:
- **Ambiente di sviluppo**: Visual Studio 2019 o versione successiva.
- **Framework .NET**: Versione 4.6.1 o superiore.
- **GroupDocs.Viewer per la libreria .NET**:
  - Tramite la console del gestore pacchetti NuGet: `Install-Package GroupDocs.Viewer -Version 25.3.0`
  - Utilizzo della CLI .NET: `dotnet add package GroupDocs.Viewer --version 25.3.0`

Per seguire agevolmente il corso si consiglia di avere familiarità con la programmazione C# e con le operazioni di base sui file in .NET.

## Impostazione di GroupDocs.Viewer per .NET

### Installazione

Per iniziare, installa il **GroupDocs.Viewer** libreria utilizzando il tuo gestore di pacchetti preferito:

#### Console del gestore pacchetti NuGet
```bash
Install-Package GroupDocs.Viewer -Version 25.3.0
```

#### Interfaccia a riga di comando .NET
```bash
dotnet add package GroupDocs.Viewer --version 25.3.0
```

### Licenza

Puoi iniziare con un **prova gratuita** o ottenere un **licenza temporanea** per esplorare tutte le funzionalità di GroupDocs.Viewer per .NET senza limitazioni di valutazione:
- Prova gratuita: [Scarica qui](https://releases.groupdocs.com/viewer/net/)
- Licenza temporanea: [Richiedi qui](https://purchase.groupdocs.com/temporary-license/)

Per un utilizzo continuativo, si consiglia di acquistare una licenza direttamente da [Documenti di gruppo](https://purchase.groupdocs.com/buy).

### Inizializzazione di base

Per configurare GroupDocs.Viewer nel tuo progetto:

```csharp
using System.IO;
using GroupDocs.Viewer;

string outputDirectory = Path.Combine("YOUR_DOCUMENT_DIRECTORY", "Output");

// Inizializza l'oggetto Viewer con un percorso file TXT.
using (Viewer viewer = new Viewer(Path.Combine("YOUR_DOCUMENT_DIRECTORY", "Sample.txt")))
{
    // Qui andrà inserito il codice di rendering.
}
```

## Guida all'implementazione

Ora approfondiamo ogni funzionalità e vediamo come implementarle.

### Trasforma il documento TXT in HTML multipagina

#### Panoramica
Questa funzionalità illustra la conversione di un documento TXT in formato HTML multipagina. Ogni pagina del file di testo viene visualizzata come un singolo file HTML con risorse incorporate.

#### Passaggio 1: configurazione del visualizzatore

Crea un `Viewer` oggetto per il file TXT di origine:

```csharp
using System.IO;
using GroupDocs.Viewer;
using GroupDocs.Viewer.Options;

string outputDirectory = Path.Combine("YOUR_DOCUMENT_DIRECTORY", "Output");
string pageFileFullPath = Path.Combine(outputDirectory, "Txt_result.html");

// Inizializzare il Viewer con un file di testo di esempio.
using (Viewer viewer = new Viewer(Path.Combine("YOUR_DOCUMENT_DIRECTORY", "Sample.txt")))
{
    // Continua al passaggio 2...
```

#### Passaggio 2: configurare le opzioni di visualizzazione HTML

Impostare `HtmlViewOptions` per rendere ogni pagina separatamente:

```csharp
// Imposta le opzioni di visualizzazione HTML per il rendering multipagina.
HtmlViewOptions options = HtmlViewOptions.ForEmbeddedResources(pageFileFullPath);

// Visualizza il documento come HTML multipagina.
viewer.View(options);
}
```

**Spiegazione**: IL `ForEmbeddedResources()` Il metodo garantisce che risorse come immagini e stili vengano incorporate direttamente nel file HTML, facilitandone la condivisione.

### Trasforma il documento TXT in HTML a pagina singola

#### Panoramica
Converte un documento TXT in un'unica pagina HTML, ideale per i documenti che devono essere visualizzati come un'unica pagina web continua.

#### Passaggio 1: configurazione del visualizzatore

Inizializzare il `Viewer` oggetto:

```csharp
string outputDirectory = Path.Combine("YOUR_DOCUMENT_DIRECTORY", "Output");
string pageFileFullPath = Path.Combine(outputDirectory, "Txt_result_single_page.html");

// Inizializza una nuova istanza del Viewer per un file di testo diverso.
using (Viewer viewer = new Viewer(Path.Combine("YOUR_DOCUMENT_DIRECTORY", "Sample2.txt")))
{
    // Continua al passaggio 2...
```

#### Passaggio 2: configurare le opzioni HTML della singola pagina

Configurare `HtmlViewOptions` con l'impostazione a pagina singola abilitata:

```csharp
// Imposta le opzioni per il rendering in un'unica pagina HTML.
HtmlViewOptions options = HtmlViewOptions.ForEmbeddedResources(pageFileFullPath);
options.RenderToSinglePage = true;

// Visualizza come una singola pagina HTML.
viewer.View(options);
}
```

**Spiegazione**: IL `RenderToSinglePage` La proprietà garantisce che l'intero contenuto venga visualizzato su un'unica pagina.

### Trasforma il documento TXT in JPG

#### Panoramica
Questa funzione consente di convertire un documento di testo in un'immagine JPEG, utile per presentazioni visive o scopi di archiviazione.

#### Passaggio 1: configurazione del visualizzatore

Prepara il tuo `Viewer` oggetto:

```csharp
string outputDirectory = Path.Combine("YOUR_DOCUMENT_DIRECTORY", "Output");
string pageFileFullPath = Path.Combine(outputDirectory, "Txt_result.jpg");

// Inizializzare il visualizzatore con un file di esempio.
using (Viewer viewer = new Viewer(Path.Combine("YOUR_DOCUMENT_DIRECTORY", "Sample.txt")))
{
    // Continua al passaggio 2...
```

#### Passaggio 2: configurare le opzioni di visualizzazione JPG

Impostare `JpgViewOptions` per il rendering delle immagini:

```csharp
// Imposta le opzioni per il rendering come immagine JPG.
JpgViewOptions options = new JpgViewOptions(pageFileFullPath);

// Rendi il documento come file JPEG.
viewer.View(options);
}
```

**Spiegazione**: IL `JpgViewOptions` La classe specifica come eseguire il rendering e salvare ogni pagina del documento in formato JPEG.

### Trasforma il documento TXT in PNG

#### Panoramica
Converti un documento di testo in formato PNG, offrendo un output di immagine di alta qualità con supporto per la trasparenza.

#### Passaggio 1: configurazione del visualizzatore

Inizializzare il `Viewer` oggetto:

```csharp
string outputDirectory = Path.Combine("YOUR_DOCUMENT_DIRECTORY", "Output");
string pageFileFullPath = Path.Combine(outputDirectory, "Txt_result.png");

// Crea un'istanza di visualizzazione per il tuo file TXT.
using (Viewer viewer = new Viewer(Path.Combine("YOUR_DOCUMENT_DIRECTORY", "Sample.txt")))
{
    // Continua al passaggio 2...
```

#### Passaggio 2: configurare le opzioni di visualizzazione PNG

Impostare `PngViewOptions`:

```csharp
// Imposta le opzioni di visualizzazione per il rendering come immagine PNG.
PngViewOptions options = new PngViewOptions(pageFileFullPath);

// Rendi il documento in formato PNG.
viewer.View(options);
}
```

**Spiegazione**: IL `PngViewOptions` La classe consente di visualizzare ogni pagina con trasparenza, rendendola adatta alla grafica a strati.

### Trasforma il documento TXT in PDF

#### Panoramica
Questa funzionalità è perfetta per convertire documenti di testo in un formato PDF universalmente accessibile.

#### Passaggio 1: configurazione del visualizzatore

Prepara il tuo `Viewer` oggetto:

```csharp
string outputDirectory = Path.Combine("YOUR_DOCUMENT_DIRECTORY", "Output");
string pageFileFullPath = Path.Combine(outputDirectory, "Txt_result.pdf");

// Inizializza un'istanza del visualizzatore per il tuo file di testo di esempio.
using (Viewer viewer = new Viewer(Path.Combine("YOUR_DOCUMENT_DIRECTORY", "Sample.txt")))
{
    // Continua al passaggio 2...
```

#### Passaggio 2: configurare le opzioni di visualizzazione PDF

Impostare `PdfViewOptions`:

```csharp
// Imposta le opzioni di visualizzazione per il rendering come documento PDF.
PdfViewOptions options = new PdfViewOptions(pageFileFullPath);

// Converti il documento in un file PDF.
viewer.View(options);
}
```

**Spiegazione**: IL `PdfViewOptions` La classe specifica come convertire e salvare i file TXT come documenti PDF.

## Conclusione

Con GroupDocs.Viewer per .NET, convertire i documenti di testo in vari formati è semplice. Questa guida ha illustrato come trasformare file TXT in HTML multipagina, HTML a pagina singola, JPG, PNG e PDF utilizzando C#. Che si desideri migliorare l'accessibilità o la compatibilità dei documenti, questi metodi offrono soluzioni affidabili.

Per ulteriore assistenza o funzionalità più avanzate, fare riferimento a [documentazione ufficiale di GroupDocs.Viewer](https://docs.groupdocs.com/viewer/net/)Buona programmazione!