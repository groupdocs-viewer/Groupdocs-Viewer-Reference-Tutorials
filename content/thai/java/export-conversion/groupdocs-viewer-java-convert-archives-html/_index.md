---
date: '2026-10-10'
description: เรียนรู้วิธีแปลง zip เป็น html ด้วย GroupDocs.Viewer Java, กำหนดจำนวนรายการต่อหน้า,
  ฝัง resources html, และแปลง archives แบบ batch อย่างมีประสิทธิภาพ
images:
- /java/export-conversion/groupdocs-viewer-java-convert-archives-html/og-image.png
keywords:
- how to convert zip
- convert archive to html
- java convert zip html
lastmod: '2026-10-10'
og_description: เรียนรู้วิธีแปลง zip เป็น html ด้วย GroupDocs.Viewer Java, ฝัง resources,
  กำหนดจำนวนรายการต่อหน้า, และ batch‑process archives เพื่อสร้าง web previews ที่เร็วและพกพาได้
og_image_alt: 'Developer guide: convert zip to HTML with GroupDocs.Viewer Java, showing
  pagination and embedded resources'
og_title: แปลง zip เป็น HTML พร้อมการแบ่งหน้าโดยใช้ GroupDocs.Viewer Java
schemas:
- author: GroupDocs
  dateModified: '2026-10-10'
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
title: แปลง zip เป็น html และกำหนดจำนวนรายการต่อหน้าโดยใช้ GroupDocs.Viewer Java
type: docs
url: /th/java/export-conversion/groupdocs-viewer-java-convert-archives-html/
weight: 1
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# แปลง zip เป็น html และตั้งค่ารายการต่อหน้าโดยใช้ GroupDocs.Viewer Java

ในหลายแอปพลิเคชันเว็บคุณต้องการแสดงเนื้อหาของไฟล์ ZIP หรือ RAR โดยตรงในเบราว์เซอร์ **วิธีแปลง zip** เป็น HTML ด้วย GroupDocs.Viewer สำหรับ Java เป็นความต้องการทั่วไป และไลบรารีนี้ให้คุณฝังรูปภาพ, CSS, และฟอนต์เพื่อให้ผลลัพธ์เป็นหน้าเดียวที่พกพาได้ บทแนะนำนี้จะพาคุณผ่านทุกขั้นตอน—from การตั้งค่า Maven ถึงการเรนเดอร์หลายหน้า—พร้อมอธิบายว่าทำไมแต่ละตัวเลือกจึงสำคัญต่อประสิทธิภาพและการใช้งาน

![แปลงไฟล์เก็บข้อมูลเป็น HTML ด้วย GroupDocs.Viewer for Java](/viewer/export-conversion/convert-archives-to-html-java.png)

## คำตอบอย่างรวดเร็ว
- **“set items per page” ควบคุมอะไร?** มันกำหนดจำนวนไฟล์หรือโฟลเดอร์จากอาร์ไคฟ์ที่จะปรากฏในแต่ละหน้า HTML ที่สร้างขึ้น  
- **ฉันสามารถฝังรูปภาพและ CSS ลงใน HTML โดยตรงได้หรือไม่?** ใช่ – ใช้ตัวเลือก `forEmbeddedResources` เพื่อฝังทรัพยากรใน HTML  
- **การแปลงเป็นชุดเป็นไปได้หรือไม่?** แน่นอน; คุณสามารถวนลูปผ่านคอลเลกชันของอาร์ไคฟ์และเรนเดอร์แต่ละไฟล์ด้วยการตั้งค่าเดียวกัน  
- **ฉันต้องใช้ Maven เพื่อใช้ GroupDocs.Viewer หรือไม่?** ใช่, เพิ่ม dependency `groupdocs-viewer` ของ Maven ตามที่แสดงด้านล่าง  
- **รูปแบบผลลัพธ์ที่รองรับคืออะไร?** HTML หน้าหนึ่งและ HTML หลายหน้า ทั้งสองรูปแบบพร้อมใช้งาน และไลบรารีรองรับประเภทอาร์ไคฟ์เข้ามากกว่า 50 ประเภท  

## “set items per page” คืออะไรใน GroupDocs.Viewer?
มันบอกให้ viewer ทราบว่าควรแสดงรายการอาร์ไคฟ์ (ไฟล์หรือโฟลเดอร์) จำนวนเท่าใดในแต่ละหน้า HTML เมื่อคุณสร้างเอกสารหลายหน้า การปรับค่าตัวนี้ช่วยให้คุณสมดุลขนาดหน้าและความเร็วในการนำทาง โดยเฉพาะสำหรับอาร์ไคฟ์ขนาดใหญ่ โดยจำกัดจำนวนข้อมูลที่โหลดต่อหน้าและลดเวลาเรนเดอร์สำหรับผู้ใช้ปลายทาง  

## ทำไมต้องฝัง resources html?
การฝังทรัพยากร (รูปภาพ, CSS, ฟอนต์) ลงในไฟล์ HTML โดยตรงทำให้ได้เอกสารหน้าเดียวที่พกพาได้ซึ่งสามารถเปิดได้โดยไม่ต้องอ้างอิงไฟล์ภายนอก สิ่งนี้เหมาะสำหรับไฟล์แนบอีเมล, การดูแบบออฟไลน์, หรือการฝังผลลัพธ์ลงในหน้าเว็บอื่น ๆ อีกด้วย นอกจากนี้ยังลบความจำเป็นในการจัดการเส้นทางของทรัพยากรภายนอกออกไป  

## ข้อกำหนดเบื้องต้น
- **ไลบรารีที่ต้องการ:** รวม GroupDocs.Viewer เวอร์ชัน 25.2 หรือใหม่กว่า  
- **สภาพแวดล้อม:** ติดตั้งและกำหนดค่า Java Development Kit (JDK)  
- **ความรู้:** พื้นฐาน Java และการจัดการ dependency ของ Maven  

## การตั้งค่า Maven GroupDocs Viewer
เพิ่มรีโพซิทอรีของ GroupDocs และ dependency ของ viewer ลงในไฟล์ `pom.xml` ของคุณ:

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
GroupDocs.Viewer มี **ลิงก์ทดลองใช้ฟรี**, ใบอนุญาตชั่วคราว, หรือตัวเลือกการซื้อเต็มรูปแบบ เลือกสิ่งที่เหมาะกับระยะเวลาโครงการของคุณ  

## การเริ่มต้นพื้นฐาน
`Viewer` class เป็นจุดเริ่มต้นสำหรับการเรนเดอร์เอกสารและอาร์ไคฟ์ หลังจากตั้งค่า Maven แล้ว ให้นำ viewer เข้ามาในโค้ดของคุณ:

```java
import com.groupdocs.viewer.Viewer;
// Your initialization code here
```

## วิธีเรนเดอร์อาร์ไคฟ์เป็น html หน้าหนึ่ง
`HtmlViewOptions` class กำหนดการตั้งค่าสำหรับการส่งออกเป็น HTML เช่น การฝังทรัพยากร โหลดอาร์ไคฟ์, ตั้งค่าตัวเลือก HTML เพื่อฝังทรัพยากร, และเรนเดอร์ทั้งหมดลงในหน้าเดียวที่เป็นอิสระ ซึ่งจะสร้างไฟล์ HTML หน้าเดียวที่มีไฟล์ทั้งหมด, รูปภาพ, CSS, และฟอนต์ พร้อมสำหรับการใช้งานออฟไลน์หรือเป็นไฟล์แนบอีเมล  

**คำตอบโดยตรง:** สร้างอินสแตนซ์ `Viewer` สำหรับไฟล์ ZIP, เรียก `HtmlViewOptions.forEmbeddedResources()`, และเรียก `viewer.view(documentPath, options)`. สิ่งนี้จะสร้างไฟล์ HTML หน้าเดียวที่มีไฟล์ทั้งหมด, รูปภาพ, CSS, และฟอนต์ พร้อมสำหรับการใช้งานออฟไลน์หรือเป็นไฟล์แนบอีเมล  

### ขั้นตอนที่ 1: กำหนดไดเรกทอรีเอาต์พุต
```java
Path outputDirectory = Utils.getOutputDirectoryPath("YOUR_OUTPUT_DIRECTORY");
```

### ขั้นตอนที่ 2: ตั้งชื่อไฟล์สำหรับเอาต์พุตหน้าเดียว
```java
Path pageFilePathFormat = outputDirectory.resolve("RAR_result.html");
```

### ขั้นตอนที่ 3: เริ่มต้น viewer
```java
try (Viewer viewer = new Viewer(TestFiles.SAMPLE_RAR_WITH_FOLDERS)) {
    // Further configuration steps follow
}
```

### ขั้นตอนที่ 4: ตั้งค่าตัวเลือกการเรนเดอร์ (ฝัง resources html)
```java
HtmlViewOptions options = HtmlViewOptions.forEmbeddedResources(pageFilePathFormat);
```

### ขั้นตอนที่ 5: เรนเดอร์เป็นหน้าเดียว
```java
options.setRenderToSinglePage(true);
viewer.view(options);
```

## วิธีเรนเดอร์อาร์ไคฟ์เป็น html หลายหน้าและตั้งค่ารายการต่อหน้า
`HtmlViewOptions` class ยังรองรับการแบ่งหน้า โดยการเรียก `options.setItemsPerPage(N)` คุณบอก viewer ให้แยกอาร์ไคฟ์เป็นหลายไฟล์ HTML แต่ละไฟล์จะแสดงรายการได้สูงสุด **N** รายการ วิธีนี้ช่วยเพิ่มความเร็วในการนำทางสำหรับอาร์ไคฟ์ขนาดใหญ่ในขณะที่ทำให้แต่ละหน้ามีน้ำหนักเบา  

**คำตอบโดยตรง:** ใช้ `HtmlViewOptions.forEmbeddedResources()`, เรียก `options.setItemsPerPage(N)`, และเรนเดอร์อาร์ไคฟ์ Viewer จะสร้างไฟล์ HTML แยกกัน—หนึ่งไฟล์ต่อหน้า—แต่ละไฟล์มีรายการได้สูงสุด **N** รายการ ซึ่งช่วยเพิ่มความเร็วในการนำทางสำหรับอาร์ไคฟ์ขนาดใหญ่  

### ขั้นตอนที่ 1: ใช้ไดเรกทอรีเอาต์พุตซ้ำ
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

### ขั้นตอนที่ 4: ตั้งค่าตัวเลือกหลายหน้า (ฝัง resources html)
```java
HtmlViewOptions options = HtmlViewOptions.forEmbeddedResources(pageFilePathFormat);
```

### ขั้นตอนที่ 5: ตั้งค่ารายการต่อหน้า (คีย์เวิร์ดหลักในแอคชัน)
`options.setItemsPerPage(20); // วิธีแปลง zip archives ด้วย 20 รายการต่อหน้า`

```java
options.getArchiveOptions().setItemsPerPage(10); // Default is 16
viewer.view(options);
```

## การประยุกต์ใช้งานจริง
- **ระบบจัดการเอกสาร:** เพิ่มฟังก์ชันการแสดงตัวอย่างอาร์ไคฟ์โดยไม่ต้องติดตั้ง viewer เพิ่มเติม  
- **พอร์ทัลเว็บ:** ให้ผู้ใช้วิธีที่รวดเร็วและไม่ต้องดาวน์โหลดเพื่อสำรวจเอกสารที่รวมกัน  
- **เครื่องมือการทำงานร่วมกัน:** ให้ทีมตรวจสอบอาร์ไคฟ์ที่แชร์โดยตรงในเบราว์เซอร์  

## พิจารณาด้านประสิทธิภาพ
- **การจัดการทรัพยากร:** รักษาการใช้หน่วยความจำให้ต่ำโดยประมวลผลอาร์ไคฟ์เป็นสตรีม; viewer สามารถจัดการอาร์ไคฟ์ขนาดถึง 500 MB โดยไม่ต้องโหลดไฟล์ทั้งหมดเข้าสู่หน่วยความจำ  
- **แปลงอาร์ไคฟ์เป็นชุด:** วนลูปผ่านรายการไฟล์อาร์ไคฟ์และเรียกตรรกะการเรนเดอร์เดียวกันเพื่อเพิ่มอัตราการทำงานสูงสุด  
- **กลยุทธ์การแคช:** เก็บ HTML ที่เรนเดอร์ไว้ในแคชหากอาร์ไคฟ์เดียวกันถูกเข้าถึงบ่อย ลดเวลาการประมวลผลซ้ำได้ถึง 70 %  

## คำถามที่พบบ่อย
**Q: GroupDocs.Viewer Java คืออะไร?**  
A: GroupDocs.Viewer Java เป็นไลบรารีฝั่งเซิร์ฟเวอร์ที่เรนเดอร์เอกสารและอาร์ไคฟ์กว่า 50 รูปแบบ—including ZIP and RAR—เป็น HTML, PDF หรือไฟล์รูปภาพโดยไม่ต้องใช้แอปพลิเคชันภายนอก  

**Q: ฉันจะได้รับลิงก์ทดลองใช้ฟรีของ GroupDocs.Viewer ได้อย่างไร?**  
A: ไปที่ [ลิงก์ทดลองใช้ฟรี](https://releases.groupdocs.com/viewer/java/) เพื่อดาวน์โหลดและทดสอบ  

**Q: ฉันสามารถแปลงประเภทเอกสารอื่น ๆ นอกจากอาร์ไคฟ์ได้หรือไม่?**  
A: ใช่, viewer รองรับ PDF, Word, Excel, PowerPoint, และรูปแบบเพิ่มเติมกว่า 35 รูปแบบ  

**Q: ควรทำอย่างไรหากการเรนเดอร์ช้า?**  
A: ลดจำนวนรายการต่อหน้า, เปิดใช้งานการสตรีม, หรือประมวลผลอาร์ไคฟ์เป็นชุดเล็ก ๆ เพื่อเพิ่มความเร็ว  

**Q: ฉันจะหาแนวทางช่วยเหลือหรือสนับสนุนได้จากที่ไหน?**  
A: ติดต่อผ่าน [ฟอรั่มสนับสนุน](https://forum.groupdocs.com/c/viewer/9)  

**Q: สามารถฝัง CSS และรูปภาพโดยตรงใน HTML ได้หรือไม่?**  
A: แน่นอน—ใช้ `HtmlViewOptions.forEmbeddedResources` ตามตัวอย่างที่แสดง  

**Q: ฉันจะแปลงโฟลเดอร์ของอาร์ไคฟ์เป็นชุดอย่างไร?**  
A: วนลูปผ่านแต่ละไฟล์ด้วย `for` loop, ใช้การตั้งค่า `Viewer` และ `HtmlViewOptions` เดียวกันสำหรับแต่ละรอบ  

**Q: ฉันสามารถหารือปัญหากับผู้ใช้คนอื่นได้ที่ไหน?**  
A: ไปที่ [ฟอรั่ม GroupDocs](https://forum.groupdocs.com/c/viewer/9) เพื่อการสนทนาชุมชน  

## แหล่งข้อมูล
- **เอกสาร:** ศึกษาฟังก์ชันเพิ่มเติมกับ [เอกสาร GroupDocs](https://docs.groupdocs.com/viewer/java/)  
- **อ้างอิง API:** สำรวจ API ทั้งหมดที่ [GroupDocs API](https://reference.groupdocs.com/viewer/java/)  
- **ดาวน์โหลด:** รับไบนารีล่าสุดจาก [หน้าดาวน์โหลด](https://releases.groupdocs.com/viewer/java/)  
- **การซื้อและใบอนุญาต:** ตรวจสอบตัวเลือกบน [หน้าการซื้อ](https://purchase.groupdocs.com/buy)  
- **สนับสนุนและชุมชน:** เข้าร่วมการสนทนาที่ [ฟอรั่มสนับสนุน](https://forum.groupdocs.com/c/viewer/9)  
- **ฟอรั่ม GroupDocs:** เข้าถึงความช่วยเหลือจากชุมชนที่ [ฟอรั่ม GroupDocs](https://forum.groupdocs.com/c/viewer/9)  

---

**อัปเดตล่าสุด:** 2026-10-10  
**ทดสอบด้วย:** GroupDocs.Viewer 25.2  
**ผู้เขียน:** GroupDocs

## บทแนะนำที่เกี่ยวข้อง
- [วิธีแปลง zip เป็น HTML และเรนเดอร์โฟลเดอร์ zip ใน Java ด้วย GroupDocs.Viewer](/viewer/java/advanced-rendering/render-archive-folders-groupdocs-viewer-java/)
- [แปลง zip เป็น pdf ด้วย GroupDocs.Viewer Java - ชื่อไฟล์กำหนดเอง](/viewer/java/advanced-rendering/groupdocs-viewer-java-custom-filenames-rendering-archives/)
- [วิธีแปลง DOCX เป็น HTML ด้วย GroupDocs.Viewer for Java: คู่มือขั้นตอนโดยละเอียด](/viewer/java/export-conversion/convert-docx-to-html-groupdocs-viewer-java/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}