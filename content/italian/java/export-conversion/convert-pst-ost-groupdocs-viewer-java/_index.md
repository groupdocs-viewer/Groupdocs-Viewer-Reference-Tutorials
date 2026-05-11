---
date: '2026-02-15'
description: Scopri come convertire i file pst in html e altri formati come JPG, PNG,
  PDF usando GroupDocs.Viewer per Java. Questa guida copre tutti i passaggi e le configurazioni
  necessarie.
keywords:
- convert PST/OST
- GroupDocs.Viewer for Java
- render documents
title: Converti PST in HTML, JPG, PNG, PDF usando GroupDocs.Viewer per Java
type: docs
url: /it/java/export-conversion/convert-pst-ost-groupdocs-viewer-java/
weight: 1
---

# Converti PST in HTML, JPG, PNG, PDF usando GroupDocs.Viewer per Java

Stai cercando di **convertire pst in html** o altri formati come JPG, PNG o PDF? Con la potente libreria GroupDocs.Viewer per Java, questa operazione è semplice ed efficiente. In questo tutorial imparerai a renderizzare i file Outlook PST/OST in HTML adatto al web, file immagine o un unico PDF, rendendo i tuoi archivi email facili da condividere e archiviare.

![Converti PST/OST in HTML, JPG, PNG, PDF con GroupDocs.Viewer per Java](/viewer/export-conversion/convert-pst-ost-to-html-jpg-png-pdf.png)

**Cosa imparerai**
- Come configurare GroupDocs.Viewer per Java in un progetto Maven.  
- Istruzioni passo‑a‑passo per **java convert pst** file in HTML, JPG, PNG e PDF.  
- Suggerimenti di configurazione per prestazioni ottimali e problemi comuni.

## Risposte rapide
- **Quale libreria gestisce la conversione PST?** GroupDocs.Viewer per Java.  
- **Posso convertire PST in PDF direttamente?** Sì, usando `PdfViewOptions`.  
- **È necessaria una licenza per la produzione?** È necessaria una licenza GroupDocs valida.  
- **Quale versione di Java è supportata?** JDK 8 o superiore.  
- **Devo estrarre gli allegati manualmente?** No, il visualizzatore li renderizza automaticamente.

## Come convertire pst in html usando GroupDocs.Viewer per Java
Di seguito trovi una panoramica concisa del processo di conversione prima di immergerti negli esempi di codice dettagliati.

### Perché scegliere GroupDocs.Viewer?
- **Alta fedeltà** nella resa dei corpi delle email, degli allegati e della formattazione.  
- **Molteplici formati di output** (HTML, JPG, PNG, PDF) da una singola API.  
- **Nessuna dipendenza esterna** – tutto gira all'interno della tua applicazione Java.

## Prerequisiti

- **GroupDocs.Viewer per Java** – versione 25.2 o successiva.  
- **Java Development Kit (JDK)** – 8 o più recente.  
- Maven per la gestione delle dipendenze.  
- Conoscenza di base di Java e familiarità con Maven.

## Configurazione di GroupDocs.Viewer per Java

Aggiungi il repository GroupDocs e la dipendenza al tuo `pom.xml`:

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
- **Prova gratuita** – esplora tutte le funzionalità senza costi.  
- **Licenza temporanea** – estendi il periodo di valutazione se necessario.  
- **Licenza completa** – necessaria per le distribuzioni in produzione.

### Inizializzazione di base

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

## Guida all'implementazione

Le sezioni seguenti ti guidano nella resa dei file PST/OST in ciascun formato supportato.

### Rendering di documenti PST/OST in HTML

#### Passo 1: Configura la directory di output

```java
Path outputDirectory = Paths.get("YOUR_OUTPUT_DIRECTORY");
Path pageFilePathFormat = outputDirectory.resolve("PST_result.html");
```

#### Passo 2: Configura le opzioni di caricamento

```java
LoadOptions loadOptions = new LoadOptions();
loadOptions.setResourceLoadingTimeout(100);
```

#### Passo 3: Inizializza Viewer e rendi HTML

```java
try (Viewer viewer = new Viewer("YOUR_DOCUMENT_DIRECTORY/SAMPLE_PST", loadOptions)) {
    HtmlViewOptions options = HtmlViewOptions.forEmbeddedResources(pageFilePathFormat);
    viewer.view(options);
}
```

### Rendering di documenti PST/OST in JPG

#### Passo 1: Configura la directory di output

```java
Path outputDirectory = Paths.get("YOUR_OUTPUT_DIRECTORY");
Path pageFilePathFormat = outputDirectory.resolve("PST_result_{0}.jpg");
```

#### Passo 2: Configura le opzioni di caricamento

```java
LoadOptions loadOptions = new LoadOptions();
loadOptions.setResourceLoadingTimeout(100);
```

#### Passo 3: Inizializza Viewer e rendi JPG

```java
try (Viewer viewer = new Viewer("YOUR_DOCUMENT_DIRECTORY/SAMPLE_PST", loadOptions)) {
    JpgViewOptions options = new JpgViewOptions(pageFilePathFormat);
    viewer.view(options);
}
```

### Rendering di documenti PST/OST in PNG

#### Passo 1: Configura la directory di output

```java
Path outputDirectory = Paths.get("YOUR_OUTPUT_DIRECTORY");
Path pageFilePathFormat = outputDirectory.resolve("PST_result_{0}.png");
```

#### Passo 2: Configura le opzioni di caricamento

```java
LoadOptions loadOptions = new LoadOptions();
loadOptions.setResourceLoadingTimeout(100);
```

#### Passo 3: Inizializza Viewer e rendi PNG

```java
try (Viewer viewer = new Viewer("YOUR_DOCUMENT_DIRECTORY/SAMPLE_PST", loadOptions)) {
    PngViewOptions options = new PngViewOptions(pageFilePathFormat);
    viewer.view(options);
}
```

### Rendering di documenti PST/OST in PDF

#### Passo 1: Configura la directory di output

```java
Path outputDirectory = Paths.get("YOUR_OUTPUT_DIRECTORY");
Path pageFilePathFormat = outputDirectory.resolve("PST_result.pdf");
```

#### Passo 2: Configura le opzioni di caricamento

```java
LoadOptions loadOptions = new LoadOptions();
loadOptions.setResourceLoadingTimeout(100);
```

#### Passo 3: Inizializza Viewer e rendi PDF

```java
try (Viewer viewer = new Viewer("YOUR_DOCUMENT_DIRECTORY/SAMPLE_PST", loadOptions)) {
    PdfViewOptions options = new PdfViewOptions(pageFilePathFormat);
    viewer.view(options);
}
```

## Applicazioni pratiche

- **Archiviazione email:** Converti grandi archivi PST in HTML o PDF ricercabili per la conformità.  
- **Sistemi di gestione documentale:** Archivia i file convertiti in sistemi che accettano solo PDF, PNG o JPG.  
- **Piattaforme di collaborazione:** Condividi le email convertite come immagini su Slack o Teams.  
- **Revisione legale:** Fornisci ai tribunali versioni PDF delle prove email.  
- **Strategie di backup:** Mantieni snapshot PNG o JPG leggeri dei messaggi critici.

## Considerazioni sulle prestazioni

- **Gestione delle risorse:** Riutilizza le istanze `Viewer` durante l'elaborazione di più file per ridurre l'overhead.  
- **Ottimizzazione della memoria:** Regola `loadOptions.setResourceLoadingTimeout` in base alla capacità del server.  
- **Elaborazione asincrona:** Sposta la conversione su thread in background per interfacce utente reattive.  

## Domande frequenti

**D: Come **convertire pst in pdf** con la stessa base di codice?**  
R: Usa `PdfViewOptions` come mostrato nella sezione di rendering PDF; il resto del codice rimane identico.

**D: GroupDocs.Viewer può gestire file PST criptati?**  
R: Sì, fornisci la password tramite `LoadOptions.setPassword("yourPassword")` prima del rendering.

**D: Qual è la differenza tra **java convert pst** in PNG rispetto a JPG?**  
R: PNG mantiene la qualità lossless, ideale per screenshot, mentre JPG offre dimensioni di file più piccole per anteprime email.

**D: Esiste un modo per **how to convert pst** file in blocco?**  
R: Avvolgi la logica di rendering in un ciclo che itera su una directory di file PST; riutilizza la stessa configurazione `Viewer` per ogni file.

## Conclusione

Ora hai una guida completa, pronta per la produzione, per **convertire pst in html**, JPG, PNG e PDF usando GroupDocs.Viewer per Java. Seguendo i passaggi sopra potrai integrare la conversione delle email in qualsiasi flusso di lavoro basato su Java, migliorare l'accessibilità e soddisfare i requisiti di conformità.

---

**Ultimo aggiornamento:** 2026-02-15  
**Testato con:** GroupDocs.Viewer per Java 25.2  
**Autore:** GroupDocs