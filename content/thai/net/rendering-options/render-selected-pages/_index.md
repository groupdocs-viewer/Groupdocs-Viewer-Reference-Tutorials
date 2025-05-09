---
title: แสดงผลหน้าที่เลือก
linktitle: แสดงผลหน้าที่เลือก
second_title: GroupDocs.Viewer .NET API
description: เรียนรู้วิธีการแสดงผลหน้าที่เลือกจากเอกสารโดยใช้ Groupdocs.Viewer สำหรับ .NET บทช่วยสอนทีละขั้นตอนพร้อมตัวอย่างโค้ดรวมอยู่ด้วย
weight: 17
url: /th/net/rendering-options/render-selected-pages/
---

# แสดงผลหน้าที่เลือก

## การแนะนำ

ในบทช่วยสอนนี้ เราจะเจาะลึกถึงวิธีใช้ Groupdocs.Viewer สำหรับ .NET เพื่อแสดงผลหน้าที่เลือกจากเอกสาร ไม่ว่าคุณจะเป็นนักพัฒนาที่มีประสบการณ์หรือเพิ่งเริ่มต้น คำแนะนำทีละขั้นตอนนี้จะนำคุณไปสู่กระบวนการต่างๆ ได้อย่างง่ายดาย

## ข้อกำหนดเบื้องต้น

ก่อนที่เราจะเริ่มต้น ตรวจสอบให้แน่ใจว่าคุณมีข้อกำหนดเบื้องต้นต่อไปนี้:

### 1. การติดตั้ง

 ตรวจสอบให้แน่ใจว่าคุณได้ติดตั้ง Groupdocs.Viewer สำหรับ .NET ในสภาพแวดล้อมการพัฒนาของคุณ ถ้าไม่เช่นนั้นคุณสามารถดาวน์โหลดได้จาก[ลิ้งค์ดาวน์โหลด](https://releases.groupdocs.com/viewer/net/).

## การนำเข้าเนมสเปซ

ในไฟล์โค้ด C# ของคุณ ให้นำเข้าเนมสเปซที่จำเป็นเพื่อเข้าถึงคลาสและวิธีการที่จำเป็น คุณสามารถทำได้โดยใช้`using` คำสั่ง:

```csharp
using System;
using System.IO;
using GroupDocs.Viewer.Options;
```

ตอนนี้เรามาแบ่งโค้ดตัวอย่างออกเป็นหลายขั้นตอน:

## ขั้นตอนที่ 1: ตั้งค่าไดเรกทอรีผลลัพธ์

 กำหนดไดเร็กทอรีที่คุณต้องการให้เพจที่แสดงผลถูกบันทึก แทนที่`"Your Document Directory"` ด้วยเส้นทางไดเร็กทอรีที่ต้องการ

```csharp
string outputDirectory = "Your Document Directory";
```

## ขั้นตอนที่ 2: กำหนดรูปแบบเส้นทางไฟล์เพจ

ระบุรูปแบบสำหรับพาธไฟล์ของเพจที่แสดงผล สิ่งนี้จะถูกใช้เพื่อบันทึกแต่ละหน้าเป็นไฟล์ HTML ในไดเร็กทอรีเอาต์พุต

```csharp
string pageFilePathFormat = Path.Combine(outputDirectory, "page_{0}.html");
```

## ขั้นตอนที่ 3: สร้างอินสแตนซ์ของวัตถุ Viewer

สร้างอินสแตนซ์ของคลาส Viewer โดยส่งผ่านเส้นทางของเอกสารที่คุณต้องการแสดงผลเป็นอาร์กิวเมนต์

```csharp
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_DOCX))
```

## ขั้นตอนที่ 4: กำหนดค่าตัวเลือกมุมมอง HTML

ตั้งค่าตัวเลือกมุมมอง HTML สำหรับการแสดงผล ในตัวอย่างนี้ เรากำลังกำหนดค่าตัวเลือกเพื่อฝังทรัพยากรในเอาต์พุต HTML

```csharp
HtmlViewOptions options = HtmlViewOptions.ForEmbeddedResources(pageFilePathFormat);
```

## ขั้นตอนที่ 5: แสดงผลหน้าที่เลือก

ระบุหมายเลขหน้าที่คุณต้องการแสดงผล ในกรณีนี้ เรากำลังแสดงผลหน้าที่ 1 ถึง 3 จากนั้น เรียกเมธอด View บนออบเจ็กต์ Viewer โดยส่งตัวเลือกและหมายเลขหน้าเป็นอาร์กิวเมนต์

```csharp
viewer.View(options, 1, 3);
```

## ขั้นตอนที่ 6: ผลลัพธ์ผลลัพธ์

สุดท้ายนี้ ให้แสดงข้อความที่ระบุว่าการแสดงผลเอกสารเสร็จสมบูรณ์และตำแหน่งที่บันทึกไฟล์เอาต์พุต

```csharp
Console.WriteLine($"\nSource document rendered successfully.\nCheck output in {outputDirectory}.");
```

## บทสรุป

ยินดีด้วย! คุณได้เรียนรู้วิธีการแสดงผลหน้าที่เลือกจากเอกสารโดยใช้ Groupdocs.Viewer สำหรับ .NET เรียบร้อยแล้ว ด้วยความรู้นี้ คุณสามารถรวมความสามารถในการเรนเดอร์เอกสารเข้ากับแอปพลิเคชัน .NET ของคุณได้อย่างง่ายดาย

## คำถามที่พบบ่อย

### ถาม: ฉันสามารถแสดงหน้าจากเอกสารประเภทต่างๆ เช่น PDF หรือรูปภาพได้หรือไม่

ตอบ: ใช่ Groupdocs.Viewer สำหรับ .NET รองรับการเรนเดอร์เพจจากรูปแบบเอกสารที่หลากหลาย รวมถึง PDF, เอกสาร Microsoft Office และไฟล์รูปภาพ

### ถาม: มีเวอร์ชันทดลองให้ทดสอบก่อนซื้อหรือไม่

 ตอบ: ได้ คุณสามารถเข้าถึง Groupdocs.Viewer สำหรับ .NET เวอร์ชันทดลองใช้ฟรีได้จาก[เว็บไซต์](https://releases.groupdocs.com/).

### ถาม: ฉันสามารถปรับแต่งรูปแบบเอาต์พุตอื่นที่ไม่ใช่ HTML ได้หรือไม่

ตอบ: แน่นอนว่า Groupdocs.Viewer สำหรับ .NET มีตัวเลือกในการเรนเดอร์เพจเป็นรูปภาพ, PDF และอื่นๆ นอกเหนือจาก HTML

### ถาม: ฉันจะขอรับใบอนุญาตชั่วคราวเพื่อการทดสอบได้อย่างไร

ตอบ: สามารถรับใบอนุญาตชั่วคราวได้จาก[หน้าใบอนุญาตชั่วคราว](https://purchase.groupdocs.com/temporary-license/) บนเว็บไซต์ Groupdocs

### ถาม: ฉันจะขอความช่วยเหลือหรือขอความช่วยเหลือเกี่ยวกับปัญหาที่พบได้ที่ไหน

 ตอบ: คุณสามารถเยี่ยมชมได้ที่[ฟอรัม Groupdocs.Viewer](https://forum.groupdocs.com/c/viewer/9) สำหรับการสนับสนุนและคำแนะนำจากชุมชนและนักพัฒนา