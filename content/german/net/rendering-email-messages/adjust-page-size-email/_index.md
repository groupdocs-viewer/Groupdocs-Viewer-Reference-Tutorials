---
title: Passen Sie die Seitengröße beim Rendern von E-Mail-Nachrichten an
linktitle: Passen Sie die Seitengröße beim Rendern von E-Mail-Nachrichten an
second_title: GroupDocs.Viewer .NET-API
description: Erfahren Sie, wie Sie die Seitengröße anpassen, wenn Sie E-Mail-Nachrichten mit GroupDocs.Viewer für .NET in PDF rendern. Verbessern Sie die Effizienz beim Anzeigen von Dokumenten.
weight: 10
url: /de/net/rendering-email-messages/adjust-page-size-email/
---

# Passen Sie die Seitengröße beim Rendern von E-Mail-Nachrichten an

## Einführung
Im Bereich der .NET-Entwicklung bietet GroupDocs.Viewer eine umfassende Lösung zum Rendern verschiedener Dokumentformate, einschließlich E-Mail-Nachrichten. Dieses Tutorial konzentriert sich auf die Anpassung der Seitengröße beim Rendern von E-Mail-Nachrichten im PDF-Format mit GroupDocs.Viewer für .NET. Indem Sie die in diesem Leitfaden beschriebenen Schritte befolgen, erfahren Sie, wie Sie die Seitengröße nahtlos an Ihre spezifischen Anforderungen anpassen können.
## Voraussetzungen
Bevor Sie mit diesem Tutorial beginnen, stellen Sie sicher, dass Sie die folgenden Voraussetzungen erfüllen:
### 1. GroupDocs.Viewer für .NET installiert
 Stellen Sie sicher, dass GroupDocs.Viewer für .NET in Ihrer Entwicklungsumgebung installiert ist. Sie können es herunterladen unter[Hier](https://releases.groupdocs.com/viewer/net/).
### 2. Grundlegendes Verständnis der .NET-Entwicklung
Machen Sie sich mit den Grundlagen der .NET-Entwicklung vertraut, einschließlich C#-Programmierung und Dateiverwaltung.
### 3. IDE (Integrierte Entwicklungsumgebung)
Installieren Sie eine IDE wie Visual Studio zum Schreiben und Ausführen von .NET-Code.

## Namespaces importieren
Importieren Sie in Ihrem C#-Projekt die erforderlichen Namespaces, um die GroupDocs.Viewer-Funktionen zu nutzen.

```csharp
using System;
using System.IO;
using GroupDocs.Viewer.Options;
```

## Schritt 1: Ausgabeverzeichnis festlegen
Definieren Sie das Verzeichnis, in dem die ausgegebene PDF-Datei gespeichert wird.
```csharp
string outputDirectory = "Your Document Directory";
```
## Schritt 2: Dateipfad definieren
Kombinieren Sie das Ausgabeverzeichnis mit dem Namen der Ausgabedatei.
```csharp
string filePath = Path.Combine(outputDirectory, "output.pdf");
```
## Schritt 3: Viewer-Objekt initialisieren
Erstellen Sie eine Instanz der Viewer-Klasse und geben Sie den Pfad der E-Mail-Nachrichtendatei an.
```csharp
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_MSG))
```
## Schritt 4: Konfigurieren Sie die PDF-Ansichtsoptionen
Instanziieren Sie PdfViewOptions und legen Sie den Pfad der Ausgabedatei fest.
```csharp
PdfViewOptions options = new PdfViewOptions(filePath);
```
## Schritt 5: Seitengröße anpassen
Ändern Sie die Seitengrößeneigenschaft in den EmailOptions von PdfViewOptions.
```csharp
options.EmailOptions.PageSize = PageSize.A4;
```
## Schritt 6: Dokument rendern
Rufen Sie die View-Methode des Viewer-Objekts auf und übergeben Sie dabei die konfigurierten PDFViewOptions.
```csharp
viewer.View(options);
```
## Schritt 7: Erfolgsmeldung anzeigen
Informieren Sie den Benutzer über das erfolgreiche Rendern und das Ausgabeverzeichnis.
```csharp
Console.WriteLine($"\nSource document rendered successfully.\nCheck output in {outputDirectory}.");
```

## Abschluss
Zusammenfassend wurde in diesem Tutorial gezeigt, wie man die Seitengröße beim Rendern von E-Mail-Nachrichten im PDF-Format mit GroupDocs.Viewer für .NET anpasst. Wenn Sie diese Schritt-für-Schritt-Anleitungen befolgen, können Sie die Seitengrößen effizient an Ihre spezifischen Anforderungen anpassen und so die Anzeige- und Verwaltungsfunktionen für Dokumente in Ihren .NET-Anwendungen verbessern.
## FAQs
### Ist GroupDocs.Viewer mit verschiedenen E-Mail-Nachrichtenformaten kompatibel?
GroupDocs.Viewer unterstützt das Rendern verschiedener E-Mail-Nachrichtenformate, einschließlich MSG und EML.
### Kann ich die Seitengröße nach meinen Wünschen anpassen?
Ja, Sie können die Seitengröße mit den PdfViewOptions von GroupDocs.Viewer anpassen und so Flexibilität beim Rendern von Dokumenten bieten.
### Bietet GroupDocs.Viewer Unterstützung für andere Dokumentformate?
Ja, GroupDocs.Viewer unterstützt eine Vielzahl von Dokumentformaten, darunter PDF, Microsoft Office, Bilder und mehr.
### Ist GroupDocs.Viewer für Anwendungen auf Unternehmensebene geeignet?
Absolut, GroupDocs.Viewer bietet robuste Funktionalitäten, die sowohl für kleine als auch für Unternehmensanwendungen geeignet sind und eine effiziente Dokumentenwiedergabe und -verwaltung gewährleisten.
### Wo kann ich Hilfe oder zusätzliche Unterstützung für GroupDocs.Viewer erhalten?
 Sie können das GroupDocs.Viewer-Forum besuchen[Hier](https://forum.groupdocs.com/c/viewer/9) um Hilfe zu suchen, Fragen zu stellen und mit der Community in Kontakt zu treten.