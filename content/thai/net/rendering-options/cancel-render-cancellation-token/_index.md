---
title: ยกเลิกการเรนเดอร์ด้วยโทเค็นการยกเลิก
linktitle: ยกเลิกการเรนเดอร์ด้วยโทเค็นการยกเลิก
second_title: GroupDocs.Viewer .NET API
description: ผสานรวม Groupdocs.Viewer สำหรับ .NET เข้ากับโปรเจ็กต์ .NET ของคุณได้อย่างราบรื่นเพื่อการดูเอกสารที่มีประสิทธิภาพ
weight: 11
url: /th/net/rendering-options/cancel-render-cancellation-token/
---
## การแนะนำ
Groupdocs.Viewer สำหรับ .NET เป็นเครื่องมืออันทรงพลังที่ออกแบบมาเพื่อลดความซับซ้อนในการดูและประมวลผลเอกสารภายในแอปพลิเคชัน .NET ไม่ว่าคุณจะจัดการกับ PDF, เอกสาร Microsoft Office หรือรูปแบบทั่วไปอื่นๆ ไลบรารีนี้มีฟังก์ชันการทำงานที่มีประสิทธิภาพเพื่อรวมความสามารถในการดูเอกสารเข้ากับโครงการ .NET ของคุณได้อย่างราบรื่น
## ข้อกำหนดเบื้องต้น
ก่อนที่จะเจาะลึกการบูรณาการ Groupdocs.Viewer สำหรับ .NET ตรวจสอบให้แน่ใจว่าคุณมีข้อกำหนดเบื้องต้นต่อไปนี้:
1.  การติดตั้ง: ดาวน์โหลดและติดตั้งไลบรารี Groupdocs.Viewer สำหรับ .NET จากไฟล์ที่ให้มา[ลิ้งค์ดาวน์โหลด](https://releases.groupdocs.com/viewer/net/).
   
2.  ใบอนุญาต: ได้รับใบอนุญาตจาก[Groupdocs](https://purchase.groupdocs.com/buy) เพื่อปลดล็อกศักยภาพของห้องสมุดอย่างเต็มประสิทธิภาพ หรือคุณสามารถเริ่มต้นด้วยการทดลองใช้ฟรีโดยใช้[ใบอนุญาตชั่วคราว](https://purchase.groupdocs.com/temporary-license/).
   
3. สภาพแวดล้อมการพัฒนา: ตรวจสอบให้แน่ใจว่าคุณได้ตั้งค่าสภาพแวดล้อมการพัฒนาที่เข้ากันได้ รวมถึง Visual Studio หรือ .NET IDE อื่นๆ ที่คุณเลือก

## นำเข้าเนมสเปซ
เพื่อที่จะใช้ Groupdocs.Viewer สำหรับ .NET อย่างมีประสิทธิภาพ คุณจะต้องนำเข้าเนมสเปซที่จำเป็นลงในโปรเจ็กต์ของคุณ ทำตามขั้นตอนเหล่านี้:

```csharp
using System;
using System.IO;
using GroupDocs.Viewer.Options;
using System.Threading.Tasks;
using System.Threading;
```

ตอนนี้ เรามาแบ่งตัวอย่างที่ให้ไว้ออกเป็นหลายขั้นตอนเพื่อความเข้าใจและการนำไปปฏิบัติที่ดีขึ้น:
## ขั้นตอนที่ 1: กำหนดไดเรกทอรีผลลัพธ์
```csharp
string outputDirectory = "Your Document Directory";
```
ขั้นตอนนี้ตั้งค่าไดเร็กทอรีที่จะจัดเก็บหน้าเอกสารที่แสดงผล
## ขั้นตอนที่ 2: กำหนดรูปแบบเส้นทางไฟล์เพจ
```csharp
string pageFilePathFormat = Path.Combine(outputDirectory, "page_{0}.html");
```
ที่นี่ เรากำหนดรูปแบบสำหรับเส้นทางไฟล์ของหน้าเอกสารแต่ละหน้า
## ขั้นตอนที่ 3: เริ่มต้น CancellationTokenSource
```csharp
CancellationTokenSource cancellationTokenSource = new CancellationTokenSource();
```
CancellationTokenSource ใช้เพื่อสร้างอินสแตนซ์ CancellationToken ที่สามารถใช้เพื่อยกเลิกการดำเนินการแบบอะซิงโครนัส
## ขั้นตอนที่ 4: รับ CancellationToken
```csharp
CancellationToken cancellationToken = cancellationTokenSource.Token;
```
ขั้นตอนนี้จะดึงโทเค็นจาก CancellationTokenSource ซึ่งจะใช้เพื่อยกเลิกการดำเนินการเรนเดอร์
## ขั้นตอนที่ 5: แสดงผลหน้าเอกสาร
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
ที่นี่ เราเริ่มต้นการเรนเดอร์หน้าเอกสารแบบอะซิงโครนัสโดยใช้ Task.Run() อินสแตนซ์ Viewer ถูกสร้างขึ้นด้วยไฟล์เอกสารที่ระบุ (SAMPLE_DOCX) และมีการกำหนดค่าตัวเลือกการแสดงผล จากนั้นกระบวนการเรนเดอร์จะเริ่มต้นโดยใช้วิธี View ของคลาส Viewer
## ขั้นตอนที่ 6: ตั้งค่าการหมดเวลาการเรนเดอร์
```csharp
cancellationTokenSource.CancelAfter(10);
```
ขั้นตอนนี้ตั้งค่าการหมดเวลา 10 มิลลิวินาทีสำหรับการดำเนินการเรนเดอร์ หากการดำเนินการเกินระยะหมดเวลานี้ การดำเนินการจะถูกยกเลิกโดยอัตโนมัติ
## ขั้นตอนที่ 7: แสดงข้อความแสดงความสำเร็จ
```csharp
Console.WriteLine($"\nSource document rendered successfully.\nCheck output in {outputDirectory}.");
```
ในที่สุด ข้อความแสดงความสำเร็จจะปรากฏขึ้นเพื่อระบุว่าเอกสารแสดงผลสำเร็จแล้ว

## บทสรุป
ในบทช่วยสอนนี้ เราได้กล่าวถึงพื้นฐานของการรวม Groupdocs.Viewer สำหรับ .NET เข้ากับโปรเจ็กต์ของคุณ ด้วยการทำตามขั้นตอนที่อธิบายไว้ข้างต้น คุณสามารถรวมความสามารถในการดูเอกสารเข้ากับแอปพลิเคชัน .NET ของคุณได้อย่างราบรื่น ซึ่งจะช่วยยกระดับประสบการณ์ผู้ใช้และประสิทธิภาพการทำงาน
## คำถามที่พบบ่อย
### Groupdocs.Viewer สำหรับ .NET เข้ากันได้กับรูปแบบเอกสารทั้งหมดหรือไม่
Groupdocs.Viewer สำหรับ .NET รองรับรูปแบบเอกสารที่หลากหลาย รวมถึง PDF, เอกสาร Microsoft Office, รูปภาพ และอื่นๆ
### ฉันสามารถปรับแต่งลักษณะที่ปรากฏของหน้าเอกสารที่แสดงผลได้หรือไม่
ใช่ คุณสามารถปรับแต่งแง่มุมต่างๆ ของกระบวนการเรนเดอร์ได้ รวมถึงขนาดหน้า คุณภาพ ลายน้ำ และอื่นๆ
### Groupdocs.Viewer สำหรับ .NET จำเป็นต้องเชื่อมต่ออินเทอร์เน็ตหรือไม่
ไม่ Groupdocs.Viewer สำหรับ .NET ทำงานภายในเครื่องภายในสภาพแวดล้อม .NET ของคุณ และไม่จำเป็นต้องเชื่อมต่ออินเทอร์เน็ตสำหรับการดูเอกสาร
### มีการสนับสนุนทางเทคนิคสำหรับ Groupdocs.Viewer สำหรับ .NET หรือไม่
 ใช่ มีการสนับสนุนทางเทคนิคผ่านทาง[ฟอรั่ม Groupdocs](https://forum.groupdocs.com/c/viewer/9)ซึ่งคุณสามารถถามคำถาม รายงานปัญหา และโต้ตอบกับชุมชนได้
### ฉันสามารถลองใช้ Groupdocs.Viewer สำหรับ .NET ก่อนซื้อได้หรือไม่
 ใช่ คุณสามารถเริ่มต้นด้วยการทดลองใช้ฟรีโดยใช้สิ่งที่ให้มา[เวอร์ชั่นทดลอง](https://releases.groupdocs.com/).