---
"date": "2025-04-24"
"description": "เรียนรู้วิธีแปลงไฟล์ IGS เป็นรูปแบบต่างๆ โดยใช้ GroupDocs.Viewer สำหรับ Java ปฏิบัติตามคำแนะนำทีละขั้นตอนนี้เพื่อเรนเดอร์โมเดล 3 มิติในรูปแบบ HTML, JPG, PNG หรือ PDF"
"title": "เรียนรู้การใช้ GroupDocs.Viewer Java เพื่อแปลงไฟล์ IGS เป็น HTML, JPG, PNG และ PDF"
"url": "/th/java/file-formats-support/groupdocs-viewer-java-igs-rendering-html-jpg-png-pdf/"
"weight": 1
---

# เรียนรู้การใช้ GroupDocs.Viewer Java: แปลงไฟล์ IGS เป็นรูปแบบต่างๆ

## การแนะนำ

คุณกำลังมองหาวิธีแปลงไฟล์ IGS ที่ซับซ้อนเป็นรูปแบบที่สามารถเข้าถึงได้ เช่น HTML, JPG, PNG หรือ PDF โดยใช้ Java หรือไม่ คู่มือฉบับสมบูรณ์นี้จะช่วยให้คุณเชี่ยวชาญไลบรารี GroupDocs.Viewer สำหรับ Java ไม่ว่าคุณจะเป็นนักพัฒนาที่มีประสบการณ์หรือเพิ่งเริ่มต้น บทช่วยสอนนี้จะช่วยให้คุณแสดงเอกสาร IGS ได้อย่างง่ายดาย

**สิ่งที่คุณจะได้เรียนรู้:**
- วิธีตั้งค่าและกำหนดค่า GroupDocs.Viewer สำหรับ Java
- คำแนะนำทีละขั้นตอนในการเรนเดอร์ไฟล์ IGS เป็นรูปแบบ HTML, JPG, PNG และ PDF
- ตัวเลือกการกำหนดค่าคีย์และเคล็ดลับการแก้ไขปัญหา
- การประยุกต์ใช้งานจริงของการแปลงเหล่านี้ในสถานการณ์โลกแห่งความเป็นจริง

มาเริ่มต้นด้วยการครอบคลุมข้อกำหนดเบื้องต้นกันก่อน!

## ข้อกำหนดเบื้องต้น

หากต้องการปฏิบัติตามบทช่วยสอนนี้อย่างมีประสิทธิผล ให้แน่ใจว่าคุณมีสิ่งต่อไปนี้:

### ไลบรารีและการอ้างอิงที่จำเป็น
- **GroupDocs.Viewer สำหรับ Java**:ขอแนะนำเวอร์ชัน 25.2 ขึ้นไป
- **ชุดพัฒนา Java (JDK)**:ตรวจสอบให้แน่ใจว่าได้ติดตั้ง JDK 8 หรือสูงกว่าบนระบบของคุณ

### ข้อกำหนดการตั้งค่าสภาพแวดล้อม
- สภาพแวดล้อมการพัฒนาแบบบูรณาการ (IDE) ที่เหมาะสม เช่น IntelliJ IDEA, Eclipse หรือ NetBeans
- ความเข้าใจพื้นฐานเกี่ยวกับแนวคิดการเขียนโปรแกรม Java และการดำเนินการ I/O ไฟล์

### ข้อกำหนดเบื้องต้นของความรู้
การคุ้นเคยกับ Maven สำหรับการจัดการการอ้างอิงจะเป็นประโยชน์แต่ไม่จำเป็น เราจะอธิบายทุกอย่างทีละขั้นตอน!

## การตั้งค่า GroupDocs.Viewer สำหรับ Java

หากต้องการเริ่มต้นการเรนเดอร์ไฟล์ IGS ขั้นแรกให้ตั้งค่าไลบรารี GroupDocs.Viewer ในโปรเจ็กต์ของคุณ

**การตั้งค่า Maven**
เพิ่มการกำหนดค่าต่อไปนี้ลงในของคุณ `pom.xml` ไฟล์:

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

### การขอใบอนุญาต
GroupDocs.Viewer นำเสนอการทดลองใช้ฟรี ใบอนุญาตชั่วคราวสำหรับการทดสอบ และตัวเลือกการซื้อสำหรับการเข้าถึงแบบเต็มรูปแบบ:
- **ทดลองใช้งานฟรี**:เข้าถึงฟีเจอร์หลักที่มีการใช้งานที่จำกัด
- **ใบอนุญาตชั่วคราว**:ประเมินห้องสมุดโดยไม่มีข้อจำกัดในช่วงระยะเวลาสั้น ๆ
- **ซื้อ**:ซื้อลิขสิทธิ์เพื่อใช้งานระยะยาว.

เมื่อตั้งค่าแล้ว ให้เริ่มต้น GroupDocs.Viewer ในแอปพลิเคชัน Java ของคุณดังนี้:

```java
import com.groupdocs.viewer.Viewer;

public class ViewerSetup {
    public static void main(String[] args) {
        try (Viewer viewer = new Viewer("path/to/your/document.igs")) {
            // ตรรกะของการกำหนดค่าและการเรนเดอร์อยู่ที่นี่
        }
    }
}
```

## คู่มือการใช้งาน

ตอนนี้เรามาดูขั้นตอนการแปลงไฟล์ IGS เป็นรูปแบบต่างๆ โดยใช้ GroupDocs.Viewer สำหรับ Java กัน

### การเรนเดอร์ IGS เป็น HTML

**ภาพรวม:**
แปลงไฟล์ IGS เป็นหน้า HTML แบบโต้ตอบที่มีทรัพยากรที่ฝังไว้ รูปแบบนี้เหมาะสำหรับแอปพลิเคชันเว็บที่ผู้ใช้จำเป็นต้องดูโมเดล 3 มิติโดยตรงในเบราว์เซอร์ของตน

#### การดำเนินการทีละขั้นตอน:
1. **ตั้งค่าไดเรกทอรีเอาท์พุตและเส้นทางไฟล์:**
   กำหนดไดเร็กทอรีที่คุณจะบันทึกไฟล์ที่เรนเดอร์ พร้อมทั้งระบุชื่อไฟล์เอาต์พุต

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

2. **ทำความเข้าใจพารามิเตอร์:**
   - `HtmlViewOptions.forEmbeddedResources()` ระบุว่าทรัพยากร (เช่น รูปภาพ) ควรจะฝังไว้ภายในไฟล์ HTML ทำให้เป็นเอกสารแบบสแตนด์อโลน

3. **เคล็ดลับการแก้ไขปัญหา:**
   - ตรวจสอบให้แน่ใจว่าเส้นทางไดเร็กทอรีเอาต์พุตของคุณถูกต้อง
   - ตรวจสอบสิทธิ์ไฟล์ในการเขียนลงในไดเร็กทอรีที่ระบุ

### การเรนเดอร์ IGS เป็น JPG

**ภาพรวม:**
แปลงไฟล์ IGS ของคุณเป็นรูปภาพ JPG คุณภาพสูง ซึ่งสามารถใช้สำหรับภาพขนาดย่อหรือภาพตัวอย่างของโมเดล 3 มิติได้

#### การดำเนินการทีละขั้นตอน:
1. **ตั้งค่าไดเรกทอรีเอาท์พุตและเส้นทางไฟล์:**
   การตั้งค่าคล้ายกับการแปลง HTML แต่มีตัวเลือกเฉพาะสำหรับ JPG

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

2. **การกำหนดค่าที่สำคัญ:**
   - `JpgViewOptions` ช่วยให้คุณกำหนดความละเอียดและคุณภาพของภาพเอาต์พุตได้

3. **เคล็ดลับการแก้ไขปัญหา:**
   - ตรวจสอบว่าไฟล์ IGS ของคุณมีการอ้างอิงอย่างถูกต้องหรือไม่
   - ปรับแต่งตัวเลือก JPG ให้ได้คุณภาพเหมาะสมที่สุดตามความต้องการของคุณ

### การเรนเดอร์ IGS เป็น PNG

**ภาพรวม:**
สร้างรูปภาพโปร่งใสหรือไม่โปร่งใสจากไฟล์ IGS ของคุณในรูปแบบ PNG เหมาะสำหรับการแสดงภาพแบบละเอียด

#### การดำเนินการทีละขั้นตอน:
1. **ตั้งค่าไดเรกทอรีเอาท์พุตและเส้นทางไฟล์:**

    ```java
    import com.groupdocs.viewer.Viewer;
    import com.groupdocs.viewer.options.PngViewOptions;
    import java.nio.file.Path;
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

2. **ตัวเลือกการกำหนดค่า:**
   - `PngViewOptions` ใช้เพื่อกำหนดคุณภาพและความโปร่งใสของภาพได้

3. **เคล็ดลับการแก้ไขปัญหา:**
   - ตรวจสอบให้แน่ใจว่าเส้นทางไฟล์ IGS ของคุณได้รับการตั้งค่าอย่างถูกต้อง
   - ทดลองใช้ตัวเลือก PNG ที่แตกต่างกันเพื่อผลลัพธ์ที่ดีที่สุด

### การเรนเดอร์ IGS เป็น PDF

**ภาพรวม:**
แปลงเอกสาร IGS เป็นไฟล์ PDF ที่สามารถเข้าถึงได้ทั่วโลก เหมาะสำหรับการแบ่งปันโมเดล 3 มิติโดยละเอียดในรูปแบบมาตรฐาน

#### การดำเนินการทีละขั้นตอน:
1. **ตั้งค่าไดเรกทอรีเอาท์พุตและเส้นทางไฟล์:**

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

2. **คุณสมบัติหลัก:**
   - `PdfViewOptions` ช่วยให้ปรับแต่งการตั้งค่า PDF เช่นเค้าโครงและคุณภาพได้

3. **เคล็ดลับการแก้ไขปัญหา:**
   - ตรวจสอบว่าไดเรกทอรีเอาท์พุตสามารถเขียนได้
   - ตรวจสอบข้อผิดพลาดใด ๆ ในรูปแบบไฟล์ IGS

## การประยุกต์ใช้งานจริง

การเรนเดอร์ไฟล์ IGS ในรูปแบบต่างๆ จะเปิดโอกาสให้เกิดความเป็นไปได้มากมาย:
1. **การบูรณาการเว็บไซต์**:ฝังโมเดล 3 มิติที่แสดงผล HTML โดยตรงลงในแอปพลิเคชันเว็บ
2. **การแบ่งปันเอกสาร**:แบ่งปันภาพรายละเอียดผ่านทาง PDF หรือการดูตัวอย่างภาพ (JPG/PNG)
3. **การแสดงภาพผลิตภัณฑ์**:ใช้รูปภาพคุณภาพสูงสำหรับแคตตาล็อกผลิตภัณฑ์และสื่อการตลาด

คู่มือนี้ช่วยให้คุณมีความรู้ในการใช้ GroupDocs.Viewer สำหรับ Java ได้อย่างมีประสิทธิภาพในการแปลงไฟล์ IGS เป็นรูปแบบต่างๆ