---
title: ปรับขนาดและคุณภาพของภาพ (JPG)
linktitle: ปรับขนาดและคุณภาพของภาพ (JPG)
second_title: GroupDocs.Viewer .NET API
description: เรียนรู้วิธีปรับขนาดและคุณภาพของภาพให้เหมาะสมในรูปแบบ JPEG โดยใช้ Groupdocs.Viewer สำหรับ .NET ยกระดับประสบการณ์การดูเอกสารของคุณ
weight: 11
url: /th/net/rendering-documents-images/adjust-image-size-and-quality-jpg/
---

# ปรับขนาดและคุณภาพของภาพ (JPG)

## การแนะนำ
Groupdocs.Viewer สำหรับ .NET เป็นไลบรารีที่มีประสิทธิภาพซึ่งช่วยให้นักพัฒนาสามารถรวมฟังก์ชันการดูเอกสารเข้ากับแอปพลิเคชัน .NET ของตนได้อย่างราบรื่น ข้อกำหนดทั่วไปอย่างหนึ่งในแอปพลิเคชันดูเอกสารคือความสามารถในการปรับขนาดและคุณภาพของภาพ โดยเฉพาะอย่างยิ่งเมื่อต้องจัดการกับภาพ JPEG (JPG) ในบทช่วยสอนนี้ เราจะแนะนำคุณตลอดขั้นตอนการปรับขนาดและคุณภาพของภาพโดยใช้ Groupdocs.Viewer สำหรับ .NET
## ข้อกำหนดเบื้องต้น
ก่อนที่เราจะเริ่ม ตรวจสอบให้แน่ใจว่าคุณมีสิ่งต่อไปนี้:
1. ความเข้าใจพื้นฐานเกี่ยวกับภาษาการเขียนโปรแกรม C#
2. ติดตั้ง Visual Studio บนระบบของคุณแล้ว
3.  ติดตั้ง Groupdocs.Viewer สำหรับไลบรารี .NET แล้ว คุณสามารถดาวน์โหลดได้จาก[ที่นี่](https://releases.groupdocs.com/viewer/net/).

## นำเข้าเนมสเปซ
ขั้นแรก คุณต้องนำเข้าเนมสเปซที่จำเป็นลงในโค้ด C# ของคุณ เนมสเปซเหล่านี้ให้สิทธิ์เข้าถึงคลาสและวิธีการที่จำเป็นสำหรับการทำงานกับ Groupdocs.Viewer
## ขั้นตอนที่ 1: นำเข้าเนมสเปซ
```csharp
using System;
using System.IO;
using GroupDocs.Viewer.Options;
```

ตอนนี้ เรามาแจกแจงโค้ดตัวอย่างที่ให้ไว้เป็นหลายขั้นตอนเพื่อความเข้าใจที่ดีขึ้น
## ขั้นตอนที่ 2: ตั้งค่าไดเร็กทอรีเอาต์พุตและรูปแบบเส้นทางไฟล์เพจ
```csharp
string outputDirectory = "Your Document Directory";
string pageFilePathFormat = Path.Combine(outputDirectory, "page_{0}.jpg");
```
ในขั้นตอนนี้ เราระบุไดเร็กทอรีเอาต์พุตที่จะบันทึกรูปภาพที่แสดงผล และกำหนดรูปแบบสำหรับเส้นทางไฟล์ของรูปภาพแต่ละหน้า
## ขั้นตอนที่ 3: เริ่มต้นโปรแกรมดูและกำหนดค่าตัวเลือกมุมมอง JPG
```csharp
using (Viewer viewer = new Viewer("Your Document Path"))
{
    JpgViewOptions options = new JpgViewOptions(pageFilePathFormat);
    options.Width = 600;
    options.Height = 800;
    viewer.View(options);
}
```
ที่นี่เราเริ่มต้นวัตถุ Viewer ด้วยเส้นทางไปยังเอกสารที่จะดู จากนั้น เราสร้างอินสแตนซ์ของ JpgViewOptions และตั้งค่าความกว้างและความสูงที่ต้องการสำหรับภาพ JPEG
## ขั้นตอนที่ 4: แสดงผลเอกสารต้นฉบับ
```csharp
Console.WriteLine($"\nSource document rendered successfully.\nCheck output in {outputDirectory}.");
```
สุดท้าย เราจะพิมพ์ข้อความที่ระบุถึงการเรนเดอร์เอกสารต้นฉบับและตำแหน่งที่บันทึกภาพที่ส่งออกได้สำเร็จ

## บทสรุป
ในบทช่วยสอนนี้ เราได้เรียนรู้วิธีปรับขนาดและคุณภาพของภาพ JPEG โดยใช้ Groupdocs.Viewer สำหรับ .NET ด้วยการทำตามขั้นตอนที่อธิบายไว้ข้างต้น คุณสามารถรวมฟังก์ชันนี้เข้ากับแอปพลิเคชัน .NET ของคุณได้อย่างง่ายดาย โดยมอบประสบการณ์การรับชมภาพที่ดีที่สุดแก่ผู้ใช้
## คำถามที่พบบ่อย
### ฉันสามารถปรับคุณภาพของภาพด้วยได้หรือไม่?
ได้ คุณสามารถปรับคุณภาพของภาพได้โดยการตั้งค่าคุณสมบัติคุณภาพใน JpgViewOptions
### Groupdocs.Viewer สำหรับ .NET รองรับรูปแบบเอกสารใดบ้าง
Groupdocs.Viewer สำหรับ .NET รองรับรูปแบบเอกสารที่หลากหลาย รวมถึง DOCX, PDF, PPTX, XLSX และอื่นๆ
### Groupdocs.Viewer สำหรับ .NET เข้ากันได้กับ .NET Core หรือไม่
ใช่ Groupdocs.Viewer สำหรับ .NET เข้ากันได้กับ .NET Core พร้อมกับ .NET Framework แบบดั้งเดิม
### ฉันสามารถปรับแต่งรูปแบบการตั้งชื่อไฟล์เอาต์พุตได้หรือไม่
ใช่ คุณสามารถปรับแต่งรูปแบบการตั้งชื่อไฟล์เอาต์พุตได้โดยการแก้ไขตัวแปร pageFilePathFormat ในโค้ด
### Groupdocs.Viewer สำหรับ .NET รองรับคำอธิบายประกอบเอกสารหรือไม่
ใช่ Groupdocs.Viewer สำหรับ .NET ให้การสนับสนุนที่ครอบคลุมสำหรับคำอธิบายประกอบเอกสาร รวมถึงการเน้นข้อความ การขีดเส้นใต้ และการแสดงความคิดเห็น