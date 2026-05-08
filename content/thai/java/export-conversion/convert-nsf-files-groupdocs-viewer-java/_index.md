---
date: '2026-02-13'
description: เรียนรู้วิธีแปลงไฟล์ nsf เป็น pdf และรูปแบบอื่น ๆ (HTML, JPG, PNG) ด้วย GroupDocs.Viewer สำหรับ Java 
  คู่มือขั้นตอนนี้แสดงวิธีแปลงไฟล์ nsf อย่างมีประสิทธิภาพ.
keywords:
- GroupDocs.Viewer Java
- NSF Document Conversion
- Convert NSF Files
title: แปลง NSF เป็น PDF, HTML, JPG, PNG ด้วย GroupDocs.Viewer สำหรับ Java
type: docs
url: /th/java/export-conversion/convert-nsf-files-groupdocs-viewer-java/
weight: 1
---

# แปลงไฟล์ NSF ไปยังหลายรูปแบบด้วย GroupDocs.Viewer for Java

การแปลงเอกสาร NSF ให้เป็นรูปแบบต่าง ๆ เช่น HTML, JPG, PNG หรือ PDF ด้วย Java ทำได้ง่ายด้วย GroupDocs.Viewer for Java. **บทแนะนำนี้จะแสดงวิธีแปลง nsf เป็น pdf** และรูปแบบอื่น ๆ ที่เป็นประโยชน์ พร้อมขั้นตอนการตั้งค่า การใช้งาน และเคล็ดลับการปฏิบัติที่ดีที่สุด

![แปลงไฟล์ NSF ไปเป็น HTML, JPG, PNG และ PDF ด้วย GroupDocs.Viewer for Java](/viewer/export-conversion/convert-nsf-files-to-html-jpg-png-pdf-java.png)

## คำตอบสั้น ๆ
- **กรณีการใช้งานหลักคืออะไร?** การแสดงผลไฟล์ NSF เป็น PDF, HTML, JPG หรือ PNG สำหรับเว็บ, การเก็บถาวร หรือการแชร์  
- **ไลบรารีใดรับผิดชอบการแปลง?** GroupDocs.Viewer for Java  
- **ต้องมีลิขสิทธิ์หรือไม่?** มีรุ่นทดลองฟรี; ต้องมีลิขสิทธิ์เต็มสำหรับการใช้งานในโปรดักชัน  
- **ต้องใช้ Java เวอร์ชันใด?** JDK 8 หรือใหม่กว่า  
- **สามารถประมวลผลหลายไฟล์ NSF พร้อมกันได้หรือไม่?** ได้ – เพียงใส่ตรรกะการแสดงผลในลูปและจัดการทรัพยากรด้วย try‑with‑resources  

## “convert nsf to pdf” คืออะไร?

การแปลงไฟล์ NSF (ฐานข้อมูล Lotus Notes) เป็น PDF จะสร้างเอกสารแบบคงที่ที่รองรับอย่างกว้างขวาง ซึ่งสามารถเปิดได้บนอุปกรณ์ใด ๆ โดยไม่ต้องใช้ไคลเอนต์ Notes ดั้งเดิม การแปลงนี้มีประโยชน์สำหรับการเก็บถาวร การปฏิบัติตามกฎหมาย และการกระจายที่ง่ายดาย

## ทำไมต้องแปลง NSF เป็น PDF และรูปแบบอื่น ๆ?

- **การเข้าถึงสากล:** PDF, HTML, JPG, และ PNG สามารถอ่านได้บนแพลตฟอร์มเกือบทุกประเภท  
- **รักษาเลย์เอาต์:** PDF คงรูปแบบหน้า, ฟอนต์, และกราฟิกเดิมไว้  
- **การรวมเข้ากับเว็บ:** HTML ทำให้ดูในเบราว์เซอร์ได้อย่างรวดเร็วโดยไม่ต้องใช้ปลั๊กอินเพิ่มเติม  
- **การสกัดภาพ:** JPG/PNG เหมาะสำหรับภาพย่อ, ตัวอย่าง, หรือการฝังในแอปพลิเคชันอื่น  

## ข้อกำหนดเบื้องต้น

ก่อนเริ่มใช้งาน GroupDocs.Viewer for Java ให้ตรวจสอบว่าคุณมีสิ่งต่อไปนี้:

1. **ไลบรารีและการพึ่งพา:**  
   - Maven (สำหรับการจัดการการพึ่งพา)  
   - JDK 8 หรือใหม่กว่า ติดตั้งบนระบบของคุณ  

2. **การตั้งค่าสภาพแวดล้อม:**  
   - ความเข้าใจพื้นฐานเกี่ยวกับการเขียนโปรแกรม Java  
   - ความคุ้นเคยกับ Maven สำหรับการตั้งค่าโครงการ  

3. **ความรู้พื้นฐานที่จำเป็น:**  
   - การจัดการไฟล์ใน Java ขั้นพื้นฐาน  
   - แนวคิดการแปลงเอกสาร  

## การตั้งค่า GroupDocs.Viewer for Java

### การกำหนดค่า Maven

เพิ่ม GroupDocs.Viewer ลงในโครงการ Java ของคุณโดยใส่การกำหนดค่าต่อไปนี้ในไฟล์ `pom.xml` ของคุณ:

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

### การขอรับลิขสิทธิ์

เพื่อใช้ GroupDocs.Viewer คุณสามารถ:

- **รุ่นทดลองฟรี:** เข้าถึงฟังก์ชันพื้นฐานเพื่อประเมินเครื่องมือ  
- **ลิขสิทธิ์ชั่วคราว:** รับลิขสิทธิ์ชั่วคราวสำหรับฟีเจอร์เต็ม  
- **ซื้อ:** พิจารณาซื้อลิขสิทธิ์สำหรับสภาพแวดล้อมการผลิต  

### การเริ่มต้นพื้นฐาน

เริ่มต้น GroupDocs.Viewer ดังนี้:

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

ส่วนต่อไปนี้จะแสดงวิธีแสดงผลไฟล์ NSF เป็น HTML, JPG, PNG, **และ PDF** ตัวอย่าง PDF ตรงกับคีย์เวิร์ดหลัก “convert nsf to pdf”

### การแปลง NSF เป็น HTML

#### ภาพรวม
แปลงเอกสาร NSF ให้เป็นรูปแบบ HTML โดยฝังทรัพยากรภายในไฟล์ HTML เพื่อการดูบนเว็บที่ง่ายดาย

#### คู่มือขั้นตอน

**1. ตั้งค่าไดเรกทอรีและเส้นทางไฟล์ผลลัพธ์**  
กำหนดตำแหน่งที่ไฟล์ HTML ผลลัพธ์จะถูกจัดเก็บ

```java
import java.nio.file.Path;
import java.nio.file.Paths;

Path outputDirectory = Paths.get("YOUR_OUTPUT_DIRECTORY");
Path pageFilePathFormat = outputDirectory.resolve("NSF_result.html");
```

**2. กำหนดค่า Load Options**  
ปรับแต่งกระบวนการโหลดด้วยตัวเลือกเฉพาะ เช่น เวลาหมดของการโหลดทรัพยากร

```java
import com.groupdocs.viewer.options.LoadOptions;

LoadOptions loadOptions = new LoadOptions();
loadOptions.setResourceLoadingTimeout(100);  // Set timeout for loading resources.
```

**3. เริ่มต้น Viewer และทำการแสดงผล**  
ใช้คลาส Viewer เพื่อแปลงเอกสารของคุณเป็นรูปแบบ HTML

```java
import com.groupdocs.viewer.Viewer;
import com.groupdocs.viewer.options.HtmlViewOptions;

try (Viewer viewer = new Viewer("YOUR_DOCUMENT_DIRECTORY/SAMPLE_NSF", loadOptions)) {
    HtmlViewOptions options = HtmlViewOptions.forEmbeddedResources(pageFilePathFormat);
    viewer.view(options);  // Render the document to HTML.
}
```

### การแปลง NSF เป็น JPG

#### ภาพรวม
แปลงเอกสาร NSF ให้เป็นภาพ JPG คุณภาพสูงสำหรับการแชร์หรือรวมเข้ากับระบบที่ใช้ภาพ

**1. กำหนดเส้นทางผลลัพธ์**  
ตั้งค่ารูปแบบเส้นทางไฟล์สำหรับจัดเก็บ JPG ที่แปลงแล้ว

```java
Path pageFilePathFormat = outputDirectory.resolve("NSF_result_{0}.jpg");
```

**2. กำหนดค่าและทำการแปลง**  
ตั้งค่า Viewer ของคุณและแปลงเอกสารเป็นภาพ JPEG

```java
import com.groupdocs.viewer.options.JpgViewOptions;

try (Viewer viewer = new Viewer("YOUR_DOCUMENT_DIRECTORY/SAMPLE_NSF", loadOptions)) {
    JpgViewOptions options = new JpgViewOptions(pageFilePathFormat);
    viewer.view(options);  // Render to JPG.
}
```

### การแปลง NSF เป็น PNG

#### ภาพรวม
แปลงเอกสารเป็นรูปแบบ PNG ซึ่งเป็นที่รู้จักสำหรับการบีบอัดแบบไม่มีการสูญเสียและความละเอียดสูง

**1. ตั้งค่าเส้นทางผลลัพธ์**

```java
Path pageFilePathFormat = outputDirectory.resolve("NSF_result_{0}.png");
```

**2. แปลงเอกสาร**

```java
import com.groupdocs.viewer.options.PngViewOptions;

try (Viewer viewer = new Viewer("YOUR_DOCUMENT_DIRECTORY/SAMPLE_NSF", loadOptions)) {
    PngViewOptions options = new PngViewOptions(pageFilePathFormat);
    viewer.view(options);  // Convert to PNG.
}
```

### การแปลง NSF เป็น PDF

#### ภาพรวม
แปลงเอกสาร NSF ให้เป็นรูปแบบ PDF ซึ่งเป็นมาตรฐานเอกสารที่ได้รับการยอมรับทั่วโลก

**1. กำหนดเส้นทางผลลัพธ์**

```java
Path pageFilePathFormat = outputDirectory.resolve("NSF_result.pdf");
```

**2. แปลงเป็น PDF**

```java
import com.groupdocs.viewer.options.PdfViewOptions;

try (Viewer viewer = new Viewer("YOUR_DOCUMENT_DIRECTORY/SAMPLE_NSF", loadOptions)) {
    PdfViewOptions options = new PdfViewOptions(pageFilePathFormat);
    viewer.view(options);  // Convert to PDF.
}
```

## การประยุกต์ใช้งานจริง

1. **การแชร์เอกสารบนเว็บ:** แปลงไฟล์ NSF เป็น HTML เพื่อการแชร์ที่ง่ายบนแพลตฟอร์มเว็บ  
2. **การเก็บภาพเอกสาร:** เก็บภาพคุณภาพสูงของเอกสารในรูปแบบ JPG หรือ PNG  
3. **การเข้าถึงเอกสารสากล:** ใช้การแปลงเป็น PDF เพื่อความเข้ากันได้ของเอกสารบนอุปกรณ์ทุกประเภท  

## พิจารณาด้านประสิทธิภาพ

- **ปรับการโหลดทรัพยากร:** ปรับ `setResourceLoadingTimeout` ตามความสามารถของระบบของคุณ  
- **การจัดการหน่วยความจำ:** ให้แน่ใจว่าการใช้หน่วยความจำมีประสิทธิภาพโดยจัดการอินสแตนซ์ Viewer อย่างถูกต้องด้วย try‑with‑resources  
- **การประมวลผลเป็นชุด:** สำหรับการแปลงในระดับใหญ่ ควรพิจารณาประมวลผลเอกสารเป็นชุดเพื่อควบคุมการใช้ทรัพยากร  

## ส่วนคำถามที่พบบ่อย (FAQ)

1. **รูปแบบที่ดีที่สุดสำหรับการแปลงไฟล์ NSF คืออะไร?**  
   - ขึ้นอยู่กับความต้องการของคุณ: HTML สำหรับการดูบนเว็บ, PDF สำหรับการเข้าถึงสากล, JPG/PNG สำหรับรูปภาพ  

2. **จะจัดการไฟล์ NSF ขนาดใหญ่อย่างมีประสิทธิภาพอย่างไร?**  
   - ปรับตัวเลือกการโหลดและประมวลผลเป็นชุด  

3. **สามารถปรับคุณภาพของผลลัพธ์ในรูปแบบภาพได้หรือไม่?**  
   - ได้, ปรับพารามิเตอร์เช่นความละเอียดเมื่อกำหนด `JpgViewOptions` หรือ `PngViewOptions`  

4. **ถ้าการแปลงล้มเหลวควรทำอย่างไร?**  
   - ตรวจสอบเส้นทางไฟล์, ตรวจสอบการตั้งค่า Viewer อย่างถูกต้อง, และอ้างอิงเอกสารของ GroupDocs เพื่อแก้ไขปัญหา  

5. **มีวิธีอัตโนมัติการแปลงเหล่านี้ในกระบวนการแบบ batch หรือไม่?**  
   - แน่นอน! การวนลูปผ่านหลายเอกสารสามารถทำให้กระบวนการอัตโนมัติได้อย่างมีประสิทธิภาพ  

## คำถามที่พบบ่อยเพิ่มเติม

**ถาม: จะทำอย่างไรให้แปลงไฟล์ NSF เป็น PDF โดยไม่สูญเสียหมายเหตุ?**  
ตอบ: GroupDocs.Viewer จะรักษาหมายเหตุส่วนใหญ่ระหว่างขั้นตอน `PdfViewOptions` ทำให้ PDF ที่ได้ตรงกับเลย์เอาต์ต้นฉบับ

**ถาม: สามารถแปลงไฟล์ NSF ที่มีการป้องกันด้วยรหัสผ่านได้หรือไม่?**  
ตอบ: ได้. ส่งข้อมูลรับรองที่เหมาะสมผ่าน `LoadOptions` ก่อนการเริ่มต้น Viewer

**ถาม: แนะนำให้ใช้ Java เวอร์ชันใดเพื่อประสิทธิภาพที่ดีที่สุด?**  
ตอบ: JDK 11 หรือใหม่กว่าให้การจัดการ garbage‑collection และการทำงานพร้อมกันที่ดีขึ้น ซึ่งเป็นประโยชน์ต่อการแปลงเป็นชุด

**ถาม: สามารถตั้งค่า DPI แบบกำหนดเองสำหรับผลลัพธ์ JPG/PNG ได้หรือไม่?**  
ตอบ: สามารถปรับ DPI ได้โดยกำหนดค่าใน `JpgViewOptions` หรือ `PngViewOptions` ก่อนเรียก `viewer.view(options)`

**ถาม: GroupDocs.Viewer รองรับการสตรีมผลลัพธ์โดยตรงไปยังการตอบสนองเว็บหรือไม่?**  
ตอบ: รองรับ. แทนการเขียนไปยังเส้นทางไฟล์ คุณสามารถใช้ overload ของ `Stream` ใน view options เพื่อส่งผลลัพธ์โดยตรงไปยัง HTTP response

## สรุป

คู่มือนี้ได้อธิบายวิธี **แปลง nsf เป็น pdf** และรูปแบบอื่น ๆ ด้วย GroupDocs.Viewer for Java โดยทำตามขั้นตอนเหล่านี้ คุณสามารถรวมความสามารถในการแปลงเอกสารเข้าไปในแอปพลิเคชันของคุณได้อย่างราบรื่น สำรวจฟีเจอร์เพิ่มเติมของ GroupDocs.Viewer และพิจารณานำไปใช้ในโครงการของคุณเพื่อการจัดการเอกสารที่ครบวงจร

---

**อัปเดตล่าสุด:** 2026-02-13  
**ทดสอบกับ:** GroupDocs.Viewer 25.2  
**ผู้เขียน:** GroupDocs