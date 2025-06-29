---
"description": "เรียนรู้วิธีการเรนเดอร์ไฟล์เก็บถาวรใน .NET โดยใช้ GroupDocs.Viewer เพื่อเพิ่มประสิทธิภาพความสามารถในการจัดการเอกสาร"
"linktitle": "ระบุชื่อไฟล์เมื่อเรนเดอร์ไฟล์เก็บถาวร"
"second_title": "API ของ GroupDocs.Viewer .NET"
"title": "ระบุชื่อไฟล์เมื่อเรนเดอร์ไฟล์เก็บถาวร"
"url": "/th/net/rendering-archive-files/specify-filename-render-archive/"
"weight": 14
---

# ระบุชื่อไฟล์เมื่อเรนเดอร์ไฟล์เก็บถาวร

## การแนะนำ
GroupDocs.Viewer เป็นเครื่องมือที่มีความยืดหยุ่นและโดดเด่นสำหรับการพัฒนา .NET เนื่องจากมีคุณลักษณะและความยืดหยุ่นสูง จึงทำให้กระบวนการดูไฟล์ต่างๆ รวมถึงไฟล์เก็บถาวรนั้นง่ายขึ้น ในบทช่วยสอนนี้ เราจะเจาะลึกถึงรายละเอียดเฉพาะของการเรนเดอร์ไฟล์เก็บถาวรโดยใช้ GroupDocs.Viewer สำหรับ .NET โดยทำตามคำแนะนำทีละขั้นตอนเหล่านี้ คุณจะเรียนรู้วิธีระบุชื่อไฟล์เมื่อเรนเดอร์ไฟล์เก็บถาวร ซึ่งช่วยให้จัดการเอกสารในแอปพลิเคชัน .NET ได้อย่างราบรื่น
## ข้อกำหนดเบื้องต้น
ก่อนจะเริ่มบทช่วยสอนนี้ ให้แน่ใจว่าคุณมีข้อกำหนดเบื้องต้นดังต่อไปนี้:
1. GroupDocs.Viewer สำหรับ .NET: ดาวน์โหลดและติดตั้งไลบรารี GroupDocs.Viewer จาก [ที่นี่](https://releases-groupdocs.com/viewer/net/).
2. สภาพแวดล้อมการพัฒนา: ตั้งค่าสภาพแวดล้อมการพัฒนา .NET เช่น Visual Studio ด้วยการกำหนดค่าที่จำเป็น
3. ความรู้พื้นฐานเกี่ยวกับ C#: ความคุ้นเคยกับภาษาการเขียนโปรแกรม C# ถือเป็นสิ่งสำคัญในการทำความเข้าใจและนำชิ้นส่วนโค้ดที่ให้มาไปใช้งาน

## นำเข้าเนมสเปซ
ในโครงการ C# ของคุณ นำเข้าเนมสเปซที่จำเป็นเพื่อเข้าถึงฟังก์ชันการทำงานของ GroupDocs.Viewer:
```csharp
using System;
using System.IO;
using GroupDocs.Viewer.Options;
```
## ขั้นตอนที่ 1: ระบุไดเรกทอรีเอาต์พุตและเส้นทางไฟล์
กำหนดไดเร็กทอรีเอาท์พุตที่เอกสารที่เรนเดอร์จะถูกบันทึกและระบุเส้นทางไฟล์เอาท์พุต:
```csharp
string outputDirectory = "Your Document Directory";
string outputFilePath = Path.Combine(outputDirectory, "output.pdf");
```
## ขั้นตอนที่ 2: เริ่มต้น Viewer Object
สร้างอินสแตนซ์ของคลาส Viewer โดยระบุเส้นทางไปยังไฟล์เก็บถาวร:
```csharp
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_ZIP))
{
    // ตัวเลือกการเรนเดอร์
}
```
## ขั้นตอนที่ 3: กำหนดค่าตัวเลือกการแสดงผล PDF
ระบุตัวเลือกการเรนเดอร์ โดยเฉพาะสำหรับเอาท์พุต PDF:
```csharp
PdfViewOptions viewOptions = new PdfViewOptions(outputFilePath);
```
## ขั้นตอนที่ 4: ระบุชื่อไฟล์เก็บถาวร
ตั้งชื่อไฟล์ที่ต้องการสำหรับไฟล์เก็บถาวรที่แสดงผล:
```csharp
viewOptions.ArchiveOptions.FileName = new FileName("my filename");
```
## ขั้นตอนที่ 5: เรนเดอร์เอกสาร
เรียกใช้เมธอด View ของอ็อบเจ็กต์ Viewer ด้วยตัวเลือกมุมมองที่กำหนดค่าไว้:
```csharp
viewer.View(viewOptions);
```
## ขั้นตอนที่ 6: แสดงข้อความแสดงว่าสำเร็จ
แจ้งให้ผู้ใช้ทราบเกี่ยวกับการเรนเดอร์ที่ประสบความสำเร็จและระบุไดเร็กทอรีเอาท์พุต:
```csharp
Console.WriteLine($"\nSource document rendered successfully.\nCheck output in {outputDirectory}.");
```

## บทสรุป
ในบทช่วยสอนนี้ เราจะมาสำรวจวิธีการใช้ GroupDocs.Viewer สำหรับ .NET เพื่อแสดงไฟล์เก็บถาวรและระบุชื่อไฟล์แบบกำหนดเองสำหรับผลลัพธ์ โดยทำตามขั้นตอนที่ระบุไว้ คุณสามารถผสานรวมฟังก์ชันนี้เข้ากับแอปพลิเคชัน .NET ของคุณได้อย่างราบรื่น ช่วยเพิ่มความสามารถในการดูและจัดการเอกสาร
## คำถามที่พบบ่อย
### GroupDocs.Viewer เข้ากันได้กับรูปแบบไฟล์เก็บถาวรทั้งหมดหรือไม่
GroupDocs.Viewer รองรับรูปแบบไฟล์เก็บถาวรต่างๆ รวมถึง ZIP, RAR, TAR และ 7z เป็นต้น
### ฉันสามารถปรับแต่งรูปแบบเอาต์พุตอื่นนอกเหนือจาก PDF ได้หรือไม่
ใช่ GroupDocs.Viewer ให้ความยืดหยุ่นในการเลือกใช้รูปแบบผลลัพธ์ รวมถึงรูปแบบภาพเช่น JPG และ PNG เช่นเดียวกับ HTML และ PDF
### GroupDocs.Viewer เหมาะกับไฟล์เก็บถาวรขนาดใหญ่หรือไม่
ใช่ GroupDocs.Viewer ได้รับการปรับปรุงเพื่อจัดการไฟล์เก็บถาวรขนาดใหญ่ได้อย่างมีประสิทธิภาพ ช่วยให้การแสดงผลและประสิทธิภาพราบรื่น
### GroupDocs.Viewer รองรับการเข้ารหัสในไฟล์เก็บถาวรหรือไม่
ใช่ GroupDocs.Viewer สามารถจัดการไฟล์เก็บถาวรที่เข้ารหัสได้ โดยต้องมีการจัดเตรียมคีย์การถอดรหัสที่จำเป็น
### ฉันสามารถรวม GroupDocs.Viewer เข้ากับบริการการจัดเก็บข้อมูลบนคลาวด์ได้หรือไม่
ใช่ GroupDocs.Viewer นำเสนอการบูรณาการที่ราบรื่นกับผู้ให้บริการที่เก็บข้อมูลบนคลาวด์ยอดนิยม ช่วยให้สามารถเรนเดอร์ไฟล์ที่จัดเก็บบนคลาวด์ได้โดยตรง