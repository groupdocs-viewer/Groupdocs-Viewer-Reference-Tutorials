---
date: '2026-06-15'
description: Lär dig hur du konverterar Excel till PDF Java och delar Excel sheets
  efter rows och columns med GroupDocs Viewer. Inkluderar setup, code och best practices.
keywords:
- convert excel to pdf java
- split excel sheet rows
- split excel sheet columns
schemas:
- author: GroupDocs
  dateModified: '2026-06-15'
  description: Learn how to convert Excel to PDF Java and split Excel sheets by rows
    and columns using GroupDocs Viewer. Includes setup, code, and best practices.
  headline: Convert Excel to PDF Java & Split Sheets by Rows & Columns
  type: TechArticle
- description: Learn how to convert Excel to PDF Java and split Excel sheets by rows
    and columns using GroupDocs Viewer. Includes setup, code, and best practices.
  name: Convert Excel to PDF Java & Split Sheets by Rows & Columns
  steps:
  - name: Set Up Paths and Initialize the Viewer
    text: First, define where the split pages will be saved and create a `Viewer`
      instance for the source workbook.
  - name: Configure Rows Per Page
    text: Tell the viewer how many rows each page should contain.
  - name: Render the Document
    text: Finally, render the workbook using the options you defined.
  - name: Set Up Paths and Initialize the Viewer
    text: The setup mirrors the row‑only example, only the file name changes.
  - name: Configure Rows and Columns Per Page
    text: Specify both dimensions to create a grid‑style split.
  - name: Render the Document
    text: Render using the same `view` call.
  type: HowTo
- questions:
  - answer: Yes. Replace `HtmlViewOptions` with `PdfViewOptions` and keep the same
      `SpreadsheetOptions` configuration.
    question: Can I generate a PDF instead of HTML?
  - answer: Direct content‑based splitting isn’t built into GroupDocs Viewer, but
      you can preprocess the workbook with Apache POI to create separate sheets before
      rendering.
    question: Is it possible to split based on cell content rather than fixed rows/columns?
  - answer: Absolutely. The viewer handles XLS, XLSX, CSV, and other spreadsheet formats.
    question: Does GroupDocs Viewer support older Excel formats (XLS)?
  - answer: Serve the output folder as a static resource and reference the generated
      `page_0.html`, `page_1.html`, etc., from your Thymeleaf or JSP templates.
    question: How do I embed the generated HTML into a Spring MVC view?
  - answer: A full production license from GroupDocs is required; trial licenses are
      for evaluation only.
    question: What license do I need for commercial deployment?
  type: FAQPage
title: Konvertera Excel till PDF Java & Dela Sheets efter Rows & Columns
type: docs
url: /sv/java/custom-rendering/groupdocs-viewer-java-split-excel-sheets-rows-columns/
weight: 1
---

# Konvertera Excel till PDF Java & Dela blad efter rader och kolumner (Java)

Stora Excel‑arbetsböcker innehåller ofta mer data än vad som bekvämt kan visas på en enda skärm eller skrivas ut på en sida. **convert excel to pdf java** är ett vanligt krav när du behöver ett statiskt, delbart format, medan **splitting Excel sheets by rows and columns** gör data lättare att konsumera i webb‑ eller utskriftslayouter. I den här guiden går vi igenom båda uppgifterna med **GroupDocs Viewer for Java**, visar hur du konfigurerar paginering och förklarar bästa praxis‑tips för prestanda och felsökning.

![Dela Excel-blad efter rader och kolumner med GroupDocs.Viewer för Java](/viewer/custom-rendering/split-excel-sheets-by-rows-and-columns.png)

[ Dela Excel-blad efter rader och kolumner med GroupDocs.Viewer för Java ](/viewer/custom-rendering/split-excel-sheets-by-rows-and-columns.png)

## Snabba svar
- **What library is used?** GroupDocs Viewer for Java.  
- **Can I split by both rows and columns?** Yes – you can define rows‑per‑page and columns‑per‑page together.  
- **Do I need a license?** A trial or temporary license works for development; a full license is required for production.  
- **What output formats are supported?** HTML (embedded resources) is shown; PDF can be generated with the same options.  
- **Is Maven required?** Maven is the recommended way to manage dependencies.  
- **Can I also convert Excel to PDF?** Absolutely – just switch `HtmlViewOptions` to `PdfViewOptions` and reuse the same pagination settings.

## Vad är “How to Split Excel”?
Att dela ett Excel‑blad betyder att dela ett enskilt arbetsblad i flera sidor eller filer baserat på ett fast antal rader, kolumner eller båda. Denna teknik är praktisk när du behöver skapa paginerade rapporter, bädda in data i webbsidor eller generera utskrivbara sektioner utan att ladda hela arbetsboken på en gång.

## Varför använda GroupDocs Viewer för Java?
GroupDocs Viewer bearbetar kalkylblad i ett enda pass och paginerar dem automatiskt, vilket eliminerar manuella beräkningar. **Snabb rendering bearbetar en 250‑sidig XLSX‑arbetsbok på under 2 sekunder på en typisk 2‑kärnig server**, och **biblioteket stödjer 50+ in‑ och utdataformat**, inklusive XLS, XLSX, CSV, PDF och HTML. Det körs på alla JVM‑kompatibla plattformar—Windows, Linux, macOS, Docker‑containrar eller molnbaserade serverlösa miljöer—så du kan integrera det var din Java‑applikation än lever.

## Förutsättningar
- Java 17 eller senare installerat.  
- En IDE som IntelliJ IDEA eller Eclipse.  
- Maven för beroendehantering.  
- Grundläggande kunskaper i Java och erfarenhet av hantering av Excel‑filer.

### Nödvändiga bibliotek, versioner och beroenden
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

### Licensinnehav
Få en gratis provperiod, tillfällig licens eller köp en full licens från [GroupDocs](https://purchase.groupdocs.com/buy).

## Hur man konverterar Excel till PDF Java?

`Viewer`‑klassen är kärnkomponenten i GroupDocs Viewer som laddar ett dokument och tillhandahåller renderingsmetoder för olika utdataformat. `SpreadsheetOptions` låter dig kontrollera pagineringsinställningar såsom rows‑per‑page och columns‑per‑page för kalkylbladsrendering.

Läs in din Excel‑fil med `new Viewer("source.xlsx")`, konfigurera `SpreadsheetOptions` för paginering och anropa `viewer.view(pdfOptions, stream)` – det enda anropet konverterar arbetsboken till en PDF samtidigt som de rad‑/kolumngränser du angivit respekteras. Konverteringen bevarar formler, bilder och cellstilar och levererar en trogen PDF‑replik redo för distribution.

## Hur man delar Excel-blad efter rader

Att dela efter rader skapar en serie HTML‑sidor, var och en innehållande ett fast antal rader (t.ex. 15). Detta tillvägagångssätt är idealiskt för instrumentpaneler som visar ett begränsat antal poster per vy. Viewern genererar separata HTML‑filer såsom `page_0.html`, `page_1.html` osv., var och en med det angivna antalet rader. Detta gör det enkelt att bara ladda den del som behövs i ett webbgränssnitt, vilket minskar bandbredd och renderingtid.

### Definition Ankare
`Viewer` är GroupDocs Viewer:s kärnklass som laddar ett dokument och orkestrerar rendering till det valda utdataformatet.

### Steg‑för‑steg-implementation

#### Steg 1: Ställ in sökvägar och initiera Viewer
Först definierar du var de delade sidorna ska sparas och skapar en `Viewer`‑instans för källarbetsboken.

```java
Path outputDirectory = Path.of("YOUR_OUTPUT_DIRECTORY/SplitByRows");
Path pageFilePathFormat = outputDirectory.resolve("page_{0}.html");

try (Viewer viewer = new Viewer("YOUR_DOCUMENT_DIRECTORY/TWO_PAGES_XLSX")) {
    // Proceed with further configuration...
}
```

#### Steg 2: Konfigurera rader per sida
Berätta för viewern hur många rader varje sida ska innehålla.

```java
int countRowsPerPage = 15;
HtmlViewOptions viewOptions = HtmlViewOptions.forEmbeddedResources(pageFilePathFormat);
viewOptions.setSpreadsheetOptions(SpreadsheetOptions.forSplitSheetIntoPages(countRowsPerPage));
```

#### Steg 3: Rendera dokumentet
Slutligen renderar du arbetsboken med de alternativ du definierat.

```java
viewer.view(viewOptions);
```

## Hur man delar Excel-blad efter rader och kolumner

Ibland måste en enda sida visa en matris av rader **och** kolumner (t.ex. 15 rader × 7 kolumner). Detta ger dig full kontroll över layouten på varje HTML‑sida. De resulterande sidorna visar ett rektangulärt block av celler, till exempel rader 1‑15 och kolumner A‑G på första sidan, rader 16‑30 och kolumner H‑N på nästa. Denna rutnäts‑paginering är användbar för att skapa utskrivbara rapporter som passar standardpappersstorlekar.

### Definition Ankare
`SpreadsheetOptions` konfigurerar hur många rader och kolumner som visas på varje genererad sida.

### Steg‑för‑steg-implementation

#### Steg 1: Ställ in sökvägar och initiera Viewer
Inställningarna speglar rad‑endast‑exemplet, bara filnamnet ändras.

```java
Path outputDirectory = Path.of("YOUR_OUTPUT_DIRECTORY/SplitByRowsAndColumns");
Path pageFilePathFormat = outputDirectory.resolve("page_{0}.html");

try (Viewer viewer = new Viewer("YOUR_DOCUMENT_DIRECTORY/FOUR_PAGES_XLSX")) {
    // Continue with configuration...
}
```

#### Steg 2: Konfigurera rader och kolumner per sida
Ange båda dimensionerna för att skapa en rutnäts‑delning.

```java
int countRowsPerPage = 15;
int countColumnsPerPage = 7;

HtmlViewOptions options = HtmlViewOptions.forEmbeddedResources(pageFilePathFormat);
options.setSpreadsheetOptions(SpreadsheetOptions.forSplitSheetIntoPages(countRowsPerPage, countColumnsPerPage));
```

#### Steg 3: Rendera dokumentet
Rendera med samma `view`‑anrop.

```java
viewer.view(options);
```

## Praktiska tillämpningar
- **Generate Excel report Java**: Förvandla stora finansiella modeller till en serie paginerade HTML‑rapporter.  
- **GroupDocs Viewer Excel**: Bädda in delade sidor direkt i en webbportal för interaktiv datautforskning.  
- **Render Excel HTML Java**: Servera de genererade HTML‑sidorna via en servlet eller Spring‑controller för snabb klient‑sid rendering.  

## Prestandaöverväganden
- **Minnesanvändning** – Stora arbetsböcker kan förbruka betydande heap; överväg att öka JVM‑inställningen `-Xmx`.  
- **Chunk‑storlek** – Välj rad‑/kolumnantal som balanserar sidstorlek och renderingshastighet.  
- **Versionuppdateringar** – Håll GroupDocs Viewer uppdaterad för att dra nytta av prestandaförbättringar; den senaste 25.2‑utgåvan förbättrar renderingshastigheten med upp till 30 % jämfört med 24.x.

## Vanliga problem & felsökning
| Symptom | Trolig orsak | Åtgärd |
|---------|--------------|-----|
| `OutOfMemoryError` | Renderar ett mycket stort blad med för många rader per sida | Reduce `countRowsPerPage` or increase JVM heap |
| Blank output files | Incorrect file path or missing write permissions | Verify `outputDirectory` exists and is writable |
| HTML resources not loading | Using `forEmbeddedResources` but serving files from a different base URL | Serve the entire output folder or switch to `forExternalResources` |

## Vanliga frågor

**Q: Can I generate a PDF instead of HTML?**  
A: Yes. Replace `HtmlViewOptions` with `PdfViewOptions` and keep the same `SpreadsheetOptions` configuration.

**Q: Is it possible to split based on cell content rather than fixed rows/columns?**  
A: Direct content‑based splitting isn’t built into GroupDocs Viewer, but you can preprocess the workbook with Apache POI to create separate sheets before rendering.

**Q: Does GroupDocs Viewer support older Excel formats (XLS)?**  
A: Absolutely. The viewer handles XLS, XLSX, CSV, and other spreadsheet formats.

**Q: How do I embed the generated HTML into a Spring MVC view?**  
A: Serve the output folder as a static resource and reference the generated `page_0.html`, `page_1.html`, etc., from your Thymeleaf or JSP templates.

**Q: What license do I need for commercial deployment?**  
A: A full production license from GroupDocs is required; trial licenses are for evaluation only.

## Resurser
- **Dokumentation**: [GroupDocs Viewer Java Documentation](https://docs.groupdocs.com/viewer/java/)
- **API Reference**: [GroupDocs API Reference](https://reference.groupdocs.com/viewer/java/)
- **Download**: [GroupDocs Viewer Java Releases](https://releases.groupdocs.com/viewer/java/)
- **Purchase**: [Buy GroupDocs License](https://purchase.groupdocs.com/buy)
- **Free Trial**: [GroupDocs Free Trial](https://releases.groupdocs.com/viewer/java/)
- **Temporary License**: [Get Temporary License](https://purchase.groupdocs.com/temporary-license/)
- **Support**: [GroupDocs Support Forum](https://forum.groupdocs.com/c/viewer/9)

---

**Senast uppdaterad:** 2026-06-15  
**Testad med:** GroupDocs Viewer 25.2 för Java  
**Författare:** GroupDocs  

## Relaterade handledningar

- [Rendera dolda rader och kolumner i Java‑kalkylblad med GroupDocs.Viewer](/viewer/java/advanced-rendering/render-hidden-rows-columns-java-groupdocs-viewer/)
- [Hoppa över rendering av tomma rader i Java med GroupDocs.Viewer: En prestandaguide](/viewer/java/advanced-rendering/skip-rendering-empty-rows-java-groupdocs-viewer/)
- [Omfattande guide: Konvertera Excel 2003 XML till HTML/JPG/PNG/PDF med GroupDocs.Viewer Java](/viewer/java/rendering-basics/groupdocs-viewer-java-excel-2003-xml-conversion/)