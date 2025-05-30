---
title: ตั้งค่ารูปแบบ DateTime และออฟเซ็ตโซนเวลา (อีเมล)
linktitle: ตั้งค่ารูปแบบ DateTime และออฟเซ็ตโซนเวลา (อีเมล)
second_title: GroupDocs.Viewer .NET API
description: ผสานรวม GroupDocs.Viewer สำหรับ .NET เข้ากับแอปพลิเคชันของคุณได้อย่างราบรื่นเพื่อความสามารถในการดูเอกสารอันทรงพลัง ปรับปรุงประสบการณ์ผู้ใช้ด้วยตัวเลือกที่ปรับแต่งได้
weight: 11
url: /th/net/rendering-email-messages/set-date-time-format-offset-email/
---

# ตั้งค่ารูปแบบ DateTime และออฟเซ็ตโซนเวลา (อีเมล)


## การแนะนำ
GroupDocs.Viewer สำหรับ .NET เป็นเครื่องมืออันทรงพลังที่ช่วยให้นักพัฒนาสามารถรวมความสามารถในการดูเอกสารเข้ากับแอปพลิเคชัน .NET ของตนได้อย่างราบรื่น ด้วย GroupDocs.Viewer คุณสามารถแสดงรูปแบบเอกสารได้หลากหลาย รวมถึง PDF, เอกสาร Microsoft Office, รูปภาพ และอื่นๆ อีกมากมายได้โดยตรงภายในแอปพลิเคชันของคุณ โดยไม่จำเป็นต้องใช้ปลั๊กอินหรือโปรแกรมดูภายนอกใดๆ ในบทช่วยสอนที่ครอบคลุมนี้ เราจะแนะนำคุณตลอดขั้นตอนการตั้งค่า GroupDocs.Viewer สำหรับ .NET สำรวจฟีเจอร์ต่างๆ และสาธิตวิธีใช้งานอย่างมีประสิทธิภาพเพื่อปรับปรุงความสามารถในการดูเอกสารของแอปพลิเคชันของคุณ
## ข้อกำหนดเบื้องต้น
ก่อนที่จะเข้าสู่บทช่วยสอนนี้ ตรวจสอบให้แน่ใจว่าคุณได้ตั้งค่าข้อกำหนดเบื้องต้นต่อไปนี้:
1. Visual Studio: ตรวจสอบให้แน่ใจว่าคุณได้ติดตั้ง Visual Studio ในระบบของคุณ GroupDocs.Viewer สำหรับ .NET เข้ากันได้กับ Visual Studio อย่างสมบูรณ์ ช่วยให้สามารถรวมเข้ากับโครงการ .NET ของคุณได้อย่างราบรื่น
2.  GroupDocs.Viewer for .NET: ดาวน์โหลดและติดตั้ง GroupDocs.Viewer for .NET จาก[ลิ้งค์ดาวน์โหลด](https://releases.groupdocs.com/viewer/net/). ปฏิบัติตามคำแนะนำในการติดตั้งที่ให้ไว้เพื่อตั้งค่าไลบรารีภายในสภาพแวดล้อมการพัฒนาของคุณ
3. .NET Framework: ตรวจสอบให้แน่ใจว่าคุณได้ติดตั้ง .NET Framework เวอร์ชันที่เหมาะสมแล้ว GroupDocs.Viewer สำหรับ .NET รองรับ .NET Framework เวอร์ชันต่างๆ รวมถึง .NET Core และ .NET Standard

## นำเข้าเนมสเปซ
เพื่อที่จะใช้ GroupDocs.Viewer สำหรับ .NET อย่างมีประสิทธิภาพ คุณจะต้องนำเข้าเนมสเปซที่จำเป็นลงในโปรเจ็กต์ของคุณ ทำตามขั้นตอนเหล่านี้เพื่อนำเข้าเนมสเปซที่จำเป็น:

```csharp
using System;
using System.IO;
using GroupDocs.Viewer.Options;
```


เรามาแบ่งตัวอย่างที่ให้ไว้ออกเป็นหลายขั้นตอนเพื่อทำความเข้าใจส่วนประกอบแต่ละส่วนและฟังก์ชันการทำงานของส่วนประกอบต่างๆ
## ขั้นตอนที่ 1: ตั้งค่า Output Directory และ File Path
```csharp
string outputDirectory = "Your Document Directory";
string filePath = Path.Combine(outputDirectory, "output.html");
```
ในขั้นตอนนี้ เรากำหนดไดเร็กทอรีเอาต์พุตที่จะบันทึกเอกสารที่แสดงผล และระบุพาธของไฟล์สำหรับไฟล์ HTML เอาท์พุต
## ขั้นตอนที่ 2: สร้างอินสแตนซ์ของวัตถุ Viewer
```csharp
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_EML))
```
 ที่นี่เราสร้างอินสแตนซ์ใหม่ของ`Viewer` คลาส โดยส่งเส้นทางของเอกสารที่จะดู (ในกรณีนี้คือไฟล์ EML ตัวอย่าง) เป็นพารามิเตอร์
## ขั้นตอนที่ 3: กำหนดตัวเลือกมุมมอง HTML
```csharp
HtmlViewOptions options = HtmlViewOptions.ForEmbeddedResources(filePath);
```
ในขั้นตอนนี้ เรากำหนดค่าตัวเลือกมุมมอง HTML สำหรับการแสดงผลเอกสาร โดยระบุเส้นทางไฟล์เอาต์พุตสำหรับเอกสาร HTML ที่แสดงผล
## ขั้นตอนที่ 4: ตั้งค่ารูปแบบ DateTime และออฟเซ็ตโซนเวลา
```csharp
options.EmailOptions.DateTimeFormat = "MM d yyyy HH:mm tt zzz";
options.EmailOptions.TimeZoneOffset = new TimeSpan(1, 0, 0);
```
ที่นี่ เราปรับแต่งรูปแบบวันที่และเวลาสำหรับข้อความอีเมล และตั้งค่าออฟเซ็ตเขตเวลาตามเขตเวลาที่ต้องการ
## ขั้นตอนที่ 5: แสดงผลเอกสาร
```csharp
viewer.View(options);
```
 ในที่สุดเราก็เรียกว่า`View` วิธีการของ`Viewer` วัตถุผ่านตัวเลือกมุมมอง HTML ที่กำหนดค่าเพื่อแสดงเอกสารเป็นรูปแบบ HTML
## ขั้นตอนที่ 6: แสดงไดเรกทอรีผลลัพธ์
```csharp
Console.WriteLine($"\nSource document rendered successfully.\nCheck output in {outputDirectory}.");
```
ขั้นตอนนี้เพียงแสดงข้อความที่บ่งชี้ว่าการเรนเดอร์เอกสารสำเร็จ และจัดเตรียมพาธไปยังไดเร็กทอรีเอาต์พุตซึ่งมีเอกสาร HTML ที่เรนเดอร์อยู่

## บทสรุป
GroupDocs.Viewer สำหรับ .NET นำเสนอโซลูชันที่มีประสิทธิภาพสำหรับการรวมความสามารถในการดูเอกสารเข้ากับแอปพลิเคชัน .NET ของคุณ ด้วยการทำตามขั้นตอนที่ระบุไว้ในบทช่วยสอนนี้ คุณสามารถตั้งค่า GroupDocs.Viewer นำเข้าเนมสเปซที่จำเป็น และใช้คุณสมบัติต่างๆ เพื่อแสดงเอกสารด้วยตัวเลือกที่ปรับแต่งได้ ไม่ว่าคุณจะทำงานกับ PDF, เอกสาร Microsoft Office หรือรูปแบบอื่นๆ GroupDocs.Viewer จะทำให้กระบวนการดูเอกสารง่ายขึ้น ช่วยเพิ่มประสบการณ์ผู้ใช้แอปพลิเคชันของคุณ
## คำถามที่พบบ่อย
### GroupDocs.Viewer เข้ากันได้กับ .NET Core หรือไม่
ใช่ GroupDocs.Viewer สำหรับ .NET รองรับ .NET Core ทำให้สามารถใช้งานร่วมกันได้ข้ามแพลตฟอร์มสำหรับแอปพลิเคชันของคุณ
### ฉันสามารถปรับแต่งลักษณะที่ปรากฏของเอกสารที่แสดงผลได้หรือไม่
อย่างแน่นอน! GroupDocs.Viewer มีตัวเลือกการปรับแต่งที่หลากหลาย รวมถึงระดับการซูม การหมุนหน้า และอื่นๆ เพื่อปรับแต่งประสบการณ์การรับชมตามความต้องการของคุณ
### มีรุ่นทดลองใช้สำหรับการทดสอบหรือไม่?
 ใช่ คุณสามารถดาวน์โหลด GroupDocs.Viewer สำหรับ .NET เวอร์ชันทดลองใช้ฟรีได้จาก[ลิงค์เว็บไซต์](https://releases.groupdocs.com/viewer/net/) เพื่อประเมินคุณสมบัติก่อนตัดสินใจซื้อ
### GroupDocs.Viewer รองรับการเรนเดอร์เอกสารที่มีการป้องกันด้วยรหัสผ่านหรือไม่
ใช่ GroupDocs.Viewer มีการรองรับในตัวสำหรับการแสดงเอกสารที่มีการป้องกันด้วยรหัสผ่าน ช่วยให้มั่นใจในการดูเอกสารภายในแอปพลิเคชันของคุณอย่างปลอดภัย
### ฉันจะรับการสนับสนุนหรือความช่วยเหลือเพิ่มเติมเกี่ยวกับ GroupDocs.Viewer ได้ที่ไหน
 หากมีข้อสงสัยหรือความช่วยเหลือทางเทคนิค คุณสามารถไปที่ GroupDocs.Viewer[ฟอรั่ม](https://forum.groupdocs.com/c/viewer/9) หรือติดต่อทีมสนับสนุนเพื่อขอความช่วยเหลือและคำแนะนำทันที