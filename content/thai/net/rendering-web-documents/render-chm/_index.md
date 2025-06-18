---
"description": "เรียนรู้วิธีการเรนเดอร์ไฟล์ CHM ใน .NET โดยใช้ GroupDocs.Viewer แปลง CHM เป็นรูปแบบ HTML, JPG, PNG และ PDF ได้อย่างง่ายดาย"
"linktitle": "เรนเดอร์ไฟล์ CHM"
"second_title": "API ของ GroupDocs.Viewer .NET"
"title": "เรนเดอร์ไฟล์ CHM"
"url": "/th/net/rendering-web-documents/render-chm/"
"weight": 10
---

# เรนเดอร์ไฟล์ CHM

## การแนะนำ
ในบทช่วยสอนนี้ เราจะมาเรียนรู้วิธีการเรนเดอร์ไฟล์ CHM (วิธีใช้ HTML ที่คอมไพล์แล้ว) โดยใช้ GroupDocs.Viewer สำหรับ .NET GroupDocs.Viewer สำหรับ .NET เป็น API การเรนเดอร์เอกสารอันทรงพลังที่ช่วยให้นักพัฒนาสามารถแสดงเอกสารได้มากกว่า 170 ประเภทภายในแอปพลิเคชัน .NET โดยไม่ต้องติดตั้งซอฟต์แวร์ภายนอกใดๆ

## ข้อกำหนดเบื้องต้น

ก่อนที่จะเริ่มการเรนเดอร์ไฟล์ CHM โปรดตรวจสอบให้แน่ใจว่าคุณมีข้อกำหนดเบื้องต้นดังต่อไปนี้:

### การติดตั้ง GroupDocs.Viewer สำหรับ .NET

ในการเริ่มต้น คุณต้องติดตั้ง GroupDocs.Viewer สำหรับ .NET คุณสามารถดาวน์โหลดไลบรารีได้จาก [เว็บไซต์ GroupDocs](https://releases.groupdocs.com/viewer/net/) หรือติดตั้งผ่านตัวจัดการแพ็กเกจ NuGet โดยรันคำสั่งต่อไปนี้ในคอนโซลตัวจัดการแพ็กเกจ:

```bash
Install-Package GroupDocs.Viewer
```

## การนำเข้าเนมสเปซ

อย่าลืมนำเข้าเนมสเปซที่จำเป็นลงในโครงการของคุณ:

```csharp
using System;
using System.Collections.Generic;
using System.Text;
using System.IO;
using GroupDocs.Viewer.Options;
```

ตอนนี้เรามาแบ่งกระบวนการเรนเดอร์ออกเป็นหลายขั้นตอน:

## ขั้นตอนที่ 1: กำหนดไดเรกทอรีผลลัพธ์

กำหนดไดเร็กทอรีที่คุณต้องการบันทึกไฟล์ที่เรนเดอร์:

```csharp
string outputDirectory = "Your Document Directory";
```

## ขั้นตอนที่ 2: เรนเดอร์เป็น HTML

หากต้องการเรนเดอร์ไฟล์ CHM เป็น HTML ให้ใช้โค้ดสั้นๆ ดังต่อไปนี้:

```csharp
string pageFilePathFormat = Path.Combine(outputDirectory, "chm_result_{0}.html");

using (Viewer viewer = new Viewer("Your_CHM_File_Path"))
{
    HtmlViewOptions options = HtmlViewOptions.ForEmbeddedResources(pageFilePathFormat);
    options.RenderToSinglePage = true; // ตั้งค่าเป็นจริงเพื่อแปลงเนื้อหา CHM ทั้งหมดลงในหน้าเดียว

    viewer.View(options); // แปลงหน้าทั้งหมด
}
```

## ขั้นตอนที่ 3: เรนเดอร์เป็น JPG

หากต้องการเรนเดอร์ไฟล์ CHM เป็นภาพ JPG ให้ใช้โค้ดสั้นๆ ดังต่อไปนี้:

```csharp
string pageFilePathFormat = Path.Combine(outputDirectory, "chm_result_{0}.jpg");

using (Viewer viewer = new Viewer("Your_CHM_File_Path"))
{
    JpgViewOptions options = new JpgViewOptions(pageFilePathFormat);

    viewer.View(options, 1, 2, 3); // แปลงเฉพาะหน้า 1, 2, 3 เท่านั้น
}
```

## ขั้นตอนที่ 4: เรนเดอร์เป็น PNG

ในการเรนเดอร์ไฟล์ CHM เป็นภาพ PNG ให้ใช้โค้ดสั้นๆ ดังต่อไปนี้:

```csharp
string pageFilePathFormat = Path.Combine(outputDirectory, "chm_result_{0}.png");

using (Viewer viewer = new Viewer("Your_CHM_File_Path"))
{
    PngViewOptions options = new PngViewOptions(pageFilePathFormat);

    viewer.View(options, 1, 2, 3); // แปลงเฉพาะหน้า 1, 2, 3 เท่านั้น
}
```

## ขั้นตอนที่ 5: เรนเดอร์เป็น PDF

หากต้องการแสดงไฟล์ CHM เป็นเอกสาร PDF ให้ใช้โค้ดสั้นๆ ดังต่อไปนี้:

```csharp
string pageFilePathFormat = Path.Combine(outputDirectory, "chm_result.pdf");

using (Viewer viewer = new Viewer("Your_CHM_File_Path"))
{
    PdfViewOptions options = new PdfViewOptions(pageFilePathFormat);

    viewer.View(options); // แปลงหน้าทั้งหมด
}
```

## ขั้นตอนที่ 6: ตรวจสอบผลลัพธ์

เมื่อกระบวนการเรนเดอร์เสร็จสมบูรณ์แล้ว ให้ตรวจสอบไดเร็กทอรีเอาท์พุตที่ระบุสำหรับไฟล์ที่เรนเดอร์:

```csharp
Console.WriteLine($"\nSource document rendered successfully.\nCheck output in {outputDirectory}.");
```

## บทสรุป

การเรนเดอร์ไฟล์ CHM โดยใช้ GroupDocs.Viewer สำหรับ .NET เป็นกระบวนการที่ตรงไปตรงมา เพียงทำตามขั้นตอนที่ระบุไว้ในบทช่วยสอนนี้ คุณจะสามารถแปลงเอกสาร CHM เป็นรูปแบบต่างๆ เช่น HTML, รูปภาพ (JPG, PNG) และ PDF ภายในแอปพลิเคชัน .NET ของคุณได้อย่างมีประสิทธิภาพ

## คำถามที่พบบ่อย

### คำถามที่ 1: GroupDocs.Viewer สามารถแสดงรูปแบบเอกสารอื่นนอกเหนือจาก CHM ได้หรือไม่

A1: ใช่ GroupDocs.Viewer รองรับการเรนเดอร์รูปแบบเอกสารมากกว่า 170 รูปแบบ รวมถึง PDF, DOCX, XLSX, PPTX และอื่นๆ อีกมากมาย

### คำถามที่ 2: GroupDocs.Viewer เข้ากันได้กับ .NET Core หรือไม่

A2: ใช่ GroupDocs.Viewer รองรับ .NET Core นอกเหนือจาก .NET Framework ดั้งเดิม

### คำถามที่ 3: ฉันสามารถปรับแต่งตัวเลือกการเรนเดอร์สำหรับรูปแบบเอาต์พุตที่แตกต่างกันได้หรือไม่

A3: ใช่ GroupDocs.Viewer มีตัวเลือกต่างๆ สำหรับการปรับแต่งกระบวนการเรนเดอร์ เช่น การระบุหมายเลขหน้า การตั้งค่าคุณภาพของภาพ และการกำหนดค่าเส้นทางเอาต์พุต

### คำถามที่ 4: GroupDocs.Viewer ต้องมีการอ้างอิงภายนอกในการเรนเดอร์เอกสารหรือไม่

A4: ไม่ GroupDocs.Viewer เป็นไลบรารีแบบสแตนด์อโลนและไม่จำเป็นต้องมีการอ้างอิงภายนอกหรือการติดตั้งซอฟต์แวร์ของบริษัทอื่น

### คำถามที่ 5: มีรุ่นทดลองใช้งานฟรีสำหรับ GroupDocs.Viewer หรือไม่

A5: ใช่ คุณสามารถใช้ประโยชน์จากการทดลองใช้ GroupDocs.Viewer ฟรีได้โดยเข้าไปที่ [เว็บไซต์](https://releases-groupdocs.com/).