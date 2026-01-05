---
date: '2026-01-05'
description: Erfahren Sie, wie Sie E‑Mail‑Felder umbenennen, E‑Mails in HTML konvertieren
  und E‑Mail‑Header mit GroupDocs.Viewer für Java anpassen.
keywords:
- rename email fields Java
- render emails HTML GroupDocs Viewer
- customize email metadata Java
title: Wie man E‑Mail‑Felder beim Rendern von E‑Mails zu HTML mit GroupDocs.Viewer
  Java umbenennt
type: docs
url: /de/java/advanced-rendering/rename-email-fields-html-groupdocs-viewer-java/
weight: 1
---

# Wie man E‑Mail‑Felder beim Rendern von E‑Mails zu HTML mit GroupDocs.Viewer Java umbenennt

Fragen Sie sich, **wie man E‑Mail**‑Felder beim Konvertieren einer E‑Mail zu HTML umbenennt? In diesem Leitfaden gehen wir die genauen Schritte zum Umbenennen von E‑Mail‑Feldern, **E‑Mail zu HTML konvertieren** und **E‑Mail‑Header anpassen** mit GroupDocs.Viewer für Java durch. Am Ende haben Sie eine saubere HTML‑Darstellung mit Ihren bevorzugten Header‑Namen, wodurch die Ausgabe leichter zu lesen und in Ihre Anwendungen zu integrieren ist.

![E‑Mail‑Felder beim Konvertieren von E‑Mails zu HTML mit GroupDocs.Viewer für Java](/viewer/advanced-rendering/rename-email-fields-when-converting-emails-to-html-java.png)

### Was Sie lernen werden
- Wie man GroupDocs.Viewer für Java verwendet, um **E‑Mail zu HTML zu konvertieren**.  
- Techniken zum **Umbenennen von E‑Mail‑Feldern** wie „From“, „To“, „Sent“ und „Subject“.  
- Best Practices für die Einrichtung von Maven und Lizenzierung.  
- Praxisnahe Szenarien, in denen **Anpassen von E‑Mail‑Headern** Mehrwert schafft.

## Schnelle Antworten
- **Was bedeutet “how to rename email”?** Es bezieht sich auf das Zuordnen von Standard‑E‑Mail‑Header‑Namen zu benutzerdefinierten Bezeichnungen während des Renderns.  
- **Welche Bibliothek übernimmt die Konvertierung?** GroupDocs.Viewer für Java (v25.2+).  
- **Benötige ich eine Lizenz?** Eine Testversion funktioniert für die Evaluierung; für die Produktion ist eine Voll‑Lizenz erforderlich.  
- **Kann ich jeden Header‑Namen ändern?** Ja, jeder Standard‑E‑Mail‑Header kann über `fieldTextMap` neu zugeordnet werden.  
- **Ist die Ausgabe HTML oder eingebettete Ressourcen?** Sie können eingebettete Ressourcen für eine einzelne eigenständige Datei wählen.

## Was bedeutet “How to Rename Email” im Kontext von GroupDocs.Viewer?
Das Umbenennen von E‑Mail‑Feldern bedeutet, die Standard‑Bezeichnungen (z. B. „From“) durch benutzerdefinierten Text (z. B. „Sender“) zu ersetzen, wenn die E‑Mail zu HTML gerendert wird. Dies ist nützlich, um die Ausgabe an die Unternehmens‑Terminologie anzupassen oder die Lesbarkeit für End‑Benutzer zu verbessern.

## Warum E‑Mail zu HTML konvertieren und E‑Mail‑Header anpassen?
- **Konsistente Markenführung:** Stimmen Sie die Sprache Ihrer Organisation über alle Kommunikationskanäle hinweg ab.  
- **Verbesserte Durchsuchbarkeit:** Benutzerdefinierte Header können in Archivierungssystemen effektiver indiziert werden.  
- **Bessere UI‑Integration:** Passen Sie das HTML‑Snippet an, damit es nahtlos in Webportale oder Support‑Dashboards passt.

## Voraussetzungen

### Erforderliche Bibliotheken, Versionen und Abhängigkeiten
- **GroupDocs.Viewer für Java** – Version 25.2 oder später.  
- **Java Development Kit (JDK)** – Version 8+.

### Anforderungen an die Umgebungseinrichtung
- **Maven** für das Abhängigkeitsmanagement.  
- Eine IDE wie IntelliJ IDEA, Eclipse oder VS Code.

### Wissensvoraussetzungen
Grundkenntnisse in Java und Maven helfen Ihnen, dem Leitfaden schnell zu folgen.

## Einrichtung von GroupDocs.Viewer für Java

### Maven‑Konfiguration
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
- **Temporäre Lizenz:** Erhalten Sie eine temporäre Lizenz, um die vollen Funktionen ohne Einschränkungen zu erkunden, unter [GroupDocs Temporary License](https://purchase.groupdocs.com/temporary-license/).  
- **Kauf:** Für die fortlaufende Nutzung sollten Sie den Kauf einer Lizenz über [GroupDocs Purchase](https://purchase.groupdocs.com/buy) in Betracht ziehen.

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

## Implementierungs‑Leitfaden

### Umbenennen von E‑Mail‑Feldern – Schritt für Schritt

#### 1. Pfad des Ausgabeverzeichnisses festlegen
```java
import java.nio.file.Path;

Path outputDirectory = Utils.getOutputDirectoryPath("YOUR_OUTPUT_DIRECTORY");
```
*Ersetzen Sie `"YOUR_OUTPUT_DIRECTORY"` durch den Ordner, in dem Sie die HTML‑Dateien speichern möchten.*

#### 2. Seiten‑Dateipfad‑Format definieren
```java
Path pageFilePathFormat = outputDirectory.resolve("page_{0}.html");
```
*`{0}` wird während des Renderns durch die Seitennummer ersetzt.*

#### 3. Zuordnung von E‑Mail‑Feldern zu neuen Namen erstellen
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

#### 4. HTML‑Ansichtsoptionen konfigurieren
```java
import com.groupdocs.viewer.options.HtmlViewOptions;

HtmlViewOptions viewOptions = HtmlViewOptions.forEmbeddedResources(pageFilePathFormat);
viewOptions.getEmailOptions().setFieldTextMap(fieldTextMap);
```
*`forEmbeddedResources` bündelt CSS/JS innerhalb des HTML, während `setFieldTextMap` die benutzerdefinierten Header‑Namen anwendet.*

#### 5. E‑Mail zu HTML rendern
```java
try (Viewer viewer = new Viewer("YOUR_DOCUMENT_DIRECTORY/SAMPLE_MSG")) {
    viewer.view(viewOptions);
}
```
*Ersetzen Sie `"YOUR_DOCUMENT_DIRECTORY/SAMPLE_MSG"` durch den tatsächlichen Pfad zu Ihrer MSG‑Datei.*

#### Tipps zur Fehlerbehebung
- Stellen Sie sicher, dass das Ausgabeverzeichnis beschreibbar ist.  
- Vergewissern Sie sich, dass die Eingabe‑MSG‑Datei existiert und der Pfad korrekt ist.  
- Verwenden Sie dieselbe GroupDocs.Viewer‑Version (25.2), die im Maven deklariert ist.

## Praktische Anwendungen
1. **Benutzerdefinierte E‑Mail‑Berichte:** Stimmen Sie die E‑Mail‑Header mit der Unternehmens‑Terminologie ab für klarere Berichte.  
2. **E‑Mail‑Archivierungssysteme:** Verbessern Sie die Durchsuchbarkeit durch die Verwendung standardisierter Header‑Namen.  
3. **Kundensupport‑Plattformen:** Stellen Sie Tickets mit personalisierten Header‑Bezeichnungen dar für ein besseres Agentenerlebnis.

## Leistungsüberlegungen
- Entsorgen Sie `Viewer`‑Objekte mit try‑with‑resources, um den Speicher schnell freizugeben.  
- Profilieren Sie große Stapel und erwägen Sie, E‑Mails bei Bedarf in parallelen Streams zu verarbeiten.

## Fazit
Sie wissen jetzt, **wie man E‑Mail‑Felder** beim **Konvertieren von E‑Mail zu HTML** und **Anpassen von E‑Mail‑Headern** mit GroupDocs.Viewer für Java umbenennt. Diese Technik gibt Ihnen die volle Kontrolle über die Darstellung von E‑Mail‑Metadaten in HTML‑Ausgaben.

### Nächste Schritte
- Experimentieren Sie mit zusätzlichen Feldzuordnungen (z. B. CC, BCC).  
- Erkunden Sie andere Render‑Formate wie PDF oder PNG.  
- Besuchen Sie [GroupDocs Documentation](https://docs.groupdocs.com/viewer/java/) für tiefere API‑Einblicke.

## FAQ‑Abschnitt
1. **Kann ich alle E‑Mail‑Header mit dieser Methode umbenennen?**  
   - Ja, Sie können jeden Standard‑E‑Mail‑Header nach Ihren Anforderungen auf einen neuen Namen abbilden.  
2. **Ist es möglich, GroupDocs.Viewer ohne Lizenz zu verwenden?**  
   - Eine Testversion steht zum Testen zur Verfügung, aber eine voll funktionsfähige Version erfordert eine gültige Lizenz.  
3. **Wie gehe ich effizient mit großen Mengen an E‑Mails mit GroupDocs.Viewer um?**  
   - Erwägen Sie die Stapelverarbeitung und optimieren Sie Systemressourcen, um größere Datensätze effektiv zu verwalten.  
4. **Kann ich diese Lösung in eine bestehende Java‑Anwendung integrieren?**  
   - Absolut, die Integration ist dank Maven‑Abhängigkeiten unkompliziert.  
5. **Wo finde ich Unterstützung, wenn ich auf Probleme stoße?**  
   - Besuchen Sie das [GroupDocs Forum](https://forum.groupdocs.com/c/viewer/9) für Community‑ und offizielle Unterstützung.

## Häufig gestellte Fragen

**Q: Funktioniert dieser Ansatz mit anderen E‑Mail‑Formaten wie EML?**  
A: Ja, GroupDocs.Viewer unterstützt sowohl MSG‑ als auch EML‑Dateien; dieselbe Feld‑Mapping‑Logik gilt.

**Q: Kann ich das HTML ohne eingebettete Ressourcen ausgeben?**  
A: Sie können `HtmlViewOptions.forExternalResources(...)` verwenden, wenn Sie separate CSS/JS‑Dateien bevorzugen.

**Q: Welche Version von GroupDocs.Viewer wurde getestet?**  
A: Der Code wurde mit GroupDocs.Viewer **25.2** getestet.

**Q: Ist es möglich, die Schriftart oder den Stil der benutzerdefinierten Header zu ändern?**  
A: Das Styling kann nach dem Rendern über CSS angewendet werden, oder Sie können benutzerdefiniertes CSS mit `HtmlViewOptions.getResourcesPath()` einfügen.

**Q: Wie kann ich programmgesteuert den Pfad der erzeugten HTML‑Datei abrufen?**  
A: Der Dateipfad folgt dem Muster, das in `pageFilePathFormat` definiert ist; Sie können ihn mit `String.format` und der Seitennummer erstellen.

## Ressourcen
- **Dokumentation:** Umfassende Anleitungen finden Sie unter [GroupDocs Documentation](https://docs.groupdocs.com/viewer/java/).  
- **API‑Referenz:** Detaillierte API‑Informationen finden Sie auf [GroupDocs API Reference](https://reference.groupdocs.com/viewer/java/).  
- **GroupDocs.Viewer herunterladen:** Greifen Sie über die [Downloads Page](https://releases.groupdocs.com/viewer/java/) auf die neueste Version zu.

---

**Zuletzt aktualisiert:** 2026-01-05  
**Getestet mit:** GroupDocs.Viewer 25.2  
**Autor:** GroupDocs