---
date: '2026-08-08'
description: Scopri come convertire IGS in PDF, HTML, JPG e PNG usando GroupDocs.Viewer
  per Java. Guida passo‑passo, requisiti e risoluzione dei problemi per gli sviluppatori
  Java.
keywords:
- convert igs to pdf
- convert cad to image
- convert igs to jpg
- java cad to pdf
lastmod: '2026-08-08'
og_description: Converti IGS in PDF, HTML, JPG e PNG usando GroupDocs.Viewer per Java.
  Configurazione dettagliata, esempi di codice e risoluzione dei problemi per gli
  sviluppatori Java.
og_image_alt: 'Developer guide: convert IGS files to PDF, HTML, JPG, PNG with GroupDocs.Viewer
  Java'
og_title: Converti IGS in PDF, HTML, JPG e PNG con GroupDocs.Viewer Java
schemas:
- author: GroupDocs
  dateModified: '2026-08-08'
  description: Learn how to convert IGS to PDF, HTML, JPG, and PNG using GroupDocs.Viewer
    for Java. Step‑by‑step guide, prerequisites, and troubleshooting for Java developers.
  headline: Convert IGS to PDF, HTML, JPG & PNG with GroupDocs.Viewer Java
  type: TechArticle
- questions:
  - answer: Yes. Iterate over a collection of file paths and invoke the appropriate
      `view` method for each file within the same `Viewer` instance.
    question: Can I convert multiple IGS files in a single run?
  - answer: Absolutely. `PdfViewOptions` offers `setPageSize(PageSize.A4)`, `PageSize.Letter`,
      and custom dimensions via `setCustomSize(width, height)`.
    question: Is it possible to customize the PDF page size?
  - answer: No. A single GroupDocs.Viewer license covers all supported formats, including
      HTML, JPG, PNG, and PDF.
    question: Do I need a separate license for each output format?
  - answer: The library reliably processes files up to **500 MB**; for models larger
      than 200 MB, allocate additional JVM memory and consider rendering in batches.
    question: How large can an IGS file be before performance degrades?
  - answer: GroupDocs.Viewer renders the default orientation defined in the IGS file.
      For custom views, preprocess the file with a CAD tool or adjust the model before
      conversion.
    question: Can I render only a specific view or orientation?
  type: FAQPage
tags:
- convert igs
- groupdocs.viewer
- java cad conversion
- pdf generation java
title: Converti IGS in PDF, HTML, JPG e PNG con GroupDocs.Viewer Java
type: docs
url: /it/java/file-formats-support/groupdocs-viewer-java-igs-rendering-html-jpg-png-pdf/
weight: 1
---

# Convertire IGS in PDF, HTML, JPG e PNG con GroupDocs.Viewer Java

If you need to **convertire IGS in PDF** (or to HTML, JPG, PNG) directly from a Java application, you’ve come to the right place. In this tutorial we’ll walk through everything you need—from installing the library to rendering the 3‑D model in the format that fits your project. You’ll understand why GroupDocs.Viewer is a solid choice for fast, reliable conversions and you’ll get ready‑to‑run code snippets you can drop into your own solution.

![Convert IGS Files to HTML, JPG, PNG, and PDF with GroupDocs.Viewer for Java](/viewer/file-formats-support/convert-igs-files-to-html-jpg-png-and-pdf-java.png)

## Risposte rapide
- **Posso convertire IGS in PDF con Java?** Sì, use `PdfViewOptions` together with the `Viewer` API.  
- **Quali formati di output sono supportati?** HTML, JPG, PNG e PDF are all natively handled.  
- **È necessaria una licenza per la produzione?** È richiesta una licenza commerciale; una prova gratuita ti consente di testare le funzionalità principali.  
- **Quale versione di Java è necessaria?** JDK 8 o superiore; la libreria funziona anche su Java 11, 17 e versioni successive.  
- **Maven è l'unico modo per aggiungere la libreria?** No, puoi anche usare Gradle o aggiungere manualmente i file JAR al tuo classpath.

## Che cos'è la conversione di IGS in PDF?
Convertire IGS in PDF significa trasformare un file CAD 3‑D neutro in un documento statico, visualizzabile universalmente. Questo ti consente di condividere le visualizzazioni del design con stakeholder che non dispongono di strumenti CAD, incorporare il rendering nei report o archiviare il modello per scopi di conformità.

## Perché utilizzare GroupDocs.Viewer per le conversioni IGS?
GroupDocs.Viewer elabora i file IGS senza richiedere alcun software CAD esterno. Supporta **oltre 50 formati di input e output**, può renderizzare assiemi contenenti **centinaia di parti** mantenendo l'uso della memoria sotto **200 MB**, e fornisce risultati in meno di **2 secondi** per modelli tipici su un server standard. Questi vantaggi quantificati lo rendono una scelta ad alte prestazioni e conveniente per le pipeline aziendali.

## Prerequisiti
- **GroupDocs.Viewer for Java** ≥ 25.2 (l'ultima versione stabile).  
- **JDK 8+** installato e configurato nel tuo IDE (IntelliJ IDEA, Eclipse, NetBeans, ecc.).  
- Conoscenza di base di Maven (opzionale ma consigliata per la gestione delle dipendenze).  

## Configurazione di GroupDocs.Viewer per Java

### Dipendenza Maven
Add the GroupDocs repository and the Viewer dependency to your `pom.xml`:

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

### Acquisizione della licenza
GroupDocs.Viewer offers three licensing options:
- **Prova gratuita** – utilizzo limitato, perfetta per test rapidi di proof‑of‑concept.  
- **Licenza temporanea** – set completo di funzionalità per un breve periodo di valutazione, ideale per progetti pilota.  
- **Licenza commerciale** – uso in produzione senza restrizioni, include supporto prioritario e aggiornamenti.

### Inizializzazione di base del viewer
The `Viewer` class is the entry point for all rendering operations. It loads the source file, parses the format, and exposes methods to produce the desired output.

```java
import com.groupdocs.viewer.Viewer;

public class ViewerSetup {
    public static void main(String[] args) {
        try (Viewer viewer = new Viewer("path/to/your/document.igs")) {
            // Configuration and rendering logic goes here.
        }
    }
}
```

## Rendering di IGS in HTML

### Come convertire IGS in HTML?
Carica il file IGS con un'istanza `Viewer` e passa un oggetto `HtmlViewOptions` che incorpora tutte le risorse necessarie. La chiamata restituisce un unico file HTML che contiene la vista 3‑D completa, facilitando l'inserimento nelle pagine web. Puoi anche personalizzare il rendering impostando opzioni come dimensione della pagina, colore di sfondo e se includere controlli interattivi.  
HtmlViewOptions configura come viene generato l'output HTML, includendo l'incorporamento delle risorse e il layout della pagina.

```java
import com.groupdocs.viewer.Viewer;
import com.groupdocs.viewer.options.HtmlViewOptions;
import java.nio.file.Path;
import static java.nio.file.Paths.get;

public class RenderIgsToHtml {
    public static void run() {
        Path outputDirectory = get("YOUR_OUTPUT_DIRECTORY");
        Path pageFilePathFormat = outputDirectory.resolve("IGS_result.html");

        try (Viewer viewer = new Viewer(get("YOUR_DOCUMENT_DIRECTORY/SAMPLE_IGS"))) {
            HtmlViewOptions options = HtmlViewOptions.forEmbeddedResources(pageFilePathFormat);
            viewer.view(options);
        }
    }
}
```

## Rendering di IGS in JPG

### Come convertire IGS in JPG?
Crea un oggetto `JpgViewOptions`, configura la risoluzione desiderata e la qualità di compressione, e lascia che il `Viewer` generi immagini raster per ogni pagina del modello. I file JPG generati possono essere salvati in una directory specificata, e puoi regolare il parametro di qualità per bilanciare la dimensione del file con la fedeltà visiva, utile per miniature o stampe ad alta risoluzione.  
JpgViewOptions specifica le impostazioni per la generazione di immagini JPG come risoluzione, qualità e directory di output.

```java
import com.groupdocs.viewer.Viewer;
import com.groupdocs.viewer.options.JpgViewOptions;
import java.nio.file.Path;
import static java.nio.file.Paths.get;

public class RenderIgsToJpg {
    public static void run() {
        Path outputDirectory = get("YOUR_OUTPUT_DIRECTORY");
        Path pageFilePathFormat = outputDirectory.resolve("IGS_result.jpg");

        try (Viewer viewer = new Viewer(get("YOUR_DOCUMENT_DIRECTORY/SAMPLE_IGS"))) {
            JpgViewOptions options = new JpgViewOptions(pageFilePathFormat);
            viewer.view(options);
        }
    }
}
```

## Rendering di IGS in PNG

### Come convertire IGS in PNG?
La classe `PngViewOptions` ti consente di produrre immagini senza perdita con trasparenza opzionale. Questo formato è ideale per sovrapporre il modello su sfondi colorati nei materiali di marketing. Puoi anche definire la risoluzione e il colore di sfondo per aderire alle linee guida del tuo brand, garantendo un aspetto coerente su tutti gli asset generati.  
PngViewOptions definisce i parametri per il rendering PNG, includendo risoluzione, trasparenza e colore di sfondo.

```java
import com.groupdocs.viewer.Viewer;
import com.groupdocs.viewer.options.PngViewOptions;
import java.nio file.Path;
import static java.nio.file.Paths.get;

public class RenderIgsToPng {
    public static void run() {
        Path outputDirectory = get("YOUR_OUTPUT_DIRECTORY");
        Path pageFilePathFormat = outputDirectory.resolve("IGS_result.png");

        try (Viewer viewer = new Viewer(get("YOUR_DOCUMENT_DIRECTORY/SAMPLE_IGS"))) {
            PngViewOptions options = new PngViewOptions(pageFilePathFormat);
            viewer.view(options);
        }
    }
}
```

## Rendering di IGS in PDF

### Come convertire IGS in PDF?
Usa `PdfViewOptions` per produrre un PDF paginato che preserva il layout visivo del modello 3‑D. Puoi anche incorporare i font e controllare la dimensione della pagina per rispettare le linee guida del branding aziendale. Impostazioni aggiuntive ti permettono di specificare la qualità dell'immagine, il livello di compressione e se includere un indice per assiemi multi‑pagina.  
PdfViewOptions controlla la creazione del PDF, consentendo configurazioni di dimensione della pagina, qualità dell'immagine e incorporamento dei font.

```java
import com.groupdocs.viewer.Viewer;
import com.groupdocs.viewer.options.PdfViewOptions;
import java.nio.file.Path;
import static java.nio.file.Paths.get;

public class RenderIgsToPdf {
    public static void run() {
        Path outputDirectory = get("YOUR_OUTPUT_DIRECTORY");
        Path pageFilePathFormat = outputDirectory.resolve("IGS_result.pdf");

        try (Viewer viewer = new Viewer(get("YOUR_DOCUMENT_DIRECTORY/SAMPLE_IGS"))) {
            PdfViewOptions options = new PdfViewOptions(pageFilePathFormat);
            viewer.view(options);
        }
    }
}
```

## Applicazioni pratiche
- **Portali web** – incorpora modelli renderizzati in HTML direttamente nei configuratori di prodotto, consentendo ai clienti di ruotare e zoomare senza installare plugin.  
- **Asset di marketing** – genera immagini JPG/PNG ad alta risoluzione per brochure, presentazioni e post sui social media.  
- **Documentazione tecnica** – includi rendering PDF di modelli CAD nei manuali utente, assicurando che gli ingegneri possano visualizzare i progetti offline.  
- **Assicurazione qualità** – automatizza la creazione di miniature per migliaia di file IGS, accelerando i flussi di lavoro di ispezione visiva.

## Problemi comuni e soluzioni

| Issue | Solution |
|-------|----------|
| **Cartella di output non trovata** | Verifica il percorso passato a `Path outputDirectory` e assicurati che il processo Java abbia permessi di scrittura sulla directory di destinazione. |
| **Pagine vuote nel PDF** | Conferma che il file IGS sorgente non sia corrotto; aprilo prima in un visualizzatore CAD nativo. |
| **Rendering lento per assiemi di grandi dimensioni** | Aumenta l'heap JVM (`-Xmx2g` o più) e considera il rendering pagina per pagina usando `viewer.getPageCount()` per elaborare i blocchi. |
| **Font mancanti nel PDF** | Usa `PdfViewOptions` per incorporare i font richiesti o installa i font mancanti sul server che ospita il servizio di conversione. |

## Domande frequenti

**Q: Posso convertire più file IGS in un'unica esecuzione?**  
A: Sì. Itera su una collezione di percorsi file e invoca il metodo `view` appropriato per ciascun file all'interno della stessa istanza `Viewer`.

**Q: È possibile personalizzare la dimensione della pagina PDF?**  
A: Assolutamente. `PdfViewOptions` offre `setPageSize(PageSize.A4)`, `PageSize.Letter` e dimensioni personalizzate tramite `setCustomSize(width, height)`.

**Q: È necessaria una licenza separata per ogni formato di output?**  
A: No. Una singola licenza GroupDocs.Viewer copre tutti i formati supportati, inclusi HTML, JPG, PNG e PDF.

**Q: Quanto grande può essere un file IGS prima che le prestazioni peggiorino?**  
A: La libreria elabora in modo affidabile file fino a **500 MB**; per modelli più grandi di 200 MB, assegna più memoria JVM e considera il rendering in batch.

**Q: Posso renderizzare solo una vista o orientamento specifico?**  
A: GroupDocs.Viewer renderizza l'orientamento predefinito definito nel file IGS. Per viste personalizzate, preelabora il file con uno strumento CAD o regola il modello prima della conversione.

---

**Ultimo aggiornamento:** 2026-08-08  
**Testato con:** GroupDocs.Viewer 25.2 for Java  
**Autore:** GroupDocs

## Tutorial correlati

- [convertire cdr in html, jpg, png, pdf con GroupDocs.Viewer Java](/viewer/java/file-formats-support/render-cdr-documents-groupdocs-viewer-java-guide/)
- [Come convertire pdf in html e ottimizzare la qualità dell'immagine in Java con GroupDocs.Viewer](/viewer/java/advanced-rendering/adjust-image-quality-groupdocs-viewer-java/)