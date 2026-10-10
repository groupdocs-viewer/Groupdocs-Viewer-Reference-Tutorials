---
date: '2026-10-10'
description: Scopri come convertire zip in html usando GroupDocs.Viewer Java, impostare
  gli elementi per pagina, incorporare risorse html e convertire batch gli archivi
  in modo efficiente.
images:
- /java/export-conversion/groupdocs-viewer-java-convert-archives-html/og-image.png
keywords:
- how to convert zip
- convert archive to html
- java convert zip html
lastmod: '2026-10-10'
og_description: Scopri come convertire zip in html con GroupDocs.Viewer Java, incorporare
  risorse, impostare gli elementi per pagina e batch‑processare gli archivi per anteprime
  web veloci e portabili.
og_image_alt: 'Developer guide: convert zip to HTML with GroupDocs.Viewer Java, showing
  pagination and embedded resources'
og_title: Converti zip in HTML con paginazione GroupDocs.Viewer Java
schemas:
- author: GroupDocs
  dateModified: '2026-10-10'
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
title: Converti zip in html e imposta gli elementi per pagina con GroupDocs.Viewer
  Java
type: docs
url: /it/java/export-conversion/groupdocs-viewer-java-convert-archives-html/
weight: 1
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Converti zip in html e imposta gli elementi per pagina con GroupDocs.Viewer Java

In molte applicazioni web è necessario mostrare il contenuto di un archivio ZIP o RAR direttamente nel browser. **Come convertire zip** in HTML usando GroupDocs.Viewer per Java è una necessità comune, e la libreria consente di incorporare immagini, CSS e font in modo che il risultato sia una pagina singola e portatile. Questo tutorial ti guida passo passo—dalla configurazione Maven al rendering multi‑pagina—spiegando perché ogni opzione è importante per le prestazioni e l'usabilità.

![Converti archivi in HTML con GroupDocs.Viewer per Java](/viewer/export-conversion/convert-archives-to-html-java.png)

## Risposte rapide
- **Cosa controlla “set items per page”?** Determina quanti file o cartelle di un archivio appaiono in ogni pagina HTML generata.  
- **Posso incorporare immagini e CSS direttamente nell'HTML?** Sì – usa l'opzione `forEmbeddedResources` per incorporare le risorse HTML.  
- **È possibile la conversione batch?** Assolutamente; è possibile iterare su una collezione di archivi e renderizzare ciascuno con le stesse impostazioni.  
- **È necessario Maven per usare GroupDocs.Viewer?** Sì, aggiungi la dipendenza Maven `groupdocs-viewer` come mostrato di seguito.  
- **Quali formati di output sono supportati?** Sono disponibili HTML a pagina singola e HTML a più pagine, e la libreria supporta oltre 50 tipi di archivio in ingresso.

## Cos'è “set items per page” in GroupDocs.Viewer?
Indica al viewer quante voci dell'archivio (file o cartelle) devono essere visualizzate su ciascuna pagina HTML quando si genera un documento multi‑pagina. Regolare questo valore aiuta a bilanciare la dimensione della pagina e la velocità di navigazione, soprattutto per archivi di grandi dimensioni, limitando la quantità di dati caricati per pagina e riducendo il tempo di rendering per gli utenti finali.

## Perché incorporare le risorse html?
Incorporare le risorse (immagini, CSS, font) direttamente nel file HTML crea un documento unico e portatile che può essere aperto senza file esterni. È ideale per allegati email, visualizzazione offline o per incorporare l'output in altre pagine web. Rimuove inoltre la necessità di gestire percorsi di risorse esterne.

## Prerequisiti

- **Librerie richieste:** Includi GroupDocs.Viewer versione 25.2 o successiva.  
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
GroupDocs.Viewer offre un **link per la prova gratuita**, una licenza temporanea o un'opzione di acquisto completo. Scegli quella che si adatta alla tempistica del tuo progetto.

## Inizializzazione di base
La classe `Viewer` è il punto di ingresso per il rendering di documenti e archivi. Dopo la configurazione Maven, porta il viewer nel tuo codice:

```java
import com.groupdocs.viewer.Viewer;
// Your initialization code here
```

## Come renderizzare archivi in HTML a pagina singola
La classe `HtmlViewOptions` definisce le impostazioni per l'output HTML, come l'incorporamento delle risorse. Carica l'archivio, configura le opzioni HTML per incorporare le risorse e renderizza tutto in una pagina autonoma. Questo produce un singolo file HTML che contiene tutti i file, le immagini, i CSS e i font, pronto per l'uso offline o come allegato email.

**Risposta diretta:** Crea un'istanza `Viewer` per il file ZIP, chiama `HtmlViewOptions.forEmbeddedResources()`, e invoca `viewer.view(documentPath, options)`. Questo produce un singolo file HTML che contiene tutti i file, le immagini, i CSS e i font, pronto per l'uso offline o come allegato email.

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

### Passo 4: Configura le opzioni di rendering (incorpora risorse html)
La classe `HtmlViewOptions` definisce le impostazioni per l'output HTML, come l'incorporamento delle risorse. Usa `forEmbeddedResources()` per raggruppare tutto in un unico file.

```java
HtmlViewOptions options = HtmlViewOptions.forEmbeddedResources(pageFilePathFormat);
```

### Passo 5: Renderizza come pagina singola
```java
options.setRenderToSinglePage(true);
viewer.view(options);
```

## Come renderizzare archivi in HTML a più pagine e impostare gli elementi per pagina
La classe `HtmlViewOptions` supporta anche la paginazione. Chiamando `options.setItemsPerPage(N)`, istruisci il viewer a suddividere l'archivio in diversi file HTML, ognuno dei quali mostra fino a **N** voci. Questo approccio migliora la velocità di navigazione per archivi di grandi dimensioni mantenendo ogni pagina leggera.

**Risposta diretta:** Usa `HtmlViewOptions.forEmbeddedResources()`, chiama `options.setItemsPerPage(N)`, e renderizza l'archivio. Il viewer genererà file HTML separati—uno per pagina—ognuno contenente fino a **N** voci, velocizzando la navigazione per archivi voluminosi.

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

### Passo 4: Configura le opzioni multi‑pagina (incorpora risorse html)
```java
HtmlViewOptions options = HtmlViewOptions.forEmbeddedResources(pageFilePathFormat);
```

### Passo 5: Imposta gli elementi per pagina (parola chiave principale nell'azione)
`options.setItemsPerPage(20); // come convertire archivi zip con 20 voci per pagina`

```java
options.getArchiveOptions().setItemsPerPage(10); // Default is 16
viewer.view(options);
```

## Applicazioni pratiche

- **Sistemi di gestione documentale:** Aggiungi la funzionalità di anteprima degli archivi senza installare visualizzatori aggiuntivi.  
- **Portali web:** Offri agli utenti un modo rapido, senza download, per esplorare documenti raggruppati.  
- **Strumenti di collaborazione:** Consenti ai team di ispezionare gli archivi condivisi direttamente nel browser.

## Considerazioni sulle prestazioni

- **Gestione delle risorse:** Mantieni basso l'uso della memoria elaborando gli archivi in streaming; il viewer può gestire archivi fino a 500 MB senza caricare l'intero file in memoria.  
- **Conversione batch di archivi:** Scorri un elenco di file archivio e chiama la stessa logica di rendering per massimizzare il throughput.  
- **Strategia di caching:** Memorizza l'HTML renderizzato in una cache se lo stesso archivio viene richiesto frequentemente, riducendo il tempo di elaborazione ripetuta fino al 70 %.

## Domande frequenti

**Q: Cos'è GroupDocs.Viewer Java?**  
A: GroupDocs.Viewer Java è una libreria server‑side che rende più di 50 formati di documenti e archivi—including ZIP e RAR—in HTML, PDF o file immagine senza richiedere applicazioni esterne.

**Q: Come posso ottenere una prova gratuita di GroupDocs.Viewer?**  
A: Visita il [link per la prova gratuita](https://releases.groupdocs.com/viewer/java/) per scaricare e testare.

**Q: Posso convertire altri tipi di documento oltre agli archivi?**  
A: Sì, il viewer supporta PDF, Word, Excel, PowerPoint e oltre 35 formati aggiuntivi.

**Q: Cosa devo fare se il rendering è lento?**  
A: Riduci il numero di elementi per pagina, abilita lo streaming o elabora gli archivi in batch più piccoli per migliorare la velocità.

**Q: Dove posso ottenere aiuto o supporto?**  
A: Rivolgiti al [forum di supporto](https://forum.groupdocs.com/c/viewer/9).

**Q: È possibile incorporare CSS e immagini direttamente nell'HTML?**  
A: Assolutamente—usa `HtmlViewOptions.forEmbeddedResources` come mostrato negli esempi.

**Q: Come faccio a convertire in batch una cartella di archivi?**  
A: Itera su ogni file con un ciclo `for`, applicando la stessa configurazione `Viewer` e `HtmlViewOptions` per ogni iterazione.

**Q: Dove posso discutere problemi con altri utenti?**  
A: Visita il [forum GroupDocs](https://forum.groupdocs.com/c/viewer/9) per discussioni della community.

## Risorse

- **Documentazione:** Approfondisci le funzionalità con la [documentazione GroupDocs](https://docs.groupdocs.com/viewer/java/).  
- **Riferimento API:** Esplora l'API completa su [GroupDocs API](https://reference.groupdocs.com/viewer/java/).  
- **Download:** Ottieni gli ultimi binari dalla [pagina di download](https://releases.groupdocs.com/viewer/java/).  
- **Acquisto e licenze:** Consulta le opzioni nella [pagina di acquisto](https://purchase.groupdocs.com/buy).  
- **Supporto e community:** Partecipa alle discussioni sul [forum di supporto](https://forum.groupdocs.com/c/viewer/9).  
- **Forum GroupDocs:** Accedi all'aiuto della community sul [forum GroupDocs](https://forum.groupdocs.com/c/viewer/9).

---

**Last Updated:** 2026-10-10  
**Tested With:** GroupDocs.Viewer 25.2  
**Author:** GroupDocs

## Tutorial correlati

- [Come convertire zip in HTML e renderizzare cartelle zip in Java con GroupDocs.Viewer](/viewer/java/advanced-rendering/render-archive-folders-groupdocs-viewer-java/)
- [converti zip in pdf con GroupDocs.Viewer Java - Nomi file personalizzati](/viewer/java/advanced-rendering/groupdocs-viewer-java-custom-filenames-rendering-archives/)
- [Come convertire DOCX in HTML usando GroupDocs.Viewer per Java: Guida passo‑passo](/viewer/java/export-conversion/convert-docx-to-html-groupdocs-viewer-java/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}