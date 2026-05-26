---
date: '2026-02-23'
description: Scopri come convertire IGS in PDF, HTML, JPG e PNG con GroupDocs.Viewer
  per Java. Segui questa guida passo‑passo con esempi di codice pronti da eseguire.
keywords:
- GroupDocs.Viewer Java
- Convert IGS Files
- Render IGS Documents
title: Converti IGS in PDF, HTML, JPG e PNG usando GroupDocs.Viewer Java
type: docs
url: /it/java/file-formats-support/groupdocs-viewer-java-igs-rendering-html-jpg-png-pdf/
weight: 1
---

# Converti IGS in PDF, HTML, JPG e PNG usando GroupDocs.Viewer Java

Se hai bisogno di **convertire IGS in PDF** (o in HTML, JPG, PNG) direttamente da un'applicazione Java, sei nel posto giusto. In questo tutorial ti guideremo attraverso tutto ciò che ti serve — dall'installazione della libreria al rendering del modello 3‑D nel formato più adatto al tuo progetto. Vedrai perché GroupDocs.Viewer è una scelta solida per conversioni rapide e affidabili e otterrai del codice pratico da inserire nella tua soluzione.

![Converti file IGS in HTML, JPG, PNG e PDF con GroupDocs.Viewer per Java](/viewer/file-formats-support/convert-igs-files-to-html-jpg-png-and-pdf-java.png)

## Risposte rapide
- **Posso convertire IGS in PDF con Java?** Sì, usando `PdfViewOptions` di GroupDocs.Viewer.  
- **Quali formati di output sono supportati?** HTML, JPG, PNG e PDF.  
- **È necessaria una licenza per la produzione?** È richiesta una licenza commerciale; è disponibile una prova gratuita per i test.  
- **Quale versione di Java è richiesta?** JDK 8 o superiore.  
- **Maven è l'unico modo per aggiungere la libreria?** No, è possibile usare anche Gradle o includere manualmente il JAR.  

## Cos'è “convertire IGS in PDF”?
Convertire IGS (un formato di file neutro per dati CAD 3‑D) in PDF significa trasformare un modello 3‑D complesso in un documento statico, ampiamente visualizzabile. Questo è utile per condividere i progetti con le parti interessate che non dispongono di strumenti CAD.

## Perché usare GroupDocs.Viewer per le conversioni IGS?
- **Rendering CAD senza codice** – la libreria gestisce il lavoro pesante di parsing del formato IGS.  
- **Molteplici opzioni di output** – una chiamata API può produrre HTML, JPG, PNG o PDF.  
- **Cross‑platform** – funziona su qualsiasi OS che supporta Java.  
- **Focalizzata sulle prestazioni** – rendering veloce anche per grandi assiemi.  

## Prerequisiti
- **GroupDocs.Viewer per Java** ≥ 25.2  
- **JDK 8+** installato e configurato nel tuo IDE (IntelliJ IDEA, Eclipse, NetBeans, ecc.)  
- Conoscenza di base di Maven (opzionale ma consigliata)  

## Configurazione di GroupDocs.Viewer per Java

### Dipendenza Maven
Aggiungi il repository GroupDocs e la dipendenza Viewer al tuo `pom.xml`:

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
GroupDocs.Viewer offre:
- **Prova gratuita** – utilizzo limitato, ottimo per test rapidi.  
- **Licenza temporanea** – set completo di funzionalità per un breve periodo di valutazione.  
- **Licenza commerciale** – uso in produzione senza restrizioni.  

### Inizializzazione di base del Viewer
Il frammento di codice qui sotto mostra come creare un'istanza `Viewer` che punta al tuo file IGS:

```java
import com.groupdocs.viewer.Viewer;

public class ViewerSetup {
    public static void main(String[] args) {
        try (Viewer viewer = new Viewer("path/to/your/document.igs")) {
            // Configuration and rendering logic goes here.
        }
    }
}
```

## Rendering di IGS in HTML

### Come convertire IGS in HTML?
L'output HTML ti fornisce una visualizzazione interattiva e compatibile con il browser del modello 3‑D.

```java
import com.groupdocs.viewer.Viewer;
import com.groupdocs.viewer.options.HtmlViewOptions;
import java.nio.file.Path;
import static java.nio.file.Paths.get;

public class RenderIgsToHtml {
    public static void run() {
        Path outputDirectory = get("YOUR_OUTPUT_DIRECTORY");
        Path pageFilePathFormat = outputDirectory.resolve("IGS_result.html");

        try (Viewer viewer = new Viewer(get("YOUR_DOCUMENT_DIRECTORY/SAMPLE_IGS"))) {
            HtmlViewOptions options = HtmlViewOptions.forEmbeddedResources(pageFilePathFormat);
            viewer.view(options);
        }
    }
}
```

**Punto chiave:** `HtmlViewOptions.forEmbeddedResources()` incorpora tutte le risorse necessarie (CSS, immagini) direttamente nel file HTML, rendendolo portabile.

## Rendering di IGS in JPG

### Come convertire IGS in JPG?
Le immagini JPG sono perfette per miniature o anteprime rapide.

```java
import com.groupdocs.viewer.Viewer;
import com.groupdocs.viewer.options.JpgViewOptions;
import java.nio.file.Path;
import static java.nio.file.Paths.get;

public class RenderIgsToJpg {
    public static void run() {
        Path outputDirectory = get("YOUR_OUTPUT_DIRECTORY");
        Path pageFilePathFormat = outputDirectory.resolve("IGS_result.jpg");

        try (Viewer viewer = new Viewer(get("YOUR_DOCUMENT_DIRECTORY/SAMPLE_IGS"))) {
            JpgViewOptions options = new JpgViewOptions(pageFilePathFormat);
            viewer.view(options);
        }
    }
}
```

Puoi modificare `JpgViewOptions` per controllare la risoluzione e la qualità della compressione.

## Rendering di IGS in PNG

### Come convertire IGS in PNG?
PNG supporta la trasparenza, utile per sovrapporre il modello su diversi sfondi.

```java
import com.groupdocs.viewer.Viewer;
import com.groupdocs.viewer.options.PngViewOptions;
import java.nio file.Path;
import static java.nio.file.Paths.get;

public class RenderIgsToPng {
    public static void run() {
        Path outputDirectory = get("YOUR_OUTPUT_DIRECTORY");
        Path pageFilePathFormat = outputDirectory.resolve("IGS_result.png");

        try (Viewer viewer = new Viewer(get("YOUR_DOCUMENT_DIRECTORY/SAMPLE_IGS"))) {
            PngViewOptions options = new PngViewOptions(pageFilePathFormat);
            viewer.view(options);
        }
    }
}
```

Sperimenta con `PngViewOptions` per ottenere il miglior equilibrio tra dimensione del file e fedeltà visiva.

## Rendering di IGS in PDF

### Come convertire IGS in PDF?
PDF è il formato di riferimento per condividere documentazione di design dettagliata. Questa sezione affronta direttamente la parola chiave principale **convertire IGS in PDF**.

```java
import com.groupdocs.viewer.Viewer;
import com.groupdocs.viewer.options.PdfViewOptions;
import java.nio.file.Path;
import static java.nio.file.Paths.get;

public class RenderIgsToPdf {
    public static void run() {
        Path outputDirectory = get("YOUR_OUTPUT_DIRECTORY");
        Path pageFilePathFormat = outputDirectory.resolve("IGS_result.pdf");

        try (Viewer viewer = new Viewer(get("YOUR_DOCUMENT_DIRECTORY/SAMPLE_IGS"))) {
            PdfViewOptions options = new PdfViewOptions(pageFilePathFormat);
            viewer.view(options);
        }
    }
}
```

`PdfViewOptions` ti consente di controllare il layout della pagina, la qualità dell'immagine e se incorporare i font.

## Applicazioni pratiche
- **Portali web** – incorpora modelli renderizzati in HTML direttamente nei configuratori di prodotto.  
- **Materiale di marketing** – genera immagini JPG/PNG ad alta risoluzione per brochure.  
- **Documentazione tecnica** – includi rendering PDF di modelli CAD nei manuali utente.  
- **Assicurazione qualità** – automatizza la generazione di miniature per grandi lotti di file IGS.  

## Problemi comuni e soluzioni

| Problema | Soluzione |
|----------|-----------|
| **Cartella di output non trovata** | Verifica il percorso passato a `Path outputDirectory` e assicurati che il processo Java abbia permessi di scrittura. |
| **Pagine vuote nel PDF** | Assicurati che il file IGS non sia corrotto; prova ad aprirlo prima in un visualizzatore CAD. |
| **Rendering lento per grandi assiemi** | Aumenta l'heap JVM (`-Xmx2g` o più) e considera il rendering pagina per pagina usando `viewer.getPageCount()` se necessario. |
| **Font mancanti nel PDF** | Usa `PdfViewOptions` per incorporare i font richiesti o installa i font mancanti sul server. |

## Domande frequenti

**D: Posso convertire più file IGS in un'unica esecuzione?**  
R: Sì. Scorri una lista di percorsi file e invoca il metodo `view` appropriato per ciascuno.

**D: È possibile personalizzare la dimensione della pagina PDF?**  
R: Assolutamente. `PdfViewOptions` fornisce `setPageSize(PageSize.A4)` e metodi simili.

**D: È necessaria una licenza separata per ogni formato di output?**  
R: No. Una singola licenza GroupDocs.Viewer copre tutti i formati supportati.

**D: Quanto grande può essere un file IGS prima che le prestazioni peggiorino?**  
R: La libreria gestisce file fino a diverse centinaia di megabyte, ma potresti dover allocare più memoria JVM per modelli molto grandi.

**D: Posso renderizzare solo una vista o orientamento specifico?**  
R: GroupDocs.Viewer renderizza la vista predefinita. Per orientamenti personalizzati, preprocessa il file IGS con uno strumento CAD prima della conversione.

---

**Ultimo aggiornamento:** 2026-02-23  
**Testato con:** GroupDocs.Viewer 25.2 per Java  
**Autore:** GroupDocs