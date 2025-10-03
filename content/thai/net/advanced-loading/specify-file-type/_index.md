---
"description": "เรียนรู้วิธีระบุประเภทไฟล์เมื่อโหลดเอกสารโดยใช้ GroupDocs.Viewer สำหรับ .NET แสดงผลรูปแบบต่างๆ ได้อย่างแม่นยำในแอปพลิเคชัน .NET ของคุณ"
"linktitle": "ระบุประเภทไฟล์เมื่อโหลดเอกสาร"
"second_title": "API ของ GroupDocs.Viewer .NET"
"title": "ระบุประเภทไฟล์เมื่อโหลดเอกสาร"
"url": "/th/net/advanced-loading/specify-file-type/"
"weight": 10
type: docs
---
# ระบุประเภทไฟล์เมื่อโหลดเอกสาร

## การแนะนำ
GroupDocs.Viewer สำหรับ .NET เป็น API การเรนเดอร์เอกสารอเนกประสงค์ที่รองรับรูปแบบไฟล์หลากหลาย เช่น DOCX, PDF, PPTX และอื่นๆ อีกมากมาย คุณสามารถมั่นใจได้ถึงการแสดงผลที่แม่นยำและประสบการณ์การรับชมที่ราบรื่นสำหรับผู้ใช้ของคุณโดยการระบุประเภทไฟล์เมื่อโหลดเอกสาร

![ระบุประเภทไฟล์เมื่อโหลดเอกสารใน GroupDocs.Viewer สำหรับ .NET](/viewer/advanced-loading/specify-file-type-when-loading-documents-img.png)

## ข้อกำหนดเบื้องต้น
ก่อนที่คุณจะเริ่มต้น โปรดตรวจสอบให้แน่ใจว่าคุณมีข้อกำหนดเบื้องต้นดังต่อไปนี้:
- ความรู้พื้นฐานเกี่ยวกับ C# และ .NET framework
- Visual Studio ติดตั้งอยู่บนระบบของคุณแล้ว
- GroupDocs.Viewer สำหรับ .NET ได้รับการติดตั้งในโครงการของคุณแล้ว คุณสามารถดาวน์โหลดได้จาก [ที่นี่](https://releases-groupdocs.com/viewer/net/).
##
## นำเข้าเนมสเปซ
ขั้นแรก คุณต้องนำเข้าเนมสเปซที่จำเป็นลงในโค้ด C# ของคุณ เนมสเปซเหล่านี้ช่วยให้เข้าถึงคลาสและวิธีการที่จำเป็นสำหรับการแสดงผลเอกสารได้
```csharp
using System;
using System.IO;
using GroupDocs.Viewer.Options;
```
## ขั้นตอนที่ 1: ตั้งค่าไดเรกทอรีเอาต์พุต
กำหนดไดเร็กทอรีที่คุณต้องการบันทึกหน้าเอกสารที่แสดงผล
```csharp
string outputDirectory = "Your Document Directory";
```
## ขั้นตอนที่ 2: กำหนดรูปแบบเส้นทางไฟล์เพจ
ระบุรูปแบบการตั้งชื่อไฟล์เอาต์พุต HTML สำหรับแต่ละหน้าของเอกสาร
```csharp
string pageFilePathFormat = Path.Combine(outputDirectory, "page_{0}.html");
```
## ขั้นตอนที่ 3: ระบุตัวเลือกการโหลด
สร้างอินสแตนซ์ของ `LoadOptions` คลาสและตั้งค่าประเภทไฟล์ที่ต้องการ
```csharp
LoadOptions loadOptions = new LoadOptions
{
    FileType = FileType.DOCX
};
```
## ขั้นตอนที่ 4: โหลดเอกสารและเรนเดอร์
ใช้ `Viewer` คลาสที่จะโหลดเอกสารและเรนเดอร์เป็นรูปแบบ HTML
```csharp
using (Viewer viewer = new Viewer("YourDocument.docx", loadOptions))
{
    HtmlViewOptions options = HtmlViewOptions.ForEmbeddedResources(pageFilePathFormat);
    viewer.View(options);
}
```
## ขั้นตอนที่ 5: แสดงข้อความแสดงว่าสำเร็จ
แจ้งให้ผู้ใช้ทราบว่าเอกสารได้รับการแสดงสำเร็จแล้ว และระบุตำแหน่งของไฟล์เอาต์พุต
```csharp
Console.WriteLine($"\nSource document rendered successfully.\nCheck output in {outputDirectory}.");
```

## บทสรุป
ในบทช่วยสอนนี้ เราได้เรียนรู้วิธีใช้ GroupDocs.Viewer สำหรับ .NET เพื่อระบุประเภทไฟล์เมื่อโหลดเอกสาร โดยทำตามขั้นตอนง่ายๆ เหล่านี้ คุณสามารถมั่นใจได้ว่าการแสดงผลเอกสารในรูปแบบต่างๆ ในแอปพลิเคชัน .NET ของคุณนั้นถูกต้องแม่นยำ
## คำถามที่พบบ่อย
### ฉันสามารถแสดงเอกสารอื่นนอกเหนือจาก DOCX โดยใช้ GroupDocs.Viewer สำหรับ .NET ได้หรือไม่
ใช่ GroupDocs.Viewer รองรับรูปแบบไฟล์ต่างๆ มากมาย รวมถึง PDF, PPTX, XLSX และอื่นๆ อีกมากมาย
### GroupDocs.Viewer สำหรับ .NET เข้ากันได้กับ .NET Core ได้หรือไม่
ใช่ GroupDocs.Viewer สำหรับ .NET เข้ากันได้กับทั้ง .NET Framework และ .NET Core
### ฉันสามารถปรับแต่งไฟล์ HTML เอาท์พุตที่สร้างโดย GroupDocs.Viewer ได้หรือไม่
ใช่ คุณสามารถปรับแต่งผลลัพธ์ HTML ได้โดยใช้ตัวเลือกต่างๆ ที่ API จัดทำไว้ให้
### GroupDocs.Viewer สำหรับ .NET ต้องมีการอ้างอิงภายนอกใด ๆ หรือไม่
ไม่ GroupDocs.Viewer สำหรับ .NET เป็นไลบรารีแบบสแตนด์อโลนและไม่จำเป็นต้องมีการอ้างอิงภายนอกใดๆ
### มีเวอร์ชันทดลองใช้สำหรับ GroupDocs.Viewer สำหรับ .NET หรือไม่
ใช่ คุณสามารถดาวน์โหลดเวอร์ชันทดลองใช้งานฟรีได้จาก [ที่นี่](https://releases-groupdocs.com/viewer/net/).