---
date: '2026-09-05'
description: Scopri come generare html da pdf e disabilitare il raggruppamento dei
  caratteri usando GroupDocs Viewer for Java per una rappresentazione testuale precisa.
keywords:
- generate html from pdf
- render pdf to html
- convert pdf to html
lastmod: '2026-09-05'
og_description: Genera html da pdf con GroupDocs Viewer for Java disabilitando il
  raggruppamento dei caratteri per un posizionamento preciso dei glifi. Scopri l'implementazione
  passo‑passo.
og_image_alt: GroupDocs Viewer for Java rendering PDF to HTML with precise character
  placement
og_title: Genera html da pdf e disabilita il raggruppamento – GroupDocs Java
schemas:
- author: GroupDocs
  dateModified: '2026-09-05'
  description: Learn how to generate html from pdf and disable character grouping
    using GroupDocs Viewer for Java for precise text representation.
  headline: Generate html from pdf & disable grouping – GroupDocs Java
  type: TechArticle
- description: Learn how to generate html from pdf and disable character grouping
    using GroupDocs Viewer for Java for precise text representation.
  name: Generate html from pdf & disable grouping – GroupDocs Java
  steps:
  - name: define output directory
    text: '**Why?** This ensures your rendered HTML files are stored in a dedicated
      folder, making it easy to locate and manage them later.'
  - name: configure file path format
    text: '**Why?** Using a placeholder (`{0}`) lets the viewer create a separate
      HTML file for each PDF page, keeping the output organized.'
  - name: initialize HTML view options
    text: '**Why?** Embedded resources bundle images, fonts, and CSS directly with
      each HTML page, which is ideal for web‑based viewers or e‑learning platforms.'
  - name: disable character grouping
    text: '`setDisableCharsGrouping(true)` disables the default behavior of grouping
      adjacent characters, ensuring each glyph is rendered separately. **Why?** This
      is the crucial line that tells the rendering engine **not** to merge adjacent
      characters, guaranteeing that the generated HTML reflects the exact g'
  - name: render the document
    text: '`Viewer` is the primary class that opens a document and provides rendering
      capabilities. **Why?** Wrapping the `Viewer` in a try‑with‑resources block guarantees
      that all native resources are released automatically, preventing memory leaks
      in long‑running applications.'
  type: HowTo
- questions:
  - answer: It forces the renderer to treat each character as an independent element,
      preserving exact layout.
    question: What does “disable grouping” do?
  - answer: '`viewOptions.getPdfOptions().setDisableCharsGrouping(true)`.'
    question: Which API option controls this?
  - answer: A trial works for testing, but a full license is required for production.
    question: Do I need a license?
  - answer: Yes—use `HtmlViewOptions` to create HTML output while disabling grouping.
    question: Can I generate html from pdf at the same time?
  - answer: It’s primarily for PDFs, but the viewer supports many other formats.
    question: Is this feature limited to PDFs?
  type: FAQPage
tags:
- generate html
- GroupDocs Viewer
- Java document rendering
title: Genera html da pdf e disabilita il raggruppamento – GroupDocs Java
type: docs
url: /it/java/advanced-rendering/groupdocs-viewer-java-disable-character-grouping-pdf/
weight: 1
---

# Genera html da pdf e disabilita il raggruppamento con GroupDocs Viewer per Java

In molti progetti è necessario **generare html da pdf** mantenendo ogni glifo esattamente al suo posto. Questo è particolarmente vero per script complessi, lingue antiche o documenti legali dove un singolo carattere fuori posto può cambiare il significato. In questo tutorial ti guideremo attraverso l’intero processo di rendering dei PDF in HTML con GroupDocs Viewer per Java e ti mostreremo **come disabilitare il raggruppamento** in modo che ogni carattere sia trattato come un elemento indipendente.

![Precise Rendering Techniques with GroupDocs.Viewer for Java](/viewer/advanced-rendering/precise-rendering-techniques-java.png)

## Risposte rapide
- **Cosa fa “disabilitare il raggruppamento”?** Forza il motore di rendering a trattare ogni carattere come un elemento indipendente, preservando il layout esatto.  
- **Quale opzione API controlla questo?** `viewOptions.getPdfOptions().setDisableCharsGrouping(true)`.  
- **Ho bisogno di una licenza?** Una versione di prova funziona per i test, ma è necessaria una licenza completa per la produzione.  
- **Posso generare html da pdf contemporaneamente?** Sì—usa `HtmlViewOptions` per creare l’output HTML disabilitando il raggruppamento.  
- **Questa funzionalità è limitata ai PDF?** È principalmente per i PDF, ma il visualizzatore supporta molti altri formati.

## Cos'è generare html da pdf?
`generate html from pdf` descrive il processo di conversione di un documento PDF in un insieme di pagine HTML che mantengono il layout originale, i font e le immagini. Questa conversione consente una facile visualizzazione web, indicizzazione e interazione senza la necessità di un plugin PDF.

## Perché usare GroupDocs Viewer per Java?
GroupDocs.Viewer per Java supporta **oltre 100 formati di input** e può renderizzare PDF fino a **500 pagine** senza caricare l’intero file in memoria. La libreria elabora ogni pagina in streaming, riducendo l’utilizzo dell’heap fino al **70 %** rispetto al caricamento dell’intero documento. Queste capacità quantificate lo rendono una scelta affidabile per pipeline di documenti enterprise ad alto volume.

## Introduzione

Quando si lavora con documenti PDF, la precisione nel rendering è fondamentale—soprattutto con strutture di testo complesse come geroglifici o lingue che richiedono una rappresentazione precisa dei caratteri. La funzionalità “Character Grouping” spesso causa problemi raggruppando i caratteri in modo errato, portando a una cattiva interpretazione del contenuto del documento. Questo può essere particolarmente problematico per gli utenti che necessitano di una replica esatta del layout testuale dei loro documenti.

**GroupDocs.Viewer per Java** è una libreria server‑side che renderizza oltre 100 formati di documento in HTML, immagini e PDF, garantendo una fedeltà pixel‑perfect.

### Prerequisiti

Prima di immergerti nell’implementazione del codice, assicurati di soddisfare i seguenti requisiti:
- **Librerie e dipendenze**: Avrai bisogno di GroupDocs.Viewer per Java versione 25.2 o successiva.  
- **Configurazione dell’ambiente**: Installa un Java Development Kit (JDK) e configura il tuo IDE per progetti Maven.  
- **Prerequisiti di conoscenza**: Programmazione Java di base, gestione del file‑system e familiarità con Maven.

## Come generare html da pdf con GroupDocs Viewer

Generare html da pdf è un processo in due fasi: configurare il visualizzatore, quindi renderizzare il documento. La chiave è disattivare il raggruppamento dei caratteri prima del rendering in modo che l’output HTML rispecchi il layout originale del PDF carattere per carattere.

### Configurazione di GroupDocs.Viewer per Java

#### Installazione tramite Maven

Aggiungi la seguente dipendenza al tuo `pom.xml`:

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

#### Acquisizione della licenza

Per sfruttare appieno GroupDocs.Viewer, considera l’acquisizione di una licenza:
- **Prova gratuita**: Inizia con la versione di prova per testare le funzionalità.  
- **Licenza temporanea**: Richiedi una licenza temporanea se hai bisogno di più tempo.  
- **Acquisto**: Per progetti a lungo termine, è consigliabile acquistare una licenza.

#### Inizializzazione e configurazione di base

`HtmlViewOptions` configura il formato di output e le opzioni per il rendering di un documento in HTML.

```java
import com.groupdocs.viewer.Viewer;
import com.groupdocs.viewer.options.HtmlViewOptions;
import java.nio.file.Path;

// Initialize the GroupDocs Viewer
Path outputDirectory = Utils.getOutputDirectoryPath("DisableCharactersGrouping");
Path pageFilePathFormat = outputDirectory.resolve("page_{0}.html");

HtmlViewOptions viewOptions = HtmlViewOptions.forEmbeddedResources(pageFilePathFormat);
viewOptions.getPdfOptions().setDisableCharsGrouping(true);

try (Viewer viewer = new Viewer("YOUR_DOCUMENT_DIRECTORY/HIEROGLYPHS_PDF")) {
    viewer.view(viewOptions);
}
```

### Guida all'implementazione

#### Funzionalità: disabilitare il raggruppamento dei caratteri

Di seguito analizziamo ogni riga dell’esempio in modo da capire **perché** la utilizziamo e **come** contribuisce a generare html da pdf senza l’unione indesiderata dei caratteri.

##### Passo 1: definire la directory di output  

```java
Path outputDirectory = Utils.getOutputDirectoryPath("DisableCharactersGrouping");
```

**Perché?** Questo garantisce che i file HTML renderizzati siano archiviati in una cartella dedicata, facilitandone la localizzazione e la gestione successiva.

##### Passo 2: configurare il formato del percorso file  

```java
Path pageFilePathFormat = outputDirectory.resolve("page_{0}.html");
```

**Perché?** L’uso di un segnaposto (`{0}`) permette al visualizzatore di creare un file HTML separato per ogni pagina PDF, mantenendo l’output organizzato.

##### Passo 3: inizializzare le opzioni di visualizzazione HTML  

```java
HtmlViewOptions viewOptions = HtmlViewOptions.forEmbeddedResources(pageFilePathFormat);
```

**Perché?** Le risorse incorporate raggruppano immagini, font e CSS direttamente con ogni pagina HTML, ideale per visualizzatori web o piattaforme e‑learning.

##### Passo 4: disabilitare il raggruppamento dei caratteri  

`setDisableCharsGrouping(true)` disabilita il comportamento predefinito di raggruppare i caratteri adiacenti, assicurando che ogni glifo venga renderizzato separatamente.

```java
viewOptions.getPdfOptions().setDisableCharsGrouping(true);
```

**Perché?** Questa è la riga cruciale che indica al motore di rendering **di non** unire i caratteri adiacenti, garantendo che l’HTML generato rifletta la posizione esatta dei glifi nel PDF di origine.

##### Passo 5: renderizzare il documento  

`Viewer` è la classe principale che apre un documento e fornisce le capacità di rendering.

```java
try (Viewer viewer = new Viewer("YOUR_DOCUMENT_DIRECTORY/HIEROGLYPHS_PDF")) {
    viewer.view(viewOptions);
}
```

**Perché?** Avvolgere il `Viewer` in un blocco try‑with‑resources garantisce che tutte le risorse native vengano rilasciate automaticamente, evitando perdite di memoria in applicazioni a lungo termine.

## Come il disabilitare il raggruppamento dei caratteri migliora la fedeltà dell'HTML?

Disabilitare il raggruppamento dei caratteri costringe il motore a emettere ogni glifo come un elemento HTML separato, preservando la spaziatura, le legature e i segni diacritici esattamente come appaiono nel PDF di origine. Il risultato è una rappresentazione web fedele, essenziale per script in cui ordine e spaziatura dei caratteri trasmettono significato, come arabo, devanagari o testi geroglifici antichi.

## Quali sono le implicazioni sulle prestazioni del disabilitare il raggruppamento?

Disattivare il raggruppamento aumenta leggermente il consumo di CPU perché il renderer elabora ogni carattere individualmente. In pratica, l’overhead è inferiore al **5 %** per PDF tipici di 100 pagine e rimane sotto il **12 %** per documenti superiori a 500 pagine, a condizione che l’heap JVM sia dimensionato adeguatamente (es. `-Xmx2g`). Il compromesso è giustificato quando è richiesta una fedeltà visiva esatta.

## Problemi comuni e soluzioni

- **FileNotFoundException** – Verifica il percorso passato a `new Viewer(...)`. Usa percorsi assoluti o `Path.of(...)` per maggiore chiarezza.  
- **Permessi di scrittura** – Assicurati che la directory di output sia scrivibile dal processo Java; su Linux potresti dover regolare i permessi della cartella (`chmod 775`).  
- **Mancata corrispondenza di versione** – L’opzione `setDisableCharsGrouping` è disponibile a partire dalla versione 25.2. Verifica che il tuo `pom.xml` rifletta la versione corretta.  

## Applicazioni pratiche

1. **Preservazione linguistica** – Ideale per renderizzare documenti in cinese, giapponese, arabo o script antichi dove la spaziatura dei caratteri è significativa.  
2. **Documenti legali e finanziari** – Garantisce una replica testuale esatta per pratiche soggette a normative rigorose.  
3. **Risorse educative** – Perfetto per libri di testo che includono diagrammi complessi, annotazioni o contenuti multilingue.

## Considerazioni sulle prestazioni

- **Ottimizzare l’uso delle risorse** – PDF di grandi dimensioni possono consumare molta memoria. Elabora le pagine in batch e disponi prontamente le istanze di `Viewer`.  
- **Gestione della memoria Java** – Regola l’heap JVM (`-Xmx2g` o superiore) se prevedi di elaborare PDF di centinaia di pagine.  
- **Rendering parallelo** – Per conversioni di massa, avvia thread separati, ciascuno con la propria istanza di `Viewer`, per sfruttare CPU multi‑core.

## Domande frequenti

**D:** *Perché dovrei disabilitare il raggruppamento dei caratteri?*  
**R:** Disabilitare il raggruppamento impedisce al renderer di unire caratteri che appartengono a glifi distinti, fondamentale per script in cui spaziatura e ordine hanno significato.

**D:** *L’impostazione `setDisableCharsGrouping` è valida solo per l’output HTML?*  
**R:** No, influisce sul motore di rendering PDF sottostante, quindi qualsiasi formato di output (HTML, PNG, JPEG, ecc.) rifletterà la modifica.

**D:** *Posso combinare questa impostazione con font personalizzati?*  
**R:** Sì—carica i tuoi font personalizzati prima di inizializzare `Viewer`; la regola di raggruppamento rimarrà attiva.

**D:** *Disabilitare il raggruppamento influisce sulle prestazioni?*  
**R:** L’impatto è minimo; il motore elabora ogni carattere singolarmente, ma l’overhead tipico è inferiore al 5 % per la maggior parte dei documenti.

**D:** *È possibile attivare/disattivare il raggruppamento per pagina?*  
**R:** Attualmente l’opzione è globale per l’istanza `PdfOptions`; per comportamenti misti occorre creare istanze separate di `Viewer` per le pagine interessate.

## Risorse

- [Documentazione GroupDocs](https://docs.groupdocs.com/viewer/java/)
- [Riferimento API](https://reference.groupdocs.com/viewer/java/)
- [Scarica GroupDocs Viewer](https://releases.groupdocs.com/viewer/java/)
- [Acquista licenza](https://purchase.groupdocs.com/buy)
- [Versione di prova gratuita](https://releases.groupdocs.com/viewer/java/)
- [Applicazione licenza temporanea](https://purchase.groupdocs.com/temporary-license/)
- [Forum di supporto GroupDocs](https://forum.groupdocs.com/c/viewer/9)

---

**Last Updated:** 2026-09-05  
**Tested With:** GroupDocs.Viewer 25.2 for Java  
**Author:** GroupDocs

## Tutorial correlati

- [Come convertire pdf in html e ottimizzare la qualità delle immagini in Java con GroupDocs.Viewer](/viewer/java/advanced-rendering/adjust-image-quality-groupdocs-viewer-java/)
- [Render PDF a strati Java – Rendering efficiente di PDF a strati con GroupDocs.Viewer](/viewer/java/advanced-rendering/pdf-layered-rendering-java-groupdocs-viewer/)
- [Rendering HTML reattivo di GroupDocs Viewer Java](/viewer/java/advanced-rendering/groupdocs-viewer-java-responsive-html-rendering/)