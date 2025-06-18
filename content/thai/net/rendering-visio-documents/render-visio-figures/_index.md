---
"description": "เรียนรู้วิธีการแสดงภาพ Visio โดยใช้ GroupDocs.Viewer สำหรับ .NET ด้วยเอกสารประกอบที่ครอบคลุมนี้ ปรับปรุงความสามารถในการดูเอกสารในแอปพลิเคชัน .NET ของคุณ"
"linktitle": "เรนเดอร์รูปภาพ Visio"
"second_title": "API ของ GroupDocs.Viewer .NET"
"title": "เรนเดอร์รูปภาพ Visio"
"url": "/th/net/rendering-visio-documents/render-visio-figures/"
"weight": 10
---

# เรนเดอร์รูปภาพ Visio

## การแนะนำ
ในยุคดิจิทัลทุกวันนี้ การเรนเดอร์เอกสารมีบทบาทสำคัญในแอปพลิเคชันต่างๆ ไม่ว่าจะเป็นการแสดงเอกสารบนเว็บไซต์หรือการแปลงเอกสารเป็นรูปแบบต่างๆ การเรนเดอร์ที่มีประสิทธิภาพถือเป็นสิ่งสำคัญ GroupDocs.Viewer สำหรับ .NET มอบโซลูชันที่มีประสิทธิภาพสำหรับการดูและจัดการเอกสารภายในแอปพลิเคชัน .NET ในบทช่วยสอนนี้ เราจะเจาะลึกการเรนเดอร์รูปภาพ Visio โดยใช้ GroupDocs.Viewer สำหรับ .NET โดยแบ่งกระบวนการออกเป็นขั้นตอนง่ายๆ
## ข้อกำหนดเบื้องต้น
ก่อนจะเริ่มบทช่วยสอนนี้ ให้แน่ใจว่าคุณมีข้อกำหนดเบื้องต้นดังต่อไปนี้:
1. การตั้งค่าสภาพแวดล้อม: ตรวจสอบให้แน่ใจว่าคุณมีสภาพแวดล้อมการทำงานสำหรับการพัฒนา .NET
2. GroupDocs.Viewer สำหรับ .NET: ดาวน์โหลดและติดตั้ง GroupDocs.Viewer สำหรับ .NET จาก [ลิงค์ดาวน์โหลด](https://releases-groupdocs.com/viewer/net/).
3. ความเข้าใจพื้นฐานเกี่ยวกับ C#: ทำความคุ้นเคยกับพื้นฐานภาษาการเขียนโปรแกรม C#
4. ตัวอย่างเอกสาร Visio: เตรียมเอกสาร Visio ตัวอย่างให้พร้อมสำหรับการเรนเดอร์

## นำเข้าเนมสเปซ
ในโครงการ C# ของคุณ เริ่มต้นด้วยการนำเข้าเนมสเปซที่จำเป็น:
```csharp
using GroupDocs.Viewer.Options;
using System;
using System.IO;
```
## 1. การเรนเดอร์เป็น HTML
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
- ไดเรกทอรีเอาต์พุต: กำหนดไดเรกทอรีที่จะบันทึก HTML ที่ถูกเรนเดอร์
- รูปแบบเส้นทางไฟล์หน้า: ระบุรูปแบบเส้นทางสำหรับหน้า HTML
- การเริ่มต้นใช้งาน Viewer: เริ่มต้นใช้งานวัตถุ Viewer ด้วยเส้นทางไปยังเอกสาร Visio
- ตัวเลือกมุมมอง HTML: กำหนดค่าตัวเลือกสำหรับการเรนเดอร์ HTML
- ตัวเลือกการเรนเดอร์ Visio: ตั้งค่าตัวเลือกที่เฉพาะเจาะจงสำหรับการเรนเดอร์ Visio เช่น เรนเดอร์เฉพาะรูปภาพและความกว้างของรูปภาพเท่านั้น
## 2. การเรนเดอร์เป็น JPG
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
- คล้ายกับการเรนเดอร์เป็น HTML กำหนดค่าตัวเลือกสำหรับการเรนเดอร์เป็นรูปแบบ JPG
## 3. การเรนเดอร์เป็น PNG
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
- การกำหนดค่าสำหรับการเรนเดอร์เป็นรูปแบบ PNG นั้นมีรูปแบบที่คล้ายกับการเรนเดอร์ JPG
## 4. การเรนเดอร์เป็น PDF
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
- สำหรับการเรนเดอร์เป็น PDF ให้กำหนดค่าตัวเลือกที่เฉพาะเจาะจงสำหรับรูปแบบ PDF

## บทสรุป
ในบทช่วยสอนนี้ เราได้ศึกษาวิธีการแสดงภาพ Visio โดยใช้ GroupDocs.Viewer สำหรับ .NET โดยปฏิบัติตามคำแนะนำทีละขั้นตอน คุณจะสามารถผสานรวมความสามารถในการแสดงเอกสารลงในแอปพลิเคชัน .NET ได้อย่างราบรื่น ช่วยเพิ่มประสบการณ์และประสิทธิภาพการทำงานของผู้ใช้
## คำถามที่พบบ่อย
### ฉันสามารถปรับแต่งตัวเลือกการเรนเดอร์สำหรับรูปภาพ Visio ได้หรือไม่
ใช่ GroupDocs.Viewer สำหรับ .NET มีตัวเลือกมากมายในการปรับแต่งการเรนเดอร์ รวมถึงความกว้างของรูปภาพ การเรนเดอร์เฉพาะรูปภาพ และอื่นๆ อีกมากมาย
### GroupDocs.Viewer สำหรับ .NET เหมาะกับการเรนเดอร์เอกสารขนาดใหญ่หรือไม่
แน่นอน GroupDocs.Viewer สำหรับ .NET ได้รับการปรับปรุงเพื่อจัดการกับการเรนเดอร์เอกสารขนาดใหญ่ได้อย่างมีประสิทธิภาพ
### GroupDocs.Viewer รองรับรูปแบบเอกสารอื่นนอกเหนือจาก Visio หรือไม่
ใช่ GroupDocs.Viewer รองรับรูปแบบเอกสารต่างๆ มากมาย รวมถึง PDF, Microsoft Office, AutoCAD และอื่นๆ อีกมากมาย
### ฉันสามารถรวม GroupDocs.Viewer เข้ากับแอพพลิเคชันเว็บได้หรือไม่
ใช่ GroupDocs.Viewer สามารถผสานรวมเข้ากับแอปพลิเคชันเว็บสำหรับการดูและจัดการเอกสารได้อย่างราบรื่น
### มีเวอร์ชันทดลองใช้งานเพื่อทดสอบก่อนซื้อหรือไม่?
ใช่ คุณสามารถใช้ประโยชน์จากการทดลองใช้ฟรีได้จาก [เว็บไซต์](https://releases.groupdocs.com/) เพื่อทดสอบความสามารถของ GroupDocs.Viewer สำหรับ .NET