---
"description": "ปกป้องไฟล์ PDF ที่คุณสร้างขึ้นด้วยรหัสผ่านได้อย่างง่ายดายโดยใช้ Groupdocs.Viewer สำหรับ .NET รักษาเอกสารของคุณให้ปลอดภัยและเป็นความลับ"
"linktitle": "ป้องกัน PDF ที่แสดงผลด้วยรหัสผ่าน"
"second_title": "API ของ GroupDocs.Viewer .NET"
"title": "ป้องกัน PDF ที่แสดงผลด้วยรหัสผ่าน"
"url": "/th/net/rendering-documents-pdf/protect-pdf/"
"weight": 12
type: docs
---
# ป้องกัน PDF ที่แสดงผลด้วยรหัสผ่าน

## การแนะนำ
ในบทช่วยสอนนี้ คุณจะได้เรียนรู้วิธีใช้ Groupdocs.Viewer สำหรับ .NET เพื่อปกป้อง PDF ที่แสดงผลด้วยรหัสผ่าน โดยการเพิ่มมาตรการรักษาความปลอดภัย คุณสามารถควบคุมการเข้าถึงเอกสาร PDF ของคุณได้ ทำให้มั่นใจได้ถึงความลับและความสมบูรณ์
## ข้อกำหนดเบื้องต้น
ก่อนที่คุณจะเริ่มต้น ให้แน่ใจว่าคุณมีสิ่งต่อไปนี้:
1. Groupdocs.Viewer สำหรับไลบรารี .NET: ดาวน์โหลดและติดตั้งไลบรารีจาก [เว็บไซต์](https://releases-groupdocs.com/viewer/net/).
2. สภาพแวดล้อมการพัฒนา: ตรวจสอบให้แน่ใจว่าคุณมีการตั้งค่าสภาพแวดล้อมการพัฒนาการทำงานสำหรับการพัฒนา .NET

## นำเข้าเนมสเปซ
```csharp
using System;
using System.IO;
using GroupDocs.Viewer.Options;
```
## ขั้นตอนที่ 1: กำหนดไดเรกทอรีเอาต์พุตและเส้นทางไฟล์
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
## ขั้นตอนที่ 4: เรนเดอร์เอกสารพร้อมตัวเลือกความปลอดภัย
```csharp
    viewer.View(options);
}
```
## ขั้นตอนที่ 5: ตรวจสอบเอกสารที่แสดงผล
```csharp
Console.WriteLine($"\nSource document rendered successfully.\nCheck output in {outputDirectory}.");
```
หากทำตามขั้นตอนเหล่านี้ คุณสามารถป้องกัน PDF ที่แสดงผลด้วยรหัสผ่านโดยใช้ Groupdocs.Viewer สำหรับ .NET ซึ่งจะช่วยให้มั่นใจว่าเอกสารของคุณจะยังคงปลอดภัยและสามารถเข้าถึงได้โดยผู้ใช้ที่ได้รับอนุญาตเท่านั้น

## บทสรุป
การรักษาความปลอดภัยเอกสาร PDF ถือเป็นสิ่งสำคัญสำหรับการรักษาความลับและความสมบูรณ์ ด้วย Groupdocs.Viewer สำหรับ .NET คุณสามารถปกป้อง PDF ที่แสดงผลด้วยรหัสผ่านได้อย่างง่ายดาย โดยควบคุมการเข้าถึงข้อมูลที่ละเอียดอ่อน

## คำถามที่พบบ่อย
### ฉันสามารถปกป้องไฟล์ PDF ด้วยระดับการอนุญาตที่แตกต่างกันได้หรือไม่
ใช่ คุณสามารถระบุสิทธิ์ที่แตกต่างกันสำหรับการดู พิมพ์ คัดลอก และอื่นๆ ในขณะที่ปกป้อง PDF ด้วยรหัสผ่าน
### Groupdocs.Viewer เข้ากันได้กับรูปแบบไฟล์ต่างๆ หรือไม่
แน่นอน! Groupdocs.Viewer รองรับการเรนเดอร์ไฟล์ในรูปแบบต่างๆ มากมาย รวมถึง DOCX, XLSX, PPTX, PDF และอื่นๆ อีกมากมาย
### ฉันสามารถรวม Groupdocs.Viewer เข้ากับแอปพลิเคชัน .NET ที่มีอยู่ได้หรือไม่
แน่นอน! Groupdocs.Viewer นำเสนอ API สำหรับการบูรณาการอย่างราบรื่นในแอปพลิเคชัน .NET พร้อมมอบความสามารถในการดูเอกสารที่แข็งแกร่ง
### Groupdocs.Viewer ให้การสนับสนุนบริการการจัดเก็บข้อมูลบนคลาวด์หรือไม่
ใช่ Groupdocs.Viewer รองรับการรวมเข้ากับบริการจัดเก็บข้อมูลบนคลาวด์ยอดนิยม เช่น Dropbox, Google Drive และ Amazon S3 ช่วยให้คุณสามารถแสดงเอกสารที่จัดเก็บในระบบคลาวด์ได้
### มีเวอร์ชันทดลองใช้สำหรับ Groupdocs.Viewer หรือไม่
ใช่ คุณสามารถเริ่มต้นใช้งาน Groupdocs.Viewer ได้โดยเข้าถึงเวอร์ชันทดลองใช้งานฟรีจาก [เว็บไซต์](https://releases-groupdocs.com/).