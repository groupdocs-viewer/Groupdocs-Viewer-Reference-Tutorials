---
"description": "เรียนรู้วิธีการแสดงโฟลเดอร์เฉพาะและกรองข้อความใน Outlook โดยใช้ GroupDocs.Viewer สำหรับ .NET ทำให้การจัดการเอกสารในแอปพลิเคชัน .NET ง่ายขึ้น"
"linktitle": "เรนเดอร์โฟลเดอร์เฉพาะและกรองข้อความ (Outlook)"
"second_title": "API ของ GroupDocs.Viewer .NET"
"title": "เรนเดอร์โฟลเดอร์เฉพาะและกรองข้อความ (Outlook)"
"url": "/th/net/rendering-outlook-data-files/render-specific-folders-and-filter-messages-outlook/"
"weight": 11
---

# เรนเดอร์โฟลเดอร์เฉพาะและกรองข้อความ (Outlook)

## การแนะนำ
ในโลกของการพัฒนา .NET การจัดการและแสดงเอกสารอย่างมีประสิทธิภาพถือเป็นสิ่งสำคัญ GroupDocs.Viewer สำหรับ .NET ทำให้ภารกิจนี้ง่ายขึ้นโดยมอบฟังก์ชันอันทรงพลังสำหรับการแสดงรูปแบบเอกสารต่างๆ ได้อย่างราบรื่น ในบทช่วยสอนนี้ เราจะเจาะลึกถึงวิธีการแสดงโฟลเดอร์เฉพาะและกรองข้อความใน Outlook โดยใช้ GroupDocs.Viewer สำหรับ .NET
## ข้อกำหนดเบื้องต้น
ก่อนจะเริ่มบทช่วยสอนนี้ ให้แน่ใจว่าคุณมีสิ่งต่อไปนี้:
1. GroupDocs.Viewer สำหรับ .NET: ตรวจสอบให้แน่ใจว่าคุณได้ติดตั้ง GroupDocs.Viewer สำหรับ .NET แล้ว คุณสามารถดาวน์โหลดได้จาก [เว็บไซต์](https://releases-groupdocs.com/viewer/net/).
2. .NET Framework: คุณต้องติดตั้ง .NET framework ไว้ในเครื่องของคุณ
3. ความเข้าใจพื้นฐานเกี่ยวกับ C#: ความคุ้นเคยกับภาษาการเขียนโปรแกรม C# จะเป็นประโยชน์ในการติดตามบทช่วยสอน

## นำเข้าเนมสเปซ
ก่อนอื่นให้เรานำเข้าเนมสเปซที่จำเป็นสู่โค้ด C# ของเรา:
```csharp
using System;
using System.IO;
using GroupDocs.Viewer.Options;
```

## ขั้นตอนที่ 1: กำหนดไดเรกทอรีผลลัพธ์
```csharp
string outputDirectory = "Your Document Directory";
```
แทนที่ `"Your Document Directory"` โดยมีเส้นทางไดเร็กทอรีที่คุณต้องการบันทึกเอกสารที่แสดงผล
## ขั้นตอนที่ 2: กำหนดรูปแบบเส้นทางไฟล์เพจ
```csharp
string pageFilePathFormat = Path.Combine(outputDirectory, "page_{0}.html");
```
บรรทัดนี้จะกำหนดรูปแบบสำหรับเส้นทางไฟล์ของแต่ละหน้าที่แสดงผล ในตัวอย่างนี้ จะสร้างไฟล์ HTML ที่มีชื่อว่า `page_1.html`- `page_2.html`และอื่นๆอีกมากมาย
## ขั้นตอนที่ 3: เริ่มต้น Viewer Object
```csharp
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_OST_SUBFOLDERS))
```
ที่นี่เราจะเริ่มต้น `Viewer` วัตถุที่มีเส้นทางไปยังโฟลเดอร์ตัวอย่าง Outlook
## ขั้นตอนที่ 4: กำหนดตัวเลือกมุมมอง HTML
```csharp
HtmlViewOptions options = HtmlViewOptions.ForEmbeddedResources(pageFilePathFormat);
options.OutlookOptions.Folder = "Входящие";
```
เราสร้างอินสแตนซ์ของ `HtmlViewOptions` และระบุรูปแบบสำหรับทรัพยากรที่ฝังไว้ นอกจากนี้ เรายังตั้งค่าโฟลเดอร์ Outlook ให้แสดงผลเป็น `"Входящие"` (ขาเข้า)
## ขั้นตอนที่ 5: เรนเดอร์เอกสาร
```csharp
viewer.View(options);
```
บรรทัดนี้จะทริกเกอร์กระบวนการเรนเดอร์ด้วยตัวเลือกที่ระบุ
## ขั้นตอนที่ 6: แสดงข้อความแสดงว่าสำเร็จ
```csharp
Console.WriteLine($"\nSource document rendered successfully.\nCheck output in {outputDirectory}.");
```
หลังจากการเรนเดอร์แล้ว ข้อความนี้จะปรากฏขึ้นเพื่อแจ้งว่ากระบวนการเรนเดอร์เสร็จสมบูรณ์ และจะเชื่อมต่อผู้ใช้ไปยังไดเร็กทอรีเอาต์พุต

## บทสรุป
ในบทช่วยสอนนี้ เราจะอธิบายวิธีการแสดงโฟลเดอร์เฉพาะและกรองข้อความใน Outlook โดยใช้ GroupDocs.Viewer สำหรับ .NET โดยทำตามขั้นตอนที่ระบุไว้ข้างต้น คุณจะสามารถจัดการและแสดงเอกสารภายในแอปพลิเคชัน .NET ได้อย่างมีประสิทธิภาพ
## คำถามที่พบบ่อย
### ฉันสามารถแสดงเอกสารอื่นนอกเหนือจากข้อความ Outlook ด้วย GroupDocs.Viewer สำหรับ .NET ได้หรือไม่
ใช่ GroupDocs.Viewer สำหรับ .NET รองรับรูปแบบเอกสารต่างๆ มากมาย เช่น PDF, DOCX, XLSX และอื่นๆ อีกมากมาย
### GroupDocs.Viewer สำหรับ .NET เข้ากันได้กับ .NET Core ได้หรือไม่
ใช่ GroupDocs.Viewer สำหรับ .NET เข้ากันได้กับทั้ง .NET Framework และ .NET Core
### ฉันสามารถปรับแต่งรูปแบบเอาท์พุตการเรนเดอร์ได้หรือไม่
แน่นอนว่า GroupDocs.Viewer สำหรับ .NET มีตัวเลือกต่าง ๆ เพื่อปรับแต่งผลลัพธ์การเรนเดอร์ รวมถึงรูปแบบ HTML, รูปภาพ และ PDF
### มีเวอร์ชันทดลองใช้สำหรับ GroupDocs.Viewer สำหรับ .NET หรือไม่
ใช่ คุณสามารถดาวน์โหลดรุ่นทดลองใช้งานฟรีได้จาก [เว็บไซต์](https://releases-groupdocs.com/).
### ฉันสามารถขอความช่วยเหลือหรือการสนับสนุนสำหรับ GroupDocs.Viewer สำหรับ .NET ได้จากที่ไหน
คุณสามารถเยี่ยมชม [ฟอรั่ม GroupDocs.Viewer](https://forum.groupdocs.com/c/viewer/9) สำหรับความช่วยเหลือหรือข้อสงสัยใด ๆ