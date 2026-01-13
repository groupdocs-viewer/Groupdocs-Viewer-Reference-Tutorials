---
date: '2026-01-13'
description: Scopri come convertire Excel in HTML Java rendendo visibili le righe
  e le colonne nascoste con GroupDocs Viewer. Questa guida ti aiuta a visualizzare
  i dati nascosti del foglio di calcolo in modo efficiente.
keywords:
- render hidden rows columns java
- GroupDocs Viewer Java
- Java spreadsheet rendering
title: excel to html java – Visualizza righe e colonne nascoste
type: docs
url: /it/java/advanced-rendering/render-hidden-rows-columns-java-groupdocs-viewer/
weight: 1
---

# excel to html java – Visualizza righe e colonne nascoste nei fogli di calcolo Java con GroupDocs.Viewer

Convertire **excel to html java** può essere complicato quando il tuo workbook contiene righe o colonne nascoste. In questo tutorial imparerai come rendere visibili quegli elementi nascosti in modo che l'HTML risultante mostri l'intero set di dati. Ti guideremo nella configurazione di GroupDocs.Viewer, nell'impostazione del progetto Maven e nella scrittura del codice Java che rende i dati nascosti del foglio di calcolo visibili nell'output.

![Rendi visibili righe e colonne nascoste con GroupDocs.Viewer per Java](/viewer/advanced-rendering/render-hidden-rows-and-columns-java.png)

## Risposte rapide
- **GroupDocs.Viewer può visualizzare righe nascoste?** Sì – abilita `setRenderHiddenRows(true)` e `setRenderHiddenColumns(true)`.
- **Quale libreria converte excel to html java?** GroupDocs.Viewer for Java.
- **È necessaria una licenza?** Una versione di prova è sufficiente per la valutazione; è richiesta una licenza permanente per la produzione.
- **Formati supportati?** Oltre 50, inclusi XLSX, XLS, CSV e molti altri.
- **L'uso della memoria è un problema?** I file di grandi dimensioni potrebbero richiedere un aumento della dimensione dell'heap; monitora la memoria durante la conversione.

## Che cos'è excel to html java?
`excel to html java` indica il processo di conversione dei workbook Microsoft Excel (XLSX, XLS) in pagine HTML utilizzando librerie Java. Questo consente la visualizzazione basata sul web dei fogli di calcolo senza richiedere Microsoft Office sul client.

## Perché visualizzare righe e colonne nascoste?
Molti file Excel nascondono righe o colonne per semplificare la presentazione, ma quelle celle nascoste spesso contengono dati critici (formule, metadati o informazioni supplementari). Visualizzarle garantisce **visualizzare i dati nascosti del foglio di calcolo** e mantiene l'integrità dei dati quando si condividono report online.

## Prerequisiti

### Librerie e dipendenze richieste
Per implementare questa funzionalità, assicurati di includere GroupDocs.Viewer for Java come dipendenza nel tuo progetto. Questa libreria è essenziale per il rendering dei documenti in vari formati come HTML, PDF e file immagine.

### Requisiti di configurazione dell'ambiente
- **Java Development Kit (JDK)**: versione 8 o successiva  
- **IDE**: IntelliJ IDEA, Eclipse o simili  
- **Maven**: per la gestione delle dipendenze del progetto  

### Prerequisiti di conoscenza
Una solida padronanza della programmazione Java e una conoscenza di base di Maven ti aiuteranno a seguire i passaggi senza difficoltà.

## Configurazione di GroupDocs.Viewer per Java
Per iniziare a utilizzare GroupDocs.Viewer nella tua applicazione Java, devi configurarlo tramite Maven. Aggiungi il repository e la dipendenza al tuo `pom.xml`:

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
- **Versione di prova gratuita** – Scarica una versione di prova per valutare le funzionalità.  
- **Licenza temporanea** – Richiedi una licenza temporanea per l'accesso completo alle funzionalità durante i test.  
- **Acquisto** – Ottieni una licenza permanente per l'uso in produzione.

Dopo aver configurato Maven e ottenuto la licenza, inizializza GroupDocs.Viewer:

```java
import com.groupdocs.viewer.Viewer;

public class ViewerInitialization {
    public static main(String[] args) {
        // Initialize the viewer with your license file if available.
        try (Viewer viewer = new Viewer("path/to/your/document.xlsx")) {
            // Your code here...
        }
    }
}
```

## Guida all'implementazione

### Rendering di righe e colonne nascoste nei fogli di calcolo
Questa funzionalità consente di renderizzare righe e colonne nascoste di un foglio di calcolo durante la conversione in formato HTML. Di seguito trovi una procedura passo‑passo.

#### Passo 1: Definisci il percorso della directory di output
Inizia definendo dove verranno salvati i file renderizzati:

```java
import java.nio.file.Path;
import java.nio.file.Paths;

Path outputDirectory = Paths.get("YOUR_OUTPUT_DIRECTORY", "RenderHiddenRowsAndColumns");
```

#### Passo 2: Configura HTMLViewOptions
Imposta `HtmlViewOptions` per incorporare le risorse direttamente nei file HTML generati:

```java
import com.groupdocs.viewer.options.HtmlViewOptions;

// Create a file path format for rendering each page.
Path pageFilePathFormat = outputDirectory.resolve("page_{0}.html");

HtmlViewOptions viewOptions = HtmlViewOptions.forEmbeddedResources(pageFilePathFormat);
```

#### Passo 3: Abilita il rendering di colonne e righe nascoste
Indica al viewer di includere gli elementi nascosti nell'output:

```java
// Enable rendering of hidden columns and rows.
viewOptions.getSpreadsheetOptions().setRenderHiddenColumns(true);
viewOptions.getSpreadsheetOptions().setRenderHiddenRows(true);
```

#### Passo 4: Inizializza il Viewer con il documento e avvia il rendering
Infine, renderizza il documento in HTML utilizzando le opzioni configurate:

```java
import com.groupdocs.viewer.Viewer;

try (Viewer viewer = new Viewer("YOUR_DOCUMENT_DIRECTORY/SAMPLE_XLSX_WITH_HIDDEN_ROW_AND_COLUMN")) {
    // Render the document to HTML using the specified view options.
    viewer.view(viewOptions);
} catch (Exception e) {
    System.out.println("Error rendering document: " + e.getMessage());
}
```

**Suggerimenti per la risoluzione dei problemi**: verifica che tutti i percorsi dei file siano corretti e che le dipendenze Maven siano risolte senza conflitti.

## Applicazioni pratiche
Ecco alcuni scenari reali in cui **excel to html java** con rendering dei dati nascosti è particolarmente utile:

1. **Report finanziari** – Mostra ogni metrica, anche quelle nascoste per calcoli interni, per soddisfare i requisiti di audit.  
2. **Analisi dei dati** – Conserva set di dati completi quando condividi i risultati dell'analisi in dashboard web.  
3. **Strumenti educativi** – Fornisci agli studenti il contenuto completo del foglio di calcolo per esercizi didattici.

## Considerazioni sulle prestazioni
- **Gestione della memoria** – I workbook di grandi dimensioni possono consumare una notevole quantità di heap; considera l'aumento dell'opzione `-Xmx` della JVM.  
- **Ottimizzazione I/O** – Salva l'HTML renderizzato in una directory SSD veloce per ridurre la latenza.  
- **Aggiornamenti della libreria** – Mantieni GroupDocs.Viewer aggiornato per beneficiare delle correzioni di performance.

## Conclusione
Ora sai come convertire **excel to html java** garantendo che righe e colonne nascoste vengano renderizzate, ottenendo una visualizzazione completa dei dati del foglio di calcolo. Sperimenta con diverse opzioni, come la personalizzazione CSS, per adattare ulteriormente l'output HTML alle esigenze del tuo progetto.

## Domande frequenti

**D: Posso usare GroupDocs.Viewer gratuitamente?**  
R: Sì, è disponibile una versione di prova per la valutazione. Per l'uso illimitato in produzione è necessaria una licenza.

**D: Quali formati di file supporta GroupDocs.Viewer?**  
R: Oltre 50 formati, inclusi XLSX, XLS, CSV, PDF, DOCX e molti tipi di immagine.

**D: Come gestire file Excel molto grandi?**  
R: Aumenta la dimensione dell'heap della JVM, suddividi il workbook in parti più piccole o elabora i fogli singolarmente.

**D: È possibile personalizzare l'HTML generato?**  
R: Assolutamente sì. `HtmlViewOptions` offre numerose impostazioni per CSS, scripting e gestione delle risorse.

**D: Dove posso trovare altri esempi di rendering di dati nascosti?**  
R: La documentazione ufficiale e il riferimento API contengono ulteriori snippet di codice e guide d'uso.

## Risorse
- **Documentazione**: [GroupDocs Viewer Documentation](https://docs.groupdocs.com/viewer/java/)
- **Riferimento API**: [GroupDocs API Reference](https://reference.groupdocs.com/viewer/java/)
- **Download**: [Get GroupDocs.Viewer](https://releases.groupdocs.com/viewer/java/)
- **Acquisto**: [Buy a License](https://purchase.groupdocs.com/buy)
- **Versione di prova gratuita**: [Try Free Version](https://releases.groupdocs.com/viewer/java/)
- **Licenza temporanea**: [Request Temporary License](https://purchase.groupdocs.com/temporary-license/)
- **Supporto**: [GroupDocs Forum](https://forum.groupdocs.com/c/viewer/9)

---

**Ultimo aggiornamento:** 2026-01-13  
**Testato con:** GroupDocs Viewer 25.2 for Java  
**Autore:** GroupDocs