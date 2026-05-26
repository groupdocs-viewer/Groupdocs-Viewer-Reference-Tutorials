---
date: '2026-02-23'
description: Tìm hiểu cách chuyển đổi IGS sang PDF, HTML, JPG và PNG với GroupDocs.Viewer
  cho Java. Hãy làm theo hướng dẫn từng bước này kèm theo các ví dụ mã sẵn sàng chạy.
keywords:
- GroupDocs.Viewer Java
- Convert IGS Files
- Render IGS Documents
title: Chuyển đổi IGS sang PDF, HTML, JPG và PNG bằng GroupDocs.Viewer Java
type: docs
url: /vi/java/file-formats-support/groupdocs-viewer-java-igs-rendering-html-jpg-png-pdf/
weight: 1
---

 construct final answer.# Chuyển đổi IGS sang PDF, HTML, JPG & PNG bằng GroupDocs.Viewer Java

Nếu bạn cần **chuyển đổi IGS sang PDF** (hoặc sang HTML, JPG, PNG) trực tiếp từ một ứng dụng Java, bạn đã đến đúng nơi. Trong hướng dẫn này, chúng tôi sẽ đi qua mọi thứ bạn cần—từ việc thiết lập thư viện đến việc render mô hình 3‑D ở định dạng phù hợp với dự án của bạn. Bạn sẽ thấy tại sao GroupDocs.Viewer là lựa chọn vững chắc cho các chuyển đổi nhanh chóng, đáng tin cậy và nhận được mã mẫu bạn có thể tích hợp ngay vào giải pháp của mình.

![Chuyển đổi tệp IGS sang HTML, JPG, PNG và PDF với GroupDocs.Viewer cho Java](/viewer/file-formats-support/convert-igs-files-to-html-jpg-png-and-pdf-java.png)

## Câu trả lời nhanh
- **Tôi có thể chuyển đổi IGS sang PDF bằng Java không?** Có, sử dụng `PdfViewOptions` của GroupDocs.Viewer.  
- **Các định dạng đầu ra nào được hỗ trợ?** HTML, JPG, PNG và PDF.  
- **Tôi có cần giấy phép cho môi trường sản xuất không?** Cần giấy phép thương mại; bản dùng thử miễn phí có sẵn để thử nghiệm.  
- **Yêu cầu phiên bản Java nào?** JDK 8 hoặc cao hơn.  
- **Maven là cách duy nhất để thêm thư viện không?** Không, bạn cũng có thể dùng Gradle hoặc thêm JAR thủ công.  

## “Chuyển đổi IGS sang PDF” là gì?
Chuyển đổi IGS (một định dạng tệp trung tính cho dữ liệu CAD 3‑D) sang PDF có nghĩa là biến một mô hình 3‑D phức tạp thành một tài liệu tĩnh, có thể xem được rộng rãi. Điều này hữu ích khi chia sẻ thiết kế với các bên liên quan không có công cụ CAD.

## Tại sao nên sử dụng GroupDocs.Viewer cho việc chuyển đổi IGS?
- **Render CAD không cần viết mã** – thư viện xử lý việc phân tích định dạng IGS.  
- **Nhiều tùy chọn đầu ra** – một lời gọi API có thể tạo HTML, JPG, PNG hoặc PDF.  
- **Đa nền tảng** – hoạt động trên mọi hệ điều hành hỗ trợ Java.  
- **Tập trung vào hiệu năng** – render nhanh ngay cả với các bộ lắp ráp lớn.  

## Yêu cầu trước
- **GroupDocs.Viewer for Java** ≥ 25.2  
- **JDK 8+** đã được cài đặt và cấu hình trong IDE của bạn (IntelliJ IDEA, Eclipse, NetBeans, v.v.)  
- Kiến thức cơ bản về Maven (tùy chọn nhưng được khuyến nghị)  

## Cài đặt GroupDocs.Viewer cho Java

### Phụ thuộc Maven
Add the GroupDocs repository and the Viewer dependency to your `pom.xml`:

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

### Cách nhận giấy phép
GroupDocs.Viewer cung cấp:
- **Bản dùng thử miễn phí** – giới hạn sử dụng, tuyệt vời cho các thử nghiệm nhanh.  
- **Giấy phép tạm thời** – đầy đủ tính năng trong thời gian đánh giá ngắn.  
- **Giấy phép thương mại** – sử dụng không giới hạn trong môi trường sản xuất.  

### Khởi tạo Viewer cơ bản
The snippet below shows how to create a `Viewer` instance that points to your IGS file:

```java
import com.groupdocs.viewer.Viewer;

public class ViewerSetup {
    public static void main(String[] args) {
        try (Viewer viewer = new Viewer("path/to/your/document.igs")) {
            // Configuration and rendering logic goes here.
        }
    }
}
```

## Render IGS sang HTML

### Cách chuyển đổi IGS sang HTML?
HTML output gives you an interactive, browser‑friendly view of the 3‑D model.

```java
import com.groupdocs.viewer.Viewer;
import com.groupdocs.viewer.options.HtmlViewOptions;
import java.nio.file.Path;
import static java.nio.file.Paths.get;

public class RenderIgsToHtml {
    public static void run() {
        Path outputDirectory = get("YOUR_OUTPUT_DIRECTORY");
        Path pageFilePathFormat = outputDirectory.resolve("IGS_result.html");

        try (Viewer viewer = new Viewer(get("YOUR_DOCUMENT_DIRECTORY/SAMPLE_IGS"))) {
            HtmlViewOptions options = HtmlViewOptions.forEmbeddedResources(pageFilePathFormat);
            viewer.view(options);
        }
    }
}
```

**Điểm quan trọng:** `HtmlViewOptions.forEmbeddedResources()` nhúng tất cả các tài nguyên cần thiết (CSS, hình ảnh) trực tiếp vào tệp HTML, giúp nó di động.

## Render IGS sang JPG

### Cách chuyển đổi IGS sang JPG?
JPG images are perfect for thumbnails or quick previews.

```java
import com.groupdocs.viewer.Viewer;
import com.groupdocs.viewer.options.JpgViewOptions;
import java.nio.file.Path;
import static java.nio.file.Paths.get;

public class RenderIgsToJpg {
    public static void run() {
        Path outputDirectory = get("YOUR_OUTPUT_DIRECTORY");
        Path pageFilePathFormat = outputDirectory.resolve("IGS_result.jpg");

        try (Viewer viewer = new Viewer(get("YOUR_DOCUMENT_DIRECTORY/SAMPLE_IGS"))) {
            JpgViewOptions options = new JpgViewOptions(pageFilePathFormat);
            viewer.view(options);
        }
    }
}
```

Bạn có thể điều chỉnh `JpgViewOptions` để kiểm soát độ phân giải và **chất lượng nén**.

## Render IGS sang PNG

### Cách chuyển đổi IGS sang PNG?
PNG supports transparency, which is handy for overlaying the model on different backgrounds.

```java
import com.groupdocs.viewer.Viewer;
import com.groupdocs.viewer.options.PngViewOptions;
import java.nio file.Path;
import static java.nio.file.Paths.get;

public class RenderIgsToPng {
    public static void run() {
        Path outputDirectory = get("YOUR_OUTPUT_DIRECTORY");
        Path pageFilePathFormat = outputDirectory.resolve("IGS_result.png");

        try (Viewer viewer = new Viewer(get("YOUR_DOCUMENT_DIRECTORY/SAMPLE_IGS"))) {
            PngViewOptions options = new PngViewOptions(pageFilePathFormat);
            viewer.view(options);
        }
    }
}
```

Thử nghiệm với `PngViewOptions` để đạt được **cân bằng tốt nhất giữa kích thước tệp và độ trung thực hình ảnh**.

## Render IGS sang PDF

### Cách chuyển đổi IGS sang PDF?
PDF is the go‑to format for sharing detailed design documentation. This section directly addresses the primary keyword **convert IGS to PDF**.

```java
import com.groupdocs.viewer.Viewer;
import com.groupdocs.viewer.options.PdfViewOptions;
import java.nio.file.Path;
import static java.nio.file.Paths.get;

public class RenderIgsToPdf {
    public static void run() {
        Path outputDirectory = get("YOUR_OUTPUT_DIRECTORY");
        Path pageFilePathFormat = outputDirectory.resolve("IGS_result.pdf");

        try (Viewer viewer = new Viewer(get("YOUR_DOCUMENT_DIRECTORY/SAMPLE_IGS"))) {
            PdfViewOptions options = new PdfViewOptions(pageFilePathFormat);
            viewer.view(options);
        }
    }
}
```

`PdfViewOptions` cho phép bạn kiểm soát bố cục trang, chất lượng hình ảnh và việc **nhúng phông chữ** hay không.

## Ứng dụng thực tiễn

- **Cổng thông tin web** – nhúng các mô hình đã render HTML trực tiếp vào các công cụ cấu hình sản phẩm.  
- **Tài sản marketing** – tạo hình ảnh JPG/PNG độ phân giải cao cho tài liệu quảng cáo.  
- **Tài liệu kỹ thuật** – bao gồm các bản render PDF của mô hình CAD trong hướng dẫn sử dụng.  
- **Đảm bảo chất lượng** – tự động tạo thumbnail cho các lô tệp IGS lớn.  

## Các vấn đề thường gặp & Giải pháp

| Vấn đề | Giải pháp |
|-------|----------|
| **Thư mục đầu ra không tồn tại** | Xác minh đường dẫn được truyền vào `Path outputDirectory` và đảm bảo quá trình Java có quyền ghi. |
| **Trang trắng trong PDF** | Đảm bảo tệp IGS không bị hỏng; thử mở nó trong một trình xem CAD trước. |
| **Render chậm cho các bộ lắp ráp lớn** | Tăng bộ nhớ heap của JVM (`-Xmx2g` hoặc hơn) và cân nhắc render từng trang bằng cách sử dụng `viewer.getPageCount()` nếu cần. |
| **Thiếu phông chữ trong PDF** | Sử dụng `PdfViewOptions` để nhúng các phông chữ cần thiết hoặc cài đặt các phông chữ thiếu trên máy chủ. |

## Câu hỏi thường gặp

**Hỏi: Tôi có thể chuyển đổi nhiều tệp IGS trong một lần chạy không?**  
**Đáp:** Có. Lặp qua danh sách các đường dẫn tệp và gọi phương thức `view` thích hợp cho mỗi tệp.

**Hỏi: Có thể tùy chỉnh kích thước trang PDF không?**  
**Đáp:** Chắc chắn. `PdfViewOptions` cung cấp `setPageSize(PageSize.A4)` và các phương thức tương tự.

**Hỏi: Tôi có cần giấy phép riêng cho mỗi định dạng đầu ra không?**  
**Đáp:** Không. Một giấy phép GroupDocs.Viewer duy nhất bao phủ tất cả các định dạng được hỗ trợ.

**Hỏi: Tệp IGS có thể lớn đến mức nào trước khi hiệu năng giảm?**  
**Đáp:** Thư viện xử lý các tệp lên tới vài trăm megabyte, nhưng bạn có thể cần cấp phát thêm bộ nhớ JVM cho các mô hình rất lớn.

**Hỏi: Tôi có thể render chỉ một góc nhìn hoặc hướng cụ thể không?**  
**Đáp:** GroupDocs.Viewer render góc nhìn mặc định. Đối với các hướng tùy chỉnh, hãy tiền xử lý tệp IGS bằng công cụ CAD trước khi chuyển đổi.

---

**Last Updated:** 2026-02-23  
**Tested With:** GroupDocs.Viewer 25.2 for Java  
**Author:** GroupDocs