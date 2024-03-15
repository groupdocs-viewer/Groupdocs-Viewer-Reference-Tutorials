---
title: Imposta la licenza a consumo
linktitle: Imposta la licenza a consumo
second_title: API GroupDocs.Viewer .NET
description: Migliora le tue applicazioni .NET con GroupDocs.Viewer per una visualizzazione fluida dei documenti. Integra facilmente le funzionalità di rendering dei documenti nei tuoi progetti.
type: docs
weight: 12
url: /it/net/getting-started/set-metered-license/
---
## introduzione
Nel mondo dello sviluppo .NET, incorporare potenti funzionalità di visualizzazione dei documenti nelle applicazioni è essenziale per migliorare l'esperienza e la funzionalità dell'utente. GroupDocs.Viewer per .NET offre una soluzione solida per integrare perfettamente le funzionalità di visualizzazione dei documenti nei tuoi progetti .NET. Che tu stia lavorando con PDF, documenti di Microsoft Office o vari formati di immagine, GroupDocs.Viewer semplifica il processo di rendering e visualizzazione di questi documenti all'interno delle tue applicazioni.
## Prerequisiti
Prima di approfondire l'implementazione di GroupDocs.Viewer per .NET, assicurati di disporre dei seguenti prerequisiti:
### 1. Installa GroupDocs.Viewer per .NET
 Per iniziare, dovrai scaricare e installare GroupDocs.Viewer per .NET. È possibile trovare il collegamento per il download[Qui](https://releases.groupdocs.com/viewer/net/). Seguire le istruzioni di installazione fornite per configurare la libreria nel proprio ambiente di sviluppo.
### 2. Ottieni la licenza misurata
Per utilizzare GroupDocs.Viewer per .NET, è necessario ottenere una licenza a consumo. Questa licenza ti consente di controllare e monitorare l'utilizzo dell'API in base a quote predefinite. Segui i passaggi seguenti per impostare la tua licenza a consumo:

## Importa spazi dei nomi
Innanzitutto, assicurati di importare gli spazi dei nomi necessari per accedere alle funzionalità fornite da GroupDocs.Viewer per .NET:
```csharp
using System;
```

Ora suddividiamo il codice di esempio fornito in più passaggi:
## Passaggio 1: dichiarare le chiavi pubbliche e private
Dichiara variabili per archiviare le tue chiavi pubbliche e private:
```csharp
string publicKey = "YOUR_PUBLIC_KEY";
string privateKey = "YOUR_PRIVATE_KEY";
```
 Assicurarsi di sostituire`"YOUR_PUBLIC_KEY"` E`"YOUR_PRIVATE_KEY"` con le tue vere chiavi.
## Passaggio 2: imposta la licenza a consumo
Controlla se viene fornita la chiave pubblica. In caso contrario, chiedere all'utente di impostare le chiavi:
```csharp
if (string.IsNullOrEmpty(publicKey))
{
    Console.WriteLine("\n[SetMeteredLicense] Please make sure to set Metered keys. Learn more at https://Purchase.groupdocs.com/faqs/licensing/metered.");
    return;
}
```
## Passaggio 3: inizializzare l'oggetto misurato e impostare la licenza
Inizializza l'oggetto Metered e imposta la licenza misurata utilizzando le chiavi pubblica e privata:
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
In conclusione, GroupDocs.Viewer per .NET fornisce una soluzione completa per incorporare funzionalità di visualizzazione di documenti nelle applicazioni .NET. Seguendo i passaggi descritti, puoi facilmente impostare una licenza a consumo e iniziare a sfruttare le funzionalità di GroupDocs.Viewer nei tuoi progetti.
## Domande frequenti
### D: Dove posso trovare la documentazione per GroupDocs.Viewer per .NET?
 Puoi trovare la documentazione[Qui](https://reference.groupdocs.com/viewer/net/).
### D: È disponibile una prova gratuita per GroupDocs.Viewer per .NET?
 Sì, puoi accedere alla prova gratuita[Qui](https://releases.groupdocs.com/).
### D: Come posso ottenere licenze temporanee a scopo di test?
 È possibile ottenere licenze temporanee[Qui](https://purchase.groupdocs.com/temporary-license/).
### D: Dove posso chiedere supporto o porre domande relative a GroupDocs.Viewer per .NET?
 Puoi cercare supporto e porre domande sul forum GroupDocs.Viewer[Qui](https://forum.groupdocs.com/c/viewer/9).
### D: Dove posso acquistare una licenza per GroupDocs.Viewer per .NET?
 È possibile acquistare una licenza[Qui](https://purchase.groupdocs.com/buy).