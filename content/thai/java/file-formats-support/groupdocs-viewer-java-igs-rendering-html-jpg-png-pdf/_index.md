---
date: '2026-02-23'
description: เรียนรู้วิธีแปลงไฟล์ IGS เป็น PDF, HTML, JPG และ PNG ด้วย GroupDocs.Viewer
  สำหรับ Java. ทำตามคู่มือขั้นตอนต่อขั้นตอนพร้อมตัวอย่างโค้ดที่พร้อมใช้งาน.
keywords:
- GroupDocs.Viewer Java
- Convert IGS Files
- Render IGS Documents
title: แปลง IGS เป็น PDF, HTML, JPG และ PNG ด้วย GroupDocs.Viewer Java
type: docs
url: /th/java/file-formats-support/groupdocs-viewer-java-igs-rendering-html-jpg-png-pdf/
weight: 1
---

# แปลง IGS เป็น PDF, HTML, JPG & PNG ด้วย GroupDocs.Viewer Java

หากคุณต้องการ **convert IGS to PDF** (หรือเป็น HTML, JPG, PNG) โดยตรงจากแอปพลิเคชัน Java คุณมาถูกที่แล้ว ในบทแนะนำนี้เราจะพาคุณผ่านทุกขั้นตอนที่ต้องการ—ตั้งแต่การตั้งค่าห้องสมุดจนถึงการเรนเดอร์โมเดล 3‑D ในรูปแบบที่เหมาะกับโครงการของคุณ คุณจะได้เห็นว่าทำไม GroupDocs.Viewer เป็นตัวเลือกที่มั่นคงสำหรับการแปลงที่รวดเร็วและเชื่อถือได้ และจะได้รับโค้ดตัวอย่างที่คุณสามารถนำไปใช้ในโซลูชันของคุณได้

![แปลงไฟล์ IGS เป็น HTML, JPG, PNG, และ PDF ด้วย GroupDocs.Viewer สำหรับ Java](/viewer/file-formats-support/convert-igs-files-to-html-jpg-png-and-pdf-java.png)

## คำตอบด่วน
- **ฉันสามารถ convert IGS to PDF ด้วย Java ได้หรือไม่?** ใช่, โดยใช้ `PdfViewOptions` ของ GroupDocs.Viewer.  
- **รูปแบบผลลัพธ์ที่รองรับคืออะไร?** HTML, JPG, PNG, และ PDF.  
- **ฉันต้องการใบอนุญาตสำหรับการใช้งานในโปรดักชันหรือไม่?** ต้องมีใบอนุญาตเชิงพาณิชย์; มีการทดลองใช้งานฟรีสำหรับการทดสอบ.  
- **ต้องการเวอร์ชัน Java อะไร?** JDK 8 หรือสูงกว่า.  
- **Maven เป็นวิธีเดียวที่ใช้เพิ่มไลบรารีหรือไม่?** ไม่, คุณยังสามารถใช้ Gradle หรือการเพิ่ม JAR ด้วยตนเองได้.  

## “convert IGS to PDF” คืออะไร?
การแปลง IGS (รูปแบบไฟล์กลางสำหรับข้อมูล CAD 3‑D) เป็น PDF หมายถึงการเปลี่ยนโมเดล 3‑D ที่ซับซ้อนให้เป็นเอกสารแบบคงที่ที่สามารถดูได้อย่างกว้างขวาง สิ่งนี้มีประโยชน์สำหรับการแชร์การออกแบบกับผู้มีส่วนได้ส่วนเสียที่ไม่มีเครื่องมือ CAD  

## ทำไมต้องใช้ GroupDocs.Viewer สำหรับการแปลง IGS?
- **Zero‑code CAD rendering** – ไลบรารีจัดการการประมวลผลขั้นสูงของการแยกวิเคราะห์รูปแบบ IGS.  
- **Multiple output options** – การเรียก API ครั้งเดียวสามารถสร้าง HTML, JPG, PNG หรือ PDF.  
- **Cross‑platform** – ทำงานบนระบบปฏิบัติการใด ๆ ที่รองรับ Java.  
- **Performance‑focused** – เรนเดอร์เร็วแม้สำหรับการประกอบขนาดใหญ่.  

## ข้อกำหนดเบื้องต้น
- **GroupDocs.Viewer for Java** ≥ 25.2  
- **JDK 8+** ที่ติดตั้งและกำหนดค่าใน IDE ของคุณ (IntelliJ IDEA, Eclipse, NetBeans, ฯลฯ)  
- ความรู้พื้นฐานเกี่ยวกับ Maven (ไม่บังคับแต่แนะนำ)  

## การตั้งค่า GroupDocs.Viewer สำหรับ Java

### การพึ่งพา Maven
เพิ่มรีโพซิทอรีของ GroupDocs และการพึ่งพา Viewer ลงในไฟล์ `pom.xml` ของคุณ:

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
GroupDocs.Viewer มีให้เลือก:
- **Free trial** – การใช้งานจำกัด, เหมาะสำหรับการทดสอบอย่างรวดเร็ว.  
- **Temporary license** – ชุดคุณสมบัติเต็มสำหรับช่วงเวลาการประเมินสั้น.  
- **Commercial license** – การใช้งานในโปรดักชันโดยไม่มีข้อจำกัด.  

### การเริ่มต้น Viewer เบื้องต้น
โค้ดตัวอย่างด้านล่างแสดงวิธีสร้างอินสแตนซ์ `Viewer` ที่ชี้ไปยังไฟล์ IGS ของคุณ:

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
ผลลัพธ์ HTML ให้มุมมองแบบโต้ตอบที่เป็นมิตรกับเบราว์เซอร์ของโมเดล 3‑D

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

**จุดสำคัญ:** `HtmlViewOptions.forEmbeddedResources()` ฝังทรัพยากรที่จำเป็นทั้งหมด (CSS, รูปภาพ) ลงในไฟล์ HTML โดยตรง ทำให้ไฟล์พกพาได้  

## การเรนเดอร์ IGS เป็น JPG

### วิธีการแปลง IGS เป็น JPG?
ภาพ JPG เหมาะสำหรับรูปย่อหรือการพรีวิวอย่างรวดเร็ว

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

คุณสามารถปรับ `JpgViewOptions` เพื่อควบคุมความละเอียดและคุณภาพการบีบอัด  

## การเรนเดอร์ IGS เป็น PNG

### วิธีการแปลง IGS เป็น PNG?
PNG รองรับความโปร่งใส ซึ่งเป็นประโยชน์สำหรับการวางโมเดลบนพื้นหลังต่าง ๆ

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

ทดลองใช้ `PngViewOptions` เพื่อหาความสมดุลที่ดีที่สุดระหว่างขนาดไฟล์และความคมชัดของภาพ  

## การเรนเดอร์ IGS เป็น PDF

### วิธีการแปลง IGS เป็น PDF?
PDF เป็นรูปแบบหลักสำหรับการแชร์เอกสารการออกแบบรายละเอียด ส่วนนี้ตอบตรงกับคีย์เวิร์ดหลัก **convert IGS to PDF**

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

`PdfViewOptions` ให้คุณควบคุมการจัดหน้า, คุณภาพภาพ, และการฝังฟอนต์หรือไม่  

## การประยุกต์ใช้งานจริง
- **Web portals** – ฝังโมเดลที่เรนเดอร์เป็น HTML ลงในตัวกำหนดค่าผลิตภัณฑ์โดยตรง.  
- **Marketing assets** – สร้างภาพ JPG/PNG ความละเอียดสูงสำหรับโบรชัวร์.  
- **Technical documentation** – รวมการเรนเดอร์ PDF ของโมเดล CAD ในคู่มือผู้ใช้.  
- **Quality assurance** – ทำการสร้างรูปย่ออัตโนมัติสำหรับชุดไฟล์ IGS จำนวนมาก.  

## ปัญหาที่พบบ่อยและวิธีแก้

| Issue | Solution |
|-------|----------|
| **ไม่พบโฟลเดอร์ผลลัพธ์** | ตรวจสอบเส้นทางที่ส่งให้ `Path outputDirectory` และให้แน่ใจว่ากระบวนการ Java มีสิทธิ์เขียน |
| **หน้าเปล่าใน PDF** | ตรวจสอบว่าไฟล์ IGS ไม่เสียหาย; ลองเปิดในโปรแกรมดู CAD ก่อน |
| **การเรนเดอร์ช้าเมื่อจัดการการประกอบขนาดใหญ่** | เพิ่มขนาด heap ของ JVM (`-Xmx2g` หรือมากกว่า) และพิจารณาเรนเดอร์ทีละหน้าโดยใช้ `viewer.getPageCount()` หากจำเป็น |
| **ฟอนต์หายใน PDF** | ใช้ `PdfViewOptions` เพื่อฝังฟอนต์ที่จำเป็นหรือทำการติดตั้งฟอนต์ที่หายไปบนเซิร์ฟเวอร์ |

## คำถามที่พบบ่อย

**Q: ฉันสามารถแปลงไฟล์ IGS หลายไฟล์ในรอบเดียวได้หรือไม่?**  
A: ใช่. วนลูปผ่านรายการเส้นทางไฟล์และเรียกใช้เมธอด `view` ที่เหมาะสมสำหรับแต่ละไฟล์.

**Q: สามารถปรับขนาดหน้าของ PDF ได้หรือไม่?**  
A: แน่นอน. `PdfViewOptions` มีเมธอด `setPageSize(PageSize.A4)` และเมธอดที่คล้ายกัน.

**Q: ฉันต้องการใบอนุญาตแยกต่างหากสำหรับแต่ละรูปแบบผลลัพธ์หรือไม่?**  
A: ไม่. ใบอนุญาต GroupDocs.Viewer เพียงใบเดียวครอบคลุมรูปแบบที่รองรับทั้งหมด.

**Q: ไฟล์ IGS สามารถมีขนาดใหญ่เท่าใดก่อนที่ประสิทธิภาพจะลดลง?**  
A: ไลบรารีรองรับไฟล์ขนาดหลายร้อยเมกะไบต์, แต่คุณอาจต้องจัดสรรหน่วยความจำ JVM เพิ่มขึ้นสำหรับโมเดลที่ใหญ่มาก.

**Q: ฉันสามารถเรนเดอร์เฉพาะมุมมองหรือทิศทางที่กำหนดได้หรือไม่?**  
A: GroupDocs.Viewer จะเรนเดอร์มุมมองเริ่มต้น. หากต้องการทิศทางที่กำหนดเอง, ให้ทำการเตรียมไฟล์ IGS ด้วยเครื่องมือ CAD ก่อนการแปลง.

---

**Last Updated:** 2026-02-23  
**ทดสอบด้วย:** GroupDocs.Viewer 25.2 for Java  
**ผู้เขียน:** GroupDocs