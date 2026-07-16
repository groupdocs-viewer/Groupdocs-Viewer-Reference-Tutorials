---
date: '2026-03-24'
description: เรียนรู้วิธีแปลงอีเมลเป็น HTML และเปลี่ยนชื่อฟิลด์อีเมลโดยใช้ GroupDocs
  Viewer สำหรับ Java คู่มือนี้แสดงการแสดงผลอีเมลเป็น HTML พร้อมหัวข้อที่กำหนดเอง
keywords:
- rename email fields Java
- render emails HTML GroupDocs Viewer
- customize email metadata Java
title: แปลงอีเมลเป็น HTML และเปลี่ยนชื่อฟิลด์ – GroupDocs Viewer Java
type: docs
url: /th/java/advanced-rendering/rename-email-fields-html-groupdocs-viewer-java/
weight: 1
---

# แปลงอีเมลเป็น HTML & เปลี่ยนชื่อฟิลด์ – GroupDocs Viewer Java

หากคุณต้องการ **แปลงอีเมลเป็น HTML** พร้อมกับให้ส่วนหัวของอีเมลมีลักษณะตามที่กำหนดเอง คุณมาถูกที่แล้ว ในบทเรียนนี้เราจะอธิบายขั้นตอนอย่างละเอียดเพื่อเปลี่ยนชื่อฟิลด์ของอีเมล, **แปลงอีเมลเป็น HTML**, และปรับแต่งส่วนหัวของอีเมลโดยใช้ GroupDocs.Viewer for Java. เมื่อเสร็จคุณจะได้การแสดงผล HTML ที่สะอาดตาพร้อมชื่อส่วนหัวที่คุณต้องการ ทำให้ผลลัพธ์อ่านง่ายและนำไปใช้ในแอปพลิเคชันของคุณได้ง่ายขึ้น.

![เปลี่ยนชื่อฟิลด์อีเมลเมื่อแปลงอีเมลเป็น HTML ด้วย GroupDocs.Viewer for Java](/viewer/advanced-rendering/rename-email-fields-when-converting-emails-to-html-java.png)

### สิ่งที่คุณจะได้เรียนรู้
- วิธีใช้ GroupDocs.Viewer for Java เพื่อ **แปลงอีเมลเป็น HTML**.  
- เทคนิคการ **เปลี่ยนชื่อฟิลด์อีเมล** เช่น “From,” “To,” “Sent,” และ “Subject.”  
- แนวปฏิบัติที่ดีที่สุดสำหรับการตั้งค่า Maven และการจัดการลิขสิทธิ์.  
- สถานการณ์จริงที่ **การปรับแต่งส่วนหัวของอีเมล** เพิ่มมูลค่าให้กับโครงการของคุณ.

## คำตอบอย่างรวดเร็ว
- **“convert email to HTML” หมายถึงอะไร?** หมายถึงการแสดงไฟล์อีเมล (MSG/EML) เป็นเอกสาร HTML ที่พร้อมใช้งานบนเว็บ.  
- **ไลบรารีใดรับหน้าที่แปลง?** GroupDocs.Viewer for Java (v25.2+).  
- **ต้องมีลิขสิทธิ์หรือไม่?** สามารถใช้รุ่นทดลองเพื่อประเมินผล; ต้องมีลิขสิทธิ์เต็มสำหรับการใช้งานในสภาพแวดล้อมจริง.  
- **สามารถเปลี่ยนชื่อส่วนหัวใดก็ได้หรือไม่?** ได้, ส่วนหัวอีเมลมาตรฐานใดก็สามารถแมปใหม่ได้ผ่าน `fieldTextMap`.  
- **ผลลัพธ์เป็น HTML หรือทรัพยากรฝังตัว?** คุณสามารถเลือกใช้ทรัพยากรฝังตัวเพื่อให้ได้ไฟล์เดียวที่มีทุกอย่างรวมอยู่.

## “convert email to HTML” ในบริบทของ GroupDocs.Viewer คืออะไร?
การแปลงอีเมลเป็น HTML หมายถึงการนำไฟล์อีเมลดิบมาผลิตหน้า HTML ที่แสดงเนื้อความของข้อความพร้อมกับเมตาดาต้า เมื่อคุณ **เปลี่ยนชื่อฟิลด์อีเมล** ด้วย, ป้ายกำกับเริ่มต้น (เช่น “From”) จะถูกแทนที่ด้วยข้อความที่กำหนดเอง (เช่น “Sender”), ซึ่งช่วยให้สอดคล้องกับคำศัพท์ขององค์กรหรือปรับปรุงความสอดคล้องของ UI.

## ทำไมต้องแปลงอีเมลเป็น HTML และเปลี่ยนชื่อฟิลด์อีเมล?
- **การสร้างแบรนด์ที่สอดคล้อง:** ทำให้ผลลัพธ์สอดคล้องกับภาษาขององค์กรของคุณ.  
- **การค้นหาได้ดีขึ้น:** ส่วนหัวที่กำหนดเองสามารถทำดัชนีได้มีประสิทธิภาพมากขึ้นในระบบจัดเก็บ.  
- **การผสาน UI ที่ดีกว่า:** ปรับแต่งส่วน HTML ให้เข้ากับพอร์ทัลเว็บหรือแดชบอร์ดสนับสนุนได้อย่างราบรื่น.

## คำแนะนำเบื้องต้น

### ไลบรารีที่ต้องการ, เวอร์ชัน, และการพึ่งพา
- **GroupDocs.Viewer for Java** – เวอร์ชัน 25.2 หรือใหม่กว่า.  
- **Java Development Kit (JDK)** – เวอร์ชัน 8+.

### ความต้องการในการตั้งค่าสภาพแวดล้อม
- **Maven** สำหรับการจัดการการพึ่งพา.  
- IDE เช่น IntelliJ IDEA, Eclipse, หรือ VS Code.

### ความรู้พื้นฐานที่จำเป็น
ความคุ้นเคยกับ Java และ Maven จะช่วยให้คุณทำตามได้อย่างรวดเร็ว.

## การตั้งค่า GroupDocs.Viewer for Java

### การกำหนดค่า Maven
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

### ขั้นตอนการรับลิขสิทธิ์
- **ทดลองใช้ฟรี:** ดาวน์โหลดรุ่นทดลองจาก [GroupDocs Releases](https://releases.groupdocs.com/viewer/java/).  
- **ลิขสิทธิ์ชั่วคราว:** รับลิขสิทธิ์ชั่วคราวเพื่อสำรวจคุณสมบัติเต็มรูปแบบโดยไม่มีข้อจำกัดที่ [GroupDocs Temporary License](https://purchase.groupdocs.com/temporary-license/).  
- **ซื้อ:** สำหรับการใช้งานต่อเนื่อง, พิจารณาซื้อไลเซนส์ผ่าน [GroupDocs Purchase](https://purchase.groupdocs.com/buy).

### การเริ่มต้นและตั้งค่าเบื้องต้น
```java
import com.groupdocs.viewer.Viewer;

public class ViewerSetup {
    public static void main(String[] args) {
        try (Viewer viewer = new Viewer("path/to/your/document.msg")) {
            // Perform operations here
        }
    }
}
```
ปรับเส้นทางไฟล์ให้ชี้ไปที่ไฟล์ `.msg` ของคุณ.

## วิธีแปลงอีเมลเป็น HTML และเปลี่ยนชื่อฟิลด์ – ขั้นตอนโดยละเอียด

### 1. ตั้งค่าเส้นทางไดเรกทอรีผลลัพธ์
```java
import java.nio.file.Path;

Path outputDirectory = Utils.getOutputDirectoryPath("YOUR_OUTPUT_DIRECTORY");
```
*แทนที่ `"YOUR_OUTPUT_DIRECTORY"` ด้วยโฟลเดอร์ที่คุณต้องการให้ไฟล์ HTML ถูกบันทึก.*

### 2. กำหนดรูปแบบเส้นทางไฟล์หน้า
```java
Path pageFilePathFormat = outputDirectory.resolve("page_{0}.html");
```
*`{0}` จะถูกแทนที่ด้วยหมายเลขหน้าในระหว่างการเรนเดอร์.*

### 3. สร้างการแมปฟิลด์อีเมลไปยังชื่อใหม่
```java
import com.groupdocs.viewer.options.Field;
import java.util.HashMap;
import java.util.Map;

Map<Field, String> fieldTextMap = new HashMap<>();
fieldTextMap.put(Field.FROM, "Sender");
fieldTextMap.put(Field.TO, "Receiver");
fieldTextMap.put(Field.SENT, "Date");
fieldTextMap.put(Field.SUBJECT, "Topic");
```
*ที่นี่เราจะเปลี่ยนป้ายกำกับเริ่มต้นให้เป็นชื่อที่กำหนดเอง.*

### 4. กำหนดค่า HTML View Options
```java
import com.groupdocs.viewer.options.HtmlViewOptions;

HtmlViewOptions viewOptions = HtmlViewOptions.forEmbeddedResources(pageFilePathFormat);
viewOptions.getEmailOptions().setFieldTextMap(fieldTextMap);
```
*`forEmbeddedResources` จะบรรจุ CSS/JS ไว้ใน HTML, ส่วน `setFieldTextMap` จะนำชื่อส่วนหัวที่กำหนดเองไปใช้.*

### 5. เรนเดอร์อีเมลเป็น HTML
```java
try (Viewer viewer = new Viewer("YOUR_DOCUMENT_DIRECTORY/SAMPLE_MSG")) {
    viewer.view(viewOptions);
}
```
*แทนที่ `"YOUR_DOCUMENT_DIRECTORY/SAMPLE_MSG"` ด้วยเส้นทางจริงของไฟล์ MSG ของคุณ.*

#### เคล็ดลับการแก้ไขปัญหา
- ตรวจสอบว่าไดเรกทอรีผลลัพธ์สามารถเขียนได้.  
- ยืนยันว่าไฟล์ MSG ที่ระบุมีอยู่และเส้นทางถูกต้อง.  
- ใช้เวอร์ชัน GroupDocs.Viewer เดียวกัน (25.2) ตามที่ระบุใน Maven.

## การประยุกต์ใช้งานจริง
1. **รายงานอีเมลแบบกำหนดเอง:** ทำให้ส่วนหัวของอีเมลสอดคล้องกับคำศัพท์ขององค์กรเพื่อรายงานที่ชัดเจนยิ่งขึ้น.  
2. **ระบบจัดเก็บอีเมล:** ปรับปรุงการค้นหาโดยใช้ชื่อส่วนหัวที่เป็นมาตรฐาน.  
3. **แพลตฟอร์มสนับสนุนลูกค้า:** แสดงตั๋วด้วยป้ายกำกับส่วนหัวที่ปรับแต่งเพื่อประสบการณ์ของเจ้าหน้าที่ที่ดียิ่งขึ้น.

## พิจารณาด้านประสิทธิภาพ
- ปิดการใช้งานอ็อบเจ็กต์ `Viewer` ด้วย try‑with‑resources เพื่อคืนหน่วยความจำอย่างรวดเร็ว.  
- ทำการประเมินประสิทธิภาพของชุดข้อมูลขนาดใหญ่และพิจารณาประมวลผลอีเมลแบบสตรีมขนานหากจำเป็น.

## สรุป
คุณได้เรียนรู้ **วิธีแปลงอีเมลเป็น HTML** พร้อมกับ **การเปลี่ยนชื่อฟิลด์อีเมล** และ **การปรับแต่งส่วนหัวของอีเมล** ด้วย GroupDocs.Viewer for Java. เทคนิคนี้ให้คุณควบคุมการแสดงผลเมตาดาต้าอีเมลในผลลัพธ์ HTML ได้อย่างเต็มที่.

### ขั้นตอนต่อไป
- ทดลองแมปฟิลด์เพิ่มเติม (เช่น CC, BCC).  
- สำรวจรูปแบบการเรนเดอร์อื่น ๆ เช่น PDF หรือ PNG.  
- เยี่ยมชม [GroupDocs Documentation](https://docs.groupdocs.com/viewer/java/) เพื่อเรียนรู้เชิงลึกเกี่ยวกับ API.

## คำถามที่พบบ่อย

**Q: วิธีนี้ทำงานกับรูปแบบอีเมลอื่น ๆ เช่น EML หรือไม่?**  
A: ใช่, GroupDocs.Viewer รองรับไฟล์ MSG และ EML; ลอจิกการแมปฟิลด์เดียวกันใช้ได้กับทั้งสองรูปแบบ.

**Q: ฉันสามารถส่งออก HTML โดยไม่มีทรัพยากรฝังตัวได้หรือไม่?**  
A: คุณสามารถใช้ `HtmlViewOptions.forExternalResources(...)` หากต้องการไฟล์ CSS/JS แยกกัน.

**Q: เวอร์ชันของ GroupDocs.Viewer ที่ทดสอบคืออะไร?**  
A: โค้ดนี้ทดสอบกับ GroupDocs.Viewer **25.2**.

**Q: สามารถเปลี่ยนฟอนต์หรือสไตล์ของส่วนหัวที่กำหนดเองได้หรือไม่?**  
A: สามารถใช้ CSS ปรับสไตล์หลังการเรนเดอร์, หรือแทรก CSS กำหนดเองผ่าน `HtmlViewOptions.getResourcesPath()`.

**Q: จะดึงเส้นทางไฟล์ HTML ที่สร้างขึ้นโดยโปรแกรมได้อย่างไร?**  
A: เส้นทางไฟล์จะตามรูปแบบที่กำหนดใน `pageFilePathFormat`; คุณสามารถสร้างโดยใช้ `String.format` พร้อมหมายเลขหน้า.

## แหล่งข้อมูล
- **Documentation:** คู่มือฉบับเต็มพร้อมใช้งานที่ [GroupDocs Documentation](https://docs.groupdocs.com/viewer/java/).  
- **API Reference:** รายละเอียด API สามารถดูได้ที่ [GroupDocs API Reference](https://reference.groupdocs.com/viewer/java/).  
- **Download GroupDocs.Viewer:** ดาวน์โหลดเวอร์ชันล่าสุดผ่าน [Downloads Page](https://releases.groupdocs.com/viewer/java/).

---

**Last Updated:** 2026-03-24  
**Tested With:** GroupDocs.Viewer 25.2  
**Author:** GroupDocs