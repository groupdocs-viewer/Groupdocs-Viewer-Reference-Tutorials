---
title: เพิ่มลายน้ำในเอกสาร
linktitle: เพิ่มลายน้ำในเอกสาร
second_title: GroupDocs.Viewer .NET API
description: เรียนรู้วิธีเพิ่มลายน้ำให้กับเอกสารได้อย่างราบรื่นโดยใช้ GroupDocs.Viewer สำหรับ .NET ปรับปรุงความปลอดภัยของเอกสารและการสร้างแบรนด์ด้วยบทช่วยสอนที่ปฏิบัติตามง่ายนี้
type: docs
weight: 10
url: /th/net/rendering-options/add-watermark/
---
## การแนะนำ
ในยุคดิจิทัลปัจจุบัน การจัดการและการดูเอกสารรูปแบบต่างๆ ได้อย่างราบรื่นเป็นสิ่งจำเป็นสำหรับธุรกิจและบุคคลจำนวนมาก โชคดีที่มีเครื่องมืออย่าง GroupDocs.Viewer สำหรับ .NET การจัดการเอกสารจึงกลายเป็นเรื่องง่าย ไลบรารี .NET อันทรงพลังนี้ช่วยให้นักพัฒนาสามารถรวมฟังก์ชันการดูเอกสารเข้ากับแอปพลิเคชันของตนได้อย่างง่ายดาย ทำให้ผู้ใช้สามารถดูเอกสารได้โดยไม่ต้องใช้ซอฟต์แวร์ต้นฉบับที่สร้างขึ้น
## ข้อกำหนดเบื้องต้น
ก่อนที่จะเริ่มใช้ GroupDocs.Viewer สำหรับ .NET เพื่อเพิ่มลายน้ำให้กับเอกสาร ตรวจสอบให้แน่ใจว่าคุณมีสิ่งต่อไปนี้:
1. การตั้งค่าสภาพแวดล้อม: มีการตั้งค่าสภาพแวดล้อมการพัฒนาด้วยการติดตั้ง .NET Framework หรือ .NET Core
2.  GroupDocs.Viewer for .NET: ดาวน์โหลดและติดตั้งไลบรารี GroupDocs.Viewer for .NET จาก[หน้าดาวน์โหลด](https://releases.groupdocs.com/viewer/net/).
3. ไฟล์เอกสาร: เตรียมไฟล์เอกสารที่คุณต้องการใช้งาน เช่น DOCX, PDF หรืออื่นๆ
4. ความรู้พื้นฐานของ C#: ความคุ้นเคยกับภาษาการเขียนโปรแกรม C# เป็นสิ่งจำเป็นในการนำตัวอย่างโค้ดไปใช้

## นำเข้าเนมสเปซ
ก่อนที่จะเริ่มเพิ่มลายน้ำให้กับเอกสารโดยใช้ GroupDocs.Viewer สำหรับ .NET ตรวจสอบให้แน่ใจว่าได้นำเข้าเนมสเปซที่จำเป็นในโค้ด C# ของคุณ ขั้นตอนนี้ช่วยให้คุณเข้าถึงคลาสและวิธีการต่างๆ ที่ห้องสมุดจัดเตรียมให้ได้อย่างราบรื่น

```csharp
using System;
using System.IO;
using GroupDocs.Viewer.Options;
```

ตอนนี้ มาดูขั้นตอนการเพิ่มลายน้ำให้กับเอกสารโดยใช้ GroupDocs.Viewer สำหรับ .NET กัน ทำตามขั้นตอนเหล่านี้เพื่อรวมฟังก์ชันลายน้ำเข้ากับแอปพลิเคชันของคุณได้อย่างราบรื่น
## ขั้นตอนที่ 1: ตั้งค่าไดเรกทอรีผลลัพธ์
```csharp
string outputDirectory = "Your Document Directory";
```
ระบุไดเร็กทอรีที่คุณต้องการให้ไฟล์เอาต์พุตถูกบันทึกหลังจากใช้ลายน้ำ
## ขั้นตอนที่ 2: กำหนดรูปแบบเส้นทางไฟล์เพจ
```csharp
string pageFilePathFormat = Path.Combine(outputDirectory, "page_{0}.html");
```
กำหนดรูปแบบสำหรับเส้นทางไฟล์ของหน้าที่แสดงผล ในตัวอย่างนี้ ไฟล์ HTML ที่มีหมายเลขหน้าจะถูกสร้างขึ้น
## ขั้นตอนที่ 3: สร้างอินสแตนซ์ของวัตถุ Viewer
```csharp
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_DOCX))
{
    // รหัสจะดำเนินต่อไปในขั้นตอนถัดไป...
}
```
สร้างอินสแตนซ์ของคลาส Viewer โดยส่งเส้นทางไปยังไฟล์เอกสารเป็นพารามิเตอร์ ในตัวอย่างนี้ เรากำลังใช้ไฟล์ DOCX ตัวอย่าง
## ขั้นตอนที่ 4: กำหนดค่าตัวเลือกมุมมอง HTML
```csharp
HtmlViewOptions options = HtmlViewOptions.ForEmbeddedResources(pageFilePathFormat);
options.Watermark = new Watermark("This is a watermark");
```
กำหนดค่าตัวเลือกมุมมอง HTML รวมถึงข้อความลายน้ำที่คุณต้องการเพิ่มลงในเอกสาร
## ขั้นตอนที่ 5: ดูเอกสารที่มีลายน้ำ
```csharp
viewer.View(options);
```
เรียกใช้เมธอด View ของวัตถุ Viewer โดยผ่านตัวเลือกที่กำหนดค่าไว้ นี่จะทำให้เอกสารมีลายน้ำที่ระบุ
## ขั้นตอนที่ 6: แสดงเส้นทางไดเรกทอรีผลลัพธ์
```csharp
Console.WriteLine($"\nSource document rendered successfully.\nCheck output in {outputDirectory}.");
```
แจ้งให้ผู้ใช้ทราบเกี่ยวกับการแสดงผลเอกสารที่สำเร็จ และระบุไดเร็กทอรีที่บันทึกไฟล์เอาต์พุต

## บทสรุป
GroupDocs.Viewer สำหรับ .NET มอบวิธีที่สะดวกในการเพิ่มลายน้ำให้กับเอกสารโดยทางโปรแกรม ด้วยการทำตามขั้นตอนที่ระบุไว้ในบทช่วยสอนนี้ คุณสามารถรวมฟังก์ชันลายน้ำเข้ากับแอปพลิเคชัน .NET ของคุณได้อย่างราบรื่น ซึ่งช่วยเพิ่มความปลอดภัยของเอกสารและการสร้างแบรนด์
## คำถามที่พบบ่อย
### ฉันสามารถปรับแต่งลักษณะของลายน้ำได้หรือไม่?
ใช่ คุณสามารถปรับแต่งคุณสมบัติต่างๆ ของลายน้ำได้ เช่น ข้อความ แบบอักษร สี ขนาด และตำแหน่ง
### GroupDocs.Viewer รองรับการดูเอกสารจากแหล่งระยะไกลหรือไม่
ใช่ GroupDocs.Viewer รองรับการดูเอกสารจากที่จัดเก็บในตัวเครื่องและ URL ระยะไกล
### มีรุ่นทดลองใช้สำหรับ GroupDocs.Viewer สำหรับ .NET หรือไม่
ใช่ คุณสามารถดาวน์โหลดเวอร์ชันทดลองใช้ฟรีได้จาก[ที่นี่](https://releases.groupdocs.com/).
### ฉันสามารถเพิ่มลายน้ำให้กับเอกสารหลายหน้าได้หรือไม่
GroupDocs.Viewer อนุญาตให้เพิ่มลายน้ำในแต่ละหน้าหรือทุกหน้าของเอกสารได้อย่างแน่นอน
### ฉันจะรับการสนับสนุนหรือความช่วยเหลือได้อย่างไรหากฉันประสบปัญหาใดๆ
 คุณสามารถขอความช่วยเหลือและการสนับสนุนจากฟอรัมชุมชน GroupDocs[ที่นี่](https://forum.groupdocs.com/c/viewer/9).