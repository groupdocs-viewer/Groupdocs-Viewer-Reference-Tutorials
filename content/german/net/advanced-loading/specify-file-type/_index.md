---
title: Geben Sie beim Laden von Dokumenten den Dateityp an
linktitle: Geben Sie beim Laden von Dokumenten den Dateityp an
second_title: GroupDocs.Viewer .NET-API
description: Erfahren Sie, wie Sie beim Laden von Dokumenten mit GroupDocs.Viewer für .NET den Dateityp angeben. Rendern Sie verschiedene Formate in Ihren .NET-Anwendungen präzise.
weight: 10
url: /de/net/advanced-loading/specify-file-type/
---

# Geben Sie beim Laden von Dokumenten den Dateityp an

## Einführung
GroupDocs.Viewer für .NET ist eine vielseitige API zum Rendern von Dokumenten, die eine Vielzahl von Dateiformaten unterstützt, darunter DOCX, PDF, PPTX und mehr. Durch die Angabe des Dateityps beim Laden von Dokumenten können Sie eine genaue Wiedergabe und ein reibungsloses Anzeigeerlebnis für Ihre Benutzer gewährleisten.
## Voraussetzungen
Bevor Sie beginnen, stellen Sie sicher, dass Sie die folgenden Voraussetzungen erfüllen:
- Grundkenntnisse in C# und .NET Framework.
- Visual Studio ist auf Ihrem System installiert.
- GroupDocs.Viewer für .NET in Ihrem Projekt installiert. Sie können es herunterladen unter[Hier](https://releases.groupdocs.com/viewer/net/).
##
## Namespaces importieren
Zunächst müssen Sie die erforderlichen Namespaces in Ihren C#-Code importieren. Diese Namespaces bieten Zugriff auf die Klassen und Methoden, die für die Dokumentwiedergabe erforderlich sind.
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
## Schritt 2: Definieren Sie das Format des Seitendateipfads
Geben Sie das Format für die Benennung der ausgegebenen HTML-Dateien für jede Seite des Dokuments an.
```csharp
string pageFilePathFormat = Path.Combine(outputDirectory, "page_{0}.html");
```
## Schritt 3: Legen Sie die Ladeoptionen fest
 Erstellen Sie eine Instanz von`LoadOptions` Klasse und legen Sie den gewünschten Dateityp fest.
```csharp
LoadOptions loadOptions = new LoadOptions
{
    FileType = FileType.DOCX
};
```
## Schritt 4: Dokument laden und rendern
 Benutzen Sie die`Viewer` Klasse, um das Dokument zu laden und in das HTML-Format zu rendern.
```csharp
using (Viewer viewer = new Viewer("YourDocument.docx", loadOptions))
{
    HtmlViewOptions options = HtmlViewOptions.ForEmbeddedResources(pageFilePathFormat);
    viewer.View(options);
}
```
## Schritt 5: Erfolgsmeldung anzeigen
Informieren Sie den Benutzer darüber, dass das Dokument erfolgreich gerendert wurde, und geben Sie den Speicherort der Ausgabedateien an.
```csharp
Console.WriteLine($"\nSource document rendered successfully.\nCheck output in {outputDirectory}.");
```

## Abschluss
In diesem Tutorial haben wir gelernt, wie Sie GroupDocs.Viewer für .NET verwenden, um beim Laden von Dokumenten den Dateityp anzugeben. Durch Befolgen dieser einfachen Schritte können Sie eine genaue Darstellung verschiedener Dokumentformate in Ihren .NET-Anwendungen sicherstellen.
## FAQs
### Kann ich mit GroupDocs.Viewer für .NET andere Dokumente als DOCX rendern?
Ja, GroupDocs.Viewer unterstützt eine Vielzahl von Dateiformaten, darunter PDF, PPTX, XLSX und mehr.
### Ist GroupDocs.Viewer für .NET mit .NET Core kompatibel?
Ja, GroupDocs.Viewer für .NET ist sowohl mit .NET Framework als auch mit .NET Core kompatibel.
### Kann ich die von GroupDocs.Viewer generierten HTML-Ausgabedateien anpassen?
Ja, Sie können die HTML-Ausgabe mithilfe verschiedener Optionen der API anpassen.
### Erfordert GroupDocs.Viewer für .NET externe Abhängigkeiten?
Nein, GroupDocs.Viewer für .NET ist eine eigenständige Bibliothek und erfordert keine externen Abhängigkeiten.
### Gibt es eine Testversion für GroupDocs.Viewer für .NET?
Ja, Sie können eine kostenlose Testversion herunterladen von[Hier](https://releases.groupdocs.com/viewer/net/).