---
date: '2026-08-03'
description: Scopri come convertire zip in html usando GroupDocs.Viewer Java, impostare
  items per page, embed resources html e batch convert archives in modo efficiente.
keywords:
- convert zip to html
- how to batch convert
- embed resources html
- batch convert archives
- how to convert archives
lastmod: '2026-08-03'
og_description: Scopri come convertire zip in html usando GroupDocs.Viewer Java, impostare
  items per page, embed resources html e batch convert archives in modo efficiente.
  Segui step‑by‑step code e performance tips.
og_image_alt: 'Guide: convert zip to html with GroupDocs.Viewer Java, showing pagination
  and embedded resources'
og_title: Converti zip in html e imposta items per page con GroupDocs.Viewer Java
schemas:
- author: GroupDocs
  dateModified: '2026-08-03'
  description: Learn how to convert zip to html using GroupDocs.Viewer Java, set items
    per page, embed resources html, and batch convert archives efficiently.
  headline: Convert zip to html and set items per page with GroupDocs.Viewer Java
  type: TechArticle
- questions:
  - answer: GroupDocs.Viewer Java is a server‑side library that renders over 50 document
      and archive formats—including ZIP and RAR—into HTML, PDF, or image files without
      requiring external applications.
    question: What is GroupDocs.Viewer Java?
  - answer: Visit the [free trial link](https://releases.groupdocs.com/viewer/java/)
      to download and test.
    question: How can I obtain a free trial of GroupDocs.Viewer?
  - answer: Yes, the viewer supports PDFs, Word, Excel, PowerPoint, and 35+ additional
      formats.
    question: Can I convert other document types besides archives?
  - answer: Reduce the number of items per page, enable streaming, or process archives
      in smaller batches to improve speed.
    question: What should I do if rendering is slow?
  - answer: Reach out via the [support forum](https://forum.groupdocs.com/c/viewer/9).
    question: Where can I get help or support?
  type: FAQPage
tags:
- convert zip
- GroupDocs.Viewer
- Java archive conversion
- html rendering
- batch conversion
title: Converti zip in html e imposta items per page con GroupDocs.Viewer Java
type: docs
url: /it/java/export-conversion/groupdocs-viewer-java-convert-archives-html/
weight: 1
---

# Converti zip in html e imposta gli elementi per pagina con GroupDocs.Viewer Java

In molte applicazioni web è necessario mostrare il contenuto di un archivio ZIP o RAR direttamente nel browser. Con GroupDocs.Viewer per Java è possibile **convertire zip in html** in un unico passaggio, controllare quante voci dell'archivio appaiono su ogni pagina, incorporare tutte le immagini e i CSS di supporto, e persino elaborare in batch decine di archivi. Questo tutorial ti guida attraverso l'intero flusso di lavoro, dalla configurazione di Maven al rendering multipagina, e spiega perché ogni impostazione è importante per le prestazioni e l'usabilità.

![Converti archivi in HTML con GroupDocs.Viewer per Java](/viewer/export-conversion/convert-archives-to-html-java.png)

## Risposte rapide
- **Cosa controlla “set items per page”?** Determina quanti file o cartelle di un archivio appaiono su ogni pagina HTML generata.  
- **Posso incorporare immagini e CSS direttamente nell'HTML?** Sì – usa l'opzione `forEmbeddedResources` per incorporare le risorse HTML.  
- **È possibile la conversione batch?** Assolutamente; è possibile iterare su una collezione di archivi e renderizzare ciascuno con le stesse impostazioni.  
- **Ho bisogno di Maven per usare GroupDocs.Viewer?** Sì, aggiungi la dipendenza Maven `groupdocs-viewer` come mostrato di seguito.  
- **Quali formati di output sono supportati?** Sono disponibili sia HTML a pagina singola che HTML multipagina, e la libreria supporta oltre 50 tipi di archivio in ingresso.

## Cos'è “set items per page” in GroupDocs.Viewer?
L'impostazione **set items per page** appartiene alle opzioni di rendering dell'archivio. Indica al visualizzatore quante voci dell'archivio (file o cartelle) devono essere visualizzate su ogni pagina HTML quando si genera un documento HTML multipagina. Regolare questo valore ti aiuta a bilanciare la dimensione della pagina e la velocità di navigazione, soprattutto per archivi di grandi dimensioni.

## Perché incorporare le risorse HTML?
Incorporare le risorse (immagini, CSS, font) direttamente nel file HTML crea un documento unico e portatile che può essere aperto senza file esterni. È ideale per allegati email, visualizzazione offline o per incorporare l'output in altre pagine web. Questo approccio semplifica anche il deployment poiché non è necessario gestire percorsi di risorse esterne.

## Prerequisiti
- **Librerie richieste:** Includere GroupDocs.Viewer versione 25.2 o successiva.  
- **Ambiente:** Java Development Kit (JDK) installato e configurato.  
- **Conoscenze:** Java di base e gestione delle dipendenze Maven.  

## Configurazione Maven di GroupDocs Viewer
Aggiungi il repository GroupDocs e la dipendenza del viewer al tuo `pom.xml`:

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
GroupDocs.Viewer offre un **link per la prova gratuita**, una licenza temporanea o un'opzione di acquisto completo. Scegli quella che meglio si adatta al tuo cronoprogramma di progetto.

### Inizializzazione di base
Dopo la configurazione di Maven, porta il viewer nel tuo codice:

```java
import com.groupdocs.viewer.Viewer;
// Your initialization code here
```

## Come renderizzare gli archivi in HTML a pagina singola
Viewer è la classe principale che carica un documento o un archivio per il rendering.

Per generare un unico file HTML che contenga l'intero archivio, crea un'istanza `Viewer` per il file ZIP e utilizza `HtmlViewOptions.forEmbeddedResources()` per incorporare tutte le immagini, i CSS e i font. Il rendering dell'archivio con queste opzioni produce una pagina autonoma adatta per email o uso offline.

### Passo 1: Definisci la directory di output
```java
Path outputDirectory = Utils.getOutputDirectoryPath("YOUR_OUTPUT_DIRECTORY");
```

### Passo 2: Imposta il nome file per l'output a pagina singola
```java
Path pageFilePathFormat = outputDirectory.resolve("RAR_result.html");
```

### Passo 3: Inizializza il viewer
```java
try (Viewer viewer = new Viewer(TestFiles.SAMPLE_RAR_WITH_FOLDERS)) {
    // Further configuration steps follow
}
```

### Passo 4: Configura le opzioni di rendering (incorpora risorse HTML)
```java
HtmlViewOptions options = HtmlViewOptions.forEmbeddedResources(pageFilePathFormat);
```

### Passo 5: Renderizza come pagina singola
```java
options.setRenderToSinglePage(true);
viewer.view(options);
```

## Come renderizzare gli archivi in HTML multipagina e impostare gli elementi per pagina
`HtmlViewOptions` configura come il viewer renderizza l'output HTML, includendo la paginazione e l'incorporamento delle risorse.

Per suddividere un archivio in più pagine, crea `HtmlViewOptions.forEmbeddedResources()` e imposta la dimensione della pagina desiderata con `options.setItemsPerPage(20)`. Il viewer genererà file HTML separati, ciascuno mostrando fino al numero specificato di voci, migliorando la navigazione per archivi di grandi dimensioni e garantendo un caricamento più rapido.

### Passo 1: Riutilizza la directory di output
```java
Path outputDirectory = Utils.getOutputDirectoryPath("YOUR_OUTPUT_DIRECTORY");
```

### Passo 2: Definisci il formato del nome file per più pagine
```java
Path pageFilePathFormat = outputDirectory.resolve("RAR_result_page_{0}.html");
```

### Passo 3: Inizializza nuovamente il viewer
```java
try (Viewer viewer = new Viewer(TestFiles.SAMPLE_RAR_WITH_FOLDERS)) {
    // Continue with multi‑page configuration
}
```

### Passo 4: Configura le opzioni multipagina (incorpora risorse HTML)
```java
HtmlViewOptions options = HtmlViewOptions.forEmbeddedResources(pageFilePathFormat);
```

### Passo 5: Imposta gli elementi per pagina (parola chiave principale in azione)
```java
options.getArchiveOptions().setItemsPerPage(10); // Default is 16
viewer.view(options);
```

## Applicazioni pratiche
- **Sistemi di gestione documentale:** Aggiungi la funzionalità di anteprima degli archivi senza installare visualizzatori aggiuntivi.  
- **Portali web:** Offri agli utenti un modo rapido, senza download, per esplorare i documenti raggruppati.  
- **Strumenti di collaborazione:** Consenti ai team di ispezionare gli archivi condivisi direttamente nel browser.

## Considerazioni sulle prestazioni
- **Gestione delle risorse:** Mantieni basso l'uso della memoria elaborando gli archivi in streaming; il viewer può gestire archivi fino a 500 MB senza caricare l'intero file in memoria.  
- **Conversione batch di archivi:** Scorri un elenco di file di archivio e chiama la stessa logica di rendering per massimizzare il throughput.  
- **Strategia di caching:** Memorizza l'HTML renderizzato in una cache se lo stesso archivio viene accesso frequentemente, riducendo il tempo di elaborazione ripetuta fino al 70 %.

## Domande frequenti
**Q: Cos'è GroupDocs.Viewer Java?**  
A: GroupDocs.Viewer Java è una libreria lato server che renderizza oltre 50 formati di documenti e archivi — inclusi ZIP e RAR — in file HTML, PDF o immagine senza richiedere applicazioni esterne.

**Q: Come posso ottenere una prova gratuita di GroupDocs.Viewer?**  
A: Visita il [link per la prova gratuita](https://releases.groupdocs.com/viewer/java/) per scaricare e testare.

**Q: Posso convertire altri tipi di documento oltre agli archivi?**  
A: Sì, il viewer supporta PDF, Word, Excel, PowerPoint e oltre 35 formati aggiuntivi.

**Q: Cosa devo fare se il rendering è lento?**  
A: Riduci il numero di elementi per pagina, abilita lo streaming o elabora gli archivi in batch più piccoli per migliorare la velocità.

**Q: Dove posso ottenere aiuto o supporto?**  
A: Contatta il [forum di supporto](https://forum.groupdocs.com/c/viewer/9).

**Q: È possibile incorporare CSS e immagini direttamente nell'HTML?**  
A: Assolutamente—usa `HtmlViewOptions.forEmbeddedResources` come mostrato negli esempi.

**Q: Come posso convertire in batch una cartella di archivi?**  
A: Itera su ogni file con un ciclo `for`, applicando la stessa configurazione `Viewer` e `HtmlViewOptions` per ogni iterazione.

## Risorse
- **Documentazione:** Approfondisci le funzionalità con la [documentazione GroupDocs](https://docs.groupdocs.com/viewer/java/).  
- **Riferimento API:** Esplora l'API completa al [GroupDocs API](https://reference.groupdocs.com/viewer/java/).  
- **Download:** Ottieni gli ultimi binari dalla [pagina di download](https://releases.groupdocs.com/viewer/java/).  
- **Acquisto e licenze:** Consulta le opzioni nella [pagina di acquisto](https://purchase.groupdocs.com/buy).  
- **Supporto e community:** Partecipa alle discussioni sul [forum GroupDocs](https://forum.groupdocs.com/c/viewer/9).

---

**Ultimo aggiornamento:** 2026-08-03  
**Testato con:** GroupDocs.Viewer 25.2  
**Autore:** GroupDocs

## Tutorial correlati
- [Come convertire zip in HTML e renderizzare le cartelle zip in Java con GroupDocs.Viewer](/viewer/java/advanced-rendering/render-archive-folders-groupdocs-viewer-java/)
- [converti zip in pdf con GroupDocs.Viewer Java - Nomi file personalizzati](/viewer/java/advanced-rendering/groupdocs-viewer-java-custom-filenames-rendering-archives/)
- [Come convertire DOCX in HTML usando GroupDocs.Viewer per Java: Guida passo‑passo](/viewer/java/export-conversion/convert-docx-to-html-groupdocs-viewer-java/)