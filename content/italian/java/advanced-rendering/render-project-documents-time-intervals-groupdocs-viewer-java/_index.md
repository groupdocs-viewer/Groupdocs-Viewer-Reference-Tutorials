---
date: '2026-03-29'
description: Scopri come creare una visualizzazione HTML di file MPP usando GroupDocs
  Viewer in Java, rendendo i documenti di progetto per intervalli di tempo con codice
  passo‑passo.
keywords:
- render project documents
- time intervals Java
- GroupDocs Viewer API
title: Crea visualizzazione HTML di MPP con GroupDocs Viewer (Java)
type: docs
url: /it/java/advanced-rendering/render-project-documents-time-intervals-groupdocs-viewer-java/
weight: 1
---

# Come utilizzare GroupDocs Viewer per rendere i documenti di progetto per intervalli di tempo in Java

In questo tutorial imparerai come **create html view mpp** con GroupDocs Viewer per Java, consentendo di rendere solo le parti di un file Microsoft Project che rientrano in un intervallo di tempo specifico. Ti guideremo attraverso la configurazione di Maven, la configurazione del codice e scenari reali in modo da poter incorporare visualizzazioni di timeline precise direttamente nelle tue applicazioni.

![Render Documenti di Progetto per Intervalli di Tempo con GroupDocs.Viewer per Java](/viewer/advanced-rendering/render-project-documents-by-time-intervals-java.png)

## Risposte Rapide
- **Cosa fa la funzionalità?** Rende solo la parte di un file Microsoft Project che cade tra una data di inizio e una data di fine.  
- **Quale formato di output viene utilizzato?** HTML con risorse incorporate, perfetto per l'integrazione web.  
- **Ho bisogno di una licenza?** Una versione di prova gratuita funziona per la valutazione; è necessaria una licenza completa per la produzione.  
- **Posso modificare l'intervallo di date a runtime?** Sì—regola i valori `setStartDate` e `setEndDate` nelle opzioni di rendering.  
- **È supportato su tutte le versioni di Java?** Funziona con Java 8+ purché si utilizzi GroupDocs.Viewer 25.2 o versioni successive.

## Come creare html view mpp per Documenti di Progetto
GroupDocs Viewer può convertire i file Microsoft Project (`.mpp`, `.mpt`) in pagine HTML. Configurando le date di inizio e fine nelle opzioni di rendering, limiti l'output alla porzione temporale di tuo interesse, riducendo la dimensione del file e velocizzando il caricamento delle pagine.

## Cos'è “How to Use GroupDocs” in questo contesto?
GroupDocs Viewer è una libreria Java che converte oltre 100 formati di file in rappresentazioni adatte al web. Quando **how to use GroupDocs** per i file di progetto, ottieni la possibilità di estrarre, visualizzare e condividere i dati di programmazione senza richiedere Microsoft Project sul lato client.

## Perché rendere i Documenti di Progetto con Intervalli di Tempo?
- **Analisi mirata:** Mostra solo la fase di tuo interesse (ad esempio, Q3 2024).  
- **Prestazioni:** Un output HTML più piccolo significa caricamenti di pagina più rapidi.  
- **Integrazione:** Integra visualizzazioni di timeline in dashboard, portali di reporting o strumenti PM personalizzati.  

## Prerequisiti
- **GroupDocs.Viewer for Java** versione 25.2 o superiore.  
- Java Development Kit (JDK) 8 o superiore.  
- Un IDE come IntelliJ IDEA o Eclipse.  
- Conoscenza di base di Maven.  

## Configurazione di GroupDocs.Viewer per Java

### Dipendenza Maven

Aggiungi il repository e la dipendenza al tuo `pom.xml`:

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

### Passaggi per l'Acquisizione della Licenza

1. **Free Trial** – Scarica una versione di prova da [GroupDocs' download page](https://releases.groupdocs.com/viewer/java/).  
2. **Temporary License** – Ottieni una licenza temporanea per test estesi tramite [this link](https://purchase.groupdocs.com/temporary-license/).  
3. **Purchase** – Per un utilizzo di produzione senza restrizioni, acquista una licenza su [GroupDocs Purchase Page](https://purchase.groupdocs.com/buy).

### Inizializzazione Base del Viewer

Il frammento seguente mostra come creare un'istanza `Viewer` che punta a un file Microsoft Project (`.mpp`):

```java
import com.groupdocs.viewer.Viewer;

public class ViewerSetup {
    public static void main(String[] args) {
        try (Viewer viewer = new Viewer("path/to/your/document.mpp")) {
            // Your rendering code goes here
        }
    }
}
```

## Guida all'Implementazione Passo‑per‑Passo

### 1. Definisci la Directory di Output

Crea una cartella dove verranno salvate le pagine HTML generate:

```java
import java.nio.file.Path;

Path outputDirectory = Path.of("YOUR_OUTPUT_DIRECTORY", "RenderProjectTimeInterval");
Path pageFilePathFormat = outputDirectory.resolve("page_{0}.html");
```

*Perché?* Tenere i file renderizzati organizzati rende più facile servirli da un server web o incorporarli in un'interfaccia utente.

### 2. Inizializza il Viewer con il Tuo File di Progetto

```java
try (Viewer viewer = new Viewer("YOUR_DOCUMENT_DIRECTORY/SAMPLE_MPP")) {
    // Continue with rendering steps
}
```

*Perché?* Caricare il documento prepara il parser interno e rende accessibili i metadati specifici del progetto.

### 3. Recupera le Informazioni di Visualizzazione per i File di Progetto

```java
import com.groupdocs.viewer.options.ViewInfoOptions;
import com.groupdocs.viewer.results.ProjectManagementViewInfo;

ViewInfoOptions viewInfoOptions = ViewInfoOptions.forHtmlView();
ProjectManagementViewInfo viewInfo = (ProjectManagementViewInfo) viewer.getViewInfo(viewInfoOptions);
```

*Perché?* `ProjectManagementViewInfo` fornisce le date di inizio e fine del programma, che utilizzerai in seguito per limitare l'ambito del rendering.

### 4. Configura le Opzioni di Rendering HTML (Genera HTML dal Progetto)

```java
import com.groupdocs.viewer.options.HtmlViewOptions;

HtmlViewOptions viewOptions = HtmlViewOptions.forEmbeddedResources(pageFilePathFormat);
viewOptions.getProjectManagementOptions().setStartDate(viewInfo.getStartDate());
viewOptions.getProjectManagementOptions().setEndDate(viewInfo.getEndDate());
```

*Perché?* Impostare `StartDate` e `EndDate` indica a GroupDocs di **generate html view mpp** dati solo all'interno di quella finestra.

### 5. Esegui il Processo di Rendering

```java
viewer.view(viewOptions);
```

*Perché?* Questa chiamata produce una serie di pagine HTML autonome che rappresentano la porzione temporale selezionata del programma del tuo progetto.

## Problemi Comuni & Risoluzione dei Problemi
- **Percorsi file errati** – Verifica che sia il file `.mpp` di origine sia la directory di output esistano.  
- **Tipo di file non supportato** – Assicurati che il documento sia in un formato Project supportato (ad esempio, `.mpp`, `.mpt`).  
- **Errori di licenza** – Una licenza di prova può imporre limiti di rendering; passa a una licenza completa per un uso senza restrizioni.  

## Applicazioni Pratiche
1. **Analisi della Timeline del Progetto** – Mostra agli stakeholder solo la fase corrente.  
2. **Reporting Automatizzato** – Genera report HTML con vincoli temporali per aggiornamenti settimanali.  
3. **Integrazione con Dashboard** – Integra le pagine renderizzate in strumenti BI o portali personalizzati.  
4. **Archiviazione** – Conserva uno snapshot web‑friendly del programma di un progetto per riferimento futuro.  

## Suggerimenti sulle Prestazioni
- Usa l'opzione *embedded resources* per mantenere ogni pagina HTML autonoma, riducendo le richieste HTTP.  
- Per progetti molto grandi, considera di renderizzare in blocchi di date più piccoli per mantenere basso l'uso della memoria.  
- Pulisci i file temporanei dopo averli serviti per evitare l'ingrossamento del disco.  

## Conclusione
Ora sai **how to use GroupDocs** Viewer per rendere i documenti di progetto entro un intervallo di tempo specifico e **generate HTML from project** dati in Java. Questa capacità semplifica le visualizzazioni delle timeline, migliora l'efficienza del reporting e si integra perfettamente con le moderne applicazioni web.

### Prossimi Passi
- Esplora funzionalità aggiuntive del Viewer come watermarking, protezione con password o styling CSS personalizzato.  
- Combina questa pipeline di rendering con un'API REST per fornire visualizzazioni di timeline on‑demand.  

## Domande Frequenti

**Q: Quali formati di file supporta GroupDocs.Viewer?**  
A: GroupDocs.Viewer supporta un'ampia gamma di formati, tra cui Microsoft Project (MPP), PDF, Word, Excel, PowerPoint e molti altri.

**Q: Come posso iniziare con una versione di prova gratuita di GroupDocs.Viewer?**  
A: Puoi scaricare la versione di prova da [here](https://releases.groupdocs.com/viewer/java/).

**Q: Posso renderizzare documenti senza incorporare risorse?**  
A: Sì, puoi scegliere un'opzione di visualizzazione HTML diversa che fa riferimento a risorse esterne invece di incorporarle.

**Q: Cosa succede se il mio documento è troppo grande per il rendering?**  
A: Considera di suddividere il documento in sezioni più piccole o di renderizzare solo l'intervallo di date richiesto, come mostrato sopra.

**Q: Come gestisco gli errori di rendering?**  
A: Verifica tutte le impostazioni di configurazione, assicurati di avere una licenza valida e consulta la documentazione di GroupDocs per i codici di errore dettagliati.

## Risorse
- **Documentation**: [GroupDocs Viewer Java Documentation](https://docs.groupdocs.com/viewer/java/)  
- **API Reference**: [GroupDocs API Reference](https://reference.groupdocs.com/viewer/java/)  
- **Download**: [GroupDocs Downloads](https://releases.groupdocs.com/viewer/java/)  
- **Purchase**: [Buy GroupDocs License](https://purchase.groupdocs.com/buy)  
- **Free Trial**: [Try the Free Version](https://releases.groupdocs.com/viewer/java/)  
- **Temporary License**: [Get a Temporary License](https://purchase.groupdocs.com/temporary-license/)  
- **Support**: [GroupDocs Forum](https://forum.groupdocs.com/c/viewer/9)

---

**Ultimo aggiornamento:** 2026-03-29  
**Testato con:** GroupDocs.Viewer 25.2 for Java  
**Autore:** GroupDocs  

---