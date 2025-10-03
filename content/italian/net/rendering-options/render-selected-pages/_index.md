---
"description": "Scopri come visualizzare pagine selezionate da documenti utilizzando Groupdocs.Viewer per .NET. Tutorial dettagliato con esempi di codice inclusi."
"linktitle": "Visualizza pagine selezionate"
"second_title": "API .NET di GroupDocs.Viewer"
"title": "Visualizza pagine selezionate"
"url": "/it/net/rendering-options/render-selected-pages/"
"weight": 17
type: docs
---
# Visualizza pagine selezionate

## Introduzione

In questo tutorial, approfondiremo come utilizzare Groupdocs.Viewer per .NET per il rendering di pagine selezionate da un documento. Che tu sia uno sviluppatore esperto o alle prime armi, questa guida passo passo ti guiderà passo passo attraverso il processo con semplicità.

## Prerequisiti

Prima di iniziare, assicurati di avere i seguenti prerequisiti:

### 1. Installazione

Assicurati di aver installato Groupdocs.Viewer per .NET nel tuo ambiente di sviluppo. In caso contrario, puoi scaricarlo da [Link per il download](https://releases.groupdocs.com/viewer/net/).

## Importazione di spazi dei nomi

Nel file di codice C#, importa gli spazi dei nomi necessari per accedere alle classi e ai metodi richiesti. Puoi farlo utilizzando `using` direttiva:

```csharp
using System;
using System.IO;
using GroupDocs.Viewer.Options;
```

Ora scomponiamo il codice di esempio fornito in più passaggi:

## Passaggio 1: impostare la directory di output

Definisci la directory in cui desideri salvare le pagine renderizzate. Sostituisci `"Your Document Directory"` con il percorso della directory desiderato.

```csharp
string outputDirectory = "Your Document Directory";
```

## Passaggio 2: definire il formato del percorso del file di paging

Specifica il formato per i percorsi dei file delle pagine renderizzate. Questo verrà utilizzato per salvare ogni pagina come file HTML nella directory di output.

```csharp
string pageFilePathFormat = Path.Combine(outputDirectory, "page_{0}.html");
```

## Passaggio 3: creare un'istanza dell'oggetto Viewer

Crea un'istanza della classe Viewer, passando come argomento il percorso del documento che vuoi visualizzare.

```csharp
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_DOCX))
```

## Passaggio 4: configurare le opzioni di visualizzazione HTML

Imposta le opzioni di visualizzazione HTML per il rendering. In questo esempio, stiamo configurando le opzioni per incorporare risorse nell'output HTML.

```csharp
HtmlViewOptions options = HtmlViewOptions.ForEmbeddedResources(pageFilePathFormat);
```

## Passaggio 5: rendering delle pagine selezionate

Specifica i numeri di pagina che desideri visualizzare. In questo caso, stiamo visualizzando le pagine da 1 a 3. Quindi, chiama il metodo View sull'oggetto Viewer, passando le opzioni e i numeri di pagina come argomenti.

```csharp
viewer.View(options, 1, 3);
```

## Passaggio 6: Risultato dell'output

Infine, visualizza un messaggio che indica l'avvenuto rendering del documento e la posizione in cui sono salvati i file di output.

```csharp
Console.WriteLine($"\nSource document rendered successfully.\nCheck output in {outputDirectory}.");
```

## Conclusione

Congratulazioni! Hai imparato con successo come visualizzare le pagine selezionate di un documento utilizzando Groupdocs.Viewer per .NET. Grazie a queste conoscenze, ora puoi integrare facilmente le funzionalità di visualizzazione dei documenti nelle tue applicazioni .NET.

## Domande frequenti

### D: Posso eseguire il rendering di pagine da diversi tipi di documenti, come PDF o immagini?

R: Sì, Groupdocs.Viewer per .NET supporta il rendering di pagine da vari formati di documenti, tra cui PDF, documenti di Microsoft Office e file di immagine.

### D: Esiste una versione di prova disponibile per testarla prima dell'acquisto?

A: Sì, puoi accedere a una versione di prova gratuita di Groupdocs.Viewer per .NET da [sito web](https://releases.groupdocs.com/).

### D: Posso personalizzare un formato di output diverso da HTML?

R: Assolutamente sì, Groupdocs.Viewer per .NET offre opzioni per visualizzare le pagine come immagini, PDF e altro ancora, oltre che in formato HTML.

### D: Come posso ottenere licenze temporanee per scopi di prova?

A: Le licenze temporanee possono essere acquisite da [pagina della licenza temporanea](https://purchase.groupdocs.com/temporary-license/) sul sito web Groupdocs.

### D: Dove posso cercare assistenza o ottenere supporto per eventuali problemi che riscontro?

A: Puoi visitare il [Forum di Groupdocs.Viewer](https://forum.groupdocs.com/c/viewer/9) per ricevere supporto e guida dalla comunità e dagli sviluppatori.