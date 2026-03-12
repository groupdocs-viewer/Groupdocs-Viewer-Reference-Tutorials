---
date: '2026-01-18'
description: เรียนรู้วิธีการหมุนหน้าต่าง PDF ด้วย GroupDocs.Viewer สำหรับ Java บทแนะนำขั้นตอนนี้ครอบคลุมการตั้งค่า
  Maven การหมุนหน้า (รวมถึงการหมุน PDF 90 องศา) และการแก้ไขปัญหา
keywords:
- rotate PDF pages Java
- GroupDocs.Viewer setup Java
- programmatically rotate PDF Java
title: วิธีหมุนหน้ากระดาษ PDF ด้วย GroupDocs.Viewer ใน Java – คู่มือฉบับสมบูรณ์
type: docs
url: /th/java/advanced-rendering/rotate-pdf-pages-groupdocs-viewer-java/
weight: 1
---

# วิธีการหมุนหน้ากระดาษ PDF ด้วย GroupDocs.Viewer ใน Java

การหมุนหน้ากระดาษเฉพาะใน PDF สามารถเป็นสิ่งสำคัญสำหรับการจัดแนวเอกสารหรือปรับสไลด์การนำเสนอ **ในคู่มือนี้คุณจะได้เรียนรู้วิธีการหมุน pdf** หน้าโดยใช้โปรแกรมกับ GroupDocs.Viewer ไม่ว่าคุณจะต้องการหมุน pdf 90 องศา, พลิกส่วนทั้งหมด, หรือจัดการหลายหน้าในหนึ่งคำสั่ง

![หมุนหน้ากระดาษ PDF เฉพาะด้วย GroupDocs.Viewer สำหรับ Java](/viewer/advanced-rendering/rotate-specific-pdf-pages-java.png)

**สิ่งที่คุณจะได้เรียนรู้:**
- การตั้งค่า GroupDocs.Viewer ในโครงการ Java ของคุณ (รวมถึงการกำหนดค่า Maven GroupDocs Viewer)
- การหมุนหน้ากระดาษ PDF เฉพาะโดยใช้โปรแกรม (หมุน pdf 90 องศา, 180 องศา, ฯลฯ)
- การกำหนดค่าหลักสำหรับการใช้งานที่เหมาะสม
- การแก้ไขปัญหาที่พบบ่อยระหว่างการนำไปใช้

## คำตอบอย่างรวดเร็ว
- **ไลบรารีใดที่สามารถหมุนหน้ากระดาษ PDF ใน Java?** GroupDocs.Viewer for Java.  
- **ฉันสามารถหมุนหน้าเดียว 90 องศาได้หรือไม่?** ใช่, ใช้ `rotatePage(pageNumber, Rotation.ON_90_DEGREE)`.  
- **ฉันต้องการไลเซนส์สำหรับการพัฒนาหรือไม่?** มีไลเซนส์ชั่วคราวให้ใช้สำหรับการทดลองฟรี.  
- **ต้องใช้ Maven หรือไม่?** Maven เป็นวิธีที่แนะนำในการจัดการ dependencies ของ GroupDocs.  
- **ฉันจะเรนเดอร์หน้าที่หมุนแล้วอย่างไร?** ใช้ `HtmlViewOptions` และเรียก `viewer.view(...)`.

## ข้อกำหนดเบื้องต้น

### ไลบรารีและ dependencies ที่จำเป็น
เพื่อเริ่มต้น, ตรวจสอบว่าคุณมี:
- Java Development Kit (JDK) รุ่น 8 หรือใหม่กว่า ติดตั้งบนเครื่องของคุณ
- Integrated Development Environment (IDE) เช่น IntelliJ IDEA หรือ Eclipse
- Maven สำหรับจัดการ dependencies ของโครงการ

### ข้อกำหนดการตั้งค่าสภาพแวดล้อม
1. **การกำหนดค่า Maven**: เพิ่ม GroupDocs.Viewer ไปยังโครงการ Maven ของคุณโดยใส่ repositories และ dependencies ที่จำเป็นในไฟล์ `pom.xml` ของคุณ.  
2. **การขอรับไลเซนส์**: รับไลเซนส์ชั่วคราวจาก GroupDocs เพื่อให้คุณสามารถสำรวจคุณสมบัติทั้งหมดโดยไม่มีข้อจำกัดในระหว่างการพัฒนา เยี่ยมชม [GroupDocs Free Trial](https://releases.groupdocs.com/viewer/java/) หรือสมัครขอไลเซนส์ชั่วคราวที่ [GroupDocs Temporary License Page](https://purchase.groupdocs.com/temporary-license/).

## การตั้งค่า GroupDocs.Viewer สำหรับ Java

เพื่อรวม GroupDocs.Viewer เข้าในโครงการ Java ของคุณโดยใช้ Maven, อัปเดตไฟล์ `pom.xml` ของคุณ:

**การกำหนดค่า Maven**  
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

### การเริ่มต้นและตั้งค่าเบื้องต้น

เริ่มต้น GroupDocs.Viewer โดยระบุไดเรกทอรีเอกสารและเส้นทางเอาต์พุตของคุณ:  
```java
Path YOUR_DOCUMENT_DIRECTORY = Path.of("YOUR_DOCUMENT_DIRECTORY");
Path YOUR_OUTPUT_DIRECTORY = Path.of("YOUR_OUTPUT_DIRECTORY");

// Format for page file paths
Path pageFilePathFormat = YOUR_OUTPUT_DIRECTORY.resolve("page_{0}.html");

HtmlViewOptions viewOptions = HtmlViewOptions.forEmbeddedResources(pageFilePathFormat);
```

## คู่มือการนำไปใช้

### การหมุนหน้าที่เฉพาะด้วย GroupDocs.Viewer

**ภาพรวม:** หมุนหน้ากระดาษ PDF เฉพาะเพื่อการนำเสนอเอกสารที่ดียิ่งขึ้น.

#### ขั้นตอนที่ 1: กำหนดค่าการหมุนหน้า

หมุนหน้าที่หนึ่ง 90 องศาและหน้าที่สอง 180 องศาโดยใช้ `HtmlViewOptions`:  
```java
// Rotate the first page by 90 degrees clockwise.
viewOptions.rotatePage(1, Rotation.ON_90_DEGREE);

// Rotate the second page by 180 degrees.
viewOptions.rotatePage(2, Rotation.ON_180_DEGREE);
```

#### ขั้นตอนที่ 2: เริ่มต้น Viewer และเรนเดอร์

สร้างอินสแตนซ์ `Viewer` ด้วยเอกสารของคุณและเรนเดอร์หน้าที่ระบุ:  
```java
Viewer viewer = new Viewer(YOUR_DOCUMENT_DIRECTORY.resolve("SampleDocument.pdf"));

// Render the specified pages (1 and 2) using the configured options.
viewer.view(viewOptions, 1, 2);

// Always close the viewer to free resources.
viewer.close();
```

### พารามิเตอร์และการกำหนดค่า
- **Rotation**: ใช้ `rotatePage` พร้อมหมายเลขหน้าและมุมการหมุน. การหมุนที่มีให้ใช้: `ON_90_DEGREE`, `ON_180_DEGREE`, `ON_270_DEGREE`.  
- **HtmlViewOptions**: กำหนดค่าการแปลงหน้ากระดาษ PDF เป็น HTML, เพื่อให้แน่ใจว่า resources ที่ฝังอยู่ถูกรวม.  
- **pdf to html java**: คลาส `HtmlViewOptions` จัดการการแปลง PDF‑to‑HTML พร้อมคงรูปแบบ.

#### เคล็ดลับการแก้ไขปัญหา (troubleshoot pdf rotation)
- ตรวจสอบเส้นทางไปยังเอกสารและไดเรกทอรีเอาต์พุตของคุณ.  
- ตรวจสอบว่ามี dependencies ที่หายไปหรือเวอร์ชันไลบรารีที่ไม่ถูกต้องหรือไม่.  
- ตรวจสอบว่าไลเซนส์ถูกนำไปใช้อย่างถูกต้องหากมีการจำกัดฟีเจอร์ในช่วงทดลอง.  
- หากคุณพบการใช้หน่วยความจำสูง, พิจารณาเรนเดอร์หน้าในชุดย่อย (หมุนหลายหน้ากระดาษ pdf อย่างค่อยเป็นค่อยไป).

## การประยุกต์ใช้งานจริง

### กรณีการใช้งานจริง
1. **Document Alignment** – หมุนเอกสารสแกนเพื่อให้มีการจัดแนวดิจิทัลที่ถูกต้อง.  
2. **Presentation Adjustments** – ปรับสไลด์การนำเสนอใน PDF ก่อนแชร์.  
3. **Archival Workflows** – ปรับทิศทางของเอกสารประวัติศาสตร์โดยอัตโนมัติระหว่างการดิจิไทซ์.

### ความเป็นไปได้ในการบูรณาการ
รวม GroupDocs.Viewer กับระบบจัดการเอกสารที่ใช้ Java, แพลตฟอร์มเนื้อหา, หรือโซลูชันองค์กรแบบกำหนดเองที่ต้องการความสามารถในการดูแบบไดนามิก.

## การพิจารณาด้านประสิทธิภาพ
- **Resource Management**: ปิดอินสแตนซ์ `Viewer` เพื่อปล่อยทรัพยากร.  
- **Java Memory Management**: ตรวจสอบการใช้หน่วยความจำเมื่อเรนเดอร์เอกสารขนาดใหญ่และใช้โครงสร้างข้อมูลที่มีประสิทธิภาพ.  
- **Best Practices**: ใช้ caching สำหรับเอกสารหรือหน้าที่เข้าถึงบ่อย.

## สรุป

บทแนะนำนี้ครอบคลุม **วิธีการหมุน pdf** หน้าโดยใช้ GroupDocs.Viewer ใน Java, ตั้งแต่การตั้งค่าสภาพแวดล้อมจนถึงการประยุกต์ใช้งานจริง. ทดลองฟังก์ชันเพิ่มเติมเช่นการใส่ลายน้ำหรือการแปลงเอกสารเป็นรูปแบบอื่น.

**ขั้นตอนต่อไป:** สำรวจคุณสมบัติเพิ่มเติมของ GroupDocs.Viewer เพื่อเพิ่มศักยภาพการประมวลผลเอกสารของคุณ.

## ส่วนคำถามที่พบบ่อย

### คำถามทั่วไป
1. **Troubleshooting Rotation Issues**: ตรวจสอบหมายเลขหน้าและพารามิเตอร์การหมุนว่าถูกต้องหรือไม่.  
2. **Handling Large PDF Files**: ประมวลผลเอกสารขนาดใหญ่อย่างมีประสิทธิภาพด้วยการจัดการทรัพยากรที่เหมาะสม.  
3. **Licensing Requirements**: ใช้ไลเซนส์ชั่วคราวสำหรับการพัฒนา; ซื้อไลเซนส์เต็มสำหรับการผลิต.  
4. **Rotating Multiple Pages**: เรียก `rotatePage` หลายครั้งพร้อมหมายเลขหน้าและมุมที่ต่างกัน.  
5. **Integration with Java Libraries**: บูรณาการ GroupDocs.Viewer อย่างราบรื่นในแอปพลิเคชันหรือเฟรมเวิร์กที่ใหญ่ขึ้น.

## คำถามที่พบบ่อย

**Q: ฉันสามารถหมุนทุกหน้าของ PDF พร้อมกันได้หรือไม่?**  
A: ได้. วนลูปผ่านหมายเลขหน้าและเรียก `rotatePage(page, Rotation.ON_90_DEGREE)` สำหรับแต่ละหน้า.

**Q: การหมุนมีผลต่อไฟล์ PDF ต้นฉบับหรือไม่?**  
A: ไม่. การหมุนจะถูกนำไปใช้เฉพาะในกระบวนการเรนเดอร์; PDF ต้นฉบับยังคงไม่เปลี่ยนแปลง.

**Q: ถ้า PDF ถูกป้องกันด้วยรหัสผ่านจะทำอย่างไร?**  
A: ให้รหัสผ่านเมื่อสร้างอินสแตนซ์ `Viewer`: `new Viewer(path, password)`.

**Q: ฉันจะดีบักข้อผิดพลาด “null pointer” เมื่อกำหนดค่า HtmlViewOptions อย่างไร?**  
A: ตรวจสอบว่าไดเรกทอรีเอาต์พุตมีอยู่และ `pageFilePathFormat` แก้ไขได้อย่างถูกต้อง.

**Q: มีวิธีหมุนหน้าเมื่อแปลงเป็นรูปแบบอื่น (เช่น PNG) หรือไม่?**  
A: ใช้การกำหนดค่า `rotatePage` เดียวกันพร้อมตัวเลือกการดูที่เหมาะสมสำหรับรูปแบบเป้าหมาย.

## แหล่งข้อมูล
- **Documentation**: [เอกสาร GroupDocs Viewer](https://docs.groupdocs.com/viewer/java/)
- **API Reference**: [อ้างอิง API ของ GroupDocs](https://reference.groupdocs.com/viewer/java/)
- **Download**: [หน้าดาวน์โหลด GroupDocs](https://releases.groupdocs.com/viewer/java/)
- **Purchase**: [ตัวเลือกการซื้อ GroupDocs](https://purchase.groupdocs.com/buy)
- **Free Trial**: [ทดลองใช้ GroupDocs ฟรี](https://releases.groupdocs.com/viewer/java/)
- **Temporary License**: [ขอไลเซนส์ชั่วคราว](https://purchase.groupdocs.com/temporary-license/)
- **Support**: [ฟอรั่มสนับสนุน GroupDocs](https://forum.groupdocs.com/c/viewer/9)

---

**อัปเดตล่าสุด:** 2026-01-18  
**ทดสอบด้วย:** GroupDocs.Viewer 25.2 for Java  
**ผู้เขียน:** GroupDocs