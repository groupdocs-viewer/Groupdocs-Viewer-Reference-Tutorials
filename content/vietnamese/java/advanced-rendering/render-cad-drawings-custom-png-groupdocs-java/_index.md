---
date: '2026-08-30'
description: Tìm hiểu cách chuyển đổi DWG sang PNG, set background color Java, và
  customize image size với GroupDocs.Viewer for Java.
keywords:
- convert dwg to png
- set background color java
- change cad background color
- java convert cad png
lastmod: '2026-08-30'
og_description: Chuyển đổi DWG sang PNG bằng GroupDocs.Viewer for Java trong khi setting
  a custom image width và background color. Hướng dẫn này cung cấp step‑by‑step setup,
  code snippets, và troubleshooting tips.
og_image_alt: 'Guide: converting DWG to PNG with custom size and background color
  using GroupDocs.Viewer for Java'
og_title: Chuyển đổi DWG sang PNG với custom size, background color trong Java
schemas:
- author: GroupDocs
  dateModified: '2026-08-30'
  description: Learn how to convert DWG to PNG, set background color Java, and customize
    image size with GroupDocs.Viewer for Java.
  headline: How to convert DWG to PNG with custom size & background color using GroupDocs.Viewer
    for Java
  type: TechArticle
- questions:
  - answer: Yes, GroupDocs.Viewer supports DXF, DWF, and several additional CAD formats.
    question: Can I render other CAD formats besides DWG?
  - answer: Instantiate a new `Color` with `new Color(123, 45, 67)` and pass it to
      `setBackgroundColor`.
    question: How do I use a custom RGB color instead of a predefined constant?
  - answer: You can specify layout or layer options via `CadOptions` before calling
      `viewer.view`.
    question: Is it possible to render only a specific layout or layer?
  - answer: Set the background color to `new Color(0,0,0,0)` for full transparency
      if the output format supports it.
    question: Does the library support transparent backgrounds?
  - answer: The tutorial uses version 25.2, but newer releases retain the same API
      surface.
    question: What version of GroupDocs.Viewer is required?
  type: FAQPage
tags:
- convert dwg
- GroupDocs.Viewer
- Java CAD rendering
- custom PNG output
title: Cách chuyển đổi DWG sang PNG với custom size & background color bằng GroupDocs.Viewer
  for Java
type: docs
url: /vi/java/advanced-rendering/render-cad-drawings-custom-png-groupdocs-java/
weight: 1
---

# Cách chuyển DWG sang PNG với kích thước tùy chỉnh & màu nền sử dụng GroupDocs.Viewer cho Java

Trong hướng dẫn này, bạn sẽ học **cách chuyển DWG sang PNG** đồng thời kiểm soát kích thước đầu ra và màu nền, sử dụng GroupDocs.Viewer cho Java. Cho dù bạn cần nhúng bản vẽ CAD vào báo cáo, tạo ảnh thu nhỏ cho cổng thông tin web, hoặc tự động hoá việc render hàng loạt, các bước dưới đây sẽ cho bạn kiểm soát đầy đủ về giao diện hình ảnh của mỗi tệp PNG.

## Câu trả lời nhanh
- **Ý nghĩa của “convert DWG to PNG” là gì?** Đó là quá trình chuyển đổi tệp DWG CAD thành hình ảnh PNG bằng mã, giữ lại chi tiết vector dưới dạng pixel raster.  
- **Tôi có thể đặt chiều rộng tùy chỉnh không?** Có – gọi `CadOptions.forRenderingByWidth(int width)` để xác định chiều rộng pixel chính xác mà bạn cần.  
- **Làm thế nào để thay đổi màu nền?** Sử dụng `cadOptions.setBackgroundColor(Color.YOUR_COLOR)` trước khi render.  
- **Thư viện nào được yêu cầu?** GroupDocs.Viewer cho Java (phiên bản 25.2 hoặc mới hơn).  
- **Tôi có cần giấy phép không?** Giấy phép tạm thời hoặc đầy đủ sẽ loại bỏ giới hạn đánh giá và cho phép render không giới hạn.

![Render bản vẽ CAD thành PNG với kích thước tùy chỉnh & màu nền bằng GroupDocs.Viewer cho Java](/viewer/advanced-rendering/render-cad-drawings-as-png-with-custom-size-background-color-java.png)

## GroupDocs.Viewer cho Java là gì?
GroupDocs.Viewer cho Java là một API phía máy chủ cho phép render hơn 150 định dạng tệp — bao gồm các tệp CAD — thành hình ảnh, PDF hoặc HTML. Nó hoạt động mà không cần phần mềm bên thứ ba như AutoCAD, làm cho nó trở nên lý tưởng cho các pipeline tự động.

## Cách chuyển DWG sang PNG với kích thước và màu nền tùy chỉnh?
Tải tệp DWG bằng một thể hiện `Viewer`, cấu hình `CadOptions` cho chiều rộng và màu nền mong muốn, và cuối cùng gọi `viewer.view` với `PngViewOptions`. Quy trình ba bước này xử lý I/O tệp, render và đặt tên đầu ra trong một thao tác duy nhất, tiết kiệm bộ nhớ.

Viewer là lớp chính tải tài liệu và thực hiện render.  
CadOptions cấu hình các thiết lập đặc thù cho CAD như chiều rộng ảnh và màu nền.  
PngViewOptions định nghĩa định dạng đầu ra PNG và mẫu đặt tên cho các trang đã render.

Bây giờ bạn có thể render bất kỳ bản vẽ DWG nào thành PNG với chiều rộng chính xác bạn chỉ định, và bạn có thể chọn bất kỳ màu nền đặc (hoặc trong suốt) nào để phù hợp với thương hiệu hoặc giao diện người dùng của bạn.

## Tại sao cần đặt màu nền tùy chỉnh?
Đặt màu nền giúp PNG đã render hòa hợp một cách liền mạch với các yếu tố UI xung quanh, tránh các lề trắng không mong muốn, và có thể làm nổi bật các chi tiết bản vẽ mà nếu không sẽ bị mất trên nền trắng mặc định. GroupDocs.Viewer hỗ trợ bất kỳ `java.awt.Color` nào, bao gồm các giá trị RGB tùy chỉnh, cung cấp cho bạn kiểm soát pixel‑perfect.

java.awt.Color đại diện cho một giá trị màu được sử dụng để render nền.

## Yêu cầu trước
- **Java Development Kit (JDK) 8+** – API nhắm tới Java 8 và các phiên bản mới hơn.  
- **Maven** – để quản lý phụ thuộc.  
- **IDE** – IntelliJ IDEA, Eclipse, hoặc bất kỳ trình soạn thảo nào bạn thích.  
- **Basic Java file‑handling knowledge** – để đọc các tệp DWG nguồn và ghi các tệp PNG đầu ra.

## Cài đặt GroupDocs.Viewer cho Java
Thêm repository của GroupDocs và phụ thuộc Viewer vào file `pom.xml` của Maven:

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

### Nhận giấy phép
Lấy khóa giấy phép tạm thời hoặc đầy đủ từ cổng thông tin GroupDocs và đặt tệp `license.lic` vào thư mục resources của dự án. Điều này loại bỏ giới hạn 20 trang trong chế độ đánh giá và mở khóa render độ phân giải đầy đủ.

### Khởi tạo và cấu hình cơ bản
Tạo một thể hiện `Viewer` trỏ tới thư mục chứa các tệp DWG của bạn:

```java
import com.groupdocs.viewer.Viewer;
import java.nio.file.Path;

Path documentPath = Path.of("YOUR_DOCUMENT_DIRECTORY/SAMPLE_DWG_WITH_LAYOUTS_AND_LAYERS");
try (Viewer viewer = new Viewer(documentPath.toString())) {
    // Rendering operations go here
}
```

## Tính năng 1: render bản vẽ CAD với kích thước ảnh tùy chỉnh và màu nền
### Cách thay đổi màu nền CAD
Để thay đổi màu nền CAD, cấu hình đối tượng CadOptions trước khi render. Đặt chiều rộng mong muốn bằng `forRenderingByWidth` và áp dụng nền mới bằng `setBackgroundColor`. Viewer sau đó sẽ tạo các ảnh PNG phản ánh màu đã chỉ định, đảm bảo phong cách hình ảnh nhất quán trên tất cả các tệp đầu ra.

#### Triển khai từng bước
##### Nhập các gói cần thiết
```java
import com.groupdocs.viewer.Viewer;
import com.groupdocs.viewer.options.CadOptions;
import com.groupdocs.viewer.options.PngViewOptions;
import java.nio.file.Path;
import java.awt.Color;
```

##### Thiết lập thư mục đầu ra và định dạng đường dẫn tệp
```java
Path outputDirectory = Path.of("YOUR_OUTPUT_DIRECTORY/SetImageBackgroundColor");
Path pageFilePathFormat = outputDirectory.resolve("page_{0}.png");
```

##### Khởi tạo viewer với các tùy chọn render tùy chỉnh
```java
try (Viewer viewer = new Viewer("YOUR_DOCUMENT_DIRECTORY/SAMPLE_DWG_WITH_LAYOUTS_AND_LAYERS")) {
    PngViewOptions options = new PngViewOptions(pageFilePathFormat);
    
    // Specify the width for rendering
    CadOptions cadOptions = CadOptions.forRenderingByWidth(800);
    cadOptions.setBackgroundColor(Color.GREEN);
    
    options.setCadOptions(cadOptions);

    viewer.view(options);
}
```

**Giải thích các tham số**  
- `PngViewOptions` – định nghĩa định dạng đầu ra PNG và mẫu đặt tên.  
- `forRenderingByWidth(int width)` – buộc renderer tạo ảnh có chiều rộng khớp với giá trị pixel được cung cấp; chiều cao được tỷ lệ tương ứng.  
- `setBackgroundColor(Color color)` – ghi đè lên nền trắng mặc định bằng màu bạn chọn, cải thiện tính nhất quán hình ảnh trên các tài nguyên được tạo.

#### Mẹo khắc phục sự cố
- Đảm bảo thư mục đầu ra tồn tại; sử dụng `Files.createDirectories(outputDir)` nếu chưa có.  
- Xác minh đường dẫn tệp đầu vào đúng và ứng dụng có quyền đọc.

## Tính năng 2: đặt màu nền trong tùy chọn render
### Cách đặt màu nền PNG
Đặt màu nền PNG bao gồm việc tạo một thể hiện Color và gán nó cho CadOptions trước khi render. Điều này đảm bảo mỗi PNG được tạo ra sử dụng nền đã chỉ định, phù hợp với hướng dẫn thương hiệu hoặc giao diện người dùng của bạn. Bạn có thể sử dụng các hằng số đã định nghĩa sẵn hoặc định nghĩa giá trị RGB tùy chỉnh để kiểm soát chính xác.

java.awt.Color đại diện cho một giá trị màu được sử dụng để render nền.

#### Triển khai từng bước
##### Nhập các gói cần thiết
```java
import com.groupdocs.viewer.Viewer;
import com.groupdocs.viewer.options.CadOptions;
import com.groupdocs.viewer.options.PngViewOptions;
import java.nio.file.Path;
import java.awt.Color;
```

##### Cấu hình tùy chọn render với màu nền
```java
Path outputDirectory = Path.of("YOUR_OUTPUT_DIRECTORY/SetImageBackgroundColor");
Path pageFilePathFormat = outputDirectory.resolve("page_{0}.png");

try (Viewer viewer = new Viewer("YOUR_DOCUMENT_DIRECTORY/SAMPLE_DWG_WITH_LAYOUTS_AND_LAYERS")) {
    PngViewOptions options = new PngViewOptions(pageFilePathFormat);
    
    CadOptions cadOptions = CadOptions.forRenderingByWidth(800);
    cadOptions.setBackgroundColor(Color.GREEN);
    
    options.setCadOptions(cadOptions);
    
    viewer.view(options);
}
```

**Các tùy chọn cấu hình chính**  
- Điều chỉnh `forRenderingByWidth(int width)` cho các kích thước khác nhau, chẳng hạn 800 px cho ảnh thu nhỏ web hoặc 1920 px cho bản in độ phân giải cao.  
- Sử dụng bất kỳ hằng số `Color` đã định nghĩa sẵn nào (ví dụ, `Color.LIGHT_GRAY`) hoặc tạo một thể hiện tùy chỉnh với `new Color(r, g, b)` để thương hiệu chính xác.

## Ứng dụng thực tiễn
### 1. Tài liệu kỹ thuật
Render tùy chỉnh đảm bảo mỗi bản vẽ tuân thủ hướng dẫn phong cách của công ty, loại bỏ việc chỉnh sửa ảnh thủ công sau khi xuất.

### 2. Trực quan kiến trúc
Trình bày bản thiết kế với nền phù hợp với các slide hoặc cổng thông tin khách hàng, cải thiện sự gắn kết hình ảnh.

### 3. Nguyên mẫu sản xuất
Tạo PNG cho quy trình nguyên mẫu nhanh, nơi các công cụ hạ nguồn yêu cầu kích thước và nền ảnh cụ thể.

### Khả năng tích hợp
Kết hợp pipeline render này với hệ thống quản lý tài liệu (ví dụ, SharePoint) để tự động tạo ảnh xem trước mỗi khi tệp DWG được tải lên.

## Các cân nhắc về hiệu năng
### Tối ưu hoá hiệu năng
- **Xử lý hàng loạt:** Lặp qua một thư mục các tệp DWG và render từng tệp một cách tuần tự để giảm chi phí khởi động JVM.  
- **Quản lý tài nguyên:** Đối với các bản vẽ lớn (hơn 500 trang), tăng heap JVM (`-Xmx2g`) hoặc xử lý tệp theo các lô nhỏ hơn để tránh lỗi hết bộ nhớ.

### Hướng dẫn sử dụng tài nguyên
Giám sát việc sử dụng CPU và bộ nhớ bằng các công cụ như VisualVM; giải phóng các thể hiện `Viewer` kịp thời bằng try‑with‑resources.

### Thực hành tốt cho quản lý bộ nhớ Java
- Sử dụng try‑with‑resources (như đã minh họa) để tự động đóng `Viewer`.  
- Tránh giữ lại các đối tượng `Path` lớn sau khi đã sử dụng.

## Các vấn đề thường gặp và giải pháp
| Vấn đề | Giải pháp |
|-------|----------|
| Thư mục đầu ra không tồn tại | Tạo thư mục trước hoặc thêm `Files.createDirectories(outputDirectory);` |
| Hình ảnh trống | Đảm bảo `cadOptions.setBackgroundColor` được gọi sau `forRenderingByWidth`. |
| Lỗi hết bộ nhớ | Tăng tùy chọn JVM `-Xmx` hoặc xử lý tệp theo các lô nhỏ hơn. |

## Câu hỏi thường gặp
**Q: Tôi có thể render các định dạng CAD khác ngoài DWG không?**  
A: Có, GroupDocs.Viewer hỗ trợ DXF, DWF và một số định dạng CAD khác.

**Q: Làm thế nào để sử dụng màu RGB tùy chỉnh thay vì hằng số đã định nghĩa?**  
A: Tạo một `Color` mới bằng `new Color(123, 45, 67)` và truyền nó vào `setBackgroundColor`.

**Q: Có thể render chỉ một layout hoặc layer cụ thể không?**  
A: Bạn có thể chỉ định các tùy chọn layout hoặc layer qua `CadOptions` trước khi gọi `viewer.view`.

**Q: Thư viện có hỗ trợ nền trong suốt không?**  
A: Đặt màu nền thành `new Color(0,0,0,0)` để có độ trong suốt hoàn toàn nếu định dạng đầu ra hỗ trợ.

**Q: Yêu cầu phiên bản nào của GroupDocs.Viewer?**  
A: Hướng dẫn này sử dụng phiên bản 25.2, nhưng các bản phát hành mới hơn vẫn giữ cùng giao diện API.

---

**Cập nhật lần cuối:** 2026-08-30  
**Kiểm tra với:** GroupDocs.Viewer 25.2 for Java  
**Tác giả:** GroupDocs

## Các hướng dẫn liên quan
- [groupdocs viewer dwg – Cách render các bản vẽ CAD cụ thể trong Java bằng GroupDocs.Viewer](/viewer/java/rendering-basics/render-cad-groupdocs-viewer-java/)
- [Render lớp CAD Java với GroupDocs.Viewer – Hướng dẫn đầy đủ](/viewer/java/advanced-rendering/render-cad-layers-java-groupdocs-viewer/)
- [Cách chuyển pdf sang html và tối ưu chất lượng hình ảnh trong Java với GroupDocs.Viewer](/viewer/java/advanced-rendering/adjust-image-quality-groupdocs-viewer-java/)