---
title: Carica documenti dal flusso
linktitle: Carica documenti dal flusso
second_title: API GroupDocs.Viewer .NET
description: Scopri come caricare facilmente documenti dai flussi utilizzando GroupDocs.Viewer per .NET. Migliora le tue applicazioni .NET con potenti funzionalità di visualizzazione dei documenti.
type: docs
weight: 12
url: /it/net/loading-documents/loading-document-stream/
---
## introduzione
Nell'ambito dello sviluppo .NET, la gestione e la visualizzazione efficiente dei documenti è fondamentale. Con l'avvento di strumenti e librerie avanzati, le attività che un tempo sembravano scoraggianti ora sono semplificate. Tra questi strumenti, GroupDocs.Viewer per .NET si distingue come una soluzione versatile per gestire senza problemi vari formati di documenti. In questa guida completa, approfondiamo le complessità dell'utilizzo di GroupDocs.Viewer per .NET per caricare documenti da un flusso. Che tu sia uno sviluppatore esperto o che tu abbia appena iniziato, questo tutorial ti fornirà le conoscenze per sfruttare la potenza di GroupDocs.Viewer in modo efficace.
## Prerequisiti
Prima di immergerti nel tutorial, assicurati di disporre dei seguenti prerequisiti:
1. Comprensione di base di C# e .NET Framework: la familiarità con il linguaggio di programmazione C# e il framework .NET aiuterà a comprendere i concetti discussi.
   
2.  Installazione di GroupDocs.Viewer per .NET: scaricare e installare GroupDocs.Viewer per .NET dal[sito web](https://releases.groupdocs.com/viewer/net/).
3. IDE: disporre di un ambiente di sviluppo integrato (IDE) come Visual Studio installato per la codifica e il test.
4. Flusso di documenti: prepara un flusso di documenti per il caricamento. Potrebbe trattarsi di un flusso di file o di qualsiasi altra sorgente di flusso compatibile.

## Importa spazi dei nomi
Prima di implementare il codice per caricare documenti da un flusso, assicurati di importare gli spazi dei nomi necessari:
```csharp
using System;
using System.IO;
using GroupDocs.Viewer.Options;
```
## Passaggio 1: definire la directory di output
```csharp
string outputDirectory = "Your Document Directory";
```
Imposta il percorso della directory in cui verrà salvato il documento renderizzato.
## Passaggio 2: definire il formato del percorso del file di paging
```csharp
string pageFilePathFormat = Path.Combine(outputDirectory, "page_{0}.html");
```
Definire il formato per il percorso del file di ciascuna pagina. Qui, "{0}" verrà sostituito dal numero di pagina.
## Passaggio 3: ottieni il flusso di documenti
```csharp
Stream stream = GetFileStream();
```
Ottieni il flusso di documenti dalla fonte desiderata. Potrebbe trattarsi di un flusso di file, di memoria o di qualsiasi altro flusso compatibile.
## Passaggio 4: caricare il documento utilizzando il visualizzatore
```csharp
using (Viewer viewer = new Viewer(stream)) 
{
    HtmlViewOptions options = HtmlViewOptions.ForEmbeddedResources(pageFilePathFormat);
    
    viewer.View(options);
}
```
Inizializza una nuova istanza della classe Viewer con il flusso di documenti. Quindi, configura le opzioni di visualizzazione HTML ed esegui il rendering del documento.
## Passaggio 5: Visualizza la directory di output
```csharp
Console.WriteLine($"\nSource document rendered successfully.\nCheck output in {outputDirectory}.");
```
Informare l'utente del rendering riuscito del documento e fornire la posizione in cui viene salvato l'output.

## Conclusione
In conclusione, GroupDocs.Viewer per .NET offre una soluzione solida per caricare e visualizzare documenti dai flussi senza sforzo. Seguendo i passaggi descritti in questo tutorial, puoi integrare perfettamente le funzionalità di visualizzazione dei documenti nelle tue applicazioni .NET, migliorando l'esperienza utente e la produttività.
## Domande frequenti
### GroupDocs.Viewer per .NET può gestire diversi formati di documenti?
Sì, GroupDocs.Viewer supporta un'ampia gamma di formati di documenti, inclusi PDF, DOCX, XLSX, PPTX e altri.
### GroupDocs.Viewer per .NET è adatto sia per applicazioni Web che desktop?
Assolutamente! GroupDocs.Viewer può essere perfettamente integrato nelle applicazioni Web e desktop sviluppate utilizzando .NET.
### GroupDocs.Viewer offre opzioni di personalizzazione per il rendering dei documenti?
Sì, puoi personalizzare vari aspetti del rendering del documento, come filigrana, rotazione della pagina e livello di zoom, in base alle tue esigenze.
### Posso utilizzare GroupDocs.Viewer for .NET in progetti commerciali?
Sì, GroupDocs.Viewer offre opzioni di licenza adatte a progetti commerciali. È possibile acquistare le licenze dal funzionario[sito web](https://purchase.groupdocs.com/temporary-license/).
### È disponibile supporto tecnico per GroupDocs.Viewer per .NET?
 Sì, puoi chiedere assistenza tecnica e guida al forum di supporto dedicato fornito da[GroupDocs.Viewer](https://forum.groupdocs.com/c/viewer/9).