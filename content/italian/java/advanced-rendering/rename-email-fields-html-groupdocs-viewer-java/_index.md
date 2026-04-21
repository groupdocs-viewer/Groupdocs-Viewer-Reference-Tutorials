---
date: '2026-03-24'
description: Scopri come convertire le email in HTML e rinominare i campi delle email
  usando GroupDocs Viewer per Java. Questa guida mostra come visualizzare le email
  come HTML con intestazioni personalizzate.
keywords:
- rename email fields Java
- render emails HTML GroupDocs Viewer
- customize email metadata Java
title: Converti Email in HTML e Rinomina Campi – GroupDocs Viewer Java
type: docs
url: /it/java/advanced-rendering/rename-email-fields-html-groupdocs-viewer-java/
weight: 1
---

# Converti Email in HTML e Rinomina i Campi – GroupDocs Viewer Java

Se hai bisogno di **convertire email in HTML** dando alle intestazioni dell'email un aspetto personalizzato, sei nel posto giusto. In questo tutorial percorreremo i passaggi esatti per rinominare i campi email, **convertire email in HTML** e personalizzare le intestazioni email usando GroupDocs.Viewer per Java. Alla fine avrai una rappresentazione HTML pulita con i nomi delle intestazioni che preferisci, rendendo l'output più facile da leggere e da integrare nelle tue applicazioni.

![Rinomina i Campi Email Quando Converti Email in HTML con GroupDocs.Viewer per Java](/viewer/advanced-rendering/rename-email-fields-when-converting-emails-to-html-java.png)

### Cosa Imparerai
- Come usare GroupDocs.Viewer per Java per **convertire email in HTML**.  
- Tecniche per **rinominare i campi email** come “From”, “To”, “Sent” e “Subject”.  
- Best practice per configurare Maven e la licenza.  
- Scenari reali in cui **personalizzare le intestazioni email** aggiunge valore.

## Risposte Rapide
- **Cosa significa “convertire email in HTML”?** Indica il rendering di un file email (MSG/EML) come documento HTML pronto per il web.  
- **Quale libreria gestisce la conversione?** GroupDocs.Viewer per Java (v25.2+).  
- **È necessaria una licenza?** Una versione di prova funziona per la valutazione; è richiesta una licenza completa per la produzione.  
- **Posso cambiare qualsiasi nome di intestazione?** Sì, qualsiasi intestazione email standard può essere rimappata tramite `fieldTextMap`.  
- **L'output è HTML o risorse incorporate?** Puoi scegliere risorse incorporate per un unico file autonomo.

## Cos'è “convertire email in HTML” nel Contesto di GroupDocs.Viewer?
Convertire email in HTML significa prendere un file email grezzo e produrre una pagina HTML che visualizza il corpo del messaggio insieme ai suoi metadati. Quando **rinomini i campi email**, le etichette predefinite (ad es., “From”) vengono sostituite con testo personalizzato (ad es., “Mittente”), il che ti aiuta a allineare la terminologia aziendale o a migliorare la coerenza dell'interfaccia utente.

## Perché convertire email in HTML e rinominare i campi email?
- **Branding coerente:** Allinea l'output con il linguaggio della tua organizzazione.  
- **Migliore indicizzabilità:** Le intestazioni personalizzate possono essere indicizzate più efficacemente nei sistemi di archiviazione.  
- **Integrazione UI più fluida:** Adatta lo snippet HTML per inserirlo senza problemi in portali web o dashboard di supporto.

## Prerequisiti

### Librerie Richieste, Versioni e Dipendenze
- **GroupDocs.Viewer per Java** – versione 25.2 o successiva.  
- **Java Development Kit (JDK)** – versione 8+.

### Requisiti di Configurazione dell'Ambiente
- **Maven** per la gestione delle dipendenze.  
- Un IDE come IntelliJ IDEA, Eclipse o VS Code.

### Prerequisiti di Conoscenza
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

### Passaggi per Ottenere la Licenza
- **Prova Gratuita:** Scarica una prova gratuita da [GroupDocs Releases](https://releases.groupdocs.com/viewer/java/).  
- **Licenza Temporanea:** Ottieni una licenza temporanea per esplorare tutte le funzionalità senza limitazioni su [GroupDocs Temporary License](https://purchase.groupdocs.com/temporary-license/).  
- **Acquisto:** Per un utilizzo continuativo, considera l'acquisto di una licenza tramite [GroupDocs Purchase](https://purchase.groupdocs.com/buy).

### Inizializzazione e Configurazione di Base
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

## Come Convertire Email in HTML e Rinomare i Campi – Passo‑per‑Passo

### 1. Configura il Percorso della Directory di Output
```java
import java.nio.file.Path;

Path outputDirectory = Utils.getOutputDirectoryPath("YOUR_OUTPUT_DIRECTORY");
```
*Sostituisci `"YOUR_OUTPUT_DIRECTORY"` con la cartella in cui desideri salvare i file HTML.*

### 2. Definisci il Formato del Percorso del File di Pagina
```java
Path pageFilePathFormat = outputDirectory.resolve("page_{0}.html");
```
*`{0}` verrà sostituito dal numero di pagina durante il rendering.*

### 3. Crea una Mappatura dei Campi Email a Nuovi Nomi
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

### 4. Configura le Opzioni di Visualizzazione HTML
```java
import com.groupdocs.viewer.options.HtmlViewOptions;

HtmlViewOptions viewOptions = HtmlViewOptions.forEmbeddedResources(pageFilePathFormat);
viewOptions.getEmailOptions().setFieldTextMap(fieldTextMap);
```
*`forEmbeddedResources` incorpora CSS/JS all'interno dell'HTML, mentre `setFieldTextMap` applica i nomi personalizzati delle intestazioni.*

### 5. Renderizza l'Email in HTML
```java
try (Viewer viewer = new Viewer("YOUR_DOCUMENT_DIRECTORY/SAMPLE_MSG")) {
    viewer.view(viewOptions);
}
```
*Sostituisci `"YOUR_DOCUMENT_DIRECTORY/SAMPLE_MSG"` con il percorso reale del tuo file MSG.*

#### Suggerimenti per la Risoluzione dei Problemi
- Verifica che la directory di output sia scrivibile.  
- Assicurati che il file MSG di input esista e che il percorso sia corretto.  
- Usa la stessa versione di GroupDocs.Viewer (25.2) dichiarata in Maven.

## Applicazioni Pratiche
1. **Report Email Personalizzati:** Allinea le intestazioni email con la terminologia aziendale per report più chiari.  
2. **Sistemi di Archiviazione Email:** Migliora l'indicizzabilità usando nomi di intestazione standardizzati.  
3. **Piattaforme di Supporto Clienti:** Presenta i ticket con etichette di intestazione personalizzate per una migliore esperienza degli operatori.

## Considerazioni sulle Prestazioni
- Dispone degli oggetti `Viewer` con try‑with‑resources per liberare rapidamente la memoria.  
- Profilare batch di grandi dimensioni e considerare l'elaborazione di email in stream paralleli, se necessario.

## Conclusione
Ora sai **come convertire email in HTML** mentre **rinomini i campi email** e **personalizzi le intestazioni email** con GroupDocs.Viewer per Java. Questa tecnica ti offre il pieno controllo sulla presentazione dei metadati email negli output HTML.

### Prossimi Passi
- Sperimenta con mappature aggiuntive (ad es., CC, BCC).  
- Esplora altri formati di rendering come PDF o PNG.  
- Visita [GroupDocs Documentation](https://docs.groupdocs.com/viewer/java/) per approfondire le API.

## Domande Frequenti

**D: Questo approccio funziona con altri formati email come EML?**  
R: Sì, GroupDocs.Viewer supporta sia file MSG sia EML; la stessa logica di mappatura dei campi si applica.

**D: Posso generare l'HTML senza risorse incorporate?**  
R: Puoi usare `HtmlViewOptions.forExternalResources(...)` se preferisci file CSS/JS separati.

**D: Quale versione di GroupDocs.Viewer è stata testata?**  
R: Il codice è stato testato con GroupDocs.Viewer **25.2**.

**D: È possibile cambiare il font o lo stile delle intestazioni personalizzate?**  
R: Lo stile può essere applicato tramite CSS dopo il rendering, oppure puoi iniettare CSS personalizzato usando `HtmlViewOptions.getResourcesPath()`.

**D: Come recupero programmaticamente il percorso del file HTML generato?**  
R: Il percorso del file segue il modello definito in `pageFilePathFormat`; puoi costruirlo usando `String.format` con il numero di pagina.

## Risorse
- **Documentazione:** Guide complete disponibili su [GroupDocs Documentation](https://docs.groupdocs.com/viewer/java/).  
- **Riferimento API:** Informazioni dettagliate sull'API si trovano su [GroupDocs API Reference](https://reference.groupdocs.com/viewer/java/).  
- **Download GroupDocs.Viewer:** Accedi all'ultima versione tramite la [Downloads Page](https://releases.groupdocs.com/viewer/java/).

---

**Ultimo Aggiornamento:** 2026-03-24  
**Testato Con:** GroupDocs.Viewer 25.2  
**Autore:** GroupDocs