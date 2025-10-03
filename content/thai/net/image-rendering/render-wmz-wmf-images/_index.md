---
"description": "เรนเดอร์ภาพ WMZ และ WMF ในแอปพลิเคชัน .NET ได้อย่างง่ายดายโดยใช้ GroupDocs.Viewer สำหรับ .NET ปรับปรุงความสามารถในการประมวลผลเอกสารได้อย่างง่ายดาย"
"linktitle": "เรนเดอร์ภาพ WMZ และ WMF"
"second_title": "API ของ GroupDocs.Viewer .NET"
"title": "เรนเดอร์ภาพ WMZ และ WMF"
"url": "/th/net/image-rendering/render-wmz-wmf-images/"
"weight": 18
type: docs
---
# เรนเดอร์ภาพ WMZ และ WMF

## การแนะนำ

ในแวดวงการพัฒนาซอฟต์แวร์ การจัดการและการแสดงผลเอกสารในรูปแบบต่างๆ อย่างมีประสิทธิภาพถือเป็นสิ่งสำคัญที่สุด GroupDocs.Viewer สำหรับ .NET เป็นเครื่องมืออันทรงพลังที่ช่วยให้แสดงผลเอกสารในรูปแบบต่างๆ ได้หลากหลาย ช่วยให้บูรณาการได้อย่างราบรื่นและมอบประสบการณ์การใช้งานที่ดีขึ้นแก่ผู้ใช้ในแอปพลิเคชัน .NET ความสามารถอย่างหนึ่งของเครื่องมือนี้ ได้แก่ การเรนเดอร์ภาพ WMZ และ WMF ซึ่งเป็นงานที่มักพบในสถานการณ์การประมวลผลเอกสาร

![เรนเดอร์ภาพ WMZ และ WMF ด้วย GroupDocs.Viewer สำหรับ .NET](/viewer/image-rendering/render-wmz-and-wmf-images.png)

## ข้อกำหนดเบื้องต้น

ก่อนที่จะเข้าสู่กระบวนการเรนเดอร์ภาพ WMZ และ WMF โดยใช้ GroupDocs.Viewer สำหรับ .NET มีข้อกำหนดเบื้องต้นหลายประการที่ต้องปฏิบัติตาม:

1. การติดตั้ง GroupDocs.Viewer สำหรับ .NET: เริ่มต้นด้วยการดาวน์โหลดและติดตั้ง GroupDocs.Viewer สำหรับ .NET จากที่ให้มา [ลิงค์ดาวน์โหลด](https://releases.groupdocs.com/viewer/net/). ปฏิบัติตามคำแนะนำในการติดตั้งเพื่อให้แน่ใจว่าการตั้งค่าถูกต้อง

2. การขอใบอนุญาต: หากต้องการใช้ GroupDocs.Viewer สำหรับ .NET คุณจะต้องขอใบอนุญาต คุณสามารถเลือกรับใบอนุญาตชั่วคราวจาก [หน้าใบอนุญาตชั่วคราว](https://purchase.groupdocs.com/temporary-license/) หรือซื้อใบอนุญาตเต็มรูปแบบจาก [หน้าการซื้อ](https://purchase-groupdocs.com/buy).

3. ความคุ้นเคยกับสภาพแวดล้อม .NET: ความเข้าใจพื้นฐานเกี่ยวกับกรอบงาน .NET และภาษาการเขียนโปรแกรม C# ถือเป็นสิ่งสำคัญสำหรับการนำกระบวนการเรนเดอร์ไปใช้งานอย่างมีประสิทธิผล

4. การบูรณาการเข้ากับโครงการของคุณ: ตรวจสอบให้แน่ใจว่า GroupDocs.Viewer สำหรับ .NET ได้รับการบูรณาการเข้ากับโครงการ .NET ของคุณอย่างถูกต้อง โปรดดูเอกสารประกอบสำหรับคำแนะนำโดยละเอียดเกี่ยวกับการบูรณาการ: [เอกสารประกอบ](https://tutorials-groupdocs.com/viewer/net/).

## นำเข้าเนมสเปซ

ก่อนดำเนินการเรนเดอร์ สิ่งสำคัญคือต้องนำเข้าเนมสเปซที่จำเป็นลงในโค้ด C# ของคุณ เนมสเปซเหล่านี้ช่วยให้เข้าถึงคลาสและวิธีการที่จำเป็นสำหรับการเรนเดอร์ภาพ WMZ และ WMF ได้

```csharp
using GroupDocs.Viewer.Options;
using System;
using System.IO;
```

ตอนนี้เราได้ครอบคลุมข้อกำหนดเบื้องต้นและนำเข้าเนมสเปซที่จำเป็นแล้ว มาแบ่งกระบวนการเรนเดอร์ออกเป็นหลายขั้นตอนกัน

## ขั้นตอนที่ 1: เรนเดอร์ภาพ WMZ เป็น HTML

หากต้องการเรนเดอร์ภาพ WMZ เป็นรูปแบบ HTML ให้ทำตามขั้นตอนเหล่านี้:

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

## ขั้นตอนที่ 2: เรนเดอร์ภาพ WMZ เป็น JPG

หากต้องการเรนเดอร์ภาพ WMZ เป็นรูปแบบ JPG ให้ดำเนินการดังต่อไปนี้:

```csharp
pageFilePathFormat = Path.Combine(outputDirectory, "wmz_result.jpg");

using (Viewer viewer = new Viewer(TestFiles.SAMPLE_WMZ))
{
    JpgViewOptions options = new JpgViewOptions(pageFilePathFormat);
    
    viewer.View(options);
}
```

## ขั้นตอนที่ 3: เรนเดอร์ภาพ WMZ เป็น PNG

หากต้องการเรนเดอร์ภาพ WMZ เป็นรูปแบบ PNG ให้ทำตามคำแนะนำเหล่านี้:

```csharp
pageFilePathFormat = Path.Combine(outputDirectory, "wmz_result.png");

using (Viewer viewer = new Viewer(TestFiles.SAMPLE_WMZ))
{
    PngViewOptions options = new PngViewOptions(pageFilePathFormat);
   
    viewer.View(options);
}
```

## ขั้นตอนที่ 4: เรนเดอร์ภาพ WMZ เป็น PDF

หากต้องการเรนเดอร์ภาพ WMZ เป็นรูปแบบ PDF ให้ดำเนินการดังต่อไปนี้:

```csharp
pageFilePathFormat = Path.Combine(outputDirectory, "wmz_result.pdf");

using (Viewer viewer = new Viewer(TestFiles.SAMPLE_WMZ))
{
    PdfViewOptions options = new PdfViewOptions(pageFilePathFormat);
   
    viewer.View(options);
}
```

## บทสรุป

โดยสรุป GroupDocs.Viewer สำหรับ .NET นำเสนอโซลูชันที่ครอบคลุมสำหรับการเรนเดอร์ภาพ WMZ และ WMF ได้อย่างง่ายดายภายในแอปพลิเคชัน .NET ด้วยการทำตามขั้นตอนที่ระบุไว้ในบทช่วยสอนนี้ คุณสามารถผสานรวมฟังก์ชันการเรนเดอร์เข้ากับโปรเจ็กต์ของคุณได้อย่างราบรื่น ซึ่งจะช่วยเพิ่มประสิทธิภาพในการประมวลผลเอกสาร

## คำถามที่พบบ่อย

### คำถามที่ 1: GroupDocs.Viewer สำหรับ .NET เข้ากันได้กับเฟรมเวิร์ก .NET ทั้งหมดหรือไม่

A1: GroupDocs.Viewer สำหรับ .NET เข้ากันได้กับกรอบงาน .NET มากมาย รวมถึง .NET Core และ .NET Framework

### คำถามที่ 2: ฉันสามารถปรับแต่งตัวเลือกการเรนเดอร์สำหรับภาพ WMZ และ WMF ได้หรือไม่

A2: ใช่ GroupDocs.Viewer สำหรับ .NET มีตัวเลือกการปรับแต่งมากมายสำหรับการเรนเดอร์รูปภาพ ช่วยให้คุณปรับแต่งเอาต์พุตตามความต้องการของคุณได้

### คำถามที่ 3: มีการสนับสนุนด้านเทคนิคสำหรับ GroupDocs.Viewer สำหรับ .NET หรือไม่

A3: ใช่ คุณสามารถเข้าถึงการสนับสนุนทางเทคนิคสำหรับ GroupDocs.Viewer สำหรับ .NET ผ่านทางส่วนสนับสนุนเฉพาะ [ฟอรั่มสนับสนุน](https://forum-groupdocs.com/c/viewer/9).

### คำถามที่ 4: GroupDocs.Viewer สำหรับ .NET รองรับการดูเอกสารบนอุปกรณ์เคลื่อนที่หรือไม่

A4: ใช่ GroupDocs.Viewer สำหรับ .NET นำเสนอความสามารถในการดูเอกสารแบบตอบสนอง ช่วยให้มั่นใจถึงประสิทธิภาพที่เหมาะสมที่สุดบนอุปกรณ์ต่างๆ รวมถึงโทรศัพท์มือถือและแท็บเล็ต

### คำถามที่ 5: ฉันสามารถทดลองใช้ GroupDocs.Viewer สำหรับ .NET ก่อนซื้อได้หรือไม่

A5: ใช่ คุณสามารถสำรวจคุณสมบัติของ GroupDocs.Viewer สำหรับ .NET ได้โดยเข้าถึงรุ่นทดลองใช้งานฟรีที่พร้อมให้บริการ [ที่นี่](https://releases-groupdocs.com/).