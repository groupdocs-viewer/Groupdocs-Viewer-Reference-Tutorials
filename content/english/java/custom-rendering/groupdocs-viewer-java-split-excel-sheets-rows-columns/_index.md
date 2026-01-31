---
title: "How to Split Excel Sheets by Rows & Columns (Java)"
description: "Learn how to split Excel sheets by rows and columns in Java using GroupDocs Viewer. This step-by-step guide covers setup, code, and best practices."
date: "2026-01-31"
weight: 1
url: "/java/custom-rendering/groupdocs-viewer-java-split-excel-sheets-rows-columns/"
keywords:
- split Excel sheets Java
- GroupDocs Viewer Java tutorial
- manageable data segments
type: docs
---

# How to Split Excel Sheets by Rows & Columns (Java)

Large Excel workbooks often contain more data than can be comfortably displayed on a single screen or printed page. **How to split Excel** sheets into smaller, readable sections makes it easier to share, embed, or print only the parts you need. In this guide we’ll show you **how to split worksheet** data by rows and columns using **GroupDocs Viewer** for Java, and we’ll also touch on generating Excel reports in Java and rendering Excel as HTML.

![Split Excel Sheets by Rows and Columns with GroupDocs.Viewer for Java](/viewer/custom-rendering/split-excel-sheets-by-rows-and-columns.png)

## Quick Answers
- **What library is used?** GroupDocs Viewer for Java.  
- **Can I split by both rows and columns?** Yes – you can define rows‑per‑page and columns‑per‑page together.  
- **Do I need a license?** A trial or temporary license works for development; a full license is required for production.  
- **What output formats are supported?** HTML (embedded resources) is shown; PDF can be generated with the same options.  
- **Is Maven required?** Maven is the recommended way to manage dependencies.

## What Is “How to Split Excel”?
Splitting an Excel sheet means dividing a single worksheet into multiple pages or files based on a fixed number of rows, columns, or both. This technique is handy when you need to create paginated reports, embed data in web pages, or generate printable sections without loading the entire workbook at once.

## Why Use GroupDocs Viewer for Java?
- **Fast rendering** – native support for XLSX, XLS, CSV, and more.  
- **Built‑in pagination** – no manual calculations required.  
- **HTML or PDF output** – perfect for web applications or offline reports.  
- **Cross‑platform** – works on any JVM‑compatible environment.

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

## How to Split Excel Sheets by Rows

### Overview
Splitting by rows lets you create a series of HTML pages, each containing a fixed number of rows (e.g., 15). This is ideal for dashboards that display a limited number of records per view.

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

### Overview
Sometimes a single page needs to show a matrix of rows **and** columns (e.g., 15 rows × 7 columns). This gives you full control over the layout of each HTML page.

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
- **Version updates** – Keep GroupDocs Viewer up‑to‑date to benefit from performance improvements.

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

**Last Updated:** 2026-01-31  
**Tested With:** GroupDocs Viewer 25.2 for Java  
**Author:** GroupDocs  

---