---
date: '2026-01-05'
description: Scopri come rinominare i campi email, convertire l'email in HTML e personalizzare
  le intestazioni email usando GroupDocs.Viewer per Java.
keywords:
- rename email fields Java
- render emails HTML GroupDocs Viewer
- customize email metadata Java
title: Come rinominare i campi email durante il rendering delle email in HTML con
  GroupDocs.Viewer Java
type: docs
url: /it/java/advanced-rendering/rename-email-fields-html-groupdocs-viewer-java/
weight: 1
---

# Come rinominare i campi email durante il rendering delle email in HTML con GroupDocs.Viewer Java

Ti stai chiedendo **come rinominare i campi email** durante la conversione di un'email in HTML? In questa guida illustreremo i passaggi esatti per rinominare i campi email, **convertire l'email in HTML** e **personalizzare le intestazioni dell'email** usando GroupDocs.Viewer per Java. Alla fine avrai una rappresentazione HTML pulita con i nomi delle intestazioni che preferisci, rendendo l'output più facile da leggere e integrare nelle tue applicazioni.

![Rinominare i campi email durante la conversione delle email in HTML con GroupDocs.Viewer per Java](/viewer/advanced-rendering/rename-email-fields-when-converting-emails-to-html-java.png)

### Cosa imparerai
- Come usare GroupDocs.Viewer per Java per **convertire l'email in HTML**.  
- Tecniche per **rinominare i campi email** come “From”, “To”, “Sent” e “Subject”.  
- Best practice per configurare Maven e le licenze.  
- Scenari reali in cui **personalizzare le intestazioni dell'email** aggiunge valore.

## Risposte rapide
- **Cosa significa “how to rename email”?** Si riferisce alla mappatura dei nomi predefiniti delle intestazioni email a etichette personalizzate durante il rendering.  
- **Quale libreria gestisce la conversione?** GroupDocs.Viewer per Java (v25.2+).  
- **Ho bisogno di una licenza?** Una versione di prova funziona per la valutazione; è necessaria una licenza completa per la produzione.  
- **Posso cambiare qualsiasi nome di intestazione?** Sì, qualsiasi intestazione email standard può essere rimappata tramite `fieldTextMap`.  
- **L'output è HTML o risorse incorporate?** Puoi scegliere risorse incorporate per un unico file autonomo.

## Cos'è “How to Rename Email” nel contesto di GroupDocs.Viewer?
Rinominare i campi email significa sostituire le etichette predefinite (ad esempio “From”) con testo personalizzato (ad esempio “Sender”) quando l'email viene renderizzata in HTML. Questo è utile per allineare l'output alla terminologia aziendale o migliorare la leggibilità per l'utente finale.

## Perché convertire l'email in HTML e personalizzare le intestazioni dell'email?
- **Branding coerente:** Allinea il linguaggio della tua organizzazione in tutte le comunicazioni.  
- **Migliore indicizzabilità:** Le intestazioni personalizzate possono essere indicizzate più efficacemente nei sistemi di archiviazione.  
- **Migliore integrazione UI:** Adatta lo snippet HTML per inserirlo senza problemi nei portali web o nei cruscotti di supporto.

## Prerequisiti

### Librerie richieste, versioni e dipendenze
- **GroupDocs.Viewer per Java** – versione 25.2 o successiva.  
- **Java Development Kit (JDK)** – versione 8+.

### Requisiti per la configurazione dell'ambiente
- **Maven** per la gestione delle dipendenze.  
- Un IDE come IntelliJ IDEA, Eclipse o VS Code.

### Prerequisiti di conoscenza
Una conoscenza di base di Java e Maven ti aiuterà a seguire rapidamente.

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
Regola il percorso del file per puntare al tuo file `.msg`.

## Guida all'implementazione

### Rinominare i campi email – Passo‑per‑passo

#### 1. Configura il percorso della directory di output
```java
import java.nio.file.Path;

Path outputDirectory = Utils.getOutputDirectoryPath("YOUR_OUTPUT_DIRECTORY");
```
*Sostituisci `"YOUR_OUTPUT_DIRECTORY"` con la cartella in cui desideri salvare i file HTML.*

#### 2. Definisci il formato del percorso del file di pagina
```java
Path pageFilePathFormat = outputDirectory.resolve("page_{0}.html");
```
*`{0}` verrà sostituito dal numero di pagina durante il rendering.*

#### 3. Crea una mappatura dei campi email a nuovi nomi
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

#### 4. Configura le opzioni di visualizzazione HTML
```java
import com.groupdocs.viewer.options.HtmlViewOptions;

HtmlViewOptions viewOptions = HtmlViewOptions.forEmbeddedResources(pageFilePathFormat);
viewOptions.getEmailOptions().setFieldTextMap(fieldTextMap);
```
*`forEmbeddedResources` raggruppa CSS/JS all'interno dell'HTML, mentre `setFieldTextMap` applica i nomi delle intestazioni personalizzate.*

#### 5. Renderizza l'email in HTML
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
- Rilascia gli oggetti `Viewer` con try‑with‑resources per liberare rapidamente la memoria.  
- Esegui il profiling di grandi batch e considera l'elaborazione delle email in stream paralleli se necessario.

## Conclusione
Ora sai **come rinominare i campi email** mentre **converti l'email in HTML** e **personalizzi le intestazioni email** con GroupDocs.Viewer per Java. Questa tecnica ti offre il pieno controllo sulla presentazione dei metadati dell'email negli output HTML.

### Prossimi passi
- Sperimenta ulteriori mappature di campi (ad esempio CC, BCC).  
- Esplora altri formati di rendering come PDF o PNG.  
- Visita [GroupDocs Documentation](https://docs.groupdocs.com/viewer/java/) per approfondimenti sull'API.

## Sezione FAQ
1. **Posso rinominare tutte le intestazioni email usando questo metodo?**  
   - Sì, puoi mappare qualsiasi intestazione email standard a un nuovo nome secondo le tue esigenze.  
2. **È possibile usare GroupDocs.Viewer senza licenza?**  
   - È disponibile una versione di prova per i test, ma la versione completa richiede una licenza valida.  
3. **Come gestire grandi volumi di email in modo efficiente con GroupDocs.Viewer?**  
   - Considera l'elaborazione batch e ottimizza le risorse di sistema per gestire dataset più grandi in modo efficace.  
4. **Posso integrare questa soluzione in un'applicazione Java esistente?**  
   - Assolutamente sì, l'integrazione è semplice usando le dipendenze Maven.  
5. **Dove posso trovare supporto se incontro problemi?**  
   - Visita il [GroupDocs Forum](https://forum.groupdocs.com/c/viewer/9) per assistenza dalla community e dal supporto ufficiale.

## Domande frequenti

**Q: Questo approccio funziona con altri formati email come EML?**  
A: Sì, GroupDocs.Viewer supporta sia file MSG che EML; la stessa logica di mappatura dei campi si applica.

**Q: Posso generare l'HTML senza risorse incorporate?**  
A: Puoi usare `HtmlViewOptions.forExternalResources(...)` se preferisci file CSS/JS separati.

**Q: Quale versione di GroupDocs.Viewer è stata testata?**  
A: Il codice è stato testato con GroupDocs.Viewer **25.2**.

**Q: È possibile cambiare il font o lo stile delle intestazioni personalizzate?**  
A: Lo stile può essere applicato tramite CSS dopo il rendering, oppure puoi iniettare CSS personalizzato usando `HtmlViewOptions.getResourcesPath()`.

**Q: Come recuperare programmaticamente il percorso del file HTML generato?**  
A: Il percorso del file segue il modello definito in `pageFilePathFormat`; puoi costruirlo usando `String.format` con il numero di pagina.

## Risorse
- **Documentazione:** Guide complete sono disponibili su [GroupDocs Documentation](https://docs.groupdocs.com/viewer/java/).  
- **Riferimento API:** Informazioni dettagliate sull'API sono disponibili su [GroupDocs API Reference](https://reference.groupdocs.com/viewer/java/).  
- **Download GroupDocs.Viewer:** Accedi all'ultima versione tramite la [Downloads Page](https://releases.groupdocs.com/viewer/java/).

---

**Ultimo aggiornamento:** 2026-01-05  
**Testato con:** GroupDocs.Viewer 25.2  
**Autore:** GroupDocs  

---