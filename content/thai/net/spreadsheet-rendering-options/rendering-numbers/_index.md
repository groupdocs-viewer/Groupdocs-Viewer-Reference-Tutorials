---
title: การแสดงผลตัวเลข
linktitle: การแสดงผลตัวเลข
second_title: GroupDocs.Viewer .NET API
description: สำรวจพลังของ Groupdocs.Viewer สำหรับ .NET ในการเรนเดอร์ไฟล์ Numbers ได้อย่างราบรื่น แปลงเป็น HTML, JPG, PNG และ PDF ได้อย่างง่ายดาย
weight: 15
url: /th/net/spreadsheet-rendering-options/rendering-numbers/
---

# การแสดงผลตัวเลข

## การแนะนำ
ยินดีต้อนรับสู่บทช่วยสอนทีละขั้นตอนเกี่ยวกับการเรนเดอร์ไฟล์ Numbers โดยใช้ Groupdocs.Viewer สำหรับ .NET ไม่ว่าคุณจะเป็นนักพัฒนาที่มีประสบการณ์หรือเป็นมือใหม่ คู่มือนี้จะแนะนำคุณตลอดขั้นตอนการแปลงเอกสาร Numbers เป็นรูปแบบต่างๆ Groupdocs.Viewer สำหรับ .NET เป็นเครื่องมืออันทรงพลังที่ช่วยให้คุณสามารถผสานรวมความสามารถในการดูเอกสารเข้ากับแอปพลิเคชัน .NET ของคุณได้อย่างราบรื่น
## ข้อกำหนดเบื้องต้น
ก่อนที่จะเข้าสู่บทช่วยสอน ตรวจสอบให้แน่ใจว่าคุณมีข้อกำหนดเบื้องต้นต่อไปนี้:
- ความรู้ด้านการทำงานของการพัฒนา C# และ .NET
-  ติดตั้ง Groupdocs.Viewer สำหรับไลบรารี .NET แล้ว คุณสามารถดาวน์โหลดได้[ที่นี่](https://releases.groupdocs.com/viewer/net/).
- เส้นทางไดเร็กทอรีเอกสารของคุณที่จะบันทึกไฟล์เอาต์พุต
## นำเข้าเนมสเปซ
ในโปรเจ็กต์ C# ของคุณ ตรวจสอบให้แน่ใจว่าคุณนำเข้าเนมสเปซที่จำเป็นเพื่อใช้ไลบรารี Groupdocs.Viewer:
```csharp
using System;
using System.Collections.Generic;
using System.Text;
using System.IO;
using GroupDocs.Viewer.Options;
```
## ขั้นตอนที่ 1: ตั้งค่าไดเรกทอรีผลลัพธ์
ก่อนที่คุณจะเริ่มเรนเดอร์ ให้กำหนดไดเร็กทอรีเอาต์พุตที่จะบันทึกไฟล์ที่แปลงแล้ว แทนที่ "Your Document Directory" ด้วยเส้นทางจริง:
```csharp
string outputDirectory = "Your Document Directory";
```
## ขั้นตอนที่ 2: แสดงผลเป็น HTML หลายหน้า
ใช้โค้ดต่อไปนี้เพื่อแปลงไฟล์ Numbers เป็น HTML หลายหน้า:
```csharp
string pageFileFullPath = Path.Combine(outputDirectory, "Numbers_result.html");
using (Viewer viewer = new Viewer("SAMPLE.NUMBERS"))
{
    HtmlViewOptions options = HtmlViewOptions.ForEmbeddedResources(pageFileFullPath);
    viewer.View(options);
}
```
## ขั้นตอนที่ 3: แสดงผลเป็น JPG
แปลงไฟล์ Numbers เป็นรูปแบบ JPG ด้วยรหัสต่อไปนี้:
```csharp
pageFileFullPath = Path.Combine(outputDirectory, "Numbers_result.jpg");
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_NUMBERS))
{
    JpgViewOptions options = new JpgViewOptions(pageFileFullPath);
    viewer.View(options);
}
```
## ขั้นตอนที่ 4: แสดงผลเป็น PNG
แปลงไฟล์ Numbers เป็นรูปแบบ PNG โดยใช้รหัสต่อไปนี้:
```csharp
pageFileFullPath = Path.Combine(outputDirectory, "Numbers_result.png");
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_NUMBERS))
{
    PngViewOptions options = new PngViewOptions(pageFileFullPath);
    viewer.View(options);
}
```
## ขั้นตอนที่ 5: แสดงผลเป็น PDF
สุดท้าย แปลงไฟล์ Numbers เป็นรูปแบบ PDF โดยใช้รหัสต่อไปนี้:
```csharp
pageFileFullPath = Path.Combine(outputDirectory, "Numbers_result.pdf");
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_NUMBERS))
{
    PdfViewOptions options = new PdfViewOptions(pageFileFullPath);
    viewer.View(options);
}
```
ยินดีด้วย! คุณเรนเดอร์ไฟล์ Numbers เป็นรูปแบบต่างๆ ได้สำเร็จโดยใช้ Groupdocs.Viewer สำหรับ .NET
## บทสรุป
ในบทช่วยสอนนี้ เราได้กล่าวถึงพื้นฐานของการเรนเดอร์ไฟล์ Numbers โดยใช้ Groupdocs.Viewer สำหรับ .NET ไลบรารีอันทรงพลังนี้ให้การบูรณาการอย่างราบรื่นสำหรับการดูและการแปลงเอกสารในแอปพลิเคชัน .NET ของคุณ
## คำถามที่พบบ่อย
### ฉันสามารถใช้ Groupdocs.Viewer สำหรับ .NET กับเอกสารประเภทอื่นได้หรือไม่
ใช่ Groupdocs.Viewer รองรับรูปแบบเอกสารที่หลากหลาย รวมถึง Word, Excel, PDF และอื่นๆ
### มีใบอนุญาตชั่วคราวสำหรับการทดสอบหรือไม่
 ใช่ คุณสามารถขอรับใบอนุญาตชั่วคราวได้[ที่นี่](https://purchase.groupdocs.com/temporary-license/) สำหรับการทดสอบ
### ฉันจะรับการสนับสนุนสำหรับ Groupdocs.Viewer สำหรับ .NET ได้ที่ไหน
 เยี่ยมชม[ฟอรัม Groupdocs.Viewer](https://forum.groupdocs.com/c/viewer/9) เพื่อขอความช่วยเหลือและหารือ
### ฉันจะซื้อ Groupdocs.Viewer สำหรับ .NET เวอร์ชันเต็มได้อย่างไร
 คุณสามารถซื้อเวอร์ชันเต็มได้[ที่นี่](https://purchase.groupdocs.com/buy).
### มีรุ่นทดลองใช้ฟรีหรือไม่?
 ใช่ คุณสามารถสำรวจเวอร์ชันทดลองใช้ฟรีได้[ที่นี่](https://releases.groupdocs.com/).