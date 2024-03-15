---
title: ปรับขนาดหน้าเมื่อแสดงข้อความอีเมล
linktitle: ปรับขนาดหน้าเมื่อแสดงข้อความอีเมล
second_title: GroupDocs.Viewer .NET API
description: เรียนรู้วิธีปรับขนาดหน้าเมื่อแสดงข้อความอีเมลเป็น PDF โดยใช้ GroupDocs.Viewer สำหรับ .NET เพิ่มประสิทธิภาพในการดูเอกสาร
type: docs
weight: 10
url: /th/net/rendering-email-messages/adjust-page-size-email/
---
## การแนะนำ
ในด้านการพัฒนา .NET นั้น GroupDocs.Viewer มอบโซลูชันที่ครอบคลุมสำหรับการเรนเดอร์เอกสารรูปแบบต่างๆ รวมถึงข้อความอีเมล บทช่วยสอนนี้เน้นที่การปรับขนาดหน้าเมื่อแสดงข้อความอีเมลเป็นรูปแบบ PDF โดยใช้ GroupDocs.Viewer สำหรับ .NET ด้วยการทำตามขั้นตอนที่ระบุไว้ในคู่มือนี้ คุณจะได้เรียนรู้วิธีจัดการขนาดหน้าได้อย่างราบรื่นเพื่อให้ตรงตามความต้องการเฉพาะของคุณ
## ข้อกำหนดเบื้องต้น
ก่อนที่จะเข้าสู่บทช่วยสอนนี้ ตรวจสอบให้แน่ใจว่าคุณมีข้อกำหนดเบื้องต้นต่อไปนี้:
### 1. ติดตั้ง GroupDocs.Viewer สำหรับ .NET แล้ว
 ตรวจสอบให้แน่ใจว่าคุณได้ติดตั้ง GroupDocs.Viewer สำหรับ .NET ในสภาพแวดล้อมการพัฒนาของคุณ คุณสามารถดาวน์โหลดได้จาก[ที่นี่](https://releases.groupdocs.com/viewer/net/).
### 2. ความเข้าใจพื้นฐานเกี่ยวกับการพัฒนา .NET
ทำความคุ้นเคยกับพื้นฐานการพัฒนา .NET รวมถึงการเขียนโปรแกรม C# และการจัดการไฟล์
### 3. IDE (สภาพแวดล้อมการพัฒนาแบบรวม)
ติดตั้ง IDE เช่น Visual Studio เพื่อเขียนและรันโค้ด .NET

## นำเข้าเนมสเปซ
ในโปรเจ็กต์ C# ของคุณ ให้นำเข้าเนมสเปซที่จำเป็นเพื่อใช้ฟังก์ชัน GroupDocs.Viewer

```csharp
using System;
using System.IO;
using GroupDocs.Viewer.Options;
```

## ขั้นตอนที่ 1: ตั้งค่าไดเรกทอรีผลลัพธ์
กำหนดไดเร็กทอรีที่จะบันทึกไฟล์ PDF เอาต์พุต
```csharp
string outputDirectory = "Your Document Directory";
```
## ขั้นตอนที่ 2: กำหนดเส้นทางไฟล์
รวมไดเร็กทอรีเอาต์พุตเข้ากับชื่อไฟล์เอาต์พุต
```csharp
string filePath = Path.Combine(outputDirectory, "output.pdf");
```
## ขั้นตอนที่ 3: เริ่มต้นวัตถุ Viewer
สร้างอินสแตนซ์ของคลาส Viewer และระบุเส้นทางไฟล์ข้อความอีเมล
```csharp
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_MSG))
```
## ขั้นตอนที่ 4: กำหนดค่าตัวเลือกมุมมอง PDF
สร้างอินสแตนซ์ PdfViewOptions และตั้งค่าเส้นทางไฟล์เอาต์พุต
```csharp
PdfViewOptions options = new PdfViewOptions(filePath);
```
## ขั้นตอนที่ 5: ปรับขนาดหน้า
แก้ไขคุณสมบัติขนาดหน้าใน EmailOptions ของ PdfViewOptions
```csharp
options.EmailOptions.PageSize = PageSize.A4;
```
## ขั้นตอนที่ 6: แสดงผลเอกสาร
เรียกใช้เมธอด View ของออบเจ็กต์วิวเวอร์ โดยส่ง PdfViewOptions ที่กำหนดค่าไว้
```csharp
viewer.View(options);
```
## ขั้นตอนที่ 7: แสดงข้อความแสดงความสำเร็จ
แจ้งให้ผู้ใช้ทราบเกี่ยวกับการเรนเดอร์ที่สำเร็จและไดเร็กทอรีเอาต์พุต
```csharp
Console.WriteLine($"\nSource document rendered successfully.\nCheck output in {outputDirectory}.");
```

## บทสรุป
โดยสรุป บทช่วยสอนนี้ได้สาธิตวิธีปรับขนาดหน้าเมื่อแสดงข้อความอีเมลเป็นรูปแบบ PDF โดยใช้ GroupDocs.Viewer สำหรับ .NET ด้วยการทำตามคำแนะนำทีละขั้นตอนเหล่านี้ คุณสามารถจัดการขนาดหน้าให้ตรงตามความต้องการเฉพาะของคุณได้อย่างมีประสิทธิภาพ เพิ่มความสามารถในการดูเอกสารและการจัดการภายในแอปพลิเคชัน .NET ของคุณ
## คำถามที่พบบ่อย
### GroupDocs.Viewer เข้ากันได้กับรูปแบบข้อความอีเมลที่แตกต่างกันหรือไม่
GroupDocs.Viewer รองรับการเรนเดอร์รูปแบบข้อความอีเมลที่หลากหลาย รวมถึง MSG และ EML
### ฉันสามารถปรับแต่งขนาดหน้าตามความต้องการของฉันได้หรือไม่?
ได้ คุณสามารถปรับขนาดหน้าได้โดยใช้ PdfViewOptions ของ GroupDocs.Viewer ซึ่งให้ความยืดหยุ่นในการแสดงเอกสาร
### GroupDocs.Viewer รองรับเอกสารรูปแบบอื่นหรือไม่
ใช่ GroupDocs.Viewer รองรับรูปแบบเอกสารที่หลากหลาย รวมถึง PDF, Microsoft Office, รูปภาพ และอื่นๆ
### GroupDocs.Viewer เหมาะสำหรับแอปพลิเคชันระดับองค์กรหรือไม่
GroupDocs.Viewer นำเสนอฟังก์ชันการทำงานที่มีประสิทธิภาพซึ่งเหมาะสำหรับแอปพลิเคชันทั้งขนาดเล็กและระดับองค์กร ทำให้มั่นใจได้ถึงการแสดงผลและการจัดการเอกสารที่มีประสิทธิภาพ
### ฉันจะขอความช่วยเหลือหรือการสนับสนุนเพิ่มเติมสำหรับ GroupDocs.Viewer ได้ที่ไหน
 คุณสามารถเยี่ยมชมฟอรัม GroupDocs.Viewer[ที่นี่](https://forum.groupdocs.com/c/viewer/9) เพื่อขอความช่วยเหลือ ถามคำถาม และมีส่วนร่วมกับชุมชน