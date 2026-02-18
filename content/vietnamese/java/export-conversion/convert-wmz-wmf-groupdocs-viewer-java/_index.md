---
date: '2026-02-18'
description: Học cách chuyển đổi các tệp WMZ và WMF sang PDF, HTML, JPG và PNG bằng
  GroupDocs Viewer cho Java. Hướng dẫn này bao gồm GroupDocs Viewer Java và chuyển
  đổi đồ họa vector bằng Java.
keywords:
- convert WMZ/WMF documents
- GroupDocs Viewer for Java
- rendering formats
title: Cách chuyển đổi WMZ sang PDF và các định dạng khác bằng GroupDocs Viewer cho
  Java
type: docs
url: /vi/java/export-conversion/convert-wmz-wmf-groupdocs-viewer-java/
weight: 1
---

# Cách Chuyển Đổi WMZ sang PDF và Các Định Dạng Khác Sử Dụng GroupDocs Viewer cho Java

Việc chuyển đổi các tệp WMZ (Web Metafile) và WMF (Windows Metafile) sang các định dạng dễ tiếp cận hơn—đặc biệt là **convert WMZ to PDF**—có thể gặp khó khăn vì các định dạng đồ họa vector này lưu trữ hướng dẫn vẽ thay vì dữ liệu pixel. Với **GroupDocs Viewer for Java**, bạn có thể render tài liệu WMZ/WMF sang HTML, JPG, PNG, **PDF**, và các định dạng phổ biến khác chỉ trong vài dòng mã.

![Chuyển đổi tài liệu WMZ/WMF với GroupDocs.Viewer cho Java](/viewer/export-conversion/convert-wmz-wmf-documents.png)

Trong hướng dẫn này, bạn sẽ học cách thiết lập thư viện, render các tệp WMZ/WMF sang đầu ra mong muốn, và xử lý các vấn đề thường gặp. Khi hoàn thành, bạn sẽ có thể tích hợp **groupdocs viewer java** vào các ứng dụng Java của mình để **java convert vector graphics** một cách nhanh chóng và đáng tin cậy.

## Câu trả lời nhanh
- **Các định dạng nào có thể chuyển đổi từ WMZ/WMF?** HTML, JPG, PNG và PDF được hỗ trợ đầy đủ.  
- **Có cần giấy phép cho việc phát triển không?** Bản dùng thử miễn phí đủ cho việc thử nghiệm; giấy phép thương mại sẽ loại bỏ các giới hạn đánh giá.  
- **Yêu cầu phiên bản Java nào?** Java 8 hoặc mới hơn được khuyến nghị.  
- **Có thể render chỉ các trang cụ thể không?** Có, bạn có thể chỉ định phạm vi trang trong các tùy chọn view.  
- **Mối quan ngại về bộ nhớ cho các tệp lớn?** Sử dụng try‑with‑resources và render chỉ các trang cần thiết để giữ bộ nhớ thấp.

## “convert WMZ to PDF” là gì?
Chuyển đổi WMZ sang PDF có nghĩa là lấy tệp WMZ dựa trên vector và raster hoá nó (hoặc giữ lại dữ liệu vector) bên trong một container PDF. PDF có thể xem được trên mọi nền tảng, có khả năng tìm kiếm và in ấn, rất phù hợp cho việc lưu trữ và chia sẻ đồ họa WMZ.

## Tại sao nên dùng GroupDocs Viewer cho Java để chuyển đổi đồ họa vector?
- **Độ trung thực cao**: Thư viện giữ nguyên chất lượng vẽ gốc, dù bạn xuất ra PDF hay PNG.  
- **Không phụ thuộc vào bên ngoài**: Không cần thư viện Windows gốc; mọi thứ chạy trên bất kỳ nền tảng nào có JDK.  
- **API đơn giản**: Một đối tượng `Viewer` và một lời gọi `view` duy nhất xử lý toàn bộ quá trình chuyển đổi.  
- **Mở rộng tốt**: Hoạt động tốt cho cả biểu tượng một trang và bản vẽ kỹ thuật đa trang.

## Yêu cầu trước

### Thư viện cần thiết
- **GroupDocs.Viewer for Java** – động cơ render cốt lõi.  
- Java Development Kit (JDK) 8+.

### Cài đặt môi trường
- IDE như IntelliJ IDEA hoặc Eclipse.  
- Maven để quản lý phụ thuộc (hoặc Gradle nếu bạn thích).

### Kiến thức nền
- Quen thuộc với I/O file trong Java (`java.nio.file.Path`).  
- Hiểu cơ bản cách các trình xem tài liệu render nội dung.

## Thiết lập GroupDocs.Viewer cho Java

Thêm kho và phụ thuộc vào `pom.xml` của bạn:

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

> **Mẹo giấy phép:** Sử dụng bản dùng thử miễn phí để đánh giá, sau đó áp dụng giấy phép tạm thời hoặc mua để mở khóa đầy đủ tính năng.

Khi phụ thuộc đã được giải quyết, bạn có thể tạo một đối tượng `Viewer` sẽ được tái sử dụng cho mỗi bước chuyển đổi.

## Hướng dẫn thực hiện

Chúng tôi sẽ trình bày bốn kịch bản chuyển đổi: HTML, JPG, PNG và PDF. Mỗi ví dụ tuân theo cùng một mẫu—định nghĩa đường dẫn đầu ra, khởi tạo `Viewer` với tệp WMZ nguồn, cấu hình các tùy chọn view phù hợp, và gọi `view`.

### Render WMZ/WMF sang HTML

#### Tổng quan
Đầu ra HTML cho phép bạn nhúng đồ họa trực tiếp vào trang web, với tất cả tài nguyên (hình ảnh, CSS) được chứa trong một tệp duy nhất.

**Bước 1: Định nghĩa đường dẫn thư mục đầu ra**

```java
Path outputDirectory = Utils.getOutputDirectoryPath("RenderingWmzAndWmf");
Path pageFilePathFormat = outputDirectory.resolve("wmz_result.html");
```

**Bước 2: Khởi tạo Viewer và render sang HTML**

```java
try (Viewer viewer = new Viewer(TestFiles.SAMPLE_WMZ)) {
    // Create options that embed all resources inside the HTML file
    HtmlViewOptions options = HtmlViewOptions.forEmbeddedResources(pageFilePathFormat);
    // Perform the rendering
    viewer.view(options);
}
```

### Render WMZ/WMF sang JPG

#### Tổng quan
JPG là định dạng raster được hỗ trợ rộng rãi, thích hợp cho bản xem nhanh hoặc đính kèm email.

**Bước 1: Định nghĩa đường dẫn thư mục đầu ra**

```java
Path outputDirectory = Utils.getOutputDirectoryPath("RenderingWmzAndWmf");
Path pageFilePathFormat = outputDirectory.resolve("wmz_result.jpg");
```

**Bước 2: Khởi tạo Viewer và render sang JPG**

```java
try (Viewer viewer = new Viewer(TestFiles.SAMPLE_WMZ)) {
    JpgViewOptions options = new JpgViewOptions(pageFilePathFormat);
    viewer.view(options);
}
```

### Render WMZ/WMF sang PNG

#### Tổng quan
PNG hỗ trợ trong suốt, rất lý tưởng cho đồ họa cần hòa nhập với các nền khác nhau.

**Bước 1: Định nghĩa đường dẫn thư mục đầu ra**

```java
Path outputDirectory = Utils.getOutputDirectoryPath("RenderingWmzAndWmf");
Path pageFilePathFormat = outputDirectory.resolve("wmz_result.png");
```

**Bước 2: Khởi tạo Viewer và render sang PNG**

```java
try (Viewer viewer = new Viewer(TestFiles.SAMPLE_WMZ)) {
    PngViewOptions options = new PngViewOptions(pageFilePathFormat);
    viewer.view(options);
}
```

### Render WMZ/WMF sang PDF

#### Tổng quan
PDF cung cấp tài liệu độc lập với nền tảng, có khả năng tìm kiếm và giữ nguyên bố cục gốc.

**Bước 1: Định nghĩa đường dẫn thư mục đầu ra**

```java
Path outputDirectory = Utils.getOutputDirectoryPath("RenderingWmzAndWmf");
Path pageFilePathFormat = outputDirectory.resolve("wmz_result.pdf");
```

**Bước 2: Khởi tạo Viewer và render sang PDF**

```java
try (Viewer viewer = new Viewer(TestFiles.SAMPLE_WMZ)) {
    PdfViewOptions options = new PdfViewOptions(pageFilePathFormat);
    viewer.view(options);
}
```

## Các vấn đề thường gặp và giải pháp

| Vấn đề | Nguyên nhân | Giải pháp |
|-------|-------------|----------|
| **OutOfMemoryError** khi xử lý các tệp WMZ lớn | Viewer tải toàn bộ tài liệu vào bộ nhớ | Render từng trang một bằng `PageStreamViewOptions` hoặc tăng heap JVM (`-Xmx`). |
| **Thiếu phông chữ** trong PDF | Phông chữ không được nhúng trong WMZ nguồn | Cài đặt phông chữ cần thiết trên máy chủ hoặc sử dụng `FontSettings` để cung cấp phông chữ tùy chỉnh. |
| **Kết quả PNG trống** | Đường dẫn đầu ra không đúng hoặc không đủ quyền ghi | Kiểm tra `outputDirectory` tồn tại và ứng dụng có quyền ghi. |
| **Tài nguyên HTML không tải** | Sử dụng `forExternalResources` mà không sao chép file | Dùng `forEmbeddedResources` để tạo tệp HTML tự chứa. |

## Câu hỏi thường gặp

**H: Tôi có thể chuyển WMF sang PNG bằng cùng một đoạn mã không?**  
Đ: Có. Ví dụ PNG hoạt động cho cả tệp WMZ và WMF; chỉ cần thay `TestFiles.SAMPLE_WMZ` bằng nguồn WMF của bạn.

**H: Có thể chuyển đổi chỉ một phần các trang không?**  
Đ: Chắc chắn. Sử dụng `PdfViewOptions` (hoặc các tùy chọn tương ứng cho định dạng khác) và gọi `setPageNumbers(List<Integer>)` trước khi render.

**H: Tôi có cần giấy phép riêng cho mỗi định dạng đầu ra không?**  
Đ: Không. Một giấy phép GroupDocs Viewer duy nhất bao phủ tất cả các định dạng được hỗ trợ, bao gồm HTML, JPG, PNG và PDF.

**H: “java convert vector graphics” ảnh hưởng như thế nào đến hiệu năng?**  
Đ: Việc chuyển đổi vector sang raster tốn nhiều CPU. Đối với các batch lớn, hãy cân nhắc đa luồng và tái sử dụng một đối tượng `Viewer` duy nhất cho nhiều tệp.

**H: PDF có giữ được chất lượng vector hay bị raster hoá?**  
Đ: Khi chuyển WMZ/WMF sang PDF, GroupDocs Viewer giữ lại các hướng dẫn vector khi có thể, tạo ra PDF có khả năng phóng to mà không mất chất lượng.

## Kết luận

Bạn đã có một hướng dẫn hoàn chỉnh, sẵn sàng cho môi trường sản xuất để **convert WMZ to PDF** và các định dạng phổ biến khác bằng **GroupDocs Viewer cho Java**. Dù bạn đang xây dựng dịch vụ web phục vụ đồ họa ngay lập tức hay công cụ lưu trữ tài liệu dưới dạng PDF, các bước trên sẽ giúp bạn thực hiện nhanh chóng.

---

**Cập nhật lần cuối:** 2026-02-18  
**Đã kiểm tra với:** GroupDocs.Viewer 25.2 cho Java  
**Tác giả:** GroupDocs  

---