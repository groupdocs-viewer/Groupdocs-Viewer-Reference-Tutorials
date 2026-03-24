---
date: '2026-03-24'
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

# Converti EML in HTML con DateTime personalizzato in Java usando GroupDocs.Viewer

Nel mondo digitale di oggi, sempre più veloce, la possibilità di **convertire EML in HTML** rapidamente e con la corretta presentazione della data‑ora è essenziale per l'archiviazione, i portali di supporto e la conformità legale. Questo tutorial ti guida nella resa dei messaggi email in HTML applicando un **formato datetime personalizzato** e un **offset del fuso orario** usando GroupDocs.Viewer per Java. Alla fine, avrai una soluzione riutilizzabile che mantiene i timestamp accurati e leggibili, perfetta per qualsiasi flusso di lavoro **email to HTML Java**.

![Render Emails with Custom DateTime with GroupDocs.Viewer for Java](/viewer/advanced-rendering/render-emails-with-custom-datetime-java.png)

**Cosa imparerai**
- Come configurare GroupDocs.Viewer in un progetto Java  
- Come rendere le email in HTML con risorse incorporate  
- Come **personalizzare il formato data‑ora** dei tuoi messaggi email (custom datetime java)  
- Come **impostare l'offset del fuso orario** per timestamp corretti (timezone offset java)  

## Risposte rapide
- **GroupDocs.Viewer può convertire EML in HTML?** Sì, rende i file EML direttamente in HTML.  
- **Ho bisogno di una licenza?** Una prova gratuita è sufficiente per i test; è necessaria una licenza a pagamento per la produzione.  
- **Quale versione di Java è richiesta?** Java 8 o superiore.  
- **Come modifico il formato della data visualizzata?** Usa `options.getEmailOptions().setDateTimeFormat(...)`.  
- **Posso regolare il fuso orario?** Sì, con `options.getEmailOptions().setTimeZoneOffset(TimeZone.getTimeZone(...))`.

## Cos'è “convertire EML in HTML”?
Convertire un file EML in HTML trasforma l'email grezza (inclusi header, corpo e allegati) in un formato web‑friendly che i browser possono visualizzare senza plugin aggiuntivi. Questo rende semplice incorporare le email in applicazioni web, archivi o dashboard di supporto.

## Perché usare GroupDocs.Viewer per questo compito?
- **Rendering senza dipendenze** – non è necessario Outlook o parser di posta esterni.  
- **Supporto integrato per risorse incorporate** (immagini, allegati).  
- **Controllo dettagliato** sul formato data‑ora e sulla gestione del fuso orario.  

## Prerequisiti
- **GroupDocs.Viewer for Java** versione 25.2 o successiva.  
- **Java Development Kit (JDK)** 8+ e un IDE (IntelliJ IDEA, Eclipse, ecc.).  
- Conoscenza di base di Java e familiarità con Maven.

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
Inizia con una prova gratuita o richiedi una licenza temporanea per test estesi. Acquista una licenza completa per l'uso in produzione.

### Inizializzazione di base
```java
import com.groupdocs.viewer.Viewer;

// Initialize Viewer with the path to your document
try (Viewer viewer = new Viewer("path/to/your/document.eml")) {
    // Perform operations here
}
```

## Converti EML in HTML con DateTime personalizzato in Java

La seguente guida passo‑passo mostra come **convertire EML in HTML** applicando un formato datetime personalizzato e un offset del fuso orario.

### Passo 1: Configura la directory di output e il percorso del file
```java
import java.nio.file.Path;

Path outputDirectory = Path.of("YOUR_OUTPUT_DIRECTORY");
Path filePath = outputDirectory.resolve("output.html");
```
*Spiegazione:* `Path.of()` crea un riferimento alla cartella dove verrà salvato l'HTML. `resolve()` aggiunge il nome del file.

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

### Passo 4: Imposta il formato DateTime personalizzato *(custom datetime java)*
```java
options.getEmailOptions().setDateTimeFormat("MM d yyyy HH:mm tt zzz");
```
*Spiegazione:* Questo pattern mostra mese, giorno, anno, ora, minuto, indicatore AM/PM e l'offset del fuso orario (`zzz`).

### Passo 5: Imposta l'offset del fuso orario *(timezone offset java)*
```java
import java.util.TimeZone;

options.getEmailOptions().setTimeZoneOffset(TimeZone.getTimeZone("GMT+1"));
```
*Spiegazione:* Regola i timestamp renderizzati al fuso orario desiderato. Sostituisci `"GMT+1"` con qualsiasi identificatore di zona valido.

### Come regolare il fuso orario dell'email in Java
Se hai bisogno di **regolare il fuso orario dell'email** oltre i semplici offset — ad esempio gestendo i cambiamenti dell'ora legale — puoi recuperare l'oggetto `TimeZone` appropriato dall'API `java.util.TimeZone` usando ID di regione come `"Europe/Paris"` o `"America/New_York"` e passarlo a `setTimeZoneOffset`. Questo garantisce che i timestamp delle email riflettano sempre l'ora locale corretta.

### Passo 6: Renderizza il documento
```java
viewer.view(options);
```
*Spiegazione:* Esegue la conversione, producendo un file HTML con le impostazioni di data‑ora personalizzate.

## Suggerimenti per la risoluzione dei problemi
- **FileNotFoundException:** Verifica nuovamente i percorsi usati in `Viewer` e `Path.of()`.  
- **Timestamp errati:** Verifica che l'ID `TimeZone` corrisponda alla tua regione target.  
- **Immagini mancanti:** Assicurati di aver usato `HtmlViewOptions.forEmbeddedResources()`; altrimenti, le risorse esterne potrebbero non essere incluse.  

## Applicazioni pratiche
1. **Archiviazione email:** Conserva snapshot HTML ricercabili delle email per la conformità.  
2. **Portali di supporto clienti:** Mostra i ticket in arrivo con orari locali accurati.  
3. **Documentazione legale:** Produci registrazioni email pronte per il tribunale con timestamp standardizzati.  

## Considerazioni sulle prestazioni
- Distribuisci su un server dedicato per conversioni di massa.  
- Monitora l'utilizzo dell'heap Java; aumenta `-Xmx` se incontri `OutOfMemoryError`.  
- Cache l'HTML renderizzato quando la stessa email viene richiesta più volte.  

## Conclusione
Ora disponi di un metodo completo, pronto per la produzione, per **convertire EML in HTML** con un formato datetime personalizzato e un offset del fuso orario usando GroupDocs.Viewer per Java. Questo migliora la leggibilità, garantisce l'accuratezza dei timestamp e si integra perfettamente nei flussi di lavoro di archiviazione o supporto.

**Passi successivi:** Esplora ulteriori opzioni di Viewer come lo styling CSS, la paginazione o la conversione PDF per personalizzare ulteriormente l'output secondo le tue esigenze.

## Domande frequenti

**Q: Come gestisco i file EML con allegati?**  
A: Gli allegati sono incorporati automaticamente quando usi `HtmlViewOptions.forEmbeddedResources()`. Puoi anche estrarli tramite l'API Viewer se necessario.

**Q: Posso modificare il modello HTML o aggiungere CSS personalizzato?**  
A: Sì, dopo il rendering puoi modificare il file HTML generato o iniettare CSS programmaticamente prima del salvataggio.

**Q: È possibile renderizzare più file EML in batch?**  
A: Avvolgi la logica di rendering in un ciclo e riutilizza la stessa istanza `HtmlViewOptions` per ogni file.

**Q: Cosa succede se devo supportare altri formati email come MSG?**  
A: GroupDocs.Viewer supporta anche MSG, PST e altri contenitori email — basta cambiare l'estensione del file nel costruttore `Viewer`.

**Q: È necessaria una licenza separata per ogni server?**  
A: La licenza è per distribuzione; consulta la guida di licenza di GroupDocs per scenari multi‑server.

## Risorse

- [Documentazione](https://docs.groupdocs.com/viewer/java/)
- [Riferimento API](https://reference.groupdocs.com/viewer/java/)
- [Download](https://releases.groupdocs.com/viewer/java/)
- [Acquista](https://purchase.groupdocs.com/buy)
- [Prova gratuita](https://releases.groupdocs.com/viewer/java/)
- [Licenza temporanea](https://purchase.groupdocs.com/temporary-license/)
- [Forum di supporto](https://forum.groupdocs.com/c/viewer/9)

---

**Ultimo aggiornamento:** 2026-03-24  
**Testato con:** GroupDocs.Viewer 25.2 (Java)  
**Autore:** GroupDocs  

---