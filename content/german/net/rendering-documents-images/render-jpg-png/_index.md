---
title: Rendern Sie das Dokument in JPGPNG
linktitle: Rendern Sie das Dokument in JPGPNG
second_title: GroupDocs.Viewer .NET-API
description: Entdecken Sie, wie Sie mit GroupDocs.Viewer Dokumente nahtlos in JPG/PNG in .NET rendern können, um die Benutzererfahrung und Produktivität zu verbessern.
weight: 10
url: /de/net/rendering-documents-images/render-jpg-png/
---
## Einführung

In der Welt der .NET-Entwicklung ist der effiziente Umgang mit Dokumenten für verschiedene Anwendungen von entscheidender Bedeutung. Unabhängig davon, ob Sie ein Dokumentenmanagementsystem, eine E-Commerce-Plattform oder eine inhaltsreiche Anwendung aufbauen, ist die Möglichkeit, Dokumente nahtlos anzuzeigen, von entscheidender Bedeutung. Hier kommt GroupDocs.Viewer für .NET ins Spiel und bietet eine umfassende Lösung zum Rendern von Dokumenten in verschiedene Formate wie JPG und PNG.

## Voraussetzungen

Bevor Sie GroupDocs.Viewer für .NET verwenden, müssen Sie einige Voraussetzungen sicherstellen:

1. .NET-Entwicklungsumgebung: Stellen Sie sicher, dass auf Ihrem Computer eine funktionierende .NET-Entwicklungsumgebung eingerichtet ist. Dazu gehört auch die Installation des .NET SDK.

2. GroupDocs.Viewer-Lizenz: Besorgen Sie sich eine gültige Lizenz für GroupDocs.Viewer. Sie können entweder eine Lizenz erwerben oder eine temporäre Lizenz zu Testzwecken verwenden.

3.  Installation: Laden Sie GroupDocs.Viewer für .NET von der bereitgestellten Website herunter und installieren Sie sie[Download-Link](https://releases.groupdocs.com/viewer/net/).

4. Dokumentdateien: Halten Sie die Dokumentdateien bereit, die Sie rendern möchten. GroupDocs.Viewer unterstützt verschiedene Formate, darunter DOCX, PDF, PPT und mehr.

## Namespaces importieren

Um mit dem Rendern von Dokumenten mit GroupDocs.Viewer für .NET zu beginnen, müssen Sie die erforderlichen Namespaces in Ihr Projekt importieren. Dadurch können Sie auf die von der Bibliothek bereitgestellten Funktionalitäten zugreifen.

```csharp
using System;
using System.IO;
using GroupDocs.Viewer.Options;
```

Das Rendern eines Dokuments im JPG- oder PNG-Format ist mit GroupDocs.Viewer für .NET ein unkomplizierter Vorgang. Nachfolgend finden Sie eine Schritt-für-Schritt-Anleitung, die Ihnen dabei hilft, dies zu erreichen:

## Schritt 1: Ausgabeverzeichnis definieren

Definieren Sie zunächst das Verzeichnis, in dem die gerenderten Seiten gespeichert werden sollen. Dieses Verzeichnis sollte vorhanden sein und für die Anwendung zugänglich sein.

```csharp
string outputDirectory = "Your Document Directory";
```

## Schritt 2: Definieren Sie das Format des Seitendateipfads

 Geben Sie das Format für die Dateipfade jeder gerenderten Seite an. GroupDocs.Viewer wird ersetzt`{0}` beim Speichern der Dateien mit der Seitenzahl versehen.

```csharp
string pageFilePathFormat = Path.Combine(outputDirectory, "page_{0}.jpg");
```

## Schritt 3: Viewer-Objekt instanziieren

 Erstellen Sie eine Instanz von`Viewer` Klasse, indem Sie den Pfad zu der Dokumentdatei angeben, die Sie rendern möchten.

```csharp
using (Viewer viewer = new Viewer("Path_to_Your_Document"))
{
    // Code zum Rendern finden Sie hier
}
```

## Schritt 4: Definieren Sie Rendering-Optionen

Geben Sie die Rendering-Optionen entsprechend Ihren Anforderungen an. Für das JPG/PNG-Rendering verwenden Sie`JpgViewOptions` oder`PngViewOptions`.

```csharp
JpgViewOptions options = new JpgViewOptions(pageFilePathFormat);
```

## Schritt 5: Dokument rendern

 Rufen Sie die auf`View` Methode der`Viewer` Objekt und übergeben Sie die zuvor erstellten Rendering-Optionen.

```csharp
viewer.View(options);
```

## Schritt 6: Ergebnisse ausgeben

Sobald der Rendervorgang abgeschlossen ist, können Sie den Benutzer über das erfolgreiche Rendern informieren und das Verzeichnis angeben, in dem die gerenderten Seiten gespeichert werden.

```csharp
Console.WriteLine($"\nSource document rendered successfully.\nCheck output in {outputDirectory}.");
```

## Abschluss

Zusammenfassend bietet GroupDocs.Viewer für .NET eine leistungsstarke Lösung zum Rendern von Dokumenten in verschiedenen Formaten, einschließlich JPG und PNG. Wenn Sie die in diesem Tutorial beschriebenen Schritte befolgen, können Sie die Funktion zur Dokumentwiedergabe nahtlos in Ihre .NET-Anwendungen integrieren und so die Benutzererfahrung und Produktivität verbessern.

## FAQs

### F: Kann ich mit GroupDocs.Viewer für .NET andere Dokumente als DOCX rendern?

A: Ja, GroupDocs.Viewer unterstützt eine Vielzahl von Dokumentformaten, darunter PDF, PPT, XLS und mehr.

### F: Gibt es eine kostenlose Testversion für GroupDocs.Viewer für .NET?

 A: Ja, Sie können eine kostenlose Testversion herunterladen[Hier](https://releases.groupdocs.com/).

### F: Wie kann ich eine temporäre Lizenz zu Evaluierungszwecken erhalten?

A: Sie können eine temporäre Lizenz bei anfordern[Hier](https://purchase.groupdocs.com/temporary-license/).

### F: Wo finde ich Dokumentation für GroupDocs.Viewer für .NET?

 A: Eine ausführliche Dokumentation ist verfügbar[Hier](https://tutorials.groupdocs.com/viewer/net/).

### F: Wo kann ich Unterstützung erhalten oder Fragen zu GroupDocs.Viewer für .NET stellen?

 A: Sie können das Support-Forum besuchen[Hier](https://forum.groupdocs.com/c/viewer/9) zur Hilfe.