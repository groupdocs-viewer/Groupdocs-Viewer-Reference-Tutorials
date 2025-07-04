---
"description": "ปรับปรุงประสบการณ์การดูเอกสารด้วย GroupDocs.Viewer สำหรับ .NET เรนเดอร์และปรับแต่งอีเมลได้อย่างราบรื่น"
"linktitle": "เปลี่ยนชื่อฟิลด์อีเมลระหว่างการเรนเดอร์"
"second_title": "API ของ GroupDocs.Viewer .NET"
"title": "เปลี่ยนชื่อฟิลด์อีเมลระหว่างการเรนเดอร์"
"url": "/th/net/rendering-email-messages/rename-email-fields/"
"weight": 12
---

# เปลี่ยนชื่อฟิลด์อีเมลระหว่างการเรนเดอร์

## การแนะนำ

ในยุคดิจิทัลทุกวันนี้ การจัดการและการดูเอกสารอย่างมีประสิทธิภาพถือเป็นสิ่งสำคัญสำหรับทั้งธุรกิจและบุคคล ไม่ว่าจะเป็นสัญญา รายงาน หรืออีเมล ความสามารถในการนำทางผ่านเอกสารเหล่านี้อย่างราบรื่นจะช่วยเพิ่มประสิทธิภาพการทำงานได้อย่างมาก ซึ่งนี่คือจุดที่ GroupDocs.Viewer สำหรับ .NET เข้ามามีบทบาท ไลบรารีอันทรงพลังนี้ช่วยให้ผู้พัฒนาสามารถผสานความสามารถในการดูเอกสารเข้ากับแอปพลิเคชัน .NET ได้โดยตรง ซึ่งมีคุณสมบัติมากมายสำหรับการแสดงผลเอกสารในรูปแบบต่างๆ

## ข้อกำหนดเบื้องต้น

ก่อนจะดำดิ่งลงไปในบทช่วยสอนเกี่ยวกับการเปลี่ยนชื่อฟิลด์อีเมลในระหว่างการเรนเดอร์โดยใช้ GroupDocs.Viewer สำหรับ .NET โปรดตรวจสอบให้แน่ใจว่าคุณมีข้อกำหนดเบื้องต้นดังต่อไปนี้:

1. GroupDocs.Viewer สำหรับไลบรารี .NET: ดาวน์โหลดและติดตั้งไลบรารี GroupDocs.Viewer สำหรับ .NET จาก [ที่นี่](https://releases-groupdocs.com/viewer/net/).

2. สภาพแวดล้อมการพัฒนา: ตรวจสอบให้แน่ใจว่าคุณมีการตั้งค่าสภาพแวดล้อมการพัฒนาที่เหมาะสมสำหรับการพัฒนา .NET เช่น Visual Studio

3. ความเข้าใจพื้นฐานเกี่ยวกับ C#: ทำความคุ้นเคยกับพื้นฐานของภาษาการเขียนโปรแกรม C# เนื่องจากบทช่วยสอนนี้จะรวมถึงตัวอย่างโค้ด C#

4. ไดเรกทอรีเอกสาร: จัดเตรียมไดเรกทอรีที่ใช้เก็บเอกสารที่ต้องการแสดง

## นำเข้าเนมสเปซ

เพื่อที่จะใช้ฟังก์ชัน GroupDocs.Viewer ในแอปพลิเคชัน .NET คุณจำเป็นต้องนำเข้าเนมสเปซที่จำเป็น

```csharp
using System;
using System.IO;
using GroupDocs.Viewer.Options;
```

ตอนนี้มาแบ่งกระบวนการเปลี่ยนชื่อฟิลด์อีเมลระหว่างการแสดงผลโดยใช้ GroupDocs.Viewer สำหรับ .NET ออกเป็นหลายขั้นตอน:

## ขั้นตอนที่ 1: กำหนดไดเรกทอรีผลลัพธ์

ประการแรก ให้ระบุไดเรกทอรีที่จะบันทึกหน้า HTML ที่แสดงผล

```csharp
string outputDirectory = "Your Document Directory";
```

## ขั้นตอนที่ 2: กำหนดรูปแบบเส้นทางไฟล์เพจ

กำหนดรูปแบบเส้นทางไฟล์ของหน้า HTML ที่แสดงผล แต่ละหน้าจะถูกบันทึกเป็นไฟล์ HTML แยกกัน

```csharp
string pageFilePathFormat = Path.Combine(outputDirectory, "page_{0}.html");
```

## ขั้นตอนที่ 3: เริ่มต้น Viewer Object

สร้างอินสแตนซ์ของคลาส Viewer และส่งเส้นทางของเอกสารที่จะดูเป็นพารามิเตอร์

```csharp
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_MSG))
{
```

## ขั้นตอนที่ 4: กำหนดค่าตัวเลือกมุมมอง HTML

กำหนดค่าตัวเลือกสำหรับมุมมอง HTML รวมถึงการระบุรูปแบบไฟล์เอาต์พุตและการตั้งค่าการแมปฟิลด์อีเมล

```csharp
HtmlViewOptions options = HtmlViewOptions.ForEmbeddedResources(pageFilePathFormat);
options.EmailOptions.FieldTextMap[Field.From] = "Sender";
options.EmailOptions.FieldTextMap[Field.To] = "Receiver";
options.EmailOptions.FieldTextMap[Field.Sent] = "Date";
options.EmailOptions.FieldTextMap[Field.Subject] = "Topic";
```

## ขั้นตอนที่ 5: เรนเดอร์เอกสาร

เรียกใช้วิธีการมุมมองของวัตถุ Viewer โดยส่งตัวเลือกมุมมอง HTML ที่กำหนดค่าไว้

```csharp
viewer.View(options);
```

## ขั้นตอนที่ 6: แสดงข้อความแสดงว่าสำเร็จ

แจ้งให้ผู้ใช้ทราบว่าเอกสารได้รับการแสดงผลเรียบร้อยแล้ว

```csharp
Console.WriteLine($"\nSource document rendered successfully.\nCheck output in {outputDirectory}.");
```

## บทสรุป

โดยสรุป GroupDocs.Viewer สำหรับ .NET มอบโซลูชันที่ราบรื่นสำหรับการเรนเดอร์เอกสารภายในแอปพลิเคชัน .NET ด้วยการทำตามขั้นตอนที่ระบุไว้ในบทช่วยสอนนี้ คุณสามารถเปลี่ยนชื่อฟิลด์อีเมลได้อย่างง่ายดายระหว่างการเรนเดอร์ ช่วยเพิ่มความสามารถในการอ่านและใช้งานเอกสารอีเมล ด้วย API ที่ใช้งานง่ายและคุณลักษณะที่ครอบคลุม GroupDocs.Viewer ช่วยให้นักพัฒนาสามารถปรับกระบวนการดูเอกสารให้มีประสิทธิภาพ

## คำถามที่พบบ่อย

### ถาม: ฉันสามารถแสดงเอกสารอื่นนอกเหนือจากอีเมลโดยใช้ GroupDocs.Viewer สำหรับ .NET ได้หรือไม่

ตอบ: ใช่ GroupDocs.Viewer รองรับการเรนเดอร์รูปแบบเอกสารต่างๆ รวมถึง PDF, เอกสาร Microsoft Office, รูปภาพ และอื่นๆ อีกมากมาย

### ถาม: GroupDocs.Viewer เข้ากันได้กับ .NET Core ได้หรือไม่

ตอบ: ใช่ GroupDocs.Viewer รองรับ .NET Core และ .NET Framework ดั้งเดิม

### ถาม: ฉันสามารถปรับแต่งลักษณะที่ปรากฏของเอกสารที่แสดงผลได้หรือไม่

A: อย่างแน่นอน GroupDocs.Viewer มีตัวเลือกการปรับแต่งมากมายสำหรับการควบคุมลักษณะที่ปรากฏและลักษณะการทำงานของเอกสารที่แสดงผล

### ถาม: GroupDocs.Viewer รองรับการสตรีมเอกสารหรือไม่

ตอบ: ใช่ GroupDocs.Viewer ช่วยให้สามารถสตรีมเอกสารโดยตรงไปยังเบราว์เซอร์ของไคลเอนต์โดยไม่จำเป็นต้องจัดเก็บไว้ในเซิร์ฟเวอร์

### ถาม: GroupDocs.Viewer เหมาะกับแอปพลิเคชันระดับองค์กรหรือไม่

A: แน่นอน GroupDocs.Viewer ได้รับการออกแบบมาเพื่อตอบสนองความต้องการของแอปพลิเคชันระดับองค์กรด้วยความสามารถในการปรับขนาด ความน่าเชื่อถือ และชุดคุณลักษณะที่แข็งแกร่ง