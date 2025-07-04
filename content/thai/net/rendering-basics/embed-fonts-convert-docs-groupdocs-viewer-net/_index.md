---
"date": "2025-04-25"
"description": "เรียนรู้วิธีฝังแบบอักษรและแปลงเอกสารเป็น HTML โดยใช้ GroupDocs.Viewer .NET เพื่อให้แน่ใจว่าการแสดงผลมีความสอดคล้องกันในทุกแพลตฟอร์ม"
"title": "Master GroupDocs.Viewer .NET ฝังฟอนต์และแปลงเอกสารเป็น HTML อย่างมีประสิทธิภาพ"
"url": "/th/net/rendering-basics/embed-fonts-convert-docs-groupdocs-viewer-net/"
"weight": 1
---

# เรียนรู้การเรนเดอร์เอกสารด้วย GroupDocs.Viewer .NET: ฝังฟอนต์และแปลงเป็น HTML

## การแนะนำ

ในยุคดิจิทัล การเรนเดอร์เอกสารอย่างราบรื่นถือเป็นสิ่งสำคัญสำหรับธุรกิจที่ต้องการนำเสนอเนื้อหาแบบไดนามิกบนแพลตฟอร์มต่างๆ ไม่ว่าคุณจะเป็นนักพัฒนาที่ทำงานบนแอปพลิเคชันข้ามแพลตฟอร์มหรือจัดการเวิร์กโฟลว์เอกสารภายใน การรับรองการเรนเดอร์แบบอักษรที่สม่ำเสมอและการแปลงเอกสารอย่างมีประสิทธิภาพอาจเป็นเรื่องท้าทาย บทช่วยสอนนี้จะกล่าวถึงความท้าทายเหล่านี้โดยใช้ GroupDocs.Viewer .NET เพื่อตรวจจับเส้นทางแบบอักษรตามระบบปฏิบัติการ กำหนดค่าแหล่งที่มาของแบบอักษร และเรนเดอร์เอกสารเป็น HTML ด้วยทรัพยากรที่ฝังไว้

ในคู่มือนี้ คุณจะได้เรียนรู้วิธีการ:
- ตรวจจับและตั้งค่าเส้นทางแบบอักษรที่เหมาะสมสำหรับแพลตฟอร์ม OS ที่แตกต่างกัน
- กำหนดค่าแหล่งที่มาของฟอนต์โดยใช้ GroupDocs.Viewer .NET
- เรนเดอร์เอกสารเป็นรูปแบบ HTML พร้อมฝังทรัพยากรที่จำเป็นทั้งหมดไว้

เมื่อสิ้นสุดบทช่วยสอนนี้ คุณจะเข้าใจอย่างถ่องแท้เกี่ยวกับการตั้งค่าและการใช้คุณลักษณะเหล่านี้อย่างมีประสิทธิภาพในแอปพลิเคชัน .NET ของคุณ เริ่มต้นด้วยการดูข้อกำหนดเบื้องต้นที่จำเป็น

## ข้อกำหนดเบื้องต้น

ก่อนที่เราจะดำเนินการต่อ โปรดตรวจสอบให้แน่ใจว่าคุณมีสิ่งต่อไปนี้:
- **ห้องสมุดและแหล่งอ้างอิง**: GroupDocs.Viewer สำหรับ .NET เวอร์ชัน 25.3.0
- **การตั้งค่าสภาพแวดล้อม**:สภาพแวดล้อมการพัฒนาที่มีการติดตั้ง .NET (ควรใช้ .NET Core หรือใหม่กว่า)
- **ฐานความรู้**: ความเข้าใจพื้นฐานเกี่ยวกับการเขียนโปรแกรม C# และความคุ้นเคยกับการทำงานของระบบไฟล์

### การตั้งค่า GroupDocs.Viewer สำหรับ .NET

ในการเริ่มต้น คุณจะต้องติดตั้งไลบรารี GroupDocs.Viewer คุณสามารถทำได้ผ่านคอนโซลตัวจัดการแพ็กเกจ NuGet หรือใช้ .NET CLI:

**คอนโซลตัวจัดการแพ็กเกจ NuGet**
```shell
Install-Package GroupDocs.Viewer -Version 25.3.0
```

**.NET CLI**
```bash
dotnet add package GroupDocs.Viewer --version 25.3.0
```

#### การขอใบอนุญาต
- **ทดลองใช้งานฟรี**:เริ่มต้นด้วยการดาวน์โหลดรุ่นทดลองใช้งานฟรีจาก [เว็บไซต์ GroupDocs](https://releases-groupdocs.com/viewer/net/).
- **ใบอนุญาตชั่วคราว**:สมัครขอใบอนุญาตชั่วคราวเพื่อเข้าถึงฟีเจอร์เต็มรูปแบบโดยไม่มีข้อจำกัดได้ที่ [หน้าใบอนุญาตชั่วคราวของ GroupDocs](https://purchase-groupdocs.com/temporary-license/).
- **ซื้อ**:หากต้องการใช้ในระยะยาว ควรพิจารณาซื้อใบอนุญาตจาก [หน้าการซื้อ GroupDocs](https://purchase-groupdocs.com/buy).

#### การเริ่มต้นขั้นพื้นฐาน

นี่คือวิธีเริ่มต้น GroupDocs.Viewer ในแอปพลิเคชัน C# ของคุณ:

```csharp
using GroupDocs.Viewer;

// เริ่มต้นวัตถุ Viewer ด้วยเส้นทางเอกสาร
using (Viewer viewer = new Viewer("sample.docx"))
{
    // ขั้นตอนการกำหนดค่าไปที่นี่
}
```

## คู่มือการใช้งาน

ในส่วนนี้ เราจะมาเจาะลึกคุณลักษณะแต่ละอย่างทีละขั้นตอน โดยจะเน้นไปที่การตรวจจับเส้นทางแบบอักษร การกำหนดค่าแบบอักษร และการเรนเดอร์เอกสาร

### การตรวจจับเส้นทางแบบอักษรตามแพลตฟอร์มระบบปฏิบัติการ

#### ภาพรวม

ฟีเจอร์นี้จะกำหนดเส้นทางสำหรับไฟล์ฟอนต์โดยอัตโนมัติโดยอิงจากว่าคุณกำลังรันแอปพลิเคชันของคุณบน Windows หรือแพลตฟอร์มที่ไม่ใช่ Windows ซึ่งเป็นสิ่งสำคัญเพื่อให้แน่ใจว่าข้อความจะถูกแสดงอย่างถูกต้องในสภาพแวดล้อมที่แตกต่างกัน

#### การดำเนินการแบบทีละขั้นตอน

**1. ตรวจสอบระบบปฏิบัติการ**

```csharp
using System;
using System.IO;
using System.Runtime.InteropServices;

public static string GetFontsPath()
{
    // กำหนดแพลตฟอร์มระบบปฏิบัติการและตั้งค่าเส้นทางแบบอักษรให้เหมาะสม
    if (RuntimeInformation.IsOSPlatform(OSPlatform.Windows))
    {
        return Utils.FontsPath;  // เส้นทางที่ตั้งไว้ล่วงหน้าสำหรับแพลตฟอร์ม Windows
    }
    else
    {
        var assembly = System.Reflection.Assembly.GetEntryAssembly();
        var entryAssemblyDirectory = Path.GetDirectoryName(assembly.Location);
        return Path.Combine(entryAssemblyDirectory, Utils.FontsPath);  // เส้นทางที่ได้มาสำหรับผู้ที่ไม่ใช่ Windows
    }
}
```

**คำอธิบาย**: วิธีนี้ใช้ `RuntimeInformation.IsOSPlatform` เพื่อตรวจสอบว่าแอปพลิเคชันกำลังทำงานบน Windows หรือไม่ หากเป็นจริง แอปพลิเคชันจะส่งคืนเส้นทางแบบอักษรที่กำหนดไว้ล่วงหน้า (`Utils.FontsPath`) สำหรับแพลตฟอร์มอื่น ๆ จะสร้างเส้นทางโดยรวมไดเร็กทอรีการประกอบรายการกับเส้นทางแบบอักษร

### การตั้งค่าแหล่งที่มาของฟอนต์สำหรับการแสดงผลเอกสาร

#### ภาพรวม

เมื่อเรากำหนดเส้นทางฟอนต์ที่ถูกต้องแล้ว ขั้นตอนถัดไปคือการกำหนดค่าเส้นทางเหล่านี้ใน GroupDocs.Viewer เพื่อให้สามารถใช้ได้ระหว่างการแสดงผลเอกสาร

**2. กำหนดค่าเส้นทางแบบอักษร**

```csharp
using GroupDocs.Viewer.Fonts;

public static void ConfigureFontSources(string fontsPath)
{
    // ตั้งค่าโฟลเดอร์ที่มีแบบอักษรเป็นแหล่งที่มาสำหรับการเรนเดอร์
    FontSettings.SetFontSources(new FolderFontSource(fontsPath, Fonts.SearchOption.TopFolderOnly));
}
```

**คำอธิบาย**: วิธีการนี้จะสร้างอินสแตนซ์ของ `FolderFontSource` ด้วยเส้นทางแบบอักษรที่กำหนดไว้ จากนั้นจึงตั้งค่าแหล่งที่มาโดยใช้ `SetFontSources`เพื่อให้แน่ใจว่า GroupDocs.Viewer จะใช้แบบอักษรเหล่านี้เมื่อเรนเดอร์เอกสาร

### การเรนเดอร์เอกสารเป็น HTML พร้อมทรัพยากรที่ฝังไว้

#### ภาพรวม

ขั้นตอนสุดท้ายคือการแปลงเอกสารของคุณให้เป็นรูปแบบที่ใช้งานบนเว็บได้ โดยให้แน่ใจว่าทรัพยากรทั้งหมดถูกฝังไว้โดยตรงภายในไฟล์เอาต์พุตเพื่อให้สามารถแจกจ่ายและดูได้ง่ายขึ้น

**3. เรนเดอร์เป็น HTML**

```csharp
using GroupDocs.Viewer;
using GroupDocs.Viewer.Options;

public static void RenderDocumentToHtml(string documentPath, string outputDirectory)
{
    // กำหนดวิธีการจัดเก็บแต่ละหน้าของ HTML
    string pageFilePathFormat = Path.Combine(outputDirectory, "page_{0}.html");

    using (Viewer viewer = new Viewer(documentPath))
    {
        HtmlViewOptions options = HtmlViewOptions.ForEmbeddedResources(pageFilePathFormat);
        viewer.View(options);  // เรนเดอร์เอกสารด้วยทรัพยากรที่ฝังไว้
    }
}
```

**คำอธิบาย**:รหัสนี้จะเริ่มต้น `Viewer` วัตถุและตั้งค่าตัวเลือกมุมมอง HTML เพื่อรวมทรัพยากรที่จำเป็นทั้งหมด (เช่น แบบอักษร รูปภาพ) ไว้ภายในไฟล์ HTML เอาต์พุตโดยตรง `ForEmbeddedResources` วิธีการนี้รับรองว่าสิ่งเหล่านี้จะเป็นอิสระ

### เคล็ดลับการแก้ไขปัญหา
- **แบบอักษรไม่แสดงอย่างถูกต้อง?** ตรวจสอบให้แน่ใจว่าเส้นทางแบบอักษรของคุณได้รับการตั้งค่าอย่างถูกต้องสำหรับแต่ละแพลตฟอร์ม
- **ปัญหาประสิทธิภาพการทำงาน:** พิจารณาปรับขนาดไฟล์ให้เหมาะสมและลดทรัพยากรที่ฝังไว้หากเป็นไปได้
- **ข้อผิดพลาดในการแสดงผล:** ตรวจสอบเส้นทางเอกสารและให้แน่ใจว่าแอปพลิเคชันสามารถเข้าถึงได้

## การประยุกต์ใช้งานจริง
1. **การจัดการเอกสารภายใน**:ใช้การตั้งค่านี้ในการแสดงเอกสารภายในเป็นหน้าเว็บ ช่วยให้เข้าถึงได้ง่ายขึ้นในแต่ละแผนก
2. **การนำเสนอต่อลูกค้า**:แปลงข้อเสนอหรือสัญญาของลูกค้าเป็น HTML เพื่อแชร์ผ่านอีเมลหรืออินทราเน็ตได้อย่างง่ายดาย
3. **เว็บพอร์ทัล**:ฝังเอกสารโดยตรงลงในแอปพลิเคชั่นเว็บโดยไม่ต้องดาวน์โหลดเพิ่มเติม

## การพิจารณาประสิทธิภาพ
- **เพิ่มประสิทธิภาพเส้นทางแบบอักษร**:ใช้เส้นทางสัมพันธ์เพื่อลดเวลาในการโหลดและให้แน่ใจว่าสามารถเข้าถึงแบบอักษรได้อย่างถูกต้องในสภาพแวดล้อมที่แตกต่างกัน
- **การจัดการทรัพยากร**ตรวจสอบทรัพยากรที่ฝังไว้ในไฟล์ HTML ของคุณเป็นประจำเพื่อป้องกันการพองตัว ซึ่งอาจทำให้ความเร็วในการเรนเดอร์ช้าลงได้
- **การเพิ่มประสิทธิภาพหน่วยความจำ**: ใช้ประโยชน์ `using` คำชี้แจงที่มีประสิทธิภาพในการจัดการการใช้หน่วยความจำโดยกำจัดวัตถุทันทีหลังใช้งาน

## บทสรุป

ด้วยการรวม GroupDocs.Viewer สำหรับ .NET เข้ากับแอปพลิเคชันของคุณ คุณจะได้ชุดเครื่องมืออันทรงพลังสำหรับการจัดการและนำเสนอเอกสาร บทช่วยสอนนี้ช่วยให้คุณมีความรู้ในการตรวจจับเส้นทางแบบอักษรตามระบบปฏิบัติการ กำหนดค่าแหล่งที่มาของแบบอักษร และแสดงเอกสารอย่างมีประสิทธิภาพในรูปแบบ HTML พร้อมทรัพยากรที่ฝังไว้

ในขั้นตอนถัดไป ให้พิจารณาสำรวจคุณลักษณะขั้นสูงเพิ่มเติมที่นำเสนอโดย GroupDocs.Viewer หรือผสานรวมฟังก์ชันนี้เข้ากับโปรเจ็กต์ขนาดใหญ่ อย่าลังเลที่จะทดลองใช้การกำหนดค่าต่างๆ เพื่อค้นหาสิ่งที่เหมาะกับความต้องการของคุณมากที่สุด

## ส่วนคำถามที่พบบ่อย
1. **ฉันจะจัดการกับแบบอักษรที่ไม่เป็นมาตรฐานได้อย่างไร**
   - ให้แน่ใจว่ารวมอยู่ในไดเร็กทอรีแหล่งที่มาของแบบอักษรและมีการอ้างอิงอย่างถูกต้อง `Utils-FontsPath`.
2. **จะเกิดอะไรขึ้นถ้าแอปพลิเคชันของฉันทำงานบนระบบที่ใช้ Unix?**
   - โค้ดได้จัดการสิ่งนี้แล้วโดยอนุมานเส้นทางจากไดเร็กทอรีแอสเซมบลีรายการ