---
"description": "เรียนรู้วิธีการเรนเดอร์ภาพ SVG และ SVGZ โดยใช้ GroupDocs.Viewer สำหรับ .NET แปลงกราฟิกเวกเตอร์เป็น HTML, JPG, PNG และ PDF ได้อย่างง่ายดาย"
"linktitle": "เรนเดอร์รูปภาพ SVG และ SVGZ"
"second_title": "API ของ GroupDocs.Viewer .NET"
"title": "เรนเดอร์รูปภาพ SVG และ SVGZ"
"url": "/th/net/image-rendering/render-svg-svgz-images/"
"weight": 16
---

# เรนเดอร์รูปภาพ SVG และ SVGZ

## การแนะนำ
ในบทช่วยสอนนี้ เราจะแนะนำคุณเกี่ยวกับกระบวนการเรนเดอร์ภาพ SVG และ SVGZ โดยใช้ GroupDocs.Viewer สำหรับ .NET GroupDocs.Viewer สำหรับ .NET เป็น API การเรนเดอร์เอกสารอันทรงพลังที่ช่วยให้นักพัฒนาสามารถเรนเดอร์รูปแบบเอกสารต่างๆ ในแอปพลิเคชัน .NET ของตนเองได้ SVG และ SVGZ เป็นรูปแบบภาพที่นิยมใช้สำหรับกราฟิกแบบเวกเตอร์ และด้วย GroupDocs.Viewer สำหรับ .NET คุณสามารถเรนเดอร์ภาพเหล่านี้เป็นรูปแบบเอาต์พุตต่างๆ เช่น HTML, JPG, PNG และ PDF ได้อย่างง่ายดาย

![เรนเดอร์ภาพ SVG และ SVGZ ด้วย GroupDocs.Viewer สำหรับ .NET](/viewer/image-rendering/render-svg-and-svgz-images.png)

## ข้อกำหนดเบื้องต้น
ก่อนที่เราจะเริ่มต้น โปรดตรวจสอบให้แน่ใจว่าคุณได้ติดตั้งและตั้งค่าข้อกำหนดเบื้องต้นต่อไปนี้แล้ว:
1. GroupDocs.Viewer สำหรับ .NET: ดาวน์โหลดและติดตั้ง GroupDocs.Viewer สำหรับ .NET จาก [ที่นี่](https://releases-groupdocs.com/viewer/net/).
2. สภาพแวดล้อมการพัฒนา: ตรวจสอบให้แน่ใจว่าคุณมีสภาพแวดล้อมการพัฒนาที่ใช้งานได้สำหรับการพัฒนา .NET เช่น Visual Studio
3. ไฟล์ตัวอย่าง SVGZ: เตรียมไฟล์ตัวอย่าง SVGZ ไว้สำหรับการทดสอบ

## นำเข้าเนมสเปซ
ก่อนที่เราจะเจาะลึกโค้ด เรามาทำการนำเข้าเนมสเปซที่จำเป็นกันก่อน:
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
ในบทช่วยสอนนี้ เราได้เรียนรู้วิธีการเรนเดอร์รูปภาพ SVG และ SVGZ โดยใช้ GroupDocs.Viewer สำหรับ .NET ด้วยขั้นตอนง่ายๆ เพียงไม่กี่ขั้นตอน คุณสามารถแปลงรูปภาพ SVGZ เป็นรูปแบบเอาต์พุตต่างๆ เช่น HTML, JPG, PNG และ PDF ทำให้เข้าถึงและดูได้ในสภาพแวดล้อมที่แตกต่างกัน
## คำถามที่พบบ่อย
### GroupDocs.Viewer สามารถแสดงรูปแบบรูปภาพอื่นๆ ได้หรือไม่
ใช่ GroupDocs.Viewer รองรับการเรนเดอร์รูปแบบภาพต่างๆ รวมถึง PNG, JPEG, BMP, TIFF, GIF และอื่นๆ อีกมากมาย
### GroupDocs.Viewer เข้ากันได้กับ .NET Core ได้หรือไม่
ใช่ GroupDocs.Viewer เข้ากันได้กับทั้ง .NET Framework และ .NET Core
### ฉันสามารถปรับแต่งตัวเลือกการเรนเดอร์ได้หรือไม่
ใช่ GroupDocs.Viewer มีตัวเลือกการเรนเดอร์มากมายทำให้คุณปรับแต่งผลลัพธ์ตามความต้องการของคุณได้
### GroupDocs.Viewer ต้องใช้การอ้างอิงของบุคคลที่สามหรือไม่
ไม่ GroupDocs.Viewer เป็น API แบบสแตนด์อโลนและไม่ต้องใช้การอ้างอิงของบุคคลที่สามเพื่อการแสดงผลเอกสาร
### มีเวอร์ชันทดลองใช้สำหรับการทดสอบหรือไม่?
ใช่ คุณสามารถดาวน์โหลด GroupDocs.Viewer เวอร์ชันทดลองใช้งานฟรีได้จาก [ที่นี่](https://releases.groupdocs.com/) เพื่อประเมินคุณสมบัติก่อนตัดสินใจซื้อ