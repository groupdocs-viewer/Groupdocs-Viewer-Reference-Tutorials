---
"description": "Verbessern Sie die Dokumentanzeige mit GroupDocs.Viewer für .NET. Rendern und passen Sie E-Mails nahtlos an."
"linktitle": "E-Mail-Felder während des Renderns umbenennen"
"second_title": "GroupDocs.Viewer .NET API"
"title": "E-Mail-Felder während des Renderns umbenennen"
"url": "/de/net/rendering-email-messages/rename-email-fields/"
"weight": 12
---

# E-Mail-Felder während des Renderns umbenennen

## Einführung

Im digitalen Zeitalter ist die effiziente Verwaltung und Anzeige von Dokumenten für Unternehmen und Privatpersonen gleichermaßen unerlässlich. Ob Verträge, Berichte oder E-Mails – die Möglichkeit, nahtlos durch diese Dokumente zu navigieren, steigert die Produktivität erheblich. Hier kommt GroupDocs.Viewer für .NET ins Spiel. Diese leistungsstarke Bibliothek ermöglicht Entwicklern die direkte Integration von Dokumentanzeigefunktionen in ihre .NET-Anwendungen und bietet eine breite Palette an Funktionen zur Darstellung verschiedener Dokumentformate.

## Voraussetzungen

Bevor Sie sich in das Tutorial zum Umbenennen von E-Mail-Feldern während des Renderings mit GroupDocs.Viewer für .NET vertiefen, stellen Sie sicher, dass Sie die folgenden Voraussetzungen erfüllen:

1. GroupDocs.Viewer für .NET-Bibliothek: Laden Sie die GroupDocs.Viewer für .NET-Bibliothek herunter und installieren Sie sie von [Hier](https://releases.groupdocs.com/viewer/net/).

2. Entwicklungsumgebung: Stellen Sie sicher, dass Sie eine geeignete Entwicklungsumgebung für die .NET-Entwicklung eingerichtet haben, beispielsweise Visual Studio.

3. Grundlegende Kenntnisse in C#: Machen Sie sich mit den Grundlagen der Programmiersprache C# vertraut, da das Tutorial C#-Codeausschnitte enthält.

4. Dokumentverzeichnis: Bereiten Sie ein Verzeichnis vor, in dem die zu rendernden Dokumente gespeichert werden.

## Namespaces importieren

Um die GroupDocs.Viewer-Funktionen in Ihrer .NET-Anwendung zu verwenden, müssen Sie die erforderlichen Namespaces importieren.

```csharp
using System;
using System.IO;
using GroupDocs.Viewer.Options;
```

Lassen Sie uns nun den Vorgang des Umbenennens von E-Mail-Feldern während des Renderings mit GroupDocs.Viewer für .NET in mehrere Schritte aufteilen:

## Schritt 1: Ausgabeverzeichnis definieren

Geben Sie zunächst das Verzeichnis an, in dem die gerenderten HTML-Seiten gespeichert werden.

```csharp
string outputDirectory = "Your Document Directory";
```

## Schritt 2: Definieren Sie das Auslagerungsdateipfadformat

Definieren Sie das Format für die Dateipfade der gerenderten HTML-Seiten. Jede Seite wird als separate HTML-Datei gespeichert.

```csharp
string pageFilePathFormat = Path.Combine(outputDirectory, "page_{0}.html");
```

## Schritt 3: Viewer-Objekt initialisieren

Erstellen Sie eine Instanz der Viewer-Klasse und übergeben Sie den Pfad des anzuzeigenden Dokuments als Parameter.

```csharp
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_MSG))
{
```

## Schritt 4: HTML-Ansichtsoptionen konfigurieren

Konfigurieren Sie die Optionen für die HTML-Ansicht, einschließlich der Angabe des Ausgabedateiformats und der Einrichtung von E-Mail-Feldzuordnungen.

```csharp
HtmlViewOptions options = HtmlViewOptions.ForEmbeddedResources(pageFilePathFormat);
options.EmailOptions.FieldTextMap[Field.From] = "Sender";
options.EmailOptions.FieldTextMap[Field.To] = "Receiver";
options.EmailOptions.FieldTextMap[Field.Sent] = "Date";
options.EmailOptions.FieldTextMap[Field.Subject] = "Topic";
```

## Schritt 5: Dokument rendern

Rufen Sie die View-Methode des Viewer-Objekts auf und übergeben Sie die konfigurierten HTML-Ansichtsoptionen.

```csharp
viewer.View(options);
```

## Schritt 6: Erfolgsmeldung anzeigen

Informieren Sie den Benutzer, dass das Dokument erfolgreich gerendert wurde.

```csharp
Console.WriteLine($"\nSource document rendered successfully.\nCheck output in {outputDirectory}.");
```

## Abschluss

Zusammenfassend lässt sich sagen, dass GroupDocs.Viewer für .NET eine nahtlose Lösung für das Rendern von Dokumenten in .NET-Anwendungen bietet. Mit den in diesem Tutorial beschriebenen Schritten können Sie E-Mail-Felder während des Renderns einfach umbenennen und so die Lesbarkeit und Benutzerfreundlichkeit von E-Mail-Dokumenten verbessern. Mit seiner intuitiven API und den umfassenden Funktionen ermöglicht GroupDocs.Viewer Entwicklern, die Dokumentanzeige effektiv zu optimieren.

## Häufig gestellte Fragen

### F: Kann ich mit GroupDocs.Viewer für .NET andere Dokumente als E-Mails rendern?

A: Ja, GroupDocs.Viewer unterstützt das Rendern verschiedener Dokumentformate, darunter PDF, Microsoft Office-Dokumente, Bilder und mehr.

### F: Ist GroupDocs.Viewer mit .NET Core kompatibel?

A: Ja, GroupDocs.Viewer unterstützt .NET Core zusammen mit dem traditionellen .NET Framework.

### F: Kann ich das Erscheinungsbild gerenderter Dokumente anpassen?

A: Auf jeden Fall. GroupDocs.Viewer bietet umfangreiche Anpassungsoptionen zur Steuerung des Erscheinungsbilds und Verhaltens gerenderter Dokumente.

### F: Unterstützt GroupDocs.Viewer Dokument-Streaming?

A: Ja, GroupDocs.Viewer ermöglicht das Streamen von Dokumenten direkt in den Browser des Clients, ohne dass diese auf dem Server gespeichert werden müssen.

### F: Ist GroupDocs.Viewer für Anwendungen auf Unternehmensebene geeignet?

A: Natürlich ist GroupDocs.Viewer mit seiner Skalierbarkeit, Zuverlässigkeit und seinem robusten Funktionsumfang darauf ausgelegt, die Anforderungen von Anwendungen auf Unternehmensebene zu erfüllen.