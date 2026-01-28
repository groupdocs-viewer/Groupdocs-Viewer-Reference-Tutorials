---
date: '2026-01-28'
description: Erfahren Sie, wie Sie die Zeiteinheiten von MS Project mit GroupDocs Viewer Java
  anpassen. Optimieren Sie den Rendering‑Prozess Ihrer Projektdokumente effizient
  und präzise.
keywords:
- GroupDocs.Viewer Java
- MS Project time units adjustment
- render MS Project files
title: 'Wie man MS Project‑Zeiteinheiten mit GroupDocs Viewer Java anpasst: Eine Schritt‑für‑Schritt‑Anleitung'
type: docs
url: /de/java/custom-rendering/adjust-ms-project-time-units-groupdocs-viewer-java/
weight: 1
---

# Wie man Zeiteinheiten von MS Project mit groupdocs viewer java anpasst: Eine Schritt‑für‑Schritt‑Anleitung

## Introduction
Sind Sie es leid, die Zeiteinheiten in Ihren MS Project‑Dokumenten manuell anzupassen, bevor Sie sie in das HTML‑Format rendern? Der Prozess kann mühsam und fehleranfällig sein, insbesondere bei großen Projekten. Mit **groupdocs viewer java** können Sie die Zeiteinheitseinstellungen programmatisch leicht anpassen und so Genauigkeit und Effizienz sicherstellen.

![Adjust MS Project Time Units with GroupDocs.Viewer for Java](/viewer/custom-rendering/adjust-ms-project-time-units-java.png)

In diesem Leitfaden zeigen wir, wie Sie die Zeiteinheiten von MS Project‑Dokumenten mithilfe von groupdocs viewer java in Tage ändern. Am Ende dieses Tutorials können Sie:
- Ihre Umgebung für das Rendern von MS Project‑Dateien mit GroupDocs.Viewer einrichten.
- Zeiteinheiten des Projektmanagements direkt in Ihrem Code anpassen.
- Diese Anpassungen nahtlos in Ihre Anwendung integrieren.

Bevor wir loslegen, stellen wir sicher, dass Sie alles bereit haben, um zu beginnen!

## Quick Answers
- **Welche Bibliothek übernimmt das Rendern von MS Project?** groupdocs viewer java
- **Welche Zeiteinheit kann eingestellt werden?** Tage (via `TimeUnit.DAYS`)
- **Benötige ich eine Lizenz?** Eine Test- oder temporäre Lizenz ist verfügbar; für die Produktion ist eine permanente Lizenz erforderlich.
- **Welche IDE ist am besten geeignet?** Jede Java‑IDE (IntelliJ IDEA, Eclipse), die Maven unterstützt.
- **Ist Maven erforderlich?** Ja, Maven vereinfacht das Abhängigkeitsmanagement für groupdocs viewer java.

## Was ist groupdocs viewer java?
groupdocs viewer java ist ein Java‑SDK, das Entwicklern ermöglicht, eine Vielzahl von Dokumentformaten – einschließlich MS Project‑Dateien – in web‑freundliche Formate wie HTML oder Bilder zu rendern. Es abstrahiert die Komplexität der Dateianalyse, sodass Sie sich auf die Geschäftslogik konzentrieren können.

## Warum Zeiteinheiten mit groupdocs viewer java anpassen?
Das Ändern der Zeiteinheit vom Standard (oft Minuten) zu Tagen macht die gerenderte Ausgabe für Stakeholder lesbarer, entspricht dem üblichen Reporting‑Rhythmus und reduziert visuelle Unordnung in HTML‑Berichten. Dies ist besonders wertvoll, wenn Projektzeitpläne in Dashboards eingebettet oder tägliche Status‑Zusammenfassungen erstellt werden.

## Prerequisites
### Erforderliche Bibliotheken und Abhängigkeiten
Um diesem Tutorial zu folgen, benötigen Sie Folgendes:
- **groupdocs viewer java** Bibliothek (Version 25.2 oder neuer).
- Maven auf Ihrem Rechner installiert für das Abhängigkeitsmanagement.
- Grundlegendes Verständnis der Java‑Programmierung.

### Anforderungen an die Umgebungseinrichtung
Stellen Sie sicher, dass Ihre Entwicklungsumgebung mit dem JDK (Java Development Kit) und einer IDE wie IntelliJ IDEA oder Eclipse, die Maven‑Projekte unterstützt, eingerichtet ist.

### Vorwissen
Ein grundlegendes Verständnis der Java‑Syntax, des Dateihandlings in Java und der Arbeit mit Maven‑Abhängigkeiten ist vorteilhaft. Dieser Leitfaden soll jedoch den Prozess für alle Fähigkeitsstufen unkompliziert gestalten.

## Einrichtung von groupdocs viewer java
Um groupdocs viewer java zu verwenden, fügen Sie es als Abhängigkeit in die `pom.xml`‑Datei Ihres Projekts ein:

```xml
<repositories>
   <repository>
      <id>repository.groupdocs.com</id>
      <name>GroupDocs Repository</name>
      <url>https://releases.groupdocs.com/viewer/java/</url>
   </repository>
</repositories>

<dependencies>
   <dependency>
      <groupId>com.groupdocs</groupId>
      <artifactId>groupdocs-viewer</artifactId>
      <version>25.2</version>
   </dependency>
</dependencies>
```

### Schritte zum Erwerb einer Lizenz
groupdocs bietet eine kostenlose Testversion ihrer Bibliotheken an, sodass Sie die Funktionen vor dem Kauf oder der Beantragung einer temporären Lizenz testen können:
- **Kostenlose Testversion**: Besuchen Sie [GroupDocs Free Trial](https://releases.groupdocs.com/viewer/java/), um die Bibliothek herunterzuladen und zu nutzen.
- **Temporäre Lizenz**: Für erweiterte Tests können Sie eine [temporary license](https://purchase.groupdocs.com/temporary-license/) anfordern.
- **Kauf**: Wenn Sie entscheiden, dass groupdocs.viewer java für Ihr Projekt geeignet ist, können Sie es direkt über die [buy page](https://purchase.groupdocs.com/buy) erwerben.

### Grundlegende Initialisierung und Einrichtung
Sobald die Abhängigkeit in Ihrer Maven‑`pom.xml` eingerichtet ist, können Sie mit dem Codieren beginnen. Initialisieren Sie eine Viewer‑Instanz mit dem Pfad Ihrer MS Project‑Datei und bereiten Sie das Rendern vor.

## Implementierungs‑Leitfaden
Tauchen wir ein, wie Sie die Zeiteinheiten für MS Project‑Dokumente mit groupdocs viewer java anpassen können. Wir werden es Schritt für Schritt aufschlüsseln.

### Funktionsübersicht: Zeiteinheiten in MS Project‑Dokumenten anpassen
Diese Funktion ermöglicht es Ihnen, die Zeiteinheitseinstellung des Projektmanagements vom Standard (in der Regel Minuten) auf Tage zu ändern, wodurch Ihr gerendertes HTML benutzerfreundlicher und an gängige Reporting‑Standards angepasst wird.

#### Schritt 1: Ausgabeverzeichnis und Seiten‑Dateipfad‑Format festlegen
Zuerst geben Sie an, wo die gerenderten HTML‑Dateien gespeichert werden sollen:

```java
import java.nio.file.Path;
// Specify the output directory for HTML files
Path outputDirectory = Utils.getOutputDirectoryPath("YOUR_OUTPUT_DIRECTORY");
```

Verwenden Sie dieses Verzeichnis, um Dateipfade dynamisch für jede Seite Ihres MS Project‑Dokuments aufzulösen:

```java
// Define a format for each rendered page's file path
Path pageFilePathFormat = outputDirectory.resolve("page_{0}.html");
```

#### Schritt 2: View‑Optionen initialisieren
Erstellen Sie View‑Optionen mit eingebetteten Ressourcen, die Ihnen ermöglichen, festzulegen, wie das Projekt angezeigt und gerendert werden soll:

```java
import com.groupdocs.viewer.options.HtmlViewOptions;
// Set up HTML view options for rendering
HtmlViewOptions viewOptions = HtmlViewOptions.forEmbeddedResources(pageFilePathFormat);
```

#### Schritt 3: Zeiteinheitseinstellung anpassen
Geben Sie an, dass die Zeiteinheit für das Projektmanagement auf Tage gesetzt wird, was häufig besser für Präsentationen und Berichte geeignet ist:

```java
import com.groupdocs.viewer.options.TimeUnit;
// Change the project management time unit to DAYS
viewOptions.getProjectManagementOptions().setTimeUnit(TimeUnit.DAYS);
```

#### Schritt 4: MS Project‑Dokument rendern
Verwenden Sie schließlich die Viewer‑Klasse, um Ihr Dokument mit den angegebenen View‑Optionen zu rendern:

```java
import com.groupdocs.viewer.Viewer;
try (Viewer viewer = new Viewer("YOUR_DOCUMENT_DIRECTORY/SAMPLE_MPP")) {
    // Render the project document as HTML using set view options
    viewer.view(viewOptions);
}
```

### Tipps zur Fehlerbehebung
- Stellen Sie sicher, dass der Pfad des Ausgabeverzeichnisses korrekt angegeben und beschreibbar ist.
- Überprüfen Sie, ob der Pfad der MS Project‑Datei korrekt und zugänglich ist.
- Bei Rendering‑Problemen prüfen Sie, ob die Viewer‑Klasse Ausnahmen wirft.

## Praktische Anwendungen
Hier sind einige Anwendungsfälle aus der Praxis, bei denen das Anpassen der Zeiteinheiten in MS Project‑Dokumenten besonders nützlich sein kann:
1. **Projektberichterstattung** – Stakeholder bevorzugen oft tägliche Zusammenfassungen gegenüber minutengenauer Detailtiefe.
2. **Integration in Dashboards** – Einbetten von Zeitplänen in Business‑Dashboards, die Granularität auf Tagesebene erfordern.
3. **Automatisierte Updates** – Systeme, die Projektstatus automatisch täglich aktualisieren müssen.

## Leistungsüberlegungen
Beim Arbeiten mit großen MS Project‑Dateien sollten Sie Folgendes für optimale Leistung berücksichtigen:
- Verwenden Sie eingebettete Ressourcen sparsam, wenn nur bestimmte Teile des Dokuments häufig benötigt werden.
- Überwachen Sie die Speichernutzung, wenn Sie mehrere oder sehr große Projekte gleichzeitig bearbeiten.
- Nutzen Sie die Garbage Collection von Java effektiv, um die Ressourcenallokation und -freigabe zu verwalten.

## Fazit
Sie haben nun gelernt, wie Sie die Zeiteinheiten von MS Project mit groupdocs viewer java anpassen. Diese Funktion optimiert den Prozess des Renderns von Projektdokumenten, macht sie zugänglicher und erleichtert die Integration in umfassendere Systeme.

Erwägen Sie, weitere Funktionen von groupdocs viewer java zu erkunden, um Ihre Dokumenten‑Management‑Lösungen weiter zu verbessern. Bereit, den nächsten Schritt zu gehen? Versuchen Sie, diese Lösung in Ihrem nächsten Projekt umzusetzen!

## FAQ‑Abschnitt
**1. Wofür wird GroupDocs.Viewer für Java verwendet?**  
GroupDocs.Viewer für Java ermöglicht Entwicklern, Dokumente in verschiedenen Formaten, einschließlich MS Project‑Dateien, in HTML‑ oder Bildformate zu rendern, um sie anzuzeigen.

**2. Kann ich GroupDocs.Viewer für andere Dokumenttypen verwenden?**  
Ja, GroupDocs.Viewer unterstützt eine breite Palette von Dokumentformaten über MS Project hinaus, wie PDFs, Word‑Dokumente und Tabellenkalkulationen.

**3. Wie gehe ich mit der Lizenzierung von GroupDocs.Viewer um?**  
GroupDocs bietet verschiedene Lizenzoptionen, darunter kostenlose Testversionen, temporäre Lizenzen für erweiterte Tests und permanente Lizenzen nach dem Kauf.

**4. Was soll ich tun, wenn beim Rendern meiner Projektdateien Fehler auftreten?**  
Überprüfen Sie die Dateipfade, stellen Sie sicher, dass Sie Schreibzugriff auf Ihr Ausgabeverzeichnis haben, und prüfen Sie etwaige Ausnahmen, die von GroupDocs.Viewer geworfen werden, für Hinweise zur Fehlerbehebung.

**5. Kann ich das Rendern von Dokumenten mit GroupDocs.Viewer anpassen?**  
Absolut! GroupDocs.Viewer bietet eine Reihe von Optionen zur Anpassung des Renderns, einschließlich der Einstellung von Zeiteinheiten für Projekte, der Auswahl, welche Ressourcen eingebettet werden sollen, und mehr.

## Ressourcen
- [Dokumentation](https://docs.groupdocs.com/viewer/java/)
- [API‑Referenz](https://reference.groupdocs.com/viewer/java/)
- [GroupDocs.Viewer herunterladen](https://releases.groupdocs.com/viewer/java/)
- [Lizenz erwerben](https://purchase.groupdocs.com/buy)

---

**Zuletzt aktualisiert:** 2026-01-28  
**Getestet mit:** groupdocs viewer java 25.2  
**Autor:** GroupDocs