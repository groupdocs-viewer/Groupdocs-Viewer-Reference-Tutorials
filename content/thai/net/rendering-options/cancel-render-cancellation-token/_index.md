---
"description": "รวม Groupdocs.Viewer สำหรับ .NET เข้ากับโครงการ .NET ของคุณอย่างราบรื่นเพื่อการดูเอกสารที่มีประสิทธิภาพ"
"linktitle": "ยกเลิกการแสดงผลด้วยโทเค็นการยกเลิก"
"second_title": "API ของ GroupDocs.Viewer .NET"
"title": "ยกเลิกการแสดงผลด้วยโทเค็นการยกเลิก"
"url": "/th/net/rendering-options/cancel-render-cancellation-token/"
"weight": 11
---

# ยกเลิกการแสดงผลด้วยโทเค็นการยกเลิก

## การแนะนำ
Groupdocs.Viewer สำหรับ .NET เป็นเครื่องมืออันทรงพลังที่ออกแบบมาเพื่อลดความซับซ้อนในการดูและประมวลผลเอกสารภายในแอปพลิเคชัน .NET ไม่ว่าคุณจะกำลังจัดการกับ PDF เอกสาร Microsoft Office หรือรูปแบบทั่วไปอื่นๆ ไลบรารีนี้ก็มีฟังก์ชันการทำงานที่แข็งแกร่งเพื่อผสานรวมความสามารถในการดูเอกสารเข้ากับโครงการ .NET ของคุณได้อย่างราบรื่น
## ข้อกำหนดเบื้องต้น
ก่อนจะดำเนินการบูรณาการของ Groupdocs.Viewer สำหรับ .NET ให้แน่ใจว่าคุณมีข้อกำหนดเบื้องต้นต่อไปนี้:
1. การติดตั้ง: ดาวน์โหลดและติดตั้งไลบรารี Groupdocs.Viewer สำหรับ .NET จากที่ให้มา [ลิงค์ดาวน์โหลด](https://releases-groupdocs.com/viewer/net/).
   
2. ใบอนุญาต: ขอใบอนุญาตจาก [เอกสารกลุ่ม](https://purchase.groupdocs.com/buy) เพื่อปลดล็อกศักยภาพทั้งหมดของห้องสมุด หรือคุณสามารถเริ่มต้นด้วยการทดลองใช้ฟรีโดยใช้ [ใบอนุญาตชั่วคราว](https://purchase-groupdocs.com/temporary-license/).
   
3. สภาพแวดล้อมการพัฒนา: ตรวจสอบให้แน่ใจว่าคุณมีการตั้งค่าสภาพแวดล้อมการพัฒนาที่เข้ากันได้ รวมถึง Visual Studio หรือ IDE .NET อื่น ๆ ที่คุณเลือก

## นำเข้าเนมสเปซ
ในการใช้ Groupdocs.Viewer สำหรับ .NET ได้อย่างมีประสิทธิภาพ คุณจะต้องนำเข้าเนมสเปซที่จำเป็นลงในโปรเจ็กต์ของคุณ ทำตามขั้นตอนเหล่านี้:

```csharp
using System;
using System.IO;
using GroupDocs.Viewer.Options;
using System.Threading.Tasks;
using System.Threading;
```

ตอนนี้เรามาแบ่งตัวอย่างที่ให้มาเป็นขั้นตอนต่างๆ เพื่อให้สามารถเข้าใจและนำไปใช้ได้ดียิ่งขึ้น:
## ขั้นตอนที่ 1: กำหนดไดเรกทอรีผลลัพธ์
```csharp
string outputDirectory = "Your Document Directory";
```
ขั้นตอนนี้จะกำหนดไดเรกทอรีที่จะจัดเก็บหน้าเอกสารที่แสดงผล
## ขั้นตอนที่ 2: กำหนดรูปแบบเส้นทางไฟล์เพจ
```csharp
string pageFilePathFormat = Path.Combine(outputDirectory, "page_{0}.html");
```
ที่นี่เราจะกำหนดรูปแบบสำหรับเส้นทางไฟล์ของหน้าเอกสารแต่ละหน้า
## ขั้นตอนที่ 3: เริ่มต้น CancellationTokenSource
```csharp
CancellationTokenSource cancellationTokenSource = new CancellationTokenSource();
```
CancellationTokenSource ใช้เพื่อสร้างอินสแตนซ์ CancellationToken ที่สามารถใช้ในการยกเลิกการดำเนินการแบบอะซิงโครนัสได้
## ขั้นตอนที่ 4: รับ CancellationToken
```csharp
CancellationToken cancellationToken = cancellationTokenSource.Token;
```
ขั้นตอนนี้จะดึงโทเค็นจาก CancellationTokenSource ซึ่งจะใช้ในการยกเลิกการดำเนินการเรนเดอร์
## ขั้นตอนที่ 5: เรนเดอร์หน้าเอกสาร
```csharp
Task.Run(() =>
{
    using (Viewer viewer = new Viewer(TestFiles.SAMPLE_DOCX, new ViewerSettings(new GroupDocs.Viewer.Logging.ConsoleLogger())))
    {
        HtmlViewOptions options = HtmlViewOptions.ForEmbeddedResources(pageFilePathFormat);
        options.RenderComments = true;
        viewer.View(options, cancellationToken);
    }
}, cancellationToken);
```
ที่นี่ เราเริ่มการเรนเดอร์หน้าเอกสารแบบอะซิงโครนัสโดยใช้ Task.Run() อินสแตนซ์ Viewer จะถูกสร้างขึ้นด้วยไฟล์เอกสารที่ระบุ (SAMPLE_DOCX) และกำหนดค่าตัวเลือกการเรนเดอร์ จากนั้นจึงเริ่มกระบวนการเรนเดอร์โดยใช้เมธอด View ของคลาส Viewer
## ขั้นตอนที่ 6: ตั้งค่าเวลาหมดเวลาการเรนเดอร์
```csharp
cancellationTokenSource.CancelAfter(10);
```
ขั้นตอนนี้จะกำหนดเวลาหมดเวลาการแสดงผลไว้ที่ 10 มิลลิวินาที หากเกินกำหนดเวลาดังกล่าว ระบบจะยกเลิกการทำงานโดยอัตโนมัติ
## ขั้นตอนที่ 7: แสดงข้อความแสดงว่าสำเร็จ
```csharp
Console.WriteLine($"\nSource document rendered successfully.\nCheck output in {outputDirectory}.");
```
ในที่สุดข้อความแสดงความสำเร็จจะปรากฏขึ้น เพื่อแจ้งว่าเอกสารได้รับการแสดงผลสำเร็จแล้ว

## บทสรุป
ในบทช่วยสอนนี้ เราได้กล่าวถึงพื้นฐานของการรวม Groupdocs.Viewer สำหรับ .NET เข้ากับโปรเจ็กต์ของคุณแล้ว โดยทำตามขั้นตอนที่ระบุไว้ข้างต้น คุณสามารถรวมความสามารถในการดูเอกสารเข้ากับแอปพลิเคชัน .NET ของคุณได้อย่างราบรื่น ช่วยเพิ่มประสบการณ์ของผู้ใช้และประสิทธิภาพการทำงาน
## คำถามที่พบบ่อย
### Groupdocs.Viewer สำหรับ .NET เข้ากันได้กับรูปแบบเอกสารทั้งหมดหรือไม่
Groupdocs.Viewer สำหรับ .NET รองรับรูปแบบเอกสารต่างๆ มากมาย รวมถึง PDF, เอกสาร Microsoft Office, รูปภาพ และอื่นๆ อีกมากมาย
### ฉันสามารถปรับแต่งลักษณะที่ปรากฏของหน้าเอกสารที่แสดงผลได้หรือไม่
ใช่ คุณสามารถปรับแต่งด้านต่าง ๆ ของกระบวนการเรนเดอร์ได้ เช่น ขนาดหน้า คุณภาพ ลายน้ำ และอื่น ๆ อีกมากมาย
### Groupdocs.Viewer สำหรับ .NET ต้องใช้การเชื่อมต่ออินเทอร์เน็ตหรือไม่
ไม่ Groupdocs.Viewer สำหรับ .NET ทำงานในเครื่องภายในสภาพแวดล้อม .NET ของคุณ และไม่จำเป็นต้องเชื่อมต่ออินเทอร์เน็ตเพื่อดูเอกสาร
### มีการสนับสนุนด้านเทคนิคสำหรับ Groupdocs.Viewer สำหรับ .NET หรือไม่
ใช่ การสนับสนุนด้านเทคนิคพร้อมให้บริการผ่าน [ฟอรั่ม Groupdocs](https://forum.groupdocs.com/c/viewer/9)ซึ่งคุณสามารถถามคำถาม รายงานปัญหา และโต้ตอบกับชุมชนได้
### ฉันสามารถทดลองใช้ Groupdocs.Viewer สำหรับ .NET ก่อนซื้อได้หรือไม่?
ใช่ คุณสามารถเริ่มต้นด้วยการทดลองใช้ฟรีโดยใช้สิ่งที่ให้ไว้ [เวอร์ชั่นทดลองใช้](https://releases-groupdocs.com/).