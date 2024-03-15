---
title: ย่อขนาดเอกสาร HTML ที่แสดงผล
linktitle: ย่อขนาดเอกสาร HTML ที่แสดงผล
second_title: GroupDocs.Viewer .NET API
description: เรียนรู้วิธีเรนเดอร์เอกสาร HTML ในแอปพลิเคชัน .NET ได้อย่างราบรื่นโดยใช้ GroupDocs.Viewer สำหรับ .NET
type: docs
weight: 11
url: /th/net/rendering-documents-html/minify-html/
---
## การแนะนำ
GroupDocs.Viewer สำหรับ .NET เป็นเครื่องมืออันทรงพลังที่ช่วยให้นักพัฒนาสามารถเรนเดอร์เอกสาร HTML ภายในแอปพลิเคชัน .NET ของตนได้อย่างราบรื่น ด้วย API ที่ใช้งานง่ายและฟังก์ชันการทำงานที่แข็งแกร่ง นักพัฒนาสามารถรวมความสามารถในการดูเอกสารเข้ากับแอปพลิเคชันของตนได้อย่างง่ายดาย ช่วยเพิ่มประสบการณ์ผู้ใช้และประสิทธิภาพการทำงาน
## ข้อกำหนดเบื้องต้น
ก่อนที่จะเริ่มใช้ GroupDocs.Viewer สำหรับ .NET ตรวจสอบให้แน่ใจว่าคุณมีข้อกำหนดเบื้องต้นต่อไปนี้:
### 1. ความรู้เกี่ยวกับ C# และ .NET Framework
หากต้องการใช้ GroupDocs.Viewer สำหรับ .NET ได้อย่างมีประสิทธิภาพ คุณควรมีความเข้าใจพื้นฐานเกี่ยวกับภาษาการเขียนโปรแกรม C# และ .NET Framework
### 2. วิชวลสตูดิโอ IDE
ตรวจสอบให้แน่ใจว่าคุณได้ติดตั้ง Visual Studio IDE บนระบบของคุณแล้ว คุณสามารถดาวน์โหลดได้จากเว็บไซต์อย่างเป็นทางการ
### 3. GroupDocs.Viewer สำหรับ .NET Library
 ดาวน์โหลดไลบรารี GroupDocs.Viewer สำหรับ .NET จากไฟล์ที่ให้มา[ลิ้งค์ดาวน์โหลด](https://releases.groupdocs.com/viewer/net/) และรวมไว้ในโครงการของคุณ
### 4. ไฟล์เอกสาร
เตรียมไฟล์เอกสารที่คุณต้องการแสดงผลโดยใช้ GroupDocs.Viewer สำหรับ .NET รูปแบบไฟล์ที่รองรับได้แก่ DOCX, PDF, PPTX และอื่นๆ
### 5. ใบอนุญาตชั่วคราว (ไม่บังคับ)
 หากคุณใช้ GroupDocs.Viewer สำหรับ .NET ในสภาพแวดล้อมการทดลองใช้หรือการทดสอบ ให้ขอรับใบอนุญาตชั่วคราวจาก[หน้าใบอนุญาตชั่วคราว](https://purchase.groupdocs.com/temporary-license/).

## นำเข้าเนมสเปซ
ในแอปพลิเคชัน .NET ของคุณ ให้เริ่มด้วยการนำเข้าเนมสเปซที่จำเป็นเพื่อเข้าถึงฟังก์ชันการทำงานของ GroupDocs.Viewer สำหรับ .NET
```csharp
using System;
using System.IO;
using GroupDocs.Viewer.Options;
```

ตอนนี้ เรามาแจกแจงกระบวนการย่อขนาดเอกสาร HTML ที่แสดงผลโดยใช้ GroupDocs.Viewer สำหรับ .NET ออกเป็นหลายขั้นตอน:
## ขั้นตอนที่ 1: กำหนดไดเรกทอรีผลลัพธ์
ระบุไดเร็กทอรีที่คุณต้องการบันทึกเพจ HTML ที่แสดงผล
```csharp
string outputDirectory = "Your Document Directory";
```
## ขั้นตอนที่ 2: กำหนดรูปแบบเส้นทางไฟล์เพจ
กำหนดรูปแบบของเส้นทางไฟล์สำหรับเพจ HTML ที่แสดงผลแต่ละหน้า
```csharp
string pageFilePathFormat = Path.Combine(outputDirectory, "page_{0}.html");
```
## ขั้นตอนที่ 3: แสดงผลเอกสาร HTML
สร้างอินสแตนซ์ของวัตถุ Viewer และส่งผ่านเส้นทางของไฟล์เอกสารที่คุณต้องการแสดงผล
```csharp
using (Viewer viewer = new Viewer("Path_to_Your_Document"))
{
    HtmlViewOptions options = HtmlViewOptions.ForEmbeddedResources(pageFilePathFormat);
    options.Minify = true;
    viewer.View(options);
}
```
## ขั้นตอนที่ 4: แสดงข้อความแสดงความสำเร็จ
แสดงข้อความระบุว่าเอกสารแสดงผลสำเร็จแล้ว
```csharp
Console.WriteLine($"\nSource document rendered successfully.\nCheck output in {outputDirectory}.");
```

## บทสรุป
โดยสรุป GroupDocs.Viewer สำหรับ .NET นำเสนอโซลูชันที่ราบรื่นสำหรับการเรนเดอร์เอกสาร HTML ภายในแอปพลิเคชัน .NET ด้วยการทำตามขั้นตอนที่ระบุไว้ในบทช่วยสอนนี้ คุณสามารถรวมความสามารถในการดูเอกสารเข้ากับแอปพลิเคชันของคุณได้อย่างง่ายดาย ปรับปรุงประสบการณ์ผู้ใช้และประสิทธิภาพการทำงาน
## คำถามที่พบบ่อย
### ฉันสามารถเรนเดอร์เอกสารจากแหล่งภายนอกโดยใช้ GroupDocs.Viewer สำหรับ .NET ได้หรือไม่
ใช่ GroupDocs.Viewer สำหรับ .NET รองรับการเรนเดอร์เอกสารจากแหล่งต่างๆ รวมถึงไฟล์ในเครื่อง สตรีม และ URL
### GroupDocs.Viewer สำหรับ .NET มีรุ่นทดลองใช้ฟรีหรือไม่
 ใช่ คุณสามารถขอรับ GroupDocs.Viewer สำหรับ .NET รุ่นทดลองใช้ฟรีได้จาก[เว็บไซต์อย่างเป็นทางการ](https://releases.groupdocs.com/).
### GroupDocs.Viewer for .NET รองรับการแปลงเอกสารเป็นรูปแบบอื่นหรือไม่
ใช่ GroupDocs.Viewer สำหรับ .NET มี API สำหรับการแปลงเอกสารเป็นรูปแบบต่างๆ เช่น PDF, HTML และรูปภาพ
### ฉันสามารถปรับแต่งตัวเลือกการเรนเดอร์สำหรับเอกสารใน GroupDocs.Viewer สำหรับ .NET ได้หรือไม่
ใช่ คุณสามารถปรับแต่งตัวเลือกการแสดงผลต่างๆ ได้ เช่น การวางแนวหน้า คุณภาพ และลายน้ำ ตามความต้องการของคุณ
### ฉันจะขอรับการสนับสนุนสำหรับ GroupDocs.Viewer สำหรับ .NET ได้ที่ไหน
 คุณสามารถขอการสนับสนุนและมีส่วนร่วมกับชุมชนได้ที่[ฟอรัม GroupDocs.Viewer](https://forum.groupdocs.com/c/viewer/9).