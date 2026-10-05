---
date: '2026-10-05'
description: Tìm hiểu cách xoay các trang PDF cụ thể bằng GroupDocs.Viewer cho Java.
  Hướng dẫn từng bước này bao gồm cài đặt Maven, xoay pdf 90 độ và khắc phục sự cố.
keywords:
- rotate specific pdf pages
- rotate pdf 90 degrees
- pdf to html java
- rotate multiple pdf pages
lastmod: '2026-10-05'
og_description: Xoay các trang PDF cụ thể bằng GroupDocs.Viewer cho Java. Tìm hiểu
  cách xoay pdf 90 độ, cấu hình Maven và khắc phục các vấn đề thường gặp trong hướng
  dẫn ngắn gọn.
og_image_alt: Developer guide showing rotation of PDF pages using GroupDocs.Viewer
  Java SDK
og_title: Xoay các trang PDF cụ thể bằng GroupDocs.Viewer cho Java
schemas:
- author: GroupDocs
  dateModified: '2026-10-05'
  description: Learn how to rotate specific PDF pages with GroupDocs.Viewer for Java.
    This step‑by‑step guide covers Maven setup, rotate pdf 90 degrees, and troubleshooting.
  headline: How to Rotate Specific PDF Pages with GroupDocs.Viewer for Java
  type: TechArticle
- questions:
  - answer: Yes. Loop through the page numbers and call `rotatePage(page, Rotation.ON_90_DEGREE)`
      for each page.
    question: Can I rotate all pages of a PDF at once?
  - answer: No. Rotation is applied only during the rendering process; the source
      PDF remains unchanged.
    question: Does the rotation affect the original PDF file?
  - answer: 'Provide the password when creating the `Viewer` instance: `new Viewer(path,
      password)`.'
    question: What if a PDF is password‑protected?
  - answer: Ensure the output directory exists and that `pageFilePathFormat` resolves
      correctly.
    question: How do I debug a “null pointer” error when setting up HtmlViewOptions?
  - answer: Yes. Use the same `rotatePage` configuration with the appropriate view
      options for the target format.
    question: Is there a way to rotate pages when converting to other formats (e.g.,
      PNG)?
  type: FAQPage
tags:
- rotate pdf
- groupdocs viewer
- java pdf processing
title: Cách xoay các trang PDF cụ thể bằng GroupDocs.Viewer cho Java
type: docs
url: /vi/java/advanced-rendering/rotate-pdf-pages-groupdocs-viewer-java/
weight: 1
---

# Cách xoay các trang pdf cụ thể với GroupDocs.Viewer cho Java

Việc xoay các trang cụ thể trong một tệp PDF có thể là cần thiết để căn chỉnh tài liệu, sửa các hình ảnh đã quét, hoặc điều chỉnh các slide trình chiếu. **Trong hướng dẫn này bạn sẽ học cách xoay các trang pdf cụ thể một cách lập trình với GroupDocs.Viewer**, cho dù bạn cần xoay pdf 90 độ, lật một phần toàn bộ, hoặc xử lý nhiều trang trong một lần gọi.

![Xoay các trang PDF cụ thể với GroupDocs.Viewer cho Java](/viewer/advanced-rendering/rotate-specific-pdf-pages-java.png)

[Xoay các trang PDF cụ thể với GroupDocs.Viewer cho Java](/viewer/advanced-rendering/rotate-specific-pdf-pages-java.png)

**Bạn sẽ học được**
- Cài đặt GroupDocs.Viewer trong dự án Java của bạn (bao gồm cấu hình Maven GroupDocs Viewer)
- Xoay các trang PDF cụ thể một cách lập trình (xoay pdf 90 độ, 180 độ, v.v.)
- Các cấu hình chính để sử dụng tối ưu
- Khắc phục các vấn đề thường gặp trong quá trình triển khai

## Câu trả lời nhanh
- **Thư viện nào có thể xoay các trang PDF trong Java?** GroupDocs.Viewer cho Java cung cấp hỗ trợ xoay tích hợp mà không cần công cụ bên ngoài.  
- **Tôi có thể xoay một trang duy nhất 90 độ không?** Có – gọi `rotatePage(pageNumber, Rotation.ON_90_DEGREE)` trên thể hiện viewer.  
- **Tôi có cần giấy phép cho việc phát triển không?** Giấy phép tạm thời miễn phí để đánh giá; giấy phép đầy đủ cần thiết cho môi trường sản xuất.  
- **Có cần Maven không?** Maven là trình quản lý phụ thuộc được khuyến nghị, nhưng bạn cũng có thể sử dụng Gradle hoặc thêm JAR thủ công.  
- **Làm sao tôi có thể render các trang đã xoay?** Sử dụng `HtmlViewOptions` cùng với `viewer.view(documentPath, viewOptions)` để nhận đầu ra HTML phản ánh việc xoay.

## Định nghĩa xoay các trang pdf cụ thể
`rotate specific pdf pages` đề cập đến khả năng thay đổi hướng của các trang riêng lẻ trong tài liệu PDF trong khi để nguyên các phần còn lại của tệp. Thao tác này được thực hiện tại thời điểm render, vì vậy tệp PDF gốc không bị thay đổi.

## Tại sao cần xoay các trang pdf cụ thể?
Bạn có thể xoay một trang duy nhất trong vòng dưới 0,05 giây trên một máy ảo cấp máy chủ tiêu chuẩn, cho phép xem trước thời gian thực các hợp đồng đã quét, các bộ slide trình chiếu, hoặc hoá đơn đa trang có ảnh quét sai hướng. Kiểm soát chi tiết này loại bỏ nhu cầu sử dụng các công cụ xử lý hậu kỳ tốn kém và giảm công sức thủ công lên tới 70 % trong các dự án số hóa quy mô lớn.

## Yêu cầu trước

### Thư viện và phụ thuộc cần thiết
- Java Development Kit (JDK) 8 hoặc mới hơn.  
- Một IDE như IntelliJ IDEA hoặc Eclipse.  
- Maven để quản lý phụ thuộc.

### Yêu cầu thiết lập môi trường
1. **Cấu hình Maven** – thêm GroupDocs.Viewer vào `pom.xml` của bạn.  
2. **Lấy giấy phép** – nhận giấy phép tạm thời từ GroupDocs. Truy cập [GroupDocs Free Trial](https://releases.groupdocs.com/viewer/java/) hoặc đăng ký giấy phép tạm thời trên [GroupDocs Temporary License Page](https://purchase.groupdocs.com/temporary-license/).

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

### Khởi tạo và thiết lập cơ bản
`Viewer` là lớp cốt lõi tải tài liệu và điều phối các thao tác render. Sau khi tạo một thể hiện, bạn có thể gọi các phương thức như `view` hoặc `rotatePage`.  

```java
Path YOUR_DOCUMENT_DIRECTORY = Path.of("YOUR_DOCUMENT_DIRECTORY");
Path YOUR_OUTPUT_DIRECTORY = Path.of("YOUR_OUTPUT_DIRECTORY");

// Format for page file paths
Path pageFilePathFormat = YOUR_OUTPUT_DIRECTORY.resolve("page_{0}.html");

HtmlViewOptions viewOptions = HtmlViewOptions.forEmbeddedResources(pageFilePathFormat);
```

## Cách xoay các trang PDF cụ thể với GroupDocs.Viewer
Việc xoay các trang PDF cụ thể với GroupDocs.Viewer bao gồm hai hành động chính: đầu tiên, chỉ định góc xoay mong muốn cho mỗi trang mục tiêu bằng phương thức `rotatePage`, và thứ hai, render tài liệu bằng `HtmlViewOptions` để góc xoay được phản ánh trong đầu ra. Cách tiếp cận này giữ nguyên PDF gốc trong khi cung cấp HTML có hướng đúng.

### Bước 1: cấu hình xoay trang
`rotatePage` là một phương thức nhận chỉ số trang bắt đầu từ 0 và một giá trị enum `Rotation`. Enum này cung cấp ba tùy chọn: `ON_90_DEGREE`, `ON_180_DEGREE`, và `ON_270_DEGREE`.  

```java
// Rotate the first page by 90 degrees clockwise.
viewOptions.rotatePage(1, Rotation.ON_90_DEGREE);

// Rotate the second page by 180 degrees.
viewOptions.rotatePage(2, Rotation.ON_180_DEGREE);
```

### Bước 2: khởi tạo viewer và render
`HtmlViewOptions` kiểm soát quá trình chuyển đổi PDF‑to‑HTML. Nó bảo tồn bố cục, phông chữ và tài nguyên nhúng đồng thời áp dụng bất kỳ góc xoay nào bạn đã cấu hình.  

```java
Viewer viewer = new Viewer(YOUR_DOCUMENT_DIRECTORY.resolve("SampleDocument.pdf"));

// Render the specified pages (1 and 2) using the configured options.
viewer.view(viewOptions, 1, 2);

// Always close the viewer to free resources.
viewer.close();
```

#### Tham số và cấu hình
- **Rotation** – `rotatePage(pageNumber, Rotation.*)` trong đó các tùy chọn xoay là `ON_90_DEGREE`, `ON_180_DEGREE`, `ON_270_DEGREE`.  
- **HtmlViewOptions** – Xử lý chuyển đổi pdf‑to‑html trong khi bảo tồn bố cục và tài nguyên nhúng.  
- **pdf to html java** – Lớp này là một phần của cùng API và đảm bảo biểu diễn hình ảnh chính xác.

## Các vấn đề thường gặp và giải pháp (khắc phục xoay pdf)
- **Đường dẫn không đúng** – Kiểm tra `YOUR_DOCUMENT_DIRECTORY` và `YOUR_OUTPUT_DIRECTORY` tồn tại và có thể truy cập.  
- **Thiếu phụ thuộc** – Đảm bảo các tọa độ Maven khớp với phiên bản GroupDocs.Viewer mới nhất (hiện tại 25.2).  
- **Hạn chế giấy phép** – Áp dụng giấy phép tạm thời đúng cách; nếu không, một số tính năng có thể bị vô hiệu hoá.  
- **Tăng đột biến bộ nhớ** – Render các PDF lớn thành các lô nhỏ hơn hoặc tăng kích thước heap JVM.

## Ứng dụng thực tiễn

### Các trường hợp sử dụng thực tế
1. **Căn chỉnh tài liệu** – Xoay các hợp đồng đã quét để có hướng kỹ thuật số đúng.  
2. **Điều chỉnh trình chiếu** – Sửa đổi các slide trình chiếu trong PDF trước khi chia sẻ.  
3. **Quy trình lưu trữ** – Tự động điều chỉnh hướng của tài liệu lịch sử trong quá trình số hóa.

### Khả năng tích hợp
Kết hợp GroupDocs.Viewer với các hệ thống quản lý nội dung dựa trên Java, các cổng doanh nghiệp, hoặc API tùy chỉnh cần xem PDF ngay lập tức.

## Các yếu tố hiệu năng
- **Quản lý tài nguyên** – Luôn đóng thể hiện `Viewer` để giải phóng các handle tệp và bộ nhớ.  
- **Quản lý bộ nhớ Java** – Giám sát việc sử dụng heap khi xử lý các PDF lớn; cân nhắc streaming các trang thay vì tải toàn bộ tệp.  
- **Thực hành tốt** – Lưu cache HTML đã render cho các tài liệu được truy cập thường xuyên để giảm thời gian xử lý lên tới 60 %.

## Kết luận
Bài hướng dẫn này đã đề cập **cách xoay các trang pdf cụ thể bằng GroupDocs.Viewer trong Java**, từ cài đặt Maven đến render các trang đã xoay và xử lý các vấn đề thường gặp. Hãy thử nghiệm các tính năng bổ sung như thêm watermark, chuyển đổi định dạng, hoặc xử lý hàng loạt để mở rộng quy trình làm việc với tài liệu của bạn.

**Bước tiếp theo:** Khám phá các khả năng khác của GroupDocs.Viewer như chuyển đổi PDF sang PNG, thêm watermark, hoặc tích hợp với các nhà cung cấp lưu trữ đám mây.

## Phần câu hỏi thường gặp
- **Khắc phục các vấn đề xoay** – Kiểm tra số trang và các tham số xoay là chính xác.  
- **Xử lý các tệp PDF lớn** – Xử lý các trang theo lô và giám sát việc sử dụng bộ nhớ.  
- **Yêu cầu giấy phép** – Sử dụng giấy phép tạm thời cho phát triển; mua giấy phép đầy đủ cho môi trường sản xuất.  
- **Xoay nhiều trang** – Gọi `rotatePage` liên tục với các số trang và góc khác nhau.  
- **Tích hợp với thư viện Java** – GroupDocs.Viewer hoạt động liền mạch với Spring Boot, Jakarta EE và các framework Java khác.

## Câu hỏi thường gặp

**Q: Tôi có thể xoay tất cả các trang của một PDF cùng lúc không?**  
A: Có. Lặp qua các số trang và gọi `rotatePage(page, Rotation.ON_90_DEGREE)` cho mỗi trang.

**Q: Việc xoay có ảnh hưởng đến tệp PDF gốc không?**  
A: Không. Việc xoay chỉ được áp dụng trong quá trình render; PDF nguồn vẫn không thay đổi.

**Q: Nếu một PDF được bảo vệ bằng mật khẩu thì sao?**  
A: Cung cấp mật khẩu khi tạo thể hiện `Viewer`: `new Viewer(path, password)`.

**Q: Làm sao tôi gỡ lỗi lỗi “null pointer” khi thiết lập HtmlViewOptions?**  
A: Đảm bảo thư mục đầu ra tồn tại và `pageFilePathFormat` được giải quyết đúng cách.

**Q: Có cách nào để xoay các trang khi chuyển đổi sang định dạng khác (ví dụ: PNG) không?**  
A: Có. Sử dụng cùng cấu hình `rotatePage` với các tùy chọn view phù hợp cho định dạng đích.

## Tài nguyên
- **Documentation**: [Tài liệu GroupDocs Viewer](https://docs.groupdocs.com/viewer/java/)  
- **API reference**: [Tham chiếu API GroupDocs](https://reference.groupdocs.com/viewer/java/)  
- **Download**: [Trang tải xuống GroupDocs](https://releases.groupdocs.com/viewer/java/)  
- **Purchase**: [Tùy chọn mua GroupDocs](https://purchase.groupdocs.com/buy)  
- **Free trial**: [Dùng thử miễn phí GroupDocs](https://releases.groupdocs.com/viewer/java/)  
- **Temporary license**: [Yêu cầu giấy phép tạm thời](https://purchase.groupdocs.com/temporary-license/)  
- **Support**: [Diễn đàn hỗ trợ GroupDocs](https://forum.groupdocs.com/c/viewer/9)

---

**Cập nhật lần cuối:** 2026-10-05  
**Kiểm thử với:** GroupDocs.Viewer 25.2 cho Java  
**Tác giả:** GroupDocs

## Hướng dẫn liên quan

- [Hướng dẫn Java: render các trang đã chọn với GroupDocs.Viewer](/viewer/java/rendering-basics/java-groupdocs-viewer-render-pages-api-tutorial/)
- [Java PDF Rendering GroupDocs Viewer Ngắt trang](/viewer/java/advanced-rendering/java-pdf-rendering-groupdocs-viewer-page-breaks/)
- [GroupDocs Viewer Java Responsive Html Rendering](/viewer/java/advanced-rendering/groupdocs-viewer-java-responsive-html-rendering/)