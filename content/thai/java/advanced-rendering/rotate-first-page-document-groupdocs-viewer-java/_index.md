---
date: '2026-09-30'
description: เรียนรู้วิธีหมุนหน้า 90 องศาใน Java ด้วย GroupDocs Viewer รวมถึงการตั้งค่า
  โค้ด และเคล็ดลับการปรับประสิทธิภาพ
keywords:
- rotate page 90 degrees
- how to rotate pdf
- GroupDocs Viewer Java rotation
- Java document rendering
- PDF page transformation
lastmod: '2026-09-30'
og_description: หมุนหน้า 90 องศาใน Java ด้วย GroupDocs Viewer คู่มือแบบขั้นตอน เคล็ดลับการปรับประสิทธิภาพ
  และกรณีใช้งานจริงสำหรับนักพัฒนา
og_image_alt: Illustration of rotating the first page of a document using GroupDocs
  Viewer for Java
og_title: หมุนหน้า 90 องศาด้วย GroupDocs Viewer for Java
schemas:
- author: GroupDocs
  dateModified: '2026-09-30'
  description: Learn how to rotate page 90 degrees in Java using GroupDocs Viewer,
    including setup, code, and performance tips.
  headline: Rotate page 90 degrees with GroupDocs Viewer for Java
  type: TechArticle
- description: Learn how to rotate page 90 degrees in Java using GroupDocs Viewer,
    including setup, code, and performance tips.
  name: Rotate page 90 degrees with GroupDocs Viewer for Java
  steps:
  - name: '**Presentation adjustments** – Convert a portrait slide to landscape on
      the fly for better visual impact.'
    text: '**Presentation adjustments** – Convert a portrait slide to landscape on
      the fly for better visual impact.'
  - name: '**Bulk document correction** – Automate fixing of scanned PDFs that were
      captured sideways, saving hours of manual work.'
    text: '**Bulk document correction** – Automate fixing of scanned PDFs that were
      captured sideways, saving hours of manual work.'
  - name: '**Print‑ready output** – Ensure landscape graphics print correctly on portrait‑oriented
      paper without manual rotation in the printer driver.'
    text: '**Print‑ready output** – Ensure landscape graphics print correctly on portrait‑oriented
      paper without manual rotation in the printer driver.'
  type: HowTo
- questions:
  - answer: Yes—invoke `rotatePage()` for each page number you need to rotate, either
      in a loop or by chaining calls.
    question: Can I rotate multiple pages at once?
  - answer: Not directly. You would need to render the document again without the
      rotation options.
    question: Is there a way to undo the rotation after rendering?
  - answer: DOCX, PDF, PPTX, XLSX, and many other formats listed in the official documentation.
    question: Which file formats support page rotation in GroupDocs Viewer?
  - answer: Wrap the rotation logic in a loop that iterates over a collection of file
      paths, applying the same `rotatePage` configuration to each file.
    question: How can I rotate pages in a batch of documents automatically?
  - answer: Enclose the Viewer usage in a `try‑catch` block, log the exception details,
      and optionally continue processing the next file to avoid a single failure stopping
      the whole batch.
    question: What is the best practice for handling errors during rotation?
  type: FAQPage
tags:
- rotate page
- GroupDocs Viewer
- Java PDF processing
- document automation
title: หมุนหน้า 90 องศาด้วย GroupDocs Viewer for Java
type: docs
url: /th/java/advanced-rendering/rotate-first-page-document-groupdocs-viewer-java/
weight: 1
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# หมุนหน้าเอกสาร 90 องศาด้วย GroupDocs Viewer for Java

If you need to **rotate page 90 degrees** in a document—whether it’s a PDF, Word file, or spreadsheet—doing it programmatically in Java saves time, removes manual errors, and lets you embed the operation into automated pipelines. In this advanced guide you’ll learn how to rotate the first page of any supported document using **GroupDocs Viewer for Java**, why this capability matters in real‑world projects, and how to keep the process lightweight and memory‑efficient.

![Rotate the First Page of a Document with GroupDocs.Viewer for Java](/viewer/advanced-rendering/rotate-the-first-page-of-a-document-java.png)

## คำตอบสั้น ๆ
- **What does “rotate page 90 degrees” mean?** It turns the selected page clockwise by a quarter turn.  
- **Which library handles the rotation?** GroupDocs Viewer for Java provides the `rotatePage` method.  
- **Can I rotate PDF pages with Java?** Yes—use the same `rotatePage` call; it works for PDF, DOCX, XLSX, and more.  
- **Do I need a license?** A free trial works for development; a paid license is required for production.  
- **Is the operation memory‑intensive?** Not when you close the `Viewer` instance promptly; see the performance tips below.

## “rotate page 90 degrees” คืออะไร?
Rotating a page 90 degrees re‑orients the page from portrait to landscape (or vice‑versa) without changing the underlying content. This is handy for presentations, printing landscape‑only graphics, or correcting scanned documents that were captured sideways. The rotation is applied at render time, leaving the original file unchanged.

## ทำไมต้องหมุนหน้าโดยใช้โปรแกรมกับ GroupDocs Viewer for Java?
GroupDocs Viewer supports **50+ input and output formats**—including PDF, DOCX, PPTX, XLSX, and many image types—so you can render any document without external converters. The API is fluent, thread‑safe, and runs on any Java 8+ runtime, making it a reliable choice for enterprise‑grade automation that must handle dozens of file types consistently.

## ข้อกำหนดเบื้องต้น

- GroupDocs Viewer for Java (latest version)
- JDK 8 หรือใหม่กว่า
- Maven (หรือ Gradle) สำหรับจัดการ dependency
- IDE เช่น IntelliJ IDEA หรือ Eclipse
- ความคุ้นเคยพื้นฐานกับ Java I/O

## การตั้งค่า GroupDocs.Viewer for Java

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

### การรับใบอนุญาต
- **Free trial** – download from the GroupDocs site.  
- **Temporary license** – request if you need an extended evaluation period.  
- **Full license** – purchase for production deployments.

### การเริ่มต้น Viewer เบื้องต้น
The `Viewer` class is the entry point that loads a document and exposes rendering and transformation methods. Keep the code exactly as shown:

```java
import com.groupdocs.viewer.Viewer;

// Initialize Viewer with your document path
try (Viewer viewer = new Viewer("path/to/your/document.docx")) {
    // Perform operations...
}
```

## วิธีหมุนหน้า PDF ด้วย Java ด้วย GroupDocs Viewer
Load the target file with `Viewer`, specify the page number, and call `rotatePage`. The method works for PDF, DOCX, PPTX, XLSX and any other format supported by the library. After rotation, you can render the document to a new PDF or stream it directly to the client, ensuring the original file remains untouched.

## ขั้นตอนการทำงานแบบละเอียด: หมุนหน้าแรก 90 องศา

### 1. นำเข้าแพ็กเกจที่จำเป็น
`PdfViewOptions` tells the Viewer to output a PDF file, while the `Rotation` enum defines the angle. Both classes belong to the `com.groupdocs.viewer.options` package.

```java
import com.groupdocs.viewer.Viewer;
import com.groupdocs.viewer.options.PdfViewOptions;
import com.groupdocs.viewer.options.Rotation;
```

### 2. กำหนดตำแหน่งไฟล์ผลลัพธ์และสร้าง Viewer
Replace the placeholder paths with your actual directories. The `Viewer` constructor accepts a `File` object that points to the source document.

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

### 3. ตั้งค่า PDF view options และใช้การหมุน
The `rotatePage(int, Rotation)` method takes a **1‑based** page index and a `Rotation` enum value. In this example we use `Rotation.ON_90_DEGREE` to turn the first page clockwise.

```java
PdfViewOptions viewOptions = new PdfViewOptions(outputFilePath);

// Specify which page to rotate (1 for first page) and the rotation angle
viewOptions.rotatePage(1, Rotation.ON_90_DEGREE);
```

### 4. เรนเดอร์เอกสาร
Calling `view` with the configured options writes the rotated PDF to the output folder.

```java
viewer.view(viewOptions);
```

#### วิธีการทำงาน
- **PdfViewOptions** directs the Viewer to generate a PDF output file.  
- **rotatePage(int, Rotation)** rotates only the specified page, leaving all other pages unchanged.  
- The method supports three rotation constants: `ON_90_DEGREE`, `ON_180_DEGREE`, and `ON_270_DEGREE`.

## ปัญหาที่พบบ่อยและวิธีแก้
| Symptom | Likely cause | Fix |
|---------|--------------|-----|
| **FileNotFoundException** | Incorrect path or missing folder | Verify `YOUR_OUTPUT_DIRECTORY` and `YOUR_DOCUMENT_DIRECTORY` exist and are readable. |
| **Unsupported file format** | Trying to rotate a format not supported by Viewer | Check the [GroupDocs Viewer supported formats] page. |
| **No rotation visible** | Using the wrong page number (0‑based) | Remember `rotatePage` uses **1‑based** indexing. |
| **Out‑of‑memory errors on large docs** | Rendering many large files in a single thread | Process documents sequentially or use a thread pool with limited concurrency. |

## การใช้งานในเชิงปฏิบัติ

1. **Presentation adjustments** – Convert a portrait slide to landscape on the fly for better visual impact.  
2. **Bulk document correction** – Automate fixing of scanned PDFs that were captured sideways, saving hours of manual work.  
3. **Print‑ready output** – Ensure landscape graphics print correctly on portrait‑oriented paper without manual rotation in the printer driver.

## เคล็ดลับด้านประสิทธิภาพ

- **Close resources promptly** – The `try‑with‑resources` block automatically disposes of the `Viewer`, freeing memory.  
- **Batch processing** – Reuse a single `Viewer` instance per thread to reduce initialization overhead.  
- **Monitor memory** – For documents larger than 100 MB, stream the output to disk instead of keeping the whole file in memory; GroupDocs Viewer can process 200 MB files using under 250 MB of RAM.

## คำถามที่พบบ่อย

**Q: Can I rotate multiple pages at once?**  
A: Yes—invoke `rotatePage()` for each page number you need to rotate, either in a loop or by chaining calls.

**Q: Is there a way to undo the rotation after rendering?**  
A: Not directly. You would need to render the document again without the rotation options.

**Q: Which file formats support page rotation in GroupDocs Viewer?**  
A: DOCX, PDF, PPTX, XLSX, and many other formats listed in the official documentation.

**Q: How can I rotate pages in a batch of documents automatically?**  
A: Wrap the rotation logic in a loop that iterates over a collection of file paths, applying the same `rotatePage` configuration to each file.

**Q: What is the best practice for handling errors during rotation?**  
A: Enclose the Viewer usage in a `try‑catch` block, log the exception details, and optionally continue processing the next file to avoid a single failure stopping the whole batch.

## แหล่งข้อมูล

- **Documentation**: [GroupDocs Viewer Java Documentation](https://docs.groupdocs.com/viewer/java/)  
- **API reference**: [GroupDocs API Reference](https://reference.groupdocs.com/viewer/java/)  
- **Download**: [Get GroupDocs Viewer for Java](https://releases.groupdocs.com/viewer/java/)  
- **Purchase**: [Buy a License](https://purchase.groupdocs.com/buy)  
- **Free trial**: [Try Free](https://releases.groupdocs.com/viewer/java/)  
- **Temporary license**: [Request Temporary License](https://purchase.groupdocs.com/temporary-license/)  
- **Support**: [GroupDocs Forum](https://forum.groupdocs.com/c/viewer/9)

---

**Last Updated:** 2026-09-30  
**Tested With:** GroupDocs Viewer 25.2 for Java  
**Author:** GroupDocs

## บทเรียนที่เกี่ยวข้อง

- [How to Rotate Specific PDF Pages with GroupDocs.Viewer for Java](/viewer/java/advanced-rendering/rotate-pdf-pages-groupdocs-viewer-java/)
- [Load Document from URL in Java – GroupDocs.Viewer Tutorial](/viewer/java/document-loading/)
- [Groupdocs Viewer Java Document Views](/viewer/java/advanced-rendering/groupdocs-viewer-java-document-views/)


{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}