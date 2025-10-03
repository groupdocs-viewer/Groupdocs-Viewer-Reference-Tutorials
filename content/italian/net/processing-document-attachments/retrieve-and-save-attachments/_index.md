---
"description": "Gestisci in modo efficiente gli allegati dei documenti nelle applicazioni .NET utilizzando GroupDocs.Viewer. Recupera e salva gli allegati senza problemi."
"linktitle": "Recupera e salva gli allegati del documento"
"second_title": "API .NET di GroupDocs.Viewer"
"title": "Recupera e salva gli allegati del documento"
"url": "/it/net/processing-document-attachments/retrieve-and-save-attachments/"
"weight": 12
type: docs
---
# Recupera e salva gli allegati del documento

## Introduzione
Nell'era digitale, la gestione efficiente dei documenti è fondamentale sia per le aziende che per i privati. Che si tratti di gestire e-mail, visualizzare contratti o accedere a report, disporre di uno strumento affidabile per la visualizzazione dei documenti è essenziale. GroupDocs.Viewer per .NET si propone come una soluzione affidabile, consentendo agli utenti di visualizzare e interagire senza problemi con diversi formati di documento direttamente all'interno delle proprie applicazioni .NET.

![Recupera e salva gli allegati dei documenti con GroupDocs.Viewer .NET](/viewer/processing-document-attachments/retrieve-and-save-document-attachments.png)

## Prerequisiti
Prima di approfondire l'utilizzo di GroupDocs.Viewer per .NET per il recupero e il salvataggio degli allegati dei documenti, assicurarsi di disporre dei seguenti prerequisiti:
1. Ambiente operativo: ambiente di lavoro configurato con .NET Framework.
2. Installazione: GroupDocs.Viewer per la libreria .NET scaricato e installato. È possibile accedere alla libreria da [collegamento per il download](https://releases.groupdocs.com/viewer/net/).
3. Nozioni di base: familiarità con il linguaggio di programmazione C#.
4. Origine del documento: accesso a un documento di esempio con allegati a scopo dimostrativo.

## Importa spazi dei nomi
Per iniziare a utilizzare GroupDocs.Viewer per .NET per il recupero e il salvataggio degli allegati dei documenti, importare gli spazi dei nomi necessari:
```csharp
using System;
using System.Collections.Generic;
using System.IO;
using GroupDocs.Viewer.Results;
```

## Passaggio 1: definire la directory di output
```csharp
string outputDirectory = "Your Document Directory";
```
Definisci la directory in cui vuoi salvare gli allegati recuperati dal documento.
## Passaggio 2: creare un'istanza dell'oggetto Viewer
```csharp
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_MSG_WITH_ATTACHMENTS))
```
Creare un'istanza dell'oggetto Viewer con il percorso al documento contenente gli allegati.
## Passaggio 3: Recupera gli allegati
```csharp
IList<Attachment> attachments = viewer.GetAttachments();
```
Recupera un elenco degli allegati presenti nel documento.
## Passaggio 4: Salva gli allegati
```csharp
foreach(Attachment attachment in attachments)
{
    string filePath = Path.Combine(outputDirectory, attachment.FileName);  
    viewer.SaveAttachment(attachment, File.OpenWrite(filePath)); 
}
```
Scorrere ogni allegato, definire il percorso del file e salvare l'allegato nella directory specificata.
## Passaggio 5: visualizzare il messaggio di successo
```csharp
Console.WriteLine($"\nAttachments saved successfully.\nCheck output in {outputDirectory}.");
```
Visualizza un messaggio di successo che indica il salvataggio riuscito degli allegati insieme al percorso della directory.

## Conclusione
L'integrazione di GroupDocs.Viewer per .NET nei flussi di lavoro di gestione dei documenti semplifica la gestione degli allegati, offrendo efficienza e praticità. Seguendo la guida dettagliata descritta sopra, gli utenti possono recuperare e salvare senza problemi gli allegati dei documenti all'interno delle loro applicazioni .NET.
## Domande frequenti
### GroupDocs.Viewer per .NET può gestire vari formati di documenti?
Sì, GroupDocs.Viewer supporta un'ampia gamma di formati di documenti, tra cui PDF, documenti Microsoft Office, immagini e altro ancora.
### È disponibile una versione di prova gratuita di GroupDocs.Viewer per .NET?
Sì, puoi accedere alla prova gratuita da [Qui](https://releases.groupdocs.com/).
### Come posso ottenere licenze temporanee per GroupDocs.Viewer per .NET?
Le licenze temporanee possono essere acquisite da [questo collegamento](https://purchase.groupdocs.com/temporary-license/).
### Dove posso trovare la documentazione per GroupDocs.Viewer per .NET?
È disponibile una documentazione completa [Qui](https://tutorials.groupdocs.com/viewer/net/).
### Quali opzioni di supporto sono disponibili per GroupDocs.Viewer per .NET?
Puoi chiedere assistenza al forum della comunità [Qui](https://forum.groupdocs.com/c/viewer/9).