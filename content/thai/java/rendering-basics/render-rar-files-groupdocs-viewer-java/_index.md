---
"date": "2025-04-24"
"description": "เรียนรู้วิธีแปลงไฟล์ RAR เป็นรูปแบบที่สามารถเข้าถึงได้ เช่น HTML, JPG, PNG และ PDF โดยใช้ GroupDocs.Viewer สำหรับ Java คำแนะนำทีละขั้นตอนนี้ครอบคลุมทุกอย่างตั้งแต่การตั้งค่าจนถึงการเรนเดอร์โฟลเดอร์เฉพาะ"
"title": "เรนเดอร์ไฟล์ RAR เป็น HTML, JPG, PNG และ PDF โดยใช้ GroupDocs.Viewer สำหรับ Java"
"url": "/th/java/rendering-basics/render-rar-files-groupdocs-viewer-java/"
"weight": 1
---

# เรนเดอร์ไฟล์ RAR เป็นรูปแบบต่างๆ โดยใช้ GroupDocs.Viewer สำหรับ Java

ปลดล็อกศักยภาพของไฟล์เก็บถาวร RAR ของคุณด้วยการแปลงไฟล์ให้เป็นรูปแบบที่สามารถเข้าถึงได้ เช่น HTML, JPG, PNG และ PDF ด้วย GroupDocs.Viewer สำหรับ Java บทช่วยสอนนี้จะแนะนำคุณในแต่ละขั้นตอน เพื่อให้สามารถจัดการและนำเสนอเอกสารได้อย่างราบรื่น

## สิ่งที่คุณจะได้เรียนรู้
- เรนเดอร์ไฟล์ RAR เป็นรูปแบบต่าง ๆ โดยใช้ GroupDocs.Viewer สำหรับ Java
- ตัวอย่างโค้ดทีละขั้นตอนสำหรับการแปลง RAR เป็น HTML, JPG, PNG และ PDF
- ดึงข้อมูลมุมมองจากไฟล์เก็บถาวร RAR
- เรนเดอร์โฟลเดอร์เฉพาะภายในไฟล์ RAR

มาดำดิ่งลงไปกันเลย!

### ข้อกำหนดเบื้องต้น
ก่อนที่เราจะเริ่ม ให้แน่ใจว่าคุณมีสิ่งต่อไปนี้:

1. **ชุดพัฒนา Java (JDK)**: ต้องมีเวอร์ชัน 8 ขึ้นไป
2. **เมเวน**:บทช่วยสอนนี้ใช้ Maven สำหรับการจัดการการอ้างอิง
3. **GroupDocs.Viewer สำหรับไลบรารี Java**:เราจะใช้เวอร์ชัน 25.2.

#### การตั้งค่าสภาพแวดล้อม
- ตรวจสอบให้แน่ใจว่าคุณตั้งค่าสภาพแวดล้อมการพัฒนาโดยมีการติดตั้ง JDK และ Maven
- ความคุ้นเคยกับแนวคิดการเขียนโปรแกรม Java ขั้นพื้นฐานจะช่วยให้คุณทำตามได้ง่ายขึ้น

### การตั้งค่า GroupDocs.Viewer สำหรับ Java
หากต้องการรวม GroupDocs.Viewer เข้าในโครงการของคุณ ให้เพิ่มการอ้างอิงต่อไปนี้ใน `pom.xml` ไฟล์:

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

#### การขอใบอนุญาต
- **ทดลองใช้งานฟรี**: ดาวน์โหลดรุ่นทดลองใช้งานฟรีได้จาก [เว็บไซต์ GroupDocs](https://releases-groupdocs.com/viewer/java/).
- **ใบอนุญาตชั่วคราว**:รับใบอนุญาตชั่วคราวสำหรับฟีเจอร์ขยายได้ที่ [หน้าใบอนุญาต GroupDocs](https://purchase-groupdocs.com/temporary-license/).
- **ซื้อ**:สำหรับการใช้งานในระยะยาว ให้ซื้อใบอนุญาตผ่านทาง [หน้าการซื้อ GroupDocs](https://purchase-groupdocs.com/buy).

#### การเริ่มต้นขั้นพื้นฐาน
หลังจากตั้งค่าสภาพแวดล้อมและการอ้างอิงของคุณแล้ว ให้เริ่มต้น GroupDocs.Viewer ดังต่อไปนี้:

```java
import com.groupdocs.viewer.Viewer;

public class ViewerInitialization {
    public static void main(String[] args) {
        try (Viewer viewer = new Viewer("path/to/your/file.rar")) {
            // รหัสการเรนเดอร์ของคุณอยู่ที่นี่
        }
    }
}
```

### คู่มือการใช้งาน
เราจะสำรวจวิธีการเรนเดอร์ไฟล์ RAR เป็นรูปแบบต่างๆ โดยแต่ละรูปแบบจะมีชุดการกำหนดค่าของตัวเอง

#### การเรนเดอร์ RAR เป็น HTML
**ภาพรวม**:แปลงไฟล์ RAR เป็นเอกสาร HTML สำหรับการดูทางเว็บ

```java
import com.groupdocs.viewer.Viewer;
import com.groupdocs.viewer.options.HtmlViewOptions;
import java.nio.file.Path;
import java.nio.file.Paths;

public class RenderRarToHtml {
    public static void main(String[] args) {
        Path outputDirectory = Paths.get("YOUR_OUTPUT_DIRECTORY", "RenderingRar");
        Path pageFilePathFormat = outputDirectory.resolve("RAR_result_{0}.html");

        try (Viewer viewer = new Viewer(Paths.get("YOUR_DOCUMENT_DIRECTORY", "SAMPLE_RAR_WITH_FOLDERS"))) {
            HtmlViewOptions options = HtmlViewOptions.forEmbeddedResources(pageFilePathFormat);
            viewer.view(options); // เรนเดอร์ไฟล์ RAR เป็นรูปแบบ HTML
        }
    }
}
```
- **คำอธิบาย**: เดอะ `HtmlViewOptions` คลาสนี้ใช้กับรีซอร์สแบบฝังตัว ช่วยให้สามารถเรนเดอร์หน้าเว็บได้สมบูรณ์ รวมถึง CSS และรูปภาพ

#### การเรนเดอร์ RAR เป็น JPG
**ภาพรวม**:แปลงไฟล์ RAR ให้เป็นภาพ JPEG เหมาะสำหรับการดูภาพตัวอย่างขนาดย่อ

```java
import com.groupdocs.viewer.Viewer;
import com.groupdocs.viewer.options.JpgViewOptions;

public class RenderRarToJpg {
    public static void main(String[] args) {
        Path outputDirectory = Paths.get("YOUR_OUTPUT_DIRECTORY", "RenderingRar");
        Path pageFilePathFormat = outputDirectory.resolve("RAR_result_{0}.jpg");

        try (Viewer viewer = new Viewer(Paths.get("YOUR_DOCUMENT_DIRECTORY", "SAMPLE_RAR_WITH_FOLDERS"))) {
            JpgViewOptions options = new JpgViewOptions(pageFilePathFormat);
            viewer.view(options); // แปลงไฟล์ RAR เป็นรูปแบบ JPG
        }
    }
}
```
- **คำอธิบาย**- `JpgViewOptions` ระบุเส้นทางเอาต์พุตและจัดการการเรนเดอร์ภาพ

#### การเรนเดอร์ RAR เป็น PNG
**ภาพรวม**:แปลงไฟล์ RAR เป็นภาพ PNG เพื่อดูตัวอย่างคุณภาพสูง

```java
import com.groupdocs.viewer.Viewer;
import com.groupdocs.viewer.options.PngViewOptions;

public class RenderRarToPng {
    public static void main(String[] args) {
        Path outputDirectory = Paths.get("YOUR_OUTPUT_DIRECTORY", "RenderingRar");
        Path pageFilePathFormat = outputDirectory.resolve("RAR_result_{0}.png");

        try (Viewer viewer = new Viewer(Paths.get("YOUR_DOCUMENT_DIRECTORY", "SAMPLE_RAR_WITH_FOLDERS"))) {
            PngViewOptions options = new PngViewOptions(pageFilePathFormat);
            viewer.view(options); // เรนเดอร์ไฟล์ RAR เป็นรูปแบบ PNG
        }
    }
}
```
- **คำอธิบาย**: คล้ายกับ JPG `PngViewOptions` ใช้ในการเรนเดอร์แต่ละหน้าของ RAR เป็นรูปภาพ PNG

#### การเรนเดอร์ RAR เป็น PDF
**ภาพรวม**:สร้างเอกสาร PDF จากไฟล์ RAR เพื่อการแบ่งปันและการพิมพ์ได้อย่างง่ายดาย

```java
import com.groupdocs.viewer.Viewer;
import com.groupdocs.viewer.options.PdfViewOptions;

public class RenderRarToPdf {
    public static void main(String[] args) {
        Path outputDirectory = Paths.get("YOUR_OUTPUT_DIRECTORY", "RenderingRar");
        Path pageFilePathFormat = outputDirectory.resolve("RAR_result.pdf");

        try (Viewer viewer = new Viewer(Paths.get("YOUR_DOCUMENT_DIRECTORY", "SAMPLE_RAR_WITH_FOLDERS"))) {
            PdfViewOptions options = new PdfViewOptions(pageFilePathFormat);
            viewer.view(options); // แปลงไฟล์ RAR เป็นรูปแบบ PDF
        }
    }
}
```
- **คำอธิบาย**- `PdfViewOptions` กำหนดค่าเส้นทางเอาต์พุตสำหรับเอกสาร PDF

#### รับข้อมูลการดูสำหรับ RAR
**ภาพรวม**:ดึงข้อมูลเมตาและโครงสร้างข้อมูลจากไฟล์เก็บถาวร RAR

```java
import com.groupdocs.viewer.Viewer;
import com.groupdocs.viewer.options.ViewInfoOptions;
import com.groupdocs.viewer.results.ArchiveViewInfo;

public class GetViewInfoForRar {
    public static void main(String[] args) {
        try (Viewer viewer = new Viewer(Paths.get("YOUR_DOCUMENT_DIRECTORY", "SAMPLE_RAR_WITH_FOLDERS"))) {
            ViewInfo info = viewer.getViewInfo(ViewInfoOptions.forHtmlView());
            System.out.println("File type: " + info.getFileType());
            System.out.println("Pages count: " + info.getPages().size());

            readFolders(viewer, "");
        }
    }

    private static void readFolders(Viewer viewer, String folder) {
        ViewInfoOptions options = ViewInfoOptions.forHtmlView();
        options.getArchiveOptions().setFolder(folder);

        ArchiveViewInfo viewInfo = (ArchiveViewInfo) viewer.getViewInfo(options);
        for (String subFolder : viewInfo.getFolders()) {
            System.out.println(" - " + subFolder);
            readFolders(viewer, subFolder);
        }
    }
}
```
- **คำอธิบาย**:รหัสนี้จะดึงและพิมพ์ประเภทไฟล์และจำนวนหน้าในไฟล์เก็บถาวร RAR

#### การเรนเดอร์โฟลเดอร์เฉพาะของไฟล์ RAR
**ภาพรวม**:เน้นการแสดงโฟลเดอร์เฉพาะภายในไฟล์ RAR เป็นรูปแบบ HTML

```java
import com.groupdocs.viewer.Viewer;
import com.groupdocs.viewer.options.HtmlViewOptions;

public class RenderSpecificArchiveFolder {
    public static void main(String[] args) {
        Path outputDirectory = Paths.get("YOUR_OUTPUT_DIRECTORY", "RenderSpecificArchiveFolder");
        Path pageFilePathFormat = outputDirectory.resolve("archive_folder_page_{0}.html");

        try (Viewer viewer = new Viewer(Paths.get("YOUR_DOCUMENT_DIRECTORY", "SAMPLE_RAR_WITH_FOLDERS"))) {
            HtmlViewOptions options = HtmlViewOptions.forEmbeddedResources(pageFilePathFormat);
            options.getArchiveOptions().setFolder("TargetFolderName"); // ระบุโฟลเดอร์ที่คุณต้องการเรนเดอร์
            viewer.view(options); // แสดงเนื้อหาโฟลเดอร์ที่ระบุเป็น HTML
        }
    }
}
```
- **คำอธิบาย**: ใช้ `HtmlViewOptions` โดยมีการตั้งค่าโฟลเดอร์ที่เฉพาะเจาะจงเพื่อกำหนดเป้าหมายและแสดงโฟลเดอร์แต่ละโฟลเดอร์ภายในไฟล์เก็บถาวร RAR

หากทำตามขั้นตอนเหล่านี้ คุณจะสามารถใช้ GroupDocs.Viewer สำหรับ Java ในการจัดการและแปลงไฟล์ RAR ของคุณเป็นรูปแบบต่างๆ ได้อย่างมีประสิทธิภาพ

## บทสรุป

บทช่วยสอนนี้จะช่วยให้คุณมีความรู้ในการแปลงไฟล์ RAR เป็นรูปแบบที่เข้าถึงได้ เช่น HTML, JPG, PNG และ PDF ได้อย่างง่ายดายโดยใช้ GroupDocs.Viewer สำหรับ Java คุณจะได้เรียนรู้รายละเอียดการใช้งานทีละขั้นตอน รวมถึงการสร้างโฟลเดอร์เฉพาะและเรียกค้นข้อมูลไฟล์เก็บถาวร เพื่อเพิ่มความสามารถในการจัดการเอกสารของคุณ ไม่ว่าจะสำหรับการดูบนเว็บ การดูตัวอย่าง หรือการแชร์ เทคนิคเหล่านี้จะช่วยปรับปรุงวิธีที่คุณจัดการไฟล์ RAR ในแอปพลิเคชัน Java ของคุณ

### คำถามที่พบบ่อย

1. **ฉันสามารถแปลงไฟล์ RAR ที่ป้องกันด้วยรหัสผ่านด้วย GroupDocs.Viewer สำหรับ Java ได้หรือไม่**  

ใช่ แต่คุณต้องระบุรหัสผ่านในตัวเลือกเพื่อปลดล็อคและดูไฟล์เก็บถาวรที่ได้รับการป้องกัน

2. **เป็นไปได้ไหมที่จะแสดงเฉพาะหน้าหรือโฟลเดอร์ที่เจาะจงภายใน RAR?**  

แน่นอน คุณสามารถระบุโฟลเดอร์หรือหน้าที่จะแสดงผลโดยใช้ตัวเลือกเฉพาะ เช่น `setFolder()` ภายในการตั้งค่าการเรนเดอร์

3. **GroupDocs.Viewer รองรับรูปแบบเอาท์พุตใดสำหรับไฟล์ RAR?**  

รองรับรูปแบบ HTML, JPG, PNG และ PDF ให้ตัวเลือกที่ยืดหยุ่นในการดูและแบ่งปัน

4. **ฉันต้องมีใบอนุญาตเพื่อใช้ GroupDocs.Viewer สำหรับ Java หรือไม่**  

มีรุ่นทดลองใช้งานฟรี หากต้องการใช้ฟีเจอร์ครบถ้วนและใช้งานในระยะยาว ขอแนะนำให้ซื้อใบอนุญาตหรือขอใบอนุญาตชั่วคราว

5. **ฉันสามารถดำเนินการแปลง RAR อัตโนมัติในแอปพลิเคชัน Java ได้หรือไม่**  

ใช่ คุณสามารถฝังตัวอย่างโค้ดที่ให้มาลงในโปรเจ็กต์ Java ของคุณเพื่อทำการแปลงแบบแบตช์โดยอัตโนมัติได้อย่างราบรื่น