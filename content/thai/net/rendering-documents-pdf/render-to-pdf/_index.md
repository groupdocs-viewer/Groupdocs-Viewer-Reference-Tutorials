---
"description": "เรียนรู้วิธีการแสดงเอกสารเป็น PDF โดยใช้ GroupDocs.Viewer สำหรับ .NET พร้อมคำแนะนำทีละขั้นตอนพร้อมข้อกำหนดเบื้องต้นและคำถามที่พบบ่อย"
"linktitle": "เรนเดอร์เอกสารเป็น PDF"
"second_title": "API ของ GroupDocs.Viewer .NET"
"title": "เรนเดอร์เอกสารเป็น PDF"
"url": "/th/net/rendering-documents-pdf/render-to-pdf/"
"weight": 10
type: docs
---
# เรนเดอร์เอกสารเป็น PDF

## การแนะนำ
GroupDocs.Viewer สำหรับ .NET เป็นเครื่องมืออันทรงพลังสำหรับการแสดงผลเอกสารในรูปแบบต่างๆ ลงใน PDF ในบทช่วยสอนนี้ เราจะแนะนำคุณทีละขั้นตอนในกระบวนการนี้
## ข้อกำหนดเบื้องต้น

ก่อนที่เราจะเริ่ม ให้แน่ใจว่าคุณมีสิ่งต่อไปนี้:
1. GroupDocs.Viewer สำหรับไลบรารี .NET: คุณสามารถดาวน์โหลดไลบรารีได้จาก [ที่นี่](https://releases-groupdocs.com/viewer/net/).
2. .NET Framework: ตรวจสอบให้แน่ใจว่าคุณได้ติดตั้ง .NET Framework เวอร์ชันที่เหมาะสมบนเครื่องของคุณแล้ว
3. ไฟล์เอกสาร: เตรียมไฟล์เอกสารที่คุณต้องการเรนเดอร์ รูปแบบที่รองรับ ได้แก่ DOCX, PDF, PPTX, XLSX และอื่นๆ

## การนำเข้าเนมสเปซ:
ก่อนที่จะเจาะลึกโค้ด ให้แน่ใจว่าคุณได้นำเข้าเนมสเปซที่จำเป็นแล้ว:
```csharp
using System;
using System.IO;
using GroupDocs.Viewer.Options;
```

ตอนนี้เรามาแบ่งกระบวนการเรนเดอร์ออกเป็นหลายขั้นตอน:
## ขั้นตอนที่ 1: กำหนดไดเรกทอรีเอาต์พุตและเส้นทางไฟล์
```csharp
string outputDirectory = "Your Document Directory";
string outputFilePath = Path.Combine(outputDirectory, "output.pdf");
```
ให้แน่ใจว่าได้เปลี่ยน `"Your Document Directory"` พร้อมไดเร็กทอรีที่คุณต้องการบันทึกไฟล์ PDF ที่จะแสดงผล
## ขั้นตอนที่ 2: สร้างอินสแตนซ์ของวัตถุ Viewer
```csharp
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_DOCX))
{
    // รหัสของคุณที่นี่
}
```
แทนที่ `TestFiles.SAMPLE_DOCX` พร้อมเส้นทางไปยังไฟล์เอกสารของคุณ
## ขั้นตอนที่ 3: ตั้งค่าตัวเลือกมุมมอง PDF
```csharp
PdfViewOptions options = new PdfViewOptions(outputFilePath);
```
## ขั้นตอนที่ 4: เรนเดอร์เอกสารเป็น PDF
```csharp
viewer.View(options);
```
## ขั้นตอนที่ 5: แสดงข้อความแสดงว่าสำเร็จ
```csharp
Console.WriteLine($"\nSource document rendered successfully.\nCheck output in {outputDirectory}.");
```
หลังจากทำตามขั้นตอนเหล่านี้แล้ว คุณจะเรนเดอร์เอกสารเป็น PDF ได้สำเร็จโดยใช้ GroupDocs.Viewer สำหรับ .NET

## บทสรุป
การเรนเดอร์เอกสารเป็น PDF เป็นข้อกำหนดทั่วไปในแอปพลิเคชันต่างๆ ด้วย GroupDocs.Viewer สำหรับ .NET กระบวนการนี้จะราบรื่นและมีประสิทธิภาพ ช่วยให้คุณสามารถจัดการเอกสารในรูปแบบต่างๆ ได้อย่างง่ายดาย
## คำถามที่พบบ่อย
### ฉันสามารถแสดงเอกสารอื่นนอกจาก DOCX เป็น PDF ได้หรือไม่
ใช่ GroupDocs.Viewer สำหรับ .NET รองรับรูปแบบต่างๆ เช่น PDF, PPTX, XLSX และอื่นๆ อีกมากมาย
### มีเวอร์ชันทดลองใช้งานไหม?
ใช่ คุณสามารถดาวน์โหลดรุ่นทดลองใช้งานฟรีได้จาก [ที่นี่](https://releases-groupdocs.com/).
### ฉันจะได้รับการสนับสนุนได้อย่างไรหากพบปัญหาใดๆ?
คุณสามารถเยี่ยมชมฟอรั่ม GroupDocs.Viewer ได้ [ที่นี่](https://forum.groupdocs.com/c/viewer/9) เพื่อขอความช่วยเหลือ
### ฉันต้องมีใบอนุญาตชั่วคราวเพื่อวัตถุประสงค์ในการทดสอบหรือไม่?
ใช่ คุณสามารถขอใบอนุญาตชั่วคราวได้จาก [ที่นี่](https://purchase-groupdocs.com/temporary-license/).
### ฉันสามารถซื้อใบอนุญาตเต็มรูปแบบได้ที่ไหน
คุณสามารถซื้อใบอนุญาตได้จาก [ที่นี่](https://purchase-groupdocs.com/buy).