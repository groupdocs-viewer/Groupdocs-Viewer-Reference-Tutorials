---
title: Carica documenti dal disco locale
linktitle: Carica documenti dal disco locale
second_title: API GroupDocs.Viewer .NET
description: Scopri come eseguire il rendering dei documenti senza problemi dal disco locale utilizzando Groupdocs.Viewer per .NET. Migliora le tue applicazioni .NET con documenti efficienti.
weight: 10
url: /it/net/loading-documents/loading-document-local-disk/
---

# Carica documenti dal disco locale

## introduzione
Nell'era digitale di oggi, un rendering efficiente dei documenti è essenziale per varie applicazioni. Groupdocs.Viewer per .NET offre una potente soluzione per il rendering di documenti direttamente dal tuo disco locale. In questo tutorial ti guideremo attraverso il processo di caricamento dei documenti dal tuo disco locale utilizzando Groupdocs.Viewer per .NET. Che tu sia uno sviluppatore esperto o che tu abbia appena iniziato, questa guida passo passo ti aiuterà a integrare perfettamente il rendering dei documenti nelle tue applicazioni .NET.
## Prerequisiti
Prima di immergerti nel tutorial, assicurati di possedere i seguenti prerequisiti:
1.  Groupdocs.Viewer per .NET: scarica e installa la versione più recente da[Qui](https://releases.groupdocs.com/viewer/net/).
2. Ambiente di sviluppo .NET: assicurati di avere un ambiente di sviluppo .NET funzionante configurato sul tuo sistema.
3. Documenti locali: i documenti di cui desideri eseguire il rendering vengono archiviati localmente sul tuo disco.

## Importa spazi dei nomi
Innanzitutto, importiamo gli spazi dei nomi necessari per accedere alle funzionalità di Groupdocs.Viewer per .NET.
```csharp
using System;
using System.IO;
using GroupDocs.Viewer.Options;
```
## Passaggio 1: caricare i documenti dal disco locale
Inizia impostando la directory di output in cui verranno salvate le pagine HTML renderizzate.
```csharp
string outputDirectory = "Your Document Directory";
string pageFilePathFormat = Path.Combine(outputDirectory, "page_{0}.html");
```
## Passaggio 2: inizializza il visualizzatore e i documenti di rendering
Inizializza l'oggetto Viewer con il percorso del documento ed eseguine il rendering utilizzando le opzioni di visualizzazione HTML.
```csharp
using (Viewer viewer = new Viewer("Path_to_Your_Document"))
{
    HtmlViewOptions options = HtmlViewOptions.ForEmbeddedResources(pageFilePathFormat);
    viewer.View(options);
}
```
## Passaggio 3: Visualizza l'output
Una volta completato il rendering, visualizza un messaggio che indica il rendering riuscito del documento sorgente e la posizione dei file di output.
```csharp
Console.WriteLine($"\nSource document rendered successfully.\nCheck output in {outputDirectory}.");
```

## Conclusione
Congratulazioni! Hai imparato con successo come caricare documenti dal tuo disco locale utilizzando Groupdocs.Viewer per .NET. Questo potente strumento apre un mondo di possibilità per il rendering dei documenti all'interno delle tue applicazioni .NET.
## Domande frequenti
### Posso eseguire il rendering di documenti di formati diversi utilizzando Groupdocs.Viewer per .NET?
Sì, Groupdocs.Viewer per .NET supporta un'ampia gamma di formati di documenti tra cui DOCX, PDF, XLSX, PPTX e altri.
### Groupdocs.Viewer per .NET è compatibile con tutti i framework .NET?
Groupdocs.Viewer per .NET è compatibile con la maggior parte dei framework .NET, inclusi .NET Core, .NET Framework e .NET Standard.
### Posso personalizzare le opzioni di rendering per i miei documenti?
Assolutamente! Groupdocs.Viewer per .NET fornisce ampie opzioni di personalizzazione che ti consentono di adattare il processo di rendering alle tue esigenze specifiche.
### È disponibile una versione di prova per Groupdocs.Viewer per .NET?
Sì, puoi scaricare una versione di prova gratuita da[Qui](https://releases.groupdocs.com/).
### Dove posso trovare supporto o risorse aggiuntive per Groupdocs.Viewer per .NET?
 Per supporto e risorse aggiuntive, visitare Groupdocs.Viewer per .NET[Forum](https://forum.groupdocs.com/c/viewer/9).