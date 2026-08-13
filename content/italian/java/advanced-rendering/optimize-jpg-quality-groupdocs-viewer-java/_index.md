---
date: '2026-08-13'
description: Scopri come ridurre le dimensioni dei PDF Java regolando la qualità JPG
  con GroupDocs Viewer, abilitando anche convert PPTX to PDF Java e altre tecniche
  di riduzione delle dimensioni.
keywords:
- reduce pdf size java
- convert pptx to pdf java
- java reduce pdf file size
lastmod: '2026-08-13'
og_description: Riduci le dimensioni dei PDF Java modificando la qualità JPG con GroupDocs
  Viewer. Questa guida ti mostra come compress images, convert PPTX to PDF Java e
  ottenere PDF più piccoli senza perdere leggibilità.
og_image_alt: 'Guide: optimizing JPG quality to reduce PDF size in Java with GroupDocs
  Viewer'
og_title: Riduci le dimensioni dei PDF Java – ottimizzazione della qualità JPG con
  GroupDocs Viewer
schemas:
- author: GroupDocs
  dateModified: '2026-08-13'
  description: Learn how to reduce PDF size Java by adjusting JPG quality with GroupDocs
    Viewer, also enabling convert PPTX to PDF Java and other size‑reduction techniques.
  headline: How to reduce PDF size Java – optimize JPG quality
  type: TechArticle
- description: Learn how to reduce PDF size Java by adjusting JPG quality with GroupDocs
    Viewer, also enabling convert PPTX to PDF Java and other size‑reduction techniques.
  name: How to reduce PDF size Java – optimize JPG quality
  steps:
  - name: resolve the output directory path
    text: Create a helper class that builds the output folder where the PDF will be
      saved.
  - name: configure `PdfViewOptions` with desired JPG quality
    text: '`PdfViewOptions` is the configuration object that tells GroupDocs how to
      render the output PDF. The `setJpgQuality(byte quality)` method specifies the
      compression level for all JPG images that appear in the resulting document.
      **Explanation:** - Lower values produce smaller files but may reduce visu'
  - name: run the code and verify the result
    text: '`FeatureAdjustQualityOfJpgImages` is a sample class that runs the conversion
      with the configured JPG quality. Execute `FeatureAdjustQualityOfJpgImages.run()`.
      The generated `output.pdf` will contain JPG images at the quality level you
      specified, effectively **compressing PDF images** and reducing ov'
  type: HowTo
- questions:
  - answer: Lowering the JPG quality reduces the amount of data stored for each image,
      which can shrink the PDF size by 30‑70 % while keeping text crisp.
    question: How does adjusting JPG quality affect file size?
  - answer: This setting targets JPG images only; other raster formats have their
      own compression options within GroupDocs Viewer.
    question: Can I adjust image quality for formats other than JPG?
  - answer: A quality value between 50 and 70 generally provides clear images with
      a modest file size, ideal for most web applications.
    question: What is the ideal JPG quality setting for web use?
  - answer: Yes, you can loop over a directory of source files, apply the same `PdfViewOptions`
      configuration, and generate compressed PDFs in parallel.
    question: Is it possible to automate this process in a batch workflow?
  - answer: Yes, a valid GroupDocs Viewer license is required for production use.
      A free trial is available for evaluation.
    question: Do I need a license for production deployments?
  type: FAQPage
tags:
- reduce pdf size
- groupdocs viewer
- java pdf compression
- convert pptx to pdf
- jpg quality optimization
title: Come ridurre le dimensioni dei PDF Java – ottimizzare la qualità JPG
type: docs
url: /it/java/advanced-rendering/optimize-jpg-quality-groupdocs-viewer-java/
weight: 1
---

# Come ridurre le dimensioni di un PDF in Java – ottimizzare la qualità JPG

Bilanciare la dimensione del file e la fedeltà visiva è una sfida comune quando si lavora con i PDF. In questo tutorial scoprirai **come ridurre le dimensioni di un PDF in Java** regolando la qualità dell'immagine JPG all'interno dei documenti PDF usando GroupDocs Viewer per Java. Passeremo in rassegna l'installazione, l'implementazione del codice e consigli pratici così potrai comprimere le immagini PDF senza sacrificare la leggibilità.

![Optimize JPG Quality in PDFs with GroupDocs.Viewer for Java](/viewer/advanced-rendering/optimize-jpg-quality-in-pdfs.png)

## Risposte rapide
- **Cosa significa “reduce PDF size Java”?** Significa ridurre la qualità dell'immagine, applicare la compressione e ottimizzare le risorse in modo che il PDF finale occupi meno spazio e si carichi più velocemente.  
- **Quale impostazione controlla la qualità JPG?** `PdfViewOptions.setJpgQuality(byte quality)` dove il valore varia da 0 (minimo) a 100 (massimo).  
- **Posso anche convertire PPTX in PDF Java nello stesso flusso?** Sì—puntare il `Viewer` a una sorgente `.pptx` e le stesse opzioni si applicano.  
- **Qual è il livello di qualità tipico per la pubblicazione web?** Un valore intorno a 50‑70 offre un buon equilibrio tra chiarezza e dimensione per la maggior parte degli scenari web.  
- **È necessaria una licenza per questa funzionalità?** Una prova gratuita è sufficiente per la valutazione; è richiesta una licenza permanente di GroupDocs Viewer per l'uso in produzione.

## Che cosa significa reduce PDF size Java?
Ridurre le dimensioni di un PDF in Java si riferisce al processo di compressione dei file PDF all'interno di applicazioni Java, comprimendo le risorse incorporate, in particolare le immagini raster. Ridurre la qualità JPG riduce direttamente il peso di un PDF, spesso consentendo riduzioni di dimensione dal 30‑70 % mantenendo il testo leggibile.

## Perché regolare la qualità JPG con GroupDocs Viewer?
Regolare la qualità JPG con GroupDocs Viewer ti offre una soluzione a passaggio unico, lato server, che elimina la necessità di un passaggio di elaborazione delle immagini esterno. La libreria supporta **oltre 50 formati di input** e può gestire PDF con **centinaia di pagine** senza caricare l'intero file in memoria, risultando in conversioni più rapide e un consumo di memoria ridotto.

## Prerequisiti
- **GroupDocs.Viewer for Java** versione 25.2 o successiva.  
- Progetto Java basato su Maven con JDK 8 o successivo.  
- Familiarità di base con Java e la gestione dei PDF.  

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

> **Pro tip:** Mantieni la versione aggiornata per beneficiare di miglioramenti delle prestazioni e nuove opzioni di compressione.

## Guida all'implementazione

### Passo 1: risolvere il percorso della directory di output
Crea una classe di supporto che costruisce la cartella di output dove verrà salvato il PDF.

```java
import java.nio.file.Path;
import java.nio.file.Paths;

public class FeatureResolveOutputDirectoryPath {
    public static Path getOutputDirectoryPath(String subdirectory) {
        String directory = Paths.get("YOUR_OUTPUT_DIRECTORY", "AdjustQualityOfJpgImages", subdirectory).toString();
        
        try {
            return Paths.get(directory);
        } catch (IOException e) {
            throw new RuntimeException("Failed to create output directory.", e);
        }
    }
}
```

### Passo 2: configurare `PdfViewOptions` con la qualità JPG desiderata
`PdfViewOptions` è l'oggetto di configurazione che indica a GroupDocs come renderizzare il PDF di output.  
Il metodo `setJpgQuality(byte quality)` specifica il livello di compressione per tutte le immagini JPG presenti nel documento risultante.

```java
import com.groupdocs.viewer.Viewer;
import com.groupdocs.viewer.options.PdfViewOptions;

public class FeatureAdjustQualityOfJpgImages {
    public static void run() {
        Path outputDirectory = FeatureResolveOutputDirectoryPath.getOutputDirectoryPath("YOUR_DOCUMENT_DIRECTORY");
        Path filePath = outputDirectory.resolve("output.pdf");

        PdfViewOptions viewOptions = new PdfViewOptions(filePath);
        
        // Set desired JPG quality (0-100 scale)
        byte quality = 10;
        viewOptions.setJpgQuality(quality);

        try (Viewer viewer = new Viewer("YOUR_DOCUMENT_DIRECTORY/source.pptx")) {
            viewer.view(viewOptions);
        }
    }
}
```

**Spiegazione:**  
- Valori più bassi producono file più piccoli ma possono ridurre la nitidezza visiva.  
- L'esempio utilizza `source.pptx` per dimostrare **convert PPTX to PDF Java** mentre comprime simultaneamente le immagini.

### Passo 3: eseguire il codice e verificare il risultato
`FeatureAdjustQualityOfJpgImages` è una classe di esempio che esegue la conversione con la qualità JPG configurata. Esegui `FeatureAdjustQualityOfJpgImages.run()`. Il `output.pdf` generato conterrà immagini JPG al livello di qualità specificato, comprimendo efficacemente le **immagini PDF** e riducendo la dimensione complessiva del file.

## Problemi comuni e risoluzione
- **Percorso file errato:** Assicurati che il documento sorgente (`source.pptx`) esista rispetto alla directory di lavoro.  
- **Permessi insufficienti:** La cartella di output deve essere scrivibile; altrimenti viene generata una `RuntimeException`.  
- **PDF inaspettatamente grandi:** Verifica che il valore `quality` sia sufficientemente basso per i tuoi obiettivi di dimensione.

## Applicazioni pratiche
1. **Archiviazione dei documenti:** PDF più piccoli riducono i costi di archiviazione e migliorano la velocità di recupero.  
2. **Pubblicazione web:** Caricamenti di pagina più rapidi quando i PDF sono incorporati o collegati sui siti web.  
3. **Allegati email:** Rispettare i limiti di dimensione comuni riducendo la qualità delle immagini prima dell'invio.

## Considerazioni sulle prestazioni
- **Elaborazione batch:** Per grandi volumi, elabora i documenti in thread paralleli monitorando l'uso della memoria.  
- **Impostazioni di qualità ottimali:** Usa qualità più alta (80‑100) per PDF pronti alla stampa; per anteprime web, 30‑50 è spesso sufficiente.

## Conclusione
Ora sai **come ridurre le dimensioni di un PDF in Java** regolando la qualità delle immagini JPG con GroupDocs Viewer. Sperimenta diversi livelli di qualità, integra il codice nei tuoi flussi di lavoro esistenti e goditi PDF più veloci e leggeri.

### Prossimi passi
- Testa varie impostazioni di qualità per trovare il punto ottimale per il tuo caso d'uso.  
- Esplora funzionalità aggiuntive di GroupDocs come watermark o protezione con password.  

## Domande frequenti

**D: Come influisce la regolazione della qualità JPG sulla dimensione del file?**  
R: Ridurre la qualità JPG diminuisce la quantità di dati memorizzati per ogni immagine, il che può ridurre la dimensione del PDF dal 30‑70 % mantenendo il testo nitido.

**D: Posso regolare la qualità dell'immagine per formati diversi da JPG?**  
R: Questa impostazione riguarda solo le immagini JPG; gli altri formati raster hanno le proprie opzioni di compressione all'interno di GroupDocs Viewer.

**D: Qual è l'impostazione ideale di qualità JPG per l'uso web?**  
R: Un valore di qualità compreso tra 50 e 70 fornisce generalmente immagini chiare con una dimensione di file moderata, ideale per la maggior parte delle applicazioni web.

**D: È possibile automatizzare questo processo in un flusso di lavoro batch?**  
R: Sì, è possibile iterare su una directory di file sorgente, applicare la stessa configurazione `PdfViewOptions` e generare PDF compressi in parallelo.

**D: È necessaria una licenza per le distribuzioni in produzione?**  
R: Sì, è necessaria una licenza valida di GroupDocs Viewer per l'uso in produzione. È disponibile una prova gratuita per la valutazione.

**D: Come posso verificare la reale riduzione della qualità?**  
R: Confronta le dimensioni dei file prima e dopo la conversione e apri il PDF per ispezionare visivamente la nitidezza delle immagini; la differenza di dimensione dovrebbe riflettere il livello di qualità scelto.

**D: Posso impostare livelli di qualità diversi per pagine individuali?**  
R: Attualmente GroupDocs Viewer applica un'impostazione di qualità JPG uniforme per conversione. Per un controllo per pagina sarebbe necessario un passaggio di post‑processing con una libreria di immagini dedicata.

## Risorse
- [Documentazione](https://docs.groupdocs.com/viewer/java/)  
- [Riferimento API](https://reference.groupdocs.com/viewer/java/)  
- [Download GroupDocs.Viewer per Java](https://releases.groupdocs.com/viewer/java/)  
- [Acquista una licenza](https://purchase.groupdocs.com/buy)  
- [Versione di prova gratuita](https://releases.groupdocs.com/viewer/java/)  
- [Informazioni sulla licenza temporanea](https://purchase.groupdocs.com/temporary-license/)  
- [Forum di supporto](https://forum.groupdocs.com/c/viewer/9)  

---

**Last Updated:** 2026-08-13  
**Tested With:** GroupDocs.Viewer 25.2 for Java  
**Author:** GroupDocs

## Tutorial correlati

- [Come convertire PDF in HTML e ottimizzare la qualità dell'immagine in Java con GroupDocs.Viewer](/viewer/java/advanced-rendering/adjust-image-quality-groupdocs-viewer-java/)
- [limit jpg size java – Rendering con GroupDocs.Viewer](/viewer/java/rendering-basics/groupdocs-viewer-java-limit-jpg-size-rendering/)
- [Render PDF Layered Java – Rendering PDF a strati efficiente con GroupDocs.Viewer](/viewer/java/advanced-rendering/pdf-layered-rendering-java-groupdocs-viewer/)