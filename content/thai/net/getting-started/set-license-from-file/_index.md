---
"description": "เรียนรู้วิธีการผสานรวม GroupDocs.Viewer สำหรับ .NET เข้ากับแอปพลิเคชันของคุณได้อย่างง่ายดาย กำหนดใบอนุญาต ดูเอกสาร และปรับแต่งรูปลักษณ์ของโปรแกรมดู"
"linktitle": "ตั้งค่าใบอนุญาตจากไฟล์"
"second_title": "API ของ GroupDocs.Viewer .NET"
"title": "ตั้งค่าใบอนุญาตจากไฟล์"
"url": "/th/net/getting-started/set-license-from-file/"
"weight": 10
---

# ตั้งค่าใบอนุญาตจากไฟล์

## การแนะนำ
GroupDocs.Viewer สำหรับ .NET เป็น API สำหรับดูเอกสารอันทรงพลังที่ช่วยให้นักพัฒนา .NET สามารถผสานรวมความสามารถในการดูเอกสารเข้ากับแอปพลิเคชันของตนได้อย่างราบรื่น ไม่ว่าคุณจะต้องแสดงเอกสารในรูปแบบต่างๆ เช่น PDF, Microsoft Office หรือรูปภาพ GroupDocs.Viewer ก็มีโซลูชันที่เชื่อถือได้พร้อมตัวเลือกการปรับแต่งมากมาย

![ตั้งค่าใบอนุญาตจากไฟล์ด้วย GroupDocs.Viewer สำหรับ .NET](/viewer/getting-started/set-license-from-file.png)

## ข้อกำหนดเบื้องต้น
ก่อนจะเริ่มใช้งาน GroupDocs.Viewer สำหรับ .NET โปรดตรวจสอบให้แน่ใจว่าคุณมีข้อกำหนดเบื้องต้นดังต่อไปนี้:
### 1. ติดตั้ง .NET Framework
ตรวจสอบให้แน่ใจว่าคุณได้ติดตั้ง .NET Framework ไว้ในเครื่องพัฒนาของคุณแล้ว คุณสามารถดาวน์โหลดได้จากเว็บไซต์ทางการของ Microsoft
### 2. GroupDocs.Viewer สำหรับแพ็คเกจ .NET
ดาวน์โหลดและติดตั้งแพ็คเกจ GroupDocs.Viewer สำหรับ .NET จาก [ลิงค์ดาวน์โหลด](https://releases-groupdocs.com/viewer/net/).
### 3. ไฟล์ลิขสิทธิ์
รับไฟล์ลิขสิทธิ์จาก [เอกสารกลุ่ม](https://purchase.groupdocs.com/buy) เพื่อใช้ GroupDocs.Viewer สำหรับ .NET โดยไม่มีข้อจำกัดใดๆ
### 4. ใบอนุญาตชั่วคราว (ทางเลือก)
หากคุณต้องการสำรวจความสามารถของ GroupDocs.Viewer สำหรับ .NET ก่อนที่จะซื้อใบอนุญาต คุณสามารถขอใบอนุญาตชั่วคราวได้จาก [ที่นี่](https://purchase-groupdocs.com/temporary-license/).
### 5. ความคุ้นเคยกับภาษาการเขียนโปรแกรม C#
ความรู้พื้นฐานเกี่ยวกับภาษาการเขียนโปรแกรม C# ถือเป็นสิ่งสำคัญที่ต้องปฏิบัติตามพร้อมกับตัวอย่างที่ให้ไว้ในบทช่วยสอนนี้

## นำเข้าเนมสเปซ
ในโครงการ C# ของคุณ นำเข้าเนมสเปซที่จำเป็นเพื่อใช้ GroupDocs.Viewer สำหรับฟังก์ชันการทำงานของ .NET

```csharp
using System;
using System.IO;
```

## ขั้นตอนที่ 1: ตรวจสอบการมีอยู่ของไฟล์ใบอนุญาต
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
## ขั้นตอนที่ 3: จัดการไฟล์ใบอนุญาตที่หายไป
```csharp
else
{
    Console.WriteLine("\nWe do not ship any license with this example. " +
                      "\nVisit the GroupDocs site to obtain either a temporary or permanent license. " +
                      "\nLearn more about licensing at https://purchase.groupdocs.com/faqs/licensing " +
                      "\nLearn how to request temporary license at https://purchase.groupdocs.com/temporary-license.");
}
```
หากทำตามขั้นตอนเหล่านี้ คุณจะสามารถตั้งค่าใบอนุญาตจากไฟล์ในแอปพลิเคชัน .NET ของคุณโดยใช้ GroupDocs.Viewer ได้

## บทสรุป
โดยสรุป GroupDocs.Viewer สำหรับ .NET นำเสนอโซลูชันที่ราบรื่นสำหรับการผสานรวมความสามารถในการดูเอกสารเข้ากับแอปพลิเคชัน .NET ของคุณ โดยทำตามขั้นตอนที่ระบุไว้ในบทช่วยสอนนี้ คุณสามารถตั้งค่าใบอนุญาตจากไฟล์ได้อย่างง่ายดายและปลดล็อกศักยภาพทั้งหมดของ GroupDocs.Viewer
## คำถามที่พบบ่อย
### ฉันจะรับใบอนุญาตถาวรสำหรับ GroupDocs.Viewer สำหรับ .NET ได้อย่างไร
คุณสามารถซื้อใบอนุญาตถาวรได้จาก [เอกสารกลุ่ม](https://purchase.groupdocs.com/buy) เพื่อใช้ GroupDocs.Viewer โดยไม่มีข้อจำกัดใดๆ
### ใบอนุญาตชั่วคราวมีไว้เพื่อวัตถุประสงค์ในการประเมินผลหรือไม่?
ใช่ คุณสามารถขอใบอนุญาตชั่วคราวได้จาก [ที่นี่](https://purchase.groupdocs.com/temporary-license/) เพื่อประเมิน GroupDocs.Viewer สำหรับ .NET ก่อนตัดสินใจซื้อ
### ฉันสามารถปรับแต่งลักษณะที่ปรากฏของโปรแกรมดูเอกสารได้หรือไม่
ใช่ GroupDocs.Viewer สำหรับ .NET มีตัวเลือกการปรับแต่งมากมายเพื่อปรับแต่งโปรแกรมดูให้ตรงตามความต้องการของคุณ
### GroupDocs.Viewer รองรับรูปแบบเอกสารหลายรูปแบบหรือไม่
ใช่ GroupDocs.Viewer รองรับรูปแบบเอกสารต่างๆ มากมาย รวมถึง PDF, Microsoft Office, รูปภาพ และอื่นๆ อีกมากมาย
### ฉันสามารถค้นหาการสนับสนุนสำหรับ GroupDocs.Viewer สำหรับ .NET ได้ที่ไหน
คุณสามารถค้นหาการสนับสนุนและความช่วยเหลือได้ที่ [ฟอรั่ม GroupDocs Viewer](https://forum-groupdocs.com/c/viewer/9).