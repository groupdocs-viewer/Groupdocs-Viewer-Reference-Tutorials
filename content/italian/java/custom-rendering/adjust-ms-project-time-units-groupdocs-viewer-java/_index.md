---
date: '2026-01-28'
description: Scopri come regolare le unità di tempo di MS Project con GroupDocs Viewer
  Java. Ottimizza il processo di rendering dei documenti del tuo progetto in modo
  efficiente e preciso.
keywords:
- GroupDocs.Viewer Java
- MS Project time units adjustment
- render MS Project files
title: 'Come regolare le unità di tempo di MS Project usando GroupDocs Viewer Java - una guida passo passo'
type: docs
url: /it/java/custom-rendering/adjust-ms-project-time-units-groupdocs-viewer-java/
weight: 1
---

# Come Regolare le Unità di Tempo di MS Project con groupdocs viewer java: Guida Passo‑Passo

## Introduzione
Sei stanco di regolare manualmente le unità di tempo nei tuoi documenti MS Project prima di renderizzarli in formato HTML? Il processo può essere noioso e soggetto a errori, soprattutto quando si gestiscono progetti di grandi dimensioni. Con **groupdocs viewer java**, puoi facilmente regolare le impostazioni dell'unità di tempo in modo programmatico, garantendo precisione ed efficienza.

![Regola le Unità di Tempo di MS Project con GroupDocs.Viewer per Java](/viewer/custom-rendering/adjust-ms-project-time-units-java.png)

In questa guida, dimostreremo come cambiare le unità di tempo dei documenti MS Project in giorni usando groupdocs viewer java. Alla fine di questo tutorial, sarai in grado di:
- Configurare l'ambiente per il rendering dei file MS Project con GroupDocs.Viewer.
- Regolare le unità di tempo della gestione del progetto direttamente nel tuo codice.
- Integrare queste regolazioni senza problemi nella tua applicazione.

Prima di iniziare, assicuriamoci di avere tutto pronto per cominciare!

## Risposte Rapide
- **Quale libreria gestisce il rendering di MS Project?** groupdocs viewer java
- **Quale unità di tempo può essere impostata?** Days (via `TimeUnit.DAYS`)
- **Devo avere una licenza?** È disponibile una versione di prova o una licenza temporanea; è necessaria una licenza permanente per la produzione.
- **Quale IDE è il migliore?** Qualsiasi IDE Java (IntelliJ IDEA, Eclipse) che supporti Maven.
- **È necessario Maven?** Sì, Maven semplifica la gestione delle dipendenze per groupdocs viewer java.

## Cos'è groupdocs viewer java?
groupdocs viewer java è un SDK Java che consente agli sviluppatori di renderizzare una vasta gamma di formati di documento — inclusi i file MS Project — in formati web‑friendly come HTML o immagini. Astrae le complessità dell'analisi dei file, permettendoti di concentrarti sulla logica di business.

## Perché regolare le unità di tempo con groupdocs viewer java?
Cambiare l'unità di tempo dal valore predefinito (spesso minuti) a giorni rende l'output renderizzato più leggibile per gli stakeholder, allineato con la consueta cadenza di reporting e riduce il disordine visivo nei report HTML. Questo è particolarmente utile quando si integrano le linee temporali di progetto in dashboard o si generano riepiloghi di stato giornalieri.

## Prerequisiti
### Librerie e Dipendenze Richieste
Per seguire questo tutorial, avrai bisogno di:
- **groupdocs viewer java** library (versione 25.2 o successiva).
- Maven installato sulla tua macchina per la gestione delle dipendenze.
- Conoscenza di base della programmazione Java.

### Requisiti per la Configurazione dell'Ambiente
Assicurati che il tuo ambiente di sviluppo sia configurato con JDK (Java Development Kit) e un IDE come IntelliJ IDEA o Eclipse che supporti progetti Maven.

### Prerequisiti di Conoscenza
Una familiarità di base con la sintassi Java, la gestione dei file in Java e il lavoro con le dipendenze Maven sarà utile. Tuttavia, questa guida è pensata per rendere il processo semplice per tutti i livelli di competenza.

## Configurazione di groupdocs viewer java
Per iniziare a usare groupdocs viewer java, aggiungilo come dipendenza nel file `pom.xml` del tuo progetto:

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
groupdocs offre una versione di prova gratuita delle proprie librerie, consentendoti di esplorare le funzionalità prima di acquistare o richiedere una licenza temporanea:
- **Versione di Prova**: Visita [GroupDocs Free Trial](https://releases.groupdocs.com/viewer/java/) per scaricare e iniziare a usare la libreria.
- **Licenza Temporanea**: Per test prolungati, richiedi una [licenza temporanea](https://purchase.groupdocs.com/temporary-license/).
- **Acquisto**: Se decidi che groupdocs.viewer java è adatto al tuo progetto, acquistalo direttamente dalla loro [pagina di acquisto](https://purchase.groupdocs.com/buy).

### Inizializzazione e Configurazione di Base
Una volta aggiunta la dipendenza nel tuo `pom.xml` Maven, sei pronto per iniziare a scrivere codice. Inizializza un'istanza di Viewer con il percorso del tuo file MS Project e preparati al rendering.

## Guida all'Implementazione
Vediamo come puoi regolare le unità di tempo per i documenti MS Project usando groupdocs viewer java. Divideremo il processo passo‑per‑passo.

### Panoramica della Funzionalità: Regolare le Unità di Tempo nei Documenti MS Project
Questa funzionalità ti consente di cambiare l'impostazione dell'unità di tempo della gestione del progetto dal valore predefinito (di solito minuti) a giorni, rendendo l'HTML renderizzato più user‑friendly e allineato con gli standard di reporting tipici.

#### Passo 1: Definire la Directory di Output e il Formato del Percorso del File di Pagina
Per prima cosa, specifica dove verranno salvati i file HTML renderizzati:

```java
import java.nio.file.Path;
// Specify the output directory for HTML files
Path outputDirectory = Utils.getOutputDirectoryPath("YOUR_OUTPUT_DIRECTORY");
```

Usa questa directory per risolvere i percorsi dei file dinamicamente per ogni pagina del tuo documento MS Project:

```java
// Define a format for each rendered page's file path
Path pageFilePathFormat = outputDirectory.resolve("page_{0}.html");
```

#### Passo 2: Inizializzare le Opzioni di Visualizzazione
Crea le opzioni di visualizzazione con risorse incorporate, che ti permettono di specificare come il progetto deve essere visualizzato e renderizzato:

```java
import com.groupdocs.viewer.options.HtmlViewOptions;
// Set up HTML view options for rendering
HtmlViewOptions viewOptions = HtmlViewOptions.forEmbeddedResources(pageFilePathFormat);
```

#### Passo 3: Regolare l'Impostazione dell'Unità di Tempo
Specifica che l'unità di tempo per la gestione del progetto è impostata su giorni, spesso più adatta per presentazioni e report:

```java
import com.groupdocs.viewer.options.TimeUnit;
// Change the project management time unit to DAYS
viewOptions.getProjectManagementOptions().setTimeUnit(TimeUnit.DAYS);
```

#### Passo 4: Renderizzare il Documento MS Project
Infine, utilizza la classe Viewer per renderizzare il tuo documento con le opzioni di visualizzazione specificate:

```java
import com.groupdocs.viewer.Viewer;
try (Viewer viewer = new Viewer("YOUR_DOCUMENT_DIRECTORY/SAMPLE_MPP")) {
    // Render the project document as HTML using set view options
    viewer.view(viewOptions);
}
```

### Suggerimenti per la Risoluzione dei Problemi
- Verifica che il percorso della directory di output sia corretto e scrivibile.
- Controlla che il percorso del file MS Project sia corretto e accessibile.
- Se si verificano problemi di rendering, controlla eventuali eccezioni generate dalla classe Viewer.

## Applicazioni Pratiche
Ecco alcuni casi d'uso reali in cui regolare le unità di tempo nei documenti MS Project può risultare particolarmente utile:
1. **Reporting di Progetto** – Gli stakeholder spesso preferiscono riepiloghi giornalieri rispetto a dettagli al livello dei minuti.
2. **Integrazione con Dashboard** – Incorporare le linee temporali in dashboard aziendali che richiedono granularità giornaliera.
3. **Aggiornamenti Automatici** – Sistemi che devono aggiornare lo stato dei progetti su base giornaliera in modo automatico.

## Considerazioni sulle Prestazioni
Quando lavori con file MS Project di grandi dimensioni, considera quanto segue per ottimizzare le prestazioni:
- Usa le risorse incorporate con parsimonia se solo alcune parti del documento sono necessarie frequentemente.
- Monitora l'utilizzo della memoria quando gestisci più progetti molto grandi simultaneamente.
- Sfrutta efficacemente il garbage collection di Java per gestire l'allocazione e la deallocazione delle risorse.

## Conclusione
Hai appena imparato come regolare le unità di tempo di MS Project usando groupdocs viewer java. Questa funzionalità semplifica il processo di rendering dei documenti di progetto, rendendoli più accessibili e più facili da integrare in sistemi più ampi.

Considera di esplorare altre capacità di groupdocs viewer java per migliorare ulteriormente le tue soluzioni di gestione dei documenti. Pronto a fare un passo avanti? Prova a implementare questa soluzione nel tuo prossimo progetto!

## Sezione FAQ
**1. A cosa serve GroupDocs.Viewer per Java?**  
GroupDocs.Viewer per Java consente agli sviluppatori di renderizzare documenti in vari formati, inclusi i file MS Project, in HTML o formati immagine per la visualizzazione.

**2. Posso usare GroupDocs.Viewer per altri tipi di documento?**  
Sì, GroupDocs.Viewer supporta un'ampia gamma di formati oltre a MS Project, come PDF, documenti Word e fogli di calcolo.

**3. Come gestisco la licenza per GroupDocs.Viewer?**  
GroupDocs offre diverse opzioni di licenza, incluse versioni di prova gratuite, licenze temporanee per test prolungati e licenze permanenti a pagamento.

**4. Cosa devo fare se incontro errori durante il rendering dei miei file di progetto?**  
Controlla i percorsi dei file, assicurati di avere i permessi di scrittura sulla directory di output e verifica eventuali eccezioni generate da GroupDocs.Viewer per suggerimenti di risoluzione.

**5. Posso personalizzare il modo in cui i documenti vengono renderizzati con GroupDocs.Viewer?**  
Assolutamente! GroupDocs.Viewer offre una serie di opzioni per personalizzare il rendering, inclusa la possibilità di impostare le unità di tempo per i progetti, selezionare quali risorse incorporare e molto altro.

## Risorse
- [Documentazione](https://docs.groupdocs.com/viewer/java/)
- [Riferimento API](https://reference.groupdocs.com/viewer/java/)
- [Scarica GroupDocs.Viewer](https://releases.groupdocs.com/viewer/java/)
- [Acquista una Licenza](https://purchase.groupdocs.com/buy)

---

**Last Updated:** 2026-01-28  
**Tested With:** groupdocs viewer java 25.2  
**Author:** GroupDocs