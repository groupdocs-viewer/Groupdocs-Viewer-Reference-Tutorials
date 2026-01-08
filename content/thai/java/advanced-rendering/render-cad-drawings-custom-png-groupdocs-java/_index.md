---
date: '2026-01-08'
description: เรียนรู้วิธีแปลงภาพวาด CAD เป็นภาพ PNG คุณภาพสูงโดยใช้ขนาดและสีพื้นหลังที่กำหนดเองด้วย
  GroupDocs.Viewer สำหรับ Java.
keywords:
- render CAD drawings PNG
- GroupDocs.Viewer for Java setup
- custom image size and background color
title: วิธีเรนเดอร์ภาพวาด CAD เป็น PNG พร้อมขนาดและสีพื้นหลังที่กำหนดเองโดยใช้ GroupDocs.Viewer
  สำหรับ Java
type: docs
url: /th/java/advanced-rendering/render-cad-drawings-custom-png-groupdocs-java/
weight: 1
---

# วิธีแสดงภาพวาด CAD เป็น PNG ด้วยขนาดและสีพื้นหลังที่กำหนดเองโดยใช้ GroupDocs.Viewer สำหรับ Java

คุณกำลังประสบปัญหาในการแปลงภาพวาด CAD ของคุณเป็นภาพคุณภาพสูงพร้อมรักษาขนาดและความสวยงามที่กำหนดไว้หรือไม่? ในบทแนะนำนี้เราจะแสดง **วิธีแสดงภาพ CAD** เป็นไฟล์ PNG ด้วยขนาดและสีพื้นหลังที่กำหนดเอง เพื่อให้คุณได้รูปลักษณ์ที่ต้องการสำหรับรายงาน การนำเสนอ หรือการแสดงตัวอย่างบนเว็บ

## คำตอบด่วน
- **“how to render CAD” หมายถึงอะไร?** หมายถึงการแปลงไฟล์ CAD (เช่น DWG) เป็นรูปแบบภาพเช่น PNG ด้วยโค้ด.  
- **ฉันสามารถตั้งความกว้างที่กำหนดเองได้หรือไม่?** ใช่ – ใช้ `CadOptions.forRenderingByWidth(int width)`.  
- **ฉันจะเปลี่ยนสีพื้นหลังได้อย่างไร?** เรียก `cadOptions.setBackgroundColor(Color.YOUR_COLOR)`.  
- **ต้องใช้ไลบรารีใด?** GroupDocs.Viewer for Java (เวอร์ชัน 25.2 หรือใหม่กว่า)  
- **ฉันต้องการไลเซนส์หรือไม่?** ไลเซนส์ชั่วคราวหรือที่ซื้อจะลบข้อจำกัดการประเมินผล

![แสดงภาพวาด CAD เป็น PNG ด้วยขนาดและสีพื้นหลังที่กำหนดเองด้วย GroupDocs.Viewer for Java](/viewer/advanced-rendering/render-cad-drawings-as-png-with-custom-size-background-color-java.png)

## วิธีแสดงภาพวาด CAD – ภาพรวม
ส่วนนี้ขยายเป้าหมายหลัก: **วิธีแสดงภาพ CAD** เป็นไฟล์ PNG พร้อมควบคุมขนาดและพื้นหลัง เราจะอธิบายขั้นตอนการตั้งค่าเต็มรูปแบบ ตัวอย่างโค้ด และเคล็ดลับที่ใช้งานได้จริง

## สิ่งที่คุณจะได้เรียนรู้
- การตั้งค่า GroupDocs.Viewer for Java ในโปรเจกต์ของคุณ  
- **แปลง DWG เป็น PNG** ด้วยมิติที่กำหนดเอง  
- **ตั้งค่าสีพื้นหลัง PNG** ระหว่างการแสดงผลเพื่อให้ได้ลุคที่เรียบหรู  
- สถานการณ์จริงที่การแสดงผลแบบกำหนดเองเพิ่มคุณค่า  

## ข้อกำหนดเบื้องต้น

### ไลบรารีและการพึ่งพาที่จำเป็น
- Java Development Kit (JDK) 8+  
- Maven สำหรับการจัดการการพึ่งพา  

### ความต้องการในการตั้งค่าสภาพแวดล้อม
- IDE เช่น IntelliJ IDEA หรือ Eclipse  
- ความรู้พื้นฐานของ Java  

### ความรู้เบื้องต้นที่จำเป็น
- ความคุ้นเคยกับการจัดการไฟล์ใน Java  

## การตั้งค่า GroupDocs.Viewer for Java
เพิ่มรีโพซิทอรีของ GroupDocs และการพึ่งพาไปยังไฟล์ `pom.xml` ของ Maven ของคุณ:

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
รับไลเซนส์ชั่วคราวหรือเต็มเพื่อยกเลิกข้อจำกัดการประเมินผล

### การเริ่มต้นและตั้งค่าเบื้องต้น
สร้างอินสแตนซ์ `Viewer` ที่ชี้ไปยังไฟล์ CAD ของคุณ:

```java
import com.groupdocs.viewer.Viewer;
import java.nio.file.Path;

Path documentPath = Path.of("YOUR_DOCUMENT_DIRECTORY/SAMPLE_DWG_WITH_LAYOUTS_AND_LAYERS");
try (Viewer viewer = new Viewer(documentPath.toString())) {
    // Rendering operations go here
}
```

## คู่มือการดำเนินการ

### ฟีเจอร์ 1: การแสดงภาพวาด CAD ด้วยขนาดภาพและสีพื้นหลังที่กำหนดเอง
#### ภาพรวม
ฟีเจอร์นี้ช่วยให้คุณ **แปลง DWG เป็น PNG** พร้อมระบุความกว้างของภาพและสีพื้นหลัง

#### การดำเนินการแบบขั้นตอน

##### นำเข้าแพคเกจที่จำเป็น
```java
import com.groupdocs.viewer.Viewer;
import com.groupdocs.viewer.options.CadOptions;
import com.groupdocs.viewer.options.PngViewOptions;
import java.nio.file.Path;
import java.awt.Color;
```

##### ตั้งค่าไดเรกทอรีเอาต์พุตและรูปแบบเส้นทางไฟล์
```java
Path outputDirectory = Path.of("YOUR_OUTPUT_DIRECTORY/SetImageBackgroundColor");
Path pageFilePathFormat = outputDirectory.resolve("page_{0}.png");
```

##### เริ่มต้น Viewer ด้วยตัวเลือกการแสดงผลที่กำหนดเอง
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
- `PngViewOptions` – กำหนดรูปแบบเอาต์พุตและการตั้งชื่อ  
- `forRenderingByWidth(int width)` – ตั้งค่าความกว้างภาพที่กำหนดเอง  
- `setBackgroundColor(Color color)` – **ใช้การแสดงผลสีพื้นหลัง** กับ PNG  

#### เคล็ดลับการแก้ไขปัญหา
- ตรวจสอบว่าโฟลเดอร์เอาต์พุตมีอยู่; สร้างหากจำเป็น  
- ตรวจสอบเส้นทางไฟล์อินพุตและสิทธิ์อีกครั้ง  

### ฟีเจอร์ 2: การตั้งค่าสีพื้นหลังในตัวเลือกการแสดงผล
#### ภาพรวม
ที่นี่เรามุ่งเน้นที่ **ตั้งค่าสีพื้นหลัง PNG** เพื่อปรับปรุงความสอดคล้องของภาพ

#### การดำเนินการแบบขั้นตอน

##### นำเข้าแพคเกจที่จำเป็น
```java
import com.groupdocs.viewer.Viewer;
import com.groupdocs.viewer.options.CadOptions;
import com.groupdocs.viewer.options.PngViewOptions;
import java.nio.file.Path;
import java.awt.Color;
```

##### กำหนดค่าตัวเลือกการแสดงผลด้วยสีพื้นหลัง
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
- ปรับ `forRenderingByWidth(int width)` สำหรับมิติที่แตกต่างกัน  
- ใช้ค่าสี `Color` ใดก็ได้หรือ `new Color(r,g,b)` แบบกำหนดเองสำหรับพื้นหลังที่ต้องการ  

## การประยุกต์ใช้งานจริง

### 1. เอกสารวิศวกรรม
การแสดงผลแบบกำหนดเองทำให้แน่ใจว่าภาพวาดวิศวกรรมตรงตามแนวทางสไตล์ขององค์กร

### 2. การแสดงผลสถาปัตยกรรม
นำเสนอแบบแปลนด้วยพื้นหลังที่สะอาดและสอดคล้องกับสไลด์การนำเสนอ

### 3. การทำต้นแบบการผลิต
สร้าง PNG ที่แม่นยำสำหรับกระบวนการทำต้นแบบอย่างรวดเร็ว

### ความเป็นไปได้ในการบูรณาการ
รวมไพป์ไลน์การแสดงผลนี้กับระบบจัดการเอกสารเพื่ออัตโนมัติการสร้างสินทรัพย์ภาพ

## การพิจารณาประสิทธิภาพ

### การเพิ่มประสิทธิภาพ
- **การประมวลผลแบบชุด:** แสดงหลายไฟล์ CAD ในลูป  
- **การจัดการทรัพยากร:** ปรับขนาด heap ของ JVM สำหรับภาพวาดขนาดใหญ่  

### แนวทางการใช้ทรัพยากร
ตรวจสอบ CPU และหน่วยความจำ; ปล่อยอินสแตนซ์ `Viewer` อย่างทันท่วงที

### แนวทางปฏิบัติที่ดีที่สุดสำหรับการจัดการหน่วยความจำใน Java
- ใช้ try‑with‑resources (ตามที่แสดง) เพื่อปิด `Viewer` อัตโนมัติ  
- หลีกเลี่ยงการเก็บอ็อบเจกต์ `Path` ขนาดใหญ่ไว้นานเกินความจำเป็น  

## ปัญหาทั่วไปและวิธีแก้
| ปัญหา | วิธีแก้ |
|-------|----------|
| **ไม่พบโฟลเดอร์เอาต์พุต** | สร้างโฟลเดอร์ล่วงหน้าหรือเพิ่ม `Files.createDirectories(outputDirectory);` |
| **ภาพว่าง** | ตรวจสอบให้แน่ใจว่าได้ตั้งค่า `cadOptions.setBackgroundColor` หลังจาก `forRenderingByWidth` |
| **ข้อผิดพลาดหน่วยความจำเต็ม** | เพิ่มตัวเลือก JVM `-Xmx` หรือประมวลผลไฟล์เป็นชุดเล็กลง |

## คำถามที่พบบ่อย

**Q: ฉันสามารถแสดงผลรูปแบบ CAD อื่น ๆ นอกจาก DWG ได้หรือไม่?**  
A: ใช่, GroupDocs.Viewer รองรับ DXF, DWF และรูปแบบไฟล์ CAD อื่น ๆ อีกหลายประเภท  

**Q: ฉันจะใช้สี RGB ที่กำหนดเองแทนค่าคงที่ที่กำหนดไว้ได้อย่างไร?**  
A: สร้างอินสแตนซ์ `Color` ใหม่ เช่น `new Color(123, 45, 67)` แล้วส่งให้กับ `setBackgroundColor`  

**Q: สามารถแสดงผลเฉพาะเลเอาต์หรือเลเยอร์ที่กำหนดได้หรือไม่?**  
A: คุณสามารถระบุตัวเลือกเลเอาต์หรือเลเยอร์ผ่าน `CadOptions` ก่อนเรียก `viewer.view`  

**Q: ไลบรารีรองรับพื้นหลังโปร่งใสหรือไม่?**  
A: ตั้งค่าสีพื้นหลังเป็น `new Color(0,0,0,0)` เพื่อให้โปร่งใสเต็มที่หากรูปแบบเป้าหมายรองรับ  

**Q: ต้องการเวอร์ชันของ GroupDocs.Viewer ใด?**  
A: บทแนะนำใช้เวอร์ชัน 25.2 แต่เวอร์ชันใหม่กว่ายังคง API เดียวกัน  

## สรุป
คุณตอนนี้รู้ **วิธีแสดงภาพ CAD** เป็นไฟล์ PNG ด้วยมิติและสีพื้นหลังที่กำหนดเองโดยใช้ GroupDocs.Viewer for Java แล้ว ใช้เทคนิคเหล่านี้เพื่อสร้างสินทรัพย์ภาพที่ดูเป็นมืออาชีพสำหรับกระบวนการวิศวกรรม สถาปัตยกรรม หรือการผลิต

### ขั้นตอนต่อไป
- ทดลองกับความกว้างและสีของภาพที่ต่างกัน  
- ผสานโค้ดการแสดงผลเข้ากับบริการประมวลผลแบบชุด  
- สำรวจตัวเลือก Viewer เพิ่มเติม เช่น การแปลงเป็น PDF หรือการแสดงผลหลายหน้า  

---

**อัปเดตล่าสุด:** 2026-01-08  
**ทดสอบด้วย:** GroupDocs.Viewer 25.2 for Java  
**ผู้เขียน:** GroupDocs