---
"description": "เรียนรู้วิธีการเรนเดอร์ภาพ EMZ และ EMF เป็นรูปแบบต่างๆ โดยใช้ GroupDocs.Viewer สำหรับ .NET บทช่วยสอนที่ทำตามได้ง่ายสำหรับนักพัฒนา"
"linktitle": "เรนเดอร์ภาพ EMZ และ EMF"
"second_title": "API ของ GroupDocs.Viewer .NET"
"title": "เรนเดอร์ภาพ EMZ และ EMF"
"url": "/th/net/image-rendering/render-emz-emf-images/"
"weight": 14
type: docs
---
# เรนเดอร์ภาพ EMZ และ EMF

## การแนะนำ

GroupDocs.Viewer สำหรับ .NET เป็น API การเรนเดอร์เอกสารอันทรงพลังที่ช่วยให้นักพัฒนาสามารถแสดงเอกสารประเภทต่างๆ รวมถึงภาพ EMZ (Enhanced Windows Metafile) และ EMF (Enhanced Metafile) ในแอปพลิเคชัน .NET ของตนเอง ในบทช่วยสอนนี้ เราจะสำรวจวิธีการเรนเดอร์ภาพ EMZ และ EMF เป็นรูปแบบต่างๆ เช่น HTML, JPG, PNG และ PDF โดยใช้ GroupDocs.Viewer สำหรับ .NET

![เรนเดอร์ภาพ EMZ และ EMF ด้วย GroupDocs.Viewer สำหรับ .NET](/viewer/image-rendering/render-emz-and-emf-images.png)

## ข้อกำหนดเบื้องต้น

ก่อนที่เราจะเริ่ม โปรดตรวจสอบให้แน่ใจว่าคุณมีข้อกำหนดเบื้องต้นดังต่อไปนี้:

1. GroupDocs.Viewer สำหรับ .NET: คุณสามารถดาวน์โหลดไลบรารีได้จาก [ที่นี่](https://releases-groupdocs.com/viewer/net/).
2. สภาพแวดล้อมการพัฒนา: ให้แน่ใจว่าคุณมีการตั้งค่าสภาพแวดล้อมการพัฒนาที่เข้ากันได้สำหรับการพัฒนา .NET
3. ตัวอย่างภาพ EMZ/EMF: มีตัวอย่างภาพ EMZ และ EMF สำหรับการเรนเดอร์

## นำเข้าเนมสเปซ

ก่อนที่จะเจาะลึกโค้ด เรามานำเข้าเนมสเปซที่จำเป็นกันก่อน:

```csharp
using GroupDocs.Viewer.Options;
using System;
using System.IO;
```

ตอนนี้เรามาแบ่งตัวอย่างแต่ละตัวอย่างออกเป็นหลายขั้นตอนในรูปแบบคำแนะนำทีละขั้นตอน:

## การเรนเดอร์ภาพ EMZ/EMF เป็น HTML

### ขั้นตอนที่ 1: ตั้งค่าไดเรกทอรีผลลัพธ์:
```csharp
string outputDirectory = "Your Document Directory";
```
แทนที่ `"Your Document Directory"` ด้วยเส้นทางที่คุณต้องการบันทึกไฟล์ HTML ที่เรนเดอร์แล้ว

### ขั้นตอนที่ 2: กำหนดรูปแบบเส้นทางไฟล์เพจ:
```csharp
string pageFilePathFormat = Path.Combine(outputDirectory, "emz_result.html");
```
นี่จะระบุรูปแบบเส้นทางไฟล์สำหรับไฟล์ HTML ที่แสดงผล

### ขั้นตอนที่ 3: เรนเดอร์เป็น HTML:
```csharp
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_EMZ))
{
    HtmlViewOptions options = HtmlViewOptions.ForEmbeddedResources(pageFilePathFormat);
    
    viewer.View(options);
}
```
รหัสนี้จะเริ่มต้นการ `Viewer` วัตถุที่มีภาพตัวอย่าง EMZ และเรนเดอร์เป็นรูปแบบ HTML โดยใช้ตัวเลือกที่ระบุ

## การเรนเดอร์ภาพ EMZ/EMF เป็น JPG, PNG และ PDF

ทำซ้ำขั้นตอนต่อไปนี้สำหรับการเรนเดอร์เป็นรูปแบบ JPG, PNG และ PDF:

### ขั้นตอนที่ 1: กำหนดรูปแบบเส้นทางไฟล์เพจ:
```csharp
pageFilePathFormat = Path.Combine(outputDirectory, "emz_result.jpg");
```
ปรับชื่อไฟล์และนามสกุลให้ตรงกับรูปแบบผลลัพธ์ที่ต้องการ (`jpg`- `png`, หรือ `pdf`-

### ขั้นตอนที่ 2: เรนเดอร์เป็นรูปแบบที่เกี่ยวข้อง:
```csharp
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_EMZ))
{
    // ปรับแต่งตัวเลือกตามรูปแบบเอาท์พุต (Jpg, PNG, Pdf)
    JpgViewOptions options = new JpgViewOptions(pageFilePathFormat);
    
    viewer.View(options);
}
```
แทนที่ `JpgViewOptions` กับ `PngViewOptions` หรือ `PdfViewOptions` ตามรูปแบบผลลัพธ์ที่ต้องการ

## บทสรุป

โดยสรุป GroupDocs.Viewer สำหรับ .NET มอบโซลูชันที่ราบรื่นสำหรับการเรนเดอร์ภาพ EMZ และ EMF เป็นรูปแบบต่างๆ ในแอปพลิเคชัน .NET โดยทำตามขั้นตอนที่ระบุไว้ในบทช่วยสอนนี้ นักพัฒนาสามารถผสานรวมความสามารถในการเรนเดอร์เอกสารลงในแอปพลิเคชันของตนได้อย่างง่ายดาย

## คำถามที่พบบ่อย

### ถาม: GroupDocs.Viewer สามารถแสดงรูปแบบเอกสารอื่นนอกเหนือจากภาพ EMZ และ EMF ได้หรือไม่
ตอบ: ใช่ GroupDocs.Viewer รองรับรูปแบบเอกสารต่างๆ มากมาย เช่น PDF, DOCX, PPTX, XLSX และอื่นๆ

### ถาม: มีรุ่นทดลองใช้งานฟรีสำหรับ GroupDocs.Viewer สำหรับ .NET หรือไม่
A: ใช่ คุณสามารถเข้าถึงการทดลองใช้ฟรีได้ [ที่นี่](https://releases-groupdocs.com/).

### ถาม: GroupDocs.Viewer ให้การสนับสนุนสำหรับนักพัฒนาหรือไม่
ตอบ ใช่ GroupDocs ให้การสนับสนุนผ่าน [ฟอรั่ม](https://forum.groupdocs.com/c/viewer/9) โดยนักพัฒนาสามารถถามคำถามและขอความช่วยเหลือได้

### ถาม: ฉันสามารถซื้อใบอนุญาตชั่วคราวสำหรับ GroupDocs.Viewer สำหรับ .NET ได้หรือไม่
A: ใช่ ใบอนุญาตชั่วคราวมีจำหน่าย [ที่นี่](https://purchase-groupdocs.com/temporary-license/).

### ถาม: ฉันสามารถหาเอกสารโดยละเอียดสำหรับ GroupDocs.Viewer สำหรับ .NET ได้ที่ไหน
A: คุณสามารถดูเอกสารประกอบได้ [ที่นี่](https://tutorials.groupdocs.com/viewer/net/) เพื่อคำแนะนำที่ครอบคลุมเกี่ยวกับการใช้ API