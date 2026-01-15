---
date: '2026-01-15'
description: เรียนรู้วิธีใช้ GroupDocs Viewer เพื่อสร้าง HTML จากเอกสารโครงการในช่วงเวลาที่กำหนด
  คู่มือนี้ครอบคลุมการตั้งค่า โค้ด และกรณีการใช้งานจริง
keywords:
- render project documents
- time intervals Java
- GroupDocs Viewer API
title: วิธีใช้ GroupDocs Viewer เพื่อแสดงเอกสารโครงการตามช่วงเวลาใน Java
type: docs
url: /th/java/advanced-rendering/render-project-documents-time-intervals-groupdocs-viewer-java/
weight: 1
---

# วิธีใช้ GroupDocs Viewer เพื่อแสดงเอกสารโครงการตามช่วงเวลาใน Java

หากคุณกำลังมองหา **how to use GroupDocs** เพื่อแสดงตารางโครงการในช่วงเวลาที่มุ่งเน้น คุณมาถูกที่แล้ว ในบทแนะนำนี้เราจะเดินผ่านกระบวนการทั้งหมด—ตั้งแต่การตั้งค่า Maven ถึงการสร้าง HTML จากเอกสารโครงการ—เพื่อให้คุณสามารถฝังมุมมองไทม์ไลน์ที่แม่นยำลงในแอปพลิเคชันของคุณได้

![แสดงเอกสารโครงการตามช่วงเวลาโดยใช้ GroupDocs.Viewer สำหรับ Java](/viewer/advanced-rendering/render-project-documents-by-time-intervals-java.png)

## คำตอบอย่างรวดเร็ว
- **ฟีเจอร์ทำอะไร?** มันจะแสดงเฉพาะส่วนของไฟล์ Microsoft Project ที่อยู่ระหว่างวันที่เริ่มต้นและสิ้นสุดเท่านั้น.  
- **รูปแบบเอาต์พุตที่ใช้คืออะไร?** HTML พร้อมทรัพยากรที่ฝังอยู่ เหมาะสำหรับการรวมเข้ากับเว็บ.  
- **ฉันต้องการไลเซนส์หรือไม่?** รุ่นทดลองฟรีใช้ได้สำหรับการประเมิน; จำเป็นต้องมีไลเซนส์เต็มสำหรับการใช้งานจริง.  
- **ฉันสามารถเปลี่ยนช่วงวันที่ในระหว่างการทำงานได้หรือไม่?** ได้—ปรับค่า `setStartDate` และ `setEndDate` ในตัวเลือกการแสดงผล.  
- **ฟีเจอร์นี้รองรับทุกเวอร์ชันของ Java หรือไม่?** ทำงานกับ Java 8+ ตราบใดที่คุณใช้ GroupDocs.Viewer 25.2 หรือใหม่กว่า.

## “How to Use GroupDocs” หมายถึงอะไรในบริบทนี้?
GroupDocs Viewer เป็นไลบรารี Java ที่แปลงไฟล์กว่า 100 รูปแบบให้เป็นรูปแบบที่เป็นมิตรกับเว็บ เมื่อคุณ **how to use GroupDocs** สำหรับไฟล์โครงการ คุณจะได้ความสามารถในการดึงข้อมูล, แสดงผล, และแชร์ข้อมูลตารางเวลาโดยไม่ต้องใช้ Microsoft Project ที่ฝั่งไคลเอนต์.

## ทำไมต้องแสดงเอกสารโครงการด้วยช่วงเวลา?
- **การวิเคราะห์ที่มุ่งเน้น:** แสดงเฉพาะช่วงที่คุณสนใจ (เช่น ไตรมาส 3 ปี 2024).  
- **ประสิทธิภาพ:** ผลลัพธ์ HTML ที่มีขนาดเล็กกว่าจะทำให้หน้าเว็บโหลดเร็วขึ้น.  
- **การรวมระบบ:** ฝังมุมมองไทม์ไลน์ลงในแดชบอร์ด, พอร์ทัลรายงาน, หรือเครื่องมือ PM ที่กำหนดเอง.

## ข้อกำหนดเบื้องต้น
- **GroupDocs.Viewer for Java** เวอร์ชัน 25.2 หรือสูงกว่า.  
- Java Development Kit (JDK) 8 หรือใหม่กว่า.  
- IDE เช่น IntelliJ IDEA หรือ Eclipse.  
- ความรู้พื้นฐานเกี่ยวกับ Maven.

## การตั้งค่า GroupDocs.Viewer สำหรับ Java

### การพึ่งพา Maven

Add the repository and dependency to your `pom.xml`:

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
1. **Free Trial** – ดาวน์โหลดรุ่นทดลองจาก [GroupDocs' download page](https://releases.groupdocs.com/viewer/java/).  
2. **Temporary License** – รับไลเซนส์ชั่วคราวสำหรับการทดสอบต่อเนื่องผ่าน [this link](https://purchase.groupdocs.com/temporary-license/).  
3. **Purchase** – สำหรับการใช้งานผลิตภัณฑ์โดยไม่มีข้อจำกัด ให้ซื้อไลเซนส์ที่ [GroupDocs Purchase Page](https://purchase.groupdocs.com/buy).

### การเริ่มต้น Viewer เบื้องต้น

โค้ดต่อไปนี้แสดงวิธีสร้างอินสแตนซ์ `Viewer` ที่ชี้ไปยังไฟล์ Microsoft Project (`.mpp`):

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

### 1. กำหนดไดเรกทอรีเอาต์พุต

Create a folder where the generated HTML pages will be saved:

```java
import java.nio.file.Path;

Path outputDirectory = Path.of("YOUR_OUTPUT_DIRECTORY", "RenderProjectTimeInterval");
Path pageFilePathFormat = outputDirectory.resolve("page_{0}.html");
```

*ทำไม?* การจัดระเบียบไฟล์ที่แสดงผลทำให้สะดวกในการให้บริการจากเว็บเซิร์ฟเวอร์หรือฝังลงใน UI.

### 2. เริ่มต้น Viewer ด้วยไฟล์โครงการของคุณ

```java
try (Viewer viewer = new Viewer("YOUR_DOCUMENT_DIRECTORY/SAMPLE_MPP")) {
    // Continue with rendering steps
}
```

*ทำไม?* การโหลดเอกสารเตรียมตัวพาร์เซอร์ภายในและทำให้เมตาดาต้าเฉพาะโครงการสามารถเข้าถึงได้.

### 3. ดึงข้อมูลการดูสำหรับไฟล์โครงการ

```java
import com.groupdocs.viewer.options.ViewInfoOptions;
import com.groupdocs.viewer.results.ProjectManagementViewInfo;

ViewInfoOptions viewInfoOptions = ViewInfoOptions.forHtmlView();
ProjectManagementViewInfo viewInfo = (ProjectManagementViewInfo) viewer.getViewInfo(viewInfoOptions);
```

*ทำไม?* `ProjectManagementViewInfo` ให้วันที่เริ่มต้นและสิ้นสุดของตารางเวลา ซึ่งคุณจะใช้ต่อไปเพื่อจำกัดขอบเขตการแสดงผล.

### 4. ตั้งค่าตัวเลือกการแสดงผล HTML (สร้าง HTML จากโครงการ)

```java
import com.groupdocs.viewer.options.HtmlViewOptions;

HtmlViewOptions viewOptions = HtmlViewOptions.forEmbeddedResources(pageFilePathFormat);
viewOptions.getProjectManagementOptions().setStartDate(viewInfo.getStartDate());
viewOptions.getProjectManagementOptions().setEndDate(viewInfo.getEndDate());
```

*ทำไม?* การตั้งค่า `StartDate` และ `EndDate` บอก GroupDocs ให้ **generate HTML from project** เฉพาะในช่วงเวลานั้น.

### 5. ดำเนินการกระบวนการแสดงผล

```java
viewer.view(viewOptions);
```

*ทำไม?* การเรียกนี้จะสร้างชุดของหน้า HTML ที่เป็นอิสระซึ่งแสดงส่วนของตารางเวลาที่เลือกของโครงการของคุณ.

## ข้อผิดพลาดทั่วไปและการแก้ไขปัญหา
- **Incorrect file paths** – ตรวจสอบให้แน่ใจว่าไฟล์ต้นทาง `.mpp` และไดเรกทอรีเอาต์พุตมีอยู่.  
- **Unsupported file type** – ตรวจสอบว่าเอกสารเป็นรูปแบบ Project ที่รองรับ (เช่น `.mpp`, `.mpt`).  
- **License errors** – ไลเซนส์ทดลองอาจมีข้อจำกัดการแสดงผล; เปลี่ยนเป็นไลเซนส์เต็มเพื่อการใช้งานโดยไม่มีข้อจำกัด.

## การประยุกต์ใช้งานจริง
1. **Project Timeline Analysis** – แสดงเฉพาะขั้นตอนปัจจุบันให้ผู้มีส่วนได้ส่วนเสีย.  
2. **Automated Reporting** – สร้างรายงาน HTML ตามช่วงเวลาเพื่ออัปเดตสถานะรายสัปดาห์.  
3. **Integration with Dashboards** – ฝังหน้าที่แสดงผลลงในเครื่องมือ BI หรือพอร์ทัลที่กำหนดเอง.  
4. **Archival** – เก็บภาพสแนปช็อตที่เป็นมิตรกับเว็บของตารางโครงการเพื่ออ้างอิงในอนาคต.

## เคล็ดลับประสิทธิภาพ
- ใช้ตัวเลือก *embedded resources* เพื่อให้แต่ละหน้า HTML เป็นอิสระ ลดจำนวนคำขอ HTTP.  
- สำหรับโครงการขนาดใหญ่มาก พิจารณาแสดงผลเป็นช่วงวันที่เล็กลงเพื่อรักษาการใช้หน่วยความจำให้ต่ำ.  
- ทำความสะอาดไฟล์ชั่วคราวหลังจากให้บริการเพื่อหลีกเลี่ยงการเพิ่มขนาดดิสก์.

## สรุป
คุณตอนนี้รู้แล้วว่า **how to use GroupDocs** Viewer สามารถแสดงเอกสารโครงการในช่วงเวลาที่กำหนดและ **generate HTML from project** ข้อมูลใน Java ความสามารถนี้ช่วยทำให้การแสดงผลไทม์ไลน์เป็นไปอย่างราบรื่น ปรับปรุงประสิทธิภาพการรายงาน และรวมเข้ากับแอปพลิเคชันเว็บสมัยใหม่ได้อย่างลงตัว.

### ขั้นตอนต่อไป
- สำรวจฟีเจอร์ Viewer เพิ่มเติม เช่น การใส่ลายน้ำ, การป้องกันด้วยรหัสผ่าน, หรือการปรับสไตล์ CSS แบบกำหนดเอง.  
- รวม pipeline การแสดงผลนี้กับ REST API เพื่อให้บริการมุมมองไทม์ไลน์ตามความต้องการ.

## คำถามที่พบบ่อย

**Q: GroupDocs.Viewer รองรับรูปแบบไฟล์อะไรบ้าง?**  
A: GroupDocs.Viewer รองรับรูปแบบไฟล์หลากหลายรวมถึง Microsoft Project (MPP), PDF, Word, Excel, PowerPoint, และอื่น ๆ อีกมากมาย.

**Q: ฉันจะเริ่มต้นด้วยรุ่นทดลองฟรีของ GroupDocs.Viewer อย่างไร?**  
A: คุณสามารถดาวน์โหลดรุ่นทดลองได้จาก [here](https://releases.groupdocs.com/viewer/java/).

**Q: ฉันสามารถแสดงผลเอกสารโดยไม่ฝังทรัพยากรได้หรือไม่?**  
A: ได้ คุณสามารถเลือกตัวเลือกการแสดงผล HTML แบบอื่นที่อ้างอิงทรัพยากรภายนอกแทนการฝังไว้

**Q: ถ้าเอกสารของฉันใหญ่เกินกว่าจะทำการแสดงผลจะทำอย่างไร?**  
A: พิจารณาแบ่งเอกสารเป็นส่วนย่อยหรือแสดงผลเฉพาะช่วงวันที่ต้องการ ตามที่แสดงในตัวอย่างข้างต้น.

**Q: ฉันจะจัดการกับข้อผิดพลาดการแสดงผลอย่างไร?**  
A: ตรวจสอบการตั้งค่าทั้งหมด, ยืนยันว่าคุณมีไลเซนส์ที่ถูกต้อง, และอ้างอิงเอกสารของ GroupDocs สำหรับรหัสข้อผิดพลาดโดยละเอียด.

## แหล่งข้อมูล
- **Documentation**: [GroupDocs Viewer Java Documentation](https://docs.groupdocs.com/viewer/java/)  
- **API Reference**: [GroupDocs API Reference](https://reference.groupdocs.com/viewer/java/)  
- **Download**: [GroupDocs Downloads](https://releases.groupdocs.com/viewer/java/)  
- **Purchase**: [Buy GroupDocs License](https://purchase.groupdocs.com/buy)  
- **Free Trial**: [Try the Free Version](https://releases.groupdocs.com/viewer/java/)  
- **Temporary License**: [Get a Temporary License](https://purchase.groupdocs.com/temporary-license/)  
- **Support**: [GroupDocs Forum](https://forum.groupdocs.com/c/viewer/9)

---

**อัปเดตล่าสุด:** 2026-01-15  
**ทดสอบกับ:** GroupDocs.Viewer 25.2 for Java  
**ผู้เขียน:** GroupDocs