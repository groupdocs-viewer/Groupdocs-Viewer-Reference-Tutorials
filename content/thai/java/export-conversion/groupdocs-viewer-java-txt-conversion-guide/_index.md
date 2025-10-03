---
"date": "2025-04-24"
"description": "เรียนรู้วิธีการแปลงไฟล์ TXT เป็นรูปแบบต่างๆ เช่น HTML, JPG, PNG และ PDF อย่างมีประสิทธิภาพโดยใช้ GroupDocs.Viewer สำหรับ Java ปฏิบัติตามคำแนะนำทีละขั้นตอนนี้"
"title": "แปลงไฟล์ TXT เป็น HTML, JPG, PNG และ PDF โดยใช้ GroupDocs.Viewer สำหรับ Java"
"url": "/th/java/export-conversion/groupdocs-viewer-java-txt-conversion-guide/"
"weight": 1
type: docs
---
# แปลงไฟล์ TXT ด้วย GroupDocs.Viewer สำหรับ Java: คู่มือฉบับสมบูรณ์

## การแนะนำ

ในโลกดิจิทัลทุกวันนี้ การจัดการเอกสารอย่างมีประสิทธิภาพถือเป็นปัจจัยสำคัญสำหรับทั้งธุรกิจและบุคคล ไม่ว่าคุณจะต้องแสดงเอกสารข้อความบนเว็บหรือเก็บไฟล์ในรูปแบบต่างๆ การแปลงไฟล์ข้อความ (TXT) ถือเป็นข้อกำหนดที่พบบ่อย **GroupDocs.Viewer สำหรับ Java** มอบโซลูชันที่มีประสิทธิภาพสำหรับการเรนเดอร์ไฟล์ TXT เป็นรูปแบบต่างๆ เช่น HTML, JPG, PNG และ PDF ได้อย่างง่ายดาย คู่มือนี้จะแนะนำคุณเกี่ยวกับการใช้ไลบรารีอเนกประสงค์นี้เพื่อให้การแปลงไฟล์เป็นไปอย่างราบรื่น

### สิ่งที่คุณจะได้เรียนรู้:
- การตั้งค่า GroupDocs.Viewer ในสภาพแวดล้อม Java ของคุณ
- การแปลงไฟล์ TXT เป็น HTML หลายหน้าและหน้าเดียว
- การเรนเดอร์เอกสาร TXT เป็นรูปแบบภาพ (JPG, PNG)
- การแปลงเนื้อหา TXT เป็นรูปแบบ PDF

มาสำรวจข้อกำหนดเบื้องต้นที่จำเป็นก่อนจะเริ่มใช้งานกัน

## ข้อกำหนดเบื้องต้น

ก่อนที่จะดำดิ่งลงไปใน GroupDocs.Viewer สำหรับ Java ให้แน่ใจว่าคุณมี:

### ไลบรารีและการอ้างอิงที่จำเป็น:
- **GroupDocs.Viewer สำหรับ Java** เวอร์ชัน 25.2 ขึ้นไป
  
### ข้อกำหนดการตั้งค่าสภาพแวดล้อม:
- ติดตั้ง Java Development Kit (JDK) ที่เข้ากันได้บนระบบของคุณ (แนะนำ Java 8 ขึ้นไป)
- สภาพแวดล้อมการพัฒนาแบบบูรณาการ (IDE) เช่น IntelliJ IDEA, Eclipse หรือ NetBeans

### ข้อกำหนดเบื้องต้นของความรู้:
- ความเข้าใจพื้นฐานเกี่ยวกับการเขียนโปรแกรม Java และการจัดการไฟล์
- ความคุ้นเคยกับ Maven สำหรับการจัดการการอ้างอิงนั้นเป็นประโยชน์

## การตั้งค่า GroupDocs.Viewer สำหรับ Java

การเริ่มใช้งาน **โปรแกรมดูเอกสารกลุ่ม**รวมไว้ในโครงการของคุณผ่าน Maven ดังต่อไปนี้:

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

### ขั้นตอนการรับใบอนุญาต:
- เริ่มต้นด้วย **ทดลองใช้งานฟรี** หรือรับ **ใบอนุญาตชั่วคราว** เพื่อสำรวจความสามารถทั้งหมดของ GroupDocs.Viewer
- พิจารณาซื้อใบอนุญาตผ่านทางเจ้าหน้าที่ของพวกเขา [หน้าการซื้อ](https://purchase.groupdocs.com/buy) สำหรับการใช้งานในระยะยาว

### การเริ่มต้นและการตั้งค่าเบื้องต้น:
1. เพิ่มการอ้างอิง Maven ให้กับโครงการของคุณ
2. ตรวจสอบให้แน่ใจว่าคุณได้ตั้งค่าสภาพแวดล้อมของคุณด้วย JDK และ IDE

ตอนนี้เรามาดูวิธีการนำฟีเจอร์ต่างๆ ของ GroupDocs.Viewer มาใช้เพื่อแปลงไฟล์ TXT เป็นรูปแบบต่างๆ กัน

## คู่มือการใช้งาน

### คุณสมบัติ 1: เรนเดอร์ TXT เป็น HTML หลายหน้า

#### ภาพรวม:
คุณลักษณะนี้จะแปลงเอกสาร TXT เป็นรูปแบบ HTML หลายหน้า โดยรักษาโครงสร้างข้อความทั่วทั้งเว็บเพจหลายๆ หน้า

##### ขั้นตอน:

**นำเข้าไลบรารีที่จำเป็น**
```java
import com.groupdocs.viewer.Viewer;
import com.groupdocs.viewer.options.HtmlViewOptions;
```

**ตั้งค่าเส้นทางและตัวแสดง**
```java
Path outputDirectory = Path.of("YOUR_OUTPUT_DIRECTORY");
Path pageFileFullPath = outputDirectory.resolve("Txt_result.html");

try (Viewer viewer = new Viewer("YOUR_DOCUMENT_DIRECTORY/SAMPLE_TXT")) {
    // กำหนดค่าตัวเลือกสำหรับการเรนเดอร์ด้วยทรัพยากรที่ฝังไว้
    HtmlViewOptions options = HtmlViewOptions.forEmbeddedResources(pageFileFullPath);
    
    // เรนเดอร์เอกสารเป็น HTML โดยใช้ตัวเลือกเหล่านี้
    viewer.view(options);
}
```

**คำอธิบาย:**
- `HtmlViewOptions.forEmbeddedResources` ถูกใช้ที่นี่เพื่อให้แน่ใจว่าทรัพยากรทั้งหมดถูกฝังไว้ในไฟล์เอาต์พุต ทำให้มีความสมบูรณ์ในตัวเอง

### คุณสมบัติ 2: เรนเดอร์ TXT เป็น HTML หน้าเดียว

#### ภาพรวม:
คุณลักษณะนี้จะช่วยรวมเอกสารข้อความทั้งหมดของคุณลงในหน้า HTML เดียว ซึ่งเหมาะสำหรับการดูตัวอย่างหรือสรุปอย่างรวดเร็ว

##### ขั้นตอน:

**นำเข้าไลบรารีที่จำเป็น**
```java
import com.groupdocs.viewer.Viewer;
import com.groupdocs.viewer.options.HtmlViewOptions;
```

**ตั้งค่าเส้นทางและตัวแสดง**
```java
Path outputDirectory = Path.of("YOUR_OUTPUT_DIRECTORY");
Path pageFileFullPath = outputDirectory.resolve("Txt_result_single_page.html");

try (Viewer viewer = new Viewer("YOUR_DOCUMENT_DIRECTORY/SAMPLE_2_TXT")) {
    // กำหนดค่าตัวเลือกสำหรับการเรนเดอร์ด้วยทรัพยากรที่ฝังไว้
    HtmlViewOptions options = HtmlViewOptions.forEmbeddedResources(pageFileFullPath);
    
    // ตั้งค่าตัวเลือกให้แสดงผลเป็น HTML หน้าเดียว
    options.setRenderToSinglePage(true);
    
    // แสดงผลเอกสารโดยใช้ตัวเลือกเหล่านี้
    viewer.view(options);
}
```

**คำอธิบาย:**
การ `setRenderToSinglePage(true)` วิธีการรวมข้อความทั้งหมดไว้ในเว็บเพจเดียว

### คุณสมบัติที่ 3: เรนเดอร์ TXT เป็น JPG

#### ภาพรวม:
แปลงไฟล์ TXT ของคุณเป็นภาพ JPEG คุณภาพสูง เหมาะสำหรับการแบ่งปันหรือการพิมพ์

##### ขั้นตอน:

**นำเข้าไลบรารีที่จำเป็น**
```java
import com.groupdocs.viewer.Viewer;
import com.groupdocs.viewer.options.JpgViewOptions;
```

**ตั้งค่าเส้นทางและตัวแสดง**
```java
Path outputDirectory = Path.of("YOUR_OUTPUT_DIRECTORY");
Path pageFileFullPath = outputDirectory.resolve("Txt_result.jpg");

try (Viewer viewer = new Viewer("YOUR_DOCUMENT_DIRECTORY/SAMPLE_TXT")) {
    // กำหนดค่าตัวเลือกสำหรับการเรนเดอร์เป็นภาพ JPEG
    JpgViewOptions options = new JpgViewOptions(pageFileFullPath);
    
    // เรนเดอร์เอกสารเป็น JPG โดยใช้ตัวเลือกเหล่านี้
    viewer.view(options);
}
```

**คำอธิบาย:**
- `JpgViewOptions` ช่วยให้คุณระบุเส้นทางเอาต์พุตและการตั้งค่าการเรนเดอร์ที่เหมาะกับการแปลงภาพได้

### คุณสมบัติที่ 4: เรนเดอร์ TXT เป็น PNG

#### ภาพรวม:
แปลงเอกสารข้อความเป็นรูปแบบ Portable Network Graphics (PNG) ให้ภาพคุณภาพสูงด้วยการบีบอัดแบบไม่สูญเสียข้อมูล

##### ขั้นตอน:

**นำเข้าไลบรารีที่จำเป็น**
```java
import com.groupdocs.viewer.Viewer;
import com.groupdocs.viewer.options.PngViewOptions;
```

**ตั้งค่าเส้นทางและตัวแสดง**
```java
Path outputDirectory = Path.of("YOUR_OUTPUT_DIRECTORY");
Path pageFileFullPath = outputDirectory.resolve("Txt_result.png");

try (Viewer viewer = new Viewer("YOUR_DOCUMENT_DIRECTORY/SAMPLE_TXT")) {
    // กำหนดค่าตัวเลือกสำหรับการเรนเดอร์เป็นภาพ PNG
    PngViewOptions options = new PngViewOptions(pageFileFullPath);
    
    // เรนเดอร์เอกสารเป็น PNG โดยใช้ตัวเลือกเหล่านี้
    viewer.view(options);
}
```

**คำอธิบาย:**
- `PngViewOptions` ใช้ที่นี่ คล้ายกับ `JpgViewOptions`แต่มีข้อดีที่เฉพาะเจาะจงกับรูปแบบ PNG

### คุณสมบัติ 5: เรนเดอร์ TXT เป็น PDF

#### ภาพรวม:
สร้างไฟล์ PDF จากเอกสารข้อความ เหมาะสำหรับการเผยแพร่หรือเก็บถาวรในรูปแบบที่ได้รับการยอมรับทั่วโลก

##### ขั้นตอน:

**นำเข้าไลบรารีที่จำเป็น**
```java
import com.groupdocs.viewer.Viewer;
import com.groupdocs.viewer.options.PdfViewOptions;
```

**ตั้งค่าเส้นทางและตัวแสดง**
```java
Path outputDirectory = Path.of("YOUR_OUTPUT_DIRECTORY");
Path pageFileFullPath = outputDirectory.resolve("Txt_result.pdf");

try (Viewer viewer = new Viewer("YOUR_DOCUMENT_DIRECTORY/SAMPLE_TXT")) {
    // กำหนดค่าตัวเลือกสำหรับการเรนเดอร์เป็น PDF
    PdfViewOptions options = new PdfViewOptions(pageFileFullPath);
    
    // แสดงเอกสารเป็น PDF โดยใช้ตัวเลือกเหล่านี้
    viewer.view(options);
}
```

**คำอธิบาย:**
- `PdfViewOptions` ให้การตั้งค่าที่เฉพาะเจาะจงสำหรับการแปลง PDF รวมถึงการตั้งค่าหน้าและการฝังทรัพยากร

## การประยุกต์ใช้งานจริง

ความสามารถของ GroupDocs.Viewer สำหรับ Java ขยายไปสู่กรณีการใช้งานจริงหลายกรณี:

1. **ระบบจัดการเอกสาร:** ทำให้การแปลงเอกสารแบบข้อความเป็นรูปแบบที่เป็นมิตรต่อเว็บสำหรับพอร์ทัลภายในเป็นแบบอัตโนมัติ
2. **แพลตฟอร์มการเผยแพร่:** แปลงการส่งของผู้เขียนจาก TXT เป็น HTML เพื่อการรวมเข้ากับระบบการจัดการเนื้อหาอย่างราบรื่น
3. **โซลูชันการเก็บถาวร:** เก็บรักษาไฟล์ข้อความดั้งเดิมในรูปแบบ PDF หรือรูปภาพที่ทันสมัยและเข้าถึงได้ง่าย
4. **การบูรณาการกับที่เก็บข้อมูลบนคลาวด์:** แปลงและจัดเก็บเอกสารโดยอัตโนมัติบนแพลตฟอร์มคลาวด์เพื่อการเข้าถึงที่ดีขึ้น