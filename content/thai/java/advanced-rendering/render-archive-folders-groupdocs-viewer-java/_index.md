---
date: '2026-01-10'
description: เรียนรู้วิธีเรนเดอร์โฟลเดอร์ zip ใน Java ด้วย GroupDocs.Viewer ผ่านคู่มือขั้นตอนที่ครอบคลุมนี้
keywords:
- render archive folders
- GroupDocs.Viewer for Java
- rendering specific folders in archives
title: วิธีแสดงโฟลเดอร์ zip ใน Java ด้วย GroupDocs.Viewer
type: docs
url: /th/java/advanced-rendering/render-archive-folders-groupdocs-viewer-java/
weight: 1
---

# วิธีเรนเดอร์โฟลเดอร์ zip ใน Java ด้วย GroupDocs.Viewer

คุณกำลังมองหาวิธีเรนเดอร์โฟลเดอร์เฉพาะภายในไฟล์บีบอัดเช่น ZIP อย่างมีประสิทธิภาพในแอปพลิเคชัน Java ของคุณหรือไม่? ในบทแนะนำนี้เราจะอธิบาย **วิธีเรนเดอร์ zip** โฟลเดอร์โดยใช้ GroupDocs.Viewer สำหรับ Java ครอบคลุมตั้งแต่การตั้งค่าโครงการจนถึงสถานการณ์การใช้งานจริง

![การเรนเดอร์โฟลเดอร์ในไฟล์บีบอัดด้วย GroupDocs.Viewer สำหรับ Java](/viewer/advanced-rendering/rendering-archive-folders-java.png)

## คำตอบอย่างรวดเร็ว
- **“render zip” หมายถึงอะไร?** หมายถึงการแปลงเนื้อหาของไฟล์ ZIP (หรือโฟลเดอร์เฉพาะภายใน) ให้เป็นรูปแบบที่สามารถดูได้ เช่น HTML หรือรูปภาพ  
- **ไลบรารีที่จัดการเรื่องนี้คืออะไร?** GroupDocs.Viewer for Java มีความสามารถในการเรนเดอร์ไฟล์บีบอัดในตัว  
- **ต้องการไลเซนส์หรือไม่?** สามารถใช้รุ่นทดลองฟรีเพื่อประเมินผล; ต้องมีไลเซนส์เต็มสำหรับการใช้งานในสภาพแวดล้อมจริง  
- **สามารถเรนเดอร์เฉพาะโฟลเดอร์เดียวได้หรือไม่?** ได้ – ใช้ `ArchiveOptions.setFolder("YourFolder")` เพื่อระบุโฟลเดอร์เป้าหมาย  
- **ต้องการเวอร์ชัน Java ใด?** Java 8 หรือสูงกว่า  

## “how to render zip” คืออะไรกับ GroupDocs.Viewer?
GroupDocs.Viewer เป็นไลบรารี Java ที่แปลงประเภทเอกสารหลากหลาย—including ไฟล์บีบอัด—ให้เป็นรูปแบบที่เหมาะกับเว็บ เมื่อคุณต้องการแสดงเฉพาะส่วนหนึ่งของไฟล์ ZIP (เช่น โฟลเดอร์ที่มีรูปภาพหรือ PDF) ตัว viewer จะช่วยให้คุณแยกและเรนเดอร์โฟลเดอร์นั้นโดยไม่ต้องแตกไฟล์บีบอัดทั้งหมด  

## ทำไมต้องใช้ GroupDocs.Viewer สำหรับการเรนเดอร์โฟลเดอร์ zip?
- **ความเร็ว:** เรนเดอร์โดยตรงจากไฟล์บีบอัด ลดขั้นตอนการแตกไฟล์ที่ใช้ทรัพยากร  
- **ความปลอดภัย:** ไม่จำเป็นต้องเขียนไฟล์ชั่วคราวลงดิสก์ เว้นแต่คุณต้องการ  
- **ความยืดหยุ่น:** ผลลัพธ์สามารถเป็น HTML, PNG หรือ PDF เหมาะกับสถานการณ์เว็บหรือเดสก์ท็อปส่วนใหญ่  
- **ความสามารถขยาย:** จัดการไฟล์บีบอัดขนาดใหญ่ด้วยการใช้หน่วยความจำต่ำเมื่อกำหนดค่าอย่างเหมาะสม  

## ข้อกำหนดเบื้องต้น
- **Java Development Kit (JDK)** 8 หรือใหม่กว่า  
- **Maven** สำหรับการจัดการ dependencies  
- ความคุ้นเคยพื้นฐานกับแนวคิดการเขียนโปรแกรม Java  

## การตั้งค่า GroupDocs.Viewer สำหรับ Java

### การกำหนดค่า Maven
เพิ่มรีโพซิทอรีของ GroupDocs และ dependency ลงในไฟล์ `pom.xml` ของคุณ:

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

### การรับไลเซนส์
เพื่อเปิดใช้งานศักยภาพเต็มของ GroupDocs.Viewer คุณสามารถรับ [รุ่นทดลองฟรี](https://releases.groupdocs.com/viewer/java/) หรือขอไลเซนส์ชั่วคราวผ่าน [หน้าลิขสิทธิ์ชั่วคราว](https://purchase.groupdocs.com/temporary-license/) สำหรับโครงการระยะยาว ควรพิจารณาซื้อไลเซนส์เต็ม  

### การเริ่มต้นพื้นฐาน
เมื่อการตั้งค่า Maven เสร็จสิ้น ให้เริ่มต้น viewer ด้วยเส้นทางไปยังไฟล์ ZIP ของคุณ:

```java
import com.groupdocs.viewer.Viewer;

try (Viewer viewer = new Viewer("path/to/archive.zip")) {
    // Rendering logic goes here
}
```

## คู่มือการนำไปใช้

### วิธีเรนเดอร์โฟลเดอร์ zip – ขั้นตอนต่อขั้นตอน

#### กำหนดเส้นทางการเอาต์พุต
สร้างเมธอดช่วยเหลือที่ชี้ไปยังไดเรกทอรีที่ไฟล์ HTML ที่เรนเดอร์จะถูกบันทึก:

```java
import java.nio.file.Path;
import java.nio.file.Paths;

public static Path definePath() {
    return Paths.get("YOUR_OUTPUT_DIRECTORY", "RenderArchiveFolder");
}
```

#### เรนเดอร์โฟลเดอร์เฉพาะ
กำหนดค่า viewer เพื่อระบุโฟลเดอร์เฉพาะภายในไฟล์บีบอัดและสร้างผลลัพธ์เป็น HTML:

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

**พารามิเตอร์สำคัญที่อธิบาย**
- `pageFilePathFormat`: ควบคุมรูปแบบการตั้งชื่อสำหรับแต่ละหน้า HTML ที่เรนเดอร์  
- `viewOptions.getArchiveOptions().setFolder(...)`: บอก viewer ให้เรนเดอร์เฉพาะโฟลเดอร์ที่ระบุภายในไฟล์ ZIP  

#### การกำหนดเส้นทางแบบกำหนดเองสำหรับไดเรกทอรีเอาต์พุต
หากต้องการตำแหน่งเอาต์พุตอื่น เพียงปรับเมธอด `definePath` :

```java
public static Path definePath() {
    return Paths.get("YOUR_OUTPUT_DIRECTORY", "RenderArchiveFolder");
}
```

## การประยุกต์ใช้งานจริง
1. **ระบบจัดการเอกสาร** – แสดงเฉพาะส่วนที่เกี่ยวข้องของไฟล์บีบอัดขนาดใหญ่โดยไม่ต้องเปิดเผยทั้งหมด  
2. **ห้องสมุดดิจิทัล** – สตรีมส่วนที่เลือกของ e‑book หรือคอลเลกชันการวิจัยโดยตรงในเบราว์เซอร์  
3. **แพลตฟอร์มตรวจสอบกฎหมาย** – มุ่งเน้นที่โฟลเดอร์คดีเฉพาะภายใน zip ขนาดใหญ่ ช่วยประหยัดเวลาและพื้นที่จัดเก็บ  

## ข้อควรพิจารณาด้านประสิทธิภาพ
- **การจัดการหน่วยความจำ:** สำหรับไฟล์ ZIP ขนาดใหญ่มาก ควรเพิ่มขนาด heap ของ JVM หรือประมวลผลโฟลเดอร์เป็นชุดเล็ก ๆ  
- **ประสิทธิภาพ I/O:** เขียนไฟล์ที่เรนเดอร์ไปยัง SSD เร็วหรือไดรฟ์ที่เชื่อมต่อเครือข่ายเพื่อ ลดความหน่วง  
- **ตัวเลือกการเรนเดอร์:** ปรับคุณภาพภาพหรือการตั้งค่าการบีบอัด HTML ใน `HtmlViewOptions` เพื่อสมดุลระหว่างความเร็วและความคมชัดของภาพ  

## สรุป
ตอนนี้คุณรู้ **วิธีเรนเดอร์ zip** โฟลเดอร์ใน Java ด้วย GroupDocs.Viewer — ตั้งแต่การตั้งค่า Maven ไปจนถึงการระบุโฟลเดอร์เดียวภายในไฟล์บีบอัดและการจัดการข้อกังวลด้านประสิทธิภาพ ผสานขั้นตอนเหล่านี้เข้ากับแอปพลิเคชันของคุณเพื่อให้การเข้าถึงเนื้อหาที่บีบอัดเป็นไปอย่างรวดเร็ว ปลอดภัย และเป็นมิตรกับผู้ใช้  

### ขั้นตอนต่อไป
สำรวจคุณลักษณะเพิ่มเติมของ GroupDocs.Viewer เช่น การแปลงเป็น PDF, การใส่ลายน้ำ, หรือการเรนเดอร์หลายหน้า เพื่อเพิ่มคุณค่าให้กับกระบวนการประมวลผลเอกสารของคุณ  

## ส่วนคำถามที่พบบ่อย

1. **GroupDocs.Viewer for Java คืออะไร?**  
   ไลบรารีที่ช่วยให้นักพัฒนาสามารถเรนเดอร์เอกสาร—including ไฟล์บีบอัด—โดยตรงในแอปพลิเคชัน Java  

2. **ฉันจะติดตั้ง GroupDocs.Viewer ด้วย Maven อย่างไร?**  
   เพิ่มการกำหนดค่ารีโพซิทอรีและ dependency ลงในไฟล์ `pom.xml` ของคุณตามที่แสดงในส่วนการกำหนดค่า Maven  

3. **ฉันสามารถใช้ GroupDocs.Viewer ได้ฟรีหรือไม่?**  
   มีรุ่นทดลองฟรีให้ใช้ แต่การใช้งานในสภาพแวดล้อมการผลิตต้องใช้เวอร์ชันที่มีไลเซนส์  

4. **ปัญหาที่พบบ่อยในการเรนเดอร์ไฟล์บีบอัดคืออะไร?**  
   ตรวจสอบให้แน่ใจว่าชื่อโฟลเดอร์ตรงกันอย่างแม่นยำ (คำนึงถึงตัวพิมพ์ใหญ่‑เล็ก) และไฟล์บีบอัดไม่ได้ถูกป้องกันด้วยรหัสผ่าน เว้นแต่คุณจะให้ข้อมูลประจำตัว  

5. **ฉันจะขอรับการสนับสนุนได้จากที่ไหน?**  
   เยี่ยมชม [GroupDocs Forum](https://forum.groupdocs.com/c/viewer/9) เพื่อรับความช่วยเหลือจากชุมชนหรือดูเอกสารอย่างเป็นทางการ  

## แหล่งข้อมูล
- [เอกสาร](https://docs.groupdocs.com/viewer/java/)
- [อ้างอิง API](https://reference.groupdocs.com/viewer/java/)
- [ดาวน์โหลด GroupDocs.Viewer](https://releases.groupdocs.com/viewer/java/)
- [ซื้อไลเซนส์](https://purchase.groupdocs.com/buy)
- [รุ่นทดลองฟรี](https://releases.groupdocs.com/viewer/java/)
- [ไลเซนส์ชั่วคราว](https://purchase.groupdocs.com/temporary-license/)
- [ฟอรั่มสนับสนุน](https://forum.groupdocs.com/c/viewer/9)

---

**อัปเดตล่าสุด:** 2026-01-10  
**ทดสอบกับ:** GroupDocs.Viewer 25.2 for Java  
**ผู้เขียน:** GroupDocs