---
"description": "Migliora le tue applicazioni .NET con GroupDocs.Viewer per una visualizzazione fluida dei documenti. Segui la nostra guida passo passo e integra potenti funzionalità di visualizzazione dei documenti senza sforzo."
"linktitle": "Imposta licenza da Stream"
"second_title": "API .NET di GroupDocs.Viewer"
"title": "Imposta licenza da Stream"
"url": "/it/net/getting-started/set-license-from-stream/"
"weight": 11
type: docs
---
# Imposta licenza da Stream

## Introduzione
Desideri potenziare le tue applicazioni .NET con funzionalità avanzate di visualizzazione dei documenti? GroupDocs.Viewer per .NET offre una soluzione completa per integrare perfettamente le funzionalità di visualizzazione dei documenti nei tuoi progetti. In questo tutorial, approfondiremo il processo di utilizzo di GroupDocs.Viewer per .NET per arricchire le tue applicazioni con potenti funzionalità di visualizzazione dei documenti. 

![Imposta la licenza dal flusso con GroupDocs.Viewer per .NET](/viewer/getting-started/set-license-from-stream.png)

## Prerequisiti
Prima di addentrarci nel processo di integrazione, assicurati di avere i seguenti prerequisiti:
1. Conoscenza di base dello sviluppo .NET: per seguire questo tutorial è essenziale avere familiarità con C# e con il framework .NET.
   
2. Pacchetto GroupDocs.Viewer per .NET: assicurati di aver scaricato e installato il pacchetto GroupDocs.Viewer per .NET. Puoi scaricarlo da [collegamento per il download](https://releases.groupdocs.com/viewer/net/).
3. Accesso alla documentazione di GroupDocs: Mantieni il [documentazione](https://tutorials.groupdocs.com/viewer/net/) utile per i tutorial durante il processo di integrazione.

## Importa spazi dei nomi
Per iniziare, importa gli spazi dei nomi necessari nella tua applicazione .NET. Segui questi passaggi:
### Passaggio 1: aprire il progetto .NET.
Assicurati di aver aperto il progetto .NET nel tuo ambiente di sviluppo preferito.
### Passaggio 2: aggiungere lo spazio dei nomi GroupDocs.Viewer.
Nel file di codice, aggiungi il seguente namespace per accedere alle funzionalità di GroupDocs.Viewer:
```csharp
using System;
using System.IO;
```
## Imposta licenza da Stream
Il passaggio successivo consiste nell'impostare la licenza da un flusso. Seguite questi passaggi dettagliati:
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
### Fase 4: gestire l'assenza della licenza.
Se il file di licenza non viene trovato, fornire istruzioni per ottenere una licenza:
```csharp
else
{
    Console.WriteLine("\nWe do not ship any license with this example. " +
                      "\nVisit the GroupDocs site to obtain either a temporary or permanent license. " +
                      "\nLearn more about licensing at https://purchase.groupdocs.com/faqs/licensing." +
                      "\nLearn how to request a temporary license at https://purchase.groupdocs.com/licenza-temporanea.");
}
```

## Conclusione
Congratulazioni! Hai imparato a integrare GroupDocs.Viewer per .NET nelle tue applicazioni. Con questo potente strumento, ora puoi visualizzare senza problemi diversi formati di documento nei tuoi progetti .NET, migliorando l'esperienza utente e la produttività.
## Domande frequenti
### Ho bisogno di una licenza per utilizzare GroupDocs.Viewer per .NET?
Sì, è necessaria una licenza per utilizzare GroupDocs.Viewer per .NET. È possibile ottenere una licenza temporanea o permanente dal sito web di GroupDocs.
### Posso integrare GroupDocs.Viewer nella mia applicazione ASP.NET?
Assolutamente sì! GroupDocs.Viewer per .NET si integra perfettamente sia nelle applicazioni desktop che in quelle web, incluso ASP.NET.
### Quali formati di documento sono supportati da GroupDocs.Viewer?
GroupDocs.Viewer supporta un'ampia gamma di formati di documenti, tra cui PDF, Microsoft Office (Word, Excel, PowerPoint), immagini e altro ancora.
### GroupDocs.Viewer è compatibile con .NET Core?
Sì, GroupDocs.Viewer per .NET è compatibile sia con .NET Framework che con .NET Core.
### Posso personalizzare l'interfaccia del visualizzatore in base al tema della mia applicazione?
Sì, GroupDocs.Viewer offre ampie opzioni di personalizzazione, consentendoti di adattare perfettamente l'interfaccia del visualizzatore al tema della tua applicazione.