---
date: '2026-02-28'
description: เรียนรู้วิธีแปลงไฟล์ CDR เป็น HTML, JPG, PNG และ PDF ด้วย GroupDocs.Viewer
  สำหรับ Java รวมถึงการตั้งค่า ตัวอย่างโค้ด และเคล็ดลับการเพิ่มประสิทธิภาพ
keywords:
- render CDR files
- GroupDocs.Viewer Java
- HTML conversion
title: แปลง cdr เป็น html, jpg, png, pdf ด้วย GroupDocs.Viewer Java
type: docs
url: /th/java/file-formats-support/render-cdr-documents-groupdocs-viewer-java-guide/
weight: 1
---

# แปลง cdr เป็น html, jpg, png, pdf ด้วย GroupDocs.Viewer Java

หากคุณต้องการ **แปลง CDR เป็น HTML** (หรือเป็น JPG, PNG, และ PDF) อย่างรวดเร็วและเชื่อถือได้ คุณมาถูกที่แล้วในบทเรียนนี้ เราจะพาคุณผ่านทุกขั้นตอนที่จำเป็น—from การติดตั้ง GroupDocs.Viewer สำหรับ Java ไปจนถึงการแสดงผลไฟล์ CorelDRAW (CDR) เป็นหน้า HTML ที่เหมาะกับเว็บ, ภาพคุณภาพสูง, และ PDF ที่อ่านได้ทั่วทุกแพลตฟอร์ม เมื่อเสร็จสิ้นคุณจะสามารถรวมการแปลงเหล่านี้เข้าไปในแอปพลิเคชัน Java ใดก็ได้ด้วยเพียงไม่กี่บรรทัดของโค้ด

![เรนเดอร์ไฟล์ CDR ด้วย GroupDocs.Viewer for Java](/viewer/file-formats-support/render-cdr-files.png)

## Quick Answers
- **ไลบรารีที่แปลง CDR เป็น HTML คืออะไร?** GroupDocs.Viewer for Java.  
- **ฉันสามารถแปลง CDR เป็น JPG, PNG, และ PDF ได้หรือไม่?** ได้—ใช้ Viewer API เดียวกันกับตัวเลือกการแสดงผลที่แตกต่างกัน.  
- **ต้องมีลิขสิทธิ์หรือไม่?** ลิขสิทธิ์ทดลองหรือชั่วคราวใช้ได้สำหรับการทดสอบ; ต้องมีลิขสิทธิ์เต็มสำหรับการใช้งานจริง.  
- **ต้องใช้ Java เวอร์ชันใด?** JDK 8 หรือใหม่กว่า.  
- **รองรับการแปลงเป็นชุดหรือไม่?** แน่นอน—เพียงวนลูปไฟล์ด้วย Viewer อินสแตนซ์เดียวกัน.

## What is “convert CDR to HTML”?
การแปลง CDR เป็น HTML หมายถึงการเปลี่ยนไฟล์เวกเตอร์ CorelDRAW ให้เป็นโค้ด HTML มาตรฐาน พร้อมฝังรูปภาพและสไตล์เพื่อให้การออกแบบสามารถดูได้โดยตรงในเว็บเบราว์เซอร์โดยไม่ต้องใช้ซอฟต์แวร์ออกแบบเดิม

## Why convert CDR to HTML, JPG, PNG, or PDF?
- **HTML** ช่วยให้คุณฝังกราฟิกในพอร์ทัลเว็บและแชร์ได้ทันที.  
- **JPG** และ **PNG** ให้ภาพราสเตอร์สำหรับแกลเลอรี, รูปย่อ, หรือแนบอีเมล.  
- **PDF** ให้เวอร์ชันที่พิมพ์ได้และเป็นอิสระจากแพลตฟอร์มสำหรับการเก็บถาวรหรือระบบแชร์เอกสาร.  

การมีสี่รูปแบบพร้อมใช้งานทำให้คุณสามารถให้ไฟล์ที่เหมาะสมกับผู้ใช้แต่ละประเภท, ปรับปรุงประสิทธิภาพ, และทำให้ทรัพย์สินของคุณพร้อมสำหรับอนาคต.

## Prerequisites

ก่อนเริ่มทำตามขั้นตอนต่อไปนี้ให้แน่ใจว่าคุณมี:

1. **ไลบรารีและการพึ่งพา** – GroupDocs.Viewer ถูกเพิ่มเข้าไปในโปรเจกต์ Maven ของคุณ.  
2. **Java Development Kit (JDK)** – เวอร์ชัน 8 หรือใหม่กว่า.  
3. **ความรู้พื้นฐานของ Java** – เพื่อทำความเข้าใจโค้ดตัวอย่าง.

### Required Libraries, Versions, and Dependencies

เพิ่มการกำหนดค่า Maven ต่อไปนี้ในไฟล์ `pom.xml` ของคุณ (ไม่ต้องแก้ไขจากบทเรียนต้นฉบับ):

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

### License Acquisition Steps

GroupDocs.Viewer มีตัวเลือกลิขสิทธิ์ฟรี, ลิขสิทธิ์ชั่วคราวสำหรับการทดสอบ, หรือการซื้อเต็มรูปแบบ:

- **ทดลองใช้ฟรี** – ดาวน์โหลดจาก [หน้ารีลีสของ GroupDocs](https://releases.groupdocs.com/viewer/java/).  
- **ลิขสิทธิ์ชั่วคราว** – ขอรับได้ที่ [หน้าลิขสิทธิ์ชั่วคราวของ GroupDocs](https://purchase.groupdocs.com/temporary-license/).  
- **ซื้อ** – รับลิขสิทธิ์ถาวรผ่าน [หน้าการซื้อของ GroupDocs](https://purchase.groupdocs.com/buy).

## Setting Up GroupDocs.Viewer for Java

### Installation with Maven
สคริปต์ Maven ด้านบนจะดึง JAR ที่จำเป็นทั้งหมดโดยอัตโนมัติ เพียงรัน `mvn clean install` หลังจากบันทึกไฟล์

### License Initialization
กำหนดค่าไลเซนส์ก่อนทำการเรนเดอร์เอกสารใด ๆ:

```java
import com.groupdocs.viewer.License;

License lic = new License();
lic.setLicense("path/to/your/license/file.lic");
```

## Implementation Guide

ด้านล่างนี้เป็นตัวอย่างขั้นตอน‑ต่อ‑ขั้นตอนสำหรับแต่ละรูปแบบผลลัพธ์ โค้ดบล็อกคงเหมือนกับบทเรียนต้นฉบับ; เราเพียงเพิ่มคำอธิบายรอบ ๆ โค้ดเท่านั้น

### How to convert CDR to HTML with GroupDocs.Viewer

#### Rendering CDR Document to HTML
**ภาพรวม:** แปลงไฟล์ CDR ของคุณเป็น HTML ที่เหมาะกับเว็บเพื่อการแชร์ที่ง่าย

**Step 1 – Set Up File Paths**

```java
import java.nio.file.Path;

Path outputDirectory = TestFiles.getOutputDirectoryPath("RenderingCdr");
Path pageFilePathFormat = outputDirectory.resolve("cdr_result_{0}.html");
```

**Step 2 – Initialize Viewer and Render**

```java
import com.groupdocs.viewer.Viewer;

try (Viewer viewer = new Viewer(TestFiles.SAMPLE_CDR)) {
    HtmlViewOptions options = HtmlViewOptions.forEmbeddedResources(pageFilePathFormat);
    viewer.view(options); // Render the document into HTML format
}
```

### How to convert CDR to JPG with GroupDocs.Viewer

#### Rendering CDR Document to JPG
**ภาพรวม:** สร้างภาพ JPEG คุณภาพสูงจากไฟล์ CDR ของคุณ

**Step 1 – Set Up File Paths**

```java
Path pageFilePathFormat = outputDirectory.resolve("cdr_result_{0}.jpg");
```

**Step 2 – Initialize Viewer and Render**

```java
import com.groupdocs.viewer.options.JpgViewOptions;

try (Viewer viewer = new Viewer(TestFiles.SAMPLE_CDR)) {
    JpgViewOptions options = new JpgViewOptions(pageFilePathFormat);
    viewer.view(options); // Render the document into JPG format
}
```

### How to convert CDR to PNG with GroupDocs.Viewer

#### Rendering CDR Document to PNG
**ภาพรวม:** สร้างภาพ PNG แบบไม่มีการสูญเสียคุณภาพสำหรับการเก็บถาวรหรือการออกแบบ

**Step 1 – Set Up File Paths**

```java
Path pageFilePathFormat = outputDirectory.resolve("cdr_result_{0}.png");
```

**Step 2 – Initialize Viewer and Render**

```java
import com.groupdocs.viewer.options.PngViewOptions;

try (Viewer viewer = new Viewer(TestFiles.SAMPLE_CDR)) {
    PngViewOptions options = new PngViewOptions(pageFilePathFormat);
    viewer.view(options); // Render the document into PNG format
}
```

### How to convert CDR to PDF with GroupDocs.Viewer

#### Rendering CDR Document to PDF
**ภาพรวม:** แปลงไฟล์ CDR ของคุณเป็น PDF ที่อ่านได้ทั่วทุกแพลตฟอร์ม

**Step 1 – Set Up File Paths**

```java
Path pageFilePathFormat = outputDirectory.resolve("cdr_result.pdf");
```

**Step 2 – Initialize Viewer and Render**

```java
import com.groupdocs.viewer.options.PdfViewOptions;

try (Viewer viewer = new Viewer(TestFiles.SAMPLE_CDR)) {
    PdfViewOptions options = new PdfViewOptions(pageFilePathFormat);
    viewer.view(options); // Render the document into PDF format
}
```

## Practical Applications

- **พอร์ทัลเว็บ:** ใช้การแปลงเป็น HTML เพื่อฝังการออกแบบ CDR ลงในเว็บไซต์ของคุณโดยตรง.  
- **แกลเลอรีภาพ:** นำผลลัพธ์ JPG/PNG ไปใช้ในแกลเลอรีที่โหลดเร็ว.  
- **การแชร์เอกสาร:** ให้ PDF แก่ลูกค้าที่ต้องการไฟล์ที่พิมพ์ได้และอ่าน‑อย่างเดียว.  
- **การเก็บถาวร:** เก็บหลายรูปแบบเพื่อรับประกันการเข้าถึงในอนาคต.  
- **การบูรณาการข้ามแพลตฟอร์ม:** ส่งไฟล์ที่สร้างขึ้นไปยังบริการอื่น ๆ (เช่น OCR, analytics).

## Performance Considerations

- **ปลดปล่อยอินสแตนซ์ Viewer** อย่างทันท่วงที (ตามตัวอย่างด้วย try‑with‑resources) เพื่อคืนหน่วยความจำ.  
- **การประมวลผลเป็นชุด:** วนลูปไฟล์ CDR หลายไฟล์โดยใช้การตั้งค่า Viewer เดียวกันเพื่อลดภาระ.  
- **การจัดสรรทรัพยากร:** จัดสรร CPU/RAM เพียงพอสำหรับไฟล์ CDR ขนาดใหญ่หรือซับซ้อน; เครื่องมือมอนิเตอร์ช่วยปรับจูนได้.

## Conclusion

เราได้แสดงวิธี **แปลง CDR เป็น HTML**, รวมถึง JPG, PNG, และ PDF ด้วย GroupDocs.Viewer สำหรับ Java ด้วยการใช้โค้ดสั้น ๆ และเคล็ดลับการปฏิบัติที่ดีที่สุด คุณจึงสามารถรวมการแปลงเหล่านี้เข้าไปในกระบวนการทำงานใด ๆ ที่ใช้ Java ได้อย่างยืดหยุ่นและได้ผลลัพธ์คุณภาพสูง

### Next Steps
- ทดลองใช้ตัวเลือกการเรนเดอร์ขั้นสูง เช่น ขนาดหน้าที่กำหนดเองหรือวอเตอร์มาร์ค.  
- ผสานท่อการแปลงกับ REST API เพื่อให้บริการแปลงไฟล์ตามความต้องการ.  
- เข้าร่วมชุมชนและตั้งคำถามใน [ฟอรั่มของ GroupDocs](https://forum.groupdocs.com/c/viewer).

## Frequently Asked Questions

**Q: ฉันสามารถแปลงไฟล์ CDR ที่มีการป้องกันด้วยรหัสผ่านได้หรือไม่?**  
A: ได้. โหลดไฟล์ด้วยอินสแตนซ์ `Viewer` ที่รับพารามิเตอร์รหัสผ่าน (ดูเอกสาร API)

**Q: มีขีดจำกัดจำนวนหน้าที่สามารถแปลงได้ในครั้งเดียวหรือไม่?**  
A: ไม่มีขีดจำกัดที่เข้มงวด, แต่ไฟล์ขนาดใหญ่อาจต้องการหน่วยความจำมากขึ้น; ควรพิจารณาการประมวลผลหน้า‑ต่อ‑หน้า

**Q: ผลลัพธ์ HTML มีฝังฟอนต์หรือไม่?**  
A: เมื่อใช้ `HtmlViewOptions.forEmbeddedResources` ฟอนต์จะถูกฝังเป็น Base64 ทำให้การเรนเดอร์คงที่

**Q: ฉันจะควบคุมคุณภาพของ JPEG ได้อย่างไร?**  
A: `JpgViewOptions` มีเมธอด `setQuality(int)` ให้กำหนดค่าตั้งแต่ 1‑100

**Q: ฉันสามารถแปลงไฟล์ CDR บนเซิร์ฟเวอร์ Linux ได้หรือไม่?**  
A: แน่นอน—GroupDocs.Viewer ทำงานได้บนทุกแพลตฟอร์มตราบใดที่ติดตั้ง JDK

**Last Updated:** 2026-02-28  
**Tested With:** GroupDocs.Viewer 25.2 for Java  
**Author:** GroupDocs