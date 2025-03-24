---
title: เรนเดอร์รูปภาพ WMZ และ WMF
linktitle: เรนเดอร์รูปภาพ WMZ และ WMF
second_title: GroupDocs.Viewer .NET API
description: เรนเดอร์อิมเมจ WMZ และ WMF ในแอปพลิเคชัน .NET ได้อย่างง่ายดายโดยใช้ GroupDocs.Viewer สำหรับ .NET เพิ่มความสามารถในการประมวลผลเอกสารได้อย่างง่ายดาย
weight: 18
url: /th/net/image-rendering/render-wmz-wmf-images/
---

# เรนเดอร์รูปภาพ WMZ และ WMF

## การแนะนำ

ในขอบเขตของการพัฒนาซอฟต์แวร์ การจัดการและการเรนเดอร์เอกสารรูปแบบต่างๆ อย่างมีประสิทธิภาพถือเป็นสิ่งสำคัญยิ่ง GroupDocs.Viewer สำหรับ .NET เป็นเครื่องมืออันทรงพลังที่อำนวยความสะดวกในการเรนเดอร์รูปแบบเอกสารที่หลากหลาย ช่วยให้มั่นใจได้ถึงการบูรณาการที่ราบรื่นและเพิ่มประสบการณ์ผู้ใช้ภายในแอปพลิเคชัน .NET ความสามารถอย่างหนึ่งคือการเรนเดอร์รูปภาพ WMZ และ WMF ซึ่งเป็นงานที่มักพบในสถานการณ์การประมวลผลเอกสาร

## ข้อกำหนดเบื้องต้น

ก่อนที่จะเจาะลึกกระบวนการเรนเดอร์อิมเมจ WMZ และ WMF โดยใช้ GroupDocs.Viewer สำหรับ .NET มีข้อกำหนดเบื้องต้นหลายประการที่ต้องปฏิบัติตาม:

1.  การติดตั้ง GroupDocs.Viewer for .NET: เริ่มต้นด้วยการดาวน์โหลดและติดตั้ง GroupDocs.Viewer for .NET จากไฟล์ที่ให้มา[ลิ้งค์ดาวน์โหลด](https://releases.groupdocs.com/viewer/net/). ปฏิบัติตามคำแนะนำในการติดตั้งเพื่อให้แน่ใจว่ามีการตั้งค่าที่เหมาะสม

2.  การได้รับใบอนุญาต: หากต้องการใช้ GroupDocs.Viewer สำหรับ .NET คุณจะต้องได้รับใบอนุญาต คุณสามารถเลือกรับใบอนุญาตชั่วคราวได้จาก[หน้าใบอนุญาตชั่วคราว](https://purchase.groupdocs.com/temporary-license/) หรือซื้อใบอนุญาตฉบับสมบูรณ์จาก[หน้าซื้อ](https://purchase.groupdocs.com/buy).

3. ความคุ้นเคยกับ .NET Environment: ความเข้าใจพื้นฐานเกี่ยวกับ .NET Framework และภาษาการเขียนโปรแกรม C# ถือเป็นสิ่งสำคัญสำหรับการนำกระบวนการเรนเดอร์ไปใช้อย่างมีประสิทธิภาพ

4.  การบูรณาการเข้ากับโปรเจ็กต์ของคุณ: ตรวจสอบให้แน่ใจว่า GroupDocs.Viewer สำหรับ .NET ได้รับการผสานรวมเข้ากับโปรเจ็กต์ .NET ของคุณอย่างเหมาะสม โปรดดูเอกสารประกอบสำหรับคำแนะนำโดยละเอียดเกี่ยวกับการบูรณาการ:[เอกสารประกอบ](https://tutorials.groupdocs.com/viewer/net/).

## นำเข้าเนมสเปซ

ก่อนดำเนินการขั้นตอนการเรนเดอร์ สิ่งสำคัญคือต้องนำเข้าเนมสเปซที่จำเป็นลงในโค้ด C# ของคุณ เนมสเปซเหล่านี้ให้การเข้าถึงคลาสและวิธีการที่จำเป็นสำหรับการแสดงภาพ WMZ และ WMF

```csharp
using GroupDocs.Viewer.Options;
using System;
using System.IO;
```

ตอนนี้เราได้ครอบคลุมข้อกำหนดเบื้องต้นและนำเข้าเนมสเปซที่จำเป็นแล้ว เรามาแจกแจงกระบวนการแสดงผลออกเป็นหลายขั้นตอนกัน

## ขั้นตอนที่ 1: เรนเดอร์รูปภาพ WMZ เป็น HTML

หากต้องการแสดงรูปภาพ WMZ เป็นรูปแบบ HTML ให้ทำตามขั้นตอนเหล่านี้:

```csharp
string outputDirectory = "Your Document Directory";
string pageFilePathFormat = Path.Combine(outputDirectory, "wmz_result.html");

// เป็น HTML
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_WMZ))
{
    HtmlViewOptions options = HtmlViewOptions.ForEmbeddedResources(pageFilePathFormat);

    viewer.View(options);
}
```

## ขั้นตอนที่ 2: เรนเดอร์รูปภาพ WMZ เป็น JPG

หากต้องการเรนเดอร์รูปภาพ WMZ เป็นรูปแบบ JPG ให้ดำเนินการดังนี้:

```csharp
pageFilePathFormat = Path.Combine(outputDirectory, "wmz_result.jpg");

using (Viewer viewer = new Viewer(TestFiles.SAMPLE_WMZ))
{
    JpgViewOptions options = new JpgViewOptions(pageFilePathFormat);
    
    viewer.View(options);
}
```

## ขั้นตอนที่ 3: เรนเดอร์รูปภาพ WMZ เป็น PNG

หากต้องการแสดงรูปภาพ WMZ เป็นรูปแบบ PNG ให้ทำตามคำแนะนำเหล่านี้:

```csharp
pageFilePathFormat = Path.Combine(outputDirectory, "wmz_result.png");

using (Viewer viewer = new Viewer(TestFiles.SAMPLE_WMZ))
{
    PngViewOptions options = new PngViewOptions(pageFilePathFormat);
   
    viewer.View(options);
}
```

## ขั้นตอนที่ 4: เรนเดอร์รูปภาพ WMZ เป็น PDF

หากต้องการเรนเดอร์รูปภาพ WMZ เป็นรูปแบบ PDF ให้ดำเนินการดังต่อไปนี้:

```csharp
pageFilePathFormat = Path.Combine(outputDirectory, "wmz_result.pdf");

using (Viewer viewer = new Viewer(TestFiles.SAMPLE_WMZ))
{
    PdfViewOptions options = new PdfViewOptions(pageFilePathFormat);
   
    viewer.View(options);
}
```

## บทสรุป

โดยสรุป GroupDocs.Viewer สำหรับ .NET นำเสนอโซลูชันที่ครอบคลุมสำหรับการแสดงภาพ WMZ และ WMF ภายในแอปพลิเคชัน .NET ได้อย่างง่ายดาย ด้วยการทำตามขั้นตอนที่ระบุไว้ในบทช่วยสอนนี้ คุณสามารถรวมฟังก์ชันการเรนเดอร์เข้ากับโปรเจ็กต์ของคุณได้อย่างราบรื่น ช่วยเพิ่มความสามารถในการประมวลผลเอกสาร

## คำถามที่พบบ่อย

### คำถามที่ 1: GroupDocs.Viewer สำหรับ .NET เข้ากันได้กับกรอบงาน .NET ทั้งหมดหรือไม่

คำตอบ 1: GroupDocs.Viewer สำหรับ .NET เข้ากันได้กับ .NET Frameworks ที่หลากหลาย รวมถึง .NET Core และ .NET Framework

### คำถามที่ 2: ฉันสามารถปรับแต่งตัวเลือกการเรนเดอร์สำหรับรูปภาพ WMZ และ WMF ได้หรือไม่

ตอบ 2: ใช่ GroupDocs.Viewer สำหรับ .NET มีตัวเลือกการปรับแต่งที่หลากหลายสำหรับการเรนเดอร์รูปภาพ ซึ่งช่วยให้คุณปรับแต่งเอาต์พุตได้ตามความต้องการของคุณ

### คำถามที่ 3: GroupDocs.Viewer สำหรับ .NET มีการสนับสนุนด้านเทคนิคหรือไม่

 A3: ได้ คุณสามารถเข้าถึงการสนับสนุนทางเทคนิคสำหรับ GroupDocs.Viewer สำหรับ .NET ผ่านทางระบบเฉพาะได้[ฟอรั่มการสนับสนุน](https://forum.groupdocs.com/c/viewer/9).

### คำถามที่ 4: GroupDocs.Viewer for .NET รองรับการดูเอกสารบนอุปกรณ์เคลื่อนที่หรือไม่

ตอบ 4: ใช่ GroupDocs.Viewer สำหรับ .NET นำเสนอความสามารถในการดูเอกสารแบบตอบสนอง เพื่อให้มั่นใจถึงประสิทธิภาพสูงสุดบนอุปกรณ์ต่างๆ รวมถึงโทรศัพท์มือถือและแท็บเล็ต

### คำถามที่ 5: ฉันสามารถลองใช้ GroupDocs.Viewer สำหรับ .NET ก่อนซื้อได้หรือไม่

 A5: ได้ คุณสามารถสำรวจคุณลักษณะต่างๆ ของ GroupDocs.Viewer สำหรับ .NET ได้โดยการเข้าถึงรุ่นทดลองใช้ฟรีที่มีให้[ที่นี่](https://releases.groupdocs.com/).