---
date: '2026-03-16'
description: เรียนรู้วิธีแปลง DWG เป็น PNG ด้วยขนาดและสีพื้นหลังที่กำหนดเองโดยใช้
  GroupDocs.Viewer สำหรับ Java.
keywords:
- render CAD drawings PNG
- GroupDocs.Viewer for Java setup
- custom image size and background color
title: วิธีแปลง DWG เป็น PNG ด้วยขนาดและสีพื้นหลังที่กำหนดเองโดยใช้ GroupDocs.Viewer
  สำหรับ Java
type: docs
url: /th/java/advanced-rendering/render-cad-drawings-custom-png-groupdocs-java/
weight: 1
---

# วิธีแปลง DWG เป็น PNG ด้วยขนาดและสีพื้นหลังที่กำหนดเองโดยใช้ GroupDocs.Viewer สำหรับ Java

หากคุณกำลังมองหา **convert DWG to PNG** พร้อมการควบคุมเต็มรูปแบบของขนาดภาพและการจัดรูปแบบพื้นหลัง คุณมาถูกที่แล้ว ในบทเรียนนี้เราจะพาคุณผ่านขั้นตอนการเรนเดอร์ไฟล์ CAD เป็น PNG ปรับความกว้างตามต้องการ และเปลี่ยนสีพื้นหลังเพื่อให้ผลลัพธ์ตรงกับรายงาน การนำเสนอ หรือความต้องการการแสดงตัวอย่างบนเว็บของคุณ

## คำตอบสั้น
- **“convert DWG to PNG” หมายถึงอะไร?** คือกระบวนการแปลงไฟล์ DWG CAD ให้เป็นภาพ PNG ด้วยโค้ด  
- **ฉันสามารถตั้งค่าความกว้างที่กำหนดเองได้หรือไม่?** ได้ – ใช้ `CadOptions.forRenderingByWidth(int width)`  
- **ฉันจะเปลี่ยนสีพื้นหลังได้อย่างไร?** เรียก `cadOptions.setBackgroundColor(Color.YOUR_COLOR)`  
- **ต้องใช้ไลบรารีใด?** GroupDocs.Viewer for Java (เวอร์ชัน 25.2 หรือใหม่กว่า)  
- **ต้องมีลิขสิทธิ์หรือไม่?** ลิขสิทธิ์ชั่วคราวหรือที่ซื้อจะลบข้อจำกัดการประเมินผล  

![Render CAD Drawings as PNG with Custom Size & Background Color with GroupDocs.Viewer for Java](/viewer/advanced-rendering/render-cad-drawings-as-png-with-custom-size-background-color-java.png)

## วิธีแปลง DWG เป็น PNG – ภาพรวม
ในส่วนนี้เราจะขยายเป้าหมายหลัก: **how to convert DWG to PNG** พร้อมการควบคุมขนาดและพื้นหลัง คุณจะได้เห็นการตั้งค่าที่ครบถ้วน โค้ดที่ต้องใช้อย่างแม่นยำ และเคล็ดลับปฏิบัติจริงเพื่อหลีกเลี่ยงข้อผิดพลาดทั่วไป

## สิ่งที่คุณจะได้เรียนรู้
- การตั้งค่า GroupDocs.Viewer for Java ในโครงการ Maven  
- **Convert DWG to PNG** ด้วยมิติที่กำหนดเอง  
- **Change CAD background color** ระหว่างการเรนเดอร์เพื่อให้ได้ลุคที่ดูดี  
- สถานการณ์จริงที่การเรนเดอร์แบบกำหนดเองเพิ่มมูลค่า  

## ข้อกำหนดเบื้องต้น

### ไลบรารีและการพึ่งพาที่จำเป็น
- Java Development Kit (JDK) 8+  
- Maven สำหรับการจัดการ dependency  

### ความต้องการในการตั้งค่าสภาพแวดล้อม
- IDE เช่น IntelliJ IDEA หรือ Eclipse  
- ความรู้พื้นฐานด้าน Java  

### ความรู้เบื้องต้นที่จำเป็น
- ความคุ้นเคยกับการจัดการไฟล์ใน Java  

## การตั้งค่า GroupDocs.Viewer for Java
เพิ่มรีโพสิตอรีของ GroupDocs และ dependency ลงใน `pom.xml` ของ Maven ของคุณ:

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
ขอรับลิขสิทธิ์ชั่วคราวหรือเต็มเพื่อยกเลิกข้อจำกัดการประเมินผล

### การเริ่มต้นและตั้งค่าพื้นฐาน
สร้างอินสแตนซ์ `Viewer` ที่ชี้ไปยังไฟล์ CAD ของคุณ:

```java
import com.groupdocs.viewer.Viewer;
import java.nio.file.Path;

Path documentPath = Path.of("YOUR_DOCUMENT_DIRECTORY/SAMPLE_DWG_WITH_LAYOUTS_AND_LAYERS");
try (Viewer viewer = new Viewer(documentPath.toString())) {
    // Rendering operations go here
}
```

## ฟีเจอร์ 1: เรนเดอร์ภาพวาด CAD ด้วยขนาดภาพและสีพื้นหลังที่กำหนดเอง

### วิธีเปลี่ยนสีพื้นหลังของ CAD
ฟีเจอร์นี้ช่วยให้คุณ **convert DWG to PNG** พร้อมระบุความกว้างที่กำหนดและใช้สีพื้นหลังใหม่

#### การดำเนินการแบบขั้นตอน

##### นำเข้าแพ็กเกจที่จำเป็น
```java
import com.groupdocs.viewer.Viewer;
import com.groupdocs.viewer.options.CadOptions;
import com.groupdocs.viewer.options.PngViewOptions;
import java.nio.file.Path;
import java.awt.Color;
```

##### ตั้งค่าโฟลเดอร์เอาต์พุตและรูปแบบเส้นทางไฟล์
```java
Path outputDirectory = Path.of("YOUR_OUTPUT_DIRECTORY/SetImageBackgroundColor");
Path pageFilePathFormat = outputDirectory.resolve("page_{0}.png");
```

##### เริ่มต้น Viewer ด้วยตัวเลือกการเรนเดอร์ที่กำหนดเอง
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
- `PngViewOptions` – กำหนดรูปแบบเอาต์พุตและการตั้งชื่อไฟล์  
- `forRenderingByWidth(int width)` – ตั้งค่าความกว้างของภาพตามที่ต้องการ  
- `setBackgroundColor(Color color)` – **set PNG background color** เพื่อปรับความสอดคล้องของภาพ  

#### เคล็ดลับการแก้ไขปัญหา
- ตรวจสอบว่าโฟลเดอร์เอาต์พุตมีอยู่แล้ว; หากไม่มีให้สร้าง  
- ตรวจสอบเส้นทางไฟล์อินพุตและสิทธิ์การเข้าถึง  

## ฟีเจอร์ 2: ตั้งค่าสีพื้นหลังในตัวเลือกการเรนเดอร์

### วิธีตั้งค่าสีพื้นหลัง PNG
ในส่วนนี้เราจะเน้นที่ตัวเลือก **set background color PNG** เพื่อให้ภาพที่เรนเดอร์ทุกภาพตรงกับพาเลตสีของแบรนด์คุณ

#### การดำเนินการแบบขั้นตอน

##### นำเข้าแพ็กเกจที่จำเป็น
```java
import com.groupdocs.viewer.Viewer;
import com.groupdocs.viewer.options.CadOptions;
import com.groupdocs.viewer.options.PngViewOptions;
import java.nio.file.Path;
import java.awt.Color;
```

##### กำหนดค่าตัวเลือกการเรนเดอร์พร้อมสีพื้นหลัง
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

**ตัวเลือกการกำหนดค่าที่สำคัญ**  
- ปรับ `forRenderingByWidth(int width)` เพื่อเปลี่ยนมิติภาพ  
- ใช้ค่าสี `Color` ใดก็ได้ หรือสร้าง `new Color(r,g,b)` สำหรับพื้นหลังแบบกำหนดเอง  

## การประยุกต์ใช้งานจริง

### 1. เอกสารวิศวกรรม
การเรนเดอร์แบบกำหนดเองทำให้ภาพวาดวิศวกรรมสอดคล้องกับแนวทางสไตล์ขององค์กร

### 2. การแสดงผลสถาปัตยกรรม
นำเสนอแบบแปลนด้วยพื้นหลังสะอาดที่เข้ากับสไลด์การนำเสนอ

### 3. การสร้างต้นแบบการผลิต
สร้าง PNG ที่แม่นยำสำหรับกระบวนการต้นแบบอย่างรวดเร็ว

### ความเป็นไปได้ในการรวมระบบ
ผสานสายการเรนเดอร์นี้กับระบบจัดการเอกสารเพื่ออัตโนมัติการสร้างสินทรัพย์ภาพ

## พิจารณาด้านประสิทธิภาพ

### การเพิ่มประสิทธิภาพ
- **การประมวลผลเป็นชุด:** เรนเดอร์ไฟล์ CAD หลายไฟล์ในลูป  
- **การจัดการทรัพยากร:** ปรับขนาด heap ของ JVM สำหรับภาพวาดขนาดใหญ่  

### แนวทางการใช้ทรัพยากร
ตรวจสอบการใช้ CPU และหน่วยความจำ; ปล่อยอินสแตนซ์ `Viewer` ทันทีเมื่อเสร็จ

### แนวปฏิบัติที่ดีที่สุดสำหรับการจัดการหน่วยความจำใน Java
- ใช้ try‑with‑resources (ตามตัวอย่าง) เพื่อปิด `Viewer` อัตโนมัติ  
- อย่าเก็บอ็อบเจกต์ `Path` ขนาดใหญ่ไว้นานเกินจำเป็น  

## ปัญหาทั่วไปและวิธีแก้
| Issue | Solution |
|-------|----------|
| **Output folder not found** | สร้างไดเรกทอรีล่วงหน้าหรือเพิ่ม `Files.createDirectories(outputDirectory);` |
| **Blank image** | ตรวจสอบให้แน่ใจว่า `cadOptions.setBackgroundColor` ถูกตั้งค่าหลัง `forRenderingByWidth` |
| **Out‑of‑memory errors** | เพิ่มพารามิเตอร์ `-Xmx` ของ JVM หรือประมวลผลไฟล์เป็นชุดเล็ก ๆ |

## คำถามที่พบบ่อย

**Q: ฉันสามารถเรนเดอร์รูปแบบ CAD อื่น ๆ นอกจาก DWG ได้หรือไม่?**  
A: ได้, GroupDocs.Viewer รองรับ DXF, DWF และหลายรูปแบบ CAD อื่น ๆ  

**Q: ฉันจะใช้สี RGB ที่กำหนดเองแทนค่าคงที่ได้อย่างไร?**  
A: สร้างอินสแตนซ์ `Color` ใหม่ เช่น `new Color(123, 45, 67)` แล้วส่งให้ `setBackgroundColor`  

**Q: สามารถเรนเดอร์เฉพาะเลเอาต์หรือเลเยอร์ใดเลเยอร์หนึ่งได้หรือไม่?**  
A: สามารถกำหนดตัวเลือกเลเอาต์หรือเลเยอร์ผ่าน `CadOptions` ก่อนเรียก `viewer.view`  

**Q: ไลบรารีสนับสนุนพื้นหลังแบบโปร่งใสหรือไม่?**  
A: ตั้งค่าสีพื้นหลังเป็น `new Color(0,0,0,0)` เพื่อความโปร่งใสเต็มที่ หากฟอร์แมตเป้าหมายรองรับ  

**Q: ต้องใช้เวอร์ชันใดของ GroupDocs.Viewer?**  
A: บทเรียนนี้ใช้เวอร์ชัน 25.2 แต่เวอร์ชันใหม่กว่าจะมี API เดียวกัน  

---

**Last Updated:** 2026-03-16  
**Tested With:** GroupDocs.Viewer 25.2 for Java  
**Author:** GroupDocs