---
date: '2026-03-14'
description: เรียนรู้วิธีแปลงไฟล์ zip เป็น HTML ด้วย GroupDocs.Viewer สำหรับ Java
  และเรนเดอร์โฟลเดอร์ zip เฉพาะในแอปพลิเคชันของคุณ
keywords:
- render archive folders
- GroupDocs.Viewer for Java
- rendering specific folders in archives
title: วิธีแปลงไฟล์ zip เป็น HTML และแสดงโฟลเดอร์ zip ใน Java ด้วย GroupDocs.Viewer
type: docs
url: /th/java/advanced-rendering/render-archive-folders-groupdocs-viewer-java/
weight: 1
---

# วิธีแปลง zip เป็น HTML และแสดงโฟลเดอร์ zip ใน Java ด้วย GroupDocs.Viewer

คุณกำลังมองหาวิธีที่มีประสิทธิภาพในการ **แปลง zip เป็น HTML** และแสดงโฟลเดอร์เฉพาะภายในไฟล์บีบอัดเช่น ZIP ในแอปพลิเคชัน Java ของคุณหรือไม่? ในบทแนะนำนี้เราจะอธิบายขั้นตอนการแสดงโฟลเดอร์ zip ด้วย GroupDocs.Viewer for Java ตั้งแต่การตั้งค่าโครงการจนถึงกรณีการใช้งานจริง คุณจะเห็นว่าทำไมวิธีนี้จึงช่วยประหยัดเวลา ลดภาระ I/O และทำให้แอปพลิเคชันของคุณปลอดภัย

![การแสดงโฟลเดอร์ Archive ด้วย GroupDocs.Viewer สำหรับ Java](/viewer/advanced-rendering/rendering-archive-folders-java.png)

## คำตอบอย่างรวดเร็ว
- **What does “convert zip to HTML” mean?** หมายถึงการแปลงเนื้อหาของไฟล์ ZIP (หรือโฟลเดอร์เฉพาะภายในไฟล์) ให้เป็นหน้า HTML ที่เหมาะกับเว็บ  
- **Which library handles this?** GroupDocs.Viewer for Java มีความสามารถในการแสดงผล archive ในตัว  
- **Do I need a license?** การทดลองใช้ฟรีสามารถใช้สำหรับการประเมินผล; จำเป็นต้องมีลิขสิทธิ์เต็มสำหรับการใช้งานจริง  
- **Can I render only one folder?** ใช่ – ใช้ `ArchiveOptions.setFolder("YourFolder")` เพื่อกำหนดโฟลเดอร์เดียว  
- **What Java version is required?** Java 8 หรือสูงกว่า  

## วิธีแปลง zip เป็น HTML ด้วย GroupDocs.Viewer
GroupDocs.Viewer ทำให้ซับซ้อนของการแยกและแปลงเนื้อหา archive ง่ายขึ้น แทนการแตกไฟล์ด้วยตนเอง คุณสามารถสั่งให้ viewer **convert zip to HTML** สำหรับโฟลเดอร์ที่เลือกได้โดยตรง ซึ่งช่วยให้กระบวนการทำงานราบรื่นและลดไฟล์ชั่วคราว  

## “how to render zip” คืออะไรกับ GroupDocs.Viewer
GroupDocs.Viewer เป็นไลบรารี Java ที่แปลงเอกสารหลากหลายประเภท—including compressed archives—ให้เป็นรูปแบบที่เหมาะกับเว็บ เมื่อคุณต้องการแสดงเฉพาะส่วนของไฟล์ ZIP (เช่น โฟลเดอร์ที่มีรูปภาพหรือ PDF) viewer จะช่วยให้คุณแยกและแสดงโฟลเดอร์นั้นโดยไม่ต้องแตก archive ทั้งหมด  

## ทำไมต้องใช้ GroupDocs.Viewer สำหรับการแสดงโฟลเดอร์ zip
- **Speed:** เรนเดอร์โดยตรงจาก archive หลีกเลี่ยงขั้นตอนการแตกไฟล์เต็มที่มีค่าใช้จ่ายสูง  
- **Security:** ไม่จำเป็นต้องเขียนไฟล์ชั่วคราวลงดิสก์ เว้นแต่คุณต้องการ  
- **Flexibility:** ผลลัพธ์สามารถเป็น HTML, PNG หรือ PDF เหมาะกับสถานการณ์เว็บหรือเดสก์ท็อปส่วนใหญ่  
- **Scalability:** รองรับ archive ขนาดใหญ่ด้วยการใช้หน่วยความจำน้อยเมื่อกำหนดค่าอย่างเหมาะสม  

## ข้อกำหนดเบื้องต้น
- **Java Development Kit (JDK)** 8 หรือใหม่กว่า  
- **Maven** สำหรับการจัดการ dependencies  
- ความคุ้นเคยพื้นฐานกับแนวคิดการเขียนโปรแกรม Java  

## การตั้งค่า GroupDocs.Viewer สำหรับ Java

### การกำหนดค่า Maven
เพิ่ม repository ของ GroupDocs และ dependency ลงในไฟล์ `pom.xml` ของคุณ:

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

### การรับลิขสิทธิ์
เพื่อเปิดใช้งานศักยภาพเต็มของ GroupDocs.Viewer คุณสามารถรับ [การทดลองใช้งานฟรี](https://releases.groupdocs.com/viewer/java/) หรือรับลิขสิทธิ์ชั่วคราวผ่าน [หน้าลิขสิทธิ์ชั่วคราว](https://purchase.groupdocs.com/temporary-license/) ของพวกเขา สำหรับโครงการระยะยาว ควรพิจารณาซื้อไลเซนส์เต็ม  

### การเริ่มต้นพื้นฐาน
เมื่อการตั้งค่า Maven เสร็จสมบูรณ์ ให้เริ่มต้น viewer ด้วยพาธไปยังไฟล์ ZIP ของคุณ:

```java
import com.groupdocs.viewer.Viewer;

try (Viewer viewer = new Viewer("path/to/archive.zip")) {
    // Rendering logic goes here
}
```

## วิธีดึงโฟลเดอร์จาก zip ด้วย GroupDocs.Viewer
เมื่อคุณต้องการเฉพาะไดเรกทอรีภายใน archive คุณสามารถบอก viewer ว่าโฟลเดอร์ใดที่จะประมวลผล การดำเนินการ **extract folder from zip** นี้ทำในหน่วยความจำ จึงหลีกเลี่ยงภาระการแตกไฟล์ด้วยตนเอง  

### กำหนดพาธการส่งออก
สร้างเมธอดช่วยเหลือที่ชี้ไปยังไดเรกทอรีที่ไฟล์ HTML ที่เรนเดอร์จะถูกบันทึก:

```java
import java.nio.file.Path;
import java.nio.file.Paths;

public static Path definePath() {
    return Paths.get("YOUR_OUTPUT_DIRECTORY", "RenderArchiveFolder");
}
```

### เรนเดอร์โฟลเดอร์เฉพาะ
กำหนดค่า viewer เพื่อกำหนดเป้าหมายโฟลเดอร์เฉพาะภายใน archive และสร้างผลลัพธ์เป็น HTML:

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

**อธิบายพารามิเตอร์สำคัญ**
- `pageFilePathFormat`: ควบคุมรูปแบบการตั้งชื่อสำหรับแต่ละหน้า HTML ที่เรนเดอร์  
- `viewOptions.getArchiveOptions().setFolder(...)`: สั่งให้ viewer เรนเดอร์เฉพาะโฟลเดอร์ที่ระบุภายใน ZIP archive  

### การกำหนดพาธแบบกำหนดเองสำหรับไดเรกทอรีผลลัพธ์
หากคุณต้องการตำแหน่งผลลัพธ์ที่แตกต่าง เพียงปรับเมธอด `definePath`:

```java
public static Path definePath() {
    return Paths.get("YOUR_OUTPUT_DIRECTORY", "RenderArchiveFolder");
}
```

## การประยุกต์ใช้งานจริง
1. **Document Management Systems** – แสดงเฉพาะส่วนที่เกี่ยวข้องของ archive ขนาดใหญ่โดยไม่เปิดเผยทั้งหมด  
2. **Digital Libraries** – สตรีมส่วนที่เลือกของ e‑books หรือคอลเลกชันการวิจัยโดยตรงในเบราว์เซอร์  
3. **Legal Review Platforms** – มุ่งเน้นที่โฟลเดอร์คดีเฉพาะภายใน zip bundle ขนาดใหญ่ ช่วยประหยัดเวลาและพื้นที่จัดเก็บ  

## ข้อควรพิจารณาด้านประสิทธิภาพ
- **Memory Management:** สำหรับไฟล์ ZIP ขนาดใหญ่มาก ควรเพิ่มขนาด heap ของ JVM หรือประมวลผลโฟลเดอร์เป็นชุดเล็ก ๆ  
- **I/O Efficiency:** เขียนไฟล์ที่เรนเดอร์ไปยัง SSD เร็วหรือไดรฟ์ที่เชื่อมต่อเครือข่ายเพื่อ ลดความหน่วง  
- **Rendering Options:** ปรับคุณภาพภาพหรือการตั้งค่าการย่อ HTML ใน `HtmlViewOptions` เพื่อสมดุลระหว่างความเร็วและความคมชัดของภาพ  

## สรุป
ตอนนี้คุณรู้แล้วว่า **how to convert zip to HTML** และการแสดงโฟลเดอร์ zip ใน Java ด้วย GroupDocs.Viewer — ตั้งแต่การตั้งค่า Maven ไปจนถึงการกำหนดเป้าหมายโฟลเดอร์เดียวภายใน archive และการจัดการข้อกังวลด้านประสิทธิภาพ ผสานขั้นตอนเหล่านี้เข้ากับแอปพลิเคชันของคุณเพื่อให้การเข้าถึงเนื้อหา archive อย่างรวดเร็ว ปลอดภัย และเป็นมิตรกับผู้ใช้  

### ขั้นตอนต่อไป
สำรวจคุณลักษณะเพิ่มเติมของ GroupDocs.Viewer เช่น การแปลง PDF, การใส่ลายน้ำ, หรือการเรนเดอร์หลายหน้า เพื่อเพิ่มคุณค่าให้กับกระบวนการประมวลผลเอกสารของคุณ  

## คำถามที่พบบ่อย

**Q: GroupDocs.Viewer for Java คืออะไร?**  
A: เป็นไลบรารีที่ช่วยให้นักพัฒนาสามารถเรนเดอร์เอกสาร—including archives—โดยตรงในแอปพลิเคชัน Java  

**Q: จะติดตั้ง GroupDocs.Viewer ด้วย Maven อย่างไร?**  
A: เพิ่มการกำหนดค่า repository และ dependency ลงในไฟล์ `pom.xml` ของคุณตามที่แสดงในส่วนการกำหนดค่า Maven  

**Q: สามารถใช้ GroupDocs.Viewer ฟรีได้หรือไม่?**  
A: มีการทดลองใช้งานฟรี แต่การใช้งานในสภาพแวดล้อมการผลิตต้องใช้เวอร์ชันที่มีลิขสิทธิ์  

**Q: ปัญหาทั่วไปเมื่อเรนเดอร์ archive มีอะไรบ้าง?**  
A: ตรวจสอบให้แน่ใจว่าชื่อโฟลเดอร์ตรงกันอย่างแม่นยำ (คำนึงถึงตัวพิมพ์ใหญ่‑เล็ก) และ archive ไม่ได้ถูกป้องกันด้วยรหัสผ่าน เว้นแต่คุณจะให้ข้อมูลประจำตัว  

**Q: จะหาการสนับสนุนได้จากที่ไหนหากต้องการ?**  
A: เยี่ยมชม [GroupDocs Forum](https://forum.groupdocs.com/c/viewer/9) เพื่อรับความช่วยเหลือจากชุมชนหรือปรึกษาเอกสารอย่างเป็นทางการ  

## แหล่งข้อมูล
- [เอกสารประกอบ](https://docs.groupdocs.com/viewer/java/)
- [อ้างอิง API](https://reference.groupdocs.com/viewer/java/)
- [ดาวน์โหลด GroupDocs.Viewer](https://releases.groupdocs.com/viewer/java/)
- [ซื้อไลเซนส์](https://purchase.groupdocs.com/buy)
- [ทดลองใช้งานฟรี](https://releases.groupdocs.com/viewer/java/)
- [ไลเซนส์ชั่วคราว](https://purchase.groupdocs.com/temporary-license/)
- [ฟอรั่มสนับสนุน](https://forum.groupdocs.com/c/viewer/9)

---

**อัปเดตล่าสุด:** 2026-03-14  
**ทดสอบกับ:** GroupDocs.Viewer 25.2 for Java  
**ผู้เขียน:** GroupDocs