---
"description": "Scopri come convertire facilmente le immagini CMX in vari formati utilizzando GroupDocs.Viewer per .NET. Migliora la gestione dei tuoi documenti."
"linktitle": "Rendering di immagini CMX"
"second_title": "API .NET di GroupDocs.Viewer"
"title": "Rendering di immagini CMX"
"url": "/it/net/image-rendering/render-cmx-images/"
"weight": 13
---

# Rendering di immagini CMX

## Introduzione
Nell'ambito della gestione e manipolazione dei documenti, il rendering di immagini da diversi formati è un'attività fondamentale. GroupDocs.Viewer per .NET semplifica questo processo offrendo funzionalità complete per il rendering di immagini CMX in diversi formati come HTML, JPG, PNG e PDF. Questo tutorial vi guiderà passo dopo passo attraverso il processo di rendering di immagini CMX utilizzando GroupDocs.Viewer per .NET.

![Rendering di immagini CMX con GroupDocs.Viewer per .NET](/viewer/image-rendering/render-cmx-images.png)

## Prerequisiti
Prima di immergerti nel tutorial, assicurati di avere i seguenti prerequisiti:
1. Libreria GroupDocs.Viewer per .NET: Scarica e installa la libreria GroupDocs.Viewer per .NET da [Qui](https://releases.groupdocs.com/viewer/net/).
2. Ambiente di sviluppo: disporre di un ambiente di sviluppo funzionante configurato con .NET Framework.
3. File immagine CMX: ottieni un file immagine CMX che desideri elaborare.

## Importazione di spazi dei nomi
Prima di procedere, assicurati di importare gli spazi dei nomi necessari per accedere alle funzionalità di GroupDocs.Viewer nella tua applicazione .NET:
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
- Specifica il formato del percorso del file: definisce il formato per i file HTML di output.
- Crea un'istanza dell'oggetto Viewer: crea un'istanza della classe Viewer con il file immagine CMX.
- Opzioni di rendering HTML: configura le opzioni di rendering HTML, come l'incorporamento di risorse.
- Esegui il rendering di CMX in HTML: richiama il metodo View dell'oggetto viewer per eseguire il rendering dell'immagine CMX in HTML.
## Rendering in JPG
```csharp
string pageFilePathFormat = Path.Combine(outputDirectory, "cmx_result_{0}.jpg");
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_CMX))
{
    JpgViewOptions options = new JpgViewOptions(pageFilePathFormat);
    
    viewer.View(options);
}
```
- Definisci directory di output: imposta la directory in cui archiviare i file JPG renderizzati.
- Specifica il formato del percorso del file: definisce il formato per i file JPG di output.
- Crea un'istanza dell'oggetto Viewer: crea un'istanza della classe Viewer con il file immagine CMX.
- Opzioni di rendering JPG: configura le opzioni di rendering JPG.
- Rendering CMX in JPG: richiama il metodo View dell'oggetto viewer per eseguire il rendering dell'immagine CMX in JPG.
## Rendering in PNG
```csharp
string pageFilePathFormat = Path.Combine(outputDirectory, "cmx_result_{0}.png");
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_CMX))
{
    PngViewOptions options = new PngViewOptions(pageFilePathFormat);
   
    viewer.View(options);
}
```
- Definisci directory di output: imposta la directory in cui archiviare i file PNG renderizzati.
- Specifica il formato del percorso del file: definisce il formato per i file PNG di output.
- Crea un'istanza dell'oggetto Viewer: crea un'istanza della classe Viewer con il file immagine CMX.
- Opzioni di rendering PNG: configura le opzioni di rendering PNG.
- Converti CMX in PNG: richiama il metodo View dell'oggetto viewer per convertire l'immagine CMX in PNG.
## Rendering in PDF
```csharp
string pageFilePathFormat = Path.Combine(outputDirectory, "cmx_result.pdf");
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_CMX))
{
    PdfViewOptions options = new PdfViewOptions(pageFilePathFormat);
   
    viewer.View(options);
}
```
- Definisci directory di output: imposta la directory in cui archiviare il file PDF elaborato.
- Specificare il formato del percorso del file: definire il formato per il file PDF di output.
- Crea un'istanza dell'oggetto Viewer: crea un'istanza della classe Viewer con il file immagine CMX.
- Opzioni di rendering PDF: configura le opzioni di rendering PDF.
- Esegui il rendering di CMX in PDF: richiama il metodo View dell'oggetto viewer per eseguire il rendering dell'immagine CMX in PDF.

## Conclusione
In conclusione, GroupDocs.Viewer per .NET offre una soluzione affidabile per il rendering di immagini CMX in vari formati in modo fluido. Seguendo i passaggi descritti in questo tutorial, è possibile integrare senza problemi le funzionalità di rendering delle immagini CMX nelle applicazioni .NET, migliorando l'efficienza della gestione dei documenti.
## Domande frequenti
### Posso eseguire il rendering di pagine specifiche di un'immagine CMX?
Sì, puoi eseguire il rendering di pagine specifiche specificando il numero di pagina nelle opzioni di rendering.
### GroupDocs.Viewer per .NET è compatibile con tutti i framework .NET?
Sì, GroupDocs.Viewer per .NET è compatibile con più framework .NET, tra cui .NET Core e .NET Framework.
### GroupDocs.Viewer supporta il rendering di immagini CMX crittografate?
Sì, GroupDocs.Viewer supporta il rendering di immagini CMX crittografate con chiavi di decrittazione appropriate.
### Posso personalizzare le opzioni di rendering per diversi formati di output?
Certamente, GroupDocs.Viewer offre ampie possibilità per personalizzare i parametri di rendering in base alle proprie esigenze.
### Esiste un forum della community per il supporto di GroupDocs.Viewer?
Sì, puoi richiedere assistenza e interagire con la community di GroupDocs.Viewer sul forum di supporto [Qui](https://forum.groupdocs.com/c/viewer/9).