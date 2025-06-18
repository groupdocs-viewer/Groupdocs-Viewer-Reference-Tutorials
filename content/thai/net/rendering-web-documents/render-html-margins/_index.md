---
"description": "เรียนรู้วิธีการเรนเดอร์ HTML ด้วยระยะขอบที่กำหนดเองใน .NET โดยใช้ GroupDocs.Viewer ปรับปรุงการนำเสนอเอกสารได้อย่างง่ายดาย"
"linktitle": "เรนเดอร์ HTML พร้อมระยะขอบที่ผู้ใช้กำหนด"
"second_title": "API ของ GroupDocs.Viewer .NET"
"title": "เรนเดอร์ HTML พร้อมระยะขอบที่ผู้ใช้กำหนด"
"url": "/th/net/rendering-web-documents/render-html-margins/"
"weight": 11
---

# เรนเดอร์ HTML พร้อมระยะขอบที่ผู้ใช้กำหนด

## การแนะนำ
ในขอบเขตของการพัฒนา .NET การเรนเดอร์ HTML ด้วยระยะขอบที่ผู้ใช้กำหนดถือเป็นส่วนสำคัญในการสร้างเอกสารที่ดึงดูดสายตา ไม่ว่าจะเป็นการปรับระยะขอบสำหรับเว็บไซต์หรือการกำหนดค่าเลย์เอาต์การพิมพ์ การควบคุมระยะขอบที่แม่นยำจะช่วยปรับปรุงการนำเสนอเนื้อหาโดยรวม ในบทช่วยสอนนี้ เราจะเจาะลึกถึงการใช้ GroupDocs.Viewer สำหรับ .NET เพื่อให้ได้ฟังก์ชันนี้อย่างราบรื่น
## ข้อกำหนดเบื้องต้น
ก่อนจะเริ่มบทช่วยสอนนี้ ให้แน่ใจว่าคุณมีข้อกำหนดเบื้องต้นดังต่อไปนี้:
1. GroupDocs.Viewer สำหรับ .NET: ติดตั้งไลบรารี GroupDocs.Viewer สำหรับ .NET คุณสามารถดาวน์โหลดได้จาก [เว็บไซต์](https://releases-groupdocs.com/viewer/net/).
2. สภาพแวดล้อม .NET: มีสภาพแวดล้อมการทำงานสำหรับการพัฒนา .NET
3. เอกสาร HTML: เตรียมเอกสาร HTML ที่คุณต้องการเรนเดอร์พร้อมระยะขอบแบบกำหนดเอง

## นำเข้าเนมสเปซ
ก่อนที่คุณจะเริ่มต้น โปรดแน่ใจว่าได้นำเข้าเนมสเปซที่จำเป็นแล้ว:
```csharp
using GroupDocs.Viewer.Options;
using System;
using System.IO;
```
## ขั้นตอนที่ 1: ตั้งค่าไดเรกทอรีผลลัพธ์
กำหนดไดเร็กทอรีที่คุณต้องการบันทึกไฟล์ที่เรนเดอร์:
```csharp
string outputDirectory = "Your Document Directory";
```
## ขั้นตอนที่ 2: กำหนดรูปแบบเส้นทางไฟล์เพจ
กำหนดรูปแบบสำหรับเส้นทางไฟล์ของหน้าที่แสดงผล:
```csharp
string pageFilePathFormat = Path.Combine(outputDirectory, "html_render_margins_page_{0}.jpg");
```
## ขั้นตอนที่ 3: ปรับระยะขอบสำหรับการเรนเดอร์ JPG
กำหนดค่าระยะขอบสำหรับการเรนเดอร์ HTML เป็นรูปแบบ JPG:
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
## ขั้นตอนที่ 4: ปรับระยะขอบสำหรับการเรนเดอร์ PNG
ในทำนองเดียวกัน ให้ปรับระยะขอบสำหรับการเรนเดอร์ HTML เป็นรูปแบบ PNG:
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
## ขั้นตอนที่ 5: ปรับระยะขอบสำหรับการเรนเดอร์ PDF
สำหรับการเรนเดอร์ PDF ให้ตั้งค่าระยะขอบให้เหมาะสม:
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
การปรับแต่งระยะขอบเมื่อแสดงผลเอกสาร HTML ใน .NET โดยใช้ GroupDocs.Viewer ช่วยให้นักพัฒนาปรับแต่งการนำเสนอเนื้อหาได้อย่างแม่นยำ ด้วยการทำตามบทช่วยสอนนี้ คุณสามารถปรับระยะขอบสำหรับรูปแบบเอาต์พุต JPG, PNG หรือ PDF ได้อย่างง่ายดาย ทำให้เอกสารของคุณดูสวยงามและอ่านง่ายขึ้น
## คำถามที่พบบ่อย
### GroupDocs.Viewer สำหรับ .NET เข้ากันได้กับรูปแบบ HTML ต่างๆ หรือไม่
GroupDocs.Viewer รองรับรูปแบบ HTML หลากหลาย เพื่อให้แน่ใจว่าเข้ากันได้กับเอกสาร HTML ต่างๆ
### ฉันสามารถปรับระยะขอบแบบไดนามิกตามเนื้อหาของเอกสารได้หรือไม่
ใช่ คุณสามารถปรับระยะขอบตามคุณสมบัติของเอกสารหรือโครงร่างการใช้งานของผู้ใช้ได้ด้วยการเขียนโปรแกรม
### มีข้อจำกัดใด ๆ ในการปรับระยะขอบหรือไม่?
GroupDocs.Viewer ให้ความยืดหยุ่นในการปรับระยะขอบ ช่วยให้ปรับแต่งได้ภายในขีดจำกัดที่เหมาะสม
### GroupDocs.Viewer รองรับรูปแบบเอาต์พุตอื่นนอกเหนือจาก JPG, PNG และ PDF หรือไม่
ใช่ GroupDocs.Viewer รองรับการเรนเดอร์เป็นรูปแบบต่างๆ รวมถึง TIFF, SVG และอื่นๆ อีกมากมาย
### ฉันจะขอความช่วยเหลือเพิ่มเติมหรือรายงานปัญหาที่เกี่ยวข้องกับ GroupDocs.Viewer ได้อย่างไร
คุณสามารถเยี่ยมชมฟอรั่ม GroupDocs.Viewer ได้ [ที่นี่](https://forum.groupdocs.com/c/viewer/9) เพื่อการสนับสนุนและการหารือ