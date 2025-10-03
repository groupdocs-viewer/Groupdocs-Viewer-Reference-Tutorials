---
"description": "สำรวจการแสดงผลไฟล์ XML SpreadSheetML ในรูปแบบต่างๆ ได้อย่างราบรื่นโดยใช้ GroupDocs.Viewer สำหรับ .NET ผสานรวมเข้ากับแอปพลิเคชันของคุณได้อย่างง่ายดาย"
"linktitle": "การเรนเดอร์ XML SpreadSheetML"
"second_title": "API ของ GroupDocs.Viewer .NET"
"title": "การเรนเดอร์ XML SpreadSheetML"
"url": "/th/net/spreadsheet-rendering-options/rendering-xml-spreadsheetml/"
"weight": 16
type: docs
---
# การเรนเดอร์ XML SpreadSheetML

## การแนะนำ
ยินดีต้อนรับสู่โลกของ GroupDocs.Viewer สำหรับ .NET! ในบทช่วยสอนนี้ เราจะแนะนำคุณเกี่ยวกับการเรนเดอร์ไฟล์ XML SpreadSheetML อย่างง่ายดายโดยใช้ GroupDocs.Viewer ซึ่งเป็นไลบรารี .NET ที่ทรงพลัง ไม่ว่าคุณจะเป็นนักพัฒนาที่มีประสบการณ์หรือเพิ่งเริ่มต้น คู่มือทีละขั้นตอนนี้จะช่วยให้คุณผสานการเรนเดอร์ XML SpreadSheetML เข้ากับแอปพลิเคชันของคุณได้อย่างง่ายดาย
## ข้อกำหนดเบื้องต้น
ก่อนจะเริ่มบทช่วยสอนนี้ ให้แน่ใจว่าคุณได้ตั้งค่าข้อกำหนดเบื้องต้นดังต่อไปนี้:
- สภาพแวดล้อมการพัฒนาที่สนับสนุน .NET
- ติดตั้งไลบรารี GroupDocs.Viewer สำหรับ .NET แล้ว คุณสามารถดาวน์โหลดได้ [ที่นี่](https://releases-groupdocs.com/viewer/net/).
- ความเข้าใจพื้นฐานเกี่ยวกับการเขียนโปรแกรม C#
## นำเข้าเนมสเปซ
เริ่มต้นด้วยการนำเข้าเนมสเปซที่จำเป็นลงในโปรเจ็กต์ C# ของคุณ ซึ่งจะช่วยให้คุณสามารถเข้าถึงฟังก์ชันต่างๆ ที่ GroupDocs.Viewer จัดเตรียมไว้ให้ได้
```csharp
using GroupDocs.Viewer.Options;
using System;
using System.IO;
```
## ขั้นตอนที่ 1: ตั้งค่าไดเรกทอรีเอกสารของคุณ
กำหนดเส้นทางไปยังไดเร็กทอรีเอกสารของคุณซึ่งเอาต์พุตจะถูกบันทึก
```csharp
string outputDirectory = "Your Document Directory";
```
## ขั้นตอนที่ 2: ระบุเส้นทางไฟล์เอาท์พุต
ตั้งค่าเส้นทางแบบเต็มสำหรับไฟล์เอาท์พุต HTML, JPG, PNG และ PDF
```csharp
string pageFileFullPath = Path.Combine(outputDirectory, "Excel_2003_Xml_result.html");
```
## ขั้นตอนที่ 3: ระบุตัวเลือกการโหลด
ระบุชนิดไฟล์อย่างชัดเจนเป็น Excel 2003 XML SpreadSheetML เพื่อแสดงผลอย่างถูกต้องแม่นยำ
```csharp
LoadOptions loadOptions = new LoadOptions(FileType.Excel2003XML);
```
## ขั้นตอนที่ 4: เรนเดอร์เป็น HTML หลายหน้า
ใช้ตัวเลือกมุมมอง HTML เพื่อแสดงไฟล์ XML SpreadSheetML เป็นเอกสาร HTML หลายหน้า
```csharp
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_XML_SPREADSHEETML, loadOptions))
{
    HtmlViewOptions options = HtmlViewOptions.ForEmbeddedResources(pageFileFullPath);
    viewer.View(options);
}
```
## ขั้นตอนที่ 5: เรนเดอร์เป็น JPG
เรนเดอร์ไฟล์ XML SpreadSheetML เป็นภาพ JPG โดยใช้ตัวเลือกที่ระบุ
```csharp
pageFileFullPath = Path.Combine(outputDirectory, "Excel_2003_Xml_result.jpg");
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_XML_SPREADSHEETML, loadOptions))
{
    JpgViewOptions options = new JpgViewOptions(pageFileFullPath);
    viewer.View(options);
}
```
## ขั้นตอนที่ 6: เรนเดอร์เป็น PNG
ในทำนองเดียวกัน ให้เรนเดอร์ไฟล์เป็นภาพ PNG พร้อมตัวเลือกที่ระบุ
```csharp
pageFileFullPath = Path.Combine(outputDirectory, "Excel_2003_Xml_result.png");
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_XML_SPREADSHEETML, loadOptions))
{
    PngViewOptions options = new PngViewOptions(pageFileFullPath);
    viewer.View(options);
}
```
## ขั้นตอนที่ 7: เรนเดอร์เป็น PDF
ในที่สุด ให้เรนเดอร์ไฟล์ XML SpreadSheetML เป็นเอกสาร PDF โดยใช้ตัวเลือกที่ระบุ
```csharp
pageFileFullPath = Path.Combine(outputDirectory, "Excel_2003_Xml_result.pdf");
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_XML_SPREADSHEETML, loadOptions))
{
    PdfViewOptions options = new PdfViewOptions(pageFileFullPath);
    viewer.View(options);
}
```
## บทสรุป
ขอแสดงความยินดี! คุณได้เรียนรู้วิธีการเรนเดอร์ไฟล์ XML SpreadSheetML โดยใช้ GroupDocs.Viewer สำหรับ .NET สำเร็จแล้ว ปรับปรุงความสามารถในการดูเอกสารของคุณโดยสำรวจคุณลักษณะและตัวเลือกเพิ่มเติมที่จัดเตรียมไว้โดยไลบรารีอเนกประสงค์นี้
## คำถามที่พบบ่อย
### GroupDocs.Viewer เข้ากันได้กับรูปแบบไฟล์อื่นหรือไม่
ใช่ GroupDocs.Viewer รองรับรูปแบบเอกสารต่างๆ มากมาย รวมถึง PDF, Word, Excel และอื่นๆ อีกมากมาย
### ฉันสามารถปรับแต่งลักษณะที่ปรากฏของเอกสารที่แสดงผลได้หรือไม่
แน่นอน! GroupDocs.Viewer มีตัวเลือกการปรับแต่งต่างๆ ช่วยให้คุณปรับแต่งผลลัพธ์ให้ตรงตามความต้องการเฉพาะของคุณได้
### ฉันสามารถหาการสนับสนุนและทรัพยากรเพิ่มเติมได้ที่ไหน
เยี่ยมชม [ฟอรั่ม GroupDocs.Viewer](https://forum.groupdocs.com/c/viewer/9) สำหรับการสนับสนุนชุมชนและสำรวจ [เอกสารประกอบ](https://tutorials.groupdocs.com/viewer/net/) เพื่อดูข้อมูลโดยละเอียด
### มีการทดลองใช้ฟรีหรือไม่?
ใช่ คุณสามารถเข้าถึงการทดลองใช้ฟรีได้ [ที่นี่](https://releases-groupdocs.com/).
### ฉันจะได้รับใบอนุญาตชั่วคราวได้อย่างไร?
คุณสามารถรับใบอนุญาตชั่วคราวได้ [ที่นี่](https://purchase-groupdocs.com/temporary-license/).