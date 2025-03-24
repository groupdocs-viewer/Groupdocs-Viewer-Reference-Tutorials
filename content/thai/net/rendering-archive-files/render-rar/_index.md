---
title: แสดงผลเอกสาร RAR
linktitle: แสดงผลเอกสาร RAR
second_title: GroupDocs.Viewer .NET API
description: เรียนรู้วิธีเรนเดอร์ไฟล์เก็บถาวร RAR เป็นรูปแบบ HTML, JPG, PNG หรือ PDF โดยใช้ GroupDocs.Viewer สำหรับ .NET ดูและแบ่งปันเนื้อหาของไฟล์เก็บถาวร RAR ได้อย่างง่ายดาย
weight: 13
url: /th/net/rendering-archive-files/render-rar/
---
## การแนะนำ
ไฟล์เก็บถาวร RAR เป็นรูปแบบยอดนิยมสำหรับการบีบอัดและจัดเก็บไฟล์และโฟลเดอร์หลาย ๆ ไฟล์ไว้ในคอนเทนเนอร์เดียว การแสดงผลไฟล์เก็บถาวร RAR ในรูปแบบต่าง ๆ เช่น HTML, JPG, PNG หรือ PDF อาจจำเป็นสำหรับการดูหรือแบ่งปันเนื้อหาของไฟล์เก็บถาวรเหล่านี้ ในบทช่วยสอนนี้ เราจะสำรวจวิธีเรนเดอร์ไฟล์เก็บถาวร RAR โดยใช้ GroupDocs.Viewer สำหรับ .NET
## ข้อกำหนดเบื้องต้น
ก่อนที่เราจะเริ่มต้น ตรวจสอบให้แน่ใจว่าคุณมีข้อกำหนดเบื้องต้นดังต่อไปนี้:
1. GroupDocs.Viewer สำหรับ .NET: ติดตั้งไลบรารี GroupDocs.Viewer สำหรับ .NET จาก[ลิ้งค์ดาวน์โหลด](https://releases.groupdocs.com/viewer/net/).
2. ไฟล์เก็บถาวร RAR ตัวอย่าง: เตรียมไฟล์เก็บถาวร RAR ตัวอย่างให้พร้อมสำหรับการเรนเดอร์

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
## ขั้นตอนที่ 2: แสดงผลเป็น HTML
```csharp
string pageFilePathFormat = Path.Combine(outputDirectory, "RAR_result_{0}.html");
using (Viewer viewer = new Viewer("YourRarFile.rar"))
{
    HtmlViewOptions options = HtmlViewOptions.ForEmbeddedResources(pageFilePathFormat);
    viewer.View(options);
}
```
## ขั้นตอนที่ 3: แสดงผลเป็น JPG
```csharp
string pageFilePathFormat = Path.Combine(outputDirectory, "RAR_result_{0}.jpg");
using (Viewer viewer = new Viewer("YourRarFile.rar"))
{
    JpgViewOptions options = new JpgViewOptions(pageFilePathFormat);
    viewer.View(options);
}
```
## ขั้นตอนที่ 4: แสดงผลเป็น PNG
```csharp
string pageFilePathFormat = Path.Combine(outputDirectory, "RAR_result_{0}.png");
using (Viewer viewer = new Viewer("YourRarFile.rar"))
{
    PngViewOptions options = new PngViewOptions(pageFilePathFormat);
    viewer.View(options);
}
```
## ขั้นตอนที่ 5: แสดงผลเป็น PDF
```csharp
string pageFilePathFormat = Path.Combine(outputDirectory, "RAR_result.pdf");
using (Viewer viewer = new Viewer("YourRarFile.rar"))
{
    PdfViewOptions options = new PdfViewOptions(pageFilePathFormat);
    viewer.View(options);
}
```

## บทสรุป
การเรนเดอร์ไฟล์เก็บถาวร RAR ในรูปแบบต่างๆ ทำได้ง่ายด้วย GroupDocs.Viewer สำหรับ .NET ด้วยการทำตามขั้นตอนที่อธิบายไว้ในบทช่วยสอนนี้ คุณสามารถแปลงไฟล์เก็บถาวร RAR เป็นรูปแบบ HTML, JPG, PNG หรือ PDF ได้อย่างง่ายดาย ทำให้สามารถดูและแบ่งปันเนื้อหาได้อย่างง่ายดาย
## คำถามที่พบบ่อย
### GroupDocs.Viewer สำหรับ .NET สามารถจัดการไฟล์ RAR ที่เข้ารหัสได้หรือไม่
ใช่ GroupDocs.Viewer สำหรับ .NET รองรับการเรนเดอร์ไฟล์เก็บถาวร RAR ที่เข้ารหัส โดยมีเงื่อนไขว่าต้องระบุรหัสผ่านที่จำเป็นในระหว่างกระบวนการเรนเดอร์
### เป็นไปได้หรือไม่ที่จะปรับแต่งลักษณะเอาต์พุตของเอกสารที่เรนเดอร์แล้ว?
อย่างแน่นอน! GroupDocs.Viewer สำหรับ .NET นำเสนอตัวเลือกการปรับแต่งที่ครอบคลุม ซึ่งช่วยให้ผู้ใช้ปรับแต่งรูปลักษณ์ของเอกสารที่เรนเดอร์ได้ตามความต้องการ
### GroupDocs.Viewer สำหรับ .NET รองรับการเรนเดอร์รูปแบบไฟล์เก็บถาวรอื่นนอกเหนือจาก RAR หรือไม่
ใช่ GroupDocs.Viewer สำหรับ .NET รองรับการเรนเดอร์รูปแบบไฟล์เก็บถาวรที่หลากหลาย รวมถึง ZIP, TAR, 7z และอื่นๆ
### ฉันสามารถรวม GroupDocs.Viewer สำหรับ .NET เข้ากับเว็บแอปพลิเคชันของฉันได้หรือไม่
แน่นอน! GroupDocs.Viewer สำหรับ .NET มี API ที่เหมาะสมสำหรับการรวมเข้ากับทั้งเดสก์ท็อปและเว็บแอปพลิเคชัน
### มีรุ่นทดลองใช้สำหรับ GroupDocs.Viewer สำหรับ .NET หรือไม่
 ใช่ คุณสามารถใช้ GroupDocs.Viewer สำหรับ .NET รุ่นทดลองใช้ฟรีได้จาก[เว็บไซต์](https://releases.groupdocs.com/).