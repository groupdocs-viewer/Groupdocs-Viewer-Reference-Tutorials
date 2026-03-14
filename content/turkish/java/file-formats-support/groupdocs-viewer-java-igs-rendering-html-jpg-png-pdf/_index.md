---
date: '2026-02-23'
description: GroupDocs.Viewer for Java ile IGS'yi PDF, HTML, JPG ve PNG'ye nasıl dönüştüreceğinizi
  öğrenin. Hazır çalışan kod örnekleriyle adım adım rehberi izleyin.
keywords:
- GroupDocs.Viewer Java
- Convert IGS Files
- Render IGS Documents
title: GroupDocs.Viewer Java kullanarak IGS'yi PDF, HTML, JPG ve PNG'ye dönüştür
type: docs
url: /tr/java/file-formats-support/groupdocs-viewer-java-igs-rendering-html-jpg-png-pdf/
weight: 1
---

# Convert IGS to PDF, HTML, JPG & PNG using GroupDocs.Viewer Java

If you need to **convert IGS to PDF** (or to HTML, JPG, PNG) directly from a Java application, you’ve come to the right place. In this tutorial we’ll walk through everything you need—from setting up the library to rendering the 3‑D model in the format that fits your project. You’ll see why GroupDocs.Viewer is a solid choice for fast, reliable conversions and get hands‑on code you can drop into your own solution.

![Convert IGS Files to HTML, JPG, PNG, and PDF with GroupDocs.Viewer for Java](/viewer/file-formats-support/convert-igs-files-to-html-jpg-png-and-pdf-java.png)

## Quick Answers
- **Can I convert IGS to PDF with Java?** Yes, using GroupDocs.Viewer’s `PdfViewOptions`.
- **Which output formats are supported?** HTML, JPG, PNG, and PDF.
- **Do I need a license for production?** A commercial license is required; a free trial is available for testing.
- **What Java version is required?** JDK 8 or higher.
- **Is Maven the only way to add the library?** No, you can also use Gradle or manual JAR inclusion.

## What is “convert IGS to PDF”?
Converting IGS (a neutral file format for 3‑D CAD data) to PDF means turning a complex 3‑D model into a static, widely viewable document. This is useful for sharing designs with stakeholders who don’t have CAD tools.

## Why use GroupDocs.Viewer for IGS conversions?
- **Zero‑code CAD rendering** – the library handles the heavy lifting of parsing the IGS format.
- **Multiple output options** – one API call can produce HTML, JPG, PNG, or PDF.
- **Cross‑platform** – works on any OS that supports Java.
- **Performance‑focused** – fast rendering even for large assemblies.

## Prerequisites
- **GroupDocs.Viewer for Java** ≥ 25.2  
- **JDK 8+** installed and configured in your IDE (IntelliJ IDEA, Eclipse, NetBeans, etc.)  
- Basic Maven knowledge (optional but recommended)  

## Setting Up GroupDocs.Viewer for Java

### Maven Dependency
Add the GroupDocs repository and the Viewer dependency to your `pom.xml`:

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
GroupDocs.Viewer offers:
- **Free trial** – limited usage, great for quick tests.  
- **Temporary license** – full feature set for a short evaluation period.  
- **Commercial license** – unrestricted production use.

### Basic Viewer Initialization
The snippet below shows how to create a `Viewer` instance that points to your IGS file:

```java
import com.groupdocs.viewer.Viewer;

public class ViewerSetup {
    public static void main(String[] args) {
        try (Viewer viewer = new Viewer("path/to/your/document.igs")) {
            // Configuration and rendering logic goes here.
        }
    }
}
```

## Rendering IGS to HTML

### How to convert IGS to HTML?
HTML output gives you an interactive, browser‑friendly view of the 3‑D model.

```java
import com.groupdocs.viewer.Viewer;
import com.groupdocs.viewer.options.HtmlViewOptions;
import java.nio.file.Path;
import static java.nio.file.Paths.get;

public class RenderIgsToHtml {
    public static void run() {
        Path outputDirectory = get("YOUR_OUTPUT_DIRECTORY");
        Path pageFilePathFormat = outputDirectory.resolve("IGS_result.html");

        try (Viewer viewer = new Viewer(get("YOUR_DOCUMENT_DIRECTORY/SAMPLE_IGS"))) {
            HtmlViewOptions options = HtmlViewOptions.forEmbeddedResources(pageFilePathFormat);
            viewer.view(options);
        }
    }
}
```

**Key point:** `HtmlViewOptions.forEmbeddedResources()` embeds all required assets (CSS, images) directly into the HTML file, making it portable.

## Rendering IGS to JPG

### How to convert IGS to JPG?
JPG images are perfect for thumbnails or quick previews.

```java
import com.groupdocs.viewer.Viewer;
import com.groupdocs.viewer.options.JpgViewOptions;
import java.nio.file.Path;
import static java.nio.file.Paths.get;

public class RenderIgsToJpg {
    public static void run() {
        Path outputDirectory = get("YOUR_OUTPUT_DIRECTORY");
        Path pageFilePathFormat = outputDirectory.resolve("IGS_result.jpg");

        try (Viewer viewer = new Viewer(get("YOUR_DOCUMENT_DIRECTORY/SAMPLE_IGS"))) {
            JpgViewOptions options = new JpgViewOptions(pageFilePathFormat);
            viewer.view(options);
        }
    }
}
```

You can tweak `JpgViewOptions` to control resolution and compression quality.

## Rendering IGS to PNG

### How to convert IGS to PNG?
PNG supports transparency, which is handy for overlaying the model on different backgrounds.

```java
import com.groupdocs.viewer.Viewer;
import com.groupdocs.viewer.options.PngViewOptions;
import java.nio file.Path;
import static java.nio.file.Paths.get;

public class RenderIgsToPng {
    public static void run() {
        Path outputDirectory = get("YOUR_OUTPUT_DIRECTORY");
        Path pageFilePathFormat = outputDirectory.resolve("IGS_result.png");

        try (Viewer viewer = new Viewer(get("YOUR_DOCUMENT_DIRECTORY/SAMPLE_IGS"))) {
            PngViewOptions options = new PngViewOptions(pageFilePathFormat);
            viewer.view(options);
        }
    }
}
```

Experiment with the `PngViewOptions` to get the best balance between file size and visual fidelity.

## Rendering IGS to PDF

### How to convert IGS to PDF?
PDF is the go‑to format for sharing detailed design documentation. This section directly addresses the primary keyword **convert IGS to PDF**.

```java
import com.groupdocs.viewer.Viewer;
import com.groupdocs.viewer.options.PdfViewOptions;
import java.nio.file.Path;
import static java.nio.file.Paths.get;

public class RenderIgsToPdf {
    public static void run() {
        Path outputDirectory = get("YOUR_OUTPUT_DIRECTORY");
        Path pageFilePathFormat = outputDirectory.resolve("IGS_result.pdf");

        try (Viewer viewer = new Viewer(get("YOUR_DOCUMENT_DIRECTORY/SAMPLE_IGS"))) {
            PdfViewOptions options = new PdfViewOptions(pageFilePathFormat);
            viewer.view(options);
        }
    }
}
```

`PdfViewOptions` lets you control page layout, image quality, and whether to embed fonts.

## Practical Applications

- **Web portals** – embed HTML‑rendered models directly into product configurators.  
- **Marketing assets** – generate high‑resolution JPG/PNG images for brochures.  
- **Technical documentation** – include PDF renderings of CAD models in user manuals.  
- **Quality assurance** – automate thumbnail generation for large batches of IGS files.

## Common Issues & Solutions

| Issue | Solution |
|-------|----------|
| **Output folder not found** | Verify the path passed to `Path outputDirectory` and ensure the Java process has write permissions. |
| **Blank pages in PDF** | Make sure the IGS file is not corrupted; try opening it in a CAD viewer first. |
| **Slow rendering for large assemblies** | Increase JVM heap (`-Xmx2g` or more) and consider rendering page‑by‑page using `viewer.getPageCount()` if needed. |
| **Missing fonts in PDF** | Use `PdfViewOptions` to embed required fonts or install the missing fonts on the server. |

## Frequently Asked Questions

**Q: Can I convert multiple IGS files in a single run?**  
A: Yes. Loop through a list of file paths and invoke the appropriate `view` method for each.

**Q: Is it possible to customize the PDF page size?**  
A: Absolutely. `PdfViewOptions` provides `setPageSize(PageSize.A4)` and similar methods.

**Q: Do I need a separate license for each output format?**  
A: No. A single GroupDocs.Viewer license covers all supported formats.

**Q: How large can an IGS file be before performance degrades?**  
A: The library handles files up to several hundred megabytes, but you may need to allocate more JVM memory for very large models.

**Q: Can I render only a specific view or orientation?**  
A: GroupDocs.Viewer renders the default view. For custom orientations, preprocess the IGS file with a CAD tool before conversion.

---

**Last Updated:** 2026-02-23  
**Tested With:** GroupDocs.Viewer 25.2 for Java  
**Author:** GroupDocs