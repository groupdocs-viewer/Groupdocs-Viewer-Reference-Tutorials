---
date: '2026-01-10'
description: Scopri come convertire EML in HTML con formato data/ora personalizzato
  e impostare il fuso orario in Java usando GroupDocs.Viewer. Ideale per l'archiviazione
  di email e i sistemi di supporto.
keywords:
- render emails with custom datetime
- GroupDocs Viewer for Java
- email rendering HTML
title: Converti EML in HTML con Data/Ora personalizzata in Java usando GroupDocs.Viewer
type: docs
url: /it/java/advanced-rendering/render-emails-custom-datetime-groupdocs-viewer-java/
weight: 1
---

# Converti EML in HTML con Data/Ora personalizzata in Java usando GroupDocs.Viewer

## Introduzione

Nel mondo digitale odierno, veloce, la capacità di **convertire EML in HTML** rapidamente e con la corretta presentazione della data‑ora è essenziale per l'archiviazione, i portali di supporto e la conformità legale. Questo tutorial ti guida nella resa dei messaggi email in HTML applicando un **formato data/ora personalizzato** e un **offset del fuso orario** usando GroupDocs.Viewer per Java. Alla fine, avrai una soluzione riutilizzabile che mantiene i timestamp accurati e leggibili.

![Render Emails with Custom DateTime with GroupDocs.Viewer for Java](/viewer/advanced-rendering/render-emails-with-custom-datetime-java.png)

**Cosa imparerai**
- Come configurare GroupDocs.Viewer in un progetto Java  
- Come rendere le email in HTML con risorse incorporate  
- Come **personalizzare il formato data‑ora** dei tuoi messaggi email (custom datetime format java)  
- Come **impostare l'offset del fuso orario** per timestamp corretti (set timezone offset java)  

## Risposte rapide
- **GroupDocs.Viewer può convertire EML in HTML?** Sì, rende i file EML direttamente in HTML.  
- **È necessaria una licenza?** Una prova gratuita è sufficiente per i test; è necessaria una licenza a pagamento per la produzione.  
- **Quale versione di Java è richiesta?** Java 8 o successiva.  
- **Come modifico il formato della data visualizzata?** Usa `options.getEmailOptions().setDateTimeFormat(...)`.  
- **Posso regolare il fuso orario?** Sì, con `options.getEmailOptions().setTimeZoneOffset(TimeZone.getTimeZone(...))`.

## Cos'è “convertire EML in HTML”?
Convertire un file EML in HTML trasforma l'email grezza (inclusi header, corpo e allegati) in un formato web‑friendly che i browser possono visualizzare senza plugin aggiuntivi. Questo rende facile incorporare le email in applicazioni web, archivi o dashboard di supporto.

## Perché usare GroupDocs.Viewer per questo compito?
- **Rendering senza dipendenze** – non è necessario Outlook o parser di posta esterni.  
- **Supporto integrato per risorse incorporate** (immagini, allegati).  
- **Controllo granulare** sul formato data‑ora e sulla gestione del fuso orario.  

## Prerequisiti

- **GroupDocs.Viewer for Java** versione 25.2 o successiva.  
- **Java Development Kit (JDK)** 8+ e un IDE (IntelliJ IDEA, Eclipse, ecc.).  
- Conoscenze di base di Java e familiarità con Maven.

## Configurazione di GroupDocs.Viewer per Java

### Configurazione Maven
Aggiungi il repository GroupDocs e la dipendenza al tuo `pom.xml`:

```xml
<repositories>
    <repository>
        <id>groupdocs-releases</id>
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
Inizia con una prova gratuita o richiedi una licenza temporanea per test più estesi. Acquista una licenza completa per l'uso in produzione.

### Inizializzazione di base
```java
import com.groupdocs.viewer.Viewer;

// Initialize Viewer with the path to your document
try (Viewer viewer = new Viewer("path/to/your/document.eml")) {
    // Perform operations here
}
```

## Converti EML in HTML con Data/Ora personalizzata in Java

La guida passo‑a‑passo seguente mostra come **convertire EML in HTML** applicando un formato data/ora personalizzato e un offset del fuso orario.

### Passo 1: Configura la directory di output e il percorso del file
```java
import java.nio.file.Path;

Path outputDirectory = Path.of("YOUR_OUTPUT_DIRECTORY");
Path filePath = outputDirectory.resolve("output.html");
```
*Spiegazione:* `Path.of()` crea un riferimento alla cartella in cui verrà salvato l'HTML. `resolve()` aggiunge il nome del file.

### Passo 2: Inizializza Viewer con il file email
```java
import com.groupdocs.viewer.Viewer;

try (Viewer viewer = new Viewer("YOUR_DOCUMENT_DIRECTORY/SAMPLE_EML")) {
    // Further configuration goes here
}
```
*Spiegazione:* L'istanza `Viewer` punta al file EML che desideri convertire.

### Passo 3: Configura HtmlViewOptions
```java
import com.groupdocs.viewer.options.HtmlViewOptions;

HtmlViewOptions options = HtmlViewOptions.forEmbeddedResources(filePath);
```
*Spiegazione:* `forEmbeddedResources()` raggruppa immagini e altre risorse direttamente nell'output HTML.

### Passo 4: Imposta il formato Data/Ora personalizzato *(custom datetime format java)*
```java
options.getEmailOptions().setDateTimeFormat("MM d yyyy HH:mm tt zzz");
```
*Spiegazione:* Questo pattern visualizza mese, giorno, anno, ora, minuti, indicatore AM/PM e l'offset del fuso orario (`zzz`).

### Passo 5: Imposta l'offset del fuso orario *(set timezone offset java)*
```java
import java.util.TimeZone;

options.getEmailOptions().setTimeZoneOffset(TimeZone.getTimeZone("GMT+1"));
```
*Spiegazione:* Regola i timestamp renderizzati al fuso orario desiderato. Sostituisci `"GMT+1"` con qualsiasi identificatore di zona valido.

### Passo 6: Renderizza il documento
```java
viewer.view(options);
```
*Spiegazione:* Esegue la conversione, producendo un file HTML con le impostazioni di data‑ora personalizzate.

## Suggerimenti per la risoluzione dei problemi
- **FileNotFoundException:** Controlla nuovamente i percorsi usati in `Viewer` e `Path.of()`.  
- **Timestamp errati:** Verifica che l'ID `TimeZone` corrisponda alla tua regione di destinazione.  
- **Immagini mancanti:** Assicurati di aver usato `HtmlViewOptions.forEmbeddedResources()`; altrimenti le risorse esterne potrebbero non essere incluse.  

## Applicazioni pratiche
1. **Archiviazione email:** Conserva snapshot HTML ricercabili delle email per la conformità.  
2. **Portali di supporto clienti:** Mostra i ticket in arrivo con orari locali accurati.  
3. **Documentazione legale:** Produci registrazioni email pronte per il tribunale con timestamp standardizzati.  

## Considerazioni sulle prestazioni
- Distribuisci su un server dedicato per conversioni in blocco.  
- Monitora l'utilizzo dell'heap Java; aumenta `-Xmx` se incontri `OutOfMemoryError`.  
- Cache l'HTML renderizzato quando la stessa email viene richiesta più volte.  

## Conclusione
Ora disponi di un metodo completo, pronto per la produzione, per **convertire EML in HTML** con un formato data/ora personalizzato e un offset del fuso orario usando GroupDocs.Viewer per Java. Questo migliora la leggibilità, garantisce l'accuratezza dei timestamp e si integra perfettamente nei flussi di lavoro di archiviazione o supporto.

**Passi successivi:** Esplora ulteriori opzioni di Viewer come lo styling CSS, la paginazione o la conversione PDF per personalizzare ulteriormente l'output secondo le tue esigenze.

## Domande frequenti

**D: Come gestisco i file EML con allegati?**  
R: Gli allegati vengono incorporati automaticamente quando usi `HtmlViewOptions.forEmbeddedResources()`. Puoi anche estrarli tramite l'API Viewer, se necessario.

**D: Posso modificare il modello HTML o aggiungere CSS personalizzato?**  
R: Sì, dopo il rendering puoi modificare il file HTML generato o iniettare CSS programmaticamente prima del salvataggio.

**D: È possibile renderizzare più file EML in batch?**  
R: Avvolgi la logica di rendering in un ciclo e riutilizza la stessa istanza `HtmlViewOptions` per ogni file.

**D: Cosa fare se devo supportare altri formati email come MSG?**  
R: GroupDocs.Viewer supporta anche MSG, PST e altri contenitori email—basta cambiare l'estensione del file nel costruttore `Viewer`.

**D: È necessaria una licenza separata per ogni server?**  
R: La licenza è per distribuzione; consulta la guida di licenza GroupDocs per scenari multi‑server.

## Risorse

- [Documentation](https://docs.groupdocs.com/viewer/java/)
- [API Reference](https://reference.groupdocs.com/viewer/java/)
- [Download](https://releases.groupdocs.com/viewer/java/)
- [Purchase](https://purchase.groupdocs.com/buy)
- [Free Trial](https://releases.groupdocs.com/viewer/java/)
- [Temporary License](https://purchase.groupdocs.com/temporary-license/)
- [Support Forum](https://forum.groupdocs.com/c/viewer/9)

---

**Ultimo aggiornamento:** 2026-01-10  
**Testato con:** GroupDocs.Viewer 25.2 (Java)  
**Autore:** GroupDocs