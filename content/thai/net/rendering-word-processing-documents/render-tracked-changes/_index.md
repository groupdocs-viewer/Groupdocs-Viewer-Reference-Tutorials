---
title: แสดงผลการเปลี่ยนแปลงที่ติดตาม
linktitle: แสดงผลการเปลี่ยนแปลงที่ติดตาม
second_title: GroupDocs.Viewer .NET API
description: ค้นพบวิธีแสดงการเปลี่ยนแปลงที่ติดตามในเอกสารได้อย่างง่ายดายโดยใช้ GroupDocs.Viewer สำหรับ .NET เพิ่มประสิทธิภาพการจัดการเอกสารของคุณ
weight: 10
url: /th/net/rendering-word-processing-documents/render-tracked-changes/
---

# แสดงผลการเปลี่ยนแปลงที่ติดตาม

## การแนะนำ
ในยุคดิจิทัลปัจจุบัน การจัดการและการดูเอกสารอย่างมีประสิทธิภาพถือเป็นสิ่งสำคัญสำหรับธุรกิจและบุคคลทั่วไป ด้วยการถือกำเนิดของเทคโนโลยีขั้นสูง โซลูชันเช่น GroupDocs.Viewer สำหรับ .NET ได้ปฏิวัติวิธีที่เราโต้ตอบกับรูปแบบเอกสารต่างๆ รวมถึงเอกสาร Word, PDF และอื่นๆ อีกมากมาย ในคู่มือที่ครอบคลุมนี้ เราจะเจาะลึกถึงวิธีใช้ประโยชน์จาก GroupDocs.Viewer สำหรับ .NET เพื่อแสดงผลการเปลี่ยนแปลงที่ติดตามในเอกสารของคุณได้อย่างราบรื่น
## ข้อกำหนดเบื้องต้น
ก่อนที่จะเข้าสู่บทช่วยสอน ตรวจสอบให้แน่ใจว่าคุณมีข้อกำหนดเบื้องต้นต่อไปนี้:
1. การติดตั้ง GroupDocs.Viewer สำหรับ .NET: ดาวน์โหลดและติดตั้ง GroupDocs.Viewer สำหรับ .NET จาก[เว็บไซต์](https://releases.groupdocs.com/viewer/net/).
2. .NET Framework: ตรวจสอบให้แน่ใจว่าคุณได้ติดตั้ง .NET Framework บนระบบของคุณ
3. Document Directory: เตรียมไดเร็กทอรีที่จะจัดเก็บเอกสารของคุณ

## นำเข้าเนมสเปซ
ในการเริ่มต้น ให้นำเข้าเนมสเปซที่จำเป็นลงในโปรเจ็กต์ของคุณ เนมสเปซเหล่านี้จำเป็นสำหรับการใช้ฟังก์ชัน GroupDocs.Viewer อย่างมีประสิทธิภาพ
## ขั้นตอน:
1. เปิด IDE ของคุณ: เรียกใช้ Integrated Development Environment (IDE) ที่คุณต้องการ เช่น Visual Studio
2. สร้างหรือเปิดโครงการของคุณ: เริ่มโครงการใหม่หรือเปิดโครงการที่มีอยู่ซึ่งคุณต้องการใช้ GroupDocs.Viewer
3. นำเข้าเนมสเปซ: ภายในไฟล์โปรเจ็กต์หรือไฟล์โค้ดของคุณ ให้เพิ่มเนมสเปซต่อไปนี้:
```csharp
using System;
using System.IO;
using GroupDocs.Viewer.Options;
```

ตอนนี้ เราจะแบ่งตัวอย่างที่ให้ไว้ออกเป็นหลายขั้นตอนเพื่อแนะนำคุณในการแสดงผลการเปลี่ยนแปลงที่ติดตามโดยใช้ GroupDocs.Viewer สำหรับ .NET
## ขั้นตอนที่ 1: ตั้งค่าไดเรกทอรีผลลัพธ์
ขั้นแรก กำหนดไดเร็กทอรีที่คุณต้องการให้บันทึกเอาต์พุตที่เรนเดอร์ไว้
```csharp
string outputDirectory = "Your Document Directory";
```
 แทนที่`"Your Document Directory"`พร้อมเส้นทางไปยังไดเร็กทอรีที่คุณต้องการ
## ขั้นตอนที่ 2: กำหนดรูปแบบเส้นทางไฟล์เพจ
ระบุรูปแบบสำหรับเส้นทางไฟล์เพจ รูปแบบนี้จะกำหนดวิธีการตั้งชื่อและจัดเก็บเพจที่แสดงผล
```csharp
string pageFilePathFormat = Path.Combine(outputDirectory, "page_{0}.html");
```
 ที่นี่,`"page_{0}.html"` บ่งชี้ว่าเพจต่างๆ จะถูกตั้งชื่อเป็น`page_1.html`, `page_2.html`และอื่นๆ
## ขั้นตอนที่ 3: เริ่มต้นวัตถุ Viewer
 เริ่มต้นก`Viewer` วัตถุโดยผ่านเส้นทางของเอกสารเป็นอาร์กิวเมนต์
```csharp
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_DOCX_WITH_TRACKED_CHANGES))
{
    // รหัสดำเนินต่อไปในขั้นตอนถัดไป...
}
```
 ให้แน่ใจว่าจะเปลี่ยน`TestFiles.SAMPLE_DOCX_WITH_TRACKED_CHANGES` พร้อมเส้นทางไปยังเอกสารของคุณ
## ขั้นตอนที่ 4: กำหนดค่าตัวเลือกมุมมอง HTML
กำหนดค่าตัวเลือกมุมมอง HTML เพื่อปรับแต่งการตั้งค่าการแสดงผล เช่น การแสดงผลการเปลี่ยนแปลงที่ติดตาม
```csharp
HtmlViewOptions options = HtmlViewOptions.ForEmbeddedResources(pageFilePathFormat);
options.WordProcessingOptions.RenderTrackedChanges = true;
```
ขั้นตอนนี้เปิดใช้งานการแสดงผลการเปลี่ยนแปลงที่ติดตามในเอาต์พุต HTML
## ขั้นตอนที่ 5: แสดงผลเอกสาร
แสดงผลเอกสารโดยใช้ตัวเลือกที่กำหนดค่าไว้
```csharp
viewer.View(options);
```
คำสั่งนี้เริ่มต้นกระบวนการเรนเดอร์ตามการตั้งค่าที่ให้ไว้
## ขั้นตอนที่ 6: แสดงไดเรกทอรีผลลัพธ์
แจ้งให้ผู้ใช้ทราบเกี่ยวกับตำแหน่งที่เก็บเอาต์พุตที่แสดงผล
```csharp
Console.WriteLine($"\nSource document rendered successfully.\nCheck output in {outputDirectory}.");
```
ข้อความนี้จะแจ้งให้ผู้ใช้ทราบเกี่ยวกับการเรนเดอร์ที่สำเร็จและตำแหน่งที่จะค้นหาไฟล์เอาต์พุต

## บทสรุป
โดยสรุป GroupDocs.Viewer สำหรับ .NET นำเสนอโซลูชันที่มีประสิทธิภาพสำหรับการแสดงการเปลี่ยนแปลงที่ติดตามในเอกสารได้อย่างง่ายดาย ด้วยการทำตามคำแนะนำทีละขั้นตอนที่สรุปไว้ในบทความนี้ คุณสามารถรวมฟังก์ชันการทำงานนี้เข้ากับแอปพลิเคชัน .NET ของคุณได้อย่างราบรื่น ซึ่งช่วยเพิ่มประสิทธิภาพการจัดการเอกสาร
## คำถามที่พบบ่อย
### ฉันสามารถแสดงการเปลี่ยนแปลงที่ติดตามในรูปแบบเอกสารต่างๆ โดยใช้ GroupDocs.Viewer สำหรับ .NET ได้หรือไม่
ใช่ GroupDocs.Viewer รองรับการเรนเดอร์การเปลี่ยนแปลงที่ติดตามในหลายรูปแบบ รวมถึง DOCX, PDF และอื่นๆ
### GroupDocs.Viewer สำหรับ .NET เข้ากันได้กับ .NET Framework เวอร์ชันทั้งหมดหรือไม่
ใช่ GroupDocs.Viewer สำหรับ .NET เข้ากันได้กับ .NET Framework เวอร์ชันต่างๆ เพื่อให้มั่นใจถึงความเข้ากันได้ในวงกว้าง
### GroupDocs.Viewer เสนอให้ทดลองใช้ฟรีเพื่อการทดสอบหรือไม่
ใช่ คุณสามารถใช้ GroupDocs.Viewer รุ่นทดลองใช้ฟรีเพื่อสำรวจฟีเจอร์ต่างๆ ก่อนตัดสินใจซื้อ
### ฉันสามารถปรับแต่งการตั้งค่าการเรนเดอร์ให้ตรงตามข้อกำหนดเฉพาะได้หรือไม่
แน่นอนว่า GroupDocs.Viewer มีตัวเลือกการปรับแต่งที่หลากหลาย ซึ่งช่วยให้คุณปรับแต่งกระบวนการเรนเดอร์ได้ตามความต้องการของคุณ
### ฉันจะขอความช่วยเหลือได้ที่ไหนหากฉันประสบปัญหาหรือมีคำถามเกี่ยวกับ GroupDocs.Viewer
 สำหรับการสนับสนุนและความช่วยเหลือจากชุมชน คุณสามารถเยี่ยมชมฟอรัม GroupDocs.Viewer ได้ที่[ลิงค์นี้](https://forum.groupdocs.com/c/viewer/9).