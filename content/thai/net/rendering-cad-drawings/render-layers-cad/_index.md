---
"description": "เรนเดอร์ภาพวาด CAD ได้อย่างราบรื่นในแอปพลิเคชัน .NET ด้วย GroupDocs.Viewer สำหรับ .NET สำรวจตัวเลือกการเรนเดอร์ ปรับแต่งเลเยอร์ และอื่นๆ อีกมากมาย"
"linktitle": "การเรนเดอร์เลเยอร์ในภาพวาด CAD"
"second_title": "API ของ GroupDocs.Viewer .NET"
"title": "การเรนเดอร์เลเยอร์ในภาพวาด CAD"
"url": "/th/net/rendering-cad-drawings/render-layers-cad/"
"weight": 13
---

# การเรนเดอร์เลเยอร์ในภาพวาด CAD

## การแนะนำ
GroupDocs.Viewer สำหรับ .NET เป็นเครื่องมืออันทรงพลังที่ช่วยให้นักพัฒนาสามารถผสานรวมความสามารถในการแสดงผลเอกสารเข้ากับแอปพลิเคชัน .NET ได้อย่างราบรื่น ไม่ว่าคุณจะต้องแสดงผลแบบ CAD, PDF, เอกสาร Microsoft Office หรืออื่นๆ GroupDocs.Viewer ก็มีโซลูชันที่ครอบคลุม
## ข้อกำหนดเบื้องต้น
ก่อนที่จะเริ่มใช้ GroupDocs.Viewer สำหรับ .NET ให้แน่ใจว่าคุณมีข้อกำหนดเบื้องต้นดังต่อไปนี้:
- ความเข้าใจพื้นฐานเกี่ยวกับภาษาการเขียนโปรแกรม C#
- ตั้งค่าสภาพแวดล้อมการพัฒนา .NET บนเครื่องของคุณ
- GroupDocs.Viewer สำหรับ .NET ได้รับการติดตั้งแล้ว คุณสามารถดาวน์โหลดได้จาก [ที่นี่](https://releases-groupdocs.com/viewer/net/).
- การเข้าถึงเอกสาร GroupDocs.Viewer สำหรับ .NET สำหรับบทช่วยสอน ซึ่งสามารถพบได้ [ที่นี่](https://tutorials-groupdocs.com/viewer/net/).

## นำเข้าเนมสเปซ
หากต้องการเริ่มใช้ GroupDocs.Viewer สำหรับ .NET คุณจะต้องนำเข้าเนมสเปซที่จำเป็นในโปรเจ็กต์ของคุณ ทำตามขั้นตอนเหล่านี้:

```csharp
using System;
using System.Collections.Generic;
using System.IO;
using GroupDocs.Viewer.Options;
using GroupDocs.Viewer.Results;
```

ให้เราแบ่งตัวอย่างที่ให้มาเป็นขั้นตอนต่างๆ ดังนี้:
## ขั้นตอนที่ 1: กำหนดไดเรกทอรีผลลัพธ์
```csharp
string outputDirectory = "Your Document Directory";
```
## ขั้นตอนที่ 2: กำหนดรูปแบบเส้นทางไฟล์เพจ
```csharp
string pageFilePathFormat = Path.Combine(outputDirectory, "page_{0}.html");
```
## ขั้นตอนที่ 3: เริ่มต้น Viewer Object
```csharp
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_DWG_WITH_LAYOUTS_AND_LAYERS))
{
    // บล็อคโค้ดยังคงดำเนินต่อไป...
}
```
## ขั้นตอนที่ 4: ตั้งค่าตัวเลือกมุมมอง HTML
```csharp
HtmlViewOptions options = HtmlViewOptions.ForEmbeddedResources(pageFilePathFormat);
```
## ขั้นตอนที่ 5: กำหนดเลเยอร์ CAD
```csharp
options.CadOptions.Layers = new List<Layer>
{
    new Layer("QUADRANT")
};
```
## ขั้นตอนที่ 6: เรนเดอร์เอกสาร
```csharp
viewer.View(options);
```
## ขั้นตอนที่ 7: ส่งออกตำแหน่งเอกสารที่แสดงผล
```csharp
Console.WriteLine($"\nSource document rendered successfully.\nCheck output in {outputDirectory}.");
```

## บทสรุป
ด้วย GroupDocs.Viewer สำหรับ .NET การเรนเดอร์แบบ CAD ในแอปพลิเคชัน .NET ของคุณจะกลายเป็นกระบวนการที่ราบรื่น เพียงทำตามขั้นตอนที่ระบุไว้ในคู่มือนี้ คุณก็ผสานรวมความสามารถในการเรนเดอร์เอกสารเข้ากับโปรเจ็กต์ของคุณได้อย่างง่ายดาย
## คำถามที่พบบ่อย
### GroupDocs.Viewer สามารถทำงานร่วมกับรูปวาด CAD ทุกประเภทได้หรือไม่
ใช่ GroupDocs.Viewer รองรับการเรนเดอร์รูปแบบการวาด CAD ที่หลากหลาย รวมถึง DWG และ DXF
### ฉันสามารถปรับแต่งตัวเลือกการเรนเดอร์สำหรับรูปวาด CAD ได้หรือไม่
แน่นอนว่า GroupDocs.Viewer มีตัวเลือกการปรับแต่งต่างๆ เช่น การระบุเลเยอร์ที่จะเรนเดอร์หรือการตั้งค่ารูปแบบเอาต์พุต
### GroupDocs.Viewer ต้องใช้การเชื่อมต่ออินเทอร์เน็ตในการเรนเดอร์เอกสารหรือไม่
ไม่ GroupDocs.Viewer ทำการเรนเดอร์ในเครื่องโดยไม่จำเป็นต้องเชื่อมต่ออินเทอร์เน็ต
### มี GroupDocs.Viewer สำหรับ .NET ให้ทดลองใช้งานฟรีหรือไม่
ใช่ คุณสามารถเข้าถึงรุ่นทดลองใช้งานฟรีของ GroupDocs.Viewer สำหรับ .NET ได้ [ที่นี่](https://releases-groupdocs.com/).
### ฉันจะได้รับการสนับสนุนสำหรับ GroupDocs.Viewer สำหรับ .NET ได้จากที่ไหน
หากต้องการความช่วยเหลือด้านเทคนิคหรือมีคำถามใดๆ คุณสามารถเยี่ยมชมฟอรัม GroupDocs.Viewer ได้ [ที่นี่](https://forum-groupdocs.com/c/viewer/9).