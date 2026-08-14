---
date: '2026-06-20'
description: Tutorial di GroupDocs Viewer Java che mostra come renderizzare file APNG
  in HTML, JPG, PNG e PDF. Include configurazione, snippet di codice e casi d'uso
  pratici.
keywords:
- groupdocs viewer java tutorial
- render animated png
- how to convert apng to jpg
schemas:
- author: GroupDocs
  dateModified: '2026-06-20'
  description: GroupDocs Viewer Java tutorial that shows how to render APNG files
    to HTML, JPG, PNG, and PDF. Includes setup, code snippets, and practical use cases.
  headline: 'GroupDocs Viewer Java Tutorial: Render Animated PNGs'
  type: TechArticle
- description: GroupDocs Viewer Java tutorial that shows how to render APNG files
    to HTML, JPG, PNG, and PDF. Includes setup, code snippets, and practical use cases.
  name: 'GroupDocs Viewer Java Tutorial: Render Animated PNGs'
  steps:
  - name: '**Set Up Paths** – define where the HTML file and its resources will be
      saved.'
    text: '**Set Up Paths** – define where the HTML file and its resources will be
      saved.'
  - name: '**Initialize Viewer** – create a `Viewer` object with the APNG path.'
    text: '**Initialize Viewer** – create a `Viewer` object with the APNG path.'
  - name: '**Configure Options** – use `HtmlViewOptions.forEmbeddedResources` to embed
      CSS, JS, and images directly into the HTML file, eliminating external dependencies.'
    text: '**Configure Options** – use `HtmlViewOptions.forEmbeddedResources` to embed
      CSS, JS, and images directly into the HTML file, eliminating external dependencies.'
  - name: '**Render** – call `viewer.view(documentPath, htmlOptions)`.'
    text: '**Render** – call `viewer.view(documentPath, htmlOptions)`.'
  - name: '**Configure Paths** – specify the output folder for the generated JPG files.'
    text: '**Configure Paths** – specify the output folder for the generated JPG files.'
  - name: '**Render to JPG** – invoke `viewer.view(documentPath, JpgViewOptions.forEmbeddedResources(outputPath))`.'
    text: '**Render to JPG** – invoke `viewer.view(documentPath, JpgViewOptions.forEmbeddedResources(outputPath))`.'
  - name: '**Result** – each frame becomes `output_1.jpg`, `output_2.jpg`, … preserving
      the original animation sequence.'
    text: '**Result** – each frame becomes `output_1.jpg`, `output_2.jpg`, … preserving
      the original animation sequence.'
  - name: '**Set Output Paths** – choose a folder for the PNG sequence.'
    text: '**Set Output Paths** – choose a folder for the PNG sequence.'
  - name: '**Execute Rendering** – call `viewer.view(documentPath, PngViewOptions.forEmbeddedResources(outputPath))`.'
    text: '**Execute Rendering** – call `viewer.view(documentPath, PngViewOptions.forEmbeddedResources(outputPath))`.'
  - name: '**Outcome** – you receive a series of PNG files that can be recombined
      or used individually.'
    text: '**Outcome** – you receive a series of PNG files that can be recombined
      or used individually.'
  type: HowTo
- questions:
  - answer: Yes, it supports GIF, WebP, and even animated SVG, providing the same
      HTML, image, and PDF output options.
    question: Can GroupDocs Viewer render other animated formats like GIF or WebP?
  - answer: There’s no hard limit, but performance may degrade after ~500 frames;
      consider down‑sampling for very large animations.
    question: Is there a limit to the number of frames an APNG can have?
  - answer: APNG does not support encryption, but if the file is inside a ZIP archive,
      supply the password via `Viewer`’s `load` method.
    question: How do I handle password‑protected APNG files?
  - answer: Absolutely—use `JpgViewOptions.setResolution(300)` and `setQuality(90)`
      before calling `view`.
    question: Can I customize the DPI or quality of the generated JPGs?
  - answer: Yes, GroupDocs Viewer is pure Java and runs on any OS with a compatible
      JRE, making it ideal for Docker deployments.
    question: Does the library work on Linux containers?
  type: FAQPage
title: 'Tutorial di GroupDocs Viewer Java: Rendering di PNG animati'
type: docs
url: /it/java/rendering-basics/render-apng-groupdocs-viewer-java/
weight: 1
---

# Tutorial di GroupDocs Viewer per Java: Renderizzare PNG animati

In questo **tutorial di GroupDocs Viewer per Java**, scoprirai come trasformare i file Animated PNG (APNG) in formati HTML, JPG, PNG e PDF utilizzando la robusta libreria GroupDocs.Viewer. Che tu stia costruendo un portale web, uno strumento di reporting o una pipeline di pubblicazione digitale, il rendering corretto degli APNG è essenziale per preservare la qualità dell'animazione su tutte le piattaforme.

![Renderizzare PNG animati con GroupDocs.Viewer per Java](/viewer/rendering-basics/render-animated-pngs-java.png)  
[Renderizzare PNG animati con GroupDocs.Viewer per Java](/viewer/rendering-basics/render-animated-pngs-java.png)

## Risposte rapide
- **Cosa fa GroupDocs.Viewer?** Renderizza oltre 70 tipi di file—including APNG—in HTML, immagini e PDF senza richiedere software esterno.  
- **Quante righe di codice sono necessarie per convertire APNG in JPG?** Solo due righe: crea un'istanza `Viewer` e chiama `viewer.view(documentPath, JpgViewOptions.forEmbeddedResources(outputPath))`.  
- **È necessaria una licenza per lo sviluppo?** Una licenza di prova funziona per i test; è necessaria una licenza commerciale per la produzione.  
- **Posso renderizzare APNG di grandi dimensioni (100+ fotogrammi) in modo efficiente?** Sì—usa try‑with‑resources e trasmetti l'output per mantenere basso l'uso della memoria.  
- **Maven è l'unico modo per aggiungere la libreria?** Maven è consigliato, ma è possibile usare anche Gradle o aggiungere manualmente i JAR.

## Cos'è GroupDocs Viewer?
**GroupDocs Viewer** è un componente Java che converte oltre 70 formati di documenti e immagini in rappresentazioni web‑friendly come HTML, JPG, PNG e PDF. Gestisce layout complessi, conserva la grafica vettoriale e supporta formati animati come APNG senza dipendenze esterne.

## Perché renderizzare PNG animati con GroupDocs Viewer?
GroupDocs Viewer fornisce un metodo affidabile e ad alte prestazioni per convertire gli APNG preservando la tempistica dell'animazione e la trasparenza. Elimina la necessità di strumenti di terze parti, funziona su qualsiasi piattaforma e si integra facilmente nelle applicazioni Java.

- **Supporto ampio di formati:** oltre 70 formati di input, inclusi APNG, PDF, DOCX e SVG.  
- **Ottimizzato per le prestazioni:** elabora documenti con centinaia di pagine o animazioni da 200 fotogrammi usando meno di 150 MB di RAM su un server tipico.  
- **Zero‑install:** non sono necessarie librerie native o codec specifici per OS, facilitando il deployment su container.  
- **Output coerente:** garantisce rendering pixel‑perfect, preservando trasparenza e tempistica dell'animazione.

## Prerequisiti
- **Java Development Kit (JDK) 8+** – garantisce la compatibilità con le funzionalità moderne del linguaggio.  
- **Maven** – semplifica la gestione delle dipendenze; anche Gradle è supportato.  
- **Un file APNG** – posizionalo nella cartella `resources` del progetto (ad es., `src/main/resources/sample.apng`).  

## Configurare GroupDocs Viewer per Java

### Configurazione Maven
Aggiungi la seguente dipendenza al tuo `pom.xml` per ottenere l'ultima versione stabile:

```xml
<repositories>
   <repository>
      <id>groupdocs-repo</id>
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
Per valutare GroupDocs Viewer, puoi:
- **Scaricare una versione di prova** dal [sito GroupDocs](https://releases.groupdocs.com/viewer/java/).  
- **Richiedere una licenza temporanea** per testare tutte le funzionalità.  
- **Acquistare una licenza di produzione** per utilizzo commerciale illimitato.  
- Per indicazioni dettagliate, consulta la [documentazione ufficiale](https://docs.groupdocs.com/viewer/java/).

### Inizializzazione di base
La classe `Viewer` è il punto di ingresso per tutte le operazioni di rendering. Carica il file sorgente e fornisce metodi per generare output in diversi formati.

`Viewer` rappresenta un documento o un'immagine e orchestra il rendering nel formato di output scelto.

```java
import com.groupdocs.viewer.Viewer;
import com.groupdocs.viewer.options.*;
```

## Come renderizzare PNG animato in HTML?
Carica il file APNG, configura le opzioni HTML e chiama `view`. Il processo è semplice e di solito richiede solo poche righe di codice, rendendolo ideale per integrazioni rapide in servizi web o lavori batch.

```java
   Path outputDirectory = Paths.get("YOUR_OUTPUT_DIRECTORY");
   Path pageFilePathFormat = outputDirectory.resolve("apng_result.html");
   ```

### Ancoraggio della definizione – Istanza Viewer
`Viewer` è la classe core di GroupDocs.Viewer che rappresenta un documento o un'immagine e orchestra il rendering nel formato di output scelto.

### Rendering HTML passo‑a‑passo
1. **Imposta i percorsi** – definisci dove verranno salvati il file HTML e le sue risorse.  
2. **Inizializza Viewer** – crea un oggetto `Viewer` con il percorso dell'APNG.  
3. **Configura le opzioni** – usa `HtmlViewOptions.forEmbeddedResources` per incorporare CSS, JS e immagini direttamente nel file HTML, eliminando dipendenze esterne.  
4. **Renderizza** – chiama `viewer.view(documentPath, htmlOptions)`.

## Come convertire APNG in JPG?
GroupDocs Viewer può estrarre ogni fotogramma dell'animazione come immagine JPG individuale, ideale per miniature o anteprime statiche. La conversione mantiene l'ordine originale dei fotogrammi e consente di controllare qualità e risoluzione dell'immagine.

```java
   Path outputDirectory = Paths.get("YOUR_OUTPUT_DIRECTORY");
   Path pageFilePathFormat = outputDirectory.resolve("apng_result_{0}.jpg");
   ```

### Ancoraggio della definizione – JpgViewOptions
`JpgViewOptions` definisce come ogni fotogramma dell'APNG di origine viene renderizzato in un file JPEG separato, permettendo di impostare qualità, DPI e convenzioni di denominazione.

### Conversione JPG passo‑a‑passo
1. **Configura i percorsi** – specifica la cartella di output per i file JPG generati.  
2. **Renderizza in JPG** – invoca `viewer.view(documentPath, JpgViewOptions.forEmbeddedResources(outputPath))`.  
3. **Risultato** – ogni fotogramma diventa `output_1.jpg`, `output_2.jpg`, … preservando la sequenza originale dell'animazione.

## Come convertire APNG in PNG?
Quando è richiesta qualità lossless, PNG è il formato di destinazione ideale. GroupDocs Viewer estrae ogni fotogramma senza artefatti di compressione, mantenendo intatta la trasparenza e garantendo fedeltà pixel‑perfect.

```java
   Path outputDirectory = Paths.get("YOUR_OUTPUT_DIRECTORY");
   Path pageFilePathFormat = outputDirectory.resolve("apng_result_{0}.png");
   ```

### Ancoraggio della definizione – PngViewOptions
`PngViewOptions` indica al viewer di scrivere ogni fotogramma dell'animazione come file PNG separato, conservando trasparenza e dati pixel esatti.

### Estrazione PNG passo‑a‑passo
1. **Imposta i percorsi di output** – scegli una cartella per la sequenza PNG.  
2. **Esegui il rendering** – chiama `viewer.view(documentPath, PngViewOptions.forEmbeddedResources(outputPath))`.  
3. **Esito** – riceverai una serie di file PNG che possono essere ricombinati o usati individualmente.

## Come convertire APNG in PDF?
Compilare una sequenza animata in un unico PDF è utile per documentazione stampabile o scopi di archiviazione. Ogni fotogramma diventa una pagina separata, preservando l'ordine dell'animazione in un formato statico e condivisibile.

```java
   Path outputDirectory = Paths.get("YOUR_OUTPUT_DIRECTORY");
   Path pageFilePathFormat = outputDirectory.resolve("apng_result.pdf");
   ```

### Ancoraggio della definizione – PdfViewOptions
`PdfViewOptions` aggrega tutti i fotogrammi dell'APNG in un unico PDF multipagina, con ogni fotogramma che occupa una pagina distinta.

### Generazione PDF passo‑a‑passo
1. **Definisci i percorsi** – imposta il percorso del file PDF di destinazione.  
2. **Renderizza in PDF** – esegui `viewer.view(documentPath, PdfViewOptions.forEmbeddedResources(outputPath))`.  
3. **Risultato** – un PDF in cui ogni pagina rispecchia un fotogramma dell'animazione originale.

## Applicazioni pratiche
- **Sviluppo web:** incorpora APNG in blog o pagine prodotto senza dipendere da GIF, garantendo animazioni più fluide e file di dimensioni inferiori.  
- **Pubblicazione digitale:** converti grafici animati in dispense PDF per conferenze, preservando la narrazione visiva.  
- **Asset di marketing:** genera snapshot JPG o PNG ad alta risoluzione per banner, annunci e post sui social media.  
- **Data visualization:** trasforma grafici a serie temporali in immagini fotogramma‑per‑fotogramma per dashboard analitici.

## Considerazioni sulle prestazioni
- **Ottimizzazione dimensione immagine:** ridimensiona o comprimi l'APNG di origine prima del rendering per ridurre l'uso della CPU.  
- **Gestione delle risorse:** avvolgi `Viewer` in un blocco try‑with‑resources per chiudere automaticamente gli stream e liberare buffer nativi.  
- **Elaborazione batch:** quando gestisci decine di APNG, elabora in batch da 10–20 per evitare picchi di memoria.

## Problemi comuni e soluzioni
- **Fotogrammi mancanti:** assicurati che l'APNG sia conforme alla specifica APNG; alcuni strumenti più vecchi generano file non standard.  
- **Tempistica errata:** usa `AnimatedPngOptions` (se disponibile) per regolare il ritardo dei fotogrammi dopo il rendering.  
- **Errori Out‑of‑Memory:** abilita `viewer.setCacheSize(50)` per limitare la cache in memoria per animazioni di grandi dimensioni.

## Domande frequenti

**Q: GroupDocs Viewer può renderizzare altri formati animati come GIF o WebP?**  
A: Sì, supporta GIF, WebP e anche SVG animato, offrendo le stesse opzioni di output HTML, immagine e PDF.

**Q: Esiste un limite al numero di fotogrammi che un APNG può contenere?**  
A: Non c'è un limite rigido, ma le prestazioni possono degradarsi dopo circa 500 fotogrammi; considera il down‑sampling per animazioni molto grandi.

**Q: Come gestire file APNG protetti da password?**  
A: L'APNG non supporta la crittografia, ma se il file è all'interno di un archivio ZIP, fornisci la password tramite il metodo `load` di `Viewer`.

**Q: Posso personalizzare DPI o qualità dei JPG generati?**  
A: Assolutamente—usa `JpgViewOptions.setResolution(300)` e `setQuality(90)` prima di chiamare `view`.

**Q: La libreria funziona su container Linux?**  
A: Sì, GroupDocs Viewer è puro Java e gira su qualsiasi OS con una JRE compatibile, rendendolo ideale per deployment Docker.

**Ultimo aggiornamento:** 2026-06-20  
**Testato con:** GroupDocs.Viewer 23.9 per Java  
**Autore:** GroupDocs

```java
   try (Viewer viewer = new Viewer("YOUR_DOCUMENT_DIRECTORY/SAMPLE_APNG")) {
       HtmlViewOptions options = HtmlViewOptions.forEmbeddedResources(pageFilePathFormat);
       // Render the APNG into HTML with embedded resources.
       viewer.view(options);
   }
   ```

```java
   try (Viewer viewer = new Viewer("YOUR_DOCUMENT_DIRECTORY/SAMPLE_APNG")) {
       JpgViewOptions options = new JpgViewOptions(pageFilePathFormat);
       // Each frame becomes a separate JPG image.
       viewer.view(options);
   }
   ```

```java
   try (Viewer viewer = new Viewer("YOUR_DOCUMENT_DIRECTORY/SAMPLE_APNG")) {
       PngViewOptions options = new PngViewOptions(pageFilePathFormat);
       // Converts each frame to a separate PNG.
       viewer.view(options);
   }
   ```

```java
   try (Viewer viewer = new Viewer("YOUR_DOCUMENT_DIRECTORY/SAMPLE_APNG")) {
       PdfViewOptions options = new PdfViewOptions(pageFilePathFormat);
       // Convert the APNG into a single PDF.
       viewer.view(options);
   }
   ```

## Tutorial correlati

- [Tutorial di rendering di documenti Java - Convertire file in HTML, PDF e Immagini](/viewer/java/rendering-basics/)
- [Come renderizzare PDF in HTML e ottimizzare la qualità dell'immagine in Java con GroupDocs.Viewer](/viewer/java/advanced-rendering/adjust-image-quality-groupdocs-viewer-java/)
- [Come convertire file DOCX in PNG usando GroupDocs.Viewer per Java](/viewer/java/rendering-basics/render-docx-png-groupdocs-viewer-java/)