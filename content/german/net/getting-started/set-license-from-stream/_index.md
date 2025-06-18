---
"description": "Optimieren Sie Ihre .NET-Anwendungen mit GroupDocs.Viewer für eine nahtlose Dokumentanzeige. Folgen Sie unserer Schritt-für-Schritt-Anleitung und integrieren Sie mühelos leistungsstarke Funktionen zur Dokumentanzeige."
"linktitle": "Lizenz vom Stream festlegen"
"second_title": "GroupDocs.Viewer .NET API"
"title": "Lizenz vom Stream festlegen"
"url": "/de/net/getting-started/set-license-from-stream/"
"weight": 11
---

# Lizenz vom Stream festlegen

## Einführung
Möchten Sie Ihre .NET-Anwendungen mit erweiterten Dokumentanzeigefunktionen erweitern? GroupDocs.Viewer für .NET bietet eine umfassende Lösung zur nahtlosen Integration von Dokumentanzeigefunktionen in Ihre Projekte. In diesem Tutorial erfahren Sie, wie Sie GroupDocs.Viewer für .NET nutzen, um Ihre Anwendungen mit leistungsstarken Dokumentanzeigefunktionen zu erweitern. 

![Lizenz aus Stream mit GroupDocs.Viewer für .NET festlegen](/viewer/getting-started/set-license-from-stream.png)

## Voraussetzungen
Bevor wir in den Integrationsprozess eintauchen, stellen Sie sicher, dass die folgenden Voraussetzungen erfüllt sind:
1. Grundkenntnisse der .NET-Entwicklung: Um diesem Tutorial folgen zu können, sind Kenntnisse in C# und dem .NET-Framework unerlässlich.
   
2. GroupDocs.Viewer für .NET-Paket: Stellen Sie sicher, dass Sie das GroupDocs.Viewer für .NET-Paket heruntergeladen und installiert haben. Sie erhalten es von der [Download-Link](https://releases.groupdocs.com/viewer/net/).
3. Zugriff auf die GroupDocs-Dokumentation: Behalten Sie die [Dokumentation](https://tutorials.groupdocs.com/viewer/net/) praktisch für Tutorials während des Integrationsprozesses.

## Namespaces importieren
Importieren Sie zunächst die erforderlichen Namespaces in Ihre .NET-Anwendung. Gehen Sie folgendermaßen vor:
### Schritt 1: Öffnen Sie Ihr .NET-Projekt.
Stellen Sie sicher, dass Ihr .NET-Projekt in Ihrer bevorzugten Entwicklungsumgebung geöffnet ist.
### Schritt 2: GroupDocs.Viewer-Namespace hinzufügen.
Fügen Sie in Ihrer Codedatei den folgenden Namespace hinzu, um auf die GroupDocs.Viewer-Funktionen zuzugreifen:
```csharp
using System;
using System.IO;
```
## Lizenz vom Stream festlegen
Im nächsten Schritt wird die Lizenz aus einem Stream eingerichtet. Befolgen Sie diese detaillierten Schritte:
### Schritt 1: Ausgabeverzeichnis definieren.
Legen Sie das Verzeichnis fest, in dem Ihre Dokumente gespeichert werden, indem Sie das Ausgabeverzeichnis definieren:
```csharp
string outputDirectory = "Your Document Directory";
```
### Schritt 2: Überprüfen Sie, ob die Lizenzdatei vorhanden ist.
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
### Schritt 4: Umgang mit fehlender Lizenz.
Wenn die Lizenzdatei nicht gefunden wird, geben Sie Anweisungen zum Erwerb einer Lizenz:
```csharp
else
{
    Console.WriteLine("\nWe do not ship any license with this example. " +
                      "\nVisit the GroupDocs site to obtain either a temporary or permanent license. " +
                      "\nLearn more about licensing at https://purchase.groupdocs.com/faqs/licensing. " +
                      "\nLearn how to request a temporary license at https://purchase.groupdocs.com/temporary-license.");
}
```

## Abschluss
Herzlichen Glückwunsch! Sie haben gelernt, wie Sie GroupDocs.Viewer für .NET erfolgreich in Ihre Anwendungen integrieren. Mit diesem leistungsstarken Tool können Sie nun mühelos verschiedene Dokumentformate in Ihren .NET-Projekten anzeigen und so die Benutzerfreundlichkeit und Produktivität steigern.
## Häufig gestellte Fragen
### Benötige ich eine Lizenz, um GroupDocs.Viewer für .NET zu verwenden?
Ja, Sie benötigen eine Lizenz, um GroupDocs.Viewer für .NET zu nutzen. Sie können eine temporäre oder permanente Lizenz von der GroupDocs-Website erhalten.
### Kann ich GroupDocs.Viewer in meine ASP.NET-Anwendung integrieren?
Absolut! GroupDocs.Viewer für .NET lässt sich nahtlos in Desktop- und Webanwendungen integrieren, einschließlich ASP.NET.
### Welche Dokumentformate werden von GroupDocs.Viewer unterstützt?
GroupDocs.Viewer unterstützt eine Vielzahl von Dokumentformaten, darunter PDF, Microsoft Office (Word, Excel, PowerPoint), Bilder und mehr.
### Ist GroupDocs.Viewer mit .NET Core kompatibel?
Ja, GroupDocs.Viewer für .NET ist sowohl mit .NET Framework als auch mit .NET Core kompatibel.
### Kann ich die Viewer-Oberfläche entsprechend dem Design meiner Anwendung anpassen?
Ja, GroupDocs.Viewer bietet umfangreiche Anpassungsoptionen, sodass Sie die Viewer-Oberfläche nahtlos an das Design Ihrer Anwendung anpassen können.