---
"date": "2025-04-25"
"description": "Scopri come escludere font come Arial dalle conversioni HTML utilizzando GroupDocs.Viewer per .NET, garantendo un branding coerente su tutte le piattaforme."
"title": "Come escludere specifici font dall'output HTML utilizzando GroupDocs.Viewer per .NET"
"url": "/it/net/advanced-rendering/exclude-fonts-html-groupdocs-viewer-net/"
"weight": 1
---

# Come escludere i font dall'output HTML utilizzando GroupDocs.Viewer per .NET

## Introduzione

Quando si convertono documenti in formato HTML, mantenere il controllo sui font utilizzati è fondamentale, soprattutto per la coerenza del brand. Questo tutorial mostra come escludere font specifici, come Arial, utilizzando GroupDocs.Viewer per .NET. Seguendo questa guida, imparerai metodi efficaci per gestire il rendering dei font nelle trasformazioni da documento a HTML.

![Escludere caratteri specifici dall'output HTML in GroupDocs.Viewer per .NET](/viewer/advanced-rendering/exclude-specific-fonts-from-html-output-img.png)

### Cosa imparerai:
- Impostazione e configurazione di GroupDocs.Viewer per .NET
- Tecniche per escludere specifici font dall'output HTML
- Suggerimenti pratici per ottimizzare le prestazioni e l'integrazione con altri sistemi .NET
- Applicazioni pratiche di queste tecniche

## Prerequisiti

Prima di iniziare, assicurati di avere quanto segue:
- **Librerie e versioni**: GroupDocs.Viewer versione 25.3.0 o successiva.
- **Configurazione dell'ambiente**: Un ambiente di sviluppo configurato con .NET Framework o .NET Core.
- **Prerequisiti di conoscenza**Conoscenza di base dello sviluppo C# e .NET.

## Impostazione di GroupDocs.Viewer per .NET

### Istruzioni per l'installazione:

**Utilizzo della console di NuGet Package Manager:**
```bash
Install-Package GroupDocs.Viewer -Version 25.3.0
```

**Utilizzo della CLI .NET:**
```bash
dotnet add package GroupDocs.Viewer --version 25.3.0
```

### Acquisizione della licenza:
È possibile acquisire una prova gratuita o acquistare una licenza da [Pagina di acquisto di GroupDocs](https://purchase.groupdocs.com/buy)Per l'accesso temporaneo, valutare la possibilità di richiedere un [licenza temporanea](https://purchase.groupdocs.com/temporary-license/).

### Inizializzazione e configurazione di base:

Ecco come inizializzare GroupDocs.Viewer nel tuo progetto .NET:
```csharp
using System;
using System.IO;
using GroupDocs.Viewer;
using GroupDocs.Viewer.Options;

string outputDirectory = Path.Combine("YOUR_OUTPUT_DIRECTORY", "RenderedHTML");
string pageFilePathFormat = Path.Combine(outputDirectory, "page_{0}.html");

if (!Directory.Exists(outputDirectory))
{
    Directory.CreateDirectory(outputDirectory);
}

using (Viewer viewer = new Viewer("YOUR_DOCUMENT_DIRECTORY\\Sample.docx"))
{
    HtmlViewOptions options = HtmlViewOptions.ForEmbeddedResources(pageFilePathFormat);
    // Le tue configurazioni andranno qui
}
```
Questa configurazione garantisce che sarai pronto a manipolare il rendering dei documenti con GroupDocs.Viewer.

## Guida all'implementazione

### Esclusione dei font dall'output HTML

In questa sezione ci concentreremo su come escludere specifici font dall'output HTML utilizzando GroupDocs.Viewer per .NET. 

#### Fase 1: Preparare l'ambiente
Assicurarsi che la directory di output esista e sia configurata correttamente:
```csharp
string outputDirectory = Path.Combine("YOUR_OUTPUT_DIRECTORY", "RenderedHTML");
string pageFilePathFormat = Path.Combine(outputDirectory, "page_{0}.html");

if (!Directory.Exists(outputDirectory))
{
    Directory.CreateDirectory(outputDirectory);
}
```
Questo passaggio garantisce che i file renderizzati abbiano una posizione designata.

#### Passaggio 2: configurare le opzioni di visualizzazione HTML
Ecco come configurare il visualizzatore per visualizzare i file HTML delle risorse incorporate:
```csharp
using (Viewer viewer = new Viewer("YOUR_DOCUMENT_DIRECTORY\\Sample.docx"))
{
    HtmlViewOptions options = HtmlViewOptions.ForEmbeddedResources(pageFilePathFormat);
```
IL `HtmlViewOptions` L'oggetto è fondamentale per specificare come i documenti vengono renderizzati in HTML.

#### Passaggio 3: Escludi caratteri specifici
Per escludere il font Arial, modificare il `options` configurazione:
```csharp
options.FontsToExclude.Add("Arial");
```
Questa riga indica a GroupDocs.Viewer di omettere Arial da tutti i font incorporati nell'HTML di output. Specificando `FontsToExclude`, ottieni il controllo su come lo stile visivo del tuo documento viene mantenuto in diversi ambienti.

#### Passaggio 4: rendering del documento
Infine, esegui il rendering del documento con queste impostazioni:
```csharp
viewer.View(options);
```
Chiamando `View()`GroupDocs.Viewer elabora il documento in base alle opzioni specificate e lo restituisce in formato HTML senza i font esclusi.

### Suggerimenti per la risoluzione dei problemi
- Assicurarsi che i percorsi dei file siano impostati correttamente.
- Verifica di utilizzare una versione compatibile di GroupDocs.Viewer per .NET.
- Controlla attentamente i nomi dei font perché devono corrispondere esattamente, inclusa la distinzione tra maiuscole e minuscole.

## Applicazioni pratiche

### Casi d'uso:
1. **Branding coerente**: Escludi i font indesiderati per garantire che la tipografia del tuo marchio rimanga coerente su tutte le piattaforme.
2. **Integrazione Web**: Integrazione con sistemi CMS che richiedono font specifici per la coerenza del web design.
3. **Archiviazione dei documenti**: Archivia i documenti in formato HTML senza font estranei, riducendo le dimensioni dei file.

### Possibilità di integrazione:
- Sfrutta GroupDocs.Viewer nelle applicazioni .NET per creare soluzioni personalizzate per la visualizzazione dei documenti.
- Combinalo con framework come ASP.NET MVC o Blazor per il rendering dinamico dei documenti sul web.

## Considerazioni sulle prestazioni

Ottimizzare le prestazioni è fondamentale quando si gestiscono documenti di grandi dimensioni. Ecco alcuni suggerimenti:

- **Gestione delle risorse**Prestate attenzione all'utilizzo della memoria della vostra applicazione, soprattutto con file di grandi dimensioni.
- **Elaborazione batch**: Se applicabile, elaborare i documenti in batch per evitare di sovraccaricare le risorse del sistema.
- **Caching efficiente**: Implementare strategie di memorizzazione nella cache per i documenti a cui si accede di frequente.

## Conclusione

In questo tutorial, abbiamo esplorato come utilizzare GroupDocs.Viewer per .NET per escludere font specifici dall'output HTML. Seguendo questi passaggi, è possibile mantenere il controllo sulla presentazione visiva dei documenti convertiti. 

Per ulteriori approfondimenti, si consiglia di integrare le funzionalità più avanzate fornite da GroupDocs.Viewer o di esplorare tutte le sue funzionalità API.

## Sezione FAQ

**D1: Posso escludere più font contemporaneamente?**
Sì, basta chiamare `options.FontsToExclude.Add("FontName")` per ogni font che desideri escludere.

**D2: Cosa succede se il font specificato non viene trovato nel documento?**
GroupDocs.Viewer lo ignorerà e continuerà il rendering con i font disponibili.

**D3: Esiste un limite al numero di font che posso escludere?**
Non esiste un limite specifico, ma quando si esclude un numero elevato di font è opportuno considerare le implicazioni in termini di prestazioni.

**D4: Questa funzionalità può essere utilizzata con altri formati di output come PDF o immagini?**
GroupDocs.Viewer supporta vari formati, ma le specifiche di esclusione dei font possono variare. Consultare la documentazione per i dettagli.

**D5: Come posso gestire i diversi tipi di documenti utilizzando GroupDocs.Viewer?**
La libreria è versatile e supporta nativamente diversi formati di file. Consulta il riferimento API per le funzionalità supportate per ogni formato.

## Risorse
- **Documentazione**: [Documentazione di GroupDocs Viewer .NET](https://docs.groupdocs.com/viewer/net/)
- **Riferimento API**: [Riferimento API GroupDocs](https://reference.groupdocs.com/viewer/net/)
- **Scaricamento**: [Download di GroupDocs](https://releases.groupdocs.com/viewer/net/)
- **Acquistare**: [Acquista la licenza GroupDocs](https://purchase.groupdocs.com/buy)
- **Prova gratuita**: [Ottieni una prova gratuita](https://releases.groupdocs.com/viewer/net/)
- **Licenza temporanea**: [Richiedi licenza temporanea](https://purchase.groupdocs.com/temporary-license/)
- **Supporto**: [Forum di supporto di GroupDocs](https://forum.groupdocs.com/c/viewer/9)

Pronti a portare i vostri progetti di rendering di documenti a un livello superiore? Provate a implementare queste soluzioni oggi stesso!