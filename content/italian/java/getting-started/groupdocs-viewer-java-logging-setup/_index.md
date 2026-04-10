---
date: '2026-04-10'
description: Scopri come configurare il logging in GroupDocs.Viewer per Java, incluso
  come aggiungere il logger della console e il logger su file per migliorare il rendering
  dei documenti.
keywords:
- how to configure logging
- add console logger
- add file logger
- java logging best practices
- html view options
title: Come configurare il logging in GroupDocs.Viewer per Java
type: docs
url: /it/java/getting-started/groupdocs-viewer-java-logging-setup/
weight: 1
---

# Come configurare il logging in GroupDocs.Viewer per Java

In questo tutorial, imparerai **come configurare il logging** in GroupDocs.Viewer per Java, che ti fornisce informazioni in tempo reale sul pipeline di rendering dei documenti e ti aiuta a risolvere rapidamente i problemi.

## Risposte rapide
- **Cosa fornisce il logging?** Feedback in tempo reale sulle operazioni di rendering e dettagli degli errori.  
- **Quale logger stampa sulla console?** `ConsoleLogger` (aggiungi logger console).  
- **Quale logger scrive su un file?** `FileLogger` (aggiungi logger file).  
- **È necessaria una licenza per abilitare il logging?** No, il logging funziona sia con la versione di prova sia con quella con licenza.  
- **Posso personalizzare il formato del log?** Sì, estendendo le classi logger.

## Introduzione
Migliora il processo di rendering dei documenti nelle applicazioni Java utilizzando **GroupDocs.Viewer per Java**. Questa guida ti accompagna nella configurazione del logging, sia sulla console che su un file, fornendo informazioni cruciali su come funziona il rendering dei tuoi documenti.

![Console e File Logging con GroupDocs.Viewer per Java](/viewer/getting-started/console-and-file-logging-java.png)

**Punti chiave di apprendimento:**
- Configurare il logging in GroupDocs.Viewer per Java.  
- Implementare sistemi di logging sia su console sia basati su file.  
- Renderizzare i documenti in HTML con risorse incorporate usando GroupDocs.Viewer.

## Prerequisiti
Assicurati di avere:
1. **Librerie richieste:**  
   - Libreria GroupDocs.Viewer per Java (versione 25.2 o successiva).  

2. **Requisiti di configurazione dell'ambiente:**  
   - Un Java Development Kit (JDK) installato sul tuo sistema.  
   - Un Integrated Development Environment (IDE) come IntelliJ IDEA o Eclipse.  

3. **Prerequisiti di conoscenza:**  
   - Comprensione di base della programmazione Java.  
   - Familiarità con Maven per la gestione delle dipendenze.  

Con questi prerequisiti in ordine, sei pronto per configurare GroupDocs.Viewer per Java!

## Configurazione di GroupDocs.Viewer per Java
Per utilizzare GroupDocs.Viewer, aggiungilo come dipendenza nel tuo progetto usando Maven. Ecco come:

### Configurazione Maven
Aggiungi la seguente configurazione nel tuo file `pom.xml`:
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
- **Prova gratuita:** Scarica una prova gratuita da [GroupDocs Releases](https://releases.groupdocs.com/viewer/java/).  
- **Licenza temporanea:** Ottieni una licenza temporanea per rimuovere le limitazioni di valutazione su [GroupDocs Temporary License](https://purchase.groupdocs.com/temporary-license/).  
- **Acquisto:** Per accesso completo, considera l'acquisto di una licenza su [GroupDocs Purchase](https://purchase.groupdocs.com/buy).

### Inizializzazione di base
Inizializza GroupDocs.Viewer con il seguente modello:
```java
import com.groupdocs.viewer.Viewer;
import com.groupdocs.viewer.options.HtmlViewOptions;

// Initialize with sample PDF file and settings
try (Viewer viewer = new Viewer("path/to/your/document.pdf")) {
    HtmlViewOptions options = HtmlViewOptions.forEmbeddedResources("output_directory/page_{0}.html");
    viewer.view(options);
}
```

Questa configurazione costituisce la base per configurazioni di logging più complesse.

## Come configurare il logging
Scopri come **aggiungere il logger console** e **aggiungere il logger file** con GroupDocs.Viewer.

### Funzione 1: Logging su console
#### Panoramica
Il logging su console fornisce feedback immediato nel tuo terminale, utile durante le fasi di sviluppo o debug.

#### Passaggi
##### Passo 1: Importa le classi necessarie
```java
import com.groupdocs.viewer.Viewer;
import com.groupdocs.viewer.ViewerSettings;
import com.groupdocs.viewer.logging.ConsoleLogger;
import com.groupdocs.viewer.options.HtmlViewOptions;
```

##### Passo 2: Configura il logging
Usa `ConsoleLogger` per indirizzare i log alla console.
```java
try (Viewer viewer = new Viewer("path/to/your/document.pdf", 
    new ViewerSettings(new ConsoleLogger()))) {
    HtmlViewOptions options = HtmlViewOptions.forEmbeddedResources("output_directory/page_{0}.html");
    viewer.view(options);
}
```
**Spiegazione**  
- **ConsoleLogger:** Questa classe indirizza i log alla console, fornendo una visualizzazione in tempo reale delle operazioni.  
- **HtmlViewOptions.forEmbeddedResources:** Genera HTML con risorse incorporate per ogni pagina, un esempio di utilizzo efficace delle **html view options**.

#### Suggerimenti per la risoluzione dei problemi
Assicurati che il percorso del documento sia corretto e accessibile. Verifica che le istruzioni di logging siano configurate correttamente nelle impostazioni della console.

### Funzione 2: Logging su file
#### Panoramica
Il logging su file aiuta a mantenere un registro persistente delle operazioni, utile per audit o analisi post‑mortem.

#### Passaggi
##### Passo 1: Importa le classi necessarie
```java
import com.groupdocs.viewer.Viewer;
import com.groupdocs.viewer.ViewerSettings;
import com.groupdocs.viewer.logging.FileLogger;
import com.groupdocs.viewer.options.HtmlViewOptions;
```

##### Passo 2: Configura il logging basato su file
Usa `FileLogger` per scrivere i log in un file specificato.
```java
try (Viewer viewer = new Viewer("path/to/your/document.pdf", 
    new ViewerSettings(new FileLogger("output.log")))) {
    HtmlViewOptions options = HtmlViewOptions.forEmbeddedResources("output_directory/page_{0}.html");
    viewer.view(options);
}
```
**Spiegazione**  
- **FileLogger:** Questa classe indirizza i log a un file chiamato `output.log`.  
- **ViewerSettings con FileLogger:** Configura GroupDocs.Viewer per **catturare i log del viewer** nel file di log specificato.

#### Suggerimenti per la risoluzione dei problemi
Assicurati che la directory per il file di output sia scrivibile. Controlla i permessi del file se il logging fallisce.

## Applicazioni pratiche
GroupDocs.Viewer può migliorare la gestione dei documenti e le capacità di rendering:
1. **Portali web:** Renderizza i documenti al volo per gli utenti web senza download diretti.  
2. **Sistemi aziendali:** Integra con strumenti CRM per visualizzare contratti o accordi.  
3. **Dashboard interne:** Fornisci visualizzazioni accessibili di report e presentazioni all'interno delle intranet.

## Considerazioni sulle prestazioni e migliori pratiche di logging Java
Quando utilizzi GroupDocs.Viewer in Java, tieni presenti questi punti:
- **Ottimizza l'uso delle risorse:** Monitora il consumo di memoria durante il rendering di documenti di grandi dimensioni.  
- **Gestione della memoria Java:** Utilizza try‑with‑resources per la pulizia automatica delle risorse.  
- **Verbosità del logging:** Regola i livelli del logger (es. INFO, DEBUG) per bilanciare i dettagli con l'impatto sulle prestazioni—una parte essenziale delle **migliori pratiche di logging Java**.

## Conclusione
Hai imparato **come configurare il logging** in GroupDocs.Viewer per Java, sia che tu abbia bisogno di una rapida visualizzazione su console sia di un registro persistente su file. Questa capacità è inestimabile per il debug, il monitoraggio e l'audit delle tue applicazioni. Esplora ulteriori configurazioni, sperimenta logger personalizzati e integra GroupDocs.Viewer con altri sistemi per aumentare la robustezza.

Pronto a portare le tue competenze di implementazione al livello successivo? Prova a configurare il logging in ambienti diversi e osserva come migliora l'affidabilità della tua applicazione!

## Risorse
- [Documentazione](https://docs.groupdocs.com/viewer/java/)
- [Riferimento API](https://reference.groupdocs.com/viewer/java/)
- [Download](https://downloads.groupdocs.com/viewer/java/)

---

**Ultimo aggiornamento:** 2026-04-10  
**Testato con:** GroupDocs.Viewer 25.2 for Java  
**Autore:** GroupDocs