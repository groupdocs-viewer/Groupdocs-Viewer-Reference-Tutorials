---
date: '2026-09-30'
description: Scopri come ruotare la pagina di 90 gradi in Java usando GroupDocs Viewer,
  inclusi configurazione, codice e consigli sulle prestazioni.
keywords:
- rotate page 90 degrees
- how to rotate pdf
- GroupDocs Viewer Java rotation
- Java document rendering
- PDF page transformation
lastmod: '2026-09-30'
og_description: Ruota la pagina di 90 gradi in Java usando GroupDocs Viewer. Guida
  passo‑passo, consigli sulle prestazioni e casi d'uso reali per gli sviluppatori.
og_image_alt: Illustration of rotating the first page of a document using GroupDocs
  Viewer for Java
og_title: Ruota la pagina di 90 gradi con GroupDocs Viewer per Java
schemas:
- author: GroupDocs
  dateModified: '2026-09-30'
  description: Learn how to rotate page 90 degrees in Java using GroupDocs Viewer,
    including setup, code, and performance tips.
  headline: Rotate page 90 degrees with GroupDocs Viewer for Java
  type: TechArticle
- description: Learn how to rotate page 90 degrees in Java using GroupDocs Viewer,
    including setup, code, and performance tips.
  name: Rotate page 90 degrees with GroupDocs Viewer for Java
  steps:
  - name: '**Presentation adjustments** – Convert a portrait slide to landscape on
      the fly for better visual impact.'
    text: '**Presentation adjustments** – Convert a portrait slide to landscape on
      the fly for better visual impact.'
  - name: '**Bulk document correction** – Automate fixing of scanned PDFs that were
      captured sideways, saving hours of manual work.'
    text: '**Bulk document correction** – Automate fixing of scanned PDFs that were
      captured sideways, saving hours of manual work.'
  - name: '**Print‑ready output** – Ensure landscape graphics print correctly on portrait‑oriented
      paper without manual rotation in the printer driver.'
    text: '**Print‑ready output** – Ensure landscape graphics print correctly on portrait‑oriented
      paper without manual rotation in the printer driver.'
  type: HowTo
- questions:
  - answer: Yes—invoke `rotatePage()` for each page number you need to rotate, either
      in a loop or by chaining calls.
    question: Can I rotate multiple pages at once?
  - answer: Not directly. You would need to render the document again without the
      rotation options.
    question: Is there a way to undo the rotation after rendering?
  - answer: DOCX, PDF, PPTX, XLSX, and many other formats listed in the official documentation.
    question: Which file formats support page rotation in GroupDocs Viewer?
  - answer: Wrap the rotation logic in a loop that iterates over a collection of file
      paths, applying the same `rotatePage` configuration to each file.
    question: How can I rotate pages in a batch of documents automatically?
  - answer: Enclose the Viewer usage in a `try‑catch` block, log the exception details,
      and optionally continue processing the next file to avoid a single failure stopping
      the whole batch.
    question: What is the best practice for handling errors during rotation?
  type: FAQPage
tags:
- rotate page
- GroupDocs Viewer
- Java PDF processing
- document automation
title: Ruota la pagina di 90 gradi con GroupDocs Viewer per Java
type: docs
url: /it/java/advanced-rendering/rotate-first-page-document-groupdocs-viewer-java/
weight: 1
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Ruota la pagina di 90 gradi con GroupDocs Viewer per Java

If you need to **ruotare la pagina di 90 gradi** in a document—whether it’s a PDF, Word file, or spreadsheet—doing it programmatically in Java saves time, removes manual errors, and lets you embed the operation into automated pipelines. In this advanced guide you’ll learn how to rotate the first page of any supported document using **GroupDocs Viewer for Java**, why this capability matters in real‑world projects, and how to keep the process lightweight and memory‑efficient.

![Rotate the First Page of a Document with GroupDocs.Viewer for Java](/viewer/advanced-rendering/rotate-the-first-page-of-a-document-java.png)

## Risposte rapide
- **Cosa significa “rotate page 90 degrees”?** Gira la pagina selezionata in senso orario di un quarto di giro.  
- **Quale libreria gestisce la rotazione?** GroupDocs Viewer for Java fornisce il metodo `rotatePage`.  
- **Posso ruotare le pagine PDF con Java?** Sì—usa la stessa chiamata `rotatePage`; funziona per PDF, DOCX, XLSX e altri.  
- **Ho bisogno di una licenza?** Una prova gratuita funziona per lo sviluppo; è necessaria una licenza a pagamento per la produzione.  
- **L'operazione è intensiva in termini di memoria?** No, se chiudi l'istanza `Viewer` tempestivamente; vedi i consigli sulle prestazioni qui sotto.

## Che cos'è “rotate page 90 degrees”?
Rotating a page 90 degrees re‑orients the page from portrait to landscape (or vice‑versa) without changing the underlying content. This is handy for presentations, printing landscape‑only graphics, or correcting scanned documents that were captured sideways. The rotation is applied at render time, leaving the original file unchanged.

## Perché ruotare le pagine programmaticamente con GroupDocs Viewer per Java?
GroupDocs Viewer supports **50+ input and output formats**—including PDF, DOCX, PPTX, XLSX, and many image types—so you can render any document without external converters. The API is fluent, thread‑safe, and runs on any Java 8+ runtime, making it a reliable choice for enterprise‑grade automation that must handle dozens of file types consistently.

## Prerequisiti

- GroupDocs Viewer for Java (ultima versione)
- JDK 8 o più recente
- Maven (o Gradle) per la gestione delle dipendenze
- Un IDE come IntelliJ IDEA o Eclipse
- Familiarità di base con Java I/O

## Configurazione di GroupDocs.Viewer per Java

Add the GroupDocs repository and dependency to your `pom.xml`. This snippet is unchanged from the original tutorial:

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
- **Prova gratuita** – scarica dal sito GroupDocs.  
- **Licenza temporanea** – richiedi se ti serve un periodo di valutazione esteso.  
- **Licenza completa** – acquista per le distribuzioni in produzione.

### Inizializzazione di base del Viewer
The `Viewer` class is the entry point that loads a document and exposes rendering and transformation methods. Keep the code exactly as shown:

```java
import com.groupdocs.viewer.Viewer;

// Initialize Viewer with your document path
try (Viewer viewer = new Viewer("path/to/your/document.docx")) {
    // Perform operations...
}
```

## Come ruotare una pagina PDF in Java con GroupDocs Viewer
Load the target file with `Viewer`, specify the page number, and call `rotatePage`. The method works for PDF, DOCX, PPTX, XLSX and any other format supported by the library. After rotation, you can render the document to a new PDF or stream it directly to the client, ensuring the original file remains untouched.

## Implementazione passo‑passo: ruotare la prima pagina di 90 gradi

### 1. Importa i pacchetti necessari
`PdfViewOptions` tells the Viewer to output a PDF file, while the `Rotation` enum defines the angle. Both classes belong to the `com.groupdocs.viewer.options` package.

```java
import com.groupdocs.viewer.Viewer;
import com.groupdocs.viewer.options.PdfViewOptions;
import com.groupdocs.viewer.options.Rotation;
```

### 2. Definisci le posizioni di output e crea il Viewer
Replace the placeholder paths with your actual directories. The `Viewer` constructor accepts a `File` object that points to the source document.

```java
import java.nio.file.Path;

public class RotateSpecificPage {
    public static void run() {
        Path outputDirectory = YOUR_OUTPUT_DIRECTORY.resolve("RotateSpecificPage");
        Path outputFilePath = outputDirectory.resolve("output.pdf");

        try (Viewer viewer = new Viewer(YOUR_DOCUMENT_DIRECTORY.resolve("Sample.docx"))) {
            // Proceed with the rotation steps below...
        }
    }
}
```

### 3. Configura le opzioni di visualizzazione PDF e applica la rotazione
The `rotatePage(int, Rotation)` method takes a **1‑based** page index and a `Rotation` enum value. In this example we use `Rotation.ON_90_DEGREE` to turn the first page clockwise.

```java
PdfViewOptions viewOptions = new PdfViewOptions(outputFilePath);

// Specify which page to rotate (1 for first page) and the rotation angle
viewOptions.rotatePage(1, Rotation.ON_90_DEGREE);
```

### 4. Renderizza il documento
Calling `view` with the configured options writes the rotated PDF to the output folder.

```java
viewer.view(viewOptions);
```

#### Come funziona
- **PdfViewOptions** indica al Viewer di generare un file PDF di output.  
- **rotatePage(int, Rotation)** ruota solo la pagina specificata, lasciando inalterate tutte le altre pagine.  
- Il metodo supporta tre costanti di rotazione: `ON_90_DEGREE`, `ON_180_DEGREE` e `ON_270_DEGREE`.

## Problemi comuni e soluzioni
| Sintomo | Probabile causa | Soluzione |
|---------|----------------|----------|
| **FileNotFoundException** | Percorso errato o cartella mancante | Verifica che `YOUR_OUTPUT_DIRECTORY` e `YOUR_DOCUMENT_DIRECTORY` esistano e siano leggibili. |
| **Unsupported file format** | Tentativo di ruotare un formato non supportato da Viewer | Controlla la pagina [GroupDocs Viewer supported formats] page. |
| **No rotation visible** | Uso del numero di pagina errato (basato su 0) | Ricorda che `rotatePage` utilizza l'indicizzazione **1‑based**. |
| **Out‑of‑memory errors on large docs** | Rendering di molti file grandi in un singolo thread | Elabora i documenti in sequenza o usa un pool di thread con concorrenza limitata. |

## Applicazioni pratiche

1. **Regolazioni delle presentazioni** – Converti una diapositiva in verticale in orizzontale al volo per un impatto visivo migliore.  
2. **Correzione di massa dei documenti** – Automatizza la correzione di PDF scansionati catturati di lato, risparmiando ore di lavoro manuale.  
3. **Output pronto per la stampa** – Assicura che le grafiche in orizzontale vengano stampate correttamente su carta orientata in verticale senza rotazione manuale nel driver della stampante.

## Consigli sulle prestazioni

- **Chiudi le risorse tempestivamente** – Il blocco `try‑with‑resources` elimina automaticamente il `Viewer`, liberando memoria.  
- **Elaborazione batch** – Riutilizza una singola istanza `Viewer` per thread per ridurre l'overhead di inizializzazione.  
- **Monitora la memoria** – Per documenti più grandi di 100 MB, trasmetti l'output su disco invece di mantenere l'intero file in memoria; GroupDocs Viewer può elaborare file da 200 MB usando meno di 250 MB di RAM.

## Domande frequenti

**Q: Posso ruotare più pagine contemporaneamente?**  
A: Sì—invoca `rotatePage()` per ogni numero di pagina da ruotare, sia in un ciclo sia concatenando le chiamate.

**Q: Esiste un modo per annullare la rotazione dopo il rendering?**  
A: Non direttamente. Dovresti renderizzare nuovamente il documento senza le opzioni di rotazione.

**Q: Quali formati di file supportano la rotazione delle pagine in GroupDocs Viewer?**  
A: DOCX, PDF, PPTX, XLSX e molti altri formati elencati nella documentazione ufficiale.

**Q: Come posso ruotare le pagine in un batch di documenti automaticamente?**  
A: Avvolgi la logica di rotazione in un ciclo che itera su una collezione di percorsi file, applicando la stessa configurazione `rotatePage` a ciascun file.

**Q: Qual è la migliore pratica per gestire gli errori durante la rotazione?**  
A: Inserisci l'uso del Viewer in un blocco `try‑catch`, registra i dettagli dell'eccezione e, facoltativamente, continua l'elaborazione del file successivo per evitare che un singolo errore fermi l'intero batch.

## Risorse

- **Documentazione**: [GroupDocs Viewer Java Documentation](https://docs.groupdocs.com/viewer/java/)  
- **Riferimento API**: [GroupDocs API Reference](https://reference.groupdocs.com/viewer/java/)  
- **Download**: [Get GroupDocs Viewer for Java](https://releases.groupdocs.com/viewer/java/)  
- **Acquista**: [Buy a License](https://purchase.groupdocs.com/buy)  
- **Prova gratuita**: [Try Free](https://releases.groupdocs.com/viewer/java/)  
- **Licenza temporanea**: [Request Temporary License](https://purchase.groupdocs.com/temporary-license/)  
- **Supporto**: [GroupDocs Forum](https://forum.groupdocs.com/c/viewer/9)

---

**Ultimo aggiornamento:** 2026-09-30  
**Testato con:** GroupDocs Viewer 25.2 for Java  
**Autore:** GroupDocs

## Tutorial correlati

- [Come ruotare pagine PDF specifiche con GroupDocs.Viewer per Java](/viewer/java/advanced-rendering/rotate-pdf-pages-groupdocs-viewer-java/)
- [Carica documento da URL in Java – Tutorial GroupDocs.Viewer](/viewer/java/document-loading/)
- [Visualizzazioni di documenti Java di Groupdocs Viewer](/viewer/java/advanced-rendering/groupdocs-viewer-java-document-views/)


{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}