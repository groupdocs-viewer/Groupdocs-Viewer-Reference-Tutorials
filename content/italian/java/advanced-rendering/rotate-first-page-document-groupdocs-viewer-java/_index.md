---
date: '2026-01-18'
description: Scopri come ruotare una pagina di 90 gradi in Java con GroupDocs Viewer,
  includendo configurazione, codice e consigli sulle prestazioni.
keywords:
- rotate first page GroupDocs Viewer Java
- GroupDocs Viewer Java setup
- rotate pages in documents using Java
title: Ruota la pagina di 90 gradi con GroupDocs Viewer per Java
type: docs
url: /it/java/advanced-rendering/rotate-first-page-document-groupdocs-viewer-java/
weight: 1
---

# Ruota la pagina di 90 gradi con GroupDocs Viewer per Java

Quando è necessario **ruotare la pagina di 90 gradi** in un documento—che sia un PDF, un file Word o un foglio di calcolo—farlo programmaticamente fa risparmiare tempo ed elimina errori manuali. In questa guida avanzata percorreremo i passaggi esatti per ruotare la prima pagina di qualsiasi documento supportato usando **GroupDocs Viewer per Java**. Alla fine avrai uno snippet riutilizzabile da inserire nei tuoi progetti.

![Rotate the First Page of a Document with GroupDocs.Viewer for Java](/viewer/advanced-rendering/rotate-the-first-page-of-a-document-java.png)

## Risposte rapide
- **Cosa significa “ruotare la pagina di 90 gradi”?** Ruota la pagina selezionata in senso orario di un quarto di giro.  
- **Quale libreria gestisce la rotazione?** GroupDocs Viewer per Java fornisce il metodo `rotatePage`.  
- **Posso ruotare pagine PDF con Java?** Sì—usa la stessa chiamata `rotatePage`; funziona per PDF, DOCX, XLSX e altri.  
- **È necessaria una licenza?** Una prova gratuita è sufficiente per lo sviluppo; è richiesta una licenza a pagamento per la produzione.  
- **L'operazione è intensiva in termini di memoria?** No, se chiudi prontamente l'istanza `Viewer`; vedi i consigli sulle prestazioni qui sotto.

## Cos’è “ruotare la pagina di 90 gradi”?
Ruotare una pagina di 90 gradi reindirizza la pagina da verticale a orizzontale (o viceversa) senza modificare il contenuto sottostante. È particolarmente utile per presentazioni, stampa di grafica solo in orizzontale o per correggere documenti scansionati catturati di lato.

## Perché ruotare le pagine con GroupDocs Viewer per Java?
GroupDocs Viewer astrae le complessità della gestione di decine di formati di file. Consente di applicare trasformazioni a livello di pagina—come la rotazione—mantenendo intatto il file originale. L'API è fluida, thread‑safe e funziona su qualsiasi runtime Java 8+.

## Prerequisiti

- **GroupDocs.Viewer per Java** (ultima versione)
- **JDK 8** o superiore
- **Maven** (o Gradle) per la gestione delle dipendenze
- Un IDE come IntelliJ IDEA o Eclipse
- Familiarità di base con Java I/O

## Configurazione di GroupDocs.Viewer per Java

Aggiungi il repository GroupDocs e la dipendenza al tuo `pom.xml`. Questo snippet è invariato rispetto al tutorial originale:

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
- **Prova gratuita** – scarica dal sito GroupDocs.  
- **Licenza temporanea** – richiedi se ti serve un periodo di valutazione esteso.  
- **Licenza completa** – acquista per le distribuzioni in produzione.

### Inizializzazione di base del Viewer
Il codice seguente mostra il modo minimo per creare un'istanza `Viewer`. Mantienilo esattamente come mostrato:

```java
import com.groupdocs.viewer.Viewer;

// Initialize Viewer with your document path
try (Viewer viewer = new Viewer("path/to/your/document.docx")) {
    // Perform operations...
}
```

## Implementazione passo‑passo: ruota la prima pagina di 90 gradi

### 1. Importa i pacchetti richiesti
Questi import ti danno accesso alle opzioni di rendering PDF e all’enumerazione di rotazione.

```java
import com.groupdocs.viewer.Viewer;
import com.groupdocs.viewer.options.PdfViewOptions;
import com.groupdocs.viewer.options.Rotation;
```

### 2. Definisci le posizioni di output e crea il Viewer
Sostituisci i percorsi segnaposto con le tue directory effettive.

```java
import java.nio.file.Path;

public class RotateSpecificPage {
    public static void run() {
        Path outputDirectory = YOUR_OUTPUT_DIRECTORY.resolve("RotateSpecificPage");
        Path outputFilePath = outputDirectory.resolve("output.pdf");

        try (Viewer viewer = new Viewer(YOUR_DOCUMENT_DIRECTORY.resolve("Sample.docx"))) {
            // Proceed with the rotation steps below...
        }
    }
}
```

### 3. Configura le opzioni di visualizzazione PDF e applica la rotazione
Il metodo `rotatePage` accetta il numero della pagina (indice a 1) e un valore enum `Rotation`.

```java
PdfViewOptions viewOptions = new PdfViewOptions(outputFilePath);

// Specify which page to rotate (1 for first page) and the rotation angle
viewOptions.rotatePage(1, Rotation.ON_90_DEGREE);
```

### 4. Renderizza il documento
Infine, chiama `view` per generare il PDF ruotato.

```java
viewer.view(viewOptions);
```

#### Come funziona
- **PdfViewOptions** indica al Viewer di produrre un file PDF.  
- **rotatePage(int, Rotation)** ruota solo la pagina specificata, lasciando intatte le altre.  
- Il metodo supporta `ON_90_DEGREE`, `ON_180_DEGREE` e `ON_270_DEGREE`.

## Problemi comuni e soluzioni
| Sintomo | Probabile causa | Soluzione |
|---------|-----------------|-----------|
| **FileNotFoundException** | Percorso errato o cartella mancante | Verifica che `YOUR_OUTPUT_DIRECTORY` e `YOUR_DOCUMENT_DIRECTORY` esistano e siano leggibili. |
| **Formato file non supportato** | Tentativo di ruotare un formato non gestito da Viewer | Controlla la pagina dei [formati supportati da GroupDocs Viewer]. |
| **Nessuna rotazione visibile** | Numero di pagina errato (indice a 0) | Ricorda che `rotatePage` utilizza l’indicizzazione **a 1**. |
| **Errori di out‑of‑memory su documenti grandi** | Rendering di molti file grandi in un unico thread | Processa i documenti in sequenza o usa un pool di thread con concorrenza limitata. |

## Applicazioni pratiche

1. **Regolazioni di presentazione** – Converti una diapositiva verticale in orizzontale al volo.  
2. **Correzione massiva di documenti** – Automatizza la sistemazione di PDF scansionati catturati di lato.  
3. **Output pronto per la stampa** – Assicura che la grafica in orizzontale stampi correttamente su carta orientata verticalmente.

## Consigli sulle prestazioni

- **Chiudi le risorse rapidamente** – Il blocco `try‑with‑resources` elimina automaticamente il `Viewer`.  
- **Elaborazione batch** – Quando gestisci molti file, riutilizza una singola istanza `Viewer` per thread per ridurre l’overhead.  
- **Monitora la memoria** – Per documenti superiori a 100 MB, considera lo streaming dell’output su disco anziché mantenerlo in memoria.

## Domande frequenti

**D: Posso ruotare più pagine contemporaneamente?**  
R: Sì—chiama `rotatePage()` per ogni numero di pagina da ruotare.

**D: Esiste un modo per annullare la rotazione dopo il rendering?**  
R: Non direttamente. Dovresti renderizzare nuovamente il documento senza le opzioni di rotazione.

**D: Quali formati di file supportano la rotazione di pagina in GroupDocs Viewer?**  
R: DOCX, PDF, PPTX, XLSX e molti altri elencati nella documentazione ufficiale.

**D: Come posso ruotare le pagine in un batch di documenti automaticamente?**  
R: Avvolgi il codice in un ciclo che itera su una collezione di percorsi file, applicando la stessa logica `rotatePage` a ciascuno.

**D: Qual è la migliore pratica per gestire gli errori durante la rotazione?**  
R: Inserisci l’utilizzo del Viewer in un blocco `try‑catch`, registra l’eccezione e, se opportuno, continua con il file successivo.

## Risorse

- **Documentazione**: [GroupDocs Viewer Java Documentation](https://docs.groupdocs.com/viewer/java/)  
- **Riferimento API**: [GroupDocs API Reference](https://reference.groupdocs.com/viewer/java/)  
- **Download**: [Get GroupDocs Viewer for Java](https://releases.groupdocs.com/viewer/java/)  
- **Acquisto**: [Buy a License](https://purchase.groupdocs.com/buy)  
- **Prova gratuita**: [Try Free](https://releases.groupdocs.com/viewer/java/)  
- **Licenza temporanea**: [Request Temporary License](https://purchase.groupdocs.com/temporary-license/)  
- **Supporto**: [GroupDocs Forum](https://forum.groupdocs.com/c/viewer/9)

---

**Ultimo aggiornamento:** 2026-01-18  
**Testato con:** GroupDocs Viewer 25.2 per Java  
**Autore:** GroupDocs  

---