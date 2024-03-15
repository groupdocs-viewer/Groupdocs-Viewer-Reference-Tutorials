---
title: เรนเดอร์เลเยอร์ในแบบร่าง CAD
linktitle: เรนเดอร์เลเยอร์ในแบบร่าง CAD
second_title: GroupDocs.Viewer .NET API
description: เรนเดอร์ภาพวาด CAD ได้อย่างราบรื่นในแอปพลิเคชัน .NET ด้วย GroupDocs.Viewer สำหรับ .NET สำรวจตัวเลือกการเรนเดอร์ ปรับแต่งเลเยอร์ และอื่นๆ
type: docs
weight: 13
url: /th/net/rendering-cad-drawings/render-layers-cad/
---
## การแนะนำ
GroupDocs.Viewer สำหรับ .NET เป็นเครื่องมืออันทรงพลังที่ช่วยให้นักพัฒนาสามารถผสานรวมความสามารถในการเรนเดอร์เอกสารเข้ากับแอปพลิเคชัน .NET ของตนได้อย่างราบรื่น ไม่ว่าคุณจะต้องเรนเดอร์ภาพวาด CAD, PDF, เอกสาร Microsoft Office หรืออื่นๆ GroupDocs.Viewer ก็มีโซลูชันที่ครอบคลุม
## ข้อกำหนดเบื้องต้น
ก่อนที่จะเริ่มใช้ GroupDocs.Viewer สำหรับ .NET ตรวจสอบให้แน่ใจว่าคุณมีข้อกำหนดเบื้องต้นต่อไปนี้:
- ความเข้าใจพื้นฐานเกี่ยวกับภาษาการเขียนโปรแกรม C#
- สภาพแวดล้อมการพัฒนา .NET ที่ตั้งค่าบนเครื่องของคุณ
-  ติดตั้ง GroupDocs.Viewer สำหรับ .NET แล้ว คุณสามารถดาวน์โหลดได้จาก[ที่นี่](https://releases.groupdocs.com/viewer/net/).
-  เข้าถึงเอกสาร GroupDocs.Viewer สำหรับ .NET เพื่อใช้อ้างอิง ซึ่งสามารถพบได้[ที่นี่](https://reference.groupdocs.com/viewer/net/).

## นำเข้าเนมสเปซ
หากต้องการเริ่มใช้ GroupDocs.Viewer สำหรับ .NET คุณจะต้องนำเข้าเนมสเปซที่จำเป็นในโปรเจ็กต์ของคุณ ทำตามขั้นตอนเหล่านี้:

```csharp
using System;
using System.Collections.Generic;
using System.IO;
using GroupDocs.Viewer.Options;
using GroupDocs.Viewer.Results;
```

มาแบ่งตัวอย่างที่ให้มาออกเป็นหลายขั้นตอน:
## ขั้นตอนที่ 1: กำหนดไดเรกทอรีผลลัพธ์
```csharp
string outputDirectory = "Your Document Directory";
```
## ขั้นตอนที่ 2: กำหนดรูปแบบเส้นทางไฟล์เพจ
```csharp
string pageFilePathFormat = Path.Combine(outputDirectory, "page_{0}.html");
```
## ขั้นตอนที่ 3: เริ่มต้นวัตถุ Viewer
```csharp
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_DWG_WITH_LAYOUTS_AND_LAYERS))
{
    // บล็อกรหัสยังคงดำเนินต่อไป...
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
## ขั้นตอนที่ 6: แสดงผลเอกสาร
```csharp
viewer.View(options);
```
## ขั้นตอนที่ 7: ตำแหน่งเอกสารแสดงผลเอาต์พุต
```csharp
Console.WriteLine($"\nSource document rendered successfully.\nCheck output in {outputDirectory}.");
```

## บทสรุป
ด้วย GroupDocs.Viewer สำหรับ .NET การเรนเดอร์ภาพวาด CAD ในแอปพลิเคชัน .NET ของคุณจะกลายเป็นกระบวนการที่ราบรื่น ด้วยการทำตามขั้นตอนที่ระบุไว้ในคู่มือนี้ คุณสามารถรวมความสามารถในการเรนเดอร์เอกสารเข้ากับโปรเจ็กต์ของคุณได้อย่างง่ายดาย
## คำถามที่พบบ่อย
### GroupDocs.Viewer เข้ากันได้กับภาพวาด CAD ทุกประเภทหรือไม่
ใช่ GroupDocs.Viewer รองรับการเรนเดอร์รูปแบบการวาด CAD ที่หลากหลาย รวมถึง DWG และ DXF
### ฉันสามารถปรับแต่งตัวเลือกการเรนเดอร์สำหรับแบบร่าง CAD ได้หรือไม่
แน่นอนว่า GroupDocs.Viewer มีตัวเลือกการปรับแต่งที่หลากหลาย เช่น การระบุเลเยอร์ที่จะเรนเดอร์หรือการตั้งค่ารูปแบบเอาต์พุต
### GroupDocs.Viewer ต้องใช้การเชื่อมต่ออินเทอร์เน็ตในการเรนเดอร์เอกสารหรือไม่
ไม่ GroupDocs.Viewer ทำการเรนเดอร์ภายในเครื่องโดยไม่จำเป็นต้องเชื่อมต่ออินเทอร์เน็ต
### GroupDocs.Viewer สำหรับ .NET มีรุ่นทดลองใช้ฟรีหรือไม่
 ใช่ คุณสามารถเข้าถึง GroupDocs.Viewer สำหรับ .NET รุ่นทดลองใช้ฟรีได้[ที่นี่](https://releases.groupdocs.com/).
### ฉันจะรับการสนับสนุนสำหรับ GroupDocs.Viewer สำหรับ .NET ได้ที่ไหน
 สำหรับความช่วยเหลือทางเทคนิคหรือข้อสงสัย คุณสามารถไปที่ฟอรัม GroupDocs.Viewer[ที่นี่](https://forum.groupdocs.com/c/viewer/9).