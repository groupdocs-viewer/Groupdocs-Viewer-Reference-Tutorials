---
date: '2026-02-18'
description: Scopri come convertire i file WMZ e WMF in PDF, HTML, JPG e PNG usando
  GroupDocs Viewer per Java. Questa guida copre GroupDocs Viewer per Java e la conversione
  di grafica vettoriale in Java.
keywords:
- convert WMZ/WMF documents
- GroupDocs Viewer for Java
- rendering formats
title: Come convertire WMZ in PDF e altri formati usando GroupDocs Viewer per Java
type: docs
url: /it/java/export-conversion/convert-wmz-wmf-groupdocs-viewer-java/
weight: 1
---

 produce final content.# Come Convertire WMZ in PDF e Altri Formati Utilizzando GroupDocs Viewer per Java

Convertire i file WMZ (Web Metafile) e WMF (Windows Metafile) in formati più accessibili—specialmente **convert WMZ to PDF**—può essere complicato perché questi formati grafici vettoriali memorizzano le istruzioni di disegno anziché i dati pixel. Con **GroupDocs Viewer for Java**, è possibile renderizzare documenti WMZ/WMF in HTML, JPG, PNG, **PDF** e altri formati popolari con poche righe di codice.

![Converti Documenti WMZ/WMF con GroupDocs.Viewer per Java](/viewer/export-conversion/convert-wmz-wmf-documents.png)

In questo tutorial imparerai come configurare la libreria, renderizzare i file WMZ/WMF nell'output desiderato e gestire le difficoltà comuni. Alla fine, sarai in grado di integrare **groupdocs viewer java** nelle tue applicazioni Java per **java convert vector graphics** rapidamente e in modo affidabile.

## Risposte Rapide
- **In quali formati può essere convertito WMZ/WMF?** HTML, JPG, PNG e PDF sono pienamente supportati.  
- **Ho bisogno di una licenza per lo sviluppo?** Una prova gratuita è sufficiente per i test; una licenza commerciale rimuove i limiti di valutazione.  
- **Quale versione di Java è richiesta?** Si consiglia Java 8 o successiva.  
- **Posso renderizzare solo pagine specifiche?** Sì, è possibile specificare intervalli di pagine nelle opzioni di visualizzazione.  
- **L'uso della memoria è un problema per file di grandi dimensioni?** Usa try‑with‑resources e renderizza solo le pagine necessarie per mantenere bassa la memoria.

## Cos'è “convert WMZ to PDF”?
Convertire WMZ in PDF significa prendere il file WMZ basato su vettori e rasterizzarlo (o preservare i suoi dati vettoriali) all'interno di un contenitore PDF. Il PDF è universalmente visualizzabile, ricercabile e stampabile, rendendolo ideale per l'archiviazione e la condivisione di grafiche WMZ.

## Perché utilizzare GroupDocs Viewer per Java per convertire grafica vettoriale?
- **Alta fedeltà**: La libreria preserva la qualità originale del disegno, sia che l'output sia PDF o PNG.  
- **Zero dipendenze esterne**: Non è necessario alcun library nativo di Windows; tutto funziona su qualsiasi piattaforma con JDK.  
- **API semplice**: Un'istanza `Viewer` e una singola chiamata `view` gestiscono l'intera conversione.  
- **Scalabile**: Funziona altrettanto bene per icone a pagina singola e disegni tecnici a più pagine.

## Prerequisiti

### Librerie Richieste
- **GroupDocs.Viewer for Java** – il motore di rendering principale.  
- Java Development Kit (JDK) 8+.

### Configurazione dell'Ambiente
- IDE come IntelliJ IDEA o Eclipse.  
- Maven per la gestione delle dipendenze (o Gradle se preferisci).

### Prerequisiti di Conoscenza
- Familiarità con Java file I/O (`java.nio.file.Path`).  
- Comprensione di base di come i visualizzatori di documenti renderizzano i contenuti.

## Configurazione di GroupDocs.Viewer per Java

Aggiungi il repository e la dipendenza al tuo `pom.xml`:

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

> **Suggerimento licenza:** Usa una prova gratuita per la valutazione, poi applica una licenza temporanea o acquistata per sbloccare tutte le funzionalità.

Una volta risolta la dipendenza, puoi creare un'istanza `Viewer` che verrà riutilizzata per ogni fase di conversione.

## Guida all'Implementazione

Passeremo in rassegna quattro scenari di conversione: HTML, JPG, PNG e PDF. Ogni esempio segue lo stesso schema—definire un percorso di output, istanziare `Viewer` con il file WMZ di origine, configurare le opzioni di visualizzazione appropriate e chiamare `view`.

### Rendering WMZ/WMF in HTML

#### Panoramica
L'output HTML ti consente di incorporare la grafica direttamente nelle pagine web, con tutte le risorse (immagini, CSS) contenute in un unico file.

**Passo 1: Definisci il Percorso della Directory di Output**

```java
Path outputDirectory = Utils.getOutputDirectoryPath("RenderingWmzAndWmf");
Path pageFilePathFormat = outputDirectory.resolve("wmz_result.html");
```

**Passo 2: Inizializza Viewer e Renderizza in HTML**

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

**Passo 1: Definisci il Percorso della Directory di Output**

```java
Path outputDirectory = Utils.getOutputDirectoryPath("RenderingWmzAndWmf");
Path pageFilePathFormat = outputDirectory.resolve("wmz_result.jpg");
```

**Passo 2: Inizializza Viewer e Renderizza in JPG**

```java
try (Viewer viewer = new Viewer(TestFiles.SAMPLE_WMZ)) {
    JpgViewOptions options = new JpgViewOptions(pageFilePathFormat);
    viewer.view(options);
}
```

### Rendering WMZ/WMF in PNG

#### Panoramica
PNG supporta la trasparenza, rendendolo ideale per grafiche che devono fondersi con diversi sfondi.

**Passo 1: Definisci il Percorso della Directory di Output**

```java
Path outputDirectory = Utils.getOutputDirectoryPath("RenderingWmzAndWmf");
Path pageFilePathFormat = outputDirectory.resolve("wmz_result.png");
```

**Passo 2: Inizializza Viewer e Renderizza in PNG**

```java
try (Viewer viewer = new Viewer(TestFiles.SAMPLE_WMZ)) {
    PngViewOptions options = new PngViewOptions(pageFilePathFormat);
    viewer.view(options);
}
```

### Rendering WMZ/WMF in PDF

#### Panoramica
PDF fornisce un documento indipendente dalla piattaforma, ricercabile, che mantiene il layout originale.

**Passo 1: Definisci il Percorso della Directory di Output**

```java
Path outputDirectory = Utils.getOutputDirectoryPath("RenderingWmzAndWmf");
Path pageFilePathFormat = outputDirectory.resolve("wmz_result.pdf");
```

**Passo 2: Inizializza Viewer e Renderizza in PDF**

```java
try (Viewer viewer = new Viewer(TestFiles.SAMPLE_WMZ)) {
    PdfViewOptions options = new PdfViewOptions(pageFilePathFormat);
    viewer.view(options);
}
```

## Problemi Comuni e Soluzioni

| Problema | Causa | Soluzione |
|----------|-------|-----------|
| **OutOfMemoryError** su file WMZ di grandi dimensioni | Viewer carica l'intero documento in memoria | Renderizza una pagina alla volta usando `PageStreamViewOptions` o aumenta l'heap JVM (`-Xmx`). |
| **Font mancanti** in PDF | Font non incorporato nel WMZ di origine | Installa i font richiesti sulla macchina host o usa `FontSettings` per fornire font personalizzati. |
| **Output PNG vuoto** | Percorso di output errato o permessi di scrittura insufficienti | Verifica che `outputDirectory` esista e che l'applicazione abbia i permessi di scrittura. |
| **Risorse HTML non caricate** | Uso di `forExternalResources` senza copiare i file | Usa `forEmbeddedResources` per un file HTML autonomo. |

## Domande Frequenti

**D: Posso convertire WMF in PNG usando lo stesso codice?**  
R: Sì. L'esempio PNG funziona sia per file WMZ che WMF; basta sostituire `TestFiles.SAMPLE_WMZ` con la tua sorgente WMF.

**D: È possibile convertire solo un sottoinsieme di pagine?**  
R: Assolutamente. Usa `PdfViewOptions` (o le opzioni corrispondenti per gli altri formati) e chiama `setPageNumbers(List<Integer>)` prima della renderizzazione.

**D: Ho bisogno di una licenza separata per ogni formato di output?**  
R: No. Una singola licenza GroupDocs Viewer copre tutti i formati supportati, inclusi HTML, JPG, PNG e PDF.

**D: Come influisce “java convert vector graphics” sulle prestazioni?**  
R: La conversione da vettoriale a raster è intensiva per la CPU. Per grandi lotti, considera il multi‑threading e il riutilizzo di una singola istanza `Viewer` tra i file.

**D: Il PDF manterrà la qualità vettoriale o sarà rasterizzato?**  
R: Quando si converte WMZ/WMF in PDF, GroupDocs Viewer preserva le istruzioni vettoriali dove possibile, risultando in un PDF scalabile.

## Conclusione

Ora hai una guida completa, pronta per la produzione, per **convert WMZ to PDF** e altri formati comuni usando **GroupDocs Viewer per Java**. Che tu stia costruendo un servizio web che serve grafiche al volo o uno strumento di archiviazione che salva i documenti come PDF, i passaggi sopra ti aiuteranno a raggiungere l'obiettivo rapidamente.

---

**Last Updated:** 2026-02-18  
**Tested With:** GroupDocs.Viewer 25.2 for Java  
**Author:** GroupDocs