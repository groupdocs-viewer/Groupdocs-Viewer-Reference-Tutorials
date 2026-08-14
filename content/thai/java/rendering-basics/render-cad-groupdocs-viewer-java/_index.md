---
date: '2026-06-20'
description: เรียนรู้วิธีเรนเดอร์เลย์เอาต์เฉพาะจากไฟล์ DWG ด้วย GroupDocs.Viewer สำหรับ
  Java, แปลง CAD เป็น HTML, และดึงข้อมูลเลย์เอาต์ DWG อย่างมีประสิทธิภาพ
keywords:
- groupdocs viewer dwg
- convert cad to html
- extract layout dwg
schemas:
- author: GroupDocs
  dateModified: '2026-06-20'
  description: Learn how to render specific layouts from DWG files with GroupDocs.Viewer
    for Java, convert CAD to HTML, and extract layout DWG efficiently.
  headline: groupdocs viewer dwg – How to Render Specific CAD Drawings in Java Using
    GroupDocs.Viewer
  type: TechArticle
- description: Learn how to render specific layouts from DWG files with GroupDocs.Viewer
    for Java, convert CAD to HTML, and extract layout DWG efficiently.
  name: groupdocs viewer dwg – How to Render Specific CAD Drawings in Java Using GroupDocs.Viewer
  steps:
  - name: Define the output directory
    text: 'Create a folder where the generated HTML files will be saved. The `Utils`
      helper creates a platform‑independent output folder for rendered files. *Explanation*:
      `Utils.getOutputDirectoryPath` builds a platform‑independent path and creates
      the folder if it does not exist.'
  - name: Set up naming for rendered pages
    text: 'Specify a naming pattern that includes a placeholder for the page number.
      *Explanation*: `{0}` is replaced by the page index, allowing you to render multiple
      layouts without filename collisions.'
  - name: Configure HtmlViewOptions
    text: 'Tell the viewer to embed resources and to target a single layout. HtmlViewOptions
      configures how the output HTML is generated, including resource embedding and
      layout selection. *Explanation*: `forEmbeddedResources` packs images and CSS
      directly into the HTML, producing a single portable file per la'
  - name: Choose the layout you want to render
    text: 'Provide the exact layout name as it appears inside the DWG file. The `layoutName`
      property specifies which drawing layout the viewer should render. *Explanation*:
      Setting `layoutName` to `"Model"` (or any custom layout) instructs GroupDocs.Viewer
      to ignore all other views.'
  - name: Render the layout and clean up
    text: 'Open the viewer in a try‑with‑resources block, invoke `view`, and let Java
      close the instance automatically. The `Viewer` class is the main entry point
      for rendering documents with GroupDocs.Viewer. *Explanation*: The `view` call
      streams the selected layout to HTML files in the output folder; the vi'
  type: HowTo
- questions:
  - answer: It is a server‑side library that converts more than 50 document and CAD
      formats—including DWG—into HTML, PNG, or JPEG without needing installed Office
      or CAD software.
    question: What is GroupDocs.Viewer for Java?
  - answer: Visit the [GroupDocs' purchase page](https://purchase.groupdocs.com/temporary-license/)
      and request a free temporary license for development and testing.
    question: How do I obtain a temporary license for GroupDocs.Viewer?
  - answer: Yes, it streams pages and can render multi‑hundred‑page drawings while
      keeping memory usage below 200 MB, provided you close the `Viewer` instance
      after each operation.
    question: Can GroupDocs.Viewer handle very large DWG files efficiently?
  - answer: Absolutely – replace `HtmlViewOptions` with `PdfViewOptions` and specify
      the same layout name to get a PDF output.
    question: Is it possible to convert a DWG layout directly to PDF instead of HTML?
  - answer: The official documentation and API reference contain additional code snippets
      for batch processing and custom rendering pipelines.
    question: Where can I find more examples of layout extraction?
  type: FAQPage
title: groupdocs viewer dwg – วิธีเรนเดอร์ภาพวาด CAD เฉพาะใน Java ด้วย GroupDocs.Viewer
type: docs
url: /th/java/rendering-basics/render-cad-groupdocs-viewer-java/
weight: 1
---

# groupdocs viewer dwg – วิธีเรนเดอร์การวาด CAD เฉพาะใน Java ด้วย GroupDocs.Viewer

การเรนเดอร์เลเอาต์เฉพาะจากไฟล์ DWG เป็นความต้องการทั่วไปเมื่อคุณต้องการโฟกัสที่มุมมองการออกแบบเดียว, สร้างตัวอย่าง HTML ที่มีน้ำหนักเบา, หรือฝังเลเยอร์การวาดเฉพาะลงในหน้าเว็บ ในบทแนะนำนี้คุณจะได้พบว่า **GroupDocs.Viewer for Java** ทำให้การเรนเดอร์เลเอาต์ที่เลือก, แปลง CAD เป็น HTML, และสกัดเลเอาต์ DWG ทำได้อย่างง่ายดายด้วยเพียงไม่กี่บรรทัดของโค้ด

![Render Specific CAD Drawings with GroupDocs.Viewer for Java](/viewer/rendering-basics/render-specific-cad-drawings-java.png)

## คำตอบด่วน
- **ไลบรารีใดที่เรนเดอร์ DWG เป็น HTML?** GroupDocs.Viewer for Java.  
- **ฉันสามารถเรนเดอร์เพียงเลเอาต์เดียวจาก DWG ได้หรือไม่?** ได้ – ระบุชื่อเลเอาต์ใน `HtmlViewOptions`.  
- **ต้องการไลเซนส์สำหรับการพัฒนาหรือไม่?** ทดลองใช้ฟรีทำงานสำหรับการทดสอบ; จำเป็นต้องมีไลเซนส์ถาวรสำหรับการใช้งานจริง.  
- **ต้องการเวอร์ชัน Java ใด?** JDK 8 หรือใหม่กว่า.  
- **การใช้หน่วยความจำเป็นปัญหากับไฟล์ CAD ขนาดใหญ่หรือไม่?** ใช้ตัวเลือกสตรีมมิ่งและปิดอินสแตนซ์ `Viewer` ทันที.

## groupdocs viewer dwg คืออะไร?
`GroupDocs.Viewer` เป็นไลบรารี Java ที่แปลงเอกสารและรูปแบบ CAD มากกว่า 50 รูปแบบ—including DWG—เป็นรูปแบบที่เป็นมิตรต่อเว็บ เช่น HTML, PNG หรือ JPEG มันประมวลผลไฟล์โดยไม่ต้องใช้ซอฟต์แวร์ CAD ต้นแบบ, ให้ผลการเรนเดอร์ที่สม่ำเสมอบนทุกแพลตฟอร์ม

## ทำไมต้องใช้ GroupDocs.Viewer สำหรับการเรนเดอร์ DWG?
GroupDocs.Viewer รองรับ **รูปแบบ CAD เข้า 50+** และสามารถเรนเดอร์การวาดหลายร้อยหน้าได้โดยคงการใช้หน่วยความจำต่ำกว่า 200 MB ด้วยการสตรีมหน้าเมื่อจำเป็น การสกัดเลเอาต์ในตัวช่วยให้คุณแยกมุมมองเดียวออกมา, ลดเวลาโหลดหน้าได้ถึง **70 %** เมื่อเทียบกับการเรนเดอร์การวาดทั้งหมด

## ข้อกำหนดเบื้องต้น
- **GroupDocs.Viewer for Java** ≥ 25.2.  
- Maven สำหรับการจัดการ dependencies.  
- JDK 8+ ติดตั้งในเครื่อง.  
- ความคุ้นเคยพื้นฐานกับโครงสร้างไฟล์ DWG (layouts, model space, paper space).

## วิธีเรนเดอร์เลเอาต์เฉพาะจากไฟล์ DWG?

โหลดไฟล์ DWG ที่ต้องการ, ตั้งค่าตัวเลือกการเรนเดอร์ HTML, และระบุเลเอาต์ที่ต้องการส่งออก โดยการตั้งชื่อเลเอาต์ใน `HtmlViewOptions` ตัว viewer จะสกัดเฉพาะมุมมองนั้นและสร้างไฟล์ HTML ที่สอดคล้องกัน วิธีนี้ทำให้การสร้างตัวอย่างง่ายขึ้นและลดเวลาการประมวลผล, ทั้งกระบวนการประกอบด้วยสามขั้นตอนสั้น ๆ

### ขั้นตอนที่ 1: กำหนดโฟลเดอร์ผลลัพธ์
สร้างโฟลเดอร์ที่ไฟล์ HTML ที่สร้างจะถูกบันทึก

`Utils` helper สร้างโฟลเดอร์ผลลัพธ์ที่เป็นอิสระต่อแพลตฟอร์มสำหรับไฟล์ที่เรนเดอร์  
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
*คำอธิบาย*: `Utils.getOutputDirectoryPath` สร้างเส้นทางที่เป็นอิสระต่อแพลตฟอร์มและสร้างโฟลเดอร์หากยังไม่มี

### ขั้นตอนที่ 2: ตั้งค่าการตั้งชื่อสำหรับหน้าที่เรนเดอร์
ระบุรูปแบบการตั้งชื่อที่รวมตัวแปรแทนเลขหน้า

```java
Path outputDirectory = Utils.getOutputDirectoryPath("YOUR_OUTPUT_DIRECTORY");
```
*คำอธิบาย*: `{0}` จะถูกแทนที่ด้วยดัชนีหน้า, ทำให้คุณสามารถเรนเดอร์หลายเลเอาต์โดยไม่เกิดการชนกันของชื่อไฟล์

### ขั้นตอนที่ 3: ตั้งค่า HtmlViewOptions
บอกให้ viewer ฝังทรัพยากรและกำหนดเป้าหมายเป็นเลเอาต์เดียว

HtmlViewOptions กำหนดวิธีการสร้าง HTML ผลลัพธ์, รวมถึงการฝังทรัพยากรและการเลือกเลเอาต์  
```java
Path pageFilePathFormat = outputDirectory.resolve("page_{0}.html");
```
*คำอธิบาย*: `forEmbeddedResources` จะบรรจุภาพและ CSS ลงใน HTML โดยตรง, ผลลัพธ์เป็นไฟล์พกพาเดียวต่อเลเอาต์

### ขั้นตอนที่ 4: เลือกเลเอาต์ที่ต้องการเรนเดอร์
ระบุชื่อเลเอาต์ที่ตรงกับที่ปรากฏในไฟล์ DWG

คุณสมบัติ `layoutName` ระบุว่า viewer ควรเรนเดอร์เลเอาต์การวาดใด  
```java
HtmlViewOptions viewOptions = HtmlViewOptions.forEmbeddedResources(pageFilePathFormat);
```
*คำอธิบาย*: การตั้งค่า `layoutName` เป็น `"Model"` (หรือเลเอาต์ที่กำหนดเอง) จะทำให้ GroupDocs.Viewer เพิกเฉยต่อมุมมองอื่นทั้งหมด

### ขั้นตอนที่ 5: เรนเดอร์เลเอาต์และทำความสะอาด
เปิด viewer ในบล็อก try‑with‑resources, เรียก `view`, และให้ Java ปิดอินสแตนซ์โดยอัตโนมัติ

คลาส `Viewer` เป็นจุดเข้าหลักสำหรับการเรนเดอร์เอกสารด้วย GroupDocs.Viewer  
```java
viewOptions.getCadOptions().setLayoutName("Model");
```
*คำอธิบาย*: การเรียก `view` จะสตรีมเลเอาต์ที่เลือกไปยังไฟล์ HTML ในโฟลเดอร์ผลลัพธ์; viewer จะถูกทำลายทันทีหลังการเรนเดอร์

## ปัญหาทั่วไปและวิธีแก้
- **ไม่พบเลเอาต์** – ตรวจสอบชื่อเลเอาต์โดยเปิด DWG ในโปรแกรม CAD; การสะกดและตัวพิมพ์ใหญ่‑เล็กต้องตรงกันอย่างแม่นยำ.  
- **ข้อผิดพลาด Out‑of‑memory** – เปิดใช้งาน `Viewer.setMemoryLimit` หรือประมวลผลไฟล์เป็นส่วนย่อย ๆ.  
- **ภาพหาย** – ตรวจสอบให้ `forEmbeddedResources` ถูกตั้งค่า; มิฉะนั้นไฟล์ภาพภายนอกอาจถูกสร้างแยกออกมา.

## คำถามที่พบบ่อย

**Q: GroupDocs.Viewer for Java คืออะไร?**  
A: เป็นไลบรารีฝั่งเซิร์ฟเวอร์ที่แปลงเอกสารและรูปแบบ CAD มากกว่า 50 รูปแบบ—including DWG—เป็น HTML, PNG หรือ JPEG โดยไม่ต้องติดตั้ง Office หรือซอฟต์แวร์ CAD

**Q: จะขอรับไลเซนส์ชั่วคราวสำหรับ GroupDocs.Viewer ได้อย่างไร?**  
A: เยี่ยมชม [GroupDocs' purchase page](https://purchase.groupdocs.com/temporary-license/) และขอรับไลเซนส์ชั่วคราวฟรีสำหรับการพัฒนาและการทดสอบ

**Q: GroupDocs.Viewer สามารถจัดการไฟล์ DWG ขนาดใหญ่อย่างมีประสิทธิภาพได้หรือไม่?**  
A: ได้, มันสตรีมหน้าและสามารถเรนเดอร์การวาดหลายร้อยหน้าได้โดยคงการใช้หน่วยความจำต่ำกว่า 200 MB, เพียงให้แน่ใจว่าปิดอินสแตนซ์ `Viewer` หลังแต่ละการดำเนินการ

**Q: สามารถแปลงเลเอาต์ DWG ไปเป็น PDF โดยตรงแทน HTML ได้หรือไม่?**  
A: แน่นอน – แทนที่ `HtmlViewOptions` ด้วย `PdfViewOptions` และระบุชื่อเลเอาต์เดียวกันเพื่อให้ได้ผลลัพธ์เป็น PDF

**Q: จะหา ตัวอย่างเพิ่มเติมของการสกัดเลเอาต์ได้จากที่ไหน?**  
A: เอกสารอย่างเป็นทางการและอ้างอิง API มีโค้ดสแนปเพิ่มเติมสำหรับการประมวลผลเป็นชุดและไพป์ไลน์การเรนเดอร์แบบกำหนดเอง

## การประยุกต์ใช้งานจริง
1. **การนำเสนอสถาปัตยกรรม** – แสดงเฉพาะเลเอาต์แปลนชั้นที่ต้องการสำหรับการประชุมกับลูกค้า.  
2. **การตรวจสอบการผลิต** – แยกมุมมองส่วนประกอบเพื่อหารือเรื่อง tolerances โดยไม่ต้องโหลดการประกอบทั้งหมด.  
3. **โมดูลการเรียนรู้ออนไลน์** – ฝังมุมมอง CAD เดียวในบทเรียนบนเว็บเพื่อความชัดเจนในการสอน.  
4. **การบูรณาการระบบจัดการเอกสาร** – สกัดตัวอย่างพรีวิวเฉพาะเลเอาต์อัตโนมัติเมื่ออัปโหลดไฟล์ DWG ไปยังคลังข้อมูล.  
5. **การสร้างรายงานแบบกำหนดเอง** – สร้างรายงาน HTML ที่มุ่งเน้นที่มุมมองการวาดเดียว, ลดขนาดไฟล์และเวลาโหลด.

## เคล็ดลับด้านประสิทธิภาพ
- **ใช้ Viewer instance ซ้ำ** สำหรับหลายไฟล์เมื่อทำได้; มันแคชทรัพยากรภายในและเร่งการเรนเดอร์ครั้งต่อไป.  
- **เปิดใช้งานสตรีมมิ่ง** โดยเรียก `Viewer.setRenderMode(RenderMode.Stream)` เพื่อลดการใช้หน่วยความจำ.  
- **บีบอัด HTML ผลลัพธ์** ด้วย gzip บนเว็บเซิร์ฟเวอร์เพื่อเพิ่มความเร็วการโหลดฝั่งไคลเอนต์.

## สรุป
คุณมีวิธีการที่พร้อมใช้งานในระดับการผลิตสำหรับการเรนเดอร์เลเอาต์เฉพาะจากไฟล์ DWG ด้วย **GroupDocs.Viewer for Java** แล้ว การมุ่งเป้าไปที่เลเอาต์เดียวช่วยลดเวลาเรนเดอร์, ลดการใช้หน่วยความจำ, และสร้าง HTML ที่สะอาดสามารถฝังได้ทุกที่—from พอร์ทัลเว็บจนถึงแดชบอร์ดภายในองค์กร

**ขั้นตอนต่อไป**  
- ทดลองเรนเดอร์ชื่อเลเอาต์ต่าง ๆ เช่น `"Top View"` หรือ `"Section A"` เพื่อดูการเปลี่ยนแปลงของผลลัพธ์.  
- สำรวจ `PdfViewOptions` หากต้องการเวอร์ชัน PDF ของเลเอาต์เดียวกัน.  
- ผสานเทคนิคนี้กับ GroupDocs.Annotation เพื่อเพิ่มวอเตอร์มาร์กหรือคอมเมนต์ลงใน HTML ที่เรนเดอร์

---

**Last Updated:** 2026-06-20  
**Tested With:** GroupDocs.Viewer for Java 25.2  
**Author:** GroupDocs  

## แหล่งข้อมูล
- [Documentation](https://docs.groupdocs.com/viewer/java/)
- [API Reference](https://reference.groupdocs.com/viewer/java/)
- [Download GroupDocs.Viewer for Java](https://releases.groupdocs.com/viewer/java/)
- [Purchase a License](https://purchase.groupdocs.com/buy)
- [Free Trial](https://releases.groupdocs.com/viewer/java/)
- [Temporary License Application](https://purchase.groupdocs.com/temporary-license)

```java
try (Viewer viewer = new Viewer(TestFiles.SAMPLE_DWG_WITH_LAYOUTS_AND_LAYERS)) {
    viewer.view(viewOptions);
}
```

## บทเรียนที่เกี่ยวข้อง

- [How to Render CAD Drawings as PNG with Custom Size & Background Color Using GroupDocs.Viewer for Java](/viewer/java/advanced-rendering/render-cad-drawings-custom-png-groupdocs-java/)
- [Split CAD Drawings into Tiles Using GroupDocs.Viewer Java for Efficient Rendering](/viewer/java/advanced-rendering/split-cad-drawings-into-tiles-groupdocs-viewer-java/)
- [Render CAD Layers Java with GroupDocs.Viewer – A Complete Guide](/viewer/java/advanced-rendering/render-cad-layers-java-groupdocs-viewer/)