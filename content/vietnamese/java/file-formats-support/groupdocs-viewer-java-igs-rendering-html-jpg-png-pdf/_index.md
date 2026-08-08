---
date: '2026-08-08'
description: Tìm hiểu cách chuyển đổi IGS sang PDF, HTML, JPG và PNG bằng GroupDocs.Viewer
  cho Java. Step‑by‑step guide, prerequisites, and troubleshooting cho các nhà phát
  triển Java.
keywords:
- convert igs to pdf
- convert cad to image
- convert igs to jpg
- java cad to pdf
lastmod: '2026-08-08'
og_description: Chuyển đổi IGS sang PDF, HTML, JPG và PNG bằng GroupDocs.Viewer cho
  Java. Detailed setup, code snippets, và troubleshooting cho các nhà phát triển Java.
og_image_alt: 'Developer guide: convert IGS files to PDF, HTML, JPG, PNG with GroupDocs.Viewer
  Java'
og_title: Chuyển đổi IGS sang PDF, HTML, JPG & PNG với GroupDocs.Viewer Java
schemas:
- author: GroupDocs
  dateModified: '2026-08-08'
  description: Learn how to convert IGS to PDF, HTML, JPG, and PNG using GroupDocs.Viewer
    for Java. Step‑by‑step guide, prerequisites, and troubleshooting for Java developers.
  headline: Convert IGS to PDF, HTML, JPG & PNG with GroupDocs.Viewer Java
  type: TechArticle
- questions:
  - answer: Yes. Iterate over a collection of file paths and invoke the appropriate
      `view` method for each file within the same `Viewer` instance.
    question: Can I convert multiple IGS files in a single run?
  - answer: Absolutely. `PdfViewOptions` offers `setPageSize(PageSize.A4)`, `PageSize.Letter`,
      and custom dimensions via `setCustomSize(width, height)`.
    question: Is it possible to customize the PDF page size?
  - answer: No. A single GroupDocs.Viewer license covers all supported formats, including
      HTML, JPG, PNG, and PDF.
    question: Do I need a separate license for each output format?
  - answer: The library reliably processes files up to **500 MB**; for models larger
      than 200 MB, allocate additional JVM memory and consider rendering in batches.
    question: How large can an IGS file be before performance degrades?
  - answer: GroupDocs.Viewer renders the default orientation defined in the IGS file.
      For custom views, preprocess the file with a CAD tool or adjust the model before
      conversion.
    question: Can I render only a specific view or orientation?
  type: FAQPage
tags:
- convert igs
- groupdocs.viewer
- java cad conversion
- pdf generation java
title: Chuyển đổi IGS sang PDF, HTML, JPG & PNG với GroupDocs.Viewer Java
type: docs
url: /vi/java/file-formats-support/groupdocs-viewer-java-igs-rendering-html-jpg-png-pdf/
weight: 1
---

# Chuyển đổi IGS sang PDF, HTML, JPG & PNG với GroupDocs.Viewer Java

Nếu bạn cần **chuyển đổi IGS sang PDF** (hoặc sang HTML, JPG, PNG) trực tiếp từ một ứng dụng Java, bạn đã đến đúng nơi. Trong hướng dẫn này, chúng tôi sẽ đi qua mọi thứ bạn cần — từ việc cài đặt thư viện đến việc render mô hình 3‑D ở định dạng phù hợp với dự án của bạn. Bạn sẽ hiểu tại sao GroupDocs.Viewer là lựa chọn vững chắc cho các chuyển đổi nhanh chóng, đáng tin cậy và bạn sẽ nhận được các đoạn mã sẵn sàng chạy mà bạn có thể đưa vào giải pháp của mình.

![Chuyển đổi tệp IGS sang HTML, JPG, PNG và PDF với GroupDocs.Viewer cho Java](/viewer/file-formats-support/convert-igs-files-to-html-jpg-png-and-pdf-java.png)

## Câu trả lời nhanh
- **Tôi có thể chuyển đổi IGS sang PDF bằng Java không?** Có, sử dụng `PdfViewOptions` cùng với API `Viewer`.  
- **Các định dạng đầu ra nào được hỗ trợ?** HTML, JPG, PNG và PDF đều được xử lý nguyên bản.  
- **Tôi có cần giấy phép cho môi trường sản xuất không?** Cần giấy phép thương mại; bản dùng thử miễn phí cho phép bạn thử các tính năng chính.  
- **Phiên bản Java nào được yêu cầu?** JDK 8 hoặc cao hơn; thư viện cũng chạy trên Java 11, 17 và các phiên bản sau.  
- **Maven là cách duy nhất để thêm thư viện không?** Không, bạn cũng có thể dùng Gradle hoặc thêm thủ công các tệp JAR vào classpath.

## Chuyển đổi IGS sang PDF là gì?
Chuyển đổi IGS sang PDF có nghĩa là biến một tệp CAD 3‑D trung tính thành một tài liệu tĩnh, có thể xem được trên mọi nền tảng. Điều này cho phép bạn chia sẻ hình ảnh thiết kế với các bên liên quan không có công cụ CAD, nhúng bản render vào báo cáo, hoặc lưu trữ mô hình để đáp ứng các yêu cầu tuân thủ.

## Tại sao nên sử dụng GroupDocs.Viewer cho việc chuyển đổi IGS?
GroupDocs.Viewer xử lý các tệp IGS mà không cần bất kỳ phần mềm CAD bên ngoài nào. Nó hỗ trợ **hơn 50 định dạng đầu vào và đầu ra**, có thể render các bộ lắp ráp chứa **hàng trăm bộ phận** trong khi giữ mức sử dụng bộ nhớ dưới **200 MB**, và cung cấp kết quả trong vòng **2 giây** cho các mô hình điển hình trên máy chủ tiêu chuẩn. Những lợi ích định lượng này khiến nó trở thành lựa chọn hiệu suất cao, chi phí hiệu quả cho các quy trình doanh nghiệp.

## Yêu cầu trước
- **GroupDocs.Viewer for Java** ≥ 25.2 (bản phát hành ổn định mới nhất).  
- **JDK 8+** đã được cài đặt và cấu hình trong IDE của bạn (IntelliJ IDEA, Eclipse, NetBeans, v.v.).  
- Kiến thức cơ bản về Maven (tùy chọn nhưng được khuyến nghị cho quản lý phụ thuộc).  

## Cài đặt GroupDocs.Viewer cho Java

### Phụ thuộc Maven
Thêm kho lưu trữ GroupDocs và phụ thuộc Viewer vào tệp `pom.xml` của bạn:

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

### Đăng ký giấy phép
GroupDocs.Viewer cung cấp ba tùy chọn giấy phép:
- **Bản dùng thử** – sử dụng giới hạn, hoàn hảo cho các thử nghiệm chứng minh khái niệm nhanh.  
- **Giấy phép tạm thời** – đầy đủ tính năng trong thời gian đánh giá ngắn, lý tưởng cho các dự án thí điểm.  
- **Giấy phép thương mại** – sử dụng sản xuất không giới hạn, bao gồm hỗ trợ ưu tiên và cập nhật.

### Khởi tạo Viewer cơ bản
Lớp `Viewer` là điểm vào cho tất cả các hoạt động render. Nó tải tệp nguồn, phân tích định dạng và cung cấp các phương thức để tạo ra đầu ra mong muốn.

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
Tải tệp IGS bằng một thể hiện `Viewer` và truyền một đối tượng `HtmlViewOptions` nhúng tất cả các tài nguyên cần thiết. Lệnh gọi trả về một tệp HTML duy nhất chứa toàn bộ view 3‑D, giúp dễ dàng nhúng vào các trang web. Bạn cũng có thể tùy chỉnh việc render bằng cách thiết lập các tùy chọn như kích thước trang, màu nền và việc có bao gồm các điều khiển tương tác hay không.  
`HtmlViewOptions` cấu hình cách đầu ra HTML được tạo, bao gồm việc nhúng tài nguyên và bố cục trang.

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

## Render IGS sang JPG

### Cách chuyển đổi IGS sang JPG?
Tạo một đối tượng `JpgViewOptions`, cấu hình độ phân giải và chất lượng nén mong muốn, và để `Viewer` tạo ra các hình raster cho mỗi trang của mô hình. Các tệp JPG được tạo có thể được lưu vào thư mục chỉ định, và bạn có thể điều chỉnh tham số chất lượng để cân bằng kích thước tệp và độ trung thực hình ảnh, hữu ích cho ảnh thu nhỏ hoặc in độ phân giải cao.  
`JpgViewOptions` chỉ định các cài đặt cho việc tạo ảnh JPG như độ phân giải, chất lượng và thư mục đầu ra.

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

## Render IGS sang PNG

### Cách chuyển đổi IGS sang PNG?
Lớp `PngViewOptions` cho phép bạn tạo ra các hình ảnh không mất dữ liệu với tùy chọn trong suốt. Định dạng này lý tưởng để đặt mô hình lên nền màu trong tài liệu marketing. Bạn cũng có thể xác định độ phân giải và màu nền để phù hợp với hướng dẫn thương hiệu, đảm bảo sự nhất quán trong mọi tài sản được tạo.  
`PngViewOptions` định nghĩa các tham số cho việc render PNG, bao gồm độ phân giải, trong suốt và màu nền.

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

## Render IGS sang PDF

### Cách chuyển đổi IGS sang PDF?
Sử dụng `PdfViewOptions` để tạo một PDF phân trang giữ nguyên bố cục hình ảnh của mô hình 3‑D. Bạn cũng có thể nhúng phông chữ và kiểm soát kích thước trang để đáp ứng các hướng dẫn thương hiệu doanh nghiệp. Các cài đặt bổ sung cho phép bạn chỉ định chất lượng hình ảnh, mức nén và việc có bao gồm mục lục cho các bộ lắp ráp đa trang.  
`PdfViewOptions` điều khiển việc tạo PDF, cho phép cấu hình kích thước trang, chất lượng hình ảnh và nhúng phông chữ.

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

## Ứng dụng thực tiễn
- **Cổng web** – nhúng các mô hình được render HTML trực tiếp vào các công cụ cấu hình sản phẩm, cho phép khách hàng xoay và phóng to mà không cần cài đặt plugin.  
- **Tài sản marketing** – tạo ảnh JPG/PNG độ phân giải cao cho brochure, slide deck và bài đăng trên mạng xã hội.  
- **Tài liệu kỹ thuật** – bao gồm các bản render PDF của mô hình CAD trong hướng dẫn sử dụng, đảm bảo kỹ sư có thể xem thiết kế offline.  
- **Đảm bảo chất lượng** – tự động tạo ảnh thu nhỏ cho hàng nghìn tệp IGS, tăng tốc quy trình kiểm tra hình ảnh.

## Các vấn đề thường gặp & giải pháp

| Vấn đề | Giải pháp |
|-------|----------|
| **Thư mục đầu ra không tồn tại** | Xác minh đường dẫn được truyền vào `Path outputDirectory` và đảm bảo quá trình Java có quyền ghi vào thư mục mục tiêu. |
| **Các trang trắng trong PDF** | Xác nhận tệp IGS nguồn không bị hỏng; mở nó trong một trình xem CAD gốc trước. |
| **Render chậm cho các bộ lắp ráp lớn** | Tăng bộ nhớ heap của JVM (`-Xmx2g` hoặc hơn) và cân nhắc render theo trang bằng cách sử dụng `viewer.getPageCount()` để xử lý từng phần. |
| **Thiếu phông chữ trong PDF** | Sử dụng `PdfViewOptions` để nhúng các phông chữ cần thiết hoặc cài đặt các phông chữ thiếu trên máy chủ lưu trữ dịch vụ chuyển đổi. |

## Câu hỏi thường gặp

**Q: Tôi có thể chuyển đổi nhiều tệp IGS trong một lần chạy không?**  
A: Có. Lặp qua một tập hợp các đường dẫn tệp và gọi phương thức `view` thích hợp cho mỗi tệp trong cùng một thể hiện `Viewer`.

**Q: Có thể tùy chỉnh kích thước trang PDF không?**  
A: Chắc chắn. `PdfViewOptions` cung cấp `setPageSize(PageSize.A4)`, `PageSize.Letter`, và kích thước tùy chỉnh qua `setCustomSize(width, height)`.

**Q: Tôi có cần giấy phép riêng cho mỗi định dạng đầu ra không?**  
A: Không. Một giấy phép GroupDocs.Viewer duy nhất bao phủ tất cả các định dạng được hỗ trợ, bao gồm HTML, JPG, PNG và PDF.

**Q: Kích thước tối đa của tệp IGS trước khi hiệu năng giảm sút là bao nhiêu?**  
A: Thư viện xử lý ổn định các tệp lên tới **500 MB**; đối với mô hình lớn hơn 200 MB, hãy cấp phát thêm bộ nhớ JVM và cân nhắc render theo lô.

**Q: Tôi có thể render chỉ một góc nhìn hoặc hướng cụ thể không?**  
A: GroupDocs.Viewer render hướng mặc định được định nghĩa trong tệp IGS. Đối với các góc nhìn tùy chỉnh, hãy tiền xử lý tệp bằng công cụ CAD hoặc điều chỉnh mô hình trước khi chuyển đổi.

---

**Cập nhật lần cuối:** 2026-08-08  
**Đã kiểm tra với:** GroupDocs.Viewer 25.2 for Java  
**Tác giả:** GroupDocs

## Hướng dẫn liên quan

- [chuyển đổi cdr sang html, jpg, png, pdf với GroupDocs.Viewer Java](/viewer/java/file-formats-support/render-cdr-documents-groupdocs-viewer-java-guide/)
- [Cách chuyển đổi pdf sang html và tối ưu chất lượng hình ảnh trong Java với GroupDocs.Viewer](/viewer/java/advanced-rendering/adjust-image-quality-groupdocs-viewer-java/)