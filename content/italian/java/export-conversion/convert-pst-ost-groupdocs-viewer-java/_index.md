---
date: '2026-07-19'
description: Scopri come convertire PST in HTML e altri formati come JPG, PNG, PDF
  usando GroupDocs.Viewer for Java. Questa guida copre tutti i passaggi e le configurazioni
  necessarie.
keywords:
- convert pst to html
- convert pst to pdf
- java convert ost
- convert pst to png
- convert pst to jpg
lastmod: '2026-07-19'
og_description: Converti PST in HTML rapidamente usando GroupDocs.Viewer for Java.
  Scopri passo passo come esportare anche in JPG, PNG e PDF in una guida pronta per
  la produzione.
og_image_alt: 'Developer guide: Convert PST to HTML, JPG, PNG, PDF using GroupDocs
  Viewer for Java'
og_title: Converti PST in HTML con GroupDocs.Viewer for Java – Esportazione Rapida
  di Email
schemas:
- author: GroupDocs
  dateModified: '2026-07-19'
  description: Learn how to convert pst to html and other formats like JPG, PNG, PDF
    using GroupDocs.Viewer for Java. This guide covers all steps and configurations
    needed.
  headline: Convert PST to HTML, JPG, PNG, PDF Using GroupDocs.Viewer for Java
  type: TechArticle
- description: Learn how to convert pst to html and other formats like JPG, PNG, PDF
    using GroupDocs.Viewer for Java. This guide covers all steps and configurations
    needed.
  name: Convert PST to HTML, JPG, PNG, PDF Using GroupDocs.Viewer for Java
  steps:
  - name: Set Up Output Directory
    text: Define a folder where the HTML pages will be written. GroupDocs creates
      a sub‑folder for each email to keep assets organized.
  - name: Configure Load Options
    text: '`LoadOptions` lets you specify password handling, resource‑loading timeouts,
      and selective page rendering. Setting a timeout of 30 seconds works well for
      most server environments.'
  - name: Define HTML View Options
    text: '`HtmlViewOptions` specifies the output folder, resource handling, and optional
      CSS settings for HTML conversion.'
  - name: Initialize Viewer and Render HTML
    text: Create a `Viewer` object, pass the PST file path, and call `view` with the
      `HtmlViewOptions`. The API automatically iterates through all messages inside
      the PST and generates a tidy HTML hierarchy.
  - name: Set Up Output Directory
    text: Create a dedicated folder for JPG snapshots; each email will become one
      or more image files depending on its length.
  - name: Configure Load Options
    text: The same `LoadOptions` used for HTML can be reused here, ensuring consistent
      password handling across formats.
  - name: Define JPG View Options
    text: '`JpgViewOptions` controls image resolution, quality, and output folder
      for JPEG conversion.'
  - name: Initialize Viewer and Render JPG
    text: Use `viewer.view(jpgOptions)` to generate high‑quality JPEG files ready
      for web preview.
  - name: Set Up Output Directory
    text: PNG output is useful when you need lossless quality for archiving or OCR
      processing.
  - name: Configure Load Options
    text: No additional settings are required beyond the password and timeout configuration.
  type: HowTo
- questions:
  - answer: Use `PdfViewOptions` as shown in the PDF rendering section; the rest of
      the code remains identical.
    question: How do I **convert pst to pdf** with the same code base?
  - answer: Yes, provide the password via `LoadOptions.setPassword("yourPassword")`
      before rendering.
    question: Can GroupDocs.Viewer handle encrypted PST files?
  - answer: PNG preserves lossless quality, ideal for screenshots, while JPG offers
      smaller file sizes for email previews.
    question: What is the difference between **java convert pst** to PNG vs JPG?
  - answer: Wrap the rendering logic in a loop that iterates over a directory of PST
      files; reuse the same `Viewer` configuration for each file.
    question: Is there a way to **how to convert pst** files in bulk?
  - answer: Yes, GroupDocs.Viewer streams data and can process files up to 2 GB without
      loading the entire archive into memory.
    question: Does the API support converting PST files larger than 1 GB?
  type: FAQPage
tags:
- convert pst
- GroupDocs.Viewer
- Java document processing
- email conversion
title: Converti PST in HTML, JPG, PNG, PDF usando GroupDocs.Viewer for Java
type: docs
url: /it/java/export-conversion/convert-pst-ost-groupdocs-viewer-java/
weight: 1
---

# Converti PST in HTML, JPG, PNG, PDF con GroupDocs.Viewer per Java

Stai cercando di **convertire pst in html** o altri formati come JPG, PNG o PDF? Con la potente libreria GroupDocs.Viewer per Java, questo compito è semplice ed efficiente. In questo tutorial imparerai a renderizzare i file Outlook PST/OST in HTML adatto al web, file immagine o un unico PDF, rendendo i tuoi archivi email facili da condividere e archiviare.

![Converti PST/OST in HTML, JPG, PNG, PDF con GroupDocs.Viewer per Java](/viewer/export-conversion/convert-pst-ost-to-html-jpg-png-pdf.png)

[Converti PST/OST in HTML, JPG, PNG, PDF con GroupDocs.Viewer per Java](/viewer/export-conversion/convert-pst-ost-to-html-jpg-png-pdf.png)

**Cosa Imparerai**
- Come configurare GroupDocs.Viewer per Java in un progetto Maven.  
- Istruzioni passo‑a‑passo per **java convertire pst** file in HTML, JPG, PNG e PDF.  
- Suggerimenti di configurazione per prestazioni ottimali e problemi comuni.

## Risposte Rapide
- **Quale libreria gestisce la conversione PST?** GroupDocs.Viewer per Java.  
- **Posso convertire PST in PDF direttamente?** Sì, usando `PdfViewOptions`.  
- **È necessaria una licenza per la produzione?** È necessaria una licenza GroupDocs valida.  
- **Quale versione di Java è supportata?** JDK 8 o superiore.  
- **Devo estrarre gli allegati manualmente?** No, il viewer li renderizza automaticamente.

## Cos'è GroupDocs.Viewer per Java?
GroupDocs.Viewer per Java è un'API lato server che carica oltre 100 formati di documenti ed email e li renderizza in output HTML, immagine o PDF senza software esterno. Elabora file PST fino a 2 GB mantenendo l'uso della memoria inferiore a 200 MB.

## Come convertire pst in html con GroupDocs.Viewer per Java?
Carica il file PST con `new Viewer("source.pst")`, configura `HtmlViewOptions` per puntare a una cartella di output e chiama `viewer.view(htmlOptions)`. L'API estrae ogni email, preserva la formattazione, gli allegati e i metadati, e scrive una pagina HTML separata per ciascun messaggio—tutto in una singola chiamata di metodo.

### Perché scegliere GroupDocs.Viewer?
- **Rendering ad alta fedeltà** – Il 99,9 % del contenuto delle email (incluse corpi in rich‑text, tabelle e immagini incorporate) è riprodotto accuratamente.  
- **Formati di output multipli** – Una chiamata API può generare HTML, JPG, PNG o PDF, coprendo oltre 50 opzioni di esportazione.  
- **Zero dipendenze esterne** – Nessun bisogno di Outlook, Exchange Server o convertitori di terze parti; tutto funziona all'interno del runtime Java.

## Prerequisiti
- **GroupDocs.Viewer per Java** – versione 25.2 o successiva.  
- **Java Development Kit (JDK)** – 8 o più recente.  
- Maven per la gestione delle dipendenze.  
- Conoscenze di base di Java e familiarità con Maven.

## Configurazione di GroupDocs.Viewer per Java
`Viewer` è la classe principale in GroupDocs.Viewer per Java che carica un documento e lo renderizza nel formato scelto. Aggiungi il repository GroupDocs e la dipendenza al tuo `pom.xml`:

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

### Acquisizione della Licenza
- **Prova gratuita** – esplora tutte le funzionalità senza costi.  
- **Licenza temporanea** – estendi il periodo di valutazione se necessario.  
- **Licenza completa** – necessaria per le distribuzioni in produzione.

### Inizializzazione di Base
Le istanze di `Viewer` sono leggere; puoi riutilizzare una singola istanza per molti file per ridurre al minimo l'overhead di creazione degli oggetti.

```java
import com.groupdocs.viewer.Viewer;
import com.groupdocs.viewer.options.HtmlViewOptions;

public class PSTToHTML {
    public static void main(String[] args) {
        // Initialize Viewer with a sample PST file path
        try (Viewer viewer = new Viewer("YOUR_DOCUMENT_DIRECTORY/SAMPLE_PST")) {
            HtmlViewOptions options = HtmlViewOptions.forEmbeddedResources("output_directory/PST_result.html");
            viewer.view(options);
        }
    }
}
```

## Guida all'Implementazione
Le sezioni seguenti ti guidano nella renderizzazione dei file PST/OST in ciascun formato supportato.

### Renderizzazione di Documenti PST/OST in HTML
#### Passo 1: Configura la Cartella di Output
Definisci una cartella dove verranno scritte le pagine HTML. GroupDocs crea una sottocartella per ogni email per mantenere gli asset organizzati.

```java
Path outputDirectory = Paths.get("YOUR_OUTPUT_DIRECTORY");
Path pageFilePathFormat = outputDirectory.resolve("PST_result.html");
```

#### Passo 2: Configura le Opzioni di Caricamento
`LoadOptions` ti consente di specificare la gestione delle password, i timeout di caricamento delle risorse e la renderizzazione selettiva delle pagine. Impostare un timeout di 30 secondi funziona bene per la maggior parte degli ambienti server.

```java
LoadOptions loadOptions = new LoadOptions();
loadOptions.setResourceLoadingTimeout(100);
```

#### Passo 3: Definisci le Opzioni di Visualizzazione HTML
`HtmlViewOptions` specifica la cartella di output, la gestione delle risorse e le impostazioni CSS opzionali per la conversione HTML.

```java
try (Viewer viewer = new Viewer("YOUR_DOCUMENT_DIRECTORY/SAMPLE_PST", loadOptions)) {
    HtmlViewOptions options = HtmlViewOptions.forEmbeddedResources(pageFilePathFormat);
    viewer.view(options);
}
```

#### Passo 4: Inizializza Viewer e Renderizza HTML
Crea un oggetto `Viewer`, passa il percorso del file PST e chiama `view` con le `HtmlViewOptions`. L'API itera automaticamente tutti i messaggi all'interno del PST e genera una gerarchia HTML ordinata.

```java
Path outputDirectory = Paths.get("YOUR_OUTPUT_DIRECTORY");
Path pageFilePathFormat = outputDirectory.resolve("PST_result_{0}.jpg");
```

### Renderizzazione di Documenti PST/OST in JPG
#### Passo 1: Configura la Cartella di Output
Crea una cartella dedicata per gli snapshot JPG; ogni email diventerà uno o più file immagine a seconda della sua lunghezza.

```java
LoadOptions loadOptions = new LoadOptions();
loadOptions.setResourceLoadingTimeout(100);
```

#### Passo 2: Configura le Opzioni di Caricamento
Le stesse `LoadOptions` usate per HTML possono essere riutilizzate qui, garantendo una gestione coerente delle password tra i formati.

```java
try (Viewer viewer = new Viewer("YOUR_DOCUMENT_DIRECTORY/SAMPLE_PST", loadOptions)) {
    JpgViewOptions options = new JpgViewOptions(pageFilePathFormat);
    viewer.view(options);
}
```

#### Passo 3: Definisci le Opzioni di Visualizzazione JPG
`JpgViewOptions` controlla la risoluzione dell'immagine, la qualità e la cartella di output per la conversione JPEG.

```java
Path outputDirectory = Paths.get("YOUR_OUTPUT_DIRECTORY");
Path pageFilePathFormat = outputDirectory.resolve("PST_result_{0}.png");
```

#### Passo 4: Inizializza Viewer e Renderizza JPG
Usa `viewer.view(jpgOptions)` per generare file JPEG ad alta qualità pronti per l'anteprima web.

```java
LoadOptions loadOptions = new LoadOptions();
loadOptions.setResourceLoadingTimeout(100);
```

### Renderizzazione di Documenti PST/OST in PNG
#### Passo 1: Configura la Cartella di Output
L'output PNG è utile quando hai bisogno di qualità lossless per l'archiviazione o l'elaborazione OCR.

```java
try (Viewer viewer = new Viewer("YOUR_DOCUMENT_DIRECTORY/SAMPLE_PST", loadOptions)) {
    PngViewOptions options = new PngViewOptions(pageFilePathFormat);
    viewer.view(options);
}
```

#### Passo 2: Configura le Opzioni di Caricamento
Non sono necessarie impostazioni aggiuntive oltre alla configurazione di password e timeout.

```java
Path outputDirectory = Paths.get("YOUR_OUTPUT_DIRECTORY");
Path pageFilePathFormat = outputDirectory.resolve("PST_result.pdf");
```

#### Passo 3: Definisci le Opzioni di Visualizzazione PNG
`PngViewOptions` ti permette di impostare uno sfondo trasparente e la cartella di output per immagini PNG lossless.

```java
LoadOptions loadOptions = new LoadOptions();
loadOptions.setResourceLoadingTimeout(100);
```

#### Passo 4: Inizializza Viewer e Renderizza PNG
Istanzia `viewer.view(pngOptions)` per produrre snapshot PNG di ogni email.

```java
try (Viewer viewer = new Viewer("YOUR_DOCUMENT_DIRECTORY/SAMPLE_PST", loadOptions)) {
    PdfViewOptions options = new PdfViewOptions(pageFilePathFormat);
    viewer.view(options);
}
```

### Renderizzazione di Documenti PST/OST in PDF
#### Passo 1: Configura la Cartella di Output
Un unico file PDF per PST semplifica i flussi di lavoro di revisione legale e riduce l'overhead di archiviazione.

CODE_BLOCK_PLACEHOLDER_14_END

#### Passo 2: Configura le Opzioni di Caricamento
Durante la conversione in PDF, potresti voler abilitare `setEmbedFonts(true)` per garantire la fedeltà visiva su qualsiasi macchina.

CODE_BLOCK_PLACEHOLDER_15_END

#### Passo 3: Definisci le Opzioni di Visualizzazione PDF
`PdfViewOptions` ti consente di scegliere il livello di compressione, incorporare i font e impostare il nome del file di output per la conversione PDF.

CODE_BLOCK_PLACEHOLDER_16_END

#### Passo 4: Inizializza Viewer e Renderizza PDF
Crea `PdfViewOptions`, opzionalmente scegli un livello di compressione, e chiama `viewer.view(pdfOptions)`. L'API unisce tutte le email in un unico documento PDF ricercabile.

CODE_BLOCK_PLACEHOLDER_17_END

## Applicazioni Pratiche
- **Archiviazione Email:** Trasforma grandi archivi PST in HTML o PDF ricercabili per la conformità.  
- **Sistemi di Gestione Documentale:** Archivia i file convertiti in sistemi che accettano solo PDF, PNG o JPG.  
- **Piattaforme di Collaborazione:** Condividi le email convertite come immagini in Slack o Teams.  
- **Revisione Legale:** Fornisci ai tribunali versioni PDF delle prove email.  
- **Strategie di Backup:** Conserva snapshot PNG o JPG leggeri dei messaggi critici.

## Considerazioni sulle Prestazioni
- **Gestione delle Risorse:** Riutilizza le istanze `Viewer` quando elabori più file per ridurre l'overhead.  
- **Ottimizzazione della Memoria:** Regola `loadOptions.setResourceLoadingTimeout` in base alla capacità del server.  
- **Elaborazione Asincrona:** Sposta la conversione su thread in background per UI reattive.  

## Domande Frequenti
**Q: Come **convertire pst in pdf** con la stessa base di codice?**  
A: Usa `PdfViewOptions` come mostrato nella sezione di rendering PDF; il resto del codice rimane identico.

**Q: GroupDocs.Viewer può gestire file PST crittografati?**  
A: Sì, fornisci la password tramite `LoadOptions.setPassword("yourPassword")` prima del rendering.

**Q: Qual è la differenza tra **java convertire pst** in PNG vs JPG?**  
A: PNG conserva la qualità lossless, ideale per screenshot, mentre JPG offre dimensioni di file più piccole per le anteprime delle email.

**Q: Esiste un modo per **come convertire pst** file in blocco?**  
A: Avvolgi la logica di rendering in un ciclo che itera su una directory di file PST; riutilizza la stessa configurazione `Viewer` per ogni file.

**Q: L'API supporta la conversione di file PST più grandi di 1 GB?**  
A: Sì, GroupDocs.Viewer trasmette i dati in streaming e può elaborare file fino a 2 GB senza caricare l'intero archivio in memoria.

## Conclusione
Ora disponi di una guida completa, pronta per la produzione, per **convertire pst in html**, JPG, PNG e PDF usando GroupDocs.Viewer per Java. Seguendo i passaggi sopra potrai integrare la conversione delle email in qualsiasi flusso di lavoro basato su Java, migliorare l'accessibilità e soddisfare i requisiti di conformità.

---

**Ultimo Aggiornamento:** 2026-07-19  
**Testato Con:** GroupDocs.Viewer per Java 25.2  
**Autore:** GroupDocs

## Tutorial Correlati
- [Converti NSF in PDF, HTML, JPG, PNG usando GroupDocs.Viewer per Java](/viewer/java/export-conversion/convert-nsf-files-groupdocs-viewer-java/)
- [convert odf html java – Converti ODF in HTML, JPG, PNG, PDF usando GroupDocs.Viewer per Java](/viewer/java/export-conversion/convert-odf-documents-groupdocs-viewer-java/)
- [Come Convertire DOCX in HTML Usando GroupDocs.Viewer per Java: Guida Passo‑Passo](/viewer/java/export-conversion/convert-docx-to-html-groupdocs-viewer-java/)