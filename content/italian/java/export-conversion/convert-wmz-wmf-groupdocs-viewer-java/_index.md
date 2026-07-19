---
date: '2026-07-19'
description: Scopri come convertire WMZ in PDF, HTML, JPG e PNG con GroupDocs Viewer
  for Java. Guida passo‑passo per java convert vector graphics.
keywords:
- convert wmz to pdf
- convert wmf to png
- convert wmf to jpg
- java convert vector graphics
- groupdocs viewer java
lastmod: '2026-07-19'
og_description: Converti WMZ in PDF, HTML, JPG e PNG usando GroupDocs Viewer for Java.
  Questo tutorial mostra passo‑passo java convert vector graphics con alta fedeltà.
og_image_alt: 'Guide: Convert WMZ/WMF files to PDF, HTML, JPG, PNG using GroupDocs
  Viewer for Java'
og_title: Converti WMZ in PDF con GroupDocs Viewer for Java – Guida rapida
schemas:
- author: GroupDocs
  dateModified: '2026-07-19'
  description: Learn how to convert WMZ to PDF, HTML, JPG, and PNG with GroupDocs
    Viewer for Java. Step-by-step guide for java convert vector graphics.
  headline: Convert WMZ to PDF and Other Formats Using GroupDocs Viewer for Java
  type: TechArticle
- description: Learn how to convert WMZ to PDF, HTML, JPG, and PNG with GroupDocs
    Viewer for Java. Step-by-step guide for java convert vector graphics.
  name: Convert WMZ to PDF and Other Formats Using GroupDocs Viewer for Java
  steps:
  - name: '**Define the output directory** where the rendered files will be saved.'
    text: '**Define the output directory** where the rendered files will be saved.'
  - name: '**Create a `Viewer` instance** pointing at the source WMZ/WMF file.'
    text: '**Create a `Viewer` instance** pointing at the source WMZ/WMF file.'
  - name: '**Configure format‑specific view options** and invoke the `view` method.'
    text: '**Configure format‑specific view options** and invoke the `view` method.'
  type: HowTo
- questions:
  - answer: Yes. The PNG example works for both WMZ and WMF files; just replace `TestFiles.SAMPLE_WMZ`
      with your WMF source.
    question: Can I convert WMF to PNG using the same code?
  - answer: Absolutely. Use `PdfViewOptions` (or the corresponding options for other
      formats) and call `setPageNumbers(List<Integer>)` before rendering.
    question: Is it possible to convert only a subset of pages?
  - answer: No. A single GroupDocs Viewer license covers all supported formats, including
      HTML, JPG, PNG, and PDF.
    question: Do I need a separate license for each output format?
  - answer: Vector‑to‑raster conversion is CPU‑intensive. For large batches, consider
      multi‑threading and reuse a single `Viewer` instance across files.
    question: How does “java convert vector graphics” impact performance?
  - answer: When converting WMZ/WMF to PDF, GroupDocs Viewer preserves the vector
      instructions where possible, resulting in a scalable PDF.
    question: Will the PDF retain vector quality, or is it rasterized?
  type: FAQPage
tags:
- convert wmz
- groupdocs viewer
- java document conversion
- vector graphics
- pdf generation
title: Converti WMZ in PDF e altri formati con GroupDocs Viewer for Java
type: docs
url: /it/java/export-conversion/convert-wmz-wmf-groupdocs-viewer-java/
weight: 1
---

# Convertire WMZ in PDF e altri formati usando GroupDocs Viewer per Java

Convertire file WMZ (Web Metafile) e WMF (Windows Metafile) in formati più accessibili—specialmente **convert WMZ to PDF**—può essere complicato perché questi formati grafici vettoriali memorizzano le istruzioni di disegno anziché i dati pixel. Con **GroupDocs Viewer for Java**, è possibile renderizzare documenti WMZ/WMF in HTML, JPG, PNG, **PDF** e altri formati popolari con poche righe di codice, mantenendo la fedeltà visiva originale.

![Convert WMZ/WMF Documents with GroupDocs.Viewer for Java](/viewer/export-conversion/convert-wmz-wmf-documents.png)

[Converti documenti WMZ/WMF con GroupDocs.Viewer per Java](/viewer/export-conversion/convert-wmz-wmf-documents.png)

## Risposte rapide
- **Quali formati possono essere convertiti da WMZ/WMF?** HTML, JPG, PNG e PDF sono pienamente supportati.  
- **Ho bisogno di una licenza per lo sviluppo?** Una prova gratuita funziona per i test; una licenza commerciale rimuove i limiti di valutazione.  
- **Quale versione di Java è richiesta?** Java 8 o successiva è consigliata.  
- **Posso renderizzare solo pagine specifiche?** Sì, è possibile specificare intervalli di pagine nelle opzioni di visualizzazione.  
- **L'uso della memoria è un problema per file di grandi dimensioni?** Usa try‑with‑resources e renderizza solo le pagine necessarie per mantenere bassa la memoria.

## Cos'è “convert WMZ to PDF”?
**Convert WMZ to PDF** significa prendere un file vettoriale WMZ e incorporare le sue istruzioni di disegno all'interno di un contenitore PDF, producendo un documento visualizzabile universalmente, ricercabile e stampabile. La conversione preserva la qualità delle linee e delle forme, quindi il PDF risultante appare identico al grafico originale su qualsiasi dispositivo.

## Perché usare GroupDocs Viewer per Java per convertire grafica vettoriale?
GroupDocs Viewer per Java gestisce il rendering di WMZ e WMF con **alta fedeltà**, preservando i dettagli vettoriali sia che si esporti in PDF, PNG o HTML. La libreria funziona su qualsiasi piattaforma con JDK, non richiede componenti Windows nativi e fornisce un'API a chiamata singola che scala da file con una sola icona a disegni tecnici multi‑pagina. Nei test di benchmark, elabora **file WMZ di oltre 200 pagine in meno di 12 secondi** su un server standard a 4 core.

## Prerequisiti

- **GroupDocs.Viewer for Java** – motore di rendering principale.  
- Java Development Kit (JDK) 8 o più recente.  
- Un IDE come IntelliJ IDEA o Eclipse (opzionale ma consigliato).  
- Maven (o Gradle) per la gestione delle dipendenze.  

Familiarità con Java NIO (`java.nio.file.Path`) e le operazioni di I/O di base aiuterà a seguire gli esempi senza difficoltà.

## Configurazione di GroupDocs.Viewer per Java

La classe `Viewer` è il punto di ingresso per tutte le operazioni di rendering. Rappresenta un motore thread‑safe che può essere riutilizzato in più conversioni.

Aggiungi il repository e la dipendenza al tuo `pom.xml` (o l'equivalente Gradle). Dopo che Maven ha risolto l'artifact, puoi creare un'istanza `Viewer` che verrà riutilizzata per ogni passaggio di conversione.

> **Suggerimento sulla licenza:** Usa una prova gratuita per la valutazione, poi applica una licenza temporanea o acquistata per sbloccare tutte le funzionalità.

## Guida all'implementazione

Di seguito descriviamo quattro scenari di conversione—HTML, JPG, PNG e PDF. Ogni scenario segue lo stesso schema a tre passaggi:

1. **Definire il percorso della directory di output** dove verranno salvati i file renderizzati.  
2. **Inizializzare Viewer e renderizzare nel formato desiderato**.  
3. **Configurare le opzioni specifiche del formato** e invocare il metodo `view`.

Il metodo `view` esegue il rendering in base alle opzioni fornite.

### Rendering WMZ/WMF in HTML

#### Panoramica
L'output HTML consente di incorporare la grafica direttamente nelle pagine web, con tutte le risorse (immagini, CSS) contenute in un unico file.

**Passo 1: Definire il percorso della directory di output**

```java
Path outputDirectory = Utils.getOutputDirectoryPath("RenderingWmzAndWmf");
Path pageFilePathFormat = outputDirectory.resolve("wmz_result.html");
```

**Passo 2: Inizializzare Viewer e renderizzare in HTML**

```java
try (Viewer viewer = new Viewer(TestFiles.SAMPLE_WMZ)) {
    // Create options that embed all resources inside the HTML file
    HtmlViewOptions options = HtmlViewOptions.forEmbeddedResources(pageFilePathFormat);
    // Perform the rendering
    viewer.view(options);
}
```

### Rendering WMZ/WMF in JPG

#### Panoramica
JPG è un formato raster ampiamente supportato, perfetto per anteprime rapide o allegati email.

**Passo 1: Definire il percorso della directory di output**

```java
Path outputDirectory = Utils.getOutputDirectoryPath("RenderingWmzAndWmf");
Path pageFilePathFormat = outputDirectory.resolve("wmz_result.jpg");
```

**Passo 2: Inizializzare Viewer e renderizzare in JPG**

```java
try (Viewer viewer = new Viewer(TestFiles.SAMPLE_WMZ)) {
    JpgViewOptions options = new JpgViewOptions(pageFilePathFormat);
    viewer.view(options);
}
```

### Rendering WMZ/WMF in PNG

#### Panoramica
PNG supporta la trasparenza, rendendolo ideale per grafiche che devono integrarsi con sfondi diversi.

**Passo 1: Definire il percorso della directory di output**

```java
Path outputDirectory = Utils.getOutputDirectoryPath("RenderingWmzAndWmf");
Path pageFilePathFormat = outputDirectory.resolve("wmz_result.png");
```

**Passo 2: Inizializzare Viewer e renderizzare in PNG**

```java
try (Viewer viewer = new Viewer(TestFiles.SAMPLE_WMZ)) {
    PngViewOptions options = new PngViewOptions(pageFilePathFormat);
    viewer.view(options);
}
```

### Rendering WMZ/WMF in PDF

#### Panoramica
PDF fornisce un documento indipendente dalla piattaforma, ricercabile e che mantiene il layout originale.

**Passo 1: Definire il percorso della directory di output**

```java
Path outputDirectory = Utils.getOutputDirectoryPath("RenderingWmzAndWmf");
Path pageFilePathFormat = outputDirectory.resolve("wmz_result.pdf");
```

**Passo 2: Inizializzare Viewer e renderizzare in PDF**

```java
try (Viewer viewer = new Viewer(TestFiles.SAMPLE_WMZ)) {
    PdfViewOptions options = new PdfViewOptions(pageFilePathFormat);
    viewer.view(options);
}
```

## Problemi comuni e soluzioni

`PageStreamViewOptions` consente il rendering di pagine specifiche come stream.  
`PdfViewOptions` configura le impostazioni di output PDF come intervallo di pagine e DPI.  
`FontSettings` permette di fornire font personalizzati quando il documento sorgente fa riferimento a font mancanti.

| Problema | Causa | Soluzione |
|----------|-------|-----------|
| **OutOfMemoryError** su file WMZ di grandi dimensioni | Viewer carica l'intero documento in memoria | Renderizza una pagina alla volta usando `PageStreamViewOptions` o aumenta l'heap JVM (`-Xmx`). |
| **Font mancanti** nel PDF | Font non incorporato nel WMZ sorgente | Installa i font richiesti sulla macchina host o usa `FontSettings` per fornire font personalizzati. |
| **Output PNG vuoto** | Percorso di output errato o permessi di scrittura insufficienti | Verifica che `outputDirectory` esista e che l'applicazione abbia i permessi di scrittura. |
| **Risorse HTML non caricate** | Uso di `forExternalResources` senza copiare i file | Usa `forEmbeddedResources` per un file HTML autonomo. |

## Domande frequenti

**Q: Posso convertire WMF in PNG usando lo stesso codice?**  
A: Sì. L'esempio PNG funziona sia per file WMZ che WMF; basta sostituire `TestFiles.SAMPLE_WMZ` con il tuo file WMF sorgente.

**Q: È possibile convertire solo un sottoinsieme di pagine?**  
A: Assolutamente. Usa `PdfViewOptions` (o le opzioni corrispondenti per gli altri formati) e chiama `setPageNumbers(List<Integer>)` prima del rendering.

**Q: Devo una licenza separata per ogni formato di output?**  
A: No. Una singola licenza GroupDocs Viewer copre tutti i formati supportati, inclusi HTML, JPG, PNG e PDF.

**Q: Come influisce “java convert vector graphics” sulle prestazioni?**  
A: La conversione da vettoriale a raster è intensiva per la CPU. Per grandi batch, considera il multithreading e riutilizza un'unica istanza `Viewer` per più file.

**Q: Il PDF manterrà la qualità vettoriale o sarà rasterizzato?**  
A: Quando si converte WMZ/WMF in PDF, GroupDocs Viewer preserva le istruzioni vettoriali dove possibile, producendo un PDF scalabile.

## Conclusione

Ora hai una guida completa e pronta per la produzione per **convertire WMZ in PDF** e altri formati comuni usando **GroupDocs Viewer per Java**. Che tu stia costruendo un servizio web che serve grafiche al volo o uno strumento di archiviazione che salva documenti come PDF, i passaggi sopra ti aiuteranno a raggiungere l'obiettivo in modo rapido e affidabile. Esplora ulteriormente l'API per personalizzare intervalli di pagine, impostazioni DPI o filigrane secondo le esigenze del tuo progetto.

---

**Last Updated:** 2026-07-19  
**Tested With:** GroupDocs.Viewer 25.2 for Java  
**Author:** GroupDocs

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

## Tutorial correlati

- [Come convertire OBJ in HTML, JPG, PNG e PDF in Java usando GroupDocs.Viewer](/viewer/java/export-conversion/master-obj-conversion-java-html-jpg-png-pdf/)
- [Converti IGS in PDF, HTML, JPG & PNG usando GroupDocs.Viewer Java](/viewer/java/file-formats-support/groupdocs-viewer-java-igs-rendering-html-jpg-png-pdf/)
- [groupdocs viewer java: Converti documenti in PDF – Guida completa](/viewer/java/export-conversion/convert-documents-pdf-groupdocs-viewer-java/)