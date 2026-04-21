---
date: '2026-03-24'
description: เรียนรู้วิธีแปลงไฟล์ EML เป็น HTML พร้อมรูปแบบวันที่และเวลาที่กำหนดเองและตั้งค่าออฟเซ็ตเขตเวลาใน
  Java ด้วย GroupDocs.Viewer เหมาะสำหรับการจัดเก็บอีเมลและระบบสนับสนุน.
keywords:
- render emails with custom datetime
- GroupDocs Viewer for Java
- email rendering HTML
title: แปลง EML เป็น HTML พร้อมกำหนดวันที่และเวลาแบบกำหนดเองใน Java ด้วย GroupDocs.Viewer
type: docs
url: /th/java/advanced-rendering/render-emails-custom-datetime-groupdocs-viewer-java/
weight: 1
---

# แปลง EML เป็น HTML ด้วย DateTime ที่กำหนดเองใน Java โดยใช้ GroupDocs.Viewer

ในโลกดิจิทัลที่เปลี่ยนแปลงอย่างรวดเร็วในวันนี้ การสามารถ **แปลง EML เป็น HTML** ได้อย่างรวดเร็วและพร้อมการแสดงผลวันที่‑เวลาอย่างเหมาะสมเป็นสิ่งสำคัญสำหรับการเก็บถาวร พอร์ทัลสนับสนุน และการปฏิบัติตามกฎหมาย บทแนะนำนี้จะพาคุณผ่านการแปลงข้อความอีเมลเป็น HTML พร้อมการใช้ **รูปแบบวันที่‑เวลาแบบกำหนดเอง** และ **การปรับเขตเวลา** โดยใช้ GroupDocs.Viewer สำหรับ Java เมื่อเสร็จแล้ว คุณจะมีโซลูชันที่นำกลับมาใช้ใหม่ได้ซึ่งทำให้เวลาต่าง ๆ มีความแม่นยำและอ่านง่าย เหมาะสำหรับกระบวนการทำงาน **email to HTML Java** ใด ๆ

![Render Emails with Custom DateTime with GroupDocs.Viewer for Java](/viewer/advanced-rendering/render-emails-with-custom-datetime-java.png)

**สิ่งที่คุณจะได้เรียนรู้**
- วิธีตั้งค่า GroupDocs.Viewer ในโครงการ Java  
- วิธีแปลงอีเมลเป็น HTML พร้อมทรัพยากรที่ฝังอยู่  
- วิธี **ปรับแต่งรูปแบบวันที่‑เวลา** ของข้อความอีเมลของคุณ (custom datetime java)  
- วิธี **ตั้งค่าการปรับเขตเวลา** เพื่อให้เวลาตรงกัน (timezone offset java)  

## คำตอบอย่างรวดเร็ว
- **GroupDocs.Viewer สามารถแปลง EML เป็น HTML ได้หรือไม่?** ใช่, มันสามารถแปลงไฟล์ EML ไปเป็น HTML ได้โดยตรง  
- **ฉันต้องมีลิขสิทธิ์หรือไม่?** ทดลองใช้ฟรีทำงานสำหรับการทดสอบ; จำเป็นต้องมีลิขสิทธิ์แบบชำระเงินสำหรับการใช้งานจริง  
- **ต้องใช้ Java เวอร์ชันใด?** Java 8 หรือใหม่กว่า  
- **ฉันจะเปลี่ยนรูปแบบวันที่ที่แสดงอย่างไร?** ใช้ `options.getEmailOptions().setDateTimeFormat(...)`  
- **ฉันสามารถปรับเขตเวลาได้หรือไม่?** ใช่, ด้วย `options.getEmailOptions().setTimeZoneOffset(TimeZone.getTimeZone(...))`  

## “การแปลง EML เป็น HTML” คืออะไร?
การแปลงไฟล์ EML เป็น HTML จะเปลี่ยนอีเมลดิบ (รวมถึงส่วนหัว, เนื้อหา, และไฟล์แนบ) ให้เป็นรูปแบบที่เป็นมิตรกับเว็บซึ่งเบราว์เซอร์สามารถแสดงได้โดยไม่ต้องใช้ปลั๊กอินเพิ่มเติม สิ่งนี้ทำให้การฝังอีเมลในแอปพลิเคชันเว็บ, คลังข้อมูล, หรือแดชบอร์ดสนับสนุนเป็นเรื่องง่าย

## ทำไมต้องใช้ GroupDocs.Viewer สำหรับงานนี้?
- **การแสดงผลไม่มีการพึ่งพาไลบรารีภายนอก** – ไม่ต้องใช้ Outlook หรือเครื่องมือแยกวิเคราะห์เมล  
- **รองรับทรัพยากรที่ฝังอยู่โดยอัตโนมัติ** (รูปภาพ, ไฟล์แนบ)  
- **ควบคุมระดับละเอียด** สำหรับการจัดรูปแบบวันที่‑เวลาและการจัดการเขตเวลา  

## ข้อกำหนดเบื้องต้น

- **GroupDocs.Viewer for Java** เวอร์ชัน 25.2 หรือใหม่กว่า  
- **Java Development Kit (JDK)** 8+ และ IDE (IntelliJ IDEA, Eclipse, ฯลฯ)  
- ความรู้พื้นฐานของ Java และความคุ้นเคยกับ Maven  

## การตั้งค่า GroupDocs.Viewer สำหรับ Java

### การกำหนดค่า Maven
เพิ่มรีโพซิทอรีของ GroupDocs และ dependency ลงใน `pom.xml` ของคุณ:

```xml
<repositories>
    <repository>
        <id>groupdocs-releases</id>
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
เริ่มต้นด้วยการทดลองใช้ฟรีหรือขอรับลิขสิทธิ์ชั่วคราวสำหรับการทดสอบแบบขยาย การซื้อไลเซนส์เต็มรูปแบบสำหรับการใช้งานในสภาพแวดล้อมการผลิต

### การเริ่มต้นพื้นฐาน
```java
import com.groupdocs.viewer.Viewer;

// Initialize Viewer with the path to your document
try (Viewer viewer = new Viewer("path/to/your/document.eml")) {
    // Perform operations here
}
```

## แปลง EML เป็น HTML ด้วย DateTime ที่กำหนดเองใน Java

คู่มือขั้นตอนต่อไปนี้จะแสดงวิธี **แปลง EML เป็น HTML** พร้อมการใช้รูปแบบวันที่‑เวลาแบบกำหนดเองและการปรับเขตเวลา

### ขั้นตอนที่ 1: ตั้งค่าไดเรกทอรีและเส้นทางไฟล์ผลลัพธ์
```java
import java.nio.file.Path;

Path outputDirectory = Path.of("YOUR_OUTPUT_DIRECTORY");
Path filePath = outputDirectory.resolve("output.html");
```
*คำอธิบาย:* `Path.of()` สร้างอ้างอิงไปยังโฟลเดอร์ที่ HTML จะถูกบันทึก `resolve()` จะต่อชื่อไฟล์เข้ากับเส้นทางนั้น

### ขั้นตอนที่ 2: เริ่มต้น Viewer ด้วยไฟล์อีเมล
```java
import com.groupdocs.viewer.Viewer;

try (Viewer viewer = new Viewer("YOUR_DOCUMENT_DIRECTORY/SAMPLE_EML")) {
    // Further configuration goes here
}
```
*คำอธิบาย:* อินสแตนซ์ `Viewer` ชี้ไปยังไฟล์ EML ที่คุณต้องการแปลง

### ขั้นตอนที่ 3: กำหนดค่า HtmlViewOptions
```java
import com.groupdocs.viewer.options.HtmlViewOptions;

HtmlViewOptions options = HtmlViewOptions.forEmbeddedResources(filePath);
```
*คำอธิบาย:* `forEmbeddedResources()` จะรวมรูปภาพและทรัพยากรอื่น ๆ ไว้ในผลลัพธ์ HTML โดยตรง

### ขั้นตอนที่ 4: ตั้งค่ารูปแบบ DateTime ที่กำหนดเอง *(custom datetime java)*
```java
options.getEmailOptions().setDateTimeFormat("MM d yyyy HH:mm tt zzz");
```
*คำอธิบาย:* แพทเทิร์นนี้จะแสดงเดือน, วัน, ปี, ชั่วโมง, นาที, ตัวบ่งชี้ AM/PM, และการปรับเขตเวลา (`zzz`)

### ขั้นตอนที่ 5: ตั้งค่าการปรับเขตเวลา *(timezone offset java)*
```java
import java.util.TimeZone;

options.getEmailOptions().setTimeZoneOffset(TimeZone.getTimeZone("GMT+1"));
```
*คำอธิบาย:* ปรับเวลาที่แสดงผลให้ตรงกับเขตเวลาที่ต้องการ แทนที่ `"GMT+1"` ด้วยตัวระบุโซนที่ถูกต้องใด ๆ

### วิธีปรับเขตเวลาอีเมลใน Java
หากคุณต้องการ **ปรับเขตเวลาอีเมล** อย่างละเอียด เช่น การจัดการการเปลี่ยนแปลงเวลาออมแสง คุณสามารถดึงอ็อบเจกต์ `TimeZone` ที่เหมาะสมจาก API `java.util.TimeZone` โดยใช้รหัสภูมิภาคเช่น `"Europe/Paris"` หรือ `"America/New_York"` แล้วส่งให้กับ `setTimeZoneOffset` วิธีนี้จะทำให้เวลาของอีเมลแสดงผลเป็นเวลาท้องถิ่นที่ถูกต้องเสมอ

### ขั้นตอนที่ 6: แสดงผลเอกสาร
```java
viewer.view(options);
```
*คำอธิบาย:* ดำเนินการแปลงและสร้างไฟล์ HTML ที่มีการตั้งค่ารูปแบบวันที่‑เวลาตามที่กำหนด

## เคล็ดลับการแก้ไขปัญหา
- **FileNotFoundException:** ตรวจสอบเส้นทางที่ใช้ใน `Viewer` และ `Path.of()` อีกครั้ง  
- **เวลาที่แสดงไม่ถูกต้อง:** ยืนยันว่า ID ของ `TimeZone` ตรงกับเขตเป้าหมายของคุณ  
- **รูปภาพหายไป:** ตรวจสอบว่าคุณใช้ `HtmlViewOptions.forEmbeddedResources()` มิฉะนั้นทรัพยากรภายนอกอาจไม่ถูกรวม  

## การประยุกต์ใช้งานจริง
1. **การเก็บถาวรอีเมล:** เก็บ snapshot HTML ที่ค้นหาได้ของอีเมลเพื่อการปฏิบัติตามข้อกำหนด  
2. **พอร์ทัลสนับสนุนลูกค้า:** แสดงตั๋วที่เข้ามาพร้อมเวลาท้องถิ่นที่แม่นยำ  
3. **เอกสารทางกฎหมาย:** ผลิตบันทึกอีเมลพร้อมเวลามาตรฐานที่พร้อมใช้ในศาล  

## พิจารณาด้านประสิทธิภาพ
- ปรับใช้บนเซิร์ฟเวอร์เฉพาะสำหรับการแปลงจำนวนมาก  
- ตรวจสอบการใช้ heap ของ Java; เพิ่มค่า `-Xmx` หากพบ `OutOfMemoryError`  
- แคช HTML ที่แปลงแล้วเมื่ออีเมลเดียวกันถูกเรียกหลายครั้ง  

## สรุป
คุณมีวิธีที่ครบถ้วนและพร้อมใช้งานในระดับผลิตเพื่อ **แปลง EML เป็น HTML** พร้อมรูปแบบวันที่‑เวลาแบบกำหนดเองและการปรับเขตเวลาโดยใช้ GroupDocs.Viewer สำหรับ Java วิธีนี้ช่วยเพิ่มความอ่านง่าย, ความแม่นยำของเวลาต่าง ๆ, และสามารถผสานรวมเข้ากับกระบวนการเก็บถาวรหรือสนับสนุนได้อย่างลงตัว

**ขั้นตอนต่อไป:** สำรวจตัวเลือก Viewer เพิ่มเติม เช่น การจัดสไตล์ CSS, การแบ่งหน้า, หรือการแปลงเป็น PDF เพื่อปรับแต่งผลลัพธ์ให้ตรงกับความต้องการของคุณ

## คำถามที่พบบ่อย

**Q: จะจัดการไฟล์ EML ที่มีไฟล์แนบอย่างไร?**  
A: ไฟล์แนบจะถูกฝังโดยอัตโนมัติเมื่อใช้ `HtmlViewOptions.forEmbeddedResources()` คุณยังสามารถดึงไฟล์แนบออกมาได้ผ่าน Viewer API หากต้องการ

**Q: สามารถเปลี่ยนเทมเพลต HTML หรือเพิ่ม CSS ที่กำหนดเองได้หรือไม่?**  
A: ได้, หลังจากแปลงแล้วคุณสามารถแก้ไขไฟล์ HTML ที่สร้างขึ้นหรือฉีด CSS เข้าด้วยโปรแกรมก่อนบันทึก

**Q: สามารถแปลงไฟล์ EML หลายไฟล์เป็นชุดได้หรือไม่?**  
A: ใช่, ให้วนลูปตรรกะการแปลงและใช้อินสแตนซ์ `HtmlViewOptions` เดียวกันสำหรับแต่ละไฟล์

**Q: หากต้องการสนับสนุนรูปแบบอีเมลอื่นเช่น MSG จะทำอย่างไร?**  
A: GroupDocs.Viewer รองรับ MSG, PST และคอนเทนเนอร์อีเมลอื่น ๆ — เพียงเปลี่ยนนามสกุลไฟล์ในคอนสตรัคเตอร์ของ `Viewer`

**Q: ต้องการลิขสิทธิ์แยกสำหรับแต่ละเซิร์ฟเวอร์หรือไม่?**  
A: การให้ลิขสิทธิ์เป็นตามการปรับใช้; โปรดดูคู่มือการให้ลิขสิทธิ์ของ GroupDocs สำหรับกรณีหลายเซิร์ฟเวอร์

## แหล่งข้อมูล

- [Documentation](https://docs.groupdocs.com/viewer/java/)
- [API Reference](https://reference.groupdocs.com/viewer/java/)
- [Download](https://releases.groupdocs.com/viewer/java/)
- [Purchase](https://purchase.groupdocs.com/buy)
- [Free Trial](https://releases.groupdocs.com/viewer/java/)
- [Temporary License](https://purchase.groupdocs.com/temporary-license/)
- [Support Forum](https://forum.groupdocs.com/c/viewer/9)

---

**Last Updated:** 2026-03-24  
**Tested With:** GroupDocs.Viewer 25.2 (Java)  
**Author:** GroupDocs  

---