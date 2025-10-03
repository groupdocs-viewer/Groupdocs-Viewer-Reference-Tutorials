---
"description": "Migliora le tue applicazioni .NET con GroupDocs.Viewer per una visualizzazione fluida dei documenti. Integra facilmente le funzionalità di rendering dei documenti nei tuoi progetti."
"linktitle": "Imposta licenza a consumo"
"second_title": "API .NET di GroupDocs.Viewer"
"title": "Imposta licenza a consumo"
"url": "/it/net/getting-started/set-metered-license/"
"weight": 12
type: docs
---
# Imposta licenza a consumo

## Introduzione
Nel mondo dello sviluppo .NET, integrare potenti funzionalità di visualizzazione dei documenti nelle applicazioni è essenziale per migliorare l'esperienza utente e le funzionalità. GroupDocs.Viewer per .NET offre una soluzione affidabile per integrare perfettamente le funzionalità di visualizzazione dei documenti nei progetti .NET. Che si lavori con PDF, documenti di Microsoft Office o vari formati di immagine, GroupDocs.Viewer semplifica il processo di rendering e visualizzazione di questi documenti all'interno delle applicazioni.

![Imposta licenza a consumo con GroupDocs.Viewer per .NET](/viewer/getting-started/set-metered-license.png)

## Prerequisiti
Prima di immergerti nell'implementazione di GroupDocs.Viewer per .NET, assicurati di avere i seguenti prerequisiti:
### 1. Installa GroupDocs.Viewer per .NET
Per iniziare, è necessario scaricare e installare GroupDocs.Viewer per .NET. Il link per il download è disponibile qui. [Qui](https://releases.groupdocs.com/viewer/net/)Seguire le istruzioni di installazione fornite per configurare la libreria nel proprio ambiente di sviluppo.
### 2. Ottieni la licenza a consumo
Per utilizzare GroupDocs.Viewer per .NET, è necessario ottenere una licenza a consumo. Questa licenza consente di controllare e monitorare l'utilizzo delle API in base a quote predefinite. Seguire i passaggi seguenti per configurare la licenza a consumo:

## Importa spazi dei nomi
Per prima cosa, assicurati di importare gli spazi dei nomi necessari per accedere alle funzionalità fornite da GroupDocs.Viewer per .NET:
```csharp
using System;
```

Ora scomponiamo il codice di esempio fornito in più passaggi:
## Passaggio 1: dichiarare le chiavi pubbliche e private
Dichiara le variabili per memorizzare le tue chiavi pubbliche e private:
```csharp
string publicKey = "YOUR_PUBLIC_KEY";
string privateKey = "YOUR_PRIVATE_KEY";
```
Assicurarsi di sostituire `"YOUR_PUBLIC_KEY"` E `"YOUR_PRIVATE_KEY"` con le tue chiavi vere.
## Passaggio 2: imposta la licenza a consumo
Verificare se la chiave pubblica è stata fornita. In caso contrario, chiedere all'utente di impostare le chiavi:
```csharp
if (string.IsNullOrEmpty(publicKey))
{
    Console.WriteLine("\n[SetMeteredLicense] Please make sure to set Metered keys. Learn more at https://purchase.groupdocs.com/faqs/licensing/metered.");
    return;
}
```
## Passaggio 3: inizializzare l'oggetto misurato e impostare la licenza
Inizializza l'oggetto Metered e imposta la licenza a consumo utilizzando le tue chiavi pubblica e privata:
```csharp
Metered metered = new Metered();
metered.SetMeteredKey(publicKey, privateKey);
```
## Passaggio 4: messaggio di conferma
Visualizza un messaggio di conferma che indica che la licenza è stata impostata correttamente:
```csharp
Console.WriteLine("License set successfully.");
```

## Conclusione
In conclusione, GroupDocs.Viewer per .NET offre una soluzione completa per integrare funzionalità di visualizzazione dei documenti nelle applicazioni .NET. Seguendo i passaggi descritti, è possibile configurare facilmente una licenza a consumo e iniziare a sfruttare le funzionalità di GroupDocs.Viewer nei propri progetti.
## Domande frequenti
### D: Dove posso trovare la documentazione per GroupDocs.Viewer per .NET?
Puoi trovare la documentazione [Qui](https://tutorials.groupdocs.com/viewer/net/).
### D: È disponibile una versione di prova gratuita di GroupDocs.Viewer per .NET?
Sì, puoi accedere alla prova gratuita [Qui](https://releases.groupdocs.com/).
### D: Come posso ottenere licenze temporanee per scopi di prova?
È possibile ottenere licenze temporanee [Qui](https://purchase.groupdocs.com/temporary-license/).
### D: Dove posso cercare supporto o porre domande relative a GroupDocs.Viewer per .NET?
Puoi cercare supporto e porre domande sul forum GroupDocs.Viewer [Qui](https://forum.groupdocs.com/c/viewer/9).
### D: Dove posso acquistare una licenza per GroupDocs.Viewer per .NET?
Puoi acquistare una licenza [Qui](https://purchase.groupdocs.com/buy).