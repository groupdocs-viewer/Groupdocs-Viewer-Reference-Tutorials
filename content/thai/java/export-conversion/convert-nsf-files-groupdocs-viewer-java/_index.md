---
date: '2026-05-26'
description: เรียนรู้วิธีแปลง nsf เป็น pdf และรูปแบบอื่น ๆ (HTML, JPG, PNG) ด้วย GroupDocs.Viewer
  for Java. คู่มือขั้นตอนโดยละเอียดพร้อมเคล็ดลับการปฏิบัติที่ดีที่สุด.
keywords:
- convert nsf to pdf
- how to convert nsf
- java convert lotus notes
schemas:
- author: GroupDocs
  dateModified: '2026-05-26'
  description: Learn how to convert nsf to pdf and other formats (HTML, JPG, PNG)
    using GroupDocs.Viewer for Java. Step‑by‑step guide with best‑practice tips.
  headline: convert nsf to pdf with GroupDocs.Viewer for Java
  type: TechArticle
- description: Learn how to convert nsf to pdf and other formats (HTML, JPG, PNG)
    using GroupDocs.Viewer for Java. Step‑by‑step guide with best‑practice tips.
  name: convert nsf to pdf with GroupDocs.Viewer for Java
  steps:
  - name: '**Web‑Based Document Sharing:** Convert NSF to HTML for instant in‑browser
      viewing without installing Notes.'
    text: '**Web‑Based Document Sharing:** Convert NSF to HTML for instant in‑browser
      viewing without installing Notes.'
  - name: '**Image Archiving:** Store page‑by‑page JPG/PNG snapshots for thumbnail
      galleries or OCR pipelines.'
    text: '**Image Archiving:** Store page‑by‑page JPG/PNG snapshots for thumbnail
      galleries or OCR pipelines.'
  - name: '**Universal Access:** Use PDF conversion to provide a single, secure file
      that can be opened on any device, meeting compliance requirements.'
    text: '**Universal Access:** Use PDF conversion to provide a single, secure file
      that can be opened on any device, meeting compliance requirements.'
  type: HowTo
- questions:
  - answer: '`PdfViewOptions` preserves most annotations automatically; just render
      the document with these options and the resulting PDF mirrors the original layout.'
    question: How do I convert an NSF file to PDF without losing annotations?
  - answer: Yes. Provide credentials through `LoadOptions` before creating the `Viewer`
      instance.
    question: Can I convert password‑protected NSF files?
  - answer: JDK 11 or newer offers improved garbage collection and concurrency, which
      speeds up batch conversions.
    question: What Java version gives the best performance?
  - answer: Configure `JpgViewOptions.setResolution(int dpi)` or `PngViewOptions.setResolution(int
      dpi)` before calling `viewer.view(options)`.
    question: Is it possible to set a custom DPI for JPG/PNG output?
  - answer: Yes. Use the `Stream` overload of the view options to write the result
      straight to `HttpServletResponse.getOutputStream()`.
    question: Does GroupDocs.Viewer support streaming the output directly to an HTTP
      response?
  type: FAQPage
title: แปลง nsf เป็น pdf ด้วย GroupDocs.Viewer for Java
type: docs
url: /th/java/export-conversion/convert-nsf-files-groupdocs-viewer-java/
weight: 1
---

# แปลงไฟล์ NSF เป็นหลายรูปแบบโดยใช้ GroupDocs.Viewer สำหรับ Java

ในคู่มือฉบับครอบคลุมนี้ คุณจะได้เรียนรู้ **วิธีแปลง nsf เป็น pdf** และยังสามารถแสดงไฟล์ NSF เป็น HTML, JPG, และ PNG ด้วย GroupDocs.Viewer สำหรับ Java ไม่ว่าคุณจะต้องการเก็บถาวรฐานข้อมูล Lotus Notes, แสดงในเบราว์เซอร์, หรือสร้างภาพตัวอย่าง คู่มือนี้จะพาคุณผ่านทุกขั้นตอน—from การตั้งค่าสภาพแวดล้อมจนถึงรายละเอียดระดับโค้ด—เพื่อให้คุณสามารถทำการแปลงได้ในไม่กี่นาที.

![แปลงไฟล์ NSF เป็น HTML, JPG, PNG, และ PDF ด้วย GroupDocs.Viewer สำหรับ Java](/viewer/export-conversion/convert-nsf-files-to-html-jpg-png-pdf-java.png)
[แปลงไฟล์ NSF เป็น HTML, JPG, PNG, และ PDF ด้วย GroupDocs.Viewer สำหรับ Java](/viewer/export-conversion/convert-nsf-files-to-html-jpg-png-pdf-java.png)

## คำตอบด่วน
- **กรณีการใช้งานหลักคืออะไร?** การแสดงไฟล์ NSF เป็น PDF, HTML, JPG หรือ PNG สำหรับเว็บ, การเก็บถาวร, หรือการแชร์.  
- **ไลบรารีใดที่จัดการการแปลง?** GroupDocs.Viewer for Java.  
- **ฉันต้องการไลเซนส์หรือไม่?** มีการทดลองใช้ฟรี; จำเป็นต้องมีไลเซนส์เต็มสำหรับการใช้งานในผลิตภัณฑ์.  
- **ต้องการเวอร์ชัน Java ใด?** JDK 8 หรือใหม่กว่า.  
- **ฉันสามารถประมวลผลหลายไฟล์ NSF เป็นชุดได้หรือไม่?** ได้ – ห่อหุ้มตรรกะการแสดงผลในลูปและจัดการทรัพยากรด้วย try‑with‑resources.

## อะไรคือ “convert nsf to pdf”?

การแปลงไฟล์ NSF (ฐานข้อมูล Lotus Notes) เป็น PDF จะสร้างเอกสารแบบคงที่ที่อ่านได้ทั่วโลก ซึ่งรักษาการจัดวาง, ฟอนต์, และกราฟิกเดิมโดยไม่ต้องใช้คลไคลเอนต์ Notes รูปแบบนี้เหมาะสำหรับการเก็บถาวรทางกฎหมาย, การแจกจ่ายที่ปลอดภัย, และการจัดเก็บระยะยาว เนื่องจากไฟล์ PDF สามารถเปิดได้บนระบบปฏิบัติการหรืออุปกรณ์ใดก็ได้.

## ทำไมต้องแปลง NSF เป็น PDF และรูปแบบอื่นๆ?

การแปลงไฟล์ NSF เป็น PDF, HTML, JPG หรือ PNG เปิดโอกาสการเข้าถึงแบบสากล, รักษาความเที่ยงตรงของภาพ, และทำให้สามารถรวมเข้ากับแอปพลิเคชันเว็บและมือถือสมัยใหม่ได้อย่างราบรื่น PDF รักษาการจัดหน้าอย่างแม่นยำ, HTML ให้การดูในเบราว์เซอร์ทันที, และ JPG/PNG ให้ภาพความละเอียดสูงสำหรับภาพย่อหรือการฝัง.

## ข้อกำหนดเบื้องต้น
- **Java Development Kit (JDK) 8+** – แนะนำให้ใช้ JDK 11 หรือใหม่กว่าเพื่อประสิทธิภาพการเก็บกวาดหน่วยความจำที่ดีกว่า.  
- **Maven** – สำหรับการจัดการ dependencies.  
- **GroupDocs.Viewer for Java** – เวอร์ชันทดลองหรือมีไลเซนส์.  
- ความคุ้นเคยพื้นฐานกับ Java file I/O และโครงสร้างโครงการ Maven.

## การตั้งค่า GroupDocs.Viewer สำหรับ Java

### การกำหนดค่า Maven

เพิ่ม dependency ของ GroupDocs.Viewer ลงใน `pom.xml` ของคุณ ซึ่งจะดึงไบนารีและไลบรารีที่จำเป็นทั้งหมดรวมถึงไลบรารีที่เป็น transitive.

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

To unlock full functionality you can:
- **Free Trial:** ประเมินคุณลักษณะหลักโดยไม่ต้องใช้คีย์ไลเซนส์.
- **Temporary License:** ขอคีย์ที่มีระยะเวลาจำกัดสำหรับการทดสอบ.
- **Full Purchase:** ซื้อไลเซนส์สำหรับการใช้งานในผลิตภัณฑ์โดยไม่มีข้อจำกัด.

### การเริ่มต้นพื้นฐาน

`Viewer` คือคลาสหลักที่ทำการแสดงเอกสารเป็นรูปแบบผลลัพธ์ที่ต้องการ เริ่มต้นด้วยไลเซนส์และเส้นทางไฟล์ของคุณภายในบล็อก try‑with‑resources เพื่อให้แน่ใจว่ามีการปล่อยทรัพยากรอย่างเหมาะสม.

```java
import com.groupdocs.viewer.Viewer;

public class InitializeViewer {
    public static void main(String[] args) {
        try (Viewer viewer = new Viewer("YOUR_DOCUMENT_DIRECTORY/SAMPLE_NSF")) {
            // Viewer is ready for use.
        }
    }
}
```

## วิธีแปลง NSF เป็น PDF

เพื่อแปลงเอกสาร NSF เป็น PDF ก่อนอื่นให้สร้างอินสแตนซ์ `Viewer` ที่ชี้ไปยังไฟล์ต้นทาง จากนั้นกำหนดค่า `PdfViewOptions` เพื่อระบุลักษณะของผลลัพธ์ เช่น ขนาดหน้า, ระดับการบีบอัด, และการฝังฟอนต์ สุดท้ายเรียก `viewer.view(pdfOptions)` ซึ่งจะทำการแสดงเอกสารทั้งหมดเป็นไฟล์ PDF ไฟล์เดียวพร้อมสำหรับการแจกจ่าย.

`PdfViewOptions` ระบุการตั้งค่าที่เฉพาะสำหรับ PDF เช่น ขนาดหน้าและการบีบอัด.

```java
Path pageFilePathFormat = outputDirectory.resolve("NSF_result.pdf");
```
```java
import com.groupdocs.viewer.options.PdfViewOptions;

try (Viewer viewer = new Viewer("YOUR_DOCUMENT_DIRECTORY/SAMPLE_NSF", loadOptions)) {
    PdfViewOptions options = new PdfViewOptions(pageFilePathFormat);
    viewer.view(options);  // Convert to PDF.
}
```

## การแสดงผล NSF เป็น HTML

### ภาพรวม

แปลงเอกสาร NSF เป็นหน้า HTML ที่เป็นอิสระโดยฝังรูปภาพและ CSS เพื่อให้การแสดงผลบนหน้าจอแม่นยำ.

### คู่มือขั้นตอนต่อขั้นตอน

#### 1. ตั้งค่าไดเรกทอรีและเส้นทางไฟล์สำหรับผลลัพธ์

กำหนดโฟลเดอร์ที่ไฟล์ HTML จะถูกบันทึก.

```java
import java.nio.file.Path;
import java.nio.file.Paths;

Path outputDirectory = Paths.get("YOUR_OUTPUT_DIRECTORY");
Path pageFilePathFormat = outputDirectory.resolve("NSF_result.html");
```

#### 2. กำหนดค่า Load Options

`LoadOptions` ให้คุณปรับแต่งการโหลดทรัพยากรอย่างละเอียด เช่น การตั้งค่า timeout สำหรับแอสเซ็ตภายนอก.

```java
import com.groupdocs.viewer.options.LoadOptions;

LoadOptions loadOptions = new LoadOptions();
loadOptions.setResourceLoadingTimeout(100);  // Set timeout for loading resources.
```

#### 3. เริ่มต้น Viewer และทำการแสดงผล

`Viewer` ประมวลผล NSF และเขียนไฟล์ HTML ไปยังไดเรกทอรีเป้าหมาย.

```java
import com.groupdocs.viewer.Viewer;
import com.groupdocs.viewer.options.HtmlViewOptions;

try (Viewer viewer = new Viewer("YOUR_DOCUMENT_DIRECTORY/SAMPLE_NSF", loadOptions)) {
    HtmlViewOptions options = HtmlViewOptions.forEmbeddedResources(pageFilePathFormat);
    viewer.view(options);  // Render the document to HTML.
}
```

## การแสดงผล NSF เป็น JPG

### ภาพรวม

สร้างภาพ JPG คุณภาพสูงจากแต่ละหน้าของเอกสาร NSF ซึ่งมีประโยชน์สำหรับการแสดงตัวอย่างหรือการฝังในกระบวนการทำงานที่เน้นภาพ.

#### 1. กำหนดเส้นทางผลลัพธ์

ระบุรูปแบบการตั้งชื่อเช่น `output_page_{0}.jpg` โดยที่ `{0}` คือหมายเลขหน้า.

```java
Path pageFilePathFormat = outputDirectory.resolve("NSF_result_{0}.jpg");
```

#### 2. กำหนดค่าและทำการแสดงผล

`JpgViewOptions` กำหนดการตั้งค่าสำหรับการส่งออกภาพ JPEG รวมถึงความละเอียดและคุณภาพ สร้าง `JpgViewOptions`, ตั้งค่า DPI ที่ต้องการ, และเรียก `viewer.view(options)`.

```java
import com.groupdocs.viewer.options.JpgViewOptions;

try (Viewer viewer = new Viewer("YOUR_DOCUMENT_DIRECTORY/SAMPLE_NSF", loadOptions)) {
    JpgViewOptions options = new JpgViewOptions(pageFilePathFormat);
    viewer.view(options);  // Render to JPG.
}
```

## การแสดงผล NSF เป็น PNG

### ภาพรวม

สร้างภาพ PNG แบบไม่สูญเสียข้อมูลที่คงรายละเอียดทั้งหมดของหน้าต้นฉบับ NSF.

#### 1. ตั้งค่าเส้นทางผลลัพธ์

ใช้เทมเพลตเช่น `nsf_page_{0}.png` สำหรับการแบ่งหน้าอัตโนมัติ.

```java
Path pageFilePathFormat = outputDirectory.resolve("NSF_result_{0}.png");
```

#### 2. แสดงผลเอกสาร

`PngViewOptions` กำหนดพารามิเตอร์การส่งออก PNG เช่น ความละเอียดและความลึกของสี ตั้งค่า `PngViewOptions` (เช่น `setResolution(300)`) แล้วทำการแสดงผล.

```java
import com.groupdocs.viewer.options.PngViewOptions;

try (Viewer viewer = new Viewer("YOUR_DOCUMENT_DIRECTORY/SAMPLE_NSF", loadOptions)) {
    PngViewOptions options = new PngViewOptions(pageFilePathFormat);
    viewer.view(options);  // Convert to PNG.
}
```

## การประยุกต์ใช้งานจริง
- **Web‑Based Document Sharing:** แปลง NSF เป็น HTML เพื่อการดูในเบราว์เซอร์ทันทีโดยไม่ต้องติดตั้ง Notes.  
- **Image Archiving:** เก็บภาพสแนปช็อต JPG/PNG หน้า‑ต่อ‑หน้า สำหรับแกลเลอรีภาพย่อหรือกระบวนการ OCR.  
- **Universal Access:** ใช้การแปลงเป็น PDF เพื่อให้ได้ไฟล์เดียวที่ปลอดภัยซึ่งสามารถเปิดได้บนอุปกรณ์ใดก็ได้ ตรงตามข้อกำหนดการปฏิบัติตาม.

## ข้อควรพิจารณาด้านประสิทธิภาพ
- **Resource Loading:** ปรับ `setResourceLoadingTimeout` ตามความหน่วงของเครือข่ายเพื่อหลีกเลี่ยงการค้าง.  
- **Memory Management:** ใช้ try‑with‑resources สำหรับอินสแตนซ์ `Viewer`; จะปล่อยทรัพยากรเนทีฟโดยอัตโนมัติ.  
- **Batch Processing:** สำหรับชุดใหญ่ ให้ประมวลผลไฟล์แบบต่อเนื่องหรือใน parallel streams, ตรวจสอบการใช้ heap เพื่อให้อยู่ต่ำกว่าขีดจำกัดหน่วยความจำของ JVM.

## ส่วนคำถามที่พบบ่อย
**รูปแบบที่ดีที่สุดสำหรับการแปลงเอกสาร NSF คืออะไร?**  
- ขึ้นอยู่กับการใช้งานต่อไป: HTML สำหรับพอร์ทัลเว็บ, PDF สำหรับการแจกจ่ายทั่วโลก, JPG/PNG สำหรับกระบวนการทำงานที่ใช้ภาพ.

**ฉันจะจัดการไฟล์ NSF ขนาดใหญ่อย่างมีประสิทธิภาพได้อย่างไร?**  
- ปรับ `LoadOptions` (เช่น เพิ่ม `setResourceLoadingTimeout`), ประมวลผลไฟล์เป็นชุดเล็กลง, และใช้ `Viewer` อินสแตนซ์เดียวซ้ำเมื่อเป็นไปได้.

**ฉันสามารถปรับคุณภาพผลลัพธ์ในรูปแบบภาพได้หรือไม่?**  
- ได้. ตั้งค่า DPI, ระดับการบีบอัด, และความลึกของสีผ่าน `JpgViewOptions` หรือ `PngViewOptions` ก่อนการแสดงผล.

**ควรทำอย่างไรหากการแปลงล้มเหลว?**  
- ตรวจสอบเส้นทางไฟล์, ยืนยันว่าไฟล์ NSF ไม่เสียหาย, และตรวจสอบบันทึกของ GroupDocs.Viewer เพื่อดูรหัสข้อผิดพลาดโดยละเอียด. การอัปเดตเป็นเวอร์ชันไลบรารีล่าสุดมักจะแก้ไขปัญหาความเข้ากันได้.

**การแปลงเป็นชุดได้รับการสนับสนุนหรือไม่?**  
- แน่นอน. ห่อหุ้มตรรกะการแสดงผลภายในลูป `for` หรือ Java Stream เพื่อประมวลผลหลายไฟล์ NSF อัตโนมัติ.

## คำถามที่พบบ่อย
**Q: ฉันจะทำการแปลงไฟล์ NSF เป็น PDF โดยไม่สูญเสียคำอธิบายประกอบได้อย่างไร?**  
`PdfViewOptions` จะรักษาคำอธิบายประกอบส่วนใหญ่โดยอัตโนมัติ; เพียงแค่แสดงเอกสารด้วยตัวเลือกเหล่านี้และ PDF ที่ได้จะสะท้อนการจัดวางต้นฉบับ.

**Q: ฉันสามารถแปลงไฟล์ NSF ที่มีการป้องกันด้วยรหัสผ่านได้หรือไม่?**  
ได้. ให้ข้อมูลประจำตัวผ่าน `LoadOptions` ก่อนสร้างอินสแตนซ์ `Viewer`.

**Q: เวอร์ชัน Java ใดให้ประสิทธิภาพดีที่สุด?**  
JDK 11 หรือใหม่กว่าให้การเก็บกวาดหน่วยความจำและการทำงานพร้อมกันที่ดีขึ้น ซึ่งทำให้การแปลงเป็นชุดเร็วขึ้น.

**Q: สามารถตั้งค่า DPI ที่กำหนดเองสำหรับการส่งออก JPG/PNG ได้หรือไม่?**  
กำหนดค่า `JpgViewOptions.setResolution(int dpi)` หรือ `PngViewOptions.setResolution(int dpi)` ก่อนเรียก `viewer.view(options)`.

**Q: GroupDocs.Viewer รองรับการสตรีมผลลัพธ์โดยตรงไปยัง HTTP response หรือไม่?**  
ได้. ใช้ overload `Stream` ของ view options เพื่อเขียนผลลัพธ์โดยตรงไปยัง `HttpServletResponse.getOutputStream()`.

## สรุป

คุณมีแผนที่เต็มรูปแบบสำหรับ **convert nsf to pdf** และการแสดงไฟล์ NSF เป็น HTML, JPG, และ PNG ด้วย GroupDocs.Viewer สำหรับ Java แล้ว ด้วยการทำตามขั้นตอนข้างต้น คุณสามารถรวมการแปลงเอกสารที่แข็งแกร่งเข้าไปในแอปพลิเคชัน Java ใดก็ได้, ทำงานอัตโนมัติเป็นชุด, และส่งมอบเนื้อหาในรูปแบบที่เหมาะกับความต้องการของผู้ใช้ของคุณ. สำรวจคุณสมบัติเพิ่มเติมของ Viewer เช่น การใส่ลายน้ำ, ฟอนต์ที่กำหนดเอง, และการจัดการหลายหน้า เพื่อเสริมโซลูชันของคุณให้ดียิ่งขึ้น.

---

**อัปเดตล่าสุด:** 2026-05-26  
**ทดสอบด้วย:** GroupDocs.Viewer 25.2  
**ผู้เขียน:** GroupDocs

## บทแนะนำที่เกี่ยวข้อง

- [groupdocs viewer java: แปลงเอกสารเป็น PDF – คู่มือเต็ม](/viewer/java/export-conversion/convert-documents-pdf-groupdocs-viewer-java/)
- [convert odf html java – แปลง ODF เป็น HTML, JPG, PNG, PDF ด้วย GroupDocs.Viewer สำหรับ Java](/viewer/java/export-conversion/convert-odf-documents-groupdocs-viewer-java/)
- [แปลง PST เป็น HTML, JPG, PNG, PDF ด้วย GroupDocs.Viewer สำหรับ Java](/viewer/java/export-conversion/convert-pst-ost-groupdocs-viewer-java/)