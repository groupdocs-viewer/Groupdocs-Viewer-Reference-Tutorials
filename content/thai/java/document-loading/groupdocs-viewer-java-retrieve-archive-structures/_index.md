---
date: '2026-02-05'
description: เรียนรู้วิธีการรับ viewinfo และดึงโครงสร้างไฟล์ประเภท Java archive โดยใช้
  GroupDocs.Viewer คู่มือนี้ครอบคลุมการตั้งค่า ตัวอย่างโค้ด และกรณีการใช้งานจริง
keywords:
- GroupDocs.Viewer for Java
- retrieve archive structures
- Java document viewer
title: วิธีรับ ViewInfo และดึงโครงสร้าง Archive ใน Java
type: docs
url: /th/java/document-loading/groupdocs-viewer-java-retrieve-archive-structures/
weight: 1
---

# วิธีการรับ ViewInfo และดึงโครงสร้าง Archive ใน Java

การจัดการไฟล์ archive อย่างมีประสิทธิภาพต้องอาศัยความเข้าใจที่ชัดเจนเกี่ยวกับโครงสร้างของมัน ในบทเรียนนี้คุณจะได้เรียนรู้ **วิธีการรับ viewinfo** สำหรับ archive ใดก็ได้และดูว่ามันช่วยคุณทำงานกับ **ประเภทไฟล์ archive ของ Java** อย่างไร เราจะเดินผ่านการตั้งค่า GroupDocs.Viewer, การสกัดข้อมูล view, และการอ่านโครงสร้างโฟลเดอร์แบบเรียกซ้ำ เพื่อให้คุณสามารถผสานโซลูชันนี้เข้ากับโครงการจริงได้

![โครงสร้าง Archive ด้วย GroupDocs.Viewer สำหรับ Java](/viewer/document-loading/archive-structures-java.png)

**สิ่งที่คุณจะได้เรียนรู้**
- การตั้งค่าและกำหนดค่า GroupDocs.Viewer สำหรับ Java.  
- วิธีการ **รับ viewinfo** จาก archive.  
- เทคนิคการอ่านและแสดงโครงสร้างโฟลเดอร์ของไฟล์ archive.  
- การประยุกต์ใช้จริงและข้อพิจารณาด้านประสิทธิภาพเมื่อใช้ GroupDocs.Viewer ในโครงการ Java.

## คำตอบอย่างรวดเร็ว
- **viewinfo** ให้ข้อมูลอะไรบ้าง? มันคืนค่าประเภทไฟล์, จำนวนหน้า, และรายการโฟลเดอร์ของ archive.  
- **archive** ใดบ้างที่รองรับ? ZIP, RAR, TAR และรูปแบบทั่วไปอื่น ๆ.  
- **ฉันต้องการไลเซนส์หรือไม่?** เวอร์ชันทดลองฟรีใช้ได้สำหรับการประเมิน; จำเป็นต้องมีไลเซนส์เชิงพาณิชย์สำหรับการใช้งานจริง.  
- **ฉันสามารถประมวลผล archive ขนาดใหญ่ได้หรือไม่?** ใช่ – ใช้การสตรีมและการจัดการหน่วยความจำที่เหมาะสมตามที่แสดงต่อไป.  
- **ต้องใช้ Maven หรือไม่?** Maven เป็นวิธีที่แนะนำในการจัดการ dependency ของ GroupDocs.Viewer.

## “how to get viewinfo” คืออะไร?
`getViewInfo` เป็นเมธอดใน GroupDocs.Viewer API ที่สกัด metadata ของเอกสารหรือ archive โดยไม่ต้องเรนเดอร์เนื้อหาเต็ม สำหรับ archive มันเปิดเผยโครงสร้างโฟลเดอร์ภายใน, ทำให้คุณสามารถตัดสินใจว่าจะเรนเดอร์หรือประมวลผลส่วนใดต่อไป

## ทำไมต้องดึงโครงสร้างประเภทไฟล์ Archive ของ Java?
การเข้าใจโครงสร้างภายในของ **ประเภทไฟล์ archive ของ Java** (เช่น ZIP, RAR) ทำให้คุณสามารถ:
- ค้นหาไฟล์ที่ต้องการได้อย่างรวดเร็วโดยไม่ต้องแตกไฟล์ทั้งหมด.  
- สร้าง pipeline อัตโนมัติที่ประมวลผลเฉพาะโฟลเดอร์ย่อยที่เกี่ยวข้อง.  
- ผสานการนำทาง archive เข้ากับระบบจัดการเนื้อหา หรือระบบรับข้อมูล.

## ข้อกำหนดเบื้องต้น

- **Java Development Kit (JDK):** เวอร์ชัน 8 หรือใหม่กว่า.  
- **Maven:** สำหรับการจัดการ dependency และการสร้าง.  
- **ความรู้พื้นฐาน Java:** ความคุ้นเคยกับแนวคิด OOP จะช่วยแต่ไม่จำเป็น.

คุณยังต้องเข้าถึงไลบรารี GroupDocs.Viewer ซึ่งคุณสามารถเพิ่มในโครงการ Maven ของคุณตามด้านล่าง

## การตั้งค่า GroupDocs.Viewer สำหรับ Java

### การกำหนดค่า Maven

เพิ่ม repository และ dependency ลงในไฟล์ `pom.xml` ของคุณ

**Repositories:**
```xml
<repositories>
   <repository>
      <id>repository.groupdocs.com</id>
      <name>GroupDocs Repository</name>
      <url>https://releases.groupdocs.com/viewer/java/</url>
   </repository>
</repositories>
```

**Dependencies:**
```xml
<dependencies>
   <dependency>
      <groupId>com.groupdocs</groupId>
      <artifactId>groupdocs-viewer</artifactId>
      <version>25.2</version>
   </dependency>
</dependencies>
```

### การรับไลเซนส์

- **Free Trial:** ดาวน์โหลดเวอร์ชันทดลองจากเว็บไซต์ GroupDocs.  
- **Temporary License:** ขอคีย์ชั่วคราวสำหรับการประเมินระยะสั้น.  
- **Full License:** ซื้อไลเซนส์เชิงพาณิชย์เพื่อการใช้งานในผลิตภัณฑ์ไม่จำกัด.

เมื่อไลบรารีอยู่ใน classpath ของคุณแล้ว คุณสามารถเริ่มเขียนโค้ดได้

## คู่มือการทำงาน

### วิธีการรับ ViewInfo สำหรับไฟล์ Archive

ส่วนนี้แสดงขั้นตอนที่แน่นอนในการเรียก `getViewInfo` และอ่านโครงสร้างโฟลเดอร์

#### เริ่มต้น Viewer

```java
try (Viewer viewer = new Viewer("YOUR_DOCUMENT_DIRECTORY/SAMPLE_ZIP_WITH_FOLDERS")) {
    // Additional steps will follow here.
}
```

#### ดึงข้อมูล View

```java
ViewInfo viewInfo = viewer.getViewInfo(ViewInfoOptions.forHtmlView());
System.out.println("File type: " + viewInfo.getFileType());
System.out.println("Pages count: " + viewInfo.getPages().size());
```

#### แสดงโครงสร้างโฟลเดอร์

```java
String rootFolder = "";
readFolders(viewer, rootFolder);
```

##### การอ่านโฟลเดอร์แบบเรียกซ้ำ

```java
private static void readFolders(Viewer viewer, String folder) {
    ViewInfoOptions viewInfoOptions = ViewInfoOptions.forHtmlView();
    viewInfoOptions.getArchiveOptions().setFolder(folder);
    
    ArchiveViewInfo viewInfo = (ArchiveViewInfo) viewer.getViewInfo(viewInfoOptions);
    
    for (String subFolder : viewInfo.getFolders()) {
        System.out.println(" - " + subFolder);
        readFolders(viewer, subFolder);
    }
}
```

### ฟีเจอร์ 2: ดึงโครงสร้างโฟลเดอร์ของ Archive

ฟีเจอร์นี้เน้นการพิมพ์โครงสร้างโฟลเดอร์ของไฟล์ archive ซึ่งคล้ายกับฟีเจอร์แรกแต่เน้นการสำรวจแบบเรียกซ้ำ

#### ตั้งค่า View Info Options

```java
ViewInfoOptions viewInfoOptions = ViewInfoOptions.forHtmlView();
viewInfoOptions.getArchiveOptions().setFolder(folder);
```

#### การสำรวจแบบเรียกซ้ำ

```java
for (String subFolder : viewInfo.getFolders()) {
    System.out.println(" - " + subFolder);
    readFolders(viewer, subFolder);
}
```

## การประยุกต์ใช้จริง

- **การจัดการข้อมูล:** จัดระเบียบชุดข้อมูลขนาดใหญ่ได้อย่างรวดเร็วโดยเข้าใจโครงสร้าง archive.  
- **การประมวลผลไฟล์อัตโนมัติ:** ประมวลผลไฟล์ archive เป็นชุดโดยไม่ต้องแตกไฟล์ทั้งหมด.  
- **การผสาน CMS:** ปรับปรุงระบบจัดการเนื้อหาให้มีการนำทาง archive แบบเรียลไทม์.

## ข้อพิจารณาด้านประสิทธิภาพ

- **เพิ่มประสิทธิภาพการใช้หน่วยความจำ:** ประมวลผลโฟลเดอร์ทีละระดับและปิดอินสแตนซ์ `Viewer` อย่างรวดเร็ว.  
- **อัปเดตอยู่เสมอ:** ใช้เวอร์ชันล่าสุดของ GroupDocs.Viewer และ JDK เพื่อเพิ่มประสิทธิภาพ.

## ปัญหาทั่วไปและวิธีแก้

| ปัญหา | สาเหตุ | วิธีแก้ |
|-------|--------|--------|
| `NullPointerException` ขณะอ่านโฟลเดอร์ | `viewInfo.getFolders()` คืนค่า null สำหรับไดเรกทอรีที่ว่าง | ตรวจสอบว่าเป็น null หรือรายการว่างก่อนทำการวนลูป. |
| การประมวลผลไฟล์ ZIP ขนาดใหญ่ช้า | Archive ทั้งหมดถูกโหลดเข้าสู่หน่วยความจำ | ใช้ตัวเลือกการสตรีมที่มีในเวอร์ชันใหม่ของ GroupDocs. |
| ไม่พบไลเซนส์ | เส้นทางไฟล์ไลเซนส์ไม่ถูกต้อง | วางไฟล์ไลเซนส์ในโฟลเดอร์รากของแอปพลิเคชันหรือกำหนด `License.setLicense("path/to/license.json")`. |

## คำถามที่พบบ่อย

**Q: GroupDocs.Viewer คืออะไร?**  
A: เป็นไลบรารี Java ที่ทรงพลังสำหรับเรนเดอร์เอกสาร รวมถึง archive ให้เป็นรูปแบบต่าง ๆ เช่น HTML, image, และ PDF.

**Q: ฉันสามารถใช้ GroupDocs.Viewer กับภาษาโปรแกรมอื่นได้หรือไม่?**  
A: ได้, GroupDocs มี SDK สำหรับหลายแพลตฟอร์ม แต่บทเรียนนี้เน้นการใช้งานใน Java

**Q: ฉันจัดการไฟล์ archive ขนาดใหญ่อย่างไร?**  
A: ใช้แนวทางการจัดการหน่วยความจำอย่างมีประสิทธิภาพ และพิจารณาแยก archive หากจำเป็น

**Q: GroupDocs.Viewer รองรับประเภท archive ใดบ้าง?**  
A: รองรับหลายรูปแบบรวมถึง ZIP, RAR, TAR และอื่น ๆ

**Q: มีขีดจำกัดขนาดของ archive ที่ฉันสามารถประมวลผลได้หรือไม่?**  
A: ขีดจำกัดขึ้นอยู่กับทรัพยากรของระบบของคุณ ทดสอบกับสภาพแวดล้อมเป้าหมายเพื่อกำหนดขีดจำกัดที่เป็นไปได้

**Q: “how to get viewinfo” ทำงานกับ archive ที่มีรหัสผ่านหรือไม่?**  
A: ใช่, คุณสามารถส่งรหัสผ่านผ่าน `ArchiveOptions.setPassword("yourPassword")` ก่อนเรียก `getViewInfo`.

## สรุป

โดยทำตามคู่มือนี้คุณจะรู้ **วิธีการรับ viewinfo** สำหรับ archive ที่รองรับทุกประเภทและวิธีการเดินทางผ่านโครงสร้างโฟลเดอร์โดยใช้ GroupDocs.Viewer สำหรับ Java เทคนิคเหล่านี้ทำให้คุณสร้าง pipeline การประมวลผลข้อมูลที่ชาญฉลาดขึ้น, ปรับปรุงการผสาน CMS, และจัดการกับคอลเลกชันไฟล์ archive ขนาดใหญ่ได้อย่างมั่นใจ ต่อไปให้สำรวจการเรนเดอร์ไฟล์แต่ละไฟล์จาก archive หรือการแปลงเป็น PDF/HTML ด้วยฟีเจอร์อื่นของ Viewer.

---

**อัปเดตล่าสุด:** 2026-02-05  
**ทดสอบกับ:** GroupDocs.Viewer 25.2 for Java  
**ผู้เขียน:** GroupDocs  

**แหล่งข้อมูล**
- **เอกสาร:** [GroupDocs Viewer Java Documentation](https://docs.groupdocs.com/viewer/java/)
- **อ้างอิง API:** [GroupDocs API Reference for Java](https://reference.groupdocs.com/viewer/java/)
- **ดาวน์โหลด GroupDocs.Viewer:** [GroupDocs Download Page](https://releases.groupdocs.com/viewer/java/)
- **ซื้อไลเซนส์:** [Buy GroupDocs](https://purchase.groupdocs.com/buy)
- **ทดลองใช้และไลเซนส์ชั่วคราว:** [GroupDocs Free Trial](https://releases.groupdocs.com/viewer/java/) | [Temporary License](https://purchase.groupdocs.com/temporary-license/)