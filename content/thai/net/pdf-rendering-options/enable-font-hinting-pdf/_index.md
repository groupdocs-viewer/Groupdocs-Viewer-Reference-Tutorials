---
title: เปิดใช้งานคำแนะนำแบบอักษรในรูปแบบ PDF
linktitle: เปิดใช้งานคำแนะนำแบบอักษรในรูปแบบ PDF
second_title: GroupDocs.Viewer .NET API
description: เรียนรู้วิธีเปิดใช้งานการบอกใบ้แบบอักษรในเอกสาร PDF โดยใช้ GroupDocs.Viewer สำหรับ .NET ปฏิบัติตามบทช่วยสอนทีละขั้นตอนของเราเพื่อการบูรณาการที่ราบรื่น
weight: 14
url: /th/net/pdf-rendering-options/enable-font-hinting-pdf/
---

# เปิดใช้งานคำแนะนำแบบอักษรในรูปแบบ PDF

## การแนะนำ
GroupDocs.Viewer สำหรับ .NET เป็นเครื่องมืออันทรงพลังสำหรับการดูและจัดการรูปแบบเอกสารต่างๆ ภายในแอปพลิเคชัน .NET ไม่ว่าคุณจะทำงานกับ PDF, เอกสาร Microsoft Office, รูปภาพ หรือรูปแบบอื่นๆ GroupDocs.Viewer มอบโซลูชันที่ราบรื่นสำหรับการเรนเดอร์และโต้ตอบกับไฟล์เหล่านี้
## ข้อกำหนดเบื้องต้น
ก่อนที่จะเริ่มใช้ GroupDocs.Viewer สำหรับ .NET ตรวจสอบให้แน่ใจว่าคุณมีสิ่งต่อไปนี้:
1. ความเข้าใจพื้นฐานของ .NET: ทำความคุ้นเคยกับพื้นฐานของ .NET Framework และภาษาการเขียนโปรแกรม C#
2.  การติดตั้ง GroupDocs.Viewer สำหรับ .NET: ดาวน์โหลดและติดตั้งไลบรารี GroupDocs.Viewer สำหรับ .NET คุณสามารถค้นหาลิงค์ดาวน์โหลด[ที่นี่](https://releases.groupdocs.com/viewer/net/).
3. สภาพแวดล้อมการพัฒนา: มีสภาพแวดล้อมการพัฒนาที่ตั้งค่าด้วย Visual Studio หรือ IDE อื่น ๆ ที่เข้ากันได้
4. เอกสารตัวอย่าง: รวบรวมเอกสารตัวอย่างที่คุณจะใช้งานในระหว่างกระบวนการพัฒนา

## นำเข้าเนมสเปซ
ในโปรเจ็กต์ .NET ของคุณ ให้นำเข้าเนมสเปซที่จำเป็นเพื่อใช้ฟังก์ชัน GroupDocs.Viewer

```csharp
using System;
using System.IO;
using GroupDocs.Viewer.Options;
```
## ขั้นตอนที่ 1: ตั้งค่าไดเรกทอรีผลลัพธ์
```csharp
string outputDirectory = "Your Document Directory";
```
ตั้งค่าไดเร็กทอรีที่คุณต้องการให้เพจที่แสดงผลถูกบันทึก
## ขั้นตอนที่ 2: กำหนดรูปแบบเส้นทางไฟล์เพจ
```csharp
string pageFilePathFormat = Path.Combine(outputDirectory, "page_{0}.png");
```
 กำหนดรูปแบบสำหรับการตั้งชื่อไฟล์เพจที่แสดงผล ในตัวอย่างนี้ หน้าต่างๆ จะถูกบันทึกเป็นรูปภาพ PNG โดยมีรูปแบบชื่อไฟล์เป็น`page_1.png`, `page_2.png`และอื่นๆ
## ขั้นตอนที่ 3: เริ่มต้นวัตถุ Viewer
```csharp
using (Viewer viewer = new Viewer(TestFiles.HIEROGLYPHS_1_PDF))
```
เริ่มต้นออบเจ็กต์ Viewer โดยระบุเส้นทางไปยังเอกสาร PDF ที่คุณต้องการแสดงผล
## ขั้นตอนที่ 4: ตั้งค่าตัวเลือกการแสดงผล
```csharp
PngViewOptions options = new PngViewOptions(pageFilePathFormat);
options.PdfOptions.EnableFontHinting = true;
```
สร้างตัวเลือกการเรนเดอร์สำหรับรูปแบบ PNG และเปิดใช้งานการบอกใบ้แบบอักษรในตัวเลือก PDF
## ขั้นตอนที่ 5: แสดงผลเอกสาร
```csharp
viewer.View(options, 1);
```
แสดงผลเอกสารโดยใช้ตัวเลือกที่ระบุ ในตัวอย่างนี้ การแสดงผลเริ่มต้นจากหน้าแรก
## ขั้นตอนที่ 6: แสดงข้อความแสดงความสำเร็จ
```csharp
Console.WriteLine($"\nSource document rendered successfully.\nCheck output in {outputDirectory}.");
```
แสดงข้อความแจ้งว่าเอกสารแสดงผลสำเร็จแล้ว และระบุไดเร็กทอรีเอาต์พุตที่บันทึกเพจที่แสดงผล

## บทสรุป
โดยสรุป GroupDocs.Viewer สำหรับ .NET นำเสนอโซลูชันที่ครอบคลุมสำหรับการดูและจัดการรูปแบบเอกสารต่างๆ ภายในแอปพลิเคชัน .NET คุณสามารถรวมความสามารถในการดูเอกสารเข้ากับโครงการ .NET ของคุณได้โดยปฏิบัติตามบทช่วยสอนที่ให้ไว้และใช้ฟังก์ชันต่างๆ ของโปรแกรม
## คำถามที่พบบ่อย
### GroupDocs.Viewer สำหรับ .NET เข้ากันได้กับกรอบงาน .NET ทั้งหมดหรือไม่
GroupDocs.Viewer สำหรับ .NET รองรับ .NET Framework หลายเวอร์ชัน รวมถึง .NET Core และ .NET Framework
### ฉันสามารถปรับแต่งตัวเลือกการเรนเดอร์สำหรับรูปแบบเอกสารต่างๆ ได้หรือไม่
ใช่ GroupDocs.Viewer สำหรับ .NET มีตัวเลือกมากมายสำหรับปรับแต่งการตั้งค่าการเรนเดอร์ตามความต้องการของคุณ
### มีรุ่นทดลองใช้สำหรับ GroupDocs.Viewer สำหรับ .NET หรือไม่
 ใช่ คุณสามารถเข้าถึง GroupDocs.Viewer สำหรับ .NET เวอร์ชันทดลองใช้ฟรีได้[ที่นี่](https://releases.groupdocs.com/).
### ฉันจะรับการสนับสนุนสำหรับ GroupDocs.Viewer สำหรับ .NET ได้อย่างไร
 คุณสามารถรับการสนับสนุนและความช่วยเหลือได้จากฟอรัมชุมชน GroupDocs.Viewer[ที่นี่](https://forum.groupdocs.com/c/viewer/9).
### มีใบอนุญาตชั่วคราวสำหรับ GroupDocs.Viewer สำหรับ .NET หรือไม่
 ได้ คุณสามารถขอรับใบอนุญาตชั่วคราวสำหรับ GroupDocs.Viewer สำหรับ .NET ได้[ที่นี่](https://purchase.groupdocs.com/temporary-license/).