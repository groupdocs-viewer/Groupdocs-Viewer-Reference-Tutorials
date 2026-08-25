---
date: '2026-08-25'
description: Tìm hiểu cách chuyển đổi Numbers bằng GroupDocs.Viewer for Java, chuyển
  các tệp Apple Numbers sang PDF, HTML, JPG hoặc PNG. Bao gồm hướng dẫn cài đặt, các
  bước chuyển đổi tài liệu java và mẹo hiển thị trên web.
keywords:
- how to convert numbers
- java document conversion
- display numbers web
- java spreadsheet pdf
lastmod: '2026-08-25'
og_description: Tìm hiểu cách chuyển đổi Numbers bằng GroupDocs.Viewer for Java, chuyển
  các tệp Apple Numbers sang PDF, HTML, JPG hoặc PNG. Bao gồm hướng dẫn cài đặt, các
  bước chuyển đổi tài liệu java và mẹo hiển thị trên web.
og_image_alt: 'Developer guide: Convert Numbers to PDF, HTML, JPG, PNG using GroupDocs.Viewer
  for Java'
og_title: Cách chuyển đổi Numbers bằng GroupDocs.Viewer for Java
schemas:
- author: GroupDocs
  dateModified: '2026-08-25'
  description: Learn how to convert numbers with GroupDocs.Viewer for Java, turning
    Apple Numbers files into PDF, HTML, JPG, or PNG. Includes setup, java document
    conversion steps, and web display tips.
  headline: How to convert numbers with GroupDocs.Viewer for Java
  type: TechArticle
- questions:
  - answer: Over 100 formats, including DOCX, XLSX, PDF, HTML, and Apple Numbers,
      with full rendering capabilities for each.
    question: What file formats does GroupDocs.Viewer support?
  - answer: Stream the conversion page‑by‑page, use `options.setPageCount()` to limit
      memory usage, and consider compressing the output PDF.
    question: How do I handle large Numbers files efficiently?
  - answer: Yes—purchase a commercial license to remove trial limitations and obtain
      production‑grade support.
    question: Can GroupDocs.Viewer be used in a commercial project?
  - answer: Absolutely. Adjust `JpgViewOptions.setQuality(int)` or `PngViewOptions.setResolution(int)`
      to meet your size‑quality requirements.
    question: Is it possible to customize the output quality of images?
  - answer: Visit the [GroupDocs documentation](https://docs.groupdocs.com/viewer/java/)
      for deep‑dive guides, sample projects, and API reference details.
    question: Where can I find more advanced usage examples?
  type: FAQPage
tags:
- convert numbers
- GroupDocs.Viewer
- Java document processing
title: Cách chuyển đổi Numbers bằng GroupDocs.Viewer for Java
type: docs
url: /vi/java/file-formats-support/render-numbers-groupdocs-viewer-java/
weight: 1
---

# Cách chuyển đổi Numbers với GroupDocs.Viewer cho Java

Hiển thị bảng tính Apple Numbers trên web hoặc trong ứng dụng máy tính để bàn có thể cảm giác như một câu đố, đặc biệt khi bạn cần **chuyển đổi Numbers sang PDF** hoặc nhúng chúng dưới dạng hình ảnh cho báo cáo. Trong hướng dẫn này, bạn sẽ học chính xác **cách chuyển đổi Numbers** sang PDF, HTML, JPG và PNG bằng **GroupDocs.Viewer cho Java**. Chúng tôi sẽ hướng dẫn cài đặt dự án, render ở mức mã, và các kịch bản thực tế để bạn có thể xây dựng các pipeline preview hoặc lưu trữ mạnh mẽ trong vài phút.

![Render tài liệu Apple Numbers với GroupDocs.Viewer cho Java](/viewer/file-formats-support/render-apple-numbers-documents-java.png)

[Render tài liệu Apple Numbers với GroupDocs.Viewer cho Java](/viewer/file-formats-support/render-apple-numbers-documents-java.png)

### Bạn sẽ học gì
- Cách thêm GroupDocs.Viewer vào dự án Java dựa trên Maven.  
- Mã từng bước để **chuyển đổi Numbers sang pdf**, **chuyển đổi Numbers sang html**, **chuyển đổi Numbers sang jpg**, và **chuyển đổi Numbers sang png**.  
- Khi nào nên chọn mỗi định dạng đầu ra cho các cổng web, quy trình email, hoặc hệ thống quản lý tài liệu.  

## Câu trả lời nhanh
- **Tôi có thể chuyển đổi Numbers sang PDF bằng Java không?** Có – khởi tạo `Viewer` và gọi `PdfViewOptions` để nhận được PDF sẵn sàng lưu trữ.  
- **Định dạng nào cung cấp preview web phong phú nhất?** HTML, vì nó giữ các bảng, công thức và kiểu dáng tương tác.  
- **Tôi có cần giấy phép cho môi trường production không?** Cần giấy phép thương mại cho bất kỳ triển khai không dùng bản thử nghiệm nào.  
- **Có hỗ trợ chuyển đổi hình ảnh không?** Chắc chắn – sử dụng `JpgViewOptions` hoặc `PngViewOptions` để có các ảnh chụp chất lượng cao.  
- **Yêu cầu phiên bản Java nào?** Java 8+ và Maven để quản lý phụ thuộc.  

## Yêu cầu trước
- Bộ công cụ phát triển Java (JDK) 8 hoặc mới hơn được cài đặt trên máy của bạn.  
- Maven để quản lý phụ thuộc và xây dựng dự án.  
- Kiến thức cơ bản về I/O file Java, đường dẫn và xử lý ngoại lệ.  

## Cài đặt GroupDocs.Viewer cho Java

### Cài đặt với Maven
Thêm repository của GroupDocs và phụ thuộc Viewer vào file `pom.xml` của bạn. Khối này phải giữ nguyên như đã hiển thị:

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

### Mua giấy phép
- **Dùng thử miễn phí:** Tất cả tính năng, không cần thẻ tín dụng.  
- **Giấy phép tạm thời:** Yêu cầu khóa thời hạn để thử nghiệm mở rộng.  
- **Mua đầy đủ:** Nhận giấy phép vĩnh viễn cho mục đích thương mại.  

## Lớp Viewer là gì?
Lớp `Viewer` là động cơ cốt lõi của GroupDocs.Viewer, tải tài liệu và render nó sang định dạng đầu ra yêu cầu. Nó trừu tượng hoá việc xử lý loại file để bạn có thể tập trung vào logic nghiệp vụ thay vì phân tích nội bộ bảng tính.

## Cách chuyển đổi Numbers sang HTML với GroupDocs.Viewer cho Java?
`HtmlViewOptions` chỉ định các cài đặt cho việc render HTML, như nhúng tài nguyên hoặc liên kết tới các file bên ngoài.  
Tải file Numbers, cấu hình các tùy chọn HTML, và gọi `viewer.view()`. Phương thức `HtmlViewOptions.forEmbeddedResources()` gộp CSS và hình ảnh trực tiếp vào HTML, khiến kết quả lý tưởng để nhúng vào trang web mà không cần tài nguyên bổ sung.

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

- **Tại sao điều này quan trọng:** Tài nguyên nhúng giữ preview tự chứa, loại bỏ các liên kết ảnh bị hỏng và đơn giản hoá việc triển khai CDN.  

## Cách chuyển đổi Numbers sang JPG với GroupDocs.Viewer cho Java?
`JpgViewOptions` cấu hình đầu ra JPEG, cho phép điều chỉnh chất lượng và kích thước cho mỗi trang được render.  
Bạn có thể chuyển mỗi trang bảng tính thành một ảnh chụp JPEG. Điều chỉnh thuộc tính `quality` để cân bằng kích thước file và độ trung thực hình ảnh, hữu ích khi cần ảnh nhẹ cho mạng xã hội hoặc bản tin email.

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

- **Mẹo:** Để xử lý nhanh hơn các workbook lớn, giảm chất lượng xuống 70 % – ảnh hưởng về hình ảnh là tối thiểu trong khi kích thước file giảm đáng kể.  

## Cách chuyển đổi Numbers sang PNG với GroupDocs.Viewer cho Java?
`PngViewOptions` cấu hình đầu ra PNG, hỗ trợ nén không mất dữ liệu và cài đặt độ phân giải cho hình ảnh chất lượng cao.  
PNG cung cấp nén không mất dữ liệu, giữ nguyên mọi pixel như khi render. Sử dụng thuộc tính `resolution` để tăng DPI khi bạn cần đồ họa sẵn sàng in cho báo cáo hoặc PDF.

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

- **Mẹo chuyên nghiệp:** Đặt `options.setResolution(300)` để có đầu ra độ phân giải cao, nét trên các trang in.  

## Cách chuyển đổi Numbers sang PDF với GroupDocs.Viewer cho Java?
`PdfViewOptions` định nghĩa các tùy chọn render PDF, bao gồm nhúng phông chữ, nén và kiểm soát kích thước trang.  
Đối tượng `PdfViewOptions` cho phép bạn nhúng phông chữ, kiểm soát kích thước trang và giữ nguyên bố cục gốc của workbook Numbers. Quá trình chuyển đổi thực hiện trong một lần gọi, tạo ra PDF có thể tìm kiếm, không thể chỉnh sửa, phù hợp cho lưu trữ hoặc tuân thủ.

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

- **Cấu hình quan trọng:** Bật `options.setCompress(true)` để giảm kích thước PDF mà không làm giảm chất lượng, điều này rất cần thiết cho kho tài liệu quy mô lớn.  

## Tại sao nên sử dụng GroupDocs.Viewer cho Java?
GroupDocs.Viewer hỗ trợ **hơn 100 định dạng file**, bao gồm Apple Numbers, và có thể render các bảng tính hàng trăm trang mà không cần tải toàn bộ file vào bộ nhớ. Các benchmark cho thấy một file Numbers 250 trang được chuyển đổi sang PDF trong chưa tới 8 giây trên CPU tiêu chuẩn 2.5 GHz, mang lại tốc độ và độ tin cậy cho các pipeline doanh nghiệp.

## Ứng dụng thực tế
- **Tích hợp web:** Render sang HTML cho một trình xem bảng tính tương tác hoạt động trên mọi trình duyệt mà không cần plugin.  
- **Chia sẻ nội dung:** Chuyển đổi sang JPG/PNG để nhúng nhanh hình ảnh trong bản tin, ứng dụng chat, hoặc feed xã hội.  
- **DMS doanh nghiệp:** Sử dụng **cách chuyển đổi Numbers** sang PDF để lưu phiên bản không thể chỉnh sửa, có thể tìm kiếm của bảng tính cho mục đích tuân thủ và theo dõi kiểm toán.  

## Cân nhắc về hiệu năng
- **Quản lý tài nguyên:** Luôn khởi tạo `Viewer` trong khối try‑with‑resources (như ví dụ) để tài nguyên gốc được giải phóng kịp thời.  
- **Workbook lớn:** Xử lý từng trang và stream đầu ra để giữ mức sử dụng bộ nhớ dưới 100 MB, ngay cả với file 500 trang.  
- **An toàn đa luồng:** Tạo một thể hiện `Viewer` riêng cho mỗi luồng; lớp này không thread‑safe, nên chia sẻ một thể hiện có thể gây race condition.  

## Những lỗi thường gặp và khắc phục
- **Phông chữ thiếu:** Nếu PDF tạo ra trông khác, hãy đảm bảo các phông chữ cần thiết có trên server hoặc nhúng chúng bằng `PdfViewOptions.setEmbedFonts(true)`.  
- **Trang trắng:** Kiểm tra file Numbers không được bảo vệ bằng mật khẩu; hiện tại GroupDocs.Viewer không giải mã workbook được bảo vệ.  
- **Lỗi hết bộ nhớ:** Đối với các file cực lớn, bật `options.setPageCount(1)` để render từng trang một và sau đó kết hợp kết quả.  

## Câu hỏi thường gặp
**Q: GroupDocs.Viewer hỗ trợ những định dạng file nào?**  
A: Hơn 100 định dạng, bao gồm DOCX, XLSX, PDF, HTML và Apple Numbers, với khả năng render đầy đủ cho mỗi loại.  

**Q: Làm sao để xử lý các file Numbers lớn một cách hiệu quả?**  
A: Stream quá trình chuyển đổi từng trang, sử dụng `options.setPageCount()` để giới hạn việc dùng bộ nhớ, và cân nhắc nén PDF đầu ra.  

**Q: GroupDocs.Viewer có thể được sử dụng trong dự án thương mại không?**  
A: Có—mua giấy phép thương mại để loại bỏ giới hạn bản thử nghiệm và nhận hỗ trợ cấp production.  

**Q: Có thể tùy chỉnh chất lượng đầu ra của hình ảnh không?**  
A: Chắc chắn. Điều chỉnh `JpgViewOptions.setQuality(int)` hoặc `PngViewOptions.setResolution(int)` để đáp ứng yêu cầu về kích thước‑chất lượng.  

**Q: Tôi có thể tìm các ví dụ sử dụng nâng cao ở đâu?**  
A: Truy cập [GroupDocs documentation](https://docs.groupdocs.com/viewer/java/) để xem các hướng dẫn chi tiết, dự án mẫu và chi tiết tham chiếu API.  

## Bước tiếp theo
Thử nghiệm các tùy chọn ở trên, sau đó khám phá các tùy chỉnh bổ sung như thêm watermark vào PDF, bảo vệ bằng mật khẩu, hoặc tích hợp viewer vào dịch vụ REST Spring Boot. Tài liệu [GroupDocs documentation](https://docs.groupdocs.com/viewer/java/) cung cấp danh mục đầy đủ các tính năng bạn có thể kết hợp.  

## Tài nguyên
- **Tài liệu:** [GroupDocs.Viewer Java Docs](https://docs.groupdocs.com/viewer/java/)  
- **Tài liệu GroupDocs:** [GroupDocs documentation](https://docs.groupdocs.com/viewer/java/)  
- **Tham chiếu API:** [API reference](https://reference.groupdocs.com/viewer/java/)  
- **Tham chiếu API GroupDocs:** [GroupDocs API Reference](https://reference.groupdocs.com/viewer/java/)  
- **Tải xuống:** [Get GroupDocs.Viewer](https://releases.groupdocs.com/viewer/java/)  
- **Mua giấy phép:** [Buy a License](https://purchase.groupdocs.com/buy)  
- **Dùng thử miễn phí:** [Start Your Free Trial](https://releases.groupdocs.com/viewer/java/)  
- **Giấy phép tạm thời:** [Request Here](https://purchase.groupdocs.com/temporary-license/)  
- **Diễn đàn hỗ trợ:** [Join the Discussion](https://forum.groupdocs.com/c/viewer/9)

---

**Cập nhật lần cuối:** 2026-08-25  
**Kiểm thử với:** GroupDocs.Viewer 25.2 for Java  
**Tác giả:** GroupDocs

## Hướng dẫn liên quan
- [Cách chuyển đổi Excel sang HTML, JPG, PNG và PDF bằng GroupDocs.Viewer Java](/viewer/java/rendering-basics/groupdocs-viewer-java-excel-to-html-jpg-png-pdf/)
- [Cách chuyển đổi Excel sang HTML và Render các hàng & cột ẩn trong Java với GroupDocs.Viewer](/viewer/java/advanced-rendering/render-hidden-rows-columns-java-groupdocs-viewer/)
- [Hướng dẫn render tài liệu Java - Chuyển đổi file sang HTML, PDF & Images](/viewer/java/rendering-basics/)