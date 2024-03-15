---
title: Imposta il timeout di caricamento delle risorse (avanzato)
linktitle: Imposta il timeout di caricamento delle risorse (avanzato)
second_title: API GroupDocs.Viewer .NET
description: Scopri come configurare in modo efficiente i timeout di caricamento delle risorse in GroupDocs.Viewer per .NET. Rendering di documenti master con precisione e stabilità.
type: docs
weight: 13
url: /it/net/advanced-loading/set-resource-loading-timeout/
---
## introduzione
Nell'ambito dello sviluppo .NET, GroupDocs.Viewer fornisce un potente set di strumenti per il rendering di documenti e immagini con precisione ed efficienza. Per sfruttare le sue capacità è necessario comprenderne le complessità, inclusa l'impostazione dei timeout di caricamento delle risorse. In questo tutorial approfondiremo il processo di configurazione dei timeout di caricamento delle risorse in GroupDocs.Viewer per .NET.
## Prerequisiti
Prima di iniziare questo tutorial, assicurati di possedere i seguenti prerequisiti:
1. Conoscenza di base dello sviluppo .NET: la familiarità con la programmazione C# e i fondamenti del framework .NET è essenziale.
2.  Installazione di GroupDocs.Viewer per .NET: scaricare e installare la libreria GroupDocs.Viewer per .NET dalla[pagina di download](https://releases.groupdocs.com/viewer/net/).
3. Ambiente di sviluppo integrato (IDE): disporre di un IDE come Visual Studio installato sul sistema.

## Importa spazi dei nomi
Prima di immergerti nel processo di codifica, importa gli spazi dei nomi necessari:
```csharp
using System;
using System.IO;
using GroupDocs.Viewer.Options;
```

## Passaggio 1: definire la directory di output
Innanzitutto, definisci la directory in cui verranno salvati i documenti renderizzati:
```csharp
string outputDirectory = "Your Document Directory";
```
 Sostituire`"Your Document Directory"`con il percorso in cui si desidera salvare i documenti sottoposti a rendering.
## Passaggio 2: definire il formato del percorso del file di paging
Definire il formato per i percorsi dei file delle singole pagine:
```csharp
string pageFilePathFormat = Path.Combine(outputDirectory, "page_{0}.html");
```
 Questo formato genererà nomi di file come`page_1.html`, `page_2.html`, ecc., all'interno della directory di output specificata.
## Passaggio 3: configura le opzioni di caricamento
Configura le opzioni di caricamento, incluso il timeout di caricamento delle risorse:
```csharp
LoadOptions loadOptions = new LoadOptions
{
    ResourceLoadingTimeout = TimeSpan.FromSeconds(5)
};
```
In questo esempio, viene impostato un timeout di 5 secondi per il caricamento delle risorse.
## Passaggio 4: inizializzare l'oggetto visualizzatore
 Inizializza il`Viewer` oggetto con il documento da sottoporre a rendering e le opzioni di caricamento definite:
```csharp
using (Viewer viewer = new Viewer(TestFiles.WITH_EXTERNAL_IMAGE_DOC, loadOptions))
```
 Sostituire`TestFiles.WITH_EXTERNAL_IMAGE_DOC` con il percorso del documento di cui desideri eseguire il rendering.
## Passaggio 5: configura le opzioni di visualizzazione HTML
Configura le opzioni di visualizzazione HTML per le risorse incorporate:
```csharp
HtmlViewOptions options = HtmlViewOptions.ForEmbeddedResources(pageFilePathFormat);
```
Questa configurazione garantisce che le risorse incorporate come le immagini siano incluse nell'HTML sottoposto a rendering.
## Passaggio 6: rendering del documento
Eseguire il rendering del documento utilizzando le opzioni configurate:
```csharp
viewer.View(options);
```
Questo passaggio avvia il processo di rendering.
## Passaggio 7: Visualizza la directory di output
Visualizza un messaggio che indica il rendering riuscito e la posizione della directory di output:
```csharp
Console.WriteLine($"\nSource document rendered successfully.\nCheck output in {outputDirectory}.");
```

## Conclusione
Controllare i timeout di caricamento delle risorse in GroupDocs.Viewer per .NET è fondamentale per garantire processi di rendering dei documenti fluidi. Seguendo questa esercitazione avrai acquisito informazioni dettagliate sulla configurazione efficace dei timeout, migliorando la tua competenza nello sviluppo .NET.
## Domande frequenti
### Qual è il significato dell'impostazione dei timeout di caricamento delle risorse?
L'impostazione dei timeout di caricamento delle risorse garantisce che i processi di rendering non si blocchino indefinitamente, migliorando la stabilità dell'applicazione.
### È possibile personalizzare i timeout di caricamento delle risorse in base ai tipi di documenti?
Sì, i timeout di caricamento delle risorse possono essere regolati in base alla complessità e alle dimensioni dei documenti sottoposti a rendering.
### Ci sono implicazioni sulle prestazioni derivanti dall'impostazione di timeout più brevi?
Timeout più brevi possono portare al rendering incompleto di documenti complessi se le risorse non possono essere caricate entro la durata specificata.
### GroupDocs.Viewer è adatto per il rendering di vari formati di documenti?
Sì, GroupDocs.Viewer supporta il rendering di un'ampia gamma di formati di documenti tra cui PDF, DOCX, XLSX e altri.
### È possibile disabilitare i timeout di caricamento delle risorse?
Anche se non è consigliabile, i timeout di caricamento delle risorse possono essere impostati su un valore elevato o disabilitati del tutto a seconda dei requisiti specifici.