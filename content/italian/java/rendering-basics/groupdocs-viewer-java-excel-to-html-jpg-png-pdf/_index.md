---
"date": "2025-04-24"
"description": "Scopri come convertire file Excel in HTML, JPG, PNG e PDF utilizzando GroupDocs.Viewer Java. Questa guida illustra la configurazione, le opzioni di rendering e le applicazioni pratiche."
"title": "Come usare GroupDocs.Viewer Java per la conversione da Excel a HTML/JPG/PNG/PDF&#58; una guida passo passo"
"url": "/it/java/rendering-basics/groupdocs-viewer-java-excel-to-html-jpg-png-pdf/"
"weight": 1
---

# Come utilizzare GroupDocs.Viewer Java per la conversione da Excel a HTML/JPG/PNG/PDF: una guida passo passo

## Introduzione

Trasformare i dati di un foglio di calcolo in vari formati come HTML, JPG, PNG o PDF, mantenendo al contempo dettagli cruciali come le intestazioni di riga e colonna, è essenziale in molti scenari. Che si tratti di generare report, condividere informazioni con gli stakeholder o integrare fogli di calcolo in applicazioni web, la conversione di fogli Excel può essere un requisito fondamentale. Questa guida illustra come GroupDocs.Viewer Java renda queste attività semplici e precise.

**Cosa imparerai:**
- Impostazione e utilizzo di GroupDocs.Viewer per Java
- Rendering di file Excel nei formati HTML, JPG, PNG e PDF
- Configurazione delle opzioni per includere intestazioni di riga e di colonna nei tuoi output
- Applicazioni pratiche dei documenti resi

Cominciamo con i prerequisiti necessari prima di passare all'implementazione.

## Prerequisiti

Prima di eseguire il rendering dei fogli di calcolo con GroupDocs.Viewer Java, assicurati di avere:

### Librerie e dipendenze richieste

Configura GroupDocs.Viewer per Java utilizzando Maven. Ecco come includerlo nel tuo progetto:

**Configurazione Maven:**
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

### Configurazione dell'ambiente
- Assicuratevi di aver installato Java Development Kit (JDK).
- Per una maggiore praticità di sviluppo, utilizzare un IDE come IntelliJ IDEA o Eclipse.

### Prerequisiti di conoscenza
- Familiarità con la programmazione Java
- Conoscenza di base di Maven per la gestione delle dipendenze

Una volta soddisfatti questi prerequisiti, procediamo alla configurazione di GroupDocs.Viewer per Java e iniziamo a implementarne le funzionalità.

## Impostazione di GroupDocs.Viewer per Java

GroupDocs.Viewer per Java è una libreria versatile che consente di visualizzare documenti in vari formati. Ecco come iniziare:

### Informazioni sull'installazione
Come accennato, usa Maven per aggiungere GroupDocs.Viewer come dipendenza nel tuo progetto `pom.xml` file.

### Fasi di acquisizione della licenza
1. **Prova gratuita:** Scarica la versione di prova da [Prova gratuita di GroupDocs](https://releases.groupdocs.com/viewer/java/).
2. **Licenza temporanea:** Acquisisci una licenza temporanea per ulteriori funzionalità da [Licenza temporanea GroupDocs](https://purchase.groupdocs.com/temporary-license/).
3. **Acquistare:** Per un accesso e un supporto completi, acquista una licenza su [Acquisto GroupDocs](https://purchase.groupdocs.com/buy).

### Inizializzazione di base
Una volta installato, puoi inizializzare GroupDocs.Viewer con:
```java
import com.groupdocs.viewer.Viewer;

public class ViewerSetup {
    public static void main(String[] args) {
        try (Viewer viewer = new Viewer("Sample.xlsx")) {
            // Il tuo codice qui per utilizzare il visualizzatore
        }
    }
}
```
In questo modo si inizializza l'ambiente, predisponendo l'utente al rendering dei documenti.

## Guida all'implementazione

Analizziamo nel dettaglio ciascuna funzionalità e scopriamo come implementarle.

### Trasforma il foglio di calcolo in HTML
**Panoramica:** Converti i fogli Excel in formato HTML mantenendo le intestazioni di righe e colonne per presentazioni o report Web.

#### Implementazione passo dopo passo:
##### 1. Importare le librerie richieste
```java
import com.groupdocs.viewer.Viewer;
import com.groupdocs.viewer.options.HtmlViewOptions;
```
##### 2. Imposta la directory di output
Definisci dove verranno archiviati i file renderizzati.
```java
Path outputDirectory = Paths.get("YOUR_DOCUMENT_DIRECTORY", "RenderRowAndColumnHeadings");
Path pageFilePathFormat = outputDirectory.resolve("page_{0}.html");
```
##### 3. Inizializza il visualizzatore e configura le opzioni
Utilizzare GroupDocs.Viewer per visualizzare il documento:
```java
try (Viewer viewer = new Viewer(Paths.get("Sample.xlsx"))) {
    HtmlViewOptions options = HtmlViewOptions.forEmbeddedResources(pageFilePathFormat);
    
    // Abilita il rendering delle intestazioni di righe e colonne nel foglio di calcolo.
    options.getSpreadsheetOptions().setRenderHeadings(true);

    viewer.view(options, 1, 2, 3); // Visualizza le pagine da 1 a 3.
}
```
**Spiegazione:** IL `HtmlViewOptions` la classe viene utilizzata per configurare l'output HTML. Impostazione `setRenderHeadings(true)` assicura che le intestazioni di riga e di colonna siano visibili nel codice HTML renderizzato.

### Trasforma il foglio di calcolo in JPG
**Panoramica:** Trasforma i fogli Excel in file immagine di alta qualità (JPG), includendo intestazioni di righe e colonne, ideali per presentazioni visive o stampe.

#### Implementazione passo dopo passo:
##### 1. Importare le librerie richieste
```java
import com.groupdocs.viewer.Viewer;
import com.groupdocs.viewer.options.JpgViewOptions;
```
##### 2. Imposta la directory di output
```java
Path outputDirectory = Paths.get("YOUR_DOCUMENT_DIRECTORY", "RenderRowAndColumnHeadings");
Path pageFilePathFormat = outputDirectory.resolve("page_{0}.jpg");
```
##### 3. Inizializza il visualizzatore e configura le opzioni
```java
try (Viewer viewer = new Viewer(Paths.get("Sample.xlsx"))) {
    JpgViewOptions options = new JpgViewOptions(pageFilePathFormat);
    
    // Abilita il rendering delle intestazioni di righe e colonne nel foglio di calcolo.
    options.getSpreadsheetOptions().setRenderHeadings(true);

    viewer.view(options, 1, 2, 3); // Visualizza le pagine da 1 a 3.
}
```
**Spiegazione:** `JpgViewOptions` gestisce le impostazioni dell'immagine. `setRenderHeadings(true)` L'opzione garantisce che le intestazioni siano incluse nell'output JPG.

### Trasforma il foglio di calcolo in PNG
**Panoramica:** Converti i fogli Excel in formato PNG mantenendo le intestazioni di righe e colonne, adatto per output di immagini di alta qualità.

#### Implementazione passo dopo passo:
##### 1. Importare le librerie richieste
```java
import com.groupdocs.viewer.Viewer;
import com.groupdocs.viewer.options.PngViewOptions;
```
##### 2. Imposta la directory di output
```java
Path outputDirectory = Paths.get("YOUR_DOCUMENT_DIRECTORY", "RenderRowAndColumnHeadings");
Path pageFilePathFormat = outputDirectory.resolve("page_{0}.png");
```
##### 3. Inizializza il visualizzatore e configura le opzioni
```java
try (Viewer viewer = new Viewer(Paths.get("Sample.xlsx"))) {
    PngViewOptions options = new PngViewOptions(pageFilePathFormat);
    
    // Abilita il rendering delle intestazioni di righe e colonne nel foglio di calcolo.
    options.getSpreadsheetOptions().setRenderHeadings(true);

    viewer.view(options, 1, 2, 3); // Visualizza le pagine da 1 a 3.
}
```
**Spiegazione:** `PngViewOptions` viene utilizzato per le impostazioni PNG. Con `setRenderHeadings(true)`, le intestazioni sono incluse nelle immagini di output.

### Trasforma il foglio di calcolo in PDF
**Panoramica:** Trasforma i fogli Excel in formato PDF assicurando che le intestazioni di righe e colonne siano visibili, perfetto per l'archiviazione o la condivisione di documenti.

#### Implementazione passo dopo passo:
##### 1. Importare le librerie richieste
```java
import com.groupdocs.viewer.Viewer;
import com.groupdocs.viewer.options.PdfViewOptions;
```
##### 2. Imposta la directory di output
```java
Path outputDirectory = Paths.get("YOUR_DOCUMENT_DIRECTORY", "RenderRowAndColumnHeadings");
Path pageFilePathFormat = outputDirectory.resolve("output.pdf");
```
##### 3. Inizializza il visualizzatore e configura le opzioni
```java
try (Viewer viewer = new Viewer(Paths.get("Sample.xlsx"))) {
    PdfViewOptions options = new PdfViewOptions(pageFilePathFormat);
    
    // Abilita il rendering delle intestazioni di righe e colonne nel foglio di calcolo.
    options.getSpreadsheetOptions().setRenderHeadings(true);

    viewer.view(options, 1, 2, 3); // Visualizza le pagine da 1 a 3.
}
```
**Spiegazione:** `PdfViewOptions` configura le impostazioni di output PDF. Il `setRenderHeadings(true)` Questa opzione garantisce che le intestazioni siano visibili nel PDF finale.

## Applicazioni pratiche
Ecco alcuni scenari reali in cui queste funzionalità possono essere applicate:

1. **Reporting aziendale:** Condividi report dettagliati con le parti interessate convertendo i dati Excel in formati HTML o PDF per facilitarne la distribuzione e la visualizzazione.
2. **Visualizzazione dei dati:** Converti i fogli di calcolo in formati immagine come JPG o PNG per le presentazioni, assicurandoti che le intestazioni forniscano contesto ai dati visualizzati.
3. **Archiviazione dei documenti:** Utilizza la conversione PDF per archiviare i documenti in un formato universalmente accessibile, conservando tutti i dettagli necessari, come le intestazioni.