---
"description": "เรียนรู้วิธีการปรับคุณภาพของภาพในเอกสาร PDF โดยใช้ GroupDocs.Viewer สำหรับ .NET ปฏิบัติตามบทช่วยสอนทีละขั้นตอนของเราเพื่อการผสานรวมที่ราบรื่น"
"linktitle": "ปรับคุณภาพรูปภาพใน PDF"
"second_title": "API ของ GroupDocs.Viewer .NET"
"title": "ปรับคุณภาพรูปภาพใน PDF"
"url": "/th/net/pdf-rendering-options/adjust-image-quality-pdf/"
"weight": 10
---

# ปรับคุณภาพรูปภาพใน PDF

## การแนะนำ
GroupDocs.Viewer สำหรับ .NET เป็นไลบรารีอันทรงพลังที่ช่วยให้นักพัฒนาสามารถผสานรวมความสามารถในการแสดงผลเอกสารลงในแอปพลิเคชัน .NET ได้อย่างง่ายดาย หนึ่งในฟีเจอร์หลักของไลบรารีนี้คือความสามารถในการปรับคุณภาพของรูปภาพเมื่อแสดงผลเอกสาร PDF ในบทช่วยสอนนี้ เราจะแนะนำคุณเกี่ยวกับขั้นตอนการปรับคุณภาพของรูปภาพทีละขั้นตอนโดยใช้ GroupDocs.Viewer สำหรับ .NET

![ปรับคุณภาพรูปภาพใน PDF ด้วย GroupDocs.Viewer .NET](/viewer/pdf-rendering-options/adjust-image-quality-in-pdf.png)

## ข้อกำหนดเบื้องต้น
ก่อนที่เราจะเริ่มต้น ให้แน่ใจว่าคุณมีข้อกำหนดเบื้องต้นดังต่อไปนี้:
1. ความรู้พื้นฐานในการเขียนโปรแกรม C#
2. Visual Studio ติดตั้งอยู่บนระบบของคุณแล้ว
3. ดาวน์โหลดและติดตั้งไลบรารี GroupDocs.Viewer สำหรับ .NET คุณสามารถดาวน์โหลดได้จาก [ที่นี่](https://releases-groupdocs.com/viewer/net/).

## นำเข้าเนมสเปซ
ขั้นแรก คุณต้องนำเข้าเนมสเปซที่จำเป็นสำหรับการทำงานกับ GroupDocs.Viewer สำหรับ .NET:
```csharp
using System;
using System.IO;
using GroupDocs.Viewer.Options;
```
## ขั้นตอนที่ 1: กำหนดไดเรกทอรีผลลัพธ์
```csharp
string outputDirectory = "Your Document Directory";
```
แทนที่ `"Your Document Directory"` ด้วยเส้นทางที่คุณต้องการบันทึกหน้า HTML ที่แสดง
## ขั้นตอนที่ 2: กำหนดรูปแบบเส้นทางไฟล์เพจ
```csharp
string pageFilePathFormat = Path.Combine(outputDirectory, "page_{0}.html");
```
บรรทัดนี้กำหนดรูปแบบสำหรับเส้นทางไฟล์ของแต่ละหน้า HTML ที่แสดงผล `{0}` เป็นตัวแทนสำหรับหมายเลขหน้า
## ขั้นตอนที่ 3: ปรับคุณภาพของภาพ
```csharp
using (Viewer viewer = new Viewer("Your PDF File Path"))
{
    HtmlViewOptions options = HtmlViewOptions.ForEmbeddedResources(pageFilePathFormat);
    options.PdfOptions.ImageQuality = ImageQuality.Medium;
    viewer.View(options);
}
```
แทนที่ `"Your PDF File Path"` พร้อมเส้นทางไปยังเอกสาร PDF ของคุณ
## ขั้นตอนที่ 4: แสดงเส้นทางผลลัพธ์
```csharp
Console.WriteLine($"\nSource document rendered successfully.\nCheck output in {outputDirectory}.");
```
บรรทัดนี้จะแสดงเส้นทางที่บันทึกหน้า HTML ที่แสดงผล

## บทสรุป
ในบทช่วยสอนนี้ เราได้เรียนรู้วิธีการปรับคุณภาพของภาพเมื่อเรนเดอร์เอกสาร PDF โดยใช้ GroupDocs.Viewer สำหรับ .NET โดยทำตามขั้นตอนง่ายๆ ที่ระบุไว้ข้างต้น คุณสามารถปรับแต่งคุณภาพของภาพตามความต้องการของคุณได้อย่างง่ายดาย
## คำถามที่พบบ่อย
### ฉันสามารถปรับคุณภาพของภาพสำหรับรูปแบบเอกสารอื่นนอกเหนือจาก PDF ได้หรือไม่
ใช่ GroupDocs.Viewer สำหรับ .NET รองรับรูปแบบเอกสารต่างๆ และคุณสามารถปรับคุณภาพของภาพสำหรับเอกสารส่วนใหญ่ได้
### ตัวเลือกคุณภาพของภาพที่มีอยู่มีอะไรบ้าง?
GroupDocs.Viewer สำหรับ .NET มีตัวเลือกสำหรับคุณภาพรูปภาพ ต่ำ กลาง และสูง
### มีวิธีดูตัวอย่างเอกสารก่อนเรนเดอร์ด้วยคุณภาพของรูปภาพที่ปรับแล้วหรือไม่
ใช่ คุณสามารถใช้ GroupDocs.Viewer สำหรับ .NET เพื่อสร้างตัวอย่างเอกสารด้วยการตั้งค่าคุณภาพรูปภาพที่แตกต่างกันได้
### GroupDocs.Viewer สำหรับ .NET ต้องมีใบอนุญาตสำหรับการใช้งานเชิงพาณิชย์หรือไม่
ใช่ คุณต้องได้รับใบอนุญาตสำหรับการใช้งานเชิงพาณิชย์ คุณสามารถซื้อใบอนุญาตได้จาก [ที่นี่](https://purchase-groupdocs.com/buy).
### ฉันจะได้รับการสนับสนุนสำหรับ GroupDocs.Viewer สำหรับ .NET ได้จากที่ไหน
คุณสามารถรับการสนับสนุนจากฟอรัม GroupDocs.Viewer ได้ [ที่นี่](https://forum-groupdocs.com/c/viewer/9).