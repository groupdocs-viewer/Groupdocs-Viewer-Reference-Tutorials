---
date: '2026-02-21'
description: Scopri come impostare il numero massimo di elementi per cartella durante
  il rendering dei file Outlook con GroupDocs.Viewer per Java, migliorando le prestazioni
  per file PST/OST di grandi dimensioni.
keywords:
- GroupDocs.Viewer Java
- Outlook item rendering
- PST file rendering
title: Come impostare il numero massimo di elementi per cartella nel rendering di
  Outlook con GroupDocs.Viewer per Java
type: docs
url: /it/java/advanced-rendering/groupdocs-viewer-java-limit-outlook-rendering/
weight: 1
---

# Limitare il rendering degli elementi Outlook in Java usando GroupDocs.Viewer

Gestire file di dati Outlook di grandi dimensioni (PST o OST) può rapidamente diventare un collo di bottiglia delle prestazioni. In questa guida scoprirai come **impostare il numero massimo di elementi** per cartella durante il rendering con GroupDocs.Viewer per Java, così elaborerai solo i dati di cui hai realmente bisogno. Applicando la tecnica **limitare gli elementi per cartella**, la tua applicazione rimane reattiva anche con gigabyte di dati email.

![Limita il rendering degli elementi Outlook con GroupDocs.Viewer per Java](/viewer/advanced-rendering/limit-outlook-item-rendering-java.png)

### Cosa imparerai
- Impostare GroupDocs.Viewer per Java  
- Configurare la libreria per **impostare il numero massimo di elementi** per cartella nei file Outlook  
- Scenari reali in cui limitare gli elementi per cartella migliora la velocità e riduce l'uso della memoria  

## Risposte rapide
- **Cosa fa “impostare il numero massimo di elementi per cartella”?** Limita il rendering a un numero definito di elementi email all'interno di ogni cartella Outlook.  
- **Perché limitare gli elementi Outlook?** Per ridurre i tempi di elaborazione e il consumo di memoria per grandi caselle di posta.  
- **Quale versione supporta questa funzionalità?** GroupDocs.Viewer 25.2 e successive.  
- **È necessaria una licenza?** Sì, è necessaria una licenza di prova o acquistata per l'uso in produzione.  
- **Posso modificare il limite a runtime?** Assolutamente – basta modificare il valore `setMaxItemsInFolder` prima del rendering.  

## Come impostare il numero massimo di elementi per cartella nel rendering Outlook
Di seguito trovi una guida passo‑passo che spiega **perché** potresti voler limitare gli elementi Outlook, **cosa** fa l'impostazione e **come** configurarla nel tuo progetto Java.

### Cos'è “impostare il numero massimo di elementi per cartella”?
L'opzione **impostare il numero massimo di elementi** indica al visualizzatore di fermarsi dopo aver renderizzato un conteggio specifico di elementi in ogni cartella. Questo è particolarmente utile quando hai bisogno solo di un'anteprima delle email recenti o quando generi report che non richiedono l'intera casella di posta.

### Perché utilizzare l'approccio di limitare gli elementi per cartella?
- **Prestazioni:** Tempi di rendering più rapidi e minore utilizzo della CPU.  
- **Scalabilità:** Gestire caselle di posta più grandi senza esaurire la memoria JVM.  
- **Flessibilità:** Regolare il limite in base alle preferenze dell'utente o alle capacità del dispositivo.  

## Prerequisiti
Assicurati di avere quanto segue prima di iniziare:

### Librerie e dipendenze richieste
1. **Java Development Kit (JDK)** – Installa JDK 8 o successivo.  
2. **GroupDocs.Viewer for Java** – Aggiungilo come dipendenza nel tuo progetto.

### Requisiti per la configurazione dell'ambiente
- Un IDE adeguato come IntelliJ IDEA, Eclipse o NetBeans.  
- Maven installato se gestisci le dipendenze tramite esso.

### Prerequisiti di conoscenza
- Conoscenza di base della programmazione Java e della gestione dei file.  
- Familiarità con progetti Maven è utile ma non obbligatoria.

## Configurazione di GroupDocs.Viewer per Java
Configura GroupDocs.Viewer nel tuo progetto usando Maven:

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

### Passaggi per l'acquisizione della licenza
- **Prova gratuita**: Scarica una prova gratuita da [GroupDocs](https://releases.groupdocs.com/viewer/java/) per esplorare le funzionalità della libreria.  
- **Licenza temporanea**: Ottieni una licenza temporanea per accesso completo senza limitazioni di valutazione su [GroupDocs Temporary License](https://purchase.groupdocs.com/temporary-license/).  
- **Acquisto**: Per un uso a lungo termine, considera l'acquisto di una licenza dalla [GroupDocs Purchase Page](https://purchase.groupdocs.com/buy).

### Inizializzazione e configurazione di base
Una volta configurato Maven, inizializza GroupDocs.Viewer nella tua applicazione Java impostando l'oggetto viewer. Questo ti consente di caricare e renderizzare i documenti.

## Guida all'implementazione

### Limitare gli elementi renderizzati dai file Outlook
Questa sezione descrive come limitare gli elementi renderizzati dai file di dati Outlook usando GroupDocs.Viewer per Java.

#### Panoramica
Configurando opzioni specifiche, puoi limitare il rendering a un certo numero di elementi per cartella. Questa funzionalità migliora le prestazioni e l'efficienza quando si gestiscono grandi set di dati email.

**Passo 1: Configurare il percorso della directory di output**  
```java
Path outputDirectory = Utils.getOutputDirectoryPath("LimitCountOfItemsToRender");
```  
Questo codice imposta la directory in cui verranno salvati i file HTML renderizzati. Sostituisci `"LimitCountOfItemsToRender"` con il nome del percorso desiderato.

**Passo 2: Definire il formato del percorso file per le pagine HTML**  
```java
Path pageFilePathFormat = outputDirectory.resolve("page_{0}.html");
```  
Crea un formato di denominazione coerente per le pagine HTML generate durante il rendering, garantendo un facile accesso e gestione.

**Passo 3: Configurare HtmlViewOptions con risorse incorporate**  
```java
HtmlViewOptions viewOptions = HtmlViewOptions.forEmbeddedResources(pageFilePathFormat);
```  
Questa opzione specifica come i documenti vengono renderizzati con risorse incorporate, consentendo una migliore integrazione di immagini e stili.

**Passo 4: Impostare le opzioni Outlook per limitare gli elementi per cartella**  
```java
viewOptions.getOutlookOptions().setMaxItemsInFolder(3); // Render only the first 3 items in each folder
```  
Qui, **impostiamo il numero massimo di elementi** a tre. Regola il numero in base alle tue esigenze per lo scenario **limitare gli elementi per cartella**.

**Passo 5: Caricare e renderizzare il documento**  
```java
try (Viewer viewer = new Viewer(TestFiles.SAMPLE_OST)) {
    viewer.view(viewOptions); // Execute rendering with specified options
}
```  
Utilizza la classe `Viewer` per caricare un file OST e renderizzarlo secondo le opzioni di visualizzazione definite. L'istruzione try‑with‑resources garantisce che le risorse vengano chiuse correttamente dopo l'uso.

### Suggerimenti per la risoluzione dei problemi
- Assicurati che tutti i percorsi e le directory esistano prima di eseguire il codice.  
- Verifica che le dipendenze di GroupDocs.Viewer siano risolte correttamente da Maven.  
- Controlla eventuali eccezioni durante il rendering, che potrebbero indicare problemi con i formati dei file o i permessi.

## Applicazioni pratiche
1. **Archiviazione email** – Limitare il rendering degli elementi è ideale per applicazioni che si concentrano sull'archiviazione di email specifiche anziché di interi set di dati.  
2. **Migrazione dati** – Durante la migrazione dei dati tra sistemi, renderizza solo gli elementi necessari per ottimizzare le prestazioni e ridurre i tempi di elaborazione.  
3. **Report personalizzati** – Genera report renderizzando selettivamente il contenuto email richiesto senza caricare intere cartelle.

## Considerazioni sulle prestazioni
### Suggerimenti per ottimizzare le prestazioni
- Limita il conteggio degli elementi per cartella per ridurre l'uso della memoria.  
- Utilizza le risorse incorporate in modo efficiente per evitare chiamate di rete aggiuntive durante il rendering.

### Linee guida sull'uso delle risorse
- Monitora la memoria JVM e regola le impostazioni in base alle dimensioni dei file Outlook elaborati.

### Best practice per la gestione della memoria Java
- Utilizza try‑with‑resources per la gestione automatica delle risorse.  
- Esegui il profiling della tua applicazione per identificare colli di bottiglia legati alla gestione di file di grandi dimensioni.

## Errori comuni e come evitarli
| Sintomo | Probabile causa | Soluzione |
|---------|----------------|----------|
| Nessun file di output generato | Il percorso della directory di output è errato o mancano i permessi | Verifica che `outputDirectory` esista e sia scrivibile |
| Il rendering si interrompe dopo pochi elementi | `setMaxItemsInFolder` impostato troppo basso | Aumenta il limite o rendilo configurabile |
| OutOfMemoryError su PST di grandi dimensioni | Impostazioni di memoria predefinite insufficienti | Aumenta l'heap JVM (`-Xmx`) e mantieni il limite basso |

## Conclusione
In questo tutorial, hai imparato come **impostare il numero massimo di elementi per cartella** nei file di dati Outlook usando GroupDocs.Viewer per Java. Seguendo i passaggi e applicando i suggerimenti sulle prestazioni, puoi creare applicazioni efficienti su misura per le tue esigenze specifiche.

### Prossimi passi
- Esplora funzionalità aggiuntive di GroupDocs.Viewer consultando la [documentazione ufficiale](https://docs.groupdocs.com/viewer/java/).  
- Sperimenta con diverse opzioni di rendering per trovare la configurazione migliore per i requisiti della tua applicazione.

Pronto a provarlo? Inizia a implementare questa soluzione nei tuoi progetti oggi stesso e osserva direttamente un miglioramento dell'efficienza.

## Domande frequenti

**Q: A cosa serve GroupDocs.Viewer Java?**  
A: È una libreria versatile progettata per renderizzare vari formati di documenti, inclusi i file di dati Outlook, in formati HTML o immagine.

**Q: Come posso ottenere una prova gratuita di GroupDocs.Viewer?**  
A: Visita [GroupDocs Free Trial](https://releases.groupdocs.com/viewer/java/) per accedere e scaricare.

**Q: Posso limitare il rendering degli elementi anche nei file PST?**  
A: Sì, la stessa configurazione si applica sia ai formati OST che PST.

**Q: Cosa devo fare se la mia applicazione è lenta durante il rendering?**  
A: Rivedi i limiti degli elementi e le impostazioni delle risorse; considera l'ottimizzazione delle pratiche di gestione della memoria.

**Q: Dove posso trovare supporto per i problemi di GroupDocs.Viewer?**  
A: Per assistenza, consulta il [GroupDocs Support Forum](https://forum.groupdocs.com/c/viewer/9).

## Risorse aggiuntive
- [Documentazione](https://docs.groupdocs.com/viewer/java/)
- [Riferimento API](https://reference.groupdocs.com/viewer/java/)
- [Download GroupDocs.Viewer per Java](https://releases.groupdocs.com/viewer/java/)
- [Acquista licenza](https://purchase.groupdocs.com/buy)
- [Versione di prova gratuita](https://releases.groupdocs.com/viewer/java/)
- [Applicazione licenza temporanea](https://purchase.groupdocs.com/temporary-license/)
- [Forum di supporto](https://forum.groupdocs.com/c/viewer/9)

---

**Ultimo aggiornamento:** 2026-02-21  
**Testato con:** GroupDocs.Viewer 25.2 per Java  
**Autore:** GroupDocs