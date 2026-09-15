---
date: '2026-09-15'
description: Scopri come convertire le email in HTML e rinominare i campi delle email
  usando GroupDocs Viewer per Java. Questa guida mostra come visualizzare le email
  in HTML con intestazioni personalizzate.
keywords:
- convert email to html
- rename email fields java
- render emails html groupdocs viewer
- customize email headers
- customize email metadata
lastmod: '2026-09-15'
og_description: Converti email in HTML e rinomina i campi delle email in Java con
  GroupDocs Viewer. Scopri la configurazione passo‑passo, la mappatura dei campi e
  le migliori pratiche per un output HTML pulito.
og_image_alt: Guide showing how to convert email to HTML and rename fields using GroupDocs
  Viewer for Java
og_title: Converti email in HTML con intestazioni personalizzate usando GroupDocs
  Viewer per Java
schemas:
- author: GroupDocs
  dateModified: '2026-09-15'
  description: Learn how to convert email to HTML and rename email fields using GroupDocs
    Viewer for Java. This guide shows rendering email as HTML with custom headers.
  headline: Convert Email to HTML & Rename Fields – GroupDocs Viewer Java
  type: TechArticle
- description: Learn how to convert email to HTML and rename email fields using GroupDocs
    Viewer for Java. This guide shows rendering email as HTML with custom headers.
  name: Convert Email to HTML & Rename Fields – GroupDocs Viewer Java
  steps:
  - name: '**Custom email reports:** Align email headers with corporate terminology
      for clearer reports.'
    text: '**Custom email reports:** Align email headers with corporate terminology
      for clearer reports.'
  - name: '**Email archiving systems:** Improve searchability by using standardized
      header names.'
    text: '**Email archiving systems:** Improve searchability by using standardized
      header names.'
  - name: '**Customer support platforms:** Present tickets with personalized header
      labels for better agent experience.'
    text: '**Customer support platforms:** Present tickets with personalized header
      labels for better agent experience.'
  type: HowTo
- questions:
  - answer: Yes, GroupDocs.Viewer supports both MSG and EML files; the same field‑mapping
      logic applies.
    question: Does this approach work with other email formats like EML?
  - answer: You can use `HtmlViewOptions.forExternalResources(...)` if you prefer
      separate CSS/JS files.
    question: Can I output the HTML without embedded resources?
  - answer: The code was tested with GroupDocs.Viewer **25.2**.
    question: What version of GroupDocs.Viewer was tested?
  - answer: Styling can be applied via CSS after rendering, or you can inject custom
      CSS using `HtmlViewOptions.getResourcesPath()`.
    question: Is it possible to change the font or style of the custom headers?
  - answer: The file path follows the pattern defined in `pageFilePathFormat`; you
      can construct it using `String.format` with the page number.
    question: How do I programmatically retrieve the generated HTML file path?
  type: FAQPage
tags:
- convert email to html
- groupdocs viewer java
- email rendering
- html conversion
- java email processing
title: Converti Email in HTML e Rinomina i Campi – GroupDocs Viewer Java
type: docs
url: /it/java/advanced-rendering/rename-email-fields-html-groupdocs-viewer-java/
weight: 1
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Convertire email in HTML e rinominare i campi – GroupDocs Viewer Java

Se hai bisogno di **convertire email in HTML** aggiungendo alle intestazioni email un aspetto personalizzato, sei nel posto giusto. In questo tutorial illustreremo i passaggi esatti per rinominare i campi email, **convertire email in HTML**, e personalizzare le intestazioni email usando GroupDocs.Viewer per Java. Alla fine avrai una rappresentazione HTML pulita con i nomi delle intestazioni che preferisci, rendendo l'output più facile da leggere e integrare nelle tue applicazioni.

![Rinominare i campi email durante la conversione delle email in HTML con GroupDocs.Viewer per Java](/viewer/advanced-rendering/rename-email-fields-when-converting-emails-to-html-java.png)

### Cosa imparerai
- Come utilizzare GroupDocs.Viewer per Java per **convertire email in HTML**.  
- Tecniche per **rinominare i campi email** come “From”, “To”, “Sent” e “Subject”.  
- Best practice per configurare Maven e la licenza.  
- Scenari reali in cui **personalizzare le intestazioni email** aggiunge valore.

## Risposte rapide
- **Cosa significa “convertire email in HTML”?** Significa renderizzare un file email (MSG/EML) come documento HTML pronto per il web.  
- **Quale libreria gestisce la conversione?** GroupDocs.Viewer per Java (v25.2+).  
- **Ho bisogno di una licenza?** Una versione di prova funziona per la valutazione; è necessaria una licenza completa per la produzione.  
- **Posso cambiare il nome di un'intestazione?** Sì, qualsiasi intestazione email standard può essere rimappata tramite `fieldTextMap`.  
- **L'output è HTML o risorse incorporate?** Puoi scegliere risorse incorporate per un unico file autonomo.

## Cos'è “convertire email in HTML” nel contesto di GroupDocs.Viewer?
**Convertire email in HTML** è il processo di prendere un file email grezzo (MSG o EML) e produrre una pagina HTML che visualizza il corpo del messaggio insieme ai suoi metadati. Quando si **rinominano i campi email**, le etichette predefinite (ad es., “From”) vengono sostituite con testo personalizzato (ad es., “Sender”), il che aiuta a corrispondere alla terminologia aziendale o a migliorare la coerenza dell'interfaccia utente.

## Perché convertire email in HTML e rinominare i campi email?
Convertire email in HTML e rinominare i suoi campi ti dà il pieno controllo su come il messaggio viene presentato agli utenti finali. Le intestazioni personalizzate allineano l'output alla terminologia aziendale, migliorano l'indicizzazione nella ricerca e consentono un'integrazione fluida in portali web o dashboard di supporto, mentre il formato HTML garantisce ampia compatibilità su browser e dispositivi.

- **Branding coerente:** Allinea l'output alla lingua della tua organizzazione.  
- **Migliore indicizzabilità:** Le intestazioni personalizzate possono essere indicizzate più efficacemente nei sistemi di archiviazione.  
- **Integrazione UI migliorata:** Adatta lo snippet HTML per inserirlo perfettamente in portali web o dashboard di supporto.  
- **Vantaggio di prestazioni:** GroupDocs.Viewer elabora email fino a 500 pagine in meno di 2 secondi su un server standard, e supporta **oltre 50** formati di input e output, inclusi MSG, EML, PDF e HTML.

## Prerequisiti
- **GroupDocs.Viewer for Java** – versione 25.2 o successiva.  
- **Java Development Kit (JDK)** – versione 8+.  
- **Maven** per la gestione delle dipendenze.  
- Un IDE come IntelliJ IDEA, Eclipse o VS Code.  
- Familiarità di base con Java e Maven accelererà la configurazione.

## Configurazione di GroupDocs.Viewer per Java

### Configurazione Maven
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
- **Prova gratuita:** Scarica una prova gratuita da [GroupDocs Releases](https://releases.groupdocs.com/viewer/java/).  
- **Licenza temporanea:** Ottieni una licenza temporanea per esplorare tutte le funzionalità senza limitazioni su [GroupDocs Temporary License](https://purchase.groupdocs.com/temporary-license/).  
- **Acquisto:** Per un uso continuato, considera l'acquisto di una licenza tramite [GroupDocs Purchase](https://purchase.groupdocs.com/buy).

### Inizializzazione e configurazione di base
La classe `Viewer` è il punto di ingresso per tutte le operazioni di rendering in GroupDocs.Viewer per Java. Gestisce automaticamente il caricamento dei file, il rilevamento del formato e la pulizia delle risorse.  
```java
import com.groupdocs.viewer.Viewer;

public class ViewerSetup {
    public static void main(String[] args) {
        try (Viewer viewer = new Viewer("path/to/your/document.msg")) {
            // Perform operations here
        }
    }
}
```
Modifica il percorso del file per puntare al tuo file `.msg`.

## Come convertire email in HTML e rinominare i campi – passo‑per‑passo

Carica la tua email, definisci un dizionario di mappatura dei campi, configura le opzioni di visualizzazione HTML e invoca la chiamata di rendering. L'intero flusso di lavoro può essere espresso in sei passaggi concisi.

### 1. Configura il percorso della directory di output
```java
import java.nio.file.Path;

Path outputDirectory = Utils.getOutputDirectoryPath("YOUR_OUTPUT_DIRECTORY");
```
*Sostituisci `"YOUR_OUTPUT_DIRECTORY"` con la cartella in cui desideri salvare i file HTML.*

### 2. Definisci il formato del percorso del file di pagina
```java
Path pageFilePathFormat = outputDirectory.resolve("page_{0}.html");
```
*`{0}` verrà sostituito dal numero di pagina durante il rendering.*

### 3. Crea una mappatura dei campi email a nuovi nomi
```java
import com.groupdocs.viewer.options.Field;
import java.util.HashMap;
import java.util.Map;

Map<Field, String> fieldTextMap = new HashMap<>();
fieldTextMap.put(Field.FROM, "Sender");
fieldTextMap.put(Field.TO, "Receiver");
fieldTextMap.put(Field.SENT, "Date");
fieldTextMap.put(Field.SUBJECT, "Topic");
```
*Qui cambiamo le etichette predefinite con quelle personalizzate.*

### 4. Configura le opzioni di visualizzazione HTML
La classe `HtmlViewOptions` controlla come viene generato l'HTML finale. Impostare `forEmbeddedResources` incorpora CSS/JS all'interno dell'HTML, mentre `setFieldTextMap` applica i nomi delle intestazioni personalizzate definiti.  
```java
import com.groupdocs.viewer.options.HtmlViewOptions;

HtmlViewOptions viewOptions = HtmlViewOptions.forEmbeddedResources(pageFilePathFormat);
viewOptions.getEmailOptions().setFieldTextMap(fieldTextMap);
```

### 5. Renderizza l'email in HTML
```java
try (Viewer viewer = new Viewer("YOUR_DOCUMENT_DIRECTORY/SAMPLE_MSG")) {
    viewer.view(viewOptions);
}
```
*Sostituisci `"YOUR_DOCUMENT_DIRECTORY/SAMPLE_MSG"` con il percorso reale del tuo file MSG.*

#### Suggerimenti per la risoluzione dei problemi
- Verifica che la directory di output sia scrivibile.  
- Assicurati che il file MSG di input esista e che il percorso sia corretto.  
- Usa la stessa versione di GroupDocs.Viewer (25.2) dichiarata in Maven.

## Applicazioni pratiche
1. **Report email personalizzati:** Allinea le intestazioni email alla terminologia aziendale per report più chiari.  
2. **Sistemi di archiviazione email:** Migliora l'indicizzabilità usando nomi di intestazione standardizzati.  
3. **Piattaforme di supporto clienti:** Presenta i ticket con etichette di intestazione personalizzate per una migliore esperienza degli operatori.

## Considerazioni sulle prestazioni
- Dispone degli oggetti `Viewer` con try‑with‑resources per liberare rapidamente la memoria.  
- Profilare batch di grandi dimensioni e considerare l'elaborazione delle email in stream paralleli se necessario.  
- GroupDocs.Viewer può renderizzare email fino a **200 MB** senza caricare l'intero documento in memoria, grazie alla sua architettura di streaming.

## Conclusione
Ora sai **come convertire email in HTML** mentre **rinomini i campi email** e **personalizzi le intestazioni email** con GroupDocs.Viewer per Java. Questa tecnica ti offre il pieno controllo sulla presentazione dei metadati email negli output HTML.

### Prossimi passi
- Sperimenta con mappature aggiuntive dei campi (ad es., CC, BCC).  
- Esplora altri formati di rendering come PDF o PNG.  
- Visita [GroupDocs Documentation](https://docs.groupdocs.com/viewer/java/) per approfondire le API.

## Domande frequenti

**D: Questo approccio funziona con altri formati email come EML?**  
R: Sì, GroupDocs.Viewer supporta sia file MSG che EML; la stessa logica di mappatura dei campi si applica.

**D: Posso generare l'HTML senza risorse incorporate?**  
R: Puoi usare `HtmlViewOptions.forExternalResources(...)` se preferisci file CSS/JS separati.

**D: Quale versione di GroupDocs.Viewer è stata testata?**  
R: Il codice è stato testato con GroupDocs.Viewer **25.2**.

**D: È possibile modificare il font o lo stile delle intestazioni personalizzate?**  
R: Lo stile può essere applicato tramite CSS dopo il rendering, oppure puoi iniettare CSS personalizzato usando `HtmlViewOptions.getResourcesPath()`.

**D: Come recupero programmaticamente il percorso del file HTML generato?**  
R: Il percorso del file segue il modello definito in `pageFilePathFormat`; puoi costruirlo usando `String.format` con il numero di pagina.

## Risorse
- **Documentazione:** Guide complete sono disponibili su [GroupDocs Documentation](https://docs.groupdocs.com/viewer/java/).  
- **Riferimento API:** Informazioni dettagliate sull'API si trovano su [GroupDocs API Reference](https://reference.groupdocs.com/viewer/java/).  
- **Download GroupDocs.Viewer:** Accedi all'ultima versione tramite la [Downloads Page](https://releases.groupdocs.com/viewer/java/).

---

**Ultimo aggiornamento:** 2026-09-15  
**Testato con:** GroupDocs.Viewer 25.2  
**Autore:** GroupDocs

## Tutorial correlati

- [Convert EML to HTML with Custom DateTime in Java Using GroupDocs.Viewer](/viewer/java/advanced-rendering/render-emails-custom-datetime-groupdocs-viewer-java/)
- [java convert msg to pdf – Optimize Email-to-PDF Rendering with GroupDocs.Viewer](/viewer/java/performance-optimization/optimize-email-pdf-rendering-java-groupdocs-viewer-api/)
- [Render Document Attachments HTML with GroupDocs.Viewer Java – A Step‑By‑Step Guide](/viewer/java/rendering-basics/render-document-attachments-html-groupdocs-viewer-java/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}