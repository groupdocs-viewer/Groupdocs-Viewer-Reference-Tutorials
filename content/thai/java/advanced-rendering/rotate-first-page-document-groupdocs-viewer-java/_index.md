---
date: '2026-01-18'
description: เรียนรู้วิธีการหมุนหน้า 90 องศาใน Java ด้วย GroupDocs Viewer รวมถึงการตั้งค่า
  โค้ด และเคล็ดลับด้านประสิทธิภาพ
keywords:
- rotate first page GroupDocs Viewer Java
- GroupDocs Viewer Java setup
- rotate pages in documents using Java
title: หมุนหน้า 90 องศาด้วย GroupDocs Viewer สำหรับ Java
type: docs
url: /th/java/advanced-rendering/rotate-first-page-document-groupdocs-viewer-java/
weight: 1
---

# หมุนหน้า 90 องศาด้วย GroupDocs Viewer for Java

เมื่อคุณต้องการ **หมุนหน้า 90 องศา** ในเอกสาร—ไม่ว่าจะเป็น PDF, ไฟล์ Word หรือสเปรดชีต—การทำแบบโปรแกรมจะช่วยประหยัดเวลาและลดข้อผิดพลาดจากการทำด้วยมือ ในคู่มือขั้นสูงนี้เราจะอธิบายขั้นตอนที่แน่นอนเพื่อหมุนหน้าแรกของเอกสารที่รองรับใด ๆ ด้วย **GroupDocs Viewer for Java** เมื่อติดตามจนจบ คุณจะได้โค้ดสั้น ๆ ที่สามารถนำไปใช้ซ้ำในโปรเจกต์ของคุณได้

![หมุนหน้าแรกของเอกสารด้วย GroupDocs.Viewer for Java](/viewer/advanced-rendering/rotate-the-first-page-of-a-document-java.png)

## คำตอบด่วน
- **“หมุนหน้า 90 องศา” หมายถึงอะไร?** หมายถึงการหมุนหน้าที่เลือกตามเข็มนาฬิกาเป็นมุมหนึ่งไตรมาส  
- **ไลบรารีใดทำการหมุน?** GroupDocs Viewer for Java มีเมธอด `rotatePage`  
- **ฉันสามารถหมุนหน้า PDF ด้วย Java ได้หรือไม่?** ได้—ใช้เมธอด `rotatePage` เดียวกัน; ทำงานกับ PDF, DOCX, XLSX และอื่น ๆ  
- **ต้องมีลิขสิทธิ์หรือไม่?** ทดลองใช้ฟรีได้สำหรับการพัฒนา; ต้องซื้อไลเซนส์สำหรับการใช้งานจริง  
- **การทำงานนี้ใช้หน่วยความจำมากหรือไม่?** ไม่มาก หากคุณปิดอินสแตนซ์ `Viewer` อย่างทันท่วงที; ดูเคล็ดลับประสิทธิภาพด้านล่าง

## “หมุนหน้า 90 องศา” คืออะไร?
การหมุนหน้า 90 องศาจะทำให้หน้าตั้งจากแนวตั้งเป็นแนวนอน (หรือกลับกัน) โดยไม่เปลี่ยนแปลงเนื้อหาภายใน นี่เป็นประโยชน์อย่างยิ่งสำหรับการนำเสนอ, การพิมพ์กราฟิกแนวนอนเท่านั้น, หรือการแก้ไขเอกสารสแกนที่ถ่ายมาผิดด้าน

## ทำไมต้องหมุนหน้าโดยใช้ GroupDocs Viewer for Java?
GroupDocs Viewer จัดการความซับซ้อนของการรองรับไฟล์หลายสิบรูปแบบให้คุณได้อย่างง่ายดาย มันให้คุณทำการแปลงระดับหน้าต่าง ๆ—เช่นการหมุน—โดยยังคงไฟล์ต้นฉบับไม่เปลี่ยนแปลง API มีความไหลลื่น, ปลอดภัยต่อเธรด, และทำงานบน Java 8+ ใดก็ได้

## ข้อกำหนดเบื้องต้น

- **GroupDocs.Viewer for Java** (เวอร์ชันล่าสุด)  
- **JDK 8** หรือใหม่กว่า  
- **Maven** (หรือ Gradle) สำหรับจัดการ dependencies  
- IDE เช่น IntelliJ IDEA หรือ Eclipse  
- ความคุ้นเคยพื้นฐานกับ Java I/O  

## การตั้งค่า GroupDocs.Viewer for Java

เพิ่มรีโพซิทอรีของ GroupDocs และ dependency ลงใน `pom.xml` ของคุณ โค้ดส่วนนั้นไม่เปลี่ยนจากบทแนะนำต้นฉบับ:

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
- **ทดลองใช้ฟรี** – ดาวน์โหลดจากเว็บไซต์ GroupDocs  
- **ลิขสิทธิ์ชั่วคราว** – ขอได้หากต้องการช่วงทดลองที่ยาวขึ้น  
- **ลิขสิทธิ์เต็ม** – ซื้อสำหรับการใช้งานในสภาพแวดล้อมจริง  

### การเริ่มต้น Viewer เบื้องต้น
โค้ดต่อไปนี้แสดงวิธีสร้างอินสแตนซ์ `Viewer` อย่างน้อยที่สุด เก็บไว้ตามที่แสดง:

```java
import com.groupdocs.viewer.Viewer;

// Initialize Viewer with your document path
try (Viewer viewer = new Viewer("path/to/your/document.docx")) {
    // Perform operations...
}
```

## การดำเนินการแบบขั้นตอน: หมุนหน้าแรก 90 องศา

### 1. นำเข้าแพ็กเกจที่จำเป็น
การนำเข้าตัวนี้ทำให้คุณเข้าถึงตัวเลือกการเรนเดอร์ PDF และ enum การหมุน

```java
import com.groupdocs.viewer.Viewer;
import com.groupdocs.viewer.options.PdfViewOptions;
import com.groupdocs.viewer.options.Rotation;
```

### 2. กำหนดตำแหน่งเอาต์พุตและสร้าง Viewer
แทนที่พาธตัวอย่างด้วยพาธจริงของคุณ

```java
import java.nio.file.Path;

public class RotateSpecificPage {
    public static void run() {
        Path outputDirectory = YOUR_OUTPUT_DIRECTORY.resolve("RotateSpecificPage");
        Path outputFilePath = outputDirectory.resolve("output.pdf");

        try (Viewer viewer = new Viewer(YOUR_DOCUMENT_DIRECTORY.resolve("Sample.docx"))) {
            // Proceed with the rotation steps below...
        }
    }
}
```

### 3. กำหนดตัวเลือกการดู PDF และใช้การหมุน
เมธอด `rotatePage` รับหมายเลขหน้า (เริ่มจาก 1) และค่า enum `Rotation`

```java
PdfViewOptions viewOptions = new PdfViewOptions(outputFilePath);

// Specify which page to rotate (1 for first page) and the rotation angle
viewOptions.rotatePage(1, Rotation.ON_90_DEGREE);
```

### 4. เรนเดอร์เอกสาร
สุดท้ายเรียก `view` เพื่อสร้าง PDF ที่หมุนแล้ว

```java
viewer.view(viewOptions);
```

#### วิธีทำงาน
- **PdfViewOptions** บอก Viewer ให้ส่งออกเป็นไฟล์ PDF  
- **rotatePage(int, Rotation)** หมุนเฉพาะหน้าที่ระบุโดยไม่กระทบหน้าที่เหลือ  
- เมธอดรองรับ `ON_90_DEGREE`, `ON_180_DEGREE`, และ `ON_270_DEGREE`

## ปัญหาที่พบบ่อยและวิธีแก้
| อาการ | สาเหตุที่เป็นไปได้ | วิธีแก้ |
|---------|--------------|-----|
| **FileNotFoundException** | พาธไม่ถูกต้องหรือโฟลเดอร์หาย | ตรวจสอบให้แน่ใจว่า `YOUR_OUTPUT_DIRECTORY` และ `YOUR_DOCUMENT_DIRECTORY` มีอยู่และสามารถอ่านได้ |
| **Unsupported file format** | พยายามหมุนไฟล์รูปแบบที่ Viewer ไม่รองรับ | ตรวจสอบหน้า [รูปแบบที่ GroupDocs Viewer รองรับ] |
| **No rotation visible** | ใช้หมายเลขหน้าไม่ถูกต้อง (เริ่มจาก 0) | จำไว้ว่า `rotatePage` ใช้การนับ **เริ่มจาก 1** |
| **Out‑of‑memory errors on large docs** | เรนเดอร์ไฟล์ขนาดใหญ่หลายไฟล์ในเธรดเดียว | ประมวลผลไฟล์ต่อเนื่องหรือใช้ thread pool ที่จำกัดจำนวนเธรด |

## การใช้งานจริง

1. **ปรับการนำเสนอ** – แปลงสไลด์แนวตั้งเป็นแนวนอนแบบอัตโนมัติ  
2. **แก้ไขเอกสารจำนวนมาก** – ทำให้ PDF สแกนที่ถ่ายมาผิดด้านถูกต้องโดยอัตโนมัติ  
3. **เอาต์พุตพร้อมพิมพ์** – ทำให้กราฟิกแนวนอนพิมพ์ได้ถูกต้องบนกระดาษแนวตั้ง  

## เคล็ดลับประสิทธิภาพ

- **ปิดทรัพยากรโดยเร็ว** – บล็อก `try‑with‑resources` จะทำการ dispose `Viewer` ให้โดยอัตโนมัติ  
- **ประมวลผลเป็นชุด** – เมื่อทำงานกับหลายไฟล์ ให้ใช้อินสแตนซ์ `Viewer` เดียวต่อเธรดเพื่อลดค่าโอเวอร์เฮด  
- **ตรวจสอบหน่วยความจำ** – สำหรับเอกสารที่ใหญ่กว่า 100 MB ควรสตรีมผลลัพธ์ไปยังดิสก์แทนการเก็บไว้ในหน่วยความจำ  

## คำถามที่พบบ่อย

**ถาม: ฉันสามารถหมุนหลายหน้าพร้อมกันได้หรือไม่?**  
ตอบ: ได้—เรียก `rotatePage()` สำหรับแต่ละหมายเลขหน้าที่ต้องการหมุน  

**ถาม: มีวิธีย้อนกลับการหมุนหลังจากเรนเดอร์หรือไม่?**  
ตอบ: ไม่โดยตรง คุณต้องเรนเดอร์เอกสารใหม่โดยไม่ใส่ตัวเลือกการหมุน  

**ถาม: ฟอร์แมตไฟล์ใดบ้างที่รองรับการหมุนหน้าใน GroupDocs Viewer?**  
ตอบ: DOCX, PDF, PPTX, XLSX และหลายฟอร์แมตอื่น ๆ ที่ระบุในเอกสารอย่างเป็นทางการ  

**ถาม: ฉันจะหมุนหน้าในชุดเอกสารหลายไฟล์โดยอัตโนมัติได้อย่างไร?**  
ตอบ: ห่อโค้ดไว้ในลูปที่วนผ่านคอลเลกชันของพาธไฟล์ แล้วใช้ตรรกะ `rotatePage` เดียวกันกับแต่ละไฟล์  

**ถาม: วิธีปฏิบัติที่ดีที่สุดสำหรับการจัดการข้อผิดพลาดระหว่างการหมุนคืออะไร?**  
ตอบ: ห่อการใช้ Viewer ด้วยบล็อก `try‑catch` บันทึกข้อยกเว้นและอาจดำเนินการต่อกับไฟล์ถัดไป  

## แหล่งข้อมูล

- **เอกสาร**: [GroupDocs Viewer Java Documentation](https://docs.groupdocs.com/viewer/java/)  
- **อ้างอิง API**: [GroupDocs API Reference](https://reference.groupdocs.com/viewer/java/)  
- **ดาวน์โหลด**: [Get GroupDocs Viewer for Java](https://releases.groupdocs.com/viewer/java/)  
- **ซื้อไลเซนส์**: [Buy a License](https://purchase.groupdocs.com/buy)  
- **ทดลองใช้ฟรี**: [Try Free](https://releases.groupdocs.com/viewer/java/)  
- **ลิขสิทธิ์ชั่วคราว**: [Request Temporary License](https://purchase.groupdocs.com/temporary-license/)  
- **สนับสนุน**: [GroupDocs Forum](https://forum.groupdocs.com/c/viewer/9)

---

**อัปเดตล่าสุด:** 2026-01-18  
**ทดสอบกับ:** GroupDocs Viewer 25.2 for Java  
**ผู้เขียน:** GroupDocs  

---