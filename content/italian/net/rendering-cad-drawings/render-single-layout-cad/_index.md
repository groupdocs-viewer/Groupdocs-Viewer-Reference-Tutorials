---
"description": "Scopri come eseguire il rendering di un singolo layout nei disegni CAD utilizzando GroupDocs.Viewer per .NET. Semplici passaggi per una perfetta integrazione nelle tue applicazioni .NET."
"linktitle": "Rendering di layout singoli in disegni CAD"
"second_title": "API .NET di GroupDocs.Viewer"
"title": "Rendering di layout singoli in disegni CAD"
"url": "/it/net/rendering-cad-drawings/render-single-layout-cad/"
"weight": 14
---

# Rendering di layout singoli in disegni CAD

## Introduzione
Nell'ambito dello sviluppo .NET, la gestione e la visualizzazione di disegni CAD è un'esigenza comune. GroupDocs.Viewer per .NET semplifica questa attività offrendo una soluzione completa per il rendering di disegni CAD all'interno di applicazioni .NET. In questo tutorial, approfondiremo il rendering di un singolo layout nei disegni CAD utilizzando GroupDocs.Viewer per .NET.
## Prerequisiti
Prima di immergerti nel tutorial, assicurati di avere i seguenti prerequisiti:
- Conoscenza di base del linguaggio di programmazione C# e del framework .NET.
- Visual Studio installato sul sistema.
- Scarica la libreria GroupDocs.Viewer per .NET e inserisci i tutorial nel tuo progetto. Puoi scaricarlo da [Qui](https://releases.groupdocs.com/viewer/net/).
- Familiarità con i formati di file CAD e le loro strutture.

## Importa spazi dei nomi
Per prima cosa, importa gli spazi dei nomi necessari nel codice C# per accedere alle funzionalità di GroupDocs.Viewer.

```csharp
using System;
using System.IO;
using GroupDocs.Viewer.Options;
```

## Passaggio 1: definire la directory di output
Specificare la directory in cui si desidera salvare l'output renderizzato.
```csharp
string outputDirectory = "Your Document Directory";
```
## Passaggio 2: definire il formato del percorso del file di paging
Definisci il formato per il percorso del file di ogni pagina renderizzata.
```csharp
string pageFilePathFormat = Path.Combine(outputDirectory, "page_{0}.html");
```
## Passaggio 3: creare un'istanza dell'oggetto Viewer
Creare un'istanza della classe Viewer fornita da GroupDocs.Viewer.
```csharp
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_DWG_WITH_LAYOUTS_AND_LAYERS))
```
## Passaggio 4: configurare le opzioni di visualizzazione HTML
Configura le opzioni per il rendering dell'output HTML con risorse incorporate.
```csharp
HtmlViewOptions options = HtmlViewOptions.ForEmbeddedResources(pageFilePathFormat);
```
## Passaggio 5: specificare il nome del layout CAD
Specificare il nome del layout CAD che si desidera eseguire il rendering.
```csharp
options.CadOptions.LayoutName = "Model";
```
## Passaggio 6: rendering del disegno CAD
Richiama il metodo View dell'oggetto Viewer con le opzioni specificate.
```csharp
viewer.View(options);
```
## Passaggio 7: visualizzare il messaggio di successo
Informare l'utente dell'avvenuto rendering del documento sorgente.
```csharp
Console.WriteLine($"\nSource document rendered successfully.\nCheck output in {outputDirectory}.");
```

## Conclusione
Il rendering di disegni CAD, soprattutto quando si tratta di layout, può essere un compito arduo. Tuttavia, con GroupDocs.Viewer per .NET, il processo diventa fluido ed efficiente. Seguendo i passaggi descritti in questo tutorial, è possibile eseguire senza problemi il rendering di un singolo layout nei disegni CAD all'interno delle applicazioni .NET.
## Domande frequenti
### Posso eseguire il rendering di più layout contemporaneamente utilizzando GroupDocs.Viewer per .NET?
Sì, GroupDocs.Viewer per .NET supporta il rendering di più layout da disegni CAD.
### GroupDocs.Viewer è compatibile con diversi formati di file CAD?
Certamente, GroupDocs.Viewer supporta un'ampia gamma di formati di file CAD, tra cui DWG, DXF, DGN e altri ancora.
### Posso personalizzare le opzioni di rendering per i disegni CAD?
Sì, GroupDocs.Viewer offre ampie opzioni per personalizzare le impostazioni di rendering in base alle proprie esigenze.
### È disponibile una versione di prova gratuita di GroupDocs.Viewer per .NET?
Sì, puoi esplorare le funzionalità di GroupDocs.Viewer con una prova gratuita disponibile [Qui](https://releases.groupdocs.com/).
### Dove posso ottenere supporto per GroupDocs.Viewer per .NET?
Per qualsiasi domanda o assistenza, puoi visitare il forum GroupDocs.Viewer [Qui](https://forum.groupdocs.com/c/viewer/9).