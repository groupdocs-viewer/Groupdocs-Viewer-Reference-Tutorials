---
title: "Rotate page 90 degrees with GroupDocs Viewer for Java"
description: "Learn how to rotate page 90 degrees in Java using GroupDocs Viewer, including setup, code, and performance tips."
date: "2026-01-18"
weight: 1
url: "/java/advanced-rendering/rotate-first-page-document-groupdocs-viewer-java/"
keywords:
- rotate first page GroupDocs Viewer Java
- GroupDocs Viewer Java setup
- rotate pages in documents using Java
type: docs
---

# Rotate page 90 degrees with GroupDocs Viewer for Java

When you need to **rotate page 90 degrees** in a document—whether it’s a PDF, Word file, or spreadsheet—doing it programmatically saves time and eliminates manual errors. In this advanced guide we’ll walk through the exact steps to rotate the first page of any supported document using **GroupDocs Viewer for Java**. By the end, you’ll have a reusable snippet that you can drop into your own projects.

![Rotate the First Page of a Document with GroupDocs.Viewer for Java](/viewer/advanced-rendering/rotate-the-first-page-of-a-document-java.png)

## Quick Answers
- **What does “rotate page 90 degrees” mean?** It turns the selected page clockwise by a quarter turn.  
- **Which library handles the rotation?** GroupDocs Viewer for Java provides the `rotatePage` method.  
- **Can I rotate PDF pages with Java?** Yes—use the same `rotatePage` call; it works for PDF, DOCX, XLSX, and more.  
- **Do I need a license?** A free trial works for development; a paid license is required for production.  
- **Is the operation memory‑intensive?** Not when you close the `Viewer` instance promptly; see the performance tips below.

## What is “rotate page 90 degrees”?
Rotating a page 90 degrees re‑orients the page from portrait to landscape (or vice‑versa) without altering the underlying content. This is especially handy for presentations, printing landscape‑only graphics, or correcting scanned documents that were captured sideways.

## Why rotate pages with GroupDocs Viewer for Java?
GroupDocs Viewer abstracts the complexities of handling dozens of file formats. It lets you apply page‑level transformations—like rotation—while keeping the original file intact. The API is fluent, thread‑safe, and works on any Java 8+ runtime.

## Prerequisites

- **GroupDocs.Viewer for Java** (latest version)
- **JDK 8** or newer
- **Maven** (or Gradle) for dependency management
- An IDE such as IntelliJ IDEA or Eclipse
- Basic familiarity with Java I/O

## Setting Up GroupDocs.Viewer for Java

Add the GroupDocs repository and dependency to your `pom.xml`. This snippet is unchanged from the original tutorial:

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

### License acquisition
- **Free trial** – download from the GroupDocs site.  
- **Temporary license** – request if you need an extended evaluation period.  
- **Full license** – purchase for production deployments.

### Basic Viewer initialization
The following code shows the minimal way to create a `Viewer` instance. Keep it exactly as shown:

```java
import com.groupdocs.viewer.Viewer;

// Initialize Viewer with your document path
try (Viewer viewer = new Viewer("path/to/your/document.docx")) {
    // Perform operations...
}
```

## Step‑by‑Step Implementation: Rotate the First Page 90 Degrees

### 1. Import the required packages
These imports give you access to PDF rendering options and the rotation enum.

```java
import com.groupdocs.viewer.Viewer;
import com.groupdocs.viewer.options.PdfViewOptions;
import com.groupdocs.viewer.options.Rotation;
```

### 2. Define output locations and create the Viewer
Replace the placeholder paths with your actual directories.

```java
import java.nio.file.Path;

public class RotateSpecificPage {
    public static void run() {
        Path outputDirectory = YOUR_OUTPUT_DIRECTORY.resolve("RotateSpecificPage");
        Path outputFilePath = outputDirectory.resolve("output.pdf");

        try (Viewer viewer = new Viewer(YOUR_DOCUMENT_DIRECTORY.resolve("Sample.docx"))) {
            // Proceed with the rotation steps below...
        }
    }
}
```

### 3. Configure PDF view options and apply the rotation
The `rotatePage` method takes the page number (1‑based) and a `Rotation` enum value.

```java
PdfViewOptions viewOptions = new PdfViewOptions(outputFilePath);

// Specify which page to rotate (1 for first page) and the rotation angle
viewOptions.rotatePage(1, Rotation.ON_90_DEGREE);
```

### 4. Render the document
Finally, call `view` to generate the rotated PDF.

```java
viewer.view(viewOptions);
```

#### How it works
- **PdfViewOptions** tells the Viewer to output a PDF file.  
- **rotatePage(int, Rotation)** rotates only the page you specify, leaving the rest untouched.  
- The method supports `ON_90_DEGREE`, `ON_180_DEGREE`, and `ON_270_DEGREE`.

## Common Issues and Solutions
| Symptom | Likely Cause | Fix |
|---------|--------------|-----|
| **FileNotFoundException** | Incorrect path or missing folder | Verify `YOUR_OUTPUT_DIRECTORY` and `YOUR_DOCUMENT_DIRECTORY` exist and are readable. |
| **Unsupported file format** | Trying to rotate a format not supported by Viewer | Check the [GroupDocs Viewer supported formats] page. |
| **No rotation visible** | Using the wrong page number (0‑based) | Remember `rotatePage` uses **1‑based** indexing. |
| **Out‑of‑memory errors on large docs** | Rendering many large files in a single thread | Process documents sequentially or use a thread pool with limited concurrency. |

## Practical Applications

1. **Presentation adjustments** – Convert a portrait slide to landscape on the fly.  
2. **Bulk document correction** – Automate fixing of scanned PDFs that were captured sideways.  
3. **Print‑ready output** – Ensure landscape graphics print correctly on portrait‑oriented paper.

## Performance Tips

- **Close resources promptly** – The `try‑with‑resources` block automatically disposes of the `Viewer`.  
- **Batch processing** – When handling many files, reuse a single `Viewer` instance per thread to reduce overhead.  
- **Monitor memory** – For documents larger than 100 MB, consider streaming the output to disk rather than keeping it in memory.

## Frequently Asked Questions

**Q: Can I rotate multiple pages at once?**  
A: Yes—call `rotatePage()` for each page number you need to rotate.

**Q: Is there a way to undo the rotation after rendering?**  
A: Not directly. You would need to render the document again without the rotation options.

**Q: Which file formats support page rotation in GroupDocs Viewer?**  
A: DOCX, PDF, PPTX, XLSX, and many other formats listed in the official documentation.

**Q: How can I rotate pages in a batch of documents automatically?**  
A: Wrap the code in a loop that iterates over a collection of file paths, applying the same `rotatePage` logic to each.

**Q: What is the best practice for handling errors during rotation?**  
A: Enclose the Viewer usage in a `try‑catch` block, log the exception, and optionally continue processing the next file.

## Resources

- **Documentation**: [GroupDocs Viewer Java Documentation](https://docs.groupdocs.com/viewer/java/)  
- **API Reference**: [GroupDocs API Reference](https://reference.groupdocs.com/viewer/java/)  
- **Download**: [Get GroupDocs Viewer for Java](https://releases.groupdocs.com/viewer/java/)  
- **Purchase**: [Buy a License](https://purchase.groupdocs.com/buy)  
- **Free Trial**: [Try Free](https://releases.groupdocs.com/viewer/java/)  
- **Temporary License**: [Request Temporary License](https://purchase.groupdocs.com/temporary-license/)  
- **Support**: [GroupDocs Forum](https://forum.groupdocs.com/c/viewer/9)

---

**Last Updated:** 2026-01-18  
**Tested With:** GroupDocs Viewer 25.2 for Java  
**Author:** GroupDocs  

---