---
date: '2026-07-19'
description: เรียนรู้วิธีแปลงไฟล์ PST เป็น HTML และรูปแบบอื่น ๆ เช่น JPG, PNG, PDF
  ด้วย GroupDocs.Viewer for Java คู่มือนี้ครอบคลุมขั้นตอนและการกำหนดค่าที่จำเป็นทั้งหมด
keywords:
- convert pst to html
- convert pst to pdf
- java convert ost
- convert pst to png
- convert pst to jpg
lastmod: '2026-07-19'
og_description: แปลง PST เป็น HTML อย่างรวดเร็วด้วย GroupDocs.Viewer for Java เรียนรู้ขั้นตอนต่อขั้นตอนว่าจะแปลงเป็น
  JPG, PNG, และ PDF อย่างพร้อมใช้งานในสภาพแวดล้อมการผลิตได้อย่างไร
og_image_alt: 'Developer guide: Convert PST to HTML, JPG, PNG, PDF using GroupDocs
  Viewer for Java'
og_title: แปลง PST เป็น HTML ด้วย GroupDocs.Viewer for Java – Fast Email Export
schemas:
- author: GroupDocs
  dateModified: '2026-07-19'
  description: Learn how to convert pst to html and other formats like JPG, PNG, PDF
    using GroupDocs.Viewer for Java. This guide covers all steps and configurations
    needed.
  headline: Convert PST to HTML, JPG, PNG, PDF Using GroupDocs.Viewer for Java
  type: TechArticle
- description: Learn how to convert pst to html and other formats like JPG, PNG, PDF
    using GroupDocs.Viewer for Java. This guide covers all steps and configurations
    needed.
  name: Convert PST to HTML, JPG, PNG, PDF Using GroupDocs.Viewer for Java
  steps:
  - name: Set Up Output Directory
    text: Define a folder where the HTML pages will be written. GroupDocs creates
      a sub‑folder for each email to keep assets organized.
  - name: Configure Load Options
    text: '`LoadOptions` lets you specify password handling, resource‑loading timeouts,
      and selective page rendering. Setting a timeout of 30 seconds works well for
      most server environments.'
  - name: Define HTML View Options
    text: '`HtmlViewOptions` specifies the output folder, resource handling, and optional
      CSS settings for HTML conversion.'
  - name: Initialize Viewer and Render HTML
    text: Create a `Viewer` object, pass the PST file path, and call `view` with the
      `HtmlViewOptions`. The API automatically iterates through all messages inside
      the PST and generates a tidy HTML hierarchy.
  - name: Set Up Output Directory
    text: Create a dedicated folder for JPG snapshots; each email will become one
      or more image files depending on its length.
  - name: Configure Load Options
    text: The same `LoadOptions` used for HTML can be reused here, ensuring consistent
      password handling across formats.
  - name: Define JPG View Options
    text: '`JpgViewOptions` controls image resolution, quality, and output folder
      for JPEG conversion.'
  - name: Initialize Viewer and Render JPG
    text: Use `viewer.view(jpgOptions)` to generate high‑quality JPEG files ready
      for web preview.
  - name: Set Up Output Directory
    text: PNG output is useful when you need lossless quality for archiving or OCR
      processing.
  - name: Configure Load Options
    text: No additional settings are required beyond the password and timeout configuration.
  type: HowTo
- questions:
  - answer: Use `PdfViewOptions` as shown in the PDF rendering section; the rest of
      the code remains identical.
    question: How do I **convert pst to pdf** with the same code base?
  - answer: Yes, provide the password via `LoadOptions.setPassword("yourPassword")`
      before rendering.
    question: Can GroupDocs.Viewer handle encrypted PST files?
  - answer: PNG preserves lossless quality, ideal for screenshots, while JPG offers
      smaller file sizes for email previews.
    question: What is the difference between **java convert pst** to PNG vs JPG?
  - answer: Wrap the rendering logic in a loop that iterates over a directory of PST
      files; reuse the same `Viewer` configuration for each file.
    question: Is there a way to **how to convert pst** files in bulk?
  - answer: Yes, GroupDocs.Viewer streams data and can process files up to 2 GB without
      loading the entire archive into memory.
    question: Does the API support converting PST files larger than 1 GB?
  type: FAQPage
tags:
- convert pst
- GroupDocs.Viewer
- Java document processing
- email conversion
title: แปลงไฟล์ PST เป็น HTML, JPG, PNG, PDF ด้วย GroupDocs.Viewer for Java
type: docs
url: /th/java/export-conversion/convert-pst-ost-groupdocs-viewer-java/
weight: 1
---

# แปลง PST เป็น HTML, JPG, PNG, PDF ด้วย GroupDocs.Viewer สำหรับ Java

คุณกำลังมองหา **convert pst to html** หรือรูปแบบอื่น ๆ เช่น JPG, PNG หรือ PDF หรือไม่? ด้วยไลบรารี GroupDocs.Viewer for Java ที่ทรงพลัง งานนี้จะทำได้อย่างง่ายดายและมีประสิทธิภาพ ในบทแนะนำนี้คุณจะได้เรียนรู้วิธีการแสดงไฟล์ Outlook PST/OST เป็น HTML ที่เหมาะกับเว็บ, ไฟล์รูปภาพ หรือ PDF เดียว ทำให้การจัดเก็บอีเมลของคุณง่ายต่อการแชร์และเก็บรักษา.

![แปลง PST/OST เป็น HTML, JPG, PNG, PDF ด้วย GroupDocs.Viewer for Java](/viewer/export-conversion/convert-pst-ost-to-html-jpg-png-pdf.png)

[แปลง PST/OST เป็น HTML, JPG, PNG, PDF ด้วย GroupDocs.Viewer for Java](/viewer/export-conversion/convert-pst-ost-to-html-jpg-png-pdf.png)

**สิ่งที่คุณจะได้เรียนรู้**
- วิธีการตั้งค่า GroupDocs.Viewer for Java ในโครงการ Maven.  
- คำแนะนำแบบขั้นตอนต่อขั้นตอนเพื่อ **java convert pst** ไฟล์เป็น HTML, JPG, PNG, และ PDF.  
- เคล็ดลับการกำหนดค่าเพื่อประสิทธิภาพสูงสุดและข้อผิดพลาดทั่วไป.

## คำตอบอย่างรวดเร็ว
- **ไลบรารีใดจัดการการแปลง PST?** GroupDocs.Viewer for Java.  
- **ฉันสามารถแปลง PST เป็น PDF โดยตรงได้หรือไม่?** ใช่, โดยใช้ `PdfViewOptions`.  
- **ต้องการใบอนุญาตสำหรับการใช้งานในผลิตภัณฑ์หรือไม่?** จำเป็นต้องมีใบอนุญาต GroupDocs ที่ถูกต้อง.  
- **รองรับเวอร์ชัน Java ใด?** JDK 8 หรือสูงกว่า.  
- **ต้องดึงไฟล์แนบออกด้วยตนเองหรือไม่?** ไม่จำเป็น, viewer จะเรนเดอร์ไฟล์แนบโดยอัตโนมัติ.

## GroupDocs.Viewer for Java คืออะไร?
GroupDocs.Viewer for Java คือ API ฝั่งเซิร์ฟเวอร์ที่โหลดรูปแบบเอกสารและอีเมลกว่า 100 แบบและแสดงผลเป็น HTML, ภาพ หรือ PDF โดยไม่ต้องใช้ซอฟต์แวร์ภายนอก มันสามารถประมวลผลไฟล์ PST ขนาดสูงสุด 2 GB พร้อมการใช้หน่วยความจำต่ำกว่า 200 MB.

## วิธีแปลง pst เป็น html ด้วย GroupDocs.Viewer for Java?
โหลดไฟล์ PST ด้วย `new Viewer("source.pst")`, ตั้งค่า `HtmlViewOptions` ให้ชี้ไปยังโฟลเดอร์ผลลัพธ์, แล้วเรียก `viewer.view(htmlOptions)`. API จะดึงอีเมลแต่ละฉบับ, รักษาการจัดรูปแบบ, ไฟล์แนบ, และเมตาดาต้า, และเขียนหน้า HTML แยกสำหรับแต่ละข้อความ—ทั้งหมดในหนึ่งคำเรียกเมธอดเดียว.

### ทำไมต้องเลือก GroupDocs.Viewer?
- **การเรนเดอร์ความละเอียดสูง** – 99.9 % ของเนื้อหาอีเมล (รวมถึงข้อความแบบ rich‑text, ตาราง, และภาพฝัง) ถูกสร้างขึ้นอย่างแม่นยำ.  
- **หลายรูปแบบผลลัพธ์** – การเรียก API ครั้งเดียวสามารถสร้าง HTML, JPG, PNG หรือ PDF, ครอบคลุมตัวเลือกการส่งออกกว่า 50 รายการ.  
- **ไม่มีการพึ่งพาภายนอก** – ไม่ต้องใช้ Outlook, Exchange Server, หรือเครื่องแปลงของบุคคลที่สาม; ทุกอย่างทำงานภายใน runtime ของ Java ของคุณ.

## ข้อกำหนดเบื้องต้น
- **GroupDocs.Viewer for Java** – เวอร์ชัน 25.2 หรือใหม่กว่า.  
- **Java Development Kit (JDK)** – 8 หรือใหม่กว่า.  
- Maven สำหรับการจัดการ dependencies.  
- ความรู้พื้นฐานของ Java และความคุ้นเคยกับ Maven.

## การตั้งค่า GroupDocs.Viewer for Java
`Viewer` คือคลาสหลักใน GroupDocs.Viewer for Java ที่โหลดเอกสารและเรนเดอร์เป็นรูปแบบที่เลือก เพิ่มรีโพซิทอรีของ GroupDocs และ dependency ลงใน `pom.xml` ของคุณ:

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

### การรับใบอนุญาต
- **ทดลองใช้ฟรี** – สำรวจฟีเจอร์ทั้งหมดโดยไม่มีค่าใช้จ่าย.  
- **ใบอนุญาตชั่วคราว** – ขยายระยะเวลาการประเมินหากต้องการ.  
- **ใบอนุญาตเต็ม** – จำเป็นสำหรับการใช้งานในสภาพแวดล้อมการผลิต.

### การเริ่มต้นพื้นฐาน
อินสแตนซ์ของ `Viewer` มีน้ำหนักเบา; คุณสามารถใช้อินสแตนซ์เดียวกันหลายไฟล์เพื่อลดภาระการสร้างอ็อบเจกต์.

```java
import com.groupdocs.viewer.Viewer;
import com.groupdocs.viewer.options.HtmlViewOptions;

public class PSTToHTML {
    public static void main(String[] args) {
        // Initialize Viewer with a sample PST file path
        try (Viewer viewer = new Viewer("YOUR_DOCUMENT_DIRECTORY/SAMPLE_PST")) {
            HtmlViewOptions options = HtmlViewOptions.forEmbeddedResources("output_directory/PST_result.html");
            viewer.view(options);
        }
    }
}
```

## คู่มือการใช้งาน
ส่วนต่อไปนี้จะพาคุณผ่านขั้นตอนการเรนเดอร์ไฟล์ PST/OST ไปยังแต่ละรูปแบบที่รองรับ.

### การแสดงผลเอกสาร PST/OST เป็น HTML
#### ขั้นตอนที่ 1: ตั้งค่าไดเรกทอรีผลลัพธ์
กำหนดโฟลเดอร์ที่หน้าต่าง HTML จะถูกเขียนลงไป GroupDocs จะสร้างโฟลเดอร์ย่อยสำหรับแต่ละอีเมลเพื่อจัดระเบียบทรัพยากร.

```java
Path outputDirectory = Paths.get("YOUR_OUTPUT_DIRECTORY");
Path pageFilePathFormat = outputDirectory.resolve("PST_result.html");
```

#### ขั้นตอนที่ 2: กำหนดค่า Load Options
`LoadOptions` ให้คุณระบุการจัดการรหัสผ่าน, เวลาหมดของการโหลดทรัพยากร, และการเรนเดอร์หน้าแบบเลือกได้ การตั้งค่า timeout เป็น 30 วินาทีทำงานได้ดีในสภาพแวดล้อมเซิร์ฟเวอร์ส่วนใหญ่.

```java
LoadOptions loadOptions = new LoadOptions();
loadOptions.setResourceLoadingTimeout(100);
```

#### ขั้นตอนที่ 3: กำหนด HTML View Options
`HtmlViewOptions` ระบุโฟลเดอร์ผลลัพธ์, การจัดการทรัพยากร, และการตั้งค่า CSS ทางเลือกสำหรับการแปลงเป็น HTML.

```java
try (Viewer viewer = new Viewer("YOUR_DOCUMENT_DIRECTORY/SAMPLE_PST", loadOptions)) {
    HtmlViewOptions options = HtmlViewOptions.forEmbeddedResources(pageFilePathFormat);
    viewer.view(options);
}
```

#### ขั้นตอนที่ 4: เริ่มต้น Viewer และเรนเดอร์ HTML
สร้างอ็อบเจกต์ `Viewer`, ส่งพาธไฟล์ PST, และเรียก `view` พร้อมกับ `HtmlViewOptions`. API จะวนผ่านข้อความทั้งหมดใน PST และสร้างโครงสร้าง HTML ที่เป็นระเบียบโดยอัตโนมัติ.

```java
Path outputDirectory = Paths.get("YOUR_OUTPUT_DIRECTORY");
Path pageFilePathFormat = outputDirectory.resolve("PST_result_{0}.jpg");
```

### การแสดงผลเอกสาร PST/OST เป็น JPG
#### ขั้นตอนที่ 1: ตั้งค่าไดเรกทอรีผลลัพธ์
สร้างโฟลเดอร์เฉพาะสำหรับสแนปชอต JPG; แต่ละอีเมลจะกลายเป็นหนึ่งหรือหลายไฟล์ภาพขึ้นอยู่กับความยาวของข้อความ.

```java
LoadOptions loadOptions = new LoadOptions();
loadOptions.setResourceLoadingTimeout(100);
```

#### ขั้นตอนที่ 2: กำหนดค่า Load Options
`LoadOptions` เดียวกันที่ใช้สำหรับ HTML สามารถนำมาใช้ซ้ำที่นี่ เพื่อให้การจัดการรหัสผ่านสอดคล้องกันในทุกรูปแบบ.

```java
try (Viewer viewer = new Viewer("YOUR_DOCUMENT_DIRECTORY/SAMPLE_PST", loadOptions)) {
    JpgViewOptions options = new JpgViewOptions(pageFilePathFormat);
    viewer.view(options);
}
```

#### ขั้นตอนที่ 3: กำหนด JPG View Options
`JpgViewOptions` ควบคุมความละเอียดของภาพ, คุณภาพ, และโฟลเดอร์ผลลัพธ์สำหรับการแปลงเป็น JPEG.

```java
Path outputDirectory = Paths.get("YOUR_OUTPUT_DIRECTORY");
Path pageFilePathFormat = outputDirectory.resolve("PST_result_{0}.png");
```

#### ขั้นตอนที่ 4: เริ่มต้น Viewer และเรนเดอร์ JPG
ใช้ `viewer.view(jpgOptions)` เพื่อสร้างไฟล์ JPEG คุณภาพสูงพร้อมสำหรับการแสดงตัวอย่างบนเว็บ.

```java
LoadOptions loadOptions = new LoadOptions();
loadOptions.setResourceLoadingTimeout(100);
```

### การแสดงผลเอกสาร PST/OST เป็น PNG
#### ขั้นตอนที่ 1: ตั้งค่าไดเรกทอรีผลลัพธ์
ผลลัพธ์ PNG มีประโยชน์เมื่อคุณต้องการคุณภาพแบบ lossless สำหรับการเก็บถาวรหรือการประมวลผล OCR.

```java
try (Viewer viewer = new Viewer("YOUR_DOCUMENT_DIRECTORY/SAMPLE_PST", loadOptions)) {
    PngViewOptions options = new PngViewOptions(pageFilePathFormat);
    viewer.view(options);
}
```

#### ขั้นตอนที่ 2: กำหนดค่า Load Options
ไม่ต้องการการตั้งค่าเพิ่มเติมนอกจากการกำหนดรหัสผ่านและ timeout.

```java
Path outputDirectory = Paths.get("YOUR_OUTPUT_DIRECTORY");
Path pageFilePathFormat = outputDirectory.resolve("PST_result.pdf");
```

#### ขั้นตอนที่ 3: กำหนด PNG View Options
`PngViewOptions` ให้คุณตั้งค่าพื้นหลังโปร่งแสงและโฟลเดอร์ผลลัพธ์สำหรับภาพ PNG lossless.

```java
LoadOptions loadOptions = new LoadOptions();
loadOptions.setResourceLoadingTimeout(100);
```

#### ขั้นตอนที่ 4: เริ่มต้น Viewer และเรนเดอร์ PNG
สร้างอินสแตนซ์ `viewer.view(pngOptions)` เพื่อผลิตสแนปชอต PNG ของแต่ละอีเมล.

```java
try (Viewer viewer = new Viewer("YOUR_DOCUMENT_DIRECTORY/SAMPLE_PST", loadOptions)) {
    PdfViewOptions options = new PdfViewOptions(pageFilePathFormat);
    viewer.view(options);
}
```

### การแสดงผลเอกสาร PST/OST เป็น PDF
#### ขั้นตอนที่ 1: ตั้งค่าไดเรกทอรีผลลัพธ์
ไฟล์ PDF เดียวต่อ PST ทำให้กระบวนการตรวจสอบทางกฎหมายง่ายขึ้นและลดภาระการจัดเก็บ.

CODE_BLOCK_PLACEHOLDER_14_END

#### ขั้นตอนที่ 2: กำหนดค่า Load Options
เมื่อแปลงเป็น PDF, คุณอาจต้องการเปิดใช้งาน `setEmbedFonts(true)` เพื่อรับประกันความแม่นยำของภาพบนเครื่องใดก็ได้.

CODE_BLOCK_PLACEHOLDER_15_END

#### ขั้นตอนที่ 3: กำหนด PDF View Options
`PdfViewOptions` ให้คุณเลือกระดับการบีบอัด, ฝังฟอนต์, และตั้งชื่อไฟล์ผลลัพธ์สำหรับการแปลงเป็น PDF.

CODE_BLOCK_PLACEHOLDER_16_END

#### ขั้นตอนที่ 4: เริ่มต้น Viewer และเรนเดอร์ PDF
สร้าง `PdfViewOptions`, เลือกระดับการบีบอัดตามต้องการ, แล้วเรียก `viewer.view(pdfOptions)`. API จะรวมอีเมลทั้งหมดเป็นเอกสาร PDF ที่สามารถค้นหาได้หนึ่งไฟล์.

CODE_BLOCK_PLACEHOLDER_17_END

## การประยุกต์ใช้งานจริง
- **การเก็บถาวรอีเมล:** แปลงคลัง PST ขนาดใหญ่เป็น HTML หรือ PDF ที่สามารถค้นหาได้เพื่อการปฏิบัติตาม.  
- **ระบบจัดการเอกสาร:** เก็บไฟล์ที่แปลงแล้วในระบบที่รับเฉพาะ PDF, PNG หรือ JPG.  
- **แพลตฟอร์มการทำงานร่วมกัน:** แชร์อีเมลที่แปลงเป็นภาพใน Slack หรือ Teams.  
- **การตรวจสอบทางกฎหมาย:** ให้ศาลมีเวอร์ชัน PDF ของหลักฐานอีเมล.  
- **กลยุทธ์การสำรองข้อมูล:** เก็บสแนปชอต PNG หรือ JPG ที่มีน้ำหนักเบาของข้อความสำคัญ.

## พิจารณาด้านประสิทธิภาพ
- **การจัดการทรัพยากร:** ใช้อินสแตนซ์ `Viewer` ซ้ำเมื่อประมวลผลหลายไฟล์เพื่อลดภาระ.  
- **การปรับจูนหน่วยความจำ:** ปรับ `loadOptions.setResourceLoadingTimeout` ตามความจุของเซิร์ฟเวอร์.  
- **การประมวลผลแบบอะซิงโครนัส:** ย้ายการแปลงไปยังเธรดพื้นหลังเพื่อ UI ที่ตอบสนองเร็ว.

## คำถามที่พบบ่อย
**Q: ฉันจะ **convert pst to pdf** ด้วยฐานโค้ดเดียวกันได้อย่างไร?**  
A: ใช้ `PdfViewOptions` ตามที่แสดงในส่วนการเรนเดอร์ PDF; ส่วนอื่นของโค้ดยังคงเหมือนเดิม.

**Q: GroupDocs.Viewer สามารถจัดการไฟล์ PST ที่เข้ารหัสได้หรือไม่?**  
A: ได้, ให้ระบุรหัสผ่านผ่าน `LoadOptions.setPassword("yourPassword")` ก่อนการเรนเดอร์.

**Q: ความแตกต่างระหว่างการ **java convert pst** เป็น PNG กับ JPG คืออะไร?**  
A: PNG รักษาคุณภาพ lossless, เหมาะสำหรับสกรีนช็อต, ในขณะที่ JPG ให้ขนาดไฟล์เล็กลงสำหรับการแสดงตัวอย่างอีเมล.

**Q: มีวิธีการ **how to convert pst** ไฟล์เป็นจำนวนมากหรือไม่?**  
A: ใส่ตรรกะการเรนเดอร์ในลูปที่วนผ่านไดเรกทอรีของไฟล์ PST; ใช้การตั้งค่า `Viewer` เดียวกันสำหรับแต่ละไฟล์.

**Q: API รองรับการแปลงไฟล์ PST ที่ใหญ่กว่า 1 GB หรือไม่?**  
A: ได้, GroupDocs.Viewer สตรีมข้อมูลและสามารถประมวลผลไฟล์ได้ถึง 2 GB โดยไม่ต้องโหลดคลังทั้งหมดเข้าสู่หน่วยความจำ.

## สรุป
คุณมีคู่มือที่ครบถ้วนและพร้อมใช้งานในสภาพแวดล้อมการผลิตเพื่อ **convert pst to html**, JPG, PNG, และ PDF ด้วย GroupDocs.Viewer for Java แล้ว ด้วยการทำตามขั้นตอนข้างต้นคุณสามารถรวมการแปลงอีเมลเข้ากับกระบวนการทำงานใด ๆ ที่ใช้ Java, ปรับปรุงการเข้าถึง, และตอบสนองความต้องการด้านการปฏิบัติตาม.

---

**อัปเดตล่าสุด:** 2026-07-19  
**ทดสอบกับ:** GroupDocs.Viewer for Java 25.2  
**ผู้เขียน:** GroupDocs

## บทแนะนำที่เกี่ยวข้อง
- [แปลง NSF เป็น PDF, HTML, JPG, PNG ด้วย GroupDocs.Viewer for Java](/viewer/java/export-conversion/convert-nsf-files-groupdocs-viewer-java/)
- [convert odf html java – แปลง ODF เป็น HTML, JPG, PNG, PDF ด้วย GroupDocs.Viewer for Java](/viewer/java/export-conversion/convert-odf-documents-groupdocs-viewer-java/)
- [วิธีแปลง DOCX เป็น HTML ด้วย GroupDocs.Viewer for Java: คู่มือขั้นตอนโดยละเอียด](/viewer/java/export-conversion/convert-docx-to-html-groupdocs-viewer-java/)