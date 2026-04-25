---
date: '2026-02-05'
description: Scopri come ottenere viewinfo e recuperare le strutture dei file di tipo
  Java archive utilizzando GroupDocs.Viewer. Questa guida copre la configurazione,
  esempi di codice e casi d'uso reali.
keywords:
- GroupDocs.Viewer for Java
- retrieve archive structures
- Java document viewer
title: Come ottenere ViewInfo e recuperare le strutture di archivio in Java
type: docs
url: /it/java/document-loading/groupdocs-viewer-java-retrieve-archive-structures/
weight: 1
---

# Come Ottenere ViewInfo e Recuperare le Strutture di Archivi in Java

Gestire i file di archivio in modo efficace richiede una chiara comprensione della loro struttura. In questo tutorial imparerai **come ottenere viewinfo** per qualsiasi archivio e vedrai come ti aiuta a lavorare con il **tipo di file di archivio java**. Ti guideremo nella configurazione di GroupDocs.Viewer, nell'estrazione delle informazioni di visualizzazione e nella lettura ricorsiva delle gerarchie di cartelle così potrai integrare la soluzione in progetti reali.

![Strutture di archivio con GroupDocs.Viewer per Java](/viewer/document-loading/archive-structures-java.png)

**Cosa Imparerai**
- Configurare e impostare GroupDocs.Viewer per Java.  
- Metodi per **ottenere viewinfo** dagli archivi.  
- Tecniche per leggere e visualizzare la struttura delle cartelle di un file di archivio.  
- Applicazioni pratiche e considerazioni sulle prestazioni quando si utilizza GroupDocs.Viewer in progetti Java.

## Risposte Rapide
- **Cosa fornisce “viewinfo”?** Restituisce il tipo di file, il conteggio delle pagine e l'elenco delle cartelle dell'archivio.  
- **Quali archivi sono supportati?** ZIP, RAR, TAR e altri formati comuni.  
- **È necessaria una licenza?** Una versione di prova gratuita è sufficiente per la valutazione; è necessaria una licenza commerciale per la produzione.  
- **Posso elaborare archivi di grandi dimensioni?** Sì – utilizza lo streaming e una corretta gestione della memoria come mostrato più avanti.  
- **Maven è obbligatorio?** Maven è il metodo consigliato per gestire la dipendenza di GroupDocs.Viewer.

## Cos'è “come ottenere viewinfo”?
`getViewInfo` è un metodo nell'API GroupDocs.Viewer che estrae i metadati di un documento o archivio senza renderizzare l'intero contenuto. Per gli archivi, rivela l'albero interno delle cartelle, consentendoti di decidere quali parti renderizzare o elaborare ulteriormente.

## Perché Recuperare le Strutture dei File di Archivio Java?
Comprendere la disposizione interna di un **tipo di file di archivio java** (ad es., ZIP, RAR) ti permette di:
- Individuare rapidamente i file necessari senza estrarre tutto.  
- Costruire pipeline automatizzate che elaborano solo le sotto‑cartelle rilevanti.  
- Integrare la navigazione degli archivi nei sistemi di gestione dei contenuti o di ingestione dati.

## Prerequisiti

- **Java Development Kit (JDK):** Versione 8 o più recente.  
- **Maven:** Per la gestione delle dipendenze e le build.  
- **Basic Java knowledge:** La familiarità con i concetti OOP è utile ma non obbligatoria.

Hai inoltre bisogno di accedere alla libreria GroupDocs.Viewer, che puoi aggiungere al tuo progetto Maven come mostrato di seguito.

## Configurare GroupDocs.Viewer per Java

### Configurazione Maven

Aggiungi il repository e la dipendenza al tuo `pom.xml`.

**Repository:**  
```xml
<repositories>
   <repository>
      <id>repository.groupdocs.com</id>
      <name>GroupDocs Repository</name>
      <url>https://releases.groupdocs.com/viewer/java/</url>
   </repository>
</repositories>
```

**Dipendenze:**  
```xml
<dependencies>
   <dependency>
      <groupId>com.groupdocs</groupId>
      <artifactId>groupdocs-viewer</artifactId>
      <version>25.2</version>
   </dependency>
</dependencies>
```

### Acquisizione Licenza

- **Free Trial:** Scarica una versione di prova dal sito GroupDocs.  
- **Temporary License:** Richiedi una chiave temporanea per una valutazione a breve termine.  
- **Full License:** Acquista una licenza commerciale per uso illimitato in produzione.

Una volta che la libreria è nel tuo classpath, puoi iniziare a scrivere codice.

## Guida all'Implementazione

### Come Ottenere ViewInfo per i File di Archivio

Questa sezione mostra i passaggi esatti per chiamare `getViewInfo` e leggere la gerarchia delle cartelle.

#### Inizializzare il Viewer

```java
try (Viewer viewer = new Viewer("YOUR_DOCUMENT_DIRECTORY/SAMPLE_ZIP_WITH_FOLDERS")) {
    // Additional steps will follow here.
}
```

#### Recuperare le Informazioni di Visualizzazione

```java
ViewInfo viewInfo = viewer.getViewInfo(ViewInfoOptions.forHtmlView());
System.out.println("File type: " + viewInfo.getFileType());
System.out.println("Pages count: " + viewInfo.getPages().size());
```

#### Visualizzare la Struttura delle Cartelle

```java
String rootFolder = "";
readFolders(viewer, rootFolder);
```

##### Lettura Ricorsiva delle Cartelle

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

### Funzione 2: Recuperare la Struttura delle Cartelle dell'Archivio

Questa funzionalità si concentra sulla stampa della struttura delle cartelle di un file di archivio. È simile alla prima funzionalità ma enfatizza l'esplorazione ricorsiva.

#### Configurare le Opzioni di ViewInfo

```java
ViewInfoOptions viewInfoOptions = ViewInfoOptions.forHtmlView();
viewInfoOptions.getArchiveOptions().setFolder(folder);
```

#### Esplorazione Ricorsiva

```java
for (String subFolder : viewInfo.getFolders()) {
    System.out.println(" - " + subFolder);
    readFolders(viewer, subFolder);
}
```

## Applicazioni Pratiche

1. **Data Management:** Organizza rapidamente grandi set di dati comprendendo le strutture degli archivi.  
2. **Automated File Processing:** Elabora in batch i file archiviati senza estrarli completamente.  
3. **CMS Integration:** Migliora i sistemi di gestione dei contenuti con navigazione degli archivi in tempo reale.

## Considerazioni sulle Prestazioni

- **Optimize Memory Usage:** Elabora le cartelle un livello alla volta e chiudi l'istanza `Viewer` prontamente.  
- **Stay Updated:** Usa l'ultima versione di GroupDocs.Viewer e le release JDK per miglioramenti di prestazioni.

## Problemi Comuni e Soluzioni

| Problema | Perché Accade | Soluzione |
|----------|----------------|-----------|
| `NullPointerException` when reading folders | `viewInfo.getFolders()` returns null for empty directories | Check for null or empty list before iterating. |
| Slow processing of huge ZIP files | Entire archive is loaded into memory | Use streaming options available in newer GroupDocs versions. |
| License not found | License file path is incorrect | Place the license file in the application root or set `License.setLicense("path/to/license.json")`. |

## Domande Frequenti

**Q: Cos'è GroupDocs.Viewer?**  
A: È una potente libreria Java per il rendering di documenti, inclusi gli archivi, in formati come HTML, immagine e PDF.

**Q: Posso usare GroupDocs.Viewer con altri linguaggi di programmazione?**  
A: Sì, GroupDocs offre SDK per più piattaforme, ma questo tutorial si concentra sull'implementazione Java.

**Q: Come gestisco file di archivio di grandi dimensioni?**  
A: Usa pratiche di gestione della memoria efficienti e considera di suddividere gli archivi se necessario.

**Q: Quali tipi di archivi supporta GroupDocs.Viewer?**  
A: Supporta una varietà di formati tra cui ZIP, RAR, TAR e altri.

**Q: Esiste un limite alla dimensione degli archivi che posso elaborare?**  
A: I limiti dipendono dalle risorse del tuo sistema. Testa nell'ambiente di destinazione per determinare i limiti pratici.

**Q: “come ottenere viewinfo” funziona con archivi protetti da password?**  
A: Sì, puoi fornire la password tramite `ArchiveOptions.setPassword("yourPassword")` prima di chiamare `getViewInfo`.

## Conclusione

Seguendo questa guida ora sai **come ottenere viewinfo** per qualsiasi archivio supportato e come attraversare la sua gerarchia di cartelle usando GroupDocs.Viewer per Java. Queste tecniche ti consentono di costruire pipeline di elaborazione dati più intelligenti, migliorare le integrazioni CMS e gestire grandi collezioni di file archiviati con fiducia. Successivamente, esplora il rendering di file individuali dall'archivio o la loro conversione in PDF/HTML usando altre funzionalità di Viewer.

---

**Ultimo Aggiornamento:** 2026-02-05  
**Testato Con:** GroupDocs.Viewer 25.2 for Java  
**Autore:** GroupDocs  

**Risorse**
- **Documentazione:** [GroupDocs Viewer Java Documentation](https://docs.groupdocs.com/viewer/java/)
- **Riferimento API:** [GroupDocs API Reference for Java](https://reference.groupdocs.com/viewer/java/)
- **Scarica GroupDocs.Viewer:** [GroupDocs Download Page](https://releases.groupdocs.com/viewer/java/)
- **Acquista Licenza:** [Buy GroupDocs](https://purchase.groupdocs.com/buy)
- **Versione di Prova Gratuita e Licenza Temporanea:** [GroupDocs Free Trial](https://releases.groupdocs.com/viewer/java/) | [Temporary License](https://purchase.groupdocs.com/temporary-license/)