---
title: ปรับคุณภาพของภาพในรูปแบบ PDF
linktitle: ปรับคุณภาพของภาพในรูปแบบ PDF
second_title: GroupDocs.Viewer .NET API
description: เรียนรู้วิธีปรับคุณภาพของภาพในเอกสาร PDF โดยใช้ GroupDocs.Viewer สำหรับ .NET ปฏิบัติตามบทช่วยสอนทีละขั้นตอนของเราเพื่อการบูรณาการที่ราบรื่น
weight: 10
url: /th/net/pdf-rendering-options/adjust-image-quality-pdf/
---

# ปรับคุณภาพของภาพในรูปแบบ PDF

## การแนะนำ
GroupDocs.Viewer สำหรับ .NET เป็นไลบรารีที่มีประสิทธิภาพซึ่งช่วยให้นักพัฒนาสามารถรวมความสามารถในการเรนเดอร์เอกสารเข้ากับแอปพลิเคชัน .NET ของตนได้อย่างง่ายดาย คุณสมบัติหลักอย่างหนึ่งของไลบรารีนี้คือความสามารถในการปรับคุณภาพของภาพเมื่อเรนเดอร์เอกสาร PDF ในบทช่วยสอนนี้ เราจะแนะนำคุณตลอดกระบวนการปรับคุณภาพของภาพทีละขั้นตอนโดยใช้ GroupDocs.Viewer สำหรับ .NET
## ข้อกำหนดเบื้องต้น
ก่อนที่เราจะเริ่ม ตรวจสอบให้แน่ใจว่าคุณมีข้อกำหนดเบื้องต้นดังต่อไปนี้:
1. ความรู้พื้นฐานเกี่ยวกับการเขียนโปรแกรม C#
2. ติดตั้ง Visual Studio บนระบบของคุณแล้ว
3. ดาวน์โหลดและติดตั้งไลบรารี GroupDocs.Viewer สำหรับ .NET แล้ว คุณสามารถดาวน์โหลดได้จาก[ที่นี่](https://releases.groupdocs.com/viewer/net/).

## นำเข้าเนมสเปซ
ขั้นแรก คุณต้องนำเข้าเนมสเปซที่จำเป็นเพื่อทำงานกับ GroupDocs.Viewer สำหรับ .NET:
```csharp
using System;
using System.IO;
using GroupDocs.Viewer.Options;
```
## ขั้นตอนที่ 1: กำหนดไดเรกทอรีผลลัพธ์
```csharp
string outputDirectory = "Your Document Directory";
```
 แทนที่`"Your Document Directory"` ด้วยเส้นทางที่คุณต้องการบันทึกหน้า HTML ที่แสดงผล
## ขั้นตอนที่ 2: กำหนดรูปแบบเส้นทางไฟล์เพจ
```csharp
string pageFilePathFormat = Path.Combine(outputDirectory, "page_{0}.html");
```
 บรรทัดนี้กำหนดรูปแบบสำหรับเส้นทางไฟล์ของเพจ HTML ที่แสดงผลแต่ละหน้า`{0}` เป็นตัวสำรองสำหรับหมายเลขหน้า
## ขั้นตอนที่ 3: ปรับคุณภาพของภาพ
```csharp
using (Viewer viewer = new Viewer("Your PDF File Path"))
{
    HtmlViewOptions options = HtmlViewOptions.ForEmbeddedResources(pageFilePathFormat);
    options.PdfOptions.ImageQuality = ImageQuality.Medium;
    viewer.View(options);
}
```
 แทนที่`"Your PDF File Path"` พร้อมเส้นทางไปยังเอกสาร PDF ของคุณ
## ขั้นตอนที่ 4: แสดงเส้นทางเอาต์พุต
```csharp
Console.WriteLine($"\nSource document rendered successfully.\nCheck output in {outputDirectory}.");
```
บรรทัดนี้แสดงเส้นทางที่บันทึกเพจ HTML ที่แสดงผล

## บทสรุป
ในบทช่วยสอนนี้ เราได้เรียนรู้วิธีปรับคุณภาพของภาพเมื่อเรนเดอร์เอกสาร PDF โดยใช้ GroupDocs.Viewer สำหรับ .NET ด้วยการทำตามขั้นตอนง่ายๆ ที่อธิบายไว้ข้างต้น คุณสามารถปรับแต่งคุณภาพของภาพตามความต้องการของคุณได้อย่างง่ายดาย
## คำถามที่พบบ่อย
### ฉันสามารถปรับคุณภาพของภาพสำหรับรูปแบบเอกสารอื่นนอกเหนือจาก PDF ได้หรือไม่
ใช่ GroupDocs.Viewer สำหรับ .NET รองรับรูปแบบเอกสารที่หลากหลาย และคุณสามารถปรับคุณภาพของรูปภาพส่วนใหญ่ได้
### ตัวเลือกคุณภาพของภาพที่มีให้เลือกมีอะไรบ้าง?
GroupDocs.Viewer สำหรับ .NET มีตัวเลือกสำหรับคุณภาพของรูปภาพต่ำ ปานกลาง และสูง
### มีวิธีดูตัวอย่างเอกสารก่อนที่จะเรนเดอร์ด้วยคุณภาพของภาพที่ปรับแล้วหรือไม่?
ได้ คุณสามารถใช้ GroupDocs.Viewer สำหรับ .NET เพื่อสร้างหน้าตัวอย่างเอกสารด้วยการตั้งค่าคุณภาพของภาพที่แตกต่างกัน
### GroupDocs.Viewer สำหรับ .NET จำเป็นต้องมีใบอนุญาตสำหรับการใช้งานเชิงพาณิชย์หรือไม่
 ใช่ คุณต้องได้รับใบอนุญาตสำหรับการใช้งานเชิงพาณิชย์ คุณสามารถซื้อใบอนุญาตได้จาก[ที่นี่](https://purchase.groupdocs.com/buy).
### ฉันจะรับการสนับสนุนสำหรับ GroupDocs.Viewer สำหรับ .NET ได้ที่ไหน
 คุณสามารถรับการสนับสนุนจากฟอรัม GroupDocs.Viewer[ที่นี่](https://forum.groupdocs.com/c/viewer/9).