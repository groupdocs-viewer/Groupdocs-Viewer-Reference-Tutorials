---
"date": "2025-04-25"
"description": "เรียนรู้วิธีแยกข้อมูลเมตาของเอกสารและปรับแต่งไดเรกทอรีเอาต์พุตโดยใช้ GroupDocs.Viewer สำหรับ .NET ปรับปรุงระบบการจัดการเอกสารของคุณวันนี้"
"title": "แยกข้อมูลเอกสารและปรับแต่งผลลัพธ์ด้วย GroupDocs.Viewer .NET คู่มือฉบับสมบูรณ์"
"url": "/th/net/custom-rendering/groupdocs-viewer-net-extract-info-customize-output/"
"weight": 1
---

# แยกข้อมูลเอกสารและปรับแต่งผลลัพธ์ด้วย GroupDocs.Viewer .NET
## บทช่วยสอนการเรนเดอร์แบบกำหนดเอง
### สิ่งที่คุณจะได้เรียนรู้:
- วิธีการดึงข้อมูลพื้นฐานจากเอกสารโดยใช้ GroupDocs.Viewer
- ขั้นตอนการปรับแต่งไดเรกทอรีเอาท์พุตเมื่อเรนเดอร์เอกสาร
- แนวทางปฏิบัติที่ดีที่สุดและเคล็ดลับการแก้ไขปัญหา

**การแนะนำ:**
ในยุคดิจิทัลทุกวันนี้ การจัดการเอกสารอย่างมีประสิทธิภาพถือเป็นสิ่งสำคัญในสภาพแวดล้อมทางธุรกิจทุกประเภท ไม่ว่าคุณจะเป็นนักพัฒนาที่สร้างระบบการจัดการเอกสารหรือผู้เชี่ยวชาญด้านไอทีที่ต้องปรับปรุงเวิร์กโฟลว์ การจัดการ PDF และรูปแบบไฟล์อื่นๆ อาจเป็นเรื่องท้าทาย GroupDocs.Viewer สำหรับ .NET ช่วยลดความซับซ้อนของกระบวนการนี้โดยมอบฟังก์ชันการทำงานที่แข็งแกร่งเพื่อดู จัดการ และดึงข้อมูลจากเอกสารได้อย่างราบรื่น ในบทช่วยสอนนี้ เราจะมาสำรวจวิธีใช้ประโยชน์จาก GroupDocs.Viewer เพื่อค้นหาข้อมูลเอกสารพื้นฐานและปรับแต่งไดเร็กทอรีเอาต์พุตสำหรับมุมมองที่แสดงผล

![แยกข้อมูลเอกสารและปรับแต่งผลลัพธ์ด้วย GroupDocs.Viewer สำหรับ .NET](/viewer/custom-rendering/extract-document-info-customize-output-img.png)

**ข้อกำหนดเบื้องต้น:**
หากต้องการทำตามบทช่วยสอนนี้ คุณจะต้องมี:
- **GroupDocs.Viewer สำหรับ .NET**:ไลบรารีนี้จำเป็นสำหรับการเข้าถึงความสามารถในการดูเอกสาร โปรดใช้เวอร์ชัน 25.3.0 ขึ้นไป
- สภาพแวดล้อมการพัฒนาที่ตั้งค่าสำหรับแอปพลิเคชัน .NET (เช่น Visual Studio)
- ความรู้พื้นฐานเกี่ยวกับ C# และความคุ้นเคยกับการจัดการเส้นทางไฟล์ในโค้ด
- ความเข้าใจเกี่ยวกับแนวคิดการเขียนโปรแกรมเชิงวัตถุใน C#
- ประสบการณ์การทำงานเกี่ยวกับการดำเนินการ I/O ไฟล์ใน .NET

**การตั้งค่า GroupDocs.Viewer สำหรับ .NET:**
ติดตั้ง GroupDocs.Viewer ผ่านตัวจัดการแพ็กเกจ NuGet หรือ .NET CLI:

**คอนโซลตัวจัดการแพ็กเกจ NuGet:**
```shell
Install-Package GroupDocs.Viewer -Version 25.3.0
```

**.NET CLI:**
```bash
dotnet add package GroupDocs.Viewer --version 25.3.0
```

### การได้มาซึ่งใบอนุญาต:
- **ทดลองใช้งานฟรี**:เริ่มต้นด้วยการทดลองใช้ฟรีเพื่อสำรวจฟังก์ชันพื้นฐาน
- **ใบอนุญาตชั่วคราว**:สำหรับการทดสอบแบบขยายเวลา ควรพิจารณาขอรับใบอนุญาตชั่วคราวจาก [เว็บไซต์ GroupDocs](https://purchase-groupdocs.com/temporary-license/).
- **ซื้อ**:หากต้องการใช้การผลิตเต็มรูปแบบ กรุณาซื้อการสมัครสมาชิก

### การเริ่มต้นและการตั้งค่าเบื้องต้น:
นี่คือวิธีเริ่มต้น GroupDocs.Viewer ในโครงการ C# ของคุณ:
```csharp
using System;
using GroupDocs.Viewer;

namespace DocumentViewerApp
{
class Program
{
    static void Main(string[] args)
    {
        string filePath = @"C:\Path\To\Your\Document.pdf";
        
        using (Viewer viewer = new Viewer(filePath))
        {
            // โค้ดของคุณในการโต้ตอบกับเอกสารอยู่ที่นี่
        }
    }
}
```

**คู่มือการใช้งาน:**
### คุณสมบัติ 1: การรับข้อมูลพื้นฐานเกี่ยวกับเอกสาร
#### ภาพรวม:
การดึงข้อมูลที่จำเป็นเกี่ยวกับเอกสารถือเป็นสิ่งสำคัญในการทำความเข้าใจโครงสร้างของเอกสารก่อนดำเนินการ GroupDocs.Viewer ช่วยให้คุณสามารถดึงข้อมูลเมตา เช่น จำนวนหน้าและประเภทไฟล์

**การดำเนินการทีละขั้นตอน:**
##### ขั้นตอนที่ 1: เริ่มต้นโปรแกรมดูด้วยเอกสารของคุณ
ระบุเส้นทางไปยังเอกสารของคุณโดยแทนที่ `'YOUR_DOCUMENT_DIRECTORY'` พร้อมไดเร็กทอรีจริงที่คุณเก็บไฟล์ไว้:
```csharp
string filePath = @"YOUR_DOCUMENT_DIRECTORY\SamplePDF.pdf";
```
##### ขั้นตอนที่ 2: ดึงข้อมูลมุมมองสำหรับการเรนเดอร์ HTML
สร้างอินสแตนซ์ของ `ViewInfoOptions` ออกแบบมาโดยเฉพาะสำหรับการเรนเดอร์ในรูปแบบ HTML เพื่อเข้าถึงข้อมูลการดูเอกสารอย่างมีประสิทธิภาพ:
```csharp
using (Viewer viewer = new Viewer(filePath))
{
    ViewInfoOptions options = ViewInfoOptions.ForHtmlView();
    ViewInfo info = viewer.GetViewInfo(options);
    
    // ส่งออกข้อมูลพื้นฐานของเอกสาร เช่น จำนวนหน้า
    Console.WriteLine($"Document type: {info.FileType}");
    Console.WriteLine($"Page count: {info.Pages.Count}");
}
```
**คำอธิบาย:** 
- `ForHtmlView()` กำหนดค่าตัวเลือกในการดึงข้อมูลรายละเอียดมุมมองที่เหมาะสำหรับการแสดงผล HTML
- `GetViewInfo(options)` ดึงข้อมูลเมตาเกี่ยวกับเอกสาร

##### เคล็ดลับการแก้ไขปัญหา:
- ตรวจสอบให้แน่ใจว่าเส้นทางไฟล์ของคุณถูกระบุอย่างถูกต้องและแอปพลิเคชันสามารถเข้าถึงได้
- ตรวจสอบว่ารูปแบบเอกสารได้รับการสนับสนุนโดย GroupDocs.Viewer หากพบข้อผิดพลาดด้วย `GetViewInfo`-

### คุณลักษณะที่ 2: การปรับแต่งไดเรกทอรีผลลัพธ์สำหรับมุมมองเอกสาร
#### ภาพรวม:
ไดเร็กทอรีเอาต์พุตแบบกำหนดเองมีความจำเป็นเมื่อต้องเรนเดอร์เอกสารเป็นรูปแบบต่างๆ คุณสมบัตินี้ช่วยให้คุณระบุตำแหน่งจัดเก็บไฟล์ที่เรนเดอร์ได้ ทำให้ควบคุมการจัดระเบียบระบบไฟล์ได้ดีขึ้น

**การดำเนินการทีละขั้นตอน:**
##### ขั้นตอนที่ 1: กำหนดเส้นทางอินพุตและเอาต์พุต
ตั้งค่าตัวแปรสำหรับทั้งเส้นทางอินพุต (เอกสารต้นฉบับ) และเส้นทางเอาท์พุต:
```csharp
string filePath = @"YOUR_DOCUMENT_DIRECTORY\SamplePDF.pdf";
string outputPath = @"@YOUR_OUTPUT_DIRECTORY";
```
##### ขั้นตอนที่ 2: เริ่มต้นโปรแกรมดูและกำหนดค่าตัวเลือกมุมมอง HTML
การกำหนดค่า `HtmlViewOptions` เพื่อระบุว่าควรบันทึกไฟล์ HTML ที่แสดงผลไว้ที่ไหนโดยใช้ `{page}.html` เป็นตัวแทนสำหรับการตั้งชื่อแบบไดนามิก:
```csharp
using (Viewer viewer = new Viewer(filePath))
{
    HtmlViewOptions options = HtmlViewOptions.ForEmbeddedResources(outputPath + "\{page}.html");
    viewer.View(options);
}
```
**คำอธิบาย:** 
- `ForEmbeddedResources()` ช่วยให้แน่ใจว่าทรัพยากรต่างๆ เช่น รูปภาพ จะถูกฝังไว้ใน HTML ช่วยให้การปรับใช้เป็นเรื่องง่าย
- เส้นทางที่ระบุใน `outputPath` เป็นสิ่งสำคัญสำหรับการจัดระเบียบไฟล์เอาต์พุตของคุณอย่างมีประสิทธิภาพ

##### เคล็ดลับการแก้ไขปัญหา:
- ตรวจสอบสิทธิ์บนไดเร็กทอรีเอาต์พุตเพื่อให้แน่ใจว่าสามารถเขียนไฟล์ที่นั่นได้
- ตรวจสอบรูปแบบสตริงที่ใช้ในการตั้งชื่อหน้า (เช่น `{page}.html`) เพื่อป้องกันข้อผิดพลาดในระหว่างการรันไทม์

**การประยุกต์ใช้งานจริง:**
GroupDocs.Viewer นำเสนอแอปพลิเคชันที่ใช้งานจริงที่หลากหลาย:
1. **ระบบจัดการเอกสาร**:ดึงข้อมูลเมตาและแสดงเอกสารโดยอัตโนมัติสำหรับการเข้าถึงบนเว็บ
2. **ลายเซ็นดิจิทัล**:ใช้ข้อมูลที่แยกออกมาเพื่อจัดการเอกสารที่ลงนามอย่างมีประสิทธิภาพ
3. **เครือข่ายการจัดส่งเนื้อหา (CDN)**:ปรับแต่งไดเร็กทอรีเอาท์พุตเพื่อกระจายเนื้อหาไปยังเซิร์ฟเวอร์ทั่วโลก
4. **แพลตฟอร์ม CRM แบบบูรณาการ**:ปรับปรุงการบริหารจัดการความสัมพันธ์กับลูกค้าด้วยการฝังมุมมองเอกสารลงในแดชบอร์ดของลูกค้าโดยตรง
5. **พอร์ทัลการศึกษา**:จัดให้มีการเข้าถึงเนื้อหาหลักสูตรได้อย่างง่ายดายแก่ผู้เรียนผ่านการเรนเดอร์ที่ปรับแต่งได้

**ข้อควรพิจารณาด้านประสิทธิภาพ:**
การเพิ่มประสิทธิภาพการทำงานเมื่อใช้ GroupDocs.Viewer ถือเป็นสิ่งสำคัญ โดยเฉพาะอย่างยิ่งสำหรับแอปพลิเคชันขนาดใหญ่:
- **การจัดการทรัพยากร**: ปิดฝาไว้เสมอ `Viewer` อินสแตนซ์หลังการใช้งานเพื่อปลดปล่อยทรัพยากรหน่วยความจำ
- **การประมวลผลแบบแบตช์**:ประมวลผลเอกสารเป็นชุดหากต้องจัดการกับไฟล์หลายไฟล์พร้อมกันเพื่อลดเวลาในการโหลด
- **กลยุทธ์การแคช**:นำกลไกการแคชมาใช้กับมุมมองเอกสารที่เข้าถึงบ่อยครั้งเพื่อปรับปรุงประสิทธิภาพ

**บทสรุป:**
เราได้ศึกษาวิธีการดึงข้อมูลพื้นฐานจากเอกสารและปรับแต่งไดเรกทอรีเอาต์พุตโดยใช้ GroupDocs.Viewer สำหรับ .NET โดยทำตามขั้นตอนเหล่านี้ คุณสามารถปรับปรุงความสามารถในการจัดการเอกสาร ปรับปรุงเวิร์กโฟลว์ และมอบประสบการณ์ผู้ใช้ที่ดีขึ้น

**ขั้นตอนต่อไป:**
- ทดลองใช้ฟีเจอร์เพิ่มเติมของ GroupDocs.Viewer
- สำรวจความเป็นไปได้ในการบูรณาการกับกรอบงานอื่นเพื่อขยายการทำงาน

**ส่วนคำถามที่พบบ่อย:**
1. **GroupDocs.Viewer รองรับรูปแบบไฟล์อะไรบ้าง?**
   - รองรับเอกสารประเภทต่างๆ มากมาย รวมถึง PDF, เอกสาร Word, สเปรดชีต Excel และอื่นๆ อีกมากมาย