---
"description": "ปรับปรุงการดูเอกสารใน .NET! เรียนรู้การแสดงส่วนหัวของแถวและคอลัมน์โดยใช้ GroupDocs.Viewer สำหรับ .NET สำรวจผลลัพธ์ HTML, JPG, PNG และ PDF"
"linktitle": "เรนเดอร์หัวแถวและคอลัมน์"
"second_title": "API ของ GroupDocs.Viewer .NET"
"title": "เรนเดอร์หัวแถวและคอลัมน์"
"url": "/th/net/spreadsheet-rendering-options/render-row-column-headings/"
"weight": 18
type: docs
---
# เรนเดอร์หัวแถวและคอลัมน์

## การแนะนำ
คุณกำลังมองหาวิธีปรับปรุงประสบการณ์การดูเอกสารในแอปพลิเคชัน .NET หรือไม่ ด้วย GroupDocs.Viewer สำหรับ .NET คุณสามารถแสดงส่วนหัวของแถวและคอลัมน์จากไฟล์สเปรดชีตของคุณได้อย่างราบรื่น ในบทช่วยสอนนี้ เราจะแนะนำคุณตลอดกระบวนการแสดงส่วนหัวของแถวและคอลัมน์โดยใช้รูปแบบเอาต์พุตต่างๆ เช่น HTML, JPG, PNG และ PDF
## ข้อกำหนดเบื้องต้น
ก่อนที่จะเริ่มลงลึกในบทช่วยสอนนี้ ให้แน่ใจว่าคุณมีข้อกำหนดเบื้องต้นดังต่อไปนี้:
- ติดตั้ง GroupDocs.Viewer สำหรับไลบรารี .NET
- ไฟล์ตัวอย่าง XLSX สำหรับวัตถุประสงค์ในการทดสอบ
- ความรู้พื้นฐานเกี่ยวกับการพัฒนา C# และ .NET
## นำเข้าเนมสเปซ
ในโค้ด C# ของคุณ ให้แน่ใจว่าคุณได้นำเข้าเนมสเปซที่จำเป็นเพื่อใช้ GroupDocs.Viewer:
```csharp
using GroupDocs.Viewer.Options;
using System;
using System.IO;
```
## 1. ตั้งค่าไดเรกทอรีเอาต์พุต
```csharp
string outputDirectory = "Your Document Directory";
string pageFilePathFormat = Path.Combine(outputDirectory, "page_{0}.html");
```
## 2. เรนเดอร์เป็น HTML
```csharp
using (Viewer viewer = new Viewer("SAMPLE.XLSX"))
{
    HtmlViewOptions options = HtmlViewOptions.ForEmbeddedResources(pageFilePathFormat);
    options.SpreadsheetOptions.RenderHeadings = true;
    viewer.View(options, 1, 2, 3);
}
```
## 3. เรนเดอร์เป็น JPG
```csharp
pageFilePathFormat = Path.Combine(outputDirectory, "page_{0}.jpg");
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_XLSX))
{
    JpgViewOptions options = new JpgViewOptions(pageFilePathFormat);
    options.SpreadsheetOptions.RenderHeadings = true;
    viewer.View(options, 1, 2, 3);
}
```
## 4. เรนเดอร์เป็น PNG
```csharp
pageFilePathFormat = Path.Combine(outputDirectory, "page_{0}.png");
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_XLSX))
{
    PngViewOptions options = new PngViewOptions(pageFilePathFormat);
    options.SpreadsheetOptions.RenderHeadings = true;
    viewer.View(options, 1, 2, 3);
}
```
## 5. เรนเดอร์เป็น PDF
```csharp
pageFilePathFormat = Path.Combine(outputDirectory, "output.pdf");
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_XLSX))
{
    PdfViewOptions options = new PdfViewOptions(pageFilePathFormat);
    options.SpreadsheetOptions.RenderHeadings = true;
    viewer.View(options, 1, 2, 3);
}
```
## บทสรุป
ขอแสดงความยินดี! คุณได้แสดงส่วนหัวของแถวและคอลัมน์จากสเปรดชีตของคุณสำเร็จแล้วโดยใช้ GroupDocs.Viewer สำหรับ .NET ทดลองใช้รูปแบบเอาต์พุตที่แตกต่างกันเพื่อให้เหมาะกับความต้องการของแอปพลิเคชันของคุณ
## คำถามที่พบบ่อย
### ถาม: ฉันสามารถปรับแต่งไดเร็กทอรีเอาท์พุตสำหรับเอกสารที่แสดงผลได้หรือไม่
A: ใช่ คุณสามารถตั้งค่าไดเร็กทอรีเอาท์พุตที่คุณต้องการในโค้ดที่ `outputDirectory` ตัวแปรถูกกำหนดแล้ว
### ถาม: GroupDocs.Viewer เข้ากันได้กับรูปแบบสเปรดชีตอื่นหรือไม่
ตอบ: ใช่ GroupDocs.Viewer รองรับรูปแบบสเปรดชีตต่างๆ รวมถึง XLS, XLSX, CSV และอื่นๆ
### ถาม: ฉันจะจัดการข้อยกเว้นในระหว่างกระบวนการเรนเดอร์ได้อย่างไร
A: คุณสามารถใช้บล็อก try-catch เพื่อจัดการข้อยกเว้นและบันทึกหรือแสดงข้อความที่เหมาะสมให้แก่ผู้ใช้ได้
### ถาม: มีข้อกำหนดการออกใบอนุญาตใดๆ สำหรับการใช้ GroupDocs.Viewer ในแอปพลิเคชันของฉันหรือไม่
A: ใช่ คุณต้องมีใบอนุญาตที่ถูกต้อง คุณสามารถขอใบอนุญาตชั่วคราวเพื่อวัตถุประสงค์ในการทดสอบหรือซื้อใบอนุญาตเต็มรูปแบบสำหรับการผลิตได้
### ถาม: ฉันสามารถหาการสนับสนุนเพิ่มเติมหรือการสนทนาชุมชนได้ที่ไหน
ก. เยี่ยมชม [ฟอรั่ม GroupDocs.Viewer](https://forum.groupdocs.com/c/viewer/9) เพื่อการสนับสนุนและการหารือ