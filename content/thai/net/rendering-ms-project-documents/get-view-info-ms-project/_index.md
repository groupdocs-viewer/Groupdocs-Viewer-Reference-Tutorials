---
title: รับข้อมูลมุมมองสำหรับเอกสารโครงการ Microsoft
linktitle: รับข้อมูลมุมมองสำหรับเอกสารโครงการ Microsoft
second_title: GroupDocs.Viewer .NET API
description: สำรวจบทช่วยสอนที่ครอบคลุมเกี่ยวกับการใช้ประโยชน์จาก Groupdocs.Viewer สำหรับ .NET เพื่อดึงข้อมูลการดูสำหรับเอกสาร Microsoft Project ได้อย่างง่ายดาย
weight: 10
url: /th/net/rendering-ms-project-documents/get-view-info-ms-project/
---

# รับข้อมูลมุมมองสำหรับเอกสารโครงการ Microsoft

## การแนะนำ
ในขอบเขตของโซลูชันการจัดการและการดูเอกสาร Groupdocs.Viewer สำหรับ .NET มีความโดดเด่นในฐานะเครื่องมืออเนกประสงค์และทนทาน ไม่ว่าคุณจะเป็นนักพัฒนาที่ต้องการรวมความสามารถในการดูเอกสารเข้ากับแอปพลิเคชัน .NET ของคุณ หรือผู้ที่กระตือรือร้นที่จะสำรวจฟังก์ชันต่างๆ ของแอปพลิเคชัน บทช่วยสอนนี้จะแนะนำคุณตลอดกระบวนการใช้ประโยชน์จาก Groupdocs.Viewer สำหรับ .NET เพื่อดึงข้อมูลการดูสำหรับเอกสาร Microsoft Project .
## ข้อกำหนดเบื้องต้น
ก่อนที่จะเข้าสู่บทช่วยสอน ตรวจสอบให้แน่ใจว่าคุณมีข้อกำหนดเบื้องต้นต่อไปนี้:
1. ความเข้าใจพื้นฐานของ .NET Framework: ความคุ้นเคยกับ .NET Framework จะช่วยให้เข้าใจกระบวนการบูรณาการได้
2.  การติดตั้ง Groupdocs.Viewer สำหรับ .NET: ดาวน์โหลดและติดตั้ง Groupdocs.Viewer สำหรับ .NET จาก[เว็บไซต์](https://releases.groupdocs.com/viewer/net/).
3. การตั้งค่าสภาพแวดล้อมการพัฒนา: มีสภาพแวดล้อมการพัฒนาที่กำหนดค่าด้วยเครื่องมือที่จำเป็น เช่น Visual Studio สำหรับการเขียนโค้ด

## การนำเข้าเนมสเปซที่จำเป็น
ในการเริ่มต้น ให้นำเข้าเนมสเปซที่จำเป็นลงในโปรเจ็กต์ .NET ของคุณ เนมสเปซเหล่านี้อำนวยความสะดวกในการสื่อสารกับ Groupdocs.Viewer สำหรับฟังก์ชัน .NET

```csharp
using System;
using GroupDocs.Viewer.Options;
using GroupDocs.Viewer.Results;
```

Groupdocs.Viewer สำหรับ .NET มอบวิธีที่ใช้งานง่ายในการดึงข้อมูลมุมมองสำหรับเอกสาร Microsoft Project ทำตามขั้นตอนเหล่านี้อย่างพิถีพิถันเพื่อให้บรรลุเป้าหมายนี้:
## ขั้นตอนที่ 1: เริ่มต้นวัตถุ Viewer
```csharp
using (Viewer viewer = new Viewer("path/to/your/MicrosoftProjectDocument.mpp"))
{
    // รหัสยังคงดำเนินต่อไป...
}
```
 ในขั้นตอนนี้ ให้เปลี่ยน`"path/to/your/MicrosoftProjectDocument.mpp"` ด้วยเส้นทางจริงไปยังเอกสาร Microsoft Project ของคุณ
## ขั้นตอนที่ 2: ดึงข้อมูลมุมมอง
```csharp
ProjectManagementViewInfo info = viewer.GetViewInfo(
    ViewInfoOptions.ForHtmlView()) as ProjectManagementViewInfo;
```
 ที่นี่เราใช้`GetViewInfo()` วิธีการดึงข้อมูลมุมมองสำหรับเอกสาร Microsoft Project ที่ระบุ เราระบุ`ViewInfoOptions.ForHtmlView()` เพื่อรับข้อมูลมุมมองสำหรับมุมมอง HTML
## ขั้นตอนที่ 3: แสดงข้อมูลมุมมอง
```csharp
Console.WriteLine("Document type is: " + info.FileType);
Console.WriteLine("Pages count: " + info.Pages.Count);
Console.WriteLine("Project start date: {0}", info.StartDate);
Console.WriteLine("Project end date: {0}", info.EndDate);
```
ขั้นตอนนี้เกี่ยวข้องกับการแสดงข้อมูลมุมมองที่ดึงมา รวมถึงประเภทเอกสาร จำนวนหน้า วันที่เริ่มต้นโครงการ และวันที่สิ้นสุดโครงการ
## ขั้นตอนที่ 4: บทสรุป
```csharp
Console.WriteLine("\nView info retrieved successfully.");
```
สุดท้าย เราจะสรุปกระบวนการโดยแสดงข้อความแสดงความสำเร็จที่ระบุว่าข้อมูลมุมมองได้รับการดึงข้อมูลสำเร็จแล้ว

## บทสรุป
ในบทช่วยสอนนี้ เราได้สำรวจวิธีการใช้ Groupdocs.Viewer สำหรับ .NET เพื่อดึงข้อมูลการดูสำหรับเอกสาร Microsoft Project ด้วยการทำตามขั้นตอนที่ระบุไว้ คุณสามารถรวมฟังก์ชันการทำงานนี้เข้ากับแอปพลิเคชัน .NET ของคุณได้อย่างราบรื่น ซึ่งช่วยเพิ่มความสามารถในการจัดการเอกสาร
## คำถามที่พบบ่อย

### Groupdocs.Viewer สำหรับ .NET เข้ากันได้กับ .NET Framework ทุกเวอร์ชันหรือไม่

ใช่ Groupdocs.Viewer สำหรับ .NET เข้ากันได้กับเวอร์ชันต่างๆ ของเฟรมเวิร์ก .NET ซึ่งให้ความยืดหยุ่นสำหรับนักพัฒนา

### ฉันสามารถปรับแต่งกระบวนการดึงข้อมูลมุมมองตามความต้องการของแอปพลิเคชันของฉันได้หรือไม่

แน่นอน! Groupdocs.Viewer สำหรับ .NET นำเสนอตัวเลือกการปรับแต่งที่ครอบคลุมเพื่อปรับแต่งกระบวนการดึงข้อมูลให้ตรงกับความต้องการเฉพาะของคุณ

### Groupdocs.Viewer for .NET รองรับรูปแบบเอกสารอื่นๆ นอกเหนือจากเอกสาร Microsoft Project หรือไม่

อย่างแน่นอน. Groupdocs.Viewer สำหรับ .NET รองรับรูปแบบเอกสารที่หลากหลาย ทำให้มั่นใจได้ถึงความคล่องตัวในความสามารถในการดูเอกสาร

### มีฟอรัมชุมชนหรือแพลตฟอร์มสนับสนุนที่ฉันสามารถขอความช่วยเหลือจาก Groupdocs.Viewer สำหรับ .NET ได้หรือไม่

 ใช่คุณสามารถเยี่ยมชม[ฟอรัม Groupdocs.Viewer](https://forum.groupdocs.com/c/viewer/9) สำหรับการสนับสนุนและคำแนะนำจากชุมชน

### ฉันสามารถสำรวจฟังก์ชันการทำงานของ Groupdocs.Viewer สำหรับ .NET ก่อนซื้อได้หรือไม่

 แน่นอน! คุณสามารถทดลองใช้ฟรีได้จาก[เว็บไซต์](https://releases.groupdocs.com/) เพื่อสำรวจคุณสมบัติและความสามารถของ Groupdocs.Viewer สำหรับ .NET