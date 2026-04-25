---
date: '2026-02-05'
description: เรียนรู้วิธีตั้งค่าประเภทไฟล์และระบุประเภทเอกสารขณะแปลง DOCX เป็น HTML
  ด้วย GroupDocs.Viewer สำหรับ Java พร้อม Maven.
keywords:
- set file type
- specify document type
- render docx to html
- groupdocs viewer maven
- configure html view
title: วิธีตั้งค่าประเภทไฟล์เมื่อแสดงผลเอกสารด้วย GroupDocs.Viewer สำหรับ Java
type: docs
url: /th/java/custom-rendering/implement-doc-type-specification-groupdocs-viewer-java/
weight: 1
---

# วิธีตั้งประเภทไฟล์เมื่อเรนเดอร์เอกสารด้วย GroupDocs.Viewer สำหรับ Java

หากคุณต้องการ **ตั้งประเภทไฟล์** อย่างชัดเจนขณะเรนเดอร์เอกสารในแอปพลิเคชัน Java คู่มือนี้จะแสดงวิธีทำด้วย GroupDocs.Viewer อย่างละเอียด โดยการระบุประเภทเอกสาร คุณสามารถ **เรนเดอร์ DOCX เป็น HTML** (หรือแม้แต่ **แปลง DOCX เป็น HTML**) ได้อย่างเชื่อถือได้โดยไม่ต้องพึ่งพาการตรวจจับอัตโนมัติ ซึ่งจะช่วยเพิ่มความเร็วและความแม่นยำ

![ดำเนินการกำหนดประเภทเอกสารด้วย GroupDocs.Viewer สำหรับ Java](/viewer/custom-rendering/implement-document-type-specification-java.png)

ในไม่กี่นาทีต่อไป เราจะพาคุณผ่านการตั้งค่าครบถ้วน ตั้งแต่การเพิ่ม GroupDocs.Viewer ผ่าน **groupdocs viewer maven** จนถึงการกำหนดตัวเลือกการดูสำหรับผลลัพธ์ HTML ที่ฝังอยู่ เมื่อเสร็จสิ้นคุณจะสามารถ **ตั้งประเภทไฟล์** สำหรับรูปแบบใด ๆ ที่รองรับและเข้าใจว่าทำไมสิ่งนี้จึงสำคัญต่อประสิทธิภาพและความสอดคล้อง

## คำตอบอย่างรวดเร็ว
- **การตั้ง “set file type” ทำอะไร?** มันบอก GroupDocs.Viewer ว่าจะต้องจัดการอินพุตเป็นรูปแบบใดโดยข้ามการตรวจจับอัตโนมัติ  
- **ทำไมต้องระบุประเภทเอกสาร?** เพื่อรับประกันการเรนเดอร์ที่ถูกต้อง โดยเฉพาะไฟล์ที่มีนามสกุลไม่ชัดเจน  
- **พิกัด Maven ที่ต้องการคืออะไร?** `com.groupdocs:groupdocs-viewer:25.2` (หรือเวอร์ชันใหม่กว่า)  
- **ฉันสามารถเรนเดอร์ DOCX เป็น HTML ได้หรือไม่?** ได้—ใช้ `HtmlViewOptions` พร้อมทรัพยากรที่ฝังอยู่  
- **ฉันต้องการไลเซนส์หรือไม่?** ไลเซนส์ชั่วคราวหรือเต็มจะลบข้อจำกัดการประเมิน; ดูลิงก์ด้านล่าง  

## “set file type” คืออะไรใน GroupDocs.Viewer?
การตั้งค่าประเภทไฟล์หมายถึงการเรียก `LoadOptions.setFileType(FileType.<FORMAT>)` ก่อนเปิดเอกสาร คำสั่งที่ชัดเจนนี้ทำให้ Viewer ประมวลผลไฟล์ตามรูปแบบที่ต้องการและขจัดการคาดเดา

## ทำไมต้องระบุประเภทไฟล์อย่างชัดเจน?
- **การเรนเดอร์ที่คาดการณ์ได้:** ไม่มีความประหลาดใจเมื่อส่วนขยายของไฟล์ไม่ตรงกับโครงสร้างภายใน  
- **เพิ่มประสิทธิภาพ:** ข้ามขั้นตอนการตรวจจับรูปแบบ ซึ่งอาจเห็นได้ชัดเมื่อประมวลผลเป็นชุดใหญ่  
- **การจัดการข้อผิดพลาดที่ดีกว่า:** คุณจะได้รับข้อยกเว้นที่ชัดเจนหากประเภทที่ระบุไม่ตรงกับเนื้อหาไฟล์  

## ข้อกำหนดเบื้องต้น
- **GroupDocs.Viewer** เวอร์ชัน 25.2 หรือใหม่กว่า  
- Java Development Kit (JDK) 8+ ที่ติดตั้งอยู่  
- Maven สำหรับการจัดการ dependencies  
- IDE เช่น IntelliJ IDEA หรือ Eclipse  

## การตั้งค่า GroupDocs.Viewer สำหรับ Java (groupdocs viewer maven)

### 1. เพิ่ม repository และ dependency
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

### 2. รับไลเซนส์
- **ทดลองใช้ฟรี:** ดาวน์โหลดจาก [GroupDocs](https://releases.groupdocs.com/viewer/java/)  
- **ไลเซนส์ชั่วคราว:** รับได้จาก [ที่นี่](https://purchase.groupdocs.com/temporary-license/)  
- **ไลเซนส์เต็ม:** ซื้อผ่าน [ลิงก์นี้](https://purchase.groupdocs.com/buy)  

## คู่มือการใช้งาน – ขั้นตอนต่อขั้นตอน

### ขั้นตอนที่ 1: เตรียมไดเรกทอรีผลลัพธ์
```java
Path outputDirectory = Utils.getOutputDirectoryPath("YOUR_OUTPUT_DIRECTORY");
```
*ที่นี่เรากำหนดตำแหน่งที่บันทึกหน้า HTML ที่เรนเดอร์*

### ขั้นตอนที่ 2: กำหนดรูปแบบการตั้งชื่อไฟล์หน้า
```java
Path pageFilePathFormat = outputDirectory.resolve("page_{0}.html");
```
*ตัวแปร `{0}` จะถูกแทนที่ด้วยหมายเลขหน้าในระหว่างการเรนเดอร์*

### ขั้นตอนที่ 3: **ตั้งประเภทไฟล์** ด้วย `LoadOptions`
```java
LoadOptions loadOptions = new LoadOptions();
loadOptions.setFileType(FileType.DOCX); // Set the file type as DOCX
```
*นี่คือหัวใจของการ **ระบุประเภทเอกสาร** – เราบอก Viewer ให้ถืออินพุตเป็นไฟล์ DOCX*

### ขั้นตอนที่ 4: **กำหนดค่าการดู HTML** เพื่อฝังทรัพยากร
```java
HtmlViewOptions viewOptions = HtmlViewOptions.forEmbeddedResources(pageFilePathFormat);
```
*การใช้ `forEmbeddedResources` ทำให้ HTML ที่สร้างขึ้นมี CSS, รูปภาพ, และฟอนต์ทั้งหมดเป็นแบบในบรรทัดเดียว ซึ่งทำให้การปรับใช้ง่ายขึ้น*

### ขั้นตอนที่ 5: โหลดเอกสารและเรนเดอร์
```java
try (Viewer viewer = new Viewer("YOUR_DOCUMENT_DIRECTORY/SAMPLE_DOCX.docx", loadOptions)) {
    viewer.view(viewOptions);
}
```
*`Viewer` ถูกสร้างด้วยตัวเลือก **ตั้งประเภทไฟล์**, และ `view` จะเขียนไฟล์ HTML ไปยังเส้นทางที่กำหนดไว้ก่อนหน้า*

## ปัญหาทั่วไปและวิธีแก้

| ปัญหา | สาเหตุ | วิธีแก้ |
|---------|-------|-----|
| **ไฟล์ไม่พบ** | เส้นทางไม่ถูกต้องในคอนสตรัคเตอร์ `Viewer` | ตรวจสอบเส้นทางแบบสัมบูรณ์/สัมพัทธ์อีกครั้งและยืนยันว่าไฟล์มีอยู่ |
| **รูปแบบไม่รองรับ** | ค่า enum `FileType` ไม่ถูกต้อง | ตรวจสอบว่าไฟล์เป็น DOCX จริงหรือไม่; ใช้ `FileType.fromExtension("docx")` หากไม่แน่ใจ |
| **การใช้หน่วยความจำพุ่งสูง** | การเรนเดอร์เอกสารขนาดใหญ่มาก | จำกัดจำนวนอินสแตนซ์ `Viewer` ที่ทำงานพร้อมกันและพิจารณาการเรนเดอร์ล่วงหน้าในช่วงเวลาที่ไม่ใช้งานหนัก |

## การประยุกต์ใช้งานจริง
1. **ระบบจัดการเอกสาร** – รับประกันการเรนเดอร์ที่สอดคล้องเมื่อผู้ใช้อัปโหลดไฟล์ที่มีนามสกุลไม่ตรงกัน  
2. **พอร์ทัลเว็บ** – ให้บริการเวอร์ชัน HTML ของไฟล์ DOCX ที่ดูได้ทันทีโดยไม่ต้องใช้เครื่องมือแปลงบนเซิร์ฟเวอร์  
3. **สายงาน CDN** – เรนเดอร์เอกสารเป็น HTML ล่วงหน้าในขั้นตอนการสร้าง เพื่อลดภาระการทำงานในขณะรันไทม์  

## เคล็ดลับด้านประสิทธิภาพ
- **ใช้ LoadOptions ซ้ำ** เมื่อประมวลผลไฟล์หลายไฟล์ที่เป็นประเภทเดียวกัน  
- **ทำลาย Viewer** อย่างทันท่วงที (try‑with‑resources) เพื่อปล่อยทรัพยากรเนทีฟ  
- **การเรนเดอร์เป็นชุด**: ประมวลผลเอกสารเป็นชุดเล็ก ๆ เพื่อให้การใช้หน่วยความจำคาดการณ์ได้  

## สรุป
ตอนนี้คุณรู้วิธี **ตั้งประเภทไฟล์** และ **ระบุประเภทเอกสาร** เมื่อเรนเดอร์ไฟล์ DOCX เป็น HTML ด้วย GroupDocs.Viewer สำหรับ Java วิธีนี้ให้ผลลัพธ์ HTML ที่เชื่อถือได้ รวดเร็ว และพกพาได้ ซึ่งสามารถฝังลงในแอปพลิเคชันเว็บของคุณโดยตรง

**ขั้นตอนต่อไป:** ศึกษาตัวเลือกการเรนเดอร์อื่น ๆ อย่างเช่น PDF, PPTX หรือผลลัพธ์รูปภาพโดยการสำรวจ [เอกสารอย่างเป็นทางการ](https://docs.groupdocs.com/viewer/java/).

## คำถามที่พบบ่อย

**ถาม: ฉันสามารถตั้งประเภทไฟล์สำหรับรูปแบบอื่น ๆ นอกจาก DOCX ได้หรือไม่?**  
ตอบ: ได้, `LoadOptions.setFileType` รองรับค่า enum `FileType` ใด ๆ รวมถึง PDF, PPTX, XLSX, เป็นต้น  

**ถาม: จะเกิดอะไรขึ้นหากฉันละเว้นการตั้งค่าประเภทไฟล์?**  
ตอบ: GroupDocs.Viewer จะพยายามตรวจจับรูปแบบอัตโนมัติ ซึ่งอาจล้มเหลวสำหรับไฟล์ที่มีเนื้อหาไม่ชัดเจนหรือส่วนขยายผิดพลาด  

**ถาม: ฉันจะจัดการกับเอกสารที่มีการป้องกันด้วยรหัสผ่านอย่างไร?**  
ตอบ: ส่งรหัสผ่านไปยังคอนสตรัคเตอร์ `Viewer` หรือกำหนดใน `LoadOptions` ก่อนเรียก `view`  

**ถาม: การรัน Viewer หลายตัวพร้อมกันปลอดภัยหรือไม่?**  
ตอบ: ปลอดภัยต่อเธรดตราบใดที่แต่ละเธรดใช้อินสแตนซ์ `Viewer` ของตนเองและคุณตรวจสอบการใช้หน่วยความจำของ JVM  

**ถาม: ฉันสามารถหา รายการเต็มของประเภทไฟล์ที่รองรับได้จากที่ไหน?**  
ตอบ: ดูอ้างอิง API อย่างเป็นทางการที่ [API Reference](https://reference.groupdocs.com/viewer/java/)

**อัปเดตล่าสุด:** 2026-02-05  
**ทดสอบกับ:** GroupDocs.Viewer 25.2 (Java)  
**ผู้เขียน:** GroupDocs  

## แหล่งข้อมูล
- เอกสาร: [GroupDocs Viewer Java Docs](https://docs.groupdocs.com/viewer/java/)  
- อ้างอิง API: [GroupDocs API Reference](https://reference.groupdocs.com/viewer/java/)  
- ดาวน์โหลด: [GroupDocs Downloads](https://releases.groupdocs.com/viewer/java/)  
- ซื้อ: [Buy GroupDocs License](https://purchase.groupdocs.com/buy)  
- ทดลองใช้งานฟรี: [GroupDocs Free Trial](https://releases.groupdocs.com/viewer/java/)  
- ไลเซนส์ชั่วคราว: [Get Temporary License](https://purchase.groupdocs.com/temporary-license/)  
- สนับสนุน: [GroupDocs Forum](https://forum.groupdocs.com/c/viewer/9)