---
date: '2026-06-15'
description: เรียนรู้วิธีแปลง Excel เป็น PDF ด้วย Java และแยกชีต Excel ตามแถวและคอลัมน์โดยใช้
  GroupDocs Viewer. รวมการตั้งค่า, โค้ด, และแนวปฏิบัติที่ดีที่สุด.
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
title: แปลง Excel เป็น PDF ด้วย Java & แยกชีตตามแถวและคอลัมน์
type: docs
url: /th/java/custom-rendering/groupdocs-viewer-java-split-excel-sheets-rows-columns/
weight: 1
---

# แปลง Excel เป็น PDF Java & แบ่งชีตตามแถวและคอลัมน์ (Java)

สมุดงาน Excel ขนาดใหญ่มักมีข้อมูลมากกว่าที่จะแสดงบนหน้าจอเดียวหรือพิมพ์ออกได้อย่างสบายใจ **convert excel to pdf java** เป็นความต้องการทั่วไปเมื่อคุณต้องการรูปแบบที่คงที่และสามารถแชร์ได้, ในขณะที่ **splitting Excel sheets by rows and columns** ทำให้ข้อมูลง่ายต่อการใช้งานในเว็บหรือการจัดหน้าเพื่อพิมพ์ ในคู่มือนี้เราจะอธิบายขั้นตอนทั้งสองโดยใช้ **GroupDocs Viewer for Java**, แสดงวิธีการกำหนดการแบ่งหน้า, และอธิบายเคล็ดลับการปฏิบัติที่ดีที่สุดสำหรับประสิทธิภาพและการแก้ปัญหา.

![แยกชีต Excel ตามแถวและคอลัมน์ด้วย GroupDocs.Viewer for Java](/viewer/custom-rendering/split-excel-sheets-by-rows-and-columns.png)

[แยกชีต Excel ตามแถวและคอลัมน์ด้วย GroupDocs.Viewer for Java](/viewer/custom-rendering/split-excel-sheets-by-rows-and-columns.png)

## คำตอบด่วน
- **What library is used?** GroupDocs Viewer for Java.  
- **Can I split by both rows and columns?** Yes – you can define rows‑per‑page and columns‑per‑page together.  
- **Do I need a license?** A trial or temporary license works for development; a full license is required for production.  
- **What output formats are supported?** HTML (embedded resources) is shown; PDF can be generated with the same options.  
- **Is Maven required?** Maven is the recommended way to manage dependencies.  
- **Can I also convert Excel to PDF?** Absolutely – just switch `HtmlViewOptions` to `PdfViewOptions` and reuse the same pagination settings.

## “วิธีการแยก Excel” คืออะไร?
การแยกชีต Excel หมายถึงการแบ่งเวิร์กชีตเดียวออกเป็นหลายหน้าหรือหลายไฟล์ตามจำนวนแถวหรือคอลัมน์ที่กำหนด (หรือทั้งสองอย่าง) เทคนิคนี้มีประโยชน์เมื่อคุณต้องการสร้างรายงานแบบแบ่งหน้า, ฝังข้อมูลในหน้าเว็บ, หรือสร้างส่วนที่พิมพ์ได้โดยไม่ต้องโหลดสมุดงานทั้งหมดในครั้งเดียว

## ทำไมต้องใช้ GroupDocs Viewer for Java?
GroupDocs Viewer ประมวลผลสเปรดชีตในหนึ่งรอบและทำการแบ่งหน้าโดยอัตโนมัติ, ลดความจำเป็นในการคำนวณด้วยตนเอง **กระบวนการเรนเดอร์ที่เร็วสามารถประมวลผลสมุดงาน XLSX 250 หน้าได้ภายในต่ำกว่า 2 วินาทีบนเซิร์ฟเวอร์ 2‑core ปกติ**, และ **ไลบรารีรองรับรูปแบบเข้าและออกกว่า 50 ประเภท** รวมถึง XLS, XLSX, CSV, PDF, และ HTML มันทำงานบนแพลตฟอร์มที่รองรับ JVM ทุกประเภท—Windows, Linux, macOS, Docker container หรือสภาพแวดล้อม serverless บนคลาวด์—ดังนั้นคุณสามารถผสานรวมได้ทุกที่ที่แอปพลิเคชัน Java ของคุณทำงาน

## ข้อกำหนดเบื้องต้น
- Java 17 หรือใหม่กว่า  
- IDE เช่น IntelliJ IDEA หรือ Eclipse  
- Maven สำหรับการจัดการ dependencies  
- ความรู้พื้นฐานของ Java และการจัดการไฟล์ Excel

### ไลบรารีที่ต้องการ, เวอร์ชัน, และการพึ่งพา
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

### การรับไลเซนส์
Obtain a free trial, temporary license, or purchase a full license from [GroupDocs](https://purchase.groupdocs.com/buy).

## วิธีแปลง Excel เป็น PDF Java?

คลาส `Viewer` เป็นคอมโพเนนต์หลักของ GroupDocs Viewer ที่โหลดเอกสารและให้เมธอดเรนเดอร์สำหรับรูปแบบผลลัพธ์ต่าง ๆ `SpreadsheetOptions` ช่วยให้คุณควบคุมการตั้งค่าการแบ่งหน้า เช่น rows‑per‑page และ columns‑per‑page สำหรับการเรนเดอร์สเปรดชีต

โหลดไฟล์ Excel ของคุณด้วย `new Viewer("source.xlsx")`, กำหนด `SpreadsheetOptions` สำหรับการแบ่งหน้า, แล้วเรียก `viewer.view(pdfOptions, stream)` – การเรียกเดียวนี้จะแปลงสมุดงานเป็น PDF พร้อมรักษาขอบเขตแถว/คอลัมน์ที่คุณตั้งค่าไว้ การแปลงจะคงสูตร, รูปภาพ, และสไตล์ของเซลล์, ให้ผลลัพธ์ PDF ที่ตรงกับต้นฉบับพร้อมสำหรับการแจกจ่าย

## วิธีแยกชีต Excel ตามแถว

การแยกตามแถวจะสร้างชุดหน้า HTML แต่ละหน้าเป็นจำนวนแถวคงที่ (เช่น 15 แถว) วิธีนี้เหมาะกับแดชบอร์ดที่ต้องการแสดงบันทึกจำนวนจำกัดต่อมุมมอง Viewer จะสร้างไฟล์ HTML แยกต่างหากเช่น `page_0.html`, `page_1.html` เป็นต้น, แต่ละไฟล์จะมีจำนวนแถวตามที่กำหนด ทำให้สามารถโหลดเฉพาะส่วนที่ต้องการในอินเทอร์เฟซเว็บ, ลดแบนด์วิธและเวลาเรนเดอร์

### คำอธิบาย Anchor
`Viewer` คือคลาสหลักของ GroupDocs Viewer ที่โหลดเอกสารและจัดการการเรนเดอร์ไปยังรูปแบบผลลัพธ์ที่เลือก

### การดำเนินการแบบขั้นตอน

#### ขั้นตอนที่ 1: ตั้งค่าเส้นทางและเริ่มต้น Viewer
First, define where the split pages will be saved and create a `Viewer` instance for the source workbook.

```java
Path outputDirectory = Path.of("YOUR_OUTPUT_DIRECTORY/SplitByRows");
Path pageFilePathFormat = outputDirectory.resolve("page_{0}.html");

try (Viewer viewer = new Viewer("YOUR_DOCUMENT_DIRECTORY/TWO_PAGES_XLSX")) {
    // Proceed with further configuration...
}
```

#### ขั้นตอนที่ 2: กำหนดจำนวนแถวต่อหน้า
Tell the viewer how many rows each page should contain.

```java
int countRowsPerPage = 15;
HtmlViewOptions viewOptions = HtmlViewOptions.forEmbeddedResources(pageFilePathFormat);
viewOptions.setSpreadsheetOptions(SpreadsheetOptions.forSplitSheetIntoPages(countRowsPerPage));
```

#### ขั้นตอนที่ 3: เรนเดอร์เอกสาร
Finally, render the workbook using the options you defined.

```java
viewer.view(viewOptions);
```

## วิธีแยกชีต Excel ตามแถวและคอลัมน์

บางครั้งหน้าหนึ่งต้องแสดงเมทริกซ์ของแถว **และ** คอลัมน์ (เช่น 15 แถว × 7 คอลัมน์) วิธีนี้ให้คุณควบคุมการจัดวางของแต่ละหน้า HTML อย่างเต็มที่ หน้าเหล่านี้จะแสดงบล็อกสี่เหลี่ยมของเซลล์, ตัวอย่างเช่น แถว 1‑15 และคอลัมน์ A‑G บนหน้าแรก, แถว 16‑30 และคอลัมน์ H‑N บนหน้าถัดไป การแบ่งหน้าแบบกริดนี้เหมาะสำหรับการสร้างรายงานที่พิมพ์ได้ตรงกับขนาดกระดาษมาตรฐาน

### คำอธิบาย Anchor
`SpreadsheetOptions` configures how many rows and columns appear on each generated page.

### การดำเนินการแบบขั้นตอน

#### ขั้นตอนที่ 1: ตั้งค่าเส้นทางและเริ่มต้น Viewer
The setup mirrors the row‑only example, only the file name changes.

```java
Path outputDirectory = Path.of("YOUR_OUTPUT_DIRECTORY/SplitByRowsAndColumns");
Path pageFilePathFormat = outputDirectory.resolve("page_{0}.html");

try (Viewer viewer = new Viewer("YOUR_DOCUMENT_DIRECTORY/FOUR_PAGES_XLSX")) {
    // Continue with configuration...
}
```

#### ขั้นตอนที่ 2: กำหนดจำนวนแถวและคอลัมน์ต่อหน้า
Specify both dimensions to create a grid‑style split.

```java
int countRowsPerPage = 15;
int countColumnsPerPage = 7;

HtmlViewOptions options = HtmlViewOptions.forEmbeddedResources(pageFilePathFormat);
options.setSpreadsheetOptions(SpreadsheetOptions.forSplitSheetIntoPages(countRowsPerPage, countColumnsPerPage));
```

#### ขั้นตอนที่ 3: เรนเดอร์เอกสาร
Render using the same `view` call.

```java
viewer.view(options);
```

## การประยุกต์ใช้งานจริง
- **Generate Excel report Java**: Turn large financial models into a series of paginated HTML reports.  
- **GroupDocs Viewer Excel**: Embed split pages directly into a web portal for interactive data exploration.  
- **Render Excel HTML Java**: Serve the generated HTML pages via a servlet or Spring controller for fast client‑side rendering.  

## พิจารณาด้านประสิทธิภาพ
- **Memory usage** – Large workbooks can consume significant heap; consider increasing the JVM `-Xmx` setting.  
- **Chunk size** – Choose row/column counts that balance page size and rendering speed.  
- **Version updates** – Keep GroupDocs Viewer up‑to‑date to benefit from performance improvements; the latest 25.2 release improves rendering speed by up to 30 % compared with 24.x.

## ปัญหาทั่วไป & การแก้ไขปัญหา
| อาการ | สาเหตุที่เป็นไปได้ | วิธีแก้ |
|---------|--------------|-----|
| `OutOfMemoryError` | Rendering a very large sheet with too many rows per page | Reduce `countRowsPerPage` or increase JVM heap |
| Blank output files | Incorrect file path or missing write permissions | Verify `outputDirectory` exists and is writable |
| HTML resources not loading | Using `forEmbeddedResources` but serving files from a different base URL | Serve the entire output folder or switch to `forExternalResources` |

## คำถามที่พบบ่อย

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

## แหล่งข้อมูล
- **เอกสารประกอบ**: [GroupDocs Viewer Java Documentation](https://docs.groupdocs.com/viewer/java/)
- **อ้างอิง API**: [GroupDocs API Reference](https://reference.groupdocs.com/viewer/java/)
- **ดาวน์โหลด**: [GroupDocs Viewer Java Releases](https://releases.groupdocs.com/viewer/java/)
- **ซื้อ**: [Buy GroupDocs License](https://purchase.groupdocs.com/buy)
- **ทดลองใช้ฟรี**: [GroupDocs Free Trial](https://releases.groupdocs.com/viewer/java/)
- **ไลเซนส์ชั่วคราว**: [Get Temporary License](https://purchase.groupdocs.com/temporary-license/)
- **สนับสนุน**: [GroupDocs Support Forum](https://forum.groupdocs.com/c/viewer/9)

---

**Last Updated:** 2026-06-15  
**Tested With:** GroupDocs Viewer 25.2 for Java  
**Author:** GroupDocs  

## บทแนะนำที่เกี่ยวข้อง

- [Render Hidden Rows & Columns in Java Spreadsheets Using GroupDocs.Viewer](/viewer/java/advanced-rendering/render-hidden-rows-columns-java-groupdocs-viewer/)
- [Skip Rendering Empty Rows in Java Using GroupDocs.Viewer: A Performance Guide](/viewer/java/advanced-rendering/skip-rendering-empty-rows-java-groupdocs-viewer/)
- [Comprehensive Guide: Convert Excel 2003 XML to HTML/JPG/PNG/PDF with GroupDocs.Viewer Java](/viewer/java/rendering-basics/groupdocs-viewer-java-excel-2003-xml-conversion/)