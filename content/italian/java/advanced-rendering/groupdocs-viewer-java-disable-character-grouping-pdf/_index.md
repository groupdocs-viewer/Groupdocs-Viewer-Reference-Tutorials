---
date: '2026-03-22'
description: Scopri come generare HTML da PDF e disabilitare il raggruppamento dei
  caratteri usando GroupDocs Viewer per Java per una rappresentazione testuale precisa.
keywords:
- disable character grouping PDFs
- GroupDocs Viewer Java configuration
- precise text representation in PDFs
title: Genera HTML da PDF e disabilita il raggruppamento – GroupDocs Java
type: docs
url: /it/java/advanced-rendering/groupdocs-viewer-java-disable-character-grouping-pdf/
weight: 1
---

# Genera HTML da PDF e Disabilita il Raggruppamento con GroupDocs Viewer per Java

In molti progetti è necessario **generare HTML da PDF** mantenendo ogni glifo esattamente al suo posto. Questo è particolarmente vero per script complessi, lingue antiche o documenti legali dove un singolo carattere fuori posto può cambiare il significato. In questo tutorial vi guideremo attraverso l'intero processo di rendering dei PDF in HTML con GroupDocs Viewer per Java e vi mostreremo **come disabilitare il raggruppamento** in modo che ogni carattere sia trattato come un elemento indipendente.

![Precise Rendering Techniques with GroupDocs.Viewer for Java](/viewer/advanced-rendering/precise-rendering-techniques-java.png)

## Risposte Rapide
- **Cosa fa “disable grouping”?** Costringe il renderer a trattare ogni carattere come un elemento indipendente, preservando il layout esatto.  
- **Quale opzione API controlla questo?** `viewOptions.getPdfOptions().setDisableCharsGrouping(true)`.  
- **Ho bisogno di una licenza?** Una versione di prova funziona per i test, ma è necessaria una licenza completa per la produzione.  
- **Posso generare HTML da PDF contemporaneamente?** Sì—usa `HtmlViewOptions` per creare l'output HTML disabilitando il raggruppamento.  
- **Questa funzionalità è limitata ai PDF?** È principalmente per PDF, ma il viewer supporta molti altri formati.

## Introduzione

Quando si lavora con documenti PDF, la precisione nel rendering è fondamentale—specialmente quando si trattano strutture di testo complesse come geroglifici o lingue che richiedono una rappresentazione precisa dei caratteri. La funzionalità "Character Grouping" spesso causa problemi raggruppando i caratteri in modo errato, portando a una cattiva interpretazione del contenuto del documento. Questo può essere particolarmente problematico per gli utenti che necessitano di una replica esatta del layout testuale dei loro documenti.

### Prerequisiti

- **Librerie e Dipendenze**: Avrai bisogno di GroupDocs.Viewer per Java versione 25.2 o successiva.  
- **Configurazione dell'Ambiente**: Assicurati di avere installato un Java Development Kit (JDK) e che il tuo IDE sia configurato per lavorare con progetti Maven.  
- **Prerequisiti di Conoscenza**: Comprensione di base della programmazione Java, specialmente nella gestione dei percorsi dei file e nell'uso di librerie esterne.

## Come generare HTML da PDF con GroupDocs Viewer

Generare HTML da PDF è un processo in due fasi: configurare il viewer, poi renderizzare il documento. La chiave è disattivare il raggruppamento dei caratteri prima del rendering in modo che l'output HTML rispecchi il layout originale del PDF carattere per carattere.

### Configurazione di GroupDocs.Viewer per Java

#### Installazione via Maven

Per prima cosa, integra la libreria necessaria nel tuo progetto. Aggiungi la seguente configurazione nel tuo `pom.xml`:

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

#### Acquisizione della Licenza

Per utilizzare appieno GroupDocs.Viewer, considera l'acquisizione di una licenza:
- **Free Trial**: Inizia con la versione di prova gratuita per testare le funzionalità.  
- **Temporary License**: Richiedi una licenza temporanea se hai bisogno di più tempo.  
- **Purchase**: Per progetti a lungo termine, è consigliabile acquistare una licenza.

#### Inizializzazione e Configurazione di Base

Di seguito è riportato uno snippet pronto all'uso che mostra l'intero flusso di lavoro—dalla definizione della cartella di output al rendering del PDF in HTML disabilitando il raggruppamento dei caratteri:

```java
import com.groupdocs.viewer.Viewer;
import com.groupdocs.viewer.options.HtmlViewOptions;
import java.nio.file.Path;

// Initialize the GroupDocs Viewer
Path outputDirectory = Utils.getOutputDirectoryPath("DisableCharactersGrouping");
Path pageFilePathFormat = outputDirectory.resolve("page_{0}.html");

HtmlViewOptions viewOptions = HtmlViewOptions.forEmbeddedResources(pageFilePathFormat);
viewOptions.getPdfOptions().setDisableCharsGrouping(true);

try (Viewer viewer = new Viewer("YOUR_DOCUMENT_DIRECTORY/HIEROGLYPHS_PDF")) {
    viewer.view(viewOptions);
}
```

### Guida all'Implementazione

#### Funzionalità: Disabilita il Raggruppamento dei Caratteri

Di seguito analizziamo ogni riga dell'esempio in modo che tu possa capire **perché** lo facciamo e **come** contribuisce a generare HTML da PDF senza l'unione indesiderata dei caratteri.

##### Passo 1: Definisci la Directory di Output  

```java
Path outputDirectory = Utils.getOutputDirectoryPath("DisableCharactersGrouping");
```

**Perché?** Questo garantisce che i file HTML renderizzati siano salvati in una cartella dedicata, facilitandone la localizzazione e la gestione in seguito.

##### Passo 2: Configura il Formato del Percorso del File  

```java
Path pageFilePathFormat = outputDirectory.resolve("page_{0}.html");
```

**Perché?** Usare un segnaposto (`{0}`) permette al viewer di creare un file HTML separato per ogni pagina PDF, mantenendo l'output organizzato.

##### Passo 3: Inizializza le Opzioni di Visualizzazione HTML  

```java
HtmlViewOptions viewOptions = HtmlViewOptions.forEmbeddedResources(pageFilePathFormat);
```

**Perché?** Le risorse incorporate raggruppano immagini, font e CSS direttamente con ogni pagina HTML, il che è ideale per visualizzatori basati sul web o piattaforme e‑learning.

##### Passo 4: Disabilita il Raggruppamento dei Caratteri  

```java
viewOptions.getPdfOptions().setDisableCharsGrouping(true);
```

**Perché?** Questa è la riga cruciale che indica al motore di rendering di **non** unire i caratteri adiacenti, garantendo che l'HTML generato rifletta la posizione esatta dei glifi dal PDF di origine.

##### Passo 5: Renderizza il Documento  

```java
try (Viewer viewer = new Viewer("YOUR_DOCUMENT_DIRECTORY/HIEROGLYPHS_PDF")) {
    viewer.view(viewOptions);
}
```

**Perché?** Avvolgere il `Viewer` in un blocco try‑with‑resources garantisce che tutte le risorse native vengano rilasciate automaticamente, evitando perdite di memoria in applicazioni a lungo termine.

### Generare HTML Java da PDF senza Raggruppamento

La classe `HtmlViewOptions` ti consente di produrre **generare html from pdf** mantenendo ogni carattere separato. Questo è particolarmente utile quando è necessario incorporare le pagine renderizzate in un portale web o in una piattaforma e‑learning dove la posizione esatta dei glifi è importante.

### Problemi Comuni e Soluzioni

- **FileNotFoundException** – Verifica nuovamente il percorso che passi a `new Viewer(...)`. Usa percorsi assoluti o `Path.of(...)` per chiarezza.  
- **Write Permissions** – Assicurati che la directory di output sia scrivibile dal processo Java; su Linux potresti dover regolare i permessi della cartella (`chmod 775`).  
- **Version Mismatch** – L'opzione `setDisableCharsGrouping` è disponibile a partire dalla versione 25.2. Verifica che il tuo `pom.xml` rifletta la versione corretta.

### Applicazioni Pratiche

1. **Preservazione della Lingua** – Ideale per il rendering di documenti in cinese, giapponese, arabo o script antichi dove la spaziatura dei caratteri trasmette significato.  
2. **Documenti Legali e Finanziari** – Garantisce una replica esatta del testo per documentazione soggetta a rigorosi requisiti di conformità.  
3. **Risorse Educative** – Perfetto per libri di testo che includono diagrammi complessi, annotazioni o contenuti multilingue.

### Considerazioni sulle Prestazioni

- **Ottimizza l'Uso delle Risorse** – I PDF di grandi dimensioni possono consumare molta memoria. Considera di elaborare le pagine in batch e di rilasciare prontamente le istanze di `Viewer`.  
- **Gestione della Memoria Java** – Regola l'heap della JVM (`-Xmx2g` o superiore) se prevedi di elaborare PDF con centinaia di pagine.  
- **Rendering Parallelo** – Per conversioni di massa, avvia thread separati, ciascuno con la propria istanza di `Viewer`, per sfruttare le CPU multi‑core.

## Domande Frequenti

**Q:** *Perché dovrei disabilitare il raggruppamento dei caratteri?*  
**A:** Disabilitare il raggruppamento impedisce al renderer di unire i caratteri che appartengono a glifi distinti, il che è essenziale per gli script in cui spaziatura e ordine trasmettono significato.

**Q:** *L'impostazione `setDisableCharsGrouping` è applicabile solo all'output HTML?*  
**A:** No, influisce sul motore di rendering PDF sottostante, quindi qualsiasi formato di output (HTML, PNG, JPEG, ecc.) rifletterà la modifica.

**Q:** *Posso combinare questa impostazione con font personalizzati?*  
**A:** Sì—carica i tuoi font personalizzati prima di inizializzare `Viewer`, e la regola di raggruppamento sarà comunque applicata.

**Q:** *Disabilitare il raggruppamento influisce sulle prestazioni?*  
**A:** Leggermente, poiché il motore elabora ogni carattere singolarmente, ma l'impatto è minimo per la maggior parte dei documenti.

**Q:** *Esiste un modo per attivare/disattivare il raggruppamento per pagina?*  
**A:** Attualmente l'opzione è globale per istanza di `PdfOptions`; dovresti utilizzare istanze separate di `Viewer` per pagine diverse se necessiti di comportamenti misti.

## Risorse

- [GroupDocs Documentation](https://docs.groupdocs.com/viewer/java/)
- [API Reference](https://reference.groupdocs.com/viewer/java/)
- [Download GroupDocs Viewer](https://releases.groupdocs.com/viewer/java/)
- [Purchase License](https://purchase.groupdocs.com/buy)
- [Free Trial Version](https://releases.groupdocs.com/viewer/java/)
- [Temporary License Application](https://purchase.groupdocs.com/temporary-license/)
- [GroupDocs Support Forum](https://forum.groupdocs.com/c/viewer/9)

---

**Ultimo Aggiornamento:** 2026-03-22  
**Testato Con:** GroupDocs.Viewer 25.2 for Java  
**Autore:** GroupDocs