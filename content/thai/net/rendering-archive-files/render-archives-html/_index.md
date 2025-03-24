---
title: เรนเดอร์ไฟล์เก็บถาวรเป็นหน้า HTML เดียวหรือหลายหน้า
linktitle: เรนเดอร์ไฟล์เก็บถาวรเป็นหน้า HTML เดียวหรือหลายหน้า
second_title: GroupDocs.Viewer .NET API
description: เรียนรู้วิธีการแสดงผลไฟล์เก็บถาวรไปยังหน้า HTML โดยใช้ GroupDocs.Viewer สำหรับ .NET ผสานรวมความสามารถในการดูเอกสารเข้ากับแอปพลิเคชัน .NET ของคุณได้อย่างง่ายดาย
weight: 12
url: /th/net/rendering-archive-files/render-archives-html/
---

# เรนเดอร์ไฟล์เก็บถาวรเป็นหน้า HTML เดียวหรือหลายหน้า

## การแนะนำ
GroupDocs.Viewer สำหรับ .NET เป็นไลบรารีการแสดงผลเอกสารที่มีประสิทธิภาพซึ่งช่วยให้นักพัฒนาสามารถรวมความสามารถในการดูเอกสารเข้ากับแอปพลิเคชัน .NET ของตนได้อย่างง่ายดาย ไม่ว่าคุณจะต้องแสดงไฟล์เก็บถาวรเป็นหน้า HTML เดียวหรือหลายหน้า บทช่วยสอนนี้จะแนะนำคุณตลอดกระบวนการทีละขั้นตอน
## ข้อกำหนดเบื้องต้น
ก่อนที่จะเข้าสู่บทช่วยสอนนี้ ตรวจสอบให้แน่ใจว่าคุณมีข้อกำหนดเบื้องต้นต่อไปนี้:
1.  GroupDocs.Viewer สำหรับ .NET: ตรวจสอบให้แน่ใจว่าคุณได้ติดตั้งไลบรารีในโครงการของคุณ คุณสามารถดาวน์โหลดได้จาก[ที่นี่](https://releases.groupdocs.com/viewer/net/).
2. สภาพแวดล้อมการพัฒนา: มีสภาพแวดล้อมการพัฒนาการทำงานที่ตั้งค่าไว้สำหรับการพัฒนา .NET
3. Document Directory: เตรียมไดเร็กทอรีสำหรับจัดเก็บเอกสารของคุณ
4. ความเข้าใจพื้นฐานของ C#: ทำความคุ้นเคยกับพื้นฐานภาษาการเขียนโปรแกรม C#

## นำเข้าเนมสเปซ
ในโค้ด C# ของคุณ ตรวจสอบให้แน่ใจว่าได้นำเข้าเนมสเปซที่จำเป็น:
```csharp
using GroupDocs.Viewer.Options;
using System;
using System.IO;
```

ทำตามขั้นตอนเหล่านี้เพื่อแสดงไฟล์เก็บถาวรไปยังหน้า HTML เดียวหรือหลายหน้าโดยใช้ GroupDocs.Viewer สำหรับ .NET:
## ขั้นตอนที่ 1: ตั้งค่าไดเรกทอรีผลลัพธ์
กำหนดไดเร็กทอรีที่คุณต้องการให้เพจ HTML ที่แสดงผลถูกบันทึก:
```csharp
string outputDirectory = "Your Document Directory";
```
## ขั้นตอนที่ 2: กำหนดรูปแบบเส้นทางไฟล์
ระบุรูปแบบเส้นทางไฟล์สำหรับหน้า HTML สำหรับการแสดงผลหน้าเดียว:
```csharp
string pageFilePathFormat = Path.Combine(outputDirectory, "RAR_result.html");
```
สำหรับการแสดงผลหลายหน้า:
```csharp
pageFilePathFormat = Path.Combine(outputDirectory, "RAR_result_page_{0}.html");
```
## ขั้นตอนที่ 3: แสดงผลเป็น HTML หน้าเดียว
```csharp
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_RAR_WITH_FOLDERS))
{
    HtmlViewOptions options = HtmlViewOptions.ForEmbeddedResources(pageFilePathFormat);
    options.RenderToSinglePage = true; 
    viewer.View(options);
}
```
## ขั้นตอนที่ 4: แสดงผลเป็น HTML หลายหน้า
```csharp
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_RAR_WITH_FOLDERS))
{
    HtmlViewOptions options = HtmlViewOptions.ForEmbeddedResources(pageFilePathFormat);
    options.ArchiveOptions.ItemsPerPage = 10; // ตั้งค่ารายการต่อหน้า
    viewer.View(options);
}
```
## ขั้นตอนที่ 5: ตรวจสอบผลลัพธ์
```csharp
Console.WriteLine($"\nSource document rendered successfully.\nCheck output in {outputDirectory}.");
```

## บทสรุป
การแสดงผลไฟล์เก็บถาวรไปยังหน้า HTML โดยใช้ GroupDocs.Viewer สำหรับ .NET เป็นกระบวนการที่ไม่ซับซ้อน ด้วยการทำตามขั้นตอนที่ระบุไว้ในบทช่วยสอนนี้ คุณสามารถรวมความสามารถในการดูเอกสารเข้ากับแอปพลิเคชัน .NET ของคุณได้อย่างราบรื่น
## คำถามที่พบบ่อย
### ฉันสามารถเรนเดอร์รูปแบบเอกสารอื่นนอกเหนือจากไฟล์เก็บถาวรได้หรือไม่
ใช่ GroupDocs.Viewer รองรับรูปแบบเอกสารที่หลากหลาย รวมถึง PDF, DOCX, XLSX, PPTX และอื่นๆ
### GroupDocs.Viewer เหมาะสำหรับทั้งเดสก์ท็อปและเว็บแอปพลิเคชันหรือไม่
GroupDocs.Viewer สามารถนำไปใช้ได้ทั้งบนเดสก์ท็อปและเว็บแอปพลิเคชันได้อย่างราบรื่น
### GroupDocs.Viewer มีตัวเลือกการปรับแต่งสำหรับอินเทอร์เฟซผู้ดูหรือไม่
ใช่ คุณสามารถปรับแต่งอินเทอร์เฟซของโปรแกรมดูได้ตามความต้องการของคุณ
### ฉันสามารถแสดงเอกสารแบบอะซิงโครนัสด้วย GroupDocs.Viewer ได้หรือไม่
ใช่ GroupDocs.Viewer มีความสามารถในการเรนเดอร์แบบอะซิงโครนัสเพื่อประสิทธิภาพที่ดีขึ้น
### GroupDocs.Viewer รองรับคำอธิบายประกอบเอกสารหรือไม่
ใช่ GroupDocs.Viewer ช่วยให้ผู้ใช้สามารถดูและจัดการคำอธิบายประกอบเอกสารได้อย่างมีประสิทธิภาพ