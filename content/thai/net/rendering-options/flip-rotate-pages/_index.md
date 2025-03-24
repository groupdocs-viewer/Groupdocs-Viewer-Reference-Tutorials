---
title: พลิกและหมุนหน้า
linktitle: พลิกและหมุนหน้า
second_title: GroupDocs.Viewer .NET API
description: เรียนรู้วิธีผสานรวม Groupdocs.Viewer สำหรับ .NET เข้ากับแอปพลิเคชันของคุณเพื่อการแสดงภาพ การพลิก และการหมุนเอกสารที่ราบรื่น
weight: 12
url: /th/net/rendering-options/flip-rotate-pages/
---
## การแนะนำ
ในบทช่วยสอนนี้ เราจะเจาะลึกฟังก์ชันการทำงานของ Groupdocs.Viewer สำหรับ .NET โดยเน้นไปที่การพลิกและหมุนหน้าโดยเฉพาะ Groupdocs.Viewer สำหรับ .NET เป็นเครื่องมืออันทรงพลังที่ออกแบบมาเพื่อแสดงเอกสารในรูปแบบต่างๆ ภายในแอปพลิเคชัน .NET ไม่ว่าคุณกำลังพัฒนาระบบการจัดการเอกสารหรือต้องการรวมความสามารถในการดูเอกสารเข้ากับซอฟต์แวร์ของคุณ Groupdocs.Viewer for .NET มอบโซลูชันที่มีประสิทธิภาพ
## ข้อกำหนดเบื้องต้น
ก่อนที่เราจะเริ่มต้น ตรวจสอบให้แน่ใจว่าคุณได้ตั้งค่าข้อกำหนดเบื้องต้นต่อไปนี้:
### การติดตั้ง Groupdocs.Viewer สำหรับ .NET
 หากต้องการใช้ Groupdocs.Viewer สำหรับ .NET คุณต้องติดตั้งแพ็คเกจผ่าน NuGet Package Manager คุณสามารถดูคำแนะนำการติดตั้งโดยละเอียดได้ใน[เอกสารประกอบ](https://tutorials.groupdocs.com/viewer/net/).

## นำเข้าเนมสเปซ
ตรวจสอบให้แน่ใจว่าคุณได้นำเข้าเนมสเปซที่จำเป็นในโปรเจ็กต์ของคุณเพื่อใช้ Groupdocs.Viewer สำหรับ .NET อย่างมีประสิทธิภาพ
```csharp
using System;
using System.IO;
using GroupDocs.Viewer.Options;
```

เรามาแจกแจงขั้นตอนการพลิกและหมุนหน้าโดยใช้ Groupdocs.Viewer สำหรับ .NET ให้เป็นขั้นตอนง่ายๆ:
## ขั้นตอนที่ 1: ตั้งค่า Output Directory และ File Path
กำหนดไดเร็กทอรีที่คุณต้องการให้ไฟล์เอาต์พุตถูกบันทึก และระบุพาธของไฟล์เอาต์พุต
```csharp
string outputDirectory = "Your Document Directory";
string outputFilePath = Path.Combine(outputDirectory, "output.pdf");
```
## ขั้นตอนที่ 2: เริ่มต้นวัตถุ Viewer
สร้างอินสแตนซ์ของคลาส Viewer โดยส่งเส้นทางไปยังเอกสารที่คุณต้องการดู
```csharp
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_DOCX))
```
## ขั้นตอนที่ 3: กำหนดค่าตัวเลือกมุมมอง
ตั้งค่าตัวเลือกมุมมอง เช่น การระบุรูปแบบไฟล์เอาต์พุต และการตั้งค่าเพิ่มเติมใดๆ เช่น การหมุนหน้า
```csharp
PdfViewOptions viewOptions = new PdfViewOptions(outputFilePath);
viewOptions.RotatePage(1, Rotation.On90Degree);
```
## ขั้นตอนที่ 4: แสดงผลเอกสาร
เรียกใช้วิธีการ View ของวัตถุ Viewer และส่งผ่านตัวเลือกมุมมอง
```csharp
viewer.View(viewOptions);
```
## ขั้นตอนที่ 5: แสดงข้อความแสดงความสำเร็จ
แจ้งให้ผู้ใช้ทราบว่าเอกสารแสดงผลสำเร็จแล้ว และระบุไดเร็กทอรีเอาต์พุตสำหรับการตรวจสอบ
```csharp
Console.WriteLine($"\nSource document rendered successfully.\nCheck output in {outputDirectory}.");
```

## บทสรุป
โดยสรุป Groupdocs.Viewer สำหรับ .NET นำเสนอความสามารถอันทรงพลังสำหรับการเรนเดอร์เอกสาร รวมถึงการพลิกและหมุนหน้า ด้วยการทำตามขั้นตอนที่ระบุไว้ในบทช่วยสอนนี้ คุณสามารถรวมคุณสมบัติเหล่านี้เข้ากับแอปพลิเคชัน .NET ของคุณได้อย่างราบรื่น ซึ่งจะช่วยปรับปรุงประสบการณ์การดูเอกสารสำหรับผู้ใช้ของคุณ
## คำถามที่พบบ่อย
### Groupdocs.Viewer สำหรับ .NET เข้ากันได้กับรูปแบบเอกสารทั้งหมดหรือไม่
ใช่ Groupdocs.Viewer สำหรับ .NET รองรับรูปแบบเอกสารที่หลากหลาย รวมถึง DOCX, PDF, PPTX และอื่นๆ
### ฉันสามารถปรับแต่งตัวเลือกการดูนอกเหนือจากการพลิกและหมุนหน้าได้หรือไม่
แน่นอนว่า Groupdocs.Viewer สำหรับ .NET มีตัวเลือกการปรับแต่งที่หลากหลายสำหรับการดูเอกสาร ซึ่งช่วยให้คุณปรับแต่งประสบการณ์ได้ตามความต้องการของคุณ
### Groupdocs.Viewer สำหรับ .NET มีรุ่นทดลองใช้ฟรีหรือไม่
 ใช่ คุณสามารถทดลองใช้ Groupdocs.Viewer สำหรับ .NET ได้ฟรีโดยไปที่[เว็บไซต์](https://releases.groupdocs.com/).
### ฉันจะรับการสนับสนุน Groupdocs.Viewer สำหรับ .NET ได้อย่างไร
 คุณสามารถขอความช่วยเหลือและมีส่วนร่วมกับชุมชนผ่านทาง[ฟอรัม Groupdocs.Viewer](https://forum.groupdocs.com/c/viewer/9).
### ฉันจะขอรับใบอนุญาตชั่วคราวสำหรับ Groupdocs.Viewer สำหรับ .NET ได้ที่ไหน
 สามารถรับใบอนุญาตชั่วคราวสำหรับ Groupdocs.Viewer สำหรับ .NET ได้จาก[หน้าซื้อ](https://purchase.groupdocs.com/temporary-license/).