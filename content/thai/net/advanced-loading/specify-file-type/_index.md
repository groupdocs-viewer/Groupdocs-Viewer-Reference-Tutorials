---
title: ระบุประเภทไฟล์เมื่อโหลดเอกสาร
linktitle: ระบุประเภทไฟล์เมื่อโหลดเอกสาร
second_title: GroupDocs.Viewer .NET API
description: เรียนรู้วิธีระบุประเภทไฟล์เมื่อโหลดเอกสารโดยใช้ GroupDocs.Viewer สำหรับ .NET เรนเดอร์รูปแบบต่างๆ ได้อย่างแม่นยำในแอปพลิเคชัน .NET ของคุณ
type: docs
weight: 10
url: /th/net/advanced-loading/specify-file-type/
---
## การแนะนำ
GroupDocs.Viewer สำหรับ .NET เป็น API การแสดงผลเอกสารอเนกประสงค์ที่รองรับรูปแบบไฟล์ที่หลากหลาย รวมถึง DOCX, PDF, PPTX และอื่นๆ ด้วยการระบุประเภทไฟล์เมื่อโหลดเอกสาร คุณสามารถรับประกันการแสดงผลที่แม่นยำและประสบการณ์การรับชมที่ราบรื่นสำหรับผู้ใช้ของคุณ
## ข้อกำหนดเบื้องต้น
ก่อนที่คุณจะเริ่มต้น ตรวจสอบให้แน่ใจว่าคุณมีข้อกำหนดเบื้องต้นต่อไปนี้:
- ความรู้พื้นฐานเกี่ยวกับกรอบงาน C# และ .NET
- ติดตั้ง Visual Studio บนระบบของคุณแล้ว
- GroupDocs.Viewer สำหรับ .NET ติดตั้งในโครงการของคุณ คุณสามารถดาวน์โหลดได้จาก[ที่นี่](https://releases.groupdocs.com/viewer/net/).
##
## นำเข้าเนมสเปซ
ขั้นแรก คุณต้องนำเข้าเนมสเปซที่จำเป็นลงในโค้ด C# ของคุณ เนมสเปซเหล่านี้ให้การเข้าถึงคลาสและวิธีการที่จำเป็นสำหรับการแสดงผลเอกสาร
```csharp
using System;
using System.IO;
using GroupDocs.Viewer.Options;
```
## ขั้นตอนที่ 1: ตั้งค่าไดเรกทอรีผลลัพธ์
กำหนดไดเร็กทอรีที่คุณต้องการบันทึกหน้าเอกสารที่แสดงผล
```csharp
string outputDirectory = "Your Document Directory";
```
## ขั้นตอนที่ 2: กำหนดรูปแบบเส้นทางไฟล์เพจ
ระบุรูปแบบสำหรับการตั้งชื่อไฟล์ HTML เอาต์พุตสำหรับแต่ละหน้าของเอกสาร
```csharp
string pageFilePathFormat = Path.Combine(outputDirectory, "page_{0}.html");
```
## ขั้นตอนที่ 3: ระบุตัวเลือกการโหลด
 สร้างอินสแตนซ์ของ`LoadOptions` และกำหนดประเภทไฟล์ที่ต้องการ
```csharp
LoadOptions loadOptions = new LoadOptions
{
    FileType = FileType.DOCX
};
```
## ขั้นตอนที่ 4: โหลดเอกสารและแสดงผล
 ใช้`Viewer` คลาสเพื่อโหลดเอกสารและแสดงผลเป็นรูปแบบ HTML
```csharp
using (Viewer viewer = new Viewer("YourDocument.docx", loadOptions))
{
    HtmlViewOptions options = HtmlViewOptions.ForEmbeddedResources(pageFilePathFormat);
    viewer.View(options);
}
```
## ขั้นตอนที่ 5: แสดงข้อความแสดงความสำเร็จ
แจ้งให้ผู้ใช้ทราบว่าเอกสารแสดงผลสำเร็จแล้ว และระบุตำแหน่งของไฟล์เอาต์พุต
```csharp
Console.WriteLine($"\nSource document rendered successfully.\nCheck output in {outputDirectory}.");
```

## บทสรุป
ในบทช่วยสอนนี้ เราได้เรียนรู้วิธีใช้ GroupDocs.Viewer สำหรับ .NET เพื่อระบุประเภทไฟล์เมื่อโหลดเอกสาร ด้วยการทำตามขั้นตอนง่ายๆ เหล่านี้ คุณสามารถรับประกันการแสดงผลรูปแบบเอกสารต่างๆ ในแอปพลิเคชัน .NET ของคุณได้อย่างแม่นยำ
## คำถามที่พบบ่อย
### ฉันสามารถเรนเดอร์เอกสารอื่นที่ไม่ใช่ DOCX โดยใช้ GroupDocs.Viewer สำหรับ .NET ได้หรือไม่
ใช่ GroupDocs.Viewer รองรับรูปแบบไฟล์ที่หลากหลาย รวมถึง PDF, PPTX, XLSX และอื่นๆ
### GroupDocs.Viewer สำหรับ .NET เข้ากันได้กับ .NET Core หรือไม่
ใช่ GroupDocs.Viewer สำหรับ .NET เข้ากันได้กับทั้ง .NET Framework และ .NET Core
### ฉันสามารถปรับแต่งไฟล์ HTML เอาท์พุตที่สร้างโดย GroupDocs.Viewer ได้หรือไม่
ใช่ คุณสามารถปรับแต่งเอาต์พุต HTML ได้โดยใช้ตัวเลือกต่างๆ ที่ API ให้ไว้
### GroupDocs.Viewer สำหรับ .NET จำเป็นต้องมีการอ้างอิงภายนอกหรือไม่
ไม่ GroupDocs.Viewer สำหรับ .NET เป็นไลบรารีแบบสแตนด์อโลนและไม่จำเป็นต้องมีการพึ่งพาภายนอกใดๆ
### มีรุ่นทดลองใช้สำหรับ GroupDocs.Viewer สำหรับ .NET หรือไม่
ใช่ คุณสามารถดาวน์โหลดเวอร์ชันทดลองใช้ฟรีได้จาก[ที่นี่](https://releases.groupdocs.com/viewer/net/).