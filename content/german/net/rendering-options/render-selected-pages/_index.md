---
"description": "Erfahren Sie, wie Sie ausgewählte Seiten aus Dokumenten mit Groupdocs.Viewer für .NET rendern. Schritt-für-Schritt-Anleitung mit Codebeispielen."
"linktitle": "Ausgewählte Seiten rendern"
"second_title": "GroupDocs.Viewer .NET API"
"title": "Ausgewählte Seiten rendern"
"url": "/de/net/rendering-options/render-selected-pages/"
"weight": 17
---

# Ausgewählte Seiten rendern

## Einführung

In diesem Tutorial erfahren Sie, wie Sie mit Groupdocs.Viewer für .NET ausgewählte Seiten aus einem Dokument rendern. Egal, ob Sie ein erfahrener Entwickler oder Anfänger sind, diese Schritt-für-Schritt-Anleitung führt Sie mühelos durch den Prozess.

## Voraussetzungen

Bevor wir beginnen, stellen Sie sicher, dass die folgenden Voraussetzungen erfüllt sind:

### 1. Installation

Stellen Sie sicher, dass Groupdocs.Viewer für .NET in Ihrer Entwicklungsumgebung installiert ist. Falls nicht, können Sie es von der [Download-Link](https://releases.groupdocs.com/viewer/net/).

## Namespaces importieren

Importieren Sie in Ihrer C#-Codedatei die erforderlichen Namespaces, um auf die benötigten Klassen und Methoden zuzugreifen. Dies können Sie mit dem `using` Richtlinie:

```csharp
using System;
using System.IO;
using GroupDocs.Viewer.Options;
```

Lassen Sie uns nun den bereitgestellten Beispielcode in mehrere Schritte aufteilen:

## Schritt 1: Ausgabeverzeichnis festlegen

Definieren Sie das Verzeichnis, in dem die gerenderten Seiten gespeichert werden sollen. Ersetzen Sie `"Your Document Directory"` durch den gewünschten Verzeichnispfad.

```csharp
string outputDirectory = "Your Document Directory";
```

## Schritt 2: Definieren Sie das Auslagerungsdateipfadformat

Geben Sie das Format für die Dateipfade der gerenderten Seiten an. Dies wird verwendet, um jede Seite als HTML-Datei im Ausgabeverzeichnis zu speichern.

```csharp
string pageFilePathFormat = Path.Combine(outputDirectory, "page_{0}.html");
```

## Schritt 3: Viewer-Objekt instanziieren

Erstellen Sie eine Instanz der Viewer-Klasse und übergeben Sie den Pfad des Dokuments, das Sie rendern möchten, als Argument.

```csharp
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_DOCX))
```

## Schritt 4: HTML-Ansichtsoptionen konfigurieren

Richten Sie die HTML-Ansichtsoptionen für die Darstellung ein. In diesem Beispiel konfigurieren wir Optionen zum Einbetten von Ressourcen in die HTML-Ausgabe.

```csharp
HtmlViewOptions options = HtmlViewOptions.ForEmbeddedResources(pageFilePathFormat);
```

## Schritt 5: Ausgewählte Seiten rendern

Geben Sie die Seitenzahlen an, die Sie rendern möchten. In diesem Fall rendern wir die Seiten 1 bis 3. Rufen Sie anschließend die View-Methode für das Viewer-Objekt auf und übergeben Sie die Optionen und Seitenzahlen als Argumente.

```csharp
viewer.View(options, 1, 3);
```

## Schritt 6: Ausgabeergebnis

Zeigen Sie abschließend eine Meldung an, die die erfolgreiche Wiedergabe des Dokuments und den Speicherort der Ausgabedateien angibt.

```csharp
Console.WriteLine($"\nSource document rendered successfully.\nCheck output in {outputDirectory}.");
```

## Abschluss

Herzlichen Glückwunsch! Sie haben erfolgreich gelernt, wie Sie ausgewählte Seiten aus einem Dokument mit Groupdocs.Viewer für .NET rendern. Mit diesem Wissen können Sie nun problemlos Dokumentrendering-Funktionen in Ihre .NET-Anwendungen integrieren.

## Häufig gestellte Fragen

### F: Kann ich Seiten aus verschiedenen Dokumenttypen rendern, z. B. PDFs oder Bildern?

A: Ja, Groupdocs.Viewer für .NET unterstützt das Rendern von Seiten aus verschiedenen Dokumentformaten, einschließlich PDFs, Microsoft Office-Dokumenten und Bilddateien.

### F: Gibt es eine Testversion zum Testen vor dem Kauf?

A: Ja, Sie können auf eine kostenlose Testversion von Groupdocs.Viewer für .NET zugreifen über [Webseite](https://releases.groupdocs.com/).

### F: Kann ich das Ausgabeformat auf ein anderes Format als HTML anpassen?

A: Absolut, Groupdocs.Viewer für .NET bietet Optionen zum Rendern von Seiten als Bilder, PDFs und mehr, zusätzlich zu HTML.

### F: Wie kann ich temporäre Lizenzen zu Testzwecken erhalten?

A: Temporäre Lizenzen können erworben werden von der [Seite mit temporärer Lizenz](https://purchase.groupdocs.com/temporary-license/) auf der Groupdocs-Website.

### F: Wo kann ich Unterstützung suchen oder Hilfe bei auftretenden Problemen erhalten?

A: Sie können die [Groupdocs.Viewer-Forum](https://forum.groupdocs.com/c/viewer/9) für Unterstützung und Anleitung durch die Community und Entwickler.