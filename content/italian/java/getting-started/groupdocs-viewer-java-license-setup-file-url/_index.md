---
date: '2026-03-08'
description: Scopri come impostare la licenza per GroupDocs.Viewer Java utilizzando
  un file locale o un URL. Questa guida passo passo ti mostra come impostare la licenza
  in modo rapido e affidabile.
keywords:
- GroupDocs.Viewer Java license
- setting license from file
- setting license via URL
title: Come impostare la licenza per GroupDocs.Viewer Java (file o URL)
type: docs
url: /it/java/getting-started/groupdocs-viewer-java-license-setup-file-url/
weight: 1
---

 25.2  
**Author:** GroupDocs

Translate:

"**Ultimo aggiornamento:** 2026-03-08  
**Testato con:** GroupDocs.Viewer for Java 25.2  
**Autore:** GroupDocs"

Now ensure all markdown preserved.

Check for any other placeholders: none.

Now produce final content.# Come impostare la licenza per GroupDocs.Viewer Java (File o URL)

Sblocca tutto il potenziale di GroupDocs.Viewer per le tue applicazioni Java imparando **come impostare la licenza** da un file locale o da un URL online. Questa guida ti accompagna attraverso entrambi gli approcci, spiega perché ogni metodo è importante e ti offre consigli pratici per mantenere le funzionalità di visualizzazione dei documenti senza interruzioni.

## Risposte rapide
- **Qual è il modo principale per impostare una licenza GroupDocs.Viewer in Java?** Usa la classe `License` e chiama `setLicense` con un `InputStream` da un file o URL.  
- **Posso cambiare la licenza senza ridistribuire l'app?** Sì—memorizza la licenza su un server web e punta l'URL al nuovo file.  
- **È necessaria una connessione internet per usare una licenza da file locale?** No, il metodo basato su file funziona completamente offline.  
- **Quale versione di Java è richiesta?** Si consiglia Java 8 o superiore.  
- **È necessaria una configurazione Maven aggiuntiva?** Solo la dipendenza GroupDocs.Viewer e le voci del repository mostrate di seguito.

## Cos'è “impostare la licenza” nel contesto di GroupDocs.Viewer?
Impostare una licenza indica al motore GroupDocs.Viewer che disponi di un diritto commerciale valido. Senza di essa, la libreria funziona in modalità di valutazione, limitando le funzionalità e aggiungendo filigrane. Configurando correttamente la licenza, sblocchi tutte le capacità di rendering per PDF, documenti Office, immagini e altro.

## Perché utilizzare un file locale anziché un URL?
- **File locale:** Ideale per ambienti senza accesso internet affidabile o quando desideri l'avvio più veloce possibile.  
- **URL:** Perfetto per la gestione centralizzata delle licenze—aggiorna la licenza in un unico punto e tutte le istanze in esecuzione rilevano automaticamente la modifica.

## Introduzione

La licenza è essenziale quando si utilizza GroupDocs.Viewer in Java per sbloccare l'intera gamma di funzionalità oltre la modalità di valutazione. Che il file di licenza sia archiviato localmente o recuperato da un URL, gestirlo efficacemente garantisce funzionalità senza interruzioni.

![Guida al file locale o URL con GroupDocs.Viewer per Java](/viewer/getting-started/local-file-or-url-guide.png)

**Cosa imparerai:**
- Come configurare una licenza GroupDocs Viewer Java utilizzando un file locale  
- Come configurare una licenza tramite un URL per risorse online  
- Comprendere i prerequisiti e la configurazione dell'ambiente  

Iniziamo con **impostare la licenza** nelle tue applicazioni Java.

### Prerequisiti

- **Librerie e dipendenze:** Includi la libreria GroupDocs.Viewer per Java. Usa Maven per una gestione facile delle dipendenze.  
- **Configurazione dell'ambiente:** Java 8 o superiore (JDK 11+ è consigliato per progetti più recenti).  
- **Prerequisiti di conoscenza:** Programmazione Java di base, gestione dei file e utilizzo degli URL.

### Configurazione di GroupDocs.Viewer per Java

Per integrare GroupDocs.Viewer nel tuo progetto Java, segui questi passaggi di configurazione:

**Configurazione Maven:**

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

**Acquisizione della licenza:**

Per utilizzare GroupDocs.Viewer, ottieni una licenza dal loro sito ufficiale. Le opzioni includono:
- **Prova gratuita:** Inizia con una prova per esplorare le funzionalità.  
- **Licenza temporanea:** Utile per valutazioni a breve termine senza limitazioni.  
- **Acquisto:** Per utilizzo a lungo termine e supporto.

Una volta ottenuto il file di licenza, inizializziamolo nella tua applicazione Java.

## Come impostare la licenza da un file locale

Questo metodo prevede la lettura di un file di licenza memorizzato localmente sul tuo sistema. È semplice se hai la licenza disponibile offline.

**Panoramica:** Impostare una licenza da un file garantisce che la tua applicazione possa avviarsi con funzionalità complete senza necessità di una connessione internet dopo la configurazione iniziale.

1. **Individua il tuo file di licenza:**  
   Sostituisci `YOUR_DOCUMENT_DIRECTORY/your-license-file.lic` con il percorso effettivo del tuo file di licenza locale.

2. **Implementa il codice:**  

```java
import com.groupdocs.viewer.License;
import java.io.File;
import java.nio.file.Files;
import java.nio.file.Paths;

public class SetLicenseFromFile {
    public static void run() {
        final String licensePath = "YOUR_DOCUMENT_DIRECTORY/your-license-file.lic";
        if (new File(licensePath).isFile()) {
            try (
                java.io.InputStream stream = Files.newInputStream(Paths.get(licensePath))
            ) {
                License license = new License();
                license.setLicense(stream);
                System.out.println("License set successfully from file.");
            } catch (IOException ex) {
                ex.printStackTrace(); // Properly handle exceptions in production
            }
        } else {
            System.err.println("License file not found at the specified path.");
        }
    }
}
```

**Spiegazione:**  
- La classe `License` è importata per gestire le impostazioni della licenza.  
- Java NIO fornisce I/O di file efficiente e non bloccante.  
- Una gestione robusta delle eccezioni previene crash se il file è mancante o illeggibile.

## Come impostare la licenza da un URL

Se il tuo file di licenza si trova online, impostarlo tramite un URL può semplificare il processo di configurazione.

**Panoramica:** Recuperare una licenza da una fonte online è ideale quando desideri una gestione centralizzata o hai bisogno di aggiornamenti frequenti senza ridistribuire le applicazioni.

1. **Prepara l'URL della tua licenza:**  
   Assicurati che `YOUR_DOCUMENT_DIRECTORY/your-license-url` punti a una risorsa HTTP(s) valida contenente il tuo file di licenza.

2. **Implementa il codice:**  

```java
import com.groupdocs.viewer.License;
import java.io.IOException;
import java.net.URL;

public class SetLicenseFromUrl {
    public static void run() {
        final String licenseUrl = "YOUR_DOCUMENT_DIRECTORY/your-license-url";
        if (licenseUrl.startsWith("http")) {
            try (
                java.io.InputStream stream = new URL(licenseUrl).openStream()
            ) {
                License license = new License();
                license.setLicense(stream);
                System.out.println("License set successfully from URL.");
            } catch (IOException ex) {
                ex.printStackTrace(); // Properly handle exceptions in production
            }
        } else {
            System.err.println("The provided path is not a valid URL.");
        }
    }
}
```

**Spiegazione:**  
- La classe `URL` recupera il file di licenza remoto.  
- La validazione dell'URL previene l'uso accidentale di un percorso malformato.  
- Le eccezioni legate alla rete vengono catturate in modo che l'app possa reagire in modo appropriato (ad esempio, ritentare o utilizzare una soluzione di fallback).

## Applicazioni pratiche

GroupDocs.Viewer può essere integrato in varie applicazioni reali:

1. **Sistemi di gestione documentale:** Migliora le capacità di visualizzazione dei documenti con accesso completo alle funzionalità.  
2. **Applicazioni web:** Offri agli utenti un'interazione fluida con i documenti senza dipendenze lato server.  
3. **App mobili:** Usalo come servizio backend per visualizzare documenti su dispositivi mobili.  
4. **Piattaforme di gestione dei contenuti:** Semplifica la consegna e la visualizzazione dei contenuti per le biblioteche digitali.

## Considerazioni sulle prestazioni

Ottimizzare la tua applicazione comporta:

- **Uso efficiente delle risorse:** Chiudi gli stream prontamente per liberare handle di file e socket di rete.  
- **Operazioni asincrone:** Quando recuperi una licenza da un URL, considera di eseguire il download in un thread in background o usare CompletableFuture per evitare di bloccare il thread principale.  
- **Gestione della memoria Java:** Monitora l'uso dell'heap, specialmente durante il rendering di documenti di grandi dimensioni, e regola le opzioni JVM (`-Xmx`, `-XX:MaxMetaspaceSize`) secondo necessità.

## Problemi comuni e soluzioni

| Problema | Causa | Soluzione |
|----------|-------|-----------|
| **File di licenza non trovato** | Percorso errato o permessi di file mancanti | Verifica il percorso assoluto e assicurati che l'utente del processo possa leggere il file. |
| **URL non valido** | Errore di battitura o schema `http/https` mancante | Controlla nuovamente la stringa URL; usa la validazione `startsWith("http")` come mostrato. |
| **Timeout di rete** | Server lento o non raggiungibile | Implementa una logica di retry con back‑off esponenziale o fornisci una copia locale di fallback. |
| **La filigrana di valutazione appare ancora** | Licenza non caricata prima di creare un'istanza `Viewer` | Chiama il codice di licenza **prima** di istanziare qualsiasi oggetto Viewer. |

## Domande frequenti

**Q:** Cosa fare se il mio file di licenza non viene trovato localmente?  
**A:** Assicurati che il percorso sia corretto, il file esista e l'applicazione abbia i permessi di lettura. Puoi anche passare al metodo URL come soluzione rapida.

**Q:** Posso aggiornare la mia licenza senza ridistribuire?  
**A:** Sì—memorizza la licenza su un server web e punta l'URL a quella posizione. L'aggiornamento del file sul server si riflette immediatamente in tutte le istanze in esecuzione dopo che ricaricano la licenza.

**Q:** Come gestire i fallimenti di rete quando si imposta una licenza tramite URL?  
**A:** Avvolgi il download in un blocco try‑catch, aggiungi una logica di retry e, opzionalmente, utilizza una copia locale nella cache come fallback.

**Q:** Quali sono i vantaggi dell'utilizzo di GroupDocs.Viewer in Java?  
**A:** Offre rendering di documenti robusto e ad alte prestazioni per oltre 100 formati, integrazione senza soluzione di continuità e nessuna dipendenza esterna.

**Q:** Dove posso ottenere supporto se incontro problemi?  
**A:** Visita il [GroupDocs Support Forum](https://forum.groupdocs.com/c/viewer/9) per assistenza e approfondimenti della community.

## Conclusione

Seguendo questo tutorial ora sai **come impostare la licenza** per GroupDocs.Viewer in Java, sia che tu preferisca un file locale sia un URL remoto. Una licenza corretta sblocca tutte le funzionalità, migliora le prestazioni e rimuove le limitazioni della valutazione.

**Passaggi successivi:**  
- Sperimenta con diversi tipi di documenti (PDF, DOCX, PPTX) per vedere tutte le capacità di rendering.  
- Esplora opzioni avanzate di Viewer come rendering pagina per pagina, filigrane e font personalizzati.  

Implementa queste soluzioni oggi e offri ai tuoi utenti un'esperienza di visualizzazione dei documenti impeccabile!

---

**Ultimo aggiornamento:** 2026-03-08  
**Testato con:** GroupDocs.Viewer for Java 25.2  
**Autore:** GroupDocs