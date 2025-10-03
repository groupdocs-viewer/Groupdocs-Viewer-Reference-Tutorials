---
"date": "2025-04-25"
"description": "เรียนรู้วิธีการแปลงไฟล์ Microsoft Visio เป็นรูปแบบต่างๆ ได้อย่างง่ายดายโดยใช้ GroupDocs.Viewer สำหรับ .NET ปรับปรุงการเข้าถึงเอกสารสำหรับการผสานรวมบนเว็บ"
"title": "วิธีการเรนเดอร์เอกสาร Visio เป็น HTML, JPG, PNG และ PDF ใน .NET โดยใช้ GroupDocs.Viewer"
"url": "/th/net/rendering-basics/groupdocs-viewer-dotnet-render-visio-documents-html-jpg-png-pdf/"
"weight": 1
type: docs
---
# วิธีการเรนเดอร์เอกสาร Visio ในรูปแบบ HTML, JPG, PNG และ PDF โดยใช้ GroupDocs.Viewer ใน .NET

## การแนะนำ

คุณกำลังมองหาเครื่องมืออเนกประสงค์ในการแปลงไดอะแกรม Microsoft Visio เป็นรูปแบบเช่น HTML, JPG, PNG หรือ PDF หรือไม่ บทช่วยสอนนี้จะแนะนำคุณเกี่ยวกับการใช้ **GroupDocs.Viewer สำหรับ .NET**ไลบรารีอันทรงพลังที่ออกแบบมาเพื่อปรับปรุงกระบวนการแปลงเอกสาร เมื่ออ่านบทความนี้จบ คุณจะทราบวิธีการแปลงไฟล์ Visio เป็นรูปแบบต่างๆ อย่างมีประสิทธิภาพ ช่วยเพิ่มการเข้าถึงและการใช้งาน

**สิ่งที่คุณจะได้เรียนรู้:**
- วิธีตั้งค่า GroupDocs.Viewer ในสภาพแวดล้อม .NET
- คำแนะนำทีละขั้นตอนสำหรับการเรนเดอร์ไดอะแกรมในรูปแบบ HTML, JPG, PNG และ PDF
- ตัวเลือกการกำหนดค่าที่สำคัญสำหรับผลลัพธ์ที่เหมาะสมที่สุด
- การประยุกต์ใช้งานจริงและความเป็นไปได้ในการบูรณาการ

มาเริ่มต้นด้วยการครอบคลุมข้อกำหนดเบื้องต้นกันก่อน

## ข้อกำหนดเบื้องต้น

ก่อนที่จะใช้งาน GroupDocs.Viewer สำหรับ .NET ให้แน่ใจว่าคุณมี:

### ไลบรารี เวอร์ชัน และการอ้างอิงที่จำเป็น
- **GroupDocs.Viewer สำหรับ .NET**:แนะนำเวอร์ชัน 25.3.0 ขึ้นไป
- สภาพแวดล้อมการพัฒนา .NET ที่เข้ากันได้ (เช่น Visual Studio)

### ข้อกำหนดการตั้งค่าสภาพแวดล้อม
- ระบบของคุณควรสนับสนุน .NET Framework หรือ .NET Core/5+

### ข้อกำหนดเบื้องต้นของความรู้
- ความเข้าใจพื้นฐานเกี่ยวกับโครงสร้างโครงการ C# และ .NET

## การตั้งค่า GroupDocs.Viewer สำหรับ .NET

ในการเริ่มต้น ให้ติดตั้ง **โปรแกรมดูเอกสารกลุ่ม** ไลบรารีที่ใช้คอนโซลตัวจัดการแพ็กเกจ NuGet หรือ .NET CLI:

**คอนโซลตัวจัดการแพ็กเกจ NuGet**
```shell
Install-Package GroupDocs.Viewer -Version 25.3.0
```

**.NET CLI**
```bash
dotnet add package GroupDocs.Viewer --version 25.3.0
```

### ขั้นตอนการรับใบอนุญาต
- **ทดลองใช้งานฟรี**:เริ่มต้นด้วยการทดลองใช้ฟรีเพื่อสำรวจคุณสมบัติต่างๆ
- **ใบอนุญาตชั่วคราว**: การขอใบอนุญาตชั่วคราวเพื่อการทดสอบขยายเวลา
- **ซื้อ**:พิจารณาซื้อหากคุณต้องการใช้งานในระยะยาว

### การเริ่มต้นและการตั้งค่าเบื้องต้น

เริ่มต้น GroupDocs.Viewer โดยตรวจสอบให้แน่ใจว่าโครงการของคุณอ้างอิงไลบรารีอย่างถูกต้อง:

```csharp
using GroupDocs.Viewer;
// เริ่มต้นวัตถุของตัวดูด้วยเส้นทางเอกสารของคุณ
using (Viewer viewer = new Viewer("path/to/your/document.vsd"))
{
    // กำหนดค่าตัวเลือกตามต้องการ
}
```

## คู่มือการใช้งาน

เราจะครอบคลุมการเรนเดอร์เอกสาร Visio เป็นรูปแบบต่างๆ ทีละขั้นตอน

### การเรนเดอร์เอกสาร Visio เป็น HTML

**ภาพรวม**:การแปลงไดอะแกรมเป็น HTML ช่วยให้ฝังลงในหน้าเว็บได้ง่าย เพิ่มการเข้าถึงและการโต้ตอบ

#### ขั้นตอนที่ 1: ตั้งค่าตัวเลือกมุมมอง HTML

การกำหนดค่า `HtmlViewOptions` สำหรับทรัพยากรที่ฝังตัว:

```csharp
string outputDirectory = Path.Combine("YOUR_OUTPUT_DIRECTORY");
string pageFilePathFormat = Path.Combine(outputDirectory, "result_page.html");

using (Viewer viewer = new Viewer(Path.Combine("YOUR_DOCUMENT_DIRECTORY", "SAMPLE_VISIO.vsd")))
{
    HtmlViewOptions options = HtmlViewOptions.ForEmbeddedResources(pageFilePathFormat);
    options.VisioRenderingOptions.RenderFiguresOnly = true;
    options.VisioRenderingOptions.FigureWidth = 250; // กำหนดค่าความกว้างของรูป
    viewer.View(options); // เรนเดอร์และบันทึกเป็น HTML
}
```

**การกำหนดค่าคีย์**- 
- `RenderFiguresOnly`:แสดงเฉพาะตัวเลขเท่านั้น
- `FigureWidth`: กำหนดความกว้างของแต่ละรูปเป็นพิกเซล

### การเรนเดอร์เอกสาร Visio เป็น JPG

**ภาพรวม**:การแปลงไดอะแกรมเป็นภาพ JPEG มีประโยชน์สำหรับการแชร์ข้ามแพลตฟอร์มโดยไม่ต้องใช้ซอฟต์แวร์เฉพาะ

#### ขั้นตอนที่ 2: กำหนดค่า JpgViewOptions

ตั้งค่าตัวเลือกที่เหมาะสมกับการแสดงภาพเป็นรูปภาพ:

```csharp
string outputDirectory = Path.Combine("YOUR_OUTPUT_DIRECTORY");
string pageFilePathFormat = Path.Combine(outputDirectory, "visio_result.jpg");

using (Viewer viewer = new Viewer(Path.Combine("YOUR_DOCUMENT_DIRECTORY", "SAMPLE_VISIO.vsd")))
{
    JpgViewOptions options = new JpgViewOptions(pageFilePathFormat);
    options.VisioRenderingOptions.RenderFiguresOnly = true;
    options.VisioRenderingOptions.FigureWidth = 250; // ปรับความกว้างของรูป
    viewer.View(options); // เรนเดอร์และบันทึกเป็น JPG
}
```

**เคล็ดลับการแก้ไขปัญหา**: หากภาพที่ออกมาไม่ชัดเจน ให้ตรวจสอบว่า `FigureWidth` ตรงตามขนาดการแสดงผลที่คุณต้องการ

### การเรนเดอร์เอกสาร Visio เป็น PNG

**ภาพรวม**:รูปแบบ PNG ให้ภาพคุณภาพสูงด้วยการบีบอัดแบบไม่สูญเสียข้อมูล เหมาะสำหรับแผนผังโดยละเอียด

#### ขั้นตอนที่ 3: กำหนด PNGViewOptions

กำหนดค่าตัวเลือกเฉพาะสำหรับการเรนเดอร์เป็น PNG:

```csharp
string outputDirectory = Path.Combine("YOUR_OUTPUT_DIRECTORY");
string pageFilePathFormat = Path.Combine(outputDirectory, "visio_result.png");

using (Viewer viewer = new Viewer(Path.Combine("YOUR_DOCUMENT_DIRECTORY", "SAMPLE_VISIO.vsd")))
{
    PngViewOptions options = new PngViewOptions(pageFilePathFormat);
    options.VisioRenderingOptions.RenderFiguresOnly = true;
    options.VisioRenderingOptions.FigureWidth = 250; // ตั้งค่าความกว้างของรูป
    viewer.View(options); // เรนเดอร์และบันทึกเป็น PNG
}
```

### การเรนเดอร์เอกสาร Visio เป็น PDF

**ภาพรวม**การแปลงไดอะแกรมเป็นรูปแบบ PDF เหมาะอย่างยิ่งสำหรับการเผยแพร่และการเก็บถาวร ช่วยให้ดูเอกสารได้แบบสากล

#### ขั้นตอนที่ 4: ตั้งค่า PdfViewOptions

กำหนดค่าตัวเลือกสำหรับการเรนเดอร์รูปภาพในรูปแบบ PDF:

```csharp
string outputDirectory = Path.Combine("YOUR_OUTPUT_DIRECTORY");
string pageFilePathFormat = Path.Combine(outputDirectory, "visio_result.pdf");

using (Viewer viewer = new Viewer(Path.Combine("YOUR_DOCUMENT_DIRECTORY", "SAMPLE_VISIO.vsd")))
{
    PdfViewOptions options = new PdfViewOptions(pageFilePathFormat);
    options.VisioRenderingOptions.RenderFiguresOnly = true;
    options.VisioRenderingOptions.FigureWidth = 250; // กำหนดความกว้างของรูปร่าง
    viewer.View(options); // เรนเดอร์และบันทึกเป็น PDF
}
```

## การประยุกต์ใช้งานจริง

GroupDocs.Viewer สามารถปรับปรุงการจัดการเอกสารในระบบต่างๆ ได้:
1. **เว็บพอร์ทัล**:ฝังรูปภาพ HTML ที่แสดงผลโดยตรงลงในหน้าเว็บสำหรับเนื้อหาแบบไดนามิก
2. **ระบบจัดการเอกสาร (DMS)**:ใช้รูปแบบ JPG, PNG หรือ PDF เพื่อการแบ่งปันและจัดเก็บได้อย่างง่ายดายภายในแพลตฟอร์ม DMS
3. **เครื่องมือการรายงานทางธุรกิจ**:สร้างรายงานที่มีแผนภาพฝังตัวในรูปแบบต่างๆ เพื่อให้เหมาะกับความต้องการในการนำเสนอ

## การพิจารณาประสิทธิภาพ

การเพิ่มประสิทธิภาพการทำงานเมื่อใช้ GroupDocs.Viewer เป็นสิ่งสำคัญ:
- **การใช้ทรัพยากร**:ตรวจสอบการใช้หน่วยความจำระหว่างการเรนเดอร์เพื่อหลีกเลี่ยงปัญหาคอขวด
- **แนวทางปฏิบัติที่ดีที่สุด**:ใช้การดำเนินการแบบอะซิงโครนัสเมื่อทำได้เพื่อปรับปรุงการตอบสนอง
- **การจัดการหน่วยความจำ**:กำจัดวัตถุของผู้ชมทันทีหลังใช้งานเพื่อปลดปล่อยทรัพยากร

## บทสรุป

ในบทช่วยสอนนี้ คุณจะได้เรียนรู้วิธีใช้ GroupDocs.Viewer สำหรับ .NET เพื่อแสดงเอกสาร Visio เป็นรูปแบบ HTML, JPG, PNG และ PDF ด้วยทักษะเหล่านี้ คุณสามารถปรับปรุงการเข้าถึงเอกสารและผสานรวมความสามารถในการแสดงผลที่หลากหลายเข้ากับแอปพลิเคชันของคุณได้

**ขั้นตอนต่อไป**:สำรวจคุณสมบัติเพิ่มเติมของ GroupDocs.Viewer โดยตรวจสอบ [เอกสารอ้างอิง API](https://reference.groupdocs.com/viewer/net/) หรือลองใช้ตัวเลือกการเรนเดอร์ที่แตกต่างกันเพื่อให้เหมาะกับความต้องการเฉพาะของคุณ

## ส่วนคำถามที่พบบ่อย

1. **ฉันสามารถเรนเดอร์เอกสาร Visio โดยไม่ต้องมีใบอนุญาตได้หรือไม่**
   - ใช่ คุณสามารถใช้ GroupDocs.Viewer โดยมีสิทธิ์ใช้งานทดลองใช้งานฟรีเพื่อสำรวจฟีเจอร์ต่างๆ ในขั้นต้นได้
2. **GroupDocs.Viewer รองรับรูปแบบไฟล์ใดบ้าง นอกจาก Visio?**
   - รองรับรูปแบบต่างๆ มากมาย เช่น PDF, Word, Excel และอื่นๆ
3. **สามารถปรับขนาดเอาต์พุตสำหรับรูปที่เรนเดอร์ได้หรือไม่**
   - แน่นอน! ปรับแต่ง `FigureWidth` ในตัวเลือกการเรนเดอร์เพื่อควบคุมมิติเอาต์พุต
4. **ฉันจะจัดการเอกสารขนาดใหญ่ด้วย GroupDocs.Viewer ได้อย่างไร**
   - เพิ่มประสิทธิภาพการทำงานด้วยการกำหนดค่าการตั้งค่าการใช้หน่วยความจำและใช้กระบวนการอะซิงโครนัสเมื่อเหมาะสม