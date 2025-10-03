---
"date": "2025-04-25"
"description": "เรียนรู้วิธีแปลงไฟล์ TXT เป็นรูปแบบต่างๆ เช่น HTML, JPG, PNG และ PDF โดยใช้ GroupDocs.Viewer สำหรับ .NET ด้วยคู่มือที่ครอบคลุมนี้"
"title": "แปลง TXT เป็น HTML, JPG, PNG, PDF โดยใช้ GroupDocs.Viewer .NET&#58; คู่มือฉบับสมบูรณ์"
"url": "/th/net/export-conversion/groupdocs-viewer-dotnet-txt-conversion-guide/"
"weight": 1
type: docs
---
# แปลง TXT เป็นรูปแบบต่างๆ ด้วย GroupDocs.Viewer .NET

## การแนะนำ

ต้องการแปลงเอกสารข้อความเป็นรูปแบบต่างๆ เช่น HTML, JPG, PNG หรือ PDF ได้อย่างง่ายดายหรือไม่ การจัดการการแปลงเอกสารอาจเป็นเรื่องท้าทาย โดยเฉพาะเมื่อต้องจัดการกับหน้าหลายหน้าหรือข้อกำหนดรูปแบบเฉพาะ **GroupDocs.Viewer สำหรับ .NET** ทำให้กระบวนการในการเรนเดอร์ไฟล์ TXT เป็นรูปแบบเอาท์พุตที่หลากหลายง่ายขึ้น เพื่อให้แน่ใจว่าข้อมูลของคุณเข้าถึงได้และน่าดึงดูดสายตา

![แปลง TXT เป็น HTML, JPG, PNG, PDF ด้วย GroupDocs.Viewer สำหรับ .NET](/viewer/export-conversion/convert-txt-to-html-jpg-png-pdf.png)

ในคู่มือนี้ เราจะมาเรียนรู้วิธีใช้ GroupDocs.Viewer สำหรับ .NET เพื่อแปลงเอกสาร TXT ให้เป็น HTML หลายหน้า, HTML หน้าเดียว, JPG, PNG และ PDF เมื่ออ่านจบ คุณจะเชี่ยวชาญ:
- การแปลงไฟล์ TXT โดยใช้ C# กับ GroupDocs.Viewer
- การนำตัวเลือกการเรนเดอร์ที่แตกต่างกันไปใช้งานตามความต้องการของคุณ
- เพิ่มประสิทธิภาพการทำงานระหว่างการแปลง

มาเริ่มต้นแก้ไขปัญหาการแปลงเอกสารของคุณกันเลย

## ข้อกำหนดเบื้องต้น

ก่อนที่เราจะเริ่ม ให้แน่ใจว่าคุณมีสิ่งต่อไปนี้พร้อมแล้ว:
- **สภาพแวดล้อมการพัฒนา**: Visual Studio 2019 หรือใหม่กว่า.
- **กรอบงาน .NET**: เวอร์ชัน 4.6.1 ขึ้นไป.
- **GroupDocs.Viewer สำหรับไลบรารี .NET**-
  - ผ่านคอนโซลตัวจัดการแพ็กเกจ NuGet: `Install-Package GroupDocs.Viewer -Version 25.3.0`
  - การใช้ .NET CLI: `dotnet add package GroupDocs.Viewer --version 25.3.0`

ขอแนะนำให้มีความคุ้นเคยกับการเขียนโปรแกรม C# และการปฏิบัติการไฟล์พื้นฐานใน .NET เพื่อปฏิบัติตามได้อย่างง่ายดาย

## การตั้งค่า GroupDocs.Viewer สำหรับ .NET

### การติดตั้ง

ในการเริ่มต้น ให้ติดตั้ง **โปรแกรมดูเอกสารกลุ่ม** ไลบรารีที่ใช้ตัวจัดการแพ็คเกจที่คุณต้องการ:

#### คอนโซลตัวจัดการแพ็กเกจ NuGet
```bash
Install-Package GroupDocs.Viewer -Version 25.3.0
```

#### .NET CLI
```bash
dotnet add package GroupDocs.Viewer --version 25.3.0
```

### การออกใบอนุญาต

คุณสามารถเริ่มต้นด้วย **ทดลองใช้งานฟรี** หรือรับ **ใบอนุญาตชั่วคราว** เพื่อสำรวจความสามารถทั้งหมดของ GroupDocs.Viewer สำหรับ .NET โดยไม่มีข้อจำกัดในการประเมิน:
- ทดลองใช้งานฟรี: [ดาวน์โหลดที่นี่](https://releases.groupdocs.com/viewer/net/)
- ใบอนุญาตชั่วคราว: [ขอคำร้องได้ที่นี่](https://purchase.groupdocs.com/temporary-license/)

สำหรับการใช้งานอย่างต่อเนื่อง โปรดพิจารณาซื้อใบอนุญาตโดยตรงจาก [เอกสารกลุ่ม](https://purchase-groupdocs.com/buy).

### การเริ่มต้นขั้นพื้นฐาน

การตั้งค่า GroupDocs.Viewer ในโครงการของคุณ:

```csharp
using System.IO;
using GroupDocs.Viewer;

string outputDirectory = Path.Combine("YOUR_DOCUMENT_DIRECTORY", "Output");

// เริ่มต้นวัตถุ Viewer ด้วยเส้นทางไฟล์ TXT
using (Viewer viewer = new Viewer(Path.Combine("YOUR_DOCUMENT_DIRECTORY", "Sample.txt")))
{
    // โค้ดการเรนเดอร์ของคุณจะอยู่ที่นี่
}
```

## คู่มือการใช้งาน

ตอนนี้เราลองเจาะลึกฟีเจอร์แต่ละอย่างและดูว่าคุณสามารถนำไปใช้งานได้อย่างไร

### เรนเดอร์เอกสาร TXT เป็น HTML หลายหน้า

#### ภาพรวม
ฟีเจอร์นี้สาธิตการแปลงเอกสาร TXT เป็นรูปแบบ HTML หลายหน้า โดยแต่ละหน้าของไฟล์ข้อความจะแสดงเป็นไฟล์ HTML แยกต่างหากพร้อมรีซอร์สที่ฝังไว้

#### ขั้นตอนที่ 1: ตั้งค่าโปรแกรมดู

สร้าง `Viewer` วัตถุสำหรับไฟล์ TXT ต้นฉบับของคุณ:

```csharp
using System.IO;
using GroupDocs.Viewer;
using GroupDocs.Viewer.Options;

string outputDirectory = Path.Combine("YOUR_DOCUMENT_DIRECTORY", "Output");
string pageFileFullPath = Path.Combine(outputDirectory, "Txt_result.html");

// เริ่มต้นการใช้งาน Viewer ด้วยไฟล์ข้อความตัวอย่าง
using (Viewer viewer = new Viewer(Path.Combine("YOUR_DOCUMENT_DIRECTORY", "Sample.txt")))
{
    // ไปต่อขั้นตอนที่ 2...
```

#### ขั้นตอนที่ 2: กำหนดค่าตัวเลือกมุมมอง HTML

ตั้งค่า `HtmlViewOptions` เพื่อแสดงแต่ละหน้าแยกกัน:

```csharp
// ตั้งค่าตัวเลือกมุมมอง HTML สำหรับการเรนเดอร์หลายหน้า
HtmlViewOptions options = HtmlViewOptions.ForEmbeddedResources(pageFileFullPath);

// เรนเดอร์เอกสารเป็น HTML หลายหน้า
viewer.View(options);
}
```

**คำอธิบาย**: เดอะ `ForEmbeddedResources()` วิธีการนี้รับรองว่าทรัพยากรต่างๆ เช่น รูปภาพและสไตล์จะถูกฝังไว้โดยตรงภายในไฟล์ HTML ช่วยให้แชร์ได้อย่างง่ายดาย

### เรนเดอร์เอกสาร TXT เป็น HTML หน้าเดียว

#### ภาพรวม
แปลงเอกสาร TXT ให้เป็นหน้า HTML เดียว เหมาะสำหรับเอกสารที่ต้องแสดงเป็นเว็บเพจต่อเนื่องกัน

#### ขั้นตอนที่ 1: ตั้งค่าโปรแกรมดู

เริ่มต้นการใช้งาน `Viewer` วัตถุ:

```csharp
string outputDirectory = Path.Combine("YOUR_DOCUMENT_DIRECTORY", "Output");
string pageFileFullPath = Path.Combine(outputDirectory, "Txt_result_single_page.html");

// สร้างอินสแตนซ์ Viewer ใหม่สำหรับไฟล์ข้อความอื่น
using (Viewer viewer = new Viewer(Path.Combine("YOUR_DOCUMENT_DIRECTORY", "Sample2.txt")))
{
    // ไปต่อขั้นตอนที่ 2...
```

#### ขั้นตอนที่ 2: กำหนดค่าตัวเลือก HTML หน้าเดียว

การกำหนดค่า `HtmlViewOptions` โดยเปิดใช้งานการตั้งค่าหน้าเดียว:

```csharp
// ตั้งค่าตัวเลือกสำหรับการเรนเดอร์ลงในหน้า HTML เดียว
HtmlViewOptions options = HtmlViewOptions.ForEmbeddedResources(pageFileFullPath);
options.RenderToSinglePage = true;

// เรนเดอร์เป็นหน้า HTML เดียว
viewer.View(options);
}
```

**คำอธิบาย**: เดอะ `RenderToSinglePage` คุณสมบัติช่วยให้แน่ใจว่าเนื้อหาทั้งหมดจะแสดงบนหน้าเดียว

### เรนเดอร์เอกสาร TXT เป็น JPG

#### ภาพรวม
คุณสมบัตินี้ช่วยให้คุณแปลงเอกสารข้อความเป็นภาพ JPEG ซึ่งมีประโยชน์สำหรับการนำเสนอภาพหรือการเก็บถาวรข้อมูล

#### ขั้นตอนที่ 1: ตั้งค่าโปรแกรมดู

เตรียมของคุณ `Viewer` วัตถุ:

```csharp
string outputDirectory = Path.Combine("YOUR_DOCUMENT_DIRECTORY", "Output");
string pageFileFullPath = Path.Combine(outputDirectory, "Txt_result.jpg");

// เริ่มต้นการดูด้วยไฟล์ตัวอย่าง
using (Viewer viewer = new Viewer(Path.Combine("YOUR_DOCUMENT_DIRECTORY", "Sample.txt")))
{
    // ไปต่อขั้นตอนที่ 2...
```

#### ขั้นตอนที่ 2: กำหนดค่าตัวเลือกมุมมอง JPG

ตั้งค่า `JpgViewOptions` สำหรับการแสดงผลภาพ:

```csharp
// ตั้งค่าตัวเลือกสำหรับการเรนเดอร์เป็นรูปภาพ JPG
JpgViewOptions options = new JpgViewOptions(pageFileFullPath);

// เรนเดอร์เอกสารเป็นไฟล์ JPEG
viewer.View(options);
}
```

**คำอธิบาย**: เดอะ `JpgViewOptions` คลาสระบุวิธีการเรนเดอร์และบันทึกแต่ละหน้าของเอกสารของคุณในรูปแบบ JPEG

### เรนเดอร์เอกสาร TXT เป็น PNG

#### ภาพรวม
แปลงเอกสารข้อความเป็นรูปแบบ PNG ที่ให้ผลลัพธ์ภาพคุณภาพสูงพร้อมการรองรับความโปร่งใส

#### ขั้นตอนที่ 1: ตั้งค่าโปรแกรมดู

เริ่มต้นการใช้งาน `Viewer` วัตถุ:

```csharp
string outputDirectory = Path.Combine("YOUR_DOCUMENT_DIRECTORY", "Output");
string pageFileFullPath = Path.Combine(outputDirectory, "Txt_result.png");

// สร้างอินสแตนซ์ของตัวดูสำหรับไฟล์ TXT ของคุณ
using (Viewer viewer = new Viewer(Path.Combine("YOUR_DOCUMENT_DIRECTORY", "Sample.txt")))
{
    // ไปต่อขั้นตอนที่ 2...
```

#### ขั้นตอนที่ 2: กำหนดค่าตัวเลือกมุมมอง PNG

ตั้งค่า `PngViewOptions`-

```csharp
// ตั้งค่าตัวเลือกมุมมองสำหรับการเรนเดอร์เป็นรูปภาพ PNG
PngViewOptions options = new PngViewOptions(pageFileFullPath);

// เรนเดอร์เอกสารในรูปแบบ PNG
viewer.View(options);
}
```

**คำอธิบาย**: เดอะ `PngViewOptions` คลาสนี้ช่วยให้สามารถเรนเดอร์แต่ละหน้าด้วยความโปร่งใส จึงเหมาะกับกราฟิกแบบหลายชั้น

### เรนเดอร์เอกสาร TXT เป็น PDF

#### ภาพรวม
คุณสมบัตินี้เหมาะอย่างยิ่งสำหรับการแปลงเอกสารข้อความเป็นรูปแบบ PDF ที่สามารถเข้าถึงได้ทั่วโลก

#### ขั้นตอนที่ 1: ตั้งค่าโปรแกรมดู

เตรียมของคุณ `Viewer` วัตถุ:

```csharp
string outputDirectory = Path.Combine("YOUR_DOCUMENT_DIRECTORY", "Output");
string pageFileFullPath = Path.Combine(outputDirectory, "Txt_result.pdf");

// เริ่มต้นอินสแตนซ์ตัวดูสำหรับไฟล์ข้อความตัวอย่างของคุณ
using (Viewer viewer = new Viewer(Path.Combine("YOUR_DOCUMENT_DIRECTORY", "Sample.txt")))
{
    // ไปต่อขั้นตอนที่ 2...
```

#### ขั้นตอนที่ 2: กำหนดค่าตัวเลือกมุมมอง PDF

ตั้งค่า `PdfViewOptions`-

```csharp
// ตั้งค่าตัวเลือกมุมมองสำหรับการเรนเดอร์เป็นเอกสาร PDF
PdfViewOptions options = new PdfViewOptions(pageFileFullPath);

// เรนเดอร์เอกสารเป็นไฟล์ PDF
viewer.View(options);
}
```

**คำอธิบาย**: เดอะ `PdfViewOptions` คลาสระบุวิธีการแปลงและบันทึกไฟล์ TXT ของคุณเป็นเอกสาร PDF

## บทสรุป

ด้วย GroupDocs.Viewer สำหรับ .NET การแปลงเอกสารข้อความเป็นรูปแบบต่างๆ เป็นเรื่องง่าย คู่มือนี้ครอบคลุมถึงการแปลงไฟล์ TXT เป็น HTML หลายหน้า, HTML หน้าเดียว, JPG, PNG และ PDF โดยใช้ C# ไม่ว่าคุณต้องการปรับปรุงการเข้าถึงหรือความเข้ากันได้ของเอกสาร วิธีการเหล่านี้ก็มีโซลูชันที่มีประสิทธิภาพ

สำหรับความช่วยเหลือเพิ่มเติมหรือคุณสมบัติขั้นสูงเพิ่มเติม โปรดดูที่ [เอกสาร GroupDocs.Viewer อย่างเป็นทางการ](https://docs.groupdocs.com/viewer/net/). สนุกกับการเขียนโค้ด!