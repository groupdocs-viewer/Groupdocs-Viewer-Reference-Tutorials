---
date: '2026-01-02'
description: เรียนรู้วิธีลดขนาด PDF ด้วย Java โดยปรับคุณภาพ JPG ด้วย GroupDocs.Viewer
  วิธีง่าย ๆ ในการบีบอัดภาพ PDF และสมดุลขนาดไฟล์กับความคมชัดของภาพ
keywords:
- reduce pdf size java
- convert pptx to pdf
- compress pdf images
title: ลดขนาด PDF ด้วย Java – ปรับคุณภาพ JPG ด้วย GroupDocs
type: docs
url: /th/java/advanced-rendering/optimize-jpg-quality-groupdocs-viewer-java/
weight: 1
---

# ลดขนาด PDF ด้วย Java – ปรับคุณภาพ JPG ด้วย GroupDocs

การสมดุลระหว่างขนาดไฟล์และความคมชัดของภาพเป็นความท้าทายทั่วไปเมื่อทำงานกับ PDF ในบทเรียนนี้คุณจะได้เรียนรู้วิธี **reduce PDF size Java** ด้วยการปรับคุณภาพภาพ JPG ภายในเอกสาร PDF โดยใช้ GroupDocs.Viewer for Java เราจะพาคุณผ่านขั้นตอนการตั้งค่า การเขียนโค้ด และเคล็ดลับปฏิบัติ เพื่อให้คุณสามารถบีบอัดภาพใน PDF ได้อย่างมั่นใจโดยไม่สูญเสียความอ่านได้

![ปรับคุณภาพ JPG ใน PDF ด้วย GroupDocs.Viewer for Java](/viewer/advanced-rendering/optimize-jpg-quality-in-pdfs.png)

## คำตอบสั้น
- **“reduce PDF size Java” หมายถึงอะไร?** การปรับคุณภาพภาพ การบีบอัด และการจัดการทรัพยากรเพื่อสร้างไฟล์ PDF ที่มีขนาดเล็กลงในแอปพลิเคชัน Java  
- **การตั้งค่าใดที่ควบคุมคุณภาพ JPG?** `PdfViewOptions.setJpgQuality(byte quality)` โดยค่าจะอยู่ระหว่าง 0 (ต่ำสุด) ถึง 100 (สูงสุด)  
- **ฉันสามารถแปลง PPTX เป็น PDF ในขั้นตอนเดียวได้หรือไม่?** ได้ — เพียงชี้ `Viewer` ไปที่ไฟล์ `.pptx` แล้วใช้ตัวเลือกเดียวกัน  
- **ระดับคุณภาพที่เหมาะสำหรับการเผยแพร่บนเว็บคือเท่าไหร่?** ค่าอยู่ที่ **50‑70** ให้สมดุลที่ดีสำหรับสถานการณ์เว็บส่วนใหญ่  
- **ต้องมีลิขสิทธิ์สำหรับฟีเจอร์นี้หรือไม่?** เวอร์ชันทดลองฟรีใช้ได้สำหรับการประเมิน; ต้องมีลิขสิทธิ์ถาวรสำหรับการใช้งานในผลิตภัณฑ์

## “reduce PDF size Java” คืออะไร?
การลดขนาด PDF ด้วย Java หมายถึงการปรับแต่งทรัพยากรภายใน PDF — โดยเฉพาะภาพ — เพื่อให้ไฟล์สุดท้ายใช้พื้นที่น้อยลงและโหลดเร็วขึ้น การลดคุณภาพ JPG จะทำให้ **compress PDF images** ได้อย่างมีประสิทธิภาพ ซึ่งมักเป็นส่วนที่ทำให้เอกสารมีขนาดใหญ่ที่สุด

## ทำไมต้องปรับคุณภาพ JPG ด้วย GroupDocs Viewer?
- **ลดขนาดอย่างมีนัยสำคัญ**: การลดคุณภาพภาพสามารถทำให้ PDF เล็กลง 30‑70 % ขึ้นอยู่กับความละเอียดต้นฉบับ  
- **การแปลงแบบครั้งเดียว**: ไม่ต้องมีขั้นตอนการประมวลผลภาพแยกต่างหาก; GroupDocs จะจัดการในระหว่างการสร้าง PDF  
- **ความยืดหยุ่น**: คุณสามารถปรับค่า `byte` ของคุณภาพตามความต้องการของโครงการ (เช่น พิมพ์คุณภาพสูง vs. ตัวอย่างเว็บเบา)

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

> **เคล็ดลับระดับโปร:** ควรอัปเดตเวอร์ชันให้เป็นล่าสุดเสมอเพื่อรับประโยชน์จากการปรับปรุงประสิทธิภาพและตัวเลือกการบีบอัดใหม่ ๆ  

## คู่มือการทำงาน

### ขั้นตอนที่ 1: กำหนดเส้นทางโฟลเดอร์ผลลัพธ์
สร้างคลาสช่วยเหลือที่สร้างโฟลเดอร์เอาต์พุตสำหรับบันทึก PDF

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
- `setJpgQuality(byte quality)` บอก GroupDocs ว่าจะบีบอัดภาพ JPG เท่าใด ค่าต่ำจะทำให้ไฟล์เล็กลงแต่อาจลดความคมชัดของภาพ  
- ตัวอย่างใช้ `source.pptx` เพื่อสาธิต **convert pptx to pdf** พร้อมกับบีบอัดภาพในเวลาเดียวกัน  

### ขั้นตอนที่ 3: รันโค้ดและตรวจสอบผลลัพธ์
เรียกใช้ `FeatureAdjustQualityOfJpgImages.run()` ไฟล์ `output.pdf` ที่สร้างขึ้นจะมีภาพ JPG ที่ระดับคุณภาพที่คุณกำหนดไว้ ทำให้ **compress PDF images** และลดขนาดไฟล์โดยรวมได้อย่างมีประสิทธิภาพ  

## ปัญหาที่พบบ่อยและการแก้ไข
- **เส้นทางไฟล์ไม่ถูกต้อง:** ตรวจสอบให้แน่ใจว่าเอกสารต้นทาง (`source.pptx`) มีอยู่ในตำแหน่งที่สัมพันธ์กับไดเรกทอรีทำงาน  
- **สิทธิ์ไม่เพียงพอ:** โฟลเดอร์เอาต์พุตต้องสามารถเขียนได้ มิฉะนั้นจะเกิด `RuntimeException`  
- **PDF ยังคงใหญ่:** ตรวจสอบว่าค่า `quality` ต่ำพอสำหรับเป้าหมายขนาดที่ต้องการ  

## การใช้งานในเชิงปฏิบัติ
1. **การจัดเก็บเอกสาร:** PDF ที่เล็กลงช่วยลดค่าใช้จ่ายด้านพื้นที่จัดเก็บและเพิ่มความเร็วในการดึงข้อมูล  
2. **การเผยแพร่บนเว็บ:** โหลดหน้าเร็วขึ้นเมื่อ PDF ถูกฝังหรือเชื่อมโยงบนเว็บไซต์  
3. **แนบอีเมล:** สามารถทำให้ไฟล์อยู่ในขนาดที่อนุญาตก่อนส่ง  

## พิจารณาด้านประสิทธิภาพ
- **การประมวลผลเป็นชุด:** สำหรับเอกสารจำนวนมาก ควรประมวลผลแบบขนานพร้อมตรวจสอบการใช้หน่วยความจำ  
- **การตั้งค่าคุณภาพที่เหมาะสม:** ใช้คุณภาพสูง (80‑100) สำหรับ PDF ที่ต้องพิมพ์; สำหรับตัวอย่างเว็บอาจใช้ 30‑50 เพียงพอ  

## สรุป
คุณได้เรียนรู้วิธี **reduce PDF size Java** ด้วยการปรับคุณภาพภาพ JPG ผ่าน GroupDocs.Viewer ทดลองปรับระดับคุณภาพต่าง ๆ ผสานโค้ดเข้ากับไลน์พายป์ไลน์ที่มีอยู่ของคุณ แล้วเพลิดเพลินกับ PDF ที่เร็วขึ้นและเบาขึ้น  

### ขั้นตอนต่อไป
- ทดสอบค่าคุณภาพหลายค่าเพื่อหา “sweet spot” ที่เหมาะกับกรณีการใช้งานของคุณ  
- สำรวจฟีเจอร์เพิ่มเติมของ GroupDocs เช่น การใส่ลายน้ำหรือการตั้งรหัสผ่าน  

## ส่วนคำถามที่พบบ่อย (FAQ)

1. **การปรับคุณภาพ JPG มีผลต่อขนาดไฟล์อย่างไร?**  
   การลดคุณภาพจะทำให้ไฟล์เล็กลง ทำให้การแชร์หรือจัดเก็บเอกสารง่ายขึ้น  

2. **สามารถปรับคุณภาพภาพสำหรับรูปแบบอื่นนอกจาก JPG ได้หรือไม่?**  
   ฟีเจอร์นี้มุ่งเน้นที่ภาพ JPG ภายใน PDF; อย่างไรก็ตาม GroupDocs.Viewer มีตัวเลือกอื่นสำหรับรูปแบบต่าง ๆ  

3. **คุณภาพ JPG ที่เหมาะสำหรับการใช้งานบนเว็บคือเท่าไหร่?**  
   ระดับประมาณ 50‑70 ให้ความคมชัดที่ดีพร้อมขนาดไฟล์ที่ลดลงเหมาะกับแอปพลิเคชันเว็บ  

4. **สามารถทำกระบวนการนี้อัตโนมัติในเวิร์กโฟลว์แบบแบชได้หรือไม่?**  
   ได้, คุณสามารถรวมฟีเจอร์นี้เข้าในระบบอัตโนมัติเพื่อจัดการเอกสารหลายไฟล์อย่างมีประสิทธิภาพ  

5. **ถ้า PDF ที่สร้างออกมามิใช่ตามคาดควรทำอย่างไร?**  
   ตรวจสอบเส้นทางไฟล์อินพุตและยืนยันว่าขึ้นตอน dependency ทั้งหมดตั้งค่าอย่างถูกต้อง  

## คำถามที่พบบ่อย (Frequently Asked Questions)

**Q:** *ฉันสามารถใช้วิธีนี้แปลงรูปแบบอื่นเช่น DOCX เป็น PDF พร้อมลดขนาดได้หรือไม่?*  
**A:** แน่นอน. การตั้งค่า `PdfViewOptions.setJpgQuality` ทำงานกับแหล่งข้อมูลใด ๆ ที่สร้างภาพ JPG ใน PDF  

**Q:** *การลดคุณภาพ JPG มีผลต่อการแสดงผลข้อความหรือไม่?*  
**A:** ไม่มี. ข้อความเป็นเวกเตอร์และคงความคมชัด; เฉพาะภาพเรสเตอร์เท่านั้นที่ได้รับผลกระทบ  

**Q:** *สามารถตั้งค่าคุณภาพต่าง ๆ สำหรับแต่ละหน้าได้หรือไม่?*  
**A:** ปัจจุบัน GroupDocs ใช้ค่าคุณภาพเดียวสำหรับการแปลงทั้งหมด หากต้องการควบคุมแยกหน้า จำเป็นต้องใช้ไลบรารีประมวลผลภาพแยกต่างหาก  

**Q:** *ต้องมีลิขสิทธิ์สำหรับการใช้งานในสภาพแวดล้อมการผลิตหรือไม่?*  
**A:** ใช่, ต้องมีลิขสิทธิ์ GroupDocs.Viewer ที่ถูกต้องสำหรับการใช้งานในผลิตภัณฑ์ เวอร์ชันทดลองฟรีใช้ได้สำหรับการประเมิน  

**Q:** *จะตรวจสอบระดับการลดคุณภาพได้อย่างไร?*  
**A:** เปรียบเทียบขนาดไฟล์ก่อนและหลังการแปลง และเปิด PDF เพื่อตรวจสอบความคมชัดของภาพด้วยตาเปล่า  

---

**อัปเดตล่าสุด:** 2026-01-02  
**ทดสอบกับ:** GroupDocs.Viewer 25.2 for Java  
**ผู้เขียน:** GroupDocs  

**แหล่งข้อมูล**  
- [Documentation](https://docs.groupdocs.com/viewer/java/)  
- [API Reference](https://reference.groupdocs.com/viewer/java/)  
- [Download GroupDocs.Viewer for Java](https://releases.groupdocs.com/viewer/java/)  
- [Purchase a License](https://purchase.groupdocs.com/buy)  
- [Free Trial Version](https://releases.groupdocs.com/viewer/java/)  
- [Temporary License Information](https://purchase.groupdocs.com/temporary-license/)  
- [Support Forum](https://forum.groupdocs.com/c/viewer/9)