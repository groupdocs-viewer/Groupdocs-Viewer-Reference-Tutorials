---
"date": "2025-04-24"
"description": "เรียนรู้วิธีการแปลงไฟล์ Outlook PST/OST เป็นรูปแบบที่เข้าถึงได้ เช่น HTML, JPG, PNG หรือ PDF ได้อย่างง่ายดายโดยใช้ GroupDocs.Viewer สำหรับ Java คู่มือนี้ครอบคลุมขั้นตอนและการกำหนดค่าทั้งหมดที่จำเป็น"
"title": "แปลง PST/OST เป็น HTML, JPG, PNG, PDF โดยใช้ GroupDocs.Viewer สำหรับ Java | คู่มือการส่งออกและการแปลง"
"url": "/th/java/export-conversion/convert-pst-ost-groupdocs-viewer-java/"
"weight": 1
---

# แปลง PST/OST เป็น HTML, JPG, PNG, PDF โดยใช้ GroupDocs.Viewer สำหรับ Java

## การแนะนำ

คุณกำลังมองหาวิธีแปลงไฟล์ Outlook PST หรือ OST เป็นรูปแบบที่เข้าถึงได้ง่ายขึ้น เช่น HTML, JPG, PNG หรือ PDF หรือไม่ ด้วยไลบรารี GroupDocs.Viewer สำหรับ Java ที่มีประสิทธิภาพ งานนี้จึงตรงไปตรงมาและมีประสิทธิภาพ บทช่วยสอนนี้จะแนะนำคุณเกี่ยวกับการแสดงเอกสาร PST/OST โดยใช้ GroupDocs.Viewer สำหรับ Java ซึ่งทำให้สามารถแชร์และดูเอกสารบนแพลตฟอร์มต่างๆ ได้อย่างง่ายดาย

**สิ่งที่คุณจะได้เรียนรู้:**
- วิธีตั้งค่าสภาพแวดล้อมของคุณด้วย GroupDocs.Viewer สำหรับ Java
- คำแนะนำทีละขั้นตอนในการแปลงไฟล์ PST/OST เป็นรูปแบบ HTML, JPG, PNG และ PDF
- ตัวเลือกการกำหนดค่าที่สำคัญสำหรับเพิ่มประสิทธิภาพกระบวนการแปลงเอกสารของคุณ

เริ่มต้นด้วยการทบทวนข้อกำหนดเบื้องต้นที่คุณจำเป็นต้องมีก่อนที่จะเริ่มต้น

## ข้อกำหนดเบื้องต้น

หากต้องการทำตามบทช่วยสอนนี้ โปรดแน่ใจว่าคุณมีสิ่งต่อไปนี้:

### ไลบรารีและการอ้างอิงที่จำเป็น
- **GroupDocs.Viewer สำหรับ Java**:คุณต้องมีเวอร์ชัน 25.2 ขึ้นไป
- **ชุดพัฒนา Java (JDK)**:ต้องมี JDK 8 ขึ้นไปจึงจะสามารถคอมไพล์และรันแอปพลิเคชันของคุณได้

### ข้อกำหนดการตั้งค่าสภาพแวดล้อม
- สภาพแวดล้อมการพัฒนาแบบบูรณาการ (IDE) ที่เข้ากันได้ เช่น IntelliJ IDEA, Eclipse หรือ NetBeans
- Maven ติดตั้งไว้ในระบบของคุณเพื่อจัดการการอ้างอิง

### ข้อกำหนดเบื้องต้นของความรู้
- ความเข้าใจพื้นฐานเกี่ยวกับการเขียนโปรแกรมภาษา Java
- ความคุ้นเคยกับการใช้ Maven เพื่อการจัดการการอ้างอิง

เมื่อเตรียมสิ่งที่จำเป็นเบื้องต้นเรียบร้อยแล้ว เรามาดำเนินการตั้งค่า GroupDocs.Viewer สำหรับ Java กันเลย

## การตั้งค่า GroupDocs.Viewer สำหรับ Java

หากต้องการใช้ GroupDocs.Viewer สำหรับ Java คุณจะต้องเพิ่มเป็นไฟล์ที่ต้องมีในโปรเจ็กต์ของคุณ หากคุณใช้ Maven ให้ทำตามขั้นตอนเหล่านี้:

**การกำหนดค่า Maven:**

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

### ขั้นตอนการรับใบอนุญาต
- **ทดลองใช้งานฟรี**คุณสามารถเริ่มต้นด้วยการทดลองใช้ฟรีเพื่อสำรวจคุณสมบัติต่างๆ
- **ใบอนุญาตชั่วคราว**:หากต้องการเวลาประเมินเพิ่มเติมให้ยื่นขอใบอนุญาตชั่วคราว
- **ซื้อ**:ซื้อใบอนุญาตเพื่อใช้งานในระยะยาว

### การเริ่มต้นและการตั้งค่าเบื้องต้น

เมื่อการกำหนดค่า Maven ของคุณเสร็จสมบูรณ์แล้ว ให้เริ่มต้น GroupDocs.Viewer ในแอปพลิเคชัน Java ของคุณ:

```java
import com.groupdocs.viewer.Viewer;
import com.groupdocs.viewer.options.HtmlViewOptions;

public class PSTToHTML {
    public static void main(String[] args) {
        // เริ่มต้น Viewer ด้วยตัวอย่างเส้นทางไฟล์ PST
        try (Viewer viewer = new Viewer("YOUR_DOCUMENT_DIRECTORY/SAMPLE_PST")) {
            HtmlViewOptions options = HtmlViewOptions.forEmbeddedResources("output_directory/PST_result.html");
            viewer.view(options);
        }
    }
}
```

เมื่อการตั้งค่าเสร็จสมบูรณ์แล้ว เรามาดำเนินการใช้งานฟีเจอร์การเรนเดอร์กัน

## คู่มือการใช้งาน

ส่วนนี้แบ่งออกเป็นขั้นตอนตามรูปแบบที่คุณต้องการแปลงเอกสาร PST/OST ของคุณ: HTML, JPG, PNG และ PDF

### การเรนเดอร์เอกสาร PST/OST เป็น HTML

**ภาพรวม:**
การเรนเดอร์ไฟล์ PST/OST เป็น HTML ช่วยให้สามารถดูไฟล์เหล่านี้ในเว็บเบราว์เซอร์ได้อย่างง่ายดาย คุณสมบัตินี้จะฝังทรัพยากรโดยตรงไว้ในไฟล์ HTML เพื่อการรับชมที่ราบรื่น

#### ขั้นตอนที่ 1: ตั้งค่าไดเรกทอรีเอาท์พุต

```java
Path outputDirectory = Paths.get("YOUR_OUTPUT_DIRECTORY");
Path pageFilePathFormat = outputDirectory.resolve("PST_result.html");
```

**คำอธิบาย**: กำหนดว่าไฟล์ HTML ของคุณจะถูกบันทึกที่ไหน `Paths` คลาสช่วยจัดการเส้นทางไฟล์อย่างมีประสิทธิภาพ

#### ขั้นตอนที่ 2: กำหนดค่าตัวเลือกการโหลด

```java
LoadOptions loadOptions = new LoadOptions();
loadOptions.setResourceLoadingTimeout(100);
```

**คำอธิบาย**ตั้งเวลาหมดเวลาสำหรับการโหลดทรัพยากรเพื่อป้องกันความล่าช้าในระหว่างการเรนเดอร์

#### ขั้นตอนที่ 3: เริ่มต้นโปรแกรม Viewer และแสดงผล HTML

```java
try (Viewer viewer = new Viewer("YOUR_DOCUMENT_DIRECTORY/SAMPLE_PST", loadOptions)) {
    HtmlViewOptions options = HtmlViewOptions.forEmbeddedResources(pageFilePathFormat);
    viewer.view(options);
}
```

**คำอธิบาย**: ใช้ `HtmlViewOptions` เพื่อฝังทรัพยากรไว้ในไฟล์ HTML `view()` วิธีการดำเนินการการแสดงผล

### การเรนเดอร์เอกสาร PST/OST เป็น JPG

**ภาพรวม:**
แปลงไฟล์ PST/OST แต่ละหน้าของคุณเป็นภาพ JPG แยกกันเพื่อการแบ่งปันและการดูได้อย่างง่ายดาย

#### ขั้นตอนที่ 1: ตั้งค่าไดเรกทอรีเอาท์พุต

```java
Path outputDirectory = Paths.get("YOUR_OUTPUT_DIRECTORY");
Path pageFilePathFormat = outputDirectory.resolve("PST_result_{0}.jpg");
```

**คำอธิบาย**: ระบุไดเรกทอรีและรูปแบบชื่อไฟล์สำหรับไฟล์ JPG เอาท์พุต

#### ขั้นตอนที่ 2: กำหนดค่าตัวเลือกการโหลด

```java
LoadOptions loadOptions = new LoadOptions();
loadOptions.setResourceLoadingTimeout(100);
```

**คำอธิบาย**:คล้ายกับการเรนเดอร์ HTML ตั้งเวลาหมดเวลาในการโหลดทรัพยากร

#### ขั้นตอนที่ 3: เริ่มต้น Viewer และ Render JPG

```java
try (Viewer viewer = new Viewer("YOUR_DOCUMENT_DIRECTORY/SAMPLE_PST", loadOptions)) {
    JpgViewOptions options = new JpgViewOptions(pageFilePathFormat);
    viewer.view(options);
}
```

**คำอธิบาย**: ใช้ `JpgViewOptions` เพื่อแสดงแต่ละหน้าเป็นไฟล์ JPG แยกกัน

### การเรนเดอร์เอกสาร PST/OST เป็น PNG

**ภาพรวม:**
แปลงไฟล์ PST/OST ของคุณเป็นภาพ PNG ซึ่งเหมาะสำหรับการนำเสนอและการพิมพ์คุณภาพสูง

#### ขั้นตอนที่ 1: ตั้งค่าไดเรกทอรีเอาท์พุต

```java
Path outputDirectory = Paths.get("YOUR_OUTPUT_DIRECTORY");
Path pageFilePathFormat = outputDirectory.resolve("PST_result_{0}.png");
```

**คำอธิบาย**: กำหนดไดเรกทอรีและรูปแบบชื่อไฟล์สำหรับไฟล์ PNG

#### ขั้นตอนที่ 2: กำหนดค่าตัวเลือกการโหลด

```java
LoadOptions loadOptions = new LoadOptions();
loadOptions.setResourceLoadingTimeout(100);
```

**คำอธิบาย**ตั้งค่าเวลาหมดเวลาการโหลดทรัพยากรเพื่อจัดการเวลาการเรนเดอร์อย่างมีประสิทธิภาพ

#### ขั้นตอนที่ 3: เริ่มต้นโปรแกรม Viewer และ Render PNG

```java
try (Viewer viewer = new Viewer("YOUR_DOCUMENT_DIRECTORY/SAMPLE_PST", loadOptions)) {
    PngViewOptions options = new PngViewOptions(pageFilePathFormat);
    viewer.view(options);
}
```

**คำอธิบาย**: ใช้ `PngViewOptions` เพื่อแสดงผลแต่ละหน้าเป็นไฟล์ PNG แยกกัน

### การเรนเดอร์เอกสาร PST/OST เป็น PDF

**ภาพรวม:**
แปลงเอกสาร PST/OST ของคุณทั้งหมดเป็นไฟล์ PDF เดียวเพื่อการเผยแพร่และการเก็บถาวรที่ง่ายดาย

#### ขั้นตอนที่ 1: ตั้งค่าไดเรกทอรีเอาท์พุต

```java
Path outputDirectory = Paths.get("YOUR_OUTPUT_DIRECTORY");
Path pageFilePathFormat = outputDirectory.resolve("PST_result.pdf");
```

**คำอธิบาย**: ระบุไดเรกทอรีและชื่อไฟล์สำหรับไฟล์ PDF ที่จะส่งออก

#### ขั้นตอนที่ 2: กำหนดค่าตัวเลือกการโหลด

```java
LoadOptions loadOptions = new LoadOptions();
loadOptions.setResourceLoadingTimeout(100);
```

**คำอธิบาย**ตั้งเวลาหมดเวลาเพื่อให้แน่ใจว่าการเรนเดอร์จะราบรื่นโดยไม่มีความล่าช้า

#### ขั้นตอนที่ 3: เริ่มต้นโปรแกรม Viewer และเรนเดอร์ PDF

```java
try (Viewer viewer = new Viewer("YOUR_DOCUMENT_DIRECTORY/SAMPLE_PST", loadOptions)) {
    PdfViewOptions options = new PdfViewOptions(pageFilePathFormat);
    viewer.view(options);
}
```

**คำอธิบาย**: ใช้ `PdfViewOptions` เพื่อแสดงเอกสารทั้งหมดเป็นไฟล์ PDF เดียว

## การประยุกต์ใช้งานจริง

ต่อไปนี้เป็นกรณีการใช้งานจริงบางส่วนสำหรับการเรนเดอร์เอกสาร PST/OST:

1. **การเก็บถาวรอีเมล์:** แปลงไฟล์อีเมลเป็น HTML หรือ PDF เพื่อให้เข้าถึงและแบ่งปันได้อย่างง่ายดาย
2. **ระบบจัดการเอกสาร:** บูรณาการกับระบบที่ต้องการการแปลงเอกสารเพื่อการจัดเก็บและค้นคืน
3. **เครื่องมือการทำงานร่วมกัน:** แบ่งปันเอกสารที่แปลงแล้วในเครื่องมือการทำงานร่วมกันเช่น Slack หรือ Microsoft Teams
4. **เอกสารทางกฎหมาย:** เตรียมเอกสารทางกฎหมายโดยแปลงให้เป็นรูปแบบที่สามารถเข้าถึงได้สากล
5. **โซลูชั่นการสำรองข้อมูล:** สร้างการสำรองข้อมูลอีเมลและไฟล์แนบที่สำคัญในรูปแบบต่างๆ

## การพิจารณาประสิทธิภาพ

หากต้องการเพิ่มประสิทธิภาพการทำงานเมื่อใช้ GroupDocs.Viewer สำหรับ Java โปรดพิจารณาเคล็ดลับต่อไปนี้:
- มั่นใจถึงการจัดการทรัพยากรอย่างมีประสิทธิภาพระหว่างการเรนเดอร์
- ตรวจสอบการใช้หน่วยความจำและปรับการกำหนดค่าตามต้องการเพื่อป้องกันปัญหาคอขวด
- ใช้ประโยชน์จากการประมวลผลแบบอะซิงโครนัสหากได้รับการสนับสนุนจากบริบทแอปพลิเคชันของคุณเพื่อปรับปรุงการตอบสนอง

หากทำตามคู่มือนี้ คุณสามารถแปลงไฟล์ PST/OST เป็นรูปแบบต่างๆ ได้อย่างมีประสิทธิภาพโดยใช้ GroupDocs.Viewer สำหรับ Java ซึ่งช่วยเพิ่มการเข้าถึงและใช้งานได้บนแพลตฟอร์มต่างๆ