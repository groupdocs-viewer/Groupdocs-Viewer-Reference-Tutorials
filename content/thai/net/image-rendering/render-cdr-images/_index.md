---
title: เรนเดอร์รูปภาพ CDR
linktitle: เรนเดอร์รูปภาพ CDR
second_title: GroupDocs.Viewer .NET API
description: เรียนรู้วิธีเรนเดอร์รูปภาพ CDR เป็น HTML, JPG, PNG และ PDF โดยใช้ GroupDocs.Viewer สำหรับ .NET แปลงไฟล์ CorelDRAW ได้อย่างง่ายดายด้วยบทช่วยสอนนี้
type: docs
weight: 12
url: /th/net/image-rendering/render-cdr-images/
---
## การแนะนำ
ในบทช่วยสอนนี้ เราจะแนะนำคุณตลอดกระบวนการเรนเดอร์อิมเมจ CDR (CorelDRAW) โดยใช้ GroupDocs.Viewer สำหรับ .NET CDR เป็นรูปแบบไฟล์ที่เกี่ยวข้องกับ CorelDRAW ซึ่งเป็นโปรแกรมแก้ไขกราฟิกแบบเวกเตอร์เป็นหลัก ด้วย GroupDocs.Viewer คุณสามารถแปลงไฟล์ CDR เป็นรูปแบบต่างๆ เช่น HTML, JPG, PNG และ PDF ได้อย่างง่ายดาย
## ข้อกำหนดเบื้องต้น
ก่อนที่คุณจะเริ่มต้น ตรวจสอบให้แน่ใจว่าคุณมีข้อกำหนดเบื้องต้นต่อไปนี้:
1.  GroupDocs.Viewer สำหรับ .NET: ตรวจสอบให้แน่ใจว่าคุณได้ติดตั้ง GroupDocs.Viewer สำหรับ .NET แล้ว คุณสามารถดาวน์โหลดได้จาก[ที่นี่](https://releases.groupdocs.com/viewer/net/).
2. ไดเร็กทอรีเอกสาร: เตรียมไดเร็กทอรีที่คุณต้องการบันทึกภาพที่เรนเดอร์
3. ความรู้พื้นฐานของ C#: ความคุ้นเคยกับภาษาการเขียนโปรแกรม C# เป็นสิ่งจำเป็นในการทำความเข้าใจตัวอย่างโค้ด
## นำเข้าเนมสเปซ
ก่อนที่จะเจาะลึกตัวอย่างโค้ด ให้นำเข้าเนมสเปซที่จำเป็นในไฟล์ C# ของคุณ:
```csharp
using GroupDocs.Viewer.Options;
using System;
using System.IO;
```
ตอนนี้ เราจะแบ่งแต่ละตัวอย่างออกเป็นหลายขั้นตอน:
## แสดงผลเป็น HTML
1. กำหนดไดเร็กทอรีเอาต์พุตที่คุณต้องการบันทึกไฟล์ HTML ที่แสดงผล:
```csharp
string outputDirectory = "Your Document Directory";
```
2. ระบุรูปแบบเส้นทางไฟล์สำหรับไฟล์ HTML:
```csharp
string pageFilePathFormat = Path.Combine(outputDirectory, "cdr_result_{0}.html");
```
3. ใช้คลาส Viewer เพื่อแสดงไฟล์ CDR เป็น HTML:
```csharp
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_CDR))
{
    HtmlViewOptions options = HtmlViewOptions.ForEmbeddedResources(pageFilePathFormat);
    
    viewer.View(options);
}
```
## แสดงผลเป็น JPG
1. กำหนดรูปแบบเส้นทางไฟล์สำหรับไฟล์ JPG:
```csharp
pageFilePathFormat = Path.Combine(outputDirectory, "cdr_result_{0}.jpg");
```
2. ใช้คลาส Viewer เพื่อแสดงไฟล์ CDR เป็น JPG:
```csharp
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_CDR))
{
    JpgViewOptions options = new JpgViewOptions(pageFilePathFormat);
    
    viewer.View(options);
}
```
## แสดงผลเป็น PNG
1. กำหนดรูปแบบเส้นทางไฟล์สำหรับไฟล์ PNG:
```csharp
pageFilePathFormat = Path.Combine(outputDirectory, "cdr_result_{0}.png");
```
2. ใช้คลาส Viewer เพื่อแสดงไฟล์ CDR เป็น PNG:
```csharp
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_CDR))
{
    PngViewOptions options = new PngViewOptions(pageFilePathFormat);
    
    viewer.View(options);
}
```
## แสดงผลเป็น PDF
1. กำหนดรูปแบบเส้นทางไฟล์สำหรับ PDF:
```csharp
pageFilePathFormat = Path.Combine(outputDirectory, "cdr_result.pdf");
```
2. ใช้คลาส Viewer เพื่อเรนเดอร์ไฟล์ CDR เป็น PDF:
```csharp
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_CDR))
{
    PdfViewOptions options = new PdfViewOptions(pageFilePathFormat);
    
    viewer.View(options);
}
```
3.  อีกทางเลือกหนึ่ง คุณสามารถระบุตัวเลือกการแสดงผลหรือแสดงผลเพจเฉพาะโดยส่งพารามิเตอร์เพิ่มเติมไปที่`viewer.View()` วิธี.
## บทสรุป
การแสดงภาพ CDR เป็นรูปแบบต่างๆ เช่น HTML, JPG, PNG และ PDF โดยใช้ GroupDocs.Viewer สำหรับ .NET เป็นกระบวนการที่ไม่ซับซ้อน ด้วยการทำตามขั้นตอนที่อธิบายไว้ในบทช่วยสอนนี้ คุณสามารถแปลงไฟล์ CDR เป็นรูปแบบต่างๆ ตามความต้องการของคุณได้อย่างมีประสิทธิภาพ
## คำถามที่พบบ่อย
### GroupDocs.Viewer สำหรับ .NET เข้ากันได้กับไฟล์ CDR ทุกเวอร์ชันหรือไม่
GroupDocs.Viewer สำหรับ .NET รองรับการเรนเดอร์ไฟล์ CDR ที่สร้างโดย CorelDRAW เวอร์ชันต่างๆ
### ฉันสามารถปรับแต่งเอาต์พุตของไฟล์ที่เรนเดอร์ได้หรือไม่
ใช่ GroupDocs.Viewer สำหรับ .NET มีตัวเลือกมากมายในการปรับแต่งผลลัพธ์ เช่น การปรับคุณภาพของภาพ การตั้งค่าลายน้ำ ฯลฯ
### GroupDocs.Viewer สำหรับ .NET จำเป็นต้องมีการอ้างอิงภายนอกหรือไม่
ไม่ GroupDocs.Viewer สำหรับ .NET เป็นไลบรารีแบบสแตนด์อโลน และไม่จำเป็นต้องอาศัยการพึ่งพาภายนอกใดๆ ในการแสดงเอกสาร
### มีรุ่นทดลองใช้สำหรับ GroupDocs.Viewer สำหรับ .NET หรือไม่
 ใช่ คุณสามารถดาวน์โหลด GroupDocs.Viewer สำหรับ .NET เวอร์ชันทดลองใช้ฟรีได้จาก[ที่นี่](https://releases.groupdocs.com/).
### ฉันจะรับการสนับสนุนสำหรับ GroupDocs.Viewer สำหรับ .NET ได้ที่ไหน
 คุณสามารถรับการสนับสนุนจากฟอรัมชุมชน GroupDocs.Viewer[ที่นี่](https://forum.groupdocs.com/c/viewer/9).