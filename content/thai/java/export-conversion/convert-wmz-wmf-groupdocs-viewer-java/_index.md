---
date: '2026-02-18'
description: เรียนรู้วิธีแปลงไฟล์ WMZ และ WMF เป็น PDF, HTML, JPG และ PNG ด้วย GroupDocs
  Viewer สำหรับ Java คู่มือนี้ครอบคลุม GroupDocs Viewer Java และการแปลงกราฟิกเวกเตอร์ด้วย
  Java
keywords:
- convert WMZ/WMF documents
- GroupDocs Viewer for Java
- rendering formats
title: วิธีแปลง WMZ เป็น PDF และรูปแบบอื่น ๆ ด้วย GroupDocs Viewer สำหรับ Java
type: docs
url: /th/java/export-conversion/convert-wmz-wmf-groupdocs-viewer-java/
weight: 1
---

 => same.

"**Tested With:** GroupDocs.Viewer 25.2 for Java" => same.

"**Author:** GroupDocs" => same.

Now ensure we preserve markdown formatting.

Also note bullet list items need to keep bold formatting.

Now produce final content.# วิธีแปลง WMZ เป็น PDF และรูปแบบอื่น ๆ ด้วย GroupDocs Viewer สำหรับ Java

การแปลงไฟล์ WMZ (Web Metafile) และ WMF (Windows Metafile) ให้เป็นรูปแบบที่เข้าถึงได้ง่ายขึ้น—โดยเฉพาะ **convert WMZ to PDF**—อาจเป็นเรื่องยากเนื่องจากรูปแบบกราฟิกเวกเตอร์เหล่านี้เก็บคำสั่งการวาดแทนข้อมูลพิกเซล ด้วย **GroupDocs Viewer for Java** คุณสามารถเรนเดอร์เอกสาร WMZ/WMF ไปเป็น HTML, JPG, PNG, **PDF** และรูปแบบยอดนิยมอื่น ๆ ได้เพียงไม่กี่บรรทัดของโค้ด

![แปลงเอกสาร WMZ/WMF ด้วย GroupDocs.Viewer สำหรับ Java](/viewer/export-conversion/convert-wmz-wmf-documents.png)

ในบทแนะนำนี้คุณจะได้เรียนรู้วิธีตั้งค่าห้องสมุด, เรนเดอร์ไฟล์ WMZ/WMF ไปยังผลลัพธ์ที่ต้องการ, และจัดการกับข้อผิดพลาดทั่วไป เมื่อเสร็จสิ้นคุณจะสามารถรวม **groupdocs viewer java** เข้าในแอปพลิเคชัน Java ของคุณเพื่อ **java convert vector graphics** อย่างรวดเร็วและเชื่อถือได้

## คำตอบอย่างรวดเร็ว
- **รูปแบบใดบ้างที่ WMZ/WMF สามารถแปลงได้?** HTML, JPG, PNG, และ PDF รองรับเต็มรูปแบบ.  
- **ฉันต้องการไลเซนส์สำหรับการพัฒนาหรือไม่?** การทดลองใช้ฟรีทำงานสำหรับการทดสอบ; ไลเซนส์เชิงพาณิชย์จะลบข้อจำกัดการประเมิน.  
- **ต้องการเวอร์ชัน Java ใด?** แนะนำให้ใช้ Java 8 หรือใหม่กว่า.  
- **ฉันสามารถเรนเดอร์เฉพาะหน้าที่ต้องการได้หรือไม่?** ได้, คุณสามารถระบุช่วงหน้าในตัวเลือกการดูได้.  
- **การใช้หน่วยความจำเป็นปัญหาสำหรับไฟล์ขนาดใหญ่หรือไม่?** ใช้ try‑with‑resources และเรนเดอร์เฉพาะหน้าที่ต้องการเพื่อรักษาหน่วยความจำให้ต่ำ.

## “convert WMZ to PDF” คืออะไร
การแปลง WMZ เป็น PDF หมายถึงการนำไฟล์ WMZ แบบเวกเตอร์มาราสเตอร์ (หรือรักษาข้อมูลเวกเตอร์) ภายในคอนเทนเนอร์ PDF. PDF สามารถดูได้ทั่วโลก, ค้นหาได้, และพิมพ์ได้, ทำให้เหมาะสำหรับการเก็บถาวรและแชร์กราฟิก WMZ

## ทำไมต้องใช้ GroupDocs Viewer สำหรับ Java เพื่อแปลงกราฟิกเวกเตอร์?
- **ความแม่นยำสูง**: ห้องสมุดรักษาคุณภาพการวาดต้นฉบับ ไม่ว่าจะส่งออกเป็น PDF หรือ PNG.  
- **ไม่มีการพึ่งพาภายนอก**: ไม่ต้องการไลบรารี Windows แบบเนทีฟ; ทุกอย่างทำงานบนแพลตฟอร์มใดก็ได้ที่มี JDK.  
- **API ง่าย**: อินสแตนซ์ `Viewer` เพียงหนึ่งตัวและการเรียก `view` ครั้งเดียวจัดการการแปลงทั้งหมด.  
- **ขยายได้**: ทำงานได้ดีเท่าเทียมสำหรับไอคอนหน้าเดียวและภาพวาดเทคนิคหลายหน้า.

## ข้อกำหนดเบื้องต้น

### ไลบรารีที่จำเป็น
- **GroupDocs.Viewer for Java** – ตัวเอนจินการเรนเดอร์หลัก.  
- Java Development Kit (JDK) 8+.

### การตั้งค่าสภาพแวดล้อม
- IDE เช่น IntelliJ IDEA หรือ Eclipse.  
- Maven สำหรับการจัดการ dependencies (หรือ Gradle หากคุณต้องการ).

### ความรู้ที่จำเป็น
- ความคุ้นเคยกับ Java file I/O (`java.nio.file.Path`).  
- ความเข้าใจพื้นฐานเกี่ยวกับวิธีที่ตัวดูเอกสารเรนเดอร์เนื้อหา.

## การตั้งค่า GroupDocs.Viewer สำหรับ Java

เพิ่ม repository และ dependency ลงใน `pom.xml` ของคุณ:

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

> **เคล็ดลับไลเซนส์:** ใช้การทดลองฟรีสำหรับการประเมิน, จากนั้นใช้ไลเซนส์ชั่วคราวหรือที่ซื้อเพื่อเปิดใช้งานฟังก์ชันเต็ม.

เมื่อ dependency ถูกแก้ไขแล้ว, คุณสามารถสร้างอินสแตนซ์ `Viewer` ที่จะถูกใช้ซ้ำสำหรับแต่ละขั้นตอนการแปลง

## คู่มือการใช้งาน

เราจะเดินผ่านสี่สถานการณ์การแปลง: HTML, JPG, PNG, และ PDF. ตัวอย่างแต่ละอันใช้รูปแบบเดียวกัน—กำหนดเส้นทางเอาต์พุต, สร้างอินสแตนซ์ `Viewer` ด้วยไฟล์ WMZ ต้นฉบับ, ตั้งค่าตัวเลือกการดูที่เหมาะสม, และเรียก `view`.

### การเรนเดอร์ WMZ/WMF เป็น HTML

#### ภาพรวม
ผลลัพธ์ HTML ช่วยให้คุณฝังกราฟิกโดยตรงในหน้าเว็บ, โดยมีทรัพยากรทั้งหมด (รูปภาพ, CSS) อยู่ในไฟล์เดียว.

**ขั้นตอนที่ 1: กำหนดเส้นทางไดเรกทอรีเอาต์พุต**

```java
Path outputDirectory = Utils.getOutputDirectoryPath("RenderingWmzAndWmf");
Path pageFilePathFormat = outputDirectory.resolve("wmz_result.html");
```

**ขั้นตอนที่ 2: เริ่มต้น Viewer และเรนเดอร์เป็น HTML**

```java
try (Viewer viewer = new Viewer(TestFiles.SAMPLE_WMZ)) {
    // Create options that embed all resources inside the HTML file
    HtmlViewOptions options = HtmlViewOptions.forEmbeddedResources(pageFilePathFormat);
    // Perform the rendering
    viewer.view(options);
}
```

### การเรนเดอร์ WMZ/WMF เป็น JPG

#### ภาพรวม
JPG เป็นรูปแบบราสเตอร์ที่ได้รับการสนับสนุนอย่างกว้างขวาง, เหมาะสำหรับการพรีวิวอย่างรวดเร็วหรือแนบอีเมล.

**ขั้นตอนที่ 1: กำหนดเส้นทางไดเรกทอรีเอาต์พุต**

```java
Path outputDirectory = Utils.getOutputDirectoryPath("RenderingWmzAndWmf");
Path pageFilePathFormat = outputDirectory.resolve("wmz_result.jpg");
```

**ขั้นตอนที่ 2: เริ่มต้น Viewer และเรนเดอร์เป็น JPG**

```java
try (Viewer viewer = new Viewer(TestFiles.SAMPLE_WMZ)) {
    JpgViewOptions options = new JpgViewOptions(pageFilePathFormat);
    viewer.view(options);
}
```

### การเรนเดอร์ WMZ/WMF เป็น PNG

#### ภาพรวม
PNG รองรับความโปร่งใส, ทำให้เหมาะสำหรับกราฟิกที่ต้องการผสมกับพื้นหลังต่าง ๆ.

**ขั้นตอนที่ 1: กำหนดเส้นทางไดเรกทอรีเอาต์พุต**

```java
Path outputDirectory = Utils.getOutputDirectoryPath("RenderingWmzAndWmf");
Path pageFilePathFormat = outputDirectory.resolve("wmz_result.png");
```

**ขั้นตอนที่ 2: เริ่มต้น Viewer และเรนเดอร์เป็น PNG**

```java
try (Viewer viewer = new Viewer(TestFiles.SAMPLE_WMZ)) {
    PngViewOptions options = new PngViewOptions(pageFilePathFormat);
    viewer.view(options);
}
```

### การเรนเดอร์ WMZ/WMF เป็น PDF

#### ภาพรวม
PDF ให้เอกสารที่ไม่ขึ้นกับแพลตฟอร์ม, ค้นหาได้, และรักษาเลย์เอาต์ต้นฉบับ.

**ขั้นตอนที่ 1: กำหนดเส้นทางไดเรกทอรีเอาต์พุต**

```java
Path outputDirectory = Utils.getOutputDirectoryPath("RenderingWmzAndWmf");
Path pageFilePathFormat = outputDirectory.resolve("wmz_result.pdf");
```

**ขั้นตอนที่ 2: เริ่มต้น Viewer และเรนเดอร์เป็น PDF**

```java
try (Viewer viewer = new Viewer(TestFiles.SAMPLE_WMZ)) {
    PdfViewOptions options = new PdfViewOptions(pageFilePathFormat);
    viewer.view(options);
}
```

## ปัญหาและวิธีแก้ไขทั่วไป

| ปัญหา | สาเหตุ | วิธีแก้ |
|-------|-------|----------|
| **OutOfMemoryError** บนไฟล์ WMZ ขนาดใหญ่ | Viewer โหลดเอกสารทั้งหมดเข้าสู่หน่วยความจำ | เรนเดอร์หนึ่งหน้าต่อครั้งโดยใช้ `PageStreamViewOptions` หรือเพิ่ม heap ของ JVM (`-Xmx`). |
| **Missing fonts** ใน PDF | ฟอนต์ไม่ได้ฝังใน WMZ ต้นฉบับ | ติดตั้งฟอนต์ที่ต้องการบนเครื่องโฮสต์หรือใช้ `FontSettings` เพื่อจัดหาฟอนต์แบบกำหนดเอง. |
| **Blank PNG output** | เส้นทางเอาต์พุตไม่ถูกต้องหรือไม่มีสิทธิ์เขียนเพียงพอ | ตรวจสอบว่า `outputDirectory` มีอยู่และแอปพลิเคชันมีสิทธิ์เขียน. |
| **HTML resources not loading** | ใช้ `forExternalResources` โดยไม่ได้คัดลอกไฟล์ | ใช้ `forEmbeddedResources` เพื่อให้ไฟล์ HTML มีทุกอย่างในตัว. |

## คำถามที่พบบ่อย

**ถาม: ฉันสามารถแปลง WMF เป็น PNG ด้วยโค้ดเดียวกันได้หรือไม่?**  
ตอบ: ใช่. ตัวอย่าง PNG ทำงานได้ทั้งไฟล์ WMZ และ WMF; เพียงเปลี่ยน `TestFiles.SAMPLE_WMZ` เป็นแหล่ง WMF ของคุณ.

**ถาม: สามารถแปลงเฉพาะส่วนของหน้าได้หรือไม่?**  
ตอบ: แน่นอน. ใช้ `PdfViewOptions` (หรือออปชันที่สอดคล้องสำหรับรูปแบบอื่น) และเรียก `setPageNumbers(List<Integer>)` ก่อนการเรนเดอร์.

**ถาม: ฉันต้องการไลเซนส์แยกสำหรับแต่ละรูปแบบเอาต์พุตหรือไม่?**  
ตอบ: ไม่. ไลเซนส์ GroupDocs Viewer เพียงหนึ่งใบครอบคลุมรูปแบบที่รองรับทั้งหมด รวมถึง HTML, JPG, PNG, และ PDF.

**ถาม: “java convert vector graphics” มีผลต่อประสิทธิภาพอย่างไร?**  
ตอบ: การแปลงเวกเตอร์เป็นราสเตอร์ต้องใช้ CPU มาก. สำหรับชุดงานขนาดใหญ่, พิจารณาใช้ multi‑threading และใช้อินสแตนซ์ `Viewer` เดียวซ้ำหลายไฟล์.

**ถาม: PDF จะรักษาคุณภาพเวกเตอร์หรือจะถูกราสเตอร์?**  
ตอบ: เมื่อแปลง WMZ/WMF เป็น PDF, GroupDocs Viewer จะรักษาคำสั่งเวกเตอร์เมื่อเป็นไปได้, ทำให้ได้ PDF ที่ขยายได้.

## สรุป

ตอนนี้คุณมีคู่มือครบถ้วนพร้อมใช้งานในขั้นตอนการผลิตเพื่อ **convert WMZ to PDF** และรูปแบบทั่วไปอื่น ๆ ด้วย **GroupDocs Viewer for Java**. ไม่ว่าคุณจะสร้างเว็บเซอร์วิสที่ให้บริการกราฟิกแบบเรียลไทม์หรือเครื่องมือเก็บถาวรที่จัดเก็บเอกสารเป็น PDF, ขั้นตอนข้างต้นจะช่วยให้คุณทำได้อย่างรวดเร็ว

---

**Last Updated:** 2026-02-18  
**Tested With:** GroupDocs.Viewer 25.2 for Java  
**Author:** GroupDocs