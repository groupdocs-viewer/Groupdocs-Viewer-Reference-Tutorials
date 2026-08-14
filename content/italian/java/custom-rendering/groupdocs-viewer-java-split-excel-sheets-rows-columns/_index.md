---
date: '2026-06-15'
description: Scopri come convertire Excel in PDF Java e dividere i fogli Excel per
  righe e colonne usando GroupDocs Viewer. Includes setup, code, and best practices.
keywords:
- convert excel to pdf java
- split excel sheet rows
- split excel sheet columns
schemas:
- author: GroupDocs
  dateModified: '2026-06-15'
  description: Learn how to convert Excel to PDF Java and split Excel sheets by rows
    and columns using GroupDocs Viewer. Includes setup, code, and best practices.
  headline: Convert Excel to PDF Java & Split Sheets by Rows & Columns
  type: TechArticle
- description: Learn how to convert Excel to PDF Java and split Excel sheets by rows
    and columns using GroupDocs Viewer. Includes setup, code, and best practices.
  name: Convert Excel to PDF Java & Split Sheets by Rows & Columns
  steps:
  - name: Set Up Paths and Initialize the Viewer
    text: First, define where the split pages will be saved and create a `Viewer`
      instance for the source workbook.
  - name: Configure Rows Per Page
    text: Tell the viewer how many rows each page should contain.
  - name: Render the Document
    text: Finally, render the workbook using the options you defined.
  - name: Set Up Paths and Initialize the Viewer
    text: The setup mirrors the row‑only example, only the file name changes.
  - name: Configure Rows and Columns Per Page
    text: Specify both dimensions to create a grid‑style split.
  - name: Render the Document
    text: Render using the same `view` call.
  type: HowTo
- questions:
  - answer: Yes. Replace `HtmlViewOptions` with `PdfViewOptions` and keep the same
      `SpreadsheetOptions` configuration.
    question: Can I generate a PDF instead of HTML?
  - answer: Direct content‑based splitting isn’t built into GroupDocs Viewer, but
      you can preprocess the workbook with Apache POI to create separate sheets before
      rendering.
    question: Is it possible to split based on cell content rather than fixed rows/columns?
  - answer: Absolutely. The viewer handles XLS, XLSX, CSV, and other spreadsheet formats.
    question: Does GroupDocs Viewer support older Excel formats (XLS)?
  - answer: Serve the output folder as a static resource and reference the generated
      `page_0.html`, `page_1.html`, etc., from your Thymeleaf or JSP templates.
    question: How do I embed the generated HTML into a Spring MVC view?
  - answer: A full production license from GroupDocs is required; trial licenses are
      for evaluation only.
    question: What license do I need for commercial deployment?
  type: FAQPage
title: Converti Excel in PDF Java e dividi i fogli per righe e colonne
type: docs
url: /it/java/custom-rendering/groupdocs-viewer-java-split-excel-sheets-rows-columns/
weight: 1
---

# Convertire Excel in PDF Java e dividere i fogli per righe e colonne (Java)

I grandi workbook Excel spesso contengono più dati di quanti possano essere visualizzati comodamente su un unico schermo o stampati su una pagina. **convert excel to pdf java** è una necessità comune quando serve un formato statico e condivisibile, mentre **splitting Excel sheets by rows and columns** rende i dati più facili da consumare in layout web o di stampa. In questa guida illustreremo entrambi i compiti usando **GroupDocs Viewer for Java**, ti mostreremo come configurare la paginazione e spiegheremo consigli di best‑practice per le prestazioni e la risoluzione dei problemi.

![Dividi fogli Excel per righe e colonne con GroupDocs.Viewer for Java](/viewer/custom-rendering/split-excel-sheets-by-rows-and-columns.png)

[Dividi fogli Excel per righe e colonne con GroupDocs.Viewer for Java](/viewer/custom-rendering/split-excel-sheets-by-rows-and-columns.png)

## Risposte rapide
- **Quale libreria è usata?** GroupDocs Viewer for Java.  
- **Posso dividere sia per righe che per colonne?** Sì – è possibile definire rows‑per‑page e columns‑per‑page insieme.  
- **Ho bisogno di una licenza?** Una licenza di prova o temporanea funziona per lo sviluppo; è necessaria una licenza completa per la produzione.  
- **Quali formati di output sono supportati?** Viene mostrato HTML (risorse incorporate); è possibile generare PDF con le stesse opzioni.  
- **Maven è obbligatorio?** Maven è il modo consigliato per gestire le dipendenze.  
- **Posso anche convertire Excel in PDF?** Assolutamente – basta sostituire `HtmlViewOptions` con `PdfViewOptions` e riutilizzare le stesse impostazioni di paginazione.

## Cos’è “How to Split Excel”?
Dividere un foglio Excel significa suddividere un singolo worksheet in più pagine o file basati su un numero fisso di righe, colonne o entrambi. Questa tecnica è utile quando è necessario creare report paginati, incorporare dati in pagine web o generare sezioni stampabili senza caricare l’intero workbook in una volta.

## Perché usare GroupDocs Viewer for Java?
GroupDocs Viewer elabora i fogli di calcolo in un unico passaggio e li pagina automaticamente, eliminando i calcoli manuali. **Il rendering veloce elabora un workbook XLSX di 250 pagine in meno di 2 secondi su un tipico server a 2 core**, e **la libreria supporta oltre 50 formati di input e output**, tra cui XLS, XLSX, CSV, PDF e HTML. Funziona su qualsiasi piattaforma compatibile con JVM—Windows, Linux, macOS, container Docker o runtime serverless basati su cloud—così puoi integrarlo ovunque viva la tua applicazione Java.

## Prerequisiti
- Java 17 o successivo installato.  
- Un IDE come IntelliJ IDEA o Eclipse.  
- Maven per la gestione delle dipendenze.  
- Conoscenze di base di Java e familiarità con la gestione dei file Excel.

### Librerie richieste, versioni e dipendenze
Add the GroupDocs repository and the viewer dependency to your `pom.xml`:

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
Ottieni una prova gratuita, una licenza temporanea o acquista una licenza completa da [GroupDocs](https://purchase.groupdocs.com/buy).

## Come convertire Excel in PDF Java?

La classe `Viewer` è il componente principale di GroupDocs Viewer che carica un documento e fornisce metodi di rendering per vari formati di output. `SpreadsheetOptions` consente di controllare le impostazioni di paginazione come rows‑per‑page e columns‑per‑page per il rendering dei fogli di calcolo.

Carica il tuo file Excel con `new Viewer("source.xlsx")`, configura `SpreadsheetOptions` per la paginazione e chiama `viewer.view(pdfOptions, stream)` – quella singola chiamata converte il workbook in PDF rispettando i limiti di righe/colonne impostati. La conversione preserva formule, immagini e stili delle celle, fornendo una replica PDF fedele pronta per la distribuzione.

## Come dividere i fogli Excel per righe

Dividere per righe crea una serie di pagine HTML, ciascuna contenente un numero fisso di righe (ad esempio, 15). Questo approccio è ideale per dashboard che mostrano un numero limitato di record per visualizzazione. Il viewer genererà file HTML separati come `page_0.html`, `page_1.html`, ecc., ognuno contenente il numero di righe specificato. Questo semplifica il caricamento solo della porzione necessaria in un'interfaccia web, riducendo larghezza di banda e tempo di rendering.

### Ancoraggio della definizione
`Viewer` è la classe principale di GroupDocs Viewer che carica un documento e orchestra il rendering nel formato di output scelto.

### Implementazione passo‑a‑passo

#### Passo 1: Configurare i percorsi e inizializzare il Viewer
First, define where the split pages will be saved and create a `Viewer` instance for the source workbook.

```java
Path outputDirectory = Path.of("YOUR_OUTPUT_DIRECTORY/SplitByRows");
Path pageFilePathFormat = outputDirectory.resolve("page_{0}.html");

try (Viewer viewer = new Viewer("YOUR_DOCUMENT_DIRECTORY/TWO_PAGES_XLSX")) {
    // Proceed with further configuration...
}
```

#### Passo 2: Configurare le righe per pagina
Tell the viewer how many rows each page should contain.

```java
int countRowsPerPage = 15;
HtmlViewOptions viewOptions = HtmlViewOptions.forEmbeddedResources(pageFilePathFormat);
viewOptions.setSpreadsheetOptions(SpreadsheetOptions.forSplitSheetIntoPages(countRowsPerPage));
```

#### Passo 3: Renderizzare il documento
Finally, render the workbook using the options you defined.

```java
viewer.view(viewOptions);
```

## Come dividere i fogli Excel per righe e colonne

A volte una singola pagina deve mostrare una matrice di righe **e** colonne (ad esempio, 15 righe × 7 colonne). Questo ti dà il pieno controllo sul layout di ogni pagina HTML. Le pagine risultanti mostrano un blocco rettangolare di celle, per esempio righe 1‑15 e colonne A‑G nella prima pagina, righe 16‑30 e colonne H‑N nella successiva. Questa paginazione in stile griglia è utile per creare report stampabili che si adattano a formati di carta standard.

### Ancoraggio della definizione
`SpreadsheetOptions` configura quante righe e colonne appaiono in ogni pagina generata.

### Implementazione passo‑a‑passo

#### Passo 1: Configurare i percorsi e inizializzare il Viewer
The setup mirrors the row‑only example, only the file name changes.

```java
Path outputDirectory = Path.of("YOUR_OUTPUT_DIRECTORY/SplitByRowsAndColumns");
Path pageFilePathFormat = outputDirectory.resolve("page_{0}.html");

try (Viewer viewer = new Viewer("YOUR_DOCUMENT_DIRECTORY/FOUR_PAGES_XLSX")) {
    // Continue with configuration...
}
```

#### Passo 2: Configurare righe e colonne per pagina
Specify both dimensions to create a grid‑style split.

```java
int countRowsPerPage = 15;
int countColumnsPerPage = 7;

HtmlViewOptions options = HtmlViewOptions.forEmbeddedResources(pageFilePathFormat);
options.setSpreadsheetOptions(SpreadsheetOptions.forSplitSheetIntoPages(countRowsPerPage, countColumnsPerPage));
```

#### Passo 3: Renderizzare il documento
Render using the same `view` call.

```java
viewer.view(options);
```

## Applicazioni pratiche
- **Generate Excel report Java**: Trasforma grandi modelli finanziari in una serie di report HTML paginati.  
- **GroupDocs Viewer Excel**: Incorpora le pagine divise direttamente in un portale web per l'esplorazione interattiva dei dati.  
- **Render Excel HTML Java**: Servi le pagine HTML generate tramite un servlet o un controller Spring per un rendering lato client veloce.  

## Considerazioni sulle prestazioni
- **Utilizzo della memoria** – I grandi workbook possono consumare una heap significativa; considera di aumentare l'impostazione JVM `-Xmx`.  
- **Dimensione del blocco** – Scegli il numero di righe/colonne che bilancia la dimensione della pagina e la velocità di rendering.  
- **Aggiornamenti di versione** – Mantieni GroupDocs Viewer aggiornato per beneficiare dei miglioramenti di prestazioni; l'ultima release 25.2 migliora la velocità di rendering fino al 30 % rispetto alla 24.x.  

## Problemi comuni e risoluzione

| Sintomo | Causa probabile | Soluzione |
|---------|-----------------|----------|
| `OutOfMemoryError` | Rendering di un foglio molto grande con troppe righe per pagina | Ridurre `countRowsPerPage` o aumentare la heap JVM |
| File di output vuoti | Percorso file errato o permessi di scrittura mancanti | Verificare che `outputDirectory` esista e sia scrivibile |
| Risorse HTML non caricate | Uso di `forEmbeddedResources` ma i file sono serviti da un URL base diverso | Servire l'intera cartella di output o passare a `forExternalResources` |

## Domande frequenti

**D: Posso generare un PDF invece di HTML?**  
R: Sì. Sostituisci `HtmlViewOptions` con `PdfViewOptions` e mantieni la stessa configurazione di `SpreadsheetOptions`.

**D: È possibile dividere in base al contenuto delle celle anziché a righe/colonne fisse?**  
R: La divisione basata sul contenuto non è integrata in GroupDocs Viewer, ma puoi pre‑processare il workbook con Apache POI per creare fogli separati prima del rendering.

**D: GroupDocs Viewer supporta formati Excel più vecchi (XLS)?**  
R: Assolutamente. Il viewer gestisce XLS, XLSX, CSV e altri formati di fogli di calcolo.

**D: Come incorporo l'HTML generato in una vista Spring MVC?**  
R: Servi la cartella di output come risorsa statica e fai riferimento ai file `page_0.html`, `page_1.html`, ecc., dai tuoi template Thymeleaf o JSP.

**D: Quale licenza è necessaria per il deployment commerciale?**  
R: È necessaria una licenza di produzione completa da GroupDocs; le licenze di prova sono solo per valutazione.

## Risorse
- **Documentazione**: [GroupDocs Viewer Java Documentation](https://docs.groupdocs.com/viewer/java/)
- **Riferimento API**: [GroupDocs API Reference](https://reference.groupdocs.com/viewer/java/)
- **Download**: [GroupDocs Viewer Java Releases](https://releases.groupdocs.com/viewer/java/)
- **Acquisto**: [Buy GroupDocs License](https://purchase.groupdocs.com/buy)
- **Prova gratuita**: [GroupDocs Free Trial](https://releases.groupdocs.com/viewer/java/)
- **Licenza temporanea**: [Get Temporary License](https://purchase.groupdocs.com/temporary-license/)
- **Supporto**: [GroupDocs Support Forum](https://forum.groupdocs.com/c/viewer/9)

---

**Ultimo aggiornamento:** 2026-06-15  
**Testato con:** GroupDocs Viewer 25.2 for Java  
**Autore:** GroupDocs  

## Tutorial correlati

- [Renderizzare righe e colonne nascoste in fogli di calcolo Java usando GroupDocs.Viewer](/viewer/java/advanced-rendering/render-hidden-rows-columns-java-groupdocs-viewer/)
- [Saltare il rendering delle righe vuote in Java usando GroupDocs.Viewer: Guida alle prestazioni](/viewer/java/advanced-rendering/skip-rendering-empty-rows-java-groupdocs-viewer/)
- [Guida completa: Convertire Excel 2003 XML in HTML/JPG/PNG/PDF con GroupDocs.Viewer Java](/viewer/java/rendering-basics/groupdocs-viewer-java-excel-2003-xml-conversion/)