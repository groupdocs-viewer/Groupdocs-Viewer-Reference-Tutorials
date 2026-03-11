---
date: '2026-01-10'
description: เรียนรู้วิธีแปลงไฟล์ EML เป็น HTML พร้อมรูปแบบวันที่และเวลาที่กำหนดเองและตั้งค่าออฟเซ็ตโซนเวลาใน
  Java ด้วย GroupDocs.Viewer เหมาะสำหรับการเก็บถาวรอีเมลและระบบสนับสนุน.
keywords:
- render emails with custom datetime
- GroupDocs Viewer for Java
- email rendering HTML
title: แปลง EML เป็น HTML พร้อมกำหนดวันที่และเวลาแบบกำหนดเองใน Java ด้วย GroupDocs.Viewer
type: docs
url: /th/java/advanced-rendering/render-emails-custom-datetime-groupdocs-viewer-java/
weight: 1
---

# แปลง EML เป็น HTML พร้อมกำหนดรูปแบบ DateTime ที่กำหนดเองใน Java ด้วย GroupDocs.Viewer

## บทนำ

ในโลกดิจิทัลที่เปลี่ยนแปลงอย่างรวดเร็วในปัจจุบัน การสามารถ **แปลง EML เป็น HTML** ได้อย่างรวดเร็วและพร้อมการแสดงผลวันที่‑เวลาอย่างเหมาะสมเป็นสิ่งสำคัญสำหรับการเก็บถาวร พอร์ทัลสนับสนุน และการปฏิบัติตามกฎหมาย บทแนะนำนี้จะพาคุณผ่านขั้นตอนการแปลงข้อความอีเมลเป็น HTML พร้อมกับการใช้ **รูปแบบ datetime ที่กำหนดเอง** และ **การปรับค่า offset ของโซนเวลา** ด้วย GroupDocs.Viewer สำหรับ Java เมื่อเสร็จสิ้น คุณจะได้โซลูชันที่สามารถนำกลับมาใช้ใหม่ซึ่งทำให้เวลาที่แสดงมีความแม่นยำและอ่านง่าย

![แสดงอีเมลด้วย DateTime ที่กำหนดเองด้วย GroupDocs.Viewer สำหรับ Java](/viewer/advanced-rendering/render-emails-with-custom-datetime-java.png)

**สิ่งที่คุณจะได้เรียนรู้**
- วิธีตั้งค่า GroupDocs.Viewer ในโครงการ Java  
- วิธีแสดงอีเมลเป็น HTML พร้อมทรัพยากรที่ฝังอยู่  
- วิธี **ปรับแต่งรูปแบบวันที่‑เวลา** ของข้อความอีเมลของคุณ (custom datetime format java)  
- วิธี **ตั้งค่า offset ของโซนเวลา** เพื่อให้เวลาที่แสดงถูกต้อง (set timezone offset java)  

## คำตอบอย่างรวดเร็ว
- **GroupDocs.Viewer สามารถแปลง EML เป็น HTML ได้หรือไม่?** ใช่ มันจะเรนเดอร์ไฟล์ EML ไปเป็น HTML โดยตรง  
- **ฉันต้องการไลเซนส์หรือไม่?** การทดลองใช้ฟรีสามารถใช้ทดสอบได้; จำเป็นต้องมีไลเซนส์แบบชำระเงินสำหรับการใช้งานจริง  
- **ต้องการเวอร์ชัน Java ใด?** Java 8 หรือใหม่กว่า  
- **ฉันจะเปลี่ยนรูปแบบวันที่ที่แสดงได้อย่างไร?** ใช้ `options.getEmailOptions().setDateTimeFormat(...)`.  
- **ฉันสามารถปรับโซนเวลาได้หรือไม่?** ได้ ด้วย `options.getEmailOptions().setTimeZoneOffset(TimeZone.getTimeZone(...))`.  

## “แปลง EML เป็น HTML” คืออะไร?
การแปลงไฟล์ EML เป็น HTML จะเปลี่ยนอีเมลดิบ (รวมถึงส่วนหัว, เนื้อหา, และไฟล์แนบ) ให้เป็นรูปแบบที่เป็นมิตรต่อเว็บซึ่งเบราว์เซอร์สามารถแสดงได้โดยไม่ต้องใช้ปลั๊กอินเพิ่มเติม ทำให้สามารถฝังอีเมลในแอปพลิเคชันเว็บ, คลังข้อมูล, หรือแดชบอร์ดสนับสนุนได้อย่างง่ายดาย  

## ทำไมต้องใช้ GroupDocs.Viewer สำหรับงานนี้?
- **การเรนเดอร์แบบไม่มีการพึ่งพา** – ไม่ต้องใช้ Outlook หรือโปรแกรมแยกวิเคราะห์เมลภายนอก  
- **รองรับทรัพยากรที่ฝังอยู่ในตัว** (รูปภาพ, ไฟล์แนบ)  
- **การควบคุมระดับละเอียด** สำหรับการจัดรูปแบบวันที่‑เวลาและการจัดการโซนเวลา  

## ข้อกำหนดเบื้องต้น

- **GroupDocs.Viewer for Java** เวอร์ชัน 25.2 หรือใหม่กว่า  
- **Java Development Kit (JDK)** 8+ และ IDE (IntelliJ IDEA, Eclipse ฯลฯ)  
- ความรู้พื้นฐานของ Java และความคุ้นเคยกับ Maven  

## การตั้งค่า GroupDocs.Viewer สำหรับ Java

### การกำหนดค่า Maven
เพิ่มรีโพซิทอรีของ GroupDocs และการพึ่งพาในไฟล์ `pom.xml` ของคุณ:

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

### การรับไลเซนส์
เริ่มต้นด้วยการทดลองใช้ฟรีหรือขอไลเซนส์ชั่วคราวสำหรับการทดสอบเพิ่มเติม ซื้อไลเซนส์เต็มสำหรับการใช้งานในสภาพแวดล้อมการผลิต  

### การเริ่มต้นพื้นฐาน
```java
import com.groupdocs.viewer.Viewer;

// Initialize Viewer with the path to your document
try (Viewer viewer = new Viewer("path/to/your/document.eml")) {
    // Perform operations here
}
```

## แปลง EML เป็น HTML พร้อมกำหนดรูปแบบ DateTime ที่กำหนดเองใน Java

คำแนะนำขั้นตอนต่อไปนี้จะแสดงวิธี **แปลง EML เป็น HTML** พร้อมกับการใช้รูปแบบ datetime ที่กำหนดเองและการปรับค่า offset ของโซนเวลา  

### ขั้นตอนที่ 1: ตั้งค่าไดเรกทอรีผลลัพธ์และเส้นทางไฟล์
```java
import java.nio.file.Path;

Path outputDirectory = Path.of("YOUR_OUTPUT_DIRECTORY");
Path filePath = outputDirectory.resolve("output.html");
```
*คำอธิบาย:* `Path.of()` สร้างอ้างอิงไปยังโฟลเดอร์ที่ HTML จะถูกบันทึก `resolve()` จะต่อชื่อไฟล์เข้ากับเส้นทาง  

### ขั้นตอนที่ 2: เริ่มต้น Viewer ด้วยไฟล์อีเมล
```java
import com.groupdocs.viewer.Viewer;

try (Viewer viewer = new Viewer("YOUR_DOCUMENT_DIRECTORY/SAMPLE_EML")) {
    // Further configuration goes here
}
```
*คำอธิบาย:* อินสแตนซ์ `Viewer` ชี้ไปที่ไฟล์ EML ที่คุณต้องการแปลง  

### ขั้นตอนที่ 3: กำหนดค่า HtmlViewOptions
```java
import com.groupdocs.viewer.options.HtmlViewOptions;

HtmlViewOptions options = HtmlViewOptions.forEmbeddedResources(filePath);
```
*คำอธิบาย:* `forEmbeddedResources()` จะรวมรูปภาพและทรัพยากรอื่น ๆ เข้าไปในผลลัพธ์ HTML โดยตรง  

### ขั้นตอนที่ 4: ตั้งค่ารูปแบบ DateTime ที่กำหนดเอง *(custom datetime format java)*
```java
options.getEmailOptions().setDateTimeFormat("MM d yyyy HH:mm tt zzz");
```
*คำอธิบาย:* แพทเทิร์นนี้จะแสดงเดือน, วัน, ปี, ชั่วโมง, นาที, ตัวบ่งชี้ AM/PM, และค่า offset ของโซนเวลา (`zzz`).  

### ขั้นตอนที่ 5: ตั้งค่า TimeZone Offset *(set timezone offset java)*
```java
import java.util.TimeZone;

options.getEmailOptions().setTimeZoneOffset(TimeZone.getTimeZone("GMT+1"));
```
*คำอธิบาย:* ปรับเวลาที่แสดงให้ตรงกับโซนเวลาที่ต้องการ แทนที่ `"GMT+1"` ด้วยตัวระบุโซนที่ถูกต้องใด ๆ  

### ขั้นตอนที่ 6: เรนเดอร์เอกสาร
```java
viewer.view(options);
```
*คำอธิบาย:* ดำเนินการแปลงและสร้างไฟล์ HTML ที่มีการตั้งค่าตามวันที่‑เวลาที่กำหนดเองของคุณ  

## เคล็ดลับการแก้ไขปัญหา
- **FileNotFoundException:** ตรวจสอบเส้นทางที่ใช้ใน `Viewer` และ `Path.of()` อีกครั้ง  
- **เวลาแสดงไม่ถูกต้อง:** ตรวจสอบให้แน่ใจว่า ID ของ `TimeZone` ตรงกับภูมิภาคเป้าหมายของคุณ  
- **รูปภาพหายไป:** ตรวจสอบว่าคุณใช้ `HtmlViewOptions.forEmbeddedResources()`; หากไม่ใช้ ทรัพยากรภายนอกอาจไม่ถูกรวม  

## การประยุกต์ใช้งานจริง
1. **การเก็บอีเมล:** เก็บสแนปช็อต HTML ที่สามารถค้นหาได้ของอีเมลเพื่อการปฏิบัติตาม  
2. **พอร์ทัลสนับสนุนลูกค้า:** แสดงตั๋วที่เข้ามาพร้อมเวลาท้องถิ่นที่แม่นยำ  
3. **เอกสารทางกฎหมาย:** สร้างบันทึกอีเมลที่พร้อมใช้ในศาลพร้อมเวลาที่เป็นมาตรฐาน  

## ข้อควรพิจารณาด้านประสิทธิภาพ
- ปรับใช้บนเซิร์ฟเวอร์เฉพาะสำหรับการแปลงจำนวนมาก  
- ตรวจสอบการใช้ heap ของ Java; เพิ่มค่า `-Xmx` หากพบ `OutOfMemoryError`  
- แคช HTML ที่เรนเดอร์เมื่ออีเมลเดียวกันถูกเรียกหลายครั้ง  

## สรุป
ตอนนี้คุณมีวิธีที่ครบถ้วนและพร้อมใช้งานในสภาพแวดล้อมการผลิตเพื่อ **แปลง EML เป็น HTML** พร้อมรูปแบบ datetime ที่กำหนดเองและการปรับค่า offset ของโซนเวลาโดยใช้ GroupDocs.Viewer สำหรับ Java วิธีนี้ช่วยเพิ่มความอ่านง่าย, ทำให้เวลาที่แสดงแม่นยำ, และผสานรวมอย่างราบรื่นกับกระบวนการเก็บถาวรหรือการสนับสนุน  

**ขั้นตอนต่อไป:** สำรวจตัวเลือก Viewer เพิ่มเติม เช่น การจัดสไตล์ CSS, การแบ่งหน้า, หรือการแปลงเป็น PDF เพื่อปรับผลลัพธ์ให้ตรงกับความต้องการของคุณ  

## คำถามที่พบบ่อย

**Q: ฉันจะจัดการไฟล์ EML ที่มีไฟล์แนบอย่างไร?**  
A: ไฟล์แนบจะถูกฝังอัตโนมัติเมื่อคุณใช้ `HtmlViewOptions.forEmbeddedResources()` คุณยังสามารถดึงไฟล์แนบออกได้ผ่าน Viewer API หากต้องการ  

**Q: ฉันสามารถเปลี่ยนเทมเพลต HTML หรือเพิ่ม CSS ที่กำหนดเองได้หรือไม่?**  
A: ได้ หลังจากการเรนเดอร์คุณสามารถแก้ไขไฟล์ HTML ที่สร้างขึ้นหรือแทรก CSS ผ่านโปรแกรมก่อนบันทึก  

**Q: สามารถเรนเดอร์ไฟล์ EML หลายไฟล์พร้อมกันได้หรือไม่?**  
A: ให้ใส่ตรรกะการเรนเดอร์ไว้ในลูปและใช้อินสแตนซ์ `HtmlViewOptions` เดียวกันสำหรับแต่ละไฟล์  

**Q: ถ้าฉันต้องการสนับสนุนรูปแบบอีเมลอื่นเช่น MSG จะทำอย่างไร?**  
A: GroupDocs.Viewer ยังรองรับ MSG, PST และคอนเทนเนอร์อีเมลอื่น ๆ — เพียงเปลี่ยนส่วนขยายไฟล์ในคอนสตรัคเตอร์ของ `Viewer`  

**Q: ฉันต้องการไลเซนส์แยกสำหรับแต่ละเซิร์ฟเวอร์หรือไม่?**  
A: การให้ไลเซนส์เป็นต่อการปรับใช้; โปรดดูคู่มือการให้ไลเซนส์ของ GroupDocs สำหรับสถานการณ์หลายเซิร์ฟเวอร์  

## แหล่งข้อมูล

- [เอกสารประกอบ](https://docs.groupdocs.com/viewer/java/)
- [อ้างอิง API](https://reference.groupdocs.com/viewer/java/)
- [ดาวน์โหลด](https://releases.groupdocs.com/viewer/java/)
- [ซื้อ](https://purchase.groupdocs.com/buy)
- [ทดลองใช้ฟรี](https://releases.groupdocs.com/viewer/java/)
- [ไลเซนส์ชั่วคราว](https://purchase.groupdocs.com/temporary-license/)
- [ฟอรั่มสนับสนุน](https://forum.groupdocs.com/c/viewer/9)

---

**อัปเดตล่าสุด:** 2026-01-10  
**ทดสอบกับ:** GroupDocs.Viewer 25.2 (Java)  
**ผู้เขียน:** GroupDocs  

---