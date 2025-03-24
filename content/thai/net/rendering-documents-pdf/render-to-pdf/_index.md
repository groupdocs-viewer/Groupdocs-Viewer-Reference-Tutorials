---
title: เรนเดอร์เอกสารเป็น PDF
linktitle: เรนเดอร์เอกสารเป็น PDF
second_title: GroupDocs.Viewer .NET API
description: เรียนรู้วิธีแสดงเอกสารเป็น PDF โดยใช้ GroupDocs.Viewer สำหรับ .NET คำแนะนำทีละขั้นตอนพร้อมข้อกำหนดเบื้องต้นและคำถามที่พบบ่อย
weight: 10
url: /th/net/rendering-documents-pdf/render-to-pdf/
---

# เรนเดอร์เอกสารเป็น PDF

## การแนะนำ
GroupDocs.Viewer สำหรับ .NET เป็นเครื่องมืออันทรงพลังสำหรับเรนเดอร์เอกสารรูปแบบต่างๆ ให้เป็น PDF ในบทช่วยสอนนี้ เราจะแนะนำคุณตลอดกระบวนการทีละขั้นตอน
## ข้อกำหนดเบื้องต้น

ก่อนที่เราจะเริ่ม ตรวจสอบให้แน่ใจว่าคุณมีสิ่งต่อไปนี้:
1.  GroupDocs.Viewer สำหรับ .NET Library: คุณสามารถดาวน์โหลดไลบรารีได้จาก[ที่นี่](https://releases.groupdocs.com/viewer/net/).
2. .NET Framework: ตรวจสอบให้แน่ใจว่าคุณได้ติดตั้ง .NET Framework เวอร์ชันที่เหมาะสมในเครื่องของคุณ
3. ไฟล์เอกสาร: เตรียมไฟล์เอกสารที่คุณต้องการแสดงผล รูปแบบที่รองรับ ได้แก่ DOCX, PDF, PPTX, XLSX และอื่นๆ

## การนำเข้าเนมสเปซ:
ก่อนที่จะเจาะลึกโค้ด ตรวจสอบให้แน่ใจว่าคุณนำเข้าเนมสเปซที่จำเป็น:
```csharp
using System;
using System.IO;
using GroupDocs.Viewer.Options;
```

ตอนนี้ เรามาแบ่งกระบวนการเรนเดอร์ออกเป็นหลายขั้นตอน:
## ขั้นตอนที่ 1: กำหนดไดเรกทอรีผลลัพธ์และเส้นทางไฟล์
```csharp
string outputDirectory = "Your Document Directory";
string outputFilePath = Path.Combine(outputDirectory, "output.pdf");
```
 ให้แน่ใจว่าจะเปลี่ยน`"Your Document Directory"` ด้วยไดเร็กทอรีที่คุณต้องการบันทึกไฟล์ PDF ที่เรนเดอร์
## ขั้นตอนที่ 2: สร้างอินสแตนซ์ของวัตถุ Viewer
```csharp
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_DOCX))
{
    // รหัสของคุณที่นี่
}
```
 แทนที่`TestFiles.SAMPLE_DOCX` พร้อมเส้นทางไปยังไฟล์เอกสารของคุณ
## ขั้นตอนที่ 3: ตั้งค่าตัวเลือกมุมมอง PDF
```csharp
PdfViewOptions options = new PdfViewOptions(outputFilePath);
```
## ขั้นตอนที่ 4: แสดงผลเอกสารเป็น PDF
```csharp
viewer.View(options);
```
## ขั้นตอนที่ 5: แสดงข้อความแสดงความสำเร็จ
```csharp
Console.WriteLine($"\nSource document rendered successfully.\nCheck output in {outputDirectory}.");
```
หลังจากทำตามขั้นตอนเหล่านี้ คุณจะแสดงผลเอกสารของคุณเป็น PDF ได้สำเร็จโดยใช้ GroupDocs.Viewer สำหรับ .NET

## บทสรุป
การแสดงเอกสารเป็น PDF เป็นข้อกำหนดทั่วไปในการใช้งานต่างๆ ด้วย GroupDocs.Viewer สำหรับ .NET กระบวนการนี้จะราบรื่นและมีประสิทธิภาพ ช่วยให้คุณสามารถจัดการรูปแบบเอกสารที่หลากหลายได้อย่างง่ายดาย
## คำถามที่พบบ่อย
### ฉันสามารถแสดงเอกสารอื่นที่ไม่ใช่ DOCX เป็น PDF ได้หรือไม่
ใช่ GroupDocs.Viewer สำหรับ .NET รองรับรูปแบบต่างๆ เช่น PDF, PPTX, XLSX และอื่นๆ
### มีรุ่นทดลองใช้งานหรือไม่?
 ใช่ คุณสามารถดาวน์โหลดรุ่นทดลองใช้ฟรีได้จาก[ที่นี่](https://releases.groupdocs.com/).
### ฉันจะรับการสนับสนุนได้อย่างไรหากฉันประสบปัญหาใดๆ
 คุณสามารถเยี่ยมชมฟอรัม GroupDocs.Viewer[ที่นี่](https://forum.groupdocs.com/c/viewer/9) สำหรับความช่วยเหลือ.
### ฉันจำเป็นต้องมีใบอนุญาตชั่วคราวเพื่อการทดสอบหรือไม่?
 ใช่ คุณสามารถขอรับใบอนุญาตชั่วคราวได้จาก[ที่นี่](https://purchase.groupdocs.com/temporary-license/).
### ฉันจะซื้อใบอนุญาตฉบับสมบูรณ์ได้ที่ไหน
 คุณสามารถซื้อใบอนุญาตได้จาก[ที่นี่](https://purchase.groupdocs.com/buy).