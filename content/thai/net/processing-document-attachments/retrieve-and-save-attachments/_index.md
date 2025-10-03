---
"description": "จัดการเอกสารแนบภายในแอปพลิเคชัน .NET อย่างมีประสิทธิภาพโดยใช้ GroupDocs.Viewer เรียกค้นและบันทึกเอกสารแนบได้โดยไม่มีปัญหา"
"linktitle": "ดึงข้อมูลและบันทึกเอกสารแนบ"
"second_title": "API ของ GroupDocs.Viewer .NET"
"title": "ดึงข้อมูลและบันทึกเอกสารแนบ"
"url": "/th/net/processing-document-attachments/retrieve-and-save-attachments/"
"weight": 12
type: docs
---
# ดึงข้อมูลและบันทึกเอกสารแนบ

## การแนะนำ
ในยุคดิจิทัล การจัดการเอกสารอย่างมีประสิทธิภาพถือเป็นสิ่งสำคัญสำหรับทั้งธุรกิจและบุคคล ไม่ว่าจะเป็นการจัดการอีเมล การดูสัญญา หรือการเข้าถึงรายงาน การมีเครื่องมือที่เชื่อถือได้สำหรับการแสดงภาพเอกสารถือเป็นสิ่งสำคัญ GroupDocs.Viewer สำหรับ .NET ถือเป็นโซลูชันที่มีประสิทธิภาพ ช่วยให้ผู้ใช้สามารถดูและโต้ตอบกับรูปแบบเอกสารต่างๆ ได้โดยตรงภายในแอปพลิเคชัน .NET ได้อย่างง่ายดาย

![ดึงข้อมูลและบันทึกสิ่งที่แนบมากับเอกสารด้วย GroupDocs.Viewer .NET](/viewer/processing-document-attachments/retrieve-and-save-document-attachments.png)

## ข้อกำหนดเบื้องต้น
ก่อนที่จะใช้งาน GroupDocs.Viewer สำหรับ .NET เพื่อค้นหาและบันทึกสิ่งที่แนบมากับเอกสาร โปรดตรวจสอบให้แน่ใจว่าคุณมีข้อกำหนดเบื้องต้นดังต่อไปนี้:
1. สภาพแวดล้อมการปฏิบัติการ: สภาพแวดล้อมการทำงานที่ตั้งค่าด้วย .NET framework
2. การติดตั้ง: ดาวน์โหลดและติดตั้งไลบรารี GroupDocs.Viewer สำหรับ .NET คุณสามารถเข้าถึงไลบรารีได้จาก [ลิงค์ดาวน์โหลด](https://releases-groupdocs.com/viewer/net/).
3. ความเข้าใจพื้นฐาน: ความคุ้นเคยกับภาษาการเขียนโปรแกรม C#
4. ที่มาของเอกสาร: การเข้าถึงเอกสารตัวอย่างพร้อมไฟล์แนบเพื่อวัตถุประสงค์ในการสาธิต

## นำเข้าเนมสเปซ
ในการเริ่มใช้ GroupDocs.Viewer สำหรับ .NET สำหรับการดึงและบันทึกสิ่งที่แนบมากับเอกสาร ให้ทำการนำเข้าเนมสเปซที่จำเป็น:
```csharp
using System;
using System.Collections.Generic;
using System.IO;
using GroupDocs.Viewer.Results;
```

## ขั้นตอนที่ 1: กำหนดไดเรกทอรีผลลัพธ์
```csharp
string outputDirectory = "Your Document Directory";
```
กำหนดไดเร็กทอรีที่คุณต้องการบันทึกสิ่งที่แนบมาที่ดึงมาจากเอกสาร
## ขั้นตอนที่ 2: สร้างอินสแตนซ์ของวัตถุ Viewer
```csharp
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_MSG_WITH_ATTACHMENTS))
```
สร้างอินสแตนซ์ของวัตถุ Viewer พร้อมด้วยเส้นทางไปยังเอกสารที่มีสิ่งที่แนบมา
## ขั้นตอนที่ 3: ดึงข้อมูลแนบ
```csharp
IList<Attachment> attachments = viewer.GetAttachments();
```
ดึงข้อมูลรายการสิ่งที่แนบมาที่มีอยู่ในเอกสาร
## ขั้นตอนที่ 4: บันทึกสิ่งที่แนบมา
```csharp
foreach(Attachment attachment in attachments)
{
    string filePath = Path.Combine(outputDirectory, attachment.FileName);  
    viewer.SaveAttachment(attachment, File.OpenWrite(filePath)); 
}
```
ทำซ้ำผ่านสิ่งที่แนบมาแต่ละรายการ กำหนดเส้นทางไฟล์ และบันทึกสิ่งที่แนบมาไปยังไดเร็กทอรีที่ระบุ
## ขั้นตอนที่ 5: แสดงข้อความแสดงว่าสำเร็จ
```csharp
Console.WriteLine($"\nAttachments saved successfully.\nCheck output in {outputDirectory}.");
```
แสดงข้อความแสดงความสำเร็จโดยระบุว่าการบันทึกสิ่งที่แนบมาพร้อมกับเส้นทางไดเร็กทอรีประสบความสำเร็จ

## บทสรุป
การรวม GroupDocs.Viewer สำหรับ .NET เข้ากับเวิร์กโฟลว์การจัดการเอกสารของคุณจะทำให้กระบวนการจัดการไฟล์แนบมีประสิทธิภาพและสะดวกยิ่งขึ้น โดยปฏิบัติตามคำแนะนำทีละขั้นตอนที่ระบุไว้ข้างต้น ผู้ใช้สามารถเรียกค้นและบันทึกไฟล์แนบเอกสารภายในแอปพลิเคชัน .NET ได้อย่างราบรื่น
## คำถามที่พบบ่อย
### GroupDocs.Viewer สำหรับ .NET สามารถจัดการรูปแบบเอกสารต่างๆ ได้หรือไม่
ใช่ GroupDocs.Viewer รองรับรูปแบบเอกสารต่างๆ มากมาย รวมถึง PDF, เอกสาร Microsoft Office, รูปภาพ และอื่นๆ อีกมากมาย
### มี GroupDocs.Viewer สำหรับ .NET ให้ทดลองใช้งานฟรีหรือไม่
ใช่ คุณสามารถเข้าถึงการทดลองใช้ฟรีได้จาก [ที่นี่](https://releases-groupdocs.com/).
### ฉันจะรับใบอนุญาตชั่วคราวสำหรับ GroupDocs.Viewer สำหรับ .NET ได้อย่างไร
ใบอนุญาตชั่วคราวสามารถขอรับได้จาก [ลิงค์นี้](https://purchase-groupdocs.com/temporary-license/).
### ฉันสามารถหาเอกสารสำหรับ GroupDocs.Viewer สำหรับ .NET ได้ที่ไหน
มีเอกสารประกอบที่ครอบคลุม [ที่นี่](https://tutorials-groupdocs.com/viewer/net/).
### มีตัวเลือกการสนับสนุนอะไรบ้างสำหรับ GroupDocs.Viewer สำหรับ .NET?
คุณสามารถขอความช่วยเหลือจากฟอรั่มชุมชนได้ [ที่นี่](https://forum-groupdocs.com/c/viewer/9).