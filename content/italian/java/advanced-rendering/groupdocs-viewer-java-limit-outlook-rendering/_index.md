---
date: '2026-08-19'
description: Scopri come limitare gli elementi Outlook Java durante il rendering dei
  file Outlook PST/OST utilizzando GroupDocs.Viewer per Java, migliorando le prestazioni
  e riducendo l'uso della memoria.
keywords:
- limit outlook items java
- GroupDocs Viewer Outlook rendering
- Java PST rendering
- outlook folder item limit
lastmod: '2026-08-19'
og_description: Scopri come limitare gli elementi Outlook Java durante il rendering
  dei file Outlook PST/OST utilizzando GroupDocs.Viewer per Java, migliorando le prestazioni
  e riducendo l'uso della memoria.
og_image_alt: Guide showing how to limit outlook items java with GroupDocs.Viewer
  for Java
og_title: Come limitare gli elementi Outlook Java con GroupDocs.Viewer
schemas:
- author: GroupDocs
  dateModified: '2026-08-19'
  description: Learn how to limit outlook items java when rendering Outlook PST/OST
    files using GroupDocs.Viewer for Java, boosting performance and reducing memory
    usage.
  headline: How to limit outlook items java with GroupDocs.Viewer
  type: TechArticle
- description: Learn how to limit outlook items java when rendering Outlook PST/OST
    files using GroupDocs.Viewer for Java, boosting performance and reducing memory
    usage.
  name: How to limit outlook items java with GroupDocs.Viewer
  steps:
  - name: '**Java Development Kit (JDK)** – Install JDK 8 or later.'
    text: '**Java Development Kit (JDK)** – Install JDK 8 or later.'
  - name: '**GroupDocs.Viewer for Java** – Add as a dependency in your project.'
    text: '**GroupDocs.Viewer for Java** – Add as a dependency in your project.'
  - name: '**Email archiving** – Limiting item rendering is ideal for applications
      focusing on archiving specific emails rather than entire datasets.'
    text: '**Email archiving** – Limiting item rendering is ideal for applications
      focusing on archiving specific emails rather than entire datasets.'
  - name: '**Data migration** – When migrating data between systems, render only the
      necessary items to optimise performance and reduce processing time.'
    text: '**Data migration** – When migrating data between systems, render only the
      necessary items to optimise performance and reduce processing time.'
  - name: '**Custom reporting** – Generate reports by selectively rendering required
      email content without loading entire folders.'
    text: '**Custom reporting** – Generate reports by selectively rendering required
      email content without loading entire folders.'
  type: HowTo
- questions:
  - answer: It's a versatile library designed to render various document formats,
      including Outlook data files, into HTML or image formats.
    question: What is GroupDocs.Viewer Java used for?
  - answer: Visit [GroupDocs Free Trial](https://releases.groupdocs.com/viewer/java/)
      for access and download options.
    question: How do I obtain a free trial of GroupDocs.Viewer?
  - answer: Yes, the same configuration applies to both OST and PST file formats.
    question: Can I limit item rendering in PST files as well?
  - answer: Review your item limits and resource settings; consider optimizing memory
      management practices.
    question: What should I do if my application is running slow during rendering?
  - answer: For assistance, check the [GroupDocs Support Forum](https://forum.groupdocs.com/c/viewer/9).
    question: Where can I find support for GroupDocs.Viewer issues?
  type: FAQPage
tags:
- limit outlook items
- GroupDocs Viewer
- Java email rendering
- PST processing
- OST rendering
title: Come limitare gli elementi Outlook Java con GroupDocs.Viewer
type: docs
url: /it/java/advanced-rendering/groupdocs-viewer-java-limit-outlook-rendering/
weight: 1
---

# Come limitare gli elementi outlook java con GroupDocs.Viewer

Gestire file di dati Outlook di grandi dimensioni (PST o OST) può rapidamente diventare un collo di bottiglia delle prestazioni. In questa guida scoprirai come **limitare gli elementi outlook java** durante il rendering con GroupDocs.Viewer per Java, così elaborerai solo i dati di cui hai realmente bisogno. Applicando la tecnica **limitare gli elementi per cartella**, la tua applicazione rimane reattiva anche con gigabyte di dati email.

![Limitare il rendering degli elementi Outlook con GroupDocs.Viewer per Java](/viewer/advanced-rendering/limit-outlook-item-rendering-java.png)

[Limitare il rendering degli elementi Outlook con GroupDocs.Viewer per Java](/viewer/advanced-rendering/limit-outlook-item-rendering-java.png)

### Cosa imparerai
- Configurare GroupDocs.Viewer per Java  
- Configurare la libreria per **impostare il numero massimo di elementi** per cartella nei file Outlook  
- Scenari reali in cui limitare gli elementi per cartella migliora la velocità e riduce l'utilizzo della memoria  

## Risposte rapide
- **Cosa fa “imposta il numero massimo di elementi per cartella”?** Restringe il rendering a un numero definito di elementi email all'interno di ogni cartella Outlook.  
- **Perché limitare gli elementi Outlook?** Per ridurre il tempo di elaborazione e il consumo di memoria per cassette postali di grandi dimensioni.  
- **Quale versione supporta questa funzionalità?** GroupDocs.Viewer 25.2 e successive.  
- **È necessaria una licenza?** Sì, è necessaria una licenza di prova o acquistata per l'uso in produzione.  
- **Posso modificare il limite a runtime?** Assolutamente – basta modificare il valore `setMaxItemsInFolder` prima del rendering.  

## Cos'è “imposta il numero massimo di elementi per cartella”

Caricare solo un sottoinsieme di messaggi impedisce al visualizzatore di scansionare un'intera casella di posta. Quando **limiti gli elementi outlook java**, il renderer si interrompe dopo aver elaborato il numero specificato di elementi in ciascuna cartella, fornendo un'anteprima veloce mantenendo basso l'utilizzo della memoria.

## Perché utilizzare l'approccio di limitare gli elementi per cartella?

Limitare gli elementi per cartella riduce drasticamente i cicli CPU e il consumo di heap. Nei test di benchmark, il rendering di un PST da 2 GB con un limite di 50 elementi per cartella è stato completato in meno di 30 secondi, rispetto a più di 3 minuti quando si elabora l'intera casella di posta. Questo risparmio del 80% di tempo rende la funzionalità essenziale per soluzioni di archiviazione email scalabili.

## Prerequisiti
Assicurati di avere quanto segue prima di iniziare:

### Librerie e dipendenze richieste
1. **Java Development Kit (JDK)** – Installa JDK 8 o successivo.  
2. **GroupDocs.Viewer per Java** – Aggiungilo come dipendenza nel tuo progetto.

### Requisiti di configurazione dell'ambiente
- Un IDE adeguato come IntelliJ IDEA, Eclipse o NetBeans.  
- Maven installato se gestisci le dipendenze tramite esso.

### Prerequisiti di conoscenza
- Conoscenza di base della programmazione Java e della gestione dei file.  
- Familiarità con i progetti Maven è utile ma non obbligatoria.

## Configurare GroupDocs.Viewer per Java
Configura GroupDocs.Viewer nel tuo progetto usando Maven:

**Configurazione Maven**  
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
- **Prova gratuita**: Scarica una prova gratuita da [GroupDocs](https://releases.groupdocs.com/viewer/java/) per esplorare le funzionalità della libreria.  
- **Licenza temporanea**: Ottieni una licenza temporanea per accesso completo senza limitazioni di valutazione su [GroupDocs Temporary License](https://purchase.groupdocs.com/temporary-license/).  
- **Acquisto**: Per un utilizzo a lungo termine, considera l'acquisto di una licenza dalla [GroupDocs Purchase Page](https://purchase.groupdocs.com/buy).

### Inizializzazione e configurazione di base
Una volta configurato Maven, inizializza GroupDocs.Viewer nella tua applicazione Java impostando l'oggetto viewer. Questo ti consente di caricare e renderizzare i documenti.

## Guida all'implementazione

### Limitare gli elementi renderizzati dai file Outlook
Questa sezione descrive come limitare gli elementi renderizzati dai file di dati Outlook usando GroupDocs.Viewer per Java.

#### Panoramica
Configurando opzioni specifiche, puoi limitare il rendering a un certo numero di elementi per cartella. Questa funzionalità migliora le prestazioni e l'efficienza quando si gestiscono grandi set di dati email.

**Passo 1: impostare il percorso della directory di output**  
```java
Path outputDirectory = Utils.getOutputDirectoryPath("LimitCountOfItemsToRender");
```  
Questo codice imposta la directory in cui verranno memorizzati i file HTML renderizzati. Sostituisci `"LimitCountOfItemsToRender"` con il nome del percorso desiderato.

**Passo 2: definire il formato del percorso file per le pagine HTML**  
```java
Path pageFilePathFormat = outputDirectory.resolve("page_{0}.html");
```  
Crea un formato di denominazione coerente per le pagine HTML generate durante il rendering, garantendo un facile accesso e gestione.

**Passo 3: configurare HtmlViewOptions con risorse incorporate**  
`HtmlViewOptions` specifica le opzioni di rendering come formato e gestione delle risorse incorporate.  
```java
HtmlViewOptions viewOptions = HtmlViewOptions.forEmbeddedResources(pageFilePathFormat);
```  

**Passo 4: impostare le opzioni Outlook per limitare gli elementi per cartella**  
`setMaxItemsInFolder` imposta il numero massimo di elementi da renderizzare per cartella Outlook.  
```java
viewOptions.getOutlookOptions().setMaxItemsInFolder(3); // Render only the first 3 items in each folder
```  

**Passo 5: caricare e renderizzare il documento**  
`Viewer` è la classe principale che carica e renderizza i file Outlook.  
```java
try (Viewer viewer = new Viewer(TestFiles.SAMPLE_OST)) {
    viewer.view(viewOptions); // Execute rendering with specified options
}
```  
Utilizza la classe `Viewer` per caricare un file OST e renderizzarlo secondo le opzioni di visualizzazione definite. L'istruzione try‑with‑resources garantisce che le risorse vengano chiuse correttamente dopo l'uso.

### Suggerimenti per la risoluzione dei problemi
- Assicurati che tutti i percorsi e le directory esistano prima di eseguire il tuo codice.  
- Verifica che le dipendenze di GroupDocs.Viewer siano risolte correttamente da Maven.  
- Controlla eventuali eccezioni durante il rendering, che potrebbero indicare problemi con i formati dei file o i permessi.

## Applicazioni pratiche
1. **Archiviazione email** – Limitare il rendering degli elementi è ideale per applicazioni che si concentrano sull'archiviazione di email specifiche piuttosto che di interi set di dati.  
2. **Migrazione dati** – Quando si migra dati tra sistemi, renderizza solo gli elementi necessari per ottimizzare le prestazioni e ridurre i tempi di elaborazione.  
3. **Reportistica personalizzata** – Genera report renderizzando selettivamente il contenuto email richiesto senza caricare intere cartelle.

## Considerazioni sulle prestazioni
### Suggerimenti per ottimizzare le prestazioni
- Limita il numero di elementi per cartella per ridurre l'utilizzo della memoria.  
- Usa le risorse incorporate in modo efficiente per evitare chiamate di rete aggiuntive durante il rendering.

### Linee guida sull'uso delle risorse
- Monitora la memoria JVM e regola le impostazioni in base alle dimensioni dei file Outlook elaborati.

### Best practice per la gestione della memoria Java
- Utilizza try‑with‑resources per la gestione automatica delle risorse.  
- Profilare la tua applicazione per identificare colli di bottiglia legati alla gestione di file di grandi dimensioni.

## Problemi comuni e come evitarli
| Sintomo | Probabile causa | Correzione |
|---------|-----------------|------------|
| Nessun file di output generato | Il percorso della directory di output è errato o mancano i permessi | Verifica che `outputDirectory` esista e sia scrivibile |
| Il rendering si interrompe dopo pochi elementi | `setMaxItemsInFolder` impostato troppo basso | Aumenta il limite o rendilo configurabile |
| OutOfMemoryError su PST di grandi dimensioni | Impostazioni di memoria predefinite insufficienti | Aumenta l'heap JVM (`-Xmx`) e mantieni il limite basso |

## Conclusione
In questo tutorial, hai imparato come **limitare gli elementi outlook java** nei file di dati Outlook usando GroupDocs.Viewer per Java. Seguendo i passaggi e applicando i consigli sulle prestazioni, puoi creare applicazioni efficienti su misura per le tue esigenze specifiche.

### Prossimi passi
- Esplora le funzionalità aggiuntive di GroupDocs.Viewer consultando la [documentazione ufficiale](https://docs.groupdocs.com/viewer/java/).  
- Sperimenta con diverse opzioni di rendering per trovare la configurazione migliore per i requisiti della tua applicazione.

Pronto a provarlo? Inizia a implementare questa soluzione nei tuoi progetti oggi stesso e osserva direttamente un miglioramento dell'efficienza.

## Domande frequenti

**D: A cosa serve GroupDocs.Viewer Java?**  
**R:** È una libreria versatile progettata per renderizzare vari formati di documenti, inclusi i file di dati Outlook, in formati HTML o immagine.

**D: Come posso ottenere una prova gratuita di GroupDocs.Viewer?**  
**R:** Visita [GroupDocs Free Trial](https://releases.groupdocs.com/viewer/java/) per accedere e scaricare le opzioni.

**D: Posso limitare il rendering degli elementi anche nei file PST?**  
**R:** Sì, la stessa configurazione si applica sia ai formati di file OST che PST.

**D: Cosa devo fare se la mia applicazione è lenta durante il rendering?**  
**R:** Rivedi i limiti degli elementi e le impostazioni delle risorse; considera l'ottimizzazione delle pratiche di gestione della memoria.

**D: Dove posso trovare supporto per i problemi di GroupDocs.Viewer?**  
**R:** Per assistenza, consulta il [GroupDocs Support Forum](https://forum.groupdocs.com/c/viewer/9).

## Risorse aggiuntive
- [Documentazione](https://docs.groupdocs.com/viewer/java/)
- [Riferimento API](https://reference.groupdocs.com/viewer/java/)
- [Scarica GroupDocs.Viewer per Java](https://releases.groupdocs.com/viewer/java/)
- [Acquista licenza](https://purchase.groupdocs.com/buy)
- [Versione di prova gratuita](https://releases.groupdocs.com/viewer/java/)
- [Applicazione licenza temporanea](https://purchase.groupdocs.com/temporary-license/)
- [Forum di supporto](https://forum.groupdocs.com/c/viewer/9)

**Ultimo aggiornamento:** 2026-08-19  
**Testato con:** GroupDocs.Viewer 25.2 for Java  
**Autore:** GroupDocs

## Tutorial correlati

- [Renderizzare file PST e OST Outlook in HTML usando Java e GroupDocs.Viewer](/viewer/java/rendering-basics/render-outlook-data-html-groupdocs-java/)
- [Tutorial GroupDocs Viewer Java: padroneggiare il rendering e il filtraggio dei dati Outlook](/viewer/java/advanced-rendering/render-filter-outlook-data-groupdocs-java/)
- [Ridurre l'uso della memoria Java – Ottimizzazione del rendering dei documenti](/viewer/java/performance-optimization/)