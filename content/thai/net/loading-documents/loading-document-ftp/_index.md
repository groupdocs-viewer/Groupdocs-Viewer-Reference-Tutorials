---
"description": "รวม GroupDocs.Viewer สำหรับ .NET เข้ากับแอปพลิเคชันของคุณอย่างราบรื่นเพื่อการดูเอกสารที่มีประสิทธิภาพ เรนเดอร์เอกสารจาก FTP ได้อย่างง่ายดาย"
"linktitle": "โหลดเอกสารจาก FTP (ขั้นสูง)"
"second_title": "API ของ GroupDocs.Viewer .NET"
"title": "โหลดเอกสารจาก FTP (ขั้นสูง)"
"url": "/th/net/loading-documents/loading-document-ftp/"
"weight": 13
---

# โหลดเอกสารจาก FTP (ขั้นสูง)

## การแนะนำ
GroupDocs.Viewer สำหรับ .NET เป็น API ที่มีประสิทธิภาพที่ช่วยให้นักพัฒนาสามารถผสานรวมความสามารถในการดูเอกสารเข้ากับแอปพลิเคชัน .NET ได้อย่างราบรื่น ไม่ว่าคุณจะทำงานกับ PDF เอกสาร Microsoft Office หรือรูปแบบไฟล์ยอดนิยมอื่น ๆ GroupDocs.Viewer ช่วยลดความยุ่งยากของกระบวนการแสดงผลเอกสารเพื่อแสดงผล ทำให้การมอบประสบการณ์การดูเอกสารที่สมบูรณ์แบบให้กับผู้ใช้เป็นเรื่องง่ายกว่าที่เคย

![โหลดเอกสารจาก FTP ด้วย GroupDocs.Viewer .NET](/viewer/loading-documents/load-documents-from-ftp.png)

## ข้อกำหนดเบื้องต้น
ก่อนที่คุณจะเริ่มทำงานกับ GroupDocs.Viewer สำหรับ .NET ตรวจสอบให้แน่ใจว่าคุณมีข้อกำหนดเบื้องต้นต่อไปนี้:
1. สภาพแวดล้อมการพัฒนา: ตั้งค่าสภาพแวดล้อมการพัฒนาด้วย Visual Studio และติดตั้ง .NET Framework
2. การติดตั้ง GroupDocs.Viewer: ดาวน์โหลดและติดตั้ง GroupDocs.Viewer สำหรับ .NET จาก [เว็บไซต์](https://releases-groupdocs.com/viewer/net/).
3. ใบอนุญาต: รับใบอนุญาตที่ถูกต้องสำหรับ GroupDocs.Viewer คุณสามารถซื้อใบอนุญาตจาก [เว็บไซต์ GroupDocs](https://purchase.groupdocs.com/buy) หรือใช้ใบอนุญาตชั่วคราวเพื่อวัตถุประสงค์ในการทดสอบ ([ใบอนุญาตชั่วคราว](https://purchase.groupdocs.com/temporary-license/)-
4. ความเข้าใจพื้นฐานของ .NET: ทำความคุ้นเคยกับหลักพื้นฐานของการพัฒนา .NET รวมถึงรูปแบบ C# และการทำงานกับสตรีม

## นำเข้าเนมสเปซ
หากต้องการเริ่มใช้ GroupDocs.Viewer สำหรับ .NET ในแอปพลิเคชันของคุณ โปรดนำเข้าเนมสเปซที่จำเป็น:
```csharp
using System;
using System.IO;
using System.Net;
using GroupDocs.Viewer.Options;
```
#ตอนนี้ เรามาแบ่งตัวอย่างที่ให้ไว้ออกเป็นหลายขั้นตอน:
## ขั้นตอนที่ 1: กำหนดไดเรกทอรีผลลัพธ์
```csharp
string outputDirectory = "Your Document Directory";
```
ตั้งค่าไดเร็กทอรีเอาท์พุตที่คุณต้องการบันทึกหน้า HTML ที่เรนเดอร์
## ขั้นตอนที่ 2: กำหนดรูปแบบเส้นทางไฟล์เพจ
```csharp
string pageFilePathFormat = Path.Combine(outputDirectory, "page_{0}.html");
```
ระบุรูปแบบการตั้งชื่อหน้า HTML ที่จะถูกสร้างขึ้น
## ขั้นตอนที่ 3: ตั้งค่าเส้นทางไฟล์เอกสาร
```csharp
string filePath = ""; // เช่น ftp://localhost/sample.doc
```
ระบุเส้นทางไปยังไฟล์เอกสารที่คุณต้องการโหลด ซึ่งอาจเป็นเส้นทางไฟล์ในเครื่องหรือ URL
## ขั้นตอนที่ 4: ตรวจสอบเส้นทางไฟล์
```csharp
if (string.IsNullOrEmpty(filePath))
{
    Console.WriteLine("\n[LoadDocumentFromFtp] Please make sure to set a proper path to the file.");
    return;
}
```
ตรวจสอบให้แน่ใจว่าเส้นทางไฟล์ไม่ว่างเปล่าหรือเป็นค่าว่าง
## ขั้นตอนที่ 5: โหลดเอกสารจาก FTP
```csharp
Stream stream = GetFileFromFtp(filePath);
```
ดึงข้อมูลไฟล์เอกสารจากเซิร์ฟเวอร์ FTP
## ขั้นตอนที่ 6: เรนเดอร์เอกสาร
```csharp
using (Viewer viewer = new Viewer(stream))
{
    HtmlViewOptions options = HtmlViewOptions.ForEmbeddedResources(pageFilePathFormat);
    viewer.View(options);
}
```
สร้างอินสแตนซ์ตัวดูใหม่และเรนเดอร์เอกสารโดยใช้ตัวเลือกมุมมอง HTML
## ขั้นตอนที่ 7: แสดงข้อความแสดงว่าสำเร็จ
```csharp
Console.WriteLine($"\nSource document rendered successfully.\nCheck output in {outputDirectory}.");
```
แจ้งให้ผู้ใช้ทราบว่าเอกสารได้รับการแสดงสำเร็จแล้ว และระบุไดเรกทอรีเอาต์พุต

## บทสรุป
โดยสรุป GroupDocs.Viewer สำหรับ .NET มอบโซลูชันอันแข็งแกร่งสำหรับนักพัฒนาในการผสานรวมความสามารถในการดูเอกสารเข้ากับแอปพลิเคชัน .NET ของพวกเขา ด้วยการทำตามขั้นตอนที่ระบุไว้ในบทช่วยสอนนี้ คุณสามารถโหลดเอกสารจากเซิร์ฟเวอร์ FTP และเรนเดอร์เพื่อแสดงได้อย่างรวดเร็ว ซึ่งช่วยปรับปรุงประสบการณ์การใช้งานแอปพลิเคชันของคุณ
## คำถามที่พบบ่อย
### ฉันสามารถใช้ GroupDocs.Viewer สำหรับ .NET เพื่อแสดงเอกสารจากแหล่งอื่นนอกเหนือจาก FTP ได้หรือไม่
ใช่ GroupDocs.Viewer รองรับการเรนเดอร์เอกสารจากแหล่งต่าง ๆ รวมถึงระบบไฟล์ภายในเครื่อง URL และสตรีม
### ต้องมีใบอนุญาตเพื่อใช้ GroupDocs.Viewer สำหรับ .NET หรือไม่
ใช่ คุณต้องมีใบอนุญาตที่ถูกต้องเพื่อใช้ GroupDocs.Viewer ในสภาพแวดล้อมการผลิต อย่างไรก็ตาม คุณสามารถขอรับใบอนุญาตชั่วคราวเพื่อวัตถุประสงค์ในการทดสอบได้เช่นกัน
### ฉันสามารถปรับแต่งตัวเลือกการแสดงผลสำหรับเอกสารได้หรือไม่
แน่นอน! GroupDocs.Viewer มีตัวเลือกต่างๆ มากมายสำหรับการปรับแต่งกระบวนการเรนเดอร์ รวมถึงการหมุนหน้า การใส่ลายน้ำ และอื่นๆ อีกมากมาย
### GroupDocs.Viewer รองรับรูปแบบเอกสารทั้งหมดหรือไม่
GroupDocs.Viewer รองรับรูปแบบเอกสารมากมาย รวมถึง PDF, เอกสาร Microsoft Office, รูปภาพ และอื่นๆ อีกมากมาย
### มีการสนับสนุนด้านเทคนิคสำหรับ GroupDocs.Viewer สำหรับ .NET หรือไม่
ใช่ คุณสามารถเข้าถึงการสนับสนุนด้านเทคนิคและทรัพยากรผ่านทาง [ฟอรั่ม GroupDocs](https://forum.groupdocs.com/c/viewer/9) เพื่อขอความช่วยเหลือเกี่ยวกับคำถามหรือปัญหาใดๆ ที่คุณพบ