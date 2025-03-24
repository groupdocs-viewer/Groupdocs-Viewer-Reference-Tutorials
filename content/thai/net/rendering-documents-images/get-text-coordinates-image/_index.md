---
title: รับพิกัดข้อความสำหรับการแสดงภาพ
linktitle: รับพิกัดข้อความสำหรับการแสดงภาพ
second_title: GroupDocs.Viewer .NET API
description: เรียนรู้วิธีแยกพิกัดข้อความสำหรับการแสดงภาพโดยใช้ GroupDocs.Viewer สำหรับ .NET เพิ่มความสามารถในการประมวลผลเอกสารของคุณได้อย่างง่ายดาย
weight: 12
url: /th/net/rendering-documents-images/get-text-coordinates-image/
---

# รับพิกัดข้อความสำหรับการแสดงภาพ

## การแนะนำ
GroupDocs.Viewer สำหรับ .NET เป็น API การเรนเดอร์เอกสารอันทรงพลังที่ช่วยให้นักพัฒนาสามารถเรนเดอร์เอกสารในรูปแบบต่าง ๆ ได้อย่างราบรื่น เช่น PDF, Microsoft Office และอื่นๆ อีกมากมาย ฟังก์ชันหลักประการหนึ่งคือความสามารถในการแยกพิกัดข้อความเพื่อการแสดงภาพที่แม่นยำ
## ข้อกำหนดเบื้องต้น
ก่อนที่เราจะเริ่มต้น ตรวจสอบให้แน่ใจว่าคุณมีข้อกำหนดเบื้องต้นดังต่อไปนี้:
1.  GroupDocs.Viewer สำหรับ .NET: ดาวน์โหลดและติดตั้งเวอร์ชันล่าสุดจาก[ที่นี่](https://releases.groupdocs.com/viewer/net/).
2. สภาพแวดล้อมการพัฒนา: ตั้งค่า IDE ที่คุณต้องการด้วยการสนับสนุนกรอบงาน .NET
3. ไฟล์เอกสาร: เตรียมไฟล์เอกสารตัวอย่างให้พร้อมสำหรับการทดสอบ

## การนำเข้าเนมสเปซ
ก่อนที่จะเจาะลึกกระบวนการเขียนโค้ด เรามานำเข้าเนมสเปซที่จำเป็นเพื่อเข้าถึงฟังก์ชันการทำงานของ GroupDocs.Viewer สำหรับ .NET กันก่อน
```csharp
using System;
using GroupDocs.Viewer.Options;
using GroupDocs.Viewer.Results;
```
## ขั้นตอนที่ 1: เริ่มต้น GroupDocs.Viewer
เริ่มต้นด้วยการเริ่มต้นออบเจ็กต์ GroupDocs.Viewer ด้วยไฟล์เอกสารที่คุณต้องการประมวลผล
```csharp
using (Viewer viewer = new Viewer("path/to/your/document"))
{
    // รหัสของคุณอยู่ที่นี่
}
```
## ขั้นตอนที่ 2: รับข้อมูลการดู
จากนั้น รับข้อมูลมุมมองของเอกสาร รวมถึงพิกัดข้อความสำหรับการแสดงภาพ
```csharp
ViewInfoOptions options = ViewInfoOptions.ForPngView(true);
ViewInfo viewInfo = viewer.GetViewInfo(options);
```
## ขั้นตอนที่ 3: วนซ้ำผ่านหน้าต่างๆ
วนซ้ำแต่ละหน้าของเอกสารเพื่อเข้าถึงบรรทัดข้อความ คำ และอักขระ
```csharp
foreach (Page page in viewInfo.Pages)
{
    Console.WriteLine($"Page: {page.Number}");
    Console.WriteLine("Text lines/words/characters:");
    foreach (Line line in page.Lines)
    {
        Console.WriteLine(line);
        foreach (Word word in line.Words)
        {
            Console.WriteLine("\t" + word);
            foreach (Character character in word.Characters)
                Console.WriteLine("\t\t" + character);
        }
    }
}
```
## ขั้นตอนที่ 4: แยกพิกัดข้อความ
แยกพิกัดข้อความเพื่อช่วยให้การแสดงภาพมีความแม่นยำ
```csharp
// รหัสของคุณสำหรับการแยกพิกัดข้อความอยู่ที่นี่
```

## บทสรุป
โดยสรุป การเรียนรู้การแยกพิกัดข้อความสำหรับการแสดงภาพโดยใช้ GroupDocs.Viewer สำหรับ .NET จะช่วยเพิ่มความสามารถในการประมวลผลเอกสารของคุณได้อย่างมาก เมื่อทำตามบทช่วยสอนนี้ คุณได้เรียนรู้ขั้นตอนสำคัญในการบรรลุงานนี้อย่างมีประสิทธิภาพ
## คำถามที่พบบ่อย
### GroupDocs.Viewer สำหรับ .NET เข้ากันได้กับรูปแบบเอกสารทั้งหมดหรือไม่
GroupDocs.Viewer สำหรับ .NET รองรับรูปแบบเอกสารที่หลากหลาย รวมถึง PDF, Microsoft Office และอื่นๆ
### ฉันสามารถรวม GroupDocs.Viewer สำหรับ .NET เข้ากับแอปพลิเคชัน .NET ที่มีอยู่ของฉันได้หรือไม่
ใช่ GroupDocs.Viewer สำหรับ .NET ได้รับการออกแบบมาเพื่อผสานรวมเข้ากับแอปพลิเคชัน .NET ของคุณได้อย่างราบรื่น
### GroupDocs.Viewer สำหรับ .NET รองรับการแยกพิกัดข้อความหรือไม่
ใช่ ตามที่แสดงให้เห็นในบทช่วยสอนนี้ GroupDocs.Viewer สำหรับ .NET มีฟังก์ชันสำหรับแยกพิกัดข้อความ
### ฉันจะหาเอกสารและการสนับสนุนเพิ่มเติมสำหรับ GroupDocs.Viewer for .NET ได้ที่ไหน
 คุณสามารถเข้าถึงเอกสารและขอการสนับสนุนจากฟอรัม GroupDocs.Viewer[ที่นี่](https://forum.groupdocs.com/c/viewer/9).
### GroupDocs.Viewer สำหรับ .NET มีรุ่นทดลองใช้ฟรีหรือไม่
 ใช่ คุณสามารถทดลองใช้ฟรีได้จากเว็บไซต์ GroupDocs[ที่นี่](https://releases.groupdocs.com/).