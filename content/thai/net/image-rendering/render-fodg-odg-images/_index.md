---
"description": "เรียนรู้วิธีการเรนเดอร์ภาพ FODG และ ODG เป็น HTML, JPG, PNG และ PDF โดยใช้ GroupDocs.Viewer สำหรับ .NET ปรับปรุงการจัดการเอกสารของคุณ"
"linktitle": "เรนเดอร์ภาพ FODG และ ODG"
"second_title": "API ของ GroupDocs.Viewer .NET"
"title": "เรนเดอร์ภาพ FODG และ ODG"
"url": "/th/net/image-rendering/render-fodg-odg-images/"
"weight": 15
type: docs
---
# เรนเดอร์ภาพ FODG และ ODG

## การแนะนำ
ในโลกของการพัฒนาซอฟต์แวร์ การจัดการรูปแบบเอกสารอย่างมีประสิทธิภาพถือเป็นสิ่งสำคัญที่สุด GroupDocs.Viewer สำหรับ .NET เป็นเครื่องมืออันทรงพลังที่ออกแบบมาเพื่อลดความซับซ้อนของกระบวนการเรนเดอร์ภาพ FODG และ ODG ในแอปพลิเคชัน .NET บทช่วยสอนนี้จะแนะนำคุณเกี่ยวกับขั้นตอนที่จำเป็นในการเรนเดอร์ภาพเหล่านี้ในรูปแบบต่างๆ เช่น HTML, JPG, PNG และ PDF โดยใช้ GroupDocs.Viewer สำหรับ .NET

![เรนเดอร์ภาพ FODG และ ODG ด้วย GroupDocs.Viewer สำหรับ .NET](/viewer/image-rendering/render-fodg-and--odg-images.png)

## ข้อกำหนดเบื้องต้น
ก่อนจะเริ่มบทช่วยสอนนี้ ให้แน่ใจว่าคุณมีข้อกำหนดเบื้องต้นดังต่อไปนี้:
1. GroupDocs.Viewer สำหรับ .NET: ดาวน์โหลดและติดตั้ง GroupDocs.Viewer สำหรับ .NET จาก [ที่นี่](https://releases-groupdocs.com/viewer/net/).
2. .NET Framework: ตรวจสอบให้แน่ใจว่าคุณได้ติดตั้ง .NET Framework ไว้ในระบบของคุณแล้ว
3. ความรู้พื้นฐานเกี่ยวกับ C#: ความคุ้นเคยกับภาษาการเขียนโปรแกรม C# จะเป็นประโยชน์

## นำเข้าเนมสเปซ
ก่อนที่จะเริ่มใช้งาน ให้โหลดเนมสเปซที่จำเป็น:
```csharp
using GroupDocs.Viewer.Options;
using System;
using System.IO;
```
## ขั้นตอนที่ 1: ตั้งค่าไดเรกทอรีผลลัพธ์
```csharp
string outputDirectory = "Your Document Directory";
```
แทนที่ `"Your Document Directory"` โดยมีเส้นทางไดเร็กทอรีที่คุณต้องการบันทึกรูปภาพที่เรนเดอร์
## ขั้นตอนที่ 2: เรนเดอร์เป็น HTML
```csharp
string pageFilePathFormat = Path.Combine(outputDirectory, "fodg_result.html");
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_FODG))
{
    HtmlViewOptions options = HtmlViewOptions.ForEmbeddedResources(pageFilePathFormat);
    viewer.View(options);
}
```
ขั้นตอนนี้จะแสดงภาพ FODG เป็นรูปแบบ HTML
## ขั้นตอนที่ 3: เรนเดอร์เป็น JPG
```csharp
pageFilePathFormat = Path.Combine(outputDirectory, "fodg_result.jpg");
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_FODG))
{
    JpgViewOptions options = new JpgViewOptions(pageFilePathFormat);
    viewer.View(options);
}
```
ที่นี่ภาพ FODG จะถูกเรนเดอร์เป็นรูปแบบ JPG
## ขั้นตอนที่ 4: เรนเดอร์เป็น PNG
```csharp
pageFilePathFormat = Path.Combine(outputDirectory, "fodg_result.png");
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_FODG))
{
    PngViewOptions options = new PngViewOptions(pageFilePathFormat);
    viewer.View(options);
}
```
ขั้นตอนนี้จะแปลงภาพ FODG เป็นรูปแบบ PNG
## ขั้นตอนที่ 5: เรนเดอร์เป็น PDF
```csharp
pageFilePathFormat = Path.Combine(outputDirectory, "fodg_result.pdf");
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_FODG))
{
    PdfViewOptions options = new PdfViewOptions(pageFilePathFormat);
    viewer.View(options);
}
```
ในที่สุดภาพ FODG จะถูกเรนเดอร์เป็นรูปแบบ PDF

## บทสรุป
ในบทช่วยสอนนี้ เราได้ศึกษาวิธีการเรนเดอร์ภาพ FODG และ ODG เป็นรูปแบบต่างๆ โดยใช้ GroupDocs.Viewer สำหรับ .NET เมื่อทำตามขั้นตอนเหล่านี้แล้ว คุณจะสามารถผสานรวมความสามารถในการเรนเดอร์เอกสารเข้ากับแอปพลิเคชัน .NET ได้อย่างราบรื่น
## คำถามที่พบบ่อย
### GroupDocs.Viewer สำหรับ .NET เข้ากันได้กับ .NET Framework ทุกเวอร์ชันหรือไม่
GroupDocs.Viewer สำหรับ .NET เข้ากันได้กับ .NET Framework เวอร์ชันต่างๆ มากมาย รวมถึงเวอร์ชันล่าสุดด้วย
### ฉันสามารถแสดงเอกสารแบบอะซิงโครนัสด้วย GroupDocs.Viewer สำหรับ .NET ได้หรือไม่
ใช่ GroupDocs.Viewer สำหรับ .NET ให้ความสามารถในการเรนเดอร์แบบอะซิงโครนัสเพื่อประสิทธิภาพที่ดีขึ้น
### GroupDocs.Viewer สำหรับ .NET รองรับการเรนเดอร์เอกสารเข้ารหัสหรือไม่
ใช่ GroupDocs.Viewer สำหรับ .NET รองรับการเรนเดอร์เอกสารเข้ารหัสด้วยคีย์การถอดรหัสที่เหมาะสม
### เป็นไปได้หรือไม่ที่จะปรับแต่งผลลัพธ์การเรนเดอร์ด้วย GroupDocs.Viewer สำหรับ .NET?
แน่นอนว่า GroupDocs.Viewer สำหรับ .NET นำเสนอตัวเลือกการปรับแต่งต่างๆ เพื่อปรับแต่งผลลัพธ์การเรนเดอร์ตามความต้องการของคุณ
### ฉันสามารถแสดงเอกสารจากตำแหน่งจัดเก็บข้อมูลระยะไกลโดยใช้ GroupDocs.Viewer สำหรับ .NET ได้หรือไม่
ใช่ GroupDocs.Viewer สำหรับ .NET รองรับการเรนเดอร์เอกสารจากตำแหน่งเก็บข้อมูลทั้งภายในและระยะไกล