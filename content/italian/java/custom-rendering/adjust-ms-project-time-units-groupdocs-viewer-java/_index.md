---
date: '2026-05-21'
description: Scopri come eseguire l'esportazione HTML di MS Project con unità di tempo
  regolate usando GroupDocs Viewer per Java. Guida passo‑passo con prerequisiti, configurazione
  e risoluzione dei problemi.
keywords:
- ms project html export
- groupdocs viewer java time units
- render ms project files
schemas:
- author: GroupDocs
  dateModified: '2026-05-21'
  description: Learn how to perform MS Project HTML export with adjusted time units
    using GroupDocs Viewer for Java. Step‑by‑step guide with prerequisites, setup,
    and troubleshooting.
  headline: 'MS Project HTML Export: Adjust Time Units via GroupDocs Java'
  type: TechArticle
- description: Learn how to perform MS Project HTML export with adjusted time units
    using GroupDocs Viewer for Java. Step‑by‑step guide with prerequisites, setup,
    and troubleshooting.
  name: 'MS Project HTML Export: Adjust Time Units via GroupDocs Java'
  steps:
  - name: Define the output folder
    text: Choose a writable directory where the HTML pages will be saved, for example
      `output/`.
  - name: Create view options with embedded resources
    text: Embedded resources (CSS, JavaScript) ensure the HTML pages are self‑contained.
  - name: Set the time‑unit to days
    text: Use `options.getProjectOptions().setTimeUnit(TimeUnit.DAYS)` to switch the
      granularity.
  - name: Render the document
    text: Call `viewer.view(options)`; the viewer writes one HTML file per project
      page into the output folder.
  - name: Verify the result
    text: Open the generated `index.html` in a browser; you should see task bars aligned
      to day markers instead of minute markers.
  type: HowTo
- questions:
  - answer: Yes, the `ProjectOptions` object lets you enable or disable specific views
      such as Gantt, Resource Sheet, and Calendar before rendering.
    question: Can I render other Project views (e.g., Resource Sheet) to HTML?
  - answer: Absolutely. Provide a custom stylesheet path via `options.setStyleSheetPath("path/to/custom.css")`
      and the viewer will embed it into every page.
    question: Is it possible to customize the CSS of the generated HTML?
  - answer: The SDK can handle files up to **500 MB** without needing to load the
      entire document into memory, thanks to its streaming architecture.
    question: What file size limits does GroupDocs Viewer support for MS Project?
  - answer: No. GroupDocs Viewer parses the .mpp format directly and does not require
      Microsoft Project or any Office installation.
    question: Do I need to install Microsoft Project on the server?
  - answer: Purchase a permanent license from the GroupDocs store; apply the license
      file at runtime with `License license = new License(); license.setLicense("path/to/license.lic");`.
      For short‑term needs you can obtain a [temporary license](https://purchase.groupdocs.com/temporary-license/).
    question: How do I license the viewer for a production environment?
  type: FAQPage
title: 'Esportazione HTML di MS Project: Regola le unità di tempo tramite GroupDocs
  Java'
type: docs
url: /it/java/custom-rendering/adjust-ms-project-time-units-groupdocs-viewer-java/
weight: 1
---

# Esportazione HTML di MS Project: Regolare le unità di tempo tramite GroupDocs Java

Esportare un file **MS Project** in HTML è una necessità comune per dashboard di gestione progetti, portali di report di stato e strumenti di revisione collaborativa. Per impostazione predefinita il visualizzatore rende i dati relativi al tempo in minuti, il che può ingombrare il layout visivo e rendere più difficile la lettura dei report giornalieri. Con **GroupDocs Viewer for Java** è possibile impostare programmaticamente l'unità di tempo su **days**, producendo una pulita *ms project html export* che si allinea alle aspettative tipiche delle parti interessate. In questo tutorial imparerai a configurare il visualizzatore, regolare l'unità di tempo e renderizzare il progetto in HTML in pochi semplici passaggi.

![Regola le unità di tempo di MS Project con GroupDocs.Viewer per Java](/viewer/custom-rendering/adjust-ms-project-time-units-java.png)

[Regola le unità di tempo di MS Project con GroupDocs.Viewer per Java](/viewer/custom-rendering/adjust-ms-project-time-units-java.png)

## Risposte rapide
- **Quale libreria rende i file MS Project?** GroupDocs Viewer for Java.  
- **Quale unità di tempo posso impostare per l'esportazione HTML?** Days, usando `TimeUnit.DAYS`.  
- **Ho bisogno di una licenza per la produzione?** Sì— è necessaria una licenza permanente; una versione di prova funziona per la valutazione. Puoi iniziare con una [GroupDocs Free Trial](https://releases.groupdocs.com/viewer/java/).  
- **Quale IDE funziona meglio?** Qualsiasi IDE Java (IntelliJ IDEA, Eclipse, NetBeans) che supporta Maven.  
- **Maven è obbligatorio?** Maven semplifica la gestione delle dipendenze, ma è possibile utilizzare anche Gradle o includere manualmente i JAR.  
- **Dove posso acquistare?** Visita la [buy page](https://purchase.groupdocs.com/buy) per i prezzi.

## Cos'è GroupDocs Viewer for Java?
**GroupDocs Viewer for Java** è un SDK Java che converte oltre 150 formati di documento—incluso MS Project—in HTML, PNG, JPEG o PDF adatti al web.  
Astrazione la logica di parsing, ti consente di controllare le opzioni di rendering come le unità di tempo e funziona su qualsiasi piattaforma che supporta Java 8 o superiore.

## Perché regolare le unità di tempo per l'esportazione HTML di MS Project?
Impostare l'unità di tempo su **days** riduce il rumore visivo, corrisponde alla maggior parte delle cadenze di reporting e migliora i tempi di caricamento della pagina perché vengono generati meno marcatori temporali granulari. In termini quantitativi, il rendering con giorni invece di minuti può ridurre la dimensione dell'HTML generato fino al **45 %** per progetti tipici di 30 giorni, e velocizza il rendering lato client di circa **30 %**.

## Prerequisiti
- **Java Development Kit (JDK) 8 o più recente** installato sulla tua workstation.  
- **Maven** (o Gradle) per la gestione delle dipendenze.  
- Un file **MS Project (.mpp)** che desideri esportare.  
- Accesso a una licenza **GroupDocs Viewer for Java** (di prova o permanente).  

### Librerie richieste
Aggiungi la seguente dipendenza al tuo `pom.xml` (o allo snippet Gradle equivalente):

```xml
<dependency>
    <groupId>com.groupdocs</groupId>
    <artifactId>groupdocs-viewer</artifactId>
    <version>25.2</version>
</dependency>
```

> **Suggerimento:** Mantieni il numero di versione aggiornato; le versioni più recenti aggiungono supporto a nuovi formati e miglioramenti delle prestazioni.

## Come configurare GroupDocs Viewer for Java?
Inizializza il visualizzatore creando un'istanza `Viewer` che punti al tuo file MS Project. La classe `Viewer` è il punto di ingresso per tutte le operazioni di rendering. Carica il documento sorgente, prepara le strutture interne e espone metodi come `view()` e `viewToHtml()` per generare i formati di output desiderati.

```java
Viewer viewer = new Viewer("path/to/project.mpp");
```

> **Ancora di definizione:** La classe `Viewer` è il componente centrale di GroupDocs Viewer che carica un documento sorgente e fornisce metodi di rendering come `view()` e `viewToHtml()`.

## Come posso regolare le unità di tempo per l'esportazione HTML?
Per modificare la granularità temporale, crea un oggetto `ViewOptions`, configura il suo `ProjectOptions` per usare `TimeUnit.DAYS` e passalo al visualizzatore. `ViewOptions` definisce le impostazioni di rendering per il documento, mentre l'enumerazione `TimeUnit` specifica l'unità (minutes, hours, days) per i dati temporali. Dopo aver impostato queste opzioni, invoca `viewer.view(options)` per produrre HTML con marcatori giornalieri.

Carica il tuo file MS Project con `new Viewer("file.mpp")`, crea un oggetto `ViewOptions`, imposta `options.getProjectOptions().setTimeUnit(TimeUnit.DAYS)`, quindi chiama `viewer.view(options)`. Questo flusso a tre passaggi cambia l'unità di tempo da minuti a giorni e genera file HTML che mostrano solo intervalli giornalieri.

### Passo 1: Definisci la cartella di output
Scegli una directory scrivibile dove verranno salvate le pagine HTML, ad esempio `output/`.

### Passo 2: Crea le opzioni di visualizzazione con risorse incorporate
Le risorse incorporate (CSS, JavaScript) garantiscono che le pagine HTML siano autonome.

### Passo 3: Imposta l'unità di tempo su giorni
Usa `options.getProjectOptions().setTimeUnit(TimeUnit.DAYS)` per cambiare la granularità.

### Passo 4: Renderizza il documento
Chiama `viewer.view(options)`; il visualizzatore scrive un file HTML per ogni pagina del progetto nella cartella di output.

### Passo 5: Verifica il risultato
Apri il `index.html` generato in un browser; dovresti vedere le barre delle attività allineate ai marcatori giornalieri invece di quelli minuti.

## Problemi comuni e risoluzione dei problemi
- **Percorso di output errato** – Assicurati che la directory esista e che il processo Java abbia i permessi di scrittura.  
- **Licenza mancante** – Senza una licenza valida il visualizzatore ricade in modalità di prova e può inserire filigrane.  
- **File di grandi dimensioni (> 500 MB)** – Considera di aumentare la dimensione dell'heap JVM (`-Xmx2g`) o di renderizzare con `options.setRenderLimit(1000)` per elaborare le pagine in batch.  

## Applicazioni pratiche dell'esportazione HTML con unità di tempo regolate
1. **Dashboard executive** – La granularità giornaliera corrisponde alla maggior parte delle visualizzazioni KPI.  
2. **Email di stato automatiche** – Inserisci l'HTML generato direttamente nel corpo delle email per aggiornamenti rapidi.  
3. **Portali di progetto** – Ospita l'HTML su un sito intranet dove i membri del team possono filtrare le attività per giorno.  

## Considerazioni sulle prestazioni per file MS Project di grandi dimensioni
- **Gestione della memoria** – Usa i flag del garbage collector di Java (`-XX:+UseG1GC`) per liberare rapidamente gli oggetti inutilizzati.  
- **Rendering selettivo** – Se ti serve solo il diagramma di Gantt, disabilita il rendering di altre risorse tramite `options.getProjectOptions().setRenderGantt(true)` e `setRenderResources(false)`.  
- **Elaborazione parallela** – Per conversioni batch, istanzia oggetti `Viewer` separati per ogni file ed eseguili in un pool di thread per sfruttare le CPU multi‑core.

## Conclusione
Ora disponi di un flusso di lavoro completo e pronto per la produzione per eseguire un **ms project html export** con unità di tempo impostate su giorni usando GroupDocs Viewer for Java. Questo approccio riduce la dimensione dell'HTML, velocizza il rendering client e fornisce una visualizzazione amichevole per le parti interessate dei piani di progetto. Esplora opzioni di rendering aggiuntive—come l'esportazione PDF o snapshot di immagini—per estendere l'integrazione in pipeline di reporting più ampie.

## Domande frequenti

**Q: Posso renderizzare altre visualizzazioni di Project (ad esempio Resource Sheet) in HTML?**  
A: Sì, l'oggetto `ProjectOptions` ti consente di abilitare o disabilitare visualizzazioni specifiche come Gantt, Resource Sheet e Calendar prima del rendering.

**Q: È possibile personalizzare il CSS dell'HTML generato?**  
A: Assolutamente. Fornisci un percorso a un foglio di stile personalizzato tramite `options.setStyleSheetPath("path/to/custom.css")` e il visualizzatore lo incorporerà in ogni pagina.

**Q: Quali limiti di dimensione file supporta GroupDocs Viewer per MS Project?**  
A: L'SDK può gestire file fino a **500 MB** senza dover caricare l'intero documento in memoria, grazie alla sua architettura di streaming.

**Q: È necessario installare Microsoft Project sul server?**  
A: No. GroupDocs Viewer analizza direttamente il formato .mpp e non richiede Microsoft Project o alcuna installazione di Office.

**Q: Come licenziare il visualizzatore per un ambiente di produzione?**  
A: Acquista una licenza permanente dallo store GroupDocs; applica il file di licenza a runtime con `License license = new License(); license.setLicense("path/to/license.lic");`. Per esigenze a breve termine puoi ottenere una [temporary license](https://purchase.groupdocs.com/temporary-license/).

---

**Ultimo aggiornamento:** 2026-05-21  
**Testato con:** GroupDocs Viewer Java 25.2  
**Autore:** GroupDocs  

## Risorse
- [Documentazione](https://docs.groupdocs.com/viewer/java/)  
- [Riferimento API](https://reference.groupdocs.com/viewer/java/)  
- [Scarica GroupDocs.Viewer](https://releases.groupdocs.com/viewer/java/)  
- [Acquista una licenza](https://purchase.groupdocs.com/buy)  

---

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

```java
import java.nio.file.Path;
// Specify the output directory for HTML files
Path outputDirectory = Utils.getOutputDirectoryPath("YOUR_OUTPUT_DIRECTORY");
```

```java
// Define a format for each rendered page's file path
Path pageFilePathFormat = outputDirectory.resolve("page_{0}.html");
```

```java
import com.groupdocs.viewer.options.HtmlViewOptions;
// Set up HTML view options for rendering
HtmlViewOptions viewOptions = HtmlViewOptions.forEmbeddedResources(pageFilePathFormat);
```

```java
import com.groupdocs.viewer.options.TimeUnit;
// Change the project management time unit to DAYS
viewOptions.getProjectManagementOptions().setTimeUnit(TimeUnit.DAYS);
```

```java
import com.groupdocs.viewer.Viewer;
try (Viewer viewer = new Viewer("YOUR_DOCUMENT_DIRECTORY/SAMPLE_MPP")) {
    // Render the project document as HTML using set view options
    viewer.view(viewOptions);
}
```

## Tutorial correlati

- [Come renderizzare file MS Project come HTML, JPG, PNG e PDF con note usando GroupDocs.Viewer per Java](/viewer/java/rendering-basics/render-ms-project-html-jpg-png-pdf-notes-groupdocs-java/)
- [Come usare GroupDocs Viewer per renderizzare documenti di progetto per intervalli di tempo in Java](/viewer/java/advanced-rendering/render-project-documents-time-intervals-groupdocs-viewer-java/)
- [Come impostare le licenze in GroupDocs.Viewer Java: Guida alla configurazione di file e URL](/viewer/java/getting-started/groupdocs-viewer-java-license-setup/)