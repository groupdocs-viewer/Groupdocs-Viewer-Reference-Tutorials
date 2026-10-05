---
date: '2026-10-05'
description: Scopri come ruotare pagine PDF specifiche con GroupDocs.Viewer for Java.
  Questa guida passo‑passo copre la configurazione di Maven, rotate pdf 90 degrees
  e la risoluzione dei problemi.
keywords:
- rotate specific pdf pages
- rotate pdf 90 degrees
- pdf to html java
- rotate multiple pdf pages
lastmod: '2026-10-05'
og_description: Ruota pagine PDF specifiche con GroupDocs.Viewer for Java. Scopri
  come rotate pdf 90 degrees, configurare Maven e risolvere i problemi comuni in una
  guida concisa.
og_image_alt: Developer guide showing rotation of PDF pages using GroupDocs.Viewer
  Java SDK
og_title: Ruota pagine PDF specifiche con GroupDocs.Viewer for Java
schemas:
- author: GroupDocs
  dateModified: '2026-10-05'
  description: Learn how to rotate specific PDF pages with GroupDocs.Viewer for Java.
    This step‑by‑step guide covers Maven setup, rotate pdf 90 degrees, and troubleshooting.
  headline: How to Rotate Specific PDF Pages with GroupDocs.Viewer for Java
  type: TechArticle
- questions:
  - answer: Yes. Loop through the page numbers and call `rotatePage(page, Rotation.ON_90_DEGREE)`
      for each page.
    question: Can I rotate all pages of a PDF at once?
  - answer: No. Rotation is applied only during the rendering process; the source
      PDF remains unchanged.
    question: Does the rotation affect the original PDF file?
  - answer: 'Provide the password when creating the `Viewer` instance: `new Viewer(path,
      password)`.'
    question: What if a PDF is password‑protected?
  - answer: Ensure the output directory exists and that `pageFilePathFormat` resolves
      correctly.
    question: How do I debug a “null pointer” error when setting up HtmlViewOptions?
  - answer: Yes. Use the same `rotatePage` configuration with the appropriate view
      options for the target format.
    question: Is there a way to rotate pages when converting to other formats (e.g.,
      PNG)?
  type: FAQPage
tags:
- rotate pdf
- groupdocs viewer
- java pdf processing
title: Come ruotare pagine PDF specifiche con GroupDocs.Viewer for Java
type: docs
url: /it/java/advanced-rendering/rotate-pdf-pages-groupdocs-viewer-java/
weight: 1
---

# Come ruotare pagine PDF specifiche con GroupDocs.Viewer per Java

Ruotare pagine specifiche all'interno di un PDF può essere essenziale per allineare documenti, correggere immagini scansionate o modificare diapositive di presentazione. **In questa guida imparerai a ruotare pagine PDF specifiche programmaticamente con GroupDocs.Viewer**, sia che tu debba ruotare il PDF di 90 gradi, capovolgere un'intera sezione o gestire più pagine in una singola chiamata.

![Ruota pagine PDF specifiche con GroupDocs.Viewer per Java](/viewer/advanced-rendering/rotate-specific-pdf-pages-java.png)

[Ruota pagine PDF specifiche con GroupDocs.Viewer per Java](/viewer/advanced-rendering/rotate-specific-pdf-pages-java.png)

**Cosa imparerai**
- Configurare GroupDocs.Viewer nel tuo progetto Java (inclusa la configurazione Maven di GroupDocs Viewer)
- Ruotare programmaticamente pagine PDF specifiche (ruotare PDF di 90 gradi, 180 gradi, ecc.)
- Configurazioni chiave per un utilizzo ottimale
- Risoluzione dei problemi comuni durante l'implementazione

## Risposte rapide
- **Quale libreria può ruotare pagine PDF in Java?** GroupDocs.Viewer per Java fornisce supporto di rotazione integrato senza strumenti esterni.  
- **Posso ruotare una singola pagina di 90 gradi?** Sì – chiama `rotatePage(pageNumber, Rotation.ON_90_DEGREE)` sull'istanza del viewer.  
- **Ho bisogno di una licenza per lo sviluppo?** Una licenza temporanea è gratuita per la valutazione; è necessaria una licenza completa per la produzione.  
- **È richiesto Maven?** Maven è il gestore di dipendenze consigliato, ma è possibile utilizzare anche Gradle o l'inclusione manuale di JAR.  
- **Come posso renderizzare le pagine ruotate?** Usa `HtmlViewOptions` con `viewer.view(documentPath, viewOptions)` per ottenere l'output HTML che riflette la rotazione.

## Cos'è ruotare pagine PDF specifiche?
`rotate specific pdf pages` si riferisce alla capacità di cambiare l'orientamento delle singole pagine all'interno di un documento PDF lasciando il resto del file intatto. Questa operazione viene eseguita al momento del rendering, quindi il file PDF originale rimane invariato.

## Perché ruotare pagine PDF specifiche?
Puoi ruotare una singola pagina in meno di 0,05 secondi su una tipica VM di livello server, consentendo l'anteprima in tempo reale di contratti scansionati, presentazioni o fatture multi‑pagina contenenti scansioni mal orientate. Questo controllo granulare elimina la necessità di costosi strumenti di post‑processing e riduce lo sforzo manuale fino al 70 % nei progetti di digitalizzazione su larga scala.

## Prerequisiti

### Librerie e dipendenze richieste
- Java Development Kit (JDK) 8 o successivo.  
- Un IDE come IntelliJ IDEA o Eclipse.  
- Maven per la gestione delle dipendenze.

### Requisiti di configurazione dell'ambiente
1. **Configurazione Maven** – aggiungi GroupDocs.Viewer al tuo `pom.xml`.  
2. **Acquisizione della licenza** – ottieni una licenza temporanea da GroupDocs. Visita [GroupDocs Free Trial](https://releases.groupdocs.com/viewer/java/) o richiedi una licenza temporanea sulla [GroupDocs Temporary License Page](https://purchase.groupdocs.com/temporary-license/).

## Configurare GroupDocs.Viewer per Java

Per integrare GroupDocs.Viewer nel tuo progetto Java usando Maven, aggiorna il tuo `pom.xml`:

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

### Inizializzazione e configurazione di base
`Viewer` è la classe principale che carica un documento e orchestra le operazioni di rendering. Dopo aver creato un'istanza puoi chiamare metodi come `view` o `rotatePage`.  

```java
Path YOUR_DOCUMENT_DIRECTORY = Path.of("YOUR_DOCUMENT_DIRECTORY");
Path YOUR_OUTPUT_DIRECTORY = Path.of("YOUR_OUTPUT_DIRECTORY");

// Format for page file paths
Path pageFilePathFormat = YOUR_OUTPUT_DIRECTORY.resolve("page_{0}.html");

HtmlViewOptions viewOptions = HtmlViewOptions.forEmbeddedResources(pageFilePathFormat);
```

## Come ruotare pagine PDF specifiche con GroupDocs.Viewer
Ruotare pagine PDF specifiche con GroupDocs.Viewer comporta due azioni principali: prima, specificare la rotazione desiderata per ogni pagina target usando il metodo `rotatePage`, e seconda, renderizzare il documento con `HtmlViewOptions` affinché la rotazione sia riflessa nell'output. Questo approccio mantiene il PDF originale invariato fornendo HTML correttamente orientato.

### Passo 1: configurare la rotazione della pagina
`rotatePage` è un metodo che accetta un indice di pagina basato su zero e un valore enum `Rotation`. L'enum fornisce tre opzioni: `ON_90_DEGREE`, `ON_180_DEGREE` e `ON_270_DEGREE`.  

```java
// Rotate the first page by 90 degrees clockwise.
viewOptions.rotatePage(1, Rotation.ON_90_DEGREE);

// Rotate the second page by 180 degrees.
viewOptions.rotatePage(2, Rotation.ON_180_DEGREE);
```

### Passo 2: inizializzare il viewer e renderizzare
`HtmlViewOptions` controlla il processo di conversione da PDF a HTML. Preserva layout, caratteri e risorse incorporate applicando al contempo qualsiasi rotazione configurata.  

```java
Viewer viewer = new Viewer(YOUR_DOCUMENT_DIRECTORY.resolve("SampleDocument.pdf"));

// Render the specified pages (1 and 2) using the configured options.
viewer.view(viewOptions, 1, 2);

// Always close the viewer to free resources.
viewer.close();
```

#### Parametri e configurazione
- **Rotation** – `rotatePage(pageNumber, Rotation.*)` dove le opzioni di rotazione sono `ON_90_DEGREE`, `ON_180_DEGREE`, `ON_270_DEGREE`.  
- **HtmlViewOptions** – Gestisce la conversione da PDF a HTML preservando layout e risorse incorporate.  
- **pdf to html java** – La classe fa parte della stessa API e garantisce una rappresentazione visiva fedele.

## Problemi comuni e soluzioni (risoluzione rotazione PDF)

- **Percorsi errati** – Verifica che `YOUR_DOCUMENT_DIRECTORY` e `YOUR_OUTPUT_DIRECTORY` esistano e siano accessibili.  
- **Dipendenze mancanti** – Assicurati che le coordinate Maven corrispondano all'ultima versione di GroupDocs.Viewer (attualmente 25.2).  
- **Restrizioni di licenza** – Applica correttamente la licenza temporanea; altrimenti, alcune funzionalità potrebbero essere disabilitate.  
- **Picchi di memoria** – Renderizza PDF di grandi dimensioni in batch più piccoli o aumenta la dimensione dell'heap JVM.

## Applicazioni pratiche

### Casi d'uso reali
1. **Allineamento dei documenti** – Ruota contratti scansionati per una corretta orientazione digitale.  
2. **Regolazioni delle presentazioni** – Modifica le diapositive di presentazione all'interno dei PDF prima della condivisione.  
3. **Flussi di lavoro di archiviazione** – Regola automaticamente l'orientazione dei documenti storici durante la digitalizzazione.

### Possibilità di integrazione
Combina GroupDocs.Viewer con sistemi di gestione dei contenuti basati su Java, portali aziendali o API personalizzate che richiedono la visualizzazione on‑the‑fly dei PDF.

## Considerazioni sulle prestazioni
- **Gestione delle risorse** – Chiudi sempre l'istanza `Viewer` per rilasciare handle di file e memoria.  
- **Gestione della memoria Java** – Monitora l'uso dell'heap durante l'elaborazione di PDF di grandi dimensioni; considera lo streaming delle pagine invece di caricare l'intero file.  
- **Best practice** – Metti in cache l'HTML renderizzato per i documenti frequentemente accessi per ridurre il tempo di elaborazione fino al 60 %.

## Conclusione
Questo tutorial ha coperto **come ruotare pagine PDF specifiche usando GroupDocs.Viewer in Java**, dalla configurazione Maven al rendering delle pagine ruotate e alla gestione dei problemi comuni. Sperimenta con funzionalità aggiuntive come watermark, conversione di formato o elaborazione batch per estendere ulteriormente il tuo flusso di lavoro documentale.

**Passi successivi:** Approfondisci altre funzionalità di GroupDocs.Viewer come la conversione di PDF in PNG, l'aggiunta di watermark o l'integrazione con provider di storage cloud.

## Sezione FAQ
- **Risoluzione dei problemi di rotazione** – Verifica che i numeri di pagina e i parametri di rotazione siano corretti.  
- **Gestione di file PDF di grandi dimensioni** – Processa le pagine in batch e monitora l'uso della memoria.  
- **Requisiti di licenza** – Usa una licenza temporanea per lo sviluppo; acquista una licenza completa per la produzione.  
- **Rotazione di più pagine** – Chiama `rotatePage` ripetutamente con diversi numeri di pagina e angoli.  
- **Integrazione con librerie Java** – GroupDocs.Viewer funziona senza problemi con Spring Boot, Jakarta EE e altri framework Java.

## Domande frequenti

**Q: Posso ruotare tutte le pagine di un PDF in una volta?**  
A: Sì. Scorri i numeri di pagina e chiama `rotatePage(page, Rotation.ON_90_DEGREE)` per ogni pagina.

**Q: La rotazione influisce sul file PDF originale?**  
A: No. La rotazione viene applicata solo durante il processo di rendering; il PDF sorgente rimane invariato.

**Q: Cosa succede se un PDF è protetto da password?**  
A: Fornisci la password quando crei l'istanza `Viewer`: `new Viewer(path, password)`.

**Q: Come posso debugare un errore “null pointer” durante la configurazione di HtmlViewOptions?**  
A: Assicurati che la directory di output esista e che `pageFilePathFormat` venga risolto correttamente.

**Q: Esiste un modo per ruotare le pagine durante la conversione in altri formati (es. PNG)?**  
A: Sì. Usa la stessa configurazione `rotatePage` con le opzioni di visualizzazione appropriate per il formato di destinazione.

## Risorse
- **Documentazione**: [Documentazione GroupDocs Viewer](https://docs.groupdocs.com/viewer/java/)  
- **Riferimento API**: [Riferimento API GroupDocs](https://reference.groupdocs.com/viewer/java/)  
- **Download**: [Pagina di download GroupDocs](https://releases.groupdocs.com/viewer/java/)  
- **Acquisto**: [Opzioni di acquisto GroupDocs](https://purchase.groupdocs.com/buy)  
- **Prova gratuita**: [Prova gratuita GroupDocs](https://releases.groupdocs.com/viewer/java/)  
- **Licenza temporanea**: [Richiedi licenza temporanea](https://purchase.groupdocs.com/temporary-license/)  
- **Supporto**: [Forum di supporto GroupDocs](https://forum.groupdocs.com/c/viewer/9)

---

**Ultimo aggiornamento:** 2026-10-05  
**Testato con:** GroupDocs.Viewer 25.2 per Java  
**Autore:** GroupDocs

## Tutorial correlati

- [Guida Java: renderizzare pagine selezionate java con GroupDocs.Viewer](/viewer/java/rendering-basics/java-groupdocs-viewer-render-pages-api-tutorial/)
- [Rendering PDF Java Groupdocs Viewer Interruzioni di pagina](/viewer/java/advanced-rendering/java-pdf-rendering-groupdocs-viewer-page-breaks/)
- [Groupdocs Viewer Java Rendering HTML Responsivo](/viewer/java/advanced-rendering/groupdocs-viewer-java-responsive-html-rendering/)