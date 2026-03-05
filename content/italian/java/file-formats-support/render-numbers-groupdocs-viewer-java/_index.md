---
date: '2026-03-05'
description: Scopri come convertire numeri in PDF e altri formati come HTML, JPG,
  PNG usando GroupDocs.Viewer per Java. Questa guida copre l'installazione, le tecniche
  di rendering e le applicazioni pratiche.
keywords:
- GroupDocs.Viewer for Java
- render Apple Numbers documents
- convert Numbers to HTML, JPG, PNG, PDF
title: Converti Numbers in PDF con GroupDocs.Viewer per Java
type: docs
url: /it/java/file-formats-support/render-numbers-groupdocs-viewer-java/
weight: 1
---

# Converti Numbers in PDF (e altri formati) con GroupDocs.Viewer per Java

Visualizzare i documenti Apple Numbers sul web o nelle applicazioni desktop può essere complicato, soprattutto quando è necessario **convertire Numbers in PDF** o incorporarli come immagini. In questo tutorial vedremo come utilizzare **GroupDocs.Viewer per Java** per renderizzare i file Numbers in HTML, JPG, PNG, **e PDF**—offrendoti opzioni flessibili per condividere, visualizzare in anteprima o archiviare i tuoi fogli di calcolo.

![Renderizza documenti Apple Numbers con GroupDocs.Viewer per Java](/viewer/file-formats-support/render-apple-numbers-documents-java.png)

### Cosa imparerai
- Come configurare GroupDocs.Viewer in un progetto Java basato su Maven  
- Codice passo‑passo per **convertire Numbers in PDF**, **convertire Numbers in HTML** e **convertire Numbers in JPG**  
- Scenari reali in cui la conversione dei documenti aggiunge valore a portali web, flussi di lavoro email e integrazioni DMS  

## Risposte rapide
- **Posso convertire Numbers in PDF con Java?** Sì, usando `PdfViewOptions` in GroupDocs.Viewer.  
- **Quale formato è migliore per l'anteprima web?** HTML offre l'esperienza più interattiva.  
- **Ho bisogno di una licenza per l'uso in produzione?** È necessaria una licenza commerciale per le distribuzioni non‑trial.  
- **La conversione delle immagini è supportata?** Assolutamente—usa `JpgViewOptions` o `PngViewOptions` per ottenere immagini ad alta qualità.  
- **Quale versione di Java è richiesta?** Java 8+ e Maven per la gestione delle dipendenze.

## Prerequisiti
- Java Development Kit (JDK) 8 o superiore installato.  
- Maven per la gestione delle dipendenze.  
- Familiarità di base con I/O di file Java e percorsi.  

## Configurazione di GroupDocs.Viewer per Java

### Installazione con Maven
Aggiungi il repository e la dipendenza al tuo `pom.xml`. Questo blocco deve rimanere esattamente così:

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
- **Prova gratuita:** Valuta tutte le funzionalità senza costi.  
- **Licenza temporanea:** Richiedi una chiave a tempo limitato per test estesi.  
- **Acquisto:** Ottieni una licenza completa per progetti commerciali.

## Rendering del documento Numbers in HTML  
*Caso d'uso: incorpora un foglio di calcolo direttamente in una pagina web.*

### Passo 1: Inizializza Viewer e configura le opzioni HTML
Di seguito il codice esatto da eseguire. I commenti spiegano ogni riga, ma **non modificare il blocco di codice**.

```java
import com.groupdocs.viewer.Viewer;
import com.groupdocs.viewer.options.HtmlViewOptions;
import java.nio.file.Path;

Path outputDirectory = Path.of("YOUR_OUTPUT_DIRECTORY");
Path pageFileFullPath = outputDirectory.resolve("Numbers_result.html");

try (Viewer viewer = new Viewer("YOUR_DOCUMENT_DIRECTORY/SAMPLE_NUMBERS")) {
    HtmlViewOptions options = HtmlViewOptions.forEmbeddedResources(pageFileFullPath);
    viewer.view(options);
}
```

- **Perché è importante:** `HtmlViewOptions.forEmbeddedResources()` raggruppa CSS e immagini all'interno dell'HTML, rendendolo perfetto per anteprime web rapide.

## Rendering del documento Numbers in JPG  
*Ideale per condividere un'istantanea di un foglio di calcolo sui social media o via email.*

### Passo 1: Configura Viewer e opzioni JPG
```java
import com.groupdocs.viewer.Viewer;
import com.groupdocs.viewer.options.JpgViewOptions;
import java.nio.file.Path;

Path outputDirectory = Path.of("YOUR_OUTPUT_DIRECTORY");
Path pageFileFullPath = outputDirectory.resolve("Numbers_result.jpg");

try (Viewer viewer = new Viewer("YOUR_DOCUMENT_DIRECTORY/SAMPLE_NUMBERS")) {
    JpgViewOptions options = new JpgViewOptions(pageFileFullPath);
    viewer.view(options);
}
```

- **Suggerimento:** Regola la qualità dell'immagine tramite `options.setQuality(int)` se hai bisogno di file più piccoli.

## Rendering del documento Numbers in PNG  
*Ideale quando ti serve un'immagine senza perdita, ad alta risoluzione, per i report.*

### Passo 1: Inizializza e configura le opzioni PNG
```java
import com.groupdocs.viewer.Viewer;
import com.groupdocs.viewer.options.PngViewOptions;
import java.nio.file.Path;

Path outputDirectory = Path.of("YOUR_OUTPUT_DIRECTORY");
Path pageFileFullPath = outputDirectory.resolve("Numbers_result.png");

try (Viewer viewer = new Viewer("YOUR_DOCUMENT_DIRECTORY/SAMPLE_NUMBERS")) {
    PngViewOptions options = new PngViewOptions(pageFileFullPath);
    viewer.view(options);
}
```

- **Consiglio professionale:** Usa `options.setResolution(int)` per controllare i DPI per immagini pronte per la stampa.

## Rendering del documento Numbers in PDF  
*L'obiettivo principale per molti sviluppatori: **convertire Numbers in PDF** per archiviazione o distribuzione.*

### Passo 1: Configura Viewer per la conversione PDF
```java
import com.groupdocs.viewer.Viewer;
import com.groupdocs.viewer.options.PdfViewOptions;
import java.nio.file.Path;

Path outputDirectory = Path.of("YOUR_OUTPUT_DIRECTORY");
Path pageFileFullPath = outputDirectory.resolve("Numbers_result.pdf");

try (Viewer viewer = new Viewer("YOUR_DOCUMENT_DIRECTORY/SAMPLE_NUMBERS")) {
    PdfViewOptions options = new PdfViewOptions(pageFileFullPath);
    viewer.view(options);
}
```

- **Configurazione chiave:** `PdfViewOptions` consente di incorporare i font e controllare le dimensioni della pagina, garantendo che l'output corrisponda ai requisiti del tuo brand.

## Applicazioni pratiche
- **Integrazione web:** Renderizza in HTML per un visualizzatore di fogli di calcolo interattivo sul tuo sito.  
- **Condivisione di contenuti:** Converti in JPG/PNG per inserimenti rapidi di immagini in newsletter o chat.  
- **DMS aziendale:** Usa **convertire Numbers in PDF** per archiviare una versione non modificabile e ricercabile del foglio di calcolo.  

## Considerazioni sulle prestazioni
- **Gestione delle risorse:** Chiudi sempre il `Viewer` in un blocco try‑with‑resources (come mostrato) per liberare rapidamente le risorse native.  
- **File di grandi dimensioni:** Per file Numbers molto grandi, considera l'elaborazione pagina per pagina e lo streaming dei risultati per evitare un elevato consumo di memoria.  
- **Sicurezza dei thread:** Crea un'istanza separata di `Viewer` per ogni thread; la classe non è thread‑safe.

## Conclusione
Ora disponi di una toolbox completa per **convertire Numbers in PDF**, così come in HTML, JPG e PNG, utilizzando GroupDocs.Viewer per Java. Queste funzionalità ti consentono di creare pipeline di documenti flessibili—che tu stia alimentando un portale web, generando report o archiviando fogli di calcolo.

### Prossimi passi
Esplora ulteriori opzioni di personalizzazione nella [documentazione di GroupDocs](https://docs.groupdocs.com/viewer/java/) e sperimenta l'integrazione di queste funzionalità nelle tue applicazioni.

## Sezione FAQ

**Q1: Quali formati di file supporta GroupDocs.Viewer?**  
A1: Supporta un'ampia gamma di formati di documento, tra cui DOCX, XLSX, PDF e altri.

**Q2: Come gestire efficientemente file Numbers di grandi dimensioni?**  
A2: Utilizza le tecniche di gestione della memoria di Java e ottimizza il tuo codice per gestire efficacemente file di grandi dimensioni.

**Q3: GroupDocs.Viewer può essere usato in un progetto commerciale?**  
A4: Sì, ma sarà necessario acquistare una licenza per l'uso commerciale.

**Q4: È possibile personalizzare la qualità di output delle immagini?**  
A5: Assolutamente. Puoi regolare le impostazioni in `JpgViewOptions` e `PngViewOptions`.

**Q5: Dove posso trovare esempi di utilizzo più avanzati?**  
A5: Visita il [riferimento API](https://reference.groupdocs.com/viewer/java/) per una documentazione dettagliata.

## Domande frequenti

**Q: Come converto un file Numbers in PDF senza perdere la formattazione?**  
A: Usa `PdfViewOptions` come mostrato sopra; il viewer preserva automaticamente layout, font e stili delle celle.

**Q: Posso convertire un foglio di calcolo in un'immagine con una singola chiamata?**  
A: Sì, `JpgViewOptions` o `PngViewOptions` gestiscono la conversione in un unico passaggio, permettendoti di specificare risoluzione e qualità.

**Q: Esiste un modo per elaborare in batch più file Numbers?**  
A: Inserisci la logica del viewer in un ciclo, reinizializzando `Viewer` per ogni file, e scrivi ogni output in una cartella distinta.

**Q: È necessaria una licenza separata per ogni formato di output?**  
A: No, una singola licenza GroupDocs.Viewer copre tutti i formati supportati.

**Q: Quale versione di GroupDocs.Viewer è necessaria per queste funzionalità?**  
A: Gli esempi sono per la versione 25.2, che include il supporto completo per la conversione di Numbers in PDF/HTML/Image.

## Risorse
- **Documentazione:** [GroupDocs.Viewer Java Docs](https://docs.groupdocs.com/viewer/java/)
- **Riferimento API:** [GroupDocs API Reference](https://reference.groupdocs.com/viewer/java/)
- **Download:** [Get GroupDocs.Viewer](https://releases.groupdocs.com/viewer/java/)
- **Acquista licenza:** [Buy a License](https://purchase.groupdocs.com/buy)
- **Prova gratuita:** [Start Your Free Trial](https://releases.groupdocs.com/viewer/java/)
- **Licenza temporanea:** [Request Here](https://purchase.groupdocs.com/temporary-license/)
- **Forum di supporto:** [Join the Discussion](https://forum.groupdocs.com/c/viewer/9)

---

**Ultimo aggiornamento:** 2026-03-05  
**Testato con:** GroupDocs.Viewer 25.2 per Java  
**Autore:** GroupDocs