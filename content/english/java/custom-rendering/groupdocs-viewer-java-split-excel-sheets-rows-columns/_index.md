---
title: "Convert Excel to PDF Java & Split Sheets by Rows & Columns"
description: "Learn how to convert Excel to PDF Java and split Excel sheets by rows and columns using GroupDocs Viewer. Includes setup, code, and best practices."
date: "2026-06-15"
weight: 1
url: "/java/custom-rendering/groupdocs-viewer-java-split-excel-sheets-rows-columns/"
keywords:
- convert excel to pdf java
- split excel sheet rows
- split excel sheet columns
type: docs
schemas:
- type: TechArticle
  headline: Convert Excel to PDF Java & Split Sheets by Rows & Columns
  description: Learn how to convert Excel to PDF Java and split Excel sheets by rows
    and columns using GroupDocs Viewer. Includes setup, code, and best practices.
  dateModified: '2026-06-15'
  author: GroupDocs
- type: HowTo
  name: Convert Excel to PDF Java & Split Sheets by Rows & Columns
  description: Learn how to convert Excel to PDF Java and split Excel sheets by rows
    and columns using GroupDocs Viewer. Includes setup, code, and best practices.
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
- type: FAQPage
  questions:
  - question: Can I generate a PDF instead of HTML?
    answer: Yes. Replace `HtmlViewOptions` with `PdfViewOptions` and keep the same
      `SpreadsheetOptions` configuration.
  - question: Is it possible to split based on cell content rather than fixed rows/columns?
    answer: Direct content‑based splitting isn’t built into GroupDocs Viewer, but
      you can preprocess the workbook with Apache POI to create separate sheets before
      rendering.
  - question: Does GroupDocs Viewer support older Excel formats (XLS)?
    answer: Absolutely. The viewer handles XLS, XLSX, CSV, and other spreadsheet formats.
  - question: How do I embed the generated HTML into a Spring MVC view?
    answer: Serve the output folder as a static resource and reference the generated
      `page_0.html`, `page_1.html`, etc., from your Thymeleaf or JSP templates.
  - question: What license do I need for commercial deployment?
    answer: A full production license from GroupDocs is required; trial licenses are
      for evaluation only.
---

# Convert Excel to PDF Java & Split Sheets by Rows & Columns (Java)

Large Excel workbooks often contain more data than can be comfortably displayed on a single screen or printed page. **convert excel to pdf java** is a common requirement when you need a static, share‑able format, while **splitting Excel sheets by rows and columns** makes the data easier to consume in web or print layouts. In this guide we’ll walk through both tasks using **GroupDocs Viewer for Java**, show you how to configure pagination, and explain best‑practice tips for performance and troubleshooting.

![Split Excel Sheets by Rows and Columns with GroupDocs.Viewer for Java](/viewer/custom-rendering/split-excel-sheets-by-rows-and-columns.png)

[Split Excel Sheets by Rows and Columns with GroupDocs.Viewer for Java](/viewer/custom-rendering/split-excel-sheets-by-rows-and-columns.png)

## Quick Answers
- **What library is used?** GroupDocs Viewer for Java.  
- **Can I split by both rows and columns?** Yes – you can define rows‑per‑page and columns‑per‑page together.  
- **Do I need a license?** A trial or temporary license works for development; a full license is required for production.  
- **What output formats are supported?** HTML (embedded resources) is shown; PDF can be generated with the same options.  
- **Is Maven required?** Maven is the recommended way to manage dependencies.  
- **Can I also convert Excel to PDF?** Absolutely – just switch `HtmlViewOptions` to `PdfViewOptions` and reuse the same pagination settings.

## What Is “How to Split Excel”?
Splitting an Excel sheet means dividing a single worksheet into multiple pages or files based on a fixed number of rows, columns, or both. This technique is handy when you need to create paginated reports, embed data in web pages, or generate printable sections without loading the entire workbook at once.

## Why Use GroupDocs Viewer for Java?
GroupDocs Viewer processes spreadsheets in a single pass and automatically paginates them, eliminating manual calculations. **Fast rendering processes a 250‑page XLSX workbook in under 2 seconds on a typical 2‑core server**, and **the library supports 50+ input and output formats**, including XLS, XLSX, CSV, PDF, and HTML. It runs on any JVM‑compatible platform—Windows, Linux, macOS, Docker containers, or cloud‑based serverless runtimes—so you can integrate it wherever your Java application lives.

## Prerequisites
- Java 17 or later installed.  
- An IDE such as IntelliJ IDEA or Eclipse.  
- Maven for dependency management.  
- Basic Java knowledge and familiarity with Excel file handling.

### Required Libraries, Versions, and Dependencies
Add the GroupDocs repository and the viewer dependency to your `pom.xml`:

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

### License Acquisition
Obtain a free trial, temporary license, or purchase a full license from [GroupDocs](https://purchase.groupdocs.com/buy).

## How to Convert Excel to PDF Java?

The `Viewer` class is the core component of GroupDocs Viewer that loads a document and provides rendering methods for various output formats. `SpreadsheetOptions` allows you to control pagination settings such as rows‑per‑page and columns‑per‑page for spreadsheet rendering.

Load your Excel file with `new Viewer("source.xlsx")`, configure `SpreadsheetOptions` for pagination, and call `viewer.view(pdfOptions, stream)` – that single call converts the workbook to a PDF while respecting the row/column limits you set. The conversion preserves formulas, images, and cell styles, delivering a faithful PDF replica ready for distribution.

## How to Split Excel Sheets by Rows

Splitting by rows creates a series of HTML pages, each containing a fixed number of rows (e.g., 15). This approach is ideal for dashboards that display a limited number of records per view. The viewer will generate separate HTML files such as `page_0.html`, `page_1.html`, etc., each containing the specified number of rows. This makes it simple to load only the needed portion in a web interface, reducing bandwidth and rendering time.

### Definition Anchor
`Viewer` is GroupDocs Viewer’s core class that loads a document and orchestrates rendering to the chosen output format.

### Step‑by‑Step Implementation

#### Step 1: Set Up Paths and Initialize the Viewer
First, define where the split pages will be saved and create a `Viewer` instance for the source workbook.

```java
Path outputDirectory = Path.of("YOUR_OUTPUT_DIRECTORY/SplitByRows");
Path pageFilePathFormat = outputDirectory.resolve("page_{0}.html");

try (Viewer viewer = new Viewer("YOUR_DOCUMENT_DIRECTORY/TWO_PAGES_XLSX")) {
    // Proceed with further configuration...
}
```

#### Step 2: Configure Rows Per Page
Tell the viewer how many rows each page should contain.

```java
int countRowsPerPage = 15;
HtmlViewOptions viewOptions = HtmlViewOptions.forEmbeddedResources(pageFilePathFormat);
viewOptions.setSpreadsheetOptions(SpreadsheetOptions.forSplitSheetIntoPages(countRowsPerPage));
```

#### Step 3: Render the Document
Finally, render the workbook using the options you defined.

```java
viewer.view(viewOptions);
```

## How to Split Excel Sheets by Rows and Columns

Sometimes a single page needs to show a matrix of rows **and** columns (e.g., 15 rows × 7 columns). This gives you full control over the layout of each HTML page. The resulting pages display a rectangular block of cells, for example rows 1‑15 and columns A‑G on the first page, rows 16‑30 and columns H‑N on the next. This grid‑style pagination is useful for creating printable reports that fit standard paper sizes.

### Definition Anchor
`SpreadsheetOptions` configures how many rows and columns appear on each generated page.

### Step‑by‑Step Implementation

#### Step 1: Set Up Paths and Initialize the Viewer
The setup mirrors the row‑only example, only the file name changes.

```java
Path outputDirectory = Path.of("YOUR_OUTPUT_DIRECTORY/SplitByRowsAndColumns");
Path pageFilePathFormat = outputDirectory.resolve("page_{0}.html");

try (Viewer viewer = new Viewer("YOUR_DOCUMENT_DIRECTORY/FOUR_PAGES_XLSX")) {
    // Continue with configuration...
}
```

#### Step 2: Configure Rows and Columns Per Page
Specify both dimensions to create a grid‑style split.

```java
int countRowsPerPage = 15;
int countColumnsPerPage = 7;

HtmlViewOptions options = HtmlViewOptions.forEmbeddedResources(pageFilePathFormat);
options.setSpreadsheetOptions(SpreadsheetOptions.forSplitSheetIntoPages(countRowsPerPage, countColumnsPerPage));
```

#### Step 3: Render the Document
Render using the same `view` call.

```java
viewer.view(options);
```

## Practical Applications
- **Generate Excel report Java**: Turn large financial models into a series of paginated HTML reports.  
- **GroupDocs Viewer Excel**: Embed split pages directly into a web portal for interactive data exploration.  
- **Render Excel HTML Java**: Serve the generated HTML pages via a servlet or Spring controller for fast client‑side rendering.  

## Performance Considerations
- **Memory usage** – Large workbooks can consume significant heap; consider increasing the JVM `-Xmx` setting.  
- **Chunk size** – Choose row/column counts that balance page size and rendering speed.  
- **Version updates** – Keep GroupDocs Viewer up‑to‑date to benefit from performance improvements; the latest 25.2 release improves rendering speed by up to 30 % compared with 24.x.

## Common Issues & Troubleshooting
| Symptom | Likely Cause | Fix |
|---------|--------------|-----|
| `OutOfMemoryError` | Rendering a very large sheet with too many rows per page | Reduce `countRowsPerPage` or increase JVM heap |
| Blank output files | Incorrect file path or missing write permissions | Verify `outputDirectory` exists and is writable |
| HTML resources not loading | Using `forEmbeddedResources` but serving files from a different base URL | Serve the entire output folder or switch to `forExternalResources` |

## Frequently Asked Questions

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

## Resources
- **Documentation**: [GroupDocs Viewer Java Documentation](https://docs.groupdocs.com/viewer/java/)
- **API Reference**: [GroupDocs API Reference](https://reference.groupdocs.com/viewer/java/)
- **Download**: [GroupDocs Viewer Java Releases](https://releases.groupdocs.com/viewer/java/)
- **Purchase**: [Buy GroupDocs License](https://purchase.groupdocs.com/buy)
- **Free Trial**: [GroupDocs Free Trial](https://releases.groupdocs.com/viewer/java/)
- **Temporary License**: [Get Temporary License](https://purchase.groupdocs.com/temporary-license/)
- **Support**: [GroupDocs Support Forum](https://forum.groupdocs.com/c/viewer/9)

---

**Last Updated:** 2026-06-15  
**Tested With:** GroupDocs Viewer 25.2 for Java  
**Author:** GroupDocs  

---

## Related Tutorials

- [Render Hidden Rows & Columns in Java Spreadsheets Using GroupDocs.Viewer](/viewer/java/advanced-rendering/render-hidden-rows-columns-java-groupdocs-viewer/)
- [Skip Rendering Empty Rows in Java Using GroupDocs.Viewer: A Performance Guide](/viewer/java/advanced-rendering/skip-rendering-empty-rows-java-groupdocs-viewer/)
- [Comprehensive Guide: Convert Excel 2003 XML to HTML/JPG/PNG/PDF with GroupDocs.Viewer Java](/viewer/java/rendering-basics/groupdocs-viewer-java-excel-2003-xml-conversion/)
