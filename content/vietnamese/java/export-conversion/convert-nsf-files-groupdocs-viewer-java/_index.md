---
date: '2026-05-26'
description: Tìm hiểu cách chuyển đổi NSF sang PDF và các định dạng khác (HTML, JPG,
  PNG) bằng cách sử dụng GroupDocs.Viewer cho Java. Hướng dẫn chi tiết từng bước kèm
  các mẹo thực hành tốt nhất.
keywords:
- convert nsf to pdf
- how to convert nsf
- java convert lotus notes
schemas:
- author: GroupDocs
  dateModified: '2026-05-26'
  description: Learn how to convert nsf to pdf and other formats (HTML, JPG, PNG)
    using GroupDocs.Viewer for Java. Step‑by‑step guide with best‑practice tips.
  headline: convert nsf to pdf with GroupDocs.Viewer for Java
  type: TechArticle
- description: Learn how to convert nsf to pdf and other formats (HTML, JPG, PNG)
    using GroupDocs.Viewer for Java. Step‑by‑step guide with best‑practice tips.
  name: convert nsf to pdf with GroupDocs.Viewer for Java
  steps:
  - name: '**Web‑Based Document Sharing:** Convert NSF to HTML for instant in‑browser
      viewing without installing Notes.'
    text: '**Web‑Based Document Sharing:** Convert NSF to HTML for instant in‑browser
      viewing without installing Notes.'
  - name: '**Image Archiving:** Store page‑by‑page JPG/PNG snapshots for thumbnail
      galleries or OCR pipelines.'
    text: '**Image Archiving:** Store page‑by‑page JPG/PNG snapshots for thumbnail
      galleries or OCR pipelines.'
  - name: '**Universal Access:** Use PDF conversion to provide a single, secure file
      that can be opened on any device, meeting compliance requirements.'
    text: '**Universal Access:** Use PDF conversion to provide a single, secure file
      that can be opened on any device, meeting compliance requirements.'
  type: HowTo
- questions:
  - answer: '`PdfViewOptions` preserves most annotations automatically; just render
      the document with these options and the resulting PDF mirrors the original layout.'
    question: How do I convert an NSF file to PDF without losing annotations?
  - answer: Yes. Provide credentials through `LoadOptions` before creating the `Viewer`
      instance.
    question: Can I convert password‑protected NSF files?
  - answer: JDK 11 or newer offers improved garbage collection and concurrency, which
      speeds up batch conversions.
    question: What Java version gives the best performance?
  - answer: Configure `JpgViewOptions.setResolution(int dpi)` or `PngViewOptions.setResolution(int
      dpi)` before calling `viewer.view(options)`.
    question: Is it possible to set a custom DPI for JPG/PNG output?
  - answer: Yes. Use the `Stream` overload of the view options to write the result
      straight to `HttpServletResponse.getOutputStream()`.
    question: Does GroupDocs.Viewer support streaming the output directly to an HTTP
      response?
  type: FAQPage
title: Chuyển đổi NSF sang PDF với GroupDocs.Viewer cho Java
type: docs
url: /vi/java/export-conversion/convert-nsf-files-groupdocs-viewer-java/
weight: 1
---

# Chuyển Đổi Tệp NSF Sang Nhiều Định Dạng Sử Dụng GroupDocs.Viewer cho Java

Trong hướng dẫn toàn diện này, bạn sẽ học **cách chuyển đổi nsf sang pdf** và cũng hiển thị các tệp NSF thành HTML, JPG và PNG bằng GroupDocs.Viewer cho Java. Cho dù bạn cần lưu trữ cơ sở dữ liệu Lotus Notes, hiển thị chúng trong trình duyệt, hoặc tạo các bản xem trước hình ảnh, bài hướng dẫn này sẽ đưa bạn qua mọi bước — từ cài đặt môi trường đến chi tiết mức độ mã — để bạn có thể thực hiện chuyển đổi trong vài phút.

![Chuyển Đổi Tệp NSF Sang HTML, JPG, PNG, và PDF với GroupDocs.Viewer cho Java](/viewer/export-conversion/convert-nsf-files-to-html-jpg-png-pdf-java.png)
[Chuyển Đổi Tệp NSF Sang HTML, JPG, PNG, và PDF với GroupDocs.Viewer cho Java](/viewer/export-conversion/convert-nsf-files-to-html-jpg-png-pdf-java.png)

## Câu Trả Lời Nhanh

- **Mục đích sử dụng chính là gì?** Hiển thị các tệp NSF thành PDF, HTML, JPG hoặc PNG cho web, lưu trữ hoặc chia sẻ.  
- **Thư viện nào thực hiện việc chuyển đổi?** GroupDocs.Viewer cho Java.  
- **Tôi có cần giấy phép không?** Có bản dùng thử miễn phí; giấy phép đầy đủ cần thiết cho môi trường sản xuất.  
- **Phiên bản Java yêu cầu là gì?** JDK 8 trở lên.  
- **Tôi có thể xử lý hàng loạt nhiều tệp NSF không?** Có – bao bọc logic hiển thị trong vòng lặp và quản lý tài nguyên bằng try‑with‑resources.

## “convert nsf to pdf” là gì?

Việc chuyển đổi một tệp NSF (cơ sở dữ liệu Lotus Notes) sang PDF tạo ra một tài liệu tĩnh, có thể đọc được trên mọi nền tảng, giữ nguyên bố cục, phông chữ và đồ họa gốc mà không cần client Notes. Định dạng này lý tưởng cho việc lưu trữ pháp lý, phân phối an toàn và lưu trữ lâu dài vì các tệp PDF có thể mở trên bất kỳ hệ điều hành hoặc thiết bị nào.

## Tại sao nên chuyển đổi NSF sang PDF và các định dạng khác?

Việc chuyển đổi các tệp NSF thành PDF, HTML, JPG hoặc PNG mở ra khả năng truy cập toàn cầu, giữ nguyên độ trung thực hình ảnh và cho phép tích hợp liền mạch với các ứng dụng web và di động hiện đại. PDF giữ nguyên bố cục trang, HTML cung cấp khả năng xem ngay trong trình duyệt, và JPG/PNG cung cấp các ảnh chụp độ phân giải cao cho hình thu nhỏ hoặc nhúng.

## Yêu Cầu Trước

- **Bộ Công Cụ Phát Triển Java (JDK) 8+** – JDK 11 hoặc mới hơn được khuyến nghị để cải thiện hiệu suất thu gom rác.  
- **Maven** – để quản lý phụ thuộc.  
- **GroupDocs.Viewer cho Java** – phiên bản dùng thử hoặc có giấy phép.  
- Kiến thức cơ bản về I/O tệp Java và cấu trúc dự án Maven.

## Cài Đặt GroupDocs.Viewer cho Java

### Cấu Hình Maven

Thêm phụ thuộc GroupDocs.Viewer vào `pom.xml` của bạn. Điều này sẽ kéo về tất cả các tệp nhị phân và thư viện phụ thuộc cần thiết.

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

### Nhận Giấy Phép

Để mở khóa đầy đủ chức năng bạn có thể:

- **Dùng Thử Miễn Phí:** Đánh giá các tính năng cốt lõi mà không cần khóa giấy phép.  
- **Giấy Phép Tạm Thời:** Yêu cầu một khóa có thời hạn để thử nghiệm.  
- **Mua Đầy Đủ:** Nhận giấy phép sản xuất để sử dụng không giới hạn.

### Khởi Tạo Cơ Bản

`Viewer` là lớp cốt lõi chịu trách nhiệm hiển thị tài liệu sang định dạng đầu ra mong muốn. Khởi tạo nó với giấy phép và đường dẫn tệp trong một khối try‑with‑resources để đảm bảo giải phóng tài nguyên đúng cách.

```java
import com.groupdocs.viewer.Viewer;

public class InitializeViewer {
    public static void main(String[] args) {
        try (Viewer viewer = new Viewer("YOUR_DOCUMENT_DIRECTORY/SAMPLE_NSF")) {
            // Viewer is ready for use.
        }
    }
}
```

## Cách Chuyển Đổi NSF sang PDF

Để chuyển đổi một tài liệu NSF sang PDF, trước tiên tạo một thể hiện `Viewer` trỏ tới tệp nguồn. Sau đó cấu hình `PdfViewOptions` để xác định các đặc tính đầu ra như kích thước trang, mức nén và việc nhúng phông chữ. Cuối cùng, gọi `viewer.view(pdfOptions)` để hiển thị toàn bộ tài liệu thành một tệp PDF duy nhất sẵn sàng cho việc phân phối.

`PdfViewOptions` chỉ định các cài đặt đặc thù cho PDF như kích thước trang và mức nén.

```java
Path pageFilePathFormat = outputDirectory.resolve("NSF_result.pdf");
```
```java
import com.groupdocs.viewer.options.PdfViewOptions;

try (Viewer viewer = new Viewer("YOUR_DOCUMENT_DIRECTORY/SAMPLE_NSF", loadOptions)) {
    PdfViewOptions options = new PdfViewOptions(pageFilePathFormat);
    viewer.view(options);  // Convert to PDF.
}
```

## Hiển Thị NSF thành HTML

### Tổng Quan

Chuyển đổi các tài liệu NSF thành các trang HTML tự chứa, nhúng hình ảnh và CSS để hiển thị chính xác trên màn hình.

### Hướng Dẫn Từng Bước

#### 1. Thiết Lập Thư Mục Đầu Ra và Đường Dẫn Tệp

Xác định thư mục nơi các tệp HTML sẽ được lưu.

```java
import java.nio.file.Path;
import java.nio.file.Paths;

Path outputDirectory = Paths.get("YOUR_OUTPUT_DIRECTORY");
Path pageFilePathFormat = outputDirectory.resolve("NSF_result.html");
```

#### 2. Cấu Hình Load Options

`LoadOptions` cho phép bạn tinh chỉnh việc tải tài nguyên, chẳng hạn đặt thời gian chờ cho các tài nguyên bên ngoài.

```java
import com.groupdocs.viewer.options.LoadOptions;

LoadOptions loadOptions = new LoadOptions();
loadOptions.setResourceLoadingTimeout(100);  // Set timeout for loading resources.
```

#### 3. Khởi Tạo Viewer và Hiển Thị

`Viewer` xử lý tệp NSF và ghi các tệp HTML vào thư mục đích.

```java
import com.groupdocs.viewer.Viewer;
import com.groupdocs.viewer.options.HtmlViewOptions;

try (Viewer viewer = new Viewer("YOUR_DOCUMENT_DIRECTORY/SAMPLE_NSF", loadOptions)) {
    HtmlViewOptions options = HtmlViewOptions.forEmbeddedResources(pageFilePathFormat);
    viewer.view(options);  // Render the document to HTML.
}
```

## Hiển Thị NSF thành JPG

### Tổng Quan

Tạo các hình ảnh JPG chất lượng cao từ mỗi trang của tài liệu NSF, hữu ích cho việc xem trước hoặc nhúng vào quy trình làm việc tập trung vào hình ảnh.

#### 1. Xác Định Đường Dẫn Đầu Ra

Chỉ định mẫu đặt tên như `output_page_{0}.jpg` trong đó `{0}` là số trang.

```java
Path pageFilePathFormat = outputDirectory.resolve("NSF_result_{0}.jpg");
```

#### 2. Cấu Hình và Hiển Thị

`JpgViewOptions` định nghĩa các cài đặt cho đầu ra hình ảnh JPEG, bao gồm độ phân giải và chất lượng. Tạo `JpgViewOptions`, đặt DPI mong muốn, và gọi `viewer.view(options)`.

```java
import com.groupdocs.viewer.options.JpgViewOptions;

try (Viewer viewer = new Viewer("YOUR_DOCUMENT_DIRECTORY/SAMPLE_NSF", loadOptions)) {
    JpgViewOptions options = new JpgViewOptions(pageFilePathFormat);
    viewer.view(options);  // Render to JPG.
}
```

## Hiển Thị NSF thành PNG

### Tổng Quan

Tạo các hình ảnh PNG không mất dữ liệu, giữ lại mọi chi tiết của các trang NSF gốc.

#### 1. Đặt Đường Dẫn Đầu Ra

Sử dụng mẫu như `nsf_page_{0}.png` để phân trang tự động.

```java
Path pageFilePathFormat = outputDirectory.resolve("NSF_result_{0}.png");
```

#### 2. Hiển Thị Tài Liệu

`PngViewOptions` cấu hình các tham số đầu ra PNG như độ phân giải và độ sâu màu. Cấu hình `PngViewOptions` (ví dụ, đặt `setResolution(300)`) và hiển thị.

```java
import com.groupdocs.viewer.options.PngViewOptions;

try (Viewer viewer = new Viewer("YOUR_DOCUMENT_DIRECTORY/SAMPLE_NSF", loadOptions)) {
    PngViewOptions options = new PngViewOptions(pageFilePathFormat);
    viewer.view(options);  // Convert to PNG.
}
```

## Ứng Dụng Thực Tế

1. **Chia Sẻ Tài Liệu Trên Web:** Chuyển NSF sang HTML để xem ngay trong trình duyệt mà không cần cài đặt Notes.  
2. **Lưu Trữ Hình Ảnh:** Lưu các ảnh chụp JPG/PNG từng trang cho bộ sưu tập hình thu nhỏ hoặc quy trình OCR.  
3. **Truy Cập Toàn Cầu:** Sử dụng chuyển đổi PDF để cung cấp một tệp duy nhất, an toàn, có thể mở trên bất kỳ thiết bị nào, đáp ứng yêu cầu tuân thủ.

## Các Yếu Tố Hiệu Suất

- **Tải Tài Nguyên:** Điều chỉnh `setResourceLoadingTimeout` dựa trên độ trễ mạng để tránh treo.  
- **Quản Lý Bộ Nhớ:** Sử dụng try‑with‑resources cho các thể hiện `Viewer`; điều này tự động giải phóng tài nguyên gốc.  
- **Xử Lý Hàng Loạt:** Đối với các lô lớn, xử lý tệp tuần tự hoặc bằng các luồng song song, giám sát việc sử dụng heap để không vượt quá giới hạn bộ nhớ của JVM.

## Phần Câu Hỏi Thường Gặp

**Định dạng tốt nhất để chuyển đổi tài liệu NSF là gì?**  
- Nó phụ thuộc vào mục đích sử dụng: HTML cho các cổng web, PDF cho việc phân phối toàn cầu, JPG/PNG cho quy trình làm việc dựa trên hình ảnh.

**Làm thế nào để xử lý các tệp NSF lớn một cách hiệu quả?**  
- Tinh chỉnh `LoadOptions` (ví dụ, tăng `setResourceLoadingTimeout`), xử lý tệp theo các lô nhỏ hơn, và tái sử dụng một thể hiện `Viewer` duy nhất khi có thể.

**Tôi có thể tùy chỉnh chất lượng đầu ra trong các định dạng hình ảnh không?**  
- Có. Đặt DPI, mức nén và độ sâu màu qua `JpgViewOptions` hoặc `PngViewOptions` trước khi hiển thị.

**Nếu quá trình chuyển đổi thất bại, tôi nên làm gì?**  
- Kiểm tra lại đường dẫn tệp, đảm bảo tệp NSF không bị hỏng, và tham khảo log của GroupDocs.Viewer để biết mã lỗi chi tiết. Cập nhật lên phiên bản thư viện mới nhất thường giải quyết các vấn đề tương thích.

**Có hỗ trợ chuyển đổi hàng loạt không?**  
- Chắc chắn. Bao bọc logic hiển thị trong một vòng lặp `for` hoặc Java Stream để tự động xử lý nhiều tệp NSF.

## Câu Hỏi Thường Gặp

**Q: Làm thế nào để chuyển đổi tệp NSF sang PDF mà không mất chú thích?**  
A: `PdfViewOptions` tự động giữ lại hầu hết các chú thích; chỉ cần hiển thị tài liệu với các tùy chọn này và PDF kết quả sẽ phản ánh bố cục gốc.

**Q: Tôi có thể chuyển đổi các tệp NSF được bảo vệ bằng mật khẩu không?**  
A: Có. Cung cấp thông tin đăng nhập qua `LoadOptions` trước khi tạo thể hiện `Viewer`.

**Q: Phiên bản Java nào cho hiệu suất tốt nhất?**  
A: JDK 11 hoặc mới hơn cung cấp bộ thu gom rác và khả năng đồng thời cải thiện, giúp tăng tốc chuyển đổi hàng loạt.

**Q: Có thể đặt DPI tùy chỉnh cho đầu ra JPG/PNG không?**  
A: Cấu hình `JpgViewOptions.setResolution(int dpi)` hoặc `PngViewOptions.setResolution(int dpi)` trước khi gọi `viewer.view(options)`.

**Q: GroupDocs.Viewer có hỗ trợ truyền luồng đầu ra trực tiếp tới phản hồi HTTP không?**  
A: Có. Sử dụng phiên bản overload `Stream` của các tùy chọn hiển thị để ghi kết quả trực tiếp vào `HttpServletResponse.getOutputStream()`.

## Kết Luận

Bạn đã có một lộ trình đầy đủ tính năng để **chuyển đổi nsf sang pdf** và hiển thị các tệp NSF thành HTML, JPG và PNG bằng GroupDocs.Viewer cho Java. Bằng cách thực hiện các bước trên, bạn có thể tích hợp chuyển đổi tài liệu mạnh mẽ vào bất kỳ ứng dụng Java nào, tự động hoá các công việc hàng loạt và cung cấp nội dung ở định dạng phù hợp nhất với nhu cầu của người dùng. Khám phá các tính năng bổ sung của Viewer như đánh dấu bản quyền, phông chữ tùy chỉnh và xử lý đa trang để làm phong phú hơn giải pháp của bạn.

---

**Cập Nhật Cuối Cùng:** 2026-05-26  
**Đã Kiểm Tra Với:** GroupDocs.Viewer 25.2  
**Tác Giả:** GroupDocs

## Hướng Dẫn Liên Quan

- [groupdocs viewer java: Chuyển Đổi Tài Liệu sang PDF – Hướng Dẫn Toàn Diện](/viewer/java/export-conversion/convert-documents-pdf-groupdocs-viewer-java/)
- [convert odf html java – Chuyển Đổi ODF sang HTML, JPG, PNG, PDF Sử Dụng GroupDocs.Viewer cho Java](/viewer/java/export-conversion/convert-odf-documents-groupdocs-viewer-java/)
- [Chuyển Đổi PST sang HTML, JPG, PNG, PDF Sử Dụng GroupDocs.Viewer cho Java](/viewer/java/export-conversion/convert-pst-ost-groupdocs-viewer-java/)