---
date: '2026-04-04'
description: เรียนรู้วิธีการหมุนหน้าที่เฉพาะของ PDF ด้วย GroupDocs.Viewer สำหรับ Java
  คู่มือขั้นตอนต่อขั้นตอนนี้ครอบคลุมการตั้งค่า Maven, การหมุน PDF 90 องศา, และการแก้ไขปัญหา.
keywords:
- rotate specific pdf pages
- rotate pdf 90 degrees
- pdf to html java
- rotate multiple pdf pages
title: วิธีหมุนหน้ากระดาษ PDF เฉพาะหน้าโดยใช้ GroupDocs.Viewer สำหรับ Java
type: docs
url: /th/java/advanced-rendering/rotate-pdf-pages-groupdocs-viewer-java/
weight: 1
---

# วิธีหมุนหน้า PDF เฉพาะด้วย GroupDocs.Viewer สำหรับ Java

การหมุนหน้าเฉพาะใน PDF สามารถเป็นสิ่งสำคัญสำหรับการจัดแนวเอกสาร, การแก้ไขภาพสแกน, หรือการปรับสไลด์การนำเสนอ **ในคู่มือนี้คุณจะได้เรียนรู้วิธีการหมุนหน้า pdf เฉพาะโดยใช้โปรแกรมกับ GroupDocs.Viewer** ไม่ว่าคุณจะต้องการหมุน pdf 90 องศา, พลิกส่วนทั้งหมด, หรือจัดการหลายหน้าในหนึ่งการเรียก

![หมุนหน้า PDF เฉพาะด้วย GroupDocs.Viewer สำหรับ Java](/viewer/advanced-rendering/rotate-specific-pdf-pages-java.png)

**สิ่งที่คุณจะได้เรียนรู้**
- การตั้งค่า GroupDocs.Viewer ในโครงการ Java ของคุณ (รวมถึงการกำหนดค่า Maven GroupDocs Viewer)
- การหมุนหน้า PDF เฉพาะโดยใช้โปรแกรม (หมุน pdf 90 องศา, 180 องศา, ฯลฯ)
- การกำหนดค่าที่สำคัญสำหรับการใช้งานที่เหมาะสม
- การแก้ไขปัญหาทั่วไประหว่างการนำไปใช้

## คำตอบอย่างรวดเร็ว
- **ไลบรารีใดที่สามารถหมุนหน้า PDF ใน Java ได้?** GroupDocs.Viewer for Java.  
- **ฉันสามารถหมุนหน้าเดียว 90 องศาได้หรือไม่?** Yes, use `rotatePage(pageNumber, Rotation.ON_90_DEGREE)`.  
- **ฉันต้องการใบอนุญาตสำหรับการพัฒนาหรือไม่?** ใบอนุญาตชั่วคราวพร้อมให้ใช้ทดลองฟรี.  
- **จำเป็นต้องใช้ Maven หรือไม่?** Maven เป็นวิธีที่แนะนำในการจัดการ dependencies ของ GroupDocs.  
- **ฉันจะเรนเดอร์หน้าที่หมุนแล้วอย่างไร?** Use `HtmlViewOptions` and call `viewer.view(...)`.

## ข้อกำหนดเบื้องต้น

### ไลบรารีและการพึ่งพาที่จำเป็น
- Java Development Kit (JDK) 8 หรือใหม่กว่า.  
- IDE เช่น IntelliJ IDEA หรือ Eclipse.  
- Maven สำหรับการจัดการ dependencies.

### ข้อกำหนดการตั้งค่าสภาพแวดล้อม
1. **Maven Configuration** – เพิ่ม GroupDocs.Viewer ไปยัง `pom.xml` ของคุณ.  
2. **License Acquisition** – รับใบอนุญาตชั่วคราวจาก GroupDocs. เยี่ยมชม [GroupDocs Free Trial](https://releases.groupdocs.com/viewer/java/) หรือสมัครใบอนุญาตชั่วคราวที่ [GroupDocs Temporary License Page](https://purchase.groupdocs.com/temporary-license/).

## การตั้งค่า GroupDocs.Viewer สำหรับ Java

เพื่อรวม GroupDocs.Viewer เข้าในโครงการ Java ของคุณโดยใช้ Maven, อัปเดต `pom.xml` ของคุณ:

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

### การเริ่มต้นและการตั้งค่าพื้นฐาน
```java
Path YOUR_DOCUMENT_DIRECTORY = Path.of("YOUR_DOCUMENT_DIRECTORY");
Path YOUR_OUTPUT_DIRECTORY = Path.of("YOUR_OUTPUT_DIRECTORY");

// Format for page file paths
Path pageFilePathFormat = YOUR_OUTPUT_DIRECTORY.resolve("page_{0}.html");

HtmlViewOptions viewOptions = HtmlViewOptions.forEmbeddedResources(pageFilePathFormat);
```

## วิธีหมุนหน้า PDF เฉพาะด้วย GroupDocs.Viewer
### ภาพรวม
การหมุนหน้า PDF เฉพาะให้คุณควบคุมการนำเสนอเอกสารอย่างละเอียดโดยไม่ต้องเปลี่ยนแปลงไฟล์ต้นฉบับ.

### ขั้นตอน 1: กำหนดค่าการหมุนหน้า
```java
// Rotate the first page by 90 degrees clockwise.
viewOptions.rotatePage(1, Rotation.ON_90_DEGREE);

// Rotate the second page by 180 degrees.
viewOptions.rotatePage(2, Rotation.ON_180_DEGREE);
```

### ขั้นตอน 2: เริ่มต้น Viewer และเรนเดอร์
```java
Viewer viewer = new Viewer(YOUR_DOCUMENT_DIRECTORY.resolve("SampleDocument.pdf"));

// Render the specified pages (1 and 2) using the configured options.
viewer.view(viewOptions, 1, 2);

// Always close the viewer to free resources.
viewer.close();
```

#### พารามิเตอร์และการกำหนดค่า
- **Rotation** – `rotatePage(pageNumber, Rotation.*)` โดยตัวเลือกการหมุนคือ `ON_90_DEGREE`, `ON_180_DEGREE`, `ON_270_DEGREE`.  
- **HtmlViewOptions** – จัดการการแปลง PDF‑to‑HTML พร้อมรักษาเลย์เอาต์และทรัพยากรที่ฝังอยู่.  
- **pdf to html java** – คลาสนี้เป็นส่วนหนึ่งของ API เดียวกันและรับประกันการแสดงผลที่ตรงตามภาพจริง.

## ทำไมต้องหมุนหน้า PDF เฉพาะ?
- **Document Alignment** – ปรับทิศทางที่ถูกต้องของสัญญาหรือใบแจ้งหนี้ที่สแกน.  
- **Presentation Tweaks** – ปรับสไลด์ที่ส่งออกเป็น PDF.  
- **Archival Consistency** – ทำให้การจัดหน้าเป็นมาตรฐานระหว่างการดิจิไทซ์เป็นจำนวนมาก.

## ปัญหาทั่วไปและวิธีแก้ (troubleshoot pdf rotation)

- **Incorrect Paths** – ตรวจสอบว่า `YOUR_DOCUMENT_DIRECTORY` และ `YOUR_OUTPUT_DIRECTORY` มีอยู่และเข้าถึงได้.  
- **Missing Dependencies** – ตรวจสอบให้แน่ใจว่า Maven coordinates ตรงกับเวอร์ชันล่าสุดของ GroupDocs.Viewer.  
- **License Restrictions** – ใช้ใบอนุญาตชั่วคราวอย่างถูกต้อง; หากไม่เช่นนั้นบางฟีเจอร์อาจถูกปิดใช้งาน.  
- **Memory Spikes** – เรนเดอร์ PDF ขนาดใหญ่เป็นชุดย่อยหรือเพิ่มขนาด heap ของ JVM.

## การประยุกต์ใช้งานจริง

### กรณีการใช้งานจริง
1. **Document Alignment** – หมุนเอกสารที่สแกนเพื่อให้ทิศทางดิจิทัลถูกต้อง.  
2. **Presentation Adjustments** – แก้ไขสไลด์การนำเสนอใน PDF ก่อนแชร์.  
3. **Archival Workflows** – ปรับทิศทางของเอกสารประวัติศาสตร์โดยอัตโนมัติระหว่างการดิจิไทซ์.

### ความเป็นไปได้ในการบูรณาการ
รวม GroupDocs.Viewer กับระบบจัดการเนื้อหาแบบ Java, พอร์ทัลองค์กร, หรือ API ที่กำหนดเองที่ต้องการการดู PDF แบบเรียลไทม์.

## พิจารณาด้านประสิทธิภาพ
- **Resource Management** – ปิดอินสแตนซ์ `Viewer` เสมอเพื่อปล่อยไฟล์แฮนด์เลอร์และหน่วยความจำ.  
- **Java Memory Management** – ตรวจสอบการใช้ heap เมื่อประมวลผล PDF ขนาดใหญ่; พิจารณาการสตรีมหน้าแทนการโหลดไฟล์ทั้งหมด.  
- **Best Practices** – แคช HTML ที่เรนเดอร์สำหรับเอกสารที่เข้าถึงบ่อยเพื่อ ลดเวลาในการประมวลผล.

## สรุป
บทเรียนนี้ครอบคลุม **วิธีการหมุนหน้า pdf เฉพาะโดยใช้ GroupDocs.Viewer ใน Java** ตั้งแต่การตั้งค่า Maven ไปจนถึงการเรนเดอร์หน้าที่หมุนและการจัดการกับปัญหาทั่วไป ทดลองใช้ฟีเจอร์เพิ่มเติมเช่นการใส่น้ำลายน้ำ, การแปลงรูปแบบ, หรือการประมวลผลเป็นชุดเพื่อขยายการทำงานของเอกสารของคุณ.

**ขั้นตอนต่อไป:** สำรวจความสามารถอื่นของ GroupDocs.Viewer เช่นการแปลง PDF เป็น PNG, การเพิ่มลายน้ำ, หรือการบูรณาการกับผู้ให้บริการคลาวด์สตอเรจ.

## ส่วนคำถามที่พบบ่อย
- **Troubleshooting Rotation Issues** – ตรวจสอบหมายเลขหน้าและพารามิเตอร์การหมุนว่าถูกต้อง.  
- **Handling Large PDF Files** – ประมวลผลหน้าเป็นชุดและตรวจสอบการใช้หน่วยความจำ.  
- **Licensing Requirements** – ใช้ใบอนุญาตชั่วคราวสำหรับการพัฒนา; ซื้อใบอนุญาตเต็มสำหรับการผลิต.  
- **Rotating Multiple Pages** – เรียก `rotatePage` ซ้ำหลายครั้งพร้อมหมายเลขหน้าและมุมที่ต่างกัน.  
- **Integration with Java Libraries** – GroupDocs.Viewer ทำงานร่วมกับ Spring Boot, Jakarta EE, และเฟรมเวิร์ก Java อื่น ๆ อย่างราบรื่น.

## คำถามที่พบบ่อย

**Q: ฉันสามารถหมุนทุกหน้าของ PDF พร้อมกันได้หรือไม่?**  
A: ใช่. วนลูปผ่านหมายเลขหน้าและเรียก `rotatePage(page, Rotation.ON_90_DEGREE)` สำหรับแต่ละหน้า.

**Q: การหมุนส่งผลต่อไฟล์ PDF ต้นฉบับหรือไม่?**  
A: ไม่. การหมุนจะถูกนำไปใช้เฉพาะระหว่างกระบวนการเรนเดอร์; PDF ต้นฉบับจะไม่ถูกเปลี่ยนแปลง.

**Q: ถ้า PDF มีการป้องกันด้วยรหัสผ่านจะทำอย่างไร?**  
A: ให้ใส่รหัสผ่านเมื่อสร้างอินสแตนซ์ `Viewer`: `new Viewer(path, password)`.

**Q: จะดีบักข้อผิดพลาด “null pointer” เมื่อกำหนดค่า HtmlViewOptions อย่างไร?**  
A: ตรวจสอบให้แน่ใจว่าไดเรกทอรีเอาต์พุตมีอยู่และว่า `pageFilePathFormat` แก้ไขได้อย่างถูกต้อง.

**Q: มีวิธีหมุนหน้าเมื่อแปลงเป็นรูปแบบอื่น (เช่น PNG) หรือไม่?**  
A: มี. ใช้การกำหนดค่า `rotatePage` เดียวกันพร้อมตัวเลือกการมองที่เหมาะสมสำหรับรูปแบบเป้าหมาย.

## แหล่งข้อมูล
- **Documentation**: [GroupDocs Viewer Documentation](https://docs.groupdocs.com/viewer/java/)  
- **API Reference**: [GroupDocs API Reference](https://reference.groupdocs.com/viewer/java/)  
- **Download**: [GroupDocs Download Page](https://releases.groupdocs.com/viewer/java/)  
- **Purchase**: [GroupDocs Purchase Options](https://purchase.groupdocs.com/buy)  
- **Free Trial**: [GroupDocs Free Trial](https://releases.groupdocs.com/viewer/java/)  
- **Temporary License**: [Request Temporary License](https://purchase.groupdocs.com/temporary-license/)  
- **Support**: [GroupDocs Support Forum](https://forum.groupdocs.com/c/viewer/9)

---

**อัปเดตล่าสุด:** 2026-04-04  
**ทดสอบกับ:** GroupDocs.Viewer 25.2 for Java  
**ผู้เขียน:** GroupDocs