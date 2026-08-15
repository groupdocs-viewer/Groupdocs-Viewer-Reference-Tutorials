---
date: '2026-07-19'
description: Learn how to convert pst to html and other formats like JPG, PNG, PDF
  using GroupDocs.Viewer for Java. This guide covers all steps and configurations
  needed.
images:
- /java/export-conversion/convert-pst-ost-groupdocs-viewer-java/og-image.png
keywords:
- convert pst to html
- convert pst to pdf
- java convert ost
- convert pst to png
- convert pst to jpg
lastmod: '2026-07-19'
og_description: Convert PST to HTML quickly using GroupDocs.Viewer for Java. Learn
  step‑by‑step how to also export to JPG, PNG, and PDF in a production‑ready guide.
og_image_alt: 'Developer guide: Convert PST to HTML, JPG, PNG, PDF using GroupDocs
  Viewer for Java'
og_title: Convert PST to HTML with GroupDocs.Viewer for Java – Fast Email Export
schemas:
- author: GroupDocs
  dateModified: '2026-07-19'
  description: Learn how to convert pst to html and other formats like JPG, PNG, PDF
    using GroupDocs.Viewer for Java. This guide covers all steps and configurations
    needed.
  headline: Convert PST to HTML, JPG, PNG, PDF Using GroupDocs.Viewer for Java
  type: TechArticle
- description: Learn how to convert pst to html and other formats like JPG, PNG, PDF
    using GroupDocs.Viewer for Java. This guide covers all steps and configurations
    needed.
  name: Convert PST to HTML, JPG, PNG, PDF Using GroupDocs.Viewer for Java
  steps:
  - name: Set Up Output Directory
    text: Define a folder where the HTML pages will be written. GroupDocs creates
      a sub‑folder for each email to keep assets organized.
  - name: Configure Load Options
    text: '`LoadOptions` lets you specify password handling, resource‑loading timeouts,
      and selective page rendering. Setting a timeout of 30 seconds works well for
      most server environments.'
  - name: Define HTML View Options
    text: '`HtmlViewOptions` specifies the output folder, resource handling, and optional
      CSS settings for HTML conversion.'
  - name: Initialize Viewer and Render HTML
    text: Create a `Viewer` object, pass the PST file path, and call `view` with the
      `HtmlViewOptions`. The API automatically iterates through all messages inside
      the PST and generates a tidy HTML hierarchy.
  - name: Set Up Output Directory
    text: Create a dedicated folder for JPG snapshots; each email will become one
      or more image files depending on its length.
  - name: Configure Load Options
    text: The same `LoadOptions` used for HTML can be reused here, ensuring consistent
      password handling across formats.
  - name: Define JPG View Options
    text: '`JpgViewOptions` controls image resolution, quality, and output folder
      for JPEG conversion.'
  - name: Initialize Viewer and Render JPG
    text: Use `viewer.view(jpgOptions)` to generate high‑quality JPEG files ready
      for web preview.
  - name: Set Up Output Directory
    text: PNG output is useful when you need lossless quality for archiving or OCR
      processing.
  - name: Configure Load Options
    text: No additional settings are required beyond the password and timeout configuration.
  type: HowTo
- questions:
  - answer: Use `PdfViewOptions` as shown in the PDF rendering section; the rest of
      the code remains identical.
    question: How do I **convert pst to pdf** with the same code base?
  - answer: Yes, provide the password via `LoadOptions.setPassword("yourPassword")`
      before rendering.
    question: Can GroupDocs.Viewer handle encrypted PST files?
  - answer: PNG preserves lossless quality, ideal for screenshots, while JPG offers
      smaller file sizes for email previews.
    question: What is the difference between **java convert pst** to PNG vs JPG?
  - answer: Wrap the rendering logic in a loop that iterates over a directory of PST
      files; reuse the same `Viewer` configuration for each file.
    question: Is there a way to **how to convert pst** files in bulk?
  - answer: Yes, GroupDocs.Viewer streams data and can process files up to 2 GB without
      loading the entire archive into memory.
    question: Does the API support converting PST files larger than 1 GB?
  type: FAQPage
tags:
- convert pst
- GroupDocs.Viewer
- Java document processing
- email conversion
title: Convert PST to HTML, JPG, PNG, PDF Using GroupDocs.Viewer for Java
type: docs
url: /java/export-conversion/convert-pst-ost-groupdocs-viewer-java/
weight: 1
---

# Convert PST to HTML, JPG, PNG, PDF Using GroupDocs.Viewer for Java

Are you looking to **convert pst to html** or other formats like JPG, PNG, or PDF? With the powerful GroupDocs.Viewer for Java library, this task is straightforward and efficient. In this tutorial you’ll learn how to render Outlook PST/OST files into web‑friendly HTML, image files, or a single PDF, making your email archives easy to share and archive.

![Convert PST/OST to HTML, JPG, PNG, PDF with GroupDocs.Viewer for Java](/viewer/export-conversion/convert-pst-ost-to-html-jpg-png-pdf.png)

[Convert PST/OST to HTML, JPG, PNG, PDF with GroupDocs.Viewer for Java](/viewer/export-conversion/convert-pst-ost-to-html-jpg-png-pdf.png)

**What You’ll Learn**
- How to set up GroupDocs.Viewer for Java in a Maven project.  
- Step‑by‑step instructions to **java convert pst** files to HTML, JPG, PNG, and PDF.  
- Configuration tips for optimal performance and common pitfalls.

## Quick Answers
- **What library handles PST conversion?** GroupDocs.Viewer for Java.  
- **Can I convert PST to PDF directly?** Yes, using `PdfViewOptions`.  
- **Is a license required for production?** A valid GroupDocs license is needed.  
- **Which Java version is supported?** JDK 8 or higher.  
- **Do I need to extract attachments manually?** No, the viewer renders them automatically.

## What is GroupDocs.Viewer for Java?
GroupDocs.Viewer for Java is a server‑side API that loads over 100 document and email formats and renders them into HTML, image, or PDF output without external software. It processes PST files up to 2 GB while keeping memory usage under 200 MB.

## How to convert pst to html using GroupDocs.Viewer for Java?

Load the PST file with `new Viewer("source.pst")`, configure `HtmlViewOptions` to point to an output folder, and call `viewer.view(htmlOptions)`. The API extracts each email, preserves formatting, attachments, and metadata, and writes a separate HTML page per message—all in a single method call.

### Why choose GroupDocs.Viewer?
- **High‑fidelity rendering** – 99.9 % of email content (including rich‑text bodies, tables, and embedded images) is reproduced accurately.  
- **Multiple output formats** – One API call can generate HTML, JPG, PNG, or PDF, covering 50+ export options.  
- **Zero external dependencies** – No need for Outlook, Exchange Server, or third‑party converters; everything runs inside your Java runtime.

## Prerequisites

- **GroupDocs.Viewer for Java** – version 25.2 or later.  
- **Java Development Kit (JDK)** – 8 or newer.  
- Maven for dependency management.  
- Basic Java knowledge and familiarity with Maven.

## Setting Up GroupDocs.Viewer for Java

`Viewer` is the core class in GroupDocs.Viewer for Java that loads a document and renders it into the chosen format. Add the GroupDocs repository and dependency to your `pom.xml`:

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
- **Free trial** – explore all features without cost.  
- **Temporary license** – extend evaluation time if needed.  
- **Full license** – required for production deployments.

### Basic Initialization

`Viewer` instances are lightweight; you can reuse a single instance for many files to minimise object‑creation overhead.

```java
import com.groupdocs.viewer.Viewer;
import com.groupdocs.viewer.options.HtmlViewOptions;

public class PSTToHTML {
    public static void main(String[] args) {
        // Initialize Viewer with a sample PST file path
        try (Viewer viewer = new Viewer("YOUR_DOCUMENT_DIRECTORY/SAMPLE_PST")) {
            HtmlViewOptions options = HtmlViewOptions.forEmbeddedResources("output_directory/PST_result.html");
            viewer.view(options);
        }
    }
}
```

## Implementation Guide

The following sections walk you through rendering PST/OST files into each supported format.

### Rendering PST/OST Documents to HTML

#### Step 1: Set Up Output Directory

Define a folder where the HTML pages will be written. GroupDocs creates a sub‑folder for each email to keep assets organized.

```java
Path outputDirectory = Paths.get("YOUR_OUTPUT_DIRECTORY");
Path pageFilePathFormat = outputDirectory.resolve("PST_result.html");
```

#### Step 2: Configure Load Options

`LoadOptions` lets you specify password handling, resource‑loading timeouts, and selective page rendering. Setting a timeout of 30 seconds works well for most server environments.

```java
LoadOptions loadOptions = new LoadOptions();
loadOptions.setResourceLoadingTimeout(100);
```

#### Step 3: Define HTML View Options

`HtmlViewOptions` specifies the output folder, resource handling, and optional CSS settings for HTML conversion.

```java
try (Viewer viewer = new Viewer("YOUR_DOCUMENT_DIRECTORY/SAMPLE_PST", loadOptions)) {
    HtmlViewOptions options = HtmlViewOptions.forEmbeddedResources(pageFilePathFormat);
    viewer.view(options);
}
```

#### Step 4: Initialize Viewer and Render HTML

Create a `Viewer` object, pass the PST file path, and call `view` with the `HtmlViewOptions`. The API automatically iterates through all messages inside the PST and generates a tidy HTML hierarchy.

```java
Path outputDirectory = Paths.get("YOUR_OUTPUT_DIRECTORY");
Path pageFilePathFormat = outputDirectory.resolve("PST_result_{0}.jpg");
```

### Rendering PST/OST Documents to JPG

#### Step 1: Set Up Output Directory

Create a dedicated folder for JPG snapshots; each email will become one or more image files depending on its length.

```java
LoadOptions loadOptions = new LoadOptions();
loadOptions.setResourceLoadingTimeout(100);
```

#### Step 2: Configure Load Options

The same `LoadOptions` used for HTML can be reused here, ensuring consistent password handling across formats.

```java
try (Viewer viewer = new Viewer("YOUR_DOCUMENT_DIRECTORY/SAMPLE_PST", loadOptions)) {
    JpgViewOptions options = new JpgViewOptions(pageFilePathFormat);
    viewer.view(options);
}
```

#### Step 3: Define JPG View Options

`JpgViewOptions` controls image resolution, quality, and output folder for JPEG conversion.

```java
Path outputDirectory = Paths.get("YOUR_OUTPUT_DIRECTORY");
Path pageFilePathFormat = outputDirectory.resolve("PST_result_{0}.png");
```

#### Step 4: Initialize Viewer and Render JPG

Use `viewer.view(jpgOptions)` to generate high‑quality JPEG files ready for web preview.

```java
LoadOptions loadOptions = new LoadOptions();
loadOptions.setResourceLoadingTimeout(100);
```

### Rendering PST/OST Documents to PNG

#### Step 1: Set Up Output Directory

PNG output is useful when you need lossless quality for archiving or OCR processing.

```java
try (Viewer viewer = new Viewer("YOUR_DOCUMENT_DIRECTORY/SAMPLE_PST", loadOptions)) {
    PngViewOptions options = new PngViewOptions(pageFilePathFormat);
    viewer.view(options);
}
```

#### Step 2: Configure Load Options

No additional settings are required beyond the password and timeout configuration.

```java
Path outputDirectory = Paths.get("YOUR_OUTPUT_DIRECTORY");
Path pageFilePathFormat = outputDirectory.resolve("PST_result.pdf");
```

#### Step 3: Define PNG View Options

`PngViewOptions` allows you to set a transparent background and output folder for lossless PNG images.

```java
LoadOptions loadOptions = new LoadOptions();
loadOptions.setResourceLoadingTimeout(100);
```

#### Step 4: Initialize Viewer and Render PNG

Instantiate `viewer.view(pngOptions)` to produce PNG snapshots of each email.

```java
try (Viewer viewer = new Viewer("YOUR_DOCUMENT_DIRECTORY/SAMPLE_PST", loadOptions)) {
    PdfViewOptions options = new PdfViewOptions(pageFilePathFormat);
    viewer.view(options);
}
```

### Rendering PST/OST Documents to PDF

#### Step 1: Set Up Output Directory

A single PDF file per PST simplifies legal‑review workflows and reduces storage overhead.

CODE_BLOCK_PLACEHOLDER_14_END

#### Step 2: Configure Load Options

When converting to PDF, you may want to enable `setEmbedFonts(true)` to guarantee visual fidelity on any machine.

CODE_BLOCK_PLACEHOLDER_15_END

#### Step 3: Define PDF View Options

`PdfViewOptions` lets you choose compression level, embed fonts, and set the output file name for PDF conversion.

CODE_BLOCK_PLACEHOLDER_16_END

#### Step 4: Initialize Viewer and Render PDF

Create `PdfViewOptions`, optionally choose a compression level, and call `viewer.view(pdfOptions)`. The API merges all emails into one searchable PDF document.

CODE_BLOCK_PLACEHOLDER_17_END

## Practical Applications

- **Email Archiving:** Turn large PST archives into searchable HTML or PDF for compliance.  
- **Document Management Systems:** Store converted files in systems that only accept PDF, PNG, or JPG.  
- **Collaboration Platforms:** Share converted emails as images in Slack or Teams.  
- **Legal Review:** Provide courts with PDF versions of email evidence.  
- **Backup Strategies:** Keep lightweight PNG or JPG snapshots of critical messages.

## Performance Considerations

- **Resource Management:** Reuse `Viewer` instances when processing multiple files to reduce overhead.  
- **Memory Tuning:** Adjust `loadOptions.setResourceLoadingTimeout` based on server capacity.  
- **Asynchronous Processing:** Offload conversion to background threads for responsive UIs.  

## Frequently Asked Questions

**Q: How do I **convert pst to pdf** with the same code base?**  
A: Use `PdfViewOptions` as shown in the PDF rendering section; the rest of the code remains identical.

**Q: Can GroupDocs.Viewer handle encrypted PST files?**  
A: Yes, provide the password via `LoadOptions.setPassword("yourPassword")` before rendering.

**Q: What is the difference between **java convert pst** to PNG vs JPG?**  
A: PNG preserves lossless quality, ideal for screenshots, while JPG offers smaller file sizes for email previews.

**Q: Is there a way to **how to convert pst** files in bulk?**  
A: Wrap the rendering logic in a loop that iterates over a directory of PST files; reuse the same `Viewer` configuration for each file.

**Q: Does the API support converting PST files larger than 1 GB?**  
A: Yes, GroupDocs.Viewer streams data and can process files up to 2 GB without loading the entire archive into memory.

## Conclusion

You now have a complete, production‑ready guide to **convert pst to html**, JPG, PNG, and PDF using GroupDocs.Viewer for Java. By following the steps above you can integrate email conversion into any Java‑based workflow, improve accessibility, and meet compliance requirements.

---

**Last Updated:** 2026-07-19  
**Tested With:** GroupDocs.Viewer for Java 25.2  
**Author:** GroupDocs

## Related Tutorials

- [Convert NSF to PDF, HTML, JPG, PNG using GroupDocs.Viewer for Java](/viewer/java/export-conversion/convert-nsf-files-groupdocs-viewer-java/)
- [convert odf html java – Convert ODF to HTML, JPG, PNG, PDF Using GroupDocs.Viewer for Java](/viewer/java/export-conversion/convert-odf-documents-groupdocs-viewer-java/)
- [How to Convert DOCX to HTML Using GroupDocs.Viewer for Java: A Step‑By‑Step Guide](/viewer/java/export-conversion/convert-docx-to-html-groupdocs-viewer-java/)