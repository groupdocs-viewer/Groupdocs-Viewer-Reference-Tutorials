---
date: '2026-03-22'
description: เรียนรู้วิธีสร้าง HTML จาก PDF และปิดการจัดกลุ่มอักขระโดยใช้ GroupDocs
  Viewer for Java เพื่อการแสดงผลข้อความที่แม่นยำ.
keywords:
- disable character grouping PDFs
- GroupDocs Viewer Java configuration
- precise text representation in PDFs
title: สร้าง HTML จาก PDF และปิดการจัดกลุ่ม – GroupDocs Java
type: docs
url: /th/java/advanced-rendering/groupdocs-viewer-java-disable-character-grouping-pdf/
weight: 1
---

# สร้าง HTML จาก PDF และปิดการจัดกลุ่มด้วย GroupDocs Viewer สำหรับ Java

![เทคนิคการเรนเดอร์ที่แม่นยำด้วย GroupDocs.Viewer สำหรับ Java](/viewer/advanced-rendering/precise-rendering-techniques-java.png)

## คำตอบสั้น
- **“การปิดการจัดกลุ่ม” ทำอะไร?** มันบังคับให้ renderer ปฏิบัติตัวอักษรแต่ละตัวเป็นองค์ประกอบอิสระ เพื่อรักษาการจัดวางที่แม่นยำ.  
- **ตัวเลือก API ใดที่ควบคุมสิ่งนี้?** `viewOptions.getPdfOptions().setDisableCharsGrouping(true)`.  
- **ฉันต้องการไลเซนส์หรือไม่?** รุ่นทดลองใช้ได้สำหรับการทดสอบ แต่ต้องมีไลเซนส์เต็มสำหรับการใช้งานจริง.  
- **ฉันสามารถสร้าง HTML จาก PDF พร้อมกันได้หรือไม่?** ใช่ — ใช้ `HtmlViewOptions` เพื่อสร้างผลลัพธ์ HTML พร้อมกับปิดการจัดกลุ่ม.  
- **ฟีเจอร์นี้จำกัดเฉพาะ PDF หรือไม่?** มันออกแบบมาสำหรับ PDF เป็นหลัก แต่ viewer รองรับหลายรูปแบบอื่นด้วย.

## คำนำ

เมื่อทำงานกับเอกสาร PDF ความแม่นยำในการเรนเดอร์เป็นสิ่งสำคัญ — โดยเฉพาะอย่างยิ่งเมื่อจัดการกับโครงสร้างข้อความซับซ้อนเช่นอักษรภาพหรือภาษาที่ต้องการการแสดงอักขระที่แม่นยำ ฟีเจอร์ “Character Grouping” มักทำให้เกิดปัญหาโดยการจัดกลุ่มอักขระอย่างไม่ถูกต้อง ส่งผลให้เนื้อหาในเอกสารถูกตีความผิดพลาด ซึ่งอาจเป็นปัญหาอย่างยิ่งสำหรับผู้ใช้ที่ต้องการการทำสำเนาเลย์เอาต์ข้อความของเอกสารอย่างแม่นยำ

### ข้อกำหนดเบื้องต้น

ก่อนจะลงมือเขียนโค้ด โปรดตรวจสอบว่าคุณมีสิ่งต่อไปนี้ครบ:
- **ไลบรารีและการพึ่งพา**: คุณจำเป็นต้องใช้ GroupDocs.Viewer สำหรับ Java รุ่น 25.2 หรือใหม่กว่า.  
- **การตั้งค่าสภาพแวดล้อม**: ตรวจสอบว่าคุณได้ติดตั้ง Java Development Kit (JDK) แล้วและ IDE ของคุณตั้งค่าให้ทำงานกับโครงการ Maven.  
- **ความรู้พื้นฐานที่ต้องมี**: ความเข้าใจพื้นฐานของการเขียนโปรแกรม Java โดยเฉพาะการจัดการเส้นทางไฟล์และการใช้ไลบรารีภายนอก.

## วิธีสร้าง HTML จาก PDF ด้วย GroupDocs Viewer

การสร้าง HTML จาก PDF เป็นกระบวนการสองขั้นตอน: ตั้งค่า viewer แล้วเรนเดอร์เอกสาร จุดสำคัญคือการปิดการจัดกลุ่มอักขระก่อนการเรนเดอร์ เพื่อให้ผลลัพธ์ HTML สะท้อนการจัดวางของ PDF ต้นฉบับแบบอักขระต่ออักขระ

### การตั้งค่า GroupDocs.Viewer สำหรับ Java

#### การติดตั้งผ่าน Maven

แรกเริ่มให้รวมไลบรารีที่จำเป็นเข้าไปในโครงการของคุณ เพิ่มการกำหนดค่าต่อไปนี้ในไฟล์ `pom.xml` ของคุณ:

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

#### การขอรับไลเซนส์

เพื่อใช้ GroupDocs.Viewer อย่างเต็มที่ ควรพิจารณาได้รับไลเซนส์:
- **ทดลองใช้ฟรี**: เริ่มต้นด้วยรุ่นทดลองฟรีเพื่อทดสอบฟีเจอร์.  
- **ไลเซนส์ชั่วคราว**: ขอรับไลเซนส์ชั่วคราวหากต้องการเวลาเพิ่มเติม.  
- **ซื้อไลเซนส์**: สำหรับโครงการระยะยาว แนะนำให้ซื้อไลเซนส์.

#### การเริ่มต้นและตั้งค่าเบื้องต้น

ด้านล่างเป็นโค้ดสั้นที่พร้อมรัน ซึ่งแสดงขั้นตอนทำงานทั้งหมด — ตั้งค่าโฟลเดอร์ผลลัพธ์, เรนเดอร์ PDF เป็น HTML พร้อมกับปิดการจัดกลุ่มอักขระ:

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

ต่อไปนี้เราจะอธิบายแต่ละบรรทัดของตัวอย่าง เพื่อให้คุณเข้าใจ **ทำไม** เราต้องทำเช่นนั้นและ **อย่างไร** มันช่วยให้การสร้าง HTML จาก PDF ปราศจากการรวมอักขระที่ไม่ต้องการ

##### ขั้นตอนที่ 1: กำหนดไดเรกทอรีผลลัพธ์  

```java
Path outputDirectory = Utils.getOutputDirectoryPath("DisableCharactersGrouping");
```

**ทำไม?** สิ่งนี้ทำให้ไฟล์ HTML ที่เรนเดอร์แล้วถูกเก็บไว้ในโฟลเดอร์เฉพาะ ทำให้ค้นหาและจัดการได้ง่ายในภายหลัง.

##### ขั้นตอนที่ 2: กำหนดรูปแบบเส้นทางไฟล์  

```java
Path pageFilePathFormat = outputDirectory.resolve("page_{0}.html");
```

**ทำไม?** การใช้ตัวแปรแทน (`{0}`) ทำให้ viewer สร้างไฟล์ HTML แยกแต่ละหน้าของ PDF ได้อย่างเป็นระบบ.

##### ขั้นตอนที่ 3: เริ่มต้น HtmlViewOptions  

```java
HtmlViewOptions viewOptions = HtmlViewOptions.forEmbeddedResources(pageFilePathFormat);
```

**ทำไม?** การฝังทรัพยากร (รูปภาพ, ฟอนต์, CSS) ไว้ในแต่ละหน้า HTML ทำให้เหมาะกับ viewer บนเว็บหรือแพลตฟอร์ม e‑learning.

##### ขั้นตอนที่ 4: ปิดการจัดกลุ่มอักขระ  

```java
viewOptions.getPdfOptions().setDisableCharsGrouping(true);
```

**ทำไม?** นี่คือบรรทัดสำคัญที่บอก engine การเรนเดอร์ **ไม่** ให้รวมอักขระที่อยู่ติดกัน เพื่อให้ HTML ที่สร้างขึ้นสะท้อนตำแหน่ง glyph อย่างแม่นยำจาก PDF ต้นฉบับ.

##### ขั้นตอนที่ 5: เรนเดอร์เอกสาร  

```java
try (Viewer viewer = new Viewer("YOUR_DOCUMENT_DIRECTORY/HIEROGLYPHS_PDF")) {
    viewer.view(viewOptions);
}
```

**ทำไม?** การใช้ `Viewer` ภายในบล็อก `try‑with‑resources` ทำให้ทรัพยากรเนทีฟทั้งหมดถูกปล่อยอัตโนมัติ ป้องกันการรั่วไหลของหน่วยความจำในแอปพลิเคชันที่ทำงานต่อเนื่อง.

### การสร้าง HTML จาก PDF ด้วย Java โดยไม่มีการจัดกลุ่ม

คลาส `HtmlViewOptions` ช่วยให้คุณ **สร้าง html จาก pdf** พร้อมกับแยกอักขระแต่ละตัวออกจากกัน ซึ่งเป็นประโยชน์อย่างยิ่งเมื่อคุณต้องฝังหน้าที่เรนเดอร์ลงในพอร์ทัลเว็บหรือแพลตฟอร์ม e‑learning ที่ต้องการตำแหน่ง glyph ที่แม่นยำ.

### ปัญหาที่พบบ่อยและวิธีแก้

- **FileNotFoundException** – ตรวจสอบเส้นทางที่ส่งให้ `new Viewer(...)` อีกครั้ง ใช้เส้นทางแบบเต็มหรือ `Path.of(...)` เพื่อความชัดเจน.  
- **สิทธิ์การเขียน** – ตรวจสอบให้แน่ใจว่าไดเรกทอรีผลลัพธ์สามารถเขียนได้โดยกระบวนการ Java; บน Linux อาจต้องปรับสิทธิ์โฟลเดอร์ (`chmod 775`).  
- **เวอร์ชันไม่ตรงกัน** – ตัวเลือก `setDisableCharsGrouping` มีตั้งแต่เวอร์ชัน 25.2 ตรวจสอบว่า `pom.xml` ของคุณระบุเวอร์ชันที่ถูกต้อง.

### การประยุกต์ใช้งานจริง

1. **การรักษาภาษา** – เหมาะสำหรับการเรนเดอร์เอกสารในภาษาจีน, ญี่ปุ่น, อาหรับ หรืออักษรโบราณที่การเว้นระยะห่างของอักขระมีความหมาย.  
2. **เอกสารกฎหมายและการเงิน** – รับประกันการทำสำเนาข้อความที่แม่นยำสำหรับเอกสารที่ต้องปฏิบัติตามกฎระเบียบอย่างเคร่งครัด.  
3. **แหล่งเรียนการสอน** – เหมาะสำหรับตำราเรียนที่มีแผนภาพซับซ้อน, คำอธิบายเสริม หรือเนื้อหาหลายภาษา.

### ข้อควรพิจารณาด้านประสิทธิภาพ

- **เพิ่มประสิทธิภาพการใช้ทรัพยากร** – PDF ขนาดใหญ่ใช้หน่วยความจำมาก พิจารณาประมวลผลหน้าเป็นชุดและทำลายอินสแตนซ์ `Viewer` อย่างทันท่วงที.  
- **การจัดการหน่วยความจำของ Java** – ปรับขนาด heap ของ JVM (`-Xmx2g` หรือสูงกว่า) หากคาดว่าจะประมวลผล PDF หลายร้อยหน้า.  
- **การเรนเดอร์แบบขนาน** – สำหรับการแปลงจำนวนมาก ให้สร้างเธรดแยกแต่ละตัวพร้อมอินสแตนซ์ `Viewer` ของตนเองเพื่อใช้ประโยชน์จาก CPU หลายคอร์.

## คำถามที่พบบ่อย

**Q:** *ทำไมต้องปิดการจัดกลุ่มอักขระ?*  
**A:** การปิดการจัดกลุ่มทำให้ renderer ไม่รวมอักขระที่เป็น glyph แยกกัน ซึ่งจำเป็นสำหรับสคริปต์ที่การเว้นระยะและลำดับอักขระมีความหมาย.

**Q:** *การตั้งค่า `setDisableCharsGrouping` ใช้ได้เฉพาะผลลัพธ์ HTML หรือไม่?*  
**A:** ไม่ใช่; มันมีผลต่อ engine การเรนเดอร์ PDF ด้านล่าง ดังนั้นรูปแบบผลลัพธ์ใด ๆ (HTML, PNG, JPEG ฯลฯ) จะสะท้อนการเปลี่ยนแปลงนี้.

**Q:** *สามารถใช้การตั้งค่านี้ร่วมกับฟอนต์กำหนดเองได้หรือไม่?*  
**A:** ได้ — โหลดฟอนต์กำหนดเองก่อนเริ่มต้น `Viewer` แล้วกฎการจัดกลุ่มจะยังคงทำงาน.

**Q:** *การปิดการจัดกลุ่มส่งผลต่อประสิทธิภาพหรือไม่?*  
**A:** มีผลเล็กน้อย เนื่องจาก engine ต้องประมวลผลอักขระแต่ละตัวแยกกัน แต่ผลกระทบโดยรวมยังคงน้อยสำหรับเอกสารส่วนใหญ่.

**Q:** *มีวิธีสลับการจัดกลุ่มตามหน้าได้หรือไม่?*  
**A:** ปัจจุบันตัวเลือกเป็นระดับทั่วไประดับ `PdfOptions` เท่านั้น; หากต้องการพฤติกรรมผสม คุณต้องใช้ `Viewer` แยกกันสำหรับหน้าต่าง ๆ.

## แหล่งข้อมูล

- [เอกสาร GroupDocs](https://docs.groupdocs.com/viewer/java/)
- [อ้างอิง API](https://reference.groupdocs.com/viewer/java/)
- [ดาวน์โหลด GroupDocs Viewer](https://releases.groupdocs.com/viewer/java/)
- [ซื้อไลเซนส์](https://purchase.groupdocs.com/buy)
- [รุ่นทดลองฟรี](https://releases.groupdocs.com/viewer/java/)
- [สมัครไลเซนส์ชั่วคราว](https://purchase.groupdocs.com/temporary-license/)
- [ฟอรั่มสนับสนุน GroupDocs](https://forum.groupdocs.com/c/viewer/9)

---

**อัปเดตล่าสุด:** 2026-03-22  
**ทดสอบด้วย:** GroupDocs.Viewer 25.2 สำหรับ Java  
**ผู้เขียน:** GroupDocs