---
date: '2026-04-10'
description: เรียนรู้วิธีกำหนดค่าการบันทึกใน GroupDocs.Viewer สำหรับ Java รวมถึงวิธีเพิ่ม
  console logger และ file logger เพื่อการแสดงผลเอกสารที่ดียิ่งขึ้น.
keywords:
- how to configure logging
- add console logger
- add file logger
- java logging best practices
- html view options
title: วิธีตั้งค่าการบันทึกใน GroupDocs.Viewer สำหรับ Java
type: docs
url: /th/java/getting-started/groupdocs-viewer-java-logging-setup/
weight: 1
---

# วิธีกำหนดค่าการบันทึกใน GroupDocs.Viewer สำหรับ Java

ในบทแนะนำนี้ คุณจะได้เรียนรู้ **วิธีกำหนดค่าการบันทึก** ใน GroupDocs.Viewer สำหรับ Java ซึ่งจะให้ข้อมูลเชิงเวลาจริงเกี่ยวกับกระบวนการเรนเดอร์เอกสารและช่วยให้คุณแก้ไขปัญหาได้อย่างรวดเร็ว.

## คำตอบสั้น
- **การบันทึกให้ข้อมูลอะไร?** ข้อเสนอแนะเชิงเวลาจริงเกี่ยวกับการดำเนินการเรนเดอร์และรายละเอียดข้อผิดพลาด.  
- **ล็อกเกอร์ใดที่พิมพ์ออกที่คอนโซล?** `ConsoleLogger` (เพิ่มล็อกเกอร์คอนโซล).  
- **ล็อกเกอร์ใดที่เขียนลงไฟล์?** `FileLogger` (เพิ่มล็อกเกอร์ไฟล์).  
- **ฉันต้องมีลิขสิทธิ์เพื่อเปิดใช้งานการบันทึกหรือไม่?** ไม่จำเป็น, การบันทึกทำงานได้ทั้งในรุ่นทดลองและรุ่นที่มีลิขสิทธิ์.  
- **ฉันสามารถปรับแต่งรูปแบบการบันทึกได้หรือไม่?** ได้, โดยการขยายคลาสล็อกเกอร์.

## บทนำ
ปรับปรุงกระบวนการเรนเดอร์เอกสารของคุณในแอปพลิเคชัน Java ด้วย **GroupDocs.Viewer for Java** คู่มือนี้จะพาคุณผ่านการกำหนดค่าการบันทึกทั้งไปที่คอนโซลหรือไฟล์ เพื่อให้ได้ข้อมูลเชิงลึกที่สำคัญเกี่ยวกับการทำงานของการเรนเดอร์เอกสารของคุณ.

![การบันทึกคอนโซลและไฟล์ด้วย GroupDocs.Viewer สำหรับ Java](/viewer/getting-started/console-and-file-logging-java.png)

**ประเด็นการเรียนรู้สำคัญ:**
- กำหนดค่าการบันทึกใน GroupDocs.Viewer for Java.  
- ดำเนินการระบบบันทึกทั้งแบบคอนโซลและไฟล์.  
- เรนเดอร์เอกสารเป็น HTML พร้อมทรัพยากรฝังด้วย GroupDocs.Viewer.

## ข้อกำหนดเบื้องต้น
ตรวจสอบว่าคุณมี:

1. **ไลบรารีที่จำเป็น:**  
   - ไลบรารี GroupDocs.Viewer for Java (เวอร์ชัน 25.2 หรือใหม่กว่า).  

2. **ข้อกำหนดการตั้งค่าสภาพแวดล้อม:**  
   - ชุดพัฒนา Java (JDK) ที่ติดตั้งบนระบบของคุณ.  
   - สภาพแวดล้อมการพัฒนาแบบบูรณาการ (IDE) เช่น IntelliJ IDEA หรือ Eclipse.  

3. **ข้อกำหนดความรู้เบื้องต้น:**  
   - ความเข้าใจพื้นฐานของการเขียนโปรแกรม Java.  
   - ความคุ้นเคยกับ Maven สำหรับการจัดการการพึ่งพา.  

เมื่อคุณมีข้อกำหนดเหล่านี้ครบแล้ว คุณพร้อมที่จะตั้งค่า GroupDocs.Viewer สำหรับ Java!

## การตั้งค่า GroupDocs.Viewer สำหรับ Java
เพื่อใช้ GroupDocs.Viewer ให้เพิ่มเป็น dependency ในโปรเจกต์ของคุณโดยใช้ Maven ดังนี้:

### การตั้งค่า Maven
เพิ่มการกำหนดค่าดังต่อไปนี้ในไฟล์ `pom.xml` ของคุณ:
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

### การรับลิขสิทธิ์
- **ทดลองใช้ฟรี:** ดาวน์โหลดรุ่นทดลองใช้ฟรีจาก [GroupDocs Releases](https://releases.groupdocs.com/viewer/java/).  
- **ลิขสิทธิ์ชั่วคราว:** รับลิขสิทธิ์ชั่วคราวเพื่อยกเลิกข้อจำกัดการประเมินที่ [GroupDocs Temporary License](https://purchase.groupdocs.com/temporary-license/).  
- **ซื้อ:** สำหรับการเข้าถึงเต็มรูปแบบ พิจารณาซื้อไลเซนส์ที่ [GroupDocs Purchase](https://purchase.groupdocs.com/buy).

### การเริ่มต้นพื้นฐาน
เริ่มต้น GroupDocs.Viewer ด้วยรูปแบบต่อไปนี้:
```java
import com.groupdocs.viewer.Viewer;
import com.groupdocs.viewer.options.HtmlViewOptions;

// Initialize with sample PDF file and settings
try (Viewer viewer = new Viewer("path/to/your/document.pdf")) {
    HtmlViewOptions options = HtmlViewOptions.forEmbeddedResources("output_directory/page_{0}.html");
    viewer.view(options);
}
```

การตั้งค่านี้เป็นพื้นฐานสำหรับการกำหนดค่าการบันทึกที่ซับซ้อนยิ่งขึ้น.

## วิธีกำหนดค่าการบันทึก
สำรวจวิธี **เพิ่มล็อกเกอร์คอนโซล** และ **เพิ่มล็อกเกอร์ไฟล์** ด้วย GroupDocs.Viewer.

### ฟีเจอร์ 1: การบันทึกไปยังคอนโซล
#### ภาพรวม
การบันทึกไปยังคอนโซลให้ข้อเสนอแนะทันทีในเทอร์มินัลของคุณ มีประโยชน์ในระหว่างการพัฒนา หรือขั้นตอนการดีบัก.

#### ขั้นตอน
##### ขั้นตอนที่ 1: นำเข้าคลาสที่จำเป็น
```java
import com.groupdocs.viewer.Viewer;
import com.groupdocs.viewer.ViewerSettings;
import com.groupdocs.viewer.logging.ConsoleLogger;
import com.groupdocs.viewer.options.HtmlViewOptions;
```

##### ขั้นตอนที่ 2: ตั้งค่าการบันทึก
ใช้ `ConsoleLogger` เพื่อส่งบันทึกไปยังคอนโซล.
```java
try (Viewer viewer = new Viewer("path/to/your/document.pdf", 
    new ViewerSettings(new ConsoleLogger()))) {
    HtmlViewOptions options = HtmlViewOptions.forEmbeddedResources("output_directory/page_{0}.html");
    viewer.view(options);
}
```
**คำอธิบาย**  
- **ConsoleLogger:** คลาสนี้ส่งบันทึกไปยังคอนโซล ให้มุมมองเชิงเวลาจริงของการดำเนินการ.  
- **HtmlViewOptions.forEmbeddedResources:** สร้าง HTML พร้อมทรัพยากรฝังสำหรับแต่ละหน้า เป็นตัวอย่างของการใช้ **html view options** อย่างมีประสิทธิภาพ.

#### เคล็ดลับการแก้ไขปัญหา
ตรวจสอบให้แน่ใจว่าเส้นทางไฟล์เอกสารของคุณถูกต้องและเข้าถึงได้ ตรวจสอบว่าคำสั่งบันทึกถูกกำหนดค่าอย่างเหมาะสมในการตั้งค่าคอนโซลของคุณ.

### ฟีเจอร์ 2: การบันทึกไปยังไฟล์
#### ภาพรวม
การบันทึกไปยังไฟล์ช่วยรักษาบันทึกการดำเนินการอย่างต่อเนื่อง มีประโยชน์สำหรับการตรวจสอบหรือการวิเคราะห์หลังเหตุการณ์.

#### ขั้นตอน
##### ขั้นตอนที่ 1: นำเข้าคลาสที่จำเป็น
```java
import com.groupdocs.viewer.Viewer;
import com.groupdocs.viewer.ViewerSettings;
import com.groupdocs.viewer.logging.FileLogger;
import com.groupdocs.viewer.options.HtmlViewOptions;
```

##### ขั้นตอนที่ 2: ตั้งค่าการบันทึกแบบไฟล์
ใช้ `FileLogger` เพื่อเขียนบันทึกลงไฟล์ที่ระบุ.
```java
try (Viewer viewer = new Viewer("path/to/your/document.pdf", 
    new ViewerSettings(new FileLogger("output.log")))) {
    HtmlViewOptions options = HtmlViewOptions.forEmbeddedResources("output_directory/page_{0}.html");
    viewer.view(options);
}
```
**คำอธิบาย**  
- **FileLogger:** คลาสนี้ส่งบันทึกไปยังไฟล์ชื่อ `output.log`.  
- **ViewerSettings with FileLogger:** กำหนดค่า GroupDocs.Viewer เพื่อ **บันทึกล็อกของ viewer** ในไฟล์ล็อกที่ระบุ.

#### เคล็ดลับการแก้ไขปัญหา
ตรวจสอบให้แน่ใจว่าไดเรกทอรีสำหรับไฟล์ผลลัพธ์สามารถเขียนได้ ตรวจสอบสิทธิ์ไฟล์หากการบันทึกล้มเหลว.

## การประยุกต์ใช้งานจริง
GroupDocs.Viewer สามารถเพิ่มประสิทธิภาพการจัดการเอกสารและความสามารถในการเรนเดอร์ได้:
1. **Web Portals:** เรนเดอร์เอกสารแบบเรียลไทม์สำหรับผู้ใช้เว็บโดยไม่ต้องดาวน์โหลดโดยตรง.  
2. **Enterprise Systems:** ผสานรวมกับเครื่องมือ CRM เพื่อแสดงสัญญาหรือข้อตกลง.  
3. **Internal Dashboards:** ให้มุมมองที่เข้าถึงได้ของรายงานและการนำเสนอภายในอินทราเน็ต.

## ข้อควรพิจารณาด้านประสิทธิภาพและแนวทางปฏิบัติที่ดีที่สุดของ Java Logging
เมื่อใช้ GroupDocs.Viewer ใน Java ให้คำนึงถึงจุดต่อไปนี้:
- **Optimize Resource Usage:** ตรวจสอบการใช้หน่วยความจำเมื่อเรนเดอร์เอกสารขนาดใหญ่.  
- **Java Memory Management:** ใช้ try‑with‑resources เพื่อทำความสะอาดทรัพยากรโดยอัตโนมัติ.  
- **Logging Verbosity:** ปรับระดับของล็อกเกอร์ (เช่น INFO, DEBUG) เพื่อสมดุลระหว่างรายละเอียดกับผลกระทบต่อประสิทธิภาพ — เป็นส่วนสำคัญของ **java logging best practices**.  

## สรุป
คุณได้เรียนรู้ **วิธีกำหนดค่าการบันทึก** ใน GroupDocs.Viewer สำหรับ Java ไม่ว่าจะต้องการมุมมองคอนโซลแบบเร็วหรือบันทึกไฟล์แบบถาวร ความสามารถนี้มีค่าสำหรับการดีบัก, การเฝ้าติดตาม, และการตรวจสอบแอปพลิเคชันของคุณ สำรวจการกำหนดค่าเพิ่มเติม, ทดลองกับล็อกเกอร์แบบกำหนดเอง, และผสานรวม GroupDocs.Viewer กับระบบอื่นเพื่อเพิ่มความทนทาน.

พร้อมที่จะยกระดับทักษะการใช้งานของคุณหรือยัง? ลองตั้งค่าการบันทึกในสภาพแวดล้อมต่าง ๆ และสังเกตว่ามันช่วยเพิ่มความเชื่อถือได้ของแอปพลิเคชันของคุณอย่างไร!

## แหล่งข้อมูล
- [เอกสาร](https://docs.groupdocs.com/viewer/java/)
- [อ้างอิง API](https://reference.groupdocs.com/viewer/java/)
- [ดาวน์โหลด](https://downloads.groupdocs.com/viewer/java/)

---

**อัปเดตล่าสุด:** 2026-04-10  
**ทดสอบด้วย:** GroupDocs.Viewer 25.2 for Java  
**ผู้เขียน:** GroupDocs