---
date: '2026-02-23'
description: Lär dig hur du ställer in antal objekt per sida, bäddar in resurser i
  HTML och batchkonverterar arkiv till enkel‑ eller flersidig HTML med GroupDocs.Viewer
  Java.
keywords:
- convert archives to HTML Java
- GroupDocs.Viewer Java tutorial
- render ZIP RAR to HTML
title: 'Ange antal objekt per sida: Konvertera arkiv till HTML med GroupDocs.Viewer
  Java'
type: docs
url: /sv/java/export-conversion/groupdocs-viewer-java-convert-archives-html/
weight: 1
---

# Ställ in objekt per sida: Konvertera arkiv till HTML med GroupDocs.Viewer Java

Att konvertera arkivfiler som ZIP eller RAR till webbvänlig HTML är ett vanligt behov när du vill dela eller granska dokument direkt i en webbläsare. I den här guiden lär du dig **hur du ställer in objekt per sida** när du renderar arkiv, hur du bäddar in resurser i HTML för en självständig output, och hur du batch‑konverterar arkiv effektivt med GroupDocs.Viewer Java.

![Konvertera arkiv till HTML med GroupDocs.Viewer för Java](/viewer/export-conversion/convert-archives-to-html-java.png)

## Snabba svar
- **Vad styr “set items per page”?** Det bestämmer hur många filer eller mappar från ett arkiv som visas på varje genererad HTML‑sida.  
- **Kan jag bädda in bilder och CSS direkt i HTML?** Ja – använd `forEmbeddedResources`‑alternativet för att bädda in resurser i HTML.  
- **Är batch‑konvertering möjlig?** Absolut; du kan loopa över en samling arkiv och rendera var och en med samma inställningar.  
- **Behöver jag Maven för att använda GroupDocs.Viewer?** Ja, lägg till `maven groupdocs viewer`‑beroendet som visas nedan.  
- **Vilka utdataformat stöds?** Single‑page HTML Java och multi‑page HTML Java är båda tillgängliga.

## Vad är “set items per page” i GroupDocs.Viewer?
Inställningen **set items per page** tillhör alternativen för arkivrendering. Den talar om för visaren hur många arkivinlägg (filer eller mappar) som ska visas på varje HTML‑sida när du genererar ett flersidigt HTML‑dokument. Att justera detta värde hjälper dig att balansera sidstorlek och navigeringshastighet, särskilt för stora arkiv.

## Varför bädda in resurser i HTML?
Att bädda in resurser (bilder, CSS, teckensnitt) direkt i HTML‑filen skapar ett enda, portabelt dokument som kan öppnas utan externa filer. Detta är idealiskt för e‑postbilagor, offline‑visning eller för att bädda in resultatet i andra webbsidor.

## Förutsättningar

- **Krävda bibliotek:** Inkludera GroupDocs.Viewer version 25.2 eller senare.  
- **Miljö:** Java Development Kit (JDK) installerat och konfigurerat.  
- **Kunskap:** Grundläggande Java och Maven‑beroendehantering.  

## Maven GroupDocs Viewer‑inställning

Lägg till GroupDocs‑arkivet och viewer‑beroendet i din `pom.xml`:

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

### Licensanskaffning
GroupDocs.Viewer erbjuder en **gratis provlänk**, en tillfällig licens eller ett fullständigt köp. Välj den som passar ditt projekts tidsplan.

### Grundläggande initiering
Efter Maven‑inställningen, ta in visaren i din kod:

```java
import com.groupdocs.viewer.Viewer;
// Your initialization code here
```

## Så renderar du arkiv till enkel‑sidig HTML

### Steg 1: Definiera utdatamapp
```java
Path outputDirectory = Utils.getOutputDirectoryPath("YOUR_OUTPUT_DIRECTORY");
```

### Steg 2: Ange filnamn för enkel‑sidig output
```java
Path pageFilePathFormat = outputDirectory.resolve("RAR_result.html");
```

### Steg 3: Initiera visaren
```java
try (Viewer viewer = new Viewer(TestFiles.SAMPLE_RAR_WITH_FOLDERS)) {
    // Further configuration steps follow
}
```

### Steg 4: Konfigurera renderingsalternativ (bädda in resurser i HTML)
```java
HtmlViewOptions options = HtmlViewOptions.forEmbeddedResources(pageFilePathFormat);
```

### Steg 5: Rendera som en enda sida
```java
options.setRenderToSinglePage(true);
viewer.view(options);
```

## Så renderar du arkiv till flersidig HTML och ställer in objekt per sida

### Steg 1: Återanvänd utdatamappen
```java
Path outputDirectory = Utils.getOutputDirectoryPath("YOUR_OUTPUT_DIRECTORY");
```

### Steg 2: Definiera filnamnsformat för flera sidor
```java
Path pageFilePathFormat = outputDirectory.resolve("RAR_result_page_{0}.html");
```

### Steg 3: Initiera visaren igen
```java
try (Viewer viewer = new Viewer(TestFiles.SAMPLE_RAR_WITH_FOLDERS)) {
    // Continue with multi‑page configuration
}
```

### Steg 4: Konfigurera flersidiga alternativ (bädda in resurser i HTML)
```java
HtmlViewOptions options = HtmlViewOptions.forEmbeddedResources(pageFilePathFormat);
```

### Steg 5: Ställ in objekt per sida (primärt nyckelord i handlingen)
```java
options.getArchiveOptions().setItemsPerPage(10); // Default is 16
viewer.view(options);
```

## Praktiska tillämpningar

- **Dokumenthanteringssystem:** Lägg till förhandsgranskning av arkiv utan att installera extra visare.  
- **Webbportaler:** Erbjud användare ett snabbt, nedladdningsfritt sätt att utforska samlade dokument.  
- **Samarbetsverktyg:** Låt team inspektera delade arkiv direkt i webbläsaren.  

## Prestandaöverväganden

- **Resurshantering:** Håll koll på minnesanvändning; överväg att finjustera JVM:s skräpsamlare för stora batcher.  
- **Batch‑konvertera arkiv:** Loop igenom en lista med arkivfiler och anropa samma renderingslogik för att maximera genomströmning.  
- **Cache‑strategi:** Spara renderad HTML i en cache om samma arkiv ofta nås.  

## Vanliga frågor

**Q: Vad är GroupDocs.Viewer Java?**  
A: Ett mångsidigt bibliotek för att rendera dokument—inklusive arkiv—till format som HTML, PDF och bilder.

**Q: Hur kan jag få en gratis provversion av GroupDocs.Viewer?**  
A: Besök [free trial link](https://releases.groupdocs.com/viewer/java/) för att ladda ner och testa.

**Q: Kan jag konvertera andra dokumenttyper än arkiv?**  
A: Ja, visaren stöder PDF, Word, Excel och många fler format.

**Q: Vad ska jag göra om renderingen är långsam?**  
A: Minska antalet objekt per sida, aktivera streaming eller bearbeta arkiv i mindre batcher.

**Q: Var kan jag få hjälp eller support?**  
A: Kontakta via [support forum](https://forum.groupdocs.com/c/viewer/9).

**Q: Är det möjligt att bädda in CSS och bilder direkt i HTML?**  
A: Absolut—använd `HtmlViewOptions.forEmbeddedResources` som visas i exemplen.

**Q: Hur batch‑konverterar jag en mapp med arkiv?**  
A: Iterera över varje fil med en `for`‑loop och applicera samma `Viewer`‑ och `HtmlViewOptions`‑konfiguration för varje iteration.

## Resurser

- **Dokumentation:** Fördjupa dig i funktionaliteten med [GroupDocs documentation](https://docs.groupdocs.com/viewer/java/).  
- **API‑referens:** Utforska hela API:n på [GroupDocs API](https://reference.groupdocs.com/viewer/java/).  
- **Nedladdning:** Hämta de senaste binärerna från [download page](https://releases.groupdocs.com/viewer/java/).  
- **Köp och licensiering:** Granska alternativ på [purchase page](https://purchase.groupdocs.com/buy).  
- **Support och community:** Delta i diskussioner på [GroupDocs forum](https://forum.groupdocs.com/c/viewer/9).

---

**Senast uppdaterad:** 2026-02-23  
**Testat med:** GroupDocs.Viewer 25.2  
**Författare:** GroupDocs