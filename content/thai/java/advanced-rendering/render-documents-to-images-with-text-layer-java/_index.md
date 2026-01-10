---
date: '2026-01-10'
description: เรียนรู้วิธีแปลงไฟล์ Word เป็นภาพพร้อมชั้นข้อความใน Java ด้วย GroupDocs.Viewer
  โดยดึงข้อความทับซ้อนเพื่อให้ได้ภาพเอกสารที่ค้นหาได้และมีความคมชัดสูง
keywords:
- convert word to image
- extract text overlay
- render pdf with text
- improve document image clarity
- configure view options
- generate searchable images
title: แปลง Word เป็นภาพพร้อมชั้นข้อความใน Java
type: docs
url: /th/java/advanced-rendering/render-documents-to-images-with-text-layer-java/
weight: 1
---

# แปลง Word เป็นภาพพร้อมชั้นข้อความใน Java ด้วย GroupDocs.Viewer

คุณต้องการ **แปลง Word เป็นภาพ** พร้อมให้ข้อความสามารถเลือกและค้นหาได้หรือไม่? การแสดงผล DOCX เป็นภาพมักทำให้ข้อความพื้นฐานหายไป ทำให้การค้นหาและคัดลอก‑วางเป็นไปไม่ได้ ในบทแนะนำนี้เราจะแสดงวิธีแสดงผลเอกสาร Word เป็นภาพ PNG **พร้อมชั้นข้อความที่ซ้อนทับ** ด้วย GroupDocs.Viewer สำหรับ Java วิธีนี้ไม่เพียงแต่ **ปรับปรุงความคมชัดของภาพเอกสาร** แต่ยัง **สร้างภาพที่สามารถค้นหาได้** ซึ่งทำงานอย่างสมบูรณ์ในพอร์ทัลเว็บและโซลูชัน CMS

![Render Documents as Images with Text Layer with GroupDocs.Viewer for Java](/viewer/advanced-rendering/render-documents-as-images-with-text-layer-java.png)

## คำตอบอย่างรวดเร็ว
- **“แปลง Word เป็นภาพ” หมายถึงอะไร?** จะสร้างภาพเรสเตอร์ (PNG) ของแต่ละหน้าในขณะที่ยังคงรักษาข้อความต้นฉบับไว้ในชั้นที่ซ่อนอยู่  
- **ทำไมต้องเพิ่มชั้นข้อความ?** ชั้นซ้อนทำให้ภาพสามารถค้นหาและเลือกได้ เพิ่มการเข้าถึงและ SEO  
- **ไลบรารีที่ทำหน้าที่นี้คืออะไร?** GroupDocs.Viewer สำหรับ Java มีการสนับสนุนการสกัดข้อความและการแสดงผลภาพในตัว  
- **ต้องมีลิขสิทธิ์หรือไม่?** สามารถใช้เวอร์ชันทดลองฟรีสำหรับการพัฒนา; ต้องซื้อไลเซนส์สำหรับการใช้งานจริง  
- **สามารถใช้โค้ดเดียวกันกับ PDF ได้หรือไม่?** ใช่ – ตัวเลือกการแสดงผลเดียวกันใช้ได้กับ PDF, DOCX และรูปแบบอื่น ๆ อีกหลายประเภท

## “แปลง Word เป็นภาพ” พร้อมชั้นข้อความคืออะไร?
การแปลงไฟล์ Word เป็นภาพโดยปกติจะสร้างบิตแมพที่มีเพียงพิกเซลเท่านั้น โดยการเปิดใช้งาน **extract text overlay** GroupDocs.Viewer จะเพิ่มชั้นข้อความที่มองไม่เห็นบนแต่ละภาพ ทำให้เบราว์เซอร์และเครื่องมือค้นหาอ่านเนื้อหาได้

## ทำไมต้องใช้ GroupDocs.Viewer สำหรับงานนี้?
- **ผลลัพธ์ PNG คุณภาพสูง** ที่รักษาเลย์เอาต์เดิมไว้  
- **สกัดชั้นข้อความโดยอัตโนมัติ** ทำให้ได้ภาพที่ค้นหาได้โดยไม่ต้องประมวลผลเพิ่มเติม  
- **API ที่เรียบง่าย** – เพียงไม่กี่บรรทัดของโค้ด Java ก็จัดการกระบวนการทั้งหมดได้  
- **รองรับรูปแบบหลากหลาย** – วิธีเดียวกันใช้ได้กับ PDF, PPTX และอื่น ๆ อีกมาก

## ข้อกำหนดเบื้องต้น
- ติดตั้ง Java Development Kit (JDK) และกำหนดค่าให้พร้อมใช้งาน  
- มี Maven สำหรับการจัดการ dependencies  
- มีความคุ้นเคยพื้นฐานกับการจัดการไฟล์ใน Java และโครงการ Maven

## การตั้งค่า GroupDocs.Viewer สำหรับ Java
### ข้อมูลการติดตั้ง
เพิ่ม GroupDocs.Viewer ลงในโครงการ Maven ของคุณโดยใส่ repository และ dependency ลงในไฟล์ `pom.xml` ของคุณ:

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
เริ่มต้นด้วยเวอร์ชันทดลองฟรีโดยดาวน์โหลด GroupDocs.Viewer จาก [download page](https://releases.groupdocs.com/viewer/java/) ของพวกเขา สำหรับการใช้งานจริง ให้ซื้อไลเซนส์หรือรับคีย์ชั่วคราวจาก [temporary license page](https://purchase.groupdocs.com/temporary-license/)

### การเริ่มต้นและตั้งค่าเบื้องต้น
หลังจากทำการ sync Maven แล้ว คุณสามารถสร้างอินสแตนซ์ `Viewer` – วัตถุนี้จะเป็นตัวขับกระบวนการแสดงผล

## คู่มือขั้นตอนต่อขั้นตอนเพื่อแปลง Word เป็นภาพ

### ขั้นตอนที่ 1: กำหนดไดเรกทอรีผลลัพธ์
แรกสุด ให้บอก Viewer ว่าจะเก็บไฟล์ PNG ที่สร้างขึ้นที่ไหน โค้ดด้านล่างจะสร้าง (หรือใช้) โฟลเดอร์ชื่อ `YOUR_OUTPUT_DIRECTORY`

```java
Path outputDirectory = Paths.get("YOUR_OUTPUT_DIRECTORY");
```

> **เคล็ดลับ:** ใช้ `Files.createDirectories(outputDirectory);` หากต้องการให้โฟลเดอร์ถูกสร้างโดยอัตโนมัติ

### ขั้นตอนที่ 2: กำหนดตัวเลือกการแสดงผล (Configure View Options)
ต่อไป ตั้งค่าตัวเลือกการแสดงผล โดยใช้ `PngViewOptions` และเปิดใช้งาน `setExtractText(true)` เพื่อบอก GroupDocs.Viewer ให้ **สกัดชั้นข้อความ** และฝังลงในแต่ละภาพ

```java
Path pageFilePathFormat = outputDirectory.resolve("page_{0}.png");
PngViewOptions viewOptions = new PngViewOptions(pageFilePathFormat);
viewOptions.setExtractText(true);  // Enable extracting text over the image
```

### ขั้นตอนที่ 3: แสดงผลเอกสาร (Convert Word to Image)
สุดท้าย เปิดไฟล์ DOCX ต้นฉบับและเรียก `viewer.view(viewOptions)` บล็อก `try‑with‑resources` จะรับประกันว่าการปิดอินสแตนซ์ `Viewer` ทำอย่างถูกต้อง

```java
try (Viewer viewer = new Viewer("YOUR_DOCUMENT_DIRECTORY/SAMPLE_DOCX")) {
    viewer.view(viewOptions);  // Perform rendering operation
}
```

เมื่อโค้ดทำงานเสร็จแต่ละหน้าของเอกสาร Word จะปรากฏเป็น PNG ความละเอียดสูงพร้อมชั้นข้อความที่มองไม่เห็น พร้อมสำหรับการทำดัชนีและการค้นหา

## เคล็ดลับการแก้ไขปัญหา
- **ไฟล์ไม่พบ:** ตรวจสอบเส้นทางของ `SAMPLE_DOCX` อีกครั้ง ใช้เส้นทางแบบเต็มเพื่อความแน่นอน  
- **ปัญหาการอนุญาต:** ตรวจสอบให้แน่ใจว่ากระบวนการ Java สามารถเขียนลงใน `YOUR_OUTPUT_DIRECTORY` ได้  
- **เวอร์ชันไม่ตรงกัน:** ยืนยันว่าเวอร์ชันใน `pom.xml` ตรงกับไลบรารีที่คุณดาวน์โหลด

## การประยุกต์ใช้งานจริง
1. **พอร์ทัลเว็บ:** แสดงตัวอย่างเอกสารที่ผู้ใช้สามารถค้นหาได้โดยไม่ต้องดาวน์โหลดไฟล์ต้นฉบับ  
2. **ระบบจัดการเนื้อหา (CMS):** เก็บภาพสแนปช็อตที่สามารถค้นหาได้สำหรับการเก็บถาวร  
3. **การเก็บถาวรเอกสาร:** มีเวอร์ชันภาพที่เบาแต่ยังคงเปิดใช้งานการค้นหาข้อความเต็มรูปแบบ

## พิจารณาด้านประสิทธิภาพ
- ปิดออบเจกต์ `Viewer` ทันที (ตามที่แสดงใน `try‑with‑resources`)  
- เลือก PNG เพื่อคุณภาพ; หากต้องการประหยัดแบนด์วิธให้เปลี่ยนเป็น JPEG  
- แคชหน้าที่แสดงผลเมื่อเอกสารเดียวกันถูกเรียกหลายครั้ง

## คำถามที่พบบ่อย

**Q: จะจัดการกับเอกสารขนาดใหญ่อย่างไร?**  
A: เรนเดอร์หน้าเป็นชุด ๆ และปล่อยอินสแตนซ์ `Viewer` หลังจากประมวลผลแต่ละชุด เพื่อรักษาการใช้หน่วยความจำให้ต่ำ

**Q: สามารถเรนเดอร์ PDF ด้วยวิธีเดียวกันได้หรือไม่?**  
A: ใช่, GroupDocs.Viewer รองรับ PDF และการตั้งค่า `setExtractText(true)` จะสร้างภาพ PDF ที่สามารถค้นหาได้เช่นกัน

**Q: ถ้าชั้นข้อความไม่ปรากฏในผลลัพธ์จะทำอย่างไร?**  
A: ตรวจสอบว่ามีการตั้งค่า `viewOptions.setExtractText(true)` แล้วและโฟลเดอร์ผลลัพธ์มีสิทธิ์เขียน

**Q: รองรับรูปแบบภาพอื่น ๆ หรือไม่?**  
A: นอกจาก PNG คุณสามารถใช้ `JpgViewOptions` หรือ `BmpViewOptions` โดยเปลี่ยนคลาสตัวเลือกการแสดงผล

**Q: จะหาเอกสาร API รายละเอียดเพิ่มเติมได้จากที่ไหน?**  
A: เอกสารอย่างเป็นทางการมีตัวอย่างและรายละเอียดการกำหนดค่าที่ครบถ้วน

## แหล่งข้อมูล
- **Documentation:** [GroupDocs Viewer Documentation](https://docs.groupdocs.com/viewer/java/)  
- **API Reference:** [API Reference Guide](https://reference.groupdocs.com/viewer/java/)  
- **Download:** [Get GroupDocs.Viewer](https://releases.groupdocs.com/viewer/java/)  
- **Purchase:** [Buy License](https://purchase.groupdocs.com/buy)  
- **Free Trial:** [Download Free Trial](https://releases.groupdocs.com/viewer/java/)  
- **Temporary License:** [Acquire Temporary License](https://purchase.groupdocs.com/temporary-license/)  
- **Support:** [GroupDocs Forum](https://forum.groupdocs.com/c/viewer/9)

---

**Last Updated:** 2026-01-10  
**Tested With:** GroupDocs.Viewer 25.2 for Java  
**Author:** GroupDocs