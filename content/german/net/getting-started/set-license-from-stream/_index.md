---
title: Lizenz aus Stream festlegen
linktitle: Lizenz aus Stream festlegen
second_title: GroupDocs.Viewer .NET-API
description: Erweitern Sie Ihre .NET-Anwendungen mit GroupDocs.Viewer für eine nahtlose Dokumentenanzeige. Befolgen Sie unsere Schritt-für-Schritt-Anleitung und integrieren Sie mühelos leistungsstarke Funktionen zur Dokumentenanzeige.
weight: 11
url: /de/net/getting-started/set-license-from-stream/
---
## Einführung
Möchten Sie Ihre .NET-Anwendungen mit erweiterten Funktionen zur Dokumentenanzeige ausstatten? GroupDocs.Viewer für .NET bietet eine umfassende Lösung zur nahtlosen Integration von Dokumentenanzeigefunktionen in Ihre Projekte. In diesem Tutorial befassen wir uns mit dem Prozess der Nutzung von GroupDocs.Viewer für .NET, um Ihre Anwendungen mit leistungsstarken Dokumentanzeigefunktionen zu bereichern. 
## Voraussetzungen
Bevor wir uns mit dem Integrationsprozess befassen, stellen Sie sicher, dass die folgenden Voraussetzungen erfüllt sind:
1. Grundkenntnisse der .NET-Entwicklung: Um diesem Tutorial folgen zu können, sind Kenntnisse mit C# und dem .NET-Framework unerlässlich.
   
2.  GroupDocs.Viewer für .NET-Paket: Stellen Sie sicher, dass Sie das GroupDocs.Viewer für .NET-Paket heruntergeladen und installiert haben. Sie können es bei der erhalten[Download-Link](https://releases.groupdocs.com/viewer/net/).
3.  Zugriff auf die GroupDocs-Dokumentation: Bewahren Sie die auf[Dokumentation](https://tutorials.groupdocs.com/viewer/net/) Praktisch als Referenz während des Integrationsprozesses.

## Namespaces importieren
Importieren Sie zunächst die erforderlichen Namespaces in Ihre .NET-Anwendung. Folge diesen Schritten:
### Schritt 1: Öffnen Sie Ihr .NET-Projekt.
Stellen Sie sicher, dass Ihr .NET-Projekt in Ihrer bevorzugten Entwicklungsumgebung geöffnet ist.
### Schritt 2: GroupDocs.Viewer-Namespace hinzufügen.
Fügen Sie in Ihrer Codedatei den folgenden Namespace hinzu, um auf die GroupDocs.Viewer-Funktionen zuzugreifen:
```csharp
using System;
using System.IO;
```
## Lizenz aus Stream festlegen
Der nächste Schritt besteht darin, die Lizenz aus einem Stream festzulegen. Befolgen Sie diese detaillierten Schritte:
### Schritt 1: Ausgabeverzeichnis definieren.
Legen Sie das Verzeichnis fest, in dem Ihre Dokumente gespeichert werden, indem Sie das Ausgabeverzeichnis definieren:
```csharp
string outputDirectory = "Your Document Directory";
```
### Schritt 2: Überprüfen Sie das Vorhandensein der Lizenzdatei.
Überprüfen Sie, ob die Lizenzdatei in Ihrem Projektverzeichnis vorhanden ist:
```csharp
if (File.Exists(Utils.LicensePath))
```
### Schritt 3: Lizenz festlegen.
Wenn die Lizenzdatei vorhanden ist, legen Sie die Lizenz mithilfe des bereitgestellten Streams fest:
```csharp
using (FileStream stream = File.OpenRead(Utils.LicensePath))
{
    License license = new License();
    license.SetLicense(stream);
}
```
### Schritt 4: Behandeln Sie das Fehlen einer Lizenz.
Wenn die Lizenzdatei nicht gefunden wird, geben Sie Anweisungen zum Erwerb einer Lizenz:
```csharp
else
{
    Console.WriteLine("\nWe do not ship any license with this example. " +
                      "\nVisit the GroupDocs site to obtain either a temporary or permanent license. " +
                      "\nLearn more about licensing at https://Purchase.groupdocs.com/faqs/licensing. " +
                      "\nLearn how to request a temporary license at https://Purchase.groupdocs.com/temporary-license.");
}
```

## Abschluss
Glückwunsch! Sie haben erfolgreich gelernt, wie Sie GroupDocs.Viewer für .NET in Ihre Anwendungen integrieren. Mit diesem leistungsstarken Tool können Sie jetzt mühelos verschiedene Dokumentformate in Ihren .NET-Projekten anzeigen und so die Benutzererfahrung und Produktivität verbessern.
## FAQs
### Benötige ich eine Lizenz, um GroupDocs.Viewer für .NET zu verwenden?
Ja, Sie benötigen eine Lizenz, um GroupDocs.Viewer für .NET nutzen zu können. Auf der GroupDocs-Website können Sie entweder eine temporäre oder eine permanente Lizenz erwerben.
### Kann ich GroupDocs.Viewer in meine ASP.NET-Anwendung integrieren?
Absolut! GroupDocs.Viewer für .NET lässt sich nahtlos in Desktop- und Webanwendungen integrieren, einschließlich ASP.NET.
### Welche Dokumentformate werden von GroupDocs.Viewer unterstützt?
GroupDocs.Viewer unterstützt eine Vielzahl von Dokumentformaten, darunter PDF, Microsoft Office (Word, Excel, PowerPoint), Bilder und mehr.
### Ist GroupDocs.Viewer mit .NET Core kompatibel?
Ja, GroupDocs.Viewer für .NET ist sowohl mit .NET Framework als auch mit .NET Core kompatibel.
### Kann ich die Viewer-Oberfläche an das Thema meiner Anwendung anpassen?
Ja, GroupDocs.Viewer bietet umfangreiche Anpassungsoptionen, sodass Sie die Viewer-Oberfläche nahtlos an das Thema Ihrer Anwendung anpassen können.