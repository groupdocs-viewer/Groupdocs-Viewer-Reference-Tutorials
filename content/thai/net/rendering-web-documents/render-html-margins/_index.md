---
title: เรนเดอร์ HTML ด้วยระยะขอบที่ผู้ใช้กำหนด
linktitle: เรนเดอร์ HTML ด้วยระยะขอบที่ผู้ใช้กำหนด
second_title: GroupDocs.Viewer .NET API
description: เรียนรู้วิธีการแสดงผล HTML ด้วยระยะขอบแบบกำหนดเองใน .NET โดยใช้ GroupDocs.Viewer ปรับปรุงการนำเสนอเอกสารได้อย่างง่ายดาย
weight: 11
url: /th/net/rendering-web-documents/render-html-margins/
---
## การแนะนำ
ในขอบเขตของการพัฒนา .NET การแสดง HTML ด้วยระยะขอบที่ผู้ใช้กำหนดเป็นส่วนสำคัญในการสร้างเอกสารที่ดึงดูดสายตา ไม่ว่าจะเป็นการปรับระยะขอบสำหรับเว็บไซต์หรือการกำหนดค่าเค้าโครงการพิมพ์ การควบคุมระยะขอบที่แม่นยำจะช่วยเพิ่มการนำเสนอเนื้อหาโดยรวม ในบทช่วยสอนนี้ เราจะเจาะลึกการใช้ GroupDocs.Viewer สำหรับ .NET เพื่อให้บรรลุฟังก์ชันการทำงานนี้ได้อย่างราบรื่น
## ข้อกำหนดเบื้องต้น
ก่อนที่จะเข้าสู่บทช่วยสอน ตรวจสอบให้แน่ใจว่าคุณมีข้อกำหนดเบื้องต้นต่อไปนี้:
1.  GroupDocs.Viewer สำหรับ .NET: ติดตั้ง GroupDocs.Viewer สำหรับไลบรารี .NET คุณสามารถดาวน์โหลดได้จาก[เว็บไซต์](https://releases.groupdocs.com/viewer/net/).
2. .NET Environment: มีสภาพแวดล้อมการทำงานสำหรับการพัฒนา .NET
3. เอกสาร HTML: เตรียมเอกสาร HTML ที่คุณต้องการแสดงผลด้วยระยะขอบที่กำหนดเอง

## นำเข้าเนมสเปซ
ก่อนที่คุณจะเริ่มต้น ตรวจสอบให้แน่ใจว่าได้นำเข้าเนมสเปซที่จำเป็น:
```csharp
using GroupDocs.Viewer.Options;
using System;
using System.IO;
```
## ขั้นตอนที่ 1: ตั้งค่าไดเรกทอรีผลลัพธ์
กำหนดไดเร็กทอรีที่คุณต้องการให้บันทึกไฟล์ที่แสดงผล:
```csharp
string outputDirectory = "Your Document Directory";
```
## ขั้นตอนที่ 2: กำหนดรูปแบบเส้นทางไฟล์เพจ
ตั้งค่ารูปแบบสำหรับเส้นทางไฟล์ของหน้าที่แสดงผล:
```csharp
string pageFilePathFormat = Path.Combine(outputDirectory, "html_render_margins_page_{0}.jpg");
```
## ขั้นตอนที่ 3: ปรับระยะขอบสำหรับการแสดงผล JPG
กำหนดค่าระยะขอบสำหรับการแสดงผล HTML เป็น JPG:
```csharp
using (Viewer viewer = new Viewer("Path_to_your_HTML_file"))
{
    JpgViewOptions options = new JpgViewOptions(pageFilePathFormat);
    options.WordProcessingOptions.LeftMargin = 40;
    options.WordProcessingOptions.RightMargin = 40;
    options.WordProcessingOptions.TopMargin = 40;
    options.WordProcessingOptions.BottomMargin = 40;
    viewer.View(options);
}
```
## ขั้นตอนที่ 4: ปรับระยะขอบสำหรับการแสดงผล PNG
ในทำนองเดียวกัน ปรับระยะขอบสำหรับการแสดงผล HTML เป็นรูปแบบ PNG:
```csharp
using (Viewer viewer = new Viewer("Path_to_your_HTML_file"))
{
    PngViewOptions options = new PngViewOptions(pageFilePathFormat);
    options.WordProcessingOptions.LeftMargin = 40;
    options.WordProcessingOptions.RightMargin = 40;
    options.WordProcessingOptions.TopMargin = 40;
    options.WordProcessingOptions.BottomMargin = 40;
    viewer.View(options);
}
```
## ขั้นตอนที่ 5: ปรับระยะขอบสำหรับการแสดงผล PDF
สำหรับการเรนเดอร์ PDF ให้ตั้งค่าระยะขอบตาม:
```csharp
using (Viewer viewer = new Viewer("Path_to_your_HTML_file"))
{
    PdfViewOptions options = new PdfViewOptions(pageFilePathFormat);
    options.WordProcessingOptions.LeftMargin = 40;
    options.WordProcessingOptions.RightMargin = 40;
    options.WordProcessingOptions.TopMargin = 40;
    options.WordProcessingOptions.BottomMargin = 40;
    viewer.View(options);
}
```

## บทสรุป
การปรับแต่งระยะขอบเมื่อเรนเดอร์เอกสาร HTML ใน .NET โดยใช้ GroupDocs.Viewer ช่วยให้นักพัฒนาปรับแต่งการนำเสนอเนื้อหาได้อย่างแม่นยำ เมื่อทำตามบทช่วยสอนนี้ คุณจะสามารถปรับระยะขอบสำหรับรูปแบบเอาต์พุต JPG, PNG หรือ PDF ได้อย่างง่ายดาย ช่วยเพิ่มความสวยงามและความสามารถในการอ่านเอกสารของคุณ
## คำถามที่พบบ่อย
### GroupDocs.Viewer สำหรับ .NET เข้ากันได้กับรูปแบบ HTML ที่แตกต่างกันหรือไม่
GroupDocs.Viewer รองรับรูปแบบ HTML ที่หลากหลาย จึงรับประกันความเข้ากันได้กับเอกสาร HTML ต่างๆ
### ฉันสามารถปรับระยะขอบแบบไดนามิกตามเนื้อหาเอกสารได้หรือไม่
ได้ คุณสามารถปรับระยะขอบโดยทางโปรแกรมตามคุณสมบัติของเอกสารหรือการตั้งค่าของผู้ใช้
### มีข้อจำกัดในการปรับมาร์จิ้นหรือไม่?
GroupDocs.Viewer มอบความยืดหยุ่นในการปรับระยะขอบ ช่วยให้ปรับแต่งได้ภายในขอบเขตที่สมเหตุสมผล
### GroupDocs.Viewer รองรับรูปแบบเอาต์พุตอื่นๆ นอกเหนือจาก JPG, PNG และ PDF หรือไม่
ใช่ GroupDocs.Viewer รองรับการเรนเดอร์ในรูปแบบต่างๆ รวมถึง TIFF, SVG และอื่นๆ
### ฉันจะขอความช่วยเหลือเพิ่มเติมหรือรายงานปัญหาที่เกี่ยวข้องกับ GroupDocs.Viewer ได้อย่างไร
 คุณสามารถเยี่ยมชมฟอรัม GroupDocs.Viewer[ที่นี่](https://forum.groupdocs.com/c/viewer/9) สำหรับการสนับสนุนและการอภิปราย