---
date: '2026-04-01'
description: Scopri come suddividere i disegni CAD in tasselli usando GroupDocs Viewer
  per Java, migliorando le prestazioni di rendering e semplificando la gestione di
  file di grandi dimensioni.
keywords:
- how to split cad
- GroupDocs Viewer Java
- CAD tiling
title: Come suddividere i disegni CAD in tasselli con GroupDocs Viewer
type: docs
url: /it/java/advanced-rendering/split-cad-drawings-into-tiles-groupdocs-viewer-java/
weight: 1
---

# Come dividere i disegni CAD in tile con GroupDocs Viewer

Se ti stai chiedendo **come dividere i file CAD** in pezzi più piccoli e gestibili, sei nel posto giusto. In questo tutorial ti guideremo passo passo attraverso le operazioni necessarie per suddividere grandi disegni CAD in tile usando **GroupDocs Viewer for Java**. Alla fine avrai una soluzione pronta all'uso che migliora la velocità di rendering, riduce il consumo di memoria e facilita la visualizzazione dei disegni in applicazioni web o mobile.

![Dividi i disegni CAD con GroupDocs.Viewer per Java](/viewer/advanced-rendering/split-cad-drawings-java.png)

## Risposte rapide
- **Cosa ottiene la “divisione CAD”?** Divide un disegno massiccio in immagini più piccole (tile) che si caricano più velocemente e consumano meno memoria.  
- **Quale formato viene usato per i tile?** I file PNG vengono generati di default, ma altri formati sono supportati tramite le opzioni di Viewer.  
- **Ho bisogno di una licenza?** Una licenza di prova gratuita funziona per lo sviluppo; è necessaria una licenza a pagamento per la produzione.  
- **Posso cambiare la dimensione del tile?** Sì – regola i calcoli `tileWidth` e `tileHeight` per adattarli alle tue esigenze.  
- **Questo approccio è thread‑safe?** Il rendering di ogni tile in una propria istanza `Viewer` con try‑with‑resources è sicuro per l'esecuzione concorrente.

## Che cosa significa “dividere CAD”?
Dividere CAD indica la suddivisione di un singolo, spesso enorme, disegno CAD in più sezioni rettangolari (tile). Ogni tile viene renderizzato in modo indipendente, consentendo di caricare solo le parti di cui l'utente ha effettivamente bisogno—perfetto per mappe web, portali documentali e visualizzatori mobili.

## Perché usare GroupDocs Viewer per Java?
GroupDocs Viewer offre supporto pronto all'uso per oltre 100 formati di file, inclusi DWG, DXF e DWF. La sua API per i tile ti consente di specificare coordinate precise, così puoi renderizzare esattamente l'area di interesse senza dover elaborare l'intero file prima. Questo risparmia cicli CPU, riduce la larghezza di banda e offre un'esperienza utente più fluida.

## Prerequisiti
- **Libraries**: GroupDocs.Viewer for Java ≥ 25.2.  
- **JDK**: Qualsiasi recente Java Development Kit (Java 8+).  
- **IDE**: IntelliJ IDEA, Eclipse o un altro IDE compatibile con Java.  
- **Build Tool**: Maven (altri strumenti di build funzionano purché la dipendenza sia aggiunta).  

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

### Acquisizione della licenza
GroupDocs.Viewer offre una licenza di prova gratuita per la valutazione:

- **Free Trial**: Visita [GroupDocs Free Trial](https://releases.groupdocs.com/viewer/java/) per scaricare la libreria.  
- **Temporary License**: Richiedi una licenza temporanea su [Temporary License Page](https://purchase.groupdocs.com/temporary-license/).  
- **Full License**: Acquista una licenza di produzione sulla [Purchase Page](https://purchase.groupdocs.com/buy).

### Inizializzazione di base
Crea un'istanza semplice di `Viewer` per verificare che la libreria venga caricata correttamente:

```java
import com.groupdocs.viewer.Viewer;

public class ViewerSetup {
    public static void main(String[] args) {
        try (Viewer viewer = new Viewer("path/to/your/drawing.dwg")) {
            // Your rendering code goes here.
        }
    }
}
```

## Guida passo‑passo per dividere i disegni CAD in tile

### Passo 1: Definisci la directory di output
Salveremo ogni tile come file PNG separato. L'uso di un metodo di utilità mantiene la logica del percorso pulita e riutilizzabile.

```java
import java.nio.file.Path;

Path outputDirectory = Utils.getOutputDirectoryPath("SplitDrawingIntoTiles");
Path pageFilePathFormat = outputDirectory.resolve("page_{0}.png");
```

### Passo 2: Configura le opzioni di visualizzazione
Imposta il formato di rendering su PNG e indica al viewer di non pre‑caricare ogni pagina (ciò salva memoria).

```java
import com.groupdocs.viewer.options.PngViewOptions;
import com.groupdocs.viewer.options.ViewInfoOptions;

PngViewOptions viewOptions = new PngViewOptions(pageFilePathFormat);
ViewInfoOptions viewInfoOptions = ViewInfoOptions.forPngView(false);
```

### Passo 3: Calcola le dimensioni del tile
Innanzitutto otteniamo la larghezza e l'altezza originali del disegno, poi lo suddividiamo in quattro quadranti uguali.

```java
import com.groupdocs.viewer.results.ViewInfo;
import com.groupdocs.viewer.options.Tile;

ViewInfo viewInfo = new Viewer("path/to/your/drawing.dwg").getViewer().getViewInfo(viewInfoOptions);
int width = viewInfo.getPages().get(0).getWidth();
int height = viewInfo.getPages().get(0).getHeight();

// Each tile is a quarter of the total size.
int tileWidth = width / 2;
int tileHeight = height / 2;

Tile[] tiles = {
    new Tile(0, 0, tileWidth, tileHeight),
    new Tile(tileWidth, 0, tileWidth, tileHeight),
    new Tile(0, tileHeight, tileWidth, tileHeight),
    new Tile(tileWidth, tileHeight, tileWidth, tileHeight)
};
```

### Passo 4: Renderizza e salva i tile
Aggiungi i tile calcolati alle opzioni di rendering e lascia che il `Viewer` generi i file PNG.

```java
viewOptions.getCadOptions().getTiles().addAll(java.util.Arrays.asList(tiles));

try (Viewer viewer = new Viewer("path/to/your/drawing.dwg")) {
    viewer.view(viewOptions);
}
```

### Suggerimenti per la risoluzione dei problemi
- **Build path** – Assicurati che i file JAR di GroupDocs siano nel classpath.  
- **Permissions** – La cartella di output deve essere scrivibile dal processo Java.  
- **Exceptions** – Se visualizzi `ViewerException`, verifica che il file DWG non sia corrotto e che la licenza corretta sia applicata.

## Casi d'uso comuni per la divisione dei tile CAD
1. **Web Mapping** – Carica solo la porzione visibile di una pianta quando l'utente esegue pan/zoom.  
2. **Document Management** – Archivia ogni tile separatamente per una generazione di anteprime più rapida.  
3. **Mobile Viewing** – Riduci la larghezza di banda scaricando solo i tile necessari per lo schermo corrente.

## Considerazioni sulle prestazioni
- **Tile Size** – Tile più grandi significano meno file ma rendering più lento; trova un equilibrio in base alle esigenze della tua UI.  
- **Memory Monitoring** – Usa gli strumenti di profiling di Java (ad es., VisualVM) per monitorare l'uso dell'heap durante l'elaborazione di disegni molto grandi.  
- **Resource Cleanup** – Il pattern try‑with‑resources mostrato sopra rilascia automaticamente le risorse native.

## Domande frequenti

**Q: Posso dividere altri tipi di file (PDF, immagini) in tile usando lo stesso approccio?**  
A: Sì. GroupDocs Viewer supporta molti formati; è sufficiente utilizzare la classe di opzioni corrispondente (ad es., `PdfViewOptions`).

**Q: Come modifico la qualità dell'immagine di output?**  
A: Regola `viewOptions.setResolution(int dpi)` o imposta le impostazioni di compressione sull'oggetto `PngOptions`.

**Q: La mia applicazione esaurisce la memoria su file DWG molto grandi—cosa posso fare?**  
A: Riduci le dimensioni dei tile, aumenta l'heap JVM (`-Xmx`) o renderizza i tile in sequenza in istanze `Viewer` separate.

**Q: È possibile renderizzare i tile in modo asincrono?**  
A: Assolutamente. Avvolgi ogni chiamata di rendering del tile in un `CompletableFuture` o usa un executor service per parallelizzare il carico di lavoro.

**Q: Ho bisogno di una licenza separata per ogni tile?**  
A: No. Una singola licenza valida di GroupDocs Viewer copre tutte le operazioni di rendering all'interno della tua applicazione.

## Risorse
- [Documentazione](https://docs.groupdocs.com/viewer/java/)
- [Riferimento API](https://reference.groupdocs.com/viewer/java/)
- [Scarica GroupDocs.Viewer](https://releases.groupdocs.com/viewer/java/)
- [Acquista una licenza](https://purchase.groupdocs.com/buy)
- [Prova gratuita](https://releases.groupdocs.com/viewer/java/)
- [Licenza temporanea](https://purchase.groupdocs.com/temporary-license/)
- [Forum di supporto](https://forum.groupdocs.com/c/viewer/9)

---

**Last Updated:** 2026-04-01  
**Testato con:** GroupDocs.Viewer 25.2 for Java  
**Autore:** GroupDocs  

---