---
date: '2026-01-18'
description: Impara come ruotare le pagine PDF con GroupDocs.Viewer per Java. Questo
  tutorial passo‑passo copre la configurazione di Maven, la rotazione delle pagine
  (inclusa la rotazione del PDF di 90 gradi) e la risoluzione dei problemi.
keywords:
- rotate PDF pages Java
- GroupDocs.Viewer setup Java
- programmatically rotate PDF Java
title: Come ruotare le pagine PDF usando GroupDocs.Viewer in Java – Guida completa
type: docs
url: /it/java/advanced-rendering/rotate-pdf-pages-groupdocs-viewer-java/
weight: 1
---

# Come ruotare le pagine PDF usando GroupDocs.Viewer in Java

Ruotare pagine specifiche all'interno di un PDF può essere essenziale per allineare i documenti o regolare le diapositive di una presentazione. **In questa guida imparerai a ruotare le pagine pdf** programmaticamente con GroupDocs.Viewer, sia che tu debba ruotare il pdf di 90 gradi, capovolgere un'intera sezione o gestire più pagine in una singola chiamata.

![Rotate Specific PDF Pages with GroupDocs.Viewer for Java](/viewer/advanced-rendering/rotate-specific-pdf-pages-java.png)

**Cosa imparerai:**
- Configurare GroupDocs.Viewer nel tuo progetto Java (inclusa la configurazione Maven di GroupDocs Viewer)
- Ruotare programmaticamente pagine PDF specifiche (ruotare pdf 90 gradi, 180 gradi, ecc.)
- Configurazioni chiave per un utilizzo ottimale
- Risoluzione dei problemi comuni durante l'implementazione

## Risposte rapide
- **Quale libreria può ruotare le pagine PDF in Java?** GroupDocs.Viewer for Java.  
- **Posso ruotare una singola pagina di 90 gradi?** Sì, usa `rotatePage(pageNumber, Rotation.ON_90_DEGREE)`.  
- **Ho bisogno di una licenza per lo sviluppo?** È disponibile una licenza temporanea per la prova gratuita.  
- **Maven è obbligatorio?** Maven è il modo consigliato per gestire le dipendenze di GroupDocs.  
- **Come faccio a renderizzare le pagine ruotate?** Usa `HtmlViewOptions` e chiama `viewer.view(...)`.

## Prerequisiti

### Librerie e dipendenze richieste

Per iniziare, assicurati di avere:
- Java Development Kit (JDK) versione 8 o successiva installato sulla tua macchina.
- Un Integrated Development Environment (IDE), come IntelliJ IDEA o Eclipse.
- Maven per gestire le dipendenze del progetto.

### Requisiti per la configurazione dell'ambiente

1. **Maven Configuration**: Aggiungi GroupDocs.Viewer al tuo progetto Maven includendo i repository e le dipendenze necessarie nel tuo `pom.xml`.  
2. **License Acquisition**: Ottieni una licenza temporanea da GroupDocs, che ti permette di esplorare tutte le funzionalità senza limitazioni durante lo sviluppo. Visita [GroupDocs Free Trial](https://releases.groupdocs.com/viewer/java/) o richiedi una licenza temporanea nella [GroupDocs Temporary License Page](https://purchase.groupdocs.com/temporary-license/).

## Configurazione di GroupDocs.Viewer per Java

Per integrare GroupDocs.Viewer nel tuo progetto Java usando Maven, aggiorna il tuo `pom.xml`:

**Maven Configuration**  
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

### Inizializzazione e configurazione di base

Inizializza GroupDocs.Viewer specificando la directory dei documenti e i percorsi di output:

```java
Path YOUR_DOCUMENT_DIRECTORY = Path.of("YOUR_DOCUMENT_DIRECTORY");
Path YOUR_OUTPUT_DIRECTORY = Path.of("YOUR_OUTPUT_DIRECTORY");

// Format for page file paths
Path pageFilePathFormat = YOUR_OUTPUT_DIRECTORY.resolve("page_{0}.html");

HtmlViewOptions viewOptions = HtmlViewOptions.forEmbeddedResources(pageFilePathFormat);
```

## Guida all'implementazione

### Rotazione di pagine specifiche con GroupDocs.Viewer

**Panoramica:** Ruota pagine PDF specifiche per una migliore presentazione del documento.

#### Passo 1: Configurare la rotazione delle pagine

Ruota la prima pagina di 90 gradi e la seconda di 180 gradi usando `HtmlViewOptions`:

```java
// Rotate the first page by 90 degrees clockwise.
viewOptions.rotatePage(1, Rotation.ON_90_DEGREE);

// Rotate the second page by 180 degrees.
viewOptions.rotatePage(2, Rotation.ON_180_DEGREE);
```

#### Passo 2: Inizializzare Viewer e renderizzare

Crea un'istanza `Viewer` con il tuo documento e renderizza le pagine specificate:

```java
Viewer viewer = new Viewer(YOUR_DOCUMENT_DIRECTORY.resolve("SampleDocument.pdf"));

// Render the specified pages (1 and 2) using the configured options.
viewer.view(viewOptions, 1, 2);

// Always close the viewer to free resources.
viewer.close();
```

### Parametri e configurazione
- **Rotation**: Usa `rotatePage` con i numeri di pagina e gli angoli di rotazione. Rotazioni disponibili: `ON_90_DEGREE`, `ON_180_DEGREE`, `ON_270_DEGREE`.  
- **HtmlViewOptions**: Configura la conversione delle pagine PDF in HTML, garantendo l'inclusione delle risorse incorporate.  
- **pdf to html java**: La classe `HtmlViewOptions` gestisce la conversione da PDF a HTML preservando il layout.

#### Suggerimenti per la risoluzione dei problemi (troubleshoot pdf rotation)
- Verifica i percorsi verso il tuo documento e le directory di output.  
- Controlla la presenza di dipendenze mancanti o versioni di libreria errate.  
- Assicurati che la licenza sia applicata correttamente se si verificano restrizioni durante la prova.  
- Se riscontri picchi di memoria, considera di renderizzare le pagine in batch più piccoli (ruota più pagine pdf gradualmente).

## Applicazioni pratiche

### Casi d'uso reali
1. **Allineamento dei documenti** – Ruota i documenti scansionati per la corretta orientazione digitale.  
2. **Regolazioni delle presentazioni** – Modifica le diapositive all'interno dei PDF prima di condividerle.  
3. **Flussi di lavoro di archiviazione** – Regola automaticamente l'orientamento dei documenti storici durante la digitalizzazione.

### Possibilità di integrazione
Integra GroupDocs.Viewer con sistemi di gestione documentale basati su Java, piattaforme di contenuto o soluzioni aziendali personalizzate che richiedono capacità di visualizzazione dinamica.

## Considerazioni sulle prestazioni
- **Resource Management**: Chiudi l'istanza `Viewer` per rilasciare le risorse.  
- **Java Memory Management**: Monitora l'uso della memoria durante la renderizzazione di documenti di grandi dimensioni e utilizza strutture dati efficienti.  
- **Best Practices**: Utilizza la cache per documenti o pagine acceduti frequentemente.

## Conclusione

Questo tutorial ha coperto **how to rotate pdf** pagine usando GroupDocs.Viewer in Java, dalla configurazione dell'ambiente alle applicazioni pratiche. Sperimenta funzionalità aggiuntive come il watermarking o la conversione dei documenti in formati diversi.

**Prossimi passi:** Esplora altre funzionalità di GroupDocs.Viewer per migliorare le tue capacità di elaborazione dei documenti.

## Sezione FAQ

### Domande comuni
1. **Troubleshooting Rotation Issues**: Verifica che i numeri di pagina e i parametri di rotazione siano corretti.  
2. **Handling Large PDF Files**: Processa efficientemente documenti di grandi dimensioni con una gestione adeguata delle risorse.  
3. **Licensing Requirements**: Usa una licenza temporanea per lo sviluppo; acquista una licenza completa per la produzione.  
4. **Rotating Multiple Pages**: Chiama `rotatePage` più volte con numeri di pagina e angoli diversi.  
5. **Integration with Java Libraries**: Integra senza problemi GroupDocs.Viewer all'interno di applicazioni o framework più ampi.

## Domande frequenti

**Q: Posso ruotare tutte le pagine di un PDF in una volta?**  
A: Sì. Scorri i numeri di pagina e chiama `rotatePage(page, Rotation.ON_90_DEGREE)` per ogni pagina.

**Q: La rotazione influisce sul file PDF originale?**  
A: No. La rotazione viene applicata solo durante il processo di renderizzazione; il PDF di origine rimane invariato.

**Q: Cosa succede se un PDF è protetto da password?**  
A: Fornisci la password quando crei l'istanza `Viewer`: `new Viewer(path, password)`.

**Q: Come debuggo un errore “null pointer” durante la configurazione di HtmlViewOptions?**  
A: Assicurati che la directory di output esista e che `pageFilePathFormat` venga risolta correttamente.

**Q: Esiste un modo per ruotare le pagine durante la conversione in altri formati (es. PNG)?**  
A: Usa la stessa configurazione `rotatePage` con le opzioni di visualizzazione appropriate per il formato di destinazione.

## Risorse
- **Documentation**: [GroupDocs Viewer Documentation](https://docs.groupdocs.com/viewer/java/)
- **API Reference**: [GroupDocs API Reference](https://reference.groupdocs.com/viewer/java/)
- **Download**: [GroupDocs Download Page](https://releases.groupdocs.com/viewer/java/)
- **Purchase**: [GroupDocs Purchase Options](https://purchase.groupdocs.com/buy)
- **Free Trial**: [GroupDocs Free Trial](https://releases.groupdocs.com/viewer/java/)
- **Temporary License**: [Request Temporary License](https://purchase.groupdocs.com/temporary-license/)
- **Support**: [GroupDocs Support Forum](https://forum.groupdocs.com/c/viewer/9)

---

**Last Updated:** 2026-01-18  
**Tested With:** GroupDocs.Viewer 25.2 for Java  
**Author:** GroupDocs