---
title: Schützen Sie gerenderte PDFs mit einem Passwort
linktitle: Schützen Sie gerenderte PDFs mit einem Passwort
second_title: GroupDocs.Viewer .NET-API
description: Schützen Sie Ihre gerenderten PDFs ganz einfach mit Passwörtern mit Groupdocs.Viewer für .NET. Bewahren Sie Ihre Dokumente sicher und vertraulich auf.
type: docs
weight: 12
url: /de/net/rendering-documents-pdf/protect-pdf/
---
## Einführung
In diesem Tutorial erfahren Sie, wie Sie Groupdocs.Viewer für .NET verwenden, um eine gerenderte PDF-Datei mit einem Passwort zu schützen. Durch das Hinzufügen von Sicherheitsmaßnahmen können Sie den Zugriff auf Ihre PDF-Dokumente kontrollieren und so Vertraulichkeit und Integrität gewährleisten.
## Voraussetzungen
Bevor Sie beginnen, stellen Sie sicher, dass Sie über Folgendes verfügen:
1.  Groupdocs.Viewer für .NET-Bibliothek: Laden Sie die Bibliothek von herunter und installieren Sie sie[Webseite](https://releases.groupdocs.com/viewer/net/).
2. Entwicklungsumgebung: Stellen Sie sicher, dass Sie eine funktionierende Entwicklungsumgebung für die .NET-Entwicklung eingerichtet haben.

## Namespaces importieren
```csharp
using System;
using System.IO;
using GroupDocs.Viewer.Options;
```
## Schritt 1: Ausgabeverzeichnis und Dateipfad definieren
```csharp
string outputDirectory = "Your Document Directory";
string filePath = Path.Combine(outputDirectory, "output.pdf");
```
## Schritt 2: Viewer-Objekt initialisieren und Sicherheitsoptionen festlegen
```csharp
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_DOCX))
{
    Security security = new Security
    {
        DocumentOpenPassword = "o123",
        PermissionsPassword = "p123",
        Permissions = Permissions.AllowAll ^ Permissions.DenyPrinting
    };
```
## Schritt 3: PDF-Ansichtsoptionen festlegen
```csharp
    PdfViewOptions options = new PdfViewOptions(filePath)
    {
        Security = security
    };
```
## Schritt 4: Dokument mit Sicherheitsoptionen rendern
```csharp
    viewer.View(options);
}
```
## Schritt 5: Überprüfen Sie das gerenderte Dokument
```csharp
Console.WriteLine($"\nSource document rendered successfully.\nCheck output in {outputDirectory}.");
```
Wenn Sie diese Schritte befolgen, können Sie ein gerendertes PDF mithilfe von Groupdocs.Viewer für .NET mit einem Kennwort schützen. Dadurch wird sichergestellt, dass Ihre Dokumente sicher und nur autorisierten Benutzern zugänglich bleiben.

## Abschluss
Die Sicherung von PDF-Dokumenten ist für die Wahrung der Vertraulichkeit und Integrität von entscheidender Bedeutung. Mit Groupdocs.Viewer für .NET können Sie gerenderte PDFs ganz einfach mit Passwörtern schützen und so den Zugriff auf vertrauliche Informationen kontrollieren.

## FAQs
### Kann ich PDFs mit unterschiedlichen Berechtigungsstufen schützen?
Ja, Sie können unterschiedliche Berechtigungen zum Anzeigen, Drucken, Kopieren usw. festlegen und gleichzeitig PDFs mit Passwörtern schützen.
### Ist Groupdocs.Viewer mit verschiedenen Dateiformaten kompatibel?
Absolut! Groupdocs.Viewer unterstützt das Rendern einer Vielzahl von Dateiformaten, darunter DOCX, XLSX, PPTX, PDF und mehr.
### Kann ich Groupdocs.Viewer in meine bestehende .NET-Anwendung integrieren?
Sicherlich! Groupdocs.Viewer bietet APIs für die nahtlose Integration in .NET-Anwendungen und bietet robuste Funktionen zur Dokumentenanzeige.
### Bietet Groupdocs.Viewer Unterstützung für Cloud-Speicherdienste?
Ja, Groupdocs.Viewer unterstützt die Integration mit beliebten Cloud-Speicherdiensten wie Dropbox, Google Drive und Amazon S3, sodass Sie in der Cloud gespeicherte Dokumente wiedergeben können.
### Gibt es eine Testversion für Groupdocs.Viewer?
 Ja, Sie können mit Groupdocs.Viewer beginnen, indem Sie auf die kostenlose Testversion zugreifen[Webseite](https://releases.groupdocs.com/).