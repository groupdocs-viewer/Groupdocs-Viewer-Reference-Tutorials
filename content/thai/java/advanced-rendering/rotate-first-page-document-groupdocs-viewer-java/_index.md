---
date: '2026-03-29'
description: เรียนรู้วิธีการหมุนหน้า 90 องศาใน Java ด้วย GroupDocs Viewer รวมถึงการตั้งค่า,
  โค้ด, และเคล็ดลับด้านประสิทธิภาพ
keywords:
- rotate first page GroupDocs Viewer Java
- GroupDocs Viewer Java setup
- rotate pages in documents using Java
title: หมุนหน้า 90 องศาด้วย GroupDocs Viewer สำหรับ Java
type: docs
url: /th/java/advanced-rendering/rotate-first-page-document-groupdocs-viewer-java/
weight: 1
---

# หมุนหน้า 90 องศาด้วย GroupDocs Viewer สำหรับ Java

เมื่อคุณต้องการ **หมุนหน้า 90 องศา** ในเอกสาร—ไม่ว่าจะเป็น PDF, ไฟล์ Word หรือสเปรดชีต—การทำแบบโปรแกรมช่วยประหยัดเวลาและลดข้อผิดพลาดจากการทำด้วยมือ ในคู่มือขั้นสูงนี้เราจะอธิบายขั้นตอนที่แน่นอนเพื่อหมุนหน้าที่หนึ่งของเอกสารที่รองรับใด ๆ ด้วย **GroupDocs Viewer for Java** เมื่อเสร็จคุณจะได้โค้ดสั้นที่สามารถนำไปใช้ในโปรเจกต์ของคุณได้  
เราจะพูดถึงเหตุผลที่การหมุนหน้าใน Java มีความสำคัญ, สถานการณ์ทั่วไปที่เทคนิคนี้โดดเด่น, และวิธีทำให้การดำเนินการมีน้ำหนักเบา

![หมุนหน้าที่หนึ่งของเอกสารด้วย GroupDocs.Viewer for Java](/viewer/advanced-rendering/rotate-the-first-page-of-a-document-java.png)

## คำตอบด่วน
- **“rotate page 90 degrees” หมายความว่าอะไร?** มันทำให้หน้าที่เลือกหมุนตามเข็มนาฬิกาเป็นมุมหนึ่งรอบ (หนึ่งในสี่ของการหมุนเต็ม).  
- **ไลบรารีใดจัดการการหมุน?** GroupDocs Viewer for Java มีเมธอด `rotatePage` ให้ใช้.  
- **ฉันสามารถหมุนหน้าของ PDF ด้วย Java ได้หรือไม่?** ใช่—ใช้การเรียก `rotatePage` เดียวกัน; มันทำงานได้กับ PDF, DOCX, XLSX, และอื่น ๆ  
- **ฉันต้องการไลเซนส์หรือไม่?** การทดลองใช้ฟรีทำงานได้สำหรับการพัฒนา; จำเป็นต้องมีไลเซนส์แบบชำระเงินสำหรับการใช้งานจริง.  
- **การดำเนินการนี้ใช้หน่วยความจำมากหรือไม่?** ไม่เมื่อคุณปิดอินสแตนซ์ `Viewer` อย่างรวดเร็ว; ดูเคล็ดลับประสิทธิภาพด้านล่าง.

## อะไรคือ “rotate page 90 degrees”?
การหมุนหน้า 90 องศาจะทำให้หน้าตั้งใหม่จากแนวตั้งเป็นแนวนอน (หรือกลับกัน) โดยไม่เปลี่ยนแปลงเนื้อหาพื้นฐาน นี่เป็นประโยชน์อย่างยิ่งสำหรับการนำเสนอ, การพิมพ์กราฟิกที่ต้องการแนวนอนเท่านั้น, หรือการแก้ไขเอกสารสแกนที่ถูกจับภาพเอียง.

## ทำไมต้องหมุนหน้าโดยโปรแกรมด้วย GroupDocs Viewer for Java?
GroupDocs Viewer แยกความซับซ้อนของการจัดการไฟล์หลายสิบรูปแบบออกให้ คุณสามารถใช้การแปลงระดับหน้า—เช่นการหมุน—โดยยังคงไฟล์ต้นฉบับไม่เปลี่ยนแปลง API มีรูปแบบการใช้งานที่เป็นมิตร, ปลอดภัยต่อเธรด, และทำงานบน Java 8+ ใด ๆ ทำให้เป็นตัวเลือกที่เชื่อถือได้สำหรับการอัตโนมัติระดับองค์กร.

## ข้อกำหนดเบื้องต้น

- **GroupDocs.Viewer for Java** (latest version)
- **JDK 8** หรือใหม่กว่า
- **Maven** (หรือ Gradle) สำหรับการจัดการ dependencies
- IDE เช่น IntelliJ IDEA หรือ Eclipse
- ความคุ้นเคยพื้นฐานกับ Java I/O

## การตั้งค่า GroupDocs.Viewer สำหรับ Java

เพิ่มรีโพซิทอรีของ GroupDocs และ dependency ลงใน `pom.xml` ของคุณ โค้ดส่วนนี้ไม่มีการเปลี่ยนแปลงจากบทแนะนำต้นฉบับ:

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
- **Free trial** – ดาวน์โหลดจากเว็บไซต์ของ GroupDocs.  
- **Temporary license** – ขอหากคุณต้องการช่วงเวลาการประเมินที่ยาวนานขึ้น.  
- **Full license** – ซื้อสำหรับการใช้งานในสภาพแวดล้อมการผลิต.

### การเริ่มต้น Viewer เบื้องต้น
โค้ดต่อไปนี้แสดงวิธีที่น้อยที่สุดในการสร้างอินสแตนซ์ `Viewer` รักษาให้เหมือนเดิมตามที่แสดง:

```java
import com.groupdocs.viewer.Viewer;

// Initialize Viewer with your document path
try (Viewer viewer = new Viewer("path/to/your/document.docx")) {
    // Perform operations...
}
```

## วิธีหมุนหน้าของ PDF ด้วย Java และ GroupDocs Viewer
แม้ว่า API จะทำงานกับหลายรูปแบบ, PDF ยังคงเป็นกรณีการใช้งานที่พบบ่อยที่สุดสำหรับการหมุนหน้า เมธอด `rotatePage` เดียวกันถูกใช้, ดังนั้นคุณเพียงแค่ชี้ Viewer ไปที่ไฟล์ PDF และระบุหมายเลขหน้า.

## การดำเนินการแบบขั้นตอน: หมุนหน้าที่หนึ่ง 90 องศา

### 1. นำเข้าชุดแพ็กเกจที่จำเป็น
การนำเข้าตัวเหล่านี้ทำให้คุณเข้าถึงตัวเลือกการเรนเดอร์ PDF และ enum การหมุน.

```java
import com.groupdocs.viewer.Viewer;
import com.groupdocs.viewer.options.PdfViewOptions;
import com.groupdocs.viewer.options.Rotation;
```

### 2. กำหนดตำแหน่งเอาต์พุตและสร้าง Viewer
แทนที่เส้นทาง placeholder ด้วยไดเรกทอรีจริงของคุณ.

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

### 3. กำหนดค่า PDF view options และใช้การหมุน
เมธอด `rotatePage` รับหมายเลขหน้า (เริ่มจาก 1) และค่า enum `Rotation`.

```java
PdfViewOptions viewOptions = new PdfViewOptions(outputFilePath);

// Specify which page to rotate (1 for first page) and the rotation angle
viewOptions.rotatePage(1, Rotation.ON_90_DEGREE);
```

### 4. เรนเดอร์เอกสาร
สุดท้าย, เรียก `view` เพื่อสร้าง PDF ที่หมุนแล้ว.

```java
viewer.view(viewOptions);
```

#### วิธีการทำงาน
- **PdfViewOptions** บอกให้ Viewer ส่งออกเป็นไฟล์ PDF.  
- **rotatePage(int, Rotation)** หมุนเฉพาะหน้าที่คุณระบุ, ส่วนที่เหลือคงเดิม.  
- เมธอดรองรับ `ON_90_DEGREE`, `ON_180_DEGREE`, และ `ON_270_DEGREE`.

## ปัญหาทั่วไปและวิธีแก้

| อาการ | สาเหตุที่เป็นไปได้ | วิธีแก้ |
|---------|--------------|-----|
| **FileNotFoundException** | เส้นทางไม่ถูกต้องหรือโฟลเดอร์หาย | ตรวจสอบว่า `YOUR_OUTPUT_DIRECTORY` และ `YOUR_DOCUMENT_DIRECTORY` มีอยู่และสามารถอ่านได้ |
| **Unsupported file format** | พยายามหมุนรูปแบบที่ Viewer ไม่รองรับ | ตรวจสอบหน้า [GroupDocs Viewer supported formats] |
| **No rotation visible** | ใช้หมายเลขหน้าผิด (เริ่มจาก 0) | จำไว้ว่า `rotatePage` ใช้การจัดลำดับ **เริ่มจาก 1** |
| **Out‑of‑memory errors on large docs** | เรนเดอร์ไฟล์ขนาดใหญ่หลายไฟล์ในเธรดเดียว | ประมวลผลเอกสารแบบต่อเนื่องหรือใช้ thread pool ที่มีการจำกัดความพร้อมกัน |

## การนำไปใช้ในทางปฏิบัติ

1. **การปรับการนำเสนอ** – แปลงสไลด์แนวตั้งเป็นแนวนอนแบบทันที.  
2. **การแก้ไขเอกสารจำนวนมาก** – ทำการแก้ไขสแกน PDF ที่ถูกจับภาพเอียงโดยอัตโนมัติ.  
3. **ผลลัพธ์พร้อมพิมพ์** – ทำให้กราฟิกแนวนอนพิมพ์ได้อย่างถูกต้องบนกระดาษแนวตั้ง.

## เคล็ดลับประสิทธิภาพ

- **ปิดทรัพยากรอย่างรวดเร็ว** – บล็อก `try‑with‑resources` จะทำการกำจัด `Viewer` โดยอัตโนมัติ.  
- **การประมวลผลเป็นชุด** – เมื่อจัดการไฟล์จำนวนมาก, ใช้ `Viewer` อินสแตนซ์เดียวต่อเธรดเพื่อ ลดภาระ.  
- **ตรวจสอบหน่วยความจำ** – สำหรับเอกสารที่ใหญ่กว่า 100 MB, พิจารณา stream ผลลัพธ์ไปยังดิสก์แทนการเก็บไว้ในหน่วยความจำ.

## คำถามที่พบบ่อย

**Q: ฉันสามารถหมุนหลายหน้าในครั้งเดียวได้หรือไม่?**  
A: ได้—เรียก `rotatePage()` สำหรับแต่ละหมายเลขหน้าที่คุณต้องการหมุน.

**Q: มีวิธีใดที่จะยกเลิกการหมุนหลังจากเรนเดอร์หรือไม่?**  
A: ไม่โดยตรง คุณต้องเรนเดอร์เอกสารอีกครั้งโดยไม่ใช้ตัวเลือกการหมุน.

**Q: รูปแบบไฟล์ใดรองรับการหมุนหน้าใน GroupDocs Viewer?**  
A: DOCX, PDF, PPTX, XLSX, และรูปแบบอื่น ๆ มากมายที่ระบุในเอกสารอย่างเป็นทางการ.

**Q: ฉันจะหมุนหลายหน้าในชุดเอกสารโดยอัตโนมัติได้อย่างไร?**  
A: ห่อโค้ดในลูปที่วนผ่านคอลเลกชันของเส้นทางไฟล์, แล้วใช้ตรรกะ `rotatePage` เดียวกันกับแต่ละไฟล์.

**Q: วิธีปฏิบัติที่ดีที่สุดสำหรับการจัดการข้อผิดพลาดระหว่างการหมุนคืออะไร?**  
A: ห่อการใช้ Viewer ในบล็อก `try‑catch`, บันทึกข้อยกเว้น, และอาจดำเนินการต่อกับไฟล์ถัดไป.

## แหล่งข้อมูล

- **เอกสาร**: [GroupDocs Viewer Java Documentation](https://docs.groupdocs.com/viewer/java/)  
- **อ้างอิง API**: [GroupDocs API Reference](https://reference.groupdocs.com/viewer/java/)  
- **ดาวน์โหลด**: [Get GroupDocs Viewer for Java](https://releases.groupdocs.com/viewer/java/)  
- **ซื้อ**: [Buy a License](https://purchase.groupdocs.com/buy)  
- **ทดลองใช้ฟรี**: [Try Free](https://releases.groupdocs.com/viewer/java/)  
- **ไลเซนส์ชั่วคราว**: [Request Temporary License](https://purchase.groupdocs.com/temporary-license/)  
- **สนับสนุน**: [GroupDocs Forum](https://forum.groupdocs.com/c/viewer/9)

---

**อัปเดตล่าสุด:** 2026-03-29  
**ทดสอบด้วย:** GroupDocs Viewer 25.2 for Java  
**ผู้เขียน:** GroupDocs