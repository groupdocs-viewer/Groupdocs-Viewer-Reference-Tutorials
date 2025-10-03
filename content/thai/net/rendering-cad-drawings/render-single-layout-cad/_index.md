---
"description": "เรียนรู้วิธีการเรนเดอร์เค้าโครงเดี่ยวในภาพวาด CAD โดยใช้ GroupDocs.Viewer สำหรับ .NET ขั้นตอนง่ายๆ เพื่อการผสานรวมที่ราบรื่นในแอปพลิเคชัน .NET ของคุณ"
"linktitle": "การเรนเดอร์เค้าโครงเดี่ยวในภาพวาด CAD"
"second_title": "API ของ GroupDocs.Viewer .NET"
"title": "การเรนเดอร์เค้าโครงเดี่ยวในภาพวาด CAD"
"url": "/th/net/rendering-cad-drawings/render-single-layout-cad/"
"weight": 14
type: docs
---
# การเรนเดอร์เค้าโครงเดี่ยวในภาพวาด CAD

## การแนะนำ
ในการพัฒนา .NET การจัดการและการดูแบบ CAD ถือเป็นข้อกำหนดทั่วไป GroupDocs.Viewer สำหรับ .NET ทำให้ภารกิจนี้ง่ายขึ้นโดยนำเสนอโซลูชันที่ครอบคลุมสำหรับการเรนเดอร์แบบ CAD ภายในแอปพลิเคชัน .NET ในบทช่วยสอนนี้ เราจะเจาะลึกการเรนเดอร์เค้าโครงเดียวในแบบ CAD โดยใช้ GroupDocs.Viewer สำหรับ .NET
## ข้อกำหนดเบื้องต้น
ก่อนจะเริ่มบทช่วยสอนนี้ ให้แน่ใจว่าคุณมีข้อกำหนดเบื้องต้นดังต่อไปนี้:
- ความเข้าใจพื้นฐานเกี่ยวกับภาษาการเขียนโปรแกรม C# และ .NET framework
- Visual Studio ติดตั้งอยู่บนระบบของคุณแล้ว
- ดาวน์โหลดไลบรารี GroupDocs.Viewer สำหรับ .NET และบทช่วยสอนในโปรเจ็กต์ของคุณ คุณสามารถดาวน์โหลดได้จาก [ที่นี่](https://releases-groupdocs.com/viewer/net/).
- ความคุ้นเคยกับรูปแบบไฟล์ CAD และโครงสร้างของมัน

## นำเข้าเนมสเปซ
ขั้นแรก นำเข้าเนมสเปซที่จำเป็นลงในโค้ด C# ของคุณเพื่อเข้าถึงฟังก์ชันการทำงานของ GroupDocs.Viewer

```csharp
using System;
using System.IO;
using GroupDocs.Viewer.Options;
```

## ขั้นตอนที่ 1: กำหนดไดเรกทอรีผลลัพธ์
ระบุไดเร็กทอรีที่คุณต้องการบันทึกเอาท์พุตที่แสดงผล
```csharp
string outputDirectory = "Your Document Directory";
```
## ขั้นตอนที่ 2: กำหนดรูปแบบเส้นทางไฟล์เพจ
กำหนดรูปแบบสำหรับเส้นทางไฟล์ของแต่ละหน้าที่แสดงผล
```csharp
string pageFilePathFormat = Path.Combine(outputDirectory, "page_{0}.html");
```
## ขั้นตอนที่ 3: สร้างอินสแตนซ์ของวัตถุ Viewer
สร้างอินสแตนซ์ของคลาส Viewer ที่ให้มาโดย GroupDocs.Viewer
```csharp
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_DWG_WITH_LAYOUTS_AND_LAYERS))
```
## ขั้นตอนที่ 4: กำหนดค่าตัวเลือกมุมมอง HTML
กำหนดค่าตัวเลือกสำหรับการเรนเดอร์เอาท์พุต HTML ด้วยรีซอร์สที่ฝังไว้
```csharp
HtmlViewOptions options = HtmlViewOptions.ForEmbeddedResources(pageFilePathFormat);
```
## ขั้นตอนที่ 5: ระบุชื่อเค้าโครง CAD
ระบุชื่อเค้าโครง CAD ที่คุณต้องการเรนเดอร์
```csharp
options.CadOptions.LayoutName = "Model";
```
## ขั้นตอนที่ 6: เรนเดอร์ภาพวาด CAD
เรียกใช้วิธีการมุมมองของวัตถุ Viewer ด้วยตัวเลือกที่ระบุ
```csharp
viewer.View(options);
```
## ขั้นตอนที่ 7: แสดงข้อความแสดงว่าสำเร็จ
แจ้งให้ผู้ใช้ทราบถึงการแสดงผลเอกสารต้นฉบับสำเร็จ
```csharp
Console.WriteLine($"\nSource document rendered successfully.\nCheck output in {outputDirectory}.");
```

## บทสรุป
การเรนเดอร์แบบ CAD โดยเฉพาะอย่างยิ่งเมื่อต้องจัดการกับเค้าโครง อาจเป็นงานที่น่ากังวล อย่างไรก็ตาม ด้วย GroupDocs.Viewer สำหรับ .NET กระบวนการนี้จะราบรื่นและมีประสิทธิภาพมากขึ้น หากทำตามขั้นตอนที่ระบุไว้ในบทช่วยสอนนี้ คุณจะสามารถเรนเดอร์เค้าโครงเดียวในแบบ CAD ภายในแอปพลิเคชัน .NET ของคุณได้อย่างง่ายดาย
## คำถามที่พบบ่อย
### ฉันสามารถเรนเดอร์เค้าโครงหลาย ๆ อันพร้อมกันโดยใช้ GroupDocs.Viewer สำหรับ .NET ได้หรือไม่
ใช่ GroupDocs.Viewer สำหรับ .NET รองรับการเรนเดอร์เค้าโครงหลายรูปแบบจากรูปวาด CAD
### GroupDocs.Viewer เข้ากันได้กับรูปแบบไฟล์ CAD ที่แตกต่างกันหรือไม่
แน่นอนว่า GroupDocs.Viewer รองรับไฟล์ CAD หลากหลายรูปแบบ รวมถึง DWG, DXF, DGN และอื่นๆ อีกมากมาย
### ฉันสามารถปรับแต่งตัวเลือกการเรนเดอร์สำหรับรูปวาด CAD ได้หรือไม่
ใช่ GroupDocs.Viewer มีตัวเลือกมากมายในการปรับแต่งการตั้งค่าการเรนเดอร์ตามความต้องการของคุณ
### มี GroupDocs.Viewer สำหรับ .NET ให้ทดลองใช้งานฟรีหรือไม่
ใช่ คุณสามารถสำรวจคุณสมบัติของ GroupDocs.Viewer ได้ด้วยการทดลองใช้ฟรี [ที่นี่](https://releases-groupdocs.com/).
### ฉันจะได้รับการสนับสนุนสำหรับ GroupDocs.Viewer สำหรับ .NET ได้จากที่ไหน
หากมีคำถามหรือต้องการความช่วยเหลือ สามารถเข้าไปที่ฟอรัม GroupDocs.Viewer ได้ [ที่นี่](https://forum-groupdocs.com/c/viewer/9).