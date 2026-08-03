---
date: '2026-08-03'
description: เรียนรู้วิธีแปลงไฟล์ zip เป็น html ด้วย GroupDocs.Viewer Java, ตั้งค่าจำนวนรายการต่อหน้า,
  ฝังทรัพยากร html, และแปลงไฟล์เก็บข้อมูลเป็นชุดอย่างมีประสิทธิภาพ
keywords:
- convert zip to html
- how to batch convert
- embed resources html
- batch convert archives
- how to convert archives
lastmod: '2026-08-03'
og_description: เรียนรู้วิธีแปลงไฟล์ zip เป็น html ด้วย GroupDocs.Viewer Java, ตั้งค่าจำนวนรายการต่อหน้า,
  ฝังทรัพยากร html, และแปลงไฟล์เก็บข้อมูลเป็นชุดอย่างมีประสิทธิภาพ. ปฏิบัติตามโค้ดขั้นตอนต่อขั้นและเคล็ดลับด้านประสิทธิภาพ
og_image_alt: 'Guide: convert zip to html with GroupDocs.Viewer Java, showing pagination
  and embedded resources'
og_title: แปลงไฟล์ zip เป็น html และตั้งค่าจำนวนรายการต่อหน้าโดยใช้ GroupDocs.Viewer
  Java
schemas:
- author: GroupDocs
  dateModified: '2026-08-03'
  description: Learn how to convert zip to html using GroupDocs.Viewer Java, set items
    per page, embed resources html, and batch convert archives efficiently.
  headline: Convert zip to html and set items per page with GroupDocs.Viewer Java
  type: TechArticle
- questions:
  - answer: GroupDocs.Viewer Java is a server‑side library that renders over 50 document
      and archive formats—including ZIP and RAR—into HTML, PDF, or image files without
      requiring external applications.
    question: What is GroupDocs.Viewer Java?
  - answer: Visit the [free trial link](https://releases.groupdocs.com/viewer/java/)
      to download and test.
    question: How can I obtain a free trial of GroupDocs.Viewer?
  - answer: Yes, the viewer supports PDFs, Word, Excel, PowerPoint, and 35+ additional
      formats.
    question: Can I convert other document types besides archives?
  - answer: Reduce the number of items per page, enable streaming, or process archives
      in smaller batches to improve speed.
    question: What should I do if rendering is slow?
  - answer: Reach out via the [support forum](https://forum.groupdocs.com/c/viewer/9).
    question: Where can I get help or support?
  type: FAQPage
tags:
- convert zip
- GroupDocs.Viewer
- Java archive conversion
- html rendering
- batch conversion
title: แปลงไฟล์ zip เป็น html และตั้งค่าจำนวนรายการต่อหน้าโดยใช้ GroupDocs.Viewer
  Java
type: docs
url: /th/java/export-conversion/groupdocs-viewer-java-convert-archives-html/
weight: 1
---

# แปลง zip เป็น html และตั้งค่ารายการต่อหน้าใน GroupDocs.Viewer Java

ในหลายแอปพลิเคชันเว็บ คุณต้องการแสดงเนื้อหาของไฟล์ ZIP หรือ RAR โดยตรงในเบราว์เซอร์. ด้วย GroupDocs.Viewer for Java คุณสามารถ **convert zip to html** ในขั้นตอนเดียว ควบคุมจำนวนรายการในไฟล์เก็บข้อมูลที่แสดงบนแต่ละหน้า ฝังรูปภาพและ CSS ที่สนับสนุนทั้งหมด และแม้กระทั่งประมวลผลหลายไฟล์พร้อมกันหลายสิบไฟล์. บทแนะนำนี้จะพาคุณผ่านกระบวนการทำงานทั้งหมด ตั้งแต่การตั้งค่า Maven ไปจนถึงการแสดงผลหลายหน้า และอธิบายว่าการตั้งค่าแต่ละอย่างมีความสำคัญต่อประสิทธิภาพและการใช้งานอย่างไร.

![แปลงไฟล์เก็บข้อมูลเป็น HTML ด้วย GroupDocs.Viewer for Java](/viewer/export-conversion/convert-archives-to-html-java.png)

## คำตอบสั้น
- **“set items per page” ควบคุมอะไร?** มันกำหนดจำนวนไฟล์หรือโฟลเดอร์จากไฟล์เก็บข้อมูลที่ปรากฏบนแต่ละหน้า HTML ที่สร้างขึ้น.  
- **ฉันสามารถฝังรูปภาพและ CSS ลงใน HTML ได้โดยตรงหรือไม่?** ใช่ – ใช้ตัวเลือก `forEmbeddedResources` เพื่อฝังทรัพยากรใน HTML.  
- **การแปลงแบบชุดเป็นไปได้หรือไม่?** แน่นอน; คุณสามารถวนลูปผ่านคอลเลกชันของไฟล์เก็บข้อมูลและเรนเดอร์แต่ละไฟล์ด้วยการตั้งค่าเดียวกัน.  
- **ฉันต้องใช้ Maven เพื่อใช้ GroupDocs.Viewer หรือไม่?** ใช่, เพิ่ม dependency `groupdocs-viewer` ของ Maven ตามที่แสดงด้านล่าง.  
- **รูปแบบผลลัพธ์ที่รองรับมีอะไรบ้าง?** HTML หน้าหนึ่งและ HTML หลายหน้า ทั้งสองรูปแบบพร้อมใช้งาน และไลบรารีรองรับไฟล์เก็บข้อมูลประเภท 50+ ประเภท.

## “set items per page” คืออะไรใน GroupDocs.Viewer?
การตั้งค่า **set items per page** อยู่ในตัวเลือกการเรนเดอร์ไฟล์เก็บข้อมูล. มันบอกให้ viewer ว่าควรแสดงรายการในไฟล์เก็บข้อมูล (ไฟล์หรือโฟลเดอร์) จำนวนเท่าใดบนแต่ละหน้า HTML เมื่อคุณสร้างเอกสาร HTML หลายหน้า. การปรับค่าตัวนี้ช่วยให้คุณสมดุลขนาดหน้าและความเร็วในการนำทาง โดยเฉพาะสำหรับไฟล์เก็บข้อมูลขนาดใหญ่.

## ทำไมต้องฝัง resources html?
การฝัง resources (รูปภาพ, CSS, ฟอนต์) โดยตรงภายในไฟล์ HTML ทำให้ได้เอกสารเดียวที่พกพาได้ซึ่งสามารถเปิดได้โดยไม่ต้องอ้างอิงไฟล์ภายนอก. สิ่งนี้เหมาะสำหรับไฟล์แนบอีเมล, การดูแบบออฟไลน์, หรือการฝังผลลัพธ์ลงในหน้าเว็บอื่น. วิธีการนี้ยังทำให้การปรับใช้ง่ายขึ้น เพราะไม่ต้องจัดการเส้นทางของ assets ภายนอก.

## ข้อกำหนดเบื้องต้น
- **ไลบรารีที่จำเป็น:** รวม GroupDocs.Viewer เวอร์ชัน 25.2 หรือใหม่กว่า.  
- **สภาพแวดล้อม:** ติดตั้งและกำหนดค่า Java Development Kit (JDK).  
- **ความรู้:** ความรู้พื้นฐานของ Java และการจัดการ dependency ของ Maven.  

## การตั้งค่า Maven GroupDocs Viewer
เพิ่ม repository ของ GroupDocs และ dependency ของ viewer ลงในไฟล์ `pom.xml` ของคุณ:

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
GroupDocs.Viewer มี **free trial link** ใบทดลองใช้ฟรี, ใบอนุญาตชั่วคราว, หรือทางเลือกการซื้อเต็มรูปแบบ. เลือกตัวเลือกที่เหมาะกับระยะเวลาโครงการของคุณ.

### การเริ่มต้นพื้นฐาน
หลังจากตั้งค่า Maven แล้ว นำ viewer เข้าสู่โค้ดของคุณ:

```java
import com.groupdocs.viewer.Viewer;
// Your initialization code here
```

## วิธีเรนเดอร์ไฟล์เก็บข้อมูลเป็น html หน้าหนึ่ง
Viewer เป็นคลาสหลักที่โหลดเอกสารหรือไฟล์เก็บข้อมูลเพื่อทำการเรนเดอร์.

เพื่อสร้างไฟล์ HTML หนึ่งไฟล์ที่บรรจุไฟล์เก็บข้อมูลทั้งหมด ให้สร้างอินสแตนซ์ `Viewer` สำหรับไฟล์ ZIP และใช้ `HtmlViewOptions.forEmbeddedResources()` เพื่อฝังรูปภาพ, CSS, และฟอนต์ทั้งหมด การเรนเดอร์ไฟล์เก็บข้อมูลด้วยตัวเลือกเหล่านี้จะสร้างหน้าเดียวที่มีทุกอย่างเหมาะสำหรับการแนบอีเมลหรือการใช้งานออฟไลน์.

### ขั้นตอนที่ 1: กำหนดไดเรกทอรีผลลัพธ์
```java
Path outputDirectory = Utils.getOutputDirectoryPath("YOUR_OUTPUT_DIRECTORY");
```

### ขั้นตอนที่ 2: ตั้งชื่อไฟล์สำหรับผลลัพธ์หน้าเดียว
```java
Path pageFilePathFormat = outputDirectory.resolve("RAR_result.html");
```

### ขั้นตอนที่ 3: เริ่มต้น viewer
```java
try (Viewer viewer = new Viewer(TestFiles.SAMPLE_RAR_WITH_FOLDERS)) {
    // Further configuration steps follow
}
```

### ขั้นตอนที่ 4: กำหนดค่าตัวเลือกการเรนเดอร์ (embed resources html)
```java
HtmlViewOptions options = HtmlViewOptions.forEmbeddedResources(pageFilePathFormat);
```

### ขั้นตอนที่ 5: เรนเดอร์เป็นหน้าเดียว
```java
options.setRenderToSinglePage(true);
viewer.view(options);
```

## วิธีเรนเดอร์ไฟล์เก็บข้อมูลเป็น html หลายหน้าและตั้งค่ารายการต่อหน้า
`HtmlViewOptions` กำหนดวิธีที่ viewer เรนเดอร์ผลลัพธ์ HTML รวมถึงการแบ่งหน้าและการฝัง resources.

เพื่อแบ่งไฟล์เก็บข้อมูลเป็นหลายหน้า ให้สร้าง `HtmlViewOptions.forEmbeddedResources()` และตั้งขนาดหน้าที่ต้องการด้วย `options.setItemsPerPage(20)`. Viewer จะสร้างไฟล์ HTML แยกกันแต่ละไฟล์จะแสดงรายการจำนวนที่กำหนด ซึ่งช่วยปรับปรุงการนำทางสำหรับไฟล์เก็บข้อมูลขนาดใหญ่และทำให้การโหลดเร็วขึ้น.

### ขั้นตอนที่ 1: ใช้ไดเรกทอรีผลลัพธ์ซ้ำ
```java
Path outputDirectory = Utils.getOutputDirectoryPath("YOUR_OUTPUT_DIRECTORY");
```

### ขั้นตอนที่ 2: กำหนดรูปแบบชื่อไฟล์สำหรับหลายหน้า
```java
Path pageFilePathFormat = outputDirectory.resolve("RAR_result_page_{0}.html");
```

### ขั้นตอนที่ 3: เริ่มต้น viewer อีกครั้ง
```java
try (Viewer viewer = new Viewer(TestFiles.SAMPLE_RAR_WITH_FOLDERS)) {
    // Continue with multi‑page configuration
}
```

### ขั้นตอนที่ 4: กำหนดค่าตัวเลือกหลายหน้า (embed resources html)
```java
HtmlViewOptions options = HtmlViewOptions.forEmbeddedResources(pageFilePathFormat);
```

### ขั้นตอนที่ 5: ตั้งค่ารายการต่อหน้า (คีย์เวิร์ดหลักในแอคชัน)
```java
options.getArchiveOptions().setItemsPerPage(10); // Default is 16
viewer.view(options);
```

## การประยุกต์ใช้งานจริง
- **Document management systems:** เพิ่มฟังก์ชันการแสดงตัวอย่างไฟล์เก็บข้อมูลโดยไม่ต้องติดตั้ง viewer เพิ่มเติม.  
- **Web portals:** ให้ผู้ใช้วิธีที่รวดเร็วและไม่ต้องดาวน์โหลดเพื่อสำรวจเอกสารที่บรรจุรวมกัน.  
- **Collaboration tools:** ให้ทีมตรวจสอบไฟล์เก็บข้อมูลที่แชร์โดยตรงในเบราว์เซอร์.  

## ข้อควรพิจารณาด้านประสิทธิภาพ
- **Resource management:** รักษาการใช้หน่วยความจำให้ต่ำโดยประมวลผลไฟล์เก็บข้อมูลเป็นสตรีม; viewer สามารถจัดการไฟล์เก็บข้อมูลขนาดสูงสุด 500 MB โดยไม่ต้องโหลดไฟล์ทั้งหมดเข้าสู่หน่วยความจำ.  
- **Batch convert archives:** วนลูปผ่านรายการไฟล์เก็บข้อมูลและเรียกใช้ตรรกะการเรนเดอร์เดียวกันเพื่อเพิ่มอัตราการประมวลผล.  
- **Caching strategy:** เก็บ HTML ที่เรนเดอร์ไว้ในแคชหากไฟล์เก็บข้อมูลเดียวกันถูกเข้าถึงบ่อย ลดเวลาการประมวลผลซ้ำได้ถึง 70 %.  

## คำถามที่พบบ่อย
**Q: GroupDocs.Viewer Java คืออะไร?**  
A: GroupDocs.Viewer Java เป็นไลบรารีฝั่งเซิร์ฟเวอร์ที่เรนเดอร์รูปแบบเอกสารและไฟล์เก็บข้อมูลกว่า 50 รูปแบบรวมถึง ZIP และ RAR ให้เป็น HTML, PDF หรือไฟล์รูปภาพโดยไม่ต้องพึ่งพาแอปพลิเคชันภายนอก.

**Q: ฉันจะได้รับลิงก์ทดลองใช้ฟรีของ GroupDocs.Viewer ได้อย่างไร?**  
A: เยี่ยมชม [free trial link](https://releases.groupdocs.com/viewer/java/) เพื่อดาวน์โหลดและทดสอบ.

**Q: ฉันสามารถแปลงประเภทเอกสารอื่น ๆ นอกจากไฟล์เก็บข้อมูลได้หรือไม่?**  
A: ใช่, viewer รองรับ PDFs, Word, Excel, PowerPoint และรูปแบบเพิ่มเติมกว่า 35 รูปแบบ.

**Q: ควรทำอย่างไรหากการเรนเดอร์ช้า?**  
A: ลดจำนวนรายการต่อหน้า, เปิดใช้งานการสตรีม, หรือประมวลผลไฟล์เก็บข้อมูลเป็นชุดเล็ก ๆ เพื่อเพิ่มความเร็ว.

**Q: ฉันจะหาความช่วยเหลือหรือการสนับสนุนได้จากที่ไหน?**  
A: ติดต่อผ่าน [support forum](https://forum.groupdocs.com/c/viewer/9).

**Q: สามารถฝัง CSS และรูปภาพโดยตรงใน HTML ได้หรือไม่?**  
A: แน่นอน—ใช้ `HtmlViewOptions.forEmbeddedResources` ตามตัวอย่าง.

**Q: ฉันจะทำการแปลงหลายไฟล์ในโฟลเดอร์ของไฟล์เก็บข้อมูลอย่างไร?**  
A: วนลูปผ่านแต่ละไฟล์ด้วย `for` loop และใช้การกำหนดค่า `Viewer` และ `HtmlViewOptions` เดียวกันสำหรับแต่ละรอบ.

## แหล่งข้อมูล
- **Documentation:** ศึกษาฟังก์ชันเพิ่มเติมกับ [GroupDocs documentation](https://docs.groupdocs.com/viewer/java/).  
- **API reference:** สำรวจ API ทั้งหมดที่ [GroupDocs API](https://reference.groupdocs.com/viewer/java/).  
- **Download:** ดาวน์โหลดไบนารีล่าสุดจาก [download page](https://releases.groupdocs.com/viewer/java/).  
- **Purchase and licensing:** ตรวจสอบตัวเลือกบน [purchase page](https://purchase.groupdocs.com/buy).  
- **Support and community:** เข้าร่วมการสนทนาที่ [GroupDocs forum](https://forum.groupdocs.com/c/viewer/9).

---

**อัปเดตล่าสุด:** 2026-08-03  
**ทดสอบด้วย:** GroupDocs.Viewer 25.2  
**ผู้เขียน:** GroupDocs

## บทแนะนำที่เกี่ยวข้อง
- [วิธีแปลง zip เป็น HTML และแสดงโฟลเดอร์ zip ใน Java ด้วย GroupDocs.Viewer](/viewer/java/advanced-rendering/render-archive-folders-groupdocs-viewer-java/)
- [แปลง zip เป็น pdf ด้วย GroupDocs.Viewer Java - ชื่อไฟล์กำหนดเอง](/viewer/java/advanced-rendering/groupdocs-viewer-java-custom-filenames-rendering-archives/)
- [วิธีแปลง DOCX เป็น HTML ด้วย GroupDocs.Viewer for Java: คู่มือขั้นตอนโดยละเอียด](/viewer/java/export-conversion/convert-docx-to-html-groupdocs-viewer-java/)