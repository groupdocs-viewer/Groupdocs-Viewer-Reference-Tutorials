---
"description": "สำรวจการแปลงไฟล์ข้อความเป็นรูปแบบต่างๆ ได้อย่างราบรื่นโดยใช้ GroupDocs.Viewer สำหรับ .NET ปรับปรุงความสามารถในการจัดการเอกสารของคุณได้อย่างง่ายดาย"
"linktitle": "เรนเดอร์ไฟล์ข้อความ (.txt)"
"second_title": "API ของ GroupDocs.Viewer .NET"
"title": "เรนเดอร์ไฟล์ข้อความ (.txt)"
"url": "/th/net/rendering-text-files/render-txt/"
"weight": 10
type: docs
---
# เรนเดอร์ไฟล์ข้อความ (.txt)

## การแนะนำ
GroupDocs.Viewer สำหรับ .NET เป็นเครื่องมือที่มีประสิทธิภาพในการจัดการและจัดการเอกสาร โดยมีฟังก์ชันมากมายสำหรับการแสดงเอกสารในรูปแบบต่างๆ อย่างมีประสิทธิภาพ บทความนี้จะเจาะลึกถึงความซับซ้อนของการใช้ GroupDocs.Viewer สำหรับ .NET เพื่อแสดงไฟล์ข้อความ (.txt) เป็นรูปแบบต่างๆ ไม่ว่าคุณจะต้องการแปลงไฟล์ข้อความเป็น HTML, JPG, PNG หรือ PDF GroupDocs.Viewer จะช่วยให้คุณมีเครื่องมือที่จำเป็นในการทำงานเหล่านี้ได้อย่างราบรื่น
## ข้อกำหนดเบื้องต้น
ก่อนจะเริ่มกระบวนการแปลง ให้แน่ใจว่าคุณมีข้อกำหนดเบื้องต้นดังต่อไปนี้:
### 1. การติดตั้ง GroupDocs.Viewer สำหรับ .NET
ตรวจสอบให้แน่ใจว่าคุณได้ติดตั้ง GroupDocs.Viewer สำหรับ .NET ไว้ในสภาพแวดล้อมการพัฒนาของคุณแล้ว คุณสามารถดาวน์โหลดไฟล์ที่จำเป็นได้จาก [เว็บไซต์](https://releases-groupdocs.com/viewer/net/).
### 2. ความคุ้นเคยเบื้องต้นกับ .NET Framework
ทำความคุ้นเคยกับหลักพื้นฐานของ .NET framework รวมถึงวิธีการตั้งค่าโครงการและใช้งานไลบรารีภายในฐานโค้ดของคุณ
### 3. ไฟล์ข้อความตัวอย่าง
เตรียมไฟล์ข้อความตัวอย่าง (.txt) ที่คุณต้องการแปลง ไฟล์เหล่านี้จะทำหน้าที่เป็นอินพุตสำหรับกระบวนการแปลง

## นำเข้าเนมสเปซ
ก่อนจะเริ่มกระบวนการแปลง โปรดตรวจสอบให้แน่ใจว่าคุณได้นำเข้าเนมสเปซที่จำเป็นลงในโปรเจ็กต์ของคุณเสียก่อน วิธีนี้จะช่วยให้คุณเข้าถึงฟังก์ชันต่างๆ ที่ GroupDocs.Viewer สำหรับ .NET จัดเตรียมไว้ได้อย่างราบรื่น
```csharp
using System;
using System.Collections.Generic;
using System.Text;
using System.IO;
using GroupDocs.Viewer.Options;
string outputDirectory = "Your Document Directory";
```
ให้เราแบ่งตัวอย่างแต่ละตัวอย่างออกเป็นหลายขั้นตอนเพื่อช่วยคุณตลอดกระบวนการแปลงอย่างมีประสิทธิภาพ:

## ขั้นตอนที่ 1: กำหนดเส้นทางผลลัพธ์ HTML
```csharp
string pageFileFullPath = Path.Combine(outputDirectory, "Txt_result.html");
```
ระบุเส้นทางแบบเต็มสำหรับไฟล์เอาท์พุต HTML
## ขั้นตอนที่ 2: เรนเดอร์ไฟล์ข้อความเป็น HTML หลายหน้า
```csharp
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_TXT))
{
    HtmlViewOptions options = HtmlViewOptions.ForEmbeddedResources(pageFileFullPath);
    viewer.View(options);
}
```
สร้างตัวอย่าง `Viewer` วัตถุที่มีเส้นทางไปยังไฟล์ข้อความ กำหนดค่า `HtmlViewOptions` สำหรับทรัพยากรที่ฝังไว้และแสดงไฟล์ข้อความเป็น HTML หลายหน้า
## ขั้นตอนที่ 3: กำหนดเส้นทางเอาต์พุต HTML แบบหน้าเดียว
```csharp
pageFileFullPath = Path.Combine(outputDirectory, "Txt_result_single_page.html");
```
ระบุเส้นทางแบบเต็มสำหรับไฟล์เอาต์พุต HTML หน้าเดียว
## ขั้นตอนที่ 4: เรนเดอร์ไฟล์ข้อความเป็น HTML หน้าเดียว
```csharp
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_2_TXT))
{
    HtmlViewOptions options = HtmlViewOptions.ForEmbeddedResources(pageFileFullPath);
    options.RenderToSinglePage = true;
    viewer.View(options);
}
```
สร้างตัวอย่าง `Viewer` วัตถุที่มีเส้นทางไปยังไฟล์ข้อความ กำหนดค่า `HtmlViewOptions` สำหรับทรัพยากรที่ฝังตัวและตั้งค่า `RenderToSinglePage` เป็นจริง แสดงไฟล์ข้อความเป็น HTML แบบหน้าเดียว
## ขั้นตอนที่ 5: กำหนดเส้นทางเอาท์พุต JPG
```csharp
pageFileFullPath = Path.Combine(outputDirectory, "Txt_result.jpg");
```
ระบุเส้นทางแบบเต็มสำหรับไฟล์เอาต์พุต JPG
## ขั้นตอนที่ 6: เรนเดอร์ไฟล์ข้อความเป็น JPG
```csharp
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_TXT))
{
    JpgViewOptions options = new JpgViewOptions(pageFileFullPath);
    viewer.View(options);
}
```
สร้างตัวอย่าง `Viewer` วัตถุที่มีเส้นทางไปยังไฟล์ข้อความ กำหนดค่า `JpgViewOptions` สำหรับเส้นทางเอาต์พุตและเรนเดอร์ไฟล์ข้อความเป็นรูปแบบ JPG
## ขั้นตอนที่ 7: กำหนดเส้นทางเอาท์พุต PNG
```csharp
pageFileFullPath = Path.Combine(outputDirectory, "Txt_result.png");
```
ระบุเส้นทางแบบเต็มสำหรับไฟล์เอาต์พุต PNG
## ขั้นตอนที่ 8: เรนเดอร์ไฟล์ข้อความเป็น PNG
```csharp
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_TXT))
{
    PngViewOptions options = new PngViewOptions(pageFileFullPath);
    viewer.View(options);
}
```
สร้างตัวอย่าง `Viewer` วัตถุที่มีเส้นทางไปยังไฟล์ข้อความ กำหนดค่า `PngViewOptions` สำหรับเส้นทางเอาต์พุตและเรนเดอร์ไฟล์ข้อความเป็นรูปแบบ PNG
## ขั้นตอนที่ 9: กำหนดเส้นทางเอาต์พุต PDF
```csharp
pageFileFullPath = Path.Combine(outputDirectory, "Txt_result.pdf");
```
ระบุเส้นทางแบบเต็มสำหรับไฟล์เอาท์พุต PDF
## ขั้นตอนที่ 10: เรนเดอร์ไฟล์ข้อความเป็น PDF
```csharp
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_TXT))
{
    PdfViewOptions options = new PdfViewOptions(pageFileFullPath);
    viewer.View(options);
}
```
สร้างตัวอย่าง `Viewer` วัตถุที่มีเส้นทางไปยังไฟล์ข้อความ กำหนดค่า `PdfViewOptions` สำหรับเส้นทางเอาต์พุตและเรนเดอร์ไฟล์ข้อความเป็นรูปแบบ PDF

## บทสรุป
โดยสรุป GroupDocs.Viewer สำหรับ .NET ช่วยให้นักพัฒนาสามารถแสดงไฟล์ข้อความเป็นรูปแบบต่างๆ ได้อย่างง่ายดาย เช่น HTML, JPG, PNG และ PDF หากปฏิบัติตามคำแนะนำทีละขั้นตอนที่ระบุไว้ในบทความนี้ คุณจะสามารถผสานรวม GroupDocs.Viewer เข้ากับแอปพลิเคชัน .NET ได้อย่างราบรื่น ซึ่งจะช่วยเพิ่มประสิทธิภาพในการจัดการเอกสาร
## คำถามที่พบบ่อย
### ถาม: GroupDocs.Viewer สำหรับ .NET เข้ากันได้กับ .NET framework ทุกเวอร์ชันหรือไม่
ใช่ GroupDocs.Viewer สำหรับ .NET ได้รับการออกแบบมาให้มีความเข้ากันได้กับ .NET framework เวอร์ชันต่างๆ มากมาย ช่วยให้เกิดความหลากหลายและความยืดหยุ่นในการพัฒนา
### ถาม: ฉันสามารถปรับแต่งลักษณะการแสดงผลของเอกสารได้หรือไม่
แน่นอน! GroupDocs.Viewer มีตัวเลือกการปรับแต่งมากมาย ช่วยให้ผู้พัฒนาสามารถปรับแต่งลักษณะของเอกสารที่แสดงผลตามรูปแบบการสอนและความต้องการของตนเองได้
### ถาม: มีเวอร์ชันทดลองใช้สำหรับ GroupDocs.Viewer สำหรับ .NET หรือไม่
ใช่ คุณสามารถสำรวจฟังก์ชันการทำงานของ GroupDocs.Viewer สำหรับ .NET ได้โดยเข้าถึงรุ่นทดลองใช้งานฟรีที่มีให้ใน [เว็บไซต์]( https://releases-groupdocs.com/).
### ถาม: ฉันจะรับการสนับสนุนหรือขอความช่วยเหลือเกี่ยวกับ GroupDocs.Viewer สำหรับ .NET ได้อย่างไร
หากต้องการสอบถาม การสนับสนุน หรือความช่วยเหลือเกี่ยวกับ GroupDocs.Viewer สำหรับ .NET คุณสามารถเข้าไปที่ฟอรัมสนับสนุนเฉพาะที่สามารถเข้าถึงได้ [ที่นี่](https://forum-groupdocs.com/c/viewer/9).
### ถาม: ฉันสามารถซื้อใบอนุญาตชั่วคราวสำหรับ GroupDocs.Viewer สำหรับ .NET ได้หรือไม่
ใช่ ใบอนุญาตชั่วคราวมีจำหน่ายสำหรับการซื้อ ซึ่งจะให้ผู้ใช้มีความยืดหยุ่นและสะดวกในการใช้ GroupDocs.Viewer สำหรับ .NET ในระยะเวลาที่กำหนด