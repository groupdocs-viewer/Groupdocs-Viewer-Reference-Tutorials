---
date: '2026-03-24'
description: Erfahren Sie, wie Sie E-Mails mit GroupDocs Viewer für Java in HTML konvertieren
  und E-Mail‑Felder umbenennen. Dieser Leitfaden zeigt, wie E-Mails als HTML mit benutzerdefinierten
  Headern gerendert werden.
keywords:
- rename email fields Java
- render emails HTML GroupDocs Viewer
- customize email metadata Java
title: E‑Mail in HTML konvertieren & Felder umbenennen – GroupDocs Viewer Java
type: docs
url: /de/java/advanced-rendering/rename-email-fields-html-groupdocs-viewer-java/
weight: 1
---

# E‑Mail in HTML konvertieren & Felder umbenennen – GroupDocs Viewer Java

Wenn Sie **E‑Mail in HTML konvertieren** und den E‑Mail‑Headern ein individuelles Aussehen verleihen möchten, sind Sie hier genau richtig. In diesem Tutorial führen wir Sie Schritt für Schritt durch das Umbenennen von E‑Mail‑Feldern, **E‑Mail in HTML konvertieren** und das Anpassen von E‑Mail‑Headern mit GroupDocs.Viewer für Java. Am Ende haben Sie eine saubere HTML‑Darstellung mit den von Ihnen gewünschten Header‑Bezeichnungen, wodurch die Ausgabe leichter zu lesen und in Ihre Anwendungen zu integrieren ist.

![E‑Mail‑Felder beim Konvertieren von E‑Mails zu HTML mit GroupDocs.Viewer für Java](/viewer/advanced-rendering/rename-email-fields-when-converting-emails-to-html-java.png)

### Was Sie lernen werden
- Wie man GroupDocs.Viewer für Java verwendet, um **E‑Mail in HTML zu konvertieren**.  
- Techniken zum **Umbenennen von E‑Mail‑Feldern** wie „From“, „To“, „Sent“ und „Subject“.  
- Best Practices für die Einrichtung von Maven und Lizenzierung.  
- Praxisbeispiele, bei denen das **Anpassen von E‑Mail‑Headern** Mehrwert schafft.

## Schnelle Antworten
- **Was bedeutet „E‑Mail in HTML konvertieren“?** Es bedeutet, dass eine E‑Mail‑Datei (MSG/EML) als web‑fertiges HTML‑Dokument gerendert wird.  
- **Welche Bibliothek übernimmt die Konvertierung?** GroupDocs.Viewer für Java (v25.2+).  
- **Benötige ich eine Lizenz?** Eine Testversion funktioniert für die Evaluierung; für die Produktion ist eine Voll‑Lizenz erforderlich.  
- **Kann ich irgendeinen Header‑Namen ändern?** Ja, jeder Standard‑E‑Mail‑Header kann über `fieldTextMap` neu zugeordnet werden.  
- **Ist die Ausgabe HTML oder eingebettete Ressourcen?** Sie können eingebettete Ressourcen für eine einzelne, eigenständige Datei wählen.

## Was bedeutet „E‑Mail in HTML konvertieren“ im Kontext von GroupDocs.Viewer?
Das Konvertieren von E‑Mail in HTML bedeutet, dass eine rohe E‑Mail‑Datei genommen und eine HTML‑Seite erzeugt wird, die den Nachrichteninhalt zusammen mit den Metadaten anzeigt. Wenn Sie zudem **E‑Mail‑Felder umbenennen**, werden die Standard‑Bezeichnungen (z. B. „From“) durch benutzerdefinierten Text (z. B. „Sender“) ersetzt, was Ihnen hilft, die Unternehmens‑Terminologie anzupassen oder die UI‑Konsistenz zu verbessern.

## Warum E‑Mail in HTML konvertieren und E‑Mail‑Felder umbenennen?
- **Konsistente Markenführung:** Passen Sie die Ausgabe an die Sprache Ihrer Organisation an.  
- **Verbesserte Durchsuchbarkeit:** Benutzerdefinierte Header können in Archivierungssystemen effektiver indiziert werden.  
- **Bessere UI‑Integration:** Passen Sie das HTML‑Snippet an, damit es nahtlos in Webportale oder Support‑Dashboards passt.

## Voraussetzungen

### Erforderliche Bibliotheken, Versionen und Abhängigkeiten
- **GroupDocs.Viewer für Java** – Version 25.2 oder neuer.  
- **Java Development Kit (JDK)** – Version 8+.

### Anforderungen an die Umgebung
- **Maven** für das Abhängigkeitsmanagement.  
- Eine IDE wie IntelliJ IDEA, Eclipse oder VS Code.

### Wissensvoraussetzungen
Grundkenntnisse in Java und Maven helfen Ihnen, dem Tutorial schnell zu folgen.

## Einrichtung von GroupDocs.Viewer für Java

### Maven-Konfiguration
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
- **Kostenlose Testversion:** Laden Sie eine kostenlose Testversion von [GroupDocs Releases](https://releases.groupdocs.com/viewer/java/) herunter.  
- **Temporäre Lizenz:** Erhalten Sie eine temporäre Lizenz, um die vollen Funktionen ohne Einschränkungen zu testen, unter [GroupDocs Temporary License](https://purchase.groupdocs.com/temporary-license/).  
- **Kauf:** Für den fortlaufenden Einsatz sollten Sie den Kauf einer Lizenz über [GroupDocs Purchase](https://purchase.groupdocs.com/buy) in Betracht ziehen.

### Grundlegende Initialisierung und Einrichtung
```java
import com.groupdocs.viewer.Viewer;

public class ViewerSetup {
    public static void main(String[] args) {
        try (Viewer viewer = new Viewer("path/to/your/document.msg")) {
            // Perform operations here
        }
    }
}
```
Passen Sie den Dateipfad an, damit er auf Ihre `.msg`‑Datei verweist.

## Wie man E‑Mail in HTML konvertiert und Felder umbenennt – Schritt für Schritt

### 1. Ausgabe‑Verzeichnis‑Pfad festlegen
```java
import java.nio.file.Path;

Path outputDirectory = Utils.getOutputDirectoryPath("YOUR_OUTPUT_DIRECTORY");
```
*Ersetzen Sie `"YOUR_OUTPUT_DIRECTORY"` durch den Ordner, in dem die HTML‑Dateien gespeichert werden sollen.*

### 2. Seiten‑Dateipfad‑Format definieren
```java
Path pageFilePathFormat = outputDirectory.resolve("page_{0}.html");
```
*`{0}` wird während des Renderns durch die Seitennummer ersetzt.*

### 3. Zuordnung von E‑Mail‑Feldern zu neuen Bezeichnungen erstellen
```java
import com.groupdocs.viewer.options.Field;
import java.util.HashMap;
import java.util.Map;

Map<Field, String> fieldTextMap = new HashMap<>();
fieldTextMap.put(Field.FROM, "Sender");
fieldTextMap.put(Field.TO, "Receiver");
fieldTextMap.put(Field.SENT, "Date");
fieldTextMap.put(Field.SUBJECT, "Topic");
```
*Hier ändern wir die Standard‑Bezeichnungen zu benutzerdefinierten.*

### 4. HTML‑Ansichtsoptionen konfigurieren
```java
import com.groupdocs.viewer.options.HtmlViewOptions;

HtmlViewOptions viewOptions = HtmlViewOptions.forEmbeddedResources(pageFilePathFormat);
viewOptions.getEmailOptions().setFieldTextMap(fieldTextMap);
```
*`forEmbeddedResources` bündelt CSS/JS innerhalb des HTML, während `setFieldTextMap` die benutzerdefinierten Header‑Bezeichnungen anwendet.*

### 5. E‑Mail in HTML rendern
```java
try (Viewer viewer = new Viewer("YOUR_DOCUMENT_DIRECTORY/SAMPLE_MSG")) {
    viewer.view(viewOptions);
}
```
*Ersetzen Sie `"YOUR_DOCUMENT_DIRECTORY/SAMPLE_MSG"` durch den tatsächlichen Pfad zu Ihrer MSG‑Datei.*

#### Tipps zur Fehlerbehebung
- Stellen Sie sicher, dass das Ausgabeverzeichnis beschreibbar ist.  
- Vergewissern Sie sich, dass die Eingabe‑MSG‑Datei existiert und der Pfad korrekt ist.  
- Verwenden Sie dieselbe GroupDocs.Viewer‑Version (25.2), die im Maven angegeben ist.

## Praktische Anwendungen
1. **Benutzerdefinierte E‑Mail‑Berichte:** Passen Sie E‑Mail‑Header an die Unternehmens‑Terminologie an, um klarere Berichte zu erhalten.  
2. **E‑Mail‑Archivierungssysteme:** Verbessern Sie die Durchsuchbarkeit durch die Verwendung standardisierter Header‑Bezeichnungen.  
3. **Kunden‑Support‑Plattformen:** Stellen Sie Tickets mit personalisierten Header‑Bezeichnungen dar, um die Agenten‑Erfahrung zu verbessern.

## Leistungsüberlegungen
- Entsorgen Sie `Viewer`‑Objekte mit try‑with‑resources, um den Speicher sofort freizugeben.  
- Profilieren Sie große Stapel und erwägen Sie bei Bedarf die Verarbeitung von E‑Mails in parallelen Streams.

## Fazit
Sie wissen jetzt, **wie man E‑Mail in HTML konvertiert**, **E‑Mail‑Felder umbenennt** und **E‑Mail‑Header mit GroupDocs.Viewer für Java anpasst**. Diese Technik gibt Ihnen die volle Kontrolle über die Darstellung von E‑Mail‑Metadaten in HTML‑Ausgaben.

### Nächste Schritte
- Experimentieren Sie mit zusätzlichen Feldzuordnungen (z. B. CC, BCC).  
- Entdecken Sie weitere Render‑Formate wie PDF oder PNG.  
- Besuchen Sie [GroupDocs Documentation](https://docs.groupdocs.com/viewer/java/) für tiefere API‑Einblicke.

## Häufig gestellte Fragen

**F: Funktioniert dieser Ansatz mit anderen E‑Mail‑Formaten wie EML?**  
A: Ja, GroupDocs.Viewer unterstützt sowohl MSG‑ als auch EML‑Dateien; die gleiche Feld‑Mapping‑Logik gilt.

**F: Kann ich das HTML ohne eingebettete Ressourcen ausgeben?**  
A: Sie können `HtmlViewOptions.forExternalResources(...)` verwenden, wenn Sie separate CSS/JS‑Dateien bevorzugen.

**F: Welche Version von GroupDocs.Viewer wurde getestet?**  
A: Der Code wurde mit GroupDocs.Viewer **25.2** getestet.

**F: Ist es möglich, die Schriftart oder den Stil der benutzerdefinierten Header zu ändern?**  
A: Das Styling kann nach dem Rendern über CSS angewendet werden, oder Sie können benutzerdefiniertes CSS mit `HtmlViewOptions.getResourcesPath()` einfügen.

**F: Wie kann ich programmgesteuert den Pfad der erzeugten HTML‑Datei abrufen?**  
A: Der Dateipfad folgt dem in `pageFilePathFormat` definierten Muster; Sie können ihn mit `String.format` und der Seitennummer erstellen.

## Ressourcen
- **Dokumentation:** Umfassende Anleitungen finden Sie unter [GroupDocs Documentation](https://docs.groupdocs.com/viewer/java/).  
- **API‑Referenz:** Detaillierte API‑Informationen finden Sie auf [GroupDocs API Reference](https://reference.groupdocs.com/viewer/java/).  
- **GroupDocs.Viewer herunterladen:** Greifen Sie über die [Downloads Page](https://releases.groupdocs.com/viewer/java/) auf die neueste Version zu.

---

**Zuletzt aktualisiert:** 2026-03-24  
**Getestet mit:** GroupDocs.Viewer 25.2  
**Autor:** GroupDocs