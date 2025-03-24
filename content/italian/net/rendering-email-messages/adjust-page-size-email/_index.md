---
title: Regola le dimensioni della pagina durante il rendering dei messaggi e-mail
linktitle: Regola le dimensioni della pagina durante il rendering dei messaggi e-mail
second_title: API GroupDocs.Viewer .NET
description: Scopri come regolare le dimensioni della pagina durante il rendering dei messaggi e-mail in PDF utilizzando GroupDocs.Viewer per .NET. Migliora l'efficienza della visualizzazione dei documenti.
weight: 10
url: /it/net/rendering-email-messages/adjust-page-size-email/
---

# Regola le dimensioni della pagina durante il rendering dei messaggi e-mail

## introduzione
Nell'ambito dello sviluppo .NET, GroupDocs.Viewer fornisce una soluzione completa per il rendering di vari formati di documenti, inclusi i messaggi di posta elettronica. Questo tutorial si concentra sulla regolazione delle dimensioni della pagina durante il rendering dei messaggi di posta elettronica in formato PDF utilizzando GroupDocs.Viewer per .NET. Seguendo i passaggi descritti in questa guida, imparerai come manipolare facilmente le dimensioni della pagina per soddisfare i tuoi requisiti specifici.
## Prerequisiti
Prima di immergerti in questo tutorial, assicurati di possedere i seguenti prerequisiti:
### 1. GroupDocs.Viewer per .NET installato
 Assicurati di avere GroupDocs.Viewer for .NET installato nel tuo ambiente di sviluppo. Puoi scaricarlo da[Qui](https://releases.groupdocs.com/viewer/net/).
### 2. Comprensione di base dello sviluppo .NET
Acquisisci familiarità con i fondamenti dello sviluppo .NET, inclusa la programmazione C# e la gestione dei file.
### 3. IDE (ambiente di sviluppo integrato)
Avere installato un IDE come Visual Studio per scrivere ed eseguire codice .NET.

## Importa spazi dei nomi
Nel tuo progetto C#, importa gli spazi dei nomi necessari per utilizzare le funzionalità GroupDocs.Viewer.

```csharp
using System;
using System.IO;
using GroupDocs.Viewer.Options;
```

## Passaggio 1: imposta la directory di output
Definire la directory in cui verrà salvato il file PDF di output.
```csharp
string outputDirectory = "Your Document Directory";
```
## Passaggio 2: definire il percorso del file
Combina la directory di output con il nome del file di output.
```csharp
string filePath = Path.Combine(outputDirectory, "output.pdf");
```
## Passaggio 3: inizializzare l'oggetto visualizzatore
Crea un'istanza della classe Viewer e specifica il percorso del file del messaggio di posta elettronica.
```csharp
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_MSG))
```
## Passaggio 4: configura le opzioni di visualizzazione PDF
Crea un'istanza di PdfViewOptions e imposta il percorso del file di output.
```csharp
PdfViewOptions options = new PdfViewOptions(filePath);
```
## Passaggio 5: regola le dimensioni della pagina
Modifica la proprietà della dimensione della pagina in EmailOptions di PdfViewOptions.
```csharp
options.EmailOptions.PageSize = PageSize.A4;
```
## Passaggio 6: rendering del documento
Richiamare il metodo View dell'oggetto visualizzatore, passando il PdfViewOptions configurato.
```csharp
viewer.View(options);
```
## Passaggio 7: Visualizza il messaggio di successo
Informare l'utente del rendering riuscito e della directory di output.
```csharp
Console.WriteLine($"\nSource document rendered successfully.\nCheck output in {outputDirectory}.");
```

## Conclusione
In conclusione, questo tutorial ha dimostrato come regolare le dimensioni della pagina durante il rendering dei messaggi di posta elettronica in formato PDF utilizzando GroupDocs.Viewer per .NET. Seguendo queste istruzioni dettagliate, puoi manipolare in modo efficiente le dimensioni della pagina per soddisfare i tuoi requisiti specifici, migliorando le funzionalità di visualizzazione e gestione dei documenti all'interno delle tue applicazioni .NET.
## Domande frequenti
### GroupDocs.Viewer è compatibile con diversi formati di messaggi e-mail?
GroupDocs.Viewer supporta il rendering di vari formati di messaggi di posta elettronica, inclusi MSG ed EML.
### Posso personalizzare la dimensione della pagina in base alle mie preferenze?
Sì, puoi regolare le dimensioni della pagina utilizzando PdfViewOptions di GroupDocs.Viewer, offrendo flessibilità nel rendering del documento.
### GroupDocs.Viewer fornisce supporto per altri formati di documenti?
Sì, GroupDocs.Viewer supporta un'ampia gamma di formati di documenti, inclusi PDF, Microsoft Office, immagini e altro.
### GroupDocs.Viewer è adatto per applicazioni di livello aziendale?
Assolutamente sì, GroupDocs.Viewer offre funzionalità robuste adatte sia ad applicazioni su piccola scala che a livello aziendale, garantendo un rendering e una gestione efficienti dei documenti.
### Dove posso cercare assistenza o ulteriore supporto per GroupDocs.Viewer?
 È possibile visitare il forum GroupDocs.Viewer[Qui](https://forum.groupdocs.com/c/viewer/9) cercare assistenza, porre domande e interagire con la comunità.