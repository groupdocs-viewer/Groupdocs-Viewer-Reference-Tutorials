---
date: '2026-02-23'
description: เรียนรู้วิธีตั้งค่าจำนวนรายการต่อหน้า, ฝังทรัพยากร HTML, และแปลงไฟล์เก็บข้อมูลเป็น
  HTML หน้าเดียวหรือหลายหน้าเป็นชุดโดยใช้ GroupDocs.Viewer Java.
keywords:
- convert archives to HTML Java
- GroupDocs.Viewer Java tutorial
- render ZIP RAR to HTML
title: 'ตั้งค่าจำนวนรายการต่อหน้า: แปลงไฟล์อาร์ไคฟ์เป็น HTML ด้วย GroupDocs.Viewer
  Java'
type: docs
url: /th/java/export-conversion/groupdocs-viewer-java-convert-archives-html/
weight: 1
---

23  
**ทดสอบด้วย:** GroupDocs.Viewer 25.2  
**ผู้เขียน:** GroupDocs

Now ensure all headings and lists preserved.

Check for any leftover English text not translated: "Single‑page HTML Java" maybe keep as is? It's a term. In headings we left "Single‑Page HTML". That's fine.

Also "Multi‑Page HTML Java". Keep.

Now produce final markdown content.# ตั้งค่ารายการต่อหน้า: แปลงไฟล์เก็บข้อมูลเป็น HTML ด้วย GroupDocs.Viewer Java

การแปลงไฟล์เก็บข้อมูลเช่น ZIP หรือ RAR ให้เป็น HTML ที่เหมาะกับเว็บเป็นความต้องการที่พบบ่อยเมื่อคุณต้องการแชร์หรือรีวิวเอกสารโดยตรงในเบราว์เซอร์ ในคู่มือนี้คุณจะได้เรียนรู้ **วิธีตั้งค่ารายการต่อหน้า** ขณะเรนเดอร์ไฟล์เก็บข้อมูล วิธีฝังทรัพยากร HTML เพื่อผลลัพธ์แบบอิสระ และวิธีแปลงไฟล์เก็บข้อมูลเป็นชุดอย่างมีประสิทธิภาพด้วย GroupDocs.Viewer Java

![แปลงไฟล์เก็บข้อมูลเป็น HTML ด้วย GroupDocs.Viewer สำหรับ Java](/viewer/export-conversion/convert-archives-to-html-java.png)

## คำตอบอย่างรวดเร็ว
- **“set items per page” ควบคุมอะไร?** It determines how many files or folders from an archive appear on each generated HTML page.  
- **ฉันสามารถฝังรูปภาพและ CSS ลงใน HTML โดยตรงได้หรือไม่?** Yes – use the `forEmbeddedResources` option to embed resources HTML.  
- **การแปลงเป็นชุดเป็นไปได้หรือไม่?** Absolutely; you can loop over a collection of archives and render each one with the same settings.  
- **ฉันต้องใช้ Maven เพื่อใช้ GroupDocs.Viewer หรือไม่?** Yes, add the `maven groupdocs viewer` dependency as shown below.  
- **รูปแบบผลลัพธ์ที่รองรับคืออะไร?** Single‑page HTML Java and multi‑page HTML Java are both available.

## “set items per page” คืออะไรใน GroupDocs.Viewer?
การตั้งค่า **set items per page** เป็นส่วนหนึ่งของตัวเลือกการเรนเดอร์ไฟล์เก็บข้อมูล มันบอกให้ viewer ว่าจะแสดงรายการในไฟล์เก็บข้อมูล (ไฟล์หรือโฟลเดอร์) จำนวนเท่าใดบนแต่ละหน้า HTML เมื่อคุณสร้างเอกสาร HTML แบบหลายหน้า การปรับค่าตัวนี้ช่วยให้คุณสมดุลขนาดหน้าและความเร็วในการนำทาง โดยเฉพาะกับไฟล์เก็บข้อมูลขนาดใหญ่

## ทำไมต้องฝังทรัพยากร HTML?
การฝังทรัพยากร (รูปภาพ, CSS, ฟอนต์) โดยตรงในไฟล์ HTML ทำให้ได้เอกสารเดียวที่พกพาได้ซึ่งสามารถเปิดได้โดยไม่ต้องอ้างอิงไฟล์ภายนอก เหมาะสำหรับแนบอีเมล, การดูแบบออฟไลน์, หรือการฝังผลลัพธ์ลงในหน้าเว็บอื่น

## ข้อกำหนดเบื้องต้น
- **ไลบรารีที่จำเป็น:** รวม GroupDocs.Viewer เวอร์ชัน 25.2 หรือใหม่กว่า  
- **สภาพแวดล้อม:** ติดตั้งและกำหนดค่า Java Development Kit (JDK) แล้ว  
- **ความรู้:** พื้นฐาน Java และการจัดการ dependency ของ Maven  

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
GroupDocs.Viewer มี **free trial link**, ใบอนุญาตชั่วคราว หรือทางเลือกการซื้อเต็มรูปแบบ เลือกตัวที่เหมาะกับระยะเวลาของโครงการของคุณ

### การเริ่มต้นพื้นฐาน
หลังจากตั้งค่า Maven แล้ว นำ viewer เข้าสู่โค้ดของคุณ:

```java
import com.groupdocs.viewer.Viewer;
// Your initialization code here
```

## วิธีเรนเดอร์ไฟล์เก็บข้อมูลเป็น Single‑Page HTML

### ขั้นตอนที่ 1: กำหนดไดเรกทอรีเอาต์พุต
```java
Path outputDirectory = Utils.getOutputDirectoryPath("YOUR_OUTPUT_DIRECTORY");
```

### ขั้นตอนที่ 2: ตั้งชื่อไฟล์สำหรับ Single‑Page Output
```java
Path pageFilePathFormat = outputDirectory.resolve("RAR_result.html");
```

### ขั้นตอนที่ 3: เริ่มต้น Viewer
```java
try (Viewer viewer = new Viewer(TestFiles.SAMPLE_RAR_WITH_FOLDERS)) {
    // Further configuration steps follow
}
```

### ขั้นตอนที่ 4: กำหนดค่า Rendering Options (embed resources HTML)
```java
HtmlViewOptions options = HtmlViewOptions.forEmbeddedResources(pageFilePathFormat);
```

### ขั้นตอนที่ 5: เรนเดอร์เป็นหน้าเดียว
```java
options.setRenderToSinglePage(true);
viewer.view(options);
```

## วิธีเรนเดอร์ไฟล์เก็บข้อมูลเป็น Multi‑Page HTML และตั้งค่ารายการต่อหน้า

### ขั้นตอนที่ 1: ใช้ไดเรกทอรีเอาต์พุตเดิม
```java
Path outputDirectory = Utils.getOutputDirectoryPath("YOUR_OUTPUT_DIRECTORY");
```

### ขั้นตอนที่ 2: กำหนดรูปแบบชื่อไฟล์สำหรับหลายหน้า
```java
Path pageFilePathFormat = outputDirectory.resolve("RAR_result_page_{0}.html");
```

### ขั้นตอนที่ 3: เริ่มต้น Viewer อีกครั้ง
```java
try (Viewer viewer = new Viewer(TestFiles.SAMPLE_RAR_WITH_FOLDERS)) {
    // Continue with multi‑page configuration
}
```

### ขั้นตอนที่ 4: กำหนดค่า Multi‑Page Options (embed resources HTML)
```java
HtmlViewOptions options = HtmlViewOptions.forEmbeddedResources(pageFilePathFormat);
```

### ขั้นตอนที่ 5: ตั้งค่ารายการต่อหน้า (primary keyword in action)
```java
options.getArchiveOptions().setItemsPerPage(10); // Default is 16
viewer.view(options);
```

## การประยุกต์ใช้งานจริง
- **Document Management Systems:** เพิ่มฟังก์ชันการแสดงตัวอย่างไฟล์เก็บข้อมูลโดยไม่ต้องติดตั้ง viewer เพิ่มเติม  
- **Web Portals:** ให้ผู้ใช้เข้าถึงวิธีที่รวดเร็วและไม่ต้องดาวน์โหลดเพื่อสำรวจเอกสารที่บรรจุไว้  
- **Collaboration Tools:** ให้ทีมตรวจสอบไฟล์เก็บข้อมูลที่แชร์โดยตรงในเบราว์เซอร์  

## ข้อควรพิจารณาด้านประสิทธิภาพ
- **Resource Management:** ติดตามการใช้หน่วยความจำ; พิจารณาปรับจูน garbage‑collector ของ JVM สำหรับชุดงานขนาดใหญ่  
- **Batch Convert Archives:** วนลูปผ่านรายการไฟล์เก็บข้อมูลและเรียกใช้ตรรกะการเรนเดอร์เดียวกันเพื่อเพิ่มอัตราการประมวลผลสูงสุด  
- **Caching Strategy:** เก็บ HTML ที่เรนเดอร์ไว้ในแคชหากไฟล์เก็บข้อมูลเดียวกันถูกเข้าถึงบ่อย  

## คำถามที่พบบ่อย

**Q: GroupDocs.Viewer Java คืออะไร?**  
A: ไลบรารีที่หลากหลายสำหรับการเรนเดอร์เอกสาร—รวมถึงไฟล์เก็บข้อมูล—เป็นรูปแบบต่าง ๆ เช่น HTML, PDF, และรูปภาพ.

**Q: ฉันจะได้รับ free trial ของ GroupDocs.Viewer อย่างไร?**  
A: เยี่ยมชม [free trial link](https://releases.groupdocs.com/viewer/java/) เพื่อดาวน์โหลดและทดสอบ

**Q: ฉันสามารถแปลงประเภทเอกสารอื่น ๆ นอกจากไฟล์เก็บข้อมูลได้หรือไม่?**  
A: ใช่, viewer รองรับ PDF, Word, Excel, และรูปแบบอื่น ๆ อีกมาก

**Q: ควรทำอย่างไรหากการเรนเดอร์ช้า?**  
A: ลดจำนวนรายการต่อหน้า, เปิดใช้งานการสตรีม, หรือประมวลผลไฟล์เก็บข้อมูลเป็นชุดเล็กลง

**Q: ฉันจะขอความช่วยเหลือหรือสนับสนุนได้จากที่ไหน?**  
A: ติดต่อผ่าน [support forum](https://forum.groupdocs.com/c/viewer/9).

**Q: สามารถฝัง CSS และรูปภาพโดยตรงใน HTML ได้หรือไม่?**  
A: แน่นอน—ใช้ `HtmlViewOptions.forEmbeddedResources` ตามตัวอย่าง

**Q: ฉันจะแปลงโฟลเดอร์ของไฟล์เก็บข้อมูลเป็นชุดอย่างไร?**  
A: วนลูปผ่านแต่ละไฟล์ด้วย `for` loop, ใช้การกำหนดค่า `Viewer` และ `HtmlViewOptions` เดียวกันสำหรับแต่ละรอบ

## แหล่งข้อมูล
- **Documentation:** ศึกษาฟังก์ชันเพิ่มเติมกับ [GroupDocs documentation](https://docs.groupdocs.com/viewer/java/).  
- **API Reference:** สำรวจ API ทั้งหมดที่ [GroupDocs API](https://reference.groupdocs.com/viewer/java/).  
- **Download:** ดาวน์โหลดไบนารีล่าสุดจาก [download page](https://releases.groupdocs.com/viewer/java/).  
- **Purchase and Licensing:** ตรวจสอบตัวเลือกบน [purchase page](https://purchase.groupdocs.com/buy).  
- **Support and Community:** เข้าร่วมการสนทนาที่ [GroupDocs forum](https://forum.groupdocs.com/c/viewer/9).

---

**อัปเดตล่าสุด:** 2026-02-23  
**ทดสอบด้วย:** GroupDocs.Viewer 25.2  
**ผู้เขียน:** GroupDocs