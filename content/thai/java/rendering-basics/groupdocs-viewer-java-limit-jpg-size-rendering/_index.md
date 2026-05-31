---
date: '2026-05-31'
description: เรียนรู้วิธีจำกัดขนาด jpg ใน java ขณะแสดงเอกสารด้วย GroupDocs.Viewer
  สำหรับ Java รวมขั้นตอนการกำหนดค่า ตัวอย่างโค้ด และเคล็ดลับปฏิบัติที่ดีที่สุด
keywords:
- limit jpg size java
- GroupDocs Viewer Java configuration
- image size limits GroupDocs Viewer
schemas:
- author: GroupDocs
  dateModified: '2026-05-31'
  description: Learn how to limit jpg size java when rendering documents with GroupDocs.Viewer
    for Java. Includes configuration steps, code snippets, and best‑practice tips.
  headline: limit jpg size java – Rendering with GroupDocs.Viewer
  type: TechArticle
- description: Learn how to limit jpg size java when rendering documents with GroupDocs.Viewer
    for Java. Includes configuration steps, code snippets, and best‑practice tips.
  name: limit jpg size java – Rendering with GroupDocs.Viewer
  steps:
  - name: '**Web Application Thumbnails** – Faster loading previews for document galleries.'
    text: '**Web Application Thumbnails** – Faster loading previews for document galleries.'
  - name: '**Email Attachments** – Smaller JPGs keep email sizes under common limits
      (e.g., 25 MB).'
    text: '**Email Attachments** – Smaller JPGs keep email sizes under common limits
      (e.g., 25 MB).'
  - name: '**Mobile Apps** – Reduced dimensions lower CPU and GPU load on handheld
      devices, improving responsiveness.'
    text: '**Mobile Apps** – Reduced dimensions lower CPU and GPU load on handheld
      devices, improving responsiveness.'
  type: HowTo
- questions:
  - answer: Choose a `setMaxWidth()` that balances resolution and file size; 400 px
      works well for most preview needs, and you can also set JPEG quality via `setQuality(int)`
      if needed.
    question: How can I keep image quality high while limiting size?
  - answer: GroupDocs.Viewer currently exposes only a width‑based limit. For height
      constraints, process the generated JPGs with an image‑processing library after
      rendering.
    question: Can I also limit the image height?
  - answer: Render them in batches or increase the JVM heap size; the viewer processes
      pages independently, so memory usage scales with the number of concurrent pages,
      not total page count.
    question: What should I do with very large documents?
  - answer: Yes—pass the password to the `Viewer` constructor or use the `loadOptions`
      parameter to unlock the document before rendering.
    question: Does the viewer support password‑protected files?
  - answer: Explore the full API guide at [GroupDocs Documentation](https://docs.groupdocs.com/viewer/java/),
      which lists over 30 rendering settings and format‑specific features.
    question: Where can I find more advanced rendering options?
  type: FAQPage
title: จำกัดขนาด jpg ใน java – การแสดงผลด้วย GroupDocs.Viewer
type: docs
url: /th/java/rendering-basics/groupdocs-viewer-java-limit-jpg-size-rendering/
weight: 1
---

# จำกัดขนาด jpg ใน Java ด้วย GroupDocs.Viewer for Java

ในแอปพลิเคชันเว็บและมือถือสมัยใหม่ การควบคุมขนาดของภาพ JPG ที่สร้างจากเอกสารสามารถปรับปรุงเวลาโหลดได้อย่างมาก ลดค่าใช้จ่ายแบนด์วิดท์ และทำให้พื้นที่จัดเก็บข้อมูลเล็กลง บทเรียนนี้จะแสดง **วิธีจำกัดขนาด jpg ใน Java** ระหว่างการเรนเดอร์ด้วย GroupDocs.Viewer for Java, แนะนำการตั้งค่าที่จำเป็น, และแชร์เคล็ดลับที่คุณสามารถนำไปใช้ได้ทันที

![จำกัดขนาด JPG ในการเรนเดอร์เอกสารด้วย GroupDocs.Viewer for Java](/viewer/rendering-basics/limit-jpg-size-in-document-rendering-java.png)

## คำตอบด่วน
- **“limit jpg size java” ทำอะไร?** มันจำกัดความกว้างของแต่ละภาพหน้าที่เรนเดอร์โดยอัตโนมัติ ลดขนาดไฟล์ขณะยังคงความอ่านได้.  
- **คลาสใดควบคุมขนาด?** `JpgViewOptions.setMaxWidth(int)` ให้คุณกำหนดความกว้างพิกเซลสูงสุด.  
- **ต้องการไลเซนส์หรือไม่?** จำเป็นต้องมีไลเซนส์ GroupDocs.Viewer ที่ถูกต้องสำหรับการใช้งานในโปรดักชัน; มีไลเซนส์ทดลองหรือไลเซนส์ชั่วคราวสำหรับการทดสอบ.  
- **สามารถเรนเดอร์ PDF ได้หรือไม่?** ใช่—GroupDocs.Viewer รองรับรูปแบบเข้า 70+ ประเภท รวมถึง PDF, DOCX, PPTX และอื่น ๆ.  
- **การใช้หน่วยความจำเป็นปัญหาหรือไม่?** การใช้ try‑with‑resources ทำให้ Viewer ปล่อยทรัพยากรเนทีฟอย่างทันท่วงที ลดการใช้หน่วยความจำ.

## limit jpg size java คืออะไร?
**limit jpg size java** เป็นตัวเลือกการกำหนดค่าภายใน GroupDocs.Viewer ที่จำกัดความกว้างพิกเซลของแต่ละภาพ JPG ที่สร้างระหว่างการเรนเดอร์เอกสาร โดยการตั้งค่าความกว้างสูงสุด คุณจะมีผลโดยตรงต่อขนาดไฟล์ที่ได้ ซึ่งสำคัญสำหรับสภาพแวดล้อมที่แบนด์วิดท์จำกัดหรือเมื่อเก็บภาพหลายหน้า.

## ทำไมต้องจำกัดขนาด JPG เมื่อเรนเดอร์เอกสาร?
การจำกัดขนาด JPG ช่วยลดพื้นที่ไฟล์โดยรวม, เร่งความเร็วการโหลดหน้า, และลดการใช้หน่วยความจำระหว่างการเรนเดอร์ ภาพที่เล็กลงใช้แบนด์วิดท์น้อยกว่า, ปรับปรุงประสบการณ์ผู้ใช้บนอุปกรณ์มือถือ, และทำให้การจัดการพื้นที่จัดเก็บมีประสิทธิภาพมากขึ้น โดยเฉพาะเมื่อจัดการเอกสารขนาดใหญ่ที่มีหลายหน้า.

- **การลดขนาดไฟล์:** การเรนเดอร์เอกสาร 300 หน้า ที่ความกว้าง 400 px สามารถลดขนาดภาพรวมได้ถึง 70 % เมื่อเทียบกับความกว้างเริ่มต้น 800 px.  
- **โหลดหน้าที่เร็วขึ้น:** ภาพที่เล็กลงดาวน์โหลดเร็วขึ้น 2‑3 เท่าโดยเฉลี่ยบนการเชื่อมต่อมือถือ.  
- **การใช้หน่วยความจำน้อยลง:** GroupDocs.Viewer ประมวลผลแต่ละหน้าแยกกัน, ดังนั้นการลดขนาดยังช่วยลดบัฟเฟอร์หน่วยความจำชั่วคราว.

## ข้อกำหนดเบื้องต้น
- **GroupDocs.Viewer for Java** เวอร์ชัน 25.2 หรือใหม่กว่า.  
- **Maven** ที่กำหนดค่าไว้ในสภาพแวดล้อมการพัฒนา.  
- ความรู้พื้นฐานของ Java และความคุ้นเคยกับการพึ่งพา Maven.  

## การตั้งค่า GroupDocs.Viewer for Java

เพิ่มการพึ่งพา GroupDocs.Viewer Maven ลงใน `pom.xml` ของคุณ:

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

เพื่อใช้ GroupDocs.Viewer อย่างเต็มที่, คุณสามารถ:
- **ทดลองใช้ฟรี:** ดาวน์โหลดและทดสอบไลบรารีโดยใช้ไลเซนส์ชั่วคราวจาก [GroupDocs Free Trial](https://releases.groupdocs.com/viewer/java/).  
- **ไลเซนส์ชั่วคราว:** รับไลเซนส์ชั่วคราวไม่มีค่าใช้จ่ายสำหรับการทดสอบที่กว้างขวางที่ [GroupDocs Temporary License](https://purchase.groupdocs.com/temporary-license/).  
- **ซื้อไลเซนส์:** สำหรับการใช้งานระยะยาว, ซื้อไลเซนส์ผ่าน [GroupDocs Purchase Page](https://purchase.groupdocs.com/buy).

### การเริ่มต้นพื้นฐาน

เมื่อคุณตั้งค่าสภาพแวดล้อมและติดตั้งการพึ่งพาที่จำเป็นแล้ว, ให้เริ่มต้น GroupDocs.Viewer ในแอปพลิเคชัน Java ของคุณ:

```java
import com.groupdocs.viewer.Viewer;

class DocumentViewer {
    public static void main(String[] args) {
        try (Viewer viewer = new Viewer("path/to/document")) {
            // Your rendering logic here
        }
    }
}
```

## วิธีจำกัดขนาด jpg ใน Java ระหว่างการเรนเดอร์เอกสาร?
`JpgViewOptions` เป็นคลาสที่ระบุตัวเลือกการเรนเดอร์สำหรับผลลัพธ์ JPG. โหลดเอกสารของคุณ, ตั้งค่า `JpgViewOptions` ด้วยความกว้างสูงสุด (เช่น 400 px), แล้วเรียก `view()`—Viewer จะสร้างภาพ JPG ที่ไม่เกินความกว้างที่กำหนด, ปรับสเกลความสูงโดยอัตโนมัติเพื่อรักษาอัตราส่วน. วิธีการสองขั้นตอนนี้รับประกันผลลัพธ์ที่สม่ำเสมอและควบคุมขนาดโดยไม่ต้องทำการประมวลผลต่อ.

### กำหนดไดเรกทอรีและเส้นทางไฟล์ผลลัพธ์

แรกสุด, ระบุที่ที่ไฟล์ JPG ที่เรนเดอร์จะถูกบันทึก:

```java
import java.nio.file.Path;
import java.nio.file.Paths;

Path outputDirectory = Paths.get("YOUR_OUTPUT_DIRECTORY", "RenderDocumentToJPGWithSizeLimit");
Path outputFile = outputDirectory.resolve("result_image_size_limit.jpg");
```

การตั้งค่านี้ช่วยจัดระเบียบผลลัพธ์และทำให้ไฟล์ที่เรนเดอร์เข้าถึงได้ง่าย.

### ตั้งค่า JpgViewOptions

`JpgViewOptions` ให้คุณตั้งค่าพารามิเตอร์ต่าง ๆ เช่น ความกว้างสูงสุด, คุณภาพ, และ DPI สำหรับการเรนเดอร์ JPG.

คลาส `JpgViewOptions` กำหนดตัวเลือกสำหรับการเรนเดอร์หน้าเป็นภาพ JPG, รวมถึงข้อจำกัดขนาดและระดับการบีบอัด.  

สร้าง `JpgViewOptions` และกำหนดขีดจำกัดความกว้างที่ 400 พิกเซล:

```java
import com.groupdocs.viewer.options.JpgViewOptions;

JpgViewOptions options = new JpgViewOptions(outputFile);
options.setMaxWidth(400);  // Set the max width to 400 pixels
```

การจำกัดความกว้างที่ 400 px ทำให้แต่ละภาพหน้าเบาลงในขณะที่ยังคงรายละเอียดเพียงพอสำหรับการพรีวิวทั่วไป.

### เรนเดอร์เอกสาร

คลาส `Viewer` เป็นจุดเริ่มต้นสำหรับการแปลงเอกสารที่รองรับเป็นรูปแบบการดูต่าง ๆ, รวมถึง JPG, PDF, และ HTML.  

ใช้เมธอด `view()` เพื่อประมวลผลเอกสารตามตัวเลือกที่ให้และเขียนไฟล์ JPG ไปยังโฟลเดอร์เป้าหมาย:

```java
import com.groupdocs.viewer.Viewer;

try (Viewer viewer = new Viewer("path/to/your/document")) {
    viewer.view(options);
}
```

## ปัญหาและวิธีแก้ไขทั่วไป
- **ข้อผิดพลาดเส้นทางไฟล์:** ตรวจสอบให้แน่ใจว่าทุกสตริงของไดเรกทอรีเป็นแบบ absolute หรือ relative อย่างถูกต้องต่อรูทโปรเจกต์ของคุณ.  
- **ความเข้ากันได้ของไลบรารี:** ตรวจสอบว่าคุณใช้ GroupDocs.Viewer 25.2 หรือใหม่กว่า; เวอร์ชันเก่าอาจไม่มี `setMaxWidth`.  
- **ข้อยกเว้น Out‑of‑Memory:** เรนเดอร์เอกสารขนาดใหญ่หน้า‑ต่อ‑หน้าในบล็อก try‑with‑resources เพื่อรับประกันว่าทรัพยากรเนทีฟจะถูกปล่อยอย่างทันท่วงที.

## การประยุกต์ใช้ในเชิงปฏิบัติ
การควบคุมขนาดภาพมีประโยชน์ในหลายสถานการณ์จริง:
1. **ภาพย่อสำหรับเว็บแอป** – พรีวิวที่โหลดเร็วสำหรับแกลเลอรีเอกสาร.  
2. **ไฟล์แนบอีเมล** – JPG ที่เล็กลงทำให้ขนาดอีเมลอยู่ภายใต้ขีดจำกัดทั่วไป (เช่น 25 MB).  
3. **แอปมือถือ** – มิติที่ลดลงทำให้ CPU และ GPU บนอุปกรณ์พกพาทำงานน้อยลง, เพิ่มความตอบสนอง.

## พิจารณาด้านประสิทธิภาพ
- **การจัดการหน่วยความจำ:** ห่ออินสแตนซ์ `Viewer` ด้วยคำสั่ง try‑with‑resources เพื่อปิดสตรีมและปล่อยหน่วยความจำเนทีฟโดยอัตโนมัติ.  
- **การปรับความกว้าง:** ปรับ `setMaxWidth()` ตามความต้องการแบนด์วิดท์และคุณภาพ; 300 px เหมาะสำหรับแบนด์วิดท์ต่ำ, ขณะที่ 600 px ให้พรีวิวคมชัดมากขึ้น.

## คำถามที่พบบ่อย

**ถาม: จะรักษาคุณภาพภาพสูงขณะจำกัดขนาดได้อย่างไร?**  
ตอบ: เลือก `setMaxWidth()` ที่สมดุลระหว่างความละเอียดและขนาดไฟล์; 400 px ทำงานได้ดีสำหรับการพรีวิวส่วนใหญ่, และคุณยังสามารถตั้งค่าคุณภาพ JPEG ผ่าน `setQuality(int)` หากต้องการ.

**ถาม: สามารถจำกัดความสูงของภาพได้หรือไม่?**  
ตอบ: GroupDocs.Viewer ปัจจุบันให้จำกัดเฉพาะความกว้างเท่านั้น. หากต้องการข้อจำกัดความสูง, ให้ประมวลผล JPG ที่สร้างแล้วด้วยไลบรารีการประมวลผลภาพต่อไป.

**ถาม: ควรทำอย่างไรกับเอกสารที่ใหญ่มาก?**  
ตอบ: เรนเดอร์เป็นชุดหรือเพิ่มขนาด heap ของ JVM; Viewer ประมวลผลหน้าแยกกัน, ดังนั้นการใช้หน่วยความจำสเกลตามจำนวนหน้าที่ประมวลผลพร้อมกัน, ไม่ใช่จำนวนหน้าทั้งหมด.

**ถาม: Viewer รองรับไฟล์ที่มีรหัสผ่านหรือไม่?**  
ตอบ: ใช่—ส่งรหัสผ่านไปยังคอนสตรัคเตอร์ `Viewer` หรือใช้พารามิเตอร์ `loadOptions` เพื่อปลดล็อกเอกสารก่อนการเรนเดอร์.

**ถาม: จะหา ตัวเลือกการเรนเดอร์ขั้นสูงได้จากที่ไหน?**  
ตอบ: สำรวจคู่มือ API เต็มรูปแบบที่ [GroupDocs Documentation](https://docs.groupdocs.com/viewer/java/), ซึ่งมีการตั้งค่าการเรนเดอร์กว่า 30 รายการและคุณลักษณะเฉพาะรูปแบบ.

## แหล่งข้อมูล
- **เอกสาร:** [GroupDocs Viewer Java Docs](https://docs.groupdocs.com/viewer/java/)  
- **อ้างอิง API:** [GroupDocs API Reference](https://reference.groupdocs.com/viewer/java/)  
- **ดาวน์โหลด:** [GroupDocs Downloads](https://releases.groupdocs.com/viewer/java/)  
- **ซื้อไลเซนส์:** [Buy GroupDocs License](https://purchase.groupdocs.com/buy)  
- **ทดลองใช้ฟรี:** [GroupDocs Free Trial](https://releases.groupdocs.com/viewer/java/)  
- **ไลเซนส์ชั่วคราว:** [GroupDocs Temporary License](https://purchase.groupdocs.com/temporary-license/)  
- **สนับสนุน:** [GroupDocs Forum](https://forum.groupdocs.com/c/viewer/9)

**อัปเดตล่าสุด:** 2026-05-31  
**ทดสอบด้วย:** GroupDocs.Viewer 25.2 for Java  
**ผู้เขียน:** GroupDocs

## บทเรียนที่เกี่ยวข้อง

- [วิธีเรนเดอร์ pdf เป็น html และปรับคุณภาพภาพใน Java ด้วย GroupDocs.Viewer](/viewer/java/advanced-rendering/adjust-image-quality-groupdocs-viewer-java/)  
- [ลดขนาด PDF ใน Java – ปรับคุณภาพ JPG ด้วย GroupDocs](/viewer/java/advanced-rendering/optimize-jpg-quality-groupdocs-viewer-java/)  
- [การเรนเดอร์ HTML แบบตอบสนองด้วย GroupDocs.Viewer for Java: คู่มือฉบับสมบูรณ์](/viewer/java/advanced-rendering/groupdocs-viewer-java-responsive-html-rendering/)