---
"description": "เรียนรู้วิธีการเรนเดอร์ภาพ CDR เป็น HTML, JPG, PNG และ PDF โดยใช้ GroupDocs.Viewer สำหรับ .NET แปลงไฟล์ CorelDRAW ได้อย่างง่ายดายด้วยบทช่วยสอนนี้"
"linktitle": "เรนเดอร์ภาพ CDR"
"second_title": "API ของ GroupDocs.Viewer .NET"
"title": "เรนเดอร์ภาพ CDR"
"url": "/th/net/image-rendering/render-cdr-images/"
"weight": 12
---

# เรนเดอร์ภาพ CDR

## การแนะนำ
ในบทช่วยสอนนี้ เราจะแนะนำคุณเกี่ยวกับกระบวนการเรนเดอร์ภาพ CDR (CorelDRAW) โดยใช้ GroupDocs.Viewer สำหรับ .NET CDR เป็นรูปแบบไฟล์ที่เชื่อมโยงกับ CorelDRAW เป็นหลัก ซึ่งเป็นโปรแกรมแก้ไขกราฟิกแบบเวกเตอร์ ด้วย GroupDocs.Viewer คุณสามารถแปลงไฟล์ CDR เป็นรูปแบบต่างๆ เช่น HTML, JPG, PNG และ PDF ได้อย่างง่ายดาย

![เรนเดอร์ภาพ CDR ด้วย GroupDocs.Viewer สำหรับ .NET](/viewer/image-rendering/render-cdr-images.png)

## ข้อกำหนดเบื้องต้น
ก่อนที่คุณจะเริ่มต้น ให้แน่ใจว่าคุณมีข้อกำหนดเบื้องต้นดังต่อไปนี้:
1. GroupDocs.Viewer สำหรับ .NET: ตรวจสอบให้แน่ใจว่าคุณได้ติดตั้ง GroupDocs.Viewer สำหรับ .NET แล้ว คุณสามารถดาวน์โหลดได้จาก [ที่นี่](https://releases-groupdocs.com/viewer/net/).
2. ไดเรกทอรีเอกสาร: เตรียมไดเรกทอรีที่คุณต้องการบันทึกรูปภาพที่เรนเดอร์
3. ความรู้พื้นฐานเกี่ยวกับ C#: ความคุ้นเคยกับภาษาการเขียนโปรแกรม C# เป็นสิ่งจำเป็นสำหรับการทำความเข้าใจตัวอย่างโค้ด
## นำเข้าเนมสเปซ
ก่อนจะดำดิ่งไปในตัวอย่างโค้ด ให้ทำการนำเข้าเนมสเปซที่จำเป็นลงในไฟล์ C# ของคุณ:
```csharp
using GroupDocs.Viewer.Options;
using System;
using System.IO;
```
ตอนนี้เรามาแบ่งตัวอย่างแต่ละตัวอย่างออกเป็นหลายขั้นตอน:
## การเรนเดอร์เป็น HTML
1. กำหนดไดเร็กทอรีเอาท์พุตที่คุณต้องการบันทึกไฟล์ HTML ที่แสดง:
```csharp
string outputDirectory = "Your Document Directory";
```
2. ระบุรูปแบบเส้นทางไฟล์สำหรับไฟล์ HTML:
```csharp
string pageFilePathFormat = Path.Combine(outputDirectory, "cdr_result_{0}.html");
```
3. ใช้คลาส Viewer เพื่อเรนเดอร์ไฟล์ CDR เป็น HTML:
```csharp
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_CDR))
{
    HtmlViewOptions options = HtmlViewOptions.ForEmbeddedResources(pageFilePathFormat);
    
    viewer.View(options);
}
```
## การเรนเดอร์เป็น JPG
1. กำหนดรูปแบบเส้นทางไฟล์สำหรับไฟล์ JPG:
```csharp
pageFilePathFormat = Path.Combine(outputDirectory, "cdr_result_{0}.jpg");
```
2. ใช้คลาส Viewer เพื่อเรนเดอร์ไฟล์ CDR เป็น JPG:
```csharp
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_CDR))
{
    JpgViewOptions options = new JpgViewOptions(pageFilePathFormat);
    
    viewer.View(options);
}
```
## การเรนเดอร์เป็น PNG
1. กำหนดรูปแบบเส้นทางไฟล์สำหรับไฟล์ PNG:
```csharp
pageFilePathFormat = Path.Combine(outputDirectory, "cdr_result_{0}.png");
```
2. ใช้คลาส Viewer เพื่อเรนเดอร์ไฟล์ CDR เป็น PNG:
```csharp
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_CDR))
{
    PngViewOptions options = new PngViewOptions(pageFilePathFormat);
    
    viewer.View(options);
}
```
## การเรนเดอร์เป็น PDF
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
3. นอกจากนี้ คุณยังสามารถระบุตัวเลือกการแสดงผลหรือแสดงผลหน้าเฉพาะได้โดยส่งพารามิเตอร์เพิ่มเติมให้กับ `viewer.View()` วิธี.
## บทสรุป
การเรนเดอร์ภาพ CDR เป็นรูปแบบต่างๆ เช่น HTML, JPG, PNG และ PDF โดยใช้ GroupDocs.Viewer สำหรับ .NET เป็นกระบวนการที่ตรงไปตรงมา เพียงทำตามขั้นตอนที่ระบุไว้ในบทช่วยสอนนี้ คุณจะสามารถแปลงไฟล์ CDR เป็นรูปแบบต่างๆ ตามความต้องการของคุณได้อย่างมีประสิทธิภาพ
## คำถามที่พบบ่อย
### GroupDocs.Viewer สำหรับ .NET เข้ากันได้กับไฟล์ CDR ทุกเวอร์ชันหรือไม่
GroupDocs.Viewer สำหรับ .NET รองรับการเรนเดอร์ไฟล์ CDR ที่สร้างโดย CorelDRAW เวอร์ชันต่างๆ
### ฉันสามารถปรับแต่งเอาท์พุตของไฟล์ที่เรนเดอร์ได้หรือไม่
ใช่ GroupDocs.Viewer สำหรับ .NET มีตัวเลือกต่าง ๆ เพื่อปรับแต่งเอาต์พุต เช่น การปรับคุณภาพของรูปภาพ การตั้งค่าลายน้ำ ฯลฯ
### GroupDocs.Viewer สำหรับ .NET ต้องมีการอ้างอิงภายนอกใด ๆ หรือไม่
ไม่ GroupDocs.Viewer สำหรับ .NET เป็นไลบรารีแบบสแตนด์อโลนและไม่จำเป็นต้องมีการอ้างอิงภายนอกใดๆ ในการแสดงผลเอกสาร
### มีเวอร์ชันทดลองใช้สำหรับ GroupDocs.Viewer สำหรับ .NET หรือไม่
ใช่ คุณสามารถดาวน์โหลด GroupDocs.Viewer รุ่นทดลองใช้งานฟรีสำหรับ .NET ได้จาก [ที่นี่](https://releases-groupdocs.com/).
### ฉันจะได้รับการสนับสนุนสำหรับ GroupDocs.Viewer สำหรับ .NET ได้จากที่ไหน
คุณสามารถรับการสนับสนุนจากฟอรัมชุมชน GroupDocs.Viewer ได้ [ที่นี่](https://forum-groupdocs.com/c/viewer/9).