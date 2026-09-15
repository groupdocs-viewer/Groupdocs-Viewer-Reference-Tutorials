---
date: '2026-09-15'
description: Scopri come convertire eml in html con un formato datetime personalizzato
  e offset del fuso orario usando GroupDocs.Viewer per Java—ideale per email archiving
  e support portals.
keywords:
- convert eml to html
- custom datetime format
- set timezone offset
- email rendering html
lastmod: '2026-09-15'
og_description: Converti eml in html con un formato datetime personalizzato e offset
  del fuso orario usando GroupDocs.Viewer per Java. Segui questa step‑by‑step guide
  per accurate email rendering.
og_image_alt: Screenshot of GroupDocs.Viewer rendering an email to HTML with custom
  datetime in Java
og_title: Converti eml in html con datetime personalizzato in java usando GroupDocs.Viewer
schemas:
- author: GroupDocs
  dateModified: '2026-09-15'
  description: Learn how to convert eml to html with a custom datetime format and
    timezone offset using GroupDocs.Viewer for Java—ideal for email archiving and
    support portals.
  headline: Convert eml to html with custom datetime in java using GroupDocs.Viewer
  type: TechArticle
- description: Learn how to convert eml to html with a custom datetime format and
    timezone offset using GroupDocs.Viewer for Java—ideal for email archiving and
    support portals.
  name: Convert eml to html with custom datetime in java using GroupDocs.Viewer
  steps:
  - name: set up output directory and file path
    text: Define where the generated HTML will be saved. *Explanation:* `Path.of()`
      creates a reference to the folder where the HTML will be saved. `resolve()`
      appends the file name.
  - name: initialize viewer with email file
    text: Instantiate the `Viewer` class for the target EML file. *Explanation:* The
      `Viewer` instance points to the EML file you want to convert.
  - name: configure HtmlViewOptions
    text: Create an `HtmlViewOptions` object that bundles images and other resources
      directly into the HTML output. *Explanation:* `forEmbeddedResources()` bundles
      images and other resources directly into the HTML output.
  - name: set custom datetime format *(custom datetime java)*
    text: '`setDateTimeFormat` sets the date‑time pattern used when rendering email
      timestamps. Define the pattern that will be used for all timestamps in the rendered
      HTML. *Explanation:* This pattern displays the month, day, year, hour, minute,
      AM/PM marker, and the timezone offset (`zzz`).'
  - name: set timezone offset *(timezone offset java)*
    text: '`setTimeZoneOffset` specifies the time‑zone that will be applied to all
      email timestamps. Adjust timestamps to the desired time zone. *Explanation:*
      Adjusts the rendered timestamps to the desired time zone. Replace `"GMT+1"`
      with any valid zone identifier.'
  - name: render document
    text: Execute the conversion and produce the final HTML file. *Explanation:* Executes
      the conversion, producing an HTML file with your custom date‑time settings.
  type: HowTo
- questions:
  - answer: Attachments are automatically embedded when you use `HtmlViewOptions.forEmbeddedResources()`.
      You can also extract them via the Viewer API if you need separate files.
    question: How do I handle eml files with attachments?
  - answer: Yes, after rendering you can edit the generated HTML file or inject CSS
      programmatically before saving.
    question: Can I change the HTML template or add custom CSS?
  - answer: Wrap the rendering logic in a loop and reuse the same `HtmlViewOptions`
      instance for each file.
    question: Is it possible to render multiple eml files in a batch?
  - answer: GroupDocs.Viewer also supports MSG, PST, and other email containers—simply
      change the file extension in the `Viewer` constructor.
    question: What if I need to support other email formats like msg?
  - answer: Licensing is per deployment; consult the GroupDocs licensing guide for
      multi‑server scenarios.
    question: Do I need a separate license for each server?
  type: FAQPage
tags:
- convert eml
- GroupDocs Viewer
- java email conversion
- email to html
- custom datetime
title: Converti eml in html con datetime personalizzato in java usando GroupDocs.Viewer
type: docs
url: /it/java/advanced-rendering/render-emails-custom-datetime-groupdocs-viewer-java/
weight: 1
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Convertire eml in html con data/ora personalizzata in java usando GroupDocs.Viewer

Nei moderni sistemi di supporto e archiviazione, **convertire eml in html** rapidamente mantenendo i timestamp esatti è una funzionalità indispensabile. Questo tutorial mostra come rendere un'email EML in HTML, applicare un **formato data/ora personalizzato** e impostare un **offset del fuso orario** usando GroupDocs.Viewer per Java. Alla fine avrai uno snippet riutilizzabile che produce visualizzazioni email accurate e pronte per il web per qualsiasi flusso di lavoro di **conversione email in html**.

![Render Emails with Custom DateTime with GroupDocs.Viewer for Java](/viewer/advanced-rendering/render-emails-with-custom-datetime-java.png)

## Risposte rapide
- **GroupDocs.Viewer può convertire EML in HTML?** Sì – l'API rende i file EML direttamente in HTML senza client di posta esterni.  
- **È necessaria una licenza per la produzione?** Una prova gratuita è sufficiente per i test; è richiesta una licenza a pagamento per le distribuzioni in produzione.  
- **Quale versione di Java è supportata?** Java 8 o versioni successive sono pienamente supportate.  
- **Come modifico il formato della data visualizzata?** Chiama `options.getEmailOptions().setDateTimeFormat("MMM dd, yyyy hh:mm a zzz")`.  
- **Posso regolare il fuso orario?** Sì, usa `options.getEmailOptions().setTimeZoneOffset(TimeZone.getTimeZone("GMT+1"))`.

## Cos'è “convert eml to html”?
`Convert eml to html` è il processo di trasformare un file email EML in un documento HTML per la visualizzazione nel browser. Convertire un file EML in HTML trasforma l'email grezza (incluse intestazioni, corpo e allegati) in un formato web‑friendly che i browser possono visualizzare senza plugin aggiuntivi. Questo semplifica l'inserimento delle email in applicazioni web, archivi o dashboard di supporto.

## Perché usare GroupDocs.Viewer per questo compito?
GroupDocs.Viewer supporta **oltre 50 formati di input e output**, inclusi EML, MSG, PST e PDF, e può rendere email di centinaia di pagine senza caricare l'intero file in memoria. Il suo motore a zero dipendenze elimina la necessità di Outlook o parser di terze parti, offrendoti pieno controllo sul **formato data/ora personalizzato** e sull'**offset del fuso orario** mantenendo un basso consumo di risorse.

## Prerequisiti
- GroupDocs.Viewer per Java ≥ 25.2  
- JDK 8+ e un IDE Java (IntelliJ IDEA, Eclipse, VS Code)  
- Maven per la gestione delle dipendenze  

## Configurazione di GroupDocs.Viewer per Java

### Configurazione Maven
Aggiungi il repository GroupDocs e la dipendenza Viewer al tuo file `pom.xml`.

```xml
<repositories>
    <repository>
        <id>groupdocs-releases</id>
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
Inizia con una prova gratuita o richiedi una licenza temporanea per test più estesi. Acquista una licenza completa per l'uso in produzione.

### Inizializzazione di base
Crea un'istanza `Viewer` che punti al file EML che desideri convertire.

```java
import com.groupdocs.viewer.Viewer;

// Initialize Viewer with the path to your document
try (Viewer viewer = new Viewer("path/to/your/document.eml")) {
    // Perform operations here
}
```

## Convertire eml in html con data/ora personalizzata in java

I passaggi seguenti ti guidano nella resa di un file EML in HTML applicando un formato data/ora personalizzato e un offset del fuso orario.

### Passo 1: impostare la directory di output e il percorso del file
Definisci dove verrà salvato l'HTML generato.

```java
import java.nio.file.Path;

Path outputDirectory = Path.of("YOUR_OUTPUT_DIRECTORY");
Path filePath = outputDirectory.resolve("output.html");
```
*Spiegazione:* `Path.of()` crea un riferimento alla cartella in cui verrà salvato l'HTML. `resolve()` aggiunge il nome del file.

### Passo 2: inizializzare il viewer con il file email
Istanzia la classe `Viewer` per il file EML di destinazione.

```java
import com.groupdocs.viewer.Viewer;

try (Viewer viewer = new Viewer("YOUR_DOCUMENT_DIRECTORY/SAMPLE_EML")) {
    // Further configuration goes here
}
```
*Spiegazione:* L'istanza `Viewer` punta al file EML che vuoi convertire.

### Passo 3: configurare HtmlViewOptions
Crea un oggetto `HtmlViewOptions` che incorpora immagini e altre risorse direttamente nell'output HTML.

```java
import com.groupdocs.viewer.options.HtmlViewOptions;

HtmlViewOptions options = HtmlViewOptions.forEmbeddedResources(filePath);
```
*Spiegazione:* `forEmbeddedResources()` incorpora immagini e altre risorse direttamente nell'output HTML.

### Passo 4: impostare il formato data/ora personalizzato *(datetime personalizzato java)*
`setDateTimeFormat` imposta il pattern data‑ora usato durante la resa dei timestamp delle email.  
Definisci il pattern che verrà usato per tutti i timestamp nell'HTML renderizzato.

```java
options.getEmailOptions().setDateTimeFormat("MM d yyyy HH:mm tt zzz");
```
*Spiegazione:* Questo pattern visualizza mese, giorno, anno, ora, minuti, indicatore AM/PM e l'offset del fuso orario (`zzz`).

### Passo 5: impostare l'offset del fuso orario *(offset fuso orario java)*
`setTimeZoneOffset` specifica il fuso orario da applicare a tutti i timestamp delle email.  
Regola i timestamp al fuso orario desiderato.

```java
import java.util.TimeZone;

options.getEmailOptions().setTimeZoneOffset(TimeZone.getTimeZone("GMT+1"));
```
*Spiegazione:* Regola i timestamp renderizzati al fuso orario desiderato. Sostituisci `"GMT+1"` con qualsiasi identificatore di zona valido.

### Come regolare il fuso orario dell'email in java
Se devi **regolare il fuso orario dell'email** oltre ai semplici offset — ad esempio gestendo il passaggio all'ora legale — puoi recuperare l'oggetto `TimeZone` appropriato dall'API `java.util.TimeZone` usando ID di regione come `"Europe/Paris"` o `"America/New_York"` e passarli a `setTimeZoneOffset`. Questo garantisce che i timestamp delle email riflettano sempre l'ora locale corretta.

### Passo 6: rendere il documento
Esegui la conversione e genera il file HTML finale.

```java
viewer.view(options);
```
*Spiegazione:* Esegue la conversione, producendo un file HTML con le impostazioni data‑ora personalizzate.

## Come influisce il formato data/ora personalizzato sull'HTML renderizzato?
Il formato data/ora personalizzato determina come appare ogni timestamp dell'email nell'HTML generato, influenzando leggibilità e conformità locale. Specificando un pattern come `"MMM dd, yyyy hh:mm a zzz"`, garantisci che ogni data sia visualizzata in modo coerente, includendo l'abbreviazione del mese, giorno, anno, ora, minuti, indicatore AM/PM e l'offset esplicito del fuso orario, elemento cruciale per i team di supporto globali.

## Quali formati di file supporta GroupDocs.Viewer per il rendering delle email?
GroupDocs.Viewer può rendere file **EML, MSG, PST, MBOX e EMLX** in HTML, PDF, PNG e JPEG. Supporta oltre 50 formati di documenti e immagini, consentendoti di convertire le email in qualsiasi output web‑friendly più comune senza convertitori aggiuntivi.

## Come posso convertire in batch più file eml?
Posiziona tutti i file EML in una singola directory, itera su ciascun file con una struttura `for` o `foreach`, riutilizza la stessa istanza `HtmlViewOptions` e chiama `viewer.view` per ogni file. Questo approccio riduce al minimo la creazione di oggetti e accelera le conversioni di massa.

## Suggerimenti per la risoluzione dei problemi
- **FileNotFoundException:** Verifica i percorsi usati in `Viewer` e `Path.of()`.  
- **Timestamp errati:** Assicurati che l'ID `TimeZone` corrisponda alla tua regione target.  
- **Immagini mancanti:** Conferma di aver usato `HtmlViewOptions.forEmbeddedResources()`; altrimenti le risorse esterne potrebbero essere omesse.  

## Applicazioni pratiche
1. **Archiviazione email:** Conserva snapshot HTML ricercabili delle email per audit di conformità.  
2. **Portali di supporto clienti:** Mostra i ticket in arrivo con orari locali accurati per agenti in tutto il mondo.  
3. **Documentazione legale:** Produci registri email pronti per il tribunale con timestamp standardizzati.  

## Considerazioni sulle prestazioni
- Distribuisci su un server dedicato per conversioni di massa.  
- Monitora l'uso dell'heap Java; aumenta `-Xmx` se incontri `OutOfMemoryError`.  
- Cache l'HTML renderizzato quando la stessa email viene richiesta più volte per ridurre il carico CPU.  

## Conclusione
Ora disponi di un metodo completo e pronto per la produzione per **convertire eml in html** con un formato data/ora personalizzato e un offset del fuso orario usando GroupDocs.Viewer per Java. Questa soluzione migliora la leggibilità, garantisce l'accuratezza dei timestamp e si integra perfettamente in flussi di lavoro di archiviazione, supporto o legali.

**Passi successivi:** Esplora ulteriori opzioni Viewer come l'iniezione di CSS personalizzato, la paginazione o la conversione in PDF per adattare ulteriormente l'output alle esigenze della tua applicazione.

## Domande frequenti

**D: Come gestisco i file eml con allegati?**  
R: Gli allegati vengono incorporati automaticamente quando usi `HtmlViewOptions.forEmbeddedResources()`. Puoi anche estrarli tramite l'API Viewer se ti servono file separati.

**D: Posso modificare il modello HTML o aggiungere CSS personalizzato?**  
R: Sì, dopo la resa puoi modificare il file HTML generato o iniettare CSS programmaticamente prima del salvataggio.

**D: È possibile rendere più file eml in batch?**  
R: Avvolgi la logica di rendering in un ciclo e riutilizza la stessa istanza `HtmlViewOptions` per ogni file.

**D: Cosa fare se devo supportare altri formati email come msg?**  
R: GroupDocs.Viewer supporta anche MSG, PST e altri contenitori email — basta cambiare l'estensione del file nel costruttore `Viewer`.

**D: È necessaria una licenza separata per ogni server?**  
R: La licenza è per distribuzione; consulta la guida di licenza GroupDocs per scenari multi‑server.

## Risorse

- [Documentazione](https://docs.groupdocs.com/viewer/java/)
- [Riferimento API](https://reference.groupdocs.com/viewer/java/)
- [Download](https://releases.groupdocs.com/viewer/java/)
- [Acquista](https://purchase.groupdocs.com/buy)
- [Prova gratuita](https://releases.groupdocs.com/viewer/java/)
- [Licenza temporanea](https://purchase.groupdocs.com/temporary-license/)
- [Forum di supporto](https://forum.groupdocs.com/c/viewer/9)

---

**Ultimo aggiornamento:** 2026-09-15  
**Testato con:** GroupDocs.Viewer 25.2 (Java)  
**Autore:** GroupDocs

## Tutorial correlati

- [Convert Email to HTML & Rename Fields – GroupDocs Viewer Java](/viewer/java/advanced-rendering/rename-email-fields-html-groupdocs-viewer-java/)
- [java convert msg to pdf – Optimize Email-to-PDF Rendering with GroupDocs.Viewer](/viewer/java/performance-optimization/optimize-email-pdf-rendering-java-groupdocs-viewer-api/)
- [Groupdocs Viewer Java Responsive Html Rendering](/viewer/java/advanced-rendering/groupdocs-viewer-java-responsive-html-rendering/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}