---
title: ดึงและบันทึกเอกสารแนบ
linktitle: ดึงและบันทึกเอกสารแนบ
second_title: GroupDocs.Viewer .NET API
description: จัดการเอกสารแนบภายในแอปพลิเคชัน .NET อย่างมีประสิทธิภาพโดยใช้ GroupDocs.Viewer ดึงและบันทึกไฟล์แนบโดยไม่ยุ่งยาก
weight: 12
url: /th/net/processing-document-attachments/retrieve-and-save-attachments/
---

# ดึงและบันทึกเอกสารแนบ

## การแนะนำ
ในยุคดิจิทัล การจัดการเอกสารที่มีประสิทธิภาพถือเป็นสิ่งสำคัญสำหรับธุรกิจและบุคคลทั่วไป ไม่ว่าจะเป็นการจัดการอีเมล การดูสัญญา หรือการเข้าถึงรายงาน การมีเครื่องมือที่เชื่อถือได้สำหรับการแสดงภาพเอกสารถือเป็นสิ่งสำคัญ GroupDocs.Viewer สำหรับ .NET กลายเป็นโซลูชันที่มีประสิทธิภาพ ช่วยให้ผู้ใช้สามารถดูและโต้ตอบกับเอกสารรูปแบบต่างๆ ได้โดยตรงภายในแอปพลิเคชัน .NET ของตนได้อย่างง่ายดาย
## ข้อกำหนดเบื้องต้น
ก่อนที่จะเจาะลึกการใช้ GroupDocs.Viewer สำหรับ .NET สำหรับการเรียกและบันทึกไฟล์แนบเอกสาร ตรวจสอบให้แน่ใจว่าคุณมีข้อกำหนดเบื้องต้นต่อไปนี้:
1. สภาพแวดล้อมการทำงาน: สภาพแวดล้อมการทำงานที่ตั้งค่าด้วย .NET Framework
2.  การติดตั้ง: ดาวน์โหลดและติดตั้งไลบรารี GroupDocs.Viewer สำหรับ .NET ท่านสามารถเข้าใช้บริการห้องสมุดได้จาก[ลิ้งค์ดาวน์โหลด](https://releases.groupdocs.com/viewer/net/).
3. ความเข้าใจพื้นฐาน: ความคุ้นเคยกับภาษาการเขียนโปรแกรม C#
4. แหล่งที่มาของเอกสาร: เข้าถึงเอกสารตัวอย่างพร้อมไฟล์แนบเพื่อวัตถุประสงค์ในการสาธิต

## นำเข้าเนมสเปซ
หากต้องการเริ่มใช้ GroupDocs.Viewer สำหรับ .NET สำหรับการเรียกและบันทึกไฟล์แนบเอกสาร ให้นำเข้าเนมสเปซที่จำเป็น:
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
กำหนดไดเร็กทอรีที่คุณต้องการบันทึกไฟล์แนบที่ดึงมาจากเอกสาร
## ขั้นตอนที่ 2: สร้างอินสแตนซ์ของวัตถุ Viewer
```csharp
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_MSG_WITH_ATTACHMENTS))
```
สร้างอินสแตนซ์ของวัตถุ Viewer ด้วยเส้นทางไปยังเอกสารที่มีไฟล์แนบ
## ขั้นตอนที่ 3: ดึงไฟล์แนบ
```csharp
IList<Attachment> attachments = viewer.GetAttachments();
```
ดึงรายการเอกสารแนบที่มีอยู่ในเอกสาร
## ขั้นตอนที่ 4: บันทึกไฟล์แนบ
```csharp
foreach(Attachment attachment in attachments)
{
    string filePath = Path.Combine(outputDirectory, attachment.FileName);  
    viewer.SaveAttachment(attachment, File.OpenWrite(filePath)); 
}
```
วนซ้ำแต่ละไฟล์แนบ กำหนดพาธของไฟล์ และบันทึกไฟล์แนบลงในไดเร็กทอรีที่ระบุ
## ขั้นตอนที่ 5: แสดงข้อความแสดงความสำเร็จ
```csharp
Console.WriteLine($"\nAttachments saved successfully.\nCheck output in {outputDirectory}.");
```
แสดงข้อความแจ้งว่าบันทึกไฟล์แนบได้สำเร็จพร้อมกับเส้นทางไดเร็กทอรี

## บทสรุป
การรวม GroupDocs.Viewer สำหรับ .NET เข้ากับเวิร์กโฟลว์การจัดการเอกสารของคุณจะช่วยเพิ่มความคล่องตัวให้กับกระบวนการจัดการไฟล์แนบ โดยให้ประสิทธิภาพและความสะดวกสบาย ด้วยการทำตามคำแนะนำทีละขั้นตอนที่อธิบายไว้ข้างต้น ผู้ใช้สามารถเรียกดูและบันทึกเอกสารแนบภายในแอปพลิเคชัน .NET ของตนได้อย่างราบรื่น
## คำถามที่พบบ่อย
### GroupDocs.Viewer for .NET สามารถจัดการเอกสารรูปแบบต่างๆ ได้หรือไม่
ใช่ GroupDocs.Viewer รองรับรูปแบบเอกสารที่หลากหลาย รวมถึง PDF, เอกสาร Microsoft Office, รูปภาพ และอื่นๆ
### GroupDocs.Viewer สำหรับ .NET มีรุ่นทดลองใช้ฟรีหรือไม่
 ใช่ คุณสามารถเข้าถึงการทดลองใช้ฟรีได้จาก[ที่นี่](https://releases.groupdocs.com/).
### ฉันจะขอรับใบอนุญาตชั่วคราวสำหรับ GroupDocs.Viewer สำหรับ .NET ได้อย่างไร
 สามารถรับใบอนุญาตชั่วคราวได้จาก[ลิงค์นี้](https://purchase.groupdocs.com/temporary-license/).
### ฉันจะหาเอกสารสำหรับ GroupDocs.Viewer for .NET ได้ที่ไหน
 มีเอกสารประกอบครบถ้วน[ที่นี่](https://tutorials.groupdocs.com/viewer/net/).
### ตัวเลือกการสนับสนุนใดบ้างสำหรับ GroupDocs.Viewer สำหรับ .NET
 คุณสามารถขอความช่วยเหลือได้จากฟอรัมชุมชน[ที่นี่](https://forum.groupdocs.com/c/viewer/9).