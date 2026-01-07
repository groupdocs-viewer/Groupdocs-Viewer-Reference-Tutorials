---
date: '2025-12-23'
description: เรียนรู้วิธีสร้างการแสดงตัวอย่างเอกสารใน Java ด้วยการเรนเดอร์พื้นที่พิมพ์ของ
  Excel โดยใช้ GroupDocs.Viewer คู่มือขั้นตอนต่อขั้นตอนสำหรับโซลูชันการแสดงตัวอย่าง
  Java ที่มีประสิทธิภาพ
keywords:
- Java spreadsheet print areas rendering
- rendering print areas with GroupDocs.Viewer for Java
- efficient document preview solutions
title: 'สร้างตัวอย่างเอกสาร Java: แสดงพื้นที่พิมพ์ของสเปรดชีตด้วย GroupDocs.Viewer'
type: docs
url: /th/java/advanced-rendering/java-groupdocs-viewer-render-print-areas-spreadsheet/
weight: 1
---

# สร้างการแสดงตัวอย่างเอกสาร Java: เรนเดอร์พื้นที่พิมพ์ของสเปรดชีตด้วย GroupDocs.Viewer

การเรนเดอร์เฉพาะส่วนพื้นที่พิมพ์ของสเปรดชีตสามารถลดจำนวนข้อมูลที่ผู้ใช้ต้องสแกนได้อย่างมาก ทำให้การแสดงตัวอย่างเอกสารเร็วขึ้นและโฟกัสมากขึ้น ในคู่มือนี้คุณจะ **create document preview java** โครงการที่เรนเดอร์เฉพาะพื้นที่พิมพ์ที่กำหนดไว้โดยใช้ **GroupDocs.Viewer for Java** เราจะพาคุณผ่านขั้นตอนการตั้งค่า การกำหนดค่า และการใช้งานจริง เพื่อให้คุณสามารถเพิ่มความสามารถนี้ให้กับแอปพลิเคชันของคุณได้อย่างรวดเร็ว

![การเรนเดอร์พื้นที่พิมพ์ของสเปรดชีตด้วย GroupDocs.Viewer for Java](/viewer/advanced-rendering/spreadsheet-print-areas-rendering-java.png)

## Quick Answers
- **“create document preview java” หมายถึงอะไร?** หมายถึงการสร้างภาพแสดงผล (HTML, image, PDF) ของเอกสารโดยตรงจากโค้ด Java  
- **ทำไมต้องเรนเดอร์เฉพาะพื้นที่พิมพ์ของ Excel?** เพราะช่วยแยกข้อมูลที่สำคัญที่สุดออกมา ลดเวลาเรนเดอร์และแบนด์วิดท์  
- **ต้องมีลิขสิทธิ์เพื่อทดลองหรือไม่?** มีการทดลองใช้ฟรีหรือใบอนุญาตชั่วคราวให้ใช้ได้; ต้องซื้อใบอนุญาตเต็มเพื่อใช้งานในโปรดักชัน  
- **รองรับเวอร์ชัน Java ใด?** Java 8 หรือใหม่กว่า  
- **สามารถฝังการแสดงตัวอย่างในหน้าเว็บได้หรือไม่?** ได้ — ใช้ตัวเลือก `embedded‑resources` เพื่อสร้างหน้า HTML ที่เป็นไฟล์เดียวครบทุกอย่าง  

## “create document preview java” คืออะไร?
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

## Setting Up GroupDocs.Viewer for Java
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

### License Acquisition
เริ่มต้นด้วย **free trial** หรือขอ **temporary license** เพื่อการประเมินผล เมื่อพร้อมสำหรับการผลิต ให้ซื้อใบอนุญาตเต็มเพื่อเปิดใช้งานฟีเจอร์ทั้งหมดและลบข้อจำกัดของการทดลอง  

### Basic Initialization
โค้ดตัวอย่างที่จำเป็นที่สุดสำหรับการเปิดสเปรดชีตด้วย GroupDocs.Viewer มีดังนี้:

```java
import com.groupdocs.viewer.Viewer;

// Initialize Viewer object with the path to your spreadsheet
try (Viewer viewer = new Viewer("path/to/your/spreadsheet.xlsx")) {
    // Further configurations will be discussed in upcoming sections.
}
```

## How to create document preview java with GroupDocs.Viewer
ต่อไปนี้เป็นขั้นตอนแบบละเอียดที่ **render excel print area** เท่านั้น และสร้างไฟล์ HTML ที่เป็นไฟล์เดียวครบทุกอย่าง

### Step 1: Define Output Directory and File Path Format
กำหนดตำแหน่งที่ Viewer จะเขียนไฟล์ HTML ที่สร้างขึ้น

```java
import java.nio.file.Path;
import java.nio.file.Paths;

// Set the output directory path
Path outputDirectory = Paths.get("YOUR_OUTPUT_DIRECTORY");

// Define a file path format for the rendered pages
Path pageFilePathFormat = outputDirectory.resolve("page_{0}.html");
```

*Explanation:* `outputDirectory` คือโฟลเดอร์ที่เก็บไฟล์การแสดงตัวอย่างทั้งหมด `pageFilePathFormat` ใช้ placeholder (`{0}`) ที่ Viewer จะแทนที่ด้วยหมายเลขหน้า  

### Step 2: Configure HTML View Options for Print‑Area Rendering
ตั้งค่า Viewer ให้ฝังทรัพยากร (CSS, images) โดยตรงและโฟกัสที่พื้นที่พิมพ์ที่กำหนด

```java
import com.groupdocs.viewer.options.HtmlViewOptions;
import com.groupdocs.viewer.options.SpreadsheetOptions;

// Configure HTML view options with embedded resources and print area rendering
HtmlViewOptions viewOptions = HtmlViewOptions.forEmbeddedResources(pageFilePathFormat);
viewOptions.setSpreadsheetOptions(SpreadsheetOptions.forRenderingPrintArea());
```

*Explanation:* `HtmlViewOptions.forEmbeddedResources` สร้างไฟล์ HTML หนึ่งไฟล์ต่อหน้าโดยมี CSS/JS ฝังอยู่ในไฟล์เดียว ทำให้การปรับใช้ง่ายขึ้น `forRenderingPrintArea()` บอก engine ให้ **render excel print area** เท่านั้น  

### Step 3: Load the Spreadsheet and Render It
สุดท้ายให้ชี้ Viewer ไปที่ workbook ของคุณและเรียกกระบวนการเรนเดอร์

```java
// Replace with your actual document path
Path documentPath = Paths.get("YOUR_DOCUMENT_DIRECTORY/SAMPLE_XLSX_WITH_PRINT_AREAS.xlsx");

try (Viewer viewer = new Viewer(documentPath.toString())) {
    // Render to HTML using the configured view options
    viewer.view(viewOptions);
}
```

*Explanation:* เมธอด `view()` จะประมวลผล workbook ตามตัวเลือกที่ตั้งค่าไว้และสร้างไฟล์ HTML ที่แสดงเฉพาะส่วนพื้นที่พิมพ์  

## Common Issues and Solutions
- **ข้อผิดพลาดเกี่ยวกับเส้นทางไฟล์:** ตรวจสอบให้แน่ใจว่าเส้นทางเป็นแบบ absolute หรือ relative อย่างถูกต้องต่อไดเรกทอรีทำงานของโปรเจกต์  
- **ปัญหาการอนุญาต:** ให้แน่ใจว่าโปรเซส Java มีสิทธิ์อ่านไฟล์ต้นฉบับและเขียนไฟล์ไปยังโฟลเดอร์ผลลัพธ์  
- **ไม่มีพื้นที่พิมพ์:** ยืนยันว่าในสเปรดชีตได้กำหนดพื้นที่พิมพ์ไว้ (Page Layout → Print Area ใน Excel)  

## Practical Applications
1. **Document Management Systems:** แสดงตัวอย่างรายงานที่สะอาดโดยไม่ต้องโหลด workbook ทั้งหมด  
2. **Financial Dashboards:** สร้างสแนปช็อต HTML ของตารางการเงินสำคัญที่กำหนดเป็นพื้นที่พิมพ์  
3. **Learning Platforms:** ให้ผู้เรียนดูข้อมูลการมอบหมายงานในมุมมองที่โฟกัส  
4. **CRM Portals:** เน้นเมตริกของลูกค้าในขณะที่ซ่อนแผ่นงานภายใน  
5. **Data‑Science Notebooks:** ฝังการแสดงตัวอย่างสเปรดชีตสั้น ๆ ในเอกสารอธิบาย  

## Performance Tips
- **Memory tuning:** สำหรับ workbook ขนาดใหญ่มาก ให้เพิ่ม heap ของ JVM (`-Xmx2g` หรือมากกว่า)  
- **Lazy loading:** หากต้องการเพียงไม่กี่หน้าแรก ให้หยุดเรนเดอร์หลังจากจำนวนหน้าที่ต้องการครบแล้ว  
- **Parallel processing:** เรนเดอร์หลาย workbook พร้อมกันโดยใช้ `Viewer` แยกแต่ละ instance ในแต่ละเธรด  

## Conclusion
คุณได้เรียนรู้วิธี **create document preview java** ที่เรนเดอร์เฉพาะพื้นที่พิมพ์ที่กำหนดไว้ของสเปรดชีต เทคนิคนี้ทำให้การแสดงตัวอย่างเร็วขึ้น สะอาดขึ้น และปลอดภัยยิ่งขึ้น — เหมาะกับเว็บแอปและแอปพลิเคชันระดับองค์กรสมัยใหม่  

### Next Steps
- ทดลองใช้รูปแบบการแสดงผลอื่น ๆ (PDF, PNG) ด้วย `PdfViewOptions` หรือ `PngViewOptions`  
- ผสานการสร้างตัวอย่างกับระบบ authentication เพื่อปกป้องข้อมูลที่สำคัญ  
- สำรวจ API `SpreadsheetOptions` ทั้งหมดสำหรับการกำหนดขนาดหน้า กริดไลน์ และอื่น ๆ  

## FAQ Section
**Q: ประโยชน์หลักของการเรนเดอร์เฉพาะพื้นที่พิมพ์ของ Excel คืออะไร?**  
A: ลดความรกและเร่งความเร็วการเรนเดอร์ ให้ได้การแสดงตัวอย่างที่โฟกัสข้อมูลสำคัญที่สุด  

**Q: สามารถเรนเดอร์แผ่นงานที่ไม่ได้กำหนดให้พิมพ์ได้หรือไม่?**  
A: ได้ — เพียงไม่ใช้ `SpreadsheetOptions.forRenderingPrintArea()` และใช้ตัวเลือกเริ่มต้นเพื่อเรนเดอร์ workbook ทั้งหมด  

**Q: GroupDocs.Viewer รองรับรูปแบบสเปรดชีตอื่น ๆ หรือไม่?**  
A: รองรับ XLS, XLSX, CSV, ODS และรูปแบบอื่น ๆ อีกหลายประเภท ดูเอกสารอย่างเป็นทางการสำหรับรายการเต็ม  

**Q: จะเพิ่มความเร็วการเรนเดอร์สำหรับไฟล์ขนาดใหญ่อย่างไร?**  
A: เพิ่ม heap ของ JVM, เรนเดอร์เฉพาะหน้าที่ต้องการ, พิจารณาใช้การประมวลผลแบบหลายเธรด  

**Q: พื้นที่พิมพ์ของฉันไม่แสดงผล — ควรตรวจสอบอะไร?**  
A: ยืนยันว่าพื้นที่พิมพ์ได้ถูกกำหนดในไฟล์ต้นฉบับ (Excel → Page Layout → Print Area) และใช้เวอร์ชัน GroupDocs.Viewer ล่าสุด  

## Resources
- **Documentation:** [GroupDocs.Viewer Java Documentation](https://docs.groupdocs.com/viewer/java/)  
- **API Reference:** [GroupDocs API Reference](https://reference.groupdocs.com/viewer/java/)  
- **Download:** [Get GroupDocs.Viewer for Java](https://releases.groupdocs.com/viewer/java/)  
- **Purchase:** [Buy a License](https://purchase.groupdocs.com/buy)  
- **Free Trial:** [Start with a Free Trial](https://releases.groupdocs.com/viewer/java/)  
- **Temporary License:** [Request Here](https://purchase.groupdocs.com/temporary-license/)  
- **Support:** [GroupDocs Forum](https://forum.groupdocs.com/c/viewer/9)  

---

**Last Updated:** 2025-12-23  
**Tested With:** GroupDocs.Viewer for Java 25.2  
**Author:** GroupDocs