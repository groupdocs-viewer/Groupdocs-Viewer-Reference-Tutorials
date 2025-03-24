---
title: เรนเดอร์ไฟล์ CHM
linktitle: เรนเดอร์ไฟล์ CHM
second_title: GroupDocs.Viewer .NET API
description: เรียนรู้วิธีเรนเดอร์ไฟล์ CHM ใน .NET โดยใช้ GroupDocs.Viewer แปลง CHM เป็นรูปแบบ HTML, JPG, PNG และ PDF ได้อย่างง่ายดาย
weight: 10
url: /th/net/rendering-web-documents/render-chm/
---
## การแนะนำ
ในบทช่วยสอนนี้ เราจะสำรวจวิธีเรนเดอร์ไฟล์ CHM (Compiled HTML Help) โดยใช้ GroupDocs.Viewer สำหรับ .NET GroupDocs.Viewer สำหรับ .NET เป็น API การเรนเดอร์เอกสารที่ทรงพลัง ซึ่งช่วยให้นักพัฒนาสามารถแสดงเอกสารมากกว่า 170 ประเภทภายในแอปพลิเคชัน .NET ของตน โดยไม่ต้องติดตั้งซอฟต์แวร์ภายนอกใดๆ

## ข้อกำหนดเบื้องต้น

ก่อนที่เราจะเจาะลึกเรื่องการเรนเดอร์ไฟล์ CHM ตรวจสอบให้แน่ใจว่าคุณมีข้อกำหนดเบื้องต้นดังต่อไปนี้:

### การติดตั้ง GroupDocs.Viewer สำหรับ .NET

 ในการเริ่มต้น คุณต้องติดตั้ง GroupDocs.Viewer สำหรับ .NET คุณสามารถดาวน์โหลดห้องสมุดได้จาก[เว็บไซต์กรุ๊ปดอคส์](https://releases.groupdocs.com/viewer/net/) หรือติดตั้งผ่าน NuGet Package Manager โดยรันคำสั่งต่อไปนี้ใน Package Manager Console:

```bash
Install-Package GroupDocs.Viewer
```

## การนำเข้าเนมสเปซ

ตรวจสอบให้แน่ใจว่าได้นำเข้าเนมสเปซที่จำเป็นในโครงการของคุณ:

```csharp
using System;
using System.Collections.Generic;
using System.Text;
using System.IO;
using GroupDocs.Viewer.Options;
```

ตอนนี้เรามาแบ่งกระบวนการเรนเดอร์ออกเป็นหลายขั้นตอน:

## ขั้นตอนที่ 1: กำหนดไดเรกทอรีผลลัพธ์

กำหนดไดเร็กทอรีที่คุณต้องการให้บันทึกไฟล์ที่แสดงผล:

```csharp
string outputDirectory = "Your Document Directory";
```

## ขั้นตอนที่ 2: แสดงผลเป็น HTML

หากต้องการเรนเดอร์ไฟล์ CHM เป็น HTML ให้ใช้ข้อมูลโค้ดต่อไปนี้:

```csharp
string pageFilePathFormat = Path.Combine(outputDirectory, "chm_result_{0}.html");

using (Viewer viewer = new Viewer("Your_CHM_File_Path"))
{
    HtmlViewOptions options = HtmlViewOptions.ForEmbeddedResources(pageFilePathFormat);
    options.RenderToSinglePage = true; // ตั้งค่าเป็นจริงเพื่อแปลงเนื้อหา CHM ทั้งหมดเป็นหน้าเดียว

    viewer.View(options); //แปลงหน้าทั้งหมด
}
```

## ขั้นตอนที่ 3: แสดงผลเป็น JPG

หากต้องการแสดงไฟล์ CHM เป็นภาพ JPG ให้ใช้ข้อมูลโค้ดต่อไปนี้:

```csharp
string pageFilePathFormat = Path.Combine(outputDirectory, "chm_result_{0}.jpg");

using (Viewer viewer = new Viewer("Your_CHM_File_Path"))
{
    JpgViewOptions options = new JpgViewOptions(pageFilePathFormat);

    viewer.View(options, 1, 2, 3); // แปลงเฉพาะหน้า 1, 2, 3
}
```

## ขั้นตอนที่ 4: แสดงผลเป็น PNG

หากต้องการแสดงไฟล์ CHM เป็นรูปภาพ PNG ให้ใช้ข้อมูลโค้ดต่อไปนี้:

```csharp
string pageFilePathFormat = Path.Combine(outputDirectory, "chm_result_{0}.png");

using (Viewer viewer = new Viewer("Your_CHM_File_Path"))
{
    PngViewOptions options = new PngViewOptions(pageFilePathFormat);

    viewer.View(options, 1, 2, 3); // แปลงเฉพาะหน้า 1, 2, 3
}
```

## ขั้นตอนที่ 5: แสดงผลเป็น PDF

หากต้องการเรนเดอร์ไฟล์ CHM เป็นเอกสาร PDF ให้ใช้ข้อมูลโค้ดต่อไปนี้:

```csharp
string pageFilePathFormat = Path.Combine(outputDirectory, "chm_result.pdf");

using (Viewer viewer = new Viewer("Your_CHM_File_Path"))
{
    PdfViewOptions options = new PdfViewOptions(pageFilePathFormat);

    viewer.View(options); //แปลงหน้าทั้งหมด
}
```

## ขั้นตอนที่ 6: ตรวจสอบเอาต์พุต

เมื่อกระบวนการเรนเดอร์เสร็จสมบูรณ์ ให้ตรวจสอบไดเร็กทอรีเอาต์พุตที่ระบุสำหรับไฟล์ที่เรนเดอร์:

```csharp
Console.WriteLine($"\nSource document rendered successfully.\nCheck output in {outputDirectory}.");
```

## บทสรุป

การเรนเดอร์ไฟล์ CHM โดยใช้ GroupDocs.Viewer สำหรับ .NET เป็นกระบวนการที่ไม่ซับซ้อน ด้วยการทำตามขั้นตอนที่อธิบายไว้ในบทช่วยสอนนี้ คุณสามารถแปลงเอกสาร CHM เป็นรูปแบบต่างๆ เช่น HTML, รูปภาพ (JPG, PNG) และ PDF ภายในแอปพลิเคชัน .NET ของคุณได้อย่างมีประสิทธิภาพ

## คำถามที่พบบ่อย

### คำถามที่ 1: GroupDocs.Viewer สามารถเรนเดอร์รูปแบบเอกสารอื่นนอกเหนือจาก CHM ได้หรือไม่

ตอบ 1: ใช่ GroupDocs.Viewer รองรับการเรนเดอร์เอกสารมากกว่า 170 รูปแบบ รวมถึง PDF, DOCX, XLSX, PPTX และอื่นๆ

### คำถามที่ 2: GroupDocs.Viewer เข้ากันได้กับ .NET Core หรือไม่

A2: ใช่ GroupDocs.Viewer รองรับ .NET Core นอกเหนือจาก .NET Framework แบบดั้งเดิม

### คำถามที่ 3: ฉันสามารถปรับแต่งตัวเลือกการเรนเดอร์สำหรับรูปแบบเอาต์พุตที่แตกต่างกันได้หรือไม่

A3: ใช่ GroupDocs.Viewer มีตัวเลือกต่างๆ สำหรับการปรับแต่งกระบวนการเรนเดอร์ เช่น การระบุหมายเลขหน้า การตั้งค่าคุณภาพของภาพ และการกำหนดค่าเส้นทางเอาต์พุต

### คำถามที่ 4: GroupDocs.Viewer จำเป็นต้องมีการอ้างอิงภายนอกในการแสดงเอกสารหรือไม่

A4: ไม่ GroupDocs.Viewer เป็นไลบรารีแบบสแตนด์อโลน และไม่จำเป็นต้องอาศัยการขึ้นต่อกันภายนอกหรือการติดตั้งซอฟต์แวร์ของบริษัทอื่น

### คำถามที่ 5: GroupDocs.Viewer มีรุ่นทดลองใช้ฟรีหรือไม่

 A5: ได้ คุณสามารถทดลองใช้ GroupDocs.Viewer ได้ฟรีโดยไปที่[เว็บไซต์](https://releases.groupdocs.com/).