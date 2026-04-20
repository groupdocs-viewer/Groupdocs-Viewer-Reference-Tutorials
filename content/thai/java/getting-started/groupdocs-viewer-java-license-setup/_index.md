---
date: '2026-03-08'
description: เรียนรู้วิธีรับใบอนุญาตชั่วคราว, ตั้งค่า GroupDocs.Viewer สำหรับ Java
  ด้วยไฟล์ในเครื่องหรือ URL, และตรวจสอบความพร้อมของเส้นทางใบอนุญาต.
keywords:
- GroupDocs.Viewer Java license
- setting license in Java
- HTTP URL-based licenses
title: วิธีรับใบอนุญาตชั่วคราวและตั้งค่าใบอนุญาตใน GroupDocs.Viewer Java
type: docs
url: /th/java/getting-started/groupdocs-viewer-java-license-setup/
weight: 1
---

# วิธีรับใบอนุญาตชั่วคราวและตั้งค่าใบอนุญาตใน GroupDocs.Viewer Java

การจัดการใบอนุญาตอย่างมีประสิทธิภาพเป็นสิ่งสำคัญเมื่อผสานรวมไลบรารีของบุคคลที่สามเช่น **GroupDocs.Viewer for Java** เข้ากับแอปพลิเคชันของคุณ คู่มือนี้จะแสดงให้คุณ **วิธีรับใบอนุญาตชั่วคราว**, ตั้งค่าโดยใช้ไฟล์ในเครื่องหรือ HTTP URL, และตรวจสอบว่าเส้นทางของใบอนุญาตถูกต้องหรือไม่ เมื่อจบบทเรียนนี้คุณจะมีการตั้งค่าใบอนุญาตที่เชื่อถือได้และพร้อมใช้งานในสภาพแวดล้อมการผลิต ซึ่งทำให้แอปของคุณเป็นไปตามข้อกำหนดและมีประสิทธิภาพ

![File and URL Setup with GroupDocs.Viewer for Java](/viewer/getting-started/file-and-url-setup-png.png)

## คำตอบด่วน
- **ฉันจะรับใบอนุญาตชั่วคราวได้อย่างไร?** ขอรับจากหน้า temporary‑license ของ GroupDocs และดาวน์โหลดไฟล์ *.lic*  
- **ฉันสามารถโหลดใบอนุญาตจาก URL ได้หรือไม่?** ใช่ – เพียงแค่ชี้ `License.setLicense` ไปที่ที่อยู่ HTTP ที่ส่งคืนไฟล์ใบอนุญาตที่ถูกต้อง  
- **จะเกิดอะไรขึ้นหากเส้นทางของใบอนุญาตหายไป?** ทำการตรวจสอบเพื่อแสดงคำแนะนำและป้องกันไม่ให้ viewer เริ่มทำงาน  
- **ฉันต้องรีสตาร์ทแอปหลังจากเปลี่ยนใบอนุญาตหรือไม่?** ไม่, `License.setLicense` สามารถเรียกใช้ได้ในระหว่างทำงาน  
- **ต้องการเวอร์ชัน Java ใด?** แนะนำให้ใช้ JDK 8 หรือสูงกว่า

## ใบอนุญาตชั่วคราวคืออะไร?
ใบอนุญาต **temporary license** คือคีย์ที่มีอายุจำกัดที่ออกโดย GroupDocs ซึ่งทำให้คุณสามารถประเมินผลิตภัณฑ์ได้โดยไม่ต้องซื้อใบอนุญาตเต็มรูปแบบ มันทำงานเหมือนกับใบอนุญาตถาวรในช่วงที่ยังมีผลใช้งาน, ทำให้คุณสามารถทดสอบคุณสมบัติทั้งหมดในสภาพแวดล้อมจริง

## ทำไมต้องรับใบอนุญาตชั่วคราว?
- **การประเมินอย่างรวดเร็ว:** รับฟังก์ชันเต็มรูปแบบทันทีสำหรับโครงการ proof‑of‑concept.  
- **ไม่มีข้อผูกมัดทางการเงิน:** ทดสอบก่อนซื้อ.  
- **การผสานรวมที่ง่าย:** ทำงานร่วมกับการเรียก API เดียวกับใบอนุญาตถาวร.

## ข้อกำหนดเบื้องต้น
1. **Java Development Kit (JDK):** เวอร์ชัน 8 หรือสูงกว่า.  
2. **IDE:** IntelliJ IDEA, Eclipse หรือ IDE ที่เข้ากันได้กับ Java ใด ๆ.  
3. **GroupDocs.Viewer for Java library:** เพิ่มลงในโปรเจคของคุณ (ดูการตั้งค่า Maven ด้านล่าง).  
4. **Basic Java knowledge:** ความคุ้นเคยกับคลาส, การนำเข้า, และการจัดการข้อยกเว้น.

## การตั้งค่า GroupDocs.Viewer for Java
เพื่อเริ่มต้น, ให้รวมไลบรารีนี้ในโปรเจค Maven ของคุณ

### การกำหนดค่า Maven
Add the following configuration to your `pom.xml` file:
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

### การรับใบอนุญาต
To use GroupDocs.Viewer, obtain a license:
- **Free Trial:** ดาวน์โหลดจาก [GroupDocs site](https://releases.groupdocs.com/viewer/java/).  
- **Temporary License:** ขอรับจาก [temporary-license page](https://purchase.groupdocs.com/temporary-license/).  
- **Purchase:** สำหรับโซลูชันถาวร, พิจารณาซื้อใบอนุญาตจาก [GroupDocs purchase page](https://purchase.groupdocs.com/buy).

### การเริ่มต้นพื้นฐาน
Once the library is added, you can initialize the viewer:
```java
import com.groupdocs.viewer.License;

public class InitializeViewer {
    public static void main(String[] args) {
        License license = new License();
        // Set the path to your license file or URL here
        license.setLicense("YOUR_LICENSE_PATH");
        System.out.println("GroupDocs.Viewer initialized successfully.");
    }
}
```

## วิธีรับใบอนุญาตชั่วคราวและตั้งค่าจากไฟล์
### ภาพรวม
การตั้งค่าใบอนุญาตจากไฟล์ในเครื่องเป็นวิธีที่ตรงไปตรงมาที่สุดและทำงานได้แม้แอปพลิเคชันทำงานแบบออฟไลน์

### ขั้นตอนการดำเนินการ
1. **กำหนดเส้นทางใบอนุญาต** – ชี้ไปที่ไฟล์ *.lic* ที่คุณได้รับหลังจากขอใบอนุญาตชั่วคราว:
```java
final String licensePath = "YOUR_DOCUMENT_DIRECTORY/your-license-file.lic";
```
2. **ใช้ใบอนุญาต** – ใช้คลาส `License` เพื่อโหลดมัน:
```java
import com.groupdocs.viewer.License;

public class SetLicenseFromFile {
    public static void run() {
        if (licensePath != null && !licensePath.startsWith("http")) {
            License license = new License();
            license.setLicense(licensePath);
            System.out.println("License set successfully.");
        } else {
            // Handle cases where the path is not valid
            System.err.println(
                "We do not ship any license with this example.\n" +
                "Visit the GroupDocs site to obtain either a temporary or permanent license.\n" +
                "Learn more about licensing at https://purchase.groupdocs.com/faqs/licensing.\n" +
                "Lear how to request temporary license at https://purchase.groupdocs.com/temporary-license.");
        }
    }
}
```
**เคล็ดลับ:**  
- ตรวจสอบว่าเส้นทางไฟล์เป็นแบบ absolute หรือ relative กับ working directory.  
- ให้แน่ใจว่าไฟล์มีสิทธิ์อ่านสำหรับผู้ใช้ที่รัน JVM.

## วิธีจัดการใบอนุญาตจาก URL
### ภาพรวม
ใบอนุญาตที่อ้างอิงจาก URL มีประโยชน์สำหรับการปรับใช้บนคลาวด์ที่ไฟล์ใบอนุญาตอยู่ในบัคเก็ตจัดเก็บที่ปลอดภัย

### ขั้นตอนการดำเนินการ
1. **กำหนด URL ของใบอนุญาต** – แทนที่ตัวแปรตำแหน่งด้วย endpoint ของคุณจริง:
```java
final String licensePath = "http://example.com/license.lic";
```
2. **ตรวจจับและบันทึกการใช้ URL** – ตัวอย่างด้านล่างจะแจ้งให้คุณทราบว่ามีการส่ง URL:
```java
public class HandleLicenseURL {
    public static void run() {
        if (licensePath != null && licensePath.startsWith("http")) {
            System.err.println("License path was not provided, license URL is found instead!");
        }
    }
}
```
**เคล็ดลับ:**  
- ใน production คุณจะต้องดาวน์โหลดไฟล์ (เช่น ด้วย `java.net.HttpURLConnection`) แล้วเรียก `license.setLicense(stream)`.  
- เพิ่ม logic การลองใหม่และการจัดการ timeout เพื่อรับมือกับปัญหาเครือข่ายชั่วคราว.

## วิธีตรวจสอบการมีอยู่ของใบอนุญาต (ตรวจสอบเส้นทางใบอนุญาต)
### ภาพรวม
ก่อนที่จะพยายามโหลดใบอนุญาต, ควรทำ **การตรวจสอบการมีอยู่ของใบอนุญาต** เพื่อให้คุณสามารถแนะนำนักพัฒนา หรือผู้ใช้ให้รับใบอนุญาตชั่วคราวเมื่อจำเป็น

### ขั้นตอนการดำเนินการ
1. **จำลองเส้นทางใบอนุญาตที่หายไป**:
```java
final String licensePath = null;
```
2. **ให้คำแนะนำที่ชัดเจนหากเส้นทางไม่มี**:
```java
public class CheckLicensePathAvailability {
    public static void run() {
        if (licensePath == null) {
            System.out.println(
                "\nWe do not ship any license with this example.\n" +
                "Visit the GroupDocs site to obtain either a temporary or permanent license.\n" +
                "Learn more about licensing at https://purchase.groupdocs.com/faqs/licensing.\n" +
                "Lear how to request temporary license at https://purchase.groupdocs.com/temporary-license.");
        }
    }
}
```
**เคล็ดลับ:**  
- บันทึกข้อความนี้ตอนเริ่มต้นเพื่อให้ทีม ops รู้ว่าใบอนุญาตหายไป.  
- พิจารณาออกจากแอปหรือปิดการทำงานของฟีเจอร์ viewer จนกว่าจะมีใบอนุญาตที่ถูกต้อง.

## การประยุกต์ใช้งานจริง
การเข้าใจวิธี **รับใบอนุญาตชั่วคราว**, ตั้งค่าจากไฟล์หรือ URL, และ **ตรวจสอบเส้นทางใบอนุญาต** จะเปิดประตูสู่หลายสถานการณ์ในโลกจริง:
1. **Document Management Systems** – ฝัง viewer ที่ตรวจสอบใบอนุญาตโดยอัตโนมัติในแต่ละครั้งที่เปิดใช้งาน.  
2. **Cloud SaaS Platforms** – เก็บใบอนุญาตใน blob storage ที่ปลอดภัยและโหลดผ่าน URL เพื่ออัปเดตโดยไม่มี downtime.  
3. **Enterprise Deployments** – ใช้ใบอนุญาตชั่วคราวในช่วง pilot ก่อนซื้อใบอนุญาตเต็มรูปแบบ.

## พิจารณาด้านประสิทธิภาพ
- **Resource usage:** โหลดใบอนุญาตครั้งเดียวที่การเริ่มต้นแอป; การเรียกซ้ำจะเพิ่ม I/O ที่ไม่จำเป็น.  
- **Memory management:** วัตถุ `License` เก็บสถานะน้อยที่สุด, แต่ควรปิด stream เสมอหากดาวน์โหลดใบอนุญาตด้วยตนเอง.

## สรุป
โดยทำตามขั้นตอนข้างต้นคุณสามารถ **รับใบอนุญาตชั่วคราว**, ตั้งค่า GroupDocs.Viewer for Java ด้วยไฟล์ในเครื่องหรือ HTTP URL, และ **ตรวจสอบการมีอยู่ของใบอนุญาต** เพื่อให้แอปของคุณเป็นไปตามข้อกำหนด พื้นฐานการจัดการใบอนุญาตที่แข็งแรงนี้ช่วยป้องกันข้อผิดพลาดระหว่างรันไทม์และให้ความยืดหยุ่นในการย้ายระหว่างสภาพแวดล้อมการพัฒนา, การทดสอบ, และการผลิตด้วยความมั่นใจ

### คำถามที่พบบ่อย

1. **ฉันจะตั้งค่าไฟล์ใบอนุญาตในเครื่องใน GroupDocs.Viewer Java อย่างไร?**  

   ใช้ `license.setLicense("path/to/license.lic")` พร้อมเส้นทางไฟล์ที่ถูกต้องเพื่อใช้ใบอนุญาตในเครื่อง

2. **ฉันสามารถโหลดใบอนุญาตโดยตรงจาก URL ได้หรือไม่?**  

   ได้, แต่ต้องแน่ใจว่าโค้ดของคุณจัดการการเข้าถึง URL, อาจดาวน์โหลดใบอนุญาตใน runtime หรือจัดการปัญหาเครือข่าย

3. **ฉันควรทำอย่างไรหากเส้นทางใบอนุญาตไม่ถูกต้องหรือหายไป?**  

   ทำการตรวจสอบค่า null หรือเส้นทางที่ไม่ถูกต้องและให้คำแนะนำหรือข้อความ fallback เพื่อรับใบอนุญาตที่ถูกต้อง

4. **สามารถสลับระหว่างไฟล์ใบอนุญาตและ URL ได้อย่างไดนามิกหรือไม่?**  

   แน่นอน, โดยเพิ่มเงื่อนไข logic เพื่อจัดการทั้งสองกรณีตามสภาพแวดล้อมหรือพารามิเตอร์ runtime

5. **แนวทางปฏิบัติที่ดีที่สุดสำหรับการจัดการใบอนุญาตใน production คืออะไร?**  

   เก็บใบอนุญาตอย่างปลอดภัย, ตรวจสอบความถูกต้องเป็นระยะ, และจัดการข้อผิดพลาดของใบอนุญาตเพื่อให้บริการต่อเนื่อง

## คำถามที่พบบ่อย

**Q: ใบอนุญาตชั่วคราวมีอายุเท่าไหร่?**  
A: ปกติ 30 วัน, หลังจากนั้นคุณสามารถขอการต่ออายุหรืออัปเกรดเป็นใบอนุญาตถาวรได้

**Q: ฉันต้องการการเชื่อมต่ออินเทอร์เน็ตเพื่อใช้ใบอนุญาตแบบไฟล์หรือไม่?**  
A: ไม่. ไฟล์ *.lic* ในเครื่องทำงานแบบออฟไลน์ได้อย่างสมบูรณ์หลังจากโหลดแล้ว

**Q: ฉันสามารถเข้ารหัสไฟล์ใบอนุญาตเพื่อความปลอดภัยเพิ่มได้หรือไม่?**  
A: ไฟล์ใบอนุญาตได้รับการเซ็นโดย GroupDocs แล้ว; การเข้ารหัสเพิ่มเติมเป็นทางเลือกแต่ไม่จำเป็น

**Q: จะเกิดอะไรขึ้นหากใบอนุญาตหมดอายุขณะแอปกำลังทำงาน?**  
A: การทำงานของ Viewer จะเริ่มโยนข้อยกเว้นเรื่องใบอนุญาต; แนะนำให้ตรวจสอบวันหมดอายุตอนเริ่มต้น

**Q: การเก็บ URL ของใบอนุญาตใน source control ปลอดภัยหรือไม่?**  
A: ควรหลีกเลี่ยงการคอมมิต URL ที่สำคัญ; ใช้ environment variables หรือที่เก็บค่าคอนฟิกที่ปลอดภัยแทน

---

**Last Updated:** 2026-03-08  
**Tested With:** GroupDocs.Viewer 25.2 for Java  
**Author:** GroupDocs