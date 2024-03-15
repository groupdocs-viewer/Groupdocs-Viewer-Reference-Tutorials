---
title: กำลังแสดงผล XML SpreadSheetML
linktitle: กำลังแสดงผล XML SpreadSheetML
second_title: GroupDocs.Viewer .NET API
description: สำรวจการเรนเดอร์ไฟล์ XML SpreadSheetML ในรูปแบบต่างๆ ได้อย่างราบรื่นโดยใช้ GroupDocs.Viewer สำหรับ .NET รวมเข้ากับแอปพลิเคชันของคุณได้อย่างง่ายดาย
type: docs
weight: 16
url: /th/net/spreadsheet-rendering-options/rendering-xml-spreadsheetml/
---
## การแนะนำ
ยินดีต้อนรับสู่โลกของ GroupDocs.Viewer สำหรับ .NET! ในบทช่วยสอนนี้ เราจะแนะนำคุณเกี่ยวกับการเรนเดอร์ไฟล์ XML SpreadSheetML อย่างง่ายดายโดยใช้ GroupDocs.Viewer ซึ่งเป็นไลบรารี .NET อันทรงพลัง ไม่ว่าคุณจะเป็นนักพัฒนาที่มีประสบการณ์หรือเพิ่งเริ่มต้น คำแนะนำทีละขั้นตอนนี้จะช่วยให้คุณรวมการเรนเดอร์ XML SpreadSheetML เข้ากับแอปพลิเคชันของคุณได้อย่างง่ายดาย
## ข้อกำหนดเบื้องต้น
ก่อนที่จะเข้าสู่บทช่วยสอน ตรวจสอบให้แน่ใจว่าคุณได้ตั้งค่าข้อกำหนดเบื้องต้นต่อไปนี้:
- สภาพแวดล้อมการพัฒนาที่รองรับ .NET
-  ติดตั้ง GroupDocs.Viewer สำหรับไลบรารี .NET แล้ว คุณสามารถดาวน์โหลดได้[ที่นี่](https://releases.groupdocs.com/viewer/net/).
- ความเข้าใจพื้นฐานเกี่ยวกับการเขียนโปรแกรม C#
## นำเข้าเนมสเปซ
เริ่มต้นด้วยการนำเข้าเนมสเปซที่จำเป็นลงในโปรเจ็กต์ C# ของคุณ ซึ่งจะทำให้แน่ใจได้ว่าคุณจะสามารถเข้าถึงฟังก์ชันต่างๆ ที่ได้รับจาก GroupDocs.Viewer
```csharp
using GroupDocs.Viewer.Options;
using System;
using System.IO;
```
## ขั้นตอนที่ 1: ตั้งค่าไดเร็กทอรีเอกสารของคุณ
กำหนดเส้นทางไปยังไดเร็กทอรีเอกสารของคุณที่จะบันทึกเอาต์พุต
```csharp
string outputDirectory = "Your Document Directory";
```
## ขั้นตอนที่ 2: ระบุเส้นทางไฟล์เอาต์พุต
ตั้งค่าเส้นทางแบบเต็มสำหรับไฟล์เอาต์พุต HTML, JPG, PNG และ PDF
```csharp
string pageFileFullPath = Path.Combine(outputDirectory, "Excel_2003_Xml_result.html");
```
## ขั้นตอนที่ 3: ระบุตัวเลือกการโหลด
ระบุประเภทไฟล์อย่างชัดเจนเป็น Excel 2003 XML SpreadSheetML เพื่อให้แสดงผลได้อย่างถูกต้อง
```csharp
LoadOptions loadOptions = new LoadOptions(FileType.Excel2003XML);
```
## ขั้นตอนที่ 4: แสดงผลเป็น HTML หลายหน้า
ใช้ตัวเลือกมุมมอง HTML เพื่อแสดงไฟล์ XML SpreadSheetML ลงในเอกสาร HTML แบบหลายหน้า
```csharp
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_XML_SPREADSHEETML, loadOptions))
{
    HtmlViewOptions options = HtmlViewOptions.ForEmbeddedResources(pageFileFullPath);
    viewer.View(options);
}
```
## ขั้นตอนที่ 5: แสดงผลเป็น JPG
แสดงไฟล์ XML SpreadSheetML ให้เป็นรูปภาพ JPG โดยใช้ตัวเลือกที่ระบุ
```csharp
pageFileFullPath = Path.Combine(outputDirectory, "Excel_2003_Xml_result.jpg");
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_XML_SPREADSHEETML, loadOptions))
{
    JpgViewOptions options = new JpgViewOptions(pageFileFullPath);
    viewer.View(options);
}
```
## ขั้นตอนที่ 6: แสดงผลเป็น PNG
ในทำนองเดียวกัน แสดงไฟล์เป็นรูปภาพ PNG ด้วยตัวเลือกที่ระบุ
```csharp
pageFileFullPath = Path.Combine(outputDirectory, "Excel_2003_Xml_result.png");
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_XML_SPREADSHEETML, loadOptions))
{
    PngViewOptions options = new PngViewOptions(pageFileFullPath);
    viewer.View(options);
}
```
## ขั้นตอนที่ 7: แสดงผลเป็น PDF
สุดท้าย เรนเดอร์ไฟล์ XML SpreadSheetML ให้เป็นเอกสาร PDF โดยใช้ตัวเลือกที่ระบุ
```csharp
pageFileFullPath = Path.Combine(outputDirectory, "Excel_2003_Xml_result.pdf");
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_XML_SPREADSHEETML, loadOptions))
{
    PdfViewOptions options = new PdfViewOptions(pageFileFullPath);
    viewer.View(options);
}
```
## บทสรุป
ยินดีด้วย! คุณได้เรียนรู้วิธีเรนเดอร์ไฟล์ XML SpreadSheetML โดยใช้ GroupDocs.Viewer สำหรับ .NET เรียบร้อยแล้ว ปรับปรุงความสามารถในการดูเอกสารของคุณโดยสำรวจคุณสมบัติและตัวเลือกเพิ่มเติมที่มีให้ในไลบรารีอเนกประสงค์นี้
## คำถามที่พบบ่อย
### GroupDocs.Viewer เข้ากันได้กับไฟล์รูปแบบอื่นหรือไม่
ใช่ GroupDocs.Viewer รองรับรูปแบบเอกสารที่หลากหลาย รวมถึง PDF, Word, Excel และอื่นๆ
### ฉันสามารถปรับแต่งลักษณะที่ปรากฏของเอกสารที่แสดงผลได้หรือไม่
อย่างแน่นอน! GroupDocs.Viewer นำเสนอตัวเลือกการปรับแต่งที่หลากหลาย ซึ่งช่วยให้คุณปรับแต่งผลลัพธ์ให้ตรงกับความต้องการเฉพาะของคุณได้
### ฉันจะหาการสนับสนุนและแหล่งข้อมูลเพิ่มเติมได้จากที่ไหน?
 เยี่ยมชม[ฟอรัม GroupDocs.Viewer](https://forum.groupdocs.com/c/viewer/9) สำหรับการสนับสนุนชุมชนและการสำรวจ[เอกสารประกอบ](https://reference.groupdocs.com/viewer/net/)สำหรับข้อมูลโดยละเอียด
### มีการทดลองใช้ฟรีหรือไม่?
 ใช่ คุณสามารถเข้าถึงการทดลองใช้ฟรีได้[ที่นี่](https://releases.groupdocs.com/).
### ฉันจะขอรับใบอนุญาตชั่วคราวได้อย่างไร
 คุณสามารถรับใบอนุญาตชั่วคราวได้[ที่นี่](https://purchase.groupdocs.com/temporary-license/).