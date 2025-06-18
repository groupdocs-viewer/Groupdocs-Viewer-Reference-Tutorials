---
"description": "สำรวจพลังของ Groupdocs.Viewer สำหรับ .NET ในการแสดงไฟล์ Numbers ได้อย่างราบรื่น แปลงเป็น HTML, JPG, PNG และ PDF ได้อย่างง่ายดาย"
"linktitle": "การเรนเดอร์ตัวเลข"
"second_title": "API ของ GroupDocs.Viewer .NET"
"title": "การเรนเดอร์ตัวเลข"
"url": "/th/net/spreadsheet-rendering-options/rendering-numbers/"
"weight": 15
---

# การเรนเดอร์ตัวเลข

## การแนะนำ
ยินดีต้อนรับสู่บทช่วยสอนทีละขั้นตอนเกี่ยวกับการเรนเดอร์ไฟล์ Numbers โดยใช้ Groupdocs.Viewer สำหรับ .NET ไม่ว่าคุณจะเป็นนักพัฒนาที่มีประสบการณ์หรือเป็นมือใหม่ คู่มือนี้จะแนะนำคุณเกี่ยวกับกระบวนการแปลงเอกสาร Numbers เป็นรูปแบบต่างๆ Groupdocs.Viewer สำหรับ .NET เป็นเครื่องมืออันทรงพลังที่ช่วยให้คุณผสานรวมความสามารถในการดูเอกสารเข้ากับแอปพลิเคชัน .NET ได้อย่างราบรื่น
## ข้อกำหนดเบื้องต้น
ก่อนจะเริ่มบทช่วยสอนนี้ โปรดแน่ใจว่าคุณมีข้อกำหนดเบื้องต้นดังต่อไปนี้:
- ความรู้พื้นฐานเกี่ยวกับการพัฒนา C# และ .NET
- ติดตั้งไลบรารี Groupdocs.Viewer สำหรับ .NET แล้ว คุณสามารถดาวน์โหลดได้ [ที่นี่](https://releases-groupdocs.com/viewer/net/).
- เส้นทางไดเร็กทอรีเอกสารของคุณที่ไฟล์เอาท์พุตจะถูกบันทึก
## นำเข้าเนมสเปซ
ในโครงการ C# ของคุณ ตรวจสอบให้แน่ใจว่าคุณได้นำเข้าเนมสเปซที่จำเป็นเพื่อใช้ไลบรารี Groupdocs.Viewer:
```csharp
using System;
using System.Collections.Generic;
using System.Text;
using System.IO;
using GroupDocs.Viewer.Options;
```
## ขั้นตอนที่ 1: ตั้งค่าไดเรกทอรีเอาท์พุต
ก่อนที่คุณจะเริ่มเรนเดอร์ ให้กำหนดไดเรกทอรีเอาต์พุตที่จะบันทึกไฟล์ที่แปลงแล้ว แทนที่ "ไดเรกทอรีเอกสารของคุณ" ด้วยเส้นทางจริง:
```csharp
string outputDirectory = "Your Document Directory";
```
## ขั้นตอนที่ 2: เรนเดอร์เป็น HTML หลายหน้า
ใช้โค้ดต่อไปนี้เพื่อแปลงไฟล์ Numbers เป็น HTML หลายหน้า:
```csharp
string pageFileFullPath = Path.Combine(outputDirectory, "Numbers_result.html");
using (Viewer viewer = new Viewer("SAMPLE.NUMBERS"))
{
    HtmlViewOptions options = HtmlViewOptions.ForEmbeddedResources(pageFileFullPath);
    viewer.View(options);
}
```
## ขั้นตอนที่ 3: เรนเดอร์เป็น JPG
แปลงไฟล์ Numbers เป็นรูปแบบ JPG ด้วยโค้ดต่อไปนี้:
```csharp
pageFileFullPath = Path.Combine(outputDirectory, "Numbers_result.jpg");
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_NUMBERS))
{
    JpgViewOptions options = new JpgViewOptions(pageFileFullPath);
    viewer.View(options);
}
```
## ขั้นตอนที่ 4: เรนเดอร์เป็น PNG
แปลงไฟล์ Numbers เป็นรูปแบบ PNG โดยใช้โค้ดต่อไปนี้:
```csharp
pageFileFullPath = Path.Combine(outputDirectory, "Numbers_result.png");
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_NUMBERS))
{
    PngViewOptions options = new PngViewOptions(pageFileFullPath);
    viewer.View(options);
}
```
## ขั้นตอนที่ 5: เรนเดอร์เป็น PDF
สุดท้ายแปลงไฟล์ Numbers เป็นรูปแบบ PDF โดยใช้โค้ดต่อไปนี้:
```csharp
pageFileFullPath = Path.Combine(outputDirectory, "Numbers_result.pdf");
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_NUMBERS))
{
    PdfViewOptions options = new PdfViewOptions(pageFileFullPath);
    viewer.View(options);
}
```
ขอแสดงความยินดี! คุณได้เรนเดอร์ไฟล์ Numbers เป็นรูปแบบต่างๆ โดยใช้ Groupdocs.Viewer สำหรับ .NET สำเร็จแล้ว
## บทสรุป
ในบทช่วยสอนนี้ เราได้กล่าวถึงพื้นฐานของการเรนเดอร์ไฟล์ Numbers โดยใช้ Groupdocs.Viewer สำหรับ .NET ไลบรารีอันทรงพลังนี้มอบการผสานรวมที่ราบรื่นสำหรับการดูและการแปลงเอกสารในแอปพลิเคชัน .NET ของคุณ
## คำถามที่พบบ่อย
### ฉันสามารถใช้ Groupdocs.Viewer สำหรับ .NET กับประเภทเอกสารอื่นๆ ได้หรือไม่
ใช่ Groupdocs.Viewer รองรับรูปแบบเอกสารต่างๆ มากมาย รวมถึง Word, Excel, PDF และอื่นๆ อีกมากมาย
### ใบอนุญาตชั่วคราวสามารถใช้สำหรับการทดสอบได้หรือไม่?
ใช่ คุณสามารถขอใบอนุญาตชั่วคราวได้ [ที่นี่](https://purchase.groupdocs.com/temporary-license/) เพื่อการทดสอบ
### ฉันสามารถค้นหาการสนับสนุนสำหรับ Groupdocs.Viewer สำหรับ .NET ได้ที่ไหน
เยี่ยมชม [ฟอรัม Groupdocs.Viewer](https://forum.groupdocs.com/c/viewer/9) เพื่อขอความช่วยเหลือและการหารือ
### ฉันจะซื้อ Groupdocs.Viewer เวอร์ชันเต็มสำหรับ .NET ได้อย่างไร
คุณสามารถซื้อเวอร์ชันเต็มได้ [ที่นี่](https://purchase-groupdocs.com/buy).
### มีเวอร์ชันทดลองใช้งานฟรีหรือไม่?
ใช่ คุณสามารถสำรวจเวอร์ชันทดลองใช้งานฟรีได้ [ที่นี่](https://releases-groupdocs.com/).