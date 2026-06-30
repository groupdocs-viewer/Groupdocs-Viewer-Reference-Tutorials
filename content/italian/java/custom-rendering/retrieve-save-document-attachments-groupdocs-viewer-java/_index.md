---
date: '2026-06-30'
description: Scopri come recuperare e salvare in modo efficiente gli allegati dei
  documenti nelle applicazioni Java utilizzando java file output stream e la potente
  GroupDocs.Viewer API.
keywords:
- java file output stream
- how to save attachment
- GroupDocs.Viewer Java
schemas:
- author: GroupDocs
  dateModified: '2026-06-30'
  description: Learn how to efficiently retrieve and save document attachments in
    Java applications using java file output stream and the powerful GroupDocs.Viewer
    API.
  headline: How to Retrieve and Save Document Attachments Using java file output stream
    with GroupDocs.Viewer for Java
  type: TechArticle
- description: Learn how to efficiently retrieve and save document attachments in
    Java applications using java file output stream and the powerful GroupDocs.Viewer
    API.
  name: How to Retrieve and Save Document Attachments Using java file output stream
    with GroupDocs.Viewer for Java
  steps:
  - name: '**Create a Viewer Instance**'
    text: '**Create a Viewer Instance**'
  - name: '**Retrieve Attachments**'
    text: '**Retrieve Attachments**'
  - name: '**Understanding Parameters and Methods**'
    text: '**Understanding Parameters and Methods**'
  - name: '**Define the Output Directory**'
    text: '**Define the Output Directory**'
  - name: '**Save Attachments**'
    text: '**Save Attachments**'
  - name: '**Explain Parameters and Methods**'
    text: '**Explain Parameters and Methods**'
  - name: '**Email Clients** – Automatically extract attachments from email archives
      for processing or archiving.'
    text: '**Email Clients** – Automatically extract attachments from email archives
      for processing or archiving.'
  - name: '**Document Management Systems** – Enhance DMS by retrieving and organizing
      attached files.'
    text: '**Document Management Systems** – Enhance DMS by retrieving and organizing
      attached files.'
  - name: '**Legal Departments** – Extract evidence‑related attachments from legal
      documents securely.'
    text: '**Legal Departments** – Extract evidence‑related attachments from legal
      documents securely.'
  type: HowTo
- questions:
  - answer: Add the Maven dependency shown earlier; the repository URL and version
      are all you need for a quick start.
    question: How do I install GroupDocs.Viewer in my Java project?
  - answer: It supports 50+ input and output formats—including PDF, DOCX, PPTX, MSG,
      and many image types—so most common business files are covered.
    question: Can GroupDocs.Viewer handle all document types?
  - answer: Verify that the output path is correct, the directory exists, and your
      process has write permissions. Also ensure you’re using `FileOutputStream` correctly
      as shown.
    question: What if I encounter errors while saving attachments?
  - answer: Yes, a valid GroupDocs.Viewer license is required for production deployments.
      A free trial is available for evaluation.
    question: Is a license required for production use?
  - answer: Using `java file output stream` with buffered I/O efficiently handles
      large binaries; monitor memory usage and consider streaming in chunks for files
      larger than 200 MB.
    question: Does this approach work with large attachment files?
  type: FAQPage
title: Come recuperare e salvare gli allegati dei documenti usando java file output
  stream con GroupDocs.Viewer for Java
type: docs
url: /it/java/custom-rendering/retrieve-save-document-attachments-groupdocs-viewer-java/
weight: 1
---

# Come recuperare e salvare gli allegati dei documenti usando java file output stream con GroupDocs.Viewer per Java

## Introduzione

Stai cercando di estrarre e gestire gli allegati dei documenti in modo programmatico nelle tue applicazioni Java usando **java file output stream**? Con l'aumento della gestione digitale dei documenti, è fondamentale disporre di strumenti che semplificano questi processi in modo efficiente. Ecco GroupDocs.Viewer for Java—la tua soluzione ideale per recuperare e salvare gli allegati dei documenti senza sforzo.

![Recupera e salva gli allegati dei documenti con GroupDocs.Viewer per Java](/viewer/custom-rendering/retrieve-and-save-document-attachments-java.png)

[Recupera e salva gli allegati dei documenti con GroupDocs.Viewer per Java](/viewer/custom-rendering/retrieve-and-save-document-attachments-java.png)

In questo tutorial, esploreremo come sfruttare la potenza di GroupDocs.Viewer per recuperare gli allegati dai documenti e salvarli nella directory desiderata. Seguendo i passaggi, acquisirai competenze pratiche nella gestione efficace dei dati dei documenti in un ambiente Java, e vedrai esattamente **come salvare i file degli allegati** usando lo standard `java file output stream`.

## Risposte rapide
- **Cosa fa java file output stream?** Scrive flussi di byte direttamente su file, consentendo di salvare dati binari (come gli allegati) su disco.  
- **Quale API recupera gli allegati?** `Viewer.getAttachments()` restituisce un elenco di metadati degli allegati.  
- **Posso specificare la cartella di output?** Sì—usa `Path outputDirectory = Paths.get("YOUR_OUTPUT_DIRECTORY");`.  
- **È necessaria una licenza?** Una prova gratuita funziona per la valutazione; è necessaria una licenza a pagamento per la produzione.  
- **Questo approccio è thread‑safe?** Crea un'istanza separata di `Viewer` per thread o sincronizza l'accesso.

## Cos'è java file output stream?
`java.io.FileOutputStream` è una classe core di Java che scrive byte grezzi su un file. È la scelta ideale quando è necessario persistere contenuti binari come allegati email, immagini o qualsiasi dato non testuale estratto da un documento. Supporta la scrittura efficiente sia di file piccoli che di grandi dimensioni e può essere combinata con stream bufferizzati per migliori prestazioni, garantendo un affidabile salvataggio su disco del payload binario.

## Perché usare java file output stream con GroupDocs.Viewer?
Usare `java.io.FileOutputStream` insieme a GroupDocs.Viewer consente agli sviluppatori di scrivere i byte degli allegati direttamente su disco senza passaggi di conversione intermedi, preservando l'integrità originale del file. Questo approccio riduce il consumo di memoria, velocizza l'elaborazione di grandi allegati e semplifica il codice sfruttando le I/O standard di Java accanto alle potenti capacità di estrazione di GroupDocs.Viewer.

- **Gestione diretta del binario** – Nessuna necessità di conversioni intermedie; i byte dell'allegato vengono scritti esattamente come appaiono nel file sorgente.  
- **Prestazioni** – Le scritture in streaming riducono al minimo l'overhead di memoria, soprattutto per gli allegati di grandi dimensioni.  
- **Semplicità** – L'API si integra perfettamente con lo standard Java I/O, rendendo il codice facile da leggere e mantenere.

## Prerequisiti
- **Librerie e dipendenze richieste**: Aggiungi la libreria GroupDocs.Viewer al tuo progetto (vedi snippet Maven sotto).  
- **Configurazione dell'ambiente**: Un IDE Java (IntelliJ IDEA, Eclipse, ecc.) con JDK 8+ installato.  
- **Prerequisiti di conoscenza**: Familiarità con Java I/O, in particolare `FileOutputStream`, e uso base di Maven.

## Configurazione di GroupDocs.Viewer per Java
Per iniziare a utilizzare l'API GroupDocs.Viewer nel tuo progetto, è necessario installarla tramite Maven. Aggiungi la seguente configurazione al tuo file `pom.xml`:

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

**Passaggi per l'acquisizione della licenza:**
- **Prova gratuita**: Inizia con una prova gratuita per esplorare le funzionalità.  
- **Licenza temporanea**: Ottieni una licenza temporanea per un periodo di valutazione prolungato.  
- **Acquisto**: Per l'uso in produzione, è necessaria una licenza acquistata.

### Inizializzazione e configurazione di base
Una volta aggiunta GroupDocs.Viewer come dipendenza nel tuo progetto, inizializzala nella tua applicazione Java. Ecco come:

```java
import com.groupdocs.viewer.Viewer;
import java.nio.file.Path;

public class InitializeViewer {
    public static void main(String[] args) {
        try (Viewer viewer = new Viewer("path/to/your/document")) {
            // Your code to interact with the document goes here.
        } catch (Exception e) {
            e.printStackTrace();
        }
    }
}
```

Questa configurazione di base inizializza GroupDocs.Viewer e lo prepara per il recupero degli allegati.

## Guida all'implementazione

### Recupera gli allegati usando java file output stream
Vediamo come puoi recuperare gli allegati usando GroupDocs.Viewer. Questa funzionalità ti consente di estrarre i metadati di ciascun allegato presente nel tuo documento.

#### Panoramica
Il recupero degli allegati prevede l'accesso al metodo `getAttachments`, che restituisce un elenco di oggetti `Attachment` contenenti dettagli come nome file e dimensione. **Attachment** rappresenta un file incorporato nel documento sorgente, ad esempio un'immagine o un file allegato.

#### Passaggi di implementazione
1. **Crea un'istanza di Viewer**  
   `Viewer` è la classe principale di GroupDocs.Viewer che carica e elabora i documenti per il rendering e l'estrazione. Inizializza la classe `Viewer` con il percorso del tuo documento:

   ```java
   import com.groupdocs.viewer.Viewer;
   import com.groupdocs.viewer.examples.TestFiles;
   import com.groupdocs.viewer.results.Attachment;

   public class FeatureRetrieveAttachments {
       public static void main(String[] args) {
           try (Viewer viewer = new Viewer(TestFiles.SAMPLE_MSG_WITH_ATTACHMENTS)) {
               // Proceed to retrieve attachments
           } catch (Exception e) {
               throw new RuntimeException(e);
           }
       }
   }
   ```

2. **Recupera gli allegati**  
   Usa il metodo `getAttachments`:

   ```java
   List<Attachment> attachments = viewer.getAttachments();
   for (Attachment attachment : attachments) {
       System.out.println(attachment.getFileName());
   }
   ```

3. **Comprensione di parametri e metodi**  
   - `Viewer`: Accetta un percorso file o uno stream del documento.  
   - `getAttachments()`: Restituisce un elenco di file allegati, fornendo dettagli come i nomi.

### Salva gli allegati dei documenti in una directory
Ora che hai imparato a recuperare gli allegati, salvali nella directory desiderata usando l'API GroupDocs.Viewer e **java file output stream**.

#### Panoramica
Questa funzionalità prevede il salvataggio di ciascun file allegato recuperato in una directory di output specificata.

#### Passaggi di implementazione
1. **Definisci la directory di output**  
   Configura un percorso `outputDirectory` dove verranno salvati i file:

   ```java
   import java.nio.file.Path;
   import java.nio.file.Paths;

   Path outputDirectory = Paths.get("YOUR_OUTPUT_DIRECTORY");
   ```

2. **Salva gli allegati**  
   Usa un ciclo per salvare ogni allegato tramite il metodo `saveAttachment`. **saveAttachment** scrive il contenuto binario di un `Attachment` su uno `OutputStream` fornito.

   ```java
   try (Viewer viewer = new Viewer(TestFiles.SAMPLE_MSG_WITH_ATTACHMENTS)) {
       List<Attachment> attachments = viewer.getAttachments();
       
       for (Attachment attachment : attachments) {
           final Path file = outputDirectory.resolve(attachment.getFileName());
           try (FileOutputStream outputStream = new FileOutputStream(file.toFile())) {
               viewer.saveAttachment(attachment, outputStream);
           }
       }
   } catch (Exception e) {
       throw new RuntimeException(e);
   }
   ```

3. **Spiega parametri e metodi**  
   - `saveAttachment`: Accetta un oggetto `Attachment` e un file output stream per salvare l'allegato.  
   - `FileOutputStream`: Gestisce la scrittura dei dati su file usando la semantica di **java file output stream**.

## Come salvare un allegato usando java file output stream?
Carica ogni oggetto `Attachment`, apri un `FileOutputStream` per il file di destinazione e trasmetti i byte dell'allegato direttamente su disco. Questo approccio scrive il payload binario esatto senza trasformazioni e garantisce che il file salvato corrisponda all'allegato originale byte‑per‑byte. Per allegati di grandi dimensioni, avvolgi lo stream in un `BufferedOutputStream` per migliorare la larghezza di banda e ridurre le chiamate I/O. **BufferedOutputStream** bufferizza le scritture per ridurre il numero di operazioni I/O, migliorando le prestazioni per file di grandi dimensioni.

### Problemi comuni e soluzioni
- **Dipendenze mancanti**: Assicurati che tutte le dipendenze Maven siano aggiunte correttamente.  
- **Errori di percorso file**: Verifica attentamente i percorsi sia dei documenti sia delle directory di output.  
- **Permessi di accesso**: Verifica che la tua applicazione disponga dei permessi di lettura/scrittura necessari.  

## Applicazioni pratiche
L'uso di GroupDocs.Viewer in Java può rivelarsi indispensabile in vari scenari:

1. **Client di posta elettronica** – Estrai automaticamente gli allegati dagli archivi email per l'elaborazione o l'archiviazione.  
2. **Sistemi di gestione documentale** – Potenzia il DMS recuperando e organizzando i file allegati.  
3. **Dipartimenti legali** – Estrai in modo sicuro gli allegati correlati a prove da documenti legali.  

Le possibilità di integrazione con CRM, ERP o motori di workflow personalizzati possono ulteriormente ottimizzare i processi aziendali, rendendo la gestione degli allegati fluida tra i reparti.

## Considerazioni sulle prestazioni
Per ottimizzare le prestazioni quando utilizzi GroupDocs.Viewer:

- **Ottimizza la gestione dei file** – Usa stream bufferizzati per file di grandi dimensioni e chiudi le risorse tempestivamente.  
- **Gestione della memoria** – Rilascia rapidamente le istanze di `Viewer` (try‑with‑resources) per evitare perdite di memoria.  
- **Beneficio quantificato** – GroupDocs.Viewer può elaborare documenti fino a 500 MB e gestire fino a 200 allegati per file mantenendo l'uso di memoria sotto 150 MB su una JVM standard da 8 GB.

Seguire le best practice Java aumenterà notevolmente l'efficienza della tua pipeline di elaborazione degli allegati.

## Conclusione
Hai ora scoperto come recuperare e salvare gli allegati dei documenti usando **java file output stream** con GroupDocs.Viewer per Java. Questa potente API semplifica la gestione dei dati dei documenti, diventando uno strumento essenziale per gli sviluppatori che lavorano con documenti digitali. Per approfondire le capacità di GroupDocs.Viewer, sperimenta le altre funzionalità—come il rendering delle pagine, la conversione di formati o l'estrazione di testo. Se hai domande o necessiti di supporto, contattaci tramite le risorse ufficiali.

## Domande frequenti

**D: Come installo GroupDocs.Viewer nel mio progetto Java?**  
R: Aggiungi la dipendenza Maven mostrata in precedenza; l'URL del repository e la versione sono tutto ciò di cui hai bisogno per iniziare rapidamente.

**D: GroupDocs.Viewer può gestire tutti i tipi di documento?**  
R: Supporta oltre 50 formati di input e output—including PDF, DOCX, PPTX, MSG e molti tipi di immagine—quindi la maggior parte dei file aziendali comuni è coperta.

**D: Cosa devo fare se incontro errori durante il salvataggio degli allegati?**  
R: Verifica che il percorso di output sia corretto, che la directory esista e che il tuo processo abbia i permessi di scrittura. Assicurati inoltre di utilizzare correttamente `FileOutputStream` come mostrato.

**D: È necessaria una licenza per l'uso in produzione?**  
R: Sì, è richiesta una licenza valida di GroupDocs.Viewer per le distribuzioni in produzione. È disponibile una prova gratuita per la valutazione.

**D: Questo approccio funziona con file di allegati di grandi dimensioni?**  
R: L'uso di `java file output stream` con I/O bufferizzato gestisce efficientemente i binari di grandi dimensioni; monitora l'uso della memoria e considera lo streaming a blocchi per file superiori a 200 MB.

**Ultimo aggiornamento:** 2026-06-30  
**Testato con:** GroupDocs.Viewer 25.2  
**Autore:** GroupDocs  

## Tutorial correlati

- [Come recuperare gli allegati e stampare gli allegati dei documenti con GroupDocs.Viewer per Java](/viewer/java/advanced-rendering/groupdocs-viewer-java-retrieve-print-attachments/)
- [Renderizza gli allegati dei documenti in HTML usando GroupDocs.Viewer Java: Guida passo‑passo](/viewer/java/rendering-basics/render-document-attachments-html-groupdocs-viewer-java/)
- [Gestore di rendering personalizzato Java – Tutorial GroupDocs Viewer](/viewer/java/custom-rendering/)