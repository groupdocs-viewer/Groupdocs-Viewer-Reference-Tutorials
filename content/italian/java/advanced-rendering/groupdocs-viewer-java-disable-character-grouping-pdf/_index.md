---
date: '2025-12-21'
description: Scopri come disabilitare il raggruppamento nei PDF con GroupDocs.Viewer
  per Java, utilizzando java html dalle opzioni di rendering PDF per garantire una
  rappresentazione precisa del testo.
keywords:
- disable character grouping PDFs
- GroupDocs Viewer Java configuration
- precise text representation in PDFs
title: Come disabilitare il raggruppamento nei PDF con GroupDocs.Viewer per Java
type: docs
url: /it/java/advanced-rendering/groupdocs-viewer-java-disable-character-grouping-pdf/
weight: 1
---

# Come Disabilitare il Raggruppamento nei PDF con GroupDocs.Viewer per Java

Quando hai bisogno di **come disabilitare il raggruppamento** durante il rendering dei PDF, soprattutto per script complessi o lingue antiche, il posizionamento preciso dei caratteri diventa essenziale. La funzionalità predefinita *Character Grouping* può unire i caratteri in modo errato, causando una cattiva interpretazione del contenuto. In questa guida ti mostreremo passo‑passo come disabilitare il raggruppamento usando GroupDocs.Viewer per Java, così ogni glifo rimane esattamente al suo posto.

![Precise Rendering Techniques with GroupDocs.Viewer for Java](/viewer/advanced-rendering/precise-rendering-techniques-java.png)

## Risposte Rapide
- **Cosa fa “disable grouping”?** Forza il renderer a trattare ogni carattere come un elemento indipendente, preservando il layout esatto.  
- **Quale opzione API controlla questo?** `viewOptions.getPdfOptions().setDisableCharsGrouping(true)`.  
- **Ho bisogno di una licenza?** Una versione di prova funziona per i test, ma è necessaria una licenza completa per la produzione.  
- **Posso generare Java HTML dal PDF contemporaneamente?** Sì—usa `HtmlViewOptions` per creare l'output HTML disabilitando il raggruppamento.  
- **Questa funzionalità è limitata ai PDF?** È principalmente per i PDF, ma il viewer supporta molti altri formati.

## Introduzione

Quando si lavora con documenti PDF, la precisione nel rendering è cruciale—soprattutto quando si trattano strutture testuali complesse come geroglifici o lingue che richiedono una rappresentazione precisa dei caratteri. La funzionalità "Character Grouping" spesso causa problemi raggruppando i caratteri in modo errato, portando a una cattiva interpretazione del contenuto del documento. Questo può essere particolarmente problematico per gli utenti che necessitano di una replica esatta del layout testuale dei loro documenti.

### Prerequisiti

Prima di immergerti nell'implementazione del codice, assicurati di soddisfare i seguenti requisiti:
- **Librerie e Dipendenze**: Avrai bisogno di GroupDocs.Viewer per Java versione 25.2 o successiva.
- **Configurazione dell'Ambiente**: Assicurati di avere installato un Java Development Kit (JDK) e che il tuo IDE sia configurato per lavorare con progetti Maven.
- **Prerequisiti di Conoscenza**: Comprensione di base della programmazione Java, in particolare la gestione dei percorsi dei file e l'uso di librerie esterne.

## Come Disabilitare il Raggruppamento nel Rendering PDF

### Configurazione di GroupDocs.Viewer per Java

#### Installazione via Maven

Prima, integra la libreria necessaria nel tuo progetto. Aggiungi la seguente configurazione nel tuo `pom.xml`:

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
- **Prova Gratuita**: Inizia con la prova gratuita per testare le funzionalità.  
- **Licenza Temporanea**: Richiedi una licenza temporanea se hai bisogno di più tempo.  
- **Acquisto**: Per progetti a lungo termine, è consigliabile acquistare una licenza.

#### Inizializzazione e Configurazione di Base

Inizia impostando l'ambiente del tuo progetto:

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

##### Passo 1: Definisci la Directory di Output

```java
Path outputDirectory = Utils.getOutputDirectoryPath("DisableCharactersGrouping");
```

**Perché?** Questo garantisce che il tuo output sia organizzato e facilmente accessibile.

##### Passo 2: Configura il Formato del Percorso del File

```java
Path pageFilePathFormat = outputDirectory.resolve("page_{0}.html");
```

**Perché?** Aiuta a organizzare sistematicamente le pagine del documento PDF.

##### Passo 3: Inizializza le Opzioni di Visualizzazione HTML

```java
HtmlViewOptions viewOptions = HtmlViewOptions.forEmbeddedResources(pageFilePathFormat);
```

**Perché?** Le risorse incorporate assicurano che tutti gli asset necessari siano inclusi nel file HTML di ogni pagina.

##### Passo 4: Disabilita il Raggruppamento dei Caratteri

```java
viewOptions.getPdfOptions().setDisableCharsGrouping(true);
```

**Perché?** Questo garantisce che i caratteri siano renderizzati individualmente, preservando il layout e il significato previsto.

##### Passo 5: Renderizza il Documento

```java
try (Viewer viewer = new Viewer("YOUR_DOCUMENT_DIRECTORY/HIEROGLYPHS_PDF")) {
    viewer.view(viewOptions);
}
```

**Perché?** Questo garantisce che tutte le risorse siano chiuse correttamente, evitando perdite di memoria.

### Generare Java HTML da PDF senza Raggruppamento

La classe `HtmlViewOptions` ti consente di produrre **java html from pdf** mantenendo ogni carattere separato. Questo è particolarmente utile quando devi incorporare le pagine renderizzate in un portale web o in una piattaforma e‑learning dove è importante il posizionamento esatto dei glifi.

### Suggerimenti per la Risoluzione dei Problemi

- Assicurati che il percorso del documento sia corretto per evitare `FileNotFoundException`.  
- Verifica che la directory di output abbia i permessi di scrittura.  
- Controlla nuovamente di utilizzare una versione compatibile di GroupDocs.Viewer per Java.

## Applicazioni Pratiche

1. **Preservazione Linguistica**: Ideale per il rendering di documenti in lingue come cinese, giapponese o script antichi dove la precisione dei caratteri è fondamentale.  
2. **Documenti Legali e Finanziari**: Garantisce l'accuratezza nei documenti che richiedono una rappresentazione testuale precisa per la conformità.  
3. **Risorse Educative**: Perfetto per libri di testo e articoli accademici che includono diagrammi complessi o annotazioni.

## Considerazioni sulle Prestazioni

- **Ottimizza l'Uso delle Risorse**: Assicurati che il tuo server abbia risorse adeguate per gestire file PDF di grandi dimensioni.  
- **Gestione della Memoria Java**: Usa strutture dati efficienti e pratiche di garbage‑collection per gestire la memoria in modo efficace.  
- **Elaborazione in Batch**: Quando renderizzi più documenti, elabora in batch per migliorare il throughput.

## Conclusione

Ora hai padroneggiato **come disabilitare il raggruppamento** durante il rendering dei PDF con GroupDocs.Viewer per Java. Questa capacità è fondamentale per le applicazioni che richiedono una rappresentazione testuale precisa. Per approfondire, prova a integrare questa funzionalità con altri sistemi di gestione documentale o sperimenta opzioni di rendering aggiuntive.

I prossimi passi includono l'esplorazione di funzionalità più avanzate di GroupDocs.Viewer e l'ottimizzazione delle prestazioni per distribuzioni su larga scala.

## Domande Frequenti

**Q:** *Perché dovrei disabilitare il raggruppamento dei caratteri?*  
**A:** Disabilitare il raggruppamento impedisce al renderer di unire caratteri che appartengono a glifi distinti, il che è essenziale per gli script in cui spaziatura e ordine trasmettono significato.

**Q:** *L'impostazione `setDisableCharsGrouping` è applicabile solo all'output HTML?*  
**A:** No, influisce sul motore di rendering PDF sottostante, quindi qualsiasi formato di output (HTML, PNG, ecc.) rifletterà la modifica.

**Q:** *Posso combinare questa impostazione con font personalizzati?*  
**A:** Sì—basta caricare i tuoi font personalizzati prima di inizializzare `Viewer`, e la regola di raggruppamento sarà comunque applicata.

**Q:** *Disabilitare il raggruppamento influisce sulle prestazioni?*  
**A:** Leggermente, poiché il motore elabora ogni carattere individualmente, ma l'impatto è minimo per la maggior parte dei documenti.

**Q:** *Esiste un modo per attivare/disattivare il raggruppamento per pagina?*  
**A:** Attualmente l'opzione è globale per l'istanza `PdfOptions`; dovresti creare istanze separate di `Viewer` per pagine diverse.

## Risorse

- [Documentazione GroupDocs](https://docs.groupdocs.com/viewer/java/)
- [Riferimento API](https://reference.groupdocs.com/viewer/java/)
- [Download GroupDocs Viewer](https://releases.groupdocs.com/viewer/java/)
- [Acquista Licenza](https://purchase.groupdocs.com/buy)
- [Versione di Prova Gratuita](https://releases.groupdocs.com/viewer/java/)
- [Applicazione Licenza Temporanea](https://purchase.groupdocs.com/temporary-license/)
- [Forum di Supporto GroupDocs](https://forum.groupdocs.com/c/viewer/9)

---

**Ultimo Aggiornamento:** 2025-12-21  
**Testato Con:** GroupDocs.Viewer 25.2 per Java  
**Autore:** GroupDocs