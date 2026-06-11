---
date: '2026-03-05'
description: Học cách chuyển đổi số sang PDF và các định dạng khác như HTML, JPG,
  PNG bằng GroupDocs.Viewer cho Java. Hướng dẫn này bao gồm cài đặt, kỹ thuật render
  và các ứng dụng thực tiễn.
keywords:
- GroupDocs.Viewer for Java
- render Apple Numbers documents
- convert Numbers to HTML, JPG, PNG, PDF
title: Chuyển đổi Numbers sang PDF bằng GroupDocs.Viewer cho Java
type: docs
url: /vi/java/file-formats-support/render-numbers-groupdocs-viewer-java/
weight: 1
---

# Chuyển đổi Numbers sang PDF (và các Định dạng Khác) với GroupDocs.Viewer cho Java

Việc hiển thị tài liệu Apple Numbers trên web hoặc trong các ứng dụng desktop có thể gặp khó khăn, đặc biệt khi bạn cần **convert numbers to pdf** hoặc nhúng chúng dưới dạng hình ảnh. Trong hướng dẫn này, chúng tôi sẽ hướng dẫn cách sử dụng **GroupDocs.Viewer for Java** để render các tệp Numbers thành HTML, JPG, PNG, **và PDF**—cung cấp cho bạn các tùy chọn linh hoạt để chia sẻ, xem trước hoặc lưu trữ các bảng tính của mình.

![Render Apple Numbers Documents with GroupDocs.Viewer for Java](/viewer/file-formats-support/render-apple-numbers-documents-java.png)

### Những Điều Bạn Sẽ Học
- Cách thiết lập GroupDocs.Viewer trong dự án Java dựa trên Maven  
- Mã từng bước để **convert numbers to pdf**, **convert numbers to html**, và **convert numbers to jpg**  
- Các kịch bản thực tế nơi việc chuyển đổi tài liệu mang lại giá trị cho các cổng thông tin web, quy trình email và tích hợp DMS  

## Câu trả lời nhanh
- **Tôi có thể chuyển đổi Numbers sang PDF bằng Java không?** Có, bằng cách sử dụng `PdfViewOptions` trong GroupDocs.Viewer.  
- **Định dạng nào là tốt nhất cho việc xem trước trên web?** HTML cung cấp trải nghiệm tương tác nhất.  
- **Tôi có cần giấy phép cho việc sử dụng trong môi trường sản xuất không?** Cần một giấy phép thương mại cho các triển khai không phải thử nghiệm.  
- **Chuyển đổi hình ảnh có được hỗ trợ không?** Chắc chắn—sử dụng `JpgViewOptions` hoặc `PngViewOptions` để có hình ảnh chất lượng cao.  
- **Phiên bản Java nào được yêu cầu?** Java 8+ và Maven để quản lý phụ thuộc.  

## Yêu cầu trước
- Java Development Kit (JDK) 8 hoặc cao hơn đã được cài đặt.  
- Maven để quản lý các phụ thuộc.  
- Kiến thức cơ bản về I/O file và đường dẫn trong Java.  

## Cài đặt GroupDocs.Viewer cho Java

### Cài đặt với Maven
Thêm kho lưu trữ và phụ thuộc vào tệp `pom.xml` của bạn. Khối này phải giữ nguyên như đã hiển thị:

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
- **Free Trial:** Evaluate all features without cost.  
- **Temporary License:** Request a time‑limited key for extended testing.  
- **Purchase:** Obtain a full license for commercial projects.  

## Render tài liệu Numbers sang HTML  
*Trường hợp sử dụng: nhúng một bảng tính trực tiếp vào trang web.*

### Bước 1: Khởi tạo Viewer và Cấu hình tùy chọn HTML
Dưới đây là đoạn mã chính xác bạn sẽ chạy. Các chú thích giải thích từng dòng, nhưng **không chỉnh sửa khối mã**.

```java
import com.groupdocs.viewer.Viewer;
import com.groupdocs.viewer.options.HtmlViewOptions;
import java.nio.file.Path;

Path outputDirectory = Path.of("YOUR_OUTPUT_DIRECTORY");
Path pageFileFullPath = outputDirectory.resolve("Numbers_result.html");

try (Viewer viewer = new Viewer("YOUR_DOCUMENT_DIRECTORY/SAMPLE_NUMBERS")) {
    HtmlViewOptions options = HtmlViewOptions.forEmbeddedResources(pageFileFullPath);
    viewer.view(options);
}
```

- **Tại sao điều này quan trọng:** `HtmlViewOptions.forEmbeddedResources()` gói CSS và hình ảnh vào trong HTML, làm cho nó hoàn hảo cho việc xem trước nhanh trên web.

## Render tài liệu Numbers sang JPG  
*Tuyệt vời để chia sẻ ảnh chụp nhanh của bảng tính trên mạng xã hội hoặc trong email.*

### Bước 1: Thiết lập Viewer và tùy chọn JPG
```java
import com.groupdocs.viewer.Viewer;
import com.groupdocs.viewer.options.JpgViewOptions;
import java.nio.file.Path;

Path outputDirectory = Path.of("YOUR_OUTPUT_DIRECTORY");
Path pageFileFullPath = outputDirectory.resolve("Numbers_result.jpg");

try (Viewer viewer = new Viewer("YOUR_DOCUMENT_DIRECTORY/SAMPLE_NUMBERS")) {
    JpgViewOptions options = new JpgViewOptions(pageFileFullPath);
    viewer.view(options);
}
```

- **Mẹo:** Điều chỉnh chất lượng hình ảnh bằng `options.setQuality(int)` nếu bạn cần tệp nhỏ hơn.

## Render tài liệu Numbers sang PNG  
*Lý tưởng khi bạn cần hình ảnh không mất dữ liệu, độ phân giải cao cho báo cáo.*

### Bước 1: Khởi tạo và Cấu hình tùy chọn PNG
```java
import com.groupdocs.viewer.Viewer;
import com.groupdocs.viewer.options.PngViewOptions;
import java.nio.file.Path;

Path outputDirectory = Path.of("YOUR_OUTPUT_DIRECTORY");
Path pageFileFullPath = outputDirectory.resolve("Numbers_result.png");

try (Viewer viewer = new Viewer("YOUR_DOCUMENT_DIRECTORY/SAMPLE_NUMBERS")) {
    PngViewOptions options = new PngViewOptions(pageFileFullPath);
    viewer.view(options);
}
```

- **Mẹo chuyên nghiệp:** Sử dụng `options.setResolution(int)` để kiểm soát DPI cho hình ảnh sẵn sàng in.

## Render tài liệu Numbers sang PDF  
*Mục tiêu chính của nhiều nhà phát triển: **convert numbers to pdf** để lưu trữ hoặc phân phối.*

### Bước 1: Thiết lập Viewer cho chuyển đổi PDF
```java
import com.groupdocs.viewer.Viewer;
import com.groupdocs.viewer.options.PdfViewOptions;
import java.nio.file.Path;

Path outputDirectory = Path.of("YOUR_OUTPUT_DIRECTORY");
Path pageFileFullPath = outputDirectory.resolve("Numbers_result.pdf");

try (Viewer viewer = new Viewer("YOUR_DOCUMENT_DIRECTORY/SAMPLE_NUMBERS")) {
    PdfViewOptions options = new PdfViewOptions(pageFileFullPath);
    viewer.view(options);
}
```

- **Cấu hình chính:** `PdfViewOptions` cho phép bạn nhúng phông chữ và kiểm soát kích thước trang, đảm bảo đầu ra phù hợp với yêu cầu thương hiệu của bạn.

## Ứng dụng thực tiễn
- **Tích hợp Web:** Render sang HTML để có trình xem bảng tính tương tác trên trang của bạn.  
- **Chia sẻ Nội dung:** Chuyển đổi sang JPG/PNG để nhúng hình ảnh nhanh trong bản tin hoặc trò chuyện.  
- **DMS Doanh nghiệp:** Sử dụng **convert numbers to pdf** để lưu một phiên bản không thể chỉnh sửa, có thể tìm kiếm của bảng tính.  

## Các lưu ý về hiệu năng
- **Quản lý tài nguyên:** Luôn đóng `Viewer` trong khối try‑with‑resources (như đã minh họa) để giải phóng tài nguyên gốc kịp thời.  
- **Tệp lớn:** Đối với các tệp Numbers khổng lồ, hãy xem xét xử lý từng trang và truyền kết quả để tránh tiêu thụ bộ nhớ cao.  
- **An toàn đa luồng:** Tạo một thể hiện `Viewer` riêng cho mỗi luồng; lớp này không an toàn với đa luồng.  

## Kết luận
Bây giờ bạn đã có một bộ công cụ hoàn chỉnh cho **convert numbers to pdf**, cũng như cho HTML, JPG và PNG, sử dụng GroupDocs.Viewer cho Java. Những khả năng này cho phép bạn xây dựng các quy trình tài liệu linh hoạt—cho dù bạn đang cung cấp cho cổng web, tạo báo cáo, hay lưu trữ bảng tính.

### Các bước tiếp theo
Khám phá các tùy chọn tùy chỉnh thêm trong [tài liệu GroupDocs](https://docs.groupdocs.com/viewer/java/) và thử nghiệm việc tích hợp các tính năng này vào ứng dụng của bạn.

## Phần Câu hỏi thường gặp
**Q1: GroupDocs.Viewer hỗ trợ những định dạng tệp nào?**  
A1: Nó hỗ trợ một loạt các định dạng tài liệu bao gồm DOCX, XLSX, PDF và nhiều hơn nữa.  

**Q2: Làm thế nào để xử lý các tệp Numbers lớn một cách hiệu quả?**  
A2: Sử dụng các kỹ thuật quản lý bộ nhớ của Java và tối ưu mã của bạn để xử lý kích thước tệp lớn một cách hiệu quả.  

**Q3: GroupDocs.Viewer có thể được sử dụng trong dự án thương mại không?**  
A4: Có, nhưng bạn sẽ cần mua giấy phép cho việc sử dụng thương mại.  

**Q4: Có thể tùy chỉnh chất lượng đầu ra của hình ảnh không?**  
A5: Chắc chắn. Bạn có thể điều chỉnh cài đặt trong `JpgViewOptions` và `PngViewOptions`.  

**Q5: Tôi có thể tìm các ví dụ sử dụng nâng cao ở đâu?**  
A5: Tham khảo [tài liệu API](https://reference.groupdocs.com/viewer/java/) để có tài liệu chi tiết.  

## Các câu hỏi thường gặp
**Q: Làm sao để chuyển đổi tệp Numbers sang PDF mà không mất định dạng?**  
A: Sử dụng `PdfViewOptions` như đã trình bày ở trên; viewer tự động giữ nguyên bố cục, phông chữ và kiểu ô.  

**Q: Tôi có thể chuyển đổi một bảng tính thành hình ảnh trong một lần gọi không?**  
A: Có, `JpgViewOptions` hoặc `PngViewOptions` thực hiện chuyển đổi trong một bước, cho phép bạn chỉ định độ phân giải và chất lượng.  

**Q: Có cách nào để xử lý hàng loạt nhiều tệp Numbers không?**  
A: Đặt logic của viewer trong một vòng lặp, khởi tạo lại `Viewer` cho mỗi tệp, và ghi mỗi đầu ra vào một thư mục riêng.  

**Q: Tôi có cần giấy phép riêng cho mỗi định dạng đầu ra không?**  
A: Không, một giấy phép GroupDocs.Viewer duy nhất bao phủ tất cả các định dạng được hỗ trợ.  

**Q: Yêu cầu phiên bản GroupDocs.Viewer nào cho các tính năng này?**  
A: Các ví dụ nhắm vào phiên bản 25.2, bao gồm hỗ trợ đầy đủ cho chuyển đổi Numbers sang PDF/HTML/Image.  

## Tài nguyên
- **Documentation:** [Tài liệu GroupDocs.Viewer Java](https://docs.groupdocs.com/viewer/java/)
- **API Reference:** [Tham khảo API GroupDocs](https://reference.groupdocs.com/viewer/java/)
- **Download:** [Tải GroupDocs.Viewer](https://releases.groupdocs.com/viewer/java/)
- **Purchase License:** [Mua giấy phép](https://purchase.groupdocs.com/buy)
- **Free Trial:** [Bắt đầu Dùng thử miễn phí](https://releases.groupdocs.com/viewer/java/)
- **Temporary License:** [Yêu cầu tại đây](https://purchase.groupdocs.com/temporary-license/)
- **Support Forum:** [Tham gia Thảo luận](https://forum.groupdocs.com/c/viewer/9)

---

**Last Updated:** 2026-03-05  
**Được kiểm tra với:** GroupDocs.Viewer 25.2 for Java  
**Tác giả:** GroupDocs