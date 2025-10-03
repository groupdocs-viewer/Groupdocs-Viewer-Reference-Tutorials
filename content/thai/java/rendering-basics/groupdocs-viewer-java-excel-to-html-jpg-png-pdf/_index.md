---
"date": "2025-04-24"
"description": "เรียนรู้วิธีแปลงไฟล์ Excel เป็น HTML, JPG, PNG และ PDF โดยใช้ GroupDocs.Viewer Java คู่มือนี้ครอบคลุมถึงการตั้งค่า ตัวเลือกการแสดงผล และการใช้งานจริง"
"title": "วิธีใช้ GroupDocs.Viewer Java สำหรับการแปลง Excel เป็น HTML/JPG/PNG/PDF พร้อมคำแนะนำทีละขั้นตอน"
"url": "/th/java/rendering-basics/groupdocs-viewer-java-excel-to-html-jpg-png-pdf/"
"weight": 1
type: docs
---
# วิธีใช้ GroupDocs.Viewer Java สำหรับการแปลง Excel เป็น HTML/JPG/PNG/PDF: คำแนะนำทีละขั้นตอน

## การแนะนำ

การแปลงข้อมูลสเปรดชีตเป็นรูปแบบต่างๆ เช่น HTML, JPG, PNG หรือ PDF โดยยังคงรายละเอียดสำคัญ เช่น ส่วนหัวของแถวและคอลัมน์ ถือเป็นสิ่งสำคัญในสถานการณ์ต่างๆ มากมาย ไม่ว่าคุณจะกำลังสร้างรายงาน แชร์ข้อมูลกับผู้มีส่วนได้ส่วนเสีย หรือผสานสเปรดชีตเข้ากับแอปพลิเคชันบนเว็บ การแปลงแผ่นงาน Excel ถือเป็นข้อกำหนดที่สำคัญ คู่มือนี้จะแนะนำคุณว่า GroupDocs.Viewer Java ช่วยให้งานเหล่านี้ง่ายและแม่นยำได้อย่างไร

**สิ่งที่คุณจะได้เรียนรู้:**
- การตั้งค่าและการใช้ GroupDocs.Viewer สำหรับ Java
- การเรนเดอร์ไฟล์ Excel เป็นรูปแบบ HTML, JPG, PNG และ PDF
- การกำหนดค่าตัวเลือกเพื่อรวมส่วนหัวของแถวและคอลัมน์ในผลลัพธ์ของคุณ
- การประยุกต์ใช้งานจริงของเอกสารที่แสดงผล

ให้เริ่มต้นด้วยข้อกำหนดเบื้องต้นที่จำเป็นก่อนจะลงลึกไปในการใช้งาน

## ข้อกำหนดเบื้องต้น

ก่อนที่จะเรนเดอร์สเปรดชีตด้วย GroupDocs.Viewer Java ให้แน่ใจว่าคุณมี:

### ไลบรารีและการอ้างอิงที่จำเป็น

ตั้งค่า GroupDocs.Viewer สำหรับ Java โดยใช้ Maven ต่อไปนี้เป็นวิธีรวมไว้ในโปรเจ็กต์ของคุณ:

**การตั้งค่า Maven:**
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

### การตั้งค่าสภาพแวดล้อม
- ตรวจสอบให้แน่ใจว่าคุณได้ติดตั้ง Java Development Kit (JDK) แล้ว
- ใช้ IDE เช่น IntelliJ IDEA หรือ Eclipse เพื่อความสะดวกในการพัฒนา

### ข้อกำหนดเบื้องต้นของความรู้
- ความคุ้นเคยกับการเขียนโปรแกรม Java
- ความเข้าใจพื้นฐานของ Maven สำหรับการจัดการการอ้างอิง

เมื่อมีข้อกำหนดเบื้องต้นเหล่านี้แล้ว เรามาดำเนินการตั้งค่า GroupDocs.Viewer สำหรับ Java และเริ่มใช้งานคุณลักษณะต่างๆ ได้เลย

## การตั้งค่า GroupDocs.Viewer สำหรับ Java

GroupDocs.Viewer สำหรับ Java เป็นไลบรารีที่มีความยืดหยุ่นซึ่งช่วยให้คุณสามารถแสดงเอกสารในรูปแบบต่างๆ ได้ วิธีเริ่มต้นใช้งานมีดังนี้:

### ข้อมูลการติดตั้ง
ตามที่กล่าวไว้ ให้ใช้ Maven เพื่อเพิ่ม GroupDocs.Viewer เป็นส่วนที่ต้องมีในโปรเจ็กต์ของคุณ `pom.xml` ไฟล์.

### ขั้นตอนการรับใบอนุญาต
1. **ทดลองใช้งานฟรี:** ดาวน์โหลดเวอร์ชันทดลองใช้ได้จาก [ทดลองใช้ GroupDocs ฟรี](https://releases-groupdocs.com/viewer/java/).
2. **ใบอนุญาตชั่วคราว:** รับใบอนุญาตชั่วคราวเพื่อใช้ฟีเจอร์เพิ่มเติมจาก [ใบอนุญาตชั่วคราวของ GroupDocs](https://purchase-groupdocs.com/temporary-license/).
3. **ซื้อ:** หากต้องการเข้าถึงและสนับสนุนอย่างเต็มรูปแบบ โปรดซื้อใบอนุญาตที่ [การซื้อ GroupDocs](https://purchase-groupdocs.com/buy).

### การเริ่มต้นขั้นพื้นฐาน
เมื่อติดตั้งแล้ว คุณสามารถเริ่มต้น GroupDocs.Viewer ด้วย:
```java
import com.groupdocs.viewer.Viewer;

public class ViewerSetup {
    public static void main(String[] args) {
        try (Viewer viewer = new Viewer("Sample.xlsx")) {
            // โค้ดของคุณที่นี่เพื่อใช้ตัวดู
        }
    }
}
```
นี่จะเป็นการเริ่มต้นสภาพแวดล้อมของคุณ และเตรียมคุณให้พร้อมสำหรับการเรนเดอร์เอกสาร

## คู่มือการใช้งาน

มาแยกรายละเอียดฟีเจอร์แต่ละอย่างและสำรวจวิธีการนำไปใช้งานโดยละเอียด

### เรนเดอร์สเปรดชีตเป็น HTML
**ภาพรวม:** แปลงแผ่นงาน Excel เป็นรูปแบบ HTML ในขณะที่รักษาส่วนหัวของแถวและคอลัมน์สำหรับการนำเสนอหรือรายงานทางเว็บ

#### การดำเนินการทีละขั้นตอน:
##### 1. นำเข้าไลบรารีที่จำเป็น
```java
import com.groupdocs.viewer.Viewer;
import com.groupdocs.viewer.options.HtmlViewOptions;
```
##### 2. ตั้งค่าไดเร็กทอรีเอาท์พุต
กำหนดว่าไฟล์ที่คุณเรนเดอร์จะถูกจัดเก็บไว้ที่ไหน
```java
Path outputDirectory = Paths.get("YOUR_DOCUMENT_DIRECTORY", "RenderRowAndColumnHeadings");
Path pageFilePathFormat = outputDirectory.resolve("page_{0}.html");
```
##### 3. เริ่มต้นตัวดูและกำหนดค่าตัวเลือก
ใช้ GroupDocs.Viewer เพื่อแสดงเอกสาร:
```java
try (Viewer viewer = new Viewer(Paths.get("Sample.xlsx"))) {
    HtmlViewOptions options = HtmlViewOptions.forEmbeddedResources(pageFilePathFormat);
    
    // เปิดใช้งานการเรนเดอร์ส่วนหัวของแถวและคอลัมน์ในสเปรดชีต
    options.getSpreadsheetOptions().setRenderHeadings(true);

    viewer.view(options, 1, 2, 3); // เรนเดอร์หน้า 1 ถึง 3
}
```
**คำอธิบาย:** การ `HtmlViewOptions` คลาสนี้ใช้สำหรับกำหนดค่าเอาต์พุต HTML การตั้งค่า `setRenderHeadings(true)` ช่วยให้แน่ใจว่าส่วนหัวของแถวและคอลัมน์สามารถมองเห็นได้ใน HTML ที่แสดงผล

### เรนเดอร์สเปรดชีตเป็น JPG
**ภาพรวม:** แปลงแผ่นงาน Excel ให้เป็นไฟล์รูปภาพคุณภาพสูง (JPG) พร้อมรวมส่วนหัวของแถวและคอลัมน์ เหมาะสำหรับการนำเสนอภาพหรือการพิมพ์ออกมา

#### การดำเนินการทีละขั้นตอน:
##### 1. นำเข้าไลบรารีที่จำเป็น
```java
import com.groupdocs.viewer.Viewer;
import com.groupdocs.viewer.options.JpgViewOptions;
```
##### 2. ตั้งค่าไดเร็กทอรีเอาท์พุต
```java
Path outputDirectory = Paths.get("YOUR_DOCUMENT_DIRECTORY", "RenderRowAndColumnHeadings");
Path pageFilePathFormat = outputDirectory.resolve("page_{0}.jpg");
```
##### 3. เริ่มต้นตัวดูและกำหนดค่าตัวเลือก
```java
try (Viewer viewer = new Viewer(Paths.get("Sample.xlsx"))) {
    JpgViewOptions options = new JpgViewOptions(pageFilePathFormat);
    
    // เปิดใช้งานการเรนเดอร์ส่วนหัวของแถวและคอลัมน์ในสเปรดชีต
    options.getSpreadsheetOptions().setRenderHeadings(true);

    viewer.view(options, 1, 2, 3); // เรนเดอร์หน้า 1 ถึง 3
}
```
**คำอธิบาย:** `JpgViewOptions` จัดการการตั้งค่าภาพ `setRenderHeadings(true)` ตัวเลือกนี้จะช่วยให้แน่ใจว่าส่วนหัวจะรวมอยู่ในผลลัพธ์ JPG

### เรนเดอร์สเปรดชีตเป็น PNG
**ภาพรวม:** แปลงแผ่นงาน Excel เป็นรูปแบบ PNG ในขณะที่ยังคงส่วนหัวของแถวและคอลัมน์ เหมาะสำหรับเอาท์พุตภาพคุณภาพสูง

#### การดำเนินการทีละขั้นตอน:
##### 1. นำเข้าไลบรารีที่จำเป็น
```java
import com.groupdocs.viewer.Viewer;
import com.groupdocs.viewer.options.PngViewOptions;
```
##### 2. ตั้งค่าไดเร็กทอรีเอาท์พุต
```java
Path outputDirectory = Paths.get("YOUR_DOCUMENT_DIRECTORY", "RenderRowAndColumnHeadings");
Path pageFilePathFormat = outputDirectory.resolve("page_{0}.png");
```
##### 3. เริ่มต้นตัวดูและกำหนดค่าตัวเลือก
```java
try (Viewer viewer = new Viewer(Paths.get("Sample.xlsx"))) {
    PngViewOptions options = new PngViewOptions(pageFilePathFormat);
    
    // เปิดใช้งานการเรนเดอร์ส่วนหัวของแถวและคอลัมน์ในสเปรดชีต
    options.getSpreadsheetOptions().setRenderHeadings(true);

    viewer.view(options, 1, 2, 3); // เรนเดอร์หน้า 1 ถึง 3
}
```
**คำอธิบาย:** `PngViewOptions` ใช้สำหรับการตั้งค่า PNG ด้วย `setRenderHeadings(true)`ส่วนหัวจะรวมอยู่ในรูปภาพเอาต์พุต

### เรนเดอร์สเปรดชีตเป็น PDF
**ภาพรวม:** แปลงแผ่นงาน Excel เป็นรูปแบบ PDF พร้อมทั้งมั่นใจว่าหัวเรื่องแถวและคอลัมน์สามารถมองเห็นได้ เหมาะสำหรับการเก็บถาวรหรือการแชร์เอกสาร

#### การดำเนินการทีละขั้นตอน:
##### 1. นำเข้าไลบรารีที่จำเป็น
```java
import com.groupdocs.viewer.Viewer;
import com.groupdocs.viewer.options.PdfViewOptions;
```
##### 2. ตั้งค่าไดเร็กทอรีเอาท์พุต
```java
Path outputDirectory = Paths.get("YOUR_DOCUMENT_DIRECTORY", "RenderRowAndColumnHeadings");
Path pageFilePathFormat = outputDirectory.resolve("output.pdf");
```
##### 3. เริ่มต้นตัวดูและกำหนดค่าตัวเลือก
```java
try (Viewer viewer = new Viewer(Paths.get("Sample.xlsx"))) {
    PdfViewOptions options = new PdfViewOptions(pageFilePathFormat);
    
    // เปิดใช้งานการเรนเดอร์ส่วนหัวของแถวและคอลัมน์ในสเปรดชีต
    options.getSpreadsheetOptions().setRenderHeadings(true);

    viewer.view(options, 1, 2, 3); // เรนเดอร์หน้า 1 ถึง 3
}
```
**คำอธิบาย:** `PdfViewOptions` กำหนดค่าการตั้งค่าเอาต์พุต PDF `setRenderHeadings(true)` ตัวเลือกนี้ทำให้แน่ใจว่าส่วนหัวจะมองเห็นได้ใน PDF ขั้นสุดท้าย

## การประยุกต์ใช้งานจริง
ต่อไปนี้เป็นสถานการณ์จริงบางส่วนที่สามารถนำคุณลักษณะเหล่านี้ไปใช้:

1. **การรายงานทางธุรกิจ:** แบ่งปันรายงานโดยละเอียดกับผู้ถือผลประโยชน์โดยการแปลงข้อมูล Excel เป็นรูปแบบ HTML หรือ PDF เพื่อการเผยแพร่และการดูได้อย่างง่ายดาย
2. **การแสดงภาพข้อมูล:** แปลงสเปรดชีตเป็นรูปแบบภาพ เช่น JPG หรือ PNG สำหรับการนำเสนอ โดยให้แน่ใจว่าส่วนหัวมีบริบทสำหรับข้อมูลที่มองเห็นได้
3. **การเก็บเอกสารถาวร:** ใช้การแปลง PDF เพื่อเก็บเอกสารในรูปแบบที่สามารถเข้าถึงได้ทั่วไป โดยรักษารายละเอียดที่จำเป็นทั้งหมด เช่น หัวเรื่อง