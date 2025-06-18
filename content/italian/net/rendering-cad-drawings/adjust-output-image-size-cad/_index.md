---
"description": "Scopri come regolare le dimensioni delle immagini di output per i disegni CAD utilizzando GroupDocs.Viewer per .NET. Migliora visibilità e usabilità senza sforzo."
"linktitle": "Regola le dimensioni dell'immagine di output per i disegni CAD"
"second_title": "API .NET di GroupDocs.Viewer"
"title": "Regola le dimensioni dell'immagine di output per i disegni CAD"
"url": "/it/net/rendering-cad-drawings/adjust-output-image-size-cad/"
"weight": 15
---

# Regola le dimensioni dell'immagine di output per i disegni CAD

## Introduzione
disegni CAD richiedono spesso regolazioni specifiche per una visualizzazione e una presentazione ottimali. GroupDocs.Viewer per .NET offre un potente set di strumenti per gestire e personalizzare l'output dei disegni CAD. In questo tutorial, vi guideremo passo dopo passo attraverso il processo di regolazione delle dimensioni delle immagini di output per i disegni CAD.
## Prerequisiti
Prima di iniziare, assicurati di disporre dei seguenti prerequisiti:
1. GroupDocs.Viewer per .NET: Scarica e installa GroupDocs.Viewer per .NET da [Qui](https://releases.groupdocs.com/viewer/net/).
2. Directory dei documenti: prepara la directory in cui si trova il documento.
3. Nozioni di base: acquisire familiarità con i concetti di base della programmazione .NET.

## Importa spazi dei nomi
Per prima cosa, assicurati di importare gli spazi dei nomi necessari per accedere alle funzionalità di GroupDocs.Viewer:
```csharp
using System;
using System.IO;
using GroupDocs.Viewer.Options;
```
## Passaggio 1: impostare la directory di output
Definisci la directory in cui desideri memorizzare le immagini di output dei disegni CAD:
```csharp
string outputDirectory = "Your Document Directory";
```
## Passaggio 2: definire il formato del percorso del file di paging
Imposta il formato per i percorsi dei file di paging. Questo formato verrà utilizzato per denominare e salvare le singole pagine come file HTML:
```csharp
string pageFilePathFormat = Path.Combine(outputDirectory, "page_{0}.html");
```
## Passaggio 3: regola le dimensioni dell'immagine
All'interno di un blocco di utilizzo per l'oggetto Visualizzatore, regola le dimensioni dell'immagine per i disegni CAD impostando le opzioni appropriate:
```csharp
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_DWG_WITH_LAYOUTS_AND_LAYERS))
{
    HtmlViewOptions options = HtmlViewOptions.ForEmbeddedResources(pageFilePathFormat);
    options.CadOptions = CadOptions.ForRenderingByScaleFactor(0.5f);
    
    viewer.View(options);
}
```
## Passaggio 4: visualizzare la directory di output
Dopo aver eseguito il rendering del documento, visualizza un messaggio che indica l'avvenuto rendering e specifica il percorso della directory di output:
```csharp
Console.WriteLine($"\nSource document rendered successfully.\nCheck output in {outputDirectory}.");
```

## Conclusione
Regolare le dimensioni dell'immagine di output per i disegni CAD è fondamentale per migliorarne la visibilità e l'usabilità. Con GroupDocs.Viewer per .NET, questo processo diventa snello ed efficiente, consentendo di personalizzare l'output in base alle proprie esigenze specifiche.
## Domande frequenti
### Posso regolare le dimensioni dell'immagine di output per altri tipi di documenti oltre ai disegni CAD?
Sì, GroupDocs.Viewer per .NET supporta vari tipi di documenti ed è possibile regolare le dimensioni dell'immagine di output per la maggior parte dei formati di documento.
### GroupDocs.Viewer per .NET è compatibile con le diverse versioni del framework .NET?
Sì, GroupDocs.Viewer per .NET è compatibile con più versioni del framework .NET, garantendo flessibilità e usabilità in diversi ambienti.
### Sono disponibili opzioni di licenza per GroupDocs.Viewer per .NET?
Sì, puoi valutare diverse opzioni di licenza, tra cui licenze temporanee e licenze commerciali, in base alle tue esigenze.
### Posso personalizzare il formato di output dei documenti renderizzati?
Certamente, GroupDocs.Viewer per .NET offre diverse opzioni di personalizzazione, consentendoti di adattare il formato di output in base alle tue esigenze.
### Dove posso trovare ulteriore supporto o assistenza per GroupDocs.Viewer per .NET?
Puoi visitare il forum GroupDocs.Viewer [Qui](https://forum.groupdocs.com/c/viewer/9) per ottenere supporto, porre domande e interagire con la community.