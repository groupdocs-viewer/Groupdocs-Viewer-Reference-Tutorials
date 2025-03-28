---
title: ดึงและพิมพ์เอกสารแนบ
linktitle: ดึงและพิมพ์เอกสารแนบ
second_title: GroupDocs.Viewer .NET API
description: ผสานรวมความสามารถในการดูเอกสารเข้ากับแอปพลิเคชัน .NET ของคุณอย่างราบรื่นด้วย GroupDocs.Viewer สำหรับ .NET ดึงและพิมพ์เอกสารแนบได้อย่างง่ายดาย
weight: 11
url: /th/net/processing-document-attachments/retrieve-and-print-attachments/
---

# ดึงและพิมพ์เอกสารแนบ

## การแนะนำ
ในโลกของการพัฒนาซอฟต์แวร์ การจัดการและการแสดงเอกสารอย่างมีประสิทธิภาพภายในแอปพลิเคชันถือเป็นสิ่งสำคัญ GroupDocs.Viewer สำหรับ .NET มอบโซลูชันอันทรงพลังสำหรับนักพัฒนาเพื่อรวมความสามารถในการดูเอกสารเข้ากับแอปพลิเคชัน .NET ของตนได้อย่างราบรื่น ไม่ว่าคุณจะสร้างระบบการจัดการเอกสารระดับองค์กรหรือโปรแกรมดูเอกสารแบบธรรมดา GroupDocs.Viewer มีชุดคุณลักษณะที่ครอบคลุมเพื่อตอบสนองความต้องการของคุณ
## ข้อกำหนดเบื้องต้น
ก่อนที่เราจะเจาะลึกในการผสานรวม GroupDocs.Viewer สำหรับ .NET เข้ากับโปรเจ็กต์ของคุณ มีข้อกำหนดเบื้องต้นบางประการที่คุณต้องมี:
### 1. การตั้งค่าสภาพแวดล้อม .NET
ตรวจสอบให้แน่ใจว่าคุณได้ติดตั้งเฟรมเวิร์ก .NET บนเครื่องพัฒนาของคุณ GroupDocs.Viewer สำหรับ .NET รองรับเฟรมเวิร์ก .NET เวอร์ชันต่างๆ ดังนั้น ตรวจสอบให้แน่ใจว่าคุณใช้เวอร์ชันที่เข้ากันได้สำหรับโปรเจ็กต์ของคุณ
### 2. การติดตั้ง GroupDocs.Viewer
 ดาวน์โหลดและติดตั้งไลบรารี GroupDocs.Viewer สำหรับ .NET จาก[ลิ้งค์ดาวน์โหลด](https://releases.groupdocs.com/viewer/net/)ปฏิบัติตามคำแนะนำในการติดตั้งที่ให้ไว้เพื่อตั้งค่าไลบรารีในสภาพแวดล้อมการพัฒนาของคุณ
### 3. ใบอนุญาตที่ถูกต้อง (ไม่บังคับ)
 แม้ว่า GroupDocs.Viewer สำหรับ .NET สามารถใช้งานได้โดยไม่ต้องมีใบอนุญาต แต่การได้รับใบอนุญาตที่ถูกต้องจะปลดล็อกคุณสมบัติเพิ่มเติมและลบข้อจำกัดในการประเมินใดๆ คุณสามารถขอรับใบอนุญาตได้จาก[หน้าซื้อ](https://purchase.groupdocs.com/buy) หรือขอใบอนุญาตชั่วคราวเพื่อการทดสอบจาก[ที่นี่](https://purchase.groupdocs.com/temporary-license/).

## นำเข้าเนมสเปซ
เมื่อคุณมีข้อกำหนดเบื้องต้นแล้ว คุณสามารถเริ่มผสานรวม GroupDocs.Viewer สำหรับ .NET เข้ากับโปรเจ็กต์ของคุณได้ เริ่มต้นด้วยการนำเข้าเนมสเปซที่จำเป็นลงในโค้ดเบสของคุณ
## นำเข้าเนมสเปซ
```csharp
using System;
using System.Collections.Generic;
using GroupDocs.Viewer.Results;
```

ตอนนี้คุณได้ตั้งค่าทุกอย่างเรียบร้อยแล้ว มาดูวิธีเรียกค้นและพิมพ์เอกสารแนบโดยใช้ GroupDocs.Viewer สำหรับ .NET กัน ทำตามคำแนะนำทีละขั้นตอนเหล่านี้เพื่อรวมฟังก์ชันนี้เข้ากับแอปพลิเคชัน .NET ของคุณ:
## ขั้นตอนที่ 1: เริ่มต้นวัตถุ Viewer
 ในการเริ่มต้น ให้สร้างอินสแตนซ์ของ`Viewer` และส่งเส้นทางไปยังเอกสารที่คุณต้องการดูเป็นพารามิเตอร์
```csharp
using (Viewer viewer = new Viewer("path/to/your/document"))
{
    // รหัสไปที่นี่
}
```
## ขั้นตอนที่ 2: ดึงไฟล์แนบ
 ภายใน`using`บล็อค โทร`GetAttachments()` วิธีการของ`Viewer` วัตถุเพื่อดึงรายการเอกสารแนบที่เกี่ยวข้องกับเอกสาร
```csharp
IList<Attachment> attachments = viewer.GetAttachments();
```
## ขั้นตอนที่ 3: พิมพ์สิ่งที่แนบมา
วนซ้ำรายการไฟล์แนบและพิมพ์แต่ละไฟล์แนบไปยังคอนโซลหรือดำเนินการอื่นๆ ที่ต้องการ
```csharp
Console.WriteLine("\nAttachments:");
foreach (Attachment attachment in attachments)
    Console.WriteLine(attachment);
```
## ขั้นตอนที่ 4: แสดงข้อความแสดงความสำเร็จ
สุดท้าย ให้พิมพ์ข้อความแจ้งว่าได้รับไฟล์แนบเรียบร้อยแล้ว
```csharp
Console.WriteLine("\nAttachments retrieved successfully.");
```

## บทสรุป
โดยสรุป การรวมความสามารถในการดูเอกสารและการจัดการเข้ากับแอปพลิเคชัน .NET ของคุณนั้นง่ายขึ้นด้วย GroupDocs.Viewer สำหรับ .NET ด้วยการทำตามขั้นตอนที่ระบุไว้ในบทช่วยสอนนี้ คุณสามารถเรียกค้นและพิมพ์เอกสารแนบภายในแอปพลิเคชันของคุณได้อย่างง่ายดาย ด้วยเอกสารประกอบที่กว้างขวางและทรัพยากรสนับสนุน GroupDocs.Viewer ช่วยให้นักพัฒนาสามารถสร้างโซลูชันที่มีประสิทธิภาพซึ่งเน้นเอกสารเป็นศูนย์กลาง
## คำถามที่พบบ่อย
### GroupDocs.Viewer สำหรับ .NET เข้ากันได้กับรูปแบบเอกสารทั้งหมดหรือไม่
GroupDocs.Viewer สำหรับ .NET รองรับรูปแบบเอกสารที่หลากหลาย รวมถึง PDF, Microsoft Office, OpenDocument และอื่นๆ อีกมากมาย โปรดดูเอกสารประกอบสำหรับรายการรูปแบบที่รองรับทั้งหมด
### ฉันสามารถปรับแต่งรูปลักษณ์ของโปรแกรมดูเอกสารในแอปพลิเคชันของฉันได้หรือไม่
ใช่ GroupDocs.Viewer สำหรับ .NET มีตัวเลือกมากมายสำหรับการปรับแต่งรูปลักษณ์และการทำงานของโปรแกรมดูเอกสาร ซึ่งช่วยให้คุณปรับแต่งให้ตรงกับความต้องการของแอปพลิเคชันของคุณได้
### GroupDocs.Viewer สำหรับ .NET จำเป็นต้องเชื่อมต่ออินเทอร์เน็ตเพื่อดูเอกสารหรือไม่
ไม่ GroupDocs.Viewer สำหรับ .NET เป็นไลบรารีแบบครบวงจรที่ไม่ต้องใช้อินเทอร์เน็ตในการดูเอกสาร การประมวลผลทั้งหมดเสร็จสิ้นภายในแอปพลิเคชันของคุณ
### GroupDocs.Viewer สำหรับ .NET มีรุ่นทดลองใช้ฟรีหรือไม่
 ใช่ คุณสามารถดาวน์โหลด GroupDocs.Viewer สำหรับ .NET เวอร์ชันทดลองใช้ฟรีได้จาก[ที่นี่](https://releases.groupdocs.com/).
### ฉันจะขอความช่วยเหลือได้ที่ไหนหากฉันประสบปัญหาขณะใช้ GroupDocs.Viewer for .NET
 คุณสามารถขอความช่วยเหลือได้จากฟอรัมชุมชน GroupDocs.Viewer[ที่นี่](https://forum.groupdocs.com/c/viewer/9) หรือติดต่อทีมสนับสนุนเพื่อขอความช่วยเหลือโดยตรง