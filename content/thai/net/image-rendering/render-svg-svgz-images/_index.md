---
title: เรนเดอร์รูปภาพ SVG และ SVGZ
linktitle: เรนเดอร์รูปภาพ SVG และ SVGZ
second_title: GroupDocs.Viewer .NET API
description: เรียนรู้วิธีเรนเดอร์รูปภาพ SVG และ SVGZ โดยใช้ GroupDocs.Viewer สำหรับ .NET แปลงกราฟิกแบบเวกเตอร์เป็น HTML, JPG, PNG และ PDF ได้อย่างง่ายดาย
type: docs
weight: 16
url: /th/net/image-rendering/render-svg-svgz-images/
---
## การแนะนำ
ในบทช่วยสอนนี้ เราจะแนะนำคุณตลอดกระบวนการเรนเดอร์รูปภาพ SVG และ SVGZ โดยใช้ GroupDocs.Viewer สำหรับ .NET GroupDocs.Viewer สำหรับ .NET เป็น API การเรนเดอร์เอกสารอันทรงพลังที่ช่วยให้นักพัฒนาสามารถเรนเดอร์รูปแบบเอกสารที่หลากหลายในแอปพลิเคชัน .NET ของตนได้ SVG และ SVGZ เป็นรูปแบบรูปภาพยอดนิยมที่ใช้สำหรับกราฟิกแบบเวกเตอร์ และด้วย GroupDocs.Viewer สำหรับ .NET คุณสามารถเรนเดอร์เป็นรูปแบบเอาต์พุตต่างๆ เช่น HTML, JPG, PNG และ PDF ได้อย่างง่ายดาย
## ข้อกำหนดเบื้องต้น
ก่อนที่เราจะเริ่มต้น ตรวจสอบให้แน่ใจว่าคุณได้ติดตั้งและตั้งค่าข้อกำหนดเบื้องต้นต่อไปนี้:
1.  GroupDocs.Viewer for .NET: ดาวน์โหลดและติดตั้ง GroupDocs.Viewer for .NET จาก[ที่นี่](https://releases.groupdocs.com/viewer/net/).
2. สภาพแวดล้อมการพัฒนา: ตรวจสอบให้แน่ใจว่าคุณมีสภาพแวดล้อมการพัฒนาที่ใช้งานได้สำหรับการพัฒนา .NET เช่น Visual Studio
3. ไฟล์ SVGZ ตัวอย่าง: เตรียมไฟล์ SVGZ ตัวอย่างให้พร้อมสำหรับการทดสอบ

## นำเข้าเนมสเปซ
ก่อนที่เราจะเจาะลึกโค้ด เรามานำเข้าเนมสเปซที่จำเป็นก่อน:
```csharp
using GroupDocs.Viewer.Options;
using System;
using System.IO;
```
## ขั้นตอนที่ 1: เรนเดอร์ SVGZ เป็น HTML
```csharp
string outputDirectory = "Your Document Directory";
string pageFilePathFormat = Path.Combine(outputDirectory, "svgz_result.html");
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_SVGZ))
{
    HtmlViewOptions options = HtmlViewOptions.ForEmbeddedResources(pageFilePathFormat);
    viewer.View(options);
}
```

## ขั้นตอนที่ 2: เรนเดอร์ SVGZ เป็น JPG
```csharp
pageFilePathFormat = Path.Combine(outputDirectory, "svgz_result.jpg");
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_SVGZ))
{
    JpgViewOptions options = new JpgViewOptions(pageFilePathFormat);
    
    viewer.View(options);
}
```

## ขั้นตอนที่ 3: เรนเดอร์ SVGZ เป็น PNG
```csharp
pageFilePathFormat = Path.Combine(outputDirectory, "svgz_result.png");
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_SVGZ))
{
    PngViewOptions options = new PngViewOptions(pageFilePathFormat);
   
    viewer.View(options);
}
```

## ขั้นตอนที่ 4: เรนเดอร์ SVGZ เป็น PDF
```csharp
pageFilePathFormat = Path.Combine(outputDirectory, "svgz_result.pdf");
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_SVGZ))
{
    PdfViewOptions options = new PdfViewOptions(pageFilePathFormat);
   
    viewer.View(options);
}
```

## บทสรุป
ในบทช่วยสอนนี้ เราได้เรียนรู้วิธีเรนเดอร์รูปภาพ SVG และ SVGZ โดยใช้ GroupDocs.Viewer สำหรับ .NET ด้วยขั้นตอนง่ายๆ เพียงไม่กี่ขั้นตอน คุณสามารถแปลงรูปภาพ SVGZ เป็นรูปแบบเอาต์พุตต่างๆ เช่น HTML, JPG, PNG และ PDF ทำให้สามารถเข้าถึงและดูได้ในสภาพแวดล้อมที่แตกต่างกัน
## คำถามที่พบบ่อย
### GroupDocs.Viewer สามารถเรนเดอร์ภาพรูปแบบอื่นได้หรือไม่
ใช่ GroupDocs.Viewer รองรับการเรนเดอร์รูปภาพหลากหลายรูปแบบ รวมถึง PNG, JPEG, BMP, TIFF, GIF และอื่นๆ
### GroupDocs.Viewer เข้ากันได้กับ .NET Core หรือไม่
ใช่ GroupDocs.Viewer เข้ากันได้กับทั้ง .NET Framework และ .NET Core
### ฉันสามารถปรับแต่งตัวเลือกการเรนเดอร์ได้หรือไม่?
ใช่ GroupDocs.Viewer มีตัวเลือกการเรนเดอร์ที่หลากหลาย ซึ่งช่วยให้คุณปรับแต่งเอาต์พุตได้ตามความต้องการของคุณ
### GroupDocs.Viewer จำเป็นต้องมีการอ้างอิงจากบุคคลที่สามหรือไม่
ไม่ GroupDocs.Viewer เป็น API แบบสแตนด์อโลนและไม่จำเป็นต้องอาศัยบุคคลที่สามในการแสดงเอกสาร
### มีรุ่นทดลองให้ทดสอบหรือไม่?
ใช่ คุณสามารถดาวน์โหลด GroupDocs.Viewer เวอร์ชันทดลองใช้ฟรีได้จาก[ที่นี่](https://releases.groupdocs.com/) เพื่อประเมินคุณสมบัติก่อนตัดสินใจซื้อ