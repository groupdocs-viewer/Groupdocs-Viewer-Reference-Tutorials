---
date: '2026-01-08'
description: Scopri come rendere i disegni CAD in immagini PNG di alta qualità utilizzando
  dimensioni personalizzate e colori di sfondo con GroupDocs.Viewer per Java.
keywords:
- render CAD drawings PNG
- GroupDocs.Viewer for Java setup
- custom image size and background color
title: Come rendere i disegni CAD in PNG con dimensioni e colore di sfondo personalizzati
  usando GroupDocs.Viewer per Java
type: docs
url: /it/java/advanced-rendering/render-cad-drawings-custom-png-groupdocs-java/
weight: 1
---

# Come renderizzare disegni CAD in PNG con dimensioni personalizzate e colore di sfondo usando GroupDocs.Viewer per Java

Hai difficoltà a convertire i tuoi disegni CAD in immagini ad alta qualità mantenendo dimensioni specifiche e estetica? In questo tutorial mostreremo **come renderizzare CAD** in file PNG con dimensioni e colore di sfondo personalizzati, così potrai ottenere esattamente l'aspetto necessario per report, presentazioni o anteprime web.

## Risposte Rapide
- **Cosa significa “how to render CAD”?** Si riferisce alla conversione di file CAD (ad es., DWG) in formati immagine come PNG tramite codice.  
- **Posso impostare una larghezza personalizzata?** Sì – usa `CadOptions.forRenderingByWidth(int width)`.  
- **Come cambio lo sfondo?** Chiama `cadOptions.setBackgroundColor(Color.YOUR_COLOR)`.  
- **Quale libreria è necessaria?** GroupDocs.Viewer per Java (versione 25.2 o successive).  
- **È necessaria una licenza?** Una licenza temporanea o acquistata rimuove i limiti di valutazione.

![Renderizza disegni CAD in PNG con dimensioni personalizzate e colore di sfondo con GroupDocs.Viewer per Java](/viewer/advanced-rendering/render-cad-drawings-as-png-with-custom-size-background-color-java.png)

## Come renderizzare disegni CAD – Panoramica
Questa sezione approfondisce l'obiettivo principale: **come renderizzare CAD** in file PNG controllando dimensione e sfondo. Ti guideremo attraverso l'intera configurazione, gli snippet di codice e consigli pratici.

## Cosa imparerai
- Configurare GroupDocs.Viewer per Java nel tuo progetto  
- **Convertire DWG in PNG** con dimensioni personalizzate  
- **Impostare colore di sfondo PNG** durante il rendering per un aspetto curato  
- Scenari reali in cui il rendering personalizzato aggiunge valore  

## Prerequisiti

### Librerie e dipendenze richieste
- Java Development Kit (JDK) 8+  
- Maven per la gestione delle dipendenze  

### Requisiti di configurazione dell'ambiente
- IDE come IntelliJ IDEA o Eclipse  
- Conoscenza di base di Java  

### Prerequisiti di conoscenza
- Familiarità con la gestione dei file in Java  

## Configurare GroupDocs.Viewer per Java
Aggiungi il repository GroupDocs e la dipendenza al tuo `pom.xml` Maven:

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
Ottieni una licenza temporanea o completa per rimuovere le limitazioni di valutazione.

### Inizializzazione e configurazione di base
Crea un'istanza `Viewer` che punti al tuo file CAD:

```java
import com.groupdocs.viewer.Viewer;
import java.nio.file.Path;

Path documentPath = Path.of("YOUR_DOCUMENT_DIRECTORY/SAMPLE_DWG_WITH_LAYOUTS_AND_LAYERS");
try (Viewer viewer = new Viewer(documentPath.toString())) {
    // Rendering operations go here
}
```

## Guida all'implementazione

### Funzione 1: Rendering di disegni CAD con dimensione immagine personalizzata e colore di sfondo

#### Panoramica
Questa funzione ti consente di **convertire DWG in PNG** specificando la larghezza dell'immagine e la tonalità dello sfondo.

#### Implementazione passo‑per‑passo

##### Importa i pacchetti necessari
```java
import com.groupdocs.viewer.Viewer;
import com.groupdocs.viewer.options.CadOptions;
import com.groupdocs.viewer.options.PngViewOptions;
import java.nio.file.Path;
import java.awt.Color;
```

##### Configura la directory di output e il formato del percorso file
```java
Path outputDirectory = Path.of("YOUR_OUTPUT_DIRECTORY/SetImageBackgroundColor");
Path pageFilePathFormat = outputDirectory.resolve("page_{0}.png");
```

##### Inizializza Viewer con opzioni di rendering personalizzate
```java
try (Viewer viewer = new Viewer("YOUR_DOCUMENT_DIRECTORY/SAMPLE_DWG_WITH_LAYOUTS_AND_LAYERS")) {
    PngViewOptions options = new PngViewOptions(pageFilePathFormat);
    
    // Specify the width for rendering
    CadOptions cadOptions = CadOptions.forRenderingByWidth(800);
    cadOptions.setBackgroundColor(Color.GREEN);
    
    options.setCadOptions(cadOptions);

    viewer.view(options);
}
```

**Spiegazione dei parametri**  
- `PngViewOptions` – definisce il formato di output e la denominazione.  
- `forRenderingByWidth(int width)` – imposta la larghezza personalizzata dell'immagine.  
- `setBackgroundColor(Color color)` – **applica il rendering del colore di sfondo** al PNG.

#### Suggerimenti per la risoluzione dei problemi
- Verifica che la cartella di output esista; creala se necessario.  
- Controlla nuovamente il percorso del file di input e le autorizzazioni.  

### Funzione 2: Impostare il colore di sfondo nelle opzioni di rendering

#### Panoramica
Qui ci concentriamo su **impostare colore di sfondo PNG** per migliorare la coerenza visiva.

#### Implementazione passo‑per‑passo

##### Importa i pacchetti necessari
```java
import com.groupdocs.viewer.Viewer;
import com.groupdocs.viewer.options.CadOptions;
import com.groupdocs.viewer.options.PngViewOptions;
import java.nio.file.Path;
import java.awt.Color;
```

##### Configura le opzioni di rendering con colore di sfondo
```java
Path outputDirectory = Path.of("YOUR_OUTPUT_DIRECTORY/SetImageBackgroundColor");
Path pageFilePathFormat = outputDirectory.resolve("page_{0}.png");

try (Viewer viewer = new Viewer("YOUR_DOCUMENT_DIRECTORY/SAMPLE_DWG_WITH_LAYOUTS_AND_LAYERS")) {
    PngViewOptions options = new PngViewOptions(pageFilePathFormat);
    
    CadOptions cadOptions = CadOptions.forRenderingByWidth(800);
    cadOptions.setBackgroundColor(Color.GREEN);
    
    options.setCadOptions(cadOptions);
    
    viewer.view(options);
}
```

**Opzioni chiave di configurazione**  
- Regola `forRenderingByWidth(int width)` per diverse dimensioni.  
- Usa qualsiasi costante `Color` o un `new Color(r,g,b)` personalizzato per sfondi su misura.  

## Applicazioni pratiche

### 1. Documentazione ingegneristica
Il rendering personalizzato garantisce che i disegni ingegneristici rispettino le linee guida di stile aziendali.

### 2. Visualizzazione architettonica
Presenta i progetti con uno sfondo pulito che corrisponde alle presentazioni.

### 3. Prototipazione manifatturiera
Genera PNG precisi per flussi di lavoro di prototipazione rapida.

### Possibilità di integrazione
Combina questa pipeline di rendering con sistemi di gestione documentale per automatizzare la generazione di asset visivi.

## Considerazioni sulle prestazioni

### Ottimizzazione delle prestazioni
- **Elaborazione batch:** Renderizza più file CAD in un ciclo.  
- **Gestione delle risorse:** Regola la dimensione dell'heap JVM per disegni di grandi dimensioni.

### Linee guida sull'uso delle risorse
Monitora CPU e memoria; rilascia prontamente le istanze di `Viewer`.

### Best practice per la gestione della memoria Java
- Usa try‑with‑resources (come mostrato) per chiudere automaticamente `Viewer`.  
- Evita di mantenere oggetti `Path` di grandi dimensioni più a lungo del necessario.

## Problemi comuni e soluzioni

| Problema | Soluzione |
|----------|-----------|
| **Cartella di output non trovata** | Crea la directory in anticipo o aggiungi `Files.createDirectories(outputDirectory);` |
| **Immagine vuota** | Assicurati che `cadOptions.setBackgroundColor` sia impostato dopo `forRenderingByWidth`. |
| **Errori di out‑of‑memory** | Aumenta l'opzione JVM `-Xmx` o elabora i file in batch più piccoli. |

## Domande frequenti

**Q: Posso renderizzare altri formati CAD oltre a DWG?**  
A: Sì, GroupDocs.Viewer supporta DXF, DWF e diversi altri tipi di file CAD.

**Q: Come posso usare un colore RGB personalizzato invece di una costante predefinita?**  
A: Crea una nuova istanza `Color`, ad esempio `new Color(123, 45, 67)` e passala a `setBackgroundColor`.

**Q: È possibile renderizzare solo un layout o un layer specifico?**  
A: Puoi specificare le opzioni di layout o layer tramite `CadOptions` prima di chiamare `viewer.view`.

**Q: La libreria supporta sfondi trasparenti?**  
A: Imposta il colore di sfondo a `new Color(0,0,0,0)` per trasparenza totale se il formato di destinazione lo supporta.

**Q: Quale versione di GroupDocs.Viewer è richiesta?**  
A: Il tutorial utilizza la versione 25.2, ma le versioni più recenti mantengono la stessa API.

## Conclusione
Ora sai **come renderizzare CAD** in file PNG con dimensioni e colori di sfondo personalizzati usando GroupDocs.Viewer per Java. Applica queste tecniche per creare asset visivi dall'aspetto professionale per flussi di lavoro di ingegneria, architettura o manifattura.

### Prossimi passi
- Sperimenta con diverse larghezze e colori dell'immagine.  
- Integra il codice di rendering in un servizio di elaborazione batch.  
- Esplora opzioni aggiuntive di Viewer come la conversione PDF o il rendering multi‑pagina.

---

**Ultimo aggiornamento:** 2026-01-08  
**Testato con:** GroupDocs.Viewer 25.2 per Java  
**Autore:** GroupDocs