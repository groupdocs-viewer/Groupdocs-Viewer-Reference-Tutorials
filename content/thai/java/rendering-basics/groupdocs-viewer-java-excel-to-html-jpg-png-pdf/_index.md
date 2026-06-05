---
date: '2026-06-05'
description: เรียนรู้วิธีแปลง Excel เป็น HTML, JPG, PNG และ PDF ด้วย GroupDocs.Viewer
  Java คู่มือแบบขั้นตอนครอบคลุมการตั้งค่า ตัวเลือกการเรนเดอร์ และกรณีการใช้งานจริง
keywords:
- convert excel to html
- excel to pdf java
- convert spreadsheet to image
- groupdocs viewer java
- excel to html java
schemas:
- author: GroupDocs
  dateModified: '2026-06-05'
  description: Learn how to convert Excel to HTML, JPG, PNG, and PDF using GroupDocs.Viewer
    Java. This step‑by‑step guide covers setup, rendering options, and real‑world
    use cases.
  headline: How to Convert Excel to HTML, JPG, PNG, and PDF Using GroupDocs.Viewer
    Java
  type: TechArticle
- description: Learn how to convert Excel to HTML, JPG, PNG, and PDF using GroupDocs.Viewer
    Java. This step‑by‑step guide covers setup, rendering options, and real‑world
    use cases.
  name: How to Convert Excel to HTML, JPG, PNG, and PDF Using GroupDocs.Viewer Java
  steps:
  - name: '**Free Trial:** Download the trial version from [GroupDocs Free Trial](https://releases.groupdocs.com/viewer/java/).'
    text: '**Free Trial:** Download the trial version from [GroupDocs Free Trial](https://releases.groupdocs.com/viewer/java/).'
  - name: '**Temporary License:** Acquire a temporary license for extended testing
      from [GroupDocs Temporary License](https://purchase.groupdocs.com/temporary-license/).'
    text: '**Temporary License:** Acquire a temporary license for extended testing
      from [GroupDocs Temporary License](https://purchase.groupdocs.com/temporary-license/).'
  - name: '**Purchase:** Obtain a full license for production use at [GroupDocs Purchase](https://purchase.groupdocs.com/buy).'
    text: '**Purchase:** Obtain a full license for production use at [GroupDocs Purchase](https://purchase.groupdocs.com/buy).'
  - name: '**Business Reporting:** Generate HTML dashboards or PDF reports from financial
      models without manual copy‑pasting.'
    text: '**Business Reporting:** Generate HTML dashboards or PDF reports from financial
      models without manual copy‑pasting.'
  - name: '**Data Visualization:** Embed JPG/PNG snapshots of spreadsheets in slide
      decks, ensuring headers give viewers immediate context.'
    text: '**Data Visualization:** Embed JPG/PNG snapshots of spreadsheets in slide
      decks, ensuring headers give viewers immediate context.'
  - name: '**Document Archiving:** Store Excel workbooks as PDFs for compliance, while
      retaining the original layout and headings.'
    text: '**Document Archiving:** Store Excel workbooks as PDFs for compliance, while
      retaining the original layout and headings.'
  - name: '**Web Portals:** Serve HTML versions of spreadsheets directly in browsers,
      enabling interactive filtering with JavaScript.'
    text: '**Web Portals:** Serve HTML versions of spreadsheets directly in browsers,
      enabling interactive filtering with JavaScript.'
  type: HowTo
- questions:
  - answer: Yes. Pass the password to the `Viewer` constructor, and the library will
      decrypt the workbook before rendering.
    question: Can I convert password‑protected Excel files?
  - answer: Absolutely. The viewer treats macros as data; they are ignored during
      rendering, ensuring a safe conversion.
    question: Does GroupDocs.Viewer support macro‑enabled workbooks (.xlsm)?
  - answer: The library can process files up to **2 GB** without loading the entire
      document into memory, thanks to its streaming architecture.
    question: What is the maximum file size supported?
  - answer: Yes. Use `ViewOptions.setPageNumber(pageIndex)` to target a single sheet
      when generating HTML, JPG, PNG, or PDF.
    question: Is it possible to render only a specific worksheet?
  - answer: Set `JpgViewOptions.setQuality(90)` (value 0‑100) to balance file size
      and visual fidelity.
    question: How do I control image quality for JPG output?
  type: FAQPage
title: วิธีแปลง Excel เป็น HTML, JPG, PNG และ PDF ด้วย GroupDocs.Viewer Java
type: docs
url: /th/java/rendering-basics/groupdocs-viewer-java-excel-to-html-jpg-png-pdf/
weight: 1
---

# วิธีแปลง Excel เป็น HTML, JPG, PNG, และ PDF ด้วย GroupDocs.Viewer Java

การแปลง Excel เป็น HTML เป็นความต้องการทั่วไปเมื่อคุณต้องการแสดงข้อมูลสเปรดชีตบนเว็บพร้อมคงไว้ซึ่งหัวแถวและหัวคอลัมน์ ในบทแนะนำนี้คุณจะได้เรียนรู้ว่า GroupDocs.Viewer สำหรับ Java ทำให้ **convert excel to html** ง่ายขึ้นอย่างไร รวมถึงวิธีการแสดงผลเวิร์กบุ๊กเดียวกันเป็นรูปแบบ JPG, PNG, และ PDF เราจะเดินผ่านข้อกำหนดเบื้องต้น การตั้งค่าห้องสมุด และแต่ละสถานการณ์การเรนเดอร์ด้วยโค้ดตัวอย่างที่ชัดเจนและพร้อมใช้งานในระดับผลิต

## คำตอบด่วน
- **Can GroupDocs.Viewer render Excel to multiple formats?** ใช่ – HTML, JPG, PNG, และ PDF รองรับโดยตรง  
- **Do I need a license for development?** การทดลองใช้ฟรีทำงานได้สำหรับการทดสอบ; จำเป็นต้องมีใบอนุญาตถาวรสำหรับการใช้งานจริง  
- **Will row and column headings be kept?** ตั้งค่า `setRenderHeadings(true)` ใน view options เพื่อรวมไว้  
- **Which Java version is required?** ต้องการ Java 8 หรือสูงกว่า; ไลบรารีเข้ากันได้กับ Java 11, 17, และรุ่นต่อไป  
- **Is the conversion fast for large workbooks?** GroupDocs.Viewer สามารถประมวลผลสเปรดชีต 200 หน้าในเวลาน้อยกว่าสักวินาทีบนฮาร์ดแวร์เซิร์ฟเวอร์ทั่วไป  

## “convert excel to html” คืออะไร?
**Convert excel to html** หมายถึงการแปลงเวิร์กบุ๊ก Excel ให้เป็นเอกสาร HTML ที่พร้อมใช้งานบนเว็บโดยคงไว้ซึ่งรูปแบบเดิม, สูตร, และส่วนหัว ซึ่งทำให้สามารถฝังสเปรดชีตลงในหน้าเว็บหรือพอร์ทัลได้อย่างราบรื่นโดยไม่ต้องให้ผู้ใช้ปลายทางติดตั้ง Excel  

## ทำไมต้องใช้ GroupDocs.Viewer Java สำหรับการเรนเดอร์ Excel?
GroupDocs.Viewer Java รองรับ **รูปแบบอินพุตและเอาต์พุตกว่า 50 ประเภท**, รวมถึง DOCX, XLSX, PPTX, HTML, JPG, PNG, และ PDF มันประมวลผลเวิร์กบุ๊กหลายร้อยหน้าโดยไม่ต้องโหลดไฟล์ทั้งหมดเข้าสู่หน่วยความจำ, ให้ความเร็วการแปลงสูงสุดถึง **10 × เร็วกว่า** ทางเลือกโอเพ่นซอร์สหลายตัว ไลบรารียังให้การควบคุมละเอียดต่อการตั้งค่าการเรนเดอร์ เช่น การมองเห็นหัวส่วน, ขนาดหน้า, และคุณภาพภาพ  

## ข้อกำหนดเบื้องต้น
- **Java Development Kit (JDK) 8+** ติดตั้งและกำหนดค่าใน IDE ของคุณ (IntelliJ IDEA, Eclipse, ฯลฯ).  
- **Maven** สำหรับการจัดการ dependencies.  
- ความคุ้นเคยพื้นฐานกับไวยากรณ์ Java และ `pom.xml` ของ Maven.  
- ใบอนุญาต **GroupDocs.Viewer Java** ที่ใช้งานได้ (ทดลองหรือถาวร).  

### ไลบรารีและ dependencies ที่จำเป็น
เพิ่ม dependency ของ GroupDocs.Viewer Java ลงใน `pom.xml` ของคุณ:

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

### การตั้งค่าสภาพแวดล้อม
- ตรวจสอบว่า `java -version` แสดงผลเป็น 1.8 หรือใหม่กว่า.  
- เปิด IDE ที่คุณชื่นชอบและสร้างโปรเจค Maven.  

มาเริ่มต้นด้วยข้อกำหนดเบื้องต้นที่จำเป็นก่อนที่เราจะลงลึกไปยังการทำงาน  

![แปลงไฟล์ Excel เป็น HTML, JPG, PNG, และ PDF ด้วย GroupDocs.Viewer สำหรับ Java](/viewer/rendering-basics/convert-excel-files-into-html-jpg-png-and-pdf.png)

## การตั้งค่า GroupDocs.Viewer Java

### ข้อมูลการติดตั้ง
รวม dependency ของ Maven ที่แสดงด้านบนใน `pom.xml` ของโปรเจคของคุณ หลังจากรัน `mvn clean install` ไลบรารีจะพร้อมใช้งานใน classpath ของคุณ  

### ขั้นตอนการรับใบอนุญาต
1. **Free Trial:** ดาวน์โหลดเวอร์ชันทดลองจาก [GroupDocs Free Trial](https://releases.groupdocs.com/viewer/java/).  
2. **Temporary License:** รับใบอนุญาตชั่วคราวสำหรับการทดสอบต่อเนื่องจาก [GroupDocs Temporary License](https://purchase.groupdocs.com/temporary-license/).  
3. **Purchase:** รับใบอนุญาตเต็มสำหรับการใช้งานในผลิตภัณฑ์ที่ [GroupDocs Purchase](https://purchase.groupdocs.com/buy).  

### การเริ่มต้นพื้นฐาน
คลาส `Viewer` เป็นจุดเริ่มต้นสำหรับการดำเนินการเรนเดอร์ทั้งหมด การเริ่มต้นใช้งานนั้นง่ายดาย:

```java
import com.groupdocs.viewer.Viewer;

public class ViewerSetup {
    public static void main(String[] args) {
        try (Viewer viewer = new Viewer("Sample.xlsx")) {
            // Your code here to use the viewer
        }
    }
}
```

นี่จะสร้างอินสแตนซ์ `Viewer` ที่ผูกกับไฟล์ใบอนุญาตในเครื่อง พร้อมประมวลผลไฟล์ Excel  

## คู่มือการใช้งาน
ด้านล่างเราจะครอบคลุมเป้าหมายการเรนเดอร์แต่ละประเภท สำหรับแต่ละรูปแบบเราจะ **นำเข้าคลาสที่จำเป็น**, จากนั้น **กำหนดไดเรกทอรีผลลัพธ์**, และสุดท้าย **กำหนดค่าตัวเลือกการดู** ด้วย `setRenderHeadings(true)` เพื่อคงหัวแถว/คอลัมน์  

### เรนเดอร์สเปรดชีตเป็น HTML
**ฉันจะแปลงเวิร์กบุ๊ก Excel เป็น HTML ด้วย GroupDocs.Viewer Java อย่างไร?**  

เพื่อแปลงเวิร์กบุ๊ก Excel เป็น HTML ให้โหลดไฟล์ด้วย Viewer, สร้างอินสแตนซ์ HtmlViewOptions, เปิดใช้งานการเรนเดอร์หัวส่วน, และเรียกเมธอด view กระบวนการจะเขียนแต่ละชีตเป็นไฟล์ HTML แยกกัน โดยคงรูปแบบเซลล์, สูตร, และโครงสร้างเดิมเพื่อการแสดงผลบนเว็บที่แม่นยำ  

#### การดำเนินการตามขั้นตอน
**1. นำเข้าห้องสมุดที่จำเป็น**  
HtmlViewOptions กำหนดวิธีการเรนเดอร์เวิร์กบุ๊กเป็น HTML, อนุญาตให้ปรับแต่งหัวส่วน, สไตล์, และการจัดหน้า.  

```java
import com.groupdocs.viewer.Viewer;
import com.groupdocs.viewer.options.HtmlViewOptions;
```

**2. กำหนดไดเรกทอรีผลลัพธ์**  
ระบุโฟลเดอร์ที่หน้าต่าง HTML ที่สร้างขึ้นจะถูกเขียนลงไป.  

```java
Path outputDirectory = Paths.get("YOUR_DOCUMENT_DIRECTORY", "RenderRowAndColumnHeadings");
Path pageFilePathFormat = outputDirectory.resolve("page_{0}.html");
```

**3. เริ่มต้น Viewer และกำหนดค่าตัวเลือก**  
สร้างอินสแตนซ์ `Viewer`, ตั้งค่า `setRenderHeadings(true)`, และเรียก `view`.  

```java
try (Viewer viewer = new Viewer(Paths.get("Sample.xlsx"))) {
    HtmlViewOptions options = HtmlViewOptions.forEmbeddedResources(pageFilePathFormat);
    
    // Enable rendering of row and column headings in the spreadsheet.
    options.getSpreadsheetOptions().setRenderHeadings(true);

    viewer.view(options, 1, 2, 3); // Render pages 1 to 3.
}
```

คำอธิบาย: `HtmlViewOptions` ควบคุมผลลัพธ์ HTML การเปิดใช้งาน `setRenderHeadings(true)` ทำให้แน่ใจว่าแถวและคอลัมน์แรก (โดยปกติเป็นหัวส่วน) ปรากฏใน HTML ที่ได้ ทำให้ข้อมูลเข้าใจได้ทันที  

### เรนเดอร์สเปรดชีตเป็น JPG
**ฉันจะเรนเดอร์ชีต Excel เป็นภาพ JPG พร้อมหัวส่วนได้อย่างไร?**  

การเรนเดอร์ชีต Excel เป็น JPG เกี่ยวข้องกับการเริ่มต้น Viewer ด้วยเวิร์กบุ๊ก, สร้างอ็อบเจกต์ JpgViewOptions, ตั้งค่า renderHeadings เป็น true, และเรียก view ไลบรารีจะแปลงแต่ละหน้าที่ DPI ที่กำหนดเป็นภาพ raster ทำให้ได้ไฟล์ JPG ความละเอียดสูงที่คงโครงสร้างภาพของสเปรดชีตและหัวส่วน  

#### การดำเนินการตามขั้นตอน
**1. นำเข้าห้องสมุดที่จำเป็น**  
JpgViewOptions กำหนดการตั้งค่าสำหรับการเรนเดอร์ชีตเป็นภาพ JPG รวมถึง DPI, คุณภาพ, และการมองเห็นหัวส่วน.  

```java
import com.groupdocs.viewer.Viewer;
import com.groupdocs.viewer.options.JpgViewOptions;
```

**2. กำหนดไดเรกทอรีผลลัพธ์**  
กำหนดตำแหน่งที่ไฟล์ JPG จะถูกจัดเก็บ.  

```java
Path outputDirectory = Paths.get("YOUR_DOCUMENT_DIRECTORY", "RenderRowAndColumnHeadings");
Path pageFilePathFormat = outputDirectory.resolve("page_{0}.jpg");
```

**3. เริ่มต้น Viewer และกำหนดค่าตัวเลือก**  
สร้าง viewer, ตั้งค่าการเรนเดอร์หัวส่วน, และดำเนินการแปลง.  

```java
try (Viewer viewer = new Viewer(Paths.get("Sample.xlsx"))) {
    JpgViewOptions options = new JpgViewOptions(pageFilePathFormat);
    
    // Enable rendering of row and column headings in the spreadsheet.
    options.getSpreadsheetOptions().setRenderHeadings(true);

    viewer.view(options, 1, 2, 3); // Render pages 1 to 3.
}
```

คำอธิบาย: `JpgViewOptions` ให้คุณควบคุม DPI และคุณภาพ ด้วย `setRenderHeadings(true)` ภาพที่ได้จะคงแถวและคอลัมน์หัวส่วนของสเปรดชีต ซึ่งสำคัญสำหรับรายงานและการนำเสนอ  

### เรนเดอร์สเปรดชีตเป็น PNG
**กระบวนการแปลง Excel เป็น PNG พร้อมคงหัวคอลัมน์เป็นอย่างไร?**  

เพื่อสร้างภาพ PNG จากไฟล์ Excel ให้ใช้ Viewer เปิดเวิร์กบุ๊ก, สร้างอินสแตนซ์ PngViewOptions, เปิดใช้งานการเรนเดอร์หัวส่วน, และเรียก view ผลลัพธ์ PNG ให้คุณภาพแบบ lossless คงสไตล์เซลล์และแถวหัวส่วนทั้งหมด ทำให้เหมาะสำหรับการเก็บถาวรหรือการประมวลผลภาพต่อไป  

#### การดำเนินการตามขั้นตอน
**1. นำเข้าห้องสมุดที่จำเป็น**  
PngViewOptions ควบคุมการเรนเดอร์ชีตเป็นภาพ PNG ให้การบีบอัดแบบ lossless และตัวเลือกหัวส่วน.  

```java
import com.groupdocs.viewer.Viewer;
import com.groupdocs.viewer.options.PngViewOptions;
```

**2. กำหนดไดเรกทอรีผลลัพธ์**  
เลือกโฟลเดอร์สำหรับผลลัพธ์ PNG.  

```java
Path outputDirectory = Paths.get("YOUR_DOCUMENT_DIRECTORY", "RenderRowAndColumnHeadings");
Path pageFilePathFormat = outputDirectory.resolve("page_{0}.png");
```

**3. เริ่มต้น Viewer และกำหนดค่าตัวเลือก**  
สร้าง viewer, เปิดใช้งานการเรนเดอร์หัวส่วน, และเรียก `view`.  

```java
try (Viewer viewer = new Viewer(Paths.get("Sample.xlsx"))) {
    PngViewOptions options = new PngViewOptions(pageFilePathFormat);
    
    // Enable rendering of row and column headings in the spreadsheet.
    options.getSpreadsheetOptions().setRenderHeadings(true);

    viewer.view(options, 1, 2, 3); // Render pages 1 to 3.
}
```

คำอธิบาย: การเรียก `setRenderHeadings(true)` ทำให้ไฟล์ PNG รวมแถวและคอลัมน์หัวส่วนของสเปรดชีตต้นฉบับ, คงบริบทสำหรับผู้ใช้ต่อไป  

### เรนเดอร์สเปรดชีตเป็น PDF
**ฉันจะแปลงไฟล์ Excel เป็น PDF พร้อมหัวแถวและหัวคอลัมน์ที่มองเห็นได้อย่างไร?**  

การแปลง Excel เป็น PDF ทำได้ง่าย: สร้างอินสแตนซ์ Viewer ด้วยไฟล์ต้นทาง, กำหนดอ็อบเจกต์ PdfViewOptions เพื่อเรนเดอร์หัวส่วน, และเรียก view PDF ที่ได้จะสะท้อนโครงสร้างของเวิร์กบุ๊กรวมถึงหัวแถวและหัวคอลัมน์, รองรับกราฟิกแบบเวกเตอร์สำหรับการพิมพ์และการแจกจ่ายที่คมชัด  

#### การดำเนินการตามขั้นตอน
**1. นำเข้าห้องสมุดที่จำเป็น**  
PdfViewOptions ระบุพารามิเตอร์การสร้าง PDF เช่น ขนาดหน้า, ระยะขอบ, และการเรนเดอร์หัวส่วน.  

```java
import com.groupdocs.viewer.Viewer;
import com.groupdocs.viewer.options.PdfViewOptions;
```

**2. กำหนดไดเรกทอรีผลลัพธ์**  
ระบุตำแหน่งโฟลเดอร์ปลายทางสำหรับเอกสาร PDF.  

```java
Path outputDirectory = Paths.get("YOUR_DOCUMENT_DIRECTORY", "RenderRowAndColumnHeadings");
Path pageFilePathFormat = outputDirectory.resolve("output.pdf");
```

**3. เริ่มต้น Viewer และกำหนดค่าตัวเลือก**  
สร้าง `Viewer`, เปิดใช้งานการเรนเดอร์หัวส่วน, และดำเนินการแปลง.  

```java
try (Viewer viewer = new Viewer(Paths.get("Sample.xlsx"))) {
    PdfViewOptions options = new PdfViewOptions(pageFilePathFormat);
    
    // Enable rendering of row and column headings in the spreadsheet.
    options.getSpreadsheetOptions().setRenderHeadings(true);

    viewer.view(options, 1, 2, 3); // Render pages 1 to 3.
}
```

คำอธิบาย: การตั้งค่า `setRenderHeadings(true)` บน `PdfViewOptions` รับประกันว่าแถว/คอลัมน์แรกจะปรากฏใน PDF สุดท้าย ทำให้เอกสารพร้อมสำหรับการพิมพ์หรือการเก็บถาวร  

## การประยุกต์ใช้งานจริง
สถานการณ์ในโลกจริงที่ **convert excel to html**, **excel to pdf java**, หรือ **convert spreadsheet to image** มีคุณค่าอย่างยิ่ง:
1. **Business Reporting:** สร้างแดชบอร์ด HTML หรือรายงาน PDF จากโมเดลการเงินโดยไม่ต้องคัดลอก‑วางด้วยตนเอง.  
2. **Data Visualization:** ฝังภาพสแนปช็อต JPG/PNG ของสเปรดชีตในสไลด์เด็ค, ทำให้หัวส่วนให้บริบททันทีแก่ผู้ชม.  
3. **Document Archiving:** เก็บเวิร์กบุ๊ก Excel เป็น PDF เพื่อการปฏิบัติตามกฎระเบียบ, พร้อมคงโครงสร้างและหัวส่วนเดิม.  
4. **Web Portals:** ให้บริการเวอร์ชัน HTML ของสเปรดชีตโดยตรงในเบราว์เซอร์, เปิดใช้งานการกรองแบบโต้ตอบด้วย JavaScript.  

## คำถามที่พบบ่อย
**Q: ฉันสามารถแปลงไฟล์ Excel ที่มีการป้องกันด้วยรหัสผ่านได้หรือไม่?**  
A: ใช่. ส่งรหัสผ่านไปยังคอนสตรัคเตอร์ของ `Viewer`, แล้วไลบรารีจะถอดรหัสเวิร์กบุ๊กก่อนการเรนเดอร์.  

**Q: GroupDocs.Viewer รองรับเวิร์กบุ๊กที่มีแมโคร (.xlsm) หรือไม่?**  
A: แน่นอน. Viewer ปฏิบัติกับแมโครเป็นข้อมูล; จะถูกละเว้นในระหว่างการเรนเดอร์, ทำให้การแปลงปลอดภัย.  

**Q: ขนาดไฟล์สูงสุดที่รองรับคือเท่าไหร่?**  
A: ไลบรารีสามารถประมวลผลไฟล์ได้สูงสุด **2 GB** โดยไม่ต้องโหลดเอกสารทั้งหมดเข้าสู่หน่วยความจำ, ขอบคุณสถาปัตยกรรมสตรีมมิ่งของมัน.  

**Q: สามารถเรนเดอร์เฉพาะชีตเดียวได้หรือไม่?**  
A: ใช่. ใช้ `ViewOptions.setPageNumber(pageIndex)` เพื่อกำหนดเป้าหมายที่ชีตเดียวเมื่อสร้าง HTML, JPG, PNG, หรือ PDF.  

**Q: ฉันจะควบคุมคุณภาพภาพสำหรับผลลัพธ์ JPG อย่างไร?**  
A: ตั้งค่า `JpgViewOptions.setQuality(90)` (ค่าระหว่าง 0‑100) เพื่อปรับสมดุลระหว่างขนาดไฟล์และความคมชัดของภาพ.  

## สรุป
คุณมีคู่มือครบถ้วนและพร้อมใช้งานในระดับผลิตภัณฑ์สำหรับ **convert excel to html**, **excel to pdf java**, และ **convert spreadsheet to image** ด้วย GroupDocs.Viewer Java แล้ว โดยทำตามขั้นตอนข้างต้นคุณสามารถรวมการเรนเดอร์สเปรดชีตเข้ากับแบ็กเอนด์ Java ใดก็ได้ ส่งมอบรายงาน HTML, ภาพความละเอียดสูง, หรือ PDF เพื่อการเก็บถาวรพร้อมหัวส่วนที่คงอัตโนมัติ  

---
**Last Updated:** 2026-06-05  
**Tested With:** GroupDocs.Viewer Java 23.12  
**Author:** GroupDocs  

## บทแนะนำที่เกี่ยวข้อง
- [วิธีแปลง DOCX เป็น HTML ด้วย GroupDocs.Viewer สำหรับ Java: คู่มือขั้นตอน](/viewer/java/export-conversion/convert-docx-to-html-groupdocs-viewer-java/)
- [การเรนเดอร์ HTML แบบตอบสนองด้วย GroupDocs.Viewer สำหรับ Java: คู่มือฉบับสมบูรณ์](/viewer/java/advanced-rendering/groupdocs-viewer-java-responsive-html-rendering/)
- [convert odf html java – แปลง ODF เป็น HTML, JPG, PNG, PDF ด้วย GroupDocs.Viewer สำหรับ Java](/viewer/java/export-conversion/convert-odf-documents-groupdocs-viewer-java/)