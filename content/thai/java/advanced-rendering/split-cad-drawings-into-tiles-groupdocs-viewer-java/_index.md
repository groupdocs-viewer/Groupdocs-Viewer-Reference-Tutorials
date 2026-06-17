---
date: '2026-04-01'
description: เรียนรู้วิธีแยกภาพวาด CAD เป็นไทล์โดยใช้ GroupDocs Viewer for Java เพื่อเพิ่มประสิทธิภาพการเรนเดอร์และทำให้การจัดการไฟล์ขนาดใหญ่ง่ายขึ้น
keywords:
- how to split cad
- GroupDocs Viewer Java
- CAD tiling
title: วิธีแบ่งภาพวาด CAD เป็นแผ่นย่อยด้วย GroupDocs Viewer
type: docs
url: /th/java/advanced-rendering/split-cad-drawings-into-tiles-groupdocs-viewer-java/
weight: 1
---

# วิธีแยกภาพวาด CAD เป็นแผ่นย่อยด้วย GroupDocs Viewer

หากคุณกำลังสงสัย **วิธีแยก CAD** เป็นไฟล์ย่อยที่เล็กลงและจัดการได้ง่ายขึ้น คุณมาถูกที่แล้ว ในบทแนะนำนี้เราจะอธิบายขั้นตอนที่จำเป็นในการแยกภาพวาด CAD ขนาดใหญ่เป็นแผ่นย่อยโดยใช้ **GroupDocs Viewer for Java** เมื่อเสร็จคุณจะได้โซลูชันพร้อมใช้งานที่ช่วยเพิ่มความเร็วในการเรนเดอร์ ลดการใช้หน่วยความจำ และทำให้การแสดงภาพวาดในเว็บหรือแอปพลิเคชันมือถือเป็นเรื่องง่ายขึ้น.

![Split CAD Drawings with GroupDocs.Viewer for Java](/viewer/advanced-rendering/split-cad-drawings-java.png)

## คำตอบสั้น
- **การแยก CAD ทำให้ได้อะไร?** มันจะแบ่งภาพวาดขนาดใหญ่เป็นภาพย่อย (tiles) ที่โหลดเร็วขึ้นและใช้หน่วยความจำน้อยลง.  
- **รูปแบบใดที่ใช้สำหรับแผ่นย่อย?** ไฟล์ PNG จะถูกสร้างโดยค่าเริ่มต้น แต่รูปแบบอื่น ๆ ก็รองรับผ่านตัวเลือกของ Viewer.  
- **ฉันต้องการไลเซนส์หรือไม่?** การทดลองใช้งานฟรีทำงานได้สำหรับการพัฒนา; จำเป็นต้องมีไลเซนส์แบบชำระเงินสำหรับการใช้งานจริง.  
- **ฉันสามารถเปลี่ยนขนาดแผ่นย่อยได้หรือไม่?** ใช่ – ปรับการคำนวณ `tileWidth` และ `tileHeight` ให้เหมาะกับความต้องการของคุณ.  
- **วิธีนี้ปลอดภัยต่อการทำงานหลายเธรดหรือไม่?** การเรนเดอร์แต่ละแผ่นย่อยในอินสแตนซ์ `Viewer` ของตนเองโดยใช้ try‑with‑resources ปลอดภัยสำหรับการทำงานพร้อมกัน.

## “การแยก CAD” คืออะไร?
การแยก CAD หมายถึงการแบ่งภาพวาด CAD เดียวที่มักมีขนาดใหญ่เป็นหลายส่วนสี่เหลี่ยมผืนผ้า (tiles) แต่ละแผ่นย่อยจะถูกเรนเดอร์แยกกัน ทำให้คุณสามารถโหลดเฉพาะส่วนที่ผู้ใช้ต้องการเท่านั้น—เหมาะสำหรับแผนที่เว็บ, พอร์ทัลเอกสาร, และผู้ชมบนมือถือ.

## ทำไมต้องใช้ GroupDocs Viewer for Java?
GroupDocs Viewer มีการสนับสนุนไฟล์กว่า 100 รูปแบบพร้อมใช้งานทันที รวมถึง DWG, DXF, และ DWF API แผ่นย่อยของมันให้คุณระบุพิกัดที่ต้องการได้อย่างแม่นยำ เพื่อให้คุณสามารถเรนเดอร์เฉพาะพื้นที่ที่ต้องการโดยไม่ต้องประมวลผลไฟล์ทั้งหมดก่อน สิ่งนี้ช่วยประหยัดการใช้ CPU, ลดแบนด์วิดท์, และมอบประสบการณ์ผู้ใช้ที่ราบรื่นยิ่งขึ้น.

## ข้อกำหนดเบื้องต้น
- **Libraries**: GroupDocs.Viewer for Java ≥ 25.2.  
- **JDK**: Java Development Kit เวอร์ชันล่าสุด (Java 8+).  
- **IDE**: IntelliJ IDEA, Eclipse หรือ IDE ที่รองรับ Java อื่น ๆ.  
- **Build Tool**: Maven (เครื่องมือสร้างอื่น ๆ จะทำงานได้ตราบใดที่เพิ่ม dependency).

## การตั้งค่า GroupDocs.Viewer สำหรับ Java
เพิ่มรีโพซิทอรีของ GroupDocs และ dependency ลงในไฟล์ `pom.xml` ของคุณ:

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

### การรับไลเซนส์
GroupDocs.Viewer offers a free trial license for evaluation:

- **Free Trial**: เยี่ยมชม [GroupDocs Free Trial](https://releases.groupdocs.com/viewer/java/) เพื่อดาวน์โหลดไลบรารี.  
- **Temporary License**: สมัครที่ [Temporary License Page](https://purchase.groupdocs.com/temporary-license/).  
- **Full License**: ซื้อไลเซนส์สำหรับการใช้งานจริงที่ [Purchase Page](https://purchase.groupdocs.com/buy).

### การเริ่มต้นพื้นฐาน
Create a simple `Viewer` instance to verify that the library loads correctly:

```java
import com.groupdocs.viewer.Viewer;

public class ViewerSetup {
    public static void main(String[] args) {
        try (Viewer viewer = new Viewer("path/to/your/drawing.dwg")) {
            // Your rendering code goes here.
        }
    }
}
```

## คู่มือขั้นตอนการแยกภาพวาด CAD เป็นแผ่นย่อย

### ขั้นตอนที่ 1: กำหนดไดเรกทอรีเอาต์พุต
เราจะเก็บแต่ละแผ่นย่อยเป็นไฟล์ PNG แยกกัน การใช้เมธอดยูทิลิตี้ช่วยให้ตรรกะของเส้นทางเป็นระเบียบและนำกลับมาใช้ใหม่ได้.

```java
import java.nio.file.Path;

Path outputDirectory = Utils.getOutputDirectoryPath("SplitDrawingIntoTiles");
Path pageFilePathFormat = outputDirectory.resolve("page_{0}.png");
```

### ขั้นตอนที่ 2: กำหนดตัวเลือกการแสดงผล
ตั้งค่ารูปแบบการเรนเดอร์เป็น PNG และบอก Viewer ไม่ให้โหลดล่วงหน้าทุกหน้า (ช่วยประหยัดหน่วยความจำ).

```java
import com.groupdocs.viewer.options.PngViewOptions;
import com.groupdocs.viewer.options.ViewInfoOptions;

PngViewOptions viewOptions = new PngViewOptions(pageFilePathFormat);
ViewInfoOptions viewInfoOptions = ViewInfoOptions.forPngView(false);
```

### ขั้นตอนที่ 3: คำนวณขนาดแผ่นย่อย
แรกเราจะรับความกว้างและความสูงต้นฉบับของภาพวาด แล้วแบ่งเป็นสี่ส่วนเท่า ๆ กัน.

```java
import com.groupdocs.viewer.results.ViewInfo;
import com.groupdocs.viewer.options.Tile;

ViewInfo viewInfo = new Viewer("path/to/your/drawing.dwg").getViewer().getViewInfo(viewInfoOptions);
int width = viewInfo.getPages().get(0).getWidth();
int height = viewInfo.getPages().get(0).getHeight();

// Each tile is a quarter of the total size.
int tileWidth = width / 2;
int tileHeight = height / 2;

Tile[] tiles = {
    new Tile(0, 0, tileWidth, tileHeight),
    new Tile(tileWidth, 0, tileWidth, tileHeight),
    new Tile(0, tileHeight, tileWidth, tileHeight),
    new Tile(tileWidth, tileHeight, tileWidth, tileHeight)
};
```

### ขั้นตอนที่ 4: เรนเดอร์และบันทึกแผ่นย่อย
เพิ่มแผ่นย่อยที่คำนวณได้ลงในตัวเลือกการเรนเดอร์และให้ `Viewer` สร้างไฟล์ PNG.

```java
viewOptions.getCadOptions().getTiles().addAll(java.util.Arrays.asList(tiles));

try (Viewer viewer = new Viewer("path/to/your/drawing.dwg")) {
    viewer.view(viewOptions);
}
```

### เคล็ดลับการแก้ไขปัญหา
- **Build path** – ตรวจสอบให้แน่ใจว่าไฟล์ JAR ของ GroupDocs อยู่ใน classpath.  
- **Permissions** – โฟลเดอร์เอาต์พุตต้องสามารถเขียนได้โดยกระบวนการ Java.  
- **Exceptions** – หากพบ `ViewerException` ให้ตรวจสอบว่าไฟล์ DWG ไม่เสียหายและไลเซนส์ที่ใช้ถูกต้อง.

## กรณีการใช้งานทั่วไปสำหรับการแยกแผ่นย่อย CAD
1. **Web Mapping** – โหลดเฉพาะส่วนที่มองเห็นของแผนผังชั้นเมื่อผู้ใช้เลื่อน/ซูม.  
2. **Document Management** – เก็บแต่ละแผ่นย่อยแยกกันเพื่อการสร้างตัวอย่างที่เร็วขึ้น.  
3. **Mobile Viewing** – ลดแบนด์วิดท์โดยดาวน์โหลดเฉพาะแผ่นย่อยที่จำเป็นสำหรับหน้าจอปัจจุบัน.

## ข้อควรพิจารณาด้านประสิทธิภาพ
- **Tile Size** – แผ่นย่อยขนาดใหญ่กว่าจะมีไฟล์น้อยลงแต่การเรนเดอร์ช้ากว่า; ค้นหาจุดสมดุลตามความต้องการของ UI ของคุณ.  
- **Memory Monitoring** – ใช้เครื่องมือโปรไฟล์ของ Java (เช่น VisualVM) เพื่อตรวจสอบการใช้ heap เมื่อประมวลผลภาพวาดขนาดใหญ่มาก.  
- **Resource Cleanup** – รูปแบบ try‑with‑resources ที่แสดงข้างต้นจะปล่อยทรัพยากรเนทีฟโดยอัตโนมัติ.

## คำถามที่พบบ่อย

**Q: ฉันสามารถแยกไฟล์ประเภทอื่น (PDF, รูปภาพ) เป็นแผ่นย่อยโดยใช้วิธีเดียวกันได้หรือไม่?**  
A: ได้. GroupDocs Viewer รองรับหลายรูปแบบ; คุณเพียงใช้คลาสตัวเลือกที่สอดคล้อง (เช่น `PdfViewOptions`).

**Q: ฉันจะเปลี่ยนคุณภาพภาพเอาต์พุตได้อย่างไร?**  
A: ปรับ `viewOptions.setResolution(int dpi)` หรือกำหนดการตั้งค่าการบีบอัดบนอ็อบเจ็กต์ `PngOptions`.

**Q: แอปพลิเคชันของฉันใช้หน่วยความจำหมดเมื่อประมวลผลไฟล์ DWG ขนาดใหญ่มาก—ฉันทำอย่างไรได้บ้าง?**  
A: ลดขนาดแผ่นย่อย, เพิ่มขนาด heap ของ JVM (`-Xmx`), หรือเรนเดอร์แผ่นย่อยแบบต่อเนื่องใน `Viewer` แยกกัน.

**Q: สามารถเรนเดอร์แผ่นย่อยแบบอะซิงโครนัสได้หรือไม่?**  
A: แน่นอน. ห่อการเรียกเรนเดอร์แต่ละแผ่นย่อยใน `CompletableFuture` หรือใช้ executor service เพื่อทำงานแบบขนาน.

**Q: ฉันต้องการไลเซนส์แยกสำหรับแต่ละแผ่นย่อยหรือไม่?**  
A: ไม่. ไลเซนส์ GroupDocs Viewer ที่ถูกต้องหนึ่งใบครอบคลุมการเรนเดอร์ทั้งหมดในแอปพลิเคชันของคุณ.

## แหล่งข้อมูล
- [เอกสาร](https://docs.groupdocs.com/viewer/java/)
- [อ้างอิง API](https://reference.groupdocs.com/viewer/java/)
- [ดาวน์โหลด GroupDocs.Viewer](https://releases.groupdocs.com/viewer/java/)
- [ซื้อไลเซนส์](https://purchase.groupdocs.com/buy)
- [ทดลองใช้ฟรี](https://releases.groupdocs.com/viewer/java/)
- [ไลเซนส์ชั่วคราว](https://purchase.groupdocs.com/temporary-license/)
- [ฟอรั่มสนับสนุน](https://forum.groupdocs.com/c/viewer/9)

---

**อัปเดตล่าสุด:** 2026-04-01  
**ทดสอบกับ:** GroupDocs.Viewer 25.2 for Java  
**ผู้เขียน:** GroupDocs  

---