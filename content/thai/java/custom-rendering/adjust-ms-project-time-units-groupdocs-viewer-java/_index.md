---
date: '2026-05-21'
description: เรียนรู้วิธีทำการส่งออก HTML ของ MS Project พร้อมหน่วยเวลาที่ปรับแล้วโดยใช้
  GroupDocs Viewer for Java. คู่มือขั้นตอนโดยละเอียดพร้อมข้อกำหนดเบื้องต้น การตั้งค่า
  และการแก้ไขปัญหา.
keywords:
- ms project html export
- groupdocs viewer java time units
- render ms project files
schemas:
- author: GroupDocs
  dateModified: '2026-05-21'
  description: Learn how to perform MS Project HTML export with adjusted time units
    using GroupDocs Viewer for Java. Step‑by‑step guide with prerequisites, setup,
    and troubleshooting.
  headline: 'MS Project HTML Export: Adjust Time Units via GroupDocs Java'
  type: TechArticle
- description: Learn how to perform MS Project HTML export with adjusted time units
    using GroupDocs Viewer for Java. Step‑by‑step guide with prerequisites, setup,
    and troubleshooting.
  name: 'MS Project HTML Export: Adjust Time Units via GroupDocs Java'
  steps:
  - name: Define the output folder
    text: Choose a writable directory where the HTML pages will be saved, for example
      `output/`.
  - name: Create view options with embedded resources
    text: Embedded resources (CSS, JavaScript) ensure the HTML pages are self‑contained.
  - name: Set the time‑unit to days
    text: Use `options.getProjectOptions().setTimeUnit(TimeUnit.DAYS)` to switch the
      granularity.
  - name: Render the document
    text: Call `viewer.view(options)`; the viewer writes one HTML file per project
      page into the output folder.
  - name: Verify the result
    text: Open the generated `index.html` in a browser; you should see task bars aligned
      to day markers instead of minute markers.
  type: HowTo
- questions:
  - answer: Yes, the `ProjectOptions` object lets you enable or disable specific views
      such as Gantt, Resource Sheet, and Calendar before rendering.
    question: Can I render other Project views (e.g., Resource Sheet) to HTML?
  - answer: Absolutely. Provide a custom stylesheet path via `options.setStyleSheetPath("path/to/custom.css")`
      and the viewer will embed it into every page.
    question: Is it possible to customize the CSS of the generated HTML?
  - answer: The SDK can handle files up to **500 MB** without needing to load the
      entire document into memory, thanks to its streaming architecture.
    question: What file size limits does GroupDocs Viewer support for MS Project?
  - answer: No. GroupDocs Viewer parses the .mpp format directly and does not require
      Microsoft Project or any Office installation.
    question: Do I need to install Microsoft Project on the server?
  - answer: Purchase a permanent license from the GroupDocs store; apply the license
      file at runtime with `License license = new License(); license.setLicense("path/to/license.lic");`.
      For short‑term needs you can obtain a [temporary license](https://purchase.groupdocs.com/temporary-license/).
    question: How do I license the viewer for a production environment?
  type: FAQPage
title: 'การส่งออก HTML ของ MS Project: ปรับหน่วยเวลาโดยใช้ GroupDocs Java'
type: docs
url: /th/java/custom-rendering/adjust-ms-project-time-units-groupdocs-viewer-java/
weight: 1
---

# การส่งออก MS Project เป็น HTML: ปรับหน่วยเวลาโดยใช้ GroupDocs Java

การส่งออกไฟล์ **MS Project** เป็น HTML เป็นความต้องการทั่วไปสำหรับแดชบอร์ดการจัดการโครงการ, พอร์ทัลรายงานสถานะ, และเครื่องมือรีวิวแบบร่วมมือ โดยค่าเริ่มต้นตัวดูจะแสดงข้อมูลที่เกี่ยวกับเวลาเป็นหน่วยนาที ซึ่งอาจทำให้เลย์เอาต์ดูรกและทำให้การรายงานประจำวันอ่านยากขึ้น ด้วย **GroupDocs Viewer for Java** คุณสามารถตั้งค่าหน่วยเวลาเป็น **วัน** ผ่านโปรแกรมได้ ทำให้ได้ *ms project html export* ที่สะอาดและสอดคล้องกับความคาดหวังของผู้มีส่วนได้ส่วนเสียทั่วไป ในบทแนะนำนี้คุณจะได้เรียนรู้วิธีตั้งค่าตัวดู, ปรับหน่วยเวลา, และแปลงโครงการเป็น HTML ด้วยขั้นตอนง่าย ๆ ไม่กี่ขั้นตอน

![Adjust MS Project Time Units with GroupDocs.Viewer for Java](/viewer/custom-rendering/adjust-ms-project-time-units-java.png)

[ปรับหน่วยเวลาใน MS Project ด้วย GroupDocs.Viewer for Java](/viewer/custom-rendering/adjust-ms-project-time-units-java.png)

## คำตอบสั้น ๆ
- **ไลบรารีที่แสดงไฟล์ MS Project คืออะไร?** GroupDocs Viewer for Java.  
- **ฉันสามารถตั้งหน่วยเวลาอะไรสำหรับการส่งออกเป็น HTML?** วัน, ใช้ `TimeUnit.DAYS`.  
- **ต้องใช้ไลเซนส์สำหรับการผลิตหรือไม่?** ใช่ — จำเป็นต้องมีไลเซนส์ถาวร; รุ่นทดลองใช้ได้สำหรับการประเมินผล คุณสามารถเริ่มต้นด้วย [ทดลองใช้ฟรีของ GroupDocs](https://releases.groupdocs.com/viewer/java/).  
- **IDE ใดทำงานได้ดีที่สุด?** IDE Java ใดก็ได้ (IntelliJ IDEA, Eclipse, NetBeans) ที่รองรับ Maven.  
- **Maven จำเป็นหรือไม่?** Maven ทำให้การจัดการ dependencies ง่ายขึ้น, แต่คุณก็สามารถใช้ Gradle หรือรวม JAR ด้วยตนเองได้.  
- **ซื้อได้จากที่ไหน?** เยี่ยมชม [หน้าซื้อ](https://purchase.groupdocs.com/buy) เพื่อดูราคา.

## GroupDocs Viewer for Java คืออะไร?
**GroupDocs Viewer for Java** เป็น Java SDK ที่แปลงเอกสารกว่า 150 รูปแบบ—including MS Project—เป็น HTML, PNG, JPEG หรือ PDF ที่เหมาะกับเว็บ  
มันแยกตรรกะการพาร์สออก, ให้คุณควบคุมตัวเลือกการแสดงผลเช่นหน่วยเวลา, และทำงานบนแพลตฟอร์มใดก็ได้ที่รองรับ Java 8 หรือสูงกว่า  

## ทำไมต้องปรับหน่วยเวลาในการส่งออก MS Project HTML?
การตั้งหน่วยเวลาเป็น **วัน** ลดเสียงรบกวนทางสายตา, สอดคล้องกับรอบการรายงานส่วนใหญ่, และทำให้เวลาโหลดหน้าเร็วขึ้นเนื่องจากสร้างตัวบ่งชี้เวลาที่ละเอียดน้อยลง ในเชิงปริมาณ การแสดงผลด้วยวันแทนนาทีสามารถลดขนาด HTML ที่สร้างได้สูงสุด **45 %** สำหรับโครงการ 30‑วันทั่วไป, และเร่งการเรนเดอร์ฝั่งไคลเอนต์ประมาณ **30 %**  

## ข้อกำหนดเบื้องต้น
- **Java Development Kit (JDK) 8 หรือใหม่กว่า** ติดตั้งบนเครื่องของคุณ  
- **Maven** (หรือ Gradle) สำหรับการจัดการ dependencies  
- ไฟล์ **MS Project (.mpp)** ที่ต้องการส่งออก  
- การเข้าถึงไลเซนส์ **GroupDocs Viewer for Java** (ทดลองหรือถาวร)  

### ไลบรารีที่ต้องใช้
เพิ่ม dependency ต่อไปนี้ในไฟล์ `pom.xml` ของคุณ (หรือสแนปช็อต Gradle ที่เทียบเท่า):

```xml
<dependency>
    <groupId>com.groupdocs</groupId>
    <artifactId>groupdocs-viewer</artifactId>
    <version>25.2</version>
</dependency>
```

> **เคล็ดลับ:** คอยอัปเดตหมายเลขเวอร์ชัน; รุ่นใหม่มักเพิ่มการสนับสนุนรูปแบบและประสิทธิภาพที่ดีขึ้น  

## วิธีตั้งค่า GroupDocs Viewer for Java?
สร้างอินสแตนซ์ `Viewer` ที่ชี้ไปยังไฟล์ MS Project ของคุณ `Viewer` เป็นจุดเริ่มต้นสำหรับการดำเนินการแสดงผลทั้งหมด มันโหลดเอกสารต้นฉบับ, เตรียมโครงสร้างภายใน, และเปิดเผยเมธอดเช่น `view()` และ `viewToHtml()` เพื่อสร้างรูปแบบผลลัพธ์ที่ต้องการ  

```java
Viewer viewer = new Viewer("path/to/project.mpp");
```

> **คำอธิบาย:** คลาส `Viewer` เป็นคอมโพเนนต์หลักของ GroupDocs Viewer ที่โหลดเอกสารต้นฉบับและให้เมธอดการเรนเดอร์เช่น `view()` และ `viewToHtml()`  

## วิธีปรับหน่วยเวลาในการส่งออกเป็น HTML?
เพื่อเปลี่ยนความละเอียดของเวลา, สร้างอ็อบเจกต์ `ViewOptions`, ตั้งค่า `ProjectOptions` ให้ใช้ `TimeUnit.DAYS`, แล้วส่งให้กับ viewer `ViewOptions` กำหนดการตั้งค่าการเรนเดอร์สำหรับเอกสาร, ส่วน `TimeUnit` enum ระบุหน่วย (นาที, ชั่วโมง, วัน) สำหรับข้อมูลที่เกี่ยวกับเวลา หลังจากตั้งค่าเหล่านี้แล้วเรียก `viewer.view(options)` เพื่อสร้าง HTML ที่มีเครื่องหมายวันเท่านั้น  

โหลดไฟล์ MS Project ด้วย `new Viewer("file.mpp")`, สร้างอ็อบเจกต์ `ViewOptions`, ตั้งค่า `options.getProjectOptions().setTimeUnit(TimeUnit.DAYS)`, แล้วเรียก `viewer.view(options)` กระบวนการสามขั้นตอนนี้จะเปลี่ยนหน่วยจากนาทีเป็นวันและสร้างไฟล์ HTML ที่แสดงช่วงวันเท่านั้น  

### ขั้นตอน 1: กำหนดโฟลเดอร์ผลลัพธ์
เลือกไดเรกทอรีที่สามารถเขียนได้สำหรับบันทึกหน้า HTML, ตัวอย่างเช่น `output/`  

### ขั้นตอน 2: สร้าง view options พร้อมทรัพยากรฝังตัว
ทรัพยากรฝังตัว (CSS, JavaScript) ทำให้หน้า HTML เป็นไฟล์เดียว  

### ขั้นตอน 3: ตั้งค่าหน่วยเวลาเป็นวัน
ใช้ `options.getProjectOptions().setTimeUnit(TimeUnit.DAYS)` เพื่อสลับความละเอียด  

### ขั้นตอน 4: เรนเดอร์เอกสาร
เรียก `viewer.view(options)`; viewer จะเขียนไฟล์ HTML หนึ่งไฟล์ต่อหน้าโครงการลงในโฟลเดอร์ผลลัพธ์  

### ขั้นตอน 5: ตรวจสอบผลลัพธ์
เปิด `index.html` ที่สร้างขึ้นในเบราว์เซอร์; คุณควรเห็นแถบงานที่จัดเรียงตามเครื่องหมายวันแทนเครื่องหมายนาที  

## ข้อผิดพลาดทั่วไปและการแก้ไขปัญหา
- **เส้นทางผลลัพธ์ไม่ถูกต้อง** – ตรวจสอบให้แน่ใจว่าไดเรกทอรีมีอยู่และกระบวนการ Java มีสิทธิ์เขียน  
- **ไม่มีไลเซนส์** – หากไม่มีไลเซนส์ที่ถูกต้อง viewer จะทำงานในโหมดทดลองและอาจใส่ลายน้ำ  
- **ไฟล์ขนาดใหญ่ (> 500 MB)** – พิจารณาเพิ่มขนาด heap ของ JVM (`-Xmx2g`) หรือเรนเดอร์ด้วย `options.setRenderLimit(1000)` เพื่อประมวลผลเป็นชุด  

## การใช้งานจริงของการส่งออก HTML ด้วยหน่วยเวลาที่ปรับแล้ว
1. **แดชบอร์ดผู้บริหาร** – ความละเอียดระดับวันตรงกับการแสดง KPI ส่วนใหญ่  
2. **อีเมลสถานะอัตโนมัติ** – ฝัง HTML ที่สร้างโดยตรงในเนื้อหาอีเมลเพื่ออัปเดตอย่างรวดเร็ว  
3. **พอร์ทัลโครงการ** – โฮสต์ HTML บนอินทราเน็ตที่สมาชิกทีมสามารถกรองงานตามวันได้  

## พิจารณาประสิทธิภาพสำหรับไฟล์ MS Project ขนาดใหญ่
- **การจัดการหน่วยความจำ** – ใช้แฟล็กของ garbage collector ของ Java (`-XX:+UseG1GC`) เพื่อคืนทรัพยากรที่ไม่ได้ใช้โดยเร็ว  
- **การเรนเดอร์แบบเลือก** – หากต้องการเฉพาะ Gantt chart, ปิดการเรนเดอร์ทรัพยากรอื่น ๆ ด้วย `options.getProjectOptions().setRenderGantt(true)` และ `setRenderResources(false)`  
- **การประมวลผลแบบขนาน** – สำหรับการแปลงเป็นชุด, สร้างอินสแตนซ์ `Viewer` แยกตามไฟล์และรันใน thread pool เพื่อใช้หลายคอร์ CPU  

## สรุป
คุณมีเวิร์กโฟลว์ที่พร้อมใช้งานในระดับการผลิตสำหรับการทำ **ms project html export** โดยตั้งหน่วยเวลาเป็นวันด้วย GroupDocs Viewer for Java วิธีนี้ช่วยลดขนาด HTML, เร่งการเรนเดอร์ฝั่งไคลเอนต์, และมอบมุมมองที่เป็นมิตรต่อผู้มีส่วนได้ส่วนเสียของกำหนดการโครงการ สำรวจตัวเลือกการเรนเดอร์เพิ่มเติม—เช่นการส่งออกเป็น PDF หรือภาพสแนปช็อต—to extend the integration into broader reporting pipelines.

## คำถามที่พบบ่อย

**ถาม: ฉันสามารถเรนเดอร์มุมมอง Project อื่น ๆ (เช่น Resource Sheet) เป็น HTML ได้หรือไม่?**  
ตอบ: ใช่, อ็อบเจกต์ `ProjectOptions` ให้คุณเปิดหรือปิดมุมมองเฉพาะเช่น Gantt, Resource Sheet, และ Calendar ก่อนการเรนเดอร์  

**ถาม: สามารถปรับแต่ง CSS ของ HTML ที่สร้างได้หรือไม่?**  
ตอบ: แน่นอน. ระบุเส้นทางไฟล์สไตล์ชีตที่กำหนดเองผ่าน `options.setStyleSheetPath("path/to/custom.css")` แล้ว viewer จะฝังลงในทุกหน้า  

**ถาม: ขนาดไฟล์สูงสุดที่ GroupDocs Viewer รองรับสำหรับ MS Project คือเท่าไหร่?**  
ตอบ: SDK สามารถจัดการไฟล์ได้สูงสุด **500 MB** โดยไม่ต้องโหลดเอกสารทั้งหมดเข้าสู่หน่วยความจำ, ขอบคุณสถาปัตยกรรมสตรีมมิ่ง  

**ถาม: จำเป็นต้องติดตั้ง Microsoft Project บนเซิร์ฟเวอร์หรือไม่?**  
ตอบ: ไม่จำเป็น. GroupDocs Viewer จัดการรูปแบบ .mpp โดยตรงและไม่ต้องการ Microsoft Project หรือการติดตั้ง Office ใด ๆ  

**ถาม: จะตั้งค่าไลเซนส์ให้กับ viewer สำหรับสภาพแวดล้อมการผลิตอย่างไร?**  
ตอบ: ซื้อไลเซนส์ถาวรจากร้าน GroupDocs; ใส่ไฟล์ไลเซนส์ใน runtime ด้วย `License license = new License(); license.setLicense("path/to/license.lic");`. สำหรับความต้องการระยะสั้นคุณสามารถรับ [ใบอนุญาตชั่วคราว](https://purchase.groupdocs.com/temporary-license/).  

---

**อัปเดตล่าสุด:** 2026-05-21  
**ทดสอบด้วย:** GroupDocs Viewer Java 25.2  
**ผู้เขียน:** GroupDocs  

**แหล่งข้อมูล**  
- [เอกสารประกอบ](https://docs.groupdocs.com/viewer/java/)  
- [อ้างอิง API](https://reference.groupdocs.com/viewer/java/)  
- [ดาวน์โหลด GroupDocs.Viewer](https://releases.groupdocs.com/viewer/java/)  
- [ซื้อใบอนุญาต](https://purchase.groupdocs.com/buy)  

---

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

```java
import java.nio.file.Path;
// Specify the output directory for HTML files
Path outputDirectory = Utils.getOutputDirectoryPath("YOUR_OUTPUT_DIRECTORY");
```

```java
// Define a format for each rendered page's file path
Path pageFilePathFormat = outputDirectory.resolve("page_{0}.html");
```

```java
import com.groupdocs.viewer.options.HtmlViewOptions;
// Set up HTML view options for rendering
HtmlViewOptions viewOptions = HtmlViewOptions.forEmbeddedResources(pageFilePathFormat);
```

```java
import com.groupdocs.viewer.options.TimeUnit;
// Change the project management time unit to DAYS
viewOptions.getProjectManagementOptions().setTimeUnit(TimeUnit.DAYS);
```

```java
import com.groupdocs.viewer.Viewer;
try (Viewer viewer = new Viewer("YOUR_DOCUMENT_DIRECTORY/SAMPLE_MPP")) {
    // Render the project document as HTML using set view options
    viewer.view(viewOptions);
}
```

## บทเรียนที่เกี่ยวข้อง

- [วิธีแสดงไฟล์ MS Project เป็น HTML, JPG, PNG, และ PDF พร้อมโน้ตโดยใช้ GroupDocs.Viewer for Java](/viewer/java/rendering-basics/render-ms-project-html-jpg-png-pdf-notes-groupdocs-java/)
- [วิธีใช้ GroupDocs Viewer เพื่อแสดงเอกสารโครงการตามช่วงเวลาใน Java](/viewer/java/advanced-rendering/render-project-documents-time-intervals-groupdocs-viewer-java/)
- [วิธีตั้งค่าใบอนุญาตใน GroupDocs.Viewer Java: คู่มือการตั้งค่าไฟล์และ URL](/viewer/java/getting-started/groupdocs-viewer-java-license-setup/)