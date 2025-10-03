---
"description": "Erfahren Sie, wie Sie beim Laden von Dokumenten mit GroupDocs.Viewer für .NET den Dateityp angeben. Rendern Sie verschiedene Formate präzise in Ihren .NET-Anwendungen."
"linktitle": "Geben Sie beim Laden von Dokumenten den Dateityp an"
"second_title": "GroupDocs.Viewer .NET API"
"title": "Geben Sie beim Laden von Dokumenten den Dateityp an"
"url": "/de/net/advanced-loading/specify-file-type/"
"weight": 10
type: docs
---
# Geben Sie beim Laden von Dokumenten den Dateityp an

## Einführung
GroupDocs.Viewer für .NET ist eine vielseitige API zur Dokumentdarstellung, die eine Vielzahl von Dateiformaten unterstützt, darunter DOCX, PDF, PPTX und mehr. Durch die Angabe des Dateityps beim Laden von Dokumenten gewährleisten Sie eine präzise Darstellung und ein reibungsloses Anzeigeerlebnis für Ihre Benutzer.

![Geben Sie den Dateityp beim Laden von Dokumenten in GroupDocs.Viewer für .NET an](/viewer/advanced-loading/specify-file-type-when-loading-documents-img.png)

## Voraussetzungen
Bevor Sie beginnen, stellen Sie sicher, dass Sie die folgenden Voraussetzungen erfüllen:
- Grundkenntnisse in C# und .NET Framework.
- Visual Studio ist auf Ihrem System installiert.
- GroupDocs.Viewer für .NET muss in Ihrem Projekt installiert sein. Sie können ihn herunterladen von [Hier](https://releases.groupdocs.com/viewer/net/).
##
## Namespaces importieren
Zunächst müssen Sie die erforderlichen Namespaces in Ihren C#-Code importieren. Diese Namespaces ermöglichen den Zugriff auf die für die Dokumentdarstellung erforderlichen Klassen und Methoden.
```csharp
using System;
using System.IO;
using GroupDocs.Viewer.Options;
```
## Schritt 1: Ausgabeverzeichnis einrichten
Definieren Sie das Verzeichnis, in dem Sie die gerenderten Dokumentseiten speichern möchten.
```csharp
string outputDirectory = "Your Document Directory";
```
## Schritt 2: Definieren Sie das Auslagerungsdateipfadformat
Geben Sie das Format für die Benennung der HTML-Ausgabedateien für jede Seite des Dokuments an.
```csharp
string pageFilePathFormat = Path.Combine(outputDirectory, "page_{0}.html");
```
## Schritt 3: Ladeoptionen festlegen
Erstellen Sie eine Instanz des `LoadOptions` Klasse und stellen Sie den gewünschten Dateityp ein.
```csharp
LoadOptions loadOptions = new LoadOptions
{
    FileType = FileType.DOCX
};
```
## Schritt 4: Dokument laden und rendern
Verwenden Sie die `Viewer` Klasse, um das Dokument zu laden und im HTML-Format darzustellen.
```csharp
using (Viewer viewer = new Viewer("YourDocument.docx", loadOptions))
{
    HtmlViewOptions options = HtmlViewOptions.ForEmbeddedResources(pageFilePathFormat);
    viewer.View(options);
}
```
## Schritt 5: Erfolgsmeldung anzeigen
Informieren Sie den Benutzer, dass das Dokument erfolgreich gerendert wurde, und geben Sie den Speicherort der Ausgabedateien an.
```csharp
Console.WriteLine($"\nSource document rendered successfully.\nCheck output in {outputDirectory}.");
```

## Abschluss
In diesem Tutorial haben wir gelernt, wie Sie mit GroupDocs.Viewer für .NET den Dateityp beim Laden von Dokumenten angeben. Mit diesen einfachen Schritten können Sie die korrekte Darstellung verschiedener Dokumentformate in Ihren .NET-Anwendungen sicherstellen.
## Häufig gestellte Fragen
### Kann ich mit GroupDocs.Viewer für .NET andere Dokumente als DOCX rendern?
Ja, GroupDocs.Viewer unterstützt eine Vielzahl von Dateiformaten, darunter PDF, PPTX, XLSX und mehr.
### Ist GroupDocs.Viewer für .NET mit .NET Core kompatibel?
Ja, GroupDocs.Viewer für .NET ist sowohl mit .NET Framework als auch mit .NET Core kompatibel.
### Kann ich die von GroupDocs.Viewer generierten HTML-Ausgabedateien anpassen?
Ja, Sie können die HTML-Ausgabe mithilfe verschiedener von der API bereitgestellter Optionen anpassen.
### Erfordert GroupDocs.Viewer für .NET externe Abhängigkeiten?
Nein, GroupDocs.Viewer für .NET ist eine eigenständige Bibliothek und erfordert keine externen Abhängigkeiten.
### Gibt es eine Testversion für GroupDocs.Viewer für .NET?
Ja, Sie können eine kostenlose Testversion herunterladen von [Hier](https://releases.groupdocs.com/viewer/net/).