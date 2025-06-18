---
"description": "Entdecken Sie, wie Sie mit GroupDocs.Viewer Dokumente in .NET nahtlos in JPG/PNG rendern und so die Benutzererfahrung und Produktivität verbessern."
"linktitle": "Dokument in JPGPNG rendern"
"second_title": "GroupDocs.Viewer .NET API"
"title": "Dokument in JPGPNG rendern"
"url": "/de/net/rendering-documents-images/render-jpg-png/"
"weight": 10
---

# Dokument in JPGPNG rendern

## Einführung

In der .NET-Entwicklung ist die effiziente Dokumentenverwaltung für verschiedene Anwendungen unerlässlich. Ob Sie ein Dokumentenmanagementsystem, eine E-Commerce-Plattform oder eine inhaltsreiche Anwendung entwickeln – die nahtlose Anzeige von Dokumenten ist entscheidend. Hier kommt GroupDocs.Viewer für .NET ins Spiel und bietet eine umfassende Lösung für die Darstellung von Dokumenten in verschiedenen Formaten wie JPG und PNG.

## Voraussetzungen

Bevor Sie sich in die Verwendung von GroupDocs.Viewer für .NET stürzen, müssen Sie einige Voraussetzungen sicherstellen:

1. .NET-Entwicklungsumgebung: Stellen Sie sicher, dass auf Ihrem Computer eine funktionierende .NET-Entwicklungsumgebung eingerichtet ist. Dazu gehört auch die Installation des .NET SDK.

2. GroupDocs.Viewer-Lizenz: Erwerben Sie eine gültige Lizenz für GroupDocs.Viewer. Sie können entweder eine Lizenz erwerben oder eine temporäre Lizenz zu Testzwecken verwenden.

3. Installation: Laden Sie GroupDocs.Viewer für .NET von der bereitgestellten [Download-Link](https://releases.groupdocs.com/viewer/net/).

4. Dokumentdateien: Halten Sie die Dokumentdateien bereit, die Sie rendern möchten. GroupDocs.Viewer unterstützt verschiedene Formate, darunter DOCX, PDF, PPT und mehr.

## Namespaces importieren

Um mit dem Rendern von Dokumenten mit GroupDocs.Viewer für .NET zu beginnen, müssen Sie die erforderlichen Namespaces in Ihr Projekt importieren. Dadurch können Sie auf die von der Bibliothek bereitgestellten Funktionen zugreifen.

```csharp
using System;
using System.IO;
using GroupDocs.Viewer.Options;
```

Das Rendern eines Dokuments im JPG- oder PNG-Format ist mit GroupDocs.Viewer für .NET ein unkomplizierter Vorgang. Nachfolgend finden Sie eine Schritt-für-Schritt-Anleitung, die Ihnen dabei hilft:

## Schritt 1: Ausgabeverzeichnis definieren

Definieren Sie zunächst das Verzeichnis, in dem die gerenderten Seiten gespeichert werden sollen. Dieses Verzeichnis muss vorhanden und für die Anwendung zugänglich sein.

```csharp
string outputDirectory = "Your Document Directory";
```

## Schritt 2: Definieren Sie das Auslagerungsdateipfadformat

Geben Sie das Format für die Dateipfade jeder gerenderten Seite an. GroupDocs.Viewer ersetzt `{0}` mit der Seitenzahl beim Speichern der Dateien.

```csharp
string pageFilePathFormat = Path.Combine(outputDirectory, "page_{0}.jpg");
```

## Schritt 3: Viewer-Objekt instanziieren

Erstellen Sie eine Instanz des `Viewer` Klasse, indem Sie den Pfad zur Dokumentdatei angeben, die Sie rendern möchten.

```csharp
using (Viewer viewer = new Viewer("Path_to_Your_Document"))
{
    // Code zum Rendern kommt hierhin
}
```

## Schritt 4: Rendering-Optionen definieren

Legen Sie die Rendering-Optionen entsprechend Ihren Anforderungen fest. Für die JPG/PNG-Darstellung verwenden Sie `JpgViewOptions` oder `PngViewOptions`.

```csharp
JpgViewOptions options = new JpgViewOptions(pageFilePathFormat);
```

## Schritt 5: Dokument rendern

Rufen Sie den `View` Methode der `Viewer` Objekt und übergeben Sie die zuvor erstellten Rendering-Optionen.

```csharp
viewer.View(options);
```

## Schritt 6: Ergebnisse ausgeben

Sobald der Rendervorgang abgeschlossen ist, können Sie den Benutzer über das erfolgreiche Rendern informieren und das Verzeichnis angeben, in dem die gerenderten Seiten gespeichert sind.

```csharp
Console.WriteLine($"\nSource document rendered successfully.\nCheck output in {outputDirectory}.");
```

## Abschluss

Zusammenfassend lässt sich sagen, dass GroupDocs.Viewer für .NET eine leistungsstarke Lösung zum Rendern von Dokumenten in verschiedenen Formaten, einschließlich JPG und PNG, bietet. Mit den in diesem Tutorial beschriebenen Schritten können Sie die Dokumentrendering-Funktionalität nahtlos in Ihre .NET-Anwendungen integrieren und so Benutzerfreundlichkeit und Produktivität steigern.

## Häufig gestellte Fragen

### F: Kann ich mit GroupDocs.Viewer für .NET andere Dokumente als DOCX rendern?

A: Ja, GroupDocs.Viewer unterstützt eine Vielzahl von Dokumentformaten, darunter PDF, PPT, XLS und mehr.

### F: Gibt es eine kostenlose Testversion für GroupDocs.Viewer für .NET?

A: Ja, Sie können eine kostenlose Testversion herunterladen von [Hier](https://releases.groupdocs.com/).

### F: Wie kann ich eine temporäre Lizenz zu Evaluierungszwecken erhalten?

A: Sie können eine temporäre Lizenz anfordern bei [Hier](https://purchase.groupdocs.com/temporary-license/).

### F: Wo finde ich Dokumentation für GroupDocs.Viewer für .NET?

A: Detaillierte Dokumentation ist verfügbar [Hier](https://tutorials.groupdocs.com/viewer/net/).

### F: Wo kann ich Support erhalten oder Fragen zu GroupDocs.Viewer für .NET stellen?

A: Sie können das Support-Forum besuchen [Hier](https://forum.groupdocs.com/c/viewer/9) um Hilfe.