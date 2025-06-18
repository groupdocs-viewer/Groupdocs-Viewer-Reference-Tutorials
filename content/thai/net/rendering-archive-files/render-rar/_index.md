---
"description": "เรียนรู้วิธีการเรนเดอร์ไฟล์เก็บถาวร RAR เป็นรูปแบบ HTML, JPG, PNG หรือ PDF โดยใช้ GroupDocs.Viewer สำหรับ .NET ดูและแบ่งปันเนื้อหาของไฟล์เก็บถาวร RAR ได้อย่างง่ายดาย"
"linktitle": "เรนเดอร์ไฟล์ RAR"
"second_title": "API ของ GroupDocs.Viewer .NET"
"title": "เรนเดอร์ไฟล์ RAR"
"url": "/th/net/rendering-archive-files/render-rar/"
"weight": 13
---

# เรนเดอร์ไฟล์ RAR

## การแนะนำ
ไฟล์เก็บถาวร RAR เป็นรูปแบบที่นิยมใช้สำหรับการบีบอัดและจัดเก็บไฟล์และโฟลเดอร์หลายไฟล์ในคอนเทนเนอร์เดียว การเรนเดอร์ไฟล์เก็บถาวร RAR เป็นรูปแบบต่างๆ เช่น HTML, JPG, PNG หรือ PDF อาจมีความจำเป็นสำหรับการดูหรือแชร์เนื้อหาของไฟล์เก็บถาวรเหล่านี้ ในบทช่วยสอนนี้ เราจะมาสำรวจวิธีการเรนเดอร์ไฟล์เก็บถาวร RAR โดยใช้ GroupDocs.Viewer สำหรับ .NET
## ข้อกำหนดเบื้องต้น
ก่อนที่เราจะเริ่มต้น ให้แน่ใจว่าคุณมีข้อกำหนดเบื้องต้นดังต่อไปนี้:
1. GroupDocs.Viewer สำหรับ .NET: ติดตั้งไลบรารี GroupDocs.Viewer สำหรับ .NET จาก [ลิงค์ดาวน์โหลด](https://releases-groupdocs.com/viewer/net/).
2. ตัวอย่างไฟล์ RAR Archive: เตรียมไฟล์ RAR ตัวอย่างให้พร้อมสำหรับการเรนเดอร์

## นำเข้าเนมสเปซ
```csharp
using GroupDocs.Viewer.Options;
using GroupDocs.Viewer.Results;
using System;
using System.IO;
```
## ขั้นตอนที่ 1: กำหนดไดเรกทอรีผลลัพธ์
```csharp
string outputDirectory = "Your Document Directory";
```
## ขั้นตอนที่ 2: เรนเดอร์เป็น HTML
```csharp
string pageFilePathFormat = Path.Combine(outputDirectory, "RAR_result_{0}.html");
using (Viewer viewer = new Viewer("YourRarFile.rar"))
{
    HtmlViewOptions options = HtmlViewOptions.ForEmbeddedResources(pageFilePathFormat);
    viewer.View(options);
}
```
## ขั้นตอนที่ 3: เรนเดอร์เป็น JPG
```csharp
string pageFilePathFormat = Path.Combine(outputDirectory, "RAR_result_{0}.jpg");
using (Viewer viewer = new Viewer("YourRarFile.rar"))
{
    JpgViewOptions options = new JpgViewOptions(pageFilePathFormat);
    viewer.View(options);
}
```
## ขั้นตอนที่ 4: เรนเดอร์เป็น PNG
```csharp
string pageFilePathFormat = Path.Combine(outputDirectory, "RAR_result_{0}.png");
using (Viewer viewer = new Viewer("YourRarFile.rar"))
{
    PngViewOptions options = new PngViewOptions(pageFilePathFormat);
    viewer.View(options);
}
```
## ขั้นตอนที่ 5: เรนเดอร์เป็น PDF
```csharp
string pageFilePathFormat = Path.Combine(outputDirectory, "RAR_result.pdf");
using (Viewer viewer = new Viewer("YourRarFile.rar"))
{
    PdfViewOptions options = new PdfViewOptions(pageFilePathFormat);
    viewer.View(options);
}
```

## บทสรุป
การเรนเดอร์ไฟล์เก็บถาวร RAR เป็นรูปแบบต่างๆ ทำได้ง่ายด้วย GroupDocs.Viewer สำหรับ .NET เมื่อทำตามขั้นตอนที่ระบุไว้ในบทช่วยสอนนี้แล้ว คุณจะสามารถแปลงไฟล์เก็บถาวร RAR เป็นรูปแบบ HTML, JPG, PNG หรือ PDF ได้อย่างง่ายดาย ทำให้สามารถดูและแชร์เนื้อหาได้อย่างง่ายดาย
## คำถามที่พบบ่อย
### GroupDocs.Viewer สำหรับ .NET สามารถจัดการกับไฟล์ RAR ที่เข้ารหัสได้หรือไม่
ใช่ GroupDocs.Viewer สำหรับ .NET รองรับการเรนเดอร์ไฟล์ RAR ที่เข้ารหัส โดยต้องระบุรหัสผ่านที่จำเป็นในระหว่างกระบวนการเรนเดอร์
### สามารถปรับแต่งลักษณะการแสดงผลของเอกสารได้หรือไม่
แน่นอน! GroupDocs.Viewer สำหรับ .NET นำเสนอตัวเลือกการปรับแต่งมากมาย ช่วยให้ผู้ใช้ปรับแต่งลักษณะของเอกสารที่แสดงผลตามความเหมาะสมของการใช้งาน
### GroupDocs.Viewer สำหรับ .NET รองรับการเรนเดอร์รูปแบบไฟล์เก็บถาวรอื่น ๆ นอกเหนือจาก RAR หรือไม่
ใช่ GroupDocs.Viewer สำหรับ .NET รองรับการเรนเดอร์รูปแบบไฟล์เก็บถาวรต่างๆ รวมถึง ZIP, TAR, 7z และอื่นๆ อีกมากมาย
### ฉันสามารถรวม GroupDocs.Viewer สำหรับ .NET เข้ากับแอปพลิเคชันเว็บของฉันได้หรือไม่
แน่นอน! GroupDocs.Viewer สำหรับ .NET นำเสนอ API ที่เหมาะสำหรับการรวมเข้าในแอพพลิเคชันเดสก์ท็อปและเว็บ
### มีเวอร์ชันทดลองใช้สำหรับ GroupDocs.Viewer สำหรับ .NET หรือไม่
ใช่ คุณสามารถใช้ประโยชน์จากการทดลองใช้ GroupDocs.Viewer สำหรับ .NET ได้ฟรีจาก [เว็บไซต์](https://releases-groupdocs.com/).