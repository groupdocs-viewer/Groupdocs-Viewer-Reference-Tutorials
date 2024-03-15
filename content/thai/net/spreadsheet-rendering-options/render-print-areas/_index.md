---
title: แสดงผลพื้นที่การพิมพ์ด้วย GroupDocs.Viewer สำหรับ .NET
linktitle: แสดงผลพื้นที่การพิมพ์
second_title: GroupDocs.Viewer .NET API
description: สำรวจ GroupDocs.Viewer สำหรับ .NET และเรนเดอร์พื้นที่พิมพ์ในรูปแบบเอกสารต่างๆ ได้อย่างง่ายดาย ลองทดลองใช้ฟรีทันที! #GroupDocsโปรแกรมดู
type: docs
weight: 17
url: /th/net/spreadsheet-rendering-options/render-print-areas/
---
## การแนะนำ
ยินดีต้อนรับสู่คู่มือที่ครอบคลุมเกี่ยวกับการใช้ประโยชน์จาก GroupDocs.Viewer สำหรับ .NET เพื่อแสดงผลพื้นที่การพิมพ์ในเอกสารของคุณ หากคุณเป็นนักพัฒนา .NET ที่กำลังมองหาโซลูชันที่มีประสิทธิภาพสำหรับการแสดงเอกสาร แสดงว่าคุณมาถูกที่แล้ว ในบทช่วยสอนนี้ เราจะแนะนำคุณตลอดขั้นตอนการเรนเดอร์พื้นที่พิมพ์โดยใช้ GroupDocs.Viewer เพื่อให้มั่นใจว่าแอปพลิเคชันของคุณจะได้รับประสบการณ์ที่ราบรื่น
## ข้อกำหนดเบื้องต้น
ก่อนที่จะเข้าสู่บทช่วยสอน ตรวจสอบให้แน่ใจว่าคุณมีข้อกำหนดเบื้องต้นต่อไปนี้:
- ความรู้ด้านการทำงานของการพัฒนา C# และ .NET
-  ติดตั้ง GroupDocs.Viewer สำหรับ .NET แล้ว คุณสามารถดาวน์โหลดได้[ที่นี่](https://releases.groupdocs.com/viewer/net/).
- เอกสารตัวอย่าง (เช่น "SAMPLE.XLSX") ในไดเร็กทอรีเอกสารที่คุณระบุ
## นำเข้าเนมสเปซ
ตรวจสอบให้แน่ใจว่าได้นำเข้าเนมสเปซที่จำเป็นในโค้ด C# ของคุณเพื่อการใช้งานที่เหมาะสม:
```csharp
using System;
using System.IO;
using GroupDocs.Viewer.Options;
```
## ขั้นตอนที่ 1: ตั้งค่าไดเร็กทอรีเอกสาร
เริ่มต้นด้วยการระบุไดเร็กทอรีเอาต์พุตสำหรับเพจ HTML ที่แสดงผล:
```csharp
string outputDirectory = "Your Document Directory";
```
## ขั้นตอนที่ 2: กำหนดรูปแบบเส้นทางไฟล์เพจ
สร้างรูปแบบสำหรับเส้นทางไฟล์เพจ รวมไดเร็กทอรีเอาต์พุตและตัวยึดตำแหน่งสำหรับหมายเลขหน้า:
```csharp
string pageFilePathFormat = Path.Combine(outputDirectory, "page_{0}.html");
```
## ขั้นตอนที่ 3: เริ่มต้น GroupDocs.Viewer
สร้างอินสแตนซ์คลาส Viewer ด้วยเส้นทางไปยังเอกสารตัวอย่างของคุณ:
```csharp
using (Viewer viewer = new Viewer("SAMPLE.XLSX"))
{
```
## ขั้นตอนที่ 4: กำหนดค่าตัวเลือกมุมมอง HTML
กำหนดค่าตัวเลือกมุมมอง HTML ระบุรูปแบบพาธของไฟล์เพจ และเปิดใช้งานตัวเลือกสำหรับการแสดงผลพื้นที่พิมพ์:
```csharp
HtmlViewOptions options = HtmlViewOptions.ForEmbeddedResources(pageFilePathFormat);
options.SpreadsheetOptions = SpreadsheetOptions.ForRenderingPrintArea();
```
## ขั้นตอนที่ 5: แสดงผลเอกสาร
 เรียกใช้`View` วิธีการแสดงเอกสารด้วยตัวเลือกที่ระบุ:
```csharp
viewer.View(options);
```
## ขั้นตอนที่ 6: แสดงข้อความแสดงความสำเร็จ
พิมพ์ข้อความแจ้งว่าเอกสารต้นฉบับแสดงผลสำเร็จแล้ว:
```csharp
Console.WriteLine($"\nSource document rendered successfully.\nCheck output in {outputDirectory}.");
```
## บทสรุป
ยินดีด้วย! คุณได้เรียนรู้วิธีใช้ GroupDocs.Viewer สำหรับ .NET เพื่อแสดงพื้นที่การพิมพ์ในเอกสารของคุณสำเร็จแล้ว เครื่องมืออันทรงพลังนี้เปิดโอกาสใหม่ๆ สำหรับการแสดงเอกสารในแอปพลิเคชัน .NET ของคุณ
## คำถามที่พบบ่อย
### GroupDocs.Viewer เข้ากันได้กับรูปแบบเอกสารที่แตกต่างกันหรือไม่
 ใช่ GroupDocs.Viewer รองรับรูปแบบเอกสารที่หลากหลาย รวมถึง PDF, DOCX, XLSX และอื่นๆ อ้างถึง[เอกสารประกอบ](https://reference.groupdocs.com/viewer/net/) สำหรับรายการทั้งหมด
### ฉันสามารถลองใช้ GroupDocs.Viewer ก่อนตัดสินใจซื้อได้หรือไม่
 อย่างแน่นอน! คุณสามารถสำรวจเครื่องมือนี้พร้อมให้ทดลองใช้ฟรี[ที่นี่](https://releases.groupdocs.com/).
### ฉันจะรับการสนับสนุนหรือขอความช่วยเหลือสำหรับปัญหาต่างๆ ได้ที่ไหน?
 เยี่ยมชม[ฟอรัม GroupDocs.Viewer](https://forum.groupdocs.com/c/viewer/9)เพื่อเชื่อมต่อกับชุมชนและรับความช่วยเหลือ
### มีตัวเลือกใบอนุญาตชั่วคราวหรือไม่?
 ใช่ คุณสามารถขอรับใบอนุญาตชั่วคราวได้[ที่นี่](https://purchase.groupdocs.com/temporary-license/).
### ฉันจะซื้อ GroupDocs.Viewer สำหรับ .NET ได้ที่ไหน
 คุณสามารถซื้อได้[ที่นี่](https://purchase.groupdocs.com/buy).