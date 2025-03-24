---
title: เรนเดอร์เค้าโครงเดี่ยวในแบบร่าง CAD
linktitle: เรนเดอร์เค้าโครงเดี่ยวในแบบร่าง CAD
second_title: GroupDocs.Viewer .NET API
description: เรียนรู้วิธีการแสดงผลเค้าโครงเดียวในแบบร่าง CAD โดยใช้ GroupDocs.Viewer สำหรับ .NET ขั้นตอนง่ายๆ สำหรับการบูรณาการอย่างราบรื่นในแอปพลิเคชัน .NET ของคุณ
weight: 14
url: /th/net/rendering-cad-drawings/render-single-layout-cad/
---

# เรนเดอร์เค้าโครงเดี่ยวในแบบร่าง CAD

## การแนะนำ
ในขอบเขตของการพัฒนา .NET การจัดการและการดูแบบ CAD ถือเป็นข้อกำหนดทั่วไป GroupDocs.Viewer สำหรับ .NET ช่วยให้งานนี้ง่ายขึ้นโดยมอบโซลูชันที่ครอบคลุมสำหรับการเรนเดอร์ภาพวาด CAD ภายในแอปพลิเคชัน .NET ในบทช่วยสอนนี้ เราจะเจาะลึกเกี่ยวกับการเรนเดอร์เค้าโครงเดี่ยวในแบบร่าง CAD โดยใช้ GroupDocs.Viewer สำหรับ .NET
## ข้อกำหนดเบื้องต้น
ก่อนที่จะเข้าสู่บทช่วยสอน ตรวจสอบให้แน่ใจว่าคุณมีข้อกำหนดเบื้องต้นต่อไปนี้:
- ความเข้าใจพื้นฐานเกี่ยวกับภาษาการเขียนโปรแกรม C# และ .NET Framework
- ติดตั้ง Visual Studio บนระบบของคุณแล้ว
-  ดาวน์โหลดและอ้างอิงไลบรารี GroupDocs.Viewer สำหรับ .NET ในโครงการของคุณ คุณสามารถดาวน์โหลดได้จาก[ที่นี่](https://releases.groupdocs.com/viewer/net/).
- ความคุ้นเคยกับรูปแบบไฟล์ CAD และโครงสร้าง

## นำเข้าเนมสเปซ
ขั้นแรก นำเข้าเนมสเปซที่จำเป็นลงในโค้ด C# ของคุณเพื่อเข้าถึงฟังก์ชัน GroupDocs.Viewer

```csharp
using System;
using System.IO;
using GroupDocs.Viewer.Options;
```

## ขั้นตอนที่ 1: กำหนดไดเรกทอรีผลลัพธ์
ระบุไดเร็กทอรีที่คุณต้องการบันทึกเอาต์พุตที่แสดงผล
```csharp
string outputDirectory = "Your Document Directory";
```
## ขั้นตอนที่ 2: กำหนดรูปแบบเส้นทางไฟล์เพจ
กำหนดรูปแบบสำหรับเส้นทางไฟล์ของแต่ละหน้าที่แสดงผล
```csharp
string pageFilePathFormat = Path.Combine(outputDirectory, "page_{0}.html");
```
## ขั้นตอนที่ 3: สร้างอินสแตนซ์ของวัตถุ Viewer
สร้างอินสแตนซ์ของคลาส Viewer ที่จัดทำโดย GroupDocs.Viewer
```csharp
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_DWG_WITH_LAYOUTS_AND_LAYERS))
```
## ขั้นตอนที่ 4: กำหนดค่าตัวเลือกมุมมอง HTML
กำหนดค่าตัวเลือกสำหรับการแสดงผลเอาต์พุต HTML ด้วยทรัพยากรที่ฝังอยู่
```csharp
HtmlViewOptions options = HtmlViewOptions.ForEmbeddedResources(pageFilePathFormat);
```
## ขั้นตอนที่ 5: ระบุชื่อเค้าโครง CAD
ระบุชื่อของเค้าโครง CAD ที่คุณต้องการแสดงผล
```csharp
options.CadOptions.LayoutName = "Model";
```
## ขั้นตอนที่ 6: เรนเดอร์ CAD Drawing
เรียกใช้วิธีการ View ของวัตถุ Viewer ด้วยตัวเลือกที่ระบุ
```csharp
viewer.View(options);
```
## ขั้นตอนที่ 7: แสดงข้อความแสดงความสำเร็จ
แจ้งให้ผู้ใช้ทราบเกี่ยวกับการแสดงผลเอกสารต้นฉบับได้สำเร็จ
```csharp
Console.WriteLine($"\nSource document rendered successfully.\nCheck output in {outputDirectory}.");
```

## บทสรุป
การเรนเดอร์ภาพวาด CAD โดยเฉพาะอย่างยิ่งเมื่อต้องจัดการกับเลย์เอาต์ อาจเป็นงานที่น่ากังวล อย่างไรก็ตาม ด้วย GroupDocs.Viewer สำหรับ .NET กระบวนการจะราบรื่นและมีประสิทธิภาพ ด้วยการทำตามขั้นตอนที่ระบุไว้ในบทช่วยสอนนี้ คุณสามารถเรนเดอร์เค้าโครงเดียวในแบบร่าง CAD ภายในแอปพลิเคชัน .NET ของคุณได้อย่างง่ายดาย
## คำถามที่พบบ่อย
### ฉันสามารถเรนเดอร์หลายเลย์เอาต์พร้อมกันโดยใช้ GroupDocs.Viewer สำหรับ .NET ได้หรือไม่
ใช่ GroupDocs.Viewer สำหรับ .NET รองรับการเรนเดอร์เค้าโครงหลายรูปแบบจากแบบร่าง CAD
### GroupDocs.Viewer เข้ากันได้กับไฟล์ CAD รูปแบบต่างๆ หรือไม่
GroupDocs.Viewer รองรับไฟล์ CAD ได้หลากหลายรูปแบบ รวมถึง DWG, DXF, DGN และอื่นๆ อีกมากมาย
### ฉันสามารถปรับแต่งตัวเลือกการเรนเดอร์สำหรับแบบร่าง CAD ได้หรือไม่
ใช่ GroupDocs.Viewer มีตัวเลือกมากมายในการปรับแต่งการตั้งค่าการเรนเดอร์ตามความต้องการของคุณ
### GroupDocs.Viewer สำหรับ .NET มีรุ่นทดลองใช้ฟรีหรือไม่
 ใช่ คุณสามารถสำรวจฟีเจอร์ของ GroupDocs.Viewer พร้อมให้ทดลองใช้ฟรีได้[ที่นี่](https://releases.groupdocs.com/).
### ฉันจะรับการสนับสนุนสำหรับ GroupDocs.Viewer สำหรับ .NET ได้ที่ไหน
 หากมีข้อสงสัยหรือความช่วยเหลือ คุณสามารถไปที่ฟอรัม GroupDocs.Viewer[ที่นี่](https://forum.groupdocs.com/c/viewer/9).