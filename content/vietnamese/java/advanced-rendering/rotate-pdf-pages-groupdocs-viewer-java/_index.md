---
date: '2026-04-04'
description: Tìm hiểu cách xoay các trang PDF cụ thể bằng GroupDocs.Viewer cho Java.
  Hướng dẫn từng bước này bao gồm cài đặt Maven, xoay PDF 90 độ và khắc phục sự cố.
keywords:
- rotate specific pdf pages
- rotate pdf 90 degrees
- pdf to html java
- rotate multiple pdf pages
title: Cách xoay các trang PDF cụ thể bằng GroupDocs.Viewer cho Java
type: docs
url: /vi/java/advanced-rendering/rotate-pdf-pages-groupdocs-viewer-java/
weight: 1
---

# Cách xoay các trang PDF cụ thể bằng GroupDocs.Viewer cho Java

Việc xoay các trang cụ thể trong một tệp PDF có thể cần thiết để căn chỉnh tài liệu, sửa các hình ảnh đã quét, hoặc điều chỉnh các slide trình chiếu. **Trong hướng dẫn này bạn sẽ học cách xoay các trang pdf cụ thể một cách lập trình bằng GroupDocs.Viewer**, cho dù bạn cần xoay pdf 90 độ, lật một phần toàn bộ, hoặc xử lý nhiều trang trong một lần gọi.

![Rotate Specific PDF Pages with GroupDocs.Viewer for Java](/viewer/advanced-rendering/rotate-specific-pdf-pages-java.png)

**Bạn sẽ học**
- Cài đặt GroupDocs.Viewer trong dự án Java của bạn (bao gồm cấu hình Maven GroupDocs Viewer)
- Xoay các trang PDF cụ thể một cách lập trình (xoay pdf 90 độ, 180 độ, v.v.)
- Các cấu hình chính để sử dụng tối ưu
- Khắc phục các vấn đề thường gặp trong quá trình triển khai

## Câu trả lời nhanh
- **Thư viện nào có thể xoay các trang PDF trong Java?** GroupDocs.Viewer for Java.  
- **Tôi có thể xoay một trang đơn 90 độ không?** Yes, use `rotatePage(pageNumber, Rotation.ON_90_DEGREE)`.  
- **Tôi có cần giấy phép cho việc phát triển không?** A temporary license is available for free trial.  
- **Có cần Maven không?** Maven is the recommended way to manage GroupDocs dependencies.  
- **Làm thế nào để tôi render các trang đã xoay?** Use `HtmlViewOptions` and call `viewer.view(...)`.

## Yêu cầu trước

### Thư viện và phụ thuộc cần thiết
- Java Development Kit (JDK) 8 hoặc mới hơn.  
- Một IDE như IntelliJ IDEA hoặc Eclipse.  
- Maven để quản lý phụ thuộc.

### Yêu cầu thiết lập môi trường
1. **Cấu hình Maven** – thêm GroupDocs.Viewer vào `pom.xml` của bạn.  
2. **Nhận giấy phép** – lấy giấy phép tạm thời từ GroupDocs. Truy cập [GroupDocs Free Trial](https://releases.groupdocs.com/viewer/java/) hoặc đăng ký giấy phép tạm thời trên [GroupDocs Temporary License Page](https://purchase.groupdocs.com/temporary-license/).

## Cài đặt GroupDocs.Viewer cho Java

Để tích hợp GroupDocs.Viewer vào dự án Java của bạn bằng Maven, cập nhật `pom.xml` của bạn:

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

### Khởi tạo và Cài đặt Cơ bản
```java
Path YOUR_DOCUMENT_DIRECTORY = Path.of("YOUR_DOCUMENT_DIRECTORY");
Path YOUR_OUTPUT_DIRECTORY = Path.of("YOUR_OUTPUT_DIRECTORY");

// Format for page file paths
Path pageFilePathFormat = YOUR_OUTPUT_DIRECTORY.resolve("page_{0}.html");

HtmlViewOptions viewOptions = HtmlViewOptions.forEmbeddedResources(pageFilePathFormat);
```

## Cách xoay các trang PDF cụ thể bằng GroupDocs.Viewer
### Tổng quan
Xoay các trang PDF cụ thể cho phép bạn kiểm soát chi tiết cách trình bày tài liệu mà không làm thay đổi tệp gốc.

### Bước 1: Cấu hình xoay trang
```java
// Rotate the first page by 90 degrees clockwise.
viewOptions.rotatePage(1, Rotation.ON_90_DEGREE);

// Rotate the second page by 180 degrees.
viewOptions.rotatePage(2, Rotation.ON_180_DEGREE);
```

### Bước 2: Khởi tạo Viewer và Render
```java
Viewer viewer = new Viewer(YOUR_DOCUMENT_DIRECTORY.resolve("SampleDocument.pdf"));

// Render the specified pages (1 and 2) using the configured options.
viewer.view(viewOptions, 1, 2);

// Always close the viewer to free resources.
viewer.close();
```

#### Tham số và Cấu hình
- **Rotation** – `rotatePage(pageNumber, Rotation.*)` where the rotation options are `ON_90_DEGREE`, `ON_180_DEGREE`, `ON_270_DEGREE`.  
- **HtmlViewOptions** – Handles PDF‑to‑HTML conversion while preserving layout and embedded resources.  
- **pdf to html java** – Lớp này là một phần của cùng API và đảm bảo biểu diễn hình ảnh chính xác.

## Tại sao phải xoay các trang PDF cụ thể?
- **Document Alignment** – Correct orientation of scanned contracts or invoices.  
- **Presentation Tweaks** – Adjust slides that were exported as PDF.  
- **Archival Consistency** – Standardize page orientation during bulk digitization.

## Các vấn đề thường gặp và giải pháp (khắc phục xoay pdf)
- **Incorrect Paths** – Verify that `YOUR_DOCUMENT_DIRECTORY` and `YOUR_OUTPUT_DIRECTORY` exist and are accessible.  
- **Missing Dependencies** – Ensure the Maven coordinates match the latest GroupDocs.Viewer version.  
- **License Restrictions** – Apply the temporary license correctly; otherwise, some features may be disabled.  
- **Memory Spikes** – Render large PDFs in smaller batches or increase the JVM heap size.

## Ứng dụng thực tiễn

### Các trường hợp sử dụng thực tế
1. **Document Alignment** – Rotate scanned documents for correct digital orientation.  
2. **Presentation Adjustments** – Modify presentation slides within PDFs before sharing.  
3. **Archival Workflows** – Automatically adjust the orientation of historical documents during digitization.

### Các khả năng tích hợp
Combine GroupDocs.Viewer with Java‑based content management systems, enterprise portals, or custom APIs that require on‑the‑fly viewing of PDFs.

## Các cân nhắc về hiệu năng
- **Resource Management** – Always close the `Viewer` instance to release file handles and memory.  
- **Java Memory Management** – Monitor heap usage when processing large PDFs; consider streaming pages instead of loading the whole file.  
- **Best Practices** – Cache rendered HTML for frequently accessed documents to reduce processing time.

## Kết luận
This tutorial covered **cách xoay các trang pdf cụ thể bằng GroupDocs.Viewer trong Java**, from Maven setup to rendering rotated pages and handling common pitfalls. Experiment with additional features such as watermarking, format conversion, or batch processing to further extend your document workflow.

**Bước tiếp theo:** Khám phá các khả năng khác của GroupDocs.Viewer như chuyển đổi PDF sang PNG, thêm watermark, hoặc tích hợp với các nhà cung cấp lưu trữ đám mây.

## Phần Câu hỏi thường gặp
- **Troubleshooting Rotation Issues** – Verify page numbers and rotation parameters are correct.  
- **Handling Large PDF Files** – Process pages in batches and monitor memory usage.  
- **Licensing Requirements** – Use a temporary license for development; purchase a full license for production.  
- **Rotating Multiple Pages** – Call `rotatePage` repeatedly with different page numbers and angles.  
- **Integration with Java Libraries** – GroupDocs.Viewer works seamlessly with Spring Boot, Jakarta EE, and other Java frameworks.

## Câu hỏi thường gặp

**Q: Tôi có thể xoay tất cả các trang của một PDF cùng một lúc không?**  
A: Yes. Loop through the page numbers and call `rotatePage(page, Rotation.ON_90_DEGREE)` for each page.

**Q: Việc xoay có ảnh hưởng đến tệp PDF gốc không?**  
A: No. Rotation is applied only during the rendering process; the source PDF remains unchanged.

**Q: Nếu một PDF được bảo vệ bằng mật khẩu thì sao?**  
A: Provide the password when creating the `Viewer` instance: `new Viewer(path, password)`.

**Q: Làm thế nào để tôi debug lỗi “null pointer” khi thiết lập HtmlViewOptions?**  
A: Ensure the output directory exists and that `pageFilePathFormat` resolves correctly.

**Q: Có cách nào để xoay các trang khi chuyển đổi sang định dạng khác (ví dụ: PNG) không?**  
A: Yes. Use the same `rotatePage` configuration with the appropriate view options for the target format.

## Tài nguyên
- **Tài liệu**: [GroupDocs Viewer Documentation](https://docs.groupdocs.com/viewer/java/)  
- **Tham chiếu API**: [GroupDocs API Reference](https://reference.groupdocs.com/viewer/java/)  
- **Tải xuống**: [GroupDocs Download Page](https://releases.groupdocs.com/viewer/java/)  
- **Mua hàng**: [GroupDocs Purchase Options](https://purchase.groupdocs.com/buy)  
- **Dùng thử miễn phí**: [GroupDocs Free Trial](https://releases.groupdocs.com/viewer/java/)  
- **Yêu cầu giấy phép tạm thời**: [Request Temporary License](https://purchase.groupdocs.com/temporary-license/)  
- **Hỗ trợ**: [GroupDocs Support Forum](https://forum.groupdocs.com/c/viewer/9)

---

**Cập nhật lần cuối:** 2026-04-04  
**Kiểm tra với:** GroupDocs.Viewer 25.2 for Java  
**Tác giả:** GroupDocs