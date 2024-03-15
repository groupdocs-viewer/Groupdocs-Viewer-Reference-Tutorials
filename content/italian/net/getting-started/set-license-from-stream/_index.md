---
title: Imposta la licenza dallo streaming
linktitle: Imposta la licenza dallo streaming
second_title: API GroupDocs.Viewer .NET
description: Migliora le tue applicazioni .NET con GroupDocs.Viewer per una visualizzazione fluida dei documenti. Segui la nostra guida passo passo e integra facilmente potenti funzionalità di visualizzazione dei documenti.
type: docs
weight: 11
url: /it/net/getting-started/set-license-from-stream/
---
## introduzione
Desideri potenziare le tue applicazioni .NET con funzionalità avanzate di visualizzazione dei documenti? GroupDocs.Viewer per .NET offre una soluzione completa per integrare perfettamente le funzionalità di visualizzazione dei documenti nei tuoi progetti. In questo tutorial approfondiremo il processo di utilizzo di GroupDocs.Viewer per .NET per arricchire le tue applicazioni con potenti funzionalità di visualizzazione dei documenti. 
## Prerequisiti
Prima di addentrarci nel processo di integrazione, assicurati di disporre dei seguenti prerequisiti:
1. Conoscenza di base dello sviluppo .NET: la familiarità con C# e .NET Framework è essenziale da seguire insieme a questo tutorial.
   
2.  Pacchetto GroupDocs.Viewer per .NET: assicurati di aver scaricato e installato il pacchetto GroupDocs.Viewer per .NET. Puoi ottenerlo da[Link per scaricare](https://releases.groupdocs.com/viewer/net/).
3.  Accesso alla documentazione di GroupDocs: conserva il file[documentazione](https://reference.groupdocs.com/viewer/net/) utile come riferimento durante il processo di integrazione.

## Importa spazi dei nomi
Per cominciare, importa gli spazi dei nomi necessari nella tua applicazione .NET. Segui questi passi:
### Passaggio 1: apri il tuo progetto .NET.
Assicurati di avere il tuo progetto .NET aperto nel tuo ambiente di sviluppo preferito.
### Passaggio 2: aggiungi lo spazio dei nomi GroupDocs.Viewer.
Nel file di codice, aggiungi il seguente spazio dei nomi per accedere alle funzionalità GroupDocs.Viewer:
```csharp
using System;
using System.IO;
```
## Imposta la licenza dallo streaming
Il passaggio successivo prevede l'impostazione della licenza da uno stream. Segui questi passaggi dettagliati:
### Passaggio 1: definire la directory di output.
Imposta la directory in cui verranno archiviati i tuoi documenti definendo la directory di output:
```csharp
string outputDirectory = "Your Document Directory";
```
### Passaggio 2: verificare l'esistenza del file di licenza.
Controlla se il file di licenza esiste nella directory del tuo progetto:
```csharp
if (File.Exists(Utils.LicensePath))
```
### Passaggio 3: imposta la licenza.
Se il file di licenza esiste, imposta la licenza utilizzando il flusso fornito:
```csharp
using (FileStream stream = File.OpenRead(Utils.LicensePath))
{
    License license = new License();
    license.SetLicense(stream);
}
```
### Passaggio 4: gestire l'assenza di licenza.
Se il file di licenza non viene trovato, fornire istruzioni per ottenere una licenza:
```csharp
else
{
    Console.WriteLine("\nWe do not ship any license with this example. " +
                      "\nVisit the GroupDocs site to obtain either a temporary or permanent license. " +
                      "\nLearn more about licensing at https://Purchase.groupdocs.com/faqs/licensing. "+
                      "\nLearn how to request a temporary license at https://Purchase.groupdocs.com/temporary-license.");
}
```

## Conclusione
Congratulazioni! Hai imparato con successo come integrare GroupDocs.Viewer per .NET nelle tue applicazioni. Con questo potente strumento, ora puoi visualizzare facilmente vari formati di documenti all'interno dei tuoi progetti .NET, migliorando l'esperienza utente e la produttività.
## Domande frequenti
### Ho bisogno di una licenza per utilizzare GroupDocs.Viewer per .NET?
Sì, è necessaria una licenza per utilizzare GroupDocs.Viewer per .NET. È possibile ottenere una licenza temporanea o permanente dal sito Web GroupDocs.
### Posso integrare GroupDocs.Viewer nella mia applicazione ASP.NET?
Assolutamente! GroupDocs.Viewer per .NET si integra perfettamente sia nelle applicazioni desktop che Web, incluso ASP.NET.
### Quali formati di documento sono supportati da GroupDocs.Viewer?
GroupDocs.Viewer supporta un'ampia gamma di formati di documenti, tra cui PDF, Microsoft Office (Word, Excel, PowerPoint), immagini e altro.
### GroupDocs.Viewer è compatibile con .NET Core?
Sì, GroupDocs.Viewer per .NET è compatibile sia con .NET Framework che con .NET Core.
### Posso personalizzare l'interfaccia del visualizzatore in base al tema della mia applicazione?
Sì, GroupDocs.Viewer offre ampie opzioni di personalizzazione, consentendoti di personalizzare l'interfaccia del visualizzatore per adattarla perfettamente al tema della tua applicazione.