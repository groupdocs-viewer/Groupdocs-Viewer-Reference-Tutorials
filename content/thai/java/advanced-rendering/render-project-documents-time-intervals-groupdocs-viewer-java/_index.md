---
date: '2026-03-29'
description: เรียนรู้วิธีสร้างมุมมอง HTML ของไฟล์ MPP ด้วย GroupDocs Viewer ใน Java
  โดยเรนเดอร์เอกสารโครงการตามช่วงเวลาแบบขั้นตอนด้วยโค้ดทีละขั้นตอน
keywords:
- render project documents
- time intervals Java
- GroupDocs Viewer API
title: สร้างมุมมอง HTML ของไฟล์ MPP ด้วย GroupDocs Viewer (Java)
type: docs
url: /th/java/advanced-rendering/render-project-documents-time-intervals-groupdocs-viewer-java/
weight: 1
---

# วิธีใช้ GroupDocs Viewer เพื่อแสดงเอกสารโครงการตามช่วงเวลาใน Java

ในบทเรียนนี้คุณจะได้เรียนรู้วิธี **create html view mpp** ด้วย GroupDocs Viewer สำหรับ Java ซึ่งช่วยให้คุณแสดงเฉพาะส่วนของไฟล์ Microsoft Project ที่อยู่ในช่วงเวลาที่กำหนด เราจะอธิบายการตั้งค่า Maven, การกำหนดค่าโค้ด, และสถานการณ์จริงเพื่อให้คุณสามารถฝังมุมมองไทม์ไลน์ที่แม่นยำลงในแอปพลิเคชันของคุณได้โดยตรง.

![Render Project Documents by Time Intervals with GroupDocs.Viewer for Java](/viewer/advanced-rendering/render-project-documents-by-time-intervals-java.png)

## คำตอบสั้น
- **ฟีเจอร์ทำอะไร?** มันจะแสดงเฉพาะส่วนของไฟล์ Microsoft Project ที่อยู่ระหว่างวันที่เริ่มต้นและวันที่สิ้นสุดเท่านั้น.  
- **รูปแบบผลลัพธ์ที่ใช้คืออะไร?** HTML พร้อมทรัพยากรฝังตัว เหมาะสำหรับการรวมเข้ากับเว็บ.  
- **ต้องการไลเซนส์หรือไม่?** เวอร์ชันทดลองฟรีใช้ได้สำหรับการประเมิน; จำเป็นต้องมีไลเซนส์เต็มสำหรับการใช้งานจริง.  
- **สามารถเปลี่ยนช่วงวันที่ระหว่างการทำงานได้หรือไม่?** ใช่—ปรับค่า `setStartDate` และ `setEndDate` ในตัวเลือกการเรนเดอร์.  
- **รองรับบนเวอร์ชัน Java ทั้งหมดหรือไม่?** ทำงานกับ Java 8+ ตราบใดที่คุณใช้ GroupDocs.Viewer 25.2 หรือใหม่กว่า.

## วิธีสร้าง html view mpp สำหรับเอกสารโครงการ
GroupDocs Viewer สามารถแปลงไฟล์ Microsoft Project (`.mpp`, `.mpt`) เป็นหน้า HTML ได้ โดยการกำหนดวันที่เริ่มต้นและสิ้นสุดในตัวเลือกการเรนเดอร์ คุณจะจำกัดผลลัพธ์ให้เป็นช่วงเวลาที่ต้องการ ซึ่งช่วยลดขนาดไฟล์และเร่งความเร็วการโหลดหน้าเว็บ.

## “How to Use GroupDocs” หมายถึงอะไรในบริบทนี้?
GroupDocs Viewer เป็นไลบรารี Java ที่แปลงไฟล์กว่า 100 รูปแบบเป็นการแสดงผลที่เป็นมิตรต่อเว็บ เมื่อคุณ **how to use GroupDocs** สำหรับไฟล์โครงการ คุณจะได้รับความสามารถในการดึงข้อมูล, แสดงผล, และแชร์ข้อมูลกำหนดเวลาโดยไม่ต้องใช้ Microsoft Project ที่ฝั่งคลไอเอนท์.

## ทำไมต้องแสดงเอกสารโครงการตามช่วงเวลา?
- **การวิเคราะห์ที่มุ่งเน้น:** แสดงเฉพาะเฟสที่คุณสนใจ (เช่น ไตรมาส 3 2024).  
- **ประสิทธิภาพ:** ผลลัพธ์ HTML ที่เล็กลงหมายถึงการโหลดหน้าเร็วขึ้น.  
- **การรวมระบบ:** ฝังมุมมองไทม์ไลน์ลงในแดชบอร์ด, พอร์ทัลรายงาน, หรือเครื่องมือ PM ที่กำหนดเอง.

## ข้อกำหนดเบื้องต้น
- **GroupDocs.Viewer for Java** เวอร์ชัน 25.2 หรือสูงกว่า.  
- Java Development Kit (JDK) 8 หรือใหม่กว่า.  
- IDE เช่น IntelliJ IDEA หรือ Eclipse.  
- ความรู้พื้นฐานเกี่ยวกับ Maven.

## การตั้งค่า GroupDocs.Viewer สำหรับ Java

### การพึ่งพา Maven
เพิ่ม repository และ dependency ลงในไฟล์ `pom.xml` ของคุณ:

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

### ขั้นตอนการรับไลเซนส์
1. **Free Trial** – ดาวน์โหลดเวอร์ชันทดลองจาก [GroupDocs' download page](https://releases.groupdocs.com/viewer/java/).  
2. **Temporary License** – รับไลเซนส์ชั่วคราวสำหรับการทดสอบต่อเนื่องผ่าน [this link](https://purchase.groupdocs.com/temporary-license/).  
3. **Purchase** – สำหรับการใช้งานผลิตภัณฑ์โดยไม่มีข้อจำกัด ให้ซื้อไลเซนส์ที่ [GroupDocs Purchase Page](https://purchase.groupdocs.com/buy).

### การเริ่มต้น Viewer เบื้องต้น
โค้ดตัวอย่างต่อไปนี้แสดงวิธีสร้างอินสแตนซ์ `Viewer` ที่ชี้ไปยังไฟล์ Microsoft Project (`.mpp`):

```java
import com.groupdocs.viewer.Viewer;

public class ViewerSetup {
    public static void main(String[] args) {
        try (Viewer viewer = new Viewer("path/to/your/document.mpp")) {
            // Your rendering code goes here
        }
    }
}
```

## คู่มือการดำเนินการแบบขั้นตอน

### 1. กำหนดไดเรกทอรีผลลัพธ์
สร้างโฟลเดอร์ที่หน้าตา HTML ที่สร้างขึ้นจะถูกบันทึกไว้:

```java
import java.nio.file.Path;

Path outputDirectory = Path.of("YOUR_OUTPUT_DIRECTORY", "RenderProjectTimeInterval");
Path pageFilePathFormat = outputDirectory.resolve("page_{0}.html");
```

*ทำไม?* การจัดระเบียบไฟล์ที่เรนเดอร์ทำให้สะดวกต่อการให้บริการจากเว็บเซิร์ฟเวอร์หรือฝังใน UI.

### 2. เริ่มต้น Viewer ด้วยไฟล์โครงการของคุณ
```java
try (Viewer viewer = new Viewer("YOUR_DOCUMENT_DIRECTORY/SAMPLE_MPP")) {
    // Continue with rendering steps
}
```

*ทำไม?* การโหลดเอกสารเตรียมตัวพาร์เซอร์ภายในและทำให้เมตาดาต้าเฉพาะโครงการเข้าถึงได้.

### 3. ดึงข้อมูลมุมมองสำหรับไฟล์โครงการ
```java
import com.groupdocs.viewer.options.ViewInfoOptions;
import com.groupdocs.viewer.results.ProjectManagementViewInfo;

ViewInfoOptions viewInfoOptions = ViewInfoOptions.forHtmlView();
ProjectManagementViewInfo viewInfo = (ProjectManagementViewInfo) viewer.getViewInfo(viewInfoOptions);
```

*ทำไม?* `ProjectManagementViewInfo` ให้วันที่เริ่มต้นและสิ้นสุดของกำหนดการ ซึ่งคุณจะใช้ต่อไปเพื่อจำกัดขอบเขตการเรนเดอร์.

### 4. กำหนดค่าตัวเลือกการเรนเดอร์ HTML (สร้าง HTML จากโครงการ)
```java
import com.groupdocs.viewer.options.HtmlViewOptions;

HtmlViewOptions viewOptions = HtmlViewOptions.forEmbeddedResources(pageFilePathFormat);
viewOptions.getProjectManagementOptions().setStartDate(viewInfo.getStartDate());
viewOptions.getProjectManagementOptions().setEndDate(viewInfo.getEndDate());
```

*ทำไม?* การตั้งค่า `StartDate` และ `EndDate` บอก GroupDocs ให้ **generate html view mpp** เฉพาะในช่วงเวลานั้น.

### 5. ดำเนินการเรนเดอร์
```java
viewer.view(viewOptions);
```

*ทำไม?* การเรียกนี้จะสร้างชุดของหน้า HTML ที่เป็นอิสระซึ่งแสดงช่วงเวลาที่เลือกของกำหนดการโครงการของคุณ.

## ข้อผิดพลาดทั่วไปและการแก้ไขปัญหา
- **Incorrect file paths** – ตรวจสอบให้แน่ใจว่าไฟล์ต้นฉบับ `.mpp` และไดเรกทอรีผลลัพธ์มีอยู่จริง.  
- **Unsupported file type** – ตรวจสอบว่าเอกสารเป็นรูปแบบ Project ที่รองรับ (เช่น `.mpp`, `.mpt`).  
- **License errors** – ไลเซนส์ทดลองอาจมีข้อจำกัดการเรนเดอร์; เปลี่ยนเป็นไลเซนส์เต็มเพื่อการใช้งานไม่จำกัด.

## การประยุกต์ใช้ในทางปฏิบัติ
1. **Project Timeline Analysis** – แสดงเฉพาะเฟสปัจจุบันให้ผู้มีส่วนได้ส่วนเสีย.  
2. **Automated Reporting** – สร้างรายงาน HTML ที่จำกัดช่วงเวลาเพื่ออัปเดตสถานะรายสัปดาห์.  
3. **Integration with Dashboards** – ฝังหน้าที่เรนเดอร์ลงในเครื่องมือ BI หรือพอร์ทัลที่กำหนดเอง.  
4. **Archival** – เก็บสแนปช็อตที่เป็นมิตรต่อเว็บของกำหนดการโครงการเพื่ออ้างอิงในอนาคต.

## เคล็ดลับด้านประสิทธิภาพ
- ใช้ตัวเลือก *embedded resources* เพื่อให้แต่ละหน้า HTML เป็นอิสระ ลดจำนวนคำขอ HTTP.  
- สำหรับโครงการขนาดใหญ่มาก พิจารณาเรนเดอร์เป็นช่วงวันที่เล็ก ๆ เพื่อลดการใช้หน่วยความจำ.  
- ทำความสะอาดไฟล์ชั่วคราวหลังการให้บริการเพื่อหลีกเลี่ยงการเพิ่มขนาดดิสก์.

## สรุป
ตอนนี้คุณรู้แล้วว่า **how to use GroupDocs** Viewer สามารถเรนเดอร์เอกสารโครงการภายในช่วงเวลาที่กำหนดและ **generate HTML from project** ใน Java ความสามารถนี้ช่วยให้การแสดงผลไทม์ไลน์เป็นไปอย่างราบรื่น, ปรับปรุงประสิทธิภาพการรายงาน, และรวมเข้ากับแอปพลิเคชันเว็บสมัยใหม่ได้อย่างลงตัว.

### ขั้นตอนต่อไป
- สำรวจฟีเจอร์ Viewer เพิ่มเติม เช่น การใส่ลายน้ำ, การป้องกันด้วยรหัสผ่าน, หรือการสไตล์ CSS ที่กำหนดเอง.  
- ผสานกระบวนการเรนเดอร์นี้กับ REST API เพื่อให้บริการมุมมองไทม์ไลน์ตามความต้องการ.

## คำถามที่พบบ่อย

**Q: GroupDocs.Viewer รองรับรูปแบบไฟล์อะไรบ้าง?**  
A: GroupDocs.Viewer รองรับรูปแบบไฟล์หลากหลายรวมถึง Microsoft Project (MPP), PDF, Word, Excel, PowerPoint, และอื่น ๆ อีกมากมาย.

**Q: จะเริ่มต้นใช้เวอร์ชันทดลองฟรีของ GroupDocs.Viewer อย่างไร?**  
A: คุณสามารถดาวน์โหลดเวอร์ชันทดลองจาก [here](https://releases.groupdocs.com/viewer/java/).

**Q: สามารถเรนเดอร์เอกสารโดยไม่ฝังทรัพยากรได้หรือไม่?**  
A: ได้ คุณสามารถเลือกตัวเลือก HTML view แบบอื่นที่อ้างอิงทรัพยากรภายนอกแทนการฝัง.

**Q: ถ้าเอกสารของฉันใหญ่เกินกว่าจะเรนเดอร์จะทำอย่างไร?**  
A: พิจารณาแบ่งเอกสารเป็นส่วนย่อยหรือเรนเดอร์เฉพาะช่วงวันที่ต้องการตามที่แสดงข้างต้น.

**Q: จะจัดการกับข้อผิดพลาดการเรนเดอร์อย่างไร?**  
A: ตรวจสอบการตั้งค่าทั้งหมด, ยืนยันว่ามีไลเซนส์ที่ถูกต้อง, และอ้างอิงเอกสาร GroupDocs เพื่อดูรหัสข้อผิดพลาดโดยละเอียด.

## แหล่งข้อมูล
- **Documentation**: [GroupDocs Viewer Java Documentation](https://docs.groupdocs.com/viewer/java/)  
- **API Reference**: [GroupDocs API Reference](https://reference.groupdocs.com/viewer/java/)  
- **Download**: [GroupDocs Downloads](https://releases.groupdocs.com/viewer/java/)  
- **Purchase**: [Buy GroupDocs License](https://purchase.groupdocs.com/buy)  
- **Free Trial**: [Try the Free Version](https://releases.groupdocs.com/viewer/java/)  
- **Temporary License**: [Get a Temporary License](https://purchase.groupdocs.com/temporary-license/)  
- **Support**: [GroupDocs Forum](https://forum.groupdocs.com/c/viewer/9)

---

**Last Updated:** 2026-03-29  
**Tested With:** GroupDocs.Viewer 25.2 for Java  
**Author:** GroupDocs  

---