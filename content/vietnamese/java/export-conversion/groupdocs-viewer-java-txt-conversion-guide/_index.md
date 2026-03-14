---
date: '2026-02-21'
description: Tìm hiểu cách sử dụng GroupDocs Viewer Maven để chuyển đổi tệp txt sang
  html, jpg, png và pdf trong Java. Bao gồm các bước chuyển txt sang pdf bằng Java
  và tạo html đa trang bằng Java.
keywords:
- GroupDocs.Viewer for Java
- convert TXT to HTML
- render TXT as JPG/PNG
title: 'groupdocs viewer maven: Chuyển đổi TXT sang HTML, JPG, PNG, PDF'
type: docs
url: /vi/java/export-conversion/groupdocs-viewer-java-txt-conversion-guide/
weight: 1
---

# groupdocs viewer maven: Chuyển Đổi Tệp TXT sang HTML, JPG, PNG và PDF bằng GroupDocs.Viewer cho Java

Trong các ứng dụng Java hiện đại, **groupdocs viewer maven** giúp việc chuyển đổi tài liệu plain‑text (TXT) thành HTML sẵn sàng cho web, hình ảnh độ phân giải cao hoặc tệp PDF di động trở nên đơn giản. Dù bạn đang xây dựng cổng tài liệu, dịch vụ lưu trữ, hay tính năng xem trước, việc chuyển đổi tệp TXT với GroupDocs.Viewer giúp tiết kiệm thời gian và loại bỏ nhu cầu viết bộ phân tích tùy chỉnh. Trong hướng dẫn này, chúng tôi sẽ trình bày toàn bộ quá trình thiết lập và chỉ cho bạn cách **convert txt files java** sang HTML (trang đơn và đa trang), JPG, PNG và PDF.

![Chuyển Đổi Tệp TXT sang HTML, JPG, PNG và PDF với GroupDocs.Viewer cho Java](/viewer/export-conversion/convert-txt-files-to-html-jpg-png-and-pdf-java.png)

## Câu trả lời nhanh
- **Artifact Maven nào tôi cần?** `com.groupdocs:groupdocs-viewer` (xem đoạn mã Maven bên dưới).  
- **Tôi có thể render HTML đa trang không?** Có – sử dụng `HtmlViewOptions.forEmbeddedResources` mà không bật cờ single‑page.  
- **Cần giấy phép cho môi trường production không?** Bản dùng thử hoạt động cho việc đánh giá; giấy phép vĩnh viễn cần thiết cho mục đích thương mại.  
- **Phiên bản Java nào được hỗ trợ?** Java 8 hoặc mới hơn (đề xuất Java 11+).  
- **Có cần thư viện bổ sung để xuất hình ảnh không?** Không, thư viện Viewer đã bao gồm hỗ trợ JPG và PNG ngay từ đầu.

## Groupdocs viewer maven là gì?
**groupdocs viewer maven** là bản phân phối dựa trên Maven của thư viện GroupDocs.Viewer cho Java. Nó cung cấp một API đơn giản để render hơn 100 định dạng tài liệu — bao gồm plain‑text — thành HTML, hình ảnh hoặc PDF mà không cần Microsoft Office hay công cụ bên thứ ba nào khác.

## Tại sao chuyển đổi txt files java?
- **Xem trước đa nền tảng** – HTML và hình ảnh có thể hiển thị trong trình duyệt hoặc ứng dụng di động.  
- **Lưu trữ chuẩn** – PDF giữ nguyên định dạng và có thể đọc trên mọi nền tảng.  
- **Thân thiện với tự động hoá** – Tích hợp chuyển đổi vào các công việc batch, dịch vụ đám mây hoặc pipeline CI.  

## Yêu cầu trước

- **GroupDocs.Viewer cho Java** phiên bản 25.2 trở lên (cung cấp qua Maven).  
- JDK 8 + (đề xuất Java 11 +).  
- Một IDE như IntelliJ IDEA, Eclipse hoặc NetBeans.  
- Kiến thức cơ bản về Java và Maven.  

## Cài đặt GroupDocs.Viewer cho Java

Thêm repository và dependency vào `pom.xml` của bạn:

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

### Các bước lấy giấy phép
- Bắt đầu với **bản dùng thử miễn phí** hoặc lấy **giấy phép tạm thời** để khám phá đầy đủ tính năng.  
- Đối với production, mua giấy phép qua [trang mua hàng](https://purchase.groupdocs.com/buy) chính thức.  

### Khởi tạo và Cài đặt Cơ bản
1. Thêm phụ thuộc Maven như trên.  
2. Đảm bảo JDK và IDE của bạn được cấu hình đúng.  

Bây giờ chúng ta sẽ đi sâu vào các kịch bản chuyển đổi cụ thể.

## Hướng dẫn triển khai

### Tính năng 1: Render TXT sang HTML đa trang *(multi page html java)*

#### Tổng quan
Ví dụ này chuyển đổi tài liệu TXT thành tệp **HTML đa trang**, giữ nguyên các ngắt dòng trên các trang web riêng biệt.

**Nhập các thư viện cần thiết**

```java
import com.groupdocs.viewer.Viewer;
import com.groupdocs.viewer.options.HtmlViewOptions;
```

**Cấu hình đường dẫn và Viewer**

```java
Path outputDirectory = Path.of("YOUR_OUTPUT_DIRECTORY");
Path pageFileFullPath = outputDirectory.resolve("Txt_result.html");

try (Viewer viewer = new Viewer("YOUR_DOCUMENT_DIRECTORY/SAMPLE_TXT")) {
    // Configure options for rendering with embedded resources
    HtmlViewOptions options = HtmlViewOptions.forEmbeddedResources(pageFileFullPath);
    
    // Render the document to HTML using these options
    viewer.view(options);
}
```

*Giải thích:* `HtmlViewOptions.forEmbeddedResources` gói CSS, phông chữ và hình ảnh trực tiếp vào đầu ra HTML, giúp nó di động.

### Tính năng 2: Render TXT sang HTML trang đơn *(convert txt to html java)*

#### Tổng quan
Nén toàn bộ tệp văn bản thành một trang HTML duy nhất — lý tưởng cho việc xem trước nhanh.

**Nhập các thư viện cần thiết**

```java
import com.groupdocs.viewer.Viewer;
import com.groupdocs.viewer.options.HtmlViewOptions;
```

**Cấu hình đường dẫn và Viewer**

```java
Path outputDirectory = Path.of("YOUR_OUTPUT_DIRECTORY");
Path pageFileFullPath = outputDirectory.resolve("Txt_result_single_page.html");

try (Viewer viewer = new Viewer("YOUR_DOCUMENT_DIRECTORY/SAMPLE_2_TXT")) {
    // Configure options for rendering with embedded resources
    HtmlViewOptions options = HtmlViewOptions.forEmbeddedResources(pageFileFullPath);
    
    // Set the option to render as a single page HTML
    options.setRenderToSinglePage(true);
    
    // Render the document using these options
    viewer.view(options);
}
```

*Giải thích:* `setRenderToSinglePage(true)` hợp nhất tất cả các trang thành một tệp HTML.

### Tính năng 3: Render TXT sang JPG

#### Tổng quan
Chuyển đổi tệp TXT thành hình ảnh JPEG chất lượng cao, hữu ích khi chia sẻ trên các nền tảng chỉ chấp nhận hình ảnh.

**Nhập các thư viện cần thiết**

```java
import com.groupdocs.viewer.Viewer;
import com.groupdocs.viewer.options.JpgViewOptions;
```

**Cấu hình đường dẫn và Viewer**

```java
Path outputDirectory = Path.of("YOUR_OUTPUT_DIRECTORY");
Path pageFileFullPath = outputDirectory.resolve("Txt_result.jpg");

try (Viewer viewer = new Viewer("YOUR_DOCUMENT_DIRECTORY/SAMPLE_TXT")) {
    // Configure options for rendering to a JPEG image
    JpgViewOptions options = new JpgViewOptions(pageFileFullPath);
    
    // Render the document as a JPG using these options
    viewer.view(options);
}
```

*Giải thích:* `JpgViewOptions` cho phép bạn kiểm soát chất lượng hình ảnh, DPI và đường dẫn xuất.

### Tính năng 4: Render TXT sang PNG

#### Tổng quan
Tạo hình ảnh PNG không mất dữ liệu từ các tệp văn bản — lý tưởng khi bạn cần đồ họa sắc nét, có thể mở rộng.

**Nhập các thư viện cần thiết**

```java
import com.groupdocs.viewer.Viewer;
import com.groupdocs.viewer.options.PngViewOptions;
```

**Cấu hình đường dẫn và Viewer**

```java
Path outputDirectory = Path.of("YOUR_OUTPUT_DIRECTORY");
Path pageFileFullPath = outputDirectory.resolve("Txt_result.png");

try (Viewer viewer = new Viewer("YOUR_DOCUMENT_DIRECTORY/SAMPLE_TXT")) {
    // Configure options for rendering to a PNG image
    PngViewOptions options = new PngViewOptions(pageFileFullPath);
    
    // Render the document as a PNG using these options
    viewer.view(options);
}
```

*Giải thích:* PNG cung cấp nén không mất dữ liệu, giữ nguyên giao diện chính xác của văn bản gốc.

### Tính năng 5: Render TXT sang PDF *(txt to pdf java / convert txt to pdf java)*

#### Tổng quan
Tạo tệp PDF từ tài liệu TXT — tuyệt vời cho việc lưu trữ, in ấn hoặc gửi cho khách hàng.

**Nhập các thư viện cần thiết**

```java
import com.groupdocs.viewer.Viewer;
import com.groupdocs.viewer.options.PdfViewOptions;
```

**Cấu hình đường dẫn và Viewer**

```java
Path outputDirectory = Path.of("YOUR_OUTPUT_DIRECTORY");
Path pageFileFullPath = outputDirectory.resolve("Txt_result.pdf");

try (Viewer viewer = new Viewer("YOUR_DOCUMENT_DIRECTORY/SAMPLE_TXT")) {
    // Configure options for rendering to a PDF
    PdfViewOptions options = new PdfViewOptions(pageFileFullPath);
    
    // Render the document as a PDF using these options
    viewer.view(options);
}
```

*Giải thích:* `PdfViewOptions` tự động xử lý bố cục trang, phông chữ và nhúng tài nguyên.

## Ứng dụng thực tiễn

1. **Hệ thống quản lý tài liệu:** Tự động chuyển đổi các tài liệu TXT cũ sang HTML cho các cổng intranet.  
2. **Nền tảng xuất bản:** Chuyển bản thảo TXT do tác giả gửi thành HTML để tích hợp mượt mà vào CMS.  
3. **Giải pháp lưu trữ:** Bảo quản các tệp văn bản cũ dưới dạng PDF hoặc PNG cho việc lưu trữ lâu dài.  
4. **Tích hợp lưu trữ đám mây:** Chuyển đổi ngay lập tức và lưu các tệp đã render vào AWS S3, Azure Blob hoặc Google Cloud.  

## Các vấn đề thường gặp và giải pháp

| Vấn đề | Nguyên nhân | Cách khắc phục |
|-------|-------------|----------------|
| **Kết quả trống** | Đường dẫn tệp không đúng hoặc thiếu quyền đọc. | Kiểm tra `YOUR_DOCUMENT_DIRECTORY` trỏ tới tệp TXT thực tế và quá trình có quyền đọc. |
| **Hình ảnh chất lượng thấp** | DPI mặc định quá thấp. | Sử dụng `JpgViewOptions.setResolution(int dpi)` hoặc `PngViewOptions.setResolution(int dpi)` để tăng DPI (ví dụ, 300). |
| **HTML có liên kết bị hỏng** | Tài nguyên không được nhúng. | Sử dụng `HtmlViewOptions.forEmbeddedResources` hoặc cung cấp thư mục tài nguyên tùy chỉnh. |
| **Ngoại lệ giấy phép** | Chưa thiết lập giấy phép hợp lệ. | Tải file giấy phép của bạn bằng `License license = new License(); license.setLicense("path/to/license.file");` trước khi tạo `Viewer`. |

## Câu hỏi thường gặp

**Q: Tôi có thể chuyển đổi các tệp TXT lớn (hàng trăm MB) bằng GroupDocs.Viewer không?**  
A: Có. Thư viện sẽ stream tệp nguồn, nhưng bạn có thể muốn tăng kích thước heap JVM cho các tài liệu rất lớn.

**Q: Tôi có cần phụ thuộc bổ sung để tạo JPG hoặc PNG không?**  
A: Không. Gói Viewer đã bao gồm tất cả các thư viện xử lý hình ảnh cần thiết.

**Q: Có thể tùy chỉnh kích thước trang PDF không?**  
A: Chắc chắn. Sử dụng `PdfViewOptions.setPageSize(PageSize.A4)` hoặc bất kỳ `PageSize` nào khác trước khi render.

**Q: Làm thế nào để xử lý các tệp TXT được bảo vệ bằng mật khẩu?**  
A: Các tệp TXT không hỗ trợ mật khẩu. Nếu tệp được mã hoá, hãy giải mã trước khi truyền cho Viewer.

**Q: Tôi có thể chạy quá trình chuyển đổi này trong container Docker không?**  
A: Có. Chỉ cần bao gồm JDK, sao chép `pom.xml` của bạn có phụ thuộc GroupDocs, và chạy ứng dụng Java bên trong container.

---

**Cập nhật lần cuối:** 2026-02-21  
**Đã kiểm tra với:** GroupDocs.Viewer 25.2 cho Java  
**Tác giả:** GroupDocs