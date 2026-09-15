---
date: '2026-09-15'
description: เรียนรู้วิธีแปลง eml เป็น html ด้วยรูปแบบ datetime แบบกำหนดเองและการปรับค่า
  timezone offset โดยใช้ GroupDocs.Viewer สำหรับ Java — เหมาะสำหรับการเก็บถาวรอีเมลและพอร์ทัลสนับสนุน
keywords:
- convert eml to html
- custom datetime format
- set timezone offset
- email rendering html
lastmod: '2026-09-15'
og_description: แปลง eml เป็น html ด้วยรูปแบบ datetime แบบกำหนดเองและ timezone offset
  โดยใช้ GroupDocs.Viewer สำหรับ Java. ทำตามคู่มือ step‑by‑step นี้เพื่อการแสดงผลอีเมลที่แม่นยำ
og_image_alt: Screenshot of GroupDocs.Viewer rendering an email to HTML with custom
  datetime in Java
og_title: แปลง eml เป็น html ด้วย datetime แบบกำหนดเองใน java โดยใช้ GroupDocs.Viewer
schemas:
- author: GroupDocs
  dateModified: '2026-09-15'
  description: Learn how to convert eml to html with a custom datetime format and
    timezone offset using GroupDocs.Viewer for Java—ideal for email archiving and
    support portals.
  headline: Convert eml to html with custom datetime in java using GroupDocs.Viewer
  type: TechArticle
- description: Learn how to convert eml to html with a custom datetime format and
    timezone offset using GroupDocs.Viewer for Java—ideal for email archiving and
    support portals.
  name: Convert eml to html with custom datetime in java using GroupDocs.Viewer
  steps:
  - name: set up output directory and file path
    text: Define where the generated HTML will be saved. *Explanation:* `Path.of()`
      creates a reference to the folder where the HTML will be saved. `resolve()`
      appends the file name.
  - name: initialize viewer with email file
    text: Instantiate the `Viewer` class for the target EML file. *Explanation:* The
      `Viewer` instance points to the EML file you want to convert.
  - name: configure HtmlViewOptions
    text: Create an `HtmlViewOptions` object that bundles images and other resources
      directly into the HTML output. *Explanation:* `forEmbeddedResources()` bundles
      images and other resources directly into the HTML output.
  - name: set custom datetime format *(custom datetime java)*
    text: '`setDateTimeFormat` sets the date‑time pattern used when rendering email
      timestamps. Define the pattern that will be used for all timestamps in the rendered
      HTML. *Explanation:* This pattern displays the month, day, year, hour, minute,
      AM/PM marker, and the timezone offset (`zzz`).'
  - name: set timezone offset *(timezone offset java)*
    text: '`setTimeZoneOffset` specifies the time‑zone that will be applied to all
      email timestamps. Adjust timestamps to the desired time zone. *Explanation:*
      Adjusts the rendered timestamps to the desired time zone. Replace `"GMT+1"`
      with any valid zone identifier.'
  - name: render document
    text: Execute the conversion and produce the final HTML file. *Explanation:* Executes
      the conversion, producing an HTML file with your custom date‑time settings.
  type: HowTo
- questions:
  - answer: Attachments are automatically embedded when you use `HtmlViewOptions.forEmbeddedResources()`.
      You can also extract them via the Viewer API if you need separate files.
    question: How do I handle eml files with attachments?
  - answer: Yes, after rendering you can edit the generated HTML file or inject CSS
      programmatically before saving.
    question: Can I change the HTML template or add custom CSS?
  - answer: Wrap the rendering logic in a loop and reuse the same `HtmlViewOptions`
      instance for each file.
    question: Is it possible to render multiple eml files in a batch?
  - answer: GroupDocs.Viewer also supports MSG, PST, and other email containers—simply
      change the file extension in the `Viewer` constructor.
    question: What if I need to support other email formats like msg?
  - answer: Licensing is per deployment; consult the GroupDocs licensing guide for
      multi‑server scenarios.
    question: Do I need a separate license for each server?
  type: FAQPage
tags:
- convert eml
- GroupDocs Viewer
- java email conversion
- email to html
- custom datetime
title: แปลง eml เป็น html ด้วย datetime แบบกำหนดเองใน java โดยใช้ GroupDocs.Viewer
type: docs
url: /th/java/advanced-rendering/render-emails-custom-datetime-groupdocs-viewer-java/
weight: 1
---

# แปลง eml เป็น html ด้วย datetime ที่กำหนดเองใน java โดยใช้ GroupDocs.Viewer

ในระบบสนับสนุนและการจัดเก็บข้อมูลสมัยใหม่ การ **แปลง eml เป็น html** อย่างรวดเร็วพร้อมการรักษาเวลาตราบตรงเป็นความสามารถที่จำเป็นอย่างยิ่ง บทแนะนำนี้จะแสดงวิธีการเรนเดอร์อีเมล EML เป็น HTML, ใช้ **รูปแบบ datetime ที่กำหนดเอง**, และตั้ง **ค่า offset ของโซนเวลา** ด้วย GroupDocs.Viewer สำหรับ Java. เมื่อเสร็จคุณจะได้โค้ดส่วนนำกลับมาใช้ใหม่ที่สร้างมุมมองอีเมลที่แม่นยำและพร้อมสำหรับเว็บสำหรับกระบวนการ **การแปลง email เป็น html** ใด ๆ

![เรนเดอร์อีเมลด้วย DateTime ที่กำหนดเองด้วย GroupDocs.Viewer สำหรับ Java](/viewer/advanced-rendering/render-emails-with-custom-datetime-java.png)

## คำตอบด่วน
- **GroupDocs.Viewer สามารถแปลง EML เป็น HTML ได้หรือไม่?** ใช่ – API เรนเดอร์ไฟล์ EML โดยตรงเป็น HTML โดยไม่ต้องใช้ไคลเอนต์เมลภายนอก.  
- **ฉันต้องการไลเซนส์สำหรับการใช้งานจริงหรือไม่?** การทดลองใช้ฟรีเพียงพอสำหรับการทดสอบ; จำเป็นต้องมีไลเซนส์แบบชำระเงินสำหรับการใช้งานจริง.  
- **เวอร์ชัน Java ที่รองรับคืออะไร?** Java 8 หรือใหม่กว่าได้รับการสนับสนุนเต็มที่.  
- **ฉันจะเปลี่ยนรูปแบบวันที่ที่แสดงอย่างไร?** เรียก `options.getEmailOptions().setDateTimeFormat("MMM dd, yyyy hh:mm a zzz")`.  
- **ฉันสามารถปรับโซนเวลาได้หรือไม่?** ได้, ใช้ `options.getEmailOptions().setTimeZoneOffset(TimeZone.getTimeZone("GMT+1"))`.

## “แปลง eml เป็น html” คืออะไร
`Convert eml to html` คือกระบวนการแปลงไฟล์อีเมล EML ให้เป็นเอกสาร HTML เพื่อการแสดงผลในเบราว์เซอร์ การแปลงไฟล์ EML เป็น HTML จะเปลี่ยนอีเมลดิบ (รวมถึงส่วนหัว, เนื้อหา, และไฟล์แนบ) ให้เป็นรูปแบบที่เหมาะกับเว็บซึ่งเบราว์เซอร์สามารถแสดงได้โดยไม่ต้องใช้ปลั๊กอินเพิ่มเติม สิ่งนี้ทำให้การฝังอีเมลในแอปพลิเคชันเว็บ, คลังข้อมูล, หรือแดชบอร์ดสนับสนุนเป็นเรื่องง่าย.

## ทำไมต้องใช้ GroupDocs.Viewer สำหรับงานนี้
GroupDocs.Viewer รองรับ **รูปแบบไฟล์เข้าและออกกว่า 50 ประเภท**, รวมถึง EML, MSG, PST, และ PDF, และสามารถเรนเดอร์อีเมลหลายร้อยหน้าโดยไม่ต้องโหลดไฟล์ทั้งหมดเข้าสู่หน่วยความจำ เครื่องยนต์ที่ไม่มีการพึ่งพาใด ๆ ทำให้ไม่ต้องใช้ Outlook หรือพาร์เซอร์ของบุคคลที่สาม, ให้คุณควบคุม **รูปแบบ datetime ที่กำหนดเอง** และ **ค่า offset ของโซนเวลา** อย่างเต็มที่ในขณะที่ใช้ทรัพยากรต่ำ.

## ข้อกำหนดเบื้องต้น
- GroupDocs.Viewer for Java ≥ 25.2  
- JDK 8+ และ IDE สำหรับ Java (IntelliJ IDEA, Eclipse, VS Code)  
- Maven สำหรับการจัดการ dependencies  

## การตั้งค่า GroupDocs.Viewer สำหรับ Java

### การกำหนดค่า Maven
เพิ่มรีโพซิทอรีของ GroupDocs และ dependency ของ Viewer ลงในไฟล์ `pom.xml` ของคุณ.

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
เริ่มต้นด้วยการทดลองใช้ฟรีหรือขอไลเซนส์ชั่วคราวสำหรับการทดสอบแบบขยาย. ซื้อไลเซนส์เต็มรูปแบบสำหรับการใช้งานในสภาพการผลิต.

### การเริ่มต้นพื้นฐาน
สร้างอินสแตนซ์ `Viewer` ที่ชี้ไปยังไฟล์ EML ที่คุณต้องการแปลง.

```java
import com.groupdocs.viewer.Viewer;

// Initialize Viewer with the path to your document
try (Viewer viewer = new Viewer("path/to/your/document.eml")) {
    // Perform operations here
}
```

## แปลง eml เป็น html ด้วย datetime ที่กำหนดเองใน java

ขั้นตอนต่อไปนี้จะพาคุณผ่านการเรนเดอร์ไฟล์ EML เป็น HTML พร้อมการใช้รูปแบบ datetime ที่กำหนดเองและค่า offset ของโซนเวลา.

### ขั้นตอนที่ 1: ตั้งค่าไดเรกทอรีและเส้นทางไฟล์ผลลัพธ์
กำหนดตำแหน่งที่ HTML ที่สร้างขึ้นจะถูกบันทึก.

```java
import java.nio.file.Path;

Path outputDirectory = Path.of("YOUR_OUTPUT_DIRECTORY");
Path filePath = outputDirectory.resolve("output.html");
```
*คำอธิบาย:* `Path.of()` สร้างการอ้างอิงไปยังโฟลเดอร์ที่ HTML จะถูกบันทึก. `resolve()` เพิ่มชื่อไฟล์.

### ขั้นตอนที่ 2: เริ่มต้น viewer ด้วยไฟล์อีเมล
สร้างอินสแตนซ์ของคลาส `Viewer` สำหรับไฟล์ EML เป้าหมาย.

```java
import com.groupdocs.viewer.Viewer;

try (Viewer viewer = new Viewer("YOUR_DOCUMENT_DIRECTORY/SAMPLE_EML")) {
    // Further configuration goes here
}
```
*คำอธิบาย:* อินสแตนซ์ `Viewer` ชี้ไปยังไฟล์ EML ที่คุณต้องการแปลง.

### ขั้นตอนที่ 3: กำหนดค่า HtmlViewOptions
สร้างอ็อบเจ็กต์ `HtmlViewOptions` ที่รวมรูปภาพและทรัพยากรอื่น ๆ เข้าไปในผลลัพธ์ HTML โดยตรง.

```java
import com.groupdocs.viewer.options.HtmlViewOptions;

HtmlViewOptions options = HtmlViewOptions.forEmbeddedResources(filePath);
```
*คำอธิบาย:* `forEmbeddedResources()` รวมรูปภาพและทรัพยากรอื่น ๆ เข้าไปในผลลัพธ์ HTML โดยตรง.

### ขั้นตอนที่ 4: ตั้งค่ารูปแบบ datetime ที่กำหนดเอง *(custom datetime java)*
`setDateTimeFormat` กำหนดรูปแบบวันที่‑เวลา ที่ใช้เมื่อเรนเดอร์ timestamp ของอีเมล.  
กำหนดรูปแบบที่จะใช้สำหรับ timestamp ทั้งหมดใน HTML ที่เรนเดอร์.

```java
options.getEmailOptions().setDateTimeFormat("MM d yyyy HH:mm tt zzz");
```
*คำอธิบาย:* รูปแบบนี้จะแสดงเดือน, วัน, ปี, ชั่วโมง, นาที, ตัวบ่งชี้ AM/PM, และค่า offset ของโซนเวลา (`zzz`).

### ขั้นตอนที่ 5: ตั้งค่า offset ของโซนเวลา *(timezone offset java)*
`setTimeZoneOffset` ระบุโซนเวลาที่จะนำไปใช้กับ timestamp ของอีเมลทั้งหมด.  
ปรับ timestamp ให้เป็นโซนเวลาที่ต้องการ.

```java
import java.util.TimeZone;

options.getEmailOptions().setTimeZoneOffset(TimeZone.getTimeZone("GMT+1"));
```
*คำอธิบาย:* ปรับ timestamp ที่เรนเดอร์ให้เป็นโซนเวลาที่ต้องการ. แทนที่ `"GMT+1"` ด้วยตัวระบุโซนที่ถูกต้องใด ๆ.

### วิธีปรับโซนเวลาอีเมลใน java
หากคุณต้องการ **ปรับโซนเวลาอีเมล** นอกเหนือจากการปรับ offset อย่างง่าย—เช่นการจัดการการเปลี่ยนแปลงเวลาออมแสง—คุณสามารถดึงอ็อบเจ็กต์ `TimeZone` ที่เหมาะสมจาก API `java.util.TimeZone` โดยใช้ ID ของภูมิภาคเช่น `"Europe/Paris"` หรือ `"America/New_York"` แล้วส่งให้กับ `setTimeZoneOffset`. วิธีนี้ทำให้ timestamp ของอีเมลแสดงเวลาในท้องถิ่นที่ถูกต้องเสมอ.

### ขั้นตอนที่ 6: เรนเดอร์เอกสาร
ดำเนินการแปลงและสร้างไฟล์ HTML สุดท้าย.

```java
viewer.view(options);
```
*คำอธิบาย:* ดำเนินการแปลง, สร้างไฟล์ HTML พร้อมการตั้งค่า date‑time ที่กำหนดเองของคุณ.

## รูปแบบ datetime ที่กำหนดเองมีผลต่อ HTML ที่เรนเดอร์อย่างไร
รูปแบบ datetime ที่กำหนดเองกำหนดว่าตำแหน่ง timestamp ของแต่ละอีเมลจะแสดงอย่างไรใน HTML ที่สร้างขึ้น, ส่งผลต่อความอ่านง่ายและการปฏิบัติตามท้องถิ่น. โดยการระบุรูปแบบเช่น `"MMM dd, yyyy hh:mm a zzz"` คุณจะทำให้ทุกวันที่แสดงอย่างสม่ำเสมอ, รวมถึงตัวย่อเดือน, วัน, ปี, ชั่วโมง, นาที, ตัวบ่งชี้ AM/PM, และค่า offset ของโซนเวลาอย่างชัดเจน, ซึ่งสำคัญสำหรับทีมสนับสนุนระดับโลก.

## GroupDocs.Viewer รองรับรูปแบบไฟล์ใดบ้างสำหรับการเรนเดอร์อีเมล
GroupDocs.Viewer สามารถเรนเดอร์ไฟล์ **EML, MSG, PST, MBOX, และ EMLX** ไปเป็น HTML, PDF, PNG, และ JPEG. รองรับรูปแบบเอกสารและภาพรวมกว่า 50 รูปแบบ, ทำให้คุณสามารถแปลงอีเมลเป็นเอาต์พุตที่เป็นมิตรต่อเว็บที่พบบ่อยที่สุดโดยไม่ต้องใช้ตัวแปลงเพิ่มเติม.

## ฉันจะทำการแปลงหลายไฟล์ eml เป็นชุดได้อย่างไร
วางไฟล์ EML ทั้งหมดในไดเรกทอรีเดียว, วนลูปผ่านแต่ละไฟล์ด้วยโครงสร้าง `for` หรือ `foreach`, ใช้อ็อบเจ็กต์ `HtmlViewOptions` ตัวเดียวกันซ้ำ, และเรียก `viewer.view` สำหรับแต่ละไฟล์. วิธีนี้ลดภาระการสร้างอ็อบเจ็กต์และเร่งความเร็วการแปลงเป็นชุด.

## เคล็ดลับการแก้ไขปัญหา
- **FileNotFoundException:** ตรวจสอบเส้นทางที่ใช้ใน `Viewer` และ `Path.of()`.  
- **Incorrect timestamps:** ตรวจสอบให้แน่ใจว่า ID ของ `TimeZone` ตรงกับภูมิภาคเป้าหมายของคุณ.  
- **Missing images:** ยืนยันว่าคุณใช้ `HtmlViewOptions.forEmbeddedResources()`; หากไม่ใช้ทรัพยากรภายนอกอาจถูกละเว้น.  

## การประยุกต์ใช้งานจริง
1. **การจัดเก็บอีเมล:** เก็บสแนปช็อต HTML ที่สามารถค้นหาได้ของอีเมลเพื่อการตรวจสอบตามข้อกำหนด.  
2. **พอร์ทัลสนับสนุนลูกค้า:** แสดงตั๋วที่เข้ามาพร้อมเวลาท้องถิ่นที่แม่นยำสำหรับเจ้าหน้าที่ทั่วโลก.  
3. **เอกสารทางกฎหมาย:** สร้างบันทึกอีเมลพร้อมใช้ในศาลที่มี timestamp มาตรฐาน.  

## ข้อควรพิจารณาด้านประสิทธิภาพ
- ปรับใช้บนเซิร์ฟเวอร์เฉพาะสำหรับการแปลงเป็นชุด.  
- ตรวจสอบการใช้ heap ของ Java; เพิ่ม `-Xmx` หากพบ `OutOfMemoryError`.  
- แคช HTML ที่เรนเดอร์เมื่ออีเมลเดียวกันถูกเรียกหลายครั้งเพื่อ ลดการใช้ CPU.  

## สรุป
ตอนนี้คุณมีวิธีที่ครบถ้วนและพร้อมใช้งานในสภาพการผลิตเพื่อ **แปลง eml เป็น html** ด้วยรูปแบบ datetime ที่กำหนดเองและค่า offset ของโซนเวลาโดยใช้ GroupDocs.Viewer สำหรับ Java. โซลูชันนี้ช่วยเพิ่มความอ่านง่าย, รับประกันความแม่นยำของ timestamp, และผสานเข้ากับกระบวนการจัดเก็บ, สนับสนุน, หรือกฎหมายได้อย่างราบรื่น.

**ขั้นตอนต่อไป:** สำรวจตัวเลือก Viewer เพิ่มเติมเช่นการฉีด CSS ที่กำหนดเอง, การแบ่งหน้า, หรือการแปลงเป็น PDF เพื่อปรับผลลัพธ์ให้ตรงกับความต้องการของแอปพลิเคชันของคุณ.

## คำถามที่พบบ่อย

**Q: ฉันจะจัดการไฟล์ eml ที่มีไฟล์แนบอย่างไร?**  
A: ไฟล์แนบจะถูกฝังอัตโนมัติเมื่อคุณใช้ `HtmlViewOptions.forEmbeddedResources()`. คุณสามารถดึงไฟล์แนบออกผ่าน Viewer API หากต้องการไฟล์แยกต่างหาก.

**Q: ฉันสามารถเปลี่ยนเทมเพลต HTML หรือเพิ่ม CSS ที่กำหนดเองได้หรือไม่?**  
A: ได้, หลังจากเรนเดอร์คุณสามารถแก้ไขไฟล์ HTML ที่สร้างขึ้นหรือฉีด CSS ผ่านโปรแกรมก่อนบันทึก.

**Q: สามารถเรนเดอร์หลายไฟล์ eml เป็นชุดได้หรือไม่?**  
A: ห่อหุ้มตรรกะการเรนเดอร์ในลูปและใช้ `HtmlViewOptions` ตัวเดียวกันซ้ำสำหรับแต่ละไฟล์.

**Q: ถ้าฉันต้องการสนับสนุนรูปแบบอีเมลอื่นเช่น msg จะทำอย่างไร?**  
A: GroupDocs.Viewer ยังรองรับ MSG, PST, และคอนเทนเนอร์อีเมลอื่น ๆ—เพียงเปลี่ยนส่วนขยายไฟล์ในคอนสตรัคเตอร์ `Viewer`.

**Q: ฉันต้องการไลเซนส์แยกสำหรับแต่ละเซิร์ฟเวอร์หรือไม่?**  
A: ไลเซนส์เป็นต่อการปรับใช้; โปรดปรึกษาคู่มือไลเซนส์ของ GroupDocs สำหรับสถานการณ์หลายเซิร์ฟเวอร์.

## แหล่งข้อมูล

- [เอกสาร](https://docs.groupdocs.com/viewer/java/)
- [อ้างอิง API](https://reference.groupdocs.com/viewer/java/)
- [ดาวน์โหลด](https://releases.groupdocs.com/viewer/java/)
- [ซื้อ](https://purchase.groupdocs.com/buy)
- [ทดลองใช้ฟรี](https://releases.groupdocs.com/viewer/java/)
- [ไลเซนส์ชั่วคราว](https://purchase.groupdocs.com/temporary-license/)
- [ฟอรั่มสนับสนุน](https://forum.groupdocs.com/c/viewer/9)

---

**อัปเดตล่าสุด:** 2026-09-15  
**ทดสอบกับ:** GroupDocs.Viewer 25.2 (Java)  
**ผู้เขียน:** GroupDocs

## บทแนะนำที่เกี่ยวข้อง

- [แปลงอีเมลเป็น HTML & เปลี่ยนชื่อฟิลด์ – GroupDocs Viewer Java](/viewer/java/advanced-rendering/rename-email-fields-html-groupdocs-viewer-java/)
- [java แปลง msg เป็น pdf – ปรับประสิทธิภาพการเรนเดอร์ Email‑to‑PDF ด้วย GroupDocs.Viewer](/viewer/java/performance-optimization/optimize-email-pdf-rendering-java-groupdocs-viewer-api/)
- [Groupdocs Viewer Java การเรนเดอร์ HTML แบบตอบสนอง](/viewer/java/advanced-rendering/groupdocs-viewer-java-responsive-html-rendering/)
