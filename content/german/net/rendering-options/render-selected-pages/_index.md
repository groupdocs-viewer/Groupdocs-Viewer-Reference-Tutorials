---
title: Ausgewählte Seiten rendern
linktitle: Ausgewählte Seiten rendern
second_title: GroupDocs.Viewer .NET-API
description: Erfahren Sie, wie Sie ausgewählte Seiten aus Dokumenten mit Groupdocs.Viewer für .NET rendern. Schritt-für-Schritt-Anleitung mit Codebeispielen.
type: docs
weight: 17
url: /de/net/rendering-options/render-selected-pages/
---
## Einführung

In diesem Tutorial befassen wir uns mit der Verwendung von Groupdocs.Viewer für .NET zum Rendern ausgewählter Seiten aus einem Dokument. Egal, ob Sie ein erfahrener Entwickler sind oder gerade erst anfangen, diese Schritt-für-Schritt-Anleitung führt Sie mühelos durch den Prozess.

## Voraussetzungen

Bevor wir beginnen, stellen Sie sicher, dass die folgenden Voraussetzungen erfüllt sind:

### 1. Installation

 Stellen Sie sicher, dass Groupdocs.Viewer für .NET in Ihrer Entwicklungsumgebung installiert ist. Wenn nicht, können Sie es hier herunterladen[Download-Link](https://releases.groupdocs.com/viewer/net/).

## Namensräume importieren

Importieren Sie in Ihre C#-Codedatei die erforderlichen Namespaces, um auf die erforderlichen Klassen und Methoden zuzugreifen. Sie können dies mit dem tun`using` Direktive:

```csharp
using System;
using System.IO;
using GroupDocs.Viewer.Options;
```

Lassen Sie uns nun den bereitgestellten Beispielcode in mehrere Schritte aufteilen:

## Schritt 1: Ausgabeverzeichnis festlegen

 Definieren Sie das Verzeichnis, in dem die gerenderten Seiten gespeichert werden sollen. Ersetzen`"Your Document Directory"` mit dem gewünschten Verzeichnispfad.

```csharp
string outputDirectory = "Your Document Directory";
```

## Schritt 2: Definieren Sie das Format des Seitendateipfads

Geben Sie das Format für die Dateipfade der gerenderten Seiten an. Dies wird verwendet, um jede Seite als HTML-Datei im Ausgabeverzeichnis zu speichern.

```csharp
string pageFilePathFormat = Path.Combine(outputDirectory, "page_{0}.html");
```

## Schritt 3: Viewer-Objekt instanziieren

Erstellen Sie eine Instanz der Viewer-Klasse und übergeben Sie dabei den Pfad des Dokuments, das Sie rendern möchten, als Argument.

```csharp
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_DOCX))
```

## Schritt 4: Konfigurieren Sie die HTML-Ansichtsoptionen

Richten Sie die HTML-Ansichtsoptionen für das Rendern ein. In diesem Beispiel konfigurieren wir Optionen zum Einbetten von Ressourcen in die HTML-Ausgabe.

```csharp
HtmlViewOptions options = HtmlViewOptions.ForEmbeddedResources(pageFilePathFormat);
```

## Schritt 5: Ausgewählte Seiten rendern

Geben Sie die Seitenzahlen an, die Sie rendern möchten. In diesem Fall rendern wir die Seiten 1 bis 3. Rufen Sie dann die View-Methode für das Viewer-Objekt auf und übergeben Sie die Optionen und Seitenzahlen als Argumente.

```csharp
viewer.View(options, 1, 3);
```

## Schritt 6: Ergebnis ausgeben

Abschließend wird eine Meldung angezeigt, die über das erfolgreiche Rendern des Dokuments und den Speicherort der Ausgabedateien informiert.

```csharp
Console.WriteLine($"\nSource document rendered successfully.\nCheck output in {outputDirectory}.");
```

## Abschluss

Glückwunsch! Sie haben erfolgreich gelernt, wie Sie ausgewählte Seiten eines Dokuments mit Groupdocs.Viewer für .NET rendern. Mit diesem Wissen können Sie jetzt problemlos Dokument-Rendering-Funktionen in Ihre .NET-Anwendungen integrieren.

## FAQs

### F: Kann ich Seiten aus verschiedenen Dokumenttypen rendern, z. B. PDFs oder Bildern?

A: Ja, Groupdocs.Viewer für .NET unterstützt das Rendern von Seiten aus verschiedenen Dokumentformaten, einschließlich PDFs, Microsoft Office-Dokumenten und Bilddateien.

### F: Gibt es eine Testversion zum Testen vor dem Kauf?

 A: Ja, Sie können über die auf eine kostenlose Testversion von Groupdocs.Viewer für .NET zugreifen[Webseite](https://releases.groupdocs.com/).

### F: Kann ich ein anderes Ausgabeformat als HTML anpassen?

A: Absolut, Groupdocs.Viewer für .NET bietet neben HTML auch Optionen zum Rendern von Seiten als Bilder, PDFs und mehr.

### F: Wie kann ich temporäre Lizenzen zu Testzwecken erhalten?

A: Temporäre Lizenzen können bei erworben werden[temporäre Lizenzseite](https://purchase.groupdocs.com/temporary-license/) auf der Groupdocs-Website.

### F: Wo kann ich Hilfe suchen oder Hilfe bei Problemen erhalten, auf die ich stoße?

 A: Sie können die besuchen[Groupdocs.Viewer-Forum](https://forum.groupdocs.com/c/viewer/9) für Unterstützung und Anleitung von der Community und den Entwicklern.