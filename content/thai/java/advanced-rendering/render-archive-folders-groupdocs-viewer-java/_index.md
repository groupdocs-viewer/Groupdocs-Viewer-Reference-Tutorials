---
date: '2026-08-24'
description: เรียนรู้วิธีแปลง zip เป็น HTML ด้วย GroupDocs.Viewer for Java และแสดงโฟลเดอร์
  zip เฉพาะในแอปพลิเคชันของคุณ
keywords:
- render archive folders
- GroupDocs.Viewer for Java
- rendering specific folders in archives
lastmod: '2026-08-24'
og_description: การแปลง zip เป็น HTML ด้วย GroupDocs.Viewer for Java ช่วยให้คุณแสดงโฟลเดอร์
  archive โดยตรงเป็นหน้าเว็บที่เป็นมิตร ลดเวลาการสกัดและลดภาระ I/O คู่มือฉบับนี้แสดงการตั้งค่า
  การกำหนดเป้าหมายโฟลเดอร์ และเคล็ดลับด้านประสิทธิภาพ
og_image_alt: GroupDocs.Viewer Java rendering of archive folders to HTML
og_title: แปลง zip เป็น HTML ด้วย GroupDocs.Viewer for Java
schemas:
- author: GroupDocs
  dateModified: '2026-08-24'
  description: Learn how to convert zip to HTML using GroupDocs.Viewer for Java and
    render specific zip folders in your applications.
  headline: How to convert zip to HTML and render zip folders in Java with GroupDocs.Viewer
  type: TechArticle
- description: Learn how to convert zip to HTML using GroupDocs.Viewer for Java and
    render specific zip folders in your applications.
  name: How to convert zip to HTML and render zip folders in Java with GroupDocs.Viewer
  steps:
  - name: '**Document management systems** – Show only the relevant part of a large
      archive without exposing everything.'
    text: '**Document management systems** – Show only the relevant part of a large
      archive without exposing everything.'
  - name: '**Digital libraries** – Stream selected sections of e‑books or research
      collections directly in the browser.'
    text: '**Digital libraries** – Stream selected sections of e‑books or research
      collections directly in the browser.'
  - name: '**Legal review platforms** – Focus on specific case folders inside massive
      zip bundles, saving time and storage.'
    text: '**Legal review platforms** – Focus on specific case folders inside massive
      zip bundles, saving time and storage.'
  type: HowTo
- questions:
  - answer: It is a library that allows developers to render documents—including archives—directly
      within Java applications.
    question: What is GroupDocs.Viewer for Java?
  - answer: Add the repository and dependency configurations to your `pom.xml` file
      as shown in the Maven configuration section.
    question: How do I install GroupDocs.Viewer using Maven?
  - answer: A free trial is available but production deployments require a licensed
      version.
    question: Can I use GroupDocs.Viewer for free?
  - answer: Ensure the folder name matches exactly (case‑sensitive) and that the archive
      is not password‑protected unless you supply credentials.
    question: What are common issues when rendering archives?
  - answer: Visit the [GroupDocs Forum](https://forum.groupdocs.com/c/viewer/9) for
      community assistance or consult the official documentation.
    question: Where can I get support if needed?
  type: FAQPage
tags:
- convert zip to HTML
- GroupDocs Viewer
- Java archive rendering
- zip folder extraction
- document conversion
title: วิธีแปลง zip เป็น HTML และแสดงโฟลเดอร์ zip ใน Java ด้วย GroupDocs.Viewer
type: docs
url: /th/java/advanced-rendering/render-archive-folders-groupdocs-viewer-java/
weight: 1
---

# วิธีแปลง zip เป็น HTML และแสดงโฟลเดอร์ zip ใน Java ด้วย GroupDocs.Viewer

ในคู่มือนี้คุณจะได้เรียนรู้ **วิธีแปลง zip เป็น HTML** และแสดงเฉพาะโฟลเดอร์ที่คุณต้องการจากไฟล์ ZIP โดยใช้ GroupDocs.Viewer สำหรับ Java. เมื่อจบบทเรียนคุณจะเข้าใจว่าทำไมวิธีนี้จึงลดภาระ I/O, วิธีกำหนดค่า viewer ให้มุ่งเป้าไปที่โฟลเดอร์เดียว, และการปรับแต่งประสิทธิภาพที่ทำให้แอปพลิเคชันของคุณตอบสนองได้แม้กับไฟล์อาร์ไคฟ์ขนาดใหญ่.

![การแสดงโฟลเดอร์อาร์ไคฟ์ด้วย GroupDocs.Viewer สำหรับ Java](/viewer/advanced-rendering/rendering-archive-folders-java.png)

[การแสดงโฟลเดอร์อาร์ไคฟ์ด้วย GroupDocs.Viewer สำหรับ Java](/viewer/advanced-rendering/rendering-archive-folders-java.png)

## คำตอบด่วน
- **“convert zip to HTML” หมายถึงอะไร?** หมายถึงการแปลงเนื้อหาของไฟล์ ZIP (หรือโฟลเดอร์เฉพาะภายใน) ให้เป็นหน้า HTML ที่เหมาะกับเว็บ.  
- **ไลบรารีใดจัดการเรื่องนี้?** GroupDocs.Viewer สำหรับ Java มีความสามารถในการแสดงผลอาร์ไคฟ์ในตัว.  
- **ฉันต้องการไลเซนส์หรือไม่?** การทดลองใช้ฟรีเพียงพอสำหรับการประเมิน; ต้องมีไลเซนส์เต็มสำหรับการใช้งานจริง.  
- **ฉันสามารถแสดงผลเพียงโฟลเดอร์เดียวได้หรือไม่?** ได้ – ใช้ `ArchiveOptions.setFolder("YourFolder")` เพื่อกำหนดโฟลเดอร์เดียว.  
- **ต้องการเวอร์ชัน Java ใด?** Java 8 หรือสูงกว่า.

## วิธีแปลง zip เป็น HTML ด้วย GroupDocs.Viewer

โหลดไฟล์ ZIP ของคุณและขอให้ viewer สร้างผลลัพธ์เป็น HTML – viewer จะสกัดไฟล์ที่ร้องขอในหน่วยความจำและเขียนหน้า HTML ที่พร้อมแสดงไปยังตำแหน่งที่คุณระบุ. วิธีนี้ทำให้ไม่ต้องทำขั้นตอน unzip แยกต่างหากและลดการใช้ดิสก์ชั่วคราว.

## “how to render zip” คืออะไรกับ GroupDocs.Viewer?

GroupDocs.Viewer เป็นไลบรารี Java ที่แปลงประเภทเอกสารหลากหลาย—including อาร์ไคฟ์ที่บีบอัด—ให้เป็นรูปแบบที่เหมาะกับเว็บ. เมื่อคุณต้องการแสดงเฉพาะส่วนของไฟล์ ZIP (เช่น โฟลเดอร์ที่มีรูปภาพหรือ PDF) viewer จะให้คุณแยกและแสดงโฟลเดอร์นั้นโดยไม่ต้องสกัดอาร์ไคฟ์ทั้งหมด.

**คำตอบโดยตรง:** GroupDocs.Viewer อ่านไฟล์ ZIP, เลือกโฟลเดอร์ที่คุณระบุผ่าน `ArchiveOptions`, และสตรีมแต่ละไฟล์เป็นหน้า HTML, ดังนั้นคุณจะได้มุมมองเว็บที่สามารถเรียกดูได้ของโฟลเดอร์นั้นในขั้นตอนเดียว.

## ทำไมต้องใช้ GroupDocs.Viewer สำหรับการแสดงโฟลเดอร์ zip?

GroupDocs.Viewer ประมวลผลอาร์ไคฟ์โดยตรงในหน่วยความจำ, ทำให้ไม่ต้องสกัดเต็มรูปแบบและรักษาข้อมูลที่สำคัญให้อยู่ไกลจากระบบไฟล์. มันสตรีมแต่ละไฟล์, แปลงเป็น HTML, และรองรับอาร์ไคฟ์ขนาดใหญ่, ให้วิธีที่เร็วและปลอดภัยในการแสดงเฉพาะเนื้อหาโฟลเดอร์ที่ต้องการ.

**ประโยชน์ที่วัดได้**
- **ความเร็ว:** การแสดงผลโดยตรงมักเร็วกว่า 2‑3× เทียบกับกระบวนการสองขั้นตอน unzip‑แล้ว‑แปลง.  
- **การใช้หน่วยความจำ:** viewer สตรีมข้อมูล, ทำให้สามารถประมวลผลอาร์ไคฟ์ขนาดถึง 5 GB บน JVM ที่มี heap 2 GB.  
- **การสนับสนุนรูปแบบ:** รองรับรูปแบบเข้าและออกกว่า 50 รูปแบบ, รวมถึง DOCX, PDF, PPTX, HTML, และประเภทภาพทั่วไป.  
- **ความปลอดภัย:** ไม่มีไฟล์กลางถูกเขียนลงเว้นแต่คุณเลือกโฟลเดอร์ผลลัพธ์อย่างชัดเจน, ลดพื้นที่โจมตีจากอาร์ไคฟ์ที่เป็นอันตราย.

## ข้อกำหนดเบื้องต้น
- **Java Development Kit (JDK)** 8 หรือใหม่กว่า.  
- **Maven** สำหรับการจัดการ dependencies.  
- ความคุ้นเคยพื้นฐานกับแนวคิดการเขียนโปรแกรม Java.  

## การตั้งค่า GroupDocs.Viewer สำหรับ Java

### การกำหนดค่า Maven

เพิ่มรีโพซิทอรีของ GroupDocs และ dependency ของ Viewer ลงในไฟล์ `pom.xml` ของคุณ. ขั้นตอนนี้จะดึงเวอร์ชันเสถียรล่าสุดของไลบรารีและ dependencies ที่ตามมา.

**Definition anchor:** `GroupDocs.Viewer` เป็นคลาสหลักที่จัดการการโหลดเอกสาร, การแสดงผล, และการสร้างผลลัพธ์สำหรับรูปแบบที่รองรับทั้งหมด.

### การรับไลเซนส์

เพื่อเปิดศักยภาพเต็มของ GroupDocs.Viewer, คุณสามารถรับ [การทดลองใช้ฟรี](https://releases.groupdocs.com/viewer/java/) หรือรับไลเซนส์ชั่วคราวผ่าน [หน้าลิขสิทธิ์ชั่วคราว](https://purchase.groupdocs.com/temporary-license/). สำหรับโครงการระยะยาว, ควรพิจารณาซื้อไลเซนส์เต็ม.

## การเริ่มต้นพื้นฐาน

หลังจาก Maven แก้ไขแพ็กเกจแล้ว, สร้างอินสแตนซ์ `Viewer` ที่ชี้ไปยังไฟล์ ZIP ที่คุณต้องการประมวลผล. viewer จะจัดการการทำงานระดับต่ำของอาร์ไคฟ์ทั้งหมดให้คุณ.

## วิธีสกัดโฟลเดอร์จาก zip ด้วย GroupDocs.Viewer

เมื่อคุณต้องการเพียงไดเรกทอรีเฉพาะภายในอาร์ไคฟ์, คุณสามารถบอก viewer ว่าโฟลเดอร์ใดที่จะประมวลผล. การดำเนินการ **extract folder from zip** นี้เกิดขึ้นในหน่วยความจำ, ดังนั้นคุณจะหลีกเลี่ยงภาระของการสกัดด้วยมือ.

**คำตอบโดยตรง:** เรียก `viewer.view(zipPath, HtmlViewOptions.forFolder("TargetFolder"))` – viewer จะอ่านอาร์ไคฟ์, แยก `TargetFolder`, และเขียนแต่ละไฟล์เป็นหน้า HTML ไปยังไดเรกทอรีผลลัพธ์ที่คุณระบุ.

### กำหนดเส้นทางผลลัพธ์

สร้างเมธอดช่วยเหลือที่ชี้ไปยังไดเรกทอรีที่ไฟล์ HTML ที่แสดงผลจะถูกบันทึก. เมธอดนี้จะคืนค่าเส้นทางระบบไฟล์ที่สมบูรณ์และตรวจสอบให้แน่ใจว่าโฟลเดอร์มีอยู่ก่อนการเริ่มแสดงผล.

### แสดงผลโฟลเดอร์เฉพาะ

กำหนดค่า viewer ให้มุ่งเป้าไปที่โฟลเดอร์เฉพาะภายในอาร์ไคฟ์และสร้างผลลัพธ์เป็น HTML. `ArchiveOptions.setFolder` ระบุโฟลเดอร์ภายในอาร์ไคฟ์ที่ต้องการแสดงผล. การเรียก `ArchiveOptions.setFolder(...)` จะแยกโฟลเดอร์, ในขณะที่ `HtmlViewOptions` ควบคุมพฤติกรรมการแสดงผล HTML.

**Definition anchor:** `HtmlViewOptions` เป็นอ็อบเจกต์การกำหนดค่าที่ให้คุณปรับแต่งผลลัพธ์ HTML, เช่น การตั้งชื่อหน้า, การจัดการภาพ, และการรวม CSS.

**พารามิเตอร์สำคัญที่อธิบาย**
- `pageFilePathFormat`: ควบคุมรูปแบบการตั้งชื่อสำหรับแต่ละหน้า HTML ที่แสดงผล.  
- `viewOptions.getArchiveOptions().setFolder(...)`: ชี้ให้ viewer แสดงผลเฉพาะโฟลเดอร์ที่ระบุภายในไฟล์ ZIP.

### การกำหนดเส้นทางแบบกำหนดเองสำหรับไดเรกทอรีผลลัพธ์

หากคุณต้องการตำแหน่งผลลัพธ์ที่ต่างออกไป, เพียงปรับเมธอดช่วยเหลือที่สร้างเส้นทางผลลัพธ์. ความยืดหยุ่นนี้ทำให้คุณสามารถเก็บไฟล์ที่แสดงผลไว้พร้อมกับทรัพยากรอื่นหรือในตำแหน่งชั่วคราวเพื่อการประมวลผลต่อไป.

## การประยุกต์ใช้งานจริง
1. **ระบบจัดการเอกสาร** – แสดงเฉพาะส่วนที่เกี่ยวข้องของอาร์ไคฟ์ขนาดใหญ่โดยไม่เปิดเผยทั้งหมด.  
2. **ห้องสมุดดิจิทัล** – สตรีมส่วนที่เลือกของ e‑books หรือคอลเลกชันการวิจัยโดยตรงในเบราว์เซอร์.  
3. **แพลตฟอร์มตรวจสอบกฎหมาย** – มุ่งเน้นที่โฟลเดอร์คดีเฉพาะภายใน zip ขนาดใหญ่, ประหยัดเวลาและพื้นที่จัดเก็บ.  

## ข้อควรพิจารณาด้านประสิทธิภาพ
- **การจัดการหน่วยความจำ:** สำหรับไฟล์ ZIP ขนาดใหญ่มาก, เพิ่มขนาด heap ของ JVM (`-Xmx4g`) หรือประมวลผลโฟลเดอร์เป็นชุดย่อยโดยใช้การแบ่งหน้า.  
- **ประสิทธิภาพ I/O:** เขียนไฟล์ที่แสดงผลไปยัง SSD ที่เร็วหรือไดรฟ์ที่เมานท์ผ่านเครือข่ายเพื่อ ลดความหน่วง.  
- **ตัวเลือกการแสดงผล:** ปรับคุณภาพภาพ (`HtmlViewOptions.setImageQuality(80)`) หรือเปิดการย่อ HTML (`HtmlViewOptions.setMinifyHtml(true)`) เพื่อสมดุลระหว่างความเร็วและความคมชัดของภาพ.  

## สรุป

ตอนนี้คุณรู้ **วิธีแปลง zip เป็น HTML** และแสดงโฟลเดอร์ zip ใน Java ด้วย GroupDocs.Viewer—ตั้งแต่การตั้งค่า Maven ไปจนถึงการมุ่งเป้าไปที่โฟลเดอร์เดียวภายในอาร์ไคฟ์และการจัดการข้อกังวลด้านประสิทธิภาพ. นำขั้นตอนเหล่านี้ไปผสานในแอปพลิเคชันของคุณเพื่อให้การเข้าถึงเนื้อหาอาร์ไคฟ์เป็นไปอย่างเร็ว, ปลอดภัย, และเป็นมิตรกับผู้ใช้.

### ขั้นตอนต่อไป
สำรวจคุณลักษณะเพิ่มเติมของ GroupDocs.Viewer เช่น การแปลง PDF, การใส่ลายน้ำ, หรือการแสดงผลหลายหน้า เพื่อเพิ่มคุณค่าให้กับกระบวนการประมวลผลเอกสารของคุณ.

## คำถามที่พบบ่อย

**Q: GroupDocs.Viewer สำหรับ Java คืออะไร?**  
A: เป็นไลบรารีที่ให้ผู้พัฒนาสามารถแสดงผลเอกสาร—including อาร์ไคฟ์—โดยตรงในแอปพลิเคชัน Java.

**Q: ฉันจะติดตั้ง GroupDocs.Viewer ด้วย Maven อย่างไร?**  
A: เพิ่มการกำหนดค่ารีโพซิทอรีและ dependency ลงในไฟล์ `pom.xml` ของคุณตามที่แสดงในส่วนการกำหนดค่า Maven.

**Q: ฉันสามารถใช้ GroupDocs.Viewer ฟรีได้หรือไม่?**  
A: มีการทดลองใช้ฟรี แต่การใช้งานในสภาพแวดล้อมการผลิตต้องมีไลเซนส์.

**Q: ปัญหาทั่วไปเมื่อแสดงผลอาร์ไคฟ์คืออะไร?**  
A: ตรวจสอบให้แน่ใจว่าชื่อโฟลเดอร์ตรงกันอย่างแม่นยำ (แยกแยะตัวพิมพ์) และอาร์ไคฟ์ไม่ได้ถูกป้องกันด้วยรหัสผ่านหากคุณไม่ได้ให้ข้อมูลประจำตัว.

**Q: ฉันจะหาแหล่งสนับสนุนได้จากที่ไหนหากต้องการ?**  
A: เยี่ยมชม [GroupDocs Forum](https://forum.groupdocs.com/c/viewer/9) เพื่อรับความช่วยเหลือจากชุมชนหรือดูเอกสารอย่างเป็นทางการ.

## แหล่งข้อมูล
- [เอกสารประกอบ](https://docs.groupdocs.com/viewer/java/)
- [อ้างอิง API](https://reference.groupdocs.com/viewer/java/)
- [ดาวน์โหลด GroupDocs.Viewer](https://releases.groupdocs.com/viewer/java/)
- [ซื้อไลเซนส์](https://purchase.groupdocs.com/buy)
- [ทดลองใช้ฟรี](https://releases.groupdocs.com/viewer/java/)
- [ไลเซนส์ชั่วคราว](https://purchase.groupdocs.com/temporary-license/)
- [ฟอรั่มสนับสนุน](https://forum.groupdocs.com/c/viewer/9)

---

**อัปเดตล่าสุด:** 2026-08-24  
**ทดสอบด้วย:** GroupDocs.Viewer 25.2 for Java  
**ผู้เขียน:** GroupDocs

```xml
<repositories>
   <repository>
      <id>groupdocs-repo</id>
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

```java
import com.groupdocs.viewer.Viewer;

try (Viewer viewer = new Viewer("path/to/archive.zip")) {
    // Rendering logic goes here
}
```

```java
import java.nio.file.Path;
import java.nio.file.Paths;

public static Path definePath() {
    return Paths.get("YOUR_OUTPUT_DIRECTORY", "RenderArchiveFolder");
}
```

```java
import com.groupdocs.viewer.Viewer;
import com.groupdocs.viewer.options.HtmlViewOptions;

public static void renderArchiveFolder() {
    Path outputDirectory = definePath();
    Path pageFilePathFormat = outputDirectory.resolve("page_{0}.html");

    HtmlViewOptions viewOptions = HtmlViewOptions.forEmbeddedResources(pageFilePathFormat);
    viewOptions.getArchiveOptions().setFolder("ThirdFolderWithItems");

    try (Viewer viewer = new Viewer("YOUR_DOCUMENT_DIRECTORY/SAMPLE_ZIP_WITH_FOLDERS")) {
        viewer.view(viewOptions);
    }
}
```

```java
public static Path definePath() {
    return Paths.get("YOUR_OUTPUT_DIRECTORY", "RenderArchiveFolder");
}
```

## บทแนะนำที่เกี่ยวข้อง

- [Groupdocs Viewer Java แปลงอาร์ไคฟ์เป็น Html](/viewer/java/export-conversion/groupdocs-viewer-java-convert-archives-html/)
- [แปลง zip เป็น pdf ด้วย GroupDocs.Viewer Java - ชื่อไฟล์กำหนดเอง](/viewer/java/advanced-rendering/groupdocs-viewer-java-custom-filenames-rendering-archives/)
- [วิธีแปลงเอกสารเป็น HTML ด้วย GroupDocs.Viewer สำหรับ Java](/viewer/java/rendering-basics/groupdocs-viewer-java-html-rendering/)