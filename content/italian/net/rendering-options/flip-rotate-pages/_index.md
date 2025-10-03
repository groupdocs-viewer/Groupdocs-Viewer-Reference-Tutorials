---
"description": "Scopri come integrare Groupdocs.Viewer per .NET nelle tue applicazioni per ottenere un rendering, un capovolgimento e una rotazione fluidi dei documenti."
"linktitle": "Capovolgi e ruota le pagine"
"second_title": "API .NET di GroupDocs.Viewer"
"title": "Capovolgi e ruota le pagine"
"url": "/it/net/rendering-options/flip-rotate-pages/"
"weight": 12
type: docs
---
# Capovolgi e ruota le pagine

## Introduzione
In questo tutorial approfondiremo le funzionalità di Groupdocs.Viewer per .NET, concentrandoci in particolare sullo scorrimento e la rotazione delle pagine. Groupdocs.Viewer per .NET è un potente strumento progettato per visualizzare documenti in vari formati all'interno di applicazioni .NET. Che stiate sviluppando un sistema di gestione documentale o abbiate bisogno di integrare funzionalità di visualizzazione dei documenti nel vostro software, Groupdocs.Viewer per .NET offre una soluzione efficiente.
## Prerequisiti
Prima di iniziare, assicurati di aver impostato i seguenti prerequisiti:
### Installazione di Groupdocs.Viewer per .NET
Per utilizzare Groupdocs.Viewer per .NET, è necessario installare il pacchetto tramite NuGet Package Manager. Le istruzioni di installazione dettagliate sono disponibili in [documentazione](https://tutorials.groupdocs.com/viewer/net/).

## Importa spazi dei nomi
Assicurati di aver importato nel tuo progetto gli spazi dei nomi necessari per utilizzare Groupdocs.Viewer per .NET in modo efficace.
```csharp
using System;
using System.IO;
using GroupDocs.Viewer.Options;
```

Analizziamo nel dettaglio il processo di capovolgimento e rotazione delle pagine tramite Groupdocs.Viewer per .NET in semplici passaggi:
## Passaggio 1: impostare la directory di output e il percorso del file
Definisci la directory in cui desideri salvare il file di output e specifica il percorso del file di output.
```csharp
string outputDirectory = "Your Document Directory";
string outputFilePath = Path.Combine(outputDirectory, "output.pdf");
```
## Passaggio 2: inizializzare l'oggetto Viewer
Crea un'istanza della classe Viewer passando il percorso al documento che vuoi visualizzare.
```csharp
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_DOCX))
```
## Passaggio 3: configurare le opzioni di visualizzazione
Imposta le opzioni di visualizzazione, ad esempio specificando il formato del file di output e qualsiasi altra impostazione aggiuntiva come la rotazione della pagina.
```csharp
PdfViewOptions viewOptions = new PdfViewOptions(outputFilePath);
viewOptions.RotatePage(1, Rotation.On90Degree);
```
## Passaggio 4: rendering del documento
Richiamare il metodo View dell'oggetto Viewer e passare le opzioni di visualizzazione.
```csharp
viewer.View(viewOptions);
```
## Passaggio 5: visualizzare il messaggio di successo
Informare l'utente che il documento è stato renderizzato correttamente e specificare la directory di output per la verifica.
```csharp
Console.WriteLine($"\nSource document rendered successfully.\nCheck output in {outputDirectory}.");
```

## Conclusione
In conclusione, Groupdocs.Viewer per .NET offre potenti funzionalità per il rendering dei documenti, tra cui il capovolgimento e la rotazione delle pagine. Seguendo i passaggi descritti in questo tutorial, è possibile integrare perfettamente queste funzionalità nelle applicazioni .NET, migliorando l'esperienza di visualizzazione dei documenti per gli utenti.
## Domande frequenti
### Groupdocs.Viewer per .NET è compatibile con tutti i formati di documento?
Sì, Groupdocs.Viewer per .NET supporta un'ampia gamma di formati di documenti, tra cui DOCX, PDF, PPTX e altri.
### Posso personalizzare le opzioni di visualizzazione oltre a sfogliare e ruotare le pagine?
Certamente, Groupdocs.Viewer per .NET offre diverse opzioni di personalizzazione per la visualizzazione dei documenti, consentendoti di adattare l'esperienza alle tue esigenze.
### È disponibile una versione di prova gratuita di Groupdocs.Viewer per .NET?
Sì, puoi usufruire di una prova gratuita di Groupdocs.Viewer per .NET visitando il sito [sito web](https://releases.groupdocs.com/).
### Come posso ottenere supporto per Groupdocs.Viewer per .NET?
Puoi cercare assistenza e interagire con la comunità attraverso [Forum di Groupdocs.Viewer](https://forum.groupdocs.com/c/viewer/9).
### Dove posso ottenere una licenza temporanea per Groupdocs.Viewer per .NET?
Le licenze temporanee per Groupdocs.Viewer per .NET possono essere ottenute da [pagina di acquisto](https://purchase.groupdocs.com/temporary-license/).