---
date: '2026-08-30'
description: เรียนรู้วิธีแปลง DWG เป็น PNG, ตั้งค่าสีพื้นหลังใน Java, และปรับขนาดภาพด้วย
  GroupDocs.Viewer for Java.
keywords:
- convert dwg to png
- set background color java
- change cad background color
- java convert cad png
lastmod: '2026-08-30'
og_description: แปลง DWG เป็น PNG ด้วย GroupDocs.Viewer for Java พร้อมกำหนดความกว้างของภาพและสีพื้นหลังตามต้องการ
  คู่มือนี้ให้ขั้นตอนการตั้งค่า, ตัวอย่างโค้ด, และเคล็ดลับการแก้ไขปัญหา.
og_image_alt: 'Guide: converting DWG to PNG with custom size and background color
  using GroupDocs.Viewer for Java'
og_title: แปลง DWG เป็น PNG ด้วยขนาดกำหนดเองและสีพื้นหลังใน Java
schemas:
- author: GroupDocs
  dateModified: '2026-08-30'
  description: Learn how to convert DWG to PNG, set background color Java, and customize
    image size with GroupDocs.Viewer for Java.
  headline: How to convert DWG to PNG with custom size & background color using GroupDocs.Viewer
    for Java
  type: TechArticle
- questions:
  - answer: Yes, GroupDocs.Viewer supports DXF, DWF, and several additional CAD formats.
    question: Can I render other CAD formats besides DWG?
  - answer: Instantiate a new `Color` with `new Color(123, 45, 67)` and pass it to
      `setBackgroundColor`.
    question: How do I use a custom RGB color instead of a predefined constant?
  - answer: You can specify layout or layer options via `CadOptions` before calling
      `viewer.view`.
    question: Is it possible to render only a specific layout or layer?
  - answer: Set the background color to `new Color(0,0,0,0)` for full transparency
      if the output format supports it.
    question: Does the library support transparent backgrounds?
  - answer: The tutorial uses version 25.2, but newer releases retain the same API
      surface.
    question: What version of GroupDocs.Viewer is required?
  type: FAQPage
tags:
- convert dwg
- GroupDocs.Viewer
- Java CAD rendering
- custom PNG output
title: วิธีแปลง DWG เป็น PNG ด้วยขนาดกำหนดเองและสีพื้นหลังโดยใช้ GroupDocs.Viewer
  for Java
type: docs
url: /th/java/advanced-rendering/render-cad-drawings-custom-png-groupdocs-java/
weight: 1
---

# วิธีแปลง DWG เป็น PNG ด้วยขนาดที่กำหนดเองและสีพื้นหลังโดยใช้ GroupDocs.Viewer สำหรับ Java

ในบทแนะนำนี้คุณจะได้เรียนรู้ **วิธีแปลง DWG เป็น PNG** พร้อมการควบคุมขนาดของผลลัพธ์และสีพื้นหลังโดยใช้ GroupDocs.Viewer สำหรับ Java ไม่ว่าคุณจะต้องการฝังภาพวาด CAD ในรายงาน, สร้างภาพย่อสำหรับพอร์ทัลเว็บ, หรือทำการเรนเดอร์เป็นชุดอัตโนมัติ ขั้นตอนต่อไปนี้จะให้คุณควบคุมลักษณะภาพของไฟล์ PNG แต่ละไฟล์ได้อย่างเต็มที่

## คำตอบอย่างรวดเร็ว
- **อะไรหมายถึง “convert DWG to PNG”?** เป็นกระบวนการแปลงไฟล์ DWG CAD ให้เป็นภาพ PNG ผ่านโค้ด โดยคงรายละเอียดเวกเตอร์เป็นพิกเซลแบบแรสเตอร์  
- **ฉันสามารถกำหนดความกว้างที่กำหนดเองได้หรือไม่?** ใช่ – เรียก `CadOptions.forRenderingByWidth(int width)` เพื่อกำหนดความกว้างพิกเซลที่ต้องการ  
- **ฉันจะเปลี่ยนสีพื้นหลังได้อย่างไร?** ใช้ `cadOptions.setBackgroundColor(Color.YOUR_COLOR)` ก่อนทำการเรนเดอร์  
- **ต้องใช้ไลบรารีใด?** GroupDocs.Viewer for Java (เวอร์ชัน 25.2 หรือใหม่กว่า)  
- **ฉันต้องมีลิขสิทธิ์หรือไม่?** ลิขสิทธิ์ชั่วคราวหรือเต็มจะลบข้อจำกัดการประเมินและเปิดใช้งานการเรนเดอร์ไม่จำกัด  

![Render CAD Drawings as PNG with Custom Size & Background Color with GroupDocs.Viewer for Java](/viewer/advanced-rendering/render-cad-drawings-as-png-with-custom-size-background-color-java.png)

## GroupDocs.Viewer for Java คืออะไร?
GroupDocs.Viewer for Java เป็น API ฝั่งเซิร์ฟเวอร์ที่เรนเดอร์ไฟล์กว่า 150 รูปแบบ—including CAD files—เป็นภาพ, PDF หรือ HTML ทำงานโดยไม่ต้องพึ่งซอฟต์แวร์ของบุคคลที่สามเช่น AutoCAD ทำให้เหมาะสำหรับกระบวนการอัตโนมัติ

## วิธีแปลง DWG เป็น PNG ด้วยขนาดและสีพื้นหลังที่กำหนดเอง
โหลดไฟล์ DWG ด้วยอินสแตนซ์ `Viewer`, ตั้งค่า `CadOptions` สำหรับความกว้างและสีพื้นหลังที่ต้องการ, แล้วเรียก `viewer.view` ด้วย `PngViewOptions`. กระบวนการสามขั้นตอนนี้จัดการ I/O ของไฟล์, การเรนเดอร์, และการตั้งชื่อผลลัพธ์ในหนึ่งการดำเนินการที่ใช้หน่วยความจำอย่างมีประสิทธิภาพ  

Viewer เป็นคลาสหลักที่โหลดเอกสารและทำการเรนเดอร์  
CadOptions กำหนดค่าการตั้งค่าเฉพาะ CAD เช่น ความกว้างของภาพและสีพื้นหลัง  
PngViewOptions กำหนดรูปแบบการส่งออก PNG และรูปแบบการตั้งชื่อสำหรับหน้าที่เรนเดอร์  

คุณสามารถเรนเดอร์ภาพวาด DWG ใดก็ได้เป็น PNG ที่มีความกว้างตรงตามที่คุณระบุ, และคุณสามารถเลือกสีพื้นหลังแบบทึบใดก็ได้ (หรือโปร่งใส) เพื่อให้ตรงกับแบรนด์หรือธีม UI ของคุณ

## ทำไมต้องตั้งค่าสีพื้นหลังที่กำหนดเอง?
การตั้งค่าสีพื้นหลังทำให้ PNG ที่เรนเดอร์ผสมผสานอย่างราบรื่นกับองค์ประกอบ UI รอบข้าง, ป้องกันขอบสีขาวที่ไม่ต้องการ, และสามารถเน้นรายละเอียดของภาพวาดที่อาจหายไปบนผืนผ้าใบสีขาวเริ่มต้นได้ GroupDocs.Viewer รองรับ `java.awt.Color` ใดก็ได้ รวมถึงค่า RGB ที่กำหนดเอง, ให้คุณควบคุมพิกเซลได้อย่างแม่นยำ  

java.awt.Color แสดงค่าของสีที่ใช้สำหรับการเรนเดอร์พื้นหลัง

## ข้อกำหนดเบื้องต้น
- **Java Development Kit (JDK) 8+** – API นี้รองรับ Java 8 และใหม่กว่า  
- **Maven** – สำหรับการจัดการ dependencies  
- **IDE** – IntelliJ IDEA, Eclipse หรือเครื่องมือแก้ไขใดก็ได้ที่คุณชอบ  
- **Basic Java file‑handling knowledge** – เพื่ออ่านไฟล์ DWG ต้นฉบับและเขียนผลลัพธ์ PNG  

## การตั้งค่า GroupDocs.Viewer สำหรับ Java
เพิ่มรีโพซิทอรีของ GroupDocs และ dependency ของ Viewer ลงในไฟล์ `pom.xml` ของ Maven ของคุณ:  

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

### การรับลิขสิทธิ์
รับคีย์ลิขสิทธิ์ชั่วคราวหรือเต็มจากพอร์ทัลของ GroupDocs แล้ววางไฟล์ `license.lic` ไว้ในโฟลเดอร์ resources ของโปรเจกต์ของคุณ สิ่งนี้จะลบข้อจำกัดการประเมิน 20 หน้าและเปิดใช้งานการเรนเดอร์ความละเอียดเต็ม  

### การเริ่มต้นและตั้งค่าเบื้องต้น
สร้างอินสแตนซ์ `Viewer` ที่ชี้ไปยังโฟลเดอร์ที่มีไฟล์ DWG ของคุณ:  

```java
import com.groupdocs.viewer.Viewer;
import java.nio.file.Path;

Path documentPath = Path.of("YOUR_DOCUMENT_DIRECTORY/SAMPLE_DWG_WITH_LAYOUTS_AND_LAYERS");
try (Viewer viewer = new Viewer(documentPath.toString())) {
    // Rendering operations go here
}
```

## ฟีเจอร์ 1: การเรนเดอร์ภาพวาด CAD ด้วยขนาดภาพและสีพื้นหลังที่กำหนดเอง
### วิธีเปลี่ยนสีพื้นหลังของ CAD
เพื่อเปลี่ยนสีพื้นหลังของ CAD, ตั้งค่าอ็อบเจ็กต์ CadOptions ก่อนทำการเรนเดอร์. กำหนดความกว้างที่ต้องการด้วย `forRenderingByWidth` และใช้ `setBackgroundColor` เพื่อกำหนดสีพื้นหลังใหม่. Viewer จะสร้างภาพ PNG ที่สะท้อนสีที่ระบุ, ทำให้สไตล์ภาพที่สอดคล้องกันในทุกไฟล์ผลลัพธ์  

#### การดำเนินการแบบขั้นตอน
##### นำเข้าชุดแพ็กเกจที่จำเป็น
```java
import com.groupdocs.viewer.Viewer;
import com.groupdocs.viewer.options.CadOptions;
import com.groupdocs.viewer.options.PngViewOptions;
import java.nio.file.Path;
import java.awt.Color;
```

##### ตั้งค่าไดเรกทอรีผลลัพธ์และรูปแบบเส้นทางไฟล์
```java
Path outputDirectory = Path.of("YOUR_OUTPUT_DIRECTORY/SetImageBackgroundColor");
Path pageFilePathFormat = outputDirectory.resolve("page_{0}.png");
```

##### เริ่มต้น viewer ด้วยตัวเลือกการเรนเดอร์ที่กำหนดเอง
```java
try (Viewer viewer = new Viewer("YOUR_DOCUMENT_DIRECTORY/SAMPLE_DWG_WITH_LAYOUTS_AND_LAYERS")) {
    PngViewOptions options = new PngViewOptions(pageFilePathFormat);
    
    // Specify the width for rendering
    CadOptions cadOptions = CadOptions.forRenderingByWidth(800);
    cadOptions.setBackgroundColor(Color.GREEN);
    
    options.setCadOptions(cadOptions);

    viewer.view(options);
}
```

**คำอธิบายพารามิเตอร์**  
- `PngViewOptions` – กำหนดรูปแบบการส่งออก PNG และรูปแบบการตั้งชื่อ  
- `forRenderingByWidth(int width)` – บังคับให้เรนเดอร์สร้างภาพที่ความกว้างตรงกับค่าพิกเซลที่ระบุ; ความสูงจะสเกลตามสัดส่วน  
- `setBackgroundColor(Color color)` – เขียนทับผืนพื้นสีขาวเริ่มต้นด้วยสีที่คุณเลือก, ปรับปรุงความสอดคล้องของภาพที่สร้างขึ้น  

#### เคล็ดลับการแก้ไขปัญหา
- ตรวจสอบให้แน่ใจว่าโฟลเดอร์ผลลัพธ์มีอยู่; ใช้ `Files.createDirectories(outputDir)` หากไม่มี  
- ตรวจสอบว่าเส้นทางไฟล์อินพุตถูกต้องและแอปพลิเคชันมีสิทธิ์อ่าน  

## ฟีเจอร์ 2: การตั้งค่าสีพื้นหลังในตัวเลือกการเรนเดอร์
### วิธีตั้งค่าสีพื้นหลังของ PNG
การตั้งค่าสีพื้นหลังของ PNG เกี่ยวข้องกับการสร้างอินสแตนซ์ Color และกำหนดให้กับ CadOptions ก่อนทำการเรนเดอร์. สิ่งนี้ทำให้ PNG ที่สร้างแต่ละไฟล์ใช้พื้นหลังที่ระบุ, ตรงกับแนวทางแบรนด์หรือธีม UI ของคุณ. คุณสามารถใช้ค่าคงที่ที่กำหนดไว้ล่วงหน้าหรือกำหนดค่า RGB ที่กำหนดเองเพื่อการควบคุมที่แม่นยำ  

java.awt.Color แสดงค่าของสีที่ใช้สำหรับการเรนเดอร์พื้นหลัง  

#### การดำเนินการแบบขั้นตอน
##### นำเข้าชุดแพ็กเกจที่จำเป็น
```java
import com.groupdocs.viewer.Viewer;
import com.groupdocs.viewer.options.CadOptions;
import com.groupdocs.viewer.options.PngViewOptions;
import java.nio.file.Path;
import java.awt.Color;
```

##### ตั้งค่าตัวเลือกการเรนเดอร์พร้อมสีพื้นหลัง
```java
Path outputDirectory = Path.of("YOUR_OUTPUT_DIRECTORY/SetImageBackgroundColor");
Path pageFilePathFormat = outputDirectory.resolve("page_{0}.png");

try (Viewer viewer = new Viewer("YOUR_DOCUMENT_DIRECTORY/SAMPLE_DWG_WITH_LAYOUTS_AND_LAYERS")) {
    PngViewOptions options = new PngViewOptions(pageFilePathFormat);
    
    CadOptions cadOptions = CadOptions.forRenderingByWidth(800);
    cadOptions.setBackgroundColor(Color.GREEN);
    
    options.setCadOptions(cadOptions);
    
    viewer.view(options);
}
```

**ตัวเลือกการกำหนดค่าหลัก**  
- ปรับ `forRenderingByWidth(int width)` สำหรับมิติที่ต่างกัน, เช่น 800 px สำหรับภาพย่อเว็บหรือ 1920 px สำหรับการพิมพ์ความละเอียดสูง  
- ใช้ค่าคงที่ `Color` ใดก็ได้ที่กำหนดไว้ล่วงหน้า (เช่น `Color.LIGHT_GRAY`) หรือสร้างอินสแตนซ์แบบกำหนดเองด้วย `new Color(r, g, b)` เพื่อการสร้างแบรนด์ที่แม่นยำ  

## การประยุกต์ใช้งานจริง
### 1. เอกสารวิศวกรรม
การเรนเดอร์แบบกำหนดเองทำให้แน่ใจว่าภาพวาดทุกภาพสอดคล้องกับแนวทางสไตล์ของบริษัท, ลดการแก้ไขภาพด้วยมือหลังการส่งออก  

### 2. การแสดงผลสถาปัตยกรรม
นำเสนอแบบแปลนด้วยพื้นหลังที่ตรงกับสไลด์เด็คหรือพอร์ทัลที่ลูกค้าเห็น, ปรับปรุงความสอดคล้องของภาพ  

### 3. การทำต้นแบบการผลิต
สร้าง PNG สำหรับกระบวนการทำต้นแบบอย่างรวดเร็วที่เครื่องมือต่อไปต้องการขนาดภาพและพื้นหลังที่กำหนด  

### ความเป็นไปได้ในการรวมระบบ
ผสานท่อการเรนเดอร์นี้กับระบบจัดการเอกสาร (เช่น SharePoint) เพื่อสร้างภาพตัวอย่างโดยอัตโนมัติเมื่อมีการอัปโหลดไฟล์ DWG  

## พิจารณาด้านประสิทธิภาพ
### การเพิ่มประสิทธิภาพ
- **การประมวลผลเป็นชุด:** วนลูปผ่านไดเรกทอรีของไฟล์ DWG และเรนเดอร์แต่ละไฟล์ต่อเนื่องเพื่อกระจายค่าใช้จ่ายการอุ่นเครื่องของ JVM  
- **การจัดการทรัพยากร:** สำหรับภาพวาดขนาดใหญ่ (500+ หน้า), เพิ่ม heap ของ JVM (`-Xmx2g`) หรือประมวลผลไฟล์เป็นชุดเล็ก ๆ เพื่อหลีกเลี่ยงข้อผิดพลาด out‑of‑memory  

### แนวทางการใช้ทรัพยากร
ตรวจสอบการใช้ CPU และหน่วยความจำด้วยเครื่องมือเช่น VisualVM; ปล่อยอินสแตนซ์ `Viewer` อย่างทันท่วงทีโดยใช้ try‑with‑resources  

### แนวทางปฏิบัติที่ดีที่สุดสำหรับการจัดการหน่วยความจำใน Java
- ใช้ try‑with‑resources (ตามตัวอย่าง) เพื่อปิด `Viewer` อัตโนมัติ  
- หลีกเลี่ยงการเก็บอ็อบเจ็กต์ `Path` ขนาดใหญ่ไว้เกินการใช้งานทันที  

## ปัญหาที่พบบ่อยและวิธีแก้
| Issue | Solution |
|-------|----------|
| ไม่พบโฟลเดอร์ผลลัพธ์ | สร้างไดเรกทอรีล่วงหน้าหรือเพิ่ม `Files.createDirectories(outputDirectory);` |
| ภาพว่าง | ตรวจสอบให้แน่ใจว่าได้เรียก `cadOptions.setBackgroundColor` หลังจาก `forRenderingByWidth`. |
| ข้อผิดพลาด out‑of‑memory | เพิ่มตัวเลือก JVM `-Xmx` หรือประมวลผลไฟล์เป็นชุดเล็ก ๆ |

## คำถามที่พบบ่อย
**Q: ฉันสามารถเรนเดอร์รูปแบบ CAD อื่นนอกจาก DWG ได้หรือไม่?**  
A: ใช่, GroupDocs.Viewer รองรับ DXF, DWF, และรูปแบบ CAD เพิ่มเติมหลายรูปแบบ  

**Q: ฉันจะใช้สี RGB ที่กำหนดเองแทนค่าคงที่ที่กำหนดไว้ล่วงหน้าอย่างไร?**  
A: สร้างอินสแตนซ์ `Color` ใหม่ด้วย `new Color(123, 45, 67)` แล้วส่งให้ `setBackgroundColor`  

**Q: สามารถเรนเดอร์เฉพาะเลย์เอาต์หรือเลเยอร์ที่กำหนดได้หรือไม่?**  
A: คุณสามารถระบุตัวเลือกเลย์เอาต์หรือเลเยอร์ผ่าน `CadOptions` ก่อนเรียก `viewer.view`  

**Q: ไลบรารีรองรับพื้นหลังโปร่งใสหรือไม่?**  
A: ตั้งค่าสีพื้นหลังเป็น `new Color(0,0,0,0)` เพื่อความโปร่งใสเต็มที่หากรูปแบบผลลัพธ์รองรับ  

**Q: ต้องการเวอร์ชันของ GroupDocs.Viewer ใด?**  
A: บทแนะนำนี้ใช้เวอร์ชัน 25.2, แต่รุ่นใหม่กว่าจะยังคง API เดียวกัน  

**อัปเดตล่าสุด:** 2026-08-30  
**ทดสอบกับ:** GroupDocs.Viewer 25.2 for Java  
**ผู้เขียน:** GroupDocs  

## บทแนะนำที่เกี่ยวข้อง
- [groupdocs viewer dwg – วิธีเรนเดอร์ภาพวาด CAD เฉพาะใน Java ด้วย GroupDocs.Viewer](/viewer/java/rendering-basics/render-cad-groupdocs-viewer-java/)
- [Render CAD Layers Java with GroupDocs.Viewer – คู่มือฉบับสมบูรณ์](/viewer/java/advanced-rendering/render-cad-layers-java-groupdocs-viewer/)
- [วิธีแปลง pdf เป็น html และปรับคุณภาพภาพใน Java ด้วย GroupDocs.Viewer](/viewer/java/advanced-rendering/adjust-image-quality-groupdocs-viewer-java/)