---
date: '2026-05-26'
description: Scopri come convertire nsf in pdf e altri formati (HTML, JPG, PNG) utilizzando
  GroupDocs.Viewer per Java. Guida passo‑passo con consigli best‑practice.
keywords:
- convert nsf to pdf
- how to convert nsf
- java convert lotus notes
schemas:
- author: GroupDocs
  dateModified: '2026-05-26'
  description: Learn how to convert nsf to pdf and other formats (HTML, JPG, PNG)
    using GroupDocs.Viewer for Java. Step‑by‑step guide with best‑practice tips.
  headline: convert nsf to pdf with GroupDocs.Viewer for Java
  type: TechArticle
- description: Learn how to convert nsf to pdf and other formats (HTML, JPG, PNG)
    using GroupDocs.Viewer for Java. Step‑by‑step guide with best‑practice tips.
  name: convert nsf to pdf with GroupDocs.Viewer for Java
  steps:
  - name: '**Web‑Based Document Sharing:** Convert NSF to HTML for instant in‑browser
      viewing without installing Notes.'
    text: '**Web‑Based Document Sharing:** Convert NSF to HTML for instant in‑browser
      viewing without installing Notes.'
  - name: '**Image Archiving:** Store page‑by‑page JPG/PNG snapshots for thumbnail
      galleries or OCR pipelines.'
    text: '**Image Archiving:** Store page‑by‑page JPG/PNG snapshots for thumbnail
      galleries or OCR pipelines.'
  - name: '**Universal Access:** Use PDF conversion to provide a single, secure file
      that can be opened on any device, meeting compliance requirements.'
    text: '**Universal Access:** Use PDF conversion to provide a single, secure file
      that can be opened on any device, meeting compliance requirements.'
  type: HowTo
- questions:
  - answer: '`PdfViewOptions` preserves most annotations automatically; just render
      the document with these options and the resulting PDF mirrors the original layout.'
    question: How do I convert an NSF file to PDF without losing annotations?
  - answer: Yes. Provide credentials through `LoadOptions` before creating the `Viewer`
      instance.
    question: Can I convert password‑protected NSF files?
  - answer: JDK 11 or newer offers improved garbage collection and concurrency, which
      speeds up batch conversions.
    question: What Java version gives the best performance?
  - answer: Configure `JpgViewOptions.setResolution(int dpi)` or `PngViewOptions.setResolution(int
      dpi)` before calling `viewer.view(options)`.
    question: Is it possible to set a custom DPI for JPG/PNG output?
  - answer: Yes. Use the `Stream` overload of the view options to write the result
      straight to `HttpServletResponse.getOutputStream()`.
    question: Does GroupDocs.Viewer support streaming the output directly to an HTTP
      response?
  type: FAQPage
title: converti nsf in pdf con GroupDocs.Viewer per Java
type: docs
url: /it/java/export-conversion/convert-nsf-files-groupdocs-viewer-java/
weight: 1
---

# Convertire file NSF in più formati usando GroupDocs.Viewer per Java

In questa guida completa imparerai **come convertire nsf in pdf** e anche a renderizzare i file NSF in HTML, JPG e PNG con GroupDocs.Viewer per Java. Che tu abbia bisogno di archiviare i database Lotus Notes, visualizzarli in un browser o generare anteprime di immagini, questo tutorial ti accompagna passo passo—dalla configurazione dell'ambiente ai dettagli a livello di codice—così potrai implementare la conversione in pochi minuti.

![Convertire file NSF in HTML, JPG, PNG e PDF con GroupDocs.Viewer per Java](/viewer/export-conversion/convert-nsf-files-to-html-jpg-png-pdf-java.png)
[Convertire file NSF in HTML, JPG, PNG e PDF con GroupDocs.Viewer per Java](/viewer/export-conversion/convert-nsf-files-to-html-jpg-png-pdf-java.png)

## Risposte rapide
- **Qual è l'uso principale?** Renderizzare i file NSF in PDF, HTML, JPG o PNG per il web, l'archiviazione o la condivisione.  
- **Quale libreria gestisce la conversione?** GroupDocs.Viewer per Java.  
- **È necessaria una licenza?** È disponibile una prova gratuita; è richiesta una licenza completa per la produzione.  
- **Quale versione di Java è necessaria?** JDK 8 o successiva.  
- **Posso elaborare più file NSF in batch?** Sì – avvolgi la logica di rendering in un ciclo e gestisci le risorse con try‑with‑resources.

## Cos'è “convert nsf to pdf”?
Convertire un file NSF (database Lotus Notes) in PDF produce un documento statico, universalmente leggibile, che preserva il layout originale, i caratteri e la grafica senza necessità del client Notes. Questo formato è ideale per l'archiviazione legale, la distribuzione sicura e la conservazione a lungo termine perché i file PDF possono essere aperti su qualsiasi sistema operativo o dispositivo.

## Perché convertire NSF in PDF e altri formati?
Trasformare i file NSF in PDF, HTML, JPG o PNG consente un'accessibilità universale, preserva la fedeltà visiva e permette un'integrazione fluida con le moderne applicazioni web e mobile. PDF mantiene l'esatto layout della pagina, HTML offre visualizzazione immediata nel browser, e JPG/PNG forniscono snapshot di immagini ad alta risoluzione per miniature o incorporamento.

## Prerequisiti
- **Java Development Kit (JDK) 8+** – JDK 11 o più recente è consigliato per migliori prestazioni di garbage‑collection.  
- **Maven** – per la gestione delle dipendenze.  
- **GroupDocs.Viewer per Java** – versione di prova o con licenza.  
- Familiarità di base con I/O di file Java e la struttura di progetto Maven.

## Configurazione di GroupDocs.Viewer per Java

### Configurazione Maven
Aggiungi la dipendenza GroupDocs.Viewer al tuo `pom.xml`. Questo scarica tutti i binari necessari e le librerie transitive.

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
Per sbloccare tutte le funzionalità puoi:
- **Prova gratuita:** Valuta le funzionalità principali senza una chiave di licenza.  
- **Licenza temporanea:** Richiedi una chiave a tempo limitato per i test.  
- **Acquisto completo:** Ottieni una licenza di produzione per uso illimitato.

### Inizializzazione di base
`Viewer` è la classe principale che rende i documenti nel formato di output desiderato. Inizializzala con la tua licenza e il percorso del file all'interno di un blocco try‑with‑resources per garantire una corretta pulizia.

```java
import com.groupdocs.viewer.Viewer;

public class InitializeViewer {
    public static void main(String[] args) {
        try (Viewer viewer = new Viewer("YOUR_DOCUMENT_DIRECTORY/SAMPLE_NSF")) {
            // Viewer is ready for use.
        }
    }
}
```

## Come convertire NSF in PDF
Per convertire un documento NSF in PDF, crea prima un'istanza `Viewer` che punta al file di origine. Quindi configura `PdfViewOptions` per definire le caratteristiche di output come la dimensione della pagina, il livello di compressione e se incorporare i font. Infine, chiama `viewer.view(pdfOptions)` che rende l'intero documento in un unico file PDF pronto per la distribuzione.

`PdfViewOptions` specifica le impostazioni specifiche per PDF come la dimensione della pagina e la compressione.

```java
Path pageFilePathFormat = outputDirectory.resolve("NSF_result.pdf");
```
```java
import com.groupdocs.viewer.options.PdfViewOptions;

try (Viewer viewer = new Viewer("YOUR_DOCUMENT_DIRECTORY/SAMPLE_NSF", loadOptions)) {
    PdfViewOptions options = new PdfViewOptions(pageFilePathFormat);
    viewer.view(options);  // Convert to PDF.
}
```

## Rendering di NSF in HTML

### Panoramica
Converti i documenti NSF in pagine HTML autonome, incorporando immagini e CSS per una rappresentazione accurata sullo schermo.

### Guida passo‑passo

#### 1. Configura la directory di output e il percorso del file
Definisci la cartella in cui verranno salvati i file HTML.

```java
import java.nio.file.Path;
import java.nio.file.Paths;

Path outputDirectory = Paths.get("YOUR_OUTPUT_DIRECTORY");
Path pageFilePathFormat = outputDirectory.resolve("NSF_result.html");
```

#### 2. Configura le opzioni di caricamento
`LoadOptions` ti permette di regolare finemente il caricamento delle risorse, ad esempio impostando un timeout per le risorse esterne.

```java
import com.groupdocs.viewer.options.LoadOptions;

LoadOptions loadOptions = new LoadOptions();
loadOptions.setResourceLoadingTimeout(100);  // Set timeout for loading resources.
```

#### 3. Inizializza Viewer e renderizza
`Viewer` elabora il NSF e scrive i file HTML nella directory di destinazione.

```java
import com.groupdocs.viewer.Viewer;
import com.groupdocs.viewer.options.HtmlViewOptions;

try (Viewer viewer = new Viewer("YOUR_DOCUMENT_DIRECTORY/SAMPLE_NSF", loadOptions)) {
    HtmlViewOptions options = HtmlViewOptions.forEmbeddedResources(pageFilePathFormat);
    viewer.view(options);  // Render the document to HTML.
}
```

## Rendering di NSF in JPG

### Panoramica
Genera immagini JPG ad alta qualità da ogni pagina di un documento NSF, utile per anteprime o per l'incorporamento in flussi di lavoro basati su immagini.

#### 1. Definisci il percorso di output
Specifica un modello di denominazione come `output_page_{0}.jpg` dove `{0}` è il numero della pagina.

```java
Path pageFilePathFormat = outputDirectory.resolve("NSF_result_{0}.jpg");
```

#### 2. Configura e renderizza
`JpgViewOptions` definisce le impostazioni per l'output di immagini JPEG, inclusi risoluzione e qualità. Crea `JpgViewOptions`, imposta i DPI desiderati e invoca `viewer.view(options)`.

```java
import com.groupdocs.viewer.options.JpgViewOptions;

try (Viewer viewer = new Viewer("YOUR_DOCUMENT_DIRECTORY/SAMPLE_NSF", loadOptions)) {
    JpgViewOptions options = new JpgViewOptions(pageFilePathFormat);
    viewer.view(options);  // Render to JPG.
}
```

## Rendering di NSF in PNG

### Panoramica
Produce immagini PNG senza perdita che conservano ogni dettaglio delle pagine NSF originali.

#### 1. Imposta il percorso di output
Usa un modello come `nsf_page_{0}.png` per la paginazione automatica.

```java
Path pageFilePathFormat = outputDirectory.resolve("NSF_result_{0}.png");
```

#### 2. Renderizza il documento
`PngViewOptions` configura i parametri di output PNG come risoluzione e profondità di colore. Configura `PngViewOptions` (ad esempio, imposta `setResolution(300)`) e renderizza.

```java
import com.groupdocs.viewer.options.PngViewOptions;

try (Viewer viewer = new Viewer("YOUR_DOCUMENT_DIRECTORY/SAMPLE_NSF", loadOptions)) {
    PngViewOptions options = new PngViewOptions(pageFilePathFormat);
    viewer.view(options);  // Convert to PNG.
}
```

## Applicazioni pratiche
1. **Condivisione di documenti basata sul web:** Converti NSF in HTML per visualizzazione immediata nel browser senza installare Notes.  
2. **Archiviazione di immagini:** Conserva snapshot JPG/PNG pagina per pagina per gallerie di miniature o pipeline OCR.  
3. **Accesso universale:** Usa la conversione in PDF per fornire un unico file sicuro che può essere aperto su qualsiasi dispositivo, soddisfacendo i requisiti di conformità.

## Considerazioni sulle prestazioni
- **Caricamento delle risorse:** Regola `setResourceLoadingTimeout` in base alla latenza di rete per evitare blocchi.  
- **Gestione della memoria:** Usa try‑with‑resources per le istanze `Viewer`; questo libera automaticamente le risorse native.  
- **Elaborazione batch:** Per grandi batch, elabora i file in modo sequenziale o con stream paralleli, monitorando l'uso dell'heap per rimanere al di sotto dei limiti di memoria della JVM.

## Sezione FAQ
**Qual è il formato migliore per convertire i documenti NSF?**  
- Dipende dall'uso successivo: HTML per portali web, PDF per distribuzione universale, JPG/PNG per flussi di lavoro basati su immagini.

**Come gestire efficientemente file NSF di grandi dimensioni?**  
- Ottimizza `LoadOptions` (ad esempio, aumenta `setResourceLoadingTimeout`), elabora i file in batch più piccoli e riutilizza una singola istanza `Viewer` quando possibile.

**Posso personalizzare la qualità dell'output nei formati immagine?**  
- Sì. Imposta DPI, livello di compressione e profondità di colore tramite `JpgViewOptions` o `PngViewOptions` prima del rendering.

**Cosa fare se la conversione fallisce?**  
- Verifica i percorsi dei file, assicurati che il file NSF non sia corrotto e consulta i log di GroupDocs.Viewer per codici di errore dettagliati. Aggiornare alla versione più recente della libreria spesso risolve problemi di compatibilità.

**La conversione batch è supportata?**  
- Assolutamente. Avvolgi la logica di rendering all'interno di un ciclo `for` o di uno Stream Java per elaborare automaticamente più file NSF.

## Domande frequenti
**D: Come converto un file NSF in PDF senza perdere le annotazioni?**  
R: `PdfViewOptions` preserva automaticamente la maggior parte delle annotazioni; basta renderizzare il documento con queste opzioni e il PDF risultante rispecchia il layout originale.

**D: Posso convertire file NSF protetti da password?**  
R: Sì. Fornisci le credenziali tramite `LoadOptions` prima di creare l'istanza `Viewer`.

**D: Quale versione di Java offre le migliori prestazioni?**  
R: JDK 11 o versioni successive offrono una migliore garbage collection e concorrenza, accelerando le conversioni batch.

**D: È possibile impostare un DPI personalizzato per l'output JPG/PNG?**  
R: Configura `JpgViewOptions.setResolution(int dpi)` o `PngViewOptions.setResolution(int dpi)` prima di chiamare `viewer.view(options)`.

**D: GroupDocs.Viewer supporta lo streaming dell'output direttamente a una risposta HTTP?**  
R: Sì. Usa la sovraccarico `Stream` delle opzioni di visualizzazione per scrivere il risultato direttamente su `HttpServletResponse.getOutputStream()`.

## Conclusione
Ora hai una roadmap completa per **convertire nsf in pdf** e renderizzare i file NSF in HTML, JPG e PNG usando GroupDocs.Viewer per Java. Seguendo i passaggi sopra potrai integrare una conversione documenti robusta in qualsiasi applicazione Java, automatizzare i lavori batch e fornire contenuti nel formato più adatto alle esigenze dei tuoi utenti. Esplora funzionalità aggiuntive di Viewer come watermark, font personalizzati e gestione multi‑pagina per arricchire ulteriormente la tua soluzione.

---

**Last Updated:** 2026-05-26  
**Tested With:** GroupDocs.Viewer 25.2  
**Author:** GroupDocs

## Tutorial correlati
- [groupdocs viewer java: Converti documenti in PDF – Guida completa](/viewer/java/export-conversion/convert-documents-pdf-groupdocs-viewer-java/)
- [convert odf html java – Converti ODF in HTML, JPG, PNG, PDF usando GroupDocs.Viewer per Java](/viewer/java/export-conversion/convert-odf-documents-groupdocs-viewer-java/)
- [Converti PST in HTML, JPG, PNG, PDF usando GroupDocs.Viewer per Java](/viewer/java/export-conversion/convert-pst-ost-groupdocs-viewer-java/)