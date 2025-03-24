---
title: เรนเดอร์รูปภาพ AI
linktitle: เรนเดอร์รูปภาพ AI
second_title: GroupDocs.Viewer .NET API
description: เรียนรู้วิธีเรนเดอร์รูปภาพ AI ได้อย่างง่ายดายในแอปพลิเคชัน .NET โดยใช้ GroupDocs.Viewer สำหรับ .NET ปฏิบัติตามบทช่วยสอนทีละขั้นตอนของเราเพื่อการบูรณาการที่ราบรื่น
weight: 10
url: /th/net/image-rendering/render-ai-images/
---

# เรนเดอร์รูปภาพ AI

## การแนะนำ
GroupDocs.Viewer สำหรับ .NET เป็นไลบรารีที่มีประสิทธิภาพซึ่งช่วยให้นักพัฒนาสามารถเรนเดอร์รูปแบบเอกสารต่างๆ ภายในแอปพลิเคชัน .NET ของตนได้อย่างง่ายดาย ไม่ว่าคุณจะต้องการแสดงรูปภาพ AI, PDF หรือเอกสารประเภทอื่นๆ GroupDocs.Viewer จะทำให้กระบวนการง่ายขึ้น โดยนำเสนอรูปแบบเอาต์พุตที่หลากหลายเพื่อการผสานรวมเข้ากับโปรเจ็กต์ของคุณได้อย่างราบรื่น บทช่วยสอนนี้จะแนะนำคุณเกี่ยวกับการเรนเดอร์รูปภาพ AI ทีละขั้นตอนโดยใช้ GroupDocs.Viewer สำหรับ .NET
## ข้อกำหนดเบื้องต้น
ก่อนที่จะเข้าสู่บทช่วยสอน ตรวจสอบให้แน่ใจว่าคุณมีข้อกำหนดเบื้องต้นต่อไปนี้:
1. Visual Studio: ติดตั้ง Visual Studio IDE บนระบบของคุณ
2.  GroupDocs.Viewer for .NET: ดาวน์โหลดและติดตั้ง GroupDocs.Viewer for .NET จาก[เว็บไซต์](https://releases.groupdocs.com/viewer/net/).
3. ความรู้พื้นฐานเกี่ยวกับ C#: จำเป็นต้องมีความคุ้นเคยกับภาษาการเขียนโปรแกรม C# เพื่อทำความเข้าใจตัวอย่างโค้ด

## นำเข้าเนมสเปซ
ในโปรเจ็กต์ C# ของคุณ ให้นำเข้าเนมสเปซที่จำเป็นเพื่อเข้าถึงฟังก์ชันของ GroupDocs.Viewer สำหรับ .NET

```csharp
using GroupDocs.Viewer.Options;
using System;
using System.IO;
```

การเรนเดอร์รูปภาพ AI ด้วย GroupDocs.Viewer สำหรับ .NET เกี่ยวข้องกับหลายขั้นตอน โดยแต่ละขั้นตอนจะรองรับรูปแบบเอาต์พุตเฉพาะ ด้านล่างนี้ เราจะแบ่งกระบวนการออกเป็นขั้นตอนต่างๆ เพื่อความชัดเจน
## ขั้นตอนที่ 1: ระบุไดเรกทอรีผลลัพธ์
```csharp
string outputDirectory = "Your Document Directory";
```
## ขั้นตอนที่ 2: แสดงผลเป็น HTML
```csharp
string pageFilePathFormat = Path.Combine(outputDirectory, "ai_result.html");
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_AI))
{
    HtmlViewOptions options = HtmlViewOptions.ForEmbeddedResources(pageFilePathFormat);
    viewer.View(options);
}
```
## ขั้นตอนที่ 3: แสดงผลเป็น JPG
```csharp
string pageFilePathFormat = Path.Combine(outputDirectory, "ai_result.jpg");
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_AI))
{
    JpgViewOptions options = new JpgViewOptions(pageFilePathFormat);
    viewer.View(options);
}
```
## ขั้นตอนที่ 4: แสดงผลเป็น PNG
```csharp
string pageFilePathFormat = Path.Combine(outputDirectory, "ai_result.png");
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_AI))
{
    PngViewOptions options = new PngViewOptions(pageFilePathFormat);
    viewer.View(options);
}
```
## ขั้นตอนที่ 5: แสดงผลเป็น PDF
```csharp
string pageFilePathFormat = Path.Combine(outputDirectory, "ai_result.pdf");
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_AI))
{
    PdfViewOptions options = new PdfViewOptions(pageFilePathFormat);
    viewer.View(options);
}
```

## บทสรุป
GroupDocs.Viewer สำหรับ .NET นำเสนอโซลูชันที่ราบรื่นสำหรับการเรนเดอร์รูปภาพ AI และรูปแบบเอกสารต่างๆ ภายในแอปพลิเคชัน .NET ด้วยการทำตามคำแนะนำทีละขั้นตอนที่ให้ไว้ในบทช่วยสอนนี้ นักพัฒนาสามารถรวมความสามารถในการเรนเดอร์เอกสารเข้ากับโปรเจ็กต์ของตนได้อย่างง่ายดาย
## คำถามที่พบบ่อย
### ฉันสามารถปรับแต่งลักษณะเอาต์พุตเมื่อเรนเดอร์รูปภาพ AI ได้หรือไม่
ใช่ GroupDocs.Viewer สำหรับ .NET มีตัวเลือกมากมายสำหรับการปรับแต่งลักษณะที่ปรากฏของผลลัพธ์ รวมถึงขนาดหน้า คุณภาพของภาพ และอื่นๆ
### มีรุ่นทดลองใช้สำหรับการทดสอบหรือไม่?
 ใช่ คุณสามารถดาวน์โหลดเวอร์ชันทดลองใช้ฟรีได้จาก GroupDocs[เว็บไซต์](https://releases.groupdocs.com/viewer/net/) เพื่อประเมินคุณสมบัติของห้องสมุดก่อนตัดสินใจซื้อ
### GroupDocs.Viewer รองรับการเรนเดอร์รูปภาพ AI ที่เข้ารหัสหรือไม่
ใช่ GroupDocs.Viewer สำหรับ .NET รองรับการเรนเดอร์อิมเมจ AI ที่เข้ารหัสพร้อมคีย์ถอดรหัสที่เหมาะสมที่ให้มา
### ฉันสามารถเรนเดอร์รูปภาพ AI จาก URL ได้โดยตรงหรือไม่
ใช่ GroupDocs.Viewer สำหรับ .NET อนุญาตให้เรนเดอร์รูปภาพ AI จาก URL โดยระบุเส้นทาง URL แทนเส้นทางไฟล์ในเครื่อง
### มีการสนับสนุนทางเทคนิคสำหรับ GroupDocs.Viewer สำหรับ .NET หรือไม่
 ใช่ การสนับสนุนด้านเทคนิคมีให้ผ่าน GroupDocs[ฟอรั่ม](https://forum.groupdocs.com/c/viewer/9)ซึ่งคุณสามารถถามคำถาม รายงานปัญหา และขอความช่วยเหลือจากชุมชนได้