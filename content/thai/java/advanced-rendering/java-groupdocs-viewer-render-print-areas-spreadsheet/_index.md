---
date: '2025-12-23'
description: เรียนรู้วิธีสร้างการแสดงตัวอย่างเอกสารใน Java ด้วยการเรนเดอร์พื้นที่พิมพ์ของ
  Excel โดยใช้ GroupDocs.Viewer คู่มือขั้นตอนต่อขั้นตอนสำหรับโซลูชันการแสดงตัวอย่าง
  Java ที่มีประสิทธิภาพ
keywords:
- Java spreadsheet print areas rendering
- rendering print areas with GroupDocs.Viewer for Java
- efficient document preview solutions
title: 'สร้างตัวอย่างเอกสาร Java - แสดงพื้นที่พิมพ์ของสเปรดชีตด้วย GroupDocs.Viewer'
type: docs
url: /th/java/advanced-rendering/java-groupdocs-viewer-render-print-areas-spreadsheet/
weight: 1
---

# สร้างการแสดงตัวอย่างเอกสาร Java: เรนเดอร์พื้นที่พิมพ์ของสเปรดชีตด้วย GroupDocs.Viewer

การเรนเดอร์เฉพาะส่วนพื้นที่พิมพ์ของสเปรดชีตสามารถลดจำนวนข้อมูลที่ผู้ใช้ต้องสแกนได้อย่างมาก ทำให้การแสดงตัวอย่างเอกสารเร็วขึ้นและโฟกัสมากขึ้น ในคู่มือนี้คุณจะ **create document preview java** โครงการที่เรนเดอร์เฉพาะพื้นที่พิมพ์ที่กำหนดไว้โดยใช้ **GroupDocs.Viewer for Java** เราจะพาคุณผ่านขั้นตอนการตั้งค่า การกำหนดค่า และการใช้งานจริง เพื่อให้คุณสามารถเพิ่มความสามารถนี้ให้กับแอปพลิเคชันของคุณได้อย่างรวดเร็ว

![การเรนเดอร์พื้นที่พิมพ์ของสเปรดชีตด้วย GroupDocs.Viewer for Java](/viewer/advanced-rendering/spreadsheet-print-areas-rendering-java.png)

## คำตอบด่วน
- **“สร้างเอกสารแสดงตัวอย่าง java” วิธีการอะไร?** การรักษาคุณภาพของภาพ (HTML, รูปภาพ, PDF) ของเอกสารขนมปังโค้ด Java
- **ทำไมต้องเรนเดอร์เฉพาะพื้นที่พิมพ์ของ Excel?** เนื่องจากช่วยแยกข้อมูลเพิกถอนเวลาเรนเดอร์และแบนด์วิดท์
- **ต้องมีลิขสิทธิ์เพื่อทดลองหรือไม่?** ประกอบด้วยส่วนประกอบฟรีหรือเป็นเพียงส่วนหนึ่งได้; เพื่อที่จะซื้อเต็มรูปแบบเพื่อใช้งานในโปรดักชัน
- ** รองรับรองรับ Java ใด ๆ ?** Java8 หรือใหม่กว่า
- **สามารถฝังการแสดงตัวอย่างในการควบคุมได้หรือไม่** — ใช้ `embedded‑resources` เพื่อให้หน้า HTML เป็นไฟล์ครบทุกอย่างได้

## “สร้าง java ตัวอย่างเอกสาร” อะไร?
การสร้างการแสดงตัวอย่างเอกสารใน Java หมายถึงการแปลงไฟล์ต้นฉบับ (เช่น workbook XLSX) ให้เป็นรูปแบบที่สามารถแสดงในเบราว์เซอร์หรือคอมโพเนนต์ UI อื่น ๆ ได้โดยไม่ต้องเปิดแอปพลิเคชันต้นฉบับ วิธีนี้จำเป็นสำหรับพอร์ทัล อินทราเน็ต และแพลตฟอร์ม SaaS ที่ต้องการแสดงเนื้อหาเอกสารอย่างรวดเร็วและปลอดภัย  

## ทำไมต้องเรนเดอร์เฉพาะพื้นที่พิมพ์ของ Excel?
- **ประสิทธิภาพ:** โหลด HTML ที่มีขนาดเล็กลงทำให้เร็วขึ้น  
- **ความชัดเจน:** ผู้ใช้เห็นเฉพาะส่วนที่กำหนดให้พิมพ์ ไม่ต้องเผชิญกับข้อมูลที่ไม่จำเป็น  
- **ความปลอดภัย:** แผ่นงานที่ไม่ต้องการจะถูกซ่อนจากการแสดงตัวอย่าง  

## Prerequisites
- **GroupDocs.Viewer for Java** v25.2 หรือใหม่กว่า  
- Maven ติดตั้งบนเครื่องพัฒนา  
- JDK 8 หรือใหม่กว่า (แนะนำ Java 11)  
- IDE (IntelliJ IDEA, Eclipse หรือ VS Code)  

## การตั้งค่า GroupDocs.Viewer สำหรับ Java
เพิ่มรีโพสิตอรีของ GroupDocs และ dependency ลงใน `pom.xml` ของคุณ:

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

### การได้มาซึ่งใบอนุญาต
ขั้นตอนที่ **ทดลองใช้ฟรี** หรือขอ **ใบอนุญาตชั่วคราว** เพื่อให้ทราบถึงความพร้อมสำหรับการผลิตเพื่อให้ซื้อได้เต็มเพื่อเปิดใช้งานทั้งหมดและลบข้อจำกัดของเชื้อโรค

### การเริ่มต้นขั้นพื้นฐาน
โค้ดตัวอย่างที่จำเป็นที่สุดสำหรับการเปิดสเปรดชีตด้วย GroupDocs.Viewer มีดังนี้:

```java
import com.groupdocs.viewer.Viewer;

// Initialize Viewer object with the path to your spreadsheet
try (Viewer viewer = new Viewer("path/to/your/spreadsheet.xlsx")) {
    // Further configurations will be discussed in upcoming sections.
}
```

## วิธีสร้าง Java ตัวอย่างเอกสารด้วย GroupDocs.Viewer
เพื่อเป็นขั้นตอนแบบละเอียดที่ **render excel print area** คุณจะต้องใช้ไฟล์ HTML ที่เป็นไฟล์เดียวครบทุกอย่าง

### ขั้นตอนที่ 1: กำหนดไดเร็กทอรีเอาต์พุตและรูปแบบเส้นทางไฟล์
กำหนดตำแหน่งที่ Viewer จะเขียนไฟล์ HTML ที่สร้างขึ้น

```java
import java.nio.file.Path;
import java.nio.file.Paths;

// Set the output directory path
Path outputDirectory = Paths.get("YOUR_OUTPUT_DIRECTORY");

// Define a file path format for the rendered pages
Path pageFilePathFormat = outputDirectory.resolve("page_{0}.html");
```

*Explanation:* `outputDirectory` คือความสามารถในการเก็บไฟล์การแสดงตัวอย่างทั้งหมด `pageFilePathFormat` ใช้ placeholder (`{0}`) ที่ Viewer จะมีความยาวด้วยหมายเลขหน้า

### ขั้นตอนที่ 2: กำหนดค่าตัวเลือกมุมมอง HTML สำหรับการแสดงผลพื้นที่การพิมพ์
ตั้งค่า Viewer ให้ฝังทรัพยากร (CSS, images) โดยตรงและโฟกัสที่พื้นที่พิมพ์ที่กำหนด

```java
import com.groupdocs.viewer.options.HtmlViewOptions;
import com.groupdocs.viewer.options.SpreadsheetOptions;

// Configure HTML view options with embedded resources and print area rendering
HtmlViewOptions viewOptions = HtmlViewOptions.forEmbeddedResources(pageFilePathFormat);
viewOptions.setSpreadsheetOptions(SpreadsheetOptions.forRenderingPrintArea());
```

*Explanation:* `HtmlViewOptions.forEmbeddedResources` สร้างไฟล์ HTML หนึ่งไฟล์ต่อหน้าโดยมี CSS/JS ฝังอยู่ในไฟล์เดียว ทำให้การปรับใช้ง่ายขึ้น `forRenderingPrintArea()` บอก engine ให้ **render excel print area** เท่านั้น  

ขั้นตอนที่ 3: โหลดสเปรดชีตและแสดงผล
สุดท้ายให้ชี้ Viewer ไปที่ workbook ของคุณและเรียกกระบวนการเรนเดอร์

```java
// Replace with your actual document path
Path documentPath = Paths.get("YOUR_DOCUMENT_DIRECTORY/SAMPLE_XLSX_WITH_PRINT_AREAS.xlsx");

try (Viewer viewer = new Viewer(documentPath.toString())) {
    // Render to HTML using the configured view options
    viewer.view(viewOptions);
}
```

*Explanation:* เมธอด `view()` จะกำหนดให้สมุดงานตามข้อกำหนดการตั้งค่าไว้รวมถึงไฟล์ HTML เพิ่มเติมเฉพาะส่วนพื้นที่พิมพ์

## ปัญหาทั่วไปและแนวทางแก้ไข
- **เพื่อตรวจสอบเส้นทางไฟล์:** ตรวจสอบเส้นทางการเดินทางแบบสัมบูรณ์หรือญาติๆ โดยตรงต่อการทำงานของโปรเจกต์
- **ปัญหาการปนเปื้อน:** ในขณะที่โปรเซสชั่น Java อนุญาตให้อ่านไฟล์ต้นฉบับและเขียนไฟล์ไปยังผลลัพธ์
- **ไม่มีพื้นที่พิมพ์:** และในสเปรดชีตได้กำหนดพื้นที่พิมพ์ไว้ (Page Layout → Print Area ใน Excel)

## การใช้งานจริง
1. **ระบบการจัดการเอกสาร:** แสดงตัวอย่างรายงานที่สะอาดและสามารถโหลดสมุดงานได้ที่นี่
2. **แดชบอร์ดทางการเงิน:** สร้างสแนปช็อต HTML ของระดับการเงินที่สำคัญที่กำหนดเป็นพื้นที่พิมพ์
3. **แพลตฟอร์มการเรียนรู้:** ให้ผู้เรียนดูข้อมูลการทำงานของคนส่วนใหญ่ในมุมมองที่มุ่งเน้น
4. **พอร์ทัล CRM:** เน้นย้ำถึงความต้องการของลูกค้าในขณะที่ซ่อนแผ่นงานภายใน
5. **สมุดบันทึกวิทยาศาสตร์ข้อมูล:** ฝังการแสดงตัวอย่างสเปรดชีตสั้น อยู่ในเอกสารอธิบาย

## เคล็ดลับประสิทธิภาพ
- **การปรับหน่วยความจำ:** สำหรับสมุดงานขนาดใหญ่มากไม่ต้องเพิ่มฮีปของ JVM (`-Xmx2g` เพิ่มเติม)
- **Lazy Loading:** ก่อนอื่นต้องหยุดเรนเดอร์หลังจากจำนวนหน้าที่ต้องการครบแล้ว
- **การประมวลผลแบบขนาน:** เรนเดอร์หลายสมุดงาน พร้อมกันนี้ `Viewer` แยกแต่ละอินสแตนซ์ ในแต่ละพื้นที่

## บทสรุป
บางครั้ง **สร้างตัวอย่างเอกสาร java** ที่เรนเดอร์เฉพาะพื้นที่พิมพ์ของสเปรดชีตเทคนิคนี้ทำให้การแสดงตัวอย่างเพิ่ มขึ้นเรื่อย ๆ — เพื่อให้เว็บแอปพลิเคชันและแอปพลิเคชันระดับองค์กรระดับสมัยใหม่

### ขั้นตอนต่อไป
- คุณสามารถดูรูปแบบอื่นๆ อีกมากมาย (PDF, PNG) ด้วย `PdfViewOptions` หรือ `PngViewOptions`
- มหัศจรรย์แห่งการอธิบายตัวอย่างกับระบบการตรวจสอบความถูกต้องข้อมูลที่สำคัญ
- การควบคุม API `SpreadsheetOptions` ไม่จำเป็นต้องกำหนดขนาดหน้าใหม่ในบรรทัดนี้ก็ได้

## ส่วนคำถามที่พบบ่อย
**ถาม: ประโยชน์ของฟังก์ชั่นการเรนเดอร์เฉพาะพื้นที่พิมพ์ของ Excel หรือไม่**
ตอบ: ลดความรกและความหลากหลายของเรนเดอร์เพื่อให้ได้ตัวอย่างที่เน้นข้อมูลสำคัญที่สุด

**ถาม: สามารถเรนเดอร์แผ่นงานไม่มีการตีพิมพ์ได้อย่างไร?**
ตอบ: ได้ — เพียงแต่ไม่ใช้ `SpreadsheetOptions.forRenderingPrintArea()` และตัวเลือกเริ่มต้นสำหรับสมุดงานของเรนเดอร์

**Q: GroupDocs.Viewer รองรับรูปแบบสเปรดชีตอื่นๆ ได้อีกหรือไม่**
ตอบ: รองรับ XLS, XLSX, CSV, ODS และรูปแบบอื่นๆ อีกมากมายเพื่อดูเอกสารอย่างเป็นทางการสำหรับรายการเต็ม

**ถาม: ติดตามความเร็วของเรนเดอร์สำหรับไฟล์ขนาดใหญ่อย่างไร?**
ตอบ: เพิ่มฮีปของ JVM, เรนเดอร์เฉพาะหน้าที่ต้องการ, พิจารณาว่าจะใช้ระบบการควบคุมแบบหลายระบบร่วมกัน

**ถาม: ข้อมูลการพิมพ์ของฉันไม่เก็บข้อมูล — ตรวจสอบอะไร?**
ตอบ: พื้นที่พื้นที่พิมพ์ได้เป็นจำนวนมากในไฟล์ต้นฉบับ (Excel → Page Layout → Print Area) และ GroupDocs.Viewer ล่าสุด

## ทรัพยากร
- **เอกสารประกอบ:** [เอกสารประกอบ GroupDocs.Viewer Java](https://docs.groupdocs.com/viewer/java/)
- **ข้อมูลอ้างอิง API:** [ข้อมูลอ้างอิง API ของ GroupDocs](https://reference.groupdocs.com/viewer/java/)
- **ดาวน์โหลด:** [รับ GroupDocs.Viewer สำหรับ Java](https://releases.groupdocs.com/viewer/java/)
- **ซื้อ:** [ซื้อใบอนุญาต](https://purchase.groupdocs.com/buy)
- **ทดลองใช้ฟรี:** [เริ่มต้นด้วยการทดลองใช้ฟรี](https://releases.groupdocs.com/viewer/java/)
- **ใบอนุญาตชั่วคราว:** [ขอที่นี่](https://purchase.groupdocs.com/temporary-license/)
- **การสนับสนุน:** [GroupDocs [ฟอรัม](https://forum.groupdocs.com/c/viewer/9)

---

**อัปเดตล่าสุด:** 2025-12-23
**ทดสอบกับ:** GroupDocs.Viewer สำหรับ Java 25.2
**ผู้เขียน:** GroupDocs