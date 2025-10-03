---
"date": "2025-04-25"
"description": "เรียนรู้วิธีการแปลงไฟล์ CHM เป็นรูปแบบ HTML, JPEG, PNG และ PDF ได้อย่างง่ายดายโดยใช้ GroupDocs.Viewer .NET เพิ่มการเข้าถึงและการกระจายไฟล์ในโครงการของคุณ"
"title": "แปลง CHM เป็น HTML, JPG, PNG, PDF โดยใช้ GroupDocs.Viewer .NET คู่มือฉบับสมบูรณ์"
"url": "/th/net/export-conversion/convert-chm-to-html-jpg-png-pdf-groupdocs-viewer-net/"
"weight": 1
type: docs
---
# แปลงไฟล์ CHM เป็น HTML, JPG, PNG และ PDF โดยใช้ GroupDocs.Viewer .NET

## การแนะนำ

คุณกำลังประสบปัญหาในการดูหรือแชร์เนื้อหาจากไฟล์ CHM เนื่องจากความเข้ากันได้ที่จำกัดหรือไม่ การแปลงไฟล์เหล่านี้เป็นรูปแบบที่เข้าถึงได้ง่ายขึ้น เช่น HTML, JPEG, PNG หรือ PDF สามารถแก้ไขปัญหานี้ได้โดยทำให้สามารถเผยแพร่ข้อมูลได้อย่างง่ายดาย ในคู่มือฉบับสมบูรณ์นี้ เราจะแสดงวิธีใช้ **โปรแกรมดู GroupDocs.NET** เพื่อแปลงไฟล์ CHM เป็นรูปแบบยอดนิยมต่างๆ ได้อย่างง่ายดาย คุณจะได้เรียนรู้วิธีการจัดการการเรนเดอร์ไฟล์ด้วยความแม่นยำและมีประสิทธิภาพ

![แปลง CHM เป็น HTML, JPG, PNG, PDF ด้วย GroupDocs.Viewer สำหรับ .NET](/viewer/export-conversion/convert-chm-html-jpg-png-pdf.png)

### สิ่งที่คุณจะได้เรียนรู้
- แปลงไฟล์ CHM เป็น HTML เพื่อให้เข้ากันได้กับเว็บ
- เรนเดอร์เนื้อหา CHM เป็นภาพ JPEG เพื่อการแบ่งปันภาพ
- แปลงหน้า CHM เป็นรูปแบบ PNG เพื่อกราฟิกคุณภาพสูง
- ส่งออกเอกสาร CHM ทั้งหมดไปยัง PDF เพื่อให้เป็นรูปแบบที่อ่านได้สากล

เมื่ออ่านคู่มือนี้จบ คุณจะเข้าใจเทคนิคการแปลงเหล่านี้เป็นอย่างดี และพร้อมที่จะนำไปใช้ในโครงการของคุณ เริ่มต้นด้วยการตั้งค่าสภาพแวดล้อมของเรา!

## ข้อกำหนดเบื้องต้น

ก่อนที่เราจะเริ่มต้น โปรดตรวจสอบให้แน่ใจว่าคุณได้ตั้งค่าทุกอย่างถูกต้องแล้ว:

- **โปรแกรมดู GroupDocs.NET** เวอร์ชัน 25.3.0 ขึ้นไป
- สภาพแวดล้อมการพัฒนา AC# เช่นเดียวกับ Visual Studio
- ความเข้าใจพื้นฐานเกี่ยวกับการจัดการไฟล์และการจัดการไดเร็กทอรีใน C#

### ข้อกำหนดการตั้งค่าสภาพแวดล้อม
ในการทำงานกับ GroupDocs.Viewer ให้ติดตั้งไลบรารีโดยใช้คอนโซลตัวจัดการแพ็กเกจ NuGet หรือ .NET CLI:

**คอนโซลตัวจัดการแพ็กเกจ NuGet**
```bash
Install-Package GroupDocs.Viewer -Version 25.3.0
```

**\.NET CLI**
```bash
dotnet add package GroupDocs.Viewer --version 25.3.0
```

### ขั้นตอนการรับใบอนุญาต

GroupDocs เสนอบริการทดลองใช้งานฟรี และคุณยังสามารถรับใบอนุญาตชั่วคราวเพื่อวัตถุประสงค์ในการทดสอบก่อนซื้อได้ เยี่ยมชม [หน้าการซื้อ](https://purchase.groupdocs.com/buy) เพื่อสำรวจตัวเลือกการออกใบอนุญาต

## การตั้งค่า GroupDocs.Viewer สำหรับ .NET

หากต้องการเริ่มใช้ GroupDocs.Viewer โปรดตรวจสอบให้แน่ใจว่าได้ติดตั้งไว้ในโปรเจ็กต์ของคุณตามที่ได้กล่าวไว้ข้างต้น นี่คือวิธีตั้งค่าสภาพแวดล้อมพื้นฐาน:

1. **เริ่มต้นการใช้งาน Viewer**โหลดไฟล์ CHM ของคุณลงในโปรแกรมดู
2. **กำหนดค่าไดเรกทอรีเอาท์พุต**ตั้งค่าว่าจะบันทึกไฟล์ที่แปลงแล้วไว้ที่ไหน

นี่คือตัวอย่างโค้ดเพื่อเริ่มต้น GroupDocs.Viewer สำหรับการแปลงไฟล์ CHM:
```csharp
using GroupDocs.Viewer;
using System.IO;

string chmFilePath = Path.Combine("YOUR_DOCUMENT_DIRECTORY", "Sample.chm");
using (Viewer viewer = new Viewer(chmFilePath))
{
    // การกำหนดค่าและการแปลงเพิ่มเติมจะอยู่ที่นี่
}
```

## คู่มือการใช้งาน

### การเรนเดอร์ CHM เป็น HTML

การแปลงไฟล์ CHM เป็นรูปแบบ HTML ช่วยให้สามารถดูในเว็บเบราว์เซอร์ใดก็ได้ เพิ่มการเข้าถึง

#### ขั้นตอนที่ 1: ตั้งค่าไดเรกทอรีเอาต์พุต
สร้างไดเร็กทอรีสำหรับไฟล์ HTML เอาท์พุตของคุณ:
```csharp
string outputDirectory = Path.Combine("YOUR_OUTPUT_DIRECTORY", "HTML");
Directory.CreateDirectory(outputDirectory);
```

#### ขั้นตอนที่ 2: กำหนดค่าตัวเลือกผู้ชม
ใช้ `HtmlViewOptions` เพื่อกำหนดว่าเนื้อหา CHM จะถูกแสดงอย่างไร:
```csharp
string pageFilePathFormat = Path.Combine(outputDirectory, "chm_result_{0}.html");

using (Viewer viewer = new Viewer(chmFilePath))
{
    HtmlViewOptions options = HtmlViewOptions.ForEmbeddedResources(pageFilePathFormat);
    options.RenderToSinglePage = true; // ตัวเลือก: เรนเดอร์หน้าทั้งหมดลงในหน้า HTML เดียว
    viewer.View(options); 
}
```

### การเรนเดอร์ CHM เป็น JPG

หากต้องการแชร์เนื้อหาเฉพาะทางภาพ การแปลงไฟล์ CHM เป็นภาพ JPEG อาจมีประโยชน์มาก

#### ขั้นตอนที่ 1: ตั้งค่าไดเรกทอรีเอาต์พุตสำหรับรูปภาพ
```csharp
string outputDirectory = Path.Combine("YOUR_OUTPUT_DIRECTORY", "JPG");
Directory.CreateDirectory(outputDirectory);
```

#### ขั้นตอนที่ 2: กำหนดค่าตัวเลือกการดูสำหรับ JPG
เรนเดอร์หน้าเฉพาะเป็น JPEG:
```csharp
string pageFilePathFormat = Path.Combine(outputDirectory, "chm_result_{0}.jpg");

using (Viewer viewer = new Viewer(chmFilePath))
{
    JpgViewOptions options = new JpgViewOptions(pageFilePathFormat);
    viewer.View(options, 1, 2, 3); // แปลงเฉพาะสามหน้าแรกเป็นรูปแบบ JPEG
}
```

### การเรนเดอร์ CHM เป็น PNG

เพื่อรักษากราฟิกคุณภาพสูงในระหว่างการแปลง ให้เรนเดอร์ไฟล์ CHM ของคุณเป็นภาพ PNG

#### ขั้นตอนที่ 1: ตั้งค่าไดเรกทอรีเอาต์พุตสำหรับไฟล์ PNG
```csharp
string outputDirectory = Path.Combine("YOUR_OUTPUT_DIRECTORY", "PNG");
Directory.CreateDirectory(outputDirectory);
```

#### ขั้นตอนที่ 2: กำหนดค่าตัวเลือกการดูสำหรับ PNG
แปลงหน้าเฉพาะเป็นรูปแบบ PNG:
```csharp
string pageFilePathFormat = Path.Combine(outputDirectory, "chm_result_{0}.png");

using (Viewer viewer = new Viewer(chmFilePath))
{
    PngViewOptions options = new PngViewOptions(pageFilePathFormat);
    viewer.View(options, 1, 2, 3); // แปลงสามหน้าแรกเป็นรูปแบบ PNG
}
```

### การเรนเดอร์ CHM เป็น PDF

การแปลงไฟล์ CHM เป็นเอกสาร PDF ช่วยให้สามารถอ่านได้บนอุปกรณ์ทุกประเภท

#### ขั้นตอนที่ 1: ตั้งค่าไดเรกทอรีเอาต์พุตสำหรับไฟล์ PDF
```csharp
string outputDirectory = Path.Combine("YOUR_OUTPUT_DIRECTORY", "PDF");
Directory.CreateDirectory(outputDirectory);
```

#### ขั้นตอนที่ 2: กำหนดค่าตัวเลือกการดูสำหรับการแปลง PDF
เรนเดอร์ไฟล์ CHM ทั้งหมดเป็น PDF:
```csharp
string pageFilePathFormat = Path.Combine(outputDirectory, "chm_result.pdf");

using (Viewer viewer = new Viewer(chmFilePath))
{
    PdfViewOptions options = new PdfViewOptions(pageFilePathFormat);
    viewer.View(options); // แปลงหน้าทั้งหมดเป็นรูปแบบ PDF
}
```

## การประยุกต์ใช้งานจริง

- **การแบ่งปันเอกสาร**:แปลงไฟล์ CHM ให้เป็น HTML สำหรับเอกสารออนไลน์
- **วัตถุประสงค์ด้านการเก็บถาวร**:จัดเก็บเนื้อหาเป็นภาพ JPEG หรือ PNG เพื่อการจัดเก็บที่ง่ายดาย
- **การสร้างรายงาน**:ส่งออกคู่มือทางเทคนิคเป็น PDF เพื่อการรายงานอย่างเป็นทางการ

การบูรณาการกับระบบ .NET อื่นๆ จะช่วยเพิ่มประสิทธิภาพการทำงาน เช่น การประมวลผลไฟล์แบบแบตช์อัตโนมัติ ทำให้กระบวนการแปลงนี้ราบรื่นในเวิร์กโฟลว์ของธุรกิจ

## การพิจารณาประสิทธิภาพ

การเพิ่มประสิทธิภาพการทำงานเมื่อใช้ GroupDocs.Viewer ให้ทำดังนี้:
- รับรองการจัดการหน่วยความจำที่มีประสิทธิภาพโดยการกำจัดวัตถุอย่างถูกต้อง
- จำกัดจำนวนหน้าที่ถูกแปลงในครั้งเดียวเพื่อป้องกันการใช้ทรัพยากรจนหมด
- ใช้ทรัพยากรที่ฝังไว้สำหรับการแปลง HTML เพื่อลดการพึ่งพาภายนอก

การยึดมั่นตามหลักปฏิบัติที่ดีที่สุดเหล่านี้จะช่วยให้การแปลงไฟล์เป็นไปอย่างราบรื่นและมีประสิทธิภาพ

## บทสรุป

ตอนนี้คุณเข้าใจอย่างถ่องแท้แล้วว่าจะต้องแปลงไฟล์ CHM เป็นรูปแบบต่างๆ โดยใช้ GroupDocs.Viewer .NET อย่างไร ไม่ว่าจะเป็นการแสดงผลเนื้อหาเป็น HTML ที่เป็นมิตรต่อเว็บ รูปแบบภาพเช่น JPEG หรือ PNG หรือ PDF ที่เข้าถึงได้ทั่วไป เครื่องมือนี้มอบความคล่องตัวสำหรับความต้องการในการจัดการเอกสารของคุณ ลองพิจารณาดูคุณสมบัติเพิ่มเติมของ API และผสานรวมเข้ากับโปรเจ็กต์ขนาดใหญ่

## ส่วนคำถามที่พบบ่อย

**คำถามที่ 1: GroupDocs.Viewer รองรับ .NET เวอร์ชันใดบ้าง**
A1: GroupDocs.Viewer รองรับ .NET framework ต่างๆ รวมถึง .NET Framework 4.6.1 และรุ่นใหม่กว่า รวมทั้ง .NET Core 2.0+

**คำถามที่ 2: ฉันจะจัดการไฟล์ CHM ขนาดใหญ่ได้อย่างมีประสิทธิภาพได้อย่างไร**
A2: แบ่งกระบวนการแปลงออกเป็นชุดย่อยๆ เพื่อจัดการการใช้หน่วยความจำได้อย่างมีประสิทธิภาพ

**คำถามที่ 3: GroupDocs.Viewer สามารถแปลงรูปแบบเอกสารอื่นได้หรือไม่**
A3: ใช่ รองรับรูปแบบต่างๆ มากมาย รวมถึง PDF, Word, Excel และอื่นๆ

**คำถามที่ 4: ข้อกำหนดของระบบสำหรับการใช้ GroupDocs.Viewer มีอะไรบ้าง**
A4: จำเป็นต้องมีสภาพแวดล้อมบน Windows ที่รองรับ .NET ตรวจสอบให้แน่ใจว่าการตั้งค่าการพัฒนาของคุณตรงตามเกณฑ์เหล่านี้

**คำถามที่ 5: ฉันจะแก้ไขข้อผิดพลาดระหว่างการแปลงได้อย่างไร**
A5: ตรวจสอบสิทธิ์ของไฟล์ ตรวจสอบว่าเส้นทางได้รับการตั้งค่าอย่างถูกต้อง และดูเอกสารหรือฟอรัมสนับสนุนหากปัญหายังคงมีอยู่

## ทรัพยากร
- [เอกสารประกอบ](https://docs.groupdocs.com/viewer/net/)
- [เอกสารอ้างอิง API](https://reference.groupdocs.com/viewer/net/)
- [ดาวน์โหลด GroupDocs.Viewer สำหรับ .NET](https://releases.groupdocs.com/viewer/net/)
- [ซื้อ GroupDocs.Viewer](https://purchase.groupdocs.com/buy)
- [ฟอรัมสนับสนุน GroupDocs](https://forum.groupdocs.com/c/viewer)