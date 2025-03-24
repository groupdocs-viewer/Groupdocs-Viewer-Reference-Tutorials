---
title: Proteggi PDF renderizzato con password
linktitle: Proteggi PDF renderizzato con password
second_title: API GroupDocs.Viewer .NET
description: Proteggi facilmente i tuoi PDF renderizzati con password utilizzando Groupdocs.Viewer per .NET. Mantieni i tuoi documenti sicuri e riservati.
weight: 12
url: /it/net/rendering-documents-pdf/protect-pdf/
---
## introduzione
In questo tutorial imparerai come utilizzare Groupdocs.Viewer per .NET per proteggere un PDF sottoposto a rendering con una password. Aggiungendo misure di sicurezza, puoi controllare l'accesso ai tuoi documenti PDF, garantendo riservatezza e integrità.
## Prerequisiti
Prima di iniziare, assicurati di avere quanto segue:
1.  Groupdocs.Viewer per .NET Library: scarica e installa la libreria da[sito web](https://releases.groupdocs.com/viewer/net/).
2. Ambiente di sviluppo: assicurati di disporre di un ambiente di sviluppo funzionante configurato per lo sviluppo .NET.

## Importa spazi dei nomi
```csharp
using System;
using System.IO;
using GroupDocs.Viewer.Options;
```
## Passaggio 1: definire la directory di output e il percorso del file
```csharp
string outputDirectory = "Your Document Directory";
string filePath = Path.Combine(outputDirectory, "output.pdf");
```
## Passaggio 2: inizializzare l'oggetto visualizzatore e impostare le opzioni di sicurezza
```csharp
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_DOCX))
{
    Security security = new Security
    {
        DocumentOpenPassword = "o123",
        PermissionsPassword = "p123",
        Permissions = Permissions.AllowAll ^ Permissions.DenyPrinting
    };
```
## Passaggio 3: imposta le opzioni di visualizzazione PDF
```csharp
    PdfViewOptions options = new PdfViewOptions(filePath)
    {
        Security = security
    };
```
## Passaggio 4: rendering del documento con opzioni di sicurezza
```csharp
    viewer.View(options);
}
```
## Passaggio 5: controlla il documento renderizzato
```csharp
Console.WriteLine($"\nSource document rendered successfully.\nCheck output in {outputDirectory}.");
```
Seguendo questi passaggi, puoi proteggere un PDF renderizzato con una password utilizzando Groupdocs.Viewer per .NET. Ciò garantisce che i tuoi documenti rimangano sicuri e accessibili solo agli utenti autorizzati.

## Conclusione
La protezione dei documenti PDF è essenziale per mantenerne la riservatezza e l'integrità. Con Groupdocs.Viewer per .NET, puoi proteggere facilmente i PDF renderizzati con password, controllando l'accesso alle informazioni sensibili.

## Domande frequenti
### Posso proteggere i PDF con diversi livelli di autorizzazioni?
Sì, puoi specificare autorizzazioni diverse per la visualizzazione, la stampa, la copia e altro proteggendo i PDF con password.
### Groupdocs.Viewer è compatibile con vari formati di file?
Assolutamente! Groupdocs.Viewer supporta il rendering di un'ampia gamma di formati di file, inclusi DOCX, XLSX, PPTX, PDF e altri.
### Posso integrare Groupdocs.Viewer nella mia applicazione .NET esistente?
Certamente! Groupdocs.Viewer fornisce API per un'integrazione perfetta nelle applicazioni .NET, offrendo solide funzionalità di visualizzazione dei documenti.
### Groupdocs.Viewer offre supporto per i servizi di archiviazione cloud?
Sì, Groupdocs.Viewer supporta l'integrazione con i più diffusi servizi di archiviazione cloud come Dropbox, Google Drive e Amazon S3, consentendoti di eseguire il rendering dei documenti archiviati nel cloud.
### È disponibile una versione di prova per Groupdocs.Viewer?
 Sì, puoi iniziare con Groupdocs.Viewer accedendo alla versione di prova gratuita da[sito web](https://releases.groupdocs.com/).