---
"date": "2025-04-25"
"description": "Scopri come convertire facilmente i file di Microsoft Visio in diversi formati utilizzando GroupDocs.Viewer per .NET. Migliora l'accessibilità dei documenti per l'integrazione web."
"title": "Come visualizzare i documenti Visio in formato HTML, JPG, PNG e PDF in .NET utilizzando GroupDocs.Viewer"
"url": "/it/net/rendering-basics/groupdocs-viewer-dotnet-render-visio-documents-html-jpg-png-pdf/"
"weight": 1
---

# Come visualizzare i documenti Visio in formato HTML, JPG, PNG e PDF utilizzando GroupDocs.Viewer in .NET

## Introduzione

Cerchi uno strumento versatile per convertire i diagrammi di Microsoft Visio in formati come HTML, JPG, PNG o PDF? Questo tutorial ti guiderà nell'utilizzo. **GroupDocs.Viewer per .NET**, una potente libreria progettata per semplificare la conversione dei documenti. Al termine di questo articolo, saprai come trasformare in modo efficiente i file Visio in diversi formati, migliorandone l'accessibilità e l'usabilità.

**Cosa imparerai:**
- Come configurare GroupDocs.Viewer in un ambiente .NET
- Istruzioni dettagliate per il rendering dei diagrammi in formato HTML, JPG, PNG e PDF
- Opzioni di configurazione chiave per risultati ottimali
- Applicazioni pratiche e possibilità di integrazione

Cominciamo col parlare dei prerequisiti.

## Prerequisiti

Prima di immergerti in GroupDocs.Viewer per .NET, assicurati di avere:

### Librerie, versioni e dipendenze richieste
- **GroupDocs.Viewer per .NET**: Si consiglia la versione 25.3.0 o successiva.
- Un ambiente di sviluppo .NET compatibile (ad esempio, Visual Studio).

### Requisiti di configurazione dell'ambiente
- Il sistema deve supportare .NET Framework o .NET Core/5+.

### Prerequisiti di conoscenza
- Conoscenza di base delle strutture dei progetti C# e .NET.

## Impostazione di GroupDocs.Viewer per .NET

Per iniziare, installa il **GroupDocs.Viewer** libreria utilizzando NuGet Package Manager Console o .NET CLI:

**Console del gestore pacchetti NuGet**
```shell
Install-Package GroupDocs.Viewer -Version 25.3.0
```

**Interfaccia a riga di comando .NET**
```bash
dotnet add package GroupDocs.Viewer --version 25.3.0
```

### Fasi di acquisizione della licenza
- **Prova gratuita**: Inizia con una prova gratuita per esplorare le funzionalità.
- **Licenza temporanea**: Ottieni una licenza temporanea per test più lunghi.
- **Acquistare**: Valuta l'acquisto se hai bisogno di un utilizzo a lungo termine.

### Inizializzazione e configurazione di base

Inizializza GroupDocs.Viewer assicurandoti che il tuo progetto faccia riferimento correttamente alla libreria:

```csharp
using GroupDocs.Viewer;
// Inizializza l'oggetto visualizzatore con il percorso del documento
using (Viewer viewer = new Viewer("path/to/your/document.vsd"))
{
    // Configurare le opzioni secondo necessità
}
```

## Guida all'implementazione

Illustreremo passo dopo passo come convertire i documenti Visio in diversi formati.

### Rendering di documenti Visio in HTML

**Panoramica**:La conversione dei diagrammi in HTML consente di incorporarli facilmente nelle pagine web, migliorando l'accessibilità e l'interattività.

#### Passaggio 1: impostare le opzioni di visualizzazione HTML

Configurare `HtmlViewOptions` per risorse incorporate:

```csharp
string outputDirectory = Path.Combine("YOUR_OUTPUT_DIRECTORY");
string pageFilePathFormat = Path.Combine(outputDirectory, "result_page.html");

using (Viewer viewer = new Viewer(Path.Combine("YOUR_DOCUMENT_DIRECTORY", "SAMPLE_VISIO.vsd")))
{
    HtmlViewOptions options = HtmlViewOptions.ForEmbeddedResources(pageFilePathFormat);
    options.VisioRenderingOptions.RenderFiguresOnly = true;
    options.VisioRenderingOptions.FigureWidth = 250; // Configura la larghezza della figura
    viewer.View(options); // Esegui il rendering e salva come HTML
}
```

**Configurazione chiave**: 
- `RenderFiguresOnly`: Visualizza solo le cifre.
- `FigureWidth`: Imposta la larghezza di ogni figura in pixel.

### Rendering di documenti Visio in JPG

**Panoramica**:La trasformazione dei diagrammi in immagini JPEG è utile per la condivisione su più piattaforme senza software specializzati.

#### Passaggio 2: configurare JpgViewOptions

Imposta opzioni su misura per il rendering delle figure come immagini:

```csharp
string outputDirectory = Path.Combine("YOUR_OUTPUT_DIRECTORY");
string pageFilePathFormat = Path.Combine(outputDirectory, "visio_result.jpg");

using (Viewer viewer = new Viewer(Path.Combine("YOUR_DOCUMENT_DIRECTORY", "SAMPLE_VISIO.vsd")))
{
    JpgViewOptions options = new JpgViewOptions(pageFilePathFormat);
    options.VisioRenderingOptions.RenderFiguresOnly = true;
    options.VisioRenderingOptions.FigureWidth = 250; // Regola la larghezza della figura
    viewer.View(options); // Rendi e salva come JPG
}
```

**Suggerimento per la risoluzione dei problemi**: Se l'immagine in uscita non è chiara, verificare se `FigureWidth` corrisponda alle dimensioni di visualizzazione desiderate.

### Rendering di documenti Visio in PNG

**Panoramica**:Il formato PNG offre immagini di alta qualità con compressione senza perdita di dati, ideale per diagrammi dettagliati.

#### Passaggio 3: definire PngViewOptions

Configura le opzioni specifiche per il rendering in formato PNG:

```csharp
string outputDirectory = Path.Combine("YOUR_OUTPUT_DIRECTORY");
string pageFilePathFormat = Path.Combine(outputDirectory, "visio_result.png");

using (Viewer viewer = new Viewer(Path.Combine("YOUR_DOCUMENT_DIRECTORY", "SAMPLE_VISIO.vsd")))
{
    PngViewOptions options = new PngViewOptions(pageFilePathFormat);
    options.VisioRenderingOptions.RenderFiguresOnly = true;
    options.VisioRenderingOptions.FigureWidth = 250; // Imposta la larghezza della figura
    viewer.View(options); // Rendi e salva come PNG
}
```

### Rendering di documenti Visio in PDF

**Panoramica**:La conversione dei diagrammi in formato PDF è perfetta per la distribuzione e l'archiviazione, poiché offre una visualizzazione universale dei documenti.

#### Passaggio 4: configurazione di PdfViewOptions

Configura le opzioni per il rendering delle figure in formato PDF:

```csharp
string outputDirectory = Path.Combine("YOUR_OUTPUT_DIRECTORY");
string pageFilePathFormat = Path.Combine(outputDirectory, "visio_result.pdf");

using (Viewer viewer = new Viewer(Path.Combine("YOUR_DOCUMENT_DIRECTORY", "SAMPLE_VISIO.vsd")))
{
    PdfViewOptions options = new PdfViewOptions(pageFilePathFormat);
    options.VisioRenderingOptions.RenderFiguresOnly = true;
    options.VisioRenderingOptions.FigureWidth = 250; // Definisci la larghezza della figura
    viewer.View(options); // Rendi e salva come PDF
}
```

## Applicazioni pratiche

GroupDocs.Viewer può migliorare la gestione dei documenti in vari sistemi:
1. **Portali Web**: Incorpora figure HTML renderizzate direttamente nelle pagine web per ottenere contenuti dinamici.
2. **Sistemi di gestione dei documenti (DMS)**Utilizza i formati JPG, PNG o PDF per una facile condivisione e archiviazione sulle piattaforme DMS.
3. **Strumenti di reporting aziendale**: Genera report con diagrammi incorporati in diversi formati per soddisfare le esigenze di presentazione.

## Considerazioni sulle prestazioni

Ottimizzare le prestazioni quando si utilizza GroupDocs.Viewer è fondamentale:
- **Utilizzo delle risorse**: Monitorare l'utilizzo della memoria durante il rendering per evitare colli di bottiglia.
- **Migliori pratiche**: Utilizzare operazioni asincrone ove possibile per migliorare la reattività.
- **Gestione della memoria**: Smaltire gli oggetti visualizzati subito dopo l'uso per liberare risorse.

## Conclusione

In questo tutorial, hai imparato come sfruttare GroupDocs.Viewer per .NET per visualizzare i documenti Visio nei formati HTML, JPG, PNG e PDF. Grazie a queste competenze, puoi migliorare l'accessibilità dei documenti e integrare funzionalità di rendering versatili nelle tue applicazioni.

**Prossimi passi**: Esplora le funzionalità aggiuntive di GroupDocs.Viewer consultando [Riferimento API](https://reference.groupdocs.com/viewer/net/) oppure prova diverse opzioni di rendering in base alle tue esigenze specifiche.

## Sezione FAQ

1. **Posso elaborare documenti Visio senza una licenza?**
   - Sì, puoi utilizzare GroupDocs.Viewer con una licenza di prova gratuita per esplorarne inizialmente le funzionalità.
2. **Quali formati di file supporta GroupDocs.Viewer oltre a Visio?**
   - Supporta un'ampia gamma di formati, tra cui PDF, Word, Excel e altri.
3. **È possibile personalizzare le dimensioni di output delle figure renderizzate?**
   - Assolutamente! Regolare `FigureWidth` nelle opzioni di rendering per controllare le dimensioni di output.
4. **Come posso gestire documenti di grandi dimensioni con GroupDocs.Viewer?**
   - Ottimizza le prestazioni configurando le impostazioni di utilizzo della memoria e utilizzando processi asincroni ove appropriato.