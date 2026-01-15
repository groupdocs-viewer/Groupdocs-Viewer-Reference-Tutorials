---
date: '2026-01-15'
description: Tìm hiểu cách hiển thị các trang và tạo HTML từ tài liệu bằng GroupDocs.Viewer
  cho Java. Hướng dẫn này bao gồm cài đặt, cấu hình và tích hợp thực tế.
keywords:
- render selected pages GroupDocs.Viewer Java
- GroupDocs Viewer for Java setup
- render HTML with embedded resources
title: Cách hiển thị các trang bằng GroupDocs.Viewer cho Java
type: docs
url: /vi/java/advanced-rendering/render-selected-pages-groupdocs-viewer-java/
weight: 1
---

# Cách Render Trang với GroupDocs.Viewer cho Java

Việc hiển thị chỉ các phần cụ thể của một tài liệu trong ứng dụng web của bạn có thể là thách thức. Trong hướng dẫn này, bạn sẽ khám phá **cách render các trang** một cách hiệu quả, chuyển chúng thành các tệp HTML tự chứa có thể nhúng trực tiếp vào giao diện người dùng của bạn. Cho dù bạn cần hiển thị một đoạn trích hợp đồng hay một chương duy nhất của sách giáo trình, các bước dưới đây sẽ hướng dẫn bạn qua toàn bộ quy trình sử dụng GroupDocs.Viewer cho Java.

Sẵn sàng nâng cấp ứng dụng của bạn? Hãy bắt đầu bằng cách đảm bảo thiết lập của bạn đã đúng.

## Câu trả lời nhanh
- **What does “render pages” mean?** Chuyển đổi các trang tài liệu được chọn thành định dạng có thể xem được như HTML.  
- **Which format is generated?** HTML với các tài nguyên được nhúng (hình ảnh, CSS, phông chữ).  
- **Do I need a license?** Bản dùng thử hoạt động cho việc đánh giá; cần giấy phép đầy đủ cho môi trường sản xuất.  
- **Can I choose non‑consecutive pages?** Có – chỉ định bất kỳ số trang nào bạn cần.  
- **Is caching recommended?** Chắc chắn, việc lưu cache HTML đã render giảm thời gian tải cho các trang được truy cập thường xuyên.

![Render Selected Pages of a Document with GroupDocs.Viewer for Java](/viewer/advanced-rendering/render-selected-pages-of-a-document-java.png)

### Những gì bạn sẽ học
- Cài đặt GroupDocs.Viewer trong môi trường Java của bạn  
- Render các trang tài liệu cụ thể bằng API Viewer  
- Cấu hình các tùy chọn hiển thị HTML để đạt hiệu quả tối ưu  
- Các trường hợp sử dụng thực tế và kịch bản tích hợp  

## Render các trang được chọn là gì?
Render các trang được chọn có nghĩa là trích xuất chỉ những trang bạn chỉ định từ tài liệu nguồn (DOCX, PDF, PPT, v.v.) và chuyển chúng thành định dạng có thể hiển thị trong trình duyệt web. Cách tiếp cận này giảm băng thông, tăng tốc độ tải trang và cải thiện trải nghiệm người dùng cuối bằng cách chỉ hiển thị nội dung liên quan.

## Tại sao tạo HTML từ tài liệu?
Việc tạo HTML từ tài liệu cung cấp cho bạn một biểu diễn nhẹ, không phụ thuộc vào nền tảng, hoạt động trên mọi trình duyệt mà không cần các trình xem hoặc plugin bên ngoài. Nhúng các tài nguyên trực tiếp vào tệp HTML (hình ảnh, phông chữ, CSS) đơn giản hoá việc triển khai và loại bỏ các vấn đề cross‑origin.

## Yêu cầu trước
Đảm bảo môi trường phát triển của bạn đáp ứng các yêu cầu sau:

1. **Required Libraries** – Bao gồm GroupDocs.Viewer cho Java (phiên bản 25.2 hoặc mới hơn) trong dự án của bạn.  
2. **Environment** – JDK 8 hoặc cao hơn; IDE như IntelliJ IDEA hoặc Eclipse.  
3. **Knowledge** – Kiến thức cơ bản về lập trình Java và quản lý phụ thuộc Maven.

## Cài đặt GroupDocs.Viewer cho Java

### Cài đặt qua Maven

Thêm kho lưu trữ và phụ thuộc vào tệp `pom.xml` của bạn:

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
- **Free Trial** – Khám phá tất cả tính năng mà không tốn phí.  
- **Temporary License** – Mở rộng thời gian thử nghiệm vượt quá thời gian dùng thử.  
- **Full Purchase** – Cần thiết cho triển khai trong môi trường sản xuất.

#### Khởi tạo và Cài đặt Cơ bản

```java
import com.groupdocs.viewer.Viewer;

public class DocumentViewer {
    public static void main(String[] args) {
        try (Viewer viewer = new Viewer("path/to/your/document.docx")) {
            // Your rendering logic here
        }
    }
}
```

## Hướng dẫn triển khai

### Render các trang cụ thể dưới dạng HTML với tài nguyên được nhúng

#### Bước 1: Cấu hình Đường dẫn Đầu ra

```java
import java.nio.file.Path;
import java.nio.file.Paths;

Path outputDirectory = Paths.get("YOUR_OUTPUT_DIRECTORY");
Path pageFilePathFormat = outputDirectory.resolve("page_{0}.html");
```

- **Explanation**: `outputDirectory` là nơi các tệp HTML được tạo sẽ được lưu.  
- **Naming**: `page_{0}.html` tạo một tệp riêng cho mỗi trang đã render.

#### Bước 2: Thiết lập tùy chọn hiển thị HTML

```java
import com.groupdocs.viewer.options.HtmlViewOptions;

HtmlViewOptions viewOptions = HtmlViewOptions.forEmbeddedResources(pageFilePathFormat);
```

- **Explanation**: `forEmbeddedResources()` gói hình ảnh, CSS và phông chữ trực tiếp bên trong mỗi tệp HTML, loại bỏ các phụ thuộc bên ngoài.

#### Bước 3: Render các trang mong muốn

```java
try (Viewer viewer = new Viewer("path/to/your/document.docx")) {
    viewer.view(viewOptions, 1, 3);
}
```

- **Explanation**: Phương thức `view()` nhận `HtmlViewOptions` và một danh sách các số trang. Trong ví dụ này, chỉ trang thứ nhất và thứ ba được render.

### Mẹo khắc phục sự cố
- Xác minh rằng thư mục đầu ra tồn tại và ứng dụng có quyền ghi.  
- Đảm bảo đường dẫn tài liệu đúng và tệp không bị hỏng.  
- Nếu gặp lỗi giấy phép, xác nhận rằng tệp giấy phép hợp lệ được đặt cùng với ứng dụng của bạn.

## Ứng dụng thực tiễn

Render các trang được chọn hữu ích trong nhiều kịch bản:

1. **Legal Documents** – Hiển thị chỉ các điều khoản liên quan của hợp đồng.  
2. **Educational Platforms** – Cho phép sinh viên xem trước các chương cụ thể mà không cần tải toàn bộ sách giáo trình.  
3. **Business Reports** – Cung cấp cho các bên liên quan các bản tóm tắt ngắn gọn bằng cách hiển thị các phần chính của báo cáo.

## Các yếu tố về hiệu năng

- **Memory Management** – Sử dụng try‑with‑resources (như đã minh họa) để giải phóng tài nguyên Viewer kịp thời.  
- **Caching** – Lưu HTML đã render trong bộ nhớ cache (ví dụ: Redis hoặc trong bộ nhớ) cho các trang được truy cập thường xuyên.  
- **Resource Minimization** – Các tài nguyên được nhúng làm tăng kích thước tệp hơi lên; cân nhắc nén đầu ra HTML nếu băng thông là vấn đề.

## Các vấn đề thường gặp và giải pháp

| Issue | Solution |
|-------|----------|
| **File not found** | Kiểm tra lại đường dẫn tuyệt đối/định tương và đảm bảo tệp tồn tại. |
| **Out‑of‑memory for large docs** | Chỉ render các trang cần thiết, hoặc tăng kích thước heap JVM (`-Xmx`). |
| **Missing images in HTML** | Xác nhận rằng `forEmbeddedResources` được sử dụng; nếu không, hình ảnh sẽ được lưu riêng. |
| **License error** | Đặt tệp `GroupDocs.Viewer.lic` hợp lệ vào thư mục gốc của ứng dụng hoặc chỉ định đường dẫn của nó bằng mã. |

## Câu hỏi thường gặp

1. **What is GroupDocs.Viewer for Java?**  
   Thư viện cho phép render hơn 90 định dạng tài liệu (PDF, DOCX, PPT, v.v.) trực tiếp trong các ứng dụng Java.  
2. **Can I render PDF pages using this method?**  
   Có – API Viewer hỗ trợ PDF cùng với nhiều định dạng khác.  
3. **How do I handle large documents efficiently?**  
   Chỉ render các trang bạn cần và sử dụng cache để tránh xử lý lặp lại.  
4. **What is the benefit of embedding resources in HTML files?**  
   Nó tạo ra một tệp tự chứa duy nhất cho mỗi trang, đơn giản hoá việc triển khai và loại bỏ việc tải tài nguyên bên ngoài.  
5. **Where can I find more information on GroupDocs.Viewer for Java?**  
   - **Documentation**: [GroupDocs.Viewer Documentation](https://docs.groupdocs.com/viewer/java/)  
   - **API Reference**: [API Reference Guide](https://reference.groupdocs.com/viewer/java/)  

## Tài nguyên

- **Tài liệu**: [GroupDocs.Viewer Documentation](https://docs.groupdocs.com/viewer/java/)  
- **Tham chiếu API**: [API Reference Guide](https://reference.groupdocs.com/viewer/java/)  
- **Tải xuống**: [GroupDocs.Viewer Download Page](https://releases.groupdocs.com/viewer/java/)  
- **Mua**: [Buy GroupDocs.Viewer](https://purchase.groupdocs.com/buy)  
- **Dùng thử miễn phí**: [GroupDocs Free Trial](https://releases.groupdocs.com/viewer/java/)  
- **Giấy phép tạm thời**: [Get a Temporary License](https://purchase.groupdocs.com/temporary-license/)  
- **Hỗ trợ**: [GroupDocs Support Forum](https://forum.groupdocs.com/c/viewer/9)

---

**Cập nhật lần cuối:** 2026-01-15  
**Đã kiểm tra với:** GroupDocs.Viewer 25.2  
**Tác giả:** GroupDocs  

---