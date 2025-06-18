---
"description": "เรียนรู้วิธีการเรนเดอร์ภาพ CMX ในรูปแบบต่างๆ ได้อย่างง่ายดายโดยใช้ GroupDocs.Viewer สำหรับ .NET ปรับปรุงการจัดการเอกสารของคุณ"
"linktitle": "การเรนเดอร์ภาพ CMX"
"second_title": "API ของ GroupDocs.Viewer .NET"
"title": "การเรนเดอร์ภาพ CMX"
"url": "/th/net/image-rendering/render-cmx-images/"
"weight": 13
---

# การเรนเดอร์ภาพ CMX

## การแนะนำ
ในแวดวงการจัดการและจัดการเอกสาร การเรนเดอร์รูปภาพจากรูปแบบต่างๆ ถือเป็นงานที่สำคัญ GroupDocs.Viewer สำหรับ .NET ทำให้กระบวนการนี้ง่ายขึ้นโดยจัดให้มีฟังก์ชันที่ครอบคลุมสำหรับการเรนเดอร์รูปภาพ CMX เป็นรูปแบบต่างๆ เช่น HTML, JPG, PNG และ PDF บทช่วยสอนนี้จะแนะนำคุณตลอดกระบวนการเรนเดอร์รูปภาพ CMX โดยใช้ GroupDocs.Viewer สำหรับ .NET ทีละขั้นตอน

![เรนเดอร์ภาพ CMX ด้วย GroupDocs.Viewer สำหรับ .NET](/viewer/image-rendering/render-cmx-images.png)

## ข้อกำหนดเบื้องต้น
ก่อนจะเริ่มบทช่วยสอนนี้ ให้แน่ใจว่าคุณมีข้อกำหนดเบื้องต้นดังต่อไปนี้:
1. GroupDocs.Viewer สำหรับไลบรารี .NET: ดาวน์โหลดและติดตั้งไลบรารี GroupDocs.Viewer สำหรับ .NET จาก [ที่นี่](https://releases-groupdocs.com/viewer/net/).
2. สภาพแวดล้อมการพัฒนา: มีการตั้งค่าสภาพแวดล้อมการพัฒนาการทำงานด้วย .NET framework
3. ไฟล์ภาพ CMX: รับไฟล์ภาพ CMX ที่คุณต้องการเรนเดอร์

## การนำเข้าเนมสเปซ
ก่อนที่จะดำเนินการต่อ โปรดแน่ใจว่าได้นำเข้าเนมสเปซที่จำเป็นเพื่อเข้าถึงฟังก์ชันการทำงานของ GroupDocs.Viewer ในแอปพลิเคชัน .NET ของคุณ:
```csharp
using GroupDocs.Viewer.Options;
using System;
using System.IO;
```

## การเรนเดอร์เป็น HTML
```csharp
string outputDirectory = "Your Document Directory";
string pageFilePathFormat = Path.Combine(outputDirectory, "cmx_result_{0}.html");
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_CMX))
{
    HtmlViewOptions options = HtmlViewOptions.ForEmbeddedResources(pageFilePathFormat);
    viewer.View(options);
}
```
- กำหนดไดเรกทอรีเอาต์พุต: ตั้งค่าไดเรกทอรีที่คุณต้องการจัดเก็บไฟล์ HTML ที่แสดงผล
- ระบุรูปแบบเส้นทางไฟล์: กำหนดรูปแบบสำหรับไฟล์ HTML เอาท์พุต
- สร้างอินสแตนซ์ของวัตถุ Viewer: สร้างอินสแตนซ์ของคลาส Viewer ด้วยไฟล์รูปภาพ CMX
- ตัวเลือกการแสดงผล HTML: กำหนดค่าตัวเลือกการแสดงผล HTML เช่น การฝังทรัพยากร
- เรนเดอร์ CMX เป็น HTML: เรียกใช้เมธอดมุมมองของวัตถุตัวดูเพื่อเรนเดอร์ภาพ CMX เป็น HTML
## การเรนเดอร์เป็น JPG
```csharp
string pageFilePathFormat = Path.Combine(outputDirectory, "cmx_result_{0}.jpg");
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_CMX))
{
    JpgViewOptions options = new JpgViewOptions(pageFilePathFormat);
    
    viewer.View(options);
}
```
- กำหนดไดเรกทอรีเอาต์พุต: ตั้งค่าไดเรกทอรีสำหรับจัดเก็บไฟล์ JPG ที่แสดงผล
- ระบุรูปแบบเส้นทางไฟล์: กำหนดรูปแบบสำหรับไฟล์ JPG เอาท์พุต
- สร้างอินสแตนซ์ของวัตถุ Viewer: สร้างอินสแตนซ์ของคลาส Viewer ด้วยไฟล์รูปภาพ CMX
- ตัวเลือกการเรนเดอร์ JPG: กำหนดค่าตัวเลือกการเรนเดอร์ JPG
- เรนเดอร์ CMX เป็น JPG: เรียกใช้เมธอดมุมมองของวัตถุตัวดูเพื่อเรนเดอร์ภาพ CMX เป็น JPG
## การเรนเดอร์เป็น PNG
```csharp
string pageFilePathFormat = Path.Combine(outputDirectory, "cmx_result_{0}.png");
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_CMX))
{
    PngViewOptions options = new PngViewOptions(pageFilePathFormat);
   
    viewer.View(options);
}
```
- กำหนดไดเร็กทอรีเอาต์พุต: ตั้งค่าไดเร็กทอรีสำหรับจัดเก็บไฟล์ PNG ที่ถูกเรนเดอร์
- ระบุรูปแบบเส้นทางไฟล์: กำหนดรูปแบบสำหรับไฟล์ PNG เอาท์พุต
- สร้างอินสแตนซ์ของวัตถุ Viewer: สร้างอินสแตนซ์ของคลาส Viewer ด้วยไฟล์รูปภาพ CMX
- ตัวเลือกการเรนเดอร์ PNG: กำหนดค่าตัวเลือกการเรนเดอร์ PNG
- เรนเดอร์ CMX เป็น PNG: เรียกใช้เมธอดมุมมองของวัตถุตัวดูเพื่อเรนเดอร์ภาพ CMX เป็น PNG
## การเรนเดอร์เป็น PDF
```csharp
string pageFilePathFormat = Path.Combine(outputDirectory, "cmx_result.pdf");
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_CMX))
{
    PdfViewOptions options = new PdfViewOptions(pageFilePathFormat);
   
    viewer.View(options);
}
```
- กำหนดไดเรกทอรีเอาต์พุต: ตั้งค่าไดเรกทอรีสำหรับจัดเก็บไฟล์ PDF ที่แสดงผล
- ระบุรูปแบบเส้นทางไฟล์: กำหนดรูปแบบสำหรับไฟล์ PDF เอาท์พุต
- สร้างอินสแตนซ์ของวัตถุ Viewer: สร้างอินสแตนซ์ของคลาส Viewer ด้วยไฟล์รูปภาพ CMX
- ตัวเลือกการเรนเดอร์ PDF: กำหนดค่าตัวเลือกการเรนเดอร์ PDF
- เรนเดอร์ CMX เป็น PDF: เรียกใช้เมธอดมุมมองของวัตถุตัวดูเพื่อเรนเดอร์ภาพ CMX เป็น PDF

## บทสรุป
โดยสรุป GroupDocs.Viewer สำหรับ .NET นำเสนอโซลูชันที่แข็งแกร่งสำหรับการเรนเดอร์ภาพ CMX ในรูปแบบต่างๆ ได้อย่างราบรื่น ด้วยการทำตามขั้นตอนที่ระบุไว้ในบทช่วยสอนนี้ คุณสามารถผสานรวมความสามารถในการเรนเดอร์ภาพ CMX ลงในแอปพลิเคชัน .NET ของคุณได้อย่างง่ายดาย ซึ่งจะช่วยเพิ่มประสิทธิภาพในการจัดการเอกสาร
## คำถามที่พบบ่อย
### ฉันสามารถเรนเดอร์หน้าเฉพาะของภาพ CMX ได้หรือไม่
ใช่ คุณสามารถเรนเดอร์หน้าเฉพาะได้โดยระบุหมายเลขหน้าในตัวเลือกการเรนเดอร์
### GroupDocs.Viewer สำหรับ .NET เข้ากันได้กับเฟรมเวิร์ก .NET ทั้งหมดหรือไม่
ใช่ GroupDocs.Viewer สำหรับ .NET เข้ากันได้กับเฟรมเวิร์ก .NET หลายตัว รวมถึง .NET Core และ .NET Framework
### GroupDocs.Viewer รองรับการเรนเดอร์ภาพ CMX ที่เข้ารหัสหรือไม่
ใช่ GroupDocs.Viewer รองรับการเรนเดอร์ภาพ CMX ที่เข้ารหัสด้วยคีย์การถอดรหัสที่เหมาะสม
### ฉันสามารถปรับแต่งตัวเลือกการเรนเดอร์สำหรับรูปแบบเอาต์พุตที่แตกต่างกันได้หรือไม่
แน่นอนว่า GroupDocs.Viewer มีตัวเลือกมากมายในการปรับแต่งพารามิเตอร์การเรนเดอร์ตามความต้องการของคุณ
### มีฟอรัมชุมชนสำหรับการสนับสนุน GroupDocs.Viewer หรือไม่
ใช่ คุณสามารถขอความช่วยเหลือและมีส่วนร่วมกับชุมชน GroupDocs.Viewer บนฟอรัมสนับสนุนได้ [ที่นี่](https://forum-groupdocs.com/c/viewer/9).