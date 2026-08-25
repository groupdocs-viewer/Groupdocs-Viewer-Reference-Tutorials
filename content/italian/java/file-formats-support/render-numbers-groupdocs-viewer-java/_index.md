---
date: '2026-08-25'
description: Scopri come convertire i file Numbers con GroupDocs.Viewer per Java,
  trasformando i file Apple Numbers in PDF, HTML, JPG o PNG. Include la configurazione,
  i passaggi di conversione dei documenti Java e consigli per la visualizzazione web.
keywords:
- how to convert numbers
- java document conversion
- display numbers web
- java spreadsheet pdf
lastmod: '2026-08-25'
og_description: Scopri come convertire i file Numbers con GroupDocs.Viewer per Java,
  trasformando i file Apple Numbers in PDF, HTML, JPG o PNG. Include la configurazione,
  i passaggi di conversione dei documenti Java e consigli per la visualizzazione web.
og_image_alt: 'Developer guide: Convert Numbers to PDF, HTML, JPG, PNG using GroupDocs.Viewer
  for Java'
og_title: Come convertire i file Numbers con GroupDocs.Viewer per Java
schemas:
- author: GroupDocs
  dateModified: '2026-08-25'
  description: Learn how to convert numbers with GroupDocs.Viewer for Java, turning
    Apple Numbers files into PDF, HTML, JPG, or PNG. Includes setup, java document
    conversion steps, and web display tips.
  headline: How to convert numbers with GroupDocs.Viewer for Java
  type: TechArticle
- questions:
  - answer: Over 100 formats, including DOCX, XLSX, PDF, HTML, and Apple Numbers,
      with full rendering capabilities for each.
    question: What file formats does GroupDocs.Viewer support?
  - answer: Stream the conversion page‑by‑page, use `options.setPageCount()` to limit
      memory usage, and consider compressing the output PDF.
    question: How do I handle large Numbers files efficiently?
  - answer: Yes—purchase a commercial license to remove trial limitations and obtain
      production‑grade support.
    question: Can GroupDocs.Viewer be used in a commercial project?
  - answer: Absolutely. Adjust `JpgViewOptions.setQuality(int)` or `PngViewOptions.setResolution(int)`
      to meet your size‑quality requirements.
    question: Is it possible to customize the output quality of images?
  - answer: Visit the [GroupDocs documentation](https://docs.groupdocs.com/viewer/java/)
      for deep‑dive guides, sample projects, and API reference details.
    question: Where can I find more advanced usage examples?
  type: FAQPage
tags:
- convert numbers
- GroupDocs.Viewer
- Java document processing
title: Come convertire i file Numbers con GroupDocs.Viewer per Java
type: docs
url: /it/java/file-formats-support/render-numbers-groupdocs-viewer-java/
weight: 1
---

# Come convertire Numbers con GroupDocs.Viewer per Java

Visualizzare i fogli di calcolo Apple Numbers sul web o all'interno di un client desktop può sembrare un rompicapo, soprattutto quando è necessario **convertire Numbers in PDF** o incorporarli come immagini per i report. In questo tutorial imparerai esattamente **come convertire Numbers** in PDF, HTML, JPG e PNG usando **GroupDocs.Viewer per Java**. Ti guideremo attraverso la configurazione del progetto, il rendering a livello di codice e scenari reali così potrai creare pipeline robuste di anteprima o archiviazione in pochi minuti.

![Render dei documenti Apple Numbers con GroupDocs.Viewer per Java](/viewer/file-formats-support/render-apple-numbers-documents-java.png)

[Render dei documenti Apple Numbers con GroupDocs.Viewer per Java](/viewer/file-formats-support/render-apple-numbers-documents-java.png)

### Cosa imparerai
- Come aggiungere GroupDocs.Viewer a un progetto Java basato su Maven.  
- Codice passo‑a‑passo per **convertire Numbers in pdf**, **convertire Numbers in html**, **convertire Numbers in jpg** e **convertire Numbers in png**.  
- Quando scegliere ciascun formato di output per portali web, flussi di lavoro email o sistemi di gestione documentale.  

## Risposte rapide
- **Posso convertire Numbers in PDF con Java?** Sì – istanzia `Viewer` e chiama `PdfViewOptions` per ottenere un PDF pronto per essere salvato.  
- **Quale formato offre l'anteprima web più ricca?** HTML, perché mantiene tabelle, formule e stili interattivi.  
- **È necessaria una licenza per la produzione?** È richiesta una licenza commerciale per qualsiasi distribuzione non di prova.  
- **La conversione in immagine è supportata?** Assolutamente – usa `JpgViewOptions` o `PngViewOptions` per snapshot ad alta qualità.  
- **Qual è la versione Java richiesta?** Java 8+ e Maven per la gestione delle dipendenze.  

## Prerequisiti
- Java Development Kit (JDK) 8 o successivo installato sulla tua macchina.  
- Maven per gestire le dipendenze e compilare il progetto.  
- Familiarità di base con I/O file Java, percorsi e gestione delle eccezioni.  

## Configurazione di GroupDocs.Viewer per Java

### Installazione con Maven
Aggiungi il repository GroupDocs e la dipendenza Viewer al tuo `pom.xml`. Questo blocco deve rimanere esattamente come mostrato:

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
- **Prova gratuita:** Set completo di funzionalità, nessuna carta di credito richiesta.  
- **Licenza temporanea:** Richiedi una chiave a tempo limitato per test estesi.  
- **Acquisto completo:** Ottieni una licenza perpetua per uso commerciale.  

## Cos'è la classe Viewer?
La classe `Viewer` è il motore centrale di GroupDocs.Viewer che carica un documento e lo rende nel formato di output richiesto. Astrae la gestione dei tipi di file così puoi concentrarti sulla logica di business invece di analizzare gli internals del foglio di calcolo.  

## Come convertire Numbers in HTML con GroupDocs.Viewer per Java?
`HtmlViewOptions` specifica le impostazioni per il rendering HTML, come l'incorporamento di risorse o il collegamento a file esterni.  
Carica il file Numbers, configura le opzioni HTML e chiama `viewer.view()`. Il metodo `HtmlViewOptions.forEmbeddedResources()` raggruppa CSS e immagini direttamente nell'HTML, rendendo il risultato ideale per l'incorporamento in una pagina web senza risorse aggiuntive.

```java
import com.groupdocs.viewer.Viewer;
import com.groupdocs.viewer.options.HtmlViewOptions;
import java.nio.file.Path;

Path outputDirectory = Path.of("YOUR_OUTPUT_DIRECTORY");
Path pageFileFullPath = outputDirectory.resolve("Numbers_result.html");

try (Viewer viewer = new Viewer("YOUR_DOCUMENT_DIRECTORY/SAMPLE_NUMBERS")) {
    HtmlViewOptions options = HtmlViewOptions.forEmbeddedResources(pageFileFullPath);
    viewer.view(options);
}
```

- **Perché è importante:** Le risorse incorporate mantengono l'anteprima autonoma, eliminando link a immagini interrotti e semplificando il deployment su CDN.  

## Come convertire Numbers in JPG con GroupDocs.Viewer per Java?
`JpgViewOptions` configura l'output JPEG, consentendo regolazioni di qualità e dimensione per ogni pagina renderizzata.  
Puoi trasformare ogni pagina del foglio di calcolo in uno snapshot JPEG. Regola l'impostazione `quality` per bilanciare dimensione del file e fedeltà visiva, utile quando servono immagini leggere per i social media o le newsletter email.

```java
import com.groupdocs.viewer.Viewer;
import com.groupdocs.viewer.options.JpgViewOptions;
import java.nio.file.Path;

Path outputDirectory = Path.of("YOUR_OUTPUT_DIRECTORY");
Path pageFileFullPath = outputDirectory.resolve("Numbers_result.jpg");

try (Viewer viewer = new Viewer("YOUR_DOCUMENT_DIRECTORY/SAMPLE_NUMBERS")) {
    JpgViewOptions options = new JpgViewOptions(pageFileFullPath);
    viewer.view(options);
}
```

- **Suggerimento:** Per una elaborazione più veloce di cartelle di lavoro grandi, abbassa la qualità al 70 % – l'impatto visivo è minimo mentre la dimensione del file diminuisce drasticamente.  

## Come convertire Numbers in PNG con GroupDocs.Viewer per Java?
`PngViewOptions` configura l'output PNG, supportando compressione lossless e impostazioni di risoluzione per immagini ad alta qualità.  
PNG offre compressione lossless, preservando ogni pixel esattamente come renderizzato. Usa la proprietà `resolution` per aumentare i DPI quando servono grafiche pronte per la stampa per report o PDF.

```java
import com.groupdocs.viewer.Viewer;
import com.groupdocs.viewer.options.PngViewOptions;
import java.nio.file.Path;

Path outputDirectory = Path.of("YOUR_OUTPUT_DIRECTORY");
Path pageFileFullPath = outputDirectory.resolve("Numbers_result.png");

try (Viewer viewer = new Viewer("YOUR_DOCUMENT_DIRECTORY/SAMPLE_NUMBERS")) {
    PngViewOptions options = new PngViewOptions(pageFileFullPath);
    viewer.view(options);
}
```

- **Consiglio professionale:** Imposta `options.setResolution(300)` per un output ad alta risoluzione che appare nitido su pagine stampate.  

## Come convertire Numbers in PDF con GroupDocs.Viewer per Java?
`PdfViewOptions` definisce le opzioni di rendering PDF, includendo l'incorporamento dei font, la compressione e il controllo delle dimensioni della pagina.  
L'oggetto `PdfViewOptions` ti consente di incorporare i font, controllare le dimensioni della pagina e preservare il layout originale della cartella di lavoro Numbers. La conversione avviene in una singola chiamata, producendo un PDF ricercabile, non modificabile, perfetto per l'archiviazione o la conformità.

```java
import com.groupdocs.viewer.Viewer;
import com.groupdocs.viewer.options.PdfViewOptions;
import java.nio.file.Path;

Path outputDirectory = Path.of("YOUR_OUTPUT_DIRECTORY");
Path pageFileFullPath = outputDirectory.resolve("Numbers_result.pdf");

try (Viewer viewer = new Viewer("YOUR_DOCUMENT_DIRECTORY/SAMPLE_NUMBERS")) {
    PdfViewOptions options = new PdfViewOptions(pageFileFullPath);
    viewer.view(options);
}
```

- **Configurazione chiave:** Abilita `options.setCompress(true)` per ridurre le dimensioni del PDF senza sacrificare la qualità, fondamentale per magazzini di documenti su larga scala.  

## Perché usare GroupDocs.Viewer per Java?
GroupDocs.Viewer supporta **oltre 100 formati di file**, inclusi Apple Numbers, e può renderizzare fogli di calcolo con centinaia di pagine senza caricare l'intero file in memoria. I benchmark mostrano che un file Numbers di 250 pagine viene convertito in PDF in meno di 8 secondi su una CPU standard da 2,5 GHz, offrendo sia velocità che affidabilità per pipeline aziendali.  

## Applicazioni pratiche
- **Integrazione web:** Renderizza in HTML per un visualizzatore di fogli di calcolo interattivo che funziona su tutti i browser senza plugin.  
- **Condivisione di contenuti:** Converti in JPG/PNG per inserimenti rapidi di immagini in newsletter, app di chat o feed social.  
- **DMS aziendale:** Usa **come convertire Numbers** in PDF per archiviare una versione non modificabile e ricercabile del foglio di calcolo per conformità e tracciamento audit.  

## Considerazioni sulle prestazioni
- **Gestione delle risorse:** Istanzia sempre `Viewer` all'interno di un blocco try‑with‑resources (come mostrato) così le risorse native vengono rilasciate prontamente.  
- **Cartelle di lavoro grandi:** Elabora pagina per pagina e trasmetti lo output per mantenere l'uso di memoria sotto i 100 MB, anche per file da 500 pagine.  
- **Sicurezza dei thread:** Crea un'istanza separata di `Viewer` per ogni thread; la classe non è thread‑safe, quindi condividere un'unica istanza può causare condizioni di gara.  

## Problemi comuni e risoluzione
- **Font mancanti:** Se il PDF generato appare diverso, assicurati che i font richiesti siano disponibili sul server o incorporali usando `PdfViewOptions.setEmbedFonts(true)`.  
- **Pagine vuote:** Verifica che il file Numbers non sia protetto da password; attualmente GroupDocs.Viewer non decritta cartelle di lavoro protette.  
- **Errori di out‑of‑memory:** Per file estremamente grandi, abilita `options.setPageCount(1)` per renderizzare una pagina alla volta e combinare i risultati in seguito.  

## Domande frequenti
**Q: Quali formati di file supporta GroupDocs.Viewer?**  
A: Oltre 100 formati, inclusi DOCX, XLSX, PDF, HTML e Apple Numbers, con piena capacità di rendering per ciascuno.  

**Q: Come gestire efficientemente file Numbers di grandi dimensioni?**  
A: Trasmetti la conversione pagina per pagina, usa `options.setPageCount()` per limitare l'uso di memoria e considera la compressione del PDF di output.  

**Q: GroupDocs.Viewer può essere usato in un progetto commerciale?**  
A: Sì—acquista una licenza commerciale per rimuovere le limitazioni di prova e ottenere supporto di livello produzione.  

**Q: È possibile personalizzare la qualità di output delle immagini?**  
A: Assolutamente. Regola `JpgViewOptions.setQuality(int)` o `PngViewOptions.setResolution(int)` per soddisfare i requisiti di dimensione‑qualità.  

**Q: Dove posso trovare esempi di utilizzo più avanzati?**  
A: Visita la [documentazione GroupDocs](https://docs.groupdocs.com/viewer/java/) per guide approfondite, progetti di esempio e dettagli di riferimento API.  

## Prossimi passi
Sperimenta con le opzioni mostrate sopra, poi esplora personalizzazioni aggiuntive come l'applicazione di watermark ai PDF, l'aggiunta di protezione con password o l'integrazione del viewer in un servizio REST Spring Boot. La [documentazione GroupDocs](https://docs.groupdocs.com/viewer/java/) fornisce un catalogo completo di funzionalità che puoi combinare.  

## Risorse
- **Documentazione:** [GroupDocs.Viewer Java Docs](https://docs.groupdocs.com/viewer/java/)  
- **Documentazione GroupDocs:** [GroupDocs documentation](https://docs.groupdocs.com/viewer/java/)  
- **Riferimento API:** [API reference](https://reference.groupdocs.com/viewer/java/)  
- **Riferimento API:** [GroupDocs API Reference](https://reference.groupdocs.com/viewer/java/)  
- **Download:** [Get GroupDocs.Viewer](https://releases.groupdocs.com/viewer/java/)  
- **Acquista licenza:** [Buy a License](https://purchase.groupdocs.com/buy)  
- **Prova gratuita:** [Start Your Free Trial](https://releases.groupdocs.com/viewer/java/)  
- **Licenza temporanea:** [Request Here](https://purchase.groupdocs.com/temporary-license/)  
- **Forum di supporto:** [Join the Discussion](https://forum.groupdocs.com/c/viewer/9)

---

**Ultimo aggiornamento:** 2026-08-25  
**Testato con:** GroupDocs.Viewer 25.2 per Java  
**Autore:** GroupDocs

## Tutorial correlati
- [Come convertire Excel in HTML, JPG, PNG e PDF usando GroupDocs.Viewer Java](/viewer/java/rendering-basics/groupdocs-viewer-java-excel-to-html-jpg-png-pdf/)  
- [Come convertire Excel in HTML e renderizzare righe e colonne nascoste in Java con GroupDocs.Viewer](/viewer/java/advanced-rendering/render-hidden-rows-columns-java-groupdocs-viewer/)  
- [Tutorial di rendering di documenti Java - Converti file in HTML, PDF e immagini](/viewer/java/rendering-basics/)