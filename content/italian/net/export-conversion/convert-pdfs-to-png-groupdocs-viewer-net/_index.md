---
"date": "2025-04-25"
"description": "Scopri come convertire le pagine PDF in immagini PNG mantenendo le dimensioni originali utilizzando GroupDocs.Viewer per .NET. Questa guida illustra l'installazione, la configurazione e le best practice."
"title": "Convertire i PDF in PNG con le dimensioni originali utilizzando GroupDocs.Viewer per .NET"
"url": "/it/net/export-conversion/convert-pdfs-to-png-groupdocs-viewer-net/"
"weight": 1
type: docs
---
# Convertire i PDF in PNG con le dimensioni originali utilizzando GroupDocs.Viewer per .NET

## Introduzione

Convertire i file PDF in immagini PNG mantenendo le dimensioni originali della pagina è essenziale per la digitalizzazione di documenti di alta qualità o la preparazione di contenuti web. Questo tutorial vi guiderà nell'utilizzo di GroupDocs.Viewer per .NET per convertire le pagine PDF in file PNG, mantenendone le dimensioni originali.

![Converti i PDF in PNG con le dimensioni originali con GroupDocs.Viewer per .NET](/viewer/export-conversion/convert-pdfs-to-png-with-original-size.png)

**Cosa imparerai:**
- Come impostare e configurare GroupDocs.Viewer per .NET nel tuo progetto
- Procedura dettagliata per trasformare i PDF in immagini PNG mantenendo le dimensioni della pagina
- Opzioni di configurazione chiave e best practice per prestazioni ottimali

Al termine di questo tutorial, sarai in grado di integrare questa funzionalità nelle tue applicazioni senza problemi. Iniziamo con i prerequisiti necessari per iniziare.

## Prerequisiti

Prima di implementare GroupDocs.Viewer per .NET nel tuo progetto, assicurati di disporre dei seguenti requisiti:

### Librerie e versioni richieste
- **GroupDocs.Viewer per .NET**: Versione 25.3.0 o successiva.

### Requisiti di configurazione dell'ambiente
- Un ambiente di sviluppo compatibile come Visual Studio.
- Conoscenza di base della programmazione C#.

### Prerequisiti di conoscenza
- Familiarità con la gestione dei pacchetti NuGet.
- Esperienza di lavoro con PDF ed elaborazione di immagini in applicazioni .NET.

Una volta soddisfatti questi prerequisiti, possiamo procedere alla configurazione di GroupDocs.Viewer per .NET.

## Impostazione di GroupDocs.Viewer per .NET

Per iniziare a utilizzare GroupDocs.Viewer per .NET, seguire i passaggi di installazione indicati di seguito:

### Installazione tramite la console di NuGet Package Manager
Apri il tuo progetto in Visual Studio e usa il seguente comando:
```plaintext
Install-Package GroupDocs.Viewer -Version 25.3.0
```

### Installazione tramite .NET CLI
In alternativa, è possibile installarlo utilizzando la CLI .NET con questo comando:
```bash
dotnet add package GroupDocs.Viewer --version 25.3.0
```

### Fasi di acquisizione della licenza
1. **Prova gratuita**: Scarica una versione di prova da [Download di GroupDocs](https://releases.groupdocs.com/viewer/net/).
2. **Licenza temporanea**: Ottieni una licenza temporanea per esplorare tutte le funzionalità su [Pagina della licenza temporanea](https://purchase.groupdocs.com/temporary-license/).
3. **Acquistare**: Per un utilizzo prolungato, acquistare una licenza tramite il [Acquista pagina](https://purchase.groupdocs.com/buy).

### Inizializzazione e configurazione di base
Per inizializzare GroupDocs.Viewer per .NET nel tuo progetto C#, segui questi passaggi:
1. Importa gli spazi dei nomi necessari:
    ```csharp
    using System;
    using GroupDocs.Viewer;
    using GroupDocs.Viewer.Options;
    ```
2. Imposta i percorsi per il PDF di input e la directory di output.
3. Inizializzare `Viewer` con il percorso al documento sorgente, come mostrato in questo frammento:
   ```csharp
   string documentPath = "YOUR_DOCUMENT_DIRECTORY/SAMPLE_PDF.pdf";
   string outputDirectory = "YOUR_OUTPUT_DIRECTORY";
   string pageFilePathFormat = $"{outputDirectory}/page_{0}.png";

   using (Viewer viewer = new Viewer(documentPath))
   {
       PngViewOptions viewOptions = new PngViewOptions(pageFilePathFormat);
       viewer.View(viewOptions);
   }
   ```

## Guida all'implementazione
Questa sezione riguarda l'implementazione del rendering delle pagine PDF come immagini PNG mantenendone le dimensioni originali.

### Rendering di pagine PDF in PNG con dimensioni di pagina originali
#### Panoramica
Questa funzione consente di convertire ogni pagina di un documento PDF in un'immagine PNG, mantenendone le dimensioni originali. Questa funzionalità è particolarmente utile per le applicazioni che richiedono una rappresentazione visiva precisa dei documenti.

##### Passaggio 1: configurazione dei percorsi e inizializzazione del visualizzatore
Crea variabili per il percorso del PDF di input e la directory di output:
```csharp
string documentPath = "YOUR_DOCUMENT_DIRECTORY/SAMPLE_PDF.pdf";
string outputDirectory = "YOUR_OUTPUT_DIRECTORY";
string pageFilePathFormat = $"{outputDirectory}/page_{0}.png";
```
Inizializzare il `Viewer` classe con il percorso del documento sorgente:
```csharp
using (Viewer viewer = new Viewer(documentPath))
{
    // Il blocco di codice continuerà nel passaggio successivo
}
```
##### Passaggio 2: configurare PngViewOptions
Crea un'istanza di `PngViewOptions`, specificando un modello di denominazione dei file per le immagini di output:
```csharp
PngViewOptions viewOptions = new PngViewOptions(pageFilePathFormat);
```
Configura le opzioni di visualizzazione per visualizzare ogni pagina nelle sue dimensioni originali:
```csharp
viewOptions.PdfOptions.RenderOriginalPageSize = true;
```
##### Passaggio 3: rendering delle pagine del documento
Chiama il `View` metodo sul tuo `Viewer` istanza, passando le opzioni di visualizzazione configurate:
```csharp
viewer.View(viewOptions);
```
### Suggerimenti per la risoluzione dei problemi
- Assicurarsi che i percorsi siano corretti e che le directory esistano.
- Verificare di disporre delle autorizzazioni necessarie per leggere dalle directory di input e scrivere nelle directory di output.

## Applicazioni pratiche
1. **Digitalizzazione dei documenti**: Converti i documenti PDF d'archivio in immagini digitali per facilitarne l'accesso e la distribuzione.
2. **Portali Web**: Visualizza le anteprime dei documenti sui siti Web senza richiedere lettori PDF.
3. **Sistemi di gestione dei contenuti (CMS)**: Integrazione con piattaforme CMS per gestire e visualizzare in modo efficiente grandi volumi di contenuti PDF.

## Considerazioni sulle prestazioni
Per ottimizzare le prestazioni della tua applicazione utilizzando GroupDocs.Viewer per .NET:
- Limitare l'utilizzo della memoria elaborando i documenti in blocchi se si gestiscono file di grandi dimensioni.
- Ove possibile, utilizzare metodi asincroni per evitare di bloccare i thread durante il rendering.
- Smaltire `Viewer` istanze subito dopo l'uso per liberare risorse.

## Conclusione
In questo tutorial, hai imparato come convertire le pagine PDF in immagini PNG mantenendone le dimensioni originali utilizzando GroupDocs.Viewer per .NET. Abbiamo illustrato come configurare l'ambiente, le opzioni necessarie per risultati ottimali e abbiamo esplorato applicazioni pratiche per questa funzionalità.

I prossimi passi prevedono la sperimentazione di altre opzioni di rendering disponibili in GroupDocs.Viewer o la sua integrazione in progetti più ampi per funzionalità avanzate di gestione dei documenti.

## Sezione FAQ
1. **Qual è il modo migliore per gestire file PDF di grandi dimensioni con GroupDocs.Viewer?**
   - Elaborare i documenti in blocchi più piccoli e utilizzare metodi asincroni per mantenere le prestazioni.
2. **Posso personalizzare i nomi dei file PNG di output?**
   - Sì, specificando un modello di denominazione in `PngViewOptions`.
3. **È possibile visualizzare solo pagine specifiche?**
   - Assolutamente, puoi configurare `PageNumbers` In `PngViewOptions` per specificare quali pagine visualizzare.
4. **Come posso gestire le licenze per GroupDocs.Viewer?**
   - Le opzioni includono una prova gratuita, una licenza temporanea o l'acquisto di una licenza completa.
5. **Questa configurazione può essere utilizzata nelle applicazioni web?**
   - Sì, è adatto per il rendering lato server di PDF in ASP.NET Core e altri framework web basati su .NET.

## Risorse
- [Documentazione](https://docs.groupdocs.com/viewer/net/)
- [Riferimento API](https://reference.groupdocs.com/viewer/net/)
- [Scarica GroupDocs.Viewer](https://releases.groupdocs.com/viewer/net/)
- [Acquista licenza](https://purchase.groupdocs.com/buy)
- [Prova gratuita](https://releases.groupdocs.com/viewer/net/)
- [Licenza temporanea](https://purchase.groupdocs.com/temporary-license/)
- [Forum di supporto](https://forum.groupdocs.com/c/viewer/9)