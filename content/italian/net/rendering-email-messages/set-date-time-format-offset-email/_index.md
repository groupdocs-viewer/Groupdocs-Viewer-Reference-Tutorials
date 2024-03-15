---
title: Imposta il formato data/ora e la differenza del fuso orario (e-mail)
linktitle: Imposta il formato data/ora e la differenza del fuso orario (e-mail)
second_title: API GroupDocs.Viewer .NET
description: Integra GroupDocs.Viewer for .NET perfettamente nelle tue applicazioni per potenti funzionalità di visualizzazione dei documenti. Migliora l'esperienza utente con opzioni personalizzabili.
type: docs
weight: 11
url: /it/net/rendering-email-messages/set-date-time-format-offset-email/
---

## introduzione
GroupDocs.Viewer per .NET è un potente strumento che consente agli sviluppatori di integrare perfettamente le funzionalità di visualizzazione dei documenti nelle loro applicazioni .NET. Con GroupDocs.Viewer puoi visualizzare un'ampia gamma di formati di documenti tra cui PDF, documenti di Microsoft Office, immagini e altro direttamente all'interno della tua applicazione, senza la necessità di plug-in o visualizzatori esterni. In questo tutorial completo ti guideremo attraverso il processo di configurazione di GroupDocs.Viewer per .NET, esplorandone le funzionalità e dimostrando come utilizzarlo in modo efficace per migliorare le capacità di visualizzazione dei documenti della tua applicazione.
## Prerequisiti
Prima di immergerti in questo tutorial, assicurati di aver impostato i seguenti prerequisiti:
1. Visual Studio: assicurati di avere Visual Studio installato sul tuo sistema. GroupDocs.Viewer per .NET è completamente compatibile con Visual Studio, consentendo una perfetta integrazione nei tuoi progetti .NET.
2.  GroupDocs.Viewer per .NET: scaricare e installare GroupDocs.Viewer per .NET dal[Link per scaricare](https://releases.groupdocs.com/viewer/net/). Seguire le istruzioni di installazione fornite per configurare la libreria nel proprio ambiente di sviluppo.
3. .NET Framework: assicurarsi di avere installata la versione appropriata di .NET Framework. GroupDocs.Viewer per .NET supporta varie versioni di .NET Framework, inclusi .NET Core e .NET Standard.

## Importa spazi dei nomi
Per utilizzare GroupDocs.Viewer for .NET in modo efficace, è necessario importare gli spazi dei nomi necessari nel progetto. Seguire questi passaggi per importare gli spazi dei nomi richiesti:

```csharp
using System;
using System.IO;
using GroupDocs.Viewer.Options;
```


Suddividiamo l'esempio fornito in più passaggi per comprendere ciascun componente e la sua funzionalità.
## Passaggio 1: impostare la directory di output e il percorso del file
```csharp
string outputDirectory = "Your Document Directory";
string filePath = Path.Combine(outputDirectory, "output.html");
```
In questo passaggio, definiamo la directory di output in cui verrà salvato il documento renderizzato e specifichiamo il percorso del file HTML di output.
## Passaggio 2: istanziare l'oggetto visualizzatore
```csharp
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_EML))
```
 Qui creiamo una nuova istanza di`Viewer` class, passando come parametro il percorso del documento da visualizzare (in questo caso, un file EML di esempio).
## Passaggio 3: definire le opzioni di visualizzazione HTML
```csharp
HtmlViewOptions options = HtmlViewOptions.ForEmbeddedResources(filePath);
```
In questo passaggio, configuriamo le opzioni di visualizzazione HTML per il rendering del documento, specificando il percorso del file di output per il documento HTML renderizzato.
## Passaggio 4: imposta il formato data e ora e la differenza del fuso orario
```csharp
options.EmailOptions.DateTimeFormat = "MM d yyyy HH:mm tt zzz";
options.EmailOptions.TimeZoneOffset = new TimeSpan(1, 0, 0);
```
Qui personalizziamo il formato di data e ora per i messaggi e-mail e impostiamo la differenza di fuso orario in base al fuso orario desiderato.
## Passaggio 5: rendering del documento
```csharp
viewer.View(options);
```
 Infine, chiamiamo il`View` metodo del`Viewer` oggetto, passando le opzioni di visualizzazione HTML configurate per eseguire il rendering del documento in formato HTML.
## Passaggio 6: Visualizza la directory di output
```csharp
Console.WriteLine($"\nSource document rendered successfully.\nCheck output in {outputDirectory}.");
```
Questo passaggio visualizza semplicemente un messaggio che indica l'avvenuto rendering del documento e fornisce il percorso della directory di output in cui si trova il documento HTML renderizzato.

## Conclusione
GroupDocs.Viewer per .NET offre una soluzione solida per integrare le funzionalità di visualizzazione dei documenti nelle applicazioni .NET. Seguendo i passaggi descritti in questo tutorial, puoi configurare facilmente GroupDocs.Viewer, importare gli spazi dei nomi necessari e utilizzare le sue funzionalità per eseguire il rendering di documenti con opzioni personalizzabili. Che tu stia lavorando con PDF, documenti di Microsoft Office o altri formati, GroupDocs.Viewer semplifica il processo di visualizzazione dei documenti, migliorando l'esperienza utente delle tue applicazioni.
## Domande frequenti
### GroupDocs.Viewer è compatibile con .NET Core?
Sì, GroupDocs.Viewer per .NET supporta .NET Core, consentendo la compatibilità multipiattaforma per le tue applicazioni.
### Posso personalizzare l'aspetto dei documenti renderizzati?
Assolutamente! GroupDocs.Viewer offre varie opzioni di personalizzazione tra cui livelli di zoom, rotazione della pagina e altro per personalizzare l'esperienza di visualizzazione in base alle tue preferenze.
### È disponibile una versione di prova a scopo di test?
 Sì, puoi scaricare una versione di prova gratuita di GroupDocs.Viewer per .NET da[collegamento al sito web](https://releases.groupdocs.com/viewer/net/) per valutarne le caratteristiche prima di effettuare l'acquisto.
### GroupDocs.Viewer supporta il rendering di documenti protetti da password?
Sì, GroupDocs.Viewer dispone del supporto integrato per il rendering di documenti protetti da password, garantendo la visualizzazione sicura dei documenti all'interno delle tue applicazioni.
### Dove posso trovare ulteriore supporto o assistenza con GroupDocs.Viewer?
 Per qualsiasi domanda tecnica o assistenza, è possibile visitare GroupDocs.Viewer[Forum](https://forum.groupdocs.com/c/viewer/9) oppure contatta il loro team di supporto per ricevere aiuto e guida tempestivi.