---
date: '2026-10-10'
description: Tìm hiểu cách chuyển đổi zip sang html bằng GroupDocs.Viewer Java, đặt
  số mục mỗi trang, nhúng tài nguyên html, và chuyển đổi hàng loạt các tệp lưu trữ
  một cách hiệu quả.
images:
- /java/export-conversion/groupdocs-viewer-java-convert-archives-html/og-image.png
keywords:
- how to convert zip
- convert archive to html
- java convert zip html
lastmod: '2026-10-10'
og_description: Tìm hiểu cách chuyển đổi zip sang html với GroupDocs.Viewer Java,
  nhúng tài nguyên, đặt số mục mỗi trang, và xử lý hàng loạt các tệp lưu trữ để có
  các bản xem trước web nhanh chóng và di động.
og_image_alt: 'Developer guide: convert zip to HTML with GroupDocs.Viewer Java, showing
  pagination and embedded resources'
og_title: Chuyển đổi zip sang HTML với phân trang bằng GroupDocs.Viewer Java
schemas:
- author: GroupDocs
  dateModified: '2026-10-10'
  description: Learn how to convert zip to html using GroupDocs.Viewer Java, set items
    per page, embed resources html, and batch convert archives efficiently.
  headline: Convert zip to html and set items per page with GroupDocs.Viewer Java
  type: TechArticle
- questions:
  - answer: GroupDocs.Viewer Java is a server‑side library that renders over 50 document
      and archive formats—including ZIP and RAR—into HTML, PDF, or image files without
      requiring external applications.
    question: What is GroupDocs.Viewer Java?
  - answer: Visit the [free trial link](https://releases.groupdocs.com/viewer/java/)
      to download and test.
    question: How can I obtain a free trial of GroupDocs.Viewer?
  - answer: Yes, the viewer supports PDFs, Word, Excel, PowerPoint, and 35+ additional
      formats.
    question: Can I convert other document types besides archives?
  - answer: Reduce the number of items per page, enable streaming, or process archives
      in smaller batches to improve speed.
    question: What should I do if rendering is slow?
  - answer: Reach out via the [support forum](https://forum.groupdocs.com/c/viewer/9).
    question: Where can I get help or support?
  type: FAQPage
tags:
- convert zip
- GroupDocs.Viewer
- Java archive conversion
- html rendering
- batch conversion
title: Chuyển đổi zip sang html và đặt số mục mỗi trang với GroupDocs.Viewer Java
type: docs
url: /vi/java/export-conversion/groupdocs-viewer-java-convert-archives-html/
weight: 1
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Chuyển đổi zip sang html và đặt số mục mỗi trang với GroupDocs.Viewer Java

Trong nhiều ứng dụng web, bạn cần hiển thị nội dung của một tệp ZIP hoặc RAR trực tiếp trong trình duyệt. **Cách chuyển đổi zip** sang HTML bằng cách sử dụng GroupDocs.Viewer cho Java là một yêu cầu phổ biến, và thư viện cho phép bạn nhúng hình ảnh, CSS và phông chữ để kết quả là một trang duy nhất, di động. Hướng dẫn này sẽ đưa bạn qua mọi bước — từ cài đặt Maven đến việc render đa trang — đồng thời giải thích lý do mỗi tùy chọn quan trọng đối với hiệu suất và khả năng sử dụng.

![Chuyển đổi lưu trữ sang HTML với GroupDocs.Viewer cho Java](/viewer/export-conversion/convert-archives-to-html-java.png)

## Câu trả lời nhanh
- **“set items per page” kiểm soát gì?** Nó xác định số lượng tệp hoặc thư mục từ một lưu trữ sẽ xuất hiện trên mỗi trang HTML được tạo.  
- **Tôi có thể nhúng hình ảnh và CSS trực tiếp vào HTML không?** Có – sử dụng tùy chọn `forEmbeddedResources` để nhúng tài nguyên vào HTML.  
- **Có thể chuyển đổi hàng loạt không?** Chắc chắn; bạn có thể lặp qua một tập hợp các lưu trữ và render mỗi cái với cùng một cài đặt.  
- **Tôi có cần Maven để sử dụng GroupDocs.Viewer không?** Có, thêm phụ thuộc Maven `groupdocs-viewer` như được hiển thị bên dưới.  
- **Các định dạng đầu ra nào được hỗ trợ?** HTML một trang và HTML đa trang đều có sẵn, và thư viện hỗ trợ hơn 50 loại lưu trữ đầu vào.

## “set items per page” là gì trong GroupDocs.Viewer?
Nó cho trình xem biết bao nhiêu mục lưu trữ (tệp hoặc thư mục) sẽ được hiển thị trên mỗi trang HTML khi bạn tạo một tài liệu đa trang. Việc điều chỉnh giá trị này giúp cân bằng kích thước trang và tốc độ điều hướng, đặc biệt đối với các lưu trữ lớn, bằng cách giới hạn lượng dữ liệu tải mỗi trang và giảm thời gian render cho người dùng cuối.

## Tại sao nên nhúng tài nguyên html?
Việc nhúng tài nguyên (hình ảnh, CSS, phông chữ) trực tiếp vào tệp HTML tạo ra một tài liệu duy nhất, di động có thể mở mà không cần các tệp bên ngoài. Điều này lý tưởng cho các tệp đính kèm email, xem offline, hoặc nhúng kết quả vào các trang web khác. Nó cũng loại bỏ nhu cầu quản lý các đường dẫn tài nguyên bên ngoài.

## Yêu cầu trước
- **Thư viện yêu cầu:** Bao gồm GroupDocs.Viewer phiên bản 25.2 hoặc mới hơn.  
- **Môi trường:** Java Development Kit (JDK) đã được cài đặt và cấu hình.  
- **Kiến thức:** Kiến thức cơ bản về Java và quản lý phụ thuộc Maven.  

## Cài đặt Maven GroupDocs Viewer
Thêm repository GroupDocs và phụ thuộc viewer vào tệp `pom.xml` của bạn:

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
GroupDocs.Viewer cung cấp **liên kết dùng thử miễn phí**, giấy phép tạm thời, hoặc tùy chọn mua đầy đủ. Hãy chọn lựa phù hợp với thời gian dự án của bạn.

## Khởi tạo cơ bản
Lớp `Viewer` là điểm vào để render tài liệu và lưu trữ. Sau khi cài đặt Maven, đưa viewer vào mã của bạn:

```java
import com.groupdocs.viewer.Viewer;
// Your initialization code here
```

## Cách render lưu trữ thành html một trang
Lớp `HtmlViewOptions` định nghĩa các cài đặt cho đầu ra HTML, chẳng hạn như nhúng tài nguyên. Tải lưu trữ, cấu hình tùy chọn HTML để nhúng tài nguyên, và render mọi thứ vào một trang tự chứa. Điều này tạo ra một tệp HTML duy nhất chứa tất cả các tệp, hình ảnh, CSS và phông chữ, sẵn sàng cho việc sử dụng offline hoặc đính kèm email.

**Direct answer:** Tạo một thể hiện `Viewer` cho tệp ZIP, gọi `HtmlViewOptions.forEmbeddedResources()`, và thực thi `viewer.view(documentPath, options)`. Điều này tạo ra một tệp HTML duy nhất chứa tất cả các tệp, hình ảnh, CSS và phông chữ, sẵn sàng cho việc sử dụng offline hoặc đính kèm email.

### Bước 1: Xác định thư mục đầu ra
```java
Path outputDirectory = Utils.getOutputDirectoryPath("YOUR_OUTPUT_DIRECTORY");
```

### Bước 2: Đặt tên tệp cho đầu ra một trang
```java
Path pageFilePathFormat = outputDirectory.resolve("RAR_result.html");
```

### Bước 3: Khởi tạo viewer
```java
try (Viewer viewer = new Viewer(TestFiles.SAMPLE_RAR_WITH_FOLDERS)) {
    // Further configuration steps follow
}
```

### Bước 4: Cấu hình tùy chọn render (nhúng tài nguyên html)
Lớp `HtmlViewOptions` định nghĩa các cài đặt cho đầu ra HTML, chẳng hạn như nhúng tài nguyên. Sử dụng `forEmbeddedResources()` để gộp mọi thứ vào một tệp.

```java
HtmlViewOptions options = HtmlViewOptions.forEmbeddedResources(pageFilePathFormat);
```

### Bước 5: Render dưới dạng một trang
```java
options.setRenderToSinglePage(true);
viewer.view(options);
```

## Cách render lưu trữ thành html đa trang và đặt số mục mỗi trang
Lớp `HtmlViewOptions` cũng hỗ trợ phân trang. Bằng cách gọi `options.setItemsPerPage(N)`, bạn chỉ định cho viewer chia lưu trữ thành nhiều tệp HTML, mỗi tệp hiển thị tối đa **N** mục. Cách tiếp cận này cải thiện tốc độ điều hướng cho các lưu trữ lớn đồng thời giữ mỗi trang nhẹ.

**Direct answer:** Sử dụng `HtmlViewOptions.forEmbeddedResources()`, gọi `options.setItemsPerPage(N)`, và render lưu trữ. Viewer sẽ tạo các tệp HTML riêng biệt — một tệp cho mỗi trang — mỗi tệp chứa tối đa **N** mục, giúp tăng tốc độ điều hướng cho các lưu trữ lớn.

### Bước 1: Tái sử dụng thư mục đầu ra
```java
Path outputDirectory = Utils.getOutputDirectoryPath("YOUR_OUTPUT_DIRECTORY");
```

### Bước 2: Định dạng tên tệp cho nhiều trang
```java
Path pageFilePathFormat = outputDirectory.resolve("RAR_result_page_{0}.html");
```

### Bước 3: Khởi tạo lại viewer
```java
try (Viewer viewer = new Viewer(TestFiles.SAMPLE_RAR_WITH_FOLDERS)) {
    // Continue with multi‑page configuration
}
```

### Bước 4: Cấu hình tùy chọn đa trang (nhúng tài nguyên html)
```java
HtmlViewOptions options = HtmlViewOptions.forEmbeddedResources(pageFilePathFormat);
```

### Bước 5: Đặt số mục mỗi trang (từ khóa chính trong hành động)
`options.setItemsPerPage(20); // cách chuyển đổi zip archives với 20 mục mỗi trang`

```java
options.getArchiveOptions().setItemsPerPage(10); // Default is 16
viewer.view(options);
```

## Ứng dụng thực tế
- **Hệ thống quản lý tài liệu:** Thêm chức năng xem trước lưu trữ mà không cần cài đặt các trình xem bổ sung.  
- **Cổng thông tin web:** Cung cấp cho người dùng cách nhanh, không tải xuống để khám phá các tài liệu được đóng gói.  
- **Công cụ hợp tác:** Cho phép các nhóm kiểm tra lưu trữ được chia sẻ trực tiếp trong trình duyệt.

## Các lưu ý về hiệu năng
- **Quản lý tài nguyên:** Giữ mức sử dụng bộ nhớ thấp bằng cách xử lý lưu trữ theo luồng; viewer có thể xử lý các lưu trữ lên tới 500 MB mà không cần tải toàn bộ tệp vào bộ nhớ.  
- **Chuyển đổi hàng loạt lưu trữ:** Lặp qua danh sách các tệp lưu trữ và gọi cùng một logic render để tối đa hoá thông lượng.  
- **Chiến lược cache:** Lưu HTML đã render trong bộ nhớ đệm nếu cùng một lưu trữ được truy cập thường xuyên, giảm thời gian xử lý lặp lại lên tới 70 %.

## Câu hỏi thường gặp
**Q: GroupDocs.Viewer Java là gì?**  
A: GroupDocs.Viewer Java là một thư viện phía máy chủ cho phép render hơn 50 định dạng tài liệu và lưu trữ — bao gồm ZIP và RAR — thành HTML, PDF hoặc tệp hình ảnh mà không cần các ứng dụng bên ngoài.

**Q: Làm sao tôi có thể nhận bản dùng thử miễn phí của GroupDocs.Viewer?**  
A: Truy cập [liên kết dùng thử miễn phí](https://releases.groupdocs.com/viewer/java/) để tải xuống và thử nghiệm.

**Q: Tôi có thể chuyển đổi các loại tài liệu khác ngoài lưu trữ không?**  
A: Có, viewer hỗ trợ PDF, Word, Excel, PowerPoint và hơn 35 định dạng bổ sung.

**Q: Tôi nên làm gì nếu quá trình render chậm?**  
A: Giảm số mục mỗi trang, bật streaming, hoặc xử lý các lưu trữ thành các lô nhỏ hơn để cải thiện tốc độ.

**Q: Tôi có thể nhận trợ giúp hoặc hỗ trợ ở đâu?**  
A: Liên hệ qua [diễn đàn hỗ trợ](https://forum.groupdocs.com/c/viewer/9).

**Q: Có thể nhúng CSS và hình ảnh trực tiếp vào HTML không?**  
A: Chắc chắn — sử dụng `HtmlViewOptions.forEmbeddedResources` như trong các ví dụ.

**Q: Làm sao tôi batch convert một thư mục chứa các lưu trữ?**  
A: Lặp qua từng tệp bằng vòng lặp `for`, áp dụng cùng cấu hình `Viewer` và `HtmlViewOptions` cho mỗi lần lặp.

**Q: Tôi có thể thảo luận các vấn đề với người dùng khác ở đâu?**  
A: Truy cập [diễn đàn GroupDocs](https://forum.groupdocs.com/c/viewer/9) để thảo luận cộng đồng.

## Tài nguyên
- **Tài liệu:** Tìm hiểu sâu hơn về chức năng với [tài liệu GroupDocs](https://docs.groupdocs.com/viewer/java/).  
- **Tham chiếu API:** Khám phá toàn bộ API tại [GroupDocs API](https://reference.groupdocs.com/viewer/java/).  
- **Tải xuống:** Nhận các binary mới nhất từ [trang tải xuống](https://releases.groupdocs.com/viewer/java/).  
- **Mua và cấp phép:** Xem các tùy chọn trên [trang mua](https://purchase.groupdocs.com/buy).  
- **Hỗ trợ và cộng đồng:** Tham gia thảo luận trên [diễn đàn hỗ trợ](https://forum.groupdocs.com/c/viewer/9).  
- **Diễn đàn GroupDocs:** Truy cập trợ giúp cộng đồng tại [diễn đàn GroupDocs](https://forum.groupdocs.com/c/viewer/9).

---

**Cập nhật lần cuối:** 2026-10-10  
**Kiểm tra với:** GroupDocs.Viewer 25.2  
**Tác giả:** GroupDocs

## Hướng dẫn liên quan
- [Cách chuyển đổi zip sang HTML và render thư mục zip trong Java với GroupDocs.Viewer](/viewer/java/advanced-rendering/render-archive-folders-groupdocs-viewer-java/)
- [chuyển đổi zip sang pdf với GroupDocs.Viewer Java - Tên tệp tùy chỉnh](/viewer/java/advanced-rendering/groupdocs-viewer-java-custom-filenames-rendering-archives/)
- [Cách chuyển đổi DOCX sang HTML bằng GroupDocs.Viewer cho Java: Hướng dẫn chi tiết](/viewer/java/export-conversion/convert-docx-to-html-groupdocs-viewer-java/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}