---
"date": "2025-04-24"
"description": "เรียนรู้วิธีแยกข้อความจากไฟล์ PDF โดยใช้ GroupDocs.Viewer ใน Java ด้วยคู่มือโดยละเอียดนี้ ซึ่งเหมาะอย่างยิ่งสำหรับนักพัฒนาที่ทำงานเกี่ยวกับการประมวลผลข้อมูลและการจัดการเอกสาร"
"title": "ดึงข้อความจาก PDF โดยใช้ GroupDocs.Viewer Java คู่มือที่ครอบคลุมสำหรับนักพัฒนา"
"url": "/th/java/metadata-properties/extract-text-pdf-groupdocs-viewer-java/"
"weight": 1
type: docs
---
# แยกข้อความจาก PDF โดยใช้ GroupDocs.Viewer Java

## การแนะนำ
การแยกข้อความจาก PDF เป็นสิ่งสำคัญสำหรับการจัดการเอกสารดิจิทัลอย่างมีประสิทธิภาพ ในบทช่วยสอนที่ครอบคลุมนี้ เราจะสาธิตวิธีใช้ **โปรแกรมดู GroupDocs.Java** เพื่อแยกข้อความจากไฟล์ PDF ได้อย่างราบรื่น

### สิ่งที่คุณจะได้เรียนรู้:
- ตั้งค่า GroupDocs.Viewer สำหรับ Java
- ดึงข้อความโดยใช้ API อันทรงพลังของ GroupDocs.Viewer
- จัดการการแยกหลายหน้าและหลายบรรทัดภายในเอกสาร
- เพิ่มประสิทธิภาพการทำงานสำหรับ PDF ขนาดใหญ่

มาเริ่มต้นด้วยข้อกำหนดเบื้องต้นที่จำเป็นในการใช้งานฟีเจอร์นี้กันก่อน
## ข้อกำหนดเบื้องต้น
ก่อนที่จะเริ่มต้น ให้แน่ใจว่าคุณมี:
### ห้องสมุดที่จำเป็น:
- **GroupDocs.Viewer สำหรับ Java**:เข้าถึงเวอร์ชัน 25.2 หรือใหม่กว่าสำหรับฟังก์ชันที่จำเป็น
### ข้อกำหนดการตั้งค่าสภาพแวดล้อม:
- สภาพแวดล้อมการพัฒนาด้วย Java (แนะนำ JDK 1.8 ขึ้นไป)
- ติดตั้ง Maven เพื่อการจัดการการอ้างอิง
### ข้อกำหนดเบื้องต้นของความรู้:
- ความเข้าใจพื้นฐานเกี่ยวกับการเขียนโปรแกรมภาษา Java
- ความคุ้นเคยกับ Maven เป็นประโยชน์แต่ไม่จำเป็น
## การตั้งค่า GroupDocs.Viewer สำหรับ Java
บูรณาการ **โปรแกรมดูเอกสารกลุ่ม** ไลบรารีที่ใช้ Maven เพื่อเริ่มแยกข้อความจาก PDF:
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
### การได้มาซึ่งใบอนุญาต:
- **ทดลองใช้งานฟรี**: พร้อมที่จะสำรวจฟีเจอร์ API
- **ใบอนุญาตชั่วคราว**:เพื่อความสามารถในการทดสอบที่ขยายเพิ่ม
- **ซื้อ**: จำเป็นสำหรับการใช้งานเชิงพาณิชย์
#### การเริ่มต้นและการตั้งค่าเบื้องต้น
เริ่มต้นวัตถุ Viewer ด้วยเส้นทางเอกสาร PDF ของคุณดังนี้:
## คู่มือการใช้งาน
ให้เราแบ่งการแยกข้อความออกเป็นขั้นตอนเชิงตรรกะดังนี้:
### การเริ่มต้นวัตถุ Viewer
```java
try (Viewer viewer = new Viewer("YOUR_DOCUMENT_DIRECTORY/SAMPLE_PDF")) {
    // การเริ่มต้นใช้งานเสร็จสิ้น ดำเนินการตามขั้นตอนต่อไป
}
```
นี่คือการเริ่มต้น `Viewer` วัตถุที่มีเส้นทางไฟล์ PDF เป้าหมายของคุณ
### การกำหนดค่า ViewInfoOptions สำหรับการแยกข้อความ
```java
ViewInfoOptions viewInfoOptions = ViewInfoOptions.forHtmlView();
viewInfoOptions.setExtractText(true);
```
กำหนดค่าตัวเลือกเพื่อเปิดใช้งานการดู HTML และการแยกข้อความ เพื่อให้แน่ใจว่าสามารถเข้าถึงเนื้อหาเอกสารที่ประมวลผลแล้วด้วยการตั้งค่าเหล่านี้
### การดึงข้อมูลเอกสาร
```java
PdfViewInfo viewInfo = (PdfViewInfo) viewer.getViewInfo(viewInfoOptions);
```
โดยการโทร `getViewInfo`ดึงข้อมูลรายละเอียดเกี่ยวกับหน้าและโครงสร้าง PDF
### การวนซ้ำผ่านหน้าและบรรทัด
```java
for (Page page : viewInfo.getPages()) {
    for (Line line : page.getLines()) {
        System.out.println(line.getValue());
    }
}
```
วนซ้ำผ่านแต่ละหน้าและแต่ละบรรทัดเพื่อแยกข้อความ ซึ่งช่วยให้ประมวลผลต่อไปได้ เช่น การบันทึกลงในฐานข้อมูล
#### เคล็ดลับการแก้ไขปัญหา:
- ตรวจสอบให้แน่ใจว่าเส้นทางไฟล์ PDF ถูกต้อง
- ตรวจสอบ `setExtractText` เปิดใช้งานหากพบข้อผิดพลาดของตัวเลือกการดู
## การประยุกต์ใช้งานจริง
ความสามารถของ GroupDocs.Viewer ขยายขอบเขตไปไกลเกินกว่าการแยกข้อความธรรมดา การใช้งานจริงประกอบด้วย:
1. **การโยกย้ายข้อมูล**:แยกและย้ายเนื้อหาจากไฟล์ PDF เก่าไปยังฐานข้อมูลที่ทันสมัยหรือโซลูชันบนคลาวด์
2. **การวิเคราะห์เนื้อหา**:ใช้ข้อความที่แยกออกมาเพื่อวิเคราะห์ความรู้สึก การสกัดคำหลัก หรือข้อมูลเชิงลึกอื่นๆ
3. **ระบบจัดการเอกสาร (DMS)**:บูรณาการกับ DMS สำหรับการสร้างดัชนีและการดึงข้อมูลเอกสารอัตโนมัติ
## การพิจารณาประสิทธิภาพ
เมื่อจัดการเอกสารขนาดใหญ่:
- **การใช้ทรัพยากร**:ตรวจสอบการใช้หน่วยความจำ เนื่องจากการประมวลผลหลายหน้าอาจใช้ทรัพยากรมาก
- **การจัดการหน่วยความจำ Java**: จัดการวงจรชีวิตของวัตถุภายใน `try-with-resources` บล็อคอย่างมีประสิทธิภาพเพื่อใช้ประโยชน์จากการรวบรวมขยะของ Java
## บทสรุป
คู่มือนี้แสดงวิธีการตั้งค่า GroupDocs.Viewer สำหรับ Java และแยกข้อความจากไฟล์ PDF อย่างมีประสิทธิภาพ สำรวจคุณสมบัติอื่นๆ ของ GroupDocs.Viewer หรือผสานรวมกับระบบเพิ่มเติมสำหรับเวิร์กโฟลว์ที่ซับซ้อน

## ส่วนคำถามที่พบบ่อย
**ถาม: ฉันสามารถใช้ GroupDocs.Viewer บนเซิร์ฟเวอร์การผลิตได้หรือไม่**

	- A: Yes, but ensure you have an appropriate license. A free trial is suitable only for testing purposes.

**ถาม: การแยกข้อความส่งผลต่อข้อมูลเมตาของ PDF อย่างไร**

	- A: Text extraction focuses on content; metadata remains intact unless explicitly modified.

**ถาม: GroupDocs.Viewer สามารถจัดการรูปแบบไฟล์ใดได้บ้าง นอกเหนือจาก PDF?**

	- A: It supports a wide range of formats, including Word documents and Excel spreadsheets.
	
## ทรัพยากร
- [เอกสารประกอบ](https://docs.groupdocs.com/viewer/java/)
- [เอกสารอ้างอิง API](https://reference.groupdocs.com/viewer/java/)
- [ดาวน์โหลด](https://releases.groupdocs.com/viewer/java/)
- [ซื้อ](https://purchase.groupdocs.com/buy)
- [ทดลองใช้งานฟรี](https://releases.groupdocs.com/viewer/java/)
- [ใบอนุญาตชั่วคราว](https://purchase.groupdocs.com/temporary-license/)
- [ฟอรั่มสนับสนุน](https://forum.groupdocs.com/c/viewer/9)
เราหวังว่าคู่มือนี้จะช่วยให้คุณใช้ประโยชน์จาก GroupDocs.Viewer สำหรับ Java ในโปรเจ็กต์ของคุณได้ ขอให้สนุกกับการเขียนโค้ด!