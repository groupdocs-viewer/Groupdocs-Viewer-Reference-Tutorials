---
"description": "เรียนรู้วิธีการแยกพิกัดข้อความสำหรับการเรนเดอร์ภาพโดยใช้ GroupDocs.Viewer สำหรับ .NET ปรับปรุงความสามารถในการประมวลผลเอกสารของคุณได้อย่างง่ายดาย"
"linktitle": "รับพิกัดข้อความสำหรับการเรนเดอร์ภาพ"
"second_title": "API ของ GroupDocs.Viewer .NET"
"title": "รับพิกัดข้อความสำหรับการเรนเดอร์ภาพ"
"url": "/th/net/rendering-documents-images/get-text-coordinates-image/"
"weight": 12
type: docs
---
# รับพิกัดข้อความสำหรับการเรนเดอร์ภาพ

## การแนะนำ
GroupDocs.Viewer สำหรับ .NET เป็น API การเรนเดอร์เอกสารอันทรงพลังที่ช่วยให้นักพัฒนาสามารถเรนเดอร์เอกสารในรูปแบบต่างๆ เช่น PDF, Microsoft Office และอื่นๆ ได้อย่างราบรื่น หนึ่งในฟังก์ชันหลักคือความสามารถในการแยกพิกัดข้อความเพื่อเรนเดอร์ภาพอย่างแม่นยำ
## ข้อกำหนดเบื้องต้น
ก่อนที่เราจะเริ่ม ให้แน่ใจว่าคุณมีข้อกำหนดเบื้องต้นดังต่อไปนี้:
1. GroupDocs.Viewer สำหรับ .NET: ดาวน์โหลดและติดตั้งเวอร์ชันล่าสุดจาก [ที่นี่](https://releases-groupdocs.com/viewer/net/).
2. สภาพแวดล้อมการพัฒนา: ตั้งค่า IDE ที่คุณต้องการด้วยการรองรับ .NET framework
3. ไฟล์เอกสาร: เตรียมไฟล์เอกสารตัวอย่างไว้เพื่อวัตถุประสงค์ในการทดสอบ

## การนำเข้าเนมสเปซ
ก่อนที่จะเริ่มเขียนโค้ด ให้เรานำเข้าเนมสเปซที่จำเป็นเพื่อเข้าถึงฟังก์ชันการทำงานของ GroupDocs.Viewer สำหรับ .NET กันก่อน
```csharp
using System;
using GroupDocs.Viewer.Options;
using GroupDocs.Viewer.Results;
```
## ขั้นตอนที่ 1: เริ่มต้น GroupDocs.Viewer
เริ่มต้นด้วยการเริ่มต้นวัตถุ GroupDocs.Viewer ด้วยไฟล์เอกสารที่คุณตั้งใจจะประมวลผล
```csharp
using (Viewer viewer = new Viewer("path/to/your/document"))
{
    // รหัสของคุณอยู่ที่นี่
}
```
## ขั้นตอนที่ 2: รับข้อมูลการดู
ขั้นตอนต่อไปคือการดึงข้อมูลมุมมองของเอกสาร รวมทั้งพิกัดข้อความสำหรับการแสดงภาพ
```csharp
ViewInfoOptions options = ViewInfoOptions.ForPngView(true);
ViewInfo viewInfo = viewer.GetViewInfo(options);
```
## ขั้นตอนที่ 3: ทำซ้ำในแต่ละหน้า
ทำซ้ำผ่านแต่ละหน้าของเอกสารเพื่อเข้าถึงบรรทัดข้อความ คำ และอักขระ
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
แยกพิกัดข้อความเพื่อให้แสดงภาพได้อย่างแม่นยำ
```csharp
// โค้ดของคุณสำหรับการแยกพิกัดข้อความอยู่ที่นี่
```

## บทสรุป
โดยสรุป การเรียนรู้การแยกพิกัดข้อความสำหรับการเรนเดอร์ภาพโดยใช้ GroupDocs.Viewer สำหรับ .NET สามารถเพิ่มความสามารถในการประมวลผลเอกสารของคุณได้อย่างมาก เมื่อทำตามบทช่วยสอนนี้ คุณจะได้เรียนรู้ขั้นตอนสำคัญในการทำงานนี้ให้สำเร็จอย่างมีประสิทธิภาพ
## คำถามที่พบบ่อย
### GroupDocs.Viewer สำหรับ .NET เข้ากันได้กับรูปแบบเอกสารทั้งหมดหรือไม่
GroupDocs.Viewer สำหรับ .NET รองรับรูปแบบเอกสารหลากหลาย รวมถึง PDF, Microsoft Office และอื่นๆ อีกมากมาย
### ฉันสามารถรวม GroupDocs.Viewer สำหรับ .NET เข้ากับแอปพลิเคชัน .NET ที่มีอยู่ได้หรือไม่
ใช่ GroupDocs.Viewer สำหรับ .NET ได้รับการออกแบบมาให้บูรณาการกับแอปพลิเคชัน .NET ของคุณได้อย่างราบรื่น
### GroupDocs.Viewer สำหรับ .NET รองรับการแยกพิกัดข้อความหรือไม่
ใช่ ตามที่สาธิตในบทช่วยสอนนี้ GroupDocs.Viewer สำหรับ .NET มีฟังก์ชันการทำงานสำหรับการแยกพิกัดข้อความ
### ฉันสามารถค้นหาเอกสารเพิ่มเติมและการสนับสนุนสำหรับ GroupDocs.Viewer สำหรับ .NET ได้จากที่ใด
คุณสามารถเข้าถึงเอกสารและขอความช่วยเหลือจากฟอรัม GroupDocs.Viewer ได้ [ที่นี่](https://forum-groupdocs.com/c/viewer/9).
### มี GroupDocs.Viewer สำหรับ .NET ให้ทดลองใช้งานฟรีหรือไม่
ใช่ คุณสามารถใช้ประโยชน์จากการทดลองใช้ฟรีจากเว็บไซต์ GroupDocs ได้ [ที่นี่](https://releases-groupdocs.com/).