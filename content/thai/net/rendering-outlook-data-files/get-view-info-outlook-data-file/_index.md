---
title: รับข้อมูลการดูสำหรับไฟล์ข้อมูล Outlook (PST, OST)
linktitle: รับข้อมูลการดูสำหรับไฟล์ข้อมูล Outlook (PST, OST)
second_title: GroupDocs.Viewer .NET API
description: สำรวจวิธีดึงข้อมูลการดูจากไฟล์ข้อมูล Outlook (PST, OST) โดยใช้ GroupDocs.Viewer สำหรับ .NET เพิ่มความสามารถในการจัดการเอกสารของคุณได้อย่างง่ายดาย
weight: 10
url: /th/net/rendering-outlook-data-files/get-view-info-outlook-data-file/
---

# รับข้อมูลการดูสำหรับไฟล์ข้อมูล Outlook (PST, OST)

## การแนะนำ
ในด้านการจัดการและการดูเอกสาร GroupDocs.Viewer สำหรับ .NET ถือเป็นเครื่องมืออันทรงพลัง โดยเฉพาะอย่างยิ่งเมื่อต้องจัดการไฟล์ข้อมูล Outlook (PST, OST) ในบทช่วยสอนนี้ เราจะเจาะลึกกระบวนการแยกข้อมูลมุมมองสำหรับไฟล์เหล่านี้ทีละขั้นตอน
## ข้อกำหนดเบื้องต้น
ก่อนที่เราจะเริ่มบทช่วยสอนนี้ ตรวจสอบให้แน่ใจว่าคุณมีข้อกำหนดเบื้องต้นต่อไปนี้:
### 1. การติดตั้ง GroupDocs.Viewer สำหรับ .NET
 ประการแรก คุณต้องติดตั้ง GroupDocs.Viewer สำหรับ .NET ในสภาพแวดล้อมการพัฒนาของคุณ คุณสามารถดาวน์โหลดแพ็คเกจที่จำเป็นได้จาก[GroupDocs.Viewer สำหรับเว็บไซต์ .NET](https://releases.groupdocs.com/viewer/net/).
### 2. ความคุ้นเคยกับภาษาการเขียนโปรแกรม C#
ความรู้พื้นฐานเกี่ยวกับภาษาการเขียนโปรแกรม C# ถือเป็นสิ่งสำคัญในการทำความเข้าใจและนำตัวอย่างโค้ดที่ให้มาไปใช้
### 3. ไฟล์ข้อมูล Outlook (PST, OST)
ตรวจสอบให้แน่ใจว่าคุณมีไฟล์ข้อมูล Outlook (PST, OST) สำหรับการทดสอบ คุณสามารถรับไฟล์ตัวอย่างจากแหล่งต่างๆ หรือใช้ไฟล์ข้อมูลของคุณเอง

## นำเข้าเนมสเปซ
ก่อนที่จะเจาะลึกโค้ด เราต้องแน่ใจว่าเรานำเข้าเนมสเปซที่จำเป็น:
```csharp
using System;
using GroupDocs.Viewer.Options;
using GroupDocs.Viewer.Results;
```

ตอนนี้ เรามาแบ่งตัวอย่างที่ให้ไว้ออกเป็นหลายขั้นตอน:
## ขั้นตอนที่ 1: สร้างอินสแตนซ์ของวัตถุ Viewer
```csharp
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_OST_SUBFOLDERS))
```
ที่นี่ เรากำลังเริ่มต้นวัตถุ Viewer ด้วยเส้นทางไปยังไฟล์ข้อมูล Outlook (OST) ที่ระบุเป็นอาร์กิวเมนต์
## ขั้นตอนที่ 2: กำหนดค่าตัวเลือกข้อมูลมุมมอง
```csharp
ViewInfoOptions options = ViewInfoOptions.ForHtmlView();
```
เรากำลังตั้งค่าตัวเลือกสำหรับการดึงข้อมูลมุมมอง ในกรณีนี้ เรากำลังเลือกใช้มุมมอง HTML
## ขั้นตอนที่ 3: ดึงข้อมูลมุมมอง Outlook
```csharp
OutlookViewInfo rootFolderInfo = viewer.GetViewInfo(options) as OutlookViewInfo;
```
บรรทัดนี้จะดึงข้อมูลมุมมองสำหรับไฟล์ข้อมูล Outlook
## ขั้นตอนที่ 4: แสดงประเภทไฟล์และจำนวนหน้า
```csharp
Console.WriteLine("File type is: " + rootFolderInfo.FileType);
Console.WriteLine("Pages count: " + rootFolderInfo.Pages.Count);
```
เรากำลังพิมพ์ประเภทไฟล์และจำนวนหน้าในไฟล์ข้อมูล Outlook
## ขั้นตอนที่ 5: วนซ้ำผ่านโฟลเดอร์
```csharp
foreach (string folder in rootFolderInfo.Folders)
    Console.WriteLine(folder);
```
การวนซ้ำนี้จะวนซ้ำตามโฟลเดอร์ต่างๆ ที่อยู่ภายในไฟล์ข้อมูล Outlook และพิมพ์ชื่อ
## ขั้นตอนที่ 6: สิ้นสุดการดึงข้อมูล
```csharp
Console.WriteLine("\nView info retrieved successfully.");
```
ข้อความระบุว่าการดึงข้อมูลมุมมองสำเร็จจะปรากฏขึ้น

## บทสรุป
GroupDocs.Viewer สำหรับ .NET มอบโซลูชันที่ราบรื่นสำหรับการดึงข้อมูลมุมมองจากไฟล์ข้อมูล Outlook (PST, OST) ด้วยการทำตามขั้นตอนที่ระบุไว้ในบทช่วยสอนนี้ คุณจะได้รับข้อมูลเชิงลึกอันมีค่าเกี่ยวกับไฟล์เหล่านี้เพื่อการจัดการเอกสารที่ได้รับการปรับปรุงได้อย่างง่ายดาย
## คำถามที่พบบ่อย
### GroupDocs.Viewer สำหรับ .NET เข้ากันได้กับไฟล์ข้อมูล Outlook เวอร์ชันต่างๆ หรือไม่
ใช่ GroupDocs.Viewer สำหรับ .NET รองรับไฟล์ข้อมูล Outlook เวอร์ชันต่างๆ เพื่อให้มั่นใจถึงความเข้ากันได้ในสภาพแวดล้อมที่แตกต่างกัน
### ฉันสามารถปรับแต่งตัวเลือกมุมมองสำหรับไฟล์ข้อมูล Outlook โดยใช้ GroupDocs.Viewer สำหรับ .NET ได้หรือไม่
อย่างแน่นอน! GroupDocs.Viewer สำหรับ .NET นำเสนอตัวเลือกการปรับแต่งที่หลากหลาย ช่วยให้คุณปรับแต่งประสบการณ์การรับชมได้ตามความต้องการของคุณ
### GroupDocs.Viewer for .NET รองรับรูปแบบไฟล์อื่นๆ นอกเหนือจากไฟล์ข้อมูล Outlook หรือไม่
ใช่ GroupDocs.Viewer สำหรับ .NET รองรับรูปแบบไฟล์ที่หลากหลาย รวมถึงแต่ไม่จำกัดเฉพาะ PDF, DOCX, XLSX และอื่นๆ
### GroupDocs.Viewer สำหรับ .NET มีรุ่นทดลองใช้ฟรีหรือไม่
 ใช่ คุณสามารถเข้าถึง GroupDocs.Viewer สำหรับ .NET รุ่นทดลองใช้ฟรีได้จากเว็บไซต์:[ทดลองฟรี](https://releases.groupdocs.com/).
### ฉันจะรับการสนับสนุนหรือความช่วยเหลือเพิ่มเติมสำหรับ GroupDocs.Viewer for .NET ได้ที่ไหน
 หากมีข้อสงสัยหรือความช่วยเหลือ คุณสามารถไปที่ฟอรัมสนับสนุน GroupDocs.Viewer สำหรับ .NET:[สนับสนุน](https://forum.groupdocs.com/c/viewer/9).