---
date: '2026-03-27'
description: Scopri come convertire Excel in HTML e visualizzare righe e colonne nascoste
  nei fogli di calcolo Java utilizzando GroupDocs.Viewer per una conversione HTML
  senza interruzioni. Garantisci la completa visibilità dei dati con questa guida
  avanzata di rendering.
keywords:
- convert excel to html
- xlsx to html java
- display hidden spreadsheet data
- GroupDocs Viewer Java
title: Come convertire Excel in HTML e visualizzare righe e colonne nascoste in Java
  con GroupDocs.Viewer
type: docs
url: /it/java/advanced-rendering/render-hidden-rows-columns-java-groupdocs-viewer/
weight: 1
---

# Convertire Excel in HTML e visualizzare righe e colonne nascoste nei fogli di calcolo Java con GroupDocs.Viewer

Stai avendo difficoltà a **convertire Excel in HTML** e visualizzare righe e colonne nascoste all'interno di un foglio di calcolo quando lo converti in HTML usando Java? Non sei solo! Molti sviluppatori affrontano questa sfida cercando di mantenere l'integrità della visualizzazione dei dati tra diversi formati. Questo tutorial ti guiderà su come rendere efficacemente visibili righe e colonne nascoste nei fogli di calcolo usando GroupDocs.Viewer per Java, garantendo che nessuna informazione cruciale venga persa durante la conversione.

![Renderizza righe e colonne nascoste con GroupDocs.Viewer per Java](/viewer/advanced-rendering/render-hidden-rows-and-columns-java.png)

## Risposte rapide
- **GroupDocs.Viewer può convertire Excel in HTML?** Sì, fornisce supporto out‑of‑the‑box per la conversione di file XLSX in HTML.  
- **Le righe e le colonne nascoste saranno visibili nell'output HTML?** Quando abiliti le opzioni corrette, i dati nascosti vengono renderizzati come le celle visibili.  
- **Quale artefatto Maven è necessario?** `com.groupdocs:groupdocs-viewer` (si consiglia l'ultima versione).  
- **È necessaria una licenza per l'uso in produzione?** È richiesta una licenza permanente per la produzione; è disponibile una versione di prova gratuita o una licenza temporanea per la valutazione.  
- **Questo approccio è compatibile con Java 8 e versioni successive?** Assolutamente – funziona con JDK 8+.

## Cos'è “convertire Excel in HTML”?
Convertire Excel in HTML significa trasformare una cartella di lavoro `.xlsx` in un insieme di pagine HTML pronte per il web, preservando il layout originale, gli stili e i dati. Questo ti consente di visualizzare i fogli di calcolo direttamente nei browser senza richiedere Microsoft Office.

## Perché visualizzare i dati nascosti del foglio di calcolo?
- **Reporting finanziario** richiede tracce di audit complete, incluse righe/colonne nascoste per scopi di presentazione.  
- **Strumenti di analisi dei dati** necessitano del set di dati completo per calcoli accurati.  
- **Risorse educative** richiedono che ogni cella sia visibile per insegnare formule e strutture dati.  

## Prerequisiti

### Librerie e dipendenze richieste
Per implementare questa funzionalità, assicurati di includere GroupDocs.Viewer per Java come dipendenza nel tuo progetto. Questa libreria è essenziale per il rendering dei documenti in vari formati come HTML, PDF e file immagine.

### Requisiti di configurazione dell'ambiente
- **Java Development Kit (JDK)**: Versione 8 o successiva  
- **Integrated Development Environment (IDE)**: Come IntelliJ IDEA o Eclipse  
- **Maven**: Per gestire le dipendenze del progetto  

### Prerequisiti di conoscenza
È necessaria una comprensione fondamentale della programmazione Java. Inoltre, familiarità con Maven sarà utile per configurare il tuo progetto.

## Configurazione di GroupDocs.Viewer per Java
Per iniziare a usare GroupDocs.Viewer nella tua applicazione Java, dovrai configurarlo tramite Maven. Ecco come:

**Maven**  
Aggiungi la seguente configurazione al tuo file `pom.xml`:
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
Per utilizzare GroupDocs.Viewer, considera le seguenti opzioni:
- **Prova gratuita**: Scarica una versione di prova per valutare le funzionalità.  
- **Licenza temporanea**: Richiedi una licenza temporanea per l'accesso completo alle funzionalità senza limitazioni di valutazione.  
- **Acquisto**: Ottieni una licenza permanente per l'uso in produzione.  

Dopo aver configurato Maven e ottenuto la licenza, puoi iniziare a inizializzare GroupDocs.Viewer. Ecco come fare:
```java
import com.groupdocs.viewer.Viewer;

public class ViewerInitialization {
    public static void main(String[] args) {
        // Initialize the viewer with your license file if available.
        try (Viewer viewer = new Viewer("path/to/your/document.xlsx")) {
            // Your code here...
        }
    }
}
```

## Come convertire Excel in HTML con dati nascosti
Questa sezione ti guida attraverso i passaggi esatti necessari per **convertire Excel in HTML** garantendo che righe e colonne nascoste siano visualizzate.

### Passo 1: Definire il percorso della directory di output
Inizia definendo dove verranno archiviati i file renderizzati:
```java
import java.nio.file.Path;
import java.nio.file.Paths;

Path outputDirectory = Paths.get("YOUR_OUTPUT_DIRECTORY", "RenderHiddenRowsAndColumns");
```

### Passo 2: Configurare HtmlViewOptions
Successivamente, imposta `HtmlViewOptions` per incorporare le risorse direttamente nei file HTML generati:
```java
import com.groupdocs.viewer.options.HtmlViewOptions;

// Create a file path format for rendering each page.
Path pageFilePathFormat = outputDirectory.resolve("page_{0}.html");

HtmlViewOptions viewOptions = HtmlViewOptions.forEmbeddedResources(pageFilePathFormat);
```

### Passo 3: Abilitare il rendering di colonne e righe nascoste
Configura `SpreadsheetOptions` per renderizzare gli elementi nascosti:
```java
// Enable rendering of hidden columns and rows.
viewOptions.getSpreadsheetOptions().setRenderHiddenColumns(true);
viewOptions.getSpreadsheetOptions().setRenderHiddenRows(true);
```

### Passo 4: Inizializzare Viewer con il documento e renderizzare
Infine, inizializza GroupDocs.Viewer con il percorso del tuo documento e renderizza il contenuto:
```java
import com.groupdocs.viewer.Viewer;

try (Viewer viewer = new Viewer("YOUR_DOCUMENT_DIRECTORY/SAMPLE_XLSX_WITH_HIDDEN_ROW_AND_COLUMN")) {
    // Render the document to HTML using the specified view options.
    viewer.view(viewOptions);
} catch (Exception e) {
    System.out.println("Error rendering document: " + e.getMessage());
}
```

**Suggerimenti per la risoluzione dei problemi**: Assicurati che i percorsi siano impostati correttamente e che le dipendenze siano incluse correttamente nel tuo `pom.xml`.

## Applicazioni pratiche
Ecco alcune applicazioni pratiche di questa funzionalità:
1. **Reporting finanziario**: Garantire che tutti i dati, incluse le metriche finanziarie nascoste, siano visibili durante la conversione per la conformità.  
2. **Analisi dei dati**: Mantenere l'integrità dei set di dati visualizzando tutte le righe e colonne nei report o nelle presentazioni.  
3. **Strumenti educativi**: Utilizzare il contenuto completo del foglio di calcolo a scopo didattico senza perdere le informazioni nascoste.  

## Considerazioni sulle prestazioni
Per ottimizzare le prestazioni quando si utilizza GroupDocs.Viewer:
- Monitorare l'uso della memoria, soprattutto con documenti di grandi dimensioni.  
- Ottimizzare i percorsi dei file e le posizioni di archiviazione per ridurre le operazioni I/O.  
- Aggiornare regolarmente la libreria per sfruttare nuovi miglioramenti delle prestazioni e correzioni di bug.  

## Conclusione
In questo tutorial, hai imparato come **convertire Excel in HTML** e configurare GroupDocs.Viewer per Java per renderizzare righe e colonne nascoste nei fogli di calcolo. Seguendo questi passaggi, puoi garantire una visibilità completa dei dati tra i formati. Come prossimo passo, sperimenta con diversi tipi di documento ed esplora le funzionalità aggiuntive offerte da GroupDocs.Viewer.

Pronto a approfondire? Prova a implementare questa funzionalità nei tuoi progetti e scopri come migliora la funzionalità della tua applicazione!

## Sezione FAQ

**Q1: Posso usare GroupDocs.Viewer gratuitamente?**  
A1: Sì, puoi scaricare una versione di prova dal sito ufficiale per esplorare le funzionalità. Per un accesso completo senza limitazioni, considera l'acquisizione di una licenza temporanea o permanente.

**Q2: Quali formati di file supporta GroupDocs.Viewer?**  
A2: Supporta oltre 50 diversi formati di documento, inclusi PDF, Word, Excel e immagini.

**Q3: Come gestisco documenti di grandi dimensioni con GroupDocs.Viewer?**  
A3: Ottimizza la gestione della memoria regolando le impostazioni Java e suddividendo i file di grandi dimensioni in parti più piccole, se necessario.

**Q4: È possibile personalizzare il formato dell'output HTML?**  
A4: Sì, puoi configurare varie opzioni usando `HtmlViewOptions` per adattare l'aspetto dei documenti renderizzati.

**Q5: Qual è il modo migliore per risolvere i problemi con GroupDocs.Viewer?**  
A5: Consulta la documentazione ufficiale e i forum per le soluzioni. Assicurati che tutte le dipendenze siano configurate correttamente nella configurazione del tuo progetto.

## Domande frequenti

**Q: L'attivazione di `setRenderHiddenColumns(true)` influisce sulle prestazioni?**  
A: Il rendering delle colonne nascoste aggiunge un piccolo overhead, ma l'impatto è minimo per i workbook tipici. Per fogli molto grandi, monitora l'uso della memoria.

**Q: Posso convertire un file XLSX in una singola pagina HTML invece di più pagine?**  
A: Sì, puoi impostare un nome file personalizzato in `HtmlViewOptions` senza il segnaposto `{0}` per generare un unico file HTML.

**Q: Come visualizzo i dati nascosti del foglio di calcolo solo per fogli di lavoro specifici?**  
A: Usa `viewOptions.getSpreadsheetOptions().setWorksheetIndexes(...)` per mirare a fogli particolari prima di abilitare il rendering dei dati nascosti.

**Q: Esiste un modo per nascondere la barra degli strumenti o la navigazione dopo la conversione?**  
A: L'output HTML generato da GroupDocs.Viewer è statico; puoi rimuovere manualmente gli elementi di navigazione se personalizzi il modello.

**Q: Quale versione di GroupDocs.Viewer è necessaria per il rendering di righe/colonne nascoste?**  
A: La funzionalità è disponibile a partire dalla versione 22.0; consigliamo di utilizzare l'ultima versione stabile.

## Risorse
- **Documentazione**: [Documentazione di GroupDocs Viewer](https://docs.groupdocs.com/viewer/java/)
- **Riferimento API**: [Riferimento API di GroupDocs](https://reference.groupdocs.com/viewer/java/)
- **Download**: [Scarica GroupDocs.Viewer](https://releases.groupdocs.com/viewer/java/)
- **Acquista**: [Acquista una licenza](https://purchase.groupdocs.com/buy)
- **Prova gratuita**: [Prova la versione gratuita](https://releases.groupdocs.com/viewer/java/)
- **Licenza temporanea**: [Richiedi licenza temporanea](https://purchase.groupdocs.com/temporary-license/)
- **Supporto**: [Forum GroupDocs](https://forum.groupdocs.com/c/viewer/9)

---

**Ultimo aggiornamento:** 2026-03-27  
**Testato con:** GroupDocs.Viewer 25.2 for Java  
**Autore:** GroupDocs