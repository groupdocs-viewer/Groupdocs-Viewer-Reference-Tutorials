---
title: Capovolgi e ruota le pagine
linktitle: Capovolgi e ruota le pagine
second_title: API GroupDocs.Viewer .NET
description: Scopri come integrare Groupdocs.Viewer for .NET nelle tue applicazioni per il rendering, il capovolgimento e la rotazione dei documenti senza interruzioni.
weight: 12
url: /it/net/rendering-options/flip-rotate-pages/
---

# Capovolgi e ruota le pagine

## introduzione
In questo tutorial, approfondiremo le funzionalità di Groupdocs.Viewer per .NET, concentrandoci in particolare sul capovolgimento e sulla rotazione delle pagine. Groupdocs.Viewer per .NET è un potente strumento progettato per eseguire il rendering di documenti in vari formati all'interno delle applicazioni .NET. Che tu stia sviluppando un sistema di gestione dei documenti o desideri integrare funzionalità di visualizzazione dei documenti nel tuo software, Groupdocs.Viewer per .NET fornisce una soluzione efficiente.
## Prerequisiti
Prima di iniziare, assicurati di aver configurato i seguenti prerequisiti:
### Installazione di Groupdocs.Viewer per .NET
 Per utilizzare Groupdocs.Viewer per .NET, è necessario installare il pacchetto tramite NuGet Package Manager. È possibile trovare istruzioni dettagliate per l'installazione nel file[documentazione](https://tutorials.groupdocs.com/viewer/net/).

## Importa spazi dei nomi
Assicurati di avere importati gli spazi dei nomi necessari nel tuo progetto per utilizzare Groupdocs.Viewer per .NET in modo efficace.
```csharp
using System;
using System.IO;
using GroupDocs.Viewer.Options;
```

Analizziamo il processo di capovolgimento e rotazione delle pagine utilizzando Groupdocs.Viewer per .NET in semplici passaggi:
## Passaggio 1: impostare la directory di output e il percorso del file
Definire la directory in cui si desidera salvare il file di output e specificare il percorso del file di output.
```csharp
string outputDirectory = "Your Document Directory";
string outputFilePath = Path.Combine(outputDirectory, "output.pdf");
```
## Passaggio 2: inizializza l'oggetto visualizzatore
Crea un'istanza della classe Viewer passando il percorso del documento che desideri visualizzare.
```csharp
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_DOCX))
```
## Passaggio 3: configura le opzioni di visualizzazione
Configura le opzioni di visualizzazione, come specificare il formato del file di output ed eventuali impostazioni aggiuntive come la rotazione della pagina.
```csharp
PdfViewOptions viewOptions = new PdfViewOptions(outputFilePath);
viewOptions.RotatePage(1, Rotation.On90Degree);
```
## Passaggio 4: rendering del documento
Richiama il metodo View dell'oggetto Viewer e passa le opzioni di visualizzazione.
```csharp
viewer.View(viewOptions);
```
## Passaggio 5: Visualizza il messaggio di successo
Informare l'utente che il rendering del documento è stato eseguito correttamente e specificare la directory di output per la verifica.
```csharp
Console.WriteLine($"\nSource document rendered successfully.\nCheck output in {outputDirectory}.");
```

## Conclusione
In conclusione, Groupdocs.Viewer per .NET offre potenti funzionalità per il rendering di documenti, incluso il capovolgimento e la rotazione delle pagine. Seguendo i passaggi descritti in questa esercitazione, puoi integrare perfettamente queste funzionalità nelle tue applicazioni .NET, migliorando le esperienze di visualizzazione dei documenti per i tuoi utenti.
## Domande frequenti
### Groupdocs.Viewer per .NET è compatibile con tutti i formati di documenti?
Sì, Groupdocs.Viewer per .NET supporta un'ampia gamma di formati di documenti, inclusi DOCX, PDF, PPTX e altri.
### Posso personalizzare le opzioni di visualizzazione oltre a sfogliare e ruotare le pagine?
Assolutamente sì, Groupdocs.Viewer per .NET offre varie opzioni di personalizzazione per la visualizzazione dei documenti, consentendoti di personalizzare l'esperienza in base alle tue esigenze.
### È disponibile una prova gratuita per Groupdocs.Viewer per .NET?
 Sì, puoi usufruire di una prova gratuita di Groupdocs.Viewer per .NET visitando il sito[sito web](https://releases.groupdocs.com/).
### Come posso ottenere supporto per Groupdocs.Viewer per .NET?
 Puoi cercare assistenza e interagire con la comunità attraverso il[Forum di Groupdocs.Viewer](https://forum.groupdocs.com/c/viewer/9).
### Dove posso ottenere una licenza temporanea per Groupdocs.Viewer per .NET?
 Le licenze temporanee per Groupdocs.Viewer per .NET possono essere ottenute da[pagina di acquisto](https://purchase.groupdocs.com/temporary-license/).