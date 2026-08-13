---
date: '2026-06-10'
description: Scopri come renderizzare DWG in JPG e convertire i file CAD in JPG usando
  GroupDocs.Viewer per Java in un tutorial passo-passo.
keywords:
- render dwg as jpg
- convert cad files to jpg
- java convert dwg to jpg
schemas:
- author: GroupDocs
  dateModified: '2026-06-10'
  description: Learn how to render DWG as JPG and convert CAD files to JPG using GroupDocs.Viewer
    for Java in a step-by-step tutorial.
  headline: Render DWG as JPG with GroupDocs.Viewer Java – Full Guide
  type: TechArticle
- description: Learn how to render DWG as JPG and convert CAD files to JPG using GroupDocs.Viewer
    for Java in a step-by-step tutorial.
  name: Render DWG as JPG with GroupDocs.Viewer Java – Full Guide
  steps:
  - name: '**Architectural Design** – Share building plans with clients who don’t
      have CAD software.'
    text: '**Architectural Design** – Share building plans with clients who don’t
      have CAD software.'
  - name: '**Engineering Projects** – Include detailed schematics in PowerPoint decks.'
    text: '**Engineering Projects** – Include detailed schematics in PowerPoint decks.'
  - name: '**Interior Design** – Quickly generate mood‑board images from floor‑plan
      DWG files.'
    text: '**Interior Design** – Quickly generate mood‑board images from floor‑plan
      DWG files.'
  type: HowTo
- questions:
  - answer: Yes, loop through page numbers and call `viewer.view(page, options, stream)`
      for each page; the library streams each JPG independently.
    question: Can I render multiple pages of a DWG in one call?
  - answer: Absolutely – you can render to PNG, BMP, or TIFF by using `PngViewOptions`,
      `BmpViewOptions`, or `TiffViewOptions` respectively.
    question: Does GroupDocs.Viewer support other raster formats?
  - answer: The engine handles files up to 2 GB; for larger archives split the drawing
      into separate files before rendering.
    question: How large a DWG can be processed?
  - answer: No, GroupDocs.Viewer performs rendering entirely on the server side without
      needing AutoCAD installed.
    question: Is a separate CAD installation required?
  - answer: Java 8, 11, 17, and newer are fully supported.
    question: What Java versions are compatible?
  type: FAQPage
title: Render DWG in JPG con GroupDocs.Viewer Java – Guida completa
type: docs
url: /it/java/rendering-basics/render-cad-drawings-jpg-groupdocs-viewer-java/
weight: 1
---

# Render DWG come JPG con GroupDocs.Viewer Java: Un tutorial passo‑passo

## Introduzione

Render DWG as JPG con GroupDocs.Viewer Java semplifica la conversione di disegni CAD complessi in immagini leggere e adatte al web. In questa guida vedrai come configurare la libreria, impostare i percorsi di output e utilizzare un file PC3 per controllare le dimensioni e la qualità dell’immagine. Alla fine sarai in grado di automatizzare la conversione dei file DWG in JPG con poche righe di codice Java.

![Render CAD Drawings as JPG with GroupDocs.Viewer for Java](/viewer/rendering-basics/render-cad-drawings-as-jpg-java.png)

## Risposte rapide
- **Quale libreria gestisce la conversione?** GroupDocs.Viewer for Java.
- **Quale formato di file viene prodotto?** Immagini JPG.
- **È necessaria una licenza per lo sviluppo?** Una prova gratuita è sufficiente per i test; è richiesta una licenza completa per la produzione.
- **Posso controllare le dimensioni dell’immagine?** Sì, tramite un file di configurazione PC3.
- **Java 8 è sufficiente?** Java 8 o versioni successive sono pienamente supportate.

## Cos'è “render dwg as jpg”?

*Render dwg as jpg* è il processo di conversione di un disegno DWG (AutoCAD) in un'immagine raster JPEG. Questa conversione preserva la fedeltà visiva rendendo il file facile da visualizzare nei browser, nelle email o nelle app mobili. Riduce inoltre le dimensioni del file in modo significativo, consentendo tempi di caricamento più rapidi e una distribuzione più semplice su piattaforme e dispositivi.

## Perché usare GroupDocs.Viewer per Java?

GroupDocs.Viewer supporta **50+** formati di input—tra cui DWG, DXF e DWF—e può renderizzare disegni di centinaia di pagine senza caricare l’intero file in memoria. La libreria elabora tipici file CAD di 200 pagine in meno di 5 secondi su un server standard a 8 CPU, fornendo JPG di alta qualità che mantengono lo spessore delle linee e il colore.

## Prerequisiti

### Librerie e dipendenze richieste
- **GroupDocs.Viewer for Java** – versione 25.2 (o successiva).

### Requisiti per la configurazione dell'ambiente
- Java Development Kit 8 o successivo.
- Maven o Gradle per la gestione delle dipendenze.

### Prerequisiti di conoscenza
- Sintassi Java di base.
- Familiarità con i percorsi del file‑system.

## Configurazione di GroupDocs.Viewer per Java

Per iniziare, includi le dipendenze necessarie. Se usi Maven, aggiungi questa configurazione:

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
- **Prova gratuita**: Scarica una versione di prova da [GroupDocs Free Trial](https://releases.groupdocs.com/viewer/java/).
- **Licenza temporanea**: Ottieni una licenza temporanea per l’accesso a tutte le funzionalità su [GroupDocs Temporary License](https://purchase.groupdocs.com/temporary-license/).
- **Acquisto**: Per un utilizzo a lungo termine, acquista una licenza tramite [GroupDocs Purchase](https://purchase.groupdocs.com/buy).

### Risorse aggiuntive
- [Documentazione di GroupDocs Viewer](https://docs.groupdocs.com/viewer/java/)
- [Riferimento API](https://reference.groupdocs.com/viewer/java/)
- [Download di GroupDocs.Viewer](https://releases.groupdocs.com/viewer/java/)
- [Acquista licenza](https://purchase.groupdocs.com/buy)
- [Prova gratuita](https://releases.groupdocs.com/viewer/java/)
- [Licenza temporanea](https://purchase.groupdocs.com/temporary-license/)
- [Forum di supporto](https://forum.groupdocs.com/c/viewer/9)

## Inizializzazione di base

La classe `Viewer` carica un documento e fornisce metodi per renderizzare le sue pagine in vari formati. Dopo aver configurato l’ambiente e aggiunto le dipendenze, inizializza GroupDocs.Viewer nella tua applicazione Java:

```java
import com.groupdocs.viewer.Viewer;

public class ViewerInitialization {
    public static void main(String[] args) {
        try (Viewer viewer = new Viewer("path/to/your/dwg/file.dwg")) {
            // Your rendering code will go here.
        }
    }
}
```

## Guida all'implementazione

### Rendering di disegni CAD con configurazione specifica

Questa funzionalità consente di renderizzare un file DWG in un'immagine JPG utilizzando le impostazioni definite in un file PC3.

#### Panoramica

Caricheremo il disegno DWG, creeremo `JpgViewOptions` e indicheremo le opzioni a un file PC3 personalizzato che definisce le dimensioni della pagina, DPI e lo stile di rendering delle linee.

#### Implementazione passo‑passo

##### Importa i pacchetti necessari

`JpgViewOptions` specifica le impostazioni di rendering come risoluzione, dimensioni della pagina e formato di output per le immagini JPEG, mentre `Viewer` esegue la conversione effettiva.

```java
import com.groupdocs.viewer.Viewer;
import com.groupdocs.viewer.options.JpgViewOptions;
import java.nio.file.Path;
import java.nio.file.Paths;
```

##### Definisci la directory di output e il percorso del file

La cartella di output mantiene le immagini generate organizzate e facilita la pulizia dopo l'elaborazione batch.

```java
Path outputDirectory = Paths.get("YOUR_OUTPUT_DIRECTORY");
Path pageFilePathFormat = outputDirectory.resolve("pc3_result.jpg");
```

##### Carica il disegno CAD e imposta la configurazione

`Viewer` legge il file DWG e il metodo `setRenderOptions` applica la configurazione PC3 prima di renderizzare ogni pagina.

```java
try (Viewer viewer = new Viewer(TestFiles.SAMPLE_DWG_WITH_LAYOUTS_AND_LAYERS)) {
    JpgViewOptions options = new JpgViewOptions(pageFilePathFormat);
    
    // Set the PC3 configuration for rendering
    options.getCadOptions().setPc3File(TestFiles.SAMPLE_PC3_CONFIG);
    
    // Render the CAD drawing to a JPG image
    viewer.view(options);
}
```

#### Suggerimenti per la risoluzione dei problemi
- **Dipendenze mancanti**: Verifica che le coordinate Maven corrispondano alla versione installata.
- **Percorsi errati**: Usa percorsi assoluti o `Path.of(...)` per evitare problemi specifici della piattaforma.

## Configurazione dei percorsi per l'output di rendering

Una corretta gestione dei percorsi previene errori di file non trovato e semplifica i lavori batch.

### Definisci il percorso della directory di output

Puoi memorizzare le immagini renderizzate in una sottocartella denominata come il file sorgente per una facile ricerca.

```java
Path outputDirectory = Paths.get("YOUR_OUTPUT_DIRECTORY");
```

### Costruisci il percorso del file per l'immagine renderizzata

Un modello di denominazione come `drawing_page_{page}.jpg` è utile quando è necessario fare riferimento a pagine individuali in seguito.

```java
Path pageFilePathFormat = outputDirectory.resolve("pc3_result.jpg");
```

## Applicazioni pratiche

1. **Progettazione architettonica** – Condividi i piani edilizi con i clienti che non hanno software CAD.
2. **Progetti ingegneristici** – Includi schemi dettagliati nelle presentazioni PowerPoint.
3. **Design d'interni** – Genera rapidamente immagini mood‑board da file DWG di planimetrie.

## Considerazioni sulle prestazioni

- **Gestione delle risorse**: Chiama `viewer.close()` non appena il rendering termina per rilasciare i handle dei file.
- **Ottimizzazione della memoria**: Per file DWG molto grandi, aumenta l'heap JVM (`-Xmx2g`) per evitare `OutOfMemoryError`.

## Come renderizzare DWG come JPG usando GroupDocs.Viewer Java?

Carica il DWG con `new Viewer("drawing.dwg")`, crea un oggetto `JpgViewOptions` che punta al tuo file PC3 e invoca `viewer.view(pageNumber, options, outputStream)`. Questa chiamata a riga singola renderizza la pagina richiesta in un JPG di alta qualità applicando automaticamente le regole di layout PC3. Il metodo restituisce anche i metadati di rendering, consentendoti di verificare il conteggio delle pagine e le dimensioni dell’immagine dopo la conversione.

## Cos'è il file di configurazione PC3?

Un file PC3 è una configurazione AutoCAD in testo semplice che definisce le dimensioni della pagina, lo stile di stampa, DPI e la scala del peso delle linee per l'output raster. Fornire un PC3 personalizzato consente di standardizzare le dimensioni delle immagini su tutti i disegni renderizzati. Modificando il PC3 è possibile controllare i margini, l'orientamento della carta e la mappatura dei colori, garantendo risultati visivi coerenti per ogni conversione.

## Problemi comuni e soluzioni

- **Immagini vuote**: Assicurati che il file PC3 faccia riferimento a un plotter valido e che il DWG contenga livelli stampabili.
- **Bassa risoluzione**: Aumenta l'impostazione DPI nel file PC3 o imposta `options.setResolution(300)` programmaticamente.
- **Errori di licenza**: Verifica che il file di licenza sia posizionato nel classpath dell’applicazione e che il periodo di prova non sia scaduto.

## Domande frequenti

**Q: Posso renderizzare più pagine di un DWG in una singola chiamata?**  
A: Sì, itera sui numeri di pagina e chiama `viewer.view(page, options, stream)` per ogni pagina; la libreria trasmette ogni JPG in modo indipendente.

**Q: GroupDocs.Viewer supporta altri formati raster?**  
A: Assolutamente – è possibile renderizzare in PNG, BMP o TIFF utilizzando rispettivamente `PngViewOptions`, `BmpViewOptions` o `TiffViewOptions`.

**Q: Qual è la dimensione massima di un DWG che può essere elaborato?**  
A: Il motore gestisce file fino a 2 GB; per archivi più grandi suddividi il disegno in file separati prima del rendering.

**Q: È necessaria un'installazione CAD separata?**  
A: No, GroupDocs.Viewer esegue il rendering interamente sul lato server senza necessità di AutoCAD installato.

**Q: Quali versioni di Java sono compatibili?**  
A: Java 8, 11, 17 e versioni successive sono pienamente supportate.

## Conclusione

Ora disponi di un approccio completo e pronto per la produzione per **render dwg as jpg** usando GroupDocs.Viewer per Java. Il tutorial ha coperto la configurazione dell'ambiente, la configurazione basata su PC3, la gestione dei percorsi e i consigli sulle prestazioni. Integra questo modello in pipeline batch, servizi web o utility desktop per fornire anteprime JPEG rapide e di alta qualità di qualsiasi disegno CAD.

---

**Ultimo aggiornamento:** 2026-06-10  
**Testato con:** GroupDocs.Viewer for Java 25.2  
**Autore:** GroupDocs

## Tutorial correlati

- [Come renderizzare disegni CAD come PNG con dimensioni personalizzate e colore di sfondo usando GroupDocs.Viewer per Java](/viewer/java/advanced-rendering/render-cad-drawings-custom-png-groupdocs-java/)
- [Renderizzare i layer CAD in Java con GroupDocs.Viewer – Guida completa](/viewer/java/advanced-rendering/render-cad-layers-java-groupdocs-viewer/)
- [Dividere i disegni CAD in tile usando GroupDocs.Viewer Java per un rendering efficiente](/viewer/java/advanced-rendering/split-cad-drawings-into-tiles-groupdocs-viewer-java/)