---
title: Rendering di layout singoli nei disegni CAD
linktitle: Rendering di layout singoli nei disegni CAD
second_title: API GroupDocs.Viewer .NET
description: Scopri come eseguire il rendering di layout singoli nei disegni CAD utilizzando GroupDocs.Viewer per .NET. Semplici passaggi per un'integrazione perfetta nelle tue applicazioni .NET.
weight: 14
url: /it/net/rendering-cad-drawings/render-single-layout-cad/
---
## introduzione
Nell'ambito dello sviluppo .NET, la gestione e la visualizzazione dei disegni CAD è un requisito comune. GroupDocs.Viewer per .NET semplifica questa attività fornendo una soluzione completa per il rendering di disegni CAD all'interno delle applicazioni .NET. In questo tutorial approfondiremo il rendering di un singolo layout nei disegni CAD utilizzando GroupDocs.Viewer per .NET.
## Prerequisiti
Prima di immergerti nel tutorial, assicurati di possedere i seguenti prerequisiti:
- Conoscenza di base del linguaggio di programmazione C# e del framework .NET.
- Visual Studio installato nel sistema.
-  Libreria GroupDocs.Viewer per .NET scaricata e a cui si fa riferimento nel progetto. Puoi scaricarlo da[Qui](https://releases.groupdocs.com/viewer/net/).
- Familiarità con i formati di file CAD e le loro strutture.

## Importa spazi dei nomi
Innanzitutto, importa gli spazi dei nomi necessari nel codice C# per accedere alle funzionalità GroupDocs.Viewer.

```csharp
using System;
using System.IO;
using GroupDocs.Viewer.Options;
```

## Passaggio 1: definire la directory di output
Specifica la directory in cui desideri salvare l'output renderizzato.
```csharp
string outputDirectory = "Your Document Directory";
```
## Passaggio 2: definire il formato del percorso del file di paging
Definire il formato per il percorso del file di ciascuna pagina sottoposta a rendering.
```csharp
string pageFilePathFormat = Path.Combine(outputDirectory, "page_{0}.html");
```
## Passaggio 3: istanziare l'oggetto visualizzatore
Crea un'istanza della classe Viewer fornita da GroupDocs.Viewer.
```csharp
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_DWG_WITH_LAYOUTS_AND_LAYERS))
```
## Passaggio 4: configura le opzioni di visualizzazione HTML
Configura le opzioni per il rendering dell'output HTML con risorse incorporate.
```csharp
HtmlViewOptions options = HtmlViewOptions.ForEmbeddedResources(pageFilePathFormat);
```
## Passaggio 5: specificare il nome del layout CAD
Specifica il nome del layout CAD di cui desideri eseguire il rendering.
```csharp
options.CadOptions.LayoutName = "Model";
```
## Passaggio 6: rendering del disegno CAD
Richiamare il metodo View dell'oggetto Viewer con le opzioni specificate.
```csharp
viewer.View(options);
```
## Passaggio 7: Visualizza il messaggio di successo
Informare l'utente del rendering riuscito del documento sorgente.
```csharp
Console.WriteLine($"\nSource document rendered successfully.\nCheck output in {outputDirectory}.");
```

## Conclusione
Il rendering dei disegni CAD, soprattutto quando si ha a che fare con i layout, può essere un compito arduo. Tuttavia, con GroupDocs.Viewer per .NET, il processo diventa semplice ed efficiente. Seguendo i passaggi descritti in questo tutorial, puoi eseguire facilmente il rendering di un singolo layout nei disegni CAD all'interno delle tue applicazioni .NET.
## Domande frequenti
### Posso eseguire il rendering di più layout contemporaneamente utilizzando GroupDocs.Viewer per .NET?
Sì, GroupDocs.Viewer per .NET supporta il rendering di più layout da disegni CAD.
### GroupDocs.Viewer è compatibile con diversi formati di file CAD?
Assolutamente, GroupDocs.Viewer supporta un'ampia gamma di formati di file CAD, inclusi DWG, DXF, DGN e altri.
### Posso personalizzare le opzioni di rendering per i disegni CAD?
Sì, GroupDocs.Viewer fornisce ampie opzioni per personalizzare le impostazioni di rendering in base alle tue esigenze.
### È disponibile una prova gratuita per GroupDocs.Viewer per .NET?
 Sì, puoi esplorare le funzionalità di GroupDocs.Viewer con una prova gratuita disponibile[Qui](https://releases.groupdocs.com/).
### Dove posso ottenere supporto per GroupDocs.Viewer per .NET?
 Per qualsiasi domanda o assistenza, puoi visitare il forum GroupDocs.Viewer[Qui](https://forum.groupdocs.com/c/viewer/9).