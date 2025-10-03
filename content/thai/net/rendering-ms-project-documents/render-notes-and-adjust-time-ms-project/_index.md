---
"description": "ฝึกฝนการเรนเดอร์เอกสาร MS Project ด้วย GroupDocs.Viewer สำหรับ .NET เรนเดอร์บันทึก ปรับหน่วยเวลา และสำรวจรูปแบบเอาต์พุตต่างๆ ได้อย่างง่ายดาย"
"linktitle": "การเรนเดอร์บันทึกและปรับหน่วยเวลา (MS Project)"
"second_title": "API ของ GroupDocs.Viewer .NET"
"title": "การเรนเดอร์บันทึกและปรับหน่วยเวลา (MS Project)"
"url": "/th/net/rendering-ms-project-documents/render-notes-and-adjust-time-ms-project/"
"weight": 11
type: docs
---
# การเรนเดอร์บันทึกและปรับหน่วยเวลา (MS Project)

## การแนะนำ
GroupDocs.Viewer สำหรับ .NET เป็น API การเรนเดอร์เอกสารอันทรงพลังที่ช่วยให้นักพัฒนาสามารถดูและจัดการรูปแบบเอกสารต่างๆ ภายในแอปพลิเคชัน .NET ของตนเองได้ ในบทช่วยสอนนี้ เราจะเน้นที่การเรนเดอร์บันทึกและการปรับหน่วยเวลาสำหรับเอกสาร MS Project โดยเฉพาะ
## ข้อกำหนดเบื้องต้น
ก่อนที่เราจะเริ่ม โปรดตรวจสอบให้แน่ใจว่าคุณมีข้อกำหนดเบื้องต้นดังต่อไปนี้:
1. GroupDocs.Viewer สำหรับ .NET: ตรวจสอบให้แน่ใจว่าคุณได้ดาวน์โหลดและติดตั้งไลบรารี GroupDocs.Viewer สำหรับ .NET แล้ว คุณสามารถดาวน์โหลดได้จาก [ที่นี่](https://releases-groupdocs.com/viewer/net/).
2. สภาพแวดล้อมการพัฒนา: ตั้งค่าสภาพแวดล้อมการพัฒนาที่คุณต้องการพร้อมการรองรับ .NET
3. เอกสาร MS Project: เตรียมเอกสาร MS Project ตัวอย่างไว้สำหรับการทดสอบ
## นำเข้าเนมสเปซ
ก่อนอื่นให้เรานำเข้าเนมสเปซที่จำเป็นเพื่อเริ่มต้นการเรนเดอร์เอกสาร MS Project:
## ขั้นตอนที่ 1: นำเข้าเนมสเปซ
```csharp
using GroupDocs.Viewer.Options;
using System;
using System.IO;
```
ตอนนี้เราได้นำเข้าเนมสเปซที่จำเป็นแล้ว มาแบ่งตัวอย่างแต่ละตัวอย่างออกเป็นหลายขั้นตอนเพื่อความเข้าใจที่ครอบคลุม
## การเรนเดอร์เอกสาร MS Project เป็น HTML
หากต้องการแสดงเอกสาร MS Project เป็นรูปแบบ HTML พร้อมหมายเหตุ ให้ทำตามขั้นตอนเหล่านี้:
### ขั้นตอนที่ 2: ตั้งค่าไดเรกทอรีผลลัพธ์และรูปแบบไฟล์
```csharp
string outputDirectory = "Your Document Directory";
string pageFilePathFormat = Path.Combine(outputDirectory, "mpp_result.html");
```
### ขั้นตอนที่ 3: เริ่มต้นวัตถุ Viewer และตั้งค่าตัวเลือก
```csharp
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_MPP))
{
    HtmlViewOptions options = HtmlViewOptions.ForEmbeddedResources(pageFilePathFormat);
    options.RenderNotes = true;
```
### ขั้นตอนที่ 4: เรนเดอร์เอกสารเป็น HTML
```csharp
viewer.View(options);
```
## การเรนเดอร์เอกสาร MS Project เป็นรูปแบบภาพ
คุณสามารถเรนเดอร์เอกสาร MS Project เป็นรูปแบบภาพเช่น JPG และ PNG ได้ ดังต่อไปนี้:
### ขั้นตอนที่ 5: ตั้งค่าไดเรกทอรีผลลัพธ์และรูปแบบไฟล์สำหรับ JPG
```csharp
pageFilePathFormat = Path.Combine(outputDirectory, "mpp_{0}_result.jpg");
```
### ขั้นตอนที่ 6: เริ่มต้น Viewer Object และตั้งค่าตัวเลือก JPG
```csharp
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_MPP))
{
    JpgViewOptions options = new JpgViewOptions(pageFilePathFormat);
    options.RenderNotes = true;
```
### ขั้นตอนที่ 7: เรนเดอร์เอกสารเป็น JPG
```csharp
viewer.View(options);
```
ทำซ้ำขั้นตอนที่คล้ายกันสำหรับการเรนเดอร์เป็น PNG และรูปแบบภาพอื่น ๆ
## การเรนเดอร์เอกสาร MS Project เป็น PDF
หากต้องการแสดงเอกสาร MS Project เป็นรูปแบบ PDF ให้ดำเนินการดังต่อไปนี้:
### ขั้นตอนที่ 8: ตั้งค่าไดเรกทอรีผลลัพธ์และรูปแบบไฟล์สำหรับ PDF
```csharp
pageFilePathFormat = Path.Combine(outputDirectory, "mpp_result.pdf");
```
### ขั้นตอนที่ 9: เริ่มต้น Viewer Object และตั้งค่าตัวเลือก PDF
```csharp
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_MPP))
{
    PdfViewOptions options = new PdfViewOptions(pageFilePathFormat);
    options.RenderNotes = true;
```
### ขั้นตอนที่ 10: เรนเดอร์เอกสารเป็น PDF
```csharp
viewer.View(options);
```

## บทสรุป
ขอแสดงความยินดี! คุณได้เรียนรู้วิธีการแสดงเอกสาร MS Project และปรับหน่วยเวลาโดยใช้ GroupDocs.Viewer สำหรับ .NET สำเร็จแล้ว นำความรู้เหล่านี้ไปใช้ในโครงการของคุณเพื่อปรับปรุงความสามารถในการดูเอกสาร
## คำถามที่พบบ่อย
### ฉันสามารถแสดงเอกสาร MS Project เป็นรูปแบบอื่นนอกจาก HTML, รูปภาพ และ PDF ได้หรือไม่
ใช่ GroupDocs.Viewer สำหรับ .NET รองรับการเรนเดอร์เป็นรูปแบบต่างๆ เช่น DOCX, XLSX, PPTX และอื่นๆ อีกมากมาย
### มีเวอร์ชันทดลองใช้สำหรับ GroupDocs.Viewer สำหรับ .NET หรือไม่
ใช่ คุณสามารถรับการทดลองใช้ฟรีได้จาก [ที่นี่](https://releases-groupdocs.com/).
### ฉันจะได้รับใบอนุญาตชั่วคราวสำหรับ GroupDocs.Viewer สำหรับ .NET ได้อย่างไร
เยี่ยม [ลิงค์นี้](https://purchase.groupdocs.com/temporary-license/) เพื่อขอรับใบอนุญาตชั่วคราว
### ฉันสามารถหาเอกสารสำหรับ GroupDocs.Viewer สำหรับ .NET ได้ที่ไหน
อ้างอิงเอกสารประกอบ [ที่นี่](https://tutorials-groupdocs.com/viewer/net/).
### ฉันสามารถขอความช่วยเหลือหรือถามคำถามที่เกี่ยวข้องกับ GroupDocs.Viewer สำหรับ .NET ได้ที่ใด
คุณสามารถเยี่ยมชมฟอรั่มสนับสนุนได้ [ที่นี่](https://forum-groupdocs.com/c/viewer/9).