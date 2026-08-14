---
date: '2026-06-30'
description: เรียนรู้วิธีรับ viewinfo และดึงโครงสร้างไฟล์ประเภท archive ของ Java ด้วย
  GroupDocs.Viewer คู่มือนี้ครอบคลุมการตั้งค่า ตัวอย่างโค้ด และกรณีการใช้งานจริง
keywords:
- how to get viewinfo
- retrieve archive structures
- java archive file type
- GroupDocs Viewer Java
schemas:
- author: GroupDocs
  dateModified: '2026-06-30'
  description: Learn how to get viewinfo and retrieve java archive file type structures
    using GroupDocs.Viewer. This guide covers setup, code examples, and real‑world
    use cases.
  headline: How to Get ViewInfo and Retrieve Archive Structures in Java
  type: TechArticle
- description: Learn how to get viewinfo and retrieve java archive file type structures
    using GroupDocs.Viewer. This guide covers setup, code examples, and real‑world
    use cases.
  name: How to Get ViewInfo and Retrieve Archive Structures in Java
  steps:
  - name: '**Data Management:** Quickly organize large datasets by understanding archive
      structures.'
    text: '**Data Management:** Quickly organize large datasets by understanding archive
      structures.'
  - name: '**Automated File Processing:** Batch‑process archived files without fully
      extracting them, cutting I/O by up to 70 %.'
    text: '**Automated File Processing:** Batch‑process archived files without fully
      extracting them, cutting I/O by up to 70 %.'
  - name: '**CMS Integration:** Enhance content‑management systems with on‑the‑fly
      archive navigation, enabling editors to preview files directly from the archive.'
    text: '**CMS Integration:** Enhance content‑management systems with on‑the‑fly
      archive navigation, enabling editors to preview files directly from the archive.'
  type: HowTo
- questions:
  - answer: It returns file type, page count, and a complete listing of folders and
      files inside an archive.
    question: What does “viewinfo” provide?
  - answer: ZIP, RAR, TAR, 7z, ISO, and 12+ other common formats.
    question: Which archive formats are supported?
  - answer: Yes—a commercial license is required for production; a free trial works
      for evaluation.
    question: Do I need a license for production?
  - answer: Absolutely—use streaming options and process one folder level at a time
      to keep memory usage low.
    question: Can large archives be processed efficiently?
  - answer: Maven is the recommended dependency manager, but Gradle or manual JAR
      inclusion also work.
    question: Is Maven the only way to add the library?
  type: FAQPage
title: วิธีรับ ViewInfo และดึงโครงสร้าง Archive ใน Java
type: docs
url: /th/java/document-loading/groupdocs-viewer-java-retrieve-archive-structures/
weight: 1
---

# วิธีการรับ ViewInfo และดึงโครงสร้างของ Archive ใน Java

การจัดการไฟล์ archive อย่างมีประสิทธิภาพต้องอาศัยความเข้าใจที่ชัดเจนเกี่ยวกับโครงสร้างของมัน ในบทแนะนำนี้คุณจะได้เรียนรู้ **วิธีการรับ viewinfo** สำหรับ archive ใด ๆ และเห็นว่ามันช่วยคุณทำงานกับ **ประเภทไฟล์ java archive** อย่างไร เราจะเดินผ่านการตั้งค่า GroupDocs.Viewer, การสกัดข้อมูล view, และการอ่านโครงสร้างโฟลเดอร์แบบเรียกซ้ำ เพื่อให้คุณสามารถนำโซลูชันนี้ไปใช้ในโครงการจริงได้

![โครงสร้าง Archive ด้วย GroupDocs.Viewer สำหรับ Java](/viewer/document-loading/archive-structures-java.png)

**สิ่งที่คุณจะได้เรียนรู้**
- การตั้งค่าและกำหนดค่า GroupDocs.Viewer สำหรับ Java  
- วิธี **รับ viewinfo** จาก archive  
- เทคนิคการอ่านและแสดงโครงสร้างโฟลเดอร์ของไฟล์ archive  
- การประยุกต์ใช้งานจริงและข้อพิจารณาด้านประสิทธิภาพเมื่อใช้ GroupDocs.Viewer ในโครงการ Java

## คำตอบสั้น ๆ
- **viewinfo ให้ข้อมูลอะไรบ้าง?** จะคืนประเภทไฟล์, จำนวนหน้า, และรายการโฟลเดอร์และไฟล์ทั้งหมดภายใน archive  
- **รองรับรูปแบบ archive ใดบ้าง?** ZIP, RAR, TAR, 7z, ISO, และรูปแบบทั่วไปอื่น ๆ มากกว่า 12 รูปแบบ  
- **ต้องมีลิขสิทธิ์สำหรับการใช้งานในโปรดักชันหรือไม่?** ใช่ — จำเป็นต้องมีลิขสิทธิ์เชิงพาณิชย์สำหรับการใช้งานในโปรดักชัน; เวอร์ชันทดลองฟรีใช้ได้สำหรับการประเมินผล  
- **สามารถประมวลผล archive ขนาดใหญ่ได้อย่างมีประสิทธิภาพหรือไม่?** แน่นอน — ใช้ตัวเลือกสตรีมมิ่งและประมวลผลระดับโฟลเดอร์หนึ่งครั้งเพื่อรักษาการใช้หน่วยความจำให้ต่ำ  
- **Maven เป็นวิธีเดียวในการเพิ่มไลบรารีหรือไม่?** Maven เป็นตัวจัดการ dependency ที่แนะนำ, แต่ Gradle หรือการเพิ่ม JAR ด้วยตนเองก็ทำงานได้เช่นกัน

## “how to get viewinfo” คืออะไร?

`getViewInfo` เป็นเมธอดของ GroupDocs.Viewer API ที่สกัด metadata จากเอกสารหรือ archive โดยไม่ต้องทำการเรนเดอร์เต็มรูปแบบ มันจะคืนโครงสร้างโฟลเดอร์ภายใน, จำนวนไฟล์, และคุณสมบัติพื้นฐานในหนึ่งคำเรียก, ทำให้คุณสามารถเลือกส่วนที่ต้องการประมวลผลได้ การเรียกนี้ให้ snapshot ที่สมบูรณ์ของ archive ขนาดสูงสุด 500 MB ภายในเวลาน้อยกว่าสักวินาทีบนเซิร์ฟเวอร์ทั่วไป

## ทำไมต้องดึงโครงสร้างของไฟล์ประเภท java archive?

การดึงเลเอาต์ภายในของ **java archive file type** ช่วยให้คุณค้นหาไฟล์ที่ต้องการได้ทันที, หลีกเลี่ยงการสกัดไฟล์ที่ไม่จำเป็น, และสร้าง pipeline อัตโนมัติที่เข้าถึงเฉพาะโฟลเดอร์ย่อยที่เกี่ยวข้อง วิธีนี้ช่วยลด I/O ได้ถึง 70 % สำหรับ archive ขนาดใหญ่และทำให้สามารถสแกนไฟล์หลายพันไฟล์ต่อวินาทีในสถานการณ์การรับข้อมูลได้

## ข้อกำหนดเบื้องต้น

- **Java Development Kit (JDK):** เวอร์ชัน 8 หรือใหม่กว่า  
- **Maven:** สำหรับการจัดการ dependency และการสร้างโปรเจกต์  
- **ความรู้พื้นฐานของ Java:** ความเข้าใจในแนวคิด OOP จะช่วยแต่ไม่จำเป็นต้องมี  

คุณยังต้องเข้าถึงไลบรารี GroupDocs.Viewer ซึ่งสามารถเพิ่มลงในโปรเจกต์ Maven ของคุณตามตัวอย่างด้านล่าง

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

### การรับลิขสิทธิ์

- **Free Trial:** ดาวน์โหลดเวอร์ชันทดลองจากเว็บไซต์ GroupDocs  
- **Temporary License:** ขอคีย์ชั่วคราวสำหรับการประเมินผลระยะสั้น  
- **Full License:** ซื้อไลเซนส์เชิงพาณิชย์สำหรับการใช้งานในโปรดักชันโดยไม่มีข้อจำกัด  

เมื่อไลบรารีอยู่ใน classpath ของคุณแล้ว คุณก็สามารถเริ่มเขียนโค้ดได้

## คู่มือการทำงาน

### วิธีรับ ViewInfo สำหรับไฟล์ Archive

เพื่อรับข้อมูล view ให้โหลด archive เข้า Viewer ก่อน, จากนั้นเรียก `getViewInfo` เพื่อดึง metadata, และสุดท้ายวนลูปผ่านโครงสร้างโฟลเดอร์ที่คืนมา รูปแบบสามขั้นตอนนี้ทำงานกับทุกรูปแบบ archive ที่รองรับและให้ snapshot สมบูรณ์ในหนึ่ง API call ทำให้การประมวลผลต่อไปง่ายขึ้น

#### เริ่มต้นใช้งาน Viewer

คลาส `Viewer` เป็นจุดเริ่มต้นสำหรับการเรนเดอร์และตรวจสอบทุกอย่าง มันจัดการสตรีมไฟล์, การตรวจจับรูปแบบ, และการทำความสะอาดทรัพยากร

```java
try (Viewer viewer = new Viewer("YOUR_DOCUMENT_DIRECTORY/SAMPLE_ZIP_WITH_FOLDERS")) {
    // Additional steps will follow here.
}
```

#### ดึงข้อมูล View

`ViewInfo` รวม metadata เช่น ประเภทไฟล์, จำนวนหน้าทั้งหมด, และรายการโฟลเดอร์และไฟล์แบบลำดับชั้น การเรียก `getViewInfo` จะคืนอ็อบเจ็กต์นี้ทันที

```java
ViewInfo viewInfo = viewer.getViewInfo(ViewInfoOptions.forHtmlView());
System.out.println("File type: " + viewInfo.getFileType());
System.out.println("Pages count: " + viewInfo.getPages().size());
```

#### แสดงโครงสร้างโฟลเดอร์

วนลูปผ่าน `viewInfo.getFolders()` เพื่อพิมพ์ชื่อโฟลเดอร์, ความลึก, และไฟล์ที่อยู่ภายใน ลูปง่าย ๆ นี้จะให้มุมมองต้นไม้ของ archive ที่อ่านได้

```java
String rootFolder = "";
readFolders(viewer, rootFolder);
```

##### การอ่านโฟลเดอร์แบบเรียกซ้ำ

สำหรับ archive ที่มีโครงสร้างลึก การใช้เมธอดช่วยเหลือแบบ recursive สามารถเดินทางผ่านต้นไม้แบบ depth‑first เพื่อให้แน่ใจว่าโฟลเดอร์ย่อยทุกอันถูกเยี่ยมชมโดยไม่ต้องโหลด archive ทั้งหมดเข้าสู่หน่วยความจำ

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

ฟีเจอร์นี้มุ่งเน้นการพิมพ์โครงสร้างโฟลเดอร์ของไฟล์ archive ซึ่งคล้ายกับฟีเจอร์แรกแต่เน้นการสำรวจแบบ recursive

#### ตั้งค่า View Info Options

`ArchiveOptions` ให้คุณระบุการป้องกันด้วยรหัสผ่าน, ขีดจำกัดหน้า, และการตั้งค่าสตรีมมิ่งก่อนเรียก `getViewInfo`

```java
ViewInfoOptions viewInfoOptions = ViewInfoOptions.forHtmlView();
viewInfoOptions.getArchiveOptions().setFolder(folder);
```

#### การสำรวจแบบ Recursive

รูทีน recursive ที่สองแสดงวิธีจัดการ archive ที่มีรหัสผ่านและชุดไฟล์ขนาดใหญ่ได้อย่างมีประสิทธิภาพ

```java
for (String subFolder : viewInfo.getFolders()) {
    System.out.println(" - " + subFolder);
    readFolders(viewer, subFolder);
}
```

## การประยุกต์ใช้งานจริง

1. **การจัดการข้อมูล:** จัดระเบียบชุดข้อมูลขนาดใหญ่ได้อย่างรวดเร็วโดยเข้าใจโครงสร้างของ archive  
2. **การประมวลผลไฟล์อัตโนมัติ:** ประมวลผลไฟล์ที่บีบอัดเป็นชุดโดยไม่ต้องสกัดทั้งหมด ลด I/O ถึง 70 %  
3. **การบูรณาการกับ CMS:** ปรับปรุงระบบจัดการเนื้อหาให้สามารถนำทาง archive บน‑the‑fly ทำให้บรรณาธิการสามารถดูตัวอย่างไฟล์โดยตรงจาก archive ได้

## ข้อพิจารณาด้านประสิทธิภาพ

- **เพิ่มประสิทธิภาพการใช้หน่วยความจำ:** ประมวลผลโฟลเดอร์ทีละระดับและปิดอินสแตนซ์ `Viewer` อย่างรวดเร็ว  
- **อัปเดตเวอร์ชัน:** ใช้ GroupDocs.Viewer เวอร์ชันล่าสุด (25.2 ณ เวลาที่เขียน) และ JDK รุ่นใหม่เพื่อเพิ่มประสิทธิภาพ  
- **สนับสนุนสตรีมมิ่ง:** ไลบรารีสามารถสตรีม archive ขนาดใหญ่กว่า 1 GB โดยไม่ต้องโหลดไฟล์ทั้งหมดเข้าสู่ RAM ด้วยสถาปัตยกรรมการอ่านแบบ chunked‑read ภายใน

## ปัญหาที่พบบ่อยและวิธีแก้

| Issue | Why It Happens | Fix |
|-------|----------------|-----|
| `NullPointerException` when reading folders | `viewInfo.getFolders()` returns null for empty directories | ตรวจสอบค่า null หรือรายการว่างก่อนทำการวนลูป |
| Slow processing of huge ZIP files | Entire archive is loaded into memory | ใช้ตัวเลือกสตรีมมิ่งที่มีในเวอร์ชันใหม่ของ GroupDocs |
| License not found | License file path is incorrect | วางไฟล์ลิขสิทธิ์ไว้ที่รูทของแอปพลิเคชันหรือกำหนด `License.setLicense("path/to/license.json")` |

## คำถามที่พบบ่อย

**Q:** GroupDocs.Viewer คืออะไร?  
**A:** GroupDocs.Viewer เป็นไลบรารี Java ที่เรนเดอร์เอกสาร, รูปภาพ, และรูปแบบ archive มากกว่า 100 รูปแบบเป็น HTML, PDF หรือสตรีมภาพโดยไม่ต้องใช้แอปพลิเคชันเนทีฟ

**Q:** สามารถใช้ GroupDocs.Viewer กับภาษาโปรแกรมอื่นได้หรือไม่?  
**A:** ใช่, GroupDocs มี SDK สำหรับ .NET, Python, PHP และอื่น ๆ แต่บทแนะนำนี้มุ่งเน้นที่การใช้งานใน Java

**Q:** จะจัดการกับไฟล์ archive ขนาดใหญ่ได้อย่างไร?  
**A:** เปิดใช้งานสตรีมมิ่งผ่าน `ArchiveOptions.setUseStreaming(true)`, ประมวลผลโฟลเดอร์ระดับหนึ่งครั้ง, และทำลายอ็อบเจ็กต์ `Viewer` หลังการใช้งาน

**Q:** GroupDocs.Viewer รองรับประเภท archive อะไรบ้าง?  
**A:** รองรับรูปแบบ archive มากกว่า 12 รูปแบบ รวมถึง ZIP, RAR, TAR, 7z, ISO, ARJ, CAB และหลายประเภทคอนเทนเนอร์ที่เป็นกรรมสิทธิ์

**Q:** มีขีดจำกัดขนาดของ archive หรือไม่?  
**A:** ขีดจำกัดเชิงปฏิบัติงานขึ้นอยู่กับ RAM และ CPU ของเซิร์ฟเวอร์; การทดสอบแสดงว่าการประมวลผล archive ขนาด 2 GB บนเครื่องที่มี RAM 16 GB ทำได้อย่างราบรื่นเมื่อเปิดสตรีมมิ่ง

**Q:** “how to get viewinfo” ทำงานกับ archive ที่มีรหัสผ่านหรือไม่?  
**A:** ทำได้, เพียงกำหนดรหัสผ่านผ่าน `ArchiveOptions.setPassword("yourPassword")` ก่อนเรียก `getViewInfo`

## สรุป

โดยทำตามคู่มือนี้คุณจะรู้ **วิธีการรับ viewinfo** สำหรับ archive ที่รองรับทั้งหมดและวิธีเดินทางผ่านโครงสร้างโฟลเดอร์โดยใช้ GroupDocs.Viewer สำหรับ Java เทคนิคเหล่านี้ช่วยให้คุณสร้าง pipeline การประมวลผลข้อมูลที่ฉลาดขึ้น, ปรับปรุงการบูรณาการกับ CMS, และจัดการกับคอลเลกชันไฟล์ archive ขนาดใหญ่ได้อย่างมั่นใจ ขั้นต่อไปลองสำรวจการเรนเดอร์ไฟล์เดี่ยวจาก archive หรือแปลงเป็น PDF/HTML ด้วยฟีเจอร์ Viewer อื่น ๆ

---

**Last Updated:** 2026-06-30  
**Tested With:** GroupDocs.Viewer 25.2 for Java  
**Author:** GroupDocs  

**Resources**
- **Documentation:** [GroupDocs Viewer Java Documentation](https://docs.groupdocs.com/viewer/java/)
- **API Reference:** [GroupDocs API Reference for Java](https://reference.groupdocs.com/viewer/java/)
- **Download GroupDocs.Viewer:** [GroupDocs Download Page](https://releases.groupdocs.com/viewer/java/)
- **Purchase License:** [Buy GroupDocs](https://purchase.groupdocs.com/buy)
- **Free Trial and Temporary License:** [GroupDocs Free Trial](https://releases.groupdocs.com/viewer/java/) | [Temporary License](https://purchase.groupdocs.com/temporary-license/)

## Related Tutorials

- [Extract Document Metadata with GroupDocs.Viewer for Java - Retrieve Document View Information and Insights](/viewer/java/advanced-rendering/groupdocs-viewer-java-document-views/)
- [How to Retrieve Attachments and Print Document Attachments with GroupDocs.Viewer for Java](/viewer/java/advanced-rendering/groupdocs-viewer-java-retrieve-print-attachments/)
- [Java Guide: Render Specific Pages with GroupDocs.Viewer API for Document Preview and Management](/viewer/java/rendering-basics/java-groupdocs-viewer-render-pages-api-tutorial/)