---
date: '2025-12-21'
description: เรียนรู้วิธีปิดการจัดกลุ่มในไฟล์ PDF ด้วย GroupDocs.Viewer สำหรับ Java
  โดยใช้ java html จากตัวเลือกการเรนเดอร์ PDF เพื่อให้ได้การแสดงผลข้อความที่แม่นยำ
keywords:
- disable character grouping PDFs
- GroupDocs Viewer Java configuration
- precise text representation in PDFs
title: วิธีปิดการจัดกลุ่มในไฟล์ PDF ด้วย GroupDocs.Viewer สำหรับ Java
type: docs
url: /th/java/advanced-rendering/groupdocs-viewer-java-disable-character-grouping-pdf/
weight: 1
---

# วิธีปิดการจัดกลุ่มใน PDF ด้วย GroupDocs.Viewer สำหรับ Java

เมื่อคุณต้องการ **วิธีปิดการจัดกลุ่ม** ขณะเรนเดอร์ PDF โดยเฉพาะสำหรับสคริปต์ที่ซับซ้อนหรือภาษาที่โบราณ การวางตำแหน่งอักขระอย่างแม่นยำจึงเป็นสิ่งสำคัญ ฟีเจอร์ *Character Grouping* เริ่มต้นอาจรวมอักขระผิดพลาด ทำให้เนื้อหาถูกตีความผิด ในคู่มือนี้เราจะแสดงขั้นตอนโดยละเอียดว่าจะแยกการจัดกลุ่มโดยใช้ GroupDocs.Viewer สำหรับ Java อย่างไร เพื่อให้แต่ละ glyph อยู่ในตำแหน่งที่ถูกต้อง

![เทคนิคการเรนเดอร์ที่แม่นยำด้วย GroupDocs.Viewer สำหรับ Java](/viewer/advanced-rendering/precise-rendering-techniques-java.png)

## คำตอบด่วน
- **“disable grouping” ทำอะไร?** มันบังคับให้ renderer ปฏิบัติต่อแต่ละอักขระเป็นองค์ประกอบอิสระ เพื่อรักษาการจัดวางที่แม่นยำ.  
- **ตัวเลือก API ใดที่ควบคุมสิ่งนี้?** `viewOptions.getPdfOptions().setDisableCharsGrouping(true)`.  
- **ฉันต้องการไลเซนส์หรือไม่?** การทดลองใช้งานทำงานได้สำหรับการทดสอบ แต่ต้องมีไลเซนส์เต็มสำหรับการใช้งานจริง.  
- **ฉันสามารถสร้าง Java HTML จาก PDF พร้อมกันได้หรือไม่?** ใช่ — ใช้ `HtmlViewOptions` เพื่อสร้างผลลัพธ์ HTML ขณะปิดการจัดกลุ่ม.  
- **ฟีเจอร์นี้จำกัดเฉพาะ PDF หรือไม่?** มันออกแบบมาสำหรับ PDF เป็นหลัก แต่ viewer รองรับหลายรูปแบบอื่น.

## คำแนะนำ

เมื่อทำงานกับเอกสาร PDF ความแม่นยำในการเรนเดอร์เป็นสิ่งสำคัญ — โดยเฉพาะเมื่อจัดการกับโครงสร้างข้อความที่ซับซ้อนเช่นอักษรไฮโรกลีฟหรือภาษาที่ต้องการการแสดงอักขระอย่างแม่นยำ ฟีเจอร์ “Character Grouping” มักทำให้เกิดปัญหาโดยการจัดกลุ่มอักขระผิดพลาด ทำให้เนื้อหาเอกสารถูกตีความผิด นี่อาจเป็นปัญหาอย่างยิ่งสำหรับผู้ใช้ที่ต้องการสำเนาต้นฉบับของการจัดวางข้อความในเอกสารอย่างแม่นยำ

### ข้อกำหนดเบื้องต้น
- **Libraries & Dependencies**: คุณจะต้องใช้ GroupDocs.Viewer สำหรับ Java เวอร์ชัน 25.2 หรือใหม่กว่า.  
- **Environment Setup**: ตรวจสอบว่าคุณได้ติดตั้ง Java Development Kit (JDK) และตั้งค่า IDE ของคุณให้ทำงานกับโปรเจกต์ Maven.  
- **Knowledge Prerequisites**: มีความเข้าใจพื้นฐานของการเขียนโปรแกรม Java โดยเฉพาะการจัดการเส้นทางไฟล์และการใช้ไลบรารีภายนอก.

## วิธีปิดการจัดกลุ่มในการเรนเดอร์ PDF

### การตั้งค่า GroupDocs.Viewer สำหรับ Java

#### การติดตั้งผ่าน Maven

ขั้นแรก ให้รวมไลบรารีที่จำเป็นเข้ากับโปรเจกต์ของคุณ เพิ่มการกำหนดค่าต่อไปนี้ในไฟล์ `pom.xml` ของคุณ:

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

#### การรับไลเซนส์

เพื่อใช้ GroupDocs.Viewer อย่างเต็มที่ ควรพิจารณาได้รับไลเซนส์:
- **Free Trial**: เริ่มต้นด้วยการทดลองใช้งานฟรีเพื่อทดสอบฟีเจอร์.  
- **Temporary License**: ขอรับไลเซนส์ชั่วคราวหากต้องการเวลาเพิ่มเติม.  
- **Purchase**: สำหรับโครงการระยะยาว ควรซื้อไลเซนส์.

#### การเริ่มต้นและตั้งค่าเบื้องต้น

เริ่มต้นโดยตั้งค่าสภาพแวดล้อมของโปรเจกต์ของคุณ:

```java
import com.groupdocs.viewer.Viewer;
import com.groupdocs.viewer.options.HtmlViewOptions;
import java.nio.file.Path;

// Initialize the GroupDocs Viewer
Path outputDirectory = Utils.getOutputDirectoryPath("DisableCharactersGrouping");
Path pageFilePathFormat = outputDirectory.resolve("page_{0}.html");

HtmlViewOptions viewOptions = HtmlViewOptions.forEmbeddedResources(pageFilePathFormat);
viewOptions.getPdfOptions().setDisableCharsGrouping(true);

try (Viewer viewer = new Viewer("YOUR_DOCUMENT_DIRECTORY/HIEROGLYPHS_PDF")) {
    viewer.view(viewOptions);
}
```

### คู่มือการใช้งาน

#### ฟีเจอร์: ปิดการจัดกลุ่มอักขระ

##### ขั้นตอนที่ 1: กำหนดไดเรกทอรีผลลัพธ์

```java
Path outputDirectory = Utils.getOutputDirectoryPath("DisableCharactersGrouping");
```

**ทำไม?** สิ่งนี้ทำให้ผลลัพธ์ของคุณเป็นระเบียบและเข้าถึงได้ง่าย.

##### ขั้นตอนที่ 2: กำหนดรูปแบบเส้นทางไฟล์

```java
Path pageFilePathFormat = outputDirectory.resolve("page_{0}.html");
```

**ทำไม?** ช่วยให้จัดระเบียบหน้าของเอกสาร PDF อย่างเป็นระบบ.

##### ขั้นตอนที่ 3: เริ่มต้น HTML View Options

```java
HtmlViewOptions viewOptions = HtmlViewOptions.forEmbeddedResources(pageFilePathFormat);
```

**ทำไม?** แหล่งข้อมูลที่ฝังไว้ทำให้แน่ใจว่า assets ที่จำเป็นทั้งหมดรวมอยู่ในไฟล์ HTML ของแต่ละหน้า.

##### ขั้นตอนที่ 4: ปิดการจัดกลุ่มอักขระ

```java
viewOptions.getPdfOptions().setDisableCharsGrouping(true);
```

**ทำไม?** สิ่งนี้ทำให้แต่ละอักขระถูกเรนเดอร์แยกกัน เพื่อรักษาการจัดวางและความหมายตามที่ตั้งใจ.

##### ขั้นตอนที่ 5: เรนเดอร์เอกสาร

```java
try (Viewer viewer = new Viewer("YOUR_DOCUMENT_DIRECTORY/HIEROGLYPHS_PDF")) {
    viewer.view(viewOptions);
}
```

**ทำไม?** สิ่งนี้ทำให้แน่ใจว่าทรัพยากรทั้งหมดถูกปิดอย่างเหมาะสม ป้องกันการรั่วไหลของหน่วยความจำ.

### การสร้าง Java HTML จาก PDF โดยไม่จัดกลุ่ม

คลาส `HtmlViewOptions` ให้คุณสร้าง **java html from pdf** โดยคงอักขระแต่ละตัวแยกกันไว้ นี่เป็นประโยชน์โดยเฉพาะเมื่อคุณต้องฝังหน้าที่เรนเดอร์ลงในพอร์ทัลเว็บหรือแพลตฟอร์ม e‑learning ที่ตำแหน่ง glyph ต้องแม่นยำ.

### เคล็ดลับการแก้ไขปัญหา
- ตรวจสอบให้แน่ใจว่าเส้นทางเอกสารของคุณถูกต้องเพื่อหลีกเลี่ยง `FileNotFoundException`.  
- ยืนยันว่าไดเรกทอรีผลลัพธ์มีสิทธิ์การเขียน.  
- ตรวจสอบอีกครั้งว่าคุณใช้เวอร์ชันที่เข้ากันได้ของ GroupDocs.Viewer สำหรับ Java.

## การประยุกต์ใช้งานจริง

1. **Language Preservation**: เหมาะสำหรับการเรนเดอร์เอกสารในภาษาต่างๆ เช่น จีน, ญี่ปุ่น หรือสคริปต์โบราณที่ต้องการความแม่นยำของอักขระ.  
2. **Legal and Financial Documents**: รับประกันความถูกต้องในเอกสารที่ต้องการการแสดงข้อความอย่างแม่นยำเพื่อการปฏิบัติตามกฎระเบียบ.  
3. **Educational Resources**: เหมาะอย่างยิ่งสำหรับตำราเรียนและเอกสารวิชาการที่มีแผนภาพหรือคำอธิบายที่ซับซ้อน.

## การพิจารณาประสิทธิภาพ

- **Optimize Resource Usage**: ตรวจสอบให้เซิร์ฟเวอร์ของคุณมีทรัพยากรเพียงพอเพื่อจัดการไฟล์ PDF ขนาดใหญ่.  
- **Java Memory Management**: ใช้โครงสร้างข้อมูลที่มีประสิทธิภาพและแนวปฏิบัติการเก็บกวาดหน่วยความจำเพื่อจัดการหน่วยความจำอย่างมีประสิทธิภาพ.  
- **Batch Processing**: เมื่อเรนเดอร์หลายเอกสาร ให้ประมวลผลเป็นชุดเพื่อเพิ่มอัตราการทำงาน.

## สรุป

คุณได้เรียนรู้ **วิธีปิดการจัดกลุ่ม** ระหว่างการเรนเดอร์ PDF ด้วย GroupDocs.Viewer สำหรับ Java แล้ว ความสามารถนี้สำคัญสำหรับแอปพลิเคชันที่ต้องการการแสดงข้อความอย่างแม่นยำ เพื่อสำรวจต่อไป ลองผสานฟีเจอร์นี้กับระบบจัดการเอกสารอื่น ๆ หรือทดลองใช้ตัวเลือกการเรนเดอร์เพิ่มเติม.

ขั้นตอนต่อไปคือการสำรวจฟีเจอร์ขั้นสูงเพิ่มเติมของ GroupDocs.Viewer และปรับแต่งประสิทธิภาพสำหรับการใช้งานในระดับใหญ่.

## ส่วนคำถามที่พบบ่อย

1. **การปิดการจัดกลุ่มอักขระทำให้ได้อะไร?**  
   - มันทำให้แต่ละอักขระถูกเรนเดอร์แยกกัน เพื่อรักษาการจัดวางเดิมของพวกมัน.  
2. **ฉันสามารถใช้ฟีเจอร์นี้กับประเภทเอกสารอื่นได้หรือไม่?**  
   - ใช่ แม้ว่าเน้นที่ PDF แต่ GroupDocs.Viewer รองรับหลายรูปแบบ.  
3. **ฉันจะจัดการเอกสารขนาดใหญ่อย่างมีประสิทธิภาพได้อย่างไร?**  
   - ใช้การประมวลผลเป็นชุดและปรับแต่งทรัพยากรเซิร์ฟเวอร์ของคุณ.  
4. **ควรทำอย่างไรหากไดเรกทอรีผลลัพธ์ไม่สามารถเขียนได้?**  
   - ตรวจสอบสิทธิ์หรือเลือกไดเรกทอรีอื่นที่มีสิทธิ์เข้าถึงที่เหมาะสม.  
5. **มีข้อจำกัดด้านไลเซนส์สำหรับ GroupDocs.Viewer หรือไม่?**  
   - มีการทดลองใช้งานฟรี แต่การใช้งานระยะยาวต้องมีไลเซนส์ที่ซื้อ.

## คำถามที่พบบ่อย

**Q:** *ทำไมฉันต้องการปิดการจัดกลุ่มอักขระ?*  
**A:** การปิดการจัดกลุ่มทำให้ renderer ไม่รวมอักขระที่เป็น glyph แยกกัน ซึ่งสำคัญสำหรับสคริปต์ที่ช่องว่างและลำดับมีความหมาย.

**Q:** *การตั้งค่า `setDisableCharsGrouping` ใช้ได้เฉพาะผลลัพธ์ HTML หรือไม่?*  
**A:** ไม่ใช่ มันส่งผลต่อเอนจินการเรนเดอร์ PDF ด้านล่าง ดังนั้นรูปแบบผลลัพธ์ใด ๆ (HTML, PNG ฯลฯ) จะสะท้อนการเปลี่ยนแปลงนี้.

**Q:** *ฉันสามารถผสานการตั้งค่านี้กับฟอนต์ที่กำหนดเองได้หรือไม่?*  
**A:** ได้ — เพียงโหลดฟอนต์ที่กำหนดเองก่อนเริ่มต้น `Viewer` แล้วกฎการจัดกลุ่มจะยังคงทำงาน.

**Q:** *การปิดการจัดกลุ่มส่งผลต่อประสิทธิภาพหรือไม่?*  
**A:** เล็กน้อย เนื่องจากเอนจินประมวลผลแต่ละอักขระแยกกัน แต่ผลกระทบโดยรวมน้อยสำหรับเอกสารส่วนใหญ่.

**Q:** *มีวิธีสลับการจัดกลุ่มต่อหน้าได้หรือไม่?*  
**A:** ปัจจุบันตัวเลือกเป็นระดับทั่วโลกต่ออินสแตนซ์ `PdfOptions` คุณต้องสร้างอินสแตนซ์ `Viewer` แยกต่างหากสำหรับแต่ละหน้า.

## แหล่งข้อมูล

- [เอกสาร GroupDocs](https://docs.groupdocs.com/viewer/java/)
- [อ้างอิง API](https://reference.groupdocs.com/viewer/java/)
- [ดาวน์โหลด GroupDocs Viewer](https://releases.groupdocs.com/viewer/java/)
- [ซื้อไลเซนส์](https://purchase.groupdocs.com/buy)
- [เวอร์ชันทดลองฟรี](https://releases.groupdocs.com/viewer/java/)
- [สมัครไลเซนส์ชั่วคราว](https://purchase.groupdocs.com/temporary-license/)
- [ฟอรั่มสนับสนุน GroupDocs](https://forum.groupdocs.com/c/viewer/9)

**อัปเดตล่าสุด:** 2025-12-21  
**ทดสอบด้วย:** GroupDocs.Viewer 25.2 for Java  
**ผู้เขียน:** GroupDocs