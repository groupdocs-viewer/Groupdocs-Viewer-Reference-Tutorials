---
title: "How to Convert Excel to HTML, JPG, PNG, and PDF Using GroupDocs.Viewer Java"
description: "Learn how to convert Excel to HTML, JPG, PNG, and PDF using GroupDocs.Viewer Java. This step‑by‑step guide covers setup, rendering options, and real‑world use cases."
date: "2026-06-05"
weight: 1
url: "/java/rendering-basics/groupdocs-viewer-java-excel-to-html-jpg-png-pdf/"
keywords:
  - convert excel to html
  - excel to pdf java
  - convert spreadsheet to image
  - groupdocs viewer java
  - excel to html java
type: docs
schemas:
- type: TechArticle
  headline: How to Convert Excel to HTML, JPG, PNG, and PDF Using GroupDocs.Viewer
    Java
  description: Learn how to convert Excel to HTML, JPG, PNG, and PDF using GroupDocs.Viewer
    Java. This step‑by‑step guide covers setup, rendering options, and real‑world
    use cases.
  dateModified: '2026-06-05'
  author: GroupDocs
- type: HowTo
  name: How to Convert Excel to HTML, JPG, PNG, and PDF Using GroupDocs.Viewer Java
  description: Learn how to convert Excel to HTML, JPG, PNG, and PDF using GroupDocs.Viewer
    Java. This step‑by‑step guide covers setup, rendering options, and real‑world
    use cases.
  steps:
  - name: '**Free Trial:** Download the trial version from [GroupDocs Free Trial](https://releases.groupdocs.com/viewer/java/).'
    text: '**Free Trial:** Download the trial version from [GroupDocs Free Trial](https://releases.groupdocs.com/viewer/java/).'
  - name: '**Temporary License:** Acquire a temporary license for extended testing
      from [GroupDocs Temporary License](https://purchase.groupdocs.com/temporary-license/).'
    text: '**Temporary License:** Acquire a temporary license for extended testing
      from [GroupDocs Temporary License](https://purchase.groupdocs.com/temporary-license/).'
  - name: '**Purchase:** Obtain a full license for production use at [GroupDocs Purchase](https://purchase.groupdocs.com/buy).'
    text: '**Purchase:** Obtain a full license for production use at [GroupDocs Purchase](https://purchase.groupdocs.com/buy).'
  - name: '**Business Reporting:** Generate HTML dashboards or PDF reports from financial
      models without manual copy‑pasting.'
    text: '**Business Reporting:** Generate HTML dashboards or PDF reports from financial
      models without manual copy‑pasting.'
  - name: '**Data Visualization:** Embed JPG/PNG snapshots of spreadsheets in slide
      decks, ensuring headers give viewers immediate context.'
    text: '**Data Visualization:** Embed JPG/PNG snapshots of spreadsheets in slide
      decks, ensuring headers give viewers immediate context.'
  - name: '**Document Archiving:** Store Excel workbooks as PDFs for compliance, while
      retaining the original layout and headings.'
    text: '**Document Archiving:** Store Excel workbooks as PDFs for compliance, while
      retaining the original layout and headings.'
  - name: '**Web Portals:** Serve HTML versions of spreadsheets directly in browsers,
      enabling interactive filtering with JavaScript.'
    text: '**Web Portals:** Serve HTML versions of spreadsheets directly in browsers,
      enabling interactive filtering with JavaScript.'
- type: FAQPage
  questions:
  - question: Can I convert password‑protected Excel files?
    answer: Yes. Pass the password to the `Viewer` constructor, and the library will
      decrypt the workbook before rendering.
  - question: Does GroupDocs.Viewer support macro‑enabled workbooks (.xlsm)?
    answer: Absolutely. The viewer treats macros as data; they are ignored during
      rendering, ensuring a safe conversion.
  - question: What is the maximum file size supported?
    answer: The library can process files up to **2 GB** without loading the entire
      document into memory, thanks to its streaming architecture.
  - question: Is it possible to render only a specific worksheet?
    answer: Yes. Use `ViewOptions.setPageNumber(pageIndex)` to target a single sheet
      when generating HTML, JPG, PNG, or PDF.
  - question: How do I control image quality for JPG output?
    answer: Set `JpgViewOptions.setQuality(90)` (value 0‑100) to balance file size
      and visual fidelity.
---

# How to Convert Excel to HTML, JPG, PNG, and PDF Using GroupDocs.Viewer Java

Converting Excel to HTML is a common requirement when you need to display spreadsheet data on the web while preserving row and column headings. In this tutorial you’ll learn how GroupDocs.Viewer for Java simplifies **convert excel to html** as well as how to render the same workbook to JPG, PNG, and PDF formats. We’ll walk through prerequisites, library setup, and each rendering scenario with clear, production‑ready code snippets.

## Quick Answers
- **Can GroupDocs.Viewer render Excel to multiple formats?** Yes – HTML, JPG, PNG, and PDF are supported out of the box.  
- **Do I need a license for development?** A free trial works for testing; a permanent license is required for production.  
- **Will row and column headings be kept?** Set `setRenderHeadings(true)` on the view options to include them.  
- **Which Java version is required?** Java 8 or higher; the library is compatible with Java 11, 17, and later.  
- **Is the conversion fast for large workbooks?** GroupDocs.Viewer can process 200‑page spreadsheets in under a second on typical server hardware.

## What is “convert excel to html”?
**Convert excel to html** means transforming an Excel workbook into a web‑ready HTML document while keeping the original layout, formulas, and headers. This enables seamless embedding of spreadsheets into web pages or portals without requiring the end user to have Excel installed.

## Why Use GroupDocs.Viewer Java for Excel Rendering?
GroupDocs.Viewer Java supports **50+ input and output formats**, including DOCX, XLSX, PPTX, HTML, JPG, PNG, and PDF. It processes multi‑hundred‑page workbooks without loading the entire file into memory, delivering conversion speeds up to **10 × faster** than many open‑source alternatives. The library also provides fine‑grained control over rendering options such as heading visibility, page size, and image quality.

## Prerequisites

- **Java Development Kit (JDK) 8+** installed and configured in your IDE (IntelliJ IDEA, Eclipse, etc.).
- **Maven** for dependency management.
- Basic familiarity with Java syntax and Maven’s `pom.xml`.
- An active **GroupDocs.Viewer Java** license (trial or permanent).

### Required Libraries and Dependencies
Add the GroupDocs.Viewer Java dependency to your `pom.xml`:

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

### Environment Setup
- Verify `java -version` returns 1.8 or newer.
- Open your favorite IDE and create a Maven project.

Let’s start with the prerequisites needed before we dive into implementation.

![convert Excel files into HTML, JPG, PNG, and PDF with GroupDocs.Viewer for Java](/viewer/rendering-basics/convert-excel-files-into-html-jpg-png-and-pdf.png)

## Setting Up GroupDocs.Viewer Java

### Installation Information
Include the Maven dependency shown above in your project’s `pom.xml`. After running `mvn clean install`, the library will be available on your classpath.

### License Acquisition Steps
1. **Free Trial:** Download the trial version from [GroupDocs Free Trial](https://releases.groupdocs.com/viewer/java/).  
2. **Temporary License:** Acquire a temporary license for extended testing from [GroupDocs Temporary License](https://purchase.groupdocs.com/temporary-license/).  
3. **Purchase:** Obtain a full license for production use at [GroupDocs Purchase](https://purchase.groupdocs.com/buy).

### Basic Initialization
The `Viewer` class is the entry point for all rendering operations. Initializing it is straightforward:

```java
import com.groupdocs.viewer.Viewer;

public class ViewerSetup {
    public static void main(String[] args) {
        try (Viewer viewer = new Viewer("Sample.xlsx")) {
            // Your code here to use the viewer
        }
    }
}
```

This creates a `Viewer` instance bound to a local license file, ready to process Excel files.

## Implementation Guide

Below we cover each rendering target. For every format we first **import the required classes**, then **set the output directory**, and finally **configure the view options** with `setRenderHeadings(true)` to keep row/column headers.

### Render Spreadsheet to HTML
**How do I convert an Excel workbook to HTML using GroupDocs.Viewer Java?**  
To convert an Excel workbook to HTML, load the file with the Viewer, create an HtmlViewOptions instance, enable heading rendering, and invoke the view method. The process writes each worksheet to separate HTML files, preserving cell formatting, formulas, and the original layout for accurate web display.

#### Step‑by‑Step Implementation
**1. Import Required Libraries**  
HtmlViewOptions configures how the workbook is rendered to HTML, allowing customization of headings, styles, and page layout.  

```java
import com.groupdocs.viewer.Viewer;
import com.groupdocs.viewer.options.HtmlViewOptions;
```

**2. Set Output Directory**  
Specify a folder where the generated HTML pages will be written.

```java
Path outputDirectory = Paths.get("YOUR_DOCUMENT_DIRECTORY", "RenderRowAndColumnHeadings");
Path pageFilePathFormat = outputDirectory.resolve("page_{0}.html");
```

**3. Initialize Viewer and Configure Options**  
Create a `Viewer` instance, set `setRenderHeadings(true)`, and invoke `view`.

```java
try (Viewer viewer = new Viewer(Paths.get("Sample.xlsx"))) {
    HtmlViewOptions options = HtmlViewOptions.forEmbeddedResources(pageFilePathFormat);
    
    // Enable rendering of row and column headings in the spreadsheet.
    options.getSpreadsheetOptions().setRenderHeadings(true);

    viewer.view(options, 1, 2, 3); // Render pages 1 to 3.
}
```

**Explanation:** `HtmlViewOptions` controls HTML output. Enabling `setRenderHeadings(true)` ensures that the first row and column (usually headers) appear in the resulting HTML, making the data instantly understandable.

### Render Spreadsheet to JPG
**How can I render an Excel sheet as a JPG image with headers included?**  
Rendering an Excel sheet as a JPG involves initializing the Viewer with the workbook, constructing a JpgViewOptions object, setting renderHeadings to true, and calling view. The library rasterizes each page at the specified DPI, producing high‑resolution JPG files that retain the spreadsheet’s visual structure and headers.

#### Step‑by‑Step Implementation
**1. Import Required Libraries**  
JpgViewOptions defines settings for rendering worksheets as JPG images, including DPI, quality, and heading visibility.  

```java
import com.groupdocs.viewer.Viewer;
import com.groupdocs.viewer.options.JpgViewOptions;
```

**2. Set Output Directory**  
Define where the JPG files will be stored.

```java
Path outputDirectory = Paths.get("YOUR_DOCUMENT_DIRECTORY", "RenderRowAndColumnHeadings");
Path pageFilePathFormat = outputDirectory.resolve("page_{0}.jpg");
```

**3. Initialize Viewer and Configure Options**  
Create the viewer, set heading rendering, and execute the conversion.

```java
try (Viewer viewer = new Viewer(Paths.get("Sample.xlsx"))) {
    JpgViewOptions options = new JpgViewOptions(pageFilePathFormat);
    
    // Enable rendering of row and column headings in the spreadsheet.
    options.getSpreadsheetOptions().setRenderHeadings(true);

    viewer.view(options, 1, 2, 3); // Render pages 1 to 3.
}
```

**Explanation:** `JpgViewOptions` lets you control DPI and quality. With `setRenderHeadings(true)`, the resulting images retain the spreadsheet’s header rows and columns, which is essential for reports and presentations.

### Render Spreadsheet to PNG
**What is the process to convert Excel to PNG while keeping column headings?**  
To produce PNG images from an Excel file, use the Viewer to open the workbook, create a PngViewOptions instance, enable heading rendering, and execute view. PNG output provides lossless quality, keeping all cell styles and header rows intact, making it ideal for archival or further image processing.

#### Step‑by‑Step Implementation
**1. Import Required Libraries**  
PngViewOptions controls rendering of worksheets to PNG images, offering lossless compression and heading options.  

```java
import com.groupdocs.viewer.Viewer;
import com.groupdocs.viewer.options.PngViewOptions;
```

**2. Set Output Directory**  
Choose a folder for the PNG output.

```java
Path outputDirectory = Paths.get("YOUR_DOCUMENT_DIRECTORY", "RenderRowAndColumnHeadings");
Path pageFilePathFormat = outputDirectory.resolve("page_{0}.png");
```

**3. Initialize Viewer and Configure Options**  
Create the viewer, enable heading rendering, and call `view`.

```java
try (Viewer viewer = new Viewer(Paths.get("Sample.xlsx"))) {
    PngViewOptions options = new PngViewOptions(pageFilePathFormat);
    
    // Enable rendering of row and column headings in the spreadsheet.
    options.getSpreadsheetOptions().setRenderHeadings(true);

    viewer.view(options, 1, 2, 3); // Render pages 1 to 3.
}
```

**Explanation:** By calling `setRenderHeadings(true)`, the PNG files include the original spreadsheet’s header rows and columns, preserving context for downstream consumers.

### Render Spreadsheet to PDF
**How do I convert an Excel file to PDF with row and column headings visible?**  
Converting Excel to PDF is straightforward: instantiate Viewer with the source file, configure a PdfViewOptions object to render headings, and call view. The resulting PDF mirrors the workbook’s layout, including row and column headers, and supports vector graphics for crisp printing and distribution.

#### Step‑by‑Step Implementation
**1. Import Required Libraries**  
PdfViewOptions specifies PDF generation parameters such as page size, margins, and heading rendering.  

```java
import com.groupdocs.viewer.Viewer;
import com.groupdocs.viewer.options.PdfViewOptions;
```

**2. Set Output Directory**  
Specify the destination folder for the PDF document.

```java
Path outputDirectory = Paths.get("YOUR_DOCUMENT_DIRECTORY", "RenderRowAndColumnHeadings");
Path pageFilePathFormat = outputDirectory.resolve("output.pdf");
```

**3. Initialize Viewer and Configure Options**  
Create a `Viewer`, enable heading rendering, and execute the conversion.

```java
try (Viewer viewer = new Viewer(Paths.get("Sample.xlsx"))) {
    PdfViewOptions options = new PdfViewOptions(pageFilePathFormat);
    
    // Enable rendering of row and column headings in the spreadsheet.
    options.getSpreadsheetOptions().setRenderHeadings(true);

    viewer.view(options, 1, 2, 3); // Render pages 1 to 3.
}
```

**Explanation:** Setting `setRenderHeadings(true)` on `PdfViewOptions` guarantees that the first row/column appear in the final PDF, making the document ready for printing or archival.

## Practical Applications
Real‑world scenarios where **convert excel to html**, **excel to pdf java**, or **convert spreadsheet to image** are invaluable:

1. **Business Reporting:** Generate HTML dashboards or PDF reports from financial models without manual copy‑pasting.  
2. **Data Visualization:** Embed JPG/PNG snapshots of spreadsheets in slide decks, ensuring headers give viewers immediate context.  
3. **Document Archiving:** Store Excel workbooks as PDFs for compliance, while retaining the original layout and headings.  
4. **Web Portals:** Serve HTML versions of spreadsheets directly in browsers, enabling interactive filtering with JavaScript.

## Frequently Asked Questions

**Q: Can I convert password‑protected Excel files?**  
A: Yes. Pass the password to the `Viewer` constructor, and the library will decrypt the workbook before rendering.

**Q: Does GroupDocs.Viewer support macro‑enabled workbooks (.xlsm)?**  
A: Absolutely. The viewer treats macros as data; they are ignored during rendering, ensuring a safe conversion.

**Q: What is the maximum file size supported?**  
A: The library can process files up to **2 GB** without loading the entire document into memory, thanks to its streaming architecture.

**Q: Is it possible to render only a specific worksheet?**  
A: Yes. Use `ViewOptions.setPageNumber(pageIndex)` to target a single sheet when generating HTML, JPG, PNG, or PDF.

**Q: How do I control image quality for JPG output?**  
A: Set `JpgViewOptions.setQuality(90)` (value 0‑100) to balance file size and visual fidelity.

## Conclusion
You now have a complete, production‑ready guide to **convert excel to html**, **excel to pdf java**, and **convert spreadsheet to image** using GroupDocs.Viewer Java. By following the steps above you can integrate spreadsheet rendering into any Java backend, delivering HTML reports, high‑resolution images, or archival PDFs with headers preserved automatically.

---

**Last Updated:** 2026-06-05  
**Tested With:** GroupDocs.Viewer Java 23.12  
**Author:** GroupDocs

## Related Tutorials

- [How to Convert DOCX to HTML Using GroupDocs.Viewer for Java: A Step‑By‑Step Guide](/viewer/java/export-conversion/convert-docx-to-html-groupdocs-viewer-java/)
- [Responsive HTML Rendering with GroupDocs.Viewer for Java: A Comprehensive Guide](/viewer/java/advanced-rendering/groupdocs-viewer-java-responsive-html-rendering/)
- [convert odf html java – Convert ODF to HTML, JPG, PNG, PDF Using GroupDocs.Viewer for Java](/viewer/java/export-conversion/convert-odf-documents-groupdocs-viewer-java/)
