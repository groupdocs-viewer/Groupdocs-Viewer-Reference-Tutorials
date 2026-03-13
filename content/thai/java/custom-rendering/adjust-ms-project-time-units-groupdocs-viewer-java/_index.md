---
date: '2026-01-28'
description: เรียนรู้วิธีปรับหน่วยเวลาใน MS Project ด้วย GroupDocs Viewer Java. ทำให้กระบวนการแสดงผลเอกสารโครงการของคุณเป็นไปอย่างมีประสิทธิภาพและแม่นยำ.
keywords:
- GroupDocs.Viewer Java
- MS Project time units adjustment
- render MS Project files
title: 'วิธีปรับหน่วยเวลาใน MS Project ด้วย GroupDocs Viewer Java - คู่มือขั้นตอนโดยละเอียด'
type: docs
url: /th/java/custom-rendering/adjust-ms-project-time-units-groupdocs-viewer-java/
weight: 1
---

# วิธีปรับหน่วยเวลาใน MS Project ด้วย groupdocs viewer java: คู่มือขั้นตอนโดยละเอียด

## คำแนะนำเบื้องต้น
คุณรู้สึกเหนื่อยกับการปรับหน่วยเวลาในเอกสาร MS Project ของคุณด้วยตนเองก่อนแปลงเป็นรูปแบบ HTML หรือไม่? กระบวนการนี้อาจน่าเบื่อและเสี่ยงต่อข้อผิดพลาด โดยเฉพาะเมื่อทำงานกับโครงการขนาดใหญ่ ด้วย **groupdocs viewer java** คุณสามารถปรับการตั้งค่าหน่วยเวลาได้โดยอัตโนมัติ ทำให้มั่นใจในความแม่นยำและประสิทธิภาพ

![ปรับหน่วยเวลา MS Project ด้วย GroupDocs.Viewer สำหรับ Java](/viewer/custom-rendering/adjust-ms-project-time-units-java.png)

ในคู่มือนี้ เราจะสาธิตวิธีการเปลี่ยนหน่วยเวลาในเอกสาร MS Project เป็นวันโดยใช้ groupdocs viewer java. เมื่อจบบทเรียนนี้ คุณจะสามารถ:
- ตั้งค่าสภาพแวดล้อมของคุณสำหรับการแปลงไฟล์ MS Project ด้วย GroupDocs.Viewer
- ปรับหน่วยเวลาในการจัดการโครงการโดยตรงในโค้ดของคุณ
- ผสานการปรับเหล่านี้เข้ากับแอปพลิเคชันของคุณอย่างราบรื่น

ก่อนที่เราจะเริ่มลงลึก ให้แน่ใจว่าคุณมีทุกอย่างพร้อมสำหรับการเริ่มต้น!

## คำตอบอย่างรวดเร็ว
- **ไลบรารีที่จัดการการแปลง MS Project คืออะไร?** groupdocs viewer java
- **หน่วยเวลาใดที่สามารถตั้งค่าได้?** Days (ผ่าน `TimeUnit.DAYS`)
- **ฉันต้องการไลเซนส์หรือไม่?** มีไลเซนส์ทดลองหรือไลเซนส์ชั่วคราว; จำเป็นต้องมีไลเซนส์ถาวรสำหรับการใช้งานจริง
- **IDE ใดที่เหมาะสมที่สุด?** IDE ของ Java ใดก็ได้ (IntelliJ IDEA, Eclipse) ที่รองรับ Maven
- **ต้องใช้ Maven หรือไม่?** ใช่, Maven ทำให้การจัดการ dependencies สำหรับ groupdocs viewer java ง่ายขึ้น

## groupdocs viewer java คืออะไร?
groupdocs viewer java เป็น Java SDK ที่ช่วยให้นักพัฒนาสามารถแปลงเอกสารหลากหลายรูปแบบ—including ไฟล์ MS Project—เป็นรูปแบบที่เหมาะกับเว็บ เช่น HTML หรือรูปภาพ มันซ่อนความซับซ้อนของการแยกวิเคราะห์ไฟล์ ทำให้คุณสามารถมุ่งเน้นที่ตรรกะทางธุรกิจได้

## ทำไมต้องปรับหน่วยเวลาโดยใช้ groupdocs viewer java?
การเปลี่ยนหน่วยเวลาจากค่าเริ่มต้น (มักเป็นนาที) เป็นวันทำให้ผลลัพธ์ที่แปลงออกมาง่ายต่อการอ่านสำหรับผู้มีส่วนได้ส่วนเสีย สอดคล้องกับรอบการรายงานทั่วไป และลดความรกของภาพในรายงาน HTML สิ่งนี้มีคุณค่าเป็นพิเศษเมื่อฝังไทม์ไลน์ของโครงการลงในแดชบอร์ดหรือสร้างสรุปสถานะประจำวัน

## ข้อกำหนดเบื้องต้น

### ไลบรารีและ dependencies ที่จำเป็น
เพื่อทำตามบทเรียนนี้ คุณจะต้องมีสิ่งต่อไปนี้:
- ไลบรารี **groupdocs viewer java** (เวอร์ชัน 25.2 หรือใหม่กว่า)
- Maven ที่ติดตั้งบนเครื่องของคุณสำหรับการจัดการ dependencies
- ความเข้าใจพื้นฐานเกี่ยวกับการเขียนโปรแกรม Java

### ความต้องการในการตั้งค่าสภาพแวดล้อม
ตรวจสอบให้แน่ใจว่าสภาพแวดล้อมการพัฒนาของคุณได้ตั้งค่า JDK (Java Development Kit) และ IDE เช่น IntelliJ IDEA หรือ Eclipse ที่รองรับโครงการ Maven

### ความรู้พื้นฐานที่จำเป็น
ความคุ้นเคยพื้นฐานกับไวยากรณ์ Java, การจัดการไฟล์ใน Java, และการทำงานกับ dependencies ของ Maven จะเป็นประโยชน์ อย่างไรก็ตาม คู่มือนี้มุ่งหมายให้กระบวนการเป็นเรื่องง่ายสำหรับทุกระดับทักษะ

## การตั้งค่า groupdocs viewer java
เพื่อเริ่มใช้ groupdocs viewer java ให้เพิ่มเป็น dependency ในไฟล์ `pom.xml` ของโครงการของคุณ:

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
groupdocs มีการให้ทดลองใช้ฟรีของไลบรารีของพวกเขา เพื่อให้คุณสำรวจฟีเจอร์ก่อนทำการซื้อหรือขอไลเซนส์ชั่วคราว:
- **ทดลองใช้ฟรี**: เยี่ยมชม [GroupDocs Free Trial](https://releases.groupdocs.com/viewer/java/) เพื่อดาวน์โหลดและเริ่มใช้ไลบรารี
- **ไลเซนส์ชั่วคราว**: สำหรับการทดสอบต่อเนื่อง ขอ [temporary license](https://purchase.groupdocs.com/temporary-license/)
- **ซื้อ**: หากคุณตัดสินใจว่า groupdocs.viewer java เหมาะกับโครงการของคุณ ให้ซื้อโดยตรงจาก [buy page](https://purchase.groupdocs.com/buy)

### การเริ่มต้นและตั้งค่าพื้นฐาน
เมื่อ dependency ถูกตั้งค่าใน `pom.xml` ของ Maven แล้ว คุณพร้อมที่จะเริ่มเขียนโค้ดแล้ว เริ่มต้นอินสแตนซ์ Viewer ด้วยเส้นทางของไฟล์ MS Project ของคุณและเตรียมพร้อมสำหรับการแปลง

## คู่มือการดำเนินการ
มาดูวิธีการปรับหน่วยเวลาในเอกสาร MS Project ด้วย groupdocs viewer java เราจะแบ่งเป็นขั้นตอนทีละขั้นตอน

### ภาพรวมฟีเจอร์: ปรับหน่วยเวลาในเอกสาร MS Project
ฟีเจอร์นี้ช่วยให้คุณเปลี่ยนการตั้งค่าหน่วยเวลาในการจัดการโครงการจากค่าเริ่มต้น (โดยปกติเป็นนาที) เป็นวัน ทำให้ HTML ที่แปลงออกมามีความเป็นมิตรต่อผู้ใช้และสอดคล้องกับมาตรฐานการรายงานทั่วไป

#### ขั้นตอนที่ 1: กำหนดไดเรกทอรีเอาต์พุตและรูปแบบเส้นทางไฟล์ของหน้า
แรกสุด ให้ระบุที่ที่ไฟล์ HTML ที่แปลงแล้วจะถูกจัดเก็บ:

```java
import java.nio.file.Path;
// Specify the output directory for HTML files
Path outputDirectory = Utils.getOutputDirectoryPath("YOUR_OUTPUT_DIRECTORY");
```

ใช้ไดเรกทอรีนี้เพื่อแก้ไขเส้นทางไฟล์แบบไดนามิกสำหรับแต่ละหน้าของเอกสาร MS Project ของคุณ:

```java
// Define a format for each rendered page's file path
Path pageFilePathFormat = outputDirectory.resolve("page_{0}.html");
```

#### ขั้นตอนที่ 2: เริ่มต้น View Options
สร้าง view options พร้อมกับ embedded resources ซึ่งช่วยให้คุณกำหนดวิธีการแสดงและแปลงโครงการ:

```java
import com.groupdocs.viewer.options.HtmlViewOptions;
// Set up HTML view options for rendering
HtmlViewOptions viewOptions = HtmlViewOptions.forEmbeddedResources(pageFilePathFormat);
```

#### ขั้นตอนที่ 3: ปรับการตั้งค่าหน่วยเวลา
ระบุว่าหน่วยเวลาสำหรับการจัดการโครงการตั้งเป็นวัน ซึ่งมักเหมาะสมกว่าสำหรับการนำเสนอและรายงาน:

```java
import com.groupdocs.viewer.options.TimeUnit;
// Change the project management time unit to DAYS
viewOptions.getProjectManagementOptions().setTimeUnit(TimeUnit.DAYS);
```

#### ขั้นตอนที่ 4: แปลงเอกสาร MS Project
สุดท้าย ใช้คลาส Viewer เพื่อแปลงเอกสารของคุณด้วย view options ที่กำหนดไว้:

```java
import com.groupdocs.viewer.Viewer;
try (Viewer viewer = new Viewer("YOUR_DOCUMENT_DIRECTORY/SAMPLE_MPP")) {
    // Render the project document as HTML using set view options
    viewer.view(viewOptions);
}
```

### เคล็ดลับการแก้ไขปัญหา
- ตรวจสอบให้แน่ใจว่าเส้นทางไดเรกทอรีเอาต์พุตระบุอย่างถูกต้องและสามารถเขียนได้
- ยืนยันว่าเส้นทางไฟล์ MS Project ถูกต้องและเข้าถึงได้
- หากเกิดปัญหาในการแปลง ตรวจสอบว่ามี exception ใดที่ถูกโยนจากคลาส Viewer หรือไม่

## การประยุกต์ใช้งานจริง
นี่คือตัวอย่างการใช้งานจริงที่การปรับหน่วยเวลาในเอกสาร MS Project มีประโยชน์เป็นพิเศษ:
1. **การรายงานโครงการ** – ผู้มีส่วนได้ส่วนเสียมักต้องการสรุปประจำวันมากกว่ารายละเอียดระดับนาที
2. **การผสานกับแดชบอร์ด** – ฝังไทม์ไลน์ลงในแดชบอร์ดธุรกิจที่ต้องการความละเอียดระดับวัน
3. **การอัปเดตอัตโนมัติ** – ระบบที่ต้องรีเฟรชสถานะโครงการเป็นประจำวันโดยอัตโนมัติ

## ข้อควรพิจารณาด้านประสิทธิภาพ
เมื่อทำงานกับไฟล์ MS Project ขนาดใหญ่ ควรพิจารณาดังต่อไปนี้เพื่อประสิทธิภาพที่ดีที่สุด:
- ใช้ embedded resources อย่างจำกัด หากต้องการเพียงบางส่วนของเอกสารบ่อยครั้ง
- ตรวจสอบการใช้หน่วยความจำเมื่อจัดการหลายโครงการหรือโครงการขนาดใหญ่อย่างพร้อมกัน
- ใช้การทำงานของ garbage collection ของ Java อย่างมีประสิทธิภาพเพื่อจัดการการจัดสรรและปล่อยทรัพยากร

## สรุป
คุณได้เรียนรู้วิธีการปรับหน่วยเวลาใน MS Project ด้วย groupdocs viewer java แล้ว ฟีเจอร์นี้ทำให้กระบวนการแปลงเอกสารโครงการเป็นเรื่องง่ายขึ้น ทำให้เข้าถึงได้ง่ายและผสานรวมกับระบบอื่นได้ง่ายขึ้น

ลองสำรวจความสามารถอื่นของ groupdocs viewer java เพื่อพัฒนาการจัดการเอกสารของคุณต่อไป พร้อมที่จะก้าวต่อไปหรือยัง? ลองนำโซลูชันนี้ไปใช้ในโครงการถัดไปของคุณ!

## ส่วนคำถามที่พบบ่อย
**1. GroupDocs.Viewer for Java ใช้เพื่ออะไร?**  
GroupDocs.Viewer for Java ช่วยให้นักพัฒนาสามารถแปลงเอกสารในรูปแบบต่าง ๆ รวมถึงไฟล์ MS Project ให้เป็น HTML หรือรูปภาพสำหรับการดู

**2. ฉันสามารถใช้ GroupDocs.Viewer กับประเภทเอกสารอื่นได้หรือไม่?**  
ได้, GroupDocs.Viewer รองรับรูปแบบเอกสารหลากหลายนอกเหนือจาก MS Project เช่น PDF, เอกสาร Word, และสเปรดชีต

**3. ฉันจะจัดการไลเซนส์สำหรับ GroupDocs.Viewer อย่างไร?**  
GroupDocs มีตัวเลือกไลเซนส์หลายแบบ รวมถึงการทดลองใช้ฟรี, ไลเซนส์ชั่วคราวสำหรับการทดสอบต่อเนื่อง, และไลเซนส์ถาวรเมื่อซื้อ

**4. จะทำอย่างไรหากพบข้อผิดพลาดขณะแปลงไฟล์โครงการของฉัน?**  
ตรวจสอบเส้นทางไฟล์, ยืนยันว่าคุณมีสิทธิ์เขียนในไดเรกทอรีเอาต์พุต, และตรวจสอบ exception ใดที่ถูกโยนจาก GroupDocs.Viewer เพื่อเป็นแนวทางแก้ไข

**5. ฉันสามารถปรับแต่งวิธีการแปลงเอกสารด้วย GroupDocs.Viewer ได้หรือไม่?**  
แน่นอน! GroupDocs.Viewer มีตัวเลือกหลากหลายเพื่อปรับแต่งการแปลง รวมถึงการตั้งค่าหน่วยเวลาในโครงการ, การเลือกทรัพยากรที่ต้อง embed, และอื่น ๆ

## แหล่งข้อมูล
- [Documentation](https://docs.groupdocs.com/viewer/java/)
- [API Reference](https://reference.groupdocs.com/viewer/java/)
- [Download GroupDocs.Viewer](https://releases.groupdocs.com/viewer/java/)
- [Purchase a License](https://purchase.groupdocs.com/buy)

**อัปเดตล่าสุด:** 2026-01-28  
**ทดสอบด้วย:** groupdocs viewer java 25.2  
**ผู้เขียน:** GroupDocs