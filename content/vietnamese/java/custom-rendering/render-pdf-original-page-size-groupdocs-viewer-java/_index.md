---
"date": "2025-04-24"
"description": "Tìm hiểu cách hiển thị chính xác các tệp PDF với kích thước trang gốc bằng GroupDocs.Viewer cho Java, đảm bảo tính toàn vẹn của tài liệu trên nhiều nền tảng."
"title": "Hiển thị PDF ở kích thước gốc bằng GroupDocs.Viewer cho Java&#58; Hướng dẫn toàn diện"
"url": "/vi/java/custom-rendering/render-pdf-original-page-size-groupdocs-viewer-java/"
"weight": 1
---

# Cách hiển thị PDF với kích thước trang gốc của chúng bằng GroupDocs.Viewer cho Java

Việc hiển thị PDF trong khi vẫn giữ nguyên kích thước trang gốc là điều cần thiết để hiển thị chính xác trên nhiều nền tảng và thiết bị khác nhau. Hướng dẫn toàn diện này sẽ hướng dẫn bạn cách triển khai tính năng này bằng GroupDocs.Viewer for Java API. Bằng cách làm theo các bước này, bạn sẽ đảm bảo PDF của mình giữ được độ trung thực trong quá trình hiển thị.

## Những gì bạn sẽ học được
- Tại sao việc giữ nguyên kích thước trang gốc khi kết xuất PDF lại quan trọng.
- Thiết lập và cấu hình GroupDocs.Viewer cho Java.
- Hướng dẫn chi tiết từng bước để hiển thị tệp PDF theo kích thước gốc.
- Ứng dụng thực tế và khả năng tích hợp.
- Các kỹ thuật để tối ưu hóa hiệu suất trong nhiệm vụ này.

Hãy cùng xem lại những điều kiện tiên quyết bạn cần có trước khi bắt đầu!

### Điều kiện tiên quyết
Để thực hiện theo, hãy đảm bảo bạn có:
- **Bộ phát triển Java (JDK):** Máy của bạn phải cài đặt JDK 8 trở lên.
- **GroupDocs.Viewer cho Java:** Tích hợp thư viện này bằng Maven.
- **Ý tưởng:** Sử dụng Môi trường phát triển tích hợp như IntelliJ IDEA hoặc Eclipse.

### Thiết lập GroupDocs.Viewer cho Java

Để bắt đầu, hãy thiết lập GroupDocs.Viewer cho Java trong môi trường phát triển của bạn. Quá trình này rất đơn giản nếu bạn sử dụng công cụ xây dựng như Maven:

**Cấu hình Maven**
```xml
<repositories>
   <repository>
      <id>groupdocs-repo</id>
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

#### Mua lại giấy phép
GroupDocs cung cấp nhiều tùy chọn cấp phép khác nhau:
- **Dùng thử miễn phí:** Bắt đầu bằng bản dùng thử miễn phí để khám phá các tính năng.
- **Giấy phép tạm thời:** Xin giấy phép tạm thời để truy cập toàn diện mà không bị giới hạn.
- **Mua:** Hãy cân nhắc mua nếu dự án của bạn cần sử dụng lâu dài.

### Hướng dẫn thực hiện

Bây giờ, chúng ta hãy tập trung vào việc triển khai kết xuất PDF trong khi vẫn giữ nguyên kích thước trang gốc. Chúng tôi sẽ hướng dẫn bạn từng bước chi tiết.

#### Khởi tạo GroupDocs.Viewer
**Tổng quan:**
Bắt đầu bằng cách thiết lập một `Viewer` ví dụ cho tài liệu nguồn của bạn.

```java
import com.groupdocs.viewer.Viewer;
import com.groupdocs.viewer.options.PngViewOptions;

import java.nio.file.Path;

public class RenderOriginalPageSize {
    public static void main(String[] args) {
        // Xác định đường dẫn thư mục đầu ra cho các trang được hiển thị
        Path outputDirectory = Path.of("YOUR_OUTPUT_DIRECTORY");
        
        // Định dạng cho đường dẫn tệp trang đầu ra
        String pageFilePathFormat = "page_{0}.png";
        Path pageFilePath = outputDirectory.resolve(pageFilePathFormat);
        
        // Khởi tạo PngViewOptions với định dạng đường dẫn
        PngViewOptions viewOptions = new PngViewOptions(pageFilePath.toString());
        
        // Đặt tùy chọn để hiển thị kích thước trang gốc cho tài liệu PDF
        viewOptions.getPdfOptions().setRenderOriginalPageSize(true);
        
        // Tạo một phiên bản Viewer cho tài liệu PDF nguồn
        try (Viewer viewer = new Viewer("YOUR_DOCUMENT_DIRECTORY/SAMPLE_PDF")) {
            // Hiển thị PDF bằng các tùy chọn đã chỉ định
            viewer.view(viewOptions);
        }
    }
}
```

**Giải thích:**
- **Cấu hình đường dẫn:** Xác định nơi lưu trữ hình ảnh đã kết xuất.
- **Tùy chọn PngView:** Xác định rằng chúng ta muốn xuất ra định dạng PNG và cấu hình định dạng đường dẫn cho từng trang.
- **Hiển thị kích thước trang gốc:** Thiết lập quan trọng này đảm bảo các trang không bị thu nhỏ, giữ nguyên kích thước ban đầu.

#### Mẹo khắc phục sự cố
Nếu bạn gặp phải vấn đề:
- Đảm bảo đường dẫn trong `outputDirectory` Và `"YOUR_DOCUMENT_DIRECTORY/SAMPLE_PDF"` là đúng.
- Xác minh GroupDocs.Viewer được cấu hình đúng trong công cụ xây dựng của bạn.

### Ứng dụng thực tế
Việc hiển thị tệp PDF với kích thước trang gốc có thể có lợi cho nhiều trường hợp, bao gồm:
1. **Lưu trữ kỹ thuật số:** Bảo tồn tính toàn vẹn của tài liệu lịch sử cho mục đích lưu trữ.
2. **Quản lý văn bản pháp lý:** Đảm bảo các văn bản pháp lý vẫn giữ nguyên bố cục khi xem dưới dạng kỹ thuật số.
3. **Chia sẻ tài liệu giáo dục:** Chia sẻ sách giáo khoa hoặc tài liệu hướng dẫn mà không thay đổi cấu trúc nội dung.
4. **Hệ thống xử lý hóa đơn:** Duy trì tính nhất quán và khả năng đọc được trong hệ thống xử lý hóa đơn tự động.

### Cân nhắc về hiệu suất
Việc tối ưu hóa hiệu suất kết xuất PDF là rất quan trọng, đặc biệt là đối với các tài liệu lớn:
- **Quản lý bộ nhớ:** Phân bổ đủ bộ nhớ để xử lý các tệp lớn một cách hiệu quả.
- **Tải chậm:** Chỉ tải các trang hoặc phần cần thiết khi xử lý các tài liệu dài.
- **Cơ chế lưu trữ đệm:** Triển khai bộ nhớ đệm cho các tệp PDF được truy cập thường xuyên để giảm thời gian xử lý.

### Phần kết luận
Bằng cách làm theo hướng dẫn này, bạn đã học cách sử dụng GroupDocs.Viewer for Java để hiển thị PDF trong khi vẫn giữ nguyên kích thước trang gốc. Kỹ năng này vô cùng hữu ích trong việc duy trì tính toàn vẹn của tài liệu trên nhiều ứng dụng khác nhau.

Bước tiếp theo, hãy cân nhắc khám phá các tính năng bổ sung của GroupDocs.Viewer, chẳng hạn như khả năng thêm hình mờ và chuyển đổi.

### Phần Câu hỏi thường gặp
**1. Làm thế nào để tích hợp GroupDocs.Viewer với các framework khác như Spring?**
   - Bạn có thể sử dụng tính năng tiêm phụ thuộc để quản lý các phiên bản Viewer trong ngữ cảnh ứng dụng của mình.

**2. Tôi có thể xuất tệp PDF sang các định dạng khác ngoài PNG không?**
   - Có, GroupDocs.Viewer hỗ trợ nhiều định dạng đầu ra bao gồm JPEG và SVG.

**3. Tôi phải làm gì nếu quá trình kết xuất không thành công?**
   - Kiểm tra nhật ký lỗi để tìm thông báo cụ thể và đảm bảo đường dẫn được chỉ định chính xác.

**4. Có giới hạn về kích thước của tệp PDF có thể hiển thị không?**
   - Hiệu suất có thể giảm sút với các tệp rất lớn, vì vậy hãy cân nhắc chia chúng thành các phần dễ quản lý hơn.

**5. Tôi có thể xuất trực tiếp tệp PDF được mã hóa không?**
   - GroupDocs.Viewer hỗ trợ hiển thị các tài liệu được bảo vệ nếu bạn cung cấp thông tin xác thực cần thiết.

### Tài nguyên
Để đọc thêm và tìm thêm tài liệu:
- **Tài liệu:** [Trình xem GroupDocs Tài liệu Java](https://docs.groupdocs.com/viewer/java/)
- **Tài liệu tham khảo API:** [Tài liệu tham khảo API GroupDocs cho Java](https://reference.groupdocs.com/viewer/java/)
- **Tải xuống GroupDocs.Viewer:** [Tải xuống chính thức](https://releases.groupdocs.com/viewer/java/)
- **Mua và cấp phép:** [Mua sản phẩm GroupDocs](https://purchase.groupdocs.com/buy)
- **Dùng thử miễn phí:** [Dùng thử miễn phí GroupDocs](https://releases.groupdocs.com/viewer/java/)
- **Giấy phép tạm thời:** [Nhận giấy phép tạm thời](https://purchase.groupdocs.com/temporary-license/)
- **Diễn đàn hỗ trợ:** [Diễn đàn hỗ trợ GroupDocs](https://forum.groupdocs.com/c/viewer/9)

Chúng tôi hy vọng hướng dẫn này giúp bạn triển khai kết xuất PDF với kích thước trang gốc bằng GroupDocs.Viewer cho Java. Chúc bạn viết mã vui vẻ!