---
title: เรนเดอร์เส้นกริด
linktitle: เรนเดอร์เส้นกริด
second_title: GroupDocs.Viewer .NET API
description: ปรับปรุงการแสดงภาพเอกสารด้วย GroupDocs.Viewer สำหรับ .NET เรนเดอร์เส้นตารางได้อย่างง่ายดาย ลองทดลองใช้ฟรีทันที! #GroupDocs #ผู้ดู
type: docs
weight: 12
url: /th/net/spreadsheet-rendering-options/render-grid-lines/
---
## การแนะนำ
ยินดีต้อนรับสู่คำแนะนำทีละขั้นตอนเกี่ยวกับการใช้ GroupDocs.Viewer สำหรับ .NET เพื่อแสดงเส้นตารางในเอกสารของคุณ ไม่ว่าคุณจะเป็นนักพัฒนาที่มีประสบการณ์หรือเพิ่งเริ่มใช้ .NET Framework บทช่วยสอนนี้จะแนะนำคุณตลอดกระบวนการพร้อมคำอธิบายโดยละเอียดและตัวอย่างที่ปฏิบัติตามได้ง่าย
## ข้อกำหนดเบื้องต้น
ก่อนที่จะเข้าสู่บทช่วยสอน ตรวจสอบให้แน่ใจว่าคุณมีข้อกำหนดเบื้องต้นต่อไปนี้:
-  GroupDocs.Viewer สำหรับ .NET: ดาวน์โหลดและติดตั้งไลบรารีจาก[เว็บไซต์อย่างเป็นทางการ](https://releases.groupdocs.com/viewer/net/).
- ไดเรกทอรีเอกสารของคุณ: ตรวจสอบให้แน่ใจว่าคุณมีไดเรกทอรีที่กำหนดสำหรับเอกสารของคุณ และแทนที่ "ไดเรกทอรีเอกสารของคุณ" ในข้อมูลโค้ดที่ให้มาด้วยเส้นทางจริง
เมื่อคุณได้ตั้งค่าทุกอย่างเรียบร้อยแล้ว เรามาเริ่มต้นกันเลย
## นำเข้าเนมสเปซ
ในโปรเจ็กต์ .NET ของคุณ ให้เริ่มด้วยการนำเข้าเนมสเปซที่จำเป็น:
```csharp
using System;
using System.IO;
using GroupDocs.Viewer.Options;
```
## ขั้นตอนที่ 1: ตั้งค่าไดเร็กทอรีเอกสาร
เริ่มต้นด้วยการระบุเส้นทางไปยังไดเร็กทอรีเอกสารของคุณ:
```csharp
string outputDirectory = "Your Document Directory";
```
แทนที่ "Your Document Directory" ด้วยเส้นทางจริงที่ใช้จัดเก็บเอกสารของคุณ
## ขั้นตอนที่ 2: กำหนดเส้นทางไฟล์และรูปแบบเอาต์พุต HTML
สร้างตัวแปรเพื่อจัดเก็บรูปแบบเส้นทางไฟล์สำหรับแต่ละหน้าและรูปแบบ HTML เอาท์พุต:
```csharp
string pageFilePathFormat = Path.Combine(outputDirectory, "page_{0}.html");
```
บรรทัดนี้สร้างเส้นทางไฟล์สำหรับแต่ละหน้าในรูปแบบที่ระบุ
## ขั้นตอนที่ 3: เริ่มต้น GroupDocs.Viewer
สร้างอินสแตนซ์คลาส Viewer ด้วยเอกสารที่คุณต้องการดู:
```csharp
using (Viewer viewer = new Viewer(outputDirectory + "SAMPLE.XLSX"))
{
    // ขั้นตอนต่อไปจะดำเนินการภายในบล็อกนี้
}
```
ตรวจสอบให้แน่ใจว่าได้แทนที่ "SAMPLE.XLSX" ด้วยชื่อของเอกสารจริงของคุณ
## ขั้นตอนที่ 4: กำหนดค่าตัวเลือกมุมมอง HTML
ตั้งค่าตัวเลือกมุมมอง HTML โดยเฉพาะการเปิดใช้งานการเรนเดอร์เส้นตาราง:
```csharp
HtmlViewOptions options = HtmlViewOptions.ForEmbeddedResources(pageFilePathFormat);
options.SpreadsheetOptions.RenderGridLines = true;
```
ข้อมูลโค้ดนี้จะกำหนดค่าตัวเลือกมุมมอง HTML เพื่อฝังทรัพยากรและแสดงเส้นตารางสำหรับเอกสารสเปรดชีต
## ขั้นตอนที่ 5: เรนเดอร์เส้นกริด
 เรียกใช้`View` วิธีการแสดงเอกสารด้วยตัวเลือกที่ระบุสำหรับหน้า 1, 2 และ 3:
```csharp
viewer.View(options, 1, 2, 3);
```
ปรับหมายเลขหน้าตามความต้องการของคุณ
แค่นั้นแหละ! คุณแสดงผลเส้นตารางได้สำเร็จโดยใช้ GroupDocs.Viewer สำหรับ .NET
## บทสรุป
ในบทช่วยสอนนี้ เราได้สำรวจกระบวนการเรนเดอร์เส้นกริดในเอกสารโดยใช้ GroupDocs.Viewer สำหรับ .NET การทำตามขั้นตอนที่ระบุไว้จะช่วยให้คุณปรับปรุงการนำเสนอเอกสารสเปรดชีตของคุณด้วยภาพได้
## คำถามที่พบบ่อย
### GroupDocs.Viewer สำหรับ .NET ใช้งานได้ฟรีหรือไม่
 GroupDocs.Viewer สำหรับ .NET มีทั้งเวอร์ชันทดลองใช้ฟรีและเวอร์ชันชำระเงิน สำรวจ[ทดลองฟรี](https://releases.groupdocs.com/) หรือเยี่ยมชมได้ที่[หน้าซื้อ](https://purchase.groupdocs.com/buy) สำหรับรายละเอียดใบอนุญาต
### ฉันจะรับการสนับสนุนสำหรับ GroupDocs.Viewer สำหรับ .NET ได้อย่างไร
 เยี่ยมชม[ฟอรัม GroupDocs.Viewer](https://forum.groupdocs.com/c/viewer/9) เพื่อขอความช่วยเหลือ แบ่งปันประสบการณ์ และเชื่อมต่อกับชุมชน
### มีใบอนุญาตชั่วคราวสำหรับ GroupDocs.Viewer สำหรับ .NET หรือไม่
 ใช่ คุณสามารถได้รับ[ใบอนุญาตชั่วคราว](https://purchase.groupdocs.com/temporary-license/) สำหรับ GroupDocs.Viewer สำหรับ .NET
### ฉันสามารถค้นหาเอกสารโดยละเอียดสำหรับ GroupDocs.Viewer สำหรับ .NET ได้หรือไม่
 อย่างแน่นอน! อ้างถึง[เอกสารอย่างเป็นทางการ](https://reference.groupdocs.com/viewer/net/) สำหรับข้อมูลเชิงลึกเกี่ยวกับการใช้ GroupDocs.Viewer สำหรับ .NET
### ฉันจะดาวน์โหลด GroupDocs.Viewer สำหรับ .NET เวอร์ชันล่าสุดได้ที่ไหน
 ดาวน์โหลดไลบรารีได้จาก[หน้าเปิดตัวอย่างเป็นทางการ](https://releases.groupdocs.com/viewer/net/).