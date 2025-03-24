---
title: เรนเดอร์ Visio Figures
linktitle: เรนเดอร์ Visio Figures
second_title: GroupDocs.Viewer .NET API
description: เรียนรู้วิธีเรนเดอร์ตัวเลข Visio โดยใช้ GroupDocs.Viewer สำหรับ .NET ด้วยความครอบคลุมนี้ ปรับปรุงความสามารถในการดูเอกสารในแอปพลิเคชัน .NET ของคุณ
weight: 10
url: /th/net/rendering-visio-documents/render-visio-figures/
---

# เรนเดอร์ Visio Figures

## การแนะนำ
ในยุคดิจิทัลปัจจุบัน การแสดงเอกสารมีบทบาทสำคัญในแอปพลิเคชันต่างๆ ไม่ว่าจะเป็นการแสดงเอกสารบนเว็บไซต์หรือแปลงเป็นรูปแบบต่างๆ การเรนเดอร์ที่มีประสิทธิภาพถือเป็นสิ่งสำคัญ GroupDocs.Viewer สำหรับ .NET มอบโซลูชันที่มีประสิทธิภาพสำหรับการดูและจัดการเอกสารภายในแอปพลิเคชัน .NET ในบทช่วยสอนนี้ เราจะเจาะลึกเกี่ยวกับการเรนเดอร์ตัวเลข Visio โดยใช้ GroupDocs.Viewer สำหรับ .NET โดยแจกแจงกระบวนการออกเป็นขั้นตอนง่ายๆ
## ข้อกำหนดเบื้องต้น
ก่อนที่จะเข้าสู่บทช่วยสอน ตรวจสอบให้แน่ใจว่าคุณมีข้อกำหนดเบื้องต้นต่อไปนี้:
1. การตั้งค่าสภาพแวดล้อม: ตรวจสอบให้แน่ใจว่าคุณมีสภาพแวดล้อมการทำงานสำหรับการพัฒนา .NET
2.  GroupDocs.Viewer for .NET: ดาวน์โหลดและติดตั้ง GroupDocs.Viewer for .NET จาก[ลิ้งค์ดาวน์โหลด](https://releases.groupdocs.com/viewer/net/).
3. ความเข้าใจพื้นฐานของ C#: ทำความคุ้นเคยกับพื้นฐานภาษาการเขียนโปรแกรม C#
4. เอกสาร Visio ตัวอย่าง: เตรียมเอกสาร Visio ตัวอย่างให้พร้อมสำหรับการเรนเดอร์

## นำเข้าเนมสเปซ
ในโปรเจ็กต์ C# ของคุณ ให้เริ่มต้นด้วยการนำเข้าเนมสเปซที่จำเป็น:
```csharp
using GroupDocs.Viewer.Options;
using System;
using System.IO;
```
## 1. แสดงผลเป็น HTML
```csharp
string outputDirectory = "Your Document Directory";
string pageFilePathFormat = Path.Combine(outputDirectory, "result_page.html");
using (Viewer viewer = new Viewer("YourVisioDocumentPath"))
{
    HtmlViewOptions options = HtmlViewOptions.ForEmbeddedResources(pageFilePathFormat);
    options.VisioRenderingOptions.RenderFiguresOnly = true;
    options.VisioRenderingOptions.FigureWidth = 250;
    viewer.View(options);
}
```
- Output Directory: กำหนดไดเร็กทอรีที่จะบันทึก HTML ที่แสดงผล
- รูปแบบเส้นทางไฟล์เพจ: ระบุรูปแบบเส้นทางสำหรับเพจ HTML
- การเตรียมใช้งานตัวแสดง: เตรียมใช้งานวัตถุตัวแสดงด้วยเส้นทางไปยังเอกสาร Visio
- ตัวเลือกมุมมอง HTML: กำหนดค่าตัวเลือกสำหรับการแสดงผล HTML
- ตัวเลือกการเรนเดอร์ Visio: ตั้งค่าตัวเลือกเฉพาะสำหรับการเรนเดอร์ Visio เช่น การแสดงเฉพาะภาพและความกว้างของภาพ
## 2. เรนเดอร์เป็น JPG
```csharp
string pageFilePathFormat = Path.Combine(outputDirectory, "visio_result.jpg");
using (Viewer viewer = new Viewer("YourVisioDocumentPath"))
{
    JpgViewOptions options = new JpgViewOptions(pageFilePathFormat);
    options.VisioRenderingOptions.RenderFiguresOnly = true;
    options.VisioRenderingOptions.FigureWidth = 250;
    viewer.View(options);
}
```
- เช่นเดียวกับการเรนเดอร์เป็น HTML ให้กำหนดค่าตัวเลือกสำหรับการเรนเดอร์เป็นรูปแบบ JPG
## 3. แสดงผลเป็น PNG
```csharp
string pageFilePathFormat = Path.Combine(outputDirectory, "visio_result.png");
using (Viewer viewer = new Viewer("YourVisioDocumentPath"))
{
    PngViewOptions options = new PngViewOptions(pageFilePathFormat);
    options.VisioRenderingOptions.RenderFiguresOnly = true;
    options.VisioRenderingOptions.FigureWidth = 250;
    viewer.View(options);
}
```
- การกำหนดค่าสำหรับการเรนเดอร์เป็นรูปแบบ PNG จะมีรูปแบบคล้ายกับการเรนเดอร์ JPG
## 4. แสดงผลเป็น PDF
```csharp
string pageFilePathFormat = Path.Combine(outputDirectory, "visio_result.pdf");
using (Viewer viewer = new Viewer("YourVisioDocumentPath"))
{
    PdfViewOptions options = new PdfViewOptions(pageFilePathFormat);
    options.VisioRenderingOptions.RenderFiguresOnly = true;
    options.VisioRenderingOptions.FigureWidth = 250;
    viewer.View(options);
}
```
- สำหรับการเรนเดอร์เป็น PDF ให้กำหนดค่าตัวเลือกเฉพาะสำหรับรูปแบบ PDF

## บทสรุป
ในบทช่วยสอนนี้ เราได้สำรวจวิธีการเรนเดอร์ตัวเลข Visio โดยใช้ GroupDocs.Viewer สำหรับ .NET ด้วยการทำตามคำแนะนำทีละขั้นตอน คุณสามารถผสานรวมความสามารถในการเรนเดอร์เอกสารเข้ากับแอปพลิเคชัน .NET ของคุณได้อย่างราบรื่น ช่วยเพิ่มประสบการณ์ผู้ใช้และประสิทธิภาพการทำงาน
## คำถามที่พบบ่อย
### ฉันสามารถปรับแต่งตัวเลือกการเรนเดอร์สำหรับตัวเลข Visio ได้หรือไม่
ใช่ GroupDocs.Viewer สำหรับ .NET มีตัวเลือกมากมายสำหรับการปรับแต่งการเรนเดอร์ รวมถึงความกว้างของรูปภาพ การเรนเดอร์เฉพาะตัวเลข และอื่นๆ อีกมากมาย
### GroupDocs.Viewer สำหรับ .NET เหมาะสำหรับการแสดงผลเอกสารขนาดใหญ่หรือไม่
GroupDocs.Viewer สำหรับ .NET ได้รับการปรับให้เหมาะสมที่สุดสำหรับการจัดการการเรนเดอร์เอกสารขนาดใหญ่อย่างมีประสิทธิภาพ
### GroupDocs.Viewer รองรับรูปแบบเอกสารอื่นนอกเหนือจาก Visio หรือไม่
ใช่ GroupDocs.Viewer รองรับรูปแบบเอกสารที่หลากหลาย รวมถึง PDF, Microsoft Office, AutoCAD และอื่นๆ
### ฉันสามารถรวม GroupDocs.Viewer เข้ากับเว็บแอปพลิเคชันได้หรือไม่
ใช่ GroupDocs.Viewer สามารถผสานรวมเข้ากับเว็บแอปพลิเคชันได้อย่างราบรื่นเพื่อการดูและจัดการเอกสาร
### มีรุ่นทดลองให้ทดสอบก่อนซื้อหรือไม่?
ใช่ คุณสามารถทดลองใช้ฟรีได้จาก[เว็บไซต์](https://releases.groupdocs.com/) เพื่อทดสอบความสามารถของ GroupDocs.Viewer สำหรับ .NET