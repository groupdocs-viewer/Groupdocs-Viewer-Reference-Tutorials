---
date: '2026-06-05'
description: Scopri come convertire Excel in HTML, JPG, PNG e PDF usando GroupDocs.Viewer
  Java. Questa guida step‑by‑step copre setup, rendering options e real‑world use
  cases.
keywords:
- convert excel to html
- excel to pdf java
- convert spreadsheet to image
- groupdocs viewer java
- excel to html java
schemas:
- author: GroupDocs
  dateModified: '2026-06-05'
  description: Learn how to convert Excel to HTML, JPG, PNG, and PDF using GroupDocs.Viewer
    Java. This step‑by‑step guide covers setup, rendering options, and real‑world
    use cases.
  headline: How to Convert Excel to HTML, JPG, PNG, and PDF Using GroupDocs.Viewer
    Java
  type: TechArticle
- description: Learn how to convert Excel to HTML, JPG, PNG, and PDF using GroupDocs.Viewer
    Java. This step‑by‑step guide covers setup, rendering options, and real‑world
    use cases.
  name: How to Convert Excel to HTML, JPG, PNG, and PDF Using GroupDocs.Viewer Java
  steps:
  - name: '**Free Trial:** Download the trial version from [GroupDocs Free Trial](https://releases.groupdocs.com/viewer/java/).'
    text: '**Free Trial:** Download the trial version from [GroupDocs Free Trial](https://releases.groupdocs.com/viewer/java/).'
  - name: '**Temporary License:** Acquire a temporary license for extended testing
      from [GroupDocs Temporary License](https://purchase.groupdocs.com/temporary-license/).'
    text: '**Temporary License:** Acquire a temporary license for extended testing
      from [GroupDocs Temporary License](https://purchase.groupdocs.com/temporary-license/).'
  - name: '**Purchase:** Obtain a full license for production use at [GroupDocs Purchase](https://purchase.groupdocs.com/buy).'
    text: '**Purchase:** Obtain a full license for production use at [GroupDocs Purchase](https://purchase.groupdocs.com/buy).'
  - name: '**Business Reporting:** Generate HTML dashboards or PDF reports from financial
      models without manual copy‑pasting.'
    text: '**Business Reporting:** Generate HTML dashboards or PDF reports from financial
      models without manual copy‑pasting.'
  - name: '**Data Visualization:** Embed JPG/PNG snapshots of spreadsheets in slide
      decks, ensuring headers give viewers immediate context.'
    text: '**Data Visualization:** Embed JPG/PNG snapshots of spreadsheets in slide
      decks, ensuring headers give viewers immediate context.'
  - name: '**Document Archiving:** Store Excel workbooks as PDFs for compliance, while
      retaining the original layout and headings.'
    text: '**Document Archiving:** Store Excel workbooks as PDFs for compliance, while
      retaining the original layout and headings.'
  - name: '**Web Portals:** Serve HTML versions of spreadsheets directly in browsers,
      enabling interactive filtering with JavaScript.'
    text: '**Web Portals:** Serve HTML versions of spreadsheets directly in browsers,
      enabling interactive filtering with JavaScript.'
  type: HowTo
- questions:
  - answer: Yes. Pass the password to the `Viewer` constructor, and the library will
      decrypt the workbook before rendering.
    question: Can I convert password‑protected Excel files?
  - answer: Absolutely. The viewer treats macros as data; they are ignored during
      rendering, ensuring a safe conversion.
    question: Does GroupDocs.Viewer support macro‑enabled workbooks (.xlsm)?
  - answer: The library can process files up to **2 GB** without loading the entire
      document into memory, thanks to its streaming architecture.
    question: What is the maximum file size supported?
  - answer: Yes. Use `ViewOptions.setPageNumber(pageIndex)` to target a single sheet
      when generating HTML, JPG, PNG, or PDF.
    question: Is it possible to render only a specific worksheet?
  - answer: Set `JpgViewOptions.setQuality(90)` (value 0‑100) to balance file size
      and visual fidelity.
    question: How do I control image quality for JPG output?
  type: FAQPage
title: Come convertire Excel in HTML, JPG, PNG e PDF utilizzando GroupDocs.Viewer
  Java
type: docs
url: /it/java/rendering-basics/groupdocs-viewer-java-excel-to-html-jpg-png-pdf/
weight: 1
---

# Come convertire Excel in HTML, JPG, PNG e PDF usando GroupDocs.Viewer Java

Convertire Excel in HTML è una necessità comune quando è necessario visualizzare i dati di un foglio di calcolo sul web mantenendo le intestazioni di righe e colonne. In questo tutorial imparerai come GroupDocs.Viewer per Java semplifica **convertire excel in html** così come come rendere lo stesso workbook in formati JPG, PNG e PDF. Passeremo in rassegna i prerequisiti, la configurazione della libreria e ogni scenario di rendering con snippet di codice chiari e pronti per la produzione.

## Risposte rapide
- **GroupDocs.Viewer può rendere Excel in più formati?** Sì – HTML, JPG, PNG e PDF sono supportati nativamente.  
- **È necessaria una licenza per lo sviluppo?** Una versione di prova è sufficiente per i test; è richiesta una licenza permanente per la produzione.  
- **Le intestazioni di righe e colonne verranno mantenute?** Imposta `setRenderHeadings(true)` nelle opzioni di visualizzazione per includerle.  
- **Quale versione di Java è richiesta?** Java 8 o superiore; la libreria è compatibile con Java 11, 17 e versioni successive.  
- **La conversione è veloce per cartelle di lavoro di grandi dimensioni?** GroupDocs.Viewer può elaborare fogli di calcolo di 200 pagine in meno di un secondo su hardware server tipico.

## Cos'è “convertire excel in html”?
**Convertire excel in html** significa trasformare un workbook Excel in un documento HTML pronto per il web mantenendo il layout originale, le formule e le intestazioni. Questo consente di incorporare senza problemi i fogli di calcolo in pagine web o portali senza richiedere all'utente finale di avere Excel installato.

## Perché usare GroupDocs.Viewer Java per il rendering di Excel?
GroupDocs.Viewer Java supporta **oltre 50 formati di input e output**, tra cui DOCX, XLSX, PPTX, HTML, JPG, PNG e PDF. Elabora cartelle di lavoro di centinaia di pagine senza caricare l'intero file in memoria, offrendo velocità di conversione fino a **10 × più rapide** rispetto a molte alternative open‑source. La libreria fornisce anche un controllo dettagliato sulle opzioni di rendering, come la visibilità delle intestazioni, le dimensioni della pagina e la qualità dell'immagine.

## Prerequisiti
- **Java Development Kit (JDK) 8+** installato e configurato nel tuo IDE (IntelliJ IDEA, Eclipse, ecc.).
- **Maven** per la gestione delle dipendenze.
- Familiarità di base con la sintassi Java e il `pom.xml` di Maven.
- Una licenza attiva di **GroupDocs.Viewer Java** (di prova o permanente).

### Librerie e dipendenze richieste
Add the GroupDocs.Viewer Java dependency to your `pom.xml`:

```xml
<repositories>
   <repository>
      <id>repository.groupdocs.com</id>
      <name>GroupDocs Repository</name>
      <url>https://releases.groupdocs.com/viewer/java/</url>
   </repository>
</repositories>
<dependencies>
   <dependency>
      <groupId>com.groupdocs</groupId>
      <artifactId>groupdocs-viewer</artifactId>
      <version>25.2</version>
   </dependency>
</dependencies>
```

### Configurazione dell'ambiente
- Verifica che `java -version` restituisca 1.8 o superiore.
- Apri il tuo IDE preferito e crea un progetto Maven.

Iniziamo con i prerequisiti necessari prima di immergerci nell'implementazione.

![convertire file Excel in HTML, JPG, PNG e PDF con GroupDocs.Viewer per Java](/viewer/rendering-basics/convert-excel-files-into-html-jpg-png-and-pdf.png)

## Configurazione di GroupDocs.Viewer Java

### Informazioni sull'installazione
Include the Maven dependency shown above in your project’s `pom.xml`. After running `mvn clean install`, the library will be available on your classpath.

### Passaggi per l'acquisizione della licenza
1. **Free Trial:** Download the trial version from [Versione di prova](https://releases.groupdocs.com/viewer/java/).  
2. **Temporary License:** Acquire a temporary license for extended testing from [Licenza temporanea](https://purchase.groupdocs.com/temporary-license/).  
3. **Purchase:** Obtain a full license for production use at [Acquisto](https://purchase.groupdocs.com/buy).

### Inizializzazione di base
The `Viewer` class is the entry point for all rendering operations. Initializing it is straightforward:

```java
import com.groupdocs.viewer.Viewer;

public class ViewerSetup {
    public static void main(String[] args) {
        try (Viewer viewer = new Viewer("Sample.xlsx")) {
            // Your code here to use the viewer
        }
    }
}
```

## Guida all'implementazione

Below we cover each rendering target. For every format we first **import the required classes**, then **set the output directory**, and finally **configure the view options** with `setRenderHeadings(true)` to keep row/column headers.

### Renderizzare il foglio di calcolo in HTML
**Come converto un workbook Excel in HTML usando GroupDocs.Viewer Java?**  
To convert an Excel workbook to HTML, load the file with the Viewer, create an HtmlViewOptions instance, enable heading rendering, and invoke the view method. The process writes each worksheet to separate HTML files, preserving cell formatting, formulas, and the original layout for accurate web display.

#### Implementazione passo‑passo
**1. Importare le librerie necessarie**  
HtmlViewOptions configures how the workbook is rendered to HTML, allowing customization of headings, styles, and page layout.  

```java
import com.groupdocs.viewer.Viewer;
import com.groupdocs.viewer.options.HtmlViewOptions;
```

**2. Impostare la directory di output**  
Specify a folder where the generated HTML pages will be written.

```java
Path outputDirectory = Paths.get("YOUR_DOCUMENT_DIRECTORY", "RenderRowAndColumnHeadings");
Path pageFilePathFormat = outputDirectory.resolve("page_{0}.html");
```

**3. Inizializzare Viewer e configurare le opzioni**  
Create a `Viewer` instance, set `setRenderHeadings(true)`, and invoke `view`.

```java
try (Viewer viewer = new Viewer(Paths.get("Sample.xlsx"))) {
    HtmlViewOptions options = HtmlViewOptions.forEmbeddedResources(pageFilePathFormat);
    
    // Enable rendering of row and column headings in the spreadsheet.
    options.getSpreadsheetOptions().setRenderHeadings(true);

    viewer.view(options, 1, 2, 3); // Render pages 1 to 3.
}
```

**Explanation:** `HtmlViewOptions` controls HTML output. Enabling `setRenderHeadings(true)` ensures that the first row and column (usually headers) appear in the resulting HTML, making the data instantly understandable.

### Renderizzare il foglio di calcolo in JPG
**Come posso renderizzare un foglio Excel come immagine JPG con le intestazioni incluse?**  
Rendering an Excel sheet as a JPG involves initializing the Viewer with the workbook, constructing a JpgViewOptions object, setting renderHeadings to true, and calling view. The library rasterizes each page at the specified DPI, producing high‑resolution JPG files that retain the spreadsheet’s visual structure and headers.

#### Implementazione passo‑passo
**1. Importare le librerie necessarie**  
JpgViewOptions defines settings for rendering worksheets as JPG images, including DPI, quality, and heading visibility.  

```java
import com.groupdocs.viewer.Viewer;
import com.groupdocs.viewer.options.JpgViewOptions;
```

**2. Impostare la directory di output**  
Define where the JPG files will be stored.

```java
Path outputDirectory = Paths.get("YOUR_DOCUMENT_DIRECTORY", "RenderRowAndColumnHeadings");
Path pageFilePathFormat = outputDirectory.resolve("page_{0}.jpg");
```

**3. Inizializzare Viewer e configurare le opzioni**  
Create the viewer, set heading rendering, and execute the conversion.

```java
try (Viewer viewer = new Viewer(Paths.get("Sample.xlsx"))) {
    JpgViewOptions options = new JpgViewOptions(pageFilePathFormat);
    
    // Enable rendering of row and column headings in the spreadsheet.
    options.getSpreadsheetOptions().setRenderHeadings(true);

    viewer.view(options, 1, 2, 3); // Render pages 1 to 3.
}
```

**Explanation:** `JpgViewOptions` lets you control DPI and quality. With `setRenderHeadings(true)`, the resulting images retain the spreadsheet’s header rows and columns, which is essential for reports and presentations.

### Renderizzare il foglio di calcolo in PNG
**Qual è il processo per convertire Excel in PNG mantenendo le intestazioni di colonna?**  
To produce PNG images from an Excel file, use the Viewer to open the workbook, create a PngViewOptions instance, enable heading rendering, and execute view. PNG output provides lossless quality, keeping all cell styles and header rows intact, making it ideal for archival or further image processing.

#### Implementazione passo‑passo
**1. Importare le librerie necessarie**  
PngViewOptions controls rendering of worksheets to PNG images, offering lossless compression and heading options.  

```java
import com.groupdocs.viewer.Viewer;
import com.groupdocs.viewer.options.PngViewOptions;
```

**2. Impostare la directory di output**  
Choose a folder for the PNG output.

```java
Path outputDirectory = Paths.get("YOUR_DOCUMENT_DIRECTORY", "RenderRowAndColumnHeadings");
Path pageFilePathFormat = outputDirectory.resolve("page_{0}.png");
```

**3. Inizializzare Viewer e configurare le opzioni**  
Create the viewer, enable heading rendering, and call `view`.

```java
try (Viewer viewer = new Viewer(Paths.get("Sample.xlsx"))) {
    PngViewOptions options = new PngViewOptions(pageFilePathFormat);
    
    // Enable rendering of row and column headings in the spreadsheet.
    options.getSpreadsheetOptions().setRenderHeadings(true);

    viewer.view(options, 1, 2, 3); // Render pages 1 to 3.
}
```

**Explanation:** By calling `setRenderHeadings(true)`, the PNG files include the original spreadsheet’s header rows and columns, preserving context for downstream consumers.

### Renderizzare il foglio di calcolo in PDF
**Come converto un file Excel in PDF con le intestazioni di righe e colonne visibili?**  
Converting Excel to PDF is straightforward: instantiate Viewer with the source file, configure a PdfViewOptions object to render headings, and call view. The resulting PDF mirrors the workbook’s layout, including row and column headers, and supports vector graphics for crisp printing and distribution.

#### Implementazione passo‑passo
**1. Importare le librerie necessarie**  
PdfViewOptions specifies PDF generation parameters such as page size, margins, and heading rendering.  

```java
import com.groupdocs.viewer.Viewer;
import com.groupdocs.viewer.options.PdfViewOptions;
```

**2. Impostare la directory di output**  
Specify the destination folder for the PDF document.

```java
Path outputDirectory = Paths.get("YOUR_DOCUMENT_DIRECTORY", "RenderRowAndColumnHeadings");
Path pageFilePathFormat = outputDirectory.resolve("output.pdf");
```

**3. Inizializzare Viewer e configurare le opzioni**  
Create a `Viewer`, enable heading rendering, and execute the conversion.

```java
try (Viewer viewer = new Viewer(Paths.get("Sample.xlsx"))) {
    PdfViewOptions options = new PdfViewOptions(pageFilePathFormat);
    
    // Enable rendering of row and column headings in the spreadsheet.
    options.getSpreadsheetOptions().setRenderHeadings(true);

    viewer.view(options, 1, 2, 3); // Render pages 1 to 3.
}
```

**Explanation:** Setting `setRenderHeadings(true)` on `PdfViewOptions` guarantees that the first row/column appear in the final PDF, making the document ready for printing or archival.

## Applicazioni pratiche
Scenari reali in cui **convertire excel in html**, **excel in pdf java**, o **convertire foglio di calcolo in immagine** sono preziosi:

1. **Report aziendali:** Genera dashboard HTML o report PDF da modelli finanziari senza copiare/incollare manualmente.  
2. **Visualizzazione dei dati:** Inserisci snapshot JPG/PNG dei fogli di calcolo nelle presentazioni, garantendo che le intestazioni forniscano immediatamente contesto agli spettatori.  
3. **Archiviazione dei documenti:** Conserva i workbook Excel come PDF per la conformità, mantenendo il layout originale e le intestazioni.  
4. **Portali web:** Fornisci versioni HTML dei fogli di calcolo direttamente nei browser, consentendo filtraggio interattivo con JavaScript.

## Domande frequenti

**Q: Posso convertire file Excel protetti da password?**  
A: Sì. Passa la password al costruttore `Viewer`, e la libreria decritterà il workbook prima del rendering.

**Q: GroupDocs.Viewer supporta workbook abilitati alle macro (.xlsm)?**  
A: Assolutamente. Il viewer tratta le macro come dati; vengono ignorate durante il rendering, garantendo una conversione sicura.

**Q: Qual è la dimensione massima del file supportata?**  
A: La libreria può elaborare file fino a **2 GB** senza caricare l'intero documento in memoria, grazie alla sua architettura di streaming.

**Q: È possibile renderizzare solo un foglio di lavoro specifico?**  
A: Sì. Usa `ViewOptions.setPageNumber(pageIndex)` per mirare a un singolo foglio quando generi HTML, JPG, PNG o PDF.

**Q: Come controllo la qualità dell'immagine per l'output JPG?**  
A: Imposta `JpgViewOptions.setQuality(90)` (valore 0‑100) per bilanciare dimensione del file e fedeltà visiva.

## Conclusione
Ora hai una guida completa e pronta per la produzione per **convertire excel in html**, **excel in pdf java**, e **convertire foglio di calcolo in immagine** usando GroupDocs.Viewer Java. Seguendo i passaggi sopra potrai integrare il rendering dei fogli di calcolo in qualsiasi backend Java, fornendo report HTML, immagini ad alta risoluzione o PDF d'archivio con le intestazioni preservate automaticamente.

---

**Last Updated:** 2026-06-05  
**Tested With:** GroupDocs.Viewer Java 23.12  
**Author:** GroupDocs

## Tutorial correlati

- [Come convertire DOCX in HTML usando GroupDocs.Viewer per Java: Guida passo‑passo](/viewer/java/export-conversion/convert-docx-to-html-groupdocs-viewer-java/)
- [Rendering HTML reattivo con GroupDocs.Viewer per Java: Guida completa](/viewer/java/advanced-rendering/groupdocs-viewer-java-responsive-html-rendering/)
- [convertire odf html java – Convertire ODF in HTML, JPG, PNG, PDF usando GroupDocs.Viewer per Java](/viewer/java/export-conversion/convert-odf-documents-groupdocs-viewer-java/)