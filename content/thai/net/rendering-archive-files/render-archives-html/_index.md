---
"description": "เรียนรู้วิธีการเรนเดอร์ไฟล์เก็บถาวรในหน้า HTML โดยใช้ GroupDocs.Viewer สำหรับ .NET ผสานรวมความสามารถในการดูเอกสารลงในแอปพลิเคชัน .NET ของคุณได้อย่างง่ายดาย"
"linktitle": "เรนเดอร์ไฟล์เก็บถาวรไปยังหน้า HTML เดียวหรือหลายหน้า"
"second_title": "API ของ GroupDocs.Viewer .NET"
"title": "เรนเดอร์ไฟล์เก็บถาวรไปยังหน้า HTML เดียวหรือหลายหน้า"
"url": "/th/net/rendering-archive-files/render-archives-html/"
"weight": 12
type: docs
---
# เรนเดอร์ไฟล์เก็บถาวรไปยังหน้า HTML เดียวหรือหลายหน้า

## การแนะนำ
GroupDocs.Viewer สำหรับ .NET เป็นไลบรารีสำหรับการเรนเดอร์เอกสารอันทรงพลังที่ช่วยให้ผู้พัฒนาสามารถผสานรวมความสามารถในการดูเอกสารเข้ากับแอปพลิเคชัน .NET ได้อย่างง่ายดาย ไม่ว่าคุณจะต้องเรนเดอร์ไฟล์เก็บถาวรลงในหน้า HTML เดียวหรือหลายหน้า บทช่วยสอนนี้จะแนะนำคุณตลอดขั้นตอนต่างๆ
## ข้อกำหนดเบื้องต้น
ก่อนที่จะเริ่มบทช่วยสอนนี้ ให้แน่ใจว่าคุณมีข้อกำหนดเบื้องต้นดังต่อไปนี้:
1. GroupDocs.Viewer สำหรับ .NET: ตรวจสอบให้แน่ใจว่าคุณได้ติดตั้งไลบรารีในโปรเจ็กต์ของคุณแล้ว คุณสามารถดาวน์โหลดได้จาก [ที่นี่](https://releases-groupdocs.com/viewer/net/).
2. สภาพแวดล้อมการพัฒนา: มีการตั้งค่าสภาพแวดล้อมการพัฒนาการทำงานสำหรับการพัฒนา .NET
3. ไดเรกทอรีเอกสาร: จัดเตรียมไดเรกทอรีที่ใช้จัดเก็บเอกสารของคุณ
4. ความเข้าใจพื้นฐานเกี่ยวกับ C#: ทำความคุ้นเคยกับพื้นฐานของภาษาการเขียนโปรแกรม C#

## นำเข้าเนมสเปซ
ในโค้ด C# ของคุณ อย่าลืมนำเข้าเนมสเปซที่จำเป็น:
```csharp
using GroupDocs.Viewer.Options;
using System;
using System.IO;
```

ปฏิบัติตามขั้นตอนเหล่านี้ในการเรนเดอร์ไฟล์เก็บถาวรไปยังหน้า HTML เดียวหรือหลายหน้าโดยใช้ GroupDocs.Viewer สำหรับ .NET:
## ขั้นตอนที่ 1: ตั้งค่าไดเรกทอรีผลลัพธ์
กำหนดไดเรกทอรีที่คุณต้องการบันทึกหน้า HTML ที่แสดงผล:
```csharp
string outputDirectory = "Your Document Directory";
```
## ขั้นตอนที่ 2: กำหนดรูปแบบเส้นทางไฟล์
ระบุรูปแบบเส้นทางไฟล์สำหรับหน้า HTML สำหรับการแสดงผลหน้าเดียว:
```csharp
string pageFilePathFormat = Path.Combine(outputDirectory, "RAR_result.html");
```
สำหรับการเรนเดอร์หลายหน้า:
```csharp
pageFilePathFormat = Path.Combine(outputDirectory, "RAR_result_page_{0}.html");
```
## ขั้นตอนที่ 3: เรนเดอร์เป็น HTML หน้าเดียว
```csharp
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_RAR_WITH_FOLDERS))
{
    HtmlViewOptions options = HtmlViewOptions.ForEmbeddedResources(pageFilePathFormat);
    options.RenderToSinglePage = true; 
    viewer.View(options);
}
```
## ขั้นตอนที่ 4: เรนเดอร์เป็น HTML หลายหน้า
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
การเรนเดอร์ไฟล์เก็บถาวรไปยังหน้า HTML โดยใช้ GroupDocs.Viewer สำหรับ .NET เป็นกระบวนการที่ตรงไปตรงมา เพียงทำตามขั้นตอนที่ระบุไว้ในบทช่วยสอนนี้ คุณก็ผสานรวมความสามารถในการดูเอกสารเข้ากับแอปพลิเคชัน .NET ของคุณได้อย่างราบรื่น
## คำถามที่พบบ่อย
### ฉันสามารถแสดงรูปแบบเอกสารอื่นนอกเหนือจากไฟล์เก็บถาวรได้หรือไม่
ใช่ GroupDocs.Viewer รองรับรูปแบบเอกสารต่างๆ มากมาย เช่น PDF, DOCX, XLSX, PPTX และอื่นๆ อีกมากมาย
### GroupDocs.Viewer เหมาะกับแอพพลิเคชันทั้งบนเดสก์ท็อปและเว็บหรือไม่
แน่นอนว่า GroupDocs.Viewer สามารถใช้งานในแอพพลิเคชันเดสก์ท็อปและเว็บได้อย่างราบรื่น
### GroupDocs.Viewer มีตัวเลือกการปรับแต่งสำหรับอินเทอร์เฟซผู้ดูหรือไม่
ใช่ คุณสามารถปรับแต่งอินเทอร์เฟซผู้ชมตามความต้องการของคุณได้
### ฉันสามารถแสดงเอกสารแบบอะซิงโครนัสด้วย GroupDocs.Viewer ได้หรือไม่
ใช่ GroupDocs.Viewer มอบความสามารถในการเรนเดอร์แบบอะซิงโครนัสเพื่อประสิทธิภาพที่ดีขึ้น
### GroupDocs.Viewer รองรับคำอธิบายประกอบเอกสารหรือไม่
ใช่ GroupDocs.Viewer ช่วยให้ผู้ใช้ดูและจัดการคำอธิบายประกอบเอกสารได้อย่างมีประสิทธิภาพ