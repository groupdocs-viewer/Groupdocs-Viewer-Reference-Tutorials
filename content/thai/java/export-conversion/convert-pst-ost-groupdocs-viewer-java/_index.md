---
date: '2026-02-15'
description: เรียนรู้วิธีแปลงไฟล์ pst เป็น html และรูปแบบอื่น ๆ เช่น JPG, PNG, PDF
  ด้วย GroupDocs.Viewer สำหรับ Java คู่มือนี้ครอบคลุมขั้นตอนและการกำหนดค่าที่จำเป็นทั้งหมด.
keywords:
- convert PST/OST
- GroupDocs.Viewer for Java
- render documents
title: แปลงไฟล์ PST เป็น HTML, JPG, PNG, PDF ด้วย GroupDocs.Viewer สำหรับ Java
type: docs
url: /th/java/export-conversion/convert-pst-ost-groupdocs-viewer-java/
weight: 1
---

 "Author"? Probably yes, but keep bold formatting. So:

**อัปเดตล่าสุด:** 2026-02-15  
**ทดสอบกับ:** GroupDocs.Viewer for Java 25.2  
**ผู้เขียน:** GroupDocs  

Now ensure all markdown formatting preserved.

Check for any other markdown links: none.

Check for any code blocks: placeholders only.

Check for any Hugo shortcodes: none.

Now produce final content.# แปลง PST เป็น HTML, JPG, PNG, PDF ด้วย GroupDocs.Viewer for Java

คุณกำลังมองหา **convert pst to html** หรือรูปแบบอื่น ๆ เช่น JPG, PNG หรือ PDF อยู่หรือไม่? ด้วยไลบรารี GroupDocs.Viewer for Java ที่มีประสิทธิภาพ งานนี้จะทำได้อย่างง่ายดายและมีประสิทธิภาพ ในบทแนะนำนี้คุณจะได้เรียนรู้วิธีเรนเดอร์ไฟล์ Outlook PST/OST ให้เป็น HTML ที่เหมาะกับเว็บ, ไฟล์รูปภาพ หรือ PDF เดียว ทำให้การเก็บอีเมลของคุณง่ายต่อการแชร์และจัดเก็บ.

![แปลง PST/OST เป็น HTML, JPG, PNG, PDF ด้วย GroupDocs.Viewer for Java](/viewer/export-conversion/convert-pst-ost-to-html-jpg-png-pdf.png)

**สิ่งที่คุณจะได้เรียนรู้**
- วิธีตั้งค่า GroupDocs.Viewer for Java ในโครงการ Maven.  
- ขั้นตอนแบบละเอียดเพื่อ **java convert pst** ไฟล์เป็น HTML, JPG, PNG, และ PDF.  
- เคล็ดลับการกำหนดค่าเพื่อประสิทธิภาพสูงสุดและหลีกเลี่ยงข้อผิดพลาดทั่วไป.

## คำตอบอย่างรวดเร็ว
- **ไลบรารีใดจัดการการแปลง PST?** GroupDocs.Viewer for Java.  
- **ฉันสามารถแปลง PST เป็น PDF ได้โดยตรงหรือไม่?** ใช่, โดยใช้ `PdfViewOptions`.  
- **ต้องการไลเซนส์สำหรับการใช้งานในโปรดักชันหรือไม่?** จำเป็นต้องมีไลเซนส์ GroupDocs ที่ถูกต้อง.  
- **เวอร์ชัน Java ที่รองรับคืออะไร?** JDK 8 หรือสูงกว่า.  
- **ต้องดึงไฟล์แนบออกด้วยตนเองหรือไม่?** ไม่จำเป็น, ตัว viewer จะเรนเดอร์ไฟล์แนบโดยอัตโนมัติ.

## วิธีแปลง pst เป็น html ด้วย GroupDocs.Viewer for Java
ด้านล่างคุณจะพบภาพรวมสั้น ๆ ของกระบวนการแปลง ก่อนที่จะลงลึกในตัวอย่างโค้ดโดยละเอียด.

### ทำไมต้องเลือก GroupDocs.Viewer?
- **ความแม่นยำสูง** ในการเรนเดอร์เนื้อหาอีเมล, ไฟล์แนบ, และรูปแบบ.  
- **หลายรูปแบบผลลัพธ์** (HTML, JPG, PNG, PDF) จาก API เดียว.  
- **ไม่มีการพึ่งพาภายนอก** – ทุกอย่างทำงานภายในแอปพลิเคชัน Java ของคุณ.

## ข้อกำหนดเบื้องต้น

- **GroupDocs.Viewer for Java** – เวอร์ชัน 25.2 หรือใหม่กว่า.  
- **Java Development Kit (JDK)** – 8 หรือใหม่กว่า.  
- Maven สำหรับการจัดการ dependencies.  
- ความรู้พื้นฐานของ Java และความคุ้นเคยกับ Maven.

## การตั้งค่า GroupDocs.Viewer for Java

เพิ่มรีโพซิทอรีของ GroupDocs และ dependency ลงในไฟล์ `pom.xml` ของคุณ:

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
- **Free trial** – ทดลองใช้ทั้งหมดโดยไม่มีค่าใช้จ่าย.  
- **Temporary license** – ขยายระยะเวลาการประเมินหากต้องการ.  
- **Full license** – จำเป็นสำหรับการใช้งานในโปรดักชัน.

### การเริ่มต้นพื้นฐาน

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

ส่วนต่อไปนี้จะพาคุณผ่านการเรนเดอร์ไฟล์ PST/OST ไปยังแต่ละรูปแบบที่รองรับ.

### การเรนเดอร์เอกสาร PST/OST เป็น HTML

#### ขั้นตอนที่ 1: ตั้งค่าไดเรกทอรีผลลัพธ์

```java
Path outputDirectory = Paths.get("YOUR_OUTPUT_DIRECTORY");
Path pageFilePathFormat = outputDirectory.resolve("PST_result.html");
```

#### ขั้นตอนที่ 2: กำหนดค่า Load Options

```java
LoadOptions loadOptions = new LoadOptions();
loadOptions.setResourceLoadingTimeout(100);
```

#### ขั้นตอนที่ 3: เริ่มต้น Viewer และเรนเดอร์ HTML

```java
try (Viewer viewer = new Viewer("YOUR_DOCUMENT_DIRECTORY/SAMPLE_PST", loadOptions)) {
    HtmlViewOptions options = HtmlViewOptions.forEmbeddedResources(pageFilePathFormat);
    viewer.view(options);
}
```

### การเรนเดอร์เอกสาร PST/OST เป็น JPG

#### ขั้นตอนที่ 1: ตั้งค่าไดเรกทอรีผลลัพธ์

```java
Path outputDirectory = Paths.get("YOUR_OUTPUT_DIRECTORY");
Path pageFilePathFormat = outputDirectory.resolve("PST_result_{0}.jpg");
```

#### ขั้นตอนที่ 2: กำหนดค่า Load Options

```java
LoadOptions loadOptions = new LoadOptions();
loadOptions.setResourceLoadingTimeout(100);
```

#### ขั้นตอนที่ 3: เริ่มต้น Viewer และเรนเดอร์ JPG

```java
try (Viewer viewer = new Viewer("YOUR_DOCUMENT_DIRECTORY/SAMPLE_PST", loadOptions)) {
    JpgViewOptions options = new JpgViewOptions(pageFilePathFormat);
    viewer.view(options);
}
```

### การเรนเดอร์เอกสาร PST/OST เป็น PNG

#### ขั้นตอนที่ 1: ตั้งค่าไดเรกทอรีผลลัพธ์

```java
Path outputDirectory = Paths.get("YOUR_OUTPUT_DIRECTORY");
Path pageFilePathFormat = outputDirectory.resolve("PST_result_{0}.png");
```

#### ขั้นตอนที่ 2: กำหนดค่า Load Options

```java
LoadOptions loadOptions = new LoadOptions();
loadOptions.setResourceLoadingTimeout(100);
```

#### ขั้นตอนที่ 3: เริ่มต้น Viewer และเรนเดอร์ PNG

```java
try (Viewer viewer = new Viewer("YOUR_DOCUMENT_DIRECTORY/SAMPLE_PST", loadOptions)) {
    PngViewOptions options = new PngViewOptions(pageFilePathFormat);
    viewer.view(options);
}
```

### การเรนเดอร์เอกสาร PST/OST เป็น PDF

#### ขั้นตอนที่ 1: ตั้งค่าไดเรกทอรีผลลัพธ์

```java
Path outputDirectory = Paths.get("YOUR_OUTPUT_DIRECTORY");
Path pageFilePathFormat = outputDirectory.resolve("PST_result.pdf");
```

#### ขั้นตอนที่ 2: กำหนดค่า Load Options

```java
LoadOptions loadOptions = new LoadOptions();
loadOptions.setResourceLoadingTimeout(100);
```

#### ขั้นตอนที่ 3: เริ่มต้น Viewer และเรนเดอร์ PDF

```java
try (Viewer viewer = new Viewer("YOUR_DOCUMENT_DIRECTORY/SAMPLE_PST", loadOptions)) {
    PdfViewOptions options = new PdfViewOptions(pageFilePathFormat);
    viewer.view(options);
}
```

## การประยุกต์ใช้งานจริง

- **Email Archiving:** แปลงคลังเก็บ PST ขนาดใหญ่เป็น HTML หรือ PDF ที่สามารถค้นหาได้เพื่อการปฏิบัติตาม.  
- **Document Management Systems:** เก็บไฟล์ที่แปลงแล้วในระบบที่รับเฉพาะ PDF, PNG หรือ JPG.  
- **Collaboration Platforms:** แชร์อีเมลที่แปลงเป็นรูปภาพใน Slack หรือ Teams.  
- **Legal Review:** ให้ศาลเข้าถึงเวอร์ชัน PDF ของหลักฐานอีเมล.  
- **Backup Strategies:** เก็บภาพสแนปช็อต PNG หรือ JPG ที่มีขนาดเบา ของข้อความสำคัญ.

## การพิจารณาด้านประสิทธิภาพ

- **Resource Management:** ใช้ instance ของ `Viewer` ซ้ำเมื่อประมวลผลหลายไฟล์เพื่อลดภาระ.  
- **Memory Tuning:** ปรับค่า `loadOptions.setResourceLoadingTimeout` ตามความจุของเซิร์ฟเวอร์.  
- **Asynchronous Processing:** ย้ายการแปลงไปทำในเธรดพื้นหลังเพื่อ UI ที่ตอบสนองเร็ว.

## คำถามที่พบบ่อย

**Q: ฉันจะ **convert pst to pdf** ด้วยโค้ดฐานเดียวกันอย่างไร?**  
A: ใช้ `PdfViewOptions` ตามที่แสดงในส่วนการเรนเดอร์ PDF; ส่วนอื่นของโค้ดยังคงเหมือนเดิม.

**Q: GroupDocs.Viewer สามารถจัดการไฟล์ PST ที่เข้ารหัสได้หรือไม่?**  
A: ได้, ให้ระบุรหัสผ่านผ่าน `LoadOptions.setPassword("yourPassword")` ก่อนการเรนเดอร์.

**Q: ความแตกต่างระหว่างการ **java convert pst** ไปเป็น PNG กับ JPG คืออะไร?**  
A: PNG รักษาคุณภาพแบบ lossless เหมาะสำหรับสกรีนช็อต, ส่วน JPG มีขนาดไฟล์เล็กลงสำหรับการพรีวิวอีเมล.

**Q: มีวิธี **how to convert pst** ไฟล์เป็นจำนวนมากหรือไม่?**  
A: ใส่ตรรกะการเรนเดอร์ไว้ในลูปที่วนผ่านไดเรกทอรีของไฟล์ PST; ใช้การกำหนดค่า `Viewer` เดียวกันซ้ำสำหรับแต่ละไฟล์.

## สรุป

คุณมีคู่มือที่ครบถ้วนและพร้อมใช้งานในโปรดักชันเพื่อ **convert pst to html**, JPG, PNG, และ PDF ด้วย GroupDocs.Viewer for Java แล้ว. ด้วยการทำตามขั้นตอนข้างต้นคุณสามารถรวมการแปลงอีเมลเข้าไปในกระบวนการทำงานใด ๆ ที่ใช้ Java, ปรับปรุงการเข้าถึง, และตอบสนองความต้องการด้านการปฏิบัติตามกฎระเบียบ.

---

**อัปเดตล่าสุด:** 2026-02-15  
**ทดสอบกับ:** GroupDocs.Viewer for Java 25.2  
**ผู้เขียน:** GroupDocs