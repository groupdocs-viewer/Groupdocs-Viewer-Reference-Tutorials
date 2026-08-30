---
date: '2026-08-30'
description: Scopri come convertire DWG in PNG, impostare il colore di sfondo in Java
  e personalizzare le dimensioni dell'immagine con GroupDocs.Viewer for Java.
keywords:
- convert dwg to png
- set background color java
- change cad background color
- java convert cad png
lastmod: '2026-08-30'
og_description: Converti DWG in PNG usando GroupDocs.Viewer for Java impostando una
  larghezza personalizzata dell'immagine e il colore di sfondo. Questa guida fornisce
  configurazione passo‑passo, snippet di codice e suggerimenti per la risoluzione
  dei problemi.
og_image_alt: 'Guide: converting DWG to PNG with custom size and background color
  using GroupDocs.Viewer for Java'
og_title: Converti DWG in PNG con dimensione personalizzata e colore di sfondo in
  Java
schemas:
- author: GroupDocs
  dateModified: '2026-08-30'
  description: Learn how to convert DWG to PNG, set background color Java, and customize
    image size with GroupDocs.Viewer for Java.
  headline: How to convert DWG to PNG with custom size & background color using GroupDocs.Viewer
    for Java
  type: TechArticle
- questions:
  - answer: Yes, GroupDocs.Viewer supports DXF, DWF, and several additional CAD formats.
    question: Can I render other CAD formats besides DWG?
  - answer: Instantiate a new `Color` with `new Color(123, 45, 67)` and pass it to
      `setBackgroundColor`.
    question: How do I use a custom RGB color instead of a predefined constant?
  - answer: You can specify layout or layer options via `CadOptions` before calling
      `viewer.view`.
    question: Is it possible to render only a specific layout or layer?
  - answer: Set the background color to `new Color(0,0,0,0)` for full transparency
      if the output format supports it.
    question: Does the library support transparent backgrounds?
  - answer: The tutorial uses version 25.2, but newer releases retain the same API
      surface.
    question: What version of GroupDocs.Viewer is required?
  type: FAQPage
tags:
- convert dwg
- GroupDocs.Viewer
- Java CAD rendering
- custom PNG output
title: Come convertire DWG in PNG con dimensione personalizzata e colore di sfondo
  usando GroupDocs.Viewer for Java
type: docs
url: /it/java/advanced-rendering/render-cad-drawings-custom-png-groupdocs-java/
weight: 1
---

# Come convertire DWG in PNG con dimensione personalizzata e colore di sfondo usando GroupDocs.Viewer per Java

In questo tutorial imparerai **come convertire DWG in PNG** controllando le dimensioni dell'output e il colore di sfondo, usando GroupDocs.Viewer per Java. Che tu debba incorporare disegni CAD in un report, generare miniature per un portale web o automatizzare il rendering batch, i passaggi seguenti ti danno il pieno controllo sull'aspetto visivo di ogni file PNG.

## Risposte rapide
- **Cosa significa “convertire DWG in PNG”?** È il processo di trasformare un file CAD DWG in un'immagine PNG tramite codice, preservando i dettagli vettoriali come pixel raster.  
- **Posso impostare una larghezza personalizzata?** Sì – chiama `CadOptions.forRenderingByWidth(int width)` per definire la larghezza in pixel esatta di cui hai bisogno.  
- **Come cambio il colore di sfondo?** Usa `cadOptions.setBackgroundColor(Color.YOUR_COLOR)` prima del rendering.  
- **Quale libreria è necessaria?** GroupDocs.Viewer per Java (versione 25.2 o successiva).  
- **È necessaria una licenza?** Una licenza temporanea o completa rimuove i limiti di valutazione e abilita il rendering illimitato.

![Rendi i disegni CAD in PNG con dimensione personalizzata e colore di sfondo con GroupDocs.Viewer per Java](/viewer/advanced-rendering/render-cad-drawings-as-png-with-custom-size-background-color-java.png)

## Cos'è GroupDocs.Viewer per Java?
GroupDocs.Viewer per Java è un'API lato server che rende più di 150 formati di file—compresi i file CAD—in immagini, PDF o HTML. Funziona senza richiedere software di terze parti come AutoCAD, rendendola ideale per pipeline automatizzate.

## Come convertire DWG in PNG con dimensione personalizzata e colore di sfondo?
Carica il file DWG con un'istanza `Viewer`, configura `CadOptions` per la larghezza desiderata e il colore di sfondo, e infine chiama `viewer.view` con `PngViewOptions`. Questo flusso a tre passaggi gestisce I/O del file, rendering e denominazione dell'output in un'unica operazione a basso consumo di memoria.

`Viewer` è la classe principale che carica un documento ed esegue il rendering.  
`CadOptions` configura le impostazioni specifiche per CAD come larghezza immagine e colore di sfondo.  
`PngViewOptions` definisce il formato di output PNG e il modello di denominazione per le pagine renderizzate.

Ora puoi renderizzare qualsiasi disegno DWG in un PNG con esattamente la larghezza che specifichi, e puoi scegliere qualsiasi colore solido (o trasparente) di sfondo per abbinare il tuo brand o tema UI.

## Perché impostare un colore di sfondo personalizzato?
Impostare un colore di sfondo garantisce che il PNG renderizzato si integri perfettamente con gli elementi UI circostanti, evita margini bianchi indesiderati e può evidenziare dettagli del disegno che altrimenti andrebbero persi su una tela bianca predefinita. GroupDocs.Viewer supporta qualsiasi `java.awt.Color`, inclusi valori RGB personalizzati, offrendoti un controllo pixel‑perfect.

`java.awt.Color` rappresenta un valore di colore usato per il rendering degli sfondi.

## Prerequisiti

- **Java Development Kit (JDK) 8+** – l'API è destinata a Java 8 e versioni successive.  
- **Maven** – per la gestione delle dipendenze.  
- **IDE** – IntelliJ IDEA, Eclipse o qualsiasi editor tu preferisca.  
- **Conoscenza di base della gestione dei file Java** – per leggere i file DWG sorgente e scrivere gli output PNG.

## Configurazione di GroupDocs.Viewer per Java
Aggiungi il repository GroupDocs e la dipendenza Viewer al tuo `pom.xml` Maven:

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
Ottieni una chiave di licenza temporanea o completa dal portale GroupDocs e posiziona il file `license.lic` nella cartella delle risorse del tuo progetto. Questo rimuove il limite di valutazione di 20 pagine e sblocca il rendering a piena risoluzione.

### Inizializzazione e configurazione di base
Crea un'istanza `Viewer` che punti alla cartella contenente i tuoi file DWG:

```java
import com.groupdocs.viewer.Viewer;
import java.nio.file.Path;

Path documentPath = Path.of("YOUR_DOCUMENT_DIRECTORY/SAMPLE_DWG_WITH_LAYOUTS_AND_LAYERS");
try (Viewer viewer = new Viewer(documentPath.toString())) {
    // Rendering operations go here
}
```

## Funzione 1: rendering di disegni CAD con dimensione immagine personalizzata e colore di sfondo

### Come cambiare il colore di sfondo CAD
Per cambiare il colore di sfondo CAD, configura l'oggetto `CadOptions` prima del rendering. Imposta la larghezza desiderata con `forRenderingByWidth` e applica il nuovo sfondo usando `setBackgroundColor`. Il viewer genera quindi immagini PNG che riflettono il colore specificato, garantendo uno stile visivo coerente in tutti i file di output.

#### Implementazione passo‑passo

##### Importare i pacchetti richiesti
```java
import com.groupdocs.viewer.Viewer;
import com.groupdocs.viewer.options.CadOptions;
import com.groupdocs.viewer.options.PngViewOptions;
import java.nio.file.Path;
import java.awt.Color;
```

##### Configurare la directory di output e il formato del percorso file
```java
Path outputDirectory = Path.of("YOUR_OUTPUT_DIRECTORY/SetImageBackgroundColor");
Path pageFilePathFormat = outputDirectory.resolve("page_{0}.png");
```

##### Inizializzare il viewer con opzioni di rendering personalizzate
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
- `PngViewOptions` – definisce il formato di output PNG e il modello di denominazione.  
- `forRenderingByWidth(int width)` – forza il renderer a produrre un'immagine la cui larghezza corrisponde al valore pixel fornito; l'altezza è scalata proporzionalmente.  
- `setBackgroundColor(Color color)` – sovrascrive la tela bianca predefinita con il colore scelto, migliorando la coerenza visiva tra le risorse generate.

#### Suggerimenti per la risoluzione dei problemi
- Assicurati che la cartella di output esista; usa `Files.createDirectories(outputDir)` se non esiste.  
- Verifica che il percorso del file di input sia corretto e che l'applicazione abbia i permessi di lettura.  

## Funzione 2: impostare il colore di sfondo nelle opzioni di rendering

### Come impostare il colore di sfondo PNG
Impostare il colore di sfondo PNG consiste nel creare un'istanza `Color` e assegnarla a `CadOptions` prima del rendering. Questo garantisce che ogni PNG generato utilizzi lo sfondo specificato, in linea con le linee guida del tuo brand o tema UI. Puoi usare costanti predefinite o definire valori RGB personalizzati per un controllo preciso.

`java.awt.Color` rappresenta un valore di colore usato per il rendering degli sfondi.

#### Implementazione passo‑passo

##### Importare i pacchetti richiesti
```java
import com.groupdocs.viewer.Viewer;
import com.groupdocs.viewer.options.CadOptions;
import com.groupdocs.viewer.options.PngViewOptions;
import java.nio.file.Path;
import java.awt.Color;
```

##### Configurare le opzioni di rendering con colore di sfondo
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

**Opzioni di configurazione chiave**  
- Regola `forRenderingByWidth(int width)` per diverse dimensioni, ad esempio 800 px per miniature web o 1920 px per stampe ad alta risoluzione.  
- Usa qualsiasi costante `Color` predefinita (es. `Color.LIGHT_GRAY`) o crea un'istanza personalizzata con `new Color(r, g, b)` per un branding preciso.  

## Applicazioni pratiche

### 1. Documentazione ingegneristica
Il rendering personalizzato garantisce che ogni disegno rispetti la guida di stile aziendale, eliminando la necessità di modifiche manuali delle immagini dopo l'esportazione.

### 2. Visualizzazione architettonica
Presenta i progetti con uno sfondo che corrisponde a presentazioni o portali client‑facing, migliorando la coesione visiva.

### 3. Prototipazione manifatturiera
Genera PNG per flussi di lavoro di prototipazione rapida dove gli strumenti a valle si aspettano una dimensione immagine e uno sfondo specifici.

### Possibilità di integrazione
Accoppia questo pipeline di rendering con un sistema di gestione documentale (es. SharePoint) per generare automaticamente immagini di anteprima ogni volta che un file DWG viene caricato.

## Considerazioni sulle prestazioni

### Ottimizzazione delle prestazioni
- **Elaborazione batch:** Scorri una directory di file DWG e renderizza ciascuno in sequenza per amortizzare i costi di avvio della JVM.  
- **Gestione delle risorse:** Per disegni di grandi dimensioni (500+ pagine), aumenta l'heap JVM (`-Xmx2g`) o elabora i file in batch più piccoli per evitare errori di out‑of‑memory.

### Linee guida sull'uso delle risorse
Monitora CPU e memoria con strumenti come VisualVM; rilascia le istanze `Viewer` prontamente usando try‑with‑resources.

### Best practice per la gestione della memoria Java
- Usa try‑with‑resources (come mostrato) per chiudere automaticamente `Viewer`.  
- Evita di mantenere oggetti `Path` di grandi dimensioni oltre il loro utilizzo immediato.  

## Problemi comuni e soluzioni

| Problema | Soluzione |
|----------|-----------|
| Cartella di output non trovata | Crea la directory in anticipo o aggiungi `Files.createDirectories(outputDirectory);` |
| Immagine vuota | Assicurati che `cadOptions.setBackgroundColor` sia chiamato dopo `forRenderingByWidth`. |
| Errori di out‑of‑memory | Aumenta l'opzione JVM `-Xmx` o elabora i file in batch più piccoli. |

## Domande frequenti

**D: Posso renderizzare altri formati CAD oltre a DWG?**  
R: Sì, GroupDocs.Viewer supporta DXF, DWF e diversi altri formati CAD.

**D: Come utilizzo un colore RGB personalizzato invece di una costante predefinita?**  
R: Istanzia un nuovo `Color` con `new Color(123, 45, 67)` e passalo a `setBackgroundColor`.

**D: È possibile renderizzare solo un layout o layer specifico?**  
R: Puoi specificare opzioni di layout o layer tramite `CadOptions` prima di chiamare `viewer.view`.

**D: La libreria supporta sfondi trasparenti?**  
R: Imposta il colore di sfondo su `new Color(0,0,0,0)` per trasparenza completa se il formato di output lo supporta.

**D: Quale versione di GroupDocs.Viewer è richiesta?**  
R: Il tutorial utilizza la versione 25.2, ma le versioni più recenti mantengono la stessa API.

**Ultimo aggiornamento:** 2026-08-30  
**Testato con:** GroupDocs.Viewer 25.2 per Java  
**Autore:** GroupDocs

## Tutorial correlati

- [groupdocs viewer dwg – Come rendere disegni CAD specifici in Java usando GroupDocs.Viewer](/viewer/java/rendering-basics/render-cad-groupdocs-viewer-java/)
- [Render CAD Layers Java con GroupDocs.Viewer – Guida completa](/viewer/java/advanced-rendering/render-cad-layers-java-groupdocs-viewer/)
- [Come convertire PDF in HTML e ottimizzare la qualità dell'immagine in Java con GroupDocs.Viewer](/viewer/java/advanced-rendering/adjust-image-quality-groupdocs-viewer-java/)