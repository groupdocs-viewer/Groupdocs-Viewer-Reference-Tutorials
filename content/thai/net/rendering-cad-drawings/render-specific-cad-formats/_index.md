---
title: เรนเดอร์รูปแบบ CAD เฉพาะ (CF2)
linktitle: เรนเดอร์รูปแบบ CAD เฉพาะ (CF2)
second_title: GroupDocs.Viewer .NET API
description: เรียนรู้วิธีเรนเดอร์รูปแบบ CAD เฉพาะ เช่น CF2 เป็น HTML, JPG, PNG และ PDF โดยใช้ Groupdocs.Viewer สำหรับ .NET
weight: 12
url: /th/net/rendering-cad-drawings/render-specific-cad-formats/
---
## การแนะนำ
ในบทช่วยสอนนี้ เราจะสำรวจวิธีการเรนเดอร์รูปแบบ CAD เฉพาะโดยใช้ Groupdocs.Viewer สำหรับ .NET Groupdocs.Viewer เป็น API โปรแกรมดูเอกสารอันทรงพลังที่ช่วยให้นักพัฒนาสามารถแสดงเอกสารมากกว่า 170 ประเภทในแอปพลิเคชันของตน โดยไม่ต้องติดตั้งซอฟต์แวร์ภายนอกใดๆ โดยเฉพาะ เราจะเน้นไปที่การเรนเดอร์รูปแบบ CAD เช่น CF2 เป็นรูปแบบเอาต์พุตต่างๆ เช่น HTML, JPG, PNG และ PDF
## ข้อกำหนดเบื้องต้น
ก่อนที่เราจะเจาะลึกบทช่วยสอน ตรวจสอบให้แน่ใจว่าคุณมีข้อกำหนดเบื้องต้นดังต่อไปนี้:
- ติดตั้ง Visual Studio บนระบบของคุณแล้ว
-  Groupdocs.Viewer สำหรับ .NET SDK คุณสามารถดาวน์โหลดได้จาก[ที่นี่](https://releases.groupdocs.com/viewer/net/).
- ความรู้พื้นฐานเกี่ยวกับภาษาการเขียนโปรแกรม C#
## นำเข้าเนมสเปซ
ขั้นแรก เรามานำเข้าเนมสเปซที่จำเป็นสำหรับการเรนเดอร์รูปแบบ CAD
```csharp
using GroupDocs.Viewer.Options;
using System;
using System.IO;
```
ตอนนี้ เราจะแบ่งแต่ละตัวอย่างออกเป็นหลายขั้นตอน:
## เรนเดอร์ CF2 เป็น HTML
### ขั้นตอนที่ 1: กำหนดไดเร็กทอรีเอาต์พุตที่จะบันทึก HTML ที่แสดงผล
```csharp
string outputDirectory = "Your Document Directory";
```
### ขั้นตอนที่ 2: กำหนดรูปแบบเส้นทางไฟล์สำหรับเอาต์พุต HTML
```csharp
string pageFilePathFormat = Path.Combine(outputDirectory, "CF2_result.html");
```
### ขั้นตอนที่ 3: เริ่มต้นวัตถุ Viewer และระบุไฟล์ CF2 อินพุต
```csharp
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_CF2))
{
    HtmlViewOptions options = HtmlViewOptions.ForEmbeddedResources(pageFilePathFormat);
    // ตั้งค่าตัวเลือกการแสดงผลเพิ่มเติมหากจำเป็น
    // options.CadOptions = CadOptions.ForRenderingByScaleFactor(0.7f);
    viewer.View(options);
}
```
## เรนเดอร์ CF2 เป็น JPG
### ขั้นตอนที่ 1: กำหนดรูปแบบเส้นทางไฟล์สำหรับเอาต์พุต JPG
```csharp
pageFilePathFormat = Path.Combine(outputDirectory, "CF2_result.jpg");
```
### ขั้นตอนที่ 2: เริ่มต้นวัตถุ Viewer และระบุไฟล์ CF2 อินพุต
```csharp
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_CF2))
{
    JpgViewOptions options = new JpgViewOptions(pageFilePathFormat);
    // ตั้งค่าตัวเลือกการแสดงผลเพิ่มเติมหากจำเป็น
    // options.CadOptions = CadOptions.ForRenderingByScaleFactor(0.7f);
    viewer.View(options);
}
```
## เรนเดอร์ CF2 เป็น PNG

### ขั้นตอนที่ 1: กำหนดรูปแบบเส้นทางไฟล์สำหรับเอาต์พุต PNG
```csharp
pageFilePathFormat = Path.Combine(outputDirectory, "CF2_result.png");
```
### ขั้นตอนที่ 2: เริ่มต้นวัตถุ Viewer และระบุไฟล์ CF2 อินพุต
```csharp
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_CF2))
{
    PngViewOptions options = new PngViewOptions(pageFilePathFormat);
    // ตั้งค่าตัวเลือกการแสดงผลเพิ่มเติมหากจำเป็น
    // options.CadOptions = CadOptions.ForRenderingByScaleFactor(0.7f);
    viewer.View(options);
}
```
## เรนเดอร์ CF2 เป็น PDF
### ขั้นตอนที่ 1: กำหนดรูปแบบเส้นทางไฟล์สำหรับเอาต์พุต PDF
```csharp
pageFilePathFormat = Path.Combine(outputDirectory, "CF2_result.pdf");
```
### ขั้นตอนที่ 2: เริ่มต้นวัตถุ Viewer และระบุไฟล์ CF2 อินพุต
```csharp
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_CF2))
{
    PdfViewOptions options = new PdfViewOptions(pageFilePathFormat);
    // ตั้งค่าตัวเลือกการแสดงผลเพิ่มเติมหากจำเป็น
    // options.CadOptions = CadOptions.ForRenderingByScaleFactor(0.7f);
    viewer.View(options);
}
```

## บทสรุป
ในบทช่วยสอนนี้ เราได้เรียนรู้วิธีเรนเดอร์รูปแบบ CAD เฉพาะ เช่น CF2 โดยใช้ Groupdocs.Viewer สำหรับ .NET ด้วยการทำตามคำแนะนำทีละขั้นตอน คุณสามารถรวมความสามารถในการเรนเดอร์เอกสารเข้ากับแอปพลิเคชัน .NET ของคุณได้อย่างง่ายดาย
## คำถามที่พบบ่อย
### Groupdocs.Viewer สามารถเรนเดอร์รูปแบบ CAD อื่นนอกเหนือจาก CF2 ได้หรือไม่
ใช่ Groupdocs.Viewer รองรับรูปแบบ CAD ที่หลากหลาย รวมถึง DWG, DXF, DGN และอื่นๆ
### Groupdocs.Viewer เหมาะสำหรับการเรนเดอร์เอกสารบนเว็บแอปพลิเคชันหรือไม่
Groupdocs.Viewer สามารถผสานรวมเข้ากับเว็บแอปพลิเคชันได้อย่างราบรื่นเพื่อเรนเดอร์เอกสารในเบราว์เซอร์ได้โดยตรง
### Groupdocs.Viewer จำเป็นต้องมีการอ้างอิงภายนอกสำหรับการเรนเดอร์หรือไม่
ไม่ Groupdocs.Viewer เป็น API แบบสแตนด์อโลน และไม่จำเป็นต้องอาศัยการขึ้นต่อกันภายนอกหรือการติดตั้งซอฟต์แวร์
### ฉันสามารถปรับแต่งตัวเลือกการเรนเดอร์ตามความต้องการของฉันได้หรือไม่?
ใช่ Groupdocs.Viewer มีตัวเลือกการเรนเดอร์ที่หลากหลายซึ่งสามารถปรับแต่งให้ตรงตามความต้องการเฉพาะของคุณได้
### มีรุ่นทดลองใช้สำหรับ Groupdocs.Viewer หรือไม่
 ใช่ คุณสามารถดาวน์โหลด Groupdocs.Viewer เวอร์ชันทดลองใช้ฟรีได้จาก[ที่นี่](https://releases.groupdocs.com/).