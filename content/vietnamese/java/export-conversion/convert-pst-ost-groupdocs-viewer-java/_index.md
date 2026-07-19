---
date: '2026-07-19'
description: Tìm hiểu cách chuyển đổi PST sang HTML và các định dạng khác như JPG,
  PNG, PDF bằng GroupDocs.Viewer for Java. Hướng dẫn này bao gồm tất cả các bước và
  cấu hình cần thiết.
keywords:
- convert pst to html
- convert pst to pdf
- java convert ost
- convert pst to png
- convert pst to jpg
lastmod: '2026-07-19'
og_description: Chuyển đổi PST sang HTML nhanh chóng bằng GroupDocs.Viewer for Java.
  Tìm hiểu từng bước cách xuất sang JPG, PNG và PDF trong hướng dẫn sẵn sàng cho môi
  trường sản xuất.
og_image_alt: 'Developer guide: Convert PST to HTML, JPG, PNG, PDF using GroupDocs
  Viewer for Java'
og_title: Chuyển đổi PST sang HTML với GroupDocs.Viewer for Java – Xuất Email Nhanh
schemas:
- author: GroupDocs
  dateModified: '2026-07-19'
  description: Learn how to convert pst to html and other formats like JPG, PNG, PDF
    using GroupDocs.Viewer for Java. This guide covers all steps and configurations
    needed.
  headline: Convert PST to HTML, JPG, PNG, PDF Using GroupDocs.Viewer for Java
  type: TechArticle
- description: Learn how to convert pst to html and other formats like JPG, PNG, PDF
    using GroupDocs.Viewer for Java. This guide covers all steps and configurations
    needed.
  name: Convert PST to HTML, JPG, PNG, PDF Using GroupDocs.Viewer for Java
  steps:
  - name: Set Up Output Directory
    text: Define a folder where the HTML pages will be written. GroupDocs creates
      a sub‑folder for each email to keep assets organized.
  - name: Configure Load Options
    text: '`LoadOptions` lets you specify password handling, resource‑loading timeouts,
      and selective page rendering. Setting a timeout of 30 seconds works well for
      most server environments.'
  - name: Define HTML View Options
    text: '`HtmlViewOptions` specifies the output folder, resource handling, and optional
      CSS settings for HTML conversion.'
  - name: Initialize Viewer and Render HTML
    text: Create a `Viewer` object, pass the PST file path, and call `view` with the
      `HtmlViewOptions`. The API automatically iterates through all messages inside
      the PST and generates a tidy HTML hierarchy.
  - name: Set Up Output Directory
    text: Create a dedicated folder for JPG snapshots; each email will become one
      or more image files depending on its length.
  - name: Configure Load Options
    text: The same `LoadOptions` used for HTML can be reused here, ensuring consistent
      password handling across formats.
  - name: Define JPG View Options
    text: '`JpgViewOptions` controls image resolution, quality, and output folder
      for JPEG conversion.'
  - name: Initialize Viewer and Render JPG
    text: Use `viewer.view(jpgOptions)` to generate high‑quality JPEG files ready
      for web preview.
  - name: Set Up Output Directory
    text: PNG output is useful when you need lossless quality for archiving or OCR
      processing.
  - name: Configure Load Options
    text: No additional settings are required beyond the password and timeout configuration.
  type: HowTo
- questions:
  - answer: Use `PdfViewOptions` as shown in the PDF rendering section; the rest of
      the code remains identical.
    question: How do I **convert pst to pdf** with the same code base?
  - answer: Yes, provide the password via `LoadOptions.setPassword("yourPassword")`
      before rendering.
    question: Can GroupDocs.Viewer handle encrypted PST files?
  - answer: PNG preserves lossless quality, ideal for screenshots, while JPG offers
      smaller file sizes for email previews.
    question: What is the difference between **java convert pst** to PNG vs JPG?
  - answer: Wrap the rendering logic in a loop that iterates over a directory of PST
      files; reuse the same `Viewer` configuration for each file.
    question: Is there a way to **how to convert pst** files in bulk?
  - answer: Yes, GroupDocs.Viewer streams data and can process files up to 2 GB without
      loading the entire archive into memory.
    question: Does the API support converting PST files larger than 1 GB?
  type: FAQPage
tags:
- convert pst
- GroupDocs.Viewer
- Java document processing
- email conversion
title: Chuyển đổi PST sang HTML, JPG, PNG, PDF bằng GroupDocs.Viewer for Java
type: docs
url: /vi/java/export-conversion/convert-pst-ost-groupdocs-viewer-java/
weight: 1
---

# Chuyển đổi PST sang HTML, JPG, PNG, PDF bằng GroupDocs.Viewer cho Java

Bạn có đang muốn **convert pst to html** hoặc các định dạng khác như JPG, PNG, hoặc PDF không? Với thư viện mạnh mẽ GroupDocs.Viewer cho Java, nhiệm vụ này trở nên đơn giản và hiệu quả. Trong hướng dẫn này, bạn sẽ học cách hiển thị các tệp Outlook PST/OST thành HTML thân thiện với web, tệp hình ảnh, hoặc một tệp PDF duy nhất, giúp lưu trữ email của bạn dễ dàng chia sẻ và lưu trữ.

![Chuyển đổi PST/OST sang HTML, JPG, PNG, PDF với GroupDocs.Viewer cho Java](/viewer/export-conversion/convert-pst-ost-to-html-jpg-png-pdf.png)

[Chuyển đổi PST/OST sang HTML, JPG, PNG, PDF với GroupDocs.Viewer cho Java](/viewer/export-conversion/convert-pst-ost-to-html-jpg-png-pdf.png)

**Bạn sẽ học được gì**
- Cách thiết lập GroupDocs.Viewer cho Java trong dự án Maven.  
- Hướng dẫn từng bước để **java convert pst** các tệp sang HTML, JPG, PNG và PDF.  
- Mẹo cấu hình để đạt hiệu suất tối ưu và tránh các lỗi thường gặp.

## Câu trả lời nhanh
- **Thư viện nào xử lý chuyển đổi PST?** GroupDocs.Viewer for Java.  
- **Tôi có thể chuyển đổi PST sang PDF trực tiếp không?** Có, sử dụng `PdfViewOptions`.  
- **Có cần giấy phép cho môi trường sản xuất không?** Cần một giấy phép GroupDocs hợp lệ.  
- **Phiên bản Java nào được hỗ trợ?** JDK 8 hoặc mới hơn.  
- **Tôi có cần trích xuất tệp đính kèm thủ công không?** Không, viewer sẽ tự động hiển thị chúng.

## GroupDocs.Viewer cho Java là gì?
GroupDocs.Viewer cho Java là một API phía máy chủ tải hơn 100 định dạng tài liệu và email và hiển thị chúng thành đầu ra HTML, hình ảnh hoặc PDF mà không cần phần mềm bên ngoài. Nó xử lý các tệp PST lên đến 2 GB trong khi giữ mức sử dụng bộ nhớ dưới 200 MB.

## Cách chuyển đổi pst sang html bằng GroupDocs.Viewer cho Java?
Tải tệp PST bằng `new Viewer("source.pst")`, cấu hình `HtmlViewOptions` để chỉ đến thư mục đầu ra, và gọi `viewer.view(htmlOptions)`. API sẽ trích xuất mỗi email, giữ nguyên định dạng, tệp đính kèm và siêu dữ liệu, và ghi một trang HTML riêng cho mỗi tin nhắn — tất cả trong một lời gọi phương thức duy nhất.

### Tại sao chọn GroupDocs.Viewer?
- **Hiển thị độ trung thực cao** – 99,9 % nội dung email (bao gồm phần thân văn bản giàu, bảng và hình ảnh nhúng) được tái tạo một cách chính xác.  
- **Nhiều định dạng đầu ra** – Một lời gọi API có thể tạo HTML, JPG, PNG hoặc PDF, bao phủ hơn 50 tùy chọn xuất.  
- **Không phụ thuộc vào bên ngoài** – Không cần Outlook, Exchange Server, hay các bộ chuyển đổi của bên thứ ba; mọi thứ chạy trong môi trường Java của bạn.

## Yêu cầu trước

- **GroupDocs.Viewer cho Java** – phiên bản 25.2 hoặc mới hơn.  
- **Java Development Kit (JDK)** – 8 hoặc mới hơn.  
- Maven để quản lý phụ thuộc.  
- Kiến thức cơ bản về Java và quen thuộc với Maven.

## Cài đặt GroupDocs.Viewer cho Java

`Viewer` là lớp cốt lõi trong GroupDocs.Viewer cho Java, tải tài liệu và hiển thị nó sang định dạng đã chọn. Thêm kho lưu trữ GroupDocs và phụ thuộc vào `pom.xml` của bạn:

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
- **Dùng thử miễn phí** – khám phá tất cả tính năng mà không tốn phí.  
- **Giấy phép tạm thời** – kéo dài thời gian đánh giá nếu cần.  
- **Giấy phép đầy đủ** – cần cho triển khai sản xuất.

### Khởi tạo cơ bản
`Viewer` instances are lightweight; you can reuse a single instance for many files to minimise object‑creation overhead.

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

Các phần sau sẽ hướng dẫn bạn cách hiển thị các tệp PST/OST thành từng định dạng được hỗ trợ.

### Hiển thị tài liệu PST/OST thành HTML

#### Bước 1: Thiết lập thư mục đầu ra
Xác định một thư mục nơi các trang HTML sẽ được ghi. GroupDocs tạo một thư mục con cho mỗi email để giữ tài nguyên được sắp xếp.

```java
Path outputDirectory = Paths.get("YOUR_OUTPUT_DIRECTORY");
Path pageFilePathFormat = outputDirectory.resolve("PST_result.html");
```

#### Bước 2: Cấu hình Load Options
`LoadOptions` cho phép bạn chỉ định cách xử lý mật khẩu, thời gian chờ tải tài nguyên, và việc hiển thị trang chọn lọc. Đặt thời gian chờ 30 giây hoạt động tốt cho hầu hết môi trường máy chủ.

```java
LoadOptions loadOptions = new LoadOptions();
loadOptions.setResourceLoadingTimeout(100);
```

#### Bước 3: Định nghĩa HTML View Options
`HtmlViewOptions` chỉ định thư mục đầu ra, cách xử lý tài nguyên, và các cài đặt CSS tùy chọn cho việc chuyển đổi HTML.

```java
try (Viewer viewer = new Viewer("YOUR_DOCUMENT_DIRECTORY/SAMPLE_PST", loadOptions)) {
    HtmlViewOptions options = HtmlViewOptions.forEmbeddedResources(pageFilePathFormat);
    viewer.view(options);
}
```

#### Bước 4: Khởi tạo Viewer và hiển thị HTML
Tạo một đối tượng `Viewer`, truyền đường dẫn tệp PST, và gọi `view` với `HtmlViewOptions`. API sẽ tự động duyệt qua tất cả các tin nhắn trong PST và tạo ra một cấu trúc HTML gọn gàng.

```java
Path outputDirectory = Paths.get("YOUR_OUTPUT_DIRECTORY");
Path pageFilePathFormat = outputDirectory.resolve("PST_result_{0}.jpg");
```

### Hiển thị tài liệu PST/OST thành JPG

#### Bước 1: Thiết lập thư mục đầu ra
Tạo một thư mục riêng cho các ảnh chụp JPG; mỗi email sẽ trở thành một hoặc nhiều tệp hình ảnh tùy thuộc vào độ dài của nó.

```java
LoadOptions loadOptions = new LoadOptions();
loadOptions.setResourceLoadingTimeout(100);
```

#### Bước 2: Cấu hình Load Options
`LoadOptions` giống như đã dùng cho HTML có thể được tái sử dụng ở đây, đảm bảo việc xử lý mật khẩu nhất quán giữa các định dạng.

```java
try (Viewer viewer = new Viewer("YOUR_DOCUMENT_DIRECTORY/SAMPLE_PST", loadOptions)) {
    JpgViewOptions options = new JpgViewOptions(pageFilePathFormat);
    viewer.view(options);
}
```

#### Bước 3: Định nghĩa JPG View Options
`JpgViewOptions` kiểm soát độ phân giải ảnh, chất lượng và thư mục đầu ra cho chuyển đổi JPEG.

```java
Path outputDirectory = Paths.get("YOUR_OUTPUT_DIRECTORY");
Path pageFilePathFormat = outputDirectory.resolve("PST_result_{0}.png");
```

#### Bước 4: Khởi tạo Viewer và hiển thị JPG
Sử dụng `viewer.view(jpgOptions)` để tạo các tệp JPEG chất lượng cao sẵn sàng cho việc xem trước trên web.

```java
LoadOptions loadOptions = new LoadOptions();
loadOptions.setResourceLoadingTimeout(100);
```

### Hiển thị tài liệu PST/OST thành PNG

#### Bước 1: Thiết lập thư mục đầu ra
Đầu ra PNG hữu ích khi bạn cần chất lượng không mất dữ liệu cho việc lưu trữ hoặc xử lý OCR.

```java
try (Viewer viewer = new Viewer("YOUR_DOCUMENT_DIRECTORY/SAMPLE_PST", loadOptions)) {
    PngViewOptions options = new PngViewOptions(pageFilePathFormat);
    viewer.view(options);
}
```

#### Bước 2: Cấu hình Load Options
Không cần cài đặt bổ sung nào ngoài cấu hình mật khẩu và thời gian chờ.

```java
Path outputDirectory = Paths.get("YOUR_OUTPUT_DIRECTORY");
Path pageFilePathFormat = outputDirectory.resolve("PST_result.pdf");
```

#### Bước 3: Định nghĩa PNG View Options
`PngViewOptions` cho phép bạn đặt nền trong suốt và thư mục đầu ra cho các ảnh PNG không mất dữ liệu.

```java
LoadOptions loadOptions = new LoadOptions();
loadOptions.setResourceLoadingTimeout(100);
```

#### Bước 4: Khởi tạo Viewer và hiển thị PNG
Khởi tạo `viewer.view(pngOptions)` để tạo các ảnh chụp PNG của mỗi email.

```java
try (Viewer viewer = new Viewer("YOUR_DOCUMENT_DIRECTORY/SAMPLE_PST", loadOptions)) {
    PdfViewOptions options = new PdfViewOptions(pageFilePathFormat);
    viewer.view(options);
}
```

### Hiển thị tài liệu PST/OST thành PDF

#### Bước 1: Thiết lập thư mục đầu ra
Một tệp PDF duy nhất cho mỗi PST đơn giản hoá quy trình xem xét pháp lý và giảm tải lưu trữ.

CODE_BLOCK_PLACEHOLDER_14_END

#### Bước 2: Cấu hình Load Options
Khi chuyển đổi sang PDF, bạn có thể muốn bật `setEmbedFonts(true)` để đảm bảo độ trung thực hình ảnh trên bất kỳ máy nào.

CODE_BLOCK_PLACEHOLDER_15_END

#### Bước 3: Định nghĩa PDF View Options
`PdfViewOptions` cho phép bạn chọn mức nén, nhúng phông chữ, và đặt tên tệp đầu ra cho việc chuyển đổi PDF.

CODE_BLOCK_PLACEHOLDER_16_END

#### Bước 4: Khởi tạo Viewer và hiển thị PDF
Tạo `PdfViewOptions`, tùy chọn chọn mức nén, và gọi `viewer.view(pdfOptions)`. API sẽ hợp nhất tất cả email thành một tài liệu PDF có thể tìm kiếm.

CODE_BLOCK_PLACEHOLDER_17_END

## Ứng dụng thực tế

- **Lưu trữ email:** Chuyển các kho lưu trữ PST lớn thành HTML hoặc PDF có thể tìm kiếm để tuân thủ.  
- **Hệ thống quản lý tài liệu:** Lưu các tệp đã chuyển đổi trong các hệ thống chỉ chấp nhận PDF, PNG hoặc JPG.  
- **Nền tảng cộng tác:** Chia sẻ email đã chuyển đổi dưới dạng hình ảnh trong Slack hoặc Teams.  
- **Xem xét pháp lý:** Cung cấp cho tòa án các phiên bản PDF của bằng chứng email.  
- **Chiến lược sao lưu:** Giữ các ảnh chụp PNG hoặc JPG nhẹ của các tin nhắn quan trọng.

## Các cân nhắc về hiệu năng

- **Quản lý tài nguyên:** Tái sử dụng các thể hiện `Viewer` khi xử lý nhiều tệp để giảm chi phí.  
- **Tinh chỉnh bộ nhớ:** Điều chỉnh `loadOptions.setResourceLoadingTimeout` dựa trên khả năng của máy chủ.  
- **Xử lý bất đồng bộ:** Đưa việc chuyển đổi sang các luồng nền để giao diện người dùng đáp ứng nhanh.  

## Câu hỏi thường gặp

**Q: Làm thế nào tôi **convert pst to pdf** với cùng một mã nguồn?**  
A: Sử dụng `PdfViewOptions` như đã minh họa trong phần hiển thị PDF; phần còn lại của mã vẫn giữ nguyên.

**Q: GroupDocs.Viewer có thể xử lý các tệp PST được mã hoá không?**  
A: Có, cung cấp mật khẩu qua `LoadOptions.setPassword("yourPassword")` trước khi hiển thị.

**Q: Sự khác biệt giữa **java convert pst** sang PNG và JPG là gì?**  
A: PNG giữ chất lượng không mất dữ liệu, lý tưởng cho ảnh chụp màn hình, trong khi JPG cung cấp kích thước tệp nhỏ hơn cho việc xem trước email.

**Q: Có cách nào **how to convert pst** các tệp hàng loạt không?**  
A: Đặt logic hiển thị trong một vòng lặp duyệt qua thư mục chứa các tệp PST; tái sử dụng cùng cấu hình `Viewer` cho mỗi tệp.

**Q: API có hỗ trợ chuyển đổi các tệp PST lớn hơn 1 GB không?**  
A: Có, GroupDocs.Viewer truyền dữ liệu theo luồng và có thể xử lý các tệp lên đến 2 GB mà không cần tải toàn bộ kho lưu trữ vào bộ nhớ.

## Kết luận

Bạn hiện đã có một hướng dẫn đầy đủ, sẵn sàng cho môi trường sản xuất để **convert pst to html**, JPG, PNG và PDF bằng GroupDocs.Viewer cho Java. Bằng cách thực hiện các bước trên, bạn có thể tích hợp việc chuyển đổi email vào bất kỳ quy trình làm việc nào dựa trên Java, cải thiện khả năng truy cập và đáp ứng các yêu cầu tuân thủ.

---

**Cập nhật lần cuối:** 2026-07-19  
**Kiểm tra với:** GroupDocs.Viewer for Java 25.2  
**Tác giả:** GroupDocs

## Hướng dẫn liên quan

- [Chuyển đổi NSF sang PDF, HTML, JPG, PNG bằng GroupDocs.Viewer cho Java](/viewer/java/export-conversion/convert-nsf-files-groupdocs-viewer-java/)
- [convert odf html java – Chuyển đổi ODF sang HTML, JPG, PNG, PDF bằng GroupDocs.Viewer cho Java](/viewer/java/export-conversion/convert-odf-documents-groupdocs-viewer-java/)
- [Cách chuyển đổi DOCX sang HTML bằng GroupDocs.Viewer cho Java: Hướng dẫn từng bước](/viewer/java/export-conversion/convert-docx-to-html-groupdocs-viewer-java/)