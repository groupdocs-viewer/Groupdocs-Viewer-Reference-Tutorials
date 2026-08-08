---
date: '2026-08-08'
description: เรียนรู้วิธีแปลง IGS เป็น PDF, HTML, JPG และ PNG ด้วย GroupDocs.Viewer
  สำหรับ Java คู่มือทีละขั้นตอน ข้อกำหนดเบื้องต้น และการแก้ไขปัญหาสำหรับนักพัฒนา Java
keywords:
- convert igs to pdf
- convert cad to image
- convert igs to jpg
- java cad to pdf
lastmod: '2026-08-08'
og_description: แปลง IGS เป็น PDF, HTML, JPG และ PNG ด้วย GroupDocs.Viewer สำหรับ
  Java การตั้งค่าโดยละเอียด ตัวอย่างโค้ด และการแก้ไขปัญหาสำหรับนักพัฒนา Java
og_image_alt: 'Developer guide: convert IGS files to PDF, HTML, JPG, PNG with GroupDocs.Viewer
  Java'
og_title: แปลง IGS เป็น PDF, HTML, JPG & PNG ด้วย GroupDocs.Viewer Java
schemas:
- author: GroupDocs
  dateModified: '2026-08-08'
  description: Learn how to convert IGS to PDF, HTML, JPG, and PNG using GroupDocs.Viewer
    for Java. Step‑by‑step guide, prerequisites, and troubleshooting for Java developers.
  headline: Convert IGS to PDF, HTML, JPG & PNG with GroupDocs.Viewer Java
  type: TechArticle
- questions:
  - answer: Yes. Iterate over a collection of file paths and invoke the appropriate
      `view` method for each file within the same `Viewer` instance.
    question: Can I convert multiple IGS files in a single run?
  - answer: Absolutely. `PdfViewOptions` offers `setPageSize(PageSize.A4)`, `PageSize.Letter`,
      and custom dimensions via `setCustomSize(width, height)`.
    question: Is it possible to customize the PDF page size?
  - answer: No. A single GroupDocs.Viewer license covers all supported formats, including
      HTML, JPG, PNG, and PDF.
    question: Do I need a separate license for each output format?
  - answer: The library reliably processes files up to **500 MB**; for models larger
      than 200 MB, allocate additional JVM memory and consider rendering in batches.
    question: How large can an IGS file be before performance degrades?
  - answer: GroupDocs.Viewer renders the default orientation defined in the IGS file.
      For custom views, preprocess the file with a CAD tool or adjust the model before
      conversion.
    question: Can I render only a specific view or orientation?
  type: FAQPage
tags:
- convert igs
- groupdocs.viewer
- java cad conversion
- pdf generation java
title: แปลง IGS เป็น PDF, HTML, JPG & PNG ด้วย GroupDocs.Viewer Java
type: docs
url: /th/java/file-formats-support/groupdocs-viewer-java-igs-rendering-html-jpg-png-pdf/
weight: 1
---

# แปลง IGS เป็น PDF, HTML, JPG และ PNG ด้วย GroupDocs.Viewer Java

หากคุณต้องการ **แปลง IGS เป็น PDF** (หรือเป็น HTML, JPG, PNG) โดยตรงจากแอปพลิเคชัน Java คุณมาถูกที่แล้ว ในบทแนะนำนี้เราจะพาคุณผ่านทุกขั้นตอนที่จำเป็น—ตั้งแต่การติดตั้งไลบรารีจนถึงการเรนเดอร์โมเดล 3‑D ในรูปแบบที่เหมาะกับโครงการของคุณ คุณจะเข้าใจว่าทำไม GroupDocs.Viewer จึงเป็นตัวเลือกที่มั่นคงสำหรับการแปลงที่รวดเร็วและเชื่อถือได้และคุณจะได้โค้ดตัวอย่างที่พร้อมใช้งานซึ่งสามารถนำไปใส่ในโซลูชันของคุณได้

![แปลงไฟล์ IGS เป็น HTML, JPG, PNG, และ PDF ด้วย GroupDocs.Viewer สำหรับ Java](/viewer/file-formats-support/convert-igs-files-to-html-jpg-png-and-pdf-java.png)

## คำตอบเร็ว
- **ฉันสามารถแปลง IGS เป็น PDF ด้วย Java ได้หรือไม่?** ใช่, ใช้ `PdfViewOptions` ร่วมกับ `Viewer` API.  
- **รูปแบบผลลัพธ์ที่รองรับมีอะไรบ้าง?** HTML, JPG, PNG, และ PDF ทั้งหมดได้รับการจัดการโดยเนทีฟ.  
- **ฉันต้องการใบอนุญาตสำหรับการผลิตหรือไม่?** จำเป็นต้องมีใบอนุญาตเชิงพาณิชย์; การทดลองใช้ฟรีช่วยให้คุณทดสอบฟีเจอร์หลักได้.  
- **ต้องการเวอร์ชัน Java ใด?** JDK 8 หรือสูงกว่า; ไลบรารียังทำงานบน Java 11, 17 และเวอร์ชันต่อไป.  
- **Maven เป็นวิธีเดียวในการเพิ่มไลบรารีหรือไม่?** ไม่, คุณยังสามารถใช้ Gradle หรือเพิ่มไฟล์ JAR ด้วยตนเองไปยัง classpath ของคุณได้.

## การแปลง IGS เป็น PDF คืออะไร?
การแปลง IGS เป็น PDF หมายถึงการเปลี่ยนไฟล์ CAD 3‑D ที่เป็นกลางให้เป็นเอกสารคงที่ที่สามารถดูได้ทั่วโลก สิ่งนี้ทำให้คุณสามารถแชร์ภาพการออกแบบกับผู้มีส่วนได้ส่วนเสียที่ไม่มีเครื่องมือ CAD, ฝังการเรนเดอร์ในรายงาน, หรือเก็บรักษาโมเดลเพื่อวัตถุประสงค์การปฏิบัติตามกฎระเบียบ.

## ทำไมต้องใช้ GroupDocs.Viewer สำหรับการแปลง IGS?
GroupDocs.Viewer ประมวลผลไฟล์ IGS โดยไม่ต้องอาศัยซอฟต์แวร์ CAD ภายนอก รองรับ **รูปแบบเข้าและออกกว่า 50+** สามารถเรนเดอร์การประกอบที่มี **หลายร้อยส่วน** ในขณะที่ใช้หน่วยความจำไม่เกิน **200 MB** และให้ผลลัพธ์ภายใน **2 วินาที** สำหรับโมเดลทั่วไปบนเซิร์ฟเวอร์มาตรฐาน ประโยชน์ที่วัดได้เหล่านี้ทำให้เป็นตัวเลือกที่มีประสิทธิภาพสูงและคุ้มค่าในการใช้งานสำหรับสายงานระดับองค์กร.

## ข้อกำหนดเบื้องต้น
- **GroupDocs.Viewer for Java** ≥ 25.2 (รุ่นเสถียรล่าสุด).  
- **JDK 8+** ติดตั้งและกำหนดค่าใน IDE ของคุณ (IntelliJ IDEA, Eclipse, NetBeans, ฯลฯ).  
- ความรู้พื้นฐานเกี่ยวกับ Maven (เป็นทางเลือกแต่แนะนำสำหรับการจัดการ dependencies).  

## การตั้งค่า GroupDocs.Viewer สำหรับ Java

### การพึ่งพา Maven
เพิ่มรีโพซิทอรีของ GroupDocs และ dependency ของ Viewer ลงในไฟล์ `pom.xml` ของคุณ:

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
GroupDocs.Viewer มีตัวเลือกใบอนุญาตสามแบบ:
- **Free trial** – การใช้งานจำกัด, เหมาะสำหรับการทดสอบแนวคิดอย่างรวดเร็ว.  
- **Temporary license** – มีฟีเจอร์ครบชุดสำหรับช่วงเวลาการประเมินสั้น ๆ, เหมาะสำหรับโครงการนำร่อง.  
- **Commercial license** – ใช้งานในการผลิตโดยไม่มีข้อจำกัด, รวมการสนับสนุนระดับสูงและอัปเดต.

### การเริ่มต้น Viewer พื้นฐาน
`Viewer` class เป็นจุดเริ่มต้นสำหรับการดำเนินการเรนเดอร์ทั้งหมด มันโหลดไฟล์ต้นทาง, วิเคราะห์รูปแบบ, และเปิดเผยเมธอดเพื่อสร้างผลลัพธ์ที่ต้องการ.

```java
import com.groupdocs.viewer.Viewer;

public class ViewerSetup {
    public static void main(String[] args) {
        try (Viewer viewer = new Viewer("path/to/your/document.igs")) {
            // Configuration and rendering logic goes here.
        }
    }
}
```

## การเรนเดอร์ IGS เป็น HTML

### วิธีการแปลง IGS เป็น HTML?
โหลดไฟล์ IGS ด้วยอินสแตนซ์ `Viewer` และส่งผ่านอ็อบเจ็กต์ `HtmlViewOptions` ที่ฝังทรัพยากรที่จำเป็นทั้งหมด การเรียกใช้จะคืนค่าไฟล์ HTML เดียวที่มีมุมมอง 3‑D เต็มรูปแบบ ทำให้การฝังในหน้าเว็บเป็นเรื่องง่าย คุณยังสามารถปรับแต่งการเรนเดอร์โดยตั้งค่าตัวเลือกต่าง ๆ เช่น ขนาดหน้า, สีพื้นหลัง, และการรวมคอนโทรลแบบโต้ตอบได้  
`HtmlViewOptions` กำหนดวิธีการสร้างผลลัพธ์ HTML รวมถึงการฝังทรัพยากรและการจัดหน้า.

```java
import com.groupdocs.viewer.Viewer;
import com.groupdocs.viewer.options.HtmlViewOptions;
import java.nio.file.Path;
import static java.nio.file.Paths.get;

public class RenderIgsToHtml {
    public static void run() {
        Path outputDirectory = get("YOUR_OUTPUT_DIRECTORY");
        Path pageFilePathFormat = outputDirectory.resolve("IGS_result.html");

        try (Viewer viewer = new Viewer(get("YOUR_DOCUMENT_DIRECTORY/SAMPLE_IGS"))) {
            HtmlViewOptions options = HtmlViewOptions.forEmbeddedResources(pageFilePathFormat);
            viewer.view(options);
        }
    }
}
```

## การเรนเดอร์ IGS เป็น JPG

### วิธีการแปลง IGS เป็น JPG?
สร้างอ็อบเจ็กต์ `JpgViewOptions`, กำหนดความละเอียดและคุณภาพการบีบอัดที่ต้องการ, แล้วให้ `Viewer` สร้างภาพแรสเตอร์สำหรับแต่ละหน้าของโมเดล ไฟล์ JPG ที่สร้างขึ้นสามารถบันทึกลงในไดเรกทอรีที่ระบุ, และคุณสามารถปรับพารามิเตอร์คุณภาพเพื่อสมดุลขนาดไฟล์กับความคมชัดของภาพ, ซึ่งมีประโยชน์สำหรับภาพย่อหรือการพิมพ์ความละเอียดสูง  
`JpgViewOptions` ระบุการตั้งค่าสำหรับการสร้างภาพ JPG เช่น ความละเอียด, คุณภาพ, และไดเรกทอรีผลลัพธ์.

```java
import com.groupdocs.viewer.Viewer;
import com.groupdocs.viewer.options.JpgViewOptions;
import java.nio.file.Path;
import static java.nio.file.Paths.get;

public class RenderIgsToJpg {
    public static void run() {
        Path outputDirectory = get("YOUR_OUTPUT_DIRECTORY");
        Path pageFilePathFormat = outputDirectory.resolve("IGS_result.jpg");

        try (Viewer viewer = new Viewer(get("YOUR_DOCUMENT_DIRECTORY/SAMPLE_IGS"))) {
            JpgViewOptions options = new JpgViewOptions(pageFilePathFormat);
            viewer.view(options);
        }
    }
}
```

## การเรนเดอร์ IGS เป็น PNG

### วิธีการแปลง IGS เป็น PNG?
`PngViewOptions` class ช่วยให้คุณสร้างภาพ lossless พร้อมความโปร่งใสแบบเลือกได้ รูปแบบนี้เหมาะสำหรับการวางซ้อนโมเดลบนพื้นหลังสีในสื่อการตลาด คุณยังสามารถกำหนดความละเอียดและสีพื้นหลังให้สอดคล้องกับแนวทางแบรนด์ของคุณ, เพื่อให้ลักษณะการแสดงผลสม่ำเสมอในทุกทรัพยากรที่สร้างขึ้น  
`PngViewOptions` กำหนดพารามิเตอร์สำหรับการเรนเดอร์ PNG รวมถึงความละเอียด, ความโปร่งใส, และสีพื้นหลัง.

```java
import com.groupdocs.viewer.Viewer;
import com.groupdocs.viewer.options.PngViewOptions;
import java.nio file.Path;
import static java.nio.file.Paths.get;

public class RenderIgsToPng {
    public static void run() {
        Path outputDirectory = get("YOUR_OUTPUT_DIRECTORY");
        Path pageFilePathFormat = outputDirectory.resolve("IGS_result.png");

        try (Viewer viewer = new Viewer(get("YOUR_DOCUMENT_DIRECTORY/SAMPLE_IGS"))) {
            PngViewOptions options = new PngViewOptions(pageFilePathFormat);
            viewer.view(options);
        }
    }
}
```

## การเรนเดอร์ IGS เป็น PDF

### วิธีการแปลง IGS เป็น PDF?
ใช้ `PdfViewOptions` เพื่อสร้าง PDF แบบหลายหน้า ที่คงรูปแบบการแสดงผลของโมเดล 3‑D คุณยังสามารถฝังฟอนต์และควบคุมขนาดหน้าให้สอดคล้องกับแนวทางแบรนด์ขององค์กร การตั้งค่าเพิ่มเติมช่วยให้คุณระบุคุณภาพภาพ, ระดับการบีบอัด, และการรวมสารบัญสำหรับการประกอบหลายหน้า  
`PdfViewOptions` ควบคุมการสร้าง PDF, ให้กำหนดขนาดหน้า, คุณภาพภาพ, และการฝังฟอนต์.

```java
import com.groupdocs.viewer.Viewer;
import com.groupdocs.viewer.options.PdfViewOptions;
import java.nio.file.Path;
import static java.nio.file.Paths.get;

public class RenderIgsToPdf {
    public static void run() {
        Path outputDirectory = get("YOUR_OUTPUT_DIRECTORY");
        Path pageFilePathFormat = outputDirectory.resolve("IGS_result.pdf");

        try (Viewer viewer = new Viewer(get("YOUR_DOCUMENT_DIRECTORY/SAMPLE_IGS"))) {
            PdfViewOptions options = new PdfViewOptions(pageFilePathFormat);
            viewer.view(options);
        }
    }
}
```

## การประยุกต์ใช้งานจริง
- **Web portals** – ฝังโมเดลที่เรนเดอร์เป็น HTML โดยตรงลงในตัวกำหนดค่าผลิตภัณฑ์, ให้ลูกค้าสามารถหมุนและซูมได้โดยไม่ต้องติดตั้งปลั๊กอิน.  
- **Marketing assets** – สร้างภาพ JPG/PNG ความละเอียดสูงสำหรับโบรชัวร์, สไลด์เด็ค, และโพสต์โซเชียลมีเดีย.  
- **Technical documentation** – รวมการเรนเดอร์ PDF ของโมเดล CAD ในคู่มือผู้ใช้, เพื่อให้วิศวกรสามารถดูแบบออกแบบแบบออฟไลน์.  
- **Quality assurance** – ทำการสร้างภาพย่ออัตโนมัติสำหรับไฟล์ IGS จำนวนหลายพันไฟล์, เร่งกระบวนการตรวจสอบภาพ.

## ปัญหาทั่วไปและวิธีแก้

| ปัญหา | วิธีแก้ |
|-------|----------|
| **ไม่พบโฟลเดอร์ผลลัพธ์** | ตรวจสอบพาธที่ส่งให้ `Path outputDirectory` และให้แน่ใจว่ากระบวนการ Java มีสิทธิ์เขียนในไดเรกทอรีเป้าหมาย. |
| **หน้าเปล่าใน PDF** | ยืนยันว่าไฟล์ IGS ต้นทางไม่ได้เสียหาย; เปิดไฟล์ในโปรแกรม CAD ดั้งเดิมก่อน. |
| **การเรนเดอร์ช้าในกรณีการประกอบขนาดใหญ่** | เพิ่มขนาด heap ของ JVM (`-Xmx2g` หรือมากกว่า) และพิจารณาเรนเดอร์ทีละหน้าโดยใช้ `viewer.getPageCount()` เพื่อประมวลผลเป็นส่วน. |
| **ฟอนต์หายใน PDF** | ใช้ `PdfViewOptions` เพื่อฝังฟอนต์ที่จำเป็นหรือทำการติดตั้งฟอนต์ที่ขาดหายบนเซิร์ฟเวอร์ที่ให้บริการการแปลง. |

## คำถามที่พบบ่อย

**Q: ฉันสามารถแปลงไฟล์ IGS หลายไฟล์ในหนึ่งการทำงานได้หรือไม่?**  
A: ใช่. ทำการวนซ้ำผ่านคอลเลกชันของพาธไฟล์และเรียกเมธอด `view` ที่เหมาะสมสำหรับแต่ละไฟล์ภายในอินสแตนซ์ `Viewer` เดียว.

**Q: สามารถปรับขนาดหน้าของ PDF ได้หรือไม่?**  
A: แน่นอน. `PdfViewOptions` มีเมธอด `setPageSize(PageSize.A4)`, `PageSize.Letter`, และกำหนดขนาดแบบกำหนดเองผ่าน `setCustomSize(width, height)`.

**Q: ฉันต้องการใบอนุญาตแยกต่างหากสำหรับแต่ละรูปแบบผลลัพธ์หรือไม่?**  
A: ไม่. ใบอนุญาต GroupDocs.Viewer เพียงใบเดียวครอบคลุมรูปแบบที่รองรับทั้งหมด รวมถึง HTML, JPG, PNG, และ PDF.

**Q: ไฟล์ IGS สามารถมีขนาดใหญ่เท่าใดก่อนที่ประสิทธิภาพจะลดลง?**  
A: ไลบรารีสามารถประมวลผลไฟล์ได้อย่างเชื่อถือได้จนถึง **500 MB**; สำหรับโมเดลที่ใหญ่กว่า 200 MB ให้จัดสรรหน่วยความจำ JVM เพิ่มเติมและพิจารณาเรนเดอร์เป็นชุด.

**Q: ฉันสามารถเรนเดอร์เฉพาะมุมมองหรือการวางแนวเฉพาะได้หรือไม่?**  
A: GroupDocs.Viewer จะเรนเดอร์ตามการวางแนวเริ่มต้นที่กำหนดในไฟล์ IGS. หากต้องการมุมมองแบบกำหนดเอง ให้ทำการเตรียมไฟล์ล่วงหน้าด้วยเครื่องมือ CAD หรือปรับโมเดลก่อนการแปลง.

---

**อัปเดตล่าสุด:** 2026-08-08  
**ทดสอบกับ:** GroupDocs.Viewer 25.2 for Java  
**ผู้เขียน:** GroupDocs

## บทแนะนำที่เกี่ยวข้อง

- [แปลง cdr เป็น html, jpg, png, pdf ด้วย GroupDocs.Viewer Java](/viewer/java/file-formats-support/render-cdr-documents-groupdocs-viewer-java-guide/)
- [วิธีแปลง pdf เป็น html และปรับคุณภาพภาพใน Java ด้วย GroupDocs.Viewer](/viewer/java/advanced-rendering/adjust-image-quality-groupdocs-viewer-java/)