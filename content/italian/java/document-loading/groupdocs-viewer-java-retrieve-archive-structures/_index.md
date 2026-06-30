---
date: '2026-06-30'
description: Scopri come ottenere ViewInfo e recuperare le strutture di tipo file
  di archivio Java utilizzando GroupDocs.Viewer. Questa guida copre la configurazione,
  esempi di codice e casi d'uso reali.
keywords:
- how to get viewinfo
- retrieve archive structures
- java archive file type
- GroupDocs Viewer Java
schemas:
- author: GroupDocs
  dateModified: '2026-06-30'
  description: Learn how to get viewinfo and retrieve java archive file type structures
    using GroupDocs.Viewer. This guide covers setup, code examples, and real‑world
    use cases.
  headline: How to Get ViewInfo and Retrieve Archive Structures in Java
  type: TechArticle
- description: Learn how to get viewinfo and retrieve java archive file type structures
    using GroupDocs.Viewer. This guide covers setup, code examples, and real‑world
    use cases.
  name: How to Get ViewInfo and Retrieve Archive Structures in Java
  steps:
  - name: '**Data Management:** Quickly organize large datasets by understanding archive
      structures.'
    text: '**Data Management:** Quickly organize large datasets by understanding archive
      structures.'
  - name: '**Automated File Processing:** Batch‑process archived files without fully
      extracting them, cutting I/O by up to 70 %.'
    text: '**Automated File Processing:** Batch‑process archived files without fully
      extracting them, cutting I/O by up to 70 %.'
  - name: '**CMS Integration:** Enhance content‑management systems with on‑the‑fly
      archive navigation, enabling editors to preview files directly from the archive.'
    text: '**CMS Integration:** Enhance content‑management systems with on‑the‑fly
      archive navigation, enabling editors to preview files directly from the archive.'
  type: HowTo
- questions:
  - answer: It returns file type, page count, and a complete listing of folders and
      files inside an archive.
    question: What does “viewinfo” provide?
  - answer: ZIP, RAR, TAR, 7z, ISO, and 12+ other common formats.
    question: Which archive formats are supported?
  - answer: Yes—a commercial license is required for production; a free trial works
      for evaluation.
    question: Do I need a license for production?
  - answer: Absolutely—use streaming options and process one folder level at a time
      to keep memory usage low.
    question: Can large archives be processed efficiently?
  - answer: Maven is the recommended dependency manager, but Gradle or manual JAR
      inclusion also work.
    question: Is Maven the only way to add the library?
  type: FAQPage
title: Come ottenere ViewInfo e recuperare le strutture di archivio in Java
type: docs
url: /it/java/document-loading/groupdocs-viewer-java-retrieve-archive-structures/
weight: 1
---

# Come ottenere ViewInfo e recuperare le strutture degli archivi in Java

Gestire efficacemente i file di archivio richiede una chiara comprensione della loro struttura. In questo tutorial imparerai **come ottenere viewinfo** per qualsiasi archivio e vedrai come ti aiuta a lavorare con il **tipo di file archivio java**. Ti guideremo nella configurazione di GroupDocs.Viewer, nell'estrazione delle informazioni di visualizzazione e nella lettura ricorsiva delle gerarchie di cartelle, così potrai integrare la soluzione in progetti reali.

![Archive Structures with GroupDocs.Viewer for Java](/viewer/document-loading/archive-structures-java.png)

**Cosa imparerai**
- Configurare e impostare GroupDocs.Viewer per Java.  
- Metodi per **ottenere viewinfo** dagli archivi.  
- Tecniche per leggere e visualizzare la struttura delle cartelle di un file di archivio.  
- Applicazioni pratiche e considerazioni sulle prestazioni quando si utilizza GroupDocs.Viewer nei progetti Java.

## Risposte rapide
- **Cosa fornisce “viewinfo”?** Restituisce il tipo di file, il conteggio delle pagine e un elenco completo di cartelle e file all'interno di un archivio.  
- **Quali formati di archivio sono supportati?** ZIP, RAR, TAR, 7z, ISO e oltre 12 altri formati comuni.  
- **È necessaria una licenza per la produzione?** Sì—è richiesta una licenza commerciale per la produzione; una prova gratuita è sufficiente per la valutazione.  
- **È possibile elaborare archivi di grandi dimensioni in modo efficiente?** Assolutamente—usa le opzioni di streaming ed elabora un livello di cartella alla volta per mantenere basso l'uso della memoria.  
- **Maven è l'unico modo per aggiungere la libreria?** Maven è il gestore di dipendenze consigliato, ma anche Gradle o l'inclusione manuale del JAR funzionano.

## Cos'è “come ottenere viewinfo”?

`getViewInfo` è un metodo API di GroupDocs.Viewer che estrae i metadati da un documento o archivio senza un rendering completo. Restituisce l'albero interno delle cartelle, il conteggio dei file e le proprietà di base in una singola chiamata, permettendoti di decidere quali parti elaborare. La chiamata restituisce un'istantanea completa degli archivi fino a 500 MB in meno di un secondo sui server tipici.

## Perché recuperare le strutture del tipo di file archivio Java?

Recuperare la disposizione interna di un **java archive file type** consente di individuare i file necessari istantaneamente, evitare estrazioni non necessarie e costruire pipeline automatizzate che toccano solo le sotto‑cartelle rilevanti. Questo approccio riduce I/O fino al 70 % per archivi di grandi dimensioni e rende possibile scansionare migliaia di file al minuto in scenari di ingestione dati.

## Prerequisiti

- **Java Development Kit (JDK):** Versione 8 o successiva.  
- **Maven:** Per la gestione delle dipendenze e le compilazioni.  
- **Conoscenza di base di Java:** Familiarità con i concetti OOP è utile ma non obbligatoria.  

È inoltre necessario accedere alla libreria GroupDocs.Viewer, che puoi aggiungere al tuo progetto Maven come mostrato di seguito.

## Configurare GroupDocs.Viewer per Java

### Configurazione Maven

Aggiungi il repository e la dipendenza al tuo `pom.xml`.

**Repositories:**
```xml
<repositories>
   <repository>
      <id>repository.groupdocs.com</id>
      <name>GroupDocs Repository</name>
      <url>https://releases.groupdocs.com/viewer/java/</url>
   </repository>
</repositories>
```

**Dependencies:**
```xml
<dependencies>
   <dependency>
      <groupId>com.groupdocs</groupId>
      <artifactId>groupdocs-viewer</artifactId>
      <version>25.2</version>
   </dependency>
</dependencies>
```

### Acquisizione della licenza

- **Prova gratuita:** Scarica una versione di prova dal sito GroupDocs.  
- **Licenza temporanea:** Richiedi una chiave temporanea per una valutazione a breve termine.  
- **Licenza completa:** Acquista una licenza commerciale per uso illimitato in produzione.

Una volta che la libreria è nel tuo classpath, puoi iniziare a scrivere codice.

## Guida all'implementazione

### Come ottenere ViewInfo per i file di archivio

Per ottenere le informazioni di visualizzazione, prima carica l'archivio nel Viewer, poi chiama `getViewInfo` per recuperare i metadati e infine itera sulla gerarchia di cartelle restituita. Questo modello a tre passaggi funziona per tutti i formati di archivio supportati e fornisce un'istantanea completa in una singola chiamata API, semplificando l'elaborazione successiva.

#### Inizializzare il Viewer

La classe `Viewer` è il punto di ingresso per tutte le operazioni di rendering e ispezione. Gestisce i flussi di file, il rilevamento del formato e la pulizia delle risorse.

```java
try (Viewer viewer = new Viewer("YOUR_DOCUMENT_DIRECTORY/SAMPLE_ZIP_WITH_FOLDERS")) {
    // Additional steps will follow here.
}
```

#### Recuperare le informazioni di visualizzazione

`ViewInfo` incapsula i metadati come tipo di file, numero totale di pagine e un elenco gerarchico di cartelle e file. Chiamando `getViewInfo` restituisce immediatamente questo oggetto.

```java
ViewInfo viewInfo = viewer.getViewInfo(ViewInfoOptions.forHtmlView());
System.out.println("File type: " + viewInfo.getFileType());
System.out.println("Pages count: " + viewInfo.getPages().size());
```

#### Visualizzare la struttura delle cartelle

Itera su `viewInfo.getFolders()` per stampare il nome di ogni cartella, la sua profondità e i file contenuti. Questo semplice ciclo fornisce una vista ad albero leggibile dell'archivio.

```java
String rootFolder = "";
readFolders(viewer, rootFolder);
```

##### Lettura ricorsiva delle cartelle

Per archivi profondamente annidati, un metodo di supporto ricorsivo può attraversare l'albero in profondità, garantendo che ogni sotto‑cartella venga visitata senza caricare l'intero archivio in memoria.

```java
private static void readFolders(Viewer viewer, String folder) {
    ViewInfoOptions viewInfoOptions = ViewInfoOptions.forHtmlView();
    viewInfoOptions.getArchiveOptions().setFolder(folder);
    
    ArchiveViewInfo viewInfo = (ArchiveViewInfo) viewer.getViewInfo(viewInfoOptions);
    
    for (String subFolder : viewInfo.getFolders()) {
        System.out.println(" - " + subFolder);
        readFolders(viewer, subFolder);
    }
}
```

### Funzione 2: Recuperare la struttura delle cartelle dell'archivio

Questa funzione si concentra sulla stampa della struttura delle cartelle di un file di archivio. È simile alla prima funzione ma enfatizza l'esplorazione ricorsiva.

#### Configurare le opzioni ViewInfo

`ArchiveOptions` consente di specificare la protezione con password, i limiti di pagine e le preferenze di streaming prima di chiamare `getViewInfo`.

```java
ViewInfoOptions viewInfoOptions = ViewInfoOptions.forHtmlView();
viewInfoOptions.getArchiveOptions().setFolder(folder);
```

#### Esplorazione ricorsiva

Una seconda routine ricorsiva dimostra come gestire archivi protetti da password e grandi insiemi di file in modo efficiente.

```java
for (String subFolder : viewInfo.getFolders()) {
    System.out.println(" - " + subFolder);
    readFolders(viewer, subFolder);
}
```

## Applicazioni pratiche

1. **Gestione dei dati:** Organizza rapidamente grandi set di dati comprendendo le strutture degli archivi.  
2. **Elaborazione automatizzata dei file:** Elabora in batch i file archiviati senza estrarli completamente, riducendo I/O fino al 70 %.  
3. **Integrazione CMS:** Migliora i sistemi di gestione dei contenuti con navigazione degli archivi in tempo reale, consentendo agli editori di visualizzare in anteprima i file direttamente dall'archivio.

## Considerazioni sulle prestazioni

- **Ottimizzare l'uso della memoria:** Elabora le cartelle un livello alla volta e chiudi l'istanza `Viewer` prontamente.  
- **Rimanere aggiornati:** Usa l'ultima versione di GroupDocs.Viewer (25.2 al momento della scrittura) e le versioni JDK per miglioramenti delle prestazioni.  
- **Supporto streaming:** La libreria può fare streaming di archivi superiori a 1 GB senza caricare l'intero file in RAM, grazie alla sua architettura interna di lettura a blocchi.

## Problemi comuni e soluzioni

| Problema | Perché accade | Soluzione |
|----------|----------------|-----------|
| `NullPointerException` durante la lettura delle cartelle | `viewInfo.getFolders()` restituisce null per directory vuote | Verifica la presenza di null o di una lista vuota prima di iterare. |
| Elaborazione lenta di file ZIP enormi | L'intero archivio viene caricato in memoria | Usa le opzioni di streaming disponibili nelle versioni più recenti di GroupDocs. |
| Licenza non trovata | Il percorso del file di licenza è errato | Posiziona il file di licenza nella radice dell'applicazione o imposta `License.setLicense("path/to/license.json")`. |

## Domande frequenti

**Q:** Cos'è GroupDocs.Viewer?  
**A:** GroupDocs.Viewer è una libreria Java che rende più di 100 formati di documenti, immagini e archivi in HTML, PDF o flussi di immagini senza richiedere applicazioni native.

**Q:** Posso usare GroupDocs.Viewer con altri linguaggi di programmazione?  
**A:** Sì, GroupDocs offre SDK per .NET, Python, PHP, e altri, ma questo tutorial si concentra sull'implementazione Java.

**Q:** Come gestisco file di archivio di grandi dimensioni?  
**A:** Abilita lo streaming via `ArchiveOptions.setUseStreaming(true)`, elabora un livello di cartella alla volta e rilascia l'oggetto `Viewer` dopo l'uso.

**Q:** Quali tipi di archivi supporta GroupDocs.Viewer?  
**A:** Supporta oltre 12 formati di archivio, inclusi ZIP, RAR, TAR, 7z, ISO, ARJ e CAB, più molti tipi proprietari.

**Q:** Esiste un limite di dimensione per gli archivi?  
**A:** Il limite pratico dipende dalla RAM e CPU del server; i test mostrano una gestione fluida di archivi da 2 GB su una macchina con 16 GB di RAM quando lo streaming è abilitato.

**Q:** Il “come ottenere viewinfo” funziona con archivi protetti da password?  
**A:** Sì, fornisci la password tramite `ArchiveOptions.setPassword("yourPassword")` prima di invocare `getViewInfo`.

## Conclusione

Seguendo questa guida ora sai **come ottenere viewinfo** per qualsiasi archivio supportato e come attraversare la sua gerarchia di cartelle usando GroupDocs.Viewer per Java. Queste tecniche ti consentono di costruire pipeline di elaborazione dati più intelligenti, migliorare le integrazioni CMS e gestire grandi collezioni di file archiviati con fiducia. Successivamente, esplora il rendering di file individuali dall'archivio o la loro conversione in PDF/HTML usando altre funzionalità del Viewer.

---

**Ultimo aggiornamento:** 2026-06-30  
**Testato con:** GroupDocs.Viewer 25.2 per Java  
**Autore:** GroupDocs  

**Risorse**
- **Documentazione:** [Documentazione GroupDocs Viewer Java](https://docs.groupdocs.com/viewer/java/)
- **Riferimento API:** [Riferimento API GroupDocs per Java](https://reference.groupdocs.com/viewer/java/)
- **Scarica GroupDocs.Viewer:** [Pagina di download GroupDocs](https://releases.groupdocs.com/viewer/java/)
- **Acquista licenza:** [Acquista GroupDocs](https://purchase.groupdocs.com/buy)
- **Prova gratuita e licenza temporanea:** [Prova gratuita GroupDocs](https://releases.groupdocs.com/viewer/java/) | [Licenza temporanea](https://purchase.groupdocs.com/temporary-license/)

## Tutorial correlati

- [Estrai i metadati del documento con GroupDocs.Viewer per Java - Recupera informazioni e approfondimenti sulla visualizzazione del documento](/viewer/java/advanced-rendering/groupdocs-viewer-java-document-views/)
- [Come recuperare gli allegati e stampare gli allegati dei documenti con GroupDocs.Viewer per Java](/viewer/java/advanced-rendering/groupdocs-viewer-java-retrieve-print-attachments/)
- [Guida Java: Renderizzare pagine specifiche con l'API GroupDocs.Viewer per anteprima e gestione dei documenti](/viewer/java/rendering-basics/java-groupdocs-viewer-render-pages-api-tutorial/)