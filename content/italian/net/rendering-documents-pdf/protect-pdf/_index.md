---
"description": "Proteggi facilmente i tuoi PDF renderizzati con password utilizzando Groupdocs.Viewer per .NET. Mantieni i tuoi documenti sicuri e riservati."
"linktitle": "Proteggi il PDF renderizzato con password"
"second_title": "API .NET di GroupDocs.Viewer"
"title": "Proteggi il PDF renderizzato con password"
"url": "/it/net/rendering-documents-pdf/protect-pdf/"
"weight": 12
type: docs
---
# Proteggi il PDF renderizzato con password

## Introduzione
In questo tutorial imparerai come utilizzare Groupdocs.Viewer per .NET per proteggere con una password un PDF renderizzato. Aggiungendo misure di sicurezza, puoi controllare l'accesso ai tuoi documenti PDF, garantendone riservatezza e integrità.
## Prerequisiti
Prima di iniziare, assicurati di avere quanto segue:
1. Groupdocs.Viewer per la libreria .NET: scarica e installa la libreria da [sito web](https://releases.groupdocs.com/viewer/net/).
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
## Passaggio 2: inizializzare l'oggetto Viewer e impostare le opzioni di sicurezza
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
## Passaggio 5: verifica del documento renderizzato
```csharp
Console.WriteLine($"\nSource document rendered successfully.\nCheck output in {outputDirectory}.");
```
Seguendo questi passaggi, è possibile proteggere un PDF renderizzato con una password utilizzando Groupdocs.Viewer per .NET. In questo modo, i documenti rimangono protetti e accessibili solo agli utenti autorizzati.

## Conclusione
Proteggere i documenti PDF è essenziale per garantirne la riservatezza e l'integrità. Con Groupdocs.Viewer per .NET, puoi proteggere facilmente i PDF renderizzati con password, controllando l'accesso alle informazioni sensibili.

## Domande frequenti
### Posso proteggere i PDF con diversi livelli di autorizzazione?
Sì, puoi specificare autorizzazioni diverse per la visualizzazione, la stampa, la copia e altro ancora, proteggendo i PDF con password.
### Groupdocs.Viewer è compatibile con vari formati di file?
Assolutamente sì! Groupdocs.Viewer supporta il rendering di un'ampia gamma di formati di file, tra cui DOCX, XLSX, PPTX, PDF e altri.
### Posso integrare Groupdocs.Viewer nella mia applicazione .NET esistente?
Certamente! Groupdocs.Viewer fornisce API per una perfetta integrazione nelle applicazioni .NET, offrendo solide funzionalità di visualizzazione dei documenti.
### Groupdocs.Viewer offre supporto per i servizi di archiviazione cloud?
Sì, Groupdocs.Viewer supporta l'integrazione con i servizi di archiviazione cloud più diffusi, come Dropbox, Google Drive e Amazon S3, consentendo di visualizzare i documenti archiviati nel cloud.
### Esiste una versione di prova disponibile per Groupdocs.Viewer?
Sì, puoi iniziare a utilizzare Groupdocs.Viewer accedendo alla versione di prova gratuita da [sito web](https://releases.groupdocs.com/).