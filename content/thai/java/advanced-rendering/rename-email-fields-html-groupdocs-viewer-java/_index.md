---
date: '2026-01-05'
description: เรียนรู้วิธีการเปลี่ยนชื่อฟิลด์อีเมล, แปลงอีเมลเป็น HTML, และปรับแต่งส่วนหัวของอีเมลโดยใช้
  GroupDocs.Viewer สำหรับ Java.
keywords:
- rename email fields Java
- render emails HTML GroupDocs Viewer
- customize email metadata Java
title: วิธีเปลี่ยนชื่อฟิลด์อีเมลเมื่อแปลงอีเมลเป็น HTML ด้วย GroupDocs.Viewer Java
type: docs
url: /th/java/advanced-rendering/rename-email-fields-html-groupdocs-viewer-java/
weight: 1
---

# วิธีการเปลี่ยนชื่อฟิลด์อีเมลเมื่อแสดงอีเมลเป็น HTML ด้วย GroupDocs.Viewer Java

คุณกำลังสงสัย **วิธีการเปลี่ยนชื่ออีเมล** ฟิลด์ขณะแปลงอีเมลเป็น HTML หรือไม่? ในคู่มือนี้เราจะอธิบายขั้นตอนที่แน่นอนเพื่อเปลี่ยนชื่อฟิลด์อีเมล, **แปลงอีเมลเป็น HTML**, และ **ปรับแต่งหัวข้ออีเมล** ด้วย GroupDocs.Viewer for Java. เมื่อเสร็จคุณจะได้การแสดงผล HTML ที่สะอาดพร้อมชื่อหัวข้อที่คุณต้องการ ทำให้ผลลัพธ์อ่านง่ายและสามารถรวมเข้ากับแอปพลิเคชันของคุณได้.

![เปลี่ยนชื่อฟิลด์อีเมลเมื่อแปลงอีเมลเป็น HTML ด้วย GroupDocs.Viewer for Java](/viewer/advanced-rendering/rename-email-fields-when-converting-emails-to-html-java.png)

### สิ่งที่คุณจะได้เรียนรู้
- วิธีใช้ GroupDocs.Viewer for Java เพื่อ **แปลงอีเมลเป็น HTML**.  
- เทคนิคการ **เปลี่ยนชื่อฟิลด์อีเมล** เช่น “From,” “To,” “Sent,” และ “Subject.”  
- แนวปฏิบัติที่ดีที่สุดสำหรับการตั้งค่า Maven และการจัดการลิขสิทธิ์.  
- สถานการณ์จริงที่ **การปรับแต่งหัวข้ออีเมล** เพิ่มคุณค่า.

## คำตอบสั้น
- **“วิธีการเปลี่ยนชื่ออีเมล” หมายถึงอะไร?** หมายถึงการแมปชื่อหัวข้ออีเมลเริ่มต้นไปยังป้ายกำกับที่กำหนดเองระหว่างการแสดงผล.  
- **ไลบรารีใดที่จัดการการแปลง?** GroupDocs.Viewer for Java (v25.2+).  
- **ฉันต้องการลิขสิทธิ์หรือไม่?** รุ่นทดลองทำงานสำหรับการประเมิน; จำเป็นต้องมีลิขสิทธิ์เต็มสำหรับการใช้งานจริง.  
- **ฉันสามารถเปลี่ยนชื่อหัวข้อใดก็ได้หรือไม่?** ใช่, สามารถแมปหัวข้ออีเมลมาตรฐานใดก็ได้ผ่าน `fieldTextMap`.  
- **ผลลัพธ์เป็น HTML หรือทรัพยากรฝังตัว?** คุณสามารถเลือกทรัพยากรฝังตัวสำหรับไฟล์เดียวที่เป็นอิสระ.

## “วิธีการเปลี่ยนชื่ออีเมล” หมายถึงอะไรในบริบทของ GroupDocs.Viewer?
การเปลี่ยนชื่อฟิลด์อีเมลหมายถึงการแทนที่ป้ายกำกับเริ่มต้น (เช่น “From”) ด้วยข้อความที่กำหนดเอง (เช่น “Sender”) เมื่ออีเมลถูกแสดงเป็น HTML. สิ่งนี้มีประโยชน์สำหรับการทำให้ผลลัพธ์สอดคล้องกับศัพท์ขององค์กรหรือปรับปรุงความอ่านง่ายของผู้ใช้ปลายทาง.

## ทำไมต้องแปลงอีเมลเป็น HTML และปรับแต่งหัวข้ออีเมล?
- **Consistent branding:** ทำให้ภาษาขององค์กรสอดคล้องกันในทุกการสื่อสาร.  
- **Improved searchability:** หัวข้อที่กำหนดเองสามารถทำดัชนีได้มีประสิทธิภาพมากขึ้นในระบบจัดเก็บ.  
- **Better UI integration:** ปรับแต่งส่วน HTML ให้เข้ากับพอร์ทัลเว็บหรือแดชบอร์ดสนับสนุนได้อย่างราบรื่น.

## ข้อกำหนดเบื้องต้น

### ไลบรารีที่จำเป็น, เวอร์ชัน, และการพึ่งพา
- **GroupDocs.Viewer for Java** – version 25.2 or later.  
- **Java Development Kit (JDK)** – version 8+.

### ความต้องการในการตั้งค่าสภาพแวดล้อม
- **Maven** for dependency management.  
- An IDE such as IntelliJ IDEA, Eclipse, or VS Code.

### ความรู้เบื้องต้นที่จำเป็น
ความคุ้นเคยกับ Java และ Maven จะช่วยให้คุณตามขั้นตอนได้อย่างรวดเร็ว.

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
- **Free Trial:** ดาวน์โหลดรุ่นทดลองฟรีจาก [GroupDocs Releases](https://releases.groupdocs.com/viewer/java/).  
- **Temporary License:** รับลิขสิทธิ์ชั่วคราวเพื่อสำรวจคุณสมบัติเต็มรูปแบบโดยไม่มีข้อจำกัดที่ [GroupDocs Temporary License](https://purchase.groupdocs.com/temporary-license/).  
- **Purchase:** สำหรับการใช้งานต่อเนื่อง พิจารณาซื้อไลเซนส์ผ่าน [GroupDocs Purchase](https://purchase.groupdocs.com/buy).

### การเริ่มต้นและตั้งค่าพื้นฐาน
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
ปรับเส้นทางไฟล์ให้ชี้ไปยังไฟล์ `.msg` ของคุณ.

## คู่มือการใช้งาน

### การเปลี่ยนชื่อฟิลด์อีเมล – ขั้นตอนโดยละเอียด

#### 1. ตั้งค่าเส้นทางไดเรกทอรีผลลัพธ์
```java
import java.nio.file.Path;

Path outputDirectory = Utils.getOutputDirectoryPath("YOUR_OUTPUT_DIRECTORY");
```
*แทนที่ `"YOUR_OUTPUT_DIRECTORY"` ด้วยโฟลเดอร์ที่คุณต้องการบันทึกไฟล์ HTML.*

#### 2. กำหนดรูปแบบเส้นทางไฟล์หน้า
```java
Path pageFilePathFormat = outputDirectory.resolve("page_{0}.html");
```
*`{0}` จะถูกแทนที่ด้วยหมายเลขหน้าขณะทำการแสดงผล.*

#### 3. สร้างการแมปฟิลด์อีเมลไปยังชื่อใหม่
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
*ที่นี่เราจะเปลี่ยนป้ายกำกับเริ่มต้นเป็นชื่อที่กำหนดเอง.*

#### 4. กำหนดค่า HTML View Options
```java
import com.groupdocs.viewer.options.HtmlViewOptions;

HtmlViewOptions viewOptions = HtmlViewOptions.forEmbeddedResources(pageFilePathFormat);
viewOptions.getEmailOptions().setFieldTextMap(fieldTextMap);
```
*`forEmbeddedResources` จะบรรจุ CSS/JS ไว้ใน HTML, ส่วน `setFieldTextMap` จะใช้ชื่อหัวข้อที่กำหนดเอง.*

#### 5. แสดงผลอีเมลเป็น HTML
```java
try (Viewer viewer = new Viewer("YOUR_DOCUMENT_DIRECTORY/SAMPLE_MSG")) {
    viewer.view(viewOptions);
}
```
*แทนที่ `"YOUR_DOCUMENT_DIRECTORY/SAMPLE_MSG"` ด้วยเส้นทางจริงไปยังไฟล์ MSG ของคุณ.*

#### เคล็ดลับการแก้ไขปัญหา
- ตรวจสอบว่าไดเรกทอรีผลลัพธ์สามารถเขียนได้.  
- ตรวจสอบว่าไฟล์ MSG อินพุตมีอยู่และเส้นทางถูกต้อง.  
- ใช้เวอร์ชัน GroupDocs.Viewer เดียวกัน (25.2) ตามที่ระบุใน Maven.

## การประยุกต์ใช้งานจริง
1. **Custom Email Reports:** ปรับหัวข้ออีเมลให้สอดคล้องกับศัพท์ขององค์กรเพื่อรายงานที่ชัดเจนยิ่งขึ้น.  
2. **Email Archiving Systems:** ปรับปรุงการค้นหาโดยใช้ชื่อหัวข้อที่เป็นมาตรฐาน.  
3. **Customer Support Platforms:** แสดงตั๋วด้วยป้ายหัวข้อที่กำหนดเองเพื่อประสบการณ์ที่ดีกว่าสำหรับเจ้าหน้าที่.

## ข้อควรพิจารณาด้านประสิทธิภาพ
- ทำลายอ็อบเจกต์ `Viewer` ด้วย try‑with‑resources เพื่อคืนหน่วยความจำอย่างรวดเร็ว.  
- ทำการวิเคราะห์ประสิทธิภาพของชุดข้อมูลขนาดใหญ่และพิจารณาประมวลผลอีเมลใน parallel streams หากจำเป็น.

## สรุป
คุณตอนนี้รู้ **วิธีการเปลี่ยนชื่ออีเมล** ฟิลด์ขณะ **แปลงอีเมลเป็น HTML** และ **ปรับแต่งหัวข้ออีเมล** ด้วย GroupDocs.Viewer for Java. เทคนิคนี้ให้คุณควบคุมการนำเสนอเมตาดาต้าอีเมลในผลลัพธ์ HTML ได้อย่างเต็มที่.

### ขั้นตอนต่อไป
- ทดลองแมปฟิลด์เพิ่มเติม (เช่น CC, BCC).  
- สำรวจรูปแบบการแสดงผลอื่น ๆ เช่น PDF หรือ PNG.  
- เยี่ยมชม [GroupDocs Documentation](https://docs.groupdocs.com/viewer/java/) เพื่อรับข้อมูลเชิงลึกเกี่ยวกับ API.

## ส่วนคำถามที่พบบ่อย
1. **Can I rename all email headers using this method?**  
   - Yes, you can map any standard email header to a new name as per your requirements.  
2. **Is it possible to use GroupDocs.Viewer without a license?**  
   - A trial version is available for testing, but a full‑featured version requires a valid license.  
3. **How do I handle large volumes of emails efficiently with GroupDocs.Viewer?**  
   - Consider batch processing and optimize system resources to manage larger datasets effectively.  
4. **Can I integrate this solution into an existing Java application?**  
   - Absolutely, integration is straightforward using Maven dependencies.  
5. **Where can I find support if I encounter issues?**  
   - Visit the [GroupDocs Forum](https://forum.groupdocs.com/c/viewer/9) for community and official assistance.

## คำถามที่พบบ่อย
**Q: Does this approach work with other email formats like EML?**  
A: Yes, GroupDocs.Viewer supports both MSG and EML files; the same field‑mapping logic applies.

**Q: Can I output the HTML without embedded resources?**  
A: You can use `HtmlViewOptions.forExternalResources(...)` if you prefer separate CSS/JS files.

**Q: What version of GroupDocs.Viewer was tested?**  
A: The code was tested with GroupDocs.Viewer **25.2**.

**Q: Is it possible to change the font or style of the custom headers?**  
A: Styling can be applied via CSS after rendering, or you can inject custom CSS using `HtmlViewOptions.getResourcesPath()`.

**Q: How do I programmatically retrieve the generated HTML file path?**  
A: The file path follows the pattern defined in `pageFilePathFormat`; you can construct it using `String.format` with the page number.

## แหล่งข้อมูล
- **Documentation:** Comprehensive guides are available at [GroupDocs Documentation](https://docs.groupdocs.com/viewer/java/).  
- **API Reference:** Detailed API information can be found on [GroupDocs API Reference](https://reference.groupdocs.com/viewer/java/).  
- **Download GroupDocs.Viewer:** Access the latest version through the [Downloads Page](https://releases.groupdocs.com/viewer/java/).

---

**อัปเดตล่าสุด:** 2026-01-05  
**ทดสอบด้วย:** GroupDocs.Viewer 25.2  
**ผู้เขียน:** GroupDocs