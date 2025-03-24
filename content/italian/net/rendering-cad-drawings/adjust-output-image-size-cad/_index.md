---
title: Regola le dimensioni dell'immagine di output per i disegni CAD
linktitle: Regola le dimensioni dell'immagine di output per i disegni CAD
second_title: API GroupDocs.Viewer .NET
description: Scopri come regolare le dimensioni dell'immagine di output per i disegni CAD utilizzando GroupDocs.Viewer per .NET. Migliora la visibilità e l'usabilità senza sforzo.
weight: 15
url: /it/net/rendering-cad-drawings/adjust-output-image-size-cad/
---

# Regola le dimensioni dell'immagine di output per i disegni CAD

## introduzione
I disegni CAD spesso richiedono regolazioni specifiche per una visualizzazione e una presentazione ottimali. GroupDocs.Viewer per .NET fornisce un potente set di strumenti per gestire e personalizzare l'output dei disegni CAD. In questo tutorial ti guideremo passo dopo passo attraverso il processo di regolazione delle dimensioni dell'immagine di output per i disegni CAD.
## Prerequisiti
Prima di iniziare, assicurati di possedere i seguenti prerequisiti:
1.  GroupDocs.Viewer per .NET: scarica e installa GroupDocs.Viewer per .NET da[Qui](https://releases.groupdocs.com/viewer/net/).
2. Directory dei documenti: prepara la directory in cui si trova il tuo documento.
3. Comprensione di base: acquisire familiarità con i concetti di base della programmazione .NET.

## Importa spazi dei nomi
Innanzitutto, assicurati di importare gli spazi dei nomi necessari per accedere alle funzionalità GroupDocs.Viewer:
```csharp
using System;
using System.IO;
using GroupDocs.Viewer.Options;
```
## Passaggio 1: imposta la directory di output
Definisci la directory in cui desideri archiviare le immagini di output dei disegni CAD:
```csharp
string outputDirectory = "Your Document Directory";
```
## Passaggio 2: definire il formato del percorso del file di paging
Imposta il formato per i percorsi dei file di paging. Questo formato verrà utilizzato per denominare e salvare singole pagine come file HTML:
```csharp
string pageFilePathFormat = Path.Combine(outputDirectory, "page_{0}.html");
```
## Passaggio 3: regola le dimensioni dell'immagine
All'interno di un blocco using per l'oggetto Visualizzatore, regola la dimensione dell'immagine per i disegni CAD impostando le opzioni appropriate:
```csharp
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_DWG_WITH_LAYOUTS_AND_LAYERS))
{
    HtmlViewOptions options = HtmlViewOptions.ForEmbeddedResources(pageFilePathFormat);
    options.CadOptions = CadOptions.ForRenderingByScaleFactor(0.5f);
    
    viewer.View(options);
}
```
## Passaggio 4: Visualizza la directory di output
Dopo aver eseguito il rendering del documento, visualizza un messaggio che indica l'avvenuto rendering e fornisci la posizione della directory di output:
```csharp
Console.WriteLine($"\nSource document rendered successfully.\nCheck output in {outputDirectory}.");
```

## Conclusione
La regolazione delle dimensioni dell'immagine di output per i disegni CAD è fondamentale per migliorarne la visibilità e l'usabilità. Con GroupDocs.Viewer per .NET, questo processo diventa snello ed efficiente, consentendoti di personalizzare l'output in base alle tue esigenze specifiche.
## Domande frequenti
### Posso regolare le dimensioni dell'immagine di output per altri tipi di documenti oltre ai disegni CAD?
Sì, GroupDocs.Viewer per .NET supporta vari tipi di documenti ed è possibile regolare le dimensioni dell'immagine di output per la maggior parte dei formati di documenti.
### GroupDocs.Viewer for .NET è compatibile con diverse versioni del framework .NET?
Sì, GroupDocs.Viewer per .NET è compatibile con più versioni del framework .NET, garantendo flessibilità e usabilità in ambienti diversi.
### Sono disponibili opzioni di licenza per GroupDocs.Viewer per .NET?
Sì, puoi esplorare diverse opzioni di licenza, comprese licenze temporanee e licenze commerciali, in base alle tue esigenze.
### Posso personalizzare il formato di output dei documenti renderizzati?
Assolutamente sì, GroupDocs.Viewer per .NET offre varie opzioni di personalizzazione, permettendoti di personalizzare il formato di output in base alle tue preferenze.
### Dove posso trovare ulteriore supporto o assistenza con GroupDocs.Viewer per .NET?
 È possibile visitare il forum GroupDocs.Viewer[Qui](https://forum.groupdocs.com/c/viewer/9) per ottenere supporto, porre domande e interagire con la comunità.