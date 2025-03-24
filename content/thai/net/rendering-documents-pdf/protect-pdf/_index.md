---
title: ป้องกัน PDF ที่แสดงผลด้วยรหัสผ่าน
linktitle: ป้องกัน PDF ที่แสดงผลด้วยรหัสผ่าน
second_title: GroupDocs.Viewer .NET API
description: ปกป้อง PDF ที่เรนเดอร์ของคุณด้วยรหัสผ่านอย่างง่ายดายโดยใช้ Groupdocs.Viewer สำหรับ .NET รักษาเอกสารของคุณให้ปลอดภัยและเป็นความลับ
weight: 12
url: /th/net/rendering-documents-pdf/protect-pdf/
---
## การแนะนำ
ในบทช่วยสอนนี้ คุณจะได้เรียนรู้วิธีใช้ Groupdocs.Viewer สำหรับ .NET เพื่อปกป้อง PDF ที่แสดงผลด้วยรหัสผ่าน ด้วยการเพิ่มมาตรการรักษาความปลอดภัย คุณสามารถควบคุมการเข้าถึงเอกสาร PDF ของคุณได้ โดยรับประกันการรักษาความลับและความสมบูรณ์
## ข้อกำหนดเบื้องต้น
ก่อนที่คุณจะเริ่มต้น ตรวจสอบให้แน่ใจว่าคุณมีสิ่งต่อไปนี้:
1.  Groupdocs.Viewer สำหรับ .NET Library: ดาวน์โหลดและติดตั้งไลบรารีจาก[เว็บไซต์](https://releases.groupdocs.com/viewer/net/).
2. สภาพแวดล้อมการพัฒนา: ตรวจสอบให้แน่ใจว่าคุณมีสภาพแวดล้อมการพัฒนาที่ใช้งานได้ซึ่งตั้งค่าไว้สำหรับการพัฒนา .NET

## นำเข้าเนมสเปซ
```csharp
using System;
using System.IO;
using GroupDocs.Viewer.Options;
```
## ขั้นตอนที่ 1: กำหนดไดเรกทอรีผลลัพธ์และเส้นทางไฟล์
```csharp
string outputDirectory = "Your Document Directory";
string filePath = Path.Combine(outputDirectory, "output.pdf");
```
## ขั้นตอนที่ 2: เริ่มต้นวัตถุ Viewer และตั้งค่าตัวเลือกความปลอดภัย
```csharp
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_DOCX))
{
    Security security = new Security
    {
        DocumentOpenPassword = "o123",
        PermissionsPassword = "p123",
        Permissions = Permissions.AllowAll ^ Permissions.DenyPrinting
    };
```
## ขั้นตอนที่ 3: ตั้งค่าตัวเลือกมุมมอง PDF
```csharp
    PdfViewOptions options = new PdfViewOptions(filePath)
    {
        Security = security
    };
```
## ขั้นตอนที่ 4: แสดงผลเอกสารด้วยตัวเลือกความปลอดภัย
```csharp
    viewer.View(options);
}
```
## ขั้นตอนที่ 5: ตรวจสอบเอกสารที่แสดงผล
```csharp
Console.WriteLine($"\nSource document rendered successfully.\nCheck output in {outputDirectory}.");
```
เมื่อทำตามขั้นตอนเหล่านี้ คุณสามารถป้องกัน PDF ที่แสดงผลด้วยรหัสผ่านโดยใช้ Groupdocs.Viewer สำหรับ .NET สิ่งนี้ทำให้แน่ใจได้ว่าเอกสารของคุณยังคงปลอดภัยและสามารถเข้าถึงได้โดยผู้ใช้ที่ได้รับอนุญาตเท่านั้น

## บทสรุป
การรักษาความปลอดภัยเอกสาร PDF ถือเป็นสิ่งสำคัญในการรักษาความลับและความสมบูรณ์ ด้วย Groupdocs.Viewer สำหรับ .NET คุณสามารถปกป้อง PDF ที่เรนเดอร์ด้วยรหัสผ่านได้อย่างง่ายดาย ควบคุมการเข้าถึงข้อมูลที่ละเอียดอ่อน

## คำถามที่พบบ่อย
### ฉันสามารถปกป้อง PDF ด้วยระดับสิทธิ์ที่แตกต่างกันได้หรือไม่
ได้ คุณสามารถระบุการอนุญาตที่แตกต่างกันสำหรับการดู พิมพ์ การคัดลอก และอื่นๆ ในขณะที่ปกป้อง PDF ด้วยรหัสผ่าน
### Groupdocs.Viewer เข้ากันได้กับไฟล์รูปแบบต่างๆ หรือไม่
อย่างแน่นอน! Groupdocs.Viewer รองรับการเรนเดอร์ไฟล์รูปแบบต่างๆ มากมาย รวมถึง DOCX, XLSX, PPTX, PDF และอื่นๆ
### ฉันสามารถรวม Groupdocs.Viewer เข้ากับแอปพลิเคชัน .NET ที่มีอยู่ได้หรือไม่
แน่นอน! Groupdocs.Viewer มอบ API สำหรับการผสานรวมเข้ากับแอปพลิเคชัน .NET ได้อย่างราบรื่น มอบความสามารถในการดูเอกสารที่แข็งแกร่ง
### Groupdocs.Viewer รองรับบริการจัดเก็บข้อมูลบนคลาวด์หรือไม่
ใช่ Groupdocs.Viewer รองรับการผสานรวมกับบริการจัดเก็บข้อมูลบนคลาวด์ยอดนิยม เช่น Dropbox, Google Drive และ Amazon S3 ทำให้คุณสามารถแสดงเอกสารที่จัดเก็บไว้ในคลาวด์ได้
### มีรุ่นทดลองใช้สำหรับ Groupdocs.Viewer หรือไม่
 ใช่ คุณสามารถเริ่มต้นใช้งาน Groupdocs.Viewer ได้โดยการเข้าถึงเวอร์ชันทดลองใช้ฟรีจาก[เว็บไซต์](https://releases.groupdocs.com/).