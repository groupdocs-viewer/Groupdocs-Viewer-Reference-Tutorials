---
"description": "Sblocca facilmente i dati nascosti nei fogli di calcolo utilizzando GroupDocs.Viewer per .NET. Segui la nostra guida passo passo per scoprire colonne e righe nascoste."
"linktitle": "Rendi colonne e righe nascoste"
"second_title": "API .NET di GroupDocs.Viewer"
"title": "Rendi colonne e righe nascoste"
"url": "/it/net/spreadsheet-rendering-options/render-hidden-columns-rows/"
"weight": 13
---

# Rendi colonne e righe nascoste

## Introduzione
Nell'ambito della visualizzazione di documenti, GroupDocs.Viewer per .NET si distingue come uno strumento affidabile che facilita il rendering fluido di vari formati di documento. Una funzionalità interessante è la possibilità di visualizzare colonne e righe nascoste all'interno dei fogli di calcolo. In questo tutorial, approfondiremo i passaggi per sbloccare questa funzionalità e liberare il potenziale dei vostri dati.
## Prerequisiti
Prima di intraprendere questo viaggio, assicurati di avere i seguenti prerequisiti:
- GroupDocs.Viewer per .NET: assicurati di avere installata la versione più recente. In caso contrario, puoi scaricarla da [sito web ufficiale](https://releases.groupdocs.com/viewer/net/).
- File di documento: preparare un documento di esempio in formato foglio di calcolo (ad esempio, SAMPLE.XLSX) per sperimentare con colonne e righe nascoste.
- Ambiente di sviluppo: impostare un ambiente di lavoro, preferibilmente utilizzando Visual Studio o qualsiasi altro IDE adatto allo sviluppo .NET.
## Importa spazi dei nomi
Nel tuo progetto .NET, importa gli spazi dei nomi necessari per sfruttare efficacemente le funzionalità di GroupDocs.Viewer:
```csharp
using System;
using System.IO;
using GroupDocs.Viewer.Options;
```
## Passaggio 1: impostare la directory di output
```csharp
string outputDirectory = "Your Document Directory";
string pageFilePathFormat = Path.Combine(outputDirectory, "page_{0}.html");
```
Definisci la directory di output in cui verranno archiviate le pagine HTML renderizzate. Modifica il formato del percorso del file di conseguenza.
## Passaggio 2: inizializzare il visualizzatore e configurare le opzioni
```csharp
using (Viewer viewer = new Viewer("SAMPLE.XLSX"))
{
    HtmlViewOptions options = HtmlViewOptions.ForEmbeddedResources(pageFilePathFormat);
    options.SpreadsheetOptions.RenderHiddenColumns = true;
    options.SpreadsheetOptions.RenderHiddenRows = true;
```
Crea un'istanza di Viewer specificando il percorso del tuo foglio di calcolo. Configura le opzioni di visualizzazione HTML per incorporare risorse e abilitare il rendering di colonne e righe nascoste.
## Passaggio 3: eseguire il processo di rendering
```csharp
    viewer.View(options);
}
```
Invoca il metodo View sull'oggetto viewer, passando le opzioni configurate. Questo avvia il processo di rendering.
## Passaggio 4: controllare l'output
```csharp
Console.WriteLine($"\nSource document rendered successfully.\nCheck output in {outputDirectory}.");
```
Verificare il corretto rendering del documento sorgente e individuare l'output nella directory specificata.
## Conclusione
Sbloccare colonne e righe nascoste nei fogli di calcolo diventa un gioco da ragazzi con GroupDocs.Viewer per .NET. Questo tutorial ti ha fornito i passaggi essenziali per rivelare i dati nascosti, offrendoti una visione più completa dei tuoi documenti.
## Domande frequenti
### Posso visualizzare colonne e righe nascoste in formati di documenti diversi dai fogli di calcolo?
Sì, GroupDocs.Viewer supporta vari formati di documenti, tra cui Word, PDF e PowerPoint, oltre ai fogli di calcolo.
### Esiste un limite al numero di colonne e righe nascoste che possono essere visualizzate?
GroupDocs.Viewer gestisce in modo efficiente il rendering di un'ampia gamma di colonne e righe nascoste. Tuttavia, casi estremi con un'elevata quantità di dati nascosti potrebbero influire sulle prestazioni.
### Posso personalizzare il formato di output dei dati renderizzati?
Assolutamente sì! GroupDocs.Viewer offre opzioni flessibili per personalizzare l'output, consentendo di adattare i dati renderizzati alle proprie esigenze specifiche.
### Ci sono considerazioni sulla licenza per l'utilizzo di GroupDocs.Viewer?
Sì, assicurati di avere la licenza appropriata per il tuo utilizzo. Esplora le opzioni di licenza su [Acquisto GroupDocs](https://purchase.groupdocs.com/buy) o ottenere un [licenza temporanea](https://purchase.groupdocs.com/temporary-license/) per effettuare i test.
### Dove posso cercare assistenza o mettermi in contatto con la community di GroupDocs per ricevere supporto?
Visita il [Forum di GroupDocs.Viewer](https://forum.groupdocs.com/c/viewer/9) per supporto, discussioni e interazione con la comunità.