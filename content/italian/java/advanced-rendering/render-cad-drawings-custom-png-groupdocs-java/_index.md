---
date: '2026-03-16'
description: Scopri come convertire DWG in PNG con dimensioni personalizzate e colore
  di sfondo usando GroupDocs.Viewer per Java.
keywords:
- render CAD drawings PNG
- GroupDocs.Viewer for Java setup
- custom image size and background color
title: Come convertire DWG in PNG con dimensioni personalizzate e colore di sfondo
  usando GroupDocs.Viewer per Java
type: docs
url: /it/java/advanced-rendering/render-cad-drawings-custom-png-groupdocs-java/
weight: 1
---

 Java -> "**Testato con:** GroupDocs.Viewer 25.2 per Java"

**Author:** GroupDocs -> "**Autore:** GroupDocs"

Now produce final markdown with translations, preserving placeholders.

Check for any remaining English text: "step‑by‑step", "step‑by‑step" maybe keep as is? It's English phrase; but we can translate "Passo‑per‑Passo". Already did.

Also "Quick Answers" -> "Risposte Rapide". Keep heading.

Make sure to keep code block placeholders unchanged.

Now produce final content.# Come Convertire DWG in PNG con Dimensione Personalizzata e Colore di Sfondo Utilizzando GroupDocs.Viewer per Java

Se desideri **convertire DWG in PNG** mantenendo il pieno controllo sulle dimensioni dell'immagine e sullo stile dello sfondo, sei nel posto giusto. In questo tutorial ti guideremo attraverso il rendering dei file CAD come PNG, la personalizzazione della larghezza e la modifica del colore di sfondo affinché l'output corrisponda ai requisiti del tuo report, presentazione o anteprima web.

## Risposte Rapide
- **Cosa significa “convertire DWG in PNG”?** È il processo di trasformare un file CAD DWG in un'immagine PNG usando codice.  
- **Posso impostare una larghezza personalizzata?** Sì – usa `CadOptions.forRenderingByWidth(int width)`.  
- **Come cambio il colore di sfondo?** Chiama `cadOptions.setBackgroundColor(Color.YOUR_COLOR)`.  
- **Quale libreria è necessaria?** GroupDocs.Viewer per Java (versione 25.2 o successiva).  
- **Ho bisogno di una licenza?** Una licenza temporanea o acquistata rimuove i limiti di valutazione.

![Renderizza Disegni CAD come PNG con Dimensione Personalizzata e Colore di Sfondo con GroupDocs.Viewer per Java](/viewer/advanced-rendering/render-cad-drawings-as-png-with-custom-size-background-color-java.png)

## Come Convertire DWG in PNG – Panoramica
In questa sezione approfondiamo l'obiettivo principale: **come convertire DWG in PNG** controllando dimensione e sfondo. Vedrai la configurazione completa, il codice esatto di cui hai bisogno e consigli pratici per evitare errori comuni.

## Cosa Imparerai
- Configurare GroupDocs.Viewer per Java in un progetto Maven  
- **Convertire DWG in PNG** con dimensioni personalizzate  
- **Cambiare il colore di sfondo CAD** durante il rendering per un aspetto curato  
- Scenari reali in cui il rendering personalizzato aggiunge valore  

## Prerequisiti

### Librerie e Dipendenze Richieste
- Java Development Kit (JDK) 8+  
- Maven per la gestione delle dipendenze  

### Requisiti di Configurazione dell'Ambiente
- IDE come IntelliJ IDEA o Eclipse  
- Conoscenza di base di Java  

### Prerequisiti di Conoscenza
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

### Acquisizione della Licenza
Ottieni una licenza temporanea o completa per rimuovere le restrizioni di valutazione.

### Inizializzazione e Configurazione di Base
Crea un'istanza `Viewer` che punti al tuo file CAD:

```java
import com.groupdocs.viewer.Viewer;
import java.nio.file.Path;

Path documentPath = Path.of("YOUR_DOCUMENT_DIRECTORY/SAMPLE_DWG_WITH_LAYOUTS_AND_LAYERS");
try (Viewer viewer = new Viewer(documentPath.toString())) {
    // Rendering operations go here
}
```

## Funzionalità 1: Rendering di Disegni CAD con Dimensione Immagine Personalizzata e Colore di Sfondo

### Come Cambiare il Colore di Sfondo CAD
Questa funzionalità ti consente di **convertire DWG in PNG** specificando una larghezza personalizzata e applicando una nuova tonalità di sfondo.

#### Implementazione Passo‑per‑Passo

##### Importa i Pacchetti Necessari
```java
import com.groupdocs.viewer.Viewer;
import com.groupdocs.viewer.options.CadOptions;
import com.groupdocs.viewer.options.PngViewOptions;
import java.nio.file.Path;
import java.awt.Color;
```

##### Configura la Directory di Output e il Formato del Percorso del File
```java
Path outputDirectory = Path.of("YOUR_OUTPUT_DIRECTORY/SetImageBackgroundColor");
Path pageFilePathFormat = outputDirectory.resolve("page_{0}.png");
```

##### Inizializza Viewer con Opzioni di Rendering Personalizzate
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

**Spiegazione dei Parametri**  
- `PngViewOptions` – definisce il formato di output e la denominazione.  
- `forRenderingByWidth(int width)` – imposta la larghezza personalizzata dell'immagine.  
- `setBackgroundColor(Color color)` – **imposta il colore di sfondo PNG** per migliorare la coerenza visiva.

#### Suggerimenti per la Risoluzione dei Problemi
- Verifica che la cartella di output esista; creala se necessario.  
- Controlla nuovamente il percorso del file di input e i permessi.  

## Funzionalità 2: Impostare il Colore di Sfondo nelle Opzioni di Rendering

### Come Impostare il Colore di Sfondo PNG
Qui ci concentriamo sull'opzione **set background color PNG** per garantire che ogni immagine renderizzata corrisponda alla palette del tuo brand.

#### Implementazione Passo‑per‑Passo

##### Importa i Pacchetti Necessari
```java
import com.groupdocs.viewer.Viewer;
import com.groupdocs.viewer.options.CadOptions;
import com.groupdocs.viewer.options.PngViewOptions;
import java.nio.file.Path;
import java.awt.Color;
```

##### Configura le Opzioni di Rendering con il Colore di Sfondo
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

**Opzioni di Configurazione Chiave**  
- Regola `forRenderingByWidth(int width)` per diverse dimensioni.  
- Usa qualsiasi costante `Color` o un `new Color(r,g,b)` personalizzato per sfondi su misura.  

## Applicazioni Pratiche

### 1. Documentazione Ingegneristica
Il rendering personalizzato garantisce che i disegni ingegneristici rispettino le linee guida di stile aziendali.

### 2. Visualizzazione Architettonica
Presenta i progetti con uno sfondo pulito che corrisponde alle presentazioni.

### 3. Prototipazione di Produzione
Genera PNG precisi per flussi di lavoro di prototipazione rapida.

### Possibilità di Integrazione
Combina questa pipeline di rendering con sistemi di gestione documentale per automatizzare la generazione di risorse visive.

## Considerazioni sulle Prestazioni

### Ottimizzazione delle Prestazioni
- **Elaborazione Batch:** Renderizza più file CAD in un ciclo.  
- **Gestione delle Risorse:** Regola la dimensione dell'heap JVM per disegni di grandi dimensioni.

### Linee Guida sull'Uso delle Risorse
Monitora CPU e memoria; rilascia prontamente le istanze `Viewer`.

### Best Practice per la Gestione della Memoria Java
- Usa try‑with‑resources (come mostrato) per chiudere automaticamente `Viewer`.  
- Evita di mantenere oggetti `Path` di grandi dimensioni più a lungo del necessario.

## Problemi Comuni e Soluzioni
| Problema | Soluzione |
|----------|-----------|
| **Cartella di output non trovata** | Crea la directory in anticipo o aggiungi `Files.createDirectories(outputDirectory);` |
| **Immagine vuota** | Assicurati che `cadOptions.setBackgroundColor` sia impostato dopo `forRenderingByWidth`. |
| **Errori di out‑of‑memory** | Aumenta l'opzione JVM `-Xmx` o elabora i file in batch più piccoli. |

## Domande Frequenti

**D: Posso renderizzare altri formati CAD oltre a DWG?**  
R: Sì, GroupDocs.Viewer supporta DXF, DWF e diversi altri tipi di file CAD.

**D: Come utilizzo un colore RGB personalizzato invece di una costante predefinita?**  
R: Crea una nuova istanza `Color`, ad esempio `new Color(123, 45, 67)`, e passala a `setBackgroundColor`.

**D: È possibile renderizzare solo un layout o layer specifico?**  
R: Puoi specificare le opzioni di layout o layer tramite `CadOptions` prima di chiamare `viewer.view`.

**D: La libreria supporta sfondi trasparenti?**  
R: Imposta il colore di sfondo su `new Color(0,0,0,0)` per trasparenza completa se il formato di destinazione lo supporta.

**D: Quale versione di GroupDocs.Viewer è necessaria?**  
R: Il tutorial utilizza la versione 25.2, ma le versioni più recenti mantengono la stessa API.

---

**Ultimo aggiornamento:** 2026-03-16  
**Testato con:** GroupDocs.Viewer 25.2 per Java  
**Autore:** GroupDocs