---
date: '2026-03-05'
description: Scopri come comprimere i PDF in Java regolando la qualità JPG con GroupDocs.Viewer
  – un metodo semplice per la compressione di PDF in Java, che bilancia la dimensione
  del file e la fedeltà visiva.
keywords:
- reduce pdf size java
- convert pptx to pdf
- compress pdf images
title: Come comprimere PDF in Java – Ottimizzare la qualità JPG
type: docs
url: /it/java/advanced-rendering/optimize-jpg-quality-groupdocs-viewer-java/
weight: 1
---

# Come comprimere pdf in Java – Ottimizzare la qualità JPG

Bilanciare la dimensione del file e la fedeltà visiva è una sfida comune quando si lavora con i PDF. In questo tutorial scoprirai **come comprimere pdf** regolando la qualità dell’immagine JPG all’interno dei documenti PDF usando GroupDocs.Viewer per Java. Ti guideremo attraverso la configurazione, l’implementazione del codice e consigli pratici affinché tu possa comprimere le immagini PDF con fiducia senza sacrificare la leggibilità.

![Ottimizzare la qualità JPG nei PDF con GroupDocs.Viewer per Java](/viewer/advanced-rendering/optimize-jpg-quality-in-pdfs.png)

## Risposte rapide
- **Che cosa significa “reduce PDF size Java”?** Adjusting image quality, compression, and resource handling to create smaller PDF files in Java applications.  
- **Quale impostazione controlla la qualità JPG?** `PdfViewOptions.setJpgQuality(byte quality)` where the value ranges from 0 (lowest) to 100 (highest).  
- **Posso anche convertire PPTX in PDF nello stesso flusso?** Yes—simply point the `Viewer` at a `.pptx` source and the same options apply.  
- **Quale livello di qualità è tipico per la pubblicazione web?** A value around **50‑70** gives a good balance for most web scenarios.  
- **Ho bisogno di una licenza per questa funzionalità?** A free trial works for evaluation; a permanent license is required for production use.

## Come comprimere pdf in Java – Panoramica
Ridurre le dimensioni di un PDF in Java comporta l'ottimizzazione delle risorse all'interno di un PDF—soprattutto le immagini—così il file finale occupa meno spazio e si carica più velocemente. Abbassando la qualità JPG, si **comprimono le immagini PDF**, che spesso costituiscono la parte più ingombrante di un documento.

## Cos'è “reduce PDF size Java”?
Ridurre le dimensioni di un PDF in Java comporta l'ottimizzazione delle risorse all'interno di un PDF—soprattutto le immagini—così il file finale occupa meno spazio e si carica più velocemente. Abbassando la qualità JPG, si **comprimono le immagini PDF**, che spesso costituiscono la parte più ingombrante di un documento.

## Perché regolare la qualità JPG con GroupDocs Viewer?
- **Riduzione significativa delle dimensioni**: Abbassare la qualità dell'immagine può ridurre i PDF del 30‑70 % a seconda della risoluzione originale.  
- **Conversione a passaggio singolo**: Non è necessario un passaggio separato di elaborazione delle immagini; GroupDocs lo gestisce durante la generazione del PDF.  
- **Flessibilità**: È possibile regolare finemente il valore di qualità `byte` in base ai requisiti del progetto (ad esempio, stampa ad alta qualità vs. anteprima web leggera).  

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

> **Consiglio professionale:** Mantieni la versione aggiornata per beneficiare di miglioramenti delle prestazioni e nuove opzioni di compressione.

## Guida all'implementazione

### Passo 1: Risolvere il percorso della directory di output
Crea una classe helper che costruisce la cartella di output dove verrà salvato il PDF.

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

### Passo 2: Configurare `PdfViewOptions` con la qualità JPG desiderata
Imposta il livello di qualità JPG (0‑100) prima di renderizzare il documento.

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
- `setJpgQuality(byte quality)` indica a GroupDocs quanta compressione applicare alle immagini JPG. Valori più bassi producono file più piccoli ma possono ridurre la nitidezza visiva.  
- L'esempio utilizza `source.pptx` per dimostrare **convert pptx to pdf** mentre comprime simultaneamente le immagini.

### Passo 3: Eseguire il codice e verificare il risultato
Esegui `FeatureAdjustQualityOfJpgImages.run()`. Il `output.pdf` generato conterrà immagini JPG al livello di qualità specificato, comprimendo efficacemente le **immagini PDF** e riducendo le dimensioni complessive del file.

## Problemi comuni e risoluzione
- **Percorso file errato:** Assicurati che il documento sorgente (`source.pptx`) esista rispetto alla directory di lavoro.  
- **Permessi insufficienti:** La cartella di output deve essere scrivibile; altrimenti verrà generata una `RuntimeException`.  
- **PDF più grandi del previsto:** Verifica che il valore `quality` sia sufficientemente basso per i tuoi obiettivi di dimensione.  

## Applicazioni pratiche
1. **Archiviazione dei documenti:** PDF più piccoli riducono i costi di archiviazione e migliorano la velocità di recupero.  
2. **Pubblicazione web:** Caricamenti di pagina più rapidi quando i PDF sono incorporati o collegati sui siti web.  
3. **Allegati email:** Rispettare i limiti di dimensione abbassando la qualità delle immagini prima dell'invio.  

## Considerazioni sulle prestazioni
- **Elaborazione batch:** Per un gran numero di documenti, elabora in thread paralleli monitorando l'uso della memoria.  
- **Impostazioni di qualità ottimali:** Usa qualità più alta (80‑100) per PDF pronti per la stampa; per anteprime web, 30‑50 è spesso sufficiente.  

## Conclusione
Ora sai **come comprimere pdf** regolando la qualità delle immagini JPG con GroupDocs.Viewer. Sperimenta diversi livelli di qualità, integra il codice nei tuoi flussi di lavoro esistenti e goditi PDF più veloci e leggeri.

### Prossimi passi
- Testa varie impostazioni di qualità per trovare il punto ottimale per il tuo caso d'uso.  
- Esplora funzionalità aggiuntive di GroupDocs come watermark o protezione con password.  

## Sezione FAQ

1. **Come influisce la regolazione della qualità JPG sulle dimensioni del file?**  
   Abbassare la qualità riduce le dimensioni del file, rendendo più facile condividere o archiviare i documenti.

2. **Posso regolare la qualità dell'immagine per formati diversi da JPG?**  
   Questa funzionalità è specifica per le immagini JPG all'interno dei PDF; tuttavia, GroupDocs.Viewer offre altre opzioni per formati diversi.

3. **Qual è l'impostazione ideale di qualità JPG per l'uso web?**  
   Un equilibrio intorno a 50‑70 fornisce spesso buona chiarezza con dimensioni ridotte, adatto alle applicazioni web.

4. **È possibile automatizzare questo processo in un flusso di lavoro batch?**  
   Sì, è possibile integrare questa funzionalità in sistemi automatizzati per gestire più documenti in modo efficiente.

5. **Cosa fare se il PDF di output non viene generato come previsto?**  
   Controlla il percorso del documento di input e assicurati che tutte le dipendenze siano configurate correttamente.

## Domande frequenti

**Q:** *Posso usare questo approccio per convertire altri formati come DOCX in PDF riducendo le dimensioni?*  
**A:** Assolutamente. La stessa impostazione `PdfViewOptions.setJpgQuality` funziona per qualsiasi formato sorgente che genera immagini JPG nel PDF.

**Q:** *La riduzione della qualità JPG influisce sul rendering del testo?*  
**A:** No. Il testo è basato su vettori e rimane nitido; solo le immagini raster sono interessate.

**Q:** *È possibile impostare livelli di qualità diversi per pagine diverse?*  
**A:** Attualmente GroupDocs applica un'impostazione di qualità uniforme per conversione. Per un controllo per pagina, sarebbe necessario post‑elaborare il PDF con una libreria dedicata alla gestione delle immagini.

**Q:** *È necessaria una licenza per le distribuzioni in produzione?*  
**A:** Sì, è necessaria una licenza valida di GroupDocs.Viewer per l'uso in produzione. È disponibile una versione di prova gratuita per la valutazione.

**Q:** *Come posso verificare la reale riduzione della qualità?*  
**A:** Confronta le dimensioni dei file prima e dopo la conversione e apri il PDF per ispezionare visivamente la chiarezza delle immagini.

---

**Risorse**  
- [Documentazione](https://docs.groupdocs.com/viewer/java/)  
- [Riferimento API](https://reference.groupdocs.com/viewer/java/)  
- [Scarica GroupDocs.Viewer per Java](https://releases.groupdocs.com/viewer/java/)  
- [Acquista una licenza](https://purchase.groupdocs.com/buy)  
- [Versione di prova gratuita](https://releases.groupdocs.com/viewer/java/)  
- [Informazioni sulla licenza temporanea](https://purchase.groupdocs.com/temporary-license/)  
- [Forum di supporto](https://forum.groupdocs.com/c/viewer/9)  

---

**Last Updated:** 2026-03-05  
**Tested With:** GroupDocs.Viewer 25.2 for Java  
**Author:** GroupDocs