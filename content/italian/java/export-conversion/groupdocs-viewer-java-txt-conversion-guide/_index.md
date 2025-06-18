---
"date": "2025-04-24"
"description": "Scopri come convertire in modo efficiente i file TXT in diversi formati come HTML, JPG, PNG e PDF utilizzando GroupDocs.Viewer per Java. Segui questa guida passo passo."
"title": "Convertire file TXT in HTML, JPG, PNG e PDF utilizzando GroupDocs.Viewer per Java"
"url": "/it/java/export-conversion/groupdocs-viewer-java-txt-conversion-guide/"
"weight": 1
---

# Convertire file TXT con GroupDocs.Viewer per Java: una guida completa

## Introduzione

Nel mondo digitale odierno, una gestione efficiente dei documenti è fondamentale sia per le aziende che per i privati. Che si tratti di visualizzare documenti di testo sul web o di archiviare file in vari formati, la conversione di file di testo (TXT) è un'esigenza frequente. **GroupDocs.Viewer per Java** Offre una soluzione efficace per convertire facilmente file TXT in diversi formati come HTML, JPG, PNG e PDF. Questa guida ti guiderà nell'utilizzo di questa versatile libreria per ottenere conversioni impeccabili.

### Cosa imparerai:
- Impostazione di GroupDocs.Viewer nel tuo ambiente Java
- Conversione di file TXT in HTML multipagina e monopagina
- Rendering di documenti TXT in formati immagine (JPG, PNG)
- Trasformazione del contenuto TXT in formato PDF

Analizziamo i prerequisiti richiesti prima di iniziare l'implementazione.

## Prerequisiti

Prima di immergerti in GroupDocs.Viewer per Java, assicurati di avere:

### Librerie e dipendenze richieste:
- **GroupDocs.Viewer per Java** versione 25.2 o successiva.
  
### Requisiti di configurazione dell'ambiente:
- Un Java Development Kit (JDK) compatibile installato sul sistema (si consiglia Java 8+).
- Un ambiente di sviluppo integrato (IDE) come IntelliJ IDEA, Eclipse o NetBeans.

### Prerequisiti di conoscenza:
- Conoscenza di base della programmazione Java e della gestione dei file.
- È utile avere familiarità con Maven per la gestione delle dipendenze.

## Impostazione di GroupDocs.Viewer per Java

Per iniziare a utilizzare **GroupDocs.Viewer**, includilo nel tuo progetto tramite Maven come segue:

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

### Fasi di acquisizione della licenza:
- Inizia con un **prova gratuita** o ottenere un **licenza temporanea** per esplorare tutte le funzionalità di GroupDocs.Viewer.
- Considerare l'acquisto di una licenza tramite il loro sito ufficiale [pagina di acquisto](https://purchase.groupdocs.com/buy) per un utilizzo a lungo termine.

### Inizializzazione e configurazione di base:
1. Aggiungi la dipendenza Maven al tuo progetto.
2. Assicurati di aver configurato il tuo ambiente con JDK e un IDE.

Ora vediamo come implementare le diverse funzionalità di GroupDocs.Viewer per convertire i file TXT in vari formati.

## Guida all'implementazione

### Funzionalità 1: Trasforma il testo in HTML multipagina

#### Panoramica:
Questa funzionalità converte un documento TXT in un formato HTML multipagina, preservando la struttura del testo su più pagine web.

##### Passaggi:

**Importa le librerie richieste**
```java
import com.groupdocs.viewer.Viewer;
import com.groupdocs.viewer.options.HtmlViewOptions;
```

**Imposta percorsi e visualizzatore**
```java
Path outputDirectory = Path.of("YOUR_OUTPUT_DIRECTORY");
Path pageFileFullPath = outputDirectory.resolve("Txt_result.html");

try (Viewer viewer = new Viewer("YOUR_DOCUMENT_DIRECTORY/SAMPLE_TXT")) {
    // Configura le opzioni per il rendering con risorse incorporate
    HtmlViewOptions options = HtmlViewOptions.forEmbeddedResources(pageFileFullPath);
    
    // Rendi il documento in HTML utilizzando queste opzioni
    viewer.view(options);
}
```

**Spiegazione:**
- `HtmlViewOptions.forEmbeddedResources` viene utilizzato qui per garantire che tutte le risorse siano incorporate nei file di output, rendendoli autosufficienti.

### Funzionalità 2: Trasforma il testo in HTML a pagina singola

#### Panoramica:
Questa funzione condensa l'intero documento di testo in un'unica pagina HTML, ideale per anteprime o riepiloghi rapidi.

##### Passaggi:

**Importa le librerie richieste**
```java
import com.groupdocs.viewer.Viewer;
import com.groupdocs.viewer.options.HtmlViewOptions;
```

**Imposta percorsi e visualizzatore**
```java
Path outputDirectory = Path.of("YOUR_OUTPUT_DIRECTORY");
Path pageFileFullPath = outputDirectory.resolve("Txt_result_single_page.html");

try (Viewer viewer = new Viewer("YOUR_DOCUMENT_DIRECTORY/SAMPLE_2_TXT")) {
    // Configura le opzioni per il rendering con risorse incorporate
    HtmlViewOptions options = HtmlViewOptions.forEmbeddedResources(pageFileFullPath);
    
    // Imposta l'opzione per il rendering come pagina HTML singola
    options.setRenderToSinglePage(true);
    
    // Esegui il rendering del documento utilizzando queste opzioni
    viewer.view(options);
}
```

**Spiegazione:**
IL `setRenderToSinglePage(true)` metodo compatta tutto il testo in un'unica pagina web.

### Funzionalità 3: Trasforma TXT in JPG

#### Panoramica:
Converti i tuoi file TXT in immagini JPEG di alta qualità, adatte alla condivisione o alla stampa.

##### Passaggi:

**Importa le librerie richieste**
```java
import com.groupdocs.viewer.Viewer;
import com.groupdocs.viewer.options.JpgViewOptions;
```

**Imposta percorsi e visualizzatore**
```java
Path outputDirectory = Path.of("YOUR_OUTPUT_DIRECTORY");
Path pageFileFullPath = outputDirectory.resolve("Txt_result.jpg");

try (Viewer viewer = new Viewer("YOUR_DOCUMENT_DIRECTORY/SAMPLE_TXT")) {
    // Configura le opzioni per il rendering in un'immagine JPEG
    JpgViewOptions options = new JpgViewOptions(pageFileFullPath);
    
    // Rendi il documento come JPG utilizzando queste opzioni
    viewer.view(options);
}
```

**Spiegazione:**
- `JpgViewOptions` consente di specificare percorsi di output e impostazioni di rendering personalizzati per la conversione delle immagini.

### Funzionalità 4: Trasforma TXT in PNG

#### Panoramica:
Converti i documenti di testo nel formato Portable Network Graphics (PNG), offrendo immagini di alta qualità con compressione senza perdite.

##### Passaggi:

**Importa le librerie richieste**
```java
import com.groupdocs.viewer.Viewer;
import com.groupdocs.viewer.options.PngViewOptions;
```

**Imposta percorsi e visualizzatore**
```java
Path outputDirectory = Path.of("YOUR_OUTPUT_DIRECTORY");
Path pageFileFullPath = outputDirectory.resolve("Txt_result.png");

try (Viewer viewer = new Viewer("YOUR_DOCUMENT_DIRECTORY/SAMPLE_TXT")) {
    // Configura le opzioni per il rendering in un'immagine PNG
    PngViewOptions options = new PngViewOptions(pageFileFullPath);
    
    // Rendi il documento come PNG utilizzando queste opzioni
    viewer.view(options);
}
```

**Spiegazione:**
- `PngViewOptions` è usato qui, simile a `JpgViewOptions`, ma con vantaggi specifici del formato PNG.

### Funzionalità 5: Trasforma TXT in PDF

#### Panoramica:
Genera file PDF da documenti di testo, ideali per la distribuzione o l'archiviazione in un formato universalmente accettato.

##### Passaggi:

**Importa le librerie richieste**
```java
import com.groupdocs.viewer.Viewer;
import com.groupdocs.viewer.options.PdfViewOptions;
```

**Imposta percorsi e visualizzatore**
```java
Path outputDirectory = Path.of("YOUR_OUTPUT_DIRECTORY");
Path pageFileFullPath = outputDirectory.resolve("Txt_result.pdf");

try (Viewer viewer = new Viewer("YOUR_DOCUMENT_DIRECTORY/SAMPLE_TXT")) {
    // Configurare le opzioni per il rendering in un PDF
    PdfViewOptions options = new PdfViewOptions(pageFileFullPath);
    
    // Rendi il documento come PDF utilizzando queste opzioni
    viewer.view(options);
}
```

**Spiegazione:**
- `PdfViewOptions` fornisce impostazioni specifiche per la conversione PDF, tra cui impostazione della pagina e incorporamento delle risorse.

## Applicazioni pratiche

Le funzionalità di GroupDocs.Viewer per Java si estendono a diversi casi di utilizzo pratico:

1. **Sistemi di gestione dei documenti:** Automatizza la conversione della documentazione testuale in formati web-friendly per i portali interni.
2. **Piattaforme di pubblicazione:** Converti i contenuti inviati dagli autori da TXT a HTML per una perfetta integrazione nei sistemi di gestione dei contenuti.
3. **Soluzioni di archiviazione:** Conserva i file di testo legacy in formati PDF o immagine moderni e facilmente accessibili.
4. **Integrazione con Cloud Storage:** Converti e archivia automaticamente i documenti su piattaforme cloud per una migliore accessibilità.