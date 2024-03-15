---
title: เรนเดอร์รูปภาพ CMX
linktitle: เรนเดอร์รูปภาพ CMX
second_title: GroupDocs.Viewer .NET API
description: เรียนรู้วิธีเรนเดอร์รูปภาพ CMX เป็นรูปแบบต่างๆ ได้อย่างง่ายดายโดยใช้ GroupDocs.Viewer สำหรับ .NET ปรับปรุงการจัดการเอกสารของคุณ
type: docs
weight: 13
url: /th/net/image-rendering/render-cmx-images/
---
## การแนะนำ
ในด้านการจัดการและการจัดการเอกสาร การแสดงภาพจากรูปแบบต่างๆ ถือเป็นงานสำคัญ GroupDocs.Viewer สำหรับ .NET ทำให้กระบวนการนี้ง่ายขึ้นโดยมอบฟังก์ชันที่ครอบคลุมสำหรับการแสดงภาพ CMX ในรูปแบบต่างๆ เช่น HTML, JPG, PNG และ PDF บทช่วยสอนนี้จะแนะนำคุณตลอดกระบวนการเรนเดอร์รูปภาพ CMX แบบทีละขั้นตอนโดยใช้ GroupDocs.Viewer สำหรับ .NET
## ข้อกำหนดเบื้องต้น
ก่อนที่จะเข้าสู่บทช่วยสอน ตรวจสอบให้แน่ใจว่าคุณมีข้อกำหนดเบื้องต้นต่อไปนี้:
1.  GroupDocs.Viewer สำหรับ .NET Library: ดาวน์โหลดและติดตั้ง GroupDocs.Viewer สำหรับ .NET Library จาก[ที่นี่](https://releases.groupdocs.com/viewer/net/).
2. สภาพแวดล้อมการพัฒนา: มีสภาพแวดล้อมการพัฒนาการทำงานที่ตั้งค่าด้วย .NET Framework
3. ไฟล์ภาพ CMX: รับไฟล์ภาพ CMX ที่คุณต้องการแสดงผล

## การนำเข้าเนมสเปซ
ก่อนดำเนินการต่อ ตรวจสอบให้แน่ใจว่าได้นำเข้าเนมสเปซที่จำเป็นเพื่อเข้าถึงฟังก์ชัน GroupDocs.Viewer ในแอปพลิเคชัน .NET ของคุณ:
```csharp
using GroupDocs.Viewer.Options;
using System;
using System.IO;
```

## แสดงผลเป็น HTML
```csharp
string outputDirectory = "Your Document Directory";
string pageFilePathFormat = Path.Combine(outputDirectory, "cmx_result_{0}.html");
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_CMX))
{
    HtmlViewOptions options = HtmlViewOptions.ForEmbeddedResources(pageFilePathFormat);
    viewer.View(options);
}
```
- กำหนดไดเร็กทอรีเอาท์พุต: ตั้งค่าไดเร็กทอรีที่คุณต้องการจัดเก็บไฟล์ HTML ที่แสดงผล
- ระบุรูปแบบเส้นทางไฟล์: กำหนดรูปแบบสำหรับไฟล์ HTML เอาท์พุต
- สร้างอินสแตนซ์ Viewer Object: สร้างอินสแตนซ์ของคลาส Viewer ด้วยไฟล์รูปภาพ CMX
- ตัวเลือกการแสดงผล HTML: กำหนดค่าตัวเลือกการแสดงผล HTML เช่น การฝังทรัพยากร
- เรนเดอร์ CMX เป็น HTML: เรียกใช้เมธอด View ของออบเจ็กต์วิวเวอร์เพื่อเรนเดอร์รูปภาพ CMX เป็น HTML
## แสดงผลเป็น JPG
```csharp
string pageFilePathFormat = Path.Combine(outputDirectory, "cmx_result_{0}.jpg");
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_CMX))
{
    JpgViewOptions options = new JpgViewOptions(pageFilePathFormat);
    
    viewer.View(options);
}
```
- กำหนดไดเร็กทอรีเอาท์พุต: ตั้งค่าไดเร็กทอรีสำหรับจัดเก็บไฟล์ JPG ที่เรนเดอร์
- ระบุรูปแบบเส้นทางไฟล์: กำหนดรูปแบบสำหรับไฟล์ JPG เอาท์พุต
- สร้างอินสแตนซ์ Viewer Object: สร้างอินสแตนซ์ของคลาส Viewer ด้วยไฟล์รูปภาพ CMX
- ตัวเลือกการเรนเดอร์ JPG: กำหนดค่าตัวเลือกการเรนเดอร์ JPG
- เรนเดอร์ CMX เป็น JPG: เรียกใช้เมธอด View ของออบเจ็กต์ตัวแสดงเพื่อเรนเดอร์รูปภาพ CMX เป็น JPG
## แสดงผลเป็น PNG
```csharp
string pageFilePathFormat = Path.Combine(outputDirectory, "cmx_result_{0}.png");
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_CMX))
{
    PngViewOptions options = new PngViewOptions(pageFilePathFormat);
   
    viewer.View(options);
}
```
- กำหนดไดเร็กทอรีเอาท์พุต: ตั้งค่าไดเร็กทอรีสำหรับจัดเก็บไฟล์ PNG ที่แสดงผล
- ระบุรูปแบบเส้นทางไฟล์: กำหนดรูปแบบสำหรับไฟล์ PNG เอาท์พุต
- สร้างอินสแตนซ์ Viewer Object: สร้างอินสแตนซ์ของคลาส Viewer ด้วยไฟล์รูปภาพ CMX
- ตัวเลือกการเรนเดอร์ PNG: กำหนดค่าตัวเลือกการเรนเดอร์ PNG
- เรนเดอร์ CMX เป็น PNG: เรียกใช้เมธอด View ของออบเจ็กต์วิวเวอร์เพื่อเรนเดอร์รูปภาพ CMX เป็น PNG
## แสดงผลเป็น PDF
```csharp
string pageFilePathFormat = Path.Combine(outputDirectory, "cmx_result.pdf");
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_CMX))
{
    PdfViewOptions options = new PdfViewOptions(pageFilePathFormat);
   
    viewer.View(options);
}
```
- กำหนดไดเร็กทอรีเอาท์พุต: ตั้งค่าไดเร็กทอรีสำหรับจัดเก็บไฟล์ PDF ที่เรนเดอร์
- ระบุรูปแบบเส้นทางไฟล์: กำหนดรูปแบบสำหรับไฟล์ PDF เอาท์พุต
- สร้างอินสแตนซ์ Viewer Object: สร้างอินสแตนซ์ของคลาส Viewer ด้วยไฟล์รูปภาพ CMX
- ตัวเลือกการเรนเดอร์ PDF: กำหนดค่าตัวเลือกการเรนเดอร์ PDF
- เรนเดอร์ CMX เป็น PDF: เรียกใช้เมธอด View ของออบเจ็กต์วิวเวอร์เพื่อเรนเดอร์รูปภาพ CMX เป็น PDF

## บทสรุป
โดยสรุป GroupDocs.Viewer สำหรับ .NET นำเสนอโซลูชันที่มีประสิทธิภาพสำหรับการแสดงภาพ CMX ในรูปแบบต่างๆ ได้อย่างราบรื่น ด้วยการทำตามขั้นตอนที่ระบุไว้ในบทช่วยสอนนี้ คุณสามารถรวมความสามารถในการเรนเดอร์รูปภาพ CMX เข้ากับแอปพลิเคชัน .NET ของคุณได้อย่างง่ายดาย ซึ่งช่วยเพิ่มประสิทธิภาพการจัดการเอกสาร
## คำถามที่พบบ่อย
### ฉันสามารถเรนเดอร์หน้าเฉพาะของรูปภาพ CMX ได้หรือไม่
ใช่ คุณสามารถแสดงผลหน้าเว็บที่ต้องการได้โดยการระบุหมายเลขหน้าในตัวเลือกการแสดงผล
### GroupDocs.Viewer สำหรับ .NET เข้ากันได้กับกรอบงาน .NET ทั้งหมดหรือไม่
ใช่ GroupDocs.Viewer สำหรับ .NET เข้ากันได้กับเฟรมเวิร์ก .NET หลายเฟรม รวมถึง .NET Core และ .NET Framework
### GroupDocs.Viewer รองรับการเรนเดอร์รูปภาพ CMX ที่เข้ารหัสหรือไม่
ใช่ GroupDocs.Viewer รองรับการเรนเดอร์ภาพ CMX ที่เข้ารหัสด้วยคีย์ถอดรหัสที่เหมาะสม
### ฉันสามารถปรับแต่งตัวเลือกการเรนเดอร์สำหรับรูปแบบเอาต์พุตต่างๆ ได้หรือไม่
แน่นอนว่า GroupDocs.Viewer มีตัวเลือกมากมายสำหรับปรับแต่งพารามิเตอร์การเรนเดอร์ตามความต้องการของคุณ
### มีฟอรัมชุมชนสำหรับการสนับสนุน GroupDocs.Viewer หรือไม่
 ใช่ คุณสามารถขอความช่วยเหลือและมีส่วนร่วมกับชุมชน GroupDocs.Viewer บนฟอรัมสนับสนุนได้[ที่นี่](https://forum.groupdocs.com/c/viewer/9).