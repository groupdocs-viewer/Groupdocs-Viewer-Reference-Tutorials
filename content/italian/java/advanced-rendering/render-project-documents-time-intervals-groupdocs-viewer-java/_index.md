---
date: '2026-09-25'
description: Scopri come creare una visualizzazione HTML di file mpp con GroupDocs
  Viewer per Java, rendendo i documenti di progetto per intervalli di tempo con codice
  passo‑passo.
keywords:
- create html view mpp
- set start end date
- GroupDocs Viewer Java
- render project documents
lastmod: '2026-09-25'
og_description: Crea visualizzazione HTML di file mpp con GroupDocs Viewer per Java
  per rendere i file Microsoft Project per intervalli di tempo specifici. Segui la
  configurazione passo‑passo, la licenza e gli snippet di codice per una visualizzazione
  precisa della timeline.
og_image_alt: 'GroupDocs Viewer Java example: rendering project documents to HTML
  by time interval'
og_title: Crea visualizzazione HTML di file mpp con GroupDocs Viewer per Java
schemas:
- author: GroupDocs
  dateModified: '2026-09-25'
  description: Learn how to create html view mpp with GroupDocs Viewer for Java, rendering
    project documents by time intervals with step‑by‑step code.
  headline: Create html view mpp with GroupDocs Viewer (Java)
  type: TechArticle
- description: Learn how to create html view mpp with GroupDocs Viewer for Java, rendering
    project documents by time intervals with step‑by‑step code.
  name: Create html view mpp with GroupDocs Viewer (Java)
  steps:
  - name: '**Free trial** – Download a trial version from [GroupDocs'' download page](https://releases.groupdocs.com/viewer/java/).'
    text: '**Free trial** – Download a trial version from [GroupDocs'' download page](https://releases.groupdocs.com/viewer/java/).'
  - name: '**Temporary license** – Obtain a temporary license for extended testing
      via the [temporary‑license page](https://purchase.groupdocs.com/temporary-license/).'
    text: '**Temporary license** – Obtain a temporary license for extended testing
      via the [temporary‑license page](https://purchase.groupdocs.com/temporary-license/).'
  - name: '**Purchase** – For unrestricted production use, buy a license at the [GroupDocs
      Purchase Page](https://purchase.groupdocs.com/buy).'
    text: '**Purchase** – For unrestricted production use, buy a license at the [GroupDocs
      Purchase Page](https://purchase.groupdocs.com/buy).'
  - name: '**Project timeline analysis** – Show stakeholders only the current phase.'
    text: '**Project timeline analysis** – Show stakeholders only the current phase.'
  - name: '**Automated reporting** – Generate time‑bound HTML reports for weekly status
      updates.'
    text: '**Automated reporting** – Generate time‑bound HTML reports for weekly status
      updates.'
  - name: '**Integration with dashboards** – Embed the rendered pages into BI tools
      or custom portals.'
    text: '**Integration with dashboards** – Embed the rendered pages into BI tools
      or custom portals.'
  - name: '**Archival** – Store a web‑friendly snapshot of a project’s schedule for
      future reference.'
    text: '**Archival** – Store a web‑friendly snapshot of a project’s schedule for
      future reference.'
  type: HowTo
- questions:
  - answer: GroupDocs.Viewer supports 100+ input formats, including PDF, DOCX, XLSX,
      PPTX, and Microsoft Project files, enabling universal document visualization.
    question: What file formats does GroupDocs.Viewer support?
  - answer: You can download the trial version from the [GroupDocs Viewer Java download
      page](https://releases.groupdocs.com/viewer/java/).
    question: How do I get started with a free trial of GroupDocs.Viewer?
  - answer: Yes, you can choose a different HTML view option that references external
      resources instead of embedding them.
    question: Can I render documents without embedding resources?
  - answer: Consider splitting the document into smaller sections or rendering only
      the required date range, as demonstrated above.
    question: What if my document is too large for rendering?
  - answer: Verify all configuration settings, ensure you have a valid license, and
      consult the GroupDocs documentation for detailed error codes.
    question: How do I handle rendering errors?
  type: FAQPage
tags:
- render project documents
- GroupDocs Viewer
- Java rendering
- project timeline
- html view mpp
title: Crea visualizzazione HTML di file mpp con GroupDocs Viewer (Java)
type: docs
url: /it/java/advanced-rendering/render-project-documents-time-intervals-groupdocs-viewer-java/
weight: 1
---

# Come usare GroupDocs Viewer per rendere i documenti di progetto per intervalli di tempo in Java

In questo tutorial imparerai come **create html view mpp** con GroupDocs Viewer per Java, consentendo di rendere solo le parti di un file Microsoft Project che rientrano in un intervallo di data di inizio e data di fine specifico. Passeremo in rassegna la configurazione di Maven, la licenza e le chiamate API esatte necessarie per incorporare visualizzazioni di timeline precise direttamente nelle tue applicazioni.

![Renderizzare documenti di progetto per intervalli di tempo con GroupDocs.Viewer per Java](/viewer/advanced-rendering/render-project-documents-by-time-intervals-java.png)

Per un'anteprima, vedi il [Renderizzare documenti di progetto per intervalli di tempo con GroupDocs.Viewer per Java](/viewer/advanced-rendering/render-project-documents-by-time-intervals-java.png).

## Risposte rapide
- **Che cosa fa la funzionalità?** Renderizza solo la parte di un file Microsoft Project che rientra tra una data di inizio e una data di fine.  
- **Quale formato di output viene utilizzato?** HTML con risorse incorporate, perfetto per l'integrazione web.  
- **È necessaria una licenza?** Una versione di prova gratuita è sufficiente per la valutazione; è necessaria una licenza completa per la produzione.  
- **Posso modificare l'intervallo di date a runtime?** Sì—regola i valori `setStartDate` e `setEndDate` nelle opzioni di rendering.  
- **È supportato su tutte le versioni di Java?** Funziona con Java 8+ purché si utilizzi GroupDocs.Viewer 25.2 o versioni successive.

## Che cos'è create html view mpp?
`create html view mpp` è il processo di conversione di un file Microsoft Project (`.mpp` o `.mpt`) in un insieme di pagine HTML che rappresentano il programma. GroupDocs Viewer esegue la conversione sul lato server, così puoi visualizzare la timeline in qualsiasi browser senza installare Microsoft Project.

## Perché rendere i documenti di progetto con intervalli di tempo?
Renderizzare solo l'intervallo di tempo richiesto riduce le dimensioni dell'HTML generato, velocizza il caricamento della pagina e consente di concentrarsi sulla fase specifica del progetto da analizzare. Questa visualizzazione mirata è ideale per dashboard, report di stato o per l'integrazione in strumenti PM personalizzati dove i dati di progetto completi sarebbero opprimenti.

## Prerequisiti

- **GroupDocs.Viewer for Java** versione 25.2 o superiore.  
- Java Development Kit (JDK) 8 o più recente.  
- Un IDE come IntelliJ IDEA o Eclipse.  
- Conoscenza di base di Maven.  

## Configurazione di GroupDocs.Viewer per Java

### Dipendenza Maven

Add the repository and dependency to your `pom.xml`:

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

### Passaggi per l'acquisizione della licenza

1. **Prova gratuita** – Scarica una versione di prova dalla [pagina di download di GroupDocs](https://releases.groupdocs.com/viewer/java/).  
2. **Licenza temporanea** – Ottieni una licenza temporanea per test estesi tramite la [pagina di licenza temporanea](https://purchase.groupdocs.com/temporary-license/).  
3. **Acquisto** – Per un uso di produzione senza restrizioni, acquista una licenza nella [pagina di acquisto di GroupDocs](https://purchase.groupdocs.com/buy).

## Inizializzazione di base del viewer

`Viewer` è la classe principale di GroupDocs.Viewer per Java che carica un documento e fornisce capacità di rendering.

```java
import com.groupdocs.viewer.Viewer;

public class ViewerSetup {
    public static void main(String[] args) {
        try (Viewer viewer = new Viewer("path/to/your/document.mpp")) {
            // Your rendering code goes here
        }
    }
}
```

## Recuperare le informazioni di visualizzazione per i file di progetto

`ProjectManagementViewInfo` fornisce metadati su un file Microsoft Project, inclusi le date di inizio e fine del programma complessivo.

```java
import com.groupdocs.viewer.options.ViewInfoOptions;
import com.groupdocs.viewer.results.ProjectManagementViewInfo;

ViewInfoOptions viewInfoOptions = ViewInfoOptions.forHtmlView();
ProjectManagementViewInfo viewInfo = (ProjectManagementViewInfo) viewer.getViewInfo(viewInfoOptions);
```

## Configurare le opzioni di rendering HTML (generare HTML dal progetto)

`HtmlViewOptions` configura come GroupDocs rende l'HTML, consentendo di impostare l'intervallo di date, incorporare risorse e personalizzare l'aspetto.

```java
import com.groupdocs.viewer.options.HtmlViewOptions;

HtmlViewOptions viewOptions = HtmlViewOptions.forEmbeddedResources(pageFilePathFormat);
viewOptions.getProjectManagementOptions().setStartDate(viewInfo.getStartDate());
viewOptions.getProjectManagementOptions().setEndDate(viewInfo.getEndDate());
```

## Eseguire il processo di rendering

`viewer.render` esegue la conversione in base alle opzioni fornite e scrive i file HTML risultanti nella cartella di destinazione.

```java
viewer.view(viewOptions);
```

## Problemi comuni e risoluzione

- **Percorsi file errati** – Verifica che sia il file `.mpp` di origine sia la directory di output esistano.  
- **Tipo di file non supportato** – Assicurati che il documento sia in un formato Project supportato (ad es., `.mpp`, `.mpt`).  
- **Errori di licenza** – Una licenza di prova può imporre limiti di rendering; passa a una licenza completa per un uso senza restrizioni.  

## Applicazioni pratiche

1. **Analisi della timeline del progetto** – Mostra agli stakeholder solo la fase corrente.  
2. **Reportistica automatizzata** – Genera report HTML limitati nel tempo per aggiornamenti di stato settimanali.  
3. **Integrazione con dashboard** – Integra le pagine renderizzate in strumenti BI o portali personalizzati.  
4. **Archiviazione** – Conserva uno snapshot web‑friendly del programma di un progetto per riferimento futuro.  

## Suggerimenti sulle prestazioni

- Usa l'opzione *embedded resources* per mantenere ogni pagina HTML autonoma, riducendo le richieste HTTP.  
- Per progetti molto grandi, considera di renderizzare in blocchi di date più piccoli per mantenere basso l'uso della memoria. Renderizzare una porzione di un anno può ridurre le dimensioni dell'HTML fino all'80 % rispetto a un'esportazione dell'intero progetto, riducendo il tempo di caricamento da diversi secondi a meno di un secondo su server tipici.  
- Pulisci i file temporanei dopo averli serviti per evitare l'ingrossamento del disco.  

## Conclusione

Ora sai **come usare GroupDocs** Viewer per renderizzare documenti di progetto entro un intervallo di tempo specifico e **generare HTML dai dati del progetto** in Java. Questa funzionalità semplifica le visualizzazioni delle timeline, migliora l'efficienza della reportistica e si integra senza problemi con le moderne applicazioni web.

### Prossimi passi
- Esplora funzionalità aggiuntive del Viewer come watermark, protezione con password o styling CSS personalizzato.  
- Combina questa pipeline di rendering con un'API REST per servire visualizzazioni di timeline su richiesta.  

## Domande frequenti

**Q: Quali formati di file supporta GroupDocs.Viewer?**  
A: GroupDocs.Viewer supporta oltre 100 formati di input, inclusi PDF, DOCX, XLSX, PPTX e file Microsoft Project, consentendo una visualizzazione universale dei documenti.

**Q: Come posso iniziare con una prova gratuita di GroupDocs.Viewer?**  
A: Puoi scaricare la versione di prova dalla [pagina di download di GroupDocs Viewer Java](https://releases.groupdocs.com/viewer/java/).

**Q: Posso renderizzare documenti senza incorporare risorse?**  
A: Sì, puoi scegliere un'opzione di visualizzazione HTML diversa che fa riferimento a risorse esterne invece di incorporarle.

**Q: Cosa succede se il mio documento è troppo grande per il rendering?**  
A: Considera di suddividere il documento in sezioni più piccole o di renderizzare solo l'intervallo di date richiesto, come mostrato sopra.

**Q: Come gestisco gli errori di rendering?**  
A: Verifica tutte le impostazioni di configurazione, assicurati di avere una licenza valida e consulta la documentazione di GroupDocs per i codici di errore dettagliati.

## Risorse
- **Documentazione**: [Documentazione GroupDocs Viewer Java](https://docs.groupdocs.com/viewer/java/)  
- **Riferimento API**: [Riferimento API GroupDocs](https://reference.groupdocs.com/viewer/java/)  
- **Download**: [Download GroupDocs](https://releases.groupdocs.com/viewer/java/)  
- **Acquisto**: [Acquista licenza GroupDocs](https://purchase.groupdocs.com/buy)  
- **Prova gratuita**: [Prova la versione gratuita](https://releases.groupdocs.com/viewer/java/)  
- **Licenza temporanea**: [Ottieni una licenza temporanea](https://purchase.groupdocs.com/temporary-license/)  
- **Supporto**: [Forum GroupDocs](https://forum.groupdocs.com/c/viewer/9)  

---

**Last Updated:** 2026-09-25  
**Tested With:** GroupDocs.Viewer 25.2 for Java  
**Author:** GroupDocs  

```java
import java.nio.file.Path;

Path outputDirectory = Path.of("YOUR_OUTPUT_DIRECTORY", "RenderProjectTimeInterval");
Path pageFilePathFormat = outputDirectory.resolve("page_{0}.html");
```

```java
try (Viewer viewer = new Viewer("YOUR_DOCUMENT_DIRECTORY/SAMPLE_MPP")) {
    // Continue with rendering steps
}
```

## Tutorial correlati

- [Come renderizzare file MS Project come HTML, JPG, PNG e PDF con note usando GroupDocs.Viewer per Java](/viewer/java/rendering-basics/render-ms-project-html-jpg-png-pdf-notes-groupdocs-java/)  
- [Esportazione HTML di MS Project: Regola le unità di tempo tramite GroupDocs Java](/viewer/java/custom-rendering/adjust-ms-project-time-units-groupdocs-viewer-java/)  
- [GroupDocs Viewer Java Rendering HTML Responsivo](/viewer/java/advanced-rendering/groupdocs-viewer-java-responsive-html-rendering/)