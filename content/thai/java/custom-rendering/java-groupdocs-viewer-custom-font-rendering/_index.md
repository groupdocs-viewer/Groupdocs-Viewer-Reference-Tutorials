---
date: '2026-02-10'
description: เรียนรู้วิธีเพิ่มฟอนต์แบบกำหนดเองใน HTML ด้วย GroupDocs.Viewer สำหรับ
  Java, กำหนดค่าการตั้งค่าฟอนต์ใน Java, และฝังฟอนต์แบบกำหนดเองใน HTML เพื่อการสร้างแบรนด์และความอ่านง่าย.
keywords:
- custom font rendering Java
- GroupDocs Viewer setup
- Java GroupDocs Viewer custom fonts
title: 'วิธีเพิ่มฟอนต์ที่กำหนดเองใน HTML ด้วย Java และ GroupDocs.Viewer: คู่มือขั้นตอนต่อขั้นตอน'
type: docs
url: /th/java/custom-rendering/java-groupdocs-viewer-custom-font-rendering/
weight: 1
---

# วิธีเพิ่มฟอนต์ HTML แบบกำหนดเองใน Java ด้วย GroupDocs.Viewer: คู่มือทีละขั้นตอน

## บทนำ

คุณกำลังประสบปัญหากับฟอนต์เริ่มต้นที่ไม่ตรงกับอัตลักษณ์ภาพของแบรนด์ของคุณหรือไม่? ในรายงานธุรกิจหลายประเภท เอกสารทางกฎหมาย และการนำเสนอ, **add custom font HTML** มีความสำคัญเพื่อให้รูปลักษณ์สอดคล้องและเพิ่มความอ่านง่าย คู่มือนี้จะพาคุณผ่านการใช้ **GroupDocs.Viewer for Java** เพื่อกำหนดค่า font settings Java และฝัง custom fonts HTML เพื่อให้เอกสารที่แสดงผลออกมามีลักษณะตรงตามที่คุณต้องการ

![Implement Custom Font Rendering with GroupDocs.Viewer for Java](/viewer/custom-rendering/implement-custom-font-rendering.png)

### สิ่งที่คุณจะได้เรียนรู้
- วิธีตั้งค่า GroupDocs.Viewer สำหรับ Java  
- วิธี **add custom font HTML** ไปยังผลลัพธ์ที่แสดงผล  
- วิธี **configure font settings Java** เพื่อประสิทธิภาพที่ดีที่สุด  

เมื่อจบบทเรียนนี้ คุณจะสามารถปรับแต่งการนำเสนอเอกสารด้วยฟอนต์แบบกำหนดเอง เพื่อให้แบรนด์สอดคล้องและเพิ่มการเข้าถึงที่ดียิ่งขึ้น

## คำตอบอย่างรวดเร็ว
- **วัตถุประสงค์หลักคืออะไร?** เพื่อแสดงเอกสารด้วยฟอนต์ของคุณโดยใช้ GroupDocs.Viewer Java.  
- **เวอร์ชันที่ต้องการคืออะไร?** GroupDocs.Viewer 25.2 (หรือใหม่กว่า).  
- **ฉันต้องการไลเซนส์หรือไม่?** มีการทดลองใช้ฟรี; จำเป็นต้องมีไลเซนส์แบบชำระเงินสำหรับการใช้งานในผลิตภัณฑ์.  
- **ฉันสามารถฝัง custom fonts HTML ได้หรือไม่?** ได้ – เพียงชี้ตัว viewer ไปยังโฟลเดอร์ที่มีฟอนต์ของคุณ.  
- **Maven เป็นวิธีเดียวในการเพิ่มไลบรารีหรือไม่?** Maven แนะนำให้ใช้, แต่คุณก็สามารถใช้ Gradle หรือการรวม JAR ด้วยตนเองได้.

## “add custom font HTML” คืออะไร?
การเพิ่ม custom font HTML หมายถึงการบอกให้เครื่องยนต์การเรนเดอร์ใช้ฟอนต์ที่คุณจัดเตรียมไว้แทนฟอนต์ระบบเริ่มต้นเมื่อสร้างผลลัพธ์ HTML. วิธีนี้ทำให้สไตล์ภาพของเอกสารตรงกับแบรนด์หรือแนวทางการเข้าถึงขององค์กรของคุณ

## ทำไมต้อง configure font settings Java กับ GroupDocs.Viewer?
การกำหนดค่า font settings Java ให้คุณควบคุมได้เต็มที่ว่าฟอนต์ไฟล์ใดบ้างที่จะค้นหา, วิธีการแคช, และวิธีการใช้ฟอนต์สำรอง. สิ่งนี้ช่วยลดข้อผิดพลาดในการเรนเดอร์, ปรับปรุงประสิทธิภาพ, และรับประกันการแสดงผลที่สอดคล้องกันในทุกเบราว์เซอร์

## ข้อกำหนดเบื้องต้น
- **Java Development Kit (JDK):** 8 หรือใหม่กว่า  
- **IDE:** IntelliJ IDEA, Eclipse หรือเครื่องมือแก้ไขที่รองรับ Java ใดๆ  
- **Maven:** สำหรับการจัดการ dependencies  
- **ไฟล์ฟอนต์แบบกำหนดเอง:** ไฟล์ `.ttf` หรือ `.otf` ที่วางไว้ในโฟลเดอร์เฉพาะ  

## การตั้งค่า GroupDocs.Viewer สำหรับ Java

### ข้อมูลการติดตั้ง

เพิ่มรีโพซิทอรีของ GroupDocs และ dependency ลงใน `pom.xml` ของ Maven ของคุณ:

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

GroupDocs มีการทดลองใช้ฟรีเพื่อสำรวจคุณสมบัติต่างๆ, พร้อมตัวเลือกในการรับไลเซนส์ชั่วคราวหรือซื้อไลเซนส์เต็ม. สำหรับการทดสอบ, ดาวน์โหลดเวอร์ชันล่าสุดจาก [release page](https://releases.groupdocs.com/viewer/java/).

#### การเริ่มต้นและตั้งค่าเบื้องต้น

หลังจากเพิ่ม GroupDocs.Viewer เป็น dependency, ให้เริ่มต้นในโปรเจกต์ Java ของคุณ:

```java
import com.groupdocs.viewer.Viewer;

public class ViewerSetup {
    public static void main(String[] args) {
        try (Viewer viewer = new Viewer("sample.pdf")) {
            // Initial setup and viewing code here
        }
    }
}
```

ตัวอย่างพื้นฐานนี้แสดงวิธีเปิดเอกสารด้วย GroupDocs.Viewer

## คู่มือการใช้งาน

### วิธีเพิ่ม custom font HTML ใน GroupDocs.Viewer Java

ในส่วนนี้เราจะอธิบายขั้นตอนที่จำเป็นเพื่อ **add custom font HTML** เมื่อเรนเดอร์เอกสาร

#### การนำเข้าแพ็กเกจที่จำเป็น

```java
import com.groupdocs.viewer.Viewer;
import com.groupdocs.viewer.options.HtmlViewOptions;
import com.groupdocs.viewer.fonts.FolderFontSource;
import com.groupdocs.viewer.fonts.FontSettings;
import com.groupdocs.viewer.fonts.SearchOption;
```

การนำเข้าเหล่านี้ช่วยให้จัดการฟอนต์แบบกำหนดเองและตัวเลือกการดูเอกสารได้ง่ายขึ้น

#### การตั้งค่า Custom Fonts

##### กำหนดเส้นทางไปยังโฟลเดอร์ฟอนต์ของคุณ

```java
String fontPath = "/path/to/your/custom/fonts";
```

แทนที่ `"/path/to/your/custom/fonts"` ด้วยตำแหน่งจริงของไฟล์ `.ttf` หรือ `.otf` ของคุณ

##### สร้างอ็อบเจ็กต์ FontSource

```java
FolderFontSource fontSource = new FolderFontSource(fontPath, SearchOption.TOP_FOLDER_ONLY);
```

`SearchOption.TOP_FOLDER_ONLY` บอก viewer ให้ค้นหาเฉพาะในโฟลเดอร์ที่ระบุ, ซึ่งช่วยเร่งการค้นหา

##### configure font settings Java

```java
FontSettings.setFontSources(fontSource);
```

บรรทัดนี้ **configures font settings Java** เพื่อให้ทุกการเรนเดอร์ใช้ฟอนต์ที่คุณจัดเตรียมไว้

#### กำหนดไดเรกทอรีเอาต์พุตและตัวเลือกการดู

```java
String outputPath = "/path/to/output/directory";
String pageFilePathFormat = String.format("%s/page_{0}.html", outputPath);
HtmlViewOptions viewOptions = HtmlViewOptions.forEmbeddedResources(pageFilePathFormat);
```

ในที่นี้เรายังแสดงวิธี **embed custom fonts HTML** ด้วยการใช้ `HtmlViewOptions.forEmbeddedResources`, ซึ่งฝังไฟล์ฟอนต์โดยตรงลงใน HTML ที่สร้างขึ้น

### เคล็ดลับการแก้ไขปัญหา
- ตรวจสอบว่าไฟล์ฟอนต์มีสิทธิ์การอ่านสำหรับผู้ใช้ที่รันกระบวนการ Java.  
- ตรวจสอบเส้นทางโฟลเดอร์อีกครั้ง; การขาดสแลชท้ายอาจทำให้เกิดข้อผิดพลาด “font not found”.  
- ตรวจสอบว่าฟอนต์เข้ากันได้กับประเภทเอกสาร (เช่น TrueType สำหรับ PDF).  

## การประยุกต์ใช้งานจริง

1. **Branding Consistency:** ใช้ฟอนต์ที่กำหนดตามแบรนด์ในรายงานที่สร้างทั้งหมด.  
2. **Accessibility Improvements:** เลือกฟอนต์ที่อ่านง่ายเพื่อช่วยผู้ใช้ที่มีปัญหาการมองเห็น.  
3. **Legal & Financial Documents:** เน้นส่วนสำคัญด้วยฟอนต์ที่ช่วยให้สแกนได้ง่ายขึ้น.  

คุณสามารถผสานวิธีนี้กับระบบจัดการเอกสาร, พอร์ทัลเนื้อหา, หรือแอปพลิเคชันองค์กรใดๆ ที่ต้องให้บริการตัวอย่าง HTML ของเอกสาร

## การพิจารณาประสิทธิภาพ

- จำกัดจำนวนฟอนต์แบบกำหนดเองเพื่อให้การใช้หน่วยความจำน้อยลง.  
- แคชอ็อบเจ็กต์ `HtmlViewOptions` เมื่อเรนเดอร์เอกสารหลายไฟล์ด้วยการตั้งค่าเดียวกัน.  
- ตรวจสอบ heap ของ JVM และปรับ `-Xmx` ตามความจำเป็นเพื่อหลีกเลี่ยงข้อผิดพลาด OutOfMemory.  

## สรุป

คุณได้เรียนรู้วิธี **add custom font HTML** ด้วย GroupDocs.Viewer สำหรับ Java, วิธี **configure font settings Java**, และวิธี **embed custom fonts HTML** เพื่อให้การเรนเดอร์เอกสารมีลักษณะสอดคล้องกับแบรนด์. เทคนิคเหล่านี้ช่วยให้คุณส่งมอบตัวอย่าง HTML ที่ดูเป็นมืออาชีพและเข้าถึงได้ในโซลูชัน Java ใดๆ

ขั้นตอนต่อไป, สำรวจความสามารถเพิ่มเติมของ GroupDocs.Viewer เช่น การใส่ลายน้ำ, การสนับสนุนคำอธิบาย, และการเรนเดอร์ PDF หลายหน้า. สำหรับรายละเอียดเพิ่มเติม, ดูที่ [documentation](https://docs.groupdocs.com/viewer/java/).

## คำถามที่พบบ่อย

**Q: ฉันจะทำให้ฟอนต์แบบกำหนดเองเข้ากันได้กับประเภทเอกสารต่างๆ อย่างไร?**  
A: ทดสอบฟอนต์ของคุณกับไฟล์ PDF, DOCX, และ PPTX เพื่อยืนยันการเรนเดอร์ที่สอดคล้องในทุกรูปแบบ.

**Q: GroupDocs.Viewer สามารถจัดการสคริปต์ที่ไม่ใช่ละตินด้วยฟอนต์แบบกำหนดเองได้หรือไม่?**  
A: ได้—เมื่อวางฟอนต์ที่รองรับ Unicode ที่เหมาะสมในโฟลเดอร์ฟอนต์, viewer จะเรนเดอร์อักขระได้อย่างถูกต้อง.

**Q: ตัวเลือกไลเซนส์สำหรับการใช้งานในผลิตภัณฑ์มีอะไรบ้าง?**  
A: คุณสามารถเริ่มต้นด้วยการทดลองใช้ฟรี, แล้วอัปเกรดเป็นไลเซนส์ชั่วคราวหรือถาวรผ่าน [purchase page](https://purchase.groupdocs.com/buy).

**Q: ฉันจะแก้ไขปัญหาไฟล์ฟอนต์หายได้อย่างไร?**  
A: ตรวจสอบสิทธิ์ไฟล์, ยืนยันเส้นทาง, และตรวจสอบว่าไฟล์ฟอนต์ไม่เสียหาย. บันทึกของ viewer จะบอกว่าไม่สามารถโหลดฟอนต์ใดได้.

**Q: ฉันสามารถกลับไปใช้ฟอนต์เริ่มต้นได้หากฟอนต์แบบกำหนดเองไม่พร้อมใช้งานหรือไม่?**  
A: ได้—โดยการเพิ่มหลายอ็อบเจ็กต์ `FontSource`, คุณสามารถให้ความสำคัญกับฟอนต์แบบกำหนดเองพร้อมคงฟอนต์ระบบเป็นสำรอง.

## แหล่งข้อมูล

- **Documentation:** [GroupDocs Viewer Java Docs](https://docs.groupdocs.com/viewer/java/)  
- **API Reference:** [GroupDocs API](https://reference.groupdocs.com/viewer/java/)  
- **Download:** [Latest Releases](https://releases.groupdocs.com/viewer/java/)  
- **Purchase and Trial Options:** [GroupDocs Purchase Page](https://purchase.groupdocs.com/buy) & [Free Trials](https://releases.groupdocs.com/viewer/java/)  
- **Support:** For additional help, visit the [GroupDocs Forum](

**Last Updated:** 2026-02-10  
**Tested With:** GroupDocs.Viewer 25.2 for Java  
**Author:** GroupDocs