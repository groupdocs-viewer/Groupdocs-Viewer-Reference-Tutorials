---
date: '2026-02-15'
description: Tìm hiểu cách chuyển đổi pst sang html và các định dạng khác như JPG,
  PNG, PDF bằng GroupDocs.Viewer cho Java. Hướng dẫn này bao gồm tất cả các bước và
  cấu hình cần thiết.
keywords:
- convert PST/OST
- GroupDocs.Viewer for Java
- render documents
title: Chuyển đổi PST sang HTML, JPG, PNG, PDF bằng GroupDocs.Viewer cho Java
type: docs
url: /vi/java/export-conversion/convert-pst-ost-groupdocs-viewer-java/
weight: 1
---

0}} not inside backticks. So we keep them as is.

Also ensure we keep any markdown formatting like bold, headings.

Now craft final answer.# Chuyển đổi PST sang HTML, JPG, PNG, PDF bằng GroupDocs.Viewer cho Java

Bạn có muốn **convert pst to html** hoặc các định dạng khác như JPG, PNG, hoặc PDF không? Với thư viện mạnh mẽ GroupDocs.Viewer for Java, nhiệm vụ này trở nên đơn giản và hiệu quả. Trong hướng dẫn này, bạn sẽ học cách render các tệp Outlook PST/OST thành HTML thân thiện với web, các tệp hình ảnh, hoặc một tệp PDF duy nhất, giúp việc chia sẻ và lưu trữ các kho lưu trữ email của bạn trở nên dễ dàng.

![Chuyển đổi PST/OST sang HTML, JPG, PNG, PDF với GroupDocs.Viewer cho Java](/viewer/export-conversion/convert-pst-ost-to-html-jpg-png-pdf.png)

**Bạn sẽ học được**
- Cách thiết lập GroupDocs.Viewer for Java trong dự án Maven.  
- Hướng dẫn từng bước để **java convert pst** các tệp sang HTML, JPG, PNG và PDF.  
- Mẹo cấu hình để đạt hiệu năng tối ưu và tránh các lỗi thường gặp.

## Câu trả lời nhanh
- **Thư viện nào xử lý chuyển đổi PST?** GroupDocs.Viewer for Java.  
- **Có thể chuyển đổi PST sang PDF trực tiếp không?** Có, sử dụng `PdfViewOptions`.  
- **Cần giấy phép cho môi trường production không?** Cần một giấy phép GroupDocs hợp lệ.  
- **Phiên bản Java nào được hỗ trợ?** JDK 8 hoặc cao hơn.  
- **Có cần phải trích xuất tệp đính kèm thủ công không?** Không, viewer sẽ render chúng tự động.

## Cách chuyển đổi pst sang html bằng GroupDocs.Viewer cho Java
Dưới đây là tổng quan ngắn gọn về quy trình chuyển đổi trước khi đi vào các ví dụ mã chi tiết.

### Tại sao chọn GroupDocs.Viewer?
- **High fidelity** rendering of email bodies, attachments, and formatting.  
- **Multiple output formats** (HTML, JPG, PNG, PDF) from a single API.  
- **No external dependencies** – everything runs inside your Java application.

## Yêu cầu trước

- **GroupDocs.Viewer for Java** – phiên bản 25.2 hoặc mới hơn.  
- **Java Development Kit (JDK)** – 8 hoặc mới hơn.  
- Maven để quản lý phụ thuộc.  
- Kiến thức cơ bản về Java và Maven.

## Thiết lập GroupDocs.Viewer cho Java

Thêm repository và dependency của GroupDocs vào file `pom.xml` của bạn:

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

### License Acquisition
- **Free trial** – khám phá tất cả tính năng mà không tốn phí.  
- **Temporary license** – kéo dài thời gian đánh giá nếu cần.  
- **Full license** – bắt buộc cho các triển khai production.

### Basic Initialization

```java
import com.groupdocs.viewer.Viewer;
import com.groupdocs.viewer.options.HtmlViewOptions;

public class PSTToHTML {
    public static void main(String[] args) {
        // Initialize Viewer with a sample PST file path
        try (Viewer viewer = new Viewer("YOUR_DOCUMENT_DIRECTORY/SAMPLE_PST")) {
            HtmlViewOptions options = HtmlViewOptions.forEmbeddedResources("output_directory/PST_result.html");
            viewer.view(options);
        }
    }
}
```

## Hướng dẫn triển khai

Các phần sau sẽ hướng dẫn bạn render các tệp PST/OST thành từng định dạng được hỗ trợ.

### Render tài liệu PST/OST sang HTML

#### Bước 1: Thiết lập thư mục đầu ra

```java
Path outputDirectory = Paths.get("YOUR_OUTPUT_DIRECTORY");
Path pageFilePathFormat = outputDirectory.resolve("PST_result.html");
```

#### Bước 2: Cấu hình Load Options

```java
LoadOptions loadOptions = new LoadOptions();
loadOptions.setResourceLoadingTimeout(100);
```

#### Bước 3: Khởi tạo Viewer và render HTML

```java
try (Viewer viewer = new Viewer("YOUR_DOCUMENT_DIRECTORY/SAMPLE_PST", loadOptions)) {
    HtmlViewOptions options = HtmlViewOptions.forEmbeddedResources(pageFilePathFormat);
    viewer.view(options);
}
```

### Render tài liệu PST/OST sang JPG

#### Bước 1: Thiết lập thư mục đầu ra

```java
Path outputDirectory = Paths.get("YOUR_OUTPUT_DIRECTORY");
Path pageFilePathFormat = outputDirectory.resolve("PST_result_{0}.jpg");
```

#### Bước 2: Cấu hình Load Options

```java
LoadOptions loadOptions = new LoadOptions();
loadOptions.setResourceLoadingTimeout(100);
```

#### Bước 3: Khởi tạo Viewer và render JPG

```java
try (Viewer viewer = new Viewer("YOUR_DOCUMENT_DIRECTORY/SAMPLE_PST", loadOptions)) {
    JpgViewOptions options = new JpgViewOptions(pageFilePathFormat);
    viewer.view(options);
}
```

### Render tài liệu PST/OST sang PNG

#### Bước 1: Thiết lập thư mục đầu ra

```java
Path outputDirectory = Paths.get("YOUR_OUTPUT_DIRECTORY");
Path pageFilePathFormat = outputDirectory.resolve("PST_result_{0}.png");
```

#### Bước 2: Cấu hình Load Options

```java
LoadOptions loadOptions = new LoadOptions();
loadOptions.setResourceLoadingTimeout(100);
```

#### Bước 3: Khởi tạo Viewer và render PNG

```java
try (Viewer viewer = new Viewer("YOUR_DOCUMENT_DIRECTORY/SAMPLE_PST", loadOptions)) {
    PngViewOptions options = new PngViewOptions(pageFilePathFormat);
    viewer.view(options);
}
```

### Render tài liệu PST/OST sang PDF

#### Bước 1: Thiết lập thư mục đầu ra

```java
Path outputDirectory = Paths.get("YOUR_OUTPUT_DIRECTORY");
Path pageFilePathFormat = outputDirectory.resolve("PST_result.pdf");
```

#### Bước 2: Cấu hình Load Options

```java
LoadOptions loadOptions = new LoadOptions();
loadOptions.setResourceLoadingTimeout(100);
```

#### Bước 3: Khởi tạo Viewer và render PDF

```java
try (Viewer viewer = new Viewer("YOUR_DOCUMENT_DIRECTORY/SAMPLE_PST", loadOptions)) {
    PdfViewOptions options = new PdfViewOptions(pageFilePathFormat);
    viewer.view(options);
}
```

## Ứng dụng thực tiễn

- **Email Archiving:** Chuyển đổi các kho lưu trữ PST lớn thành HTML hoặc PDF có thể tìm kiếm để đáp ứng yêu cầu tuân thủ.  
- **Document Management Systems:** Lưu trữ các tệp đã chuyển đổi trong các hệ thống chỉ chấp nhận PDF, PNG hoặc JPG.  
- **Collaboration Platforms:** Chia sẻ email đã chuyển đổi dưới dạng hình ảnh trên Slack hoặc Teams.  
- **Legal Review:** Cung cấp cho tòa án các phiên bản PDF của bằng chứng email.  
- **Backup Strategies:** Giữ các bản sao PNG hoặc JPG nhẹ nhàng của các tin nhắn quan trọng.

## Các lưu ý về hiệu năng

- **Resource Management:** Tái sử dụng các instance của `Viewer` khi xử lý nhiều tệp để giảm tải.  
- **Memory Tuning:** Điều chỉnh `loadOptions.setResourceLoadingTimeout` dựa trên khả năng của server.  
- **Asynchronous Processing:** Đẩy quá trình chuyển đổi sang các luồng nền để UI phản hồi nhanh hơn.  

## Câu hỏi thường gặp

**Q: Làm thế nào để **convert pst to pdf** với cùng một mã nguồn?**  
A: Sử dụng `PdfViewOptions` như đã trình bày trong phần render PDF; phần còn lại của mã vẫn giống nhau.

**Q: GroupDocs.Viewer có thể xử lý các tệp PST được mã hóa không?**  
A: Có, cung cấp mật khẩu bằng `LoadOptions.setPassword("yourPassword")` trước khi render.

**Q: Sự khác biệt giữa **java convert pst** sang PNG và JPG là gì?**  
A: PNG giữ chất lượng không mất dữ liệu, lý tưởng cho ảnh chụp màn hình, trong khi JPG cung cấp kích thước tệp nhỏ hơn cho bản xem trước email.

**Q: Có cách nào để **how to convert pst** các tệp hàng loạt không?**  
A: Bao bọc logic render trong một vòng lặp duyệt qua thư mục chứa các tệp PST; tái sử dụng cùng cấu hình `Viewer` cho mỗi tệp.

## Kết luận

Bạn đã có một hướng dẫn đầy đủ, sẵn sàng cho môi trường production để **convert pst to html**, JPG, PNG và PDF bằng GroupDocs.Viewer cho Java. Bằng cách thực hiện các bước trên, bạn có thể tích hợp việc chuyển đổi email vào bất kỳ quy trình làm việc nào dựa trên Java, nâng cao khả năng truy cập và đáp ứng các yêu cầu tuân thủ.

---

**Cập nhật lần cuối:** 2026-02-15  
**Được kiểm tra với:** GroupDocs.Viewer for Java 25.2  
**Tác giả:** GroupDocs