---
"description": "Scopri come specificare il tipo di file quando carichi documenti utilizzando GroupDocs.Viewer per .NET. Visualizza con precisione vari formati nelle tue applicazioni .NET."
"linktitle": "Specificare il tipo di file durante il caricamento dei documenti"
"second_title": "API .NET di GroupDocs.Viewer"
"title": "Specificare il tipo di file durante il caricamento dei documenti"
"url": "/it/net/advanced-loading/specify-file-type/"
"weight": 10
type: docs
---
# Specificare il tipo di file durante il caricamento dei documenti

## Introduzione
GroupDocs.Viewer per .NET è un'API versatile per il rendering di documenti che supporta un'ampia gamma di formati di file, tra cui DOCX, PDF, PPTX e altri. Specificando il tipo di file al momento del caricamento dei documenti, è possibile garantire un rendering accurato e un'esperienza di visualizzazione fluida per gli utenti.

![Specificare il tipo di file durante il caricamento di documenti in GroupDocs.Viewer per .NET](/viewer/advanced-loading/specify-file-type-when-loading-documents-img.png)

## Prerequisiti
Prima di iniziare, assicurati di avere i seguenti prerequisiti:
- Conoscenza di base di C# e .NET Framework.
- Visual Studio installato sul sistema.
- GroupDocs.Viewer per .NET installato nel tuo progetto. Puoi scaricarlo da [Qui](https://releases.groupdocs.com/viewer/net/).
##
## Importa spazi dei nomi
Innanzitutto, è necessario importare gli spazi dei nomi necessari nel codice C#. Questi spazi dei nomi forniscono l'accesso alle classi e ai metodi necessari per il rendering dei documenti.
```csharp
using System;
using System.IO;
using GroupDocs.Viewer.Options;
```
## Passaggio 1: impostare la directory di output
Definisci la directory in cui vuoi salvare le pagine del documento renderizzate.
```csharp
string outputDirectory = "Your Document Directory";
```
## Passaggio 2: definire il formato del percorso del file di paging
Specificare il formato per la denominazione dei file HTML di output per ogni pagina del documento.
```csharp
string pageFilePathFormat = Path.Combine(outputDirectory, "page_{0}.html");
```
## Passaggio 3: specificare le opzioni di carico
Crea un'istanza di `LoadOptions` classe e imposta il tipo di file desiderato.
```csharp
LoadOptions loadOptions = new LoadOptions
{
    FileType = FileType.DOCX
};
```
## Passaggio 4: caricare il documento e renderizzarlo
Utilizzare il `Viewer` classe per caricare il documento e visualizzarlo in formato HTML.
```csharp
using (Viewer viewer = new Viewer("YourDocument.docx", loadOptions))
{
    HtmlViewOptions options = HtmlViewOptions.ForEmbeddedResources(pageFilePathFormat);
    viewer.View(options);
}
```
## Passaggio 5: visualizzare il messaggio di successo
Informare l'utente che il documento è stato renderizzato correttamente e specificare il percorso dei file di output.
```csharp
Console.WriteLine($"\nSource document rendered successfully.\nCheck output in {outputDirectory}.");
```

## Conclusione
In questo tutorial, abbiamo imparato come utilizzare GroupDocs.Viewer per .NET per specificare il tipo di file durante il caricamento dei documenti. Seguendo questi semplici passaggi, è possibile garantire un rendering accurato di diversi formati di documento nelle applicazioni .NET.
## Domande frequenti
### Posso visualizzare documenti in formato diverso da DOCX utilizzando GroupDocs.Viewer per .NET?
Sì, GroupDocs.Viewer supporta un'ampia gamma di formati di file, tra cui PDF, PPTX, XLSX e altri.
### GroupDocs.Viewer per .NET è compatibile con .NET Core?
Sì, GroupDocs.Viewer per .NET è compatibile sia con .NET Framework che con .NET Core.
### Posso personalizzare i file HTML di output generati da GroupDocs.Viewer?
Sì, puoi personalizzare l'output HTML utilizzando varie opzioni fornite dall'API.
### GroupDocs.Viewer per .NET richiede dipendenze esterne?
No, GroupDocs.Viewer per .NET è una libreria autonoma e non richiede dipendenze esterne.
### Esiste una versione di prova disponibile per GroupDocs.Viewer per .NET?
Sì, puoi scaricare una versione di prova gratuita da [Qui](https://releases.groupdocs.com/viewer/net/).