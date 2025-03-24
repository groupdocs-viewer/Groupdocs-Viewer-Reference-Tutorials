---
title: เรนเดอร์ไฟล์ข้อความ (.txt)
linktitle: เรนเดอร์ไฟล์ข้อความ (.txt)
second_title: GroupDocs.Viewer .NET API
description: สำรวจการแปลงไฟล์ข้อความเป็นหลายรูปแบบได้อย่างราบรื่นโดยใช้ GroupDocs.Viewer สำหรับ .NET เพิ่มความสามารถในการจัดการเอกสารของคุณได้อย่างง่ายดาย
weight: 10
url: /th/net/rendering-text-files/render-txt/
---

# เรนเดอร์ไฟล์ข้อความ (.txt)

## การแนะนำ
ในขอบเขตของการจัดการและจัดการเอกสาร GroupDocs.Viewer สำหรับ .NET กลายเป็นเครื่องมืออันทรงพลัง โดยมีฟังก์ชันการทำงานมากมายเหลือเฟือในการแสดงรูปแบบเอกสารต่างๆ ได้อย่างมีประสิทธิภาพ บทความนี้เจาะลึกความซับซ้อนของการใช้ GroupDocs.Viewer สำหรับ .NET เพื่อแสดงไฟล์ข้อความ (.txt) ในหลายรูปแบบ ไม่ว่าคุณจะตั้งเป้าที่จะแปลงไฟล์ข้อความเป็น HTML, JPG, PNG หรือ PDF, GroupDocs.Viewer ก็มีเครื่องมือที่จำเป็นเพื่อทำงานเหล่านี้ให้สำเร็จได้อย่างราบรื่น
## ข้อกำหนดเบื้องต้น
ก่อนที่จะเจาะลึกกระบวนการแปลง ตรวจสอบให้แน่ใจว่าคุณมีข้อกำหนดเบื้องต้นต่อไปนี้:
### 1. การติดตั้ง GroupDocs.Viewer สำหรับ .NET
 ตรวจสอบให้แน่ใจว่าคุณได้ติดตั้ง GroupDocs.Viewer สำหรับ .NET ในสภาพแวดล้อมการพัฒนาของคุณ คุณสามารถดาวน์โหลดไฟล์ที่จำเป็นได้จาก[เว็บไซต์](https://releases.groupdocs.com/viewer/net/).
### 2. ความคุ้นเคยขั้นพื้นฐานกับ .NET Framework
ทำความคุ้นเคยกับพื้นฐานของ .NET Framework รวมถึงวิธีตั้งค่าโปรเจ็กต์และใช้ไลบรารีภายในโค้ดเบสของคุณ
### 3. ไฟล์ข้อความตัวอย่าง
เตรียมไฟล์ข้อความตัวอย่าง (.txt) ที่คุณต้องการแปลง ไฟล์เหล่านี้จะทำหน้าที่เป็นอินพุตสำหรับกระบวนการแปลง

## นำเข้าเนมสเปซ
ก่อนที่จะเข้าสู่กระบวนการแปลง ตรวจสอบให้แน่ใจว่าได้นำเข้าเนมสเปซที่จำเป็นลงในโปรเจ็กต์ของคุณ ซึ่งช่วยให้คุณเข้าถึงฟังก์ชันการทำงานที่ GroupDocs.Viewer สำหรับ .NET มอบให้ได้อย่างราบรื่น
```csharp
using System;
using System.Collections.Generic;
using System.Text;
using System.IO;
using GroupDocs.Viewer.Options;
string outputDirectory = "Your Document Directory";
```
เราจะแบ่งแต่ละตัวอย่างออกเป็นหลายขั้นตอนเพื่อแนะนำคุณตลอดกระบวนการแปลงอย่างมีประสิทธิภาพ:

## ขั้นตอนที่ 1: กำหนดเส้นทางเอาต์พุต HTML
```csharp
string pageFileFullPath = Path.Combine(outputDirectory, "Txt_result.html");
```
ระบุเส้นทางแบบเต็มสำหรับไฟล์เอาต์พุต HTML
## ขั้นตอนที่ 2: เรนเดอร์ไฟล์ข้อความเป็น HTML หลายหน้า
```csharp
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_TXT))
{
    HtmlViewOptions options = HtmlViewOptions.ForEmbeddedResources(pageFileFullPath);
    viewer.View(options);
}
```
 ยกตัวอย่าง`Viewer` วัตถุที่มีเส้นทางไปยังไฟล์ข้อความ กำหนดค่า`HtmlViewOptions` สำหรับทรัพยากรที่ฝังอยู่และแสดงไฟล์ข้อความเป็น HTML หลายหน้า
## ขั้นตอนที่ 3: กำหนดเส้นทางเอาต์พุต HTML หน้าเดียว
```csharp
pageFileFullPath = Path.Combine(outputDirectory, "Txt_result_single_page.html");
```
ระบุเส้นทางแบบเต็มสำหรับไฟล์เอาต์พุต HTML หน้าเดียว
## ขั้นตอนที่ 4: เรนเดอร์ไฟล์ข้อความเป็น HTML หน้าเดียว
```csharp
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_2_TXT))
{
    HtmlViewOptions options = HtmlViewOptions.ForEmbeddedResources(pageFileFullPath);
    options.RenderToSinglePage = true;
    viewer.View(options);
}
```
 ยกตัวอย่าง`Viewer` วัตถุที่มีเส้นทางไปยังไฟล์ข้อความ กำหนดค่า`HtmlViewOptions` สำหรับทรัพยากรที่ฝังตัวและการตั้งค่า`RenderToSinglePage` เป็นจริง แสดงไฟล์ข้อความเป็น HTML หน้าเดียว
## ขั้นตอนที่ 5: กำหนดเส้นทางเอาต์พุต JPG
```csharp
pageFileFullPath = Path.Combine(outputDirectory, "Txt_result.jpg");
```
ระบุเส้นทางแบบเต็มสำหรับไฟล์เอาต์พุต JPG
## ขั้นตอนที่ 6: เรนเดอร์ไฟล์ข้อความเป็น JPG
```csharp
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_TXT))
{
    JpgViewOptions options = new JpgViewOptions(pageFileFullPath);
    viewer.View(options);
}
```
 ยกตัวอย่าง`Viewer` วัตถุที่มีเส้นทางไปยังไฟล์ข้อความ กำหนดค่า`JpgViewOptions` สำหรับเส้นทางเอาต์พุตและแสดงไฟล์ข้อความเป็นรูปแบบ JPG
## ขั้นตอนที่ 7: กำหนดเส้นทางเอาต์พุต PNG
```csharp
pageFileFullPath = Path.Combine(outputDirectory, "Txt_result.png");
```
ระบุเส้นทางแบบเต็มสำหรับไฟล์เอาต์พุต PNG
## ขั้นตอนที่ 8: เรนเดอร์ไฟล์ข้อความเป็น PNG
```csharp
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_TXT))
{
    PngViewOptions options = new PngViewOptions(pageFileFullPath);
    viewer.View(options);
}
```
 ยกตัวอย่าง`Viewer` วัตถุที่มีเส้นทางไปยังไฟล์ข้อความ กำหนดค่า`PngViewOptions` สำหรับเส้นทางเอาต์พุตและแสดงไฟล์ข้อความเป็นรูปแบบ PNG
## ขั้นตอนที่ 9: กำหนดเส้นทางเอาต์พุต PDF
```csharp
pageFileFullPath = Path.Combine(outputDirectory, "Txt_result.pdf");
```
ระบุเส้นทางแบบเต็มสำหรับไฟล์เอาต์พุต PDF
## ขั้นตอนที่ 10: เรนเดอร์ไฟล์ข้อความเป็น PDF
```csharp
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_TXT))
{
    PdfViewOptions options = new PdfViewOptions(pageFileFullPath);
    viewer.View(options);
}
```
 ยกตัวอย่าง`Viewer` วัตถุที่มีเส้นทางไปยังไฟล์ข้อความ กำหนดค่า`PdfViewOptions` สำหรับเส้นทางเอาต์พุตและแสดงไฟล์ข้อความเป็นรูปแบบ PDF

## บทสรุป
โดยสรุป GroupDocs.Viewer สำหรับ .NET ช่วยให้นักพัฒนาสามารถเรนเดอร์ไฟล์ข้อความเป็นรูปแบบต่างๆ ได้อย่างง่ายดาย รวมถึง HTML, JPG, PNG และ PDF เมื่อปฏิบัติตามคำแนะนำทีละขั้นตอนที่สรุปไว้ในบทความนี้ คุณจะสามารถรวม GroupDocs.Viewer เข้ากับแอปพลิเคชัน .NET ของคุณได้อย่างราบรื่น ซึ่งช่วยเพิ่มความสามารถในการจัดการเอกสาร
## คำถามที่พบบ่อย
### ถาม: GroupDocs.Viewer สำหรับ .NET เข้ากันได้กับเฟรมเวิร์ก .NET ทุกเวอร์ชันหรือไม่
ใช่ GroupDocs.Viewer สำหรับ .NET ได้รับการออกแบบมาให้เข้ากันได้กับเวอร์ชันเฟรมเวิร์ก .NET ที่หลากหลาย ทำให้มั่นใจได้ถึงความคล่องตัวและความยืดหยุ่นในการพัฒนา
### ถาม: ฉันสามารถปรับแต่งลักษณะเอาต์พุตของเอกสารที่เรนเดอร์ได้หรือไม่
อย่างแน่นอน! GroupDocs.Viewer นำเสนอตัวเลือกการปรับแต่งที่หลากหลาย ช่วยให้นักพัฒนาสามารถปรับแต่งรูปลักษณ์ของเอกสารที่เรนเดอร์ได้ตามความต้องการและความต้องการของพวกเขา
### ถาม: GroupDocs.Viewer สำหรับ .NET มีเวอร์ชันทดลองใช้งานหรือไม่
 ใช่ คุณสามารถสำรวจฟังก์ชันการทำงานของ GroupDocs.Viewer สำหรับ .NET ได้โดยการเข้าถึงรุ่นทดลองใช้ฟรีที่[เว็บไซต์]( https://releases.groupdocs.com/).
### ถาม: ฉันจะรับการสนับสนุนหรือขอความช่วยเหลือเกี่ยวกับ GroupDocs.Viewer สำหรับ .NET ได้อย่างไร
 หากมีข้อสงสัย การสนับสนุน หรือความช่วยเหลือเกี่ยวกับ GroupDocs.Viewer สำหรับ .NET คุณสามารถไปที่ฟอรัมการสนับสนุนเฉพาะที่สามารถเข้าถึงได้[ที่นี่](https://forum.groupdocs.com/c/viewer/9).
### ถาม: ฉันสามารถซื้อใบอนุญาตชั่วคราวสำหรับ GroupDocs.Viewer สำหรับ .NET ได้หรือไม่
ใช่ ใบอนุญาตชั่วคราวพร้อมให้ซื้อได้ โดยให้ความยืดหยุ่นและความสะดวกสบายแก่ผู้ใช้ในการใช้ GroupDocs.Viewer สำหรับ .NET ตามระยะเวลาที่กำหนด