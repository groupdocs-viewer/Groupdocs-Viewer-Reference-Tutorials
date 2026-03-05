---
date: '2026-03-05'
description: เรียนรู้วิธีบีบอัด PDF ใน Java โดยการปรับคุณภาพ JPG ด้วย GroupDocs.Viewer
  – วิธีง่ายสำหรับการบีบอัด PDF ใน Java ที่สมดุลระหว่างขนาดไฟล์และความคมชัดของภาพ
keywords:
- reduce pdf size java
- convert pptx to pdf
- compress pdf images
title: วิธีบีบอัด PDF ใน Java – ปรับคุณภาพ JPG
type: docs
url: /th/java/advanced-rendering/optimize-jpg-quality-groupdocs-viewer-java/
weight: 1
---

# วิธีบีบอัด PDF ใน Java – ปรับคุณภาพ JPG

การสมดุลระหว่างขนาดไฟล์และความคมชัดของภาพเป็นความท้าทายทั่วไปเมื่อทำงานกับ PDF ในบทเรียนนี้คุณจะได้เรียนรู้ **วิธีบีบอัด PDF** โดยการปรับคุณภาพภาพ JPG ภายในเอกสาร PDF ด้วย GroupDocs.Viewer for Java เราจะพาคุณผ่านขั้นตอนการตั้งค่า การเขียนโค้ด และเคล็ดลับปฏิบัติ เพื่อให้คุณสามารถบีบอัดภาพใน PDF ได้อย่างมั่นใจโดยไม่ทำให้การอ่านเสียหาย

![ปรับคุณภาพ JPG ใน PDF ด้วย GroupDocs.Viewer for Java](/viewer/advanced-rendering/optimize-jpg-quality-in-pdfs.png)

## คำตอบสั้น
- **“reduce PDF size Java” หมายถึงอะไร?** การปรับคุณภาพภาพ การบีบอัด และการจัดการทรัพยากรเพื่อสร้างไฟล์ PDF ที่มีขนาดเล็กลงในแอปพลิเคชัน Java  
- **การตั้งค่าใดที่ควบคุมคุณภาพ JPG?** `PdfViewOptions.setJpgQuality(byte quality)` โดยค่าจะอยู่ระหว่าง 0 (ต่ำสุด) ถึง 100 (สูงสุด)  
- **ฉันสามารถแปลง PPTX เป็น PDF ในขั้นตอนเดียวได้หรือไม่?** ได้ — เพียงชี้ `Viewer` ไปที่ไฟล์ `.pptx` แล้วใช้ตัวเลือกเดียวกัน  
- **ระดับคุณภาพที่เหมาะสำหรับการเผยแพร่บนเว็บคือเท่าไหร่?** ค่าอยู่ที่ **50‑70** ให้สมดุลที่ดีสำหรับสถานการณ์เว็บส่วนใหญ่  
- **ต้องใช้ไลเซนส์สำหรับฟีเจอร์นี้หรือไม่?** เวอร์ชันทดลองฟรีใช้ได้สำหรับการประเมินผล; ต้องมีไลเซนส์ถาวรสำหรับการใช้งานในผลิตภัณฑ์

## วิธีบีบอัด PDF ใน Java – ภาพรวม
การลดขนาด PDF ใน Java เกี่ยวข้องกับการปรับแต่งทรัพยากรภายใน PDF — โดยเฉพาะภาพ — เพื่อให้ไฟล์สุดท้ายใช้พื้นที่จัดเก็บน้อยลงและโหลดเร็วขึ้น การลดคุณภาพ JPG ทำให้คุณ **บีบอัดภาพใน PDF** ได้อย่างมีประสิทธิภาพ ซึ่งมักเป็นส่วนที่ทำให้เอกสารมีขนาดใหญ่ที่สุด

## “reduce PDF size Java” คืออะไร?
การลดขนาด PDF ใน Java เกี่ยวข้องกับการปรับแต่งทรัพยากรภายใน PDF — โดยเฉพาะภาพ — เพื่อให้ไฟล์สุดท้ายใช้พื้นที่จัดเก็บน้อยลงและโหลดเร็วขึ้น การลดคุณภาพ JPG ทำให้คุณ **บีบอัดภาพใน PDF** ได้อย่างมีประสิทธิภาพ ซึ่งมักเป็นส่วนที่ทำให้เอกสารมีขนาดใหญ่ที่สุด

## ทำไมต้องปรับคุณภาพ JPG ด้วย GroupDocs Viewer?
- **ลดขนาดอย่างมีนัยสำคัญ**: การลดคุณภาพภาพสามารถทำให้ PDF เล็กลง 30‑70 % ขึ้นอยู่กับความละเอียดต้นฉบับ  
- **การแปลงแบบครั้งเดียว**: ไม่ต้องมีขั้นตอนการประมวลผลภาพแยกต่างหาก; GroupDocs จะจัดการในระหว่างการสร้าง PDF  
- **ความยืดหยุ่น**: คุณสามารถปรับค่า `byte` ของคุณภาพตามความต้องการของโครงการ (เช่น พิมพ์คุณภาพสูง vs. ตัวอย่างเว็บที่เบา)  

## ข้อกำหนดเบื้องต้น
- **GroupDocs.Viewer for Java** เวอร์ชัน 25.2 หรือใหม่กว่า  
- โครงการ Java ที่ใช้ Maven พร้อม JDK 8 หรือใหม่กว่า  
- ความคุ้นเคยพื้นฐานกับ Java และการจัดการ PDF  

## การตั้งค่า GroupDocs.Viewer for Java
เพิ่มรีโพซิทอรีและ dependency ของ GroupDocs ลงใน `pom.xml` ของคุณ:

```xml
<repositories>
   <repository>
      <id>repository.groupdocs.com</id>
      <name>GroupDocs Repository</name>
      <url>https://releases.groupdocs.com/viewer/java/</url>
   </repository>
</repositories>

<dependencies>
   <dependency>
      <groupId>com.groupdocs</groupId>
      <artifactId>groupdocs-viewer</artifactId>
      <version>25.2</version>
   </dependency>
</dependencies>
```

> **เคล็ดลับระดับมืออาชีพ:** ควรอัปเดตเวอร์ชันให้เป็นล่าสุดเสมอเพื่อรับประโยชน์จากการปรับปรุงประสิทธิภาพและตัวเลือกการบีบอัดใหม่ ๆ

## คู่มือการใช้งาน

### ขั้นตอนที่ 1: กำหนดเส้นทางโฟลเดอร์ผลลัพธ์
สร้างคลาสช่วยเหลือที่สร้างโฟลเดอร์ผลลัพธ์สำหรับบันทึก PDF

```java
import java.nio.file.Path;
import java.nio.file.Paths;

public class FeatureResolveOutputDirectoryPath {
    public static Path getOutputDirectoryPath(String subdirectory) {
        String directory = Paths.get("YOUR_OUTPUT_DIRECTORY", "AdjustQualityOfJpgImages", subdirectory).toString();
        
        try {
            return Paths.get(directory);
        } catch (IOException e) {
            throw new RuntimeException("Failed to create output directory.", e);
        }
    }
}
```

### ขั้นตอนที่ 2: ตั้งค่า `PdfViewOptions` ด้วยคุณภาพ JPG ที่ต้องการ
กำหนดระดับคุณภาพ JPG (0‑100) ก่อนทำการเรนเดอร์เอกสาร

```java
import com.groupdocs.viewer.Viewer;
import com.groupdocs.viewer.options.PdfViewOptions;

public class FeatureAdjustQualityOfJpgImages {
    public static void run() {
        Path outputDirectory = FeatureResolveOutputDirectoryPath.getOutputDirectoryPath("YOUR_DOCUMENT_DIRECTORY");
        Path filePath = outputDirectory.resolve("output.pdf");

        PdfViewOptions viewOptions = new PdfViewOptions(filePath);
        
        // Set desired JPG quality (0-100 scale)
        byte quality = 10;
        viewOptions.setJpgQuality(quality);

        try (Viewer viewer = new Viewer("YOUR_DOCUMENT_DIRECTORY/source.pptx")) {
            viewer.view(viewOptions);
        }
    }
}
```

**คำอธิบาย:**  
- `setJpgQuality(byte quality)` บอก GroupDocs ว่าจะบีบอัดภาพ JPG มากแค่ไหน ค่าใต้มักทำให้ไฟล์เล็กลงแต่อาจทำให้ความคมชัดลดลง  
- ตัวอย่างใช้ `source.pptx` เพื่อสาธิต **convert pptx to pdf** พร้อมกับบีบอัดภาพในเวลาเดียวกัน  

### ขั้นตอนที่ 3: รันโค้ดและตรวจสอบผลลัพธ์
เรียกใช้ `FeatureAdjustQualityOfJpgImages.run()` ไฟล์ `output.pdf` ที่สร้างขึ้นจะมีภาพ JPG ที่คุณกำหนดคุณภาพไว้ ทำให้ **บีบอัดภาพใน PDF** และลดขนาดไฟล์โดยรวมได้อย่างมีประสิทธิภาพ

## ปัญหาที่พบบ่อย & การแก้ไข
- **เส้นทางไฟล์ไม่ถูกต้อง:** ตรวจสอบให้แน่ใจว่าไฟล์ต้นฉบับ (`source.pptx`) มีอยู่ในตำแหน่งสัมพันธ์กับไดเรกทอรีทำงาน  
- **สิทธิ์ไม่เพียงพอ:** โฟลเดอร์ผลลัพธ์ต้องสามารถเขียนได้ มิฉะนั้นจะเกิด `RuntimeException`  
- **PDF มีขนาดใหญ่กว่าที่คาด:** ตรวจสอบว่าค่า `quality` ต่ำพอสำหรับเป้าหมายขนาดของคุณ  

## การประยุกต์ใช้ในเชิงปฏิบัติ
1. **การจัดเก็บเอกสาร:** PDF ที่เล็กลงช่วยลดค่าใช้จ่ายด้านพื้นที่จัดเก็บและเพิ่มความเร็วในการดึงข้อมูล  
2. **การเผยแพร่บนเว็บ:** โหลดหน้าเร็วขึ้นเมื่อ PDF ถูกฝังหรือเชื่อมโยงในเว็บไซต์  
3. **แนบไฟล์อีเมล:** ปรับคุณภาพภาพเพื่อตรงตามขนาดไฟล์ที่กำหนดก่อนส่ง  

## พิจารณาด้านประสิทธิภาพ
- **การประมวลผลเป็นชุด:** สำหรับเอกสารจำนวนมาก ควรประมวลผลแบบขนานพร้อมตรวจสอบการใช้หน่วยความจำ  
- **การตั้งค่าคุณภาพที่เหมาะสม:** ใช้คุณภาพสูง (80‑100) สำหรับ PDF ที่พร้อมพิมพ์; สำหรับตัวอย่างเว็บ 30‑50 มักเพียงพอ  

## สรุป
คุณได้เรียนรู้ **วิธีบีบอัด PDF** ด้วยการปรับคุณภาพภาพ JPG ด้วย GroupDocs.Viewer ทดลองปรับระดับคุณภาพต่าง ๆ ผสานโค้ดเข้ากับไพพ์ไลน์ที่มีอยู่ของคุณ แล้วเพลิดเพลินกับ PDF ที่เร็วขึ้นและเบาขึ้น

### ขั้นตอนต่อไป
- ทดสอบค่าคุณภาพต่าง ๆ เพื่อหาจุดที่เหมาะสมกับการใช้งานของคุณ  
- สำรวจฟีเจอร์เพิ่มเติมของ GroupDocs เช่น การใส่ลายน้ำหรือการตั้งรหัสผ่าน  

## ส่วนคำถามที่พบบ่อย

1. **การปรับคุณภาพ JPG มีผลต่อขนาดไฟล์อย่างไร?**  
   การลดคุณภาพทำให้ขนาดไฟล์ลดลง ทำให้แชร์หรือจัดเก็บเอกสารง่ายขึ้น  

2. **ฉันสามารถปรับคุณภาพภาพสำหรับรูปแบบอื่นที่ไม่ใช่ JPG ได้หรือไม่?**  
   ฟีเจอร์นี้มุ่งเน้นที่ภาพ JPG ภายใน PDF; อย่างไรก็ตาม GroupDocs.Viewer มีตัวเลือกอื่นสำหรับรูปแบบต่าง ๆ  

3. **ค่าคุณภาพ JPG ที่เหมาะสำหรับการใช้งานบนเว็บคือเท่าไหร่?**  
   ค่าอยู่ที่ประมาณ 50‑70 ให้ความคมชัดที่ดีพร้อมขนาดไฟล์ที่ลดลงเหมาะกับแอปพลิเคชันเว็บ  

4. **สามารถทำกระบวนการนี้อัตโนมัติในเวิร์กโฟลว์แบบแบตช์ได้หรือไม่?**  
   ได้, คุณสามารถรวมฟีเจอร์นี้เข้าในระบบอัตโนมัติเพื่อจัดการเอกสารหลายไฟล์ได้อย่างมีประสิทธิภาพ  

5. **ควรทำอย่างไรหาก PDF ผลลัพธ์ไม่ถูกสร้างตามคาด?**  
   ตรวจสอบเส้นทางไฟล์ต้นฉบับและตรวจสอบให้แน่ใจว่าการตั้งค่าขึ้นต่อทั้งหมดถูกต้อง  

## คำถามที่พบบ่อย

**ถาม:** *ฉันสามารถใช้วิธีนี้แปลงรูปแบบอื่นเช่น DOCX เป็น PDF พร้อมลดขนาดได้หรือไม่?*  
**ตอบ:** แน่นอน. การตั้งค่า `PdfViewOptions.setJpgQuality` ทำงานกับแหล่งข้อมูลใด ๆ ที่สร้างภาพ JPG ใน PDF  

**ถาม:** *การลดคุณภาพ JPG มีผลต่อการแสดงผลข้อความหรือไม่?*  
**ตอบ:** ไม่มี. ข้อความเป็นเวกเตอร์และคงความคมชัด; มีผลต่อเฉพาะภาพเรสเตอร์เท่านั้น  

**ถาม:** *สามารถตั้งค่าคุณภาพต่าง ๆ สำหรับแต่ละหน้าได้หรือไม่?*  
**ตอบ:** GroupDocs ปัจจุบันใช้ค่าคุณภาพเดียวสำหรับการแปลงทั้งหมด หากต้องการควบคุมแยกหน้า ต้องใช้ไลบรารีประมวลผลภาพแยกต่างหาก  

**ถาม:** *ต้องใช้ไลเซนส์สำหรับการใช้งานในผลิตภัณฑ์หรือไม่?*  
**ตอบ:** ใช่, จำเป็นต้องมีไลเซนส์ GroupDocs.Viewer ที่ถูกต้องสำหรับการใช้งานในผลิตภัณฑ์ เวอร์ชันทดลองฟรีใช้ได้สำหรับการประเมินผล  

**ถาม:** *จะตรวจสอบการลดคุณภาพจริงได้อย่างไร?*  
**ตอบ:** เปรียบเทียบขนาดไฟล์ก่อนและหลังการแปลง และเปิด PDF เพื่อตรวจสอบความคมชัดของภาพ  

---

**แหล่งข้อมูล**  
- [Documentation](https://docs.groupdocs.com/viewer/java/)  
- [API Reference](https://reference.groupdocs.com/viewer/java/)  
- [Download GroupDocs.Viewer for Java](https://releases.groupdocs.com/viewer/java/)  
- [Purchase a License](https://purchase.groupdocs.com/buy)  
- [Free Trial Version](https://releases.groupdocs.com/viewer/java/)  
- [Temporary License Information](https://purchase.groupdocs.com/temporary-license/)  
- [Support Forum](https://forum.groupdocs.com/c/viewer/9)  

---

**อัปเดตล่าสุด:** 2026-03-05  
**ทดสอบกับ:** GroupDocs.Viewer 25.2 for Java  
**ผู้เขียน:** GroupDocs