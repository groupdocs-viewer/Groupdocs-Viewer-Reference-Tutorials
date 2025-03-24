---
title: Aggiungi filigrana nel documento
linktitle: Aggiungi filigrana nel documento
second_title: API GroupDocs.Viewer .NET
description: Scopri come aggiungere facilmente filigrane ai documenti utilizzando GroupDocs.Viewer per .NET. Migliora la sicurezza e il branding dei documenti con questo tutorial facile da seguire.
weight: 10
url: /it/net/rendering-options/add-watermark/
---

# Aggiungi filigrana nel documento

## introduzione
Nell'era digitale di oggi, la gestione e la visualizzazione fluida di vari formati di documenti è una necessità per molte aziende e privati. Fortunatamente, con strumenti come GroupDocs.Viewer per .NET, gestire i documenti diventa un gioco da ragazzi. Questa potente libreria .NET consente agli sviluppatori di integrare facilmente la funzionalità di visualizzazione dei documenti nelle loro applicazioni, consentendo agli utenti di visualizzare i documenti senza bisogno del software originale che li ha creati.
## Prerequisiti
Prima di immergerti nell'utilizzo di GroupDocs.Viewer for .NET per aggiungere filigrane ai documenti, assicurati di avere quanto segue:
1. Configurazione dell'ambiente: disporre di un ambiente di sviluppo configurato con .NET Framework o .NET Core installato.
2.  GroupDocs.Viewer per .NET: scaricare e installare la libreria GroupDocs.Viewer per .NET dalla[pagina di download](https://releases.groupdocs.com/viewer/net/).
3. File di documenti: prepara i file di documenti con cui desideri lavorare, come DOCX, PDF o altri.
4. Conoscenza di base di C#: la familiarità con il linguaggio di programmazione C# è necessaria per implementare gli esempi di codice.

## Importa spazi dei nomi
Prima di iniziare ad aggiungere filigrane ai documenti utilizzando GroupDocs.Viewer per .NET, assicurati di importare gli spazi dei nomi richiesti nel codice C#. Questo passaggio consente di accedere senza problemi alle classi e ai metodi forniti dalla libreria.

```csharp
using System;
using System.IO;
using GroupDocs.Viewer.Options;
```

Ora esaminiamo il processo di aggiunta di una filigrana a un documento utilizzando GroupDocs.Viewer per .NET. Segui questi passaggi per integrare perfettamente la funzionalità di filigrana nella tua applicazione.
## Passaggio 1: imposta la directory di output
```csharp
string outputDirectory = "Your Document Directory";
```
Specifica la directory in cui desideri salvare i file di output dopo aver applicato la filigrana.
## Passaggio 2: definire il formato del percorso del file di paging
```csharp
string pageFilePathFormat = Path.Combine(outputDirectory, "page_{0}.html");
```
Imposta il formato per i percorsi dei file delle pagine renderizzate. In questo esempio verranno generati file HTML con numeri di pagina.
## Passaggio 3: istanziare l'oggetto visualizzatore
```csharp
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_DOCX))
{
    // Il codice continua nel passaggio successivo...
}
```
Crea un'istanza della classe Viewer, passando il percorso del file del documento come parametro. In questo esempio, stiamo utilizzando un file DOCX di esempio.
## Passaggio 4: configura le opzioni di visualizzazione HTML
```csharp
HtmlViewOptions options = HtmlViewOptions.ForEmbeddedResources(pageFilePathFormat);
options.Watermark = new Watermark("This is a watermark");
```
Configura le opzioni di visualizzazione HTML, incluso il testo della filigrana che desideri aggiungere al documento.
## Passaggio 5: Visualizza il documento con filigrana
```csharp
viewer.View(options);
```
Richiamare il metodo View dell'oggetto Viewer, passando le opzioni configurate. Ciò renderà il documento con la filigrana specificata.
## Passaggio 6: Visualizza il percorso della directory di output
```csharp
Console.WriteLine($"\nSource document rendered successfully.\nCheck output in {outputDirectory}.");
```
Informare l'utente del corretto rendering del documento e indicare la directory in cui vengono salvati i file di output.

## Conclusione
GroupDocs.Viewer per .NET fornisce un modo conveniente per aggiungere filigrane ai documenti a livello di codice. Seguendo i passaggi descritti in questo tutorial, puoi integrare perfettamente la funzionalità di filigrana nelle tue applicazioni .NET, migliorando la sicurezza e il branding dei documenti.
## Domande frequenti
### Posso personalizzare l'aspetto della filigrana?
Sì, puoi personalizzare varie proprietà della filigrana, come testo, carattere, colore, dimensione e posizione.
### GroupDocs.Viewer supporta la visualizzazione di documenti da fonti remote?
Sì, GroupDocs.Viewer supporta la visualizzazione di documenti dalla memoria locale e da URL remoti.
### È disponibile una versione di prova per GroupDocs.Viewer per .NET?
Sì, puoi scaricare una versione di prova gratuita da[Qui](https://releases.groupdocs.com/).
### Posso aggiungere filigrane a più pagine di un documento?
Assolutamente sì, GroupDocs.Viewer consente di aggiungere filigrane a singole pagine o a tutte le pagine di un documento.
### Come posso ottenere supporto o assistenza in caso di problemi?
 Puoi cercare aiuto e supporto nei forum della community di GroupDocs[Qui](https://forum.groupdocs.com/c/viewer/9).