---
title: เรนเดอร์โฟลเดอร์เฉพาะและข้อความกรอง (Outlook)
linktitle: เรนเดอร์โฟลเดอร์เฉพาะและข้อความกรอง (Outlook)
second_title: GroupDocs.Viewer .NET API
description: เรียนรู้วิธีแสดงโฟลเดอร์เฉพาะและกรองข้อความใน Outlook โดยใช้ GroupDocs.Viewer สำหรับ .NET ลดความซับซ้อนในการจัดการเอกสารในแอปพลิเคชัน .NET
type: docs
weight: 11
url: /th/net/rendering-outlook-data-files/render-specific-folders-and-filter-messages-outlook/
---
## การแนะนำ
ในโลกของการพัฒนา .NET การจัดการและการแสดงเอกสารอย่างมีประสิทธิภาพถือเป็นสิ่งสำคัญ GroupDocs.Viewer สำหรับ .NET ช่วยให้งานนี้ง่ายขึ้นโดยมอบฟังก์ชันการทำงานที่มีประสิทธิภาพสำหรับการเรนเดอร์เอกสารรูปแบบต่างๆ ได้อย่างราบรื่น ในบทช่วยสอนนี้ เราจะเจาะลึกวิธีการแสดงโฟลเดอร์เฉพาะและกรองข้อความใน Outlook โดยใช้ GroupDocs.Viewer สำหรับ .NET
## ข้อกำหนดเบื้องต้น
ก่อนที่จะเข้าสู่บทช่วยสอน ตรวจสอบให้แน่ใจว่าคุณมีสิ่งต่อไปนี้:
1.  GroupDocs.Viewer สำหรับ .NET: ตรวจสอบให้แน่ใจว่าคุณได้ติดตั้ง GroupDocs.Viewer สำหรับ .NET แล้ว คุณสามารถดาวน์โหลดได้จาก[เว็บไซต์](https://releases.groupdocs.com/viewer/net/).
2. .NET Framework: คุณต้องติดตั้ง .NET Framework บนเครื่องของคุณ
3. ความเข้าใจพื้นฐานของ C#: ความคุ้นเคยกับภาษาการเขียนโปรแกรม C# จะเป็นประโยชน์ในการปฏิบัติตามพร้อมกับบทช่วยสอน

## นำเข้าเนมสเปซ
ขั้นแรก เรามานำเข้าเนมสเปซที่จำเป็นไปยังโค้ด C# ของเรา:
```csharp
using System;
using System.IO;
using GroupDocs.Viewer.Options;
```

## ขั้นตอนที่ 1: กำหนดไดเรกทอรีผลลัพธ์
```csharp
string outputDirectory = "Your Document Directory";
```
 แทนที่`"Your Document Directory"` ด้วยพาธไดเร็กทอรีที่คุณต้องการให้บันทึกเอกสารที่แสดงผล
## ขั้นตอนที่ 2: กำหนดรูปแบบเส้นทางไฟล์เพจ
```csharp
string pageFilePathFormat = Path.Combine(outputDirectory, "page_{0}.html");
```
 บรรทัดนี้กำหนดรูปแบบสำหรับเส้นทางไฟล์ของแต่ละหน้าที่แสดงผล ในตัวอย่างนี้ มันจะสร้างไฟล์ HTML ชื่อ`page_1.html`, `page_2.html`และอื่นๆ
## ขั้นตอนที่ 3: เริ่มต้นวัตถุ Viewer
```csharp
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_OST_SUBFOLDERS))
```
 ที่นี่เราเริ่มต้น a`Viewer` วัตถุที่มีเส้นทางไปยังโฟลเดอร์ Outlook ตัวอย่าง
## ขั้นตอนที่ 4: กำหนดตัวเลือกมุมมอง HTML
```csharp
HtmlViewOptions options = HtmlViewOptions.ForEmbeddedResources(pageFilePathFormat);
options.OutlookOptions.Folder = "Входящие";
```
 เราสร้างอินสแตนซ์ของ`HtmlViewOptions` และระบุรูปแบบสำหรับทรัพยากรที่ฝังตัว นอกจากนี้ เรายังตั้งค่าโฟลเดอร์ Outlook ที่จะแสดงผลเป็น`"Входящие"` (เข้ามา).
## ขั้นตอนที่ 5: แสดงผลเอกสาร
```csharp
viewer.View(options);
```
บรรทัดนี้ทริกเกอร์กระบวนการเรนเดอร์ด้วยตัวเลือกที่ระบุ
## ขั้นตอนที่ 6: แสดงข้อความแสดงความสำเร็จ
```csharp
Console.WriteLine($"\nSource document rendered successfully.\nCheck output in {outputDirectory}.");
```
หลังจากการเรนเดอร์ ข้อความนี้จะปรากฏขึ้นเพื่อระบุว่ากระบวนการเรนเดอร์เสร็จสมบูรณ์ และนำผู้ใช้ไปยังไดเร็กทอรีเอาต์พุต

## บทสรุป
ในบทช่วยสอนนี้ เราได้ศึกษาวิธีแสดงโฟลเดอร์เฉพาะและกรองข้อความใน Outlook โดยใช้ GroupDocs.Viewer สำหรับ .NET ด้วยการทำตามขั้นตอนที่อธิบายไว้ข้างต้น คุณสามารถจัดการและแสดงเอกสารภายในแอปพลิเคชัน .NET ของคุณได้อย่างมีประสิทธิภาพ
## คำถามที่พบบ่อย
### ฉันสามารถแสดงเอกสารอื่นนอกเหนือจากข้อความ Outlook ด้วย GroupDocs.Viewer สำหรับ .NET ได้หรือไม่
ใช่ GroupDocs.Viewer สำหรับ .NET รองรับรูปแบบเอกสารที่หลากหลาย รวมถึง PDF, DOCX, XLSX และอื่นๆ
### GroupDocs.Viewer สำหรับ .NET เข้ากันได้กับ .NET Core หรือไม่
ใช่ GroupDocs.Viewer สำหรับ .NET เข้ากันได้กับทั้ง .NET Framework และ .NET Core
### ฉันสามารถปรับแต่งรูปแบบเอาต์พุตการเรนเดอร์ได้หรือไม่
แน่นอนว่า GroupDocs.Viewer สำหรับ .NET มีตัวเลือกมากมายในการปรับแต่งเอาท์พุตการเรนเดอร์ รวมถึงรูปแบบ HTML, รูปภาพ และ PDF
### มีรุ่นทดลองใช้สำหรับ GroupDocs.Viewer สำหรับ .NET หรือไม่
 ใช่ คุณสามารถดาวน์โหลดรุ่นทดลองใช้ฟรีได้จาก[เว็บไซต์](https://releases.groupdocs.com/).
### ฉันจะขอความช่วยเหลือหรือสนับสนุน GroupDocs.Viewer for .NET ได้ที่ไหน
 ท่านสามารถเยี่ยมชมได้ที่[ฟอรัม GroupDocs.Viewer](https://forum.groupdocs.com/c/viewer/9) สำหรับความช่วยเหลือหรือข้อสงสัยใด ๆ