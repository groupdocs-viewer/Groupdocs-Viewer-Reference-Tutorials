---
date: '2026-03-08'
description: Scopri come ottenere una licenza temporanea, configurare GroupDocs.Viewer
  per Java usando file locali o URL e verificare la disponibilità del percorso della
  licenza.
keywords:
- GroupDocs.Viewer Java license
- setting license in Java
- HTTP URL-based licenses
title: Come ottenere una licenza temporanea e impostare le licenze in GroupDocs.Viewer
  Java
type: docs
url: /it/java/getting-started/groupdocs-viewer-java-license-setup/
weight: 1
---

**Last Updated:** 2026-03-08 -> "**Ultimo aggiornamento:** 2026-03-08"

**Tested With:** GroupDocs.Viewer 25.2 for Java -> "**Testato con:** GroupDocs.Viewer 25.2 per Java"

**Author:** GroupDocs -> "**Autore:** GroupDocs"

Make sure to keep markdown formatting.

Now produce final content.# Come ottenere una licenza temporanea e impostare le licenze in GroupDocs.Viewer Java

Gestire le licenze in modo efficiente è fondamentale quando si integrano librerie di terze parti come **GroupDocs.Viewer for Java** nelle proprie applicazioni. Questa guida mostra **come ottenere una licenza temporanea**, impostarla da un file locale o da un URL HTTP e verificare che il percorso della licenza sia corretto. Alla fine di questo tutorial avrai una configurazione di licenza affidabile e pronta per la produzione, che mantiene la tua app conforme e performante.

![File and URL Setup with GroupDocs.Viewer for Java](/viewer/getting-started/file-and-url-setup-png.png)

## Risposte rapide
- **Come posso ottenere una licenza temporanea?** Richiedila dalla pagina di licenza temporanea di GroupDocs e scarica il file *.lic*.  
- **Posso caricare la licenza da un URL?** Sì – basta puntare `License.setLicense` a un indirizzo HTTP che restituisce un file di licenza valido.  
- **Cosa succede se il percorso della licenza è mancante?** Implementa un controllo per mostrare indicazioni e impedire l'avvio del visualizzatore.  
- **Devo riavviare l'app dopo aver cambiato la licenza?** No, `License.setLicense` può essere chiamato a runtime.  
- **Quale versione di Java è richiesta?** Si consiglia JDK 8 o superiore.

## Cos'è una licenza temporanea?
Una **licenza temporanea** è una chiave a tempo limitato rilasciata da GroupDocs che consente di valutare il prodotto senza acquistare una licenza completa. Si comporta esattamente come una licenza permanente finché è valida, permettendoti di testare tutte le funzionalità in un ambiente reale.

## Perché ottenere una licenza temporanea?
- **Valutazione rapida:** Ottieni subito tutte le funzionalità per progetti proof‑of‑concept.  
- **Nessun impegno finanziario:** Prova prima di acquistare.  
- **Integrazione semplice:** Funziona con le stesse chiamate API di una licenza permanente.

## Prerequisiti
1. **Java Development Kit (JDK):** Versione 8 o superiore.  
2. **IDE:** IntelliJ IDEA, Eclipse o qualsiasi IDE compatibile con Java.  
3. **Libreria GroupDocs.Viewer per Java:** Aggiunta al tuo progetto (vedi configurazione Maven di seguito).  
4. **Conoscenze di base di Java:** Familiarità con classi, import e gestione delle eccezioni.

## Configurazione di GroupDocs.Viewer per Java
Per iniziare, includi la libreria nel tuo progetto Maven.

### Configurazione Maven
Aggiungi la seguente configurazione al tuo file `pom.xml`:
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

### Ottenere una licenza
Per usare GroupDocs.Viewer, ottieni una licenza:
- **Prova gratuita:** Scarica dal [sito GroupDocs](https://releases.groupdocs.com/viewer/java/).  
- **Licenza temporanea:** Richiedila alla [pagina di licenza temporanea](https://purchase.groupdocs.com/temporary-license/).  
- **Acquisto:** Per una soluzione permanente, considera l'acquisto di una licenza dalla [pagina di acquisto GroupDocs](https://purchase.groupdocs.com/buy).

### Inizializzazione di base
Una volta aggiunta la libreria, puoi inizializzare il visualizzatore:
```java
import com.groupdocs.viewer.License;

public class InitializeViewer {
    public static void main(String[] args) {
        License license = new License();
        // Set the path to your license file or URL here
        license.setLicense("YOUR_LICENSE_PATH");
        System.out.println("GroupDocs.Viewer initialized successfully.");
    }
}
```

## Come ottenere una licenza temporanea e impostarla da un file
### Panoramica
Impostare una licenza da un file locale è l'approccio più semplice e funziona anche quando l'applicazione è offline.

### Passaggi di implementazione
1. **Define the License Path** – point to the *.lic* file you received after requesting a temporary license:
```java
final String licensePath = "YOUR_DOCUMENT_DIRECTORY/your-license-file.lic";
```
2. **Apply the License** – use the `License` class to load it:
```java
import com.groupdocs.viewer.License;

public class SetLicenseFromFile {
    public static void run() {
        if (licensePath != null && !licensePath.startsWith("http")) {
            License license = new License();
            license.setLicense(licensePath);
            System.out.println("License set successfully.");
        } else {
            // Handle cases where the path is not valid
            System.err.println(
                "We do not ship any license with this example.\n" +
                "Visit the GroupDocs site to obtain either a temporary or permanent license.\n" +
                "Learn more about licensing at https://purchase.groupdocs.com/faqs/licensing.\n" +
                "Lear how to request temporary license at https://purchase.groupdocs.com/temporary-license.");
        }
    }
}
```
**Suggerimenti:**  
- Verifica che il percorso del file sia assoluto o relativo alla directory di lavoro.  
- Assicurati che il file abbia i permessi di lettura per l'utente che esegue la JVM.

## Come gestire un URL di licenza
### Panoramica
Una licenza basata su URL è comoda per le distribuzioni cloud dove il file di licenza risiede in un bucket di storage sicuro.

### Passaggi di implementazione
1. **Define the License URL** – replace the placeholder with your actual endpoint:
```java
final String licensePath = "http://example.com/license.lic";
```
2. **Detect and Log URL usage** – the sample below simply notifies you that a URL was supplied:
```java
public class HandleLicenseURL {
    public static void run() {
        if (licensePath != null && licensePath.startsWith("http")) {
            System.err.println("License path was not provided, license URL is found instead!");
        }
    }
}
```
**Suggerimenti:**  
- In produzione scaricheresti il file (ad esempio con `java.net.HttpURLConnection`) e poi chiameresti `license.setLicense(stream)`.  
- Aggiungi logica di retry e gestione dei timeout per affrontare problemi di rete transitori.

## Come verificare la disponibilità della licenza (verificare il percorso della licenza)
### Panoramica
Prima di tentare di caricare una licenza, è buona pratica **verificare la disponibilità della licenza** così da guidare sviluppatori o utenti a ottenere una licenza temporanea quando necessario.

### Passaggi di implementazione
1. **Simulate a missing license path**:
```java
final String licensePath = null;
```
2. **Provide clear guidance if the path is absent**:
```java
public class CheckLicensePathAvailability {
    public static void run() {
        if (licensePath == null) {
            System.out.println(
                "\nWe do not ship any license with this example.\n" +
                "Visit the GroupDocs site to obtain either a temporary or permanent license.\n" +
                "Learn more about licensing at https://purchase.groupdocs.com/faqs/licensing.\n" +
                "Lear how to request temporary license at https://purchase.groupdocs.com/temporary-license.");
        }
    }
}
```
**Suggerimenti:**  
- Registra questo messaggio all'avvio così i team operativi sanno che manca una licenza.  
- Considera di terminare l'applicazione o disabilitare le funzionalità del visualizzatore finché non viene fornita una licenza valida.

## Applicazioni pratiche
Comprendere come **ottenere una licenza temporanea**, impostarla da un file o da un URL e **verificare il percorso della licenza** apre diversi scenari reali:
1. **Sistemi di gestione documentale** – incorpora un visualizzatore che valida automaticamente la licenza ad ogni avvio.  
2. **Piattaforme SaaS cloud** – archivia la licenza in uno storage blob protetto e caricala via URL per aggiornamenti senza downtime.  
3. **Distribuzioni aziendali** – utilizza una licenza temporanea durante le fasi pilota prima di acquistare una licenza a pieno regime.

## Considerazioni sulle prestazioni
- **Utilizzo delle risorse:** Carica la licenza una sola volta all'avvio dell'applicazione; chiamate ripetute aggiungono I/O non necessario.  
- **Gestione della memoria:** L'oggetto `License` mantiene uno stato minimo, ma chiudi sempre gli stream se scarichi manualmente la licenza.

## Conclusione
Seguendo i passaggi sopra potrai **ottenere una licenza temporanea**, configurare GroupDocs.Viewer per Java usando sia un file locale sia un URL HTTP, e **verificare la disponibilità della licenza** per mantenere la tua applicazione conforme. Questa solida base di licenza previene errori a runtime e ti offre la flessibilità di passare tra ambienti di sviluppo, test e produzione con fiducia.

### FAQ

1. **Come imposto un file di licenza locale in GroupDocs.Viewer Java?**  

   Usa `license.setLicense("path/to/license.lic")` con il percorso corretto del file per applicare una licenza locale.

2. **Posso caricare una licenza direttamente da un URL?**  

   Sì, ma assicurati che il tuo codice gestisca l'accesso all'URL, potenzialmente scaricando la licenza a runtime o gestendo problemi di rete.

3. **Cosa devo fare se il percorso della licenza è invalido o mancante?**  

   Implementa controlli per percorsi null o non validi e fornisci indicazioni o prompt di fallback per ottenere una licenza valida.

4. **È possibile passare dinamicamente da un file di licenza a un URL?**  

   Assolutamente, aggiungendo logica condizionale per gestire entrambi gli scenari in base al tuo ambiente o ai parametri di runtime.

5. **Quali sono le best practice per la gestione delle licenze in produzione?**  

   Conserva le licenze in modo sicuro, verifica regolarmente la loro validità e implementa la gestione degli errori per i problemi di licenza per garantire un servizio ininterrotto.

## Domande frequenti

**D: Quanto dura una licenza temporanea?**  
R: Tipicamente 30 giorni, dopodiché puoi richiedere un rinnovo o passare a una licenza permanente.

**D: È necessaria una connessione internet per usare una licenza basata su file?**  
R: No. Un file *.lic* locale funziona completamente offline una volta caricato.

**D: Posso crittografare il file di licenza per maggiore sicurezza?**  
R: Il file di licenza è già firmato da GroupDocs; la crittografia aggiuntiva è opzionale ma non obbligatoria.

**D: Cosa succede se la licenza scade mentre l'app è in esecuzione?**  
R: Le operazioni del visualizzatore inizieranno a lanciare eccezioni di licenza; è consigliato verificare la scadenza all'avvio.

**D: È sicuro memorizzare l'URL della licenza nel controllo di versione?**  
R: Evita di commettere URL sensibili; usa variabili d'ambiente o archivi di configurazione sicuri.

---

**Ultimo aggiornamento:** 2026-03-08  
**Testato con:** GroupDocs.Viewer 25.2 per Java  
**Autore:** GroupDocs