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

# Cách Xoay Trang PDF Sử dụng GroupDocs.Viewer trong Java

Việc xoay các trang cụ thể trong một tệp PDF có thể rất cần thiết để chỉnh sửa tài liệu hoặc điều chỉnh trình chiếu. **Trong hướng dẫn này, bạn sẽ học cách xoay pdf** các trang cách thiết lập với GroupDocs.Viewer, chọn dù bạn cần xoay pdf 90 độ, Cô một phần toàn bộ, hoặc xử lý nhiều trang trong một lần gọi.

![Xoay Các Trang PDF Cụ Thể với GroupDocs.Viewer cho Java](/viewer/advanced-rendering/rotate-special-pdf-page-java.png)

**Bạn Sẽ Học:**
- Cài đặt GroupDocs.Viewer trong dự án Java của bạn (bao gồm cấu hình Maven GroupDocs Viewer)
- Xoay các trang PDF cụ thể bằng cách cài đặt (xoay pdf 90 độ, 180 độ, v.v.)
- Cấu hình chính để sử dụng mức độ ưu tiên
- Khắc phục các vấn đề thường gặp trong quá trình khai báo phát triển

## Trả lời nhanh
- **Thư viện nào có thể xoay các trang PDF trong Java?** GroupDocs.Viewer cho Java.
- **Tôi có thể xoay một trang duy nhất 90 độ không?** Có, sử dụng `rotatePage(pageNumber, Rotation.ON_90_DEGREE)`.
- **Tôi có cần giấy phép để phát triển không?** Một giấy phép tạm thời có sẵn cho bản dùng thử miễn phí.
- **Có cần Maven không?** Maven là cách được đưa ra để quản lý các phụ thuộc của GroupDocs.
- **Làm thế nào để hiển thị các trang xoay?** Sử dụng `HtmlViewOptions` và gọi `viewer.view(...)`.

## Điều kiện tiên quyết

### Thư viện và thư viện phụ thuộc bắt buộc

- Bộ công cụ phát triển Java (JDK) phiên bản 8 đã được cài đặt trên máy của bạn.
- Môi trường phát triển hợp tác (IDE), giới hạn IntelliJ IDEA hoặc Eclipse.
- Maven quản lý các phụ thuộc của dự án.

### Yêu cầu thiết lập môi trường

1. **Cấu hình Maven**: Thêm GroupDocs.Viewer vào dự án Maven của bạn bằng cách bao gồm các kho và phụ thuộc cần thiết trong `pom.xml`.
2. **Lấy giấy phép**: Nhận giấy phép tạm thời từ GroupDocs, cho phép bạn khám phá tất cả các tính năng mà không bị giới hạn trong quá trình phát triển. Truy cập [Bản dùng thử miễn phí GroupDocs](https://releases.groupdocs.com/viewer/java/) hoặc đăng ký giấy phép tạm thời tại [Trang giấy phép tạm thời của GroupDocs](https://purchase.groupdocs.com/temporary-license/).

## Thiết lập GroupDocs.Viewer cho Java

Để tích hợp GroupDocs.Viewer vào dự án Java của bạn bằng Maven, hãy cập nhật `pom.xml` của bạn:

**Cấu hình Maven**
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

### Khởi tạo và thiết lập cơ bản

Khởi tạo GroupDocs.Viewer bằng cách chỉ định tài liệu thư mục và đường dẫn đầu ra của bạn:

```java
Path YOUR_DOCUMENT_DIRECTORY = Path.of("YOUR_DOCUMENT_DIRECTORY");
Path YOUR_OUTPUT_DIRECTORY = Path.of("YOUR_OUTPUT_DIRECTORY");

// Format for page file paths
Path pageFilePathFormat = YOUR_OUTPUT_DIRECTORY.resolve("page_{0}.html");

HtmlViewOptions viewOptions = HtmlViewOptions.forEmbeddedResources(pageFilePathFormat);
```

## Hướng dẫn thực hiện

### Xoay các trang cụ thể bằng GroupDocs.Viewer

**Tổng quan:** Xoay các công cụ PDF của trang để cải thiện trình bày tài liệu.

#### Bước 1: Định cấu hình Xoay trang

Xoay trang đầu tiên 90 độ và trang thứ hai 180 độ bằng cách sử dụng `HtmlViewOptions`:

```java
// Rotate the first page by 90 degrees clockwise.
viewOptions.rotatePage(1, Rotation.ON_90_DEGREE);

// Rotate the second page by 180 degrees.
viewOptions.rotatePage(2, Rotation.ON_180_DEGREE);
```

#### Bước 2: Khởi tạo Trình xem và Hiển thị

Tạo một đối tượng `Viewer` với tài liệu của bạn và render các trang đã chỉ định:

```java
Viewer viewer = new Viewer(YOUR_DOCUMENT_DIRECTORY.resolve("SampleDocument.pdf"));

// Render the specified pages (1 and 2) using the configured options.
viewer.view(viewOptions, 1, 2);

// Always close the viewer to free resources.
viewer.close();
```

### Thông số và cấu hình

- **Rotation**: Sử dụng `rotatePage` với số trang và góc xoay. Các góc xoay: `ON_90_DEGREE`, `ON_180_DEGREE`, `ON_270_DEGREE`.
- **HtmlViewOptions**: Cấu hình chuyển đổi trang PDF sang HTML, đảm bảo bao gồm các tài nguyên được nhúng.
- **pdf sang html java**: Lớp `HtmlViewOptions` xử lý công việc chuyển đổi PDF‑to‑HTML trong khi giữ nguyên bố cục.

#### Mẹo khắc phục sự cố (khắc phục sự cố xoay pdf)

- Xác định đường dẫn tới tài liệu và thư mục đầu tiên của bạn.
- Kiểm tra việc thiếu các phụ thuộc hoặc thư viện phiên bản không chính xác.
- Đảm bảo giấy được phép áp dụng đúng nếu có các chế độ giới hạn xảy ra trong thời gian thử nghiệm.
- Nếu bạn hiện bộ nhớ biến đổi tăng biểu tượng, hãy cân nhắc kết xuất các trang theo lô nhỏ hơn (xoay nhiều trang pdf tăng dần).

## Ứng dụng thực tế

### Các trường hợp sử dụng trong thế giới thực
1. **Căn chỉnh tài liệu** – Xoay tài liệu đã quét để có hướng dẫn kỹ thuật số đúng.
2. **Điều chỉnh bài thuyết trình** – Chỉnh sửa các slide trong PDF trước khi chia sẻ.
3. **Quy trình lưu trữ** – Tự động điều chỉnh hướng dẫn của tài liệu lịch trong quá trình số hóa.

### Khả năng tích hợp
Tích hợp GroupDocs.Viewer với các hệ thống quản lý tài liệu dựa trên Java, nội dung nền tảng hoặc các giải pháp doanh nghiệp tùy chỉnh yêu cầu xem khả năng tùy chỉnh.

## Cân nhắc về hiệu suất

- **Quản lý tài nguyên**: Đóng đối tượng `Viewer` để giải nén tài nguyên.
- **Quản lý bộ nhớ Java**: Giám sát việc sử dụng bộ nhớ khi kết xuất tài liệu lớn và sử dụng kết quả hiệu suất dữ liệu cấu trúc.
- **Thực hành tốt**: Sử dụng bộ nhớ đệm cho tài liệu hoặc trang được truy cập thường xuyên.

## Phần kết luận

Bài hướng dẫn này đã được **cách xoay pdf** các trang bằng GroupDocs.Viewer trong Java, từ môi trường cài đặt đến các ứng dụng thực tế. Hãy thử nghiệm các tính năng bổ sung như thêm hình mờ hoặc chuyển đổi tài liệu sang các định dạng khác.

**Bước tiếp theo:** Khám phá thêm các tính năng của GroupDocs.Viewer để nâng cao khả năng xử lý tài liệu của bạn.

## Phần Câu hỏi thường gặp

### Câu hỏi thường gặp
1. **Khắc phục các vấn đề**: Xác minh số trang và các tham số xoay chính xác.
2. **Xử lý lớn các tệp PDF**: Xử lý hiệu quả các tài liệu lớn bằng cách quản lý tài nguyên phù hợp.
3. **Yêu cầu giấy phép**: Sử dụng giấy phép tạm thời cho việc phát triển; mua giấy phép đầy đủ cho sản phẩm môi trường.
4. **Xoay nhiều trang**: Gọi `rotatePage` nhiều lần với các số trang và góc khác nhau.
5. **Sự hợp nhất với các thư viện Java**: Tích hợp GroupDocs.Viewer một cách tiếp cận các ứng dụng hoặc khung lớn hơn.

## Câu hỏi thường gặp

**Q: Tôi có thể xoay tất cả các trang của một tệp PDF cùng một lúc không?**
A: Có. Lặp lại số trang và gọi `rotatePage(page, Rotation.ON_90_DEGREE)` cho mỗi trang.

**Q: Việc xoay ảnh có ảnh hưởng đến bản gốc PDF không?**
A: Không. The xoay chỉ được áp dụng trong quá trình kết xuất; Nguồn PDF vẫn không thay đổi.

**Q: Nếu một tệp PDF được bảo vệ bằng mật khẩu thì sao?**
A: Cung cấp mật khẩu khi tạo đối tượng `Viewer`: `new Viewer(path, pass)`.

**Q: Làm cách nào để gỡ lỗi “con trỏ null” khi thiết lập HtmlViewOptions?**
A: Đảm bảo đầu thư mục tồn tại và `pageFilePathFormat` được giải quyết đúng.

**Q: Có cách nào để xoay các trang khi chuyển đổi sang định dạng khác (ví dụ: PNG) không?**
A: Sử dụng cùng cấu hình `rotatePage` với chế độ xem tùy chọn phù hợp với định dạng mục tiêu.

## Tài nguyên
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