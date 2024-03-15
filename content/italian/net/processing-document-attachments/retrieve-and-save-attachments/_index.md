---
title: Recupera e salva gli allegati dei documenti
linktitle: Recupera e salva gli allegati dei documenti
second_title: API GroupDocs.Viewer .NET
description: Gestisci in modo efficiente i documenti allegati all'interno delle applicazioni .NET utilizzando GroupDocs.Viewer. Recupera e salva gli allegati senza problemi.
type: docs
weight: 12
url: /it/net/processing-document-attachments/retrieve-and-save-attachments/
---
## introduzione
Nell’era digitale, una gestione efficiente dei documenti è fondamentale sia per le aziende che per i privati. Che si tratti di gestire e-mail, visualizzare contratti o accedere a report, disporre di uno strumento affidabile per la visualizzazione dei documenti è essenziale. GroupDocs.Viewer per .NET emerge come una soluzione solida, che consente agli utenti di visualizzare e interagire facilmente con vari formati di documenti direttamente all'interno delle loro applicazioni .NET.
## Prerequisiti
Prima di approfondire l'utilizzo di GroupDocs.Viewer for .NET per il recupero e il salvataggio degli allegati di documenti, assicurarsi di disporre dei seguenti prerequisiti:
1. Ambiente operativo: un ambiente di lavoro configurato con .NET framework.
2.  Installazione: libreria GroupDocs.Viewer per .NET scaricata e installata. È possibile accedere alla libreria da[Link per scaricare](https://releases.groupdocs.com/viewer/net/).
3. Comprensioni di base: familiarità con il linguaggio di programmazione C#.
4. Origine documento: accesso a un documento di esempio con allegati a scopo dimostrativo.

## Importa spazi dei nomi
Per iniziare a utilizzare GroupDocs.Viewer for .NET per il recupero e il salvataggio degli allegati ai documenti, importare gli spazi dei nomi necessari:
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
Definire la directory in cui si desidera salvare gli allegati recuperati dal documento.
## Passaggio 2: istanziare l'oggetto visualizzatore
```csharp
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_MSG_WITH_ATTACHMENTS))
```
Crea un'istanza dell'oggetto Viewer con il percorso del documento contenente gli allegati.
## Passaggio 3: recuperare gli allegati
```csharp
IList<Attachment> attachments = viewer.GetAttachments();
```
Recuperare l'elenco degli allegati presenti nel documento.
## Passaggio 4: salva gli allegati
```csharp
foreach(Attachment attachment in attachments)
{
    string filePath = Path.Combine(outputDirectory, attachment.FileName);  
    viewer.SaveAttachment(attachment, File.OpenWrite(filePath)); 
}
```
Scorrere ogni allegato, definire il percorso del file e salvare l'allegato nella directory specificata.
## Passaggio 5: Visualizza il messaggio di successo
```csharp
Console.WriteLine($"\nAttachments saved successfully.\nCheck output in {outputDirectory}.");
```
Visualizza un messaggio di successo che indica il salvataggio riuscito degli allegati insieme al percorso della directory.

## Conclusione
L'integrazione di GroupDocs.Viewer for .NET nei flussi di lavoro di gestione dei documenti semplifica il processo di gestione degli allegati, offrendo efficienza e praticità. Seguendo la guida passo passo sopra descritta, gli utenti possono recuperare e salvare senza problemi gli allegati ai documenti nelle loro applicazioni .NET.
## Domande frequenti
### GroupDocs.Viewer per .NET può gestire vari formati di documenti?
Sì, GroupDocs.Viewer supporta un'ampia gamma di formati di documenti, inclusi PDF, documenti di Microsoft Office, immagini e altro ancora.
### È disponibile una prova gratuita per GroupDocs.Viewer per .NET?
 Sì, puoi accedere alla prova gratuita da[Qui](https://releases.groupdocs.com/).
### Come posso ottenere licenze temporanee per GroupDocs.Viewer per .NET?
 È possibile acquisire licenze temporanee da[questo link](https://purchase.groupdocs.com/temporary-license/).
### Dove posso trovare la documentazione per GroupDocs.Viewer per .NET?
 È disponibile una documentazione completa[Qui](https://reference.groupdocs.com/viewer/net/).
### Quali opzioni di supporto sono disponibili per GroupDocs.Viewer per .NET?
 Puoi chiedere assistenza al forum della community[Qui](https://forum.groupdocs.com/c/viewer/9).