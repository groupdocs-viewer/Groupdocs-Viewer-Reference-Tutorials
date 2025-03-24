---
title: เรนเดอร์รูปภาพ EMZ และ EMF
linktitle: เรนเดอร์รูปภาพ EMZ และ EMF
second_title: GroupDocs.Viewer .NET API
description: เรียนรู้วิธีเรนเดอร์อิมเมจ EMZ และ EMF เป็นรูปแบบต่างๆ โดยใช้ GroupDocs.Viewer สำหรับ .NET บทช่วยสอนที่ปฏิบัติตามง่ายสำหรับนักพัฒนา
weight: 14
url: /th/net/image-rendering/render-emz-emf-images/
---

# เรนเดอร์รูปภาพ EMZ และ EMF

## การแนะนำ

GroupDocs.Viewer สำหรับ .NET เป็น API การเรนเดอร์เอกสารอันทรงพลังที่ช่วยให้นักพัฒนาสามารถแสดงเอกสารประเภทต่างๆ รวมถึงรูปภาพ EMZ (Enhanced Windows Metafile) และ EMF (Enhanced Metafile) ในแอปพลิเคชัน .NET ของตน ในบทช่วยสอนนี้ เราจะสำรวจวิธีเรนเดอร์รูปภาพ EMZ และ EMF เป็นรูปแบบต่างๆ เช่น HTML, JPG, PNG และ PDF โดยใช้ GroupDocs.Viewer สำหรับ .NET

## ข้อกำหนดเบื้องต้น

ก่อนที่เราจะเริ่มต้น ตรวจสอบให้แน่ใจว่าคุณมีข้อกำหนดเบื้องต้นดังต่อไปนี้:

1.  GroupDocs.Viewer สำหรับ .NET: คุณสามารถดาวน์โหลดไลบรารีได้จาก[ที่นี่](https://releases.groupdocs.com/viewer/net/).
2. สภาพแวดล้อมการพัฒนา: ตรวจสอบให้แน่ใจว่าคุณมีสภาพแวดล้อมการพัฒนาที่เข้ากันได้ซึ่งตั้งค่าไว้สำหรับการพัฒนา .NET
3. ตัวอย่างรูปภาพ EMZ/EMF: มีรูปภาพ EMZ และ EMF ตัวอย่างที่พร้อมสำหรับการเรนเดอร์

## นำเข้าเนมสเปซ

ก่อนที่จะเจาะลึกโค้ด มานำเข้าเนมสเปซที่จำเป็นก่อน:

```csharp
using GroupDocs.Viewer.Options;
using System;
using System.IO;
```

ตอนนี้ เราจะแบ่งแต่ละตัวอย่างออกเป็นหลายขั้นตอนในรูปแบบคำแนะนำทีละขั้นตอน:

## การแสดงภาพ EMZ/EMF เป็น HTML

### ขั้นตอนที่ 1: ตั้งค่าไดเรกทอรีผลลัพธ์:
```csharp
string outputDirectory = "Your Document Directory";
```
 แทนที่`"Your Document Directory"`ด้วยเส้นทางที่คุณต้องการบันทึกไฟล์ HTML ที่แสดงผล

### ขั้นตอนที่ 2: กำหนดรูปแบบเส้นทางไฟล์เพจ:
```csharp
string pageFilePathFormat = Path.Combine(outputDirectory, "emz_result.html");
```
ซึ่งจะระบุรูปแบบเส้นทางไฟล์สำหรับไฟล์ HTML ที่แสดงผล

### ขั้นตอนที่ 3: แสดงผลเป็น HTML:
```csharp
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_EMZ))
{
    HtmlViewOptions options = HtmlViewOptions.ForEmbeddedResources(pageFilePathFormat);
    
    viewer.View(options);
}
```
 รหัสนี้เริ่มต้น`Viewer` วัตถุด้วยรูปภาพ EMZ ตัวอย่างและเรนเดอร์เป็นรูปแบบ HTML โดยใช้ตัวเลือกที่ระบุ

## เรนเดอร์รูปภาพ EMZ/EMF เป็น JPG, PNG และ PDF

ทำซ้ำขั้นตอนต่อไปนี้เพื่อเรนเดอร์เป็นรูปแบบ JPG, PNG และ PDF:

### ขั้นตอนที่ 1: กำหนดรูปแบบเส้นทางไฟล์เพจ:
```csharp
pageFilePathFormat = Path.Combine(outputDirectory, "emz_result.jpg");
```
ปรับชื่อไฟล์และนามสกุลตามรูปแบบเอาต์พุตที่ต้องการ (`jpg`, `png` , หรือ`pdf`).

### ขั้นตอนที่ 2: แสดงผลเป็นรูปแบบที่เกี่ยวข้อง:
```csharp
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_EMZ))
{
    // ปรับตัวเลือกตามรูปแบบเอาต์พุต (JPG, PNG, Pdf)
    JpgViewOptions options = new JpgViewOptions(pageFilePathFormat);
    
    viewer.View(options);
}
```
 แทนที่`JpgViewOptions` กับ`PngViewOptions` หรือ`PdfViewOptions` ตามรูปแบบเอาต์พุตที่ต้องการ

## บทสรุป

โดยสรุป GroupDocs.Viewer สำหรับ .NET มอบโซลูชันที่ราบรื่นสำหรับการแสดงภาพ EMZ และ EMF เป็นรูปแบบต่างๆ ในแอปพลิเคชัน .NET ด้วยการทำตามขั้นตอนที่ระบุไว้ในบทช่วยสอนนี้ นักพัฒนาสามารถรวมความสามารถในการเรนเดอร์เอกสารเข้ากับแอปพลิเคชันของตนได้อย่างง่ายดาย

## คำถามที่พบบ่อย

### ถาม: GroupDocs.Viewer สามารถเรนเดอร์รูปแบบเอกสารอื่นๆ นอกเหนือจากอิมเมจ EMZ และ EMF ได้หรือไม่
ตอบ: ใช่ GroupDocs.Viewer รองรับรูปแบบเอกสารที่หลากหลาย รวมถึง PDF, DOCX, PPTX, XLSX และอื่นๆ

### ถาม: GroupDocs.Viewer สำหรับ .NET มีรุ่นทดลองใช้ฟรีหรือไม่
 ตอบ: ได้ คุณสามารถเข้าถึงรุ่นทดลองใช้ฟรีได้[ที่นี่](https://releases.groupdocs.com/).

### ถาม: GroupDocs.Viewer ให้การสนับสนุนสำหรับนักพัฒนาหรือไม่
 ตอบ: ได้ GroupDocs ให้การสนับสนุนผ่านทาง[ฟอรั่ม](https://forum.groupdocs.com/c/viewer/9) โดยนักพัฒนาสามารถถามคำถามและขอความช่วยเหลือได้

### ถาม: ฉันสามารถซื้อใบอนุญาตชั่วคราวสำหรับ GroupDocs.Viewer สำหรับ .NET ได้หรือไม่
 ตอบ: ได้ มีใบอนุญาตชั่วคราวให้ซื้อได้[ที่นี่](https://purchase.groupdocs.com/temporary-license/).

### ถาม: ฉันจะหาเอกสารโดยละเอียดสำหรับ GroupDocs.Viewer for .NET ได้ที่ไหน
 ตอบ: คุณสามารถดูเอกสารประกอบได้[ที่นี่](https://tutorials.groupdocs.com/viewer/net/)สำหรับคำแนะนำที่ครอบคลุมเกี่ยวกับการใช้ API