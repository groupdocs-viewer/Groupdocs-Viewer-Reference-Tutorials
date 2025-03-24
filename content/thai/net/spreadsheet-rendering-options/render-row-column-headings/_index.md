---
title: แสดงผลส่วนหัวของแถวและคอลัมน์
linktitle: แสดงผลส่วนหัวของแถวและคอลัมน์
second_title: GroupDocs.Viewer .NET API
description: ปรับปรุงการดูเอกสารใน .NET! เรียนรู้วิธีการแสดงผลส่วนหัวของแถวและคอลัมน์โดยใช้ GroupDocs.Viewer สำหรับ .NET สำรวจเอาต์พุต HTML, JPG, PNG และ PDF
weight: 18
url: /th/net/spreadsheet-rendering-options/render-row-column-headings/
---
## การแนะนำ
คุณต้องการปรับปรุงประสบการณ์การดูเอกสารของคุณในแอปพลิเคชัน .NET หรือไม่? ด้วย GroupDocs.Viewer สำหรับ .NET คุณสามารถเรนเดอร์ส่วนหัวของแถวและคอลัมน์จากไฟล์สเปรดชีตของคุณได้อย่างราบรื่น ในบทช่วยสอนนี้ เราจะแนะนำคุณตลอดกระบวนการแสดงส่วนหัวของแถวและคอลัมน์โดยใช้รูปแบบเอาต์พุตที่แตกต่างกัน เช่น HTML, JPG, PNG และ PDF
## ข้อกำหนดเบื้องต้น
ก่อนที่เราจะเจาะลึกบทช่วยสอน ตรวจสอบให้แน่ใจว่าคุณมีข้อกำหนดเบื้องต้นต่อไปนี้:
- ติดตั้ง GroupDocs.Viewer สำหรับไลบรารี .NET แล้ว
- ไฟล์ XLSX ตัวอย่างเพื่อการทดสอบ
- ความรู้ด้านการทำงานของการพัฒนา C# และ .NET
## นำเข้าเนมสเปซ
ในโค้ด C# ของคุณ ตรวจสอบให้แน่ใจว่าคุณนำเข้าเนมสเปซที่จำเป็นเพื่อใช้ GroupDocs.Viewer:
```csharp
using GroupDocs.Viewer.Options;
using System;
using System.IO;
```
## 1. ตั้งค่าไดเร็กทอรีเอาท์พุต
```csharp
string outputDirectory = "Your Document Directory";
string pageFilePathFormat = Path.Combine(outputDirectory, "page_{0}.html");
```
## 2. แสดงผลเป็น HTML
```csharp
using (Viewer viewer = new Viewer("SAMPLE.XLSX"))
{
    HtmlViewOptions options = HtmlViewOptions.ForEmbeddedResources(pageFilePathFormat);
    options.SpreadsheetOptions.RenderHeadings = true;
    viewer.View(options, 1, 2, 3);
}
```
## 3. เรนเดอร์เป็น JPG
```csharp
pageFilePathFormat = Path.Combine(outputDirectory, "page_{0}.jpg");
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_XLSX))
{
    JpgViewOptions options = new JpgViewOptions(pageFilePathFormat);
    options.SpreadsheetOptions.RenderHeadings = true;
    viewer.View(options, 1, 2, 3);
}
```
## 4. เรนเดอร์เป็น PNG
```csharp
pageFilePathFormat = Path.Combine(outputDirectory, "page_{0}.png");
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_XLSX))
{
    PngViewOptions options = new PngViewOptions(pageFilePathFormat);
    options.SpreadsheetOptions.RenderHeadings = true;
    viewer.View(options, 1, 2, 3);
}
```
## 5. แสดงผลเป็น PDF
```csharp
pageFilePathFormat = Path.Combine(outputDirectory, "output.pdf");
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_XLSX))
{
    PdfViewOptions options = new PdfViewOptions(pageFilePathFormat);
    options.SpreadsheetOptions.RenderHeadings = true;
    viewer.View(options, 1, 2, 3);
}
```
## บทสรุป
ยินดีด้วย! คุณแสดงผลส่วนหัวของแถวและคอลัมน์จากสเปรดชีตของคุณสำเร็จแล้วโดยใช้ GroupDocs.Viewer สำหรับ .NET ทดลองใช้รูปแบบเอาต์พุตที่แตกต่างกันเพื่อให้เหมาะกับความต้องการของแอปพลิเคชันของคุณ
## คำถามที่พบบ่อย
### ถาม: ฉันสามารถปรับแต่งไดเร็กทอรีเอาต์พุตสำหรับเอกสารที่แสดงผลได้หรือไม่
 ตอบ: ได้ คุณสามารถตั้งค่าไดเร็กทอรีเอาต์พุตที่คุณต้องการในโค้ดโดยที่`outputDirectory` ตัวแปรถูกกำหนดไว้
### ถาม: GroupDocs.Viewer เข้ากันได้กับรูปแบบสเปรดชีตอื่นหรือไม่
ตอบ: ใช่ GroupDocs.Viewer รองรับรูปแบบสเปรดชีตที่หลากหลาย รวมถึง XLS, XLSX, CSV และอื่นๆ
### ถาม: ฉันจะจัดการกับข้อยกเว้นในระหว่างกระบวนการเรนเดอร์ได้อย่างไร
ตอบ: คุณสามารถใช้บล็อก try-catch เพื่อจัดการกับข้อยกเว้นและบันทึกหรือแสดงข้อความที่เหมาะสมแก่ผู้ใช้
### ถาม: มีข้อกำหนดสิทธิ์การใช้งาน GroupDocs.Viewer ในแอปพลิเคชันของฉันหรือไม่
ตอบ: ใช่ คุณต้องมีใบอนุญาตที่ถูกต้อง คุณสามารถขอรับใบอนุญาตชั่วคราวเพื่อการทดสอบหรือซื้อใบอนุญาตแบบเต็มสำหรับการผลิตได้
### ถาม: ฉันจะรับการสนับสนุนเพิ่มเติมหรือการสนทนาในชุมชนได้จากที่ไหน
 ตอบ: เยี่ยมชม[ฟอรัม GroupDocs.Viewer](https://forum.groupdocs.com/c/viewer/9) สำหรับการสนับสนุนและการอภิปราย