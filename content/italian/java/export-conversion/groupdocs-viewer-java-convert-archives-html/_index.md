---
date: '2026-02-23'
description: Scopri come impostare gli elementi per pagina, incorporare le risorse
  HTML e convertire in batch gli archivi in HTML a pagina singola o multipagina utilizzando
  GroupDocs.Viewer Java.
keywords:
- convert archives to HTML Java
- GroupDocs.Viewer Java tutorial
- render ZIP RAR to HTML
title: 'Imposta elementi per pagina: Converti archivi in HTML con GroupDocs.Viewer
  Java'
type: docs
url: /it/java/export-conversion/groupdocs-viewer-java-convert-archives-html/
weight: 1
---

# Imposta elementi per pagina: Converti archivi in HTML con GroupDocs.Viewer Java

Convertire file di archivio come ZIP o RAR in HTML adatto al web è una necessità frequente quando si desidera condividere o visualizzare documenti direttamente in un browser. In questa guida imparerai **come impostare gli elementi per pagina** durante il rendering degli archivi, come incorporare le risorse HTML per un output autonomo e come convertire in batch gli archivi in modo efficiente con GroupDocs.Viewer Java.

![Converti archivi in HTML con GroupDocs.Viewer per Java](/viewer/export-conversion/convert-archives-to-html-java.png)

## Risposte rapide
- **Cosa controlla “imposta elementi per pagina”?** Determina quanti file o cartelle di un archivio appaiono in ciascuna pagina HTML generata.  
- **Posso incorporare immagini e CSS direttamente nell'HTML?** Sì – usa l'opzione `forEmbeddedResources` per incorporare le risorse HTML.  
- **È possibile la conversione batch?** Assolutamente; puoi iterare su una collezione di archivi e renderizzare ciascuno con le stesse impostazioni.  
- **È necessario Maven per usare GroupDocs.Viewer?** Sì, aggiungi la dipendenza `maven groupdocs viewer` come mostrato di seguito.  
- **Quali formati di output sono supportati?** Sono disponibili sia HTML Java a pagina singola sia HTML Java a più pagine.

## Cos'è “imposta elementi per pagina” in GroupDocs.Viewer?
L'impostazione **imposta elementi per pagina** appartiene alle opzioni di rendering degli archivi. Indica al visualizzatore quanti elementi dell'archivio (file o cartelle) devono essere visualizzati in ogni pagina HTML quando generi un documento HTML a più pagine. Regolare questo valore ti aiuta a bilanciare la dimensione della pagina e la velocità di navigazione, soprattutto per archivi di grandi dimensioni.

## Perché incorporare le risorse HTML?
Incorporare le risorse (immagini, CSS, font) direttamente nel file HTML crea un documento unico e portatile che può essere aperto senza file esterni. Questo è ideale per allegati email, visualizzazione offline o per inserire l'output in altre pagine web.

## Prerequisiti

- **Librerie richieste:** Includi GroupDocs.Viewer versione 25.2 o successiva.  
- **Ambiente:** Java Development Kit (JDK) installato e configurato.  
- **Conoscenze:** Nozioni di base su Java e gestione delle dipendenze Maven.  

## Configurazione Maven di GroupDocs Viewer

Aggiungi il repository GroupDocs e la dipendenza del viewer al tuo `pom.xml`:

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
GroupDocs.Viewer offre un **link per la prova gratuita**, una licenza temporanea o un'opzione di acquisto completo. Scegli quella più adatta al tuo calendario di progetto.

### Inizializzazione di base
Dopo la configurazione Maven, porta il viewer nel tuo codice:

```java
import com.groupdocs.viewer.Viewer;
// Your initialization code here
```

## Come renderizzare gli archivi in HTML a pagina singola

### Passo 1: Definisci la directory di output
```java
Path outputDirectory = Utils.getOutputDirectoryPath("YOUR_OUTPUT_DIRECTORY");
```

### Passo 2: Imposta il nome file per l'output a pagina singola
```java
Path pageFilePathFormat = outputDirectory.resolve("RAR_result.html");
```

### Passo 3: Inizializza il Viewer
```java
try (Viewer viewer = new Viewer(TestFiles.SAMPLE_RAR_WITH_FOLDERS)) {
    // Further configuration steps follow
}
```

### Passo 4: Configura le opzioni di rendering (incorpora risorse HTML)
```java
HtmlViewOptions options = HtmlViewOptions.forEmbeddedResources(pageFilePathFormat);
```

### Passo 5: Renderizza come pagina singola
```java
options.setRenderToSinglePage(true);
viewer.view(options);
```

## Come renderizzare gli archivi in HTML a più pagine e impostare gli elementi per pagina

### Passo 1: Riutilizza la directory di output
```java
Path outputDirectory = Utils.getOutputDirectoryPath("YOUR_OUTPUT_DIRECTORY");
```

### Passo 2: Definisci il formato del nome file per più pagine
```java
Path pageFilePathFormat = outputDirectory.resolve("RAR_result_page_{0}.html");
```

### Passo 3: Inizializza nuovamente il Viewer
```java
try (Viewer viewer = new Viewer(TestFiles.SAMPLE_RAR_WITH_FOLDERS)) {
    // Continue with multi‑page configuration
}
```

### Passo 4: Configura le opzioni a più pagine (incorpora risorse HTML)
```java
HtmlViewOptions options = HtmlViewOptions.forEmbeddedResources(pageFilePathFormat);
```

### Passo 5: Imposta gli elementi per pagina (parola chiave principale in azione)
```java
options.getArchiveOptions().setItemsPerPage(10); // Default is 16
viewer.view(options);
```

## Applicazioni pratiche

- **Sistemi di gestione documentale:** Aggiungi la funzionalità di anteprima degli archivi senza installare visualizzatori aggiuntivi.  
- **Portali web:** Offri agli utenti un modo rapido, senza download, per esplorare documenti raggruppati.  
- **Strumenti di collaborazione:** Consenti ai team di ispezionare gli archivi condivisi direttamente nel browser.

## Considerazioni sulle prestazioni

- **Gestione delle risorse:** Monitora l'utilizzo della memoria; valuta di ottimizzare il garbage collector della JVM per batch di grandi dimensioni.  
- **Conversione batch di archivi:** Itera su un elenco di file di archivio e chiama la stessa logica di rendering per massimizzare il throughput.  
- **Strategia di caching:** Memorizza l'HTML renderizzato in una cache se lo stesso archivio viene richiesto frequentemente.

## Domande frequenti

**D: Cos'è GroupDocs.Viewer Java?**  
R: Una libreria versatile per il rendering di documenti—including archivi—nei formati HTML, PDF e immagini.

**D: Come posso ottenere una prova gratuita di GroupDocs.Viewer?**  
R: Visita il [link per la prova gratuita](https://releases.groupdocs.com/viewer/java/) per scaricare e testare.

**D: Posso convertire altri tipi di documento oltre agli archivi?**  
R: Sì, il viewer supporta PDF, Word, Excel e molti altri formati.

**D: Cosa fare se il rendering è lento?**  
R: Riduci il numero di elementi per pagina, abilita lo streaming o elabora gli archivi in batch più piccoli.

**D: Dove posso trovare aiuto o supporto?**  
R: Rivolgiti al [forum di supporto](https://forum.groupdocs.com/c/viewer/9).

**D: È possibile incorporare CSS e immagini direttamente nell'HTML?**  
R: Assolutamente—usa `HtmlViewOptions.forEmbeddedResources` come mostrato negli esempi.

**D: Come eseguo una conversione batch di una cartella di archivi?**  
R: Itera su ciascun file con un ciclo `for`, applicando la stessa configurazione di `Viewer` e `HtmlViewOptions` per ogni iterazione.

## Risorse

- **Documentazione:** Approfondisci le funzionalità con la [documentazione GroupDocs](https://docs.groupdocs.com/viewer/java/).  
- **Riferimento API:** Esplora l'API completa su [GroupDocs API](https://reference.groupdocs.com/viewer/java/).  
- **Download:** Ottieni gli ultimi binari dalla [pagina di download](https://releases.groupdocs.com/viewer/java/).  
- **Acquisto e licenze:** Consulta le opzioni nella [pagina di acquisto](https://purchase.groupdocs.com/buy).  
- **Supporto e community:** Partecipa alle discussioni sul [forum GroupDocs](https://forum.groupdocs.com/c/viewer/9).

---

**Ultimo aggiornamento:** 2026-02-23  
**Testato con:** GroupDocs.Viewer 25.2  
**Autore:** GroupDocs