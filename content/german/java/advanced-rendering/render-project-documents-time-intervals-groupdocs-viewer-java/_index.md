---
date: '2026-03-29'
description: Erfahren Sie, wie Sie mit GroupDocs Viewer in Java eine HTML‑Ansicht
  für MPP erstellen und Projektdokumente nach Zeitintervallen mit Schritt‑für‑Schritt‑Code
  rendern.
keywords:
- render project documents
- time intervals Java
- GroupDocs Viewer API
title: HTML-Ansicht für MPP mit GroupDocs Viewer (Java) erstellen
type: docs
url: /de/java/advanced-rendering/render-project-documents-time-intervals-groupdocs-viewer-java/
weight: 1
---

# Wie man GroupDocs Viewer verwendet, um Projektdokumente nach Zeitintervallen in Java zu rendern

In diesem Tutorial lernen Sie, wie Sie **create html view mpp** mit GroupDocs Viewer für Java erstellen, sodass Sie nur die Teile einer Microsoft Project‑Datei rendern können, die in einen bestimmten Zeitintervall fallen. Wir gehen die Maven‑Einrichtung, Code‑Konfiguration und praxisnahe Szenarien durch, damit Sie präzise Zeitstrahl‑Ansichten direkt in Ihre Anwendungen einbetten können.

![Projektdokumente nach Zeitintervallen mit GroupDocs.Viewer für Java rendern](/viewer/advanced-rendering/render-project-documents-by-time-intervals-java.png)

## Schnelle Antworten
- **Was macht die Funktion?** Sie rendert nur den Teil einer Microsoft Project‑Datei, der zwischen einem Start‑ und Enddatum liegt.  
- **Welches Ausgabeformat wird verwendet?** HTML mit eingebetteten Ressourcen, ideal für die Web‑Integration.  
- **Benötige ich eine Lizenz?** Eine kostenlose Testversion reicht für die Evaluierung; für den Produktionseinsatz ist eine Voll‑Lizenz erforderlich.  
- **Kann ich den Datumsbereich zur Laufzeit ändern?** Ja – passen Sie die Werte `setStartDate` und `setEndDate` in den Rendering‑Optionen an.  
- **Wird dies von allen Java‑Versionen unterstützt?** Funktioniert mit Java 8+ solange Sie GroupDocs.Viewer 25.2 oder neuer verwenden.

## Wie man html view mpp für Projektdokumente erstellt
GroupDocs Viewer kann Microsoft Project‑Dateien (`.mpp`, `.mpt`) in HTML‑Seiten konvertieren. Durch die Konfiguration von Start‑ und Enddatum in den Rendering‑Optionen begrenzen Sie die Ausgabe auf den für Sie relevanten Zeitabschnitt, was die Dateigröße reduziert und das Laden der Seiten beschleunigt.

## Was bedeutet „How to Use GroupDocs“ in diesem Kontext?
GroupDocs Viewer ist eine Java‑Bibliothek, die über 100 Dateiformate in web‑freundliche Darstellungen konvertiert. Wenn Sie **how to use GroupDocs** für Projektdateien verwenden, erhalten Sie die Möglichkeit, Zeitplandaten zu extrahieren, zu visualisieren und zu teilen, ohne dass Microsoft Project auf der Client‑Seite erforderlich ist.

## Warum Projektdokumente mit Zeitintervallen rendern?
- **Gezielte Analyse:** Zeigen Sie nur die Phase, die Sie interessiert (z. B. Q3 2024).  
- **Performance:** Kleinere HTML‑Ausgabe bedeutet schnellere Seitenladezeiten.  
- **Integration:** Betten Sie Zeitstrahl‑Ansichten in Dashboards, Reporting‑Portale oder benutzerdefinierte PM‑Tools ein.  

## Voraussetzungen
- **GroupDocs.Viewer für Java** Version 25.2 oder höher.  
- Java Development Kit (JDK) 8 oder neuer.  
- Eine IDE wie IntelliJ IDEA oder Eclipse.  
- Grundkenntnisse in Maven.  

## Einrichtung von GroupDocs.Viewer für Java

### Maven‑Abhängigkeit

Fügen Sie das Repository und die Abhängigkeit zu Ihrer `pom.xml` hinzu:

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

1. **Free Trial** – Laden Sie eine Testversion von [GroupDocs' download page](https://releases.groupdocs.com/viewer/java/) herunter.  
2. **Temporary License** – Erhalten Sie eine temporäre Lizenz für erweiterte Tests über [this link](https://purchase.groupdocs.com/temporary-license/).  
3. **Purchase** – Für uneingeschränkten Produktionseinsatz kaufen Sie eine Lizenz auf [GroupDocs Purchase Page](https://purchase.groupdocs.com/buy).

### Grundlegende Viewer‑Initialisierung

Das folgende Snippet zeigt, wie Sie eine `Viewer`‑Instanz erstellen, die auf eine Microsoft Project‑Datei (`.mpp`) verweist:

```java
import com.groupdocs.viewer.Viewer;

public class ViewerSetup {
    public static void main(String[] args) {
        try (Viewer viewer = new Viewer("path/to/your/document.mpp")) {
            // Your rendering code goes here
        }
    }
}
```

## Schritt‑für‑Schritt‑Implementierungs‑Leitfaden

### 1. Definieren Sie das Ausgabeverzeichnis

Erstellen Sie einen Ordner, in dem die generierten HTML‑Seiten gespeichert werden:

```java
import java.nio.file.Path;

Path outputDirectory = Path.of("YOUR_OUTPUT_DIRECTORY", "RenderProjectTimeInterval");
Path pageFilePathFormat = outputDirectory.resolve("page_{0}.html");
```

*Warum?* Das organisierte Aufbewahren gerenderter Dateien erleichtert das Bereitstellen von einem Web‑Server oder das Einbetten in eine Benutzeroberfläche.

### 2. Initialisieren Sie den Viewer mit Ihrer Projektdatei

```java
try (Viewer viewer = new Viewer("YOUR_DOCUMENT_DIRECTORY/SAMPLE_MPP")) {
    // Continue with rendering steps
}
```

*Warum?* Das Laden des Dokuments bereitet den internen Parser vor und macht projektspezifische Metadaten zugänglich.

### 3. Abrufen von View‑Informationen für Projektdateien

```java
import com.groupdocs.viewer.options.ViewInfoOptions;
import com.groupdocs.viewer.results.ProjectManagementViewInfo;

ViewInfoOptions viewInfoOptions = ViewInfoOptions.forHtmlView();
ProjectManagementViewInfo viewInfo = (ProjectManagementViewInfo) viewer.getViewInfo(viewInfoOptions);
```

*Warum?* `ProjectManagementViewInfo` liefert Ihnen die Start‑ und Enddaten des Zeitplans, die Sie später verwenden, um den Rendering‑Umfang zu begrenzen.

### 4. Konfigurieren der HTML‑Rendering‑Optionen (HTML aus Projekt generieren)

```java
import com.groupdocs.viewer.options.HtmlViewOptions;

HtmlViewOptions viewOptions = HtmlViewOptions.forEmbeddedResources(pageFilePathFormat);
viewOptions.getProjectManagementOptions().setStartDate(viewInfo.getStartDate());
viewOptions.getProjectManagementOptions().setEndDate(viewInfo.getEndDate());
```

*Warum?* Durch das Setzen von `StartDate` und `EndDate` wird GroupDocs angewiesen, nur Daten innerhalb dieses Zeitfensters zu **generate html view mpp**.

### 5. Ausführen des Rendering‑Prozesses

```java
viewer.view(viewOptions);
```

*Warum?* Dieser Aufruf erzeugt eine Reihe von eigenständigen HTML‑Seiten, die den ausgewählten Zeitabschnitt Ihres Projektzeitplans darstellen.

## Häufige Fallstricke & Fehlersuche
- **Falsche Dateipfade** – Überprüfen Sie, dass sowohl die Quell‑`.mpp`‑Datei als auch das Ausgabeverzeichnis existieren.  
- **Nicht unterstützter Dateityp** – Stellen Sie sicher, dass das Dokument ein unterstütztes Project‑Format ist (z. B. `.mpp`, `.mpt`).  
- **Lizenzfehler** – Eine Testlizenz kann Rendering‑Grenzen setzen; wechseln Sie zu einer Voll‑Lizenz für uneingeschränkte Nutzung.  

## Praktische Anwendungen
1. **Projektzeitstrahl‑Analyse** – Zeigen Sie den Stakeholdern nur die aktuelle Phase.  
2. **Automatisiertes Reporting** – Generieren Sie zeitlich begrenzte HTML‑Berichte für wöchentliche Statusupdates.  
3. **Integration mit Dashboards** – Betten Sie die gerenderten Seiten in BI‑Tools oder benutzerdefinierte Portale ein.  
4. **Archivierung** – Speichern Sie einen web‑freundlichen Schnappschuss des Projektzeitplans für zukünftige Referenz.  

## Leistungstipps
- Verwenden Sie die Option *embedded resources*, um jede HTML‑Seite eigenständig zu halten und HTTP‑Anfragen zu reduzieren.  
- Bei sehr großen Projekten sollten Sie das Rendering in kleineren Datumsabschnitten durchführen, um den Speicherverbrauch gering zu halten.  
- Bereinigen Sie temporäre Dateien nach dem Ausliefern, um Speicherplatzverschwendung zu vermeiden.  

## Fazit
Sie wissen jetzt, **how to use GroupDocs** Viewer zu verwenden, um Projektdokumente innerhalb eines bestimmten Zeitintervalls zu rendern und **generate HTML from project** Daten in Java zu **generate HTML from project**. Diese Fähigkeit vereinfacht Zeitstrahl‑Visualisierungen, verbessert die Reporting‑Effizienz und lässt sich nahtlos in moderne Web‑Anwendungen integrieren.

### Nächste Schritte
- Erkunden Sie weitere Viewer‑Funktionen wie Wasserzeichen, Passwortschutz oder benutzerdefiniertes CSS‑Styling.  
- Kombinieren Sie diese Rendering‑Pipeline mit einer REST‑API, um zeitgesteuerte Timeline‑Ansichten auf Abruf bereitzustellen.  

## Häufig gestellte Fragen

**Q: Welche Dateiformate unterstützt GroupDocs.Viewer?**  
A: GroupDocs.Viewer unterstützt eine breite Palette von Formaten, darunter Microsoft Project (MPP), PDF, Word, Excel, PowerPoint und viele weitere.

**Q: Wie starte ich mit einer kostenlosen Testversion von GroupDocs.Viewer?**  
A: Sie können die Testversion von [here](https://releases.groupdocs.com/viewer/java/) herunterladen.

**Q: Kann ich Dokumente rendern, ohne Ressourcen einzubetten?**  
A: Ja, Sie können eine andere HTML‑View‑Option wählen, die externe Ressourcen referenziert anstatt sie einzubetten.

**Q: Was ist, wenn mein Dokument zu groß zum Rendern ist?**  
A: Erwägen Sie, das Dokument in kleinere Abschnitte zu teilen oder nur den erforderlichen Datumsbereich zu rendern, wie oben gezeigt.

**Q: Wie gehe ich mit Rendering‑Fehlern um?**  
A: Überprüfen Sie alle Konfigurationseinstellungen, stellen Sie sicher, dass Sie eine gültige Lizenz besitzen, und konsultieren Sie die GroupDocs‑Dokumentation für detaillierte Fehlercodes.

## Ressourcen
- **Dokumentation**: [GroupDocs Viewer Java Documentation](https://docs.groupdocs.com/viewer/java/)  
- **API Reference**: [GroupDocs API Reference](https://reference.groupdocs.com/viewer/java/)  
- **Download**: [GroupDocs Downloads](https://releases.groupdocs.com/viewer/java/)  
- **Purchase**: [Buy GroupDocs License](https://purchase.groupdocs.com/buy)  
- **Free Trial**: [Try the Free Version](https://releases.groupdocs.com/viewer/java/)  
- **Temporary License**: [Get a Temporary License](https://purchase.groupdocs.com/temporary-license/)  
- **Support**: [GroupDocs Forum](https://forum.groupdocs.com/c/viewer/9)

---

**Zuletzt aktualisiert:** 2026-03-29  
**Getestet mit:** GroupDocs.Viewer 25.2 for Java  
**Autor:** GroupDocs  

---