---
"description": "เรียนรู้วิธีการเรนเดอร์รูปแบบ CAD เฉพาะ เช่น CF2 เป็น HTML, JPG, PNG และ PDF โดยใช้ Groupdocs.Viewer สำหรับ .NET"
"linktitle": "เรนเดอร์รูปแบบ CAD เฉพาะ (CF2)"
"second_title": "API ของ GroupDocs.Viewer .NET"
"title": "เรนเดอร์รูปแบบ CAD เฉพาะ (CF2)"
"url": "/th/net/rendering-cad-drawings/render-specific-cad-formats/"
"weight": 12
---

# เรนเดอร์รูปแบบ CAD เฉพาะ (CF2)

## การแนะนำ
ในบทช่วยสอนนี้ เราจะมาเรียนรู้วิธีการเรนเดอร์รูปแบบ CAD เฉพาะโดยใช้ Groupdocs.Viewer สำหรับ .NET Groupdocs.Viewer เป็น API สำหรับดูเอกสารอันทรงพลังที่ช่วยให้ผู้พัฒนาสามารถแสดงเอกสารได้มากกว่า 170 ประเภทในแอปพลิเคชันของตนเองโดยไม่ต้องติดตั้งซอฟต์แวร์ภายนอกใดๆ โดยเฉพาะอย่างยิ่ง เราจะเน้นไปที่การเรนเดอร์รูปแบบ CAD เช่น CF2 เป็นรูปแบบเอาต์พุตต่างๆ เช่น HTML, JPG, PNG และ PDF
## ข้อกำหนดเบื้องต้น
ก่อนที่จะเริ่มลงลึกในบทช่วยสอนนี้ ให้แน่ใจว่าคุณมีข้อกำหนดเบื้องต้นดังต่อไปนี้:
- Visual Studio ติดตั้งอยู่บนระบบของคุณแล้ว
- Groupdocs.Viewer สำหรับ .NET SDK คุณสามารถดาวน์โหลดได้จาก [ที่นี่](https://releases-groupdocs.com/viewer/net/).
- ความรู้พื้นฐานเกี่ยวกับภาษาการเขียนโปรแกรม C#
## นำเข้าเนมสเปซ
ก่อนอื่นให้เรานำเข้าเนมสเปซที่จำเป็นสำหรับการเรนเดอร์รูปแบบ CAD
```csharp
using GroupDocs.Viewer.Options;
using System;
using System.IO;
```
ตอนนี้เรามาแบ่งตัวอย่างแต่ละตัวอย่างออกเป็นหลายขั้นตอน:
## เรนเดอร์ CF2 เป็น HTML
### ขั้นตอนที่ 1: กำหนดไดเรกทอรีเอาต์พุตที่จะบันทึก HTML ที่แสดงผล
```csharp
string outputDirectory = "Your Document Directory";
```
### ขั้นตอนที่ 2: กำหนดรูปแบบเส้นทางไฟล์สำหรับเอาท์พุต HTML
```csharp
string pageFilePathFormat = Path.Combine(outputDirectory, "CF2_result.html");
```
### ขั้นตอนที่ 3: เริ่มต้นวัตถุ Viewer และระบุไฟล์ CF2 อินพุต
```csharp
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_CF2))
{
    HtmlViewOptions options = HtmlViewOptions.ForEmbeddedResources(pageFilePathFormat);
    // ตั้งค่าตัวเลือกการเรนเดอร์เพิ่มเติมหากจำเป็น
    // options.CadOptions = CadOptions.ForRenderingByScaleFactor(0.7f);
    viewer.View(options);
}
```
## เรนเดอร์ CF2 เป็น JPG
### ขั้นตอนที่ 1: กำหนดรูปแบบเส้นทางไฟล์สำหรับเอาท์พุต JPG
```csharp
pageFilePathFormat = Path.Combine(outputDirectory, "CF2_result.jpg");
```
### ขั้นตอนที่ 2: เริ่มต้นวัตถุ Viewer และระบุไฟล์ CF2 อินพุต
```csharp
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_CF2))
{
    JpgViewOptions options = new JpgViewOptions(pageFilePathFormat);
    // ตั้งค่าตัวเลือกการเรนเดอร์เพิ่มเติมหากจำเป็น
    // options.CadOptions = CadOptions.ForRenderingByScaleFactor(0.7f);
    viewer.View(options);
}
```
## เรนเดอร์ CF2 เป็น PNG

### ขั้นตอนที่ 1: กำหนดรูปแบบเส้นทางไฟล์สำหรับเอาท์พุต PNG
```csharp
pageFilePathFormat = Path.Combine(outputDirectory, "CF2_result.png");
```
### ขั้นตอนที่ 2: เริ่มต้นวัตถุ Viewer และระบุไฟล์ CF2 อินพุต
```csharp
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_CF2))
{
    PngViewOptions options = new PngViewOptions(pageFilePathFormat);
    // ตั้งค่าตัวเลือกการเรนเดอร์เพิ่มเติมหากจำเป็น
    // options.CadOptions = CadOptions.ForRenderingByScaleFactor(0.7f);
    viewer.View(options);
}
```
## เรนเดอร์ CF2 เป็น PDF
### ขั้นตอนที่ 1: กำหนดรูปแบบเส้นทางไฟล์สำหรับเอาท์พุต PDF
```csharp
pageFilePathFormat = Path.Combine(outputDirectory, "CF2_result.pdf");
```
### ขั้นตอนที่ 2: เริ่มต้นวัตถุ Viewer และระบุไฟล์ CF2 อินพุต
```csharp
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_CF2))
{
    PdfViewOptions options = new PdfViewOptions(pageFilePathFormat);
    // ตั้งค่าตัวเลือกการเรนเดอร์เพิ่มเติมหากจำเป็น
    // options.CadOptions = CadOptions.ForRenderingByScaleFactor(0.7f);
    viewer.View(options);
}
```

## บทสรุป
ในบทช่วยสอนนี้ เราได้เรียนรู้วิธีการเรนเดอร์รูปแบบ CAD เฉพาะ เช่น CF2 โดยใช้ Groupdocs.Viewer สำหรับ .NET โดยปฏิบัติตามคำแนะนำทีละขั้นตอน คุณจะสามารถผสานรวมความสามารถในการเรนเดอร์เอกสารเข้ากับแอปพลิเคชัน .NET ของคุณได้อย่างง่ายดาย
## คำถามที่พบบ่อย
### Groupdocs.Viewer สามารถแสดงรูปแบบ CAD อื่น ๆ นอกจาก CF2 ได้หรือไม่
ใช่ Groupdocs.Viewer รองรับรูปแบบ CAD มากมาย รวมถึง DWG, DXF, DGN และอื่นๆ อีกมากมาย
### Groupdocs.Viewer เหมาะกับการเรนเดอร์เอกสารในแอปพลิเคชันเว็บหรือไม่
แน่นอนว่า Groupdocs.Viewer สามารถผสานเข้ากับแอปพลิเคชันเว็บได้อย่างราบรื่นในการแสดงเอกสารโดยตรงในเบราว์เซอร์
### Groupdocs.Viewer ต้องมีการอ้างอิงภายนอกเพื่อการแสดงผลหรือไม่
ไม่ Groupdocs.Viewer เป็น API แบบสแตนด์อโลนและไม่จำเป็นต้องพึ่งพาภายนอกหรือติดตั้งซอฟต์แวร์ใดๆ
### ฉันสามารถปรับแต่งตัวเลือกการเรนเดอร์ตามความต้องการของฉันได้หรือไม่
ใช่ Groupdocs.Viewer มีตัวเลือกการเรนเดอร์ต่างๆ ที่สามารถปรับแต่งให้ตรงตามความต้องการเฉพาะของคุณได้
### มีเวอร์ชันทดลองใช้สำหรับ Groupdocs.Viewer หรือไม่
ใช่ คุณสามารถรับ Groupdocs.Viewer เวอร์ชันทดลองใช้งานฟรีได้จาก [ที่นี่](https://releases-groupdocs.com/).