---
title: เรนเดอร์บันทึกย่อและปรับหน่วยเวลา (โครงการ MS)
linktitle: เรนเดอร์บันทึกย่อและปรับหน่วยเวลา (โครงการ MS)
second_title: GroupDocs.Viewer .NET API
description: ต้นแบบการเรนเดอร์เอกสาร MS Project ด้วย GroupDocs.Viewer สำหรับ .NET เรนเดอร์บันทึก ปรับหน่วยเวลา และสำรวจรูปแบบเอาต์พุตต่างๆ ได้อย่างง่ายดาย
weight: 11
url: /th/net/rendering-ms-project-documents/render-notes-and-adjust-time-ms-project/
---
## การแนะนำ
GroupDocs.Viewer สำหรับ .NET เป็น API การเรนเดอร์เอกสารที่มีประสิทธิภาพซึ่งช่วยให้นักพัฒนาสามารถดูและจัดการรูปแบบเอกสารต่างๆ ภายในแอปพลิเคชัน .NET ของตนได้ ในบทช่วยสอนนี้ เราจะเน้นที่การแสดงบันทึกและการปรับหน่วยเวลาสำหรับเอกสาร MS Project โดยเฉพาะ
## ข้อกำหนดเบื้องต้น
ก่อนที่เราจะเริ่มต้น ตรวจสอบให้แน่ใจว่าคุณมีข้อกำหนดเบื้องต้นดังต่อไปนี้:
1. GroupDocs.Viewer for .NET: ตรวจสอบให้แน่ใจว่าคุณได้ดาวน์โหลดและติดตั้งไลบรารี GroupDocs.Viewer for .NET แล้ว คุณสามารถดาวน์โหลดได้จาก[ที่นี่](https://releases.groupdocs.com/viewer/net/).
2. สภาพแวดล้อมการพัฒนา: ตั้งค่าสภาพแวดล้อมการพัฒนาที่คุณต้องการด้วยการสนับสนุน .NET
3. เอกสารโครงการ MS: เตรียมเอกสารโครงการ MS ตัวอย่างให้พร้อมสำหรับการทดสอบ
## นำเข้าเนมสเปซ
ขั้นแรก เรามานำเข้าเนมสเปซที่จำเป็นเพื่อเริ่มต้นการเรนเดอร์เอกสาร MS Project:
## ขั้นตอนที่ 1: นำเข้าเนมสเปซ
```csharp
using GroupDocs.Viewer.Options;
using System;
using System.IO;
```
ตอนนี้เราได้นำเข้าเนมสเปซที่จำเป็นแล้ว เรามาแบ่งแต่ละตัวอย่างออกเป็นหลายขั้นตอนเพื่อความเข้าใจที่ครอบคลุม
## แสดงผลเอกสารโครงการ MS เป็น HTML
หากต้องการแสดงเอกสาร MS Project เป็นรูปแบบ HTML พร้อมหมายเหตุรวมอยู่ด้วย ให้ทำตามขั้นตอนเหล่านี้:
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
### ขั้นตอนที่ 4: แสดงผลเอกสารเป็น HTML
```csharp
viewer.View(options);
```
## การเรนเดอร์เอกสารโครงการ MS เป็นรูปแบบรูปภาพ
คุณยังสามารถเรนเดอร์เอกสาร MS Project เป็นรูปแบบภาพ เช่น JPG และ PNG มีวิธีดังนี้:
### ขั้นตอนที่ 5: ตั้งค่า Output Directory และรูปแบบไฟล์สำหรับ JPG
```csharp
pageFilePathFormat = Path.Combine(outputDirectory, "mpp_{0}_result.jpg");
```
### ขั้นตอนที่ 6: เริ่มต้นวัตถุ Viewer และตั้งค่าตัวเลือก JPG
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
ทำซ้ำขั้นตอนที่คล้ายกันเพื่อเรนเดอร์เป็น PNG และรูปแบบรูปภาพอื่น ๆ
## การเรนเดอร์เอกสารโครงการ MS เป็น PDF
หากต้องการเรนเดอร์เอกสาร MS Project เป็นรูปแบบ PDF ให้ดำเนินการดังนี้:
### ขั้นตอนที่ 8: ตั้งค่า Output Directory และรูปแบบไฟล์สำหรับ PDF
```csharp
pageFilePathFormat = Path.Combine(outputDirectory, "mpp_result.pdf");
```
### ขั้นตอนที่ 9: เริ่มต้นวัตถุ Viewer และตั้งค่าตัวเลือก PDF
```csharp
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_MPP))
{
    PdfViewOptions options = new PdfViewOptions(pageFilePathFormat);
    options.RenderNotes = true;
```
### ขั้นตอนที่ 10: แสดงผลเอกสารเป็น PDF
```csharp
viewer.View(options);
```

## บทสรุป
ยินดีด้วย! คุณได้เรียนรู้วิธีการเรนเดอร์เอกสาร MS Project และปรับหน่วยเวลาโดยใช้ GroupDocs.Viewer สำหรับ .NET เรียบร้อยแล้ว รวมความรู้นี้เข้ากับโครงการของคุณเพื่อเพิ่มความสามารถในการดูเอกสาร
## คำถามที่พบบ่อย
### ฉันสามารถเรนเดอร์เอกสาร MS Project เป็นรูปแบบอื่นนอกเหนือจาก HTML, รูปภาพ และ PDF ได้หรือไม่
ใช่ GroupDocs.Viewer สำหรับ .NET รองรับการเรนเดอร์ในรูปแบบต่างๆ เช่น DOCX, XLSX, PPTX และอื่นๆ
### มีรุ่นทดลองใช้สำหรับ GroupDocs.Viewer สำหรับ .NET หรือไม่
 ใช่ คุณสามารถทดลองใช้ฟรีได้จาก[ที่นี่](https://releases.groupdocs.com/).
### ฉันจะได้รับใบอนุญาตชั่วคราวสำหรับ GroupDocs.Viewer สำหรับ .NET ได้อย่างไร
 เยี่ยม[ลิงค์นี้](https://purchase.groupdocs.com/temporary-license/) เพื่อขอรับใบอนุญาตชั่วคราว
### ฉันจะหาเอกสารสำหรับ GroupDocs.Viewer for .NET ได้ที่ไหน
 โปรดดูเอกสารประกอบ[ที่นี่](https://tutorials.groupdocs.com/viewer/net/).
### ฉันจะขอความช่วยเหลือหรือถามคำถามที่เกี่ยวข้องกับ GroupDocs.Viewer for .NET ได้ที่ไหน
 คุณสามารถเยี่ยมชมฟอรั่มการสนับสนุน[ที่นี่](https://forum.groupdocs.com/c/viewer/9).