---
title: เรนเดอร์รูปภาพ FODG และ ODG
linktitle: เรนเดอร์รูปภาพ FODG และ ODG
second_title: GroupDocs.Viewer .NET API
description: เรียนรู้วิธีเรนเดอร์รูปภาพ FODG และ ODG เป็น HTML, JPG, PNG และ PDF โดยใช้ GroupDocs.Viewer สำหรับ .NET ปรับปรุงการจัดการเอกสารของคุณ
weight: 15
url: /th/net/image-rendering/render-fodg-odg-images/
---

# เรนเดอร์รูปภาพ FODG และ ODG

## การแนะนำ
ในโลกของการพัฒนาซอฟต์แวร์ การจัดการรูปแบบเอกสารอย่างมีประสิทธิภาพเป็นสิ่งสำคัญยิ่ง GroupDocs.Viewer สำหรับ .NET เป็นเครื่องมืออันทรงพลังที่ออกแบบมาเพื่อลดความซับซ้อนของกระบวนการเรนเดอร์ภาพ FODG และ ODG ภายในแอปพลิเคชัน .NET บทช่วยสอนนี้จะแนะนำคุณตลอดขั้นตอนที่จำเป็นในการแสดงรูปภาพเหล่านี้เป็นรูปแบบต่างๆ เช่น HTML, JPG, PNG และ PDF โดยใช้ GroupDocs.Viewer สำหรับ .NET
## ข้อกำหนดเบื้องต้น
ก่อนที่จะเข้าสู่บทช่วยสอน ตรวจสอบให้แน่ใจว่าคุณมีข้อกำหนดเบื้องต้นต่อไปนี้:
1.  GroupDocs.Viewer for .NET: ดาวน์โหลดและติดตั้ง GroupDocs.Viewer for .NET จาก[ที่นี่](https://releases.groupdocs.com/viewer/net/).
2. .NET Framework: ตรวจสอบให้แน่ใจว่าคุณได้ติดตั้ง .NET Framework บนระบบของคุณ
3. ความรู้พื้นฐานของ C#: ความคุ้นเคยกับภาษาการเขียนโปรแกรม C# จะเป็นประโยชน์

## นำเข้าเนมสเปซ
ก่อนที่จะเริ่มใช้งาน ให้นำเข้าเนมสเปซที่จำเป็น:
```csharp
using GroupDocs.Viewer.Options;
using System;
using System.IO;
```
## ขั้นตอนที่ 1: ตั้งค่าไดเรกทอรีผลลัพธ์
```csharp
string outputDirectory = "Your Document Directory";
```
 แทนที่`"Your Document Directory"`ด้วยเส้นทางไดเร็กทอรีที่คุณต้องการบันทึกภาพที่เรนเดอร์
## ขั้นตอนที่ 2: แสดงผลเป็น HTML
```csharp
string pageFilePathFormat = Path.Combine(outputDirectory, "fodg_result.html");
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_FODG))
{
    HtmlViewOptions options = HtmlViewOptions.ForEmbeddedResources(pageFilePathFormat);
    viewer.View(options);
}
```
ขั้นตอนนี้แสดงรูปภาพ FODG เป็นรูปแบบ HTML
## ขั้นตอนที่ 3: แสดงผลเป็น JPG
```csharp
pageFilePathFormat = Path.Combine(outputDirectory, "fodg_result.jpg");
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_FODG))
{
    JpgViewOptions options = new JpgViewOptions(pageFilePathFormat);
    viewer.View(options);
}
```
ที่นี่ รูปภาพ FODG ถูกเรนเดอร์เป็นรูปแบบ JPG
## ขั้นตอนที่ 4: แสดงผลเป็น PNG
```csharp
pageFilePathFormat = Path.Combine(outputDirectory, "fodg_result.png");
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_FODG))
{
    PngViewOptions options = new PngViewOptions(pageFilePathFormat);
    viewer.View(options);
}
```
ขั้นตอนนี้แปลงรูปภาพ FODG เป็นรูปแบบ PNG
## ขั้นตอนที่ 5: แสดงผลเป็น PDF
```csharp
pageFilePathFormat = Path.Combine(outputDirectory, "fodg_result.pdf");
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_FODG))
{
    PdfViewOptions options = new PdfViewOptions(pageFilePathFormat);
    viewer.View(options);
}
```
สุดท้าย รูปภาพ FODG จะถูกเรนเดอร์เป็นรูปแบบ PDF

## บทสรุป
ในบทช่วยสอนนี้ เราได้สำรวจวิธีเรนเดอร์รูปภาพ FODG และ ODG เป็นรูปแบบต่างๆ โดยใช้ GroupDocs.Viewer สำหรับ .NET ด้วยการทำตามขั้นตอนเหล่านี้ คุณสามารถรวมความสามารถในการเรนเดอร์เอกสารเข้ากับแอปพลิเคชัน .NET ของคุณได้อย่างราบรื่น
## คำถามที่พบบ่อย
### GroupDocs.Viewer สำหรับ .NET เข้ากันได้กับ .NET Framework ทุกเวอร์ชันหรือไม่
GroupDocs.Viewer สำหรับ .NET เข้ากันได้กับ .NET Framework เวอร์ชันต่างๆ มากมาย รวมถึงเวอร์ชันล่าสุดด้วย
### ฉันสามารถแสดงเอกสารแบบอะซิงโครนัสด้วย GroupDocs.Viewer สำหรับ .NET ได้หรือไม่
ใช่ GroupDocs.Viewer สำหรับ .NET มีความสามารถในการเรนเดอร์แบบอะซิงโครนัสเพื่อประสิทธิภาพที่ดีขึ้น
### GroupDocs.Viewer สำหรับ .NET รองรับการเรนเดอร์เอกสารที่เข้ารหัสหรือไม่
ใช่ GroupDocs.Viewer สำหรับ .NET รองรับการเรนเดอร์เอกสารที่เข้ารหัสด้วยคีย์ถอดรหัสที่เหมาะสม
### เป็นไปได้ไหมที่จะปรับแต่งเอาต์พุตการเรนเดอร์ด้วย GroupDocs.Viewer สำหรับ .NET
แน่นอนว่า GroupDocs.Viewer สำหรับ .NET มีตัวเลือกการปรับแต่งที่หลากหลายเพื่อปรับแต่งเอาท์พุตการเรนเดอร์ตามความต้องการของคุณ
### ฉันสามารถเรนเดอร์เอกสารจากพื้นที่จัดเก็บข้อมูลระยะไกลโดยใช้ GroupDocs.Viewer สำหรับ .NET ได้หรือไม่
ใช่ GroupDocs.Viewer สำหรับ .NET รองรับการเรนเดอร์เอกสารจากที่จัดเก็บข้อมูลทั้งภายในและระยะไกล