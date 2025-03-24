---
title: ตั้งค่าใบอนุญาตจากไฟล์
linktitle: ตั้งค่าใบอนุญาตจากไฟล์
second_title: GroupDocs.Viewer .NET API
description: เรียนรู้วิธีผสานรวม GroupDocs.Viewer สำหรับ .NET เข้ากับแอปพลิเคชันของคุณได้อย่างง่ายดาย ตั้งค่าใบอนุญาต ดูเอกสาร และปรับแต่งรูปลักษณ์ของผู้ดู
weight: 10
url: /th/net/getting-started/set-license-from-file/
---

# ตั้งค่าใบอนุญาตจากไฟล์

## การแนะนำ
GroupDocs.Viewer สำหรับ .NET เป็น API โปรแกรมดูเอกสารอันทรงพลังที่ช่วยให้นักพัฒนา .NET สามารถรวมความสามารถในการดูเอกสารเข้ากับแอปพลิเคชันของตนได้อย่างราบรื่น ไม่ว่าคุณจะต้องการแสดงเอกสารในรูปแบบต่างๆ เช่น PDF, Microsoft Office หรือรูปภาพ GroupDocs.Viewer มอบโซลูชันที่เชื่อถือได้พร้อมตัวเลือกการปรับแต่งที่หลากหลาย
## ข้อกำหนดเบื้องต้น
ก่อนที่จะเจาะลึกการใช้งาน GroupDocs.Viewer สำหรับ .NET ตรวจสอบให้แน่ใจว่าคุณมีข้อกำหนดเบื้องต้นต่อไปนี้:
### 1. ติดตั้ง .NET Framework แล้ว
ตรวจสอบให้แน่ใจว่าคุณได้ติดตั้ง .NET Framework บนเครื่องพัฒนาของคุณแล้ว คุณสามารถดาวน์โหลดได้จากเว็บไซต์ทางการของ Microsoft
### 2. GroupDocs.Viewer สำหรับแพ็คเกจ .NET
 ดาวน์โหลดและติดตั้งแพ็คเกจ GroupDocs.Viewer สำหรับ .NET จาก[ลิ้งค์ดาวน์โหลด](https://releases.groupdocs.com/viewer/net/).
### 3. ไฟล์ใบอนุญาต
 รับไฟล์ลิขสิทธิ์จาก[GroupDocs](https://purchase.groupdocs.com/buy) เพื่อใช้ GroupDocs.Viewer สำหรับ .NET โดยไม่มีข้อจำกัดใดๆ
### 4. ใบอนุญาตชั่วคราว (ไม่บังคับ)
 หากคุณต้องการสำรวจความสามารถของ GroupDocs.Viewer สำหรับ .NET ก่อนที่จะซื้อใบอนุญาต คุณสามารถขอใบอนุญาตชั่วคราวได้จาก[ที่นี่](https://purchase.groupdocs.com/temporary-license/).
### 5. ความคุ้นเคยกับภาษาการเขียนโปรแกรม C#
ความรู้พื้นฐานเกี่ยวกับภาษาการเขียนโปรแกรม C# เป็นสิ่งจำเป็นในการปฏิบัติตามพร้อมกับตัวอย่างที่ให้ไว้ในบทช่วยสอนนี้

## นำเข้าเนมสเปซ
ในโปรเจ็กต์ C# ของคุณ ให้นำเข้าเนมสเปซที่จำเป็นเพื่อใช้ฟังก์ชัน GroupDocs.Viewer สำหรับ .NET

```csharp
using System;
using System.IO;
```

## ขั้นตอนที่ 1: ตรวจสอบการมีอยู่ของไฟล์ลิขสิทธิ์
```csharp
if (File.Exists(Utils.LicensePath))
{
```
## ขั้นตอนที่ 2: ตั้งค่าใบอนุญาตจากไฟล์
```csharp
    License license = new License();
    license.SetLicense(Utils.LicensePath);
    Console.WriteLine("License set successfully.");
}
```
## ขั้นตอนที่ 3: จัดการไฟล์ลิขสิทธิ์ที่หายไป
```csharp
else
{
    Console.WriteLine("\nWe do not ship any license with this example. " +
                      "\nVisit the GroupDocs site to obtain either a temporary or permanent license. " +
                      "\nLearn more about licensing at https://buy.groupdocs.com/faqs/licensing " +
                      "\nLearn how to request temporary license at https://buy.groupdocs.com/temporary-license");
}
```
เมื่อทำตามขั้นตอนเหล่านี้ คุณจะสามารถตั้งค่าใบอนุญาตจากไฟล์ในแอปพลิเคชัน .NET ของคุณโดยใช้ GroupDocs.Viewer

## บทสรุป
โดยสรุป GroupDocs.Viewer สำหรับ .NET นำเสนอโซลูชันที่ราบรื่นสำหรับการรวมความสามารถในการดูเอกสารเข้ากับแอปพลิเคชัน .NET ของคุณ ด้วยการทำตามขั้นตอนที่ระบุไว้ในบทช่วยสอนนี้ คุณสามารถตั้งค่าใบอนุญาตจากไฟล์และปลดล็อกศักยภาพสูงสุดของ GroupDocs.Viewer ได้อย่างง่ายดาย
## คำถามที่พบบ่อย
### ฉันจะขอรับใบอนุญาตถาวรสำหรับ GroupDocs.Viewer สำหรับ .NET ได้อย่างไร
 คุณสามารถซื้อใบอนุญาตถาวรได้จาก[GroupDocs](https://purchase.groupdocs.com/buy) เพื่อใช้ GroupDocs.Viewer โดยไม่มีข้อจำกัดใดๆ
### มีใบอนุญาตชั่วคราวเพื่อวัตถุประสงค์ในการประเมินหรือไม่
 ใช่ คุณสามารถขอใบอนุญาตชั่วคราวได้จาก[ที่นี่](https://purchase.groupdocs.com/temporary-license/) เพื่อประเมิน GroupDocs.Viewer สำหรับ .NET ก่อนตัดสินใจซื้อ
### ฉันสามารถปรับแต่งรูปลักษณ์ของโปรแกรมดูเอกสารได้หรือไม่
ใช่ GroupDocs.Viewer สำหรับ .NET มีตัวเลือกการปรับแต่งที่ครอบคลุมเพื่อปรับแต่งโปรแกรมดูตามความต้องการของคุณ
### GroupDocs.Viewer รองรับเอกสารหลายรูปแบบหรือไม่
ใช่ GroupDocs.Viewer รองรับรูปแบบเอกสารที่หลากหลาย รวมถึง PDF, Microsoft Office, รูปภาพ และอื่นๆ
### ฉันจะรับการสนับสนุนสำหรับ GroupDocs.Viewer สำหรับ .NET ได้ที่ไหน
 คุณสามารถค้นหาการสนับสนุนและความช่วยเหลือได้ที่[ฟอรัม GroupDocs Viewer](https://forum.groupdocs.com/c/viewer/9).