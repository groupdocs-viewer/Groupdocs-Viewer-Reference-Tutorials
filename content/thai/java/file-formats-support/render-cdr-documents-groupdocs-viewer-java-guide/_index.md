---
date: '2026-08-19'
description: เรียนรู้วิธีแปลง cdr เป็น html รวมถึง jpg, png, และ pdf ด้วย GroupDocs.Viewer
  for Java. รวม setup, code examples, และ performance tips.
keywords:
- convert cdr to html
- convert cdr to pdf
- convert cdr to jpg
- convert cdr to png
- java convert coreldraw
lastmod: '2026-08-19'
og_description: เรียนรู้วิธีแปลง cdr เป็น html, jpg, png, และ pdf ด้วย GroupDocs.Viewer
  for Java. Step‑by‑step guide with setup, code snippets, and performance best practices.
og_image_alt: Guide showing conversion of CorelDRAW CDR files to HTML, JPG, PNG, and
  PDF using GroupDocs.Viewer for Java
og_title: แปลง cdr เป็น html, jpg, png, pdf ด้วย GroupDocs.Viewer Java
schemas:
- author: GroupDocs
  dateModified: '2026-08-19'
  description: Learn how to convert cdr to html, as well as jpg, png, and pdf, using
    GroupDocs.Viewer for Java. Includes setup, code examples, and performance tips.
  headline: Convert cdr to html, jpg, png, pdf with GroupDocs.Viewer Java
  type: TechArticle
- description: Learn how to convert cdr to html, as well as jpg, png, and pdf, using
    GroupDocs.Viewer for Java. Includes setup, code examples, and performance tips.
  name: Convert cdr to html, jpg, png, pdf with GroupDocs.Viewer Java
  steps:
  - name: '**Libraries and dependencies** – GroupDocs.Viewer added to your Maven project.'
    text: '**Libraries and dependencies** – GroupDocs.Viewer added to your Maven project.'
  - name: '**Java Development Kit (JDK)** – version 8 or newer installed.'
    text: '**Java Development Kit (JDK)** – version 8 or newer installed.'
  - name: '**Basic Java knowledge** – to understand the code snippets.'
    text: '**Basic Java knowledge** – to understand the code snippets.'
  type: HowTo
- questions:
  - answer: Yes. Load the file with a `Viewer` instance that accepts a password parameter
      (see the API docs).
    question: Can I convert password‑protected CDR files?
  - answer: No hard limit, but very large files may require more memory; consider
      processing page‑by‑page.
    question: Is there a limit on the number of pages that can be converted at once?
  - answer: When using `HtmlViewOptions.forEmbeddedResources`, fonts are embedded
      as Base64, ensuring consistent rendering across browsers.
    question: Does the HTML output include embedded fonts?
  - answer: '`JpgViewOptions` provides a `setQuality(int)` method where you can specify
      a value from 1‑100.'
    question: How do I control JPEG quality?
  - answer: Absolutely—GroupDocs.Viewer is platform‑agnostic as long as the JDK is
      installed.
    question: Can I convert CDR files on a Linux server?
  type: FAQPage
tags:
- convert cdr
- groupdocs.viewer
- java file conversion
- coreldraw cdr
- document rendering
title: แปลง cdr เป็น html, jpg, png, pdf ด้วย GroupDocs.Viewer Java
type: docs
url: /th/java/file-formats-support/render-cdr-documents-groupdocs-viewer-java-guide/
weight: 1
---

# แปลง cdr เป็น html, jpg, png, pdf ด้วย GroupDocs.Viewer Java

หากคุณต้องการ **แปลง cdr เป็น html** (หรือเป็น JPG, PNG, และ PDF) อย่างรวดเร็วและเชื่อถือได้ คุณมาถูกที่แล้วในบทแนะนำนี้ ในคู่มือนี้เราจะอธิบายทุกอย่างที่คุณต้องการ—ตั้งแต่การติดตั้ง GroupDocs.Viewer สำหรับ Java ไปจนถึงการแปลงไฟล์ CorelDRAW (CDR) ให้เป็นหน้า HTML ที่เหมาะกับเว็บ ภาพคุณภาพสูง และ PDF ที่อ่านได้ทั่วโลก เมื่อเสร็จสิ้น คุณจะสามารถรวมการแปลงเหล่านี้เข้าไปในแอปพลิเคชัน Java ใดก็ได้ด้วยเพียงไม่กี่บรรทัดของโค้ด.

![Render CDR Files with GroupDocs.Viewer for Java](/viewer/file-formats-support/render-cdr-files.png)

[Render CDR Files with GroupDocs.Viewer for Java](/viewer/file-formats-support/render-cdr-files.png)

## คำตอบเร็ว
- **ไลบรารีอะไรที่แปลง CDR เป็น HTML?** GroupDocs.Viewer for Java.  
- **ฉันสามารถแปลง CDR เป็น JPG, PNG, และ PDF ได้ด้วยหรือไม่?** ใช่—ใช้ Viewer API เดียวกันกับตัวเลือกการแสดงผลที่ต่างกัน.  
- **ฉันต้องการไลเซนส์หรือไม่?** การทดลองใช้ฟรีหรือไลเซนส์ชั่วคราวใช้ได้สำหรับการทดสอบ; จำเป็นต้องมีไลเซนส์เต็มสำหรับการใช้งานจริง.  
- **ต้องการเวอร์ชัน Java ใด?** JDK 8 หรือใหม่กว่า.  
- **รองรับการแปลงเป็นชุดหรือไม่?** แน่นอน—เพียงวนลูปไฟล์ด้วย Viewer instance เดียวกัน.

## “แปลง cdr เป็น html” คืออะไร
การแปลง cdr เป็น html หมายถึงการเปลี่ยนไฟล์เวกเตอร์ CorelDRAW ให้เป็นโค้ด HTML มาตรฐาน โดยอาจฝังรูปภาพและสไตล์เพื่อให้การออกแบบสามารถดูได้โดยตรงในเว็บเบราว์เซอร์โดยไม่ต้องใช้ซอฟต์แวร์ออกแบบเดิม กระบวนการนี้รักษาเลย์เอาต์ สี และรูปทรงเวกเตอร์เดิมโดยแปลงเป็นองค์ประกอบ SVG ที่ขยายได้หรือรูปภาพแรสเตอร์ที่ฝังอยู่ใน HTML ทำให้การแสดงผลที่แม่นยำข้ามเบราว์เซอร์ในขณะที่ขนาดไฟล์ยังคงเล็ก.

## ทำไมต้องแปลง cdr เป็น html, jpg, png หรือ pdf
คุณสามารถเรนเดอร์ไฟล์ CDR ต้นฉบับเป็นสี่รูปแบบที่รองรับอย่างกว้างขวาง แต่ละรูปแบบมีจุดประสงค์ที่แตกต่างกัน: HTML สำหรับการพรีวิวบนเว็บทันที, JPG/PNG สำหรับรูปภาพแรสเตอร์, และ PDF สำหรับเอกสารที่พิมพ์ได้และเก็บถาวร ความยืดหยุ่นนี้ช่วยให้คุณส่งไฟล์ประเภทที่เหมาะสมที่สุดให้กับลูกค้า ลดการซ้ำซ้อนของการเก็บข้อมูล และทำให้ทรัพยากรของคุณพร้อมใช้งานในอนาคต.

## ข้อกำหนดเบื้องต้น

ก่อนเริ่มทำตามขั้นตอนต่อไปนี้ให้แน่ใจว่าคุณมี:

1. **ไลบรารีและการพึ่งพา** – เพิ่ม GroupDocs.Viewer ลงในโครงการ Maven ของคุณ.  
2. **Java Development Kit (JDK)** – ติดตั้งเวอร์ชัน 8 หรือใหม่กว่า.  
3. **ความรู้พื้นฐานของ Java** – เพื่อเข้าใจโค้ดตัวอย่าง.

### ไลบรารีที่ต้องการ, เวอร์ชัน, และการพึ่งพา

เพิ่มการกำหนดค่า Maven ต่อไปนี้ในไฟล์ `pom.xml` ของคุณ (ไม่เปลี่ยนแปลงจากบทแนะนำต้นฉบับ):

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

### ขั้นตอนการรับไลเซนส์

GroupDocs.Viewer มีตัวเลือกการทดลองใช้ฟรี, ไลเซนส์ชั่วคราวสำหรับการทดสอบ, หรือการซื้อเต็มรูปแบบ:

- **ทดลองใช้ฟรี** – ดาวน์โหลดจาก [GroupDocs Release Page](https://releases.groupdocs.com/viewer/java/).  
- **ไลเซนส์ชั่วคราว** – ขอได้ที่ [GroupDocs Temporary License Page](https://purchase.groupdocs.com/temporary-license/).  
- **ซื้อ** – รับไลเซนส์ถาวรผ่าน [GroupDocs Purchase Page](https://purchase.groupdocs.com/buy).

## การตั้งค่า GroupDocs.Viewer สำหรับ Java

Viewer เป็นคลาสหลักที่โหลดเอกสารและให้เมธอดการเรนเดอร์สำหรับรูปแบบผลลัพธ์ที่รองรับทั้งหมด.

### การติดตั้งด้วย Maven
ส่วนโค้ด Maven ด้านบนจะดึง JAR ที่จำเป็นทั้งหมดโดยอัตโนมัติ เพียงรัน `mvn clean install` หลังจากบันทึกไฟล์.

### การเริ่มต้นไลเซนส์
`Viewer` เป็นคลาสหลักที่โหลดเอกสารและให้เมธอดการเรนเดอร์สำหรับรูปแบบผลลัพธ์ที่รองรับทั้งหมด เริ่มต้นไลเซนส์ของคุณก่อนทำการเรนเดอร์เอกสารใด ๆ:

```java
import com.groupdocs.viewer.License;

License lic = new License();
lic.setLicense("path/to/your/license/file.lic");
```

## คู่มือการใช้งาน

ด้านล่างนี้คุณจะพบตัวอย่างขั้นตอนต่อขั้นตอนสำหรับแต่ละรูปแบบผลลัพธ์ โค้ดบล็อกเป็นสำเนาตรงจากบทแนะนำต้นฉบับ; เราเพียงเพิ่มข้อความอธิบายรอบ ๆ เท่านั้น.

### วิธีแปลง cdr เป็น html ด้วย GroupDocs.Viewer

โหลดไฟล์ CDR แล้วเรียก API การเรนเดอร์ HTML – นั่นคือทั้งหมดที่คุณต้องการเพื่อสร้างมาร์กอัปที่พร้อมใช้งานบนเว็บ กระบวนการต้องตั้งค่าเส้นทางไฟล์, สร้างอินสแตนซ์ `HtmlViewOptions`, และเรียก `viewer.view()` รูปแบบสองขั้นตอนนี้ทำงานกับเอกสารขนาดใดก็ได้และรักษาความแม่นยำของเวกเตอร์ไว้.

#### การแปลงเอกสาร cdr เป็น HTML
**ภาพรวม:** แปลงไฟล์ CDR ของคุณเป็น HTML ที่เหมาะกับเว็บเพื่อการแชร์ที่ง่าย.

**ขั้นตอนที่ 1 – ตั้งค่าเส้นทางไฟล์**

```java
import java.nio.file.Path;

Path outputDirectory = TestFiles.getOutputDirectoryPath("RenderingCdr");
Path pageFilePathFormat = outputDirectory.resolve("cdr_result_{0}.html");
```

**ขั้นตอนที่ 2 – เริ่มต้น viewer และเรนเดอร์**

HtmlViewOptions กำหนดค่าการเรนเดอร์ HTML, ให้คุณฝังทรัพยากรหรือบันทึกแยกต่างหาก โค้ดต่อไปนี้เรนเดอร์แต่ละหน้าเป็นไฟล์ HTML แยกกันพร้อมฝังรูปภาพเป็นสตริง Base64.

```java
import com.groupdocs.viewer.Viewer;

try (Viewer viewer = new Viewer(TestFiles.SAMPLE_CDR)) {
    HtmlViewOptions options = HtmlViewOptions.forEmbeddedResources(pageFilePathFormat);
    viewer.view(options); // Render the document into HTML format
}
```

### วิธีแปลง cdr เป็น jpg ด้วย GroupDocs.Viewer

คุณสามารถสร้างภาพ JPEG คุณภาพสูงจากแหล่ง CDR ได้ด้วยเพียงสองบรรทัดโค้ด ก่อนอื่นกำหนดค่า `JpgViewOptions` ด้วยคุณภาพที่ต้องการ แล้วเรียก `viewer.view()` วิธีนี้เหมาะสำหรับรูปภาพขนาดย่อ, แนบอีเมล, หรือสถานการณ์ใด ๆ ที่ต้องการภาพแรสเตอร์ขนาดกะทัดรัด.

#### การแปลงเอกสาร cdr เป็น JPG
**ภาพรวม:** สร้างภาพ JPEG คุณภาพสูงจากแหล่ง CDR ของคุณ.

**ขั้นตอนที่ 1 – ตั้งค่าเส้นทางไฟล์**

```java
Path pageFilePathFormat = outputDirectory.resolve("cdr_result_{0}.jpg");
```

**ขั้นตอนที่ 2 – เริ่มต้น viewer และเรนเดอร์**

JpgViewOptions กำหนดการตั้งค่าการเรนเดอร์ JPEG เช่น คุณภาพการบีบอัดและการตั้งชื่อไฟล์ ตัวอย่างด้านล่างบันทึกแต่ละหน้าเป็นไฟล์ JPEG แยกกัน.

```java
import com.groupdocs.viewer.options.JpgViewOptions;

try (Viewer viewer = new Viewer(TestFiles.SAMPLE_CDR)) {
    JpgViewOptions options = new JpgViewOptions(pageFilePathFormat);
    viewer.view(options); // Render the document into JPG format
}
```

### วิธีแปลง cdr เป็น png ด้วย GroupDocs.Viewer

ผลลัพธ์ PNG ให้คุณได้ภาพแรสเตอร์แบบไม่มีการสูญเสีย เหมาะสำหรับการเก็บถาวรหรือการประมวลผลกราฟิกต่อไป ใช้ `PngViewOptions` เพื่อรักษาพิกเซลทุกพิกเซลไว้ครบ แล้วเรนเดอร์เอกสารหน้าโดยหน้า.

#### การแปลงเอกสาร cdr เป็น PNG
**ภาพรวม:** สร้างภาพ PNG แบบไม่มีการสูญเสียสำหรับการเก็บถาวรหรือการออกแบบ.

**ขั้นตอนที่ 1 – ตั้งค่าเส้นทางไฟล์**

```java
Path pageFilePathFormat = outputDirectory.resolve("cdr_result_{0}.png");
```

**ขั้นตอนที่ 2 – เริ่มต้น viewer และเรนเดอร์**

PngViewOptions ระบุพารามิเตอร์การเรนเดอร์ PNG รวมถึงการสนับสนุนพื้นหลังโปร่งใส โค้ดจะสร้าง PNG ต่อหน้าโดยอัตโนมัติ.

```java
import com.groupdocs.viewer.options.PngViewOptions;

try (Viewer viewer = new Viewer(TestFiles.SAMPLE_CDR)) {
    PngViewOptions options = new PngViewOptions(pageFilePathFormat);
    viewer.view(options); // Render the document into PNG format
}
```

### วิธีแปลง cdr เป็น pdf ด้วย GroupDocs.Viewer

การแปลงไฟล์ CDR เป็น PDF ให้คุณได้เอกสารที่อ่านได้ทั่วโลกและพร้อมพิมพ์ `PdfViewOptions` จัดการการแปลงจากเวกเตอร์เป็นแรสเตอร์ภายใน, รักษาเลย์เอาต์และฟอนต์โดยไม่ต้องใช้ Adobe Illustrator.

#### การแปลงเอกสาร cdr เป็น PDF
**ภาพรวม:** แปลงไฟล์ CDR ของคุณเป็น PDF ที่อ่านได้ทั่วโลก.

**ขั้นตอนที่ 1 – ตั้งค่าเส้นทางไฟล์**

```java
Path pageFilePathFormat = outputDirectory.resolve("cdr_result.pdf");
```

**ขั้นตอนที่ 2 – เริ่มต้น viewer และเรนเดอร์**

PdfViewOptions ควบคุมการสร้าง PDF, เปิดใช้งานการฝังฟอนต์และการปรับแต่งเลย์เอาต์ของหน้า โค้ดตัวอย่างสร้าง PDF ไฟล์เดียวที่รวมทุกหน้า.

```java
import com.groupdocs.viewer.options.PdfViewOptions;

try (Viewer viewer = new Viewer(TestFiles.SAMPLE_CDR)) {
    PdfViewOptions options = new PdfViewOptions(pageFilePathFormat);
    viewer.view(options); // Render the document into PDF format
}
```

## การประยุกต์ใช้งานจริง

- **พอร์ทัลเว็บ:** ใช้การแปลงเป็น HTML เพื่อฝังการออกแบบ CDR โดยตรงบนเว็บไซต์ของคุณ.  
- **แกลเลอรีภาพ:** ใช้ผลลัพธ์ JPG/PNG สำหรับแกลเลอรีที่โหลดเร็วหรือแคตาล็อกสินค้า.  
- **การแชร์เอกสาร:** ให้ PDF แก่ลูกค้าที่ต้องการเวอร์ชันที่พิมพ์ได้และอ่านอย่างเดียว.  
- **การเก็บถาวร:** เก็บหลายรูปแบบเพื่อรับประกันการเข้าถึงในอนาคตโดยไม่คำนึงถึงการเปลี่ยนแปลงซอฟต์แวร์.  
- **การบูรณาการข้ามแพลตฟอร์ม:** ส่งไฟล์ที่สร้างไปยังบริการต่อเนื่องเช่น OCR, การวิเคราะห์, หรือระบบจัดการสินทรัพย์ดิจิทัล.

## ข้อควรพิจารณาด้านประสิทธิภาพ

- **ทำลายอินสแตนซ์ Viewer** อย่างทันท่วงที (ตามที่แสดงด้วย try‑with‑resources) เพื่อคืนหน่วยความจำ.  
- **การประมวลผลเป็นชุด:** วนลูปไฟล์ CDR ด้วยการตั้งค่า Viewer เดียวกันเพื่อลดภาระ.  
- **การจัดสรรทรัพยากร:** GroupDocs.Viewer สามารถเรนเดอร์เอกสารได้ถึง 500 หน้าโดยไม่ต้องโหลดไฟล์ทั้งหมดเข้าสู่หน่วยความจำ แต่ภาพวาดที่ซับซ้อนมากอาจต้องเพิ่มขนาด heap. ควรตรวจสอบการใช้ CPU และ RAM ระหว่างการแปลงขนาดใหญ่.

## ข้อผิดพลาดทั่วไปและเคล็ดลับการแก้ปัญหา

- **ฟอนต์หาย:** หากผลลัพธ์ดูแตกต่าง ให้ตรวจสอบว่าฟอนต์ที่ต้องการมีบนเซิร์ฟเวอร์หรือฝังผ่าน `PdfViewOptions`.  
- **ไฟล์ขนาดใหญ่:** สำหรับไฟล์ CDR ที่เกิน 200 MB ควรประมวลผลหน้า‑ต่อหน้าเพื่อหลีกเลี่ยง `OutOfMemoryError`.  
- **คุณภาพภาพไม่ถูกต้อง:** ปรับค่า `setQuality` ใน `JpgViewOptions` หาก JPEG ดูบีบอัดเกินไป.  
- **ข้อผิดพลาดไลเซนส์:** ตรวจสอบว่าเส้นทางไฟล์ไลเซนส์ถูกต้องและเวอร์ชันไลเซนส์ตรงกับเวอร์ชันของไลบรารี Viewer ของคุณ.

## สรุป

เราได้แสดงวิธี **แปลง cdr เป็น html**, รวมถึง JPG, PNG, และ PDF ด้วย GroupDocs.Viewer สำหรับ Java โดยการทำตามโค้ดสั้น ๆ และเคล็ดลับการปฏิบัติที่ดีที่สุด คุณสามารถฝังการแปลงเหล่านี้เข้าไปในกระบวนการทำงานใด ๆ ที่ใช้ Java ได้, มอบผลลัพธ์ที่ยืดหยุ่นและคุณภาพสูงให้กับผู้ใช้ของคุณ.

### ขั้นตอนต่อไป
- ทดลองใช้ตัวเลือกการเรนเดอร์ขั้นสูงเช่นขนาดหน้าที่กำหนดเองหรือวอเตอร์มาร์ค.  
- รวมกระบวนการแปลงกับ REST API เพื่อให้บริการแปลงไฟล์ตามความต้องการ.  
- เข้าร่วมชุมชนและถามคำถามใน [GroupDocs Forum](https://forum.groupdocs.com/c/viewer).

## คำถามที่พบบ่อย

**Q: Can I convert password‑protected CDR files?**  
A: Yes. Load the file with a `Viewer` instance that accepts a password parameter (see the API docs).  

**Q: Is there a limit on the number of pages that can be converted at once?**  
A: No hard limit, but very large files may require more memory; consider processing page‑by‑page.  

**Q: Does the HTML output include embedded fonts?**  
A: When using `HtmlViewOptions.forEmbeddedResources`, fonts are embedded as Base64, ensuring consistent rendering across browsers.  

**Q: How do I control JPEG quality?**  
A: `JpgViewOptions` provides a `setQuality(int)` method where you can specify a value from 1‑100.  

**Q: Can I convert CDR files on a Linux server?**  
A: Absolutely—GroupDocs.Viewer is platform‑agnostic as long as the JDK is installed.  

---

**อัปเดตล่าสุด:** 2026-08-19  
**ทดสอบกับ:** GroupDocs.Viewer 25.2 for Java  
**ผู้เขียน:** GroupDocs

## บทแนะนำที่เกี่ยวข้อง

- [วิธีแปลง Excel เป็น HTML, JPG, PNG, และ PDF ด้วย GroupDocs.Viewer Java](/viewer/java/rendering-basics/groupdocs-viewer-java-excel-to-html-jpg-png-pdf/)
- [วิธีแปลง CF2 เป็น PDF, HTML, JPG, PNG ด้วย GroupDocs.Viewer สำหรับ Java](/viewer/java/rendering-basics/render-cf2-files-groupdocs-java/)
- [วิธีแปลง pdf เป็น html และปรับคุณภาพภาพใน Java ด้วย GroupDocs.Viewer](/viewer/java/advanced-rendering/adjust-image-quality-groupdocs-viewer-java/)