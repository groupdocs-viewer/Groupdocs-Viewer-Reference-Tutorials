---
title: เรนเดอร์โฟลเดอร์เก็บถาวร
linktitle: เรนเดอร์โฟลเดอร์เก็บถาวร
second_title: GroupDocs.Viewer .NET API
description: ผสานรวม GroupDocs.Viewer สำหรับ .NET เข้ากับแอปพลิเคชัน .NET ของคุณได้อย่างราบรื่น เพื่อความสามารถในการเรนเดอร์และดูเอกสารอย่างมีประสิทธิภาพ
type: docs
weight: 11
url: /th/net/rendering-archive-files/render-archive-folder/
---
## การแนะนำ
ในยุคดิจิทัลปัจจุบัน การเข้าถึงและดูเอกสารได้อย่างราบรื่นถือเป็นสิ่งสำคัญสำหรับธุรกิจและบุคคลทั่วไป โชคดีที่ด้วยความก้าวหน้าของเทคโนโลยี ขณะนี้นักพัฒนาจึงมีเครื่องมืออันทรงพลังเพื่อรวมความสามารถในการดูเอกสารเข้ากับแอปพลิเคชันของตนได้อย่างง่ายดาย เครื่องมือหนึ่งดังกล่าวคือ GroupDocs.Viewer สำหรับ .NET ซึ่งเป็นไลบรารีอเนกประสงค์ที่ช่วยให้นักพัฒนาสามารถเรนเดอร์รูปแบบเอกสารที่หลากหลายภายในแอปพลิเคชัน .NET ของตนได้
## ข้อกำหนดเบื้องต้น
ก่อนที่จะเจาะลึกการบูรณาการ GroupDocs.Viewer สำหรับ .NET เข้ากับโปรเจ็กต์ของคุณ ตรวจสอบให้แน่ใจว่าคุณมีข้อกำหนดเบื้องต้นต่อไปนี้:
### ความรู้เกี่ยวกับการเขียนโปรแกรม C#
หากต้องการใช้ GroupDocs.Viewer สำหรับ .NET ได้อย่างมีประสิทธิภาพ จำเป็นต้องมีความเข้าใจพื้นฐานเกี่ยวกับภาษาการเขียนโปรแกรม C# ทำความคุ้นเคยกับแนวคิดต่างๆ เช่น คลาส วิธีการ และตัวแปร
### การติดตั้ง GroupDocs.Viewer สำหรับ .NET
ตรวจสอบให้แน่ใจว่าคุณได้ดาวน์โหลดและติดตั้ง GroupDocs.Viewer สำหรับ .NET แล้ว คุณสามารถขอรับห้องสมุดได้จากที่ให้ไว้[ลิ้งค์ดาวน์โหลด](https://releases.groupdocs.com/viewer/net/).
### การตั้งค่าสภาพแวดล้อมการพัฒนา
มีสภาพแวดล้อมการพัฒนาที่กำหนดค่าด้วย Visual Studio หรือ IDE ที่ต้องการสำหรับการพัฒนา .NET

## นำเข้าเนมสเปซ
ก่อนที่จะรวม GroupDocs.Viewer สำหรับ .NET เข้ากับโปรเจ็กต์ของคุณ ให้นำเข้าเนมสเปซที่จำเป็นเพื่อเข้าถึงฟังก์ชันการทำงานได้อย่างราบรื่น:
```csharp
using System;
using System.IO;
using GroupDocs.Viewer.Options;
```

ตอนนี้ เรามาแจกแจงขั้นตอนการเรนเดอร์โฟลเดอร์เก็บถาวรโดยใช้ GroupDocs.Viewer สำหรับ .NET ให้เป็นขั้นตอนที่สามารถจัดการได้:
## ขั้นตอนที่ 1: กำหนดไดเรกทอรีผลลัพธ์
ระบุไดเร็กทอรีที่คุณต้องการให้เอกสารที่แสดงผลถูกบันทึก
```csharp
string outputDirectory = "Your Document Directory";
```
## ขั้นตอนที่ 2: กำหนดรูปแบบเส้นทางไฟล์เพจ
กำหนดรูปแบบการตั้งชื่อไฟล์แต่ละหน้า
```csharp
string pageFilePathFormat = Path.Combine(outputDirectory, "page_{0}.html");
```
## ขั้นตอนที่ 3: สร้างอินสแตนซ์ของวัตถุ Viewer
สร้างอินสแตนซ์ของคลาส Viewer โดยส่งพาธไปยังไฟล์เก็บถาวรเป็นพารามิเตอร์
```csharp
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_ZIP_WITH_FOLDERS))
```
## ขั้นตอนที่ 4: กำหนดค่าตัวเลือกมุมมอง HTML
ตั้งค่าตัวเลือกมุมมอง HTML รวมถึงรูปแบบของทรัพยากรที่ฝังและโฟลเดอร์เป้าหมายภายในไฟล์เก็บถาวร
```csharp
HtmlViewOptions options = HtmlViewOptions.ForEmbeddedResources(pageFilePathFormat);
options.ArchiveOptions.Folder = "ThirdFolderWithItems";
```
## ขั้นตอนที่ 5: เรนเดอร์โฟลเดอร์เก็บถาวร
เรียกใช้เมธอด View ของออบเจ็กต์ Viewer โดยส่งผ่านตัวเลือกมุมมอง HTML ที่กำหนดค่าไว้
```csharp
viewer.View(options);
```
## ขั้นตอนที่ 6: แสดงข้อความแสดงความสำเร็จ
แจ้งให้ผู้ใช้ทราบว่ากระบวนการเรนเดอร์เอกสารเสร็จสมบูรณ์ และจัดเตรียมไดเร็กทอรีเอาต์พุต
```csharp
Console.WriteLine($"\nSource document rendered successfully.\nCheck output in {outputDirectory}.");
```

## บทสรุป
การรวม GroupDocs.Viewer สำหรับ .NET เข้ากับแอปพลิเคชัน .NET ของคุณจะเปิดโลกแห่งความเป็นไปได้ในการแสดงเอกสารที่ราบรื่น ด้วยการทำตามขั้นตอนที่ระบุไว้ คุณสามารถผสานรวมความสามารถในการดูเอกสารได้อย่างง่ายดาย และปรับปรุงฟังก์ชันการทำงานของแอปพลิเคชันของคุณ
## คำถามที่พบบ่อย
### GroupDocs.Viewer สำหรับ .NET เข้ากันได้กับรูปแบบเอกสารทั้งหมดหรือไม่
GroupDocs.Viewer สำหรับ .NET รองรับรูปแบบเอกสารที่หลากหลาย รวมถึง PDF, เอกสาร Microsoft Office, รูปภาพ และอื่นๆ โปรดดูเอกสารประกอบสำหรับรายการที่ครอบคลุม
### ฉันสามารถปรับแต่งลักษณะที่ปรากฏของเอกสารที่แสดงผลได้หรือไม่
ใช่ GroupDocs.Viewer สำหรับ .NET มีตัวเลือกมากมายในการปรับแต่งรูปลักษณ์ของเอกสารที่เรนเดอร์ เช่น ลายน้ำ การหมุนหน้า และการซูม
### GroupDocs.Viewer สำหรับ .NET ให้การสนับสนุนบริการจัดเก็บข้อมูลบนคลาวด์หรือไม่
ได้ คุณสามารถผสานรวม GroupDocs.Viewer สำหรับ .NET เข้ากับบริการจัดเก็บข้อมูลบนคลาวด์ยอดนิยม เช่น Dropbox, Google Drive และ Amazon S3 เพื่อการดึงและเรนเดอร์เอกสารได้อย่างราบรื่น
### มีเวอร์ชันทดลองใช้งานเพื่อการประเมินผลหรือไม่?
ใช่ คุณสามารถใช้ GroupDocs.Viewer สำหรับ .NET รุ่นทดลองใช้ฟรีได้ เพื่อสำรวจคุณลักษณะและความสามารถของ GroupDocs.Viewer ก่อนตัดสินใจซื้อ
### ฉันจะขอความช่วยเหลือได้ที่ไหน หากฉันพบปัญหาหรือมีคำถามเกี่ยวกับ GroupDocs.Viewer for .NET
 ท่านสามารถเยี่ยมชมได้ที่[ฟอรัม GroupDocs.Viewer](https://forum.groupdocs.com/c/viewer/9) เพื่อขอการสนับสนุนจากชุมชนและทีมงาน GroupDocs