---
"date": "2025-04-24"
"description": "Scopri come suddividere i fogli Excel in sezioni gestibili utilizzando GroupDocs.Viewer per Java. Migliora la gestione e la presentazione dei dati con la nostra guida passo passo."
"title": "Dividi i fogli Excel per righe e colonne con GroupDocs.Viewer in Java&#58; una guida completa"
"url": "/it/java/custom-rendering/groupdocs-viewer-java-split-excel-sheets-rows-columns/"
"weight": 1
type: docs
---
# Divisione di fogli Excel per righe e colonne utilizzando GroupDocs.Viewer in Java

## Introduzione

Gestire file Excel di grandi dimensioni può essere impegnativo, soprattutto quando si presentano segmenti di dati specifici senza sovraccaricare il pubblico. Con GroupDocs.Viewer per Java, è possibile suddividere i fogli di lavoro in blocchi gestibili in base a righe e colonne, migliorando la leggibilità e semplificando la gestione dei dati.

In questa guida completa, esploreremo come utilizzare GroupDocs.Viewer per dividere efficacemente i fogli Excel per righe e colonne. Imparerai:
- Come configurare GroupDocs.Viewer per Java
- Implementazione passo passo della divisione dei fogli di lavoro
- Applicazioni pratiche di queste tecniche

Cominciamo con i prerequisiti necessari per proseguire!

## Prerequisiti

Per implementare correttamente questa soluzione, assicurati di aver soddisfatto i seguenti requisiti:

### Librerie, versioni e dipendenze richieste

Imposta il tuo progetto utilizzando Maven aggiungendo la seguente configurazione:

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

### Requisiti di configurazione dell'ambiente

Assicurati che Java sia installato sul tuo computer e di avere un IDE compatibile, come IntelliJ IDEA o Eclipse.

### Prerequisiti di conoscenza

Per leggere questa guida è essenziale avere una conoscenza di base della programmazione Java, della configurazione di Maven e dell'uso dei file Excel.

## Impostazione di GroupDocs.Viewer per Java

L'impostazione di GroupDocs.Viewer prevede semplici passaggi:
1. **Configurazione Maven**: Aggiungi il repository Maven sopra e la dipendenza al tuo `pom.xml` file.
2. **Acquisizione della licenza**: Ottieni una prova gratuita, una licenza temporanea o acquista una licenza completa da [Documenti di gruppo](https://purchase.groupdocs.com/buy).
3. **Inizializzazione di base**:
   - Crea un nuovo progetto Java nel tuo IDE.
   - Aggiungere la dipendenza Maven come mostrato sopra.

Dopo aver completato questi passaggi, sarai pronto a implementare la funzionalità principale di suddivisione dei fogli Excel in righe e colonne utilizzando GroupDocs.Viewer per Java.

## Guida all'implementazione

### Divisione dei fogli di lavoro per righe

#### Panoramica
Questa funzione consente di suddividere un foglio di lavoro in più pagine in base al numero di righe per pagina. È particolarmente utile per gestire dataset estesi, presentandoli in sezioni più piccole.

#### Fasi di implementazione
**Passaggio 1: impostare percorsi e visualizzatore**
Inizia impostando la directory di output e inizializzando il `Viewer` oggetto per il tuo file Excel:
```java
Path outputDirectory = Path.of("YOUR_OUTPUT_DIRECTORY/SplitByRows");
Path pageFilePathFormat = outputDirectory.resolve("page_{0}.html");

try (Viewer viewer = new Viewer("YOUR_DOCUMENT_DIRECTORY/TWO_PAGES_XLSX")) {
    // Procedere con gli ulteriori passaggi...
}
```
**Passaggio 2: configurare le righe per pagina**
Definisci il numero di righe per pagina e imposta `HtmlViewOptions`:
```java
int countRowsPerPage = 15;
HtmlViewOptions viewOptions = HtmlViewOptions.forEmbeddedResources(pageFilePathFormat);
viewOptions.setSpreadsheetOptions(SpreadsheetOptions.forSplitSheetIntoPages(countRowsPerPage));
```
**Passaggio 3: rendering del documento**
Esegui il rendering del documento con le opzioni specificate:
```java
viewer.view(viewOptions);
```
### Divisione dei fogli di lavoro per righe e colonne

#### Panoramica
Questa funzionalità aumenta la flessibilità consentendo di suddividere i fogli di lavoro in base a righe e colonne per pagina. È ideale per creare layout personalizzati su misura per specifiche esigenze di presentazione.

#### Fasi di implementazione
**Passaggio 1: impostare percorsi e visualizzatore**
Similmente alla sezione precedente, imposta i tuoi percorsi e inizializza il `Viewer` oggetto:
```java
Path outputDirectory = Path.of("YOUR_OUTPUT_DIRECTORY/SplitByRowsAndColumns");
Path pageFilePathFormat = outputDirectory.resolve("page_{0}.html");

try (Viewer viewer = new Viewer("YOUR_DOCUMENT_DIRECTORY/FOUR_PAGES_XLSX")) {
    // Procedere con gli ulteriori passaggi...
}
```
**Passaggio 2: configurare righe e colonne per pagina**
Specificare sia il numero di righe che di colonne per pagina:
```java
int countRowsPerPage = 15;
int countColumnsPerPage = 7;

HtmlViewOptions options = HtmlViewOptions.forEmbeddedResources(pageFilePathFormat);
options.setSpreadsheetOptions(SpreadsheetOptions.forSplitSheetIntoPages(countRowsPerPage, countColumnsPerPage));
```
**Passaggio 3: rendering del documento**
Esegui il rendering del documento con le tue impostazioni personalizzate:
```java
viewer.view(options);
```
## Applicazioni pratiche
Ecco alcuni casi d'uso reali per la suddivisione dei fogli Excel in righe e colonne:
1. **Presentazione dei dati**: Crea report concisi dividendo grandi set di dati in sezioni più piccole.
2. **Materiali didattici**: Genera dispense per gli studenti con punti dati mirati da schede di lavoro dettagliate.
3. **Analisi aziendale**Scomporre fogli di calcolo finanziari complessi per semplificare l'analisi e la discussione.

Le possibilità di integrazione includono l'incorporamento di questi fogli divisi in applicazioni web o la generazione di PDF per l'utilizzo offline.

## Considerazioni sulle prestazioni
Per garantire prestazioni ottimali durante l'utilizzo di GroupDocs.Viewer:
- **Ottimizzare l'utilizzo delle risorse**: Monitorare l'utilizzo della memoria, soprattutto con file Excel di grandi dimensioni.
- **Gestione della memoria Java**: Utilizzare strutture dati efficienti e gestire efficacemente la garbage collection.
- **Migliori pratiche**: Aggiornare regolarmente GroupDocs.Viewer all'ultima versione per funzionalità migliorate e correzioni di bug.

## Conclusione
Seguendo questa guida, hai imparato a dividere i fogli Excel per righe e colonne utilizzando GroupDocs.Viewer per Java. Questa potente funzionalità migliora la gestione e la presentazione dei dati, semplificando la gestione di dataset di grandi dimensioni.

passaggi successivi prevedono l'esplorazione di funzionalità più avanzate di GroupDocs.Viewer o l'integrazione di queste funzionalità nelle applicazioni esistenti.

## Sezione FAQ
**D1: Qual è il numero massimo di righe in cui posso suddividere un foglio Excel?**
A1: Il massimo dipende dalla capacità di memoria del sistema e dalla complessità dei dati.

**D2: Posso personalizzare il formato di output per i fogli divisi?**
A2: Sì, puoi usare `HtmlViewOptions` per specificare formati diversi come HTML o PDF.

**D3: Come posso gestire in modo efficiente file Excel di grandi dimensioni con GroupDocs.Viewer?**
A3: Ottimizzare l'utilizzo della memoria e valutare la possibilità di suddividere il file in parti più piccole prima dell'elaborazione.

**D4: È possibile suddividere i fogli in base a criteri di dati specifici?**
R4: Sebbene non sia disponibile il supporto diretto per la suddivisione basata sui dati, è possibile preelaborare i dati utilizzando Java prima di applicare le suddivisioni riga/colonna.

**D5: Quali sono alcuni problemi comuni quando si utilizza GroupDocs.Viewer per dividere i fogli?**
R5: Problemi comuni includono errori di memoria con file di grandi dimensioni e configurazioni di percorso errate. Assicurarsi che i percorsi siano impostati correttamente e che l'ambiente disponga di risorse sufficienti.

## Risorse
- **Documentazione**: [Documentazione Java di GroupDocs Viewer](https://docs.groupdocs.com/viewer/java/)
- **Riferimento API**: [Riferimento API GroupDocs](https://reference.groupdocs.com/viewer/java/)
- **Scaricamento**: [Versioni Java di GroupDocs Viewer](https://releases.groupdocs.com/viewer/java/)
- **Acquistare**: [Acquista la licenza GroupDocs](https://purchase.groupdocs.com/buy)
- **Prova gratuita**: [Prova gratuita di GroupDocs](https://releases.groupdocs.com/viewer/java/)
- **Licenza temporanea**: [Ottieni la licenza temporanea](https://purchase.groupdocs.com/temporary-license/)
- **Supporto**: [Forum di supporto di GroupDocs](https://forum.groupdocs.com/c/viewer/9)

Intraprendete il vostro percorso per padroneggiare GroupDocs.Viewer per Java esplorando queste risorse e implementando le funzionalità illustrate. Buona programmazione!