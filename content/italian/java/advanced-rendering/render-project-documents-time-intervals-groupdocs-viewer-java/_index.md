---
date: '2026-01-15'
description: Scopri come utilizzare GroupDocs Viewer per generare HTML dai documenti
  di progetto entro intervalli di tempo specifici. Questa guida copre l'installazione,
  il codice e casi d'uso reali.
keywords:
- render project documents
- time intervals Java
- GroupDocs Viewer API
title: Come utilizzare GroupDocs Viewer per visualizzare i documenti di progetto per
  intervalli di tempo in Java
type: docs
url: /it/java/advanced-rendering/render-project-documents-time-intervals-groupdocs-viewer-java/
weight: 1
---

# Come utilizzare GroupDocs Viewer per renderizzare documenti di progetto per intervalli di tempo in Java

Se stai cercando **come utilizzare GroupDocs** per renderizzare i piani di progetto in una finestra temporale specifica, sei nel posto giusto. In questo tutorial percorreremo l'intero processo—dalla configurazione di Maven alla generazione di HTML dai documenti di progetto—così potrai incorporare visualizzazioni precise della timeline direttamente nelle tue applicazioni.

![Renderizza documenti di progetto per intervalli di tempo con GroupDocs.Viewer per Java](/viewer/advanced-rendering/render-project-documents-by-time-intervals-java.png)

## Risposte rapide
- **Cosa fa la funzionalità?** Renderizza solo la parte di un file Microsoft Project compresa tra una data di inizio e una data di fine.  
- **Quale formato di output viene utilizzato?** HTML con risorse incorporate, perfetto per l'integrazione web.  
- **È necessaria una licenza?** Una versione di prova gratuita è sufficiente per la valutazione; è necessaria una licenza completa per la produzione.  
- **Posso modificare l'intervallo di date a runtime?** Sì—regola i valori `setStartDate` e `setEndDate` nelle opzioni di rendering.  
- **È supportato su tutte le versioni di Java?** Funziona con Java 8+ purché si utilizzi GroupDocs.Viewer 25.2 o versioni successive.

## Cos'è “Come utilizzare GroupDocs” in questo contesto?
GroupDocs Viewer è una libreria Java che converte oltre 100 formati di file in rappresentazioni adatte al web. Quando **come utilizzare GroupDocs** per i file di progetto, ottieni la possibilità di estrarre, visualizzare e condividere i dati di pianificazione senza richiedere Microsoft Project sul lato client.

## Perché renderizzare documenti di progetto con intervalli di tempo?
- **Analisi mirata:** Mostra solo la fase di tuo interesse (ad es., Q3 2024).  
- **Prestazioni:** Un output HTML più piccolo significa caricamenti di pagina più rapidi.  
- **Integrazione:** Incorpora visualizzazioni della timeline in dashboard, portali di reporting o strumenti PM personalizzati.  

## Prerequisiti

- **GroupDocs.Viewer per Java** versione 25.2 o superiore.  
- Java Development Kit (JDK) 8 o successivo.  
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

### Passaggi per l'acquisizione della licenza

1. **Prova gratuita** – Scarica una versione di prova dalla [pagina di download di GroupDocs](https://releases.groupdocs.com/viewer/java/).  
2. **Licenza temporanea** – Ottieni una licenza temporanea per test estesi tramite [questo link](https://purchase.groupdocs.com/temporary-license/).  
3. **Acquisto** – Per un utilizzo di produzione senza restrizioni, acquista una licenza su [GroupDocs Purchase Page](https://purchase.groupdocs.com/buy).

### Inizializzazione di base del Viewer

Il seguente snippet mostra come creare un'istanza `Viewer` che punta a un file Microsoft Project (`.mpp`):

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

## Guida all'implementazione passo‑passo

### 1. Definisci la directory di output

Crea una cartella dove verranno salvate le pagine HTML generate:

```java
import java.nio.file.Path;

Path outputDirectory = Path.of("YOUR_OUTPUT_DIRECTORY", "RenderProjectTimeInterval");
Path pageFilePathFormat = outputDirectory.resolve("page_{0}.html");
```

*Perché?* Tenere i file renderizzati organizzati rende più semplice servirli da un server web o incorporarli in un'interfaccia utente.

### 2. Inizializza il Viewer con il tuo file di progetto

```java
try (Viewer viewer = new Viewer("YOUR_DOCUMENT_DIRECTORY/SAMPLE_MPP")) {
    // Continue with rendering steps
}
```

*Perché?* Il caricamento del documento prepara il parser interno e rende accessibili i metadati specifici del progetto.

### 3. Recupera le informazioni di visualizzazione per i file di progetto

```java
import com.groupdocs.viewer.options.ViewInfoOptions;
import com.groupdocs.viewer.results.ProjectManagementViewInfo;

ViewInfoOptions viewInfoOptions = ViewInfoOptions.forHtmlView();
ProjectManagementViewInfo viewInfo = (ProjectManagementViewInfo) viewer.getViewInfo(viewInfoOptions);
```

*Perché?* `ProjectManagementViewInfo` fornisce le date di inizio e fine del programma, che utilizzerai in seguito per limitare l'ambito del rendering.

### 4. Configura le opzioni di rendering HTML (Genera HTML dal progetto)

```java
import com.groupdocs.viewer.options.HtmlViewOptions;

HtmlViewOptions viewOptions = HtmlViewOptions.forEmbeddedResources(pageFilePathFormat);
viewOptions.getProjectManagementOptions().setStartDate(viewInfo.getStartDate());
viewOptions.getProjectManagementOptions().setEndDate(viewInfo.getEndDate());
```

*Perché?* Impostare `StartDate` e `EndDate` indica a GroupDocs di **generare HTML dal progetto** solo per i dati compresi in quell'intervallo.

### 5. Esegui il processo di rendering

```java
viewer.view(viewOptions);
```

*Perché?* Questa chiamata produce una serie di pagine HTML autonome che rappresentano la porzione temporale selezionata del tuo programma di progetto.

## Problemi comuni e risoluzione

- **Percorsi file errati** – Verifica che sia il file `.mpp` di origine sia la directory di output esistano.  
- **Tipo di file non supportato** – Assicurati che il documento sia in un formato Project supportato (ad es., `.mpp`, `.mpt`).  
- **Errori di licenza** – Una licenza di prova può imporre limiti di rendering; passa a una licenza completa per un uso senza restrizioni.  

## Applicazioni pratiche

1. **Analisi della timeline di progetto** – Mostra agli stakeholder solo la fase corrente.  
2. **Reporting automatizzato** – Genera report HTML con limiti temporali per gli aggiornamenti settimanali di stato.  
3. **Integrazione con dashboard** – Incorpora le pagine renderizzate in strumenti BI o portali personalizzati.  
4. **Archiviazione** – Conserva uno snapshot web‑friendly del programma di un progetto per riferimento futuro.  

## Suggerimenti sulle prestazioni

- Usa l'opzione *embedded resources* per mantenere ogni pagina HTML autonoma, riducendo le richieste HTTP.  
- Per progetti molto grandi, considera di renderizzare in blocchi di date più piccoli per mantenere basso l'uso di memoria.  
- Pulisci i file temporanei dopo averli serviti per evitare l'accumulo di spazio su disco.  

## Conclusione

Ora sai **come utilizzare GroupDocs** Viewer per renderizzare documenti di progetto entro un intervallo di tempo specifico e **generare HTML dai dati del progetto** in Java. Questa funzionalità semplifica le visualizzazioni della timeline, migliora l'efficienza del reporting e si integra perfettamente con le moderne applicazioni web.

### Prossimi passi
- Esplora funzionalità aggiuntive del Viewer come watermark, protezione con password o styling CSS personalizzato.  
- Combina questa pipeline di rendering con un'API REST per fornire visualizzazioni della timeline su richiesta.  

## Domande frequenti

**D: Quali formati di file supporta GroupDocs.Viewer?**  
R: GroupDocs.Viewer supporta un'ampia gamma di formati tra cui Microsoft Project (MPP), PDF, Word, Excel, PowerPoint e molti altri.

**D: Come posso iniziare con una prova gratuita di GroupDocs.Viewer?**  
R: Puoi scaricare la versione di prova da [qui](https://releases.groupdocs.com/viewer/java/).

**D: Posso renderizzare i documenti senza incorporare le risorse?**  
R: Sì, puoi scegliere un'opzione di visualizzazione HTML diversa che fa riferimento a risorse esterne invece di incorporarle.

**D: Cosa succede se il mio documento è troppo grande per il rendering?**  
R: Considera di suddividere il documento in sezioni più piccole o di renderizzare solo l'intervallo di date richiesto, come mostrato sopra.

**D: Come gestisco gli errori di rendering?**  
R: Verifica tutte le impostazioni di configurazione, assicurati di avere una licenza valida e consulta la documentazione di GroupDocs per i codici di errore dettagliati.

## Risorse
- **Documentazione**: [GroupDocs Viewer Java Documentation](https://docs.groupdocs.com/viewer/java/)
- **Riferimento API**: [GroupDocs API Reference](https://reference.groupdocs.com/viewer/java/)
- **Download**: [GroupDocs Downloads](https://releases.groupdocs.com/viewer/java/)
- **Acquisto**: [Buy GroupDocs License](https://purchase.groupdocs.com/buy)
- **Prova gratuita**: [Try the Free Version](https://releases.groupdocs.com/viewer/java/)
- **Licenza temporanea**: [Get a Temporary License](https://purchase.groupdocs.com/temporary-license/)
- **Supporto**: [GroupDocs Forum](https://forum.groupdocs.com/c/viewer/9)

---

**Ultimo aggiornamento:** 2026-01-15  
**Testato con:** GroupDocs.Viewer 25.2 per Java  
**Autore:** GroupDocs