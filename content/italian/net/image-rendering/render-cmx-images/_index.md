---
title: Rendering di immagini CMX
linktitle: Rendering di immagini CMX
second_title: API GroupDocs.Viewer .NET
description: Scopri come eseguire facilmente il rendering delle immagini CMX in vari formati utilizzando GroupDocs.Viewer per .NET. Migliora la gestione dei tuoi documenti.
type: docs
weight: 13
url: /it/net/image-rendering/render-cmx-images/
---
## introduzione
Nell'ambito della gestione e manipolazione dei documenti, il rendering di immagini di vari formati è un compito fondamentale. GroupDocs.Viewer per .NET semplifica questo processo fornendo funzionalità complete per il rendering di immagini CMX in diversi formati come HTML, JPG, PNG e PDF. Questo tutorial ti guiderà attraverso il processo passo passo di rendering delle immagini CMX utilizzando GroupDocs.Viewer per .NET.
## Prerequisiti
Prima di immergerti nel tutorial, assicurati di disporre dei seguenti prerequisiti:
1.  Libreria GroupDocs.Viewer per .NET: scaricare e installare la libreria GroupDocs.Viewer per .NET da[Qui](https://releases.groupdocs.com/viewer/net/).
2. Ambiente di sviluppo: disporre di un ambiente di sviluppo funzionante configurato con .NET framework.
3. File immagine CMX: ottieni un file immagine CMX di cui desideri eseguire il rendering.

## Importazione di spazi dei nomi
Prima di procedere, assicurati di importare gli spazi dei nomi necessari per accedere alle funzionalità GroupDocs.Viewer nella tua applicazione .NET:
```csharp
using GroupDocs.Viewer.Options;
using System;
using System.IO;
```

## Rendering in HTML
```csharp
string outputDirectory = "Your Document Directory";
string pageFilePathFormat = Path.Combine(outputDirectory, "cmx_result_{0}.html");
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_CMX))
{
    HtmlViewOptions options = HtmlViewOptions.ForEmbeddedResources(pageFilePathFormat);
    viewer.View(options);
}
```
- Definisci directory di output: imposta la directory in cui desideri archiviare i file HTML renderizzati.
- Specifica il formato del percorso file: definisce il formato per i file HTML di output.
- Istanzia l'oggetto Viewer: crea un'istanza della classe Viewer con il file immagine CMX.
- Opzioni di rendering HTML: configura le opzioni di rendering HTML, come l'incorporamento di risorse.
- Render CMX in HTML: richiamare il metodo View dell'oggetto visualizzatore per eseguire il rendering dell'immagine CMX in HTML.
## Rendering in JPG
```csharp
string pageFilePathFormat = Path.Combine(outputDirectory, "cmx_result_{0}.jpg");
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_CMX))
{
    JpgViewOptions options = new JpgViewOptions(pageFilePathFormat);
    
    viewer.View(options);
}
```
- Definisci directory di output: imposta la directory per archiviare i file JPG renderizzati.
- Specifica il formato del percorso file: definire il formato per i file JPG di output.
- Istanzia l'oggetto Viewer: crea un'istanza della classe Viewer con il file immagine CMX.
- Opzioni di rendering JPG: configura le opzioni di rendering JPG.
- Render CMX in JPG: richiama il metodo View dell'oggetto visualizzatore per eseguire il rendering dell'immagine CMX in JPG.
## Rendering in PNG
```csharp
string pageFilePathFormat = Path.Combine(outputDirectory, "cmx_result_{0}.png");
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_CMX))
{
    PngViewOptions options = new PngViewOptions(pageFilePathFormat);
   
    viewer.View(options);
}
```
- Definisci directory di output: imposta la directory per l'archiviazione dei file PNG renderizzati.
- Specifica il formato del percorso file: definisce il formato per i file PNG di output.
- Istanzia l'oggetto Viewer: crea un'istanza della classe Viewer con il file immagine CMX.
- Opzioni di rendering PNG: configura le opzioni di rendering PNG.
- Rendering di CMX in PNG: richiama il metodo View dell'oggetto visualizzatore per eseguire il rendering dell'immagine CMX in PNG.
## Rendering in PDF
```csharp
string pageFilePathFormat = Path.Combine(outputDirectory, "cmx_result.pdf");
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_CMX))
{
    PdfViewOptions options = new PdfViewOptions(pageFilePathFormat);
   
    viewer.View(options);
}
```
- Definisci directory di output: imposta la directory per l'archiviazione del file PDF renderizzato.
- Specifica il formato del percorso file: definire il formato per il file PDF di output.
- Istanzia l'oggetto Viewer: crea un'istanza della classe Viewer con il file immagine CMX.
- Opzioni di rendering PDF: configura le opzioni di rendering PDF.
- Render CMX in PDF: richiamare il metodo View dell'oggetto visualizzatore per eseguire il rendering dell'immagine CMX in PDF.

## Conclusione
In conclusione, GroupDocs.Viewer per .NET offre una soluzione solida per il rendering di immagini CMX in vari formati senza problemi. Seguendo i passaggi descritti in questo tutorial, puoi integrare facilmente le funzionalità di rendering delle immagini CMX nelle tue applicazioni .NET, migliorando l'efficienza della gestione dei documenti.
## Domande frequenti
### Posso eseguire il rendering di pagine specifiche di un'immagine CMX?
Sì, puoi eseguire il rendering di pagine specifiche specificando il numero di pagina nelle opzioni di rendering.
### GroupDocs.Viewer per .NET è compatibile con tutti i framework .NET?
Sì, GroupDocs.Viewer per .NET è compatibile con più framework .NET, inclusi .NET Core e .NET Framework.
### GroupDocs.Viewer supporta il rendering di immagini CMX crittografate?
Sì, GroupDocs.Viewer supporta il rendering di immagini CMX crittografate con chiavi di decrittografia appropriate.
### Posso personalizzare le opzioni di rendering per diversi formati di output?
Assolutamente sì, GroupDocs.Viewer offre ampie opzioni per personalizzare i parametri di rendering in base alle vostre esigenze.
### Esiste un forum della community per il supporto di GroupDocs.Viewer?
 Sì, puoi chiedere assistenza e interagire con la community GroupDocs.Viewer sul forum di supporto[Qui](https://forum.groupdocs.com/c/viewer/9).