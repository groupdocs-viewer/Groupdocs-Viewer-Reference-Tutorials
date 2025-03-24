---
title: รับชื่อแผ่นงาน
linktitle: รับชื่อแผ่นงาน
second_title: GroupDocs.Viewer .NET API
description: สำรวจความมหัศจรรย์ของ GroupDocs.Viewer สำหรับ .NET – ผสานรวมการดูเอกสารเข้ากับแอปพลิเคชันของคุณได้อย่างราบรื่น ลองทดลองใช้ฟรีทันที!
weight: 11
url: /th/net/spreadsheet-rendering-options/get-worksheets-names/
---
## การแนะนำ
ยินดีต้อนรับสู่โลกอันน่าทึ่งของ GroupDocs.Viewer สำหรับ .NET! หากคุณเป็นนักพัฒนาหรือผู้ที่กระตือรือร้นในการสำรวจความสามารถอันทรงพลังในการดูเอกสารภายในแอปพลิเคชัน .NET ของคุณ คุณจะได้รับสิทธิพิเศษ ในคู่มือที่ครอบคลุมนี้ เราจะเจาะลึกความซับซ้อนของการเรียกชื่อเวิร์กชีทโดยใช้ GroupDocs.Viewer คาดเข็มขัดนิรภัยแล้วเริ่มต้นการเดินทางที่น่าตื่นเต้นนี้กันเถอะ!
## ข้อกำหนดเบื้องต้น
ก่อนที่เราจะเจาะลึกเรื่องความมหัศจรรย์ของการเขียนโค้ด เรามาตรวจสอบให้แน่ใจว่าคุณได้ตั้งค่าทุกอย่างเรียบร้อยแล้ว:
1.  ติดตั้ง GroupDocs.Viewer สำหรับ .NET: ตรงไปที่[ลิ้งค์ดาวน์โหลด](https://releases.groupdocs.com/viewer/net/)เพื่อรับ GroupDocs.Viewer สำหรับ .NET เวอร์ชันล่าสุด ปฏิบัติตามคำแนะนำในการติดตั้งเพื่อรวมเข้ากับสภาพแวดล้อมการพัฒนาของคุณได้อย่างราบรื่น
2. เตรียมเอกสารของคุณให้พร้อม: ตรวจสอบให้แน่ใจว่าคุณมีเอกสารเป้าหมาย สมมติว่าไฟล์ Excel ชื่อ "file.xlsx" ในไดเร็กทอรีเอกสารที่คุณกำหนด
## นำเข้าเนมสเปซ
ตอนนี้คุณมีข้อกำหนดเบื้องต้นแล้ว เรามาเริ่มต้นด้วยการนำเข้าเนมสเปซที่จำเป็นกันดีกว่า สิ่งนี้ทำให้มั่นใจได้ว่าแอปพลิเคชันของคุณจะจดจำและสามารถใช้ฟังก์ชันการทำงานที่ GroupDocs.Viewer สำหรับ .NET มอบให้ได้
```csharp
using System;
using System.IO;
using GroupDocs.Viewer.Options;
using GroupDocs.Viewer.Results;
```
## 1. การตั้งค่าไดเร็กทอรีเอกสาร
```csharp
string outputDirectory = "Your Document Directory";
```
แทนที่ "Your Document Directory" ด้วยเส้นทางไปยังไดเร็กทอรีที่มีเอกสารเป้าหมายของคุณ
## 2. การเริ่มต้นโปรแกรมดู
```csharp
using (Viewer viewer = new Viewer(Path.Combine(outputDirectory, "file.xlsx")))
```
ในขั้นตอนนี้ เราจะสร้างอินสแตนซ์ของคลาส Viewer เพื่อระบุเส้นทางไปยังไฟล์ Excel ของคุณ
## 3. การกำหนดค่าตัวเลือกข้อมูลมุมมอง
```csharp
ViewInfoOptions viewInfoOptions = ViewInfoOptions.ForHtmlView();
viewInfoOptions.SpreadsheetOptions = SpreadsheetOptions.ForOnePagePerSheet();
```
ที่นี่ เรากำหนดค่า ViewInfoOptions เพื่อสร้างมุมมอง HTML และตั้งค่าตัวเลือกเพิ่มเติมสำหรับการแสดงผลสเปรดชีต
## 4. การดึงข้อมูลมุมมอง
```csharp
ViewInfo viewInfo = viewer.GetViewInfo(viewInfoOptions);
```
ใช้อินสแตนซ์ Viewer เพื่อดึงข้อมูลมุมมองตามตัวเลือกที่กำหนดค่าไว้
## 5. การแสดงชื่อแผ่นงาน
```csharp
Console.WriteLine("Worksheets:");
foreach (Page page in viewInfo.Pages)
{
    Console.WriteLine($" - Worksheet {page.Number} name '{page.Name}'");
}
```
วนซ้ำหน้าที่ดึงข้อมูลและพิมพ์ชื่อของแต่ละแผ่นงานไปยังคอนโซล
## บทสรุป
ยินดีด้วย! คุณได้สำรวจกระบวนการดึงชื่อเวิร์กชีทโดยใช้ GroupDocs.Viewer สำหรับ .NET สำเร็จแล้ว ซึ่งเปิดโอกาสมากมายในการปรับปรุงฟังก์ชันการดูเอกสารภายในแอปพลิเคชันของคุณ
## คำถามที่พบบ่อย
### ฉันสามารถใช้ GroupDocs.Viewer สำหรับ .NET กับเอกสารรูปแบบอื่นได้หรือไม่
อย่างแน่นอน! GroupDocs.Viewer รองรับรูปแบบเอกสารที่หลากหลาย รวมถึง PDF, Microsoft Office และอื่นๆ
### มีการทดลองใช้ฟรีหรือไม่?
 ใช่ คุณสามารถสำรวจ GroupDocs.Viewer สำหรับ .NET กับเราได้[ทดลองฟรี](https://releases.groupdocs.com/).
### ฉันจะหาการสนับสนุนเพิ่มเติมได้จากที่ไหน?
 มุ่งหน้าไปที่[ฟอรัม GroupDocs.Viewer](https://forum.groupdocs.com/c/viewer/9) สำหรับการสนับสนุนและการอภิปรายของชุมชน
### ฉันสามารถขอรับใบอนุญาตชั่วคราวได้หรือไม่?
 แน่นอน! เยี่ยม[ลิงค์นี้](https://purchase.groupdocs.com/temporary-license/) เพื่อรับใบอนุญาตชั่วคราวของคุณ
### มีแหล่งข้อมูลเอกสารโดยละเอียดหรือไม่?
 อย่างแน่นอน! ตรวจสอบ[เอกสารอย่างเป็นทางการ](https://tutorials.groupdocs.com/viewer/net/) สำหรับข้อมูลเชิงลึกและคำแนะนำ