---
"description": "Scopri come visualizzare documenti dal tuo disco locale in modo fluido utilizzando Groupdocs.Viewer per .NET. Migliora le tue applicazioni .NET con un'elaborazione efficiente dei documenti."
"linktitle": "Carica documenti dal disco locale"
"second_title": "API .NET di GroupDocs.Viewer"
"title": "Carica documenti dal disco locale"
"url": "/it/net/loading-documents/loading-document-local-disk/"
"weight": 10
---

# Carica documenti dal disco locale

## Introduzione
Nell'era digitale odierna, un rendering efficiente dei documenti è essenziale per diverse applicazioni. Groupdocs.Viewer per .NET offre una soluzione potente per il rendering dei documenti direttamente dal disco locale. In questo tutorial, ti guideremo attraverso il processo di caricamento dei documenti dal disco locale utilizzando Groupdocs.Viewer per .NET. Che tu sia uno sviluppatore esperto o alle prime armi, questa guida passo passo ti aiuterà a integrare perfettamente il rendering dei documenti nelle tue applicazioni .NET.

![Carica documenti dal disco locale con GroupDocs.Viewer .NET](/viewer/loading-documents/load-documents-from-local-disk.png)

## Prerequisiti
Prima di immergerti nel tutorial, assicurati di avere i seguenti prerequisiti:
1. Groupdocs.Viewer per .NET: Scarica e installa l'ultima versione da [Qui](https://releases.groupdocs.com/viewer/net/).
2. Ambiente di sviluppo .NET: assicurati di avere un ambiente di sviluppo .NET funzionante installato sul tuo sistema.
3. Documenti locali: memorizza localmente sul tuo disco i documenti che vuoi riprodurre.

## Importa spazi dei nomi
Per prima cosa, importiamo gli spazi dei nomi necessari per accedere alle funzionalità di Groupdocs.Viewer per .NET.
```csharp
using System;
using System.IO;
using GroupDocs.Viewer.Options;
```
## Passaggio 1: caricare i documenti dal disco locale
Per prima cosa, imposta la directory di output in cui verranno salvate le pagine HTML renderizzate.
```csharp
string outputDirectory = "Your Document Directory";
string pageFilePathFormat = Path.Combine(outputDirectory, "page_{0}.html");
```
## Passaggio 2: inizializzare il visualizzatore e visualizzare i documenti
Inizializza l'oggetto Viewer con il percorso del documento ed esegui il rendering utilizzando le opzioni di visualizzazione HTML.
```csharp
using (Viewer viewer = new Viewer("Path_to_Your_Document"))
{
    HtmlViewOptions options = HtmlViewOptions.ForEmbeddedResources(pageFilePathFormat);
    viewer.View(options);
}
```
## Passaggio 3: Visualizza l'output
Una volta completato il rendering, viene visualizzato un messaggio che indica l'avvenuto rendering del documento sorgente e la posizione dei file di output.
```csharp
Console.WriteLine($"\nSource document rendered successfully.\nCheck output in {outputDirectory}.");
```

## Conclusione
Congratulazioni! Hai imparato a caricare documenti dal tuo disco locale utilizzando Groupdocs.Viewer per .NET. Questo potente strumento apre un mondo di possibilità per il rendering dei documenti nelle tue applicazioni .NET.
## Domande frequenti
### Posso visualizzare documenti di formati diversi utilizzando Groupdocs.Viewer per .NET?
Sì, Groupdocs.Viewer per .NET supporta un'ampia gamma di formati di documenti, tra cui DOCX, PDF, XLSX, PPTX e altri.
### Groupdocs.Viewer per .NET è compatibile con tutti i framework .NET?
Groupdocs.Viewer per .NET è compatibile con la maggior parte dei framework .NET, tra cui .NET Core, .NET Framework e .NET Standard.
### Posso personalizzare le opzioni di rendering dei miei documenti?
Assolutamente sì! Groupdocs.Viewer per .NET offre ampie opzioni di personalizzazione che consentono di adattare il processo di rendering alle proprie esigenze specifiche.
### Esiste una versione di prova disponibile per Groupdocs.Viewer per .NET?
Sì, puoi scaricare una versione di prova gratuita da [Qui](https://releases.groupdocs.com/).
### Dove posso trovare supporto o risorse aggiuntive per Groupdocs.Viewer per .NET?
Per supporto e risorse aggiuntive, visita Groupdocs.Viewer per .NET [foro](https://forum.groupdocs.com/c/viewer/9).