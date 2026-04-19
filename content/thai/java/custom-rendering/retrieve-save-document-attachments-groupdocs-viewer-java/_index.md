---
date: '2026-02-02'
description: เรียนรู้วิธีดึงและบันทึกไฟล์แนบของเอกสารอย่างมีประสิทธิภาพในแอปพลิเคชัน
  Java โดยใช้ java file output stream และ API ที่ทรงพลังของ GroupDocs.Viewer.
keywords:
- GroupDocs.Viewer Java
- retrieve document attachments Java
- save document attachments GroupDocs
title: วิธีดึงและบันทึกไฟล์แนบของเอกสารโดยใช้ Java File Output Stream กับ GroupDocs.Viewer
  สำหรับ Java
type: docs
url: /th/java/custom-rendering/retrieve-save-document-attachments-groupdocs-viewer-java/
weight: 1
---

# วิธีดึงและบันทึกไฟล์แนบของเอกสารโดยใช้ java file output stream กับ GroupDocs.Viewer for Java

## คำแนะนำ

คุณกำลังมองหาวิธีดึงและจัดการไฟล์แนบของเอกสารโดยอัตโนมัติในแอปพลิเคชัน Java ของคุณโดยใช้ **java file output stream** หรือไม่? ด้วยการเพิ่มขึ้นของการจัดการเอกสารดิจิทัล การมีเครื่องมือที่ทำให้กระบวนการเหล่านี้เป็นไปอย่างราบรื่นและมีประสิทธิภาพจึงเป็นสิ่งสำคัญ มาแนะนำ GroupDocs.Viewer for Java—โซลูชันที่คุณควรใช้เพื่อดึงและบันทึกไฟล์แนบของเอกสารได้อย่างง่ายดาย

![ดึงและบันทึกไฟล์แนบของเอกสารด้วย GroupDocs.Viewer for Java](/viewer/custom-rendering/retrieve-and-save-document-attachments-java.png)

ในบทแนะนำนี้ เราจะสำรวจวิธีใช้พลังของ GroupDocs.Viewer เพื่อดึงไฟล์แนบจากเอกสารและบันทึกลงในไดเรกทอรีที่คุณต้องการ โดยทำตามขั้นตอนนี้ คุณจะได้ทักษะการจัดการข้อมูลเอกสารอย่างมีประสิทธิภาพในสภาพแวดล้อม Java

## คำตอบอย่างรวดเร็ว
- **java file output stream ทำอะไร?** มันเขียนสตรีมไบต์โดยตรงลงไฟล์ ทำให้ข้อมูลไบนารี (เช่นไฟล์แนบ) สามารถบันทึกลงดิสก์ได้.  
- **API ใดที่ดึงไฟล์แนบ?** `Viewer.getAttachments()` คืนรายการเมตาดาต้าไฟล์แนบ.  
- **ฉันสามารถระบุโฟลเดอร์ปลายทางได้หรือไม่?** ได้—ใช้ `Path outputDirectory = Paths.get("YOUR_OUTPUT_DIRECTORY");`.  
- **ต้องการไลเซนส์หรือไม่?** การทดลองใช้ฟรีทำงานสำหรับการประเมิน; จำเป็นต้องมีไลเซนส์แบบชำระเงินสำหรับการใช้งานจริง.  
- **วิธีนี้ปลอดภัยต่อการทำงานหลาย แยกสำหรับStream` เป็นคลาสหลักของ Java ที่เขียนไบต์ดิบลงไฟล์ เป็นตัวเลือกที่เหมาะสมเมื่อคุณต้องการบันทึก หรือ stream กับ GroupDocs.Viewer?
- **การจัดการไบนารีโดยตรง** – ไม่ต้องแปลงผ่านขั้นตอนกลาง; ไบต์ของไฟล์แนบจะถูกเขียนลงไฟล์อย่างตรงตามที่ปรากฏในไฟล์ต้นฉบับ.  
- **ประสิทธิความจำ โดยเฉพาะสำหรับไฟรำรุงรักษาได้ง่าย.

## ข้อกำหนดเบื้องต้น
- **ไลบรารีและการพึ่งพาที่จำเป็น**: เพิ่มไลบล่าง).  
- **การตั้งค่าสภาพแวดล้อม**: IDE สำหรับ Java (IntelliJ IDEA, Eclipse ฯลฯ) พร้อม JDK 8+ ติดตั้ง.  
- **ความรู้พื้นฐานที่ต้องมี**: ความคุ้นเคยกับ Java I/O โดยเฉพาะ `FileOutputStream` และการใช้ Maven เบื้องต้น.

## การตั้งค่า GroupDocs.Viewer สำหรับ Java
เพื่อเริ่มต้นใช้ API ของ GroupDocs.Viewer ในโปรเจกต์ของคุณ คุณต้องติดตั้งผ่าน Maven โดยเพิ่มการกำหนดค่าต่อไปนี้ในไฟล์ `pom.xml` ของคุณ:

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

**ขั้นตอนการรับไลเซนส์:**
- **ทดลองใช้ฟรี**: เริ่มต้นด้วยการทดลองใช้ฟรีเพื่อสำรวจฟีเจอร์ต่าง ๆ.  
- **ไลเซนส์ชั่วคราว**: รับไลเซนส์ชั่วคราวสำหรับช่วงเวลาการประเมินที่ยาวนานขึ้น.  
- **การซื้อ**: สำหรับการใช้งานในผลิตภัณฑ์จริง คุณจะต้องซื้อไลเซนส์.

### การเริ่มต้นและตั้งค่าเบื้องต้น
เมื่อเพิ่ม GroupDocs.Viewer เป็น dependency ในโปรเจกต์ของคุณแล้ว ให้ทำการเริ่มต้นในแอปพลิเคชัน Java ดังนี้:

```java
import com.groupdocs.viewer.Viewer;
import java.nio.file.Path;

public class InitializeViewer {
    public static void main(String[] args) {
        try (Viewer viewer = new Viewer("path/to/your/document")) {
            // Your code to interact with the document goes here.
        } catch (Exception e) {
            e.printStackTrace();
        }
    }
}
```

การตั้งค่าเบื้องต้นนี้จะทำให้ GroupDocs.Viewer พร้อมสำหรับการดึงไฟล์แนบ

## คู่มือการดำเนินการ

### ดึงไฟล์แนบโดยใช้ javaDocs.Viewer ซึ่งฟีเจอร์นี้ช่วยให้แนบแต่ละไฟล์ที่อยู่ในเอกสารของคุณได้

#### ภาพรวม
การดึงไฟล์แนบทำได้โดยเรียกเมธอด `getAttachments` ซึ่งจะคืนรายการอ็อบเจกต์ `Attachment` ที่มีรายละเอียดเช่นชื่อไฟล์และขนาด

#### ขั้นตอนการดำเนินการ
1. **Create a Viewer Instance**  
   เริ่มต้นคลาส `Viewer` ด้วยพาธของเอกสารของคุณ:

   ```java
   import com.groupdocs.viewer.Viewer;
   import com.groupdocs.viewer.examples.TestFiles;
   import com.groupdocs.viewer.results.Attachment;

   public class FeatureRetrieveAttachments {
       public static void main(String[] args) {
           try (Viewer viewer = new Viewer(TestFiles.SAMPLE_MSG_WITH_ATTACHMENTS)) {
               // Proceed to retrieve attachments
           } catch (Exception e) {
               throw new RuntimeException(e);
           }
       }
   }
   ```

2. **Retrieve Attachments**  
   ใช้เมธอด `getAttachments`:

   ```java
   List<Attachment> attachments = viewer.getAttachments();
   for (Attachment attachment : attachments) {
       System.out.println(attachment.getFileName());
   }
   ```

3. **Understanding Parameters and Methods**  
   - `Viewer`: รับพาธไฟล์หรือสตรีมของเอกสาร.  
   - `getAttachments()`: ดึงรายการไฟล์แนบที่แนบมาพร้อมรายละเอียดเช่นชื่อไฟล์.

### บันทึกไฟล์แนบของเอกสารลงในไดเรกทอรี
เมื่อคุณเรียนรู้วิธีดึงไฟล์แนบแล้ว เราจะบันทึกไฟล์เหล่านั้นลงในดเรกทอรีที่คุณต้องการโดยใช้ API ของ GroupDocs.Viewer และ **java file output stream**

#### ภาพรวม
ฟีเจอร์นี้จะบันทึกไฟล์แนบแต่ละไฟล์ที่ดึงมาไว้ในไดเรกทอรีปลายทางที่กำหนด

#### ขั้นตอนการดำเนินการ
1. **Define the Output Directory**  
   ตั้งค่าพาธ `outputDirectory` ที่ไฟล์จะถูกบันทึก:

   ```java
   import java.nio.file.Path;
   import java.nio.file.Paths;

   Path outputDirectory = Paths.get("YOUR_OUTPUT_DIRECTORY");
   ```

2. **Save Attachments**  
   ใช้ลูปเพื่อบันทึกไฟล์แนบแต่ละไฟล์ด้วยเมธอด `saveAttachment`:

   ```java
   try (Viewer viewer = new Viewer(TestFiles.SAMPLE_MSG_WITH_ATTACHMENTS)) {
       List<Attachment> attachments = viewer.getAttachments();
       
       for (Attachment attachment : attachments) {
           final Path file = outputDirectory.resolve(attachment.getFileName());
           try (FileOutputStream outputStream = new FileOutputStream(file.toFile())) {
               viewer.saveAttachment(attachment, outputStream);
           }
       }
   } catch (Exception e) {
       throw new RuntimeException(e);
   }
   ```

3. **Explain Parameters and Methods**  
   - `saveAttachment`: รับอ็อบเจกต์ `Attachment` และไฟล์เอาต์พุตสตรีมเพื่อบันทึกไฟล์แนบ.  
   - `FileOutputStream`: จัดการการเขียนข้อมูลลงไฟล์โดยใช้หลักการของ **java file output stream**.

### เคล็ดลับการแก้ไขปัญหา
- **Missing Dependencies**: ตรวจสอบให้แน่ใจว่าได้เพิ่ม dependency ของ Maven ทั้งหมดอย่างถูกต้อง.  
- **File Path Errors**: ตรวจสอบพาธของเอกสารและไดเรกทอรีปลายทางให้ถูกต้อง.  
- **Access Permissions**: ยืนยันว่าแอปพลิเคชันของคุณมีสิทธิ์อ่าน/เขียนที่จำเป็น.

## การประยุกต์ใช้งานจริง
การใช้ GroupDocs.Viewer ใน Java มีประโยชน์ในหลายสถานการณ์:

1. **Email Clients** – ดึงไฟล์แนบจากอาร์ไคฟ์อีเมลโดยอัตโนมัติเพื่อประมวลผลหรือจัดเก็บ.  
2. **Document Management Systems** – ปรับปรุง DMS ด้วยการดึงและจัดระเบียบไฟล์แนบ.  
3. **Legal Departments** – สกัดไฟล์แนบที่เกี่ยวข้องกับหลักฐานจากเอกสารทางกฎหมายอย่างปลอดภัย.

ความเป็นไปได้ในการผสานรวมกับ CRM, ERP หรือเอนจินเวิร์กโฟลว์แบบกำหนดเองสามารถทำให้กระบวนการธุรกิจเป็นอัตโนมัติมากยิ่งขึ้น ทำให้การจัดการไฟล์แนบเป็นเรื่องราบรื่นในทุกแผนก.

## ข้อควรพิจารณาด้านประสิทธิภาพ
เพื่อเพิ่มประสิทธิภาพเมื่อใช้ GroupDocs.Viewer:

- **Optimize File Handling** – ใช้ buffered streams สำหรับไฟล์ขนาดใหญ่และปิดทรัพยากรโดยเร็ว.  
- **Memory Management** – ปล่อยอินสแตนซ์ `Viewer` อย่างรวดเร็ว (ใช้ try‑with‑resources) เพื่อหลีกเลี่ยงการรั่วของหน่วยความจำ.  

การปฏิบัติตามแนวทางที่ดีที่สุดของ Java จะช่วยเพิ่มประสิทธิภาพของสายการประมวลผลไฟล์แนบของคุณอย่างมาก

## สรุป
คุณได้เรียนรู้วิธีดึงและบันทึกไฟล์แนบของเอกสารโดยใช้ **java file output stream** กับ GroupDocs.Viewer for Java แล้ว API ที่ทรงพลังนี้ทำให้การจัดการข้อมูลเอกสารเป็นเรื่องง่ายและเป็นเครื่องมือสำคัญสำหรับนักพัฒนาที่ทำงานกับเอกสารดิจิทัล

เพื่อสำรวจความสามารถของ GroupDocs.Viewer เพิ่มเติม ลองทดลองฟีเจอร์อื่น ๆ เช่น การเรนเดอร์หน้า, การแปลงรูปแบบ, หรือการสกัดข้อความ หากมีคำถามหรือจำเป็นต้องการสนับสนุน โปรดติดต่อผ่านช่องทางอย่างเป็นทางการ

## คำถามที่พบบ่อย

**Q: ฉันจะติดตั้ง GroupDocs.Viewer ในโปรเจกต์ Java ของฉันได้อย่างไร?**  
A: เพิ่ม dependency ของ Maven ที่แสดงไว้ก่อนหน้านี้; URL ของ repository และเวอร์ชันเป็นสิ่งที่คุณต้องการสำหรับการเริ่มต้นอย่างรวดเร็ว.

**Q: GroupDocs.Viewer รองรับประเภทเอกสารทั้งหมดหรือไม่?**  
A: รองรับรูปแบบหลากหลาย (PDF,ผิดพลาดขณะบันทึกไฟล์แนบควรทำอย่างไร?**  
A: ตรวจสอบว่าพียน.**Q:ส์สำหรับการใช้งานในผลิตภัณฑ์หรือไม่?**  
A: ใช่, จำเป็นต้องมีไลเซนส์ GroupDocs.Viewer ที่ถูกต้องสำหรับการใช้งานในผลิตภัณฑ์. มี**จัดการไบนารีขนาดใหญ่ได้อย่างมีประสิทธิภาพ. ควรตรวจสอบการใช้หน่วยความจำและพิจารณาการสตรีมเป็นชิ้นส่วนหากจำเป็น.

---

**อัปเดตล่าสุด:** 202Docs.Viewer 25.