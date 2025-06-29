---
"description": "เรียนรู้วิธีการแสดงเอกสารพร้อมบันทึกย่อโดยใช้ GroupDocs.Viewer สำหรับ .NET บทช่วยสอนแบบทีละขั้นตอนสำหรับการผสานรวมเข้ากับแอปพลิเคชัน .NET ของคุณอย่างราบรื่น"
"linktitle": "เรนเดอร์เอกสารพร้อมหมายเหตุ"
"second_title": "API ของ GroupDocs.Viewer .NET"
"title": "เรนเดอร์เอกสารพร้อมหมายเหตุ"
"url": "/th/net/rendering-options/render-document-notes/"
"weight": 14
---

# เรนเดอร์เอกสารพร้อมหมายเหตุ

## การแนะนำ
GroupDocs.Viewer สำหรับ .NET เป็นโซลูชันที่มีประสิทธิภาพสำหรับการจัดการและการดูเอกสาร โดยผสานรวมได้อย่างราบรื่นและมีฟังก์ชันการทำงานอันทรงพลัง บทช่วยสอนนี้มุ่งหวังที่จะแนะนำคุณตลอดกระบวนการเรนเดอร์เอกสารพร้อมหมายเหตุโดยใช้ GroupDocs.Viewer สำหรับ .NET ไม่ว่าคุณจะเป็นนักพัฒนาที่มีประสบการณ์หรือเพิ่งเริ่มใช้ .NET คำแนะนำทีละขั้นตอนนี้จะช่วยให้คุณเข้าใจความซับซ้อนของการเรนเดอร์เอกสารได้อย่างง่ายดาย
## ข้อกำหนดเบื้องต้น
ก่อนจะเริ่มบทช่วยสอนนี้ ให้แน่ใจว่าคุณมีข้อกำหนดเบื้องต้นดังต่อไปนี้:
### 1. การติดตั้ง GroupDocs.Viewer สำหรับ .NET
ก่อนอื่นเลย คุณต้องติดตั้ง GroupDocs.Viewer สำหรับ .NET ไว้ในสภาพแวดล้อมการพัฒนาของคุณก่อน คุณสามารถดาวน์โหลดไฟล์ที่จำเป็นได้จากไฟล์ที่ให้มา [ลิงค์ดาวน์โหลด](https://releases.groupdocs.com/viewer/net/) และทำตามคำแนะนำการติดตั้ง
### 2. ความรู้พื้นฐานเกี่ยวกับ .NET Framework
ความเข้าใจพื้นฐานเกี่ยวกับกรอบงาน .NET ถือเป็นสิ่งสำคัญในการทำความเข้าใจแนวคิดและปฏิบัติตามขั้นตอนที่ระบุไว้ในบทช่วยสอนนี้ หากคุณเพิ่งเริ่มใช้ .NET โปรดพิจารณาทำความคุ้นเคยกับพื้นฐานของกรอบงานดังกล่าวผ่านทรัพยากรออนไลน์หรือบทช่วยสอน
### 3. ความคุ้นเคยกับภาษาการเขียนโปรแกรม C#
เนื่องจาก GroupDocs.Viewer สำหรับ .NET ทำงานภายในสภาพแวดล้อม C# ความคุ้นเคยกับภาษาการเขียนโปรแกรม C# จึงมีความสำคัญอย่างยิ่ง ตรวจสอบให้แน่ใจว่าคุณมีความรู้พื้นฐานเกี่ยวกับไวยากรณ์ C# ประเภทข้อมูล และหลักการเขียนโปรแกรมเชิงวัตถุ
### 4. ไฟล์เอกสารพร้อมบันทึก
ตรวจสอบให้แน่ใจว่าคุณมีไฟล์เอกสารที่มีหมายเหตุที่คุณต้องการเรนเดอร์โดยใช้ GroupDocs.Viewer สำหรับ .NET รูปแบบที่รองรับ ได้แก่ PDF, DOCX, PPTX เป็นต้น แต่ไม่จำกัดเพียงเท่านั้น

## นำเข้าเนมสเปซ
ตอนนี้คุณมีข้อกำหนดเบื้องต้นแล้ว เรามาดำเนินการนำเข้าเนมสเปซที่จำเป็นเพื่อเริ่มกระบวนการเรนเดอร์เอกสารกันเลย

```csharp
using System;
using System.IO;
using GroupDocs.Viewer.Options;
```
เนมสเปซ System.IO จัดเตรียมคลาสสำหรับการอ่านและการเขียนไปยังไฟล์และสตรีม ซึ่งจะถูกใช้สำหรับการจัดการเส้นทางไฟล์ในระหว่างกระบวนการเรนเดอร์

ตอนนี้ มาแบ่งขั้นตอนในการเรนเดอร์เอกสารพร้อมบันทึกเป็นชุดคำแนะนำทีละขั้นตอนกัน
## ขั้นตอนที่ 1: กำหนดไดเรกทอรีผลลัพธ์
```csharp
string outputDirectory = "Your Document Directory";
```
ระบุไดเรกทอรีที่คุณต้องการบันทึกไฟล์เอกสารที่แสดงผล ตรวจสอบให้แน่ใจว่าคุณมีสิทธิ์ที่เหมาะสมในการเขียนลงในไดเรกทอรีนี้
## ขั้นตอนที่ 2: กำหนดรูปแบบเส้นทางไฟล์เพจ
```csharp
string pageFilePathFormat = Path.Combine(outputDirectory, "page_{0}.html");
```
กำหนดรูปแบบเส้นทางไฟล์สำหรับหน้าต่างๆ ของเอกสารที่แสดงผล รูปแบบนี้จะกำหนดว่าหน้าต่างๆ จะถูกตั้งชื่อและจัดระเบียบอย่างไรในไดเร็กทอรีเอาต์พุต
## ขั้นตอนที่ 3: เริ่มต้น Viewer Object
```csharp
using (Viewer viewer = new Viewer(TestFiles.PPTX_WITH_NOTES))
```
เริ่มต้นวัตถุ Viewer โดยระบุเส้นทางไปยังไฟล์เอกสารพร้อมหมายเหตุ แทนที่ `TestFiles.PPTX_WITH_NOTES` พร้อมเส้นทางจริงไปยังไฟล์เอกสารของคุณ
## ขั้นตอนที่ 4: กำหนดค่าตัวเลือกมุมมอง HTML
```csharp
HtmlViewOptions options = HtmlViewOptions.ForEmbeddedResources(pageFilePathFormat);
options.RenderNotes = true;
```
กำหนดค่าตัวเลือกมุมมอง HTML สำหรับการแสดงผลเอกสาร เปิดใช้งานการแสดงผลบันทึกย่อโดยตั้งค่า `RenderNotes` ทรัพย์สินที่จะ `true`-
## ขั้นตอนที่ 5: เรนเดอร์เอกสาร
```csharp
viewer.View(options);
```
เรียกใช้ `View` วิธีการของวัตถุ Viewer โดยส่งผ่านตัวเลือกมุมมอง HTML ที่กำหนดค่าไว้ การดำเนินการนี้จะเริ่มกระบวนการแสดงผลสำหรับเอกสารพร้อมหมายเหตุ
## ขั้นตอนที่ 6: แสดงไดเรกทอรีผลลัพธ์
```csharp
Console.WriteLine($"\nSource document rendered successfully.\nCheck output in {outputDirectory}.");
```
แสดงข้อความที่ระบุว่าการเรนเดอร์สำเร็จ และระบุเส้นทางไปยังไดเร็กทอรีเอาต์พุตซึ่งไฟล์เอกสารที่เรนเดอร์ตั้งอยู่

## บทสรุป
โดยสรุป การเรนเดอร์เอกสารพร้อมหมายเหตุโดยใช้ GroupDocs.Viewer สำหรับ .NET เป็นกระบวนการที่ตรงไปตรงมาซึ่งสามารถทำได้โดยใช้โค้ดเพียงไม่กี่บรรทัด โดยทำตามขั้นตอนที่ระบุไว้ในบทช่วยสอนนี้และใช้ประโยชน์จากฟีเจอร์อันทรงพลังของ GroupDocs.Viewer คุณสามารถผสานรวมความสามารถในการดูเอกสารเข้ากับแอปพลิเคชัน .NET ของคุณได้อย่างราบรื่น
## คำถามที่พบบ่อย
### GroupDocs.Viewer สำหรับ .NET เข้ากันได้กับรูปแบบเอกสารทั้งหมดหรือไม่
GroupDocs.Viewer สำหรับ .NET รองรับรูปแบบเอกสารต่างๆ มากมาย เช่น PDF, DOCX, PPTX, XLSX และอื่นๆ โปรดดูเอกสารประกอบเพื่อดูรายการรูปแบบที่รองรับทั้งหมด
### ฉันสามารถปรับแต่งตัวเลือกการเรนเดอร์เพื่อให้เหมาะกับความต้องการเฉพาะได้หรือไม่
ใช่ GroupDocs.Viewer สำหรับ .NET มีตัวเลือกการปรับแต่งมากมายสำหรับการเรนเดอร์เอกสาร ช่วยให้คุณปรับแต่งเอาต์พุตตามความต้องการของคุณได้
### มี GroupDocs.Viewer สำหรับ .NET ให้ทดลองใช้งานฟรีหรือไม่
ใช่ คุณสามารถใช้ประโยชน์จากการทดลองใช้ GroupDocs.Viewer สำหรับ .NET ฟรีได้จากเว็บไซต์ที่ให้มา [ลิงค์](https://releases-groupdocs.com/).
### ฉันสามารถค้นหาการสนับสนุนด้านเทคนิคหรือความช่วยเหลือสำหรับ GroupDocs.Viewer สำหรับ .NET ได้จากที่ไหน
หากต้องการการสนับสนุนและความช่วยเหลือด้านเทคนิค คุณสามารถเยี่ยมชมฟอรัม GroupDocs.Viewer ได้ [ที่นี่](https://forum-groupdocs.com/c/viewer/9).
### ฉันสามารถรับใบอนุญาตชั่วคราวสำหรับ GroupDocs.Viewer สำหรับ .NET ได้หรือไม่
ใช่ คุณสามารถขอรับใบอนุญาตชั่วคราวสำหรับ GroupDocs.Viewer สำหรับ .NET ได้จากที่ให้ไว้ [ลิงค์](https://purchase-groupdocs.com/temporary-license/).