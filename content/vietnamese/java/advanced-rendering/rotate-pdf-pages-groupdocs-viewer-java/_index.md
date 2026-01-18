---
date: '2026-01-18'
description: Tìm hiểu cách xoay các trang PDF với GroupDocs.Viewer cho Java. Hướng
  dẫn từng bước này bao gồm cài đặt Maven, xoay trang (bao gồm xoay PDF 90 độ) và
  khắc phục sự cố.
keywords:
- rotate PDF pages Java
- GroupDocs.Viewer setup Java
- programmatically rotate PDF Java
title: Cách xoay các trang PDF bằng GroupDocs.Viewer trong Java – Hướng dẫn toàn diện
type: docs
url: /vi/java/advanced-rendering/rotate-pdf-pages-groupdocs-viewer-java/
weight: 1
---

# Cách Xoay Các Trang PDF Sử Dụng GroupDocs.Viewer trong Java

Việc xoay các trang cụ thể trong một tệp PDF có thể rất cần thiết để căn chỉnh tài liệu hoặc điều chỉnh các slide thuyết trình. **Trong hướng dẫn này bạn sẽ học cách xoay pdf** các trang một cách lập trình với GroupDocs.Viewer, cho dù bạn cần xoay pdf 90 độ, lật một phần toàn bộ, hoặc xử lý nhiều trang trong một lần gọi.

![Xoay Các Trang PDF Cụ Thể với GroupDocs.Viewer cho Java](/viewer/advanced-rendering/rotate-specific-pdf-pages-java.png)

**Bạn Sẽ Học:**
- Cài đặt GroupDocs.Viewer trong dự án Java của bạn (bao gồm cấu hình Maven GroupDocs Viewer)
- Xoay các trang PDF cụ thể một cách lập trình (xoay pdf 90 độ, 180 độ, v.v.)
- Các cấu hình chính để sử dụng tối ưu
- Khắc phục các vấn đề thường gặp trong quá trình triển khai

## Quick Answers
- **Thư viện nào có thể xoay các trang PDF trong Java?** GroupDocs.Viewer cho Java.
- **Tôi có thể xoay một trang duy nhất 90 độ không?** Có, sử dụng `rotatePage(pageNumber, Rotation.ON_90_DEGREE)`.
- **Tôi có cần giấy phép cho việc phát triển không?** Một giấy phép tạm thời có sẵn cho bản dùng thử miễn phí.
- **Có cần Maven không?** Maven là cách được khuyến nghị để quản lý các phụ thuộc của GroupDocs.
- **Làm thế nào để render các trang đã xoay?** Sử dụng `HtmlViewOptions` và gọi `viewer.view(...)`.

## Prerequisites

### Required Libraries and Dependencies

- Bộ công cụ phát triển Java (JDK) phiên bản 8 trở lên đã được cài đặt trên máy của bạn.
- Môi trường phát triển tích hợp (IDE), chẳng hạn IntelliJ IDEA hoặc Eclipse.
- Maven để quản lý các phụ thuộc của dự án.

### Environment Setup Requirements

1. **Cấu hình Maven**: Thêm GroupDocs.Viewer vào dự án Maven của bạn bằng cách bao gồm các kho và phụ thuộc cần thiết trong `pom.xml`.
2. **Lấy giấy phép**: Nhận giấy phép tạm thời từ GroupDocs, cho phép bạn khám phá tất cả các tính năng mà không bị giới hạn trong quá trình phát triển. Truy cập [GroupDocs Free Trial](https://releases.groupdocs.com/viewer/java/) hoặc đăng ký giấy phép tạm thời tại [GroupDocs Temporary License Page](https://purchase.groupdocs.com/temporary-license/).

## Setting Up GroupDocs.Viewer for Java

Để tích hợp GroupDocs.Viewer vào dự án Java của bạn bằng Maven, cập nhật `pom.xml` của bạn:

**Maven Configuration**
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

### Basic Initialization and Setup

Khởi tạo GroupDocs.Viewer bằng cách chỉ định thư mục tài liệu và đường dẫn đầu ra của bạn:

```java
Path YOUR_DOCUMENT_DIRECTORY = Path.of("YOUR_DOCUMENT_DIRECTORY");
Path YOUR_OUTPUT_DIRECTORY = Path.of("YOUR_OUTPUT_DIRECTORY");

// Format for page file paths
Path pageFilePathFormat = YOUR_OUTPUT_DIRECTORY.resolve("page_{0}.html");

HtmlViewOptions viewOptions = HtmlViewOptions.forEmbeddedResources(pageFilePathFormat);
```

## Implementation Guide

### Rotating Specific Pages with GroupDocs.Viewer

**Tổng quan:** Xoay các trang PDF cụ thể để cải thiện việc trình bày tài liệu.

#### Step 1: Configure Page Rotation

Xoay trang đầu tiên 90 độ và trang thứ hai 180 độ bằng cách sử dụng `HtmlViewOptions`:

```java
// Rotate the first page by 90 degrees clockwise.
viewOptions.rotatePage(1, Rotation.ON_90_DEGREE);

// Rotate the second page by 180 degrees.
viewOptions.rotatePage(2, Rotation.ON_180_DEGREE);
```

#### Step 2: Initialize Viewer and Render

Tạo một đối tượng `Viewer` với tài liệu của bạn và render các trang đã chỉ định:

```java
Viewer viewer = new Viewer(YOUR_DOCUMENT_DIRECTORY.resolve("SampleDocument.pdf"));

// Render the specified pages (1 and 2) using the configured options.
viewer.view(viewOptions, 1, 2);

// Always close the viewer to free resources.
viewer.close();
```

### Parameters and Configuration

- **Rotation**: Sử dụng `rotatePage` với số trang và góc xoay. Các góc xoay khả dụng: `ON_90_DEGREE`, `ON_180_DEGREE`, `ON_270_DEGREE`.
- **HtmlViewOptions**: Cấu hình chuyển đổi trang PDF sang HTML, đảm bảo các tài nguyên nhúng được bao gồm.
- **pdf to html java**: Lớp `HtmlViewOptions` xử lý việc chuyển đổi PDF‑to‑HTML trong khi giữ nguyên bố cục.

#### Troubleshooting Tips (troubleshoot pdf rotation)

- Xác minh đường dẫn tới tài liệu và thư mục đầu ra của bạn.
- Kiểm tra các phụ thuộc bị thiếu hoặc phiên bản thư viện không đúng.
- Đảm bảo giấy phép được áp dụng đúng nếu có các hạn chế tính năng xảy ra trong thời gian dùng thử.
- Nếu bạn gặp hiện tượng tăng đột biến bộ nhớ, hãy cân nhắc render các trang theo lô nhỏ hơn (xoay nhiều trang pdf dần dần).

## Practical Applications

### Real‑world Use Cases
1. **Căn chỉnh tài liệu** – Xoay tài liệu đã quét để có hướng kỹ thuật số đúng.
2. **Điều chỉnh bài thuyết trình** – Sửa đổi các slide trong PDF trước khi chia sẻ.
3. **Quy trình lưu trữ** – Tự động điều chỉnh hướng của tài liệu lịch sử trong quá trình số hoá.

### Integration Possibilities
Tích hợp GroupDocs.Viewer với các hệ thống quản lý tài liệu dựa trên Java, nền tảng nội dung, hoặc các giải pháp doanh nghiệp tùy chỉnh yêu cầu khả năng xem động.

## Performance Considerations

- **Quản lý tài nguyên**: Đóng đối tượng `Viewer` để giải phóng tài nguyên.
- **Quản lý bộ nhớ Java**: Giám sát việc sử dụng bộ nhớ khi render tài liệu lớn và sử dụng các cấu trúc dữ liệu hiệu quả.
- **Thực hành tốt**: Sử dụng bộ nhớ đệm cho các tài liệu hoặc trang được truy cập thường xuyên.

## Conclusion

Bài hướng dẫn này đã đề cập **cách xoay pdf** các trang bằng GroupDocs.Viewer trong Java, từ cài đặt môi trường đến các ứng dụng thực tiễn. Hãy thử nghiệm các chức năng bổ sung như thêm watermark hoặc chuyển đổi tài liệu sang các định dạng khác.

**Bước tiếp theo:** Khám phá thêm các tính năng của GroupDocs.Viewer để nâng cao khả năng xử lý tài liệu của bạn.

## FAQ Section

### Common Questions
1. **Khắc phục các vấn đề xoay**: Xác minh số trang và các tham số xoay là chính xác.
2. **Xử lý các tệp PDF lớn**: Xử lý hiệu quả các tài liệu lớn với quản lý tài nguyên phù hợp.
3. **Yêu cầu giấy phép**: Sử dụng giấy phép tạm thời cho việc phát triển; mua giấy phép đầy đủ cho môi trường sản xuất.
4. **Xoay nhiều trang**: Gọi `rotatePage` nhiều lần với các số trang và góc khác nhau.
5. **Tích hợp với các thư viện Java**: Tích hợp GroupDocs.Viewer một cách liền mạch trong các ứng dụng hoặc khung lớn hơn.

## Frequently Asked Questions

**Q: Tôi có thể xoay tất cả các trang của một PDF cùng một lúc không?**  
A: Có. Lặp qua các số trang và gọi `rotatePage(page, Rotation.ON_90_DEGREE)` cho mỗi trang.

**Q: Việc xoay có ảnh hưởng đến tệp PDF gốc không?**  
A: Không. Việc xoay chỉ được áp dụng trong quá trình render; PDF nguồn vẫn không thay đổi.

**Q: Nếu một PDF được bảo vệ bằng mật khẩu thì sao?**  
A: Cung cấp mật khẩu khi tạo đối tượng `Viewer`: `new Viewer(path, password)`.

**Q: Làm thế nào để gỡ lỗi lỗi “null pointer” khi thiết lập HtmlViewOptions?**  
A: Đảm bảo thư mục đầu ra tồn tại và `pageFilePathFormat` được giải quyết đúng.

**Q: Có cách nào để xoay các trang khi chuyển đổi sang định dạng khác (ví dụ: PNG) không?**  
A: Sử dụng cùng cấu hình `rotatePage` với các tùy chọn view phù hợp cho định dạng đích.

## Resources
- **Tài liệu**: [GroupDocs Viewer Documentation](https://docs.groupdocs.com/viewer/java/)
- **Tham chiếu API**: [GroupDocs API Reference](https://reference.groupdocs.com/viewer/java/)
- **Tải xuống**: [GroupDocs Download Page](https://releases.groupdocs.com/viewer/java/)
- **Mua hàng**: [GroupDocs Purchase Options](https://purchase.groupdocs.com/buy)
- **Dùng thử miễn phí**: [GroupDocs Free Trial](https://releases.groupdocs.com/viewer/java/)
- **Giấy phép tạm thời**: [Request Temporary License](https://purchase.groupdocs.com/temporary-license/)
- **Hỗ trợ**: [GroupDocs Support Forum](https://forum.groupdocs.com/c/viewer/9)

---

**Cập nhật lần cuối:** 2026-01-18  
**Đã kiểm tra với:** GroupDocs.Viewer 25.2 cho Java  
**Tác giả:** GroupDocs