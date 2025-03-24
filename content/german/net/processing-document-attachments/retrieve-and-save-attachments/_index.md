---
title: Dokumentanhänge abrufen und speichern
linktitle: Dokumentanhänge abrufen und speichern
second_title: GroupDocs.Viewer .NET-API
description: Verwalten Sie Dokumentanhänge in .NET-Anwendungen effizient mit GroupDocs.Viewer. Anhänge problemlos abrufen und speichern.
weight: 12
url: /de/net/processing-document-attachments/retrieve-and-save-attachments/
---

# Dokumentanhänge abrufen und speichern

## Einführung
Im digitalen Zeitalter ist eine effiziente Dokumentenverarbeitung für Unternehmen und Privatpersonen gleichermaßen von entscheidender Bedeutung. Ob es darum geht, E-Mails zu verwalten, Verträge anzuzeigen oder auf Berichte zuzugreifen, ein zuverlässiges Tool zur Dokumentenvisualisierung ist unerlässlich. GroupDocs.Viewer für .NET erweist sich als robuste Lösung, die es Benutzern ermöglicht, verschiedene Dokumentformate mühelos direkt in ihren .NET-Anwendungen anzuzeigen und mit ihnen zu interagieren.
## Voraussetzungen
Bevor Sie sich mit der Verwendung von GroupDocs.Viewer für .NET zum Abrufen und Speichern von Dokumentanhängen befassen, stellen Sie sicher, dass Sie die folgenden Voraussetzungen erfüllen:
1. Betriebsumgebung: Eine mit .NET Framework eingerichtete Arbeitsumgebung.
2.  Installation: GroupDocs.Viewer für .NET-Bibliothek heruntergeladen und installiert. Sie können auf die Bibliothek zugreifen[Download-Link](https://releases.groupdocs.com/viewer/net/).
3. Grundverständnis: Vertrautheit mit der Programmiersprache C#.
4. Dokumentquelle: Zugriff auf ein Beispieldokument mit Anhängen zu Demonstrationszwecken.

## Namespaces importieren
Um GroupDocs.Viewer für .NET zum Abrufen und Speichern von Dokumentanhängen zu verwenden, importieren Sie die erforderlichen Namespaces:
```csharp
using System;
using System.Collections.Generic;
using System.IO;
using GroupDocs.Viewer.Results;
```

## Schritt 1: Ausgabeverzeichnis definieren
```csharp
string outputDirectory = "Your Document Directory";
```
Definieren Sie das Verzeichnis, in dem Sie die aus dem Dokument abgerufenen Anhänge speichern möchten.
## Schritt 2: Viewer-Objekt instanziieren
```csharp
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_MSG_WITH_ATTACHMENTS))
```
Instanziieren Sie das Viewer-Objekt mit dem Pfad zum Dokument, das Anhänge enthält.
## Schritt 3: Anhänge abrufen
```csharp
IList<Attachment> attachments = viewer.GetAttachments();
```
Rufen Sie eine Liste der im Dokument vorhandenen Anhänge ab.
## Schritt 4: Anhänge speichern
```csharp
foreach(Attachment attachment in attachments)
{
    string filePath = Path.Combine(outputDirectory, attachment.FileName);  
    viewer.SaveAttachment(attachment, File.OpenWrite(filePath)); 
}
```
Durchlaufen Sie jeden Anhang, definieren Sie den Dateipfad und speichern Sie den Anhang im angegebenen Verzeichnis.
## Schritt 5: Erfolgsmeldung anzeigen
```csharp
Console.WriteLine($"\nAttachments saved successfully.\nCheck output in {outputDirectory}.");
```
Zeigt eine Erfolgsmeldung an, die das erfolgreiche Speichern der Anhänge zusammen mit dem Verzeichnispfad anzeigt.

## Abschluss
Durch die Einbindung von GroupDocs.Viewer für .NET in Ihre Dokumentenverarbeitungsabläufe wird die Verwaltung von Anhängen rationalisiert und bietet Effizienz und Komfort. Durch Befolgen der oben beschriebenen Schritt-für-Schritt-Anleitung können Benutzer Dokumentanhänge nahtlos in ihren .NET-Anwendungen abrufen und speichern.
## FAQs
### Kann GroupDocs.Viewer für .NET verschiedene Dokumentformate verarbeiten?
Ja, GroupDocs.Viewer unterstützt eine Vielzahl von Dokumentformaten, darunter PDF, Microsoft Office-Dokumente, Bilder und mehr.
### Gibt es eine kostenlose Testversion für GroupDocs.Viewer für .NET?
 Ja, Sie können auf die kostenlose Testversion zugreifen[Hier](https://releases.groupdocs.com/).
### Wie kann ich temporäre Lizenzen für GroupDocs.Viewer für .NET erhalten?
 Temporäre Lizenzen können bei erworben werden[dieser Link](https://purchase.groupdocs.com/temporary-license/).
### Wo finde ich Dokumentation für GroupDocs.Viewer für .NET?
 Eine umfassende Dokumentation ist vorhanden[Hier](https://tutorials.groupdocs.com/viewer/net/).
### Welche Supportoptionen stehen für GroupDocs.Viewer für .NET zur Verfügung?
 Sie können Hilfe im Community-Forum suchen[Hier](https://forum.groupdocs.com/c/viewer/9).