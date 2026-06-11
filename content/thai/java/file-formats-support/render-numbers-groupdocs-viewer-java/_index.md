---
date: '2026-03-05'
description: เรียนรู้วิธีแปลงตัวเลขเป็น PDF และรูปแบบอื่น ๆ เช่น HTML, JPG, PNG ด้วย
  GroupDocs.Viewer สำหรับ Java คู่มือนี้ครอบคลุมการตั้งค่า เทคนิคการเรนเดอร์ และการใช้งานจริง
keywords:
- GroupDocs.Viewer for Java
- render Apple Numbers documents
- convert Numbers to HTML, JPG, PNG, PDF
title: แปลงตัวเลขเป็น PDF ด้วย GroupDocs.Viewer สำหรับ Java
type: docs
url: /th/java/file-formats-support/render-numbers-groupdocs-viewer-java/
weight: 1
---

# แปลง Numbers เป็น PDF (และรูปแบบอื่น) ด้วย GroupDocs.Viewer สำหรับ Java

การแสดงเอกสาร Apple Numbers บนเว็บหรือในแอปพลิเคชันเดสก์ท็อปอาจเป็นเรื่องยาก โดยเฉพาะเมื่อคุณต้องการ **convert numbers to pdf** หรือฝังเป็นรูปภาพ ในบทแนะนำนี้เราจะอธิบายวิธีใช้ **GroupDocs.Viewer for Java** เพื่อเรนเดอร์ไฟล์ Numbers เป็น HTML, JPG, PNG, **และ PDF**—ให้คุณมีตัวเลือกที่ยืดหยุ่นสำหรับการแชร์, ดูตัวอย่าง, หรือเก็บถาวรสเปรดชีตของคุณ

![เรนเดอร์เอกสาร Apple Numbers ด้วย GroupDocs.Viewer สำหรับ Java](/viewer/file-formats-support/render-apple-numbers-documents-java.png)

### สิ่งที่คุณจะได้เรียนรู้
- วิธีตั้งค่า GroupDocs.Viewer ในโครงการ Java ที่ใช้ Maven  
- โค้ดแบบขั้นตอนต่อขั้นตอนเพื่อ **convert numbers to pdf**, **convert numbers to html**, และ **convert numbers to jpg**  
- สถานการณ์จริงที่การแปลงเอกสารเพิ่มคุณค่าให้กับพอร์ทัลเว็บ, กระบวนการทำงานอีเมล, และการรวม DMS  

## คำตอบอย่างรวดเร็ว
- **ฉันสามารถแปลง Numbers เป็น PDF ด้วย Java ได้หรือไม่?** ใช่, โดยใช้ `PdfViewOptions` ใน GroupDocs.Viewer.  
- **รูปแบบใดดีที่สุดสำหรับการดูตัวอย่างบนเว็บ?** HTML ให้ประสบการณ์ที่โต้ตอบที่สุด.  
- **ฉันต้องการไลเซนส์สำหรับการใช้งานในผลิตภัณฑ์หรือไม่?** ต้องมีไลเซนส์เชิงพาณิชย์สำหรับการใช้งานที่ไม่ใช่การทดลอง.  
- **การแปลงเป็นรูปภาพได้รับการสนับสนุนหรือไม่?** แน่นอน—ใช้ `JpgViewOptions` หรือ `PngViewOptions` เพื่อรับภาพคุณภาพสูง.  
- **ต้องการเวอร์ชัน Java ใด?** Java 8+ และ Maven สำหรับการจัดการ dependencies.  

## ข้อกำหนดเบื้องต้น
- Java Development Kit (JDK) 8 หรือสูงกว่า ติดตั้งแล้ว.  
- Maven สำหรับจัดการ dependencies.  
- ความคุ้นเคยพื้นฐานกับการทำ I/O ของไฟล์ Java และเส้นทาง.  

## การตั้งค่า GroupDocs.Viewer สำหรับ Java

### การติดตั้งด้วย Maven
เพิ่ม repository และ dependency ลงใน `pom.xml` ของคุณ บล็อกนี้ต้องคงอยู่ตามที่แสดง:

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
- **Free Trial:** ประเมินคุณลักษณะทั้งหมดโดยไม่มีค่าใช้จ่าย.  
- **Temporary License:** ขอคีย์ที่มีระยะเวลาจำกัดสำหรับการทดสอบต่อเนื่อง.  
- **Purchase:** รับไลเซนส์เต็มสำหรับโครงการเชิงพาณิชย์.  

## การเรนเดอร์เอกสาร Numbers เป็น HTML  
*กรณีใช้งาน: ฝังสเปรดชีตโดยตรงในหน้าเว็บ.*

### ขั้นตอนที่ 1: เริ่มต้น Viewer และกำหนดค่า HTML Options
ด้านล่างเป็นโค้ดที่คุณจะรันอย่างแม่นยำ คอมเมนต์อธิบายแต่ละบรรทัด, แต่ **ห้ามแก้ไขบล็อกโค้ด**.

```java
import com.groupdocs.viewer.Viewer;
import com.groupdocs.viewer.options.HtmlViewOptions;
import java.nio.file.Path;

Path outputDirectory = Path.of("YOUR_OUTPUT_DIRECTORY");
Path pageFileFullPath = outputDirectory.resolve("Numbers_result.html");

try (Viewer viewer = new Viewer("YOUR_DOCUMENT_DIRECTORY/SAMPLE_NUMBERS")) {
    HtmlViewOptions options = HtmlViewOptions.forEmbeddedResources(pageFileFullPath);
    viewer.view(options);
}
```

- **ทำไมเรื่องนี้สำคัญ:** `HtmlViewOptions.forEmbeddedResources()` รวม CSS และรูปภาพไว้ใน HTML ทำให้เหมาะสำหรับการดูตัวอย่างเว็บอย่างรวดเร็ว.

## การเรนเดอร์เอกสาร Numbers เป็น JPG  
*เหมาะสำหรับการแชร์ภาพสแนปช็อตของสเปรดชีตบนโซเชียลมีเดียหรืออีเมล.*

### ขั้นตอนที่ 1: ตั้งค่า Viewer และ JPG Options
```java
import com.groupdocs.viewer.Viewer;
import com.groupdocs.viewer.options.JpgViewOptions;
import java.nio.file.Path;

Path outputDirectory = Path.of("YOUR_OUTPUT_DIRECTORY");
Path pageFileFullPath = outputDirectory.resolve("Numbers_result.jpg");

try (Viewer viewer = new Viewer("YOUR_DOCUMENT_DIRECTORY/SAMPLE_NUMBERS")) {
    JpgViewOptions options = new JpgViewOptions(pageFileFullPath);
    viewer.view(options);
}
```

- **เคล็ดลับ:** ปรับคุณภาพภาพด้วย `options.setQuality(int)` หากต้องการไฟล์ขนาดเล็กลง.  

## การเรนเดอร์เอกสาร Numbers เป็น PNG  
*เหมาะเมื่อคุณต้องการภาพที่ไม่มีการสูญเสียและความละเอียดสูงสำหรับรายงาน.*

### ขั้นตอนที่ 1: เริ่มต้นและกำหนดค่า PNG Options
```java
import com.groupdocs.viewer.Viewer;
import com.groupdocs.viewer.options.PngViewOptions;
import java.nio.file.Path;

Path outputDirectory = Path.of("YOUR_OUTPUT_DIRECTORY");
Path pageFileFullPath = outputDirectory.resolve("Numbers_result.png");

try (Viewer viewer = new Viewer("YOUR_DOCUMENT_DIRECTORY/SAMPLE_NUMBERS")) {
    PngViewOptions options = new PngViewOptions(pageFileFullPath);
    viewer.view(options);
}
```

- **เคล็ดลับระดับมืออาชีพ:** ใช้ `options.setResolution(int)` เพื่อควบคุม DPI สำหรับภาพพร้อมพิมพ์.  

## การเรนเดอร์เอกสาร Numbers เป็น PDF  
*เป้าหมายหลักของนักพัฒนาหลายคน: **convert numbers to pdf** สำหรับการเก็บถาวรหรือการแจกจ่าย.*

### ขั้นตอนที่ 1: ตั้งค่า Viewer สำหรับการแปลงเป็น PDF
```java
import com.groupdocs.viewer.Viewer;
import com.groupdocs.viewer.options.PdfViewOptions;
import java.nio.file.Path;

Path outputDirectory = Path.of("YOUR_OUTPUT_DIRECTORY");
Path pageFileFullPath = outputDirectory.resolve("Numbers_result.pdf");

try (Viewer viewer = new Viewer("YOUR_DOCUMENT_DIRECTORY/SAMPLE_NUMBERS")) {
    PdfViewOptions options = new PdfViewOptions(pageFileFullPath);
    viewer.view(options);
}
```

- **การกำหนดค่าหลัก:** `PdfViewOptions` ให้คุณฝังฟอนต์และควบคุมขนาดหน้า, ทำให้ผลลัพธ์ตรงตามความต้องการของแบรนด์ของคุณ.  

## การประยุกต์ใช้งานจริง
- **Web Integration:** เรนเดอร์เป็น HTML เพื่อให้มีตัวดูสเปรดชีตแบบโต้ตอบบนเว็บไซต์ของคุณ.  
- **Content Sharing:** แปลงเป็น JPG/PNG เพื่อฝังรูปภาพอย่างรวดเร็วในจดหมายข่าวหรือแชท.  
- **Enterprise DMS:** ใช้ **convert numbers to pdf** เพื่อเก็บเวอร์ชันของสเปรดชีตที่ไม่สามารถแก้ไขได้และค้นหาได้.  

## การพิจารณาประสิทธิภาพ
- **Resource Management:** ควรปิด `Viewer` เสมอในบล็อก try‑with‑resources (ตามที่แสดง) เพื่อปล่อยทรัพยากรเนทีฟโดยเร็ว.  
- **Large Files:** สำหรับไฟล์ Numbers ขนาดใหญ่, พิจารณาประมวลผลทีละหน้าและสตรีมผลลัพธ์เพื่อหลีกเลี่ยงการใช้หน่วยความจำสูง.  
- **Thread Safety:** สร้างอินสแตนซ์ `Viewer` แยกสำหรับแต่ละเธรด; คลาสนี้ไม่ปลอดภัยต่อการทำงานหลายเธรด.  

## สรุป
คุณมีเครื่องมือครบชุดสำหรับ **convert numbers to pdf**, รวมถึง HTML, JPG, และ PNG, ด้วยการใช้ GroupDocs.Viewer สำหรับ Java ความสามารถเหล่านี้ทำให้คุณสามารถสร้าง pipeline เอกสารที่ยืดหยุ่น—ไม่ว่าจะเป็นการส่งข้อมูลให้พอร์ทัลเว็บ, สร้างรายงาน, หรือเก็บสเปรดชีต.

### ขั้นตอนต่อไป
สำรวจตัวเลือกการปรับแต่งเพิ่มเติมใน [เอกสาร GroupDocs](https://docs.groupdocs.com/viewer/java/) และทดลองผสานคุณลักษณะเหล่านี้เข้ากับแอปพลิเคชันของคุณ.

## ส่วนคำถามที่พบบ่อย

**Q1: GroupDocs.Viewer รองรับรูปแบบไฟล์อะไรบ้าง?**  
A1: รองรับรูปแบบเอกสารหลากหลายรวมถึง DOCX, XLSX, PDF, และอื่น ๆ.

**Q2: ฉันจะจัดการไฟล์ Numbers ขนาดใหญ่อย่างมีประสิทธิภาพได้อย่างไร?**  
A2: ใช้เทคนิคการจัดการหน่วยความจำของ Java และปรับแต่งโค้ดของคุณเพื่อจัดการไฟล์ขนาดใหญ่ได้อย่างมีประสิทธิภาพ.

**Q3: GroupDocs.Viewer สามารถใช้ในโครงการเชิงพาณิชย์ได้หรือไม่?**  
A4: ใช่, แต่คุณจะต้องซื้อไลเซนส์สำหรับการใช้งานเชิงพาณิชย์.

**Q4: สามารถปรับคุณภาพของภาพที่ส่งออกได้หรือไม่?**  
A5: แน่นอน. คุณสามารถปรับการตั้งค่าใน `JpgViewOptions` และ `PngViewOptions`.

**Q5: จะหา ตัวอย่างการใช้งานขั้นสูงได้จากที่ไหน?**  
A5: เยี่ยมชม [API reference](https://reference.groupdocs.com/viewer/java/) เพื่อดูเอกสารรายละเอียด.

## คำถามที่พบบ่อย

**Q: ฉันจะแปลงไฟล์ Numbers เป็น PDF โดยไม่สูญเสียรูปแบบได้อย่างไร?**  
A: ใช้ `PdfViewOptions` ตามที่แสดงด้านบน; Viewer จะรักษาเลย์เอาต์, ฟอนต์, และสไตล์ของเซลล์โดยอัตโนมัติ.

**Q: ฉันสามารถแปลงสเปรดชีตเป็นรูปภาพได้ในหนึ่งคำสั่งหรือไม่?**  
A: ใช่, `JpgViewOptions` หรือ `PngViewOptions` จัดการการแปลงในขั้นตอนเดียว, ให้คุณกำหนดความละเอียดและคุณภาพได้.

**Q: มีวิธีการประมวลผลหลายไฟล์ Numbers พร้อมกันหรือไม่?**  
A: ห่อโลจิกของ Viewer ไว้ในลูป, เริ่มต้น `Viewer` ใหม่สำหรับแต่ละไฟล์, แล้วเขียนผลลัพธ์แต่ละไฟล์ลงในโฟลเดอร์แยกกัน.

**Q: ฉันต้องการไลเซนส์แยกสำหรับแต่ละรูปแบบการส่งออกหรือไม่?**  
A: ไม่, ไลเซนส์ GroupDocs.Viewer เพียงหนึ่งใบครอบคลุมทุกรูปแบบที่สนับสนุน.

**Q: ต้องใช้เวอร์ชันของ GroupDocs.Viewer ใดสำหรับคุณลักษณะเหล่านี้?**  
A: ตัวอย่างนี้ใช้เวอร์ชัน 25.2 ซึ่งรองรับการแปลง Numbers เป็น PDF/HTML/Image อย่างเต็มรูปแบบ.

## แหล่งข้อมูล
- **Documentation:** [GroupDocs.Viewer Java Docs](https://docs.groupdocs.com/viewer/java/)  
- **API Reference:** [GroupDocs API Reference](https://reference.groupdocs.com/viewer/java/)  
- **Download:** [Get GroupDocs.Viewer](https://releases.groupdocs.com/viewer/java/)  
- **Purchase License:** [Buy a License](https://purchase.groupdocs.com/buy)  
- **Free Trial:** [Start Your Free Trial](https://releases.groupdocs.com/viewer/java/)  
- **Temporary License:** [Request Here](https://purchase.groupdocs.com/temporary-license/)  
- **Support Forum:** [Join the Discussion](https://forum.groupdocs.com/c/viewer/9)  

---

**Last Updated:** 2026-03-05  
**Tested With:** GroupDocs.Viewer 25.2 for Java  
**Author:** GroupDocs